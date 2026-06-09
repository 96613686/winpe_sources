# WSP_Partition_Invoke_DeleteObject

- ea: `0x180168f80`
- end: `0x180169597`
- name: `WSP_Partition_Invoke_DeleteObject`
- size: `1559`
- prototype: ``
- caller_count: `0`
- callee_count: `33`
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
- `0x18000cc78`
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
- `0x180119964`
- `0x18012a5e0`
- `0x18012c56c`
- `0x18012ca54`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180168f80`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180168ff7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169059`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169560`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180168ff7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169059`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180169560`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016901d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016901d`

## string_xrefs

- `0x180169113`: `DeletePartition`
- `0x1801693c3`: `DeletePartition`
- `0x18016944b`: `DeletePartition`
- `0x18016906b`: `WSP_Partition_Invoke_DeleteObject`
- `0x1801692eb`: `WSP_Partition_Invoke_DeleteObject`
- `0x180169519`: `WSP_Partition_Invoke_DeleteObject`

## pseudocode

```c
ULONG __fastcall WSP_Partition_Invoke_DeleteObject(
        __int64 a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        void *a7)
{
  int v9; // r15d
  const MI_Char *v10; // rdx
  MI_Type *v11; // r8
  int v12; // r8d
  int v13; // r9d
  unsigned __int16 **v14; // rdi
  enum _MI_Result v15; // ebx
  char IsRemoteInstance; // al
  unsigned __int16 *v17; // rcx
  unsigned int SubsystemType; // ebx
  int SubsystemVersion; // esi
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  enum _MI_Result v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 *v27; // rsi
  __int16 *v28; // rdx
  MI_Uint32 v29; // ebx
  int v30; // r9d
  unsigned __int16 *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  unsigned __int32 v36; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v37; // [rsp+74h] [rbp-8Ch] BYREF
  int IsRemoteRequest; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v40; // [rsp+80h] [rbp-80h] BYREF
  const char *v41; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v43; // [rsp+98h] [rbp-68h] BYREF
  const char *v44; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v45; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v46; // [rsp+B0h] [rbp-50h] BYREF
  const char *v47; // [rsp+B8h] [rbp-48h] BYREF
  const char *v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v51; // [rsp+D8h] [rbp-28h]
  MI_Value value; // [rsp+E8h] [rbp-18h] BYREF
  MI_Instance instance; // [rsp+110h] [rbp+10h] BYREF
  struct _MI_ConstUint32Field v54; // [rsp+150h] [rbp+50h] BYREF
  GUID ActivityId; // [rsp+170h] [rbp+70h] BYREF
  __int128 v56; // [rsp+180h] [rbp+80h] BYREF
  int v57; // [rsp+190h] [rbp+90h]
  GUID v58; // [rsp+198h] [rbp+98h]
  GUID v59; // [rsp+1A8h] [rbp+A8h] BYREF

  v45 = a5;
  memset(&value, 0, sizeof(value));
  v9 = 1;
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v10, v11, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v58 = ActivityId;
  v59 = ActivityId;
  EventActivityIdControl(4u, &v59);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v40 = 624;
    v43 = (unsigned __int16 *)"WSP_Partition_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"WSP_Partition_Invoke_DeleteObject",
      (unsigned int)byte_180360F0B,
      v12,
      v13,
      (__int64)&v43,
      (__int64)&v40);
  }
  v43 = 0;
  v46 = 0;
  v39 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x50u);
  CSmTimer::CSmTimer((CSmTimer *)&v49);
  CSmTimer::Start((CSmTimer *)&v49);
  v14 = (unsigned __int16 **)&a6[4];
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !a6[4].exists || !(unsigned __int8)WspIsRemoteInstance(*v14) )
    v9 = 0;
  v40 = 0;
  v15 = (unsigned int)WspProviderEnter(a2);
  if ( v15 == MI_RESULT_OK )
  {
    IsRemoteInstance = WspIsRemoteInstance(*v14);
    v17 = *v14;
    if ( IsRemoteInstance )
    {
      v15 = (unsigned int)WspInvokeRemoteMethod(a2, a4, *v14, v45, a7);
      goto LABEL_36;
    }
    v56 = 0;
    v57 = 0;
    LODWORD(v42) = 0;
    SubsystemType = WspGetSubsystemType(v17);
    SubsystemVersion = _GetSubsystemVersion(&v42);
    WspGetSubsystemInfo(SubsystemType, (struct _SUBSYSTEM_INFO *)&v56);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v36 = SubsystemType;
      v37 = SubsystemVersion != v42;
      LOWORD(v42) = v57;
      v41 = (const char *)&v56;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)&byte_18036171F,
        v21,
        v22,
        (__int64)&v41,
        (__int64)&v36,
        (__int64)&v42,
        (__int64)&v37);
    }
    v23 = (unsigned int)WspUnpackObjectId(*v14, &v39, &v36, &v43);
    v27 = v43;
    v15 = v23;
    if ( v23 )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_29;
      v37 = 654;
      v28 = word_180361892;
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &WSP_Partition_DeleteObject_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_29;
        v37 = 662;
        v28 = &word_1803611BE;
      }
      else
      {
        if ( v39 )
        {
          v29 = PmcDeletePartition(v27);
          if ( !v29 && (unsigned int)PmUnpackPartitionKey(v27, &v46, 0) )
            PmcRefreshDisk(v46);
        }
        else
        {
          v29 = PmDeletePartition(v27);
        }
        v54.value = v29;
        v54.exists = 1;
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 == MI_RESULT_OK || (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_29;
        v37 = 698;
        v28 = &word_180360E3E;
      }
    }
    v41 = "WSP_Partition_Invoke_DeleteObject";
    v36 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v24,
      (_DWORD)v28,
      v25,
      v26,
      (__int64)&v41,
      (__int64)&v37,
      (__int64)&v36);
LABEL_29:
    SmLogOnMethodFailure(a4, v45, a6 + 4, &v54, v15, 0);
    CSmTimer::Stop((CSmTimer *)&v49);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v41 = 0;
      v45 = 0;
      v42 = 1000 * (v50 - v49) / v51;
      v43 = 0;
      v36 = v15;
      v39 = v9;
      v37 = v54.exists != 0 ? v54.value : 0;
      if ( a6[4].exists )
        v31 = *v14;
      else
        v31 = 0;
      v47 = (const char *)v31;
      v48 = "DeletePartition";
      v44 = "WspPartition";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v54.exists != 0 ? v54.value : 0,
        (unsigned int)&unk_180362008,
        0,
        v30,
        (__int64)&v44,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&v39,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v45,
        (__int64)&v41);
    }
    WspFreeString(v27);
    SmFreeString(&v46);
    MI_Instance_Destruct(&instance);
  }
LABEL_36:
  MI_Context_PostResult_0(a2, v15);
  WspProviderExit(v40);
  if ( IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)&v49);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        IsRemoteRequest = v9;
        v48 = "DeletePartition";
        v44 = (const char *)(1000 * (v50 - v49) / v51);
        v47 = "WspPartition";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v32,
          (unsigned int)&unk_180361DC8,
          v33,
          v34,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&IsRemoteRequest,
          (__int64)&v44);
      }
    }
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    IsRemoteRequest = 746;
    v44 = "WSP_Partition_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)word_180361AAA,
      v33,
      v34,
      (__int64)&v44,
      (__int64)&IsRemoteRequest);
  }
  CSmTimer::~CSmTimer((CSmTimer *)&v49);
  return EventActivityIdControl(4u, &v59);
}

```

