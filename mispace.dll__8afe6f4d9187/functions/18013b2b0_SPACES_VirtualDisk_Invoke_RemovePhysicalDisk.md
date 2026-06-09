# SPACES_VirtualDisk_Invoke_RemovePhysicalDisk

- ea: `0x18013b2b0`
- end: `0x18013b85b`
- name: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
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
- `0x18001afd0`
- `0x1800215bc`
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x18013b2b0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b32d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b38c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b82b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b32d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b38c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013b82b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013b350`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013b350`

## string_xrefs

- `0x18013b727`: `RemovePhysicalDisk`
- `0x18013b398`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013b4b0`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013b512`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013b585`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013b5d9`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013b7ca`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG __fastcall SPACES_VirtualDisk_Invoke_RemovePhysicalDisk(
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
  enum _MI_Result v13; // r14d
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
  unsigned __int16 *v25; // rax
  const MI_Char *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned __int16 *v31; // [rsp+28h] [rbp-D8h]
  const char *v32; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v33; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v34; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v35; // [rsp+90h] [rbp-70h] BYREF
  const char *v36; // [rsp+98h] [rbp-68h] BYREF
  const char *v37; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v38; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v41; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v42; // [rsp+C8h] [rbp-38h] BYREF
  const char *v43; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v44[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v45; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v46; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v47; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v50; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v51; // [rsp+1E0h] [rbp+E0h]
  char v52; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v54; // [rsp+210h] [rbp+110h]
  GUID v55; // [rsp+220h] [rbp+120h] BYREF

  v42 = a4;
  v41 = a5;
  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v54 = ActivityId;
  v55 = ActivityId;
  EventActivityIdControl(4u, &v55);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v36) = 1572;
    v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
    v31 = (unsigned __int16 *)&v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_VirtualDisk_Invoke_RemovePhysicalDisk",
      (__int64)word_18034B01A,
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
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v45) = 16;
    *((_QWORD *)&v45 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v45, &v35, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v36) = v15;
        LODWORD(v38) = 1603;
        v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
        v20 = &v32;
        v21 = (__int16 *)&unk_18034CBA0;
LABEL_22:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (__int64)v21,
          v18,
          v19,
          v20);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_RemovePhysicalDisk_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v39) = v15;
          LODWORD(v40) = 1611;
          v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
          v20 = &v32;
          v21 = &word_18034AD3E;
          goto LABEL_22;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, unsigned __int16 *))(*(_QWORD *)v35 + 48LL))(
                v35,
                1048588,
                a2,
                a7,
                &instance,
                v31);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_23;
          v34 = v15;
          LODWORD(v32) = 1630;
          v37 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
          v20 = &v37;
          v21 = (__int16 *)&dword_18034BBC4;
          goto LABEL_22;
        }
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v33 = v15;
          LODWORD(v37) = 1622;
          v32 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
          v20 = &v32;
          v21 = word_18034B49A;
          goto LABEL_22;
        }
      }
    }
LABEL_23:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v42, v41, a6 + 4, &v50, v15, 0);
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
        if ( v52 )
        {
          v47 = *v51;
          v25 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v47, 0);
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
        LODWORD(v37) = v50.exists != 0 ? v50.value : 0;
        v33 = v13;
        if ( a6[4].exists )
          v26 = a6[4].value;
        else
          v26 = 0;
        v38 = v26;
        v36 = "RemovePhysicalDisk";
        v43 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v50.exists != 0 ? v50.value : 0,
          (__int64)&unk_18034B048,
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
    LODWORD(v32) = 1664;
    v43 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)byte_18034B773,
      v28,
      v29,
      &v43);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v44);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  return EventActivityIdControl(4u, &v55);
}

```

## disassembly

