# CddBitmapSw::Release(void)

- ea: `0x140032000`
- end: `0x1400324b3`
- name: `?Release@CddBitmapSw@@UEAAXXZ`
- size: `1203`
- prototype: `void __fastcall(CddBitmapSw *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400011f0`
- `0x140001cb4`
- `0x140002020`
- `0x14000229c`
- `0x140002470`
- `0x140006a30`
- `0x14000fbb4`
- `0x14001f494`
- `0x140022b9c`
- `0x140031cf4`
- `0x140032000`
- `0x1400371f0`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140032392`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140032392`
- `ntoskrnl!ObCloseHandle` at `0x14003232c`
- `ntoskrnl!ObCloseHandle` at `0x14003232c`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400323cb`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400323cb`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1400323e7`
- `ntoskrnl!MmUnmapViewOfSection` at `0x1400323e7`
- `ntoskrnl!ObfDereferenceObject` at `0x140032408`
- `ntoskrnl!ObfDereferenceObject` at `0x140032408`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400321dd`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14003227b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400322d4`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400321dd`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14003227b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400322d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032450`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032450`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400321f5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400321f5`
- `ntoskrnl!DbgPrint` at `0x140032106`
- `ntoskrnl!DbgPrint` at `0x140032106`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400320f3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003212b`
- `watchdog!WdLogNewEntry5_WdError` at `0x14003212b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14003206b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400320bf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14003221e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140032356`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14003206b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400320bf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14003221e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140032356`
- `watchdog!WdLogSingleEntry0` at `0x140032054`
- `watchdog!WdLogSingleEntry0` at `0x1400320a9`
- `watchdog!WdLogSingleEntry0` at `0x140032115`
- `watchdog!WdLogSingleEntry0` at `0x140032208`
- `watchdog!WdLogSingleEntry0` at `0x14003233f`
- `watchdog!WdLogSingleEntry0` at `0x140032054`
- `watchdog!WdLogSingleEntry0` at `0x1400320a9`
- `watchdog!WdLogSingleEntry0` at `0x140032115`
- `watchdog!WdLogSingleEntry0` at `0x140032208`
- `watchdog!WdLogSingleEntry0` at `0x14003233f`
- `WIN32K!EngAcquireSemaphore` at `0x140032187`
- `WIN32K!EngAcquireSemaphore` at `0x140032187`
- `WIN32K!EngDeleteSurface` at `0x14003242f`
- `WIN32K!EngDeleteSurface` at `0x14003242f`
- `WIN32K!EngFreeMem` at `0x14003247e`
- `WIN32K!EngFreeMem` at `0x14003247e`

## string_xrefs

- `0x1400320ff`: `CddBitmapSw::Release is called after the bitmap was deleted`

## pseudocode

```c
void __fastcall CddBitmapSw::Release(CddBitmapSw *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  int v6; // r8d
  HSEMAPHORE v7; // rcx
  char *v8; // rdi
  int v9; // esi
  __int64 v10; // rsi
  int v11; // r8d
  _QWORD *v12; // rax
  int v13; // r8d
  __int64 v14; // rcx
  char **v15; // rax
  unsigned int v16; // edx
  int v17; // eax
  _QWORD *v18; // rax
  HSURF v19; // rcx
  void *v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-39h] BYREF
  int v22; // [rsp+28h] [rbp-31h]
  __int64 v23; // [rsp+30h] [rbp-29h] BYREF
  CddBitmapSw *v24; // [rsp+38h] [rbp-21h]
  struct _KAPC_STATE ApcState; // [rsp+48h] [rbp-11h] BYREF
  char v26; // [rsp+78h] [rbp+1Fh]

  if ( KeGetCurrentThread() == *(struct _KTHREAD **)(*((_QWORD *)this + 1) + 2568LL) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 40;
    v2 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v2[3] = gCddImageInfo;
    v2[4] = (unsigned int)dword_14003E570;
    v2[5] = 215857758;
    WdLogGlobalForLineNumber = 40;
  }
  if ( !*((_DWORD *)this + 46) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 41;
    v3 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 41;
    if ( !*((_DWORD *)this + 46) )
    {
      if ( (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("CddBitmapSw::Release is called after the bitmap was deleted");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 42;
        v4 = (_QWORD *)WdLogNewEntry5_WdError();
        v4[3] = gCddImageInfo;
        v4[4] = (unsigned int)dword_14003E570;
        v4[5] = 215857758;
        WdLogGlobalForLineNumber = 42;
        __debugbreak();
      }
    }
  }
  if ( (*((_DWORD *)this + 46))-- == 1 )
  {
    CddBitmap::RemoveFromCddBitmapList(this);
    *((_DWORD *)this + 32) |= 4u;
    v7 = (HSEMAPHORE)*((_QWORD *)this + 24);
    v24 = this;
    LODWORD(v23) = 1;
    if ( v7 )
      EngAcquireSemaphore(v7);
    *((_QWORD *)this + 67) = KeGetCurrentThread();
    CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v21, *(struct CDDMUTEX **)(*((_QWORD *)this + 1) + 7200LL), v6);
    v8 = (char *)this + 872;
    if ( *((_QWORD *)this + 109) || (v9 = 0, *((_BYTE *)this + 569)) )
      v9 = 1;
    if ( v22 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v21);
    if ( v9 )
    {
      v10 = *((_QWORD *)this + 1);
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 785;
        v12 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v12[3] = gCddImageInfo;
        v12[4] = (unsigned int)dword_14003E570;
        v12[5] = 215857758;
        WdLogGlobalForLineNumber = 785;
      }
      CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v21, *(struct CDDMUTEX **)(v10 + 5488), v11);
      *(_DWORD *)(v10 + 3648) = 0;
      CddIssueCommand(v10, 13);
      if ( v22 )
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v21);
    }
    CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)&v23);
    if ( *(_QWORD *)v8 )
    {
      CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v23, *(struct CDDMUTEX **)(*((_QWORD *)this + 1) + 7200LL), v13);
      v14 = *(_QWORD *)v8;
      if ( *(char **)(*(_QWORD *)v8 + 8LL) != v8 || (v15 = (char **)*((_QWORD *)this + 110), *v15 != v8) )
        __fastfail(3u);
      *v15 = (char *)v14;
      *(_QWORD *)(v14 + 8) = v15;
      if ( (_DWORD)v24 )
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v23);
    }
    v16 = *((_DWORD *)this + 10);
    if ( v16 )
      CDDPDEV::DestroyAllocation(*((CDDPDEV **)this + 1), v16);
    v17 = *((_DWORD *)this + 32);
    *((_DWORD *)this + 10) = 0;
    if ( (v17 & 0x40) != 0 && *((_QWORD *)this + 22) )
    {
      CProcessAttachHelper::CProcessAttachHelper(&ApcState, *(PRKPROCESS *)(*((_QWORD *)this + 1) + 752LL));
      if ( ObCloseHandle(*((HANDLE *)this + 22), 0) < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 97;
        v18 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v18[3] = gCddImageInfo;
        v18[4] = (unsigned int)dword_14003E570;
        v18[5] = 215857758;
        WdLogGlobalForLineNumber = 97;
      }
      *((_QWORD *)this + 22) = 0;
      if ( v26 )
        KeUnstackDetachProcess(&ApcState);
    }
    CddBitmap::Release(this);
    if ( *((_QWORD *)this + 111) )
    {
      if ( *((_QWORD *)this + 113) )
      {
        if ( (unsigned int)IsSurfaceMappingEnabled() )
          MmUnmapViewInSystemSpace(*((PVOID *)this + 112));
        else
          MmUnmapViewOfSection(*((_QWORD *)this + 113), *((_QWORD *)this + 112));
        *((_QWORD *)this + 112) = 0;
        *((_QWORD *)this + 113) = 0;
      }
      ObfDereferenceObject(*((PVOID *)this + 111));
      *((_QWORD *)this + 111) = 0;
    }
    CddBitmapSw::UnlockSurfObj(this);
    v19 = (HSURF)*((_QWORD *)this + 117);
    if ( v19 )
    {
      EngDeleteSurface(v19);
      *((_QWORD *)this + 117) = 0;
    }
    v20 = (void *)*((_QWORD *)this + 108);
    if ( v20 )
    {
      ExFreePoolWithTag(v20, 0);
      *((_QWORD *)this + 108) = 0;
    }
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 1) + 7228LL));
    *((_QWORD *)this + 1) = 0;
    CddResidencyState::~CddResidencyState((CddBitmapSw *)((char *)this + 48));
    EngFreeMem(this);
  }
}

