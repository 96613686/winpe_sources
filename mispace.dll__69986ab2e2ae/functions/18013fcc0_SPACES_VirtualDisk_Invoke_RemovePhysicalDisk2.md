# SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2

- ea: `0x18013fcc0`
- end: `0x1801402fb`
- name: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- size: `1595`
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
- `0x18013fcc0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013fd2e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013fd99`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801402c4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013fd2e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013fd99`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801402c4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013fd57`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013fd57`

## string_xrefs

- `0x1801401d0`: `RemovePhysicalDisk`
- `0x18013fdab`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013fec1`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013ff1e`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18013ff80`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x18014002f`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x180140104`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`
- `0x180140273`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2`

## pseudocode

```c
ULONG __fastcall SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2(
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
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v39; // r9d
  const char *v41; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v42; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v43; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v44; // [rsp+90h] [rbp-70h] BYREF
  const char *v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v51; // [rsp+C8h] [rbp-38h] BYREF
  const char *v52; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v53[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v56; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  int v59; // [rsp+1C0h] [rbp+C0h]
  char v60; // [rsp+1C4h] [rbp+C4h]
  struct _MI_Instance *v61; // [rsp+1E0h] [rbp+E0h]
  char v62; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v64; // [rsp+210h] [rbp+110h]
  GUID v65; // [rsp+220h] [rbp+120h] BYREF

  memset(&value, 0, sizeof(value));
  ActivityId = GUID_NULL;
  EventActivityIdControl(1u, &ActivityId);
  if ( MI_Context_GetCustomOption_1(a2, v9, v10, &value) == MI_RESULT_OK )
    CLSIDFromString(value.string, &ActivityId);
  v64 = ActivityId;
  v65 = ActivityId;
  EventActivityIdControl(4u, &v65);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v45) = 1680;
    v41 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2",
      (unsigned int)&dword_18035231C,
      v11,
      v12,
      (__int64)&v41,
      (__int64)&v45);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v54 = 0;
  v55 = 0;
  v44 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v44);
  v44 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v53);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v53);
    if ( !*(_BYTE *)(a6 + 72)
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance(*(unsigned __int16 **)(a6 + 64))) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v54) = 16;
    *((_QWORD *)&v54 + 1) = *(_QWORD *)(a6 + 64);
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v44);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v54, &v44, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v45) = v15;
        LODWORD(v47) = 1712;
        v41 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180351D38,
          v18,
          v19,
          (__int64)&v41,
          (__int64)&v47,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_RemovePhysicalDisk2_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v50) = v15;
          LODWORD(v51) = 1731;
          v41 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)word_180351DAA,
            v24,
            v25,
            (__int64)&v41,
            (__int64)&v51,
            (__int64)&v50);
        }
      }
      else
      {
        if ( v13 && *(_BYTE *)(a7 + 88) && *(_DWORD *)(a7 + 80) > 0x200u )
        {
          v59 = 5;
          v60 = 1;
          PostExtendedStatus(a2, &instance, 0x8022u, 1u, L"512");
        }
        else
        {
          v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v44 + 48LL))(
                  v44,
                  1048590,
                  a2,
                  a7,
                  &instance);
          if ( v15 )
          {
            if ( (unsigned int)dword_18039EB68 > 2 )
            {
              v42 = v15;
              LODWORD(v46) = 1758;
              v41 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v32,
                (unsigned int)word_180352D22,
                v33,
                v34,
                (__int64)&v41,
                (__int64)&v46,
                (__int64)&v42);
            }
            goto LABEL_26;
          }
        }
        v15 = MI_Instance_Destruct((MI_Instance *)a2);
        if ( v15 && (unsigned int)dword_18039EB68 > 2 )
        {
          v43 = v15;
          LODWORD(v41) = 1767;
          v46 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)word_1803532AA,
            v27,
            v28,
            (__int64)&v46,
            (__int64)&v41,
            (__int64)&v43);
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v48) = 7;
        LODWORD(v49) = 1723;
        v41 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&word_180351A46,
          v21,
          v22,
          (__int64)&v41,
          (__int64)&v49,
          (__int64)&v48);
      }
    }
LABEL_26:
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v53);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 88) )
          v31 = *(_DWORD *)(a7 + 80);
        else
          v31 = 0;
        LODWORD(v41) = v31;
        if ( v62 )
        {
          v56 = *v61;
          v35 = SmMIGetString(L"ObjectId", &v56, 0);
        }
        else
        {
          v35 = 0;
        }
        v51 = v35;
        v50 = 0;
        v49 = 0;
        v48 = (unsigned __int64)(1000LL * (v53[1] - v53[0])) / v53[2];
        v43 = v15;
        LODWORD(v46) = v60 != 0 ? v59 : 0;
        v42 = v13;
        if ( *(_BYTE *)(a6 + 72) )
          v36 = *(_QWORD *)(a6 + 64);
        else
          v36 = 0;
        v47 = v36;
        v45 = "RemovePhysicalDisk";
        v52 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v60 != 0 ? v59 : 0,
          (unsigned int)&word_1803521EE,
          v29,
          v30,
          (__int64)&v52,
          (__int64)&v45,
          (__int64)&v47,
          (__int64)&v42,
          (__int64)&v46,
          (__int64)&v43,
          (__int64)&v48,
          (__int64)&v49,
          (__int64)&v50,
          (__int64)&v51,
          (__int64)&v41);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v41) = 1795;
    v52 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk2";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)&dword_1803534F4,
      v38,
      v39,
      (__int64)&v52,
      (__int64)&v41);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v53);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v44);
  return EventActivityIdControl(4u, &v65);
}

```

