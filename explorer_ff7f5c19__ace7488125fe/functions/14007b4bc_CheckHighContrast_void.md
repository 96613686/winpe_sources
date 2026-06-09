# CheckHighContrast(void)

- ea: `0x14007b4bc`
- end: `0x14007b828`
- name: `?CheckHighContrast@@YAXXZ`
- size: `876`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007b430`
- `0x1400a3f04`

## callees

- `0x14001fae4`
- `0x140033ec0`
- `0x140079cc8`
- `0x14007b4bc`
- `0x14010e160`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x14007b6bf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x14007b6ff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x14007b6bf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x14007b6ff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b61c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b637`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b652`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b66d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b61c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b637`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b652`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14007b66d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14007b551`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14007b551`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007b526`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14007b526`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007b77b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14007b77b`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14007b74c`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14007b74c`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x14007b6e3`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x14007b6e3`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007b57e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007b72f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007b7fe`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007b57e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007b72f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x14007b7fe`

## string_xrefs

- `0x14007b51d`: `Control Panel\Accessibility\HighContrast`
- `0x14007b5a6`: `InstallHighContrast`
- `0x14007b73b`: `InstallHighContrast`
- `0x14007b62c`: `@themeui.dll,-851`
- `0x14007b611`: `@themeui.dll,-850`
- `0x14007b662`: `@themeui.dll,-853`
- `0x14007b647`: `@themeui.dll,-852`
- `0x14007b67d`: `@themeui.dll,-852`

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
0x14007b4bc  push    rbp
0x14007b4be  push    rbx
0x14007b4bf  push    rsi
0x14007b4c0  push    rdi
0x14007b4c1  push    r13
0x14007b4c3  lea     rbp, [rsp-3B0h]
0x14007b4cb  sub     rsp, 4B0h
0x14007b4d2  mov     rax, cs:__security_cookie
0x14007b4d9  xor     rax, rsp
0x14007b4dc  mov     [rbp+3D0h+var_30], rax
0x14007b4e3  xor     esi, esi
0x14007b4e5  mov     [rsp+4D0h+var_478], 14h
0x14007b4ed  lea     rax, [rsp+4D0h+var_478]
0x14007b4f2  mov     r13, 0FFFFFFFF80000001h
0x14007b4f9  mov     [rsp+4D0h+pcbData], rax; pcbData
0x14007b4fe  lea     r8, aFlags; "Flags"
0x14007b505  lea     rax, [rsp+4D0h+pszSrc]
0x14007b50a  mov     rcx, r13; hkey
0x14007b50d  mov     [rsp+4D0h+pvData], rax; pvData
0x14007b512  lea     ebx, [rsi+2]
0x14007b515  mov     r9d, ebx; dwFlags
0x14007b518  mov     [rsp+4D0h+pdwType], rsi; pdwType
0x14007b51d  lea     rdx, aControlPanelAc; "Control Panel\\Accessibility\\HighContr"...
0x14007b524  mov     edi, esi
0x14007b526  call    cs:__imp_RegGetValueW
0x14007b52d  nop     dword ptr [rax+rax+00h]
0x14007b532  mov     ecx, eax
0x14007b534  test    eax, eax
0x14007b536  jz      short loc_14007B548
0x14007b538  mov     [rsp+4D0h+pszSrc], si
0x14007b53d  jle     short loc_14007B548
0x14007b53f  movzx   ecx, ax
0x14007b542  or      ecx, 80070000h
0x14007b548  test    ecx, ecx
0x14007b54a  js      short loc_14007B55F
0x14007b54c  lea     rcx, [rsp+4D0h+pszSrc]; pszSrc
0x14007b551  call    cs:__imp_StrToIntW
0x14007b558  nop     dword ptr [rax+rax+00h]
0x14007b55d  mov     edi, eax
0x14007b55f  xor     r9d, r9d; fWinIni
0x14007b562  lea     r8, [rsp+4D0h+pvParam]; pvParam
0x14007b567  xorps   xmm0, xmm0
0x14007b56a  movups  [rsp+4D0h+pvParam], xmm0
0x14007b56f  mov     dword ptr [rsp+4D0h+pvParam], 10h
0x14007b577  lea     edx, [r9+10h]; uiParam
0x14007b57b  lea     ecx, [rdx+32h]; uiAction
0x14007b57e  call    cs:__imp_SystemParametersInfoW
0x14007b585  nop     dword ptr [rax+rax+00h]
0x14007b58a  test    eax, eax
0x14007b58c  jz      loc_14007B80A
0x14007b592  lea     rax, [rbp+3D0h+pszStr1]
0x14007b596  mov     dword ptr [rsp+4D0h+pvData], 104h; unsigned int
0x14007b59e  mov     r9d, ebx; int
0x14007b5a1  mov     [rsp+4D0h+pdwType], rax; unsigned __int16 *
0x14007b5a6  lea     r8, aInstallhighcon; "InstallHighContrast"
0x14007b5ad  mov     rcx, r13; HKEY
0x14007b5b0  lea     rdx, aSoftwareMicros_60; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007b5b7  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x14007b5bc  test    eax, eax
0x14007b5be  js      short loc_14007B5CA
0x14007b5c0  cmp     [rbp+3D0h+pszStr1], si
0x14007b5c4  jnz     loc_14007B6AA
0x14007b5ca  test    byte ptr [rsp+4D0h+pvParam+4], 1
0x14007b5cf  jz      loc_14007B699
0x14007b5d5  lea     rax, [rbp+3D0h+pszStr1]
0x14007b5d9  mov     dword ptr [rsp+4D0h+pvData], 104h; unsigned int
0x14007b5e1  mov     r9d, ebx; int
0x14007b5e4  mov     [rsp+4D0h+pdwType], rax; unsigned __int16 *
0x14007b5e9  lea     r8, aCurrent; "Current"
0x14007b5f0  mov     rcx, r13; HKEY
0x14007b5f3  lea     rdx, aControlPanelAp; "Control Panel\\Appearance"
0x14007b5fa  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x14007b5ff  test    eax, eax
0x14007b601  js      loc_14007B699
0x14007b607  cmp     [rbp+3D0h+pszStr1], si
0x14007b60b  jz      loc_14007B699
0x14007b611  lea     rdx, aThemeuiDll850; "@themeui.dll,-850"
0x14007b618  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x14007b61c  call    cs:__imp_StrCmpICW
0x14007b623  nop     dword ptr [rax+rax+00h]
0x14007b628  test    eax, eax
0x14007b62a  jz      short loc_14007B699
0x14007b62c  lea     rdx, aThemeuiDll851; "@themeui.dll,-851"
0x14007b633  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x14007b637  call    cs:__imp_StrCmpICW
0x14007b63e  nop     dword ptr [rax+rax+00h]
0x14007b643  test    eax, eax
0x14007b645  jz      short loc_14007B699
0x14007b647  lea     rdx, aThemeuiDll852; "@themeui.dll,-852"
0x14007b64e  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x14007b652  call    cs:__imp_StrCmpICW
0x14007b659  nop     dword ptr [rax+rax+00h]
0x14007b65e  test    eax, eax
0x14007b660  jz      short loc_14007B699
0x14007b662  lea     rdx, aThemeuiDll853; "@themeui.dll,-853"
0x14007b669  lea     rcx, [rbp+3D0h+pszStr1]; pszStr1
0x14007b66d  call    cs:__imp_StrCmpICW
0x14007b674  nop     dword ptr [rax+rax+00h]
0x14007b679  test    eax, eax
0x14007b67b  jz      short loc_14007B699
0x14007b67d  lea     r8, aThemeuiDll852; "@themeui.dll,-852"
0x14007b684  mov     edx, 104h; unsigned __int64
0x14007b689  lea     rcx, [rbp+3D0h+pszStr1]; unsigned __int16 *
0x14007b68d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14007b692  movzx   r10d, [rbp+3D0h+pszStr1]
0x14007b697  jmp     short loc_14007B6A0
0x14007b699  mov     r10d, esi
0x14007b69c  mov     [rbp+3D0h+pszStr1], si
0x14007b6a0  test    r10w, r10w
0x14007b6a4  jz      loc_14007B7B2
0x14007b6aa  test    byte ptr [rsp+4D0h+pvParam+4], 1
0x14007b6af  jz      short loc_14007B70F
0x14007b6b1  mov     rcx, qword ptr [rsp+4D0h+pvParam+8]; psz1
0x14007b6b6  test    rcx, rcx
0x14007b6b9  jz      short loc_14007B70F
0x14007b6bb  lea     rdx, [rbp+3D0h+pszStr1]; psz2
0x14007b6bf  call    cs:__imp_StrCmpIW
0x14007b6c6  nop     dword ptr [rax+rax+00h]
0x14007b6cb  test    eax, eax
0x14007b6cd  jz      short loc_14007B73B
0x14007b6cf  xor     r9d, r9d; ppvReserved
0x14007b6d2  lea     rdx, [rbp+3D0h+pszOutBuf]; pszOutBuf
0x14007b6d9  mov     r8d, 104h; cchOutBuf
0x14007b6df  lea     rcx, [rbp+3D0h+pszStr1]; pszSource
0x14007b6e3  call    cs:__imp_SHLoadIndirectString
0x14007b6ea  nop     dword ptr [rax+rax+00h]
0x14007b6ef  test    eax, eax
0x14007b6f1  js      short loc_14007B70F
0x14007b6f3  mov     rcx, qword ptr [rsp+4D0h+pvParam+8]; psz1
0x14007b6f8  lea     rdx, [rbp+3D0h+pszOutBuf]; psz2
0x14007b6ff  call    cs:__imp_StrCmpIW
0x14007b706  nop     dword ptr [rax+rax+00h]
0x14007b70b  test    eax, eax
0x14007b70d  jz      short loc_14007B73B
0x14007b70f  or      dword ptr [rsp+4D0h+pvParam+4], 1
0x14007b714  lea     rax, [rbp+3D0h+pszStr1]
0x14007b718  mov     r9d, 3; fWinIni
0x14007b71e  mov     qword ptr [rsp+4D0h+pvParam+8], rax
0x14007b723  lea     r8, [rsp+4D0h+pvParam]; pvParam
0x14007b728  lea     edx, [r9+0Dh]; uiParam
0x14007b72c  lea     ecx, [rdx+33h]; uiAction
0x14007b72f  call    cs:__imp_SystemParametersInfoW
0x14007b736  nop     dword ptr [rax+rax+00h]
0x14007b73b  lea     r8, aInstallhighcon; "InstallHighContrast"
0x14007b742  mov     rcx, r13; hkey
0x14007b745  lea     rdx, aSoftwareMicros_60; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14007b74c  call    cs:__imp_SHDeleteValueW
0x14007b753  nop     dword ptr [rax+rax+00h]
0x14007b758  xor     edx, edx; pUnkOuter
0x14007b75a  mov     qword ptr [rsp+4D0h+var_478], rsi
0x14007b75f  lea     rax, [rsp+4D0h+var_478]
0x14007b764  lea     r9, _GUID_c1e8c83e_845d_4d95_81db_e283fdffc000; riid
0x14007b76b  mov     [rsp+4D0h+pdwType], rax; ppv
0x14007b770  lea     rcx, CLSID_ThemeManager2; rclsid
0x14007b777  lea     r8d, [rdx+3]; dwClsContext
0x14007b77b  call    cs:__imp_CoCreateInstance
0x14007b782  nop     dword ptr [rax+rax+00h]
0x14007b787  test    eax, eax
0x14007b789  js      short loc_14007B80A
0x14007b78b  mov     rcx, qword ptr [rsp+4D0h+var_478]
0x14007b790  mov     rax, [rcx]
0x14007b793  mov     rax, [rax+0C0h]
0x14007b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007b79f  mov     rcx, qword ptr [rsp+4D0h+var_478]
0x14007b7a4  mov     rax, [rcx]
0x14007b7a7  mov     rax, [rax+10h]
0x14007b7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007b7b0  jmp     short loc_14007B80A
0x14007b7b2  mov     bl, byte ptr [rsp+4D0h+pvParam+4]
0x14007b7b6  lea     rdx, [rsp+4D0h+var_490]; bool *
0x14007b7bb  lea     rcx, [rsp+4D0h+var_48F]; bool *
0x14007b7c0  mov     [rsp+4D0h+var_48F], sil
0x14007b7c5  and     bl, 1
0x14007b7c8  mov     [rsp+4D0h+var_490], sil
0x14007b7cd  call    ?GetPerUserHighContrastSettings@@YAJPEA_N0@Z; GetPerUserHighContrastSettings(bool *,bool *)
0x14007b7d2  test    eax, eax
0x14007b7d4  js      short loc_14007B7E3
0x14007b7d6  cmp     bl, [rsp+4D0h+var_490]
0x14007b7da  jz      short loc_14007B7EC
0x14007b7dc  xor     dword ptr [rsp+4D0h+pvParam+4], 1
0x14007b7e1  jmp     short loc_14007B7EC
0x14007b7e3  and     dil, 1
0x14007b7e7  cmp     dil, bl
0x14007b7ea  jz      short loc_14007B80A
0x14007b7ec  mov     r9d, 3; fWinIni
0x14007b7f2  lea     r8, [rsp+4D0h+pvParam]; pvParam
0x14007b7f7  lea     edx, [r9+0Dh]; uiParam
0x14007b7fb  lea     ecx, [rdx+33h]; uiAction
0x14007b7fe  call    cs:__imp_SystemParametersInfoW
0x14007b805  nop     dword ptr [rax+rax+00h]
0x14007b80a  mov     rcx, [rbp+3D0h+var_30]
0x14007b811  xor     rcx, rsp; StackCookie
0x14007b814  call    __security_check_cookie
0x14007b819  add     rsp, 4B0h
0x14007b820  pop     r13
0x14007b822  pop     rdi
0x14007b823  pop     rsi
0x14007b824  pop     rbx
0x14007b825  pop     rbp
0x14007b826  retn
```
