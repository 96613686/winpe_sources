# FvepRegDeleteSubKeys

- ea: `0x14005f15c`
- end: `0x14005f2ed`
- name: `FvepRegDeleteSubKeys`
- size: `401`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14005edb8`

## callees

- `0x140022bf0`
- `0x140023040`
- `0x14005f15c`
- `0x14005f2f4`
- `0x140096ab8`

## import_xrefs

- `ntoskrnl!ZwEnumerateKey` at `0x14005f1d1`
- `ntoskrnl!ZwEnumerateKey` at `0x14005f1d1`
- `ntoskrnl!RtlGUIDFromString` at `0x14005f226`
- `ntoskrnl!RtlGUIDFromString` at `0x14005f226`
- `ntoskrnl!ZwDeleteKey` at `0x14005f284`
- `ntoskrnl!ZwDeleteKey` at `0x14005f284`
- `ntoskrnl!ZwClose` at `0x14005f29a`
- `ntoskrnl!ZwClose` at `0x14005f2bd`
- `ntoskrnl!ZwClose` at `0x14005f29a`
- `ntoskrnl!ZwClose` at `0x14005f2bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f212`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f261`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f212`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005f261`

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
0x14005f15c  mov     [rsp-8+arg_8], rbx
0x14005f161  mov     [rsp-8+arg_10], rdi
0x14005f166  push    rbp
0x14005f167  lea     rbp, [rsp-57h]
0x14005f16c  sub     rsp, 100h
0x14005f173  mov     rax, cs:__security_cookie
0x14005f17a  xor     rax, rsp
0x14005f17d  mov     [rbp+57h+var_10], rax
0x14005f181  xorps   xmm0, xmm0
0x14005f184  mov     [rbp+57h+var_C8], 0
0x14005f18b  xorps   xmm1, xmm1
0x14005f18e  mov     rdi, rcx
0x14005f191  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x14005f195  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14005f199  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14005f19d  xor     edx, edx; Val
0x14005f19f  mov     [rbp+57h+KeyHandle], 0
0x14005f1a7  lea     rcx, [rbp+57h+KeyInformation]; void *
0x14005f1ab  lea     r8d, [rdx+72h]; Size
0x14005f1af  call    memset
0x14005f1b4  lea     rax, [rbp+57h+var_C8]
0x14005f1b8  xor     r8d, r8d; KeyInformationClass
0x14005f1bb  mov     [rsp+100h+ResultLength], rax; ResultLength
0x14005f1c0  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x14005f1c4  xor     edx, edx; Index
0x14005f1c6  mov     [rsp+100h+Length], 72h ; 'r'; Length
0x14005f1ce  mov     rcx, rdi; KeyHandle
0x14005f1d1  call    cs:__imp_ZwEnumerateKey
0x14005f1d8  nop     dword ptr [rax+rax+00h]
0x14005f1dd  mov     ebx, eax
0x14005f1df  cmp     eax, 8000001Ah
0x14005f1e4  jz      loc_14005F2B2
0x14005f1ea  test    eax, eax
0x14005f1ec  js      loc_14005F2B4
0x14005f1f2  mov     ecx, [rbp+57h+var_84]
0x14005f1f5  shr     ecx, 1
0x14005f1f7  lea     eax, [rcx-1]
0x14005f1fa  cmp     eax, 2Bh ; '+'
0x14005f1fd  ja      loc_14005F2AB
0x14005f203  xor     eax, eax
0x14005f205  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14005f209  mov     [rbp+rcx*2+57h+SourceString], ax
0x14005f20e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005f212  call    cs:__imp_RtlInitUnicodeString
0x14005f219  nop     dword ptr [rax+rax+00h]
0x14005f21e  lea     rdx, [rbp+57h+Guid]; Guid
0x14005f222  lea     rcx, [rbp+57h+DestinationString]; GuidString
0x14005f226  call    cs:__imp_RtlGUIDFromString
0x14005f22d  nop     dword ptr [rax+rax+00h]
0x14005f232  mov     ebx, eax
0x14005f234  test    eax, eax
0x14005f236  js      short loc_14005F2B4
0x14005f238  lea     r9, [rbp+57h+KeyHandle]
0x14005f23c  mov     edx, 30006h
0x14005f241  mov     r8d, 1
0x14005f247  lea     rcx, [rbp+57h+Guid]
0x14005f24b  call    FvepRegOpenKey
0x14005f250  mov     ebx, eax
0x14005f252  test    eax, eax
0x14005f254  js      short loc_14005F2B4
0x14005f256  lea     rdx, aData_0; "Data"
0x14005f25d  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14005f261  call    cs:__imp_RtlInitUnicodeString
0x14005f268  nop     dword ptr [rax+rax+00h]
0x14005f26d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005f271  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14005f275  call    FvepRegSecureOverwriteValueKey
0x14005f27a  mov     ebx, eax
0x14005f27c  test    eax, eax
0x14005f27e  js      short loc_14005F2B4
0x14005f280  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14005f284  call    cs:__imp_ZwDeleteKey
0x14005f28b  nop     dword ptr [rax+rax+00h]
0x14005f290  mov     ebx, eax
0x14005f292  test    eax, eax
0x14005f294  js      short loc_14005F2B4
0x14005f296  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14005f29a  call    cs:__imp_ZwClose
0x14005f2a1  nop     dword ptr [rax+rax+00h]
0x14005f2a6  jmp     loc_14005F19D
0x14005f2ab  mov     ebx, 0C0000001h
0x14005f2b0  jmp     short loc_14005F2B4
0x14005f2b2  xor     ebx, ebx
0x14005f2b4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14005f2b8  test    rcx, rcx
0x14005f2bb  jz      short loc_14005F2C9
0x14005f2bd  call    cs:__imp_ZwClose
0x14005f2c4  nop     dword ptr [rax+rax+00h]
0x14005f2c9  mov     eax, ebx
0x14005f2cb  mov     rcx, [rbp+57h+var_10]
0x14005f2cf  xor     rcx, rsp; StackCookie
0x14005f2d2  call    __security_check_cookie
0x14005f2d7  lea     r11, [rsp+100h+var_s0]
0x14005f2df  mov     rbx, [r11+18h]
0x14005f2e3  mov     rdi, [r11+20h]
0x14005f2e7  mov     rsp, r11
0x14005f2ea  pop     rbp
0x14005f2eb  retn
```
