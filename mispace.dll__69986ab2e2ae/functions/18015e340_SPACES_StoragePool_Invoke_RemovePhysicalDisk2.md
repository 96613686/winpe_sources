# SPACES_StoragePool_Invoke_RemovePhysicalDisk2

- ea: `0x18015e340`
- end: `0x18015e97b`
- name: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- size: `1595`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
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
- `0x180021dcc`
- `0x1800226ac`
- `0x180023e18`
- `0x180025e78`
- `0x180081a70`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18015e340`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e3ae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e419`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e944`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e3ae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e419`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015e944`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015e3d7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015e3d7`

## string_xrefs

- `0x18015e850`: `RemovePhysicalDisk`
- `0x18015e42b`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015e541`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015e59e`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015e600`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015e6af`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015e784`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015e8f3`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_RemovePhysicalDisk2(
        CSpProvider **a1,
        MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  int v11; // r8d
  int v12; // r9d
  enum _MI_Result v13; // r15d
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
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  const unsigned __int16 *v35; // rax
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  const char *v41; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v42; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v43; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v44; // [rsp+90h] [rbp-70h] BYREF
  const char *v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v51; // [rsp+C8h] [rbp-38h] BYREF
  const char *v52; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v53[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v56; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  int v59; // [rsp+1C0h] [rbp+C0h]
  char v60; // [rsp+1C4h] [rbp+C4h]
  struct _MI_Instance *v61; // [rsp+1E0h] [rbp+E0h]
  char v62; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v64; // [rsp+210h] [rbp+110h]
  GUID v65; // [rsp+220h] [rbp+120h] BYREF

  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v64 = ActivityId;
  v65 = ActivityId;
  EventActivityIdControl(4u, &v65);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v45) = 1742;
    v41 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_RemovePhysicalDisk2",
      (unsigned int)&word_18035C61E,
      v11,
      v12,
      (__int64)&v41,
      (__int64)&v45);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v54 = 0;
  v55 = 0;
  v44 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v44);
  v44 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v53);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v53);
    if ( !*(_BYTE *)(a6 + 72)
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64))) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v54) = 11;
    *((_QWORD *)&v54 + 1) = *(_QWORD *)(a6 + 64);
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v44);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v54, &v44, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v45) = v15;
        LODWORD(v47) = 1774;
        v41 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_18035C50D,
          v18,
          v19,
          (__int64)&v41,
          (__int64)&v47,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_RemovePhysicalDisk2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v50) = v15;
          LODWORD(v51) = 1793;
          v41 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)&word_18035B4AE,
            v24,
            v25,
            (__int64)&v41,
            (__int64)&v51,
            (__int64)&v50);
        }
      }
      else
      {
        if ( v13 && *(_BYTE *)(a7 + 88) && *(_DWORD *)(a7 + 80) > 0x200u )
        {
          v59 = 5;
          v60 = 1;
          PostExtendedStatus(a2, &instance, 0x8022u, 1u, L"512");
        }
        else
        {
          v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v44 + 48LL))(
                  v44,
                  720913,
                  a2,
                  a7,
                  &instance);
          if ( v15 )
          {
            if ( (unsigned int)dword_18039EB68 > 2 )
            {
              v42 = v15;
              LODWORD(v46) = 1820;
              v41 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v32,
                (unsigned int)&dword_18035E564,
                v33,
                v34,
                (__int64)&v41,
                (__int64)&v46,
                (__int64)&v42);
            }
            goto LABEL_26;
          }
        }
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_18039EB68 > 2 )
        {
          v43 = v15;
          LODWORD(v41) = 1829;
          v46 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)byte_18035CDC5,
            v27,
            v28,
            (__int64)&v46,
            (__int64)&v41,
            (__int64)&v43);
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v48) = 7;
        LODWORD(v49) = 1785;
        v41 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)byte_18035BD33,
          v21,
          v22,
          (__int64)&v41,
          (__int64)&v49,
          (__int64)&v48);
      }
    }
