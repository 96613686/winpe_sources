# SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain

- ea: `0x180140310`
- end: `0x1801408ee`
- name: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- size: `1502`
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
- `0x180021dcc`
- `0x1800226ac`
- `0x180023e18`
- `0x180025e78`
- `0x18013bd9c`
- `0x18013c4e8`
- `0x18013c50c`
- `0x180140310`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014037e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801403e9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801408b7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18014037e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801403e9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1801408b7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801403a7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801403a7`

## string_xrefs

- `0x1801403fb`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x180140510`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x18014056f`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x1801405d1`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x180140644`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x180140698`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x180140866`: `SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain`
- `0x1801407c3`: `RemoveStorageFaultDomain`

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
  int v11; // r8d
  int v12; // r9d
  enum _MI_Result v13; // r15d
  int IsRemoteRequest; // r12d
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
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // r8d
  int v33; // r9d
  int v34; // eax
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
    LODWORD(v45) = 1924;
    v41 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain",
      (unsigned int)byte_180351CD1,
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
        LODWORD(v47) = 1956;
        v41 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_1803519D4,
          v18,
          v19,
          (__int64)&v41,
          (__int64)&v47,
          (__int64)&v45);
      }
    }
    else if ( (unsigned int)CSpProvider::GetSubsystemVersion(*a1, a2, *(_QWORD *)(a6 + 64)) >= 3 )
    {
      v15 = MI_Context_ConstructParameters(a2, &SPACES_VirtualDisk_RemoveStorageFaultDomain_rtti, &instance);
      if ( v15 )
      {
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          LODWORD(v50) = v15;
          LODWORD(v51) = 1974;
          v41 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)byte_180352DC1,
            v24,
            v25,
            (__int64)&v41,
            (__int64)&v51,
            (__int64)&v50);
        }
      }
      else
      {
        v15 = (*(unsigned int (__fastcall **)(struct ISpWmiObject *, __int64, MI_Context *, __int64, MI_Instance *))(*(_QWORD *)v44 + 48LL))(
                v44,
                1048594,
                a2,
                a7,
                &instance);
        if ( v15 )
        {
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            v42 = v15;
            LODWORD(v46) = 1985;
            v41 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v26,
              (unsigned int)byte_18035320B,
              v27,
              v28,
              (__int64)&v41,
              (__int64)&v46,
              (__int64)&v42);
          }
        }
        else
        {
          v15 = MI_Instance_Destruct((MI_Instance *)a2);
          if ( v15 && (unsigned int)dword_18039EB68 > 2 )
          {
            v43 = v15;
            LODWORD(v41) = 1993;
            v46 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v29,
              (unsigned int)&word_180352FE6,
              v30,
              v31,
              (__int64)&v46,
              (__int64)&v41,
              (__int64)&v43);
          }
        }
      }
    }
    else
    {
      v15 = MI_RESULT_NOT_SUPPORTED;
      if ( (unsigned int)dword_18039EB68 > 2 )
      {
        LODWORD(v48) = 7;
        LODWORD(v49) = 1966;
        v41 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v20,
          (unsigned int)&unk_1803516E8,
          v21,
          v22,
          (__int64)&v41,
          (__int64)&v49,
          (__int64)&v48);
      }
    }
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
          v34 = *(_DWORD *)(a7 + 80);
        else
          v34 = 0;
        LODWORD(v41) = v34;
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
        v45 = "RemoveStorageFaultDomain";
        v52 = "VirtualDisk";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v60 != 0 ? v59 : 0,
          (unsigned int)&dword_180352C54,
          v32,
          v33,
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
    LODWORD(v41) = 2021;
    v52 = "SPACES_VirtualDisk_Invoke_RemoveStorageFaultDomain";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)word_1803537DA,
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
0x180140310  mov     [rsp-8+arg_10], rbx
0x180140315  push    rbp
0x180140316  push    rsi
0x180140317  push    rdi
0x180140318  push    r12
0x18014031a  push    r13
0x18014031c  push    r14
0x18014031e  push    r15
0x180140320  lea     rbp, [rsp-140h]
0x180140328  sub     rsp, 240h
0x18014032f  mov     rax, cs:__security_cookie
0x180140336  xor     rax, rsp
0x180140339  mov     [rbp+170h+var_40], rax
0x180140340  mov     rsi, rdx
0x180140343  mov     r14, rcx
0x180140346  mov     rdi, [rbp+170h+arg_28]
0x18014034d  mov     r13, [rbp+170h+arg_30]
0x180140354  xorps   xmm0, xmm0
0x180140357  xor     eax, eax
0x180140359  movups  xmmword ptr [rbp+170h+value], xmm0
0x18014035d  movups  xmmword ptr [rbp+170h+value+10h], xmm0
0x180140361  mov     qword ptr [rbp+170h+value+20h], rax
0x180140365  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014036c  movdqu  xmmword ptr [rbp+170h+ActivityId.Data1], xmm0
0x180140374  lea     rdx, [rbp+170h+ActivityId]; ActivityId
0x18014037b  lea     ecx, [rax+1]; ControlCode
0x18014037e  call    cs:__imp_EventActivityIdControl
0x180140385  nop     dword ptr [rax+rax+00h]
0x18014038a  lea     r9, [rbp+170h+value]; value
0x18014038e  mov     rcx, rsi; context
0x180140391  call    MI_Context_GetCustomOption_1
0x180140396  xor     ebx, ebx
0x180140398  test    eax, eax
0x18014039a  jnz     short loc_1801403B3
0x18014039c  lea     rdx, [rbp+170h+ActivityId]; pclsid
0x1801403a3  mov     rcx, qword ptr [rbp+170h+value]; lpsz
0x1801403a7  call    cs:__imp_CLSIDFromString
0x1801403ae  nop     dword ptr [rax+rax+00h]
0x1801403b3  mov     rcx, qword ptr [rbp+170h+ActivityId.Data1]
0x1801403ba  mov     [rbp+170h+var_60], rcx
0x1801403c1  mov     rax, qword ptr [rbp+170h+ActivityId.Data4]
0x1801403c8  mov     [rbp+170h+var_58], rax
0x1801403cf  mov     qword ptr [rbp+170h+var_50.Data1], rcx
0x1801403d6  mov     qword ptr [rbp+170h+var_50.Data4], rax
0x1801403dd  lea     rdx, [rbp+170h+var_50]; ActivityId
0x1801403e4  mov     ecx, 4; ControlCode
0x1801403e9  call    cs:__imp_EventActivityIdControl
0x1801403f0  nop     dword ptr [rax+rax+00h]
0x1801403f5  mov     eax, cs:dword_18039EB68
0x1801403fb  lea     rcx, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x180140402  cmp     eax, 5
0x180140405  jbe     short loc_180140430
0x180140407  mov     dword ptr [rbp+170h+var_1D8], 784h
0x18014040e  mov     [rbp+170h+var_1F0], rcx
0x180140412  lea     rax, [rbp+170h+var_1D8]
0x180140416  mov     [rsp+270h+var_248], rax
0x18014041b  lea     rax, [rbp+170h+var_1F0]
0x18014041f  mov     qword ptr [rsp+270h+var_250], rax
0x180140424  lea     rdx, byte_180351CD1
0x18014042b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180140430  mov     [rbp+170h+instance.ft], rbx
0x180140437  xor     edx, edx; Val
0x180140439  lea     r8d, [rdx+78h]; Size
0x18014043d  lea     rcx, [rbp+170h+instance.classDecl]; void *
0x180140444  call    memset_0
0x180140449  xorps   xmm0, xmm0
0x18014044c  xor     eax, eax
0x18014044e  movups  [rbp+170h+var_178], xmm0
0x180140452  mov     [rbp+170h+var_168], rax
0x180140456  mov     [rbp+170h+var_1E0], rbx
0x18014045a  lea     rcx, [rbp+170h+var_1E0]
0x18014045e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180140463  mov     [rbp+170h+var_1E0], rbx
0x180140467  mov     r15d, ebx
0x18014046a  lea     rcx, [rbp+170h+var_198]; this
0x18014046e  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180140473  mov     rcx, rsi; context
0x180140476  call    WspIsRemoteRequest
0x18014047b  mov     r12d, eax
0x18014047e  test    eax, eax
0x180140480  jnz     short loc_1801404A5
0x180140482  lea     rcx, [rbp+170h+var_198]; this
0x180140486  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18014048b  cmp     [rdi+48h], bl
0x18014048e  jz      short loc_1801404A2
0x180140490  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180140494  call    WspIsRemoteInstance
0x180140499  test    al, al
0x18014049b  lea     r15d, [r12+1]
0x1801404a0  jnz     short loc_1801404A5
0x1801404a2  mov     r15d, ebx
0x1801404a5  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x1801404ac  call    ?AddRef@MISpaceHandle@@QEAA?AW4_MI_Result@@XZ; MISpaceHandle::AddRef(void)
0x1801404b1  mov     ebx, eax
0x1801404b3  test    eax, eax
0x1801404b5  jnz     loc_1801406D6
0x1801404bb  mov     dword ptr [rbp+170h+var_178], 10h
0x1801404c2  mov     rax, [rdi+40h]
0x1801404c6  mov     qword ptr [rbp+170h+var_178+8], rax
0x1801404ca  mov     rbx, [r14]
0x1801404cd  lea     rcx, [rbp+170h+var_1E0]
0x1801404d1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801404d6  mov     [rsp+270h+var_250], 1; int
0x1801404de  lea     r9, [rbp+170h+var_1E0]; struct ISpWmiObject **
0x1801404e2  lea     r8, [rbp+170h+var_178]; struct _SP_OBJECT_ID *
0x1801404e6  mov     rdx, rsi; context
0x1801404e9  mov     rcx, rbx; this
0x1801404ec  call    ?GetInstance@CSpProvider@@QEAA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_SP_OBJECT_ID@@PEAPEAVISpWmiObject@@H@Z; CSpProvider::GetInstance(_MI_Context *,_SP_OBJECT_ID *,ISpWmiObject * *,int)
0x1801404f1  mov     ebx, eax
0x1801404f3  test    eax, eax
0x1801404f5  jz      short loc_18014053D
0x1801404f7  mov     eax, cs:dword_18039EB68
0x1801404fd  cmp     eax, 2
0x180140500  jbe     loc_1801406CA
0x180140506  mov     dword ptr [rbp+170h+var_1D8], ebx
0x180140509  mov     dword ptr [rbp+170h+var_1C8], 7A4h
0x180140510  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x180140517  mov     [rbp+170h+var_1F0], rax
0x18014051b  lea     rax, [rbp+170h+var_1D8]
0x18014051f  mov     [rsp+270h+var_240], rax
0x180140524  lea     rax, [rbp+170h+var_1C8]
0x180140528  mov     [rsp+270h+var_248], rax
0x18014052d  lea     rax, [rbp+170h+var_1F0]
0x180140531  lea     rdx, dword_1803519D4
0x180140538  jmp     loc_1801406C0
0x18014053d  mov     r8, [rdi+40h]
0x180140541  mov     rdx, rsi
0x180140544  mov     rcx, [r14]
0x180140547  call    ?GetSubsystemVersion@CSpProvider@@QEAA?AW4WSP_SUBSYSTEM_VERSION@@PEAU_MI_Context@@PEBG@Z; CSpProvider::GetSubsystemVersion(_MI_Context *,ushort const *)
0x18014054c  cmp     eax, 3
0x18014054f  jnb     short loc_18014059C
0x180140551  mov     ebx, 7
0x180140556  mov     eax, cs:dword_18039EB68
0x18014055c  cmp     eax, 2
0x18014055f  jbe     loc_1801406CA
0x180140565  mov     dword ptr [rbp+170h+var_1C0], ebx
0x180140568  mov     dword ptr [rbp+170h+var_1B8], 7AEh
0x18014056f  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x180140576  mov     [rbp+170h+var_1F0], rax
0x18014057a  lea     rax, [rbp+170h+var_1C0]
0x18014057e  mov     [rsp+270h+var_240], rax
0x180140583  lea     rax, [rbp+170h+var_1B8]
0x180140587  mov     [rsp+270h+var_248], rax
0x18014058c  lea     rax, [rbp+170h+var_1F0]
0x180140590  lea     rdx, unk_1803516E8
0x180140597  jmp     loc_1801406C0
0x18014059c  lea     r8, [rbp+170h+instance]; instance
0x1801405a3  lea     rdx, SPACES_VirtualDisk_RemoveStorageFaultDomain_rtti; methodDecl
0x1801405aa  mov     rcx, rsi; context
0x1801405ad  call    MI_Context_ConstructParameters
0x1801405b2  mov     ebx, eax
0x1801405b4  test    eax, eax
0x1801405b6  jz      short loc_1801405FE
0x1801405b8  mov     eax, cs:dword_18039EB68
0x1801405be  cmp     eax, 2
0x1801405c1  jbe     loc_1801406CA
0x1801405c7  mov     dword ptr [rbp+170h+var_1B0], ebx
0x1801405ca  mov     dword ptr [rbp+170h+var_1A8], 7B6h
0x1801405d1  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x1801405d8  mov     [rbp+170h+var_1F0], rax
0x1801405dc  lea     rax, [rbp+170h+var_1B0]
0x1801405e0  mov     [rsp+270h+var_240], rax
0x1801405e5  lea     rax, [rbp+170h+var_1A8]
0x1801405e9  mov     [rsp+270h+var_248], rax
0x1801405ee  lea     rax, [rbp+170h+var_1F0]
0x1801405f2  lea     rdx, byte_180352DC1
0x1801405f9  jmp     loc_1801406C0
0x1801405fe  mov     rcx, [rbp+170h+var_1E0]
0x180140602  mov     rax, [rcx]
0x180140605  lea     rdx, [rbp+170h+instance]
0x18014060c  mov     qword ptr [rsp+270h+var_250], rdx
0x180140611  mov     r9, r13
0x180140614  mov     r8, rsi
0x180140617  mov     edx, 100012h
0x18014061c  mov     rax, [rax+30h]
0x180140620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180140625  mov     ebx, eax
0x180140627  test    eax, eax
0x180140629  jz      short loc_18014066E
0x18014062b  mov     eax, cs:dword_18039EB68
0x180140631  cmp     eax, 2
0x180140634  jbe     loc_1801406CA
0x18014063a  mov     [rbp+170h+var_1E8], ebx
0x18014063d  mov     dword ptr [rbp+170h+var_1D0], 7C1h
0x180140644  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18014064b  mov     [rbp+170h+var_1F0], rax
0x18014064f  lea     rax, [rbp+170h+var_1E8]
0x180140653  mov     [rsp+270h+var_240], rax
0x180140658  lea     rax, [rbp+170h+var_1D0]
0x18014065c  mov     [rsp+270h+var_248], rax
0x180140661  lea     rax, [rbp+170h+var_1F0]
0x180140665  lea     rdx, byte_18035320B
0x18014066c  jmp     short loc_1801406C0
0x18014066e  lea     rdx, [rbp+170h+instance]
0x180140675  mov     rcx, rsi; self
0x180140678  call    MI_Instance_Destruct
0x18014067d  mov     ebx, eax
0x18014067f  test    eax, eax
0x180140681  jz      short loc_1801406CA
0x180140683  mov     eax, cs:dword_18039EB68
0x180140689  cmp     eax, 2
0x18014068c  jbe     short loc_1801406CA
0x18014068e  mov     [rbp+170h+var_1E4], ebx
0x180140691  mov     dword ptr [rbp+170h+var_1F0], 7C9h
0x180140698  lea     rax, aSpacesVirtuald_29; "SPACES_VirtualDisk_Invoke_RemoveStorage"...
0x18014069f  mov     [rbp+170h+var_1D0], rax
0x1801406a3  lea     rax, [rbp+170h+var_1E4]
0x1801406a7  mov     [rsp+270h+var_240], rax
0x1801406ac  lea     rax, [rbp+170h+var_1F0]
0x1801406b0  mov     [rsp+270h+var_248], rax
0x1801406b5  lea     rax, [rbp+170h+var_1D0]
0x1801406b9  lea     rdx, word_180352FE6
0x1801406c0  mov     qword ptr [rsp+270h+var_250], rax
0x1801406c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801406ca  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; this
0x1801406d1  call    ?Release@MISpaceHandle@@QEAAXXZ; MISpaceHandle::Release(void)
0x1801406d6  xor     r14d, r14d
0x1801406d9  test    r12d, r12d
0x1801406dc  jnz     loc_180140848
0x1801406e2  lea     rcx, [rbp+170h+var_198]; this
0x1801406e6  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801406eb  mov     eax, cs:dword_18039EB68
0x1801406f1  cmp     eax, 5
0x1801406f4  jbe     loc_180140848
0x1801406fa  mov     rdx, 400000000000h
0x180140704  lea     rcx, dword_18039EB68
0x18014070b  call    _tlgKeywordOn
0x180140710  test    al, al
0x180140712  jz      loc_180140848
0x180140718  cmp     [r13+58h], r14b
0x18014071c  jz      short loc_180140724
0x18014071e  mov     eax, [r13+50h]
0x180140722  jmp     short loc_180140727
0x180140724  mov     eax, r14d
0x180140727  mov     dword ptr [rbp+170h+var_1F0], eax
0x18014072a  cmp     [rbp+170h+var_88], r14b
0x180140731  jz      short loc_18014076E
0x180140733  mov     rax, [rbp+170h+var_90]
0x18014073a  movups  xmm0, xmmword ptr [rax]
0x18014073d  movaps  xmmword ptr [rbp+170h+var_160.ft], xmm0
0x180140741  movups  xmm1, xmmword ptr [rax+10h]
0x180140745  movaps  xmmword ptr [rbp+170h+var_160.serverName], xmm1
0x180140749  movups  xmm0, xmmword ptr [rax+20h]
0x18014074d  movaps  xmmword ptr [rbp+170h+var_160.reserved], xmm0
0x180140751  movups  xmm1, xmmword ptr [rax+30h]
0x180140755  movaps  xmmword ptr [rbp+170h+var_160.reserved+10h], xmm1
0x180140759  xor     r8d, r8d; unsigned __int16 *
0x18014075c  lea     rdx, [rbp+170h+var_160]; struct _MI_Instance
0x180140760  lea     rcx, name; "ObjectId"
0x180140767  call    ?SmMIGetString@@YAPEBGPEBGU_MI_Instance@@0@Z; SmMIGetString(ushort const *,_MI_Instance,ushort const *)
0x18014076c  jmp     short loc_180140771
0x18014076e  mov     rax, r14
0x180140771  mov     [rbp+170h+var_1A8], rax
0x180140775  mov     [rbp+170h+var_1B0], r14
0x180140779  mov     [rbp+170h+var_1B8], r14
0x18014077d  mov     rax, [rbp+170h+var_190]
0x180140781  sub     rax, [rbp+170h+var_198]
0x180140785  imul    rax, 3E8h
0x18014078c  xor     edx, edx
0x18014078e  div     [rbp+170h+var_188]
0x180140792  mov     [rbp+170h+var_1C0], rax
0x180140796  mov     [rbp+170h+var_1E4], ebx
0x180140799  mov     al, [rbp+170h+var_AC]
0x18014079f  neg     al
0x1801407a1  sbb     ecx, ecx
0x1801407a3  and     ecx, [rbp+170h+var_B0]
0x1801407a9  mov     dword ptr [rbp+170h+var_1D0], ecx
0x1801407ac  mov     [rbp+170h+var_1E8], r15d
0x1801407b0  cmp     [rdi+48h], r14b
0x1801407b4  jz      short loc_1801407BC
0x1801407b6  mov     rax, [rdi+40h]
0x1801407ba  jmp     short loc_1801407BF
0x1801407bc  mov     rax, r14
0x1801407bf  mov     [rbp+170h+var_1C8], rax
0x1801407c3  lea     rax, aRemovestoragef_0; "RemoveStorageFaultDomain"
0x1801407ca  mov     [rbp+170h+var_1D8], rax
0x1801407ce  lea     rax, aVirtualdisk_0; "VirtualDisk"
0x1801407d5  mov     [rbp+170h+var_1A0], rax
0x1801407d9  lea     rax, [rbp+170h+var_1F0]
0x1801407dd  mov     [rsp+270h+var_200], rax
0x1801407e2  lea     rax, [rbp+170h+var_1A8]
0x1801407e6  mov     [rsp+270h+var_208], rax
0x1801407eb  lea     rax, [rbp+170h+var_1B0]
0x1801407ef  mov     [rsp+270h+var_210], rax
0x1801407f4  lea     rax, [rbp+170h+var_1B8]
0x1801407f8  mov     [rsp+270h+var_218], rax
0x1801407fd  lea     rax, [rbp+170h+var_1C0]
0x180140801  mov     [rsp+270h+var_220], rax
0x180140806  lea     rax, [rbp+170h+var_1E4]
0x18014080a  mov     [rsp+270h+var_228], rax
0x18014080f  lea     rax, [rbp+170h+var_1D0]
0x180140813  mov     [rsp+270h+var_230], rax
0x180140818  lea     rax, [rbp+170h+var_1E8]
0x18014081c  mov     [rsp+270h+var_238], rax
0x180140821  lea     rax, [rbp+170h+var_1C8]
0x180140825  mov     [rsp+270h+var_240], rax
0x18014082a  lea     rax, [rbp+170h+var_1D8]
0x18014082e  mov     [rsp+270h+var_248], rax
0x180140833  lea     rax, [rbp+170h+var_1A0]
0x180140837  mov     qword ptr [rsp+270h+var_250], rax
  ... truncated ...
```
