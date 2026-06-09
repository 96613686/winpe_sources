# SPACES_StoragePool_Invoke_CreateVirtualDisk

- ea: `0x18015a3e0`
- end: `0x18015a9a0`
- name: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
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
- `0x18015a3e0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a45d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a4c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a969`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a45d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a4c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a969`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015a486`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015a486`

## string_xrefs

- `0x18015a4da`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x18015a606`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x18015a6ef`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x18015a71e`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x18015a733`: `SPACES_StoragePool_Invoke_CreateVirtualDisk`
- `0x18015a884`: `CreateVirtualDisk`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVirtualDisk(
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
  struct _MI_Instance *v53; // [rsp+290h] [rbp+190h]
  char v54; // [rsp+298h] [rbp+198h]
  struct _MI_Instance *v55; // [rsp+2A0h] [rbp+1A0h]
  char v56; // [rsp+2A8h] [rbp+1A8h]
  GUID ActivityId; // [rsp+2C0h] [rbp+1C0h] BYREF
  GUID v58; // [rsp+2D0h] [rbp+1D0h]
  GUID v59; // [rsp+2E0h] [rbp+1E0h] BYREF

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
    LODWORD(v38) = 149;
    v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVirtualDisk",
      (unsigned int)&dword_18035DCB4,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v38);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x148u);
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
        LODWORD(v41) = 180;
        v34 = &v38;
        v20 = &v41;
        v21 = word_18035BCFA;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk";
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
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVirtualDisk_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v42) = v15;
          LODWORD(v43) = 188;
          v34 = (const char **)&v42;
          v20 = (const char **)&v43;
          v21 = (__int16 *)&byte_18035D5D7;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v37 + 48LL))(
                v37,
                720897,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v36 = v15;
            LODWORD(v35) = 207;
            v39 = "SPACES_StoragePool_Invoke_CreateVirtualDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&byte_18035CFEF,
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
          LODWORD(v39) = 199;
          v34 = &v44;
          v20 = &v39;
          v21 = (__int16 *)&unk_18035BED8;
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
        v44 = "VirtualDisk";
        v43 = (unsigned __int64)(1000LL * (v46[1] - v46[0])) / v46[2];
        LODWORD(v35) = v15;
        v36 = v52.exists != 0 ? v52.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v42 = v29;
        v41 = "CreateVirtualDisk";
        v38 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)byte_18035D061,
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
    LODWORD(v35) = 240;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVirtualDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&word_18035E5D6,
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
0x18015a3e0  mov     [rsp-8+arg_10], rbx
0x18015a3e5  push    rbp
0x18015a3e6  push    rsi
0x18015a3e7  push    rdi
0x18015a3e8  push    r12
0x18015a3ea  push    r13
0x18015a3ec  push    r14
0x18015a3ee  push    r15
0x18015a3f0  lea     rbp, [rsp-200h]
0x18015a3f8  sub     rsp, 300h
0x18015a3ff  mov     rax, cs:__security_cookie
0x18015a406  xor     rax, rsp
0x18015a409  mov     [rbp+230h+var_40], rax
0x18015a410  mov     [rbp+230h+var_298], r9
0x18015a414  mov     rsi, rdx
0x18015a417  mov     r15, rcx
0x18015a41a  mov     rax, [rbp+230h+arg_20]
0x18015a421  mov     [rbp+230h+var_270], rax
0x18015a425  mov     rdi, [rbp+230h+arg_28]
0x18015a42c  mov     r13, [rbp+230h+arg_30]
0x18015a433  xorps   xmm0, xmm0
0x18015a436  xor     eax, eax
0x18015a438  movups  xmmword ptr [rbp+230h+value], xmm0
0x18015a43c  movups  xmmword ptr [rbp+230h+value+10h], xmm0
0x18015a440  mov     qword ptr [rbp+230h+value+20h], rax
0x18015a444  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015a44b  movdqu  xmmword ptr [rbp+230h+ActivityId.Data1], xmm0
0x18015a453  lea     rdx, [rbp+230h+ActivityId]; ActivityId
0x18015a45a  lea     ecx, [rax+1]; ControlCode
0x18015a45d  call    cs:__imp_EventActivityIdControl
0x18015a464  nop     dword ptr [rax+rax+00h]
0x18015a469  lea     r9, [rbp+230h+value]; value
0x18015a46d  mov     rcx, rsi; context
0x18015a470  call    MI_Context_GetCustomOption_1
0x18015a475  xor     ebx, ebx
0x18015a477  test    eax, eax
0x18015a479  jnz     short loc_18015A492
0x18015a47b  lea     rdx, [rbp+230h+ActivityId]; pclsid
0x18015a482  mov     rcx, qword ptr [rbp+230h+value]; lpsz
0x18015a486  call    cs:__imp_CLSIDFromString
0x18015a48d  nop     dword ptr [rax+rax+00h]
0x18015a492  mov     rcx, qword ptr [rbp+230h+ActivityId.Data1]
0x18015a499  mov     [rbp+230h+var_60], rcx
0x18015a4a0  mov     rax, qword ptr [rbp+230h+ActivityId.Data4]
0x18015a4a7  mov     [rbp+230h+var_58], rax
0x18015a4ae  mov     qword ptr [rbp+230h+var_50.Data1], rcx
0x18015a4b5  mov     qword ptr [rbp+230h+var_50.Data4], rax
0x18015a4bc  lea     rdx, [rbp+230h+var_50]; ActivityId
0x18015a4c3  mov     ecx, 4; ControlCode
0x18015a4c8  call    cs:__imp_EventActivityIdControl
0x18015a4cf  nop     dword ptr [rax+rax+00h]
0x18015a4d4  mov     eax, cs:dword_18039EB68
0x18015a4da  lea     rcx, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015a4e1  cmp     eax, 5
0x18015a4e4  jbe     short loc_18015A511
0x18015a4e6  mov     dword ptr [rbp+230h+var_2A8], 95h
0x18015a4ed  mov     [rsp+330h+var_2C0], rcx
0x18015a4f2  lea     rax, [rbp+230h+var_2A8]
0x18015a4f6  mov     [rsp+330h+var_308], rax
0x18015a4fb  lea     rax, [rsp+330h+var_2C0]
0x18015a500  mov     qword ptr [rsp+330h+var_310], rax
0x18015a505  lea     rdx, dword_18035DCB4
0x18015a50c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015a511  mov     [rbp+230h+instance.ft], rbx
0x18015a515  xor     edx, edx; Val
0x18015a517  mov     r8d, 148h; Size
0x18015a51d  lea     rcx, [rbp+230h+instance.classDecl]; void *
0x18015a521  call    memset_0
0x18015a526  xorps   xmm0, xmm0
0x18015a529  xor     eax, eax
0x18015a52b  movups  [rbp+230h+var_248], xmm0
0x18015a52f  mov     [rbp+230h+var_238], rax
0x18015a533  mov     [rbp+230h+var_2B0], rbx
0x18015a537  lea     rcx, [rbp+230h+var_2B0]
0x18015a53b  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015a540  mov     [rbp+230h+var_2B0], rbx
0x18015a544  mov     r14d, ebx
0x18015a547  lea     rcx, [rbp+230h+var_268]; this
0x18015a54b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015a550  mov     rcx, rsi; context
0x18015a553  call    WspIsRemoteRequest
0x18015a558  mov     r12d, eax
0x18015a55b  test    eax, eax
0x18015a55d  jnz     short loc_18015A582
0x18015a55f  lea     rcx, [rbp+230h+var_268]; this
0x18015a563  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015a568  cmp     [rdi+48h], bl
0x18015a56b  jz      short loc_18015A57F
0x18015a56d  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015a571  call    WspIsRemoteInstance
0x18015a576  test    al, al
0x18015a578  lea     r14d, [r12+1]
0x18015a57d  jnz     short loc_18015A582
0x18015a57f  mov     r14d, ebx
0x18015a582  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015a589  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015a58e  mov     ebx, eax
0x18015a590  test    eax, eax
0x18015a592  jnz     loc_18015A733
0x18015a598  mov     dword ptr [rbp+230h+var_248], 0Bh
0x18015a59f  mov     rax, [rdi+40h]
0x18015a5a3  mov     qword ptr [rbp+230h+var_248+8], rax
0x18015a5a7  mov     rbx, [r15]
0x18015a5aa  lea     rcx, [rbp+230h+var_2B0]
0x18015a5ae  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015a5b3  mov     [rsp+330h+var_310], 1; int
0x18015a5bb  lea     r9, [rbp+230h+var_2B0]; struct ISpWmiObject **
0x18015a5bf  lea     r8, [rbp+230h+var_248]; struct _SP_OBJECT_ID *
0x18015a5c3  mov     rdx, rsi; context
0x18015a5c6  mov     rcx, rbx; this
0x18015a5c9  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015a5ce  mov     ebx, eax
0x18015a5d0  test    eax, eax
0x18015a5d2  jz      short loc_18015A626
0x18015a5d4  mov     eax, cs:dword_18039EB68
0x18015a5da  cmp     eax, 2
0x18015a5dd  jbe     loc_18015A71E
0x18015a5e3  mov     dword ptr [rbp+230h+var_2A8], ebx
0x18015a5e6  mov     dword ptr [rbp+230h+var_290], 0B4h
0x18015a5ed  lea     rax, [rbp+230h+var_2A8]
0x18015a5f1  mov     [rsp+330h+var_300], rax
0x18015a5f6  lea     rax, [rbp+230h+var_290]
0x18015a5fa  lea     rdx, word_18035BCFA
0x18015a601  mov     [rsp+330h+var_308], rax
0x18015a606  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015a60d  lea     rax, [rsp+330h+var_2C0]
0x18015a612  mov     [rsp+330h+var_2C0], r15
0x18015a617  mov     qword ptr [rsp+330h+var_310], rax
0x18015a61c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015a621  jmp     loc_18015A725
0x18015a626  lea     r8, [rbp+230h+instance]; instance
0x18015a62a  lea     rdx, SPACES_StoragePool_CreateVirtualDisk_rtti; methodDecl
0x18015a631  mov     rcx, rsi; context
0x18015a634  call    MI_Context_ConstructParameters
0x18015a639  mov     ebx, eax
0x18015a63b  test    eax, eax
0x18015a63d  jz      short loc_18015A66E
0x18015a63f  mov     eax, cs:dword_18039EB68
0x18015a645  cmp     eax, 2
0x18015a648  jbe     loc_18015A71E
0x18015a64e  mov     dword ptr [rbp+230h+var_288], ebx
0x18015a651  mov     dword ptr [rbp+230h+var_280], 0BCh
0x18015a658  lea     rax, [rbp+230h+var_288]
0x18015a65c  mov     [rsp+330h+var_300], rax
0x18015a661  lea     rax, [rbp+230h+var_280]
0x18015a665  lea     rdx, byte_18035D5D7
0x18015a66c  jmp     short loc_18015A601
0x18015a66e  mov     rcx, [rbp+230h+var_2B0]
0x18015a672  mov     rax, [rcx]
0x18015a675  lea     rdx, [rbp+230h+instance]
0x18015a679  mov     qword ptr [rsp+330h+var_310], rdx
0x18015a67e  mov     r9, r13
0x18015a681  mov     r8, rsi
0x18015a684  mov     edx, 0B0001h
0x18015a689  mov     rax, [rax+30h]
0x18015a68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a692  mov     ebx, eax
0x18015a694  test    eax, eax
0x18015a696  jz      short loc_18015A6C6
0x18015a698  mov     eax, cs:dword_18039EB68
0x18015a69e  cmp     eax, 2
0x18015a6a1  jbe     short loc_18015A71E
0x18015a6a3  mov     dword ptr [rbp+230h+var_278], ebx
0x18015a6a6  mov     dword ptr [rbp+230h+var_2A0], 0C7h
0x18015a6ad  lea     rax, [rbp+230h+var_278]
0x18015a6b1  mov     [rsp+330h+var_300], rax
0x18015a6b6  lea     rax, [rbp+230h+var_2A0]
0x18015a6ba  lea     rdx, unk_18035BED8
0x18015a6c1  jmp     loc_18015A601
0x18015a6c6  lea     rdx, [rbp+230h+instance]
0x18015a6ca  mov     rcx, rsi; self
0x18015a6cd  call    MI_Instance_Destruct
0x18015a6d2  mov     ebx, eax
0x18015a6d4  test    eax, eax
0x18015a6d6  jz      short loc_18015A71E
0x18015a6d8  mov     eax, cs:dword_18039EB68
0x18015a6de  cmp     eax, 2
0x18015a6e1  jbe     short loc_18015A71E
0x18015a6e3  mov     [rsp+330h+var_2B8], ebx
0x18015a6e7  mov     dword ptr [rsp+330h+var_2C0], 0CFh
0x18015a6ef  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015a6f6  mov     [rbp+230h+var_2A0], r15
0x18015a6fa  lea     rax, [rsp+330h+var_2B8]
0x18015a6ff  mov     [rsp+330h+var_300], rax
0x18015a704  lea     rax, [rsp+330h+var_2C0]
0x18015a709  mov     [rsp+330h+var_308], rax
0x18015a70e  lea     rax, [rbp+230h+var_2A0]
0x18015a712  lea     rdx, byte_18035CFEF
0x18015a719  jmp     loc_18015A617
0x18015a71e  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015a725  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015a72c  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015a731  jmp     short loc_18015A73A
0x18015a733  lea     r15, aSpacesStoragep_47; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015a73a  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015a73e  mov     [rsp+330h+var_308], 0; unsigned __int16 *
0x18015a747  mov     [rsp+330h+var_310], ebx; enum _MI_Result
0x18015a74b  lea     r9, [rbp+230h+var_180]; struct _MI_ConstUint32Field *
0x18015a752  mov     rdx, [rbp+230h+var_270]; unsigned __int16 *
0x18015a756  mov     rcx, [rbp+230h+var_298]; unsigned __int16 *
0x18015a75a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015a75f  test    r12d, r12d
0x18015a762  jnz     loc_18015A902
0x18015a768  lea     rcx, [rbp+230h+var_268]; this
0x18015a76c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015a771  mov     eax, cs:dword_18039EB68
0x18015a777  cmp     eax, 5
0x18015a77a  jbe     loc_18015A902
0x18015a780  mov     rdx, 400000000000h
0x18015a78a  lea     rcx, dword_18039EB68
0x18015a791  call    _tlgKeywordOn
0x18015a796  test    al, al
0x18015a798  jz      loc_18015A902
0x18015a79e  cmp     [rbp+230h+var_88], r12b
0x18015a7a5  jz      short loc_18015A7E2
0x18015a7a7  mov     rax, [rbp+230h+var_90]
0x18015a7ae  movups  xmm0, xmmword ptr [rax]
0x18015a7b1  movaps  xmmword ptr [rbp+230h+var_230.ft], xmm0
0x18015a7b5  movups  xmm1, xmmword ptr [rax+10h]
0x18015a7b9  movaps  xmmword ptr [rbp+230h+var_230.serverName], xmm1
0x18015a7bd  movups  xmm0, xmmword ptr [rax+20h]
0x18015a7c1  movaps  xmmword ptr [rbp+230h+var_230.reserved], xmm0
0x18015a7c5  movups  xmm1, xmmword ptr [rax+30h]
0x18015a7c9  movaps  xmmword ptr [rbp+230h+var_230.reserved+10h], xmm1
0x18015a7cd  xor     r8d, r8d; unsigned __int16 *
0x18015a7d0  lea     rdx, [rbp+230h+var_230]; struct _MI_Instance
0x18015a7d4  lea     rcx, name; "ObjectId"
0x18015a7db  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015a7e0  jmp     short loc_18015A7E4
0x18015a7e2  xor     eax, eax
0x18015a7e4  mov     [rbp+230h+var_298], rax
0x18015a7e8  cmp     [rbp+230h+var_98], 0
0x18015a7ef  jz      short loc_18015A82C
0x18015a7f1  mov     rax, [rbp+230h+var_A0]
0x18015a7f8  movups  xmm0, xmmword ptr [rax]
0x18015a7fb  movaps  xmmword ptr [rbp+230h+var_230.ft], xmm0
0x18015a7ff  movups  xmm1, xmmword ptr [rax+10h]
0x18015a803  movaps  xmmword ptr [rbp+230h+var_230.serverName], xmm1
0x18015a807  movups  xmm0, xmmword ptr [rax+20h]
0x18015a80b  movaps  xmmword ptr [rbp+230h+var_230.reserved], xmm0
0x18015a80f  movups  xmm1, xmmword ptr [rax+30h]
0x18015a813  movaps  xmmword ptr [rbp+230h+var_230.reserved+10h], xmm1
0x18015a817  xor     r8d, r8d; unsigned __int16 *
0x18015a81a  lea     rdx, [rbp+230h+var_230]; struct _MI_Instance
0x18015a81e  lea     rcx, name; "ObjectId"
0x18015a825  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015a82a  jmp     short loc_18015A82E
0x18015a82c  xor     eax, eax
0x18015a82e  mov     [rbp+230h+var_270], rax
0x18015a832  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18015a839  mov     [rbp+230h+var_278], rax
0x18015a83d  mov     rax, [rbp+230h+var_260]
0x18015a841  sub     rax, [rbp+230h+var_268]
0x18015a845  imul    rax, 3E8h
0x18015a84c  xor     edx, edx
0x18015a84e  div     [rbp+230h+var_258]
0x18015a852  mov     [rbp+230h+var_280], rax
0x18015a856  mov     dword ptr [rsp+330h+var_2C0], ebx
0x18015a85a  mov     al, [rbp+230h+var_180.exists]
0x18015a860  neg     al
0x18015a862  sbb     ecx, ecx
0x18015a864  and     ecx, [rbp+230h+var_180.value]
0x18015a86a  mov     [rsp+330h+var_2B8], ecx
0x18015a86e  mov     dword ptr [rbp+230h+var_2A0], r14d
0x18015a872  cmp     byte ptr [rdi+48h], 0
0x18015a876  jz      short loc_18015A87E
0x18015a878  mov     rax, [rdi+40h]
0x18015a87c  jmp     short loc_18015A880
0x18015a87e  xor     eax, eax
0x18015a880  mov     [rbp+230h+var_288], rax
0x18015a884  lea     rax, aCreatevirtuald_2; "CreateVirtualDisk"
0x18015a88b  mov     [rbp+230h+var_290], rax
0x18015a88f  lea     rax, aStoragepool_0; "StoragePool"
0x18015a896  mov     [rbp+230h+var_2A8], rax
0x18015a89a  lea     rax, [rbp+230h+var_298]
0x18015a89e  mov     [rsp+330h+var_2C8], rax
0x18015a8a3  lea     rax, [rbp+230h+var_270]
0x18015a8a7  mov     [rsp+330h+var_2D0], rax
0x18015a8ac  lea     rax, [rbp+230h+var_278]
0x18015a8b0  mov     [rsp+330h+var_2D8], rax
0x18015a8b5  lea     rax, [rbp+230h+var_280]
0x18015a8b9  mov     [rsp+330h+var_2E0], rax
0x18015a8be  lea     rax, [rsp+330h+var_2C0]
0x18015a8c3  mov     [rsp+330h+var_2E8], rax
0x18015a8c8  lea     rax, [rsp+330h+var_2B8]
0x18015a8cd  mov     [rsp+330h+var_2F0], rax
0x18015a8d2  lea     rax, [rbp+230h+var_2A0]
0x18015a8d6  mov     [rsp+330h+var_2F8], rax
0x18015a8db  lea     rax, [rbp+230h+var_288]
0x18015a8df  mov     [rsp+330h+var_300], rax
0x18015a8e4  lea     rax, [rbp+230h+var_290]
0x18015a8e8  mov     [rsp+330h+var_308], rax
0x18015a8ed  lea     rax, [rbp+230h+var_2A8]
0x18015a8f1  mov     qword ptr [rsp+330h+var_310], rax
0x18015a8f6  lea     rdx, byte_18035D061
0x18015a8fd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18015a902  lea     rcx, [rbp+230h+instance]; self
0x18015a906  call    MI_Instance_Destruct
0x18015a90b  mov     eax, cs:dword_18039EB68
0x18015a911  cmp     eax, 5
  ... truncated ...
```