LABEL_26:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v53);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 88) )
          v31 = *(_DWORD *)(a7 + 80);
        else
          v31 = 0;
        LODWORD(v41) = v31;
        if ( v62 )
        {
          v56 = *v61;
          v35 = SmMIGetString(L"ObjectId", &v56, 0);
        }
        else
        {
          v35 = 0;
        }
        v51 = v35;
        v50 = 0;
        v49 = 0;
        v48 = (unsigned __int64)(1000LL * (v53[1] - v53[0])) / v53[2];
        v43 = v15;
        LODWORD(v46) = v60 != 0 ? v59 : 0;
        v42 = v13;
        if ( *(_BYTE *)(a6 + 72) )
          v36 = *(_QWORD *)(a6 + 64);
        else
          v36 = 0;
        v47 = v36;
        v45 = "RemovePhysicalDisk";
        v52 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v60 != 0 ? v59 : 0,
          (unsigned int)&byte_18035C977,
          v29,
          v30,
          (__int64)&v52,
          (__int64)&v45,
          (__int64)&v47,
          (__int64)&v42,
          (__int64)&v46,
          (__int64)&v43,
          (__int64)&v48,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v41);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v41) = 1857;
    v52 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)byte_18035C323,
      v38,
      v39,
      (__int64)&v52,
      (__int64)&v41);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v53);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v44);
  return EventActivityIdControl(4u, &v65);
}

