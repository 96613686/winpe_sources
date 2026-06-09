# CUMRDPListenerNPDebug::CreateDebugNamedPipe(uchar *,ulong,uchar *,ulong,ulong,int,ushort *,ulong)

- ea: `0x180039f10`
- end: `0x18003a898`
- name: `?CreateDebugNamedPipe@CUMRDPListenerNPDebug@@UEAAJPEAEK0KKHPEAGK@Z`
- size: `2440`
- prototype: `__int64 __fastcall(struct IUnknown **this, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int Size, unsigned int, int, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800071c0`
- `0x180009628`
- `0x18000e420`
- `0x18000f784`
- `0x180010908`
- `0x180012200`
- `0x18003394c`
- `0x180033958`
- `0x180033da0`
- `0x180039f10`
- `0x18003c318`
- `0x18003c3a0`
- `0x18003fb8c`
- `0x180040490`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `RDPBASE!PAL_System_CritSecEnter` at `0x180039fb3`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180039fb3`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a85f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a85f`

## string_xrefs

- `0x18003a023`: `Pipe is already in use`
- `0x18003a058`: `Existing pipe found but is disconnected, will create new pipe`
- `0x18003a11e`: `CreateDebugNamedPipe`
- `0x18003a1d2`: `CreateDebugNamedPipe`
- `0x18003a2b6`: `CreateDebugNamedPipe`
- `0x18003a324`: `CreateDebugNamedPipe`
- `0x18003a3dc`: `CreateDebugNamedPipe`
- `0x18003a44a`: `CreateDebugNamedPipe`
- `0x18003a1be`: `Failed to copy pipe name to out buffer`
- `0x18003a0c9`: `Failed to create new pipe listener entry`
- `0x18003a310`: `Failed to create new pipe listener`
- `0x18003a6ea`: `Failed to copy pipe name to output parameter`
- `0x18003a78f`: `Failed OnCreateNamedPipe`

## pseudocode

