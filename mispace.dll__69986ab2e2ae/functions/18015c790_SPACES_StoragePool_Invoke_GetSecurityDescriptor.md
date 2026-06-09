# SPACES_StoragePool_Invoke_GetSecurityDescriptor

- ea: `0x18015c790`
- end: `0x18015ccd5`
- name: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- size: `1349`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
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
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18015c790`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c80d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c878`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015cc9e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c80d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c878`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015cc9e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015c836`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015c836`

## string_xrefs

- `0x18015cbb2`: `GetSecurityDescriptor`
- `0x18015c88a`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015c99c`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015c9fd`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015ca6f`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015cac4`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`
- `0x18015cc4c`: `SPACES_StoragePool_Invoke_GetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_GetSecurityDescriptor(
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
  int v13; // r15d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  const MI_Char *v31; // rax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  const char *v36; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v37; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  const char *v40; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v43; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v47[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v48; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v49; // [rsp+F8h] [rbp-8h]
  MI_Value value; // [rsp+100h] [rbp+0h] BYREF
  MI_Instance instance; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v52; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+1A0h] [rbp+A0h] BYREF
  GUID v54; // [rsp+1B0h] [rbp+B0h]
  GUID v55; // [rsp+1C0h] [rbp+C0h] BYREF

  v41 = a4;
  v46 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v54 = ActivityId;
  v55 = ActivityId;
  EventActivityIdControl(4u, &v55);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v39) = 2100;
    v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_GetSecurityDescriptor",
      (unsigned int)&byte_18035B4E7,
      v11,
      v12,
      (__int64)&v36,
      (__int64)&v39);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  v48 = 0;
  v49 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v47);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v47);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v48) = 11;
    *((_QWORD *)&v48 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v48, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v39) = v15;
        LODWORD(v42) = 2131;
        v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_18035C8CC,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_GetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 2139;
          v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)byte_18035C121,
            v21,
            v22,
            (__int64)&v36,
            (__int64)&v44,
            (__int64)&v43);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720902,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 2150;
            v36 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&dword_18035BBBC,
              v24,
              v25,
              (__int64)&v36,
              (__int64)&v40,
              (__int64)&v45);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v36) = 2158;
            v40 = "SPACES_StoragePool_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_18035B8ED,
              v27,
              v28,
              (__int64)&v40,
              (__int64)&v36,
              (__int64)&v37);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v41, v46, a6 + 4, &v52, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v47);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        v41 = 0;
        v46 = 0;
        v45 = 0;
        v44 = (unsigned __int64)(1000LL * (v47[1] - v47[0])) / v47[2];
        LODWORD(v36) = v15;
        v37 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v40) = v13;
        if ( a6[4].exists )
          v31 = a6[4].value;
        else
          v31 = 0;
        v43 = v31;
        v42 = "GetSecurityDescriptor";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)byte_18035CAE9,
          v29,
          v30,
          (__int64)&v39,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v44,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v41);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v36) = 2191;
    v41 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)&word_18035D21E,
      v33,
      v34,
      (__int64)&v41,
      (__int64)&v36);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v47);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v55);
}

```

## disassembly

