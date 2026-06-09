# WSP_Partition_Invoke_AddAccessPath

- ea: `0x1801687f0`
- end: `0x180168f79`
- name: `WSP_Partition_Invoke_AddAccessPath`
- size: `1929`
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
- `0x18012a008`
- `0x18012c738`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x1801687f0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016886d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801688d9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180168f42`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016886d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801688d9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180168f42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180168e36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180168e36`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180168897`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180168897`

## string_xrefs

- `0x1801689be`: `AddAccessPath`
- `0x180168d95`: `AddAccessPath`
- `0x180168e1d`: `AddAccessPath`
- `0x1801688eb`: `WSP_Partition_Invoke_AddAccessPath`
- `0x1801689b7`: `WSP_Partition_Invoke_AddAccessPath`
- `0x180168abc`: `WSP_Partition_Invoke_AddAccessPath`
- `0x180168baa`: `WSP_Partition_Invoke_AddAccessPath`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_AddAccessPath(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        unsigned __int8 *a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r12d
  int v12; // r8d
  int v13; // r9d
  const struct _MI_ConstStringField *v14; // r15
  enum _MI_Result v15; // ebx
  unsigned __int16 *v16; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // esi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // r8d
  int v23; // r9d
  const MI_Char *v24; // rax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  char *v28; // rdx
  unsigned __int8 v29; // al
  __int64 v30; // r8
  MI_Uint32 v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  unsigned __int32 v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[12]; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+80h] [rbp-80h] BYREF
  int v42; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  const char *v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v48; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v49; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  const char *v51; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v53; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v54; // [rsp+E0h] [rbp-20h]
  MI_Value value; // [rsp+F0h] [rbp-10h] BYREF
  MI_Instance instance; // [rsp+120h] [rbp+20h] BYREF
  struct _MI_ConstUint32Field v57; // [rsp+160h] [rbp+60h] BYREF
  MI_Instance self; // [rsp+190h] [rbp+90h] BYREF
  GUID ActivityId; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v60; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v61; // [rsp+2C0h] [rbp+1C0h]
  GUID v62; // [rsp+2C8h] [rbp+1C8h]
  GUID v63; // [rsp+2D8h] [rbp+1D8h] BYREF

  memset(&value, 0, sizeof(value));
  v48 = a5;
  v49 = a6;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  v11 = 0;
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v62 = ActivityId;
  v63 = ActivityId;
  EventActivityIdControl(4u, &v63);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v43 = 895;
    v46 = "WSP_Partition_Invoke_AddAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Partition_Invoke_AddAccessPath",
      (unsigned int)byte_180360F39,
      v12,
      v13,
      (__int64)&v46,
      (__int64)&v43);
  }
  v46 = 0;
  v42 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x68u);
  CSmTimer::CSmTimer((CSmTimer *)&v52);
  hMem = 0;
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  CSmTimer::Start((CSmTimer *)&v52);
  v14 = a6 + 4;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( a6[4].exists && (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v14->value) )
    v11 = 1;
  v43 = 0;
  v15 = (unsigned int)WspProviderEnter(a2);
  if ( v15 == MI_RESULT_OK )
  {
    if ( (unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)v14->value) )
    {
      v15 = (unsigned int)WspInvokeRemoteMethod(a2, a4, (unsigned __int16 *)v14->value, a5, a7);
      goto LABEL_65;
    }
    v16 = (unsigned __int16 *)v14->value;
    v61 = 0;
    v60 = 0;
    LODWORD(v44) = 0;
    SubsystemType = WspGetSubsystemType(v16);
    SubsystemVersion = _GetSubsystemVersion(&v44);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v60);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v39 = SubsystemType;
      *(_DWORD *)v40 = SubsystemVersion != v44;
      LOWORD(v44) = v61;
      *(_QWORD *)&v40[4] = &v60;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&unk_180361540,
        v20,
        v21,
        (__int64)&v40[4],
        (__int64)&v39,
        (__int64)&v44,
        (__int64)v40);
    }
    if ( !a7 )
    {
      v15 = MI_RESULT_INVALID_PARAMETER;
      goto LABEL_16;
    }
    v15 = (unsigned int)WspUnpackObjectId((unsigned __int16 *)v14->value, &v42, &v39, &v46);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_16;
      *(_DWORD *)v40 = 932;
      v28 = byte_1803605D1;
      goto LABEL_23;
    }
    v15 = MI_Context_ConstructParameters(a2, &WSP_Partition_AddAccessPath_rtti, &instance);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        *(_DWORD *)v40 = 940;
        v28 = byte_1803612F9;
