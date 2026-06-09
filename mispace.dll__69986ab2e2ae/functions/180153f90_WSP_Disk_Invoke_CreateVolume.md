# WSP_Disk_Invoke_CreateVolume

- ea: `0x180153f90`
- end: `0x18015478c`
- name: `WSP_Disk_Invoke_CreateVolume`
- size: `2044`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001994`
- `0x180004608`
- `0x180004c3c`
- `0x180006350`
- `0x1800063a0`
- `0x180006dd4`
- `0x18000b840`
- `0x18000ba50`
- `0x18000cca4`
- `0x18000ccd4`
- `0x1800142e8`
- `0x180014a54`
- `0x180015850`
- `0x180015a20`
- `0x180015c30`
- `0x180015ea0`
- `0x180015fc0`
- `0x1800167e0`
- `0x180016950`
- `0x180016b40`
- `0x180017020`
- `0x180023e18`
- `0x1800810a0`
- `0x1800810ec`
- `0x180081424`
- `0x180081d38`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180151cf8`
- `0x180153f90`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180154009`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180154074`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180154755`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180154009`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180154074`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180154755`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180154032`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180154032`

## string_xrefs

- `0x1801543d6`: `Create Volume`
- `0x180154086`: `WSP_Disk_Invoke_CreateVolume`
- `0x18015414e`: `WSP_Disk_Invoke_CreateVolume`
- `0x18015425a`: `WSP_Disk_Invoke_CreateVolume`
- `0x180154329`: `WSP_Disk_Invoke_CreateVolume`
- `0x180154568`: `WSP_Disk_Invoke_CreateVolume`
- `0x180154593`: `WSP_Disk_Invoke_CreateVolume`
- `0x180154155`: `CreateVolume`
- `0x1801545b2`: `CreateVolume`
- `0x18015463a`: `CreateVolume`

## pseudocode

