# CUMRDPListenerVMBus::OnConnectionCompleted(void *)

- ea: `0x180064ae0`
- end: `0x18006504f`
- name: `?OnConnectionCompleted@CUMRDPListenerVMBus@@UEAAJPEAX@Z`
- size: `1391`
- prototype: `__int64 __fastcall(CUMRDPListenerVMBus *__hidden this, HANDLE hObject)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x180010908`
- `0x180012200`
- `0x180017db4`
- `0x18001c164`
- `0x180033da0`
- `0x180034970`
- `0x180064ae0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064ea7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180064bb7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180064bb7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180064e8b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180064fa8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180064fe0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180064e8b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180064fa8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180064fe0`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180064b46`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180064ec0`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180064b46`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180064ec0`

## string_xrefs

- `0x180064d2d`: `Failed to create the UMRDP connection object`
- `0x180064bef`: `OnConnectionCompleted`
- `0x180064ca6`: `OnConnectionCompleted`
- `0x180064e23`: `OnConnectionCompleted`
- `0x180064f35`: `OnConnectionCompleted`
- `0x180064b93`: `CUMRDPListenerVMBus: OnConnectionCompleted`

## pseudocode

```c
__int64 __fastcall CUMRDPListenerVMBus::OnConnectionCompleted(CUMRDPListenerVMBus *this, HANDLE hObject)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // r15
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HRESULT v13; // eax
  int v14; // r8d
  int v15; // r9d
  int v16; // esi
  int v17; // ecx
  __int64 v18; // r8
  int v19; // r9d
  char *v20; // rdx
  const char **v21; // rax
  const char *v22; // rax
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  bool v28; // zf
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  void *v38; // rcx
  const char **v40; // [rsp+30h] [rbp-D0h]
  const char **v41; // [rsp+40h] [rbp-C0h]
  const char **v42; // [rsp+48h] [rbp-B8h]
  __int64 v43; // [rsp+50h] [rbp-B0h]
  int v44; // [rsp+80h] [rbp-80h] BYREF
  int v45; // [rsp+84h] [rbp-7Ch] BYREF
  const char *v46; // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown *v47; // [rsp+90h] [rbp-70h] BYREF
  const char *v48; // [rsp+98h] [rbp-68h] BYREF
  const char *v49; // [rsp+A0h] [rbp-60h] BYREF
  void *v50; // [rsp+A8h] [rbp-58h] BYREF
  const char *v51; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-48h] BYREF
  const char *v53; // [rsp+C0h] [rbp-40h] BYREF
  GUID ActivityId; // [rsp+C8h] [rbp-38h] BYREF
  GUID pguid; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v56[3]; // [rsp+F0h] [rbp-10h] BYREF
  char v57; // [rsp+FFh] [rbp-1h]
  char v58; // [rsp+107h] [rbp+7h]
  char v59; // [rsp+10Fh] [rbp+Fh]
  int v60; // [rsp+F70h] [rbp+E70h]
  int v61; // [rsp+F78h] [rbp+E78h]
  GUID v62; // [rsp+F88h] [rbp+E88h]

  v4 = 0;
  v52 = 0;
  v50 = 0;
  memset_0(v56, 0, 0xEB8u);
  v7 = (_QWORD *)((char *)this + 96);
  pguid = 0;
  v46 = (char *)this + 96;
  if ( *((_DWORD *)this + 26) )
    PAL_System_CritSecEnter(*v7, v5, v6);
  if ( !(*(unsigned int (__fastcall **)(CUMRDPListenerVMBus *))(*(_QWORD *)this + 80LL))(this) && *((_QWORD *)this + 10) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v52, v8, v9);
    v4 = *((_QWORD *)this + 10);
    v52 = v4;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v52);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v46);
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    v46 = "CUMRDPListenerVMBus: OnConnectionCompleted";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v10,
      (unsigned int)byte_18019BF4D,
      v11,
      v12,
      (__int64)&v46);
  }
  v13 = CoCreateGuid(&pguid);
  v16 = v13;
  if ( v13 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v44 = 1401;
      v46 = "Failed to generate a connection GUID";
      v45 = v13;
      v47 = (struct IUnknown *)"OnConnectionCompleted";
      v48 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
      v49 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_1801B76C8,
        (unsigned int)byte_18019BEF9,
        v14,
        v15,
        (__int64)&v49,
        (__int64)&v45,
        (__int64)&v48,
        (__int64)&v44,
        (__int64)&v47,
        (__int64)&v46);
    }
    goto LABEL_23;
  }
  v47 = 0;
  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, &pguid);
  v16 = CUMRDPListenerBase::CreateChildPlatformContext(this, &pguid, (struct IRDPENCPlatformContext **)&v47);
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v45 = 1411;
      v49 = "Failed to initialize the child platform context";
      v20 = byte_18019BEA5;
      v48 = "OnConnectionCompleted";
      v46 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
      v51 = "Error HResult failed";
      v42 = &v49;
      v41 = &v48;
      v40 = &v46;
      v21 = &v51;
LABEL_21:
      v44 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v17,
        (_DWORD)v20,
        v18,
        v19,
        (__int64)v21,
        (__int64)&v44,
        (__int64)v40,
        (__int64)&v45,
        (__int64)v41,
        (__int64)v42);
    }
LABEL_22:
    EventActivityIdControl(2u, &ActivityId);
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v26, v27);
LABEL_23:
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    goto LABEL_35;
  }
  v16 = __RDPAPIDLL__CreateInstance(v47, &CLSID_UMRDPConnection, &IID_IUMRDPConnection, &v50);
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_22;
    v22 = "Failed to create the UMRDP connection object";
    v45 = 1417;
    v20 = byte_18019BE51;
LABEL_20:
    v51 = v22;
    v49 = "OnConnectionCompleted";
    v48 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
    v46 = "Error HResult failed";
    v42 = &v51;
    v41 = &v49;
    v40 = &v48;
    v21 = &v46;
    goto LABEL_21;
  }
  memset_0(v56, 0, 0xEB8u);
  v23 = *((_QWORD *)this + 11);
  v43 = *((_QWORD *)this + 31);
  v24 = *((_QWORD *)this + 25);
  v56[0] = 1;
  v58 = 1;
  v57 = 1;
  v60 = 1;
  v61 = -1;
  v62 = pguid;
  v59 = 2;
  v16 = (*(__int64 (__fastcall **)(void *, CUMRDPListenerVMBus *, __int64, _QWORD, HANDLE, __int64, __int64, _QWORD, int, _DWORD *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v50 + 24LL))(
          v50,
          this,
          v23,
          0,
          hObject,
          v4,
          v24,
          0,
          -1,
          v56,
          v43,
          0,
          0,
          0);
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_22;
    v22 = "Failed to initialize connection";
    v45 = 1442;
    v20 = byte_18019BDFD;
    goto LABEL_20;
  }
  v28 = *((_DWORD *)this + 26) == 0;
  v46 = (char *)this + 96;
  if ( !v28 )
    PAL_System_CritSecEnter(*v7, v25, v18);
  if ( !*((_DWORD *)this + 60) || (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)v50 + 48LL))(v50) )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v50 + 32LL))(v50);
    v16 = -2147467260;
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(char *, void *))(*((_QWORD *)this + 26) + 8LL))((char *)this + 208, v50);
    if ( v16 >= 0 )
    {
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v46);
      EventActivityIdControl(2u, &ActivityId);
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v32, v33);
      goto LABEL_36;
    }
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v45 = 1456;
      v51 = "Failed to add the element to the list";
      v44 = v16;
      v49 = "OnConnectionCompleted";
      v48 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpvmconnectlistener.cpp";
      v53 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v29,
        (unsigned int)byte_18019BDA9,
        v30,
        v31,
        (__int64)&v53,
        (__int64)&v44,
        (__int64)&v48,
        (__int64)&v45,
        (__int64)&v49,
        (__int64)&v51);
    }
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v46);
  EventActivityIdControl(2u, &ActivityId);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v47, v36, v37);
LABEL_35:
  (*(void (__fastcall **)(CUMRDPListenerVMBus *, _QWORD))(*(_QWORD *)this + 104LL))(this, (unsigned int)v16);
LABEL_36:
  v38 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v52, v34, v35);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180064ae0  mov     [rsp-8+arg_10], rbx
0x180064ae5  push    rbp
0x180064ae6  push    rsi
0x180064ae7  push    r12
0x180064ae9  push    r14
0x180064aeb  push    r15
0x180064aed  lea     rbp, [rsp-0EC0h]
0x180064af5  sub     rsp, 0FC0h
0x180064afc  mov     rax, cs:__security_cookie
0x180064b03  xor     rax, rsp
0x180064b06  mov     [rbp+0EE0h+var_30], rax
0x180064b0d  mov     r12, rdx
0x180064b10  mov     r14, rcx
0x180064b13  xor     ebx, ebx
0x180064b15  lea     rcx, [rbp+0EE0h+var_EF0]; void *
0x180064b19  xor     edx, edx; Val
0x180064b1b  mov     [rbp+0EE0h+var_F28], rbx
0x180064b1f  mov     r8d, 0EB8h; Size
0x180064b25  mov     [rbp+0EE0h+var_F38], rbx
0x180064b29  call    memset_0
0x180064b2e  lea     r15, [r14+60h]
0x180064b32  xorps   xmm0, xmm0
0x180064b35  movups  xmmword ptr [rbp+0EE0h+pguid.Data1], xmm0
0x180064b39  mov     [rbp+0EE0h+var_F58], r15
0x180064b3d  cmp     [r15+8], ebx
0x180064b41  jz      short loc_180064B4C
0x180064b43  mov     rcx, [r15]
0x180064b46  call    cs:__imp_PAL_System_CritSecEnter
0x180064b4c  mov     rax, [r14]
0x180064b4f  mov     rcx, r14
0x180064b52  mov     rax, [rax+50h]
0x180064b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b5b  test    eax, eax
0x180064b5d  jnz     short loc_180064B7F
0x180064b5f  cmp     [r14+50h], rbx
0x180064b63  jz      short loc_180064B7F
0x180064b65  lea     rcx, [rbp+0EE0h+var_F28]
0x180064b69  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180064b6e  mov     rbx, [r14+50h]
0x180064b72  lea     rcx, [rbp+0EE0h+var_F28]
0x180064b76  mov     [rbp+0EE0h+var_F28], rbx
0x180064b7a  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180064b7f  lea     rcx, [rbp+0EE0h+var_F58]; this
0x180064b83  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180064b88  mov     eax, cs:dword_1801B76C8
0x180064b8e  cmp     eax, 4
0x180064b91  jbe     short loc_180064BB3
0x180064b93  lea     rax, aCumrdplistener_5; "CUMRDPListenerVMBus: OnConnectionComple"...
0x180064b9a  mov     [rbp+0EE0h+var_F58], rax
0x180064b9e  lea     rdx, byte_18019BF4D
0x180064ba5  lea     rax, [rbp+0EE0h+var_F58]
0x180064ba9  mov     [rsp+0FE0h+var_FC0], rax
0x180064bae  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180064bb3  lea     rcx, [rbp+0EE0h+pguid]; pguid
0x180064bb7  call    cs:__imp_CoCreateGuid
0x180064bbd  mov     esi, eax
0x180064bbf  test    eax, eax
0x180064bc1  jns     loc_180064C53
0x180064bc7  mov     ecx, cs:dword_1801B76C8
0x180064bcd  cmp     ecx, 2
0x180064bd0  jbe     loc_180064E9A
0x180064bd6  lea     rax, aFailedToGenera; "Failed to generate a connection GUID"
0x180064bdd  mov     [rbp+0EE0h+var_F60], 579h
0x180064be4  mov     [rbp+0EE0h+var_F58], rax
0x180064be8  lea     rdx, byte_18019BEF9
0x180064bef  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x180064bf6  mov     [rbp+0EE0h+var_F5C], esi
0x180064bf9  mov     [rbp+0EE0h+var_F50], rax
0x180064bfd  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180064c04  mov     [rbp+0EE0h+var_F48], rax
0x180064c08  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180064c0f  mov     [rbp+0EE0h+var_F40], rax
0x180064c13  lea     rax, [rbp+0EE0h+var_F58]
0x180064c17  mov     [rsp+0FE0h+var_F98], rax
0x180064c1c  lea     rax, [rbp+0EE0h+var_F50]
0x180064c20  mov     [rsp+0FE0h+var_FA0], rax
0x180064c25  lea     rax, [rbp+0EE0h+var_F60]
0x180064c29  mov     [rsp+0FE0h+var_FA8], rax
0x180064c2e  lea     rax, [rbp+0EE0h+var_F48]
0x180064c32  mov     [rsp+0FE0h+var_FB0], rax
0x180064c37  lea     rax, [rbp+0EE0h+var_F5C]
0x180064c3b  mov     [rsp+0FE0h+var_FB8], rax
0x180064c40  lea     rax, [rbp+0EE0h+var_F40]
0x180064c44  mov     [rsp+0FE0h+var_FC0], rax
0x180064c49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180064c4e  jmp     loc_180064E9A
0x180064c53  lea     rdx, [rbp+0EE0h+pguid]; struct _GUID *
0x180064c57  mov     [rbp+0EE0h+var_F50], 0
0x180064c5f  lea     rcx, [rbp+0EE0h+ActivityId]; ActivityId
0x180064c63  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180064c68  lea     r8, [rbp+0EE0h+var_F50]; struct IRDPENCPlatformContext **
0x180064c6c  mov     rcx, r14; this
0x180064c6f  lea     rdx, [rbp+0EE0h+pguid]; struct _GUID *
0x180064c73  call    ?CreateChildPlatformContext@CUMRDPListenerBase@@IEAAJPEAU_GUID@@PEAPEAUIRDPENCPlatformContext@@@Z; CUMRDPListenerBase::CreateChildPlatformContext(_GUID *,IRDPENCPlatformContext * *)
0x180064c78  mov     esi, eax
0x180064c7a  test    eax, eax
0x180064c7c  jns     short loc_180064CFD
0x180064c7e  mov     eax, cs:dword_1801B76C8
0x180064c84  cmp     eax, 2
0x180064c87  jbe     loc_180064E82
0x180064c8d  lea     rax, aFailedToInitia_37; "Failed to initialize the child platform"...
0x180064c94  mov     [rbp+0EE0h+var_F5C], 583h
0x180064c9b  mov     [rbp+0EE0h+var_F40], rax
0x180064c9f  lea     rdx, byte_18019BEA5
0x180064ca6  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x180064cad  mov     [rbp+0EE0h+var_F48], rax
0x180064cb1  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180064cb8  mov     [rbp+0EE0h+var_F58], rax
0x180064cbc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180064cc3  mov     [rbp+0EE0h+var_F30], rax
0x180064cc7  lea     rax, [rbp+0EE0h+var_F40]
0x180064ccb  mov     [rsp+0FE0h+var_F98], rax
0x180064cd0  lea     rax, [rbp+0EE0h+var_F48]
0x180064cd4  mov     [rsp+0FE0h+var_FA0], rax
0x180064cd9  lea     rax, [rbp+0EE0h+var_F5C]
0x180064cdd  mov     [rsp+0FE0h+var_FA8], rax
0x180064ce2  lea     rax, [rbp+0EE0h+var_F58]
0x180064ce6  mov     [rsp+0FE0h+var_FB0], rax
0x180064ceb  lea     rax, [rbp+0EE0h+var_F60]
0x180064cef  mov     [rsp+0FE0h+var_FB8], rax
0x180064cf4  lea     rax, [rbp+0EE0h+var_F30]
0x180064cf8  jmp     loc_180064E75
0x180064cfd  mov     rcx, [rbp+0EE0h+var_F50]; struct IUnknown *
0x180064d01  lea     r9, [rbp+0EE0h+var_F38]; void **
0x180064d05  lea     r8, IID_IUMRDPConnection; struct _GUID *
0x180064d0c  lea     rdx, CLSID_UMRDPConnection; struct _GUID *
0x180064d13  call    ?__RDPAPIDLL__CreateInstance@@YAJPEAUIUnknown@@AEBU_GUID@@1PEAPEAX@Z; __RDPAPIDLL__CreateInstance(IUnknown *,_GUID const &,_GUID const &,void * *)
0x180064d18  mov     esi, eax
0x180064d1a  test    eax, eax
0x180064d1c  jns     short loc_180064D47
0x180064d1e  mov     eax, cs:dword_1801B76C8
0x180064d24  cmp     eax, 2
0x180064d27  jbe     loc_180064E82
0x180064d2d  lea     rax, aFailedToCreate; "Failed to create the UMRDP connection o"...
0x180064d34  mov     [rbp+0EE0h+var_F5C], 589h
0x180064d3b  lea     rdx, byte_18019BE51
0x180064d42  jmp     loc_180064E1F
0x180064d47  xor     edx, edx; Val
0x180064d49  lea     rcx, [rbp+0EE0h+var_EF0]; void *
0x180064d4d  mov     r8d, 0EB8h; Size
0x180064d53  call    memset_0
0x180064d58  mov     r10, [rbp+0EE0h+var_F38]
0x180064d5c  mov     eax, 1
0x180064d61  mov     rcx, [r14+0F8h]
0x180064d68  or      edx, 0FFFFFFFFh
0x180064d6b  movups  xmm0, xmmword ptr [rbp+0EE0h+pguid.Data1]
0x180064d6f  mov     r8, [r14+58h]
0x180064d73  xor     r9d, r9d
0x180064d76  mov     [rsp+0FE0h+var_F78], 0
0x180064d7f  mov     [rsp+0FE0h+var_F80], 0
0x180064d88  mov     [rsp+0FE0h+var_F88], 0
0x180064d91  mov     [rsp+0FE0h+var_F90], rcx
0x180064d96  lea     rcx, [rbp+0EE0h+var_EF0]
0x180064d9a  mov     [rsp+0FE0h+var_F98], rcx
0x180064d9f  mov     rcx, [r14+0C8h]
0x180064da6  mov     dword ptr [rsp+0FE0h+var_FA0], edx
0x180064daa  mov     [rbp+0EE0h+var_EF0], eax
0x180064dad  mov     [rbp+0EE0h+var_ED9], al
0x180064db0  mov     [rbp+0EE0h+var_EE1], al
0x180064db3  mov     [rbp+0EE0h+var_70], eax
0x180064db9  mov     [rbp+0EE0h+var_68], edx
0x180064dbf  mov     rdx, r14
0x180064dc2  mov     [rsp+0FE0h+var_FA8], 0
0x180064dcb  mov     [rsp+0FE0h+var_FB0], rcx
0x180064dd0  mov     rcx, r10
0x180064dd3  movdqu  [rbp+0EE0h+var_58], xmm0
0x180064ddb  mov     [rbp+0EE0h+var_ED1], 2
0x180064ddf  mov     rax, [r10]
0x180064de2  mov     [rsp+0FE0h+var_FB8], rbx
0x180064de7  mov     [rsp+0FE0h+var_FC0], r12
0x180064dec  mov     rax, [rax+18h]
0x180064df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064df5  mov     esi, eax
0x180064df7  test    eax, eax
0x180064df9  jns     loc_180064EB2
0x180064dff  mov     eax, cs:dword_1801B76C8
0x180064e05  cmp     eax, 2
0x180064e08  jbe     short loc_180064E82
0x180064e0a  lea     rax, aFailedToInitia_11; "Failed to initialize connection"
0x180064e11  mov     [rbp+0EE0h+var_F5C], 5A2h
0x180064e18  lea     rdx, byte_18019BDFD
0x180064e1f  mov     [rbp+0EE0h+var_F30], rax
0x180064e23  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x180064e2a  mov     [rbp+0EE0h+var_F40], rax
0x180064e2e  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180064e35  mov     [rbp+0EE0h+var_F48], rax
0x180064e39  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180064e40  mov     [rbp+0EE0h+var_F58], rax
0x180064e44  lea     rax, [rbp+0EE0h+var_F30]
0x180064e48  mov     [rsp+0FE0h+var_F98], rax
0x180064e4d  lea     rax, [rbp+0EE0h+var_F40]
0x180064e51  mov     [rsp+0FE0h+var_FA0], rax
0x180064e56  lea     rax, [rbp+0EE0h+var_F5C]
0x180064e5a  mov     [rsp+0FE0h+var_FA8], rax
0x180064e5f  lea     rax, [rbp+0EE0h+var_F48]
0x180064e63  mov     [rsp+0FE0h+var_FB0], rax
0x180064e68  lea     rax, [rbp+0EE0h+var_F60]
0x180064e6c  mov     [rsp+0FE0h+var_FB8], rax
0x180064e71  lea     rax, [rbp+0EE0h+var_F58]
0x180064e75  mov     [rsp+0FE0h+var_FC0], rax
0x180064e7a  mov     [rbp+0EE0h+var_F60], esi
0x180064e7d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180064e82  lea     rdx, [rbp+0EE0h+ActivityId]; ActivityId
0x180064e86  mov     ecx, 2; ControlCode
0x180064e8b  call    cs:__imp_EventActivityIdControl
0x180064e91  lea     rcx, [rbp+0EE0h+var_F50]
0x180064e95  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180064e9a  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180064e9e  jz      loc_180064FEF
0x180064ea4  mov     rcx, r12; hObject
0x180064ea7  call    cs:__imp_CloseHandle
0x180064ead  jmp     loc_180064FEF
0x180064eb2  cmp     dword ptr [r15+8], 0
0x180064eb7  mov     [rbp+0EE0h+var_F58], r15
0x180064ebb  jz      short loc_180064EC6
0x180064ebd  mov     rcx, [r15]
0x180064ec0  call    cs:__imp_PAL_System_CritSecEnter
0x180064ec6  cmp     dword ptr [r14+0F0h], 0
0x180064ece  jz      loc_180064FB9
0x180064ed4  mov     rcx, [rbp+0EE0h+var_F38]
0x180064ed8  mov     rax, [rcx]
0x180064edb  mov     rax, [rax+30h]
0x180064edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064ee4  test    eax, eax
0x180064ee6  jnz     loc_180064FB9
0x180064eec  mov     rdx, [rbp+0EE0h+var_F38]
0x180064ef0  lea     rcx, [r14+0D0h]
0x180064ef7  mov     rax, [rcx]
0x180064efa  mov     rax, [rax+8]
0x180064efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064f03  mov     esi, eax
0x180064f05  test    eax, eax
0x180064f07  jns     loc_180064F96
0x180064f0d  mov     eax, cs:dword_1801B76C8
0x180064f13  cmp     eax, 2
0x180064f16  jbe     loc_180064FCE
0x180064f1c  lea     rax, aFailedToAddThe_0; "Failed to add the element to the list"
0x180064f23  mov     [rbp+0EE0h+var_F5C], 5B0h
0x180064f2a  mov     [rbp+0EE0h+var_F30], rax
0x180064f2e  lea     rdx, byte_18019BDA9
0x180064f35  lea     rax, aOnconnectionco_0; "OnConnectionCompleted"
0x180064f3c  mov     [rbp+0EE0h+var_F60], esi
0x180064f3f  mov     [rbp+0EE0h+var_F40], rax
0x180064f43  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180064f4a  mov     [rbp+0EE0h+var_F48], rax
0x180064f4e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180064f55  mov     [rbp+0EE0h+var_F20], rax
0x180064f59  lea     rax, [rbp+0EE0h+var_F30]
0x180064f5d  mov     [rsp+0FE0h+var_F98], rax
0x180064f62  lea     rax, [rbp+0EE0h+var_F40]
0x180064f66  mov     [rsp+0FE0h+var_FA0], rax
0x180064f6b  lea     rax, [rbp+0EE0h+var_F5C]
0x180064f6f  mov     [rsp+0FE0h+var_FA8], rax
0x180064f74  lea     rax, [rbp+0EE0h+var_F48]
0x180064f78  mov     [rsp+0FE0h+var_FB0], rax
0x180064f7d  lea     rax, [rbp+0EE0h+var_F60]
0x180064f81  mov     [rsp+0FE0h+var_FB8], rax
0x180064f86  lea     rax, [rbp+0EE0h+var_F20]
0x180064f8a  mov     [rsp+0FE0h+var_FC0], rax
0x180064f8f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180064f94  jmp     short loc_180064FCE
0x180064f96  lea     rcx, [rbp+0EE0h+var_F58]; this
0x180064f9a  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180064f9f  lea     rdx, [rbp+0EE0h+ActivityId]; ActivityId
0x180064fa3  mov     ecx, 2; ControlCode
0x180064fa8  call    cs:__imp_EventActivityIdControl
0x180064fae  lea     rcx, [rbp+0EE0h+var_F50]
0x180064fb2  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180064fb7  jmp     short loc_180065000
0x180064fb9  mov     rcx, [rbp+0EE0h+var_F38]
0x180064fbd  mov     rax, [rcx]
0x180064fc0  mov     rax, [rax+20h]
0x180064fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064fc9  mov     esi, 80004004h
0x180064fce  lea     rcx, [rbp+0EE0h+var_F58]; this
0x180064fd2  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180064fd7  lea     rdx, [rbp+0EE0h+ActivityId]; ActivityId
0x180064fdb  mov     ecx, 2; ControlCode
0x180064fe0  call    cs:__imp_EventActivityIdControl
0x180064fe6  lea     rcx, [rbp+0EE0h+var_F50]
0x180064fea  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180064fef  mov     rax, [r14]
0x180064ff2  mov     edx, esi
0x180064ff4  mov     rcx, r14
0x180064ff7  mov     rax, [rax+68h]
0x180064ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065000  mov     rcx, [rbp+0EE0h+var_F38]
0x180065004  test    rcx, rcx
0x180065007  jz      short loc_18006501D
0x180065009  mov     [rbp+0EE0h+var_F38], 0
0x180065011  mov     rax, [rcx]
0x180065014  mov     rax, [rax+10h]
0x180065018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006501d  lea     rcx, [rbp+0EE0h+var_F28]
0x180065021  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180065026  mov     eax, esi
0x180065028  mov     rcx, [rbp+0EE0h+var_30]
0x18006502f  xor     rcx, rsp; StackCookie
0x180065032  call    __security_check_cookie
0x180065037  mov     rbx, [rsp+0FE0h+arg_10]
  ... truncated ...
```
