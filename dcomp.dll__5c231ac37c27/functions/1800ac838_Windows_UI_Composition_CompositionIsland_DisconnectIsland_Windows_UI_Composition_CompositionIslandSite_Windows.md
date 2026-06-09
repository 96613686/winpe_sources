# Windows::UI::Composition::CompositionIsland::DisconnectIsland(Windows::UI::Composition::CompositionIslandSite *,Windows::UI::Composition::CompositionIsland *)

- ea: `0x1800ac838`
- end: `0x1800ac98a`
- name: `?DisconnectIsland@CompositionIsland@Composition@UI@Windows@@SAJPEAVCompositionIslandSite@234@PEAV1234@@Z`
- size: `338`
- prototype: `static int(struct Windows::UI::Composition::CompositionIslandSite *, struct Windows::UI::Composition::CompositionIsland *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180081110`
- `0x1800ac640`
- `0x18011bfe0`

## callees

- `0x18000c924`
- `0x180073388`
- `0x1800ac838`
- `0x1800acd48`
- `0x1800ad1c4`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ac85c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ac85c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ac915`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ac915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ac862`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ac862`

## string_xrefs

- `0x1800ac96b`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositionisland.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionIsland::DisconnectIsland(
        struct Windows::UI::Composition::CompositionIslandSite *a1,
        struct Windows::UI::Composition::CompositionIsland *a2)
{
  struct IUnknown *v4; // rdx
  Microsoft::WRL2::ContextSession *v5; // rcx
  struct IUnknown *v6; // rdx
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = &Windows::UI::Composition::CompositionIsland::s_sharedLock;
  AcquireSRWLockExclusive(&Windows::UI::Composition::CompositionIsland::s_sharedLock);
  dword_1801E1448 = GetCurrentThreadId();
  if ( __PAIR128__(*((_QWORD *)a1 + 25), *((_QWORD *)a2 + 29)) == __PAIR128__(
                                                                    (unsigned __int64)a2,
                                                                    (unsigned __int64)a1) )
  {
    (*(void (__fastcall **)(struct Windows::UI::Composition::CompositionIslandSite *))(*(_QWORD *)a1 + 280LL))(a1);
    *((_BYTE *)a2 + 204) = 0;
    *((_DWORD *)a2 + 50) = 0;
    *((_DWORD *)a1 + 49) = 0;
    *((_QWORD *)a2 + 30) = 0;
    *((_QWORD *)a1 + 26) = 0;
    v4 = (struct IUnknown *)*((_QWORD *)a2 + 29);
    *((_QWORD *)a2 + 29) = 0;
    Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(
      *((Microsoft::WRL2::ContextSession **)a2 + 3),
      v4);
    *((_QWORD *)a1 + 25) = 0;
    ++*((_DWORD *)a2 + 115);
    *((_QWORD *)a2 + 56) = 0;
    ++*((_DWORD *)a1 + 58);
    dword_1801E1448 = 0;
    ReleaseSRWLockExclusive(&Windows::UI::Composition::CompositionIsland::s_sharedLock);
    Windows::UI::Composition::CompositionIsland::SetIsContentVisible(a2, 0);
    v5 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)a2 + 3);
    v6 = (struct IUnknown *)*((_QWORD *)a2 + 61);
    *((_QWORD *)a2 + 61) = 0;
    Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(v5, v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3B4,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositionisland.cpp",
      (const char *)0x8007139FLL,
      (int)"Objects not connected to each other.",
      v8);
    CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(&v10);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x1800ac838  mov     [rsp+arg_8], rbx
0x1800ac83d  mov     [rsp+arg_10], rbp
0x1800ac842  push    rdi
0x1800ac843  sub     rsp, 30h
0x1800ac847  lea     rbp, ?s_sharedLock@CompositionIsland@Composition@UI@Windows@@2VCReadWriteLock@@A; CReadWriteLock Windows::UI::Composition::CompositionIsland::s_sharedLock
0x1800ac84e  mov     rdi, rcx
0x1800ac851  mov     rcx, rbp; SRWLock
0x1800ac854  mov     [rsp+38h+arg_0], rbp
0x1800ac859  mov     rbx, rdx
0x1800ac85c  call    cs:__imp_AcquireSRWLockExclusive
0x1800ac862  call    cs:__imp_GetCurrentThreadId
0x1800ac868  mov     cs:dword_1801E1448, eax
0x1800ac86e  cmp     [rbx+0E8h], rdi
0x1800ac875  jnz     loc_1800AC952
0x1800ac87b  cmp     [rdi+0C8h], rbx
0x1800ac882  jnz     loc_1800AC952
0x1800ac888  mov     rax, [rdi]
0x1800ac88b  mov     rcx, rdi
0x1800ac88e  mov     rax, [rax+118h]
0x1800ac895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac89a  mov     byte ptr [rbx+0CCh], 0
0x1800ac8a1  mov     dword ptr [rbx+0C8h], 0
0x1800ac8ab  mov     dword ptr [rdi+0C4h], 0
0x1800ac8b5  mov     qword ptr [rbx+0F0h], 0
0x1800ac8c0  mov     qword ptr [rdi+0D0h], 0
0x1800ac8cb  mov     rdx, [rbx+0E8h]; struct IUnknown *
0x1800ac8d2  mov     qword ptr [rbx+0E8h], 0
0x1800ac8dd  mov     rcx, [rbx+18h]; this
0x1800ac8e1  call    ?EnqueueReleaseAndPassOwnershipWorker@ContextSession@WRL2@Microsoft@@AEAAXPEAUIUnknown@@@Z; Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(IUnknown *)
0x1800ac8e6  mov     qword ptr [rdi+0C8h], 0
0x1800ac8f1  mov     rcx, rbp; SRWLock
0x1800ac8f4  inc     dword ptr [rbx+1CCh]
0x1800ac8fa  mov     qword ptr [rbx+1C0h], 0
0x1800ac905  inc     dword ptr [rdi+0E8h]
0x1800ac90b  mov     cs:dword_1801E1448, 0
0x1800ac915  call    cs:__imp_ReleaseSRWLockExclusive
0x1800ac91b  xor     edx, edx; bool
0x1800ac91d  mov     rcx, rbx; this
0x1800ac920  call    ?SetIsContentVisible@CompositionIsland@Composition@UI@Windows@@QEAAX_N@Z; Windows::UI::Composition::CompositionIsland::SetIsContentVisible(bool)
0x1800ac925  mov     rcx, [rbx+18h]; this
0x1800ac929  mov     rdx, [rbx+1E8h]; struct IUnknown *
0x1800ac930  mov     qword ptr [rbx+1E8h], 0
0x1800ac93b  call    ?EnqueueReleaseAndPassOwnershipWorker@ContextSession@WRL2@Microsoft@@AEAAXPEAUIUnknown@@@Z; Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(IUnknown *)
0x1800ac940  xor     eax, eax
0x1800ac942  mov     rbx, [rsp+38h+arg_8]
0x1800ac947  mov     rbp, [rsp+38h+arg_10]
0x1800ac94c  add     rsp, 30h
0x1800ac950  pop     rdi
0x1800ac951  retn
0x1800ac952  mov     rcx, [rsp+38h]; this
0x1800ac957  lea     rax, aObjectsNotConn; "Objects not connected to each other."
0x1800ac95e  mov     ebx, 8007139Fh
0x1800ac963  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800ac968  mov     r9d, ebx; char *
0x1800ac96b  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800ac972  mov     edx, 3B4h; void *
0x1800ac977  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800ac97c  lea     rcx, [rsp+38h+arg_0]
0x1800ac981  call    ??1?$CWriteGuard@VCReadWriteLock@@@@QEAA@XZ; CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(void)
0x1800ac986  mov     eax, ebx
0x1800ac988  jmp     short loc_1800AC942
```
