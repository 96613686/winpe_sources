# SPACES_StorageSubsystem_Invoke_CreateStoragePool

- ea: `0x180170670`
- end: `0x180170c77`
- name: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- size: `1543`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x1800047fc`
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
- `0x180170670`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801706ed`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170758`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170c40`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801706ed`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170758`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170c40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180170716`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180170716`

## string_xrefs

- `0x180170b4c`: `CreateStoragePool`
- `0x18017076a`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x180170884`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x1801708e6`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x180170959`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x1801709ad`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`
- `0x180170bef`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool`

## pseudocode

```c
ULONG __fastcall SPACES_StorageSubsystem_Invoke_CreateStoragePool(
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
  enum _MI_Result v13; // r14d
  int IsRemoteRequest; // r13d
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
  int v31; // eax
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rax
  const MI_Char *v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  const char *v39; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v40; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v41; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v42; // [rsp+90h] [rbp-70h] BYREF
  const char *v43; // [rsp+98h] [rbp-68h] BYREF
  const char *v44; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v45; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  const char *v47; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v48; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v49; // [rsp+C8h] [rbp-38h] BYREF
  const char *v50; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v51[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v52; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v54; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v57; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v58; // [rsp+250h] [rbp+150h]
  char v59; // [rsp+258h] [rbp+158h]
  struct _MI_Instance *v60; // [rsp+260h] [rbp+160h]
  char v61; // [rsp+268h] [rbp+168h]
  GUID ActivityId; // [rsp+280h] [rbp+180h] BYREF
  GUID v63; // [rsp+290h] [rbp+190h]
  GUID v64; // [rsp+2A0h] [rbp+1A0h] BYREF

  v49 = a4;
  v48 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v63 = ActivityId;
  v64 = ActivityId;
  EventActivityIdControl(4u, &v64);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v43) = 149;
    v39 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageSubsystem_Invoke_CreateStoragePool",
      (unsigned int)word_180363432,
      v11,
      v12,
      (__int64)&v39,
      (__int64)&v43);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xF8u);
  v52 = 0;
  v53 = 0;
  v42 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  v42 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v51);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v51);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v52) = 13;
    *((_QWORD *)&v52 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v52, &v42, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v43) = v15;
        LODWORD(v45) = 180;
        v39 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180364508,
          v18,
          v19,
          (__int64)&v39,
          (__int64)&v45,
          (__int64)&v43);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageSubsystem_CreateStoragePool_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v46) = v15;
          LODWORD(v47) = 188;
          v39 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)byte_18036445D,
            v21,
            v22,
            (__int64)&v39,
            (__int64)&v47,
            (__int64)&v46);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v42 + 48LL))(
                v42,
                851969,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            v40 = v15;
            LODWORD(v44) = 199;
            v39 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)word_180363FB2,
              v24,
              v25,
              (__int64)&v39,
              (__int64)&v44,
              (__int64)&v40);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v41 = v15;
            LODWORD(v39) = 207;
            v44 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_180364B91,
              v27,
              v28,
              (__int64)&v44,
              (__int64)&v39,
              (__int64)&v41);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v49, v48, a6 + 4, &v57, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v51);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 128) )
          v31 = *(_DWORD *)(a7 + 120);
        else
          v31 = 0;
        LODWORD(v39) = v31;
        if ( v61 )
        {
          v54 = *v60;
          v32 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v54, 0);
        }
        else
        {
          v32 = 0;
        }
        v49 = v32;
        if ( v59 )
        {
          v54 = *v58;
          v33 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v54, 0);
        }
        else
        {
          v33 = 0;
        }
        v48 = v33;
        v47 = "StoragePool";
        v46 = (unsigned __int64)(1000LL * (v51[1] - v51[0])) / v51[2];
        v41 = v15;
        LODWORD(v44) = v57.exists != 0 ? v57.value : 0;
        v40 = v13;
        if ( a6[4].exists )
          v34 = a6[4].value;
        else
          v34 = 0;
        v45 = v34;
        v43 = "CreateStoragePool";
        v50 = "StorageSubsystem";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v57.exists != 0 ? v57.value : 0,
          (unsigned int)&unk_1803641D8,
          v29,
          v30,
          (__int64)&v50,
          (__int64)&v43,
          (__int64)&v45,
          (__int64)&v40,
          (__int64)&v44,
          (__int64)&v41,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v49,
          (__int64)&v39);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v39) = 241;
    v50 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)&word_180363BA6,
      v36,
      v37,
      (__int64)&v50,
      (__int64)&v39);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v51);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v42);
  return EventActivityIdControl(4u, &v64);
}

```

