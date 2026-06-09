# AOMDHandler::EventThresholdMet(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string_view<ushort,std::char_traits<ushort>>,ulong,bool &)

- ea: `0x18000b238`
- end: `0x18000bfd6`
- name: `?EventThresholdMet@AOMDHandler@@AEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0KAEA_N@Z`
- size: `3486`
- prototype: `__int64 __fastcall(const wchar_t *, LPCWSTR *, __int64, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aed0`

## callees

- `0x180001008`
- `0x180002e50`
- `0x180002e74`
- `0x180003940`
- `0x180004470`
- `0x180004b84`
- `0x180004bfc`
- `0x180004c74`
- `0x180005ef0`
- `0x180006210`
- `0x180006e1c`
- `0x18000772c`
- `0x180007818`
- `0x180007ee4`
- `0x18000b238`
- `0x18000e168`
- `0x18000e7ec`
- `0x1800109b4`
- `0x1800109d4`
- `0x18001672c`
- `0x180019e08`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000bcf5`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000bcf5`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000bce1`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18000bce1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bc88`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000bc88`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18000bcc7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoull` at `0x18000bcc7`
- `KERNEL32!GetLastError` at `0x18000b40c`
- `KERNEL32!GetLastError` at `0x18000b4ae`
- `KERNEL32!GetLastError` at `0x18000b7bc`
- `KERNEL32!GetLastError` at `0x18000beb3`
- `KERNEL32!GetLastError` at `0x18000bec0`
- `KERNEL32!GetLastError` at `0x18000b40c`
- `KERNEL32!GetLastError` at `0x18000b4ae`
- `KERNEL32!GetLastError` at `0x18000b7bc`
- `KERNEL32!GetLastError` at `0x18000beb3`
- `KERNEL32!GetLastError` at `0x18000bec0`
- `KERNEL32!SetLastError` at `0x18000b421`
- `KERNEL32!SetLastError` at `0x18000b421`
- `wevtapi!EvtRender` at `0x18000b4a0`
- `wevtapi!EvtRender` at `0x18000b5b3`
- `wevtapi!EvtRender` at `0x18000b7ae`
- `wevtapi!EvtRender` at `0x18000b8cf`
- `wevtapi!EvtRender` at `0x18000b4a0`
- `wevtapi!EvtRender` at `0x18000b5b3`
- `wevtapi!EvtRender` at `0x18000b7ae`
- `wevtapi!EvtRender` at `0x18000b8cf`
- `wevtapi!EvtNext` at `0x18000b453`
- `wevtapi!EvtNext` at `0x18000b453`
- `wevtapi!EvtQuery` at `0x18000b2ad`
- `wevtapi!EvtQuery` at `0x18000b2ad`
- `wevtapi!EvtClose` at `0x18000b383`
- `wevtapi!EvtClose` at `0x18000b38d`
- `wevtapi!EvtClose` at `0x18000b418`
- `wevtapi!EvtClose` at `0x18000b4df`
- `wevtapi!EvtClose` at `0x18000b4f9`
- `wevtapi!EvtClose` at `0x18000b503`
- `wevtapi!EvtClose` at `0x18000b50d`
- `wevtapi!EvtClose` at `0x18000b5e6`
- `wevtapi!EvtClose` at `0x18000b600`
- `wevtapi!EvtClose` at `0x18000b60a`
- `wevtapi!EvtClose` at `0x18000b614`
- `wevtapi!EvtClose` at `0x18000b65a`
- `wevtapi!EvtClose` at `0x18000b674`
- `wevtapi!EvtClose` at `0x18000b67e`
- `wevtapi!EvtClose` at `0x18000b688`
- `wevtapi!EvtClose` at `0x18000b7f8`
- `wevtapi!EvtClose` at `0x18000b812`
- `wevtapi!EvtClose` at `0x18000b81c`
- `wevtapi!EvtClose` at `0x18000b826`
- `wevtapi!EvtClose` at `0x18000b90d`
- `wevtapi!EvtClose` at `0x18000b927`
- `wevtapi!EvtClose` at `0x18000b931`
- `wevtapi!EvtClose` at `0x18000b93b`
- `wevtapi!EvtClose` at `0x18000b9f9`
- `wevtapi!EvtClose` at `0x18000ba13`
- `wevtapi!EvtClose` at `0x18000ba1d`
- `wevtapi!EvtClose` at `0x18000ba27`
- `wevtapi!EvtClose` at `0x18000bf25`
- `wevtapi!EvtClose` at `0x18000bf3f`
- `wevtapi!EvtClose` at `0x18000bf49`
- `wevtapi!EvtClose` at `0x18000bf53`
- `wevtapi!EvtClose` at `0x18000bf7b`
- `wevtapi!EvtClose` at `0x18000b383`
- `wevtapi!EvtClose` at `0x18000b38d`
- `wevtapi!EvtClose` at `0x18000b418`
- `wevtapi!EvtClose` at `0x18000b4df`
- `wevtapi!EvtClose` at `0x18000b4f9`
- `wevtapi!EvtClose` at `0x18000b503`
- `wevtapi!EvtClose` at `0x18000b50d`
- `wevtapi!EvtClose` at `0x18000b5e6`
- `wevtapi!EvtClose` at `0x18000b600`
- `wevtapi!EvtClose` at `0x18000b60a`
- `wevtapi!EvtClose` at `0x18000b614`
- `wevtapi!EvtClose` at `0x18000b65a`
- `wevtapi!EvtClose` at `0x18000b674`
- `wevtapi!EvtClose` at `0x18000b67e`
- `wevtapi!EvtClose` at `0x18000b688`
- `wevtapi!EvtClose` at `0x18000b7f8`
- `wevtapi!EvtClose` at `0x18000b812`
- `wevtapi!EvtClose` at `0x18000b81c`
- `wevtapi!EvtClose` at `0x18000b826`
- `wevtapi!EvtClose` at `0x18000b90d`
- `wevtapi!EvtClose` at `0x18000b927`
- `wevtapi!EvtClose` at `0x18000b931`
- `wevtapi!EvtClose` at `0x18000b93b`
- `wevtapi!EvtClose` at `0x18000b9f9`
- `wevtapi!EvtClose` at `0x18000ba13`
- `wevtapi!EvtClose` at `0x18000ba1d`
- `wevtapi!EvtClose` at `0x18000ba27`
- `wevtapi!EvtClose` at `0x18000bf25`
- `wevtapi!EvtClose` at `0x18000bf3f`
- `wevtapi!EvtClose` at `0x18000bf49`
- `wevtapi!EvtClose` at `0x18000bf53`
- `wevtapi!EvtClose` at `0x18000bf7b`
- `wevtapi!EvtCreateRenderContext` at `0x18000b2d5`
- `wevtapi!EvtCreateRenderContext` at `0x18000b348`
- `wevtapi!EvtCreateRenderContext` at `0x18000b2d5`
- `wevtapi!EvtCreateRenderContext` at `0x18000b348`