```c
__int64 __fastcall CUMRDPListenerNPDebug::CreateDebugNamedPipe(
        struct IUnknown **this,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int Size,
        unsigned int a6,
        int a7,
        unsigned __int16 *a8,
        unsigned int a9)
{
  unsigned __int8 *v9; // rax
  size_t v10; // r14
  void **v12; // rsi
  struct IUnknown **v13; // rcx
  int v14; // r8d
  int v15; // r9d
  struct _PIPE_LISTENER_ENTRY *v16; // rdi
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int UniquePipeName; // ebx
  __int64 v22; // rcx
  char *v23; // rdx
  const char *v24; // rax
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  CUMRDPListenerNPDebug *v33; // rcx
  unsigned int v34; // r8d
  int v35; // r9d
  int v36; // r12d
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  int v40; // r9d
  void *v41; // rcx
  void *v42; // rdx
  void *v43; // rdx
  char *v44; // rcx
  int v45; // ecx
  int v46; // r8d
  int v47; // r9d
  int v48; // ecx
  int v49; // r9d
  char *v50; // rax
  char *v51; // rdx
  struct _PIPE_LISTENER_ENTRY *v53; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  const char *v55; // [rsp+60h] [rbp-A0h] BYREF
  const char *v56; // [rsp+68h] [rbp-98h] BYREF
  const char *v57; // [rsp+70h] [rbp-90h] BYREF
  void *v58; // [rsp+78h] [rbp-88h] BYREF
  struct IUnknown **v59; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v60; // [rsp+88h] [rbp-78h] BYREF
  void *v61; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v63[64]; // [rsp+A0h] [rbp-60h] BYREF

  v58 = a4;
  v9 = a2;
  v10 = (unsigned int)a3;
  Src = a2;
  v12 = 0;
  v60 = a8;
  v61 = 0;
  bstrString = 0;
  if ( !a2 || !a4 || !(_DWORD)a3 || !Size || (unsigned int)a3 > 0x44 || Size > 0x44 )
  {
    UniquePipeName = -2147024809;
    goto LABEL_66;
  }
  v13 = this - 42;
  v59 = v13;
  if ( *((_DWORD *)v13 + 2) )
  {
    PAL_System_CritSecEnter(*v13, a2, a3);
    v9 = (unsigned __int8 *)Src;
  }
  v53 = 0;
  if ( !a7 && CUMRDPListenerNPDebug::FindListenerEntryByPSID((CUMRDPListenerNPDebug *)(this - 54), v9, v10, &v53) )
  {
    v16 = v53;
    v17 = *((_QWORD *)v53 + 1);
    if ( !v17 )
    {
      v22 = *(_QWORD *)v53;
      if ( *(_QWORD *)v53 )
      {
        UniquePipeName = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 40LL))(v22, &bstrString);
        if ( UniquePipeName >= 0 )
        {
          UniquePipeName = StringCchCopyW(a8, a9, bstrString);
          if ( UniquePipeName >= 0 )
          {
            *((_DWORD *)v16 + 5) = 0;
            CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v59);
            goto LABEL_70;
          }
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            LODWORD(v53) = 1981;
            v57 = "Failed to copy pipe name to out buffer";
            v56 = "CreateDebugNamedPipe";
            v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
            LODWORD(Src) = UniquePipeName;
            v58 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v27,
              (unsigned int)byte_18018F635,
              v28,
              v29,
              (__int64)&v58,
              (__int64)&Src,
              (__int64)&v55,
              (__int64)&v53,
              (__int64)&v56,
              (__int64)&v57);
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(Src) = 1974;
          v58 = "Failed to get pipe name from existing listener";
          v55 = "CreateDebugNamedPipe";
          v56 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
          LODWORD(v53) = UniquePipeName;
          v57 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            dword_1801B76C8,
            (unsigned int)byte_18018F68B,
            v25,
            v26,
            (__int64)&v57,
            (__int64)&v53,
            (__int64)&v56,
            (__int64)&Src,
            (__int64)&v55,
            (__int64)&v58);
        }
      }
      else
      {
        UniquePipeName = -2147418113;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          LODWORD(v53) = 1989;
          v56 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
          v23 = &byte_18018F5E7;
          v24 = "Listener entry found in list, but no valid pointers";
          goto LABEL_33;
        }
      }
LABEL_15:
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v59);
      goto LABEL_66;
    }
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17) )
    {
      UniquePipeName = -2147024713;
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        v53 = (struct _PIPE_LISTENER_ENTRY *)"Pipe is already in use";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v18,
          (unsigned int)byte_18018F70B,
          v19,
          v20,
          (__int64)&v53);
      }
      goto LABEL_15;
    }
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v53 = (struct _PIPE_LISTENER_ENTRY *)"Existing pipe found but is disconnected, will create new pipe";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v18,
        (unsigned int)byte_18018F6E1,
        v19,
        v20,
        (__int64)&v53);
    }
    CUMRDPListenerNPDebug::OnConnectionClosedNoLock(
      (CUMRDPListenerNPDebug *)(this - 54),
      *((struct IUnknown **)v16 + 1));
  }
  v12 = (void **)operator new[]((unsigned int)v10 + Size + 56);
  if ( !v12 )
  {
    UniquePipeName = -2147024882;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v53) = 2001;
      v56 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v23 = byte_18018F599;
      v24 = "Failed to create new pipe listener entry";
LABEL_33:
      v55 = v24;
      v57 = "CreateDebugNamedPipe";
      LODWORD(Src) = UniquePipeName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v22,
        (_DWORD)v23,
        v14,
        v15,
        (__int64)&v55,
        (__int64)&Src,
        (__int64)&v56,
        (__int64)&v53,
        (__int64)&v57);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  UniquePipeName = __RDPAPIDLL__CreateInstance(
                     *(this - 40),
                     &CLSID_RDPENCONNamedPipeListener,
                     &IID_IRDPENCONNamedPipeListenerEx,
                     &v61);
  if ( UniquePipeName < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v53) = 2012;
      v57 = "Failed to create new pipe listener";
      v56 = "CreateDebugNamedPipe";
      v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      LODWORD(Src) = UniquePipeName;
      v58 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v30,
        (unsigned int)byte_18018F543,
        v31,
        v32,
        (__int64)&v58,
        (__int64)&Src,
        (__int64)&v55,
        (__int64)&v53,
        (__int64)&v56,
        (__int64)&v57);
    }
    goto LABEL_15;
  }
  UniquePipeName = (*(__int64 (__fastcall **)(void *, unsigned __int64))(*(_QWORD *)v61 + 56LL))(
                     v61,
                     -(__int64)(this != (struct IUnknown **)432) & (unsigned __int64)(this + 1));
  if ( UniquePipeName < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v53) = 2015;
      v57 = "Failed to initialize new pipe listener";
      v56 = "CreateDebugNamedPipe";
      v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      LODWORD(Src) = UniquePipeName;
      v58 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v33,
        (unsigned int)byte_18018F4ED,
        v34,
        v35,
        (__int64)&v58,
        (__int64)&Src,
        (__int64)&v55,
        (__int64)&v53,
        (__int64)&v56,
        (__int64)&v57);
    }
    goto LABEL_15;
  }
  v36 = 0;
  while ( 1 )
  {
    UniquePipeName = CUMRDPListenerNPDebug::GenerateUniquePipeName(v33, v63, v34);
    if ( UniquePipeName < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v57 = "CreateDebugNamedPipe";
        v60 = (unsigned __int16 *)"Failed to generate pipe name";
        LODWORD(v53) = 2022;
        v56 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
        v55 = "Error HResult failed";
        LODWORD(Src) = UniquePipeName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v37,
          (unsigned int)&byte_18018F497,
          v38,
          v39,
          (__int64)&v55,
          (__int64)&Src,
          (__int64)&v56,
          (__int64)&v53,
          (__int64)&v57,
          (__int64)&v60);
      }
      goto LABEL_15;
    }
    UniquePipeName = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, void *, __int64, int))(*(_QWORD *)v61 + 64LL))(
                       v61,
                       v63,
                       Src,
                       1,
                       1);
    if ( UniquePipeName < 0 && (unsigned int)dword_1801B76C8 > 3 )
    {
      v57 = "CreateDebugNamedPipe";
      v56 = "Failed to start listener, retrying";
      LODWORD(v53) = UniquePipeName;
      v55 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v33,
        (unsigned int)byte_18018F453,
        v34,
        v40,
        (__int64)&v55,
        (__int64)&v56,
        (__int64)&v53,
        (__int64)&v57);
    }
    if ( UniquePipeName != -2147024665 )
      break;
    if ( (unsigned int)++v36 >= 0x14 )
      goto LABEL_49;
  }
  if ( UniquePipeName >= 0 )
  {
    v41 = v61;
    *v12 = v61;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 8LL))(v41);
    v42 = Src;
    v12[4] = v12 + 7;
    v12[1] = 0;
    v12[2] = (void *)a6;
    *((_DWORD *)v12 + 6) = v10;
    memcpy_0(v12 + 7, v42, v10);
    v43 = v58;
    v44 = (char *)v12 + v10 + 56;
    *((_DWORD *)v12 + 10) = Size;
    v12[6] = v44;
    memcpy_0(v44, v43, Size);
    UniquePipeName = ((__int64 (__fastcall *)(char *, void **))this[474][1].lpVtbl)((char *)this + 3792, v12);
    if ( UniquePipeName >= 0 )
    {
      v12 = 0;
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v59);
      UniquePipeName = StringCchCopyW(v60, a9, v63);
      if ( UniquePipeName >= 0 )
      {
        UniquePipeName = CUMRDPListenerNPDebug::OnCreateNamedPipe(this - 54);
        if ( UniquePipeName >= 0 )
          goto LABEL_70;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_66;
        v50 = "Failed OnCreateNamedPipe";
        LODWORD(v53) = 2064;
        v51 = byte_18018F2FB;
      }
      else
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_66;
        v50 = "Failed to copy pipe name to output parameter";
        LODWORD(v53) = 2061;
        v51 = byte_18018F351;
      }
      v60 = (unsigned __int16 *)v50;
      v56 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v55 = "Error HResult failed";
      LODWORD(Src) = UniquePipeName;
      v57 = "CreateDebugNamedPipe";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v48,
        (_DWORD)v51,
        a3,
        v49,
        (__int64)&v55,
        (__int64)&Src,
        (__int64)&v56,
        (__int64)&v53,
        (__int64)&v57,
        (__int64)&v60);
      goto LABEL_66;
    }
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v56 = "CreateDebugNamedPipe";
      v57 = "Failed to add entry to listener list";
      LODWORD(v53) = 2051;
      v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v58 = "Error HResult failed";
      LODWORD(Src) = UniquePipeName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v45,
        (unsigned int)&byte_18018F3A7,
        v46,
        v47,
        (__int64)&v58,
        (__int64)&Src,
        (__int64)&v55,
        (__int64)&v53,
        (__int64)&v56,
        (__int64)&v57);
    }
    goto LABEL_15;
  }
LABEL_49:
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v56 = "CreateDebugNamedPipe";
    v57 = "Failed to start listener after too many tries, giving up";
    LODWORD(v53) = 2032;
    v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
    v58 = "Error HResult failed";
    LODWORD(Src) = UniquePipeName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)v33,
      (unsigned int)byte_18018F3FD,
      v34,
      v40,
      (__int64)&v58,
      (__int64)&Src,
      (__int64)&v55,
      (__int64)&v53,
      (__int64)&v56,
      (__int64)&v57);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v59);
LABEL_66:
  if ( v61 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v61 + 32LL))(v61);
  if ( v12 )
    operator delete(v12);
LABEL_70:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v61, a2, a3);
  return (unsigned int)UniquePipeName;
}

```