```c
ULONG __fastcall WSP_Disk_Invoke_CreateVolume(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        void *a7)
{
  int v9; // r13d
  const MI_Char *v10; // rdx
  MI_Type *v11; // r8
  int v12; // r8d
  int v13; // r9d
  MI_Result v14; // ebx
  char IsRemoteInstance; // al
  __int64 v16; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r15d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // r8d
  int v23; // r9d
  const char *v24; // rax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  char *v28; // rdx
  unsigned int v29; // ebx
  int v30; // eax
  int v31; // edi
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int *v35; // rdx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int32 v41; // [rsp+74h] [rbp-8Ch] BYREF
  MI_Instance *p_self; // [rsp+78h] [rbp-88h] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  const char *v48; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h] BYREF
  const char *v50; // [rsp+B0h] [rbp-50h] BYREF
  const char *v51; // [rsp+B8h] [rbp-48h] BYREF
  const char *v52; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v55; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v56; // [rsp+E8h] [rbp-18h] BYREF
  MI_Value value; // [rsp+F0h] [rbp-10h] BYREF
  MI_Instance instance; // [rsp+120h] [rbp+20h] BYREF
  int v59; // [rsp+160h] [rbp+60h]
  char v60; // [rsp+164h] [rbp+64h]
  MI_Instance self; // [rsp+1D0h] [rbp+D0h] BYREF
  GUID ActivityId; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v63; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v64; // [rsp+300h] [rbp+200h]
  GUID v65; // [rsp+308h] [rbp+208h]
  GUID v66; // [rsp+318h] [rbp+218h] BYREF
  _BYTE v67[128]; // [rsp+330h] [rbp+230h] BYREF

  memset(&value, 0, sizeof(value));
  v9 = 1;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v10, v11, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v65 = ActivityId;
  v66 = ActivityId;
  EventActivityIdControl(4u, &v66);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v45 = 2251;
    v50 = "WSP_Disk_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Disk_Invoke_CreateVolume",
      (unsigned int)qword_1803594D0,
      v12,
      v13,
      (__int64)&v50,
      (__int64)&v45);
  }
  v50 = 0;
  LODWORD(v46) = 0;
  v44 = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xA0u);
  Block = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v53);
  CSmTimer::Start((CSmTimer *)&v53);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !*(_BYTE *)(a6 + 72) || !(unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64)) )
    v9 = 0;
  v45 = 0;
  v14 = (unsigned int)WspProviderEnter(a2);
  if ( v14 == MI_RESULT_OK )
  {
    IsRemoteInstance = WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64));
    v16 = *(_QWORD *)(a6 + 64);
    if ( IsRemoteInstance )
    {
      v14 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *(unsigned __int16 **)(a6 + 64), a5, a7);
      goto LABEL_54;
    }
    v64 = 0;
    v63 = 0;
    LODWORD(v47) = 0;
    SubsystemType = WspGetSubsystemType(v16);
    SubsystemVersion = _GetSubsystemVersion(&v47);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v63);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v41 = SubsystemType;
      v40 = SubsystemVersion != v47;
      LOWORD(v47) = v64;
      p_self = (MI_Instance *)&v63;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&unk_180359408,
        v20,
        v21,
        (__int64)&p_self,
        (__int64)&v41,
        (__int64)&v47,
        (__int64)&v40);
    }
    if ( !a7 )
    {
      v14 = MI_RESULT_INVALID_PARAMETER;
      goto LABEL_16;
    }
    v14 = (unsigned int)WspUnpackObjectId(*(unsigned __int16 **)(a6 + 64), &v46, &v44, &v50);
    if ( v14 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_16;
      v40 = 2288;
      v28 = &byte_18035A1FF;
      goto LABEL_23;
    }
    v14 = MI_Context_ConstructParameters(a2, &WSP_Disk_CreateVolume_rtti, &instance);
    if ( v14 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = 2296;
        v28 = &byte_180358D3F;
LABEL_23:
        p_self = (MI_Instance *)"WSP_Disk_Invoke_CreateVolume";
        v41 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v25,
          (_DWORD)v28,
          v26,
          v27,
          (__int64)&p_self,
          (__int64)&v40,
          (__int64)&v41);
        goto LABEL_16;
      }
      goto LABEL_16;
    }
    v29 = v46;
    v30 = WspParseCreateVolumeParameters(a2, a7, (unsigned int)v46, &Block);
    LODWORD(v46) = v30;
    v31 = v30;
    if ( !v30 )
    {
      v14 = (unsigned int)WspRunMethodAsJob(
                            a2,
                            (__int64)L"Create Volume",
                            4u,
                            (__int64)WSP_Disk_Invoke_CreateVolume_Async,
                            (__int64)Block,
                            v29,
                            v44,
                            *(_QWORD *)(a6 + 64),
                            &instance,
                            &v46);
      if ( v14 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v40 = 2320;
          v28 = (char *)&unk_18035A390;
          goto LABEL_23;
        }
LABEL_16:
        CSmTimer::Stop((CSmTimer *)&v53);
        if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
        {
          p_self = 0;
          v46 = 0;
          v56 = 1000 * (v54 - v53) / v55;
          v47 = 0;
          v41 = v14;
          v44 = v9;
          v40 = v60 != 0 ? v59 : 0;
          if ( *(_BYTE *)(a6 + 72) )
            v24 = *(const char **)(a6 + 64);
          else
            v24 = 0;
          v51 = v24;
          v52 = "CreateVolume";
          v48 = "WspDisk";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v60 != 0 ? v59 : 0,
            (unsigned int)&byte_180358EC7,
            v22,
            v23,
            (__int64)&v48,
            (__int64)&v52,
            (__int64)&v51,
            (__int64)&v44,
            (__int64)&v40,
            (__int64)&v41,
            (__int64)&v56,
            (__int64)&v47,
            (__int64)&v46,
            (__int64)&p_self);
        }
        WspFreeString(v50);
        if ( Block )
          operator delete(Block);
        MI_Instance_Destruct(&self);
        MI_Instance_Destruct(&instance);
        goto LABEL_54;
      }
      v31 = v46;
      Block = 0;
LABEL_32:
      v59 = v31;
      v60 = 1;
      v14 = MI_Instance_Destruct((MI_Instance *)a2);
      if ( v14 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_16;
      v40 = 2363;
      v28 = byte_180358B29;
      goto LABEL_23;
    }
    if ( v30 != 43001 )
      goto LABEL_32;
    CSpExtendedStatus::CSpExtendedStatus((CSpExtendedStatus *)v67);
    CSpExtendedStatus::Initialize((CSpExtendedStatus *)v67, 0x8011u, 0);
    if ( a2 && a2->ft )
    {
      v14 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
              a2,
              &MSFT_StorageExtendedStatus_rtti,
              &self);
      if ( v14 == MI_RESULT_OK )
      {
        if ( !(unsigned int)CSpExtendedStatus::ToMsftExtendedStatus(
                              (CSpExtendedStatus *)v67,
                              (struct _MSFT_StorageExtendedStatus *)&self)
          || (p_self = &self,
              (v14 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, MI_Instance **, _QWORD, _DWORD))instance.ft->SetElementAt)(
                       &instance,
                       (unsigned int)(v14 + 7),
                       &p_self,
                       (unsigned int)(v14 + 15),
                       0)) == MI_RESULT_OK) )
        {
          CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)v67);
          goto LABEL_32;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v40 = 2345;
          v35 = &dword_180358BD4;
LABEL_47:
          p_self = (MI_Instance *)"WSP_Disk_Invoke_CreateVolume";
          v41 = v14;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v32,
            (_DWORD)v35,
            v33,
            v34,
            (__int64)&p_self,
            (__int64)&v40,
            (__int64)&v41);
          goto LABEL_48;
        }
        goto LABEL_48;
      }
    }
    else
    {
      v14 = MI_RESULT_INVALID_PARAMETER;
    }
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v40 = 2335;
      v35 = (int *)&unk_18035A238;
      goto LABEL_47;
    }
LABEL_48:
    CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)v67);
    goto LABEL_16;
  }
LABEL_54:
  MI_Context_PostResult_0(a2, v14);
  WspProviderExit(v45);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v53);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v52 = "CreateVolume";
        v48 = (const char *)(1000 * (v54 - v53) / v55);
        v51 = "WspDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v36,
          (unsigned int)byte_1803592B9,
          v37,
          v38,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&IsRemoteRequest,
          (__int64)&v48);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 2407;
    v48 = "WSP_Disk_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v36,
      (unsigned int)&byte_18035AD87,
      v37,
      v38,
      (__int64)&v48,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v53);
  return EventActivityIdControl(4u, &v66);
}

```

