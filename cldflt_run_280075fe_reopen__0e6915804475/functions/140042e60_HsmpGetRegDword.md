# HsmpGetRegDword

- ea: `0x140042e60`
- end: `0x140042fbb`
- name: `HsmpGetRegDword`
- size: `347`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `5`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140003c50`
- `0x140007bb0`
- `0x140012080`
- `0x1400121b8`
- `0x140037a84`

## callees

- `0x14001e140`
- `0x140042e60`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140042f60`
- `ntoskrnl!ZwQueryValueKey` at `0x140042f60`
- `ntoskrnl!ZwOpenKey` at `0x140042f18`
- `ntoskrnl!ZwOpenKey` at `0x140042f18`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042eb8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042eb8`
- `ntoskrnl!ZwClose` at `0x140042f8d`
- `ntoskrnl!ZwClose` at `0x140042f8d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042ed9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042f31`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042ed9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140042f31`

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
0x140042e60  mov     [rsp-8+arg_18], rbx
0x140042e65  push    rbp
0x140042e66  push    rsi
0x140042e67  push    rdi
0x140042e68  lea     rbp, [rsp-47h]
0x140042e6d  sub     rsp, 0B0h
0x140042e74  mov     rax, cs:__security_cookie
0x140042e7b  xor     rax, rsp
0x140042e7e  mov     [rbp+57h+var_20], rax
0x140042e82  xorps   xmm0, xmm0
0x140042e85  mov     [rbp+57h+KeyHandle], 0
0x140042e8d  xorps   xmm1, xmm1
0x140042e90  mov     [rbp+57h+var_90], 0
0x140042e97  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140042e9b  mov     rdi, r8
0x140042e9e  mov     rsi, rdx
0x140042ea1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140042ea5  mov     rbx, rcx
0x140042ea8  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140042eac  movups  [rbp+57h+KeyValueInformation], xmm0
0x140042eb0  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140042eb4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140042eb8  call    cs:__imp_KeGetCurrentIrql
0x140042ebf  nop     dword ptr [rax+rax+00h]
0x140042ec4  test    al, al
0x140042ec6  jz      short loc_140042ED2
0x140042ec8  mov     ebx, 0C00000BBh
0x140042ecd  jmp     loc_140042F84
0x140042ed2  mov     rdx, rbx; SourceString
0x140042ed5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140042ed9  call    cs:__imp_RtlInitUnicodeString
0x140042ee0  nop     dword ptr [rax+rax+00h]
0x140042ee5  lea     rax, [rbp+57h+DestinationString]
0x140042ee9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140042ef0  xorps   xmm0, xmm0
0x140042ef3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140042ef7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140042efb  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140042f03  mov     edx, 20019h; DesiredAccess
0x140042f08  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140042f0f  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140042f13  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140042f18  call    cs:__imp_ZwOpenKey
0x140042f1f  nop     dword ptr [rax+rax+00h]
0x140042f24  mov     ebx, eax
0x140042f26  test    eax, eax
0x140042f28  js      short loc_140042F84
0x140042f2a  mov     rdx, rsi; SourceString
0x140042f2d  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140042f31  call    cs:__imp_RtlInitUnicodeString
0x140042f38  nop     dword ptr [rax+rax+00h]
0x140042f3d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140042f41  lea     rax, [rbp+57h+var_90]
0x140042f45  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140042f4a  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140042f4e  mov     r8d, 2; KeyValueInformationClass
0x140042f54  mov     [rsp+0C0h+Length], 10h; Length
0x140042f5c  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140042f60  call    cs:__imp_ZwQueryValueKey
0x140042f67  nop     dword ptr [rax+rax+00h]
0x140042f6c  mov     ebx, eax
0x140042f6e  test    eax, eax
0x140042f70  js      short loc_140042F84
0x140042f72  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140042f76  jz      short loc_140042F7F
0x140042f78  mov     ebx, 0C0000024h
0x140042f7d  jmp     short loc_140042F84
0x140042f7f  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x140042f82  mov     [rdi], eax
0x140042f84  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140042f88  test    rcx, rcx
0x140042f8b  jz      short loc_140042F99
0x140042f8d  call    cs:__imp_ZwClose
0x140042f94  nop     dword ptr [rax+rax+00h]
0x140042f99  mov     eax, ebx
0x140042f9b  mov     rcx, [rbp+57h+var_20]
0x140042f9f  xor     rcx, rsp; StackCookie
0x140042fa2  call    __security_check_cookie
0x140042fa7  mov     rbx, [rsp+0C0h+arg_18]
0x140042faf  add     rsp, 0B0h
0x140042fb6  pop     rdi
0x140042fb7  pop     rsi
0x140042fb8  pop     rbp
0x140042fb9  retn
```
