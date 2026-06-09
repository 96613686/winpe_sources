# DasEvaluateIdleStop(int *)

- ea: `0x180042ea8`
- end: `0x180042f3b`
- name: `?DasEvaluateIdleStop@@YAXPEAH@Z`
- size: `147`
- prototype: `void __fastcall(int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180028ed8`
- `0x180042f44`
- `0x18004a590`

## callees

- `0x180028f58`
- `0x180028f9c`
- `0x180042ea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042ebc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042ebc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042f34`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042f16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180042f16`

## pseudocode

```c
void __fastcall DasEvaluateIdleStop(int *a1)
{
  int v2; // edi
  struct _FILETIME *v3; // rdx
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  EnterCriticalSection(&g_csDasIdleStop);
  if ( !g_bDasStopping )
  {
    if ( !g_bDasRpcIdle
      || (v2 = 1, DAS::DevnodeManagment::DevnodeManager::IsManagingDevnodes(g_devnodeManager, 1))
      || (unsigned int)AnyInboundOperationsToManage() )
    {
      v2 = 0;
      v3 = 0;
    }
    else
    {
      v4 = -600000000;
      v3 = (struct _FILETIME *)&v4;
    }
    SetThreadpoolTimer(g_DasStopTimer, v3, 0, 0);
    if ( a1 )
      *a1 = v2;
  }
  LeaveCriticalSection(&g_csDasIdleStop);
}

```

## disassembly

```asm
0x180042ea8  mov     [rsp+arg_0], rbx
0x180042ead  push    rdi
0x180042eae  sub     rsp, 20h
0x180042eb2  mov     rbx, rcx
0x180042eb5  lea     rcx, ?g_csDasIdleStop@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180042ebc  call    cs:__imp_EnterCriticalSection
0x180042ec2  cmp     cs:?g_bDasStopping@@3JA, 0; long g_bDasStopping
0x180042ec9  jnz     short loc_180042F23
0x180042ecb  cmp     cs:?g_bDasRpcIdle@@3HA, 0; int g_bDasRpcIdle
0x180042ed2  jz      short loc_180042F05
0x180042ed4  mov     rcx, cs:?g_devnodeManager@@3V?$unique_ptr@VDevnodeManager@DevnodeManagment@DAS@@U?$default_delete@VDevnodeManager@DevnodeManagment@DAS@@@std@@@std@@A; this
0x180042edb  mov     edi, 1
0x180042ee0  mov     dl, dil; bool
0x180042ee3  call    ?IsManagingDevnodes@DevnodeManager@DevnodeManagment@DAS@@QEAA_N_N@Z; DAS::DevnodeManagment::DevnodeManager::IsManagingDevnodes(bool)
0x180042ee8  test    al, al
0x180042eea  jnz     short loc_180042F05
0x180042eec  call    ?AnyInboundOperationsToManage@@YAHXZ; AnyInboundOperationsToManage(void)
0x180042ef1  test    eax, eax
0x180042ef3  jnz     short loc_180042F05
0x180042ef5  mov     [rsp+28h+arg_8], 0FFFFFFFFDC3CBA00h
0x180042efe  lea     rdx, [rsp+28h+arg_8]
0x180042f03  jmp     short loc_180042F09
0x180042f05  xor     edi, edi
0x180042f07  xor     edx, edx; pftDueTime
0x180042f09  mov     rcx, cs:?g_DasStopTimer@@3PEAU_TP_TIMER@@EA; pti
0x180042f10  xor     r9d, r9d; msWindowLength
0x180042f13  xor     r8d, r8d; msPeriod
0x180042f16  call    cs:__imp_SetThreadpoolTimer
0x180042f1c  test    rbx, rbx
0x180042f1f  jz      short loc_180042F23
0x180042f21  mov     [rbx], edi
0x180042f23  lea     rcx, ?g_csDasIdleStop@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csDasIdleStop
0x180042f2a  mov     rbx, [rsp+28h+arg_0]
0x180042f2f  add     rsp, 20h
0x180042f33  pop     rdi
0x180042f34  jmp     cs:__imp_LeaveCriticalSection
```
