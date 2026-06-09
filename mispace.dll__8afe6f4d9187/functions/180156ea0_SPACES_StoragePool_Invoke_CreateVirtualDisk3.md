# SPACES_StoragePool_Invoke_CreateVirtualDisk3

- ea: `0x180156ea0`
- end: `0x1801574ba`
- name: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- size: `1562`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800045d0`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000c704`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180015b40`
- `0x180015c60`
- `0x1800175f0`
- `0x18001a5e4`
- `0x18001afd0`
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x180156ea0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156f1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156f7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015748a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156f1d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180156f7c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015748a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180156f40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180156f40`

## string_xrefs

- `0x180157392`: `CreateVirtualDisk`
- `0x180156f88`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x1801570c3`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x1801571fb`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x18015722a`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x18015723f`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_StoragePool_Invoke_CreateVirtualDisk3(
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
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r15d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  char *v20; // rdx
  const char **v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // rax
  const MI_Char *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned __int16 *v31; // [rsp+28h] [rbp-D8h]
  const char *v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h] BYREF
  MI_Uint32 v34; // [rsp+7Ch] [rbp-84h] BYREF
  struct ISpWmiObject *v35; // [rsp+80h] [rbp-80h] BYREF
  const char *v36; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v37; // [rsp+90h] [rbp-70h] BYREF
  int v38; // [rsp+98h] [rbp-68h]
  const char *v39; // [rsp+A0h] [rbp-60h] BYREF
  const char *v40; // [rsp+A8h] [rbp-58h] BYREF
  const MI_Char *v41; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v42; // [rsp+B8h] [rbp-48h] BYREF
  const char *v43; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v44; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v45[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v46; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v47; // [rsp+100h] [rbp+0h]
  struct _MI_Instance v48; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v51; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v52; // [rsp+2F0h] [rbp+1F0h]
  char v53; // [rsp+2F8h] [rbp+1F8h]
  struct _MI_Instance *v54; // [rsp+300h] [rbp+200h]
  char v55; // [rsp+308h] [rbp+208h]
  GUID ActivityId; // [rsp+320h] [rbp+220h] BYREF
  GUID v57; // [rsp+330h] [rbp+230h]
  GUID v58; // [rsp+340h] [rbp+240h] BYREF

  v37 = a4;
  v44 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v57 = ActivityId;
  v58 = ActivityId;
  EventActivityIdControl(4u, &v58);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v33 = 375;
    v32 = "SPACES_StoragePool_Invoke_CreateVirtualDisk3";
    v31 = (unsigned __int16 *)&v33;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StoragePool_Invoke_CreateVirtualDisk3",
      (__int64)&word_180356F7E,
      v11,
      v12,
      &v32);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x198u);
  v46 = 0;
  v47 = 0;
  v35 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  v35 = 0;
  v13 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v45);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v45);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v46) = 11;
    *((_QWORD *)&v46 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v46, &v35, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
      {
LABEL_27:
        MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
        goto LABEL_28;
      }
      v33 = v15;
      v38 = 407;
      v20 = (char *)word_1803558D2;
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVirtualDisk3_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        LODWORD(v41) = v15;
        LODWORD(v42) = 426;
        v20 = &byte_1803552B7;
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v35 + 48LL))(
                v35,
                720919,
                a2,
                a7,
                &instance,
                v31);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_27;
          v34 = v15;
          LODWORD(v32) = 445;
          v36 = "SPACES_StoragePool_Invoke_CreateVirtualDisk3";
          v21 = &v36;
          v20 = (char *)&dword_1803564A4;
          goto LABEL_14;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        LODWORD(v43) = v15;
        LODWORD(v36) = 437;
        v20 = byte_180356FD9;
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_27;
      LODWORD(v39) = 7;
      LODWORD(v40) = 418;
      v20 = &byte_180356067;
    }
    v21 = &v32;
    v32 = "SPACES_StoragePool_Invoke_CreateVirtualDisk3";
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (__int64)v20,
      v18,
      v19,
      v21);
    goto LABEL_27;
  }
