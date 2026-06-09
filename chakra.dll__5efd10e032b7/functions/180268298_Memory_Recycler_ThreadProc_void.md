# Memory::Recycler::ThreadProc(void)

- ea: `0x180268298`
- end: `0x180268425`
- name: `?ThreadProc@Recycler@Memory@@AEAAKXZ`
- size: `397`
- prototype: `unsigned int __fastcall(Memory::Recycler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1803b8140`

## callees

- `0x180268298`
- `0x18026842c`
- `0x180268494`
- `0x180268574`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1802682fa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1802682fa`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802683a7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802683a7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18026830d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802683e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18026830d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802683e9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1802682d2`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1802682d2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibraryAndExitThread` at `0x180268418`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibraryAndExitThread` at `0x180268418`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18026832b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18026832b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180268319`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180268319`

## pseudocode

```c
__int64 __fastcall Memory::Recycler::ThreadProc(Memory::Recycler *this)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // edi
  unsigned int v4; // r9d
  DWORD dwMilliseconds; // [rsp+30h] [rbp-48h] BYREF
  HMODULE phModule; // [rsp+38h] [rbp-40h] BYREF
  HANDLE Handles; // [rsp+40h] [rbp-38h] BYREF
  __int64 v9; // [rsp+48h] [rbp-30h]
  GUID ActivityId; // [rsp+50h] [rbp-28h] BYREF

  phModule = 0;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)Memory::Recycler::StaticThreadProc, &phModule) )
    phModule = 0;
  ActivityId = 0;
  EventActivityIdControl(5u, &ActivityId);
  SetEvent(*((HANDLE *)this + 272));
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  v9 = *((_QWORD *)this + 2166);
  Handles = (HANDLE)*((_QWORD *)this + 271);
  v3 = v9 != 0;
  while ( 1 )
  {
    do
    {
      *((_DWORD *)this + 4334) = 0;
      dwMilliseconds = -1;
      Memory::HeapInfo::ForEachNonLeafPageAllocator__lambda_24cc5d073afeaaa5892ae3ac095eece2___(
        (char *)this + 17504,
        &dwMilliseconds);
      v4 = Memory::IdleDecommitPageAllocator::IdleDecommit(*((Memory::IdleDecommitPageAllocator **)this + 13386));
      if ( dwMilliseconds < v4 )
        v4 = dwMilliseconds;
    }
    while ( v4 == -1 && _InterlockedCompareExchange((volatile signed __int32 *)this + 4334, 2, 0) == 1
         || WaitForMultipleObjectsEx(v3 + 1, &Handles, 0, v4, 0) );
    if ( *((_DWORD *)this + 8) == 4 )
      break;
    Memory::Recycler::DoBackgroundWork(this, 0);
  }
  SetEvent(*((HANDLE *)this + 272));
  if ( phModule )
    FreeLibraryAndExitThread(phModule, 0);
  return 0;
}

```

## disassembly

