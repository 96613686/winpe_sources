# SPACES_VirtualDisk_Invoke_RemovePhysicalDisk

- ea: `0x18013f700`
- end: `0x18013fcb4`
- name: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- size: `1460`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
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
- `0x18001b4a0`
- `0x180021dcc`
- `0x180023e18`
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x18013f700`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f77d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f7e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013fc7d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f77d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013f7e8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18013fc7d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013f7a6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18013f7a6`

## string_xrefs

- `0x18013f7fa`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013f912`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013f974`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013f9e7`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013fa3b`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013fc2c`: `SPACES_VirtualDisk_Invoke_RemovePhysicalDisk`
- `0x18013fb89`: `RemovePhysicalDisk`

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
  int v11; // r8d
  int v12; // r9d
  enum _MI_Result v13; // r14d
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
  unsigned __int16 *v32; // rax
  const MI_Char *v33; // rax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  const char *v38; // [rsp+80h] [rbp-80h] BYREF
  enum _MI_Result v39; // [rsp+88h] [rbp-78h] BYREF
  enum _MI_Result v40; // [rsp+8Ch] [rbp-74h] BYREF
  struct ISpWmiObject *v41; // [rsp+90h] [rbp-70h] BYREF
  const char *v42; // [rsp+98h] [rbp-68h] BYREF
  const char *v43; // [rsp+A0h] [rbp-60h] BYREF
  const MI_Char *v44; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v45; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v47; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v48; // [rsp+C8h] [rbp-38h] BYREF
  const char *v49; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v50[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+108h] [rbp+8h]
  struct _MI_Instance v53; // [rsp+110h] [rbp+10h] BYREF
  MI_Value value; // [rsp+150h] [rbp+50h] BYREF
  MI_Instance instance; // [rsp+180h] [rbp+80h] BYREF
  struct _MI_ConstUint32Field v56; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _MI_Instance *v57; // [rsp+1E0h] [rbp+E0h]
  char v58; // [rsp+1E8h] [rbp+E8h]
  GUID ActivityId; // [rsp+200h] [rbp+100h] BYREF
  GUID v60; // [rsp+210h] [rbp+110h]
  GUID v61; // [rsp+220h] [rbp+120h] BYREF

  v48 = a4;
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
    LODWORD(v42) = 1572;
    v38 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_RemovePhysicalDisk",
      (unsigned int)qword_1803520E8,
      v11,
      v12,
      (__int64)&v38,
      (__int64)&v42);
  }
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x78u);
  v51 = 0;
  v52 = 0;
  v41 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
  v41 = 0;
  v13 = MI_RESULT_OK;
  CSmTimer::CSmTimer((CSmTimer *)v50);
  IsRemoteRequest = WspIsRemoteRequest(a2);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Start((CSmTimer *)v50);
    if ( !a6[4].exists
      || (v13 = IsRemoteRequest + 1, !(unsigned __int8)WspIsRemoteInstance((unsigned __int16 *)a6[4].value)) )
    {
      v13 = MI_RESULT_OK;
    }
  }
  v15 = MISpaceHandle::AddRef(MISpaceHandle::g_MISpaceHandle);
  if ( v15 == MI_RESULT_OK )
  {
    LODWORD(v51) = 16;
    *((_QWORD *)&v51 + 1) = a6[4].value;
    v16 = *a1;
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
    v15 = CSpProvider::GetInstance(v16, a2, (struct _SP_OBJECT_ID *)&v51, &v41, 1);
    if ( v15 )
    {
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v42) = v15;
        LODWORD(v44) = 1603;
        v38 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&byte_180353AEF,
          v18,
          v19,
          (__int64)&v38,
          (__int64)&v44,
          (__int64)&v42);
      }
    }
    else
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_RemovePhysicalDisk_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v45) = v15;
          LODWORD(v46) = 1611;
          v38 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&unk_180351C98,
            v21,
            v22,
            (__int64)&v38,
            (__int64)&v46,
            (__int64)&v45);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v41 + 48LL))(
                v41,
                1048588,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            v39 = v15;
            LODWORD(v43) = 1622;
            v38 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)word_180352422,
              v24,
              v25,
              (__int64)&v38,
              (__int64)&v43,
              (__int64)&v39);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v40 = v15;
            LODWORD(v38) = 1630;
            v43 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)&word_180352A7E,
              v27,
              v28,
              (__int64)&v43,
              (__int64)&v38,
              (__int64)&v40);
          }
        }
      }
    }
    MISpaceHandle::Release((MISpaceHandle *)MISpaceHandle::g_MISpaceHandle);
  }
  SmLogOnMethodFailure(v48, v47, a6 + 4, &v56, v15, 0);
  if ( !IsRemoteRequest )
  {
    CSmTimer::Stop((CSmTimer *)v50);
    if ( (unsigned int)dword_18039EB68 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
      {
        if ( *(_BYTE *)(a7 + 88) )
          v31 = *(_DWORD *)(a7 + 80);
        else
          v31 = 0;
        LODWORD(v38) = v31;
        if ( v58 )
        {
          v53 = *v57;
          v32 = (unsigned __int16 *)SmMIGetString(L"ObjectId", &v53, 0);
        }
        else
        {
          v32 = 0;
        }
        v48 = v32;
        v47 = 0;
        v46 = 0;
        v45 = (unsigned __int64)(1000LL * (v50[1] - v50[0])) / v50[2];
        v40 = v15;
        LODWORD(v43) = v56.exists != 0 ? v56.value : 0;
        v39 = v13;
        if ( a6[4].exists )
          v33 = a6[4].value;
        else
          v33 = 0;
        v44 = v33;
        v42 = "RemovePhysicalDisk";
        v49 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v56.exists != 0 ? v56.value : 0,
          (unsigned int)&unk_180351E78,
          v29,
          v30,
          (__int64)&v49,
          (__int64)&v42,
          (__int64)&v44,
          (__int64)&v39,
          (__int64)&v43,
          (__int64)&v40,
          (__int64)&v45,
          (__int64)&v46,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v38);
      }
    }
  }
  MI_Instance_Destruct(&instance);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v38) = 1664;
    v49 = "SPACES_VirtualDisk_Invoke_RemovePhysicalDisk";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v34,
      (unsigned int)&dword_180352734,
      v35,
      v36,
      (__int64)&v49,
      (__int64)&v38);
  }
  MI_Context_PostResult_0(a2, v15);
  CSmTimer::~CSmTimer((CSmTimer *)v50);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v41);
  return EventActivityIdControl(4u, &v61);
}

```

