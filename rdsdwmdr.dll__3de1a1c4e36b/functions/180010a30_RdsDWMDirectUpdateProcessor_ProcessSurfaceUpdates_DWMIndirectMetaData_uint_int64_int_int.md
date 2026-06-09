# RdsDWMDirectUpdateProcessor::ProcessSurfaceUpdates(_DWMIndirectMetaData *,uint,__int64,int *,int *)

- ea: `0x180010a30`
- end: `0x1800117a5`
- name: `?ProcessSurfaceUpdates@RdsDWMDirectUpdateProcessor@@UEAAJPEAU_DWMIndirectMetaData@@I_JPEAH2@Z`
- size: `3445`
- prototype: `__int64 __usercall@<rax>(RdsDWMDirectUpdateProcessor *__hidden this@<rcx>, struct _DWMIndirectMetaData *@<rdx>, unsigned int@<r8d>, __int64@<r9>, int *, int *)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800010f8`
- `0x180001564`
- `0x180001724`
- `0x180001f98`
- `0x180005f9c`
- `0x18000f52c`
- `0x18000f670`
- `0x18000f950`
- `0x18000fcb8`
- `0x18000fcdc`
- `0x18000fe68`
- `0x18000fff0`
- `0x1800103d8`
- `0x18001054c`
- `0x180010724`
- `0x1800108a8`
- `0x180010a30`
- `0x1800117ac`
- `0x18001196c`
- `0x180011b08`
- `0x180019d58`

## string_xrefs

