# CheckHighContrast(void)

- ea: `0x140076410`
- end: `0x14007671f`
- name: `?CheckHighContrast@@YAXXZ`
- size: `783`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400763a0`
- `0x14009ae00`

## callees

- `0x140014ec4`
- `0x14003dd00`
- `0x140075164`
- `0x140076410`
- `0x1401040e0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14007649f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14007649f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x140076556`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007656b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x140076580`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x140076595`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x140076556`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007656b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x140076580`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x140076595`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1400765e1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x140076615`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1400765e1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x140076615`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007647a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007647a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007667f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007667f`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x140076656`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x140076656`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1400765ff`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1400765ff`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400764c6`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007663f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400766fc`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400764c6`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007663f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400766fc`

## string_xrefs

- `0x140076471`: `Control Panel\Accessibility\HighContrast`
- `0x1400764e8`: `InstallHighContrast`
- `0x140076645`: `InstallHighContrast`
- `0x140076560`: `@themeui.dll,-851`
- `0x14007654b`: `@themeui.dll,-850`
- `0x14007658a`: `@themeui.dll,-853`
- `0x140076575`: `@themeui.dll,-852`
- `0x14007659f`: `@themeui.dll,-852`

## pseudocode

```c
void CheckHighContrast(void)
{
  char v0; // di
  LSTATUS ValueW; // eax
  signed int v2; // ecx
  WCHAR v3; // r10
  char v4; // bl
  bool v5; // [rsp+40h] [rbp-C0h] BYREF
  bool v6; // [rsp+41h] [rbp-BFh] BYREF
  __int128 pvParam; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszSrc[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszStr1[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR pszOutBuf[264]; // [rsp+290h] [rbp+190h] BYREF

  pcbData[0] = 20;
  v0 = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Control Panel\\Accessibility\\HighContrast",
             L"Flags",
             2u,
             0,
             pszSrc,
             pcbData);
  v2 = ValueW;
  if ( ValueW )
  {
    pszSrc[0] = 0;
    if ( ValueW > 0 )
      v2 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v2 >= 0 )
    v0 = StrToIntW(pszSrc);
  pvParam = 0;
  LODWORD(pvParam) = 16;
  if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) )
  {
    if ( (int)SHRegGetStringEx(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                L"InstallHighContrast",
                2,
                pszStr1,
                0x104u) >= 0
      && pszStr1[0]
      || ((BYTE4(pvParam) & 1) == 0
       || (int)SHRegGetStringEx(HKEY_CURRENT_USER, L"Control Panel\\Appearance", L"Current", 2, pszStr1, 0x104u) < 0
       || !pszStr1[0]
       || !StrCmpICW(pszStr1, L"@themeui.dll,-850")
       || !StrCmpICW(pszStr1, L"@themeui.dll,-851")
       || !StrCmpICW(pszStr1, L"@themeui.dll,-852")
       || !StrCmpICW(pszStr1, L"@themeui.dll,-853")
        ? (v3 = 0, pszStr1[0] = 0)
        : (StringCchCopyW(pszStr1, 0x104u, L"@themeui.dll,-852"), v3 = pszStr1[0]),
          v3) )
    {
      if ( (BYTE4(pvParam) & 1) == 0
        || !*((_QWORD *)&pvParam + 1)
        || StrCmpIW(*((PCWSTR *)&pvParam + 1), pszStr1)
        && (SHLoadIndirectString(pszStr1, pszOutBuf, 0x104u, 0) < 0 || StrCmpIW(*((PCWSTR *)&pvParam + 1), pszOutBuf)) )
      {
        DWORD1(pvParam) |= 1u;
        *((_QWORD *)&pvParam + 1) = pszStr1;
        SystemParametersInfoW(0x43u, 0x10u, &pvParam, 3u);
      }
      SHDeleteValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"InstallHighContrast");
      *(_QWORD *)pcbData = 0;
      if ( CoCreateInstance(&CLSID_ThemeManager2, 0, 3u, &GUID_c1e8c83e_845d_4d95_81db_e283fdffc000, (LPVOID *)pcbData) >= 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 192LL))(*(_QWORD *)pcbData);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
      }
    }
    else
    {
      v6 = 0;
      v4 = BYTE4(pvParam) & 1;
      v5 = 0;
      if ( (int)GetPerUserHighContrastSettings(&v6, &v5) < 0 )
      {
        if ( (v0 & 1) == v4 )
          return;
      }
      else if ( v4 != v5 )
      {
        DWORD1(pvParam) ^= 1u;
      }
      SystemParametersInfoW(0x43u, 0x10u, &pvParam, 3u);
    }
  }
}

