# CDSLPageHolder::GetHelpDir(ushort *,long)

- ea: `0x180059bd0`
- end: `0x180059de8`
- name: `?GetHelpDir@CDSLPageHolder@@QEAAHPEAGJ@Z`
- size: `536`
- prototype: `int(CDSLPageHolder *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005a500`

## callees

- `0x180059bd0`
- `0x18005a184`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180059da5`
- `msvcrt!wcsrchr` at `0x180059da5`
- `ADVAPI32!RegOpenKeyExW` at `0x180059ca0`
- `ADVAPI32!RegOpenKeyExW` at `0x180059ced`
- `ADVAPI32!RegOpenKeyExW` at `0x180059d62`
- `ADVAPI32!RegOpenKeyExW` at `0x180059ca0`
- `ADVAPI32!RegOpenKeyExW` at `0x180059ced`
- `ADVAPI32!RegOpenKeyExW` at `0x180059d62`
- `ADVAPI32!RegCloseKey` at `0x180059d12`
- `ADVAPI32!RegCloseKey` at `0x180059d93`
- `ADVAPI32!RegCloseKey` at `0x180059db9`
- `ADVAPI32!RegCloseKey` at `0x180059d12`
- `ADVAPI32!RegCloseKey` at `0x180059d93`
- `ADVAPI32!RegCloseKey` at `0x180059db9`
- `ole32!StringFromGUID2` at `0x180059c73`
- `ole32!StringFromGUID2` at `0x180059c73`

## string_xrefs

- `0x180059c07`: `CLSID\`

## pseudocode

```c
__int64 __fastcall CDSLPageHolder::GetHelpDir(const GUID *this, unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // edi
  int v6; // ebx
  int StringValue; // eax
  int v8; // edx
  wchar_t *v9; // rax
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[7]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[514]; // [rsp+4Eh] [rbp-B2h] BYREF

  hKey = 0;
  wcscpy(SubKey, L"CLSID\\");
  memset_0(v14, 0, 0x1FAu);
  phkResult = 0;
  v4 = -1;
  v5 = 0;
  do
    ++v4;
  while ( SubKey[v4] );
  if ( StringFromGUID2(this + 1, &SubKey[v4], 260 - v4) && !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
  {
    if ( (unsigned int)MyRegQueryStringValue(hKey, L"HelpDir", a2) )
    {
      if ( RegOpenKeyExW(hKey, L"HelpDir", 0, 0x20019u, &phkResult)
        || (v6 = MyRegQueryStringValue(phkResult, &String, a2), RegCloseKey(phkResult), LOBYTE(v5) = v6 == 0, v6) )
      {
        if ( (unsigned int)MyRegQueryStringValue(hKey, L"InProcServer32", a2) )
        {
          if ( RegOpenKeyExW(hKey, L"InProcServer32", 0, 0x20019u, &phkResult) )
            goto LABEL_17;
          StringValue = MyRegQueryStringValue(phkResult, &String, a2);
          v8 = v5;
          if ( !StringValue )
            v8 = 1;
          v5 = v8;
          RegCloseKey(phkResult);
          if ( !v5 )
            goto LABEL_17;
        }
        else
        {
          v5 = 1;
        }
        v9 = wcsrchr(a2, 0x5Cu);
        if ( v9 )
          *v9 = 0;
      }
    }
    else
    {
      v5 = 1;
    }
LABEL_17:
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180059bd0  mov     [rsp-8+arg_10], rbx
0x180059bd5  mov     [rsp-8+arg_18], rsi
0x180059bda  push    rbp
0x180059bdb  push    rdi
0x180059bdc  push    r14
0x180059bde  lea     rbp, [rsp-160h]
0x180059be6  sub     rsp, 260h
0x180059bed  mov     rax, cs:__security_cookie
0x180059bf4  xor     rax, rsp
0x180059bf7  mov     [rbp+170h+var_20], rax
0x180059bfe  mov     eax, dword ptr cs:aClsid+8; "D\\"
0x180059c04  mov     rsi, rdx
0x180059c07  movsd   xmm0, qword ptr cs:aClsid; "CLSID\\"
0x180059c0f  mov     rbx, rcx
0x180059c12  mov     [rsp+270h+var_228], eax
0x180059c16  lea     rcx, [rsp+270h+var_222]; void *
0x180059c1b  movzx   eax, word ptr cs:aClsid+0Ch; ""
0x180059c22  xor     r14d, r14d
0x180059c25  xor     edx, edx; Val
0x180059c27  mov     [rsp+270h+var_224], ax
0x180059c2c  mov     r8d, 1FAh; Size
0x180059c32  mov     [rsp+270h+hKey], r14
0x180059c37  movsd   qword ptr [rsp+270h+SubKey], xmm0
0x180059c3d  call    memset_0
0x180059c42  lea     rcx, [rsp+270h+SubKey]
0x180059c47  mov     [rsp+270h+var_240], r14
0x180059c4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059c50  mov     edi, r14d
0x180059c53  inc     rax
0x180059c56  cmp     [rcx+rax*2], r14w
0x180059c5b  jnz     short loc_180059C53
0x180059c5d  mov     r8d, 104h
0x180059c63  lea     rdx, [rsp+270h+SubKey]
0x180059c68  sub     r8d, eax; cchMax
0x180059c6b  lea     rdx, [rdx+rax*2]; lpsz
0x180059c6f  lea     rcx, [rbx+10h]; rguid
0x180059c73  call    cs:__imp_StringFromGUID2
0x180059c79  test    eax, eax
0x180059c7b  jz      loc_180059DBF
0x180059c81  lea     rax, [rsp+270h+hKey]
0x180059c86  mov     r9d, 20019h; samDesired
0x180059c8c  xor     r8d, r8d; ulOptions
0x180059c8f  mov     [rsp+270h+phkResult], rax; phkResult
0x180059c94  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180059c99  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180059ca0  call    cs:__imp_RegOpenKeyExW
0x180059ca6  test    eax, eax
0x180059ca8  jnz     loc_180059DBF
0x180059cae  mov     rcx, [rsp+270h+hKey]
0x180059cb3  lea     rdx, aHelpdir; "HelpDir"
0x180059cba  mov     r8, rsi
0x180059cbd  call    MyRegQueryStringValue
0x180059cc2  test    eax, eax
0x180059cc4  jnz     short loc_180059CCE
0x180059cc6  lea     edi, [rax+1]
0x180059cc9  jmp     loc_180059DB4
0x180059cce  mov     rcx, [rsp+270h+hKey]; hKey
0x180059cd3  lea     rax, [rsp+270h+var_240]
0x180059cd8  mov     r9d, 20019h; samDesired
0x180059cde  mov     [rsp+270h+phkResult], rax; phkResult
0x180059ce3  xor     r8d, r8d; ulOptions
0x180059ce6  lea     rdx, aHelpdir; "HelpDir"
0x180059ced  call    cs:__imp_RegOpenKeyExW
0x180059cf3  test    eax, eax
0x180059cf5  jnz     short loc_180059D26
0x180059cf7  mov     rcx, [rsp+270h+var_240]
0x180059cfc  lea     rdx, String
0x180059d03  mov     r8, rsi
0x180059d06  call    MyRegQueryStringValue
0x180059d0b  mov     rcx, [rsp+270h+var_240]; hKey
0x180059d10  mov     ebx, eax
0x180059d12  call    cs:__imp_RegCloseKey
0x180059d18  test    ebx, ebx
0x180059d1a  setz    dil
0x180059d1e  test    ebx, ebx
0x180059d20  jz      loc_180059DB4
0x180059d26  mov     rcx, [rsp+270h+hKey]
0x180059d2b  lea     rdx, aInprocserver32; "InProcServer32"
0x180059d32  mov     r8, rsi
0x180059d35  call    MyRegQueryStringValue
0x180059d3a  test    eax, eax
0x180059d3c  jnz     short loc_180059D43
0x180059d3e  lea     edi, [rax+1]
0x180059d41  jmp     short loc_180059D9D
0x180059d43  mov     rcx, [rsp+270h+hKey]; hKey
0x180059d48  lea     rax, [rsp+270h+var_240]
0x180059d4d  mov     r9d, 20019h; samDesired
0x180059d53  mov     [rsp+270h+phkResult], rax; phkResult
0x180059d58  xor     r8d, r8d; ulOptions
0x180059d5b  lea     rdx, aInprocserver32; "InProcServer32"
0x180059d62  call    cs:__imp_RegOpenKeyExW
0x180059d68  test    eax, eax
0x180059d6a  jnz     short loc_180059DB4
0x180059d6c  mov     rcx, [rsp+270h+var_240]
0x180059d71  lea     rdx, String
0x180059d78  mov     r8, rsi
0x180059d7b  call    MyRegQueryStringValue
0x180059d80  mov     rcx, [rsp+270h+var_240]; hKey
0x180059d85  mov     edx, edi
0x180059d87  test    eax, eax
0x180059d89  mov     edi, 1
0x180059d8e  cmovz   edx, edi
0x180059d91  mov     edi, edx
0x180059d93  call    cs:__imp_RegCloseKey
0x180059d99  test    edi, edi
0x180059d9b  jz      short loc_180059DB4
0x180059d9d  mov     edx, 5Ch ; '\'; Ch
0x180059da2  mov     rcx, rsi; Str
0x180059da5  call    cs:__imp_wcsrchr
0x180059dab  test    rax, rax
0x180059dae  jz      short loc_180059DB4
0x180059db0  mov     [rax], r14w
0x180059db4  mov     rcx, [rsp+270h+hKey]; hKey
0x180059db9  call    cs:__imp_RegCloseKey
0x180059dbf  mov     eax, edi
0x180059dc1  mov     rcx, [rbp+170h+var_20]
0x180059dc8  xor     rcx, rsp; StackCookie
0x180059dcb  call    __security_check_cookie
0x180059dd0  lea     r11, [rsp+270h+var_10]
0x180059dd8  mov     rbx, [r11+30h]
0x180059ddc  mov     rsi, [r11+38h]
0x180059de0  mov     rsp, r11
0x180059de3  pop     r14
0x180059de5  pop     rdi
0x180059de6  pop     rbp
0x180059de7  retn
```
