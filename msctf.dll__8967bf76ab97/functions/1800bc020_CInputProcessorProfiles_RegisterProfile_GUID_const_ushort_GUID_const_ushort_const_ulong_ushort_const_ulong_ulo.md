# CInputProcessorProfiles::RegisterProfile(_GUID const &,ushort,_GUID const &,ushort const *,ulong,ushort const *,ulong,ulong,HKL__ *,ulong,int,ulong)

- ea: `0x1800bc020`
- end: `0x1800bc452`
- name: `?RegisterProfile@CInputProcessorProfiles@@UEAAJAEBU_GUID@@G0PEBGK1KKPEAUHKL__@@KHK@Z`
- size: `1074`
- prototype: `int(CInputProcessorProfiles *__hidden this, const struct _GUID *, unsigned __int16, const struct _GUID *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, HKL, unsigned int, int, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000fac0`
- `0x1800226c0`
- `0x180022740`
- `0x180026580`
- `0x180053824`
- `0x1800539d8`
- `0x18005c40c`
- `0x18009eaea`
- `0x1800a4e04`
- `0x1800b7440`
- `0x1800bc020`
- `0x1800be834`
- `0x1800be9f4`
- `0x180106a60`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800bc14c`
- `msvcrt!wcsnlen` at `0x1800bc15e`
- `msvcrt!wcsnlen` at `0x1800bc14c`
- `msvcrt!wcsnlen` at `0x1800bc15e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc2af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc316`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc2af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bc316`

## pseudocode

```c
__int64 __fastcall CInputProcessorProfiles::RegisterProfile(
        CInputProcessorProfiles *this,
        struct _GUID *a2,
        unsigned __int16 a3,
        struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned int a9,
        HKL a10,
        unsigned int a11,
        int a12,
        char a13)
{
  unsigned int v13; // edi
  unsigned __int16 v14; // r14
  int v15; // esi
  size_t v16; // rbx
  size_t v17; // rax
  unsigned __int16 *v18; // r9
  unsigned __int16 *v20; // r9
  int v21; // eax
  CInputProfileManager *v22; // rcx
  DWORD lpData; // [rsp+20h] [rbp-E0h]
  DWORD lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int v25; // [rsp+38h] [rbp-C8h]
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  void **v27; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h]
  void **v29; // [rsp+78h] [rbp-88h] BYREF
  HKEY v30; // [rsp+80h] [rbp-80h]
  struct _GUID *v31; // [rsp+88h] [rbp-78h]
  struct _GUID *v32; // [rsp+90h] [rbp-70h]
  CInputProcessorProfiles *v33; // [rsp+98h] [rbp-68h]
  struct _GUID v34; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v35[40]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Source[256]; // [rsp+100h] [rbp+0h] BYREF

  v13 = a12 != 0 ? 2 : 0;
  *(_DWORD *)Data = 0xFFFF;
  v31 = a4;
  v14 = 0;
  if ( a3 != 0xFFFF )
    v14 = a3;
  v32 = a2;
  v33 = this;
  v15 = 0;
  v34 = GUID_NULL;
  if ( (a13 & 0xC) == 0 )
  {
    v30 = 0;
    v29 = &CPreloadRegKey::`vftable';
    v27 = &CPreloadRegKey::`vftable';
    hKey = 0;
    StringCchCopyW(Source, 0x100u, L"SOFTWARE\\Microsoft\\CTF\\TIP\\");
    memset_0(v35, 0, 0x4Eu);
    CLSIDToStringW(v32, v35);
    StringCchCatW(Source, 0x100u, v35);
    StringCchCatW(Source, 0x100u, L"\\");
    StringCchCatW(Source, 0x100u, L"LanguageProfile\\");
    if ( v14 )
      *(_DWORD *)Data = v14;
    v16 = wcsnlen(Source, 0x100u);
    v17 = wcsnlen(Source, 0x100u);
    StringCchPrintfW(&Source[v17], 256 - v16, L"0x%08x", *(unsigned int *)Data);
    if ( (unsigned int)CMyRegKey::Create((CMyRegKey *)&v29, HKEY_LOCAL_MACHINE, Source, v18, lpData, 0x2001Fu) )
    {
      CInputDllRegKey::Close((CInputDllRegKey *)&v27);
LABEL_8:
      v29 = &CPreloadRegKey::`vftable';
      CInputDllRegKey::Close((CInputDllRegKey *)&v29);
      return 2147500037LL;
    }
    CLSIDToStringW(v31, Source);
    if ( (unsigned int)CMyRegKey::Create((CMyRegKey *)&v27, v30, Source, v20, lpDataa, 0x2001Fu) )
    {
      v27 = &CPreloadRegKey::`vftable';
      CInputDllRegKey::Close((CInputDllRegKey *)&v27);
      goto LABEL_8;
    }
    if ( a5 && a6 )
    {
      StringCchCopyNW(Source, 0x100u, a5, a6);
      CMyRegKey::SetValue((CMyRegKey *)&v27, Source, L"Description");
    }
    if ( a7 && a8 )
    {
      StringCchCopyNW(Source, 0x100u, a7, a8);
      CMyRegKey::SetValue((CMyRegKey *)&v27, Source, L"IconFile");
      *(_DWORD *)Data = a9;
      RegSetValueExW(hKey, L"IconIndex", 0, 4u, Data, 4u);
    }
    if ( a10 )
    {
      StringCchPrintfW(Source, 0x100u, L"0x%08x", (unsigned int)a10);
      CMyRegKey::SetValue((CMyRegKey *)&v27, Source, L"SubstituteLayout");
    }
    *(_DWORD *)Data = a12 != 0;
    RegSetValueExW(hKey, L"Enable", 0, 4u, Data, 4u);
    v27 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v27);
    v29 = &CPreloadRegKey::`vftable';
    CInputDllRegKey::Close((CInputDllRegKey *)&v29);
    goto LABEL_25;
  }
  if ( (a13 & 4) != 0 )
  {
    v13 |= 0x80000000;
    v21 = CInputProcessorProfiles::RegisterProfile_LocalProcess(this, v14, a2, a4, &v34, a5, a6, a7, a8, a9, a10, v13);
  }
  else
  {
    if ( (a13 & 8) == 0 )
      goto LABEL_26;
    v13 |= 0x80000000;
    v21 = CInputProcessorProfiles::RegisterProfile_LocalThread(this, v14, a2, a4, &v34, a5, a6, a7, a8, a9, a10, v13);
  }
  v15 = v21;
  if ( !v21 )
  {
LABEL_25:
    a2 = v32;
    a4 = v31;
LABEL_26:
    v22 = (CInputProfileManager *)*((_QWORD *)v33 + 5);
    if ( v22 )
      v15 = CInputProfileManager::RegisterProfile(v22, v14, a2, a4, &v34, a10, v13, v25);
  }
  return (v15 >> 31) & 0x80004005;
}

