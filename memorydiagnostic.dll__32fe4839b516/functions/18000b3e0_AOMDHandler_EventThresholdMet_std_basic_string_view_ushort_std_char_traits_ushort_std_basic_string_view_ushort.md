# AOMDHandler::EventThresholdMet(std::basic_string_view<ushort,std::char_traits<ushort>>,std::basic_string_view<ushort,std::char_traits<ushort>>,ulong,bool &)

- ea: `0x18000b3e0`
- end: `0x18000c957`
- name: `?EventThresholdMet@AOMDHandler@@AEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0KAEA_N@Z`
- size: `5495`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000b014`

## callees

- `0x180001008`
- `0x1800026b0`
- `0x1800026d4`
- `0x180002b0c`
- `0x180003374`
- `0x180003e4c`
- `0x180003ebc`
- `0x1800042c8`
- `0x18000433c`
- `0x1800043b0`
- `0x180004424`
- `0x180004498`
- `0x18000450c`
- `0x180004580`
- `0x180005c80`
- `0x180005fdc`
- `0x180006140`
- `0x180006ec4`
- `0x180007778`
- `0x180007858`
- `0x180007d68`
- `0x18000b3e0`
- `0x18000e710`
- `0x18000e964`
- `0x18000f144`
- `0x180011384`
- `0x1800113a4`
- `0x1800172f4`
- `0x180019cec`
- `0x180019d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000b95a`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000beb8`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000c7ed`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000b95a`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000beb8`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000c7ed`
- `KERNEL32!GetLastError` at `0x18000b5ed`
- `KERNEL32!GetLastError` at `0x18000b6ab`
- `KERNEL32!GetLastError` at `0x18000bad7`
- `KERNEL32!GetLastError` at `0x18000c7fa`
- `KERNEL32!GetLastError` at `0x18000c80d`
- `KERNEL32!GetLastError` at `0x18000b5ed`
- `KERNEL32!GetLastError` at `0x18000b6ab`
- `KERNEL32!GetLastError` at `0x18000bad7`
- `KERNEL32!GetLastError` at `0x18000c7fa`
- `KERNEL32!GetLastError` at `0x18000c80d`
- `KERNEL32!SetLastError` at `0x18000b60e`
- `KERNEL32!SetLastError` at `0x18000b60e`
- `wevtapi!EvtCreateRenderContext` at `0x18000b477`
- `wevtapi!EvtCreateRenderContext` at `0x18000b517`
- `wevtapi!EvtCreateRenderContext` at `0x18000b477`
- `wevtapi!EvtCreateRenderContext` at `0x18000b517`
- `wevtapi!EvtClose` at `0x18000b558`
- `wevtapi!EvtClose` at `0x18000b568`
- `wevtapi!EvtClose` at `0x18000b5ff`
- `wevtapi!EvtClose` at `0x18000b6e6`
- `wevtapi!EvtClose` at `0x18000b746`
- `wevtapi!EvtClose` at `0x18000b756`
- `wevtapi!EvtClose` at `0x18000b766`
- `wevtapi!EvtClose` at `0x18000b84a`
- `wevtapi!EvtClose` at `0x18000b8aa`
- `wevtapi!EvtClose` at `0x18000b8ba`
- `wevtapi!EvtClose` at `0x18000b8ca`
- `wevtapi!EvtClose` at `0x18000b91a`
- `wevtapi!EvtClose` at `0x18000b983`
- `wevtapi!EvtClose` at `0x18000b993`
- `wevtapi!EvtClose` at `0x18000b9a3`
- `wevtapi!EvtClose` at `0x18000bb5c`
- `wevtapi!EvtClose` at `0x18000bbbc`
- `wevtapi!EvtClose` at `0x18000bbcc`
- `wevtapi!EvtClose` at `0x18000bbdc`
- `wevtapi!EvtClose` at `0x18000bd0a`
- `wevtapi!EvtClose` at `0x18000bd6a`
- `wevtapi!EvtClose` at `0x18000bd7a`
- `wevtapi!EvtClose` at `0x18000bd8a`
- `wevtapi!EvtClose` at `0x18000be78`
- `wevtapi!EvtClose` at `0x18000bee1`
- `wevtapi!EvtClose` at `0x18000bef1`
- `wevtapi!EvtClose` at `0x18000bf01`
- `wevtapi!EvtClose` at `0x18000c892`
- `wevtapi!EvtClose` at `0x18000c8b2`
- `wevtapi!EvtClose` at `0x18000c8c2`
- `wevtapi!EvtClose` at `0x18000c8d2`
- `wevtapi!EvtClose` at `0x18000c900`
- `wevtapi!EvtClose` at `0x18000b558`
- `wevtapi!EvtClose` at `0x18000b568`
- `wevtapi!EvtClose` at `0x18000b5ff`
- `wevtapi!EvtClose` at `0x18000b6e6`
- `wevtapi!EvtClose` at `0x18000b746`
- `wevtapi!EvtClose` at `0x18000b756`
- `wevtapi!EvtClose` at `0x18000b766`
- `wevtapi!EvtClose` at `0x18000b84a`
- `wevtapi!EvtClose` at `0x18000b8aa`
- `wevtapi!EvtClose` at `0x18000b8ba`
- `wevtapi!EvtClose` at `0x18000b8ca`
- `wevtapi!EvtClose` at `0x18000b91a`
- `wevtapi!EvtClose` at `0x18000b983`
- `wevtapi!EvtClose` at `0x18000b993`
- `wevtapi!EvtClose` at `0x18000b9a3`
- `wevtapi!EvtClose` at `0x18000bb5c`
- `wevtapi!EvtClose` at `0x18000bbbc`
- `wevtapi!EvtClose` at `0x18000bbcc`
- `wevtapi!EvtClose` at `0x18000bbdc`
- `wevtapi!EvtClose` at `0x18000bd0a`
- `wevtapi!EvtClose` at `0x18000bd6a`
- `wevtapi!EvtClose` at `0x18000bd7a`
- `wevtapi!EvtClose` at `0x18000bd8a`
- `wevtapi!EvtClose` at `0x18000be78`
- `wevtapi!EvtClose` at `0x18000bee1`
- `wevtapi!EvtClose` at `0x18000bef1`
- `wevtapi!EvtClose` at `0x18000bf01`
- `wevtapi!EvtClose` at `0x18000c892`
- `wevtapi!EvtClose` at `0x18000c8b2`
- `wevtapi!EvtClose` at `0x18000c8c2`
- `wevtapi!EvtClose` at `0x18000c8d2`
- `wevtapi!EvtClose` at `0x18000c900`
- `wevtapi!EvtRender` at `0x18000b697`
- `wevtapi!EvtRender` at `0x18000b810`
- `wevtapi!EvtRender` at `0x18000bac3`
- `wevtapi!EvtRender` at `0x18000bc86`
- `wevtapi!EvtRender` at `0x18000b697`
- `wevtapi!EvtRender` at `0x18000b810`
- `wevtapi!EvtRender` at `0x18000bac3`
- `wevtapi!EvtRender` at `0x18000bc86`
- `wevtapi!EvtNext` at `0x18000b644`
- `wevtapi!EvtNext` at `0x18000b644`
- `wevtapi!EvtQuery` at `0x18000b449`
- `wevtapi!EvtQuery` at `0x18000b449`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall AOMDHandler::EventThresholdMet(__int64 a1, LPCWSTR *a2, LPCWSTR *a3, unsigned int a4, bool *a5)
{
  int v6; // r12d
  EVT_HANDLE v8; // rdi
  const char *v9; // r9
  EVT_HANDLE RenderContext; // rsi
  const char *v11; // r9
  EVT_HANDLE v12; // rbx
  unsigned __int64 v13; // rcx
  const wchar_t *v14; // rdx
  const char *v15; // r9
  unsigned int v16; // ebx
  char *v17; // rax
  HANDLE v18; // r13
  DWORD v19; // r14d
  const char *v20; // r9
  unsigned int v21; // r14d
  _BYTE *v22; // rcx
  unsigned __int64 v23; // rdx
  DWORD v24; // r9d
  PVOID v25; // rcx
  char *v26; // r14
  const char *v27; // r9
  const struct _tlgProvider_t *v28; // rax
  __int64 v29; // rcx
  int v30; // r8d
  int v31; // r9d
  char *v32; // rax
  const char *v33; // r9
  PVOID v34; // rcx
  unsigned __int64 v35; // rdx
  _BYTE *v36; // rcx
  unsigned __int64 v37; // rdx
  DWORD v38; // r9d
  PVOID v39; // rcx
  char *v40; // r14
  const char *v41; // r9
  const struct _tlgProvider_t *v42; // rax
  int v43; // r8d
  int v44; // r9d
  const WCHAR *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r8
  wchar_t *v48; // rax
  __int64 v49; // rcx
  const struct _tlgProvider_t *v50; // rax
  int v51; // r8d
  int v52; // r9d
  const WCHAR *v53; // rax
  __int128 *v54; // rax
  __int64 v56; // rcx
  __int128 *v57; // rdx
  __int64 v58; // r8
  __int64 v59; // r13
  __int64 v60; // rcx
  const WCHAR *v61; // r14
  __int128 *v62; // rax
  __int128 *v63; // rdx
  char *v64; // r8
  __int64 v65; // r8
  __int128 *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // r14
  __int64 first_of; // rax
  __int64 v70; // rax
  wchar_t *v71; // rax
  __int64 v72; // rcx
  wchar_t *v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rcx
  wchar_t *v76; // rax
  __int64 v77; // rcx
  const WCHAR *v78; // rax
  const WCHAR *v79; // rax
  __int64 v80; // rcx
  const WCHAR *v81; // rax
  const WCHAR *v82; // rax
  const WCHAR *v83; // rax
  signed int v84; // eax
  unsigned int LastError; // ebx
  wchar_t *v86; // rax
  wchar_t *v87; // rax
  const WCHAR *v88; // rax
  const WCHAR *v89; // rax
  int Flags; // [rsp+20h] [rbp-1F8h]
  int Flagsa; // [rsp+20h] [rbp-1F8h]
  int v92; // [rsp+40h] [rbp-1D8h]
  char v93; // [rsp+44h] [rbp-1D4h]
  PVOID Buffer; // [rsp+48h] [rbp-1D0h] BYREF
  void *v95; // [rsp+50h] [rbp-1C8h]
  char *v96; // [rsp+58h] [rbp-1C0h]
  PVOID v97[2]; // [rsp+60h] [rbp-1B8h] BYREF
  char *v98; // [rsp+70h] [rbp-1A8h]
  HANDLE Events; // [rsp+78h] [rbp-1A0h] BYREF
  unsigned int v100; // [rsp+80h] [rbp-198h] BYREF
  DWORD BufferUsed; // [rsp+84h] [rbp-194h] BYREF
  DWORD v102; // [rsp+88h] [rbp-190h] BYREF
  DWORD v103; // [rsp+8Ch] [rbp-18Ch] BYREF
  DWORD Returned; // [rsp+90h] [rbp-188h] BYREF
  EVT_HANDLE v105; // [rsp+98h] [rbp-180h]
  DWORD PropertyCount; // [rsp+A0h] [rbp-178h] BYREF
  EVT_HANDLE v107; // [rsp+A8h] [rbp-170h]
  EVT_HANDLE v108; // [rsp+B0h] [rbp-168h]
  __int128 v109; // [rsp+C0h] [rbp-158h] BYREF
  bool *v110; // [rsp+D0h] [rbp-148h]
  __int128 v111; // [rsp+E0h] [rbp-138h]
  LPCWSTR ValuePaths[2]; // [rsp+F0h] [rbp-128h] BYREF
  __int64 v113; // [rsp+100h] [rbp-118h]
  __int64 v114; // [rsp+108h] [rbp-110h]
  __int128 v115; // [rsp+110h] [rbp-108h] BYREF
  __int128 v116; // [rsp+120h] [rbp-F8h]
  wchar_t String[8]; // [rsp+130h] [rbp-E8h] BYREF
  __int128 v118; // [rsp+140h] [rbp-D8h]
  __int128 v119; // [rsp+150h] [rbp-C8h] BYREF
  __int64 v120; // [rsp+160h] [rbp-B8h]
  unsigned __int64 v121; // [rsp+168h] [rbp-B0h]
  _BYTE v122[32]; // [rsp+170h] [rbp-A8h] BYREF
  _BYTE v123[32]; // [rsp+190h] [rbp-88h] BYREF
  _BYTE v124[32]; // [rsp+1B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v110 = a5;
  v6 = 0;
  *a5 = 0;
  if ( !a4 )
    return 0;
  v8 = EvtQuery(0, *a2, *a3, 0x201u);
  v107 = v8;
  if ( !v8 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x135,
             (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
             v9);
  RenderContext = EvtCreateRenderContext(1u, &::ValuePaths, 0);
  v108 = RenderContext;
  if ( !RenderContext )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x138,
                  (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                  v11);
    EvtClose(v8);
    return LastError;
  }
  v12 = 0;
  v105 = 0;
  v13 = _mm_srli_si128(*(__m128i *)a3, 8).m128i_u64[0];
  if ( v13 == 90 )
  {
    v14 = L"*[System[Provider[@Name='Microsoft-Windows-WER-SystemErrorReporting'] and (EventID=1001)]]";
    while ( *(const wchar_t *)((char *)v14
                             + (char *)*a3
                             - (char *)L"*[System[Provider[@Name='Microsoft-Windows-WER-SystemErrorReporting'] and (EventID=1001)]]") == *v14 )
    {
      ++v14;
      if ( !--v13 )
      {
        ValuePaths[0] = L"Event/System/EventID";
        ValuePaths[1] = L"Event/EventData/Data[@Name='param1']";
        v12 = EvtCreateRenderContext(2u, ValuePaths, 0);
        v105 = v12;
        if ( !v12 )
        {
          v16 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x14C,
                  (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                  v15);
          EvtClose(RenderContext);
          EvtClose(v8);
          return v16;
        }
        v93 = 1;
        goto LABEL_13;
      }
    }
  }
  v93 = 0;
LABEL_13:
  v17 = (char *)operator new(0x10u);
  Buffer = v17;
  v96 = v17 + 16;
  *(_OWORD *)v17 = 0;
  v95 = v17 + 16;
  ValuePaths[0] = 0;
  std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(ValuePaths);
  BufferUsed = 0;
  Returned = 0;
  v100 = 0;
  v18 = 0;
  for ( Events = 0; ; v18 = Events )
  {
    if ( v18 )
    {
      v19 = GetLastError();
      EvtClose(v18);
      SetLastError(v19);
    }
    Events = 0;
    if ( !EvtNext(v8, 1u, &Events, 0x7D0u, 0, &Returned) )
      goto LABEL_226;
    PropertyCount = 0;
    if ( !EvtRender(RenderContext, Events, 0, (_DWORD)v95 - (_DWORD)Buffer, Buffer, &BufferUsed, &PropertyCount) )
    {
      if ( GetLastError() != 122 )
      {
        v21 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x15C,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v20);
        if ( Events )
          EvtClose(Events);
        v22 = Buffer;
        if ( Buffer )
        {
          v23 = v96 - (_BYTE *)Buffer;
          if ( (unsigned __int64)(v96 - (_BYTE *)Buffer) >= 0x1000 )
          {
            v23 += 39LL;
            v22 = (_BYTE *)*((_QWORD *)Buffer - 1);
            if ( (unsigned __int64)((_BYTE *)Buffer - v22 - 8) > 0x1F )
              goto LABEL_51;
          }
          operator delete(v22, v23);
          Buffer = 0;
          v95 = 0;
          v96 = 0;
        }
        if ( v12 )
          EvtClose(v12);
        goto LABEL_118;
      }
      v24 = (unsigned int)v95;
      v25 = Buffer;
      if ( BufferUsed >= (unsigned __int64)((_BYTE *)v95 - (_BYTE *)Buffer) )
      {
        if ( BufferUsed > (unsigned __int64)((_BYTE *)v95 - (_BYTE *)Buffer) )
        {
          if ( BufferUsed <= (unsigned __int64)(v96 - (_BYTE *)Buffer) )
          {
            v26 = (char *)Buffer + BufferUsed;
            memset_0(v95, 0, BufferUsed - ((_BYTE *)v95 - (_BYTE *)Buffer));
            v24 = (unsigned int)v26;
            v95 = v26;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&Buffer, BufferUsed);
            v24 = (unsigned int)v95;
          }
          v25 = Buffer;
        }
      }
      else
      {
        v24 = BufferUsed + (_DWORD)Buffer;
        v95 = (char *)Buffer + BufferUsed;
      }
      if ( !EvtRender(RenderContext, Events, 0, v24 - (_DWORD)v25, v25, &BufferUsed, &PropertyCount) )
      {
        v21 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x162,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v27);
        if ( Events )
          EvtClose(Events);
        v22 = Buffer;
        if ( Buffer )
        {
          v23 = v96 - (_BYTE *)Buffer;
          if ( (unsigned __int64)(v96 - (_BYTE *)Buffer) < 0x1000
            || (v23 += 39LL,
                v22 = (_BYTE *)*((_QWORD *)Buffer - 1),
                (unsigned __int64)((_BYTE *)Buffer - v22 - 8) <= 0x1F) )
          {
            operator delete(v22, v23);
            Buffer = 0;
            v95 = 0;
            v96 = 0;
            goto LABEL_42;
          }
LABEL_51:
          _o__invalid_parameter_noinfo_noreturn(v22, v23);
          __debugbreak();
LABEL_52:
          operator delete(v22, v23);
          Buffer = 0;
          v95 = 0;
          v96 = 0;
          goto LABEL_53;
        }
LABEL_42:
        if ( v12 )
          EvtClose(v12);
LABEL_118:
        EvtClose(RenderContext);
        EvtClose(v8);
        return v21;
      }
    }
    if ( *((_DWORD *)Buffer + 3) != 17 )
    {
      v21 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x166,
        (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
        (const char *)0x8007000DLL,
        Flags);
      if ( Events )
        EvtClose(Events);
      v22 = Buffer;
      if ( Buffer )
      {
        v23 = v96 - (_BYTE *)Buffer;
        if ( (unsigned __int64)(v96 - (_BYTE *)Buffer) >= 0x1000 )
        {
          v23 += 39LL;
          v22 = (_BYTE *)*((_QWORD *)Buffer - 1);
          if ( (unsigned __int64)((_BYTE *)Buffer - v22 - 8) > 0x1F )
            goto LABEL_51;
        }
        goto LABEL_52;
      }
LABEL_53:
      if ( v12 )
        EvtClose(v12);
      goto LABEL_118;
    }
    if ( *(_QWORD *)Buffer < *(_QWORD *)(a1 + 88) )
    {
      v28 = TlgHelper::Provider();
      if ( *(_DWORD *)v28 > 4u && (*((_BYTE *)v28 + 16) & 2) != 0 )
      {
        v29 = *((_QWORD *)v28 + 3) & 2LL;
        if ( v29 == *((_QWORD *)v28 + 3) )
        {
          ValuePaths[0] = L"EventThresholdMet_ReachedLookbackLimit";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (_DWORD)v28,
            (unsigned int)&unk_18002AB01,
            v30,
            v31,
            (__int64)ValuePaths);
        }
      }
      goto LABEL_230;
    }
    if ( !v93 )
      goto LABEL_207;
    *(_OWORD *)v97 = 0;
    v98 = 0;
    v32 = (char *)operator new(0x20u);
    v97[0] = v32;
    v98 = v32 + 32;
    *(_OWORD *)v32 = 0;
    *((_OWORD *)v32 + 1) = 0;
    v97[1] = v32 + 32;
    ValuePaths[0] = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(ValuePaths);
    v102 = 0;
    v103 = 0;
    if ( !EvtRender(v12, Events, 0, LODWORD(v97[1]) - LODWORD(v97[0]), v97[0], &v102, &v103) )
    {
      if ( GetLastError() != 122 )
      {
        v21 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x179,
                (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                v33);
        v34 = v97[0];
        if ( v97[0] )
        {
          v35 = v98 - (char *)v97[0];
          if ( (unsigned __int64)(v98 - (char *)v97[0]) >= 0x1000 )
          {
            v35 += 39LL;
            v34 = (PVOID)*((_QWORD *)v97[0] - 1);
            if ( (unsigned __int64)((char *)v97[0] - (char *)v34 - 8) > 0x1F )
              goto LABEL_225;
          }
          operator delete(v34, v35);
          *(_OWORD *)v97 = 0;
          v98 = 0;
        }
        if ( Events )
          EvtClose(Events);
        v36 = Buffer;
        if ( Buffer )
        {
          v37 = v96 - (_BYTE *)Buffer;
          if ( (unsigned __int64)(v96 - (_BYTE *)Buffer) >= 0x1000 )
          {
            v37 += 39LL;
            v36 = (_BYTE *)*((_QWORD *)Buffer - 1);
            if ( (unsigned __int64)((_BYTE *)Buffer - v36 - 8) > 0x1F )
              goto LABEL_114;
          }
          operator delete(v36, v37);
          Buffer = 0;
          v95 = 0;
          v96 = 0;
        }
        if ( v12 )
          EvtClose(v12);
        goto LABEL_118;
      }
      v38 = (DWORD)v97[1];
      v39 = v97[0];
      if ( (PVOID)v102 >= (PVOID)((char *)v97[1] - (char *)v97[0]) )
      {
        if ( (PVOID)v102 > (PVOID)((char *)v97[1] - (char *)v97[0]) )
        {
          if ( v102 <= (unsigned __int64)(v98 - (char *)v97[0]) )
          {
            v40 = (char *)v97[0] + v102;
            memset_0(v97[1], 0, v102 - (unsigned __int64)((char *)v97[1] - (char *)v97[0]));
            v38 = (unsigned int)v40;
            v97[1] = v40;
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v97, v102);
            v38 = (DWORD)v97[1];
          }
          v39 = v97[0];
        }
      }
      else
      {
        v38 = v102 + LODWORD(v97[0]);
        v97[1] = (char *)v97[0] + v102;
      }
      if ( !EvtRender(v12, Events, 0, v38 - (_DWORD)v39, v39, &v102, &v103) )
        break;
    }
    if ( v103 >= 2 )
    {
      if ( *(_WORD *)v97[0] != 1001 )
      {
        v21 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18F,
          (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
          (const char *)0x8000FFFFLL,
          Flagsa);
        v34 = v97[0];
        if ( v97[0] )
        {
          v35 = v98 - (char *)v97[0];
          if ( (unsigned __int64)(v98 - (char *)v97[0]) >= 0x1000 )
          {
            v35 += 39LL;
            v34 = (PVOID)*((_QWORD *)v97[0] - 1);
            if ( (unsigned __int64)((char *)v97[0] - (char *)v34 - 8) > 0x1F )
              goto LABEL_225;
          }
          operator delete(v34, v35);
          *(_OWORD *)v97 = 0;
          v98 = 0;
        }
        if ( Events )
          EvtClose(Events);
        v36 = Buffer;
        if ( Buffer )
        {
          v37 = v96 - (_BYTE *)Buffer;
          if ( (unsigned __int64)(v96 - (_BYTE *)Buffer) >= 0x1000 )
          {
            v37 += 39LL;
            v36 = (_BYTE *)*((_QWORD *)Buffer - 1);
            if ( (unsigned __int64)((_BYTE *)Buffer - v36 - 8) > 0x1F )
              goto LABEL_114;
          }
          goto LABEL_115;
        }
LABEL_116:
        if ( v12 )
          EvtClose(v12);
        goto LABEL_118;
      }
      if ( *((_DWORD *)v97[0] + 7) == 1 && (v46 = *((_QWORD *)v97[0] + 2)) != 0 )
      {
        v119 = 0;
        v120 = 0;
        v121 = 0;
        v47 = -1;
        do
          ++v47;
        while ( *(_WORD *)(v46 + 2 * v47) );
        std::wstring::_Construct<1,unsigned short const *>(&v119);
        if ( std::wstring::find_first_of(&v119, L" (", 0) == -1 )
        {
          v48 = (wchar_t *)std::wstring::wstring(v122, &v119);
          v6 |= 1u;
        }
        else
        {
          *(_OWORD *)String = 0;
          v118 = 0u;
          std::wstring::_Construct<1,unsigned short const *>(String);
          v48 = String;
          v6 |= 0x12u;
        }
        v92 = v6;
        v115 = 0;
        v116 = 0u;
        v115 = *(_OWORD *)v48;
        v116 = *((_OWORD *)v48 + 1);
        *((_QWORD *)v48 + 2) = 0;
        *((_QWORD *)v48 + 3) = 7;
        *v48 = 0;
        if ( (v6 & 2) != 0 )
        {
          v6 &= ~2u;
          v92 = v6;
          std::wstring::~wstring(String);
        }
        if ( (v6 & 1) != 0 )
        {
          v6 &= ~1u;
          v92 = v6;
          std::wstring::~wstring(v122);
        }
        if ( (_QWORD)v116 )
        {
          v53 = (const WCHAR *)&v115;
          if ( *((_QWORD *)&v116 + 1) > 7u )
            v53 = (const WCHAR *)v115;
          ValuePaths[0] = v53;
          TlgHelper::LogInfoString<unsigned short const (&)[41],unsigned short const *>(v49, ValuePaths);
          v54 = &v115;
          if ( *((_QWORD *)&v116 + 1) > 7u )
            v54 = (__int128 *)v115;
          *(_QWORD *)&v111 = v54;
          *((_QWORD *)&v111 + 1) = v116;
          *(_OWORD *)ValuePaths = v111;
          if ( (unsigned __int8)anonymous_namespace_::IsHexToken(ValuePaths) )
          {
            v57 = &v115;
            if ( *((_QWORD *)&v116 + 1) > 7u )
              v57 = (__int128 *)v115;
            *(_OWORD *)String = 0;
            v118 = 0u;
            v58 = -1;
            do
              ++v58;
            while ( *((_WORD *)v57 + v58) );
            try
            {
              std::wstring::_Construct<1,unsigned short const *>(String);
              v59 = std::stoull(String);
              std::wstring::~wstring(String);
              v61 = 0;
              ValuePaths[0] = 0;
              v62 = &v119;
              if ( v121 > 7 )
                v62 = (__int128 *)v119;
            }
            catch ( std::invalid_argument )
            {
              v88 = (const WCHAR *)&v115;
              if ( *((_QWORD *)&v116 + 1) > 7u )
                v88 = (const WCHAR *)v115;
              ValuePaths[0] = v88;
              TlgHelper::LogWarningString<unsigned short const (&)[55],unsigned short const *>(v60, ValuePaths);
              goto LABEL_209;
            }
            catch ( std::out_of_range )
            {
              v89 = (const WCHAR *)&v115;
              if ( *((_QWORD *)&v116 + 1) > 7u )
                v89 = (const WCHAR *)v115;
              ValuePaths[0] = v89;
              TlgHelper::LogWarningString<unsigned short const (&)[48],unsigned short const *>(v60, ValuePaths);
LABEL_209:
              std::wstring::~wstring(&v115);
              std::wstring::~wstring(&v119);
              v34 = v97[0];
              if ( v97[0] )
              {
                v35 = v98 - (char *)v97[0];
                if ( (unsigned __int64)(v98 - (char *)v97[0]) >= 0x1000 )
                {
                  v35 += 39LL;
                  v34 = (PVOID)*((_QWORD *)v97[0] - 1);
                  if ( (unsigned __int64)((char *)v97[0] - (char *)v34 - 8) > 0x1F )
                    goto LABEL_225;
                }
                operator delete(v34, v35);
              }
              goto LABEL_213;
            }
            if ( !v120 )
              goto LABEL_182;
            v60 = v120;
            v63 = v62;
            v64 = 0;
            if ( *(_WORD *)v62 == 40 )
            {
LABEL_152:
              v64 = (char *)v63;
            }
            else
            {
              while ( v60 != 1 )
              {
                --v60;
                v63 = (__int128 *)((char *)v63 + 2);
                if ( *(_WORD *)v63 == 40 )
                  goto LABEL_152;
              }
            }
            if ( !v64 )
              goto LABEL_182;
            v65 = (v64 - (char *)v62) >> 1;
            if ( v65 == -1 )
              goto LABEL_182;
            v66 = &v119;
            if ( v121 > 7 )
              LODWORD(v66) = v119;
            v67 = std::_Traits_find_first_not_of<std::char_traits<unsigned short>,1>(
                    (_DWORD)v66,
                    v120,
                    (int)v65 + 1,
                    (unsigned int)L" \t",
                    2);
            v68 = v67;
            if ( v67 == -1 )
            {
              v61 = ValuePaths[0];
              goto LABEL_182;
            }
            first_of = std::wstring::find_first_of(&v119, L",) ", v67);
            if ( first_of == -1 )
            {
              v70 = std::wstring::substr(&v119, v124, v68, -1);
              v6 |= 4u;
            }
            else
            {
              v70 = std::wstring::substr(&v119, v123, v68, first_of - v68);
              v6 |= 8u;
            }
            v92 = v6;
            *(_OWORD *)String = 0;
            v118 = 0u;
            *(_OWORD *)String = *(_OWORD *)v70;
            v118 = *(_OWORD *)(v70 + 16);
            *(_QWORD *)(v70 + 16) = 0;
            *(_QWORD *)(v70 + 24) = 7;
            *(_WORD *)v70 = 0;
            if ( (v6 & 8) != 0 )
            {
              v6 &= ~8u;
              v92 = v6;
              std::wstring::~wstring(v123);
            }
            if ( (v6 & 4) != 0 )
            {
              v6 &= ~4u;
              v92 = v6;
              std::wstring::~wstring(v124);
            }
            if ( !(_QWORD)v118 )
            {
              v61 = ValuePaths[0];
              goto LABEL_180;
            }
            v71 = String;
            if ( *((_QWORD *)&v118 + 1) > 7u )
              v71 = *(wchar_t **)String;
            *(_QWORD *)&v109 = v71;
            *((_QWORD *)&v109 + 1) = v118;
            *(_OWORD *)ValuePaths = v109;
            if ( !(unsigned __int8)anonymous_namespace_::IsHexToken(ValuePaths) )
            {
              v76 = String;
              if ( *((_QWORD *)&v118 + 1) > 7u )
                v76 = *(wchar_t **)String;
              ValuePaths[0] = v76;
              TlgHelper::LogWarningString<unsigned short const (&)[42],unsigned short const *>(v72, ValuePaths);
              std::wstring::~wstring(String);
              goto LABEL_178;
            }
            v73 = String;
            if ( *((_QWORD *)&v118 + 1) > 7u )
              v73 = *(wchar_t **)String;
            *(_OWORD *)ValuePaths = 0;
            v113 = 0;
            v114 = 0;
            v74 = -1;
            do
              ++v74;
            while ( v73[v74] );
            try
            {
              std::wstring::_Construct<1,unsigned short const *>(ValuePaths);
              v61 = (const WCHAR *)std::stoull((wchar_t *)ValuePaths);
              std::wstring::~wstring(ValuePaths);
            }
            catch ( std::invalid_argument )
            {
              v86 = String;
              if ( *((_QWORD *)&v118 + 1) > 7u )
                v86 = *(wchar_t **)String;
              ValuePaths[0] = v86;
              TlgHelper::LogWarningString<unsigned short const (&)[53],unsigned short const *>(v75, ValuePaths);
              goto LABEL_174;
            }
            catch ( std::out_of_range )
            {
              v87 = String;
              if ( *((_QWORD *)&v118 + 1) > 7u )
                v87 = *(wchar_t **)String;
              ValuePaths[0] = v87;
              TlgHelper::LogWarningString<unsigned short const (&)[46],unsigned short const *>(v75, ValuePaths);
LABEL_174:
              std::wstring::~wstring(String);
              std::wstring::~wstring(&v115);
              std::wstring::~wstring(&v119);
              std::vector<unsigned char>::~vector<unsigned char>(v97);
LABEL_213:
              v8 = v107;
              RenderContext = v108;
              v12 = v105;
              v6 = v92;
              goto LABEL_208;
            }
LABEL_180:
            std::wstring::~wstring(String);
LABEL_182:
            ValuePaths[0] = v61;
            TlgHelper::LogInfo<unsigned short const (&)[29],unsigned __int64>(v60, ValuePaths);
            if ( v59 != 26 )
            {
              if ( (unsigned __int64)(v59 - 261) > 0x35 || (v77 = 0x30004400000011LL, !_bittest64(&v77, v59 - 261)) )
              {
                if ( v59 != 455 )
                {
                  if ( (unsigned __int64)(v59 - 162) > 0x39 || (v77 = 0x380400980000401LL, !_bittest64(&v77, v59 - 162)) )
                  {
                    if ( v59 != 250 && v59 != 401 )
                    {
                      v78 = (const WCHAR *)&v115;
                      if ( *((_QWORD *)&v116 + 1) > 7u )
                        v78 = (const WCHAR *)v115;
                      ValuePaths[0] = v78;
                      TlgHelper::LogInfoString<unsigned short const (&)[51],unsigned short const *>(v77, ValuePaths);
LABEL_178:
                      std::wstring::~wstring(&v115);
                      std::wstring::~wstring(&v119);
                      std::vector<unsigned char>::~vector<unsigned char>(v97);
                      goto LABEL_208;
                    }
                  }
                }
              }
            }
            v79 = (const WCHAR *)&v115;
            if ( *((_QWORD *)&v116 + 1) > 7u )
              v79 = (const WCHAR *)v115;
            ValuePaths[0] = v79;
            TlgHelper::LogInfoString<unsigned short const (&)[49],unsigned short const *>(v77, ValuePaths);
            if ( v59 == 313 )
            {
              if ( v61 != (const WCHAR *)29 )
              {
                v81 = (const WCHAR *)&v115;
                if ( *((_QWORD *)&v116 + 1) > 7u )
                  v81 = (const WCHAR *)v115;
                ValuePaths[0] = v81;
                TlgHelper::LogInfoString<unsigned short const (&)[47],unsigned short const *>(v80, ValuePaths);
                goto LABEL_178;
              }
            }
            else if ( v59 == 26 && (v61 == (const WCHAR *)399681 || v61 == (const WCHAR *)63) )
            {
              v82 = (const WCHAR *)&v115;
              if ( *((_QWORD *)&v116 + 1) > 7u )
                v82 = (const WCHAR *)v115;
              ValuePaths[0] = v82;
              TlgHelper::LogInfoString<unsigned short const (&)[46],unsigned short const *>(v80, ValuePaths);
              goto LABEL_178;
            }
            std::wstring::~wstring(&v115);
            std::wstring::~wstring(&v119);
            std::vector<unsigned char>::~vector<unsigned char>(v97);
LABEL_207:
            ++v100;
            goto LABEL_208;
          }
          v83 = (const WCHAR *)&v115;
          if ( *((_QWORD *)&v116 + 1) > 7u )
            v83 = (const WCHAR *)v115;
          ValuePaths[0] = v83;
          TlgHelper::LogWarningString<unsigned short const (&)[44],unsigned short const *>(v56, ValuePaths);
        }
        else
        {
          v50 = TlgHelper::Provider();
          if ( *(_DWORD *)v50 > 4u
            && (*((_BYTE *)v50 + 16) & 2) != 0
            && (*((_QWORD *)v50 + 3) & 2LL) == *((_QWORD *)v50 + 3) )
          {
            ValuePaths[0] = L"EventThresholdMet_SkipBugcheckEventWithEmptyParam1";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v50,
              (unsigned int)&unk_18002AB01,
              v51,
              v52,
              (__int64)ValuePaths);
          }
        }
        std::wstring::~wstring(&v115);
        std::wstring::~wstring(&v119);
      }
      else
      {
        v42 = TlgHelper::Provider();
        if ( *(_DWORD *)v42 > 4u
          && (*((_BYTE *)v42 + 16) & 2) != 0
          && (*((_QWORD *)v42 + 3) & 2LL) == *((_QWORD *)v42 + 3) )
        {
          v45 = L"EventThresholdMet_SkipBugcheckEventWithWrongParam1Type";
          goto LABEL_221;
        }
      }
    }
    else
    {
      v42 = TlgHelper::Provider();
      if ( *(_DWORD *)v42 > 4u
        && (*((_BYTE *)v42 + 16) & 2) != 0
        && (*((_QWORD *)v42 + 3) & 2LL) == *((_QWORD *)v42 + 3) )
      {
        v45 = L"EventThresholdMet_SkipBugcheckEventWithWrongPropCount";
LABEL_221:
        ValuePaths[0] = v45;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v42,
          (unsigned int)&unk_18002AB01,
          v43,
          v44,
          (__int64)ValuePaths);
      }
    }
    v34 = v97[0];
    if ( v97[0] )
    {
      v35 = v98 - (char *)v97[0];
      if ( (unsigned __int64)(v98 - (char *)v97[0]) >= 0x1000 )
      {
        v34 = (PVOID)*((_QWORD *)v97[0] - 1);
        v35 += 39LL;
        if ( (unsigned __int64)((char *)v97[0] - (char *)v34 - 8) > 0x1F )
          goto LABEL_225;
      }
      operator delete(v34, v35);
    }
