# SPACES_StorageTier_Invoke_DeleteObject

- ea: `0x18017b390`
- end: `0x18017b905`
- name: `SPACES_StorageTier_Invoke_DeleteObject`
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
- `0x18017b390`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017b40d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017b478`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017b8ce`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017b40d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017b478`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18017b8ce`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017b436`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18017b436`

## string_xrefs

- `0x18017b48a`: `SPACES_StorageTier_Invoke_DeleteObject`
- `0x18017b5b7`: `SPACES_StorageTier_Invoke_DeleteObject`
- `0x18017b6a0`: `SPACES_StorageTier_Invoke_DeleteObject`
- `0x18017b6cf`: `SPACES_StorageTier_Invoke_DeleteObject`
- `0x18017b6e7`: `SPACES_StorageTier_Invoke_DeleteObject`
- `0x18017b7e9`: `DeleteStorageTier`

## pseudocode

```c
ULONG __fastcall SPACES_StorageTier_Invoke_DeleteObject(
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
    LODWORD(v37) = 144;
    v34 = "SPACES_StorageTier_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageTier_Invoke_DeleteObject",
      (unsigned int)&word_180367C06,
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
    LODWORD(v46) = 12;
    *((_QWORD *)&v46 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v36);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v46, &v36, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v37) = v15;
        LODWORD(v40) = 175;
        v33 = &v37;
        v20 = &v40;
        v21 = &byte_180367EA7;
LABEL_13:
        v34 = "SPACES_StorageTier_Invoke_DeleteObject";
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
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageTier_DeleteObject_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v41) = v15;
          LODWORD(v42) = 183;
          v33 = (const char **)&v41;
          v20 = (const char **)&v42;
          v21 = (char *)&dword_180367FF4;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v36 + 48LL))(
                v36,
                786433,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v35 = v15;
            LODWORD(v34) = 202;
            v38 = "SPACES_StorageTier_Invoke_DeleteObject";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&unk_1803682F0,
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
          LODWORD(v38) = 194;
          v33 = (const char **)&v43;
          v20 = &v38;
          v21 = byte_1803674D5;
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
        v40 = "DeleteStorageTier";
        v37 = "StorageTier";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (unsigned int)&word_18036750E,
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
    LODWORD(v34) = 235;
    v39 = (unsigned __int16 *)"SPACES_StorageTier_Invoke_DeleteObject";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)byte_180367233,
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
0x18017b390  mov     [rsp-8+arg_10], rbx
0x18017b395  push    rbp
0x18017b396  push    rsi
0x18017b397  push    rdi
0x18017b398  push    r12
0x18017b39a  push    r13
0x18017b39c  push    r14
0x18017b39e  push    r15
0x18017b3a0  lea     rbp, [rsp-120h]
0x18017b3a8  sub     rsp, 220h
0x18017b3af  mov     rax, cs:__security_cookie
0x18017b3b6  xor     rax, rsp
0x18017b3b9  mov     [rbp+150h+var_40], rax
0x18017b3c0  mov     [rbp+150h+var_1B8], r9
0x18017b3c4  mov     rsi, rdx
0x18017b3c7  mov     r15, rcx
0x18017b3ca  mov     rax, [rbp+150h+arg_20]
0x18017b3d1  mov     [rbp+150h+var_190], rax
0x18017b3d5  mov     rdi, [rbp+150h+arg_28]
0x18017b3dc  mov     r13, [rbp+150h+arg_30]
0x18017b3e3  xorps   xmm0, xmm0
0x18017b3e6  xor     eax, eax
0x18017b3e8  movups  xmmword ptr [rbp+150h+value], xmm0
0x18017b3ec  movups  xmmword ptr [rbp+150h+value+10h], xmm0
0x18017b3f0  mov     qword ptr [rbp+150h+value+20h], rax
0x18017b3f4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18017b3fb  movdqu  xmmword ptr [rbp+150h+ActivityId.Data1], xmm0
0x18017b403  lea     rdx, [rbp+150h+ActivityId]; ActivityId
0x18017b40a  lea     ecx, [rax+1]; ControlCode
0x18017b40d  call    cs:__imp_EventActivityIdControl
0x18017b414  nop     dword ptr [rax+rax+00h]
0x18017b419  lea     r9, [rbp+150h+value]; value
0x18017b41d  mov     rcx, rsi; context
0x18017b420  call    MI_Context_GetCustomOption_1
0x18017b425  xor     ebx, ebx
0x18017b427  test    eax, eax
0x18017b429  jnz     short loc_18017B442
0x18017b42b  lea     rdx, [rbp+150h+ActivityId]; pclsid
0x18017b432  mov     rcx, qword ptr [rbp+150h+value]; lpsz
0x18017b436  call    cs:__imp_CLSIDFromString
0x18017b43d  nop     dword ptr [rax+rax+00h]
0x18017b442  mov     rcx, qword ptr [rbp+150h+ActivityId.Data1]
0x18017b449  mov     [rbp+150h+var_60], rcx
0x18017b450  mov     rax, qword ptr [rbp+150h+ActivityId.Data4]
0x18017b457  mov     [rbp+150h+var_58], rax
0x18017b45e  mov     qword ptr [rbp+150h+var_50.Data1], rcx
0x18017b465  mov     qword ptr [rbp+150h+var_50.Data4], rax
0x18017b46c  lea     rdx, [rbp+150h+var_50]; ActivityId
0x18017b473  mov     ecx, 4; ControlCode
0x18017b478  call    cs:__imp_EventActivityIdControl
0x18017b47f  nop     dword ptr [rax+rax+00h]
0x18017b484  mov     eax, cs:dword_18039EB68
0x18017b48a  lea     rcx, aSpacesStoraget; "SPACES_StorageTier_Invoke_DeleteObject"
0x18017b491  cmp     eax, 5
0x18017b494  jbe     short loc_18017B4C1
0x18017b496  mov     dword ptr [rbp+150h+var_1C8], 90h
0x18017b49d  mov     [rsp+250h+var_1E0], rcx
0x18017b4a2  lea     rax, [rbp+150h+var_1C8]
0x18017b4a6  mov     [rsp+250h+var_228], rax
0x18017b4ab  lea     rax, [rsp+250h+var_1E0]
0x18017b4b0  mov     qword ptr [rsp+250h+var_230], rax
0x18017b4b5  lea     rdx, word_180367C06
0x18017b4bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017b4c1  mov     [rbp+150h+instance.ft], rbx
0x18017b4c5  xor     edx, edx; Val
0x18017b4c7  lea     r8d, [rdx+60h]; Size
0x18017b4cb  lea     rcx, [rbp+150h+instance.classDecl]; void *
0x18017b4cf  call    memset_0
0x18017b4d4  xorps   xmm0, xmm0
0x18017b4d7  xor     eax, eax
0x18017b4d9  movups  [rbp+150h+var_168], xmm0
0x18017b4dd  mov     [rbp+150h+var_158], rax
0x18017b4e1  mov     [rbp+150h+var_1D0], rbx
0x18017b4e5  lea     rcx, [rbp+150h+var_1D0]
0x18017b4e9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017b4ee  mov     [rbp+150h+var_1D0], rbx
0x18017b4f2  mov     r14d, ebx
0x18017b4f5  lea     rcx, [rbp+150h+var_188]; this
0x18017b4f9  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18017b4fe  mov     rcx, rsi; context
0x18017b501  call    WspIsRemoteRequest
0x18017b506  mov     r12d, eax
0x18017b509  test    eax, eax
0x18017b50b  jnz     short loc_18017B530
0x18017b50d  lea     rcx, [rbp+150h+var_188]; this
0x18017b511  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18017b516  cmp     [rdi+48h], bl
0x18017b519  jz      short loc_18017B52D
0x18017b51b  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18017b51f  call    WspIsRemoteInstance
0x18017b524  test    al, al
0x18017b526  lea     r14d, [r12+1]
0x18017b52b  jnz     short loc_18017B530
0x18017b52d  mov     r14d, ebx
0x18017b530  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18017b537  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18017b53c  mov     ebx, eax
0x18017b53e  test    eax, eax
0x18017b540  jnz     loc_18017B6E4
0x18017b546  mov     dword ptr [rbp+150h+var_168], 0Ch
0x18017b54d  mov     rax, [rdi+40h]
0x18017b551  mov     qword ptr [rbp+150h+var_168+8], rax
0x18017b555  mov     rbx, [r15]
0x18017b558  lea     rcx, [rbp+150h+var_1D0]
0x18017b55c  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18017b561  mov     [rsp+250h+var_230], 1; int
0x18017b569  lea     r9, [rbp+150h+var_1D0]; struct ISpWmiObject **
0x18017b56d  lea     r8, [rbp+150h+var_168]; struct _SP_OBJECT_ID *
0x18017b571  mov     rdx, rsi; context
0x18017b574  mov     rcx, rbx; this
0x18017b577  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18017b57c  mov     ebx, eax
0x18017b57e  xor     r15d, r15d
0x18017b581  test    eax, eax
0x18017b583  jz      short loc_18017B5D7
0x18017b585  mov     eax, cs:dword_18039EB68
0x18017b58b  cmp     eax, 2
0x18017b58e  jbe     loc_18017B6CF
0x18017b594  mov     dword ptr [rbp+150h+var_1C8], ebx
0x18017b597  mov     dword ptr [rbp+150h+var_1B0], 0AFh
0x18017b59e  lea     rax, [rbp+150h+var_1C8]
0x18017b5a2  mov     [rsp+250h+var_220], rax
0x18017b5a7  lea     rax, [rbp+150h+var_1B0]
0x18017b5ab  lea     rdx, byte_180367EA7
0x18017b5b2  mov     [rsp+250h+var_228], rax
0x18017b5b7  lea     r13, aSpacesStoraget; "SPACES_StorageTier_Invoke_DeleteObject"
0x18017b5be  lea     rax, [rsp+250h+var_1E0]
0x18017b5c3  mov     [rsp+250h+var_1E0], r13
0x18017b5c8  mov     qword ptr [rsp+250h+var_230], rax
0x18017b5cd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18017b5d2  jmp     loc_18017B6D6
0x18017b5d7  lea     r8, [rbp+150h+instance]; instance
0x18017b5db  lea     rdx, SPACES_StorageTier_DeleteObject_rtti; methodDecl
0x18017b5e2  mov     rcx, rsi; context
0x18017b5e5  call    MI_Context_ConstructParameters
0x18017b5ea  mov     ebx, eax
0x18017b5ec  test    eax, eax
0x18017b5ee  jz      short loc_18017B61F
0x18017b5f0  mov     eax, cs:dword_18039EB68
0x18017b5f6  cmp     eax, 2
0x18017b5f9  jbe     loc_18017B6CF
0x18017b5ff  mov     dword ptr [rbp+150h+var_1A8], ebx
0x18017b602  mov     dword ptr [rbp+150h+var_1A0], 0B7h
0x18017b609  lea     rax, [rbp+150h+var_1A8]
0x18017b60d  mov     [rsp+250h+var_220], rax
0x18017b612  lea     rax, [rbp+150h+var_1A0]
0x18017b616  lea     rdx, dword_180367FF4
0x18017b61d  jmp     short loc_18017B5B2
0x18017b61f  mov     rcx, [rbp+150h+var_1D0]
0x18017b623  mov     rax, [rcx]
0x18017b626  lea     rdx, [rbp+150h+instance]
0x18017b62a  mov     qword ptr [rsp+250h+var_230], rdx
0x18017b62f  mov     r9, r13
0x18017b632  mov     r8, rsi
0x18017b635  mov     edx, 0C0001h
0x18017b63a  mov     rax, [rax+30h]
0x18017b63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017b643  mov     ebx, eax
0x18017b645  test    eax, eax
0x18017b647  jz      short loc_18017B677
0x18017b649  mov     eax, cs:dword_18039EB68
0x18017b64f  cmp     eax, 2
0x18017b652  jbe     short loc_18017B6CF
0x18017b654  mov     dword ptr [rbp+150h+var_198], ebx
0x18017b657  mov     dword ptr [rbp+150h+var_1C0], 0C2h
0x18017b65e  lea     rax, [rbp+150h+var_198]
0x18017b662  mov     [rsp+250h+var_220], rax
0x18017b667  lea     rax, [rbp+150h+var_1C0]
0x18017b66b  lea     rdx, byte_1803674D5
0x18017b672  jmp     loc_18017B5B2
0x18017b677  lea     rdx, [rbp+150h+instance]
0x18017b67b  mov     rcx, rsi; self
0x18017b67e  call    MI_Instance_Destruct
0x18017b683  mov     ebx, eax
0x18017b685  test    eax, eax
0x18017b687  jz      short loc_18017B6CF
0x18017b689  mov     eax, cs:dword_18039EB68
0x18017b68f  cmp     eax, 2
0x18017b692  jbe     short loc_18017B6CF
0x18017b694  mov     [rsp+250h+var_1D8], ebx
0x18017b698  mov     dword ptr [rsp+250h+var_1E0], 0CAh
0x18017b6a0  lea     r13, aSpacesStoraget; "SPACES_StorageTier_Invoke_DeleteObject"
0x18017b6a7  mov     [rbp+150h+var_1C0], r13
0x18017b6ab  lea     rax, [rsp+250h+var_1D8]
0x18017b6b0  mov     [rsp+250h+var_220], rax
0x18017b6b5  lea     rax, [rsp+250h+var_1E0]
0x18017b6ba  mov     [rsp+250h+var_228], rax
0x18017b6bf  lea     rax, [rbp+150h+var_1C0]
0x18017b6c3  lea     rdx, unk_1803682F0
0x18017b6ca  jmp     loc_18017B5C8
0x18017b6cf  lea     r13, aSpacesStoraget; "SPACES_StorageTier_Invoke_DeleteObject"
0x18017b6d6  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18017b6dd  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18017b6e2  jmp     short loc_18017B6EE
0x18017b6e4  xor     r15d, r15d
0x18017b6e7  lea     r13, aSpacesStoraget; "SPACES_StorageTier_Invoke_DeleteObject"
0x18017b6ee  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18017b6f2  mov     [rsp+250h+var_228], r15; unsigned __int16 *
0x18017b6f7  mov     [rsp+250h+var_230], ebx; enum _MI_Result
0x18017b6fb  lea     r9, [rbp+150h+var_A0]; struct _MI_ConstUint32Field *
0x18017b702  mov     rdx, [rbp+150h+var_190]; unsigned __int16 *
0x18017b706  mov     rcx, [rbp+150h+var_1B8]; unsigned __int16 *
0x18017b70a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18017b70f  test    r12d, r12d
0x18017b712  jnz     loc_18017B867
0x18017b718  lea     rcx, [rbp+150h+var_188]; this
0x18017b71c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18017b721  mov     eax, cs:dword_18039EB68
0x18017b727  cmp     eax, 5
0x18017b72a  jbe     loc_18017B867
0x18017b730  mov     rdx, 400000000000h
0x18017b73a  lea     rcx, dword_18039EB68
0x18017b741  call    _tlgKeywordOn
0x18017b746  test    al, al
0x18017b748  jz      loc_18017B867
0x18017b74e  cmp     [rbp+150h+var_90], r15b
0x18017b755  jz      short loc_18017B792
0x18017b757  mov     rax, [rbp+150h+var_98]
0x18017b75e  movups  xmm0, xmmword ptr [rax]
0x18017b761  movaps  xmmword ptr [rbp+150h+var_150.ft], xmm0
0x18017b765  movups  xmm1, xmmword ptr [rax+10h]
0x18017b769  movaps  xmmword ptr [rbp+150h+var_150.serverName], xmm1
0x18017b76d  movups  xmm0, xmmword ptr [rax+20h]
0x18017b771  movaps  xmmword ptr [rbp+150h+var_150.reserved], xmm0
0x18017b775  movups  xmm1, xmmword ptr [rax+30h]
0x18017b779  movaps  xmmword ptr [rbp+150h+var_150.reserved+10h], xmm1
0x18017b77d  xor     r8d, r8d; unsigned __int16 *
0x18017b780  lea     rdx, [rbp+150h+var_150]; struct _MI_Instance
0x18017b784  lea     rcx, name; "ObjectId"
0x18017b78b  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18017b790  jmp     short loc_18017B795
0x18017b792  mov     rax, r15
0x18017b795  mov     [rbp+150h+var_1B8], rax
0x18017b799  mov     [rbp+150h+var_190], r15
0x18017b79d  mov     [rbp+150h+var_198], r15
0x18017b7a1  mov     rax, [rbp+150h+var_180]
0x18017b7a5  sub     rax, [rbp+150h+var_188]
0x18017b7a9  imul    rax, 3E8h
0x18017b7b0  xor     edx, edx
0x18017b7b2  div     [rbp+150h+var_178]
0x18017b7b6  mov     [rbp+150h+var_1A0], rax
0x18017b7ba  mov     dword ptr [rsp+250h+var_1E0], ebx
0x18017b7be  mov     al, [rbp+150h+var_A0.exists]
0x18017b7c4  neg     al
0x18017b7c6  sbb     ecx, ecx
0x18017b7c8  and     ecx, [rbp+150h+var_A0.value]
0x18017b7ce  mov     [rsp+250h+var_1D8], ecx
0x18017b7d2  mov     dword ptr [rbp+150h+var_1C0], r14d
0x18017b7d6  cmp     [rdi+48h], r15b
0x18017b7da  jz      short loc_18017B7E2
0x18017b7dc  mov     rax, [rdi+40h]
0x18017b7e0  jmp     short loc_18017B7E5
0x18017b7e2  mov     rax, r15
0x18017b7e5  mov     [rbp+150h+var_1A8], rax
0x18017b7e9  lea     rax, aDeletestoraget; "DeleteStorageTier"
0x18017b7f0  mov     [rbp+150h+var_1B0], rax
0x18017b7f4  lea     rax, aStoragetier; "StorageTier"
0x18017b7fb  mov     [rbp+150h+var_1C8], rax
0x18017b7ff  lea     rax, [rbp+150h+var_1B8]
0x18017b803  mov     [rsp+250h+var_1E8], rax
0x18017b808  lea     rax, [rbp+150h+var_190]
0x18017b80c  mov     [rsp+250h+var_1F0], rax
0x18017b811  lea     rax, [rbp+150h+var_198]
0x18017b815  mov     [rsp+250h+var_1F8], rax
0x18017b81a  lea     rax, [rbp+150h+var_1A0]
0x18017b81e  mov     [rsp+250h+var_200], rax
0x18017b823  lea     rax, [rsp+250h+var_1E0]
0x18017b828  mov     [rsp+250h+var_208], rax
0x18017b82d  lea     rax, [rsp+250h+var_1D8]
0x18017b832  mov     [rsp+250h+var_210], rax
0x18017b837  lea     rax, [rbp+150h+var_1C0]
0x18017b83b  mov     [rsp+250h+var_218], rax
0x18017b840  lea     rax, [rbp+150h+var_1A8]
0x18017b844  mov     [rsp+250h+var_220], rax
0x18017b849  lea     rax, [rbp+150h+var_1B0]
0x18017b84d  mov     [rsp+250h+var_228], rax
0x18017b852  lea     rax, [rbp+150h+var_1C8]
0x18017b856  mov     qword ptr [rsp+250h+var_230], rax
0x18017b85b  lea     rdx, word_18036750E
0x18017b862  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18017b867  lea     rcx, [rbp+150h+instance]; self
0x18017b86b  call    MI_Instance_Destruct
0x18017b870  mov     eax, cs:dword_18039EB68
0x18017b876  cmp     eax, 5
0x18017b879  jbe     short loc_18017B8A6
0x18017b87b  mov     dword ptr [rsp+250h+var_1E0], 0EBh
0x18017b883  mov     [rbp+150h+var_1B8], r13
0x18017b887  lea     rax, [rsp+250h+var_1E0]
0x18017b88c  mov     [rsp+250h+var_228], rax
0x18017b891  lea     rax, [rbp+150h+var_1B8]
0x18017b895  mov     qword ptr [rsp+250h+var_230], rax
0x18017b89a  lea     rdx, byte_180367233
0x18017b8a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017b8a6  mov     edx, ebx; result
0x18017b8a8  mov     rcx, rsi; context
0x18017b8ab  call    MI_Context_PostResult_0
0x18017b8b0  lea     rcx, [rbp+150h+var_188]; this
0x18017b8b4  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18017b8b9  lea     rcx, [rbp+150h+var_1D0]
0x18017b8bd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
  ... truncated ...
```
