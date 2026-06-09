# WSP_Partition_Invoke_SetAttributes

- ea: `0x180167b80`
- end: `0x180168514`
- name: `WSP_Partition_Invoke_SetAttributes`
- size: `2452`
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
- `0x180128288`
- `0x18012a188`
- `0x180137a24`
- `0x180138120`
- `0x180167b80`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180167bfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180167c5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180167ec7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180167bfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180167c5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180167ec7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801684d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801684d2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180167c21`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801682ce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180167c21`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801682ce`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_SetAttributes(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        LPCOLESTR *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r13d
  __int64 v12; // r8
  __int64 v13; // r9
  struct _SUEX_EXTENDEDSTATUS_OBJECT *v14; // r12
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  const MI_Char *v22; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // r14d
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
  int v35; // ecx
  char v36; // al
  int v37; // ecx
  char v38; // al
  int v39; // ecx
  char v40; // al
  int v41; // ecx
  char v42; // al
  int v43; // ecx
  char v44; // al
  int v45; // ecx
  char v46; // al
  __int16 v47; // cx
  char v48; // al
  int v49; // eax
  HRESULT v50; // eax
  MI_Uint32 v51; // eax
  _BYTE *v52; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v53; // [rsp+28h] [rbp-D8h]
  const char **v54; // [rsp+30h] [rbp-D0h]
  _BYTE *v55; // [rsp+38h] [rbp-C8h]
  unsigned __int32 v56; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v57[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h]
  int v59; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v60; // [rsp+88h] [rbp-78h] BYREF
  const char *v61; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v62; // [rsp+98h] [rbp-68h] BYREF
  const char *v63; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v64; // [rsp+A8h] [rbp-58h] BYREF
  const char *v65; // [rsp+B0h] [rbp-50h] BYREF
  const char *v66; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v67; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v68; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v69; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v70; // [rsp+D8h] [rbp-28h]
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  struct _MI_ConstUint32Field v73; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance self; // [rsp+190h] [rbp+90h] BYREF
  char v75; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v76; // [rsp+2A1h] [rbp+1A1h]
  char v77; // [rsp+2A3h] [rbp+1A3h]
  int v78; // [rsp+2A4h] [rbp+1A4h]
  char v79; // [rsp+2A8h] [rbp+1A8h]
  __int16 v80; // [rsp+2A9h] [rbp+1A9h]
  char v81; // [rsp+2ABh] [rbp+1ABh]
  int v82; // [rsp+2ACh] [rbp+1ACh]
  char v83; // [rsp+2B0h] [rbp+1B0h]
  __int16 v84; // [rsp+2B1h] [rbp+1B1h]
  char v85; // [rsp+2B3h] [rbp+1B3h]
  int v86; // [rsp+2B4h] [rbp+1B4h]
  char v87; // [rsp+2B8h] [rbp+1B8h]
  __int16 v88; // [rsp+2B9h] [rbp+1B9h]
  char v89; // [rsp+2BBh] [rbp+1BBh]
  int v90; // [rsp+2BCh] [rbp+1BCh]
  char v91; // [rsp+2C0h] [rbp+1C0h]
  __int16 v92; // [rsp+2C1h] [rbp+1C1h]
  char v93; // [rsp+2C3h] [rbp+1C3h]
  int v94; // [rsp+2C4h] [rbp+1C4h]
  char v95; // [rsp+2C8h] [rbp+1C8h]
  char v96; // [rsp+2C9h] [rbp+1C9h]
  __int16 v97; // [rsp+2CAh] [rbp+1CAh]
  _BYTE v98[20]; // [rsp+2CCh] [rbp+1CCh] BYREF
  char v99; // [rsp+2E0h] [rbp+1E0h]
  __int16 v100; // [rsp+2E1h] [rbp+1E1h]
  char v101; // [rsp+2E3h] [rbp+1E3h]
  int v102; // [rsp+2E4h] [rbp+1E4h]
  GUID ActivityId; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v104; // [rsp+300h] [rbp+200h] BYREF
  int v105; // [rsp+310h] [rbp+210h]
  GUID pclsid; // [rsp+318h] [rbp+218h] BYREF
  GUID v107; // [rsp+328h] [rbp+228h]
  GUID v108; // [rsp+338h] [rbp+238h] BYREF

  memset(&value, 0, sizeof(value));
  v64 = a4;
  v67 = a5;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v107 = ActivityId;
  v108 = ActivityId;
  EventActivityIdControl(4u, &v108);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v60 = 1763;
    v53 = (unsigned __int16 *)&v60;
    v63 = "WSP_Partition_Invoke_SetAttributes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"WSP_Partition_Invoke_SetAttributes",
      (__int64)&byte_180359EEF,
      v12,
      v13,
      &v63);
  }
  v63 = 0;
  v59 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v75 = 1;
  memset(v98, 0, sizeof(v98));
  v78 = 0;
  v79 = 0;
  pclsid = GUID_NULL;
  v82 = 0;
  v83 = 0;
  v86 = 0;
  v87 = 0;
  v90 = 0;
  v91 = 0;
  v94 = 0;
  v95 = 0;
  v97 = 0;
  v99 = 0;
  v102 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v68);
  v62 = 0;
  self.ft = 0;
  v14 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v68);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value) )
    v11 = 1;
  v15 = (__int64)a6[4].value;
  v60 = 0;
  v16 = WspProviderEnter(a2, v15, 1u, &v60);
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
  v105 = 0;
  v104 = 0;
  LODWORD(v61) = 0;
  SubsystemType = WspGetSubsystemType(v22);
  SubsystemVersion = _GetSubsystemVersion(&v61);
  WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v104);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v56 = SubsystemType;
    *(_DWORD *)v57 = SubsystemVersion != (_DWORD)v61;
    LOWORD(v61) = v105;
    *(_QWORD *)&v57[4] = &v104;
    v55 = v57;
    v54 = &v61;
    v53 = (unsigned __int16 *)&v56;
    v52 = &v57[4];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v25,
      (__int64)byte_180359A43);
  }
  if ( !a7 )
  {
    v26 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_26;
  }
  v30 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)a6[4].value, &v59, &v56, &v63);
  v26 = v30;
  if ( v30 )
  {
    v33 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v56 = v30;
    v34 = (char *)word_18035A552;
    *(_DWORD *)v57 = 1802;
    goto LABEL_33;
  }
  v26 = MI_Context_ConstructParameters(a2, &WSP_Partition_SetAttributes_rtti, &instance);
  if ( v26 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v56 = v26;
      v34 = (char *)&unk_180359610;
      *(_DWORD *)v57 = 1810;
LABEL_33:
      *(_QWORD *)&v57[4] = "WSP_Partition_Invoke_SetAttributes";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v33,
        (__int64)v34,
        v31,
        v32,
        &v57[4]);
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  if ( *((_BYTE *)a7 + 79) )
  {
    v35 = *((unsigned __int8 *)a7 + 78);
    v36 = 1;
  }
  else
  {
    v35 = 0;
    v36 = 0;
  }
  v83 = v36;
  v84 = *(_WORD *)&v57[5];
  v85 = v57[7];
  v86 = v35;
  if ( *((_BYTE *)a7 + 82) )
  {
    v37 = *((unsigned __int8 *)a7 + 81);
    v38 = 1;
  }
  else
  {
    v37 = 0;
    v38 = 0;
  }
  v87 = v38;
  v88 = *(_WORD *)&v57[5];
  v89 = v57[7];
  v90 = v37;
  if ( *((_BYTE *)a7 + 85) )
  {
    v39 = *((unsigned __int8 *)a7 + 84);
    v40 = 1;
  }
  else
  {
    v39 = 0;
    v40 = 0;
  }
  v99 = v40;
  v100 = *(_WORD *)&v57[5];
  v101 = v57[7];
  v102 = v39;
  if ( *((_BYTE *)a7 + 73) )
  {
    v41 = *((unsigned __int8 *)a7 + 72);
    v42 = 1;
  }
  else
  {
    v41 = 0;
    v42 = 0;
  }
  v75 = v42;
  v76 = *(_WORD *)&v57[5];
  v77 = v57[7];
  v78 = v41;
  if ( *((_BYTE *)a7 + 88) )
  {
    v43 = *((unsigned __int8 *)a7 + 87);
    v44 = 1;
  }
  else
  {
    v43 = 0;
    v44 = 0;
  }
  v91 = v44;
  v92 = *(_WORD *)&v57[5];
  v93 = v57[7];
  v94 = v43;
  if ( *((_BYTE *)a7 + 76) )
  {
    v45 = *((unsigned __int8 *)a7 + 75);
    v46 = 1;
  }
  else
  {
    v45 = 0;
    v46 = 0;
  }
  v79 = v46;
  v80 = *(_WORD *)&v57[5];
  v81 = v57[7];
  v82 = v45;
  if ( *((_BYTE *)a7 + 92) )
  {
    v47 = *((_WORD *)a7 + 45);
    v48 = 1;
  }
  else
  {
    v47 = 0;
    v48 = 0;
  }
  v95 = v48;
  v96 = BYTE1(IsRemoteRequest);
  v49 = *((unsigned __int8 *)a7 + 104);
  v97 = v47;
  *(_DWORD *)v98 = v49;
  if ( !(_BYTE)v49
    || (v50 = CLSIDFromString(a7[12], &pclsid), *(GUID *)&v98[4] = pclsid, (v51 = (v50 >> 31) & 0xA032) == 0) )
  {
    if ( v59 )
      v51 = PmcSetPartitionAttributes(v63, &v75, &v62);
    else
      v51 = PmSetPartitionAttributes(v63, &v75, &v62);
    v14 = (struct _SUEX_EXTENDEDSTATUS_OBJECT *)v62;
  }
  v73.value = v51;
  v73.exists = 1;
  if ( !v14 )
  {
LABEL_75:
    v26 = MI_Instance_Destruct((MI_Instance *)a2);
    if ( v26 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_26;
    v56 = v26;
    v34 = byte_18035A86B;
    *(_DWORD *)v57 = 1880;
    goto LABEL_33;
  }
  if ( !a2 || !a2->ft )
  {
    v26 = MI_RESULT_INVALID_PARAMETER;
LABEL_73:
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v56 = v26;
      v34 = (char *)&unk_180359D78;
      *(_DWORD *)v57 = 1860;
      goto LABEL_33;
    }
    goto LABEL_26;
  }
  v26 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
          a2,
          &MSFT_StorageExtendedStatus_rtti,
          &self);
  if ( v26 )
    goto LABEL_73;
  if ( !(unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(v14, (struct _MSFT_StorageExtendedStatus *)&self) )
    goto LABEL_75;
  LODWORD(v52) = 0;
  *(_QWORD *)&v57[4] = &self;
  v26 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _BYTE *, unsigned __int16 *, const char **, _BYTE *))instance.ft->SetElementAt)(
          &instance,
          (unsigned int)(v26 + 9),
          &v57[4],
          (unsigned int)(v26 + 15),
          v52,
          v53,
          v54,
          v55);
  if ( v26 == MI_RESULT_OK )
    goto LABEL_75;
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    v56 = v26;
    v34 = &byte_18035ACC7;
    *(_DWORD *)v57 = 1870;
    goto LABEL_33;
  }
LABEL_26:
  CSmTimer::Stop((CSmTimer *)&v68);
  SmLogOnMethodFailure(v64, v67, a6 + 4, &v73, v26, 0);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v64 = 0;
    v67 = 0;
    v62 = 1000 * (v69 - v68) / v70;
    *(_DWORD *)&v57[8] = 0;
    v56 = v26;
    v59 = v11;
    *(_QWORD *)v57 = v73.exists != 0 ? v73.value : 0;
    if ( a6[4].exists )
      v29 = (const char *)a6[4].value;
    else
      v29 = 0;
    v65 = v29;
    v61 = "SetAttributes";
    v66 = "WspPartition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v73.exists != 0 ? v73.value : 0,
      (__int64)byte_18035998B,
      v27,
      v28,
      &v66,
      &v61,
      &v65,
      (__int64)&v59,
      (__int64)v57,
      (__int64)&v56,
      (__int64)&v62,
      &v57[4],
      &v67,
      &v64);
  }
  WspFreeString(v63);
  if ( v14 )
    LocalFree(v14);
  MI_Instance_Destruct(&self);
  MI_Instance_Destruct(&instance);
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v26);
LABEL_12:
  WspProviderExit(v60, v17);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v68);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        IsRemoteRequest = v11;
        v65 = "SetAttributes";
        v66 = (const char *)(1000 * (v69 - v68) / v70);
        v64 = (unsigned __int16 *)"WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v18,
          (__int64)&word_18035B376,
          v19,
          v20,
          &v64,
          &v65);
      }
    }
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    IsRemoteRequest = 1930;
    v66 = "WSP_Partition_Invoke_SetAttributes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v18,
      (__int64)qword_18035AD00,
      v19,
      v20,
      &v66);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v68);
  return EventActivityIdControl(4u, &v108);
}

```

