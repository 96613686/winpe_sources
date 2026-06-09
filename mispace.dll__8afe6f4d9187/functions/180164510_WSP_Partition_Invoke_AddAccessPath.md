# WSP_Partition_Invoke_AddAccessPath

- ea: `0x180164510`
- end: `0x180164ccd`
- name: `WSP_Partition_Invoke_AddAccessPath`
- size: `1981`
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
- `0x180126260`
- `0x180128978`
- `0x180137a24`
- `0x180138120`
- `0x180164510`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164591`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801645f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801647d3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180164591`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801645f1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801647d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180164c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180164c87`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801645b5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801645b5`

## string_xrefs

- `0x1801646e7`: `AddAccessPath`
- `0x180164be6`: `AddAccessPath`
- `0x180164c6e`: `AddAccessPath`
- `0x1801645fd`: `WSP_Partition_Invoke_AddAccessPath`
- `0x1801646ee`: `WSP_Partition_Invoke_AddAccessPath`
- `0x1801648f5`: `WSP_Partition_Invoke_AddAccessPath`
- `0x1801649e7`: `WSP_Partition_Invoke_AddAccessPath`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_AddAccessPath(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        unsigned __int16 **a7)
{
  int v9; // r12d
  const MI_Char *v10; // rdx
  MI_Type *v11; // r8
  __int64 v12; // r8
  __int64 v13; // r9
  const struct _MI_ConstStringField *v14; // r15
  unsigned __int16 *v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned __int16 *v22; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r14d
  __int64 v25; // rcx
  enum _MI_Result v26; // ebx
  __int64 v27; // r8
  __int64 v28; // r9
  const MI_Char *v29; // rax
  enum _MI_Result v30; // eax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  char *v34; // rdx
  char v35; // al
  unsigned __int16 *v36; // r8
  MI_Uint32 v37; // eax
  __int64 v38; // rdx
  unsigned __int16 *v39; // r8
  unsigned int v40; // edx
  _BYTE *v41; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v42; // [rsp+28h] [rbp-D8h]
  __int64 *v43; // [rsp+30h] [rbp-D0h]
  _BYTE *v44; // [rsp+38h] [rbp-C8h]
  unsigned __int32 v45; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h]
  int v48; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v49; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  const char *v52; // [rsp+A0h] [rbp-60h] BYREF
  const char *v53; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v54; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v55; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v56; // [rsp+C0h] [rbp-40h] BYREF
  const char *v57; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v60; // [rsp+E0h] [rbp-20h]
  MI_Value value; // [rsp+F0h] [rbp-10h] BYREF
  MI_Instance instance; // [rsp+120h] [rbp+20h] BYREF
  struct _MI_ConstUint32Field v63; // [rsp+160h] [rbp+60h] BYREF
  MI_Instance self; // [rsp+190h] [rbp+90h] BYREF
  GUID ActivityId; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v66; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v67; // [rsp+2C0h] [rbp+1C0h]
  GUID v68; // [rsp+2C8h] [rbp+1C8h]
  GUID v69; // [rsp+2D8h] [rbp+1D8h] BYREF

  memset(&value, 0, sizeof(value));
  v9 = 1;
  v54 = a5;
  v55 = a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v10, v11, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v68 = ActivityId;
  v69 = ActivityId;
  EventActivityIdControl(4u, &v69);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v49 = 895;
    v42 = (unsigned __int16 *)&v49;
    v52 = "WSP_Partition_Invoke_AddAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"WSP_Partition_Invoke_AddAccessPath",
      (__int64)byte_180359FB1,
      v12,
      v13,
      &v52);
  }
  v52 = 0;
  v48 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x68u);
  CSmTimer::CSmTimer((CSmTimer *)&v58);
  hMem = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v58);
  v14 = a6 + 4;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !a6[4].exists || !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v14->value) )
    v9 = 0;
  v15 = (unsigned __int16 *)v14->value;
  v49 = 0;
  v16 = WspProviderEnter(a2, (__int64)v15, 1u, &v49);
  v17 = v16;
  if ( v16 )
    goto LABEL_9;
  if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v14->value) )
  {
    v17 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v14->value, a5, a7);
