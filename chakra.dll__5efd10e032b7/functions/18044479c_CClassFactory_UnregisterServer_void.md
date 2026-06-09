# CClassFactory::UnregisterServer(void)

- ea: `0x18044479c`
- end: `0x180444be3`
- name: `?UnregisterServer@CClassFactory@@QEAAJXZ`
- size: `1095`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180424050`
- `0x180444130`

## callees

- `0x1804446cc`
- `0x18044479c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444833`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444875`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18044490b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444920`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444a01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444b5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444833`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444875`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18044490b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444920`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444a01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444b5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180444b92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1804447ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18044481b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18044485d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1804449a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180444ab6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1804447ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18044481b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18044485d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1804449a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180444ab6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180444a88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180444a88`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444892`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1804448fb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1804449ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1804449ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444a22`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444ae4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b06`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b28`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444bb6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444892`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1804448fb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1804449ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1804449ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444a22`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444ae4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b06`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b28`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444b7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180444bb6`

## string_xrefs

- `0x1804447de`: `CLSID`
- `0x1804449bd`: `CLSID`
- `0x180444a5b`: `CLSID`

## pseudocode

```c
__int64 __fastcall CClassFactory::UnregisterServer(CClassFactory *this)
{
  unsigned int v2; // ebx
  int v3; // r15d
  _DWORD *v4; // r14
  const WCHAR *v5; // rdx
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  GUID v9; // [rsp+60h] [rbp-10h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20006u, &hKey) )
  {
    if ( !RegOpenKeyExW(hKey, *((LPCWSTR *)this + 2), 0, 0x20006u, &phkResult) )
    {
      RegCloseKey(hKey);
      hKey = phkResult;
      if ( !RegOpenKeyExW(phkResult, L"InprocServer", 0, 0x20006u, &phkResult) )
      {
        RegCloseKey(phkResult);
        v2 = RegDeleteKeyExW(hKey, L"InprocServer32", 0, 0) != 0 ? 0x80004005 : 0;
        if ( (*((_BYTE *)this + 76) & 1) != 0 )
        {
          v9 = CATID_ActiveScript;
          UnRegisterCLSIDInCategory((char *)this + 60, &v9);
        }
        if ( (*((_BYTE *)this + 76) & 2) != 0 )
        {
          v9 = CATID_ActiveScriptParse;
          UnRegisterCLSIDInCategory((char *)this + 60, &v9);
        }
        RegDeleteKeyExW(hKey, L"Implemented Categories", 0, 0);
        RegCloseKey(hKey);
        return v2;
      }
    }
    RegCloseKey(hKey);
  }
  v2 = 0;
  if ( (*((_BYTE *)this + 76) & 1) != 0 )
  {
    v9 = CATID_ActiveScript;
    UnRegisterCLSIDInCategory((char *)this + 60, &v9);
  }
  if ( (*((_BYTE *)this + 76) & 2) != 0 )
  {
    v9 = CATID_ActiveScriptParse;
    UnRegisterCLSIDInCategory((char *)this + 60, &v9);
  }
  v3 = 0;
  v4 = (_DWORD *)((char *)this + 56);
  if ( *((int *)this + 14) > 0 )
  {
    do
    {
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, *(LPCWSTR *)(*((_QWORD *)this + 6) + 8LL * v3), 0, 0x20006u, &hKey) )
      {
        v2 = -2147467259;
      }
      else
      {
        if ( RegDeleteKeyExW(hKey, L"CLSID", 0, 0) )
          v2 = -2147467259;
        if ( RegDeleteKeyExW(hKey, L"OLEScript", 0, 0) )
          v2 = -2147467259;
        RegCloseKey(hKey);
        if ( RegDeleteKeyExW(HKEY_CLASSES_ROOT, *(LPCWSTR *)(*((_QWORD *)this + 6) + 8LL * v3), 0, 0) )
          v2 = -2147467259;
      }
      ++v3;
    }
    while ( v3 < *v4 );
    v4 = (_DWORD *)((char *)this + 56);
  }
  if ( RegCreateKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0, 0, 0x20006u, 0, &hKey, 0) )
  {
    v2 = -2147467259;
  }
  else
  {
    if ( RegOpenKeyExW(hKey, *((LPCWSTR *)this + 2), 0, 0x20006u, &phkResult) )
    {
      v2 = -2147467259;
    }
    else
    {
      if ( *v4 && RegDeleteKeyExW(phkResult, L"ProgID", 0, 0) )
        v2 = -2147467259;
      if ( RegDeleteKeyExW(phkResult, L"OLEScript", 0, 0) )
        v2 = -2147467259;
      if ( RegDeleteKeyExW(phkResult, L"Implemented Categories", 0, 0) )
        v2 = -2147467259;
      if ( RegDeleteKeyExW(phkResult, L"InprocServer32", 0, 0) )
        v2 = -2147467259;
      RegCloseKey(phkResult);
      v4 = (_DWORD *)((char *)this + 56);
    }
    if ( RegDeleteKeyExW(hKey, *((LPCWSTR *)this + 2), 0, 0) )
      v2 = -2147467259;
    RegCloseKey(hKey);
  }
  v5 = (const WCHAR *)*((_QWORD *)this + 4);
  if ( v5 && *v4 && RegDeleteKeyExW(HKEY_CLASSES_ROOT, v5, 0, 0) )
    return (unsigned int)-2147467259;
  return v2;
}

```

