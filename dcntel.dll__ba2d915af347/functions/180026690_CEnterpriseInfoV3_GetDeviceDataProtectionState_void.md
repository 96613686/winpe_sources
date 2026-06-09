# CEnterpriseInfoV3::GetDeviceDataProtectionState(void)

- ea: `0x180026690`
- end: `0x1800270c9`
- name: `?GetDeviceDataProtectionState@CEnterpriseInfoV3@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `2617`
- prototype: `__int64 *__fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18001286c`
- `0x180014f2c`
- `0x180016748`
- `0x180016db0`
- `0x180019324`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800220b4`
- `0x180026690`
- `0x1800270d0`
- `0x180027b4c`
- `0x180027cd8`
- `0x180028920`
- `0x180029e50`
- `0x18002b344`
- `0x18002b3e4`
- `0x18002b470`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800267ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800267ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026816`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002684a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026864`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002687e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026898`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800268b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800268cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800268e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026903`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002691d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026816`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026830`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002684a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026864`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002687e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026898`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800268b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800268cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800268e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180026903`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002691d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270af`

## string_xrefs

- `0x1800267e5`: `Fveapi.DLL`
- `0x1800268c3`: `FveOpenVolumeByHandle`

## pseudocode

```c
__int64 *__fastcall CEnterpriseInfoV3::GetDeviceDataProtectionState(__int64 a1, __int64 *a2)
{
  __int64 *v2; // rsi
  int v3; // r15d
  unsigned int v4; // ebx
  unsigned int v5; // r13d
  HMODULE Library; // rax
  FARPROC v7; // r14
  FARPROC v8; // rax
  int v9; // r14d
  int (__fastcall *v10)(_QWORD, _QWORD); // rsi
  int (__fastcall *v11)(void *); // r15
  __int64 ProtectionInfo; // rax
  __int64 FveOSMethodInfoForEdrive; // rax
  int v14; // r14d
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 *v18; // r9
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 *v22; // r9
  int v23; // r15d
  __int64 v24; // rax
  __int64 DeviceDataProtectionStateForWin7; // rax
  signed int LastError; // eax
  int v28; // edx
  unsigned int v29; // r8d
  char v30; // [rsp+40h] [rbp-4A8h]
  unsigned int v31; // [rsp+44h] [rbp-4A4h] BYREF
  int v32; // [rsp+48h] [rbp-4A0h]
  void *v33; // [rsp+50h] [rbp-498h] BYREF
  int v34; // [rsp+58h] [rbp-490h]
  unsigned int v35; // [rsp+5Ch] [rbp-48Ch] BYREF
  unsigned int v36; // [rsp+60h] [rbp-488h] BYREF
  const int *v37; // [rsp+68h] [rbp-480h] BYREF
  HMODULE hModule; // [rsp+70h] [rbp-478h]
  unsigned __int64 v39; // [rsp+78h] [rbp-470h] BYREF
  __int64 v40; // [rsp+80h] [rbp-468h] BYREF
  int v41; // [rsp+88h] [rbp-460h] BYREF
  _QWORD *v42; // [rsp+90h] [rbp-458h]
  _QWORD *v43; // [rsp+98h] [rbp-450h]
  __int64 *v44; // [rsp+A0h] [rbp-448h]
  _BYTE v45[8]; // [rsp+B0h] [rbp-438h] BYREF
  void (*ProcAddress)(void); // [rsp+B8h] [rbp-430h]
  FARPROC v47; // [rsp+C0h] [rbp-428h]
  FARPROC v48; // [rsp+C8h] [rbp-420h]
  FARPROC v49; // [rsp+D0h] [rbp-418h]
  FARPROC v50; // [rsp+D8h] [rbp-410h]
  FARPROC v51; // [rsp+E0h] [rbp-408h]
  FARPROC v52; // [rsp+E8h] [rbp-400h]
  FARPROC v53; // [rsp+F0h] [rbp-3F8h]
  void (*v54)(void); // [rsp+F8h] [rbp-3F0h]
  FARPROC v55; // [rsp+110h] [rbp-3D8h]
  FARPROC v56; // [rsp+118h] [rbp-3D0h]
  __int64 *v57; // [rsp+120h] [rbp-3C8h]
  _QWORD *v58; // [rsp+128h] [rbp-3C0h]
  _QWORD *v59; // [rsp+130h] [rbp-3B8h]
  _BYTE Src[32]; // [rsp+138h] [rbp-3B0h] BYREF
  _OWORD v61[2]; // [rsp+158h] [rbp-390h] BYREF
  __int128 v62; // [rsp+178h] [rbp-370h] BYREF
  __int128 v63; // [rsp+188h] [rbp-360h]
  _OWORD v64[2]; // [rsp+198h] [rbp-350h] BYREF
  _DWORD v65[14]; // [rsp+1C0h] [rbp-328h] BYREF
  __int64 v66; // [rsp+1F8h] [rbp-2F0h]
  _DWORD v67[2]; // [rsp+200h] [rbp-2E8h] BYREF
  _BYTE v68[74]; // [rsp+208h] [rbp-2E0h] BYREF
  char v69; // [rsp+252h] [rbp-296h]
  unsigned __int16 v70[24]; // [rsp+280h] [rbp-268h] BYREF
  _BYTE v71[512]; // [rsp+2B0h] [rbp-238h] BYREF

  v2 = a2;
  v57 = a2;
  v44 = a2;
  v39 = 0;
  v33 = (void *)-1LL;
  v40 = -1;
  memset(v61, 0, sizeof(v61));
  memset_0(v65, 0, 0x40u);
  memset_0(v67, 0, 0x80u);
  *(_OWORD *)v2 = 0;
  v42 = v2 + 2;
  v2[2] = 0;
  v43 = v2 + 3;
  v2[3] = 0;
  std::wstring::_Construct<1,unsigned short const *>(v2, L"DEVICE_PROTECTION_UNKNOWN", 25);
  v3 = 1;
  v32 = 1;
  v4 = 0;
  v31 = 0;
  memset_0(v45, 0, 0x70u);
  v35 = -1;
  v41 = 0;
  memset_0(v71, 0, sizeof(v71));
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,unsigned short const *>(v64, &word_1801B4598, 0);
  v5 = 0;
  v36 = 0;
  Library = LoadLibraryExW(L"Fveapi.DLL", 0, 0x800u);
  v37 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( !Library )
    goto LABEL_90;
  ProcAddress = (void (*)(void))GetProcAddress(Library, "FveCloseVolume");
  v47 = GetProcAddress(hModule, "FveGetStatus");
  v49 = GetProcAddress(hModule, "FveGetFveMethod");
  v50 = GetProcAddress(hModule, "FveGetFveMethodEx");
  v52 = GetProcAddress(hModule, "FveFindFirstVolume");
  v53 = GetProcAddress(hModule, "FveFindNextVolume");
  v7 = GetProcAddress(hModule, "FveCloseHandle");
  v54 = (void (*)(void))v7;
  v51 = GetProcAddress(hModule, "FveOpenVolumeByHandle");
  v48 = GetProcAddress(hModule, "FveIsVolumeEncryptable");
  v55 = GetProcAddress(hModule, "FveGetAuthMethodGuids");
  v8 = GetProcAddress(hModule, "FveGetAuthMethodInformation");
  v56 = v8;
  if ( !v52 )
    goto LABEL_90;
  if ( v53 && ProcAddress && v51 && v47 && v48 && v7 && v55 && v8 && v49 )
  {
    v59 = v2 + 2;
    v58 = v2 + 3;
    LOBYTE(v9) = 0;
    v30 = 0;
    v39 = 0xFFFFFFFF00000001uLL;
    if ( ((int (__fastcall *)(__int64 *, unsigned __int64 *))v52)(&v40, &v39) >= 0 )
    {
      v10 = (int (__fastcall *)(_QWORD, _QWORD))v47;
      v11 = (int (__fastcall *)(void *))v48;
      while ( 1 )
      {
        if ( v33 != (void *)-1LL )
        {
          ProcAddress();
          v33 = (void *)-1LL;
        }
        memset((char *)v61 + 8, 0, 24);
        *(_QWORD *)&v61[0] = 0x100000020LL;
        if ( ((int (__fastcall *)(__int64, _QWORD, _QWORD, __int64, _DWORD, void **))v51)(
               v40,
               0,
               0,
               0xFFFFFFFFLL,
               0,
               &v33) < 0
          || v10(v33, v61) < 0 )
        {
          v4 |= 2u;
          goto LABEL_18;
        }
        v9 = (unsigned __int8)v9;
        if ( (WORD4(v61[0]) & 0x4000) != 0 )
          v9 = 1;
        v34 = v9;
        if ( (DWORD2(v61[0]) & 0x400000) != 0 || v11(v33) < 0 && (WORD4(v61[0]) & 0x4000) == 0 )
          goto LABEL_19;
        if ( (WORD4(v61[0]) & 0x4000) != 0 && (BYTE8(v61[0]) & 4) == 0 )
        {
          GetTPMPcrProfile((struct _FVEAPI_LIB_FN *)v45, v33, &v31, &v36);
          if ( v50 )
            ((void (__fastcall *)(void *, unsigned int *, _BYTE *, int *))v50)(v33, &v35, v71, &v41);
          else
            ((void (__fastcall *)(void *, unsigned int *))v49)(v33, &v35);
          v30 = 1;
          v4 = v31;
          v10 = (int (__fastcall *)(_QWORD, _QWORD))v47;
          v11 = (int (__fastcall *)(void *))v48;
        }
        memset_0(v65, 0, 0x40u);
        v65[0] = 64;
        v65[1] = 4;
        v14 = v10(v33, v65);
        if ( v14 >= 0 )
        {
          if ( (v66 & 0x400) != 0 )
            v4 |= 0x2000u;
          if ( (v66 & 0x800) != 0 )
            v4 |= 0x4000u;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::GetImpl'::`2'::impl) )
        {
          memset_0(v68, 0, 0x78u);
          v67[0] = 128;
          v67[1] = 9;
          v14 = v10(v33, v67);
          if ( v14 >= 0 )
          {
            if ( (v69 & 0x20) != 0 )
              v4 |= 0x8000u;
            if ( (v69 & 4) != 0 )
              v4 |= 0x10000u;
            if ( (v69 & 0x40) != 0 )
              v4 |= 0x20000u;
            if ( (v69 & 8) != 0 )
              v4 |= 0x40000u;
            if ( v69 < 0 )
              v4 |= 0x80000u;
            if ( (v69 & 0x10) != 0 )
              v4 |= 0x100000u;
          }
        }
        if ( (DWORD2(v61[0]) & 0x2000414) == 0 )
        {
          if ( (BYTE8(v61[0]) & 0x20) != 0 && (v14 < 0 || (v66 & 1) == 0) )
          {
            v4 |= 0x24u;
          }
          else if ( (WORD4(v61[0]) & 0x4000) != 0 )
          {
            v4 |= 8u;
          }
          else
          {
            v4 |= 0x200u;
          }
          goto LABEL_74;
        }
        if ( (DWORD2(v61[0]) & 0x2000400) != 0 )
        {
          if ( (WORD4(v61[0]) & 0x4000) == 0 )
            goto LABEL_65;
          if ( (BYTE8(v61[0]) & 0x10) == 0 )
          {
            v4 |= 0x10u;
            if ( (DWORD2(v61[0]) & 0x2000000) != 0 )
              v4 |= 0x800u;
          }
        }
        if ( (WORD4(v61[0]) & 0x4000) == 0 )
