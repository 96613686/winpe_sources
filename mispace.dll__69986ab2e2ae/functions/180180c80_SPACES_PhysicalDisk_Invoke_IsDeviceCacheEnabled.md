# SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled

- ea: `0x180180c80`
- end: `0x180181227`
- name: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- size: `1447`
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
- `0x1800226ac`
- `0x180023e18`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180180c80`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180180cfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180180d68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801811f0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180180cfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180180d68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801811f0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180180d26`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180180d26`

## string_xrefs

- `0x180180d7a`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x180180e8f`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x180180eee`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x180180f4f`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x180180fc1`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x180181016`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x18018119e`: `SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled`
- `0x180181104`: `IsDeviceCacheEnabled`

## pseudocode

```c
ULONG __fastcall SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled(
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
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  int v33; // r9d
  const MI_Char *v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v41; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v42; // [rsp+80h] [rbp-80h] BYREF
  const char *v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  const char *v47; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v48; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v51; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v52[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h]
  MI_Value value; // [rsp+108h] [rbp+8h] BYREF
  MI_Instance instance; // [rsp+130h] [rbp+30h] BYREF
  struct _MI_ConstUint32Field v57; // [rsp+170h] [rbp+70h] BYREF
  GUID ActivityId; // [rsp+190h] [rbp+90h] BYREF
  GUID v59; // [rsp+1A0h] [rbp+A0h]
  GUID v60; // [rsp+1B0h] [rbp+B0h] BYREF

  v44 = a4;
  v51 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v59 = ActivityId;
  v60 = ActivityId;
  EventActivityIdControl(4u, &v60);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v40 = 1024;
    v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled",
      (unsigned int)&dword_180369544,
      v11,
      v12,
      (__int64)&v39,
      (__int64)&v40);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x58u);
  v53 = 0;
  v54 = 0;
  v42 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  v42 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v52);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v52);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v53) = 4;
    *((_QWORD *)&v53 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v53, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v40 = v15;
        v45 = 1056;
        v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180369478,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v40);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_PhysicalDisk_IsDeviceCacheEnabled_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v48) = v15;
          LODWORD(v49) = 1074;
          v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&dword_18036975C,
            v24,
            v25,
            (__int64)&v39,
            (__int64)&v49,
            (__int64)&v48);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v42 + 48LL))(
                v42,
                262152,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            LODWORD(v50) = v15;
            LODWORD(v43) = 1085;
            v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&dword_180369F54,
              v27,
              v28,
              (__int64)&v39,
              (__int64)&v43,
              (__int64)&v50);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v41 = v15;
            LODWORD(v39) = 1093;
            v43 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)byte_18036A3F9,
              v30,
              v31,
              (__int64)&v43,
              (__int64)&v39,
              (__int64)&v41);
          }
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v46) = 7;
        LODWORD(v47) = 1066;
        v39 = "SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_180369611,
          v21,
          v22,
          (__int64)&v39,
          (__int64)&v47,
          (__int64)&v46);
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v44, v51, a6 + 4, &v57, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v52);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        v44 = 0;
        v51 = 0;
        v50 = 0;
        v49 = (unsigned __int64)(1000LL * (v52[1] - v52[0])) / v52[2];
        LODWORD(v39) = v15;
        v41 = v57.exists != 0 ? v57.value : 0;
        LODWORD(v43) = v13;
        if ( a6[4].exists )
          v34 = a6[4].value;
        else
          v34 = 0;
        v48 = v34;
        v47 = "IsDeviceCacheEnabled";
        v46 = "PhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v57.exists != 0 ? v57.value : 0,
          (unsigned int)&byte_18036999F,
          v32,
          v33,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v41,
          (__int64)&v39,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v44);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v39) = 1126;
    v44 = (unsigned __int16 *)"SPACES_PhysicalDisk_Invoke_IsDeviceCacheEnabled";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)byte_18036A183,
      v36,
      v37,
      (__int64)&v44,
      (__int64)&v39);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v52);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  return EventActivityIdControl(4u, &v60);
}

