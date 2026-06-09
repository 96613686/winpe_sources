# CSpProvider::Initialize(void)

- ea: `0x180022158`
- end: `0x180022609`
- name: `?Initialize@CSpProvider@@QEAA?AW4_MI_Result@@XZ`
- size: `1201`
- prototype: `enum _MI_Result __fastcall(CSpProvider *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c300`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x1800062ec`
- `0x18000b964`
- `0x18000bb68`
- `0x18000c704`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180013898`
- `0x180019800`
- `0x18001f2d0`
- `0x180021414`
- `0x180022158`
- `0x180026b18`
- `0x1800270a0`
- `0x1800271bc`
- `0x180027500`
- `0x180027c94`
- `0x180027d64`
- `0x18005ddb0`
- `0x18007a46c`
- `0x1801ad3f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800222df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800222df`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800221ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800221ef`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800224e7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800224f4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800224e7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800224f4`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x1800224fa`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x1800224fa`

## string_xrefs

- `0x1800222d8`: `mispace.dll`
- `0x180022255`: `MISpaceHandle::Create`
- `0x180022354`: `CSpProvider::_LoadRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSpProvider::Initialize(RTL_SRWLOCK *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  enum _MI_Result Libraries; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  const char *v9; // rdi
  __int16 *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  CSpRuntimeCounters *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const char *v19; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v20[5]; // [rsp+48h] [rbp-28h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+A8h] [rbp+38h]
  const char *v22; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v23; // [rsp+B8h] [rbp+48h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v22 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)this,
      (__int64)&dword_1802F1DE4,
      a3,
      a4,
      &v22);
  }
  v23 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v23);
  v23 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v20);
  CSmTimer::Start((CSmTimer *)v20);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&CSpCluster::g_ClusterInstance);
  CSpCluster::g_ClusterInstance = 0;
  InitializeCriticalSection(&CSpCluster::g_InstanceCS);
  CSpCluster::g_IsClusterNode = SmIsClusteredNode(0, 0);
  v21 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u);
  LODWORD(v21[1].DebugInfo) = 0;
  HIDWORD(v21[1].DebugInfo) = 0;
  *(_QWORD *)&v21[1].LockCount = MISpaceHandle::ShutdownCallback;
  v21[1].OwningThread = 0;
  v21[1].LockSemaphore = 0;
  v21[1].SpinCount = 0;
  MISpaceHandle::g_MISpaceHandle = v21;
  Libraries = (unsigned int)MISpaceHandle::Initialize((MISpaceHandle *)MISpaceHandle::ShutdownCallback);
  if ( Libraries )
  {
    v9 = "MISpaceHandle::Create";
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_37;
    LODWORD(v22) = 80;
    v10 = (__int16 *)&unk_1802F35B0;
LABEL_36:
    v19 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)v10,
      v7,
      v8,
      &v19);
    goto LABEL_37;
  }
  Libraries = CSpProvider::_LoadLibraries((CSpProvider *)v5);
  if ( Libraries )
  {
    v9 = "CSpProvider::_LoadLibraries";
    v5 = (unsigned int)dword_180397B68;
    if ( (unsigned int)dword_180397B68 <= 2 )
      goto LABEL_37;
    LODWORD(v22) = 90;
    v10 = (__int16 *)&unk_1802F1920;
    goto LABEL_36;
  }
  g_SpacesModule = LoadLibraryExW(L"mispace.dll", 0, 0x802u);
  if ( g_SpacesModule )
  {
    Libraries = CSpProvider::_LoadRegistry((CSpProvider *)this);
    if ( Libraries )
    {
      v9 = "CSpProvider::_LoadRegistry";
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_37;
      LODWORD(v22) = 110;
      v10 = (__int16 *)&dword_1802F1794;
    }
    else
    {
      *(_OWORD *)&this[20].Ptr = 0;
      *(_OWORD *)&this[22].Ptr = 0;
      *(_OWORD *)&this[24].Ptr = 0;
      *(_OWORD *)&this[26].Ptr = 0;
      Libraries = CSpProvider::_LoadSubsystems((CSpProvider *)this);
      if ( Libraries )
      {
        v9 = "CSpProvider::_LoadSubsystems";
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_37;
        LODWORD(v22) = 124;
        v10 = word_1802F47F2;
      }
      else
      {
        Libraries = CSpProvider::_ConnectAllSubsystems((CSpProvider *)this);
        if ( Libraries )
        {
          v9 = "CSpProvider::_ConnectAllSubsystems";
          if ( (unsigned int)dword_180397B68 <= 2 )
            goto LABEL_37;
          LODWORD(v22) = 134;
          v10 = &word_1802F1556;
        }
        else
        {
          CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v23);
          if ( (unsigned int)CRefMap<unsigned short *,CSpSubsystem *>::Find(
                               &this[2],
                               L"{00000000-0000-0000-0000-000000000000}",
                               &v23) )
          {
            v5 = *(_QWORD *)(v23 + 8);
            if ( v5 && *(_DWORD *)(v5 + 8) )
            {
              if ( (unsigned int)CSpJobMgr::Initialize() )
              {
                if ( (unsigned int)CSpRuntimeCounters::Initialize(v14) )
                {
                  LODWORD(v9) = 0;
                  InitializeSRWLock(this + 19);
                  InitializeSRWLock(this + 28);
                  I_RpcServerDisableExceptionFilter();
                  goto LABEL_37;
                }
                v9 = "CSpRuntimeCounters::Initialize";
                Libraries = GleToMiResult();
                if ( (unsigned int)dword_180397B68 <= 2 )
                  goto LABEL_37;
                LODWORD(v22) = 171;
                v10 = (__int16 *)&byte_1802F4647;
              }
              else
              {
                v9 = "CSpJobMgr::Initialize";
                Libraries = GleToMiResult();
                if ( (unsigned int)dword_180397B68 <= 2 )
                  goto LABEL_37;
                LODWORD(v22) = 163;
                v10 = (__int16 *)&unk_1802F45D8;
              }
            }
            else
            {
              v9 = "CSpSubsystem::IsConnected";
              Libraries = MI_RESULT_FAILED;
              if ( (unsigned int)dword_180397B68 <= 2 )
                goto LABEL_37;
              LODWORD(v22) = 155;
              v10 = word_1802F296A;
            }
          }
          else
          {
            v9 = "CRefMap<LPWSTR, CSpSubsystem*>::Find";
            Libraries = MI_RESULT_NOT_FOUND;
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_37;
            LODWORD(v22) = 147;
            v10 = (__int16 *)byte_1802F32DD;
          }
        }
      }
    }
    goto LABEL_36;
  }
  v9 = "CSpProvider::_LoadResources";
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    LODWORD(v22) = 100;
    v19 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v11,
      (__int64)byte_1802F2931,
      v12,
      v13,
      &v19);
  }
  Libraries = MI_RESULT_FAILED;
LABEL_37:
  CSmTimer::Stop((CSmTimer *)v20);
  if ( Libraries )
  {
    CSpProvider::Cleanup((CSpProvider *)this);
    if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 1) != 0 )
      McTemplateU0ssq_EventWriteTransfer(
        v15,
        (unsigned int)ProviderInitializationFailed,
        (unsigned int)"CSpProvider::Initialize",
        (_DWORD)v9,
        Libraries);
  }
  else if ( (Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits & 4) != 0 )
  {
    McTemplateU0sx_EventWriteTransfer(
      v15,
      ProviderInitializationSucceeded,
      "CSpProvider::Initialize",
      (unsigned __int64)(1000LL * (v20[1] - v20[0])) / v20[2]);
  }
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v22 = "CSpProvider::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v15,
      (__int64)byte_1802F450D,
      v16,
      v17,
      &v22);
  }
  CSmTimer::~CSmTimer((CSmTimer *)v20);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v23);
  return (unsigned int)Libraries;
}

```

