# OpenSortIdKey

- ea: `0x180019010`
- end: `0x1800190e8`
- name: `OpenSortIdKey`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018c78`

## callees

- `0x180019010`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180019096`
- `ntdll!NtOpenKey` at `0x180019096`
- `ntdll!NtClose` at `0x1800190bf`
- `ntdll!NtClose` at `0x1800190bf`
- `ntdll!RtlInitUnicodeString` at `0x180019057`
- `ntdll!RtlInitUnicodeString` at `0x180019057`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800190d5`

## string_xrefs

- `0x180019040`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\Sorting\Ids`

## pseudocode

```c
__int64 OpenSortIdKey()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  if ( hSortIdKey )
    return 1;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\Sorting\\Ids");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hSortIdKey, (signed __int64)KeyHandle, 0) )
      NtClose(KeyHandle);
    return 1;
  }
  SetLastError(0x3F1u);
  return 0;
}

```

## disassembly

```asm
0x180019010  push    rbp
0x180019012  mov     rbp, rsp
0x180019015  sub     rsp, 60h
0x180019019  cmp     cs:hSortIdKey, 0
0x180019021  jz      short loc_18001902F
0x180019023  mov     eax, 1
0x180019028  add     rsp, 60h
0x18001902c  pop     rbp
0x18001902d  retn
0x18001902f  xorps   xmm0, xmm0
0x180019032  mov     [rbp+KeyHandle], 0
0x18001903a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001903e  xor     eax, eax
0x180019040  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x180019047  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001904b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18001904f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180019053  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180019057  call    cs:__imp_RtlInitUnicodeString
0x18001905e  nop     dword ptr [rax+rax+00h]
0x180019063  lea     rax, [rbp+DestinationString]
0x180019067  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001906e  xorps   xmm0, xmm0
0x180019071  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180019075  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180019079  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180019081  mov     edx, 20019h; DesiredAccess
0x180019086  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001908d  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180019091  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180019096  call    cs:__imp_NtOpenKey
0x18001909d  nop     dword ptr [rax+rax+00h]
0x1800190a2  test    eax, eax
0x1800190a4  js      short loc_1800190D0
0x1800190a6  mov     rcx, [rbp+KeyHandle]
0x1800190aa  xor     eax, eax
0x1800190ac  lock cmpxchg cs:hSortIdKey, rcx
0x1800190b5  jz      loc_180019023
0x1800190bb  mov     rcx, [rbp+KeyHandle]; Handle
0x1800190bf  call    cs:__imp_NtClose
0x1800190c6  nop     dword ptr [rax+rax+00h]
0x1800190cb  jmp     loc_180019023
0x1800190d0  mov     ecx, 3F1h; dwErrCode
0x1800190d5  call    cs:__imp_SetLastError
0x1800190dc  nop     dword ptr [rax+rax+00h]
0x1800190e1  xor     eax, eax
0x1800190e3  jmp     loc_180019028
```
