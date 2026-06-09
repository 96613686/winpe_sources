# WSP_Partition_Invoke_SetAttributes

- ea: `0x18016bd00`
- end: `0x18016c662`
- name: `WSP_Partition_Invoke_SetAttributes`
- size: `2402`
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
- `0x18012c064`
- `0x18012deec`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18016bd00`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016bd81`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016bded`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016c62b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016bd81`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016bded`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016c62b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18016c51c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18016c51c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016bdab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016c324`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016bdab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016c324`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_SetAttributes(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        LPCOLESTR *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r13d
  int v12; // r8d
  int v13; // r9d
  void *v14; // r12
  const struct _MI_ConstStringField *v15; // r15
  enum _MI_Result v16; // ebx
  unsigned __int16 *v17; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // esi
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
  int v30; // ecx
  char v31; // al
  int v32; // ecx
  char v33; // al
  int v34; // ecx
  char v35; // al
  int v36; // ecx
  char v37; // al
  int v38; // ecx
  char v39; // al
  int v40; // ecx
  char v41; // al
  __int16 v42; // cx
  char v43; // al
  int v44; // eax
  HRESULT v45; // eax
  MI_Uint32 v46; // eax
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  unsigned __int32 v51; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v52[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h] BYREF
  int v54; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v55; // [rsp+88h] [rbp-78h] BYREF
  const char *v56; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v57; // [rsp+98h] [rbp-68h] BYREF
  const char *v58; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v59; // [rsp+A8h] [rbp-58h] BYREF
  const char *v60; // [rsp+B0h] [rbp-50h] BYREF
  const char *v61; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v62; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v63; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v64; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v65; // [rsp+D8h] [rbp-28h]
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  struct _MI_ConstUint32Field v68; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance self; // [rsp+190h] [rbp+90h] BYREF
  char v70; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int16 v71; // [rsp+2A1h] [rbp+1A1h]
  char v72; // [rsp+2A3h] [rbp+1A3h]
  int v73; // [rsp+2A4h] [rbp+1A4h]
  char v74; // [rsp+2A8h] [rbp+1A8h]
  __int16 v75; // [rsp+2A9h] [rbp+1A9h]
  char v76; // [rsp+2ABh] [rbp+1ABh]
  int v77; // [rsp+2ACh] [rbp+1ACh]
  char v78; // [rsp+2B0h] [rbp+1B0h]
  __int16 v79; // [rsp+2B1h] [rbp+1B1h]
  char v80; // [rsp+2B3h] [rbp+1B3h]
  int v81; // [rsp+2B4h] [rbp+1B4h]
  char v82; // [rsp+2B8h] [rbp+1B8h]
  __int16 v83; // [rsp+2B9h] [rbp+1B9h]
  char v84; // [rsp+2BBh] [rbp+1BBh]
  int v85; // [rsp+2BCh] [rbp+1BCh]
  char v86; // [rsp+2C0h] [rbp+1C0h]
  __int16 v87; // [rsp+2C1h] [rbp+1C1h]
  char v88; // [rsp+2C3h] [rbp+1C3h]
  int v89; // [rsp+2C4h] [rbp+1C4h]
  char v90; // [rsp+2C8h] [rbp+1C8h]
  char v91; // [rsp+2C9h] [rbp+1C9h]
  __int16 v92; // [rsp+2CAh] [rbp+1CAh]
  _BYTE v93[20]; // [rsp+2CCh] [rbp+1CCh] BYREF
  char v94; // [rsp+2E0h] [rbp+1E0h]
  __int16 v95; // [rsp+2E1h] [rbp+1E1h]
  char v96; // [rsp+2E3h] [rbp+1E3h]
  int v97; // [rsp+2E4h] [rbp+1E4h]
  GUID ActivityId; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v99; // [rsp+300h] [rbp+200h] BYREF
  int v100; // [rsp+310h] [rbp+210h]
  GUID pclsid; // [rsp+318h] [rbp+218h] BYREF
  GUID v102; // [rsp+328h] [rbp+228h]
  GUID v103; // [rsp+338h] [rbp+238h] BYREF

  v62 = a5;
  v59 = a4;
  memset(&value, 0, sizeof(value));
  v60 = (const char *)a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v102 = ActivityId;
  v103 = ActivityId;
  EventActivityIdControl(4u, &v103);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v55 = 1763;
    v58 = "WSP_Partition_Invoke_SetAttributes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Partition_Invoke_SetAttributes",
      (unsigned int)qword_180360EB0,
      v12,
      v13,
      (__int64)&v58,
      (__int64)&v55);
  }
  v58 = 0;
  v54 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v70 = 1;
  memset(v93, 0, sizeof(v93));
  v73 = 0;
  v74 = 0;
  pclsid = GUID_NULL;
  v77 = 0;
  v78 = 0;
  v81 = 0;
  v82 = 0;
  v85 = 0;
  v86 = 0;
  v89 = 0;
  v90 = 0;
  v92 = 0;
  v94 = 0;
  v97 = 0;
  CSmTimer::CSmTimer((CSmTimer *)&v63);
  v57 = 0;
  self.ft = 0;
  v14 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v63);
  v15 = (const struct _MI_ConstStringField *)(a6 + 64);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( *(_BYTE *)(a6 + 72) && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v15->value) )
    v11 = 1;
  v55 = 0;
  v16 = (unsigned int)WspProviderEnter(a2);
  if ( v16 == MI_RESULT_OK )
  {
    if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v15->value) )
    {
      v16 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v15->value, v62, a7);
      goto LABEL_73;
    }
    v17 = (unsigned __int16 *)v15->value;
    v100 = 0;
    v99 = 0;
    LODWORD(v56) = 0;
    SubsystemType = WspGetSubsystemType(v17);
    SubsystemVersion = _GetSubsystemVersion(&v56);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v99);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v51 = SubsystemType;
      *(_DWORD *)v52 = SubsystemVersion != (_DWORD)v56;
      LOWORD(v56) = v100;
      *(_QWORD *)&v52[4] = &v99;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)word_180360992,
        v21,
        v22,
        (__int64)&v52[4],
        (__int64)&v51,
        (__int64)&v56,
        (__int64)v52);
    }
    if ( !a7 )
    {
      v16 = MI_RESULT_INVALID_PARAMETER;
      goto LABEL_16;
    }
    v16 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v15->value, &v54, &v51, &v58);
    if ( v16 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_16;
      *(_DWORD *)v52 = 1802;
      v29 = byte_1803614A1;
      goto LABEL_23;
    }
    v16 = MI_Context_ConstructParameters(a2, &WSP_Partition_SetAttributes_rtti, &instance);
    if ( v16 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        *(_DWORD *)v52 = 1810;
        v29 = &byte_18036055F;
LABEL_23:
        *(_QWORD *)&v52[4] = "WSP_Partition_Invoke_SetAttributes";
        v51 = v16;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v26,
          (_DWORD)v29,
          v27,
          v28,
          (__int64)&v52[4],
          (__int64)v52,
          (__int64)&v51);
        goto LABEL_16;
      }
      goto LABEL_16;
    }
    if ( *((_BYTE *)a7 + 79) )
    {
      v30 = *((unsigned __int8 *)a7 + 78);
      v31 = 1;
    }
    else
    {
      v30 = 0;
      v31 = 0;
    }
    v78 = v31;
    v79 = *(_WORD *)&v52[5];
    v80 = v52[7];
    v81 = v30;
    if ( *((_BYTE *)a7 + 82) )
    {
      v32 = *((unsigned __int8 *)a7 + 81);
      v33 = 1;
    }
    else
    {
      v32 = 0;
      v33 = 0;
    }
    v82 = v33;
    v83 = *(_WORD *)&v52[5];
    v84 = v52[7];
    v85 = v32;
    if ( *((_BYTE *)a7 + 85) )
    {
      v34 = *((unsigned __int8 *)a7 + 84);
      v35 = 1;
    }
    else
    {
      v34 = 0;
      v35 = 0;
    }
    v94 = v35;
    v95 = *(_WORD *)&v52[5];
    v96 = v52[7];
    v97 = v34;
    if ( *((_BYTE *)a7 + 73) )
    {
      v36 = *((unsigned __int8 *)a7 + 72);
      v37 = 1;
    }
    else
    {
      v36 = 0;
      v37 = 0;
    }
    v70 = v37;
    v71 = *(_WORD *)&v52[5];
    v72 = v52[7];
    v73 = v36;
    if ( *((_BYTE *)a7 + 88) )
    {
      v38 = *((unsigned __int8 *)a7 + 87);
      v39 = 1;
    }
    else
    {
      v38 = 0;
      v39 = 0;
    }
    v86 = v39;
    v87 = *(_WORD *)&v52[5];
    v88 = v52[7];
    v89 = v38;
    if ( *((_BYTE *)a7 + 76) )
    {
      v40 = *((unsigned __int8 *)a7 + 75);
      v41 = 1;
    }
    else
    {
      v40 = 0;
      v41 = 0;
    }
    v74 = v41;
    v75 = *(_WORD *)&v52[5];
    v76 = v52[7];
    v77 = v40;
    if ( *((_BYTE *)a7 + 92) )
    {
      v42 = *((_WORD *)a7 + 45);
      v43 = 1;
    }
    else
    {
      v42 = 0;
      v43 = 0;
    }
    v90 = v43;
    v91 = BYTE1(IsRemoteRequest);
    v44 = *((unsigned __int8 *)a7 + 104);
    v92 = v42;
    *(_DWORD *)v93 = v44;
    if ( !(_BYTE)v44
      || (v45 = CLSIDFromString(a7[12], &pclsid), *(GUID *)&v93[4] = pclsid, (v46 = (v45 >> 31) & 0xA032) == 0) )
    {
      if ( v54 )
        v46 = PmcSetPartitionAttributes(v58, &v70, &v57);
      else
        v46 = PmSetPartitionAttributes(v58, &v70, &v57);
      v14 = (void *)v57;
    }
    v68.value = v46;
    v68.exists = 1;
    if ( v14 )
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
                               (struct _SUEX_EXTENDEDSTATUS_OBJECT *)v14,
                               (struct _MSFT_StorageExtendedStatus *)&self) )
          {
            *(_QWORD *)&v52[4] = &self;
            v16 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _DWORD))instance.ft->SetElementAt)(
                    &instance,
                    (unsigned int)(v16 + 9),
                    &v52[4],
                    (unsigned int)(v16 + 15),
                    0);
            if ( v16 )
            {
              if ( (unsigned int)dword_18039EB68 > 2 )
              {
                *(_DWORD *)v52 = 1870;
                v29 = byte_180361C21;
                goto LABEL_23;
              }
LABEL_16:
              CSmTimer::Stop((CSmTimer *)&v63);
              SmLogOnMethodFailure(v59, v62, v15, &v68, v16, 0);
              if ( (unsigned int)dword_18039EB68 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
              {
                v59 = 0;
                *(_DWORD *)&v52[8] = 0;
                v57 = 1000 * (v64 - v63) / v65;
                v62 = 0;
                v51 = v16;
                *(_QWORD *)v52 = v68.exists != 0 ? v68.value : 0;
                v54 = v11;
                if ( v60[72] )
                  v25 = (const char *)v15->value;
                else
                  v25 = 0;
                v60 = v25;
                v56 = "SetAttributes";
                v61 = "WspPartition";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  v68.exists != 0 ? v68.value : 0,
                  (unsigned int)word_1803608DA,
                  v23,
                  v24,
                  (__int64)&v61,
                  (__int64)&v56,
                  (__int64)&v60,
                  (__int64)&v54,
                  (__int64)v52,
                  (__int64)&v51,
                  (__int64)&v57,
                  (__int64)&v62,
                  (__int64)&v52[4],
                  (__int64)&v59);
              }
              WspFreeString(v58);
              if ( v14 )
                LocalFree(v14);
              MI_Instance_Destruct(&self);
              MI_Instance_Destruct(&instance);
              goto LABEL_73;
            }
          }
          goto LABEL_65;
        }
      }
      else
      {
        v16 = MI_RESULT_INVALID_PARAMETER;
      }
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        *(_DWORD *)v52 = 1860;
        v29 = (char *)&unk_180360D00;
        goto LABEL_23;
      }
      goto LABEL_16;
    }
LABEL_65:
    v16 = MI_Instance_Destruct((MI_Instance *)a2);
    if ( v16 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_16;
    *(_DWORD *)v52 = 1880;
    v29 = (char *)word_1803617BA;
    goto LABEL_23;
  }
LABEL_73:
  MI_Context_PostResult_0(a2, v16);
  WspProviderExit(v55);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v63);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v11;
        v60 = "SetAttributes";
        v61 = (const char *)(1000 * (v64 - v63) / v65);
        v59 = (unsigned __int16 *)"WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v47,
          (unsigned int)word_180362332,
          v48,
          v49,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&IsRemoteRequest,
          (__int64)&v61);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 1930;
    v61 = "WSP_Partition_Invoke_SetAttributes";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v47,
      (unsigned int)qword_180361C88,
      v48,
      v49,
      (__int64)&v61,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v63);
  return EventActivityIdControl(4u, &v103);
}

```

