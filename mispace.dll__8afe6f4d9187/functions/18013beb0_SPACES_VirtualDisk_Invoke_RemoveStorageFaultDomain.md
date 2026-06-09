# SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain

- ea: `0x18013beb0`
- end: `0x18013c485`
- name: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- size: `1493`
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
- `0x1800215bc`
- `0x180021e88`
- `0x1800234e4`
- `0x180025444`
- `0x180137a24`
- `0x180138120`
- `0x18013beb0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013bf1e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013bf7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c455`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013bf1e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013bf7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013c455`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013bf41`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013bf41`

## string_xrefs

- `0x18013bf89`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c09e`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c0fd`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c15f`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c1d2`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c226`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c3f4`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18013c351`: `RemoveStorageFaultDomain`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain(
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
  __int64 v11; // r8
  __int64 v12; // r9
  enum _MI_Result v13; // r15d
  int IsRemoteRequest; // r12d
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
    LODWORD(v36) = 1924;
    v32 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
    v31 = &v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)"SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain",
      (__int64)&word_18034AC9E,
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
        LODWORD(v38) = 1956;
        v32 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
        v20 = &v32;
        v21 = byte_18034A9E5;
LABEL_25:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (__int64)v21,
          v18,
          v19,
          v20);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_RemoveStorageFaultDomain_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          LODWORD(v41) = v15;
          LODWORD(v42) = 1974;
          v32 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
          v20 = &v32;
          v21 = (char *)&unk_18034BE00;
          goto LABEL_25;
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *, const char **))(*(_QWORD *)v35 + 48LL))(
                v35,
                1048594,
                a2,
                a7,
                &instance,
                v31);
        if ( v15 == MI_RESULT_OK )
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 == MI_RESULT_OK || (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_26;
          v34 = v15;
          LODWORD(v32) = 1993;
          v37 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
          v20 = &v37;
          v21 = &byte_18034BF07;
          goto LABEL_25;
        }
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v33 = v15;
          LODWORD(v37) = 1985;
          v32 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
          v20 = &v32;
          v21 = byte_18034C231;
          goto LABEL_25;
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        LODWORD(v39) = 7;
        LODWORD(v40) = 1966;
        v32 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
        v20 = &v32;
        v21 = &byte_18034A727;
        goto LABEL_25;
      }
    }
LABEL_26:
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
        v36 = "RemoveStorageFaultDomain";
        v43 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v50 & (unsigned int)-(v51 != 0),
          (__int64)&word_18034BAF6,
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
    LODWORD(v32) = 2021;
    v43 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v27,
      (__int64)&dword_18034C79C,
      v28,
      v29,
      &v43);
  }
  if ( a2 && a2->ft )
    ((void (__fastcall *)(MI_Context *, _QWORD))a2->ft->PostResult)(a2, (unsigned int)v15);
  CSmTimer::~CSmTimer((CSmTimer *)v44);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v35);
  return EventActivityIdControl(4u, &v56);
}

