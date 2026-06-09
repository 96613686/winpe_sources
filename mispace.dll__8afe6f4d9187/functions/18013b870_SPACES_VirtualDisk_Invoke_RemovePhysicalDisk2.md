# SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2

- ea: `0x18013b870`
- end: `0x18013bea2`
- name: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- size: `1586`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x1800047c0`
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
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180025444`
- `0x18007f384`
- `0x180137a24`
- `0x180138120`
- `0x18013b870`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b8de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b93d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013be72`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b8de`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b93d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013be72`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013b901`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013b901`

## string_xrefs

- `0x18013bd6e`: `RemovePhysicalDisk`
- `0x18013b949`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013ba5f`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013babc`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013bb1e`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013bbcd`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013bca2`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013be11`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2(
        CSpProvider **a1,
        struct _MI_Context *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  const MI_Char *v9; // rdx
  MI_Type *v10; // r8
  __int64 v11; // r8
  __int64 v12; // r9
  enum _MI_Result v13; // r15d
  int IsRemoteRequest; // r13d
  enum _MI_Result v15; // ebx
  CSpProvider *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const char **v20; // rax
  __int16 *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // eax
  const unsigned __int16 *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  const char **v31; // [rsp+28h] [rbp-D8h]
  const char *v32; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v33; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v34; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v35; // [rsp+90h] [rbp-70h] BYREF
  const char *v36; // [rsp+98h] [rbp-68h] BYREF
  const char *v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v42; // [rsp+C8h] [rbp-38h] BYREF
  const char *v43; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v44[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v45; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v46; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v47; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  int v50; // [rsp+1C0h] [rbp+C0h]
  char v51; // [rsp+1C4h] [rbp+C4h]
  struct _MI_Instance *v52; // [rsp+1E0h] [rbp+E0h]
  char v53; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v55; // [rsp+210h] [rbp+110h]
  GUID v56; // [rsp+220h] [rbp+120h] BYREF

  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v55 = ActivityId;
  v56 = ActivityId;
  EventActivityIdControl(4u, &v56);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v36) = 1680;
    v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
    v31 = &v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2",
      (__int64)&word_18034B366,
      v11,
      v12,
      &v32);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v45 = 0;
  v46 = 0;
  v35 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  v35 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v44);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v44);
    if ( !*(_BYTE *)(a6 + 72)
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64))) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v45) = 16;
    *((_QWORD *)&v45 + 1) = *(_QWORD *)(a6 + 64);
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v45, &v35, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v36) = v15;
        LODWORD(v38) = 1712;
        v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
        v20 = &v32;
        v21 = (__int16 *)&unk_18034ADB0;
        goto LABEL_26;
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_RemovePhysicalDisk2_rtti, &instance);
      if ( v15 == MI_RESULT_OK )
      {
        if ( v13 && *(_BYTE *)(a7 + 88) && *(_DWORD *)(a7 + 80) > 0x200u )
        {
          v50 = 5;
          v51 = 1;
          PostExtendedStatus(a2, &instance, 0x8022u, 1u, L"512");
        }
        else
        {
          v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, struct _MI_Context *, __int64, MI_Instance *, const char **))(*(_QWORD *)v35 + 48LL))(
                  v35,
                  1048590,
                  a2,
                  a7,
                  &instance,
                  v31);
          if ( v15 )
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_27;
            v33 = v15;
            LODWORD(v37) = 1758;
            v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
            v20 = &v32;
            v21 = word_18034BE72;
            goto LABEL_26;
          }
        }
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        v34 = v15;
        LODWORD(v32) = 1767;
        v37 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
        v20 = &v37;
        v21 = (__int16 *)&unk_18034C388;
LABEL_26:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (__int64)v21,
          v18,
          v19,
          v20);
        goto LABEL_27;
      }
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v41) = v15;
        LODWORD(v42) = 1731;
        v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
        v20 = &v32;
        v21 = word_18034AE22;
        goto LABEL_26;
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v39) = 7;
        LODWORD(v40) = 1723;
        v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
        v20 = &v32;
        v21 = &word_18034ABFE;
        goto LABEL_26;
      }
    }
LABEL_27:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v44);
    if ( (unsigned int)dword_180397B68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 88) )
          v24 = *(_DWORD *)(a7 + 80);
        else
          v24 = 0;
        LODWORD(v32) = v24;
        if ( v53 )
        {
          v47 = *v52;
          v25 = SmMIGetString(L"ObjectId", &v47, 0);
        }
        else
        {
          v25 = 0;
        }
        v42 = v25;
        v41 = 0;
        v40 = 0;
        v39 = (unsigned __int64)(1000LL * (v44[1] - v44[0])) / v44[2];
        v34 = v15;
        LODWORD(v37) = v51 != 0 ? v50 : 0;
        v33 = v13;
        if ( *(_BYTE *)(a6 + 72) )
          v26 = *(_QWORD *)(a6 + 64);
        else
          v26 = 0;
        v38 = v26;
        v36 = "RemovePhysicalDisk";
        v43 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v50 & (unsigned int)-(v51 != 0),
          (__int64)&word_18034B266,
          v22,
          v23,
          &v43,
          &v36,
          &v38,
          (__int64)&v33,
          (__int64)&v37,
          (__int64)&v34,
          (__int64)&v39,
          &v40,
          &v41,
          &v42);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v32) = 1795;
    v43 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)&dword_18034C624,
      v28,
      v29,
      &v43);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(struct _MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v44);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  return EventActivityIdControl(4u, &v56);
}

```

