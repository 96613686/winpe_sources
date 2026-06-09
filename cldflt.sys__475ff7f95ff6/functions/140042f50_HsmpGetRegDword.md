# HsmpGetRegDword

- ea: `0x140042f50`
- end: `0x1400430ab`
- name: `HsmpGetRegDword`
- size: `347`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, _DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003c50`
- `0x140007bb0`
- `0x140012100`
- `0x140012238`
- `0x140037aa4`

## callees

- `0x14001e1c0`
- `0x140042f50`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140043050`
- `ntoskrnl!ZwQueryValueKey` at `0x140043050`
- `ntoskrnl!ZwOpenKey` at `0x140043008`
- `ntoskrnl!ZwOpenKey` at `0x140043008`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042fa8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042fa8`
- `ntoskrnl!ZwClose` at `0x14004307d`
- `ntoskrnl!ZwClose` at `0x14004307d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042fc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043021`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042fc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043021`

## pseudocode

```c
__int64 __fastcall HsmpGetRegDword(PCWSTR SourceString, PCWSTR a2, _DWORD *a3)
{
  NTSTATUS v6; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-9h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+27h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyValueInformation = 0;
  ValueName = 0;
  DestinationString = 0;
  if ( KeGetCurrentIrql() )
  {
    v6 = -1073741637;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v6 >= 0 )
    {
      RtlInitUnicodeString(&ValueName, a2);
      v6 = ZwQueryValueKey(
             KeyHandle,
             &ValueName,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x10u,
             &ResultLength);
      if ( v6 >= 0 )
      {
        if ( DWORD1(KeyValueInformation) == 4 )
          *a3 = HIDWORD(KeyValueInformation);
        else
          v6 = -1073741788;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140042f50  mov     [rsp-8+arg_18], rbx
0x140042f55  push    rbp
0x140042f56  push    rsi
0x140042f57  push    rdi
0x140042f58  lea     rbp, [rsp-47h]
0x140042f5d  sub     rsp, 0B0h
0x140042f64  mov     rax, cs:__security_cookie
0x140042f6b  xor     rax, rsp
0x140042f6e  mov     [rbp+57h+var_20], rax
0x140042f72  xorps   xmm0, xmm0
0x140042f75  mov     [rbp+57h+KeyHandle], 0
0x140042f7d  xorps   xmm1, xmm1
0x140042f80  mov     [rbp+57h+var_90], 0
0x140042f87  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140042f8b  mov     rdi, r8
0x140042f8e  mov     rsi, rdx
0x140042f91  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140042f95  mov     rbx, rcx
0x140042f98  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140042f9c  movups  [rbp+57h+KeyValueInformation], xmm0
0x140042fa0  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140042fa4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140042fa8  call    cs:__imp_KeGetCurrentIrql
0x140042faf  nop     dword ptr [rax+rax+00h]
0x140042fb4  test    al, al
0x140042fb6  jz      short loc_140042FC2
0x140042fb8  mov     ebx, 0C00000BBh
0x140042fbd  jmp     loc_140043074
0x140042fc2  mov     rdx, rbx; SourceString
0x140042fc5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140042fc9  call    cs:__imp_RtlInitUnicodeString
0x140042fd0  nop     dword ptr [rax+rax+00h]
0x140042fd5  lea     rax, [rbp+57h+DestinationString]
0x140042fd9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140042fe0  xorps   xmm0, xmm0
0x140042fe3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140042fe7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140042feb  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140042ff3  mov     edx, 20019h; DesiredAccess
0x140042ff8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140042fff  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140043003  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140043008  call    cs:__imp_ZwOpenKey
0x14004300f  nop     dword ptr [rax+rax+00h]
0x140043014  mov     ebx, eax
0x140043016  test    eax, eax
0x140043018  js      short loc_140043074
0x14004301a  mov     rdx, rsi; SourceString
0x14004301d  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140043021  call    cs:__imp_RtlInitUnicodeString
0x140043028  nop     dword ptr [rax+rax+00h]
0x14004302d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140043031  lea     rax, [rbp+57h+var_90]
0x140043035  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14004303a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14004303e  mov     r8d, 2; KeyValueInformationClass
0x140043044  mov     [rsp+0C0h+Length], 10h; Length
0x14004304c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140043050  call    cs:__imp_ZwQueryValueKey
0x140043057  nop     dword ptr [rax+rax+00h]
0x14004305c  mov     ebx, eax
0x14004305e  test    eax, eax
0x140043060  js      short loc_140043074
0x140043062  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140043066  jz      short loc_14004306F
0x140043068  mov     ebx, 0C0000024h
0x14004306d  jmp     short loc_140043074
0x14004306f  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140043072  mov     [rdi], eax
0x140043074  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140043078  test    rcx, rcx
0x14004307b  jz      short loc_140043089
0x14004307d  call    cs:__imp_ZwClose
0x140043084  nop     dword ptr [rax+rax+00h]
0x140043089  mov     eax, ebx
0x14004308b  mov     rcx, [rbp+57h+var_20]
0x14004308f  xor     rcx, rsp; StackCookie
0x140043092  call    __security_check_cookie
0x140043097  mov     rbx, [rsp+0C0h+arg_18]
0x14004309f  add     rsp, 0B0h
0x1400430a6  pop     rdi
0x1400430a7  pop     rsi
0x1400430a8  pop     rbp
0x1400430a9  retn
```
