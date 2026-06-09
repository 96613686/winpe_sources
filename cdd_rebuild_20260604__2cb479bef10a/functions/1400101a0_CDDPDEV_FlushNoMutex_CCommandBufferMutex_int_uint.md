# CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)

- ea: `0x1400101a0`
- end: `0x140010669`
- name: `?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this, struct CCommandBufferMutex *, int, unsigned int)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000f370`
- `0x14000fdb0`
- `0x14001c630`
- `0x14001cce4`
- `0x14001fa08`
- `0x140020e48`
- `0x14002ea64`

## callees

- `0x1400101a0`
- `0x140010670`
- `0x1400106ec`
- `0x140010798`
- `0x140010850`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400102ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400103e5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400102ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400103e5`
- `ntoskrnl!KeClearEvent` at `0x1400102fd`
- `ntoskrnl!KeClearEvent` at `0x1400103f8`
- `ntoskrnl!KeClearEvent` at `0x1400102fd`
- `ntoskrnl!KeClearEvent` at `0x1400103f8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010258`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010353`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010258`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010353`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010317`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010412`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010317`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010412`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001023a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001026a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010335`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010365`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001023a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001026a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010335`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010365`
- `ntoskrnl!KeSetEvent` at `0x1400102c6`
- `ntoskrnl!KeSetEvent` at `0x1400103c1`
- `ntoskrnl!KeSetEvent` at `0x1400102c6`
- `ntoskrnl!KeSetEvent` at `0x1400103c1`
- `ntoskrnl!DbgPrint` at `0x1400104ec`
- `ntoskrnl!DbgPrint` at `0x140010609`
- `ntoskrnl!DbgPrint` at `0x1400104ec`
- `ntoskrnl!DbgPrint` at `0x140010609`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400104d5`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400105f2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010513`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010630`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010513`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010630`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001044a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001049d`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140010567`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400105ba`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001044a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001049d`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140010567`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400105ba`
- `watchdog!WdLogSingleEntry0` at `0x140010434`
- `watchdog!WdLogSingleEntry0` at `0x140010487`
- `watchdog!WdLogSingleEntry0` at `0x1400104fd`
- `watchdog!WdLogSingleEntry0` at `0x140010551`
- `watchdog!WdLogSingleEntry0` at `0x1400105a4`
- `watchdog!WdLogSingleEntry0` at `0x14001061a`
- `watchdog!WdLogSingleEntry0` at `0x140010434`
- `watchdog!WdLogSingleEntry0` at `0x140010487`
- `watchdog!WdLogSingleEntry0` at `0x1400104fd`
- `watchdog!WdLogSingleEntry0` at `0x140010551`
- `watchdog!WdLogSingleEntry0` at `0x1400105a4`
- `watchdog!WdLogSingleEntry0` at `0x14001061a`

## string_xrefs

- `0x1400104e5`: `CddIssueCommand: worker thread submission mutex is not held\n`
- `0x140010602`: `CddIssueCommand: worker thread submission mutex is not held\n`

## pseudocode

```c
__int64 __fastcall CDDPDEV::FlushNoMutex(CDDPDEV *this, struct CCommandBufferMutex *a2, int a3, int a4)
{
  __int64 v7; // rdx
  __int64 result; // rax
  __int64 v9; // rbp
  __int64 v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax

  if ( *(_DWORD *)(*((_QWORD *)this + 1587) + 32LL) != *(_DWORD *)(*((_QWORD *)this + 1587) + 16LL) || a3 )
  {
    if ( KeGetCurrentThread() == *((struct _KTHREAD **)this + 321) )
    {
      CDDPDEV::FlushGdiOutput(this, 0);
    }
    else if ( a2 && *((_BYTE *)a2 + 9) )
    {
      CCommandBufferMutex::EnableWorkerThreadAccess(a2);
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 785;
        v11 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v11[3] = gCddImageInfo;
        v11[4] = (unsigned int)dword_14003E570;
        v11[5] = 215857758;
        WdLogGlobalForLineNumber = 785;
      }
      v9 = *((_QWORD *)this + 686);
      ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v9);
      *((_DWORD *)this + 912) = a4;
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2021;
        v12 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v12[3] = gCddImageInfo;
        v12[4] = (unsigned int)dword_14003E570;
        v12[5] = 215857758;
        WdLogGlobalForLineNumber = 2021;
      }
      if ( *(struct _KTHREAD **)(*((_QWORD *)this + 686) + 8LL) != KeGetCurrentThread() && (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("CddIssueCommand: worker thread submission mutex is not held\n");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 2025;
        v13 = (_QWORD *)WdLogNewEntry5_WdError();
        v13[3] = gCddImageInfo;
        v13[4] = (unsigned int)dword_14003E570;
        v13[5] = 215857758;
        WdLogGlobalForLineNumber = 2025;
        __debugbreak();
      }
      *((_QWORD *)this + 322) = KeGetCurrentThread();
      *((_DWORD *)this + 900) = 13;
      GetConnectedStandbyProcessName(this);
      KeSetEvent(*((PRKEVENT *)this + 326), 0, 0);
      KeWaitForSingleObject(*((PVOID *)this + 329), Executive, 0, 0, 0);
      KeClearEvent(*((PRKEVENT *)this + 326));
      *((_QWORD *)this + 322) = 0;
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v9);
      CCommandBufferMutex::DisableWorkerThreadAccess(a2);
    }
    else
    {
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 785;
        v14 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v14[3] = gCddImageInfo;
        v14[4] = (unsigned int)dword_14003E570;
        v14[5] = 215857758;
        WdLogGlobalForLineNumber = 785;
      }
      v10 = *((_QWORD *)this + 686);
      ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v10);
      *((_DWORD *)this + 912) = a4;
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2021;
        v15 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v15[3] = gCddImageInfo;
        v15[4] = (unsigned int)dword_14003E570;
        v15[5] = 215857758;
        WdLogGlobalForLineNumber = 2021;
      }
      if ( *(struct _KTHREAD **)(*((_QWORD *)this + 686) + 8LL) != KeGetCurrentThread() && (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("CddIssueCommand: worker thread submission mutex is not held\n");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 2025;
        v16 = (_QWORD *)WdLogNewEntry5_WdError();
        v16[3] = gCddImageInfo;
        v16[4] = (unsigned int)dword_14003E570;
        v16[5] = 215857758;
        WdLogGlobalForLineNumber = 2025;
        __debugbreak();
      }
      *((_QWORD *)this + 322) = KeGetCurrentThread();
      *((_DWORD *)this + 900) = 13;
      GetConnectedStandbyProcessName(this);
      KeSetEvent(*((PRKEVENT *)this + 326), 0, 0);
      KeWaitForSingleObject(*((PVOID *)this + 329), Executive, 0, 0, 0);
      KeClearEvent(*((PRKEVENT *)this + 326));
      *((_QWORD *)this + 322) = 0;
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v10);
    }
  }
  v7 = *((_QWORD *)this + 1587);
  result = 0;
  if ( *(_DWORD *)(v7 + 32) == *(_DWORD *)(v7 + 16) )
  {
    *(_DWORD *)(v7 + 2120) = 0;
    *(_BYTE *)(v7 + 2144) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400101a0  sub     rsp, 38h
0x1400101a4  mov     rax, [rcx+3198h]
0x1400101ab  mov     [rsp+38h+arg_0], rbx
0x1400101b0  mov     rbx, rcx
0x1400101b3  mov     [rsp+38h+arg_10], rsi
0x1400101b8  mov     esi, r9d
0x1400101bb  mov     [rsp+38h+var_8], rdi
0x1400101c0  mov     rdi, rdx
0x1400101c3  mov     r10d, [rax+10h]
0x1400101c7  cmp     [rax+20h], r10d
0x1400101cb  jnz     short loc_140010204
0x1400101cd  test    r8d, r8d
0x1400101d0  jnz     short loc_140010204
0x1400101d2  mov     rdx, [rbx+3198h]
0x1400101d9  xor     eax, eax
0x1400101db  mov     rdi, [rsp+38h+var_8]
0x1400101e0  mov     rsi, [rsp+38h+arg_10]
0x1400101e5  mov     rbx, [rsp+38h+arg_0]
0x1400101ea  mov     ecx, [rdx+10h]
0x1400101ed  cmp     [rdx+20h], ecx
0x1400101f0  jnz     short loc_1400101FE
0x1400101f2  mov     [rdx+848h], eax
0x1400101f8  mov     [rdx+860h], al
0x1400101fe  add     rsp, 38h
0x140010202  retn
0x140010204  mov     rax, gs:188h
0x14001020d  cmp     rax, [rcx+0A08h]
0x140010214  jz      loc_140010423
0x14001021a  test    rdi, rdi
0x14001021d  jz      loc_140010335
0x140010223  cmp     byte ptr [rdx+9], 0
0x140010227  jz      loc_140010335
0x14001022d  mov     rcx, rdi; this
0x140010230  mov     [rsp+38h+arg_8], rbp
0x140010235  call    ?EnableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::EnableWorkerThreadAccess(void)
0x14001023a  call    cs:__imp_KeGetCurrentIrql
0x140010241  nop     dword ptr [rax+rax+00h]
0x140010246  test    al, al
0x140010248  jnz     loc_14001042F
0x14001024e  mov     rbp, [rbx+1570h]
0x140010255  mov     rcx, rbp
0x140010258  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001025f  nop     dword ptr [rax+rax+00h]
0x140010264  mov     [rbx+0E40h], esi
0x14001026a  call    cs:__imp_KeGetCurrentIrql
0x140010271  nop     dword ptr [rax+rax+00h]
0x140010276  test    al, al
0x140010278  jnz     loc_140010482
0x14001027e  mov     rcx, gs:188h
0x140010287  mov     rax, [rbx+1570h]
0x14001028e  cmp     [rax+8], rcx
0x140010292  jnz     loc_1400104D5
0x140010298  mov     rax, gs:188h
0x1400102a1  mov     rcx, rbx; struct CDDPDEV *
0x1400102a4  mov     [rbx+0A10h], rax
0x1400102ab  mov     dword ptr [rbx+0E10h], 0Dh
0x1400102b5  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x1400102ba  mov     rcx, [rbx+0A30h]; Event
0x1400102c1  xor     r8d, r8d; Wait
0x1400102c4  xor     edx, edx; Increment
0x1400102c6  call    cs:__imp_KeSetEvent
0x1400102cd  nop     dword ptr [rax+rax+00h]
0x1400102d2  mov     rcx, [rbx+0A48h]; Object
0x1400102d9  xor     r9d, r9d; Alertable
0x1400102dc  xor     r8d, r8d; WaitMode
0x1400102df  mov     [rsp+38h+Timeout], 0; Timeout
0x1400102e8  xor     edx, edx; WaitReason
0x1400102ea  call    cs:__imp_KeWaitForSingleObject
0x1400102f1  nop     dword ptr [rax+rax+00h]
0x1400102f6  mov     rcx, [rbx+0A30h]; Event
0x1400102fd  call    cs:__imp_KeClearEvent
0x140010304  nop     dword ptr [rax+rax+00h]
0x140010309  mov     rcx, rbp
0x14001030c  mov     qword ptr [rbx+0A10h], 0
0x140010317  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14001031e  nop     dword ptr [rax+rax+00h]
0x140010323  mov     rcx, rdi; this
0x140010326  call    ?DisableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::DisableWorkerThreadAccess(void)
0x14001032b  mov     rbp, [rsp+38h+arg_8]
0x140010330  jmp     loc_1400101D2
0x140010335  call    cs:__imp_KeGetCurrentIrql
0x14001033c  nop     dword ptr [rax+rax+00h]
0x140010341  test    al, al
0x140010343  jnz     loc_14001054C
0x140010349  mov     rdi, [rbx+1570h]
0x140010350  mov     rcx, rdi
0x140010353  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001035a  nop     dword ptr [rax+rax+00h]
0x14001035f  mov     [rbx+0E40h], esi
0x140010365  call    cs:__imp_KeGetCurrentIrql
0x14001036c  nop     dword ptr [rax+rax+00h]
0x140010371  test    al, al
0x140010373  jnz     loc_14001059F
0x140010379  mov     rcx, gs:188h
0x140010382  mov     rax, [rbx+1570h]
0x140010389  cmp     [rax+8], rcx
0x14001038d  jnz     loc_1400105F2
0x140010393  mov     rax, gs:188h
0x14001039c  mov     rcx, rbx; struct CDDPDEV *
0x14001039f  mov     [rbx+0A10h], rax
0x1400103a6  mov     dword ptr [rbx+0E10h], 0Dh
0x1400103b0  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x1400103b5  mov     rcx, [rbx+0A30h]; Event
0x1400103bc  xor     r8d, r8d; Wait
0x1400103bf  xor     edx, edx; Increment
0x1400103c1  call    cs:__imp_KeSetEvent
0x1400103c8  nop     dword ptr [rax+rax+00h]
0x1400103cd  mov     rcx, [rbx+0A48h]; Object
0x1400103d4  xor     r9d, r9d; Alertable
0x1400103d7  xor     r8d, r8d; WaitMode
0x1400103da  mov     [rsp+38h+Timeout], 0; Timeout
0x1400103e3  xor     edx, edx; WaitReason
0x1400103e5  call    cs:__imp_KeWaitForSingleObject
0x1400103ec  nop     dword ptr [rax+rax+00h]
0x1400103f1  mov     rcx, [rbx+0A30h]; Event
0x1400103f8  call    cs:__imp_KeClearEvent
0x1400103ff  nop     dword ptr [rax+rax+00h]
0x140010404  mov     rcx, rdi
0x140010407  mov     qword ptr [rbx+0A10h], 0
0x140010412  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140010419  nop     dword ptr [rax+rax+00h]
0x14001041e  jmp     loc_1400101D2
0x140010423  xor     edx, edx; unsigned int
0x140010425  call    ?FlushGdiOutput@CDDPDEV@@QEAAXI@Z; CDDPDEV::FlushGdiOutput(uint)
0x14001042a  jmp     loc_1400101D2
0x14001042f  mov     ecx, 1
0x140010434  call    cs:__imp_WdLogSingleEntry0
0x14001043b  nop     dword ptr [rax+rax+00h]
0x140010440  mov     cs:WdLogGlobalForLineNumber, 311h
0x14001044a  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140010451  nop     dword ptr [rax+rax+00h]
0x140010456  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001045d  mov     [rax+18h], rcx
0x140010461  mov     ecx, cs:dword_14003E570
0x140010467  mov     [rax+20h], rcx
0x14001046b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140010473  mov     cs:WdLogGlobalForLineNumber, 311h
0x14001047d  jmp     loc_14001024E
0x140010482  mov     ecx, 1
0x140010487  call    cs:__imp_WdLogSingleEntry0
0x14001048e  nop     dword ptr [rax+rax+00h]
0x140010493  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x14001049d  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400104a4  nop     dword ptr [rax+rax+00h]
0x1400104a9  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400104b0  mov     [rax+18h], rcx
0x1400104b4  mov     ecx, cs:dword_14003E570
0x1400104ba  mov     [rax+20h], rcx
0x1400104be  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400104c6  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x1400104d0  jmp     loc_14001027E
0x1400104d5  mov     rax, cs:KdDebuggerEnabled
0x1400104dc  cmp     byte ptr [rax], 0
0x1400104df  jz      loc_140010298
0x1400104e5  lea     rcx, aCddissuecomman; "CddIssueCommand: worker thread submissi"...
0x1400104ec  call    cs:__imp_DbgPrint
0x1400104f3  nop     dword ptr [rax+rax+00h]
0x1400104f8  mov     ecx, 2
0x1400104fd  call    cs:__imp_WdLogSingleEntry0
0x140010504  nop     dword ptr [rax+rax+00h]
0x140010509  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x140010513  call    cs:__imp_WdLogNewEntry5_WdError
0x14001051a  nop     dword ptr [rax+rax+00h]
0x14001051f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140010526  mov     [rax+18h], rcx
0x14001052a  mov     ecx, cs:dword_14003E570
0x140010530  mov     [rax+20h], rcx
0x140010534  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001053c  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x140010546  int     3; Trap to Debugger
0x140010547  jmp     loc_140010298
0x14001054c  mov     ecx, 1
0x140010551  call    cs:__imp_WdLogSingleEntry0
0x140010558  nop     dword ptr [rax+rax+00h]
0x14001055d  mov     cs:WdLogGlobalForLineNumber, 311h
0x140010567  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001056e  nop     dword ptr [rax+rax+00h]
0x140010573  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001057a  mov     [rax+18h], rcx
0x14001057e  mov     ecx, cs:dword_14003E570
0x140010584  mov     [rax+20h], rcx
0x140010588  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140010590  mov     cs:WdLogGlobalForLineNumber, 311h
0x14001059a  jmp     loc_140010349
0x14001059f  mov     ecx, 1
0x1400105a4  call    cs:__imp_WdLogSingleEntry0
0x1400105ab  nop     dword ptr [rax+rax+00h]
0x1400105b0  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x1400105ba  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400105c1  nop     dword ptr [rax+rax+00h]
0x1400105c6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400105cd  mov     [rax+18h], rcx
0x1400105d1  mov     ecx, cs:dword_14003E570
0x1400105d7  mov     [rax+20h], rcx
0x1400105db  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400105e3  mov     cs:WdLogGlobalForLineNumber, 7E5h
0x1400105ed  jmp     loc_140010379
0x1400105f2  mov     rax, cs:KdDebuggerEnabled
0x1400105f9  cmp     byte ptr [rax], 0
0x1400105fc  jz      loc_140010393
0x140010602  lea     rcx, aCddissuecomman; "CddIssueCommand: worker thread submissi"...
0x140010609  call    cs:__imp_DbgPrint
0x140010610  nop     dword ptr [rax+rax+00h]
0x140010615  mov     ecx, 2
0x14001061a  call    cs:__imp_WdLogSingleEntry0
0x140010621  nop     dword ptr [rax+rax+00h]
0x140010626  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x140010630  call    cs:__imp_WdLogNewEntry5_WdError
0x140010637  nop     dword ptr [rax+rax+00h]
0x14001063c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140010643  mov     [rax+18h], rcx
0x140010647  mov     ecx, cs:dword_14003E570
0x14001064d  mov     [rax+20h], rcx
0x140010651  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140010659  mov     cs:WdLogGlobalForLineNumber, 7E9h
0x140010663  int     3; Trap to Debugger
0x140010664  jmp     loc_140010393
```
