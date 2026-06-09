# AfxRegisterThumbnailHandler(wchar_t const *,wchar_t const *,ulong)

- ea: `0x18026ff00`
- end: `0x1802700a4`
- name: `?AfxRegisterThumbnailHandler@@YAHPEB_W0K@Z`
- size: `420`
- prototype: `int __fastcall(const wchar_t *lpszCLSID, const wchar_t *lpszFilterExt, unsigned int nTreatment)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000dc50`
- `0x18026ff00`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18026ffa9`
- `ADVAPI32!RegCloseKey` at `0x18026fff6`
- `ADVAPI32!RegCloseKey` at `0x18027002d`
- `ADVAPI32!RegCloseKey` at `0x180270066`
- `ADVAPI32!RegCloseKey` at `0x18026ffa9`
- `ADVAPI32!RegCloseKey` at `0x18026fff6`
- `ADVAPI32!RegCloseKey` at `0x18027002d`
- `ADVAPI32!RegCloseKey` at `0x180270066`
- `ADVAPI32!RegCreateKeyExW` at `0x18026ff9c`
- `ADVAPI32!RegCreateKeyExW` at `0x18026ff9c`
- `ADVAPI32!RegSetValueExW` at `0x18026ffe0`
- `ADVAPI32!RegSetValueExW` at `0x180270058`
- `ADVAPI32!RegSetValueExW` at `0x18026ffe0`
- `ADVAPI32!RegSetValueExW` at `0x180270058`
- `ADVAPI32!RegOpenKeyExW` at `0x18027001b`
- `ADVAPI32!RegOpenKeyExW` at `0x18027001b`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026ffbf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026ffbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AfxRegisterThumbnailHandler(
        wchar_t *lpszCLSID,
        const wchar_t *lpszFilterExt,
        unsigned int nTreatment)
{
  HKEY v5; // rdi
  wchar_t *m_pszData; // rbx
  int v7; // eax
  unsigned int v8; // esi
  BYTE *lpData; // [rsp+20h] [rbp-40h]
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strShellExKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY__ *phkResult; // [rsp+58h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  Data = nTreatment;
  strShellExKey.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
    &strShellExKey,
    _afxShellExFormat,
    lpszFilterExt,
    _afxThumbnailHostCLSID);
  v5 = HKEY_CLASSES_ROOT;
  phkResult = 0;
  m_pszData = strShellExKey.m_pszData;
  if ( !RegCreateKeyExW(HKEY_CLASSES_ROOT, strShellExKey.m_pszData, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
  {
    RegCloseKey(HKEY_CLASSES_ROOT);
    v5 = phkResult;
  }
  if ( lpszCLSID )
    v7 = wcslen(lpszCLSID);
  else
    v7 = 0;
  lpData = (BYTE *)lpszCLSID;
  v8 = 1;
  if ( RegSetValueExW(v5, 0, 0, 1u, lpData, 2 * v7) )
  {
    v8 = 0;
  }
  else
  {
    if ( v5 )
    {
      RegCloseKey(v5);
      v5 = 0;
    }
    strShellExKey.m_pszData = 0;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, lpszFilterExt, 0, 0x2001Fu, (PHKEY)&strShellExKey) )
      v5 = (HKEY)strShellExKey.m_pszData;
    RegSetValueExW(v5, L"Treatment", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( v5 )
    RegCloseKey(v5);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
  return v8;
}

```

## disassembly