```

## disassembly

```asm
0x140032000  mov     [rsp-8+arg_8], rbx
0x140032005  mov     [rsp-8+arg_10], rsi
0x14003200a  push    rbp
0x14003200b  push    rdi
0x14003200c  push    r12
0x14003200e  push    r13
0x140032010  push    r15
0x140032012  lea     rbp, [rsp-37h]
0x140032017  sub     rsp, 90h
0x14003201e  mov     rax, cs:__security_cookie
0x140032025  xor     rax, rsp
0x140032028  mov     [rbp+57h+var_30], rax
0x14003202c  mov     rbx, rcx
0x14003202f  mov     r12d, 1
0x140032035  mov     rcx, gs:188h
0x14003203e  mov     r13d, 0CDDBA5Eh
0x140032044  mov     rax, [rbx+8]
0x140032048  cmp     rcx, [rax+0A08h]
0x14003204f  jnz     short loc_140032096
0x140032051  mov     ecx, r12d
0x140032054  call    cs:__imp_WdLogSingleEntry0
0x14003205b  nop     dword ptr [rax+rax+00h]
0x140032060  lea     edi, [r12+27h]
0x140032065  mov     cs:WdLogGlobalForLineNumber, edi
0x14003206b  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140032072  nop     dword ptr [rax+rax+00h]
0x140032077  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14003207e  mov     [rax+18h], rcx
0x140032082  mov     ecx, cs:dword_14003E570
0x140032088  mov     [rax+20h], rcx
0x14003208c  mov     [rax+28h], r13
0x140032090  mov     cs:WdLogGlobalForLineNumber, edi
0x140032096  xor     r15d, r15d
0x140032099  cmp     [rbx+0B8h], r15d
0x1400320a0  ja      loc_140032157
0x1400320a6  mov     ecx, r12d
0x1400320a9  call    cs:__imp_WdLogSingleEntry0
0x1400320b0  nop     dword ptr [rax+rax+00h]
0x1400320b5  lea     edi, [r15+29h]
0x1400320b9  mov     cs:WdLogGlobalForLineNumber, edi
0x1400320bf  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400320c6  nop     dword ptr [rax+rax+00h]
0x1400320cb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400320d2  mov     [rax+18h], rcx
0x1400320d6  mov     ecx, cs:dword_14003E570
0x1400320dc  mov     [rax+20h], rcx
0x1400320e0  mov     [rax+28h], r13
0x1400320e4  mov     cs:WdLogGlobalForLineNumber, edi
0x1400320ea  cmp     [rbx+0B8h], r15d
0x1400320f1  ja      short loc_140032157
0x1400320f3  mov     rax, cs:KdDebuggerEnabled
0x1400320fa  cmp     [rax], r15b
0x1400320fd  jz      short loc_140032157
0x1400320ff  lea     rcx, aCddbitmapswRel; "CddBitmapSw::Release is called after th"...
0x140032106  call    cs:__imp_DbgPrint
0x14003210d  nop     dword ptr [rax+rax+00h]
0x140032112  lea     ecx, [rdi-27h]
0x140032115  call    cs:__imp_WdLogSingleEntry0
0x14003211c  nop     dword ptr [rax+rax+00h]
0x140032121  lea     edi, [r15+2Ah]
0x140032125  mov     cs:WdLogGlobalForLineNumber, edi
0x14003212b  call    cs:__imp_WdLogNewEntry5_WdError
0x140032132  nop     dword ptr [rax+rax+00h]
0x140032137  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14003213e  mov     [rax+18h], rcx
0x140032142  mov     ecx, cs:dword_14003E570
0x140032148  mov     [rax+20h], rcx
0x14003214c  mov     [rax+28h], r13
0x140032150  mov     cs:WdLogGlobalForLineNumber, edi
0x140032156  int     3; Trap to Debugger
0x140032157  add     dword ptr [rbx+0B8h], 0FFFFFFFFh
0x14003215e  jnz     loc_14003248A
0x140032164  mov     rcx, rbx; this
0x140032167  call    ?RemoveFromCddBitmapList@CddBitmap@@QEAAXXZ; CddBitmap::RemoveFromCddBitmapList(void)
0x14003216c  or      dword ptr [rbx+80h], 4
0x140032173  mov     rcx, [rbx+0C0h]; hsem
0x14003217a  mov     [rbp+57h+var_78], rbx
0x14003217e  mov     dword ptr [rbp+57h+var_80], r12d
0x140032182  test    rcx, rcx
0x140032185  jz      short loc_140032193
0x140032187  call    cs:__imp_EngAcquireSemaphore
0x14003218e  nop     dword ptr [rax+rax+00h]
0x140032193  mov     rax, gs:188h
0x14003219c  lea     rcx, [rbp+57h+var_90]; this
0x1400321a0  mov     [rbx+218h], rax
0x1400321a7  mov     rdx, [rbx+8]
0x1400321ab  mov     rdx, [rdx+1C20h]; struct CDDMUTEX *
0x1400321b2  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x1400321b7  lea     rdi, [rbx+368h]
0x1400321be  cmp     [rdi], r15
0x1400321c1  jnz     short loc_1400321D0
0x1400321c3  mov     al, [rbx+239h]
0x1400321c9  mov     esi, r15d
0x1400321cc  test    al, al
0x1400321ce  jz      short loc_1400321D3
0x1400321d0  mov     esi, r12d
0x1400321d3  cmp     [rbp+57h+var_88], r15d
0x1400321d7  jz      short loc_1400321E9
0x1400321d9  mov     rcx, [rbp+57h+var_90]
0x1400321dd  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400321e4  nop     dword ptr [rax+rax+00h]
0x1400321e9  test    esi, esi
0x1400321eb  jz      loc_140032287
0x1400321f1  mov     rsi, [rbx+8]
0x1400321f5  call    cs:__imp_KeGetCurrentIrql
0x1400321fc  nop     dword ptr [rax+rax+00h]
0x140032201  test    al, al
0x140032203  jz      short loc_14003224D
0x140032205  mov     ecx, r12d
0x140032208  call    cs:__imp_WdLogSingleEntry0
0x14003220f  nop     dword ptr [rax+rax+00h]
0x140032214  mov     cs:WdLogGlobalForLineNumber, 311h
0x14003221e  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140032225  nop     dword ptr [rax+rax+00h]
0x14003222a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140032231  mov     [rax+18h], rcx
0x140032235  mov     ecx, cs:dword_14003E570
0x14003223b  mov     [rax+20h], rcx
0x14003223f  mov     [rax+28h], r13
0x140032243  mov     cs:WdLogGlobalForLineNumber, 311h
0x14003224d  mov     rdx, [rsi+1570h]; struct CDDMUTEX *
0x140032254  lea     rcx, [rbp+57h+var_90]; this
0x140032258  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x14003225d  mov     edx, 0Dh
0x140032262  mov     [rsi+0E40h], r15d
0x140032269  mov     rcx, rsi
0x14003226c  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x140032271  cmp     [rbp+57h+var_88], r15d
0x140032275  jz      short loc_140032287
0x140032277  mov     rcx, [rbp+57h+var_90]
0x14003227b  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140032282  nop     dword ptr [rax+rax+00h]
0x140032287  lea     rcx, [rbp+57h+var_80]; this
0x14003228b  call    ??1CDDBITMAPLOCK@@QEAA@XZ; CDDBITMAPLOCK::~CDDBITMAPLOCK(void)
0x140032290  cmp     [rdi], r15
0x140032293  jz      short loc_1400322E0
0x140032295  mov     rdx, [rbx+8]
0x140032299  lea     rcx, [rbp+57h+var_80]; this
0x14003229d  mov     rdx, [rdx+1C20h]; struct CDDMUTEX *
0x1400322a4  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x1400322a9  mov     rcx, [rdi]
0x1400322ac  cmp     [rcx+8], rdi
0x1400322b0  jnz     loc_1400323D9
0x1400322b6  mov     rax, [rdi+8]
0x1400322ba  cmp     [rax], rdi
0x1400322bd  jnz     loc_1400323D9
0x1400322c3  mov     [rax], rcx
0x1400322c6  mov     [rcx+8], rax
0x1400322ca  cmp     dword ptr [rbp+57h+var_78], r15d
0x1400322ce  jz      short loc_1400322E0
0x1400322d0  mov     rcx, [rbp+57h+var_80]
0x1400322d4  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400322db  nop     dword ptr [rax+rax+00h]
0x1400322e0  mov     edx, [rbx+28h]; unsigned int
0x1400322e3  test    edx, edx
0x1400322e5  jz      short loc_1400322F0
0x1400322e7  mov     rcx, [rbx+8]; this
0x1400322eb  call    ?DestroyAllocation@CDDPDEV@@QEAAJI@Z; CDDPDEV::DestroyAllocation(uint)
0x1400322f0  mov     eax, [rbx+80h]
0x1400322f6  mov     [rbx+28h], r15d
0x1400322fa  test    al, 40h
0x1400322fc  jz      loc_14003239E
0x140032302  cmp     [rbx+0B0h], r15
0x140032309  jz      loc_14003239E
0x14003230f  mov     rdx, [rbx+8]
0x140032313  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140032317  mov     rdx, [rdx+2F0h]; PROCESS
0x14003231e  call    ??0CProcessAttachHelper@@QEAA@PEAU_EPROCESS@@@Z; CProcessAttachHelper::CProcessAttachHelper(_EPROCESS *)
0x140032323  mov     rcx, [rbx+0B0h]; Handle
0x14003232a  xor     edx, edx; PreviousMode
0x14003232c  call    cs:__imp_ObCloseHandle
0x140032333  nop     dword ptr [rax+rax+00h]
0x140032338  test    eax, eax
0x14003233a  jns     short loc_140032381
0x14003233c  mov     ecx, r12d
0x14003233f  call    cs:__imp_WdLogSingleEntry0
0x140032346  nop     dword ptr [rax+rax+00h]
0x14003234b  mov     edi, 61h ; 'a'
0x140032350  mov     cs:WdLogGlobalForLineNumber, edi
0x140032356  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14003235d  nop     dword ptr [rax+rax+00h]
0x140032362  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140032369  mov     [rax+18h], rcx
0x14003236d  mov     ecx, cs:dword_14003E570
0x140032373  mov     [rax+20h], rcx
0x140032377  mov     [rax+28h], r13
0x14003237b  mov     cs:WdLogGlobalForLineNumber, edi
0x140032381  mov     [rbx+0B0h], r15
0x140032388  cmp     [rbp+57h+var_38], r15b
0x14003238c  jz      short loc_14003239E
0x14003238e  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140032392  call    cs:__imp_KeUnstackDetachProcess
0x140032399  nop     dword ptr [rax+rax+00h]
0x14003239e  mov     rcx, rbx; this
0x1400323a1  call    ?Release@CddBitmap@@UEAAXXZ; CddBitmap::Release(void)
0x1400323a6  cmp     [rbx+378h], r15
0x1400323ad  jz      short loc_14003241B
0x1400323af  cmp     [rbx+388h], r15
0x1400323b6  jz      short loc_140032401
0x1400323b8  call    ?IsSurfaceMappingEnabled@@YAHXZ; IsSurfaceMappingEnabled(void)
0x1400323bd  mov     rdx, [rbx+380h]
0x1400323c4  test    eax, eax
0x1400323c6  jz      short loc_1400323E0
0x1400323c8  mov     rcx, rdx; MappedBase
0x1400323cb  call    cs:__imp_MmUnmapViewInSystemSpace
0x1400323d2  nop     dword ptr [rax+rax+00h]
0x1400323d7  jmp     short loc_1400323F3
0x1400323d9  mov     ecx, 3
0x1400323de  int     29h; Win8: RtlFailFast(ecx)
0x1400323e0  mov     rcx, [rbx+388h]
0x1400323e7  call    cs:__imp_MmUnmapViewOfSection
0x1400323ee  nop     dword ptr [rax+rax+00h]
0x1400323f3  mov     [rbx+380h], r15
0x1400323fa  mov     [rbx+388h], r15
0x140032401  mov     rcx, [rbx+378h]; Object
0x140032408  call    cs:__imp_ObfDereferenceObject
0x14003240f  nop     dword ptr [rax+rax+00h]
0x140032414  mov     [rbx+378h], r15
0x14003241b  mov     rcx, rbx; this
0x14003241e  call    ?UnlockSurfObj@CddBitmapSw@@IEAAXXZ; CddBitmapSw::UnlockSurfObj(void)
0x140032423  mov     rcx, [rbx+3A8h]; hsurf
0x14003242a  test    rcx, rcx
0x14003242d  jz      short loc_140032442
0x14003242f  call    cs:__imp_EngDeleteSurface
0x140032436  nop     dword ptr [rax+rax+00h]
0x14003243b  mov     [rbx+3A8h], r15
0x140032442  mov     rcx, [rbx+360h]; P
0x140032449  test    rcx, rcx
0x14003244c  jz      short loc_140032463
0x14003244e  xor     edx, edx; Tag
0x140032450  call    cs:__imp_ExFreePoolWithTag
0x140032457  nop     dword ptr [rax+rax+00h]
0x14003245c  mov     [rbx+360h], r15
0x140032463  mov     rax, [rbx+8]
0x140032467  lea     rcx, [rbx+30h]; this
0x14003246b  lock dec dword ptr [rax+1C3Ch]
0x140032472  mov     [rbx+8], r15
0x140032476  call    ??1CddResidencyState@@QEAA@XZ; CddResidencyState::~CddResidencyState(void)
0x14003247b  mov     rcx, rbx; pv
0x14003247e  call    cs:__imp_EngFreeMem
0x140032485  nop     dword ptr [rax+rax+00h]
0x14003248a  mov     rcx, [rbp+57h+var_30]
0x14003248e  xor     rcx, rsp; StackCookie
0x140032491  call    __security_check_cookie
0x140032496  lea     r11, [rsp+0B0h+var_20]
0x14003249e  mov     rbx, [r11+38h]
0x1400324a2  mov     rsi, [r11+40h]
0x1400324a6  mov     rsp, r11
0x1400324a9  pop     r15
0x1400324ab  pop     r13
0x1400324ad  pop     r12
0x1400324af  pop     rdi
0x1400324b0  pop     rbp
0x1400324b1  retn
```
