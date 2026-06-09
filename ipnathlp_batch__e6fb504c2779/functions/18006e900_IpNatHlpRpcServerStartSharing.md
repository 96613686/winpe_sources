# IpNatHlpRpcServerStartSharing

- ea: `0x18006e900`
- end: `0x18006eaa4`
- name: `IpNatHlpRpcServerStartSharing`
- size: `420`
- prototype: `__int64 __fastcall(void *, unsigned int, NET_IFINDEX, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180013650`
- `0x180040c54`
- `0x1800427e8`
- `0x18006e3bc`
- `0x18006e900`
- `0x1800785e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e9e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ea2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e9e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ea2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ea00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ea47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ea00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ea47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006ea18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006ea18`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006ea5a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006ea5a`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006e9d3`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006e9d3`
- `RPCRT4!RpcImpersonateClient` at `0x18006e9b8`
- `RPCRT4!RpcImpersonateClient` at `0x18006e9b8`

## pseudocode

```c
__int64 __fastcall IpNatHlpRpcServerStartSharing(void *a1, unsigned int a2, NET_IFINDEX a3, int a4)
{
  PVOID *v7; // rcx
  unsigned int started; // ebx
  __int64 v9; // rdx
  bool v10; // si

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, a2, a3);
  }
  if ( !IsDriverLoadDisabled() )
  {
    if ( (unsigned int)IsIcsV2RetargetEnabled() )
    {
      started = V2StartSharing((__int64)a1, v9, a3);
    }
    else
    {
      started = 0;
      v10 = 0;
      if ( !RpcImpersonateClient(a1) )
      {
        v10 = CheckLocalSystem();
        RpcRevertToSelfEx(a1);
      }
      EnterCriticalSection(&g_csPolicyLock);
      g_bIsCallerLocalSystem = v10;
      LeaveCriticalSection(&g_csPolicyLock);
      WaitForThreadpoolWorkCallbacks(g_StartSharingBackgroundWork, 1);
      EnterCriticalSection(&g_csForceRoutingLock);
      g_fForceRouting = a4 != 0;
      LeaveCriticalSection(&g_csForceRoutingLock);
      SubmitThreadpoolWork(g_StartSharingBackgroundWork);
    }
    goto LABEL_15;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  started = 5;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return started;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids);
LABEL_15:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 51, &WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids, started);
  return started;
}