LABEL_9:
    if ( a2 && a2->ft )
      ((void (__fastcall *)(MI_Context *, __int64))a2->ft->PostResult)(a2, v17);
    goto LABEL_12;
  }
  v22 = (unsigned __int16 *)v14->value;
  LODWORD(v50) = 0;
  v66 = 0;
  v67 = 0;
  SubsystemType = WspGetSubsystemType(v22);
  SubsystemVersion = _GetSubsystemVersion(&v50);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v66);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v45 = SubsystemType;
    *(_DWORD *)v46 = SubsystemVersion != v50;
    LOWORD(v50) = v67;
    *(_QWORD *)&v46[4] = &v66;
    v44 = v46;
    v43 = &v50;
    v42 = (unsigned __int16 *)&v45;
    v41 = &v46[4];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v25,
      (__int64)&word_18035A616);
  }
  if ( !a7 )
  {
    v26 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_26;
  }
  v30 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v14->value, &v48, &v45, &v52);
  v26 = v30;
  if ( v30 )
  {
    v33 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v45 = v30;
    v34 = (char *)word_18035973A;
    *(_DWORD *)v46 = 932;
    goto LABEL_33;
  }
  v26 = MI_Context_ConstructParameters(a2, &WSP_Partition_AddAccessPath_rtti, &instance);
  if ( v26 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v45 = v26;
      v34 = &byte_18035A4A7;
      *(_DWORD *)v46 = 940;
LABEL_33:
      *(_QWORD *)&v46[4] = "WSP_Partition_Invoke_AddAccessPath";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v33,
        (__int64)v34,
        v31,
        v32,
        &v46[4]);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  LOBYTE(v33) = *((_BYTE *)a7 + 80);
  v35 = *((_BYTE *)a7 + 89);
  if ( !(_BYTE)v33 )
  {
    if ( v35 )
      goto LABEL_39;
LABEL_43:
    v37 = 5;
    goto LABEL_56;
  }
  if ( v35 )
    goto LABEL_43;
LABEL_39:
  if ( v48 )
  {
    if ( (_BYTE)v33 )
      v39 = a7[9];
    else
      v39 = 0;
    if ( v35 )
      v40 = *((unsigned __int8 *)a7 + 88);
    else
      v40 = 0;
    v37 = PmcAddAccessPath((__int64)v52, v40, v39, (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&hMem);
  }
  else
  {
    if ( (_BYTE)v33 )
      v36 = a7[9];
    else
      v36 = 0;
    if ( v35 )
      v38 = *((unsigned __int8 *)a7 + 88);
    else
      v38 = 0;
    v37 = PmAddAccessPath(v52, v38, v36, &hMem);
  }
LABEL_56:
  v63.value = v37;
  v63.exists = 1;
  if ( !hMem )
  {
LABEL_67:
    v26 = MI_Instance_Destruct((MI_Instance *)a2);
    if ( v26 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v45 = v26;
    v34 = &byte_18035AF8F;
    *(_DWORD *)v46 = 997;
    goto LABEL_33;
  }
  if ( !a2 || !a2->ft )
  {
    v26 = MI_RESULT_INVALID_PARAMETER;
LABEL_65:
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v45 = v26;
      v34 = byte_18035A9D3;
      *(_DWORD *)v46 = 977;
      goto LABEL_33;
    }
    goto LABEL_26;
  }
  v26 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
          a2,
          &MSFT_StorageExtendedStatus_rtti,
          &self);
  if ( v26 )
    goto LABEL_65;
  if ( !(unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(
                        (struct _SUEX_EXTENDEDSTATUS_OBJECT *)hMem,
                        (struct _MSFT_StorageExtendedStatus *)&self) )
    goto LABEL_67;
  LODWORD(v41) = 0;
  *(_QWORD *)&v46[4] = &self;
  v26 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _BYTE *, unsigned __int16 *, __int64 *, _BYTE *))instance.ft->SetElementAt)(
          &instance,
          (unsigned int)(v26 + 3),
          &v46[4],
          (unsigned int)(v26 + 15),
          v41,
          v42,
          v43,
          v44);
  if ( v26 == MI_RESULT_OK )
    goto LABEL_67;
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v45 = v26;
    v34 = (char *)&unk_18035A678;
    *(_DWORD *)v46 = 987;
    goto LABEL_33;
  }
LABEL_26:
  CSmTimer::Stop((CSmTimer *)&v58);
  SmLogOnMethodFailure(a4, v54, v14, &v63, v26, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v54 = 0;
    *(_DWORD *)&v46[8] = 0;
    v56 = 1000 * (v59 - v58) / v60;
    v50 = 0;
    v45 = v26;
    *(_QWORD *)v46 = v63.exists != 0 ? v63.value : 0;
    v48 = v9;
    if ( v55[72] )
      v29 = v14->value;
    else
      v29 = 0;
    v55 = v29;
    v57 = "AddAccessPath";
    v53 = "WspPartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v63.exists != 0 ? v63.value : 0,
      (__int64)&word_18035980E,
      v27,
      v28,
      &v53,
      &v57,
      &v55,
      (__int64)&v48,
      (__int64)v46,
      (__int64)&v45,
      (__int64)&v56,
      &v50,
      &v46[4],
      &v54);
  }
  WspFreeString(v52);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  MI_Instance_Destruct(&self);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v26);