```asm
0x18013b2b0  mov     [rsp-8+arg_10], rbx
0x18013b2b5  push    rbp
0x18013b2b6  push    rsi
0x18013b2b7  push    rdi
0x18013b2b8  push    r12
0x18013b2ba  push    r13
0x18013b2bc  push    r14
0x18013b2be  push    r15
0x18013b2c0  lea     rbp, [rsp-140h]
0x18013b2c8  sub     rsp, 240h
0x18013b2cf  mov     rax, cs:__security_cookie
0x18013b2d6  xor     rax, rsp
0x18013b2d9  mov     [rbp+170h+var_40], rax
0x18013b2e0  mov     [rbp+170h+var_1A8], r9
0x18013b2e4  mov     rdi, rdx
0x18013b2e7  mov     r12, rcx
0x18013b2ea  mov     rax, [rbp+170h+arg_20]
0x18013b2f1  mov     [rbp+170h+var_1B0], rax
0x18013b2f5  mov     rsi, [rbp+170h+arg_28]
0x18013b2fc  mov     r15, [rbp+170h+arg_30]
0x18013b303  xorps   xmm0, xmm0
0x18013b306  xor     eax, eax
0x18013b308  movups  xmmword ptr [rbp+170h+value], xmm0
0x18013b30c  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18013b310  mov     qword ptr [rbp+170h+value+20h], rax
0x18013b314  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013b31b  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18013b323  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18013b32a  lea     ecx, [rax+1]; ControlCode
0x18013b32d  call    cs:__imp_EventActivityIdControl
0x18013b333  lea     r9, [rbp+170h+value]; value
0x18013b337  mov     rcx, rdi; context
0x18013b33a  call    MI_Context_GetCustomOption_1
0x18013b33f  xor     ebx, ebx
0x18013b341  test    eax, eax
0x18013b343  jnz     short loc_18013B356
0x18013b345  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18013b34c  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18013b350  call    cs:__imp_CLSIDFromString
0x18013b356  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18013b35d  mov     [rbp+170h+var_60], rcx
0x18013b364  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18013b36b  mov     [rbp+170h+var_58], rax
0x18013b372  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18013b379  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18013b380  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18013b387  mov     ecx, 4; ControlCode
0x18013b38c  call    cs:__imp_EventActivityIdControl
0x18013b392  mov     eax, cs:dword_180397B68
0x18013b398  lea     rcx, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b39f  cmp     eax, 5
0x18013b3a2  jbe     short loc_18013B3CD
0x18013b3a4  mov     dword ptr [rbp+170h+var_1D8], 624h
0x18013b3ab  mov     [rbp+170h+var_1F0], rcx
0x18013b3af  lea     rax, [rbp+170h+var_1D8]
0x18013b3b3  mov     [rsp+270h+var_248], rax
0x18013b3b8  lea     rax, [rbp+170h+var_1F0]
0x18013b3bc  mov     qword ptr [rsp+270h+var_250], rax
0x18013b3c1  lea     rdx, word_18034B01A
0x18013b3c8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013b3cd  mov     [rbp+170h+instance.ft], rbx
0x18013b3d4  xor     edx, edx; Val
0x18013b3d6  lea     r8d, [rdx+78h]; Size
0x18013b3da  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18013b3e1  call    memset_0
0x18013b3e6  xorps   xmm0, xmm0
0x18013b3e9  xor     eax, eax
0x18013b3eb  movups  [rbp+170h+var_178], xmm0
0x18013b3ef  mov     [rbp+170h+var_168], rax
0x18013b3f3  mov     [rbp+170h+var_1E0], rbx
0x18013b3f7  lea     rcx, [rbp+170h+var_1E0]
0x18013b3fb  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013b400  mov     [rbp+170h+var_1E0], rbx
0x18013b404  mov     r14d, ebx
0x18013b407  lea     rcx, [rbp+170h+var_198]; this
0x18013b40b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013b410  mov     rcx, rdi; context
0x18013b413  call    WspIsRemoteRequest
0x18013b418  mov     r13d, eax
0x18013b41b  test    eax, eax
0x18013b41d  jnz     short loc_18013B441
0x18013b41f  lea     rcx, [rbp+170h+var_198]; this
0x18013b423  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013b428  cmp     [rsi+48h], bl
0x18013b42b  jz      short loc_18013B43E
0x18013b42d  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18013b431  call    WspIsRemoteInstance
0x18013b436  test    al, al
0x18013b438  lea     r14d, [r13+1]
0x18013b43c  jnz     short loc_18013B441
0x18013b43e  mov     r14d, ebx
0x18013b441  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013b448  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013b44d  mov     ebx, eax
0x18013b44f  test    eax, eax
0x18013b451  jnz     loc_18013B619
0x18013b457  mov     dword ptr [rbp+170h+var_178], 10h
0x18013b45e  mov     rax, [rsi+40h]
0x18013b462  mov     qword ptr [rbp+170h+var_178+8], rax
0x18013b466  mov     rbx, [r12]
0x18013b46a  lea     rcx, [rbp+170h+var_1E0]
0x18013b46e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013b473  mov     [rsp+270h+var_250], 1; int
0x18013b47b  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18013b47f  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18013b483  mov     rdx, rdi; context
0x18013b486  mov     rcx, rbx; this
0x18013b489  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013b48e  mov     ebx, eax
0x18013b490  xor     r12d, r12d
0x18013b493  test    eax, eax
0x18013b495  jz      short loc_18013B4DD
0x18013b497  mov     eax, cs:dword_180397B68
0x18013b49d  cmp     eax, 2
0x18013b4a0  jbe     loc_18013B60B
0x18013b4a6  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18013b4a9  mov     dword ptr [rbp+170h+var_1C8], 643h
0x18013b4b0  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b4b7  mov     [rbp+170h+var_1F0], rax
0x18013b4bb  lea     rax, [rbp+170h+var_1D8]
0x18013b4bf  mov     [rsp+270h+var_240], rax
0x18013b4c4  lea     rax, [rbp+170h+var_1C8]
0x18013b4c8  mov     [rsp+270h+var_248], rax
0x18013b4cd  lea     rax, [rbp+170h+var_1F0]
0x18013b4d1  lea     rdx, unk_18034CBA0
0x18013b4d8  jmp     loc_18013B601
0x18013b4dd  lea     r8, [rbp+170h+instance]; instance
0x18013b4e4  lea     rdx, SPACES_VirtualDisk_RemovePhysicalDisk_rtti; methodDecl
0x18013b4eb  mov     rcx, rdi; context
0x18013b4ee  call    MI_Context_ConstructParameters
0x18013b4f3  mov     ebx, eax
0x18013b4f5  test    eax, eax
0x18013b4f7  jz      short loc_18013B53F
0x18013b4f9  mov     eax, cs:dword_180397B68
0x18013b4ff  cmp     eax, 2
0x18013b502  jbe     loc_18013B60B
0x18013b508  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18013b50b  mov     dword ptr [rbp+170h+var_1B8], 64Bh
0x18013b512  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b519  mov     [rbp+170h+var_1F0], rax
0x18013b51d  lea     rax, [rbp+170h+var_1C0]
0x18013b521  mov     [rsp+270h+var_240], rax
0x18013b526  lea     rax, [rbp+170h+var_1B8]
0x18013b52a  mov     [rsp+270h+var_248], rax
0x18013b52f  lea     rax, [rbp+170h+var_1F0]
0x18013b533  lea     rdx, word_18034AD3E
0x18013b53a  jmp     loc_18013B601
0x18013b53f  mov     rcx, [rbp+170h+var_1E0]
0x18013b543  mov     rax, [rcx]
0x18013b546  lea     rdx, [rbp+170h+instance]
0x18013b54d  mov     qword ptr [rsp+270h+var_250], rdx
0x18013b552  mov     r9, r15
0x18013b555  mov     r8, rdi
0x18013b558  mov     edx, 10000Ch
0x18013b55d  mov     rax, [rax+30h]
0x18013b561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013b566  mov     ebx, eax
0x18013b568  test    eax, eax
0x18013b56a  jz      short loc_18013B5AF
0x18013b56c  mov     eax, cs:dword_180397B68
0x18013b572  cmp     eax, 2
0x18013b575  jbe     loc_18013B60B
0x18013b57b  mov     [rbp+170h+var_1E8], ebx
0x18013b57e  mov     dword ptr [rbp+170h+var_1D0], 656h
0x18013b585  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b58c  mov     [rbp+170h+var_1F0], rax
0x18013b590  lea     rax, [rbp+170h+var_1E8]
0x18013b594  mov     [rsp+270h+var_240], rax
0x18013b599  lea     rax, [rbp+170h+var_1D0]
0x18013b59d  mov     [rsp+270h+var_248], rax
0x18013b5a2  lea     rax, [rbp+170h+var_1F0]
0x18013b5a6  lea     rdx, word_18034B49A
0x18013b5ad  jmp     short loc_18013B601
0x18013b5af  lea     rdx, [rbp+170h+instance]
0x18013b5b6  mov     rcx, rdi; self
0x18013b5b9  call    MI_Instance_Destruct
0x18013b5be  mov     ebx, eax
0x18013b5c0  test    eax, eax
0x18013b5c2  jz      short loc_18013B60B
0x18013b5c4  mov     eax, cs:dword_180397B68
0x18013b5ca  cmp     eax, 2
0x18013b5cd  jbe     short loc_18013B60B
0x18013b5cf  mov     [rbp+170h+var_1E4], ebx
0x18013b5d2  mov     dword ptr [rbp+170h+var_1F0], 65Eh
0x18013b5d9  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b5e0  mov     [rbp+170h+var_1D0], rax
0x18013b5e4  lea     rax, [rbp+170h+var_1E4]
0x18013b5e8  mov     [rsp+270h+var_240], rax
0x18013b5ed  lea     rax, [rbp+170h+var_1F0]
0x18013b5f1  mov     [rsp+270h+var_248], rax
0x18013b5f6  lea     rax, [rbp+170h+var_1D0]
0x18013b5fa  lea     rdx, dword_18034BBC4
0x18013b601  mov     qword ptr [rsp+270h+var_250], rax
0x18013b606  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013b60b  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013b612  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013b617  jmp     short loc_18013B61C
0x18013b619  xor     r12d, r12d
0x18013b61c  lea     r8, [rsi+40h]; struct _MI_ConstStringField *
0x18013b620  mov     [rsp+270h+var_248], r12; unsigned __int16 *
0x18013b625  mov     [rsp+270h+var_250], ebx; enum _MI_Result
0x18013b629  lea     r9, [rbp+170h+var_B0]; struct _MI_ConstUint32Field *
0x18013b630  mov     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x18013b634  mov     rcx, [rbp+170h+var_1A8]; unsigned __int16 *
0x18013b638  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013b63d  test    r13d, r13d
0x18013b640  jnz     loc_18013B7AC
0x18013b646  lea     rcx, [rbp+170h+var_198]; this
0x18013b64a  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013b64f  mov     eax, cs:dword_180397B68
0x18013b655  cmp     eax, 5
0x18013b658  jbe     loc_18013B7AC
0x18013b65e  mov     rdx, 400000000000h
0x18013b668  lea     rcx, dword_180397B68
0x18013b66f  call    _tlgKeywordOn
0x18013b674  test    al, al
0x18013b676  jz      loc_18013B7AC
0x18013b67c  cmp     [r15+58h], r12b
0x18013b680  jz      short loc_18013B688
0x18013b682  mov     eax, [r15+50h]
0x18013b686  jmp     short loc_18013B68B
0x18013b688  mov     eax, r12d
0x18013b68b  mov     dword ptr [rbp+170h+var_1F0], eax
0x18013b68e  cmp     [rbp+170h+var_88], r12b
0x18013b695  jz      short loc_18013B6D2
0x18013b697  mov     rax, [rbp+170h+var_90]
0x18013b69e  movups  xmm0, xmmword ptr [rax]
0x18013b6a1  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18013b6a5  movups  xmm1, xmmword ptr [rax+10h]
0x18013b6a9  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18013b6ad  movups  xmm0, xmmword ptr [rax+20h]
0x18013b6b1  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18013b6b5  movups  xmm1, xmmword ptr [rax+30h]
0x18013b6b9  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18013b6bd  xor     r8d, r8d; unsigned __int16 *
0x18013b6c0  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18013b6c4  lea     rcx, name; "ObjectId"
0x18013b6cb  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18013b6d0  jmp     short loc_18013B6D5
0x18013b6d2  mov     rax, r12
0x18013b6d5  mov     [rbp+170h+var_1A8], rax
0x18013b6d9  mov     [rbp+170h+var_1B0], r12
0x18013b6dd  mov     [rbp+170h+var_1B8], r12
0x18013b6e1  mov     rax, [rbp+170h+var_190]
0x18013b6e5  sub     rax, [rbp+170h+var_198]
0x18013b6e9  imul    rax, 3E8h
0x18013b6f0  xor     edx, edx
0x18013b6f2  div     [rbp+170h+var_188]
0x18013b6f6  mov     [rbp+170h+var_1C0], rax
0x18013b6fa  mov     [rbp+170h+var_1E4], ebx
0x18013b6fd  mov     al, [rbp+170h+var_B0.exists]
0x18013b703  neg     al
0x18013b705  sbb     ecx, ecx
0x18013b707  and     ecx, [rbp+170h+var_B0.value]
0x18013b70d  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18013b710  mov     [rbp+170h+var_1E8], r14d
0x18013b714  cmp     [rsi+48h], r12b
0x18013b718  jz      short loc_18013B720
0x18013b71a  mov     rax, [rsi+40h]
0x18013b71e  jmp     short loc_18013B723
0x18013b720  mov     rax, r12
0x18013b723  mov     [rbp+170h+var_1C8], rax
0x18013b727  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18013b72e  mov     [rbp+170h+var_1D8], rax
0x18013b732  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013b739  mov     [rbp+170h+var_1A0], rax
0x18013b73d  lea     rax, [rbp+170h+var_1F0]
0x18013b741  mov     [rsp+270h+var_200], rax
0x18013b746  lea     rax, [rbp+170h+var_1A8]
0x18013b74a  mov     [rsp+270h+var_208], rax
0x18013b74f  lea     rax, [rbp+170h+var_1B0]
0x18013b753  mov     [rsp+270h+var_210], rax
0x18013b758  lea     rax, [rbp+170h+var_1B8]
0x18013b75c  mov     [rsp+270h+var_218], rax
0x18013b761  lea     rax, [rbp+170h+var_1C0]
0x18013b765  mov     [rsp+270h+var_220], rax
0x18013b76a  lea     rax, [rbp+170h+var_1E4]
0x18013b76e  mov     [rsp+270h+var_228], rax
0x18013b773  lea     rax, [rbp+170h+var_1D0]
0x18013b777  mov     [rsp+270h+var_230], rax
0x18013b77c  lea     rax, [rbp+170h+var_1E8]
0x18013b780  mov     [rsp+270h+var_238], rax
0x18013b785  lea     rax, [rbp+170h+var_1C8]
0x18013b789  mov     [rsp+270h+var_240], rax
0x18013b78e  lea     rax, [rbp+170h+var_1D8]
0x18013b792  mov     [rsp+270h+var_248], rax
0x18013b797  lea     rax, [rbp+170h+var_1A0]
0x18013b79b  mov     qword ptr [rsp+270h+var_250], rax
0x18013b7a0  lea     rdx, unk_18034B048
0x18013b7a7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@3445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18013b7ac  lea     rcx, [rbp+170h+instance]; self
0x18013b7b3  call    MI_Instance_Destruct
0x18013b7b8  mov     eax, cs:dword_180397B68
0x18013b7be  cmp     eax, 5
0x18013b7c1  jbe     short loc_18013B7F3
0x18013b7c3  mov     dword ptr [rbp+170h+var_1F0], 680h
0x18013b7ca  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013b7d1  mov     [rbp+170h+var_1A0], rax
0x18013b7d5  lea     rax, [rbp+170h+var_1F0]
0x18013b7d9  mov     [rsp+270h+var_248], rax
  ... truncated ...
```
