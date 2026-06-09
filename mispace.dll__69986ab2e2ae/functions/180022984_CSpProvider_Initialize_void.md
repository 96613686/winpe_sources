# CSpProvider::Initialize(void)

- ea: `0x180022984`
- end: `0x180022e57`
- name: `?Initialize@CSpProvider@@QEAA?AW4_MI_Result@@XZ`
- size: `1235`
- prototype: `enum _MI_Result __fastcall(CSpProvider *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c220`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x1800063ac`
- `0x18000b840`
- `0x18000ba50`
- `0x18000c644`
- `0x18000cca4`
- `0x18000ccd4`
- `0x180013b4c`
- `0x180019c38`
- `0x18001fa44`
- `0x180021c14`
- `0x180022984`
- `0x180027588`
- `0x180027b6c`
- `0x180027c88`
- `0x180027fcc`
- `0x180028778`
- `0x180028848`
- `0x18005fc50`
- `0x18007c964`
- `0x1801b2fb8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022b11`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022b11`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a1b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a1b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022d22`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022d35`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022d22`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180022d35`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x180022d41`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x180022d41`

## string_xrefs

- `0x180022b0a`: `mispace.dll`
- `0x180022a87`: `MISpaceHandle::Create`
- `0x180022b8c`: `CSpProvider::_LoadRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSpProvider::Initialize(RTL_SRWLOCK *this, __int64 a2, int a3, int a4)
{
  _DWORD *v5; // rax
  CSpProvider *v6; // rcx
  enum _MI_Result Registry; // ebx
  int v8; // r8d
  int v9; // r9d
  const char *v10; // rdi
  __int16 *v11; // rdx
  enum _MI_Result Libraries; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  CSpRuntimeCounters *v16; // rcx
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // r9d
  const char *v21; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v22[5]; // [rsp+48h] [rbp-28h] BYREF
  _DWORD *v23; // [rsp+A8h] [rbp+38h] BYREF
  const char *v24; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+B8h] [rbp+48h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v23) = 63;
    v24 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&dword_1802F8D6C,
      a3,
      a4,
      (__int64)&v24,
      (__int64)&v23);
  }
  v25 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v25);
  v25 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v22);
  CSmTimer::Start((CSmTimer *)v22);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&CSpCluster::g_ClusterInstance);
  CSpCluster::g_ClusterInstance = 0;
  InitializeCriticalSection(&CSpCluster::g_InstanceCS);
  CSpCluster::g_IsClusterNode = SmIsClusteredNode(0, 0);
  v5 = operator new(0x50u);
  v23 = v5;
  v5[10] = 0;
  v5[11] = 0;
  *((_QWORD *)v5 + 6) = MISpaceHandle::ShutdownCallback;
  *((_QWORD *)v5 + 7) = 0;
  *((_QWORD *)v5 + 8) = 0;
  *((_QWORD *)v5 + 9) = 0;
  MISpaceHandle::g_MISpaceHandle = (LPCRITICAL_SECTION)v5;
  Registry = (unsigned int)MISpaceHandle::Initialize((MISpaceHandle *)MISpaceHandle::ShutdownCallback);
  if ( Registry )
  {
    v10 = "MISpaceHandle::Create";
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_38;
    LODWORD(v24) = 80;
    v11 = (__int16 *)&unk_1802FA538;
LABEL_36:
    LODWORD(v23) = Registry;
LABEL_37:
    v21 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v6,
      (_DWORD)v11,
      v8,
      v9,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v23);
    goto LABEL_38;
  }
  Libraries = CSpProvider::_LoadLibraries(v6);
  Registry = Libraries;
  if ( Libraries )
  {
    v10 = "CSpProvider::_LoadLibraries";
    LODWORD(v6) = dword_18039EB68;
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_38;
    LODWORD(v23) = Libraries;
    LODWORD(v24) = 90;
    v11 = (__int16 *)&unk_1802F88A8;
    goto LABEL_37;
  }
  g_SpacesModule = LoadLibraryExW(L"mispace.dll", 0, 0x802u);
  if ( g_SpacesModule )
  {
    Registry = CSpProvider::_LoadRegistry((CSpProvider *)this);
    if ( Registry )
    {
      v10 = "CSpProvider::_LoadRegistry";
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_38;
      LODWORD(v24) = 110;
      v11 = (__int16 *)&dword_1802F871C;
    }
    else
    {
      *(_OWORD *)&this[20].Ptr = 0;
      *(_OWORD *)&this[22].Ptr = 0;
      *(_OWORD *)&this[24].Ptr = 0;
      *(_OWORD *)&this[26].Ptr = 0;
      Registry = CSpProvider::_LoadSubsystems((CSpProvider *)this);
      if ( Registry )
      {
        v10 = "CSpProvider::_LoadSubsystems";
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_38;
        LODWORD(v24) = 124;
        v11 = word_1802FB77A;
      }
      else
      {
        Registry = CSpProvider::_ConnectAllSubsystems((CSpProvider *)this);
        if ( Registry )
        {
          v10 = "CSpProvider::_ConnectAllSubsystems";
          if ( (unsigned int)dword_18039EB68 <= 2 )
            goto LABEL_38;
          LODWORD(v24) = 134;
          v11 = &word_1802F84DE;
        }
        else
        {
          CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v25);
          if ( (unsigned int)CRefMap<unsigned short *,CSpSubsystem *>::Find(
                               &this[2],
                               L"{00000000-0000-0000-0000-000000000000}",
                               &v25) )
          {
            v6 = *(CSpProvider **)(v25 + 8);
            if ( v6 && *((_DWORD *)v6 + 2) )
            {
              if ( (unsigned int)CSpJobMgr::Initialize() )
              {
                if ( (unsigned int)CSpRuntimeCounters::Initialize(v16) )
                {
                  LODWORD(v10) = 0;
                  InitializeSRWLock(this + 19);
                  InitializeSRWLock(this + 28);
                  I_RpcServerDisableExceptionFilter();
                  goto LABEL_38;
                }
                v10 = "CSpRuntimeCounters::Initialize";
                Registry = GleToMiResult();
                if ( (unsigned int)dword_18039EB68 <= 2 )
                  goto LABEL_38;
                LODWORD(v24) = 171;
                v11 = (__int16 *)&byte_1802FB5CF;
              }
              else
              {
                v10 = "CSpJobMgr::Initialize";
                Registry = GleToMiResult();
                if ( (unsigned int)dword_18039EB68 <= 2 )
                  goto LABEL_38;
                LODWORD(v24) = 163;
                v11 = (__int16 *)&unk_1802FB560;
              }
            }
            else
            {
              v10 = "CSpSubsystem::IsConnected";
              Registry = MI_RESULT_FAILED;
              if ( (unsigned int)dword_18039EB68 <= 2 )
                goto LABEL_38;
              LODWORD(v24) = 155;
              v11 = word_1802F98F2;
            }
          }
          else
          {
            v10 = "CRefMap<LPWSTR, CSpSubsystem*>::Find";
            Registry = MI_RESULT_NOT_FOUND;
            if ( (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_38;
            LODWORD(v24) = 147;
            v11 = (__int16 *)byte_1802FA265;
          }
        }
      }
    }
    goto LABEL_36;
  }
  v10 = "CSpProvider::_LoadResources";
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    LODWORD(v23) = 1;
    LODWORD(v24) = 100;
    v21 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_1802F98B9,
      v14,
      v15,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v23);
  }
  Registry = MI_RESULT_FAILED;
LABEL_38:
  CSmTimer::Stop((CSmTimer *)v22);
  if ( Registry )
  {
    CSpProvider::Cleanup((CSpProvider *)this);
    if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
      McTemplateU0ssq_EventWriteTransfer(
        v17,
        (unsigned int)ProviderInitializationFailed,
        (unsigned int)"CSpProvider::Initialize",
        (_DWORD)v10,
        Registry);
  }
  else if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
  {
    McTemplateU0sx_EventWriteTransfer(
      v17,
      ProviderInitializationSucceeded,
      "CSpProvider::Initialize",
      (unsigned __int64)(1000LL * (v22[1] - v22[0])) / v22[2]);
  }
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v23) = 198;
    v24 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)byte_1802FB495,
      v18,
      v19,
      (__int64)&v24,
      (__int64)&v23);
  }
  CSmTimer::~CSmTimer((CSmTimer *)v22);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v25);
  return (unsigned int)Registry;
}

```

