# WSP_Partition_Invoke_RemoveAccessPath

- ea: `0x180166c90`
- end: `0x1801673f9`
- name: `WSP_Partition_Invoke_RemoveAccessPath`
- size: `1897`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001970`
- `0x1800045d0`
- `0x180004bfc`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180014000`
- `0x180014720`
- `0x180015500`
- `0x1800156c0`
- `0x1800158d0`
- `0x180015b40`
- `0x180015c60`
- `0x180016480`
- `0x1800165f0`
- `0x180016c80`
- `0x18001afd0`
- `0x1800234e4`
- `0x18007f590`
- `0x180127e50`
- `0x180129bdc`
- `0x180137a24`
- `0x180138120`
- `0x180166c90`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180166d0d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180166d6d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180166f53`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180166d0d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180166d6d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180166f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801673b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801673b7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180166d31`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180166d31`

## string_xrefs

- `0x180166d79`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x180166e67`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x180167079`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x18016716e`: `WSP_Partition_Invoke_RemoveAccessPath`
- `0x180166e60`: `RemoveAccessPath`
- `0x18016731e`: `RemoveAccessPath`
- `0x18016739f`: `RemoveAccessPath`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_RemoveAccessPath(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        _QWORD *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r13d
  __int64 v12; // r8
  __int64 v13; // r9
  struct _SUEX_EXTENDEDSTATUS_OBJECT *v14; // r15
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  const MI_Char *v22; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r12d
  __int64 v25; // rcx
  enum _MI_Result v26; // ebx
  __int64 v27; // r8
  __int64 v28; // r9
  const char *v29; // rax
  enum _MI_Result v30; // eax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  char *v34; // rdx
  unsigned __int16 *v35; // rdx
  MI_Uint32 v36; // eax
  _BYTE *v37; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v38; // [rsp+28h] [rbp-D8h]
  const char **v39; // [rsp+30h] [rbp-D0h]
  _BYTE *v40; // [rsp+38h] [rbp-C8h]
  unsigned __int32 v41; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v42[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h]
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v45; // [rsp+88h] [rbp-78h] BYREF
  struct _SUEX_EXTENDEDSTATUS_OBJECT *v46; // [rsp+90h] [rbp-70h] BYREF
  const char *v47; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v48; // [rsp+A0h] [rbp-60h] BYREF
  const char *v49; // [rsp+A8h] [rbp-58h] BYREF
  const char *v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v52; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v55; // [rsp+D8h] [rbp-28h]
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  struct _MI_ConstUint32Field v58; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance self; // [rsp+180h] [rbp+80h] BYREF
  GUID ActivityId; // [rsp+290h] [rbp+190h] BYREF
  __int128 v61; // [rsp+2A0h] [rbp+1A0h] BYREF
  int v62; // [rsp+2B0h] [rbp+1B0h]
  GUID v63; // [rsp+2B8h] [rbp+1B8h]
  GUID v64; // [rsp+2C8h] [rbp+1C8h] BYREF

  memset(&value, 0, sizeof(value));
  v48 = a4;
  v52 = a5;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v63 = ActivityId;
  v64 = ActivityId;
  EventActivityIdControl(4u, &v64);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v45 = 1059;
    v38 = (unsigned __int16 *)&v45;
    v46 = (struct _SUEX_EXTENDEDSTATUS_OBJECT *)"WSP_Partition_Invoke_RemoveAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"WSP_Partition_Invoke_RemoveAccessPath",
      (__int64)word_18035B27A,
      v12,
      v13,
      &v46);
  }
  v51 = 0;
  v44 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  CSmTimer::CSmTimer((CSmTimer *)&v53);
  v46 = 0;
  self.ft = 0;
  v14 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v53);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
    v11 = 1;
  v15 = (__int64)a6[4].value;
  v45 = 0;
  v16 = WspProviderEnter(a2, v15, 1u, &v45);
  v17 = v16;
  if ( v16 )
    goto LABEL_9;
  if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
  {
    v17 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)a6[4].value, a5, a7);
