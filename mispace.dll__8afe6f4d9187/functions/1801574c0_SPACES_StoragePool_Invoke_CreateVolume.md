# SPACES_StoragePool_Invoke_CreateVolume

- ea: `0x1801574c0`
- end: `0x180157a77`
- name: `SPACES_StoragePool_Invoke_CreateVolume`
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
- `0x1801574c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015753d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015759c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180157a47`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015753d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015759c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180157a47`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180157560`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180157560`

## string_xrefs

- `0x180157952`: `CreateVolume`
- `0x1801575a8`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x1801576d4`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x1801577bd`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x1801577ec`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x180157801`: `SPACES_StoragePool_Invoke_CreateVolume`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVolume(
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
  struct _MI_Instance *v50; // [rsp+250h] [rbp+150h]
  char v51; // [rsp+258h] [rbp+158h]
  struct _MI_Instance *v52; // [rsp+260h] [rbp+160h]
  char v53; // [rsp+268h] [rbp+168h]
  GUID ActivityId; // [rsp+280h] [rbp+180h] BYREF
  GUID v55; // [rsp+290h] [rbp+190h]
  GUID v56; // [rsp+2A0h] [rbp+1A0h] BYREF

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
    LODWORD(v35) = 495;
    v32 = "SPACES_StoragePool_Invoke_CreateVolume";
    v31 = (unsigned __int16 *)&v35;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StoragePool_Invoke_CreateVolume",
      (__int64)word_18035507A,
      v11,
      v12,
      &v32);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x108u);
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
      LODWORD(v38) = 526;
      v20 = (char *)word_180355362;
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVolume_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_24;
        LODWORD(v39) = v15;
        LODWORD(v40) = 534;
        v20 = byte_1803564DD;
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v34 + 48LL))(
                v34,
                720910,
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
          LODWORD(v32) = 553;
          v36 = "SPACES_StoragePool_Invoke_CreateVolume";
          v21 = &v36;
          v20 = (char *)&unk_180355860;
          goto LABEL_14;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_24;
        LODWORD(v41) = v15;
        LODWORD(v36) = 545;
        v20 = &byte_180354BEF;
      }
    }
    v21 = &v32;
    v32 = "SPACES_StoragePool_Invoke_CreateVolume";
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
        v41 = "Volume";
        v40 = (unsigned __int64)(1000LL * (v43[1] - v43[0])) / v43[2];
        LODWORD(v32) = v15;
        v33 = v49.exists != 0 ? v49.value : 0;
        LODWORD(v36) = v13;
        if ( a6[4].exists )
          v26 = a6[4].value;
        else
          v26 = 0;
        v39 = v26;
        v38 = "CreateVolume";
        v35 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v49.exists != 0 ? v49.value : 0,
          (__int64)byte_1803546AB,
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
    LODWORD(v32) = 586;
    v37 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)qword_180355BE0,
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
0x1801574c0  mov     [rsp-8+arg_10], rbx
0x1801574c5  push    rbp
0x1801574c6  push    rsi
0x1801574c7  push    rdi
0x1801574c8  push    r12
0x1801574ca  push    r13
0x1801574cc  push    r14
0x1801574ce  push    r15
0x1801574d0  lea     rbp, [rsp-1C0h]
0x1801574d8  sub     rsp, 2C0h
0x1801574df  mov     rax, cs:__security_cookie
0x1801574e6  xor     rax, rsp
0x1801574e9  mov     [rbp+1F0h+var_40], rax
0x1801574f0  mov     [rbp+1F0h+var_258], r9
0x1801574f4  mov     rdi, rdx
0x1801574f7  mov     r15, rcx
0x1801574fa  mov     rax, [rbp+1F0h+arg_20]
0x180157501  mov     [rbp+1F0h+var_230], rax
0x180157505  mov     rsi, [rbp+1F0h+arg_28]
0x18015750c  mov     r13, [rbp+1F0h+arg_30]
0x180157513  xorps   xmm0, xmm0
0x180157516  xor     eax, eax
0x180157518  movups  xmmword ptr [rbp+1F0h+value], xmm0
0x18015751c  movups  xmmword ptr [rbp+1F0h+value+10h], xmm0
0x180157520  mov     qword ptr [rbp+1F0h+value+20h], rax
0x180157524  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015752b  movdqu  xmmword ptr [rbp+1F0h+ActivityId.Data1], xmm0
0x180157533  lea     rdx, [rbp+1F0h+ActivityId]; ActivityId
0x18015753a  lea     ecx, [rax+1]; ControlCode
0x18015753d  call    cs:__imp_EventActivityIdControl
0x180157543  lea     r9, [rbp+1F0h+value]; value
0x180157547  mov     rcx, rdi; context
0x18015754a  call    MI_Context_GetCustomOption_1
0x18015754f  xor     ebx, ebx
0x180157551  test    eax, eax
0x180157553  jnz     short loc_180157566
0x180157555  lea     rdx, [rbp+1F0h+ActivityId]; pclsid
0x18015755c  mov     rcx, qword ptr [rbp+1F0h+value]; lpsz
0x180157560  call    cs:__imp_CLSIDFromString
0x180157566  mov     rcx, qword ptr [rbp+1F0h+ActivityId.Data1]
0x18015756d  mov     [rbp+1F0h+var_60], rcx
0x180157574  mov     rax, qword ptr [rbp+1F0h+ActivityId.Data4]
0x18015757b  mov     [rbp+1F0h+var_58], rax
0x180157582  mov     qword ptr [rbp+1F0h+var_50.Data1], rcx
0x180157589  mov     qword ptr [rbp+1F0h+var_50.Data4], rax
0x180157590  lea     rdx, [rbp+1F0h+var_50]; ActivityId
0x180157597  mov     ecx, 4; ControlCode
0x18015759c  call    cs:__imp_EventActivityIdControl
0x1801575a2  mov     eax, cs:dword_180397B68
0x1801575a8  lea     rcx, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x1801575af  cmp     eax, 5
0x1801575b2  jbe     short loc_1801575DF
0x1801575b4  mov     dword ptr [rbp+1F0h+var_268], 1EFh
0x1801575bb  mov     [rsp+2F0h+var_280], rcx
0x1801575c0  lea     rax, [rbp+1F0h+var_268]
0x1801575c4  mov     [rsp+2F0h+var_2C8], rax
0x1801575c9  lea     rax, [rsp+2F0h+var_280]
0x1801575ce  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x1801575d3  lea     rdx, word_18035507A
0x1801575da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801575df  mov     [rbp+1F0h+instance.ft], rbx
0x1801575e3  xor     edx, edx; Val
0x1801575e5  mov     r8d, 108h; Size
0x1801575eb  lea     rcx, [rbp+1F0h+instance.classDecl]; void *
0x1801575ef  call    memset_0
0x1801575f4  xorps   xmm0, xmm0
0x1801575f7  xor     eax, eax
0x1801575f9  movups  [rbp+1F0h+var_208], xmm0
0x1801575fd  mov     [rbp+1F0h+var_1F8], rax
0x180157601  mov     [rbp+1F0h+var_270], rbx
0x180157605  lea     rcx, [rbp+1F0h+var_270]
0x180157609  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015760e  mov     [rbp+1F0h+var_270], rbx
0x180157612  mov     r14d, ebx
0x180157615  lea     rcx, [rbp+1F0h+var_228]; this
0x180157619  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015761e  mov     rcx, rdi; context
0x180157621  call    WspIsRemoteRequest
0x180157626  mov     r12d, eax
0x180157629  test    eax, eax
0x18015762b  jnz     short loc_180157650
0x18015762d  lea     rcx, [rbp+1F0h+var_228]; this
0x180157631  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180157636  cmp     [rsi+48h], bl
0x180157639  jz      short loc_18015764D
0x18015763b  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18015763f  call    WspIsRemoteInstance
0x180157644  test    al, al
0x180157646  lea     r14d, [r12+1]
0x18015764b  jnz     short loc_180157650
0x18015764d  mov     r14d, ebx
0x180157650  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180157657  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015765c  mov     ebx, eax
0x18015765e  test    eax, eax
0x180157660  jnz     loc_180157801
0x180157666  mov     dword ptr [rbp+1F0h+var_208], 0Bh
0x18015766d  mov     rax, [rsi+40h]
0x180157671  mov     qword ptr [rbp+1F0h+var_208+8], rax
0x180157675  mov     rbx, [r15]
0x180157678  lea     rcx, [rbp+1F0h+var_270]
0x18015767c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180157681  mov     [rsp+2F0h+var_2D0], 1; int
0x180157689  lea     r9, [rbp+1F0h+var_270]; struct ISpWmiObject **
0x18015768d  lea     r8, [rbp+1F0h+var_208]; struct _SP_OBJECT_ID *
0x180157691  mov     rdx, rdi; context
0x180157694  mov     rcx, rbx; this
0x180157697  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015769c  mov     ebx, eax
0x18015769e  test    eax, eax
0x1801576a0  jz      short loc_1801576F4
0x1801576a2  mov     eax, cs:dword_180397B68
0x1801576a8  cmp     eax, 2
0x1801576ab  jbe     loc_1801577EC
0x1801576b1  mov     dword ptr [rbp+1F0h+var_268], ebx
0x1801576b4  mov     dword ptr [rbp+1F0h+var_250], 20Eh
0x1801576bb  lea     rax, [rbp+1F0h+var_268]
0x1801576bf  mov     [rsp+2F0h+var_2C0], rax
0x1801576c4  lea     rax, [rbp+1F0h+var_250]
0x1801576c8  lea     rdx, word_180355362
0x1801576cf  mov     [rsp+2F0h+var_2C8], rax
0x1801576d4  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x1801576db  lea     rax, [rsp+2F0h+var_280]
0x1801576e0  mov     [rsp+2F0h+var_280], r15
0x1801576e5  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x1801576ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801576ef  jmp     loc_1801577F3
0x1801576f4  lea     r8, [rbp+1F0h+instance]; instance
0x1801576f8  lea     rdx, SPACES_StoragePool_CreateVolume_rtti; methodDecl
0x1801576ff  mov     rcx, rdi; context
0x180157702  call    MI_Context_ConstructParameters
0x180157707  mov     ebx, eax
0x180157709  test    eax, eax
0x18015770b  jz      short loc_18015773C
0x18015770d  mov     eax, cs:dword_180397B68
0x180157713  cmp     eax, 2
0x180157716  jbe     loc_1801577EC
0x18015771c  mov     dword ptr [rbp+1F0h+var_248], ebx
0x18015771f  mov     dword ptr [rbp+1F0h+var_240], 216h
0x180157726  lea     rax, [rbp+1F0h+var_248]
0x18015772a  mov     [rsp+2F0h+var_2C0], rax
0x18015772f  lea     rax, [rbp+1F0h+var_240]
0x180157733  lea     rdx, byte_1803564DD
0x18015773a  jmp     short loc_1801576CF
0x18015773c  mov     rcx, [rbp+1F0h+var_270]
0x180157740  mov     rax, [rcx]
0x180157743  lea     rdx, [rbp+1F0h+instance]
0x180157747  mov     qword ptr [rsp+2F0h+var_2D0], rdx
0x18015774c  mov     r9, r13
0x18015774f  mov     r8, rdi
0x180157752  mov     edx, 0B000Eh
0x180157757  mov     rax, [rax+30h]
0x18015775b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157760  mov     ebx, eax
0x180157762  test    eax, eax
0x180157764  jz      short loc_180157794
0x180157766  mov     eax, cs:dword_180397B68
0x18015776c  cmp     eax, 2
0x18015776f  jbe     short loc_1801577EC
0x180157771  mov     dword ptr [rbp+1F0h+var_238], ebx
0x180157774  mov     dword ptr [rbp+1F0h+var_260], 221h
0x18015777b  lea     rax, [rbp+1F0h+var_238]
0x18015777f  mov     [rsp+2F0h+var_2C0], rax
0x180157784  lea     rax, [rbp+1F0h+var_260]
0x180157788  lea     rdx, byte_180354BEF
0x18015778f  jmp     loc_1801576CF
0x180157794  lea     rdx, [rbp+1F0h+instance]
0x180157798  mov     rcx, rdi; self
0x18015779b  call    MI_Instance_Destruct
0x1801577a0  mov     ebx, eax
0x1801577a2  test    eax, eax
0x1801577a4  jz      short loc_1801577EC
0x1801577a6  mov     eax, cs:dword_180397B68
0x1801577ac  cmp     eax, 2
0x1801577af  jbe     short loc_1801577EC
0x1801577b1  mov     [rsp+2F0h+var_278], ebx
0x1801577b5  mov     dword ptr [rsp+2F0h+var_280], 229h
0x1801577bd  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x1801577c4  mov     [rbp+1F0h+var_260], r15
0x1801577c8  lea     rax, [rsp+2F0h+var_278]
0x1801577cd  mov     [rsp+2F0h+var_2C0], rax
0x1801577d2  lea     rax, [rsp+2F0h+var_280]
0x1801577d7  mov     [rsp+2F0h+var_2C8], rax
0x1801577dc  lea     rax, [rbp+1F0h+var_260]
0x1801577e0  lea     rdx, unk_180355860
0x1801577e7  jmp     loc_1801576E5
0x1801577ec  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x1801577f3  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801577fa  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801577ff  jmp     short loc_180157808
0x180157801  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x180157808  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18015780c  mov     [rsp+2F0h+var_2C8], 0; unsigned __int16 *
0x180157815  mov     [rsp+2F0h+var_2D0], ebx; enum _MI_Result
0x180157819  lea     r9, [rbp+1F0h+var_140]; struct _MI_ConstUint32Field *
0x180157820  mov     rdx, [rbp+1F0h+var_230]; unsigned __int16 *
0x180157824  mov     rcx, [rbp+1F0h+var_258]; unsigned __int16 *
0x180157828  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015782d  test    r12d, r12d
0x180157830  jnz     loc_1801579D0
0x180157836  lea     rcx, [rbp+1F0h+var_228]; this
0x18015783a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015783f  mov     eax, cs:dword_180397B68
0x180157845  cmp     eax, 5
0x180157848  jbe     loc_1801579D0
0x18015784e  mov     rdx, 400000000000h
0x180157858  lea     rcx, dword_180397B68
0x18015785f  call    _tlgKeywordOn
0x180157864  test    al, al
0x180157866  jz      loc_1801579D0
0x18015786c  cmp     [rbp+1F0h+var_88], r12b
0x180157873  jz      short loc_1801578B0
0x180157875  mov     rax, [rbp+1F0h+var_90]
0x18015787c  movups  xmm0, xmmword ptr [rax]
0x18015787f  movaps  xmmword ptr [rbp+1F0h+var_1F0.ft], xmm0
0x180157883  movups  xmm1, xmmword ptr [rax+10h]
0x180157887  movaps  xmmword ptr [rbp+1F0h+var_1F0.serverName], xmm1
0x18015788b  movups  xmm0, xmmword ptr [rax+20h]
0x18015788f  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved], xmm0
0x180157893  movups  xmm1, xmmword ptr [rax+30h]
0x180157897  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved+10h], xmm1
0x18015789b  xor     r8d, r8d; unsigned __int16 *
0x18015789e  lea     rdx, [rbp+1F0h+var_1F0]; struct _MI_Instance
0x1801578a2  lea     rcx, name; "ObjectId"
0x1801578a9  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801578ae  jmp     short loc_1801578B2
0x1801578b0  xor     eax, eax
0x1801578b2  mov     [rbp+1F0h+var_258], rax
0x1801578b6  cmp     [rbp+1F0h+var_98], 0
0x1801578bd  jz      short loc_1801578FA
0x1801578bf  mov     rax, [rbp+1F0h+var_A0]
0x1801578c6  movups  xmm0, xmmword ptr [rax]
0x1801578c9  movaps  xmmword ptr [rbp+1F0h+var_1F0.ft], xmm0
0x1801578cd  movups  xmm1, xmmword ptr [rax+10h]
0x1801578d1  movaps  xmmword ptr [rbp+1F0h+var_1F0.serverName], xmm1
0x1801578d5  movups  xmm0, xmmword ptr [rax+20h]
0x1801578d9  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved], xmm0
0x1801578dd  movups  xmm1, xmmword ptr [rax+30h]
0x1801578e1  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved+10h], xmm1
0x1801578e5  xor     r8d, r8d; unsigned __int16 *
0x1801578e8  lea     rdx, [rbp+1F0h+var_1F0]; struct _MI_Instance
0x1801578ec  lea     rcx, name; "ObjectId"
0x1801578f3  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801578f8  jmp     short loc_1801578FC
0x1801578fa  xor     eax, eax
0x1801578fc  mov     [rbp+1F0h+var_230], rax
0x180157900  lea     rax, aVolume_1; "Volume"
0x180157907  mov     [rbp+1F0h+var_238], rax
0x18015790b  mov     rax, [rbp+1F0h+var_220]
0x18015790f  sub     rax, [rbp+1F0h+var_228]
0x180157913  imul    rax, 3E8h
0x18015791a  xor     edx, edx
0x18015791c  div     [rbp+1F0h+var_218]
0x180157920  mov     [rbp+1F0h+var_240], rax
0x180157924  mov     dword ptr [rsp+2F0h+var_280], ebx
0x180157928  mov     al, [rbp+1F0h+var_140.exists]
0x18015792e  neg     al
0x180157930  sbb     ecx, ecx
0x180157932  and     ecx, [rbp+1F0h+var_140.value]
0x180157938  mov     [rsp+2F0h+var_278], ecx
0x18015793c  mov     dword ptr [rbp+1F0h+var_260], r14d
0x180157940  cmp     byte ptr [rsi+48h], 0
0x180157944  jz      short loc_18015794C
0x180157946  mov     rax, [rsi+40h]
0x18015794a  jmp     short loc_18015794E
0x18015794c  xor     eax, eax
0x18015794e  mov     [rbp+1F0h+var_248], rax
0x180157952  lea     rax, aCreatevolume_0; "CreateVolume"
0x180157959  mov     [rbp+1F0h+var_250], rax
0x18015795d  lea     rax, aStoragepool_0; "StoragePool"
0x180157964  mov     [rbp+1F0h+var_268], rax
0x180157968  lea     rax, [rbp+1F0h+var_258]
0x18015796c  mov     [rsp+2F0h+var_288], rax
0x180157971  lea     rax, [rbp+1F0h+var_230]
0x180157975  mov     [rsp+2F0h+var_290], rax
0x18015797a  lea     rax, [rbp+1F0h+var_238]
0x18015797e  mov     [rsp+2F0h+var_298], rax
0x180157983  lea     rax, [rbp+1F0h+var_240]
0x180157987  mov     [rsp+2F0h+var_2A0], rax
0x18015798c  lea     rax, [rsp+2F0h+var_280]
0x180157991  mov     [rsp+2F0h+var_2A8], rax
0x180157996  lea     rax, [rsp+2F0h+var_278]
0x18015799b  mov     [rsp+2F0h+var_2B0], rax
0x1801579a0  lea     rax, [rbp+1F0h+var_260]
0x1801579a4  mov     [rsp+2F0h+var_2B8], rax
0x1801579a9  lea     rax, [rbp+1F0h+var_248]
0x1801579ad  mov     [rsp+2F0h+var_2C0], rax
0x1801579b2  lea     rax, [rbp+1F0h+var_250]
0x1801579b6  mov     [rsp+2F0h+var_2C8], rax
0x1801579bb  lea     rax, [rbp+1F0h+var_268]
0x1801579bf  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x1801579c4  lea     rdx, byte_1803546AB
0x1801579cb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801579d0  lea     rcx, [rbp+1F0h+instance]; self
0x1801579d4  call    MI_Instance_Destruct
0x1801579d9  mov     eax, cs:dword_180397B68
0x1801579df  cmp     eax, 5
0x1801579e2  jbe     short loc_180157A0F
0x1801579e4  mov     dword ptr [rsp+2F0h+var_280], 24Ah
0x1801579ec  mov     [rbp+1F0h+var_258], r15
  ... truncated ...
```