## disassembly

```asm
0x180022984  push    rbp
0x180022986  push    rbx
0x180022987  push    rsi
0x180022988  push    rdi
0x180022989  push    r15
0x18002298b  mov     rbp, rsp
0x18002298e  sub     rsp, 70h
0x180022992  mov     rsi, rcx
0x180022995  mov     eax, cs:dword_18039EB68
0x18002299b  lea     r15, aCspproviderIni; "CSpProvider::Initialize"
0x1800229a2  cmp     eax, 5
0x1800229a5  jbe     short loc_1800229D0
0x1800229a7  mov     dword ptr [rbp+arg_8], 3Fh ; '?'
0x1800229ae  mov     [rbp+arg_10], r15
0x1800229b2  lea     rax, [rbp+arg_8]
0x1800229b6  mov     [rsp+70h+var_48], rax
0x1800229bb  lea     rax, [rbp+arg_10]
0x1800229bf  mov     [rsp+70h+var_50], rax
0x1800229c4  lea     rdx, dword_1802F8D6C
0x1800229cb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800229d0  mov     [rbp+arg_18], 0
0x1800229d8  lea     rcx, [rbp+arg_18]
0x1800229dc  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800229e1  mov     [rbp+arg_18], 0
0x1800229e9  lea     rcx, [rbp+var_28]; this
0x1800229ed  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1800229f2  nop
0x1800229f3  lea     rcx, [rbp+var_28]; this
0x1800229f7  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1800229fc  nop
0x1800229fd  lea     rcx, ?g_ClusterInstance@CSpCluster@@0V?$CSmRefPtr@VCSpCluster@@X@@A; CSmRefPtr<CSpCluster,void> CSpCluster::g_ClusterInstance
0x180022a04  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180022a09  mov     cs:?g_ClusterInstance@CSpCluster@@0V?$CSmRefPtr@VCSpCluster@@X@@A, 0; CSmRefPtr<CSpCluster,void> CSpCluster::g_ClusterInstance
0x180022a14  lea     rcx, ?g_InstanceCS@CSpCluster@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180022a1b  call    cs:__imp_InitializeCriticalSection
0x180022a22  nop     dword ptr [rax+rax+00h]
0x180022a27  xor     edx, edx; int *
0x180022a29  xor     ecx, ecx; unsigned __int16 *
0x180022a2b  call    ?SmIsClusteredNode@@YAHPEBGPEAH@Z; SmIsClusteredNode(ushort const *,int *)
0x180022a30  mov     cs:?g_IsClusterNode@CSpCluster@@0HA, eax; int CSpCluster::g_IsClusterNode
0x180022a36  mov     ecx, 50h ; 'P'; Size
0x180022a3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022a40  mov     [rbp+arg_8], rax
0x180022a44  mov     dword ptr [rax+28h], 0
0x180022a4b  mov     dword ptr [rax+2Ch], 0
0x180022a52  lea     rcx, ?ShutdownCallback@MISpaceHandle@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; this
0x180022a59  mov     [rax+30h], rcx
0x180022a5d  mov     qword ptr [rax+38h], 0
0x180022a65  mov     qword ptr [rax+40h], 0
0x180022a6d  mov     qword ptr [rax+48h], 0
0x180022a75  mov     cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA, rax; MISpaceHandle * MISpaceHandle::g_MISpaceHandle
0x180022a7c  call    ?Initialize@MISpaceHandle@@AEAA?AW4_MI_Result@@XZ; MISpaceHandle::Initialize(void)
0x180022a81  mov     ebx, eax
0x180022a83  test    eax, eax
0x180022a85  jz      short loc_180022AB0
0x180022a87  lea     rdi, aMispacehandleC; "MISpaceHandle::Create"
0x180022a8e  mov     eax, cs:dword_18039EB68
0x180022a94  cmp     eax, 2
0x180022a97  jbe     loc_180022D9B
0x180022a9d  mov     dword ptr [rbp+arg_10], 50h ; 'P'
0x180022aa4  lea     rdx, unk_1802FA538
0x180022aab  jmp     loc_180022D74
0x180022ab0  call    ?_LoadLibraries@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_LoadLibraries(void)
0x180022ab5  mov     ebx, eax
0x180022ab7  test    eax, eax
0x180022ab9  jz      short loc_180022B02
0x180022abb  lea     rdi, aCspproviderLoa_2; "CSpProvider::_LoadLibraries"
0x180022ac2  mov     ecx, cs:dword_18039EB68
0x180022ac8  cmp     ecx, 2
0x180022acb  jbe     loc_180022D9B
0x180022ad1  mov     dword ptr [rbp+arg_8], eax
0x180022ad4  mov     dword ptr [rbp+arg_10], 5Ah ; 'Z'
0x180022adb  lea     rax, [rbp+arg_8]
0x180022adf  mov     [rsp+70h+var_40], rax
0x180022ae4  lea     rax, [rbp+arg_10]
0x180022ae8  mov     [rsp+70h+var_48], rax
0x180022aed  lea     rax, [rbp+var_30]
0x180022af1  mov     [rsp+70h+var_50], rax
0x180022af6  lea     rdx, unk_1802F88A8
0x180022afd  jmp     loc_180022D92
0x180022b02  xor     edx, edx; hFile
0x180022b04  mov     r8d, 802h; dwFlags
0x180022b0a  lea     rcx, aMispaceDll_0; "mispace.dll"
0x180022b11  call    cs:__imp_LoadLibraryExW
0x180022b18  nop     dword ptr [rax+rax+00h]
0x180022b1d  mov     cs:?g_SpacesModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_SpacesModule
0x180022b24  test    rax, rax
0x180022b27  jnz     short loc_180022B7E
0x180022b29  lea     rdi, aCspproviderLoa_1; "CSpProvider::_LoadResources"
0x180022b30  mov     eax, cs:dword_18039EB68
0x180022b36  cmp     eax, 2
0x180022b39  jbe     short loc_180022B74
0x180022b3b  mov     dword ptr [rbp+arg_8], 1
0x180022b42  mov     dword ptr [rbp+arg_10], 64h ; 'd'
0x180022b49  mov     [rbp+var_30], r15
0x180022b4d  lea     rax, [rbp+arg_8]
0x180022b51  mov     [rsp+70h+var_40], rax
0x180022b56  lea     rax, [rbp+arg_10]
0x180022b5a  mov     [rsp+70h+var_48], rax
0x180022b5f  lea     rax, [rbp+var_30]
0x180022b63  mov     [rsp+70h+var_50], rax
0x180022b68  lea     rdx, byte_1802F98B9
0x180022b6f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022b74  mov     ebx, 1
0x180022b79  jmp     loc_180022D9B
0x180022b7e  mov     rcx, rsi; this
0x180022b81  call    ?_LoadRegistry@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_LoadRegistry(void)
0x180022b86  mov     ebx, eax
0x180022b88  test    eax, eax
0x180022b8a  jz      short loc_180022BB5
0x180022b8c  lea     rdi, aCspproviderLoa_0; "CSpProvider::_LoadRegistry"
0x180022b93  mov     eax, cs:dword_18039EB68
0x180022b99  cmp     eax, 2
0x180022b9c  jbe     loc_180022D9B
0x180022ba2  mov     dword ptr [rbp+arg_10], 6Eh ; 'n'
0x180022ba9  lea     rdx, dword_1802F871C
0x180022bb0  jmp     loc_180022D74
0x180022bb5  xorps   xmm0, xmm0
0x180022bb8  movups  xmmword ptr [rsi+0A0h], xmm0
0x180022bbf  movups  xmmword ptr [rsi+0B0h], xmm0
0x180022bc6  movups  xmmword ptr [rsi+0C0h], xmm0
0x180022bcd  movups  xmmword ptr [rsi+0D0h], xmm0
0x180022bd4  mov     rcx, rsi; this
0x180022bd7  call    ?_LoadSubsystems@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_LoadSubsystems(void)
0x180022bdc  mov     ebx, eax
0x180022bde  test    eax, eax
0x180022be0  jz      short loc_180022C0B
0x180022be2  lea     rdi, aCspproviderLoa; "CSpProvider::_LoadSubsystems"
0x180022be9  mov     eax, cs:dword_18039EB68
0x180022bef  cmp     eax, 2
0x180022bf2  jbe     loc_180022D9B
0x180022bf8  mov     dword ptr [rbp+arg_10], 7Ch ; '|'
0x180022bff  lea     rdx, word_1802FB77A
0x180022c06  jmp     loc_180022D74
0x180022c0b  mov     rcx, rsi; this
0x180022c0e  call    ?_ConnectAllSubsystems@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_ConnectAllSubsystems(void)
0x180022c13  mov     ebx, eax
0x180022c15  test    eax, eax
0x180022c17  jz      short loc_180022C42
0x180022c19  lea     rdi, aCspproviderCon; "CSpProvider::_ConnectAllSubsystems"
0x180022c20  mov     eax, cs:dword_18039EB68
0x180022c26  cmp     eax, 2
0x180022c29  jbe     loc_180022D9B
0x180022c2f  mov     dword ptr [rbp+arg_10], 86h
0x180022c36  lea     rdx, word_1802F84DE
0x180022c3d  jmp     loc_180022D74
0x180022c42  lea     rcx, [rbp+arg_18]
0x180022c46  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180022c4b  lea     rcx, [rsi+10h]
0x180022c4f  lea     r8, [rbp+arg_18]
0x180022c53  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180022c5a  call    ?Find@?$CRefMap@PEAGPEAVCSpSubsystem@@@@QEAAHPEAGPEAPEAVCSpSubsystem@@@Z; CRefMap<ushort *,CSpSubsystem *>::Find(ushort *,CSpSubsystem * *)
0x180022c5f  test    eax, eax
0x180022c61  jnz     short loc_180022C8F
0x180022c63  lea     rdi, aCrefmapLpwstrC; "CRefMap<LPWSTR, CSpSubsystem*>::Find"
0x180022c6a  lea     ebx, [rax+6]
0x180022c6d  mov     eax, cs:dword_18039EB68
0x180022c73  cmp     eax, 2
0x180022c76  jbe     loc_180022D9B
0x180022c7c  mov     dword ptr [rbp+arg_10], 93h
0x180022c83  lea     rdx, byte_1802FA265
0x180022c8a  jmp     loc_180022D74
0x180022c8f  mov     rax, [rbp+arg_18]
0x180022c93  mov     rcx, [rax+8]
0x180022c97  test    rcx, rcx
0x180022c9a  jz      loc_180022D4F
0x180022ca0  cmp     dword ptr [rcx+8], 0
0x180022ca4  jz      loc_180022D4F
0x180022caa  call    ?Initialize@CSpJobMgr@@SAHXZ; CSpJobMgr::Initialize(void)
0x180022caf  test    eax, eax
0x180022cb1  jnz     short loc_180022CE3
0x180022cb3  lea     rdi, aCspjobmgrIniti; "CSpJobMgr::Initialize"
0x180022cba  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180022cbf  mov     ebx, eax
0x180022cc1  mov     eax, cs:dword_18039EB68
0x180022cc7  cmp     eax, 2
0x180022cca  jbe     loc_180022D9B
0x180022cd0  mov     dword ptr [rbp+arg_10], 0A3h
0x180022cd7  lea     rdx, unk_1802FB560
0x180022cde  jmp     loc_180022D74
0x180022ce3  call    ?Initialize@CSpRuntimeCounters@@QEAAHXZ; CSpRuntimeCounters::Initialize(void)
0x180022ce8  test    eax, eax
0x180022cea  jnz     short loc_180022D19
0x180022cec  lea     rdi, aCspruntimecoun_1; "CSpRuntimeCounters::Initialize"
0x180022cf3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180022cf8  mov     ebx, eax
0x180022cfa  mov     eax, cs:dword_18039EB68
0x180022d00  cmp     eax, 2
0x180022d03  jbe     loc_180022D9B
0x180022d09  mov     dword ptr [rbp+arg_10], 0ABh
0x180022d10  lea     rdx, byte_1802FB5CF
0x180022d17  jmp     short loc_180022D74
0x180022d19  xor     edi, edi
0x180022d1b  lea     rcx, [rsi+98h]; SRWLock
0x180022d22  call    cs:__imp_InitializeSRWLock
0x180022d29  nop     dword ptr [rax+rax+00h]
0x180022d2e  lea     rcx, [rsi+0E0h]; SRWLock
0x180022d35  call    cs:__imp_InitializeSRWLock
0x180022d3c  nop     dword ptr [rax+rax+00h]
0x180022d41  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x180022d48  nop     dword ptr [rax+rax+00h]
0x180022d4d  jmp     short loc_180022D9B
0x180022d4f  lea     rdi, aCspsubsystemIs; "CSpSubsystem::IsConnected"
0x180022d56  mov     ebx, 1
0x180022d5b  mov     eax, cs:dword_18039EB68
0x180022d61  cmp     eax, 2
0x180022d64  jbe     short loc_180022D9B
0x180022d66  mov     dword ptr [rbp+arg_10], 9Bh
0x180022d6d  lea     rdx, word_1802F98F2
0x180022d74  lea     rax, [rbp+arg_8]
0x180022d78  mov     [rsp+70h+var_40], rax
0x180022d7d  lea     rax, [rbp+arg_10]
0x180022d81  mov     [rsp+70h+var_48], rax
0x180022d86  lea     rax, [rbp+var_30]
0x180022d8a  mov     [rsp+70h+var_50], rax
0x180022d8f  mov     dword ptr [rbp+arg_8], ebx
0x180022d92  mov     [rbp+var_30], r15
0x180022d96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022d9b  lea     rcx, [rbp+var_28]; this
0x180022d9f  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180022da4  test    ebx, ebx
0x180022da6  jz      short loc_180022DD1
0x180022da8  mov     rcx, rsi; this
0x180022dab  call    ?Cleanup@CSpProvider@@QEAA?AW4_MI_Result@@XZ; CSpProvider::Cleanup(void)
0x180022db0  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x180022db7  jz      short loc_180022E01
0x180022db9  mov     dword ptr [rsp+70h+var_50], ebx
0x180022dbd  mov     r9, rdi
0x180022dc0  mov     r8, r15
0x180022dc3  lea     rdx, ProviderInitializationFailed
0x180022dca  call    McTemplateU0ssq_EventWriteTransfer
0x180022dcf  jmp     short loc_180022E01
0x180022dd1  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 4
0x180022dd8  jz      short loc_180022E01
0x180022dda  mov     rax, [rbp+var_20]
0x180022dde  sub     rax, [rbp+var_28]
0x180022de2  imul    rax, 3E8h
0x180022de9  xor     edx, edx
0x180022deb  div     [rbp+var_18]
0x180022def  mov     r9, rax
0x180022df2  mov     r8, r15
0x180022df5  lea     rdx, ProviderInitializationSucceeded
0x180022dfc  call    McTemplateU0sx_EventWriteTransfer
0x180022e01  mov     eax, cs:dword_18039EB68
0x180022e07  cmp     eax, 5
0x180022e0a  jbe     short loc_180022E36
0x180022e0c  mov     dword ptr [rbp+arg_8], 0C6h
0x180022e13  mov     [rbp+arg_10], r15
0x180022e17  lea     rax, [rbp+arg_8]
0x180022e1b  mov     [rsp+70h+var_48], rax
0x180022e20  lea     rax, [rbp+arg_10]
0x180022e24  mov     [rsp+70h+var_50], rax
0x180022e29  lea     rdx, byte_1802FB495
0x180022e30  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180022e35  nop
0x180022e36  lea     rcx, [rbp+var_28]; this
0x180022e3a  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x180022e3f  nop
0x180022e40  lea     rcx, [rbp+arg_18]
0x180022e44  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180022e49  mov     eax, ebx
0x180022e4b  add     rsp, 70h
0x180022e4f  pop     r15
0x180022e51  pop     rdi
0x180022e52  pop     rsi
0x180022e53  pop     rbx
0x180022e54  pop     rbp
0x180022e55  retn
```
