# CWwanTranslator::_DisableCurrentDmProfile(_GUID const &,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18003d268`
- end: `0x18003d851`
- name: `?_DisableCurrentDmProfile@CWwanTranslator@@AEAAJAEBU_GUID@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1513`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180033e24`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001ae38`
- `0x18001dd10`
- `0x180028f20`
- `0x18003d268`
- `0x1800588d0`

## import_xrefs

- `WwanPrfl!WwanProfileGenerateXml` at `0x18003d750`
- `WwanPrfl!WwanProfileGenerateXml` at `0x18003d750`
- `WwanPrfl!WwanProfileLoadXml` at `0x18003d55e`
- `WwanPrfl!WwanProfileLoadXml` at `0x18003d55e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003d4cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003d6ed`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003d4cc`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003d6ed`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d581`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d6df`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d77c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d7e6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d845`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d581`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d6df`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d77c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d7e6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18003d845`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003d381`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003d381`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfileList` at `0x18003d3cc`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfileList` at `0x18003d3cc`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18003d52f`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x18003d52f`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetDMConfigProfile` at `0x18003d7a6`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetDMConfigProfile` at `0x18003d7a6`

## string_xrefs

- `0x18003d7bf`: `WwanSetDMConfigProfile failed with reason %d.`
- `0x18003d419`: `No DM config Profile to disable.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWwanTranslator::_DisableCurrentDmProfile(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int DMConfigProfileList; // eax
  const struct _tlgProvider_t *v13; // rax
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // esi
  unsigned int *v17; // rbx
  unsigned int DMConfigProfile; // eax
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rbx
  const wchar_t *v21; // rcx
  size_t v22; // r8
  const struct _tlgProvider_t *v23; // rax
  int v24; // r8d
  int v25; // r9d
  unsigned int Xml; // eax
  int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  unsigned int *v31; // [rsp+20h] [rbp-E0h]
  char *v32; // [rsp+28h] [rbp-D8h]
  char *v33; // [rsp+28h] [rbp-D8h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v35; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v36[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v38[3]; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int16 *v39[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v41[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v46[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v48; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t S2[1538]; // [rsp+D0h] [rbp-30h] BYREF
  int v50; // [rsp+CD4h] [rbp+BD4h]
  int v51; // [rsp+D54h] [rbp+C54h]
  int v52; // [rsp+1328h] [rbp+1228h]
  __int64 v53; // [rsp+1330h] [rbp+1230h]
  __int64 v54; // [rsp+1338h] [rbp+1238h]
  wil::details::in1diag3 *retaddr; // [rsp+19C8h] [rbp+18C8h]

  v48 = (unsigned __int16 *)a4;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  *(_OWORD *)v39 = 0;
  v40 = 0;
  std::vector<unsigned short>::resize(v44);
  std::vector<unsigned short>::resize(v39);
  StringCchPrintfW(v44[0], v44[1] - v44[0], L"Enter");
  HIDWORD(v32) = HIDWORD(v44[0]);
  LODWORD(v31) = 2799;
  StringCchPrintfW(v39[0], v39[1] - v39[0], L"%S(%d):%s", "CWwanTranslator::_DisableCurrentDmProfile");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(unsigned __int16 **)v36 = v39[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)byte_180076731,
      v8,
      v9,
      (__int64)v36);
  }
  std::vector<unsigned short>::~vector<unsigned short>(v39);
  std::vector<unsigned short>::~vector<unsigned short>(v44);
  v34 = 0;
  v43 = 0;
  v10 = WwanOpenHandle(1, 0, &v43, &v34);
  if ( v10 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xAF1,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)v10,
            (unsigned int)v31);
    goto LABEL_39;
  }
  v44[0] = (unsigned __int16 *)&v34;
  LOBYTE(v44[1]) = 1;
  v35 = 0;
  DMConfigProfileList = WwanGetDMConfigProfileList(v34, a2, &v35);
  if ( DMConfigProfileList == 1168 )
  {
    *(_OWORD *)v41 = 0;
    v42 = 0;
    *(_OWORD *)v39 = 0;
    v40 = 0;
    std::vector<unsigned short>::resize(v41);
    std::vector<unsigned short>::resize(v39);
    StringCchPrintfW(v41[0], v41[1] - v41[0], L"No DM config Profile to disable.");
    LODWORD(v31) = 2808;
    StringCchPrintfW(v39[0], v39[1] - v39[0], L"%S(%d):%s", "CWwanTranslator::_DisableCurrentDmProfile", v31, v41[0]);
    v13 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v13 > 5u )
    {
      *(unsigned __int16 **)v36 = v39[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v13,
        (unsigned int)&dword_180076754,
        v14,
        v15,
        (__int64)v36);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v39);
    std::vector<unsigned short>::~vector<unsigned short>(v41);
LABEL_38:
    WwanCloseHandle(v34, 0);
    v11 = 0;
    goto LABEL_39;
  }
  if ( DMConfigProfileList )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xAFD,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)DMConfigProfileList,
            (unsigned int)v31);
    goto LABEL_11;
  }
  v39[0] = (unsigned __int16 *)&v35;
  LOBYTE(v39[1]) = 1;
  v16 = 0;
  v17 = v35;
  if ( !*v35 )
  {
LABEL_34:
    *(_OWORD *)v46 = 0;
    v47 = 0;
    *(_OWORD *)v41 = 0;
    v42 = 0;
    std::vector<unsigned short>::resize(v46);
    std::vector<unsigned short>::resize(v41);
    StringCchPrintfW(v46[0], v46[1] - v46[0], L"Exit");
    LODWORD(v31) = 2871;
    StringCchPrintfW(v41[0], v41[1] - v41[0], L"%S(%d):%s", "CWwanTranslator::_DisableCurrentDmProfile", v31, v46[0]);
    v23 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v23 > 5u )
    {
      v48 = v41[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v23,
        (unsigned int)&word_18007670E,
        v24,
        v25,
        (__int64)&v48);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v41);
    std::vector<unsigned short>::~vector<unsigned short>(v46);
    if ( v35 )
      WwanFreeMemory(v35);
    goto LABEL_38;
  }
  while ( 1 )
  {
    *(_QWORD *)v36 = 0;
    memset_0(S2, 0, 0x18B0u);
    v37 = 0;
    DMConfigProfile = WwanGetDMConfigProfile(v34, a2, &v17[129 * v16 + 1], v36);
    if ( DMConfigProfile )
    {
      v30 = 2830;
      goto LABEL_49;
    }
    LODWORD(v32) = 1;
    v31 = &v37;
    DMConfigProfile = WwanProfileLoadXml(S2, *(_QWORD *)v36, 0, 0);
    if ( DMConfigProfile )
    {
      v30 = 2832;
LABEL_49:
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v30,
              (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
              (const char *)DMConfigProfile,
              (unsigned int)v31);
      goto LABEL_50;
    }
    if ( v37 )
    {
      v11 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB12,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
        (const char *)0x80004005LL,
        (int)&v37);
      goto LABEL_50;
    }
    if ( *(_QWORD *)v36 )
      WwanFreeMemory(*(_QWORD *)v36);
    if ( v53 == *a3 && v54 == a3[1] && !v50 && v52 )
    {
      v19 = *(_QWORD *)(a4 + 16);
      if ( !v19 )
        break;
      v20 = -1;
      do
        ++v20;
      while ( S2[v20] );
      if ( *(_QWORD *)(a4 + 24) <= 7u )
        v21 = (const wchar_t *)a4;
      else
        v21 = *(const wchar_t **)a4;
      v22 = *(_QWORD *)(a4 + 16);
      if ( v20 < v19 )
        v22 = v20;
      if ( wmemcmp(v21, S2, v22) || v19 < v20 || v19 > v20 )
        break;
    }
    ++v16;
    v17 = v35;
    if ( v16 >= *v35 )
      goto LABEL_34;
  }
  v52 = 0;
  v51 = 1;
  *(_QWORD *)&v38[1] = 0;
  Xml = WwanProfileGenerateXml(S2, 2, &v38[1], 1);
  if ( Xml )
  {
    v28 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xB29,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)Xml,
            (unsigned int)&v37);
  }
  else
  {
    v38[0] = 0;
    v29 = WwanSetDMConfigProfile(v34, a2, *(_QWORD *)&v38[1], 1, v38, v32);
    if ( !v29 )
    {
      WwanFreeMemory(*(_QWORD *)&v38[1]);
      goto LABEL_34;
    }
    LODWORD(v33) = v38[0];
    v28 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)0xB30,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)v29,
            (unsigned int)"WwanSetDMConfigProfile failed with reason %d.",
            v33);
  }
  v11 = v28;
  WwanFreeMemory(*(_QWORD *)&v38[1]);
LABEL_50:
  if ( v35 )
    WwanFreeMemory(v35);
LABEL_11:
  WwanCloseHandle(v34, 0);
LABEL_39:
  std::wstring::~wstring(a4);
  return v11;
}

```