## disassembly

```asm
0x18013fcc0  mov     [rsp-8+arg_10], rbx
0x18013fcc5  push    rbp
0x18013fcc6  push    rsi
0x18013fcc7  push    rdi
0x18013fcc8  push    r12
0x18013fcca  push    r13
0x18013fccc  push    r14
0x18013fcce  push    r15
0x18013fcd0  lea     rbp, [rsp-140h]
0x18013fcd8  sub     rsp, 240h
0x18013fcdf  mov     rax, cs:__security_cookie
0x18013fce6  xor     rax, rsp
0x18013fce9  mov     [rbp+170h+var_40], rax
0x18013fcf0  mov     rdi, rdx
0x18013fcf3  mov     r12, rcx
0x18013fcf6  mov     r14, [rbp+170h+arg_28]
0x18013fcfd  mov     rsi, [rbp+170h+arg_30]
0x18013fd04  xorps   xmm0, xmm0
0x18013fd07  xor     eax, eax
0x18013fd09  movups  xmmword ptr [rbp+170h+value], xmm0
0x18013fd0d  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18013fd11  mov     qword ptr [rbp+170h+value+20h], rax
0x18013fd15  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013fd1c  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18013fd24  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18013fd2b  lea     ecx, [rax+1]; ControlCode
0x18013fd2e  call    cs:__imp_EventActivityIdControl
0x18013fd35  nop     dword ptr [rax+rax+00h]
0x18013fd3a  lea     r9, [rbp+170h+value]; value
0x18013fd3e  mov     rcx, rdi; context
0x18013fd41  call    MI_Context_GetCustomOption_1
0x18013fd46  xor     ebx, ebx
0x18013fd48  test    eax, eax
0x18013fd4a  jnz     short loc_18013FD63
0x18013fd4c  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18013fd53  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18013fd57  call    cs:__imp_CLSIDFromString
0x18013fd5e  nop     dword ptr [rax+rax+00h]
0x18013fd63  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18013fd6a  mov     [rbp+170h+var_60], rcx
0x18013fd71  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18013fd78  mov     [rbp+170h+var_58], rax
0x18013fd7f  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18013fd86  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18013fd8d  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18013fd94  mov     ecx, 4; ControlCode
0x18013fd99  call    cs:__imp_EventActivityIdControl
0x18013fda0  nop     dword ptr [rax+rax+00h]
0x18013fda5  mov     eax, cs:dword_18039EB68
0x18013fdab  lea     rcx, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013fdb2  cmp     eax, 5
0x18013fdb5  jbe     short loc_18013FDE0
0x18013fdb7  mov     dword ptr [rbp+170h+var_1D8], 690h
0x18013fdbe  mov     [rbp+170h+var_1F0], rcx
0x18013fdc2  lea     rax, [rbp+170h+var_1D8]
0x18013fdc6  mov     [rsp+270h+var_248], rax
0x18013fdcb  lea     rax, [rbp+170h+var_1F0]
0x18013fdcf  mov     qword ptr [rsp+270h+var_250], rax
0x18013fdd4  lea     rdx, dword_18035231C
0x18013fddb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013fde0  mov     [rbp+170h+instance.ft], rbx
0x18013fde7  xor     edx, edx; Val
0x18013fde9  lea     r8d, [rdx+78h]; Size
0x18013fded  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18013fdf4  call    memset_0
0x18013fdf9  xorps   xmm0, xmm0
0x18013fdfc  xor     eax, eax
0x18013fdfe  movups  [rbp+170h+var_178], xmm0
0x18013fe02  mov     [rbp+170h+var_168], rax
0x18013fe06  mov     [rbp+170h+var_1E0], rbx
0x18013fe0a  lea     rcx, [rbp+170h+var_1E0]
0x18013fe0e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013fe13  mov     [rbp+170h+var_1E0], rbx
0x18013fe17  mov     r15d, ebx
0x18013fe1a  lea     rcx, [rbp+170h+var_198]; this
0x18013fe1e  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013fe23  mov     rcx, rdi; context
0x18013fe26  call    WspIsRemoteRequest
0x18013fe2b  mov     r13d, eax
0x18013fe2e  test    eax, eax
0x18013fe30  jnz     short loc_18013FE55
0x18013fe32  lea     rcx, [rbp+170h+var_198]; this
0x18013fe36  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013fe3b  cmp     [r14+48h], bl
0x18013fe3f  jz      short loc_18013FE52
0x18013fe41  mov     rcx, [r14+40h]; unsigned __int16 *
0x18013fe45  call    WspIsRemoteInstance
0x18013fe4a  test    al, al
0x18013fe4c  lea     r15d, [r13+1]
0x18013fe50  jnz     short loc_18013FE55
0x18013fe52  mov     r15d, ebx
0x18013fe55  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013fe5c  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013fe61  mov     ebx, eax
0x18013fe63  test    eax, eax
0x18013fe65  jnz     loc_18014006D
0x18013fe6b  mov     dword ptr [rbp+170h+var_178], 10h
0x18013fe72  mov     rax, [r14+40h]
0x18013fe76  mov     qword ptr [rbp+170h+var_178+8], rax
0x18013fe7a  mov     rbx, [r12]
0x18013fe7e  lea     rcx, [rbp+170h+var_1E0]
0x18013fe82  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013fe87  mov     [rsp+270h+var_250], 1; int
0x18013fe8f  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18013fe93  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18013fe97  mov     rdx, rdi; context
0x18013fe9a  mov     rcx, rbx; this
0x18013fe9d  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013fea2  mov     ebx, eax
0x18013fea4  test    eax, eax
0x18013fea6  jz      short loc_18013FEEE
0x18013fea8  mov     eax, cs:dword_18039EB68
0x18013feae  cmp     eax, 2
0x18013feb1  jbe     loc_180140061
0x18013feb7  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18013feba  mov     dword ptr [rbp+170h+var_1C8], 6B0h
0x18013fec1  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013fec8  mov     [rbp+170h+var_1F0], rax
0x18013fecc  lea     rax, [rbp+170h+var_1D8]
0x18013fed0  mov     [rsp+270h+var_240], rax
0x18013fed5  lea     rax, [rbp+170h+var_1C8]
0x18013fed9  mov     [rsp+270h+var_248], rax
0x18013fede  lea     rax, [rbp+170h+var_1F0]
0x18013fee2  lea     rdx, unk_180351D38
0x18013fee9  jmp     loc_180140057
0x18013feee  mov     r8, [r14+40h]
0x18013fef2  mov     rdx, rdi
0x18013fef5  mov     rcx, [r12]
0x18013fef9  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18013fefe  test    eax, eax
0x18013ff00  jnz     short loc_18013FF4B
0x18013ff02  lea     ebx, [rax+7]
0x18013ff05  mov     eax, cs:dword_18039EB68
0x18013ff0b  cmp     eax, 2
0x18013ff0e  jbe     loc_180140061
0x18013ff14  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18013ff17  mov     dword ptr [rbp+170h+var_1B8], 6BBh
0x18013ff1e  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013ff25  mov     [rbp+170h+var_1F0], rax
0x18013ff29  lea     rax, [rbp+170h+var_1C0]
0x18013ff2d  mov     [rsp+270h+var_240], rax
0x18013ff32  lea     rax, [rbp+170h+var_1B8]
0x18013ff36  mov     [rsp+270h+var_248], rax
0x18013ff3b  lea     rax, [rbp+170h+var_1F0]
0x18013ff3f  lea     rdx, word_180351A46
0x18013ff46  jmp     loc_180140057
0x18013ff4b  lea     r8, [rbp+170h+instance]; instance
0x18013ff52  lea     rdx, SPACES_VirtualDisk_RemovePhysicalDisk2_rtti; methodDecl
0x18013ff59  mov     rcx, rdi; context
0x18013ff5c  call    MI_Context_ConstructParameters
0x18013ff61  mov     ebx, eax
0x18013ff63  test    eax, eax
0x18013ff65  jz      short loc_18013FFAD
0x18013ff67  mov     eax, cs:dword_18039EB68
0x18013ff6d  cmp     eax, 2
0x18013ff70  jbe     loc_180140061
0x18013ff76  mov     dword ptr [rbp+170h+var_1B0], ebx
0x18013ff79  mov     dword ptr [rbp+170h+var_1A8], 6C3h
0x18013ff80  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013ff87  mov     [rbp+170h+var_1F0], rax
0x18013ff8b  lea     rax, [rbp+170h+var_1B0]
0x18013ff8f  mov     [rsp+270h+var_240], rax
0x18013ff94  lea     rax, [rbp+170h+var_1A8]
0x18013ff98  mov     [rsp+270h+var_248], rax
0x18013ff9d  lea     rax, [rbp+170h+var_1F0]
0x18013ffa1  lea     rdx, word_180351DAA
0x18013ffa8  jmp     loc_180140057
0x18013ffad  test    r15d, r15d
0x18013ffb0  jz      loc_1801400BA
0x18013ffb6  cmp     byte ptr [rsi+58h], 0
0x18013ffba  jz      loc_1801400BA
0x18013ffc0  cmp     dword ptr [rsi+50h], 200h
0x18013ffc7  jbe     loc_1801400BA
0x18013ffcd  mov     [rbp+170h+var_B0], 5
0x18013ffd7  mov     [rbp+170h+var_AC], 1
0x18013ffde  lea     rax, a512; "512"
0x18013ffe5  mov     qword ptr [rsp+270h+var_250], rax
0x18013ffea  mov     r9d, 1; unsigned int
0x18013fff0  mov     r8d, 8022h; unsigned int
0x18013fff6  lea     rdx, [rbp+170h+instance]; struct _MI_Instance *
0x18013fffd  mov     rcx, rdi; struct _MI_Context *
0x180140000  call    ?PostExtendedStatus@@YA_NPEAU_MI_Context@@PEAU_MI_Instance@@KIZZ; PostExtendedStatus(_MI_Context *,_MI_Instance *,ulong,uint,...)
0x180140005  lea     rdx, [rbp+170h+instance]
0x18014000c  mov     rcx, rdi; self
0x18014000f  call    MI_Instance_Destruct
0x180140014  mov     ebx, eax
0x180140016  test    eax, eax
0x180140018  jz      short loc_180140061
0x18014001a  mov     eax, cs:dword_18039EB68
0x180140020  cmp     eax, 2
0x180140023  jbe     short loc_180140061
0x180140025  mov     [rbp+170h+var_1E4], ebx
0x180140028  mov     dword ptr [rbp+170h+var_1F0], 6E7h
0x18014002f  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x180140036  mov     [rbp+170h+var_1D0], rax
0x18014003a  lea     rax, [rbp+170h+var_1E4]
0x18014003e  mov     [rsp+270h+var_240], rax
0x180140043  lea     rax, [rbp+170h+var_1F0]
0x180140047  mov     [rsp+270h+var_248], rax
0x18014004c  lea     rax, [rbp+170h+var_1D0]
0x180140050  lea     rdx, word_1803532AA
0x180140057  mov     qword ptr [rsp+270h+var_250], rax
0x18014005c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180140061  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x180140068  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18014006d  xor     r12d, r12d
0x180140070  test    r13d, r13d
0x180140073  jnz     loc_180140255
0x180140079  lea     rcx, [rbp+170h+var_198]; this
0x18014007d  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180140082  mov     eax, cs:dword_18039EB68
0x180140088  cmp     eax, 5
0x18014008b  jbe     loc_180140255
0x180140091  mov     rdx, 400000000000h
0x18014009b  lea     rcx, dword_18039EB68
0x1801400a2  call    _tlgKeywordOn
0x1801400a7  test    al, al
0x1801400a9  jz      loc_180140255
0x1801400af  cmp     [rsi+58h], r12b
0x1801400b3  jz      short loc_180140131
0x1801400b5  mov     eax, [rsi+50h]
0x1801400b8  jmp     short loc_180140134
0x1801400ba  mov     rcx, [rbp+170h+var_1E0]
0x1801400be  mov     rax, [rcx]
0x1801400c1  lea     rdx, [rbp+170h+instance]
0x1801400c8  mov     qword ptr [rsp+270h+var_250], rdx
0x1801400cd  mov     r9, rsi
0x1801400d0  mov     r8, rdi
0x1801400d3  mov     edx, 10000Eh
0x1801400d8  mov     rax, [rax+30h]
0x1801400dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801400e1  mov     ebx, eax
0x1801400e3  test    eax, eax
0x1801400e5  jz      loc_180140005
0x1801400eb  mov     eax, cs:dword_18039EB68
0x1801400f1  cmp     eax, 2
0x1801400f4  jbe     loc_180140061
0x1801400fa  mov     [rbp+170h+var_1E8], ebx
0x1801400fd  mov     dword ptr [rbp+170h+var_1D0], 6DEh
0x180140104  lea     rax, aSpacesVirtuald_1; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18014010b  mov     [rbp+170h+var_1F0], rax
0x18014010f  lea     rax, [rbp+170h+var_1E8]
0x180140113  mov     [rsp+270h+var_240], rax
0x180140118  lea     rax, [rbp+170h+var_1D0]
0x18014011c  mov     [rsp+270h+var_248], rax
0x180140121  lea     rax, [rbp+170h+var_1F0]
0x180140125  lea     rdx, word_180352D22
0x18014012c  jmp     loc_180140057
0x180140131  mov     eax, r12d
0x180140134  mov     dword ptr [rbp+170h+var_1F0], eax
0x180140137  cmp     [rbp+170h+var_88], r12b
0x18014013e  jz      short loc_18014017B
0x180140140  mov     rax, [rbp+170h+var_90]
0x180140147  movups  xmm0, xmmword ptr [rax]
0x18014014a  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18014014e  movups  xmm1, xmmword ptr [rax+10h]
0x180140152  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x180140156  movups  xmm0, xmmword ptr [rax+20h]
0x18014015a  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18014015e  movups  xmm1, xmmword ptr [rax+30h]
0x180140162  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x180140166  xor     r8d, r8d; unsigned __int16 *
0x180140169  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18014016d  lea     rcx, name; "ObjectId"
0x180140174  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x180140179  jmp     short loc_18014017E
0x18014017b  mov     rax, r12
0x18014017e  mov     [rbp+170h+var_1A8], rax
0x180140182  mov     [rbp+170h+var_1B0], r12
0x180140186  mov     [rbp+170h+var_1B8], r12
0x18014018a  mov     rax, [rbp+170h+var_190]
0x18014018e  sub     rax, [rbp+170h+var_198]
0x180140192  imul    rax, 3E8h
0x180140199  xor     edx, edx
0x18014019b  div     [rbp+170h+var_188]
0x18014019f  mov     [rbp+170h+var_1C0], rax
0x1801401a3  mov     [rbp+170h+var_1E4], ebx
0x1801401a6  mov     al, [rbp+170h+var_AC]
0x1801401ac  neg     al
0x1801401ae  sbb     ecx, ecx
0x1801401b0  and     ecx, [rbp+170h+var_B0]
0x1801401b6  mov     dword ptr [rbp+170h+var_1D0], ecx
0x1801401b9  mov     [rbp+170h+var_1E8], r15d
0x1801401bd  cmp     [r14+48h], r12b
0x1801401c1  jz      short loc_1801401C9
0x1801401c3  mov     rax, [r14+40h]
0x1801401c7  jmp     short loc_1801401CC
0x1801401c9  mov     rax, r12
0x1801401cc  mov     [rbp+170h+var_1C8], rax
0x1801401d0  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x1801401d7  mov     [rbp+170h+var_1D8], rax
0x1801401db  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x1801401e2  mov     [rbp+170h+var_1A0], rax
0x1801401e6  lea     rax, [rbp+170h+var_1F0]
0x1801401ea  mov     [rsp+270h+var_200], rax
0x1801401ef  lea     rax, [rbp+170h+var_1A8]
0x1801401f3  mov     [rsp+270h+var_208], rax
0x1801401f8  lea     rax, [rbp+170h+var_1B0]
0x1801401fc  mov     [rsp+270h+var_210], rax
0x180140201  lea     rax, [rbp+170h+var_1B8]
  ... truncated ...
```
