# SPACES_VirtualDisk_Invoke_SetSecurityDescriptor

- ea: `0x180142430`
- end: `0x180142975`
- name: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
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
- `0x180142430`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801424ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180142518`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014293e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801424ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180142518`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014293e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801424d6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801424d6`

## string_xrefs

- `0x18014252a`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18014263c`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18014269d`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x18014270f`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x180142764`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x1801428ec`: `SPACES_VirtualDisk_Invoke_SetSecurityDescriptor`
- `0x180142852`: `SetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_SetSecurityDescriptor(
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
    LODWORD(v39) = 576;
    v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_SetSecurityDescriptor",
      (unsigned int)word_180351912,
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
  CSmTimer::CSmTimer((CSmTimer *)v47);
  v13 = 0;
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
    LODWORD(v48) = 16;
    *((_QWORD *)&v48 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v48, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v39) = v15;
        LODWORD(v42) = 607;
        v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180353BE0,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_SetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 615;
          v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&byte_180352667,
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
                1048581,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 626;
            v36 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)byte_180352D5B,
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
            LODWORD(v36) = 634;
            v40 = "SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_1803522B5,
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
        v42 = "SetSecurityDescriptor";
        v39 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&dword_1803538D4,
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
    LODWORD(v36) = 667;
    v41 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_SetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)&dword_1803523BC,
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
0x180142430  mov     [rsp-8+arg_10], rbx
0x180142435  push    rbp
0x180142436  push    rsi
0x180142437  push    rdi
0x180142438  push    r12
0x18014243a  push    r13
0x18014243c  push    r14
0x18014243e  push    r15
0x180142440  lea     rbp, [rsp-0E0h]
0x180142448  sub     rsp, 1E0h
0x18014244f  mov     rax, cs:__security_cookie
0x180142456  xor     rax, rsp
0x180142459  mov     [rbp+110h+var_40], rax
0x180142460  mov     [rbp+110h+var_178], r9
0x180142464  mov     rsi, rdx
0x180142467  mov     rdi, rcx
0x18014246a  mov     rax, [rbp+110h+arg_20]
0x180142471  mov     [rbp+110h+var_150], rax
0x180142475  mov     r14, [rbp+110h+arg_28]
0x18014247c  mov     r13, [rbp+110h+arg_30]
0x180142483  xorps   xmm0, xmm0
0x180142486  xor     eax, eax
0x180142488  movups  xmmword ptr [rbp+110h+value], xmm0
0x18014248c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x180142490  mov     qword ptr [rbp+110h+value+20h], rax
0x180142494  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014249b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x1801424a3  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x1801424aa  lea     ecx, [rax+1]; ControlCode
0x1801424ad  call    cs:__imp_EventActivityIdControl
0x1801424b4  nop     dword ptr [rax+rax+00h]
0x1801424b9  lea     r9, [rbp+110h+value]; value
0x1801424bd  mov     rcx, rsi; context
0x1801424c0  call    MI_Context_GetCustomOption_1
0x1801424c5  xor     ebx, ebx
0x1801424c7  test    eax, eax
0x1801424c9  jnz     short loc_1801424E2
0x1801424cb  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x1801424d2  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x1801424d6  call    cs:__imp_CLSIDFromString
0x1801424dd  nop     dword ptr [rax+rax+00h]
0x1801424e2  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x1801424e9  mov     [rbp+110h+var_60], rcx
0x1801424f0  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x1801424f7  mov     [rbp+110h+var_58], rax
0x1801424fe  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x180142505  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18014250c  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180142513  mov     ecx, 4; ControlCode
0x180142518  call    cs:__imp_EventActivityIdControl
0x18014251f  nop     dword ptr [rax+rax+00h]
0x180142524  mov     eax, cs:dword_18039EB68
0x18014252a  lea     rcx, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x180142531  cmp     eax, 5
0x180142534  jbe     short loc_180142561
0x180142536  mov     dword ptr [rbp+110h+var_188], 240h
0x18014253d  mov     [rsp+210h+var_1A0], rcx
0x180142542  lea     rax, [rbp+110h+var_188]
0x180142546  mov     [rsp+210h+var_1E8], rax
0x18014254b  lea     rax, [rsp+210h+var_1A0]
0x180142550  mov     qword ptr [rsp+210h+var_1F0], rax
0x180142555  lea     rdx, word_180351912
0x18014255c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180142561  mov     [rbp+110h+instance.ft], rbx
0x180142565  xor     edx, edx; Val
0x180142567  lea     r8d, [rdx+60h]; Size
0x18014256b  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18014256f  call    memset_0
0x180142574  xorps   xmm0, xmm0
0x180142577  xor     eax, eax
0x180142579  movups  [rbp+110h+var_128], xmm0
0x18014257d  mov     [rbp+110h+var_118], rax
0x180142581  mov     [rbp+110h+var_190], rbx
0x180142585  lea     rcx, [rbp+110h+var_190]
0x180142589  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18014258e  mov     [rbp+110h+var_190], rbx
0x180142592  lea     rcx, [rbp+110h+var_148]; this
0x180142596  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18014259b  mov     r15d, ebx
0x18014259e  mov     rcx, rsi; context
0x1801425a1  call    WspIsRemoteRequest
0x1801425a6  mov     r12d, eax
0x1801425a9  test    eax, eax
0x1801425ab  jnz     short loc_1801425D1
0x1801425ad  lea     rcx, [rbp+110h+var_148]; this
0x1801425b1  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801425b6  cmp     [r14+48h], bl
0x1801425ba  jz      short loc_1801425CE
0x1801425bc  mov     rcx, [r14+40h]; unsigned __int16 *
0x1801425c0  call    WspIsRemoteInstance
0x1801425c5  test    al, al
0x1801425c7  lea     r15d, [r12+1]
0x1801425cc  jnz     short loc_1801425D1
0x1801425ce  mov     r15d, ebx
0x1801425d1  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x1801425d8  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x1801425dd  mov     ebx, eax
0x1801425df  test    eax, eax
0x1801425e1  jnz     loc_1801427A4
0x1801425e7  mov     dword ptr [rbp+110h+var_128], 10h
0x1801425ee  mov     rax, [r14+40h]
0x1801425f2  mov     qword ptr [rbp+110h+var_128+8], rax
0x1801425f6  mov     rbx, [rdi]
0x1801425f9  lea     rcx, [rbp+110h+var_190]
0x1801425fd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180142602  mov     [rsp+210h+var_1F0], 1; int
0x18014260a  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18014260e  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x180142612  mov     rdx, rsi; context
0x180142615  mov     rcx, rbx; this
0x180142618  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18014261d  mov     ebx, eax
0x18014261f  test    eax, eax
0x180142621  jz      short loc_18014266B
0x180142623  mov     eax, cs:dword_18039EB68
0x180142629  cmp     eax, 2
0x18014262c  jbe     loc_180142798
0x180142632  mov     dword ptr [rbp+110h+var_188], ebx
0x180142635  mov     dword ptr [rbp+110h+var_170], 25Fh
0x18014263c  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x180142643  mov     [rsp+210h+var_1A0], rax
0x180142648  lea     rax, [rbp+110h+var_188]
0x18014264c  mov     [rsp+210h+var_1E0], rax
0x180142651  lea     rax, [rbp+110h+var_170]
0x180142655  mov     [rsp+210h+var_1E8], rax
0x18014265a  lea     rax, [rsp+210h+var_1A0]
0x18014265f  lea     rdx, unk_180353BE0
0x180142666  jmp     loc_18014278E
0x18014266b  lea     r8, [rbp+110h+instance]; instance
0x18014266f  lea     rdx, SPACES_VirtualDisk_SetSecurityDescriptor_rtti; methodDecl
0x180142676  mov     rcx, rsi; context
0x180142679  call    MI_Context_ConstructParameters
0x18014267e  mov     ebx, eax
0x180142680  test    eax, eax
0x180142682  jz      short loc_1801426CC
0x180142684  mov     eax, cs:dword_18039EB68
0x18014268a  cmp     eax, 2
0x18014268d  jbe     loc_180142798
0x180142693  mov     dword ptr [rbp+110h+var_168], ebx
0x180142696  mov     dword ptr [rbp+110h+var_160], 267h
0x18014269d  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x1801426a4  mov     [rsp+210h+var_1A0], rax
0x1801426a9  lea     rax, [rbp+110h+var_168]
0x1801426ad  mov     [rsp+210h+var_1E0], rax
0x1801426b2  lea     rax, [rbp+110h+var_160]
0x1801426b6  mov     [rsp+210h+var_1E8], rax
0x1801426bb  lea     rax, [rsp+210h+var_1A0]
0x1801426c0  lea     rdx, byte_180352667
0x1801426c7  jmp     loc_18014278E
0x1801426cc  mov     rcx, [rbp+110h+var_190]
0x1801426d0  mov     rax, [rcx]
0x1801426d3  lea     rdx, [rbp+110h+instance]
0x1801426d7  mov     qword ptr [rsp+210h+var_1F0], rdx
0x1801426dc  mov     r9, r13
0x1801426df  mov     r8, rsi
0x1801426e2  mov     edx, 100005h
0x1801426e7  mov     rax, [rax+30h]
0x1801426eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801426f0  mov     ebx, eax
0x1801426f2  test    eax, eax
0x1801426f4  jz      short loc_18014273B
0x1801426f6  mov     eax, cs:dword_18039EB68
0x1801426fc  cmp     eax, 2
0x1801426ff  jbe     loc_180142798
0x180142705  mov     dword ptr [rbp+110h+var_158], ebx
0x180142708  mov     dword ptr [rbp+110h+var_180], 272h
0x18014270f  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x180142716  mov     [rsp+210h+var_1A0], rax
0x18014271b  lea     rax, [rbp+110h+var_158]
0x18014271f  mov     [rsp+210h+var_1E0], rax
0x180142724  lea     rax, [rbp+110h+var_180]
0x180142728  mov     [rsp+210h+var_1E8], rax
0x18014272d  lea     rax, [rsp+210h+var_1A0]
0x180142732  lea     rdx, byte_180352D5B
0x180142739  jmp     short loc_18014278E
0x18014273b  lea     rdx, [rbp+110h+instance]
0x18014273f  mov     rcx, rsi; self
0x180142742  call    MI_Instance_Destruct
0x180142747  mov     ebx, eax
0x180142749  test    eax, eax
0x18014274b  jz      short loc_180142798
0x18014274d  mov     eax, cs:dword_18039EB68
0x180142753  cmp     eax, 2
0x180142756  jbe     short loc_180142798
0x180142758  mov     [rsp+210h+var_198], ebx
0x18014275c  mov     dword ptr [rsp+210h+var_1A0], 27Ah
0x180142764  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x18014276b  mov     [rbp+110h+var_180], rax
0x18014276f  lea     rax, [rsp+210h+var_198]
0x180142774  mov     [rsp+210h+var_1E0], rax
0x180142779  lea     rax, [rsp+210h+var_1A0]
0x18014277e  mov     [rsp+210h+var_1E8], rax
0x180142783  lea     rax, [rbp+110h+var_180]
0x180142787  lea     rdx, byte_1803522B5
0x18014278e  mov     qword ptr [rsp+210h+var_1F0], rax
0x180142793  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180142798  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18014279f  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801427a4  xor     r13d, r13d
0x1801427a7  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x1801427ac  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x1801427b0  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x1801427b4  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x1801427b8  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x1801427bc  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x1801427c0  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x1801427c5  test    r12d, r12d
0x1801427c8  jnz     loc_1801428D0
0x1801427ce  lea     rcx, [rbp+110h+var_148]; this
0x1801427d2  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801427d7  mov     eax, cs:dword_18039EB68
0x1801427dd  cmp     eax, 5
0x1801427e0  jbe     loc_1801428D0
0x1801427e6  mov     rdx, 400000000000h
0x1801427f0  lea     rcx, dword_18039EB68
0x1801427f7  call    _tlgKeywordOn
0x1801427fc  test    al, al
0x1801427fe  jz      loc_1801428D0
0x180142804  mov     [rbp+110h+var_178], r13
0x180142808  mov     [rbp+110h+var_150], r13
0x18014280c  mov     [rbp+110h+var_158], r13
0x180142810  mov     rax, [rbp+110h+var_140]
0x180142814  sub     rax, [rbp+110h+var_148]
0x180142818  imul    rax, 3E8h
0x18014281f  xor     edx, edx
0x180142821  div     [rbp+110h+var_138]
0x180142825  mov     [rbp+110h+var_160], rax
0x180142829  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18014282d  mov     al, [rbp+110h+var_A0.exists]
0x180142830  neg     al
0x180142832  sbb     ecx, ecx
0x180142834  and     ecx, [rbp+110h+var_A0.value]
0x180142837  mov     [rsp+210h+var_198], ecx
0x18014283b  mov     dword ptr [rbp+110h+var_180], r15d
0x18014283f  cmp     [r14+48h], r13b
0x180142843  jz      short loc_18014284B
0x180142845  mov     rax, [r14+40h]
0x180142849  jmp     short loc_18014284E
0x18014284b  mov     rax, r13
0x18014284e  mov     [rbp+110h+var_168], rax
0x180142852  lea     rax, aSetsecuritydes_0; "SetSecurityDescriptor"
0x180142859  mov     [rbp+110h+var_170], rax
0x18014285d  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x180142864  mov     [rbp+110h+var_188], rax
0x180142868  lea     rax, [rbp+110h+var_178]
0x18014286c  mov     [rsp+210h+var_1A8], rax
0x180142871  lea     rax, [rbp+110h+var_150]
0x180142875  mov     [rsp+210h+var_1B0], rax
0x18014287a  lea     rax, [rbp+110h+var_158]
0x18014287e  mov     [rsp+210h+var_1B8], rax
0x180142883  lea     rax, [rbp+110h+var_160]
0x180142887  mov     [rsp+210h+var_1C0], rax
0x18014288c  lea     rax, [rsp+210h+var_1A0]
0x180142891  mov     [rsp+210h+var_1C8], rax
0x180142896  lea     rax, [rsp+210h+var_198]
0x18014289b  mov     [rsp+210h+var_1D0], rax
0x1801428a0  lea     rax, [rbp+110h+var_180]
0x1801428a4  mov     [rsp+210h+var_1D8], rax
0x1801428a9  lea     rax, [rbp+110h+var_168]
0x1801428ad  mov     [rsp+210h+var_1E0], rax
0x1801428b2  lea     rax, [rbp+110h+var_170]
0x1801428b6  mov     [rsp+210h+var_1E8], rax
0x1801428bb  lea     rax, [rbp+110h+var_188]
0x1801428bf  mov     qword ptr [rsp+210h+var_1F0], rax
0x1801428c4  lea     rdx, dword_1803538D4
0x1801428cb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801428d0  lea     rcx, [rbp+110h+instance]; self
0x1801428d4  call    MI_Instance_Destruct
0x1801428d9  mov     eax, cs:dword_18039EB68
0x1801428df  cmp     eax, 5
0x1801428e2  jbe     short loc_180142916
0x1801428e4  mov     dword ptr [rsp+210h+var_1A0], 29Bh
0x1801428ec  lea     rax, aSpacesVirtuald_27; "SPACES_VirtualDisk_Invoke_SetSecurityDe"...
0x1801428f3  mov     [rbp+110h+var_178], rax
0x1801428f7  lea     rax, [rsp+210h+var_1A0]
0x1801428fc  mov     [rsp+210h+var_1E8], rax
0x180142901  lea     rax, [rbp+110h+var_178]
0x180142905  mov     qword ptr [rsp+210h+var_1F0], rax
0x18014290a  lea     rdx, dword_1803523BC
0x180142911  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180142916  mov     edx, ebx; result
0x180142918  mov     rcx, rsi; context
0x18014291b  call    MI_Context_PostResult_0
0x180142920  lea     rcx, [rbp+110h+var_148]; this
0x180142924  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180142929  lea     rcx, [rbp+110h+var_190]
0x18014292d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180142932  lea     rdx, [rbp+110h+var_50]; ActivityId
0x180142939  mov     ecx, 4; ControlCode
0x18014293e  call    cs:__imp_EventActivityIdControl
0x180142945  nop     dword ptr [rax+rax+00h]
0x18014294a  mov     rcx, [rbp+110h+var_40]
0x180142951  xor     rcx, rsp; StackCookie
0x180142954  call    __security_check_cookie
0x180142959  mov     rbx, [rsp+210h+arg_10]
0x180142961  add     rsp, 1E0h
0x180142968  pop     r15
0x18014296a  pop     r14
0x18014296c  pop     r13
0x18014296e  pop     r12
  ... truncated ...
```
