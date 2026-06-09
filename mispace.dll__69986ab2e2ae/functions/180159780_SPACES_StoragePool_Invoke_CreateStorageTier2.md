# SPACES_StoragePool_Invoke_CreateStorageTier2

- ea: `0x180159780`
- end: `0x180159da0`
- name: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- size: `1568`
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
- `0x180159780`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801597fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159868`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159d69`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801597fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159868`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180159d69`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159826`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180159826`

## string_xrefs

- `0x180159c81`: `CreateStorageTier`
- `0x18015987a`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x1801599b5`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x180159aea`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x180159b19`: `SPACES_StoragePool_Invoke_CreateStorageTier2`
- `0x180159b2e`: `SPACES_StoragePool_Invoke_CreateStorageTier2`

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
  char *v21; // rdx
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
  struct _MI_Instance *v55; // [rsp+228h] [rbp+128h]
  char v56; // [rsp+230h] [rbp+130h]
  struct _MI_Instance *v57; // [rsp+238h] [rbp+138h]
  char v58; // [rsp+240h] [rbp+140h]
  GUID ActivityId; // [rsp+260h] [rbp+160h] BYREF
  GUID v60; // [rsp+270h] [rbp+170h]
  GUID v61; // [rsp+280h] [rbp+180h] BYREF

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
    v36 = 829;
    v35 = "SPACES_StoragePool_Invoke_CreateStorageTier2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateStorageTier2",
      (unsigned int)&byte_18035D92F,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xD0u);
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
        v41 = 861;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = byte_18035E52B;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateStorageTier2";
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
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateStorageTier2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v45) = 880;
          v34 = (const char **)&v44;
          v20 = (const char **)&v45;
          v21 = (char *)&unk_18035C278;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720918,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v35) = 899;
            v39 = "SPACES_StoragePool_Invoke_CreateStorageTier2";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&unk_18035C350,
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
          LODWORD(v39) = 891;
          v34 = &v46;
          v20 = &v39;
          v21 = byte_18035D95D;
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
        LODWORD(v43) = 872;
        v34 = &v42;
        v20 = &v43;
        v21 = (char *)&dword_18035CCD4;
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
          (unsigned int)byte_18035B57B,
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
    LODWORD(v35) = 932;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateStorageTier2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_18035B481,
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
0x180159780  mov     [rsp-8+arg_10], rbx
0x180159785  push    rbp
0x180159786  push    rsi
0x180159787  push    rdi
0x180159788  push    r12
0x18015978a  push    r13
0x18015978c  push    r14
0x18015978e  push    r15
0x180159790  lea     rbp, [rsp-1A0h]
0x180159798  sub     rsp, 2A0h
0x18015979f  mov     rax, cs:__security_cookie
0x1801597a6  xor     rax, rsp
0x1801597a9  mov     [rbp+1D0h+var_40], rax
0x1801597b0  mov     [rbp+1D0h+var_240], r9
0x1801597b4  mov     rsi, rdx
0x1801597b7  mov     r15, rcx
0x1801597ba  mov     rax, [rbp+1D0h+arg_20]
0x1801597c1  mov     [rbp+1D0h+var_208], rax
0x1801597c5  mov     rdi, [rbp+1D0h+arg_28]
0x1801597cc  mov     r13, [rbp+1D0h+arg_30]
0x1801597d3  xorps   xmm0, xmm0
0x1801597d6  xor     eax, eax
0x1801597d8  movups  xmmword ptr [rbp+1D0h+value], xmm0
0x1801597dc  movups  xmmword ptr [rbp+1D0h+value+10h], xmm0
0x1801597e0  mov     qword ptr [rbp+1D0h+value+20h], rax
0x1801597e4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801597eb  movdqu  xmmword ptr [rbp+1D0h+ActivityId.Data1], xmm0
0x1801597f3  lea     rdx, [rbp+1D0h+ActivityId]; ActivityId
0x1801597fa  lea     ecx, [rax+1]; ControlCode
0x1801597fd  call    cs:__imp_EventActivityIdControl
0x180159804  nop     dword ptr [rax+rax+00h]
0x180159809  lea     r9, [rbp+1D0h+value]; value
0x18015980d  mov     rcx, rsi; context
0x180159810  call    MI_Context_GetCustomOption_1
0x180159815  xor     ebx, ebx
0x180159817  test    eax, eax
0x180159819  jnz     short loc_180159832
0x18015981b  lea     rdx, [rbp+1D0h+ActivityId]; pclsid
0x180159822  mov     rcx, qword ptr [rbp+1D0h+value]; lpsz
0x180159826  call    cs:__imp_CLSIDFromString
0x18015982d  nop     dword ptr [rax+rax+00h]
0x180159832  mov     rcx, qword ptr [rbp+1D0h+ActivityId.Data1]
0x180159839  mov     [rbp+1D0h+var_60], rcx
0x180159840  mov     rax, qword ptr [rbp+1D0h+ActivityId.Data4]
0x180159847  mov     [rbp+1D0h+var_58], rax
0x18015984e  mov     qword ptr [rbp+1D0h+var_50.Data1], rcx
0x180159855  mov     qword ptr [rbp+1D0h+var_50.Data4], rax
0x18015985c  lea     rdx, [rbp+1D0h+var_50]; ActivityId
0x180159863  mov     ecx, 4; ControlCode
0x180159868  call    cs:__imp_EventActivityIdControl
0x18015986f  nop     dword ptr [rax+rax+00h]
0x180159874  mov     eax, cs:dword_18039EB68
0x18015987a  lea     rcx, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180159881  cmp     eax, 5
0x180159884  jbe     short loc_1801598B3
0x180159886  mov     [rsp+2D0h+var_258], 33Dh
0x18015988e  mov     [rsp+2D0h+var_260], rcx
0x180159893  lea     rax, [rsp+2D0h+var_258]
0x180159898  mov     [rsp+2D0h+var_2A8], rax
0x18015989d  lea     rax, [rsp+2D0h+var_260]
0x1801598a2  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x1801598a7  lea     rdx, byte_18035D92F
0x1801598ae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801598b3  mov     [rbp+1D0h+instance.ft], rbx
0x1801598ba  xor     edx, edx; Val
0x1801598bc  mov     r8d, 0D0h; Size
0x1801598c2  lea     rcx, [rbp+1D0h+instance.classDecl]; void *
0x1801598c9  call    memset_0
0x1801598ce  xorps   xmm0, xmm0
0x1801598d1  xor     eax, eax
0x1801598d3  movups  [rbp+1D0h+var_1E0], xmm0
0x1801598d7  mov     [rbp+1D0h+var_1D0], rax
0x1801598db  mov     [rbp+1D0h+var_250], rbx
0x1801598df  lea     rcx, [rbp+1D0h+var_250]
0x1801598e3  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801598e8  mov     [rbp+1D0h+var_250], rbx
0x1801598ec  mov     r14d, ebx
0x1801598ef  lea     rcx, [rbp+1D0h+var_200]; this
0x1801598f3  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801598f8  mov     rcx, rsi; context
0x1801598fb  call    WspIsRemoteRequest
0x180159900  mov     r12d, eax
0x180159903  test    eax, eax
0x180159905  jnz     short loc_18015992A
0x180159907  lea     rcx, [rbp+1D0h+var_200]; this
0x18015990b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180159910  cmp     [rdi+48h], bl
0x180159913  jz      short loc_180159927
0x180159915  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180159919  call    WspIsRemoteInstance
0x18015991e  test    al, al
0x180159920  lea     r14d, [r12+1]
0x180159925  jnz     short loc_18015992A
0x180159927  mov     r14d, ebx
0x18015992a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180159931  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180159936  mov     ebx, eax
0x180159938  test    eax, eax
0x18015993a  jnz     loc_180159B2E
0x180159940  mov     dword ptr [rbp+1D0h+var_1E0], 0Bh
0x180159947  mov     rax, [rdi+40h]
0x18015994b  mov     qword ptr [rbp+1D0h+var_1E0+8], rax
0x18015994f  mov     rbx, [r15]
0x180159952  lea     rcx, [rbp+1D0h+var_250]
0x180159956  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015995b  mov     [rsp+2D0h+var_2B0], 1; int
0x180159963  lea     r9, [rbp+1D0h+var_250]; struct ISpWmiObject **
0x180159967  lea     r8, [rbp+1D0h+var_1E0]; struct _SP_OBJECT_ID *
0x18015996b  mov     rdx, rsi; context
0x18015996e  mov     rcx, rbx; this
0x180159971  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180159976  mov     ebx, eax
0x180159978  test    eax, eax
0x18015997a  jz      short loc_1801599D0
0x18015997c  mov     eax, cs:dword_18039EB68
0x180159982  cmp     eax, 2
0x180159985  jbe     loc_180159B19
0x18015998b  mov     [rsp+2D0h+var_258], ebx
0x18015998f  mov     [rbp+1D0h+var_238], 35Dh
0x180159996  lea     rax, [rsp+2D0h+var_258]
0x18015999b  mov     [rsp+2D0h+var_2A0], rax
0x1801599a0  lea     rax, [rbp+1D0h+var_238]
0x1801599a4  lea     rdx, byte_18035E52B
0x1801599ab  mov     [rsp+2D0h+var_2A8], rax
0x1801599b0  lea     rax, [rsp+2D0h+var_260]
0x1801599b5  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801599bc  mov     [rsp+2D0h+var_260], r13
0x1801599c1  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x1801599c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801599cb  jmp     loc_180159B20
0x1801599d0  mov     r8, [rdi+40h]
0x1801599d4  mov     rdx, rsi
0x1801599d7  mov     rcx, [r15]
0x1801599da  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x1801599df  test    eax, eax
0x1801599e1  jnz     short loc_180159A15
0x1801599e3  lea     ebx, [rax+7]
0x1801599e6  mov     eax, cs:dword_18039EB68
0x1801599ec  cmp     eax, 2
0x1801599ef  jbe     loc_180159B19
0x1801599f5  mov     dword ptr [rbp+1D0h+var_230], ebx
0x1801599f8  mov     dword ptr [rbp+1D0h+var_228], 368h
0x1801599ff  lea     rax, [rbp+1D0h+var_230]
0x180159a03  mov     [rsp+2D0h+var_2A0], rax
0x180159a08  lea     rax, [rbp+1D0h+var_228]
0x180159a0c  lea     rdx, dword_18035CCD4
0x180159a13  jmp     short loc_1801599AB
0x180159a15  lea     r8, [rbp+1D0h+instance]; instance
0x180159a1c  lea     rdx, SPACES_StoragePool_CreateStorageTier2_rtti; methodDecl
0x180159a23  mov     rcx, rsi; context
0x180159a26  call    MI_Context_ConstructParameters
0x180159a2b  mov     ebx, eax
0x180159a2d  test    eax, eax
0x180159a2f  jz      short loc_180159A63
0x180159a31  mov     eax, cs:dword_18039EB68
0x180159a37  cmp     eax, 2
0x180159a3a  jbe     loc_180159B19
0x180159a40  mov     dword ptr [rbp+1D0h+var_220], ebx
0x180159a43  mov     dword ptr [rbp+1D0h+var_218], 370h
0x180159a4a  lea     rax, [rbp+1D0h+var_220]
0x180159a4e  mov     [rsp+2D0h+var_2A0], rax
0x180159a53  lea     rax, [rbp+1D0h+var_218]
0x180159a57  lea     rdx, unk_18035C278
0x180159a5e  jmp     loc_1801599AB
0x180159a63  mov     rcx, [rbp+1D0h+var_250]
0x180159a67  mov     rax, [rcx]
0x180159a6a  lea     rdx, [rbp+1D0h+instance]
0x180159a71  mov     qword ptr [rsp+2D0h+var_2B0], rdx
0x180159a76  mov     r9, r13
0x180159a79  mov     r8, rsi
0x180159a7c  mov     edx, 0B0016h
0x180159a81  mov     rax, [rax+30h]
0x180159a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180159a8a  mov     ebx, eax
0x180159a8c  test    eax, eax
0x180159a8e  jz      short loc_180159ABE
0x180159a90  mov     eax, cs:dword_18039EB68
0x180159a96  cmp     eax, 2
0x180159a99  jbe     short loc_180159B19
0x180159a9b  mov     dword ptr [rbp+1D0h+var_210], ebx
0x180159a9e  mov     dword ptr [rbp+1D0h+var_248], 37Bh
0x180159aa5  lea     rax, [rbp+1D0h+var_210]
0x180159aa9  mov     [rsp+2D0h+var_2A0], rax
0x180159aae  lea     rax, [rbp+1D0h+var_248]
0x180159ab2  lea     rdx, byte_18035D95D
0x180159ab9  jmp     loc_1801599AB
0x180159abe  lea     rdx, [rbp+1D0h+instance]
0x180159ac5  mov     rcx, rsi; self
0x180159ac8  call    MI_Instance_Destruct
0x180159acd  mov     ebx, eax
0x180159acf  test    eax, eax
0x180159ad1  jz      short loc_180159B19
0x180159ad3  mov     eax, cs:dword_18039EB68
0x180159ad9  cmp     eax, 2
0x180159adc  jbe     short loc_180159B19
0x180159ade  mov     [rsp+2D0h+var_254], ebx
0x180159ae2  mov     dword ptr [rsp+2D0h+var_260], 383h
0x180159aea  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180159af1  mov     [rbp+1D0h+var_248], r13
0x180159af5  lea     rax, [rsp+2D0h+var_254]
0x180159afa  mov     [rsp+2D0h+var_2A0], rax
0x180159aff  lea     rax, [rsp+2D0h+var_260]
0x180159b04  mov     [rsp+2D0h+var_2A8], rax
0x180159b09  lea     rax, [rbp+1D0h+var_248]
0x180159b0d  lea     rdx, unk_18035C350
0x180159b14  jmp     loc_1801599C1
0x180159b19  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180159b20  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180159b27  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180159b2c  jmp     short loc_180159B35
0x180159b2e  lea     r13, aSpacesStoragep_64; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180159b35  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x180159b39  xor     r15d, r15d
0x180159b3c  mov     [rsp+2D0h+var_2A8], r15; unsigned __int16 *
0x180159b41  mov     [rsp+2D0h+var_2B0], ebx; enum _MI_Result
0x180159b45  lea     r9, [rbp+1D0h+var_110]; struct _MI_ConstUint32Field *
0x180159b4c  mov     rdx, [rbp+1D0h+var_208]; unsigned __int16 *
0x180159b50  mov     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x180159b54  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180159b59  test    r12d, r12d
0x180159b5c  jnz     loc_180159CFF
0x180159b62  lea     rcx, [rbp+1D0h+var_200]; this
0x180159b66  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180159b6b  mov     eax, cs:dword_18039EB68
0x180159b71  cmp     eax, 5
0x180159b74  jbe     loc_180159CFF
0x180159b7a  mov     rdx, 400000000000h
0x180159b84  lea     rcx, dword_18039EB68
0x180159b8b  call    _tlgKeywordOn
0x180159b90  test    al, al
0x180159b92  jz      loc_180159CFF
0x180159b98  cmp     [rbp+1D0h+var_90], r15b
0x180159b9f  jz      short loc_180159BDC
0x180159ba1  mov     rax, [rbp+1D0h+var_98]
0x180159ba8  movups  xmm0, xmmword ptr [rax]
0x180159bab  movaps  xmmword ptr [rbp+1D0h+var_1C0.ft], xmm0
0x180159baf  movups  xmm1, xmmword ptr [rax+10h]
0x180159bb3  movaps  xmmword ptr [rbp+1D0h+var_1C0.serverName], xmm1
0x180159bb7  movups  xmm0, xmmword ptr [rax+20h]
0x180159bbb  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved], xmm0
0x180159bbf  movups  xmm1, xmmword ptr [rax+30h]
0x180159bc3  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved+10h], xmm1
0x180159bc7  xor     r8d, r8d; unsigned __int16 *
0x180159bca  lea     rdx, [rbp+1D0h+var_1C0]; struct _MI_Instance
0x180159bce  lea     rcx, name; "ObjectId"
0x180159bd5  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180159bda  jmp     short loc_180159BDF
0x180159bdc  mov     rax, r15
0x180159bdf  mov     [rbp+1D0h+var_240], rax
0x180159be3  cmp     [rbp+1D0h+var_A0], r15b
0x180159bea  jz      short loc_180159C27
0x180159bec  mov     rax, [rbp+1D0h+var_A8]
0x180159bf3  movups  xmm0, xmmword ptr [rax]
0x180159bf6  movaps  xmmword ptr [rbp+1D0h+var_1C0.ft], xmm0
0x180159bfa  movups  xmm1, xmmword ptr [rax+10h]
0x180159bfe  movaps  xmmword ptr [rbp+1D0h+var_1C0.serverName], xmm1
0x180159c02  movups  xmm0, xmmword ptr [rax+20h]
0x180159c06  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved], xmm0
0x180159c0a  movups  xmm1, xmmword ptr [rax+30h]
0x180159c0e  movaps  xmmword ptr [rbp+1D0h+var_1C0.reserved+10h], xmm1
0x180159c12  xor     r8d, r8d; unsigned __int16 *
0x180159c15  lea     rdx, [rbp+1D0h+var_1C0]; struct _MI_Instance
0x180159c19  lea     rcx, name; "ObjectId"
0x180159c20  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180159c25  jmp     short loc_180159C2A
0x180159c27  mov     rax, r15
0x180159c2a  mov     [rbp+1D0h+var_208], rax
0x180159c2e  lea     rax, aStoragetier; "StorageTier"
0x180159c35  mov     [rbp+1D0h+var_210], rax
0x180159c39  mov     rax, [rbp+1D0h+var_1F8]
0x180159c3d  sub     rax, [rbp+1D0h+var_200]
0x180159c41  imul    rax, 3E8h
0x180159c48  xor     edx, edx
0x180159c4a  div     [rbp+1D0h+var_1F0]
0x180159c4e  mov     [rbp+1D0h+var_218], rax
0x180159c52  mov     dword ptr [rsp+2D0h+var_260], ebx
0x180159c56  mov     al, [rbp+1D0h+var_110.exists]
0x180159c5c  neg     al
0x180159c5e  sbb     ecx, ecx
0x180159c60  and     ecx, [rbp+1D0h+var_110.value]
0x180159c66  mov     [rsp+2D0h+var_254], ecx
0x180159c6a  mov     dword ptr [rbp+1D0h+var_248], r14d
0x180159c6e  cmp     [rdi+48h], r15b
0x180159c72  jz      short loc_180159C7A
0x180159c74  mov     rax, [rdi+40h]
0x180159c78  jmp     short loc_180159C7D
0x180159c7a  mov     rax, r15
0x180159c7d  mov     [rbp+1D0h+var_220], rax
0x180159c81  lea     rax, aCreatestoraget_1; "CreateStorageTier"
0x180159c88  mov     [rbp+1D0h+var_228], rax
0x180159c8c  lea     rax, aStoragepool_0; "StoragePool"
0x180159c93  mov     [rbp+1D0h+var_230], rax
0x180159c97  lea     rax, [rbp+1D0h+var_240]
0x180159c9b  mov     [rsp+2D0h+var_268], rax
0x180159ca0  lea     rax, [rbp+1D0h+var_208]
0x180159ca4  mov     [rsp+2D0h+var_270], rax
0x180159ca9  lea     rax, [rbp+1D0h+var_210]
0x180159cad  mov     [rsp+2D0h+var_278], rax
0x180159cb2  lea     rax, [rbp+1D0h+var_218]
0x180159cb6  mov     [rsp+2D0h+var_280], rax
  ... truncated ...
```
