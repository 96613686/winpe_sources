# CddBitmapHw::Release(void)

- ea: `0x1400015e0`
- end: `0x140001a56`
- name: `?Release@CddBitmapHw@@UEAAXXZ`
- size: `1142`
- prototype: `void __fastcall(CddBitmapHw *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400011f0`
- `0x1400015e0`
- `0x140001b6c`
- `0x140001cb4`
- `0x140001f04`
- `0x140002020`
- `0x140002130`
- `0x14000229c`
- `0x14000df80`
- `0x14000fbb4`
- `0x1400106ec`
- `0x140010798`
- `0x140022b9c`
- `0x1400371f0`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140001994`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140001994`
- `ntoskrnl!ObCloseHandle` at `0x14000192a`
- `ntoskrnl!ObCloseHandle` at `0x14000192a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140001732`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140001745`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400017c9`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140001732`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140001745`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400017c9`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400017eb`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400017eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400019df`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001768`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001768`
- `ntoskrnl!DbgPrint` at `0x14000189d`
- `ntoskrnl!DbgPrint` at `0x14000189d`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000188a`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400018c5`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400018c5`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000163f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000168e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001794`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001956`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000163f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000168e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001794`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140001956`
- `watchdog!WdLogSingleEntry0` at `0x140001628`
- `watchdog!WdLogSingleEntry0` at `0x140001677`
- `watchdog!WdLogSingleEntry0` at `0x14000177d`
- `watchdog!WdLogSingleEntry0` at `0x1400018ae`
- `watchdog!WdLogSingleEntry0` at `0x14000193f`
- `watchdog!WdLogSingleEntry0` at `0x140001628`
- `watchdog!WdLogSingleEntry0` at `0x140001677`
- `watchdog!WdLogSingleEntry0` at `0x14000177d`
- `watchdog!WdLogSingleEntry0` at `0x1400018ae`
- `watchdog!WdLogSingleEntry0` at `0x14000193f`
- `WIN32K!EngReleaseSemaphore` at `0x1400019bd`
- `WIN32K!EngReleaseSemaphore` at `0x1400019bd`
- `WIN32K!EngAcquireSemaphore` at `0x1400016e1`
- `WIN32K!EngAcquireSemaphore` at `0x1400016e1`
- `WIN32K!EngFreeMem` at `0x1400019fe`
- `WIN32K!EngFreeMem` at `0x140001a1d`
- `WIN32K!EngFreeMem` at `0x1400019fe`
- `WIN32K!EngFreeMem` at `0x140001a1d`

## string_xrefs

- `0x140001896`: `Bitmap is still in command buffer list`

## pseudocode