LABEL_23:
        *(_QWORD *)&v40[4] = "WSP_Partition_Invoke_AddAccessPath";
        v39 = v15;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v25,
          (_DWORD)v28,
          v26,
          v27,
          (__int64)&v40[4],
          (__int64)v40,
          (__int64)&v39);
        goto LABEL_16;
      }
      goto LABEL_16;
    }
    LOBYTE(v25) = a7[80];
    v29 = a7[89];
    if ( (_BYTE)v25 )
    {
      if ( !v29 )
      {
LABEL_29:
        if ( v42 )
        {
          if ( (_BYTE)v25 )
            v33 = *((_QWORD *)a7 + 9);
          else
            v33 = 0;
          if ( v29 )
            v34 = a7[88];
          else
            v34 = 0;
          v31 = PmcAddAccessPath(v46, v34, v33, &hMem);
        }
        else
        {
          if ( (_BYTE)v25 )
            v30 = *((_QWORD *)a7 + 9);
          else
            v30 = 0;
          if ( v29 )
            v32 = a7[88];
          else
            v32 = 0;
          v31 = PmAddAccessPath(v46, v32, v30, &hMem);
        }
LABEL_46:
        v57.value = v31;
        v57.exists = 1;
        if ( !hMem )
          goto LABEL_57;
        if ( a2 && a2->ft )
        {
          v15 = ((unsigned int (__fastcall *)(MI_Context *, __int64 *, MI_Instance *))a2->ft->ConstructInstance)(
                  a2,
                  &MSFT_StorageExtendedStatus_rtti,
                  &self);
          if ( v15 == MI_RESULT_OK )
          {
            if ( (unsigned int)CSpExtendedStatus::SuexToMsftExtendedStatus(
                                 (struct _SUEX_EXTENDEDSTATUS_OBJECT *)hMem,
                                 (struct _MSFT_StorageExtendedStatus *)&self) )
            {
              *(_QWORD *)&v40[4] = &self;
              v15 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, _BYTE *, _QWORD, _DWORD))instance.ft->SetElementAt)(
                      &instance,
                      (unsigned int)(v15 + 3),
                      &v40[4],
                      (unsigned int)(v15 + 15),
                      0);
              if ( v15 )
              {
                if ( (unsigned int)dword_18039EB68 > 2 )
                {
                  *(_DWORD *)v40 = 987;
                  v28 = (char *)&unk_1803616B8;
                  goto LABEL_23;
                }
LABEL_16:
                CSmTimer::Stop((CSmTimer *)&v52);
                SmLogOnMethodFailure(a4, v48, v14, &v57, v15, 0);
                if ( (unsigned int)dword_18039EB68 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
                {
                  v48 = 0;
                  *(_DWORD *)&v40[8] = 0;
                  v50 = 1000 * (v53 - v52) / v54;
                  v44 = 0;
                  v39 = v15;
                  *(_QWORD *)v40 = v57.exists != 0 ? v57.value : 0;
                  v42 = v11;
                  if ( v49[72] )
                    v24 = v14->value;
                  else
                    v24 = 0;
                  v49 = v24;
                  v51 = "AddAccessPath";
                  v47 = "WspPartition";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                    v57.exists != 0 ? v57.value : 0,
                    (unsigned int)word_180360762,
                    v22,
                    v23,
                    (__int64)&v47,
                    (__int64)&v51,
                    (__int64)&v49,
                    (__int64)&v42,
                    (__int64)v40,
                    (__int64)&v39,
                    (__int64)&v50,
                    (__int64)&v44,
                    (__int64)&v40[4],
                    (__int64)&v48);
                }
                WspFreeString(v46);
                if ( hMem )
                {
                  LocalFree(hMem);
                  hMem = 0;
                }
                MI_Instance_Destruct(&self);
                MI_Instance_Destruct(&instance);
                goto LABEL_65;
              }
            }
LABEL_57:
            v15 = MI_Instance_Destruct((MI_Instance *)a2);
            if ( v15 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_16;
            *(_DWORD *)v40 = 997;
            v28 = &byte_180361F17;
            goto LABEL_23;
          }
        }
        else
        {
          v15 = MI_RESULT_INVALID_PARAMETER;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          *(_DWORD *)v40 = 977;
          v28 = &byte_180361AD7;
          goto LABEL_23;
        }
        goto LABEL_16;
      }
    }
    else if ( v29 )
    {
      goto LABEL_29;
    }
    v31 = 5;
    goto LABEL_46;
  }
