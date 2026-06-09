# SPACES_StoragePool_Invoke_RemovePhysicalDisk

- ea: `0x18015dd80`
- end: `0x18015e334`
- name: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- size: `1460`
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
- `0x18015dd80`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015ddfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015de68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e2fd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015ddfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015de68`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e2fd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015de26`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015de26`

## string_xrefs

- `0x18015e209`: `RemovePhysicalDisk`
- `0x18015de7a`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x18015df92`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x18015dff4`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x18015e067`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x18015e0bb`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`
- `0x18015e2ac`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_RemovePhysicalDisk(
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
  const MI_Char *v33; // rax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  const char *v38; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v39; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v40; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v41; // [rsp+90h] [rbp-70h] BYREF
  const char *v42; // [rsp+98h] [rbp-68h] BYREF
  const char *v43; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v44; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v47; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v48; // [rsp+C8h] [rbp-38h] BYREF
  const char *v49; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v50[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v53; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v56; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v57; // [rsp+1E0h] [rbp+E0h]
  char v58; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v60; // [rsp+210h] [rbp+110h]
  GUID v61; // [rsp+220h] [rbp+120h] BYREF

  v48 = a4;
  v47 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v60 = ActivityId;
  v61 = ActivityId;
  EventActivityIdControl(4u, &v61);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v42) = 1502;
    v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_RemovePhysicalDisk",
      (unsigned int)byte_18035CC79,
      v11,
      v12,
      (__int64)&v38,
      (__int64)&v42);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v51 = 0;
  v52 = 0;
  v41 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
  v41 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v50);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v50);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v51) = 11;
    *((_QWORD *)&v51 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v51, &v41, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v42) = v15;
        LODWORD(v44) = 1533;
        v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_18035DA9B,
          v18,
          v19,
          (__int64)&v38,
          (__int64)&v44,
          (__int64)&v42);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_RemovePhysicalDisk_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v45) = v15;
          LODWORD(v46) = 1541;
          v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&byte_18035BF3F,
            v21,
            v22,
            (__int64)&v38,
            (__int64)&v46,
            (__int64)&v45);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v41 + 48LL))(
                v41,
                720900,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            v39 = v15;
            LODWORD(v43) = 1552;
            v38 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)&byte_18035C6F7,
              v24,
              v25,
              (__int64)&v38,
              (__int64)&v43,
              (__int64)&v39);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v40 = v15;
            LODWORD(v38) = 1560;
            v43 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_18035D119,
              v27,
              v28,
              (__int64)&v43,
              (__int64)&v38,
              (__int64)&v40);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v48, v47, a6 + 4, &v56, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v50);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 88) )
          v31 = *(_DWORD *)(a7 + 80);
        else
          v31 = 0;
        LODWORD(v38) = v31;
        if ( v58 )
        {
          v53 = *v57;
          v32 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v53, 0);
        }
        else
        {
          v32 = 0;
        }
        v48 = v32;
        v47 = 0;
        v46 = 0;
        v45 = (unsigned __int64)(1000LL * (v50[1] - v50[0])) / v50[2];
        v40 = v15;
        LODWORD(v43) = v56.exists != 0 ? v56.value : 0;
        v39 = v13;
        if ( a6[4].exists )
          v33 = a6[4].value;
        else
          v33 = 0;
        v44 = v33;
        v42 = "RemovePhysicalDisk";
        v49 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v56.exists != 0 ? v56.value : 0,
          (unsigned int)&byte_18035CEEF,
          v29,
          v30,
          (__int64)&v49,
          (__int64)&v42,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v38);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v38) = 1594;
    v49 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v34,
      (unsigned int)qword_18035C5B8,
      v35,
      v36,
      (__int64)&v49,
      (__int64)&v38);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v50);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x18015dd80  mov     [rsp-8+arg_10], rbx