```

## disassembly

```asm
0x18015e340  mov     [rsp-8+arg_10], rbx
0x18015e345  push    rbp
0x18015e346  push    rsi
0x18015e347  push    rdi
0x18015e348  push    r12
0x18015e34a  push    r13
0x18015e34c  push    r14
0x18015e34e  push    r15
0x18015e350  lea     rbp, [rsp-140h]
0x18015e358  sub     rsp, 240h
0x18015e35f  mov     rax, cs:__security_cookie
0x18015e366  xor     rax, rsp
0x18015e369  mov     [rbp+170h+var_40], rax
0x18015e370  mov     rdi, rdx
0x18015e373  mov     r12, rcx
0x18015e376  mov     r14, [rbp+170h+arg_28]
0x18015e37d  mov     rsi, [rbp+170h+arg_30]
0x18015e384  xorps   xmm0, xmm0
0x18015e387  xor     eax, eax
0x18015e389  movups  xmmword ptr [rbp+170h+value], xmm0
0x18015e38d  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18015e391  mov     qword ptr [rbp+170h+value+20h], rax
0x18015e395  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015e39c  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18015e3a4  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18015e3ab  lea     ecx, [rax+1]; ControlCode
0x18015e3ae  call    cs:__imp_EventActivityIdControl
0x18015e3b5  nop     dword ptr [rax+rax+00h]
0x18015e3ba  lea     r9, [rbp+170h+value]; value
0x18015e3be  mov     rcx, rdi; context
0x18015e3c1  call    MI_Context_GetCustomOption_1
0x18015e3c6  xor     ebx, ebx
0x18015e3c8  test    eax, eax
0x18015e3ca  jnz     short loc_18015E3E3
0x18015e3cc  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18015e3d3  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18015e3d7  call    cs:__imp_CLSIDFromString
0x18015e3de  nop     dword ptr [rax+rax+00h]
0x18015e3e3  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18015e3ea  mov     [rbp+170h+var_60], rcx
0x18015e3f1  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18015e3f8  mov     [rbp+170h+var_58], rax
0x18015e3ff  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18015e406  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18015e40d  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18015e414  mov     ecx, 4; ControlCode
0x18015e419  call    cs:__imp_EventActivityIdControl
0x18015e420  nop     dword ptr [rax+rax+00h]
0x18015e425  mov     eax, cs:dword_18039EB68
0x18015e42b  lea     rcx, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e432  cmp     eax, 5
0x18015e435  jbe     short loc_18015E460
0x18015e437  mov     dword ptr [rbp+170h+var_1D8], 6CEh
0x18015e43e  mov     [rbp+170h+var_1F0], rcx
0x18015e442  lea     rax, [rbp+170h+var_1D8]
0x18015e446  mov     [rsp+270h+var_248], rax
0x18015e44b  lea     rax, [rbp+170h+var_1F0]
0x18015e44f  mov     qword ptr [rsp+270h+var_250], rax
0x18015e454  lea     rdx, word_18035C61E
0x18015e45b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015e460  mov     [rbp+170h+instance.ft], rbx
0x18015e467  xor     edx, edx; Val
0x18015e469  lea     r8d, [rdx+78h]; Size
0x18015e46d  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18015e474  call    memset_0
0x18015e479  xorps   xmm0, xmm0
0x18015e47c  xor     eax, eax
0x18015e47e  movups  [rbp+170h+var_178], xmm0
0x18015e482  mov     [rbp+170h+var_168], rax
0x18015e486  mov     [rbp+170h+var_1E0], rbx
0x18015e48a  lea     rcx, [rbp+170h+var_1E0]
0x18015e48e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015e493  mov     [rbp+170h+var_1E0], rbx
0x18015e497  mov     r15d, ebx
0x18015e49a  lea     rcx, [rbp+170h+var_198]; this
0x18015e49e  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015e4a3  mov     rcx, rdi; context
0x18015e4a6  call    WspIsRemoteRequest
0x18015e4ab  mov     r13d, eax
0x18015e4ae  test    eax, eax
0x18015e4b0  jnz     short loc_18015E4D5
0x18015e4b2  lea     rcx, [rbp+170h+var_198]; this
0x18015e4b6  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015e4bb  cmp     [r14+48h], bl
0x18015e4bf  jz      short loc_18015E4D2
0x18015e4c1  mov     rcx, [r14+40h]; unsigned __int16 *
0x18015e4c5  call    WspIsRemoteInstance
0x18015e4ca  test    al, al
0x18015e4cc  lea     r15d, [r13+1]
0x18015e4d0  jnz     short loc_18015E4D5
0x18015e4d2  mov     r15d, ebx
0x18015e4d5  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015e4dc  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015e4e1  mov     ebx, eax
0x18015e4e3  test    eax, eax
0x18015e4e5  jnz     loc_18015E6ED
0x18015e4eb  mov     dword ptr [rbp+170h+var_178], 0Bh
0x18015e4f2  mov     rax, [r14+40h]
0x18015e4f6  mov     qword ptr [rbp+170h+var_178+8], rax
0x18015e4fa  mov     rbx, [r12]
0x18015e4fe  lea     rcx, [rbp+170h+var_1E0]
0x18015e502  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015e507  mov     [rsp+270h+var_250], 1; int
0x18015e50f  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18015e513  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18015e517  mov     rdx, rdi; context
0x18015e51a  mov     rcx, rbx; this
0x18015e51d  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015e522  mov     ebx, eax
0x18015e524  test    eax, eax
0x18015e526  jz      short loc_18015E56E
0x18015e528  mov     eax, cs:dword_18039EB68
0x18015e52e  cmp     eax, 2
0x18015e531  jbe     loc_18015E6E1
0x18015e537  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18015e53a  mov     dword ptr [rbp+170h+var_1C8], 6EEh
0x18015e541  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e548  mov     [rbp+170h+var_1F0], rax
0x18015e54c  lea     rax, [rbp+170h+var_1D8]
0x18015e550  mov     [rsp+270h+var_240], rax
0x18015e555  lea     rax, [rbp+170h+var_1C8]
0x18015e559  mov     [rsp+270h+var_248], rax
0x18015e55e  lea     rax, [rbp+170h+var_1F0]
0x18015e562  lea     rdx, byte_18035C50D
0x18015e569  jmp     loc_18015E6D7
0x18015e56e  mov     r8, [r14+40h]
0x18015e572  mov     rdx, rdi
0x18015e575  mov     rcx, [r12]
0x18015e579  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18015e57e  test    eax, eax
0x18015e580  jnz     short loc_18015E5CB
0x18015e582  lea     ebx, [rax+7]
0x18015e585  mov     eax, cs:dword_18039EB68
0x18015e58b  cmp     eax, 2
0x18015e58e  jbe     loc_18015E6E1
0x18015e594  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18015e597  mov     dword ptr [rbp+170h+var_1B8], 6F9h
0x18015e59e  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e5a5  mov     [rbp+170h+var_1F0], rax
0x18015e5a9  lea     rax, [rbp+170h+var_1C0]
0x18015e5ad  mov     [rsp+270h+var_240], rax
0x18015e5b2  lea     rax, [rbp+170h+var_1B8]
0x18015e5b6  mov     [rsp+270h+var_248], rax
0x18015e5bb  lea     rax, [rbp+170h+var_1F0]
0x18015e5bf  lea     rdx, byte_18035BD33
0x18015e5c6  jmp     loc_18015E6D7
0x18015e5cb  lea     r8, [rbp+170h+instance]; instance
0x18015e5d2  lea     rdx, SPACES_StoragePool_RemovePhysicalDisk2_rtti; methodDecl
0x18015e5d9  mov     rcx, rdi; context
0x18015e5dc  call    MI_Context_ConstructParameters
0x18015e5e1  mov     ebx, eax
0x18015e5e3  test    eax, eax
0x18015e5e5  jz      short loc_18015E62D
0x18015e5e7  mov     eax, cs:dword_18039EB68
0x18015e5ed  cmp     eax, 2
0x18015e5f0  jbe     loc_18015E6E1
0x18015e5f6  mov     dword ptr [rbp+170h+var_1B0], ebx
0x18015e5f9  mov     dword ptr [rbp+170h+var_1A8], 701h
0x18015e600  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e607  mov     [rbp+170h+var_1F0], rax
0x18015e60b  lea     rax, [rbp+170h+var_1B0]
0x18015e60f  mov     [rsp+270h+var_240], rax
0x18015e614  lea     rax, [rbp+170h+var_1A8]
0x18015e618  mov     [rsp+270h+var_248], rax
0x18015e61d  lea     rax, [rbp+170h+var_1F0]
0x18015e621  lea     rdx, word_18035B4AE
0x18015e628  jmp     loc_18015E6D7
0x18015e62d  test    r15d, r15d
0x18015e630  jz      loc_18015E73A
0x18015e636  cmp     byte ptr [rsi+58h], 0
0x18015e63a  jz      loc_18015E73A
0x18015e640  cmp     dword ptr [rsi+50h], 200h
0x18015e647  jbe     loc_18015E73A
0x18015e64d  mov     [rbp+170h+var_B0], 5
0x18015e657  mov     [rbp+170h+var_AC], 1
0x18015e65e  lea     rax, a512; "512"
0x18015e665  mov     qword ptr [rsp+270h+var_250], rax
0x18015e66a  mov     r9d, 1; unsigned int
0x18015e670  mov     r8d, 8022h; unsigned int
0x18015e676  lea     rdx, [rbp+170h+instance]; struct _MI_Instance *
0x18015e67d  mov     rcx, rdi; struct _MI_Context *
0x18015e680  call    ?PostExtendedStatus@@YA_NPEAU_MI_Context@@PEAU_MI_Instance@@KIZZ; PostExtendedStatus(_MI_Context *,_MI_Instance *,ulong,uint,...)
0x18015e685  lea     rdx, [rbp+170h+instance]
0x18015e68c  mov     rcx, rdi; self
0x18015e68f  call    MI_Instance_Destruct
0x18015e694  mov     ebx, eax
0x18015e696  test    eax, eax
0x18015e698  jz      short loc_18015E6E1
0x18015e69a  mov     eax, cs:dword_18039EB68
0x18015e6a0  cmp     eax, 2
0x18015e6a3  jbe     short loc_18015E6E1
0x18015e6a5  mov     [rbp+170h+var_1E4], ebx
0x18015e6a8  mov     dword ptr [rbp+170h+var_1F0], 725h
0x18015e6af  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e6b6  mov     [rbp+170h+var_1D0], rax
0x18015e6ba  lea     rax, [rbp+170h+var_1E4]
0x18015e6be  mov     [rsp+270h+var_240], rax
0x18015e6c3  lea     rax, [rbp+170h+var_1F0]
0x18015e6c7  mov     [rsp+270h+var_248], rax
0x18015e6cc  lea     rax, [rbp+170h+var_1D0]
0x18015e6d0  lea     rdx, byte_18035CDC5
0x18015e6d7  mov     qword ptr [rsp+270h+var_250], rax
0x18015e6dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015e6e1  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015e6e8  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015e6ed  xor     r12d, r12d
0x18015e6f0  test    r13d, r13d
0x18015e6f3  jnz     loc_18015E8D5
0x18015e6f9  lea     rcx, [rbp+170h+var_198]; this
0x18015e6fd  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015e702  mov     eax, cs:dword_18039EB68
0x18015e708  cmp     eax, 5
0x18015e70b  jbe     loc_18015E8D5
0x18015e711  mov     rdx, 400000000000h
0x18015e71b  lea     rcx, dword_18039EB68
0x18015e722  call    _tlgKeywordOn
0x18015e727  test    al, al
0x18015e729  jz      loc_18015E8D5
0x18015e72f  cmp     [rsi+58h], r12b
0x18015e733  jz      short loc_18015E7B1
0x18015e735  mov     eax, [rsi+50h]
0x18015e738  jmp     short loc_18015E7B4
0x18015e73a  mov     rcx, [rbp+170h+var_1E0]
0x18015e73e  mov     rax, [rcx]
0x18015e741  lea     rdx, [rbp+170h+instance]
0x18015e748  mov     qword ptr [rsp+270h+var_250], rdx
0x18015e74d  mov     r9, rsi
0x18015e750  mov     r8, rdi
0x18015e753  mov     edx, 0B0011h
0x18015e758  mov     rax, [rax+30h]
0x18015e75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015e761  mov     ebx, eax
0x18015e763  test    eax, eax
0x18015e765  jz      loc_18015E685
0x18015e76b  mov     eax, cs:dword_18039EB68
0x18015e771  cmp     eax, 2
0x18015e774  jbe     loc_18015E6E1
0x18015e77a  mov     [rbp+170h+var_1E8], ebx
0x18015e77d  mov     dword ptr [rbp+170h+var_1D0], 71Ch
0x18015e784  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015e78b  mov     [rbp+170h+var_1F0], rax
0x18015e78f  lea     rax, [rbp+170h+var_1E8]
0x18015e793  mov     [rsp+270h+var_240], rax
0x18015e798  lea     rax, [rbp+170h+var_1D0]
0x18015e79c  mov     [rsp+270h+var_248], rax
0x18015e7a1  lea     rax, [rbp+170h+var_1F0]
0x18015e7a5  lea     rdx, dword_18035E564
0x18015e7ac  jmp     loc_18015E6D7
0x18015e7b1  mov     eax, r12d
0x18015e7b4  mov     dword ptr [rbp+170h+var_1F0], eax
0x18015e7b7  cmp     [rbp+170h+var_88], r12b
0x18015e7be  jz      short loc_18015E7FB
0x18015e7c0  mov     rax, [rbp+170h+var_90]
0x18015e7c7  movups  xmm0, xmmword ptr [rax]
0x18015e7ca  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18015e7ce  movups  xmm1, xmmword ptr [rax+10h]
0x18015e7d2  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18015e7d6  movups  xmm0, xmmword ptr [rax+20h]
0x18015e7da  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18015e7de  movups  xmm1, xmmword ptr [rax+30h]
0x18015e7e2  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18015e7e6  xor     r8d, r8d; unsigned __int16 *
0x18015e7e9  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18015e7ed  lea     rcx, name; "ObjectId"
0x18015e7f4  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015e7f9  jmp     short loc_18015E7FE
0x18015e7fb  mov     rax, r12
0x18015e7fe  mov     [rbp+170h+var_1A8], rax
0x18015e802  mov     [rbp+170h+var_1B0], r12
0x18015e806  mov     [rbp+170h+var_1B8], r12
0x18015e80a  mov     rax, [rbp+170h+var_190]
0x18015e80e  sub     rax, [rbp+170h+var_198]
0x18015e812  imul    rax, 3E8h
0x18015e819  xor     edx, edx
0x18015e81b  div     [rbp+170h+var_188]
0x18015e81f  mov     [rbp+170h+var_1C0], rax
0x18015e823  mov     [rbp+170h+var_1E4], ebx
0x18015e826  mov     al, [rbp+170h+var_AC]
0x18015e82c  neg     al
0x18015e82e  sbb     ecx, ecx
0x18015e830  and     ecx, [rbp+170h+var_B0]
0x18015e836  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18015e839  mov     [rbp+170h+var_1E8], r15d
0x18015e83d  cmp     [r14+48h], r12b
0x18015e841  jz      short loc_18015E849
0x18015e843  mov     rax, [r14+40h]
0x18015e847  jmp     short loc_18015E84C
0x18015e849  mov     rax, r12
0x18015e84c  mov     [rbp+170h+var_1C8], rax
0x18015e850  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18015e857  mov     [rbp+170h+var_1D8], rax
0x18015e85b  lea     rax, aStoragepool_0; "StoragePool"
0x18015e862  mov     [rbp+170h+var_1A0], rax
0x18015e866  lea     rax, [rbp+170h+var_1F0]
0x18015e86a  mov     [rsp+270h+var_200], rax
0x18015e86f  lea     rax, [rbp+170h+var_1A8]
0x18015e873  mov     [rsp+270h+var_208], rax
0x18015e878  lea     rax, [rbp+170h+var_1B0]
0x18015e87c  mov     [rsp+270h+var_210], rax
0x18015e881  lea     rax, [rbp+170h+var_1B8]
  ... truncated ...
```
