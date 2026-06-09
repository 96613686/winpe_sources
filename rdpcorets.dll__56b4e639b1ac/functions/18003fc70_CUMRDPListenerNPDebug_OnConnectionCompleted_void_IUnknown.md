# CUMRDPListenerNPDebug::OnConnectionCompleted(void *,IUnknown *)

- ea: `0x18003fc70`
- end: `0x18004034d`
- name: `?OnConnectionCompleted@CUMRDPListenerNPDebug@@UEAAXPEAXPEAUIUnknown@@@Z`
- size: `1757`
- prototype: `void __fastcall(CUMRDPListenerNPDebug *this, void *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x180010908`
- `0x180012200`
- `0x180017db4`
- `0x18001c164`
- `0x180033da0`
- `0x180039e10`
- `0x18003c15c`
- `0x18003fc70`
- `0x18014c328`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800402d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800402d8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003fd7b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003fd7b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003feda`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180040284`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003feda`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180040284`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800402c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800402c6`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003fcff`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003ff97`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003fcff`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003ff97`

## string_xrefs

- `0x18003ff1a`: `Failed to create the UMRDP connection object`
- `0x18003fdb3`: `OnConnectionCompleted`
- `0x18003fe6f`: `OnConnectionCompleted`
- `0x18003ff33`: `OnConnectionCompleted`
- `0x18004005f`: `OnConnectionCompleted`
- `0x18004019a`: `OnConnectionCompleted`
- `0x18004020b`: `OnConnectionCompleted`
- `0x18003fd54`: `CUMRDPListenerNPDebug: OnConnectionCompleted`
- `0x180040046`: `CreateConnectionSecurityDescriptor failed`
- `0x180040232`: `OnConnectionCompleted came from a listener not in our list!`

## pseudocode

```c
void __fastcall CUMRDPListenerNPDebug::OnConnectionCompleted(
        CUMRDPListenerNPDebug *this,
        void *a2,
        struct IUnknown *a3)
{
  CUMRDPListenerBase *v3; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // r14
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  HRESULT v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // r9d
  int v20; // esi
  int v21; // ecx
  __int64 v22; // r8
  int v23; // r9d
  char *v24; // rdx
  const char **v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // ecx
  __int64 v31; // r8
  int v32; // r9d
  struct _PIPE_LISTENER_ENTRY *v33; // r14
  _QWORD *v34; // rsi
  __int64 v35; // rax
  void *v36; // rdx
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // r8
  __int64 v41; // rcx
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rdx
  __int64 v48; // r8
  void *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r8
  const char **v52; // [rsp+30h] [rbp-D0h]
  const char **v53; // [rsp+40h] [rbp-C0h]
  const char **v54; // [rsp+48h] [rbp-B8h]
  __int64 v55; // [rsp+50h] [rbp-B0h]
  int v56; // [rsp+80h] [rbp-80h] BYREF
  struct _PIPE_LISTENER_ENTRY *v57; // [rsp+88h] [rbp-78h] BYREF
  const char *v58; // [rsp+90h] [rbp-70h] BYREF
  const char *v59; // [rsp+98h] [rbp-68h] BYREF
  struct IUnknown *v60; // [rsp+A0h] [rbp-60h] BYREF
  const char *v61; // [rsp+A8h] [rbp-58h] BYREF
  const char *v62; // [rsp+B0h] [rbp-50h] BYREF
  void *v63; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v64; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v65; // [rsp+C8h] [rbp-38h] BYREF
  const char *v66; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp-20h] BYREF
  struct IUnknown *v69; // [rsp+E8h] [rbp-18h]
  _BYTE v70[3724]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v71; // [rsp+F7Ch] [rbp+E7Ch]
  HLOCAL v72; // [rsp+F80h] [rbp+E80h]
  GUID v73; // [rsp+F88h] [rbp+E88h]
  GUID ActivityId; // [rsp+FB0h] [rbp+EB0h] BYREF
  GUID pguid; // [rsp+FC0h] [rbp+EC0h] BYREF

  v69 = a3;
  v3 = (CUMRDPListenerNPDebug *)((char *)this - 440);
  v67 = 0;
  v63 = 0;
  v6 = 0;
  v65 = 0;
  v7 = 0;
  memcpy_0(v70, (char *)this + 8, 0xEB8u);
  v10 = (_QWORD *)((char *)this - 344);
  hMem = 0;
  v64 = 0;
  pguid = 0;
  v58 = (char *)this - 344;
  if ( *((_DWORD *)this - 84) )
    PAL_System_CritSecEnter(*v10, v8, v9);
  if ( !(*(unsigned int (__fastcall **)(CUMRDPListenerBase *))(*(_QWORD *)v3 + 80LL))(v3) && *((_QWORD *)this - 45) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v67, v11, v12);
    v7 = *((_QWORD *)this - 45);
    v67 = v7;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v67);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v58);
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v58 = "CUMRDPListenerNPDebug: OnConnectionCompleted";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v13,
      (unsigned int)byte_18018F2D1,
      v14,
      v15,
      (__int64)&v58);
  }
  v16 = CoCreateGuid(&pguid);
  v20 = v16;
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v56 = 2118;
      v58 = "Failed to generate a connection GUID";
      LODWORD(v57) = v16;
      v60 = (struct IUnknown *)"OnConnectionCompleted";
      v61 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v59 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_18018F27B,
        v18,
        v19,
        (__int64)&v59,
        (__int64)&v57,
        (__int64)&v61,
        (__int64)&v56,
        (__int64)&v60,
        (__int64)&v58);
    }
    goto LABEL_35;
  }
  v60 = 0;
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, &pguid);
  v20 = CUMRDPListenerBase::CreateChildPlatformContext(v3, &pguid, (struct IRDPENCPlatformContext **)&v60);
  if ( v20 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
    {
LABEL_15:
      EventActivityIdControl(2u, &ActivityId);
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v60, v26, v27);
      goto LABEL_35;
    }
    LODWORD(v57) = 2128;
    v59 = "Failed to initialize the child platform context";
    v24 = byte_18018F225;
    v61 = "OnConnectionCompleted";
    v58 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
    v62 = "Error HResult failed";
    v54 = &v59;
    v53 = &v61;
    v52 = &v58;
    v25 = &v62;
