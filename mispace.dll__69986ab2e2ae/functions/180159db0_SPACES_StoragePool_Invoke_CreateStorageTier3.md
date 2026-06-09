# SPACES_StoragePool_Invoke_CreateStorageTier3

- ea: `0x180159db0`
- end: `0x18015a3d3`
- name: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- size: `1571`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180004608`
- `0x180006350`
- `0x180006dd4`
- `0x18000b840`
- `0x18000ba50`
- `0x18000c644`
- `0x18000cca4`
- `0x18000ccd4`
- `0x180015ea0`
- `0x180015fc0`
- `0x1800179c0`
- `0x18001aa70`
- `0x18001b4a0`
- `0x180021dcc`
- `0x1800226ac`
- `0x180023e18`
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180159db0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159e2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159e98`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a39c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159e2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159e98`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a39c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159e56`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159e56`

## string_xrefs

- `0x18015a2b4`: `CreateStorageTier`
- `0x180159eaa`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x180159fe5`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x18015a11d`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x18015a14c`: `SPACES_StoragePool_Invoke_CreateStorageTier3`
- `0x18015a161`: `SPACES_StoragePool_Invoke_CreateStorageTier3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateStorageTier3(
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
  int v11; // r8d
  int v12; // r9d
  int v13; // r14d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  const char **v20; // rax
  __int16 *v21; // rdx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // r8d
  int v26; // r9d
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rax
  const MI_Char *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  const char **v34; // [rsp+30h] [rbp-D0h]
  const char *v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v37; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const char *v43; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  const char *v46; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v47; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v48[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  struct _MI_Instance v51; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v54; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v55; // [rsp+260h] [rbp+160h]
  char v56; // [rsp+268h] [rbp+168h]
  struct _MI_Instance *v57; // [rsp+270h] [rbp+170h]
  char v58; // [rsp+278h] [rbp+178h]
  GUID ActivityId; // [rsp+290h] [rbp+190h] BYREF
  GUID v60; // [rsp+2A0h] [rbp+1A0h]
  GUID v61; // [rsp+2B0h] [rbp+1B0h] BYREF

  v40 = a4;
  v47 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v60 = ActivityId;
  v61 = ActivityId;
  EventActivityIdControl(4u, &v61);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v36 = 948;
    v35 = "SPACES_StoragePool_Invoke_CreateStorageTier3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateStorageTier3",
      (unsigned int)&word_18035DC86,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x108u);
  v49 = 0;
  v50 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v48);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v48);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v49) = 11;
    *((_QWORD *)&v49 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v49, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v36 = v15;
        v41 = 980;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = &word_18035CEB6;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateStorageTier3";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (_DWORD)v21,
          v18,
          v19,
          (__int64)&v35,
          (__int64)v20,
          (__int64)v34);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateStorageTier3_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v45) = 999;
          v34 = (const char **)&v44;
          v20 = (const char **)&v45;
          v21 = (__int16 *)&unk_18035D610;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720920,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v35) = 1018;
            v39 = "SPACES_StoragePool_Invoke_CreateStorageTier3";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&unk_18035DE38,
              v23,
              v24,
              (__int64)&v39,
              (__int64)&v35,
              (__int64)&v37);
          }
          goto LABEL_27;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v46) = v15;
          LODWORD(v39) = 1010;
          v34 = &v46;
          v20 = &v39;
          v21 = (__int16 *)byte_18035BB83;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v42) = 7;
        LODWORD(v43) = 991;
        v34 = &v42;
        v20 = &v43;
        v21 = &word_18035B9C6;
        goto LABEL_13;
      }
    }
LABEL_27:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v40, v47, a6 + 4, &v54, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v48);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( v58 )
        {
          v51 = *v57;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v27 = 0;
        }
        v40 = v27;
        if ( v56 )
        {
          v51 = *v55;
          v28 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v28 = 0;
        }
        v47 = v28;
        v46 = "StorageTier";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateStorageTier";
        v42 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)&unk_18035C730,
          v25,
          v26,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v35,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v40);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v35) = 1051;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateStorageTier3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&byte_18035DF3F,
      v31,
      v32,
      (__int64)&v40,
      (__int64)&v35);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v48);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x180159db0  mov     [rsp-8+arg_10], rbx
0x180159db5  push    rbp
0x180159db6  push    rsi
0x180159db7  push    rdi
0x180159db8  push    r12
0x180159dba  push    r13
0x180159dbc  push    r14
0x180159dbe  push    r15
0x180159dc0  lea     rbp, [rsp-1D0h]
0x180159dc8  sub     rsp, 2D0h
0x180159dcf  mov     rax, cs:__security_cookie
0x180159dd6  xor     rax, rsp
0x180159dd9  mov     [rbp+200h+var_40], rax
0x180159de0  mov     [rbp+200h+var_270], r9
0x180159de4  mov     rsi, rdx
0x180159de7  mov     r15, rcx
0x180159dea  mov     rax, [rbp+200h+arg_20]
0x180159df1  mov     [rbp+200h+var_238], rax
0x180159df5  mov     rdi, [rbp+200h+arg_28]
0x180159dfc  mov     r13, [rbp+200h+arg_30]
0x180159e03  xorps   xmm0, xmm0
0x180159e06  xor     eax, eax
0x180159e08  movups  xmmword ptr [rbp+200h+value], xmm0
0x180159e0c  movups  xmmword ptr [rbp+200h+value+10h], xmm0
0x180159e10  mov     qword ptr [rbp+200h+value+20h], rax
0x180159e14  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180159e1b  movdqu  xmmword ptr [rbp+200h+ActivityId.Data1], xmm0
0x180159e23  lea     rdx, [rbp+200h+ActivityId]; ActivityId
0x180159e2a  lea     ecx, [rax+1]; ControlCode
0x180159e2d  call    cs:__imp_EventActivityIdControl
0x180159e34  nop     dword ptr [rax+rax+00h]
0x180159e39  lea     r9, [rbp+200h+value]; value
0x180159e3d  mov     rcx, rsi; context
0x180159e40  call    MI_Context_GetCustomOption_1
0x180159e45  xor     ebx, ebx
0x180159e47  test    eax, eax
0x180159e49  jnz     short loc_180159E62
0x180159e4b  lea     rdx, [rbp+200h+ActivityId]; pclsid
0x180159e52  mov     rcx, qword ptr [rbp+200h+value]; lpsz
0x180159e56  call    cs:__imp_CLSIDFromString
0x180159e5d  nop     dword ptr [rax+rax+00h]
0x180159e62  mov     rcx, qword ptr [rbp+200h+ActivityId.Data1]
0x180159e69  mov     [rbp+200h+var_60], rcx
0x180159e70  mov     rax, qword ptr [rbp+200h+ActivityId.Data4]
0x180159e77  mov     [rbp+200h+var_58], rax
0x180159e7e  mov     qword ptr [rbp+200h+var_50.Data1], rcx
0x180159e85  mov     qword ptr [rbp+200h+var_50.Data4], rax
0x180159e8c  lea     rdx, [rbp+200h+var_50]; ActivityId
0x180159e93  mov     ecx, 4; ControlCode
0x180159e98  call    cs:__imp_EventActivityIdControl
0x180159e9f  nop     dword ptr [rax+rax+00h]
0x180159ea4  mov     eax, cs:dword_18039EB68
0x180159eaa  lea     rcx, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180159eb1  cmp     eax, 5
0x180159eb4  jbe     short loc_180159EE3
0x180159eb6  mov     [rsp+300h+var_288], 3B4h
0x180159ebe  mov     [rsp+300h+var_290], rcx
0x180159ec3  lea     rax, [rsp+300h+var_288]
0x180159ec8  mov     [rsp+300h+var_2D8], rax
0x180159ecd  lea     rax, [rsp+300h+var_290]
0x180159ed2  mov     qword ptr [rsp+300h+var_2E0], rax
0x180159ed7  lea     rdx, word_18035DC86
0x180159ede  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180159ee3  mov     [rbp+200h+instance.ft], rbx
0x180159eea  xor     edx, edx; Val
0x180159eec  mov     r8d, 108h; Size
0x180159ef2  lea     rcx, [rbp+200h+instance.classDecl]; void *
0x180159ef9  call    memset_0
0x180159efe  xorps   xmm0, xmm0
0x180159f01  xor     eax, eax
0x180159f03  movups  [rbp+200h+var_210], xmm0
0x180159f07  mov     [rbp+200h+var_200], rax
0x180159f0b  mov     [rbp+200h+var_280], rbx
0x180159f0f  lea     rcx, [rbp+200h+var_280]
0x180159f13  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180159f18  mov     [rbp+200h+var_280], rbx
0x180159f1c  mov     r14d, ebx
0x180159f1f  lea     rcx, [rbp+200h+var_230]; this
0x180159f23  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180159f28  mov     rcx, rsi; context
0x180159f2b  call    WspIsRemoteRequest
0x180159f30  mov     r12d, eax
0x180159f33  test    eax, eax
0x180159f35  jnz     short loc_180159F5A
0x180159f37  lea     rcx, [rbp+200h+var_230]; this
0x180159f3b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180159f40  cmp     [rdi+48h], bl
0x180159f43  jz      short loc_180159F57
0x180159f45  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180159f49  call    WspIsRemoteInstance
0x180159f4e  test    al, al
0x180159f50  lea     r14d, [r12+1]
0x180159f55  jnz     short loc_180159F5A
0x180159f57  mov     r14d, ebx
0x180159f5a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180159f61  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180159f66  mov     ebx, eax
0x180159f68  test    eax, eax
0x180159f6a  jnz     loc_18015A161
0x180159f70  mov     dword ptr [rbp+200h+var_210], 0Bh
0x180159f77  mov     rax, [rdi+40h]
0x180159f7b  mov     qword ptr [rbp+200h+var_210+8], rax
0x180159f7f  mov     rbx, [r15]
0x180159f82  lea     rcx, [rbp+200h+var_280]
0x180159f86  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180159f8b  mov     [rsp+300h+var_2E0], 1; int
0x180159f93  lea     r9, [rbp+200h+var_280]; struct ISpWmiObject **
0x180159f97  lea     r8, [rbp+200h+var_210]; struct _SP_OBJECT_ID *
0x180159f9b  mov     rdx, rsi; context
0x180159f9e  mov     rcx, rbx; this
0x180159fa1  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180159fa6  mov     ebx, eax
0x180159fa8  test    eax, eax
0x180159faa  jz      short loc_18015A000
0x180159fac  mov     eax, cs:dword_18039EB68
0x180159fb2  cmp     eax, 2
0x180159fb5  jbe     loc_18015A14C
0x180159fbb  mov     [rsp+300h+var_288], ebx
0x180159fbf  mov     [rbp+200h+var_268], 3D4h
0x180159fc6  lea     rax, [rsp+300h+var_288]
0x180159fcb  mov     [rsp+300h+var_2D0], rax
0x180159fd0  lea     rax, [rbp+200h+var_268]
0x180159fd4  lea     rdx, word_18035CEB6
0x180159fdb  mov     [rsp+300h+var_2D8], rax
0x180159fe0  lea     rax, [rsp+300h+var_290]
0x180159fe5  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180159fec  mov     [rsp+300h+var_290], r13
0x180159ff1  mov     qword ptr [rsp+300h+var_2E0], rax
0x180159ff6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180159ffb  jmp     loc_18015A153
0x18015a000  mov     r8, [rdi+40h]
0x18015a004  mov     rdx, rsi
0x18015a007  mov     rcx, [r15]
0x18015a00a  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18015a00f  cmp     eax, 3
0x18015a012  jnb     short loc_18015A048
0x18015a014  mov     ebx, 7
0x18015a019  mov     eax, cs:dword_18039EB68
0x18015a01f  cmp     eax, 2
0x18015a022  jbe     loc_18015A14C
0x18015a028  mov     dword ptr [rbp+200h+var_260], ebx
0x18015a02b  mov     dword ptr [rbp+200h+var_258], 3DFh
0x18015a032  lea     rax, [rbp+200h+var_260]
0x18015a036  mov     [rsp+300h+var_2D0], rax
0x18015a03b  lea     rax, [rbp+200h+var_258]
0x18015a03f  lea     rdx, word_18035B9C6
0x18015a046  jmp     short loc_180159FDB
0x18015a048  lea     r8, [rbp+200h+instance]; instance
0x18015a04f  lea     rdx, SPACES_StoragePool_CreateStorageTier3_rtti; methodDecl
0x18015a056  mov     rcx, rsi; context
0x18015a059  call    MI_Context_ConstructParameters
0x18015a05e  mov     ebx, eax
0x18015a060  test    eax, eax
0x18015a062  jz      short loc_18015A096
0x18015a064  mov     eax, cs:dword_18039EB68
0x18015a06a  cmp     eax, 2
0x18015a06d  jbe     loc_18015A14C
0x18015a073  mov     dword ptr [rbp+200h+var_250], ebx
0x18015a076  mov     dword ptr [rbp+200h+var_248], 3E7h
0x18015a07d  lea     rax, [rbp+200h+var_250]
0x18015a081  mov     [rsp+300h+var_2D0], rax
0x18015a086  lea     rax, [rbp+200h+var_248]
0x18015a08a  lea     rdx, unk_18035D610
0x18015a091  jmp     loc_180159FDB
0x18015a096  mov     rcx, [rbp+200h+var_280]
0x18015a09a  mov     rax, [rcx]
0x18015a09d  lea     rdx, [rbp+200h+instance]
0x18015a0a4  mov     qword ptr [rsp+300h+var_2E0], rdx
0x18015a0a9  mov     r9, r13
0x18015a0ac  mov     r8, rsi
0x18015a0af  mov     edx, 0B0018h
0x18015a0b4  mov     rax, [rax+30h]
0x18015a0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a0bd  mov     ebx, eax
0x18015a0bf  test    eax, eax
0x18015a0c1  jz      short loc_18015A0F1
0x18015a0c3  mov     eax, cs:dword_18039EB68
0x18015a0c9  cmp     eax, 2
0x18015a0cc  jbe     short loc_18015A14C
0x18015a0ce  mov     dword ptr [rbp+200h+var_240], ebx
0x18015a0d1  mov     dword ptr [rbp+200h+var_278], 3F2h
0x18015a0d8  lea     rax, [rbp+200h+var_240]
0x18015a0dc  mov     [rsp+300h+var_2D0], rax
0x18015a0e1  lea     rax, [rbp+200h+var_278]
0x18015a0e5  lea     rdx, byte_18035BB83
0x18015a0ec  jmp     loc_180159FDB
0x18015a0f1  lea     rdx, [rbp+200h+instance]
0x18015a0f8  mov     rcx, rsi; self
0x18015a0fb  call    MI_Instance_Destruct
0x18015a100  mov     ebx, eax
0x18015a102  test    eax, eax
0x18015a104  jz      short loc_18015A14C
0x18015a106  mov     eax, cs:dword_18039EB68
0x18015a10c  cmp     eax, 2
0x18015a10f  jbe     short loc_18015A14C
0x18015a111  mov     [rsp+300h+var_284], ebx
0x18015a115  mov     dword ptr [rsp+300h+var_290], 3FAh
0x18015a11d  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x18015a124  mov     [rbp+200h+var_278], r13
0x18015a128  lea     rax, [rsp+300h+var_284]
0x18015a12d  mov     [rsp+300h+var_2D0], rax
0x18015a132  lea     rax, [rsp+300h+var_290]
0x18015a137  mov     [rsp+300h+var_2D8], rax
0x18015a13c  lea     rax, [rbp+200h+var_278]
0x18015a140  lea     rdx, unk_18035DE38
0x18015a147  jmp     loc_180159FF1
0x18015a14c  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x18015a153  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015a15a  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015a15f  jmp     short loc_18015A168
0x18015a161  lea     r13, aSpacesStoragep_1; "SPACES_StoragePool_Invoke_CreateStorage"...
0x18015a168  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015a16c  xor     r15d, r15d
0x18015a16f  mov     [rsp+300h+var_2D8], r15; unsigned __int16 *
0x18015a174  mov     [rsp+300h+var_2E0], ebx; enum _MI_Result
0x18015a178  lea     r9, [rbp+200h+var_140]; struct _MI_ConstUint32Field *
0x18015a17f  mov     rdx, [rbp+200h+var_238]; unsigned __int16 *
0x18015a183  mov     rcx, [rbp+200h+var_270]; unsigned __int16 *
0x18015a187  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015a18c  test    r12d, r12d
0x18015a18f  jnz     loc_18015A332
0x18015a195  lea     rcx, [rbp+200h+var_230]; this
0x18015a199  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015a19e  mov     eax, cs:dword_18039EB68
0x18015a1a4  cmp     eax, 5
0x18015a1a7  jbe     loc_18015A332
0x18015a1ad  mov     rdx, 400000000000h
0x18015a1b7  lea     rcx, dword_18039EB68
0x18015a1be  call    _tlgKeywordOn
0x18015a1c3  test    al, al
0x18015a1c5  jz      loc_18015A332
0x18015a1cb  cmp     [rbp+200h+var_88], r15b
0x18015a1d2  jz      short loc_18015A20F
0x18015a1d4  mov     rax, [rbp+200h+var_90]
0x18015a1db  movups  xmm0, xmmword ptr [rax]
0x18015a1de  movaps  xmmword ptr [rbp+200h+var_1F0.ft], xmm0
0x18015a1e2  movups  xmm1, xmmword ptr [rax+10h]
0x18015a1e6  movaps  xmmword ptr [rbp+200h+var_1F0.serverName], xmm1
0x18015a1ea  movups  xmm0, xmmword ptr [rax+20h]
0x18015a1ee  movaps  xmmword ptr [rbp+200h+var_1F0.reserved], xmm0
0x18015a1f2  movups  xmm1, xmmword ptr [rax+30h]
0x18015a1f6  movaps  xmmword ptr [rbp+200h+var_1F0.reserved+10h], xmm1
0x18015a1fa  xor     r8d, r8d; unsigned __int16 *
0x18015a1fd  lea     rdx, [rbp+200h+var_1F0]; struct _MI_Instance
0x18015a201  lea     rcx, name; "ObjectId"
0x18015a208  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015a20d  jmp     short loc_18015A212
0x18015a20f  mov     rax, r15
0x18015a212  mov     [rbp+200h+var_270], rax
0x18015a216  cmp     [rbp+200h+var_98], r15b
0x18015a21d  jz      short loc_18015A25A
0x18015a21f  mov     rax, [rbp+200h+var_A0]
0x18015a226  movups  xmm0, xmmword ptr [rax]
0x18015a229  movaps  xmmword ptr [rbp+200h+var_1F0.ft], xmm0
0x18015a22d  movups  xmm1, xmmword ptr [rax+10h]
0x18015a231  movaps  xmmword ptr [rbp+200h+var_1F0.serverName], xmm1
0x18015a235  movups  xmm0, xmmword ptr [rax+20h]
0x18015a239  movaps  xmmword ptr [rbp+200h+var_1F0.reserved], xmm0
0x18015a23d  movups  xmm1, xmmword ptr [rax+30h]
0x18015a241  movaps  xmmword ptr [rbp+200h+var_1F0.reserved+10h], xmm1
0x18015a245  xor     r8d, r8d; unsigned __int16 *
0x18015a248  lea     rdx, [rbp+200h+var_1F0]; struct _MI_Instance
0x18015a24c  lea     rcx, name; "ObjectId"
0x18015a253  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015a258  jmp     short loc_18015A25D
0x18015a25a  mov     rax, r15
0x18015a25d  mov     [rbp+200h+var_238], rax
0x18015a261  lea     rax, aStoragetier; "StorageTier"
0x18015a268  mov     [rbp+200h+var_240], rax
0x18015a26c  mov     rax, [rbp+200h+var_228]
0x18015a270  sub     rax, [rbp+200h+var_230]
0x18015a274  imul    rax, 3E8h
0x18015a27b  xor     edx, edx
0x18015a27d  div     [rbp+200h+var_220]
0x18015a281  mov     [rbp+200h+var_248], rax
0x18015a285  mov     dword ptr [rsp+300h+var_290], ebx
0x18015a289  mov     al, [rbp+200h+var_140.exists]
0x18015a28f  neg     al
0x18015a291  sbb     ecx, ecx
0x18015a293  and     ecx, [rbp+200h+var_140.value]
0x18015a299  mov     [rsp+300h+var_284], ecx
0x18015a29d  mov     dword ptr [rbp+200h+var_278], r14d
0x18015a2a1  cmp     [rdi+48h], r15b
0x18015a2a5  jz      short loc_18015A2AD
0x18015a2a7  mov     rax, [rdi+40h]
0x18015a2ab  jmp     short loc_18015A2B0
0x18015a2ad  mov     rax, r15
0x18015a2b0  mov     [rbp+200h+var_250], rax
0x18015a2b4  lea     rax, aCreatestoraget_1; "CreateStorageTier"
0x18015a2bb  mov     [rbp+200h+var_258], rax
0x18015a2bf  lea     rax, aStoragepool_0; "StoragePool"
0x18015a2c6  mov     [rbp+200h+var_260], rax
0x18015a2ca  lea     rax, [rbp+200h+var_270]
0x18015a2ce  mov     [rsp+300h+var_298], rax
0x18015a2d3  lea     rax, [rbp+200h+var_238]
0x18015a2d7  mov     [rsp+300h+var_2A0], rax
0x18015a2dc  lea     rax, [rbp+200h+var_240]
0x18015a2e0  mov     [rsp+300h+var_2A8], rax
0x18015a2e5  lea     rax, [rbp+200h+var_248]
0x18015a2e9  mov     [rsp+300h+var_2B0], rax
  ... truncated ...
```