## disassembly

```asm
0x180167b80  mov     [rsp-8+arg_0], rbx
0x180167b85  push    rbp
0x180167b86  push    rsi
0x180167b87  push    rdi
0x180167b88  push    r12
0x180167b8a  push    r13
0x180167b8c  push    r14
0x180167b8e  push    r15
0x180167b90  lea     rbp, [rsp-250h]
0x180167b98  sub     rsp, 350h
0x180167b9f  mov     rax, cs:__security_cookie
0x180167ba6  xor     rax, rsp
0x180167ba9  mov     [rbp+280h+var_38], rax
0x180167bb0  mov     r14, [rbp+280h+arg_20]
0x180167bb7  xorps   xmm0, xmm0
0x180167bba  mov     r15, [rbp+280h+arg_28]
0x180167bc1  xor     eax, eax
0x180167bc3  mov     rdi, [rbp+280h+arg_30]
0x180167bca  mov     rbx, r9
0x180167bcd  movups  xmmword ptr [rbp+280h+value], xmm0
0x180167bd1  mov     rsi, rdx
0x180167bd4  lea     rdx, [rbp+280h+ActivityId]; ActivityId
0x180167bdb  movups  xmmword ptr [rbp+280h+value+10h], xmm0
0x180167bdf  lea     ecx, [rax+1]; ControlCode
0x180167be2  mov     [rbp+280h+var_2D8], rbx
0x180167be6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180167bed  mov     [rbp+280h+var_2C0], r14
0x180167bf1  mov     qword ptr [rbp+280h+value+20h], rax
0x180167bf5  movdqu  xmmword ptr [rbp+280h+ActivityId.Data1], xmm0
0x180167bfd  call    cs:__imp_EventActivityIdControl
0x180167c03  lea     r9, [rbp+280h+value]; value
0x180167c07  mov     rcx, rsi; context
0x180167c0a  call    MI_Context_GetCustomOption_1
0x180167c0f  xor     r13d, r13d
0x180167c12  test    eax, eax
0x180167c14  jnz     short loc_180167C27
0x180167c16  mov     rcx, qword ptr [rbp+280h+value]; lpsz
0x180167c1a  lea     rdx, [rbp+280h+ActivityId]; pclsid
0x180167c21  call    cs:__imp_CLSIDFromString
0x180167c27  mov     rcx, qword ptr [rbp+280h+ActivityId.Data1]
0x180167c2e  lea     rdx, [rbp+280h+var_48]; ActivityId
0x180167c35  mov     rax, qword ptr [rbp+280h+ActivityId.Data4]
0x180167c3c  mov     [rbp+280h+var_58], rcx
0x180167c43  mov     qword ptr [rbp+280h+var_48.Data1], rcx
0x180167c4a  mov     ecx, 4; ControlCode
0x180167c4f  mov     [rbp+280h+var_50], rax
0x180167c56  mov     qword ptr [rbp+280h+var_48.Data4], rax
0x180167c5d  call    cs:__imp_EventActivityIdControl
0x180167c63  mov     eax, cs:dword_180397B68
0x180167c69  lea     rcx, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x180167c70  cmp     eax, 5
0x180167c73  jbe     short loc_180167C9E
0x180167c75  lea     rax, [rbp+280h+var_2F8]
0x180167c79  mov     [rbp+280h+var_2F8], 6E3h
0x180167c80  mov     [rsp+380h+var_358], rax
0x180167c85  lea     rdx, byte_180359EEF
0x180167c8c  lea     rax, [rbp+280h+var_2E0]
0x180167c90  mov     [rbp+280h+var_2E0], rcx
0x180167c94  mov     qword ptr [rsp+380h+var_360], rax
0x180167c99  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180167c9e  xor     edx, edx; Val
0x180167ca0  mov     [rbp+280h+var_2E0], r13
0x180167ca4  lea     rcx, [rbp+280h+instance.classDecl]; void *
0x180167ca8  mov     [rbp+280h+var_2FC], r13d
0x180167cac  mov     [rbp+280h+instance.ft], r13
0x180167cb0  lea     r8d, [rdx+78h]; Size
0x180167cb4  call    memset_0
0x180167cb9  xorps   xmm0, xmm0
0x180167cbc  mov     [rbp+280h+var_E0], 1
0x180167cc3  movups  [rbp+280h+var_B4], xmm0
0x180167cca  xor     eax, eax
0x180167ccc  lea     rcx, [rbp+280h+var_2B8]; this
0x180167cd0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180167cd7  mov     [rbp+280h+var_DC], r13d
0x180167cde  mov     [rbp+280h+var_D8], r13b
0x180167ce5  movdqu  xmmword ptr [rbp+280h+pclsid.Data1], xmm0
0x180167ced  mov     [rbp+280h+var_D4], r13d
0x180167cf4  mov     [rbp+280h+var_D0], r13b
0x180167cfb  mov     [rbp+280h+var_CC], r13d
0x180167d02  mov     [rbp+280h+var_C8], r13b
0x180167d09  mov     [rbp+280h+var_C4], r13d
0x180167d10  mov     [rbp+280h+var_C0], r13b
0x180167d17  mov     [rbp+280h+var_BC], r13d
0x180167d1e  mov     [rbp+280h+var_B8], r13b
0x180167d25  mov     [rbp+280h+var_B6], r13w
0x180167d2d  mov     [rbp+280h+var_A4], eax
0x180167d33  mov     [rbp+280h+var_A0], r13b
0x180167d3a  mov     [rbp+280h+var_9C], r13d
0x180167d41  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180167d46  xor     edx, edx; Val
0x180167d48  mov     [rbp+280h+var_2E8], r13
0x180167d4c  mov     r8d, 108h; Size
0x180167d52  mov     [rbp+280h+self.ft], r13
0x180167d59  lea     rcx, [rbp+280h+self.classDecl]; void *
0x180167d60  mov     r12, r13
0x180167d63  call    memset_0
0x180167d68  lea     rcx, [rbp+280h+var_2B8]; this
0x180167d6c  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180167d71  mov     rcx, rsi; context
0x180167d74  call    WspIsRemoteRequest
0x180167d79  mov     [rbp+280h+var_300], eax
0x180167d7c  cmp     [r15+48h], r13b
0x180167d80  jz      short loc_180167D95
0x180167d82  mov     rcx, [r15+40h]; unsigned __int16 *
0x180167d86  call    WspIsRemoteInstance
0x180167d8b  test    al, al
0x180167d8d  jz      short loc_180167D95
0x180167d8f  mov     r13d, 1
0x180167d95  mov     rdx, [r15+40h]
0x180167d99  lea     r9, [rbp+280h+var_2F8]
0x180167d9d  mov     r8d, 1
0x180167da3  mov     [rbp+280h+var_2F8], r12d
0x180167da7  mov     rcx, rsi; context
0x180167daa  call    WspProviderEnter
0x180167daf  mov     edx, eax
0x180167db1  test    eax, eax
0x180167db3  jz      loc_180167EF7
0x180167db9  xor     r14d, r14d
0x180167dbc  test    rsi, rsi
0x180167dbf  jz      short loc_180167DD4
0x180167dc1  mov     rax, [rsi]
0x180167dc4  test    rax, rax
0x180167dc7  jz      short loc_180167DD4
0x180167dc9  mov     rax, [rax]
0x180167dcc  mov     rcx, rsi
0x180167dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180167dd4  lea     r15, aSetattributes; "SetAttributes"
0x180167ddb  lea     rdi, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x180167de2  mov     ecx, [rbp+280h+var_2F8]
0x180167de5  call    WspProviderExit
0x180167dea  cmp     [rbp+280h+var_300], r14d
0x180167dee  jz      loc_180167E7E
0x180167df4  lea     rcx, [rbp+280h+var_2B8]; this
0x180167df8  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180167dfd  mov     eax, cs:dword_180397B68
0x180167e03  cmp     eax, 5
0x180167e06  jbe     short loc_180167E7E
0x180167e08  mov     rdx, 400000000000h
0x180167e12  lea     rcx, dword_180397B68
0x180167e19  call    _tlgKeywordOn
0x180167e1e  test    al, al
0x180167e20  jz      short loc_180167E7E
0x180167e22  mov     rax, [rbp+280h+var_2B0]
0x180167e26  xor     edx, edx
0x180167e28  sub     rax, [rbp+280h+var_2B8]
0x180167e2c  imul    rax, 3E8h
0x180167e33  mov     [rbp+280h+var_300], r13d
0x180167e37  div     [rbp+280h+var_2A8]
0x180167e3b  lea     rdx, word_18035B376
0x180167e42  mov     [rbp+280h+var_2D0], r15
0x180167e46  mov     [rbp+280h+var_2C8], rax
0x180167e4a  lea     rax, aWsppartition; "WspPartition"
0x180167e51  mov     [rbp+280h+var_2D8], rax
0x180167e55  lea     rax, [rbp+280h+var_2C8]
0x180167e59  mov     [rsp+380h+var_348], rax
0x180167e5e  lea     rax, [rbp+280h+var_300]
0x180167e62  mov     [rsp+380h+var_350], rax
0x180167e67  lea     rax, [rbp+280h+var_2D0]
0x180167e6b  mov     [rsp+380h+var_358], rax
0x180167e70  lea     rax, [rbp+280h+var_2D8]
0x180167e74  mov     qword ptr [rsp+380h+var_360], rax
0x180167e79  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180167e7e  mov     eax, cs:dword_180397B68
0x180167e84  cmp     eax, 5
0x180167e87  jbe     short loc_180167EB2
0x180167e89  lea     rax, [rbp+280h+var_300]
0x180167e8d  mov     [rbp+280h+var_300], 78Ah
0x180167e94  mov     [rsp+380h+var_358], rax
0x180167e99  lea     rdx, qword_18035AD00
0x180167ea0  lea     rax, [rbp+280h+var_2C8]
0x180167ea4  mov     [rbp+280h+var_2C8], rdi
0x180167ea8  mov     qword ptr [rsp+380h+var_360], rax
0x180167ead  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180167eb2  lea     rcx, [rbp+280h+var_2B8]; this
0x180167eb6  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180167ebb  lea     rdx, [rbp+280h+var_48]; ActivityId
0x180167ec2  mov     ecx, 4; ControlCode
0x180167ec7  call    cs:__imp_EventActivityIdControl
0x180167ecd  mov     rcx, [rbp+280h+var_38]
0x180167ed4  xor     rcx, rsp; StackCookie
0x180167ed7  call    __security_check_cookie
0x180167edc  mov     rbx, [rsp+380h+arg_0]
0x180167ee4  add     rsp, 350h
0x180167eeb  pop     r15
0x180167eed  pop     r14
0x180167eef  pop     r13
0x180167ef1  pop     r12
0x180167ef3  pop     rdi
0x180167ef4  pop     rsi
0x180167ef5  pop     rbp
0x180167ef6  retn
0x180167ef7  mov     rcx, [r15+40h]; unsigned __int16 *
0x180167efb  call    WspIsRemoteInstance
0x180167f00  test    al, al
0x180167f02  jz      short loc_180167F22
0x180167f04  mov     r8, [r15+40h]; unsigned __int16 *
0x180167f08  mov     r9, r14; unsigned __int16 *
0x180167f0b  mov     rdx, rbx; unsigned __int16 *
0x180167f0e  mov     qword ptr [rsp+380h+var_360], rdi; void *
0x180167f13  mov     rcx, rsi; struct _MI_Context *
0x180167f16  call    WspInvokeRemoteMethod
0x180167f1b  mov     edx, eax
0x180167f1d  jmp     loc_180167DB9
0x180167f22  mov     rcx, [r15+40h]
0x180167f26  xor     eax, eax
0x180167f28  xorps   xmm0, xmm0
0x180167f2b  mov     [rbp+280h+var_70], eax
0x180167f31  movups  [rbp+280h+var_80], xmm0
0x180167f38  mov     dword ptr [rbp+280h+var_2F0], eax
0x180167f3b  call    WspGetSubsystemType
0x180167f40  lea     rcx, [rbp+280h+var_2F0]
0x180167f44  mov     ebx, eax
0x180167f46  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180167f4b  lea     rdx, [rbp+280h+var_80]; struct _SUBSYSTEM_INFO *
0x180167f52  mov     ecx, ebx; unsigned int
0x180167f54  mov     r14d, eax
0x180167f57  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180167f5c  mov     ecx, cs:dword_180397B68
0x180167f62  cmp     ecx, 5
0x180167f65  jbe     short loc_180167FDC
0x180167f67  mov     rdx, 400000000000h
0x180167f71  lea     rcx, dword_180397B68
0x180167f78  call    _tlgKeywordOn
0x180167f7d  test    al, al
0x180167f7f  jz      short loc_180167FDC
0x180167f81  xor     eax, eax
0x180167f83  mov     [rsp+380h+var_310], ebx
0x180167f87  cmp     r14d, dword ptr [rbp+280h+var_2F0]
0x180167f8b  lea     rdx, byte_180359A43
0x180167f92  setnz   al
0x180167f95  mov     [rsp+380h+var_30C], eax
0x180167f99  movzx   eax, word ptr [rbp+280h+var_70]
0x180167fa0  mov     word ptr [rbp+280h+var_2F0], ax
0x180167fa4  lea     rax, [rbp+280h+var_80]
0x180167fab  mov     [rsp+380h+var_308], rax
0x180167fb0  lea     rax, [rsp+380h+var_30C]
0x180167fb5  mov     [rsp+380h+var_348], rax
0x180167fba  lea     rax, [rbp+280h+var_2F0]
0x180167fbe  mov     [rsp+380h+var_350], rax
0x180167fc3  lea     rax, [rsp+380h+var_310]
0x180167fc8  mov     [rsp+380h+var_358], rax
0x180167fcd  lea     rax, [rsp+380h+var_308]
0x180167fd2  mov     qword ptr [rsp+380h+var_360], rax
0x180167fd7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180167fdc  xor     r14d, r14d
0x180167fdf  test    rdi, rdi
0x180167fe2  jnz     loc_180168098
0x180167fe8  lea     ebx, [rdi+4]
0x180167feb  lea     rdi, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x180167ff2  lea     rcx, [rbp+280h+var_2B8]; this
0x180167ff6  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180167ffb  mov     rdx, [rbp+280h+var_2C0]; unsigned __int16 *
0x180167fff  lea     r9, [rbp+280h+var_230]; struct _MI_ConstUint32Field *
0x180168003  mov     rcx, [rbp+280h+var_2D8]; unsigned __int16 *
0x180168007  lea     r8, [r15+40h]; struct _MI_ConstStringField *
0x18016800b  mov     [rsp+380h+var_358], r14; unsigned __int16 *
0x180168010  mov     [rsp+380h+var_360], ebx; enum _MI_Result
0x180168014  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180168019  mov     eax, cs:dword_180397B68
0x18016801f  cmp     eax, 5
0x180168022  jbe     loc_1801684BA
0x180168028  mov     rdx, 400000000000h
0x180168032  lea     rcx, dword_180397B68
0x180168039  call    _tlgKeywordOn
0x18016803e  test    al, al
0x180168040  jz      loc_1801684BA
0x180168046  mov     rax, [rbp+280h+var_2B0]
0x18016804a  xor     edx, edx
0x18016804c  sub     rax, [rbp+280h+var_2B8]
0x180168050  imul    rax, 3E8h
0x180168057  mov     [rbp+280h+var_2D8], r14
0x18016805b  div     [rbp+280h+var_2A8]
0x18016805f  mov     [rbp+280h+var_2C0], r14
0x180168063  mov     [rbp+280h+var_2E8], rax
0x180168067  mov     al, [rbp+280h+var_230.exists]
0x18016806a  neg     al
0x18016806c  mov     [rsp+380h+var_308], r14
0x180168071  mov     rax, r15
0x180168074  mov     [rsp+380h+var_310], ebx
0x180168078  sbb     ecx, ecx
0x18016807a  mov     [rbp+280h+var_2FC], r13d
0x18016807e  and     ecx, [rbp+280h+var_230.value]
0x180168081  mov     [rsp+380h+var_30C], ecx
0x180168085  cmp     [rax+48h], r14b
0x180168089  jz      loc_180168432
0x18016808f  mov     rax, [r15+40h]
0x180168093  jmp     loc_180168435
0x180168098  mov     rcx, [r15+40h]; unsigned __int16 *
0x18016809c  lea     r9, [rbp+280h+var_2E0]
0x1801680a0  lea     r8, [rsp+380h+var_310]
0x1801680a5  lea     rdx, [rbp+280h+var_2FC]
0x1801680a9  call    WspUnpackObjectId
0x1801680ae  mov     ebx, eax
0x1801680b0  test    eax, eax
0x1801680b2  jz      short loc_18016810A
0x1801680b4  mov     ecx, cs:dword_180397B68
0x1801680ba  cmp     ecx, 2
0x1801680bd  jbe     loc_180167FEB
0x1801680c3  mov     [rsp+380h+var_310], eax
0x1801680c7  lea     rdx, word_18035A552
  ... truncated ...
```