LABEL_14:
    v56 = v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v21,
      (_DWORD)v24,
      v22,
      v23,
      (__int64)v25,
      (__int64)&v56,
      (__int64)v52,
      (__int64)&v57,
      (__int64)v53,
      (__int64)v54);
    goto LABEL_15;
  }
  v20 = __RDPAPIDLL__CreateInstance(v60, &CLSID_UMRDPConnection, &IID_IUMRDPConnection, &v63);
  if ( v20 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_15;
    LODWORD(v57) = 2134;
    v62 = "Failed to create the UMRDP connection object";
    v24 = &byte_18018F1CF;
    v59 = "OnConnectionCompleted";
    v61 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
    v58 = "Error HResult failed";
    v54 = &v62;
    v53 = &v59;
    v52 = &v61;
    v25 = &v58;
    goto LABEL_14;
  }
  v58 = (char *)this - 344;
  if ( *((_DWORD *)v10 + 2) )
    PAL_System_CritSecEnter(*v10, v28, v22);
  v57 = 0;
  if ( (unsigned int)CUMRDPListenerNPDebug::FindListenerEntryByListener(v3, v69, &v57) )
  {
    v33 = v57;
    v34 = *(_QWORD **)v57;
    if ( *(_QWORD *)v57 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v65, v29, v31);
      v35 = *v34;
      v6 = v34;
      v65 = v34;
      (*(void (__fastcall **)(_QWORD *))(v35 + 8))(v34);
    }
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v33 + 16LL))(*(_QWORD *)v33);
    *(_QWORD *)v33 = 0;
    *((_QWORD *)v33 + 1) = v63;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v63 + 8LL))(v63);
    v36 = (void *)*((_QWORD *)v33 + 6);
    LODWORD(v57) = *((_DWORD *)v33 + 4);
    v20 = CUMRDPListenerNPDebug::CreateConnectionSecurityDescriptor(v3, v36, &hMem, &v64);
    if ( v20 >= 0 )
    {
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v58);
      v40 = *((_QWORD *)this - 44);
      v55 = *((_QWORD *)this - 24);
      v41 = *((_QWORD *)this - 30);
      v72 = hMem;
      v71 = v64;
      v73 = pguid;
      v20 = (*(__int64 (__fastcall **)(void *, CUMRDPListenerBase *, __int64, _QWORD, void *, __int64, __int64, _QWORD, _DWORD, _BYTE *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v63 + 24LL))(
              v63,
              v3,
              v40,
              0,
              a2,
              v7,
              v41,
              0,
              (_DWORD)v57,
              v70,
              v55,
              0,
              0,
              0);
      if ( v20 < 0 && (unsigned int)dword_1801B76C8 > 2 )
      {
        LODWORD(v57) = 2192;
        v66 = "Failed to initialize connection";
        v56 = v20;
        v62 = "OnConnectionCompleted";
        v59 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
        v61 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v42,
          (unsigned int)byte_18018F0D5,
          v43,
          v44,
          (__int64)&v61,
          (__int64)&v56,
          (__int64)&v59,
          (__int64)&v57,
          (__int64)&v62,
          (__int64)&v66);
      }
      goto LABEL_33;
    }
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v57) = 2163;
      v62 = "CreateConnectionSecurityDescriptor failed";
      v56 = v20;
      v59 = "OnConnectionCompleted";
      v61 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v66 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v37,
        (unsigned int)byte_18018F179,
        v38,
        v39,
        (__int64)&v66,
        (__int64)&v56,
        (__int64)&v61,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v62);
    }
  }
  else
  {
    v20 = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v57) = 2168;
      v66 = "OnConnectionCompleted";
      v56 = -2147418113;
      v62 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v59 = "OnConnectionCompleted came from a listener not in our list!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v30,
        (unsigned int)byte_18018F12B,
        v31,
        v32,
        (__int64)&v59,
        (__int64)&v56,
        (__int64)&v62,
        (__int64)&v57,
        (__int64)&v66);
    }
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v58);
LABEL_33:
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v60, v45, v46);
  if ( v6 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v6 + 32LL))(v6);
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v65, v47, v48);
    v65 = 0;
  }