## pseudocode

```c
__int64 __fastcall AOMDHandler::EventThresholdMet(
        const wchar_t *a1,
        LPCWSTR *a2,
        __int64 a3,
        unsigned int a4,
        bool *a5)
{
  __int64 result; // rax
  HANDLE v7; // r15
  int v8; // r12d
  EVT_HANDLE v9; // rdi
  const char *v10; // r9
  EVT_HANDLE RenderContext; // rsi
  const char *v12; // r9
  EVT_HANDLE v13; // rbx
  const char *v14; // r9
  unsigned int v15; // ebx
  char *v16; // rax
  unsigned int v17; // r13d
  DWORD v18; // r14d
  const char *v19; // r9
  unsigned int v20; // r14d
  char *v21; // r14
  PVOID v22; // rcx
  size_t v23; // r15
  const char *v24; // r9
  const struct _tlgProvider_t *v25; // rax
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rcx
  char *v29; // rax
  const char *v30; // r9
  char *v31; // r14
  PVOID v32; // rcx
  size_t v33; // r15
  const char *v34; // r9
  const struct _tlgProvider_t *v35; // rax
  int v36; // r8d
  int v37; // r9d
  const WCHAR *v38; // rcx
  char *v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  LPCWSTR *v42; // rcx
  const struct _tlgProvider_t *v43; // rax
  int v44; // r8d
  int v45; // r9d
  const WCHAR *v46; // rax
  __int128 *v47; // rdx
  __int64 v48; // r8
  _DWORD *v49; // rax
  _DWORD *v50; // r13
  const wchar_t *v51; // r14
  unsigned __int64 v52; // r15
  __int64 v53; // rcx
  const WCHAR *v54; // rax
  const WCHAR *v55; // rax
  signed int v56; // eax
  unsigned int LastError; // ebx
  int Flags; // [rsp+20h] [rbp-198h]
  int Flagsa; // [rsp+20h] [rbp-198h]
  char v60; // [rsp+40h] [rbp-178h]
  HANDLE Events; // [rsp+48h] [rbp-170h] BYREF
  int v62; // [rsp+50h] [rbp-168h]
  int v63; // [rsp+54h] [rbp-164h] BYREF
  PVOID Buffer[2]; // [rsp+58h] [rbp-160h] BYREF
  char *v65; // [rsp+68h] [rbp-150h]
  PVOID v66[2]; // [rsp+70h] [rbp-148h] BYREF
  char *v67; // [rsp+80h] [rbp-138h]
  DWORD BufferUsed; // [rsp+88h] [rbp-130h] BYREF
  DWORD v69; // [rsp+8Ch] [rbp-12Ch] BYREF
  DWORD v70; // [rsp+90h] [rbp-128h] BYREF
  unsigned int v71; // [rsp+94h] [rbp-124h]
  DWORD PropertyCount; // [rsp+98h] [rbp-120h] BYREF
  wchar_t *EndPtr; // [rsp+A0h] [rbp-118h] BYREF
  DWORD Returned; // [rsp+A8h] [rbp-110h] BYREF
  const wchar_t *v75; // [rsp+B0h] [rbp-108h] BYREF
  EVT_HANDLE v76; // [rsp+B8h] [rbp-100h]
  bool *v77; // [rsp+C0h] [rbp-F8h]
  _QWORD v78[3]; // [rsp+D0h] [rbp-E8h] BYREF
  LPCWSTR ValuePaths[2]; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v80; // [rsp+F8h] [rbp-C0h]
  __int64 v81; // [rsp+100h] [rbp-B8h]
  __int128 v82; // [rsp+108h] [rbp-B0h] BYREF
  __int128 v83; // [rsp+118h] [rbp-A0h]
  __int128 v84; // [rsp+128h] [rbp-90h] BYREF
  __int64 v85; // [rsp+138h] [rbp-80h]
  __int64 v86; // [rsp+140h] [rbp-78h]
  wchar_t *String[2]; // [rsp+148h] [rbp-70h] BYREF
  __int64 v88; // [rsp+158h] [rbp-60h]
  unsigned __int64 v89; // [rsp+160h] [rbp-58h]
  _BYTE v90[32]; // [rsp+168h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  result = a4;
  v71 = a4;
  v75 = a1;
  v77 = a5;
  v7 = 0;
  v8 = 0;
  v62 = 0;
  *a5 = 0;
  if ( !a4 )
    return result;
  v9 = EvtQuery(0, *a2, *(LPCWSTR *)a3, 0x201u);
  v78[2] = v9;
  if ( !v9 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x124,
             (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
             v10);
  RenderContext = EvtCreateRenderContext(1u, &::ValuePaths, 0);
  v78[0] = RenderContext;
  if ( !RenderContext )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x127,
                  (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                  v12);
    EvtClose(v9);
    return LastError;
  }
  v13 = 0;
  v76 = 0;
  if ( *(_QWORD *)(a3 + 8) == 90
    && !wmemcmp(
          *(const wchar_t **)a3,
          L"*[System[Provider[@Name='Microsoft-Windows-WER-SystemErrorReporting'] and (EventID=1001)]]",
          0x5Au) )
  {
    ValuePaths[0] = L"Event/System/EventID";
    ValuePaths[1] = L"Event/EventData/Data[@Name='param1']";
    v13 = EvtCreateRenderContext(2u, ValuePaths, 0);
    v76 = v13;
    if ( !v13 )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x13B,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
              v14);
      EvtClose(RenderContext);
      EvtClose(v9);
      return v15;
    }
    v60 = 1;
  }
  else
  {
    v60 = 0;
  }
  v16 = (char *)operator new(0x10u);
  Buffer[0] = v16;
  v65 = v16 + 16;
  *(_OWORD *)v16 = 0;
  Buffer[1] = v16 + 16;
  EndPtr = 0;
  std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&EndPtr);
  BufferUsed = 0;
  Returned = 0;
  v17 = 0;
  v63 = 0;
  for ( Events = 0; ; v7 = Events )
  {
    if ( v7 )
    {
      v18 = GetLastError();
      EvtClose(v7);
      SetLastError(v18);
    }
    Events = 0;
    if ( !EvtNext(v9, 1u, &Events, 0x7D0u, 0, &Returned) )
      break;
    PropertyCount = 0;
    if ( EvtRender(
           RenderContext,
           Events,
           0,
           LODWORD(Buffer[1]) - LODWORD(Buffer[0]),
           Buffer[0],
           &BufferUsed,
           &PropertyCount) )
    {
      goto LABEL_34;
    }
    if ( GetLastError() != 122 )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x14B,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
              v19);
      if ( Events )
        EvtClose(Events);
      std::vector<unsigned char>::~vector<unsigned char>(Buffer);
      if ( v13 )
        EvtClose(v13);
LABEL_65:
      EvtClose(RenderContext);
      EvtClose(v9);
      return v20;
    }
    v21 = (char *)Buffer[1];
    v22 = Buffer[0];
    if ( (PVOID)BufferUsed >= (PVOID)((char *)Buffer[1] - (char *)Buffer[0]) )
    {
      if ( (PVOID)BufferUsed <= (PVOID)((char *)Buffer[1] - (char *)Buffer[0]) )
        goto LABEL_28;
      if ( BufferUsed > (unsigned __int64)(v65 - (char *)Buffer[0]) )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(Buffer, BufferUsed);
        LODWORD(v21) = Buffer[1];
        v22 = Buffer[0];
        goto LABEL_28;
      }
      v23 = BufferUsed - (unsigned __int64)((char *)Buffer[1] - (char *)Buffer[0]);
      memset_0(Buffer[1], 0, v23);
      v21 += v23;
      v22 = Buffer[0];
    }
    else
    {
      v21 = (char *)Buffer[0] + BufferUsed;
    }
    Buffer[1] = v21;
LABEL_28:
    if ( !EvtRender(RenderContext, Events, 0, (_DWORD)v21 - (_DWORD)v22, v22, &BufferUsed, &PropertyCount) )
    {
      v20 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x151,
              (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
              v24);
      if ( Events )
        EvtClose(Events);
      std::vector<unsigned char>::~vector<unsigned char>(Buffer);
      if ( v13 )
        EvtClose(v13);
      goto LABEL_65;
    }
LABEL_34:
    if ( *((_DWORD *)Buffer[0] + 3) != 17 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x155,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)0x8007000DLL,
        Flags);
      if ( Events )
        EvtClose(Events);
      std::vector<unsigned char>::~vector<unsigned char>(Buffer);
      if ( v13 )
        EvtClose(v13);
      EvtClose(RenderContext);
      EvtClose(v9);
      return 2147942413LL;
    }
    if ( *(_QWORD *)Buffer[0] < *((_QWORD *)v75 + 11) )
    {
      v25 = TlgHelper::Provider();
      v28 = *(unsigned int *)v25;
      if ( (unsigned int)v28 > 4 )
      {
        v28 = *((_QWORD *)v25 + 2);
        if ( (v28 & 2) != 0 )
        {
          v28 = *((_QWORD *)v25 + 3) & 2LL;
          if ( v28 == *((_QWORD *)v25 + 3) )
          {
            v75 = L"EventThresholdMet_ReachedLookbackLimit";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v25,
              (unsigned int)byte_180029F35,
              v26,
              v27,
              (__int64)&v75);
          }
        }
      }
      goto LABEL_134;
    }
    if ( !v60 )
      goto LABEL_124;
    *(_OWORD *)v66 = 0;
    v67 = 0;
    v29 = (char *)operator new(0x20u);
    v66[0] = v29;
    v67 = v29 + 32;
    *(_OWORD *)v29 = 0;
    *((_OWORD *)v29 + 1) = 0;
    v66[1] = v29 + 32;
    ValuePaths[0] = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(ValuePaths);
    v69 = 0;
    v70 = 0;
    if ( !EvtRender(v13, Events, 0, LODWORD(v66[1]) - LODWORD(v66[0]), v66[0], &v69, &v70) )
    {
      if ( GetLastError() != 122 )
      {
        v20 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x168,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v30);
        std::vector<unsigned char>::~vector<unsigned char>(v66);
        if ( Events )
          EvtClose(Events);
        std::vector<unsigned char>::~vector<unsigned char>(Buffer);
        if ( v13 )
          EvtClose(v13);
        goto LABEL_65;
      }
      v31 = (char *)v66[1];
      v32 = v66[0];
      if ( (PVOID)v69 < (PVOID)((char *)v66[1] - (char *)v66[0]) )
      {
        v31 = (char *)v66[0] + v69;
        goto LABEL_59;
      }
      if ( (PVOID)v69 > (PVOID)((char *)v66[1] - (char *)v66[0]) )
      {
        if ( v69 <= (unsigned __int64)(v67 - (char *)v66[0]) )
        {
          v33 = v69 - (unsigned __int64)((char *)v66[1] - (char *)v66[0]);
          memset_0(v66[1], 0, v33);
          v31 += v33;
          v32 = v66[0];
LABEL_59:
          v66[1] = v31;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v66, v69);
          LODWORD(v31) = v66[1];
          v32 = v66[0];
        }
      }
      if ( !EvtRender(v13, Events, 0, (_DWORD)v31 - (_DWORD)v32, v32, &v69, &v70) )
      {
        v20 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x16E,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v34);
        std::vector<unsigned char>::~vector<unsigned char>(v66);
        if ( Events )
          EvtClose(Events);
        std::vector<unsigned char>::~vector<unsigned char>(Buffer);
        if ( v13 )
          EvtClose(v13);
        goto LABEL_65;
      }
    }
    if ( v70 < 2 )
    {
      v35 = TlgHelper::Provider();
      if ( *(_DWORD *)v35 > 4u
        && (*((_QWORD *)v35 + 2) & 2) != 0
        && (*((_QWORD *)v35 + 3) & 2LL) == *((_QWORD *)v35 + 3) )
      {
        v38 = L"EventThresholdMet_SkipBugcheckEventWithWrongPropCount";
        v39 = byte_18002A303;
        goto LABEL_71;
      }
      goto LABEL_72;
    }
    if ( *(_WORD *)v66[0] != 1001 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)0x8000FFFFLL,
        Flagsa);
      std::vector<unsigned char>::~vector<unsigned char>(v66);
      if ( Events )
        EvtClose(Events);
      std::vector<unsigned char>::~vector<unsigned char>(Buffer);
      if ( v13 )
        EvtClose(v13);
      EvtClose(RenderContext);
      EvtClose(v9);
      return 2147549183LL;
    }
    if ( *((_DWORD *)v66[0] + 7) != 1 || (v40 = *((_QWORD *)v66[0] + 2)) == 0 )
    {
      v35 = TlgHelper::Provider();
      if ( *(_DWORD *)v35 > 4u
        && (*((_QWORD *)v35 + 2) & 2) != 0
        && (*((_QWORD *)v35 + 3) & 2LL) == *((_QWORD *)v35 + 3) )
      {
        v38 = L"EventThresholdMet_SkipBugcheckEventWithWrongParam1Type";
        v39 = &byte_18002A2E7;
LABEL_71:
        ValuePaths[0] = v38;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v35,
          (_DWORD)v39,
          v36,
          v37,
          (__int64)ValuePaths);
      }
LABEL_72:
      std::vector<unsigned char>::~vector<unsigned char>(v66);
      goto LABEL_125;
    }
    v84 = 0;
    v85 = 0;
    v86 = 0;
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)(v40 + 2 * v41) );
    std::wstring::_Construct<1,unsigned short const *>(&v84);
    if ( std::wstring::find_first_of(&v84) == -1 )
    {
      v42 = (LPCWSTR *)std::wstring::wstring(v90, &v84);
      v8 |= 1u;
    }
    else
    {
      *(_OWORD *)ValuePaths = 0;
      v80 = 0;
      v81 = 0;
      std::wstring::_Construct<1,unsigned short const *>(ValuePaths);
      v42 = ValuePaths;
      v8 |= 6u;
    }
    v62 = v8;
    v82 = 0;
    v83 = 0u;
    v82 = *(_OWORD *)v42;
    v83 = *((_OWORD *)v42 + 1);
    v42[2] = 0;
    v42[3] = (LPCWSTR)7;
    *(_WORD *)v42 = 0;
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      v62 = v8;
      std::wstring::~wstring(ValuePaths);
    }
    if ( (v8 & 1) != 0 )
    {
      v8 &= ~1u;
      v62 = v8;
      std::wstring::~wstring(v90);
    }
    if ( !(_QWORD)v83 )
    {
      v43 = TlgHelper::Provider();
      if ( *(_DWORD *)v43 > 4u
        && (*((_QWORD *)v43 + 2) & 2) != 0
        && (*((_QWORD *)v43 + 3) & 2LL) == *((_QWORD *)v43 + 3) )
      {
        ValuePaths[0] = L"EventThresholdMet_SkipBugcheckEventWithEmptyParam1";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v43,
          (unsigned int)byte_180029A45,
          v44,
          v45,
          (__int64)ValuePaths);
      }
      std::wstring::~wstring(&v82);
      std::wstring::~wstring(&v84);
      goto LABEL_72;
    }
    v46 = (const WCHAR *)&v82;
    if ( *((_QWORD *)&v83 + 1) > 7u )
      v46 = (const WCHAR *)v82;
    ValuePaths[0] = v46;
    TlgHelper::LogInfoString<unsigned short const (&)[41],unsigned short const *>(v42, ValuePaths);
    v47 = &v82;
    if ( *((_QWORD *)&v83 + 1) > 7u )
      v47 = (__int128 *)v82;
    *(_OWORD *)String = 0;
    v88 = 0;
    v89 = 0;
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)v47 + v48) );
    std::wstring::_Construct<1,unsigned short const *>(String);
    v49 = (_DWORD *)_o__errno();
    v50 = v49;
    v51 = (const wchar_t *)String;
    if ( v89 > 7 )
      v51 = String[0];
    EndPtr = 0;
    *v49 = 0;
    v52 = wcstoull(v51, &EndPtr, 16);
    if ( v51 == EndPtr )
      std::_Xinvalid_argument("invalid stoull argument");
    if ( *v50 == 34 )
      std::_Xout_of_range("stoull argument out of range");
    std::wstring::~wstring(String);
    if ( v52 - 25 <= 1
      || v52 - 261 <= 0x35 && (v53 = 0x30004480000011LL, _bittest64(&v53, v52 - 261))
      || v52 - 339 <= 0x3E && (v53 = 0x4240000000020003LL, _bittest64(&v53, v52 - 339))
      || v52 == 455
      || v52 - 162 <= 0x3C && (v53 = 0x1380400980000401LL, _bittest64(&v53, v52 - 162))
      || v52 == 78
      || v52 == 250 )
    {
      v55 = (const WCHAR *)&v82;
      if ( *((_QWORD *)&v83 + 1) > 7u )
        v55 = (const WCHAR *)v82;
      ValuePaths[0] = v55;
      TlgHelper::LogInfoString<unsigned short const (&)[49],unsigned short const *>(v53, ValuePaths);
      std::wstring::~wstring(&v82);
      std::wstring::~wstring(&v84);
      std::vector<unsigned char>::~vector<unsigned char>(v66);
      v17 = v63;
LABEL_124:
      v63 = ++v17;
      goto LABEL_125;
    }
    v54 = (const WCHAR *)&v82;
    if ( *((_QWORD *)&v83 + 1) > 7u )
      v54 = (const WCHAR *)v82;
    ValuePaths[0] = v54;
    TlgHelper::LogInfoString<unsigned short const (&)[51],unsigned short const *>(v53, ValuePaths);
    std::wstring::~wstring(&v82);
    std::wstring::~wstring(&v84);
    std::vector<unsigned char>::~vector<unsigned char>(v66);
    v17 = v63;
LABEL_125:
    memset_0(Buffer[0], 0, (char *)Buffer[1] - (char *)Buffer[0]);
  }
  if ( GetLastError() != 259 )
  {
    v56 = GetLastError();
    if ( v56 > 0 )
      v56 = (unsigned __int16)v56 | 0x80070000;
    v78[0] = L"EventThresholdMet_FailedToGetAllEvents";
    v78[1] = 38;
    TlgHelper::LogIfFailedExpected(v78, (unsigned int)v56);
  }
LABEL_134:
  TlgHelper::LogInfo<unsigned short const (&)[33],unsigned long &>(v28, &v63);
  *v77 = v17 >= v71;
  if ( Events )
    EvtClose(Events);
  std::vector<unsigned char>::~vector<unsigned char>(Buffer);
  if ( v13 )
    EvtClose(v13);
  EvtClose(RenderContext);
  EvtClose(v9);
  return 0;
}

```