```

## disassembly

```asm
0x140076410  push    rbp
0x140076412  push    rbx
0x140076413  push    rsi
0x140076414  push    rdi
0x140076415  push    r13
0x140076417  lea     rbp, [rsp-3B0h]
0x14007641f  sub     rsp, 4B0h
0x140076426  mov     rax, cs:__security_cookie
0x14007642d  xor     rax, rsp
0x140076430  mov     [rbp+3D0h+var_30], rax
0x140076437  xor     esi, esi
0x140076439  mov     [rsp+4D0h+var_478], 14h
0x140076441  lea     rax, [rsp+4D0h+var_478]
0x140076446  mov     r13, 0FFFFFFFF80000001h
0x14007644d  mov     [rsp+4D0h+pcbData], rax; pcbData
0x140076452  lea     r8, aFlags; "Flags"
0x140076459  lea     rax, [rsp+4D0h+pszSrc]
0x14007645e  mov     rcx, r13; hkey
0x140076461  mov     [rsp+4D0h+pvData], rax; pvData
0x140076466  lea     ebx, [rsi+2]
0x140076469  mov     r9d, ebx; dwFlags
0x14007646c  mov     [rsp+4D0h+pdwType], rsi; pdwType
0x140076471  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility\\HighContr"...
0x140076478  mov     edi, esi
0x14007647a  call    cs:__imp_RegGetValueW
0x140076480  mov     ecx, eax
0x140076482  test    eax, eax
0x140076484  jz      short loc_140076496
0x140076486  mov     [rsp+4D0h+pszSrc], si
0x14007648b  jle     short loc_140076496
0x14007648d  movzx   ecx, ax
0x140076490  or      ecx, 80070000h
0x140076496  test    ecx, ecx
0x140076498  js      short loc_1400764A7
0x14007649a  lea     rcx, [rsp+4D0h+pszSrc]; pszSrc
0x14007649f  call    cs:__imp_StrToIntW
0x1400764a5  mov     edi, eax
0x1400764a7  xor     r9d, r9d; fWinIni
0x1400764aa  lea     r8, [rsp+4D0h+pvParam]; pvParam
0x1400764af  xorps   xmm0, xmm0
0x1400764b2  movups  [rsp+4D0h+pvParam], xmm0
0x1400764b7  mov     dword ptr [rsp+4D0h+pvParam], 10h
0x1400764bf  lea     edx, [r9+10h]; uiParam
0x1400764c3  lea     ecx, [rdx+32h]; uiAction
0x1400764c6  call    cs:__imp_SystemParametersInfoW
0x1400764cc  test    eax, eax
0x1400764ce  jz      loc_140076702
0x1400764d4  lea     rax, [rbp+3D0h+pszStr1]
0x1400764d8  mov     dword ptr [rsp+4D0h+pvData], 104h; unsigned int
0x1400764e0  mov     r9d, ebx; int
0x1400764e3  mov     [rsp+4D0h+pdwType], rax; unsigned __int16 *
0x1400764e8  lea     r8, aInstallhighcon; "InstallHighContrast"
0x1400764ef  mov     rcx, r13; HKEY
0x1400764f2  lea     rdx, aSoftwareMicros_60; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400764f9  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1400764fe  test    eax, eax
0x140076500  js      short loc_14007650C
0x140076502  cmp     [rbp+3D0h+pszStr1], si
0x140076506  jnz     loc_1400765CC
0x14007650c  test    byte ptr [rsp+4D0h+pvParam+4], 1
0x140076511  jz      loc_1400765BB
0x140076517  lea     rax, [rbp+3D0h+pszStr1]
0x14007651b  mov     dword ptr [rsp+4D0h+pvData], 104h; unsigned int
0x140076523  mov     r9d, ebx; int
0x140076526  mov     [rsp+4D0h+pdwType], rax; unsigned __int16 *
0x14007652b  lea     r8, aCurrent; "Current"
0x140076532  mov     rcx, r13; HKEY
0x140076535  lea     rdx, aControlPanelAp; "Control Panel\\Appearance"
0x14007653c  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x140076541  test    eax, eax
0x140076543  js      short loc_1400765BB
0x140076545  cmp     [rbp+3D0h+pszStr1], si
0x140076549  jz      short loc_1400765BB
0x14007654b  lea     rdx, aThemeuiDll850; "@themeui.dll,-850"
0x140076552  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x140076556  call    cs:__imp_StrCmpICW
0x14007655c  test    eax, eax
0x14007655e  jz      short loc_1400765BB
0x140076560  lea     rdx, aThemeuiDll851; "@themeui.dll,-851"
0x140076567  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x14007656b  call    cs:__imp_StrCmpICW
0x140076571  test    eax, eax
0x140076573  jz      short loc_1400765BB
0x140076575  lea     rdx, aThemeuiDll852; "@themeui.dll,-852"
0x14007657c  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x140076580  call    cs:__imp_StrCmpICW
0x140076586  test    eax, eax
0x140076588  jz      short loc_1400765BB
0x14007658a  lea     rdx, aThemeuiDll853; "@themeui.dll,-853"
0x140076591  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x140076595  call    cs:__imp_StrCmpICW
0x14007659b  test    eax, eax
0x14007659d  jz      short loc_1400765BB
0x14007659f  lea     r8, aThemeuiDll852; "@themeui.dll,-852"
0x1400765a6  mov     edx, 104h; unsigned __int64
0x1400765ab  lea     rcx, [rbp+3D0h+pszStr1]; unsigned __int16 *
0x1400765af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400765b4  movzx   r10d, [rbp+3D0h+pszStr1]
0x1400765b9  jmp     short loc_1400765C2
0x1400765bb  mov     r10d, esi
0x1400765be  mov     [rbp+3D0h+pszStr1], si
0x1400765c2  test    r10w, r10w
0x1400765c6  jz      loc_1400766B0
0x1400765cc  test    byte ptr [rsp+4D0h+pvParam+4], 1
0x1400765d1  jz      short loc_14007661F
0x1400765d3  mov     rcx, qword ptr [rsp+4D0h+pvParam+8]; psz1
0x1400765d8  test    rcx, rcx
0x1400765db  jz      short loc_14007661F
0x1400765dd  lea     rdx, [rbp+3D0h+pszStr1]; psz2
0x1400765e1  call    cs:__imp_StrCmpIW
0x1400765e7  test    eax, eax
0x1400765e9  jz      short loc_140076645
0x1400765eb  xor     r9d, r9d; ppvReserved
0x1400765ee  lea     rdx, [rbp+3D0h+pszOutBuf]; pszOutBuf
0x1400765f5  mov     r8d, 104h; cchOutBuf
0x1400765fb  lea     rcx, [rbp+3D0h+pszStr1]; pszSource
0x1400765ff  call    cs:__imp_SHLoadIndirectString
0x140076605  test    eax, eax
0x140076607  js      short loc_14007661F
0x140076609  mov     rcx, qword ptr [rsp+4D0h+pvParam+8]; psz1
0x14007660e  lea     rdx, [rbp+3D0h+pszOutBuf]; psz2
0x140076615  call    cs:__imp_StrCmpIW
0x14007661b  test    eax, eax
0x14007661d  jz      short loc_140076645
0x14007661f  or      dword ptr [rsp+4D0h+pvParam+4], 1
0x140076624  lea     rax, [rbp+3D0h+pszStr1]
0x140076628  mov     r9d, 3; fWinIni
0x14007662e  mov     qword ptr [rsp+4D0h+pvParam+8], rax
0x140076633  lea     r8, [rsp+4D0h+pvParam]; pvParam
0x140076638  lea     edx, [r9+0Dh]; uiParam
0x14007663c  lea     ecx, [rdx+33h]; uiAction
0x14007663f  call    cs:__imp_SystemParametersInfoW
0x140076645  lea     r8, aInstallhighcon; "InstallHighContrast"
0x14007664c  mov     rcx, r13; hkey
0x14007664f  lea     rdx, aSoftwareMicros_60; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140076656  call    cs:__imp_SHDeleteValueW
0x14007665c  xor     edx, edx; pUnkOuter
0x14007665e  mov     qword ptr [rsp+4D0h+var_478], rsi
0x140076663  lea     rax, [rsp+4D0h+var_478]
0x140076668  lea     r9, _GUID_c1e8c83e_845d_4d95_81db_e283fdffc000; riid
0x14007666f  mov     [rsp+4D0h+pdwType], rax; ppv
0x140076674  lea     rcx, CLSID_ThemeManager2; rclsid
0x14007667b  lea     r8d, [rdx+3]; dwClsContext
0x14007667f  call    cs:__imp_CoCreateInstance
0x140076685  test    eax, eax
0x140076687  js      short loc_140076702
0x140076689  mov     rcx, qword ptr [rsp+4D0h+var_478]
0x14007668e  mov     rax, [rcx]
0x140076691  mov     rax, [rax+0C0h]
0x140076698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007669d  mov     rcx, qword ptr [rsp+4D0h+var_478]
0x1400766a2  mov     rax, [rcx]
0x1400766a5  mov     rax, [rax+10h]
0x1400766a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400766ae  jmp     short loc_140076702
0x1400766b0  mov     bl, byte ptr [rsp+4D0h+pvParam+4]
0x1400766b4  lea     rdx, [rsp+4D0h+var_490]; bool *
0x1400766b9  lea     rcx, [rsp+4D0h+var_48F]; bool *
0x1400766be  mov     [rsp+4D0h+var_48F], sil
0x1400766c3  and     bl, 1
0x1400766c6  mov     [rsp+4D0h+var_490], sil
0x1400766cb  call    ?GetPerUserHighContrastSettings@@YAJPEA_N0@Z; GetPerUserHighContrastSettings(bool *,bool *)
0x1400766d0  test    eax, eax
0x1400766d2  js      short loc_1400766E1
0x1400766d4  cmp     bl, [rsp+4D0h+var_490]
0x1400766d8  jz      short loc_1400766EA
0x1400766da  xor     dword ptr [rsp+4D0h+pvParam+4], 1
0x1400766df  jmp     short loc_1400766EA
0x1400766e1  and     dil, 1
0x1400766e5  cmp     dil, bl
0x1400766e8  jz      short loc_140076702
0x1400766ea  mov     r9d, 3; fWinIni
0x1400766f0  lea     r8, [rsp+4D0h+pvParam]; pvParam
0x1400766f5  lea     edx, [r9+0Dh]; uiParam
0x1400766f9  lea     ecx, [rdx+33h]; uiAction
0x1400766fc  call    cs:__imp_SystemParametersInfoW
0x140076702  mov     rcx, [rbp+3D0h+var_30]
0x140076709  xor     rcx, rsp; StackCookie
0x14007670c  call    __security_check_cookie
0x140076711  add     rsp, 4B0h
0x140076718  pop     r13
0x14007671a  pop     rdi
0x14007671b  pop     rsi
0x14007671c  pop     rbx
0x14007671d  pop     rbp
0x14007671e  retn
```
