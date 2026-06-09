# SPACES_StoragePool_Invoke_CreateVirtualDisk3

- ea: `0x18015afe0`
- end: `0x18015b603`
- name: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
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
- `0x18015afe0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b05d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b0c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b5cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b05d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b0c8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015b5cc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015b086`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015b086`

## string_xrefs

- `0x18015b4e4`: `CreateVirtualDisk`
- `0x18015b0da`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x18015b215`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x18015b34d`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x18015b37c`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`
- `0x18015b391`: `SPACES_StoragePool_Invoke_CreateVirtualDisk3`

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
  __int16 *v21; // rdx
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
  struct _MI_Instance *v55; // [rsp+2F0h] [rbp+1F0h]
  char v56; // [rsp+2F8h] [rbp+1F8h]
  struct _MI_Instance *v57; // [rsp+300h] [rbp+200h]
  char v58; // [rsp+308h] [rbp+208h]
  GUID ActivityId; // [rsp+320h] [rbp+220h] BYREF
  GUID v60; // [rsp+330h] [rbp+230h]
  GUID v61; // [rsp+340h] [rbp+240h] BYREF

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
    v36 = 375;
    v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_StoragePool_Invoke_CreateVirtualDisk3",
      (unsigned int)&byte_18035DE9F,
      v11,
      v12,
      (__int64)&v35,
      (__int64)&v36);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x198u);
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
        v41 = 407;
        v34 = (const char **)&v36;
        v20 = (const char **)&v41;
        v21 = (__int16 *)&unk_18035C7E8;
LABEL_13:
        v35 = "SPACES_StoragePool_Invoke_CreateVirtualDisk3";
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
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, a6[4].value) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_CreateVirtualDisk3_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v44) = v15;
          LODWORD(v45) = 426;
          v34 = (const char **)&v44;
          v20 = (const char **)&v45;
          v21 = word_18035C15A;
          goto LABEL_13;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v38 + 48LL))(
                v38,
                720919,
                a2,
                a7,
                &instance);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v37 = v15;
            LODWORD(v35) = 445;
            v39 = "SPACES_StoragePool_Invoke_CreateVirtualDisk3";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (unsigned int)&word_18035D59E,
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
          LODWORD(v39) = 437;
          v34 = &v46;
          v20 = &v39;
          v21 = &word_18035E136;
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
        LODWORD(v43) = 418;
        v34 = &v42;
        v20 = &v43;
        v21 = (__int16 *)byte_18035D1E5;
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
          (unsigned int)&unk_18035C1C0,
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
    LODWORD(v35) = 478;
    v40 = (unsigned __int16 *)"SPACES_StoragePool_Invoke_CreateVirtualDisk3";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)byte_18035BA65,
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
0x18015afe0  mov     [rsp-8+arg_10], rbx
0x18015afe5  push    rbp
0x18015afe6  push    rsi
0x18015afe7  push    rdi
0x18015afe8  push    r12
0x18015afea  push    r13
0x18015afec  push    r14
0x18015afee  push    r15
0x18015aff0  lea     rbp, [rsp-260h]
0x18015aff8  sub     rsp, 360h
0x18015afff  mov     rax, cs:__security_cookie
0x18015b006  xor     rax, rsp
0x18015b009  mov     [rbp+290h+var_40], rax
0x18015b010  mov     [rbp+290h+var_300], r9
0x18015b014  mov     rsi, rdx
0x18015b017  mov     r15, rcx
0x18015b01a  mov     rax, [rbp+290h+arg_20]
0x18015b021  mov     [rbp+290h+var_2C8], rax
0x18015b025  mov     rdi, [rbp+290h+arg_28]
0x18015b02c  mov     r13, [rbp+290h+arg_30]
0x18015b033  xorps   xmm0, xmm0
0x18015b036  xor     eax, eax
0x18015b038  movups  xmmword ptr [rbp+290h+value], xmm0
0x18015b03c  movups  xmmword ptr [rbp+290h+value+10h], xmm0
0x18015b040  mov     qword ptr [rbp+290h+value+20h], rax
0x18015b044  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015b04b  movdqu  xmmword ptr [rbp+290h+ActivityId.Data1], xmm0
0x18015b053  lea     rdx, [rbp+290h+ActivityId]; ActivityId
0x18015b05a  lea     ecx, [rax+1]; ControlCode
0x18015b05d  call    cs:__imp_EventActivityIdControl
0x18015b064  nop     dword ptr [rax+rax+00h]
0x18015b069  lea     r9, [rbp+290h+value]; value
0x18015b06d  mov     rcx, rsi; context
0x18015b070  call    MI_Context_GetCustomOption_1
0x18015b075  xor     ebx, ebx
0x18015b077  test    eax, eax
0x18015b079  jnz     short loc_18015B092
0x18015b07b  lea     rdx, [rbp+290h+ActivityId]; pclsid
0x18015b082  mov     rcx, qword ptr [rbp+290h+value]; lpsz
0x18015b086  call    cs:__imp_CLSIDFromString
0x18015b08d  nop     dword ptr [rax+rax+00h]
0x18015b092  mov     rcx, qword ptr [rbp+290h+ActivityId.Data1]
0x18015b099  mov     [rbp+290h+var_60], rcx
0x18015b0a0  mov     rax, qword ptr [rbp+290h+ActivityId.Data4]
0x18015b0a7  mov     [rbp+290h+var_58], rax
0x18015b0ae  mov     qword ptr [rbp+290h+var_50.Data1], rcx
0x18015b0b5  mov     qword ptr [rbp+290h+var_50.Data4], rax
0x18015b0bc  lea     rdx, [rbp+290h+var_50]; ActivityId
0x18015b0c3  mov     ecx, 4; ControlCode
0x18015b0c8  call    cs:__imp_EventActivityIdControl
0x18015b0cf  nop     dword ptr [rax+rax+00h]
0x18015b0d4  mov     eax, cs:dword_18039EB68
0x18015b0da  lea     rcx, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015b0e1  cmp     eax, 5
0x18015b0e4  jbe     short loc_18015B113
0x18015b0e6  mov     [rsp+390h+var_318], 177h
0x18015b0ee  mov     [rsp+390h+var_320], rcx
0x18015b0f3  lea     rax, [rsp+390h+var_318]
0x18015b0f8  mov     [rsp+390h+var_368], rax
0x18015b0fd  lea     rax, [rsp+390h+var_320]
0x18015b102  mov     qword ptr [rsp+390h+var_370], rax
0x18015b107  lea     rdx, byte_18035DE9F
0x18015b10e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015b113  mov     [rbp+290h+instance.ft], rbx
0x18015b11a  xor     edx, edx; Val
0x18015b11c  mov     r8d, 198h; Size
0x18015b122  lea     rcx, [rbp+290h+instance.classDecl]; void *
0x18015b129  call    memset_0
0x18015b12e  xorps   xmm0, xmm0
0x18015b131  xor     eax, eax
0x18015b133  movups  [rbp+290h+var_2A0], xmm0
0x18015b137  mov     [rbp+290h+var_290], rax
0x18015b13b  mov     [rbp+290h+var_310], rbx
0x18015b13f  lea     rcx, [rbp+290h+var_310]
0x18015b143  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015b148  mov     [rbp+290h+var_310], rbx
0x18015b14c  mov     r14d, ebx
0x18015b14f  lea     rcx, [rbp+290h+var_2C0]; this
0x18015b153  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015b158  mov     rcx, rsi; context
0x18015b15b  call    WspIsRemoteRequest
0x18015b160  mov     r12d, eax
0x18015b163  test    eax, eax
0x18015b165  jnz     short loc_18015B18A
0x18015b167  lea     rcx, [rbp+290h+var_2C0]; this
0x18015b16b  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015b170  cmp     [rdi+48h], bl
0x18015b173  jz      short loc_18015B187
0x18015b175  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18015b179  call    WspIsRemoteInstance
0x18015b17e  test    al, al
0x18015b180  lea     r14d, [r12+1]
0x18015b185  jnz     short loc_18015B18A
0x18015b187  mov     r14d, ebx
0x18015b18a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015b191  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015b196  mov     ebx, eax
0x18015b198  test    eax, eax
0x18015b19a  jnz     loc_18015B391
0x18015b1a0  mov     dword ptr [rbp+290h+var_2A0], 0Bh
0x18015b1a7  mov     rax, [rdi+40h]
0x18015b1ab  mov     qword ptr [rbp+290h+var_2A0+8], rax
0x18015b1af  mov     rbx, [r15]
0x18015b1b2  lea     rcx, [rbp+290h+var_310]
0x18015b1b6  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015b1bb  mov     [rsp+390h+var_370], 1; int
0x18015b1c3  lea     r9, [rbp+290h+var_310]; struct ISpWmiObject **
0x18015b1c7  lea     r8, [rbp+290h+var_2A0]; struct _SP_OBJECT_ID *
0x18015b1cb  mov     rdx, rsi; context
0x18015b1ce  mov     rcx, rbx; this
0x18015b1d1  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015b1d6  mov     ebx, eax
0x18015b1d8  test    eax, eax
0x18015b1da  jz      short loc_18015B230
0x18015b1dc  mov     eax, cs:dword_18039EB68
0x18015b1e2  cmp     eax, 2
0x18015b1e5  jbe     loc_18015B37C
0x18015b1eb  mov     [rsp+390h+var_318], ebx
0x18015b1ef  mov     [rbp+290h+var_2F8], 197h
0x18015b1f6  lea     rax, [rsp+390h+var_318]
0x18015b1fb  mov     [rsp+390h+var_360], rax
0x18015b200  lea     rax, [rbp+290h+var_2F8]
0x18015b204  lea     rdx, unk_18035C7E8
0x18015b20b  mov     [rsp+390h+var_368], rax
0x18015b210  lea     rax, [rsp+390h+var_320]
0x18015b215  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015b21c  mov     [rsp+390h+var_320], r13
0x18015b221  mov     qword ptr [rsp+390h+var_370], rax
0x18015b226  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015b22b  jmp     loc_18015B383
0x18015b230  mov     r8, [rdi+40h]
0x18015b234  mov     rdx, rsi
0x18015b237  mov     rcx, [r15]
0x18015b23a  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18015b23f  cmp     eax, 3
0x18015b242  jnb     short loc_18015B278
0x18015b244  mov     ebx, 7
0x18015b249  mov     eax, cs:dword_18039EB68
0x18015b24f  cmp     eax, 2
0x18015b252  jbe     loc_18015B37C
0x18015b258  mov     dword ptr [rbp+290h+var_2F0], ebx
0x18015b25b  mov     dword ptr [rbp+290h+var_2E8], 1A2h
0x18015b262  lea     rax, [rbp+290h+var_2F0]
0x18015b266  mov     [rsp+390h+var_360], rax
0x18015b26b  lea     rax, [rbp+290h+var_2E8]
0x18015b26f  lea     rdx, byte_18035D1E5
0x18015b276  jmp     short loc_18015B20B
0x18015b278  lea     r8, [rbp+290h+instance]; instance
0x18015b27f  lea     rdx, SPACES_StoragePool_CreateVirtualDisk3_rtti; methodDecl
0x18015b286  mov     rcx, rsi; context
0x18015b289  call    MI_Context_ConstructParameters
0x18015b28e  mov     ebx, eax
0x18015b290  test    eax, eax
0x18015b292  jz      short loc_18015B2C6
0x18015b294  mov     eax, cs:dword_18039EB68
0x18015b29a  cmp     eax, 2
0x18015b29d  jbe     loc_18015B37C
0x18015b2a3  mov     dword ptr [rbp+290h+var_2E0], ebx
0x18015b2a6  mov     dword ptr [rbp+290h+var_2D8], 1AAh
0x18015b2ad  lea     rax, [rbp+290h+var_2E0]
0x18015b2b1  mov     [rsp+390h+var_360], rax
0x18015b2b6  lea     rax, [rbp+290h+var_2D8]
0x18015b2ba  lea     rdx, word_18035C15A
0x18015b2c1  jmp     loc_18015B20B
0x18015b2c6  mov     rcx, [rbp+290h+var_310]
0x18015b2ca  mov     rax, [rcx]
0x18015b2cd  lea     rdx, [rbp+290h+instance]
0x18015b2d4  mov     qword ptr [rsp+390h+var_370], rdx
0x18015b2d9  mov     r9, r13
0x18015b2dc  mov     r8, rsi
0x18015b2df  mov     edx, 0B0017h
0x18015b2e4  mov     rax, [rax+30h]
0x18015b2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b2ed  mov     ebx, eax
0x18015b2ef  test    eax, eax
0x18015b2f1  jz      short loc_18015B321
0x18015b2f3  mov     eax, cs:dword_18039EB68
0x18015b2f9  cmp     eax, 2
0x18015b2fc  jbe     short loc_18015B37C
0x18015b2fe  mov     dword ptr [rbp+290h+var_2D0], ebx
0x18015b301  mov     dword ptr [rbp+290h+var_308], 1B5h
0x18015b308  lea     rax, [rbp+290h+var_2D0]
0x18015b30c  mov     [rsp+390h+var_360], rax
0x18015b311  lea     rax, [rbp+290h+var_308]
0x18015b315  lea     rdx, word_18035E136
0x18015b31c  jmp     loc_18015B20B
0x18015b321  lea     rdx, [rbp+290h+instance]
0x18015b328  mov     rcx, rsi; self
0x18015b32b  call    MI_Instance_Destruct
0x18015b330  mov     ebx, eax
0x18015b332  test    eax, eax
0x18015b334  jz      short loc_18015B37C
0x18015b336  mov     eax, cs:dword_18039EB68
0x18015b33c  cmp     eax, 2
0x18015b33f  jbe     short loc_18015B37C
0x18015b341  mov     [rsp+390h+var_314], ebx
0x18015b345  mov     dword ptr [rsp+390h+var_320], 1BDh
0x18015b34d  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015b354  mov     [rbp+290h+var_308], r13
0x18015b358  lea     rax, [rsp+390h+var_314]
0x18015b35d  mov     [rsp+390h+var_360], rax
0x18015b362  lea     rax, [rsp+390h+var_320]
0x18015b367  mov     [rsp+390h+var_368], rax
0x18015b36c  lea     rax, [rbp+290h+var_308]
0x18015b370  lea     rdx, word_18035D59E
0x18015b377  jmp     loc_18015B221
0x18015b37c  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015b383  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015b38a  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015b38f  jmp     short loc_18015B398
0x18015b391  lea     r13, aSpacesStoragep_31; "SPACES_StoragePool_Invoke_CreateVirtual"...
0x18015b398  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18015b39c  xor     r15d, r15d
0x18015b39f  mov     [rsp+390h+var_368], r15; unsigned __int16 *
0x18015b3a4  mov     [rsp+390h+var_370], ebx; enum _MI_Result
0x18015b3a8  lea     r9, [rbp+290h+var_1D0]; struct _MI_ConstUint32Field *
0x18015b3af  mov     rdx, [rbp+290h+var_2C8]; unsigned __int16 *
0x18015b3b3  mov     rcx, [rbp+290h+var_300]; unsigned __int16 *
0x18015b3b7  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18015b3bc  test    r12d, r12d
0x18015b3bf  jnz     loc_18015B562
0x18015b3c5  lea     rcx, [rbp+290h+var_2C0]; this
0x18015b3c9  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015b3ce  mov     eax, cs:dword_18039EB68
0x18015b3d4  cmp     eax, 5
0x18015b3d7  jbe     loc_18015B562
0x18015b3dd  mov     rdx, 400000000000h
0x18015b3e7  lea     rcx, dword_18039EB68
0x18015b3ee  call    _tlgKeywordOn
0x18015b3f3  test    al, al
0x18015b3f5  jz      loc_18015B562
0x18015b3fb  cmp     [rbp+290h+var_88], r15b
0x18015b402  jz      short loc_18015B43F
0x18015b404  mov     rax, [rbp+290h+var_90]
0x18015b40b  movups  xmm0, xmmword ptr [rax]
0x18015b40e  movaps  xmmword ptr [rbp+290h+var_280.ft], xmm0
0x18015b412  movups  xmm1, xmmword ptr [rax+10h]
0x18015b416  movaps  xmmword ptr [rbp+290h+var_280.serverName], xmm1
0x18015b41a  movups  xmm0, xmmword ptr [rax+20h]
0x18015b41e  movaps  xmmword ptr [rbp+290h+var_280.reserved], xmm0
0x18015b422  movups  xmm1, xmmword ptr [rax+30h]
0x18015b426  movaps  xmmword ptr [rbp+290h+var_280.reserved+10h], xmm1
0x18015b42a  xor     r8d, r8d; unsigned __int16 *
0x18015b42d  lea     rdx, [rbp+290h+var_280]; struct _MI_Instance
0x18015b431  lea     rcx, name; "ObjectId"
0x18015b438  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015b43d  jmp     short loc_18015B442
0x18015b43f  mov     rax, r15
0x18015b442  mov     [rbp+290h+var_300], rax
0x18015b446  cmp     [rbp+290h+var_98], r15b
0x18015b44d  jz      short loc_18015B48A
0x18015b44f  mov     rax, [rbp+290h+var_A0]
0x18015b456  movups  xmm0, xmmword ptr [rax]
0x18015b459  movaps  xmmword ptr [rbp+290h+var_280.ft], xmm0
0x18015b45d  movups  xmm1, xmmword ptr [rax+10h]
0x18015b461  movaps  xmmword ptr [rbp+290h+var_280.serverName], xmm1
0x18015b465  movups  xmm0, xmmword ptr [rax+20h]
0x18015b469  movaps  xmmword ptr [rbp+290h+var_280.reserved], xmm0
0x18015b46d  movups  xmm1, xmmword ptr [rax+30h]
0x18015b471  movaps  xmmword ptr [rbp+290h+var_280.reserved+10h], xmm1
0x18015b475  xor     r8d, r8d; unsigned __int16 *
0x18015b478  lea     rdx, [rbp+290h+var_280]; struct _MI_Instance
0x18015b47c  lea     rcx, name; "ObjectId"
0x18015b483  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015b488  jmp     short loc_18015B48D
0x18015b48a  mov     rax, r15
0x18015b48d  mov     [rbp+290h+var_2C8], rax
0x18015b491  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18015b498  mov     [rbp+290h+var_2D0], rax
0x18015b49c  mov     rax, [rbp+290h+var_2B8]
0x18015b4a0  sub     rax, [rbp+290h+var_2C0]
0x18015b4a4  imul    rax, 3E8h
0x18015b4ab  xor     edx, edx
0x18015b4ad  div     [rbp+290h+var_2B0]
0x18015b4b1  mov     [rbp+290h+var_2D8], rax
0x18015b4b5  mov     dword ptr [rsp+390h+var_320], ebx
0x18015b4b9  mov     al, [rbp+290h+var_1D0.exists]
0x18015b4bf  neg     al
0x18015b4c1  sbb     ecx, ecx
0x18015b4c3  and     ecx, [rbp+290h+var_1D0.value]
0x18015b4c9  mov     [rsp+390h+var_314], ecx
0x18015b4cd  mov     dword ptr [rbp+290h+var_308], r14d
0x18015b4d1  cmp     [rdi+48h], r15b
0x18015b4d5  jz      short loc_18015B4DD
0x18015b4d7  mov     rax, [rdi+40h]
0x18015b4db  jmp     short loc_18015B4E0
0x18015b4dd  mov     rax, r15
0x18015b4e0  mov     [rbp+290h+var_2E0], rax
0x18015b4e4  lea     rax, aCreatevirtuald_2; "CreateVirtualDisk"
0x18015b4eb  mov     [rbp+290h+var_2E8], rax
0x18015b4ef  lea     rax, aStoragepool_0; "StoragePool"
0x18015b4f6  mov     [rbp+290h+var_2F0], rax
0x18015b4fa  lea     rax, [rbp+290h+var_300]
0x18015b4fe  mov     [rsp+390h+var_328], rax
0x18015b503  lea     rax, [rbp+290h+var_2C8]
0x18015b507  mov     [rsp+390h+var_330], rax
0x18015b50c  lea     rax, [rbp+290h+var_2D0]
0x18015b510  mov     [rsp+390h+var_338], rax
0x18015b515  lea     rax, [rbp+290h+var_2D8]
0x18015b519  mov     [rsp+390h+var_340], rax
  ... truncated ...
```
