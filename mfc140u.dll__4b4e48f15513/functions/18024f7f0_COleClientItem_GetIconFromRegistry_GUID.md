# COleClientItem::GetIconFromRegistry(_GUID &)

- ea: `0x18024f7f0`
- end: `0x18024fb12`
- name: `?GetIconFromRegistry@COleClientItem@@SAPEAUHICON__@@AEAU_GUID@@@Z`
- size: `802`
- prototype: `HICON__ *__fastcall(_GUID *clsid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18024f790`

## callees

- `0x18000df50`
- `0x180139860`
- `0x18024f7f0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18024f97d`
- `ADVAPI32!RegCloseKey` at `0x18024f988`
- `ADVAPI32!RegCloseKey` at `0x18024f993`
- `ADVAPI32!RegCloseKey` at `0x18024facb`
- `ADVAPI32!RegCloseKey` at `0x18024fad6`
- `ADVAPI32!RegCloseKey` at `0x18024f97d`
- `ADVAPI32!RegCloseKey` at `0x18024f988`
- `ADVAPI32!RegCloseKey` at `0x18024f993`
- `ADVAPI32!RegCloseKey` at `0x18024facb`
- `ADVAPI32!RegCloseKey` at `0x18024fad6`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f861`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f899`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f8c3`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f9e7`
- `ADVAPI32!RegOpenKeyExW` at `0x18024fa11`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f861`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f899`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f8c3`
- `ADVAPI32!RegOpenKeyExW` at `0x18024f9e7`
- `ADVAPI32!RegOpenKeyExW` at `0x18024fa11`
- `ADVAPI32!RegQueryValueExW` at `0x18024f8fc`
- `ADVAPI32!RegQueryValueExW` at `0x18024fa4a`
- `ADVAPI32!RegQueryValueExW` at `0x18024f8fc`
- `ADVAPI32!RegQueryValueExW` at `0x18024fa4a`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x18024f941`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x18024fa8f`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x18024f941`
- `api-ms-win-crt-convert-l1-1-0!_wtol` at `0x18024fa8f`
- `ole32!CoTaskMemFree` at `0x18024fae1`
- `ole32!CoTaskMemFree` at `0x18024fae1`
- `ole32!StringFromCLSID` at `0x18024f82c`
- `ole32!StringFromCLSID` at `0x18024f82c`
- `SHELL32!ExtractIconW` at `0x18024f967`
- `SHELL32!ExtractIconW` at `0x18024fab5`
- `SHELL32!ExtractIconW` at `0x18024f967`
- `SHELL32!ExtractIconW` at `0x18024fab5`

## string_xrefs

- `0x18024f853`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HICON __fastcall COleClientItem::GetIconFromRegistry(_GUID *clsid)
{
  HICON IconW; // rbx
  wchar_t *v3; // rdx
  wchar_t *v4; // rcx
  wchar_t i; // ax
  UINT v6; // ebx
  AFX_MODULE_STATE *ModuleState; // rax
  wchar_t *v8; // rdx
  wchar_t *v9; // rdx
  wchar_t *v10; // rcx
  wchar_t j; // ax
  UINT v12; // ebx
  AFX_MODULE_STATE *v13; // rax
  HKEY__ *hkeyDefIcon; // [rsp+38h] [rbp-D0h] BYREF
  HKEY__ *hkeyObj; // [rsp+40h] [rbp-C8h] BYREF
  HKEY__ *hkeyCLSID; // [rsp+48h] [rbp-C0h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strCLSID; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *szCLSID; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t szName[261]; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t szPathName[268]; // [rsp+270h] [rbp+168h] BYREF

  IconW = 0;
  HIDWORD(hkeyDefIcon) = 0;
  if ( StringFromCLSID(clsid, (LPOLESTR *)szName) < 0 )
    return 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20019u, (PHKEY)&strCLSID) )
    goto LABEL_38;
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&szCLSID,
    *(const wchar_t **)szName);
  if ( !RegOpenKeyExW((HKEY)strCLSID.m_pszData, szCLSID, 0, 0x20019u, &hkeyCLSID) )
  {
    if ( !RegOpenKeyExW(hkeyCLSID, L"DefaultIcon", 0, 0x20019u, &hkeyObj) )
    {
      LODWORD(hkeyDefIcon) = 522;
      if ( !RegQueryValueExW(hkeyObj, 0, 0, (LPDWORD)&hkeyDefIcon + 1, (LPBYTE)&szName[4], (LPDWORD)&hkeyDefIcon) )
      {
        v3 = &szPathName[4];
        v4 = &szName[4];
        for ( i = szName[4]; i != 44 && i; i = *v4 )
          *v3++ = *v4++;
        *v3 = 0;
        v6 = *v4 ? _wtol(v4 + 1) : 0;
        ModuleState = AfxGetModuleState();
        IconW = ExtractIconW(ModuleState->m_pCurrentWinApp->m_hInstance, &szPathName[4], v6);
        if ( IconW == (HICON)1 )
          IconW = 0;
      }
      RegCloseKey(hkeyObj);
    }
    RegCloseKey(hkeyCLSID);
  }
  RegCloseKey((HKEY)strCLSID.m_pszData);
  v8 = szCLSID - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)szCLSID - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  if ( !IconW )
  {
LABEL_38:
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"DocShortcut", 0, 0x20019u, &hkeyCLSID) )
    {
      if ( !RegOpenKeyExW(hkeyCLSID, L"DefaultIcon", 0, 0x20019u, &hkeyObj) )
      {
        LODWORD(hkeyDefIcon) = 522;
        if ( !RegQueryValueExW(hkeyObj, 0, 0, (LPDWORD)&hkeyDefIcon + 1, (LPBYTE)&szName[4], (LPDWORD)&hkeyDefIcon) )
        {
          v9 = &szPathName[4];
          v10 = &szName[4];
          for ( j = szName[4]; j != 44 && j; j = *v10 )
            *v9++ = *v10++;
          *v9 = 0;
          if ( *v10 )
            v12 = _wtol(v10 + 1);
          else
            v12 = 0;
          v13 = AfxGetModuleState();
          IconW = ExtractIconW(v13->m_pCurrentWinApp->m_hInstance, &szPathName[4], v12);
          if ( IconW == (HICON)1 )
            IconW = 0;
        }
        RegCloseKey(hkeyObj);
      }
      RegCloseKey(hkeyCLSID);
    }
  }
  CoTaskMemFree(*(LPVOID *)szName);
  return IconW;
}