```asm
0x18015c790  mov     [rsp-8+arg_10], rbx
0x18015c795  push    rbp
0x18015c796  push    rsi
0x18015c797  push    rdi
0x18015c798  push    r12
0x18015c79a  push    r13
0x18015c79c  push    r14
0x18015c79e  push    r15
0x18015c7a0  lea     rbp, [rsp-0E0h]
0x18015c7a8  sub     rsp, 1E0h
0x18015c7af  mov     rax, cs:__security_cookie
0x18015c7b6  xor     rax, rsp
0x18015c7b9  mov     [rbp+110h+var_40], rax
0x18015c7c0  mov     [rbp+110h+var_178], r9
0x18015c7c4  mov     rsi, rdx
0x18015c7c7  mov     rdi, rcx
0x18015c7ca  mov     rax, [rbp+110h+arg_20]
0x18015c7d1  mov     [rbp+110h+var_150], rax
0x18015c7d5  mov     r14, [rbp+110h+arg_28]
0x18015c7dc  mov     r13, [rbp+110h+arg_30]
0x18015c7e3  xorps   xmm0, xmm0
0x18015c7e6  xor     eax, eax
0x18015c7e8  movups  xmmword ptr [rbp+110h+value], xmm0
0x18015c7ec  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18015c7f0  mov     qword ptr [rbp+110h+value+20h], rax
0x18015c7f4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015c7fb  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18015c803  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18015c80a  lea     ecx, [rax+1]; ControlCode
0x18015c80d  call    cs:__imp_EventActivityIdControl
0x18015c814  nop     dword ptr [rax+rax+00h]
0x18015c819  lea     r9, [rbp+110h+value]; value
0x18015c81d  mov     rcx, rsi; context
0x18015c820  call    MI_Context_GetCustomOption_1
0x18015c825  xor     ebx, ebx
0x18015c827  test    eax, eax
0x18015c829  jnz     short loc_18015C842
0x18015c82b  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18015c832  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18015c836  call    cs:__imp_CLSIDFromString
0x18015c83d  nop     dword ptr [rax+rax+00h]
0x18015c842  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18015c849  mov     [rbp+110h+var_60], rcx
0x18015c850  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18015c857  mov     [rbp+110h+var_58], rax
0x18015c85e  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18015c865  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18015c86c  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18015c873  mov     ecx, 4; ControlCode
0x18015c878  call    cs:__imp_EventActivityIdControl
0x18015c87f  nop     dword ptr [rax+rax+00h]
0x18015c884  mov     eax, cs:dword_18039EB68
0x18015c88a  lea     rcx, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015c891  cmp     eax, 5
0x18015c894  jbe     short loc_18015C8C1
0x18015c896  mov     dword ptr [rbp+110h+var_188], 834h
0x18015c89d  mov     [rsp+210h+var_1A0], rcx
0x18015c8a2  lea     rax, [rbp+110h+var_188]
0x18015c8a6  mov     [rsp+210h+var_1E8], rax
0x18015c8ab  lea     rax, [rsp+210h+var_1A0]
0x18015c8b0  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015c8b5  lea     rdx, byte_18035B4E7
0x18015c8bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015c8c1  mov     [rbp+110h+instance.ft], rbx
0x18015c8c5  xor     edx, edx; Val
0x18015c8c7  lea     r8d, [rdx+60h]; Size
0x18015c8cb  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18015c8cf  call    memset_0
0x18015c8d4  xorps   xmm0, xmm0
0x18015c8d7  xor     eax, eax
0x18015c8d9  movups  [rbp+110h+var_128], xmm0
0x18015c8dd  mov     [rbp+110h+var_118], rax
0x18015c8e1  mov     [rbp+110h+var_190], rbx
0x18015c8e5  lea     rcx, [rbp+110h+var_190]
0x18015c8e9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015c8ee  mov     [rbp+110h+var_190], rbx
0x18015c8f2  mov     r15d, ebx
0x18015c8f5  lea     rcx, [rbp+110h+var_148]; this
0x18015c8f9  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015c8fe  mov     rcx, rsi; context
0x18015c901  call    WspIsRemoteRequest
0x18015c906  mov     r12d, eax
0x18015c909  test    eax, eax
0x18015c90b  jnz     short loc_18015C931
0x18015c90d  lea     rcx, [rbp+110h+var_148]; this
0x18015c911  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015c916  cmp     [r14+48h], bl
0x18015c91a  jz      short loc_18015C92E
0x18015c91c  mov     rcx, [r14+40h]; unsigned __int16 *
0x18015c920  call    WspIsRemoteInstance
0x18015c925  test    al, al
0x18015c927  lea     r15d, [r12+1]
0x18015c92c  jnz     short loc_18015C931
0x18015c92e  mov     r15d, ebx
0x18015c931  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015c938  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015c93d  mov     ebx, eax
0x18015c93f  test    eax, eax
0x18015c941  jnz     loc_18015CB04
0x18015c947  mov     dword ptr [rbp+110h+var_128], 0Bh
0x18015c94e  mov     rax, [r14+40h]
0x18015c952  mov     qword ptr [rbp+110h+var_128+8], rax
0x18015c956  mov     rbx, [rdi]
0x18015c959  lea     rcx, [rbp+110h+var_190]
0x18015c95d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015c962  mov     [rsp+210h+var_1F0], 1; int
0x18015c96a  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18015c96e  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x18015c972  mov     rdx, rsi; context
0x18015c975  mov     rcx, rbx; this
0x18015c978  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015c97d  mov     ebx, eax
0x18015c97f  test    eax, eax
0x18015c981  jz      short loc_18015C9CB
0x18015c983  mov     eax, cs:dword_18039EB68
0x18015c989  cmp     eax, 2
0x18015c98c  jbe     loc_18015CAF8
0x18015c992  mov     dword ptr [rbp+110h+var_188], ebx
0x18015c995  mov     dword ptr [rbp+110h+var_170], 853h
0x18015c99c  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015c9a3  mov     [rsp+210h+var_1A0], rax
0x18015c9a8  lea     rax, [rbp+110h+var_188]
0x18015c9ac  mov     [rsp+210h+var_1E0], rax
0x18015c9b1  lea     rax, [rbp+110h+var_170]
0x18015c9b5  mov     [rsp+210h+var_1E8], rax
0x18015c9ba  lea     rax, [rsp+210h+var_1A0]
0x18015c9bf  lea     rdx, dword_18035C8CC
0x18015c9c6  jmp     loc_18015CAEE
0x18015c9cb  lea     r8, [rbp+110h+instance]; instance
0x18015c9cf  lea     rdx, SPACES_StoragePool_GetSecurityDescriptor_rtti; methodDecl
0x18015c9d6  mov     rcx, rsi; context
0x18015c9d9  call    MI_Context_ConstructParameters
0x18015c9de  mov     ebx, eax
0x18015c9e0  test    eax, eax
0x18015c9e2  jz      short loc_18015CA2C
0x18015c9e4  mov     eax, cs:dword_18039EB68
0x18015c9ea  cmp     eax, 2
0x18015c9ed  jbe     loc_18015CAF8
0x18015c9f3  mov     dword ptr [rbp+110h+var_168], ebx
0x18015c9f6  mov     dword ptr [rbp+110h+var_160], 85Bh
0x18015c9fd  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015ca04  mov     [rsp+210h+var_1A0], rax
0x18015ca09  lea     rax, [rbp+110h+var_168]
0x18015ca0d  mov     [rsp+210h+var_1E0], rax
0x18015ca12  lea     rax, [rbp+110h+var_160]
0x18015ca16  mov     [rsp+210h+var_1E8], rax
0x18015ca1b  lea     rax, [rsp+210h+var_1A0]
0x18015ca20  lea     rdx, byte_18035C121
0x18015ca27  jmp     loc_18015CAEE
0x18015ca2c  mov     rcx, [rbp+110h+var_190]
0x18015ca30  mov     rax, [rcx]
0x18015ca33  lea     rdx, [rbp+110h+instance]
0x18015ca37  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18015ca3c  mov     r9, r13
0x18015ca3f  mov     r8, rsi
0x18015ca42  mov     edx, 0B0006h
0x18015ca47  mov     rax, [rax+30h]
0x18015ca4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015ca50  mov     ebx, eax
0x18015ca52  test    eax, eax
0x18015ca54  jz      short loc_18015CA9B
0x18015ca56  mov     eax, cs:dword_18039EB68
0x18015ca5c  cmp     eax, 2
0x18015ca5f  jbe     loc_18015CAF8
0x18015ca65  mov     dword ptr [rbp+110h+var_158], ebx
0x18015ca68  mov     dword ptr [rbp+110h+var_180], 866h
0x18015ca6f  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015ca76  mov     [rsp+210h+var_1A0], rax
0x18015ca7b  lea     rax, [rbp+110h+var_158]
0x18015ca7f  mov     [rsp+210h+var_1E0], rax
0x18015ca84  lea     rax, [rbp+110h+var_180]
0x18015ca88  mov     [rsp+210h+var_1E8], rax
0x18015ca8d  lea     rax, [rsp+210h+var_1A0]
0x18015ca92  lea     rdx, dword_18035BBBC
0x18015ca99  jmp     short loc_18015CAEE
0x18015ca9b  lea     rdx, [rbp+110h+instance]
0x18015ca9f  mov     rcx, rsi; self
0x18015caa2  call    MI_Instance_Destruct
0x18015caa7  mov     ebx, eax
0x18015caa9  test    eax, eax
0x18015caab  jz      short loc_18015CAF8
0x18015caad  mov     eax, cs:dword_18039EB68
0x18015cab3  cmp     eax, 2
0x18015cab6  jbe     short loc_18015CAF8
0x18015cab8  mov     [rsp+210h+var_198], ebx
0x18015cabc  mov     dword ptr [rsp+210h+var_1A0], 86Eh
0x18015cac4  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015cacb  mov     [rbp+110h+var_180], rax
0x18015cacf  lea     rax, [rsp+210h+var_198]
0x18015cad4  mov     [rsp+210h+var_1E0], rax
0x18015cad9  lea     rax, [rsp+210h+var_1A0]
0x18015cade  mov     [rsp+210h+var_1E8], rax
0x18015cae3  lea     rax, [rbp+110h+var_180]
0x18015cae7  lea     rdx, byte_18035B8ED
0x18015caee  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015caf3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015caf8  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015caff  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015cb04  xor     r13d, r13d
0x18015cb07  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18015cb0c  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18015cb10  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x18015cb14  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18015cb18  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x18015cb1c  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x18015cb20  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015cb25  test    r12d, r12d
0x18015cb28  jnz     loc_18015CC30
0x18015cb2e  lea     rcx, [rbp+110h+var_148]; this
0x18015cb32  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015cb37  mov     eax, cs:dword_18039EB68
0x18015cb3d  cmp     eax, 5
0x18015cb40  jbe     loc_18015CC30
0x18015cb46  mov     rdx, 400000000000h
0x18015cb50  lea     rcx, dword_18039EB68
0x18015cb57  call    _tlgKeywordOn
0x18015cb5c  test    al, al
0x18015cb5e  jz      loc_18015CC30
0x18015cb64  mov     [rbp+110h+var_178], r13
0x18015cb68  mov     [rbp+110h+var_150], r13
0x18015cb6c  mov     [rbp+110h+var_158], r13
0x18015cb70  mov     rax, [rbp+110h+var_140]
0x18015cb74  sub     rax, [rbp+110h+var_148]
0x18015cb78  imul    rax, 3E8h
0x18015cb7f  xor     edx, edx
0x18015cb81  div     [rbp+110h+var_138]
0x18015cb85  mov     [rbp+110h+var_160], rax
0x18015cb89  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18015cb8d  mov     al, [rbp+110h+var_A0.exists]
0x18015cb90  neg     al
0x18015cb92  sbb     ecx, ecx
0x18015cb94  and     ecx, [rbp+110h+var_A0.value]
0x18015cb97  mov     [rsp+210h+var_198], ecx
0x18015cb9b  mov     dword ptr [rbp+110h+var_180], r15d
0x18015cb9f  cmp     [r14+48h], r13b
0x18015cba3  jz      short loc_18015CBAB
0x18015cba5  mov     rax, [r14+40h]
0x18015cba9  jmp     short loc_18015CBAE
0x18015cbab  mov     rax, r13
0x18015cbae  mov     [rbp+110h+var_168], rax
0x18015cbb2  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptor"
0x18015cbb9  mov     [rbp+110h+var_170], rax
0x18015cbbd  lea     rax, aStoragepool_0; "StoragePool"
0x18015cbc4  mov     [rbp+110h+var_188], rax
0x18015cbc8  lea     rax, [rbp+110h+var_178]
0x18015cbcc  mov     [rsp+210h+var_1A8], rax
0x18015cbd1  lea     rax, [rbp+110h+var_150]
0x18015cbd5  mov     [rsp+210h+var_1B0], rax
0x18015cbda  lea     rax, [rbp+110h+var_158]
0x18015cbde  mov     [rsp+210h+var_1B8], rax
0x18015cbe3  lea     rax, [rbp+110h+var_160]
0x18015cbe7  mov     [rsp+210h+var_1C0], rax
0x18015cbec  lea     rax, [rsp+210h+var_1A0]
0x18015cbf1  mov     [rsp+210h+var_1C8], rax
0x18015cbf6  lea     rax, [rsp+210h+var_198]
0x18015cbfb  mov     [rsp+210h+var_1D0], rax
0x18015cc00  lea     rax, [rbp+110h+var_180]
0x18015cc04  mov     [rsp+210h+var_1D8], rax
0x18015cc09  lea     rax, [rbp+110h+var_168]
0x18015cc0d  mov     [rsp+210h+var_1E0], rax
0x18015cc12  lea     rax, [rbp+110h+var_170]
0x18015cc16  mov     [rsp+210h+var_1E8], rax
0x18015cc1b  lea     rax, [rbp+110h+var_188]
0x18015cc1f  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015cc24  lea     rdx, byte_18035CAE9
0x18015cc2b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18015cc30  lea     rcx, [rbp+110h+instance]; self
0x18015cc34  call    MI_Instance_Destruct
0x18015cc39  mov     eax, cs:dword_18039EB68
0x18015cc3f  cmp     eax, 5
0x18015cc42  jbe     short loc_18015CC76
0x18015cc44  mov     dword ptr [rsp+210h+var_1A0], 88Fh
0x18015cc4c  lea     rax, aSpacesStoragep_4; "SPACES_StoragePool_Invoke_GetSecurityDe"...
0x18015cc53  mov     [rbp+110h+var_178], rax
0x18015cc57  lea     rax, [rsp+210h+var_1A0]
0x18015cc5c  mov     [rsp+210h+var_1E8], rax
0x18015cc61  lea     rax, [rbp+110h+var_178]
0x18015cc65  mov     qword ptr [rsp+210h+var_1F0], rax
0x18015cc6a  lea     rdx, word_18035D21E
0x18015cc71  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015cc76  mov     edx, ebx; result
0x18015cc78  mov     rcx, rsi; context
0x18015cc7b  call    MI_Context_PostResult_0
0x18015cc80  lea     rcx, [rbp+110h+var_148]; this
0x18015cc84  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18015cc89  lea     rcx, [rbp+110h+var_190]
0x18015cc8d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015cc92  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18015cc99  mov     ecx, 4; ControlCode
0x18015cc9e  call    cs:__imp_EventActivityIdControl
0x18015cca5  nop     dword ptr [rax+rax+00h]
0x18015ccaa  mov     rcx, [rbp+110h+var_40]
0x18015ccb1  xor     rcx, rsp; StackCookie
0x18015ccb4  call    __security_check_cookie
0x18015ccb9  mov     rbx, [rsp+210h+arg_10]
0x18015ccc1  add     rsp, 1E0h
0x18015ccc8  pop     r15
0x18015ccca  pop     r14
0x18015cccc  pop     r13
0x18015ccce  pop     r12
  ... truncated ...
```
