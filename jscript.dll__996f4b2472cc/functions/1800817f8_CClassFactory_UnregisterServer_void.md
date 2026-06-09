# CClassFactory::UnregisterServer(void)

- ea: `0x1800817f8`
- end: `0x180081ca1`
- name: `?UnregisterServer@CClassFactory@@QEAAJXZ`
- size: `1193`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800748f0`
- `0x180080fc4`

## callees

- `0x18008172c`
- `0x1800817f8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18008184a`
- `ADVAPI32!RegOpenKeyExA` at `0x180081875`
- `ADVAPI32!RegOpenKeyExA` at `0x1800818b7`
- `ADVAPI32!RegOpenKeyExA` at `0x180081a79`
- `ADVAPI32!RegOpenKeyExA` at `0x180081b84`
- `ADVAPI32!RegOpenKeyExA` at `0x18008184a`
- `ADVAPI32!RegOpenKeyExA` at `0x180081875`
- `ADVAPI32!RegOpenKeyExA` at `0x1800818b7`
- `ADVAPI32!RegOpenKeyExA` at `0x180081a79`
- `ADVAPI32!RegOpenKeyExA` at `0x180081b84`
- `ADVAPI32!RegCloseKey` at `0x18008188d`
- `ADVAPI32!RegCloseKey` at `0x1800818cf`
- `ADVAPI32!RegCloseKey` at `0x1800819a5`
- `ADVAPI32!RegCloseKey` at `0x1800819bd`
- `ADVAPI32!RegCloseKey` at `0x180081adc`
- `ADVAPI32!RegCloseKey` at `0x180081c27`
- `ADVAPI32!RegCloseKey` at `0x180081c56`
- `ADVAPI32!RegCloseKey` at `0x18008188d`
- `ADVAPI32!RegCloseKey` at `0x1800818cf`
- `ADVAPI32!RegCloseKey` at `0x1800819a5`
- `ADVAPI32!RegCloseKey` at `0x1800819bd`
- `ADVAPI32!RegCloseKey` at `0x180081adc`
- `ADVAPI32!RegCloseKey` at `0x180081c27`
- `ADVAPI32!RegCloseKey` at `0x180081c56`
- `ADVAPI32!RegCreateKeyExA` at `0x180081b56`
- `ADVAPI32!RegCreateKeyExA` at `0x180081b56`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800818ec`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081995`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081aa5`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081ac7`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081b00`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081bac`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081bce`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081bf0`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081c12`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081c41`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081c74`
- `ADVAPI32!RegDeleteKeyExA` at `0x1800818ec`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081995`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081aa5`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081ac7`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081b00`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081bac`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081bce`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081bf0`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081c12`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081c41`
- `ADVAPI32!RegDeleteKeyExA` at `0x180081c74`

## string_xrefs

- `0x18008183a`: `CLSID`
- `0x180081a98`: `CLSID`
- `0x180081b30`: `CLSID`

## pseudocode

```c
__int64 __fastcall CClassFactory::UnregisterServer(CClassFactory *this)
{
  unsigned int v2; // r14d
  unsigned int v4; // edi
  int i; // r14d
  const CHAR *v6; // rdx
  GUID v7; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+40h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x2000000u, &hKey) )
  {
    if ( !RegOpenKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0x2000000u, &phkResult) )
    {
      RegCloseKey(hKey);
      hKey = phkResult;
      if ( !RegOpenKeyExA(phkResult, "InprocServer", 0, 0x2000000u, &phkResult) )
      {
        RegCloseKey(phkResult);
        v2 = RegDeleteKeyExA(hKey, "InprocServer32", 0, 0) != 0 ? 0x80004005 : 0;
        if ( (*((_BYTE *)this + 84) & 1) != 0 )
        {
          v7 = CATID_ActiveScript;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        if ( (*((_BYTE *)this + 84) & 2) != 0 )
        {
          v7 = CATID_ActiveScriptParse;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        if ( (*((_BYTE *)this + 84) & 4) != 0 )
        {
          v7 = CATID_ActiveScriptAuthor;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        if ( (*((_BYTE *)this + 84) & 8) != 0 )
        {
          v7 = CATID_ActiveScriptEncode;
          UnRegisterCLSIDInCategory((char *)this + 68, &v7);
        }
        RegDeleteKeyExA(hKey, "Implemented Categories", 0, 0);
        RegCloseKey(hKey);
        return v2;
      }
    }
    RegCloseKey(hKey);
  }
  v4 = 0;
  if ( (*((_BYTE *)this + 84) & 1) != 0 )
  {
    v7 = CATID_ActiveScript;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  if ( (*((_BYTE *)this + 84) & 2) != 0 )
  {
    v7 = CATID_ActiveScriptParse;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  if ( (*((_BYTE *)this + 84) & 4) != 0 )
  {
    v7 = CATID_ActiveScriptAuthor;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  if ( (*((_BYTE *)this + 84) & 8) != 0 )
  {
    v7 = CATID_ActiveScriptEncode;
    UnRegisterCLSIDInCategory((char *)this + 68, &v7);
  }
  for ( i = 0; i < *((_DWORD *)this + 16); ++i )
  {
    if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i), 0, 0x2000000u, &hKey) )
    {
      v4 = -2147467259;
    }
    else
    {
      if ( RegDeleteKeyExA(hKey, "CLSID", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(hKey, "OLEScript", 0, 0) )
        v4 = -2147467259;
      RegCloseKey(hKey);
      if ( RegDeleteKeyExA(HKEY_CLASSES_ROOT, *(LPCSTR *)(*((_QWORD *)this + 7) + 8LL * i), 0, 0) )
        v4 = -2147467259;
    }
  }
  if ( RegCreateKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0, 0, 0x2000000u, 0, &hKey, 0) )
  {
    v4 = -2147467259;
  }
  else
  {
    if ( RegOpenKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0x2000000u, &phkResult) )
    {
      v4 = -2147467259;
    }
    else
    {
      if ( RegDeleteKeyExA(phkResult, "ProgID", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "OLEScript", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "Implemented Categories", 0, 0) )
        v4 = -2147467259;
      if ( RegDeleteKeyExA(phkResult, "InprocServer32", 0, 0) )
        v4 = -2147467259;
      RegCloseKey(phkResult);
    }
    if ( RegDeleteKeyExA(hKey, *((LPCSTR *)this + 3), 0, 0) )
      v4 = -2147467259;
    RegCloseKey(hKey);
  }
  v6 = (const CHAR *)*((_QWORD *)this + 5);
  if ( v6 && RegDeleteKeyExA(HKEY_CLASSES_ROOT, v6, 0, 0) )
    return (unsigned int)-2147467259;
  return v4;
}