- `0x180010b87`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010d06`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010da4`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010e4a`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010f1c`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010fb1`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011058`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800110fc`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800111bf`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011248`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800112b8`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18001135a`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800113e3`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180011462`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800114eb`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x18001156a`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800115e9`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x1800116ad`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010a70`: `RdsDWMDirectUpdateProcessor::ProcessSurfaceUpdates`
- `0x180010adb`: `Ignoring DWMDR_Metadata_WriteToScreen metadata.`
- `0x180010b7c`: `ProcessSurfaceUpdates`
- `0x180010cfb`: `ProcessSurfaceUpdates`
- `0x180010d99`: `ProcessSurfaceUpdates`
- `0x180010e3f`: `ProcessSurfaceUpdates`
- `0x180010f11`: `ProcessSurfaceUpdates`
- `0x180010fa6`: `ProcessSurfaceUpdates`
- `0x18001104d`: `ProcessSurfaceUpdates`
- `0x1800110f1`: `ProcessSurfaceUpdates`
- `0x1800111b1`: `ProcessSurfaceUpdates`
- `0x18001123a`: `ProcessSurfaceUpdates`
- `0x1800112ad`: `ProcessSurfaceUpdates`
- `0x18001134c`: `ProcessSurfaceUpdates`
- `0x1800113d5`: `ProcessSurfaceUpdates`
- `0x180011457`: `ProcessSurfaceUpdates`
- `0x1800114dd`: `ProcessSurfaceUpdates`
- `0x18001155f`: `ProcessSurfaceUpdates`
- `0x1800115de`: `ProcessSurfaceUpdates`
- `0x1800116a2`: `ProcessSurfaceUpdates`
- `0x18001164e`: `Ignoring metadata type %d - processor not ready.`
- `0x180011734`: `Ignoring metadata type %d - processor not ready.`
- `0x180011689`: `Failed send a StartOfFrame - ignoring the rest of the updates.`
- `0x1800115c5`: `Failed to retrieve or create a window context`
- `0x1800114c4`: `Composition handle received before vail mode enabled`
- `0x180010ef8`: `Failed to process composition surface metadata`
- `0x1800113bc`: `VAIL Create Super Wet Ink message received before vail mode enabled`
- `0x180010e26`: `Failed to process VAIL Create Super Wet Ink metadata`
- `0x180011221`: `Composition window dpi received before vail mode enabled`
- `0x180010ce2`: `Failed to process composition window dpi metadata`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessSurfaceUpdates(
        RdsDWMDirectUpdateProcessor *this,
        struct _DWMIndirectMetaData *a2,
        unsigned __int16 *a3,
        __int64 a4,
        RdsDWMDirectUpdateProcessor *a5,
        const char *a6)
{
  RdsDWMDirectUpdateProcessor *v6; // rdi
  int WindowContext; // ebx
  char *v8; // r13
  unsigned int v9; // r12d
  __int64 v12; // r15
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  char *v18; // rdx
  const char **v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  RdsDWMDirectUpdateProcessor *v26; // rcx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  RdsDWMDirectUpdateProcessor *v31; // rcx
  __int64 v32; // rcx
  RdsDWMDirectUpdateProcessor *v33; // rcx
  struct RdpDWMDirectWindowContext *v34; // rdx
  struct RdpDWMDirectWindowContext *v35; // rdx
  RdsDWMDirectUpdateProcessor *v36; // rcx
  struct RdpDWMDirectWindowContext *v37; // rdx
  int *v38; // rdx
  const char *v39; // rax
  __int64 result; // rax
  const char **v41; // [rsp+40h] [rbp-30h]
  struct RdpDWMDirectWindowContext *v42; // [rsp+50h] [rbp-20h] BYREF
  const char *v43; // [rsp+58h] [rbp-18h] BYREF
  const char *v44; // [rsp+60h] [rbp-10h] BYREF
  const char *v45; // [rsp+68h] [rbp-8h] BYREF
  const char *v46; // [rsp+B0h] [rbp+40h] BYREF
  int v47; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v48; // [rsp+C8h] [rbp+58h]

  v48 = a4;
  v6 = a5;
  WindowContext = 0;
  v8 = (char *)a6;
  v9 = (unsigned int)a3;
  *(_DWORD *)a5 = 0;
  *(_DWORD *)v8 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    a6 = "RdsDWMDirectUpdateProcessor::ProcessSurfaceUpdates";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)&word_18003B48E,
      (__int64)a3,
      a4,
      (const unsigned __int16 **)&a6);
  }
  v12 = 0;
  v13 = 1;
  if ( !v9 )
    goto LABEL_97;
  while ( 1 )
  {
    v42 = 0;
    v14 = *((_DWORD *)a2 + 18 * v12);
    switch ( v14 )
    {
      case 5:
        *((_DWORD *)this + 30) = 0;
        RdsDWMDirectUpdateProcessor::ProcessEndOfFrame(this);
LABEL_6:
        WindowContext = 0;
        goto LABEL_63;
      case 3:
        if ( (unsigned int)dword_180044008 > 4 )
        {
          a6 = "Ignoring DWMDR_Metadata_WriteToScreen metadata.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (__int64)this,
            (__int64)byte_18003B46D,
            (__int64)a3,
            a4,
            (const unsigned __int16 **)&a6);
        }
        goto LABEL_6;
      case 7:
        RDSDWMDirectTraceLogging::LogVAILModeState(
          (RdsDWMDirectUpdateProcessor *)((char *)this + 92),
          (struct _GUID *)&stru_1800317F0,
          a3);
        *((_DWORD *)this + 43) = 1;
        *(_DWORD *)v8 = 1;
        goto LABEL_63;
    }
    if ( v14 != 11 )
      break;
    if ( !*((_DWORD *)this + 42) )
    {
      if ( !*((_DWORD *)this + 43) )
      {
        WindowContext = -2147418113;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v47 = 647;
          v46 = "DWMDR_Metadata_VailMMCSS received before vail mode enabled";
          LODWORD(a6) = -2147418113;
          v45 = "ProcessSurfaceUpdates";
          v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
          v43 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            2147549183LL,
            (__int64)byte_18003B3D3,
            (__int64)a3,
            a4,
            (const unsigned __int16 **)&v43,
            (__int64)&a6,
            (const unsigned __int16 **)&v44,
            (__int64)&v47,
            (const unsigned __int16 **)&v45,
            (const unsigned __int16 **)&v46);
        }
        goto LABEL_95;
      }
      *((_DWORD *)this + 44) = *((unsigned __int8 *)a2 + 72 * v12 + 16);
      goto LABEL_6;
    }
    WindowContext = RdsDWMDirectUpdateProcessor::EnableVailMMCSS(
                      this,
                      *((unsigned __int8 *)a2 + 72 * v12 + 16),
                      (__int64)a3,
                      a4);
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 <= 2 )
        goto LABEL_95;
      v47 = 637;
      v46 = "DWMDR_Metadata_VailMMCSS failure calling EnableVailMMCSS";
      v18 = (char *)qword_18003B420;
      v43 = "ProcessSurfaceUpdates";
      v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v45 = "Error HResult failed";
      v41 = &v43;
      v19 = &v45;
      goto LABEL_17;
    }
LABEL_63:
    TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v42);
    v13 = 1;
    v12 = (unsigned int)(v12 + 1);
    if ( (unsigned int)v12 >= v9 )
      goto LABEL_96;
  }
  if ( !RdsDWMDirectUpdateProcessor::IsHiDefProcessorReady(this) )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v38 = &dword_18003B3A4;
      v47 = *((_DWORD *)a2 + 18 * v12);
      v39 = "Ignoring metadata type %d - processor not ready.";
      goto LABEL_93;
    }
LABEL_94:
    WindowContext = 0;
    goto LABEL_95;
  }
  if ( *((_DWORD *)this + 41) )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v38 = (int *)byte_18003B375;
      v47 = *((_DWORD *)a2 + 18 * v12);
      v39 = "Ignoring metadata type %d - we are in the process of session disconnect.";
