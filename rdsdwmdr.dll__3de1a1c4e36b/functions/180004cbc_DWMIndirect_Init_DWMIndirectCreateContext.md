# DWMIndirect::Init(_DWMIndirectCreateContext)

- ea: `0x180004cbc`
- end: `0x1800052ba`
- name: `?Init@DWMIndirect@@QEAAJU_DWMIndirectCreateContext@@@Z`
- size: `1534`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004670`

## callees

- `0x1800010f8`
- `0x180001188`
- `0x180001290`
- `0x180001564`
- `0x18000160c`
- `0x180001724`
- `0x180003d7c`
- `0x180004cbc`
- `0x180005504`
- `0x180005918`
- `0x180005c20`
- `0x18000601c`
- `0x180006098`
- `0x180006124`
- `0x18000f7cc`
- `0x1800199f4`
- `0x18002b960`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005200`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180005200`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000523d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000523d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000518d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000518d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005148`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180005148`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000517a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000517a`
- `GDI32!CreatePen` at `0x180004ff2`
- `GDI32!CreatePen` at `0x18000500c`
- `GDI32!CreatePen` at `0x180005026`
- `GDI32!CreatePen` at `0x180004ff2`
- `GDI32!CreatePen` at `0x18000500c`
- `GDI32!CreatePen` at `0x180005026`
- `GDI32!CreateRectRgn` at `0x180004f32`
- `GDI32!CreateRectRgn` at `0x180004f32`
- `GDI32!SelectObject` at `0x180004f18`
- `GDI32!SelectObject` at `0x180004f18`
- `GDI32!CreateDIBSection` at `0x180004efe`
- `GDI32!CreateDIBSection` at `0x180004efe`
- `GDI32!CreateCompatibleDC` at `0x180004e8c`
- `GDI32!CreateCompatibleDC` at `0x180004e8c`
- `GDI32!__imp_DwmCreatedBitmapRemotingOutput` at `0x1800051a2`
- `GDI32!__imp_DwmCreatedBitmapRemotingOutput` at `0x1800051a2`
- `GDI32!__imp_CreateDCExW` at `0x180004e71`
- `GDI32!__imp_CreateDCExW` at `0x180004e71`

## string_xrefs

- `0x180004d23`: `Failed to get the global update processor`
- `0x18000505f`: `DWMDirect frame interval registry value not present`
- `0x1800051d1`: `DWMDirect frame dump registry value not present`
- `0x180005281`: `Using rdsdwmdr dump filepath of %s`

## pseudocode

