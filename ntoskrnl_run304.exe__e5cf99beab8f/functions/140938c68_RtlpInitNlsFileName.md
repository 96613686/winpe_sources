# RtlpInitNlsFileName

- ea: `0x140938c68`
- end: `0x140938e35`
- name: `RtlpInitNlsFileName`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14090c8a0`

## callees

- `0x1402dc448`
- `0x1403f2d50`
- `0x1404729c0`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dab70`
- `0x140937c20`
- `0x140938c68`

## string_xrefs

- `0x140938e1c`: `\SystemRoot\System32\l_intl.nls`
- `0x140938ce3`: `\SystemRoot\System32\%s`
- `0x140938d4b`: `\Registry\Machine\System\CurrentControlSet\Control\Nls\Normalization`
- `0x140938d2f`: `\SystemRoot\System32\c_%.3d.nls`

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
0x140938c68  mov     [rsp-8+arg_0], rbx
0x140938c6d  push    rbp
0x140938c6e  push    rsi
0x140938c6f  push    rdi
0x140938c70  push    r14
0x140938c72  push    r15
0x140938c74  lea     rbp, [rsp-100h]
0x140938c7c  sub     rsp, 200h
0x140938c83  mov     rax, cs:__security_cookie
0x140938c8a  xor     rax, rsp
0x140938c8d  mov     [rbp+120h+var_30], rax
0x140938c94  mov     r15, [rbp+120h+DestinationString]
0x140938c9b  xorps   xmm0, xmm0
0x140938c9e  xor     eax, eax
0x140938ca0  mov     rsi, r8
0x140938ca3  mov     [rsp+220h+var_1F0], eax
0x140938ca7  mov     r14d, edx
0x140938caa  mov     [rsp+220h+KeyHandle], rax
0x140938caf  movups  xmmword ptr [rsp+220h+ObjectAttributes.ObjectName], xmm0
0x140938cb4  movups  xmmword ptr [rsp+220h+ObjectAttributes+1Ch], xmm0
0x140938cb9  movups  xmmword ptr [rbp+120h+var_1A0.Length], xmm0
0x140938cbd  movups  xmmword ptr [rsp+220h+ObjectAttributes.Length], xmm0
0x140938cc2  sub     ecx, 0Bh
0x140938cc5  jz      short loc_140938D2C
0x140938cc7  sub     ecx, 1
0x140938cca  jz      short loc_140938D4B
0x140938ccc  cmp     ecx, 2
0x140938ccf  jz      loc_140938E1C
0x140938cd5  mov     ebx, 0C00000EFh
0x140938cda  jmp     short loc_140938D03
0x140938cdc  lea     r9, [rbp+120h+var_144]
0x140938ce0  mov     rdx, rdi; cchDest
0x140938ce3  lea     r8, aSystemrootSyst_4; "\\SystemRoot\\System32\\%s"
0x140938cea  mov     rcx, rsi; pszDest
0x140938ced  call    RtlStringCchPrintfW
0x140938cf2  mov     ebx, eax
0x140938cf4  test    eax, eax
0x140938cf6  js      short loc_140938D03
0x140938cf8  mov     rdx, rsi; SourceString
0x140938cfb  mov     rcx, r15; DestinationString
0x140938cfe  call    RtlInitUnicodeString
0x140938d03  mov     eax, ebx
0x140938d05  mov     rcx, [rbp+120h+var_30]
0x140938d0c  xor     rcx, rsp; StackCookie
0x140938d0f  call    __security_check_cookie
0x140938d14  mov     rbx, [rsp+220h+arg_0]
0x140938d1c  add     rsp, 200h
0x140938d23  pop     r15
0x140938d25  pop     r14
0x140938d27  pop     rdi
0x140938d28  pop     rsi
0x140938d29  pop     rbp
0x140938d2a  retn
0x140938d2c  mov     r9d, r14d
0x140938d2f  lea     r8, aSystemrootSyst_9; "\\SystemRoot\\System32\\c_%.3d.nls"
0x140938d36  mov     edx, 40h ; '@'; cchDest
0x140938d3b  mov     rcx, rsi; pszDest
0x140938d3e  call    RtlStringCchPrintfW
0x140938d43  mov     ebx, eax
0x140938d45  test    eax, eax
0x140938d47  js      short loc_140938D05
0x140938d49  jmp     short loc_140938CF8
0x140938d4b  lea     rdx, aRegistryMachin_187; "\\Registry\\Machine\\System\\CurrentCon"...
0x140938d52  lea     rcx, [rbp+120h+var_1A0]; DestinationString
0x140938d56  call    RtlInitUnicodeString
0x140938d5b  lea     rax, [rbp+120h+var_1A0]
0x140938d5f  mov     [rsp+220h+ObjectAttributes.Length], 30h ; '0'
0x140938d67  xorps   xmm0, xmm0
0x140938d6a  mov     [rsp+220h+ObjectAttributes.ObjectName], rax
0x140938d6f  lea     r8, [rsp+220h+ObjectAttributes]; ObjectAttributes
0x140938d74  mov     [rsp+220h+ObjectAttributes.RootDirectory], 0
0x140938d7d  mov     edx, 80000000h; DesiredAccess
0x140938d82  mov     [rsp+220h+ObjectAttributes.Attributes], 240h
0x140938d8a  lea     rcx, [rsp+220h+KeyHandle]; KeyHandle
0x140938d8f  movdqu  xmmword ptr [rsp+220h+ObjectAttributes.SecurityDescriptor], xmm0
0x140938d95  call    ZwOpenKey
0x140938d9a  mov     ebx, eax
0x140938d9c  test    eax, eax
0x140938d9e  js      loc_140938D03
0x140938da4  lea     rax, [rbp+120h+var_190]
0x140938da8  mov     qword ptr [rsp+220h+String.Length], 400040h
0x140938db1  mov     edi, 40h ; '@'
0x140938db6  mov     [rsp+220h+String.Buffer], rax
0x140938dbb  lea     r8, [rsp+220h+String]; String
0x140938dc0  mov     ecx, r14d; Value
0x140938dc3  lea     edx, [rdi-30h]; Base
0x140938dc6  call    RtlIntegerToUnicodeString
0x140938dcb  mov     rcx, [rsp+220h+KeyHandle]; KeyHandle
0x140938dd0  lea     rax, [rsp+220h+var_1F0]
0x140938dd5  mov     [rsp+220h+ResultLength], rax; ResultLength
0x140938dda  lea     r9, [rbp+120h+KeyValueInformation]; KeyValueInformation
0x140938dde  lea     r8d, [rdi-3Eh]; KeyValueInformationClass
0x140938de2  mov     [rsp+220h+Length], 120h; Length
0x140938dea  lea     rdx, [rsp+220h+String]; ValueName
0x140938def  call    ZwQueryValueKey
0x140938df4  mov     rcx, [rsp+220h+KeyHandle]; Handle
0x140938df9  mov     ebx, eax
0x140938dfb  call    ZwClose
0x140938e00  test    ebx, ebx
0x140938e02  js      loc_140938D03
0x140938e08  cmp     [rbp+120h+var_14C], 1
0x140938e0c  jz      loc_140938CDC
0x140938e12  mov     eax, 0C0000001h
0x140938e17  jmp     loc_140938D05
0x140938e1c  lea     r8, aSystemrootSyst_7; "\\SystemRoot\\System32\\l_intl.nls"
0x140938e23  mov     edx, 40h ; '@'; cchDest
0x140938e28  mov     rcx, rsi; pszDest
0x140938e2b  call    RtlStringCchCopyW
0x140938e30  jmp     loc_140938D43
```