```

## disassembly

```asm
0x18024f7f0  mov     rax, rsp
0x18024f7f3  mov     [rax+10h], rbx
0x18024f7f7  mov     [rax+18h], rdi
0x18024f7fb  mov     [rax+20h], r14
0x18024f7ff  push    rbp
0x18024f800  lea     rbp, [rax-398h]
0x18024f807  sub     rsp, 490h
0x18024f80e  mov     rax, cs:__security_cookie
0x18024f815  xor     rax, rsp
0x18024f818  mov     [rbp+390h+var_10], rax
0x18024f81f  xor     edi, edi
0x18024f821  mov     ebx, edi
0x18024f823  mov     dword ptr [rsp+490h+hkeyDefIcon+4], edi
0x18024f827  lea     rdx, [rsp+490h+szName]; lplpsz
0x18024f82c  call    cs:__imp_StringFromCLSID
0x18024f832  test    eax, eax
0x18024f834  jns     short loc_18024F83D
0x18024f836  xor     eax, eax
0x18024f838  jmp     loc_18024FAEA
0x18024f83d  lea     rax, [rsp+490h+strCLSID]
0x18024f842  mov     [rsp+490h+phkResult], rax; phkResult
0x18024f847  mov     r14d, 20019h
0x18024f84d  mov     r9d, r14d; samDesired
0x18024f850  xor     r8d, r8d; ulOptions
0x18024f853  lea     rdx, aClsid_0; "CLSID"
0x18024f85a  mov     clsid, 0FFFFFFFF80000000h; hKey
0x18024f861  call    cs:__imp_RegOpenKeyExW
0x18024f867  test    eax, eax
0x18024f869  jnz     loc_18024F9C9
0x18024f86f  mov     rdx, qword ptr [rsp+490h+szName]; pszSrc
0x18024f874  lea     clsid, [rsp+490h+szCLSID]; this
0x18024f879  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x18024f87e  nop
0x18024f87f  lea     rax, [rsp+490h+hkeyCLSID]
0x18024f884  mov     [rsp+490h+phkResult], rax; phkResult
0x18024f889  mov     r9d, r14d; samDesired
0x18024f88c  xor     r8d, r8d; ulOptions
0x18024f88f  mov     rdx, [rsp+490h+szCLSID]; lpSubKey
0x18024f894  mov     clsid, [rsp+490h+strCLSID.m_pszData]; hKey
0x18024f899  call    cs:__imp_RegOpenKeyExW
0x18024f89f  test    eax, eax
0x18024f8a1  jnz     loc_18024F98E
0x18024f8a7  lea     rax, [rsp+490h+hkeyObj]
0x18024f8ac  mov     [rsp+490h+phkResult], rax; phkResult
0x18024f8b1  mov     r9d, r14d; samDesired
0x18024f8b4  xor     r8d, r8d; ulOptions
0x18024f8b7  lea     rdx, aDefaulticon; "DefaultIcon"
0x18024f8be  mov     clsid, [rsp+490h+hkeyCLSID]; hKey
0x18024f8c3  call    cs:__imp_RegOpenKeyExW
0x18024f8c9  test    eax, eax
0x18024f8cb  jnz     loc_18024F983
0x18024f8d1  mov     dword ptr [rsp+490h+hkeyDefIcon], 20Ah
0x18024f8d9  lea     rax, [rsp+490h+hkeyDefIcon]
0x18024f8de  mov     qword ptr [rsp+490h+dwCount], rax; lpcbData
0x18024f8e3  lea     rax, [rsp+490h+szName+8]
0x18024f8e8  mov     [rsp+490h+phkResult], rax; lpData
0x18024f8ed  lea     r9, [rsp+490h+hkeyDefIcon+4]; lpType
0x18024f8f2  xor     r8d, r8d; lpReserved
0x18024f8f5  xor     edx, edx; lpValueName
0x18024f8f7  mov     clsid, [rsp+490h+hkeyObj]; hKey
0x18024f8fc  call    cs:__imp_RegQueryValueExW
0x18024f902  test    eax, eax
0x18024f904  jnz     short loc_18024F978
0x18024f906  lea     rdx, [rbp+390h+szPathName+8]
0x18024f90d  lea     clsid, [rsp+490h+szName+8]
0x18024f912  movzx   eax, [rsp+490h+szName+8]
0x18024f917  jmp     short loc_18024F92F
0x18024f919  test    ax, ax
0x18024f91c  jz      short loc_18024F935
0x18024f91e  movzx   eax, word ptr [clsid]
0x18024f921  mov     [rdx], ax
0x18024f924  add     rdx, 2
0x18024f928  add     clsid, 2
0x18024f92c  movzx   eax, word ptr [clsid]
0x18024f92f  cmp     ax, 2Ch ; ','
0x18024f933  jnz     short loc_18024F919
0x18024f935  mov     [rdx], di
0x18024f938  cmp     [clsid], di
0x18024f93b  jz      short loc_18024F94B
0x18024f93d  add     clsid, 2; String
0x18024f941  call    cs:__imp__wtol
0x18024f947  mov     ebx, eax
0x18024f949  jmp     short loc_18024F94D
0x18024f94b  mov     ebx, edi
0x18024f94d  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18024f952  mov     clsid, [rax+8]
0x18024f956  mov     r8d, ebx; nIconIndex
0x18024f959  lea     rdx, [rbp+390h+szPathName+8]; pszExeFileName
0x18024f960  mov     clsid, [clsid+88h]; hInst
0x18024f967  call    cs:__imp_ExtractIconW
0x18024f96d  mov     rbx, rax
0x18024f970  cmp     rax, 1
0x18024f974  cmovz   rbx, rdi
0x18024f978  mov     clsid, [rsp+490h+hkeyObj]; hKey
0x18024f97d  call    cs:__imp_RegCloseKey
0x18024f983  mov     clsid, [rsp+490h+hkeyCLSID]; hKey
0x18024f988  call    cs:__imp_RegCloseKey
0x18024f98e  mov     clsid, [rsp+490h+strCLSID.m_pszData]; hKey
0x18024f993  call    cs:__imp_RegCloseKey
0x18024f999  nop
0x18024f99a  mov     rdx, [rsp+490h+szCLSID]
0x18024f99f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18024f9a3  or      eax, 0FFFFFFFFh
0x18024f9a6  lock xadd [rdx+10h], eax
0x18024f9ab  sub     eax, 1
0x18024f9ae  jg      short loc_18024F9C0
0x18024f9b0  mov     clsid, [rdx]
0x18024f9b3  mov     rax, [clsid]
0x18024f9b6  mov     rax, [rax+8]
0x18024f9ba  call    cs:__guard_dispatch_icall_fptr
0x18024f9c0  test    rbx, rbx
0x18024f9c3  jnz     loc_18024FADC
0x18024f9c9  lea     rax, [rsp+490h+hkeyCLSID]
0x18024f9ce  mov     [rsp+490h+phkResult], rax; phkResult
0x18024f9d3  mov     r9d, r14d; samDesired
0x18024f9d6  xor     r8d, r8d; ulOptions
0x18024f9d9  lea     rdx, aDocshortcut; "DocShortcut"
0x18024f9e0  mov     clsid, 0FFFFFFFF80000000h; hKey
0x18024f9e7  call    cs:__imp_RegOpenKeyExW
0x18024f9ed  test    eax, eax
0x18024f9ef  jnz     loc_18024FADC
0x18024f9f5  lea     rax, [rsp+490h+hkeyObj]
0x18024f9fa  mov     [rsp+490h+phkResult], rax; phkResult
0x18024f9ff  mov     r9d, r14d; samDesired
0x18024fa02  xor     r8d, r8d; ulOptions
0x18024fa05  lea     rdx, aDefaulticon; "DefaultIcon"
0x18024fa0c  mov     clsid, [rsp+490h+hkeyCLSID]; hKey
0x18024fa11  call    cs:__imp_RegOpenKeyExW
0x18024fa17  test    eax, eax
0x18024fa19  jnz     loc_18024FAD1
0x18024fa1f  mov     dword ptr [rsp+490h+hkeyDefIcon], 20Ah
0x18024fa27  lea     rax, [rsp+490h+hkeyDefIcon]
0x18024fa2c  mov     qword ptr [rsp+490h+dwCount], rax; lpcbData
0x18024fa31  lea     rax, [rsp+490h+szName+8]
0x18024fa36  mov     [rsp+490h+phkResult], rax; lpData
0x18024fa3b  lea     r9, [rsp+490h+hkeyDefIcon+4]; lpType
0x18024fa40  xor     r8d, r8d; lpReserved
0x18024fa43  xor     edx, edx; lpValueName
0x18024fa45  mov     clsid, [rsp+490h+hkeyObj]; hKey
0x18024fa4a  call    cs:__imp_RegQueryValueExW
0x18024fa50  test    eax, eax
0x18024fa52  jnz     short loc_18024FAC6
0x18024fa54  lea     rdx, [rbp+390h+szPathName+8]
0x18024fa5b  lea     clsid, [rsp+490h+szName+8]
0x18024fa60  movzx   eax, [rsp+490h+szName+8]
0x18024fa65  jmp     short loc_18024FA7D
0x18024fa67  test    ax, ax
0x18024fa6a  jz      short loc_18024FA83
0x18024fa6c  movzx   eax, word ptr [clsid]
0x18024fa6f  mov     [rdx], ax
0x18024fa72  add     rdx, 2
0x18024fa76  add     clsid, 2
0x18024fa7a  movzx   eax, word ptr [clsid]
0x18024fa7d  cmp     ax, 2Ch ; ','
0x18024fa81  jnz     short loc_18024FA67
0x18024fa83  mov     [rdx], di
0x18024fa86  cmp     [clsid], di
0x18024fa89  jz      short loc_18024FA99
0x18024fa8b  add     clsid, 2; String
0x18024fa8f  call    cs:__imp__wtol
0x18024fa95  mov     ebx, eax
0x18024fa97  jmp     short loc_18024FA9B
0x18024fa99  mov     ebx, edi
0x18024fa9b  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x18024faa0  mov     clsid, [rax+8]
0x18024faa4  mov     r8d, ebx; nIconIndex
0x18024faa7  lea     rdx, [rbp+390h+szPathName+8]; pszExeFileName
0x18024faae  mov     clsid, [clsid+88h]; hInst
0x18024fab5  call    cs:__imp_ExtractIconW
0x18024fabb  mov     rbx, rax
0x18024fabe  cmp     rax, 1
0x18024fac2  cmovz   rbx, rdi
0x18024fac6  mov     clsid, [rsp+490h+hkeyObj]; hKey
0x18024facb  call    cs:__imp_RegCloseKey
0x18024fad1  mov     clsid, [rsp+490h+hkeyCLSID]; hKey
0x18024fad6  call    cs:__imp_RegCloseKey
0x18024fadc  mov     clsid, qword ptr [rsp+490h+szName]; pv
0x18024fae1  call    cs:__imp_CoTaskMemFree
0x18024fae7  mov     rax, rbx
0x18024faea  mov     clsid, [rbp+390h+var_10]
0x18024faf1  xor     clsid, rsp; StackCookie
0x18024faf4  call    __security_check_cookie
0x18024faf9  lea     r11, [rsp+490h+var_s0]
0x18024fb01  mov     rbx, [r11+18h]
0x18024fb05  mov     rdi, [r11+20h]
0x18024fb09  mov     r14, [r11+28h]
0x18024fb0d  mov     rsp, r11
0x18024fb10  pop     rbp
0x18024fb11  retn
```
