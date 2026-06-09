# SPACES_VirtualDisk_Invoke_Repair

- ea: `0x18013c490`
- end: `0x18013c9fc`
- name: `SPACES_VirtualDisk_Invoke_Repair`
- size: `1388`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

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
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x18013c490`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c50d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c56c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c9cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c50d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c56c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c9cc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013c530`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013c530`

## string_xrefs

- `0x18013c578`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x18013c6a5`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x18013c78e`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x18013c7bd`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x18013c7d5`: `SPACES_VirtualDisk_Invoke_Repair`
- `0x18013c8d7`: `Repair`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_Repair(
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
  int v13; // r14d
  int IsRemoteRequest; // r12d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int16 *v20; // rdx
  const char **v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int16 *v24; // rax
  const MI_Char *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned __int16 *v30; // [rsp+28h] [rbp-D8h]
  const char *v31; // [rsp+70h] [rbp-90h] BYREF
  MI_Uint32 v32; // [rsp+78h] [rbp-88h] BYREF
  struct ISpWmiObject *v33; // [rsp+80h] [rbp-80h] BYREF
  const char *v34; // [rsp+88h] [rbp-78h] BYREF
  const char *v35; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v36; // [rsp+98h] [rbp-68h] BYREF
  const char *v37; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v38; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v41; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v42[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v43; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-8h]
  struct _MI_Instance v45; // [rsp+100h] [rbp+0h] BYREF
  MI_Value value; // [rsp+140h] [rbp+40h] BYREF
  MI_Instance instance; // [rsp+170h] [rbp+70h] BYREF
  struct _MI_ConstUint32Field v48; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _MI_Instance *v49; // [rsp+1B8h] [rbp+B8h]
  char v50; // [rsp+1C0h] [rbp+C0h]
  GUID ActivityId; // [rsp+1E0h] [rbp+E0h] BYREF
  GUID v52; // [rsp+1F0h] [rbp+F0h]
  GUID v53; // [rsp+200h] [rbp+100h] BYREF

  v36 = a4;
  v41 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v52 = ActivityId;
  v53 = ActivityId;
  EventActivityIdControl(4u, &v53);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v34) = 362;
    v31 = "SPACES_VirtualDisk_Invoke_Repair";
    v30 = (unsigned __int16 *)&v34;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_VirtualDisk_Invoke_Repair",
      (__int64)byte_18034B545,
      v11,
      v12,
      &v31);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x60u);
  v43 = 0;
  v44 = 0;
  v33 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v33);
  v33 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v42);
  v13 = 0;
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v42);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = 0;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v43) = 16;
    *((_QWORD *)&v43 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v33);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v43, &v33, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
      {
LABEL_24:
        MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
        goto LABEL_25;
      }
      LODWORD(v34) = v15;
      LODWORD(v37) = 393;
      v20 = (__int16 *)byte_18034ADE9;
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_Repair_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_24;
        LODWORD(v38) = v15;
        LODWORD(v39) = 401;
        v20 = word_18034B98A;
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v33 + 48LL))(
                v33,
                1048579,
                a2,
                a7,
                &instance,
                v30);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_24;
          v32 = v15;
          LODWORD(v31) = 420;
          v35 = "SPACES_VirtualDisk_Invoke_Repair";
          v21 = &v35;
          v20 = word_18034C4FA;
          goto LABEL_14;
        }
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_24;
        LODWORD(v40) = v15;
        LODWORD(v35) = 412;
        v20 = (__int16 *)byte_18034C0F3;
      }
    }
    v21 = &v31;
    v31 = "SPACES_VirtualDisk_Invoke_Repair";
LABEL_14:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (__int64)v20,
      v18,
      v19,
      v21);
    goto LABEL_24;
  }
LABEL_25:
  SmLogOnMethodFailure(v36, v41, a6 + 4, &v48, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v42);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( v50 )
        {
          v45 = *v49;
          v24 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v45, 0);
        }
        else
        {
          v24 = 0;
        }
        v36 = v24;
        v41 = 0;
        v40 = 0;
        v39 = (unsigned __int64)(1000LL * (v42[1] - v42[0])) / v42[2];
        LODWORD(v31) = v15;
        v32 = v48.exists != 0 ? v48.value : 0;
        LODWORD(v35) = v13;
        if ( a6[4].exists )
          v25 = a6[4].value;
        else
          v25 = 0;
        v38 = v25;
        v37 = "Repair";
        v34 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v48.exists != 0 ? v48.value : 0,
          (__int64)&dword_18034BFD4,
          v22,
          v23,
          &v34,
          &v37,
          &v38,
          (__int64)&v35,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v39,
          &v40,
          &v41,
          &v36);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v31) = 453;
    v36 = (unsigned __int16 *)"SPACES_VirtualDisk_Invoke_Repair";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v26,
      (__int64)&byte_18034BFA7,
      v27,
      v28,
      &v36);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v42);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v33);
  return EventActivityIdControl(4u, &v53);
}

```

