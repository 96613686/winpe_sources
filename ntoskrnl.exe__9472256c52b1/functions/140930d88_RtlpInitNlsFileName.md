# RtlpInitNlsFileName

- ea: `0x140930d88`
- end: `0x140930f55`
- name: `RtlpInitNlsFileName`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140a3d970`

## callees

- `0x140403380`
- `0x140438468`
- `0x140481fa0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x14092fd40`
- `0x140930d88`

## string_xrefs

- `0x140930f3c`: `\SystemRoot\System32\l_intl.nls`
- `0x140930e03`: `\SystemRoot\System32\%s`
- `0x140930e6b`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\Normalization`
- `0x140930e4f`: `\SystemRoot\System32\c_%.3d.nls`

## pseudocode

```c
NTSTATUS __fastcall RtlpInitNlsFileName(int a1, ULONG a2, wchar_t *a3, __int64 a4, UNICODE_STRING *DestinationString)
{
  int v7; // ecx
  int v8; // ecx
  NTSTATUS v9; // ebx
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING String; // [rsp+40h] [rbp-C0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING v15; // [rsp+80h] [rbp-80h] BYREF
  char v16; // [rsp+90h] [rbp-70h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v18; // [rsp+D4h] [rbp-2Ch]
  _BYTE v19[276]; // [rsp+DCh] [rbp-24h] BYREF

  ResultLength = 0;
  KeyHandle = 0;
  v15 = 0;
  memset(&ObjectAttributes, 0, 44);
  v7 = a1 - 11;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( !v8 )
    {
      RtlInitUnicodeString(&v15, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nls\\Normalization");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v15;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
      if ( v9 < 0 )
        return v9;
      *(_QWORD *)&String.Length = 4194368;
      String.Buffer = (wchar_t *)&v16;
      RtlIntegerToUnicodeString(a2, 0x10u, &String);
      v9 = ZwQueryValueKey(KeyHandle, &String, KeyValuePartialInformation, KeyValueInformation, 0x120u, &ResultLength);
      ZwClose(KeyHandle);
      if ( v9 < 0 )
        return v9;
      if ( v18 != 1 )
        return -1073741823;
      v9 = RtlStringCchPrintfW(a3, 0x40u, L"\\SystemRoot\\System32\\%s", v19);
      if ( v9 < 0 )
        return v9;
      goto LABEL_6;
    }
    if ( v8 != 2 )
      return -1073741585;
    result = RtlStringCchCopyW(a3, 0x40u, L"\\SystemRoot\\System32\\l_intl.nls");
  }
  else
  {
    result = RtlStringCchPrintfW(a3, 0x40u, L"\\SystemRoot\\System32\\c_%.3d.nls", a2);
  }
  v9 = result;
  if ( result >= 0 )
  {
LABEL_6:
    RtlInitUnicodeString(DestinationString, a3);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140930d88  mov     [rsp-8+arg_0], rbx
0x140930d8d  push    rbp
0x140930d8e  push    rsi
0x140930d8f  push    rdi
0x140930d90  push    r14
0x140930d92  push    r15
0x140930d94  lea     rbp, [rsp-100h]
0x140930d9c  sub     rsp, 200h
0x140930da3  mov     rax, cs:__security_cookie
0x140930daa  xor     rax, rsp
0x140930dad  mov     [rbp+120h+var_30], rax
0x140930db4  mov     r15, [rbp+120h+DestinationString]
0x140930dbb  xorps   xmm0, xmm0
0x140930dbe  xor     eax, eax
0x140930dc0  mov     rsi, r8
0x140930dc3  mov     [rsp+220h+var_1F0], eax
0x140930dc7  mov     r14d, edx
0x140930dca  mov     [rsp+220h+KeyHandle], rax
0x140930dcf  movups  xmmword ptr [rsp+220h+ObjectAttributes.ObjectName], xmm0
0x140930dd4  movups  xmmword ptr [rsp+220h+ObjectAttributes+1Ch], xmm0
0x140930dd9  movups  xmmword ptr [rbp+120h+var_1A0.Length], xmm0
0x140930ddd  movups  xmmword ptr [rsp+220h+ObjectAttributes.Length], xmm0
0x140930de2  sub     ecx, 0Bh
0x140930de5  jz      short loc_140930E4C
0x140930de7  sub     ecx, 1
0x140930dea  jz      short loc_140930E6B
0x140930dec  cmp     ecx, 2
0x140930def  jz      loc_140930F3C
0x140930df5  mov     ebx, 0C00000EFh
0x140930dfa  jmp     short loc_140930E23
0x140930dfc  lea     r9, [rbp+120h+var_144]
0x140930e00  mov     rdx, rdi; cchDest
0x140930e03  lea     r8, aSystemrootSyst_4; "\\SystemRoot\\System32\\%s"
0x140930e0a  mov     rcx, rsi; pszDest
0x140930e0d  call    RtlStringCchPrintfW
0x140930e12  mov     ebx, eax
0x140930e14  test    eax, eax
0x140930e16  js      short loc_140930E23
0x140930e18  mov     rdx, rsi; SourceString
0x140930e1b  mov     rcx, r15; DestinationString
0x140930e1e  call    RtlInitUnicodeString
0x140930e23  mov     eax, ebx
0x140930e25  mov     rcx, [rbp+120h+var_30]
0x140930e2c  xor     rcx, rsp; StackCookie
0x140930e2f  call    __security_check_cookie
0x140930e34  mov     rbx, [rsp+220h+arg_0]
0x140930e3c  add     rsp, 200h
0x140930e43  pop     r15
0x140930e45  pop     r14
0x140930e47  pop     rdi
0x140930e48  pop     rsi
0x140930e49  pop     rbp
0x140930e4a  retn
0x140930e4c  mov     r9d, r14d
0x140930e4f  lea     r8, aSystemrootSyst_9; "\\SystemRoot\\System32\\c_%.3d.nls"
0x140930e56  mov     edx, 40h ; '@'; cchDest
0x140930e5b  mov     rcx, rsi; pszDest
0x140930e5e  call    RtlStringCchPrintfW
0x140930e63  mov     ebx, eax
0x140930e65  test    eax, eax
0x140930e67  js      short loc_140930E25
0x140930e69  jmp     short loc_140930E18
0x140930e6b  lea     rdx, aRegistryMachin_187; "\\Registry\\Machine\\System\\CurrentCon"...
0x140930e72  lea     rcx, [rbp+120h+var_1A0]; DestinationString
0x140930e76  call    RtlInitUnicodeString
0x140930e7b  lea     rax, [rbp+120h+var_1A0]
0x140930e7f  mov     [rsp+220h+ObjectAttributes.Length], 30h ; '0'
0x140930e87  xorps   xmm0, xmm0
0x140930e8a  mov     [rsp+220h+ObjectAttributes.ObjectName], rax
0x140930e8f  lea     r8, [rsp+220h+ObjectAttributes]; ObjectAttributes
0x140930e94  mov     [rsp+220h+ObjectAttributes.RootDirectory], 0
0x140930e9d  mov     edx, 80000000h; DesiredAccess
0x140930ea2  mov     [rsp+220h+ObjectAttributes.Attributes], 240h
0x140930eaa  lea     rcx, [rsp+220h+KeyHandle]; KeyHandle
0x140930eaf  movdqu  xmmword ptr [rsp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x140930eb5  call    ZwOpenKey
0x140930eba  mov     ebx, eax
0x140930ebc  test    eax, eax
0x140930ebe  js      loc_140930E23
0x140930ec4  lea     rax, [rbp+120h+var_190]
0x140930ec8  mov     qword ptr [rsp+220h+String.Length], 400040h
0x140930ed1  mov     edi, 40h ; '@'
0x140930ed6  mov     [rsp+220h+String.Buffer], rax
0x140930edb  lea     r8, [rsp+220h+String]; String
0x140930ee0  mov     ecx, r14d; Value
0x140930ee3  lea     edx, [rdi-30h]; Base
0x140930ee6  call    RtlIntegerToUnicodeString
0x140930eeb  mov     rcx, [rsp+220h+KeyHandle]; KeyHandle
0x140930ef0  lea     rax, [rsp+220h+var_1F0]
0x140930ef5  mov     [rsp+220h+ResultLength], rax; ResultLength
0x140930efa  lea     r9, [rbp+120h+KeyValueInformation]; KeyValueInformation
0x140930efe  lea     r8d, [rdi-3Eh]; KeyValueInformationClass
0x140930f02  mov     [rsp+220h+Length], 120h; Length
0x140930f0a  lea     rdx, [rsp+220h+String]; ValueName
0x140930f0f  call    ZwQueryValueKey
0x140930f14  mov     rcx, [rsp+220h+KeyHandle]; Handle
0x140930f19  mov     ebx, eax
0x140930f1b  call    ZwClose
0x140930f20  test    ebx, ebx
0x140930f22  js      loc_140930E23
0x140930f28  cmp     [rbp+120h+var_14C], 1
0x140930f2c  jz      loc_140930DFC
0x140930f32  mov     eax, 0C0000001h
0x140930f37  jmp     loc_140930E25
0x140930f3c  lea     r8, aSystemrootSyst_7; "\\SystemRoot\\System32\\l_intl.nls"
0x140930f43  mov     edx, 40h ; '@'; cchDest
0x140930f48  mov     rcx, rsi; pszDest
0x140930f4b  call    RtlStringCchCopyW
0x140930f50  jmp     loc_140930E63
```
