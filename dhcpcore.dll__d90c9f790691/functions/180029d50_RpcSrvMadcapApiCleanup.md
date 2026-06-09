# RpcSrvMadcapApiCleanup

- ea: `0x180029d50`
- end: `0x180029e88`
- name: `RpcSrvMadcapApiCleanup`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800020d0`
- `0x1800021c0`
- `0x180029d50`
- `0x180029e90`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029e4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029e6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029e6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029e12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029e12`
- `RPCRT4!RpcImpersonateClient` at `0x180029dad`
- `RPCRT4!RpcImpersonateClient` at `0x180029dad`
- `RPCRT4!RpcRevertToSelf` at `0x180029e72`
- `RPCRT4!RpcRevertToSelf` at `0x180029e72`
- `WS2_32!__imp_WSACleanup` at `0x180029e5f`
- `WS2_32!__imp_WSACleanup` at `0x180029e5f`

## pseudocode

```c
void __fastcall RpcSrvMadcapApiCleanup(CRpcWatchDog *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // eax
  CRpcWatchDog *v5; // rcx
  unsigned int v6; // ebx
  int v7; // eax
  _OWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF

  memset(v8, 0, sizeof(v8));
  if ( g_fVelocityApistubStyleUpdate )
  {
    RpcSrvMadcapApiCleanup_New(a1, a2, a3, a4);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 229, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
    *(_QWORD *)&v8[0] = RpcSrvMadcapApiCleanup;
    CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)v8, a3);
    v4 = RpcImpersonateClient(0);
    v6 = v4;
    if ( v4 )
    {
      LOBYTE(v5) = xmmword_1800616A0;
      if ( (xmmword_1800616A0 & 2) != 0 )
      {
        WPP_SF_D(1025, 230, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v4);
        LOBYTE(v5) = xmmword_1800616A0;
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 231, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v6);
      }
    }
    else
    {
      EnterCriticalSection(&MadcapGlobalScopeListCritSect);
      v7 = MadcapGlobalInitialized;
      if ( MadcapGlobalInitialized )
      {
        --MadcapGlobalInitialized;
        if ( v7 == 1 )
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
    CRpcWatchDog::RemoveEntry(v5, (struct _WatchDogEntry *)v8);
  }
}

```

## disassembly

```asm
0x180029d50  push    rbx
0x180029d52  sub     rsp, 40h
0x180029d56  cmp     cs:g_fVelocityApistubStyleUpdate, 0
0x180029d5d  xorps   xmm0, xmm0
0x180029d60  movups  [rsp+48h+var_28], xmm0
0x180029d65  movups  [rsp+48h+var_18], xmm0
0x180029d6a  jz      short loc_180029D76
0x180029d6c  call    RpcSrvMadcapApiCleanup_New
0x180029d71  jmp     loc_180029E82
0x180029d76  test    byte ptr cs:xmmword_1800616A0, 10h
0x180029d7d  jz      short loc_180029D95
0x180029d7f  mov     edx, 0E5h
0x180029d84  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029d8b  mov     ecx, 404h
0x180029d90  call    WPP_SF_
0x180029d95  lea     rax, RpcSrvMadcapApiCleanup
0x180029d9c  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x180029da1  mov     qword ptr [rsp+48h+var_28], rax
0x180029da6  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180029dab  xor     ecx, ecx; BindingHandle
0x180029dad  call    cs:__imp_RpcImpersonateClient
0x180029db3  mov     ebx, eax
0x180029db5  test    eax, eax
0x180029db7  jz      short loc_180029E0B
0x180029db9  mov     cl, byte ptr cs:xmmword_1800616A0
0x180029dbf  test    cl, 2
0x180029dc2  jz      loc_180029E78
0x180029dc8  mov     edx, 0E6h
0x180029dcd  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029dd4  mov     ecx, 401h
0x180029dd9  mov     r9d, eax
0x180029ddc  call    WPP_SF_D
0x180029de1  mov     cl, byte ptr cs:xmmword_1800616A0
0x180029de7  test    cl, 2
0x180029dea  jz      loc_180029E78
0x180029df0  mov     edx, 0E7h
0x180029df5  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x180029dfc  mov     ecx, 401h
0x180029e01  mov     r9d, ebx
0x180029e04  call    WPP_SF_D
0x180029e09  jmp     short loc_180029E78
0x180029e0b  lea     rcx, MadcapGlobalScopeListCritSect; lpCriticalSection
0x180029e12  call    cs:__imp_EnterCriticalSection
0x180029e18  mov     eax, cs:MadcapGlobalInitialized
0x180029e1e  test    eax, eax
0x180029e20  jz      short loc_180029E65
0x180029e22  add     eax, 0FFFFFFFFh
0x180029e25  mov     cs:MadcapGlobalInitialized, eax
0x180029e2b  jnz     short loc_180029E65
0x180029e2d  mov     rcx, cs:gMScopeQueryEvent; hObject
0x180029e34  mov     cs:gMadcapScopeList, 0
0x180029e3f  mov     cs:gMScopeQueryInProgress, 0
0x180029e49  test    rcx, rcx
0x180029e4c  jz      short loc_180029E5F
0x180029e4e  call    cs:__imp_CloseHandle
0x180029e54  mov     cs:gMScopeQueryEvent, 0
0x180029e5f  call    cs:__imp_WSACleanup
0x180029e65  lea     rcx, MadcapGlobalScopeListCritSect; lpCriticalSection
0x180029e6c  call    cs:__imp_LeaveCriticalSection
0x180029e72  call    cs:__imp_RpcRevertToSelf
0x180029e78  lea     rdx, [rsp+48h+var_28]; struct _WatchDogEntry *
0x180029e7d  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x180029e82  add     rsp, 40h
0x180029e86  pop     rbx
0x180029e87  retn
```