LABEL_35:
  if ( hMem )
    LocalFree(hMem);
  if ( v20 < 0 )
  {
    if ( a2 )
      CloseHandle(a2);
    (*(void (__fastcall **)(CUMRDPListenerNPDebug *, _QWORD, struct IUnknown *))(*(_QWORD *)this + 32LL))(
      this,
      (unsigned int)v20,
      v69);
  }
  v49 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v49 + 16LL))(v49);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v65, v17, v18);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v67, v50, v51);
}

```

## disassembly

```asm
0x18003fc70  mov     [rsp-8+arg_18], rbx
0x18003fc75  push    rbp
0x18003fc76  push    rsi
0x18003fc77  push    rdi
0x18003fc78  push    r12
0x18003fc7a  push    r13
0x18003fc7c  push    r14
0x18003fc7e  push    r15
0x18003fc80  lea     rbp, [rsp-0EE0h]
0x18003fc88  sub     rsp, 0FE0h
0x18003fc8f  mov     rax, cs:__security_cookie
0x18003fc96  xor     rax, rsp
0x18003fc99  mov     [rbp+0F10h+var_40], rax
0x18003fca0  xor     esi, esi
0x18003fca2  mov     [rbp+0F10h+var_F28], r8
0x18003fca6  lea     r15, [rcx-1B8h]
0x18003fcad  mov     [rbp+0F10h+var_F38], rsi
0x18003fcb1  mov     r13, rdx
0x18003fcb4  mov     [rbp+0F10h+var_F58], rsi
0x18003fcb8  mov     r12, rcx
0x18003fcbb  lea     rdx, [r15+1C0h]; Src
0x18003fcc2  mov     ebx, esi
0x18003fcc4  lea     rcx, [rbp+0F10h+var_F20]; void *
0x18003fcc8  mov     r8d, 0EB8h; Size
0x18003fcce  mov     [rbp+0F10h+var_F48], rbx
0x18003fcd2  mov     edi, esi
0x18003fcd4  call    memcpy_0
0x18003fcd9  lea     r14, [r12-158h]
0x18003fce1  mov     [rbp+0F10h+hMem], rsi
0x18003fce5  xorps   xmm0, xmm0
0x18003fce8  mov     [rbp+0F10h+var_F50], esi
0x18003fceb  movups  xmmword ptr [rbp+0F10h+pguid.Data1], xmm0
0x18003fcf2  mov     [rbp+0F10h+var_F80], r14
0x18003fcf6  cmp     [r14+8], esi
0x18003fcfa  jz      short loc_18003FD05
0x18003fcfc  mov     rcx, [r14]
0x18003fcff  call    cs:__imp_PAL_System_CritSecEnter
0x18003fd05  mov     rax, [r15]
0x18003fd08  mov     rcx, r15
0x18003fd0b  mov     rax, [rax+50h]
0x18003fd0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd14  test    eax, eax
0x18003fd16  jnz     short loc_18003FD40
0x18003fd18  cmp     [r12-168h], rsi
0x18003fd20  jz      short loc_18003FD40
0x18003fd22  lea     rcx, [rbp+0F10h+var_F38]
0x18003fd26  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18003fd2b  mov     rdi, [r12-168h]
0x18003fd33  lea     rcx, [rbp+0F10h+var_F38]
0x18003fd37  mov     [rbp+0F10h+var_F38], rdi
0x18003fd3b  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18003fd40  lea     rcx, [rbp+0F10h+var_F80]; this
0x18003fd44  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18003fd49  mov     eax, cs:dword_1801B76C8
0x18003fd4f  cmp     eax, 4
0x18003fd52  jbe     short loc_18003FD74
0x18003fd54  lea     rax, aCumrdplistener_22; "CUMRDPListenerNPDebug: OnConnectionComp"...
0x18003fd5b  mov     [rbp+0F10h+var_F80], rax
0x18003fd5f  lea     rdx, byte_18018F2D1
0x18003fd66  lea     rax, [rbp+0F10h+var_F80]
0x18003fd6a  mov     [rsp+1010h+var_FF0], rax
0x18003fd6f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003fd74  lea     rcx, [rbp+0F10h+pguid]; pguid
0x18003fd7b  call    cs:__imp_CoCreateGuid
0x18003fd81  mov     esi, eax
0x18003fd83  test    eax, eax
0x18003fd85  jns     loc_18003FE17
0x18003fd8b  mov     ecx, cs:dword_1801B76C8
0x18003fd91  cmp     ecx, 2
0x18003fd94  jbe     loc_1800402BD
0x18003fd9a  lea     rax, aFailedToGenera; "Failed to generate a connection GUID"
0x18003fda1  mov     [rbp+0F10h+var_F90], 846h
0x18003fda8  mov     [rbp+0F10h+var_F80], rax
0x18003fdac  lea     rdx, byte_18018F27B
0x18003fdb3  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x18003fdba  mov     dword ptr [rbp+0F10h+var_F88], esi
0x18003fdbd  mov     [rbp+0F10h+var_F70], rax
0x18003fdc1  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003fdc8  mov     [rbp+0F10h+var_F68], rax
0x18003fdcc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003fdd3  mov     [rbp+0F10h+var_F78], rax
0x18003fdd7  lea     rax, [rbp+0F10h+var_F80]
0x18003fddb  mov     [rsp+1010h+var_FC8], rax
0x18003fde0  lea     rax, [rbp+0F10h+var_F70]
0x18003fde4  mov     [rsp+1010h+var_FD0], rax
0x18003fde9  lea     rax, [rbp+0F10h+var_F90]
0x18003fded  mov     [rsp+1010h+var_FD8], rax
0x18003fdf2  lea     rax, [rbp+0F10h+var_F68]
0x18003fdf6  mov     [rsp+1010h+var_FE0], rax
0x18003fdfb  lea     rax, [rbp+0F10h+var_F88]
0x18003fdff  mov     [rsp+1010h+var_FE8], rax
0x18003fe04  lea     rax, [rbp+0F10h+var_F78]
0x18003fe08  mov     [rsp+1010h+var_FF0], rax
0x18003fe0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003fe12  jmp     loc_1800402BD
0x18003fe17  lea     rdx, [rbp+0F10h+pguid]; struct _GUID *
0x18003fe1e  mov     [rbp+0F10h+var_F70], rbx
0x18003fe22  lea     rcx, [rbp+0F10h+ActivityId]; ActivityId
0x18003fe29  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18003fe2e  lea     r8, [rbp+0F10h+var_F70]; struct IRDPENCPlatformContext **
0x18003fe32  mov     rcx, r15; this
0x18003fe35  lea     rdx, [rbp+0F10h+pguid]; struct _GUID *
0x18003fe3c  call    ?CreateChildPlatformContext@CUMRDPListenerBase@@IEAAJPEAU_GUID@@PEAPEAUIRDPENCPlatformContext@@@Z; CUMRDPListenerBase::CreateChildPlatformContext(_GUID *,IRDPENCPlatformContext * *)
0x18003fe41  mov     esi, eax
0x18003fe43  test    eax, eax
0x18003fe45  jns     loc_18003FEEE
0x18003fe4b  mov     eax, cs:dword_1801B76C8
0x18003fe51  cmp     eax, 2
0x18003fe54  jbe     short loc_18003FECE
0x18003fe56  lea     rax, aFailedToInitia_37; "Failed to initialize the child platform"...
0x18003fe5d  mov     dword ptr [rbp+0F10h+var_F88], 850h
0x18003fe64  mov     [rbp+0F10h+var_F78], rax
0x18003fe68  lea     rdx, byte_18018F225
0x18003fe6f  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x18003fe76  mov     [rbp+0F10h+var_F68], rax
0x18003fe7a  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003fe81  mov     [rbp+0F10h+var_F80], rax
0x18003fe85  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003fe8c  mov     [rbp+0F10h+var_F60], rax
0x18003fe90  lea     rax, [rbp+0F10h+var_F78]
0x18003fe94  mov     [rsp+1010h+var_FC8], rax
0x18003fe99  lea     rax, [rbp+0F10h+var_F68]
0x18003fe9d  mov     [rsp+1010h+var_FD0], rax
0x18003fea2  lea     rax, [rbp+0F10h+var_F88]
0x18003fea6  mov     [rsp+1010h+var_FD8], rax
0x18003feab  lea     rax, [rbp+0F10h+var_F80]
0x18003feaf  mov     [rsp+1010h+var_FE0], rax
0x18003feb4  lea     rax, [rbp+0F10h+var_F90]
0x18003feb8  mov     [rsp+1010h+var_FE8], rax
0x18003febd  lea     rax, [rbp+0F10h+var_F60]
0x18003fec1  mov     [rsp+1010h+var_FF0], rax
0x18003fec6  mov     [rbp+0F10h+var_F90], esi
0x18003fec9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003fece  lea     rdx, [rbp+0F10h+ActivityId]; ActivityId
0x18003fed5  mov     ecx, 2; ControlCode
0x18003feda  call    cs:__imp_EventActivityIdControl
0x18003fee0  lea     rcx, [rbp+0F10h+var_F70]
0x18003fee4  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18003fee9  jmp     loc_1800402BD
0x18003feee  mov     rcx, [rbp+0F10h+var_F70]; struct IUnknown *
0x18003fef2  lea     r9, [rbp+0F10h+var_F58]; void **
0x18003fef6  lea     r8, IID_IUMRDPConnection; struct _GUID *
0x18003fefd  lea     rdx, CLSID_UMRDPConnection; struct _GUID *
0x18003ff04  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x18003ff09  mov     esi, eax
0x18003ff0b  test    eax, eax
0x18003ff0d  jns     short loc_18003FF8A
0x18003ff0f  mov     eax, cs:dword_1801B76C8
0x18003ff15  cmp     eax, 2
0x18003ff18  jbe     short loc_18003FECE
0x18003ff1a  lea     rax, aFailedToCreate; "Failed to create the UMRDP connection o"...
0x18003ff21  mov     dword ptr [rbp+0F10h+var_F88], 856h
0x18003ff28  mov     [rbp+0F10h+var_F60], rax
0x18003ff2c  lea     rdx, byte_18018F1CF
0x18003ff33  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x18003ff3a  mov     [rbp+0F10h+var_F78], rax
0x18003ff3e  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003ff45  mov     [rbp+0F10h+var_F68], rax
0x18003ff49  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003ff50  mov     [rbp+0F10h+var_F80], rax
0x18003ff54  lea     rax, [rbp+0F10h+var_F60]
0x18003ff58  mov     [rsp+1010h+var_FC8], rax
0x18003ff5d  lea     rax, [rbp+0F10h+var_F78]
0x18003ff61  mov     [rsp+1010h+var_FD0], rax
0x18003ff66  lea     rax, [rbp+0F10h+var_F88]
0x18003ff6a  mov     [rsp+1010h+var_FD8], rax
0x18003ff6f  lea     rax, [rbp+0F10h+var_F68]
0x18003ff73  mov     [rsp+1010h+var_FE0], rax
0x18003ff78  lea     rax, [rbp+0F10h+var_F90]
0x18003ff7c  mov     [rsp+1010h+var_FE8], rax
0x18003ff81  lea     rax, [rbp+0F10h+var_F80]
0x18003ff85  jmp     loc_18003FEC1
0x18003ff8a  mov     [rbp+0F10h+var_F80], r14
0x18003ff8e  cmp     [r14+8], ebx
0x18003ff92  jz      short loc_18003FF9D
0x18003ff94  mov     rcx, [r14]
0x18003ff97  call    cs:__imp_PAL_System_CritSecEnter
0x18003ff9d  mov     rdx, [rbp+0F10h+var_F28]; struct IUnknown *
0x18003ffa1  lea     r8, [rbp+0F10h+var_F88]; struct _PIPE_LISTENER_ENTRY **
0x18003ffa5  mov     rcx, r15; this
0x18003ffa8  mov     [rbp+0F10h+var_F88], rbx
0x18003ffac  call    ?FindListenerEntryByListener@CUMRDPListenerNPDebug@@AEAAHPEAUIUnknown@@PEAPEAU_PIPE_LISTENER_ENTRY@@@Z; CUMRDPListenerNPDebug::FindListenerEntryByListener(IUnknown *,_PIPE_LISTENER_ENTRY * *)
0x18003ffb1  test    eax, eax
0x18003ffb3  jz      loc_1800401FB
0x18003ffb9  mov     r14, [rbp+0F10h+var_F88]
0x18003ffbd  mov     rsi, [r14]
0x18003ffc0  test    rsi, rsi
0x18003ffc3  jz      short loc_18003FFE4
0x18003ffc5  lea     rcx, [rbp+0F10h+var_F48]
0x18003ffc9  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18003ffce  mov     rax, [rsi]
0x18003ffd1  mov     rbx, rsi
0x18003ffd4  mov     rcx, rsi
0x18003ffd7  mov     [rbp+0F10h+var_F48], rbx
0x18003ffdb  mov     rax, [rax+8]
0x18003ffdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffe4  mov     rcx, [r14]
0x18003ffe7  mov     rax, [rcx]
0x18003ffea  mov     rax, [rax+10h]
0x18003ffee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fff3  mov     qword ptr [r14], 0
0x18003fffa  mov     rax, [rbp+0F10h+var_F58]
0x18003fffe  mov     [r14+8], rax
0x180040002  mov     rcx, [rbp+0F10h+var_F58]
0x180040006  mov     rax, [rcx]
0x180040009  mov     rax, [rax+8]
0x18004000d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040012  mov     eax, [r14+10h]
0x180040016  lea     r9, [rbp+0F10h+var_F50]; unsigned int *
0x18004001a  mov     rdx, [r14+30h]; void *
0x18004001e  lea     r8, [rbp+0F10h+hMem]; void **
0x180040022  mov     rcx, r15; this
0x180040025  mov     dword ptr [rbp+0F10h+var_F88], eax
0x180040028  call    ?CreateConnectionSecurityDescriptor@CUMRDPListenerNPDebug@@AEAAJPEAXPEAPEAXPEAK@Z; CUMRDPListenerNPDebug::CreateConnectionSecurityDescriptor(void *,void * *,ulong *)
0x18004002d  mov     esi, eax
0x18004002f  test    eax, eax
0x180040031  jns     loc_1800400C3
0x180040037  mov     eax, cs:dword_1801B76C8
0x18004003d  cmp     eax, 2
0x180040040  jbe     loc_18004026F
0x180040046  lea     rax, aCreateconnecti; "CreateConnectionSecurityDescriptor fail"...
0x18004004d  mov     dword ptr [rbp+0F10h+var_F88], 873h
0x180040054  mov     [rbp+0F10h+var_F60], rax
0x180040058  lea     rdx, byte_18018F179
0x18004005f  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x180040066  mov     [rbp+0F10h+var_F90], esi
0x180040069  mov     [rbp+0F10h+var_F78], rax
0x18004006d  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180040074  mov     [rbp+0F10h+var_F68], rax
0x180040078  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18004007f  mov     [rbp+0F10h+var_F40], rax
0x180040083  lea     rax, [rbp+0F10h+var_F60]
0x180040087  mov     [rsp+1010h+var_FC8], rax
0x18004008c  lea     rax, [rbp+0F10h+var_F78]
0x180040090  mov     [rsp+1010h+var_FD0], rax
0x180040095  lea     rax, [rbp+0F10h+var_F88]
0x180040099  mov     [rsp+1010h+var_FD8], rax
0x18004009e  lea     rax, [rbp+0F10h+var_F68]
0x1800400a2  mov     [rsp+1010h+var_FE0], rax
0x1800400a7  lea     rax, [rbp+0F10h+var_F90]
0x1800400ab  mov     [rsp+1010h+var_FE8], rax
0x1800400b0  lea     rax, [rbp+0F10h+var_F40]
0x1800400b4  mov     [rsp+1010h+var_FF0], rax
0x1800400b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800400be  jmp     loc_18004026F
0x1800400c3  lea     rcx, [rbp+0F10h+var_F80]; this
0x1800400c7  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800400cc  mov     rax, [rbp+0F10h+hMem]
0x1800400d0  xor     r9d, r9d
0x1800400d3  mov     rcx, [r12-0C0h]
0x1800400db  mov     rdx, r15
0x1800400de  mov     r10, [rbp+0F10h+var_F58]
0x1800400e2  movups  xmm0, xmmword ptr [rbp+0F10h+pguid.Data1]
0x1800400e9  mov     r8, [r12-160h]
0x1800400f1  mov     [rsp+1010h+var_FA8], 0
0x1800400fa  mov     [rsp+1010h+var_FB0], 0
0x180040103  mov     [rsp+1010h+var_FB8], 0
0x18004010c  mov     [rsp+1010h+var_FC0], rcx
0x180040111  lea     rcx, [rbp+0F10h+var_F20]
0x180040115  mov     [rsp+1010h+var_FC8], rcx
0x18004011a  mov     ecx, dword ptr [rbp+0F10h+var_F88]
0x18004011d  mov     dword ptr [rsp+1010h+var_FD0], ecx
0x180040121  mov     rcx, [r12-0F0h]
0x180040129  mov     [rbp+0F10h+var_90], rax
0x180040130  mov     eax, [rbp+0F10h+var_F50]
0x180040133  mov     [rbp+0F10h+var_94], eax
0x180040139  mov     [rsp+1010h+var_FD8], 0
0x180040142  mov     [rsp+1010h+var_FE0], rcx
0x180040147  mov     rcx, r10
0x18004014a  movdqu  [rbp+0F10h+var_88], xmm0
0x180040152  mov     rax, [r10]
0x180040155  mov     [rsp+1010h+var_FE8], rdi
0x18004015a  mov     [rsp+1010h+var_FF0], r13
0x18004015f  mov     rax, [rax+18h]
0x180040163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040168  mov     esi, eax
0x18004016a  test    eax, eax
0x18004016c  jns     loc_180040278
0x180040172  mov     eax, cs:dword_1801B76C8
0x180040178  cmp     eax, 2
0x18004017b  jbe     loc_180040278
0x180040181  lea     rax, aFailedToInitia_11; "Failed to initialize connection"
0x180040188  mov     dword ptr [rbp+0F10h+var_F88], 890h
0x18004018f  mov     [rbp+0F10h+var_F40], rax
0x180040193  lea     rdx, byte_18018F0D5
0x18004019a  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x1800401a1  mov     [rbp+0F10h+var_F90], esi
0x1800401a4  mov     [rbp+0F10h+var_F60], rax
0x1800401a8  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x1800401af  mov     [rbp+0F10h+var_F78], rax
0x1800401b3  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800401ba  mov     [rbp+0F10h+var_F68], rax
0x1800401be  lea     rax, [rbp+0F10h+var_F40]
0x1800401c2  mov     [rsp+1010h+var_FC8], rax
0x1800401c7  lea     rax, [rbp+0F10h+var_F60]
0x1800401cb  mov     [rsp+1010h+var_FD0], rax
0x1800401d0  lea     rax, [rbp+0F10h+var_F88]
0x1800401d4  mov     [rsp+1010h+var_FD8], rax
0x1800401d9  lea     rax, [rbp+0F10h+var_F78]
0x1800401dd  mov     [rsp+1010h+var_FE0], rax
  ... truncated ...
```
