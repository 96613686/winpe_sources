# MRxDAVCreateEncryptedDirectoryKey

- ea: `0x140001c30`
- end: `0x140001ddd`
- name: `MRxDAVCreateEncryptedDirectoryKey`
- size: `429`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140011eec`
- `0x140015c30`
- `0x14001e6a0`
- `0x140022a80`

## callees

- `0x140001680`
- `0x140001c30`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140001da8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001da8`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001c77`
- `ntoskrnl!RtlInitUnicodeString` at `0x140001c77`
- `ntoskrnl!ZwClose` at `0x140001d78`
- `ntoskrnl!ZwClose` at `0x140001d78`
- `ntoskrnl!ZwOpenKey` at `0x140001cb8`
- `ntoskrnl!ZwOpenKey` at `0x140001cb8`
- `ntoskrnl!ZwCreateKey` at `0x140001cef`
- `ntoskrnl!ZwCreateKey` at `0x140001cef`
- `ntoskrnl!ZwSetValueKey` at `0x140001d59`
- `ntoskrnl!ZwSetValueKey` at `0x140001d59`
- `ntoskrnl!ZwQueryValueKey` at `0x140001d26`
- `ntoskrnl!ZwQueryValueKey` at `0x140001d26`

## string_xrefs

- `0x140001c60`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\MRxDAV\EncryptedDirectories`

## pseudocode

```c
__int64 __fastcall MRxDAVCreateEncryptedDirectoryKey(PUNICODE_STRING ValueName)
{
  unsigned int v2; // edi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int Data; // [rsp+A8h] [rbp+28h] BYREF
  ULONG ResultLength; // [rsp+B0h] [rbp+30h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+38h] BYREF

  Data = 0;
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
  if ( !ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) )
  {
    v2 = ZwQueryValueKey(KeyHandle, ValueName, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( v2 != -1073741772 )
    {
      if ( v2 == -1073741789 )
        v2 = 0;
LABEL_8:
      ZwClose(KeyHandle);
      if ( !v2 )
        return v2;
      goto LABEL_9;
    }
LABEL_5:
    v2 = ZwSetValueKey(KeyHandle, ValueName, 0, 4u, &Data, 4u);
    goto LABEL_8;
  }
  v2 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
  if ( !v2 )
    goto LABEL_5;
LABEL_9:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qD(v3, 134, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x140001c30  push    rbp
0x140001c32  push    rbx
0x140001c33  push    rdi
0x140001c34  mov     rbp, rsp
0x140001c37  sub     rsp, 80h
0x140001c3e  xorps   xmm0, xmm0
0x140001c41  mov     [rbp+Data], 0
0x140001c48  mov     rbx, rcx
0x140001c4b  mov     [rbp+KeyHandle], 0
0x140001c53  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140001c57  xor     eax, eax
0x140001c59  mov     [rbp+ResultLength], 0
0x140001c60  lea     rdx, SourceString; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140001c67  lea     rcx, [rbp+DestinationString]; DestinationString
0x140001c6b  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140001c6f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140001c73  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140001c77  call    cs:__imp_RtlInitUnicodeString
0x140001c7e  nop     dword ptr [rax+rax+00h]
0x140001c83  lea     rax, [rbp+DestinationString]
0x140001c87  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140001c8e  xorps   xmm0, xmm0
0x140001c91  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140001c95  mov     edi, 0F003Fh
0x140001c9a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140001ca2  mov     edx, edi; DesiredAccess
0x140001ca4  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140001cab  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140001caf  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140001cb3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140001cb8  call    cs:__imp_ZwOpenKey
0x140001cbf  nop     dword ptr [rax+rax+00h]
0x140001cc4  test    eax, eax
0x140001cc6  jz      short loc_140001D07
0x140001cc8  mov     [rsp+80h+Disposition], 0; Disposition
0x140001cd1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140001cd5  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x140001cdd  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140001ce1  xor     r9d, r9d; TitleIndex
0x140001ce4  mov     [rsp+80h+Class], 0; Class
0x140001ced  mov     edx, edi; DesiredAccess
0x140001cef  call    cs:__imp_ZwCreateKey
0x140001cf6  nop     dword ptr [rax+rax+00h]
0x140001cfb  mov     edi, eax
0x140001cfd  test    eax, eax
0x140001cff  jnz     loc_140001D88
0x140001d05  jmp     short loc_140001D3B
0x140001d07  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140001d0b  lea     rax, [rbp+ResultLength]
0x140001d0f  xor     r9d, r9d; KeyValueInformation
0x140001d12  mov     qword ptr [rsp+80h+CreateOptions], rax; ResultLength
0x140001d17  mov     rdx, rbx; ValueName
0x140001d1a  mov     dword ptr [rsp+80h+Class], 0; Length
0x140001d22  lea     r8d, [r9+2]; KeyValueInformationClass
0x140001d26  call    cs:__imp_ZwQueryValueKey
0x140001d2d  nop     dword ptr [rax+rax+00h]
0x140001d32  mov     edi, eax
0x140001d34  cmp     eax, 0C0000034h
0x140001d39  jnz     short loc_140001D69
0x140001d3b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140001d3f  lea     rax, [rbp+Data]
0x140001d43  mov     r9d, 4; Type
0x140001d49  xor     r8d, r8d; TitleIndex
0x140001d4c  mov     [rsp+80h+CreateOptions], r9d; DataSize
0x140001d51  mov     rdx, rbx; ValueName
0x140001d54  mov     [rsp+80h+Class], rax; Data
0x140001d59  call    cs:__imp_ZwSetValueKey
0x140001d60  nop     dword ptr [rax+rax+00h]
0x140001d65  mov     edi, eax
0x140001d67  jmp     short loc_140001D74
0x140001d69  xor     eax, eax
0x140001d6b  cmp     edi, 0C0000023h
0x140001d71  cmovz   edi, eax
0x140001d74  mov     rcx, [rbp+KeyHandle]; Handle
0x140001d78  call    cs:__imp_ZwClose
0x140001d7f  nop     dword ptr [rax+rax+00h]
0x140001d84  test    edi, edi
0x140001d86  jz      short loc_140001DCF
0x140001d88  mov     rbx, cs:WPP_GLOBAL_Control
0x140001d8f  lea     rax, WPP_GLOBAL_Control
0x140001d96  cmp     rbx, rax
0x140001d99  jz      short loc_140001DCF
0x140001d9b  test    dword ptr [rbx+2Ch], 2000h
0x140001da2  jz      short loc_140001DCF
0x140001da4  mov     rbx, [rbx+18h]
0x140001da8  call    cs:__imp_PsGetCurrentThreadId
0x140001daf  nop     dword ptr [rax+rax+00h]
0x140001db4  mov     edx, 86h
0x140001db9  mov     dword ptr [rsp+80h+Class], edi
0x140001dbd  mov     r9, rax
0x140001dc0  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140001dc7  mov     rcx, rbx
0x140001dca  call    WPP_SF_qD
0x140001dcf  mov     eax, edi
0x140001dd1  add     rsp, 80h
0x140001dd8  pop     rdi
0x140001dd9  pop     rbx
0x140001dda  pop     rbp
0x140001ddb  retn
```