LABEL_12:
  WspProviderExit(v49, v17);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v58);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v57 = "AddAccessPath";
        v53 = (const char *)(1000 * (v59 - v58) / v60);
        v56 = (unsigned __int64)"WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v18,
          (__int64)byte_18035992D,
          v19,
          v20,
          &v56,
          &v57);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 1047;
    v53 = "WSP_Partition_Invoke_AddAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v18,
      (__int64)&dword_180359E5C,
      v19,
      v20,
      &v53);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v58);
  return EventActivityIdControl(4u, &v69);
}

```

## disassembly

```asm
0x180164510  mov     [rsp-8+arg_0], rbx
0x180164515  push    rbp
0x180164516  push    rsi
0x180164517  push    rdi
0x180164518  push    r12
0x18016451a  push    r13
0x18016451c  push    r14
0x18016451e  push    r15
0x180164520  lea     rbp, [rsp-1F0h]
0x180164528  sub     rsp, 2F0h
0x18016452f  mov     rax, cs:__security_cookie
0x180164536  xor     rax, rsp
0x180164539  mov     [rbp+220h+var_38], rax
0x180164540  mov     rbx, [rbp+220h+arg_20]
0x180164547  xorps   xmm0, xmm0
0x18016454a  mov     r14, [rbp+220h+arg_28]
0x180164551  xor     eax, eax
0x180164553  mov     rsi, [rbp+220h+arg_30]
0x18016455a  mov     rdi, rdx
0x18016455d  movups  xmmword ptr [rbp+220h+value], xmm0
0x180164561  lea     rdx, [rbp+220h+ActivityId]; ActivityId
0x180164568  mov     r13, r9
0x18016456b  movups  xmmword ptr [rbp+220h+value+10h], xmm0
0x18016456f  lea     r12d, [rax+1]
0x180164573  mov     [rbp+220h+var_270], rbx
0x180164577  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016457e  mov     ecx, r12d; ControlCode
0x180164581  mov     [rbp+220h+var_268], r14
0x180164585  mov     qword ptr [rbp+220h+value+20h], rax
0x180164589  movdqu  xmmword ptr [rbp+220h+ActivityId.Data1], xmm0
0x180164591  call    cs:__imp_EventActivityIdControl
0x180164597  lea     r9, [rbp+220h+value]; value
0x18016459b  mov     rcx, rdi; context
0x18016459e  call    MI_Context_GetCustomOption_1
0x1801645a3  xor     r15d, r15d
0x1801645a6  test    eax, eax
0x1801645a8  jnz     short loc_1801645BB
0x1801645aa  mov     rcx, qword ptr [rbp+220h+value]; lpsz
0x1801645ae  lea     rdx, [rbp+220h+ActivityId]; pclsid
0x1801645b5  call    cs:__imp_CLSIDFromString
0x1801645bb  mov     rcx, qword ptr [rbp+220h+ActivityId.Data1]
0x1801645c2  lea     rdx, [rbp+220h+var_48]; ActivityId
0x1801645c9  mov     rax, qword ptr [rbp+220h+ActivityId.Data4]
0x1801645d0  mov     [rbp+220h+var_58], rcx
0x1801645d7  mov     qword ptr [rbp+220h+var_48.Data1], rcx
0x1801645de  mov     ecx, 4; ControlCode
0x1801645e3  mov     [rbp+220h+var_50], rax
0x1801645ea  mov     qword ptr [rbp+220h+var_48.Data4], rax
0x1801645f1  call    cs:__imp_EventActivityIdControl
0x1801645f7  mov     eax, cs:dword_180397B68
0x1801645fd  lea     rcx, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x180164604  cmp     eax, 5
0x180164607  jbe     short loc_180164632
0x180164609  lea     rax, [rbp+220h+var_298]
0x18016460d  mov     [rbp+220h+var_298], 37Fh
0x180164614  mov     [rsp+320h+var_2F8], rax
0x180164619  lea     rdx, byte_180359FB1
0x180164620  lea     rax, [rbp+220h+var_280]
0x180164624  mov     [rbp+220h+var_280], rcx
0x180164628  mov     qword ptr [rsp+320h+var_300], rax
0x18016462d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180164632  xor     edx, edx; Val
0x180164634  mov     [rbp+220h+var_280], r15
0x180164638  lea     rcx, [rbp+220h+instance.classDecl]; void *
0x18016463c  mov     [rbp+220h+var_29C], r15d
0x180164640  mov     [rbp+220h+instance.ft], r15
0x180164644  lea     r8d, [rdx+68h]; Size
0x180164648  call    memset_0
0x18016464d  lea     rcx, [rbp+220h+var_250]; this
0x180164651  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180164656  xor     edx, edx; Val
0x180164658  mov     [rbp+220h+hMem], r15
0x18016465c  mov     r8d, 108h; Size
0x180164662  mov     [rbp+220h+self.ft], r15
0x180164669  lea     rcx, [rbp+220h+self.classDecl]; void *
0x180164670  call    memset_0
0x180164675  lea     rcx, [rbp+220h+var_250]; this
0x180164679  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016467e  mov     rcx, rdi; context
0x180164681  call    WspIsRemoteRequest
0x180164686  lea     r15, [r14+40h]
0x18016468a  mov     [rbp+220h+var_2A0], eax
0x18016468d  xor     r14d, r14d
0x180164690  cmp     [r15+8], r14b
0x180164694  jz      short loc_1801646A2
0x180164696  mov     rcx, [r15]; unsigned __int16 *
0x180164699  call    WspIsRemoteInstance
0x18016469e  test    al, al
0x1801646a0  jnz     short loc_1801646A5
0x1801646a2  mov     r12d, r14d
0x1801646a5  mov     rdx, [r15]
0x1801646a8  lea     r9, [rbp+220h+var_298]
0x1801646ac  mov     r8d, 1
0x1801646b2  mov     [rbp+220h+var_298], r14d
0x1801646b6  mov     rcx, rdi; context
0x1801646b9  call    WspProviderEnter
0x1801646be  mov     edx, eax
0x1801646c0  test    eax, eax
0x1801646c2  jz      loc_180164803
0x1801646c8  test    rdi, rdi
0x1801646cb  jz      short loc_1801646E0
0x1801646cd  mov     rax, [rdi]
0x1801646d0  test    rax, rax
0x1801646d3  jz      short loc_1801646E0
0x1801646d5  mov     rax, [rax]
0x1801646d8  mov     rcx, rdi
0x1801646db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801646e0  lea     r13, aWsppartition; "WspPartition"
0x1801646e7  lea     r15, aAddaccesspath_0; "AddAccessPath"
0x1801646ee  lea     rsi, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x1801646f5  mov     ecx, [rbp+220h+var_298]
0x1801646f8  call    WspProviderExit
0x1801646fd  cmp     [rbp+220h+var_2A0], r14d
0x180164701  jz      loc_18016478A
0x180164707  lea     rcx, [rbp+220h+var_250]; this
0x18016470b  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180164710  mov     eax, cs:dword_180397B68
0x180164716  cmp     eax, 5
0x180164719  jbe     short loc_18016478A
0x18016471b  mov     rdx, 400000000000h
0x180164725  lea     rcx, dword_180397B68
0x18016472c  call    _tlgKeywordOn
0x180164731  test    al, al
0x180164733  jz      short loc_18016478A
0x180164735  mov     rax, [rbp+220h+var_248]
0x180164739  xor     edx, edx
0x18016473b  sub     rax, [rbp+220h+var_250]
0x18016473f  imul    rax, 3E8h
0x180164746  mov     [rbp+220h+var_2A0], r12d
0x18016474a  div     [rbp+220h+var_240]
0x18016474e  lea     rdx, byte_18035992D
0x180164755  mov     [rbp+220h+var_258], r15
0x180164759  mov     [rbp+220h+var_278], rax
0x18016475d  lea     rax, [rbp+220h+var_278]
0x180164761  mov     [rsp+320h+var_2E8], rax
0x180164766  lea     rax, [rbp+220h+var_2A0]
0x18016476a  mov     [rsp+320h+var_2F0], rax
0x18016476f  lea     rax, [rbp+220h+var_258]
0x180164773  mov     [rsp+320h+var_2F8], rax
0x180164778  lea     rax, [rbp+220h+var_260]
0x18016477c  mov     qword ptr [rsp+320h+var_300], rax
0x180164781  mov     [rbp+220h+var_260], r13
0x180164785  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18016478a  mov     eax, cs:dword_180397B68
0x180164790  cmp     eax, 5
0x180164793  jbe     short loc_1801647BE
0x180164795  lea     rax, [rbp+220h+var_2A0]
0x180164799  mov     [rbp+220h+var_2A0], 417h
0x1801647a0  mov     [rsp+320h+var_2F8], rax
0x1801647a5  lea     rdx, dword_180359E5C
0x1801647ac  lea     rax, [rbp+220h+var_278]
0x1801647b0  mov     [rbp+220h+var_278], rsi
0x1801647b4  mov     qword ptr [rsp+320h+var_300], rax
0x1801647b9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801647be  lea     rcx, [rbp+220h+var_250]; this
0x1801647c2  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1801647c7  lea     rdx, [rbp+220h+var_48]; ActivityId
0x1801647ce  mov     ecx, 4; ControlCode
0x1801647d3  call    cs:__imp_EventActivityIdControl
0x1801647d9  mov     rcx, [rbp+220h+var_38]
0x1801647e0  xor     rcx, rsp; StackCookie
0x1801647e3  call    __security_check_cookie
0x1801647e8  mov     rbx, [rsp+320h+arg_0]
0x1801647f0  add     rsp, 2F0h
0x1801647f7  pop     r15
0x1801647f9  pop     r14
0x1801647fb  pop     r13
0x1801647fd  pop     r12
0x1801647ff  pop     rdi
0x180164800  pop     rsi
0x180164801  pop     rbp
0x180164802  retn
0x180164803  mov     rcx, [r15]; unsigned __int16 *
0x180164806  call    WspIsRemoteInstance
0x18016480b  test    al, al
0x18016480d  jz      short loc_18016482C
0x18016480f  mov     r8, [r15]; unsigned __int16 *
0x180164812  mov     r9, rbx; unsigned __int16 *
0x180164815  mov     rdx, r13; unsigned __int16 *
0x180164818  mov     qword ptr [rsp+320h+var_300], rsi; void *
0x18016481d  mov     rcx, rdi; struct _MI_Context *
0x180164820  call    WspInvokeRemoteMethod
0x180164825  mov     edx, eax
0x180164827  jmp     loc_1801646C8
0x18016482c  mov     rcx, [r15]
0x18016482f  xorps   xmm0, xmm0
0x180164832  xor     eax, eax
0x180164834  mov     dword ptr [rbp+220h+var_290], r14d
0x180164838  movups  [rbp+220h+var_70], xmm0
0x18016483f  mov     [rbp+220h+var_60], eax
0x180164845  call    WspGetSubsystemType
0x18016484a  lea     rcx, [rbp+220h+var_290]
0x18016484e  mov     ebx, eax
0x180164850  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180164855  lea     rdx, [rbp+220h+var_70]; struct _SUBSYSTEM_INFO *
0x18016485c  mov     ecx, ebx; unsigned int
0x18016485e  mov     r14d, eax
0x180164861  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180164866  mov     ecx, cs:dword_180397B68
0x18016486c  cmp     ecx, 5
0x18016486f  jbe     short loc_1801648E6
0x180164871  mov     rdx, 400000000000h
0x18016487b  lea     rcx, dword_180397B68
0x180164882  call    _tlgKeywordOn
0x180164887  test    al, al
0x180164889  jz      short loc_1801648E6
0x18016488b  xor     eax, eax
0x18016488d  mov     [rsp+320h+var_2B0], ebx
0x180164891  cmp     r14d, dword ptr [rbp+220h+var_290]
0x180164895  lea     rdx, word_18035A616
0x18016489c  setnz   al
0x18016489f  mov     [rsp+320h+var_2AC], eax
0x1801648a3  movzx   eax, word ptr [rbp+220h+var_60]
0x1801648aa  mov     word ptr [rbp+220h+var_290], ax
0x1801648ae  lea     rax, [rbp+220h+var_70]
0x1801648b5  mov     [rsp+320h+var_2A8], rax
0x1801648ba  lea     rax, [rsp+320h+var_2AC]
0x1801648bf  mov     [rsp+320h+var_2E8], rax
0x1801648c4  lea     rax, [rbp+220h+var_290]
0x1801648c8  mov     [rsp+320h+var_2F0], rax
0x1801648cd  lea     rax, [rsp+320h+var_2B0]
0x1801648d2  mov     [rsp+320h+var_2F8], rax
0x1801648d7  lea     rax, [rsp+320h+var_2A8]
0x1801648dc  mov     qword ptr [rsp+320h+var_300], rax
0x1801648e1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1801648e6  xor     r14d, r14d
0x1801648e9  test    rsi, rsi
0x1801648ec  jnz     loc_1801649A0
0x1801648f2  lea     ebx, [rsi+4]
0x1801648f5  lea     rsi, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x1801648fc  lea     rcx, [rbp+220h+var_250]; this
0x180164900  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180164905  mov     rdx, [rbp+220h+var_270]; unsigned __int16 *
0x180164909  lea     r9, [rbp+220h+var_1C0]; struct _MI_ConstUint32Field *
0x18016490d  mov     r8, r15; struct _MI_ConstStringField *
0x180164910  mov     [rsp+320h+var_2F8], r14; unsigned __int16 *
0x180164915  mov     rcx, r13; unsigned __int16 *
0x180164918  mov     [rsp+320h+var_300], ebx; enum _MI_Result
0x18016491c  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180164921  mov     eax, cs:dword_180397B68
0x180164927  cmp     eax, 5
0x18016492a  jbe     loc_180164C67
0x180164930  mov     rdx, 400000000000h
0x18016493a  lea     rcx, dword_180397B68
0x180164941  call    _tlgKeywordOn
0x180164946  test    al, al
0x180164948  jz      loc_180164C67
0x18016494e  mov     rax, [rbp+220h+var_248]
0x180164952  xor     edx, edx
0x180164954  sub     rax, [rbp+220h+var_250]
0x180164958  imul    rax, 3E8h
0x18016495f  mov     [rbp+220h+var_270], r14
0x180164963  div     [rbp+220h+var_240]
0x180164967  mov     [rsp+320h+var_2A8], r14
0x18016496c  mov     [rbp+220h+var_260], rax
0x180164970  mov     al, [rbp+220h+var_1C0.exists]
0x180164973  neg     al
0x180164975  mov     [rbp+220h+var_290], r14
0x180164979  mov     rax, [rbp+220h+var_268]
0x18016497d  sbb     ecx, ecx
0x18016497f  mov     [rsp+320h+var_2B0], ebx
0x180164983  and     ecx, [rbp+220h+var_1C0.value]
0x180164986  mov     [rsp+320h+var_2AC], ecx
0x18016498a  mov     [rbp+220h+var_29C], r12d
0x18016498e  cmp     [rax+48h], r14b
0x180164992  jz      loc_180164BDF
0x180164998  mov     rax, [r15]
0x18016499b  jmp     loc_180164BE2
0x1801649a0  mov     rcx, [r15]; unsigned __int16 *
0x1801649a3  lea     r9, [rbp+220h+var_280]
0x1801649a7  lea     r8, [rsp+320h+var_2B0]
0x1801649ac  lea     rdx, [rbp+220h+var_29C]
0x1801649b0  call    WspUnpackObjectId
0x1801649b5  mov     ebx, eax
0x1801649b7  test    eax, eax
0x1801649b9  jz      short loc_180164A11
0x1801649bb  mov     ecx, cs:dword_180397B68
0x1801649c1  cmp     ecx, 2
0x1801649c4  jbe     loc_1801648F5
0x1801649ca  mov     [rsp+320h+var_2B0], eax
0x1801649ce  lea     rdx, word_18035973A
0x1801649d5  mov     [rsp+320h+var_2AC], 3A4h
0x1801649dd  lea     rax, [rsp+320h+var_2B0]
0x1801649e2  mov     [rsp+320h+var_2F0], rax
0x1801649e7  lea     rsi, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x1801649ee  lea     rax, [rsp+320h+var_2AC]
0x1801649f3  mov     [rsp+320h+var_2A8], rsi
0x1801649f8  mov     [rsp+320h+var_2F8], rax
0x1801649fd  lea     rax, [rsp+320h+var_2A8]
0x180164a02  mov     qword ptr [rsp+320h+var_300], rax
0x180164a07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180164a0c  jmp     loc_1801648FC
0x180164a11  lea     r8, [rbp+220h+instance]; instance
0x180164a15  mov     rcx, rdi; context
0x180164a18  lea     rdx, WSP_Partition_AddAccessPath_rtti; methodDecl
0x180164a1f  call    MI_Context_ConstructParameters
0x180164a24  mov     ebx, eax
0x180164a26  test    eax, eax
0x180164a28  jz      short loc_180164A4E
0x180164a2a  mov     eax, cs:dword_180397B68
  ... truncated ...
```
