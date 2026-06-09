# GetNlsTablePath

- ea: `0x14002c2e0`
- end: `0x14002c4be`
- name: `GetNlsTablePath`
- size: `478`
- prototype: `__int64 __fastcall(ULONG Value, PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002c4c4`

## callees

- `0x14002c2e0`
- `0x14003aba0`
- `0x14003adc0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002c43f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002c43f`
- `ntoskrnl!ZwOpenKey` at `0x14002c36d`
- `ntoskrnl!ZwOpenKey` at `0x14002c36d`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14002c3c5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14002c3c5`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c3f3`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c3f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c332`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c42c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c332`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c42c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c47b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c47b`
- `ntoskrnl!ZwClose` at `0x14002c48b`
- `ntoskrnl!ZwClose` at `0x14002c48b`
- `ntoskrnl!ExAllocatePool2` at `0x14002c394`
- `ntoskrnl!ExAllocatePool2` at `0x14002c394`

## string_xrefs

- `0x14002c30e`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\CodePage`
- `0x14002c41a`: `\SystemRoot\System32\`

## pseudocode

```c
__int64 __fastcall GetNlsTablePath(ULONG Value, PUNICODE_STRING DestinationString)
{
  unsigned int v4; // r14d
  __int64 Pool2; // rdi
  __int16 v6; // bx
  __int64 v7; // rcx
  int v8; // ebx
  ULONG Length; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationStringa; // [rsp+40h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-39h] BYREF
  UNICODE_STRING SourceString; // [rsp+80h] [rbp-9h] BYREF
  char v15; // [rsp+90h] [rbp+7h] BYREF

  v4 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationStringa = 0;
  RtlInitUnicodeString(&DestinationStringa, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\CodePage");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationStringa;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes) >= 0 )
  {
    Length = 544;
    Pool2 = ExAllocatePool2(258, 544, 844260942);
    if ( Pool2 )
    {
      *(_DWORD *)&DestinationStringa.Length = 2621440;
      DestinationStringa.Buffer = (PWSTR)&v15;
      RtlIntegerToUnicodeString(Value, 0xAu, &DestinationStringa);
      if ( ZwQueryValueKey(KeyHandle, &DestinationStringa, KeyValuePartialInformation, (PVOID)Pool2, Length, &Length) >= 0
        && *(_DWORD *)(Pool2 + 4) == 1
        && (unsigned int)(*(_DWORD *)(Pool2 + 8) - 3) <= 0xFFFC )
      {
        v6 = *(_WORD *)(Pool2 + 8);
        SourceString = 0;
        RtlInitUnicodeString(&SourceString, L"\\SystemRoot\\System32\\");
        RtlCopyUnicodeString(DestinationString, &SourceString);
        v7 = DestinationString->Length;
        v8 = (unsigned __int16)(v6 - 2);
        if ( DestinationString->MaximumLength - (int)v7 >= v8 )
        {
          memmove((char *)DestinationString->Buffer + v7, (const void *)(Pool2 + 12), (unsigned int)v8);
          DestinationString->Length += v8;
          v4 = 1;
        }
      }
      ExFreePoolWithTag((PVOID)Pool2, 0);
    }
    ZwClose(KeyHandle);
  }
  return v4;
}

```

## disassembly

```asm
0x14002c2e0  mov     [rsp-8+arg_10], rbx
0x14002c2e5  push    rbp
0x14002c2e6  push    rsi
0x14002c2e7  push    rdi
0x14002c2e8  push    r14
0x14002c2ea  push    r15
0x14002c2ec  lea     rbp, [rsp-37h]
0x14002c2f1  sub     rsp, 0C0h
0x14002c2f8  mov     rax, cs:__security_cookie
0x14002c2ff  xor     rax, rsp
0x14002c302  mov     [rbp+57h+var_28], rax
0x14002c306  xorps   xmm0, xmm0
0x14002c309  mov     rsi, rdx
0x14002c30c  mov     ebx, ecx
0x14002c30e  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002c315  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002c319  xor     r14d, r14d
0x14002c31c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002c320  xor     eax, eax
0x14002c322  mov     [rbp+57h+KeyHandle], r14
0x14002c326  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002c32a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002c32e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002c332  call    cs:__imp_RtlInitUnicodeString
0x14002c339  nop     dword ptr [rax+rax+00h]
0x14002c33e  lea     rax, [rbp+57h+DestinationString]
0x14002c342  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002c349  xorps   xmm0, xmm0
0x14002c34c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002c350  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002c354  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14002c358  mov     edx, 80000000h; DesiredAccess
0x14002c35d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002c364  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002c368  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002c36d  call    cs:__imp_ZwOpenKey
0x14002c374  nop     dword ptr [rax+rax+00h]
0x14002c379  test    eax, eax
0x14002c37b  js      loc_14002C497
0x14002c381  mov     edx, 220h
0x14002c386  mov     ecx, 102h
0x14002c38b  mov     r8d, 3252664Eh
0x14002c391  mov     [rbp+57h+var_B0], edx
0x14002c394  call    cs:__imp_ExAllocatePool2
0x14002c39b  nop     dword ptr [rax+rax+00h]
0x14002c3a0  mov     rdi, rax
0x14002c3a3  test    rax, rax
0x14002c3a6  jz      loc_14002C487
0x14002c3ac  lea     rax, [rbp+57h+var_50]
0x14002c3b0  mov     dword ptr [rbp+57h+DestinationString.Length], 280000h
0x14002c3b7  lea     r8, [rbp+57h+DestinationString]; String
0x14002c3bb  mov     [rbp+57h+DestinationString.Buffer], rax
0x14002c3bf  lea     edx, [r14+0Ah]; Base
0x14002c3c3  mov     ecx, ebx; Value
0x14002c3c5  call    cs:__imp_RtlIntegerToUnicodeString
0x14002c3cc  nop     dword ptr [rax+rax+00h]
0x14002c3d1  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002c3d5  lea     rax, [rbp+57h+var_B0]
0x14002c3d9  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14002c3de  lea     r15d, [r14+2]
0x14002c3e2  mov     eax, [rbp+57h+var_B0]
0x14002c3e5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14002c3e9  mov     r9, rdi; KeyValueInformation
0x14002c3ec  mov     [rsp+0E0h+Length], eax; Length
0x14002c3f0  mov     r8d, r15d; KeyValueInformationClass
0x14002c3f3  call    cs:__imp_ZwQueryValueKey
0x14002c3fa  nop     dword ptr [rax+rax+00h]
0x14002c3ff  test    eax, eax
0x14002c401  js      short loc_14002C476
0x14002c403  cmp     dword ptr [rdi+4], 1
0x14002c407  jnz     short loc_14002C476
0x14002c409  mov     eax, [rdi+8]
0x14002c40c  sub     eax, 3
0x14002c40f  cmp     eax, 0FFFCh
0x14002c414  ja      short loc_14002C476
0x14002c416  movzx   ebx, word ptr [rdi+8]
0x14002c41a  lea     rdx, aSystemrootSyst; "\\SystemRoot\\System32\\"
0x14002c421  xorps   xmm0, xmm0
0x14002c424  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14002c428  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x14002c42c  call    cs:__imp_RtlInitUnicodeString
0x14002c433  nop     dword ptr [rax+rax+00h]
0x14002c438  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14002c43c  mov     rcx, rsi; DestinationString
0x14002c43f  call    cs:__imp_RtlCopyUnicodeString
0x14002c446  nop     dword ptr [rax+rax+00h]
0x14002c44b  movzx   ecx, word ptr [rsi]
0x14002c44e  sub     bx, r15w
0x14002c452  movzx   eax, word ptr [rsi+2]
0x14002c456  sub     eax, ecx
0x14002c458  movzx   ebx, bx
0x14002c45b  cmp     eax, ebx
0x14002c45d  jl      short loc_14002C476
0x14002c45f  add     rcx, [rsi+8]; void *
0x14002c463  lea     rdx, [rdi+0Ch]; Src
0x14002c467  mov     r8d, ebx; Size
0x14002c46a  call    memmove
0x14002c46f  add     [rsi], bx
0x14002c472  lea     r14d, [r15-1]
0x14002c476  xor     edx, edx; Tag
0x14002c478  mov     rcx, rdi; P
0x14002c47b  call    cs:__imp_ExFreePoolWithTag
0x14002c482  nop     dword ptr [rax+rax+00h]
0x14002c487  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002c48b  call    cs:__imp_ZwClose
0x14002c492  nop     dword ptr [rax+rax+00h]
0x14002c497  mov     eax, r14d
0x14002c49a  mov     rcx, [rbp+57h+var_28]
0x14002c49e  xor     rcx, rsp; StackCookie
0x14002c4a1  call    __security_check_cookie
0x14002c4a6  mov     rbx, [rsp+0E0h+arg_10]
0x14002c4ae  add     rsp, 0C0h
0x14002c4b5  pop     r15
0x14002c4b7  pop     r14
0x14002c4b9  pop     rdi
0x14002c4ba  pop     rsi
0x14002c4bb  pop     rbp
0x14002c4bc  retn
```
