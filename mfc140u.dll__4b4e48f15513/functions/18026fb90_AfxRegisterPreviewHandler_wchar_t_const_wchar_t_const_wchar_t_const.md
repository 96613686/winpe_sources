# AfxRegisterPreviewHandler(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18026fb90`
- end: `0x18026fdd9`
- name: `?AfxRegisterPreviewHandler@@YAHPEB_W00@Z`
- size: `585`
- prototype: `int __fastcall(const wchar_t *lpszCLSID, const wchar_t *lpszShortTypeName, const wchar_t *lpszFilterExt)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18022d760`

## callees

- `0x180002b60`
- `0x18000dc50`
- `0x18000df50`
- `0x18026fb90`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18026fc33`
- `ADVAPI32!RegCloseKey` at `0x18026fd10`
- `ADVAPI32!RegCloseKey` at `0x18026fd5b`
- `ADVAPI32!RegCloseKey` at `0x18026fd93`
- `ADVAPI32!RegCloseKey` at `0x18026fc33`
- `ADVAPI32!RegCloseKey` at `0x18026fd10`
- `ADVAPI32!RegCloseKey` at `0x18026fd5b`
- `ADVAPI32!RegCloseKey` at `0x18026fd93`
- `ADVAPI32!RegCreateKeyExW` at `0x18026fc26`
- `ADVAPI32!RegCreateKeyExW` at `0x18026fd03`
- `ADVAPI32!RegCreateKeyExW` at `0x18026fc26`
- `ADVAPI32!RegCreateKeyExW` at `0x18026fd03`
- `ADVAPI32!RegSetValueExW` at `0x18026fc7a`
- `ADVAPI32!RegSetValueExW` at `0x18026fd45`
- `ADVAPI32!RegSetValueExW` at `0x18026fc7a`
- `ADVAPI32!RegSetValueExW` at `0x18026fd45`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026fbbf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026fc55`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026fd26`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026fbbf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026fc55`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026fd26`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_BOOL8 __fastcall AfxRegisterPreviewHandler(
        const wchar_t *lpszCLSID,
        const wchar_t *lpszShortTypeName,
        const wchar_t *lpszFilterExt)
{
  int v5; // eax
  __int64 m_pszData; // rbx
  wchar_t *lpData; // rsi
  int v8; // eax
  HKEY__ *v9; // rsi
  wchar_t *v10; // rbx
  int v11; // eax
  BOOL v12; // edi
  wchar_t *v13; // rdx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strData; // [rsp+50h] [rbp-30h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strShellExKey; // [rsp+58h] [rbp-28h] BYREF
  HKEY__ *phkResult; // [rsp+60h] [rbp-20h] BYREF
  ATL::CRegKey regPreviewHandlersKey; // [rsp+68h] [rbp-18h]
  DWORD dwDisposition; // [rsp+B8h] [rbp+38h] BYREF

  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &strData,
    lpszShortTypeName);
  v5 = wcslen(L" Preview Handler");
  ATL::CSimpleStringT<wchar_t,1>::Append(&strData, L" Preview Handler", v5);
  m_pszData = -2147483646;
  regPreviewHandlersKey.m_hKey = (HKEY__ *)-2147483646LL;
  regPreviewHandlersKey.m_samWOW64 = 0;
  regPreviewHandlersKey.m_pTM = 0;
  strShellExKey.m_pszData = 0;
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          _afxPreviewHandlersRegPath,
          0,
          0,
          0,
          0x2001Fu,
          0,
          (PHKEY)&strShellExKey,
          &dwDisposition) )
  {
    RegCloseKey(HKEY_LOCAL_MACHINE);
    m_pszData = (__int64)strShellExKey.m_pszData;
    regPreviewHandlersKey.m_hKey = (HKEY__ *)strShellExKey.m_pszData;
    regPreviewHandlersKey.m_samWOW64 = 0;
  }
  lpData = strData.m_pszData;
  if ( !strData.m_pszData
    || (v8 = wcslen(strData.m_pszData),
        RegSetValueExW((HKEY)m_pszData, lpszCLSID, 0, 1u, (const BYTE *)lpData, 2 * v8 + 2)) )
  {
    v12 = 0;
  }
  else
  {
    strShellExKey.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(
      &strShellExKey,
      _afxShellExFormat,
      lpszFilterExt,
      _afxPreviewHostCLSID);
    v9 = (HKEY__ *)0xFFFFFFFF80000000LL;
    phkResult = 0;
    v10 = strShellExKey.m_pszData;
    if ( !RegCreateKeyExW(HKEY_CLASSES_ROOT, strShellExKey.m_pszData, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
    {
      RegCloseKey(HKEY_CLASSES_ROOT);
      v9 = phkResult;
    }
    if ( lpszCLSID )
      v11 = wcslen(lpszCLSID);
    else
      v11 = 0;
    v12 = RegSetValueExW(v9, 0, 0, 1u, (const BYTE *)lpszCLSID, 2 * v11) == 0;
    if ( v9 )
      RegCloseKey(v9);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v10 - 3) + 8LL))(*((_QWORD *)v10 - 3));
    m_pszData = (__int64)regPreviewHandlersKey.m_hKey;
  }
  if ( m_pszData )
    RegCloseKey((HKEY)m_pszData);
  v13 = strData.m_pszData - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)strData.m_pszData - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  return v12;
}

```

