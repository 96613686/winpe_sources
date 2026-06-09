# CWwanSvcNotificationManager::Activate(ushort const *,ushort const *,NOTIFICATION_USER_INPUT_DATA const *,ulong)

- ea: `0x1800295d0`
- end: `0x180029e0d`
- name: `?Activate@CWwanSvcNotificationManager@@UEAAJPEBG0PEBUNOTIFICATION_USER_INPUT_DATA@@K@Z`
- size: `2109`
- prototype: `__int64 __fastcall(CWwanSvcNotificationManager *this, const unsigned __int16 *, const unsigned __int16 *, const struct NOTIFICATION_USER_INPUT_DATA *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x180009ffc`
- `0x18001105c`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e0d0`
- `0x1800293b8`
- `0x1800295d0`
- `0x18002a014`
- `0x18002b068`
- `0x1800583ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800296dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002975e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029781`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800297a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800297c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029852`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002986b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029884`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800296dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002975e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029781`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800297a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800297c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029852`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002986b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029884`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180029bb4`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180029bb4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029a7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a68`
- `RPCRT4!UuidFromStringW` at `0x180029bc6`
- `RPCRT4!UuidFromStringW` at `0x180029bc6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180029a75`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180029db7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180029a75`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180029db7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180029a94`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180029a94`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180029cd0`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x180029cd0`

## string_xrefs

- `0x180029861`: `SIM_REMOVE_SS`
- `0x18002987a`: `OPEN_SETTING`
- `0x180029af2`: `WwanOpenHandle failed with hr=0x%08x.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWwanSvcNotificationManager::Activate(
        CWwanSvcNotificationManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct NOTIFICATION_USER_INPUT_DATA *a4)
{
  const unsigned __int16 *v6; // r9
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // r8
  __int128 *v11; // rcx
  __int128 *v12; // rcx
  __int128 *v13; // rcx
  __int128 *v14; // rcx
  __int64 v15; // rax
  __int128 *v16; // rbx
  __int64 v17; // rax
  int v18; // ebx
  int v19; // eax
  unsigned int EmbeddedSlotIndex; // eax
  int v21; // ebx
  int v22; // ebx
  __int128 *v23; // r9
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 **v27; // rcx
  int v28; // ebx
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rdi
  DWORD LastError; // ebx
  int v34; // eax
  signed int v35; // ebx
  const struct _tlgProvider_t *v36; // rax
  int v37; // r8d
  int v38; // r9d
  __int128 *v39; // rbx
  BOOL v40; // ecx
  const struct _tlgProvider_t *v41; // rax
  int v42; // r8d
  int v43; // r9d
  int v44; // eax
  signed int v45; // ebx
  const struct _tlgProvider_t *v46; // rax
  int v47; // r8d
  int v48; // r9d
  __int64 v50; // [rsp+20h] [rbp-E0h]
  __int64 v51; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v52[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v54; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v55[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h]
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+88h] [rbp-78h] BYREF
  int v59; // [rsp+8Ch] [rbp-74h] BYREF
  int v60; // [rsp+90h] [rbp-70h] BYREF
  int v61; // [rsp+94h] [rbp-6Ch] BYREF
  __int128 v62; // [rsp+98h] [rbp-68h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-58h]
  UUID Uuid; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h]
  __int128 v66; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v67; // [rsp+F0h] [rbp-10h]
  __int128 v68; // [rsp+100h] [rbp+0h] BYREF
  __m128i v69; // [rsp+110h] [rbp+10h]
  _OWORD v70[2]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 StringUuid[40]; // [rsp+140h] [rbp+40h] BYREF

  *(_OWORD *)v52 = 0;
  v53 = 0;
  Uuid = 0;
  v65 = 0;
  std::vector<unsigned short>::resize(v52);
  std::vector<unsigned short>::resize(&Uuid);
  v6 = a3;
  if ( !a3 )
    v6 = &dword_1800684AC;
  StringCchPrintfW(v52[0], v52[1] - v52[0], L"Activate the toast from action center with invokedArgs=%s", v6);
  StringCchPrintfW(
    *(unsigned __int16 **)&Uuid.Data1,
    (__int64)(*(_QWORD *)Uuid.Data4 - *(_QWORD *)&Uuid.Data1) >> 1,
    L"%S(%d):%s",
    "CWwanSvcNotificationManager::Activate",
    467,
    v52[0]);
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 4u )
  {
    v57 = *(_QWORD *)&Uuid.Data1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v7,
      (unsigned int)&word_180075FDE,
      v8,
      v9,
      (__int64)&v57);
  }
  std::vector<unsigned short>::~vector<unsigned short>(&Uuid);
  std::vector<unsigned short>::~vector<unsigned short>(v52);
  if ( !(unsigned int)_o__wcsicmp(a2, aWindowsSystemt) )
  {
    v62 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v62) = 0;
    v70[0] = 0;
    v70[1] = si128;
    LOWORD(v70[0]) = 0;
    v66 = 0;
    v67 = 0u;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    std::wstring::_Construct<1,unsigned short const *>(&v66, a3);
    ParseInvokedArgs(&v66, &v62, v70);
    v11 = &v62;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v62;
    if ( !(unsigned int)_o__wcsicmp(v11, L"LpaSvc") )
      goto LABEL_75;
    v12 = &v62;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = (__int128 *)v62;
    if ( !(unsigned int)_o__wcsicmp(v12, L"ImsSvc") )
      goto LABEL_75;
    v13 = &v62;
    if ( si128.m128i_i64[1] > 7uLL )
      v13 = (__int128 *)v62;
    if ( !(unsigned int)_o__wcsicmp(v13, L"UtkSvc") )
      goto LABEL_75;
    v14 = &v62;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = (__int128 *)v62;
    if ( (unsigned int)_o__wcsicmp(v14, L"WwanSvc") )
      goto LABEL_75;
    v66 = 0;
    v67 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v66) = 0;
    v68 = 0;
    v69 = v67;
    LOWORD(v68) = 0;
    v57 = -1;
    v59 = 0;
    v61 = 0;
    v60 = 0;
    Uuid = 0;
    v15 = std::wstring::wstring(v55, v70);
    ParseInvokedArgs(v15, &v66, &v68);
    v16 = &v68;
    if ( v69.m128i_i64[1] > 7uLL )
      v16 = (__int128 *)v68;
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    if ( v17 )
    {
      if ( (unsigned int)_o__wcsicmp(v16, L"SIM_INSERT_SS") )
      {
        if ( (unsigned int)_o__wcsicmp(v16, L"SIM_REMOVE_SS") )
        {
          v19 = _o__wcsicmp(v16, L"OPEN_SETTING");
          v18 = 1;
          if ( !v19 )
            v18 = 4;
        }
        else
        {
          v18 = 3;
        }
      }
      else
      {
        v18 = 2;
      }
    }
    else
    {
      v18 = 0;
    }
    EmbeddedSlotIndex = getEmbeddedSlotIndex();
    v58 = EmbeddedSlotIndex;
    v21 = v18 - 2;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        if ( v22 != 1 )
        {
          *(_OWORD *)v55 = 0;
          v56 = 0;
          *(_OWORD *)v52 = 0;
          v53 = 0;
          std::vector<unsigned short>::resize(v55);
          std::vector<unsigned short>::resize(v52);
          v23 = &v68;
          if ( v69.m128i_i64[1] > 7uLL )
            v23 = (__int128 *)v68;
          StringCchPrintfW(v55[0], v55[1] - v55[0], L"The action %s is wrong", v23);
          LODWORD(v50) = 541;
          StringCchPrintfW(v52[0], v52[1] - v52[0], L"%S(%d):%s", "CWwanSvcNotificationManager::Activate", v50, v55[0]);
          v24 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v24 > 2u )
          {
            v54 = v52[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v24,
              (unsigned int)byte_180075F39,
              v25,
              v26,
              (__int64)&v54);
          }
          std::vector<unsigned short>::~vector<unsigned short>(v52);
          v27 = v55;
          goto LABEL_71;
        }
        v28 = anonymous_namespace_::LaunchNetworkSettingsByUri();
        if ( v28 >= 0 )
        {
LABEL_72:
          if ( v57 != -1 )
            WwanCloseHandle(v57, 0);
          std::wstring::~wstring(&v68);
          std::wstring::~wstring(&v66);
LABEL_75:
          std::wstring::~wstring(v70);
          std::wstring::~wstring(&v62);
          return 0;
        }
        *(_OWORD *)v52 = 0;
        v53 = 0;
        *(_OWORD *)v55 = 0;
        v56 = 0;
        std::vector<unsigned short>::resize(v52);
        std::vector<unsigned short>::resize(v55);
        StringCchPrintfW(
          v52[0],
          v52[1] - v52[0],
          L"NetworkUiUtilities::LaunchNetworkSettingsMobileBroadband failed with hr=0x%08x.",
          (unsigned int)v28);
        LODWORD(v50) = 537;
        StringCchPrintfW(v55[0], v55[1] - v55[0], L"%S(%d):%s", "CWwanSvcNotificationManager::Activate", v50, v52[0]);
        v29 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v29 > 2u )
        {
          v54 = v55[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v29,
            (unsigned int)word_180075F5A,
            v30,
            v31,
            (__int64)&v54);
        }
