# SPACES_StorageSubsystem_Invoke_CreateStoragePool

- ea: `0x18016c440`
- end: `0x18016ca3e`
- name: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- size: `1534`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800047c0`
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
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x18016c440`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016c4bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016c51c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016ca0e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016c4bd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016c51c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18016ca0e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016c4e0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18016c4e0`

## string_xrefs

- `0x18016c528`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x18016c642`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x18016c6a4`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x18016c717`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x18016c76b`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x18016c9ad`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x18016c90a`: `CreateStoragePool`

## pseudocode

```c
ULONG __fastcall SPACES_StorageSubsystem_Invoke_CreateStoragePool(
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
  enum _MI_Result v13; // r14d
  int IsRemoteRequest; // r13d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const char **v20; // rax
  char *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // eax
  unsigned __int16 *v25; // rax
  unsigned __int16 *v26; // rax
  const MI_Char *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  unsigned __int16 *v32; // [rsp+28h] [rbp-D8h]
  const char *v33; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v34; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v35; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v36; // [rsp+90h] [rbp-70h] BYREF
  const char *v37; // [rsp+98h] [rbp-68h] BYREF
  const char *v38; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v39; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v40; // [rsp+B0h] [rbp-50h] BYREF
  const char *v41; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v42; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v43; // [rsp+C8h] [rbp-38h] BYREF
  const char *v44; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v45[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v46; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v47; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v48; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v51; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v52; // [rsp+250h] [rbp+150h]
  char v53; // [rsp+258h] [rbp+158h]
  struct _MI_Instance *v54; // [rsp+260h] [rbp+160h]
  char v55; // [rsp+268h] [rbp+168h]
  GUID ActivityId; // [rsp+280h] [rbp+180h] BYREF
  GUID v57; // [rsp+290h] [rbp+190h]
  GUID v58; // [rsp+2A0h] [rbp+1A0h] BYREF

  v43 = a4;
  v42 = a5;
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
    LODWORD(v37) = 149;
    v33 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
    v32 = (unsigned __int16 *)&v37;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StorageSubsystem_Invoke_CreateStoragePool",
      (__int64)word_18035C4AA,
      v11,
      v12,
      &v33);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xF8u);
  v46 = 0;
  v47 = 0;
  v36 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
  v36 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v45);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v45);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v46) = 13;
    *((_QWORD *)&v46 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v46, &v36, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v37) = v15;
        LODWORD(v39) = 180;
        v33 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
        v20 = &v33;
        v21 = &byte_18035D4A7;
LABEL_22:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (__int64)v21,
          v18,
          v19,
          v20);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageSubsystem_CreateStoragePool_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v40) = v15;
          LODWORD(v41) = 188;
          v33 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
          v20 = &v33;
          v21 = &byte_18035D547;
          goto LABEL_22;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v36 + 48LL))(
                v36,
                851969,
                a2,
                a7,
                &instance,
                v32);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_23;
          v35 = v15;
          LODWORD(v33) = 207;
          v38 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
          v20 = &v38;
          v21 = &byte_18035DC37;
          goto LABEL_22;
        }
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v34 = v15;
          LODWORD(v38) = 199;
          v33 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
          v20 = &v33;
          v21 = (char *)word_18035D02A;
          goto LABEL_22;
        }
      }
    }
