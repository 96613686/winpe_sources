# SPACES_StoragePool_Invoke_CreateVolume2

- ea: `0x18015bbe0`
- end: `0x18015c200`
- name: `SPACES_StoragePool_Invoke_CreateVolume2`
- size: `1568`
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
- `0x18015bbe0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015bc5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015bcc8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c1c9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015bc5d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015bcc8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015c1c9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015bc86`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015bc86`

## string_xrefs

- `0x18015c0e1`: `CreateVolume`
- `0x18015bcda`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x18015be15`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x18015bf4a`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x18015bf79`: `SPACES_StoragePool_Invoke_CreateVolume2`
- `0x18015bf8e`: `SPACES_StoragePool_Invoke_CreateVolume2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVolume2(
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
  struct _MI_Instance *v55; // [rsp+278h] [rbp+178h]
  char v56; // [rsp+280h] [rbp+180h]
  struct _MI_Instance *v57; // [rsp+288h] [rbp+188h]
  char v58; // [rsp+290h] [rbp+190h]
  GUID ActivityId; // [rsp+2B0h] [rbp+1B0h] BYREF
  GUID v60; // [rsp+2C0h] [rbp+1C0h]
  GUID v61; // [rsp+2D0h] [rbp+1D0h] BYREF

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
    v36 = 602;
    v35 = "SPACES_StoragePool_Invoke_CreateVolume2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVolume2",
      (unsigned int)byte_18035D4C5,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x120u);
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
        v41 = 634;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = byte_18035D3C5;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVolume2";
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
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVolume2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v45) = 653;
          v34 = (const char **)&v44;
          v20 = (const char **)&v45;
          v21 = byte_18035B633;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720917,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v35) = 672;
            v39 = "SPACES_StoragePool_Invoke_CreateVolume2";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)byte_18035B98D,
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
          LODWORD(v39) = 664;
          v34 = &v46;
          v20 = &v39;
          v21 = byte_18035C389;
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
        LODWORD(v43) = 645;
        v34 = &v42;
        v20 = &v43;
        v21 = &byte_18035DB2F;
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
        v46 = "Volume";
        v45 = (unsigned __int64)(1000LL * (v48[1] - v48[0])) / v48[2];
        LODWORD(v35) = v15;
        v37 = v54.exists != 0 ? v54.value : 0;
        LODWORD(v39) = v13;
        if ( a6[4].exists )
          v29 = a6[4].value;
        else
          v29 = 0;
        v44 = v29;
        v43 = "CreateVolume";
        v42 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v54.exists != 0 ? v54.value : 0,
          (unsigned int)&unk_18035DB68,
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
    LODWORD(v35) = 705;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVolume2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_18035C3FB,
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
0x18015bbe0  mov     [rsp-8+arg_10], rbx
0x18015bbe5  push    rbp
0x18015bbe6  push    rsi
0x18015bbe7  push    rdi
0x18015bbe8  push    r12
0x18015bbea  push    r13
0x18015bbec  push    r14
0x18015bbee  push    r15
0x18015bbf0  lea     rbp, [rsp-1F0h]
0x18015bbf8  sub     rsp, 2F0h
0x18015bbff  mov     rax, cs:__security_cookie
0x18015bc06  xor     rax, rsp
0x18015bc09  mov     [rbp+220h+var_40], rax
0x18015bc10  mov     [rbp+220h+var_290], r9
0x18015bc14  mov     rsi, rdx
0x18015bc17  mov     r15, rcx
0x18015bc1a  mov     rax, [rbp+220h+arg_20]
0x18015bc21  mov     [rbp+220h+var_258], rax
0x18015bc25  mov     rdi, [rbp+220h+arg_28]
0x18015bc2c  mov     r13, [rbp+220h+arg_30]
0x18015bc33  xorps   xmm0, xmm0
0x18015bc36  xor     eax, eax
0x18015bc38  movups  xmmword ptr [rbp+220h+value], xmm0
0x18015bc3c  movups  xmmword ptr [rbp+220h+value+10h], xmm0
0x18015bc40  mov     qword ptr [rbp+220h+value+20h], rax
0x18015bc44  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015bc4b  movdqu  xmmword ptr [rbp+220h+ActivityId.Data1], xmm0
0x18015bc53  lea     rdx, [rbp+220h+ActivityId]; ActivityId
0x18015bc5a  lea     ecx, [rax+1]; ControlCode
0x18015bc5d  call    cs:__imp_EventActivityIdControl
0x18015bc64  nop     dword ptr [rax+rax+00h]
0x18015bc69  lea     r9, [rbp+220h+value]; value
0x18015bc6d  mov     rcx, rsi; context
0x18015bc70  call    MI_Context_GetCustomOption_1
0x18015bc75  xor     ebx, ebx
0x18015bc77  test    eax, eax
0x18015bc79  jnz     short loc_18015BC92
0x18015bc7b  lea     rdx, [rbp+220h+ActivityId]; pclsid
0x18015bc82  mov     rcx, qword ptr [rbp+220h+value]; lpsz
0x18015bc86  call    cs:__imp_CLSIDFromString
0x18015bc8d  nop     dword ptr [rax+rax+00h]
0x18015bc92  mov     rcx, qword ptr [rbp+220h+ActivityId.Data1]
0x18015bc99  mov     [rbp+220h+var_60], rcx
0x18015bca0  mov     rax, qword ptr [rbp+220h+ActivityId.Data4]
0x18015bca7  mov     [rbp+220h+var_58], rax
0x18015bcae  mov     qword ptr [rbp+220h+var_50.Data1], rcx
0x18015bcb5  mov     qword ptr [rbp+220h+var_50.Data4], rax
0x18015bcbc  lea     rdx, [rbp+220h+var_50]; ActivityId
0x18015bcc3  mov     ecx, 4; ControlCode
0x18015bcc8  call    cs:__imp_EventActivityIdControl
0x18015bccf  nop     dword ptr [rax+rax+00h]
0x18015bcd4  mov     eax, cs:dword_18039EB68
0x18015bcda  lea     rcx, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x18015bce1  cmp     eax, 5
0x18015bce4  jbe     short loc_18015BD13
0x18015bce6  mov     [rsp+320h+var_2A8], 25Ah
0x18015bcee  mov     [rsp+320h+var_2B0], rcx
0x18015bcf3  lea     rax, [rsp+320h+var_2A8]
0x18015bcf8  mov     [rsp+320h+var_2F8], rax
0x18015bcfd  lea     rax, [rsp+320h+var_2B0]
0x18015bd02  mov     qword ptr [rsp+320h+var_300], rax
0x18015bd07  lea     rdx, byte_18035D4C5
0x18015bd0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015bd13  mov     [rbp+220h+instance.ft], rbx
0x18015bd1a  xor     edx, edx; Val
0x18015bd1c  mov     r8d, 120h; Size
0x18015bd22  lea     rcx, [rbp+220h+instance.classDecl]; void *
0x18015bd29  call    memset_0
0x18015bd2e  xorps   xmm0, xmm0
0x18015bd31  xor     eax, eax
0x18015bd33  movups  [rbp+220h+var_230], xmm0
0x18015bd37  mov     [rbp+220h+var_220], rax
0x18015bd3b  mov     [rbp+220h+var_2A0], rbx
0x18015bd3f  lea     rcx, [rbp+220h+var_2A0]
0x18015bd43  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015bd48  mov     [rbp+220h+var_2A0], rbx
0x18015bd4c  mov     r14d, ebx
0x18015bd4f  lea     rcx, [rbp+220h+var_250]; this
0x18015bd53  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015bd58  mov     rcx, rsi; context
0x18015bd5b  call    WspIsRemoteRequest
0x18015bd60  mov     r12d, eax
0x18015bd63  test    eax, eax
0x18015bd65  jnz     short loc_18015BD8A
0x18015bd67  lea     rcx, [rbp+220h+var_250]; this
0x18015bd6b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015bd70  cmp     [rdi+48h], bl
0x18015bd73  jz      short loc_18015BD87
0x18015bd75  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015bd79  call    WspIsRemoteInstance
0x18015bd7e  test    al, al
0x18015bd80  lea     r14d, [r12+1]
0x18015bd85  jnz     short loc_18015BD8A
0x18015bd87  mov     r14d, ebx
0x18015bd8a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015bd91  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015bd96  mov     ebx, eax
0x18015bd98  test    eax, eax
0x18015bd9a  jnz     loc_18015BF8E
0x18015bda0  mov     dword ptr [rbp+220h+var_230], 0Bh
0x18015bda7  mov     rax, [rdi+40h]
0x18015bdab  mov     qword ptr [rbp+220h+var_230+8], rax
0x18015bdaf  mov     rbx, [r15]
0x18015bdb2  lea     rcx, [rbp+220h+var_2A0]
0x18015bdb6  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015bdbb  mov     [rsp+320h+var_300], 1; int
0x18015bdc3  lea     r9, [rbp+220h+var_2A0]; struct ISpWmiObject **
0x18015bdc7  lea     r8, [rbp+220h+var_230]; struct _SP_OBJECT_ID *
0x18015bdcb  mov     rdx, rsi; context
0x18015bdce  mov     rcx, rbx; this
0x18015bdd1  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015bdd6  mov     ebx, eax
0x18015bdd8  test    eax, eax
0x18015bdda  jz      short loc_18015BE30
0x18015bddc  mov     eax, cs:dword_18039EB68
0x18015bde2  cmp     eax, 2
0x18015bde5  jbe     loc_18015BF79
0x18015bdeb  mov     [rsp+320h+var_2A8], ebx
0x18015bdef  mov     [rbp+220h+var_288], 27Ah
0x18015bdf6  lea     rax, [rsp+320h+var_2A8]
0x18015bdfb  mov     [rsp+320h+var_2F0], rax
0x18015be00  lea     rax, [rbp+220h+var_288]
0x18015be04  lea     rdx, byte_18035D3C5
0x18015be0b  mov     [rsp+320h+var_2F8], rax
0x18015be10  lea     rax, [rsp+320h+var_2B0]
0x18015be15  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x18015be1c  mov     [rsp+320h+var_2B0], r13
0x18015be21  mov     qword ptr [rsp+320h+var_300], rax
0x18015be26  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015be2b  jmp     loc_18015BF80
0x18015be30  mov     r8, [rdi+40h]
0x18015be34  mov     rdx, rsi
0x18015be37  mov     rcx, [r15]
0x18015be3a  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18015be3f  test    eax, eax
0x18015be41  jnz     short loc_18015BE75
0x18015be43  lea     ebx, [rax+7]
0x18015be46  mov     eax, cs:dword_18039EB68
0x18015be4c  cmp     eax, 2
0x18015be4f  jbe     loc_18015BF79
0x18015be55  mov     dword ptr [rbp+220h+var_280], ebx
0x18015be58  mov     dword ptr [rbp+220h+var_278], 285h
0x18015be5f  lea     rax, [rbp+220h+var_280]
0x18015be63  mov     [rsp+320h+var_2F0], rax
0x18015be68  lea     rax, [rbp+220h+var_278]
0x18015be6c  lea     rdx, byte_18035DB2F
0x18015be73  jmp     short loc_18015BE0B
0x18015be75  lea     r8, [rbp+220h+instance]; instance
0x18015be7c  lea     rdx, SPACES_StoragePool_CreateVolume2_rtti; methodDecl
0x18015be83  mov     rcx, rsi; context
0x18015be86  call    MI_Context_ConstructParameters
0x18015be8b  mov     ebx, eax
0x18015be8d  test    eax, eax
0x18015be8f  jz      short loc_18015BEC3
0x18015be91  mov     eax, cs:dword_18039EB68
0x18015be97  cmp     eax, 2
0x18015be9a  jbe     loc_18015BF79
0x18015bea0  mov     dword ptr [rbp+220h+var_270], ebx
0x18015bea3  mov     dword ptr [rbp+220h+var_268], 28Dh
0x18015beaa  lea     rax, [rbp+220h+var_270]
0x18015beae  mov     [rsp+320h+var_2F0], rax
0x18015beb3  lea     rax, [rbp+220h+var_268]
0x18015beb7  lea     rdx, byte_18035B633
0x18015bebe  jmp     loc_18015BE0B
0x18015bec3  mov     rcx, [rbp+220h+var_2A0]
0x18015bec7  mov     rax, [rcx]
0x18015beca  lea     rdx, [rbp+220h+instance]
0x18015bed1  mov     qword ptr [rsp+320h+var_300], rdx
0x18015bed6  mov     r9, r13
0x18015bed9  mov     r8, rsi
0x18015bedc  mov     edx, 0B0015h
0x18015bee1  mov     rax, [rax+30h]
0x18015bee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015beea  mov     ebx, eax
0x18015beec  test    eax, eax
0x18015beee  jz      short loc_18015BF1E
0x18015bef0  mov     eax, cs:dword_18039EB68
0x18015bef6  cmp     eax, 2
0x18015bef9  jbe     short loc_18015BF79
0x18015befb  mov     dword ptr [rbp+220h+var_260], ebx
0x18015befe  mov     dword ptr [rbp+220h+var_298], 298h
0x18015bf05  lea     rax, [rbp+220h+var_260]
0x18015bf09  mov     [rsp+320h+var_2F0], rax
0x18015bf0e  lea     rax, [rbp+220h+var_298]
0x18015bf12  lea     rdx, byte_18035C389
0x18015bf19  jmp     loc_18015BE0B
0x18015bf1e  lea     rdx, [rbp+220h+instance]
0x18015bf25  mov     rcx, rsi; self
0x18015bf28  call    MI_Instance_Destruct
0x18015bf2d  mov     ebx, eax
0x18015bf2f  test    eax, eax
0x18015bf31  jz      short loc_18015BF79
0x18015bf33  mov     eax, cs:dword_18039EB68
0x18015bf39  cmp     eax, 2
0x18015bf3c  jbe     short loc_18015BF79
0x18015bf3e  mov     [rsp+320h+var_2A4], ebx
0x18015bf42  mov     dword ptr [rsp+320h+var_2B0], 2A0h
0x18015bf4a  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x18015bf51  mov     [rbp+220h+var_298], r13
0x18015bf55  lea     rax, [rsp+320h+var_2A4]
0x18015bf5a  mov     [rsp+320h+var_2F0], rax
0x18015bf5f  lea     rax, [rsp+320h+var_2B0]
0x18015bf64  mov     [rsp+320h+var_2F8], rax
0x18015bf69  lea     rax, [rbp+220h+var_298]
0x18015bf6d  lea     rdx, byte_18035B98D
0x18015bf74  jmp     loc_18015BE21
0x18015bf79  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x18015bf80  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015bf87  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015bf8c  jmp     short loc_18015BF95
0x18015bf8e  lea     r13, aSpacesStoragep_11; "SPACES_StoragePool_Invoke_CreateVolume2"
0x18015bf95  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015bf99  xor     r15d, r15d
0x18015bf9c  mov     [rsp+320h+var_2F8], r15; unsigned __int16 *
0x18015bfa1  mov     [rsp+320h+var_300], ebx; enum _MI_Result
0x18015bfa5  lea     r9, [rbp+220h+var_160]; struct _MI_ConstUint32Field *
0x18015bfac  mov     rdx, [rbp+220h+var_258]; unsigned __int16 *
0x18015bfb0  mov     rcx, [rbp+220h+var_290]; unsigned __int16 *
0x18015bfb4  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015bfb9  test    r12d, r12d
0x18015bfbc  jnz     loc_18015C15F
0x18015bfc2  lea     rcx, [rbp+220h+var_250]; this
0x18015bfc6  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015bfcb  mov     eax, cs:dword_18039EB68
0x18015bfd1  cmp     eax, 5
0x18015bfd4  jbe     loc_18015C15F
0x18015bfda  mov     rdx, 400000000000h
0x18015bfe4  lea     rcx, dword_18039EB68
0x18015bfeb  call    _tlgKeywordOn
0x18015bff0  test    al, al
0x18015bff2  jz      loc_18015C15F
0x18015bff8  cmp     [rbp+220h+var_90], r15b
0x18015bfff  jz      short loc_18015C03C
0x18015c001  mov     rax, [rbp+220h+var_98]
0x18015c008  movups  xmm0, xmmword ptr [rax]
0x18015c00b  movaps  xmmword ptr [rbp+220h+var_210.ft], xmm0
0x18015c00f  movups  xmm1, xmmword ptr [rax+10h]
0x18015c013  movaps  xmmword ptr [rbp+220h+var_210.serverName], xmm1
0x18015c017  movups  xmm0, xmmword ptr [rax+20h]
0x18015c01b  movaps  xmmword ptr [rbp+220h+var_210.reserved], xmm0
0x18015c01f  movups  xmm1, xmmword ptr [rax+30h]
0x18015c023  movaps  xmmword ptr [rbp+220h+var_210.reserved+10h], xmm1
0x18015c027  xor     r8d, r8d; unsigned __int16 *
0x18015c02a  lea     rdx, [rbp+220h+var_210]; struct _MI_Instance
0x18015c02e  lea     rcx, name; "ObjectId"
0x18015c035  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015c03a  jmp     short loc_18015C03F
0x18015c03c  mov     rax, r15
0x18015c03f  mov     [rbp+220h+var_290], rax
0x18015c043  cmp     [rbp+220h+var_A0], r15b
0x18015c04a  jz      short loc_18015C087
0x18015c04c  mov     rax, [rbp+220h+var_A8]
0x18015c053  movups  xmm0, xmmword ptr [rax]
0x18015c056  movaps  xmmword ptr [rbp+220h+var_210.ft], xmm0
0x18015c05a  movups  xmm1, xmmword ptr [rax+10h]
0x18015c05e  movaps  xmmword ptr [rbp+220h+var_210.serverName], xmm1
0x18015c062  movups  xmm0, xmmword ptr [rax+20h]
0x18015c066  movaps  xmmword ptr [rbp+220h+var_210.reserved], xmm0
0x18015c06a  movups  xmm1, xmmword ptr [rax+30h]
0x18015c06e  movaps  xmmword ptr [rbp+220h+var_210.reserved+10h], xmm1
0x18015c072  xor     r8d, r8d; unsigned __int16 *
0x18015c075  lea     rdx, [rbp+220h+var_210]; struct _MI_Instance
0x18015c079  lea     rcx, name; "ObjectId"
0x18015c080  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015c085  jmp     short loc_18015C08A
0x18015c087  mov     rax, r15
0x18015c08a  mov     [rbp+220h+var_258], rax
0x18015c08e  lea     rax, aVolume_1; "Volume"
0x18015c095  mov     [rbp+220h+var_260], rax
0x18015c099  mov     rax, [rbp+220h+var_248]
0x18015c09d  sub     rax, [rbp+220h+var_250]
0x18015c0a1  imul    rax, 3E8h
0x18015c0a8  xor     edx, edx
0x18015c0aa  div     [rbp+220h+var_240]
0x18015c0ae  mov     [rbp+220h+var_268], rax
0x18015c0b2  mov     dword ptr [rsp+320h+var_2B0], ebx
0x18015c0b6  mov     al, [rbp+220h+var_160.exists]
0x18015c0bc  neg     al
0x18015c0be  sbb     ecx, ecx
0x18015c0c0  and     ecx, [rbp+220h+var_160.value]
0x18015c0c6  mov     [rsp+320h+var_2A4], ecx
0x18015c0ca  mov     dword ptr [rbp+220h+var_298], r14d
0x18015c0ce  cmp     [rdi+48h], r15b
0x18015c0d2  jz      short loc_18015C0DA
0x18015c0d4  mov     rax, [rdi+40h]
0x18015c0d8  jmp     short loc_18015C0DD
0x18015c0da  mov     rax, r15
0x18015c0dd  mov     [rbp+220h+var_270], rax
0x18015c0e1  lea     rax, aCreatevolume_0; "CreateVolume"
0x18015c0e8  mov     [rbp+220h+var_278], rax
0x18015c0ec  lea     rax, aStoragepool_0; "StoragePool"
0x18015c0f3  mov     [rbp+220h+var_280], rax
0x18015c0f7  lea     rax, [rbp+220h+var_290]
0x18015c0fb  mov     [rsp+320h+var_2B8], rax
0x18015c100  lea     rax, [rbp+220h+var_258]
0x18015c104  mov     [rsp+320h+var_2C0], rax
0x18015c109  lea     rax, [rbp+220h+var_260]
0x18015c10d  mov     [rsp+320h+var_2C8], rax
0x18015c112  lea     rax, [rbp+220h+var_268]
0x18015c116  mov     [rsp+320h+var_2D0], rax
  ... truncated ...
```