```c
void __fastcall CddBitmapHw::Release(CddBitmapHw *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  HSEMAPHORE v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rbx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 **v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  HSEMAPHORE v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  __int64 v23; // [rsp+20h] [rbp-78h] BYREF
  __int16 v24; // [rsp+28h] [rbp-70h]
  char v25; // [rsp+2Ah] [rbp-6Eh]
  _KAPC_STATE ApcState; // [rsp+38h] [rbp-60h] BYREF
  char v27; // [rsp+68h] [rbp-30h]

  if ( KeGetCurrentThread() == *(struct _KTHREAD **)(*((_QWORD *)this + 1) + 2568LL) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 273;
    v2 = (_QWORD *)((__int64 (*)(void))WdLogNewEntry5_WdAssertion)();
    v2[3] = gCddImageInfo;
    v2[4] = (unsigned int)dword_14003E570;
    v2[5] = 215857758;
    WdLogGlobalForLineNumber = 273;
  }
  if ( !*((_DWORD *)this + 46) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 274;
    v3 = (_QWORD *)((__int64 (*)(void))WdLogNewEntry5_WdAssertion)();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 274;
  }
  if ( (*((_DWORD *)this + 46))-- == 1 )
  {
    CddBitmap::RemoveFromCddBitmapList(this);
    *((_DWORD *)this + 32) |= 4u;
    v5 = (HSEMAPHORE)*((_QWORD *)this + 24);
    if ( v5 )
      EngAcquireSemaphore(v5);
    *((_QWORD *)this + 67) = KeGetCurrentThread();
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 1) + 7228LL));
    CDDSYNCOBJECT::DestroyDxSyncObject((CddBitmapHw *)((char *)this + 208), 0);
    v23 = *((_QWORD *)this + 1);
    v24 = 257;
    v25 = 0;
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v23 + 2888));
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(v23 + 2896));
    if ( *((_DWORD *)this + 10) )
    {
      CCommandBufferMutex::EnableWorkerThreadAccess((CCommandBufferMutex *)&v23);
      v6 = *((_QWORD *)this + 1);
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 785;
        v9 = (_QWORD *)WdLogNewEntry5_WdAssertion(v8, v7);
        v9[3] = gCddImageInfo;
        v9[4] = (unsigned int)dword_14003E570;
        v9[5] = 215857758;
        WdLogGlobalForLineNumber = 785;
      }
      v10 = *(_QWORD *)(v6 + 5488);
      ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v10);
      *(_DWORD *)(v6 + 3648) = 0;
      CddIssueCommand(v6, 13);
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v10);
      CCommandBufferMutex::DisableWorkerThreadAccess((CCommandBufferMutex *)&v23);
      CDDPDEV::RemoveLruListEntryNoLockHeld(*((CDDPDEV **)this + 1), (struct _LIST_ENTRY *)this + 5);
      CDDPDEV::DestroyAllocation(*((CDDPDEV **)this + 1), *((_DWORD *)this + 10));
      CDDPDEV::DestroySyncObject(*((CDDPDEV **)this + 1), *((_DWORD *)this + 53));
    }
    else
    {
      v11 = (__int64 *)((char *)this + 16 * *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 1) + 12696LL) + 8LL) + 96);
      v12 = *v11;
      if ( *v11 )
      {
        if ( *(__int64 **)(v12 + 8) != v11 || (v13 = (__int64 **)v11[1], *v13 != v11) )
          __fastfail(3u);
        *v13 = (__int64 *)v12;
        *(_QWORD *)(v12 + 8) = v13;
        *v11 = 0;
        v11[1] = 0;
      }
      CDDPDEV::RemoveLruListEntryNoLockHeld(*((CDDPDEV **)this + 1), (struct _LIST_ENTRY *)this + 5);
    }
    if ( (*((_QWORD *)this + 12) || *((_QWORD *)this + 14)) && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Bitmap is still in command buffer list");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 338;
      v16 = (_QWORD *)WdLogNewEntry5_WdError(v15, v14);
      v16[3] = gCddImageInfo;
      v16[4] = (unsigned int)dword_14003E570;
      v16[5] = 215857758;
      WdLogGlobalForLineNumber = 338;
      __debugbreak();
    }
    if ( (*((_DWORD *)this + 32) & 0x40) != 0 && *((_QWORD *)this + 22) )
    {
      CProcessAttachHelper::CProcessAttachHelper(&ApcState, *(PRKPROCESS *)(*((_QWORD *)this + 1) + 752LL));
      if ( ObCloseHandle(*((HANDLE *)this + 22), 0) < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 350;
        v19 = (_QWORD *)WdLogNewEntry5_WdAssertion(v18, v17);
        v19[3] = gCddImageInfo;
        v19[4] = (unsigned int)dword_14003E570;
        v19[5] = 215857758;
        WdLogGlobalForLineNumber = 350;
      }
      *((_QWORD *)this + 22) = 0;
      if ( v27 )
        KeUnstackDetachProcess(&ApcState);
    }
    CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)&v23);
    v20 = (HSEMAPHORE)*((_QWORD *)this + 24);
    *((_QWORD *)this + 67) = 0;
    if ( v20 )
      EngReleaseSemaphore(v20);
    CddBitmap::Release(this);
    v21 = (void *)*((_QWORD *)this + 147);
    if ( v21 )
    {
      ExFreePoolWithTag(v21, 0);
      *((_QWORD *)this + 147) = 0;
    }
    v22 = (void *)*((_QWORD *)this + 148);
    if ( v22 )
    {
      EngFreeMem(v22);
      *((_QWORD *)this + 148) = 0;
    }
    CddResidencyState::~CddResidencyState((CddBitmapHw *)((char *)this + 48));
    EngFreeMem(this);
  }
}

```

## disassembly