## disassembly

```asm
0x180168f80  mov     [rsp-8+arg_0], rbx
0x180168f85  push    rbp
0x180168f86  push    rsi
0x180168f87  push    rdi
0x180168f88  push    r12
0x180168f8a  push    r13
0x180168f8c  push    r14
0x180168f8e  push    r15
0x180168f90  lea     rbp, [rsp-0C0h]
0x180168f98  sub     rsp, 1C0h
0x180168f9f  mov     rax, cs:__security_cookie
0x180168fa6  xor     rax, rsp
0x180168fa9  mov     [rbp+0F0h+var_38], rax
0x180168fb0  mov     rax, [rbp+0F0h+arg_20]
0x180168fb7  xorps   xmm0, xmm0
0x180168fba  mov     r13, [rbp+0F0h+arg_28]
0x180168fc1  mov     r14, rdx
0x180168fc4  mov     rsi, [rbp+0F0h+arg_30]
0x180168fcb  lea     rdx, [rbp+0F0h+ActivityId]; ActivityId
0x180168fcf  mov     [rbp+0F0h+var_148], rax
0x180168fd3  mov     r12, r9
0x180168fd6  xor     eax, eax
0x180168fd8  movups  xmmword ptr [rbp+0F0h+value], xmm0
0x180168fdc  mov     qword ptr [rbp+0F0h+value+20h], rax
0x180168fe0  movups  xmmword ptr [rbp+0F0h+value+10h], xmm0
0x180168fe4  lea     r15d, [rax+1]
0x180168fe8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180168fef  mov     ecx, r15d; ControlCode
0x180168ff2  movdqu  xmmword ptr [rbp+0F0h+ActivityId.Data1], xmm0
0x180168ff7  call    cs:__imp_EventActivityIdControl
0x180168ffe  nop     dword ptr [rax+rax+00h]
0x180169003  lea     r9, [rbp+0F0h+value]; value
0x180169007  mov     rcx, r14; context
0x18016900a  call    MI_Context_GetCustomOption_1
0x18016900f  xor     ebx, ebx
0x180169011  test    eax, eax
0x180169013  jnz     short loc_180169029
0x180169015  mov     rcx, qword ptr [rbp+0F0h+value]; lpsz
0x180169019  lea     rdx, [rbp+0F0h+ActivityId]; pclsid
0x18016901d  call    cs:__imp_CLSIDFromString
0x180169024  nop     dword ptr [rax+rax+00h]
0x180169029  mov     rcx, qword ptr [rbp+0F0h+ActivityId.Data1]
0x18016902d  lea     rdx, [rbp+0F0h+var_48]; ActivityId
0x180169034  mov     rax, qword ptr [rbp+0F0h+ActivityId.Data4]
0x180169038  mov     [rbp+0F0h+var_58], rcx
0x18016903f  mov     qword ptr [rbp+0F0h+var_48.Data1], rcx
0x180169046  mov     ecx, 4; ControlCode
0x18016904b  mov     [rbp+0F0h+var_50], rax
0x180169052  mov     qword ptr [rbp+0F0h+var_48.Data4], rax
0x180169059  call    cs:__imp_EventActivityIdControl
0x180169060  nop     dword ptr [rax+rax+00h]
0x180169065  mov     eax, cs:dword_18039EB68
0x18016906b  lea     rcx, aWspPartitionIn_2; "WSP_Partition_Invoke_DeleteObject"
0x180169072  cmp     eax, 5
0x180169075  jbe     short loc_1801690A0
0x180169077  lea     rax, [rbp+0F0h+var_170]
0x18016907b  mov     [rbp+0F0h+var_170], 270h
0x180169082  mov     [rsp+1F0h+var_1C8], rax
0x180169087  lea     rdx, byte_180360F0B
0x18016908e  lea     rax, [rbp+0F0h+var_158]
0x180169092  mov     [rbp+0F0h+var_158], rcx
0x180169096  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18016909b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801690a0  xor     edx, edx; Val
0x1801690a2  mov     [rbp+0F0h+var_158], rbx
0x1801690a6  lea     rcx, [rbp+0F0h+instance.classDecl]; void *
0x1801690aa  mov     [rbp+0F0h+var_140], rbx
0x1801690ae  mov     [rsp+1F0h+var_174], ebx
0x1801690b2  mov     [rbp+0F0h+instance.ft], rbx
0x1801690b6  lea     r8d, [rdx+50h]; Size
0x1801690ba  call    memset_0
0x1801690bf  lea     rcx, [rbp+0F0h+var_128]; this
0x1801690c3  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801690c8  lea     rcx, [rbp+0F0h+var_128]; this
0x1801690cc  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801690d1  mov     rcx, r14; context
0x1801690d4  call    WspIsRemoteRequest
0x1801690d9  lea     rdi, [r13+40h]
0x1801690dd  mov     [rsp+1F0h+var_178], eax
0x1801690e1  cmp     [rdi+8], bl
0x1801690e4  jz      short loc_1801690F2
0x1801690e6  mov     rcx, [rdi]; unsigned __int16 *
0x1801690e9  call    WspIsRemoteInstance
0x1801690ee  test    al, al
0x1801690f0  jnz     short loc_1801690F5
0x1801690f2  mov     r15d, ebx
0x1801690f5  mov     rdx, [rdi]
0x1801690f8  lea     r9, [rbp+0F0h+var_170]
0x1801690fc  mov     r8d, 1
0x180169102  mov     [rbp+0F0h+var_170], ebx
0x180169105  mov     rcx, r14; context
0x180169108  call    WspProviderEnter
0x18016910d  mov     ebx, eax
0x18016910f  test    eax, eax
0x180169111  jz      short loc_180169126
0x180169113  lea     rdi, aDeletepartitio; "DeletePartition"
0x18016911a  lea     r12, aWsppartition; "WspPartition"
0x180169121  jmp     loc_18016946C
0x180169126  mov     rcx, [rdi]; unsigned __int16 *
0x180169129  call    WspIsRemoteInstance
0x18016912e  mov     rcx, [rdi]
0x180169131  test    al, al
0x180169133  jz      short loc_180169150
0x180169135  mov     r9, [rbp+0F0h+var_148]; unsigned __int16 *
0x180169139  mov     r8, rcx; unsigned __int16 *
0x18016913c  mov     rcx, r14; struct _MI_Context *
0x18016913f  mov     qword ptr [rsp+1F0h+var_1D0], rsi; void *
0x180169144  mov     rdx, r12; unsigned __int16 *
0x180169147  call    WspInvokeRemoteMethod
0x18016914c  mov     ebx, eax
0x18016914e  jmp     short loc_180169113
0x180169150  xor     eax, eax
0x180169152  xorps   xmm0, xmm0
0x180169155  movups  [rbp+0F0h+var_70], xmm0
0x18016915c  mov     [rbp+0F0h+var_60], eax
0x180169162  mov     dword ptr [rbp+0F0h+var_160], eax
0x180169165  call    WspGetSubsystemType
0x18016916a  lea     rcx, [rbp+0F0h+var_160]
0x18016916e  mov     ebx, eax
0x180169170  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180169175  lea     rdx, [rbp+0F0h+var_70]; struct _SUBSYSTEM_INFO *
0x18016917c  mov     ecx, ebx; unsigned int
0x18016917e  mov     esi, eax
0x180169180  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180169185  mov     ecx, cs:dword_18039EB68
0x18016918b  cmp     ecx, 5
0x18016918e  jbe     short loc_180169202
0x180169190  mov     rdx, 400000000000h
0x18016919a  lea     rcx, dword_18039EB68
0x1801691a1  call    _tlgKeywordOn
0x1801691a6  test    al, al
0x1801691a8  jz      short loc_180169202
0x1801691aa  xor     eax, eax
0x1801691ac  mov     [rsp+1F0h+var_180], ebx
0x1801691b0  cmp     esi, dword ptr [rbp+0F0h+var_160]
0x1801691b3  lea     rdx, byte_18036171F
0x1801691ba  setnz   al
0x1801691bd  mov     [rsp+1F0h+var_17C], eax
0x1801691c1  movzx   eax, word ptr [rbp+0F0h+var_60]
0x1801691c8  mov     word ptr [rbp+0F0h+var_160], ax
0x1801691cc  lea     rax, [rbp+0F0h+var_70]
0x1801691d3  mov     [rbp+0F0h+var_168], rax
0x1801691d7  lea     rax, [rsp+1F0h+var_17C]
0x1801691dc  mov     [rsp+1F0h+var_1B8], rax
0x1801691e1  lea     rax, [rbp+0F0h+var_160]
0x1801691e5  mov     [rsp+1F0h+var_1C0], rax
0x1801691ea  lea     rax, [rsp+1F0h+var_180]
0x1801691ef  mov     [rsp+1F0h+var_1C8], rax
0x1801691f4  lea     rax, [rbp+0F0h+var_168]
0x1801691f8  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x1801691fd  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180169202  mov     rcx, [rdi]; unsigned __int16 *
0x180169205  lea     r9, [rbp+0F0h+var_158]
0x180169209  lea     r8, [rsp+1F0h+var_180]
0x18016920e  lea     rdx, [rsp+1F0h+var_174]
0x180169213  call    WspUnpackObjectId
0x180169218  mov     rsi, [rbp+0F0h+var_158]
0x18016921c  mov     ebx, eax
0x18016921e  test    eax, eax
0x180169220  jz      short loc_180169245
0x180169222  mov     eax, cs:dword_18039EB68
0x180169228  cmp     eax, 2
0x18016922b  jbe     loc_18016931C
0x180169231  mov     [rsp+1F0h+var_17C], 28Eh
0x180169239  lea     rdx, word_180361892
0x180169240  jmp     loc_1801692EB
0x180169245  lea     r8, [rbp+0F0h+instance]; instance
0x180169249  mov     rcx, r14; context
0x18016924c  lea     rdx, WSP_Partition_DeleteObject_rtti; methodDecl
0x180169253  call    MI_Context_ConstructParameters
0x180169258  mov     ebx, eax
0x18016925a  test    eax, eax
0x18016925c  jz      short loc_18016927E
0x18016925e  mov     eax, cs:dword_18039EB68
0x180169264  cmp     eax, 2
0x180169267  jbe     loc_18016931C
0x18016926d  mov     [rsp+1F0h+var_17C], 296h
0x180169275  lea     rdx, word_1803611BE
0x18016927c  jmp     short loc_1801692EB
0x18016927e  cmp     [rsp+1F0h+var_174], 0
0x180169283  mov     rcx, rsi
0x180169286  jnz     short loc_180169291
0x180169288  call    ?PmDeletePartition@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmDeletePartition(ushort const *)
0x18016928d  mov     ebx, eax
0x18016928f  jmp     short loc_1801692B8
0x180169291  call    ?PmcDeletePartition@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmcDeletePartition(ushort const *)
0x180169296  mov     ebx, eax
0x180169298  test    eax, eax
0x18016929a  jnz     short loc_1801692B8
0x18016929c  xor     r8d, r8d; unsigned __int64 *
0x18016929f  lea     rdx, [rbp+0F0h+var_140]; unsigned __int16 **
0x1801692a3  mov     rcx, rsi; unsigned __int16 *
0x1801692a6  call    ?PmUnpackPartitionKey@@YAHPEBGPEAPEAGPEA_K@Z; PmUnpackPartitionKey(ushort const *,ushort * *,unsigned __int64 *)
0x1801692ab  test    eax, eax
0x1801692ad  jz      short loc_1801692B8
0x1801692af  mov     rcx, [rbp+0F0h+var_140]
0x1801692b3  call    ?PmcRefreshDisk@@YA?AW4SM_RETURN_CODE@@PEBG@Z; PmcRefreshDisk(ushort const *)
0x1801692b8  lea     rdx, [rbp+0F0h+instance]
0x1801692bc  mov     [rbp+0F0h+var_A0.value], ebx
0x1801692bf  mov     rcx, r14; self
0x1801692c2  mov     [rbp+0F0h+var_A0.exists], 1
0x1801692c6  call    MI_Instance_Destruct
0x1801692cb  mov     ebx, eax
0x1801692cd  test    eax, eax
0x1801692cf  jz      short loc_18016931C
0x1801692d1  mov     eax, cs:dword_18039EB68
0x1801692d7  cmp     eax, 2
0x1801692da  jbe     short loc_18016931C
0x1801692dc  mov     [rsp+1F0h+var_17C], 2BAh
0x1801692e4  lea     rdx, word_180360E3E
0x1801692eb  lea     rax, aWspPartitionIn_2; "WSP_Partition_Invoke_DeleteObject"
0x1801692f2  mov     [rbp+0F0h+var_168], rax
0x1801692f6  lea     rax, [rsp+1F0h+var_180]
0x1801692fb  mov     [rsp+1F0h+var_1C0], rax
0x180169300  lea     rax, [rsp+1F0h+var_17C]
0x180169305  mov     [rsp+1F0h+var_1C8], rax
0x18016930a  lea     rax, [rbp+0F0h+var_168]
0x18016930e  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x180169313  mov     [rsp+1F0h+var_180], ebx
0x180169317  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016931c  mov     rdx, [rbp+0F0h+var_148]; unsigned __int16 *
0x180169320  lea     r9, [rbp+0F0h+var_A0]; struct _MI_ConstUint32Field *
0x180169324  mov     [rsp+1F0h+var_1C8], 0; unsigned __int16 *
0x18016932d  mov     r8, rdi; struct _MI_ConstStringField *
0x180169330  mov     rcx, r12; unsigned __int16 *
0x180169333  mov     [rsp+1F0h+var_1D0], ebx; enum _MI_Result
0x180169337  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18016933c  lea     rcx, [rbp+0F0h+var_128]; this
0x180169340  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180169345  mov     eax, cs:dword_18039EB68
0x18016934b  cmp     eax, 5
0x18016934e  jbe     loc_180169444
0x180169354  mov     rdx, 400000000000h
0x18016935e  lea     rcx, dword_18039EB68
0x180169365  call    _tlgKeywordOn
0x18016936a  xor     r8d, r8d
0x18016936d  test    al, al
0x18016936f  jz      loc_180169444
0x180169375  mov     rax, [rbp+0F0h+var_120]
0x180169379  xor     edx, edx
0x18016937b  sub     rax, [rbp+0F0h+var_128]
0x18016937f  imul    rax, 3E8h
0x180169386  mov     [rbp+0F0h+var_168], r8
0x18016938a  div     [rbp+0F0h+var_118]
0x18016938e  mov     [rbp+0F0h+var_148], r8
0x180169392  mov     [rbp+0F0h+var_160], rax
0x180169396  mov     al, [rbp+0F0h+var_A0.exists]
0x180169399  neg     al
0x18016939b  mov     [rbp+0F0h+var_158], r8
0x18016939f  mov     [rsp+1F0h+var_180], ebx
0x1801693a3  sbb     ecx, ecx
0x1801693a5  mov     [rsp+1F0h+var_174], r15d
0x1801693aa  and     ecx, [rbp+0F0h+var_A0.value]
0x1801693ad  mov     [rsp+1F0h+var_17C], ecx
0x1801693b1  cmp     [r13+48h], r8b
0x1801693b5  jz      short loc_1801693BC
0x1801693b7  mov     rax, [rdi]
0x1801693ba  jmp     short loc_1801693BF
0x1801693bc  mov     rax, r8
0x1801693bf  mov     [rbp+0F0h+var_138], rax
0x1801693c3  lea     rdi, aDeletepartitio; "DeletePartition"
0x1801693ca  lea     rax, [rbp+0F0h+var_168]
0x1801693ce  mov     [rbp+0F0h+var_130], rdi
0x1801693d2  mov     [rsp+1F0h+var_188], rax
0x1801693d7  lea     r12, aWsppartition; "WspPartition"
0x1801693de  lea     rax, [rbp+0F0h+var_148]
0x1801693e2  mov     [rbp+0F0h+var_150], r12
0x1801693e6  mov     [rsp+1F0h+var_190], rax
0x1801693eb  lea     rdx, unk_180362008
0x1801693f2  lea     rax, [rbp+0F0h+var_158]
0x1801693f6  mov     [rsp+1F0h+var_198], rax
0x1801693fb  lea     rax, [rbp+0F0h+var_160]
0x1801693ff  mov     [rsp+1F0h+var_1A0], rax
0x180169404  lea     rax, [rsp+1F0h+var_180]
0x180169409  mov     [rsp+1F0h+var_1A8], rax
0x18016940e  lea     rax, [rsp+1F0h+var_17C]
0x180169413  mov     [rsp+1F0h+var_1B0], rax
0x180169418  lea     rax, [rsp+1F0h+var_174]
0x18016941d  mov     [rsp+1F0h+var_1B8], rax
0x180169422  lea     rax, [rbp+0F0h+var_138]
0x180169426  mov     [rsp+1F0h+var_1C0], rax
0x18016942b  lea     rax, [rbp+0F0h+var_130]
0x18016942f  mov     [rsp+1F0h+var_1C8], rax
0x180169434  lea     rax, [rbp+0F0h+var_150]
0x180169438  mov     qword ptr [rsp+1F0h+var_1D0], rax
0x18016943d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180169442  jmp     short loc_180169452
0x180169444  lea     r12, aWsppartition; "WspPartition"
0x18016944b  lea     rdi, aDeletepartitio; "DeletePartition"
0x180169452  mov     rcx, rsi
0x180169455  call    WspFreeString
0x18016945a  lea     rcx, [rbp+0F0h+var_140]; unsigned __int16 **
0x18016945e  call    ?SmFreeString@@YAXAEAPEAG@Z; SmFreeString(ushort * &)
0x180169463  lea     rcx, [rbp+0F0h+instance]; self
0x180169467  call    MI_Instance_Destruct
0x18016946c  mov     edx, ebx; result
0x18016946e  mov     rcx, r14; context
0x180169471  call    MI_Context_PostResult_0
0x180169476  mov     ecx, [rbp+0F0h+var_170]
0x180169479  call    WspProviderExit
  ... truncated ...
```