LABEL_70:
        std::vector<unsigned short>::~vector<unsigned short>(v55);
        v27 = v52;
LABEL_71:
        std::vector<unsigned short>::~vector<unsigned short>(v27);
        goto LABEL_72;
      }
    }
    else
    {
      v58 = ((_BYTE)EmbeddedSlotIndex - 1) & 1;
    }
    v32 = v57;
    if ( v57 != -1 )
    {
      LastError = GetLastError();
      WwanCloseHandle(v32, 0);
      SetLastError(LastError);
    }
    v57 = -1;
    v34 = WwanOpenHandle(1, 0, &v59, &v57);
    v35 = v34;
    if ( v34 > 0 )
      v35 = (unsigned __int16)v34 | 0x80070000;
    if ( v35 < 0 )
    {
      *(_OWORD *)v52 = 0;
      v53 = 0;
      *(_OWORD *)v55 = 0;
      v56 = 0;
      std::vector<unsigned short>::resize(v52);
      std::vector<unsigned short>::resize(v55);
      StringCchPrintfW(v52[0], v52[1] - v52[0], L"WwanOpenHandle failed with hr=0x%08x.", (unsigned int)v35);
      LODWORD(v50) = 510;
      StringCchPrintfW(v55[0], v55[1] - v55[0], L"%S(%d):%s", "CWwanSvcNotificationManager::Activate", v50, v52[0]);
      v36 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v36 > 2u )
      {
        v54 = v55[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v36,
          (unsigned int)byte_180075FBD,
          v37,
          v38,
          (__int64)&v54);
      }
      std::vector<unsigned short>::~vector<unsigned short>(v55);
      std::vector<unsigned short>::~vector<unsigned short>(v52);
    }
    v39 = &v66;
    if ( v67.m128i_i64[1] > 7uLL )
      v39 = (__int128 *)v66;
    memset_0(StringUuid, 0, 0x4Au);
    Uuid = 0;
    if ( v39 && *(_WORD *)v39 )
    {
      if ( (unsigned int)_o_wcsncpy_s(StringUuid, 37, v39) )
        goto LABEL_62;
      v40 = UuidFromStringW(StringUuid, &Uuid) == 0;
    }
    else
    {
      v40 = 0;
    }
    if ( v40 )
    {
LABEL_65:
      v44 = WwanSetInterface(v57, &Uuid, 47, 4);
      v45 = v44;
      if ( v44 > 0 )
        v45 = (unsigned __int16)v44 | 0x80070000;
      if ( v45 >= 0 )
        goto LABEL_72;
      *(_OWORD *)v52 = 0;
      v53 = 0;
      *(_OWORD *)v55 = 0;
      v56 = 0;
      std::vector<unsigned short>::resize(v52);
      std::vector<unsigned short>::resize(v55);
      StringCchPrintfW(
        v52[0],
        v52[1] - v52[0],
        L"WwanSetInterface failed with hr=0x%08x.",
        (unsigned int)v45,
        &v58,
        &v61,
        &v60,
        0);
      LODWORD(v51) = 529;
      StringCchPrintfW(v55[0], v55[1] - v55[0], L"%S(%d):%s", "CWwanSvcNotificationManager::Activate", v51, v52[0]);
      v46 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v46 > 2u )
      {
        v54 = v55[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v46,
          (unsigned int)byte_180075F7B,
          v47,
          v48,
          (__int64)&v54);
      }
      goto LABEL_70;
    }