## disassembly

```asm
0x18044479c  mov     r11, rsp
0x18044479f  mov     [r11+10h], rbx
0x1804447a3  mov     [r11+18h], rsi
0x1804447a7  mov     [r11+8], rcx
0x1804447ab  push    rbp
0x1804447ac  push    rdi
0x1804447ad  push    r12
0x1804447af  push    r14
0x1804447b1  push    r15
0x1804447b3  mov     rbp, rsp
0x1804447b6  sub     rsp, 70h
0x1804447ba  lea     rax, [rbp+hKey]
0x1804447be  mov     [rbp+hKey], 0
0x1804447c6  mov     r12d, 20006h
0x1804447cc  mov     [rbp+var_18], 0
0x1804447d4  mov     r9d, r12d; samDesired
0x1804447d7  mov     [r11-78h], rax
0x1804447db  xor     r8d, r8d; ulOptions
0x1804447de  lea     rdx, aClsid; "CLSID"
0x1804447e5  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1804447ec  call    cs:__imp_RegOpenKeyExW
0x1804447f3  nop     dword ptr [rax+rax+00h]
0x1804447f8  mov     rdi, [rbp+arg_0]
0x1804447fc  test    eax, eax
0x1804447fe  jnz     loc_18044492C
0x180444804  mov     rdx, [rdi+10h]; lpSubKey
0x180444808  lea     rax, [rbp+var_18]
0x18044480c  mov     rcx, [rbp+hKey]; hKey
0x180444810  mov     r9d, r12d; samDesired
0x180444813  xor     r8d, r8d; ulOptions
0x180444816  mov     [rsp+70h+phkResult], rax; phkResult
0x18044481b  call    cs:__imp_RegOpenKeyExW
0x180444822  nop     dword ptr [rax+rax+00h]
0x180444827  test    eax, eax
0x180444829  jnz     loc_18044491C
0x18044482f  mov     rcx, [rbp+hKey]; hKey
0x180444833  call    cs:__imp_RegCloseKey
0x18044483a  nop     dword ptr [rax+rax+00h]
0x18044483f  mov     rcx, [rbp+var_18]; hKey
0x180444843  lea     rax, [rbp+var_18]
0x180444847  mov     r9d, r12d; samDesired
0x18044484a  mov     [rbp+hKey], rcx
0x18044484e  xor     r8d, r8d; ulOptions
0x180444851  mov     [rsp+70h+phkResult], rax; phkResult
0x180444856  lea     rdx, aInprocserver; "InprocServer"
0x18044485d  call    cs:__imp_RegOpenKeyExW
0x180444864  nop     dword ptr [rax+rax+00h]
0x180444869  test    eax, eax
0x18044486b  jnz     loc_18044491C
0x180444871  mov     rcx, [rbp+var_18]; hKey
0x180444875  call    cs:__imp_RegCloseKey
0x18044487c  nop     dword ptr [rax+rax+00h]
0x180444881  mov     rcx, [rbp+hKey]; hKey
0x180444885  lea     rdx, aInprocserver32; "InprocServer32"
0x18044488c  xor     r9d, r9d; Reserved
0x18044488f  xor     r8d, r8d; samDesired
0x180444892  call    cs:__imp_RegDeleteKeyExW
0x180444899  nop     dword ptr [rax+rax+00h]
0x18044489e  xor     ecx, ecx
0x1804448a0  sub     ecx, eax
0x1804448a2  neg     ecx
0x1804448a4  sbb     ebx, ebx
0x1804448a6  and     ebx, 80004005h
0x1804448ac  test    byte ptr [rdi+4Ch], 1
0x1804448b0  jz      short loc_1804448CB
0x1804448b2  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x1804448b9  lea     rdx, [rbp+var_10]
0x1804448bd  lea     rcx, [rdi+3Ch]
0x1804448c1  movdqu  [rbp+var_10], xmm0
0x1804448c6  call    UnRegisterCLSIDInCategory
0x1804448cb  test    byte ptr [rdi+4Ch], 2
0x1804448cf  jz      short loc_1804448EA
0x1804448d1  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x1804448d8  lea     rdx, [rbp+var_10]
0x1804448dc  lea     rcx, [rdi+3Ch]
0x1804448e0  movdqu  [rbp+var_10], xmm0
0x1804448e5  call    UnRegisterCLSIDInCategory
0x1804448ea  mov     rcx, [rbp+hKey]; hKey
0x1804448ee  lea     rdx, aImplementedCat; "Implemented Categories"
0x1804448f5  xor     r9d, r9d; Reserved
0x1804448f8  xor     r8d, r8d; samDesired
0x1804448fb  call    cs:__imp_RegDeleteKeyExW
0x180444902  nop     dword ptr [rax+rax+00h]
0x180444907  mov     rcx, [rbp+hKey]; hKey
0x18044490b  call    cs:__imp_RegCloseKey
0x180444912  nop     dword ptr [rax+rax+00h]
0x180444917  jmp     loc_180444BC7
0x18044491c  mov     rcx, [rbp+hKey]; hKey
0x180444920  call    cs:__imp_RegCloseKey
0x180444927  nop     dword ptr [rax+rax+00h]
0x18044492c  xor     ebx, ebx
0x18044492e  test    byte ptr [rdi+4Ch], 1
0x180444932  jz      short loc_18044494D
0x180444934  movups  xmm0, xmmword ptr cs:CATID_ActiveScript.Data1
0x18044493b  lea     rdx, [rbp+var_10]
0x18044493f  lea     rcx, [rdi+3Ch]
0x180444943  movdqu  [rbp+var_10], xmm0
0x180444948  call    UnRegisterCLSIDInCategory
0x18044494d  test    byte ptr [rdi+4Ch], 2
0x180444951  jz      short loc_18044496C
0x180444953  movups  xmm0, xmmword ptr cs:CATID_ActiveScriptParse.Data1
0x18044495a  lea     rdx, [rbp+var_10]
0x18044495e  lea     rcx, [rdi+3Ch]
0x180444962  movdqu  [rbp+var_10], xmm0
0x180444967  call    UnRegisterCLSIDInCategory
0x18044496c  xor     r15d, r15d
0x18044496f  lea     r14, [rdi+38h]
0x180444973  mov     esi, 80004005h
0x180444978  cmp     [r14], ebx
0x18044497b  jle     loc_180444A49
0x180444981  mov     rdx, [rdi+30h]
0x180444985  lea     rax, [rbp+hKey]
0x180444989  movsxd  r12, r15d
0x18044498c  mov     r9d, 20006h; samDesired
0x180444992  xor     r8d, r8d; ulOptions
0x180444995  mov     [rsp+70h+phkResult], rax; phkResult
0x18044499a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1804449a1  mov     rdx, [rdx+r12*8]; lpSubKey
0x1804449a5  call    cs:__imp_RegOpenKeyExW
0x1804449ac  nop     dword ptr [rax+rax+00h]
0x1804449b1  test    eax, eax
0x1804449b3  jz      short loc_1804449B9
0x1804449b5  mov     ebx, esi
0x1804449b7  jmp     short loc_180444A33
0x1804449b9  mov     rcx, [rbp+hKey]; hKey
0x1804449bd  lea     rdx, aClsid; "CLSID"
0x1804449c4  xor     r9d, r9d; Reserved
0x1804449c7  xor     r8d, r8d; samDesired
0x1804449ca  call    cs:__imp_RegDeleteKeyExW
0x1804449d1  nop     dword ptr [rax+rax+00h]
0x1804449d6  mov     rcx, [rbp+hKey]; hKey
0x1804449da  lea     rdx, aOlescript; "OLEScript"
0x1804449e1  test    eax, eax
0x1804449e3  cmovnz  ebx, esi
0x1804449e6  xor     r9d, r9d; Reserved
0x1804449e9  xor     r8d, r8d; samDesired
0x1804449ec  call    cs:__imp_RegDeleteKeyExW
0x1804449f3  nop     dword ptr [rax+rax+00h]
0x1804449f8  mov     rcx, [rbp+hKey]; hKey
0x1804449fc  test    eax, eax
0x1804449fe  cmovnz  ebx, esi
0x180444a01  call    cs:__imp_RegCloseKey
0x180444a08  nop     dword ptr [rax+rax+00h]
0x180444a0d  mov     rdx, [rdi+30h]
0x180444a11  xor     r9d, r9d; Reserved
0x180444a14  xor     r8d, r8d; samDesired
0x180444a17  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180444a1e  mov     rdx, [rdx+r12*8]; lpSubKey
0x180444a22  call    cs:__imp_RegDeleteKeyExW
0x180444a29  nop     dword ptr [rax+rax+00h]
0x180444a2e  test    eax, eax
0x180444a30  cmovnz  ebx, esi
0x180444a33  inc     r15d
0x180444a36  cmp     r15d, [r14]
0x180444a39  jl      loc_180444981
0x180444a3f  lea     r14, [rdi+38h]
0x180444a43  mov     r12d, 20006h
0x180444a49  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180444a52  lea     rax, [rbp+hKey]
0x180444a56  mov     [rsp+70h+var_38], rax; phkResult
0x180444a5b  lea     rdx, aClsid; "CLSID"
0x180444a62  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180444a6b  mov     r15, 0FFFFFFFF80000000h
0x180444a72  mov     [rsp+70h+samDesired], r12d; samDesired
0x180444a77  xor     r9d, r9d; lpClass
0x180444a7a  xor     r8d, r8d; Reserved
0x180444a7d  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x180444a85  mov     rcx, r15; hKey
0x180444a88  call    cs:__imp_RegCreateKeyExW
0x180444a8f  nop     dword ptr [rax+rax+00h]
0x180444a94  test    eax, eax
0x180444a96  jz      short loc_180444A9F
0x180444a98  mov     ebx, esi
0x180444a9a  jmp     loc_180444B9E
0x180444a9f  mov     rdx, [rdi+10h]; lpSubKey
0x180444aa3  lea     rax, [rbp+var_18]
0x180444aa7  mov     rcx, [rbp+hKey]; hKey
0x180444aab  mov     r9d, r12d; samDesired
0x180444aae  xor     r8d, r8d; ulOptions
0x180444ab1  mov     [rsp+70h+phkResult], rax; phkResult
0x180444ab6  call    cs:__imp_RegOpenKeyExW
0x180444abd  nop     dword ptr [rax+rax+00h]
0x180444ac2  test    eax, eax
0x180444ac4  jz      short loc_180444ACD
0x180444ac6  mov     ebx, esi
0x180444ac8  jmp     loc_180444B6F
0x180444acd  cmp     dword ptr [r14], 0
0x180444ad1  jz      short loc_180444AF5
0x180444ad3  mov     rcx, [rbp+var_18]; hKey
0x180444ad7  lea     rdx, aProgid; "ProgID"
0x180444ade  xor     r9d, r9d; Reserved
0x180444ae1  xor     r8d, r8d; samDesired
0x180444ae4  call    cs:__imp_RegDeleteKeyExW
0x180444aeb  nop     dword ptr [rax+rax+00h]
0x180444af0  test    eax, eax
0x180444af2  cmovnz  ebx, esi
0x180444af5  mov     rcx, [rbp+var_18]; hKey
0x180444af9  lea     rdx, aOlescript; "OLEScript"
0x180444b00  xor     r9d, r9d; Reserved
0x180444b03  xor     r8d, r8d; samDesired
0x180444b06  call    cs:__imp_RegDeleteKeyExW
0x180444b0d  nop     dword ptr [rax+rax+00h]
0x180444b12  mov     rcx, [rbp+var_18]; hKey
0x180444b16  lea     rdx, aImplementedCat; "Implemented Categories"
0x180444b1d  test    eax, eax
0x180444b1f  cmovnz  ebx, esi
0x180444b22  xor     r9d, r9d; Reserved
0x180444b25  xor     r8d, r8d; samDesired
0x180444b28  call    cs:__imp_RegDeleteKeyExW
0x180444b2f  nop     dword ptr [rax+rax+00h]
0x180444b34  mov     rcx, [rbp+var_18]; hKey
0x180444b38  lea     rdx, aInprocserver32; "InprocServer32"
0x180444b3f  test    eax, eax
0x180444b41  cmovnz  ebx, esi
0x180444b44  xor     r9d, r9d; Reserved
0x180444b47  xor     r8d, r8d; samDesired
0x180444b4a  call    cs:__imp_RegDeleteKeyExW
0x180444b51  nop     dword ptr [rax+rax+00h]
0x180444b56  mov     rcx, [rbp+var_18]; hKey
0x180444b5a  test    eax, eax
0x180444b5c  cmovnz  ebx, esi
0x180444b5f  call    cs:__imp_RegCloseKey
0x180444b66  nop     dword ptr [rax+rax+00h]
0x180444b6b  lea     r14, [rdi+38h]
0x180444b6f  mov     rdx, [rdi+10h]; lpSubKey
0x180444b73  xor     r9d, r9d; Reserved
0x180444b76  mov     rcx, [rbp+hKey]; hKey
0x180444b7a  xor     r8d, r8d; samDesired
0x180444b7d  call    cs:__imp_RegDeleteKeyExW
0x180444b84  nop     dword ptr [rax+rax+00h]
0x180444b89  mov     rcx, [rbp+hKey]; hKey
0x180444b8d  test    eax, eax
0x180444b8f  cmovnz  ebx, esi
0x180444b92  call    cs:__imp_RegCloseKey
0x180444b99  nop     dword ptr [rax+rax+00h]
0x180444b9e  mov     rdx, [rdi+20h]; lpSubKey
0x180444ba2  test    rdx, rdx
0x180444ba5  jz      short loc_180444BC7
0x180444ba7  cmp     dword ptr [r14], 0
0x180444bab  jz      short loc_180444BC7
0x180444bad  xor     r9d, r9d; Reserved
0x180444bb0  xor     r8d, r8d; samDesired
0x180444bb3  mov     rcx, r15; hKey
0x180444bb6  call    cs:__imp_RegDeleteKeyExW
0x180444bbd  nop     dword ptr [rax+rax+00h]
0x180444bc2  test    eax, eax
0x180444bc4  cmovnz  ebx, esi
0x180444bc7  lea     r11, [rsp+70h+var_s0]
0x180444bcc  mov     eax, ebx
0x180444bce  mov     rbx, [r11+38h]
0x180444bd2  mov     rsi, [r11+40h]
0x180444bd6  mov     rsp, r11
0x180444bd9  pop     r15
0x180444bdb  pop     r14
0x180444bdd  pop     r12
0x180444bdf  pop     rdi
0x180444be0  pop     rbp
0x180444be1  retn
```