## disassembly

```asm
0x180153f90  mov     [rsp-8+arg_0], rbx
0x180153f95  push    rbp
0x180153f96  push    rsi
0x180153f97  push    rdi
0x180153f98  push    r12
0x180153f9a  push    r13
0x180153f9c  push    r14
0x180153f9e  push    r15
0x180153fa0  lea     rbp, [rsp-2C0h]
0x180153fa8  sub     rsp, 3C0h
0x180153faf  mov     rax, cs:__security_cookie
0x180153fb6  xor     rax, rsp
0x180153fb9  mov     [rbp+2F0h+var_40], rax
0x180153fc0  mov     r12, [rbp+2F0h+arg_20]
0x180153fc7  xorps   xmm0, xmm0
0x180153fca  mov     r14, [rbp+2F0h+arg_28]
0x180153fd1  xor     eax, eax
0x180153fd3  mov     rdi, [rbp+2F0h+arg_30]
0x180153fda  mov     rsi, rdx
0x180153fdd  movups  xmmword ptr [rbp+2F0h+value], xmm0
0x180153fe1  lea     rdx, [rbp+2F0h+ActivityId]; ActivityId
0x180153fe8  mov     r15, r9
0x180153feb  movups  xmmword ptr [rbp+2F0h+value+10h], xmm0
0x180153fef  lea     r13d, [rax+1]
0x180153ff3  mov     qword ptr [rbp+2F0h+value+20h], rax
0x180153ff7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180153ffe  mov     ecx, r13d; ControlCode
0x180154001  movdqu  xmmword ptr [rbp+2F0h+ActivityId.Data1], xmm0
0x180154009  call    cs:__imp_EventActivityIdControl
0x180154010  nop     dword ptr [rax+rax+00h]
0x180154015  lea     r9, [rbp+2F0h+value]; value
0x180154019  mov     rcx, rsi; context
0x18015401c  call    MI_Context_GetCustomOption_1
0x180154021  xor     ebx, ebx
0x180154023  test    eax, eax
0x180154025  jnz     short loc_18015403E
0x180154027  mov     rcx, qword ptr [rbp+2F0h+value]; lpsz
0x18015402b  lea     rdx, [rbp+2F0h+ActivityId]; pclsid
0x180154032  call    cs:__imp_CLSIDFromString
0x180154039  nop     dword ptr [rax+rax+00h]
0x18015403e  mov     rcx, qword ptr [rbp+2F0h+ActivityId.Data1]
0x180154045  lea     rdx, [rbp+2F0h+var_D8]; ActivityId
0x18015404c  mov     rax, qword ptr [rbp+2F0h+ActivityId.Data4]
0x180154053  mov     [rbp+2F0h+var_E8], rcx
0x18015405a  mov     qword ptr [rbp+2F0h+var_D8.Data1], rcx
0x180154061  mov     ecx, 4; ControlCode
0x180154066  mov     [rbp+2F0h+var_E0], rax
0x18015406d  mov     qword ptr [rbp+2F0h+var_D8.Data4], rax
0x180154074  call    cs:__imp_EventActivityIdControl
0x18015407b  nop     dword ptr [rax+rax+00h]
0x180154080  mov     eax, cs:dword_18039EB68
0x180154086  lea     rcx, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x18015408d  cmp     eax, 5
0x180154090  jbe     short loc_1801540BB
0x180154092  lea     rax, [rbp+2F0h+var_368]
0x180154096  mov     [rbp+2F0h+var_368], 8CBh
0x18015409d  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x1801540a2  lea     rdx, qword_1803594D0
0x1801540a9  lea     rax, [rbp+2F0h+var_340]
0x1801540ad  mov     [rbp+2F0h+var_340], rcx
0x1801540b1  mov     [rsp+3F0h+var_3D0], rax
0x1801540b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801540bb  xor     edx, edx; Val
0x1801540bd  mov     [rbp+2F0h+var_340], rbx
0x1801540c1  mov     r8d, 108h; Size
0x1801540c7  mov     dword ptr [rbp+2F0h+var_360], ebx
0x1801540ca  lea     rcx, [rbp+2F0h+self.classDecl]; void *
0x1801540d1  mov     [rbp+2F0h+var_36C], ebx
0x1801540d4  mov     [rbp+2F0h+self.ft], rbx
0x1801540db  call    memset_0
0x1801540e0  xor     edx, edx; Val
0x1801540e2  mov     [rbp+2F0h+instance.ft], rbx
0x1801540e6  mov     r8d, 0A0h; Size
0x1801540ec  lea     rcx, [rbp+2F0h+instance.classDecl]; void *
0x1801540f0  call    memset_0
0x1801540f5  lea     rcx, [rbp+2F0h+var_328]; this
0x1801540f9  mov     [rbp+2F0h+Block], rbx
0x1801540fd  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180154102  lea     rcx, [rbp+2F0h+var_328]; this
0x180154106  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015410b  mov     rcx, rsi; context
0x18015410e  call    WspIsRemoteRequest
0x180154113  mov     [rbp+2F0h+var_370], eax
0x180154116  cmp     [r14+48h], bl
0x18015411a  jz      short loc_180154129
0x18015411c  mov     rcx, [r14+40h]; unsigned __int16 *
0x180154120  call    WspIsRemoteInstance
0x180154125  test    al, al
0x180154127  jnz     short loc_18015412C
0x180154129  mov     r13d, ebx
0x18015412c  mov     rdx, [r14+40h]
0x180154130  lea     r9, [rbp+2F0h+var_368]
0x180154134  mov     r8d, 1
0x18015413a  mov     [rbp+2F0h+var_368], ebx
0x18015413d  mov     rcx, rsi; context
0x180154140  call    WspProviderEnter
0x180154145  mov     ebx, eax
0x180154147  test    eax, eax
0x180154149  jz      short loc_180154168
0x18015414b  xor     r12d, r12d
0x18015414e  lea     rdi, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x180154155  lea     r14, aCreatevolume_0; "CreateVolume"
0x18015415c  lea     r15, aWspdisk; "WspDisk"
0x180154163  jmp     loc_18015466D
0x180154168  mov     rcx, [r14+40h]; unsigned __int16 *
0x18015416c  call    WspIsRemoteInstance
0x180154171  mov     rcx, [r14+40h]
0x180154175  test    al, al
0x180154177  jz      short loc_180154193
0x180154179  mov     r8, rcx; unsigned __int16 *
0x18015417c  mov     [rsp+3F0h+var_3D0], rdi; void *
0x180154181  mov     rcx, rsi; struct _MI_Context *
0x180154184  mov     r9, r12; unsigned __int16 *
0x180154187  mov     rdx, r15; unsigned __int16 *
0x18015418a  call    WspInvokeRemoteMethod
0x18015418f  mov     ebx, eax
0x180154191  jmp     short loc_18015414B
0x180154193  xorps   xmm0, xmm0
0x180154196  xor     eax, eax
0x180154198  xor     r12d, r12d
0x18015419b  mov     [rbp+2F0h+var_F0], eax
0x1801541a1  movups  [rbp+2F0h+var_100], xmm0
0x1801541a8  mov     dword ptr [rbp+2F0h+var_358], r12d
0x1801541ac  call    WspGetSubsystemType
0x1801541b1  lea     rcx, [rbp+2F0h+var_358]
0x1801541b5  mov     ebx, eax
0x1801541b7  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801541bc  lea     rdx, [rbp+2F0h+var_100]; struct _SUBSYSTEM_INFO *
0x1801541c3  mov     ecx, ebx; unsigned int
0x1801541c5  mov     r15d, eax
0x1801541c8  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801541cd  mov     ecx, cs:dword_18039EB68
0x1801541d3  cmp     ecx, 5
0x1801541d6  jbe     short loc_18015424E
0x1801541d8  mov     rdx, 400000000000h
0x1801541e2  lea     rcx, dword_18039EB68
0x1801541e9  call    _tlgKeywordOn
0x1801541ee  test    al, al
0x1801541f0  jz      short loc_18015424E
0x1801541f2  cmp     r15d, dword ptr [rbp+2F0h+var_358]
0x1801541f6  lea     rdx, unk_180359408
0x1801541fd  mov     eax, r12d
0x180154200  mov     [rsp+3F0h+var_37C], ebx
0x180154204  setnz   al
0x180154207  mov     [rsp+3F0h+var_380], eax
0x18015420b  movzx   eax, word ptr [rbp+2F0h+var_F0]
0x180154212  mov     word ptr [rbp+2F0h+var_358], ax
0x180154216  lea     rax, [rbp+2F0h+var_100]
0x18015421d  mov     [rsp+3F0h+var_378], rax
0x180154222  lea     rax, [rsp+3F0h+var_380]
0x180154227  mov     [rsp+3F0h+var_3B8], rax
0x18015422c  lea     rax, [rbp+2F0h+var_358]
0x180154230  mov     qword ptr [rsp+3F0h+var_3C0], rax
0x180154235  lea     rax, [rsp+3F0h+var_37C]
0x18015423a  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x18015423f  lea     rax, [rsp+3F0h+var_378]
0x180154244  mov     [rsp+3F0h+var_3D0], rax
0x180154249  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18015424e  test    rdi, rdi
0x180154251  jnz     loc_1801542E6
0x180154257  lea     ebx, [rdi+4]
0x18015425a  lea     rdi, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x180154261  lea     rcx, [rbp+2F0h+var_328]; this
0x180154265  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015426a  mov     eax, cs:dword_18039EB68
0x180154270  cmp     eax, 5
0x180154273  jbe     loc_180154633
0x180154279  mov     rdx, 400000000000h
0x180154283  lea     rcx, dword_18039EB68
0x18015428a  call    _tlgKeywordOn
0x18015428f  test    al, al
0x180154291  jz      loc_180154633
0x180154297  mov     rax, [rbp+2F0h+var_320]
0x18015429b  xor     edx, edx
0x18015429d  sub     rax, [rbp+2F0h+var_328]
0x1801542a1  imul    rax, 3E8h
0x1801542a8  mov     [rsp+3F0h+var_378], r12
0x1801542ad  div     [rbp+2F0h+var_318]
0x1801542b1  mov     [rbp+2F0h+var_360], r12
0x1801542b5  mov     [rbp+2F0h+var_308], rax
0x1801542b9  mov     al, [rbp+2F0h+var_28C]
0x1801542bc  neg     al
0x1801542be  mov     [rbp+2F0h+var_358], r12
0x1801542c2  mov     [rsp+3F0h+var_37C], ebx
0x1801542c6  sbb     ecx, ecx
0x1801542c8  mov     [rbp+2F0h+var_36C], r13d
0x1801542cc  and     ecx, [rbp+2F0h+var_290]
0x1801542cf  mov     [rsp+3F0h+var_380], ecx
0x1801542d3  cmp     [r14+48h], r12b
0x1801542d7  jz      loc_1801545AB
0x1801542dd  mov     rax, [r14+40h]
0x1801542e1  jmp     loc_1801545AE
0x1801542e6  mov     rcx, [r14+40h]; unsigned __int16 *
0x1801542ea  lea     r9, [rbp+2F0h+var_340]
0x1801542ee  lea     r8, [rbp+2F0h+var_36C]
0x1801542f2  lea     rdx, [rbp+2F0h+var_360]
0x1801542f6  call    WspUnpackObjectId
0x1801542fb  mov     ebx, eax
0x1801542fd  test    eax, eax
0x1801542ff  jz      short loc_180154357
0x180154301  mov     eax, cs:dword_18039EB68
0x180154307  cmp     eax, 2
0x18015430a  jbe     loc_18015425A
0x180154310  mov     [rsp+3F0h+var_380], 8F0h
0x180154318  lea     rdx, byte_18035A1FF
0x18015431f  lea     rax, [rsp+3F0h+var_37C]
0x180154324  mov     qword ptr [rsp+3F0h+var_3C0], rax
0x180154329  lea     rdi, aWspDiskInvokeC_2; "WSP_Disk_Invoke_CreateVolume"
0x180154330  lea     rax, [rsp+3F0h+var_380]
0x180154335  mov     [rsp+3F0h+var_378], rdi
0x18015433a  mov     qword ptr [rsp+3F0h+var_3C8], rax
0x18015433f  lea     rax, [rsp+3F0h+var_378]
0x180154344  mov     [rsp+3F0h+var_3D0], rax
0x180154349  mov     [rsp+3F0h+var_37C], ebx
0x18015434d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180154352  jmp     loc_180154261
0x180154357  lea     r8, [rbp+2F0h+instance]; instance
0x18015435b  mov     rcx, rsi; context
0x18015435e  lea     rdx, WSP_Disk_CreateVolume_rtti; methodDecl
0x180154365  call    MI_Context_ConstructParameters
0x18015436a  mov     ebx, eax
0x18015436c  test    eax, eax
0x18015436e  jz      short loc_180154390
0x180154370  mov     eax, cs:dword_18039EB68
0x180154376  cmp     eax, 2
0x180154379  jbe     loc_18015425A
0x18015437f  mov     [rsp+3F0h+var_380], 8F8h
0x180154387  lea     rdx, byte_180358D3F
0x18015438e  jmp     short loc_18015431F
0x180154390  mov     ebx, dword ptr [rbp+2F0h+var_360]
0x180154393  lea     r9, [rbp+2F0h+Block]
0x180154397  mov     r8d, ebx
0x18015439a  mov     rdx, rdi
0x18015439d  mov     rcx, rsi
0x1801543a0  call    ?WspParseCreateVolumeParameters@@YA?AW4SM_RETURN_CODE@@PEAU_MI_Context@@PEBU_WSP_Disk_CreateVolume@@W4WSP_SUBSYSTEM_TYPE@@PEAPEAU_PM_CREATE_VOLUME_PARAMETERS@@@Z; WspParseCreateVolumeParameters(_MI_Context *,_WSP_Disk_CreateVolume const *,WSP_SUBSYSTEM_TYPE,_PM_CREATE_VOLUME_PARAMETERS * *)
0x1801543a5  mov     dword ptr [rbp+2F0h+var_360], eax
0x1801543a8  mov     edi, eax
0x1801543aa  test    eax, eax
0x1801543ac  jnz     loc_18015446B
0x1801543b2  lea     rax, [rbp+2F0h+var_360]
0x1801543b6  mov     rcx, rsi; struct _MI_Context *
0x1801543b9  mov     [rsp+3F0h+var_3A8], rax; __int64
0x1801543be  lea     r9, ?WSP_Disk_Invoke_CreateVolume_Async@@YAXPEAX0@Z; WSP_Disk_Invoke_CreateVolume_Async(void *,void *)
0x1801543c5  lea     rax, [rbp+2F0h+instance]
0x1801543c9  mov     [rsp+3F0h+var_3B0], rax; struct _MI_Instance *
0x1801543ce  lea     r8d, [rdi+4]
0x1801543d2  mov     rax, [r14+40h]
0x1801543d6  lea     rdx, aCreateVolume; "Create Volume"
0x1801543dd  mov     [rsp+3F0h+var_3B8], rax; __int64
0x1801543e2  mov     eax, [rbp+2F0h+var_36C]
0x1801543e5  mov     [rsp+3F0h+var_3C0], eax; int
0x1801543e9  mov     rax, [rbp+2F0h+Block]
0x1801543ed  mov     [rsp+3F0h+var_3C8], ebx; int
0x1801543f1  mov     [rsp+3F0h+var_3D0], rax; __int64
0x1801543f6  call    WspRunMethodAsJob
0x1801543fb  mov     ebx, eax
0x1801543fd  test    eax, eax
0x1801543ff  jz      short loc_180154424
0x180154401  mov     eax, cs:dword_18039EB68
0x180154407  cmp     eax, 2
0x18015440a  jbe     loc_18015425A
0x180154410  mov     [rsp+3F0h+var_380], 910h
0x180154418  lea     rdx, unk_18035A390
0x18015441f  jmp     loc_18015431F
0x180154424  mov     edi, dword ptr [rbp+2F0h+var_360]
0x180154427  mov     [rbp+2F0h+Block], r12
0x18015442b  lea     rdx, [rbp+2F0h+instance]
0x18015442f  mov     [rbp+2F0h+var_290], edi
0x180154432  mov     rcx, rsi; self
0x180154435  mov     [rbp+2F0h+var_28C], 1
0x180154439  call    MI_Instance_Destruct
0x18015443e  mov     ebx, eax
0x180154440  test    eax, eax
0x180154442  jz      loc_18015425A
0x180154448  mov     eax, cs:dword_18039EB68
0x18015444e  cmp     eax, 2
0x180154451  jbe     loc_18015425A
0x180154457  mov     [rsp+3F0h+var_380], 93Bh
0x18015445f  lea     rdx, byte_180358B29
0x180154466  jmp     loc_18015431F
0x18015446b  cmp     eax, 0A7F9h
0x180154470  jnz     short loc_18015442B
0x180154472  lea     rcx, [rbp+2F0h+var_C0]; this
0x180154479  call    ??0CSpExtendedStatus@@QEAA@XZ; CSpExtendedStatus::CSpExtendedStatus(void)
0x18015447e  xor     r8d, r8d; unsigned int
0x180154481  lea     rcx, [rbp+2F0h+var_C0]; this
0x180154488  mov     edx, 8011h; unsigned int
0x18015448d  call    ?Initialize@CSpExtendedStatus@@QEAAHKIZZ; CSpExtendedStatus::Initialize(ulong,uint,...)
0x180154492  test    rsi, rsi
0x180154495  jz      loc_18015453F
0x18015449b  mov     rax, [rsi]
0x18015449e  test    rax, rax
0x1801544a1  jz      loc_18015453F
0x1801544a7  mov     rax, [rax+18h]
0x1801544ab  lea     r8, [rbp+2F0h+self]
0x1801544b2  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1801544b9  mov     rcx, rsi
0x1801544bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801544c1  mov     ebx, eax
0x1801544c3  test    eax, eax
  ... truncated ...
```
