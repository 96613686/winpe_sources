# MRxDAVQueryEncryptedDirectoryKey

- ea: `0x140002374`
- end: `0x1400024a8`
- name: `MRxDAVQueryEncryptedDirectoryKey`
- size: `308`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400130e0`
- `0x140015c30`
- `0x14001e6a0`

## callees

- `0x140001680`
- `0x140002374`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000246c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000246c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400023b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400023b8`
- `ntoskrnl!ZwClose` at `0x14000243c`
- `ntoskrnl!ZwClose` at `0x14000243c`
- `ntoskrnl!ZwOpenKey` at `0x1400023f7`
- `ntoskrnl!ZwOpenKey` at `0x1400023f7`
- `ntoskrnl!ZwQueryValueKey` at `0x140002424`
- `ntoskrnl!ZwQueryValueKey` at `0x140002424`

## string_xrefs

- `0x1400023a1`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\MRxDAV\EncryptedDirectories`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryEncryptedDirectoryKey(PUNICODE_STRING ValueName)
{
  unsigned int v2; // edi
  NTSTATUS v3; // eax
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+18h] BYREF
  void *KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\MRxDAV\\EncryptedDirectories");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( v2 )
    goto LABEL_6;
  v3 = ZwQueryValueKey(KeyHandle, ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
  if ( v3 != -1073741789 )
    v2 = v3;
  ZwClose(KeyHandle);
  if ( v2 )
  {
LABEL_6:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_qD(v4, 136, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId, v2);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140002374  mov     [rsp-8+arg_0], rbx
0x140002379  mov     [rsp-8+arg_18], rdi
0x14000237e  push    rbp
0x14000237f  mov     rbp, rsp
0x140002382  sub     rsp, 70h
0x140002386  xorps   xmm0, xmm0
0x140002389  mov     [rbp+KeyHandle], 0
0x140002391  mov     rbx, rcx
0x140002394  mov     [rbp+arg_8], 0
0x14000239b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000239f  xor     eax, eax
0x1400023a1  lea     rdx, SourceString; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1400023a8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400023ac  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400023b0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400023b4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400023b8  call    cs:__imp_RtlInitUnicodeString
0x1400023bf  nop     dword ptr [rax+rax+00h]
0x1400023c4  lea     rax, [rbp+DestinationString]
0x1400023c8  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400023cf  xorps   xmm0, xmm0
0x1400023d2  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400023d6  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400023da  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400023e2  mov     edx, 0F003Fh; DesiredAccess
0x1400023e7  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400023ee  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400023f2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400023f7  call    cs:__imp_ZwOpenKey
0x1400023fe  nop     dword ptr [rax+rax+00h]
0x140002403  mov     edi, eax
0x140002405  test    eax, eax
0x140002407  jnz     short loc_14000244C
0x140002409  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000240d  lea     rax, [rbp+arg_8]
0x140002411  mov     [rsp+70h+ResultLength], rax; ResultLength
0x140002416  lea     r8d, [rdi+2]; KeyValueInformationClass
0x14000241a  xor     r9d, r9d; KeyValueInformation
0x14000241d  mov     [rsp+70h+Length], edi; Length
0x140002421  mov     rdx, rbx; ValueName
0x140002424  call    cs:__imp_ZwQueryValueKey
0x14000242b  nop     dword ptr [rax+rax+00h]
0x140002430  mov     rcx, [rbp+KeyHandle]; Handle
0x140002434  cmp     eax, 0C0000023h
0x140002439  cmovnz  edi, eax
0x14000243c  call    cs:__imp_ZwClose
0x140002443  nop     dword ptr [rax+rax+00h]
0x140002448  test    edi, edi
0x14000244a  jz      short loc_140002493
0x14000244c  mov     rbx, cs:WPP_GLOBAL_Control
0x140002453  lea     rax, WPP_GLOBAL_Control
0x14000245a  cmp     rbx, rax
0x14000245d  jz      short loc_140002493
0x14000245f  test    dword ptr [rbx+2Ch], 4000h
0x140002466  jz      short loc_140002493
0x140002468  mov     rbx, [rbx+18h]
0x14000246c  call    cs:__imp_PsGetCurrentThreadId
0x140002473  nop     dword ptr [rax+rax+00h]
0x140002478  mov     edx, 88h
0x14000247d  mov     [rsp+70h+Length], edi
0x140002481  mov     r9, rax
0x140002484  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x14000248b  mov     rcx, rbx
0x14000248e  call    WPP_SF_qD
0x140002493  lea     r11, [rsp+70h+var_s0]
0x140002498  mov     eax, edi
0x14000249a  mov     rbx, [r11+10h]
0x14000249e  mov     rdi, [r11+28h]
0x1400024a2  mov     rsp, r11
0x1400024a5  pop     rbp
0x1400024a6  retn
```
