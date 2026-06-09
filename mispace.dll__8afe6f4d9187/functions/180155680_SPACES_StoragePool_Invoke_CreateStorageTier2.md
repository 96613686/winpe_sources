# SPACES_StoragePool_Invoke_CreateStorageTier2

- ea: `0x180155680`
- end: `0x180155c97`
- name: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- size: `1559`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800045d0`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000c704`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180015b40`
- `0x180015c60`
- `0x1800175f0`
- `0x18001a5e4`
- `0x18001afd0`
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x180155680`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801556fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015575c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155c67`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801556fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015575c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155c67`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180155720`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180155720`

## string_xrefs

- `0x180155b6f`: `CreateStorageTier`
- `0x180155768`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x1801558a3`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x1801559d8`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x180155a07`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x180155a1c`: `SPACES_StoragePool_Invoke_CreateStorageTier2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateStorageTier2(
        CSpProvider **a1,
        MI_Context *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        const struct _MI_ConstStringField *a6,
        __int64 a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r15d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int16 *v20; // rdx
  const char **v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rax
  const MI_Char *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned __int16 *v31; // [rsp+28h] [rbp-D8h]
  const char *v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v34; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v35; // [rsp+80h] [rbp-80h] BYREF
  const char *v36; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v37; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+98h] [rbp-68h]
  const char *v39; // [rsp+A0h] [rbp-60h] BYREF
  const char *v40; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v41; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v42; // [rsp+B8h] [rbp-48h] BYREF
  const char *v43; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v44; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v45[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v46; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v47; // [rsp+100h] [rbp+0h]
  struct _MI_Instance v48; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v51; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v52; // [rsp+228h] [rbp+128h]
  char v53; // [rsp+230h] [rbp+130h]
  struct _MI_Instance *v54; // [rsp+238h] [rbp+138h]
  char v55; // [rsp+240h] [rbp+140h]
  GUID ActivityId; // [rsp+260h] [rbp+160h] BYREF
  GUID v57; // [rsp+270h] [rbp+170h]
  GUID v58; // [rsp+280h] [rbp+180h] BYREF

  v37 = a4;
  v44 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v57 = ActivityId;
  v58 = ActivityId;
  EventActivityIdControl(4u, &v58);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v33 = 829;
    v32 = "SPACES_StoragePool_Invoke_CreateStorageTier2";
    v31 = (unsigned __int16 *)&v33;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StoragePool_Invoke_CreateStorageTier2",
      (__int64)qword_1803569E0,
      v11,
      v12,
      &v32);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xD0u);
  v46 = 0;
  v47 = 0;
  v35 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  v35 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v45);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v45);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v46) = 11;
    *((_QWORD *)&v46 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v46, &v35, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
      {
LABEL_27:
        MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
        goto LABEL_28;
      }
      v33 = v15;
      v38 = 861;
      v20 = (__int16 *)&dword_1803575DC;
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateStorageTier2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        LODWORD(v41) = v15;
        LODWORD(v42) = 880;
        v20 = (__int16 *)&unk_1803552F0;
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v35 + 48LL))(
                v35,
                720918,
                a2,
                a7,
                &instance,
                v31);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_27;
          v34 = v15;
          LODWORD(v32) = 899;
          v36 = "SPACES_StoragePool_Invoke_CreateStorageTier2";
          v21 = &v36;
          v20 = (__int16 *)byte_180355329;
          goto LABEL_14;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        LODWORD(v43) = v15;
        LODWORD(v36) = 891;
        v20 = (__int16 *)&unk_180356940;
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_27;
      LODWORD(v39) = 7;
      LODWORD(v40) = 872;
      v20 = &word_180355E76;
    }
    v21 = &v32;
    v32 = "SPACES_StoragePool_Invoke_CreateStorageTier2";
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (__int64)v20,
      v18,
      v19,
      v21);
    goto LABEL_27;
  }
LABEL_28:
  SmLogOnMethodFailure(v37, v44, a6 + 4, &v51, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v45);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( v55 )
        {
          v48 = *v54;
          v24 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v24 = 0;
        }
        v37 = v24;
        if ( v53 )
        {
          v48 = *v52;
          v25 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v25 = 0;
        }
        v44 = v25;
        v43 = "StorageTier";
        v42 = (unsigned __int64)(1000LL * (v45[1] - v45[0])) / v45[2];
        LODWORD(v32) = v15;
        v34 = v51.exists != 0 ? v51.value : 0;
        LODWORD(v36) = v13;
        if ( a6[4].exists )
          v26 = a6[4].value;
        else
          v26 = 0;
        v41 = v26;
        v40 = "CreateStorageTier";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (__int64)byte_1803545C5,
          v22,
          v23,
          &v39,
          &v40,
          &v41,
          (__int64)&v36,
          (__int64)&v34,
          (__int64)&v32,
          (__int64)&v42,
          &v43,
          &v44,
          &v37);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v32) = 932;
    v37 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateStorageTier2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)qword_1803544C0,
      v28,
      v29,
      &v37);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v45);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  return EventActivityIdControl(4u, &v58);
}

```