## disassembly

```asm
0x18013f700  mov     [rsp-8+arg_10], rbx
0x18013f705  push    rbp
0x18013f706  push    rsi
0x18013f707  push    rdi
0x18013f708  push    r12
0x18013f70a  push    r13
0x18013f70c  push    r14
0x18013f70e  push    r15
0x18013f710  lea     rbp, [rsp-140h]
0x18013f718  sub     rsp, 240h
0x18013f71f  mov     rax, cs:__security_cookie
0x18013f726  xor     rax, rsp
0x18013f729  mov     [rbp+170h+var_40], rax
0x18013f730  mov     [rbp+170h+var_1A8], r9
0x18013f734  mov     rsi, rdx
0x18013f737  mov     r12, rcx
0x18013f73a  mov     rax, [rbp+170h+arg_20]
0x18013f741  mov     [rbp+170h+var_1B0], rax
0x18013f745  mov     rdi, [rbp+170h+arg_28]
0x18013f74c  mov     r15, [rbp+170h+arg_30]
0x18013f753  xorps   xmm0, xmm0
0x18013f756  xor     eax, eax
0x18013f758  movups  xmmword ptr [rbp+170h+value], xmm0
0x18013f75c  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x18013f760  mov     qword ptr [rbp+170h+value+20h], rax
0x18013f764  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18013f76b  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x18013f773  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18013f77a  lea     ecx, [rax+1]; ControlCode
0x18013f77d  call    cs:__imp_EventActivityIdControl
0x18013f784  nop     dword ptr [rax+rax+00h]
0x18013f789  lea     r9, [rbp+170h+value]; value
0x18013f78d  mov     rcx, rsi; context
0x18013f790  call    MI_Context_GetCustomOption_1
0x18013f795  xor     ebx, ebx
0x18013f797  test    eax, eax
0x18013f799  jnz     short loc_18013F7B2
0x18013f79b  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x18013f7a2  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x18013f7a6  call    cs:__imp_CLSIDFromString
0x18013f7ad  nop     dword ptr [rax+rax+00h]
0x18013f7b2  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x18013f7b9  mov     [rbp+170h+var_60], rcx
0x18013f7c0  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x18013f7c7  mov     [rbp+170h+var_58], rax
0x18013f7ce  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x18013f7d5  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x18013f7dc  lea     rdx, [rbp+170h+var_50]; ActivityId
0x18013f7e3  mov     ecx, 4; ControlCode
0x18013f7e8  call    cs:__imp_EventActivityIdControl
0x18013f7ef  nop     dword ptr [rax+rax+00h]
0x18013f7f4  mov     eax, cs:dword_18039EB68
0x18013f7fa  lea     rcx, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013f801  cmp     eax, 5
0x18013f804  jbe     short loc_18013F82F
0x18013f806  mov     dword ptr [rbp+170h+var_1D8], 624h
0x18013f80d  mov     [rbp+170h+var_1F0], rcx
0x18013f811  lea     rax, [rbp+170h+var_1D8]
0x18013f815  mov     [rsp+270h+var_248], rax
0x18013f81a  lea     rax, [rbp+170h+var_1F0]
0x18013f81e  mov     qword ptr [rsp+270h+var_250], rax
0x18013f823  lea     rdx, qword_1803520E8
0x18013f82a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18013f82f  mov     [rbp+170h+instance.ft], rbx
0x18013f836  xor     edx, edx; Val
0x18013f838  lea     r8d, [rdx+78h]; Size
0x18013f83c  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x18013f843  call    memset_0
0x18013f848  xorps   xmm0, xmm0
0x18013f84b  xor     eax, eax
0x18013f84d  movups  [rbp+170h+var_178], xmm0
0x18013f851  mov     [rbp+170h+var_168], rax
0x18013f855  mov     [rbp+170h+var_1E0], rbx
0x18013f859  lea     rcx, [rbp+170h+var_1E0]
0x18013f85d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013f862  mov     [rbp+170h+var_1E0], rbx
0x18013f866  mov     r14d, ebx
0x18013f869  lea     rcx, [rbp+170h+var_198]; this
0x18013f86d  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x18013f872  mov     rcx, rsi; context
0x18013f875  call    WspIsRemoteRequest
0x18013f87a  mov     r13d, eax
0x18013f87d  test    eax, eax
0x18013f87f  jnz     short loc_18013F8A3
0x18013f881  lea     rcx, [rbp+170h+var_198]; this
0x18013f885  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18013f88a  cmp     [rdi+48h], bl
0x18013f88d  jz      short loc_18013F8A0
0x18013f88f  mov     rcx, [rdi+40h]; unsigned __int16 *
0x18013f893  call    WspIsRemoteInstance
0x18013f898  test    al, al
0x18013f89a  lea     r14d, [r13+1]
0x18013f89e  jnz     short loc_18013F8A3
0x18013f8a0  mov     r14d, ebx
0x18013f8a3  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x18013f8aa  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x18013f8af  mov     ebx, eax
0x18013f8b1  test    eax, eax
0x18013f8b3  jnz     loc_18013FA7B
0x18013f8b9  mov     dword ptr [rbp+170h+var_178], 10h
0x18013f8c0  mov     rax, [rdi+40h]
0x18013f8c4  mov     qword ptr [rbp+170h+var_178+8], rax
0x18013f8c8  mov     rbx, [r12]
0x18013f8cc  lea     rcx, [rbp+170h+var_1E0]
0x18013f8d0  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18013f8d5  mov     [rsp+270h+var_250], 1; int
0x18013f8dd  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x18013f8e1  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x18013f8e5  mov     rdx, rsi; context
0x18013f8e8  mov     rcx, rbx; this
0x18013f8eb  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x18013f8f0  mov     ebx, eax
0x18013f8f2  xor     r12d, r12d
0x18013f8f5  test    eax, eax
0x18013f8f7  jz      short loc_18013F93F
0x18013f8f9  mov     eax, cs:dword_18039EB68
0x18013f8ff  cmp     eax, 2
0x18013f902  jbe     loc_18013FA6D
0x18013f908  mov     dword ptr [rbp+170h+var_1D8], ebx
0x18013f90b  mov     dword ptr [rbp+170h+var_1C8], 643h
0x18013f912  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013f919  mov     [rbp+170h+var_1F0], rax
0x18013f91d  lea     rax, [rbp+170h+var_1D8]
0x18013f921  mov     [rsp+270h+var_240], rax
0x18013f926  lea     rax, [rbp+170h+var_1C8]
0x18013f92a  mov     [rsp+270h+var_248], rax
0x18013f92f  lea     rax, [rbp+170h+var_1F0]
0x18013f933  lea     rdx, byte_180353AEF
0x18013f93a  jmp     loc_18013FA63
0x18013f93f  lea     r8, [rbp+170h+instance]; instance
0x18013f946  lea     rdx, SPACES_VirtualDisk_RemovePhysicalDisk_rtti; methodDecl
0x18013f94d  mov     rcx, rsi; context
0x18013f950  call    MI_Context_ConstructParameters
0x18013f955  mov     ebx, eax
0x18013f957  test    eax, eax
0x18013f959  jz      short loc_18013F9A1
0x18013f95b  mov     eax, cs:dword_18039EB68
0x18013f961  cmp     eax, 2
0x18013f964  jbe     loc_18013FA6D
0x18013f96a  mov     dword ptr [rbp+170h+var_1C0], ebx
0x18013f96d  mov     dword ptr [rbp+170h+var_1B8], 64Bh
0x18013f974  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013f97b  mov     [rbp+170h+var_1F0], rax
0x18013f97f  lea     rax, [rbp+170h+var_1C0]
0x18013f983  mov     [rsp+270h+var_240], rax
0x18013f988  lea     rax, [rbp+170h+var_1B8]
0x18013f98c  mov     [rsp+270h+var_248], rax
0x18013f991  lea     rax, [rbp+170h+var_1F0]
0x18013f995  lea     rdx, unk_180351C98
0x18013f99c  jmp     loc_18013FA63
0x18013f9a1  mov     rcx, [rbp+170h+var_1E0]
0x18013f9a5  mov     rax, [rcx]
0x18013f9a8  lea     rdx, [rbp+170h+instance]
0x18013f9af  mov     qword ptr [rsp+270h+var_250], rdx
0x18013f9b4  mov     r9, r15
0x18013f9b7  mov     r8, rsi
0x18013f9ba  mov     edx, 10000Ch
0x18013f9bf  mov     rax, [rax+30h]
0x18013f9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f9c8  mov     ebx, eax
0x18013f9ca  test    eax, eax
0x18013f9cc  jz      short loc_18013FA11
0x18013f9ce  mov     eax, cs:dword_18039EB68
0x18013f9d4  cmp     eax, 2
0x18013f9d7  jbe     loc_18013FA6D
0x18013f9dd  mov     [rbp+170h+var_1E8], ebx
0x18013f9e0  mov     dword ptr [rbp+170h+var_1D0], 656h
0x18013f9e7  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013f9ee  mov     [rbp+170h+var_1F0], rax
0x18013f9f2  lea     rax, [rbp+170h+var_1E8]
0x18013f9f6  mov     [rsp+270h+var_240], rax
0x18013f9fb  lea     rax, [rbp+170h+var_1D0]
0x18013f9ff  mov     [rsp+270h+var_248], rax
0x18013fa04  lea     rax, [rbp+170h+var_1F0]
0x18013fa08  lea     rdx, word_180352422
0x18013fa0f  jmp     short loc_18013FA63
0x18013fa11  lea     rdx, [rbp+170h+instance]
0x18013fa18  mov     rcx, rsi; self
0x18013fa1b  call    MI_Instance_Destruct
0x18013fa20  mov     ebx, eax
0x18013fa22  test    eax, eax
0x18013fa24  jz      short loc_18013FA6D
0x18013fa26  mov     eax, cs:dword_18039EB68
0x18013fa2c  cmp     eax, 2
0x18013fa2f  jbe     short loc_18013FA6D
0x18013fa31  mov     [rbp+170h+var_1E4], ebx
0x18013fa34  mov     dword ptr [rbp+170h+var_1F0], 65Eh
0x18013fa3b  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
0x18013fa42  mov     [rbp+170h+var_1D0], rax
0x18013fa46  lea     rax, [rbp+170h+var_1E4]
0x18013fa4a  mov     [rsp+270h+var_240], rax
0x18013fa4f  lea     rax, [rbp+170h+var_1F0]
0x18013fa53  mov     [rsp+270h+var_248], rax
0x18013fa58  lea     rax, [rbp+170h+var_1D0]
0x18013fa5c  lea     rdx, word_180352A7E
0x18013fa63  mov     qword ptr [rsp+270h+var_250], rax
0x18013fa68  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18013fa6d  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x18013fa74  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x18013fa79  jmp     short loc_18013FA7E
0x18013fa7b  xor     r12d, r12d
0x18013fa7e  lea     r8, [rdi+40h]; struct _MI_ConstStringField *
0x18013fa82  mov     [rsp+270h+var_248], r12; unsigned __int16 *
0x18013fa87  mov     [rsp+270h+var_250], ebx; enum _MI_Result
0x18013fa8b  lea     r9, [rbp+170h+var_B0]; struct _MI_ConstUint32Field *
0x18013fa92  mov     rdx, [rbp+170h+var_1B0]; unsigned __int16 *
0x18013fa96  mov     rcx, [rbp+170h+var_1A8]; unsigned __int16 *
0x18013fa9a  call    ?SmLogOnMethodFailure@@YAXPEBG0AEBU_MI_ConstStringField@@AEBU_MI_ConstUint32Field@@W4_MI_Result@@0@Z; SmLogOnMethodFailure(ushort const *,ushort const *,_MI_ConstStringField const &,_MI_ConstUint32Field const &,_MI_Result,ushort const *)
0x18013fa9f  test    r13d, r13d
0x18013faa2  jnz     loc_18013FC0E
0x18013faa8  lea     rcx, [rbp+170h+var_198]; this
0x18013faac  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x18013fab1  mov     eax, cs:dword_18039EB68
0x18013fab7  cmp     eax, 5
0x18013faba  jbe     loc_18013FC0E
0x18013fac0  mov     rdx, 400000000000h
0x18013faca  lea     rcx, dword_18039EB68
0x18013fad1  call    _tlgKeywordOn
0x18013fad6  test    al, al
0x18013fad8  jz      loc_18013FC0E
0x18013fade  cmp     [r15+58h], r12b
0x18013fae2  jz      short loc_18013FAEA
0x18013fae4  mov     eax, [r15+50h]
0x18013fae8  jmp     short loc_18013FAED
0x18013faea  mov     eax, r12d
0x18013faed  mov     dword ptr [rbp+170h+var_1F0], eax
0x18013faf0  cmp     [rbp+170h+var_88], r12b
0x18013faf7  jz      short loc_18013FB34
0x18013faf9  mov     rax, [rbp+170h+var_90]
0x18013fb00  movups  xmm0, xmmword ptr [rax]
0x18013fb03  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x18013fb07  movups  xmm1, xmmword ptr [rax+10h]
0x18013fb0b  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x18013fb0f  movups  xmm0, xmmword ptr [rax+20h]
0x18013fb13  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x18013fb17  movups  xmm1, xmmword ptr [rax+30h]
0x18013fb1b  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x18013fb1f  xor     r8d, r8d; unsigned __int16 *
0x18013fb22  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x18013fb26  lea     rcx, name; "ObjectId"
0x18013fb2d  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18013fb32  jmp     short loc_18013FB37
0x18013fb34  mov     rax, r12
0x18013fb37  mov     [rbp+170h+var_1A8], rax
0x18013fb3b  mov     [rbp+170h+var_1B0], r12
0x18013fb3f  mov     [rbp+170h+var_1B8], r12
0x18013fb43  mov     rax, [rbp+170h+var_190]
0x18013fb47  sub     rax, [rbp+170h+var_198]
0x18013fb4b  imul    rax, 3E8h
0x18013fb52  xor     edx, edx
0x18013fb54  div     [rbp+170h+var_188]
0x18013fb58  mov     [rbp+170h+var_1C0], rax
0x18013fb5c  mov     [rbp+170h+var_1E4], ebx
0x18013fb5f  mov     al, [rbp+170h+var_B0.exists]
0x18013fb65  neg     al
0x18013fb67  sbb     ecx, ecx
0x18013fb69  and     ecx, [rbp+170h+var_B0.value]
0x18013fb6f  mov     dword ptr [rbp+170h+var_1D0], ecx
0x18013fb72  mov     [rbp+170h+var_1E8], r14d
0x18013fb76  cmp     [rdi+48h], r12b
0x18013fb7a  jz      short loc_18013FB82
0x18013fb7c  mov     rax, [rdi+40h]
0x18013fb80  jmp     short loc_18013FB85
0x18013fb82  mov     rax, r12
0x18013fb85  mov     [rbp+170h+var_1C8], rax
0x18013fb89  lea     rax, aRemovephysical; "RemovePhysicalDisk"
0x18013fb90  mov     [rbp+170h+var_1D8], rax
0x18013fb94  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x18013fb9b  mov     [rbp+170h+var_1A0], rax
0x18013fb9f  lea     rax, [rbp+170h+var_1F0]
0x18013fba3  mov     [rsp+270h+var_200], rax
0x18013fba8  lea     rax, [rbp+170h+var_1A8]
0x18013fbac  mov     [rsp+270h+var_208], rax
0x18013fbb1  lea     rax, [rbp+170h+var_1B0]
0x18013fbb5  mov     [rsp+270h+var_210], rax
0x18013fbba  lea     rax, [rbp+170h+var_1B8]
0x18013fbbe  mov     [rsp+270h+var_218], rax
0x18013fbc3  lea     rax, [rbp+170h+var_1C0]
0x18013fbc7  mov     [rsp+270h+var_220], rax
0x18013fbcc  lea     rax, [rbp+170h+var_1E4]
0x18013fbd0  mov     [rsp+270h+var_228], rax
0x18013fbd5  lea     rax, [rbp+170h+var_1D0]
0x18013fbd9  mov     [rsp+270h+var_230], rax
0x18013fbde  lea     rax, [rbp+170h+var_1E8]
0x18013fbe2  mov     [rsp+270h+var_238], rax
0x18013fbe7  lea     rax, [rbp+170h+var_1C8]
0x18013fbeb  mov     [rsp+270h+var_240], rax
0x18013fbf0  lea     rax, [rbp+170h+var_1D8]
0x18013fbf4  mov     [rsp+270h+var_248], rax
0x18013fbf9  lea     rax, [rbp+170h+var_1A0]
0x18013fbfd  mov     qword ptr [rsp+270h+var_250], rax
0x18013fc02  lea     rdx, unk_180351E78
0x18013fc09  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U?$_tlgWrapperByVal@$07@@U1@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@55AEBU?$_tlgWrapperByVal@$07@@3445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18013fc0e  lea     rcx, [rbp+170h+instance]; self
0x18013fc15  call    MI_Instance_Destruct
0x18013fc1a  mov     eax, cs:dword_18039EB68
0x18013fc20  cmp     eax, 5
0x18013fc23  jbe     short loc_18013FC55
0x18013fc25  mov     dword ptr [rbp+170h+var_1F0], 680h
0x18013fc2c  lea     rax, aSpacesVirtuald_4; "SPACES_VirtualDisk_Invoke_RemovePhysica"...
  ... truncated ...
```