LABEL_93:
      a6 = v39;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v20,
        (__int64)v38,
        v21,
        v22,
        (const unsigned __int16 **)&a6,
        (__int64)&v47);
      goto LABEL_94;
    }
    goto LABEL_94;
  }
  WindowContext = RdsDWMDirectUpdateProcessor::ProcessStartOfFrame(this, v48, 0);
  if ( WindowContext < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v47 = 691;
      v46 = "Failed send a StartOfFrame - ignoring the rest of the updates.";
      v18 = (char *)qword_18003B328;
      v45 = "ProcessSurfaceUpdates";
      v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v43 = "Error HResult failed";
      v41 = &v45;
      v19 = &v43;
      goto LABEL_17;
    }
    goto LABEL_95;
  }
  if ( !RdsDWMDirectUpdateProcessor::IsHiDefProcessorReady(this) )
  {
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v47 = *((_DWORD *)a2 + 18 * v12);
      a6 = "Ignoring metadata type %d - processor not ready.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v23,
        (__int64)byte_18003B2F9,
        v24,
        v25,
        (const unsigned __int16 **)&a6,
        (__int64)&v47);
    }
    WindowContext = -2147483638;
    goto LABEL_95;
  }
  WindowContext = RdsDWMDirectUpdateProcessor::GetWindowContext((__int64)this, *((HWND *)a2 + 9 * v12 + 1), &v42, v25);
  if ( WindowContext < 0 )
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v47 = 705;
      v46 = "Failed to retrieve or create a window context";
      v18 = (char *)&dword_18003B2AC;
      v45 = "ProcessSurfaceUpdates";
      v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v43 = "Error HResult failed";
      v41 = &v45;
      v19 = &v43;
      goto LABEL_17;
    }
    goto LABEL_95;
  }
  v26 = (RdsDWMDirectUpdateProcessor *)*((unsigned int *)a2 + 18 * v12);
  if ( !(_DWORD)v26 )
  {
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessWindowGeometry(
                      v26,
                      v42,
                      (struct _DWMIndirectMetaData *)((char *)a2 + 72 * v12 + 16));
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 714;
        v46 = "Failed to process window geometry metadata";
        v18 = &byte_18003B25F;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
        goto LABEL_17;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  v27 = (_DWORD)v26 - 1;
  if ( !v27 )
  {
    v36 = a5;
    v37 = v42;
    *(_DWORD *)a5 = 1;
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessScrBlt(
                      v36,
                      v37,
                      (struct _DWMIndirectMetaData *)((char *)a2 + 72 * v12 + 16));
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 721;
        v46 = "Failed to process ScrBlt";
        v18 = (char *)word_18003B212;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
        goto LABEL_17;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  v28 = v27 - 1;
  if ( !v28 )
  {
    v35 = v42;
    *(_DWORD *)a5 = 1;
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessWindowDirtyRegion(
                      this,
                      v35,
                      (struct _DWMIndirectMetaData *)((char *)a2 + 72 * v12 + 16));
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 732;
        v46 = "Failed to process dirty region metadata";
        v18 = byte_18003B1C5;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
        goto LABEL_17;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  v29 = v28 - 2;
  if ( !v29 )
  {
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessWindowDestroy(this, v42);
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 737;
        v46 = "Failed to process window destroy metadata";
        v18 = (char *)qword_18003B178;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
        goto LABEL_17;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  v30 = v29 - 2;
  if ( !v30 )
  {
    if ( *((_DWORD *)this + 43) )
    {
      WindowContext = RdsDWMDirectUpdateProcessor::EnableVailMode(this);
      if ( WindowContext < 0 )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v47 = 745;
          v46 = "Failed enabling VAIL mode";
          v18 = byte_18003B12B;
          v45 = "ProcessSurfaceUpdates";
          v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
          v43 = "Error HResult failed";
          v41 = &v45;
          v19 = &v43;
          goto LABEL_17;
        }
        goto LABEL_95;
      }
      *((_DWORD *)this + 43) = 0;
    }
    if ( !*((_DWORD *)this + 42) )
    {
      WindowContext = -2147418113;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 750;
        v46 = "Composition handle received before vail mode enabled";
        LODWORD(a6) = -2147418113;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          2147549183LL,
          (__int64)&word_18003B0DE,
          v16,
          v17,
          (const unsigned __int16 **)&v43,
          (__int64)&a6,
          (const unsigned __int16 **)&v44,
          (__int64)&v47,
          (const unsigned __int16 **)&v45,
          (const unsigned __int16 **)&v46);
      }
      goto LABEL_95;
    }
    v33 = a5;
    v34 = v42;
    *(_DWORD *)a5 = 1;
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessCompositionSurface(
                      v33,
                      v34,
                      (struct _DWMIndirectMetaData *)((char *)a2 + 72 * v12 + 16));
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 758;
        v46 = "Failed to process composition surface metadata";
        v18 = byte_18003B091;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
        goto LABEL_17;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  v31 = (RdsDWMDirectUpdateProcessor *)(unsigned int)(v30 - 2);
  if ( !(_DWORD)v31 )
  {
    if ( !*((_DWORD *)this + 42) )
    {
      WindowContext = -2147418113;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 763;
        v46 = "VAIL Create Super Wet Ink message received before vail mode enabled";
        LODWORD(a6) = -2147418113;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          2147549183LL,
          (__int64)&dword_18003B044,
          v16,
          v17,
          (const unsigned __int16 **)&v43,
          (__int64)&a6,
          (const unsigned __int16 **)&v44,
          (__int64)&v47,
          (const unsigned __int16 **)&v45,
          (const unsigned __int16 **)&v46);
      }
      goto LABEL_95;
    }
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk(
                      v31,
                      v42,
                      (struct _DWMIndirectMetaData *)((char *)a2 + 72 * v12 + 16));
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 769;
        v46 = "Failed to process VAIL Create Super Wet Ink metadata";
        v18 = &byte_18003AFF7;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
        goto LABEL_17;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  v32 = (unsigned int)((_DWORD)v31 - 1);
  if ( (_DWORD)v32 )
  {
    if ( (_DWORD)v32 != 1 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = *((_DWORD *)a2 + 18 * v12);
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Unexpected metadata type";
        LODWORD(a6) = 794;
        LODWORD(v46) = WindowContext;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v32,
          (__int64)qword_18003AE70,
          v16,
          v17,
          (const unsigned __int16 **)&v43,
          (__int64)&v46,
          (const unsigned __int16 **)&v44,
          (__int64)&a6,
          (const unsigned __int16 **)&v45,
          (__int64)&v47);
      }
      WindowContext = -2147418113;
      goto LABEL_95;
    }
    if ( !*((_DWORD *)this + 42) )
    {
      WindowContext = -2147418113;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 784;
        v46 = "Composition window dpi received before vail mode enabled";
        LODWORD(a6) = -2147418113;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          2147549183LL,
          (__int64)qword_18003AF10,
          v16,
          v17,
          (const unsigned __int16 **)&v43,
          (__int64)&a6,
          (const unsigned __int16 **)&v44,
          (__int64)&v47,
          (const unsigned __int16 **)&v45,
          (const unsigned __int16 **)&v46);
      }
      goto LABEL_95;
    }
    WindowContext = RdsDWMDirectUpdateProcessor::ProcessCompositionWindowDpi(
                      (RdsDWMDirectUpdateProcessor *)v32,
                      v42,
                      (struct _DWMIndirectMetaData *)((char *)a2 + 72 * v12 + 16));
    if ( WindowContext < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v47 = 790;
        v46 = "Failed to process composition window dpi metadata";
        v18 = byte_18003AEC3;
        v45 = "ProcessSurfaceUpdates";
        v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        v43 = "Error HResult failed";
        v41 = &v45;
        v19 = &v43;
LABEL_17:
        LODWORD(a6) = WindowContext;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v15,
          (__int64)v18,
          v16,
          v17,
          (const unsigned __int16 **)v19,
          (__int64)&a6,
          (const unsigned __int16 **)&v44,
          (__int64)&v47,
          (const unsigned __int16 **)v41,
          (const unsigned __int16 **)&v46);
        goto LABEL_95;
      }
      goto LABEL_95;
    }
    goto LABEL_63;
  }
  if ( !*((_DWORD *)this + 42) )
  {
    WindowContext = -2147418113;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v47 = 774;
      v46 = "VAIL Destroy Super Wet Ink message received before vail mode enabled";
      LODWORD(a6) = -2147418113;
      v45 = "ProcessSurfaceUpdates";
      v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
      v43 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        2147549183LL,
        (__int64)word_18003AFAA,
        v16,
        v17,
        (const unsigned __int16 **)&v43,
        (__int64)&a6,
        (const unsigned __int16 **)&v44,
        (__int64)&v47,
        (const unsigned __int16 **)&v45,
        (const unsigned __int16 **)&v46);
    }
    goto LABEL_95;
  }
  WindowContext = RdsDWMDirectUpdateProcessor::ProcessDestroyVailSuperWetInk((RdsDWMDirectUpdateProcessor *)v32, v42);
  if ( WindowContext >= 0 )
    goto LABEL_63;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v47 = 779;
    v46 = "Failed to process VAIL Destroy Super Wet Ink metadata";
    v18 = byte_18003AF5D;
    v45 = "ProcessSurfaceUpdates";
    v44 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
    v43 = "Error HResult failed";
    v41 = &v45;
    v19 = &v43;
    goto LABEL_17;
  }