```asm
0x180268298  mov     [rsp-20h+arg_0], rcx
0x18026829d  push    rbp
0x18026829e  push    rbx
0x18026829f  push    rsi
0x1802682a0  push    rdi
0x1802682a1  mov     rbp, rsp
0x1802682a4  sub     rsp, 78h
0x1802682a8  mov     rax, cs:__security_cookie
0x1802682af  xor     rax, rsp
0x1802682b2  mov     [rbp+var_18], rax
0x1802682b6  mov     rbx, [rbp+arg_0]
0x1802682ba  lea     r8, [rbp+phModule]; phModule
0x1802682be  lea     rdx, ?StaticThreadProc@Recycler@Memory@@CAIPEAX@Z; lpModuleName
0x1802682c5  mov     [rbp+phModule], 0
0x1802682cd  mov     ecx, 4; dwFlags
0x1802682d2  call    cs:__imp_GetModuleHandleExW
0x1802682d9  nop     dword ptr [rax+rax+00h]
0x1802682de  test    eax, eax
0x1802682e0  jnz     short loc_1802682EA
0x1802682e2  mov     [rbp+phModule], 0
0x1802682ea  xorps   xmm0, xmm0
0x1802682ed  lea     rdx, [rbp+ActivityId]; ActivityId
0x1802682f1  mov     ecx, 5; ControlCode
0x1802682f6  movups  xmmword ptr [rbp+ActivityId.Data1], xmm0
0x1802682fa  call    cs:__imp_EventActivityIdControl
0x180268301  nop     dword ptr [rax+rax+00h]
0x180268306  mov     rcx, [rbx+880h]; hEvent
0x18026830d  call    cs:__imp_SetEvent
0x180268314  nop     dword ptr [rax+rax+00h]
0x180268319  call    cs:__imp_GetCurrentThread
0x180268320  nop     dword ptr [rax+rax+00h]
0x180268325  mov     rcx, rax; hThread
0x180268328  or      edx, 0FFFFFFFFh; nPriority
0x18026832b  call    cs:__imp_SetThreadPriority
0x180268332  nop     dword ptr [rax+rax+00h]
0x180268337  mov     rcx, [rbx+43B0h]
0x18026833e  mov     rax, rcx
0x180268341  mov     [rbp+var_30], rcx
0x180268345  neg     rax
0x180268348  mov     rax, [rbx+878h]
0x18026834f  sbb     edi, edi
0x180268351  mov     [rbp+Handles], rax
0x180268355  neg     edi
0x180268357  lea     rdx, [rbp+dwMilliseconds]
0x18026835b  mov     dword ptr [rbx+43B8h], 0
0x180268365  lea     rcx, [rbx+4460h]
0x18026836c  mov     [rbp+dwMilliseconds], 0FFFFFFFFh
0x180268373  call    Memory__HeapInfo__ForEachNonLeafPageAllocator__lambda_24cc5d073afeaaa5892ae3ac095eece2___
0x180268378  mov     rcx, [rbx+1A250h]; this
0x18026837f  call    ?IdleDecommit@IdleDecommitPageAllocator@Memory@@QEAAKXZ; Memory::IdleDecommitPageAllocator::IdleDecommit(void)
0x180268384  cmp     [rbp+dwMilliseconds], eax
0x180268387  mov     r9d, eax
0x18026838a  cmovb   r9d, [rbp+dwMilliseconds]; dwMilliseconds
0x18026838f  cmp     r9d, 0FFFFFFFFh
0x180268393  jz      short loc_1802683C9
0x180268395  xor     r8d, r8d; bWaitAll
0x180268398  mov     [rsp+78h+bAlertable], 0; bAlertable
0x1802683a0  lea     rdx, [rbp+Handles]; lpHandles
0x1802683a4  lea     ecx, [rdi+1]; nCount
0x1802683a7  call    cs:__imp_WaitForMultipleObjectsEx
0x1802683ae  nop     dword ptr [rax+rax+00h]
0x1802683b3  test    eax, eax
0x1802683b5  jnz     short loc_180268357
0x1802683b7  cmp     dword ptr [rbx+20h], 4
0x1802683bb  jz      short loc_1802683E2
0x1802683bd  xor     edx, edx; bool
0x1802683bf  mov     rcx, rbx; this
0x1802683c2  call    ?DoBackgroundWork@Recycler@Memory@@AEAAX_N@Z; Memory::Recycler::DoBackgroundWork(bool)
0x1802683c7  jmp     short loc_180268357
0x1802683c9  mov     ecx, 2
0x1802683ce  xor     eax, eax
0x1802683d0  lock cmpxchg [rbx+43B8h], ecx
0x1802683d8  cmp     eax, 1
0x1802683db  jnz     short loc_180268395
0x1802683dd  jmp     loc_180268357
0x1802683e2  mov     rcx, [rbx+880h]; hEvent
0x1802683e9  call    cs:__imp_SetEvent
0x1802683f0  nop     dword ptr [rax+rax+00h]
0x1802683f5  mov     rcx, [rbp+phModule]; hLibModule
0x1802683f9  test    rcx, rcx
0x1802683fc  jnz     short loc_180268416
0x1802683fe  xor     eax, eax
0x180268400  mov     rcx, [rbp+var_18]
0x180268404  xor     rcx, rsp; StackCookie
0x180268407  call    __security_check_cookie
0x18026840c  add     rsp, 78h
0x180268410  pop     rdi
0x180268411  pop     rsi
0x180268412  pop     rbx
0x180268413  pop     rbp
0x180268414  retn
0x180268416  xor     edx, edx; dwExitCode
0x180268418  call    cs:__imp_FreeLibraryAndExitThread
0x18026841f  nop     dword ptr [rax+rax+00h]
0x180268424  int     3; Trap to Debugger
```