## disassembly

```asm
0x18016bd00  mov     [rsp-8+arg_0], rbx
0x18016bd05  push    rbp
0x18016bd06  push    rsi
0x18016bd07  push    rdi
0x18016bd08  push    r12
0x18016bd0a  push    r13
0x18016bd0c  push    r14
0x18016bd0e  push    r15
0x18016bd10  lea     rbp, [rsp-250h]
0x18016bd18  sub     rsp, 350h
0x18016bd1f  mov     rax, cs:__security_cookie
0x18016bd26  xor     rax, rsp
0x18016bd29  mov     [rbp+280h+var_38], rax
0x18016bd30  mov     rax, [rbp+280h+arg_20]
0x18016bd37  xorps   xmm0, xmm0
0x18016bd3a  mov     rbx, [rbp+280h+arg_28]
0x18016bd41  mov     r14, rdx
0x18016bd44  mov     rdi, [rbp+280h+arg_30]
0x18016bd4b  lea     rdx, [rbp+280h+ActivityId]; ActivityId
0x18016bd52  mov     [rbp+280h+var_2C0], rax
0x18016bd56  mov     rsi, r9
0x18016bd59  xor     eax, eax
0x18016bd5b  mov     [rbp+280h+var_2D8], r9
0x18016bd5f  movups  xmmword ptr [rbp+280h+value], xmm0
0x18016bd63  mov     [rbp+280h+var_2D0], rbx
0x18016bd67  movups  xmmword ptr [rbp+280h+value+10h], xmm0
0x18016bd6b  lea     ecx, [rax+1]; ControlCode
0x18016bd6e  mov     qword ptr [rbp+280h+value+20h], rax
0x18016bd72  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016bd79  movdqu  xmmword ptr [rbp+280h+ActivityId.Data1], xmm0
0x18016bd81  call    cs:__imp_EventActivityIdControl
0x18016bd88  nop     dword ptr [rax+rax+00h]
0x18016bd8d  lea     r9, [rbp+280h+value]; value
0x18016bd91  mov     rcx, r14; context
0x18016bd94  call    MI_Context_GetCustomOption_1
0x18016bd99  xor     r13d, r13d
0x18016bd9c  test    eax, eax
0x18016bd9e  jnz     short loc_18016BDB7
0x18016bda0  mov     rcx, qword ptr [rbp+280h+value]; lpsz
0x18016bda4  lea     rdx, [rbp+280h+ActivityId]; pclsid
0x18016bdab  call    cs:__imp_CLSIDFromString
0x18016bdb2  nop     dword ptr [rax+rax+00h]
0x18016bdb7  mov     rcx, qword ptr [rbp+280h+ActivityId.Data1]
0x18016bdbe  lea     rdx, [rbp+280h+var_48]; ActivityId
0x18016bdc5  mov     rax, qword ptr [rbp+280h+ActivityId.Data4]
0x18016bdcc  mov     [rbp+280h+var_58], rcx
0x18016bdd3  mov     qword ptr [rbp+280h+var_48.Data1], rcx
0x18016bdda  mov     ecx, 4; ControlCode
0x18016bddf  mov     [rbp+280h+var_50], rax
0x18016bde6  mov     qword ptr [rbp+280h+var_48.Data4], rax
0x18016bded  call    cs:__imp_EventActivityIdControl
0x18016bdf4  nop     dword ptr [rax+rax+00h]
0x18016bdf9  mov     eax, cs:dword_18039EB68
0x18016bdff  lea     rcx, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x18016be06  cmp     eax, 5
0x18016be09  jbe     short loc_18016BE34
0x18016be0b  lea     rax, [rbp+280h+var_2F8]
0x18016be0f  mov     [rbp+280h+var_2F8], 6E3h
0x18016be16  mov     [rsp+380h+var_358], rax
0x18016be1b  lea     rdx, qword_180360EB0
0x18016be22  lea     rax, [rbp+280h+var_2E0]
0x18016be26  mov     [rbp+280h+var_2E0], rcx
0x18016be2a  mov     qword ptr [rsp+380h+var_360], rax
0x18016be2f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016be34  xor     edx, edx; Val
0x18016be36  mov     [rbp+280h+var_2E0], r13
0x18016be3a  lea     rcx, [rbp+280h+instance.classDecl]; void *
0x18016be3e  mov     [rbp+280h+var_2FC], r13d
0x18016be42  mov     [rbp+280h+instance.ft], r13
0x18016be46  lea     r8d, [rdx+78h]; Size
0x18016be4a  call    memset_0
0x18016be4f  xorps   xmm0, xmm0
0x18016be52  mov     [rbp+280h+var_E0], 1
0x18016be59  movups  [rbp+280h+var_B4], xmm0
0x18016be60  xor     eax, eax
0x18016be62  lea     rcx, [rbp+280h+var_2B8]; this
0x18016be66  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016be6d  mov     [rbp+280h+var_DC], r13d
0x18016be74  mov     [rbp+280h+var_D8], r13b
0x18016be7b  movdqu  xmmword ptr [rbp+280h+pclsid.Data1], xmm0
0x18016be83  mov     [rbp+280h+var_D4], r13d
0x18016be8a  mov     [rbp+280h+var_D0], r13b
0x18016be91  mov     [rbp+280h+var_CC], r13d
0x18016be98  mov     [rbp+280h+var_C8], r13b
0x18016be9f  mov     [rbp+280h+var_C4], r13d
0x18016bea6  mov     [rbp+280h+var_C0], r13b
0x18016bead  mov     [rbp+280h+var_BC], r13d
0x18016beb4  mov     [rbp+280h+var_B8], r13b
0x18016bebb  mov     [rbp+280h+var_B6], r13w
0x18016bec3  mov     [rbp+280h+var_A4], eax
0x18016bec9  mov     [rbp+280h+var_A0], r13b
0x18016bed0  mov     [rbp+280h+var_9C], r13d
0x18016bed7  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016bedc  xor     edx, edx; Val
0x18016bede  mov     [rbp+280h+var_2E8], r13
0x18016bee2  mov     r8d, 108h; Size
0x18016bee8  mov     [rbp+280h+self.ft], r13
0x18016beef  lea     rcx, [rbp+280h+self.classDecl]; void *
0x18016bef6  mov     r12, r13
0x18016bef9  call    memset_0
0x18016befe  lea     rcx, [rbp+280h+var_2B8]; this
0x18016bf02  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016bf07  mov     rcx, r14; context
0x18016bf0a  call    WspIsRemoteRequest
0x18016bf0f  lea     r15, [rbx+40h]
0x18016bf13  mov     [rbp+280h+var_300], eax
0x18016bf16  cmp     [r15+8], r13b
0x18016bf1a  jz      short loc_18016BF2E
0x18016bf1c  mov     rcx, [r15]; unsigned __int16 *
0x18016bf1f  call    WspIsRemoteInstance
0x18016bf24  test    al, al
0x18016bf26  jz      short loc_18016BF2E
0x18016bf28  mov     r13d, 1
0x18016bf2e  mov     rdx, [r15]
0x18016bf31  lea     r9, [rbp+280h+var_2F8]
0x18016bf35  mov     r8d, 1
0x18016bf3b  mov     [rbp+280h+var_2F8], r12d
0x18016bf3f  mov     rcx, r14; context
0x18016bf42  call    WspProviderEnter
0x18016bf47  mov     ebx, eax
0x18016bf49  test    eax, eax
0x18016bf4b  jz      short loc_18016BF62
0x18016bf4d  xor     esi, esi
0x18016bf4f  lea     rdi, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x18016bf56  lea     r15, aSetattributes; "SetAttributes"
0x18016bf5d  jmp     loc_18016C53D
0x18016bf62  mov     rcx, [r15]; unsigned __int16 *
0x18016bf65  call    WspIsRemoteInstance
0x18016bf6a  test    al, al
0x18016bf6c  jz      short loc_18016BF89
0x18016bf6e  mov     r9, [rbp+280h+var_2C0]; unsigned __int16 *
0x18016bf72  mov     rdx, rsi; unsigned __int16 *
0x18016bf75  mov     r8, [r15]; unsigned __int16 *
0x18016bf78  mov     rcx, r14; struct _MI_Context *
0x18016bf7b  mov     qword ptr [rsp+380h+var_360], rdi; void *
0x18016bf80  call    WspInvokeRemoteMethod
0x18016bf85  mov     ebx, eax
0x18016bf87  jmp     short loc_18016BF4D
0x18016bf89  mov     rcx, [r15]
0x18016bf8c  xor     eax, eax
0x18016bf8e  xorps   xmm0, xmm0
0x18016bf91  mov     [rbp+280h+var_70], eax
0x18016bf97  movups  [rbp+280h+var_80], xmm0
0x18016bf9e  mov     dword ptr [rbp+280h+var_2F0], eax
0x18016bfa1  call    WspGetSubsystemType
0x18016bfa6  lea     rcx, [rbp+280h+var_2F0]
0x18016bfaa  mov     ebx, eax
0x18016bfac  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18016bfb1  lea     rdx, [rbp+280h+var_80]; struct _SUBSYSTEM_INFO *
0x18016bfb8  mov     ecx, ebx; unsigned int
0x18016bfba  mov     esi, eax
0x18016bfbc  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18016bfc1  mov     ecx, cs:dword_18039EB68
0x18016bfc7  cmp     ecx, 5
0x18016bfca  jbe     short loc_18016C040
0x18016bfcc  mov     rdx, 400000000000h
0x18016bfd6  lea     rcx, dword_18039EB68
0x18016bfdd  call    _tlgKeywordOn
0x18016bfe2  test    al, al
0x18016bfe4  jz      short loc_18016C040
0x18016bfe6  xor     eax, eax
0x18016bfe8  mov     [rsp+380h+var_310], ebx
0x18016bfec  cmp     esi, dword ptr [rbp+280h+var_2F0]
0x18016bfef  lea     rdx, word_180360992
0x18016bff6  setnz   al
0x18016bff9  mov     [rsp+380h+var_30C], eax
0x18016bffd  movzx   eax, word ptr [rbp+280h+var_70]
0x18016c004  mov     word ptr [rbp+280h+var_2F0], ax
0x18016c008  lea     rax, [rbp+280h+var_80]
0x18016c00f  mov     [rsp+380h+var_308], rax
0x18016c014  lea     rax, [rsp+380h+var_30C]
0x18016c019  mov     [rsp+380h+var_348], rax
0x18016c01e  lea     rax, [rbp+280h+var_2F0]
0x18016c022  mov     [rsp+380h+var_350], rax
0x18016c027  lea     rax, [rsp+380h+var_310]
0x18016c02c  mov     [rsp+380h+var_358], rax
0x18016c031  lea     rax, [rsp+380h+var_308]
0x18016c036  mov     qword ptr [rsp+380h+var_360], rax
0x18016c03b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18016c040  xor     esi, esi
0x18016c042  test    rdi, rdi
0x18016c045  jnz     loc_18016C0FA
0x18016c04b  lea     ebx, [rsi+4]
0x18016c04e  lea     rdi, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x18016c055  lea     rcx, [rbp+280h+var_2B8]; this
0x18016c059  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18016c05e  mov     rdx, [rbp+280h+var_2C0]; unsigned __int16 *
0x18016c062  lea     r9, [rbp+280h+var_230]; struct _MI_ConstUint32Field *
0x18016c066  mov     rcx, [rbp+280h+var_2D8]; unsigned __int16 *
0x18016c06a  mov     r8, r15; struct _MI_ConstStringField *
0x18016c06d  mov     [rsp+380h+var_358], rsi; unsigned __int16 *
0x18016c072  mov     [rsp+380h+var_360], ebx; enum _MI_Result
0x18016c076  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18016c07b  mov     eax, cs:dword_18039EB68
0x18016c081  cmp     eax, 5
0x18016c084  jbe     loc_18016C504
0x18016c08a  mov     rdx, 400000000000h
0x18016c094  lea     rcx, dword_18039EB68
0x18016c09b  call    _tlgKeywordOn
0x18016c0a0  test    al, al
0x18016c0a2  jz      loc_18016C504
0x18016c0a8  mov     rax, [rbp+280h+var_2B0]
0x18016c0ac  xor     edx, edx
0x18016c0ae  sub     rax, [rbp+280h+var_2B8]
0x18016c0b2  imul    rax, 3E8h
0x18016c0b9  mov     [rbp+280h+var_2D8], rsi
0x18016c0bd  div     [rbp+280h+var_2A8]
0x18016c0c1  mov     [rsp+380h+var_308], rsi
0x18016c0c6  mov     [rbp+280h+var_2E8], rax
0x18016c0ca  mov     al, [rbp+280h+var_230.exists]
0x18016c0cd  neg     al
0x18016c0cf  mov     [rbp+280h+var_2C0], rsi
0x18016c0d3  mov     rax, [rbp+280h+var_2D0]
0x18016c0d7  sbb     ecx, ecx
0x18016c0d9  mov     [rsp+380h+var_310], ebx
0x18016c0dd  and     ecx, [rbp+280h+var_230.value]
0x18016c0e0  mov     [rsp+380h+var_30C], ecx
0x18016c0e4  mov     [rbp+280h+var_2FC], r13d
0x18016c0e8  cmp     [rax+48h], sil
0x18016c0ec  jz      loc_18016C47C
0x18016c0f2  mov     rax, [r15]
0x18016c0f5  jmp     loc_18016C47F
0x18016c0fa  mov     rcx, [r15]; unsigned __int16 *
0x18016c0fd  lea     r9, [rbp+280h+var_2E0]
0x18016c101  lea     r8, [rsp+380h+var_310]
0x18016c106  lea     rdx, [rbp+280h+var_2FC]
0x18016c10a  call    WspUnpackObjectId
0x18016c10f  mov     ebx, eax
0x18016c111  test    eax, eax
0x18016c113  jz      short loc_18016C16B
0x18016c115  mov     eax, cs:dword_18039EB68
0x18016c11b  cmp     eax, 2
0x18016c11e  jbe     loc_18016C04E
0x18016c124  mov     [rsp+380h+var_30C], 70Ah
0x18016c12c  lea     rdx, byte_1803614A1
0x18016c133  lea     rax, [rsp+380h+var_310]
0x18016c138  mov     [rsp+380h+var_350], rax
0x18016c13d  lea     rdi, aWspPartitionIn_6; "WSP_Partition_Invoke_SetAttributes"
0x18016c144  lea     rax, [rsp+380h+var_30C]
0x18016c149  mov     [rsp+380h+var_308], rdi
0x18016c14e  mov     [rsp+380h+var_358], rax
0x18016c153  lea     rax, [rsp+380h+var_308]
0x18016c158  mov     qword ptr [rsp+380h+var_360], rax
0x18016c15d  mov     [rsp+380h+var_310], ebx
0x18016c161  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016c166  jmp     loc_18016C055
0x18016c16b  lea     r8, [rbp+280h+instance]; instance
0x18016c16f  mov     rcx, r14; context
0x18016c172  lea     rdx, WSP_Partition_SetAttributes_rtti; methodDecl
0x18016c179  call    MI_Context_ConstructParameters
0x18016c17e  mov     ebx, eax
0x18016c180  test    eax, eax
0x18016c182  jz      short loc_18016C1A4
0x18016c184  mov     eax, cs:dword_18039EB68
0x18016c18a  cmp     eax, 2
0x18016c18d  jbe     loc_18016C04E
0x18016c193  mov     [rsp+380h+var_30C], 712h
0x18016c19b  lea     rdx, byte_18036055F
0x18016c1a2  jmp     short loc_18016C133
0x18016c1a4  cmp     [rdi+4Fh], sil
0x18016c1a8  jz      short loc_18016C1B2
0x18016c1aa  movzx   ecx, byte ptr [rdi+4Eh]
0x18016c1ae  mov     al, 1
0x18016c1b0  jmp     short loc_18016C1B7
0x18016c1b2  mov     ecx, esi
0x18016c1b4  mov     al, sil
0x18016c1b7  mov     [rbp+280h+var_D0], al
0x18016c1bd  movzx   eax, word ptr [rsp+380h+var_308+1]
0x18016c1c2  mov     [rbp+280h+var_CF], ax
0x18016c1c9  mov     al, byte ptr [rsp+380h+var_308+3]
0x18016c1cd  mov     [rbp+280h+var_CD], al
0x18016c1d3  mov     [rbp+280h+var_CC], ecx
0x18016c1d9  cmp     [rdi+52h], sil
0x18016c1dd  jz      short loc_18016C1E7
0x18016c1df  movzx   ecx, byte ptr [rdi+51h]
0x18016c1e3  mov     al, 1
0x18016c1e5  jmp     short loc_18016C1EC
0x18016c1e7  mov     ecx, esi
0x18016c1e9  mov     al, sil
0x18016c1ec  mov     [rbp+280h+var_C8], al
0x18016c1f2  movzx   eax, word ptr [rsp+380h+var_308+1]
0x18016c1f7  mov     [rbp+280h+var_C7], ax
0x18016c1fe  mov     al, byte ptr [rsp+380h+var_308+3]
0x18016c202  mov     [rbp+280h+var_C5], al
0x18016c208  mov     [rbp+280h+var_C4], ecx
0x18016c20e  cmp     [rdi+55h], sil
0x18016c212  jz      short loc_18016C21C
0x18016c214  movzx   ecx, byte ptr [rdi+54h]
0x18016c218  mov     al, 1
0x18016c21a  jmp     short loc_18016C221
0x18016c21c  mov     ecx, esi
0x18016c21e  mov     al, sil
0x18016c221  mov     [rbp+280h+var_A0], al
0x18016c227  movzx   eax, word ptr [rsp+380h+var_308+1]
0x18016c22c  mov     [rbp+280h+var_9F], ax
0x18016c233  mov     al, byte ptr [rsp+380h+var_308+3]
0x18016c237  mov     [rbp+280h+var_9D], al
0x18016c23d  mov     [rbp+280h+var_9C], ecx
0x18016c243  cmp     [rdi+49h], sil
0x18016c247  jz      short loc_18016C251
  ... truncated ...
```
