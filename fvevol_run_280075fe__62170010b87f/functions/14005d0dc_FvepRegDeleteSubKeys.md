# FvepRegDeleteSubKeys

- ea: `0x14005d0dc`
- end: `0x14005d26d`
- name: `FvepRegDeleteSubKeys`
- size: `401`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005cd38`

## callees

- `0x1400218c0`
- `0x140021d00`
- `0x14005d0dc`
- `0x14005d274`
- `0x140094a08`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x14005d151`
- `ntoskrnl!ZwEnumerateKey` at `0x14005d151`
- `ntoskrnl!RtlGUIDFromString` at `0x14005d1a6`
- `ntoskrnl!RtlGUIDFromString` at `0x14005d1a6`
- `ntoskrnl!ZwDeleteKey` at `0x14005d204`
- `ntoskrnl!ZwDeleteKey` at `0x14005d204`
- `ntoskrnl!ZwClose` at `0x14005d21a`
- `ntoskrnl!ZwClose` at `0x14005d23d`
- `ntoskrnl!ZwClose` at `0x14005d21a`
- `ntoskrnl!ZwClose` at `0x14005d23d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d192`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d1e1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d192`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005d1e1`

## pseudocode

```c
__int64 __fastcall FvepRegDeleteSubKeys(HANDLE KeyHandle)
{
  NTSTATUS v2; // eax
  int v3; // ebx
  __int64 v4; // rcx
  HANDLE KeyHandlea; // [rsp+30h] [rbp-79h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-59h] BYREF
  GUID Guid; // [rsp+60h] [rbp-49h] BYREF
  _DWORD KeyInformation[32]; // [rsp+70h] [rbp-39h] BYREF

  ResultLength = 0;
  Guid = 0;
  DestinationString = 0;
  ValueName = 0;
  while ( 1 )
  {
    KeyHandlea = 0;
    memset(KeyInformation, 0, 0x72u);
    v2 = ZwEnumerateKey(KeyHandle, 0, KeyBasicInformation, KeyInformation, 0x72u, &ResultLength);
    v3 = v2;
    if ( v2 == -2147483622 )
      break;
    if ( v2 < 0 )
      goto LABEL_12;
    v4 = KeyInformation[3] >> 1;
    if ( (unsigned int)(v4 - 1) > 0x2B )
    {
      v3 = -1073741823;
      goto LABEL_12;
    }
    *((_WORD *)&KeyInformation[4] + v4) = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)&KeyInformation[4]);
    v3 = RtlGUIDFromString(&DestinationString, &Guid);
    if ( v3 < 0 )
      goto LABEL_12;
    v3 = FvepRegOpenKey(&Guid, 0x30006u, 1, &KeyHandlea);
    if ( v3 < 0 )
      goto LABEL_12;
    RtlInitUnicodeString(&ValueName, L"Data");
    v3 = FvepRegSecureOverwriteValueKey(KeyHandlea, &ValueName);
    if ( v3 < 0 )
      goto LABEL_12;
    v3 = ZwDeleteKey(KeyHandlea);
    if ( v3 < 0 )
      goto LABEL_12;
    ZwClose(KeyHandlea);
  }
  v3 = 0;
LABEL_12:
  if ( KeyHandlea )
    ZwClose(KeyHandlea);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14005d0dc  mov     [rsp-8+arg_8], rbx
0x14005d0e1  mov     [rsp-8+arg_10], rdi
0x14005d0e6  push    rbp
0x14005d0e7  lea     rbp, [rsp-57h]
0x14005d0ec  sub     rsp, 100h
0x14005d0f3  mov     rax, cs:__security_cookie
0x14005d0fa  xor     rax, rsp
0x14005d0fd  mov     [rbp+57h+var_10], rax
0x14005d101  xorps   xmm0, xmm0
0x14005d104  mov     [rbp+57h+var_C8], 0
0x14005d10b  xorps   xmm1, xmm1
0x14005d10e  mov     rdi, rcx
0x14005d111  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14005d115  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14005d119  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14005d11d  xor     edx, edx; Val
0x14005d11f  mov     [rbp+57h+KeyHandle], 0
0x14005d127  lea     rcx, [rbp+57h+KeyInformation]; void *
0x14005d12b  lea     r8d, [rdx+72h]; Size
0x14005d12f  call    memset
0x14005d134  lea     rax, [rbp+57h+var_C8]
0x14005d138  xor     r8d, r8d; KeyInformationClass
0x14005d13b  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14005d140  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x14005d144  xor     edx, edx; Index
0x14005d146  mov     [rsp+100h+Length], 72h ; 'r'; Length
0x14005d14e  mov     rcx, rdi; KeyHandle
0x14005d151  call    cs:__imp_ZwEnumerateKey
0x14005d158  nop     dword ptr [rax+rax+00h]
0x14005d15d  mov     ebx, eax
0x14005d15f  cmp     eax, 8000001Ah
0x14005d164  jz      loc_14005D232
0x14005d16a  test    eax, eax
0x14005d16c  js      loc_14005D234
0x14005d172  mov     ecx, [rbp+57h+var_84]
0x14005d175  shr     ecx, 1
0x14005d177  lea     eax, [rcx-1]
0x14005d17a  cmp     eax, 2Bh ; '+'
0x14005d17d  ja      loc_14005D22B
0x14005d183  xor     eax, eax
0x14005d185  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14005d189  mov     [rbp+rcx*2+57h+SourceString], ax
0x14005d18e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005d192  call    cs:__imp_RtlInitUnicodeString
0x14005d199  nop     dword ptr [rax+rax+00h]
0x14005d19e  lea     rdx, [rbp+57h+Guid]; Guid
0x14005d1a2  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x14005d1a6  call    cs:__imp_RtlGUIDFromString
0x14005d1ad  nop     dword ptr [rax+rax+00h]
0x14005d1b2  mov     ebx, eax
0x14005d1b4  test    eax, eax
0x14005d1b6  js      short loc_14005D234
0x14005d1b8  lea     r9, [rbp+57h+KeyHandle]
0x14005d1bc  mov     edx, 30006h
0x14005d1c1  mov     r8d, 1
0x14005d1c7  lea     rcx, [rbp+57h+Guid]
0x14005d1cb  call    FvepRegOpenKey
0x14005d1d0  mov     ebx, eax
0x14005d1d2  test    eax, eax
0x14005d1d4  js      short loc_14005D234
0x14005d1d6  lea     rdx, aData_0; "Data"
0x14005d1dd  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14005d1e1  call    cs:__imp_RtlInitUnicodeString
0x14005d1e8  nop     dword ptr [rax+rax+00h]
0x14005d1ed  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005d1f1  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14005d1f5  call    FvepRegSecureOverwriteValueKey
0x14005d1fa  mov     ebx, eax
0x14005d1fc  test    eax, eax
0x14005d1fe  js      short loc_14005D234
0x14005d200  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005d204  call    cs:__imp_ZwDeleteKey
0x14005d20b  nop     dword ptr [rax+rax+00h]
0x14005d210  mov     ebx, eax
0x14005d212  test    eax, eax
0x14005d214  js      short loc_14005D234
0x14005d216  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14005d21a  call    cs:__imp_ZwClose
0x14005d221  nop     dword ptr [rax+rax+00h]
0x14005d226  jmp     loc_14005D11D
0x14005d22b  mov     ebx, 0C0000001h
0x14005d230  jmp     short loc_14005D234
0x14005d232  xor     ebx, ebx
0x14005d234  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14005d238  test    rcx, rcx
0x14005d23b  jz      short loc_14005D249
0x14005d23d  call    cs:__imp_ZwClose
0x14005d244  nop     dword ptr [rax+rax+00h]
0x14005d249  mov     eax, ebx
0x14005d24b  mov     rcx, [rbp+57h+var_10]
0x14005d24f  xor     rcx, rsp; StackCookie
0x14005d252  call    __security_check_cookie
0x14005d257  lea     r11, [rsp+100h+var_s0]
0x14005d25f  mov     rbx, [r11+18h]
0x14005d263  mov     rdi, [r11+20h]
0x14005d267  mov     rsp, r11
0x14005d26a  pop     rbp
0x14005d26b  retn
```
