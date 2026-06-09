# IpNatHlpRpcServerStartSharing

- ea: `0x180069660`
- end: `0x1800697d3`
- name: `IpNatHlpRpcServerStartSharing`
- size: `371`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180012730`
- `0x18003d8d0`
- `0x18003f2f0`
- `0x18006912c`
- `0x180069660`
- `0x180072ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006973a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006976d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006973a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006976d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006974e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069783`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006974e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180069783`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180069760`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180069760`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069790`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180069790`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006972d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18006972d`
- `RPCRT4!RpcImpersonateClient` at `0x180069718`
- `RPCRT4!RpcImpersonateClient` at `0x180069718`

## pseudocode

```c
__int64 __fastcall IpNatHlpRpcServerStartSharing(void *a1, unsigned int a2, unsigned int a3, int a4)
{
  PVOID *v7; // rcx
  unsigned int started; // ebx
  unsigned int v9; // edx
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
      started = V2StartSharing(a1, v9, a3);
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
0x180069660  push    rbx
0x180069662  push    rbp
0x180069663  push    rsi
0x180069664  push    rdi
0x180069665  push    r15
0x180069667  sub     rsp, 30h
0x18006966b  mov     ebp, r9d
0x18006966e  mov     ebx, r8d
0x180069671  mov     r9d, edx
0x180069674  mov     rdi, rcx
0x180069677  mov     rcx, cs:WPP_GLOBAL_Control
0x18006967e  lea     r15, WPP_GLOBAL_Control
0x180069685  cmp     rcx, r15
0x180069688  jz      short loc_1800696AF
0x18006968a  test    byte ptr [rcx+1Ch], 40h
0x18006968e  jz      short loc_1800696AF
0x180069690  cmp     byte ptr [rcx+19h], 6
0x180069694  jb      short loc_1800696AF
0x180069696  mov     rcx, [rcx+10h]
0x18006969a  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x1800696a1  mov     edx, 31h ; '1'
0x1800696a6  mov     [rsp+58h+var_38], ebx
0x1800696aa  call    WPP_SF_dd
0x1800696af  call    ?IsDriverLoadDisabled@@YAEXZ; IsDriverLoadDisabled(void)
0x1800696b4  test    al, al
0x1800696b6  jz      short loc_1800696F8
0x1800696b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800696bf  mov     ebx, 5
0x1800696c4  cmp     rcx, r15
0x1800696c7  jz      loc_1800697C6
0x1800696cd  test    byte ptr [rcx+1Ch], 40h
0x1800696d1  jz      loc_18006979D
0x1800696d7  cmp     [rcx+19h], bl
0x1800696da  jb      loc_18006979D
0x1800696e0  mov     rcx, [rcx+10h]
0x1800696e4  lea     edx, [rbx+2Dh]
0x1800696e7  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x1800696ee  call    WPP_SF_
0x1800696f3  jmp     loc_180069796
0x1800696f8  call    ?IsIcsV2RetargetEnabled@@YAHXZ; IsIcsV2RetargetEnabled(void)
0x1800696fd  mov     rcx, rdi; void *
0x180069700  test    eax, eax
0x180069702  jz      short loc_180069713
0x180069704  mov     r8d, ebx; unsigned int
0x180069707  call    ?V2StartSharing@@YAKPEAXKK@Z; V2StartSharing(void *,ulong,ulong)
0x18006970c  mov     ebx, eax
0x18006970e  jmp     loc_180069796
0x180069713  xor     ebx, ebx
0x180069715  xor     sil, sil
0x180069718  call    cs:__imp_RpcImpersonateClient
0x18006971e  test    eax, eax
0x180069720  jnz     short loc_180069733
0x180069722  call    ?CheckLocalSystem@@YA_NXZ; CheckLocalSystem(void)
0x180069727  mov     rcx, rdi; BindingHandle
0x18006972a  mov     sil, al
0x18006972d  call    cs:__imp_RpcRevertToSelfEx
0x180069733  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006973a  call    cs:__imp_EnterCriticalSection
0x180069740  lea     rcx, ?g_csPolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180069747  mov     cs:?g_bIsCallerLocalSystem@@3_NA, sil; bool g_bIsCallerLocalSystem
0x18006974e  call    cs:__imp_LeaveCriticalSection
0x180069754  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006975b  mov     edx, 1; fCancelPendingCallbacks
0x180069760  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180069766  lea     rcx, ?g_csForceRoutingLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006976d  call    cs:__imp_EnterCriticalSection
0x180069773  test    ebp, ebp
0x180069775  lea     rcx, ?g_csForceRoutingLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18006977c  setnz   cs:?g_fForceRouting@@3_NA; bool g_fForceRouting
0x180069783  call    cs:__imp_LeaveCriticalSection
0x180069789  mov     rcx, cs:?g_StartSharingBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180069790  call    cs:__imp_SubmitThreadpoolWork
0x180069796  mov     rcx, cs:WPP_GLOBAL_Control
0x18006979d  cmp     rcx, r15
0x1800697a0  jz      short loc_1800697C6
0x1800697a2  test    byte ptr [rcx+1Ch], 40h
0x1800697a6  jz      short loc_1800697C6
0x1800697a8  cmp     byte ptr [rcx+19h], 6
0x1800697ac  jb      short loc_1800697C6
0x1800697ae  mov     rcx, [rcx+10h]
0x1800697b2  lea     r8, WPP_8dfbd5b0420c35e65ae705cfc0f87da9_Traceguids
0x1800697b9  mov     edx, 33h ; '3'
0x1800697be  mov     r9d, ebx
0x1800697c1  call    WPP_SF_d
0x1800697c6  mov     eax, ebx
0x1800697c8  add     rsp, 30h
0x1800697cc  pop     r15
0x1800697ce  pop     rdi
0x1800697cf  pop     rsi
0x1800697d0  pop     rbp
0x1800697d1  pop     rbx
0x1800697d2  retn
```
