# SPACES_StoragePool_Invoke_DeleteObject

- ea: `0x18015c210`
- end: `0x18015c785`
- name: `SPACES_StoragePool_Invoke_DeleteObject`
- size: `1397`
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
- `0x18015c210`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c28d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c2f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c74e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c28d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c2f8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c74e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015c2b6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015c2b6`

## string_xrefs

- `0x18015c669`: `DeletePool`
- `0x18015c30a`: `SPACES_StoragePool_Invoke_DeleteObject`
- `0x18015c437`: `SPACES_StoragePool_Invoke_DeleteObject`
- `0x18015c520`: `SPACES_StoragePool_Invoke_DeleteObject`
- `0x18015c54f`: `SPACES_StoragePool_Invoke_DeleteObject`
- `0x18015c567`: `SPACES_StoragePool_Invoke_DeleteObject`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_DeleteObject(
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
  const MI_Char *v28; // rax
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  const char **v33; // [rsp+30h] [rbp-D0h]
  const char *v34; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v35; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v36; // [rsp+80h] [rbp-80h] BYREF
  const char *v37; // [rsp+88h] [rbp-78h] BYREF
  const char *v38; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v39; // [rsp+98h] [rbp-68h] BYREF
  const char *v40; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v41; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v42; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v44; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v45[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v47; // [rsp+F8h] [rbp-8h]
  struct _MI_Instance v48; // [rsp+100h] [rbp+0h] BYREF
  MI_Value value; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+170h] [rbp+70h] BYREF
  struct _MI_ConstUint32Field v51; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _MI_Instance *v52; // [rsp+1B8h] [rbp+B8h]
  char v53; // [rsp+1C0h] [rbp+C0h]
  GUID ActivityId; // [rsp+1E0h] [rbp+E0h] BYREF
  GUID v55; // [rsp+1F0h] [rbp+F0h]
  GUID v56; // [rsp+200h] [rbp+100h] BYREF

  v39 = a4;
  v44 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v55 = ActivityId;
  v56 = ActivityId;
  EventActivityIdControl(4u, &v56);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v37) = 1067;
    v34 = "SPACES_StoragePool_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_DeleteObject",
      (unsigned int)qword_18035B7B8,
      v11,
      v12,
      (__int64)&v34,
      (__int64)&v37);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  v46 = 0;
  v47 = 0;
  v36 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
  v36 = 0;
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
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v46, &v36, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v37) = v15;
        LODWORD(v40) = 1098;
        v33 = &v37;
        v20 = &v40;
        v21 = (__int16 *)byte_18035E0FD;
LABEL_13:
        v34 = "SPACES_StoragePool_Invoke_DeleteObject";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (_DWORD)v21,
          v18,
          v19,
          (__int64)&v34,
          (__int64)v20,
          (__int64)v33);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_DeleteObject_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v41) = v15;
          LODWORD(v42) = 1106;
          v33 = (const char **)&v41;
          v20 = (const char **)&v42;
          v21 = &word_18035DF06;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v36 + 48LL))(
                v36,
                720898,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v35 = v15;
            LODWORD(v34) = 1125;
            v38 = "SPACES_StoragePool_Invoke_DeleteObject";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)byte_18035BDA5,
              v23,
              v24,
              (__int64)&v38,
              (__int64)&v34,
              (__int64)&v35);
          }
          goto LABEL_24;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v38) = 1117;
          v33 = (const char **)&v43;
          v20 = &v38;
          v21 = &word_18035B7E6;
          goto LABEL_13;
        }
      }
    }
LABEL_24:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v39, v44, a6 + 4, &v51, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v45);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( v53 )
        {
          v48 = *v52;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v27 = 0;
        }
        v39 = v27;
        v44 = 0;
        v43 = 0;
        v42 = (unsigned __int64)(1000LL * (v45[1] - v45[0])) / v45[2];
        LODWORD(v34) = v15;
        v35 = v51.exists != 0 ? v51.value : 0;
        LODWORD(v38) = v13;
        if ( a6[4].exists )
          v28 = a6[4].value;
        else
          v28 = 0;
        v41 = v28;
        v40 = "DeletePool";
        v37 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (unsigned int)byte_18035C069,
          v25,
          v26,
          (__int64)&v37,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v39);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v34) = 1158;
    v39 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)qword_18035DC20,
      v30,
      v31,
      (__int64)&v39,
      (__int64)&v34);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v45);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
  return EventActivityIdControl(4u, &v56);
}

```

## disassembly

