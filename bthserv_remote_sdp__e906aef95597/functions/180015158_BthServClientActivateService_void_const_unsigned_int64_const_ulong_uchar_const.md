# BthServClientActivateService(void * const,unsigned __int64 const *,ulong,uchar * const)

- ea: `0x180015158`
- end: `0x18001598f`
- name: `?BthServClientActivateService@@YAKQEAXPEB_KKQEAE@Z`
- size: `2103`
- prototype: `__int64 __fastcall(void *const, const unsigned __int64 *, DWORD, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800130b0`
- `0x180027ea8`

## callees

- `0x1800017a0`
- `0x180001b94`
- `0x180008af8`
- `0x180011b9c`
- `0x180014944`
- `0x180014af0`
- `0x180014ccc`
- `0x180014e30`
- `0x180014f14`
- `0x180015158`
- `0x180017944`
- `0x1800179bc`
- `0x1800179dc`
- `0x1800179fc`
- `0x180034b50`
- `0x180034b5c`
- `0x180036034`
- `0x180036108`
- `0x18003627c`
- `0x1800362f0`
- `0x180036d0c`
- `0x180037044`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001533f`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001533f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001583b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001583b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001575c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001575c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015815`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015815`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015257`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800152d6`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015257`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800152d6`

## string_xrefs

- `0x180015249`: `System\CurrentControlSet\Services\BTHPORT\Parameters`
- `0x1800152c8`: `System\CurrentControlSet\Services\BTHPORT\Parameters`
- `0x1800158a6`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x1800158ba`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x1800158ce`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x1800158e2`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180015940`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180015954`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180015968`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x18001597c`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x1800156a7`: `CachedServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BthServClientActivateService(
        void *const a1,
        const unsigned __int64 *a2,
        DWORD a3,
        unsigned __int8 *const a4)
{
  char v7; // al
  int v8; // eax
  int IsStreamRecord; // eax
  int v10; // eax
  int PersistedRegistryLocationW; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rbx
  unsigned int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // rsi
  __int64 v19; // rbx
  void **v20; // rax
  __int64 v21; // r13
  __int64 v22; // rcx
  __int128 *v23; // rdi
  unsigned __int64 v24; // rax
  size_t v25; // rbx
  __int64 v26; // rax
  __m128i *v27; // rdi
  unsigned __int64 v28; // rbx
  __int64 v29; // r13
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  __m128i *v32; // rax
  void **v33; // rdx
  void *v34; // rsi
  char *v35; // rsi
  size_t v36; // rbx
  void **v37; // rdx
  __int64 v38; // rax
  const WCHAR *v39; // rdx
  unsigned int v40; // eax
  int AttributeInStream; // eax
  __int64 v42; // r8
  __int64 v43; // r9
  unsigned int v44; // eax
  int v45; // eax
  unsigned int v46; // eax
  wil *v47; // rcx
  __int64 result; // rax
  signed int v49; // eax
  int dwOptions; // [rsp+20h] [rbp-1B8h]
  int dwOptionsa; // [rsp+20h] [rbp-1B8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-1B8h]
  int dwOptionsc; // [rsp+20h] [rbp-1B8h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-1B8h]
  unsigned int v55[2]; // [rsp+50h] [rbp-188h] BYREF
  void **v56; // [rsp+58h] [rbp-180h]
  HKEY hKey; // [rsp+60h] [rbp-178h] BYREF
  __m128i v58; // [rsp+68h] [rbp-170h] BYREF
  __m128i v59; // [rsp+78h] [rbp-160h]
  void *v60[2]; // [rsp+88h] [rbp-150h] BYREF
  __m128i si128; // [rsp+98h] [rbp-140h]
  __int128 v62; // [rsp+A8h] [rbp-130h] BYREF
  __int128 v63; // [rsp+B8h] [rbp-120h]
  void *Src[2]; // [rsp+C8h] [rbp-110h] BYREF
  __int64 v65; // [rsp+D8h] [rbp-100h]
  unsigned __int64 v66; // [rsp+E0h] [rbp-F8h]
  LPCWSTR lpSubKey[4]; // [rsp+E8h] [rbp-F0h] BYREF
  _BYTE v68[32]; // [rsp+108h] [rbp-D0h] BYREF
  _BYTE v69[32]; // [rsp+128h] [rbp-B0h] BYREF
  _BYTE v70[32]; // [rsp+148h] [rbp-90h] BYREF
  void *v71[2]; // [rsp+168h] [rbp-70h] BYREF
  __int64 v72; // [rsp+178h] [rbp-60h]
  __int16 v73; // [rsp+180h] [rbp-58h]
  WCHAR ValueName[12]; // [rsp+188h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  if ( !a4 || (v7 = 0, a3 < 2) )
    v7 = 1;
  try
  {
    if ( v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2DC,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)0x80070057LL,
        dwOptions);
    v8 = SdpValidateStream((_DWORD)a4, a3, 0, 0, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2DF,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)v8,
        dwOptionsa);
    IsStreamRecord = SdpIsStreamRecord(a4, a3);
    if ( IsStreamRecord < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2E2,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)IsStreamRecord,
        dwOptionsa);
    LOWORD(v55[0]) = 0;
    v10 = SdpVerifyServiceRecord(a4);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2E8,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)v10,
        dwOptionsa);
    *(_OWORD *)v71 = 0;
    v72 = 0;
    v55[0] = 0;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"BluetoothBthPortParams",
                                   L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
                                   0,
                                   0);
    if ( PersistedRegistryLocationW > 0 )
      v12 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    else
      v12 = (unsigned int)PersistedRegistryLocationW;
    if ( PersistedRegistryLocationW != 234 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateLocationHelpers.h",
        (const char *)v12,
        (int)v55);
    v13 = (__int64)v71[0];
    v14 = GetPersistedRegistryLocationW(
            L"BluetoothBthPortParams",
            L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
            v71[0],
            (char *)v71[1] - (char *)v71[0]);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateLocationHelpers.h",
        (const char *)v14,
        (unsigned int)v55);
    std::wstring::wstring(Src, v71[0]);
    if ( v13 )
    {
      v15 = -v13;
      v16 = v13;
      if ( (unsigned __int64)-v13 >= 0x1000 )
      {
        v15 = 39 - v13;
        v13 = *(_QWORD *)(v13 - 8);
        if ( (unsigned __int64)(v16 - v13 - 8) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn();
          __debugbreak();
        }
      }
      operator delete((void *)v13, (const struct std::nothrow_t *)v15);
    }
    v17 = *a2;
    *(_OWORD *)v71 = 0;
    v72 = 0;
    v73 = 0;
    StringCchPrintfW((unsigned __int16 *)v71, 0xDu, L"%012llX", v17 & 0xFFFFFFFFFFFFLL);
    std::wstring::wstring(v60, v71);
    v18 = 0x7FFFFFFFFFFFFFFELL;
    v19 = v65;
    if ( v65 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v20 = Src;
    if ( v66 > 7 )
      v20 = (void **)Src[0];
    v56 = v20;
    v62 = 0;
    v63 = 0;
    v21 = v65 + 1;
    v22 = 7;
    v23 = &v62;
    if ( (unsigned __int64)(v65 + 1) > 7 )
    {
      v24 = v21 | 7;
      if ( (v21 | 7uLL) <= 0x7FFFFFFFFFFFFFFELL )
      {
        if ( v24 < 0xA )
          v24 = 10;
      }
      else
      {
        v24 = 0x7FFFFFFFFFFFFFFELL;
      }
      *(_QWORD *)v55 = v24;
      v23 = (__int128 *)std::wstring::_Allocate_for_capacity<0>(7, v55);
      *(_QWORD *)&v62 = v23;
      v22 = *(_QWORD *)v55;
      v20 = v56;
    }
    *(_QWORD *)&v63 = v19 + 1;
    *((_QWORD *)&v63 + 1) = v22;
    v25 = 2 * v19;
    memcpy_0(v23, v20, v25);
    *(_WORD *)((char *)v23 + v25) = psz[0];
    *((_WORD *)v23 + v21) = 0;
    v26 = std::operator+<unsigned short>(v70, &v62, L"Devices");
    v27 = (__m128i *)std::operator+<unsigned short>(v69, v26, L"\\");
    v58 = 0;
    v59 = 0;
    v28 = v27[1].m128i_u64[0];
    v29 = si128.m128i_i64[0];
    v30 = v28 + si128.m128i_i64[0];
    v31 = si128.m128i_u64[1];
    if ( si128.m128i_i64[0] > v27[1].m128i_i64[1] - v28 || si128.m128i_i64[1] > (unsigned __int64)v27[1].m128i_i64[1] )
    {
      if ( v28 > si128.m128i_i64[1] - si128.m128i_i64[0] )
      {
        if ( 0x7FFFFFFFFFFFFFFELL - v28 < si128.m128i_i64[0] )
          std::_Xlen_string();
        if ( (v30 | 7) <= 0x7FFFFFFFFFFFFFFELL )
        {
          v18 = v30 | 7;
          if ( (v30 | 7) < 0xA )
            v18 = 10;
        }
        *(_QWORD *)v55 = v18;
        v35 = (char *)std::wstring::_Allocate_for_capacity<0>(si128.m128i_i64[1], v55);
        v58.m128i_i64[0] = (__int64)v35;
        v59.m128i_i64[0] = v28 + v29;
        v59.m128i_i64[1] = *(_QWORD *)v55;
        if ( v27[1].m128i_i64[1] > 7uLL )
          v27 = (__m128i *)v27->m128i_i64[0];
        v36 = 2 * v28;
        memcpy_0(v35, v27, v36);
        v37 = v60;
        if ( si128.m128i_i64[1] > 7uLL )
          v37 = (void **)v60[0];
        memcpy_0(&v35[v36], v37, 2 * v29 + 2);
      }
      else
      {
        v58 = *(__m128i *)v60;
        v59 = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v60[0]) = 0;
        v34 = (void *)v58.m128i_i64[0];
        memmove_0((void *)(2 * v28 + v58.m128i_i64[0]), (const void *)v58.m128i_i64[0], 2 * v29 + 2);
        if ( v27[1].m128i_i64[1] > 7uLL )
          v27 = (__m128i *)v27->m128i_i64[0];
        memcpy_0(v34, v27, 2 * v28);
        v59.m128i_i64[0] = v28 + v29;
      }
    }
    else
    {
      v58 = *v27;
      v59 = v27[1];
      v27[1].m128i_i64[0] = 0;
      v27[1].m128i_i64[1] = 7;
      v27->m128i_i16[0] = 0;
      v32 = &v58;
      if ( v59.m128i_i64[1] > 7uLL )
        v32 = (__m128i *)v58.m128i_i64[0];
      v33 = v60;
      if ( v31 > 7 )
        v33 = (void **)v60[0];
      memcpy_0((char *)v32 + 2 * v28, v33, 2 * v29 + 2);
      v59.m128i_i64[0] = v28 + v29;
    }
    v38 = std::operator+<unsigned short>(v68, &v58, L"\\");
    std::operator+<unsigned short>(lpSubKey, v38, L"CachedServices");
    std::wstring::~wstring(v68);
    std::wstring::~wstring(&v58);
    std::wstring::~wstring(v69);
    std::wstring::~wstring(v70);
    std::wstring::~wstring(&v62);
    std::wstring::~wstring(v60);
    hKey = 0;
    v39 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v39 = lpSubKey[0];
    v40 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v39, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v40 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2FC,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)v40,
        dwOptionsb);
    v56 = 0;
    AttributeInStream = SdpFindAttributeInStream(a4, (__int64)v55);
    if ( AttributeInStream < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x301,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)AttributeInStream,
        dwOptionsc);
    v55[0] = 0;
    SdpRetrieveUint32((char *)v56 + 1, v55, v42, v43);
    v44 = SdpByteSwapUint32(v55[0]);
    v45 = StringCbPrintfW(ValueName, 0x12u, L"%08x", v44);
    if ( v45 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30F,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)v45,
        dwOptionsc);
    v46 = RegSetValueExW(hKey, ValueName, 0, 3u, a4, a3);
    if ( v46 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x311,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)v46,
        dwOptionsd);
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring(lpSubKey);
    std::wstring::~wstring(Src);
    result = 0;
  }
  catch ( ... )
  {
    v49 = wil::ResultFromCaughtException(v47);
    if ( v49 < 0 )
    {
      if ( (v49 & 0x1FFF0000) == 0x70000 )
      {
        v49 = (unsigned __int16)v49;
      }
      else
      {
        if ( (v49 & 0x10000000) == 0 )
          return 87;
        v49 = RtlNtStatusToDosErrorNoTeb(v49 & 0xEFFFFFFF);
      }
      v55[0] = v49;
    }
    else
    {
      v55[0] = 0;
    }
    return v55[0];
  }
  return result;
}