```

## disassembly

```asm
0x1800bc020  push    rbp
0x1800bc022  push    rbx
0x1800bc023  push    rsi
0x1800bc024  push    rdi
0x1800bc025  push    r12
0x1800bc027  push    r13
0x1800bc029  push    r14
0x1800bc02b  push    r15
0x1800bc02d  lea     rbp, [rsp-218h]
0x1800bc035  sub     rsp, 318h
0x1800bc03c  mov     rax, cs:__security_cookie
0x1800bc043  xor     rax, rsp
0x1800bc046  mov     [rbp+250h+var_50], rax
0x1800bc04d  mov     eax, [rbp+250h+arg_58]
0x1800bc053  xor     ebx, ebx
0x1800bc055  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800bc05c  mov     r12, [rbp+250h+arg_20]
0x1800bc063  neg     eax
0x1800bc065  mov     r13, [rbp+250h+arg_30]
0x1800bc06c  mov     eax, 0FFFFh
0x1800bc071  mov     r15, [rbp+250h+arg_48]
0x1800bc078  sbb     edi, edi
0x1800bc07a  and     edi, 2
0x1800bc07d  mov     dword ptr [rsp+350h+Data], eax
0x1800bc081  cmp     r8w, ax
0x1800bc085  mov     [rbp+250h+var_2C8], r9
0x1800bc089  mov     eax, [rbp+250h+arg_60]
0x1800bc08f  mov     r14d, ebx
0x1800bc092  cmovnz  r14w, r8w
0x1800bc097  mov     [rbp+250h+var_2C0], rdx
0x1800bc09b  mov     [rbp+250h+var_2B8], rcx
0x1800bc09f  mov     esi, ebx
0x1800bc0a1  movdqu  xmmword ptr [rbp+250h+var_2B0.Data1], xmm0
0x1800bc0a6  test    al, 0Ch
0x1800bc0a8  jnz     loc_1800BC346
0x1800bc0ae  lea     rax, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800bc0b5  mov     [rbp+250h+var_2D0], rbx
0x1800bc0b9  lea     r8, ?c_szCTFTIPKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\TIP\\"
0x1800bc0c0  mov     [rsp+350h+var_2D8], rax
0x1800bc0c5  mov     edx, 100h; unsigned __int64
0x1800bc0ca  mov     [rsp+350h+var_2E8], rax
0x1800bc0cf  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc0d3  mov     [rsp+350h+hKey], rbx
0x1800bc0d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bc0dd  xor     edx, edx; Val
0x1800bc0df  lea     r8d, [rbx+4Eh]; Size
0x1800bc0e3  lea     rcx, [rbp+250h+var_2A0]; void *
0x1800bc0e7  call    memset_0
0x1800bc0ec  mov     rcx, [rbp+250h+var_2C0]; struct _GUID *
0x1800bc0f0  lea     rdx, [rbp+250h+var_2A0]; unsigned __int16 *
0x1800bc0f4  call    ?CLSIDToStringW@@YAHAEBU_GUID@@PEAG@Z; CLSIDToStringW(_GUID const &,ushort *)
0x1800bc0f9  lea     r8, [rbp+250h+var_2A0]; unsigned __int16 *
0x1800bc0fd  mov     edx, 100h; unsigned __int64
0x1800bc102  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc106  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bc10b  lea     r8, SubBlock; "\\"
0x1800bc112  mov     edx, 100h; unsigned __int64
0x1800bc117  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc11b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bc120  lea     r8, ?c_szLanguageProfileKey@@3QBGB; "LanguageProfile\\"
0x1800bc127  mov     edx, 100h; unsigned __int64
0x1800bc12c  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc130  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800bc135  test    r14w, r14w
0x1800bc139  jz      short loc_1800BC143
0x1800bc13b  movzx   eax, r14w
0x1800bc13f  mov     dword ptr [rsp+350h+Data], eax
0x1800bc143  mov     edx, 100h; MaxCount
0x1800bc148  lea     rcx, [rbp+250h+Source]; Source
0x1800bc14c  call    cs:__imp_wcsnlen
0x1800bc152  mov     edx, 100h; MaxCount
0x1800bc157  lea     rcx, [rbp+250h+Source]; Source
0x1800bc15b  mov     rbx, rax
0x1800bc15e  call    cs:__imp_wcsnlen
0x1800bc164  mov     r9d, dword ptr [rsp+350h+Data]
0x1800bc169  lea     rcx, [rbp+250h+Source]
0x1800bc16d  mov     edx, 100h
0x1800bc172  lea     r8, a0x08x; "0x%08x"
0x1800bc179  sub     rdx, rbx; unsigned __int64
0x1800bc17c  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x1800bc180  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bc185  mov     ebx, 2001Fh
0x1800bc18a  lea     r8, [rbp+250h+Source]; lpSubKey
0x1800bc18e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800bc195  mov     [rsp+350h+cbData], ebx; unsigned int
0x1800bc199  lea     rcx, [rsp+350h+var_2D8]; this
0x1800bc19e  call    ?Create@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CMyRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800bc1a3  test    eax, eax
0x1800bc1a5  jz      short loc_1800BC1D1
0x1800bc1a7  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc1ac  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800bc1b1  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800bc1b8  lea     rcx, [rsp+350h+var_2D8]; this
0x1800bc1bd  mov     [rsp+350h+var_2D8], rbx
0x1800bc1c2  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800bc1c7  mov     eax, 80004005h
0x1800bc1cc  jmp     loc_1800BC42F
0x1800bc1d1  mov     rcx, [rbp+250h+var_2C8]; struct _GUID *
0x1800bc1d5  lea     rdx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc1d9  call    ?CLSIDToStringW@@YAHAEBU_GUID@@PEAG@Z; CLSIDToStringW(_GUID const &,ushort *)
0x1800bc1de  mov     rdx, [rbp+250h+var_2D0]; hKey
0x1800bc1e2  lea     r8, [rbp+250h+Source]; lpSubKey
0x1800bc1e6  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc1eb  mov     [rsp+350h+cbData], ebx; unsigned int
0x1800bc1ef  call    ?Create@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CMyRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800bc1f4  test    eax, eax
0x1800bc1f6  jz      short loc_1800BC210
0x1800bc1f8  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800bc1ff  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc204  mov     [rsp+350h+var_2E8], rbx
0x1800bc209  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800bc20e  jmp     short loc_1800BC1B8
0x1800bc210  test    r12, r12
0x1800bc213  jz      short loc_1800BC248
0x1800bc215  mov     eax, [rbp+250h+arg_28]
0x1800bc21b  test    eax, eax
0x1800bc21d  jz      short loc_1800BC248
0x1800bc21f  mov     r9d, eax; unsigned __int64
0x1800bc222  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc226  mov     r8, r12; unsigned __int16 *
0x1800bc229  mov     edx, 100h; unsigned __int64
0x1800bc22e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800bc233  lea     r8, ?c_szDescription@@3QBGB; "Description"
0x1800bc23a  lea     rdx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc23e  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc243  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800bc248  mov     ebx, 4
0x1800bc24d  test    r13, r13
0x1800bc250  jz      short loc_1800BC2B5
0x1800bc252  mov     eax, [rbp+250h+arg_38]
0x1800bc258  test    eax, eax
0x1800bc25a  jz      short loc_1800BC2B5
0x1800bc25c  mov     r9d, eax; unsigned __int64
0x1800bc25f  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc263  mov     r8, r13; unsigned __int16 *
0x1800bc266  mov     edx, 100h; unsigned __int64
0x1800bc26b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800bc270  lea     r8, ?c_szIconFile@@3QBGB; "IconFile"
0x1800bc277  lea     rdx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc27b  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc280  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800bc285  mov     eax, [rbp+250h+arg_40]
0x1800bc28b  lea     rdx, ?c_szIconIndex@@3QBGB; "IconIndex"
0x1800bc292  mov     rcx, [rsp+350h+hKey]; hKey
0x1800bc297  mov     r9d, ebx; dwType
0x1800bc29a  mov     dword ptr [rsp+350h+Data], eax
0x1800bc29e  xor     r8d, r8d; Reserved
0x1800bc2a1  lea     rax, [rsp+350h+Data]
0x1800bc2a6  mov     [rsp+350h+cbData], ebx; cbData
0x1800bc2aa  mov     [rsp+350h+lpData], rax; lpData
0x1800bc2af  call    cs:__imp_RegSetValueExW
0x1800bc2b5  test    r15, r15
0x1800bc2b8  jz      short loc_1800BC2E7
0x1800bc2ba  mov     r9d, r15d
0x1800bc2bd  lea     r8, a0x08x; "0x%08x"
0x1800bc2c4  mov     edx, 100h; unsigned __int64
0x1800bc2c9  lea     rcx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc2cd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bc2d2  lea     r8, ?c_szSubstitutehKL@@3QBGB; "SubstituteLayout"
0x1800bc2d9  lea     rdx, [rbp+250h+Source]; unsigned __int16 *
0x1800bc2dd  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc2e2  call    ?SetValue@CMyRegKey@@QEAAJPEBG0@Z; CMyRegKey::SetValue(ushort const *,ushort const *)
0x1800bc2e7  mov     rcx, [rsp+350h+hKey]; hKey
0x1800bc2ec  lea     rdx, ?c_szEnable@@3QBGB; "Enable"
0x1800bc2f3  xor     eax, eax
0x1800bc2f5  mov     [rsp+350h+cbData], ebx; cbData
0x1800bc2f9  cmp     [rbp+250h+arg_58], eax
0x1800bc2ff  mov     r9d, ebx; dwType
0x1800bc302  setnz   al
0x1800bc305  xor     r8d, r8d; Reserved
0x1800bc308  mov     dword ptr [rsp+350h+Data], eax
0x1800bc30c  lea     rax, [rsp+350h+Data]
0x1800bc311  mov     [rsp+350h+lpData], rax; lpData
0x1800bc316  call    cs:__imp_RegSetValueExW
0x1800bc31c  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800bc323  lea     rcx, [rsp+350h+var_2E8]; this
0x1800bc328  mov     [rsp+350h+var_2E8], rbx
0x1800bc32d  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800bc332  lea     rcx, [rsp+350h+var_2D8]; this
0x1800bc337  mov     [rsp+350h+var_2D8], rbx
0x1800bc33c  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800bc341  jmp     loc_1800BC3EF
0x1800bc346  mov     ebx, 4
0x1800bc34b  test    bl, al
0x1800bc34d  jz      short loc_1800BC39B
0x1800bc34f  mov     eax, [rbp+250h+arg_40]
0x1800bc355  bts     edi, 1Fh
0x1800bc359  mov     [rsp+350h+var_2F8], edi; unsigned int
0x1800bc35d  mov     r8, rdx; struct _GUID *
0x1800bc360  mov     [rsp+350h+var_300], r15; HKL
0x1800bc365  movzx   edx, r14w; unsigned __int16
0x1800bc369  mov     [rsp+350h+var_308], eax; unsigned int
0x1800bc36d  mov     eax, [rbp+250h+arg_38]
0x1800bc373  mov     [rsp+350h+var_310], eax; unsigned int
0x1800bc377  mov     eax, [rbp+250h+arg_28]
0x1800bc37d  mov     [rsp+350h+var_318], r13; unsigned __int16 *
0x1800bc382  mov     [rsp+350h+var_320], eax; unsigned int
0x1800bc386  lea     rax, [rbp+250h+var_2B0]
0x1800bc38a  mov     qword ptr [rsp+350h+cbData], r12; unsigned __int16 *
0x1800bc38f  mov     [rsp+350h+lpData], rax; struct _GUID *
0x1800bc394  call    ?RegisterProfile_LocalProcess@CInputProcessorProfiles@@AEAAJGAEBU_GUID@@00PEBGK1KKPEAUHKL__@@K@Z; CInputProcessorProfiles::RegisterProfile_LocalProcess(ushort,_GUID const &,_GUID const &,_GUID const &,ushort const *,ulong,ushort const *,ulong,ulong,HKL__ *,ulong)
0x1800bc399  jmp     short loc_1800BC3E9
0x1800bc39b  test    al, 8
0x1800bc39d  jz      short loc_1800BC3F7
0x1800bc39f  mov     eax, [rbp+250h+arg_40]
0x1800bc3a5  bts     edi, 1Fh
0x1800bc3a9  mov     [rsp+350h+var_2F8], edi; unsigned int
0x1800bc3ad  mov     r8, rdx; struct _GUID *
0x1800bc3b0  mov     [rsp+350h+var_300], r15; HKL
0x1800bc3b5  movzx   edx, r14w; unsigned __int16
0x1800bc3b9  mov     [rsp+350h+var_308], eax; unsigned int
0x1800bc3bd  mov     eax, [rbp+250h+arg_38]
0x1800bc3c3  mov     [rsp+350h+var_310], eax; unsigned int
0x1800bc3c7  mov     eax, [rbp+250h+arg_28]
0x1800bc3cd  mov     [rsp+350h+var_318], r13; unsigned int
0x1800bc3d2  mov     [rsp+350h+var_320], eax; unsigned int
0x1800bc3d6  lea     rax, [rbp+250h+var_2B0]
0x1800bc3da  mov     qword ptr [rsp+350h+cbData], r12; unsigned __int16 *
0x1800bc3df  mov     [rsp+350h+lpData], rax; struct _GUID *
0x1800bc3e4  call    ?RegisterProfile_LocalThread@CInputProcessorProfiles@@AEAAJGAEBU_GUID@@00PEBGK1KKPEAUHKL__@@K@Z; CInputProcessorProfiles::RegisterProfile_LocalThread(ushort,_GUID const &,_GUID const &,_GUID const &,ushort const *,ulong,ushort const *,ulong,ulong,HKL__ *,ulong)
0x1800bc3e9  mov     esi, eax
0x1800bc3eb  test    eax, eax
0x1800bc3ed  jnz     short loc_1800BC424
0x1800bc3ef  mov     rdx, [rbp+250h+var_2C0]
0x1800bc3f3  mov     r9, [rbp+250h+var_2C8]; struct _GUID *
0x1800bc3f7  mov     rcx, [rbp+250h+var_2B8]
0x1800bc3fb  mov     rcx, [rcx+28h]; this
0x1800bc3ff  test    rcx, rcx
0x1800bc402  jz      short loc_1800BC424
0x1800bc404  mov     [rsp+350h+var_320], edi; unsigned int
0x1800bc408  lea     rax, [rbp+250h+var_2B0]
0x1800bc40c  mov     r8, rdx; struct _GUID *
0x1800bc40f  mov     qword ptr [rsp+350h+cbData], r15; HKL
0x1800bc414  movzx   edx, r14w; unsigned __int16
0x1800bc418  mov     [rsp+350h+lpData], rax; struct _GUID *
0x1800bc41d  call    ?RegisterProfile@CInputProfileManager@@QEAAJGAEBU_GUID@@00PEAUHKL__@@KK@Z; CInputProfileManager::RegisterProfile(ushort,_GUID const &,_GUID const &,_GUID const &,HKL__ *,ulong,ulong)
0x1800bc422  mov     esi, eax
0x1800bc424  sar     esi, 1Fh
0x1800bc427  and     esi, 80004005h
0x1800bc42d  mov     eax, esi
0x1800bc42f  mov     rcx, [rbp+250h+var_50]
0x1800bc436  xor     rcx, rsp; StackCookie
0x1800bc439  call    __security_check_cookie
0x1800bc43e  add     rsp, 318h
0x1800bc445  pop     r15
0x1800bc447  pop     r14
0x1800bc449  pop     r13
0x1800bc44b  pop     r12
0x1800bc44d  pop     rdi
0x1800bc44e  pop     rsi
0x1800bc44f  pop     rbx
0x1800bc450  pop     rbp
0x1800bc451  retn
```