LABEL_23:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v43, v42, a6 + 4, &v51, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v45);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 128) )
          v24 = *(_DWORD *)(a7 + 120);
        else
          v24 = 0;
        LODWORD(v33) = v24;
        if ( v55 )
        {
          v48 = *v54;
          v25 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v25 = 0;
        }
        v43 = v25;
        if ( v53 )
        {
          v48 = *v52;
          v26 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v26 = 0;
        }
        v42 = v26;
        v41 = "StoragePool";
        v40 = (unsigned __int64)(1000LL * (v45[1] - v45[0])) / v45[2];
        v35 = v15;
        LODWORD(v38) = v51.exists != 0 ? v51.value : 0;
        v34 = v13;
        if ( a6[4].exists )
          v27 = a6[4].value;
        else
          v27 = 0;
        v39 = v27;
        v37 = "CreateStoragePool";
        v44 = "StorageSubsystem";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v51.exists != 0 ? v51.value : 0,
          (__int64)byte_18035D289,
          v22,
          v23,
          &v44,
          &v37,
          &v39,
          (__int64)&v34,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v40,
          &v41,
          &v42,
          &v43);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v33) = 241;
    v44 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v28,
      (__int64)&byte_18035CC57,
      v29,
      v30,
      &v44);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v45);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
  return EventActivityIdControl(4u, &v58);
}