## disassembly

```asm
0x18026fb90  mov     [rsp-18h+arg_0], rbx
0x18026fb95  mov     [rsp-18h+arg_8], rsi
0x18026fb9a  push    rbp
0x18026fb9b  push    rdi
0x18026fb9c  push    r14
0x18026fb9e  mov     rbp, rsp
0x18026fba1  sub     rsp, 80h
0x18026fba8  mov     r14, lpszFilterExt
0x18026fbab  mov     rdi, lpszCLSID
0x18026fbae  lea     lpszCLSID, [rbp+strData]; this
0x18026fbb2  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18026fbb7  nop
0x18026fbb8  lea     lpszCLSID, aPreviewHandler; " Preview Handler"
0x18026fbbf  call    cs:__imp_wcslen
0x18026fbc5  mov     r8d, eax; nLength
0x18026fbc8  lea     lpszShortTypeName, aPreviewHandler; " Preview Handler"
0x18026fbcf  lea     lpszCLSID, [rbp+strData]; this
0x18026fbd3  call    ?Append@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::Append(wchar_t const *,int)
0x18026fbd8  mov     rbx, 0FFFFFFFF80000002h
0x18026fbdf  mov     [rbp+regPreviewHandlersKey.m_hKey], rbx
0x18026fbe3  and     [rbp+regPreviewHandlersKey.m_samWOW64], 0
0x18026fbe7  and     [rbp+regPreviewHandlersKey.m_pTM], 0
0x18026fbec  and     [rbp+strShellExKey.m_pszData], 0
0x18026fbf1  lea     rax, [rbp+dwDisposition]
0x18026fbf5  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18026fbfa  lea     rax, [rbp+strShellExKey]
0x18026fbfe  mov     [rsp+80h+phkResult], rax; phkResult
0x18026fc03  and     [rsp+80h+var_50], 0
0x18026fc09  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x18026fc11  and     dword ptr [rsp+80h+lpData], 0
0x18026fc16  xor     r9d, r9d; lpClass
0x18026fc19  xor     r8d, r8d; Reserved
0x18026fc1c  lea     lpszShortTypeName, ?_afxPreviewHandlersRegPath@@3QB_WB; lpSubKey
0x18026fc23  mov     lpszCLSID, rbx; hKey
0x18026fc26  call    cs:__imp_RegCreateKeyExW
0x18026fc2c  test    eax, eax
0x18026fc2e  jnz     short loc_18026FC45
0x18026fc30  mov     lpszCLSID, rbx; hKey
0x18026fc33  call    cs:__imp_RegCloseKey
0x18026fc39  mov     rbx, [rbp+strShellExKey.m_pszData]
0x18026fc3d  mov     [rbp+regPreviewHandlersKey.m_hKey], rbx
0x18026fc41  and     [rbp+regPreviewHandlersKey.m_samWOW64], 0
0x18026fc45  mov     rsi, [rbp+strData.m_pszData]
0x18026fc49  test    rsi, rsi
0x18026fc4c  jz      loc_18026FD89
0x18026fc52  mov     lpszCLSID, rsi; String
0x18026fc55  call    cs:__imp_wcslen
0x18026fc5b  lea     eax, ds:2[rax*2]
0x18026fc62  mov     [rsp+80h+samDesired], eax; cbData
0x18026fc66  mov     [rsp+80h+lpData], rsi; dwOptions
0x18026fc6b  mov     r9d, 1; dwType
0x18026fc71  xor     r8d, r8d; Reserved
0x18026fc74  mov     lpszShortTypeName, rdi; lpValueName
0x18026fc77  mov     lpszCLSID, rbx; hKey
0x18026fc7a  call    cs:__imp_RegSetValueExW
0x18026fc80  test    eax, eax
0x18026fc82  jnz     loc_18026FD89
0x18026fc88  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026fc8f  lea     lpszCLSID, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18026fc96  mov     rax, [rax+18h]
0x18026fc9a  call    cs:__guard_dispatch_icall_fptr
0x18026fca0  add     rax, 18h
0x18026fca4  mov     [rbp+strShellExKey.m_pszData], rax
0x18026fca8  lea     r9, ?_afxPreviewHostCLSID@@3QB_WB; wchar_t const near * const _afxPreviewHostCLSID
0x18026fcaf  mov     lpszFilterExt, r14
0x18026fcb2  lea     lpszShortTypeName, ?_afxShellExFormat@@3QB_WB; pszFormat
0x18026fcb9  lea     lpszCLSID, [rbp+strShellExKey]; this
0x18026fcbd  call    ?Format@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAXPEB_WZZ; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Format(wchar_t const *,...)
0x18026fcc2  mov     rsi, 0FFFFFFFF80000000h
0x18026fcc9  and     [rbp+var_20], 0
0x18026fcce  lea     rax, [rbp+dwDisposition]
0x18026fcd2  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18026fcd7  lea     rax, [rbp+var_20]
0x18026fcdb  mov     [rsp+80h+phkResult], rax; phkResult
0x18026fce0  and     [rsp+80h+var_50], 0
0x18026fce6  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x18026fcee  and     dword ptr [rsp+80h+lpData], 0
0x18026fcf3  xor     r9d, r9d; lpClass
0x18026fcf6  xor     r8d, r8d; Reserved
0x18026fcf9  mov     rbx, [rbp+strShellExKey.m_pszData]
0x18026fcfd  mov     lpszShortTypeName, rbx; lpSubKey
0x18026fd00  mov     lpszCLSID, rsi; hKey
0x18026fd03  call    cs:__imp_RegCreateKeyExW
0x18026fd09  test    eax, eax
0x18026fd0b  jnz     short loc_18026FD1A
0x18026fd0d  mov     lpszCLSID, rsi; hKey
0x18026fd10  call    cs:__imp_RegCloseKey
0x18026fd16  mov     rsi, [rbp+var_20]
0x18026fd1a  test    rdi, rdi
0x18026fd1d  jnz     short loc_18026FD23
0x18026fd1f  xor     eax, eax
0x18026fd21  jmp     short loc_18026FD2C
0x18026fd23  mov     lpszCLSID, rdi; String
0x18026fd26  call    cs:__imp_wcslen
0x18026fd2c  add     eax, eax
0x18026fd2e  mov     [rsp+80h+samDesired], eax; cbData
0x18026fd32  mov     [rsp+80h+lpData], rdi; lpData
0x18026fd37  mov     r9d, 1; dwType
0x18026fd3d  xor     r8d, r8d; Reserved
0x18026fd40  xor     edx, edx; lpValueName
0x18026fd42  mov     lpszCLSID, rsi; hKey
0x18026fd45  call    cs:__imp_RegSetValueExW
0x18026fd4b  xor     edi, edi
0x18026fd4d  test    eax, eax
0x18026fd4f  setz    dil
0x18026fd53  test    rsi, rsi
0x18026fd56  jz      short loc_18026FD62
0x18026fd58  mov     lpszCLSID, rsi; hKey
0x18026fd5b  call    cs:__imp_RegCloseKey
0x18026fd61  nop
0x18026fd62  lea     lpszShortTypeName, [rbx-18h]
0x18026fd66  or      eax, 0FFFFFFFFh
0x18026fd69  lock xadd [lpszShortTypeName+10h], eax
0x18026fd6e  sub     eax, 1
0x18026fd71  jg      short loc_18026FD83
0x18026fd73  mov     lpszCLSID, [lpszShortTypeName]
0x18026fd76  mov     rax, [lpszCLSID]
0x18026fd79  mov     rax, [rax+8]
0x18026fd7d  call    cs:__guard_dispatch_icall_fptr
0x18026fd83  mov     rbx, [rbp+regPreviewHandlersKey.m_hKey]
0x18026fd87  jmp     short loc_18026FD8B
0x18026fd89  xor     edi, edi
0x18026fd8b  test    rbx, rbx
0x18026fd8e  jz      short loc_18026FD9A
0x18026fd90  mov     lpszCLSID, rbx; hKey
0x18026fd93  call    cs:__imp_RegCloseKey
0x18026fd99  nop
0x18026fd9a  mov     lpszShortTypeName, [rbp+strData.m_pszData]
0x18026fd9e  add     lpszShortTypeName, 0FFFFFFFFFFFFFFE8h
0x18026fda2  or      ecx, 0FFFFFFFFh
0x18026fda5  lock xadd [lpszShortTypeName+10h], ecx
0x18026fdaa  sub     ecx, 1
0x18026fdad  jg      short loc_18026FDBF
0x18026fdaf  mov     lpszCLSID, [lpszShortTypeName]
0x18026fdb2  mov     lpszFilterExt, [lpszCLSID]
0x18026fdb5  mov     rax, [lpszFilterExt+8]
0x18026fdb9  call    cs:__guard_dispatch_icall_fptr
0x18026fdbf  mov     eax, edi
0x18026fdc1  lea     r11, [rsp+80h+var_s0]
0x18026fdc9  mov     rbx, [r11+20h]
0x18026fdcd  mov     rsi, [r11+28h]
0x18026fdd1  mov     rsp, r11
0x18026fdd4  pop     r14
0x18026fdd6  pop     rdi
0x18026fdd7  pop     rbp
0x18026fdd8  retn
```
