# SPACES_StoragePool_Invoke_CreateStorageTier

- ea: `0x1801591b0`
- end: `0x180159770`
- name: `SPACES_StoragePool_Invoke_CreateStorageTier`
- size: `1472`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
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
- `0x180023e18`
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x1801591b0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015922d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159739`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015922d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159739`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159256`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159256`

## string_xrefs

- `0x1801592aa`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x1801593d6`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x1801594bf`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x1801594ee`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x180159503`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x180159654`: `CreateStorageTier`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_CreateStorageTier(
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
  MI_Uint32 v36; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v37; // [rsp+80h] [rbp-80h] BYREF
  const char *v38; // [rsp+88h] [rbp-78h] BYREF
  const char *v39; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v40; // [rsp+98h] [rbp-68h] BYREF
  const char *v41; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v42; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v43; // [rsp+B0h] [rbp-50h] BYREF
  const char *v44; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v45; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v46[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v47; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-8h]
  struct _MI_Instance v49; // [rsp+100h] [rbp+0h] BYREF
  MI_Value value; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+170h] [rbp+70h] BYREF
  struct _MI_ConstUint32Field v52; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _MI_Instance *v53; // [rsp+1E0h] [rbp+E0h]
  char v54; // [rsp+1E8h] [rbp+E8h]
  struct _MI_Instance *v55; // [rsp+1F0h] [rbp+F0h]
  char v56; // [rsp+1F8h] [rbp+F8h]
  GUID ActivityId; // [rsp+210h] [rbp+110h] BYREF
  GUID v58; // [rsp+220h] [rbp+120h]
  GUID v59; // [rsp+230h] [rbp+130h] BYREF

  v40 = a4;
  v45 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v58 = ActivityId;
  v59 = ActivityId;
  EventActivityIdControl(4u, &v59);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v38) = 722;
    v35 = "SPACES_StoragePool_Invoke_CreateStorageTier";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateStorageTier",
      (unsigned int)byte_18035D24B,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v38);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x98u);
  v47 = 0;
  v48 = 0;
  v37 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
  v37 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v46);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v46);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v47) = 11;
    *((_QWORD *)&v47 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v47, &v37, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v38) = v15;
        LODWORD(v41) = 753;
        v34 = &v38;
        v20 = &v41;
        v21 = (__int16 *)&unk_18035D750;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateStorageTier";
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
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateStorageTier_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v42) = v15;
          LODWORD(v43) = 761;
          v34 = (const char **)&v42;
          v20 = (const char **)&v43;
          v21 = (__int16 *)&byte_18035D677;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v37 + 48LL))(
                v37,
                720908,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v36 = v15;
            LODWORD(v35) = 780;
            v39 = "SPACES_StoragePool_Invoke_CreateStorageTier";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)word_18035E052,
              v23,
              v24,
              (__int64)&v39,
              (__int64)&v35,
              (__int64)&v36);
          }
          goto LABEL_24;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v39) = 772;
          v34 = &v44;
          v20 = &v39;
          v21 = &word_18035CA3E;
          goto LABEL_13;
        }
      }
    }
LABEL_24:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v40, v45, a6 + 4, &v52, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v46);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( v56 )
        {
          v49 = *v55;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v49, 0);
        }
        else
        {
          v27 = 0;
        }
        v40 = v27;
        if ( v54 )
        {
          v49 = *v53;
          v28 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v49, 0);
        }
        else
        {
          v28 = 0;
        }
        v45 = v28;
        v44 = "StorageTier";
        v43 = (unsigned __int64)(1000LL * (v46[1] - v46[0])) / v46[2];
        LODWORD(v35) = v15;
        v36 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v42 = v29;
        v41 = "CreateStorageTier";
        v38 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)word_18035BA92,
          v25,
          v26,
          (__int64)&v38,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v39,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v35) = 813;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateStorageTier";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_18035D829,
      v31,
      v32,
      (__int64)&v40,
      (__int64)&v35);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v46);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v37);
  return EventActivityIdControl(4u, &v59);
}

```

## disassembly