LABEL_62:
    *(_OWORD *)v52 = 0;
    v53 = 0;
    *(_OWORD *)v55 = 0;
    v56 = 0;
    std::vector<unsigned short>::resize(v52);
    std::vector<unsigned short>::resize(v55);
    StringCchPrintfW(v52[0], v52[1] - v52[0], L"StringToGuid failed");
    LODWORD(v50) = 515;
    StringCchPrintfW(v55[0], v55[1] - v55[0], L"%S(%d):%s", "CWwanSvcNotificationManager::Activate", v50, v52[0]);
    v41 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v41 > 2u )
    {
      v54 = v55[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v41,
        (unsigned int)&dword_180075F9C,
        v42,
        v43,
        (__int64)&v54);
    }
    std::vector<unsigned short>::~vector<unsigned short>(v55);
    std::vector<unsigned short>::~vector<unsigned short>(v52);
    goto LABEL_65;
  }
  return 0;
}

```

## disassembly

```asm
0x1800295d0  mov     [rsp-8+arg_0], rbx
0x1800295d5  push    rbp
0x1800295d6  push    rsi
0x1800295d7  push    rdi
0x1800295d8  push    r12
0x1800295da  push    r13
0x1800295dc  lea     rbp, [rsp-0A0h]
0x1800295e4  sub     rsp, 1A0h
0x1800295eb  mov     rax, cs:__security_cookie
0x1800295f2  xor     rax, rsp
0x1800295f5  mov     [rbp+0C0h+var_30], rax
0x1800295fc  mov     rbx, r8
0x1800295ff  mov     rdi, rdx
0x180029602  xorps   xmm0, xmm0
0x180029605  movdqu  xmmword ptr [rsp+1C0h+var_180], xmm0
0x18002960b  xor     esi, esi
0x18002960d  mov     [rsp+1C0h+var_170], rsi
0x180029612  movdqu  xmmword ptr [rbp+0C0h+Uuid.Data1], xmm0
0x180029617  mov     [rbp+0C0h+var_F0], rsi
0x18002961b  lea     rcx, [rsp+1C0h+var_180]
0x180029620  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180029625  lea     rcx, [rbp+0C0h+Uuid]
0x180029629  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18002962e  lea     rax, dword_1800684AC
0x180029635  mov     r9, rbx
0x180029638  test    rbx, rbx
0x18002963b  cmovz   r9, rax
0x18002963f  mov     rdx, [rsp+1C0h+var_180+8]
0x180029644  mov     rcx, [rsp+1C0h+var_180]; unsigned __int16 *
0x180029649  sub     rdx, rcx
0x18002964c  sar     rdx, 1; unsigned __int64
0x18002964f  lea     r8, aActivateTheToa; "Activate the toast from action center w"...
0x180029656  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002965b  mov     rdx, qword ptr [rbp+0C0h+Uuid.Data4]
0x18002965f  mov     rcx, qword ptr [rbp+0C0h+Uuid.Data1]; unsigned __int16 *
0x180029663  sub     rdx, rcx
0x180029666  sar     rdx, 1; unsigned __int64
0x180029669  mov     rax, [rsp+1C0h+var_180]
0x18002966e  mov     [rsp+1C0h+var_198], rax
0x180029673  mov     dword ptr [rsp+1C0h+var_1A0], 1D3h
0x18002967b  lea     r13, aCwwansvcnotifi; "CWwanSvcNotificationManager::Activate"
0x180029682  mov     r9, r13
0x180029685  lea     r8, aSDS; "%S(%d):%s"
0x18002968c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029691  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180029696  mov     ecx, [rax]
0x180029698  cmp     ecx, 4
0x18002969b  jbe     short loc_1800296BE
0x18002969d  mov     rcx, qword ptr [rbp+0C0h+Uuid.Data1]
0x1800296a1  mov     [rbp+0C0h+var_140], rcx
0x1800296a5  lea     rcx, [rbp+0C0h+var_140]
0x1800296a9  mov     [rsp+1C0h+var_1A0], rcx
0x1800296ae  lea     rdx, word_180075FDE
0x1800296b5  mov     rcx, rax
0x1800296b8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800296bd  nop
0x1800296be  lea     rcx, [rbp+0C0h+Uuid]
0x1800296c2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800296c7  nop
0x1800296c8  lea     rcx, [rsp+1C0h+var_180]
0x1800296cd  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800296d2  lea     rdx, aWindowsSystemt; "Windows.SystemToast.Wwansvc"
0x1800296d9  mov     rcx, rdi
0x1800296dc  call    cs:__imp__o__wcsicmp
0x1800296e2  test    eax, eax
0x1800296e4  jnz     loc_180029DE5
0x1800296ea  xorps   xmm0, xmm0
0x1800296ed  movups  [rbp+0C0h+var_128], xmm0
0x1800296f1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800296f9  movdqu  [rbp+0C0h+var_118], xmm1
0x1800296fe  mov     word ptr [rbp+0C0h+var_128], si
0x180029702  movups  [rbp+0C0h+var_A0], xmm0
0x180029706  movdqu  [rbp+0C0h+var_90], xmm1
0x18002970b  mov     word ptr [rbp+0C0h+var_A0], si
0x18002970f  movups  [rbp+0C0h+var_E0], xmm0
0x180029713  mov     qword ptr [rbp+0C0h+var_D0], rsi
0x180029717  mov     qword ptr [rbp+0C0h+var_D0+8], rsi
0x18002971b  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002971f  mov     r8, r12
0x180029722  inc     r8
0x180029725  cmp     [rbx+r8*2], si
0x18002972a  jnz     short loc_180029722
0x18002972c  mov     rdx, rbx
0x18002972f  lea     rcx, [rbp+0C0h+var_E0]
0x180029733  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180029738  lea     r8, [rbp+0C0h+var_A0]
0x18002973c  lea     rdx, [rbp+0C0h+var_128]
0x180029740  lea     rcx, [rbp+0C0h+var_E0]
0x180029744  call    ?ParseInvokedArgs@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@1@Z; ParseInvokedArgs(std::wstring,std::wstring &,std::wstring &)
0x180029749  lea     rcx, [rbp+0C0h+var_128]
0x18002974d  cmp     qword ptr [rbp+0C0h+var_118+8], 7
0x180029752  cmova   rcx, qword ptr [rbp+0C0h+var_128]
0x180029757  lea     rdx, aLpasvc; "LpaSvc"
0x18002975e  call    cs:__imp__o__wcsicmp
0x180029764  test    eax, eax
0x180029766  jz      loc_180029DD2
0x18002976c  lea     rcx, [rbp+0C0h+var_128]
0x180029770  cmp     qword ptr [rbp+0C0h+var_118+8], 7
0x180029775  cmova   rcx, qword ptr [rbp+0C0h+var_128]
0x18002977a  lea     rdx, aImssvc; "ImsSvc"
0x180029781  call    cs:__imp__o__wcsicmp
0x180029787  test    eax, eax
0x180029789  jz      loc_180029DD2
0x18002978f  lea     rcx, [rbp+0C0h+var_128]
0x180029793  cmp     qword ptr [rbp+0C0h+var_118+8], 7
0x180029798  cmova   rcx, qword ptr [rbp+0C0h+var_128]
0x18002979d  lea     rdx, aUtksvc; "UtkSvc"
0x1800297a4  call    cs:__imp__o__wcsicmp
0x1800297aa  test    eax, eax
0x1800297ac  jz      loc_180029DD2
0x1800297b2  lea     rcx, [rbp+0C0h+var_128]
0x1800297b6  cmp     qword ptr [rbp+0C0h+var_118+8], 7
0x1800297bb  cmova   rcx, qword ptr [rbp+0C0h+var_128]
0x1800297c0  lea     rdx, aWwansvc; "WwanSvc"
0x1800297c7  call    cs:__imp__o__wcsicmp
0x1800297cd  test    eax, eax
0x1800297cf  jnz     loc_180029DD2
0x1800297d5  xorps   xmm0, xmm0
0x1800297d8  movups  [rbp+0C0h+var_E0], xmm0
0x1800297dc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800297e4  movdqu  [rbp+0C0h+var_D0], xmm1
0x1800297e9  mov     word ptr [rbp+0C0h+var_E0], si
0x1800297ed  movups  [rbp+0C0h+var_C0], xmm0
0x1800297f1  movdqu  [rbp+0C0h+var_B0], xmm1
0x1800297f6  mov     word ptr [rbp+0C0h+var_C0], si
0x1800297fa  mov     [rbp+0C0h+var_140], r12
0x1800297fe  mov     [rbp+0C0h+var_134], esi
0x180029801  mov     [rbp+0C0h+var_12C], esi
0x180029804  mov     [rbp+0C0h+var_130], esi
0x180029807  movups  xmmword ptr [rbp+0C0h+Uuid.Data1], xmm0
0x18002980b  lea     rdx, [rbp+0C0h+var_A0]
0x18002980f  lea     rcx, [rsp+1C0h+var_160]
0x180029814  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180029819  lea     r8, [rbp+0C0h+var_C0]
0x18002981d  lea     rdx, [rbp+0C0h+var_E0]
0x180029821  mov     rcx, rax
0x180029824  call    ?ParseInvokedArgs@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@1@Z; ParseInvokedArgs(std::wstring,std::wstring &,std::wstring &)
0x180029829  lea     rbx, [rbp+0C0h+var_C0]
0x18002982d  cmp     qword ptr [rbp+0C0h+var_B0+8], 7
0x180029832  cmova   rbx, qword ptr [rbp+0C0h+var_C0]
0x180029837  mov     rax, r12
0x18002983a  inc     rax
0x18002983d  cmp     [rbx+rax*2], si
0x180029841  jnz     short loc_18002983A
0x180029843  test    rax, rax
0x180029846  jz      short loc_180029899
0x180029848  lea     rdx, aSimInsertSs; "SIM_INSERT_SS"
0x18002984f  mov     rcx, rbx
0x180029852  call    cs:__imp__o__wcsicmp
0x180029858  test    eax, eax
0x18002985a  jnz     short loc_180029861
0x18002985c  lea     ebx, [rax+2]
0x18002985f  jmp     short loc_18002989B
0x180029861  lea     rdx, aSimRemoveSs; "SIM_REMOVE_SS"
0x180029868  mov     rcx, rbx
0x18002986b  call    cs:__imp__o__wcsicmp
0x180029871  test    eax, eax
0x180029873  jnz     short loc_18002987A
0x180029875  lea     ebx, [rax+3]
0x180029878  jmp     short loc_18002989B
0x18002987a  lea     rdx, aOpenSetting; "OPEN_SETTING"
0x180029881  mov     rcx, rbx
0x180029884  call    cs:__imp__o__wcsicmp
0x18002988a  mov     ebx, 1
0x18002988f  test    eax, eax
0x180029891  lea     eax, [rbx+3]
0x180029894  cmovz   ebx, eax
0x180029897  jmp     short loc_18002989B
0x180029899  mov     ebx, esi
0x18002989b  call    ?getEmbeddedSlotIndex@@YAKXZ; getEmbeddedSlotIndex(void)
0x1800298a0  mov     [rbp+0C0h+var_138], eax
0x1800298a3  sub     ebx, 2
0x1800298a6  jz      loc_180029A57
0x1800298ac  sub     ebx, 1
0x1800298af  jz      loc_180029A5F
0x1800298b5  cmp     ebx, 1
0x1800298b8  jz      loc_18002998B
0x1800298be  xorps   xmm0, xmm0
0x1800298c1  movdqu  xmmword ptr [rsp+1C0h+var_160], xmm0
0x1800298c7  mov     [rsp+1C0h+var_150], rsi
0x1800298cc  movdqu  xmmword ptr [rsp+1C0h+var_180], xmm0
0x1800298d2  mov     [rsp+1C0h+var_170], rsi
0x1800298d7  lea     rcx, [rsp+1C0h+var_160]
0x1800298dc  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800298e1  lea     rcx, [rsp+1C0h+var_180]
0x1800298e6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800298eb  lea     r9, [rbp+0C0h+var_C0]
0x1800298ef  cmp     qword ptr [rbp+0C0h+var_B0+8], 7
0x1800298f4  cmova   r9, qword ptr [rbp+0C0h+var_C0]
0x1800298f9  mov     rdx, [rsp+1C0h+var_160+8]
0x1800298fe  mov     rcx, [rsp+1C0h+var_160]; unsigned __int16 *
0x180029903  sub     rdx, rcx
0x180029906  sar     rdx, 1; unsigned __int64
0x180029909  lea     r8, aTheActionSIsWr; "The action %s is wrong"
0x180029910  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029915  mov     rdx, [rsp+1C0h+var_180+8]
0x18002991a  mov     rcx, [rsp+1C0h+var_180]; unsigned __int16 *
0x18002991f  sub     rdx, rcx
0x180029922  sar     rdx, 1; unsigned __int64
0x180029925  mov     rax, [rsp+1C0h+var_160]
0x18002992a  mov     [rsp+1C0h+var_198], rax
0x18002992f  mov     dword ptr [rsp+1C0h+var_1A0], 21Dh
0x180029937  mov     r9, r13
0x18002993a  lea     r8, aSDS; "%S(%d):%s"
0x180029941  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029946  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18002994b  mov     ecx, [rax]
0x18002994d  cmp     ecx, 2
0x180029950  jbe     short loc_180029976
0x180029952  mov     rcx, [rsp+1C0h+var_180]
0x180029957  mov     [rsp+1C0h+var_168], rcx
0x18002995c  lea     rcx, [rsp+1C0h+var_168]
0x180029961  mov     [rsp+1C0h+var_1A0], rcx
0x180029966  lea     rdx, byte_180075F39
0x18002996d  mov     rcx, rax
0x180029970  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180029975  nop
0x180029976  lea     rcx, [rsp+1C0h+var_180]
0x18002997b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180029980  nop
0x180029981  lea     rcx, [rsp+1C0h+var_160]
0x180029986  jmp     loc_180029DA6
0x18002998b  call    _anonymous_namespace___LaunchNetworkSettingsByUri
0x180029990  mov     ebx, eax
0x180029992  test    eax, eax
0x180029994  jns     loc_180029DAC
0x18002999a  xorps   xmm0, xmm0
0x18002999d  movdqu  xmmword ptr [rsp+1C0h+var_180], xmm0
0x1800299a3  mov     [rsp+1C0h+var_170], rsi
0x1800299a8  movdqu  xmmword ptr [rsp+1C0h+var_160], xmm0
0x1800299ae  mov     [rsp+1C0h+var_150], rsi
0x1800299b3  lea     rcx, [rsp+1C0h+var_180]
0x1800299b8  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800299bd  lea     rcx, [rsp+1C0h+var_160]
0x1800299c2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800299c7  mov     rdx, [rsp+1C0h+var_180+8]
0x1800299cc  mov     rcx, [rsp+1C0h+var_180]; unsigned __int16 *
0x1800299d1  sub     rdx, rcx
0x1800299d4  sar     rdx, 1; unsigned __int64
0x1800299d7  mov     r9d, ebx
0x1800299da  lea     r8, aNetworkuiutili; "NetworkUiUtilities::LaunchNetworkSettin"...
0x1800299e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800299e6  mov     rdx, [rsp+1C0h+var_160+8]
0x1800299eb  mov     rcx, [rsp+1C0h+var_160]; unsigned __int16 *
0x1800299f0  sub     rdx, rcx
0x1800299f3  sar     rdx, 1; unsigned __int64
0x1800299f6  mov     rax, [rsp+1C0h+var_180]
0x1800299fb  mov     [rsp+1C0h+var_198], rax
0x180029a00  mov     dword ptr [rsp+1C0h+var_1A0], 219h
0x180029a08  mov     r9, r13
0x180029a0b  lea     r8, aSDS; "%S(%d):%s"
0x180029a12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029a17  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180029a1c  mov     ecx, [rax]
0x180029a1e  cmp     ecx, 2
0x180029a21  jbe     short loc_180029A47
0x180029a23  mov     rcx, [rsp+1C0h+var_160]
0x180029a28  mov     [rsp+1C0h+var_168], rcx
0x180029a2d  lea     rcx, [rsp+1C0h+var_168]
0x180029a32  mov     [rsp+1C0h+var_1A0], rcx
0x180029a37  lea     rdx, word_180075F5A
0x180029a3e  mov     rcx, rax
0x180029a41  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180029a46  nop
0x180029a47  lea     rcx, [rsp+1C0h+var_160]
0x180029a4c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180029a51  nop
0x180029a52  jmp     loc_180029DA1
0x180029a57  dec     eax
0x180029a59  and     eax, 1
0x180029a5c  mov     [rbp+0C0h+var_138], eax
0x180029a5f  mov     rdi, [rbp+0C0h+var_140]
0x180029a63  cmp     rdi, r12
0x180029a66  jz      short loc_180029A83
0x180029a68  call    cs:__imp_GetLastError
0x180029a6e  mov     ebx, eax
0x180029a70  xor     edx, edx
0x180029a72  mov     rcx, rdi
0x180029a75  call    cs:__imp_WwanCloseHandle
0x180029a7b  mov     ecx, ebx; dwErrCode
0x180029a7d  call    cs:__imp_SetLastError
0x180029a83  mov     [rbp+0C0h+var_140], r12
0x180029a87  lea     r9, [rbp+0C0h+var_140]
0x180029a8b  lea     r8, [rbp+0C0h+var_134]
0x180029a8f  xor     edx, edx
0x180029a91  lea     ecx, [rdx+1]
0x180029a94  call    cs:__imp_WwanOpenHandle
0x180029a9a  mov     ebx, eax
0x180029a9c  mov     edi, 80070000h
0x180029aa1  test    eax, eax
0x180029aa3  jle     short loc_180029AAA
0x180029aa5  movzx   ebx, ax
0x180029aa8  or      ebx, edi
0x180029aaa  test    ebx, ebx
0x180029aac  jns     loc_180029B74
0x180029ab2  xorps   xmm0, xmm0
0x180029ab5  movdqu  xmmword ptr [rsp+1C0h+var_180], xmm0
0x180029abb  mov     [rsp+1C0h+var_170], rsi
0x180029ac0  movdqu  xmmword ptr [rsp+1C0h+var_160], xmm0
0x180029ac6  mov     [rsp+1C0h+var_150], rsi
  ... truncated ...
```
