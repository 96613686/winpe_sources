# IopSymlinkQueryEnabledClasses

- ea: `0x140af7ea8`
- end: `0x140af8032`
- name: `IopSymlinkQueryEnabledClasses`
- size: `394`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14075d730`

## callees

- `0x140403380`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x140af7ea8`

## string_xrefs

- `0x140af7f68`: `SymlinkRemoteToRemoteEvaluation`
- `0x140af7f7f`: `SymlinkRemoteToLocalEvaluation`
- `0x140af7f3e`: `SymlinkLocalToLocalEvaluation`
- `0x140af7f54`: `SymlinkLocalToRemoteEvaluation`

## pseudocode

```c
__int64 __fastcall IopSymlinkQueryEnabledClasses(PCWSTR SourceString)
{
  NTSTATUS v1; // esi
  __int32 v2; // ebx
  unsigned __int16 v3; // di
  ULONG ResultLength; // [rsp+30h] [rbp-99h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-89h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-79h] BYREF
  UNICODE_STRING v9; // [rsp+80h] [rbp-49h] BYREF
  _DWORD v10[2]; // [rsp+90h] [rbp-39h]
  UNICODE_STRING v11; // [rsp+98h] [rbp-31h] BYREF
  int v12; // [rsp+A8h] [rbp-21h]
  UNICODE_STRING v13; // [rsp+B0h] [rbp-19h] BYREF
  int v14; // [rsp+C0h] [rbp-9h]
  UNICODE_STRING v15; // [rsp+C8h] [rbp-1h] BYREF
  int v16; // [rsp+D8h] [rbp+Fh]
  _BYTE KeyValueInformation[12]; // [rsp+E0h] [rbp+17h] BYREF
  int v18; // [rsp+ECh] [rbp+23h]

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
    v2 = 0;
    RtlInitUnicodeString(&v9, L"SymlinkLocalToLocalEvaluation");
    v10[0] = 1;
    RtlInitUnicodeString(&v11, L"SymlinkLocalToRemoteEvaluation");
    v12 = 2;
    RtlInitUnicodeString(&v13, L"SymlinkRemoteToRemoteEvaluation");
    v14 = 8;
    RtlInitUnicodeString(&v15, L"SymlinkRemoteToLocalEvaluation");
    v3 = 0;
    v16 = 4;
    while ( v3 < 4u )
    {
      v1 = ZwQueryValueKey(
             KeyHandle,
             (UNICODE_STRING *)((char *)&v9 + 24 * v3),
             KeyValuePartialInformation,
             KeyValueInformation,
             0x14u,
             &ResultLength);
      if ( v1 < 0 )
        goto LABEL_9;
      if ( v18 )
        v2 += v10[6 * v3];
      ++v3;
    }
    _InterlockedExchange(&IopSymlinkEnabledTypes, v2);
  }
LABEL_9:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140af7ea8  mov     [rsp-8+arg_8], rbx
0x140af7ead  mov     [rsp-8+arg_10], rsi
0x140af7eb2  push    rbp
0x140af7eb3  push    rdi
0x140af7eb4  push    r12
0x140af7eb6  push    r13
0x140af7eb8  push    r14
0x140af7eba  lea     rbp, [rsp-37h]
0x140af7ebf  sub     rsp, 100h
0x140af7ec6  mov     rax, cs:__security_cookie
0x140af7ecd  xor     rax, rsp
0x140af7ed0  mov     [rbp+57h+var_28], rax
0x140af7ed4  xorps   xmm0, xmm0
0x140af7ed7  mov     [rsp+120h+KeyHandle], 0
0x140af7ee0  mov     rdx, rcx; SourceString
0x140af7ee3  mov     [rsp+120h+var_F0], 0
0x140af7eeb  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x140af7ef0  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x140af7ef5  call    RtlInitUnicodeString
0x140af7efa  xor     eax, eax
0x140af7efc  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140af7f04  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140af7f08  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140af7f0c  lea     rax, [rsp+120h+DestinationString]
0x140af7f11  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140af7f19  xorps   xmm0, xmm0
0x140af7f1c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140af7f20  mov     edx, 20019h; DesiredAccess
0x140af7f25  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140af7f2a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140af7f2f  call    ZwOpenKey
0x140af7f34  mov     esi, eax
0x140af7f36  test    eax, eax
0x140af7f38  js      loc_140AF7FF8
0x140af7f3e  lea     rdx, aSymlinklocalto; "SymlinkLocalToLocalEvaluation"
0x140af7f45  xor     ebx, ebx
0x140af7f47  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x140af7f4b  call    RtlInitUnicodeString
0x140af7f50  lea     r12d, [rbx+1]
0x140af7f54  lea     rdx, aSymlinklocalto_0; "SymlinkLocalToRemoteEvaluation"
0x140af7f5b  mov     [rbp+57h+var_90], r12d
0x140af7f5f  lea     rcx, [rbp+57h+var_88]; DestinationString
0x140af7f63  call    RtlInitUnicodeString
0x140af7f68  lea     rdx, aSymlinkremotet; "SymlinkRemoteToRemoteEvaluation"
0x140af7f6f  mov     [rbp+57h+var_78], 2
0x140af7f76  lea     rcx, [rbp+57h+var_70]; DestinationString
0x140af7f7a  call    RtlInitUnicodeString
0x140af7f7f  lea     rdx, aSymlinkremotet_0; "SymlinkRemoteToLocalEvaluation"
0x140af7f86  mov     [rbp+57h+var_60], 8
0x140af7f8d  lea     rcx, [rbp+57h+var_58]; DestinationString
0x140af7f91  call    RtlInitUnicodeString
0x140af7f96  lea     r13d, [rbx+4]
0x140af7f9a  xor     edi, edi
0x140af7f9c  mov     [rbp+57h+var_48], r13d
0x140af7fa0  cmp     di, r13w
0x140af7fa4  jnb     short loc_140AF7FF2
0x140af7fa6  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x140af7fab  lea     rdx, [rbp+57h+var_A0]
0x140af7faf  movzx   eax, di
0x140af7fb2  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140af7fb6  mov     r8d, 2; KeyValueInformationClass
0x140af7fbc  lea     r14, [rax+rax*2]
0x140af7fc0  lea     rax, [rsp+120h+var_F0]
0x140af7fc5  mov     [rsp+120h+ResultLength], rax; ResultLength
0x140af7fca  lea     rdx, [rdx+r14*8]; ValueName
0x140af7fce  mov     [rsp+120h+Length], 14h; Length
0x140af7fd6  call    ZwQueryValueKey
0x140af7fdb  mov     esi, eax
0x140af7fdd  test    eax, eax
0x140af7fdf  js      short loc_140AF7FF8
0x140af7fe1  cmp     [rbp+57h+var_34], 0
0x140af7fe5  jz      short loc_140AF7FEC
0x140af7fe7  add     ebx, [rbp+r14*8+57h+var_90]
0x140af7fec  add     di, r12w
0x140af7ff0  jmp     short loc_140AF7FA0
0x140af7ff2  xchg    ebx, cs:IopSymlinkEnabledTypes
0x140af7ff8  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x140af7ffd  test    rcx, rcx
0x140af8000  jz      short loc_140AF8007
0x140af8002  call    ZwClose
0x140af8007  mov     eax, esi
0x140af8009  mov     rcx, [rbp+57h+var_28]
0x140af800d  xor     rcx, rsp; StackCookie
0x140af8010  call    __security_check_cookie
0x140af8015  lea     r11, [rsp+120h+var_20]
0x140af801d  mov     rbx, [r11+38h]
0x140af8021  mov     rsi, [r11+40h]
0x140af8025  mov     rsp, r11
0x140af8028  pop     r14
0x140af802a  pop     r13
0x140af802c  pop     r12
0x140af802e  pop     rdi
0x140af802f  pop     rbp
0x140af8030  retn
```
