# RpcSrvMadcapApiCleanup_New

- ea: `0x180029e90`
- end: `0x180029fa5`
- name: `RpcSrvMadcapApiCleanup_New`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180029d50`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x180029e90`
- `0x18004d1e0`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029f25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029f43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029f43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029ee9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029ee9`
- `RPCRT4!RpcImpersonateClient` at `0x180029ed8`
- `RPCRT4!RpcImpersonateClient` at `0x180029ed8`
- `RPCRT4!RpcRevertToSelf` at `0x180029f49`
- `RPCRT4!RpcRevertToSelf` at `0x180029f49`
- `WS2_32!__imp_WSACleanup` at `0x180029f36`
- `WS2_32!__imp_WSACleanup` at `0x180029f36`

## pseudocode

```c
void __fastcall RpcSrvMadcapApiCleanup_New(CRpcWatchDog *a1, __int64 a2, int a3)
{
  unsigned int v3; // eax
  CRpcWatchDog *v4; // rcx
  int v5; // eax
  _OWORD v6[2]; // [rsp+30h] [rbp-28h] BYREF

  memset(v6, 0, sizeof(v6));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 226, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  *(_QWORD *)&v6[0] = RpcSrvMadcapApiCleanup;
  CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v6, a3);
  v3 = RpcImpersonateClient(0);
  if ( v3 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_Dd(1025, 227, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v3, v3);
  }
  else
  {
    EnterCriticalSection(&MadcapGlobalScopeListCritSect);
    v5 = MadcapGlobalInitialized;
    if ( MadcapGlobalInitialized )
    {
      --MadcapGlobalInitialized;
      if ( v5 == 1 )
      {
        gMadcapScopeList = 0;
        gMScopeQueryInProgress = 0;
        if ( gMScopeQueryEvent )
        {
          CloseHandle(gMScopeQueryEvent);
          gMScopeQueryEvent = 0;
        }
        WSACleanup();
      }
    }
    LeaveCriticalSection(&MadcapGlobalScopeListCritSect);
    RpcRevertToSelf();
  }
  CRpcWatchDog::RemoveEntry(v4, (struct _WatchDogEntry *)v6);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 228, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
}

```

## disassembly

```asm
0x180029e90  sub     rsp, 58h
0x180029e94  xorps   xmm0, xmm0
0x180029e97  movups  [rsp+58h+var_28], xmm0
0x180029e9c  movups  [rsp+58h+var_18], xmm0
0x180029ea1  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029ea8  jz      short loc_180029EC0
0x180029eaa  mov     edx, 0E2h
0x180029eaf  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029eb6  mov     ecx, 404h
0x180029ebb  call    WPP_SF_
0x180029ec0  lea     rax, RpcSrvMadcapApiCleanup
0x180029ec7  lea     rdx, [rsp+58h+var_28]; struct _WatchDogEntry *
0x180029ecc  mov     qword ptr [rsp+58h+var_28], rax
0x180029ed1  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180029ed6  xor     ecx, ecx; BindingHandle
0x180029ed8  call    cs:__imp_RpcImpersonateClient
0x180029ede  test    eax, eax
0x180029ee0  jnz     short loc_180029F51
0x180029ee2  lea     rcx, MadcapGlobalScopeListCritSect; lpCriticalSection
0x180029ee9  call    cs:__imp_EnterCriticalSection
0x180029eef  mov     eax, cs:MadcapGlobalInitialized
0x180029ef5  test    eax, eax
0x180029ef7  jz      short loc_180029F3C
0x180029ef9  add     eax, 0FFFFFFFFh
0x180029efc  mov     cs:MadcapGlobalInitialized, eax
0x180029f02  jnz     short loc_180029F3C
0x180029f04  mov     rcx, cs:gMScopeQueryEvent; hObject
0x180029f0b  mov     cs:gMadcapScopeList, 0
0x180029f16  mov     cs:gMScopeQueryInProgress, 0
0x180029f20  test    rcx, rcx
0x180029f23  jz      short loc_180029F36
0x180029f25  call    cs:__imp_CloseHandle
0x180029f2b  mov     cs:gMScopeQueryEvent, 0
0x180029f36  call    cs:__imp_WSACleanup
0x180029f3c  lea     rcx, MadcapGlobalScopeListCritSect; lpCriticalSection
0x180029f43  call    cs:__imp_LeaveCriticalSection
0x180029f49  call    cs:__imp_RpcRevertToSelf
0x180029f4f  jmp     short loc_180029F77
0x180029f51  test    byte ptr cs:xmmword_1800616A0, 2
0x180029f58  jz      short loc_180029F77
0x180029f5a  mov     edx, 0E3h
0x180029f5f  mov     [rsp+58h+var_38], eax
0x180029f63  mov     ecx, 401h
0x180029f68  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029f6f  mov     r9d, eax
0x180029f72  call    WPP_SF_Dd
0x180029f77  lea     rdx, [rsp+58h+var_28]; struct _WatchDogEntry *
0x180029f7c  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180029f81  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029f88  jz      short loc_180029FA0
0x180029f8a  mov     edx, 0E4h
0x180029f8f  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029f96  mov     ecx, 404h
0x180029f9b  call    WPP_SF_
0x180029fa0  add     rsp, 58h
0x180029fa4  retn
```