LABEL_65:
  MI_Context_PostResult_0(a2, v15);
  WspProviderExit(v43);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v52);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v11;
        v51 = "AddAccessPath";
        v47 = (const char *)(1000 * (v53 - v52) / v54);
        v50 = (unsigned __int64)"WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v35,
          (unsigned int)&dword_18036087C,
          v36,
          v37,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&IsRemoteRequest,
          (__int64)&v47);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 1047;
    v47 = "WSP_Partition_Invoke_AddAccessPath";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)qword_180360DD8,
      v36,
      v37,
      (__int64)&v47,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v52);
  return EventActivityIdControl(4u, &v63);
}

```

## disassembly

```asm
0x1801687f0  mov     [rsp-8+arg_0], rbx
0x1801687f5  push    rbp
0x1801687f6  push    rsi
0x1801687f7  push    rdi
0x1801687f8  push    r12
0x1801687fa  push    r13
0x1801687fc  push    r14
0x1801687fe  push    r15
0x180168800  lea     rbp, [rsp-1F0h]
0x180168808  sub     rsp, 2F0h
0x18016880f  mov     rax, cs:__security_cookie
0x180168816  xor     rax, rsp
0x180168819  mov     [rbp+220h+var_38], rax
0x180168820  mov     rsi, [rbp+220h+arg_20]
0x180168827  xorps   xmm0, xmm0
0x18016882a  mov     rbx, [rbp+220h+arg_28]
0x180168831  xor     eax, eax
0x180168833  mov     rdi, [rbp+220h+arg_30]
0x18016883a  mov     r14, rdx
0x18016883d  movups  xmmword ptr [rbp+220h+value], xmm0
0x180168841  lea     rdx, [rbp+220h+ActivityId]; ActivityId
0x180168848  mov     r13, r9
0x18016884b  movups  xmmword ptr [rbp+220h+value+10h], xmm0
0x18016884f  lea     ecx, [rax+1]; ControlCode
0x180168852  mov     [rbp+220h+var_270], rsi
0x180168856  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016885d  mov     [rbp+220h+var_268], rbx
0x180168861  mov     qword ptr [rbp+220h+value+20h], rax
0x180168865  movdqu  xmmword ptr [rbp+220h+ActivityId.Data1], xmm0
0x18016886d  call    cs:__imp_EventActivityIdControl
0x180168874  nop     dword ptr [rax+rax+00h]
0x180168879  lea     r9, [rbp+220h+value]; value
0x18016887d  mov     rcx, r14; context
0x180168880  call    MI_Context_GetCustomOption_1
0x180168885  xor     r12d, r12d
0x180168888  test    eax, eax
0x18016888a  jnz     short loc_1801688A3
0x18016888c  mov     rcx, qword ptr [rbp+220h+value]; lpsz
0x180168890  lea     rdx, [rbp+220h+ActivityId]; pclsid
0x180168897  call    cs:__imp_CLSIDFromString
0x18016889e  nop     dword ptr [rax+rax+00h]
0x1801688a3  mov     rcx, qword ptr [rbp+220h+ActivityId.Data1]
0x1801688aa  lea     rdx, [rbp+220h+var_48]; ActivityId
0x1801688b1  mov     rax, qword ptr [rbp+220h+ActivityId.Data4]
0x1801688b8  mov     [rbp+220h+var_58], rcx
0x1801688bf  mov     qword ptr [rbp+220h+var_48.Data1], rcx
0x1801688c6  mov     ecx, 4; ControlCode
0x1801688cb  mov     [rbp+220h+var_50], rax
0x1801688d2  mov     qword ptr [rbp+220h+var_48.Data4], rax
0x1801688d9  call    cs:__imp_EventActivityIdControl
0x1801688e0  nop     dword ptr [rax+rax+00h]
0x1801688e5  mov     eax, cs:dword_18039EB68
0x1801688eb  lea     rcx, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x1801688f2  cmp     eax, 5
0x1801688f5  jbe     short loc_180168920
0x1801688f7  lea     rax, [rbp+220h+var_298]
0x1801688fb  mov     [rbp+220h+var_298], 37Fh
0x180168902  mov     [rsp+320h+var_2F8], rax
0x180168907  lea     rdx, byte_180360F39
0x18016890e  lea     rax, [rbp+220h+var_280]
0x180168912  mov     [rbp+220h+var_280], rcx
0x180168916  mov     qword ptr [rsp+320h+var_300], rax
0x18016891b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180168920  xor     edx, edx; Val
0x180168922  mov     [rbp+220h+var_280], r12
0x180168926  lea     rcx, [rbp+220h+instance.classDecl]; void *
0x18016892a  mov     [rbp+220h+var_29C], r12d
0x18016892e  mov     [rbp+220h+instance.ft], r12
0x180168932  lea     r8d, [rdx+68h]; Size
0x180168936  call    memset_0
0x18016893b  lea     rcx, [rbp+220h+var_250]; this
0x18016893f  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180168944  xor     edx, edx; Val
0x180168946  mov     [rbp+220h+hMem], r12
0x18016894a  mov     r8d, 108h; Size
0x180168950  mov     [rbp+220h+self.ft], r12
0x180168957  lea     rcx, [rbp+220h+self.classDecl]; void *
0x18016895e  call    memset_0
0x180168963  lea     rcx, [rbp+220h+var_250]; this
0x180168967  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016896c  mov     rcx, r14; context
0x18016896f  call    WspIsRemoteRequest
0x180168974  lea     r15, [rbx+40h]
0x180168978  mov     [rbp+220h+var_2A0], eax
0x18016897b  cmp     [r15+8], r12b
0x18016897f  jz      short loc_180168993
0x180168981  mov     rcx, [r15]; unsigned __int16 *
0x180168984  call    WspIsRemoteInstance
0x180168989  test    al, al
0x18016898b  jz      short loc_180168993
0x18016898d  mov     r12d, 1
0x180168993  mov     rdx, [r15]
0x180168996  lea     r9, [rbp+220h+var_298]
0x18016899a  mov     r8d, 1
0x1801689a0  mov     [rbp+220h+var_298], 0
0x1801689a7  mov     rcx, r14; context
0x1801689aa  call    WspProviderEnter
0x1801689af  mov     ebx, eax
0x1801689b1  test    eax, eax
0x1801689b3  jz      short loc_1801689D1
0x1801689b5  xor     esi, esi
0x1801689b7  lea     rdi, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x1801689be  lea     r15, aAddaccesspath_0; "AddAccessPath"
0x1801689c5  lea     r13, aWsppartition; "WspPartition"
0x1801689cc  jmp     loc_180168E5B
0x1801689d1  mov     rcx, [r15]; unsigned __int16 *
0x1801689d4  call    WspIsRemoteInstance
0x1801689d9  test    al, al
0x1801689db  jz      short loc_1801689F7
0x1801689dd  mov     r8, [r15]; unsigned __int16 *
0x1801689e0  mov     r9, rsi; unsigned __int16 *
0x1801689e3  mov     rdx, r13; unsigned __int16 *
0x1801689e6  mov     qword ptr [rsp+320h+var_300], rdi; void *
0x1801689eb  mov     rcx, r14; struct _MI_Context *
0x1801689ee  call    WspInvokeRemoteMethod
0x1801689f3  mov     ebx, eax
0x1801689f5  jmp     short loc_1801689B5
0x1801689f7  mov     rcx, [r15]
0x1801689fa  xor     eax, eax
0x1801689fc  xorps   xmm0, xmm0
0x1801689ff  mov     [rbp+220h+var_60], eax
0x180168a05  movups  [rbp+220h+var_70], xmm0
0x180168a0c  mov     dword ptr [rbp+220h+var_290], eax
0x180168a0f  call    WspGetSubsystemType
0x180168a14  lea     rcx, [rbp+220h+var_290]
0x180168a18  mov     ebx, eax
0x180168a1a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180168a1f  lea     rdx, [rbp+220h+var_70]; struct _SUBSYSTEM_INFO *
0x180168a26  mov     ecx, ebx; unsigned int
0x180168a28  mov     esi, eax
0x180168a2a  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180168a2f  mov     ecx, cs:dword_18039EB68
0x180168a35  cmp     ecx, 5
0x180168a38  jbe     short loc_180168AAE
0x180168a3a  mov     rdx, 400000000000h
0x180168a44  lea     rcx, dword_18039EB68
0x180168a4b  call    _tlgKeywordOn
0x180168a50  test    al, al
0x180168a52  jz      short loc_180168AAE
0x180168a54  xor     eax, eax
0x180168a56  mov     [rsp+320h+var_2B0], ebx
0x180168a5a  cmp     esi, dword ptr [rbp+220h+var_290]
0x180168a5d  lea     rdx, unk_180361540
0x180168a64  setnz   al
0x180168a67  mov     [rsp+320h+var_2AC], eax
0x180168a6b  movzx   eax, word ptr [rbp+220h+var_60]
0x180168a72  mov     word ptr [rbp+220h+var_290], ax
0x180168a76  lea     rax, [rbp+220h+var_70]
0x180168a7d  mov     [rsp+320h+var_2A8], rax
0x180168a82  lea     rax, [rsp+320h+var_2AC]
0x180168a87  mov     [rsp+320h+var_2E8], rax
0x180168a8c  lea     rax, [rbp+220h+var_290]
0x180168a90  mov     [rsp+320h+var_2F0], rax
0x180168a95  lea     rax, [rsp+320h+var_2B0]
0x180168a9a  mov     [rsp+320h+var_2F8], rax
0x180168a9f  lea     rax, [rsp+320h+var_2A8]
0x180168aa4  mov     qword ptr [rsp+320h+var_300], rax
0x180168aa9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180168aae  xor     esi, esi
0x180168ab0  test    rdi, rdi
0x180168ab3  jnz     loc_180168B67
0x180168ab9  lea     ebx, [rsi+4]
0x180168abc  lea     rdi, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x180168ac3  lea     rcx, [rbp+220h+var_250]; this
0x180168ac7  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180168acc  mov     rdx, [rbp+220h+var_270]; unsigned __int16 *
0x180168ad0  lea     r9, [rbp+220h+var_1C0]; struct _MI_ConstUint32Field *
0x180168ad4  mov     r8, r15; struct _MI_ConstStringField *
0x180168ad7  mov     [rsp+320h+var_2F8], rsi; unsigned __int16 *
0x180168adc  mov     rcx, r13; unsigned __int16 *
0x180168adf  mov     [rsp+320h+var_300], ebx; enum _MI_Result
0x180168ae3  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180168ae8  mov     eax, cs:dword_18039EB68
0x180168aee  cmp     eax, 5
0x180168af1  jbe     loc_180168E16
0x180168af7  mov     rdx, 400000000000h
0x180168b01  lea     rcx, dword_18039EB68
0x180168b08  call    _tlgKeywordOn
0x180168b0d  test    al, al
0x180168b0f  jz      loc_180168E16
0x180168b15  mov     rax, [rbp+220h+var_248]
0x180168b19  xor     edx, edx
0x180168b1b  sub     rax, [rbp+220h+var_250]
0x180168b1f  imul    rax, 3E8h
0x180168b26  mov     [rbp+220h+var_270], rsi
0x180168b2a  div     [rbp+220h+var_240]
0x180168b2e  mov     [rsp+320h+var_2A8], rsi
0x180168b33  mov     [rbp+220h+var_260], rax
0x180168b37  mov     al, [rbp+220h+var_1C0.exists]
0x180168b3a  neg     al
0x180168b3c  mov     [rbp+220h+var_290], rsi
0x180168b40  mov     rax, [rbp+220h+var_268]
0x180168b44  sbb     ecx, ecx
0x180168b46  mov     [rsp+320h+var_2B0], ebx
0x180168b4a  and     ecx, [rbp+220h+var_1C0.value]
0x180168b4d  mov     [rsp+320h+var_2AC], ecx
0x180168b51  mov     [rbp+220h+var_29C], r12d
0x180168b55  cmp     [rax+48h], sil
0x180168b59  jz      loc_180168D8E
0x180168b5f  mov     rax, [r15]
0x180168b62  jmp     loc_180168D91
0x180168b67  mov     rcx, [r15]; unsigned __int16 *
0x180168b6a  lea     r9, [rbp+220h+var_280]
0x180168b6e  lea     r8, [rsp+320h+var_2B0]
0x180168b73  lea     rdx, [rbp+220h+var_29C]
0x180168b77  call    WspUnpackObjectId
0x180168b7c  mov     ebx, eax
0x180168b7e  test    eax, eax
0x180168b80  jz      short loc_180168BD8
0x180168b82  mov     eax, cs:dword_18039EB68
0x180168b88  cmp     eax, 2
0x180168b8b  jbe     loc_180168ABC
0x180168b91  mov     [rsp+320h+var_2AC], 3A4h
0x180168b99  lea     rdx, byte_1803605D1
0x180168ba0  lea     rax, [rsp+320h+var_2B0]
0x180168ba5  mov     [rsp+320h+var_2F0], rax
0x180168baa  lea     rdi, aWspPartitionIn_7; "WSP_Partition_Invoke_AddAccessPath"
0x180168bb1  lea     rax, [rsp+320h+var_2AC]
0x180168bb6  mov     [rsp+320h+var_2A8], rdi
0x180168bbb  mov     [rsp+320h+var_2F8], rax
0x180168bc0  lea     rax, [rsp+320h+var_2A8]
0x180168bc5  mov     qword ptr [rsp+320h+var_300], rax
0x180168bca  mov     [rsp+320h+var_2B0], ebx
0x180168bce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180168bd3  jmp     loc_180168AC3
0x180168bd8  lea     r8, [rbp+220h+instance]; instance
0x180168bdc  mov     rcx, r14; context
0x180168bdf  lea     rdx, WSP_Partition_AddAccessPath_rtti; methodDecl
0x180168be6  call    MI_Context_ConstructParameters
0x180168beb  mov     ebx, eax
0x180168bed  test    eax, eax
0x180168bef  jz      short loc_180168C11
0x180168bf1  mov     eax, cs:dword_18039EB68
0x180168bf7  cmp     eax, 2
0x180168bfa  jbe     loc_180168ABC
0x180168c00  mov     [rsp+320h+var_2AC], 3ACh
0x180168c08  lea     rdx, byte_1803612F9
0x180168c0f  jmp     short loc_180168BA0
0x180168c11  mov     cl, [rdi+50h]
0x180168c14  mov     al, [rdi+59h]
0x180168c17  test    cl, cl
0x180168c19  jnz     short loc_180168C2E
0x180168c1b  test    al, al
0x180168c1d  jz      short loc_180168C32
0x180168c1f  cmp     [rbp+220h+var_29C], esi
0x180168c22  jnz     short loc_180168C57
0x180168c24  test    cl, cl
0x180168c26  jz      short loc_180168C39
0x180168c28  mov     r8, [rdi+48h]
0x180168c2c  jmp     short loc_180168C3C
0x180168c2e  test    al, al
0x180168c30  jz      short loc_180168C1F
0x180168c32  mov     eax, 5
0x180168c37  jmp     short loc_180168C7D
0x180168c39  mov     r8, rsi
0x180168c3c  test    al, al
0x180168c3e  jz      short loc_180168C46
0x180168c40  movzx   edx, byte ptr [rdi+58h]
0x180168c44  jmp     short loc_180168C48
0x180168c46  mov     edx, esi
0x180168c48  mov     rcx, [rbp+220h+var_280]
0x180168c4c  lea     r9, [rbp+220h+hMem]
0x180168c50  call    ?PmAddAccessPath@@YA?AW4SM_RETURN_CODE@@PEBGH0PEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; PmAddAccessPath(ushort const *,int,ushort const *,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x180168c55  jmp     short loc_180168C7D
0x180168c57  test    cl, cl
0x180168c59  jz      short loc_180168C61
0x180168c5b  mov     r8, [rdi+48h]
0x180168c5f  jmp     short loc_180168C64
0x180168c61  mov     r8, rsi
0x180168c64  test    al, al
0x180168c66  jz      short loc_180168C6E
0x180168c68  movzx   edx, byte ptr [rdi+58h]
0x180168c6c  jmp     short loc_180168C70
0x180168c6e  mov     edx, esi
0x180168c70  mov     rcx, [rbp+220h+var_280]
0x180168c74  lea     r9, [rbp+220h+hMem]
0x180168c78  call    ?PmcAddAccessPath@@YA?AW4SM_RETURN_CODE@@PEBGH0PEAPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@@Z; PmcAddAccessPath(ushort const *,int,ushort const *,_SUEX_EXTENDEDSTATUS_OBJECT * *)
0x180168c7d  mov     [rbp+220h+var_1C0.value], eax
0x180168c80  mov     [rbp+220h+var_1C0.exists], 1
0x180168c84  cmp     [rbp+220h+hMem], rsi
0x180168c88  jz      loc_180168D55
0x180168c8e  test    r14, r14
0x180168c91  jz      loc_180168D2D
0x180168c97  mov     rax, [r14]
0x180168c9a  test    rax, rax
0x180168c9d  jz      loc_180168D2D
0x180168ca3  mov     rax, [rax+18h]
0x180168ca7  lea     r8, [rbp+220h+self]
0x180168cae  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180168cb5  mov     rcx, r14
0x180168cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168cbd  mov     ebx, eax
0x180168cbf  test    eax, eax
0x180168cc1  jnz     short loc_180168D32
0x180168cc3  mov     rcx, [rbp+220h+hMem]; struct _SUEX_EXTENDEDSTATUS_OBJECT *
0x180168cc7  lea     rdx, [rbp+220h+self]; struct _MSFT_StorageExtendedStatus *
0x180168cce  call    ?SuexToMsftExtendedStatus@CSpExtendedStatus@@SAHPEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAU_MSFT_StorageExtendedStatus@@@Z; CSpExtendedStatus::SuexToMsftExtendedStatus(_SUEX_EXTENDEDSTATUS_OBJECT *,_MSFT_StorageExtendedStatus *)
0x180168cd3  test    eax, eax
0x180168cd5  jz      short loc_180168D55
0x180168cd7  lea     rax, [rbp+220h+self]
  ... truncated ...
```