## disassembly

```asm
0x18000b238  mov     [rsp+arg_0], rbx
0x18000b23d  mov     [rsp+arg_18], rsi
0x18000b242  push    rdi
0x18000b243  push    r12
0x18000b245  push    r13
0x18000b247  push    r14
0x18000b249  push    r15
0x18000b24b  sub     rsp, 190h
0x18000b252  mov     rax, cs:__security_cookie
0x18000b259  xor     rax, rsp
0x18000b25c  mov     [rsp+1B8h+var_30], rax
0x18000b264  mov     eax, r9d
0x18000b267  mov     [rsp+1B8h+var_124], eax
0x18000b26e  mov     r14, r8
0x18000b271  mov     [rsp+1B8h+var_108], rcx
0x18000b279  mov     rcx, [rsp+1B8h+arg_20]
0x18000b281  mov     [rsp+1B8h+var_F8], rcx
0x18000b289  xor     r15d, r15d
0x18000b28c  mov     r12d, r15d
0x18000b28f  mov     [rsp+1B8h+var_168], r15d
0x18000b294  mov     [rcx], r15b
0x18000b297  test    eax, eax
0x18000b299  jz      loc_18000BFA8
0x18000b29f  mov     r9d, 201h; Flags
0x18000b2a5  mov     r8, [r8]; Query
0x18000b2a8  mov     rdx, [rdx]; Path
0x18000b2ab  xor     ecx, ecx; Session
0x18000b2ad  call    cs:__imp_EvtQuery
0x18000b2b3  mov     rdi, rax
0x18000b2b6  mov     [rsp+1B8h+var_D8], rax
0x18000b2be  test    rax, rax
0x18000b2c1  jz      loc_18000BF85
0x18000b2c7  xor     r8d, r8d; Flags
0x18000b2ca  lea     rdx, ValuePaths; ValuePaths
0x18000b2d1  lea     ecx, [r8+1]; ValuePathsCount
0x18000b2d5  call    cs:__imp_EvtCreateRenderContext
0x18000b2db  mov     rsi, rax
0x18000b2de  mov     [rsp+1B8h+var_E8], rax
0x18000b2e6  test    rax, rax
0x18000b2e9  jz      loc_18000BF5D
0x18000b2ef  mov     rbx, r15
0x18000b2f2  mov     [rsp+1B8h+var_100], rbx
0x18000b2fa  mov     r8, [r14+8]; N
0x18000b2fe  cmp     r8, 5Ah ; 'Z'
0x18000b302  jnz     loc_18000B39A
0x18000b308  lea     rdx, aSystemProvider_2; "*[System[Provider[@Name='Microsoft-Wind"...
0x18000b30f  mov     rcx, [r14]; S1
0x18000b312  call    wmemcmp
0x18000b317  test    eax, eax
0x18000b319  jnz     short loc_18000B39A
0x18000b31b  lea     rax, aEventSystemEve; "Event/System/EventID"
0x18000b322  mov     [rsp+1B8h+ValuePaths], rax
0x18000b32a  lea     rax, aEventEventdata; "Event/EventData/Data[@Name='param1']"
0x18000b331  mov     [rsp+1B8h+ValuePaths+8], rax
0x18000b339  xor     r8d, r8d; Flags
0x18000b33c  lea     rdx, [rsp+1B8h+ValuePaths]; ValuePaths
0x18000b344  lea     ecx, [r8+2]; ValuePathsCount
0x18000b348  call    cs:__imp_EvtCreateRenderContext
0x18000b34e  mov     rbx, rax
0x18000b351  mov     [rsp+1B8h+var_100], rax
0x18000b359  test    rax, rax
0x18000b35c  jz      short loc_18000B365
0x18000b35e  mov     [rsp+1B8h+var_178], 1
0x18000b363  jmp     short loc_18000B39F
0x18000b365  mov     rcx, [rsp+1B8h]; this
0x18000b36d  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b374  mov     edx, 13Bh; void *
0x18000b379  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b37e  mov     ebx, eax
0x18000b380  mov     rcx, rsi; Object
0x18000b383  call    cs:__imp_EvtClose
0x18000b389  nop
0x18000b38a  mov     rcx, rdi; Object
0x18000b38d  call    cs:__imp_EvtClose
0x18000b393  mov     eax, ebx
0x18000b395  jmp     loc_18000BFA8
0x18000b39a  mov     [rsp+1B8h+var_178], r15b
0x18000b39f  xorps   xmm0, xmm0
0x18000b3a2  movdqu  xmmword ptr [rsp+1B8h+Buffer], xmm0
0x18000b3a8  mov     [rsp+1B8h+var_150], r15
0x18000b3ad  mov     ecx, 10h; Size
0x18000b3b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b3b7  mov     [rsp+1B8h+Buffer], rax
0x18000b3bc  lea     rcx, [rax+10h]
0x18000b3c0  mov     [rsp+1B8h+var_150], rcx
0x18000b3c5  xorps   xmm0, xmm0
0x18000b3c8  movups  xmmword ptr [rax], xmm0
0x18000b3cb  add     rax, 10h
0x18000b3cf  mov     [rsp+1B8h+Buffer+8], rax
0x18000b3d4  mov     [rsp+1B8h+EndPtr], r15
0x18000b3dc  lea     rcx, [rsp+1B8h+EndPtr]
0x18000b3e4  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18000b3e9  nop
0x18000b3ea  mov     [rsp+1B8h+BufferUsed], r15d
0x18000b3f2  mov     [rsp+1B8h+var_110], r15d
0x18000b3fa  mov     r13d, r15d
0x18000b3fd  mov     [rsp+1B8h+var_164], r15d
0x18000b402  mov     [rsp+1B8h+Events], r15
0x18000b407  test    r15, r15
0x18000b40a  jz      short loc_18000B427
0x18000b40c  call    cs:__imp_GetLastError
0x18000b412  mov     r14d, eax
0x18000b415  mov     rcx, r15; Object
0x18000b418  call    cs:__imp_EvtClose
0x18000b41e  mov     ecx, r14d; dwErrCode
0x18000b421  call    cs:__imp_SetLastError
0x18000b427  xor     r15d, r15d
0x18000b42a  mov     [rsp+1B8h+Events], r15
0x18000b42f  lea     rax, [rsp+1B8h+var_110]
0x18000b437  mov     [rsp+1B8h+Returned], rax; Returned
0x18000b43c  mov     [rsp+1B8h+Flags], r15d; Flags
0x18000b441  mov     r9d, 7D0h; Timeout
0x18000b447  lea     r8, [rsp+1B8h+Events]; Events
0x18000b44c  lea     edx, [r15+1]; EventsSize
0x18000b450  mov     rcx, rdi; ResultSet
0x18000b453  call    cs:__imp_EvtNext
0x18000b459  test    eax, eax
0x18000b45b  jz      loc_18000BEB3
0x18000b461  mov     [rsp+1B8h+var_120], r15d
0x18000b469  mov     rax, [rsp+1B8h+Buffer]
0x18000b46e  mov     r9d, dword ptr [rsp+1B8h+Buffer+8]
0x18000b473  sub     r9d, eax; BufferSize
0x18000b476  lea     rcx, [rsp+1B8h+var_120]
0x18000b47e  mov     [rsp+1B8h+PropertyCount], rcx; PropertyCount
0x18000b483  lea     rcx, [rsp+1B8h+BufferUsed]
0x18000b48b  mov     [rsp+1B8h+Returned], rcx; BufferUsed
0x18000b490  mov     qword ptr [rsp+1B8h+Flags], rax; int
0x18000b495  xor     r8d, r8d; Flags
0x18000b498  mov     rdx, [rsp+1B8h+Events]; Fragment
0x18000b49d  mov     rcx, rsi; Context
0x18000b4a0  call    cs:__imp_EvtRender
0x18000b4a6  test    eax, eax
0x18000b4a8  jnz     loc_18000B622
0x18000b4ae  call    cs:__imp_GetLastError
0x18000b4b4  cmp     eax, 7Ah ; 'z'
0x18000b4b7  jz      short loc_18000B51B
0x18000b4b9  mov     rcx, [rsp+1B8h]; this
0x18000b4c1  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b4c8  mov     edx, 14Bh; void *
0x18000b4cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b4d2  mov     r14d, eax
0x18000b4d5  mov     rcx, [rsp+1B8h+Events]; Object
0x18000b4da  test    rcx, rcx
0x18000b4dd  jz      short loc_18000B4E6
0x18000b4df  call    cs:__imp_EvtClose
0x18000b4e5  nop
0x18000b4e6  lea     rcx, [rsp+1B8h+Buffer]
0x18000b4eb  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000b4f0  nop
0x18000b4f1  test    rbx, rbx
0x18000b4f4  jz      short loc_18000B500
0x18000b4f6  mov     rcx, rbx; Object
0x18000b4f9  call    cs:__imp_EvtClose
0x18000b4ff  nop
0x18000b500  mov     rcx, rsi; Object
0x18000b503  call    cs:__imp_EvtClose
0x18000b509  nop
0x18000b50a  mov     rcx, rdi; Object
0x18000b50d  call    cs:__imp_EvtClose
0x18000b513  mov     eax, r14d
0x18000b516  jmp     loc_18000BFA8
0x18000b51b  mov     r15d, [rsp+1B8h+BufferUsed]
0x18000b523  mov     r14, [rsp+1B8h+Buffer+8]
0x18000b528  mov     rdx, r14
0x18000b52b  mov     rcx, [rsp+1B8h+Buffer]
0x18000b530  sub     rdx, rcx
0x18000b533  cmp     r15, rdx
0x18000b536  jnb     short loc_18000B53E
0x18000b538  lea     r14, [r15+rcx]
0x18000b53c  jmp     short loc_18000B57E
0x18000b53e  jbe     short loc_18000B583
0x18000b540  mov     rax, [rsp+1B8h+var_150]
0x18000b545  sub     rax, rcx
0x18000b548  cmp     r15, rax
0x18000b54b  jbe     short loc_18000B566
0x18000b54d  mov     rdx, r15
0x18000b550  lea     rcx, [rsp+1B8h+Buffer]
0x18000b555  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000b55a  mov     r14, [rsp+1B8h+Buffer+8]
0x18000b55f  mov     rcx, [rsp+1B8h+Buffer]
0x18000b564  jmp     short loc_18000B583
0x18000b566  sub     r15, rdx
0x18000b569  mov     r8, r15; Size
0x18000b56c  xor     edx, edx; Val
0x18000b56e  mov     rcx, r14; void *
0x18000b571  call    memset_0
0x18000b576  add     r14, r15
0x18000b579  mov     rcx, [rsp+1B8h+Buffer]
0x18000b57e  mov     [rsp+1B8h+Buffer+8], r14
0x18000b583  sub     r14d, ecx
0x18000b586  lea     rax, [rsp+1B8h+var_120]
0x18000b58e  mov     [rsp+1B8h+PropertyCount], rax; PropertyCount
0x18000b593  lea     rax, [rsp+1B8h+BufferUsed]
0x18000b59b  mov     [rsp+1B8h+Returned], rax; BufferUsed
0x18000b5a0  mov     qword ptr [rsp+1B8h+Flags], rcx; Buffer
0x18000b5a5  mov     r9d, r14d; BufferSize
0x18000b5a8  xor     r8d, r8d; Flags
0x18000b5ab  mov     rdx, [rsp+1B8h+Events]; Fragment
0x18000b5b0  mov     rcx, rsi; Context
0x18000b5b3  call    cs:__imp_EvtRender
0x18000b5b9  xor     r15d, r15d
0x18000b5bc  test    eax, eax
0x18000b5be  jnz     short loc_18000B622
0x18000b5c0  mov     rcx, [rsp+1B8h]; this
0x18000b5c8  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b5cf  mov     edx, 151h; void *
0x18000b5d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b5d9  mov     r14d, eax
0x18000b5dc  mov     rcx, [rsp+1B8h+Events]; Object
0x18000b5e1  test    rcx, rcx
0x18000b5e4  jz      short loc_18000B5ED
0x18000b5e6  call    cs:__imp_EvtClose
0x18000b5ec  nop
0x18000b5ed  lea     rcx, [rsp+1B8h+Buffer]
0x18000b5f2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000b5f7  nop
0x18000b5f8  test    rbx, rbx
0x18000b5fb  jz      short loc_18000B607
0x18000b5fd  mov     rcx, rbx; Object
0x18000b600  call    cs:__imp_EvtClose
0x18000b606  nop
0x18000b607  mov     rcx, rsi; Object
0x18000b60a  call    cs:__imp_EvtClose
0x18000b610  nop
0x18000b611  mov     rcx, rdi; Object
0x18000b614  call    cs:__imp_EvtClose
0x18000b61a  mov     eax, r14d
0x18000b61d  jmp     loc_18000BFA8
0x18000b622  mov     rcx, [rsp+1B8h+Buffer]
0x18000b627  cmp     dword ptr [rcx+0Ch], 11h
0x18000b62b  jz      short loc_18000B696
0x18000b62d  mov     rcx, [rsp+1B8h]; this
0x18000b635  mov     r14d, 8007000Dh
0x18000b63b  mov     r9d, r14d; char *
0x18000b63e  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b645  mov     edx, 155h; void *
0x18000b64a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b64f  nop
0x18000b650  mov     rcx, [rsp+1B8h+Events]; Object
0x18000b655  test    rcx, rcx
0x18000b658  jz      short loc_18000B661
0x18000b65a  call    cs:__imp_EvtClose
0x18000b660  nop
0x18000b661  lea     rcx, [rsp+1B8h+Buffer]
0x18000b666  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000b66b  nop
0x18000b66c  test    rbx, rbx
0x18000b66f  jz      short loc_18000B67B
0x18000b671  mov     rcx, rbx; Object
0x18000b674  call    cs:__imp_EvtClose
0x18000b67a  nop
0x18000b67b  mov     rcx, rsi; Object
0x18000b67e  call    cs:__imp_EvtClose
0x18000b684  nop
0x18000b685  mov     rcx, rdi; Object
0x18000b688  call    cs:__imp_EvtClose
0x18000b68e  mov     eax, r14d
0x18000b691  jmp     loc_18000BFA8
0x18000b696  mov     rax, [rsp+1B8h+var_108]
0x18000b69e  mov     rax, [rax+58h]
0x18000b6a2  cmp     [rcx], rax
0x18000b6a5  jnb     short loc_18000B707
0x18000b6a7  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000b6ac  mov     ecx, [rax]
0x18000b6ae  cmp     ecx, 4
0x18000b6b1  jbe     loc_18000BEFC
0x18000b6b7  mov     rdx, [rax+18h]
0x18000b6bb  mov     rcx, [rax+10h]
0x18000b6bf  test    cl, 2
0x18000b6c2  jz      loc_18000BEFC
0x18000b6c8  mov     rcx, rdx
0x18000b6cb  and     ecx, 2
0x18000b6ce  cmp     rcx, rdx
0x18000b6d1  jnz     loc_18000BEFC
0x18000b6d7  lea     rcx, aEventthreshold_7; "EventThresholdMet_ReachedLookbackLimit"
0x18000b6de  mov     [rsp+1B8h+var_108], rcx
0x18000b6e6  lea     rcx, [rsp+1B8h+var_108]
0x18000b6ee  mov     qword ptr [rsp+1B8h+Flags], rcx
0x18000b6f3  lea     rdx, byte_180029F35
0x18000b6fa  mov     rcx, rax
0x18000b6fd  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b702  jmp     loc_18000BEFC
0x18000b707  cmp     [rsp+1B8h+var_178], r15b
0x18000b70c  jz      loc_18000BE4A
0x18000b712  xorps   xmm0, xmm0
0x18000b715  movdqu  xmmword ptr [rsp+1B8h+var_148], xmm0
0x18000b71b  mov     [rsp+1B8h+var_138], r15
0x18000b723  mov     ecx, 20h ; ' '; Size
0x18000b728  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b72d  mov     [rsp+1B8h+var_148], rax
0x18000b732  lea     rcx, [rax+20h]
0x18000b736  mov     [rsp+1B8h+var_138], rcx
0x18000b73e  xorps   xmm0, xmm0
0x18000b741  movups  xmmword ptr [rax], xmm0
0x18000b744  movups  xmmword ptr [rax+10h], xmm0
0x18000b748  add     rax, 20h ; ' '
0x18000b74c  mov     [rsp+1B8h+var_148+8], rax
0x18000b751  mov     [rsp+1B8h+ValuePaths], r15
0x18000b759  lea     rcx, [rsp+1B8h+ValuePaths]
0x18000b761  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
  ... truncated ...
```
