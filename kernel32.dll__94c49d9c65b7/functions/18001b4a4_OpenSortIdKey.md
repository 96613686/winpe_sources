# OpenSortIdKey

- ea: `0x18001b4a4`
- end: `0x18001b563`
- name: `OpenSortIdKey`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b124`

## callees

- `0x18001b4a4`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18001b523`
- `ntdll!NtOpenKey` at `0x18001b523`
- `ntdll!NtClose` at `0x18001b546`
- `ntdll!NtClose` at `0x18001b546`
- `ntdll!RtlInitUnicodeString` at `0x18001b4ea`
- `ntdll!RtlInitUnicodeString` at `0x18001b4ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b556`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b556`

## string_xrefs

- `0x18001b4d3`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\Sorting\Ids`

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
0x18001b4a4  push    rbp
0x18001b4a6  mov     rbp, rsp
0x18001b4a9  sub     rsp, 60h
0x18001b4ad  cmp     cs:hSortIdKey, 0
0x18001b4b5  jz      short loc_18001B4C2
0x18001b4b7  mov     eax, 1
0x18001b4bc  add     rsp, 60h
0x18001b4c0  pop     rbp
0x18001b4c1  retn
0x18001b4c2  xorps   xmm0, xmm0
0x18001b4c5  mov     [rbp+KeyHandle], 0
0x18001b4cd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001b4d1  xor     eax, eax
0x18001b4d3  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001b4da  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001b4de  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18001b4e2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001b4e6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001b4ea  call    cs:__imp_RtlInitUnicodeString
0x18001b4f0  lea     rax, [rbp+DestinationString]
0x18001b4f4  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001b4fb  xorps   xmm0, xmm0
0x18001b4fe  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001b502  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001b506  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001b50e  mov     edx, 20019h; DesiredAccess
0x18001b513  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001b51a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18001b51e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b523  call    cs:__imp_NtOpenKey
0x18001b529  test    eax, eax
0x18001b52b  js      short loc_18001B551
0x18001b52d  mov     rcx, [rbp+KeyHandle]
0x18001b531  xor     eax, eax
0x18001b533  lock cmpxchg cs:hSortIdKey, rcx
0x18001b53c  jz      loc_18001B4B7
0x18001b542  mov     rcx, [rbp+KeyHandle]; Handle
0x18001b546  call    cs:__imp_NtClose
0x18001b54c  jmp     loc_18001B4B7
0x18001b551  mov     ecx, 3F1h; dwErrCode
0x18001b556  call    cs:__imp_SetLastError
0x18001b55c  xor     eax, eax
0x18001b55e  jmp     loc_18001B4BC
```
