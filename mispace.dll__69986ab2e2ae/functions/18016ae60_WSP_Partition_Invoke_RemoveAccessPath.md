# WSP_Partition_Invoke_RemoveAccessPath

- ea: `0x18016ae60`
- end: `0x18016b59f`
- name: `WSP_Partition_Invoke_RemoveAccessPath`
- size: `1855`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001994`
- `0x180004608`
- `0x180004c3c`
- `0x180006350`
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
- `0x180017020`
- `0x18001b4a0`
- `0x180023e18`
- `0x180081c44`
- `0x18012bc58`
- `0x18012d98c`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18016ae60`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016aee1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016af4d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016b568`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016aee1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016af4d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016b568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18016b458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18016b458`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016af0b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016af0b`

## string_xrefs

- `0x18016af5f`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x18016b02c`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x18016b130`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x18016b21f`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x18016b033`: `RemoveAccessPath`
- `0x18016b3bf`: `RemoveAccessPath`
- `0x18016b440`: `RemoveAccessPath`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_RemoveAccessPath(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        _QWORD *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r13d
  int v12; // r8d
  int v13; // r9d
  struct _SUEX_EXTENDEDSTATUS_OBJECT *v14; // r15
  const struct _MI_ConstStringField *v15; // rsi
  enum _MI_Result v16; // ebx
  unsigned __int16 *v17; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r12d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  const char *v25; // rax
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  char *v29; // rdx
  __int64 v30; // rdx
  MI_Uint32 v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  unsigned __int32 v36; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v37[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h] BYREF
  int v39; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v40; // [rsp+88h] [rbp-78h] BYREF
  struct _SUEX_EXTENDEDSTATUS_OBJECT *v41; // [rsp+90h] [rbp-70h] BYREF
  const char *v42; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v43; // [rsp+A0h] [rbp-60h] BYREF
  const char *v44; // [rsp+A8h] [rbp-58h] BYREF
  const char *v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v49; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v50; // [rsp+D8h] [rbp-28h]
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  struct _MI_ConstUint32Field v53; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance self; // [rsp+180h] [rbp+80h] BYREF
  GUID ActivityId; // [rsp+290h] [rbp+190h] BYREF
  __int128 v56; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v57; // [rsp+2B0h] [rbp+1B0h]
  GUID v58; // [rsp+2B8h] [rbp+1B8h]
  GUID v59; // [rsp+2C8h] [rbp+1C8h] BYREF

  v47 = a5;
  v43 = a4;
  memset(&value, 0, sizeof(value));
  v44 = (const char *)a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v58 = ActivityId;
  v59 = ActivityId;
  EventActivityIdControl(4u, &v59);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v40 = 1059;
    v41 = (struct _SUEX_EXTENDEDSTATUS_OBJECT *)"WSP_Partition_Invoke_RemoveAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Partition_Invoke_RemoveAccessPath",
      (unsigned int)byte_1803621C9,
      v12,
      v13,
      (__int64)&v41,
      (__int64)&v40);
  }
  v46 = 0;
  v39 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  CSmTimer::CSmTimer((CSmTimer *)&v48);
  v41 = 0;
  self.ft = 0;
  v14 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v48);
  v15 = (const struct _MI_ConstStringField *)(a6 + 64);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( *(_BYTE *)(a6 + 72) && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v15->value) )
    v11 = 1;
  v40 = 0;
  v16 = (unsigned int)WspProviderEnter(a2);
  if ( v16 == MI_RESULT_OK )
  {
    if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v15->value) )
    {
      v16 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v15->value, v47, a7);
      goto LABEL_49;
    }
    v17 = (unsigned __int16 *)v15->value;
    v57 = 0;
    v56 = 0;
    LODWORD(v42) = 0;
    SubsystemType = WspGetSubsystemType(v17);
    SubsystemVersion = _GetSubsystemVersion(&v42);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v56);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v36 = SubsystemType;
      *(_DWORD *)v37 = SubsystemVersion != (_DWORD)v42;
      LOWORD(v42) = v57;
      *(_QWORD *)&v37[4] = &v56;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)word_1803622A2,
        v21,
        v22,
        (__int64)&v37[4],
        (__int64)&v36,
        (__int64)&v42,
        (__int64)v37);
    }
    if ( !a7 )
    {
      v16 = MI_RESULT_INVALID_PARAMETER;
      goto LABEL_16;
    }
    v16 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v15->value, &v39, &v36, &v46);
    if ( v16 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_16;
      *(_DWORD *)v37 = 1096;
      v29 = (char *)&word_180360C8E;
      goto LABEL_23;
    }
    v16 = MI_Context_ConstructParameters(a2, &WSP_Partition_RemoveAccessPath_rtti, &instance);
    if ( v16 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        *(_DWORD *)v37 = 1104;
        v29 = &byte_1803621F7;
LABEL_23:
        *(_QWORD *)&v37[4] = "WSP_Partition_Invoke_RemoveAccessPath";
        v36 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v26,
          (_DWORD)v29,
          v27,
          v28,
          (__int64)&v37[4],
          (__int64)v37,
          (__int64)&v36);
        goto LABEL_16;
      }
      goto LABEL_16;
    }
    v30 = a7[9];
    if ( v39 )
      v31 = PmcRemoveAccessPath(v46, v30, &v41);
    else
      v31 = PmRemoveAccessPath(v46, v30, &v41);
    v14 = v41;
    v53.value = v31;
    v53.exists = 1;
    if ( v41 )
    {
      if ( a2 && a2->ft )
      {
        v16 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
                a2,
                &MSFT_StorageExtendedStatus_rtti,
                &self);
        if ( v16 == MI_RESULT_OK )
        {
          if ( (unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(
                               v14,
                               (struct _MSFT_StorageExtendedStatus *)&self) )
          {
            *(_QWORD *)&v37[4] = &self;
            v16 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _DWORD))instance.ft->SetElementAt)(
                    &instance,
                    (unsigned int)(v16 + 2),
                    &v37[4],
                    (unsigned int)(v16 + 15),
                    0);
            if ( v16 )
            {
              if ( (unsigned int)dword_18039EB68 > 2 )
              {
                *(_DWORD *)v37 = 1145;
                v29 = &byte_1803611F7;
                goto LABEL_23;
              }
LABEL_16:
              CSmTimer::Stop((CSmTimer *)&v48);
              SmLogOnMethodFailure(v43, v47, v15, &v53, v16, 0);
              if ( (unsigned int)dword_18039EB68 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
              {
                v43 = 0;
                *(_DWORD *)&v37[8] = 0;
                v41 = (struct _SUEX_EXTENDEDSTATUS_OBJECT *)(1000 * (v49 - v48) / v50);
                v47 = 0;
                v36 = v16;
                *(_QWORD *)v37 = v53.exists != 0 ? v53.value : 0;
                v39 = v11;
                if ( v44[72] )
                  v25 = (const char *)v15->value;
                else
                  v25 = 0;
                v44 = v25;
                v42 = "RemoveAccessPath";
                v45 = "WspPartition";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  v53.exists != 0 ? v53.value : 0,
                  (unsigned int)word_18036060A,
                  v23,
                  v24,
                  (__int64)&v45,
                  (__int64)&v42,
                  (__int64)&v44,
                  (__int64)&v39,
                  (__int64)v37,
                  (__int64)&v36,
                  (__int64)&v41,
                  (__int64)&v47,
                  (__int64)&v37[4],
                  (__int64)&v43);
              }
              WspFreeString(v46);
              if ( v14 )
                LocalFree(v14);
              MI_Instance_Destruct(&self);
              MI_Instance_Destruct(&instance);
              goto LABEL_49;
            }
          }
          goto LABEL_41;
        }
      }
      else
      {
        v16 = MI_RESULT_INVALID_PARAMETER;
      }
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        *(_DWORD *)v37 = 1135;
        v29 = byte_180362269;
        goto LABEL_23;
      }
      goto LABEL_16;
    }
LABEL_41:
    v16 = MI_Instance_Destruct((MI_Instance *)a2);
    if ( v16 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_16;
    *(_DWORD *)v37 = 1155;
    v29 = byte_180360B91;
    goto LABEL_23;
  }
LABEL_49:
  MI_Context_PostResult_0(a2, v16);
  WspProviderExit(v40);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v48);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v11;
        v44 = "RemoveAccessPath";
        v45 = (const char *)(1000 * (v49 - v48) / v50);
        v43 = (unsigned __int16 *)"WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v32,
          (unsigned int)word_1803615A2,
          v33,
          v34,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&IsRemoteRequest,
          (__int64)&v45);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 1206;
    v45 = "WSP_Partition_Invoke_RemoveAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)byte_180361191,
      v33,
      v34,
      (__int64)&v45,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v48);
  return EventActivityIdControl(4u, &v59);
}

```