```asm
0x1801591b0  mov     [rsp-8+arg_10], rbx
0x1801591b5  push    rbp
0x1801591b6  push    rsi
0x1801591b7  push    rdi
0x1801591b8  push    r12
0x1801591ba  push    r13
0x1801591bc  push    r14
0x1801591be  push    r15
0x1801591c0  lea     rbp, [rsp-150h]
0x1801591c8  sub     rsp, 250h
0x1801591cf  mov     rax, cs:__security_cookie
0x1801591d6  xor     rax, rsp
0x1801591d9  mov     [rbp+180h+var_40], rax
0x1801591e0  mov     [rbp+180h+var_1E8], r9
0x1801591e4  mov     rsi, rdx
0x1801591e7  mov     r15, rcx
0x1801591ea  mov     rax, [rbp+180h+arg_20]
0x1801591f1  mov     [rbp+180h+var_1C0], rax
0x1801591f5  mov     rdi, [rbp+180h+arg_28]
0x1801591fc  mov     r13, [rbp+180h+arg_30]
0x180159203  xorps   xmm0, xmm0
0x180159206  xor     eax, eax
0x180159208  movups  xmmword ptr [rbp+180h+value], xmm0
0x18015920c  movups  xmmword ptr [rbp+180h+value+10h], xmm0
0x180159210  mov     qword ptr [rbp+180h+value+20h], rax
0x180159214  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015921b  movdqu  xmmword ptr [rbp+180h+ActivityId.Data1], xmm0
0x180159223  lea     rdx, [rbp+180h+ActivityId]; ActivityId
0x18015922a  lea     ecx, [rax+1]; ControlCode
0x18015922d  call    cs:__imp_EventActivityIdControl
0x180159234  nop     dword ptr [rax+rax+00h]
0x180159239  lea     r9, [rbp+180h+value]; value
0x18015923d  mov     rcx, rsi; context
0x180159240  call    MI_Context_GetCustomOption_1
0x180159245  xor     ebx, ebx
0x180159247  test    eax, eax
0x180159249  jnz     short loc_180159262
0x18015924b  lea     rdx, [rbp+180h+ActivityId]; pclsid
0x180159252  mov     rcx, qword ptr [rbp+180h+value]; lpsz
0x180159256  call    cs:__imp_CLSIDFromString
0x18015925d  nop     dword ptr [rax+rax+00h]
0x180159262  mov     rcx, qword ptr [rbp+180h+ActivityId.Data1]
0x180159269  mov     [rbp+180h+var_60], rcx
0x180159270  mov     rax, qword ptr [rbp+180h+ActivityId.Data4]
0x180159277  mov     [rbp+180h+var_58], rax
0x18015927e  mov     qword ptr [rbp+180h+var_50.Data1], rcx
0x180159285  mov     qword ptr [rbp+180h+var_50.Data4], rax
0x18015928c  lea     rdx, [rbp+180h+var_50]; ActivityId
0x180159293  mov     ecx, 4; ControlCode
0x180159298  call    cs:__imp_EventActivityIdControl
0x18015929f  nop     dword ptr [rax+rax+00h]
0x1801592a4  mov     eax, cs:dword_18039EB68
0x1801592aa  lea     rcx, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801592b1  cmp     eax, 5
0x1801592b4  jbe     short loc_1801592E1
0x1801592b6  mov     dword ptr [rbp+180h+var_1F8], 2D2h
0x1801592bd  mov     [rsp+280h+var_210], rcx
0x1801592c2  lea     rax, [rbp+180h+var_1F8]
0x1801592c6  mov     [rsp+280h+var_258], rax
0x1801592cb  lea     rax, [rsp+280h+var_210]
0x1801592d0  mov     qword ptr [rsp+280h+var_260], rax
0x1801592d5  lea     rdx, byte_18035D24B
0x1801592dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801592e1  mov     [rbp+180h+instance.ft], rbx
0x1801592e5  xor     edx, edx; Val
0x1801592e7  mov     r8d, 98h; Size
0x1801592ed  lea     rcx, [rbp+180h+instance.classDecl]; void *
0x1801592f1  call    memset_0
0x1801592f6  xorps   xmm0, xmm0
0x1801592f9  xor     eax, eax
0x1801592fb  movups  [rbp+180h+var_198], xmm0
0x1801592ff  mov     [rbp+180h+var_188], rax
0x180159303  mov     [rbp+180h+var_200], rbx
0x180159307  lea     rcx, [rbp+180h+var_200]
0x18015930b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180159310  mov     [rbp+180h+var_200], rbx
0x180159314  mov     r14d, ebx
0x180159317  lea     rcx, [rbp+180h+var_1B8]; this
0x18015931b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180159320  mov     rcx, rsi; context
0x180159323  call    WspIsRemoteRequest
0x180159328  mov     r12d, eax
0x18015932b  test    eax, eax
0x18015932d  jnz     short loc_180159352
0x18015932f  lea     rcx, [rbp+180h+var_1B8]; this
0x180159333  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180159338  cmp     [rdi+48h], bl
0x18015933b  jz      short loc_18015934F
0x18015933d  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180159341  call    WspIsRemoteInstance
0x180159346  test    al, al
0x180159348  lea     r14d, [r12+1]
0x18015934d  jnz     short loc_180159352
0x18015934f  mov     r14d, ebx
0x180159352  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180159359  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015935e  mov     ebx, eax
0x180159360  test    eax, eax
0x180159362  jnz     loc_180159503
0x180159368  mov     dword ptr [rbp+180h+var_198], 0Bh
0x18015936f  mov     rax, [rdi+40h]
0x180159373  mov     qword ptr [rbp+180h+var_198+8], rax
0x180159377  mov     rbx, [r15]
0x18015937a  lea     rcx, [rbp+180h+var_200]
0x18015937e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180159383  mov     [rsp+280h+var_260], 1; int
0x18015938b  lea     r9, [rbp+180h+var_200]; struct ISpWmiObject **
0x18015938f  lea     r8, [rbp+180h+var_198]; struct _SP_OBJECT_ID *
0x180159393  mov     rdx, rsi; context
0x180159396  mov     rcx, rbx; this
0x180159399  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015939e  mov     ebx, eax
0x1801593a0  test    eax, eax
0x1801593a2  jz      short loc_1801593F6
0x1801593a4  mov     eax, cs:dword_18039EB68
0x1801593aa  cmp     eax, 2
0x1801593ad  jbe     loc_1801594EE
0x1801593b3  mov     dword ptr [rbp+180h+var_1F8], ebx
0x1801593b6  mov     dword ptr [rbp+180h+var_1E0], 2F1h
0x1801593bd  lea     rax, [rbp+180h+var_1F8]
0x1801593c1  mov     [rsp+280h+var_250], rax
0x1801593c6  lea     rax, [rbp+180h+var_1E0]
0x1801593ca  lea     rdx, unk_18035D750
0x1801593d1  mov     [rsp+280h+var_258], rax
0x1801593d6  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801593dd  lea     rax, [rsp+280h+var_210]
0x1801593e2  mov     [rsp+280h+var_210], r15
0x1801593e7  mov     qword ptr [rsp+280h+var_260], rax
0x1801593ec  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801593f1  jmp     loc_1801594F5
0x1801593f6  lea     r8, [rbp+180h+instance]; instance
0x1801593fa  lea     rdx, SPACES_StoragePool_CreateStorageTier_rtti; methodDecl
0x180159401  mov     rcx, rsi; context
0x180159404  call    MI_Context_ConstructParameters
0x180159409  mov     ebx, eax
0x18015940b  test    eax, eax
0x18015940d  jz      short loc_18015943E
0x18015940f  mov     eax, cs:dword_18039EB68
0x180159415  cmp     eax, 2
0x180159418  jbe     loc_1801594EE
0x18015941e  mov     dword ptr [rbp+180h+var_1D8], ebx
0x180159421  mov     dword ptr [rbp+180h+var_1D0], 2F9h
0x180159428  lea     rax, [rbp+180h+var_1D8]
0x18015942c  mov     [rsp+280h+var_250], rax
0x180159431  lea     rax, [rbp+180h+var_1D0]
0x180159435  lea     rdx, byte_18035D677
0x18015943c  jmp     short loc_1801593D1
0x18015943e  mov     rcx, [rbp+180h+var_200]
0x180159442  mov     rax, [rcx]
0x180159445  lea     rdx, [rbp+180h+instance]
0x180159449  mov     qword ptr [rsp+280h+var_260], rdx
0x18015944e  mov     r9, r13
0x180159451  mov     r8, rsi
0x180159454  mov     edx, 0B000Ch
0x180159459  mov     rax, [rax+30h]
0x18015945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159462  mov     ebx, eax
0x180159464  test    eax, eax
0x180159466  jz      short loc_180159496
0x180159468  mov     eax, cs:dword_18039EB68
0x18015946e  cmp     eax, 2
0x180159471  jbe     short loc_1801594EE
0x180159473  mov     dword ptr [rbp+180h+var_1C8], ebx
0x180159476  mov     dword ptr [rbp+180h+var_1F0], 304h
0x18015947d  lea     rax, [rbp+180h+var_1C8]
0x180159481  mov     [rsp+280h+var_250], rax
0x180159486  lea     rax, [rbp+180h+var_1F0]
0x18015948a  lea     rdx, word_18035CA3E
0x180159491  jmp     loc_1801593D1
0x180159496  lea     rdx, [rbp+180h+instance]
0x18015949a  mov     rcx, rsi; self
0x18015949d  call    MI_Instance_Destruct
0x1801594a2  mov     ebx, eax
0x1801594a4  test    eax, eax
0x1801594a6  jz      short loc_1801594EE
0x1801594a8  mov     eax, cs:dword_18039EB68
0x1801594ae  cmp     eax, 2
0x1801594b1  jbe     short loc_1801594EE
0x1801594b3  mov     [rsp+280h+var_208], ebx
0x1801594b7  mov     dword ptr [rsp+280h+var_210], 30Ch
0x1801594bf  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801594c6  mov     [rbp+180h+var_1F0], r15
0x1801594ca  lea     rax, [rsp+280h+var_208]
0x1801594cf  mov     [rsp+280h+var_250], rax
0x1801594d4  lea     rax, [rsp+280h+var_210]
0x1801594d9  mov     [rsp+280h+var_258], rax
0x1801594de  lea     rax, [rbp+180h+var_1F0]
0x1801594e2  lea     rdx, word_18035E052
0x1801594e9  jmp     loc_1801593E7
0x1801594ee  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801594f5  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801594fc  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180159501  jmp     short loc_18015950A
0x180159503  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x18015950a  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015950e  mov     [rsp+280h+var_258], 0; unsigned __int16 *
0x180159517  mov     [rsp+280h+var_260], ebx; enum _MI_Result
0x18015951b  lea     r9, [rbp+180h+var_D0]; struct _MI_ConstUint32Field *
0x180159522  mov     rdx, [rbp+180h+var_1C0]; unsigned __int16 *
0x180159526  mov     rcx, [rbp+180h+var_1E8]; unsigned __int16 *
0x18015952a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015952f  test    r12d, r12d
0x180159532  jnz     loc_1801596D2
0x180159538  lea     rcx, [rbp+180h+var_1B8]; this
0x18015953c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180159541  mov     eax, cs:dword_18039EB68
0x180159547  cmp     eax, 5
0x18015954a  jbe     loc_1801596D2
0x180159550  mov     rdx, 400000000000h
0x18015955a  lea     rcx, dword_18039EB68
0x180159561  call    _tlgKeywordOn
0x180159566  test    al, al
0x180159568  jz      loc_1801596D2
0x18015956e  cmp     [rbp+180h+var_88], r12b
0x180159575  jz      short loc_1801595B2
0x180159577  mov     rax, [rbp+180h+var_90]
0x18015957e  movups  xmm0, xmmword ptr [rax]
0x180159581  movaps  xmmword ptr [rbp+180h+var_180.ft], xmm0
0x180159585  movups  xmm1, xmmword ptr [rax+10h]
0x180159589  movaps  xmmword ptr [rbp+180h+var_180.serverName], xmm1
0x18015958d  movups  xmm0, xmmword ptr [rax+20h]
0x180159591  movaps  xmmword ptr [rbp+180h+var_180.reserved], xmm0
0x180159595  movups  xmm1, xmmword ptr [rax+30h]
0x180159599  movaps  xmmword ptr [rbp+180h+var_180.reserved+10h], xmm1
0x18015959d  xor     r8d, r8d; unsigned __int16 *
0x1801595a0  lea     rdx, [rbp+180h+var_180]; struct _MI_Instance
0x1801595a4  lea     rcx, name; "ObjectId"
0x1801595ab  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801595b0  jmp     short loc_1801595B4
0x1801595b2  xor     eax, eax
0x1801595b4  mov     [rbp+180h+var_1E8], rax
0x1801595b8  cmp     [rbp+180h+var_98], 0
0x1801595bf  jz      short loc_1801595FC
0x1801595c1  mov     rax, [rbp+180h+var_A0]
0x1801595c8  movups  xmm0, xmmword ptr [rax]
0x1801595cb  movaps  xmmword ptr [rbp+180h+var_180.ft], xmm0
0x1801595cf  movups  xmm1, xmmword ptr [rax+10h]
0x1801595d3  movaps  xmmword ptr [rbp+180h+var_180.serverName], xmm1
0x1801595d7  movups  xmm0, xmmword ptr [rax+20h]
0x1801595db  movaps  xmmword ptr [rbp+180h+var_180.reserved], xmm0
0x1801595df  movups  xmm1, xmmword ptr [rax+30h]
0x1801595e3  movaps  xmmword ptr [rbp+180h+var_180.reserved+10h], xmm1
0x1801595e7  xor     r8d, r8d; unsigned __int16 *
0x1801595ea  lea     rdx, [rbp+180h+var_180]; struct _MI_Instance
0x1801595ee  lea     rcx, name; "ObjectId"
0x1801595f5  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801595fa  jmp     short loc_1801595FE
0x1801595fc  xor     eax, eax
0x1801595fe  mov     [rbp+180h+var_1C0], rax
0x180159602  lea     rax, aStoragetier; "StorageTier"
0x180159609  mov     [rbp+180h+var_1C8], rax
0x18015960d  mov     rax, [rbp+180h+var_1B0]
0x180159611  sub     rax, [rbp+180h+var_1B8]
0x180159615  imul    rax, 3E8h
0x18015961c  xor     edx, edx
0x18015961e  div     [rbp+180h+var_1A8]
0x180159622  mov     [rbp+180h+var_1D0], rax
0x180159626  mov     dword ptr [rsp+280h+var_210], ebx
0x18015962a  mov     al, [rbp+180h+var_D0.exists]
0x180159630  neg     al
0x180159632  sbb     ecx, ecx
0x180159634  and     ecx, [rbp+180h+var_D0.value]
0x18015963a  mov     [rsp+280h+var_208], ecx
0x18015963e  mov     dword ptr [rbp+180h+var_1F0], r14d
0x180159642  cmp     byte ptr [rdi+48h], 0
0x180159646  jz      short loc_18015964E
0x180159648  mov     rax, [rdi+40h]
0x18015964c  jmp     short loc_180159650
0x18015964e  xor     eax, eax
0x180159650  mov     [rbp+180h+var_1D8], rax
0x180159654  lea     rax, aCreatestoraget_1; "CreateStorageTier"
0x18015965b  mov     [rbp+180h+var_1E0], rax
0x18015965f  lea     rax, aStoragepool_0; "StoragePool"
0x180159666  mov     [rbp+180h+var_1F8], rax
0x18015966a  lea     rax, [rbp+180h+var_1E8]
0x18015966e  mov     [rsp+280h+var_218], rax
0x180159673  lea     rax, [rbp+180h+var_1C0]
0x180159677  mov     [rsp+280h+var_220], rax
0x18015967c  lea     rax, [rbp+180h+var_1C8]
0x180159680  mov     [rsp+280h+var_228], rax
0x180159685  lea     rax, [rbp+180h+var_1D0]
0x180159689  mov     [rsp+280h+var_230], rax
0x18015968e  lea     rax, [rsp+280h+var_210]
0x180159693  mov     [rsp+280h+var_238], rax
0x180159698  lea     rax, [rsp+280h+var_208]
0x18015969d  mov     [rsp+280h+var_240], rax
0x1801596a2  lea     rax, [rbp+180h+var_1F0]
0x1801596a6  mov     [rsp+280h+var_248], rax
0x1801596ab  lea     rax, [rbp+180h+var_1D8]
0x1801596af  mov     [rsp+280h+var_250], rax
0x1801596b4  lea     rax, [rbp+180h+var_1E0]
0x1801596b8  mov     [rsp+280h+var_258], rax
0x1801596bd  lea     rax, [rbp+180h+var_1F8]
0x1801596c1  mov     qword ptr [rsp+280h+var_260], rax
0x1801596c6  lea     rdx, word_18035BA92
0x1801596cd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801596d2  lea     rcx, [rbp+180h+instance]; self
0x1801596d6  call    MI_Instance_Destruct
0x1801596db  mov     eax, cs:dword_18039EB68
0x1801596e1  cmp     eax, 5
  ... truncated ...
```
