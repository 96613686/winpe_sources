# CFDRPlugin::WriteFDRSessionSettings(wchar_t const *)

- ea: `0x180036a5c`
- end: `0x180036de7`
- name: `?WriteFDRSessionSettings@CFDRPlugin@@AEAAJPEB_W@Z`
- size: `907`
- prototype: `int(CFDRPlugin *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035224`

## callees

- `0x1800028b4`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x1800354c8`
- `0x180036a5c`
- `0x180036ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036bd9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036c39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036cd5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036bd9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036c39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180036cd5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036b1d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180036b1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036acc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036dc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036acc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036dc7`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180036d42`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180036d42`

## string_xrefs

- `0x180036af3`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\FDR\CurrentSession`
- `0x180036c32`: `AppPath`
- `0x180036cc3`: `LogPath`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::WriteFDRSessionSettings(const BYTE **this, const BYTE *a2)
{
  HKEY v3; // rcx
  BYTE *v5; // r15
  HKEY *phkResult; // rax
  const struct std::nothrow_t *v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // ebx
  int v12; // eax
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // eax
  LPCWSTR pszPath[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+50h] BYREF
  BYTE *lpData; // [rsp+B8h] [rbp+58h] BYREF

  dwDisposition = 0;
  v3 = 0;
  hKey = 0;
  pszPath[0] = 0;
  v5 = 0;
  lpData = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      v3 = hKey;
    }
    if ( v3 )
      RegCloseKey(v3);
    return 2147942487LL;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\FDR\\CurrentSession",
         0,
         0,
         1u,
         0x60002u,
         0,
         phkResult,
         &dwDisposition) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v10 = 35;
    goto LABEL_12;
  }
  v12 = WerPluginAdjustAppContainerAccessToKey(hKey, (enum _ACCESS_MODE)v8, 0x80010002);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_928a4490cd403d1d5470036a68085293_Traceguids,
      (unsigned int)v12);
  }
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)&a2[2 * v14] );
  if ( RegSetValueExW(hKey, L"SessionSettings", 0, 1u, a2, 2 * v14 + 2) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v10 = 37;
    goto LABEL_12;
  }
  if ( RegSetValueExW(hKey, L"AppPath", 0, 1u, this[1], 2 * ((this[2] - this[1]) >> 1) + 2) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v10 = 38;
    goto LABEL_12;
  }
  v11 = CFDRPlugin::GenerateLogPathAndFileName(v15, pszPath, &lpData);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    v5 = lpData;
    goto LABEL_54;
  }
  v5 = lpData;
  do
    ++v13;
  while ( *(_WORD *)&lpData[2 * v13] );
  if ( !RegSetValueExW(hKey, L"LogPath", 0, 1u, lpData, 2 * v13 + 2) )
  {
    v8 = (const struct std::nothrow_t *)pszPath[0];
    if ( pszPath[0] )
    {
      v17 = SHCreateDirectoryExW(0, pszPath[0], 0);
      if ( !v17 || v17 == 183 )
      {
        v11 = 0;
        goto LABEL_54;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      v11 = -2147467259;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
        v16 = WPP_GLOBAL_Control;
      }
      v11 = -2147024809;
    }
    if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      WPP_SF_(v16[2], 41, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
    goto LABEL_54;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 40;
LABEL_12:
    WPP_SF_(v9[2], v10, &WPP_928a4490cd403d1d5470036a68085293_Traceguids);
  }
LABEL_13:
  v11 = -2147467259;
LABEL_54:
  if ( v5 )
    operator delete(v5, v8);
  if ( pszPath[0] )
    operator delete((void *)pszPath[0], v8);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180036a5c  mov     [rsp-38h+arg_0], rbx
0x180036a61  push    rbp
0x180036a62  push    rsi
0x180036a63  push    rdi
0x180036a64  push    r12
0x180036a66  push    r13
0x180036a68  push    r14
0x180036a6a  push    r15
0x180036a6c  mov     rbp, rsp
0x180036a6f  sub     rsp, 60h
0x180036a73  xor     edi, edi
0x180036a75  mov     r13, rcx
0x180036a78  mov     [rbp+dwDisposition], edi
0x180036a7b  mov     ecx, edi
0x180036a7d  mov     [rbp+hKey], rcx
0x180036a81  mov     rbx, rdx
0x180036a84  mov     [rbp+pszPath], rdi
0x180036a88  mov     r15d, edi
0x180036a8b  mov     [rbp+lpData], rdi
0x180036a8f  test    rdx, rdx
0x180036a92  jnz     short loc_180036ADC
0x180036a94  mov     rax, cs:WPP_GLOBAL_Control
0x180036a9b  lea     rdi, WPP_GLOBAL_Control
0x180036aa2  cmp     rax, rdi
0x180036aa5  jz      short loc_180036AC7
0x180036aa7  lea     esi, [rdx+1]
0x180036aaa  test    [rax+1Ch], sil
0x180036aae  jz      short loc_180036AC7
0x180036ab0  mov     rcx, [rax+10h]
0x180036ab4  lea     edx, [rbx+22h]
0x180036ab7  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180036abe  call    WPP_SF_
0x180036ac3  mov     rcx, [rbp+hKey]; hKey
0x180036ac7  test    rcx, rcx
0x180036aca  jz      short loc_180036AD2
0x180036acc  call    cs:__imp_RegCloseKey
0x180036ad2  mov     eax, 80070057h
0x180036ad7  jmp     loc_180036DCF
0x180036adc  lea     rcx, [rbp+hKey]
0x180036ae0  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180036ae5  lea     rcx, [rbp+dwDisposition]
0x180036ae9  mov     esi, 1
0x180036aee  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x180036af3  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\Windows E"...
0x180036afa  mov     [rsp+60h+phkResult], rax; phkResult
0x180036aff  xor     r9d, r9d; lpClass
0x180036b02  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180036b07  xor     r8d, r8d; Reserved
0x180036b0a  mov     [rsp+60h+samDesired], 60002h; samDesired
0x180036b12  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180036b19  mov     [rsp+60h+dwOptions], esi; dwOptions
0x180036b1d  call    cs:__imp_RegCreateKeyExW
0x180036b23  test    eax, eax
0x180036b25  jz      short loc_180036B5D
0x180036b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b2e  lea     rdi, WPP_GLOBAL_Control
0x180036b35  cmp     rcx, rdi
0x180036b38  jz      short loc_180036B53
0x180036b3a  test    [rcx+1Ch], sil
0x180036b3e  jz      short loc_180036B53
0x180036b40  lea     edx, [rsi+22h]
0x180036b43  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180036b4a  mov     rcx, [rcx+10h]
0x180036b4e  call    WPP_SF_
0x180036b53  mov     ebx, 80004005h
0x180036b58  jmp     loc_180036DA3
0x180036b5d  mov     rcx, [rbp+hKey]; hKey
0x180036b61  mov     r8d, 80010002h; unsigned int
0x180036b67  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x180036b6c  xor     ecx, ecx
0x180036b6e  lea     r14, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180036b75  lea     rdi, WPP_GLOBAL_Control
0x180036b7c  test    eax, eax
0x180036b7e  jns     short loc_180036BA8
0x180036b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b87  cmp     rcx, rdi
0x180036b8a  jz      short loc_180036BA6
0x180036b8c  test    byte ptr [rcx+1Ch], 2
0x180036b90  jz      short loc_180036BA6
0x180036b92  mov     rcx, [rcx+10h]
0x180036b96  mov     edx, 24h ; '$'
0x180036b9b  mov     r9d, eax
0x180036b9e  mov     r8, r14
0x180036ba1  call    WPP_SF_d
0x180036ba6  xor     ecx, ecx
0x180036ba8  or      r12, 0FFFFFFFFFFFFFFFFh
0x180036bac  mov     rax, r12
0x180036baf  inc     rax
0x180036bb2  cmp     [rbx+rax*2], cx
0x180036bb6  jnz     short loc_180036BAF
0x180036bb8  mov     rcx, [rbp+hKey]; hKey
0x180036bbc  lea     eax, ds:2[rax*2]
0x180036bc3  mov     [rsp+60h+samDesired], eax; cbData
0x180036bc7  lea     rdx, aSessionsetting; "SessionSettings"
0x180036bce  mov     r9d, esi; dwType
0x180036bd1  mov     qword ptr [rsp+60h+dwOptions], rbx; lpData
0x180036bd6  xor     r8d, r8d; Reserved
0x180036bd9  call    cs:__imp_RegSetValueExW
0x180036bdf  test    eax, eax
0x180036be1  jz      short loc_180036C0A
0x180036be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180036bea  cmp     rcx, rdi
0x180036bed  jz      loc_180036B53
0x180036bf3  test    [rcx+1Ch], sil
0x180036bf7  jz      loc_180036B53
0x180036bfd  mov     edx, 25h ; '%'
0x180036c02  mov     r8, r14
0x180036c05  jmp     loc_180036B4A
0x180036c0a  mov     rdx, [r13+8]
0x180036c0e  mov     r9d, esi; dwType
0x180036c11  mov     rax, [r13+10h]
0x180036c15  xor     r8d, r8d; Reserved
0x180036c18  mov     rcx, [rbp+hKey]; hKey
0x180036c1c  sub     rax, rdx
0x180036c1f  sar     rax, 1
0x180036c22  lea     eax, ds:2[rax*2]
0x180036c29  mov     [rsp+60h+samDesired], eax; cbData
0x180036c2d  mov     qword ptr [rsp+60h+dwOptions], rdx; lpData
0x180036c32  lea     rdx, aApppath; "AppPath"
0x180036c39  call    cs:__imp_RegSetValueExW
0x180036c3f  xor     r13d, r13d
0x180036c42  test    eax, eax
0x180036c44  jz      short loc_180036C66
0x180036c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c4d  cmp     rcx, rdi
0x180036c50  jz      loc_180036B53
0x180036c56  test    [rcx+1Ch], sil
0x180036c5a  jz      loc_180036B53
0x180036c60  lea     edx, [r13+26h]
0x180036c64  jmp     short loc_180036C02
0x180036c66  lea     r8, [rbp+lpData]
0x180036c6a  lea     rdx, [rbp+pszPath]
0x180036c6e  call    ?GenerateLogPathAndFileName@CFDRPlugin@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@0K@Z; CFDRPlugin::GenerateLogPathAndFileName(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,ulong)
0x180036c73  mov     ebx, eax
0x180036c75  test    eax, eax
0x180036c77  jns     short loc_180036CA5
0x180036c79  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c80  cmp     rcx, rdi
0x180036c83  jz      short loc_180036C9C
0x180036c85  test    [rcx+1Ch], sil
0x180036c89  jz      short loc_180036C9C
0x180036c8b  mov     rcx, [rcx+10h]
0x180036c8f  mov     edx, 27h ; '''
0x180036c94  mov     r8, r14
0x180036c97  call    WPP_SF_
0x180036c9c  mov     r15, [rbp+lpData]
0x180036ca0  jmp     loc_180036DA3
0x180036ca5  mov     r15, [rbp+lpData]
0x180036ca9  inc     r12
0x180036cac  cmp     [r15+r12*2], r13w
0x180036cb1  jnz     short loc_180036CA9
0x180036cb3  mov     rcx, [rbp+hKey]; hKey
0x180036cb7  lea     eax, ds:2[r12*2]
0x180036cbf  mov     [rsp+60h+samDesired], eax; cbData
0x180036cc3  lea     rdx, aLogpath; "LogPath"
0x180036cca  mov     r9d, esi; dwType
0x180036ccd  mov     qword ptr [rsp+60h+dwOptions], r15; lpData
0x180036cd2  xor     r8d, r8d; Reserved
0x180036cd5  call    cs:__imp_RegSetValueExW
0x180036cdb  test    eax, eax
0x180036cdd  jz      short loc_180036D03
0x180036cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ce6  cmp     rcx, rdi
0x180036ce9  jz      loc_180036B53
0x180036cef  test    [rcx+1Ch], sil
0x180036cf3  jz      loc_180036B53
0x180036cf9  mov     edx, 28h ; '('
0x180036cfe  jmp     loc_180036C02
0x180036d03  mov     rdx, [rbp+pszPath]; pszPath
0x180036d07  test    rdx, rdx
0x180036d0a  jnz     short loc_180036D3D
0x180036d0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d13  cmp     rcx, rdi
0x180036d16  jz      short loc_180036D36
0x180036d18  test    [rcx+1Ch], sil
0x180036d1c  jz      short loc_180036D36
0x180036d1e  mov     rcx, [rcx+10h]
0x180036d22  mov     edx, 42h ; 'B'
0x180036d27  mov     r8, r14
0x180036d2a  call    WPP_SF_
0x180036d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d36  mov     ebx, 80070057h
0x180036d3b  jmp     short loc_180036D82
0x180036d3d  xor     r8d, r8d; psa
0x180036d40  xor     ecx, ecx; hwnd
0x180036d42  call    cs:__imp_SHCreateDirectoryExW
0x180036d48  test    eax, eax
0x180036d4a  jz      short loc_180036DA0
0x180036d4c  cmp     eax, 0B7h
0x180036d51  jz      short loc_180036DA0
0x180036d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d5a  cmp     rcx, rdi
0x180036d5d  jz      short loc_180036D7D
0x180036d5f  test    [rcx+1Ch], sil
0x180036d63  jz      short loc_180036D7D
0x180036d65  mov     rcx, [rcx+10h]
0x180036d69  mov     edx, 43h ; 'C'
0x180036d6e  mov     r8, r14
0x180036d71  call    WPP_SF_
0x180036d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d7d  mov     ebx, 80004005h
0x180036d82  cmp     rcx, rdi
0x180036d85  jz      short loc_180036DA3
0x180036d87  test    [rcx+1Ch], sil
0x180036d8b  jz      short loc_180036DA3
0x180036d8d  mov     rcx, [rcx+10h]
0x180036d91  mov     edx, 29h ; ')'
0x180036d96  mov     r8, r14
0x180036d99  call    WPP_SF_
0x180036d9e  jmp     short loc_180036DA3
0x180036da0  mov     ebx, r13d
0x180036da3  test    r15, r15
0x180036da6  jz      short loc_180036DB0
0x180036da8  mov     rcx, r15; void *
0x180036dab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036db0  mov     rcx, [rbp+pszPath]; void *
0x180036db4  test    rcx, rcx
0x180036db7  jz      short loc_180036DBE
0x180036db9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036dbe  mov     rcx, [rbp+hKey]; hKey
0x180036dc2  test    rcx, rcx
0x180036dc5  jz      short loc_180036DCD
0x180036dc7  call    cs:__imp_RegCloseKey
0x180036dcd  mov     eax, ebx
0x180036dcf  mov     rbx, [rsp+60h+arg_0]
0x180036dd7  add     rsp, 60h
0x180036ddb  pop     r15
0x180036ddd  pop     r14
0x180036ddf  pop     r13
0x180036de1  pop     r12
0x180036de3  pop     rdi
0x180036de4  pop     rsi
0x180036de5  pop     rbp
0x180036de6  retn
```
