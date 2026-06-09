# Recycler::ThreadProc(void)

- ea: `0x180008354`
- end: `0x180008499`
- name: `?ThreadProc@Recycler@@AEAAKXZ`
- size: `325`
- prototype: `unsigned int __fastcall(Recycler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180259390`

## callees

- `0x180008354`
- `0x1800084a0`
- `0x180008a7c`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x18000848c`
- `KERNEL32!FreeLibraryAndExitThread` at `0x18000848c`
- `KERNEL32!SetThreadPriority` at `0x1800083be`
- `KERNEL32!SetThreadPriority` at `0x1800083be`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000842c`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18000842c`
- `KERNEL32!GetCurrentThread` at `0x1800083ac`
- `KERNEL32!GetCurrentThread` at `0x1800083ac`
- `KERNEL32!SetEvent` at `0x1800083a0`
- `KERNEL32!SetEvent` at `0x180008468`
- `KERNEL32!SetEvent` at `0x1800083a0`
- `KERNEL32!SetEvent` at `0x180008468`
- `KERNEL32!GetModuleHandleExW` at `0x180008378`
- `KERNEL32!GetModuleHandleExW` at `0x180008378`

## pseudocode

```c
__int64 __fastcall Recycler::ThreadProc(Recycler *this)
{
  HANDLE CurrentThread; // rax
  BOOL v2; // esi
  IdleDecommitPageAllocator *v3; // rcx
  unsigned int v4; // ebx
  DWORD v5; // r9d
  bool v6; // dl
  HMODULE phModule; // [rsp+30h] [rbp-48h] BYREF
  HANDLE Handles; // [rsp+38h] [rbp-40h] BYREF
  __int64 v10; // [rsp+40h] [rbp-38h]

  phModule = 0;
  if ( !GetModuleHandleExW(0, &AutoSystemInfo::binaryName, &phModule) )
    phModule = 0;
  SetEvent(*((HANDLE *)this + 1618));
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, -1);
  v10 = *((_QWORD *)this + 2018);
  Handles = (HANDLE)*((_QWORD *)this + 1617);
  v2 = v10 != 0;
  while ( 1 )
  {
    do
    {
      v3 = (IdleDecommitPageAllocator *)*((_QWORD *)this + 1);
      *((_DWORD *)this + 4038) = 0;
      v4 = IdleDecommitPageAllocator::IdleDecommit(v3);
      v5 = IdleDecommitPageAllocator::IdleDecommit((Recycler *)((char *)this + 16));
      if ( v4 < v5 )
        v5 = v4;
    }
    while ( v5 == -1 && _InterlockedCompareExchange((volatile signed __int32 *)this + 4038, 2, 0) == 1
         || WaitForMultipleObjectsEx(v2 + 1, &Handles, 0, v5, 0) );
    if ( *(_DWORD *)this == 4 )
      break;
    Recycler::DoBackgroundWork(this, v6);
  }
  SetEvent(*((HANDLE *)this + 1618));
  if ( phModule )
    FreeLibraryAndExitThread(phModule, 0);
  return 0;
}

```

## disassembly

```asm
0x180008354  mov     [rsp+arg_0], rcx
0x180008359  push    rbx
0x18000835a  push    rbp
0x18000835b  push    rsi
0x18000835c  push    rdi
0x18000835d  sub     rsp, 58h
0x180008361  lea     r8, [rsp+78h+phModule]; phModule
0x180008366  mov     [rsp+78h+phModule], 0
0x18000836f  lea     rdx, ?binaryName@AutoSystemInfo@@0PAGA; lpModuleName
0x180008376  xor     ecx, ecx; dwFlags
0x180008378  call    cs:__imp_GetModuleHandleExW
0x18000837f  nop     dword ptr [rax+rax+00h]
0x180008384  test    eax, eax
0x180008386  jnz     short loc_180008391
0x180008388  mov     [rsp+78h+phModule], 0
0x180008391  mov     rdi, [rsp+78h+arg_0]
0x180008399  mov     rcx, [rdi+3290h]; hEvent
0x1800083a0  call    cs:__imp_SetEvent
0x1800083a7  nop     dword ptr [rax+rax+00h]
0x1800083ac  call    cs:__imp_GetCurrentThread
0x1800083b3  nop     dword ptr [rax+rax+00h]
0x1800083b8  mov     rcx, rax; hThread
0x1800083bb  or      edx, 0FFFFFFFFh; nPriority
0x1800083be  call    cs:__imp_SetThreadPriority
0x1800083c5  nop     dword ptr [rax+rax+00h]
0x1800083ca  mov     rcx, [rdi+3F10h]
0x1800083d1  mov     rax, rcx
0x1800083d4  mov     [rsp+78h+var_38], rcx
0x1800083d9  neg     rax
0x1800083dc  mov     rax, [rdi+3288h]
0x1800083e3  sbb     esi, esi
0x1800083e5  mov     [rsp+78h+Handles], rax
0x1800083ea  neg     esi
0x1800083ec  mov     rcx, [rdi+8]; this
0x1800083f0  mov     dword ptr [rdi+3F18h], 0
0x1800083fa  call    ?IdleDecommit@IdleDecommitPageAllocator@@QEAAKXZ; IdleDecommitPageAllocator::IdleDecommit(void)
0x1800083ff  lea     rcx, [rdi+10h]; this
0x180008403  mov     ebx, eax
0x180008405  call    ?IdleDecommit@IdleDecommitPageAllocator@@QEAAKXZ; IdleDecommitPageAllocator::IdleDecommit(void)
0x18000840a  cmp     ebx, eax
0x18000840c  mov     r9d, eax
0x18000840f  cmovb   r9d, ebx; dwMilliseconds
0x180008413  cmp     r9d, 0FFFFFFFFh
0x180008417  jz      short loc_18000844B
0x180008419  xor     r8d, r8d; bWaitAll
0x18000841c  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180008424  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180008429  lea     ecx, [rsi+1]; nCount
0x18000842c  call    cs:__imp_WaitForMultipleObjectsEx
0x180008433  nop     dword ptr [rax+rax+00h]
0x180008438  test    eax, eax
0x18000843a  jnz     short loc_1800083EC
0x18000843c  cmp     dword ptr [rdi], 4
0x18000843f  jz      short loc_180008461
0x180008441  mov     rcx, rdi; this
0x180008444  call    ?DoBackgroundWork@Recycler@@AEAAX_N@Z; Recycler::DoBackgroundWork(bool)
0x180008449  jmp     short loc_1800083EC
0x18000844b  mov     ecx, 2
0x180008450  xor     eax, eax
0x180008452  lock cmpxchg [rdi+3F18h], ecx
0x18000845a  cmp     eax, 1
0x18000845d  jnz     short loc_180008419
0x18000845f  jmp     short loc_1800083EC
0x180008461  mov     rcx, [rdi+3290h]; hEvent
0x180008468  call    cs:__imp_SetEvent
0x18000846f  nop     dword ptr [rax+rax+00h]
0x180008474  mov     rcx, [rsp+78h+phModule]; hLibModule
0x180008479  test    rcx, rcx
0x18000847c  jnz     short loc_18000848A
0x18000847e  xor     eax, eax
0x180008480  add     rsp, 58h
0x180008484  pop     rdi
0x180008485  pop     rsi
0x180008486  pop     rbp
0x180008487  pop     rbx
0x180008488  retn
0x18000848a  xor     edx, edx; dwExitCode
0x18000848c  call    cs:__imp_FreeLibraryAndExitThread
```