0x18015dd85  push    rbp
0x18015dd86  push    rsi
0x18015dd87  push    rdi
0x18015dd88  push    r12
0x18015dd8a  push    r13
0x18015dd8c  push    r14
0x18015dd8e  push    r15
0x18015dd90  lea     rbp, [rsp-140h]
0x18015dd98  sub     rsp, 240h
0x18015dd9f  mov     rax, cs:__security_cookie
0x18015dda6  xor     rax, rsp
0x18015dda9  mov     [rbp+170h+var_40], rax
0x18015ddb0  mov     [rbp+170h+var_1A8], r9
0x18015ddb4  mov     rsi, rdx
0x18015ddb7  mov     r12, rcx
0x18015ddba  mov     rax, [rbp+170h+arg_20]
0x18015ddc1  mov     [rbp+170h+var_1B0], rax
0x18015ddc5  mov     rdi, [rbp+170h+arg_28]
0x18015ddcc  mov     r15, [rbp+170h+arg_30]
0x18015ddd3  xorps   xmm0, xmm0
0x18015ddd6  xor     eax, eax
0x18015ddd8  movups  xmmword ptr [rbp+170h+value], xmm0
0x18015dddc  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18015dde0  mov     qword ptr [rbp+170h+value+20h], rax
0x18015dde4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015ddeb  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18015ddf3  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18015ddfa  lea     ecx, [rax+1]; ControlCode
0x18015ddfd  call    cs:__imp_EventActivityIdControl
0x18015de04  nop     dword ptr [rax+rax+00h]
0x18015de09  lea     r9, [rbp+170h+value]; value
0x18015de0d  mov     rcx, rsi; context
0x18015de10  call    MI_Context_GetCustomOption_1
0x18015de15  xor     ebx, ebx
0x18015de17  test    eax, eax
0x18015de19  jnz     short loc_18015DE32
0x18015de1b  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18015de22  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18015de26  call    cs:__imp_CLSIDFromString
0x18015de2d  nop     dword ptr [rax+rax+00h]
0x18015de32  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18015de39  mov     [rbp+170h+var_60], rcx
0x18015de40  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18015de47  mov     [rbp+170h+var_58], rax
0x18015de4e  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18015de55  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18015de5c  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18015de63  mov     ecx, 4; ControlCode
0x18015de68  call    cs:__imp_EventActivityIdControl
0x18015de6f  nop     dword ptr [rax+rax+00h]
0x18015de74  mov     eax, cs:dword_18039EB68
0x18015de7a  lea     rcx, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015de81  cmp     eax, 5
0x18015de84  jbe     short loc_18015DEAF
0x18015de86  mov     dword ptr [rbp+170h+var_1D8], 5DEh
0x18015de8d  mov     [rbp+170h+var_1F0], rcx
0x18015de91  lea     rax, [rbp+170h+var_1D8]
0x18015de95  mov     [rsp+270h+var_248], rax
0x18015de9a  lea     rax, [rbp+170h+var_1F0]
0x18015de9e  mov     qword ptr [rsp+270h+var_250], rax
0x18015dea3  lea     rdx, byte_18035CC79
0x18015deaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015deaf  mov     [rbp+170h+instance.ft], rbx
0x18015deb6  xor     edx, edx; Val
0x18015deb8  lea     r8d, [rdx+78h]; Size
0x18015debc  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18015dec3  call    memset_0
0x18015dec8  xorps   xmm0, xmm0
0x18015decb  xor     eax, eax
0x18015decd  movups  [rbp+170h+var_178], xmm0
0x18015ded1  mov     [rbp+170h+var_168], rax
0x18015ded5  mov     [rbp+170h+var_1E0], rbx
0x18015ded9  lea     rcx, [rbp+170h+var_1E0]
0x18015dedd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015dee2  mov     [rbp+170h+var_1E0], rbx
0x18015dee6  mov     r14d, ebx
0x18015dee9  lea     rcx, [rbp+170h+var_198]; this
0x18015deed  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015def2  mov     rcx, rsi; context
0x18015def5  call    WspIsRemoteRequest
0x18015defa  mov     r13d, eax
0x18015defd  test    eax, eax
0x18015deff  jnz     short loc_18015DF23
0x18015df01  lea     rcx, [rbp+170h+var_198]; this
0x18015df05  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015df0a  cmp     [rdi+48h], bl
0x18015df0d  jz      short loc_18015DF20
0x18015df0f  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015df13  call    WspIsRemoteInstance
0x18015df18  test    al, al
0x18015df1a  lea     r14d, [r13+1]
0x18015df1e  jnz     short loc_18015DF23
0x18015df20  mov     r14d, ebx
0x18015df23  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015df2a  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015df2f  mov     ebx, eax
0x18015df31  test    eax, eax
0x18015df33  jnz     loc_18015E0FB
0x18015df39  mov     dword ptr [rbp+170h+var_178], 0Bh
0x18015df40  mov     rax, [rdi+40h]
0x18015df44  mov     qword ptr [rbp+170h+var_178+8], rax
0x18015df48  mov     rbx, [r12]
0x18015df4c  lea     rcx, [rbp+170h+var_1E0]
0x18015df50  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015df55  mov     [rsp+270h+var_250], 1; int
0x18015df5d  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18015df61  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18015df65  mov     rdx, rsi; context
0x18015df68  mov     rcx, rbx; this
0x18015df6b  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015df70  mov     ebx, eax
0x18015df72  xor     r12d, r12d
0x18015df75  test    eax, eax
0x18015df77  jz      short loc_18015DFBF
0x18015df79  mov     eax, cs:dword_18039EB68
0x18015df7f  cmp     eax, 2
0x18015df82  jbe     loc_18015E0ED
0x18015df88  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18015df8b  mov     dword ptr [rbp+170h+var_1C8], 5FDh
0x18015df92  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015df99  mov     [rbp+170h+var_1F0], rax
0x18015df9d  lea     rax, [rbp+170h+var_1D8]
0x18015dfa1  mov     [rsp+270h+var_240], rax
0x18015dfa6  lea     rax, [rbp+170h+var_1C8]
0x18015dfaa  mov     [rsp+270h+var_248], rax
0x18015dfaf  lea     rax, [rbp+170h+var_1F0]
0x18015dfb3  lea     rdx, byte_18035DA9B
0x18015dfba  jmp     loc_18015E0E3
0x18015dfbf  lea     r8, [rbp+170h+instance]; instance
0x18015dfc6  lea     rdx, SPACES_StoragePool_RemovePhysicalDisk_rtti; methodDecl
0x18015dfcd  mov     rcx, rsi; context
0x18015dfd0  call    MI_Context_ConstructParameters
0x18015dfd5  mov     ebx, eax
0x18015dfd7  test    eax, eax
0x18015dfd9  jz      short loc_18015E021
0x18015dfdb  mov     eax, cs:dword_18039EB68
0x18015dfe1  cmp     eax, 2
0x18015dfe4  jbe     loc_18015E0ED
0x18015dfea  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18015dfed  mov     dword ptr [rbp+170h+var_1B8], 605h
0x18015dff4  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015dffb  mov     [rbp+170h+var_1F0], rax
0x18015dfff  lea     rax, [rbp+170h+var_1C0]
0x18015e003  mov     [rsp+270h+var_240], rax
0x18015e008  lea     rax, [rbp+170h+var_1B8]
0x18015e00c  mov     [rsp+270h+var_248], rax
0x18015e011  lea     rax, [rbp+170h+var_1F0]
0x18015e015  lea     rdx, byte_18035BF3F
0x18015e01c  jmp     loc_18015E0E3
0x18015e021  mov     rcx, [rbp+170h+var_1E0]
0x18015e025  mov     rax, [rcx]
0x18015e028  lea     rdx, [rbp+170h+instance]
0x18015e02f  mov     qword ptr [rsp+270h+var_250], rdx
0x18015e034  mov     r9, r15
0x18015e037  mov     r8, rsi
0x18015e03a  mov     edx, 0B0004h
0x18015e03f  mov     rax, [rax+30h]
0x18015e043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015e048  mov     ebx, eax
0x18015e04a  test    eax, eax
0x18015e04c  jz      short loc_18015E091
0x18015e04e  mov     eax, cs:dword_18039EB68
0x18015e054  cmp     eax, 2
0x18015e057  jbe     loc_18015E0ED
0x18015e05d  mov     [rbp+170h+var_1E8], ebx
0x18015e060  mov     dword ptr [rbp+170h+var_1D0], 610h
0x18015e067  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e06e  mov     [rbp+170h+var_1F0], rax
0x18015e072  lea     rax, [rbp+170h+var_1E8]
0x18015e076  mov     [rsp+270h+var_240], rax
0x18015e07b  lea     rax, [rbp+170h+var_1D0]
0x18015e07f  mov     [rsp+270h+var_248], rax
0x18015e084  lea     rax, [rbp+170h+var_1F0]
0x18015e088  lea     rdx, byte_18035C6F7
0x18015e08f  jmp     short loc_18015E0E3
0x18015e091  lea     rdx, [rbp+170h+instance]
0x18015e098  mov     rcx, rsi; self
0x18015e09b  call    MI_Instance_Destruct
0x18015e0a0  mov     ebx, eax
0x18015e0a2  test    eax, eax
0x18015e0a4  jz      short loc_18015E0ED
0x18015e0a6  mov     eax, cs:dword_18039EB68
0x18015e0ac  cmp     eax, 2
0x18015e0af  jbe     short loc_18015E0ED
0x18015e0b1  mov     [rbp+170h+var_1E4], ebx
0x18015e0b4  mov     dword ptr [rbp+170h+var_1F0], 618h
0x18015e0bb  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e0c2  mov     [rbp+170h+var_1D0], rax
0x18015e0c6  lea     rax, [rbp+170h+var_1E4]
0x18015e0ca  mov     [rsp+270h+var_240], rax
0x18015e0cf  lea     rax, [rbp+170h+var_1F0]
0x18015e0d3  mov     [rsp+270h+var_248], rax
0x18015e0d8  lea     rax, [rbp+170h+var_1D0]
0x18015e0dc  lea     rdx, byte_18035D119
0x18015e0e3  mov     qword ptr [rsp+270h+var_250], rax
0x18015e0e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015e0ed  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015e0f4  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015e0f9  jmp     short loc_18015E0FE
0x18015e0fb  xor     r12d, r12d
0x18015e0fe  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015e102  mov     [rsp+270h+var_248], r12; unsigned __int16 *
0x18015e107  mov     [rsp+270h+var_250], ebx; enum _MI_Result
0x18015e10b  lea     r9, [rbp+170h+var_B0]; struct _MI_ConstUint32Field *
0x18015e112  mov     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x18015e116  mov     rcx, [rbp+170h+var_1A8]; unsigned __int16 *
0x18015e11a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015e11f  test    r13d, r13d
0x18015e122  jnz     loc_18015E28E
0x18015e128  lea     rcx, [rbp+170h+var_198]; this
0x18015e12c  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015e131  mov     eax, cs:dword_18039EB68
0x18015e137  cmp     eax, 5
0x18015e13a  jbe     loc_18015E28E
0x18015e140  mov     rdx, 400000000000h
0x18015e14a  lea     rcx, dword_18039EB68
0x18015e151  call    _tlgKeywordOn
0x18015e156  test    al, al
0x18015e158  jz      loc_18015E28E
0x18015e15e  cmp     [r15+58h], r12b
0x18015e162  jz      short loc_18015E16A
0x18015e164  mov     eax, [r15+50h]
0x18015e168  jmp     short loc_18015E16D
0x18015e16a  mov     eax, r12d
0x18015e16d  mov     dword ptr [rbp+170h+var_1F0], eax
0x18015e170  cmp     [rbp+170h+var_88], r12b
0x18015e177  jz      short loc_18015E1B4
0x18015e179  mov     rax, [rbp+170h+var_90]
0x18015e180  movups  xmm0, xmmword ptr [rax]
0x18015e183  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18015e187  movups  xmm1, xmmword ptr [rax+10h]
0x18015e18b  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18015e18f  movups  xmm0, xmmword ptr [rax+20h]
0x18015e193  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18015e197  movups  xmm1, xmmword ptr [rax+30h]
0x18015e19b  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18015e19f  xor     r8d, r8d; unsigned __int16 *
0x18015e1a2  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18015e1a6  lea     rcx, name; "ObjectId"
0x18015e1ad  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015e1b2  jmp     short loc_18015E1B7
0x18015e1b4  mov     rax, r12
0x18015e1b7  mov     [rbp+170h+var_1A8], rax
0x18015e1bb  mov     [rbp+170h+var_1B0], r12
0x18015e1bf  mov     [rbp+170h+var_1B8], r12
0x18015e1c3  mov     rax, [rbp+170h+var_190]
0x18015e1c7  sub     rax, [rbp+170h+var_198]
0x18015e1cb  imul    rax, 3E8h
0x18015e1d2  xor     edx, edx
0x18015e1d4  div     [rbp+170h+var_188]
0x18015e1d8  mov     [rbp+170h+var_1C0], rax
0x18015e1dc  mov     [rbp+170h+var_1E4], ebx
0x18015e1df  mov     al, [rbp+170h+var_B0.exists]
0x18015e1e5  neg     al
0x18015e1e7  sbb     ecx, ecx
0x18015e1e9  and     ecx, [rbp+170h+var_B0.value]
0x18015e1ef  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18015e1f2  mov     [rbp+170h+var_1E8], r14d
0x18015e1f6  cmp     [rdi+48h], r12b
0x18015e1fa  jz      short loc_18015E202
0x18015e1fc  mov     rax, [rdi+40h]
0x18015e200  jmp     short loc_18015E205
0x18015e202  mov     rax, r12
0x18015e205  mov     [rbp+170h+var_1C8], rax
0x18015e209  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18015e210  mov     [rbp+170h+var_1D8], rax
0x18015e214  lea     rax, aStoragepool_0; "StoragePool"
0x18015e21b  mov     [rbp+170h+var_1A0], rax
0x18015e21f  lea     rax, [rbp+170h+var_1F0]
0x18015e223  mov     [rsp+270h+var_200], rax
0x18015e228  lea     rax, [rbp+170h+var_1A8]
0x18015e22c  mov     [rsp+270h+var_208], rax
0x18015e231  lea     rax, [rbp+170h+var_1B0]
0x18015e235  mov     [rsp+270h+var_210], rax
0x18015e23a  lea     rax, [rbp+170h+var_1B8]
0x18015e23e  mov     [rsp+270h+var_218], rax
0x18015e243  lea     rax, [rbp+170h+var_1C0]
0x18015e247  mov     [rsp+270h+var_220], rax
0x18015e24c  lea     rax, [rbp+170h+var_1E4]
0x18015e250  mov     [rsp+270h+var_228], rax
0x18015e255  lea     rax, [rbp+170h+var_1D0]
0x18015e259  mov     [rsp+270h+var_230], rax
0x18015e25e  lea     rax, [rbp+170h+var_1E8]
0x18015e262  mov     [rsp+270h+var_238], rax
0x18015e267  lea     rax, [rbp+170h+var_1C8]
0x18015e26b  mov     [rsp+270h+var_240], rax
0x18015e270  lea     rax, [rbp+170h+var_1D8]
0x18015e274  mov     [rsp+270h+var_248], rax
0x18015e279  lea     rax, [rbp+170h+var_1A0]
0x18015e27d  mov     qword ptr [rsp+270h+var_250], rax
0x18015e282  lea     rdx, byte_18035CEEF
0x18015e289  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@3445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18015e28e  lea     rcx, [rbp+170h+instance]; self
0x18015e295  call    MI_Instance_Destruct
0x18015e29a  mov     eax, cs:dword_18039EB68
0x18015e2a0  cmp     eax, 5
0x18015e2a3  jbe     short loc_18015E2D5
0x18015e2a5  mov     dword ptr [rbp+170h+var_1F0], 63Ah
0x18015e2ac  lea     rax, aSpacesStoragep_20; "SPACES_StoragePool_Invoke_RemovePhysica"...
  ... truncated ...
```
