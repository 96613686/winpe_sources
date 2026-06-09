# CLocalDumpGenerator::Initialize(void *,ulong)

- ea: `0x18001a3a4`
- end: `0x18001a9ed`
- name: `?Initialize@CLocalDumpGenerator@@QEAAXPEAXK@Z`
- size: `1609`
- prototype: `void __fastcall(CLocalDumpGenerator *__hidden this, HANDLE hProcess, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ff8c`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000aac8`
- `0x18001a3a4`
- `0x18001a9f4`
- `0x18001aad8`
- `0x18001b5b4`
- `0x18002769c`
- `0x180038c0c`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001a407`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18001a407`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001a5f1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001a5f1`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001a64f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001a790`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001a64f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001a790`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001a58c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001a58c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a5b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a69c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a5b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a69c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CLocalDumpGenerator::Initialize(CLocalDumpGenerator *this, HANDLE hProcess, char a3)
{
  unsigned __int16 *v6; // rbx
  unsigned __int64 v7; // r12
  unsigned __int16 *v8; // rdx
  __int64 v9; // rax
  unsigned __int16 *v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // r8
  const wchar_t *v13; // r15
  _DWORD *v14; // r14
  const wchar_t *v15; // r13
  int SettingsFromSubKey; // ebx
  _BOOL8 v17; // r9
  _BYTE *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  int v21; // ebx
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  int ActivationFactory; // eax
  int v26; // edx
  unsigned int v27; // r8d
  _QWORD *v28; // rcx
  _QWORD *v29; // r15
  __int64 v30; // r13
  HRESULT v31; // eax
  int v32; // edx
  unsigned int v33; // r8d
  int v34; // eax
  _QWORD *v35; // rcx
  _QWORD *v36; // rcx
  _QWORD *v37; // rcx
  int v38; // eax
  int v39; // r8d
  unsigned int v40; // esi
  int ProtectedProcessInfo; // eax
  unsigned int v42; // ebx
  int v43; // r14d
  _QWORD *v44; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v45; // [rsp+38h] [rbp-41h] BYREF
  int v46; // [rsp+3Ch] [rbp-3Dh] BYREF
  PCWSTR sourceString; // [rsp+40h] [rbp-39h]
  const WCHAR *v48; // [rsp+48h] [rbp-31h]
  _WORD v49[8]; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwSize; // [rsp+60h] [rbp-19h] BYREF
  void *v51; // [rsp+68h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF

  v51 = hProcess;
  *((_DWORD *)this + 164) &= ~1u;
  v6 = (unsigned __int16 *)((char *)this + 104);
  *((_WORD *)this + 52) = 0;
  *((_QWORD *)this + 78) = 0;
  dwSize = 260;
  v7 = -1;
  if ( QueryFullProcessImageNameW(hProcess, 0, (LPWSTR)this + 52, &dwSize) )
  {
    if ( v6 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v6[v9] );
      v10 = &v6[v9];
      while ( 1 )
      {
        v8 = v10;
        if ( v10 <= v6 )
          break;
        v11 = *--v10;
        LOWORD(v11) = v11 - 47;
        if ( (unsigned __int16)v11 <= 0x2Du )
        {
          v12 = 0x200000000801LL;
          if ( _bittest64(&v12, v11) )
            break;
        }
      }
    }
    else
    {
      v8 = 0;
    }
    *((_QWORD *)this + 78) = v8;
  }
  sourceString = v49;
  v48 = v49;
  v49[0] = 0;
  v13 = 0;
  if ( (int)PackageUtility::GetProcessPackageFullName(hProcess) >= 0 )
    v13 = sourceString;
  v14 = (_DWORD *)((char *)this + 40);
  v15 = (const wchar_t *)*((_QWORD *)this + 78);
  if ( (int)UtilExpandEnvironmentStrings(L"%LOCALAPPDATA%\\CrashDumps") < 0 )
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      (char *)this + 48,
      L"%LOCALAPPDATA%\\CrashDumps",
      25);
  *((_DWORD *)this + 20) = 10;
  *((_DWORD *)this + 21) = 1;
  *((_DWORD *)this + 22) = 289;
  SettingsFromSubKey = CLocalDumpSettings::LoadSettingsFromSubKey((CLocalDumpGenerator *)((char *)this + 40), 0);
  if ( v15 )
    CLocalDumpSettings::LoadSettingsFromSubKey((CLocalDumpGenerator *)((char *)this + 40), v15);
  if ( v13 )
    CLocalDumpSettings::LoadSettingsFromSubKey((CLocalDumpGenerator *)((char *)this + 40), v13);
  v17 = SettingsFromSubKey >= 0;
  *v14 = v17;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_bb2f0e3f91823ea90d6fa399a905fc71_Traceguids, v17);
    v18 = WPP_GLOBAL_Control;
  }
  if ( SettingsFromSubKey < 0 )
  {
    if ( v18 == (_BYTE *)&WPP_GLOBAL_Control || (v18[28] & 1) == 0 )
      goto LABEL_94;
    v19 = 10;
    v20 = (unsigned int)SettingsFromSubKey;
    goto LABEL_93;
  }
  if ( *((_DWORD *)this + 24) && sourceString != v48 )
  {
    v21 = RoInitialize(1);
    v46 = v21;
    v44 = 0;
    v45 = 0;
    string = 0;
    v22 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v44);
    if ( ActivationFactory < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
          (unsigned int)ActivationFactory);
      v28 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
      }