## disassembly

```asm
0x180039f10  push    rbp
0x180039f12  push    rbx
0x180039f13  push    rsi
0x180039f14  push    rdi
0x180039f15  push    r12
0x180039f17  push    r13
0x180039f19  push    r14
0x180039f1b  push    r15
0x180039f1d  lea     rbp, [rsp-38h]
0x180039f22  sub     rsp, 138h
0x180039f29  mov     rax, cs:__security_cookie
0x180039f30  xor     rax, rsp
0x180039f33  mov     [rbp+70h+var_50], rax
0x180039f37  mov     r12, [rbp+70h+arg_38]
0x180039f3e  xor     edi, edi
0x180039f40  mov     [rsp+170h+var_F8], r9
0x180039f45  mov     rax, rdx
0x180039f48  mov     r14d, r8d
0x180039f4b  mov     r13, rcx
0x180039f4e  mov     [rsp+170h+Src], rdx
0x180039f53  mov     esi, edi
0x180039f55  mov     [rbp+70h+var_E8], r12
0x180039f59  mov     [rbp+70h+var_E0], rdi
0x180039f5d  mov     [rbp+70h+bstrString], rdi
0x180039f61  test    rdx, rdx
0x180039f64  jz      loc_18003A82F
0x180039f6a  test    r9, r9
0x180039f6d  jz      loc_18003A82F
0x180039f73  test    r8d, r8d
0x180039f76  jz      loc_18003A82F
0x180039f7c  mov     r15d, dword ptr [rbp+70h+Size]
0x180039f83  test    r15d, r15d
0x180039f86  jz      loc_18003A82F
0x180039f8c  cmp     r14d, 44h ; 'D'
0x180039f90  ja      loc_18003A82F
0x180039f96  cmp     r15d, 44h ; 'D'
0x180039f9a  ja      loc_18003A82F
0x180039fa0  add     rcx, 0FFFFFFFFFFFFFEB0h
0x180039fa7  mov     [rbp+70h+var_F0], rcx
0x180039fab  cmp     [rcx+8], edi
0x180039fae  jz      short loc_180039FBE
0x180039fb0  mov     rcx, [rcx]
0x180039fb3  call    cs:__imp_PAL_System_CritSecEnter
0x180039fb9  mov     rax, [rsp+170h+Src]
0x180039fbe  mov     [rsp+170h+var_120], rdi
0x180039fc3  cmp     [rbp+70h+arg_30], edi
0x180039fc9  jnz     loc_18003A086
0x180039fcf  lea     rbx, [r13-1B0h]
0x180039fd6  mov     r8d, r14d; unsigned int
0x180039fd9  mov     rcx, rbx; this
0x180039fdc  lea     r9, [rsp+170h+var_120]; struct _PIPE_LISTENER_ENTRY **
0x180039fe1  mov     rdx, rax; unsigned __int8 *
0x180039fe4  call    ?FindListenerEntryByPSID@CUMRDPListenerNPDebug@@AEAAHPEAEKPEAPEAU_PIPE_LISTENER_ENTRY@@@Z; CUMRDPListenerNPDebug::FindListenerEntryByPSID(uchar *,ulong,_PIPE_LISTENER_ENTRY * *)
0x180039fe9  test    eax, eax
0x180039feb  jz      loc_18003A086
0x180039ff1  mov     rdi, [rsp+170h+var_120]
0x180039ff6  mov     rcx, [rdi+8]
0x180039ffa  test    rcx, rcx
0x180039ffd  jz      loc_18003A0D5
0x18003a003  mov     rax, [rcx]
0x18003a006  mov     rax, [rax+28h]
0x18003a00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a00f  test    eax, eax
0x18003a011  mov     eax, cs:dword_1801B76C8
0x18003a017  jz      short loc_18003A053
0x18003a019  mov     ebx, 800700B7h
0x18003a01e  cmp     eax, 3
0x18003a021  jbe     short loc_18003A045
0x18003a023  lea     rax, aPipeIsAlreadyI; "Pipe is already in use"
0x18003a02a  mov     [rsp+170h+var_120], rax
0x18003a02f  lea     rdx, byte_18018F70B
0x18003a036  lea     rax, [rsp+170h+var_120]
0x18003a03b  mov     [rsp+170h+var_150], rax
0x18003a040  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003a045  lea     rcx, [rbp+70h+var_F0]; this
0x18003a049  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18003a04e  jmp     loc_18003A834
0x18003a053  cmp     eax, 3
0x18003a056  jbe     short loc_18003A07A
0x18003a058  lea     rax, aExistingPipeFo; "Existing pipe found but is disconnected"...
0x18003a05f  mov     [rsp+170h+var_120], rax
0x18003a064  lea     rdx, byte_18018F6E1
0x18003a06b  lea     rax, [rsp+170h+var_120]
0x18003a070  mov     [rsp+170h+var_150], rax
0x18003a075  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003a07a  mov     rdx, [rdi+8]; struct IUnknown *
0x18003a07e  mov     rcx, rbx; this
0x18003a081  call    ?OnConnectionClosedNoLock@CUMRDPListenerNPDebug@@IEAAXPEAUIUnknown@@@Z; CUMRDPListenerNPDebug::OnConnectionClosedNoLock(IUnknown *)
0x18003a086  lea     ecx, [r15+38h]
0x18003a08a  add     ecx, r14d; unsigned __int64
0x18003a08d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003a092  mov     rsi, rax
0x18003a095  test    rax, rax
0x18003a098  jnz     loc_18003A2D5
0x18003a09e  mov     eax, cs:dword_1801B76C8
0x18003a0a4  mov     ebx, 8007000Eh
0x18003a0a9  cmp     eax, 2
0x18003a0ac  jbe     short loc_18003A045
0x18003a0ae  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003a0b5  mov     dword ptr [rsp+170h+var_120], 7D1h
0x18003a0bd  mov     [rsp+170h+var_108], rax
0x18003a0c2  lea     rdx, byte_18018F599
0x18003a0c9  lea     rax, aFailedToCreate_82; "Failed to create new pipe listener entr"...
0x18003a0d0  jmp     loc_18003A284
0x18003a0d5  mov     rcx, [rdi]
0x18003a0d8  test    rcx, rcx
0x18003a0db  jz      loc_18003A24E
0x18003a0e1  mov     rax, [rcx]
0x18003a0e4  lea     rdx, [rbp+70h+bstrString]
0x18003a0e8  mov     rax, [rax+28h]
0x18003a0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0f1  mov     ebx, eax
0x18003a0f3  test    eax, eax
0x18003a0f5  jns     loc_18003A193
0x18003a0fb  mov     ecx, cs:dword_1801B76C8
0x18003a101  cmp     ecx, 2
0x18003a104  jbe     loc_18003A045
0x18003a10a  lea     rax, aFailedToGetPip; "Failed to get pipe name from existing l"...
0x18003a111  mov     dword ptr [rsp+170h+Src], 7B6h
0x18003a119  mov     [rsp+170h+var_F8], rax
0x18003a11e  lea     rdi, aCreatedebugnam; "CreateDebugNamedPipe"
0x18003a125  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003a12c  mov     [rsp+170h+var_110], rdi
0x18003a131  mov     [rsp+170h+var_108], rax
0x18003a136  lea     rdx, byte_18018F68B
0x18003a13d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003a144  mov     dword ptr [rsp+170h+var_120], ebx
0x18003a148  mov     [rsp+170h+var_100], rax
0x18003a14d  lea     rax, [rsp+170h+var_F8]
0x18003a152  mov     [rsp+170h+var_128], rax
0x18003a157  lea     rax, [rsp+170h+var_110]
0x18003a15c  mov     [rsp+170h+var_130], rax
0x18003a161  lea     rax, [rsp+170h+Src]
0x18003a166  mov     [rsp+170h+var_138], rax
0x18003a16b  lea     rax, [rsp+170h+var_108]
0x18003a170  mov     [rsp+170h+var_140], rax
0x18003a175  lea     rax, [rsp+170h+var_120]
0x18003a17a  mov     [rsp+170h+var_148], rax
0x18003a17f  lea     rax, [rsp+170h+var_100]
0x18003a184  mov     [rsp+170h+var_150], rax
0x18003a189  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003a18e  jmp     loc_18003A045
0x18003a193  mov     edx, [rbp+70h+arg_40]; unsigned __int64
0x18003a199  mov     rcx, r12; unsigned __int16 *
0x18003a19c  mov     r8, [rbp+70h+bstrString]; unsigned __int16 *
0x18003a1a0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a1a5  mov     ebx, eax
0x18003a1a7  test    eax, eax
0x18003a1a9  jns     loc_18003A23D
0x18003a1af  mov     eax, cs:dword_1801B76C8
0x18003a1b5  cmp     eax, 2
0x18003a1b8  jbe     loc_18003A045
0x18003a1be  lea     rax, aFailedToCopyPi_0; "Failed to copy pipe name to out buffer"
0x18003a1c5  mov     dword ptr [rsp+170h+var_120], 7BDh
0x18003a1cd  mov     [rsp+170h+var_100], rax
0x18003a1d2  lea     rdi, aCreatedebugnam; "CreateDebugNamedPipe"
0x18003a1d9  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003a1e0  mov     [rsp+170h+var_108], rdi
0x18003a1e5  mov     [rsp+170h+var_110], rax
0x18003a1ea  lea     rdx, byte_18018F635
0x18003a1f1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003a1f8  mov     dword ptr [rsp+170h+Src], ebx
0x18003a1fc  mov     [rsp+170h+var_F8], rax
0x18003a201  lea     rax, [rsp+170h+var_100]
0x18003a206  mov     [rsp+170h+var_128], rax
0x18003a20b  lea     rax, [rsp+170h+var_108]
0x18003a210  mov     [rsp+170h+var_130], rax
0x18003a215  lea     rax, [rsp+170h+var_120]
0x18003a21a  mov     [rsp+170h+var_138], rax
0x18003a21f  lea     rax, [rsp+170h+var_110]
0x18003a224  mov     [rsp+170h+var_140], rax
0x18003a229  lea     rax, [rsp+170h+Src]
0x18003a22e  mov     [rsp+170h+var_148], rax
0x18003a233  lea     rax, [rsp+170h+var_F8]
0x18003a238  jmp     loc_18003A184
0x18003a23d  lea     rcx, [rbp+70h+var_F0]; this
0x18003a241  mov     [rdi+14h], esi
0x18003a244  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18003a249  jmp     loc_18003A856
0x18003a24e  mov     eax, cs:dword_1801B76C8
0x18003a254  mov     ebx, 8000FFFFh
0x18003a259  cmp     eax, 2
0x18003a25c  jbe     loc_18003A045
0x18003a262  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003a269  mov     dword ptr [rsp+170h+var_120], 7C5h
0x18003a271  mov     [rsp+170h+var_108], rax
0x18003a276  lea     rdx, byte_18018F5E7
0x18003a27d  lea     rax, aListenerEntryF; "Listener entry found in list, but no va"...
0x18003a284  mov     [rsp+170h+var_110], rax
0x18003a289  lea     rax, [rsp+170h+var_100]
0x18003a28e  mov     [rsp+170h+var_130], rax
0x18003a293  lea     rax, [rsp+170h+var_120]
0x18003a298  mov     [rsp+170h+var_138], rax
0x18003a29d  lea     rax, [rsp+170h+var_108]
0x18003a2a2  mov     [rsp+170h+var_140], rax
0x18003a2a7  lea     rax, [rsp+170h+Src]
0x18003a2ac  mov     [rsp+170h+var_148], rax
0x18003a2b1  lea     rax, [rsp+170h+var_110]
0x18003a2b6  lea     rdi, aCreatedebugnam; "CreateDebugNamedPipe"
0x18003a2bd  mov     [rsp+170h+var_150], rax
0x18003a2c2  mov     [rsp+170h+var_100], rdi
0x18003a2c7  mov     dword ptr [rsp+170h+Src], ebx
0x18003a2cb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003a2d0  jmp     loc_18003A045
0x18003a2d5  lea     rdi, [r13-1B0h]
0x18003a2dc  mov     rcx, [rdi+70h]; struct IUnknown *
0x18003a2e0  lea     r9, [rbp+70h+var_E0]; void **
0x18003a2e4  lea     r8, IID_IRDPENCONNamedPipeListenerEx; struct _GUID *
0x18003a2eb  lea     rdx, CLSID_RDPENCONNamedPipeListener; struct _GUID *
0x18003a2f2  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18003a2f7  mov     ebx, eax
0x18003a2f9  test    eax, eax
0x18003a2fb  jns     loc_18003A38F
0x18003a301  mov     eax, cs:dword_1801B76C8
0x18003a307  cmp     eax, 2
0x18003a30a  jbe     loc_18003A045
0x18003a310  lea     rax, aFailedToCreate_19; "Failed to create new pipe listener"
0x18003a317  mov     dword ptr [rsp+170h+var_120], 7DCh
0x18003a31f  mov     [rsp+170h+var_100], rax
0x18003a324  lea     rdi, aCreatedebugnam; "CreateDebugNamedPipe"
0x18003a32b  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003a332  mov     [rsp+170h+var_108], rdi
0x18003a337  mov     [rsp+170h+var_110], rax
0x18003a33c  lea     rdx, byte_18018F543
0x18003a343  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003a34a  mov     dword ptr [rsp+170h+Src], ebx
0x18003a34e  mov     [rsp+170h+var_F8], rax
0x18003a353  lea     rax, [rsp+170h+var_100]
0x18003a358  mov     [rsp+170h+var_128], rax
0x18003a35d  lea     rax, [rsp+170h+var_108]
0x18003a362  mov     [rsp+170h+var_130], rax
0x18003a367  lea     rax, [rsp+170h+var_120]
0x18003a36c  mov     [rsp+170h+var_138], rax
0x18003a371  lea     rax, [rsp+170h+var_110]
0x18003a376  mov     [rsp+170h+var_140], rax
0x18003a37b  lea     rax, [rsp+170h+Src]
0x18003a380  mov     [rsp+170h+var_148], rax
0x18003a385  lea     rax, [rsp+170h+var_F8]
0x18003a38a  jmp     loc_18003A184
0x18003a38f  mov     rcx, [rbp+70h+var_E0]
0x18003a393  lea     rdx, [r13+8]
0x18003a397  mov     rax, rdi
0x18003a39a  neg     rax
0x18003a39d  mov     r9, [rcx]
0x18003a3a0  sbb     r8, r8
0x18003a3a3  and     rdx, r8
0x18003a3a6  mov     rax, [r9+38h]
0x18003a3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3af  mov     ebx, eax
0x18003a3b1  test    eax, eax
0x18003a3b3  jns     loc_18003A447
0x18003a3b9  mov     eax, cs:dword_1801B76C8
0x18003a3bf  cmp     eax, 2
0x18003a3c2  jbe     loc_18003A045
0x18003a3c8  lea     rax, aFailedToInitia_32; "Failed to initialize new pipe listener"
0x18003a3cf  mov     dword ptr [rsp+170h+var_120], 7DFh
0x18003a3d7  mov     [rsp+170h+var_100], rax
0x18003a3dc  lea     rdi, aCreatedebugnam; "CreateDebugNamedPipe"
0x18003a3e3  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003a3ea  mov     [rsp+170h+var_108], rdi
0x18003a3ef  mov     [rsp+170h+var_110], rax
0x18003a3f4  lea     rdx, byte_18018F4ED
0x18003a3fb  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003a402  mov     dword ptr [rsp+170h+Src], ebx
0x18003a406  mov     [rsp+170h+var_F8], rax
0x18003a40b  lea     rax, [rsp+170h+var_100]
0x18003a410  mov     [rsp+170h+var_128], rax
0x18003a415  lea     rax, [rsp+170h+var_108]
0x18003a41a  mov     [rsp+170h+var_130], rax
0x18003a41f  lea     rax, [rsp+170h+var_120]
0x18003a424  mov     [rsp+170h+var_138], rax
0x18003a429  lea     rax, [rsp+170h+var_110]
0x18003a42e  mov     [rsp+170h+var_140], rax
0x18003a433  lea     rax, [rsp+170h+Src]
0x18003a438  mov     [rsp+170h+var_148], rax
0x18003a43d  lea     rax, [rsp+170h+var_F8]
0x18003a442  jmp     loc_18003A184
0x18003a447  xor     r12d, r12d
0x18003a44a  lea     rdi, aCreatedebugnam; "CreateDebugNamedPipe"
0x18003a451  lea     rdx, [rbp+70h+var_D0]; unsigned __int16 *
0x18003a455  call    ?GenerateUniquePipeName@CUMRDPListenerNPDebug@@IEAAJPEAGK@Z; CUMRDPListenerNPDebug::GenerateUniquePipeName(ushort *,ulong)
0x18003a45a  mov     ebx, eax
0x18003a45c  test    eax, eax
0x18003a45e  js      loc_18003A7AA
0x18003a464  mov     rcx, [rbp+70h+var_E0]
0x18003a468  mov     edx, 1
0x18003a46d  mov     r8, [rsp+170h+Src]
0x18003a472  mov     r9d, edx
0x18003a475  mov     dword ptr [rsp+170h+var_150], edx
0x18003a479  lea     rdx, [rbp+70h+var_D0]
0x18003a47d  mov     rax, [rcx]
0x18003a480  mov     rax, [rax+40h]
0x18003a484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a489  mov     ebx, eax
0x18003a48b  test    eax, eax
0x18003a48d  jns     short loc_18003A4EF
0x18003a48f  mov     eax, cs:dword_1801B76C8
0x18003a495  cmp     eax, 3
0x18003a498  jbe     short loc_18003A4EF
0x18003a49a  lea     rax, aFailedToStartL_1; "Failed to start listener, retrying"
  ... truncated ...
```
