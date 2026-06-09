# SPACES_StoragePool_Invoke_CreateVolume2

- ea: `0x180157a80`
- end: `0x180158097`
- name: `SPACES_StoragePool_Invoke_CreateVolume2`
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
- `0x180157a80`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180157afd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180157b5c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180158067`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180157afd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180157b5c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180158067`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180157b20`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180157b20`

## string_xrefs

- `0x180157f6f`: `CreateVolume`
- `0x180157b68`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x180157ca3`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x180157dd8`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x180157e07`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x180157e1c`: `SPACES_StoragePool_Invoke_CreateVolume2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVolume2(
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
  int *v20; // rdx
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
  struct _MI_Instance *v52; // [rsp+278h] [rbp+178h]
  char v53; // [rsp+280h] [rbp+180h]
  struct _MI_Instance *v54; // [rsp+288h] [rbp+188h]
  char v55; // [rsp+290h] [rbp+190h]
  GUID ActivityId; // [rsp+2B0h] [rbp+1B0h] BYREF
  GUID v57; // [rsp+2C0h] [rbp+1C0h]
  GUID v58; // [rsp+2D0h] [rbp+1D0h] BYREF

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
    v33 = 602;
    v32 = "SPACES_StoragePool_Invoke_CreateVolume2";
    v31 = (unsigned __int16 *)&v33;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StoragePool_Invoke_CreateVolume2",
      (__int64)byte_180356449,
      v11,
      v12,
      &v32);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x120u);
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
      v38 = 634;
      v20 = (int *)&unk_180356358;
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVolume2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        LODWORD(v41) = v15;
        LODWORD(v42) = 653;
        v20 = &dword_18035479C;
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v35 + 48LL))(
                v35,
                720917,
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
          LODWORD(v32) = 672;
          v36 = "SPACES_StoragePool_Invoke_CreateVolume2";
          v21 = &v36;
          v20 = (int *)byte_180354B89;
          goto LABEL_14;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        LODWORD(v43) = v15;
        LODWORD(v36) = 664;
        v20 = &dword_1803553D4;
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_27;
      LODWORD(v39) = 7;
      LODWORD(v40) = 645;
      v20 = (int *)&unk_180356CE8;
    }
    v21 = &v32;
    v32 = "SPACES_StoragePool_Invoke_CreateVolume2";
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
        v43 = "Volume";
        v42 = (unsigned __int64)(1000LL * (v45[1] - v45[0])) / v45[2];
        LODWORD(v32) = v15;
        v34 = v51.exists != 0 ? v51.value : 0;
        LODWORD(v36) = v13;
        if ( a6[4].exists )
          v26 = a6[4].value;
        else
          v26 = 0;
        v41 = v26;
        v40 = "CreateVolume";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (__int64)&dword_180356BD4,
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
    LODWORD(v32) = 705;
    v37 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVolume2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)&dword_1803554AC,
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
0x180157a80  mov     [rsp-8+arg_10], rbx
0x180157a85  push    rbp
0x180157a86  push    rsi
0x180157a87  push    rdi
0x180157a88  push    r12
0x180157a8a  push    r13
0x180157a8c  push    r14
0x180157a8e  push    r15
0x180157a90  lea     rbp, [rsp-1F0h]
0x180157a98  sub     rsp, 2F0h
0x180157a9f  mov     rax, cs:__security_cookie
0x180157aa6  xor     rax, rsp
0x180157aa9  mov     [rbp+220h+var_40], rax
0x180157ab0  mov     [rbp+220h+var_290], r9
0x180157ab4  mov     rdi, rdx
0x180157ab7  mov     r14, rcx
0x180157aba  mov     rax, [rbp+220h+arg_20]
0x180157ac1  mov     [rbp+220h+var_258], rax
0x180157ac5  mov     rsi, [rbp+220h+arg_28]
0x180157acc  mov     r13, [rbp+220h+arg_30]
0x180157ad3  xorps   xmm0, xmm0
0x180157ad6  xor     eax, eax
0x180157ad8  movups  xmmword ptr [rbp+220h+value], xmm0
0x180157adc  movups  xmmword ptr [rbp+220h+value+10h], xmm0
0x180157ae0  mov     qword ptr [rbp+220h+value+20h], rax
0x180157ae4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180157aeb  movdqu  xmmword ptr [rbp+220h+ActivityId.Data1], xmm0
0x180157af3  lea     rdx, [rbp+220h+ActivityId]; ActivityId
0x180157afa  lea     ecx, [rax+1]; ControlCode
0x180157afd  call    cs:__imp_EventActivityIdControl
0x180157b03  lea     r9, [rbp+220h+value]; value
0x180157b07  mov     rcx, rdi; context
0x180157b0a  call    MI_Context_GetCustomOption_1
0x180157b0f  xor     ebx, ebx
0x180157b11  test    eax, eax
0x180157b13  jnz     short loc_180157B26
0x180157b15  lea     rdx, [rbp+220h+ActivityId]; pclsid
0x180157b1c  mov     rcx, qword ptr [rbp+220h+value]; lpsz
0x180157b20  call    cs:__imp_CLSIDFromString
0x180157b26  mov     rcx, qword ptr [rbp+220h+ActivityId.Data1]
0x180157b2d  mov     [rbp+220h+var_60], rcx
0x180157b34  mov     rax, qword ptr [rbp+220h+ActivityId.Data4]
0x180157b3b  mov     [rbp+220h+var_58], rax
0x180157b42  mov     qword ptr [rbp+220h+var_50.Data1], rcx
0x180157b49  mov     qword ptr [rbp+220h+var_50.Data4], rax
0x180157b50  lea     rdx, [rbp+220h+var_50]; ActivityId
0x180157b57  mov     ecx, 4; ControlCode
0x180157b5c  call    cs:__imp_EventActivityIdControl
0x180157b62  mov     eax, cs:dword_180397B68
0x180157b68  lea     rcx, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x180157b6f  cmp     eax, 5
0x180157b72  jbe     short loc_180157BA1
0x180157b74  mov     [rsp+320h+var_2A8], 25Ah
0x180157b7c  mov     [rsp+320h+var_2B0], rcx
0x180157b81  lea     rax, [rsp+320h+var_2A8]
0x180157b86  mov     [rsp+320h+var_2F8], rax
0x180157b8b  lea     rax, [rsp+320h+var_2B0]
0x180157b90  mov     qword ptr [rsp+320h+var_300], rax
0x180157b95  lea     rdx, byte_180356449
0x180157b9c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180157ba1  mov     [rbp+220h+instance.ft], rbx
0x180157ba8  xor     edx, edx; Val
0x180157baa  mov     r8d, 120h; Size
0x180157bb0  lea     rcx, [rbp+220h+instance.classDecl]; void *
0x180157bb7  call    memset_0
0x180157bbc  xorps   xmm0, xmm0
0x180157bbf  xor     eax, eax
0x180157bc1  movups  [rbp+220h+var_230], xmm0
0x180157bc5  mov     [rbp+220h+var_220], rax
0x180157bc9  mov     [rbp+220h+var_2A0], rbx
0x180157bcd  lea     rcx, [rbp+220h+var_2A0]
0x180157bd1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180157bd6  mov     [rbp+220h+var_2A0], rbx
0x180157bda  mov     r15d, ebx
0x180157bdd  lea     rcx, [rbp+220h+var_250]; this
0x180157be1  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180157be6  mov     rcx, rdi; context
0x180157be9  call    WspIsRemoteRequest
0x180157bee  mov     r12d, eax
0x180157bf1  test    eax, eax
0x180157bf3  jnz     short loc_180157C18
0x180157bf5  lea     rcx, [rbp+220h+var_250]; this
0x180157bf9  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180157bfe  cmp     [rsi+48h], bl
0x180157c01  jz      short loc_180157C15
0x180157c03  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180157c07  call    WspIsRemoteInstance
0x180157c0c  test    al, al
0x180157c0e  lea     r15d, [r12+1]
0x180157c13  jnz     short loc_180157C18
0x180157c15  mov     r15d, ebx
0x180157c18  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180157c1f  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180157c24  mov     ebx, eax
0x180157c26  test    eax, eax
0x180157c28  jnz     loc_180157E1C
0x180157c2e  mov     dword ptr [rbp+220h+var_230], 0Bh
0x180157c35  mov     rax, [rsi+40h]
0x180157c39  mov     qword ptr [rbp+220h+var_230+8], rax
0x180157c3d  mov     rbx, [r14]
0x180157c40  lea     rcx, [rbp+220h+var_2A0]
0x180157c44  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180157c49  mov     [rsp+320h+var_300], 1; int
0x180157c51  lea     r9, [rbp+220h+var_2A0]; struct ISpWmiObject **
0x180157c55  lea     r8, [rbp+220h+var_230]; struct _SP_OBJECT_ID *
0x180157c59  mov     rdx, rdi; context
0x180157c5c  mov     rcx, rbx; this
0x180157c5f  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180157c64  mov     ebx, eax
0x180157c66  test    eax, eax
0x180157c68  jz      short loc_180157CBE
0x180157c6a  mov     eax, cs:dword_180397B68
0x180157c70  cmp     eax, 2
0x180157c73  jbe     loc_180157E07
0x180157c79  mov     [rsp+320h+var_2A8], ebx
0x180157c7d  mov     [rbp+220h+var_288], 27Ah
0x180157c84  lea     rax, [rsp+320h+var_2A8]
0x180157c89  mov     [rsp+320h+var_2F0], rax
0x180157c8e  lea     rax, [rbp+220h+var_288]
0x180157c92  lea     rdx, unk_180356358
0x180157c99  mov     [rsp+320h+var_2F8], rax
0x180157c9e  lea     rax, [rsp+320h+var_2B0]
0x180157ca3  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x180157caa  mov     [rsp+320h+var_2B0], r13
0x180157caf  mov     qword ptr [rsp+320h+var_300], rax
0x180157cb4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180157cb9  jmp     loc_180157E0E
0x180157cbe  mov     r8, [rsi+40h]
0x180157cc2  mov     rdx, rdi
0x180157cc5  mov     rcx, [r14]
0x180157cc8  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180157ccd  test    eax, eax
0x180157ccf  jnz     short loc_180157D03
0x180157cd1  lea     ebx, [rax+7]
0x180157cd4  mov     eax, cs:dword_180397B68
0x180157cda  cmp     eax, 2
0x180157cdd  jbe     loc_180157E07
0x180157ce3  mov     dword ptr [rbp+220h+var_280], ebx
0x180157ce6  mov     dword ptr [rbp+220h+var_278], 285h
0x180157ced  lea     rax, [rbp+220h+var_280]
0x180157cf1  mov     [rsp+320h+var_2F0], rax
0x180157cf6  lea     rax, [rbp+220h+var_278]
0x180157cfa  lea     rdx, unk_180356CE8
0x180157d01  jmp     short loc_180157C99
0x180157d03  lea     r8, [rbp+220h+instance]; instance
0x180157d0a  lea     rdx, SPACES_StoragePool_CreateVolume2_rtti; methodDecl
0x180157d11  mov     rcx, rdi; context
0x180157d14  call    MI_Context_ConstructParameters
0x180157d19  mov     ebx, eax
0x180157d1b  test    eax, eax
0x180157d1d  jz      short loc_180157D51
0x180157d1f  mov     eax, cs:dword_180397B68
0x180157d25  cmp     eax, 2
0x180157d28  jbe     loc_180157E07
0x180157d2e  mov     dword ptr [rbp+220h+var_270], ebx
0x180157d31  mov     dword ptr [rbp+220h+var_268], 28Dh
0x180157d38  lea     rax, [rbp+220h+var_270]
0x180157d3c  mov     [rsp+320h+var_2F0], rax
0x180157d41  lea     rax, [rbp+220h+var_268]
0x180157d45  lea     rdx, dword_18035479C
0x180157d4c  jmp     loc_180157C99
0x180157d51  mov     rcx, [rbp+220h+var_2A0]
0x180157d55  mov     rax, [rcx]
0x180157d58  lea     rdx, [rbp+220h+instance]
0x180157d5f  mov     qword ptr [rsp+320h+var_300], rdx
0x180157d64  mov     r9, r13
0x180157d67  mov     r8, rdi
0x180157d6a  mov     edx, 0B0015h
0x180157d6f  mov     rax, [rax+30h]
0x180157d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157d78  mov     ebx, eax
0x180157d7a  test    eax, eax
0x180157d7c  jz      short loc_180157DAC
0x180157d7e  mov     eax, cs:dword_180397B68
0x180157d84  cmp     eax, 2
0x180157d87  jbe     short loc_180157E07
0x180157d89  mov     dword ptr [rbp+220h+var_260], ebx
0x180157d8c  mov     dword ptr [rbp+220h+var_298], 298h
0x180157d93  lea     rax, [rbp+220h+var_260]
0x180157d97  mov     [rsp+320h+var_2F0], rax
0x180157d9c  lea     rax, [rbp+220h+var_298]
0x180157da0  lea     rdx, dword_1803553D4
0x180157da7  jmp     loc_180157C99
0x180157dac  lea     rdx, [rbp+220h+instance]
0x180157db3  mov     rcx, rdi; self
0x180157db6  call    MI_Instance_Destruct
0x180157dbb  mov     ebx, eax
0x180157dbd  test    eax, eax
0x180157dbf  jz      short loc_180157E07
0x180157dc1  mov     eax, cs:dword_180397B68
0x180157dc7  cmp     eax, 2
0x180157dca  jbe     short loc_180157E07
0x180157dcc  mov     [rsp+320h+var_2A4], ebx
0x180157dd0  mov     dword ptr [rsp+320h+var_2B0], 2A0h
0x180157dd8  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x180157ddf  mov     [rbp+220h+var_298], r13
0x180157de3  lea     rax, [rsp+320h+var_2A4]
0x180157de8  mov     [rsp+320h+var_2F0], rax
0x180157ded  lea     rax, [rsp+320h+var_2B0]
0x180157df2  mov     [rsp+320h+var_2F8], rax
0x180157df7  lea     rax, [rbp+220h+var_298]
0x180157dfb  lea     rdx, byte_180354B89
0x180157e02  jmp     loc_180157CAF
0x180157e07  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x180157e0e  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180157e15  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180157e1a  jmp     short loc_180157E23
0x180157e1c  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x180157e23  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x180157e27  xor     r14d, r14d
0x180157e2a  mov     [rsp+320h+var_2F8], r14; unsigned __int16 *
0x180157e2f  mov     [rsp+320h+var_300], ebx; enum _MI_Result
0x180157e33  lea     r9, [rbp+220h+var_160]; struct _MI_ConstUint32Field *
0x180157e3a  mov     rdx, [rbp+220h+var_258]; unsigned __int16 *
0x180157e3e  mov     rcx, [rbp+220h+var_290]; unsigned __int16 *
0x180157e42  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180157e47  test    r12d, r12d
0x180157e4a  jnz     loc_180157FED
0x180157e50  lea     rcx, [rbp+220h+var_250]; this
0x180157e54  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180157e59  mov     eax, cs:dword_180397B68
0x180157e5f  cmp     eax, 5
0x180157e62  jbe     loc_180157FED
0x180157e68  mov     rdx, 400000000000h
0x180157e72  lea     rcx, dword_180397B68
0x180157e79  call    _tlgKeywordOn
0x180157e7e  test    al, al
0x180157e80  jz      loc_180157FED
0x180157e86  cmp     [rbp+220h+var_90], r14b
0x180157e8d  jz      short loc_180157ECA
0x180157e8f  mov     rax, [rbp+220h+var_98]
0x180157e96  movups  xmm0, xmmword ptr [rax]
0x180157e99  movaps  xmmword ptr [rbp+220h+var_210.ft], xmm0
0x180157e9d  movups  xmm1, xmmword ptr [rax+10h]
0x180157ea1  movaps  xmmword ptr [rbp+220h+var_210.serverName], xmm1
0x180157ea5  movups  xmm0, xmmword ptr [rax+20h]
0x180157ea9  movaps  xmmword ptr [rbp+220h+var_210.reserved], xmm0
0x180157ead  movups  xmm1, xmmword ptr [rax+30h]
0x180157eb1  movaps  xmmword ptr [rbp+220h+var_210.reserved+10h], xmm1
0x180157eb5  xor     r8d, r8d; unsigned __int16 *
0x180157eb8  lea     rdx, [rbp+220h+var_210]; struct _MI_Instance
0x180157ebc  lea     rcx, name; "ObjectId"
0x180157ec3  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180157ec8  jmp     short loc_180157ECD
0x180157eca  mov     rax, r14
0x180157ecd  mov     [rbp+220h+var_290], rax
0x180157ed1  cmp     [rbp+220h+var_A0], r14b
0x180157ed8  jz      short loc_180157F15
0x180157eda  mov     rax, [rbp+220h+var_A8]
0x180157ee1  movups  xmm0, xmmword ptr [rax]
0x180157ee4  movaps  xmmword ptr [rbp+220h+var_210.ft], xmm0
0x180157ee8  movups  xmm1, xmmword ptr [rax+10h]
0x180157eec  movaps  xmmword ptr [rbp+220h+var_210.serverName], xmm1
0x180157ef0  movups  xmm0, xmmword ptr [rax+20h]
0x180157ef4  movaps  xmmword ptr [rbp+220h+var_210.reserved], xmm0
0x180157ef8  movups  xmm1, xmmword ptr [rax+30h]
0x180157efc  movaps  xmmword ptr [rbp+220h+var_210.reserved+10h], xmm1
0x180157f00  xor     r8d, r8d; unsigned __int16 *
0x180157f03  lea     rdx, [rbp+220h+var_210]; struct _MI_Instance
0x180157f07  lea     rcx, name; "ObjectId"
0x180157f0e  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180157f13  jmp     short loc_180157F18
0x180157f15  mov     rax, r14
0x180157f18  mov     [rbp+220h+var_258], rax
0x180157f1c  lea     rax, aVolume_1; "Volume"
0x180157f23  mov     [rbp+220h+var_260], rax
0x180157f27  mov     rax, [rbp+220h+var_248]
0x180157f2b  sub     rax, [rbp+220h+var_250]
0x180157f2f  imul    rax, 3E8h
0x180157f36  xor     edx, edx
0x180157f38  div     [rbp+220h+var_240]
0x180157f3c  mov     [rbp+220h+var_268], rax
0x180157f40  mov     dword ptr [rsp+320h+var_2B0], ebx
0x180157f44  mov     al, [rbp+220h+var_160.exists]
0x180157f4a  neg     al
0x180157f4c  sbb     ecx, ecx
0x180157f4e  and     ecx, [rbp+220h+var_160.value]
0x180157f54  mov     [rsp+320h+var_2A4], ecx
0x180157f58  mov     dword ptr [rbp+220h+var_298], r15d
0x180157f5c  cmp     [rsi+48h], r14b
0x180157f60  jz      short loc_180157F68
0x180157f62  mov     rax, [rsi+40h]
0x180157f66  jmp     short loc_180157F6B
0x180157f68  mov     rax, r14
0x180157f6b  mov     [rbp+220h+var_270], rax
0x180157f6f  lea     rax, aCreatevolume_0; "CreateVolume"
0x180157f76  mov     [rbp+220h+var_278], rax
0x180157f7a  lea     rax, aStoragepool_0; "StoragePool"
0x180157f81  mov     [rbp+220h+var_280], rax
0x180157f85  lea     rax, [rbp+220h+var_290]
0x180157f89  mov     [rsp+320h+var_2B8], rax
0x180157f8e  lea     rax, [rbp+220h+var_258]
0x180157f92  mov     [rsp+320h+var_2C0], rax
0x180157f97  lea     rax, [rbp+220h+var_260]
0x180157f9b  mov     [rsp+320h+var_2C8], rax
0x180157fa0  lea     rax, [rbp+220h+var_268]
0x180157fa4  mov     [rsp+320h+var_2D0], rax
0x180157fa9  lea     rax, [rsp+320h+var_2B0]
0x180157fae  mov     [rsp+320h+var_2D8], rax
0x180157fb3  lea     rax, [rsp+320h+var_2A4]
  ... truncated ...
```
