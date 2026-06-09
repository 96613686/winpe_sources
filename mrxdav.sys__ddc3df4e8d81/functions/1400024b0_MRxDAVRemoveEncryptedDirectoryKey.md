# MRxDAVRemoveEncryptedDirectoryKey

- ea: `0x1400024b0`
- end: `0x1400025c3`
- name: `MRxDAVRemoveEncryptedDirectoryKey`
- size: `275`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `3`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140011eec`
- `0x1400128a0`
- `0x140022a80`

## callees

- `0x140001680`
- `0x1400024b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140002587`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002587`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400024ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400024ed`
- `ntoskrnl!ZwClose` at `0x140002557`
- `ntoskrnl!ZwClose` at `0x140002557`
- `ntoskrnl!ZwOpenKey` at `0x14000252c`
- `ntoskrnl!ZwOpenKey` at `0x14000252c`
- `ntoskrnl!ZwDeleteValueKey` at `0x140002545`
- `ntoskrnl!ZwDeleteValueKey` at `0x140002545`

## string_xrefs

- `0x1400024d0`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\MRxDAV\EncryptedDirectories`

## pseudocode

```c
__int64 __fastcall MRxDAVRemoveEncryptedDirectoryKey(PUNICODE_STRING ValueName)
{
  unsigned int v2; // edi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+88h] [rbp+18h] BYREF

  KeyHandle = 0;
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
  if ( v2 || (v2 = ZwDeleteValueKey(KeyHandle, ValueName), ZwClose(KeyHandle), v2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_qD(v3, 135, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId, v2);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400024b0  mov     [rsp-8+arg_0], rbx
0x1400024b5  mov     [rsp-8+arg_10], rdi
0x1400024ba  push    rbp
0x1400024bb  mov     rbp, rsp
0x1400024be  sub     rsp, 70h
0x1400024c2  xorps   xmm0, xmm0
0x1400024c5  mov     [rbp+KeyHandle], 0
0x1400024cd  mov     rbx, rcx
0x1400024d0  lea     rdx, SourceString; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1400024d7  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400024db  xor     eax, eax
0x1400024dd  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400024e1  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400024e5  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400024e9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400024ed  call    cs:__imp_RtlInitUnicodeString
0x1400024f4  nop     dword ptr [rax+rax+00h]
0x1400024f9  lea     rax, [rbp+DestinationString]
0x1400024fd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140002504  xorps   xmm0, xmm0
0x140002507  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000250b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000250f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140002517  mov     edx, 0F003Fh; DesiredAccess
0x14000251c  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140002523  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140002527  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000252c  call    cs:__imp_ZwOpenKey
0x140002533  nop     dword ptr [rax+rax+00h]
0x140002538  mov     edi, eax
0x14000253a  test    eax, eax
0x14000253c  jnz     short loc_140002567
0x14000253e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140002542  mov     rdx, rbx; ValueName
0x140002545  call    cs:__imp_ZwDeleteValueKey
0x14000254c  nop     dword ptr [rax+rax+00h]
0x140002551  mov     rcx, [rbp+KeyHandle]; Handle
0x140002555  mov     edi, eax
0x140002557  call    cs:__imp_ZwClose
0x14000255e  nop     dword ptr [rax+rax+00h]
0x140002563  test    edi, edi
0x140002565  jz      short loc_1400025AE
0x140002567  mov     rbx, cs:WPP_GLOBAL_Control
0x14000256e  lea     rax, WPP_GLOBAL_Control
0x140002575  cmp     rbx, rax
0x140002578  jz      short loc_1400025AE
0x14000257a  test    dword ptr [rbx+2Ch], 2000h
0x140002581  jz      short loc_1400025AE
0x140002583  mov     rbx, [rbx+18h]
0x140002587  call    cs:__imp_PsGetCurrentThreadId
0x14000258e  nop     dword ptr [rax+rax+00h]
0x140002593  mov     edx, 87h
0x140002598  mov     [rsp+70h+var_50], edi
0x14000259c  mov     r9, rax
0x14000259f  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400025a6  mov     rcx, rbx
0x1400025a9  call    WPP_SF_qD
0x1400025ae  lea     r11, [rsp+70h+var_s0]
0x1400025b3  mov     eax, edi
0x1400025b5  mov     rbx, [r11+10h]
0x1400025b9  mov     rdi, [r11+20h]
0x1400025bd  mov     rsp, r11
0x1400025c0  pop     rbp
0x1400025c1  retn
```