## disassembly

```asm
0x18003d268  mov     [rsp-8+arg_0], rbx
0x18003d26d  push    rbp
0x18003d26e  push    rsi
0x18003d26f  push    rdi
0x18003d270  push    r12
0x18003d272  push    r13
0x18003d274  push    r14
0x18003d276  push    r15
0x18003d278  lea     rbp, [rsp-1890h]
0x18003d280  mov     eax, 1990h
0x18003d285  call    _alloca_probe
0x18003d28a  sub     rsp, rax
0x18003d28d  mov     rax, cs:__security_cookie
0x18003d294  xor     rax, rsp
0x18003d297  mov     [rbp+18C0h+var_40], rax
0x18003d29e  mov     r14, r9
0x18003d2a1  mov     r12, r8
0x18003d2a4  mov     r15, rdx
0x18003d2a7  mov     [rbp+18C0h+var_1900], r9
0x18003d2ab  xorps   xmm0, xmm0
0x18003d2ae  movdqu  xmmword ptr [rbp+18C0h+var_1930], xmm0
0x18003d2b3  xor     r13d, r13d
0x18003d2b6  mov     [rbp+18C0h+var_1920], r13
0x18003d2ba  movdqu  xmmword ptr [rsp+19C0h+var_1968], xmm0
0x18003d2c0  mov     [rsp+19C0h+var_1958], r13
0x18003d2c5  lea     rcx, [rbp+18C0h+var_1930]
0x18003d2c9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d2ce  lea     rcx, [rsp+19C0h+var_1968]
0x18003d2d3  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d2d8  mov     rdx, [rbp+18C0h+var_1930+8]
0x18003d2dc  mov     rcx, [rbp+18C0h+var_1930]; unsigned __int16 *
0x18003d2e0  sub     rdx, rcx
0x18003d2e3  sar     rdx, 1; unsigned __int64
0x18003d2e6  lea     r8, aEnter; "Enter"
0x18003d2ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d2f2  mov     rdx, [rsp+19C0h+var_1968+8]
0x18003d2f7  mov     rcx, [rsp+19C0h+var_1968]; unsigned __int16 *
0x18003d2fc  sub     rdx, rcx
0x18003d2ff  sar     rdx, 1; unsigned __int64
0x18003d302  mov     rax, [rbp+18C0h+var_1930]
0x18003d306  mov     [rsp+19C0h+var_1998], rax
0x18003d30b  mov     [rsp+19C0h+var_19A0], 0AEFh
0x18003d313  lea     r9, aCwwantranslato_9; "CWwanTranslator::_DisableCurrentDmProfi"...
0x18003d31a  lea     r8, aSDS; "%S(%d):%s"
0x18003d321  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d326  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003d32b  mov     ecx, [rax]
0x18003d32d  cmp     ecx, 5
0x18003d330  jbe     short loc_18003D356
0x18003d332  mov     rcx, [rsp+19C0h+var_1968]
0x18003d337  mov     qword ptr [rsp+19C0h+var_1980], rcx
0x18003d33c  lea     rcx, [rsp+19C0h+var_1980]
0x18003d341  mov     qword ptr [rsp+19C0h+var_19A0], rcx; unsigned int
0x18003d346  lea     rdx, byte_180076731
0x18003d34d  mov     rcx, rax
0x18003d350  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003d355  nop
0x18003d356  lea     rcx, [rsp+19C0h+var_1968]
0x18003d35b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d360  nop
0x18003d361  lea     rcx, [rbp+18C0h+var_1930]
0x18003d365  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d36a  mov     [rsp+19C0h+var_1990], r13
0x18003d36f  mov     [rbp+18C0h+var_1938], r13d
0x18003d373  lea     r9, [rsp+19C0h+var_1990]
0x18003d378  lea     r8, [rbp+18C0h+var_1938]
0x18003d37c  xor     edx, edx
0x18003d37e  lea     ecx, [rdx+1]
0x18003d381  call    cs:__imp_WwanOpenHandle
0x18003d387  test    eax, eax
0x18003d389  jz      short loc_18003D3AD
0x18003d38b  mov     rcx, [rbp+18C8h]; this
0x18003d392  mov     r9d, eax; char *
0x18003d395  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003d39c  mov     edx, 0AF1h; void *
0x18003d3a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003d3a6  mov     ebx, eax
0x18003d3a8  jmp     loc_18003D6F6
0x18003d3ad  lea     rax, [rsp+19C0h+var_1990]
0x18003d3b2  mov     [rbp+18C0h+var_1930], rax
0x18003d3b6  mov     byte ptr [rbp+18C0h+var_1930+8], 1
0x18003d3ba  mov     [rsp+19C0h+var_1988], r13
0x18003d3bf  lea     r8, [rsp+19C0h+var_1988]
0x18003d3c4  mov     rdx, r15
0x18003d3c7  mov     rcx, [rsp+19C0h+var_1990]
0x18003d3cc  call    cs:__imp_WwanGetDMConfigProfileList
0x18003d3d2  cmp     eax, 490h
0x18003d3d7  jnz     loc_18003D4A4
0x18003d3dd  xorps   xmm0, xmm0
0x18003d3e0  movdqu  xmmword ptr [rsp+19C0h+var_1950], xmm0
0x18003d3e6  mov     [rbp+18C0h+var_1940], r13
0x18003d3ea  movdqu  xmmword ptr [rsp+19C0h+var_1968], xmm0
0x18003d3f0  mov     [rsp+19C0h+var_1958], r13
0x18003d3f5  lea     rcx, [rsp+19C0h+var_1950]
0x18003d3fa  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d3ff  lea     rcx, [rsp+19C0h+var_1968]
0x18003d404  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d409  mov     rdx, [rsp+19C0h+var_1950+8]
0x18003d40e  mov     rcx, [rsp+19C0h+var_1950]; unsigned __int16 *
0x18003d413  sub     rdx, rcx
0x18003d416  sar     rdx, 1; unsigned __int64
0x18003d419  lea     r8, aNoDmConfigProf; "No DM config Profile to disable."
0x18003d420  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d425  mov     rdx, [rsp+19C0h+var_1968+8]
0x18003d42a  mov     rcx, [rsp+19C0h+var_1968]; unsigned __int16 *
0x18003d42f  sub     rdx, rcx
0x18003d432  sar     rdx, 1; unsigned __int64
0x18003d435  mov     rax, [rsp+19C0h+var_1950]
0x18003d43a  mov     [rsp+19C0h+var_1998], rax
0x18003d43f  mov     [rsp+19C0h+var_19A0], 0AF8h
0x18003d447  lea     r9, aCwwantranslato_9; "CWwanTranslator::_DisableCurrentDmProfi"...
0x18003d44e  lea     r8, aSDS; "%S(%d):%s"
0x18003d455  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d45a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003d45f  mov     ecx, [rax]
0x18003d461  cmp     ecx, 5
0x18003d464  jbe     short loc_18003D48A
0x18003d466  mov     rcx, [rsp+19C0h+var_1968]
0x18003d46b  mov     qword ptr [rsp+19C0h+var_1980], rcx
0x18003d470  lea     rcx, [rsp+19C0h+var_1980]
0x18003d475  mov     qword ptr [rsp+19C0h+var_19A0], rcx
0x18003d47a  lea     rdx, dword_180076754
0x18003d481  mov     rcx, rax
0x18003d484  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003d489  nop
0x18003d48a  lea     rcx, [rsp+19C0h+var_1968]
0x18003d48f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d494  nop
0x18003d495  lea     rcx, [rsp+19C0h+var_1950]
0x18003d49a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d49f  jmp     loc_18003D6E6
0x18003d4a4  test    eax, eax
0x18003d4a6  jz      short loc_18003D4D7
0x18003d4a8  mov     rcx, [rbp+18C8h]; this
0x18003d4af  mov     r9d, eax; char *
0x18003d4b2  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18003d4b9  mov     edx, 0AFDh; void *
0x18003d4be  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003d4c3  mov     ebx, eax
0x18003d4c5  xor     edx, edx
0x18003d4c7  mov     rcx, [rsp+19C0h+var_1990]
0x18003d4cc  call    cs:__imp_WwanCloseHandle
0x18003d4d2  jmp     loc_18003D6F6
0x18003d4d7  lea     rax, [rsp+19C0h+var_1988]
0x18003d4dc  mov     [rsp+19C0h+var_1968], rax
0x18003d4e1  mov     byte ptr [rsp+19C0h+var_1968+8], 1
0x18003d4e6  mov     esi, r13d
0x18003d4e9  mov     rbx, [rsp+19C0h+var_1988]
0x18003d4ee  cmp     [rbx], r13d
0x18003d4f1  jbe     loc_18003D61B
0x18003d4f7  mov     qword ptr [rsp+19C0h+var_1980], r13
0x18003d4fc  xor     edx, edx; Val
0x18003d4fe  mov     r8d, 18B0h; Size
0x18003d504  lea     rcx, [rbp+18C0h+S2]; void *
0x18003d508  call    memset_0
0x18003d50d  mov     [rsp+19C0h+var_1978], r13d
0x18003d512  mov     eax, esi
0x18003d514  imul    r8, rax, 204h
0x18003d51b  add     r8, 4
0x18003d51f  add     r8, rbx
0x18003d522  lea     r9, [rsp+19C0h+var_1980]
0x18003d527  mov     rdx, r15
0x18003d52a  mov     rcx, [rsp+19C0h+var_1990]
0x18003d52f  call    cs:__imp_WwanGetDMConfigProfile
0x18003d535  test    eax, eax
0x18003d537  jnz     loc_18003D81A
0x18003d53d  mov     dword ptr [rsp+19C0h+var_1998], 1
0x18003d545  lea     rax, [rsp+19C0h+var_1978]
0x18003d54a  mov     qword ptr [rsp+19C0h+var_19A0], rax; int
0x18003d54f  xor     r9d, r9d
0x18003d552  xor     r8d, r8d
0x18003d555  mov     rdx, qword ptr [rsp+19C0h+var_1980]
0x18003d55a  lea     rcx, [rbp+18C0h+S2]
0x18003d55e  call    cs:__imp_WwanProfileLoadXml
0x18003d564  test    eax, eax
0x18003d566  jnz     loc_18003D813
0x18003d56c  cmp     [rsp+19C0h+var_1978], r13d
0x18003d571  jnz     loc_18003D7F1
0x18003d577  mov     rcx, qword ptr [rsp+19C0h+var_1980]
0x18003d57c  test    rcx, rcx
0x18003d57f  jz      short loc_18003D587
0x18003d581  call    cs:__imp_WwanFreeMemory
0x18003d587  mov     rax, [rbp+18C0h+var_690]
0x18003d58e  cmp     rax, [r12]
0x18003d592  jnz     short loc_18003D60C
0x18003d594  mov     rax, [rbp+18C0h+var_688]
0x18003d59b  cmp     rax, [r12+8]
0x18003d5a0  jnz     short loc_18003D60C
0x18003d5a2  cmp     [rbp+18C0h+var_CEC], r13d
0x18003d5a9  jnz     short loc_18003D60C
0x18003d5ab  cmp     [rbp+18C0h+var_698], r13d
0x18003d5b2  jz      short loc_18003D60C
0x18003d5b4  mov     rdi, [r14+10h]
0x18003d5b8  test    rdi, rdi
0x18003d5bb  jz      loc_18003D72A
0x18003d5c1  lea     rax, [rbp+18C0h+S2]
0x18003d5c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003d5c9  inc     rbx
0x18003d5cc  cmp     [rax+rbx*2], r13w
0x18003d5d1  jnz     short loc_18003D5C9
0x18003d5d3  cmp     qword ptr [r14+18h], 7
0x18003d5d8  jbe     short loc_18003D5DF
0x18003d5da  mov     rcx, [r14]
0x18003d5dd  jmp     short loc_18003D5E2
0x18003d5df  mov     rcx, r14; S1
0x18003d5e2  mov     r8, rdi
0x18003d5e5  cmp     rbx, rdi
0x18003d5e8  cmovb   r8, rbx; N
0x18003d5ec  lea     rdx, [rbp+18C0h+S2]; S2
0x18003d5f0  call    wmemcmp
0x18003d5f5  test    eax, eax
0x18003d5f7  jnz     loc_18003D72A
0x18003d5fd  cmp     rdi, rbx
0x18003d600  jb      loc_18003D72A
0x18003d606  ja      loc_18003D72A
0x18003d60c  inc     esi
0x18003d60e  mov     rbx, [rsp+19C0h+var_1988]
0x18003d613  cmp     esi, [rbx]
0x18003d615  jb      loc_18003D4F7
0x18003d61b  xorps   xmm0, xmm0
0x18003d61e  movdqu  xmmword ptr [rbp+18C0h+var_1918], xmm0
0x18003d623  mov     [rbp+18C0h+var_1908], r13
0x18003d627  movdqu  xmmword ptr [rsp+19C0h+var_1950], xmm0
0x18003d62d  mov     [rbp+18C0h+var_1940], r13
0x18003d631  lea     rcx, [rbp+18C0h+var_1918]
0x18003d635  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d63a  lea     rcx, [rsp+19C0h+var_1950]
0x18003d63f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d644  mov     rdx, [rbp+18C0h+var_1918+8]
0x18003d648  mov     rcx, [rbp+18C0h+var_1918]; unsigned __int16 *
0x18003d64c  sub     rdx, rcx
0x18003d64f  sar     rdx, 1; unsigned __int64
0x18003d652  lea     r8, aExit; "Exit"
0x18003d659  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d65e  mov     rdx, [rsp+19C0h+var_1950+8]
0x18003d663  mov     rcx, [rsp+19C0h+var_1950]; unsigned __int16 *
0x18003d668  sub     rdx, rcx
0x18003d66b  sar     rdx, 1; unsigned __int64
0x18003d66e  mov     rax, [rbp+18C0h+var_1918]
0x18003d672  mov     [rsp+19C0h+var_1998], rax
0x18003d677  mov     [rsp+19C0h+var_19A0], 0B37h
0x18003d67f  lea     r9, aCwwantranslato_9; "CWwanTranslator::_DisableCurrentDmProfi"...
0x18003d686  lea     r8, aSDS; "%S(%d):%s"
0x18003d68d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003d692  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003d697  mov     ecx, [rax]
0x18003d699  cmp     ecx, 5
0x18003d69c  jbe     short loc_18003D6C0
0x18003d69e  mov     rcx, [rsp+19C0h+var_1950]
0x18003d6a3  mov     [rbp+18C0h+var_1900], rcx
0x18003d6a7  lea     rcx, [rbp+18C0h+var_1900]
0x18003d6ab  mov     qword ptr [rsp+19C0h+var_19A0], rcx
0x18003d6b0  lea     rdx, word_18007670E
0x18003d6b7  mov     rcx, rax
0x18003d6ba  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003d6bf  nop
0x18003d6c0  lea     rcx, [rsp+19C0h+var_1950]
0x18003d6c5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d6ca  nop
0x18003d6cb  lea     rcx, [rbp+18C0h+var_1918]
0x18003d6cf  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d6d4  nop
0x18003d6d5  mov     rcx, [rsp+19C0h+var_1988]
0x18003d6da  test    rcx, rcx
0x18003d6dd  jz      short loc_18003D6E6
0x18003d6df  call    cs:__imp_WwanFreeMemory
0x18003d6e5  nop
0x18003d6e6  xor     edx, edx
0x18003d6e8  mov     rcx, [rsp+19C0h+var_1990]
0x18003d6ed  call    cs:__imp_WwanCloseHandle
0x18003d6f3  mov     ebx, r13d
0x18003d6f6  mov     rcx, r14
0x18003d6f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d6fe  mov     eax, ebx
0x18003d700  mov     rcx, [rbp+18C0h+var_40]
0x18003d707  xor     rcx, rsp; StackCookie
0x18003d70a  call    __security_check_cookie
0x18003d70f  mov     rbx, [rsp+19C0h+arg_0]
0x18003d717  add     rsp, 1990h
0x18003d71e  pop     r15
0x18003d720  pop     r14
0x18003d722  pop     r13
0x18003d724  pop     r12
0x18003d726  pop     rdi
0x18003d727  pop     rsi
0x18003d728  pop     rbp
0x18003d729  retn
0x18003d72a  mov     [rbp+18C0h+var_698], r13d
0x18003d731  mov     ebx, 1
0x18003d736  mov     [rbp+18C0h+var_C6C], ebx
0x18003d73c  mov     qword ptr [rsp+19C0h+var_1974+4], r13
0x18003d741  mov     r9d, ebx
0x18003d744  lea     r8, [rsp+19C0h+var_1974+4]
0x18003d749  lea     edx, [rbx+1]
0x18003d74c  lea     rcx, [rbp+18C0h+S2]
0x18003d750  call    cs:__imp_WwanProfileGenerateXml
0x18003d756  test    eax, eax
0x18003d758  jz      short loc_18003D787
0x18003d75a  mov     rcx, [rbp+18C8h]; this
0x18003d761  mov     r9d, eax; char *
  ... truncated ...
```
