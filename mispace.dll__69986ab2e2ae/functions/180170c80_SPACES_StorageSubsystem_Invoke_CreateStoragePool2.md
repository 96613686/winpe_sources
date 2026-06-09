# SPACES_StorageSubsystem_Invoke_CreateStoragePool2

- ea: `0x180170c80`
- end: `0x180171311`
- name: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- size: `1681`
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
- `0x180170c80`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170cee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170d59`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801712da`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170cee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180170d59`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801712da`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180170d17`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180170d17`

## string_xrefs

- `0x1801711e6`: `CreateStoragePool`
- `0x180170d6b`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x180170e83`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x180170ee0`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x180170f42`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x180170ff4`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x1801710cc`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`
- `0x180171289`: `SPACES_StorageSubsystem_Invoke_CreateStoragePool2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StorageSubsystem_Invoke_CreateStoragePool2(
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
  const unsigned __int16 *v36; // rax
  __int64 v37; // rax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  const char *v42; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v43; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v44; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v45; // [rsp+90h] [rbp-70h] BYREF
  const char *v46; // [rsp+98h] [rbp-68h] BYREF
  const char *v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  const char *v50; // [rsp+B8h] [rbp-48h] BYREF
  const unsigned __int16 *v51; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v52; // [rsp+C8h] [rbp-38h] BYREF
  const char *v53; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v54[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v55; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v57; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  int v60; // [rsp+1C0h] [rbp+C0h]
  char v61; // [rsp+1C4h] [rbp+C4h]
  struct _MI_Instance *v62; // [rsp+270h] [rbp+170h]
  char v63; // [rsp+278h] [rbp+178h]
  struct _MI_Instance *v64; // [rsp+280h] [rbp+180h]
  char v65; // [rsp+288h] [rbp+188h]
  GUID ActivityId; // [rsp+2A0h] [rbp+1A0h] BYREF
  GUID v67; // [rsp+2B0h] [rbp+1B0h]
  GUID v68; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v67 = ActivityId;
  v68 = ActivityId;
  EventActivityIdControl(4u, &v68);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v46) = 255;
    v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StorageSubsystem_Invoke_CreateStoragePool2",
      (unsigned int)&byte_18036442F,
      v11,
      v12,
      (__int64)&v42,
      (__int64)&v46);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x118u);
  v55 = 0;
  v56 = 0;
  v45 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v45);
  v45 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v54);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v54);
    if ( !*(_BYTE *)(a6 + 72)
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64))) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v55) = 13;
    *((_QWORD *)&v55 + 1) = *(_QWORD *)(a6 + 64);
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v45);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v55, &v45, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v46) = v15;
        LODWORD(v48) = 287;
        v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)byte_180363D83,
          v18,
          v19,
          (__int64)&v42,
          (__int64)&v48,
          (__int64)&v46);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StorageSubsystem_CreateStoragePool2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v51) = v15;
          LODWORD(v52) = 306;
          v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)byte_180363891,
            v24,
            v25,
            (__int64)&v42,
            (__int64)&v52,
            (__int64)&v51);
        }
      }
      else
      {
        if ( v13 && *(_BYTE *)(a7 + 128) && *(_DWORD *)(a7 + 120) > 0x200u )
        {
          v60 = 5;
          v61 = 1;
          PostExtendedStatus(a2, &instance, 0x8022u, 1u, L"512");
        }
        else
        {
          v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v45 + 48LL))(
                  v45,
                  851978,
                  a2,
                  a7,
                  &instance);
          if ( v15 )
          {
            if ( (unsigned int)dword_18039EB68 > 2 )
            {
              v43 = v15;
              LODWORD(v47) = 333;
              v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v32,
                (unsigned int)&unk_180364BF8,
                v33,
                v34,
                (__int64)&v42,
                (__int64)&v47,
                (__int64)&v43);
            }
            goto LABEL_26;
          }
        }
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_18039EB68 > 2 )
        {
          v44 = v15;
          LODWORD(v42) = 342;
          v47 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)byte_180363D1D,
            v27,
            v28,
            (__int64)&v47,
            (__int64)&v42,
            (__int64)&v44);
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v49) = 7;
        LODWORD(v50) = 298;
        v42 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&word_18036372E,
          v21,
          v22,
          (__int64)&v42,
          (__int64)&v50,
          (__int64)&v49);
      }
    }
LABEL_26:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v54);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 128) )
          v31 = *(_DWORD *)(a7 + 120);
        else
          v31 = 0;
        LODWORD(v42) = v31;
        if ( v65 )
        {
          v57 = *v64;
          v35 = SmMIGetString(L"ObjectId", &v57, 0);
        }
        else
        {
          v35 = 0;
        }
        v52 = v35;
        if ( v63 )
        {
          v57 = *v62;
          v36 = SmMIGetString(L"ObjectId", &v57, 0);
        }
        else
        {
          v36 = 0;
        }
        v51 = v36;
        v50 = "StoragePool";
        v49 = (unsigned __int64)(1000LL * (v54[1] - v54[0])) / v54[2];
        v44 = v15;
        LODWORD(v47) = v61 != 0 ? v60 : 0;
        v43 = v13;
        if ( *(_BYTE *)(a6 + 72) )
          v37 = *(_QWORD *)(a6 + 64);
        else
          v37 = 0;
        v48 = v37;
        v46 = "CreateStoragePool";
        v53 = "StorageSubsystem";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v61 != 0 ? v60 : 0,
          (unsigned int)word_1803647FA,
          v29,
          v30,
          (__int64)&v53,
          (__int64)&v46,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v47,
          (__int64)&v44,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v52,
          (__int64)&v42);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v42) = 370;
    v53 = "SPACES_StorageSubsystem_Invoke_CreateStoragePool2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v38,
      (unsigned int)&word_180363D56,
      v39,
      v40,
      (__int64)&v53,
      (__int64)&v42);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v54);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v45);
  return EventActivityIdControl(4u, &v68);
}

```