```asm
0x18026ff00  mov     [rsp-28h+arg_0], rbx
0x18026ff05  mov     [rsp-28h+Data], nTreatment
0x18026ff0a  push    rbp
0x18026ff0b  push    rsi
0x18026ff0c  push    rdi
0x18026ff0d  push    r12
0x18026ff0f  push    r14
0x18026ff11  mov     rbp, rsp
0x18026ff14  sub     rsp, 60h
0x18026ff18  mov     r14, lpszFilterExt
0x18026ff1b  mov     rsi, lpszCLSID
0x18026ff1e  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026ff25  lea     lpszCLSID, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18026ff2c  mov     rax, [rax+18h]
0x18026ff30  call    cs:__guard_dispatch_icall_fptr
0x18026ff36  add     rax, 18h
0x18026ff3a  mov     [rbp+strShellExKey.m_pszData], rax
0x18026ff3e  lea     r9, ?_afxThumbnailHostCLSID@@3QB_WB; wchar_t const near * const _afxThumbnailHostCLSID
0x18026ff45  mov     r8, r14
0x18026ff48  lea     lpszFilterExt, ?_afxShellExFormat@@3QB_WB; pszFormat
0x18026ff4f  lea     lpszCLSID, [rbp+strShellExKey]; this
0x18026ff53  call    ?Format@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x18026ff58  mov     r12, 0FFFFFFFF80000000h
0x18026ff5f  mov     rdi, r12
0x18026ff62  and     [rbp+var_8], 0
0x18026ff67  lea     rax, [rbp+dwDisposition]
0x18026ff6b  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18026ff70  lea     rax, [rbp+var_8]
0x18026ff74  mov     [rsp+60h+phkResult], rax; phkResult
0x18026ff79  and     [rsp+60h+var_30], 0
0x18026ff7f  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x18026ff87  and     dword ptr [rsp+60h+lpData], 0
0x18026ff8c  xor     r9d, r9d; lpClass
0x18026ff8f  xor     nTreatment, nTreatment; Reserved
0x18026ff92  mov     rbx, [rbp+strShellExKey.m_pszData]
0x18026ff96  mov     lpszFilterExt, rbx; lpSubKey
0x18026ff99  mov     lpszCLSID, r12; hKey
0x18026ff9c  call    cs:__imp_RegCreateKeyExW
0x18026ffa2  test    eax, eax
0x18026ffa4  jnz     short loc_18026FFB3
0x18026ffa6  mov     lpszCLSID, r12; hKey
0x18026ffa9  call    cs:__imp_RegCloseKey
0x18026ffaf  mov     rdi, [rbp+var_8]
0x18026ffb3  test    rsi, rsi
0x18026ffb6  jnz     short loc_18026FFBC
0x18026ffb8  xor     eax, eax
0x18026ffba  jmp     short loc_18026FFC5
0x18026ffbc  mov     lpszCLSID, rsi; String
0x18026ffbf  call    cs:__imp_wcslen
0x18026ffc5  add     eax, eax
0x18026ffc7  mov     [rsp+60h+samDesired], eax; cbData
0x18026ffcb  mov     [rsp+60h+lpData], rsi; lpData
0x18026ffd0  mov     esi, 1
0x18026ffd5  mov     r9d, esi; dwType
0x18026ffd8  xor     nTreatment, nTreatment; Reserved
0x18026ffdb  xor     edx, edx; lpValueName
0x18026ffdd  mov     lpszCLSID, rdi; hKey
0x18026ffe0  call    cs:__imp_RegSetValueExW
0x18026ffe6  test    eax, eax
0x18026ffe8  jz      short loc_18026FFEE
0x18026ffea  xor     esi, esi
0x18026ffec  jmp     short loc_18027005E
0x18026ffee  test    rdi, rdi
0x18026fff1  jz      short loc_18026FFFE
0x18026fff3  mov     lpszCLSID, rdi; hKey
0x18026fff6  call    cs:__imp_RegCloseKey
0x18026fffc  xor     edi, edi
0x18026fffe  and     [rbp+strShellExKey.m_pszData], 0
0x180270003  lea     rax, [rbp+strShellExKey]
0x180270007  mov     [rsp+60h+lpData], rax; phkResult
0x18027000c  mov     r9d, 2001Fh; samDesired
0x180270012  xor     nTreatment, nTreatment; ulOptions
0x180270015  mov     lpszFilterExt, r14; lpSubKey
0x180270018  mov     lpszCLSID, r12; hKey
0x18027001b  call    cs:__imp_RegOpenKeyExW
0x180270021  test    eax, eax
0x180270023  jnz     short loc_180270037
0x180270025  test    rdi, rdi
0x180270028  jz      short loc_180270033
0x18027002a  mov     lpszCLSID, rdi; hKey
0x18027002d  call    cs:__imp_RegCloseKey
0x180270033  mov     rdi, [rbp+strShellExKey.m_pszData]
0x180270037  mov     r9d, 4; dwType
0x18027003d  mov     [rsp+60h+samDesired], r9d; cbData
0x180270042  lea     rax, [rbp+Data]
0x180270046  mov     [rsp+60h+lpData], rax; lpData
0x18027004b  xor     nTreatment, nTreatment; Reserved
0x18027004e  lea     lpszFilterExt, aTreatment; "Treatment"
0x180270055  mov     lpszCLSID, rdi; hKey
0x180270058  call    cs:__imp_RegSetValueExW
0x18027005e  test    rdi, rdi
0x180270061  jz      short loc_18027006D
0x180270063  mov     lpszCLSID, rdi; hKey
0x180270066  call    cs:__imp_RegCloseKey
0x18027006c  nop
0x18027006d  lea     lpszFilterExt, [rbx-18h]
0x180270071  or      ecx, 0FFFFFFFFh
0x180270074  lock xadd [lpszFilterExt+10h], ecx
0x180270079  sub     ecx, 1
0x18027007c  jg      short loc_18027008E
0x18027007e  mov     lpszCLSID, [lpszFilterExt]
0x180270081  mov     r8, [lpszCLSID]
0x180270084  mov     rax, [r8+8]
0x180270088  call    cs:__guard_dispatch_icall_fptr
0x18027008e  mov     eax, esi
0x180270090  mov     rbx, [rsp+60h+arg_0]
0x180270098  add     rsp, 60h
0x18027009c  pop     r14
0x18027009e  pop     r12
0x1802700a0  pop     rdi
0x1802700a1  pop     rsi
0x1802700a2  pop     rbp
0x1802700a3  retn
```
