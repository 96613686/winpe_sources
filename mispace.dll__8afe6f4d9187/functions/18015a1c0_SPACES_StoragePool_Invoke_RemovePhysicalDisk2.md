# SPACES_StoragePool_Invoke_RemovePhysicalDisk2

- ea: `0x18015a1c0`
- end: `0x18015a7f2`
- name: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
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
- `0x18015a1c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a22e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a28d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a7c2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a22e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a28d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015a7c2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015a251`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18015a251`

## string_xrefs

- `0x18015a6be`: `RemovePhysicalDisk`
- `0x18015a299`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015a3af`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015a40c`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015a46e`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015a51d`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015a5f2`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`
- `0x18015a761`: `SPACES_StoragePool_Invoke_RemovePhysicalDisk2`

## pseudocode

```c
ULONG __fastcall SPACES_StoragePool_Invoke_RemovePhysicalDisk2(
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
  char *v21; // rdx
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
    LODWORD(v36) = 1742;
    v32 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
    v31 = &v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_StoragePool_Invoke_RemovePhysicalDisk2",
      (__int64)qword_180355708,
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
    LODWORD(v45) = 11;
    *((_QWORD *)&v45 + 1) = *(_QWORD *)(a6 + 64);
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v45, &v35, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v36) = v15;
        LODWORD(v38) = 1774;
        v32 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
        v20 = &v32;
        v21 = byte_180355473;
        goto LABEL_26;
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_StoragePool_RemovePhysicalDisk2_rtti, &instance);
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
                  720913,
                  a2,
                  a7,
                  &instance,
                  v31);
          if ( v15 )
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_27;
            v33 = v15;
            LODWORD(v37) = 1820;
            v32 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
            v20 = &v32;
            v21 = byte_180357615;
            goto LABEL_26;
          }
        }
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_27;
        v34 = v15;
        LODWORD(v32) = 1829;
        v37 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
        v20 = &v37;
        v21 = byte_180355CE5;
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
        LODWORD(v42) = 1793;
        v32 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
        v20 = &v32;
        v21 = byte_1803544ED;
        goto LABEL_26;
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v39) = 7;
        LODWORD(v40) = 1785;
        v32 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
        v20 = &v32;
        v21 = (char *)&dword_180354DE4;
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
        v43 = "StoragePool";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v50 & (unsigned int)-(v51 != 0),
          (__int64)&unk_180355AE0,
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
    LODWORD(v32) = 1857;
    v43 = "SPACES_StoragePool_Invoke_RemovePhysicalDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)byte_18035540D,
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
0x18015a1c0  mov     [rsp-8+arg_10], rbx
0x18015a1c5  push    rbp
0x18015a1c6  push    rsi
0x18015a1c7  push    rdi
0x18015a1c8  push    r12
0x18015a1ca  push    r13
0x18015a1cc  push    r14
0x18015a1ce  push    r15
0x18015a1d0  lea     rbp, [rsp-140h]
0x18015a1d8  sub     rsp, 240h
0x18015a1df  mov     rax, cs:__security_cookie
0x18015a1e6  xor     rax, rsp
0x18015a1e9  mov     [rbp+170h+var_40], rax
0x18015a1f0  mov     rdi, rdx
0x18015a1f3  mov     r12, rcx
0x18015a1f6  mov     r14, [rbp+170h+arg_28]
0x18015a1fd  mov     rsi, [rbp+170h+arg_30]
0x18015a204  xorps   xmm0, xmm0
0x18015a207  xor     eax, eax
0x18015a209  movups  xmmword ptr [rbp+170h+value], xmm0
0x18015a20d  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18015a211  mov     qword ptr [rbp+170h+value+20h], rax
0x18015a215  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18015a21c  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18015a224  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18015a22b  lea     ecx, [rax+1]; ControlCode
0x18015a22e  call    cs:__imp_EventActivityIdControl
0x18015a234  lea     r9, [rbp+170h+value]; value
0x18015a238  mov     rcx, rdi; context
0x18015a23b  call    MI_Context_GetCustomOption_1
0x18015a240  xor     ebx, ebx
0x18015a242  test    eax, eax
0x18015a244  jnz     short loc_18015A257
0x18015a246  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18015a24d  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18015a251  call    cs:__imp_CLSIDFromString
0x18015a257  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18015a25e  mov     [rbp+170h+var_60], rcx
0x18015a265  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18015a26c  mov     [rbp+170h+var_58], rax
0x18015a273  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18015a27a  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18015a281  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18015a288  mov     ecx, 4; ControlCode
0x18015a28d  call    cs:__imp_EventActivityIdControl
0x18015a293  mov     eax, cs:dword_180397B68
0x18015a299  lea     rcx, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a2a0  cmp     eax, 5
0x18015a2a3  jbe     short loc_18015A2CE
0x18015a2a5  mov     dword ptr [rbp+170h+var_1D8], 6CEh
0x18015a2ac  mov     [rbp+170h+var_1F0], rcx
0x18015a2b0  lea     rax, [rbp+170h+var_1D8]
0x18015a2b4  mov     [rsp+270h+var_248], rax
0x18015a2b9  lea     rax, [rbp+170h+var_1F0]
0x18015a2bd  mov     qword ptr [rsp+270h+var_250], rax
0x18015a2c2  lea     rdx, qword_180355708
0x18015a2c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18015a2ce  mov     [rbp+170h+instance.ft], rbx
0x18015a2d5  xor     edx, edx; Val
0x18015a2d7  lea     r8d, [rdx+78h]; Size
0x18015a2db  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18015a2e2  call    memset_0
0x18015a2e7  xorps   xmm0, xmm0
0x18015a2ea  xor     eax, eax
0x18015a2ec  movups  [rbp+170h+var_178], xmm0
0x18015a2f0  mov     [rbp+170h+var_168], rax
0x18015a2f4  mov     [rbp+170h+var_1E0], rbx
0x18015a2f8  lea     rcx, [rbp+170h+var_1E0]
0x18015a2fc  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015a301  mov     [rbp+170h+var_1E0], rbx
0x18015a305  mov     r15d, ebx
0x18015a308  lea     rcx, [rbp+170h+var_198]; this
0x18015a30c  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18015a311  mov     rcx, rdi; context
0x18015a314  call    WspIsRemoteRequest
0x18015a319  mov     r13d, eax
0x18015a31c  test    eax, eax
0x18015a31e  jnz     short loc_18015A343
0x18015a320  lea     rcx, [rbp+170h+var_198]; this
0x18015a324  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18015a329  cmp     [r14+48h], bl
0x18015a32d  jz      short loc_18015A340
0x18015a32f  mov     rcx, [r14+40h]; unsigned __int16 *
0x18015a333  call    WspIsRemoteInstance
0x18015a338  test    al, al
0x18015a33a  lea     r15d, [r13+1]
0x18015a33e  jnz     short loc_18015A343
0x18015a340  mov     r15d, ebx
0x18015a343  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18015a34a  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18015a34f  mov     ebx, eax
0x18015a351  test    eax, eax
0x18015a353  jnz     loc_18015A55B
0x18015a359  mov     dword ptr [rbp+170h+var_178], 0Bh
0x18015a360  mov     rax, [r14+40h]
0x18015a364  mov     qword ptr [rbp+170h+var_178+8], rax
0x18015a368  mov     rbx, [r12]
0x18015a36c  lea     rcx, [rbp+170h+var_1E0]
0x18015a370  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18015a375  mov     [rsp+270h+var_250], 1; int
0x18015a37d  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18015a381  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18015a385  mov     rdx, rdi; context
0x18015a388  mov     rcx, rbx; this
0x18015a38b  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18015a390  mov     ebx, eax
0x18015a392  test    eax, eax
0x18015a394  jz      short loc_18015A3DC
0x18015a396  mov     eax, cs:dword_180397B68
0x18015a39c  cmp     eax, 2
0x18015a39f  jbe     loc_18015A54F
0x18015a3a5  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18015a3a8  mov     dword ptr [rbp+170h+var_1C8], 6EEh
0x18015a3af  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a3b6  mov     [rbp+170h+var_1F0], rax
0x18015a3ba  lea     rax, [rbp+170h+var_1D8]
0x18015a3be  mov     [rsp+270h+var_240], rax
0x18015a3c3  lea     rax, [rbp+170h+var_1C8]
0x18015a3c7  mov     [rsp+270h+var_248], rax
0x18015a3cc  lea     rax, [rbp+170h+var_1F0]
0x18015a3d0  lea     rdx, byte_180355473
0x18015a3d7  jmp     loc_18015A545
0x18015a3dc  mov     r8, [r14+40h]
0x18015a3e0  mov     rdx, rdi
0x18015a3e3  mov     rcx, [r12]
0x18015a3e7  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18015a3ec  test    eax, eax
0x18015a3ee  jnz     short loc_18015A439
0x18015a3f0  lea     ebx, [rax+7]
0x18015a3f3  mov     eax, cs:dword_180397B68
0x18015a3f9  cmp     eax, 2
0x18015a3fc  jbe     loc_18015A54F
0x18015a402  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18015a405  mov     dword ptr [rbp+170h+var_1B8], 6F9h
0x18015a40c  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a413  mov     [rbp+170h+var_1F0], rax
0x18015a417  lea     rax, [rbp+170h+var_1C0]
0x18015a41b  mov     [rsp+270h+var_240], rax
0x18015a420  lea     rax, [rbp+170h+var_1B8]
0x18015a424  mov     [rsp+270h+var_248], rax
0x18015a429  lea     rax, [rbp+170h+var_1F0]
0x18015a42d  lea     rdx, dword_180354DE4
0x18015a434  jmp     loc_18015A545
0x18015a439  lea     r8, [rbp+170h+instance]; instance
0x18015a440  lea     rdx, SPACES_StoragePool_RemovePhysicalDisk2_rtti; methodDecl
0x18015a447  mov     rcx, rdi; context
0x18015a44a  call    MI_Context_ConstructParameters
0x18015a44f  mov     ebx, eax
0x18015a451  test    eax, eax
0x18015a453  jz      short loc_18015A49B
0x18015a455  mov     eax, cs:dword_180397B68
0x18015a45b  cmp     eax, 2
0x18015a45e  jbe     loc_18015A54F
0x18015a464  mov     dword ptr [rbp+170h+var_1B0], ebx
0x18015a467  mov     dword ptr [rbp+170h+var_1A8], 701h
0x18015a46e  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a475  mov     [rbp+170h+var_1F0], rax
0x18015a479  lea     rax, [rbp+170h+var_1B0]
0x18015a47d  mov     [rsp+270h+var_240], rax
0x18015a482  lea     rax, [rbp+170h+var_1A8]
0x18015a486  mov     [rsp+270h+var_248], rax
0x18015a48b  lea     rax, [rbp+170h+var_1F0]
0x18015a48f  lea     rdx, byte_1803544ED
0x18015a496  jmp     loc_18015A545
0x18015a49b  test    r15d, r15d
0x18015a49e  jz      loc_18015A5A8
0x18015a4a4  cmp     byte ptr [rsi+58h], 0
0x18015a4a8  jz      loc_18015A5A8
0x18015a4ae  cmp     dword ptr [rsi+50h], 200h
0x18015a4b5  jbe     loc_18015A5A8
0x18015a4bb  mov     [rbp+170h+var_B0], 5
0x18015a4c5  mov     [rbp+170h+var_AC], 1
0x18015a4cc  lea     rax, a512; "512"
0x18015a4d3  mov     qword ptr [rsp+270h+var_250], rax
0x18015a4d8  mov     r9d, 1; unsigned int
0x18015a4de  mov     r8d, 8022h; unsigned int
0x18015a4e4  lea     rdx, [rbp+170h+instance]; struct _MI_Instance *
0x18015a4eb  mov     rcx, rdi; struct _MI_Context *
0x18015a4ee  call    ?PostExtendedStatus@@YA_NPEAU_MI_Context@@PEAU_MI_Instance@@KIZZ; PostExtendedStatus(_MI_Context *,_MI_Instance *,ulong,uint,...)
0x18015a4f3  lea     rdx, [rbp+170h+instance]
0x18015a4fa  mov     rcx, rdi; self
0x18015a4fd  call    MI_Instance_Destruct
0x18015a502  mov     ebx, eax
0x18015a504  test    eax, eax
0x18015a506  jz      short loc_18015A54F
0x18015a508  mov     eax, cs:dword_180397B68
0x18015a50e  cmp     eax, 2
0x18015a511  jbe     short loc_18015A54F
0x18015a513  mov     [rbp+170h+var_1E4], ebx
0x18015a516  mov     dword ptr [rbp+170h+var_1F0], 725h
0x18015a51d  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a524  mov     [rbp+170h+var_1D0], rax
0x18015a528  lea     rax, [rbp+170h+var_1E4]
0x18015a52c  mov     [rsp+270h+var_240], rax
0x18015a531  lea     rax, [rbp+170h+var_1F0]
0x18015a535  mov     [rsp+270h+var_248], rax
0x18015a53a  lea     rax, [rbp+170h+var_1D0]
0x18015a53e  lea     rdx, byte_180355CE5
0x18015a545  mov     qword ptr [rsp+270h+var_250], rax
0x18015a54a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18015a54f  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18015a556  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18015a55b  xor     r12d, r12d
0x18015a55e  test    r13d, r13d
0x18015a561  jnz     loc_18015A743
0x18015a567  lea     rcx, [rbp+170h+var_198]; this
0x18015a56b  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18015a570  mov     eax, cs:dword_180397B68
0x18015a576  cmp     eax, 5
0x18015a579  jbe     loc_18015A743
0x18015a57f  mov     rdx, 400000000000h
0x18015a589  lea     rcx, dword_180397B68
0x18015a590  call    _tlgKeywordOn
0x18015a595  test    al, al
0x18015a597  jz      loc_18015A743
0x18015a59d  cmp     [rsi+58h], r12b
0x18015a5a1  jz      short loc_18015A61F
0x18015a5a3  mov     eax, [rsi+50h]
0x18015a5a6  jmp     short loc_18015A622
0x18015a5a8  mov     rcx, [rbp+170h+var_1E0]
0x18015a5ac  mov     rax, [rcx]
0x18015a5af  lea     rdx, [rbp+170h+instance]
0x18015a5b6  mov     qword ptr [rsp+270h+var_250], rdx
0x18015a5bb  mov     r9, rsi
0x18015a5be  mov     r8, rdi
0x18015a5c1  mov     edx, 0B0011h
0x18015a5c6  mov     rax, [rax+30h]
0x18015a5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a5cf  mov     ebx, eax
0x18015a5d1  test    eax, eax
0x18015a5d3  jz      loc_18015A4F3
0x18015a5d9  mov     eax, cs:dword_180397B68
0x18015a5df  cmp     eax, 2
0x18015a5e2  jbe     loc_18015A54F
0x18015a5e8  mov     [rbp+170h+var_1E8], ebx
0x18015a5eb  mov     dword ptr [rbp+170h+var_1D0], 71Ch
0x18015a5f2  lea     rax, aSpacesStoragep_48; "SPACES_StoragePool_Invoke_RemovePhysica"...
0x18015a5f9  mov     [rbp+170h+var_1F0], rax
0x18015a5fd  lea     rax, [rbp+170h+var_1E8]
0x18015a601  mov     [rsp+270h+var_240], rax
0x18015a606  lea     rax, [rbp+170h+var_1D0]
0x18015a60a  mov     [rsp+270h+var_248], rax
0x18015a60f  lea     rax, [rbp+170h+var_1F0]
0x18015a613  lea     rdx, byte_180357615
0x18015a61a  jmp     loc_18015A545
0x18015a61f  mov     eax, r12d
0x18015a622  mov     dword ptr [rbp+170h+var_1F0], eax
0x18015a625  cmp     [rbp+170h+var_88], r12b
0x18015a62c  jz      short loc_18015A669
0x18015a62e  mov     rax, [rbp+170h+var_90]
0x18015a635  movups  xmm0, xmmword ptr [rax]
0x18015a638  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18015a63c  movups  xmm1, xmmword ptr [rax+10h]
0x18015a640  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18015a644  movups  xmm0, xmmword ptr [rax+20h]
0x18015a648  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18015a64c  movups  xmm1, xmmword ptr [rax+30h]
0x18015a650  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18015a654  xor     r8d, r8d; unsigned __int16 *
0x18015a657  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18015a65b  lea     rcx, name; "ObjectId"
0x18015a662  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18015a667  jmp     short loc_18015A66C
0x18015a669  mov     rax, r12
0x18015a66c  mov     [rbp+170h+var_1A8], rax
0x18015a670  mov     [rbp+170h+var_1B0], r12
0x18015a674  mov     [rbp+170h+var_1B8], r12
0x18015a678  mov     rax, [rbp+170h+var_190]
0x18015a67c  sub     rax, [rbp+170h+var_198]
0x18015a680  imul    rax, 3E8h
0x18015a687  xor     edx, edx
0x18015a689  div     [rbp+170h+var_188]
0x18015a68d  mov     [rbp+170h+var_1C0], rax
0x18015a691  mov     [rbp+170h+var_1E4], ebx
0x18015a694  mov     al, [rbp+170h+var_AC]
0x18015a69a  neg     al
0x18015a69c  sbb     ecx, ecx
0x18015a69e  and     ecx, [rbp+170h+var_B0]
0x18015a6a4  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18015a6a7  mov     [rbp+170h+var_1E8], r15d
0x18015a6ab  cmp     [r14+48h], r12b
0x18015a6af  jz      short loc_18015A6B7
0x18015a6b1  mov     rax, [r14+40h]
0x18015a6b5  jmp     short loc_18015A6BA
0x18015a6b7  mov     rax, r12
0x18015a6ba  mov     [rbp+170h+var_1C8], rax
0x18015a6be  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18015a6c5  mov     [rbp+170h+var_1D8], rax
0x18015a6c9  lea     rax, aStoragepool_0; "StoragePool"
0x18015a6d0  mov     [rbp+170h+var_1A0], rax
0x18015a6d4  lea     rax, [rbp+170h+var_1F0]
0x18015a6d8  mov     [rsp+270h+var_200], rax
0x18015a6dd  lea     rax, [rbp+170h+var_1A8]
0x18015a6e1  mov     [rsp+270h+var_208], rax
0x18015a6e6  lea     rax, [rbp+170h+var_1B0]
0x18015a6ea  mov     [rsp+270h+var_210], rax
0x18015a6ef  lea     rax, [rbp+170h+var_1B8]
0x18015a6f3  mov     [rsp+270h+var_218], rax
0x18015a6f8  lea     rax, [rbp+170h+var_1C0]
0x18015a6fc  mov     [rsp+270h+var_220], rax
  ... truncated ...
```