```

## disassembly

```asm
0x180015158  mov     [rsp+arg_0], rbx
0x18001515d  mov     [rsp+arg_8], rsi
0x180015162  push    rdi
0x180015163  push    r12
0x180015165  push    r13
0x180015167  push    r14
0x180015169  push    r15
0x18001516b  sub     rsp, 1B0h
0x180015172  mov     rax, cs:__security_cookie
0x180015179  xor     rax, rsp
0x18001517c  mov     [rsp+1D8h+var_38], rax
0x180015184  mov     r12, r9
0x180015187  mov     r15d, r8d
0x18001518a  mov     rsi, rdx
0x18001518d  xor     r14d, r14d
0x180015190  test    r9, r9
0x180015193  jz      short loc_18001519E
0x180015195  cmp     r8d, 2
0x180015199  mov     al, r14b
0x18001519c  jnb     short loc_1800151A0
0x18001519e  mov     al, 1
0x1800151a0  mov     rcx, [rsp+1D8h]; this
0x1800151a8  test    al, al
0x1800151aa  jnz     loc_1800158A0
0x1800151b0  mov     qword ptr [rsp+1D8h+dwOptions], r14; int
0x1800151b5  xor     r9d, r9d
0x1800151b8  xor     r8d, r8d
0x1800151bb  mov     edx, r15d
0x1800151be  mov     rcx, r12
0x1800151c1  call    SdpValidateStream
0x1800151c6  mov     rcx, [rsp+1D8h]; this
0x1800151ce  test    eax, eax
0x1800151d0  js      loc_1800158B7
0x1800151d6  mov     edx, r15d
0x1800151d9  mov     rcx, r12
0x1800151dc  call    SdpIsStreamRecord
0x1800151e1  mov     rcx, [rsp+1D8h]; this
0x1800151e9  test    eax, eax
0x1800151eb  js      loc_1800158CB
0x1800151f1  mov     word ptr [rsp+1D8h+var_188], r14w
0x1800151f7  lea     r9, [rsp+1D8h+var_188]
0x1800151fc  mov     r8d, 4
0x180015202  mov     edx, r15d
0x180015205  mov     rcx, r12; unsigned __int8 *
0x180015208  call    SdpVerifyServiceRecord
0x18001520d  mov     rcx, [rsp+1D8h]; this
0x180015215  test    eax, eax
0x180015217  js      loc_1800158DF
0x18001521d  xorps   xmm0, xmm0
0x180015220  movdqu  xmmword ptr [rsp+1D8h+var_70], xmm0
0x180015229  mov     rdi, r14
0x18001522c  mov     [rsp+1D8h+var_60], r14
0x180015234  mov     [rsp+1D8h+var_188], r14d
0x180015239  lea     rax, [rsp+1D8h+var_188]
0x18001523e  mov     qword ptr [rsp+1D8h+dwOptions], rax; int
0x180015243  xor     r9d, r9d
0x180015246  xor     r8d, r8d
0x180015249  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BT"...
0x180015250  lea     rcx, aBluetoothbthpo; "BluetoothBthPortParams"
0x180015257  call    cs:__imp_GetPersistedRegistryLocationW
0x18001525e  nop     dword ptr [rax+rax+00h]
0x180015263  test    eax, eax
0x180015265  jg      short loc_18001526C
0x180015267  mov     r9d, eax
0x18001526a  jmp     short loc_180015277
0x18001526c  movzx   r9d, ax
0x180015270  or      r9d, 80070000h; char *
0x180015277  mov     rcx, [rsp+1D8h]; this
0x18001527f  cmp     eax, 0EAh
0x180015284  jnz     loc_1800158F4
0x18001528a  mov     edx, [rsp+1D8h+var_188]
0x18001528e  test    rdx, rdx
0x180015291  jz      short loc_1800152A8
0x180015293  lea     rcx, [rsp+1D8h+var_70]
0x18001529b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800152a0  mov     rdi, [rsp+1D8h+var_60]
0x1800152a8  mov     r9, [rsp+1D8h+var_70+8]
0x1800152b0  mov     rbx, [rsp+1D8h+var_70]
0x1800152b8  sub     r9, rbx
0x1800152bb  lea     rax, [rsp+1D8h+var_188]
0x1800152c0  mov     qword ptr [rsp+1D8h+dwOptions], rax; int
0x1800152c5  mov     r8, rbx
0x1800152c8  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BT"...
0x1800152cf  lea     rcx, aBluetoothbthpo; "BluetoothBthPortParams"
0x1800152d6  call    cs:__imp_GetPersistedRegistryLocationW
0x1800152dd  nop     dword ptr [rax+rax+00h]
0x1800152e2  mov     rcx, [rsp+1D8h]; this
0x1800152ea  test    eax, eax
0x1800152ec  jnz     loc_180015905
0x1800152f2  mov     rcx, [rsp+1D8h]; this
0x1800152fa  test    byte ptr [rsp+1D8h+var_188], 1
0x1800152ff  jnz     loc_180015919
0x180015305  mov     rdx, rbx
0x180015308  lea     rcx, [rsp+1D8h+Src]
0x180015310  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015315  nop
0x180015316  test    rbx, rbx
0x180015319  jz      short loc_180015358
0x18001531b  sub     rdi, rbx
0x18001531e  mov     rax, rbx
0x180015321  cmp     rdi, 1000h
0x180015328  jb      short loc_18001534C
0x18001532a  add     rdi, 27h ; '''
0x18001532e  mov     rbx, [rbx-8]
0x180015332  sub     rax, rbx
0x180015335  add     rax, 0FFFFFFFFFFFFFFF8h
0x180015339  cmp     rax, 1Fh
0x18001533d  jbe     short loc_18001534C
0x18001533f  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180015346  nop     dword ptr [rax+rax+00h]
0x18001534b  int     3; Trap to Debugger
0x18001534c  mov     rdx, rdi; struct std::nothrow_t *
0x18001534f  mov     rcx, rbx; void *
0x180015352  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180015357  nop
0x180015358  mov     r9, [rsi]
0x18001535b  xorps   xmm0, xmm0
0x18001535e  xor     eax, eax
0x180015360  movups  xmmword ptr [rsp+1D8h+var_70], xmm0
0x180015368  mov     [rsp+1D8h+var_60], rax
0x180015370  mov     [rsp+1D8h+var_58], ax
0x180015378  mov     rax, 0FFFFFFFFFFFFh
0x180015382  and     r9, rax
0x180015385  lea     r8, ?c_addressStringFormat@?1??to_wstring_macaddress@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z@4QBGB; "%012llX"
0x18001538c  mov     edx, 0Dh; unsigned __int64
0x180015391  lea     rcx, [rsp+1D8h+var_70]; unsigned __int16 *
0x180015399  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001539e  lea     rdx, [rsp+1D8h+var_70]
0x1800153a6  lea     rcx, [rsp+1D8h+var_150]
0x1800153ae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800153b3  nop
0x1800153b4  mov     rsi, 7FFFFFFFFFFFFFFEh
0x1800153be  mov     rax, rsi
0x1800153c1  mov     rbx, [rsp+1D8h+var_100]
0x1800153c9  sub     rax, rbx
0x1800153cc  cmp     rax, 1
0x1800153d0  jb      loc_180015931
0x1800153d6  lea     rax, [rsp+1D8h+Src]
0x1800153de  mov     edx, 7
0x1800153e3  cmp     [rsp+1D8h+var_F8], rdx
0x1800153eb  cmova   rax, [rsp+1D8h+Src]
0x1800153f4  mov     [rsp+1D8h+var_180], rax
0x1800153f9  xorps   xmm0, xmm0
0x1800153fc  movups  [rsp+1D8h+var_130], xmm0
0x180015404  xorps   xmm1, xmm1
0x180015407  movdqu  [rsp+1D8h+var_120], xmm1
0x180015410  lea     r13, [rbx+1]
0x180015414  mov     ecx, edx
0x180015416  lea     rdi, [rsp+1D8h+var_130]
0x18001541e  lea     r14d, [rdx+3]
0x180015422  cmp     r13, rdx
0x180015425  jbe     short loc_180015462
0x180015427  mov     rax, r13
0x18001542a  or      rax, rdx
0x18001542d  cmp     rax, rsi
0x180015430  jbe     short loc_180015437
0x180015432  mov     rax, rsi
0x180015435  jmp     short loc_18001543E
0x180015437  cmp     rax, r14
0x18001543a  cmovb   rax, r14
0x18001543e  mov     qword ptr [rsp+1D8h+var_188], rax
0x180015443  lea     rdx, [rsp+1D8h+var_188]
0x180015448  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18001544d  mov     rdi, rax
0x180015450  mov     qword ptr [rsp+1D8h+var_130], rax
0x180015458  mov     rcx, qword ptr [rsp+1D8h+var_188]
0x18001545d  mov     rax, [rsp+1D8h+var_180]
0x180015462  mov     qword ptr [rsp+1D8h+var_120], r13
0x18001546a  mov     qword ptr [rsp+1D8h+var_120+8], rcx
0x180015472  add     rbx, rbx
0x180015475  mov     r8, rbx; Size
0x180015478  mov     rdx, rax; Src
0x18001547b  mov     rcx, rdi; void *
0x18001547e  call    memcpy_0
0x180015483  mov     eax, dword ptr cs:psz; "\\"
0x180015489  mov     [rbx+rdi], ax
0x18001548d  xor     eax, eax
0x18001548f  mov     [rdi+r13*2], ax
0x180015494  lea     r8, aDevices; "Devices"
0x18001549b  lea     rdx, [rsp+1D8h+var_130]
0x1800154a3  lea     rcx, [rsp+1D8h+var_90]
0x1800154ab  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800154b0  nop
0x1800154b1  lea     r8, psz; "\\"
0x1800154b8  mov     rdx, rax
0x1800154bb  lea     rcx, [rsp+1D8h+var_B0]
0x1800154c3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800154c8  mov     rdi, rax
0x1800154cb  xorps   xmm0, xmm0
0x1800154ce  movups  [rsp+1D8h+var_170], xmm0
0x1800154d3  xorps   xmm1, xmm1
0x1800154d6  movdqu  [rsp+1D8h+var_160], xmm1
0x1800154dc  mov     rbx, [rax+10h]
0x1800154e0  mov     r13, qword ptr [rsp+1D8h+var_140]
0x1800154e8  lea     rdx, [rbx+r13]
0x1800154ec  mov     rax, [rax+18h]
0x1800154f0  sub     rax, rbx
0x1800154f3  mov     rcx, qword ptr [rsp+1D8h+var_140+8]
0x1800154fb  cmp     r13, rax
0x1800154fe  ja      short loc_180015570
0x180015500  cmp     rcx, [rdi+18h]
0x180015504  ja      short loc_180015570
0x180015506  movups  xmm0, xmmword ptr [rdi]
0x180015509  movups  [rsp+1D8h+var_170], xmm0
0x18001550e  movups  xmm1, xmmword ptr [rdi+10h]
0x180015512  movups  [rsp+1D8h+var_160], xmm1
0x180015517  xor     esi, esi
0x180015519  mov     [rdi+10h], rsi
0x18001551d  mov     qword ptr [rdi+18h], 7
0x180015525  mov     [rdi], si
0x180015528  lea     rax, [rsp+1D8h+var_170]
0x18001552d  cmp     qword ptr [rsp+1D8h+var_160+8], 7
0x180015536  cmova   rax, qword ptr [rsp+1D8h+var_170]
0x18001553c  lea     rdx, [rsp+1D8h+var_150]
0x180015544  cmp     rcx, 7
0x180015548  cmova   rdx, [rsp+1D8h+var_150]; Src
0x180015551  lea     rcx, [rax+rbx*2]; void *
0x180015555  lea     r8, ds:2[r13*2]; Size
0x18001555d  call    memcpy_0
0x180015562  lea     rax, [rbx+r13]
0x180015566  mov     qword ptr [rsp+1D8h+var_160], rax
0x18001556b  jmp     loc_18001568D
0x180015570  mov     rax, rcx
0x180015573  sub     rax, r13
0x180015576  cmp     rbx, rax
0x180015579  ja      short loc_1800155F3
0x18001557b  movups  xmm2, xmmword ptr [rsp+1D8h+var_150]
0x180015583  movups  [rsp+1D8h+var_170], xmm2
0x180015588  movups  xmm0, [rsp+1D8h+var_140]
0x180015590  movups  [rsp+1D8h+var_160], xmm0
0x180015595  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001559d  movdqu  [rsp+1D8h+var_140], xmm1
0x1800155a6  xor     eax, eax
0x1800155a8  mov     word ptr [rsp+1D8h+var_150], ax
0x1800155b0  movq    rsi, xmm2
0x1800155b5  lea     r14, [rbx+rbx]
0x1800155b9  lea     rcx, [r14+rsi]; void *
0x1800155bd  lea     r8, ds:2[r13*2]; Size
0x1800155c5  mov     rdx, rsi; Src
0x1800155c8  call    memmove_0
0x1800155cd  cmp     qword ptr [rdi+18h], 7
0x1800155d2  jbe     short loc_1800155D7
0x1800155d4  mov     rdi, [rdi]
0x1800155d7  mov     r8, r14; Size
0x1800155da  mov     rdx, rdi; Src
0x1800155dd  mov     rcx, rsi; void *
0x1800155e0  call    memcpy_0
0x1800155e5  lea     rax, [rbx+r13]
0x1800155e9  mov     qword ptr [rsp+1D8h+var_160], rax
0x1800155ee  jmp     loc_18001568B
0x1800155f3  mov     rax, rsi
0x1800155f6  sub     rax, rbx
0x1800155f9  cmp     rax, r13
0x1800155fc  jb      loc_180015937
0x180015602  mov     rax, rdx
0x180015605  or      rax, 7
0x180015609  cmp     rax, rsi
0x18001560c  ja      short loc_180015618
0x18001560e  mov     rsi, rax
0x180015611  cmp     rax, r14
0x180015614  cmovb   rsi, r14
0x180015618  mov     qword ptr [rsp+1D8h+var_188], rsi
0x18001561d  lea     rdx, [rsp+1D8h+var_188]
0x180015622  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180015627  mov     rsi, rax
0x18001562a  mov     qword ptr [rsp+1D8h+var_170], rax
0x18001562f  lea     rax, [rbx+r13]
0x180015633  mov     qword ptr [rsp+1D8h+var_160], rax
0x180015638  mov     rcx, qword ptr [rsp+1D8h+var_188]
0x18001563d  mov     qword ptr [rsp+1D8h+var_160+8], rcx
0x180015645  cmp     qword ptr [rdi+18h], 7
0x18001564a  jbe     short loc_18001564F
0x18001564c  mov     rdi, [rdi]
0x18001564f  add     rbx, rbx
0x180015652  mov     r8, rbx; Size
0x180015655  mov     rdx, rdi; Src
0x180015658  mov     rcx, rsi; void *
0x18001565b  call    memcpy_0
0x180015660  lea     rdx, [rsp+1D8h+var_150]
0x180015668  cmp     qword ptr [rsp+1D8h+var_140+8], 7
0x180015671  cmova   rdx, [rsp+1D8h+var_150]; Src
0x18001567a  lea     rcx, [rbx+rsi]; void *
0x18001567e  lea     r8, ds:2[r13*2]; Size
0x180015686  call    memcpy_0
0x18001568b  xor     esi, esi
0x18001568d  lea     r8, psz; "\\"
0x180015694  lea     rdx, [rsp+1D8h+var_170]
0x180015699  lea     rcx, [rsp+1D8h+var_D0]
0x1800156a1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800156a6  nop
0x1800156a7  lea     r8, aCachedservices; "CachedServices"
0x1800156ae  mov     rdx, rax
0x1800156b1  lea     rcx, [rsp+1D8h+lpSubKey]
0x1800156b9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800156be  nop
0x1800156bf  lea     rcx, [rsp+1D8h+var_D0]
0x1800156c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800156cc  nop
0x1800156cd  lea     rcx, [rsp+1D8h+var_170]
0x1800156d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