```asm
0x18015c210  mov     [rsp-8+arg_10], rbx
0x18015c215  push    rbp
0x18015c216  push    rsi
0x18015c217  push    rdi
0x18015c218  push    r12
0x18015c21a  push    r13
0x18015c21c  push    r14
0x18015c21e  push    r15
0x18015c220  lea     rbp, [rsp-120h]
0x18015c228  sub     rsp, 220h
0x18015c22f  mov     rax, cs:__security_cookie
0x18015c236  xor     rax, rsp
0x18015c239  mov     [rbp+150h+var_40], rax
0x18015c240  mov     [rbp+150h+var_1B8], r9
0x18015c244  mov     rsi, rdx
0x18015c247  mov     r15, rcx
0x18015c24a  mov     rax, [rbp+150h+arg_20]
0x18015c251  mov     [rbp+150h+var_190], rax
0x18015c255  mov     rdi, [rbp+150h+arg_28]
0x18015c25c  mov     r13, [rbp+150h+arg_30]
0x18015c263  xorps   xmm0, xmm0
0x18015c266  xor     eax, eax
0x18015c268  movups  xmmword ptr [rbp+150h+value], xmm0
0x18015c26c  movups  xmmword ptr [rbp+150h+value+10h], xmm0
0x18015c270  mov     qword ptr [rbp+150h+value+20h], rax
0x18015c274  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015c27b  movdqu  xmmword ptr [rbp+150h+ActivityId.Data1], xmm0
0x18015c283  lea     rdx, [rbp+150h+ActivityId]; ActivityId
0x18015c28a  lea     ecx, [rax+1]; ControlCode
0x18015c28d  call    cs:__imp_EventActivityIdControl
0x18015c294  nop     dword ptr [rax+rax+00h]
0x18015c299  lea     r9, [rbp+150h+value]; value
0x18015c29d  mov     rcx, rsi; context
0x18015c2a0  call    MI_Context_GetCustomOption_1
0x18015c2a5  xor     ebx, ebx
0x18015c2a7  test    eax, eax
0x18015c2a9  jnz     short loc_18015C2C2
0x18015c2ab  lea     rdx, [rbp+150h+ActivityId]; pclsid
0x18015c2b2  mov     rcx, qword ptr [rbp+150h+value]; lpsz
0x18015c2b6  call    cs:__imp_CLSIDFromString
0x18015c2bd  nop     dword ptr [rax+rax+00h]
0x18015c2c2  mov     rcx, qword ptr [rbp+150h+ActivityId.Data1]
0x18015c2c9  mov     [rbp+150h+var_60], rcx
0x18015c2d0  mov     rax, qword ptr [rbp+150h+ActivityId.Data4]
0x18015c2d7  mov     [rbp+150h+var_58], rax
0x18015c2de  mov     qword ptr [rbp+150h+var_50.Data1], rcx
0x18015c2e5  mov     qword ptr [rbp+150h+var_50.Data4], rax
0x18015c2ec  lea     rdx, [rbp+150h+var_50]; ActivityId
0x18015c2f3  mov     ecx, 4; ControlCode
0x18015c2f8  call    cs:__imp_EventActivityIdControl
0x18015c2ff  nop     dword ptr [rax+rax+00h]
0x18015c304  mov     eax, cs:dword_18039EB68
0x18015c30a  lea     rcx, aSpacesStoragep_61; "SPACES_StoragePool_Invoke_DeleteObject"
0x18015c311  cmp     eax, 5
0x18015c314  jbe     short loc_18015C341
0x18015c316  mov     dword ptr [rbp+150h+var_1C8], 42Bh
0x18015c31d  mov     [rsp+250h+var_1E0], rcx
0x18015c322  lea     rax, [rbp+150h+var_1C8]
0x18015c326  mov     [rsp+250h+var_228], rax
0x18015c32b  lea     rax, [rsp+250h+var_1E0]
0x18015c330  mov     qword ptr [rsp+250h+var_230], rax
0x18015c335  lea     rdx, qword_18035B7B8
0x18015c33c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015c341  mov     [rbp+150h+instance.ft], rbx
0x18015c345  xor     edx, edx; Val
0x18015c347  lea     r8d, [rdx+60h]; Size
0x18015c34b  lea     rcx, [rbp+150h+instance.classDecl]; void *
0x18015c34f  call    memset_0
0x18015c354  xorps   xmm0, xmm0
0x18015c357  xor     eax, eax
0x18015c359  movups  [rbp+150h+var_168], xmm0
0x18015c35d  mov     [rbp+150h+var_158], rax
0x18015c361  mov     [rbp+150h+var_1D0], rbx
0x18015c365  lea     rcx, [rbp+150h+var_1D0]
0x18015c369  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015c36e  mov     [rbp+150h+var_1D0], rbx
0x18015c372  mov     r14d, ebx
0x18015c375  lea     rcx, [rbp+150h+var_188]; this
0x18015c379  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015c37e  mov     rcx, rsi; context
0x18015c381  call    WspIsRemoteRequest
0x18015c386  mov     r12d, eax
0x18015c389  test    eax, eax
0x18015c38b  jnz     short loc_18015C3B0
0x18015c38d  lea     rcx, [rbp+150h+var_188]; this
0x18015c391  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015c396  cmp     [rdi+48h], bl
0x18015c399  jz      short loc_18015C3AD
0x18015c39b  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015c39f  call    WspIsRemoteInstance
0x18015c3a4  test    al, al
0x18015c3a6  lea     r14d, [r12+1]
0x18015c3ab  jnz     short loc_18015C3B0
0x18015c3ad  mov     r14d, ebx
0x18015c3b0  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015c3b7  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015c3bc  mov     ebx, eax
0x18015c3be  test    eax, eax
0x18015c3c0  jnz     loc_18015C564
0x18015c3c6  mov     dword ptr [rbp+150h+var_168], 0Bh
0x18015c3cd  mov     rax, [rdi+40h]
0x18015c3d1  mov     qword ptr [rbp+150h+var_168+8], rax
0x18015c3d5  mov     rbx, [r15]
0x18015c3d8  lea     rcx, [rbp+150h+var_1D0]
0x18015c3dc  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015c3e1  mov     [rsp+250h+var_230], 1; int
0x18015c3e9  lea     r9, [rbp+150h+var_1D0]; struct ISpWmiObject **
0x18015c3ed  lea     r8, [rbp+150h+var_168]; struct _SP_OBJECT_ID *
0x18015c3f1  mov     rdx, rsi; context
0x18015c3f4  mov     rcx, rbx; this
0x18015c3f7  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015c3fc  mov     ebx, eax
0x18015c3fe  xor     r15d, r15d
0x18015c401  test    eax, eax
0x18015c403  jz      short loc_18015C457
0x18015c405  mov     eax, cs:dword_18039EB68
0x18015c40b  cmp     eax, 2
0x18015c40e  jbe     loc_18015C54F
0x18015c414  mov     dword ptr [rbp+150h+var_1C8], ebx
0x18015c417  mov     dword ptr [rbp+150h+var_1B0], 44Ah
0x18015c41e  lea     rax, [rbp+150h+var_1C8]
0x18015c422  mov     [rsp+250h+var_220], rax
0x18015c427  lea     rax, [rbp+150h+var_1B0]
0x18015c42b  lea     rdx, byte_18035E0FD
0x18015c432  mov     [rsp+250h+var_228], rax
0x18015c437  lea     r13, aSpacesStoragep_61; "SPACES_StoragePool_Invoke_DeleteObject"
0x18015c43e  lea     rax, [rsp+250h+var_1E0]
0x18015c443  mov     [rsp+250h+var_1E0], r13
0x18015c448  mov     qword ptr [rsp+250h+var_230], rax
0x18015c44d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015c452  jmp     loc_18015C556
0x18015c457  lea     r8, [rbp+150h+instance]; instance
0x18015c45b  lea     rdx, SPACES_StoragePool_DeleteObject_rtti; methodDecl
0x18015c462  mov     rcx, rsi; context
0x18015c465  call    MI_Context_ConstructParameters
0x18015c46a  mov     ebx, eax
0x18015c46c  test    eax, eax
0x18015c46e  jz      short loc_18015C49F
0x18015c470  mov     eax, cs:dword_18039EB68
0x18015c476  cmp     eax, 2
0x18015c479  jbe     loc_18015C54F
0x18015c47f  mov     dword ptr [rbp+150h+var_1A8], ebx
0x18015c482  mov     dword ptr [rbp+150h+var_1A0], 452h
0x18015c489  lea     rax, [rbp+150h+var_1A8]
0x18015c48d  mov     [rsp+250h+var_220], rax
0x18015c492  lea     rax, [rbp+150h+var_1A0]
0x18015c496  lea     rdx, word_18035DF06
0x18015c49d  jmp     short loc_18015C432
0x18015c49f  mov     rcx, [rbp+150h+var_1D0]
0x18015c4a3  mov     rax, [rcx]
0x18015c4a6  lea     rdx, [rbp+150h+instance]
0x18015c4aa  mov     qword ptr [rsp+250h+var_230], rdx
0x18015c4af  mov     r9, r13
0x18015c4b2  mov     r8, rsi
0x18015c4b5  mov     edx, 0B0002h
0x18015c4ba  mov     rax, [rax+30h]
0x18015c4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015c4c3  mov     ebx, eax
0x18015c4c5  test    eax, eax
0x18015c4c7  jz      short loc_18015C4F7
0x18015c4c9  mov     eax, cs:dword_18039EB68
0x18015c4cf  cmp     eax, 2
0x18015c4d2  jbe     short loc_18015C54F
0x18015c4d4  mov     dword ptr [rbp+150h+var_198], ebx
0x18015c4d7  mov     dword ptr [rbp+150h+var_1C0], 45Dh
0x18015c4de  lea     rax, [rbp+150h+var_198]
0x18015c4e2  mov     [rsp+250h+var_220], rax
0x18015c4e7  lea     rax, [rbp+150h+var_1C0]
0x18015c4eb  lea     rdx, word_18035B7E6
0x18015c4f2  jmp     loc_18015C432
0x18015c4f7  lea     rdx, [rbp+150h+instance]
0x18015c4fb  mov     rcx, rsi; self
0x18015c4fe  call    MI_Instance_Destruct
0x18015c503  mov     ebx, eax
0x18015c505  test    eax, eax
0x18015c507  jz      short loc_18015C54F
0x18015c509  mov     eax, cs:dword_18039EB68
0x18015c50f  cmp     eax, 2
0x18015c512  jbe     short loc_18015C54F
0x18015c514  mov     [rsp+250h+var_1D8], ebx
0x18015c518  mov     dword ptr [rsp+250h+var_1E0], 465h
0x18015c520  lea     r13, aSpacesStoragep_61; "SPACES_StoragePool_Invoke_DeleteObject"
0x18015c527  mov     [rbp+150h+var_1C0], r13
0x18015c52b  lea     rax, [rsp+250h+var_1D8]
0x18015c530  mov     [rsp+250h+var_220], rax
0x18015c535  lea     rax, [rsp+250h+var_1E0]
0x18015c53a  mov     [rsp+250h+var_228], rax
0x18015c53f  lea     rax, [rbp+150h+var_1C0]
0x18015c543  lea     rdx, byte_18035BDA5
0x18015c54a  jmp     loc_18015C448
0x18015c54f  lea     r13, aSpacesStoragep_61; "SPACES_StoragePool_Invoke_DeleteObject"
0x18015c556  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015c55d  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015c562  jmp     short loc_18015C56E
0x18015c564  xor     r15d, r15d
0x18015c567  lea     r13, aSpacesStoragep_61; "SPACES_StoragePool_Invoke_DeleteObject"
0x18015c56e  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015c572  mov     [rsp+250h+var_228], r15; unsigned __int16 *
0x18015c577  mov     [rsp+250h+var_230], ebx; enum _MI_Result
0x18015c57b  lea     r9, [rbp+150h+var_A0]; struct _MI_ConstUint32Field *
0x18015c582  mov     rdx, [rbp+150h+var_190]; unsigned __int16 *
0x18015c586  mov     rcx, [rbp+150h+var_1B8]; unsigned __int16 *
0x18015c58a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015c58f  test    r12d, r12d
0x18015c592  jnz     loc_18015C6E7
0x18015c598  lea     rcx, [rbp+150h+var_188]; this
0x18015c59c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015c5a1  mov     eax, cs:dword_18039EB68
0x18015c5a7  cmp     eax, 5
0x18015c5aa  jbe     loc_18015C6E7
0x18015c5b0  mov     rdx, 400000000000h
0x18015c5ba  lea     rcx, dword_18039EB68
0x18015c5c1  call    _tlgKeywordOn
0x18015c5c6  test    al, al
0x18015c5c8  jz      loc_18015C6E7
0x18015c5ce  cmp     [rbp+150h+var_90], r15b
0x18015c5d5  jz      short loc_18015C612
0x18015c5d7  mov     rax, [rbp+150h+var_98]
0x18015c5de  movups  xmm0, xmmword ptr [rax]
0x18015c5e1  movaps  xmmword ptr [rbp+150h+var_150.ft], xmm0
0x18015c5e5  movups  xmm1, xmmword ptr [rax+10h]
0x18015c5e9  movaps  xmmword ptr [rbp+150h+var_150.serverName], xmm1
0x18015c5ed  movups  xmm0, xmmword ptr [rax+20h]
0x18015c5f1  movaps  xmmword ptr [rbp+150h+var_150.reserved], xmm0
0x18015c5f5  movups  xmm1, xmmword ptr [rax+30h]
0x18015c5f9  movaps  xmmword ptr [rbp+150h+var_150.reserved+10h], xmm1
0x18015c5fd  xor     r8d, r8d; unsigned __int16 *
0x18015c600  lea     rdx, [rbp+150h+var_150]; struct _MI_Instance
0x18015c604  lea     rcx, name; "ObjectId"
0x18015c60b  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015c610  jmp     short loc_18015C615
0x18015c612  mov     rax, r15
0x18015c615  mov     [rbp+150h+var_1B8], rax
0x18015c619  mov     [rbp+150h+var_190], r15
0x18015c61d  mov     [rbp+150h+var_198], r15
0x18015c621  mov     rax, [rbp+150h+var_180]
0x18015c625  sub     rax, [rbp+150h+var_188]
0x18015c629  imul    rax, 3E8h
0x18015c630  xor     edx, edx
0x18015c632  div     [rbp+150h+var_178]
0x18015c636  mov     [rbp+150h+var_1A0], rax
0x18015c63a  mov     dword ptr [rsp+250h+var_1E0], ebx
0x18015c63e  mov     al, [rbp+150h+var_A0.exists]
0x18015c644  neg     al
0x18015c646  sbb     ecx, ecx
0x18015c648  and     ecx, [rbp+150h+var_A0.value]
0x18015c64e  mov     [rsp+250h+var_1D8], ecx
0x18015c652  mov     dword ptr [rbp+150h+var_1C0], r14d
0x18015c656  cmp     [rdi+48h], r15b
0x18015c65a  jz      short loc_18015C662
0x18015c65c  mov     rax, [rdi+40h]
0x18015c660  jmp     short loc_18015C665
0x18015c662  mov     rax, r15
0x18015c665  mov     [rbp+150h+var_1A8], rax
0x18015c669  lea     rax, aDeletepool; "DeletePool"
0x18015c670  mov     [rbp+150h+var_1B0], rax
0x18015c674  lea     rax, aStoragepool_0; "StoragePool"
0x18015c67b  mov     [rbp+150h+var_1C8], rax
0x18015c67f  lea     rax, [rbp+150h+var_1B8]
0x18015c683  mov     [rsp+250h+var_1E8], rax
0x18015c688  lea     rax, [rbp+150h+var_190]
0x18015c68c  mov     [rsp+250h+var_1F0], rax
0x18015c691  lea     rax, [rbp+150h+var_198]
0x18015c695  mov     [rsp+250h+var_1F8], rax
0x18015c69a  lea     rax, [rbp+150h+var_1A0]
0x18015c69e  mov     [rsp+250h+var_200], rax
0x18015c6a3  lea     rax, [rsp+250h+var_1E0]
0x18015c6a8  mov     [rsp+250h+var_208], rax
0x18015c6ad  lea     rax, [rsp+250h+var_1D8]
0x18015c6b2  mov     [rsp+250h+var_210], rax
0x18015c6b7  lea     rax, [rbp+150h+var_1C0]
0x18015c6bb  mov     [rsp+250h+var_218], rax
0x18015c6c0  lea     rax, [rbp+150h+var_1A8]
0x18015c6c4  mov     [rsp+250h+var_220], rax
0x18015c6c9  lea     rax, [rbp+150h+var_1B0]
0x18015c6cd  mov     [rsp+250h+var_228], rax
0x18015c6d2  lea     rax, [rbp+150h+var_1C8]
0x18015c6d6  mov     qword ptr [rsp+250h+var_230], rax
0x18015c6db  lea     rdx, byte_18035C069
0x18015c6e2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18015c6e7  lea     rcx, [rbp+150h+instance]; self
0x18015c6eb  call    MI_Instance_Destruct
0x18015c6f0  mov     eax, cs:dword_18039EB68
0x18015c6f6  cmp     eax, 5
0x18015c6f9  jbe     short loc_18015C726
0x18015c6fb  mov     dword ptr [rsp+250h+var_1E0], 486h
0x18015c703  mov     [rbp+150h+var_1B8], r13
0x18015c707  lea     rax, [rsp+250h+var_1E0]
0x18015c70c  mov     [rsp+250h+var_228], rax
0x18015c711  lea     rax, [rbp+150h+var_1B8]
0x18015c715  mov     qword ptr [rsp+250h+var_230], rax
0x18015c71a  lea     rdx, qword_18035DC20
0x18015c721  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015c726  mov     edx, ebx; result
0x18015c728  mov     rcx, rsi; context
0x18015c72b  call    MI_Context_PostResult_0
0x18015c730  lea     rcx, [rbp+150h+var_188]; this
0x18015c734  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18015c739  lea     rcx, [rbp+150h+var_1D0]
0x18015c73d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
  ... truncated ...
```
