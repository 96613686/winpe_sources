# SPACES_StoragePool_Invoke_CreateStorageTier

- ea: `0x1801550c0`
- end: `0x180155677`
- name: `SPACES_StoragePool_Invoke_CreateStorageTier`
- size: `1463`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
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
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x1801550c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015513d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015519c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155647`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015513d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015519c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180155647`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180155160`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180155160`

## string_xrefs

- `0x1801551a8`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x1801552d4`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x1801553bd`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x1801553ec`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x180155401`: `SPACES_StoragePool_Invoke_CreateStorageTier`
- `0x180155552`: `CreateStorageTier`

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
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r14d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  char *v20; // rdx
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
  MI_Uint32 v33; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v34; // [rsp+80h] [rbp-80h] BYREF
  const char *v35; // [rsp+88h] [rbp-78h] BYREF
  const char *v36; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v37; // [rsp+98h] [rbp-68h] BYREF
  const char *v38; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v39; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v40; // [rsp+B0h] [rbp-50h] BYREF
  const char *v41; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v42; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v43[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v44; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v45; // [rsp+F8h] [rbp-8h]
  struct _MI_Instance v46; // [rsp+100h] [rbp+0h] BYREF
  MI_Value value; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+170h] [rbp+70h] BYREF
  struct _MI_ConstUint32Field v49; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _MI_Instance *v50; // [rsp+1E0h] [rbp+E0h]
  char v51; // [rsp+1E8h] [rbp+E8h]
  struct _MI_Instance *v52; // [rsp+1F0h] [rbp+F0h]
  char v53; // [rsp+1F8h] [rbp+F8h]
  GUID ActivityId; // [rsp+210h] [rbp+110h] BYREF
  GUID v55; // [rsp+220h] [rbp+120h]
  GUID v56; // [rsp+230h] [rbp+130h] BYREF

  v37 = a4;
  v42 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v55 = ActivityId;
  v56 = ActivityId;
  EventActivityIdControl(4u, &v56);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v35) = 722;
    v32 = "SPACES_StoragePool_Invoke_CreateStorageTier";
    v31 = (unsigned __int16 *)&v35;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StoragePool_Invoke_CreateStorageTier",
      (__int64)word_18035632A,
      v11,
      v12,
      &v32);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x98u);
  v44 = 0;
  v45 = 0;
  v34 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v34);
  v34 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v43);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v43);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v44) = 11;
    *((_QWORD *)&v44 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v34);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v44, &v34, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
      {
LABEL_24:
        MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
        goto LABEL_25;
      }
      LODWORD(v35) = v15;
      LODWORD(v38) = 753;
      v20 = byte_180356801;
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateStorageTier_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_24;
        LODWORD(v39) = v15;
        LODWORD(v40) = 761;
        v20 = (char *)&word_180356756;
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v34 + 48LL))(
                v34,
                720908,
                a2,
                a7,
                &instance,
                v31);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_24;
          v33 = v15;
          LODWORD(v32) = 780;
          v36 = "SPACES_StoragePool_Invoke_CreateStorageTier";
          v21 = &v36;
          v20 = (char *)&dword_180357084;
          goto LABEL_14;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_24;
        LODWORD(v41) = v15;
        LODWORD(v36) = 772;
        v20 = byte_18035590B;
      }
    }
    v21 = &v32;
    v32 = "SPACES_StoragePool_Invoke_CreateStorageTier";
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (__int64)v20,
      v18,
      v19,
      v21);
    goto LABEL_24;
  }
LABEL_25:
  SmLogOnMethodFailure(v37, v42, a6 + 4, &v49, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v43);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( v53 )
        {
          v46 = *v52;
          v24 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v46, 0);
        }
        else
        {
          v24 = 0;
        }
        v37 = v24;
        if ( v51 )
        {
          v46 = *v50;
          v25 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v46, 0);
        }
        else
        {
          v25 = 0;
        }
        v42 = v25;
        v41 = "StorageTier";
        v40 = (unsigned __int64)(1000LL * (v43[1] - v43[0])) / v43[2];
        LODWORD(v32) = v15;
        v33 = v49.exists != 0 ? v49.value : 0;
        LODWORD(v36) = v13;
        if ( a6[4].exists )
          v26 = a6[4].value;
        else
          v26 = 0;
        v39 = v26;
        v38 = "CreateStorageTier";
        v35 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v49.exists != 0 ? v49.value : 0,
          (__int64)&unk_180354A98,
          v22,
          v23,
          &v35,
          &v38,
          &v39,
          (__int64)&v36,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v40,
          &v41,
          &v42,
          &v37);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v32) = 813;
    v37 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateStorageTier";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)byte_1803568A1,
      v28,
      v29,
      &v37);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v43);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v34);
  return EventActivityIdControl(4u, &v56);
}

