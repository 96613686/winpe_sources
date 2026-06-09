# SPACES_StoragePool_Invoke_CreateVolume

- ea: `0x18015b610`
- end: `0x18015bbd0`
- name: `SPACES_StoragePool_Invoke_CreateVolume`
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
- `0x18015b610`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b68d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b6f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015bb99`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b68d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b6f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015bb99`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015b6b6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015b6b6`

## string_xrefs

- `0x18015bab4`: `CreateVolume`
- `0x18015b70a`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x18015b836`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x18015b91f`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x18015b94e`: `SPACES_StoragePool_Invoke_CreateVolume`
- `0x18015b963`: `SPACES_StoragePool_Invoke_CreateVolume`

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
  struct _MI_Instance *v53; // [rsp+250h] [rbp+150h]
  char v54; // [rsp+258h] [rbp+158h]
  struct _MI_Instance *v55; // [rsp+260h] [rbp+160h]
  char v56; // [rsp+268h] [rbp+168h]
  GUID ActivityId; // [rsp+280h] [rbp+180h] BYREF
  GUID v58; // [rsp+290h] [rbp+190h]
  GUID v59; // [rsp+2A0h] [rbp+1A0h] BYREF

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
    LODWORD(v38) = 495;
    v35 = "SPACES_StoragePool_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVolume",
      (unsigned int)byte_18035BF11,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v38);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x108u);
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
        LODWORD(v41) = 526;
        v34 = &v38;
        v20 = &v41;
        v21 = byte_18035C2B1;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVolume";
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
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVolume_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v42) = v15;
          LODWORD(v43) = 534;
          v34 = (const char **)&v42;
          v20 = (const char **)&v43;
          v21 = byte_18035D4F3;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v37 + 48LL))(
                v37,
                720910,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v36 = v15;
            LODWORD(v35) = 553;
            v39 = "SPACES_StoragePool_Invoke_CreateVolume";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)word_18035C85A,
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
          LODWORD(v39) = 545;
          v34 = &v44;
          v20 = &v39;
          v21 = (char *)word_18035BB4A;
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
        v44 = "Volume";
        v43 = (unsigned __int64)(1000LL * (v46[1] - v46[0])) / v46[2];
        LODWORD(v35) = v15;
        v36 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v42 = v29;
        v41 = "CreateVolume";
        v38 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)byte_18035B6A5,
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
    LODWORD(v35) = 586;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVolume";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_18035CC13,
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
0x18015b610  mov     [rsp-8+arg_10], rbx
0x18015b615  push    rbp
0x18015b616  push    rsi
0x18015b617  push    rdi
0x18015b618  push    r12
0x18015b61a  push    r13
0x18015b61c  push    r14
0x18015b61e  push    r15
0x18015b620  lea     rbp, [rsp-1C0h]
0x18015b628  sub     rsp, 2C0h
0x18015b62f  mov     rax, cs:__security_cookie
0x18015b636  xor     rax, rsp
0x18015b639  mov     [rbp+1F0h+var_40], rax
0x18015b640  mov     [rbp+1F0h+var_258], r9
0x18015b644  mov     rsi, rdx
0x18015b647  mov     r15, rcx
0x18015b64a  mov     rax, [rbp+1F0h+arg_20]
0x18015b651  mov     [rbp+1F0h+var_230], rax
0x18015b655  mov     rdi, [rbp+1F0h+arg_28]
0x18015b65c  mov     r13, [rbp+1F0h+arg_30]
0x18015b663  xorps   xmm0, xmm0
0x18015b666  xor     eax, eax
0x18015b668  movups  xmmword ptr [rbp+1F0h+value], xmm0
0x18015b66c  movups  xmmword ptr [rbp+1F0h+value+10h], xmm0
0x18015b670  mov     qword ptr [rbp+1F0h+value+20h], rax
0x18015b674  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015b67b  movdqu  xmmword ptr [rbp+1F0h+ActivityId.Data1], xmm0
0x18015b683  lea     rdx, [rbp+1F0h+ActivityId]; ActivityId
0x18015b68a  lea     ecx, [rax+1]; ControlCode
0x18015b68d  call    cs:__imp_EventActivityIdControl
0x18015b694  nop     dword ptr [rax+rax+00h]
0x18015b699  lea     r9, [rbp+1F0h+value]; value
0x18015b69d  mov     rcx, rsi; context
0x18015b6a0  call    MI_Context_GetCustomOption_1
0x18015b6a5  xor     ebx, ebx
0x18015b6a7  test    eax, eax
0x18015b6a9  jnz     short loc_18015B6C2
0x18015b6ab  lea     rdx, [rbp+1F0h+ActivityId]; pclsid
0x18015b6b2  mov     rcx, qword ptr [rbp+1F0h+value]; lpsz
0x18015b6b6  call    cs:__imp_CLSIDFromString
0x18015b6bd  nop     dword ptr [rax+rax+00h]
0x18015b6c2  mov     rcx, qword ptr [rbp+1F0h+ActivityId.Data1]
0x18015b6c9  mov     [rbp+1F0h+var_60], rcx
0x18015b6d0  mov     rax, qword ptr [rbp+1F0h+ActivityId.Data4]
0x18015b6d7  mov     [rbp+1F0h+var_58], rax
0x18015b6de  mov     qword ptr [rbp+1F0h+var_50.Data1], rcx
0x18015b6e5  mov     qword ptr [rbp+1F0h+var_50.Data4], rax
0x18015b6ec  lea     rdx, [rbp+1F0h+var_50]; ActivityId
0x18015b6f3  mov     ecx, 4; ControlCode
0x18015b6f8  call    cs:__imp_EventActivityIdControl
0x18015b6ff  nop     dword ptr [rax+rax+00h]
0x18015b704  mov     eax, cs:dword_18039EB68
0x18015b70a  lea     rcx, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x18015b711  cmp     eax, 5
0x18015b714  jbe     short loc_18015B741
0x18015b716  mov     dword ptr [rbp+1F0h+var_268], 1EFh
0x18015b71d  mov     [rsp+2F0h+var_280], rcx
0x18015b722  lea     rax, [rbp+1F0h+var_268]
0x18015b726  mov     [rsp+2F0h+var_2C8], rax
0x18015b72b  lea     rax, [rsp+2F0h+var_280]
0x18015b730  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18015b735  lea     rdx, byte_18035BF11
0x18015b73c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015b741  mov     [rbp+1F0h+instance.ft], rbx
0x18015b745  xor     edx, edx; Val
0x18015b747  mov     r8d, 108h; Size
0x18015b74d  lea     rcx, [rbp+1F0h+instance.classDecl]; void *
0x18015b751  call    memset_0
0x18015b756  xorps   xmm0, xmm0
0x18015b759  xor     eax, eax
0x18015b75b  movups  [rbp+1F0h+var_208], xmm0
0x18015b75f  mov     [rbp+1F0h+var_1F8], rax
0x18015b763  mov     [rbp+1F0h+var_270], rbx
0x18015b767  lea     rcx, [rbp+1F0h+var_270]
0x18015b76b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015b770  mov     [rbp+1F0h+var_270], rbx
0x18015b774  mov     r14d, ebx
0x18015b777  lea     rcx, [rbp+1F0h+var_228]; this
0x18015b77b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015b780  mov     rcx, rsi; context
0x18015b783  call    WspIsRemoteRequest
0x18015b788  mov     r12d, eax
0x18015b78b  test    eax, eax
0x18015b78d  jnz     short loc_18015B7B2
0x18015b78f  lea     rcx, [rbp+1F0h+var_228]; this
0x18015b793  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015b798  cmp     [rdi+48h], bl
0x18015b79b  jz      short loc_18015B7AF
0x18015b79d  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015b7a1  call    WspIsRemoteInstance
0x18015b7a6  test    al, al
0x18015b7a8  lea     r14d, [r12+1]
0x18015b7ad  jnz     short loc_18015B7B2
0x18015b7af  mov     r14d, ebx
0x18015b7b2  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015b7b9  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015b7be  mov     ebx, eax
0x18015b7c0  test    eax, eax
0x18015b7c2  jnz     loc_18015B963
0x18015b7c8  mov     dword ptr [rbp+1F0h+var_208], 0Bh
0x18015b7cf  mov     rax, [rdi+40h]
0x18015b7d3  mov     qword ptr [rbp+1F0h+var_208+8], rax
0x18015b7d7  mov     rbx, [r15]
0x18015b7da  lea     rcx, [rbp+1F0h+var_270]
0x18015b7de  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015b7e3  mov     [rsp+2F0h+var_2D0], 1; int
0x18015b7eb  lea     r9, [rbp+1F0h+var_270]; struct ISpWmiObject **
0x18015b7ef  lea     r8, [rbp+1F0h+var_208]; struct _SP_OBJECT_ID *
0x18015b7f3  mov     rdx, rsi; context
0x18015b7f6  mov     rcx, rbx; this
0x18015b7f9  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015b7fe  mov     ebx, eax
0x18015b800  test    eax, eax
0x18015b802  jz      short loc_18015B856
0x18015b804  mov     eax, cs:dword_18039EB68
0x18015b80a  cmp     eax, 2
0x18015b80d  jbe     loc_18015B94E
0x18015b813  mov     dword ptr [rbp+1F0h+var_268], ebx
0x18015b816  mov     dword ptr [rbp+1F0h+var_250], 20Eh
0x18015b81d  lea     rax, [rbp+1F0h+var_268]
0x18015b821  mov     [rsp+2F0h+var_2C0], rax
0x18015b826  lea     rax, [rbp+1F0h+var_250]
0x18015b82a  lea     rdx, byte_18035C2B1
0x18015b831  mov     [rsp+2F0h+var_2C8], rax
0x18015b836  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x18015b83d  lea     rax, [rsp+2F0h+var_280]
0x18015b842  mov     [rsp+2F0h+var_280], r15
0x18015b847  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18015b84c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015b851  jmp     loc_18015B955
0x18015b856  lea     r8, [rbp+1F0h+instance]; instance
0x18015b85a  lea     rdx, SPACES_StoragePool_CreateVolume_rtti; methodDecl
0x18015b861  mov     rcx, rsi; context
0x18015b864  call    MI_Context_ConstructParameters
0x18015b869  mov     ebx, eax
0x18015b86b  test    eax, eax
0x18015b86d  jz      short loc_18015B89E
0x18015b86f  mov     eax, cs:dword_18039EB68
0x18015b875  cmp     eax, 2
0x18015b878  jbe     loc_18015B94E
0x18015b87e  mov     dword ptr [rbp+1F0h+var_248], ebx
0x18015b881  mov     dword ptr [rbp+1F0h+var_240], 216h
0x18015b888  lea     rax, [rbp+1F0h+var_248]
0x18015b88c  mov     [rsp+2F0h+var_2C0], rax
0x18015b891  lea     rax, [rbp+1F0h+var_240]
0x18015b895  lea     rdx, byte_18035D4F3
0x18015b89c  jmp     short loc_18015B831
0x18015b89e  mov     rcx, [rbp+1F0h+var_270]
0x18015b8a2  mov     rax, [rcx]
0x18015b8a5  lea     rdx, [rbp+1F0h+instance]
0x18015b8a9  mov     qword ptr [rsp+2F0h+var_2D0], rdx
0x18015b8ae  mov     r9, r13
0x18015b8b1  mov     r8, rsi
0x18015b8b4  mov     edx, 0B000Eh
0x18015b8b9  mov     rax, [rax+30h]
0x18015b8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b8c2  mov     ebx, eax
0x18015b8c4  test    eax, eax
0x18015b8c6  jz      short loc_18015B8F6
0x18015b8c8  mov     eax, cs:dword_18039EB68
0x18015b8ce  cmp     eax, 2
0x18015b8d1  jbe     short loc_18015B94E
0x18015b8d3  mov     dword ptr [rbp+1F0h+var_238], ebx
0x18015b8d6  mov     dword ptr [rbp+1F0h+var_260], 221h
0x18015b8dd  lea     rax, [rbp+1F0h+var_238]
0x18015b8e1  mov     [rsp+2F0h+var_2C0], rax
0x18015b8e6  lea     rax, [rbp+1F0h+var_260]
0x18015b8ea  lea     rdx, word_18035BB4A
0x18015b8f1  jmp     loc_18015B831
0x18015b8f6  lea     rdx, [rbp+1F0h+instance]
0x18015b8fa  mov     rcx, rsi; self
0x18015b8fd  call    MI_Instance_Destruct
0x18015b902  mov     ebx, eax
0x18015b904  test    eax, eax
0x18015b906  jz      short loc_18015B94E
0x18015b908  mov     eax, cs:dword_18039EB68
0x18015b90e  cmp     eax, 2
0x18015b911  jbe     short loc_18015B94E
0x18015b913  mov     [rsp+2F0h+var_278], ebx
0x18015b917  mov     dword ptr [rsp+2F0h+var_280], 229h
0x18015b91f  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x18015b926  mov     [rbp+1F0h+var_260], r15
0x18015b92a  lea     rax, [rsp+2F0h+var_278]
0x18015b92f  mov     [rsp+2F0h+var_2C0], rax
0x18015b934  lea     rax, [rsp+2F0h+var_280]
0x18015b939  mov     [rsp+2F0h+var_2C8], rax
0x18015b93e  lea     rax, [rbp+1F0h+var_260]
0x18015b942  lea     rdx, word_18035C85A
0x18015b949  jmp     loc_18015B847
0x18015b94e  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x18015b955  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015b95c  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015b961  jmp     short loc_18015B96A
0x18015b963  lea     r15, aSpacesStoragep_41; "SPACES_StoragePool_Invoke_CreateVolume"
0x18015b96a  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015b96e  mov     [rsp+2F0h+var_2C8], 0; unsigned __int16 *
0x18015b977  mov     [rsp+2F0h+var_2D0], ebx; enum _MI_Result
0x18015b97b  lea     r9, [rbp+1F0h+var_140]; struct _MI_ConstUint32Field *
0x18015b982  mov     rdx, [rbp+1F0h+var_230]; unsigned __int16 *
0x18015b986  mov     rcx, [rbp+1F0h+var_258]; unsigned __int16 *
0x18015b98a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015b98f  test    r12d, r12d
0x18015b992  jnz     loc_18015BB32
0x18015b998  lea     rcx, [rbp+1F0h+var_228]; this
0x18015b99c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015b9a1  mov     eax, cs:dword_18039EB68
0x18015b9a7  cmp     eax, 5
0x18015b9aa  jbe     loc_18015BB32
0x18015b9b0  mov     rdx, 400000000000h
0x18015b9ba  lea     rcx, dword_18039EB68
0x18015b9c1  call    _tlgKeywordOn
0x18015b9c6  test    al, al
0x18015b9c8  jz      loc_18015BB32
0x18015b9ce  cmp     [rbp+1F0h+var_88], r12b
0x18015b9d5  jz      short loc_18015BA12
0x18015b9d7  mov     rax, [rbp+1F0h+var_90]
0x18015b9de  movups  xmm0, xmmword ptr [rax]
0x18015b9e1  movaps  xmmword ptr [rbp+1F0h+var_1F0.ft], xmm0
0x18015b9e5  movups  xmm1, xmmword ptr [rax+10h]
0x18015b9e9  movaps  xmmword ptr [rbp+1F0h+var_1F0.serverName], xmm1
0x18015b9ed  movups  xmm0, xmmword ptr [rax+20h]
0x18015b9f1  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved], xmm0
0x18015b9f5  movups  xmm1, xmmword ptr [rax+30h]
0x18015b9f9  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved+10h], xmm1
0x18015b9fd  xor     r8d, r8d; unsigned __int16 *
0x18015ba00  lea     rdx, [rbp+1F0h+var_1F0]; struct _MI_Instance
0x18015ba04  lea     rcx, name; "ObjectId"
0x18015ba0b  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015ba10  jmp     short loc_18015BA14
0x18015ba12  xor     eax, eax
0x18015ba14  mov     [rbp+1F0h+var_258], rax
0x18015ba18  cmp     [rbp+1F0h+var_98], 0
0x18015ba1f  jz      short loc_18015BA5C
0x18015ba21  mov     rax, [rbp+1F0h+var_A0]
0x18015ba28  movups  xmm0, xmmword ptr [rax]
0x18015ba2b  movaps  xmmword ptr [rbp+1F0h+var_1F0.ft], xmm0
0x18015ba2f  movups  xmm1, xmmword ptr [rax+10h]
0x18015ba33  movaps  xmmword ptr [rbp+1F0h+var_1F0.serverName], xmm1
0x18015ba37  movups  xmm0, xmmword ptr [rax+20h]
0x18015ba3b  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved], xmm0
0x18015ba3f  movups  xmm1, xmmword ptr [rax+30h]
0x18015ba43  movaps  xmmword ptr [rbp+1F0h+var_1F0.reserved+10h], xmm1
0x18015ba47  xor     r8d, r8d; unsigned __int16 *
0x18015ba4a  lea     rdx, [rbp+1F0h+var_1F0]; struct _MI_Instance
0x18015ba4e  lea     rcx, name; "ObjectId"
0x18015ba55  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015ba5a  jmp     short loc_18015BA5E
0x18015ba5c  xor     eax, eax
0x18015ba5e  mov     [rbp+1F0h+var_230], rax
0x18015ba62  lea     rax, aVolume_1; "Volume"
0x18015ba69  mov     [rbp+1F0h+var_238], rax
0x18015ba6d  mov     rax, [rbp+1F0h+var_220]
0x18015ba71  sub     rax, [rbp+1F0h+var_228]
0x18015ba75  imul    rax, 3E8h
0x18015ba7c  xor     edx, edx
0x18015ba7e  div     [rbp+1F0h+var_218]
0x18015ba82  mov     [rbp+1F0h+var_240], rax
0x18015ba86  mov     dword ptr [rsp+2F0h+var_280], ebx
0x18015ba8a  mov     al, [rbp+1F0h+var_140.exists]
0x18015ba90  neg     al
0x18015ba92  sbb     ecx, ecx
0x18015ba94  and     ecx, [rbp+1F0h+var_140.value]
0x18015ba9a  mov     [rsp+2F0h+var_278], ecx
0x18015ba9e  mov     dword ptr [rbp+1F0h+var_260], r14d
0x18015baa2  cmp     byte ptr [rdi+48h], 0
0x18015baa6  jz      short loc_18015BAAE
0x18015baa8  mov     rax, [rdi+40h]
0x18015baac  jmp     short loc_18015BAB0
0x18015baae  xor     eax, eax
0x18015bab0  mov     [rbp+1F0h+var_248], rax
0x18015bab4  lea     rax, aCreatevolume_0; "CreateVolume"
0x18015babb  mov     [rbp+1F0h+var_250], rax
0x18015babf  lea     rax, aStoragepool_0; "StoragePool"
0x18015bac6  mov     [rbp+1F0h+var_268], rax
0x18015baca  lea     rax, [rbp+1F0h+var_258]
0x18015bace  mov     [rsp+2F0h+var_288], rax
0x18015bad3  lea     rax, [rbp+1F0h+var_230]
0x18015bad7  mov     [rsp+2F0h+var_290], rax
0x18015badc  lea     rax, [rbp+1F0h+var_238]
0x18015bae0  mov     [rsp+2F0h+var_298], rax
0x18015bae5  lea     rax, [rbp+1F0h+var_240]
0x18015bae9  mov     [rsp+2F0h+var_2A0], rax
0x18015baee  lea     rax, [rsp+2F0h+var_280]
0x18015baf3  mov     [rsp+2F0h+var_2A8], rax
0x18015baf8  lea     rax, [rsp+2F0h+var_278]
0x18015bafd  mov     [rsp+2F0h+var_2B0], rax
0x18015bb02  lea     rax, [rbp+1F0h+var_260]
0x18015bb06  mov     [rsp+2F0h+var_2B8], rax
0x18015bb0b  lea     rax, [rbp+1F0h+var_248]
0x18015bb0f  mov     [rsp+2F0h+var_2C0], rax
0x18015bb14  lea     rax, [rbp+1F0h+var_250]
0x18015bb18  mov     [rsp+2F0h+var_2C8], rax
0x18015bb1d  lea     rax, [rbp+1F0h+var_268]
0x18015bb21  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x18015bb26  lea     rdx, byte_18035B6A5
0x18015bb2d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18015bb32  lea     rcx, [rbp+1F0h+instance]; self
0x18015bb36  call    MI_Instance_Destruct
0x18015bb3b  mov     eax, cs:dword_18039EB68
0x18015bb41  cmp     eax, 5
  ... truncated ...
```