LABEL_28:
  SmLogOnMethodFailure(v37, v44, a6 + 4, &v51, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v45);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( v55 )
        {
          v48 = *v54;
          v24 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v24 = 0;
        }
        v37 = v24;
        if ( v53 )
        {
          v48 = *v52;
          v25 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v48, 0);
        }
        else
        {
          v25 = 0;
        }
        v44 = v25;
        v43 = "VirtualDisk";
        v42 = (unsigned __int64)(1000LL * (v45[1] - v45[0])) / v45[2];
        LODWORD(v32) = v15;
        v34 = v51.exists != 0 ? v51.value : 0;
        LODWORD(v36) = v13;
        if ( a6[4].exists )
          v26 = a6[4].value;
        else
          v26 = 0;
        v41 = v26;
        v40 = "CreateVirtualDisk";
        v39 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v51.exists != 0 ? v51.value : 0,
          (__int64)word_1803551D2,
          v22,
          v23,
          &v39,
          &v40,
          &v41,
          (__int64)&v36,
          (__int64)&v34,
          (__int64)&v32,
          (__int64)&v42,
          &v43,
          &v44,
          &v37);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v32) = 478;
    v37 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVirtualDisk3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)byte_180354A6B,
      v28,
      v29,
      &v37);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v45);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  return EventActivityIdControl(4u, &v58);
}