```c
__int64 __fastcall DWMIndirect::Init(__int64 a1, __int64 a2)
{
  signed int DWMDirectGlobalUpdateProcessor; // eax
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  size_t *v8; // r8
  int v9; // r9d
  unsigned __int16 *v10; // r8
  DWMIndirect *v11; // rcx
  int DeviceTargetId; // eax
  int v13; // r8d
  int v14; // r9d
  __int64 DCExW; // rax
  unsigned int v16; // ebx
  HDC CompatibleDC; // rax
  LONG v18; // edx
  void *v19; // r8
  LONG v20; // ecx
  HBITMAP v21; // rax
  int v22; // r9d
  HRGN RectRgn; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  unsigned __int16 *v36; // rdx
  unsigned __int16 *v37; // rcx
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  DWORD TickCount; // eax
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  size_t cchToCopy; // [rsp+20h] [rbp-89h]
  unsigned int v49; // [rsp+50h] [rbp-59h] BYREF
  const char *v50; // [rsp+58h] [rbp-51h] BYREF
  const char *v51; // [rsp+60h] [rbp-49h] BYREF
  size_t v52; // [rsp+68h] [rbp-41h] BYREF
  const char *v53; // [rsp+70h] [rbp-39h] BYREF
  const char *v54; // [rsp+78h] [rbp-31h] BYREF
  BITMAPINFO pbmi; // [rsp+80h] [rbp-29h] BYREF
  GUID ActivityId; // [rsp+B0h] [rbp+7h] BYREF
  unsigned __int16 v57[8]; // [rsp+C0h] [rbp+17h] BYREF
  __int64 v58; // [rsp+D0h] [rbp+27h]

  memset(&pbmi, 0, sizeof(pbmi));
  DWMDirectGlobalUpdateProcessor = GetDWMDirectGlobalUpdateProcessor((struct IRdsDWMDirectUpdateProcessor **)(a1 + 912));
  if ( DWMDirectGlobalUpdateProcessor < 0 && (unsigned int)dword_180044008 > 3 )
  {
    v49 = DWMDirectGlobalUpdateProcessor;
    v51 = "Init";
    v53 = "Failed to get the global update processor";
    v52 = (size_t)"HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_180044008,
      (unsigned int)&word_18003790E,
      v5,
      v6,
      (__int64)&v52,
      (__int64)&v53,
      (__int64)&v49,
      (__int64)&v51);
  }
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, &stru_1800440EC);
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v52 = (size_t)"DWMIndirect::Init";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v7,
      (unsigned int)byte_1800378ED,
      (_DWORD)v8,
      v9,
      (__int64)&v52);
  }
  StringCopyWorkerW((STRSAFE_LPWSTR)(a1 + 836), 0x20u, v8, *(STRSAFE_PCNZWCH *)(a2 + 16), cchToCopy);
  *(_WORD *)(a1 + 898) = 0;
  RDSDWMDirectTraceLogging::LogDWMIndirectCreate(
    (RDSDWMDirectTraceLogging *)&stru_1800440EC,
    (struct _GUID *)(a1 + 836),
    v10);
  DeviceTargetId = DWMIndirect::QueryDeviceTargetId(
                     v11,
                     (const unsigned __int16 *)(a1 + 836),
                     (struct _LUID *)(a1 + 900),
                     (unsigned int *)(a1 + 908));
  if ( DeviceTargetId < 0 && (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v51) = DeviceTargetId;
    v54 = "Failed to query device target id";
    v53 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    v52 = (size_t)"Init";
    v49 = 555;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_180044008,
      (unsigned int)qword_1800378A8,
      v13,
      v14,
      (__int64)&v54,
      (__int64)&v51,
      (__int64)&v53,
      (__int64)&v49,
      (__int64)&v52);
  }
  DCExW = CreateDCExW(L"DISPLAY", *(_QWORD *)(a2 + 16), 0, 0, 1);
  *(_QWORD *)(a1 + 72) = DCExW;
  if ( !DCExW )
    goto LABEL_10;
  CompatibleDC = CreateCompatibleDC(0);
  *(_QWORD *)(a1 + 80) = CompatibleDC;
  if ( !CompatibleDC )
    goto LABEL_10;
  v18 = *(_DWORD *)(a2 + 28);
  v19 = *(void **)a2;
  v20 = *(_DWORD *)(a2 + 24);
  *(_QWORD *)(a1 + 64) = *(_QWORD *)a2;
  *(_DWORD *)(a1 + 108) = v18;
  *(_DWORD *)(a1 + 104) = v20;
  if ( v18 && v20 > 0 )
  {
    pbmi.bmiHeader.biWidth = v20;
    pbmi.bmiHeader.biHeight = v18;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v21 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)(a1 + 96), v19, 0);
    *(_QWORD *)(a1 + 88) = v21;
    if ( !v21 )
    {
LABEL_10:
      v16 = -2147467259;
      goto LABEL_38;
    }
    SelectObject(*(HDC *)(a1 + 80), v21);
    v22 = *(_DWORD *)(a1 + 108);
    if ( v22 < 0 )
      v22 = -v22;
    RectRgn = CreateRectRgn(0, 0, *(_DWORD *)(a1 + 104), v22);
    *(_QWORD *)(a1 + 824) = RectRgn;
    if ( !RectRgn )
    {
      v16 = -2147467261;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v52 = (size_t)"Init";
        v54 = "HRGN";
        LODWORD(v51) = 627;
        v53 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
        v50 = "Unexpected NULL object";
        v49 = -2147467261;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v24,
          (unsigned int)byte_18003785D,
          v25,
          v26,
          (__int64)&v50,
          (__int64)&v49,
          (__int64)&v53,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&v54);
      }
      goto LABEL_38;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 824) = 0;
  }
  *(_QWORD *)(a1 + 232) = CreatePen(0, 2, 0xFFu);
  *(_QWORD *)(a1 + 240) = CreatePen(0, 2, 0xFF00u);
  *(_QWORD *)(a1 + 248) = CreatePen(0, 2, 0xFF0000u);
  if ( (int)ReadRegistryUINT(
              L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
              L"DWMFRAMEINTERVAL",
              (unsigned int *)(a1 + 832),
              v27) < 0
    && (unsigned int)dword_180044008 > 3 )
  {
    v50 = "DWMDirect frame interval registry value not present";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v28,
      (unsigned int)&dword_18003783C,
      v29,
      v30,
      (__int64)&v50);
  }
  if ( (int)ReadRegistryUINT(
              L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
              L"DwmDirectRenderingFlags",
              &g_uiDwmDirectRenderingFlags,
              v30) < 0
    && (unsigned int)dword_180044008 > 3 )
  {
    v50 = "DWMDirect rendering flags not present";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v31,
      (unsigned int)byte_18003781B,
      v32,
      v33,
      (__int64)&v50);
  }
  if ( (unsigned int)dword_180044008 > 4 )
  {
    LODWORD(v51) = *(_DWORD *)(a1 + 832);
    v50 = "DWM Direct Frame Interval %d";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v31,
      (unsigned int)byte_1800377EB,
      v32,
      v33,
      (__int64)&v50,
      (__int64)&v51);
  }
  if ( (unsigned int)dword_180044008 > 4 )
  {
    LODWORD(v51) = g_uiDwmDirectRenderingFlags;
    v50 = "DWM Direct rendering flags 0x%x";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v31,
      (unsigned int)byte_1800377BD,
      v32,
      v33,
      (__int64)&v50,
      (__int64)&v51);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 120) = EventW;
  if ( !EventW )
    goto LABEL_10;
  Thread = CreateThread(0, 0, DWMIndirect::SyncThread, (LPVOID)a1, 0, 0);
  *(_QWORD *)(a1 + 112) = Thread;
  if ( !Thread )
  {
    CloseHandle(*(HANDLE *)(a1 + 120));
    *(_QWORD *)(a1 + 120) = 0;
    goto LABEL_10;
  }
  v16 = 0;
  DwmCreatedBitmapRemotingOutput();
  v49 = 260;
  if ( (int)ReadRegistrySTRING(v37, v36, (BYTE *)(a1 + 300), &v49) < 0 )
  {
    if ( (unsigned int)dword_180044008 > 3 )
    {
      v50 = "DWMDirect frame dump registry value not present";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v38,
        (unsigned int)&dword_18003779C,
        v39,
        v40,
        (__int64)&v50);
    }
    goto LABEL_37;
  }
  if ( !v49 )
  {
LABEL_37:
    *(_DWORD *)(a1 + 296) = 0;
    goto LABEL_38;
  }
  *(_OWORD *)v57 = 0;
  v58 = 0;
  TickCount = GetTickCount();
  StringCchPrintfW(v57, 0xCu, L"%u", TickCount);
  StringCchCatW((unsigned __int16 *)(a1 + 300), v43, v57);
  StringCchCatW((unsigned __int16 *)(a1 + 300), v44, L"_");
  if ( (unsigned int)dword_180044008 > 4 )
  {
    v50 = (const char *)(a1 + 300);
    v54 = "Using rdsdwmdr dump filepath of %s";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      v45,
      (unsigned int)byte_180037771,
      v46,
      v47,
      (__int64)&v54,
      (__int64)&v50);
  }
  *(_DWORD *)(a1 + 296) = 1;
LABEL_38:
  EventActivityIdControl(2u, &ActivityId);
  return v16;
}

```