## disassembly

```asm
0x18013c490  mov     [rsp-8+arg_10], rbx
0x18013c495  push    rbp
0x18013c496  push    rsi
0x18013c497  push    rdi
0x18013c498  push    r12
0x18013c49a  push    r13
0x18013c49c  push    r14
0x18013c49e  push    r15
0x18013c4a0  lea     rbp, [rsp-120h]
0x18013c4a8  sub     rsp, 220h
0x18013c4af  mov     rax, cs:__security_cookie
0x18013c4b6  xor     rax, rsp
0x18013c4b9  mov     [rbp+150h+var_40], rax
0x18013c4c0  mov     [rbp+150h+var_1B8], r9
0x18013c4c4  mov     rdi, rdx
0x18013c4c7  mov     r15, rcx
0x18013c4ca  mov     rax, [rbp+150h+arg_20]
0x18013c4d1  mov     [rbp+150h+var_190], rax
0x18013c4d5  mov     rsi, [rbp+150h+arg_28]
0x18013c4dc  mov     r13, [rbp+150h+arg_30]
0x18013c4e3  xorps   xmm0, xmm0
0x18013c4e6  xor     eax, eax
0x18013c4e8  movups  xmmword ptr [rbp+150h+value], xmm0
0x18013c4ec  movups  xmmword ptr [rbp+150h+value+10h], xmm0
0x18013c4f0  mov     qword ptr [rbp+150h+value+20h], rax
0x18013c4f4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013c4fb  movdqu  xmmword ptr [rbp+150h+ActivityId.Data1], xmm0
0x18013c503  lea     rdx, [rbp+150h+ActivityId]; ActivityId
0x18013c50a  lea     ecx, [rax+1]; ControlCode
0x18013c50d  call    cs:__imp_EventActivityIdControl
0x18013c513  lea     r9, [rbp+150h+value]; value
0x18013c517  mov     rcx, rdi; context
0x18013c51a  call    MI_Context_GetCustomOption_1
0x18013c51f  xor     ebx, ebx
0x18013c521  test    eax, eax
0x18013c523  jnz     short loc_18013C536
0x18013c525  lea     rdx, [rbp+150h+ActivityId]; pclsid
0x18013c52c  mov     rcx, qword ptr [rbp+150h+value]; lpsz
0x18013c530  call    cs:__imp_CLSIDFromString
0x18013c536  mov     rcx, qword ptr [rbp+150h+ActivityId.Data1]
0x18013c53d  mov     [rbp+150h+var_60], rcx
0x18013c544  mov     rax, qword ptr [rbp+150h+ActivityId.Data4]
0x18013c54b  mov     [rbp+150h+var_58], rax
0x18013c552  mov     qword ptr [rbp+150h+var_50.Data1], rcx
0x18013c559  mov     qword ptr [rbp+150h+var_50.Data4], rax
0x18013c560  lea     rdx, [rbp+150h+var_50]; ActivityId
0x18013c567  mov     ecx, 4; ControlCode
0x18013c56c  call    cs:__imp_EventActivityIdControl
0x18013c572  mov     eax, cs:dword_180397B68
0x18013c578  lea     rcx, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x18013c57f  cmp     eax, 5
0x18013c582  jbe     short loc_18013C5AF
0x18013c584  mov     dword ptr [rbp+150h+var_1C8], 16Ah
0x18013c58b  mov     [rsp+250h+var_1E0], rcx
0x18013c590  lea     rax, [rbp+150h+var_1C8]
0x18013c594  mov     [rsp+250h+var_228], rax
0x18013c599  lea     rax, [rsp+250h+var_1E0]
0x18013c59e  mov     qword ptr [rsp+250h+var_230], rax
0x18013c5a3  lea     rdx, byte_18034B545
0x18013c5aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013c5af  mov     [rbp+150h+instance.ft], rbx
0x18013c5b3  xor     edx, edx; Val
0x18013c5b5  lea     r8d, [rdx+60h]; Size
0x18013c5b9  lea     rcx, [rbp+150h+instance.classDecl]; void *
0x18013c5bd  call    memset_0
0x18013c5c2  xorps   xmm0, xmm0
0x18013c5c5  xor     eax, eax
0x18013c5c7  movups  [rbp+150h+var_168], xmm0
0x18013c5cb  mov     [rbp+150h+var_158], rax
0x18013c5cf  mov     [rbp+150h+var_1D0], rbx
0x18013c5d3  lea     rcx, [rbp+150h+var_1D0]
0x18013c5d7  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013c5dc  mov     [rbp+150h+var_1D0], rbx
0x18013c5e0  lea     rcx, [rbp+150h+var_188]; this
0x18013c5e4  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013c5e9  mov     r14d, ebx
0x18013c5ec  mov     rcx, rdi; context
0x18013c5ef  call    WspIsRemoteRequest
0x18013c5f4  mov     r12d, eax
0x18013c5f7  test    eax, eax
0x18013c5f9  jnz     short loc_18013C61E
0x18013c5fb  lea     rcx, [rbp+150h+var_188]; this
0x18013c5ff  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013c604  cmp     [rsi+48h], bl
0x18013c607  jz      short loc_18013C61B
0x18013c609  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18013c60d  call    WspIsRemoteInstance
0x18013c612  test    al, al
0x18013c614  lea     r14d, [r12+1]
0x18013c619  jnz     short loc_18013C61E
0x18013c61b  mov     r14d, ebx
0x18013c61e  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013c625  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013c62a  mov     ebx, eax
0x18013c62c  test    eax, eax
0x18013c62e  jnz     loc_18013C7D2
0x18013c634  mov     dword ptr [rbp+150h+var_168], 10h
0x18013c63b  mov     rax, [rsi+40h]
0x18013c63f  mov     qword ptr [rbp+150h+var_168+8], rax
0x18013c643  mov     rbx, [r15]
0x18013c646  lea     rcx, [rbp+150h+var_1D0]
0x18013c64a  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013c64f  mov     [rsp+250h+var_230], 1; int
0x18013c657  lea     r9, [rbp+150h+var_1D0]; struct ISpWmiObject **
0x18013c65b  lea     r8, [rbp+150h+var_168]; struct _SP_OBJECT_ID *
0x18013c65f  mov     rdx, rdi; context
0x18013c662  mov     rcx, rbx; this
0x18013c665  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013c66a  mov     ebx, eax
0x18013c66c  xor     r15d, r15d
0x18013c66f  test    eax, eax
0x18013c671  jz      short loc_18013C6C5
0x18013c673  mov     eax, cs:dword_180397B68
0x18013c679  cmp     eax, 2
0x18013c67c  jbe     loc_18013C7BD
0x18013c682  mov     dword ptr [rbp+150h+var_1C8], ebx
0x18013c685  mov     dword ptr [rbp+150h+var_1B0], 189h
0x18013c68c  lea     rax, [rbp+150h+var_1C8]
0x18013c690  mov     [rsp+250h+var_220], rax
0x18013c695  lea     rax, [rbp+150h+var_1B0]
0x18013c699  lea     rdx, byte_18034ADE9
0x18013c6a0  mov     [rsp+250h+var_228], rax
0x18013c6a5  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x18013c6ac  lea     rax, [rsp+250h+var_1E0]
0x18013c6b1  mov     [rsp+250h+var_1E0], r13
0x18013c6b6  mov     qword ptr [rsp+250h+var_230], rax
0x18013c6bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013c6c0  jmp     loc_18013C7C4
0x18013c6c5  lea     r8, [rbp+150h+instance]; instance
0x18013c6c9  lea     rdx, SPACES_VirtualDisk_Repair_rtti; methodDecl
0x18013c6d0  mov     rcx, rdi; context
0x18013c6d3  call    MI_Context_ConstructParameters
0x18013c6d8  mov     ebx, eax
0x18013c6da  test    eax, eax
0x18013c6dc  jz      short loc_18013C70D
0x18013c6de  mov     eax, cs:dword_180397B68
0x18013c6e4  cmp     eax, 2
0x18013c6e7  jbe     loc_18013C7BD
0x18013c6ed  mov     dword ptr [rbp+150h+var_1A8], ebx
0x18013c6f0  mov     dword ptr [rbp+150h+var_1A0], 191h
0x18013c6f7  lea     rax, [rbp+150h+var_1A8]
0x18013c6fb  mov     [rsp+250h+var_220], rax
0x18013c700  lea     rax, [rbp+150h+var_1A0]
0x18013c704  lea     rdx, word_18034B98A
0x18013c70b  jmp     short loc_18013C6A0
0x18013c70d  mov     rcx, [rbp+150h+var_1D0]
0x18013c711  mov     rax, [rcx]
0x18013c714  lea     rdx, [rbp+150h+instance]
0x18013c718  mov     qword ptr [rsp+250h+var_230], rdx
0x18013c71d  mov     r9, r13
0x18013c720  mov     r8, rdi
0x18013c723  mov     edx, 100003h
0x18013c728  mov     rax, [rax+30h]
0x18013c72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c731  mov     ebx, eax
0x18013c733  test    eax, eax
0x18013c735  jz      short loc_18013C765
0x18013c737  mov     eax, cs:dword_180397B68
0x18013c73d  cmp     eax, 2
0x18013c740  jbe     short loc_18013C7BD
0x18013c742  mov     dword ptr [rbp+150h+var_198], ebx
0x18013c745  mov     dword ptr [rbp+150h+var_1C0], 19Ch
0x18013c74c  lea     rax, [rbp+150h+var_198]
0x18013c750  mov     [rsp+250h+var_220], rax
0x18013c755  lea     rax, [rbp+150h+var_1C0]
0x18013c759  lea     rdx, byte_18034C0F3
0x18013c760  jmp     loc_18013C6A0
0x18013c765  lea     rdx, [rbp+150h+instance]
0x18013c769  mov     rcx, rdi; self
0x18013c76c  call    MI_Instance_Destruct
0x18013c771  mov     ebx, eax
0x18013c773  test    eax, eax
0x18013c775  jz      short loc_18013C7BD
0x18013c777  mov     eax, cs:dword_180397B68
0x18013c77d  cmp     eax, 2
0x18013c780  jbe     short loc_18013C7BD
0x18013c782  mov     [rsp+250h+var_1D8], ebx
0x18013c786  mov     dword ptr [rsp+250h+var_1E0], 1A4h
0x18013c78e  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x18013c795  mov     [rbp+150h+var_1C0], r13
0x18013c799  lea     rax, [rsp+250h+var_1D8]
0x18013c79e  mov     [rsp+250h+var_220], rax
0x18013c7a3  lea     rax, [rsp+250h+var_1E0]
0x18013c7a8  mov     [rsp+250h+var_228], rax
0x18013c7ad  lea     rax, [rbp+150h+var_1C0]
0x18013c7b1  lea     rdx, word_18034C4FA
0x18013c7b8  jmp     loc_18013C6B6
0x18013c7bd  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x18013c7c4  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013c7cb  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013c7d0  jmp     short loc_18013C7DC
0x18013c7d2  xor     r15d, r15d
0x18013c7d5  lea     r13, aSpacesVirtuald_32; "SPACES_VirtualDisk_Invoke_Repair"
0x18013c7dc  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18013c7e0  mov     [rsp+250h+var_228], r15; unsigned __int16 *
0x18013c7e5  mov     [rsp+250h+var_230], ebx; enum _MI_Result
0x18013c7e9  lea     r9, [rbp+150h+var_A0]; struct _MI_ConstUint32Field *
0x18013c7f0  mov     rdx, [rbp+150h+var_190]; unsigned __int16 *
0x18013c7f4  mov     rcx, [rbp+150h+var_1B8]; unsigned __int16 *
0x18013c7f8  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013c7fd  test    r12d, r12d
0x18013c800  jnz     loc_18013C955
0x18013c806  lea     rcx, [rbp+150h+var_188]; this
0x18013c80a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013c80f  mov     eax, cs:dword_180397B68
0x18013c815  cmp     eax, 5
0x18013c818  jbe     loc_18013C955
0x18013c81e  mov     rdx, 400000000000h
0x18013c828  lea     rcx, dword_180397B68
0x18013c82f  call    _tlgKeywordOn
0x18013c834  test    al, al
0x18013c836  jz      loc_18013C955
0x18013c83c  cmp     [rbp+150h+var_90], r15b
0x18013c843  jz      short loc_18013C880
0x18013c845  mov     rax, [rbp+150h+var_98]
0x18013c84c  movups  xmm0, xmmword ptr [rax]
0x18013c84f  movaps  xmmword ptr [rbp+150h+var_150.ft], xmm0
0x18013c853  movups  xmm1, xmmword ptr [rax+10h]
0x18013c857  movaps  xmmword ptr [rbp+150h+var_150.serverName], xmm1
0x18013c85b  movups  xmm0, xmmword ptr [rax+20h]
0x18013c85f  movaps  xmmword ptr [rbp+150h+var_150.reserved], xmm0
0x18013c863  movups  xmm1, xmmword ptr [rax+30h]
0x18013c867  movaps  xmmword ptr [rbp+150h+var_150.reserved+10h], xmm1
0x18013c86b  xor     r8d, r8d; unsigned __int16 *
0x18013c86e  lea     rdx, [rbp+150h+var_150]; struct _MI_Instance
0x18013c872  lea     rcx, name; "ObjectId"
0x18013c879  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18013c87e  jmp     short loc_18013C883
0x18013c880  mov     rax, r15
0x18013c883  mov     [rbp+150h+var_1B8], rax
0x18013c887  mov     [rbp+150h+var_190], r15
0x18013c88b  mov     [rbp+150h+var_198], r15
0x18013c88f  mov     rax, [rbp+150h+var_180]
0x18013c893  sub     rax, [rbp+150h+var_188]
0x18013c897  imul    rax, 3E8h
0x18013c89e  xor     edx, edx
0x18013c8a0  div     [rbp+150h+var_178]
0x18013c8a4  mov     [rbp+150h+var_1A0], rax
0x18013c8a8  mov     dword ptr [rsp+250h+var_1E0], ebx
0x18013c8ac  mov     al, [rbp+150h+var_A0.exists]
0x18013c8b2  neg     al
0x18013c8b4  sbb     ecx, ecx
0x18013c8b6  and     ecx, [rbp+150h+var_A0.value]
0x18013c8bc  mov     [rsp+250h+var_1D8], ecx
0x18013c8c0  mov     dword ptr [rbp+150h+var_1C0], r14d
0x18013c8c4  cmp     [rsi+48h], r15b
0x18013c8c8  jz      short loc_18013C8D0
0x18013c8ca  mov     rax, [rsi+40h]
0x18013c8ce  jmp     short loc_18013C8D3
0x18013c8d0  mov     rax, r15
0x18013c8d3  mov     [rbp+150h+var_1A8], rax
0x18013c8d7  lea     rax, aRepair_0; "Repair"
0x18013c8de  mov     [rbp+150h+var_1B0], rax
0x18013c8e2  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013c8e9  mov     [rbp+150h+var_1C8], rax
0x18013c8ed  lea     rax, [rbp+150h+var_1B8]
0x18013c8f1  mov     [rsp+250h+var_1E8], rax
0x18013c8f6  lea     rax, [rbp+150h+var_190]
0x18013c8fa  mov     [rsp+250h+var_1F0], rax
0x18013c8ff  lea     rax, [rbp+150h+var_198]
0x18013c903  mov     [rsp+250h+var_1F8], rax
0x18013c908  lea     rax, [rbp+150h+var_1A0]
0x18013c90c  mov     [rsp+250h+var_200], rax
0x18013c911  lea     rax, [rsp+250h+var_1E0]
0x18013c916  mov     [rsp+250h+var_208], rax
0x18013c91b  lea     rax, [rsp+250h+var_1D8]
0x18013c920  mov     [rsp+250h+var_210], rax
0x18013c925  lea     rax, [rbp+150h+var_1C0]
0x18013c929  mov     [rsp+250h+var_218], rax
0x18013c92e  lea     rax, [rbp+150h+var_1A8]
0x18013c932  mov     [rsp+250h+var_220], rax
0x18013c937  lea     rax, [rbp+150h+var_1B0]
0x18013c93b  mov     [rsp+250h+var_228], rax
0x18013c940  lea     rax, [rbp+150h+var_1C8]
0x18013c944  mov     qword ptr [rsp+250h+var_230], rax
0x18013c949  lea     rdx, dword_18034BFD4
0x18013c950  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18013c955  lea     rcx, [rbp+150h+instance]; self
0x18013c959  call    MI_Instance_Destruct
0x18013c95e  mov     eax, cs:dword_180397B68
0x18013c964  cmp     eax, 5
0x18013c967  jbe     short loc_18013C994
0x18013c969  mov     dword ptr [rsp+250h+var_1E0], 1C5h
0x18013c971  mov     [rbp+150h+var_1B8], r13
0x18013c975  lea     rax, [rsp+250h+var_1E0]
0x18013c97a  mov     [rsp+250h+var_228], rax
0x18013c97f  lea     rax, [rbp+150h+var_1B8]
0x18013c983  mov     qword ptr [rsp+250h+var_230], rax
0x18013c988  lea     rdx, byte_18034BFA7
0x18013c98f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013c994  test    rdi, rdi
0x18013c997  jz      short loc_18013C9AE
0x18013c999  mov     rax, [rdi]
0x18013c99c  test    rax, rax
0x18013c99f  jz      short loc_18013C9AE
0x18013c9a1  mov     edx, ebx
0x18013c9a3  mov     rcx, rdi
0x18013c9a6  mov     rax, [rax]
0x18013c9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c9ae  lea     rcx, [rbp+150h+var_188]; this
  ... truncated ...
```