LABEL_65:
          v4 |= 0x400u;
        v4 |= 4u;
LABEL_74:
        v31 = v4;
        LOBYTE(v9) = v34;
        if ( (DWORD2(v61[0]) & 0x8000000) == 0 )
          goto LABEL_19;
        v4 |= 0x40u;
        v31 = v4;
        if ( (WORD4(v61[0]) & 0x4000) == 0 )
          goto LABEL_19;
        v4 |= 0x1000u;
LABEL_18:
        v31 = v4;
LABEL_19:
        if ( ((int (__fastcall *)(__int64, unsigned __int64 *))v53)(v40, &v39) < 0 )
        {
          v5 = v36;
          v2 = v57;
          v3 = v32;
          break;
        }
      }
    }
    if ( (v4 & 2) != 0 && (_BYTE)v9 )
      v4 |= 0x400u;
    try
    {
      ProtectionInfo = CEnterpriseInfoV3::GetProtectionInfo(Src, v4);
      std::wstring::operator=(v2, ProtectionInfo);
      std::wstring::~wstring(Src);
      if ( v30 )
      {
        if ( (v4 & 0x1000) != 0 )
          FveOSMethodInfoForEdrive = EnterpriseInfo::GetFveOSMethodInfoForEdrive(Src, v71);
        else
          FveOSMethodInfoForEdrive = EnterpriseInfo::GetFveOSMethodInfo(Src, v35);
        std::wstring::operator=(v64, FveOSMethodInfoForEdrive);
        std::wstring::~wstring(Src);
        v17 = v2[2];
        if ( 0x7FFFFFFFFFFFFFFELL == v17 )
          std::_Xlen_string();
        if ( (unsigned __int64)v2[3] <= 7 )
          v18 = v2;
        else
          v18 = (__int64 *)*v2;
        std::wstring::wstring(Src, v15, v16, v18, v17, L"|", 1);
        v32 = 3;
        v19 = std::wstring::append(Src);
        v62 = *(_OWORD *)v19;
        v63 = *(_OWORD *)(v19 + 16);
        *(_QWORD *)(v19 + 16) = 0;
        *(_QWORD *)(v19 + 24) = 7;
        *(_WORD *)v19 = 0;
        v3 = 7;
        v32 = 7;
        std::wstring::operator=(v2, &v62);
        std::wstring::~wstring(&v62);
        std::wstring::~wstring(Src);
      }
    }
    catch ( ... )
    {
      v5 = v36;
      v3 = v32;
      v2 = v44;
      v43 = v58;
      v42 = v59;
    }
    try
    {
      if ( v5 )
      {
        v70[0] = 0;
        if ( (int)StringCchPrintfW(v70, 0x14u, L"PCR_%03x", v5) >= 0 )
        {
          if ( 0x7FFFFFFFFFFFFFFELL == *v42 )
            std::_Xlen_string();
          if ( *v43 <= 7u )
            v22 = v2;
          else
            v22 = (__int64 *)*v2;
          std::wstring::wstring(Src, v20, v21, v22, *v42, L"|", 1);
          v23 = v3 | 8;
          v32 = v23;
          v24 = std::wstring::append(Src, v70);
          v62 = *(_OWORD *)v24;
          v63 = *(_OWORD *)(v24 + 16);
          *(_QWORD *)(v24 + 16) = 0;
          *(_QWORD *)(v24 + 24) = 7;
          *(_WORD *)v24 = 0;
          v32 = v23 | 0x10;
          std::wstring::operator=(v2, &v62);
          std::wstring::~wstring(&v62);
          std::wstring::~wstring(Src);
        }
      }
    }
    catch ( ... )
    {
      v2 = v44;
    }
  }
  else
  {
LABEL_90:
    DeviceDataProtectionStateForWin7 = EnterpriseInfo::GetDeviceDataProtectionStateForWin7(Src);
    std::wstring::operator=(v2, DeviceDataProtectionStateForWin7);
    std::wstring::~wstring(Src);
  }
  if ( v33 != (void *)-1LL && ProcAddress )
    ProcAddress();
  if ( v40 != -1 && v54 )
    v54();
  v37 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v37) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v28, v29);
      JUMPOUT(0x1800270C8LL);
    }
    hModule = 0;
  }
  std::wstring::~wstring(v64);
  return v2;
}