```

## disassembly

```asm
0x180180c80  mov     [rsp-8+arg_10], rbx
0x180180c85  push    rbp
0x180180c86  push    rsi
0x180180c87  push    rdi
0x180180c88  push    r12
0x180180c8a  push    r13
0x180180c8c  push    r14
0x180180c8e  push    r15
0x180180c90  lea     rbp, [rsp-0D0h]
0x180180c98  sub     rsp, 1D0h
0x180180c9f  mov     rax, cs:__security_cookie
0x180180ca6  xor     rax, rsp
0x180180ca9  mov     [rbp+100h+var_40], rax
0x180180cb0  mov     [rbp+100h+var_170], r9
0x180180cb4  mov     rsi, rdx
0x180180cb7  mov     rdi, rcx
0x180180cba  mov     rax, [rbp+100h+arg_20]
0x180180cc1  mov     [rbp+100h+var_138], rax
0x180180cc5  mov     r14, [rbp+100h+arg_28]
0x180180ccc  mov     r13, [rbp+100h+arg_30]
0x180180cd3  xorps   xmm0, xmm0
0x180180cd6  xor     eax, eax
0x180180cd8  movups  xmmword ptr [rbp+100h+value], xmm0
0x180180cdc  movups  xmmword ptr [rbp+100h+value+10h], xmm0
0x180180ce0  mov     qword ptr [rbp+100h+value+20h], rax
0x180180ce4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180180ceb  movdqu  xmmword ptr [rbp+100h+ActivityId.Data1], xmm0
0x180180cf3  lea     rdx, [rbp+100h+ActivityId]; ActivityId
0x180180cfa  lea     ecx, [rax+1]; ControlCode
0x180180cfd  call    cs:__imp_EventActivityIdControl
0x180180d04  nop     dword ptr [rax+rax+00h]
0x180180d09  lea     r9, [rbp+100h+value]; value
0x180180d0d  mov     rcx, rsi; context
0x180180d10  call    MI_Context_GetCustomOption_1
0x180180d15  xor     ebx, ebx
0x180180d17  test    eax, eax
0x180180d19  jnz     short loc_180180D32
0x180180d1b  lea     rdx, [rbp+100h+ActivityId]; pclsid
0x180180d22  mov     rcx, qword ptr [rbp+100h+value]; lpsz
0x180180d26  call    cs:__imp_CLSIDFromString
0x180180d2d  nop     dword ptr [rax+rax+00h]
0x180180d32  mov     rcx, qword ptr [rbp+100h+ActivityId.Data1]
0x180180d39  mov     [rbp+100h+var_60], rcx
0x180180d40  mov     rax, qword ptr [rbp+100h+ActivityId.Data4]
0x180180d47  mov     [rbp+100h+var_58], rax
0x180180d4e  mov     qword ptr [rbp+100h+var_50.Data1], rcx
0x180180d55  mov     qword ptr [rbp+100h+var_50.Data4], rax
0x180180d5c  lea     rdx, [rbp+100h+var_50]; ActivityId
0x180180d63  mov     ecx, 4; ControlCode
0x180180d68  call    cs:__imp_EventActivityIdControl
0x180180d6f  nop     dword ptr [rax+rax+00h]
0x180180d74  mov     eax, cs:dword_18039EB68
0x180180d7a  lea     rcx, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x180180d81  cmp     eax, 5
0x180180d84  jbe     short loc_180180DB3
0x180180d86  mov     [rsp+200h+var_188], 400h
0x180180d8e  mov     [rsp+200h+var_190], rcx
0x180180d93  lea     rax, [rsp+200h+var_188]
0x180180d98  mov     [rsp+200h+var_1D8], rax
0x180180d9d  lea     rax, [rsp+200h+var_190]
0x180180da2  mov     qword ptr [rsp+200h+var_1E0], rax
0x180180da7  lea     rdx, dword_180369544
0x180180dae  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180180db3  mov     [rbp+100h+instance.ft], rbx
0x180180db7  xor     edx, edx; Val
0x180180db9  lea     r8d, [rdx+58h]; Size
0x180180dbd  lea     rcx, [rbp+100h+instance.classDecl]; void *
0x180180dc1  call    memset_0
0x180180dc6  xorps   xmm0, xmm0
0x180180dc9  xor     eax, eax
0x180180dcb  movups  [rbp+100h+var_110], xmm0
0x180180dcf  mov     [rbp+100h+var_100], rax
0x180180dd3  mov     [rbp+100h+var_180], rbx
0x180180dd7  lea     rcx, [rbp+100h+var_180]
0x180180ddb  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180180de0  mov     [rbp+100h+var_180], rbx
0x180180de4  mov     r15d, ebx
0x180180de7  lea     rcx, [rbp+100h+var_130]; this
0x180180deb  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180180df0  mov     rcx, rsi; context
0x180180df3  call    WspIsRemoteRequest
0x180180df8  mov     r12d, eax
0x180180dfb  test    eax, eax
0x180180dfd  jnz     short loc_180180E23
0x180180dff  lea     rcx, [rbp+100h+var_130]; this
0x180180e03  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180180e08  cmp     [r14+48h], bl
0x180180e0c  jz      short loc_180180E20
0x180180e0e  mov     rcx, [r14+40h]; unsigned __int16 *
0x180180e12  call    WspIsRemoteInstance
0x180180e17  test    al, al
0x180180e19  lea     r15d, [r12+1]
0x180180e1e  jnz     short loc_180180E23
0x180180e20  mov     r15d, ebx
0x180180e23  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180180e2a  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180180e2f  mov     ebx, eax
0x180180e31  test    eax, eax
0x180180e33  jnz     loc_180181056
0x180180e39  mov     dword ptr [rbp+100h+var_110], 4
0x180180e40  mov     rax, [r14+40h]
0x180180e44  mov     qword ptr [rbp+100h+var_110+8], rax
0x180180e48  mov     rbx, [rdi]
0x180180e4b  lea     rcx, [rbp+100h+var_180]
0x180180e4f  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180180e54  mov     [rsp+200h+var_1E0], 1; int
0x180180e5c  lea     r9, [rbp+100h+var_180]; struct ISpWmiObject **
0x180180e60  lea     r8, [rbp+100h+var_110]; struct _SP_OBJECT_ID *
0x180180e64  mov     rdx, rsi; context
0x180180e67  mov     rcx, rbx; this
0x180180e6a  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180180e6f  mov     ebx, eax
0x180180e71  test    eax, eax
0x180180e73  jz      short loc_180180EBF
0x180180e75  mov     eax, cs:dword_18039EB68
0x180180e7b  cmp     eax, 2
0x180180e7e  jbe     loc_18018104A
0x180180e84  mov     [rsp+200h+var_188], ebx
0x180180e88  mov     [rbp+100h+var_168], 420h
0x180180e8f  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x180180e96  mov     [rsp+200h+var_190], rax
0x180180e9b  lea     rax, [rsp+200h+var_188]
0x180180ea0  mov     [rsp+200h+var_1D0], rax
0x180180ea5  lea     rax, [rbp+100h+var_168]
0x180180ea9  mov     [rsp+200h+var_1D8], rax
0x180180eae  lea     rax, [rsp+200h+var_190]
0x180180eb3  lea     rdx, unk_180369478
0x180180eba  jmp     loc_180181040
0x180180ebf  mov     r8, [r14+40h]
0x180180ec3  mov     rdx, rsi
0x180180ec6  mov     rcx, [rdi]
0x180180ec9  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180180ece  test    eax, eax
0x180180ed0  jnz     short loc_180180F1D
0x180180ed2  lea     ebx, [rax+7]
0x180180ed5  mov     eax, cs:dword_18039EB68
0x180180edb  cmp     eax, 2
0x180180ede  jbe     loc_18018104A
0x180180ee4  mov     dword ptr [rbp+100h+var_160], ebx
0x180180ee7  mov     dword ptr [rbp+100h+var_158], 42Ah
0x180180eee  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x180180ef5  mov     [rsp+200h+var_190], rax
0x180180efa  lea     rax, [rbp+100h+var_160]
0x180180efe  mov     [rsp+200h+var_1D0], rax
0x180180f03  lea     rax, [rbp+100h+var_158]
0x180180f07  mov     [rsp+200h+var_1D8], rax
0x180180f0c  lea     rax, [rsp+200h+var_190]
0x180180f11  lea     rdx, byte_180369611
0x180180f18  jmp     loc_180181040
0x180180f1d  lea     r8, [rbp+100h+instance]; instance
0x180180f21  lea     rdx, SPACES_PhysicalDisk_IsDeviceCacheEnabled_rtti; methodDecl
0x180180f28  mov     rcx, rsi; context
0x180180f2b  call    MI_Context_ConstructParameters
0x180180f30  mov     ebx, eax
0x180180f32  test    eax, eax
0x180180f34  jz      short loc_180180F7E
0x180180f36  mov     eax, cs:dword_18039EB68
0x180180f3c  cmp     eax, 2
0x180180f3f  jbe     loc_18018104A
0x180180f45  mov     dword ptr [rbp+100h+var_150], ebx
0x180180f48  mov     dword ptr [rbp+100h+var_148], 432h
0x180180f4f  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x180180f56  mov     [rsp+200h+var_190], rax
0x180180f5b  lea     rax, [rbp+100h+var_150]
0x180180f5f  mov     [rsp+200h+var_1D0], rax
0x180180f64  lea     rax, [rbp+100h+var_148]
0x180180f68  mov     [rsp+200h+var_1D8], rax
0x180180f6d  lea     rax, [rsp+200h+var_190]
0x180180f72  lea     rdx, dword_18036975C
0x180180f79  jmp     loc_180181040
0x180180f7e  mov     rcx, [rbp+100h+var_180]
0x180180f82  mov     rax, [rcx]
0x180180f85  lea     rdx, [rbp+100h+instance]
0x180180f89  mov     qword ptr [rsp+200h+var_1E0], rdx
0x180180f8e  mov     r9, r13
0x180180f91  mov     r8, rsi
0x180180f94  mov     edx, 40008h
0x180180f99  mov     rax, [rax+30h]
0x180180f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180fa2  mov     ebx, eax
0x180180fa4  test    eax, eax
0x180180fa6  jz      short loc_180180FED
0x180180fa8  mov     eax, cs:dword_18039EB68
0x180180fae  cmp     eax, 2
0x180180fb1  jbe     loc_18018104A
0x180180fb7  mov     dword ptr [rbp+100h+var_140], ebx
0x180180fba  mov     dword ptr [rbp+100h+var_178], 43Dh
0x180180fc1  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x180180fc8  mov     [rsp+200h+var_190], rax
0x180180fcd  lea     rax, [rbp+100h+var_140]
0x180180fd1  mov     [rsp+200h+var_1D0], rax
0x180180fd6  lea     rax, [rbp+100h+var_178]
0x180180fda  mov     [rsp+200h+var_1D8], rax
0x180180fdf  lea     rax, [rsp+200h+var_190]
0x180180fe4  lea     rdx, dword_180369F54
0x180180feb  jmp     short loc_180181040
0x180180fed  lea     rdx, [rbp+100h+instance]
0x180180ff1  mov     rcx, rsi; self
0x180180ff4  call    MI_Instance_Destruct
0x180180ff9  mov     ebx, eax
0x180180ffb  test    eax, eax
0x180180ffd  jz      short loc_18018104A
0x180180fff  mov     eax, cs:dword_18039EB68
0x180181005  cmp     eax, 2
0x180181008  jbe     short loc_18018104A
0x18018100a  mov     [rsp+200h+var_184], ebx
0x18018100e  mov     dword ptr [rsp+200h+var_190], 445h
0x180181016  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x18018101d  mov     [rbp+100h+var_178], rax
0x180181021  lea     rax, [rsp+200h+var_184]
0x180181026  mov     [rsp+200h+var_1D0], rax
0x18018102b  lea     rax, [rsp+200h+var_190]
0x180181030  mov     [rsp+200h+var_1D8], rax
0x180181035  lea     rax, [rbp+100h+var_178]
0x180181039  lea     rdx, byte_18036A3F9
0x180181040  mov     qword ptr [rsp+200h+var_1E0], rax
0x180181045  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18018104a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180181051  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180181056  xor     r13d, r13d
0x180181059  mov     [rsp+200h+var_1D8], r13; unsigned __int16 *
0x18018105e  mov     [rsp+200h+var_1E0], ebx; enum _MI_Result
0x180181062  lea     r9, [rbp+100h+var_90]; struct _MI_ConstUint32Field *
0x180181066  lea     r8, [r14+40h]; struct _MI_ConstStringField *
0x18018106a  mov     rdx, [rbp+100h+var_138]; unsigned __int16 *
0x18018106e  mov     rcx, [rbp+100h+var_170]; unsigned __int16 *
0x180181072  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180181077  test    r12d, r12d
0x18018107a  jnz     loc_180181182
0x180181080  lea     rcx, [rbp+100h+var_130]; this
0x180181084  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180181089  mov     eax, cs:dword_18039EB68
0x18018108f  cmp     eax, 5
0x180181092  jbe     loc_180181182
0x180181098  mov     rdx, 400000000000h
0x1801810a2  lea     rcx, dword_18039EB68
0x1801810a9  call    _tlgKeywordOn
0x1801810ae  test    al, al
0x1801810b0  jz      loc_180181182
0x1801810b6  mov     [rbp+100h+var_170], r13
0x1801810ba  mov     [rbp+100h+var_138], r13
0x1801810be  mov     [rbp+100h+var_140], r13
0x1801810c2  mov     rax, [rbp+100h+var_128]
0x1801810c6  sub     rax, [rbp+100h+var_130]
0x1801810ca  imul    rax, 3E8h
0x1801810d1  xor     edx, edx
0x1801810d3  div     [rbp+100h+var_120]
0x1801810d7  mov     [rbp+100h+var_148], rax
0x1801810db  mov     dword ptr [rsp+200h+var_190], ebx
0x1801810df  mov     al, [rbp+100h+var_90.exists]
0x1801810e2  neg     al
0x1801810e4  sbb     ecx, ecx
0x1801810e6  and     ecx, [rbp+100h+var_90.value]
0x1801810e9  mov     [rsp+200h+var_184], ecx
0x1801810ed  mov     dword ptr [rbp+100h+var_178], r15d
0x1801810f1  cmp     [r14+48h], r13b
0x1801810f5  jz      short loc_1801810FD
0x1801810f7  mov     rax, [r14+40h]
0x1801810fb  jmp     short loc_180181100
0x1801810fd  mov     rax, r13
0x180181100  mov     [rbp+100h+var_150], rax
0x180181104  lea     rax, aIsdevicecachee_0; "IsDeviceCacheEnabled"
0x18018110b  mov     [rbp+100h+var_158], rax
0x18018110f  lea     rax, aPhysicaldisk_0; "PhysicalDisk"
0x180181116  mov     [rbp+100h+var_160], rax
0x18018111a  lea     rax, [rbp+100h+var_170]
0x18018111e  mov     [rsp+200h+var_198], rax
0x180181123  lea     rax, [rbp+100h+var_138]
0x180181127  mov     [rsp+200h+var_1A0], rax
0x18018112c  lea     rax, [rbp+100h+var_140]
0x180181130  mov     [rsp+200h+var_1A8], rax
0x180181135  lea     rax, [rbp+100h+var_148]
0x180181139  mov     [rsp+200h+var_1B0], rax
0x18018113e  lea     rax, [rsp+200h+var_190]
0x180181143  mov     [rsp+200h+var_1B8], rax
0x180181148  lea     rax, [rsp+200h+var_184]
0x18018114d  mov     [rsp+200h+var_1C0], rax
0x180181152  lea     rax, [rbp+100h+var_178]
0x180181156  mov     [rsp+200h+var_1C8], rax
0x18018115b  lea     rax, [rbp+100h+var_150]
0x18018115f  mov     [rsp+200h+var_1D0], rax
0x180181164  lea     rax, [rbp+100h+var_158]
0x180181168  mov     [rsp+200h+var_1D8], rax
0x18018116d  lea     rax, [rbp+100h+var_160]
0x180181171  mov     qword ptr [rsp+200h+var_1E0], rax
0x180181176  lea     rdx, byte_18036999F
0x18018117d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180181182  lea     rcx, [rbp+100h+instance]; self
0x180181186  call    MI_Instance_Destruct
0x18018118b  mov     eax, cs:dword_18039EB68
0x180181191  cmp     eax, 5
0x180181194  jbe     short loc_1801811C8
0x180181196  mov     dword ptr [rsp+200h+var_190], 466h
0x18018119e  lea     rax, aSpacesPhysical_17; "SPACES_PhysicalDisk_Invoke_IsDeviceCach"...
0x1801811a5  mov     [rbp+100h+var_170], rax
0x1801811a9  lea     rax, [rsp+200h+var_190]
0x1801811ae  mov     [rsp+200h+var_1D8], rax
0x1801811b3  lea     rax, [rbp+100h+var_170]
0x1801811b7  mov     qword ptr [rsp+200h+var_1E0], rax
0x1801811bc  lea     rdx, byte_18036A183
  ... truncated ...
```