## disassembly

```asm
0x180022158  push    rbp
0x18002215a  push    rbx
0x18002215b  push    rsi
0x18002215c  push    rdi
0x18002215d  push    r15
0x18002215f  mov     rbp, rsp
0x180022162  sub     rsp, 70h
0x180022166  mov     rsi, rcx
0x180022169  mov     eax, cs:dword_180397B68
0x18002216f  lea     r15, aCspproviderIni; "CSpProvider::Initialize"
0x180022176  cmp     eax, 5
0x180022179  jbe     short loc_1800221A4
0x18002217b  mov     dword ptr [rbp+arg_8], 3Fh ; '?'
0x180022182  mov     [rbp+arg_10], r15
0x180022186  lea     rax, [rbp+arg_8]
0x18002218a  mov     [rsp+70h+var_48], rax
0x18002218f  lea     rax, [rbp+arg_10]
0x180022193  mov     [rsp+70h+var_50], rax
0x180022198  lea     rdx, dword_1802F1DE4
0x18002219f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800221a4  mov     [rbp+arg_18], 0
0x1800221ac  lea     rcx, [rbp+arg_18]
0x1800221b0  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800221b5  mov     [rbp+arg_18], 0
0x1800221bd  lea     rcx, [rbp+var_28]; this
0x1800221c1  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1800221c6  nop
0x1800221c7  lea     rcx, [rbp+var_28]; this
0x1800221cb  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1800221d0  nop
0x1800221d1  lea     rcx, ?g_ClusterInstance@CSpCluster@@0V?$CSmRefPtr@VCSpCluster@@X@@A; CSmRefPtr<CSpCluster,void> CSpCluster::g_ClusterInstance
0x1800221d8  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800221dd  mov     cs:?g_ClusterInstance@CSpCluster@@0V?$CSmRefPtr@VCSpCluster@@X@@A, 0; CSmRefPtr<CSpCluster,void> CSpCluster::g_ClusterInstance
0x1800221e8  lea     rcx, ?g_InstanceCS@CSpCluster@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800221ef  call    cs:__imp_InitializeCriticalSection
0x1800221f5  xor     edx, edx; int *
0x1800221f7  xor     ecx, ecx; unsigned __int16 *
0x1800221f9  call    ?SmIsClusteredNode@@YAHPEBGPEAH@Z; SmIsClusteredNode(ushort const *,int *)
0x1800221fe  mov     cs:?g_IsClusterNode@CSpCluster@@0HA, eax; int CSpCluster::g_IsClusterNode
0x180022204  mov     ecx, 50h ; 'P'; Size
0x180022209  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002220e  mov     [rbp+arg_8], rax
0x180022212  mov     dword ptr [rax+28h], 0
0x180022219  mov     dword ptr [rax+2Ch], 0
0x180022220  lea     rcx, ?ShutdownCallback@MISpaceHandle@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; this
0x180022227  mov     [rax+30h], rcx
0x18002222b  mov     qword ptr [rax+38h], 0
0x180022233  mov     qword ptr [rax+40h], 0
0x18002223b  mov     qword ptr [rax+48h], 0
0x180022243  mov     cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA, rax; MISpaceHandle * MISpaceHandle::g_MISpaceHandle
0x18002224a  call    ?Initialize@MISpaceHandle@@AEAA?AW4_MI_Result@@XZ; MISpaceHandle::Initialize(void)
0x18002224f  mov     ebx, eax
0x180022251  test    eax, eax
0x180022253  jz      short loc_18002227E
0x180022255  lea     rdi, aMispacehandleC; "MISpaceHandle::Create"
0x18002225c  mov     eax, cs:dword_180397B68
0x180022262  cmp     eax, 2
0x180022265  jbe     loc_18002254E
0x18002226b  mov     dword ptr [rbp+arg_10], 50h ; 'P'
0x180022272  lea     rdx, unk_1802F35B0
0x180022279  jmp     loc_180022527
0x18002227e  call    ?_LoadLibraries@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_LoadLibraries(void)
0x180022283  mov     ebx, eax
0x180022285  test    eax, eax
0x180022287  jz      short loc_1800222D0
0x180022289  lea     rdi, aCspproviderLoa_2; "CSpProvider::_LoadLibraries"
0x180022290  mov     ecx, cs:dword_180397B68
0x180022296  cmp     ecx, 2
0x180022299  jbe     loc_18002254E
0x18002229f  mov     dword ptr [rbp+arg_8], eax
0x1800222a2  mov     dword ptr [rbp+arg_10], 5Ah ; 'Z'
0x1800222a9  lea     rax, [rbp+arg_8]
0x1800222ad  mov     [rsp+70h+var_40], rax
0x1800222b2  lea     rax, [rbp+arg_10]
0x1800222b6  mov     [rsp+70h+var_48], rax
0x1800222bb  lea     rax, [rbp+var_30]
0x1800222bf  mov     [rsp+70h+var_50], rax
0x1800222c4  lea     rdx, unk_1802F1920
0x1800222cb  jmp     loc_180022545
0x1800222d0  xor     edx, edx; hFile
0x1800222d2  mov     r8d, 802h; dwFlags
0x1800222d8  lea     rcx, aMispaceDll_0; "mispace.dll"
0x1800222df  call    cs:__imp_LoadLibraryExW
0x1800222e5  mov     cs:?g_SpacesModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_SpacesModule
0x1800222ec  test    rax, rax
0x1800222ef  jnz     short loc_180022346
0x1800222f1  lea     rdi, aCspproviderLoa_1; "CSpProvider::_LoadResources"
0x1800222f8  mov     eax, cs:dword_180397B68
0x1800222fe  cmp     eax, 2
0x180022301  jbe     short loc_18002233C
0x180022303  mov     dword ptr [rbp+arg_8], 1
0x18002230a  mov     dword ptr [rbp+arg_10], 64h ; 'd'
0x180022311  mov     [rbp+var_30], r15
0x180022315  lea     rax, [rbp+arg_8]
0x180022319  mov     [rsp+70h+var_40], rax
0x18002231e  lea     rax, [rbp+arg_10]
0x180022322  mov     [rsp+70h+var_48], rax
0x180022327  lea     rax, [rbp+var_30]
0x18002232b  mov     [rsp+70h+var_50], rax
0x180022330  lea     rdx, byte_1802F2931
0x180022337  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002233c  mov     ebx, 1
0x180022341  jmp     loc_18002254E
0x180022346  mov     rcx, rsi; this
0x180022349  call    ?_LoadRegistry@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_LoadRegistry(void)
0x18002234e  mov     ebx, eax
0x180022350  test    eax, eax
0x180022352  jz      short loc_18002237D
0x180022354  lea     rdi, aCspproviderLoa_0; "CSpProvider::_LoadRegistry"
0x18002235b  mov     eax, cs:dword_180397B68
0x180022361  cmp     eax, 2
0x180022364  jbe     loc_18002254E
0x18002236a  mov     dword ptr [rbp+arg_10], 6Eh ; 'n'
0x180022371  lea     rdx, dword_1802F1794
0x180022378  jmp     loc_180022527
0x18002237d  xorps   xmm0, xmm0
0x180022380  movups  xmmword ptr [rsi+0A0h], xmm0
0x180022387  movups  xmmword ptr [rsi+0B0h], xmm0
0x18002238e  movups  xmmword ptr [rsi+0C0h], xmm0
0x180022395  movups  xmmword ptr [rsi+0D0h], xmm0
0x18002239c  mov     rcx, rsi; this
0x18002239f  call    ?_LoadSubsystems@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_LoadSubsystems(void)
0x1800223a4  mov     ebx, eax
0x1800223a6  test    eax, eax
0x1800223a8  jz      short loc_1800223D3
0x1800223aa  lea     rdi, aCspproviderLoa; "CSpProvider::_LoadSubsystems"
0x1800223b1  mov     eax, cs:dword_180397B68
0x1800223b7  cmp     eax, 2
0x1800223ba  jbe     loc_18002254E
0x1800223c0  mov     dword ptr [rbp+arg_10], 7Ch ; '|'
0x1800223c7  lea     rdx, word_1802F47F2
0x1800223ce  jmp     loc_180022527
0x1800223d3  mov     rcx, rsi; this
0x1800223d6  call    ?_ConnectAllSubsystems@CSpProvider@@AEAA?AW4_MI_Result@@XZ; CSpProvider::_ConnectAllSubsystems(void)
0x1800223db  mov     ebx, eax
0x1800223dd  test    eax, eax
0x1800223df  jz      short loc_18002240A
0x1800223e1  lea     rdi, aCspproviderCon; "CSpProvider::_ConnectAllSubsystems"
0x1800223e8  mov     eax, cs:dword_180397B68
0x1800223ee  cmp     eax, 2
0x1800223f1  jbe     loc_18002254E
0x1800223f7  mov     dword ptr [rbp+arg_10], 86h
0x1800223fe  lea     rdx, word_1802F1556
0x180022405  jmp     loc_180022527
0x18002240a  lea     rcx, [rbp+arg_18]
0x18002240e  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180022413  lea     rcx, [rsi+10h]
0x180022417  lea     r8, [rbp+arg_18]
0x18002241b  lea     rdx, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180022422  call    ?Find@?$CRefMap@PEAGPEAVCSpSubsystem@@@@QEAAHPEAGPEAPEAVCSpSubsystem@@@Z; CRefMap<ushort *,CSpSubsystem *>::Find(ushort *,CSpSubsystem * *)
0x180022427  test    eax, eax
0x180022429  jnz     short loc_180022457
0x18002242b  lea     rdi, aCrefmapLpwstrC; "CRefMap<LPWSTR, CSpSubsystem*>::Find"
0x180022432  lea     ebx, [rax+6]
0x180022435  mov     eax, cs:dword_180397B68
0x18002243b  cmp     eax, 2
0x18002243e  jbe     loc_18002254E
0x180022444  mov     dword ptr [rbp+arg_10], 93h
0x18002244b  lea     rdx, byte_1802F32DD
0x180022452  jmp     loc_180022527
0x180022457  mov     rax, [rbp+arg_18]
0x18002245b  mov     rcx, [rax+8]
0x18002245f  test    rcx, rcx
0x180022462  jz      loc_180022502
0x180022468  cmp     dword ptr [rcx+8], 0
0x18002246c  jz      loc_180022502
0x180022472  call    ?Initialize@CSpJobMgr@@SAHXZ; CSpJobMgr::Initialize(void)
0x180022477  test    eax, eax
0x180022479  jnz     short loc_1800224A8
0x18002247b  lea     rdi, aCspjobmgrIniti; "CSpJobMgr::Initialize"
0x180022482  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180022487  mov     ebx, eax
0x180022489  mov     eax, cs:dword_180397B68
0x18002248f  cmp     eax, 2
0x180022492  jbe     loc_18002254E
0x180022498  mov     dword ptr [rbp+arg_10], 0A3h
0x18002249f  lea     rdx, unk_1802F45D8
0x1800224a6  jmp     short loc_180022527
0x1800224a8  call    ?Initialize@CSpRuntimeCounters@@QEAAHXZ; CSpRuntimeCounters::Initialize(void)
0x1800224ad  test    eax, eax
0x1800224af  jnz     short loc_1800224DE
0x1800224b1  lea     rdi, aCspruntimecoun_1; "CSpRuntimeCounters::Initialize"
0x1800224b8  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800224bd  mov     ebx, eax
0x1800224bf  mov     eax, cs:dword_180397B68
0x1800224c5  cmp     eax, 2
0x1800224c8  jbe     loc_18002254E
0x1800224ce  mov     dword ptr [rbp+arg_10], 0ABh
0x1800224d5  lea     rdx, byte_1802F4647
0x1800224dc  jmp     short loc_180022527
0x1800224de  xor     edi, edi
0x1800224e0  lea     rcx, [rsi+98h]; SRWLock
0x1800224e7  call    cs:__imp_InitializeSRWLock
0x1800224ed  lea     rcx, [rsi+0E0h]; SRWLock
0x1800224f4  call    cs:__imp_InitializeSRWLock
0x1800224fa  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x180022500  jmp     short loc_18002254E
0x180022502  lea     rdi, aCspsubsystemIs; "CSpSubsystem::IsConnected"
0x180022509  mov     ebx, 1
0x18002250e  mov     eax, cs:dword_180397B68
0x180022514  cmp     eax, 2
0x180022517  jbe     short loc_18002254E
0x180022519  mov     dword ptr [rbp+arg_10], 9Bh
0x180022520  lea     rdx, word_1802F296A
0x180022527  lea     rax, [rbp+arg_8]
0x18002252b  mov     [rsp+70h+var_40], rax
0x180022530  lea     rax, [rbp+arg_10]
0x180022534  mov     [rsp+70h+var_48], rax
0x180022539  lea     rax, [rbp+var_30]
0x18002253d  mov     [rsp+70h+var_50], rax
0x180022542  mov     dword ptr [rbp+arg_8], ebx
0x180022545  mov     [rbp+var_30], r15
0x180022549  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002254e  lea     rcx, [rbp+var_28]; this
0x180022552  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180022557  test    ebx, ebx
0x180022559  jz      short loc_180022584
0x18002255b  mov     rcx, rsi; this
0x18002255e  call    ?Cleanup@CSpProvider@@QEAA?AW4_MI_Result@@XZ; CSpProvider::Cleanup(void)
0x180022563  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 1
0x18002256a  jz      short loc_1800225B4
0x18002256c  mov     dword ptr [rsp+70h+var_50], ebx
0x180022570  mov     r9, rdi
0x180022573  mov     r8, r15
0x180022576  lea     rdx, ProviderInitializationFailed
0x18002257d  call    McTemplateU0ssq_EventWriteTransfer
0x180022582  jmp     short loc_1800225B4
0x180022584  test    cs:Microsoft_Windows_StorageManagement_WSP_SpacesEnableBits, 4
0x18002258b  jz      short loc_1800225B4
0x18002258d  mov     rax, [rbp+var_20]
0x180022591  sub     rax, [rbp+var_28]
0x180022595  imul    rax, 3E8h
0x18002259c  xor     edx, edx
0x18002259e  div     [rbp+var_18]
0x1800225a2  mov     r9, rax
0x1800225a5  mov     r8, r15
0x1800225a8  lea     rdx, ProviderInitializationSucceeded
0x1800225af  call    McTemplateU0sx_EventWriteTransfer
0x1800225b4  mov     eax, cs:dword_180397B68
0x1800225ba  cmp     eax, 5
0x1800225bd  jbe     short loc_1800225E9
0x1800225bf  mov     dword ptr [rbp+arg_8], 0C6h
0x1800225c6  mov     [rbp+arg_10], r15
0x1800225ca  lea     rax, [rbp+arg_8]
0x1800225ce  mov     [rsp+70h+var_48], rax
0x1800225d3  lea     rax, [rbp+arg_10]
0x1800225d7  mov     [rsp+70h+var_50], rax
0x1800225dc  lea     rdx, byte_1802F450D
0x1800225e3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800225e8  nop
0x1800225e9  lea     rcx, [rbp+var_28]; this
0x1800225ed  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1800225f2  nop
0x1800225f3  lea     rcx, [rbp+arg_18]
0x1800225f7  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800225fc  mov     eax, ebx
0x1800225fe  add     rsp, 70h
0x180022602  pop     r15
0x180022604  pop     rdi
0x180022605  pop     rsi
0x180022606  pop     rbx
0x180022607  pop     rbp
0x180022608  retn
```