LABEL_208:
    memset_0(Buffer, 0, (_BYTE *)v95 - (_BYTE *)Buffer);
  }
  v21 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x17F,
          (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
          v41);
  v34 = v97[0];
  if ( !v97[0] )
    goto LABEL_89;
  v35 = v98 - (char *)v97[0];
  if ( (unsigned __int64)(v98 - (char *)v97[0]) < 0x1000
    || (v35 += 39LL, v34 = (PVOID)*((_QWORD *)v97[0] - 1), (unsigned __int64)((char *)v97[0] - (char *)v34 - 8) <= 0x1F) )
  {
    operator delete(v34, v35);
    *(_OWORD *)v97 = 0;
    v98 = 0;
LABEL_89:
    if ( Events )
      EvtClose(Events);
    v36 = Buffer;
    if ( !Buffer )
    {
LABEL_95:
      if ( v12 )
        EvtClose(v12);
      goto LABEL_118;
    }
    v37 = v96 - (_BYTE *)Buffer;
    if ( (unsigned __int64)(v96 - (_BYTE *)Buffer) < 0x1000
      || (v37 += 39LL, v36 = (_BYTE *)*((_QWORD *)Buffer - 1), (unsigned __int64)((_BYTE *)Buffer - v36 - 8) <= 0x1F) )
    {
      operator delete(v36, v37);
      Buffer = 0;
      v95 = 0;
      v96 = 0;
      goto LABEL_95;
    }
LABEL_114:
    _o__invalid_parameter_noinfo_noreturn(v36, v37);
    __debugbreak();
LABEL_115:
    operator delete(v36, v37);
    Buffer = 0;
    v95 = 0;
    v96 = 0;
    goto LABEL_116;
  }