## disassembly

```asm
0x18013b870  mov     [rsp-8+arg_10], rbx
0x18013b875  push    rbp
0x18013b876  push    rsi
0x18013b877  push    rdi
0x18013b878  push    r12
0x18013b87a  push    r13
0x18013b87c  push    r14
0x18013b87e  push    r15
0x18013b880  lea     rbp, [rsp-140h]
0x18013b888  sub     rsp, 240h
0x18013b88f  mov     rax, cs:__security_cookie
0x18013b896  xor     rax, rsp
0x18013b899  mov     [rbp+170h+var_40], rax
0x18013b8a0  mov     rdi, rdx
0x18013b8a3  mov     r12, rcx
0x18013b8a6  mov     r14, [rbp+170h+arg_28]
0x18013b8ad  mov     rsi, [rbp+170h+arg_30]
0x18013b8b4  xorps   xmm0, xmm0
0x18013b8b7  xor     eax, eax
0x18013b8b9  movups  xmmword ptr [rbp+170h+value], xmm0
0x18013b8bd  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18013b8c1  mov     qword ptr [rbp+170h+value+20h], rax
0x18013b8c5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013b8cc  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18013b8d4  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18013b8db  lea     ecx, [rax+1]; ControlCode
0x18013b8de  call    cs:__imp_EventActivityIdControl
0x18013b8e4  lea     r9, [rbp+170h+value]; value
0x18013b8e8  mov     rcx, rdi; context
0x18013b8eb  call    MI_Context_GetCustomOption_1
0x18013b8f0  xor     ebx, ebx
0x18013b8f2  test    eax, eax
0x18013b8f4  jnz     short loc_18013B907
0x18013b8f6  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18013b8fd  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18013b901  call    cs:__imp_CLSIDFromString
0x18013b907  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18013b90e  mov     [rbp+170h+var_60], rcx
0x18013b915  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18013b91c  mov     [rbp+170h+var_58], rax
0x18013b923  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18013b92a  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18013b931  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18013b938  mov     ecx, 4; ControlCode
0x18013b93d  call    cs:__imp_EventActivityIdControl
0x18013b943  mov     eax, cs:dword_180397B68
0x18013b949  lea     rcx, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b950  cmp     eax, 5
0x18013b953  jbe     short loc_18013B97E
0x18013b955  mov     dword ptr [rbp+170h+var_1D8], 690h
0x18013b95c  mov     [rbp+170h+var_1F0], rcx
0x18013b960  lea     rax, [rbp+170h+var_1D8]
0x18013b964  mov     [rsp+270h+var_248], rax
0x18013b969  lea     rax, [rbp+170h+var_1F0]
0x18013b96d  mov     qword ptr [rsp+270h+var_250], rax
0x18013b972  lea     rdx, word_18034B366
0x18013b979  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013b97e  mov     [rbp+170h+instance.ft], rbx
0x18013b985  xor     edx, edx; Val
0x18013b987  lea     r8d, [rdx+78h]; Size
0x18013b98b  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18013b992  call    memset_0
0x18013b997  xorps   xmm0, xmm0
0x18013b99a  xor     eax, eax
0x18013b99c  movups  [rbp+170h+var_178], xmm0
0x18013b9a0  mov     [rbp+170h+var_168], rax
0x18013b9a4  mov     [rbp+170h+var_1E0], rbx
0x18013b9a8  lea     rcx, [rbp+170h+var_1E0]
0x18013b9ac  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013b9b1  mov     [rbp+170h+var_1E0], rbx
0x18013b9b5  mov     r15d, ebx
0x18013b9b8  lea     rcx, [rbp+170h+var_198]; this
0x18013b9bc  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013b9c1  mov     rcx, rdi; context
0x18013b9c4  call    WspIsRemoteRequest
0x18013b9c9  mov     r13d, eax
0x18013b9cc  test    eax, eax
0x18013b9ce  jnz     short loc_18013B9F3
0x18013b9d0  lea     rcx, [rbp+170h+var_198]; this
0x18013b9d4  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013b9d9  cmp     [r14+48h], bl
0x18013b9dd  jz      short loc_18013B9F0
0x18013b9df  mov     rcx, [r14+40h]; unsigned __int16 *
0x18013b9e3  call    WspIsRemoteInstance
0x18013b9e8  test    al, al
0x18013b9ea  lea     r15d, [r13+1]
0x18013b9ee  jnz     short loc_18013B9F3
0x18013b9f0  mov     r15d, ebx
0x18013b9f3  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013b9fa  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013b9ff  mov     ebx, eax
0x18013ba01  test    eax, eax
0x18013ba03  jnz     loc_18013BC0B
0x18013ba09  mov     dword ptr [rbp+170h+var_178], 10h
0x18013ba10  mov     rax, [r14+40h]
0x18013ba14  mov     qword ptr [rbp+170h+var_178+8], rax
0x18013ba18  mov     rbx, [r12]
0x18013ba1c  lea     rcx, [rbp+170h+var_1E0]
0x18013ba20  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013ba25  mov     [rsp+270h+var_250], 1; int
0x18013ba2d  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18013ba31  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18013ba35  mov     rdx, rdi; context
0x18013ba38  mov     rcx, rbx; this
0x18013ba3b  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013ba40  mov     ebx, eax
0x18013ba42  test    eax, eax
0x18013ba44  jz      short loc_18013BA8C
0x18013ba46  mov     eax, cs:dword_180397B68
0x18013ba4c  cmp     eax, 2
0x18013ba4f  jbe     loc_18013BBFF
0x18013ba55  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18013ba58  mov     dword ptr [rbp+170h+var_1C8], 6B0h
0x18013ba5f  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013ba66  mov     [rbp+170h+var_1F0], rax
0x18013ba6a  lea     rax, [rbp+170h+var_1D8]
0x18013ba6e  mov     [rsp+270h+var_240], rax
0x18013ba73  lea     rax, [rbp+170h+var_1C8]
0x18013ba77  mov     [rsp+270h+var_248], rax
0x18013ba7c  lea     rax, [rbp+170h+var_1F0]
0x18013ba80  lea     rdx, unk_18034ADB0
0x18013ba87  jmp     loc_18013BBF5
0x18013ba8c  mov     r8, [r14+40h]
0x18013ba90  mov     rdx, rdi
0x18013ba93  mov     rcx, [r12]
0x18013ba97  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18013ba9c  test    eax, eax
0x18013ba9e  jnz     short loc_18013BAE9
0x18013baa0  lea     ebx, [rax+7]
0x18013baa3  mov     eax, cs:dword_180397B68
0x18013baa9  cmp     eax, 2
0x18013baac  jbe     loc_18013BBFF
0x18013bab2  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18013bab5  mov     dword ptr [rbp+170h+var_1B8], 6BBh
0x18013babc  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013bac3  mov     [rbp+170h+var_1F0], rax
0x18013bac7  lea     rax, [rbp+170h+var_1C0]
0x18013bacb  mov     [rsp+270h+var_240], rax
0x18013bad0  lea     rax, [rbp+170h+var_1B8]
0x18013bad4  mov     [rsp+270h+var_248], rax
0x18013bad9  lea     rax, [rbp+170h+var_1F0]
0x18013badd  lea     rdx, word_18034ABFE
0x18013bae4  jmp     loc_18013BBF5
0x18013bae9  lea     r8, [rbp+170h+instance]; instance
0x18013baf0  lea     rdx, SPACES_VirtualDisk_RemovePhysicalDisk2_rtti; methodDecl
0x18013baf7  mov     rcx, rdi; context
0x18013bafa  call    MI_Context_ConstructParameters
0x18013baff  mov     ebx, eax
0x18013bb01  test    eax, eax
0x18013bb03  jz      short loc_18013BB4B
0x18013bb05  mov     eax, cs:dword_180397B68
0x18013bb0b  cmp     eax, 2
0x18013bb0e  jbe     loc_18013BBFF
0x18013bb14  mov     dword ptr [rbp+170h+var_1B0], ebx
0x18013bb17  mov     dword ptr [rbp+170h+var_1A8], 6C3h
0x18013bb1e  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013bb25  mov     [rbp+170h+var_1F0], rax
0x18013bb29  lea     rax, [rbp+170h+var_1B0]
0x18013bb2d  mov     [rsp+270h+var_240], rax
0x18013bb32  lea     rax, [rbp+170h+var_1A8]
0x18013bb36  mov     [rsp+270h+var_248], rax
0x18013bb3b  lea     rax, [rbp+170h+var_1F0]
0x18013bb3f  lea     rdx, word_18034AE22
0x18013bb46  jmp     loc_18013BBF5
0x18013bb4b  test    r15d, r15d
0x18013bb4e  jz      loc_18013BC58
0x18013bb54  cmp     byte ptr [rsi+58h], 0
0x18013bb58  jz      loc_18013BC58
0x18013bb5e  cmp     dword ptr [rsi+50h], 200h
0x18013bb65  jbe     loc_18013BC58
0x18013bb6b  mov     [rbp+170h+var_B0], 5
0x18013bb75  mov     [rbp+170h+var_AC], 1
0x18013bb7c  lea     rax, a512; "512"
0x18013bb83  mov     qword ptr [rsp+270h+var_250], rax
0x18013bb88  mov     r9d, 1; unsigned int
0x18013bb8e  mov     r8d, 8022h; unsigned int
0x18013bb94  lea     rdx, [rbp+170h+instance]; struct _MI_Instance *
0x18013bb9b  mov     rcx, rdi; struct _MI_Context *
0x18013bb9e  call    ?PostExtendedStatus@@YA_NPEAU_MI_Context@@PEAU_MI_Instance@@KIZZ; PostExtendedStatus(_MI_Context *,_MI_Instance *,ulong,uint,...)
0x18013bba3  lea     rdx, [rbp+170h+instance]
0x18013bbaa  mov     rcx, rdi; self
0x18013bbad  call    MI_Instance_Destruct
0x18013bbb2  mov     ebx, eax
0x18013bbb4  test    eax, eax
0x18013bbb6  jz      short loc_18013BBFF
0x18013bbb8  mov     eax, cs:dword_180397B68
0x18013bbbe  cmp     eax, 2
0x18013bbc1  jbe     short loc_18013BBFF
0x18013bbc3  mov     [rbp+170h+var_1E4], ebx
0x18013bbc6  mov     dword ptr [rbp+170h+var_1F0], 6E7h
0x18013bbcd  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013bbd4  mov     [rbp+170h+var_1D0], rax
0x18013bbd8  lea     rax, [rbp+170h+var_1E4]
0x18013bbdc  mov     [rsp+270h+var_240], rax
0x18013bbe1  lea     rax, [rbp+170h+var_1F0]
0x18013bbe5  mov     [rsp+270h+var_248], rax
0x18013bbea  lea     rax, [rbp+170h+var_1D0]
0x18013bbee  lea     rdx, unk_18034C388
0x18013bbf5  mov     qword ptr [rsp+270h+var_250], rax
0x18013bbfa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013bbff  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013bc06  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013bc0b  xor     r12d, r12d
0x18013bc0e  test    r13d, r13d
0x18013bc11  jnz     loc_18013BDF3
0x18013bc17  lea     rcx, [rbp+170h+var_198]; this
0x18013bc1b  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013bc20  mov     eax, cs:dword_180397B68
0x18013bc26  cmp     eax, 5
0x18013bc29  jbe     loc_18013BDF3
0x18013bc2f  mov     rdx, 400000000000h
0x18013bc39  lea     rcx, dword_180397B68
0x18013bc40  call    _tlgKeywordOn
0x18013bc45  test    al, al
0x18013bc47  jz      loc_18013BDF3
0x18013bc4d  cmp     [rsi+58h], r12b
0x18013bc51  jz      short loc_18013BCCF
0x18013bc53  mov     eax, [rsi+50h]
0x18013bc56  jmp     short loc_18013BCD2
0x18013bc58  mov     rcx, [rbp+170h+var_1E0]
0x18013bc5c  mov     rax, [rcx]
0x18013bc5f  lea     rdx, [rbp+170h+instance]
0x18013bc66  mov     qword ptr [rsp+270h+var_250], rdx
0x18013bc6b  mov     r9, rsi
0x18013bc6e  mov     r8, rdi
0x18013bc71  mov     edx, 10000Eh
0x18013bc76  mov     rax, [rax+30h]
0x18013bc7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013bc7f  mov     ebx, eax
0x18013bc81  test    eax, eax
0x18013bc83  jz      loc_18013BBA3
0x18013bc89  mov     eax, cs:dword_180397B68
0x18013bc8f  cmp     eax, 2
0x18013bc92  jbe     loc_18013BBFF
0x18013bc98  mov     [rbp+170h+var_1E8], ebx
0x18013bc9b  mov     dword ptr [rbp+170h+var_1D0], 6DEh
0x18013bca2  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013bca9  mov     [rbp+170h+var_1F0], rax
0x18013bcad  lea     rax, [rbp+170h+var_1E8]
0x18013bcb1  mov     [rsp+270h+var_240], rax
0x18013bcb6  lea     rax, [rbp+170h+var_1D0]
0x18013bcba  mov     [rsp+270h+var_248], rax
0x18013bcbf  lea     rax, [rbp+170h+var_1F0]
0x18013bcc3  lea     rdx, word_18034BE72
0x18013bcca  jmp     loc_18013BBF5
0x18013bccf  mov     eax, r12d
0x18013bcd2  mov     dword ptr [rbp+170h+var_1F0], eax
0x18013bcd5  cmp     [rbp+170h+var_88], r12b
0x18013bcdc  jz      short loc_18013BD19
0x18013bcde  mov     rax, [rbp+170h+var_90]
0x18013bce5  movups  xmm0, xmmword ptr [rax]
0x18013bce8  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18013bcec  movups  xmm1, xmmword ptr [rax+10h]
0x18013bcf0  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18013bcf4  movups  xmm0, xmmword ptr [rax+20h]
0x18013bcf8  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18013bcfc  movups  xmm1, xmmword ptr [rax+30h]
0x18013bd00  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18013bd04  xor     r8d, r8d; unsigned __int16 *
0x18013bd07  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18013bd0b  lea     rcx, name; "ObjectId"
0x18013bd12  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18013bd17  jmp     short loc_18013BD1C
0x18013bd19  mov     rax, r12
0x18013bd1c  mov     [rbp+170h+var_1A8], rax
0x18013bd20  mov     [rbp+170h+var_1B0], r12
0x18013bd24  mov     [rbp+170h+var_1B8], r12
0x18013bd28  mov     rax, [rbp+170h+var_190]
0x18013bd2c  sub     rax, [rbp+170h+var_198]
0x18013bd30  imul    rax, 3E8h
0x18013bd37  xor     edx, edx
0x18013bd39  div     [rbp+170h+var_188]
0x18013bd3d  mov     [rbp+170h+var_1C0], rax
0x18013bd41  mov     [rbp+170h+var_1E4], ebx
0x18013bd44  mov     al, [rbp+170h+var_AC]
0x18013bd4a  neg     al
0x18013bd4c  sbb     ecx, ecx
0x18013bd4e  and     ecx, [rbp+170h+var_B0]
0x18013bd54  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18013bd57  mov     [rbp+170h+var_1E8], r15d
0x18013bd5b  cmp     [r14+48h], r12b
0x18013bd5f  jz      short loc_18013BD67
0x18013bd61  mov     rax, [r14+40h]
0x18013bd65  jmp     short loc_18013BD6A
0x18013bd67  mov     rax, r12
0x18013bd6a  mov     [rbp+170h+var_1C8], rax
0x18013bd6e  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18013bd75  mov     [rbp+170h+var_1D8], rax
0x18013bd79  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013bd80  mov     [rbp+170h+var_1A0], rax
0x18013bd84  lea     rax, [rbp+170h+var_1F0]
0x18013bd88  mov     [rsp+270h+var_200], rax
0x18013bd8d  lea     rax, [rbp+170h+var_1A8]
0x18013bd91  mov     [rsp+270h+var_208], rax
0x18013bd96  lea     rax, [rbp+170h+var_1B0]
0x18013bd9a  mov     [rsp+270h+var_210], rax
0x18013bd9f  lea     rax, [rbp+170h+var_1B8]
0x18013bda3  mov     [rsp+270h+var_218], rax
0x18013bda8  lea     rax, [rbp+170h+var_1C0]
0x18013bdac  mov     [rsp+270h+var_220], rax
  ... truncated ...
```