```

## disassembly

```asm
0x180156ea0  mov     [rsp-8+arg_10], rbx
0x180156ea5  push    rbp
0x180156ea6  push    rsi
0x180156ea7  push    rdi
0x180156ea8  push    r12
0x180156eaa  push    r13
0x180156eac  push    r14
0x180156eae  push    r15
0x180156eb0  lea     rbp, [rsp-260h]
0x180156eb8  sub     rsp, 360h
0x180156ebf  mov     rax, cs:__security_cookie
0x180156ec6  xor     rax, rsp
0x180156ec9  mov     [rbp+290h+var_40], rax
0x180156ed0  mov     [rbp+290h+var_300], r9
0x180156ed4  mov     rdi, rdx
0x180156ed7  mov     r14, rcx
0x180156eda  mov     rax, [rbp+290h+arg_20]
0x180156ee1  mov     [rbp+290h+var_2C8], rax
0x180156ee5  mov     rsi, [rbp+290h+arg_28]
0x180156eec  mov     r13, [rbp+290h+arg_30]
0x180156ef3  xorps   xmm0, xmm0
0x180156ef6  xor     eax, eax
0x180156ef8  movups  xmmword ptr [rbp+290h+value], xmm0
0x180156efc  movups  xmmword ptr [rbp+290h+value+10h], xmm0
0x180156f00  mov     qword ptr [rbp+290h+value+20h], rax
0x180156f04  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180156f0b  movdqu  xmmword ptr [rbp+290h+ActivityId.Data1], xmm0
0x180156f13  lea     rdx, [rbp+290h+ActivityId]; ActivityId
0x180156f1a  lea     ecx, [rax+1]; ControlCode
0x180156f1d  call    cs:__imp_EventActivityIdControl
0x180156f23  lea     r9, [rbp+290h+value]; value
0x180156f27  mov     rcx, rdi; context
0x180156f2a  call    MI_Context_GetCustomOption_1
0x180156f2f  xor     ebx, ebx
0x180156f31  test    eax, eax
0x180156f33  jnz     short loc_180156F46
0x180156f35  lea     rdx, [rbp+290h+ActivityId]; pclsid
0x180156f3c  mov     rcx, qword ptr [rbp+290h+value]; lpsz
0x180156f40  call    cs:__imp_CLSIDFromString
0x180156f46  mov     rcx, qword ptr [rbp+290h+ActivityId.Data1]
0x180156f4d  mov     [rbp+290h+var_60], rcx
0x180156f54  mov     rax, qword ptr [rbp+290h+ActivityId.Data4]
0x180156f5b  mov     [rbp+290h+var_58], rax
0x180156f62  mov     qword ptr [rbp+290h+var_50.Data1], rcx
0x180156f69  mov     qword ptr [rbp+290h+var_50.Data4], rax
0x180156f70  lea     rdx, [rbp+290h+var_50]; ActivityId
0x180156f77  mov     ecx, 4; ControlCode
0x180156f7c  call    cs:__imp_EventActivityIdControl
0x180156f82  mov     eax, cs:dword_180397B68
0x180156f88  lea     rcx, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180156f8f  cmp     eax, 5
0x180156f92  jbe     short loc_180156FC1
0x180156f94  mov     [rsp+390h+var_318], 177h
0x180156f9c  mov     [rsp+390h+var_320], rcx
0x180156fa1  lea     rax, [rsp+390h+var_318]
0x180156fa6  mov     [rsp+390h+var_368], rax
0x180156fab  lea     rax, [rsp+390h+var_320]
0x180156fb0  mov     qword ptr [rsp+390h+var_370], rax
0x180156fb5  lea     rdx, word_180356F7E
0x180156fbc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180156fc1  mov     [rbp+290h+instance.ft], rbx
0x180156fc8  xor     edx, edx; Val
0x180156fca  mov     r8d, 198h; Size
0x180156fd0  lea     rcx, [rbp+290h+instance.classDecl]; void *
0x180156fd7  call    memset_0
0x180156fdc  xorps   xmm0, xmm0
0x180156fdf  xor     eax, eax
0x180156fe1  movups  [rbp+290h+var_2A0], xmm0
0x180156fe5  mov     [rbp+290h+var_290], rax
0x180156fe9  mov     [rbp+290h+var_310], rbx
0x180156fed  lea     rcx, [rbp+290h+var_310]
0x180156ff1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180156ff6  mov     [rbp+290h+var_310], rbx
0x180156ffa  mov     r15d, ebx
0x180156ffd  lea     rcx, [rbp+290h+var_2C0]; this
0x180157001  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180157006  mov     rcx, rdi; context
0x180157009  call    WspIsRemoteRequest
0x18015700e  mov     r12d, eax
0x180157011  test    eax, eax
0x180157013  jnz     short loc_180157038
0x180157015  lea     rcx, [rbp+290h+var_2C0]; this
0x180157019  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015701e  cmp     [rsi+48h], bl
0x180157021  jz      short loc_180157035
0x180157023  mov     rcx, [rsi+40h]; unsigned __int16 *
0x180157027  call    WspIsRemoteInstance
0x18015702c  test    al, al
0x18015702e  lea     r15d, [r12+1]
0x180157033  jnz     short loc_180157038
0x180157035  mov     r15d, ebx
0x180157038  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015703f  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x180157044  mov     ebx, eax
0x180157046  test    eax, eax
0x180157048  jnz     loc_18015723F
0x18015704e  mov     dword ptr [rbp+290h+var_2A0], 0Bh
0x180157055  mov     rax, [rsi+40h]
0x180157059  mov     qword ptr [rbp+290h+var_2A0+8], rax
0x18015705d  mov     rbx, [r14]
0x180157060  lea     rcx, [rbp+290h+var_310]
0x180157064  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180157069  mov     [rsp+390h+var_370], 1; int
0x180157071  lea     r9, [rbp+290h+var_310]; struct ISpWmiObject **
0x180157075  lea     r8, [rbp+290h+var_2A0]; struct _SP_OBJECT_ID *
0x180157079  mov     rdx, rdi; context
0x18015707c  mov     rcx, rbx; this
0x18015707f  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x180157084  mov     ebx, eax
0x180157086  test    eax, eax
0x180157088  jz      short loc_1801570DE
0x18015708a  mov     eax, cs:dword_180397B68
0x180157090  cmp     eax, 2
0x180157093  jbe     loc_18015722A
0x180157099  mov     [rsp+390h+var_318], ebx
0x18015709d  mov     [rbp+290h+var_2F8], 197h
0x1801570a4  lea     rax, [rsp+390h+var_318]
0x1801570a9  mov     [rsp+390h+var_360], rax
0x1801570ae  lea     rax, [rbp+290h+var_2F8]
0x1801570b2  lea     rdx, word_1803558D2
0x1801570b9  mov     [rsp+390h+var_368], rax
0x1801570be  lea     rax, [rsp+390h+var_320]
0x1801570c3  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x1801570ca  mov     [rsp+390h+var_320], r13
0x1801570cf  mov     qword ptr [rsp+390h+var_370], rax
0x1801570d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801570d9  jmp     loc_180157231
0x1801570de  mov     r8, [rsi+40h]
0x1801570e2  mov     rdx, rdi
0x1801570e5  mov     rcx, [r14]
0x1801570e8  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x1801570ed  cmp     eax, 3
0x1801570f0  jnb     short loc_180157126
0x1801570f2  mov     ebx, 7
0x1801570f7  mov     eax, cs:dword_180397B68
0x1801570fd  cmp     eax, 2
0x180157100  jbe     loc_18015722A
0x180157106  mov     dword ptr [rbp+290h+var_2F0], ebx
0x180157109  mov     dword ptr [rbp+290h+var_2E8], 1A2h
0x180157110  lea     rax, [rbp+290h+var_2F0]
0x180157114  mov     [rsp+390h+var_360], rax
0x180157119  lea     rax, [rbp+290h+var_2E8]
0x18015711d  lea     rdx, byte_180356067
0x180157124  jmp     short loc_1801570B9
0x180157126  lea     r8, [rbp+290h+instance]; instance
0x18015712d  lea     rdx, SPACES_StoragePool_CreateVirtualDisk3_rtti; methodDecl
0x180157134  mov     rcx, rdi; context
0x180157137  call    MI_Context_ConstructParameters
0x18015713c  mov     ebx, eax
0x18015713e  test    eax, eax
0x180157140  jz      short loc_180157174
0x180157142  mov     eax, cs:dword_180397B68
0x180157148  cmp     eax, 2
0x18015714b  jbe     loc_18015722A
0x180157151  mov     dword ptr [rbp+290h+var_2E0], ebx
0x180157154  mov     dword ptr [rbp+290h+var_2D8], 1AAh
0x18015715b  lea     rax, [rbp+290h+var_2E0]
0x18015715f  mov     [rsp+390h+var_360], rax
0x180157164  lea     rax, [rbp+290h+var_2D8]
0x180157168  lea     rdx, byte_1803552B7
0x18015716f  jmp     loc_1801570B9
0x180157174  mov     rcx, [rbp+290h+var_310]
0x180157178  mov     rax, [rcx]
0x18015717b  lea     rdx, [rbp+290h+instance]
0x180157182  mov     qword ptr [rsp+390h+var_370], rdx
0x180157187  mov     r9, r13
0x18015718a  mov     r8, rdi
0x18015718d  mov     edx, 0B0017h
0x180157192  mov     rax, [rax+30h]
0x180157196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015719b  mov     ebx, eax
0x18015719d  test    eax, eax
0x18015719f  jz      short loc_1801571CF
0x1801571a1  mov     eax, cs:dword_180397B68
0x1801571a7  cmp     eax, 2
0x1801571aa  jbe     short loc_18015722A
0x1801571ac  mov     dword ptr [rbp+290h+var_2D0], ebx
0x1801571af  mov     dword ptr [rbp+290h+var_308], 1B5h
0x1801571b6  lea     rax, [rbp+290h+var_2D0]
0x1801571ba  mov     [rsp+390h+var_360], rax
0x1801571bf  lea     rax, [rbp+290h+var_308]
0x1801571c3  lea     rdx, byte_180356FD9
0x1801571ca  jmp     loc_1801570B9
0x1801571cf  lea     rdx, [rbp+290h+instance]
0x1801571d6  mov     rcx, rdi; self
0x1801571d9  call    MI_Instance_Destruct
0x1801571de  mov     ebx, eax
0x1801571e0  test    eax, eax
0x1801571e2  jz      short loc_18015722A
0x1801571e4  mov     eax, cs:dword_180397B68
0x1801571ea  cmp     eax, 2
0x1801571ed  jbe     short loc_18015722A
0x1801571ef  mov     [rsp+390h+var_314], ebx
0x1801571f3  mov     dword ptr [rsp+390h+var_320], 1BDh
0x1801571fb  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180157202  mov     [rbp+290h+var_308], r13
0x180157206  lea     rax, [rsp+390h+var_314]
0x18015720b  mov     [rsp+390h+var_360], rax
0x180157210  lea     rax, [rsp+390h+var_320]
0x180157215  mov     [rsp+390h+var_368], rax
0x18015721a  lea     rax, [rbp+290h+var_308]
0x18015721e  lea     rdx, dword_1803564A4
0x180157225  jmp     loc_1801570CF
0x18015722a  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180157231  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180157238  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015723d  jmp     short loc_180157246
0x18015723f  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x180157246  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18015724a  xor     r14d, r14d
0x18015724d  mov     [rsp+390h+var_368], r14; unsigned __int16 *
0x180157252  mov     [rsp+390h+var_370], ebx; enum _MI_Result
0x180157256  lea     r9, [rbp+290h+var_1D0]; struct _MI_ConstUint32Field *
0x18015725d  mov     rdx, [rbp+290h+var_2C8]; unsigned __int16 *
0x180157261  mov     rcx, [rbp+290h+var_300]; unsigned __int16 *
0x180157265  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015726a  test    r12d, r12d
0x18015726d  jnz     loc_180157410
0x180157273  lea     rcx, [rbp+290h+var_2C0]; this
0x180157277  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015727c  mov     eax, cs:dword_180397B68
0x180157282  cmp     eax, 5
0x180157285  jbe     loc_180157410
0x18015728b  mov     rdx, 400000000000h
0x180157295  lea     rcx, dword_180397B68
0x18015729c  call    _tlgKeywordOn
0x1801572a1  test    al, al
0x1801572a3  jz      loc_180157410
0x1801572a9  cmp     [rbp+290h+var_88], r14b
0x1801572b0  jz      short loc_1801572ED
0x1801572b2  mov     rax, [rbp+290h+var_90]
0x1801572b9  movups  xmm0, xmmword ptr [rax]
0x1801572bc  movaps  xmmword ptr [rbp+290h+var_280.ft], xmm0
0x1801572c0  movups  xmm1, xmmword ptr [rax+10h]
0x1801572c4  movaps  xmmword ptr [rbp+290h+var_280.serverName], xmm1
0x1801572c8  movups  xmm0, xmmword ptr [rax+20h]
0x1801572cc  movaps  xmmword ptr [rbp+290h+var_280.reserved], xmm0
0x1801572d0  movups  xmm1, xmmword ptr [rax+30h]
0x1801572d4  movaps  xmmword ptr [rbp+290h+var_280.reserved+10h], xmm1
0x1801572d8  xor     r8d, r8d; unsigned __int16 *
0x1801572db  lea     rdx, [rbp+290h+var_280]; struct _MI_Instance
0x1801572df  lea     rcx, name; "ObjectId"
0x1801572e6  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x1801572eb  jmp     short loc_1801572F0
0x1801572ed  mov     rax, r14
0x1801572f0  mov     [rbp+290h+var_300], rax
0x1801572f4  cmp     [rbp+290h+var_98], r14b
0x1801572fb  jz      short loc_180157338
0x1801572fd  mov     rax, [rbp+290h+var_A0]
0x180157304  movups  xmm0, xmmword ptr [rax]
0x180157307  movaps  xmmword ptr [rbp+290h+var_280.ft], xmm0
0x18015730b  movups  xmm1, xmmword ptr [rax+10h]
0x18015730f  movaps  xmmword ptr [rbp+290h+var_280.serverName], xmm1
0x180157313  movups  xmm0, xmmword ptr [rax+20h]
0x180157317  movaps  xmmword ptr [rbp+290h+var_280.reserved], xmm0
0x18015731b  movups  xmm1, xmmword ptr [rax+30h]
0x18015731f  movaps  xmmword ptr [rbp+290h+var_280.reserved+10h], xmm1
0x180157323  xor     r8d, r8d; unsigned __int16 *
0x180157326  lea     rdx, [rbp+290h+var_280]; struct _MI_Instance
0x18015732a  lea     rcx, name; "ObjectId"
0x180157331  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180157336  jmp     short loc_18015733B
0x180157338  mov     rax, r14
0x18015733b  mov     [rbp+290h+var_2C8], rax
0x18015733f  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x180157346  mov     [rbp+290h+var_2D0], rax
0x18015734a  mov     rax, [rbp+290h+var_2B8]
0x18015734e  sub     rax, [rbp+290h+var_2C0]
0x180157352  imul    rax, 3E8h
0x180157359  xor     edx, edx
0x18015735b  div     [rbp+290h+var_2B0]
0x18015735f  mov     [rbp+290h+var_2D8], rax
0x180157363  mov     dword ptr [rsp+390h+var_320], ebx
0x180157367  mov     al, [rbp+290h+var_1D0.exists]
0x18015736d  neg     al
0x18015736f  sbb     ecx, ecx
0x180157371  and     ecx, [rbp+290h+var_1D0.value]
0x180157377  mov     [rsp+390h+var_314], ecx
0x18015737b  mov     dword ptr [rbp+290h+var_308], r15d
0x18015737f  cmp     [rsi+48h], r14b
0x180157383  jz      short loc_18015738B
0x180157385  mov     rax, [rsi+40h]
0x180157389  jmp     short loc_18015738E
0x18015738b  mov     rax, r14
0x18015738e  mov     [rbp+290h+var_2E0], rax
0x180157392  lea     rax, aCreatevirtuald_2; "CreateVirtualDisk"
0x180157399  mov     [rbp+290h+var_2E8], rax
0x18015739d  lea     rax, aStoragepool_0; "StoragePool"
0x1801573a4  mov     [rbp+290h+var_2F0], rax
0x1801573a8  lea     rax, [rbp+290h+var_300]
0x1801573ac  mov     [rsp+390h+var_328], rax
0x1801573b1  lea     rax, [rbp+290h+var_2C8]
0x1801573b5  mov     [rsp+390h+var_330], rax
0x1801573ba  lea     rax, [rbp+290h+var_2D0]
0x1801573be  mov     [rsp+390h+var_338], rax
0x1801573c3  lea     rax, [rbp+290h+var_2D8]
0x1801573c7  mov     [rsp+390h+var_340], rax
0x1801573cc  lea     rax, [rsp+390h+var_320]
0x1801573d1  mov     [rsp+390h+var_348], rax
0x1801573d6  lea     rax, [rsp+390h+var_314]
  ... truncated ...
```