```

## disassembly

```asm
0x18016c440  mov     [rsp-8+arg_10], rbx
0x18016c445  push    rbp
0x18016c446  push    rsi
0x18016c447  push    rdi
0x18016c448  push    r12
0x18016c44a  push    r13
0x18016c44c  push    r14
0x18016c44e  push    r15
0x18016c450  lea     rbp, [rsp-1C0h]
0x18016c458  sub     rsp, 2C0h
0x18016c45f  mov     rax, cs:__security_cookie
0x18016c466  xor     rax, rsp
0x18016c469  mov     [rbp+1F0h+var_40], rax
0x18016c470  mov     [rbp+1F0h+var_228], r9
0x18016c474  mov     rdi, rdx
0x18016c477  mov     r12, rcx
0x18016c47a  mov     rax, [rbp+1F0h+arg_20]
0x18016c481  mov     [rbp+1F0h+var_230], rax
0x18016c485  mov     rsi, [rbp+1F0h+arg_28]
0x18016c48c  mov     r15, [rbp+1F0h+arg_30]
0x18016c493  xorps   xmm0, xmm0
0x18016c496  xor     eax, eax
0x18016c498  movups  xmmword ptr [rbp+1F0h+value], xmm0
0x18016c49c  movups  xmmword ptr [rbp+1F0h+value+10h], xmm0
0x18016c4a0  mov     qword ptr [rbp+1F0h+value+20h], rax
0x18016c4a4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18016c4ab  movdqu  xmmword ptr [rbp+1F0h+ActivityId.Data1], xmm0
0x18016c4b3  lea     rdx, [rbp+1F0h+ActivityId]; ActivityId
0x18016c4ba  lea     ecx, [rax+1]; ControlCode
0x18016c4bd  call    cs:__imp_EventActivityIdControl
0x18016c4c3  lea     r9, [rbp+1F0h+value]; value
0x18016c4c7  mov     rcx, rdi; context
0x18016c4ca  call    MI_Context_GetCustomOption_1
0x18016c4cf  xor     ebx, ebx
0x18016c4d1  test    eax, eax
0x18016c4d3  jnz     short loc_18016C4E6
0x18016c4d5  lea     rdx, [rbp+1F0h+ActivityId]; pclsid
0x18016c4dc  mov     rcx, qword ptr [rbp+1F0h+value]; lpsz
0x18016c4e0  call    cs:__imp_CLSIDFromString
0x18016c4e6  mov     rcx, qword ptr [rbp+1F0h+ActivityId.Data1]
0x18016c4ed  mov     [rbp+1F0h+var_60], rcx
0x18016c4f4  mov     rax, qword ptr [rbp+1F0h+ActivityId.Data4]
0x18016c4fb  mov     [rbp+1F0h+var_58], rax
0x18016c502  mov     qword ptr [rbp+1F0h+var_50.Data1], rcx
0x18016c509  mov     qword ptr [rbp+1F0h+var_50.Data4], rax
0x18016c510  lea     rdx, [rbp+1F0h+var_50]; ActivityId
0x18016c517  mov     ecx, 4; ControlCode
0x18016c51c  call    cs:__imp_EventActivityIdControl
0x18016c522  mov     eax, cs:dword_180397B68
0x18016c528  lea     rcx, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016c52f  cmp     eax, 5
0x18016c532  jbe     short loc_18016C55D
0x18016c534  mov     dword ptr [rbp+1F0h+var_258], 95h
0x18016c53b  mov     [rbp+1F0h+var_270], rcx
0x18016c53f  lea     rax, [rbp+1F0h+var_258]
0x18016c543  mov     [rsp+2F0h+var_2C8], rax
0x18016c548  lea     rax, [rbp+1F0h+var_270]
0x18016c54c  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18016c551  lea     rdx, word_18035C4AA
0x18016c558  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016c55d  mov     [rbp+1F0h+instance.ft], rbx
0x18016c564  xor     edx, edx; Val
0x18016c566  mov     r8d, 0F8h; Size
0x18016c56c  lea     rcx, [rbp+1F0h+instance.classDecl]; void *
0x18016c573  call    memset_0
0x18016c578  xorps   xmm0, xmm0
0x18016c57b  xor     eax, eax
0x18016c57d  movups  [rbp+1F0h+var_1F8], xmm0
0x18016c581  mov     [rbp+1F0h+var_1E8], rax
0x18016c585  mov     [rbp+1F0h+var_260], rbx
0x18016c589  lea     rcx, [rbp+1F0h+var_260]
0x18016c58d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016c592  mov     [rbp+1F0h+var_260], rbx
0x18016c596  mov     r14d, ebx
0x18016c599  lea     rcx, [rbp+1F0h+var_218]; this
0x18016c59d  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18016c5a2  mov     rcx, rdi; context
0x18016c5a5  call    WspIsRemoteRequest
0x18016c5aa  mov     r13d, eax
0x18016c5ad  test    eax, eax
0x18016c5af  jnz     short loc_18016C5D3
0x18016c5b1  lea     rcx, [rbp+1F0h+var_218]; this
0x18016c5b5  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18016c5ba  cmp     [rsi+48h], bl
0x18016c5bd  jz      short loc_18016C5D0
0x18016c5bf  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18016c5c3  call    WspIsRemoteInstance
0x18016c5c8  test    al, al
0x18016c5ca  lea     r14d, [r13+1]
0x18016c5ce  jnz     short loc_18016C5D3
0x18016c5d0  mov     r14d, ebx
0x18016c5d3  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18016c5da  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18016c5df  mov     ebx, eax
0x18016c5e1  test    eax, eax
0x18016c5e3  jnz     loc_18016C7AB
0x18016c5e9  mov     dword ptr [rbp+1F0h+var_1F8], 0Dh
0x18016c5f0  mov     rax, [rsi+40h]
0x18016c5f4  mov     qword ptr [rbp+1F0h+var_1F8+8], rax
0x18016c5f8  mov     rbx, [r12]
0x18016c5fc  lea     rcx, [rbp+1F0h+var_260]
0x18016c600  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18016c605  mov     [rsp+2F0h+var_2D0], 1; int
0x18016c60d  lea     r9, [rbp+1F0h+var_260]; struct ISpWmiObject **
0x18016c611  lea     r8, [rbp+1F0h+var_1F8]; struct _SP_OBJECT_ID *
0x18016c615  mov     rdx, rdi; context
0x18016c618  mov     rcx, rbx; this
0x18016c61b  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18016c620  mov     ebx, eax
0x18016c622  xor     r12d, r12d
0x18016c625  test    eax, eax
0x18016c627  jz      short loc_18016C66F
0x18016c629  mov     eax, cs:dword_180397B68
0x18016c62f  cmp     eax, 2
0x18016c632  jbe     loc_18016C79D
0x18016c638  mov     dword ptr [rbp+1F0h+var_258], ebx
0x18016c63b  mov     dword ptr [rbp+1F0h+var_248], 0B4h
0x18016c642  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016c649  mov     [rbp+1F0h+var_270], rax
0x18016c64d  lea     rax, [rbp+1F0h+var_258]
0x18016c651  mov     [rsp+2F0h+var_2C0], rax
0x18016c656  lea     rax, [rbp+1F0h+var_248]
0x18016c65a  mov     [rsp+2F0h+var_2C8], rax
0x18016c65f  lea     rax, [rbp+1F0h+var_270]
0x18016c663  lea     rdx, byte_18035D4A7
0x18016c66a  jmp     loc_18016C793
0x18016c66f  lea     r8, [rbp+1F0h+instance]; instance
0x18016c676  lea     rdx, SPACES_StorageSubsystem_CreateStoragePool_rtti; methodDecl
0x18016c67d  mov     rcx, rdi; context
0x18016c680  call    MI_Context_ConstructParameters
0x18016c685  mov     ebx, eax
0x18016c687  test    eax, eax
0x18016c689  jz      short loc_18016C6D1
0x18016c68b  mov     eax, cs:dword_180397B68
0x18016c691  cmp     eax, 2
0x18016c694  jbe     loc_18016C79D
0x18016c69a  mov     dword ptr [rbp+1F0h+var_240], ebx
0x18016c69d  mov     dword ptr [rbp+1F0h+var_238], 0BCh
0x18016c6a4  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016c6ab  mov     [rbp+1F0h+var_270], rax
0x18016c6af  lea     rax, [rbp+1F0h+var_240]
0x18016c6b3  mov     [rsp+2F0h+var_2C0], rax
0x18016c6b8  lea     rax, [rbp+1F0h+var_238]
0x18016c6bc  mov     [rsp+2F0h+var_2C8], rax
0x18016c6c1  lea     rax, [rbp+1F0h+var_270]
0x18016c6c5  lea     rdx, byte_18035D547
0x18016c6cc  jmp     loc_18016C793
0x18016c6d1  mov     rcx, [rbp+1F0h+var_260]
0x18016c6d5  mov     rax, [rcx]
0x18016c6d8  lea     rdx, [rbp+1F0h+instance]
0x18016c6df  mov     qword ptr [rsp+2F0h+var_2D0], rdx
0x18016c6e4  mov     r9, r15
0x18016c6e7  mov     r8, rdi
0x18016c6ea  mov     edx, 0D0001h
0x18016c6ef  mov     rax, [rax+30h]
0x18016c6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016c6f8  mov     ebx, eax
0x18016c6fa  test    eax, eax
0x18016c6fc  jz      short loc_18016C741
0x18016c6fe  mov     eax, cs:dword_180397B68
0x18016c704  cmp     eax, 2
0x18016c707  jbe     loc_18016C79D
0x18016c70d  mov     [rbp+1F0h+var_268], ebx
0x18016c710  mov     dword ptr [rbp+1F0h+var_250], 0C7h
0x18016c717  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016c71e  mov     [rbp+1F0h+var_270], rax
0x18016c722  lea     rax, [rbp+1F0h+var_268]
0x18016c726  mov     [rsp+2F0h+var_2C0], rax
0x18016c72b  lea     rax, [rbp+1F0h+var_250]
0x18016c72f  mov     [rsp+2F0h+var_2C8], rax
0x18016c734  lea     rax, [rbp+1F0h+var_270]
0x18016c738  lea     rdx, word_18035D02A
0x18016c73f  jmp     short loc_18016C793
0x18016c741  lea     rdx, [rbp+1F0h+instance]
0x18016c748  mov     rcx, rdi; self
0x18016c74b  call    MI_Instance_Destruct
0x18016c750  mov     ebx, eax
0x18016c752  test    eax, eax
0x18016c754  jz      short loc_18016C79D
0x18016c756  mov     eax, cs:dword_180397B68
0x18016c75c  cmp     eax, 2
0x18016c75f  jbe     short loc_18016C79D
0x18016c761  mov     [rbp+1F0h+var_264], ebx
0x18016c764  mov     dword ptr [rbp+1F0h+var_270], 0CFh
0x18016c76b  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18016c772  mov     [rbp+1F0h+var_250], rax
0x18016c776  lea     rax, [rbp+1F0h+var_264]
0x18016c77a  mov     [rsp+2F0h+var_2C0], rax
0x18016c77f  lea     rax, [rbp+1F0h+var_270]
0x18016c783  mov     [rsp+2F0h+var_2C8], rax
0x18016c788  lea     rax, [rbp+1F0h+var_250]
0x18016c78c  lea     rdx, byte_18035DC37
0x18016c793  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18016c798  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18016c79d  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18016c7a4  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18016c7a9  jmp     short loc_18016C7AE
0x18016c7ab  xor     r12d, r12d
0x18016c7ae  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18016c7b2  mov     [rsp+2F0h+var_2C8], r12; unsigned __int16 *
0x18016c7b7  mov     [rsp+2F0h+var_2D0], ebx; enum _MI_Result
0x18016c7bb  lea     r9, [rbp+1F0h+var_130]; struct _MI_ConstUint32Field *
0x18016c7c2  mov     rdx, [rbp+1F0h+var_230]; unsigned __int16 *
0x18016c7c6  mov     rcx, [rbp+1F0h+var_228]; unsigned __int16 *
0x18016c7ca  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18016c7cf  test    r13d, r13d
0x18016c7d2  jnz     loc_18016C98F
0x18016c7d8  lea     rcx, [rbp+1F0h+var_218]; this
0x18016c7dc  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18016c7e1  mov     eax, cs:dword_180397B68
0x18016c7e7  cmp     eax, 5
0x18016c7ea  jbe     loc_18016C98F
0x18016c7f0  mov     rdx, 400000000000h
0x18016c7fa  lea     rcx, dword_180397B68
0x18016c801  call    _tlgKeywordOn
0x18016c806  test    al, al
0x18016c808  jz      loc_18016C98F
0x18016c80e  cmp     [r15+80h], r12b
0x18016c815  jz      short loc_18016C81D
0x18016c817  mov     eax, [r15+78h]
0x18016c81b  jmp     short loc_18016C820
0x18016c81d  mov     eax, r12d
0x18016c820  mov     dword ptr [rbp+1F0h+var_270], eax
0x18016c823  cmp     [rbp+1F0h+var_88], r12b
0x18016c82a  jz      short loc_18016C867
0x18016c82c  mov     rax, [rbp+1F0h+var_90]
0x18016c833  movups  xmm0, xmmword ptr [rax]
0x18016c836  movaps  xmmword ptr [rbp+1F0h+var_1E0.ft], xmm0
0x18016c83a  movups  xmm1, xmmword ptr [rax+10h]
0x18016c83e  movaps  xmmword ptr [rbp+1F0h+var_1E0.serverName], xmm1
0x18016c842  movups  xmm0, xmmword ptr [rax+20h]
0x18016c846  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved], xmm0
0x18016c84a  movups  xmm1, xmmword ptr [rax+30h]
0x18016c84e  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved+10h], xmm1
0x18016c852  xor     r8d, r8d; unsigned __int16 *
0x18016c855  lea     rdx, [rbp+1F0h+var_1E0]; struct _MI_Instance
0x18016c859  lea     rcx, name; "ObjectId"
0x18016c860  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18016c865  jmp     short loc_18016C86A
0x18016c867  mov     rax, r12
0x18016c86a  mov     [rbp+1F0h+var_228], rax
0x18016c86e  cmp     [rbp+1F0h+var_98], r12b
0x18016c875  jz      short loc_18016C8B2
0x18016c877  mov     rax, [rbp+1F0h+var_A0]
0x18016c87e  movups  xmm0, xmmword ptr [rax]
0x18016c881  movaps  xmmword ptr [rbp+1F0h+var_1E0.ft], xmm0
0x18016c885  movups  xmm1, xmmword ptr [rax+10h]
0x18016c889  movaps  xmmword ptr [rbp+1F0h+var_1E0.serverName], xmm1
0x18016c88d  movups  xmm0, xmmword ptr [rax+20h]
0x18016c891  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved], xmm0
0x18016c895  movups  xmm1, xmmword ptr [rax+30h]
0x18016c899  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved+10h], xmm1
0x18016c89d  xor     r8d, r8d; unsigned __int16 *
0x18016c8a0  lea     rdx, [rbp+1F0h+var_1E0]; struct _MI_Instance
0x18016c8a4  lea     rcx, name; "ObjectId"
0x18016c8ab  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18016c8b0  jmp     short loc_18016C8B5
0x18016c8b2  mov     rax, r12
0x18016c8b5  mov     [rbp+1F0h+var_230], rax
0x18016c8b9  lea     rax, aStoragepool_0; "StoragePool"
0x18016c8c0  mov     [rbp+1F0h+var_238], rax
0x18016c8c4  mov     rax, [rbp+1F0h+var_210]
0x18016c8c8  sub     rax, [rbp+1F0h+var_218]
0x18016c8cc  imul    rax, 3E8h
0x18016c8d3  xor     edx, edx
0x18016c8d5  div     [rbp+1F0h+var_208]
0x18016c8d9  mov     [rbp+1F0h+var_240], rax
0x18016c8dd  mov     [rbp+1F0h+var_264], ebx
0x18016c8e0  mov     al, [rbp+1F0h+var_130.exists]
0x18016c8e6  neg     al
0x18016c8e8  sbb     ecx, ecx
0x18016c8ea  and     ecx, [rbp+1F0h+var_130.value]
0x18016c8f0  mov     dword ptr [rbp+1F0h+var_250], ecx
0x18016c8f3  mov     [rbp+1F0h+var_268], r14d
0x18016c8f7  cmp     [rsi+48h], r12b
0x18016c8fb  jz      short loc_18016C903
0x18016c8fd  mov     rax, [rsi+40h]
0x18016c901  jmp     short loc_18016C906
0x18016c903  mov     rax, r12
0x18016c906  mov     [rbp+1F0h+var_248], rax
0x18016c90a  lea     rax, aCreatestoragep; "CreateStoragePool"
0x18016c911  mov     [rbp+1F0h+var_258], rax
0x18016c915  lea     rax, aStoragesubsyst_3; "StorageSubsystem"
0x18016c91c  mov     [rbp+1F0h+var_220], rax
0x18016c920  lea     rax, [rbp+1F0h+var_270]
0x18016c924  mov     [rsp+2F0h+var_280], rax
0x18016c929  lea     rax, [rbp+1F0h+var_228]
0x18016c92d  mov     [rsp+2F0h+var_288], rax
0x18016c932  lea     rax, [rbp+1F0h+var_230]
0x18016c936  mov     [rsp+2F0h+var_290], rax
0x18016c93b  lea     rax, [rbp+1F0h+var_238]
0x18016c93f  mov     [rsp+2F0h+var_298], rax
0x18016c944  lea     rax, [rbp+1F0h+var_240]
0x18016c948  mov     [rsp+2F0h+var_2A0], rax
0x18016c94d  lea     rax, [rbp+1F0h+var_264]
0x18016c951  mov     [rsp+2F0h+var_2A8], rax
0x18016c956  lea     rax, [rbp+1F0h+var_250]
0x18016c95a  mov     [rsp+2F0h+var_2B0], rax
0x18016c95f  lea     rax, [rbp+1F0h+var_268]
0x18016c963  mov     [rsp+2F0h+var_2B8], rax
  ... truncated ...
```