```asm
0x1400015e0  mov     [rsp+arg_8], rbx
0x1400015e5  mov     [rsp+arg_10], rbp
0x1400015ea  push    rsi
0x1400015eb  push    rdi
0x1400015ec  push    r15
0x1400015ee  sub     rsp, 80h
0x1400015f5  mov     rax, cs:__security_cookie
0x1400015fc  xor     rax, rsp
0x1400015ff  mov     [rsp+98h+var_28], rax
0x140001604  mov     rdi, rcx
0x140001607  mov     r15d, 0CDDBA5Eh
0x14000160d  mov     rcx, gs:188h
0x140001616  mov     rax, [rdi+8]
0x14000161a  cmp     rcx, [rax+0A08h]
0x140001621  jnz     short loc_14000166A
0x140001623  mov     ecx, 1
0x140001628  call    cs:__imp_WdLogSingleEntry0
0x14000162f  nop     dword ptr [rax+rax+00h]
0x140001634  mov     ebx, 111h
0x140001639  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000163f  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140001646  nop     dword ptr [rax+rax+00h]
0x14000164b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140001652  mov     [rax+18h], rcx
0x140001656  mov     ecx, cs:dword_14003E570
0x14000165c  mov     [rax+20h], rcx
0x140001660  mov     [rax+28h], r15
0x140001664  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000166a  xor     ebp, ebp
0x14000166c  cmp     [rdi+0B8h], ebp
0x140001672  ja      short loc_1400016B9
0x140001674  lea     ecx, [rbp+1]
0x140001677  call    cs:__imp_WdLogSingleEntry0
0x14000167e  nop     dword ptr [rax+rax+00h]
0x140001683  mov     ebx, 112h
0x140001688  mov     cs:WdLogGlobalForLineNumber, ebx
0x14000168e  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140001695  nop     dword ptr [rax+rax+00h]
0x14000169a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400016a1  mov     [rax+18h], rcx
0x1400016a5  mov     ecx, cs:dword_14003E570
0x1400016ab  mov     [rax+20h], rcx
0x1400016af  mov     [rax+28h], r15
0x1400016b3  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400016b9  add     dword ptr [rdi+0B8h], 0FFFFFFFFh
0x1400016c0  jnz     loc_140001A29
0x1400016c6  mov     rcx, rdi; this
0x1400016c9  call    ?RemoveFromCddBitmapList@CddBitmap@@QEAAXXZ; CddBitmap::RemoveFromCddBitmapList(void)
0x1400016ce  or      dword ptr [rdi+80h], 4
0x1400016d5  mov     rcx, [rdi+0C0h]; hsem
0x1400016dc  test    rcx, rcx
0x1400016df  jz      short loc_1400016ED
0x1400016e1  call    cs:__imp_EngAcquireSemaphore
0x1400016e8  nop     dword ptr [rax+rax+00h]
0x1400016ed  mov     rax, gs:188h
0x1400016f6  lea     rcx, [rdi+0D0h]; this
0x1400016fd  mov     [rdi+218h], rax
0x140001704  xor     edx, edx; int
0x140001706  mov     rax, [rdi+8]
0x14000170a  lock dec dword ptr [rax+1C3Ch]
0x140001711  call    ?DestroyDxSyncObject@CDDSYNCOBJECT@@QEAAXH@Z; CDDSYNCOBJECT::DestroyDxSyncObject(int)
0x140001716  mov     rbx, [rdi+8]
0x14000171a  mov     [rsp+98h+var_78], rbx
0x14000171f  mov     [rsp+98h+var_70], 101h
0x140001726  mov     [rsp+98h+var_6E], bpl
0x14000172b  mov     rcx, [rbx+0B48h]
0x140001732  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140001739  nop     dword ptr [rax+rax+00h]
0x14000173e  mov     rcx, [rbx+0B50h]
0x140001745  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14000174c  nop     dword ptr [rax+rax+00h]
0x140001751  cmp     [rdi+28h], ebp
0x140001754  jz      loc_14000182B
0x14000175a  lea     rcx, [rsp+98h+var_78]; this
0x14000175f  call    ?EnableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::EnableWorkerThreadAccess(void)
0x140001764  mov     rsi, [rdi+8]
0x140001768  call    cs:__imp_KeGetCurrentIrql
0x14000176f  nop     dword ptr [rax+rax+00h]
0x140001774  test    al, al
0x140001776  jz      short loc_1400017BF
0x140001778  mov     ecx, 1
0x14000177d  call    cs:__imp_WdLogSingleEntry0
0x140001784  nop     dword ptr [rax+rax+00h]
0x140001789  mov     ebx, 311h
0x14000178e  mov     cs:WdLogGlobalForLineNumber, ebx
0x140001794  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000179b  nop     dword ptr [rax+rax+00h]
0x1400017a0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400017a7  mov     [rax+18h], rcx
0x1400017ab  mov     ecx, cs:dword_14003E570
0x1400017b1  mov     [rax+20h], rcx
0x1400017b5  mov     [rax+28h], r15
0x1400017b9  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400017bf  mov     rbx, [rsi+1570h]
0x1400017c6  mov     rcx, rbx
0x1400017c9  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400017d0  nop     dword ptr [rax+rax+00h]
0x1400017d5  mov     edx, 0Dh
0x1400017da  mov     [rsi+0E40h], ebp
0x1400017e0  mov     rcx, rsi
0x1400017e3  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x1400017e8  mov     rcx, rbx
0x1400017eb  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400017f2  nop     dword ptr [rax+rax+00h]
0x1400017f7  lea     rcx, [rsp+98h+var_78]; this
0x1400017fc  call    ?DisableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ; CCommandBufferMutex::DisableWorkerThreadAccess(void)
0x140001801  mov     rcx, [rdi+8]; this
0x140001805  lea     rdx, [rdi+50h]; struct _LIST_ENTRY *
0x140001809  call    ?RemoveLruListEntryNoLockHeld@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z; CDDPDEV::RemoveLruListEntryNoLockHeld(_LIST_ENTRY *)
0x14000180e  mov     edx, [rdi+28h]; unsigned int
0x140001811  mov     rcx, [rdi+8]; this
0x140001815  call    ?DestroyAllocation@CDDPDEV@@QEAAJI@Z; CDDPDEV::DestroyAllocation(uint)
0x14000181a  mov     edx, [rdi+0D4h]; unsigned int
0x140001820  mov     rcx, [rdi+8]; this
0x140001824  call    ?DestroySyncObject@CDDPDEV@@QEAAJI@Z; CDDPDEV::DestroySyncObject(uint)
0x140001829  jmp     short loc_14000187E
0x14000182b  mov     rax, [rdi+8]
0x14000182f  mov     rcx, [rax+3198h]
0x140001836  mov     ecx, [rcx+8]
0x140001839  add     rcx, 6
0x14000183d  shl     rcx, 4
0x140001841  add     rcx, rdi
0x140001844  mov     rax, [rcx]
0x140001847  test    rax, rax
0x14000184a  jz      short loc_140001871
0x14000184c  cmp     [rax+8], rcx
0x140001850  jnz     loc_140001A4F
0x140001856  mov     rdx, [rcx+8]
0x14000185a  cmp     [rdx], rcx
0x14000185d  jnz     loc_140001A4F
0x140001863  mov     [rdx], rax
0x140001866  mov     [rax+8], rdx
0x14000186a  mov     [rcx], rbp
0x14000186d  mov     [rcx+8], rbp
0x140001871  mov     rcx, [rdi+8]; this
0x140001875  lea     rdx, [rdi+50h]; struct _LIST_ENTRY *
0x140001879  call    ?RemoveLruListEntryNoLockHeld@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z; CDDPDEV::RemoveLruListEntryNoLockHeld(_LIST_ENTRY *)
0x14000187e  cmp     [rdi+60h], rbp
0x140001882  jnz     short loc_14000188A
0x140001884  cmp     [rdi+70h], rbp
0x140001888  jz      short loc_1400018F1
0x14000188a  mov     rax, cs:KdDebuggerEnabled
0x140001891  cmp     [rax], bpl
0x140001894  jz      short loc_1400018F1
0x140001896  lea     rcx, aBitmapIsStillI; "Bitmap is still in command buffer list"
0x14000189d  call    cs:__imp_DbgPrint
0x1400018a4  nop     dword ptr [rax+rax+00h]
0x1400018a9  mov     ecx, 2
0x1400018ae  call    cs:__imp_WdLogSingleEntry0
0x1400018b5  nop     dword ptr [rax+rax+00h]
0x1400018ba  mov     ebx, 152h
0x1400018bf  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400018c5  call    cs:__imp_WdLogNewEntry5_WdError
0x1400018cc  nop     dword ptr [rax+rax+00h]
0x1400018d1  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400018d8  mov     [rax+18h], rcx
0x1400018dc  mov     ecx, cs:dword_14003E570
0x1400018e2  mov     [rax+20h], rcx
0x1400018e6  mov     [rax+28h], r15
0x1400018ea  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400018f0  int     3; Trap to Debugger
0x1400018f1  mov     eax, [rdi+80h]
0x1400018f7  test    al, 40h
0x1400018f9  jz      loc_1400019A0
0x1400018ff  cmp     [rdi+0B0h], rbp
0x140001906  jz      loc_1400019A0
0x14000190c  mov     rdx, [rdi+8]
0x140001910  lea     rcx, [rsp+98h+ApcState]; ApcState
0x140001915  mov     rdx, [rdx+2F0h]; PROCESS
0x14000191c  call    ??0CProcessAttachHelper@@QEAA@PEAU_EPROCESS@@@Z; CProcessAttachHelper::CProcessAttachHelper(_EPROCESS *)
0x140001921  mov     rcx, [rdi+0B0h]; Handle
0x140001928  xor     edx, edx; PreviousMode
0x14000192a  call    cs:__imp_ObCloseHandle
0x140001931  nop     dword ptr [rax+rax+00h]
0x140001936  test    eax, eax
0x140001938  jns     short loc_140001981
0x14000193a  mov     ecx, 1
0x14000193f  call    cs:__imp_WdLogSingleEntry0
0x140001946  nop     dword ptr [rax+rax+00h]
0x14000194b  mov     ebx, 15Eh
0x140001950  mov     cs:WdLogGlobalForLineNumber, ebx
0x140001956  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000195d  nop     dword ptr [rax+rax+00h]
0x140001962  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140001969  mov     [rax+18h], rcx
0x14000196d  mov     ecx, cs:dword_14003E570
0x140001973  mov     [rax+20h], rcx
0x140001977  mov     [rax+28h], r15
0x14000197b  mov     cs:WdLogGlobalForLineNumber, ebx
0x140001981  mov     [rdi+0B0h], rbp
0x140001988  cmp     [rsp+98h+var_30], bpl
0x14000198d  jz      short loc_1400019A0
0x14000198f  lea     rcx, [rsp+98h+ApcState]; ApcState
0x140001994  call    cs:__imp_KeUnstackDetachProcess
0x14000199b  nop     dword ptr [rax+rax+00h]
0x1400019a0  lea     rcx, [rsp+98h+var_78]; this
0x1400019a5  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x1400019aa  mov     rcx, [rdi+0C0h]; hsem
0x1400019b1  mov     [rdi+218h], rbp
0x1400019b8  test    rcx, rcx
0x1400019bb  jz      short loc_1400019C9
0x1400019bd  call    cs:__imp_EngReleaseSemaphore
0x1400019c4  nop     dword ptr [rax+rax+00h]
0x1400019c9  mov     rcx, rdi; this
0x1400019cc  call    ?Release@CddBitmap@@UEAAXXZ; CddBitmap::Release(void)
0x1400019d1  mov     rcx, [rdi+498h]; P
0x1400019d8  test    rcx, rcx
0x1400019db  jz      short loc_1400019F2
0x1400019dd  xor     edx, edx; Tag
0x1400019df  call    cs:__imp_ExFreePoolWithTag
0x1400019e6  nop     dword ptr [rax+rax+00h]
0x1400019eb  mov     [rdi+498h], rbp
0x1400019f2  mov     rcx, [rdi+4A0h]; pv
0x1400019f9  test    rcx, rcx
0x1400019fc  jz      short loc_140001A11
0x1400019fe  call    cs:__imp_EngFreeMem
0x140001a05  nop     dword ptr [rax+rax+00h]
0x140001a0a  mov     [rdi+4A0h], rbp
0x140001a11  lea     rcx, [rdi+30h]; this
0x140001a15  call    ??1CddResidencyState@@QEAA@XZ; CddResidencyState::~CddResidencyState(void)
0x140001a1a  mov     rcx, rdi; pv
0x140001a1d  call    cs:__imp_EngFreeMem
0x140001a24  nop     dword ptr [rax+rax+00h]
0x140001a29  mov     rcx, [rsp+98h+var_28]
0x140001a2e  xor     rcx, rsp; StackCookie
0x140001a31  call    __security_check_cookie
0x140001a36  lea     r11, [rsp+98h+var_18]
0x140001a3e  mov     rbx, [r11+28h]
0x140001a42  mov     rbp, [r11+30h]
0x140001a46  mov     rsp, r11
0x140001a49  pop     r15
0x140001a4b  pop     rdi
0x140001a4c  pop     rsi
0x140001a4d  retn
0x140001a4f  mov     ecx, 3
0x140001a54  int     29h; Win8: RtlFailFast(ecx)
```