```

## disassembly

```asm
0x18013beb0  mov     [rsp-8+arg_10], rbx
0x18013beb5  push    rbp
0x18013beb6  push    rsi
0x18013beb7  push    rdi
0x18013beb8  push    r12
0x18013beba  push    r13
0x18013bebc  push    r14
0x18013bebe  push    r15
0x18013bec0  lea     rbp, [rsp-140h]
0x18013bec8  sub     rsp, 240h
0x18013becf  mov     rax, cs:__security_cookie
0x18013bed6  xor     rax, rsp
0x18013bed9  mov     [rbp+170h+var_40], rax
0x18013bee0  mov     rdi, rdx
0x18013bee3  mov     r14, rcx
0x18013bee6  mov     rsi, [rbp+170h+arg_28]
0x18013beed  mov     r13, [rbp+170h+arg_30]
0x18013bef4  xorps   xmm0, xmm0
0x18013bef7  xor     eax, eax
0x18013bef9  movups  xmmword ptr [rbp+170h+value], xmm0
0x18013befd  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18013bf01  mov     qword ptr [rbp+170h+value+20h], rax
0x18013bf05  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013bf0c  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18013bf14  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18013bf1b  lea     ecx, [rax+1]; ControlCode
0x18013bf1e  call    cs:__imp_EventActivityIdControl
0x18013bf24  lea     r9, [rbp+170h+value]; value
0x18013bf28  mov     rcx, rdi; context
0x18013bf2b  call    MI_Context_GetCustomOption_1
0x18013bf30  xor     ebx, ebx
0x18013bf32  test    eax, eax
0x18013bf34  jnz     short loc_18013BF47
0x18013bf36  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18013bf3d  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18013bf41  call    cs:__imp_CLSIDFromString
0x18013bf47  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18013bf4e  mov     [rbp+170h+var_60], rcx
0x18013bf55  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18013bf5c  mov     [rbp+170h+var_58], rax
0x18013bf63  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18013bf6a  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18013bf71  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18013bf78  mov     ecx, 4; ControlCode
0x18013bf7d  call    cs:__imp_EventActivityIdControl
0x18013bf83  mov     eax, cs:dword_180397B68
0x18013bf89  lea     rcx, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18013bf90  cmp     eax, 5
0x18013bf93  jbe     short loc_18013BFBE
0x18013bf95  mov     dword ptr [rbp+170h+var_1D8], 784h
0x18013bf9c  mov     [rbp+170h+var_1F0], rcx
0x18013bfa0  lea     rax, [rbp+170h+var_1D8]
0x18013bfa4  mov     [rsp+270h+var_248], rax
0x18013bfa9  lea     rax, [rbp+170h+var_1F0]
0x18013bfad  mov     qword ptr [rsp+270h+var_250], rax
0x18013bfb2  lea     rdx, word_18034AC9E
0x18013bfb9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013bfbe  mov     [rbp+170h+instance.ft], rbx
0x18013bfc5  xor     edx, edx; Val
0x18013bfc7  lea     r8d, [rdx+78h]; Size
0x18013bfcb  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18013bfd2  call    memset_0
0x18013bfd7  xorps   xmm0, xmm0
0x18013bfda  xor     eax, eax
0x18013bfdc  movups  [rbp+170h+var_178], xmm0
0x18013bfe0  mov     [rbp+170h+var_168], rax
0x18013bfe4  mov     [rbp+170h+var_1E0], rbx
0x18013bfe8  lea     rcx, [rbp+170h+var_1E0]
0x18013bfec  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013bff1  mov     [rbp+170h+var_1E0], rbx
0x18013bff5  mov     r15d, ebx
0x18013bff8  lea     rcx, [rbp+170h+var_198]; this
0x18013bffc  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013c001  mov     rcx, rdi; context
0x18013c004  call    WspIsRemoteRequest
0x18013c009  mov     r12d, eax
0x18013c00c  test    eax, eax
0x18013c00e  jnz     short loc_18013C033
0x18013c010  lea     rcx, [rbp+170h+var_198]; this
0x18013c014  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013c019  cmp     [rsi+48h], bl
0x18013c01c  jz      short loc_18013C030
0x18013c01e  mov     rcx, [rsi+40h]; unsigned __int16 *
0x18013c022  call    WspIsRemoteInstance
0x18013c027  test    al, al
0x18013c029  lea     r15d, [r12+1]
0x18013c02e  jnz     short loc_18013C033
0x18013c030  mov     r15d, ebx
0x18013c033  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013c03a  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013c03f  mov     ebx, eax
0x18013c041  test    eax, eax
0x18013c043  jnz     loc_18013C264
0x18013c049  mov     dword ptr [rbp+170h+var_178], 10h
0x18013c050  mov     rax, [rsi+40h]
0x18013c054  mov     qword ptr [rbp+170h+var_178+8], rax
0x18013c058  mov     rbx, [r14]
0x18013c05b  lea     rcx, [rbp+170h+var_1E0]
0x18013c05f  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013c064  mov     [rsp+270h+var_250], 1; int
0x18013c06c  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18013c070  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18013c074  mov     rdx, rdi; context
0x18013c077  mov     rcx, rbx; this
0x18013c07a  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013c07f  mov     ebx, eax
0x18013c081  test    eax, eax
0x18013c083  jz      short loc_18013C0CB
0x18013c085  mov     eax, cs:dword_180397B68
0x18013c08b  cmp     eax, 2
0x18013c08e  jbe     loc_18013C258
0x18013c094  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18013c097  mov     dword ptr [rbp+170h+var_1C8], 7A4h
0x18013c09e  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18013c0a5  mov     [rbp+170h+var_1F0], rax
0x18013c0a9  lea     rax, [rbp+170h+var_1D8]
0x18013c0ad  mov     [rsp+270h+var_240], rax
0x18013c0b2  lea     rax, [rbp+170h+var_1C8]
0x18013c0b6  mov     [rsp+270h+var_248], rax
0x18013c0bb  lea     rax, [rbp+170h+var_1F0]
0x18013c0bf  lea     rdx, byte_18034A9E5
0x18013c0c6  jmp     loc_18013C24E
0x18013c0cb  mov     r8, [rsi+40h]
0x18013c0cf  mov     rdx, rdi
0x18013c0d2  mov     rcx, [r14]
0x18013c0d5  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18013c0da  cmp     eax, 3
0x18013c0dd  jnb     short loc_18013C12A
0x18013c0df  mov     ebx, 7
0x18013c0e4  mov     eax, cs:dword_180397B68
0x18013c0ea  cmp     eax, 2
0x18013c0ed  jbe     loc_18013C258
0x18013c0f3  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18013c0f6  mov     dword ptr [rbp+170h+var_1B8], 7AEh
0x18013c0fd  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18013c104  mov     [rbp+170h+var_1F0], rax
0x18013c108  lea     rax, [rbp+170h+var_1C0]
0x18013c10c  mov     [rsp+270h+var_240], rax
0x18013c111  lea     rax, [rbp+170h+var_1B8]
0x18013c115  mov     [rsp+270h+var_248], rax
0x18013c11a  lea     rax, [rbp+170h+var_1F0]
0x18013c11e  lea     rdx, byte_18034A727
0x18013c125  jmp     loc_18013C24E
0x18013c12a  lea     r8, [rbp+170h+instance]; instance
0x18013c131  lea     rdx, SPACES_VirtualDisk_RemoveStorageFaultDomain_rtti; methodDecl
0x18013c138  mov     rcx, rdi; context
0x18013c13b  call    MI_Context_ConstructParameters
0x18013c140  mov     ebx, eax
0x18013c142  test    eax, eax
0x18013c144  jz      short loc_18013C18C
0x18013c146  mov     eax, cs:dword_180397B68
0x18013c14c  cmp     eax, 2
0x18013c14f  jbe     loc_18013C258
0x18013c155  mov     dword ptr [rbp+170h+var_1B0], ebx
0x18013c158  mov     dword ptr [rbp+170h+var_1A8], 7B6h
0x18013c15f  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18013c166  mov     [rbp+170h+var_1F0], rax
0x18013c16a  lea     rax, [rbp+170h+var_1B0]
0x18013c16e  mov     [rsp+270h+var_240], rax
0x18013c173  lea     rax, [rbp+170h+var_1A8]
0x18013c177  mov     [rsp+270h+var_248], rax
0x18013c17c  lea     rax, [rbp+170h+var_1F0]
0x18013c180  lea     rdx, unk_18034BE00
0x18013c187  jmp     loc_18013C24E
0x18013c18c  mov     rcx, [rbp+170h+var_1E0]
0x18013c190  mov     rax, [rcx]
0x18013c193  lea     rdx, [rbp+170h+instance]
0x18013c19a  mov     qword ptr [rsp+270h+var_250], rdx
0x18013c19f  mov     r9, r13
0x18013c1a2  mov     r8, rdi
0x18013c1a5  mov     edx, 100012h
0x18013c1aa  mov     rax, [rax+30h]
0x18013c1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c1b3  mov     ebx, eax
0x18013c1b5  test    eax, eax
0x18013c1b7  jz      short loc_18013C1FC
0x18013c1b9  mov     eax, cs:dword_180397B68
0x18013c1bf  cmp     eax, 2
0x18013c1c2  jbe     loc_18013C258
0x18013c1c8  mov     [rbp+170h+var_1E8], ebx
0x18013c1cb  mov     dword ptr [rbp+170h+var_1D0], 7C1h
0x18013c1d2  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18013c1d9  mov     [rbp+170h+var_1F0], rax
0x18013c1dd  lea     rax, [rbp+170h+var_1E8]
0x18013c1e1  mov     [rsp+270h+var_240], rax
0x18013c1e6  lea     rax, [rbp+170h+var_1D0]
0x18013c1ea  mov     [rsp+270h+var_248], rax
0x18013c1ef  lea     rax, [rbp+170h+var_1F0]
0x18013c1f3  lea     rdx, byte_18034C231
0x18013c1fa  jmp     short loc_18013C24E
0x18013c1fc  lea     rdx, [rbp+170h+instance]
0x18013c203  mov     rcx, rdi; self
0x18013c206  call    MI_Instance_Destruct
0x18013c20b  mov     ebx, eax
0x18013c20d  test    eax, eax
0x18013c20f  jz      short loc_18013C258
0x18013c211  mov     eax, cs:dword_180397B68
0x18013c217  cmp     eax, 2
0x18013c21a  jbe     short loc_18013C258
0x18013c21c  mov     [rbp+170h+var_1E4], ebx
0x18013c21f  mov     dword ptr [rbp+170h+var_1F0], 7C9h
0x18013c226  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18013c22d  mov     [rbp+170h+var_1D0], rax
0x18013c231  lea     rax, [rbp+170h+var_1E4]
0x18013c235  mov     [rsp+270h+var_240], rax
0x18013c23a  lea     rax, [rbp+170h+var_1F0]
0x18013c23e  mov     [rsp+270h+var_248], rax
0x18013c243  lea     rax, [rbp+170h+var_1D0]
0x18013c247  lea     rdx, byte_18034BF07
0x18013c24e  mov     qword ptr [rsp+270h+var_250], rax
0x18013c253  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013c258  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013c25f  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013c264  xor     r14d, r14d
0x18013c267  test    r12d, r12d
0x18013c26a  jnz     loc_18013C3D6
0x18013c270  lea     rcx, [rbp+170h+var_198]; this
0x18013c274  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013c279  mov     eax, cs:dword_180397B68
0x18013c27f  cmp     eax, 5
0x18013c282  jbe     loc_18013C3D6
0x18013c288  mov     rdx, 400000000000h
0x18013c292  lea     rcx, dword_180397B68
0x18013c299  call    _tlgKeywordOn
0x18013c29e  test    al, al
0x18013c2a0  jz      loc_18013C3D6
0x18013c2a6  cmp     [r13+58h], r14b
0x18013c2aa  jz      short loc_18013C2B2
0x18013c2ac  mov     eax, [r13+50h]
0x18013c2b0  jmp     short loc_18013C2B5
0x18013c2b2  mov     eax, r14d
0x18013c2b5  mov     dword ptr [rbp+170h+var_1F0], eax
0x18013c2b8  cmp     [rbp+170h+var_88], r14b
0x18013c2bf  jz      short loc_18013C2FC
0x18013c2c1  mov     rax, [rbp+170h+var_90]
0x18013c2c8  movups  xmm0, xmmword ptr [rax]
0x18013c2cb  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18013c2cf  movups  xmm1, xmmword ptr [rax+10h]
0x18013c2d3  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18013c2d7  movups  xmm0, xmmword ptr [rax+20h]
0x18013c2db  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18013c2df  movups  xmm1, xmmword ptr [rax+30h]
0x18013c2e3  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18013c2e7  xor     r8d, r8d; unsigned __int16 *
0x18013c2ea  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18013c2ee  lea     rcx, name; "ObjectId"
0x18013c2f5  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18013c2fa  jmp     short loc_18013C2FF
0x18013c2fc  mov     rax, r14
0x18013c2ff  mov     [rbp+170h+var_1A8], rax
0x18013c303  mov     [rbp+170h+var_1B0], r14
0x18013c307  mov     [rbp+170h+var_1B8], r14
0x18013c30b  mov     rax, [rbp+170h+var_190]
0x18013c30f  sub     rax, [rbp+170h+var_198]
0x18013c313  imul    rax, 3E8h
0x18013c31a  xor     edx, edx
0x18013c31c  div     [rbp+170h+var_188]
0x18013c320  mov     [rbp+170h+var_1C0], rax
0x18013c324  mov     [rbp+170h+var_1E4], ebx
0x18013c327  mov     al, [rbp+170h+var_AC]
0x18013c32d  neg     al
0x18013c32f  sbb     ecx, ecx
0x18013c331  and     ecx, [rbp+170h+var_B0]
0x18013c337  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18013c33a  mov     [rbp+170h+var_1E8], r15d
0x18013c33e  cmp     [rsi+48h], r14b
0x18013c342  jz      short loc_18013C34A
0x18013c344  mov     rax, [rsi+40h]
0x18013c348  jmp     short loc_18013C34D
0x18013c34a  mov     rax, r14
0x18013c34d  mov     [rbp+170h+var_1C8], rax
0x18013c351  lea     rax, aRemovestoragef_0; "RemoveStorageFaultDomain"
0x18013c358  mov     [rbp+170h+var_1D8], rax
0x18013c35c  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013c363  mov     [rbp+170h+var_1A0], rax
0x18013c367  lea     rax, [rbp+170h+var_1F0]
0x18013c36b  mov     [rsp+270h+var_200], rax
0x18013c370  lea     rax, [rbp+170h+var_1A8]
0x18013c374  mov     [rsp+270h+var_208], rax
0x18013c379  lea     rax, [rbp+170h+var_1B0]
0x18013c37d  mov     [rsp+270h+var_210], rax
0x18013c382  lea     rax, [rbp+170h+var_1B8]
0x18013c386  mov     [rsp+270h+var_218], rax
0x18013c38b  lea     rax, [rbp+170h+var_1C0]
0x18013c38f  mov     [rsp+270h+var_220], rax
0x18013c394  lea     rax, [rbp+170h+var_1E4]
0x18013c398  mov     [rsp+270h+var_228], rax
0x18013c39d  lea     rax, [rbp+170h+var_1D0]
0x18013c3a1  mov     [rsp+270h+var_230], rax
0x18013c3a6  lea     rax, [rbp+170h+var_1E8]
0x18013c3aa  mov     [rsp+270h+var_238], rax
0x18013c3af  lea     rax, [rbp+170h+var_1C8]
0x18013c3b3  mov     [rsp+270h+var_240], rax
0x18013c3b8  lea     rax, [rbp+170h+var_1D8]
0x18013c3bc  mov     [rsp+270h+var_248], rax
0x18013c3c1  lea     rax, [rbp+170h+var_1A0]
0x18013c3c5  mov     qword ptr [rsp+270h+var_250], rax
0x18013c3ca  lea     rdx, word_18034BAF6
0x18013c3d1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@3445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18013c3d6  lea     rcx, [rbp+170h+instance]; self
  ... truncated ...
```