## disassembly

```asm
0x180170670  mov     [rsp-8+arg_10], rbx
0x180170675  push    rbp
0x180170676  push    rsi
0x180170677  push    rdi
0x180170678  push    r12
0x18017067a  push    r13
0x18017067c  push    r14
0x18017067e  push    r15
0x180170680  lea     rbp, [rsp-1C0h]
0x180170688  sub     rsp, 2C0h
0x18017068f  mov     rax, cs:__security_cookie
0x180170696  xor     rax, rsp
0x180170699  mov     [rbp+1F0h+var_40], rax
0x1801706a0  mov     [rbp+1F0h+var_228], r9
0x1801706a4  mov     rsi, rdx
0x1801706a7  mov     r12, rcx
0x1801706aa  mov     rax, [rbp+1F0h+arg_20]
0x1801706b1  mov     [rbp+1F0h+var_230], rax
0x1801706b5  mov     rdi, [rbp+1F0h+arg_28]
0x1801706bc  mov     r15, [rbp+1F0h+arg_30]
0x1801706c3  xorps   xmm0, xmm0
0x1801706c6  xor     eax, eax
0x1801706c8  movups  xmmword ptr [rbp+1F0h+value], xmm0
0x1801706cc  movups  xmmword ptr [rbp+1F0h+value+10h], xmm0
0x1801706d0  mov     qword ptr [rbp+1F0h+value+20h], rax
0x1801706d4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801706db  movdqu  xmmword ptr [rbp+1F0h+ActivityId.Data1], xmm0
0x1801706e3  lea     rdx, [rbp+1F0h+ActivityId]; ActivityId
0x1801706ea  lea     ecx, [rax+1]; ControlCode
0x1801706ed  call    cs:__imp_EventActivityIdControl
0x1801706f4  nop     dword ptr [rax+rax+00h]
0x1801706f9  lea     r9, [rbp+1F0h+value]; value
0x1801706fd  mov     rcx, rsi; context
0x180170700  call    MI_Context_GetCustomOption_1
0x180170705  xor     ebx, ebx
0x180170707  test    eax, eax
0x180170709  jnz     short loc_180170722
0x18017070b  lea     rdx, [rbp+1F0h+ActivityId]; pclsid
0x180170712  mov     rcx, qword ptr [rbp+1F0h+value]; lpsz
0x180170716  call    cs:__imp_CLSIDFromString
0x18017071d  nop     dword ptr [rax+rax+00h]
0x180170722  mov     rcx, qword ptr [rbp+1F0h+ActivityId.Data1]
0x180170729  mov     [rbp+1F0h+var_60], rcx
0x180170730  mov     rax, qword ptr [rbp+1F0h+ActivityId.Data4]
0x180170737  mov     [rbp+1F0h+var_58], rax
0x18017073e  mov     qword ptr [rbp+1F0h+var_50.Data1], rcx
0x180170745  mov     qword ptr [rbp+1F0h+var_50.Data4], rax
0x18017074c  lea     rdx, [rbp+1F0h+var_50]; ActivityId
0x180170753  mov     ecx, 4; ControlCode
0x180170758  call    cs:__imp_EventActivityIdControl
0x18017075f  nop     dword ptr [rax+rax+00h]
0x180170764  mov     eax, cs:dword_18039EB68
0x18017076a  lea     rcx, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170771  cmp     eax, 5
0x180170774  jbe     short loc_18017079F
0x180170776  mov     dword ptr [rbp+1F0h+var_258], 95h
0x18017077d  mov     [rbp+1F0h+var_270], rcx
0x180170781  lea     rax, [rbp+1F0h+var_258]
0x180170785  mov     [rsp+2F0h+var_2C8], rax
0x18017078a  lea     rax, [rbp+1F0h+var_270]
0x18017078e  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x180170793  lea     rdx, word_180363432
0x18017079a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18017079f  mov     [rbp+1F0h+instance.ft], rbx
0x1801707a6  xor     edx, edx; Val
0x1801707a8  mov     r8d, 0F8h; Size
0x1801707ae  lea     rcx, [rbp+1F0h+instance.classDecl]; void *
0x1801707b5  call    memset_0
0x1801707ba  xorps   xmm0, xmm0
0x1801707bd  xor     eax, eax
0x1801707bf  movups  [rbp+1F0h+var_1F8], xmm0
0x1801707c3  mov     [rbp+1F0h+var_1E8], rax
0x1801707c7  mov     [rbp+1F0h+var_260], rbx
0x1801707cb  lea     rcx, [rbp+1F0h+var_260]
0x1801707cf  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801707d4  mov     [rbp+1F0h+var_260], rbx
0x1801707d8  mov     r14d, ebx
0x1801707db  lea     rcx, [rbp+1F0h+var_218]; this
0x1801707df  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801707e4  mov     rcx, rsi; context
0x1801707e7  call    WspIsRemoteRequest
0x1801707ec  mov     r13d, eax
0x1801707ef  test    eax, eax
0x1801707f1  jnz     short loc_180170815
0x1801707f3  lea     rcx, [rbp+1F0h+var_218]; this
0x1801707f7  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801707fc  cmp     [rdi+48h], bl
0x1801707ff  jz      short loc_180170812
0x180170801  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180170805  call    WspIsRemoteInstance
0x18017080a  test    al, al
0x18017080c  lea     r14d, [r13+1]
0x180170810  jnz     short loc_180170815
0x180170812  mov     r14d, ebx
0x180170815  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18017081c  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180170821  mov     ebx, eax
0x180170823  test    eax, eax
0x180170825  jnz     loc_1801709ED
0x18017082b  mov     dword ptr [rbp+1F0h+var_1F8], 0Dh
0x180170832  mov     rax, [rdi+40h]
0x180170836  mov     qword ptr [rbp+1F0h+var_1F8+8], rax
0x18017083a  mov     rbx, [r12]
0x18017083e  lea     rcx, [rbp+1F0h+var_260]
0x180170842  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180170847  mov     [rsp+2F0h+var_2D0], 1; int
0x18017084f  lea     r9, [rbp+1F0h+var_260]; struct ISpWmiObject **
0x180170853  lea     r8, [rbp+1F0h+var_1F8]; struct _SP_OBJECT_ID *
0x180170857  mov     rdx, rsi; context
0x18017085a  mov     rcx, rbx; this
0x18017085d  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180170862  mov     ebx, eax
0x180170864  xor     r12d, r12d
0x180170867  test    eax, eax
0x180170869  jz      short loc_1801708B1
0x18017086b  mov     eax, cs:dword_18039EB68
0x180170871  cmp     eax, 2
0x180170874  jbe     loc_1801709DF
0x18017087a  mov     dword ptr [rbp+1F0h+var_258], ebx
0x18017087d  mov     dword ptr [rbp+1F0h+var_248], 0B4h
0x180170884  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x18017088b  mov     [rbp+1F0h+var_270], rax
0x18017088f  lea     rax, [rbp+1F0h+var_258]
0x180170893  mov     [rsp+2F0h+var_2C0], rax
0x180170898  lea     rax, [rbp+1F0h+var_248]
0x18017089c  mov     [rsp+2F0h+var_2C8], rax
0x1801708a1  lea     rax, [rbp+1F0h+var_270]
0x1801708a5  lea     rdx, unk_180364508
0x1801708ac  jmp     loc_1801709D5
0x1801708b1  lea     r8, [rbp+1F0h+instance]; instance
0x1801708b8  lea     rdx, SPACES_StorageSubsystem_CreateStoragePool_rtti; methodDecl
0x1801708bf  mov     rcx, rsi; context
0x1801708c2  call    MI_Context_ConstructParameters
0x1801708c7  mov     ebx, eax
0x1801708c9  test    eax, eax
0x1801708cb  jz      short loc_180170913
0x1801708cd  mov     eax, cs:dword_18039EB68
0x1801708d3  cmp     eax, 2
0x1801708d6  jbe     loc_1801709DF
0x1801708dc  mov     dword ptr [rbp+1F0h+var_240], ebx
0x1801708df  mov     dword ptr [rbp+1F0h+var_238], 0BCh
0x1801708e6  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x1801708ed  mov     [rbp+1F0h+var_270], rax
0x1801708f1  lea     rax, [rbp+1F0h+var_240]
0x1801708f5  mov     [rsp+2F0h+var_2C0], rax
0x1801708fa  lea     rax, [rbp+1F0h+var_238]
0x1801708fe  mov     [rsp+2F0h+var_2C8], rax
0x180170903  lea     rax, [rbp+1F0h+var_270]
0x180170907  lea     rdx, byte_18036445D
0x18017090e  jmp     loc_1801709D5
0x180170913  mov     rcx, [rbp+1F0h+var_260]
0x180170917  mov     rax, [rcx]
0x18017091a  lea     rdx, [rbp+1F0h+instance]
0x180170921  mov     qword ptr [rsp+2F0h+var_2D0], rdx
0x180170926  mov     r9, r15
0x180170929  mov     r8, rsi
0x18017092c  mov     edx, 0D0001h
0x180170931  mov     rax, [rax+30h]
0x180170935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017093a  mov     ebx, eax
0x18017093c  test    eax, eax
0x18017093e  jz      short loc_180170983
0x180170940  mov     eax, cs:dword_18039EB68
0x180170946  cmp     eax, 2
0x180170949  jbe     loc_1801709DF
0x18017094f  mov     [rbp+1F0h+var_268], ebx
0x180170952  mov     dword ptr [rbp+1F0h+var_250], 0C7h
0x180170959  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170960  mov     [rbp+1F0h+var_270], rax
0x180170964  lea     rax, [rbp+1F0h+var_268]
0x180170968  mov     [rsp+2F0h+var_2C0], rax
0x18017096d  lea     rax, [rbp+1F0h+var_250]
0x180170971  mov     [rsp+2F0h+var_2C8], rax
0x180170976  lea     rax, [rbp+1F0h+var_270]
0x18017097a  lea     rdx, word_180363FB2
0x180170981  jmp     short loc_1801709D5
0x180170983  lea     rdx, [rbp+1F0h+instance]
0x18017098a  mov     rcx, rsi; self
0x18017098d  call    MI_Instance_Destruct
0x180170992  mov     ebx, eax
0x180170994  test    eax, eax
0x180170996  jz      short loc_1801709DF
0x180170998  mov     eax, cs:dword_18039EB68
0x18017099e  cmp     eax, 2
0x1801709a1  jbe     short loc_1801709DF
0x1801709a3  mov     [rbp+1F0h+var_264], ebx
0x1801709a6  mov     dword ptr [rbp+1F0h+var_270], 0CFh
0x1801709ad  lea     rax, aSpacesStorages_41; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x1801709b4  mov     [rbp+1F0h+var_250], rax
0x1801709b8  lea     rax, [rbp+1F0h+var_264]
0x1801709bc  mov     [rsp+2F0h+var_2C0], rax
0x1801709c1  lea     rax, [rbp+1F0h+var_270]
0x1801709c5  mov     [rsp+2F0h+var_2C8], rax
0x1801709ca  lea     rax, [rbp+1F0h+var_250]
0x1801709ce  lea     rdx, byte_180364B91
0x1801709d5  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x1801709da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801709df  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801709e6  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801709eb  jmp     short loc_1801709F0
0x1801709ed  xor     r12d, r12d
0x1801709f0  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x1801709f4  mov     [rsp+2F0h+var_2C8], r12; unsigned __int16 *
0x1801709f9  mov     [rsp+2F0h+var_2D0], ebx; enum _MI_Result
0x1801709fd  lea     r9, [rbp+1F0h+var_130]; struct _MI_ConstUint32Field *
0x180170a04  mov     rdx, [rbp+1F0h+var_230]; unsigned __int16 *
0x180170a08  mov     rcx, [rbp+1F0h+var_228]; unsigned __int16 *
0x180170a0c  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x180170a11  test    r13d, r13d
0x180170a14  jnz     loc_180170BD1
0x180170a1a  lea     rcx, [rbp+1F0h+var_218]; this
0x180170a1e  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180170a23  mov     eax, cs:dword_18039EB68
0x180170a29  cmp     eax, 5
0x180170a2c  jbe     loc_180170BD1
0x180170a32  mov     rdx, 400000000000h
0x180170a3c  lea     rcx, dword_18039EB68
0x180170a43  call    _tlgKeywordOn
0x180170a48  test    al, al
0x180170a4a  jz      loc_180170BD1
0x180170a50  cmp     [r15+80h], r12b
0x180170a57  jz      short loc_180170A5F
0x180170a59  mov     eax, [r15+78h]
0x180170a5d  jmp     short loc_180170A62
0x180170a5f  mov     eax, r12d
0x180170a62  mov     dword ptr [rbp+1F0h+var_270], eax
0x180170a65  cmp     [rbp+1F0h+var_88], r12b
0x180170a6c  jz      short loc_180170AA9
0x180170a6e  mov     rax, [rbp+1F0h+var_90]
0x180170a75  movups  xmm0, xmmword ptr [rax]
0x180170a78  movaps  xmmword ptr [rbp+1F0h+var_1E0.ft], xmm0
0x180170a7c  movups  xmm1, xmmword ptr [rax+10h]
0x180170a80  movaps  xmmword ptr [rbp+1F0h+var_1E0.serverName], xmm1
0x180170a84  movups  xmm0, xmmword ptr [rax+20h]
0x180170a88  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved], xmm0
0x180170a8c  movups  xmm1, xmmword ptr [rax+30h]
0x180170a90  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved+10h], xmm1
0x180170a94  xor     r8d, r8d; unsigned __int16 *
0x180170a97  lea     rdx, [rbp+1F0h+var_1E0]; struct _MI_Instance
0x180170a9b  lea     rcx, name; "ObjectId"
0x180170aa2  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180170aa7  jmp     short loc_180170AAC
0x180170aa9  mov     rax, r12
0x180170aac  mov     [rbp+1F0h+var_228], rax
0x180170ab0  cmp     [rbp+1F0h+var_98], r12b
0x180170ab7  jz      short loc_180170AF4
0x180170ab9  mov     rax, [rbp+1F0h+var_A0]
0x180170ac0  movups  xmm0, xmmword ptr [rax]
0x180170ac3  movaps  xmmword ptr [rbp+1F0h+var_1E0.ft], xmm0
0x180170ac7  movups  xmm1, xmmword ptr [rax+10h]
0x180170acb  movaps  xmmword ptr [rbp+1F0h+var_1E0.serverName], xmm1
0x180170acf  movups  xmm0, xmmword ptr [rax+20h]
0x180170ad3  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved], xmm0
0x180170ad7  movups  xmm1, xmmword ptr [rax+30h]
0x180170adb  movaps  xmmword ptr [rbp+1F0h+var_1E0.reserved+10h], xmm1
0x180170adf  xor     r8d, r8d; unsigned __int16 *
0x180170ae2  lea     rdx, [rbp+1F0h+var_1E0]; struct _MI_Instance
0x180170ae6  lea     rcx, name; "ObjectId"
0x180170aed  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180170af2  jmp     short loc_180170AF7
0x180170af4  mov     rax, r12
0x180170af7  mov     [rbp+1F0h+var_230], rax
0x180170afb  lea     rax, aStoragepool_0; "StoragePool"
0x180170b02  mov     [rbp+1F0h+var_238], rax
0x180170b06  mov     rax, [rbp+1F0h+var_210]
0x180170b0a  sub     rax, [rbp+1F0h+var_218]
0x180170b0e  imul    rax, 3E8h
0x180170b15  xor     edx, edx
0x180170b17  div     [rbp+1F0h+var_208]
0x180170b1b  mov     [rbp+1F0h+var_240], rax
0x180170b1f  mov     [rbp+1F0h+var_264], ebx
0x180170b22  mov     al, [rbp+1F0h+var_130.exists]
0x180170b28  neg     al
0x180170b2a  sbb     ecx, ecx
0x180170b2c  and     ecx, [rbp+1F0h+var_130.value]
0x180170b32  mov     dword ptr [rbp+1F0h+var_250], ecx
0x180170b35  mov     [rbp+1F0h+var_268], r14d
0x180170b39  cmp     [rdi+48h], r12b
0x180170b3d  jz      short loc_180170B45
0x180170b3f  mov     rax, [rdi+40h]
0x180170b43  jmp     short loc_180170B48
0x180170b45  mov     rax, r12
0x180170b48  mov     [rbp+1F0h+var_248], rax
0x180170b4c  lea     rax, aCreatestoragep; "CreateStoragePool"
0x180170b53  mov     [rbp+1F0h+var_258], rax
0x180170b57  lea     rax, aStoragesubsyst_3; "StorageSubsystem"
0x180170b5e  mov     [rbp+1F0h+var_220], rax
0x180170b62  lea     rax, [rbp+1F0h+var_270]
0x180170b66  mov     [rsp+2F0h+var_280], rax
0x180170b6b  lea     rax, [rbp+1F0h+var_228]
0x180170b6f  mov     [rsp+2F0h+var_288], rax
0x180170b74  lea     rax, [rbp+1F0h+var_230]
0x180170b78  mov     [rsp+2F0h+var_290], rax
0x180170b7d  lea     rax, [rbp+1F0h+var_238]
0x180170b81  mov     [rsp+2F0h+var_298], rax
0x180170b86  lea     rax, [rbp+1F0h+var_240]
0x180170b8a  mov     [rsp+2F0h+var_2A0], rax
0x180170b8f  lea     rax, [rbp+1F0h+var_264]
0x180170b93  mov     [rsp+2F0h+var_2A8], rax
0x180170b98  lea     rax, [rbp+1F0h+var_250]
  ... truncated ...
```