```

## disassembly

```asm
0x180026690  mov     r11, rsp
0x180026693  mov     [r11+8], rbx
0x180026697  mov     [r11+18h], rsi
0x18002669b  push    rdi
0x18002669c  push    r12
0x18002669e  push    r13
0x1800266a0  push    r14
0x1800266a2  push    r15
0x1800266a4  sub     rsp, 4C0h
0x1800266ab  mov     rax, cs:__security_cookie
0x1800266b2  xor     rax, rsp
0x1800266b5  mov     [rsp+4E8h+var_38], rax
0x1800266bd  mov     rsi, rdx
0x1800266c0  mov     [r11-3C8h], rdx
0x1800266c7  mov     [r11-448h], rdx
0x1800266ce  xor     edi, edi
0x1800266d0  mov     [rsp+4E8h+var_4A0], edi
0x1800266d4  mov     [rsp+4E8h+var_470], rdi
0x1800266d9  mov     [rsp+4E8h+var_498], 0FFFFFFFFFFFFFFFFh
0x1800266e2  mov     qword ptr [r11-468h], 0FFFFFFFFFFFFFFFFh
0x1800266ed  xorps   xmm0, xmm0
0x1800266f0  movups  [rsp+4E8h+var_390], xmm0
0x1800266f8  movups  [rsp+4E8h+var_380], xmm0
0x180026700  xor     edx, edx; Val
0x180026702  lea     r8d, [rdi+40h]; Size
0x180026706  lea     rcx, [r11-328h]; void *
0x18002670d  call    memset_0
0x180026712  xor     edx, edx; Val
0x180026714  mov     r8d, 80h; Size
0x18002671a  lea     rcx, [rsp+4E8h+var_2E8]; void *
0x180026722  call    memset_0
0x180026727  xorps   xmm0, xmm0
0x18002672a  movups  xmmword ptr [rsi], xmm0
0x18002672d  lea     rax, [rsi+10h]
0x180026731  mov     [rsp+4E8h+var_458], rax
0x180026739  mov     [rax], rdi
0x18002673c  lea     rax, [rsi+18h]
0x180026740  mov     [rsp+4E8h+var_450], rax
0x180026748  mov     [rax], rdi
0x18002674b  lea     r8d, [rdi+19h]
0x18002674f  lea     rdx, aDeviceProtecti; "DEVICE_PROTECTION_UNKNOWN"
0x180026756  mov     rcx, rsi
0x180026759  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002675e  lea     r12d, [rdi+1]
0x180026762  mov     r15d, r12d
0x180026765  mov     [rsp+4E8h+var_4A0], r12d
0x18002676a  mov     ebx, edi
0x18002676c  mov     [rsp+4E8h+var_4A4], ebx
0x180026770  xor     edx, edx; Val
0x180026772  lea     r8d, [rdi+70h]; Size
0x180026776  lea     rcx, [rsp+4E8h+var_438]; void *
0x18002677e  call    memset_0
0x180026783  mov     [rsp+4E8h+var_48C], 0FFFFFFFFh
0x18002678b  mov     [rsp+4E8h+var_460], edi
0x180026792  xor     edx, edx; Val
0x180026794  mov     r8d, 200h; Size
0x18002679a  lea     rcx, [rsp+4E8h+var_238]; void *
0x1800267a2  call    memset_0
0x1800267a7  xorps   xmm0, xmm0
0x1800267aa  movups  [rsp+4E8h+var_350], xmm0
0x1800267b2  xorps   xmm1, xmm1
0x1800267b5  movdqu  [rsp+4E8h+var_340], xmm1
0x1800267be  xor     r8d, r8d
0x1800267c1  lea     rdx, word_1801B4598
0x1800267c8  lea     rcx, [rsp+4E8h+var_350]
0x1800267d0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800267d5  nop
0x1800267d6  mov     r13d, edi
0x1800267d9  mov     [rsp+4E8h+var_488], edi
0x1800267dd  xor     edx, edx; hFile
0x1800267df  mov     r8d, 800h; dwFlags
0x1800267e5  lea     rcx, aFveapiDll_0; "Fveapi.DLL"
0x1800267ec  call    cs:__imp_LoadLibraryExW
0x1800267f2  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800267f9  mov     [rsp+4E8h+var_480], r14
0x1800267fe  mov     [rsp+4E8h+hModule], rax
0x180026803  test    rax, rax
0x180026806  jz      loc_180026FDA
0x18002680c  lea     rdx, aFveclosevolume_0; "FveCloseVolume"
0x180026813  mov     rcx, rax; hModule
0x180026816  call    cs:__imp_GetProcAddress
0x18002681c  mov     [rsp+4E8h+var_430], rax
0x180026824  lea     rdx, aFvegetstatus_0; "FveGetStatus"
0x18002682b  mov     rcx, [rsp+4E8h+hModule]; hModule
0x180026830  call    cs:__imp_GetProcAddress
0x180026836  mov     [rsp+4E8h+var_428], rax
0x18002683e  lea     rdx, aFvegetfvemetho_0; "FveGetFveMethod"
0x180026845  mov     rcx, [rsp+4E8h+hModule]; hModule
0x18002684a  call    cs:__imp_GetProcAddress
0x180026850  mov     [rsp+4E8h+var_418], rax
0x180026858  lea     rdx, aFvegetfvemetho; "FveGetFveMethodEx"
0x18002685f  mov     rcx, [rsp+4E8h+hModule]; hModule
0x180026864  call    cs:__imp_GetProcAddress
0x18002686a  mov     [rsp+4E8h+var_410], rax
0x180026872  lea     rdx, aFvefindfirstvo; "FveFindFirstVolume"
0x180026879  mov     rcx, [rsp+4E8h+hModule]; hModule
0x18002687e  call    cs:__imp_GetProcAddress
0x180026884  mov     [rsp+4E8h+var_400], rax
0x18002688c  lea     rdx, aFvefindnextvol; "FveFindNextVolume"
0x180026893  mov     rcx, [rsp+4E8h+hModule]; hModule
0x180026898  call    cs:__imp_GetProcAddress
0x18002689e  mov     [rsp+4E8h+var_3F8], rax
0x1800268a6  lea     rdx, aFveclosehandle; "FveCloseHandle"
0x1800268ad  mov     rcx, [rsp+4E8h+hModule]; hModule
0x1800268b2  call    cs:__imp_GetProcAddress
0x1800268b8  mov     r14, rax
0x1800268bb  mov     [rsp+4E8h+var_3F0], rax
0x1800268c3  lea     rdx, aFveopenvolumeb; "FveOpenVolumeByHandle"
0x1800268ca  mov     rcx, [rsp+4E8h+hModule]; hModule
0x1800268cf  call    cs:__imp_GetProcAddress
0x1800268d5  mov     [rsp+4E8h+var_408], rax
0x1800268dd  lea     rdx, aFveisvolumeenc; "FveIsVolumeEncryptable"
0x1800268e4  mov     rcx, [rsp+4E8h+hModule]; hModule
0x1800268e9  call    cs:__imp_GetProcAddress
0x1800268ef  mov     [rsp+4E8h+var_420], rax
0x1800268f7  lea     rdx, aFvegetauthmeth_0; "FveGetAuthMethodGuids"
0x1800268fe  mov     rcx, [rsp+4E8h+hModule]; hModule
0x180026903  call    cs:__imp_GetProcAddress
0x180026909  mov     [rsp+4E8h+var_3D8], rax
0x180026911  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x180026918  mov     rcx, [rsp+4E8h+hModule]; hModule
0x18002691d  call    cs:__imp_GetProcAddress
0x180026923  mov     [rsp+4E8h+var_3D0], rax
0x18002692b  mov     r8, [rsp+4E8h+var_400]
0x180026933  test    r8, r8
0x180026936  jz      loc_180026FDA
0x18002693c  cmp     [rsp+4E8h+var_3F8], rdi
0x180026944  jz      loc_180026FDA
0x18002694a  cmp     [rsp+4E8h+var_430], rdi
0x180026952  jz      loc_180026FDA
0x180026958  cmp     [rsp+4E8h+var_408], rdi
0x180026960  jz      loc_180026FDA
0x180026966  cmp     [rsp+4E8h+var_428], rdi
0x18002696e  jz      loc_180026FDA
0x180026974  cmp     [rsp+4E8h+var_420], rdi
0x18002697c  jz      loc_180026FDA
0x180026982  test    r14, r14
0x180026985  jz      loc_180026FDA
0x18002698b  cmp     [rsp+4E8h+var_3D8], rdi
0x180026993  jz      loc_180026FDA
0x180026999  test    rax, rax
0x18002699c  jz      loc_180026FDA
0x1800269a2  cmp     [rsp+4E8h+var_418], rdi
0x1800269aa  jz      loc_180026FDA
0x1800269b0  lea     rax, [rsi+10h]
0x1800269b4  mov     [rsp+4E8h+var_3B8], rax
0x1800269bc  lea     rax, [rsi+18h]
0x1800269c0  mov     [rsp+4E8h+var_3C0], rax
0x1800269c8  mov     r14b, dil
0x1800269cb  mov     [rsp+4E8h+var_4A8], dil
0x1800269d0  mov     dword ptr [rsp+4E8h+var_470], r12d
0x1800269d5  mov     dword ptr [rsp+4E8h+var_470+4], 0FFFFFFFFh
0x1800269dd  lea     rdx, [rsp+4E8h+var_470]
0x1800269e2  lea     rcx, [rsp+4E8h+var_468]
0x1800269ea  mov     rax, r8
0x1800269ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269f2  test    eax, eax
0x1800269f4  js      loc_180026AC7
0x1800269fa  mov     r13d, 4000h
0x180026a00  mov     rsi, [rsp+4E8h+var_428]
0x180026a08  mov     r15, [rsp+4E8h+var_420]
0x180026a10  mov     rcx, [rsp+4E8h+var_498]
0x180026a15  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026a19  jz      short loc_180026A31
0x180026a1b  mov     rax, [rsp+4E8h+var_430]
0x180026a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a28  mov     [rsp+4E8h+var_498], 0FFFFFFFFFFFFFFFFh
0x180026a31  xorps   xmm0, xmm0
0x180026a34  movdqu  [rsp+4E8h+var_390+8], xmm0
0x180026a3d  mov     qword ptr [rsp+4E8h+var_380+8], rdi
0x180026a45  mov     dword ptr [rsp+4E8h+var_390], 20h ; ' '
0x180026a50  mov     dword ptr [rsp+4E8h+var_390+4], r12d
0x180026a58  lea     rax, [rsp+4E8h+var_498]
0x180026a5d  mov     [rsp+4E8h+var_4C0], rax
0x180026a62  mov     dword ptr [rsp+4E8h+var_4C8], edi
0x180026a66  or      r9d, 0FFFFFFFFh
0x180026a6a  xor     r8d, r8d
0x180026a6d  xor     edx, edx
0x180026a6f  mov     rcx, [rsp+4E8h+var_468]
0x180026a77  mov     rax, [rsp+4E8h+var_408]
0x180026a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a84  test    eax, eax
0x180026a86  jns     loc_180026B27
0x180026a8c  or      ebx, 2
0x180026a8f  mov     [rsp+4E8h+var_4A4], ebx
0x180026a93  lea     rdx, [rsp+4E8h+var_470]
0x180026a98  mov     rcx, [rsp+4E8h+var_468]
0x180026aa0  mov     rax, [rsp+4E8h+var_3F8]
0x180026aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aad  test    eax, eax
0x180026aaf  jns     loc_180026A10
0x180026ab5  mov     r13d, [rsp+4E8h+var_488]
0x180026aba  mov     rsi, [rsp+4E8h+var_3C8]
0x180026ac2  mov     r15d, [rsp+4E8h+var_4A0]
0x180026ac7  test    bl, 2
0x180026aca  jz      short loc_180026AD5
0x180026acc  test    r14b, r14b
0x180026acf  jz      short loc_180026AD5
0x180026ad1  bts     ebx, 0Ah
0x180026ad5  mov     edx, ebx
0x180026ad7  lea     rcx, [rsp+4E8h+Src]
0x180026adf  call    ?GetProtectionInfo@CEnterpriseInfoV3@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; CEnterpriseInfoV3::GetProtectionInfo(ulong)
0x180026ae4  mov     rdx, rax
0x180026ae7  mov     rcx, rsi
0x180026aea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180026aef  lea     rcx, [rsp+4E8h+Src]
0x180026af7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026afc  cmp     [rsp+4E8h+var_4A8], dil
0x180026b01  jz      loc_180026E79
0x180026b07  lea     rcx, [rsp+4E8h+Src]
0x180026b0f  bt      ebx, 0Ch
0x180026b13  jb      loc_180026D85
0x180026b19  mov     edx, [rsp+4E8h+var_48C]
0x180026b1d  call    ?GetFveOSMethodInfo@EnterpriseInfo@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; EnterpriseInfo::GetFveOSMethodInfo(int)
0x180026b22  jmp     loc_180026D92
0x180026b27  lea     rdx, [rsp+4E8h+var_390]
0x180026b2f  mov     rcx, [rsp+4E8h+var_498]
0x180026b34  mov     rax, rsi
0x180026b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b3c  test    eax, eax
0x180026b3e  js      loc_180026A8C
0x180026b44  test    dword ptr [rsp+4E8h+var_390+8], r13d
0x180026b4c  movzx   r14d, r14b
0x180026b50  cmovnz  r14d, r12d
0x180026b54  mov     [rsp+4E8h+var_490], r14d
0x180026b59  test    dword ptr [rsp+4E8h+var_390+8], 400000h
0x180026b64  jnz     loc_180026A93
0x180026b6a  mov     rcx, [rsp+4E8h+var_498]
0x180026b6f  mov     rax, r15
0x180026b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b77  test    eax, eax
0x180026b79  mov     eax, dword ptr [rsp+4E8h+var_390+8]
0x180026b80  jns     short loc_180026B8B
0x180026b82  test    r13d, eax
0x180026b85  jz      loc_180026A93
0x180026b8b  test    r13d, eax
0x180026b8e  jz      short loc_180026C04
0x180026b90  test    al, 4
0x180026b92  jnz     short loc_180026C04
0x180026b94  lea     r9, [rsp+4E8h+var_488]; unsigned int *
0x180026b99  lea     r8, [rsp+4E8h+var_4A4]; unsigned int *
0x180026b9e  mov     rdx, [rsp+4E8h+var_498]; void *
0x180026ba3  lea     rcx, [rsp+4E8h+var_438]; struct _FVEAPI_LIB_FN *
0x180026bab  call    ?GetTPMPcrProfile@@YAXPEAU_FVEAPI_LIB_FN@@PEAXPEAK2@Z; GetTPMPcrProfile(_FVEAPI_LIB_FN *,void *,ulong *,ulong *)
0x180026bb0  mov     rax, [rsp+4E8h+var_410]
0x180026bb8  lea     rdx, [rsp+4E8h+var_48C]
0x180026bbd  mov     rcx, [rsp+4E8h+var_498]
0x180026bc2  test    rax, rax
0x180026bc5  jz      short loc_180026BDE
0x180026bc7  lea     r9, [rsp+4E8h+var_460]
0x180026bcf  lea     r8, [rsp+4E8h+var_238]
0x180026bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bdc  jmp     short loc_180026BEB
0x180026bde  mov     rax, [rsp+4E8h+var_418]
0x180026be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026beb  mov     [rsp+4E8h+var_4A8], r12b
0x180026bf0  mov     ebx, [rsp+4E8h+var_4A4]
0x180026bf4  mov     rsi, [rsp+4E8h+var_428]
0x180026bfc  mov     r15, [rsp+4E8h+var_420]
0x180026c04  mov     r14d, 40h ; '@'
0x180026c0a  mov     r8d, r14d; Size
0x180026c0d  xor     edx, edx; Val
0x180026c0f  lea     rcx, [rsp+4E8h+var_328]; void *
0x180026c17  call    memset_0
0x180026c1c  mov     [rsp+4E8h+var_328], r14d
0x180026c24  mov     [rsp+4E8h+var_324], 4
0x180026c2f  lea     rdx, [rsp+4E8h+var_328]
0x180026c37  mov     rcx, [rsp+4E8h+var_498]
0x180026c3c  mov     rax, rsi
0x180026c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c44  mov     r14d, eax
0x180026c47  test    eax, eax
0x180026c49  js      short loc_180026C6E
0x180026c4b  test    [rsp+4E8h+var_2F0], 400h
0x180026c57  jz      short loc_180026C5D
0x180026c59  bts     ebx, 0Dh
0x180026c5d  test    [rsp+4E8h+var_2F0], 800h
0x180026c69  jz      short loc_180026C6E
0x180026c6b  or      ebx, r13d
0x180026c6e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine> `wil::Feature<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::GetImpl(void)'::`2'::impl
0x180026c75  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SteelixInlineNvmeCryptoEngine>::__private_IsEnabled(void)
0x180026c7a  test    al, al
0x180026c7c  jz      short loc_180026CFA
0x180026c7e  xor     edx, edx; Val
0x180026c80  lea     r8d, [rdx+78h]; Size
0x180026c84  lea     rcx, [rsp+4E8h+var_2E0]; void *
0x180026c8c  call    memset_0
0x180026c91  mov     [rsp+4E8h+var_2E8], 80h
0x180026c9c  mov     [rsp+4E8h+var_2E4], 9
0x180026ca7  lea     rdx, [rsp+4E8h+var_2E8]
0x180026caf  mov     rcx, [rsp+4E8h+var_498]
0x180026cb4  mov     rax, rsi
0x180026cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cbc  mov     r14d, eax
0x180026cbf  test    eax, eax
0x180026cc1  js      short loc_180026CFA
0x180026cc3  mov     al, [rsp+4E8h+var_296]
0x180026cca  test    al, 20h
0x180026ccc  jz      short loc_180026CD2
0x180026cce  bts     ebx, 0Fh
  ... truncated ...
```