```

## disassembly

```asm
0x18006e900  push    rbx
0x18006e902  push    rbp
0x18006e903  push    rsi
0x18006e904  push    rdi
0x18006e905  push    r15
0x18006e907  sub     rsp, 30h
0x18006e90b  mov     ebp, r9d
0x18006e90e  mov     ebx, r8d
0x18006e911  mov     r9d, edx
0x18006e914  mov     rdi, rcx
0x18006e917  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e91e  lea     r15, WPP_GLOBAL_Control
0x18006e925  cmp     rcx, r15
0x18006e928  jz      short loc_18006E94F
0x18006e92a  test    byte ptr [rcx+1Ch], 40h
0x18006e92e  jz      short loc_18006E94F
0x18006e930  cmp     byte ptr [rcx+19h], 6
0x18006e934  jb      short loc_18006E94F
0x18006e936  mov     rcx, [rcx+10h]
0x18006e93a  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18006e941  mov     edx, 31h ; '1'
0x18006e946  mov     [rsp+58h+var_38], ebx
0x18006e94a  call    WPP_SF_dd
0x18006e94f  call    ?IsDriverLoadDisabled@@YAEXZ; IsDriverLoadDisabled(void)
0x18006e954  test    al, al
0x18006e956  jz      short loc_18006E998
0x18006e958  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e95f  mov     ebx, 5
0x18006e964  cmp     rcx, r15
0x18006e967  jz      loc_18006EA96
0x18006e96d  test    byte ptr [rcx+1Ch], 40h
0x18006e971  jz      loc_18006EA6D
0x18006e977  cmp     [rcx+19h], bl
0x18006e97a  jb      loc_18006EA6D
0x18006e980  mov     rcx, [rcx+10h]
0x18006e984  lea     edx, [rbx+2Dh]
0x18006e987  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18006e98e  call    WPP_SF_
0x18006e993  jmp     loc_18006EA66
0x18006e998  call    ?IsIcsV2RetargetEnabled@@YAHXZ; IsIcsV2RetargetEnabled(void)
0x18006e99d  mov     rcx, rdi; void *
0x18006e9a0  test    eax, eax
0x18006e9a2  jz      short loc_18006E9B3
0x18006e9a4  mov     r8d, ebx; unsigned int
0x18006e9a7  call    ?V2StartSharing@@YAKPEAXKK@Z; V2StartSharing(void *,ulong,ulong)
0x18006e9ac  mov     ebx, eax
0x18006e9ae  jmp     loc_18006EA66
0x18006e9b3  xor     ebx, ebx
0x18006e9b5  xor     sil, sil
0x18006e9b8  call    cs:__imp_RpcImpersonateClient
0x18006e9bf  nop     dword ptr [rax+rax+00h]
0x18006e9c4  test    eax, eax
0x18006e9c6  jnz     short loc_18006E9DF
0x18006e9c8  call    ?CheckLocalSystem@@YA_NXZ; CheckLocalSystem(void)
0x18006e9cd  mov     rcx, rdi; BindingHandle
0x18006e9d0  mov     sil, al
0x18006e9d3  call    cs:__imp_RpcRevertToSelfEx
0x18006e9da  nop     dword ptr [rax+rax+00h]
0x18006e9df  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006e9e6  call    cs:__imp_EnterCriticalSection
0x18006e9ed  nop     dword ptr [rax+rax+00h]
0x18006e9f2  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006e9f9  mov     cs:?g_bIsCallerLocalSystem@@3_NA, sil; bool g_bIsCallerLocalSystem
0x18006ea00  call    cs:__imp_LeaveCriticalSection
0x18006ea07  nop     dword ptr [rax+rax+00h]
0x18006ea0c  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006ea13  mov     edx, 1; fCancelPendingCallbacks
0x18006ea18  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18006ea1f  nop     dword ptr [rax+rax+00h]
0x18006ea24  lea     rcx, ?g_csForceRoutingLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006ea2b  call    cs:__imp_EnterCriticalSection
0x18006ea32  nop     dword ptr [rax+rax+00h]
0x18006ea37  test    ebp, ebp
0x18006ea39  lea     rcx, ?g_csForceRoutingLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006ea40  setnz   cs:?g_fForceRouting@@3_NA; bool g_fForceRouting
0x18006ea47  call    cs:__imp_LeaveCriticalSection
0x18006ea4e  nop     dword ptr [rax+rax+00h]
0x18006ea53  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006ea5a  call    cs:__imp_SubmitThreadpoolWork
0x18006ea61  nop     dword ptr [rax+rax+00h]
0x18006ea66  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ea6d  cmp     rcx, r15
0x18006ea70  jz      short loc_18006EA96
0x18006ea72  test    byte ptr [rcx+1Ch], 40h
0x18006ea76  jz      short loc_18006EA96
0x18006ea78  cmp     byte ptr [rcx+19h], 6
0x18006ea7c  jb      short loc_18006EA96
0x18006ea7e  mov     rcx, [rcx+10h]
0x18006ea82  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x18006ea89  mov     edx, 33h ; '3'
0x18006ea8e  mov     r9d, ebx
0x18006ea91  call    WPP_SF_d
0x18006ea96  mov     eax, ebx
0x18006ea98  add     rsp, 30h
0x18006ea9c  pop     r15
0x18006ea9e  pop     rdi
0x18006ea9f  pop     rsi
0x18006eaa0  pop     rbp
0x18006eaa1  pop     rbx
0x18006eaa2  retn
```