LABEL_9:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(MI_Context *, __int64))a2->ft->PostResult)(a2, v17);
    goto LABEL_12;
  }
  v22 = a6[4].value;
  v62 = 0;
  v61 = 0;
  LODWORD(v47) = 0;
  SubsystemType = WspGetSubsystemType(v22);
  SubsystemVersion = _GetSubsystemVersion(&v47);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v61);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v41 = SubsystemType;
    *(_DWORD *)v42 = SubsystemVersion != (_DWORD)v47;
    LOWORD(v47) = v62;
    *(_QWORD *)&v42[4] = &v61;
    v40 = v42;
    v39 = &v47;
    v38 = (unsigned __int16 *)&v41;
    v37 = &v42[4];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v25,
      (__int64)&word_18035B436);
  }
  if ( !a7 )
  {
    v26 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_26;
  }
  v30 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)a6[4].value, &v44, &v41, &v51);
  v26 = v30;
  if ( v30 )
  {
    v33 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v41 = v30;
    v34 = (char *)&word_180359D06;
    *(_DWORD *)v42 = 1096;
    goto LABEL_33;
  }
  v26 = MI_Context_ConstructParameters(a2, &WSP_Partition_RemoveAccessPath_rtti, &instance);
  if ( v26 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v41 = v26;
      v34 = byte_18035B241;
      *(_DWORD *)v42 = 1104;
LABEL_33:
      *(_QWORD *)&v42[4] = "WSP_Partition_Invoke_RemoveAccessPath";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v33,
        (__int64)v34,
        v31,
        v32,
        &v42[4]);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  v35 = (unsigned __int16 *)a7[9];
  if ( v44 )
    v36 = PmcRemoveAccessPath(v51, v35, &v46, v32);
  else
    v36 = PmRemoveAccessPath(v51, v35, &v46);
  v14 = v46;
  v58.value = v36;
  v58.exists = 1;
  if ( !v46 )
  {
LABEL_51:
    v26 = MI_Instance_Destruct((MI_Instance *)a2);
    if ( v26 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v41 = v26;
    v34 = (char *)&unk_180359CA0;
    *(_DWORD *)v42 = 1155;
    goto LABEL_33;
  }
  if ( !a2 || !a2->ft )
  {
    v26 = MI_RESULT_INVALID_PARAMETER;
LABEL_49:
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v41 = v26;
      v34 = &byte_18035B30F;
      *(_DWORD *)v42 = 1135;
      goto LABEL_33;
    }
    goto LABEL_26;
  }
  v26 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
          a2,
          &MSFT_StorageExtendedStatus_rtti,
          &self);
  if ( v26 )
    goto LABEL_49;
  if ( !(unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(v14, (struct _MSFT_StorageExtendedStatus *)&self) )
    goto LABEL_51;
  LODWORD(v37) = 0;
  *(_QWORD *)&v42[4] = &self;
  v26 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _BYTE *, unsigned __int16 *, const char **, _BYTE *))instance.ft->SetElementAt)(
          &instance,
          (unsigned int)(v26 + 2),
          &v42[4],
          (unsigned int)(v26 + 15),
          v37,
          v38,
          v39,
          v40);
  if ( v26 == MI_RESULT_OK )
    goto LABEL_51;
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v41 = v26;
    v34 = &byte_18035A2FF;
    *(_DWORD *)v42 = 1145;
    goto LABEL_33;
  }
LABEL_26:
  CSmTimer::Stop((CSmTimer *)&v53);
  SmLogOnMethodFailure(v48, v52, a6 + 4, &v58, v26, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v48 = 0;
    v52 = 0;
    v46 = (struct _SUEX_EXTENDEDSTATUS_OBJECT *)(1000 * (v54 - v53) / v55);
    *(_DWORD *)&v42[8] = 0;
    v41 = v26;
    v44 = v11;
    *(_QWORD *)v42 = v58.exists != 0 ? v58.value : 0;
    if ( a6[4].exists )
      v29 = (const char *)a6[4].value;
    else
      v29 = 0;
    v49 = v29;
    v47 = "RemoveAccessPath";
    v50 = "WspPartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v58.exists != 0 ? v58.value : 0,
      (__int64)byte_180359649,
      v27,
      v28,
      &v50,
      &v47,
      &v49,
      (__int64)&v44,
      (__int64)v42,
      (__int64)&v41,
      (__int64)&v46,
      &v42[4],
      &v52,
      &v48);
  }
  WspFreeString(v51);
  if ( v14 )
    LocalFree(v14);
  MI_Instance_Destruct(&self);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v26);