## disassembly

```asm
0x180155680  mov     [rsp-8+arg_10], rbx
0x180155685  push    rbp
0x180155686  push    rsi
0x180155687  push    rdi
0x180155688  push    r12
0x18015568a  push    r13
0x18015568c  push    r14
0x18015568e  push    r15
0x180155690  lea     rbp, [rsp-1A0h]
0x180155698  sub     rsp, 2A0h
0x18015569f  mov     rax, cs:__security_cookie
0x1801556a6  xor     rax, rsp
0x1801556a9  mov     [rbp+1D0h+var_40], rax
0x1801556b0  mov     [rbp+1D0h+var_240], r9
0x1801556b4  mov     rdi, rdx
0x1801556b7  mov     r14, rcx
0x1801556ba  mov     rax, [rbp+1D0h+arg_20]
0x1801556c1  mov     [rbp+1D0h+var_208], rax
0x1801556c5  mov     rsi, [rbp+1D0h+arg_28]
0x1801556cc  mov     r13, [rbp+1D0h+arg_30]
0x1801556d3  xorps   xmm0, xmm0
0x1801556d6  xor     eax, eax
0x1801556d8  movups  xmmword ptr [rbp+1D0h+value], xmm0
0x1801556dc  movups  xmmword ptr [rbp+1D0h+value+10h], xmm0
0x1801556e0  mov     qword ptr [rbp+1D0h+value+20h], rax
0x1801556e4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801556eb  movdqu  xmmword ptr [rbp+1D0h+ActivityId.Data1], xmm0
0x1801556f3  lea     rdx, [rbp+1D0h+ActivityId]; ActivityId
0x1801556fa  lea     ecx, [rax+1]; ControlCode
0x1801556fd  call    cs:__imp_EventActivityIdControl
0x180155703  lea     r9, [rbp+1D0h+value]; value
0x180155707  mov     rcx, rdi; context
0x18015570a  call    MI_Context_GetCustomOption_1
0x18015570f  xor     ebx, ebx
0x180155711  test    eax, eax
0x180155713  jnz     short loc_180155726
0x180155715  lea     rdx, [rbp+1D0h+ActivityId]; pclsid
0x18015571c  mov     rcx, qword ptr [rbp+1D0h+value]; lpsz
0x180155720  call    cs:__imp_CLSIDFromString
0x180155726  mov     rcx, qword ptr [rbp+1D0h+ActivityId.Data1]
0x18015572d  mov     [rbp+1D0h+var_60], rcx
0x180155734  mov     rax, qword ptr [rbp+1D0h+ActivityId.Data4]
0x18015573b  mov     [rbp+1D0h+var_58], rax
0x180155742  mov     qword ptr [rbp+1D0h+var_50.Data1], rcx
0x180155749  mov     qword ptr [rbp+1D0h+var_50.Data4], rax
0x180155750  lea     rdx, [rbp+1D0h+var_50]; ActivityId
0x180155757  mov     ecx, 4; ControlCode
0x18015575c  call    cs:__imp_EventActivityIdControl
0x180155762  mov     eax, cs:dword_180397B68
0x180155768  lea     rcx, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x18015576f  cmp     eax, 5
0x180155772  jbe     short loc_1801557A1
0x180155774  mov     [rsp+2D0h+var_258], 33Dh
0x18015577c  mov     [rsp+2D0h+var_260], rcx
0x180155781  lea     rax, [rsp+2D0h+var_258]
0x180155786  mov     [rsp+2D0h+var_2A8], rax
0x18015578b  lea     rax, [rsp+2D0h+var_260]
0x180155790  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x180155795  lea     rdx, qword_1803569E0
0x18015579c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801557a1  mov     [rbp+1D0h+instance.ft], rbx
0x1801557a8  xor     edx, edx; Val
0x1801557aa  mov     r8d, 0D0h; Size
0x1801557b0  lea     rcx, [rbp+1D0h+instance.classDecl]; void *
0x1801557b7  call    memset_0
0x1801557bc  xorps   xmm0, xmm0
0x1801557bf  xor     eax, eax
0x1801557c1  movups  [rbp+1D0h+var_1E0], xmm0
0x1801557c5  mov     [rbp+1D0h+var_1D0], rax
0x1801557c9  mov     [rbp+1D0h+var_250], rbx
0x1801557cd  lea     rcx, [rbp+1D0h+var_250]
0x1801557d1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801557d6  mov     [rbp+1D0h+var_250], rbx
0x1801557da  mov     r15d, ebx
0x1801557dd  lea     rcx, [rbp+1D0h+var_200]; this
0x1801557e1  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801557e6  mov     rcx, rdi; context
0x1801557e9  call    WspIsRemoteRequest
0x1801557ee  mov     r12d, eax
0x1801557f1  test    eax, eax
0x1801557f3  jnz     short loc_180155818
0x1801557f5  lea     rcx, [rbp+1D0h+var_200]; this
0x1801557f9  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801557fe  cmp     [rsi+48h], bl
0x180155801  jz      short loc_180155815
0x180155803  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180155807  call    WspIsRemoteInstance
0x18015580c  test    al, al
0x18015580e  lea     r15d, [r12+1]
0x180155813  jnz     short loc_180155818
0x180155815  mov     r15d, ebx
0x180155818  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015581f  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180155824  mov     ebx, eax
0x180155826  test    eax, eax
0x180155828  jnz     loc_180155A1C
0x18015582e  mov     dword ptr [rbp+1D0h+var_1E0], 0Bh
0x180155835  mov     rax, [rsi+40h]
0x180155839  mov     qword ptr [rbp+1D0h+var_1E0+8], rax
0x18015583d  mov     rbx, [r14]
0x180155840  lea     rcx, [rbp+1D0h+var_250]
0x180155844  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180155849  mov     [rsp+2D0h+var_2B0], 1; int
0x180155851  lea     r9, [rbp+1D0h+var_250]; struct ISpWmiObject **
0x180155855  lea     r8, [rbp+1D0h+var_1E0]; struct _SP_OBJECT_ID *
0x180155859  mov     rdx, rdi; context
0x18015585c  mov     rcx, rbx; this
0x18015585f  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180155864  mov     ebx, eax
0x180155866  test    eax, eax
0x180155868  jz      short loc_1801558BE
0x18015586a  mov     eax, cs:dword_180397B68
0x180155870  cmp     eax, 2
0x180155873  jbe     loc_180155A07
0x180155879  mov     [rsp+2D0h+var_258], ebx
0x18015587d  mov     [rbp+1D0h+var_238], 35Dh
0x180155884  lea     rax, [rsp+2D0h+var_258]
0x180155889  mov     [rsp+2D0h+var_2A0], rax
0x18015588e  lea     rax, [rbp+1D0h+var_238]
0x180155892  lea     rdx, dword_1803575DC
0x180155899  mov     [rsp+2D0h+var_2A8], rax
0x18015589e  lea     rax, [rsp+2D0h+var_260]
0x1801558a3  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801558aa  mov     [rsp+2D0h+var_260], r13
0x1801558af  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x1801558b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801558b9  jmp     loc_180155A0E
0x1801558be  mov     r8, [rsi+40h]
0x1801558c2  mov     rdx, rdi
0x1801558c5  mov     rcx, [r14]
0x1801558c8  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x1801558cd  test    eax, eax
0x1801558cf  jnz     short loc_180155903
0x1801558d1  lea     ebx, [rax+7]
0x1801558d4  mov     eax, cs:dword_180397B68
0x1801558da  cmp     eax, 2
0x1801558dd  jbe     loc_180155A07
0x1801558e3  mov     dword ptr [rbp+1D0h+var_230], ebx
0x1801558e6  mov     dword ptr [rbp+1D0h+var_228], 368h
0x1801558ed  lea     rax, [rbp+1D0h+var_230]
0x1801558f1  mov     [rsp+2D0h+var_2A0], rax
0x1801558f6  lea     rax, [rbp+1D0h+var_228]
0x1801558fa  lea     rdx, word_180355E76
0x180155901  jmp     short loc_180155899
0x180155903  lea     r8, [rbp+1D0h+instance]; instance
0x18015590a  lea     rdx, SPACES_StoragePool_CreateStorageTier2_rtti; methodDecl
0x180155911  mov     rcx, rdi; context
0x180155914  call    MI_Context_ConstructParameters
0x180155919  mov     ebx, eax
0x18015591b  test    eax, eax
0x18015591d  jz      short loc_180155951
0x18015591f  mov     eax, cs:dword_180397B68
0x180155925  cmp     eax, 2
0x180155928  jbe     loc_180155A07
0x18015592e  mov     dword ptr [rbp+1D0h+var_220], ebx
0x180155931  mov     dword ptr [rbp+1D0h+var_218], 370h
0x180155938  lea     rax, [rbp+1D0h+var_220]
0x18015593c  mov     [rsp+2D0h+var_2A0], rax
0x180155941  lea     rax, [rbp+1D0h+var_218]
0x180155945  lea     rdx, unk_1803552F0
0x18015594c  jmp     loc_180155899
0x180155951  mov     rcx, [rbp+1D0h+var_250]
0x180155955  mov     rax, [rcx]
0x180155958  lea     rdx, [rbp+1D0h+instance]
0x18015595f  mov     qword ptr [rsp+2D0h+var_2B0], rdx
0x180155964  mov     r9, r13
0x180155967  mov     r8, rdi
0x18015596a  mov     edx, 0B0016h
0x18015596f  mov     rax, [rax+30h]
0x180155973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155978  mov     ebx, eax
0x18015597a  test    eax, eax
0x18015597c  jz      short loc_1801559AC
0x18015597e  mov     eax, cs:dword_180397B68
0x180155984  cmp     eax, 2
0x180155987  jbe     short loc_180155A07
0x180155989  mov     dword ptr [rbp+1D0h+var_210], ebx
0x18015598c  mov     dword ptr [rbp+1D0h+var_248], 37Bh
0x180155993  lea     rax, [rbp+1D0h+var_210]
0x180155997  mov     [rsp+2D0h+var_2A0], rax
0x18015599c  lea     rax, [rbp+1D0h+var_248]
0x1801559a0  lea     rdx, unk_180356940
0x1801559a7  jmp     loc_180155899
0x1801559ac  lea     rdx, [rbp+1D0h+instance]
0x1801559b3  mov     rcx, rdi; self
0x1801559b6  call    MI_Instance_Destruct
0x1801559bb  mov     ebx, eax
0x1801559bd  test    eax, eax
0x1801559bf  jz      short loc_180155A07
0x1801559c1  mov     eax, cs:dword_180397B68
0x1801559c7  cmp     eax, 2
0x1801559ca  jbe     short loc_180155A07
0x1801559cc  mov     [rsp+2D0h+var_254], ebx
0x1801559d0  mov     dword ptr [rsp+2D0h+var_260], 383h
0x1801559d8  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801559df  mov     [rbp+1D0h+var_248], r13
0x1801559e3  lea     rax, [rsp+2D0h+var_254]
0x1801559e8  mov     [rsp+2D0h+var_2A0], rax
0x1801559ed  lea     rax, [rsp+2D0h+var_260]
0x1801559f2  mov     [rsp+2D0h+var_2A8], rax
0x1801559f7  lea     rax, [rbp+1D0h+var_248]
0x1801559fb  lea     rdx, byte_180355329
0x180155a02  jmp     loc_1801558AF
0x180155a07  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180155a0e  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180155a15  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180155a1a  jmp     short loc_180155A23
0x180155a1c  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180155a23  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x180155a27  xor     r14d, r14d
0x180155a2a  mov     [rsp+2D0h+var_2A8], r14; unsigned __int16 *
0x180155a2f  mov     [rsp+2D0h+var_2B0], ebx; enum _MI_Result
0x180155a33  lea     r9, [rbp+1D0h+var_110]; struct _MI_ConstUint32Field *
0x180155a3a  mov     rdx, [rbp+1D0h+var_208]; unsigned __int16 *
0x180155a3e  mov     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x180155a42  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180155a47  test    r12d, r12d
0x180155a4a  jnz     loc_180155BED
0x180155a50  lea     rcx, [rbp+1D0h+var_200]; this
0x180155a54  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180155a59  mov     eax, cs:dword_180397B68
0x180155a5f  cmp     eax, 5
0x180155a62  jbe     loc_180155BED
0x180155a68  mov     rdx, 400000000000h
0x180155a72  lea     rcx, dword_180397B68
0x180155a79  call    _tlgKeywordOn
0x180155a7e  test    al, al
0x180155a80  jz      loc_180155BED
0x180155a86  cmp     [rbp+1D0h+var_90], r14b
0x180155a8d  jz      short loc_180155ACA
0x180155a8f  mov     rax, [rbp+1D0h+var_98]
0x180155a96  movups  xmm0, xmmword ptr [rax]
0x180155a99  movaps  xmmword ptr [rbp+1D0h+var_1C0.ft], xmm0
0x180155a9d  movups  xmm1, xmmword ptr [rax+10h]
0x180155aa1  movaps  xmmword ptr [rbp+1D0h+var_1C0.serverName], xmm1
0x180155aa5  movups  xmm0, xmmword ptr [rax+20h]
0x180155aa9  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved], xmm0
0x180155aad  movups  xmm1, xmmword ptr [rax+30h]
0x180155ab1  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved+10h], xmm1
0x180155ab5  xor     r8d, r8d; unsigned __int16 *
0x180155ab8  lea     rdx, [rbp+1D0h+var_1C0]; struct _MI_Instance
0x180155abc  lea     rcx, name; "ObjectId"
0x180155ac3  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180155ac8  jmp     short loc_180155ACD
0x180155aca  mov     rax, r14
0x180155acd  mov     [rbp+1D0h+var_240], rax
0x180155ad1  cmp     [rbp+1D0h+var_A0], r14b
0x180155ad8  jz      short loc_180155B15
0x180155ada  mov     rax, [rbp+1D0h+var_A8]
0x180155ae1  movups  xmm0, xmmword ptr [rax]
0x180155ae4  movaps  xmmword ptr [rbp+1D0h+var_1C0.ft], xmm0
0x180155ae8  movups  xmm1, xmmword ptr [rax+10h]
0x180155aec  movaps  xmmword ptr [rbp+1D0h+var_1C0.serverName], xmm1
0x180155af0  movups  xmm0, xmmword ptr [rax+20h]
0x180155af4  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved], xmm0
0x180155af8  movups  xmm1, xmmword ptr [rax+30h]
0x180155afc  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved+10h], xmm1
0x180155b00  xor     r8d, r8d; unsigned __int16 *
0x180155b03  lea     rdx, [rbp+1D0h+var_1C0]; struct _MI_Instance
0x180155b07  lea     rcx, name; "ObjectId"
0x180155b0e  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180155b13  jmp     short loc_180155B18
0x180155b15  mov     rax, r14
0x180155b18  mov     [rbp+1D0h+var_208], rax
0x180155b1c  lea     rax, aStoragetier; "StorageTier"
0x180155b23  mov     [rbp+1D0h+var_210], rax
0x180155b27  mov     rax, [rbp+1D0h+var_1F8]
0x180155b2b  sub     rax, [rbp+1D0h+var_200]
0x180155b2f  imul    rax, 3E8h
0x180155b36  xor     edx, edx
0x180155b38  div     [rbp+1D0h+var_1F0]
0x180155b3c  mov     [rbp+1D0h+var_218], rax
0x180155b40  mov     dword ptr [rsp+2D0h+var_260], ebx
0x180155b44  mov     al, [rbp+1D0h+var_110.exists]
0x180155b4a  neg     al
0x180155b4c  sbb     ecx, ecx
0x180155b4e  and     ecx, [rbp+1D0h+var_110.value]
0x180155b54  mov     [rsp+2D0h+var_254], ecx
0x180155b58  mov     dword ptr [rbp+1D0h+var_248], r15d
0x180155b5c  cmp     [rsi+48h], r14b
0x180155b60  jz      short loc_180155B68
0x180155b62  mov     rax, [rsi+40h]
0x180155b66  jmp     short loc_180155B6B
0x180155b68  mov     rax, r14
0x180155b6b  mov     [rbp+1D0h+var_220], rax
0x180155b6f  lea     rax, aCreatestoraget_1; "CreateStorageTier"
0x180155b76  mov     [rbp+1D0h+var_228], rax
0x180155b7a  lea     rax, aStoragepool_0; "StoragePool"
0x180155b81  mov     [rbp+1D0h+var_230], rax
0x180155b85  lea     rax, [rbp+1D0h+var_240]
0x180155b89  mov     [rsp+2D0h+var_268], rax
0x180155b8e  lea     rax, [rbp+1D0h+var_208]
0x180155b92  mov     [rsp+2D0h+var_270], rax
0x180155b97  lea     rax, [rbp+1D0h+var_210]
0x180155b9b  mov     [rsp+2D0h+var_278], rax
0x180155ba0  lea     rax, [rbp+1D0h+var_218]
0x180155ba4  mov     [rsp+2D0h+var_280], rax
0x180155ba9  lea     rax, [rsp+2D0h+var_260]
0x180155bae  mov     [rsp+2D0h+var_288], rax
0x180155bb3  lea     rax, [rsp+2D0h+var_254]
  ... truncated ...
```