## disassembly

```asm
0x180170c80  mov     [rsp-8+arg_10], rbx
0x180170c85  push    rbp
0x180170c86  push    rsi
0x180170c87  push    rdi
0x180170c88  push    r12
0x180170c8a  push    r13
0x180170c8c  push    r14
0x180170c8e  push    r15
0x180170c90  lea     rbp, [rsp-1E0h]
0x180170c98  sub     rsp, 2E0h
0x180170c9f  mov     rax, cs:__security_cookie
0x180170ca6  xor     rax, rsp
0x180170ca9  mov     [rbp+210h+var_40], rax
0x180170cb0  mov     rsi, rdx
0x180170cb3  mov     r12, rcx
0x180170cb6  mov     r14, [rbp+210h+arg_28]
0x180170cbd  mov     rdi, [rbp+210h+arg_30]
0x180170cc4  xorps   xmm0, xmm0
0x180170cc7  xor     eax, eax
0x180170cc9  movups  xmmword ptr [rbp+210h+value], xmm0
0x180170ccd  movups  xmmword ptr [rbp+210h+value+10h], xmm0
0x180170cd1  mov     qword ptr [rbp+210h+value+20h], rax
0x180170cd5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180170cdc  movdqu  xmmword ptr [rbp+210h+ActivityId.Data1], xmm0
0x180170ce4  lea     rdx, [rbp+210h+ActivityId]; ActivityId
0x180170ceb  lea     ecx, [rax+1]; ControlCode
0x180170cee  call    cs:__imp_EventActivityIdControl
0x180170cf5  nop     dword ptr [rax+rax+00h]
0x180170cfa  lea     r9, [rbp+210h+value]; value
0x180170cfe  mov     rcx, rsi; context
0x180170d01  call    MI_Context_GetCustomOption_1
0x180170d06  xor     ebx, ebx
0x180170d08  test    eax, eax
0x180170d0a  jnz     short loc_180170D23
0x180170d0c  lea     rdx, [rbp+210h+ActivityId]; pclsid
0x180170d13  mov     rcx, qword ptr [rbp+210h+value]; lpsz
0x180170d17  call    cs:__imp_CLSIDFromString
0x180170d1e  nop     dword ptr [rax+rax+00h]
0x180170d23  mov     rcx, qword ptr [rbp+210h+ActivityId.Data1]
0x180170d2a  mov     [rbp+210h+var_60], rcx
0x180170d31  mov     rax, qword ptr [rbp+210h+ActivityId.Data4]
0x180170d38  mov     [rbp+210h+var_58], rax
0x180170d3f  mov     qword ptr [rbp+210h+var_50.Data1], rcx
0x180170d46  mov     qword ptr [rbp+210h+var_50.Data4], rax
0x180170d4d  lea     rdx, [rbp+210h+var_50]; ActivityId
0x180170d54  mov     ecx, 4; ControlCode
0x180170d59  call    cs:__imp_EventActivityIdControl
0x180170d60  nop     dword ptr [rax+rax+00h]
0x180170d65  mov     eax, cs:dword_18039EB68
0x180170d6b  lea     rcx, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170d72  cmp     eax, 5
0x180170d75  jbe     short loc_180170DA0
0x180170d77  mov     dword ptr [rbp+210h+var_278], 0FFh
0x180170d7e  mov     [rbp+210h+var_290], rcx
0x180170d82  lea     rax, [rbp+210h+var_278]
0x180170d86  mov     [rsp+310h+var_2E8], rax
0x180170d8b  lea     rax, [rbp+210h+var_290]
0x180170d8f  mov     qword ptr [rsp+310h+var_2F0], rax
0x180170d94  lea     rdx, byte_18036442F
0x180170d9b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180170da0  mov     [rbp+210h+instance.ft], rbx
0x180170da7  xor     edx, edx; Val
0x180170da9  mov     r8d, 118h; Size
0x180170daf  lea     rcx, [rbp+210h+instance.classDecl]; void *
0x180170db6  call    memset_0
0x180170dbb  xorps   xmm0, xmm0
0x180170dbe  xor     eax, eax
0x180170dc0  movups  [rbp+210h+var_218], xmm0
0x180170dc4  mov     [rbp+210h+var_208], rax
0x180170dc8  mov     [rbp+210h+var_280], rbx
0x180170dcc  lea     rcx, [rbp+210h+var_280]
0x180170dd0  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180170dd5  mov     [rbp+210h+var_280], rbx
0x180170dd9  mov     r15d, ebx
0x180170ddc  lea     rcx, [rbp+210h+var_238]; this
0x180170de0  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180170de5  mov     rcx, rsi; context
0x180170de8  call    WspIsRemoteRequest
0x180170ded  mov     r13d, eax
0x180170df0  test    eax, eax
0x180170df2  jnz     short loc_180170E17
0x180170df4  lea     rcx, [rbp+210h+var_238]; this
0x180170df8  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180170dfd  cmp     [r14+48h], bl
0x180170e01  jz      short loc_180170E14
0x180170e03  mov     rcx, [r14+40h]; unsigned __int16 *
0x180170e07  call    WspIsRemoteInstance
0x180170e0c  test    al, al
0x180170e0e  lea     r15d, [r13+1]
0x180170e12  jnz     short loc_180170E17
0x180170e14  mov     r15d, ebx
0x180170e17  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180170e1e  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180170e23  mov     ebx, eax
0x180170e25  test    eax, eax
0x180170e27  jnz     loc_180171032
0x180170e2d  mov     dword ptr [rbp+210h+var_218], 0Dh
0x180170e34  mov     rax, [r14+40h]
0x180170e38  mov     qword ptr [rbp+210h+var_218+8], rax
0x180170e3c  mov     rbx, [r12]
0x180170e40  lea     rcx, [rbp+210h+var_280]
0x180170e44  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180170e49  mov     [rsp+310h+var_2F0], 1; int
0x180170e51  lea     r9, [rbp+210h+var_280]; struct ISpWmiObject **
0x180170e55  lea     r8, [rbp+210h+var_218]; struct _SP_OBJECT_ID *
0x180170e59  mov     rdx, rsi; context
0x180170e5c  mov     rcx, rbx; this
0x180170e5f  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180170e64  mov     ebx, eax
0x180170e66  test    eax, eax
0x180170e68  jz      short loc_180170EB0
0x180170e6a  mov     eax, cs:dword_18039EB68
0x180170e70  cmp     eax, 2
0x180170e73  jbe     loc_180171026
0x180170e79  mov     dword ptr [rbp+210h+var_278], ebx
0x180170e7c  mov     dword ptr [rbp+210h+var_268], 11Fh
0x180170e83  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170e8a  mov     [rbp+210h+var_290], rax
0x180170e8e  lea     rax, [rbp+210h+var_278]
0x180170e92  mov     [rsp+310h+var_2E0], rax
0x180170e97  lea     rax, [rbp+210h+var_268]
0x180170e9b  mov     [rsp+310h+var_2E8], rax
0x180170ea0  lea     rax, [rbp+210h+var_290]
0x180170ea4  lea     rdx, byte_180363D83
0x180170eab  jmp     loc_18017101C
0x180170eb0  mov     r8, [r14+40h]
0x180170eb4  mov     rdx, rsi
0x180170eb7  mov     rcx, [r12]
0x180170ebb  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x180170ec0  test    eax, eax
0x180170ec2  jnz     short loc_180170F0D
0x180170ec4  lea     ebx, [rax+7]
0x180170ec7  mov     eax, cs:dword_18039EB68
0x180170ecd  cmp     eax, 2
0x180170ed0  jbe     loc_180171026
0x180170ed6  mov     dword ptr [rbp+210h+var_260], ebx
0x180170ed9  mov     dword ptr [rbp+210h+var_258], 12Ah
0x180170ee0  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170ee7  mov     [rbp+210h+var_290], rax
0x180170eeb  lea     rax, [rbp+210h+var_260]
0x180170eef  mov     [rsp+310h+var_2E0], rax
0x180170ef4  lea     rax, [rbp+210h+var_258]
0x180170ef8  mov     [rsp+310h+var_2E8], rax
0x180170efd  lea     rax, [rbp+210h+var_290]
0x180170f01  lea     rdx, word_18036372E
0x180170f08  jmp     loc_18017101C
0x180170f0d  lea     r8, [rbp+210h+instance]; instance
0x180170f14  lea     rdx, SPACES_StorageSubsystem_CreateStoragePool2_rtti; methodDecl
0x180170f1b  mov     rcx, rsi; context
0x180170f1e  call    MI_Context_ConstructParameters
0x180170f23  mov     ebx, eax
0x180170f25  test    eax, eax
0x180170f27  jz      short loc_180170F6F
0x180170f29  mov     eax, cs:dword_18039EB68
0x180170f2f  cmp     eax, 2
0x180170f32  jbe     loc_180171026
0x180170f38  mov     dword ptr [rbp+210h+var_250], ebx
0x180170f3b  mov     dword ptr [rbp+210h+var_248], 132h
0x180170f42  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170f49  mov     [rbp+210h+var_290], rax
0x180170f4d  lea     rax, [rbp+210h+var_250]
0x180170f51  mov     [rsp+310h+var_2E0], rax
0x180170f56  lea     rax, [rbp+210h+var_248]
0x180170f5a  mov     [rsp+310h+var_2E8], rax
0x180170f5f  lea     rax, [rbp+210h+var_290]
0x180170f63  lea     rdx, byte_180363891
0x180170f6a  jmp     loc_18017101C
0x180170f6f  test    r15d, r15d
0x180170f72  jz      loc_180171082
0x180170f78  cmp     byte ptr [rdi+80h], 0
0x180170f7f  jz      loc_180171082
0x180170f85  cmp     dword ptr [rdi+78h], 200h
0x180170f8c  jbe     loc_180171082
0x180170f92  mov     [rbp+210h+var_150], 5
0x180170f9c  mov     [rbp+210h+var_14C], 1
0x180170fa3  lea     rax, a512; "512"
0x180170faa  mov     qword ptr [rsp+310h+var_2F0], rax
0x180170faf  mov     r9d, 1; unsigned int
0x180170fb5  mov     r8d, 8022h; unsigned int
0x180170fbb  lea     rdx, [rbp+210h+instance]; struct _MI_Instance *
0x180170fc2  mov     rcx, rsi; struct _MI_Context *
0x180170fc5  call    ?PostExtendedStatus@@YA_NPEAU_MI_Context@@PEAU_MI_Instance@@KIZZ; PostExtendedStatus(_MI_Context *,_MI_Instance *,ulong,uint,...)
0x180170fca  lea     rdx, [rbp+210h+instance]
0x180170fd1  mov     rcx, rsi; self
0x180170fd4  call    MI_Instance_Destruct
0x180170fd9  mov     ebx, eax
0x180170fdb  test    eax, eax
0x180170fdd  jz      short loc_180171026
0x180170fdf  mov     eax, cs:dword_18039EB68
0x180170fe5  cmp     eax, 2
0x180170fe8  jbe     short loc_180171026
0x180170fea  mov     [rbp+210h+var_284], ebx
0x180170fed  mov     dword ptr [rbp+210h+var_290], 156h
0x180170ff4  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x180170ffb  mov     [rbp+210h+var_270], rax
0x180170fff  lea     rax, [rbp+210h+var_284]
0x180171003  mov     [rsp+310h+var_2E0], rax
0x180171008  lea     rax, [rbp+210h+var_290]
0x18017100c  mov     [rsp+310h+var_2E8], rax
0x180171011  lea     rax, [rbp+210h+var_270]
0x180171015  lea     rdx, byte_180363D1D
0x18017101c  mov     qword ptr [rsp+310h+var_2F0], rax
0x180171021  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180171026  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18017102d  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x180171032  xor     r12d, r12d
0x180171035  test    r13d, r13d
0x180171038  jnz     loc_18017126B
0x18017103e  lea     rcx, [rbp+210h+var_238]; this
0x180171042  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180171047  mov     eax, cs:dword_18039EB68
0x18017104d  cmp     eax, 5
0x180171050  jbe     loc_18017126B
0x180171056  mov     rdx, 400000000000h
0x180171060  lea     rcx, dword_18039EB68
0x180171067  call    _tlgKeywordOn
0x18017106c  test    al, al
0x18017106e  jz      loc_18017126B
0x180171074  cmp     [rdi+80h], r12b
0x18017107b  jz      short loc_1801710F9
0x18017107d  mov     eax, [rdi+78h]
0x180171080  jmp     short loc_1801710FC
0x180171082  mov     rcx, [rbp+210h+var_280]
0x180171086  mov     rax, [rcx]
0x180171089  lea     rdx, [rbp+210h+instance]
0x180171090  mov     qword ptr [rsp+310h+var_2F0], rdx
0x180171095  mov     r9, rdi
0x180171098  mov     r8, rsi
0x18017109b  mov     edx, 0D000Ah
0x1801710a0  mov     rax, [rax+30h]
0x1801710a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801710a9  mov     ebx, eax
0x1801710ab  test    eax, eax
0x1801710ad  jz      loc_180170FCA
0x1801710b3  mov     eax, cs:dword_18039EB68
0x1801710b9  cmp     eax, 2
0x1801710bc  jbe     loc_180171026
0x1801710c2  mov     [rbp+210h+var_288], ebx
0x1801710c5  mov     dword ptr [rbp+210h+var_270], 14Dh
0x1801710cc  lea     rax, aSpacesStorages_15; "SPACES_StorageSubsystem_Invoke_CreateSt"...
0x1801710d3  mov     [rbp+210h+var_290], rax
0x1801710d7  lea     rax, [rbp+210h+var_288]
0x1801710db  mov     [rsp+310h+var_2E0], rax
0x1801710e0  lea     rax, [rbp+210h+var_270]
0x1801710e4  mov     [rsp+310h+var_2E8], rax
0x1801710e9  lea     rax, [rbp+210h+var_290]
0x1801710ed  lea     rdx, unk_180364BF8
0x1801710f4  jmp     loc_18017101C
0x1801710f9  mov     eax, r12d
0x1801710fc  mov     dword ptr [rbp+210h+var_290], eax
0x1801710ff  cmp     [rbp+210h+var_88], r12b
0x180171106  jz      short loc_180171143
0x180171108  mov     rax, [rbp+210h+var_90]
0x18017110f  movups  xmm0, xmmword ptr [rax]
0x180171112  movaps  xmmword ptr [rbp+210h+var_200.ft], xmm0
0x180171116  movups  xmm1, xmmword ptr [rax+10h]
0x18017111a  movaps  xmmword ptr [rbp+210h+var_200.serverName], xmm1
0x18017111e  movups  xmm0, xmmword ptr [rax+20h]
0x180171122  movaps  xmmword ptr [rbp+210h+var_200.reserved], xmm0
0x180171126  movups  xmm1, xmmword ptr [rax+30h]
0x18017112a  movaps  xmmword ptr [rbp+210h+var_200.reserved+10h], xmm1
0x18017112e  xor     r8d, r8d; unsigned __int16 *
0x180171131  lea     rdx, [rbp+210h+var_200]; struct _MI_Instance
0x180171135  lea     rcx, name; "ObjectId"
0x18017113c  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180171141  jmp     short loc_180171146
0x180171143  mov     rax, r12
0x180171146  mov     [rbp+210h+var_248], rax
0x18017114a  cmp     [rbp+210h+var_98], r12b
0x180171151  jz      short loc_18017118E
0x180171153  mov     rax, [rbp+210h+var_A0]
0x18017115a  movups  xmm0, xmmword ptr [rax]
0x18017115d  movaps  xmmword ptr [rbp+210h+var_200.ft], xmm0
0x180171161  movups  xmm1, xmmword ptr [rax+10h]
0x180171165  movaps  xmmword ptr [rbp+210h+var_200.serverName], xmm1
0x180171169  movups  xmm0, xmmword ptr [rax+20h]
0x18017116d  movaps  xmmword ptr [rbp+210h+var_200.reserved], xmm0
0x180171171  movups  xmm1, xmmword ptr [rax+30h]
0x180171175  movaps  xmmword ptr [rbp+210h+var_200.reserved+10h], xmm1
0x180171179  xor     r8d, r8d; unsigned __int16 *
0x18017117c  lea     rdx, [rbp+210h+var_200]; struct _MI_Instance
0x180171180  lea     rcx, name; "ObjectId"
0x180171187  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18017118c  jmp     short loc_180171191
0x18017118e  mov     rax, r12
0x180171191  mov     [rbp+210h+var_250], rax
0x180171195  lea     rax, aStoragepool_0; "StoragePool"
0x18017119c  mov     [rbp+210h+var_258], rax
0x1801711a0  mov     rax, [rbp+210h+var_230]
0x1801711a4  sub     rax, [rbp+210h+var_238]
0x1801711a8  imul    rax, 3E8h
0x1801711af  xor     edx, edx
0x1801711b1  div     [rbp+210h+var_228]
0x1801711b5  mov     [rbp+210h+var_260], rax
0x1801711b9  mov     [rbp+210h+var_284], ebx
0x1801711bc  mov     al, [rbp+210h+var_14C]
0x1801711c2  neg     al
0x1801711c4  sbb     ecx, ecx
0x1801711c6  and     ecx, [rbp+210h+var_150]
0x1801711cc  mov     dword ptr [rbp+210h+var_270], ecx
  ... truncated ...
```