```

## disassembly

```asm
0x1800817f8  mov     [rsp-28h+arg_0], rbx
0x1800817fd  mov     [rsp-28h+arg_18], rsi
0x180081802  push    rbp
0x180081803  push    rdi
0x180081804  push    r13
0x180081806  push    r14
0x180081808  push    r15
0x18008180a  mov     rbp, rsp
0x18008180d  sub     rsp, 60h
0x180081811  mov     rbx, rcx
0x180081814  mov     [rbp+hKey], 0
0x18008181c  lea     rax, [rbp+hKey]
0x180081820  mov     [rbp+arg_10], 0
0x180081828  mov     r13d, 2000000h
0x18008182e  mov     [rsp+60h+phkResult], rax; phkResult
0x180081833  mov     r15, 0FFFFFFFF80000000h
0x18008183a  lea     rdx, aClsid; "CLSID"
0x180081841  mov     r9d, r13d; samDesired
0x180081844  mov     rcx, r15; hKey
0x180081847  xor     r8d, r8d; ulOptions
0x18008184a  call    cs:__imp_RegOpenKeyExA
0x180081851  nop     dword ptr [rax+rax+00h]
0x180081856  test    eax, eax
0x180081858  jnz     loc_1800819C9
0x18008185e  mov     rdx, [rbx+18h]; lpSubKey
0x180081862  lea     rax, [rbp+arg_10]
0x180081866  mov     rcx, [rbp+hKey]; hKey
0x18008186a  mov     r9d, r13d; samDesired
0x18008186d  xor     r8d, r8d; ulOptions
0x180081870  mov     [rsp+60h+phkResult], rax; phkResult
0x180081875  call    cs:__imp_RegOpenKeyExA
0x18008187c  nop     dword ptr [rax+rax+00h]
0x180081881  test    eax, eax
0x180081883  jnz     loc_1800819B9
0x180081889  mov     rcx, [rbp+hKey]; hKey
0x18008188d  call    cs:__imp_RegCloseKey
0x180081894  nop     dword ptr [rax+rax+00h]
0x180081899  mov     rcx, [rbp+arg_10]; hKey
0x18008189d  lea     rax, [rbp+arg_10]
0x1800818a1  mov     r9d, r13d; samDesired
0x1800818a4  mov     [rbp+hKey], rcx
0x1800818a8  xor     r8d, r8d; ulOptions
0x1800818ab  mov     [rsp+60h+phkResult], rax; phkResult
0x1800818b0  lea     rdx, aInprocserver; "InprocServer"
0x1800818b7  call    cs:__imp_RegOpenKeyExA
0x1800818be  nop     dword ptr [rax+rax+00h]
0x1800818c3  test    eax, eax
0x1800818c5  jnz     loc_1800819B9
0x1800818cb  mov     rcx, [rbp+arg_10]; hKey
0x1800818cf  call    cs:__imp_RegCloseKey
0x1800818d6  nop     dword ptr [rax+rax+00h]
0x1800818db  mov     rcx, [rbp+hKey]; hKey
0x1800818df  lea     rdx, aInprocserver32; "InprocServer32"
0x1800818e6  xor     r9d, r9d; Reserved
0x1800818e9  xor     r8d, r8d; samDesired
0x1800818ec  call    cs:__imp_RegDeleteKeyExA
0x1800818f3  nop     dword ptr [rax+rax+00h]
0x1800818f8  xor     ecx, ecx
0x1800818fa  lea     rdi, [rbx+44h]
0x1800818fe  sub     ecx, eax
0x180081900  neg     ecx
0x180081902  sbb     r14d, r14d
0x180081905  and     r14d, 80004005h
0x18008190c  test    byte ptr [rbx+54h], 1
0x180081910  jz      short loc_18008192A
0x180081912  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x180081919  lea     rdx, [rbp+var_10]
0x18008191d  mov     rcx, rdi
0x180081920  movdqu  [rbp+var_10], xmm0
0x180081925  call    UnRegisterCLSIDInCategory
0x18008192a  test    byte ptr [rbx+54h], 2
0x18008192e  jz      short loc_180081948
0x180081930  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x180081937  lea     rdx, [rbp+var_10]
0x18008193b  mov     rcx, rdi
0x18008193e  movdqu  [rbp+var_10], xmm0
0x180081943  call    UnRegisterCLSIDInCategory
0x180081948  test    byte ptr [rbx+54h], 4
0x18008194c  jz      short loc_180081966
0x18008194e  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x180081955  lea     rdx, [rbp+var_10]
0x180081959  mov     rcx, rdi
0x18008195c  movdqu  [rbp+var_10], xmm0
0x180081961  call    UnRegisterCLSIDInCategory
0x180081966  test    byte ptr [rbx+54h], 8
0x18008196a  jz      short loc_180081984
0x18008196c  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x180081973  lea     rdx, [rbp+var_10]
0x180081977  mov     rcx, rdi
0x18008197a  movdqu  [rbp+var_10], xmm0
0x18008197f  call    UnRegisterCLSIDInCategory
0x180081984  mov     rcx, [rbp+hKey]; hKey
0x180081988  lea     rdx, aImplementedCat; "Implemented Categories"
0x18008198f  xor     r9d, r9d; Reserved
0x180081992  xor     r8d, r8d; samDesired
0x180081995  call    cs:__imp_RegDeleteKeyExA
0x18008199c  nop     dword ptr [rax+rax+00h]
0x1800819a1  mov     rcx, [rbp+hKey]; hKey
0x1800819a5  call    cs:__imp_RegCloseKey
0x1800819ac  nop     dword ptr [rax+rax+00h]
0x1800819b1  mov     eax, r14d
0x1800819b4  jmp     loc_180081C87
0x1800819b9  mov     rcx, [rbp+hKey]; hKey
0x1800819bd  call    cs:__imp_RegCloseKey
0x1800819c4  nop     dword ptr [rax+rax+00h]
0x1800819c9  xor     edi, edi
0x1800819cb  lea     rsi, [rbx+44h]
0x1800819cf  test    byte ptr [rbx+54h], 1
0x1800819d3  jz      short loc_1800819ED
0x1800819d5  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x1800819dc  lea     rdx, [rbp+var_10]
0x1800819e0  mov     rcx, rsi
0x1800819e3  movdqu  [rbp+var_10], xmm0
0x1800819e8  call    UnRegisterCLSIDInCategory
0x1800819ed  test    byte ptr [rbx+54h], 2
0x1800819f1  jz      short loc_180081A0B
0x1800819f3  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x1800819fa  lea     rdx, [rbp+var_10]
0x1800819fe  mov     rcx, rsi
0x180081a01  movdqu  [rbp+var_10], xmm0
0x180081a06  call    UnRegisterCLSIDInCategory
0x180081a0b  test    byte ptr [rbx+54h], 4
0x180081a0f  jz      short loc_180081A29
0x180081a11  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptAuthor.Data1
0x180081a18  lea     rdx, [rbp+var_10]
0x180081a1c  mov     rcx, rsi
0x180081a1f  movdqu  [rbp+var_10], xmm0
0x180081a24  call    UnRegisterCLSIDInCategory
0x180081a29  test    byte ptr [rbx+54h], 8
0x180081a2d  jz      short loc_180081A47
0x180081a2f  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptEncode.Data1
0x180081a36  lea     rdx, [rbp+var_10]
0x180081a3a  mov     rcx, rsi
0x180081a3d  movdqu  [rbp+var_10], xmm0
0x180081a42  call    UnRegisterCLSIDInCategory
0x180081a47  xor     r14d, r14d
0x180081a4a  mov     esi, 80004005h
0x180081a4f  cmp     [rbx+40h], edi
0x180081a52  jle     loc_180081B1E
0x180081a58  mov     rdx, [rbx+38h]
0x180081a5c  lea     rax, [rbp+hKey]
0x180081a60  movsxd  r15, r14d
0x180081a63  mov     r9d, r13d; samDesired
0x180081a66  xor     r8d, r8d; ulOptions
0x180081a69  mov     [rsp+60h+phkResult], rax; phkResult
0x180081a6e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180081a75  mov     rdx, [rdx+r15*8]; lpSubKey
0x180081a79  call    cs:__imp_RegOpenKeyExA
0x180081a80  nop     dword ptr [rax+rax+00h]
0x180081a85  test    eax, eax
0x180081a87  jz      short loc_180081A94
0x180081a89  mov     edi, esi
0x180081a8b  mov     r15, 0FFFFFFFF80000000h
0x180081a92  jmp     short loc_180081B11
0x180081a94  mov     rcx, [rbp+hKey]; hKey
0x180081a98  lea     rdx, aClsid; "CLSID"
0x180081a9f  xor     r9d, r9d; Reserved
0x180081aa2  xor     r8d, r8d; samDesired
0x180081aa5  call    cs:__imp_RegDeleteKeyExA
0x180081aac  nop     dword ptr [rax+rax+00h]
0x180081ab1  mov     rcx, [rbp+hKey]; hKey
0x180081ab5  lea     rdx, aOlescript; "OLEScript"
0x180081abc  test    eax, eax
0x180081abe  cmovnz  edi, esi
0x180081ac1  xor     r9d, r9d; Reserved
0x180081ac4  xor     r8d, r8d; samDesired
0x180081ac7  call    cs:__imp_RegDeleteKeyExA
0x180081ace  nop     dword ptr [rax+rax+00h]
0x180081ad3  mov     rcx, [rbp+hKey]; hKey
0x180081ad7  test    eax, eax
0x180081ad9  cmovnz  edi, esi
0x180081adc  call    cs:__imp_RegCloseKey
0x180081ae3  nop     dword ptr [rax+rax+00h]
0x180081ae8  mov     rdx, [rbx+38h]
0x180081aec  xor     r9d, r9d; Reserved
0x180081aef  xor     r8d, r8d; samDesired
0x180081af2  mov     rdx, [rdx+r15*8]; lpSubKey
0x180081af6  mov     r15, 0FFFFFFFF80000000h
0x180081afd  mov     rcx, r15; hKey
0x180081b00  call    cs:__imp_RegDeleteKeyExA
0x180081b07  nop     dword ptr [rax+rax+00h]
0x180081b0c  test    eax, eax
0x180081b0e  cmovnz  edi, esi
0x180081b11  inc     r14d
0x180081b14  cmp     r14d, [rbx+40h]
0x180081b18  jl      loc_180081A58
0x180081b1e  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180081b27  lea     rax, [rbp+hKey]
0x180081b2b  mov     [rsp+60h+var_28], rax; phkResult
0x180081b30  lea     rdx, aClsid; "CLSID"
0x180081b37  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180081b40  xor     r9d, r9d; lpClass
0x180081b43  mov     [rsp+60h+samDesired], r13d; samDesired
0x180081b48  xor     r8d, r8d; Reserved
0x180081b4b  mov     rcx, r15; hKey
0x180081b4e  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180081b56  call    cs:__imp_RegCreateKeyExA
0x180081b5d  nop     dword ptr [rax+rax+00h]
0x180081b62  test    eax, eax
0x180081b64  jz      short loc_180081B6D
0x180081b66  mov     edi, esi
0x180081b68  jmp     loc_180081C62
0x180081b6d  mov     rdx, [rbx+18h]; lpSubKey
0x180081b71  lea     rax, [rbp+arg_10]
0x180081b75  mov     rcx, [rbp+hKey]; hKey
0x180081b79  mov     r9d, r13d; samDesired
0x180081b7c  xor     r8d, r8d; ulOptions
0x180081b7f  mov     [rsp+60h+phkResult], rax; phkResult
0x180081b84  call    cs:__imp_RegOpenKeyExA
0x180081b8b  nop     dword ptr [rax+rax+00h]
0x180081b90  test    eax, eax
0x180081b92  jz      short loc_180081B9B
0x180081b94  mov     edi, esi
0x180081b96  jmp     loc_180081C33
0x180081b9b  mov     rcx, [rbp+arg_10]; hKey
0x180081b9f  lea     rdx, aProgid; "ProgID"
0x180081ba6  xor     r9d, r9d; Reserved
0x180081ba9  xor     r8d, r8d; samDesired
0x180081bac  call    cs:__imp_RegDeleteKeyExA
0x180081bb3  nop     dword ptr [rax+rax+00h]
0x180081bb8  mov     rcx, [rbp+arg_10]; hKey
0x180081bbc  lea     rdx, aOlescript; "OLEScript"
0x180081bc3  test    eax, eax
0x180081bc5  cmovnz  edi, esi
0x180081bc8  xor     r9d, r9d; Reserved
0x180081bcb  xor     r8d, r8d; samDesired
0x180081bce  call    cs:__imp_RegDeleteKeyExA
0x180081bd5  nop     dword ptr [rax+rax+00h]
0x180081bda  mov     rcx, [rbp+arg_10]; hKey
0x180081bde  lea     rdx, aImplementedCat; "Implemented Categories"
0x180081be5  test    eax, eax
0x180081be7  cmovnz  edi, esi
0x180081bea  xor     r9d, r9d; Reserved
0x180081bed  xor     r8d, r8d; samDesired
0x180081bf0  call    cs:__imp_RegDeleteKeyExA
0x180081bf7  nop     dword ptr [rax+rax+00h]
0x180081bfc  mov     rcx, [rbp+arg_10]; hKey
0x180081c00  lea     rdx, aInprocserver32; "InprocServer32"
0x180081c07  test    eax, eax
0x180081c09  cmovnz  edi, esi
0x180081c0c  xor     r9d, r9d; Reserved
0x180081c0f  xor     r8d, r8d; samDesired
0x180081c12  call    cs:__imp_RegDeleteKeyExA
0x180081c19  nop     dword ptr [rax+rax+00h]
0x180081c1e  mov     rcx, [rbp+arg_10]; hKey
0x180081c22  test    eax, eax
0x180081c24  cmovnz  edi, esi
0x180081c27  call    cs:__imp_RegCloseKey
0x180081c2e  nop     dword ptr [rax+rax+00h]
0x180081c33  mov     rdx, [rbx+18h]; lpSubKey
0x180081c37  xor     r9d, r9d; Reserved
0x180081c3a  mov     rcx, [rbp+hKey]; hKey
0x180081c3e  xor     r8d, r8d; samDesired
0x180081c41  call    cs:__imp_RegDeleteKeyExA
0x180081c48  nop     dword ptr [rax+rax+00h]
0x180081c4d  mov     rcx, [rbp+hKey]; hKey
0x180081c51  test    eax, eax
0x180081c53  cmovnz  edi, esi
0x180081c56  call    cs:__imp_RegCloseKey
0x180081c5d  nop     dword ptr [rax+rax+00h]
0x180081c62  mov     rdx, [rbx+28h]; lpSubKey
0x180081c66  test    rdx, rdx
0x180081c69  jz      short loc_180081C85
0x180081c6b  xor     r9d, r9d; Reserved
0x180081c6e  xor     r8d, r8d; samDesired
0x180081c71  mov     rcx, r15; hKey
0x180081c74  call    cs:__imp_RegDeleteKeyExA
0x180081c7b  nop     dword ptr [rax+rax+00h]
0x180081c80  test    eax, eax
0x180081c82  cmovnz  edi, esi
0x180081c85  mov     eax, edi
0x180081c87  lea     r11, [rsp+60h+var_s0]
0x180081c8c  mov     rbx, [r11+30h]
0x180081c90  mov     rsi, [r11+48h]
0x180081c94  mov     rsp, r11
0x180081c97  pop     r15
0x180081c99  pop     r14
0x180081c9b  pop     r13
0x180081c9d  pop     rdi
0x180081c9e  pop     rbp
0x180081c9f  retn
```