## disassembly

```asm
0x18016ae60  mov     [rsp-8+arg_0], rbx
0x18016ae65  push    rbp
0x18016ae66  push    rsi
0x18016ae67  push    rdi
0x18016ae68  push    r12
0x18016ae6a  push    r13
0x18016ae6c  push    r14
0x18016ae6e  push    r15
0x18016ae70  lea     rbp, [rsp-1E0h]
0x18016ae78  sub     rsp, 2E0h
0x18016ae7f  mov     rax, cs:__security_cookie
0x18016ae86  xor     rax, rsp
0x18016ae89  mov     [rbp+210h+var_38], rax
0x18016ae90  mov     rax, [rbp+210h+arg_20]
0x18016ae97  xorps   xmm0, xmm0
0x18016ae9a  mov     rbx, [rbp+210h+arg_28]
0x18016aea1  mov     rdi, rdx
0x18016aea4  mov     r14, [rbp+210h+arg_30]
0x18016aeab  lea     rdx, [rbp+210h+ActivityId]; ActivityId
0x18016aeb2  mov     [rbp+210h+var_250], rax
0x18016aeb6  mov     r12, r9
0x18016aeb9  xor     eax, eax
0x18016aebb  mov     [rbp+210h+var_270], r9
0x18016aebf  movups  xmmword ptr [rbp+210h+value], xmm0
0x18016aec3  mov     [rbp+210h+var_268], rbx
0x18016aec7  movups  xmmword ptr [rbp+210h+value+10h], xmm0
0x18016aecb  lea     ecx, [rax+1]; ControlCode
0x18016aece  mov     qword ptr [rbp+210h+value+20h], rax
0x18016aed2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016aed9  movdqu  xmmword ptr [rbp+210h+ActivityId.Data1], xmm0
0x18016aee1  call    cs:__imp_EventActivityIdControl
0x18016aee8  nop     dword ptr [rax+rax+00h]
0x18016aeed  lea     r9, [rbp+210h+value]; value
0x18016aef1  mov     rcx, rdi; context
0x18016aef4  call    MI_Context_GetCustomOption_1
0x18016aef9  xor     r13d, r13d
0x18016aefc  test    eax, eax
0x18016aefe  jnz     short loc_18016AF17
0x18016af00  mov     rcx, qword ptr [rbp+210h+value]; lpsz
0x18016af04  lea     rdx, [rbp+210h+ActivityId]; pclsid
0x18016af0b  call    cs:__imp_CLSIDFromString
0x18016af12  nop     dword ptr [rax+rax+00h]
0x18016af17  mov     rcx, qword ptr [rbp+210h+ActivityId.Data1]
0x18016af1e  lea     rdx, [rbp+210h+var_48]; ActivityId
0x18016af25  mov     rax, qword ptr [rbp+210h+ActivityId.Data4]
0x18016af2c  mov     [rbp+210h+var_58], rcx
0x18016af33  mov     qword ptr [rbp+210h+var_48.Data1], rcx
0x18016af3a  mov     ecx, 4; ControlCode
0x18016af3f  mov     [rbp+210h+var_50], rax
0x18016af46  mov     qword ptr [rbp+210h+var_48.Data4], rax
0x18016af4d  call    cs:__imp_EventActivityIdControl
0x18016af54  nop     dword ptr [rax+rax+00h]
0x18016af59  mov     eax, cs:dword_18039EB68
0x18016af5f  lea     rcx, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x18016af66  cmp     eax, 5
0x18016af69  jbe     short loc_18016AF94
0x18016af6b  lea     rax, [rbp+210h+var_288]
0x18016af6f  mov     [rbp+210h+var_288], 423h
0x18016af76  mov     [rsp+310h+var_2E8], rax
0x18016af7b  lea     rdx, byte_1803621C9
0x18016af82  lea     rax, [rbp+210h+var_280]
0x18016af86  mov     [rbp+210h+var_280], rcx
0x18016af8a  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016af8f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016af94  xor     edx, edx; Val
0x18016af96  mov     [rbp+210h+var_258], r13
0x18016af9a  lea     rcx, [rbp+210h+instance.classDecl]; void *
0x18016af9e  mov     [rbp+210h+var_28C], r13d
0x18016afa2  mov     [rbp+210h+instance.ft], r13
0x18016afa6  lea     r8d, [rdx+60h]; Size
0x18016afaa  call    memset_0
0x18016afaf  lea     rcx, [rbp+210h+var_248]; this
0x18016afb3  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016afb8  xor     edx, edx; Val
0x18016afba  mov     [rbp+210h+var_280], r13
0x18016afbe  mov     r8d, 108h; Size
0x18016afc4  mov     [rbp+210h+self.ft], r13
0x18016afcb  lea     rcx, [rbp+210h+self.classDecl]; void *
0x18016afd2  mov     r15, r13
0x18016afd5  call    memset_0
0x18016afda  lea     rcx, [rbp+210h+var_248]; this
0x18016afde  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016afe3  mov     rcx, rdi; context
0x18016afe6  call    WspIsRemoteRequest
0x18016afeb  lea     rsi, [rbx+40h]
0x18016afef  mov     [rbp+210h+var_290], eax
0x18016aff2  cmp     [rsi+8], r13b
0x18016aff6  jz      short loc_18016B00A
0x18016aff8  mov     rcx, [rsi]; unsigned __int16 *
0x18016affb  call    WspIsRemoteInstance
0x18016b000  test    al, al
0x18016b002  jz      short loc_18016B00A
0x18016b004  mov     r13d, 1
0x18016b00a  mov     rdx, [rsi]
0x18016b00d  lea     r9, [rbp+210h+var_288]
0x18016b011  mov     r8d, 1
0x18016b017  mov     [rbp+210h+var_288], r15d
0x18016b01b  mov     rcx, rdi; context
0x18016b01e  call    WspProviderEnter
0x18016b023  mov     ebx, eax
0x18016b025  test    eax, eax
0x18016b027  jz      short loc_18016B03F
0x18016b029  xor     r12d, r12d
0x18016b02c  lea     r14, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x18016b033  lea     rsi, aRemoveaccesspa; "RemoveAccessPath"
0x18016b03a  jmp     loc_18016B479
0x18016b03f  mov     rcx, [rsi]; unsigned __int16 *
0x18016b042  call    WspIsRemoteInstance
0x18016b047  test    al, al
0x18016b049  jz      short loc_18016B066
0x18016b04b  mov     r9, [rbp+210h+var_250]; unsigned __int16 *
0x18016b04f  mov     rdx, r12; unsigned __int16 *
0x18016b052  mov     r8, [rsi]; unsigned __int16 *
0x18016b055  mov     rcx, rdi; struct _MI_Context *
0x18016b058  mov     qword ptr [rsp+310h+var_2F0], r14; void *
0x18016b05d  call    WspInvokeRemoteMethod
0x18016b062  mov     ebx, eax
0x18016b064  jmp     short loc_18016B029
0x18016b066  mov     rcx, [rsi]
0x18016b069  xor     eax, eax
0x18016b06b  xorps   xmm0, xmm0
0x18016b06e  mov     [rbp+210h+var_60], eax
0x18016b074  movups  [rbp+210h+var_70], xmm0
0x18016b07b  mov     dword ptr [rbp+210h+var_278], eax
0x18016b07e  call    WspGetSubsystemType
0x18016b083  lea     rcx, [rbp+210h+var_278]
0x18016b087  mov     ebx, eax
0x18016b089  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18016b08e  lea     rdx, [rbp+210h+var_70]; struct _SUBSYSTEM_INFO *
0x18016b095  mov     ecx, ebx; unsigned int
0x18016b097  mov     r12d, eax
0x18016b09a  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18016b09f  mov     ecx, cs:dword_18039EB68
0x18016b0a5  cmp     ecx, 5
0x18016b0a8  jbe     short loc_18016B11F
0x18016b0aa  mov     rdx, 400000000000h
0x18016b0b4  lea     rcx, dword_18039EB68
0x18016b0bb  call    _tlgKeywordOn
0x18016b0c0  test    al, al
0x18016b0c2  jz      short loc_18016B11F
0x18016b0c4  xor     eax, eax
0x18016b0c6  mov     [rsp+310h+var_2A0], ebx
0x18016b0ca  cmp     r12d, dword ptr [rbp+210h+var_278]
0x18016b0ce  lea     rdx, word_1803622A2
0x18016b0d5  setnz   al
0x18016b0d8  mov     [rsp+310h+var_29C], eax
0x18016b0dc  movzx   eax, word ptr [rbp+210h+var_60]
0x18016b0e3  mov     word ptr [rbp+210h+var_278], ax
0x18016b0e7  lea     rax, [rbp+210h+var_70]
0x18016b0ee  mov     [rsp+310h+var_298], rax
0x18016b0f3  lea     rax, [rsp+310h+var_29C]
0x18016b0f8  mov     [rsp+310h+var_2D8], rax
0x18016b0fd  lea     rax, [rbp+210h+var_278]
0x18016b101  mov     [rsp+310h+var_2E0], rax
0x18016b106  lea     rax, [rsp+310h+var_2A0]
0x18016b10b  mov     [rsp+310h+var_2E8], rax
0x18016b110  lea     rax, [rsp+310h+var_298]
0x18016b115  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016b11a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18016b11f  xor     r12d, r12d
0x18016b122  test    r14, r14
0x18016b125  jnz     loc_18016B1DC
0x18016b12b  lea     ebx, [r12+4]
0x18016b130  lea     r14, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x18016b137  lea     rcx, [rbp+210h+var_248]; this
0x18016b13b  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18016b140  mov     rdx, [rbp+210h+var_250]; unsigned __int16 *
0x18016b144  lea     r9, [rbp+210h+var_1C0]; struct _MI_ConstUint32Field *
0x18016b148  mov     rcx, [rbp+210h+var_270]; unsigned __int16 *
0x18016b14c  mov     r8, rsi; struct _MI_ConstStringField *
0x18016b14f  mov     [rsp+310h+var_2E8], r12; unsigned __int16 *
0x18016b154  mov     [rsp+310h+var_2F0], ebx; enum _MI_Result
0x18016b158  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18016b15d  mov     eax, cs:dword_18039EB68
0x18016b163  cmp     eax, 5
0x18016b166  jbe     loc_18016B440
0x18016b16c  mov     rdx, 400000000000h
0x18016b176  lea     rcx, dword_18039EB68
0x18016b17d  call    _tlgKeywordOn
0x18016b182  test    al, al
0x18016b184  jz      loc_18016B440
0x18016b18a  mov     rax, [rbp+210h+var_240]
0x18016b18e  xor     edx, edx
0x18016b190  sub     rax, [rbp+210h+var_248]
0x18016b194  imul    rax, 3E8h
0x18016b19b  mov     [rbp+210h+var_270], r12
0x18016b19f  div     [rbp+210h+var_238]
0x18016b1a3  mov     [rsp+310h+var_298], r12
0x18016b1a8  mov     [rbp+210h+var_280], rax
0x18016b1ac  mov     al, [rbp+210h+var_1C0.exists]
0x18016b1af  neg     al
0x18016b1b1  mov     [rbp+210h+var_250], r12
0x18016b1b5  mov     rax, [rbp+210h+var_268]
0x18016b1b9  sbb     ecx, ecx
0x18016b1bb  mov     [rsp+310h+var_2A0], ebx
0x18016b1bf  and     ecx, [rbp+210h+var_1C0.value]
0x18016b1c2  mov     [rsp+310h+var_29C], ecx
0x18016b1c6  mov     [rbp+210h+var_28C], r13d
0x18016b1ca  cmp     [rax+48h], r12b
0x18016b1ce  jz      loc_18016B3B8
0x18016b1d4  mov     rax, [rsi]
0x18016b1d7  jmp     loc_18016B3BB
0x18016b1dc  mov     rcx, [rsi]; unsigned __int16 *
0x18016b1df  lea     r9, [rbp+210h+var_258]
0x18016b1e3  lea     r8, [rsp+310h+var_2A0]
0x18016b1e8  lea     rdx, [rbp+210h+var_28C]
0x18016b1ec  call    WspUnpackObjectId
0x18016b1f1  mov     ebx, eax
0x18016b1f3  test    eax, eax
0x18016b1f5  jz      short loc_18016B24D
0x18016b1f7  mov     eax, cs:dword_18039EB68
0x18016b1fd  cmp     eax, 2
0x18016b200  jbe     loc_18016B130
0x18016b206  mov     [rsp+310h+var_29C], 448h
0x18016b20e  lea     rdx, word_180360C8E
0x18016b215  lea     rax, [rsp+310h+var_2A0]
0x18016b21a  mov     [rsp+310h+var_2E0], rax
0x18016b21f  lea     r14, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x18016b226  lea     rax, [rsp+310h+var_29C]
0x18016b22b  mov     [rsp+310h+var_298], r14
0x18016b230  mov     [rsp+310h+var_2E8], rax
0x18016b235  lea     rax, [rsp+310h+var_298]
0x18016b23a  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016b23f  mov     [rsp+310h+var_2A0], ebx
0x18016b243  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016b248  jmp     loc_18016B137
0x18016b24d  lea     r8, [rbp+210h+instance]; instance
0x18016b251  mov     rcx, rdi; context
0x18016b254  lea     rdx, WSP_Partition_RemoveAccessPath_rtti; methodDecl
0x18016b25b  call    MI_Context_ConstructParameters
0x18016b260  mov     ebx, eax
0x18016b262  test    eax, eax
0x18016b264  jz      short loc_18016B286
0x18016b266  mov     eax, cs:dword_18039EB68
0x18016b26c  cmp     eax, 2
0x18016b26f  jbe     loc_18016B130
0x18016b275  mov     [rsp+310h+var_29C], 450h
0x18016b27d  lea     rdx, byte_1803621F7
0x18016b284  jmp     short loc_18016B215
0x18016b286  lea     r8, [rbp+210h+var_280]
0x18016b28a  mov     rdx, [r14+48h]
0x18016b28e  mov     rcx, [rbp+210h+var_258]
0x18016b292  cmp     [rbp+210h+var_28C], r12d
0x18016b296  jnz     short loc_18016B29F
0x18016b298  call    ?PmRemoveAccessPath@@YA?AW4SM_RETURN_CODE@@PEBG0PEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; PmRemoveAccessPath(ushort const *,ushort const *,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x18016b29d  jmp     short loc_18016B2A4
0x18016b29f  call    ?PmcRemoveAccessPath@@YA?AW4SM_RETURN_CODE@@PEBG0PEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; PmcRemoveAccessPath(ushort const *,ushort const *,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x18016b2a4  mov     r15, [rbp+210h+var_280]
0x18016b2a8  mov     [rbp+210h+var_1C0.value], eax
0x18016b2ab  mov     [rbp+210h+var_1C0.exists], 1
0x18016b2af  test    r15, r15
0x18016b2b2  jz      loc_18016B37F
0x18016b2b8  test    rdi, rdi
0x18016b2bb  jz      loc_18016B357
0x18016b2c1  mov     rax, [rdi]
0x18016b2c4  test    rax, rax
0x18016b2c7  jz      loc_18016B357
0x18016b2cd  mov     rax, [rax+18h]
0x18016b2d1  lea     r8, [rbp+210h+self]
0x18016b2d8  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18016b2df  mov     rcx, rdi
0x18016b2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b2e7  mov     ebx, eax
0x18016b2e9  test    eax, eax
0x18016b2eb  jnz     short loc_18016B35C
0x18016b2ed  lea     rdx, [rbp+210h+self]; struct _MSFT_StorageExtendedStatus *
0x18016b2f4  mov     rcx, r15; struct _SUEX_EXTENDEDSTATUS_OBJECT *
0x18016b2f7  call    ?SuexToMsftExtendedStatus@CSpExtendedStatus@@SAHPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAU_MSFT_StorageExtendedStatus@@@Z; CSpExtendedStatus::SuexToMsftExtendedStatus(_SUEX_EXTENDEDSTATUS_OBJECT *,_MSFT_StorageExtendedStatus *)
0x18016b2fc  test    eax, eax
0x18016b2fe  jz      short loc_18016B37F
0x18016b300  lea     rax, [rbp+210h+self]
0x18016b307  mov     [rsp+310h+var_2F0], r12d
0x18016b30c  mov     [rsp+310h+var_298], rax
0x18016b311  lea     r9d, [rbx+0Fh]
0x18016b315  mov     rax, [rbp+210h+instance.ft]
0x18016b319  lea     r8, [rsp+310h+var_298]
0x18016b31e  lea     edx, [rbx+2]
0x18016b321  lea     rcx, [rbp+210h+instance]
0x18016b325  mov     rax, [rax+50h]
0x18016b329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b32e  mov     ebx, eax
0x18016b330  test    eax, eax
0x18016b332  jz      short loc_18016B37F
0x18016b334  mov     eax, cs:dword_18039EB68
0x18016b33a  cmp     eax, 2
0x18016b33d  jbe     loc_18016B130
0x18016b343  mov     [rsp+310h+var_29C], 479h
0x18016b34b  lea     rdx, byte_1803611F7
0x18016b352  jmp     loc_18016B215
0x18016b357  mov     ebx, 4
0x18016b35c  mov     eax, cs:dword_18039EB68
0x18016b362  cmp     eax, 2
0x18016b365  jbe     loc_18016B130
0x18016b36b  mov     [rsp+310h+var_29C], 46Fh
0x18016b373  lea     rdx, byte_180362269
0x18016b37a  jmp     loc_18016B215
0x18016b37f  lea     rdx, [rbp+210h+instance]
0x18016b383  mov     rcx, rdi; self
0x18016b386  call    MI_Instance_Destruct
0x18016b38b  mov     ebx, eax
  ... truncated ...
```