LABEL_35:
      if ( v21 >= 0 )
        RoUninitialize();
      goto LABEL_94;
    }
    v29 = v44;
    v30 = *v44;
    string = 0;
    do
      ++v7;
    while ( sourceString[v7] );
    if ( v7 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v26, v27);
      __debugbreak();
    }
    if ( (int)v7 + 1 < (unsigned int)v7 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v26, v27);
      JUMPOUT(0x18001A9ECLL);
    }
    v31 = WindowsCreateStringReference(sourceString, v7, &hstringHeader, &string);
    if ( v31 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v31, v32, v33);
      __debugbreak();
    }
    v34 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, unsigned int *))(v30 + 288))(v29, string, &v45);
    if ( v34 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
          (unsigned int)v34);
      v35 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v35 + 16LL))(v35);
      }
      goto LABEL_35;
    }
    if ( v45 - 4 > 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
      v36 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
      }
      goto LABEL_35;
    }
    v37 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
    }
    if ( v21 >= 0 )
      RoUninitialize();
  }
  if ( !*v14
    || *((_QWORD *)this + 6) == *((_QWORD *)this + 7)
    || !*((_DWORD *)this + 20)
    || (v38 = 1, *((_DWORD *)this + 21) > 2u) )
  {
    v38 = 0;
  }
  *((_DWORD *)this + 164) &= ~1u;
  *((_DWORD *)this + 164) |= v38;
  if ( v38 )
  {
    v39 = a3 & 2;
    v40 = (v39 != 0 ? 4 : 0) | (*((_DWORD *)this + 164) & 0xFFFFFFF7 ^ (8 * (a3 & 1))) & 0xFFFFFFFB;
    *((_DWORD *)this + 164) = v40;
    if ( !v39 )
    {
      v45 = 0;
      v46 = 0;
      ProtectedProcessInfo = UtilGetProtectedProcessInfo(
                               v51,
                               (enum _PS_PROTECTED_TYPE *)&v45,
                               (enum _PS_PROTECTED_SIGNER *)&v46);
      if ( ProtectedProcessInfo < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
            (unsigned int)ProtectedProcessInfo);
        goto LABEL_74;
      }
      v42 = v45;
      v43 = v46;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids, v45, v46);
      *((_DWORD *)this + 164) &= ~4u;
      v40 = *((_DWORD *)this + 164);
      if ( v42 == 2 )
      {
        v40 |= 4u;
      }
      else
      {
        if ( v42 != 1 )
          goto LABEL_85;
        v40 |= 4u;
        *((_DWORD *)this + 164) = v40;
        if ( v43 != 8 && v43 != 3 )
          goto LABEL_85;
        v40 &= ~4u;
      }
      *((_DWORD *)this + 164) = v40;
    }