LABEL_225:
  _o__invalid_parameter_noinfo_noreturn(v34, v35);
  __debugbreak();
LABEL_226:
  if ( GetLastError() != 259 )
  {
    v84 = GetLastError();
    if ( v84 > 0 )
      v84 = (unsigned __int16)v84 | 0x80070000;
    *(_QWORD *)&v109 = L"EventThresholdMet_FailedToGetAllEvents";
    *((_QWORD *)&v109 + 1) = 38;
    TlgHelper::LogIfFailedExpected(&v109, (unsigned int)v84);
  }
LABEL_230:
  TlgHelper::LogInfo<unsigned short const (&)[33],unsigned long &>(v29, &v100);
  *v110 = v100 >= a4;
  if ( Events )
    EvtClose(Events);
  std::vector<unsigned char>::~vector<unsigned char>(&Buffer);
  if ( v12 )
    EvtClose(v12);
  EvtClose(RenderContext);
  EvtClose(v8);
  return 0;
}

```

## disassembly

```asm
0x18000b3e0  mov     [rsp+arg_18], r9d
0x18000b3e5  mov     [rsp+arg_0], rcx
0x18000b3ea  push    rbx
0x18000b3eb  push    rsi
0x18000b3ec  push    rdi
0x18000b3ed  push    r12
0x18000b3ef  push    r13
0x18000b3f1  push    r14
0x18000b3f3  push    r15
0x18000b3f5  sub     rsp, 1E0h
0x18000b3fc  mov     rax, cs:__security_cookie
0x18000b403  xor     rax, rsp
0x18000b406  mov     [rsp+218h+var_48], rax
0x18000b40e  mov     r14, r8
0x18000b411  mov     rax, [rsp+218h+arg_20]
0x18000b419  mov     [rsp+218h+var_148], rax
0x18000b421  xor     r15d, r15d
0x18000b424  mov     r12d, r15d
0x18000b427  mov     [rsp+218h+var_1D8], r15d
0x18000b42c  mov     [rax], r15b
0x18000b42f  test    r9d, r9d
0x18000b432  jnz     short loc_18000B43B
0x18000b434  xor     eax, eax
0x18000b436  jmp     loc_18000C933
0x18000b43b  mov     r9d, 201h; Flags
0x18000b441  mov     r8, [r8]; Query
0x18000b444  mov     rdx, [rdx]; Path
0x18000b447  xor     ecx, ecx; Session
0x18000b449  call    cs:__imp_EvtQuery
0x18000b450  nop     dword ptr [rax+rax+00h]
0x18000b455  mov     rdi, rax
0x18000b458  mov     [rsp+218h+var_170], rax
0x18000b460  test    rax, rax
0x18000b463  jz      loc_18000C910
0x18000b469  xor     r8d, r8d; Flags
0x18000b46c  lea     rdx, ValuePaths; ValuePaths
0x18000b473  lea     ecx, [r8+1]; ValuePathsCount
0x18000b477  call    cs:__imp_EvtCreateRenderContext
0x18000b47e  nop     dword ptr [rax+rax+00h]
0x18000b483  mov     rsi, rax
0x18000b486  mov     [rsp+218h+var_168], rax
0x18000b48e  test    rax, rax
0x18000b491  jz      loc_18000C8E2
0x18000b497  mov     rbx, r15
0x18000b49a  mov     [rsp+218h+var_180], rbx
0x18000b4a2  movaps  xmm1, xmmword ptr [r14]
0x18000b4a6  movdqa  xmm0, xmm1
0x18000b4aa  psrldq  xmm0, 8
0x18000b4af  movq    rcx, xmm0
0x18000b4b4  cmp     rcx, 5Ah ; 'Z'
0x18000b4b8  jnz     loc_18000B57B
0x18000b4be  lea     rdx, aSystemProvider_2; "*[System[Provider[@Name='Microsoft-Wind"...
0x18000b4c5  test    rcx, rcx
0x18000b4c8  jz      short loc_18000B4EA
0x18000b4ca  movq    r8, xmm1
0x18000b4cf  sub     r8, rdx
0x18000b4d2  movzx   eax, word ptr [rdx+r8]
0x18000b4d7  cmp     ax, [rdx]
0x18000b4da  jnz     loc_18000B57B
0x18000b4e0  add     rdx, 2
0x18000b4e4  sub     rcx, 1
0x18000b4e8  jnz     short loc_18000B4D2
0x18000b4ea  lea     rax, aEventSystemEve; "Event/System/EventID"
0x18000b4f1  mov     [rsp+218h+ValuePaths], rax
0x18000b4f9  lea     rax, aEventEventdata; "Event/EventData/Data[@Name='param1']"
0x18000b500  mov     [rsp+218h+ValuePaths+8], rax
0x18000b508  xor     r8d, r8d; Flags
0x18000b50b  lea     rdx, [rsp+218h+ValuePaths]; ValuePaths
0x18000b513  lea     ecx, [r8+2]; ValuePathsCount
0x18000b517  call    cs:__imp_EvtCreateRenderContext
0x18000b51e  nop     dword ptr [rax+rax+00h]
0x18000b523  mov     rbx, rax
0x18000b526  mov     [rsp+218h+var_180], rax
0x18000b52e  test    rax, rax
0x18000b531  jz      short loc_18000B53A
0x18000b533  mov     [rsp+218h+var_1D4], 1
0x18000b538  jmp     short loc_18000B580
0x18000b53a  mov     rcx, [rsp+218h]; this
0x18000b542  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b549  mov     edx, 14Ch; void *
0x18000b54e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b553  mov     ebx, eax
0x18000b555  mov     rcx, rsi; Object
0x18000b558  call    cs:__imp_EvtClose
0x18000b55f  nop     dword ptr [rax+rax+00h]
0x18000b564  nop
0x18000b565  mov     rcx, rdi; Object
0x18000b568  call    cs:__imp_EvtClose
0x18000b56f  nop     dword ptr [rax+rax+00h]
0x18000b574  mov     eax, ebx
0x18000b576  jmp     loc_18000C933
0x18000b57b  mov     [rsp+218h+var_1D4], r15b
0x18000b580  mov     [rsp+218h+Buffer], r15
0x18000b585  mov     [rsp+218h+var_1C8], r15
0x18000b58a  mov     [rsp+218h+var_1C0], r15
0x18000b58f  mov     ecx, 10h; Size
0x18000b594  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b599  mov     [rsp+218h+Buffer], rax
0x18000b59e  lea     rcx, [rax+10h]
0x18000b5a2  mov     [rsp+218h+var_1C0], rcx
0x18000b5a7  xorps   xmm0, xmm0
0x18000b5aa  movups  xmmword ptr [rax], xmm0
0x18000b5ad  mov     [rsp+218h+var_1C8], rcx
0x18000b5b2  mov     [rsp+218h+ValuePaths], r15
0x18000b5ba  lea     rcx, [rsp+218h+ValuePaths]
0x18000b5c2  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18000b5c7  nop
0x18000b5c8  mov     [rsp+218h+BufferUsed], r15d
0x18000b5d0  mov     [rsp+218h+var_188], r15d
0x18000b5d8  mov     [rsp+218h+var_198], r15d
0x18000b5e0  mov     r13, r15
0x18000b5e3  mov     [rsp+218h+Events], r15
0x18000b5e8  test    r13, r13
0x18000b5eb  jz      short loc_18000B61A
0x18000b5ed  call    cs:__imp_GetLastError
0x18000b5f4  nop     dword ptr [rax+rax+00h]
0x18000b5f9  mov     r14d, eax
0x18000b5fc  mov     rcx, r13; Object
0x18000b5ff  call    cs:__imp_EvtClose
0x18000b606  nop     dword ptr [rax+rax+00h]
0x18000b60b  mov     ecx, r14d; dwErrCode
0x18000b60e  call    cs:__imp_SetLastError
0x18000b615  nop     dword ptr [rax+rax+00h]
0x18000b61a  mov     [rsp+218h+Events], r15
0x18000b61f  lea     rax, [rsp+218h+var_188]
0x18000b627  mov     [rsp+218h+Returned], rax; Returned
0x18000b62c  mov     [rsp+218h+Flags], r15d; Flags
0x18000b631  mov     r9d, 7D0h; Timeout
0x18000b637  lea     r8, [rsp+218h+Events]; Events
0x18000b63c  mov     edx, 1; EventsSize
0x18000b641  mov     rcx, rdi; ResultSet
0x18000b644  call    cs:__imp_EvtNext
0x18000b64b  nop     dword ptr [rax+rax+00h]
0x18000b650  test    eax, eax
0x18000b652  jz      loc_18000C7FA
0x18000b658  mov     [rsp+218h+var_178], r15d
0x18000b660  mov     r9, [rsp+218h+var_1C8]
0x18000b665  mov     rax, [rsp+218h+Buffer]
0x18000b66a  sub     r9, rax; BufferSize
0x18000b66d  lea     rcx, [rsp+218h+var_178]
0x18000b675  mov     [rsp+218h+PropertyCount], rcx; PropertyCount
0x18000b67a  lea     rcx, [rsp+218h+BufferUsed]
0x18000b682  mov     [rsp+218h+Returned], rcx; BufferUsed
0x18000b687  mov     qword ptr [rsp+218h+Flags], rax; int
0x18000b68c  xor     r8d, r8d; Flags
0x18000b68f  mov     rdx, [rsp+218h+Events]; Fragment
0x18000b694  mov     rcx, rsi; Context
0x18000b697  call    cs:__imp_EvtRender
0x18000b69e  nop     dword ptr [rax+rax+00h]
0x18000b6a3  test    eax, eax
0x18000b6a5  jnz     loc_18000B8DE
0x18000b6ab  call    cs:__imp_GetLastError
0x18000b6b2  nop     dword ptr [rax+rax+00h]
0x18000b6b7  cmp     eax, 7Ah ; 'z'
0x18000b6ba  jz      loc_18000B77A
0x18000b6c0  mov     rcx, [rsp+218h]; this
0x18000b6c8  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b6cf  mov     edx, 15Ch; void *
0x18000b6d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b6d9  mov     r14d, eax
0x18000b6dc  mov     rcx, [rsp+218h+Events]; Object
0x18000b6e1  test    rcx, rcx
0x18000b6e4  jz      short loc_18000B6F3
0x18000b6e6  call    cs:__imp_EvtClose
0x18000b6ed  nop     dword ptr [rax+rax+00h]
0x18000b6f2  nop
0x18000b6f3  mov     rcx, [rsp+218h+Buffer]
0x18000b6f8  test    rcx, rcx
0x18000b6fb  jz      short loc_18000B73E
0x18000b6fd  mov     rdx, [rsp+218h+var_1C0]
0x18000b702  sub     rdx, rcx
0x18000b705  mov     rax, rcx
0x18000b708  cmp     rdx, 1000h
0x18000b70f  jb      short loc_18000B72A
0x18000b711  add     rdx, 27h ; '''; unsigned __int64
0x18000b715  mov     rcx, [rcx-8]; void *
0x18000b719  sub     rax, rcx
0x18000b71c  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000b720  cmp     rax, 1Fh
0x18000b724  ja      loc_18000B95A
0x18000b72a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b72f  mov     [rsp+218h+Buffer], r15
0x18000b734  mov     [rsp+218h+var_1C8], r15
0x18000b739  mov     [rsp+218h+var_1C0], r15
0x18000b73e  test    rbx, rbx
0x18000b741  jz      short loc_18000B753
0x18000b743  mov     rcx, rbx; Object
0x18000b746  call    cs:__imp_EvtClose
0x18000b74d  nop     dword ptr [rax+rax+00h]
0x18000b752  nop
0x18000b753  mov     rcx, rsi; Object
0x18000b756  call    cs:__imp_EvtClose
0x18000b75d  nop     dword ptr [rax+rax+00h]
0x18000b762  nop
0x18000b763  mov     rcx, rdi; Object
0x18000b766  call    cs:__imp_EvtClose
0x18000b76d  nop     dword ptr [rax+rax+00h]
0x18000b772  mov     eax, r14d
0x18000b775  jmp     loc_18000C933
0x18000b77a  mov     r8d, [rsp+218h+BufferUsed]
0x18000b782  mov     r9, [rsp+218h+var_1C8]
0x18000b787  mov     rdx, r9
0x18000b78a  mov     rcx, [rsp+218h+Buffer]
0x18000b78f  sub     rdx, rcx
0x18000b792  cmp     r8, rdx
0x18000b795  jnb     short loc_18000B7A2
0x18000b797  lea     r9, [r8+rcx]
0x18000b79b  mov     [rsp+218h+var_1C8], r9
0x18000b7a0  jmp     short loc_18000B7E3
0x18000b7a2  jbe     short loc_18000B7E3
0x18000b7a4  mov     rax, [rsp+218h+var_1C0]
0x18000b7a9  sub     rax, rcx
0x18000b7ac  cmp     r8, rax
0x18000b7af  jbe     short loc_18000B7C5
0x18000b7b1  mov     rdx, r8
0x18000b7b4  lea     rcx, [rsp+218h+Buffer]
0x18000b7b9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000b7be  mov     r9, [rsp+218h+var_1C8]
0x18000b7c3  jmp     short loc_18000B7DE
0x18000b7c5  sub     r8, rdx; Size
0x18000b7c8  lea     r14, [r9+r8]
0x18000b7cc  xor     edx, edx; Val
0x18000b7ce  mov     rcx, r9; void *
0x18000b7d1  call    memset_0
0x18000b7d6  mov     r9, r14
0x18000b7d9  mov     [rsp+218h+var_1C8], r14
0x18000b7de  mov     rcx, [rsp+218h+Buffer]
0x18000b7e3  sub     r9, rcx; BufferSize
0x18000b7e6  lea     rax, [rsp+218h+var_178]
0x18000b7ee  mov     [rsp+218h+PropertyCount], rax; PropertyCount
0x18000b7f3  lea     rax, [rsp+218h+BufferUsed]
0x18000b7fb  mov     [rsp+218h+Returned], rax; BufferUsed
0x18000b800  mov     qword ptr [rsp+218h+Flags], rcx; Buffer
0x18000b805  xor     r8d, r8d; Flags
0x18000b808  mov     rdx, [rsp+218h+Events]; Fragment
0x18000b80d  mov     rcx, rsi; Context
0x18000b810  call    cs:__imp_EvtRender
0x18000b817  nop     dword ptr [rax+rax+00h]
0x18000b81c  test    eax, eax
0x18000b81e  jnz     loc_18000B8DE
0x18000b824  mov     rcx, [rsp+218h]; this
0x18000b82c  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b833  mov     edx, 162h; void *
0x18000b838  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b83d  mov     r14d, eax
0x18000b840  mov     rcx, [rsp+218h+Events]; Object
0x18000b845  test    rcx, rcx
0x18000b848  jz      short loc_18000B857
0x18000b84a  call    cs:__imp_EvtClose
0x18000b851  nop     dword ptr [rax+rax+00h]
0x18000b856  nop
0x18000b857  mov     rcx, [rsp+218h+Buffer]
0x18000b85c  test    rcx, rcx
0x18000b85f  jz      short loc_18000B8A2
0x18000b861  mov     rdx, [rsp+218h+var_1C0]
0x18000b866  sub     rdx, rcx
0x18000b869  mov     rax, rcx
0x18000b86c  cmp     rdx, 1000h
0x18000b873  jb      short loc_18000B88E
0x18000b875  add     rdx, 27h ; '''; unsigned __int64
0x18000b879  mov     rcx, [rcx-8]; void *
0x18000b87d  sub     rax, rcx
0x18000b880  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000b884  cmp     rax, 1Fh
0x18000b888  ja      loc_18000B95A
0x18000b88e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b893  mov     [rsp+218h+Buffer], r15
0x18000b898  mov     [rsp+218h+var_1C8], r15
0x18000b89d  mov     [rsp+218h+var_1C0], r15
0x18000b8a2  test    rbx, rbx
0x18000b8a5  jz      short loc_18000B8B7
0x18000b8a7  mov     rcx, rbx; Object
0x18000b8aa  call    cs:__imp_EvtClose
0x18000b8b1  nop     dword ptr [rax+rax+00h]
0x18000b8b6  nop
0x18000b8b7  mov     rcx, rsi; Object
0x18000b8ba  call    cs:__imp_EvtClose
0x18000b8c1  nop     dword ptr [rax+rax+00h]
0x18000b8c6  nop
0x18000b8c7  mov     rcx, rdi; Object
0x18000b8ca  call    cs:__imp_EvtClose
0x18000b8d1  nop     dword ptr [rax+rax+00h]
0x18000b8d6  mov     eax, r14d
0x18000b8d9  jmp     loc_18000C933
0x18000b8de  mov     rax, [rsp+218h+Buffer]
0x18000b8e3  cmp     dword ptr [rax+0Ch], 11h
0x18000b8e7  jz      loc_18000B9B7
0x18000b8ed  mov     rcx, [rsp+218h]; this
0x18000b8f5  mov     r14d, 8007000Dh
0x18000b8fb  mov     r9d, r14d; char *
0x18000b8fe  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000b905  mov     edx, 166h; void *
0x18000b90a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b90f  nop
0x18000b910  mov     rcx, [rsp+218h+Events]; Object
0x18000b915  test    rcx, rcx
0x18000b918  jz      short loc_18000B927
0x18000b91a  call    cs:__imp_EvtClose
0x18000b921  nop     dword ptr [rax+rax+00h]
0x18000b926  nop
  ... truncated ...
```