## disassembly

```asm
0x180004cbc  mov     [rsp-8+arg_10], rbx
0x180004cc1  push    rbp
0x180004cc2  push    rsi
0x180004cc3  push    rdi
0x180004cc4  push    r12
0x180004cc6  push    r13
0x180004cc8  lea     rbp, [rsp-37h]
0x180004ccd  sub     rsp, 0E0h
0x180004cd4  mov     rax, cs:__security_cookie
0x180004cdb  xor     rax, rsp
0x180004cde  mov     [rbp+57h+var_28], rax
0x180004ce2  xorps   xmm0, xmm0
0x180004ce5  mov     rdi, rcx
0x180004ce8  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biCompression], xmm0
0x180004cec  add     rcx, 390h; struct IRdsDWMDirectUpdateProcessor **
0x180004cf3  mov     rsi, rdx
0x180004cf6  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x180004cfa  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSize], xmm0
0x180004cfe  call    ?GetDWMDirectGlobalUpdateProcessor@@YAJPEAPEAUIRdsDWMDirectUpdateProcessor@@@Z; GetDWMDirectGlobalUpdateProcessor(IRdsDWMDirectUpdateProcessor * *)
0x180004d03  lea     r12, aInit; "Init"
0x180004d0a  test    eax, eax
0x180004d0c  jns     short loc_180004D66
0x180004d0e  mov     ecx, cs:dword_180044008
0x180004d14  cmp     ecx, 3
0x180004d17  jbe     short loc_180004D66
0x180004d19  mov     [rbp+57h+var_B0], eax
0x180004d1c  lea     rdx, word_18003790E
0x180004d23  lea     rax, aFailedToGetThe_2; "Failed to get the global update process"...
0x180004d2a  mov     [rbp+57h+var_A0], r12
0x180004d2e  mov     [rbp+57h+var_90], rax
0x180004d32  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180004d39  mov     [rbp+57h+var_98], rax
0x180004d3d  lea     rax, [rbp+57h+var_A0]
0x180004d41  mov     [rsp+100h+var_C8], rax
0x180004d46  lea     rax, [rbp+57h+var_B0]
0x180004d4a  mov     [rsp+100h+var_D0], rax
0x180004d4f  lea     rax, [rbp+57h+var_90]
0x180004d53  mov     qword ptr [rsp+100h+offset], rax
0x180004d58  lea     rax, [rbp+57h+var_98]
0x180004d5c  mov     [rsp+100h+cchToCopy], rax
0x180004d61  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180004d66  lea     rdx, stru_1800440EC; struct _GUID *
0x180004d6d  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180004d71  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180004d76  mov     eax, cs:dword_180044008
0x180004d7c  cmp     eax, 4
0x180004d7f  jbe     short loc_180004DA1
0x180004d81  lea     rax, aDwmindirectIni; "DWMIndirect::Init"
0x180004d88  mov     [rbp+57h+var_98], rax
0x180004d8c  lea     rdx, byte_1800378ED
0x180004d93  lea     rax, [rbp+57h+var_98]
0x180004d97  mov     [rsp+100h+cchToCopy], rax; cchToCopy
0x180004d9c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180004da1  mov     r9, [rsi+10h]; pszSrc
0x180004da5  lea     rbx, [rdi+344h]
0x180004dac  mov     rcx, rbx; pszDest
0x180004daf  mov     edx, 20h ; ' '; cchDest
0x180004db4  call    StringCopyWorkerW
0x180004db9  xor     r11d, r11d
0x180004dbc  lea     rcx, stru_1800440EC; this
0x180004dc3  mov     rdx, rbx; struct _GUID *
0x180004dc6  mov     [rdi+382h], r11w
0x180004dce  call    ?LogDWMIndirectCreate@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAG@Z; RDSDWMDirectTraceLogging::LogDWMIndirectCreate(_GUID *,ushort *)
0x180004dd3  lea     r9, [rdi+38Ch]; unsigned int *
0x180004dda  mov     rdx, rbx; unsigned __int16 *
0x180004ddd  lea     r8, [rdi+384h]; struct _LUID *
0x180004de4  call    ?QueryDeviceTargetId@DWMIndirect@@IEAAJPEBGPEAU_LUID@@PEAI@Z; DWMIndirect::QueryDeviceTargetId(ushort const *,_LUID *,uint *)
0x180004de9  lea     rdx, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180004df0  test    eax, eax
0x180004df2  jns     short loc_180004E55
0x180004df4  mov     ecx, cs:dword_180044008
0x180004dfa  cmp     ecx, 2
0x180004dfd  jbe     short loc_180004E55
0x180004dff  mov     dword ptr [rbp+57h+var_A0], eax
0x180004e02  lea     rax, aFailedToQueryD; "Failed to query device target id"
0x180004e09  mov     [rbp+57h+var_88], rax
0x180004e0d  lea     rax, [rbp+57h+var_98]
0x180004e11  mov     [rsp+100h+var_C0], rax
0x180004e16  lea     rax, [rbp+57h+var_B0]
0x180004e1a  mov     [rsp+100h+var_C8], rax
0x180004e1f  lea     rax, [rbp+57h+var_90]
0x180004e23  mov     [rsp+100h+var_D0], rax
0x180004e28  lea     rax, [rbp+57h+var_A0]
0x180004e2c  mov     qword ptr [rsp+100h+offset], rax
0x180004e31  lea     rax, [rbp+57h+var_88]
0x180004e35  mov     [rbp+57h+var_90], rdx
0x180004e39  lea     rdx, qword_1800378A8
0x180004e40  mov     [rsp+100h+cchToCopy], rax
0x180004e45  mov     [rbp+57h+var_98], r12
0x180004e49  mov     [rbp+57h+var_B0], 22Bh
0x180004e50  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180004e55  mov     rdx, [rsi+10h]
0x180004e59  lea     rcx, aDisplay; "DISPLAY"
0x180004e60  mov     r13d, 1
0x180004e66  xor     r9d, r9d
0x180004e69  xor     r8d, r8d
0x180004e6c  mov     dword ptr [rsp+100h+cchToCopy], r13d
0x180004e71  call    cs:__imp_CreateDCExW
0x180004e77  mov     [rdi+48h], rax
0x180004e7b  test    rax, rax
0x180004e7e  jnz     short loc_180004E8A
0x180004e80  mov     ebx, 80004005h
0x180004e85  jmp     loc_1800051F7
0x180004e8a  xor     ecx, ecx; hdc
0x180004e8c  call    cs:__imp_CreateCompatibleDC
0x180004e92  mov     [rdi+50h], rax
0x180004e96  test    rax, rax
0x180004e99  jz      short loc_180004E80
0x180004e9b  mov     edx, [rsi+1Ch]
0x180004e9e  mov     r8, [rsi]
0x180004ea1  mov     ecx, [rsi+18h]
0x180004ea4  mov     [rdi+40h], r8
0x180004ea8  mov     [rdi+6Ch], edx
0x180004eab  mov     [rdi+68h], ecx
0x180004eae  test    edx, edx
0x180004eb0  jz      loc_180004FD2
0x180004eb6  test    ecx, ecx
0x180004eb8  jle     loc_180004FD2
0x180004ebe  xorps   xmm0, xmm0
0x180004ec1  mov     [rbp+57h+pbmi.bmiHeader.biWidth], ecx
0x180004ec4  mov     [rbp+57h+pbmi.bmiHeader.biHeight], edx
0x180004ec7  lea     r9, [rdi+60h]; ppvBits
0x180004ecb  mov     [rsp+100h+offset], 0; offset
0x180004ed3  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180004ed7  mov     [rsp+100h+cchToCopy], r8; hSection
0x180004edc  mov     rcx, rax; hdc
0x180004edf  xor     r8d, r8d; usage
0x180004ee2  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x180004eea  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180004eef  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x180004ef6  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180004efe  call    cs:__imp_CreateDIBSection
0x180004f04  mov     [rdi+58h], rax
0x180004f08  test    rax, rax
0x180004f0b  jz      loc_180004E80
0x180004f11  mov     rcx, [rdi+50h]; hdc
0x180004f15  mov     rdx, rax; h
0x180004f18  call    cs:__imp_SelectObject
0x180004f1e  mov     r9d, [rdi+6Ch]
0x180004f22  xor     edx, edx; y1
0x180004f24  mov     r8d, [rdi+68h]; x2
0x180004f28  xor     ecx, ecx; x1
0x180004f2a  test    r9d, r9d
0x180004f2d  jns     short loc_180004F32
0x180004f2f  neg     r9d; y2
0x180004f32  call    cs:__imp_CreateRectRgn
0x180004f38  mov     [rdi+338h], rax
0x180004f3f  test    rax, rax
0x180004f42  jnz     loc_180004FE5
0x180004f48  mov     eax, cs:dword_180044008
0x180004f4e  mov     ebx, 80004003h
0x180004f53  cmp     eax, 2
0x180004f56  jbe     loc_1800051F7
0x180004f5c  lea     rax, aHrgn; "HRGN"
0x180004f63  mov     [rbp+57h+var_98], r12
0x180004f67  mov     [rbp+57h+var_88], rax
0x180004f6b  lea     rdx, byte_18003785D
0x180004f72  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180004f79  mov     dword ptr [rbp+57h+var_A0], 273h
0x180004f80  mov     [rbp+57h+var_90], rax
0x180004f84  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180004f8b  mov     [rbp+57h+var_A8], rax
0x180004f8f  lea     rax, [rbp+57h+var_88]
0x180004f93  mov     [rsp+100h+var_B8], rax
0x180004f98  lea     rax, [rbp+57h+var_98]
0x180004f9c  mov     [rsp+100h+var_C0], rax
0x180004fa1  lea     rax, [rbp+57h+var_A0]
0x180004fa5  mov     [rsp+100h+var_C8], rax
0x180004faa  lea     rax, [rbp+57h+var_90]
0x180004fae  mov     [rsp+100h+var_D0], rax
0x180004fb3  lea     rax, [rbp+57h+var_B0]
0x180004fb7  mov     qword ptr [rsp+100h+offset], rax
0x180004fbc  lea     rax, [rbp+57h+var_A8]
0x180004fc0  mov     [rsp+100h+cchToCopy], rax
0x180004fc5  mov     [rbp+57h+var_B0], ebx
0x180004fc8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180004fcd  jmp     loc_1800051F7
0x180004fd2  mov     qword ptr [rdi+58h], 0
0x180004fda  mov     qword ptr [rdi+338h], 0
0x180004fe5  mov     edx, 2; cWidth
0x180004fea  xor     ecx, ecx; iStyle
0x180004fec  mov     r8d, 0FFh; color
0x180004ff2  call    cs:__imp_CreatePen
0x180004ff8  mov     edx, 2; cWidth
0x180004ffd  xor     ecx, ecx; iStyle
0x180004fff  mov     r8d, 0FF00h; color
0x180005005  mov     [rdi+0E8h], rax
0x18000500c  call    cs:__imp_CreatePen
0x180005012  mov     edx, 2; cWidth
0x180005017  xor     ecx, ecx; iStyle
0x180005019  mov     r8d, 0FF0000h; color
0x18000501f  mov     [rdi+0F0h], rax
0x180005026  call    cs:__imp_CreatePen
0x18000502c  lea     rbx, [rdi+340h]
0x180005033  mov     [rdi+0F8h], rax
0x18000503a  mov     r8, rbx; unsigned int *
0x18000503d  lea     rdx, aDwmframeinterv; "DWMFRAMEINTERVAL"
0x180005044  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18000504b  call    ?ReadRegistryUINT@@YAJPEAG0PEAI@Z; ReadRegistryUINT(ushort *,ushort *,uint *)
0x180005050  test    eax, eax
0x180005052  jns     short loc_18000507F
0x180005054  mov     eax, cs:dword_180044008
0x18000505a  cmp     eax, 3
0x18000505d  jbe     short loc_18000507F
0x18000505f  lea     rax, aDwmdirectFrame_0; "DWMDirect frame interval registry value"...
0x180005066  mov     [rbp+57h+var_A8], rax
0x18000506a  lea     rdx, dword_18003783C
0x180005071  lea     rax, [rbp+57h+var_A8]
0x180005075  mov     [rsp+100h+cchToCopy], rax
0x18000507a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000507f  lea     r8, ?g_uiDwmDirectRenderingFlags@@3IA; unsigned int *
0x180005086  lea     rdx, aDwmdirectrende; "DwmDirectRenderingFlags"
0x18000508d  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180005094  call    ?ReadRegistryUINT@@YAJPEAG0PEAI@Z; ReadRegistryUINT(ushort *,ushort *,uint *)
0x180005099  test    eax, eax
0x18000509b  jns     short loc_1800050C8
0x18000509d  mov     eax, cs:dword_180044008
0x1800050a3  cmp     eax, 3
0x1800050a6  jbe     short loc_1800050C8
0x1800050a8  lea     rax, aDwmdirectRende; "DWMDirect rendering flags not present"
0x1800050af  mov     [rbp+57h+var_A8], rax
0x1800050b3  lea     rdx, byte_18003781B
0x1800050ba  lea     rax, [rbp+57h+var_A8]
0x1800050be  mov     [rsp+100h+cchToCopy], rax
0x1800050c3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800050c8  mov     eax, cs:dword_180044008
0x1800050ce  cmp     eax, 4
0x1800050d1  jbe     short loc_180005101
0x1800050d3  mov     eax, [rbx]
0x1800050d5  lea     rdx, byte_1800377EB
0x1800050dc  mov     dword ptr [rbp+57h+var_A0], eax
0x1800050df  lea     rax, aDwmDirectFrame; "DWM Direct Frame Interval %d"
0x1800050e6  mov     [rbp+57h+var_A8], rax
0x1800050ea  lea     rax, [rbp+57h+var_A0]
0x1800050ee  mov     qword ptr [rsp+100h+offset], rax
0x1800050f3  lea     rax, [rbp+57h+var_A8]
0x1800050f7  mov     [rsp+100h+cchToCopy], rax
0x1800050fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180005101  mov     eax, cs:dword_180044008
0x180005107  cmp     eax, 4
0x18000510a  jbe     short loc_18000513E
0x18000510c  mov     eax, cs:?g_uiDwmDirectRenderingFlags@@3IA; uint g_uiDwmDirectRenderingFlags
0x180005112  lea     rdx, byte_1800377BD
0x180005119  mov     dword ptr [rbp+57h+var_A0], eax
0x18000511c  lea     rax, aDwmDirectRende; "DWM Direct rendering flags 0x%x"
0x180005123  mov     [rbp+57h+var_A8], rax
0x180005127  lea     rax, [rbp+57h+var_A0]
0x18000512b  mov     qword ptr [rsp+100h+offset], rax
0x180005130  lea     rax, [rbp+57h+var_A8]
0x180005134  mov     [rsp+100h+cchToCopy], rax
0x180005139  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000513e  xor     r9d, r9d; lpName
0x180005141  xor     r8d, r8d; bInitialState
0x180005144  xor     edx, edx; bManualReset
0x180005146  xor     ecx, ecx; lpEventAttributes
0x180005148  call    cs:__imp_CreateEventW
0x18000514e  mov     [rdi+78h], rax
0x180005152  test    rax, rax
0x180005155  jz      loc_180004E80
0x18000515b  mov     qword ptr [rsp+100h+offset], 0; lpThreadId
0x180005164  lea     r8, ?SyncThread@DWMIndirect@@CAKPEAX@Z; lpStartAddress
0x18000516b  mov     r9, rdi; lpParameter
0x18000516e  mov     dword ptr [rsp+100h+cchToCopy], 0; dwCreationFlags
0x180005176  xor     edx, edx; dwStackSize
0x180005178  xor     ecx, ecx; lpThreadAttributes
0x18000517a  call    cs:__imp_CreateThread
0x180005180  mov     [rdi+70h], rax
0x180005184  test    rax, rax
0x180005187  jnz     short loc_1800051A0
0x180005189  mov     rcx, [rdi+78h]; hObject
0x18000518d  call    cs:__imp_CloseHandle
0x180005193  mov     qword ptr [rdi+78h], 0
0x18000519b  jmp     loc_180004E80
0x1800051a0  xor     ebx, ebx
0x1800051a2  call    cs:__imp_DwmCreatedBitmapRemotingOutput
0x1800051a8  lea     rsi, [rdi+12Ch]
0x1800051af  mov     [rbp+57h+var_B0], 104h
0x1800051b6  mov     r8, rsi; unsigned __int16 *
0x1800051b9  lea     r9, [rbp+57h+var_B0]; unsigned int *
0x1800051bd  call    ?ReadRegistrySTRING@@YAJPEAG00PEAK@Z; ReadRegistrySTRING(ushort *,ushort *,ushort *,ulong *)
0x1800051c2  test    eax, eax
0x1800051c4  jns     short loc_18000522B
0x1800051c6  mov     eax, cs:dword_180044008
0x1800051cc  cmp     eax, 3
0x1800051cf  jbe     short loc_1800051F1
0x1800051d1  lea     rax, aDwmdirectFrame; "DWMDirect frame dump registry value not"...
0x1800051d8  mov     [rbp+57h+var_A8], rax
0x1800051dc  lea     rdx, dword_18003779C
0x1800051e3  lea     rax, [rbp+57h+var_A8]
0x1800051e7  mov     [rsp+100h+cchToCopy], rax
0x1800051ec  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800051f1  mov     [rdi+128h], ebx
0x1800051f7  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800051fb  mov     ecx, 2; ControlCode
0x180005200  call    cs:__imp_EventActivityIdControl
0x180005206  mov     eax, ebx
0x180005208  mov     rcx, [rbp+57h+var_28]
0x18000520c  xor     rcx, rsp; StackCookie
0x18000520f  call    __security_check_cookie
0x180005214  mov     rbx, [rsp+100h+arg_10]
  ... truncated ...
```