LABEL_85:
    if ( (v40 & 4) == 0 || (int)CLocalDumpGenerator::InitializeDumpEncryptor(this) >= 0 )
    {
      *((_DWORD *)this + 164) |= 1u;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_94;
      v20 = (*((_DWORD *)this + 164) >> 2) & 1;
      v19 = 18;
LABEL_93:
      WPP_SF_d(*((_QWORD *)v18 + 2), v19, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids, v20);
      goto LABEL_94;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
LABEL_74:
    *((_DWORD *)this + 164) &= ~1u;
    goto LABEL_94;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
LABEL_94:
  if ( sourceString != v49 )
    operator delete((void *)sourceString, (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x18001a3a4  mov     [rsp-8+arg_10], rbx
0x18001a3a9  push    rbp
0x18001a3aa  push    rsi
0x18001a3ab  push    rdi
0x18001a3ac  push    r12
0x18001a3ae  push    r13
0x18001a3b0  push    r14
0x18001a3b2  push    r15
0x18001a3b4  lea     rbp, [rsp-27h]
0x18001a3b9  sub     rsp, 0A0h
0x18001a3c0  mov     rax, cs:__security_cookie
0x18001a3c7  xor     rax, rsp
0x18001a3ca  mov     [rbp+57h+var_40], rax
0x18001a3ce  mov     esi, r8d
0x18001a3d1  mov     r14, rdx
0x18001a3d4  mov     [rbp+57h+var_68], rdx
0x18001a3d8  mov     rdi, rcx
0x18001a3db  and     dword ptr [rcx+290h], 0FFFFFFFEh
0x18001a3e2  lea     rbx, [rcx+68h]
0x18001a3e6  xor     r13d, r13d
0x18001a3e9  mov     [rbx], r13w
0x18001a3ed  mov     [rcx+270h], r13
0x18001a3f4  mov     [rbp+57h+dwSize], 104h
0x18001a3fb  lea     r9, [rbp+57h+dwSize]; lpdwSize
0x18001a3ff  mov     r8, rbx; lpExeName
0x18001a402  xor     edx, edx; dwFlags
0x18001a404  mov     rcx, r14; hProcess
0x18001a407  call    cs:__imp_QueryFullProcessImageNameW
0x18001a40d  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001a411  test    eax, eax
0x18001a413  jz      short loc_18001A462
0x18001a415  test    rbx, rbx
0x18001a418  jnz     short loc_18001A41F
0x18001a41a  mov     edx, r13d
0x18001a41d  jmp     short loc_18001A45B
0x18001a41f  mov     rax, r12
0x18001a422  inc     rax
0x18001a425  cmp     [rbx+rax*2], r13w
0x18001a42a  jnz     short loc_18001A422
0x18001a42c  lea     rcx, [rbx+rax*2]
0x18001a430  jmp     short loc_18001A453
0x18001a432  sub     rcx, 2
0x18001a436  movzx   eax, word ptr [rcx]
0x18001a439  sub     ax, 2Fh ; '/'
0x18001a43d  cmp     ax, 2Dh ; '-'
0x18001a441  ja      short loc_18001A453
0x18001a443  mov     r8, 200000000801h
0x18001a44d  bt      r8, rax
0x18001a451  jb      short loc_18001A45B
0x18001a453  mov     rdx, rcx
0x18001a456  cmp     rcx, rbx
0x18001a459  ja      short loc_18001A432
0x18001a45b  mov     [rdi+270h], rdx
0x18001a462  lea     rax, [rbp+57h+var_80]
0x18001a466  mov     [rbp+57h+sourceString], rax
0x18001a46a  lea     rax, [rbp+57h+var_80]
0x18001a46e  mov     [rbp+57h+var_88], rax
0x18001a472  mov     [rbp+57h+var_80], r13w
0x18001a477  mov     r15, r13
0x18001a47a  lea     rdx, [rbp+57h+sourceString]
0x18001a47e  mov     rcx, r14; hProcess
0x18001a481  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001a486  test    eax, eax
0x18001a488  cmovns  r15, [rbp+57h+sourceString]
0x18001a48d  lea     r14, [rdi+28h]
0x18001a491  mov     r13, [rdi+270h]
0x18001a498  lea     rdx, [r14+8]
0x18001a49c  lea     rcx, Src; "%LOCALAPPDATA%\\CrashDumps"
0x18001a4a3  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001a4a8  test    eax, eax
0x18001a4aa  jns     short loc_18001A4C2
0x18001a4ac  mov     r8d, 19h
0x18001a4b2  lea     rdx, Src; "%LOCALAPPDATA%\\CrashDumps"
0x18001a4b9  lea     rcx, [r14+8]
0x18001a4bd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18001a4c2  mov     dword ptr [r14+28h], 0Ah
0x18001a4ca  mov     dword ptr [r14+2Ch], 1
0x18001a4d2  mov     dword ptr [r14+30h], 121h
0x18001a4da  xor     edx, edx; wchar_t *
0x18001a4dc  mov     rcx, r14; this
0x18001a4df  call    ?LoadSettingsFromSubKey@CLocalDumpSettings@@AEAAJPEB_W@Z; CLocalDumpSettings::LoadSettingsFromSubKey(wchar_t const *)
0x18001a4e4  mov     ebx, eax
0x18001a4e6  test    r13, r13
0x18001a4e9  jz      short loc_18001A4F6
0x18001a4eb  mov     rdx, r13; wchar_t *
0x18001a4ee  mov     rcx, r14; this
0x18001a4f1  call    ?LoadSettingsFromSubKey@CLocalDumpSettings@@AEAAJPEB_W@Z; CLocalDumpSettings::LoadSettingsFromSubKey(wchar_t const *)
0x18001a4f6  xor     r13d, r13d
0x18001a4f9  test    r15, r15
0x18001a4fc  jz      short loc_18001A509
0x18001a4fe  mov     rdx, r15; wchar_t *
0x18001a501  mov     rcx, r14; this
0x18001a504  call    ?LoadSettingsFromSubKey@CLocalDumpSettings@@AEAAJPEB_W@Z; CLocalDumpSettings::LoadSettingsFromSubKey(wchar_t const *)
0x18001a509  mov     r9d, ebx
0x18001a50c  not     r9d
0x18001a50f  shr     r9d, 1Fh
0x18001a513  mov     [r14], r9d
0x18001a516  lea     r15, WPP_GLOBAL_Control
0x18001a51d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a524  cmp     rcx, r15
0x18001a527  jz      short loc_18001A54B
0x18001a529  test    byte ptr [rcx+1Ch], 8
0x18001a52d  jz      short loc_18001A54B
0x18001a52f  mov     edx, 0Ah
0x18001a534  lea     r8, WPP_bb2f0e3f91823ea90d6fa399a905fc71_Traceguids
0x18001a53b  mov     rcx, [rcx+10h]
0x18001a53f  call    WPP_SF_d
0x18001a544  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a54b  test    ebx, ebx
0x18001a54d  jns     short loc_18001A56F
0x18001a54f  cmp     rcx, r15
0x18001a552  jz      loc_18001A987
0x18001a558  test    byte ptr [rcx+1Ch], 1
0x18001a55c  jz      loc_18001A987
0x18001a562  mov     edx, 0Ah
0x18001a567  mov     r9d, ebx
0x18001a56a  jmp     loc_18001A976
0x18001a56f  cmp     [rdi+60h], r13d
0x18001a573  jz      loc_18001A79D
0x18001a579  mov     rax, [rbp+57h+var_88]
0x18001a57d  cmp     [rbp+57h+sourceString], rax
0x18001a581  jz      loc_18001A79D
0x18001a587  mov     ecx, 1
0x18001a58c  call    cs:__imp_RoInitialize
0x18001a592  mov     ebx, eax
0x18001a594  mov     [rbp+57h+var_94], eax
0x18001a597  mov     [rbp+57h+var_A0], r13
0x18001a59b  mov     [rbp+57h+var_98], r13d
0x18001a59f  mov     [rbp+57h+string], r13
0x18001a5a3  lea     r9, [rbp+57h+string]; string
0x18001a5a7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001a5ab  mov     edx, 28h ; '('; length
0x18001a5b0  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QB_WB; "Windows.Internal.StateRepository.Packag"...
0x18001a5b7  call    cs:__imp_WindowsCreateStringReference
0x18001a5bd  test    eax, eax
0x18001a5bf  js      loc_18001A9D2
0x18001a5c5  mov     r15, [rbp+57h+string]
0x18001a5c9  mov     rcx, [rbp+57h+var_A0]
0x18001a5cd  test    rcx, rcx
0x18001a5d0  jz      short loc_18001A5E3
0x18001a5d2  mov     [rbp+57h+var_A0], r13
0x18001a5d6  mov     rax, [rcx]
0x18001a5d9  mov     rax, [rax+10h]
0x18001a5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e2  nop
0x18001a5e3  lea     r8, [rbp+57h+var_A0]
0x18001a5e7  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18001a5ee  mov     rcx, r15
0x18001a5f1  call    cs:__imp_RoGetActivationFactory
0x18001a5f7  test    eax, eax
0x18001a5f9  jns     short loc_18001A65A
0x18001a5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a602  lea     rdx, WPP_GLOBAL_Control
0x18001a609  cmp     rcx, rdx
0x18001a60c  jz      short loc_18001A62D
0x18001a60e  test    byte ptr [rcx+1Ch], 1
0x18001a612  jz      short loc_18001A62D
0x18001a614  mov     edx, 0Bh
0x18001a619  mov     r9d, eax
0x18001a61c  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x18001a623  mov     rcx, [rcx+10h]
0x18001a627  call    WPP_SF_d
0x18001a62c  nop
0x18001a62d  mov     rcx, [rbp+57h+var_A0]
0x18001a631  test    rcx, rcx
0x18001a634  jz      short loc_18001A647
0x18001a636  mov     [rbp+57h+var_A0], r13
0x18001a63a  mov     rax, [rcx]
0x18001a63d  mov     rax, [rax+10h]
0x18001a641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a646  nop
0x18001a647  test    ebx, ebx
0x18001a649  js      loc_18001A987
0x18001a64f  call    cs:__imp_RoUninitialize
0x18001a655  jmp     loc_18001A987
0x18001a65a  mov     r15, [rbp+57h+var_A0]
0x18001a65e  mov     r13, [r15]
0x18001a661  xor     eax, eax
0x18001a663  mov     [rbp+57h+string], rax
0x18001a667  mov     rcx, [rbp+57h+sourceString]; sourceString
0x18001a66b  inc     r12
0x18001a66e  cmp     [rcx+r12*2], ax
0x18001a673  jnz     short loc_18001A66B
0x18001a675  mov     eax, 0FFFFFFFFh
0x18001a67a  cmp     r12, rax
0x18001a67d  ja      loc_18001A9C7
0x18001a683  lea     eax, [r12+1]
0x18001a688  cmp     eax, r12d
0x18001a68b  jb      loc_18001A9E2
0x18001a691  lea     r9, [rbp+57h+string]; string
0x18001a695  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001a699  mov     edx, r12d; length
0x18001a69c  call    cs:__imp_WindowsCreateStringReference
0x18001a6a2  test    eax, eax
0x18001a6a4  js      loc_18001A9DA
0x18001a6aa  lea     r8, [rbp+57h+var_98]
0x18001a6ae  mov     rdx, [rbp+57h+string]
0x18001a6b2  mov     rcx, r15
0x18001a6b5  mov     rax, [r13+120h]
0x18001a6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c1  nop
0x18001a6c2  xor     r13d, r13d
0x18001a6c5  test    eax, eax
0x18001a6c7  jns     short loc_18001A719
0x18001a6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6d0  lea     rdx, WPP_GLOBAL_Control
0x18001a6d7  cmp     rcx, rdx
0x18001a6da  jz      short loc_18001A6FA
0x18001a6dc  test    byte ptr [rcx+1Ch], 1
0x18001a6e0  jz      short loc_18001A6FA
0x18001a6e2  lea     edx, [r13+0Ch]
0x18001a6e6  mov     r9d, eax
0x18001a6e9  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x18001a6f0  mov     rcx, [rcx+10h]
0x18001a6f4  call    WPP_SF_d
0x18001a6f9  nop
0x18001a6fa  mov     rcx, [rbp+57h+var_A0]
0x18001a6fe  test    rcx, rcx
0x18001a701  jz      short loc_18001A714
0x18001a703  mov     [rbp+57h+var_A0], r13
0x18001a707  mov     rax, [rcx]
0x18001a70a  mov     rax, [rax+10h]
0x18001a70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a713  nop
0x18001a714  jmp     loc_18001A647
0x18001a719  mov     eax, [rbp+57h+var_98]
0x18001a71c  add     eax, 0FFFFFFFCh
0x18001a71f  cmp     eax, 1
0x18001a722  jbe     short loc_18001A772
0x18001a724  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a72b  lea     rdx, WPP_GLOBAL_Control
0x18001a732  cmp     rcx, rdx
0x18001a735  jz      short loc_18001A753
0x18001a737  test    byte ptr [rcx+1Ch], 4
0x18001a73b  jz      short loc_18001A753
0x18001a73d  mov     edx, 0Dh
0x18001a742  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x18001a749  mov     rcx, [rcx+10h]
0x18001a74d  call    WPP_SF_
0x18001a752  nop
0x18001a753  mov     rcx, [rbp+57h+var_A0]
0x18001a757  test    rcx, rcx
0x18001a75a  jz      short loc_18001A76D
0x18001a75c  mov     [rbp+57h+var_A0], r13
0x18001a760  mov     rax, [rcx]
0x18001a763  mov     rax, [rax+10h]
0x18001a767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a76c  nop
0x18001a76d  jmp     loc_18001A647
0x18001a772  mov     rcx, [rbp+57h+var_A0]
0x18001a776  test    rcx, rcx
0x18001a779  jz      short loc_18001A78C
0x18001a77b  mov     [rbp+57h+var_A0], r13
0x18001a77f  mov     rax, [rcx]
0x18001a782  mov     rax, [rax+10h]
0x18001a786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a78b  nop
0x18001a78c  test    ebx, ebx
0x18001a78e  js      short loc_18001A796
0x18001a790  call    cs:__imp_RoUninitialize
0x18001a796  lea     r15, WPP_GLOBAL_Control
0x18001a79d  cmp     [r14], r13d
0x18001a7a0  jz      short loc_18001A7BE
0x18001a7a2  mov     rax, [r14+10h]
0x18001a7a6  cmp     [r14+8], rax
0x18001a7aa  jz      short loc_18001A7BE
0x18001a7ac  cmp     [r14+28h], r13d
0x18001a7b0  jbe     short loc_18001A7BE
0x18001a7b2  cmp     dword ptr [r14+2Ch], 2
0x18001a7b7  mov     eax, 1
0x18001a7bc  jbe     short loc_18001A7C1
0x18001a7be  mov     eax, r13d
0x18001a7c1  and     dword ptr [rdi+290h], 0FFFFFFFEh
0x18001a7c8  or      [rdi+290h], eax
0x18001a7ce  mov     ecx, [rdi+290h]
0x18001a7d4  test    eax, eax
0x18001a7d6  jnz     short loc_18001A80A
0x18001a7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7df  cmp     rcx, r15
0x18001a7e2  jz      loc_18001A987
0x18001a7e8  test    byte ptr [rcx+1Ch], 4
0x18001a7ec  jz      loc_18001A987
0x18001a7f2  lea     edx, [rax+0Eh]
0x18001a7f5  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x18001a7fc  mov     rcx, [rcx+10h]
0x18001a800  call    WPP_SF_
0x18001a805  jmp     loc_18001A987
0x18001a80a  mov     r8d, esi
0x18001a80d  and     r8d, 2
0x18001a811  and     esi, 1
0x18001a814  shl     esi, 3
0x18001a817  and     ecx, 0FFFFFFF7h
0x18001a81a  xor     esi, ecx
0x18001a81c  mov     r12d, 0FFFFFFFBh
0x18001a822  and     esi, r12d
0x18001a825  mov     eax, r8d
0x18001a828  neg     eax
0x18001a82a  sbb     edx, edx
0x18001a82c  and     edx, 4
0x18001a82f  or      esi, edx
  ... truncated ...
```