LABEL_12:
  WspProviderExit(v45, v17);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v53);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v11;
        v49 = "RemoveAccessPath";
        v50 = (const char *)(1000 * (v54 - v53) / v55);
        v48 = (unsigned __int16 *)"WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v18,
          (__int64)byte_18035A58B,
          v19,
          v20,
          &v48,
          &v49);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 1206;
    v50 = "WSP_Partition_Invoke_RemoveAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v18,
      (__int64)byte_18035A209,
      v19,
      v20,
      &v50);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v53);
  return EventActivityIdControl(4u, &v64);
}

```

## disassembly

```asm
0x180166c90  mov     [rsp-8+arg_0], rbx
0x180166c95  push    rbp
0x180166c96  push    rsi
0x180166c97  push    rdi
0x180166c98  push    r12
0x180166c9a  push    r13
0x180166c9c  push    r14
0x180166c9e  push    r15
0x180166ca0  lea     rbp, [rsp-1E0h]
0x180166ca8  sub     rsp, 2E0h
0x180166caf  mov     rax, cs:__security_cookie
0x180166cb6  xor     rax, rsp
0x180166cb9  mov     [rbp+210h+var_38], rax
0x180166cc0  mov     r12, [rbp+210h+arg_20]
0x180166cc7  xorps   xmm0, xmm0
0x180166cca  mov     rsi, [rbp+210h+arg_28]
0x180166cd1  xor     eax, eax
0x180166cd3  mov     r14, [rbp+210h+arg_30]
0x180166cda  mov     rbx, r9
0x180166cdd  movups  xmmword ptr [rbp+210h+value], xmm0
0x180166ce1  mov     rdi, rdx
0x180166ce4  lea     rdx, [rbp+210h+ActivityId]; ActivityId
0x180166ceb  movups  xmmword ptr [rbp+210h+value+10h], xmm0
0x180166cef  lea     ecx, [rax+1]; ControlCode
0x180166cf2  mov     [rbp+210h+var_270], rbx
0x180166cf6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180166cfd  mov     [rbp+210h+var_250], r12
0x180166d01  mov     qword ptr [rbp+210h+value+20h], rax
0x180166d05  movdqu  xmmword ptr [rbp+210h+ActivityId.Data1], xmm0
0x180166d0d  call    cs:__imp_EventActivityIdControl
0x180166d13  lea     r9, [rbp+210h+value]; value
0x180166d17  mov     rcx, rdi; context
0x180166d1a  call    MI_Context_GetCustomOption_1
0x180166d1f  xor     r13d, r13d
0x180166d22  test    eax, eax
0x180166d24  jnz     short loc_180166D37
0x180166d26  mov     rcx, qword ptr [rbp+210h+value]; lpsz
0x180166d2a  lea     rdx, [rbp+210h+ActivityId]; pclsid
0x180166d31  call    cs:__imp_CLSIDFromString
0x180166d37  mov     rcx, qword ptr [rbp+210h+ActivityId.Data1]
0x180166d3e  lea     rdx, [rbp+210h+var_48]; ActivityId
0x180166d45  mov     rax, qword ptr [rbp+210h+ActivityId.Data4]
0x180166d4c  mov     [rbp+210h+var_58], rcx
0x180166d53  mov     qword ptr [rbp+210h+var_48.Data1], rcx
0x180166d5a  mov     ecx, 4; ControlCode
0x180166d5f  mov     [rbp+210h+var_50], rax
0x180166d66  mov     qword ptr [rbp+210h+var_48.Data4], rax
0x180166d6d  call    cs:__imp_EventActivityIdControl
0x180166d73  mov     eax, cs:dword_180397B68
0x180166d79  lea     rcx, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x180166d80  cmp     eax, 5
0x180166d83  jbe     short loc_180166DAE
0x180166d85  lea     rax, [rbp+210h+var_288]
0x180166d89  mov     [rbp+210h+var_288], 423h
0x180166d90  mov     [rsp+310h+var_2E8], rax
0x180166d95  lea     rdx, word_18035B27A
0x180166d9c  lea     rax, [rbp+210h+var_280]
0x180166da0  mov     [rbp+210h+var_280], rcx
0x180166da4  mov     qword ptr [rsp+310h+var_2F0], rax
0x180166da9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180166dae  xor     edx, edx; Val
0x180166db0  mov     [rbp+210h+var_258], r13
0x180166db4  lea     rcx, [rbp+210h+instance.classDecl]; void *
0x180166db8  mov     [rbp+210h+var_28C], r13d
0x180166dbc  mov     [rbp+210h+instance.ft], r13
0x180166dc0  lea     r8d, [rdx+60h]; Size
0x180166dc4  call    memset_0
0x180166dc9  lea     rcx, [rbp+210h+var_248]; this
0x180166dcd  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180166dd2  xor     edx, edx; Val
0x180166dd4  mov     [rbp+210h+var_280], r13
0x180166dd8  mov     r8d, 108h; Size
0x180166dde  mov     [rbp+210h+self.ft], r13
0x180166de5  lea     rcx, [rbp+210h+self.classDecl]; void *
0x180166dec  mov     r15, r13
0x180166def  call    memset_0
0x180166df4  lea     rcx, [rbp+210h+var_248]; this
0x180166df8  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180166dfd  mov     rcx, rdi; context
0x180166e00  call    WspIsRemoteRequest
0x180166e05  mov     [rbp+210h+var_290], eax
0x180166e08  cmp     [rsi+48h], r13b
0x180166e0c  jz      short loc_180166E21
0x180166e0e  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180166e12  call    WspIsRemoteInstance
0x180166e17  test    al, al
0x180166e19  jz      short loc_180166E21
0x180166e1b  mov     r13d, 1
0x180166e21  mov     rdx, [rsi+40h]
0x180166e25  lea     r9, [rbp+210h+var_288]
0x180166e29  mov     r8d, 1
0x180166e2f  mov     [rbp+210h+var_288], r15d
0x180166e33  mov     rcx, rdi; context
0x180166e36  call    WspProviderEnter
0x180166e3b  mov     edx, eax
0x180166e3d  test    eax, eax
0x180166e3f  jz      loc_180166F83
0x180166e45  xor     r12d, r12d
0x180166e48  test    rdi, rdi
0x180166e4b  jz      short loc_180166E60
0x180166e4d  mov     rax, [rdi]
0x180166e50  test    rax, rax
0x180166e53  jz      short loc_180166E60
0x180166e55  mov     rax, [rax]
0x180166e58  mov     rcx, rdi
0x180166e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180166e60  lea     rsi, aRemoveaccesspa; "RemoveAccessPath"
0x180166e67  lea     r14, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x180166e6e  mov     ecx, [rbp+210h+var_288]
0x180166e71  call    WspProviderExit
0x180166e76  cmp     [rbp+210h+var_290], r12d
0x180166e7a  jz      loc_180166F0A
0x180166e80  lea     rcx, [rbp+210h+var_248]; this
0x180166e84  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180166e89  mov     eax, cs:dword_180397B68
0x180166e8f  cmp     eax, 5
0x180166e92  jbe     short loc_180166F0A
0x180166e94  mov     rdx, 400000000000h
0x180166e9e  lea     rcx, dword_180397B68
0x180166ea5  call    _tlgKeywordOn
0x180166eaa  test    al, al
0x180166eac  jz      short loc_180166F0A
0x180166eae  mov     rax, [rbp+210h+var_240]
0x180166eb2  xor     edx, edx
0x180166eb4  sub     rax, [rbp+210h+var_248]
0x180166eb8  imul    rax, 3E8h
0x180166ebf  mov     [rbp+210h+var_290], r13d
0x180166ec3  div     [rbp+210h+var_238]
0x180166ec7  lea     rdx, byte_18035A58B
0x180166ece  mov     [rbp+210h+var_268], rsi
0x180166ed2  mov     [rbp+210h+var_260], rax
0x180166ed6  lea     rax, aWsppartition; "WspPartition"
0x180166edd  mov     [rbp+210h+var_270], rax
0x180166ee1  lea     rax, [rbp+210h+var_260]
0x180166ee5  mov     [rsp+310h+var_2D8], rax
0x180166eea  lea     rax, [rbp+210h+var_290]
0x180166eee  mov     [rsp+310h+var_2E0], rax
0x180166ef3  lea     rax, [rbp+210h+var_268]
0x180166ef7  mov     [rsp+310h+var_2E8], rax
0x180166efc  lea     rax, [rbp+210h+var_270]
0x180166f00  mov     qword ptr [rsp+310h+var_2F0], rax
0x180166f05  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180166f0a  mov     eax, cs:dword_180397B68
0x180166f10  cmp     eax, 5
0x180166f13  jbe     short loc_180166F3E
0x180166f15  lea     rax, [rbp+210h+var_290]
0x180166f19  mov     [rbp+210h+var_290], 4B6h
0x180166f20  mov     [rsp+310h+var_2E8], rax
0x180166f25  lea     rdx, byte_18035A209
0x180166f2c  lea     rax, [rbp+210h+var_260]
0x180166f30  mov     [rbp+210h+var_260], r14
0x180166f34  mov     qword ptr [rsp+310h+var_2F0], rax
0x180166f39  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180166f3e  lea     rcx, [rbp+210h+var_248]; this
0x180166f42  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180166f47  lea     rdx, [rbp+210h+var_48]; ActivityId
0x180166f4e  mov     ecx, 4; ControlCode
0x180166f53  call    cs:__imp_EventActivityIdControl
0x180166f59  mov     rcx, [rbp+210h+var_38]
0x180166f60  xor     rcx, rsp; StackCookie
0x180166f63  call    __security_check_cookie
0x180166f68  mov     rbx, [rsp+310h+arg_0]
0x180166f70  add     rsp, 2E0h
0x180166f77  pop     r15
0x180166f79  pop     r14
0x180166f7b  pop     r13
0x180166f7d  pop     r12
0x180166f7f  pop     rdi
0x180166f80  pop     rsi
0x180166f81  pop     rbp
0x180166f82  retn
0x180166f83  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180166f87  call    WspIsRemoteInstance
0x180166f8c  test    al, al
0x180166f8e  jz      short loc_180166FAE
0x180166f90  mov     r8, [rsi+40h]; unsigned __int16 *
0x180166f94  mov     r9, r12; unsigned __int16 *
0x180166f97  mov     rdx, rbx; unsigned __int16 *
0x180166f9a  mov     qword ptr [rsp+310h+var_2F0], r14; void *
0x180166f9f  mov     rcx, rdi; struct _MI_Context *
0x180166fa2  call    WspInvokeRemoteMethod
0x180166fa7  mov     edx, eax
0x180166fa9  jmp     loc_180166E45
0x180166fae  mov     rcx, [rsi+40h]
0x180166fb2  xor     eax, eax
0x180166fb4  xorps   xmm0, xmm0
0x180166fb7  mov     [rbp+210h+var_60], eax
0x180166fbd  movups  [rbp+210h+var_70], xmm0
0x180166fc4  mov     dword ptr [rbp+210h+var_278], eax
0x180166fc7  call    WspGetSubsystemType
0x180166fcc  lea     rcx, [rbp+210h+var_278]
0x180166fd0  mov     ebx, eax
0x180166fd2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180166fd7  lea     rdx, [rbp+210h+var_70]; struct _SUBSYSTEM_INFO *
0x180166fde  mov     ecx, ebx; unsigned int
0x180166fe0  mov     r12d, eax
0x180166fe3  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180166fe8  mov     ecx, cs:dword_180397B68
0x180166fee  cmp     ecx, 5
0x180166ff1  jbe     short loc_180167068
0x180166ff3  mov     rdx, 400000000000h
0x180166ffd  lea     rcx, dword_180397B68
0x180167004  call    _tlgKeywordOn
0x180167009  test    al, al
0x18016700b  jz      short loc_180167068
0x18016700d  xor     eax, eax
0x18016700f  mov     [rsp+310h+var_2A0], ebx
0x180167013  cmp     r12d, dword ptr [rbp+210h+var_278]
0x180167017  lea     rdx, word_18035B436
0x18016701e  setnz   al
0x180167021  mov     [rsp+310h+var_29C], eax
0x180167025  movzx   eax, word ptr [rbp+210h+var_60]
0x18016702c  mov     word ptr [rbp+210h+var_278], ax
0x180167030  lea     rax, [rbp+210h+var_70]
0x180167037  mov     [rsp+310h+var_298], rax
0x18016703c  lea     rax, [rsp+310h+var_29C]
0x180167041  mov     [rsp+310h+var_2D8], rax
0x180167046  lea     rax, [rbp+210h+var_278]
0x18016704a  mov     [rsp+310h+var_2E0], rax
0x18016704f  lea     rax, [rsp+310h+var_2A0]
0x180167054  mov     [rsp+310h+var_2E8], rax
0x180167059  lea     rax, [rsp+310h+var_298]
0x18016705e  mov     qword ptr [rsp+310h+var_2F0], rax
0x180167063  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180167068  xor     r12d, r12d
0x18016706b  test    r14, r14
0x18016706e  jnz     loc_180167126
0x180167074  lea     ebx, [r12+4]
0x180167079  lea     r14, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x180167080  lea     rcx, [rbp+210h+var_248]; this
0x180167084  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180167089  mov     rdx, [rbp+210h+var_250]; unsigned __int16 *
0x18016708d  lea     r9, [rbp+210h+var_1C0]; struct _MI_ConstUint32Field *
0x180167091  mov     rcx, [rbp+210h+var_270]; unsigned __int16 *
0x180167095  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x180167099  mov     [rsp+310h+var_2E8], r12; unsigned __int16 *
0x18016709e  mov     [rsp+310h+var_2F0], ebx; enum _MI_Result
0x1801670a2  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801670a7  mov     eax, cs:dword_180397B68
0x1801670ad  cmp     eax, 5
0x1801670b0  jbe     loc_18016739F
0x1801670b6  mov     rdx, 400000000000h
0x1801670c0  lea     rcx, dword_180397B68
0x1801670c7  call    _tlgKeywordOn
0x1801670cc  test    al, al
0x1801670ce  jz      loc_18016739F
0x1801670d4  mov     rax, [rbp+210h+var_240]
0x1801670d8  xor     edx, edx
0x1801670da  sub     rax, [rbp+210h+var_248]
0x1801670de  imul    rax, 3E8h
0x1801670e5  mov     [rbp+210h+var_270], r12
0x1801670e9  div     [rbp+210h+var_238]
0x1801670ed  mov     [rbp+210h+var_250], r12
0x1801670f1  mov     [rbp+210h+var_280], rax
0x1801670f5  mov     al, [rbp+210h+var_1C0.exists]
0x1801670f8  neg     al
0x1801670fa  mov     [rsp+310h+var_298], r12
0x1801670ff  mov     rax, rsi
0x180167102  mov     [rsp+310h+var_2A0], ebx
0x180167106  sbb     ecx, ecx
0x180167108  mov     [rbp+210h+var_28C], r13d
0x18016710c  and     ecx, [rbp+210h+var_1C0.value]
0x18016710f  mov     [rsp+310h+var_29C], ecx
0x180167113  cmp     [rax+48h], r12b
0x180167117  jz      loc_180167317
0x18016711d  mov     rax, [rsi+40h]
0x180167121  jmp     loc_18016731A
0x180167126  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18016712a  lea     r9, [rbp+210h+var_258]
0x18016712e  lea     r8, [rsp+310h+var_2A0]
0x180167133  lea     rdx, [rbp+210h+var_28C]
0x180167137  call    WspUnpackObjectId
0x18016713c  mov     ebx, eax
0x18016713e  test    eax, eax
0x180167140  jz      short loc_180167198
0x180167142  mov     ecx, cs:dword_180397B68
0x180167148  cmp     ecx, 2
0x18016714b  jbe     loc_180167079
0x180167151  mov     [rsp+310h+var_2A0], eax
0x180167155  lea     rdx, word_180359D06
0x18016715c  mov     [rsp+310h+var_29C], 448h
0x180167164  lea     rax, [rsp+310h+var_2A0]
0x180167169  mov     [rsp+310h+var_2E0], rax
0x18016716e  lea     r14, aWspPartitionIn_3; "WSP_Partition_Invoke_RemoveAccessPath"
0x180167175  lea     rax, [rsp+310h+var_29C]
0x18016717a  mov     [rsp+310h+var_298], r14
0x18016717f  mov     [rsp+310h+var_2E8], rax
0x180167184  lea     rax, [rsp+310h+var_298]
0x180167189  mov     qword ptr [rsp+310h+var_2F0], rax
0x18016718e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180167193  jmp     loc_180167080
0x180167198  lea     r8, [rbp+210h+instance]; instance
0x18016719c  mov     rcx, rdi; context
0x18016719f  lea     rdx, WSP_Partition_RemoveAccessPath_rtti; methodDecl
0x1801671a6  call    MI_Context_ConstructParameters
0x1801671ab  mov     ebx, eax
0x1801671ad  test    eax, eax
0x1801671af  jz      short loc_1801671D5
0x1801671b1  mov     eax, cs:dword_180397B68
0x1801671b7  cmp     eax, 2
  ... truncated ...
```