```

## disassembly

```asm
0x1801550c0  mov     [rsp-8+arg_10], rbx
0x1801550c5  push    rbp
0x1801550c6  push    rsi
0x1801550c7  push    rdi
0x1801550c8  push    r12
0x1801550ca  push    r13
0x1801550cc  push    r14
0x1801550ce  push    r15
0x1801550d0  lea     rbp, [rsp-150h]
0x1801550d8  sub     rsp, 250h
0x1801550df  mov     rax, cs:__security_cookie
0x1801550e6  xor     rax, rsp
0x1801550e9  mov     [rbp+180h+var_40], rax
0x1801550f0  mov     [rbp+180h+var_1E8], r9
0x1801550f4  mov     rdi, rdx
0x1801550f7  mov     r15, rcx
0x1801550fa  mov     rax, [rbp+180h+arg_20]
0x180155101  mov     [rbp+180h+var_1C0], rax
0x180155105  mov     rsi, [rbp+180h+arg_28]
0x18015510c  mov     r13, [rbp+180h+arg_30]
0x180155113  xorps   xmm0, xmm0
0x180155116  xor     eax, eax
0x180155118  movups  xmmword ptr [rbp+180h+value], xmm0
0x18015511c  movups  xmmword ptr [rbp+180h+value+10h], xmm0
0x180155120  mov     qword ptr [rbp+180h+value+20h], rax
0x180155124  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015512b  movdqu  xmmword ptr [rbp+180h+ActivityId.Data1], xmm0
0x180155133  lea     rdx, [rbp+180h+ActivityId]; ActivityId
0x18015513a  lea     ecx, [rax+1]; ControlCode
0x18015513d  call    cs:__imp_EventActivityIdControl
0x180155143  lea     r9, [rbp+180h+value]; value
0x180155147  mov     rcx, rdi; context
0x18015514a  call    MI_Context_GetCustomOption_1
0x18015514f  xor     ebx, ebx
0x180155151  test    eax, eax
0x180155153  jnz     short loc_180155166
0x180155155  lea     rdx, [rbp+180h+ActivityId]; pclsid
0x18015515c  mov     rcx, qword ptr [rbp+180h+value]; lpsz
0x180155160  call    cs:__imp_CLSIDFromString
0x180155166  mov     rcx, qword ptr [rbp+180h+ActivityId.Data1]
0x18015516d  mov     [rbp+180h+var_60], rcx
0x180155174  mov     rax, qword ptr [rbp+180h+ActivityId.Data4]
0x18015517b  mov     [rbp+180h+var_58], rax
0x180155182  mov     qword ptr [rbp+180h+var_50.Data1], rcx
0x180155189  mov     qword ptr [rbp+180h+var_50.Data4], rax
0x180155190  lea     rdx, [rbp+180h+var_50]; ActivityId
0x180155197  mov     ecx, 4; ControlCode
0x18015519c  call    cs:__imp_EventActivityIdControl
0x1801551a2  mov     eax, cs:dword_180397B68
0x1801551a8  lea     rcx, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801551af  cmp     eax, 5
0x1801551b2  jbe     short loc_1801551DF
0x1801551b4  mov     dword ptr [rbp+180h+var_1F8], 2D2h
0x1801551bb  mov     [rsp+280h+var_210], rcx
0x1801551c0  lea     rax, [rbp+180h+var_1F8]
0x1801551c4  mov     [rsp+280h+var_258], rax
0x1801551c9  lea     rax, [rsp+280h+var_210]
0x1801551ce  mov     qword ptr [rsp+280h+var_260], rax
0x1801551d3  lea     rdx, word_18035632A
0x1801551da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801551df  mov     [rbp+180h+instance.ft], rbx
0x1801551e3  xor     edx, edx; Val
0x1801551e5  mov     r8d, 98h; Size
0x1801551eb  lea     rcx, [rbp+180h+instance.classDecl]; void *
0x1801551ef  call    memset_0
0x1801551f4  xorps   xmm0, xmm0
0x1801551f7  xor     eax, eax
0x1801551f9  movups  [rbp+180h+var_198], xmm0
0x1801551fd  mov     [rbp+180h+var_188], rax
0x180155201  mov     [rbp+180h+var_200], rbx
0x180155205  lea     rcx, [rbp+180h+var_200]
0x180155209  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015520e  mov     [rbp+180h+var_200], rbx
0x180155212  mov     r14d, ebx
0x180155215  lea     rcx, [rbp+180h+var_1B8]; this
0x180155219  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015521e  mov     rcx, rdi; context
0x180155221  call    WspIsRemoteRequest
0x180155226  mov     r12d, eax
0x180155229  test    eax, eax
0x18015522b  jnz     short loc_180155250
0x18015522d  lea     rcx, [rbp+180h+var_1B8]; this
0x180155231  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180155236  cmp     [rsi+48h], bl
0x180155239  jz      short loc_18015524D
0x18015523b  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18015523f  call    WspIsRemoteInstance
0x180155244  test    al, al
0x180155246  lea     r14d, [r12+1]
0x18015524b  jnz     short loc_180155250
0x18015524d  mov     r14d, ebx
0x180155250  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180155257  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015525c  mov     ebx, eax
0x18015525e  test    eax, eax
0x180155260  jnz     loc_180155401
0x180155266  mov     dword ptr [rbp+180h+var_198], 0Bh
0x18015526d  mov     rax, [rsi+40h]
0x180155271  mov     qword ptr [rbp+180h+var_198+8], rax
0x180155275  mov     rbx, [r15]
0x180155278  lea     rcx, [rbp+180h+var_200]
0x18015527c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180155281  mov     [rsp+280h+var_260], 1; int
0x180155289  lea     r9, [rbp+180h+var_200]; struct ISpWmiObject **
0x18015528d  lea     r8, [rbp+180h+var_198]; struct _SP_OBJECT_ID *
0x180155291  mov     rdx, rdi; context
0x180155294  mov     rcx, rbx; this
0x180155297  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015529c  mov     ebx, eax
0x18015529e  test    eax, eax
0x1801552a0  jz      short loc_1801552F4
0x1801552a2  mov     eax, cs:dword_180397B68
0x1801552a8  cmp     eax, 2
0x1801552ab  jbe     loc_1801553EC
0x1801552b1  mov     dword ptr [rbp+180h+var_1F8], ebx
0x1801552b4  mov     dword ptr [rbp+180h+var_1E0], 2F1h
0x1801552bb  lea     rax, [rbp+180h+var_1F8]
0x1801552bf  mov     [rsp+280h+var_250], rax
0x1801552c4  lea     rax, [rbp+180h+var_1E0]
0x1801552c8  lea     rdx, byte_180356801
0x1801552cf  mov     [rsp+280h+var_258], rax
0x1801552d4  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801552db  lea     rax, [rsp+280h+var_210]
0x1801552e0  mov     [rsp+280h+var_210], r15
0x1801552e5  mov     qword ptr [rsp+280h+var_260], rax
0x1801552ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801552ef  jmp     loc_1801553F3
0x1801552f4  lea     r8, [rbp+180h+instance]; instance
0x1801552f8  lea     rdx, SPACES_StoragePool_CreateStorageTier_rtti; methodDecl
0x1801552ff  mov     rcx, rdi; context
0x180155302  call    MI_Context_ConstructParameters
0x180155307  mov     ebx, eax
0x180155309  test    eax, eax
0x18015530b  jz      short loc_18015533C
0x18015530d  mov     eax, cs:dword_180397B68
0x180155313  cmp     eax, 2
0x180155316  jbe     loc_1801553EC
0x18015531c  mov     dword ptr [rbp+180h+var_1D8], ebx
0x18015531f  mov     dword ptr [rbp+180h+var_1D0], 2F9h
0x180155326  lea     rax, [rbp+180h+var_1D8]
0x18015532a  mov     [rsp+280h+var_250], rax
0x18015532f  lea     rax, [rbp+180h+var_1D0]
0x180155333  lea     rdx, word_180356756
0x18015533a  jmp     short loc_1801552CF
0x18015533c  mov     rcx, [rbp+180h+var_200]
0x180155340  mov     rax, [rcx]
0x180155343  lea     rdx, [rbp+180h+instance]
0x180155347  mov     qword ptr [rsp+280h+var_260], rdx
0x18015534c  mov     r9, r13
0x18015534f  mov     r8, rdi
0x180155352  mov     edx, 0B000Ch
0x180155357  mov     rax, [rax+30h]
0x18015535b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155360  mov     ebx, eax
0x180155362  test    eax, eax
0x180155364  jz      short loc_180155394
0x180155366  mov     eax, cs:dword_180397B68
0x18015536c  cmp     eax, 2
0x18015536f  jbe     short loc_1801553EC
0x180155371  mov     dword ptr [rbp+180h+var_1C8], ebx
0x180155374  mov     dword ptr [rbp+180h+var_1F0], 304h
0x18015537b  lea     rax, [rbp+180h+var_1C8]
0x18015537f  mov     [rsp+280h+var_250], rax
0x180155384  lea     rax, [rbp+180h+var_1F0]
0x180155388  lea     rdx, byte_18035590B
0x18015538f  jmp     loc_1801552CF
0x180155394  lea     rdx, [rbp+180h+instance]
0x180155398  mov     rcx, rdi; self
0x18015539b  call    MI_Instance_Destruct
0x1801553a0  mov     ebx, eax
0x1801553a2  test    eax, eax
0x1801553a4  jz      short loc_1801553EC
0x1801553a6  mov     eax, cs:dword_180397B68
0x1801553ac  cmp     eax, 2
0x1801553af  jbe     short loc_1801553EC
0x1801553b1  mov     [rsp+280h+var_208], ebx
0x1801553b5  mov     dword ptr [rsp+280h+var_210], 30Ch
0x1801553bd  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801553c4  mov     [rbp+180h+var_1F0], r15
0x1801553c8  lea     rax, [rsp+280h+var_208]
0x1801553cd  mov     [rsp+280h+var_250], rax
0x1801553d2  lea     rax, [rsp+280h+var_210]
0x1801553d7  mov     [rsp+280h+var_258], rax
0x1801553dc  lea     rax, [rbp+180h+var_1F0]
0x1801553e0  lea     rdx, dword_180357084
0x1801553e7  jmp     loc_1801552E5
0x1801553ec  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x1801553f3  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801553fa  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801553ff  jmp     short loc_180155408
0x180155401  lea     r15, aSpacesStoragep_52; "SPACES_StoragePool_Invoke_CreateStorage"...
0x180155408  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18015540c  mov     [rsp+280h+var_258], 0; unsigned __int16 *
0x180155415  mov     [rsp+280h+var_260], ebx; enum _MI_Result
0x180155419  lea     r9, [rbp+180h+var_D0]; struct _MI_ConstUint32Field *
0x180155420  mov     rdx, [rbp+180h+var_1C0]; unsigned __int16 *
0x180155424  mov     rcx, [rbp+180h+var_1E8]; unsigned __int16 *
0x180155428  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015542d  test    r12d, r12d
0x180155430  jnz     loc_1801555D0
0x180155436  lea     rcx, [rbp+180h+var_1B8]; this
0x18015543a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015543f  mov     eax, cs:dword_180397B68
0x180155445  cmp     eax, 5
0x180155448  jbe     loc_1801555D0
0x18015544e  mov     rdx, 400000000000h
0x180155458  lea     rcx, dword_180397B68
0x18015545f  call    _tlgKeywordOn
0x180155464  test    al, al
0x180155466  jz      loc_1801555D0
0x18015546c  cmp     [rbp+180h+var_88], r12b
0x180155473  jz      short loc_1801554B0
0x180155475  mov     rax, [rbp+180h+var_90]
0x18015547c  movups  xmm0, xmmword ptr [rax]
0x18015547f  movaps  xmmword ptr [rbp+180h+var_180.ft], xmm0
0x180155483  movups  xmm1, xmmword ptr [rax+10h]
0x180155487  movaps  xmmword ptr [rbp+180h+var_180.serverName], xmm1
0x18015548b  movups  xmm0, xmmword ptr [rax+20h]
0x18015548f  movaps  xmmword ptr [rbp+180h+var_180.reserved], xmm0
0x180155493  movups  xmm1, xmmword ptr [rax+30h]
0x180155497  movaps  xmmword ptr [rbp+180h+var_180.reserved+10h], xmm1
0x18015549b  xor     r8d, r8d; unsigned __int16 *
0x18015549e  lea     rdx, [rbp+180h+var_180]; struct _MI_Instance
0x1801554a2  lea     rcx, name; "ObjectId"
0x1801554a9  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801554ae  jmp     short loc_1801554B2
0x1801554b0  xor     eax, eax
0x1801554b2  mov     [rbp+180h+var_1E8], rax
0x1801554b6  cmp     [rbp+180h+var_98], 0
0x1801554bd  jz      short loc_1801554FA
0x1801554bf  mov     rax, [rbp+180h+var_A0]
0x1801554c6  movups  xmm0, xmmword ptr [rax]
0x1801554c9  movaps  xmmword ptr [rbp+180h+var_180.ft], xmm0
0x1801554cd  movups  xmm1, xmmword ptr [rax+10h]
0x1801554d1  movaps  xmmword ptr [rbp+180h+var_180.serverName], xmm1
0x1801554d5  movups  xmm0, xmmword ptr [rax+20h]
0x1801554d9  movaps  xmmword ptr [rbp+180h+var_180.reserved], xmm0
0x1801554dd  movups  xmm1, xmmword ptr [rax+30h]
0x1801554e1  movaps  xmmword ptr [rbp+180h+var_180.reserved+10h], xmm1
0x1801554e5  xor     r8d, r8d; unsigned __int16 *
0x1801554e8  lea     rdx, [rbp+180h+var_180]; struct _MI_Instance
0x1801554ec  lea     rcx, name; "ObjectId"
0x1801554f3  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801554f8  jmp     short loc_1801554FC
0x1801554fa  xor     eax, eax
0x1801554fc  mov     [rbp+180h+var_1C0], rax
0x180155500  lea     rax, aStoragetier; "StorageTier"
0x180155507  mov     [rbp+180h+var_1C8], rax
0x18015550b  mov     rax, [rbp+180h+var_1B0]
0x18015550f  sub     rax, [rbp+180h+var_1B8]
0x180155513  imul    rax, 3E8h
0x18015551a  xor     edx, edx
0x18015551c  div     [rbp+180h+var_1A8]
0x180155520  mov     [rbp+180h+var_1D0], rax
0x180155524  mov     dword ptr [rsp+280h+var_210], ebx
0x180155528  mov     al, [rbp+180h+var_D0.exists]
0x18015552e  neg     al
0x180155530  sbb     ecx, ecx
0x180155532  and     ecx, [rbp+180h+var_D0.value]
0x180155538  mov     [rsp+280h+var_208], ecx
0x18015553c  mov     dword ptr [rbp+180h+var_1F0], r14d
0x180155540  cmp     byte ptr [rsi+48h], 0
0x180155544  jz      short loc_18015554C
0x180155546  mov     rax, [rsi+40h]
0x18015554a  jmp     short loc_18015554E
0x18015554c  xor     eax, eax
0x18015554e  mov     [rbp+180h+var_1D8], rax
0x180155552  lea     rax, aCreatestoraget_1; "CreateStorageTier"
0x180155559  mov     [rbp+180h+var_1E0], rax
0x18015555d  lea     rax, aStoragepool_0; "StoragePool"
0x180155564  mov     [rbp+180h+var_1F8], rax
0x180155568  lea     rax, [rbp+180h+var_1E8]
0x18015556c  mov     [rsp+280h+var_218], rax
0x180155571  lea     rax, [rbp+180h+var_1C0]
0x180155575  mov     [rsp+280h+var_220], rax
0x18015557a  lea     rax, [rbp+180h+var_1C8]
0x18015557e  mov     [rsp+280h+var_228], rax
0x180155583  lea     rax, [rbp+180h+var_1D0]
0x180155587  mov     [rsp+280h+var_230], rax
0x18015558c  lea     rax, [rsp+280h+var_210]
0x180155591  mov     [rsp+280h+var_238], rax
0x180155596  lea     rax, [rsp+280h+var_208]
0x18015559b  mov     [rsp+280h+var_240], rax
0x1801555a0  lea     rax, [rbp+180h+var_1F0]
0x1801555a4  mov     [rsp+280h+var_248], rax
0x1801555a9  lea     rax, [rbp+180h+var_1D8]
0x1801555ad  mov     [rsp+280h+var_250], rax
0x1801555b2  lea     rax, [rbp+180h+var_1E0]
0x1801555b6  mov     [rsp+280h+var_258], rax
0x1801555bb  lea     rax, [rbp+180h+var_1F8]
0x1801555bf  mov     qword ptr [rsp+280h+var_260], rax
0x1801555c4  lea     rdx, unk_180354A98
0x1801555cb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801555d0  lea     rcx, [rbp+180h+instance]; self
0x1801555d4  call    MI_Instance_Destruct
0x1801555d9  mov     eax, cs:dword_180397B68
0x1801555df  cmp     eax, 5
0x1801555e2  jbe     short loc_18015560F
0x1801555e4  mov     dword ptr [rsp+280h+var_210], 32Dh
0x1801555ec  mov     [rbp+180h+var_1E8], r15
  ... truncated ...
```