LABEL_95:
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v42);
  v13 = 1;
LABEL_96:
  v6 = a5;
LABEL_97:
  if ( !*((_DWORD *)this + 30) && !*(_DWORD *)v6 )
    v13 = 0;
  *((_DWORD *)this + 30) = v13;
  RdsDWMDirectUpdateProcessor::ProcessEndOfFrame(this);
  result = 0;
  if ( WindowContext != -2147483638 )
    return (unsigned int)WindowContext;
  return result;
}

```

## disassembly

```asm
0x180010a30  mov     [rsp-38h+arg_8], rbx
0x180010a35  mov     [rsp-38h+arg_18], r9
0x180010a3a  push    rbp
0x180010a3b  push    rsi
0x180010a3c  push    rdi
0x180010a3d  push    r12
0x180010a3f  push    r13
0x180010a41  push    r14
0x180010a43  push    r15
0x180010a45  mov     rbp, rsp
0x180010a48  sub     rsp, 70h
0x180010a4c  mov     rdi, [rbp+arg_20]
0x180010a50  xor     ebx, ebx
0x180010a52  mov     r13, [rbp+arg_28]
0x180010a56  mov     r12d, r8d
0x180010a59  mov     r14, rdx
0x180010a5c  mov     rsi, rcx
0x180010a5f  mov     [rdi], ebx
0x180010a61  mov     [r13+0], ebx
0x180010a65  mov     eax, cs:dword_180044008
0x180010a6b  cmp     eax, 5
0x180010a6e  jbe     short loc_180010A90
0x180010a70  lea     rax, aRdsdwmdirectup_8; "RdsDWMDirectUpdateProcessor::ProcessSur"...
0x180010a77  mov     [rbp+arg_28], rax
0x180010a7b  lea     rdx, word_18003B48E
0x180010a82  lea     rax, [rbp+arg_28]
0x180010a86  mov     [rsp+70h+var_50], rax
0x180010a8b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010a90  xor     r15d, r15d
0x180010a93  lea     eax, [r15+1]
0x180010a97  test    r12d, r12d
0x180010a9a  jz      loc_18001176A
0x180010aa0  lea     rdi, [r15+r15*8]
0x180010aa4  mov     [rbp+var_20], 0
0x180010aac  mov     eax, [r14+rdi*8]
0x180010ab0  cmp     eax, 5
0x180010ab3  jnz     short loc_180010ACB
0x180010ab5  mov     rcx, rsi; this
0x180010ab8  mov     dword ptr [rsi+78h], 0
0x180010abf  call    ?ProcessEndOfFrame@RdsDWMDirectUpdateProcessor@@IEAAXXZ; RdsDWMDirectUpdateProcessor::ProcessEndOfFrame(void)
0x180010ac4  xor     ebx, ebx
0x180010ac6  jmp     loc_180011163
0x180010acb  cmp     eax, 3
0x180010ace  jnz     short loc_180010AFD
0x180010ad0  mov     eax, cs:dword_180044008
0x180010ad6  cmp     eax, 4
0x180010ad9  jbe     short loc_180010AC4
0x180010adb  lea     rax, aIgnoringDwmdrM; "Ignoring DWMDR_Metadata_WriteToScreen m"...
0x180010ae2  mov     [rbp+arg_28], rax
0x180010ae6  lea     rdx, byte_18003B46D
0x180010aed  lea     rax, [rbp+arg_28]
0x180010af1  mov     [rsp+70h+var_50], rax
0x180010af6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010afb  jmp     short loc_180010AC4
0x180010afd  cmp     eax, 7
0x180010b00  jnz     short loc_180010B26
0x180010b02  lea     rcx, [rsi+5Ch]; this
0x180010b06  lea     rdx, stru_1800317F0; struct _GUID *
0x180010b0d  call    ?LogVAILModeState@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@PEAG@Z; RDSDWMDirectTraceLogging::LogVAILModeState(_GUID *,ushort *)
0x180010b12  mov     eax, 1
0x180010b17  mov     [rsi+0ACh], eax
0x180010b1d  mov     [r13+0], eax
0x180010b21  jmp     loc_180011163
0x180010b26  cmp     eax, 0Bh
0x180010b29  jnz     loc_180010BFE
0x180010b2f  cmp     dword ptr [rsi+0A8h], 0
0x180010b36  jz      loc_180010BE0
0x180010b3c  movzx   edx, byte ptr [r14+rdi*8+10h]; int
0x180010b42  mov     rcx, rsi; this
0x180010b45  call    ?EnableVailMMCSS@RdsDWMDirectUpdateProcessor@@IEAAJH@Z; RdsDWMDirectUpdateProcessor::EnableVailMMCSS(int)
0x180010b4a  mov     ebx, eax
0x180010b4c  test    eax, eax
0x180010b4e  jns     loc_180011163
0x180010b54  mov     eax, cs:dword_180044008
0x180010b5a  cmp     eax, 2
0x180010b5d  jbe     loc_180011758
0x180010b63  lea     rax, aDwmdrMetadataV; "DWMDR_Metadata_VailMMCSS failure callin"...
0x180010b6a  mov     [rbp+arg_10], 27Dh
0x180010b71  mov     [rbp+arg_0], rax
0x180010b75  lea     rdx, qword_18003B420
0x180010b7c  lea     rax, aProcesssurface; "ProcessSurfaceUpdates"
0x180010b83  mov     [rbp+var_18], rax
0x180010b87  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010b8e  mov     [rbp+var_10], rax
0x180010b92  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010b99  mov     [rbp+var_8], rax
0x180010b9d  lea     rax, [rbp+arg_0]
0x180010ba1  mov     [rsp+70h+var_28], rax
0x180010ba6  lea     rax, [rbp+var_18]
0x180010baa  mov     [rsp+70h+var_30], rax
0x180010baf  lea     rax, [rbp+arg_10]
0x180010bb3  mov     [rsp+70h+var_38], rax
0x180010bb8  lea     rax, [rbp+var_10]
0x180010bbc  mov     [rsp+70h+var_40], rax
0x180010bc1  lea     rax, [rbp+arg_28]
0x180010bc5  mov     [rsp+70h+var_48], rax
0x180010bca  lea     rax, [rbp+var_8]
0x180010bce  mov     dword ptr [rbp+arg_28], ebx
0x180010bd1  mov     [rsp+70h+var_50], rax
0x180010bd6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180010bdb  jmp     loc_180011758
0x180010be0  cmp     dword ptr [rsi+0ACh], 0
0x180010be7  jz      loc_180011182
0x180010bed  movzx   eax, byte ptr [r14+rdi*8+10h]
0x180010bf3  mov     [rsi+0B0h], eax
0x180010bf9  jmp     loc_180010AC4
0x180010bfe  mov     rcx, rsi; this
0x180010c01  call    ?IsHiDefProcessorReady@RdsDWMDirectUpdateProcessor@@IEAAHXZ; RdsDWMDirectUpdateProcessor::IsHiDefProcessorReady(void)
0x180010c06  test    eax, eax
0x180010c08  jz      loc_18001171B
0x180010c0e  cmp     dword ptr [rsi+0A4h], 0
0x180010c15  jnz     loc_1800116F9
0x180010c1b  mov     rdx, [rbp+arg_18]; __int64
0x180010c1f  xor     r8d, r8d; int *
0x180010c22  mov     rcx, rsi; this
0x180010c25  call    ?ProcessStartOfFrame@RdsDWMDirectUpdateProcessor@@IEAAJ_JPEAH@Z; RdsDWMDirectUpdateProcessor::ProcessStartOfFrame(__int64,int *)
0x180010c2a  mov     ebx, eax
0x180010c2c  test    eax, eax
0x180010c2e  js      loc_18001167A
0x180010c34  mov     rcx, rsi; this
0x180010c37  call    ?IsHiDefProcessorReady@RdsDWMDirectUpdateProcessor@@IEAAHXZ; RdsDWMDirectUpdateProcessor::IsHiDefProcessorReady(void)
0x180010c3c  test    eax, eax
0x180010c3e  jz      loc_180011635
0x180010c44  mov     rdx, [r14+rdi*8+8]; HWND
0x180010c49  lea     r8, [rbp+var_20]; struct RdpDWMDirectWindowContext **
0x180010c4d  mov     rcx, rsi; this
0x180010c50  call    ?GetWindowContext@RdsDWMDirectUpdateProcessor@@IEAAJPEAUHWND__@@PEAPEAVRdpDWMDirectWindowContext@@@Z; RdsDWMDirectUpdateProcessor::GetWindowContext(HWND__ *,RdpDWMDirectWindowContext * *)
0x180010c55  xor     edx, edx
0x180010c57  mov     ebx, eax
0x180010c59  test    eax, eax
0x180010c5b  js      loc_1800115B6
0x180010c61  mov     ecx, [r14+rdi*8]; this
0x180010c65  test    ecx, ecx
0x180010c67  jz      loc_180011148
0x180010c6d  sub     ecx, 1
0x180010c70  jz      loc_1800110A4
0x180010c76  sub     ecx, 1
0x180010c79  jz      loc_180010FFD
0x180010c7f  sub     ecx, 2
0x180010c82  jz      loc_180010F68
0x180010c88  sub     ecx, 2
0x180010c8b  jz      loc_180010E96
0x180010c91  sub     ecx, 2; this
0x180010c94  jz      loc_180010DF0
0x180010c9a  sub     ecx, 1; this
0x180010c9d  jz      loc_180010D52
0x180010ca3  cmp     ecx, 1
0x180010ca6  jnz     loc_180011294
0x180010cac  cmp     [rsi+0A8h], edx
0x180010cb2  jz      loc_18001120B
0x180010cb8  mov     rdx, [rbp+var_20]; struct RdpDWMDirectWindowContext *
0x180010cbc  lea     r8, [r14+10h]
0x180010cc0  lea     r8, [r8+rdi*8]; struct _DWMIndirectCompositionWindowDpiMetadata *
0x180010cc4  call    ?ProcessCompositionWindowDpi@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectCompositionWindowDpiMetadata@@@Z; RdsDWMDirectUpdateProcessor::ProcessCompositionWindowDpi(RdpDWMDirectWindowContext *,_DWMIndirectCompositionWindowDpiMetadata *)
0x180010cc9  mov     ebx, eax
0x180010ccb  test    eax, eax
0x180010ccd  jns     loc_180011163
0x180010cd3  mov     eax, cs:dword_180044008
0x180010cd9  cmp     eax, 2
0x180010cdc  jbe     loc_180011758
0x180010ce2  lea     rax, aFailedToProces_4; "Failed to process composition window dp"...
0x180010ce9  mov     [rbp+arg_10], 316h
0x180010cf0  mov     [rbp+arg_0], rax
0x180010cf4  lea     rdx, byte_18003AEC3
0x180010cfb  lea     rax, aProcesssurface; "ProcessSurfaceUpdates"
0x180010d02  mov     [rbp+var_8], rax
0x180010d06  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010d0d  mov     [rbp+var_10], rax
0x180010d11  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010d18  mov     [rbp+var_18], rax
0x180010d1c  lea     rax, [rbp+arg_0]
0x180010d20  mov     [rsp+70h+var_28], rax
0x180010d25  lea     rax, [rbp+var_8]
0x180010d29  mov     [rsp+70h+var_30], rax
0x180010d2e  lea     rax, [rbp+arg_10]
0x180010d32  mov     [rsp+70h+var_38], rax
0x180010d37  lea     rax, [rbp+var_10]
0x180010d3b  mov     [rsp+70h+var_40], rax
0x180010d40  lea     rax, [rbp+arg_28]
0x180010d44  mov     [rsp+70h+var_48], rax
0x180010d49  lea     rax, [rbp+var_18]
0x180010d4d  jmp     loc_180010BCE
0x180010d52  cmp     [rsi+0A8h], edx
0x180010d58  jz      loc_18001131D
0x180010d5e  mov     rdx, [rbp+var_20]; struct RdpDWMDirectWindowContext *
0x180010d62  call    ?ProcessDestroyVailSuperWetInk@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@@Z; RdsDWMDirectUpdateProcessor::ProcessDestroyVailSuperWetInk(RdpDWMDirectWindowContext *)
0x180010d67  mov     ebx, eax
0x180010d69  test    eax, eax
0x180010d6b  jns     loc_180011163
0x180010d71  mov     eax, cs:dword_180044008
0x180010d77  cmp     eax, 2
0x180010d7a  jbe     loc_180011758
0x180010d80  lea     rax, aFailedToProces_1; "Failed to process VAIL Destroy Super We"...
0x180010d87  mov     [rbp+arg_10], 30Bh
0x180010d8e  mov     [rbp+arg_0], rax
0x180010d92  lea     rdx, byte_18003AF5D
0x180010d99  lea     rax, aProcesssurface; "ProcessSurfaceUpdates"
0x180010da0  mov     [rbp+var_8], rax
0x180010da4  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010dab  mov     [rbp+var_10], rax
0x180010daf  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010db6  mov     [rbp+var_18], rax
0x180010dba  lea     rax, [rbp+arg_0]
0x180010dbe  mov     [rsp+70h+var_28], rax
0x180010dc3  lea     rax, [rbp+var_8]
0x180010dc7  mov     [rsp+70h+var_30], rax
0x180010dcc  lea     rax, [rbp+arg_10]
0x180010dd0  mov     [rsp+70h+var_38], rax
0x180010dd5  lea     rax, [rbp+var_10]
0x180010dd9  mov     [rsp+70h+var_40], rax
0x180010dde  lea     rax, [rbp+arg_28]
0x180010de2  mov     [rsp+70h+var_48], rax
0x180010de7  lea     rax, [rbp+var_18]
0x180010deb  jmp     loc_180010BCE
0x180010df0  cmp     [rsi+0A8h], edx
0x180010df6  jz      loc_1800113A6
0x180010dfc  mov     rdx, [rbp+var_20]; struct RdpDWMDirectWindowContext *
0x180010e00  lea     r8, [r14+10h]
0x180010e04  lea     r8, [r8+rdi*8]; struct _DWMIndirectCompositionCreateVailSuperWetInkMetadata *
0x180010e08  call    ?ProcessCreateVailSuperWetInk@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectCompositionCreateVailSuperWetInkMetadata@@@Z; RdsDWMDirectUpdateProcessor::ProcessCreateVailSuperWetInk(RdpDWMDirectWindowContext *,_DWMIndirectCompositionCreateVailSuperWetInkMetadata *)
0x180010e0d  mov     ebx, eax
0x180010e0f  test    eax, eax
0x180010e11  jns     loc_180011163
0x180010e17  mov     eax, cs:dword_180044008
0x180010e1d  cmp     eax, 2
0x180010e20  jbe     loc_180011758
0x180010e26  lea     rax, aFailedToProces_0; "Failed to process VAIL Create Super Wet"...
0x180010e2d  mov     [rbp+arg_10], 301h
0x180010e34  mov     [rbp+arg_0], rax
0x180010e38  lea     rdx, byte_18003AFF7
0x180010e3f  lea     rax, aProcesssurface; "ProcessSurfaceUpdates"
0x180010e46  mov     [rbp+var_8], rax
0x180010e4a  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010e51  mov     [rbp+var_10], rax
0x180010e55  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010e5c  mov     [rbp+var_18], rax
0x180010e60  lea     rax, [rbp+arg_0]
0x180010e64  mov     [rsp+70h+var_28], rax
0x180010e69  lea     rax, [rbp+var_8]
0x180010e6d  mov     [rsp+70h+var_30], rax
0x180010e72  lea     rax, [rbp+arg_10]
0x180010e76  mov     [rsp+70h+var_38], rax
0x180010e7b  lea     rax, [rbp+var_10]
0x180010e7f  mov     [rsp+70h+var_40], rax
0x180010e84  lea     rax, [rbp+arg_28]
0x180010e88  mov     [rsp+70h+var_48], rax
0x180010e8d  lea     rax, [rbp+var_18]
0x180010e91  jmp     loc_180010BCE
0x180010e96  cmp     [rsi+0ACh], edx
0x180010e9c  jz      short loc_180010EB8
0x180010e9e  mov     rcx, rsi; this
0x180010ea1  call    ?EnableVailMode@RdsDWMDirectUpdateProcessor@@IEAAJXZ; RdsDWMDirectUpdateProcessor::EnableVailMode(void)
0x180010ea6  xor     edx, edx
0x180010ea8  mov     ebx, eax
0x180010eaa  test    eax, eax
0x180010eac  js      loc_18001142F
0x180010eb2  mov     [rsi+0ACh], edx
0x180010eb8  cmp     [rsi+0A8h], edx
0x180010ebe  jz      loc_1800114AE
0x180010ec4  mov     rcx, [rbp+arg_20]; this
0x180010ec8  lea     r8, [r14+10h]
0x180010ecc  mov     rdx, [rbp+var_20]; struct RdpDWMDirectWindowContext *
0x180010ed0  lea     r8, [r8+rdi*8]; struct _DWMIndirectCompositionSurfaceMetadata *
0x180010ed4  mov     dword ptr [rcx], 1
0x180010eda  call    ?ProcessCompositionSurface@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@PEAU_DWMIndirectCompositionSurfaceMetadata@@@Z; RdsDWMDirectUpdateProcessor::ProcessCompositionSurface(RdpDWMDirectWindowContext *,_DWMIndirectCompositionSurfaceMetadata *)
0x180010edf  mov     ebx, eax
0x180010ee1  test    eax, eax
0x180010ee3  jns     loc_180011163
0x180010ee9  mov     eax, cs:dword_180044008
0x180010eef  cmp     eax, 2
0x180010ef2  jbe     loc_180011758
0x180010ef8  lea     rax, aFailedToProces_6; "Failed to process composition surface m"...
0x180010eff  mov     [rbp+arg_10], 2F6h
0x180010f06  mov     [rbp+arg_0], rax
0x180010f0a  lea     rdx, byte_18003B091
0x180010f11  lea     rax, aProcesssurface; "ProcessSurfaceUpdates"
0x180010f18  mov     [rbp+var_8], rax
0x180010f1c  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180010f23  mov     [rbp+var_10], rax
0x180010f27  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010f2e  mov     [rbp+var_18], rax
0x180010f32  lea     rax, [rbp+arg_0]
0x180010f36  mov     [rsp+70h+var_28], rax
0x180010f3b  lea     rax, [rbp+var_8]
0x180010f3f  mov     [rsp+70h+var_30], rax
0x180010f44  lea     rax, [rbp+arg_10]
0x180010f48  mov     [rsp+70h+var_38], rax
0x180010f4d  lea     rax, [rbp+var_10]
0x180010f51  mov     [rsp+70h+var_40], rax
0x180010f56  lea     rax, [rbp+arg_28]
0x180010f5a  mov     [rsp+70h+var_48], rax
0x180010f5f  lea     rax, [rbp+var_18]
0x180010f63  jmp     loc_180010BCE
0x180010f68  mov     rdx, [rbp+var_20]; struct RdpDWMDirectWindowContext *
0x180010f6c  mov     rcx, rsi; this
0x180010f6f  call    ?ProcessWindowDestroy@RdsDWMDirectUpdateProcessor@@IEAAJPEAVRdpDWMDirectWindowContext@@@Z; RdsDWMDirectUpdateProcessor::ProcessWindowDestroy(RdpDWMDirectWindowContext *)
0x180010f74  mov     ebx, eax
0x180010f76  test    eax, eax
0x180010f78  jns     loc_180011163
0x180010f7e  mov     eax, cs:dword_180044008
  ... truncated ...
```
