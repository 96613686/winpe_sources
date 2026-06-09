# SPACES_StoragePool_Invoke_CreateVirtualDisk2

- ea: `0x18015a9b0`
- end: `0x18015afd3`
- name: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- size: `1571`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
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
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18015a9b0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015aa2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015aa98`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015af9c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015aa2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015aa98`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015af9c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015aa56`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015aa56`

## string_xrefs

- `0x18015aeb4`: `CreateVirtualDisk`
- `0x18015aaaa`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x18015abe5`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x18015ad1d`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x18015ad4c`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`
- `0x18015ad61`: `SPACES_StoragePool_Invoke_CreateVirtualDisk2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVirtualDisk2(
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
  unsigned __int16 *v28; // rax
  const MI_Char *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  const char **v34; // [rsp+30h] [rbp-D0h]
  const char *v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v37; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  const char *v43; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v44; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  const char *v46; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v47; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v48[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h]
  struct _MI_Instance v51; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v54; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v55; // [rsp+2D0h] [rbp+1D0h]
  char v56; // [rsp+2D8h] [rbp+1D8h]
  struct _MI_Instance *v57; // [rsp+2E0h] [rbp+1E0h]
  char v58; // [rsp+2E8h] [rbp+1E8h]
  GUID ActivityId; // [rsp+300h] [rbp+200h] BYREF
  GUID v60; // [rsp+310h] [rbp+210h]
  GUID v61; // [rsp+320h] [rbp+220h] BYREF

  v40 = a4;
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
    v36 = 256;
    v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVirtualDisk2",
      (unsigned int)&dword_18035B334,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x178u);
  v49 = 0;
  v50 = 0;
  v38 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  v38 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v48);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v48);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v49) = 11;
    *((_QWORD *)&v49 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v49, &v38, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v36 = v15;
        v41 = 288;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = byte_18035DC4D;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk2";
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
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVirtualDisk2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v45) = 307;
          v34 = (const char **)&v44;
          v20 = (const char **)&v45;
          v21 = (char *)&word_18035CFB6;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720916,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v35) = 326;
            v39 = "SPACES_StoragePool_Invoke_CreateVirtualDisk2";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&unk_18035CAB0,
              v23,
              v24,
              (__int64)&v39,
              (__int64)&v35,
              (__int64)&v37);
          }
          goto LABEL_27;
        }
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v46) = v15;
          LODWORD(v39) = 318;
          v34 = &v46;
          v20 = &v39;
          v21 = (char *)&dword_18035D52C;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v42) = 7;
        LODWORD(v43) = 299;
        v34 = &v42;
        v20 = &v43;
        v21 = &byte_18035DDFF;
        goto LABEL_13;
      }
    }
LABEL_27:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v40, v47, a6 + 4, &v54, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v48);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( v58 )
        {
          v51 = *v57;
          v27 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v27 = 0;
        }
        v40 = v27;
        if ( v56 )
        {
          v51 = *v55;
          v28 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v51, 0);
        }
        else
        {
          v28 = 0;
        }
        v47 = v28;
        v46 = "VirtualDisk";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateVirtualDisk";
        v42 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)&word_18035CDFE,
          v25,
          v26,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v35,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v40);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v35) = 359;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVirtualDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_18035B78B,
      v31,
      v32,
      (__int64)&v40,
      (__int64)&v35);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v48);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v38);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x18015a9b0  mov     [rsp-8+arg_10], rbx
0x18015a9b5  push    rbp
0x18015a9b6  push    rsi
0x18015a9b7  push    rdi
0x18015a9b8  push    r12
0x18015a9ba  push    r13
0x18015a9bc  push    r14
0x18015a9be  push    r15
0x18015a9c0  lea     rbp, [rsp-240h]
0x18015a9c8  sub     rsp, 340h
0x18015a9cf  mov     rax, cs:__security_cookie
0x18015a9d6  xor     rax, rsp
0x18015a9d9  mov     [rbp+270h+var_40], rax
0x18015a9e0  mov     [rbp+270h+var_2E0], r9
0x18015a9e4  mov     rsi, rdx
0x18015a9e7  mov     r15, rcx
0x18015a9ea  mov     rax, [rbp+270h+arg_20]
0x18015a9f1  mov     [rbp+270h+var_2A8], rax
0x18015a9f5  mov     rdi, [rbp+270h+arg_28]
0x18015a9fc  mov     r13, [rbp+270h+arg_30]
0x18015aa03  xorps   xmm0, xmm0
0x18015aa06  xor     eax, eax
0x18015aa08  movups  xmmword ptr [rbp+270h+value], xmm0
0x18015aa0c  movups  xmmword ptr [rbp+270h+value+10h], xmm0
0x18015aa10  mov     qword ptr [rbp+270h+value+20h], rax
0x18015aa14  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015aa1b  movdqu  xmmword ptr [rbp+270h+ActivityId.Data1], xmm0
0x18015aa23  lea     rdx, [rbp+270h+ActivityId]; ActivityId
0x18015aa2a  lea     ecx, [rax+1]; ControlCode
0x18015aa2d  call    cs:__imp_EventActivityIdControl
0x18015aa34  nop     dword ptr [rax+rax+00h]
0x18015aa39  lea     r9, [rbp+270h+value]; value
0x18015aa3d  mov     rcx, rsi; context
0x18015aa40  call    MI_Context_GetCustomOption_1
0x18015aa45  xor     ebx, ebx
0x18015aa47  test    eax, eax
0x18015aa49  jnz     short loc_18015AA62
0x18015aa4b  lea     rdx, [rbp+270h+ActivityId]; pclsid
0x18015aa52  mov     rcx, qword ptr [rbp+270h+value]; lpsz
0x18015aa56  call    cs:__imp_CLSIDFromString
0x18015aa5d  nop     dword ptr [rax+rax+00h]
0x18015aa62  mov     rcx, qword ptr [rbp+270h+ActivityId.Data1]
0x18015aa69  mov     [rbp+270h+var_60], rcx
0x18015aa70  mov     rax, qword ptr [rbp+270h+ActivityId.Data4]
0x18015aa77  mov     [rbp+270h+var_58], rax
0x18015aa7e  mov     qword ptr [rbp+270h+var_50.Data1], rcx
0x18015aa85  mov     qword ptr [rbp+270h+var_50.Data4], rax
0x18015aa8c  lea     rdx, [rbp+270h+var_50]; ActivityId
0x18015aa93  mov     ecx, 4; ControlCode
0x18015aa98  call    cs:__imp_EventActivityIdControl
0x18015aa9f  nop     dword ptr [rax+rax+00h]
0x18015aaa4  mov     eax, cs:dword_18039EB68
0x18015aaaa  lea     rcx, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015aab1  cmp     eax, 5
0x18015aab4  jbe     short loc_18015AAE3
0x18015aab6  mov     [rsp+370h+var_2F8], 100h
0x18015aabe  mov     [rsp+370h+var_300], rcx
0x18015aac3  lea     rax, [rsp+370h+var_2F8]
0x18015aac8  mov     [rsp+370h+var_348], rax
0x18015aacd  lea     rax, [rsp+370h+var_300]
0x18015aad2  mov     qword ptr [rsp+370h+var_350], rax
0x18015aad7  lea     rdx, dword_18035B334
0x18015aade  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015aae3  mov     [rbp+270h+instance.ft], rbx
0x18015aaea  xor     edx, edx; Val
0x18015aaec  mov     r8d, 178h; Size
0x18015aaf2  lea     rcx, [rbp+270h+instance.classDecl]; void *
0x18015aaf9  call    memset_0
0x18015aafe  xorps   xmm0, xmm0
0x18015ab01  xor     eax, eax
0x18015ab03  movups  [rbp+270h+var_280], xmm0
0x18015ab07  mov     [rbp+270h+var_270], rax
0x18015ab0b  mov     [rbp+270h+var_2F0], rbx
0x18015ab0f  lea     rcx, [rbp+270h+var_2F0]
0x18015ab13  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015ab18  mov     [rbp+270h+var_2F0], rbx
0x18015ab1c  mov     r14d, ebx
0x18015ab1f  lea     rcx, [rbp+270h+var_2A0]; this
0x18015ab23  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015ab28  mov     rcx, rsi; context
0x18015ab2b  call    WspIsRemoteRequest
0x18015ab30  mov     r12d, eax
0x18015ab33  test    eax, eax
0x18015ab35  jnz     short loc_18015AB5A
0x18015ab37  lea     rcx, [rbp+270h+var_2A0]; this
0x18015ab3b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015ab40  cmp     [rdi+48h], bl
0x18015ab43  jz      short loc_18015AB57
0x18015ab45  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015ab49  call    WspIsRemoteInstance
0x18015ab4e  test    al, al
0x18015ab50  lea     r14d, [r12+1]
0x18015ab55  jnz     short loc_18015AB5A
0x18015ab57  mov     r14d, ebx
0x18015ab5a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015ab61  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015ab66  mov     ebx, eax
0x18015ab68  test    eax, eax
0x18015ab6a  jnz     loc_18015AD61
0x18015ab70  mov     dword ptr [rbp+270h+var_280], 0Bh
0x18015ab77  mov     rax, [rdi+40h]
0x18015ab7b  mov     qword ptr [rbp+270h+var_280+8], rax
0x18015ab7f  mov     rbx, [r15]
0x18015ab82  lea     rcx, [rbp+270h+var_2F0]
0x18015ab86  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015ab8b  mov     [rsp+370h+var_350], 1; int
0x18015ab93  lea     r9, [rbp+270h+var_2F0]; struct ISpWmiObject **
0x18015ab97  lea     r8, [rbp+270h+var_280]; struct _SP_OBJECT_ID *
0x18015ab9b  mov     rdx, rsi; context
0x18015ab9e  mov     rcx, rbx; this
0x18015aba1  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015aba6  mov     ebx, eax
0x18015aba8  test    eax, eax
0x18015abaa  jz      short loc_18015AC00
0x18015abac  mov     eax, cs:dword_18039EB68
0x18015abb2  cmp     eax, 2
0x18015abb5  jbe     loc_18015AD4C
0x18015abbb  mov     [rsp+370h+var_2F8], ebx
0x18015abbf  mov     [rbp+270h+var_2D8], 120h
0x18015abc6  lea     rax, [rsp+370h+var_2F8]
0x18015abcb  mov     [rsp+370h+var_340], rax
0x18015abd0  lea     rax, [rbp+270h+var_2D8]
0x18015abd4  lea     rdx, byte_18035DC4D
0x18015abdb  mov     [rsp+370h+var_348], rax
0x18015abe0  lea     rax, [rsp+370h+var_300]
0x18015abe5  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015abec  mov     [rsp+370h+var_300], r13
0x18015abf1  mov     qword ptr [rsp+370h+var_350], rax
0x18015abf6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015abfb  jmp     loc_18015AD53
0x18015ac00  mov     r8, [rdi+40h]
0x18015ac04  mov     rdx, rsi
0x18015ac07  mov     rcx, [r15]
0x18015ac0a  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18015ac0f  cmp     eax, 1
0x18015ac12  jnb     short loc_18015AC48
0x18015ac14  mov     ebx, 7
0x18015ac19  mov     eax, cs:dword_18039EB68
0x18015ac1f  cmp     eax, 2
0x18015ac22  jbe     loc_18015AD4C
0x18015ac28  mov     dword ptr [rbp+270h+var_2D0], ebx
0x18015ac2b  mov     dword ptr [rbp+270h+var_2C8], 12Bh
0x18015ac32  lea     rax, [rbp+270h+var_2D0]
0x18015ac36  mov     [rsp+370h+var_340], rax
0x18015ac3b  lea     rax, [rbp+270h+var_2C8]
0x18015ac3f  lea     rdx, byte_18035DDFF
0x18015ac46  jmp     short loc_18015ABDB
0x18015ac48  lea     r8, [rbp+270h+instance]; instance
0x18015ac4f  lea     rdx, SPACES_StoragePool_CreateVirtualDisk2_rtti; methodDecl
0x18015ac56  mov     rcx, rsi; context
0x18015ac59  call    MI_Context_ConstructParameters
0x18015ac5e  mov     ebx, eax
0x18015ac60  test    eax, eax
0x18015ac62  jz      short loc_18015AC96
0x18015ac64  mov     eax, cs:dword_18039EB68
0x18015ac6a  cmp     eax, 2
0x18015ac6d  jbe     loc_18015AD4C
0x18015ac73  mov     dword ptr [rbp+270h+var_2C0], ebx
0x18015ac76  mov     dword ptr [rbp+270h+var_2B8], 133h
0x18015ac7d  lea     rax, [rbp+270h+var_2C0]
0x18015ac81  mov     [rsp+370h+var_340], rax
0x18015ac86  lea     rax, [rbp+270h+var_2B8]
0x18015ac8a  lea     rdx, word_18035CFB6
0x18015ac91  jmp     loc_18015ABDB
0x18015ac96  mov     rcx, [rbp+270h+var_2F0]
0x18015ac9a  mov     rax, [rcx]
0x18015ac9d  lea     rdx, [rbp+270h+instance]
0x18015aca4  mov     qword ptr [rsp+370h+var_350], rdx
0x18015aca9  mov     r9, r13
0x18015acac  mov     r8, rsi
0x18015acaf  mov     edx, 0B0014h
0x18015acb4  mov     rax, [rax+30h]
0x18015acb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015acbd  mov     ebx, eax
0x18015acbf  test    eax, eax
0x18015acc1  jz      short loc_18015ACF1
0x18015acc3  mov     eax, cs:dword_18039EB68
0x18015acc9  cmp     eax, 2
0x18015accc  jbe     short loc_18015AD4C
0x18015acce  mov     dword ptr [rbp+270h+var_2B0], ebx
0x18015acd1  mov     dword ptr [rbp+270h+var_2E8], 13Eh
0x18015acd8  lea     rax, [rbp+270h+var_2B0]
0x18015acdc  mov     [rsp+370h+var_340], rax
0x18015ace1  lea     rax, [rbp+270h+var_2E8]
0x18015ace5  lea     rdx, dword_18035D52C
0x18015acec  jmp     loc_18015ABDB
0x18015acf1  lea     rdx, [rbp+270h+instance]
0x18015acf8  mov     rcx, rsi; self
0x18015acfb  call    MI_Instance_Destruct
0x18015ad00  mov     ebx, eax
0x18015ad02  test    eax, eax
0x18015ad04  jz      short loc_18015AD4C
0x18015ad06  mov     eax, cs:dword_18039EB68
0x18015ad0c  cmp     eax, 2
0x18015ad0f  jbe     short loc_18015AD4C
0x18015ad11  mov     [rsp+370h+var_2F4], ebx
0x18015ad15  mov     dword ptr [rsp+370h+var_300], 146h
0x18015ad1d  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015ad24  mov     [rbp+270h+var_2E8], r13
0x18015ad28  lea     rax, [rsp+370h+var_2F4]
0x18015ad2d  mov     [rsp+370h+var_340], rax
0x18015ad32  lea     rax, [rsp+370h+var_300]
0x18015ad37  mov     [rsp+370h+var_348], rax
0x18015ad3c  lea     rax, [rbp+270h+var_2E8]
0x18015ad40  lea     rdx, unk_18035CAB0
0x18015ad47  jmp     loc_18015ABF1
0x18015ad4c  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015ad53  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015ad5a  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015ad5f  jmp     short loc_18015AD68
0x18015ad61  lea     r13, aSpacesStoragep; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015ad68  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015ad6c  xor     r15d, r15d
0x18015ad6f  mov     [rsp+370h+var_348], r15; unsigned __int16 *
0x18015ad74  mov     [rsp+370h+var_350], ebx; enum _MI_Result
0x18015ad78  lea     r9, [rbp+270h+var_1B0]; struct _MI_ConstUint32Field *
0x18015ad7f  mov     rdx, [rbp+270h+var_2A8]; unsigned __int16 *
0x18015ad83  mov     rcx, [rbp+270h+var_2E0]; unsigned __int16 *
0x18015ad87  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015ad8c  test    r12d, r12d
0x18015ad8f  jnz     loc_18015AF32
0x18015ad95  lea     rcx, [rbp+270h+var_2A0]; this
0x18015ad99  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015ad9e  mov     eax, cs:dword_18039EB68
0x18015ada4  cmp     eax, 5
0x18015ada7  jbe     loc_18015AF32
0x18015adad  mov     rdx, 400000000000h
0x18015adb7  lea     rcx, dword_18039EB68
0x18015adbe  call    _tlgKeywordOn
0x18015adc3  test    al, al
0x18015adc5  jz      loc_18015AF32
0x18015adcb  cmp     [rbp+270h+var_88], r15b
0x18015add2  jz      short loc_18015AE0F
0x18015add4  mov     rax, [rbp+270h+var_90]
0x18015addb  movups  xmm0, xmmword ptr [rax]
0x18015adde  movaps  xmmword ptr [rbp+270h+var_260.ft], xmm0
0x18015ade2  movups  xmm1, xmmword ptr [rax+10h]
0x18015ade6  movaps  xmmword ptr [rbp+270h+var_260.serverName], xmm1
0x18015adea  movups  xmm0, xmmword ptr [rax+20h]
0x18015adee  movaps  xmmword ptr [rbp+270h+var_260.reserved], xmm0
0x18015adf2  movups  xmm1, xmmword ptr [rax+30h]
0x18015adf6  movaps  xmmword ptr [rbp+270h+var_260.reserved+10h], xmm1
0x18015adfa  xor     r8d, r8d; unsigned __int16 *
0x18015adfd  lea     rdx, [rbp+270h+var_260]; struct _MI_Instance
0x18015ae01  lea     rcx, name; "ObjectId"
0x18015ae08  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015ae0d  jmp     short loc_18015AE12
0x18015ae0f  mov     rax, r15
0x18015ae12  mov     [rbp+270h+var_2E0], rax
0x18015ae16  cmp     [rbp+270h+var_98], r15b
0x18015ae1d  jz      short loc_18015AE5A
0x18015ae1f  mov     rax, [rbp+270h+var_A0]
0x18015ae26  movups  xmm0, xmmword ptr [rax]
0x18015ae29  movaps  xmmword ptr [rbp+270h+var_260.ft], xmm0
0x18015ae2d  movups  xmm1, xmmword ptr [rax+10h]
0x18015ae31  movaps  xmmword ptr [rbp+270h+var_260.serverName], xmm1
0x18015ae35  movups  xmm0, xmmword ptr [rax+20h]
0x18015ae39  movaps  xmmword ptr [rbp+270h+var_260.reserved], xmm0
0x18015ae3d  movups  xmm1, xmmword ptr [rax+30h]
0x18015ae41  movaps  xmmword ptr [rbp+270h+var_260.reserved+10h], xmm1
0x18015ae45  xor     r8d, r8d; unsigned __int16 *
0x18015ae48  lea     rdx, [rbp+270h+var_260]; struct _MI_Instance
0x18015ae4c  lea     rcx, name; "ObjectId"
0x18015ae53  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015ae58  jmp     short loc_18015AE5D
0x18015ae5a  mov     rax, r15
0x18015ae5d  mov     [rbp+270h+var_2A8], rax
0x18015ae61  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18015ae68  mov     [rbp+270h+var_2B0], rax
0x18015ae6c  mov     rax, [rbp+270h+var_298]
0x18015ae70  sub     rax, [rbp+270h+var_2A0]
0x18015ae74  imul    rax, 3E8h
0x18015ae7b  xor     edx, edx
0x18015ae7d  div     [rbp+270h+var_290]
0x18015ae81  mov     [rbp+270h+var_2B8], rax
0x18015ae85  mov     dword ptr [rsp+370h+var_300], ebx
0x18015ae89  mov     al, [rbp+270h+var_1B0.exists]
0x18015ae8f  neg     al
0x18015ae91  sbb     ecx, ecx
0x18015ae93  and     ecx, [rbp+270h+var_1B0.value]
0x18015ae99  mov     [rsp+370h+var_2F4], ecx
0x18015ae9d  mov     dword ptr [rbp+270h+var_2E8], r14d
0x18015aea1  cmp     [rdi+48h], r15b
0x18015aea5  jz      short loc_18015AEAD
0x18015aea7  mov     rax, [rdi+40h]
0x18015aeab  jmp     short loc_18015AEB0
0x18015aead  mov     rax, r15
0x18015aeb0  mov     [rbp+270h+var_2C0], rax
0x18015aeb4  lea     rax, aCreatevirtuald_2; "CreateVirtualDisk"
0x18015aebb  mov     [rbp+270h+var_2C8], rax
0x18015aebf  lea     rax, aStoragepool_0; "StoragePool"
0x18015aec6  mov     [rbp+270h+var_2D0], rax
0x18015aeca  lea     rax, [rbp+270h+var_2E0]
0x18015aece  mov     [rsp+370h+var_308], rax
0x18015aed3  lea     rax, [rbp+270h+var_2A8]
0x18015aed7  mov     [rsp+370h+var_310], rax
0x18015aedc  lea     rax, [rbp+270h+var_2B0]
0x18015aee0  mov     [rsp+370h+var_318], rax
0x18015aee5  lea     rax, [rbp+270h+var_2B8]
0x18015aee9  mov     [rsp+370h+var_320], rax
  ... truncated ...
```
