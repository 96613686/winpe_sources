# SPACES_VirtualDisk_Invoke_GetSecurityDescriptor

- ea: `0x18013f1b0`
- end: `0x18013f6f5`
- name: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
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
- `0x18013f1b0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f22d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f6be`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f22d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f298`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f6be`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013f256`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013f256`

## string_xrefs

- `0x18013f2aa`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013f3bc`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013f41d`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013f48f`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013f4e4`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013f66c`: `SPACES_VirtualDisk_Invoke_GetSecurityDescriptor`
- `0x18013f5d2`: `GetSecurityDescriptor`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_GetSecurityDescriptor(
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
    LODWORD(v39) = 469;
    v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_GetSecurityDescriptor",
      (unsigned int)byte_180351C31,
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
        LODWORD(v42) = 500;
        v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180351BF8,
          v18,
          v19,
          (__int64)&v36,
          (__int64)&v42,
          (__int64)&v39);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_GetSecurityDescriptor_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v43) = v15;
          LODWORD(v44) = 508;
          v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)byte_180352601,
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
                1048580,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v45) = v15;
            LODWORD(v40) = 519;
            v36 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&dword_180352F74,
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
            LODWORD(v36) = 527;
            v40 = "SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&byte_180351E3F,
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
        v39 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v52.exists != 0 ? v52.value : 0,
          (unsigned int)&byte_180352B6F,
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
    LODWORD(v36) = 560;
    v41 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_GetSecurityDescriptor";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v32,
      (unsigned int)qword_1803526A0,
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
0x18013f1b0  mov     [rsp-8+arg_10], rbx
0x18013f1b5  push    rbp
0x18013f1b6  push    rsi
0x18013f1b7  push    rdi
0x18013f1b8  push    r12
0x18013f1ba  push    r13
0x18013f1bc  push    r14
0x18013f1be  push    r15
0x18013f1c0  lea     rbp, [rsp-0E0h]
0x18013f1c8  sub     rsp, 1E0h
0x18013f1cf  mov     rax, cs:__security_cookie
0x18013f1d6  xor     rax, rsp
0x18013f1d9  mov     [rbp+110h+var_40], rax
0x18013f1e0  mov     [rbp+110h+var_178], r9
0x18013f1e4  mov     rsi, rdx
0x18013f1e7  mov     rdi, rcx
0x18013f1ea  mov     rax, [rbp+110h+arg_20]
0x18013f1f1  mov     [rbp+110h+var_150], rax
0x18013f1f5  mov     r14, [rbp+110h+arg_28]
0x18013f1fc  mov     r13, [rbp+110h+arg_30]
0x18013f203  xorps   xmm0, xmm0
0x18013f206  xor     eax, eax
0x18013f208  movups  xmmword ptr [rbp+110h+value], xmm0
0x18013f20c  movups  xmmword ptr [rbp+110h+value+10h], xmm0
0x18013f210  mov     qword ptr [rbp+110h+value+20h], rax
0x18013f214  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013f21b  movdqu  xmmword ptr [rbp+110h+ActivityId.Data1], xmm0
0x18013f223  lea     rdx, [rbp+110h+ActivityId]; ActivityId
0x18013f22a  lea     ecx, [rax+1]; ControlCode
0x18013f22d  call    cs:__imp_EventActivityIdControl
0x18013f234  nop     dword ptr [rax+rax+00h]
0x18013f239  lea     r9, [rbp+110h+value]; value
0x18013f23d  mov     rcx, rsi; context
0x18013f240  call    MI_Context_GetCustomOption_1
0x18013f245  xor     ebx, ebx
0x18013f247  test    eax, eax
0x18013f249  jnz     short loc_18013F262
0x18013f24b  lea     rdx, [rbp+110h+ActivityId]; pclsid
0x18013f252  mov     rcx, qword ptr [rbp+110h+value]; lpsz
0x18013f256  call    cs:__imp_CLSIDFromString
0x18013f25d  nop     dword ptr [rax+rax+00h]
0x18013f262  mov     rcx, qword ptr [rbp+110h+ActivityId.Data1]
0x18013f269  mov     [rbp+110h+var_60], rcx
0x18013f270  mov     rax, qword ptr [rbp+110h+ActivityId.Data4]
0x18013f277  mov     [rbp+110h+var_58], rax
0x18013f27e  mov     qword ptr [rbp+110h+var_50.Data1], rcx
0x18013f285  mov     qword ptr [rbp+110h+var_50.Data4], rax
0x18013f28c  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18013f293  mov     ecx, 4; ControlCode
0x18013f298  call    cs:__imp_EventActivityIdControl
0x18013f29f  nop     dword ptr [rax+rax+00h]
0x18013f2a4  mov     eax, cs:dword_18039EB68
0x18013f2aa  lea     rcx, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013f2b1  cmp     eax, 5
0x18013f2b4  jbe     short loc_18013F2E1
0x18013f2b6  mov     dword ptr [rbp+110h+var_188], 1D5h
0x18013f2bd  mov     [rsp+210h+var_1A0], rcx
0x18013f2c2  lea     rax, [rbp+110h+var_188]
0x18013f2c6  mov     [rsp+210h+var_1E8], rax
0x18013f2cb  lea     rax, [rsp+210h+var_1A0]
0x18013f2d0  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013f2d5  lea     rdx, byte_180351C31
0x18013f2dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013f2e1  mov     [rbp+110h+instance.ft], rbx
0x18013f2e5  xor     edx, edx; Val
0x18013f2e7  lea     r8d, [rdx+60h]; Size
0x18013f2eb  lea     rcx, [rbp+110h+instance.classDecl]; void *
0x18013f2ef  call    memset_0
0x18013f2f4  xorps   xmm0, xmm0
0x18013f2f7  xor     eax, eax
0x18013f2f9  movups  [rbp+110h+var_128], xmm0
0x18013f2fd  mov     [rbp+110h+var_118], rax
0x18013f301  mov     [rbp+110h+var_190], rbx
0x18013f305  lea     rcx, [rbp+110h+var_190]
0x18013f309  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013f30e  mov     [rbp+110h+var_190], rbx
0x18013f312  lea     rcx, [rbp+110h+var_148]; this
0x18013f316  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013f31b  mov     r15d, ebx
0x18013f31e  mov     rcx, rsi; context
0x18013f321  call    WspIsRemoteRequest
0x18013f326  mov     r12d, eax
0x18013f329  test    eax, eax
0x18013f32b  jnz     short loc_18013F351
0x18013f32d  lea     rcx, [rbp+110h+var_148]; this
0x18013f331  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013f336  cmp     [r14+48h], bl
0x18013f33a  jz      short loc_18013F34E
0x18013f33c  mov     rcx, [r14+40h]; unsigned __int16 *
0x18013f340  call    WspIsRemoteInstance
0x18013f345  test    al, al
0x18013f347  lea     r15d, [r12+1]
0x18013f34c  jnz     short loc_18013F351
0x18013f34e  mov     r15d, ebx
0x18013f351  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013f358  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013f35d  mov     ebx, eax
0x18013f35f  test    eax, eax
0x18013f361  jnz     loc_18013F524
0x18013f367  mov     dword ptr [rbp+110h+var_128], 10h
0x18013f36e  mov     rax, [r14+40h]
0x18013f372  mov     qword ptr [rbp+110h+var_128+8], rax
0x18013f376  mov     rbx, [rdi]
0x18013f379  lea     rcx, [rbp+110h+var_190]
0x18013f37d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013f382  mov     [rsp+210h+var_1F0], 1; int
0x18013f38a  lea     r9, [rbp+110h+var_190]; struct ISpWmiObject **
0x18013f38e  lea     r8, [rbp+110h+var_128]; struct _SP_OBJECT_ID *
0x18013f392  mov     rdx, rsi; context
0x18013f395  mov     rcx, rbx; this
0x18013f398  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013f39d  mov     ebx, eax
0x18013f39f  test    eax, eax
0x18013f3a1  jz      short loc_18013F3EB
0x18013f3a3  mov     eax, cs:dword_18039EB68
0x18013f3a9  cmp     eax, 2
0x18013f3ac  jbe     loc_18013F518
0x18013f3b2  mov     dword ptr [rbp+110h+var_188], ebx
0x18013f3b5  mov     dword ptr [rbp+110h+var_170], 1F4h
0x18013f3bc  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013f3c3  mov     [rsp+210h+var_1A0], rax
0x18013f3c8  lea     rax, [rbp+110h+var_188]
0x18013f3cc  mov     [rsp+210h+var_1E0], rax
0x18013f3d1  lea     rax, [rbp+110h+var_170]
0x18013f3d5  mov     [rsp+210h+var_1E8], rax
0x18013f3da  lea     rax, [rsp+210h+var_1A0]
0x18013f3df  lea     rdx, unk_180351BF8
0x18013f3e6  jmp     loc_18013F50E
0x18013f3eb  lea     r8, [rbp+110h+instance]; instance
0x18013f3ef  lea     rdx, SPACES_VirtualDisk_GetSecurityDescriptor_rtti; methodDecl
0x18013f3f6  mov     rcx, rsi; context
0x18013f3f9  call    MI_Context_ConstructParameters
0x18013f3fe  mov     ebx, eax
0x18013f400  test    eax, eax
0x18013f402  jz      short loc_18013F44C
0x18013f404  mov     eax, cs:dword_18039EB68
0x18013f40a  cmp     eax, 2
0x18013f40d  jbe     loc_18013F518
0x18013f413  mov     dword ptr [rbp+110h+var_168], ebx
0x18013f416  mov     dword ptr [rbp+110h+var_160], 1FCh
0x18013f41d  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013f424  mov     [rsp+210h+var_1A0], rax
0x18013f429  lea     rax, [rbp+110h+var_168]
0x18013f42d  mov     [rsp+210h+var_1E0], rax
0x18013f432  lea     rax, [rbp+110h+var_160]
0x18013f436  mov     [rsp+210h+var_1E8], rax
0x18013f43b  lea     rax, [rsp+210h+var_1A0]
0x18013f440  lea     rdx, byte_180352601
0x18013f447  jmp     loc_18013F50E
0x18013f44c  mov     rcx, [rbp+110h+var_190]
0x18013f450  mov     rax, [rcx]
0x18013f453  lea     rdx, [rbp+110h+instance]
0x18013f457  mov     qword ptr [rsp+210h+var_1F0], rdx
0x18013f45c  mov     r9, r13
0x18013f45f  mov     r8, rsi
0x18013f462  mov     edx, 100004h
0x18013f467  mov     rax, [rax+30h]
0x18013f46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f470  mov     ebx, eax
0x18013f472  test    eax, eax
0x18013f474  jz      short loc_18013F4BB
0x18013f476  mov     eax, cs:dword_18039EB68
0x18013f47c  cmp     eax, 2
0x18013f47f  jbe     loc_18013F518
0x18013f485  mov     dword ptr [rbp+110h+var_158], ebx
0x18013f488  mov     dword ptr [rbp+110h+var_180], 207h
0x18013f48f  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013f496  mov     [rsp+210h+var_1A0], rax
0x18013f49b  lea     rax, [rbp+110h+var_158]
0x18013f49f  mov     [rsp+210h+var_1E0], rax
0x18013f4a4  lea     rax, [rbp+110h+var_180]
0x18013f4a8  mov     [rsp+210h+var_1E8], rax
0x18013f4ad  lea     rax, [rsp+210h+var_1A0]
0x18013f4b2  lea     rdx, dword_180352F74
0x18013f4b9  jmp     short loc_18013F50E
0x18013f4bb  lea     rdx, [rbp+110h+instance]
0x18013f4bf  mov     rcx, rsi; self
0x18013f4c2  call    MI_Instance_Destruct
0x18013f4c7  mov     ebx, eax
0x18013f4c9  test    eax, eax
0x18013f4cb  jz      short loc_18013F518
0x18013f4cd  mov     eax, cs:dword_18039EB68
0x18013f4d3  cmp     eax, 2
0x18013f4d6  jbe     short loc_18013F518
0x18013f4d8  mov     [rsp+210h+var_198], ebx
0x18013f4dc  mov     dword ptr [rsp+210h+var_1A0], 20Fh
0x18013f4e4  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013f4eb  mov     [rbp+110h+var_180], rax
0x18013f4ef  lea     rax, [rsp+210h+var_198]
0x18013f4f4  mov     [rsp+210h+var_1E0], rax
0x18013f4f9  lea     rax, [rsp+210h+var_1A0]
0x18013f4fe  mov     [rsp+210h+var_1E8], rax
0x18013f503  lea     rax, [rbp+110h+var_180]
0x18013f507  lea     rdx, byte_180351E3F
0x18013f50e  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013f513  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013f518  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013f51f  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013f524  xor     r13d, r13d
0x18013f527  mov     [rsp+210h+var_1E8], r13; unsigned __int16 *
0x18013f52c  mov     [rsp+210h+var_1F0], ebx; enum _MI_Result
0x18013f530  lea     r9, [rbp+110h+var_A0]; struct _MI_ConstUint32Field *
0x18013f534  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18013f538  mov     rdx, [rbp+110h+var_150]; unsigned __int16 *
0x18013f53c  mov     rcx, [rbp+110h+var_178]; unsigned __int16 *
0x18013f540  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013f545  test    r12d, r12d
0x18013f548  jnz     loc_18013F650
0x18013f54e  lea     rcx, [rbp+110h+var_148]; this
0x18013f552  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013f557  mov     eax, cs:dword_18039EB68
0x18013f55d  cmp     eax, 5
0x18013f560  jbe     loc_18013F650
0x18013f566  mov     rdx, 400000000000h
0x18013f570  lea     rcx, dword_18039EB68
0x18013f577  call    _tlgKeywordOn
0x18013f57c  test    al, al
0x18013f57e  jz      loc_18013F650
0x18013f584  mov     [rbp+110h+var_178], r13
0x18013f588  mov     [rbp+110h+var_150], r13
0x18013f58c  mov     [rbp+110h+var_158], r13
0x18013f590  mov     rax, [rbp+110h+var_140]
0x18013f594  sub     rax, [rbp+110h+var_148]
0x18013f598  imul    rax, 3E8h
0x18013f59f  xor     edx, edx
0x18013f5a1  div     [rbp+110h+var_138]
0x18013f5a5  mov     [rbp+110h+var_160], rax
0x18013f5a9  mov     dword ptr [rsp+210h+var_1A0], ebx
0x18013f5ad  mov     al, [rbp+110h+var_A0.exists]
0x18013f5b0  neg     al
0x18013f5b2  sbb     ecx, ecx
0x18013f5b4  and     ecx, [rbp+110h+var_A0.value]
0x18013f5b7  mov     [rsp+210h+var_198], ecx
0x18013f5bb  mov     dword ptr [rbp+110h+var_180], r15d
0x18013f5bf  cmp     [r14+48h], r13b
0x18013f5c3  jz      short loc_18013F5CB
0x18013f5c5  mov     rax, [r14+40h]
0x18013f5c9  jmp     short loc_18013F5CE
0x18013f5cb  mov     rax, r13
0x18013f5ce  mov     [rbp+110h+var_168], rax
0x18013f5d2  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptor"
0x18013f5d9  mov     [rbp+110h+var_170], rax
0x18013f5dd  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013f5e4  mov     [rbp+110h+var_188], rax
0x18013f5e8  lea     rax, [rbp+110h+var_178]
0x18013f5ec  mov     [rsp+210h+var_1A8], rax
0x18013f5f1  lea     rax, [rbp+110h+var_150]
0x18013f5f5  mov     [rsp+210h+var_1B0], rax
0x18013f5fa  lea     rax, [rbp+110h+var_158]
0x18013f5fe  mov     [rsp+210h+var_1B8], rax
0x18013f603  lea     rax, [rbp+110h+var_160]
0x18013f607  mov     [rsp+210h+var_1C0], rax
0x18013f60c  lea     rax, [rsp+210h+var_1A0]
0x18013f611  mov     [rsp+210h+var_1C8], rax
0x18013f616  lea     rax, [rsp+210h+var_198]
0x18013f61b  mov     [rsp+210h+var_1D0], rax
0x18013f620  lea     rax, [rbp+110h+var_180]
0x18013f624  mov     [rsp+210h+var_1D8], rax
0x18013f629  lea     rax, [rbp+110h+var_168]
0x18013f62d  mov     [rsp+210h+var_1E0], rax
0x18013f632  lea     rax, [rbp+110h+var_170]
0x18013f636  mov     [rsp+210h+var_1E8], rax
0x18013f63b  lea     rax, [rbp+110h+var_188]
0x18013f63f  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013f644  lea     rdx, byte_180352B6F
0x18013f64b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18013f650  lea     rcx, [rbp+110h+instance]; self
0x18013f654  call    MI_Instance_Destruct
0x18013f659  mov     eax, cs:dword_18039EB68
0x18013f65f  cmp     eax, 5
0x18013f662  jbe     short loc_18013F696
0x18013f664  mov     dword ptr [rsp+210h+var_1A0], 230h
0x18013f66c  lea     rax, aSpacesVirtuald_17; "SPACES_VirtualDisk_Invoke_GetSecurityDe"...
0x18013f673  mov     [rbp+110h+var_178], rax
0x18013f677  lea     rax, [rsp+210h+var_1A0]
0x18013f67c  mov     [rsp+210h+var_1E8], rax
0x18013f681  lea     rax, [rbp+110h+var_178]
0x18013f685  mov     qword ptr [rsp+210h+var_1F0], rax
0x18013f68a  lea     rdx, qword_1803526A0
0x18013f691  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013f696  mov     edx, ebx; result
0x18013f698  mov     rcx, rsi; context
0x18013f69b  call    MI_Context_PostResult_0
0x18013f6a0  lea     rcx, [rbp+110h+var_148]; this
0x18013f6a4  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x18013f6a9  lea     rcx, [rbp+110h+var_190]
0x18013f6ad  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013f6b2  lea     rdx, [rbp+110h+var_50]; ActivityId
0x18013f6b9  mov     ecx, 4; ControlCode
0x18013f6be  call    cs:__imp_EventActivityIdControl
0x18013f6c5  nop     dword ptr [rax+rax+00h]
0x18013f6ca  mov     rcx, [rbp+110h+var_40]
0x18013f6d1  xor     rcx, rsp; StackCookie
0x18013f6d4  call    __security_check_cookie
0x18013f6d9  mov     rbx, [rsp+210h+arg_10]
0x18013f6e1  add     rsp, 1E0h
0x18013f6e8  pop     r15
0x18013f6ea  pop     r14
0x18013f6ec  pop     r13
0x18013f6ee  pop     r12
  ... truncated ...
```
