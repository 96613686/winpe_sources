# Recycler::ThreadProc(void)

- ea: `0x180005dcc`
- end: `0x180005ee6`
- name: `?ThreadProc@Recycler@@AEAAKXZ`
- size: `282`
- prototype: `unsigned int __fastcall(Recycler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180254be0`

## callees

- `0x180005dcc`
- `0x180005eec`
- `0x18000646c`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180005edf`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180005edf`
- `KERNEL32!SetThreadPriority` at `0x180005e24`
- `KERNEL32!SetThreadPriority` at `0x180005e24`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005e8c`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180005e8c`
- `KERNEL32!GetCurrentThread` at `0x180005e18`
- `KERNEL32!GetCurrentThread` at `0x180005e18`
- `KERNEL32!SetEvent` at `0x180005e12`
- `KERNEL32!SetEvent` at `0x180005ec2`
- `KERNEL32!SetEvent` at `0x180005e12`
- `KERNEL32!SetEvent` at `0x180005ec2`
- `KERNEL32!GetModuleHandleExW` at `0x180005df0`
- `KERNEL32!GetModuleHandleExW` at `0x180005df0`

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
0x180005dcc  mov     [rsp+arg_0], rcx
0x180005dd1  push    rbx
0x180005dd2  push    rbp
0x180005dd3  push    rsi
0x180005dd4  push    rdi
0x180005dd5  sub     rsp, 58h
0x180005dd9  lea     r8, [rsp+78h+phModule]; phModule
0x180005dde  mov     [rsp+78h+phModule], 0
0x180005de7  lea     rdx, ?binaryName@AutoSystemInfo@@0PAGA; lpModuleName
0x180005dee  xor     ecx, ecx; dwFlags
0x180005df0  call    cs:__imp_GetModuleHandleExW
0x180005df6  test    eax, eax
0x180005df8  jnz     short loc_180005E03
0x180005dfa  mov     [rsp+78h+phModule], 0
0x180005e03  mov     rdi, [rsp+78h+arg_0]
0x180005e0b  mov     rcx, [rdi+3290h]; hEvent
0x180005e12  call    cs:__imp_SetEvent
0x180005e18  call    cs:__imp_GetCurrentThread
0x180005e1e  mov     rcx, rax; hThread
0x180005e21  or      edx, 0FFFFFFFFh; nPriority
0x180005e24  call    cs:__imp_SetThreadPriority
0x180005e2a  mov     rcx, [rdi+3F10h]
0x180005e31  mov     rax, rcx
0x180005e34  mov     [rsp+78h+var_38], rcx
0x180005e39  neg     rax
0x180005e3c  mov     rax, [rdi+3288h]
0x180005e43  sbb     esi, esi
0x180005e45  mov     [rsp+78h+Handles], rax
0x180005e4a  neg     esi
0x180005e4c  mov     rcx, [rdi+8]; this
0x180005e50  mov     dword ptr [rdi+3F18h], 0
0x180005e5a  call    ?IdleDecommit@IdleDecommitPageAllocator@@QEAAKXZ; IdleDecommitPageAllocator::IdleDecommit(void)
0x180005e5f  lea     rcx, [rdi+10h]; this
0x180005e63  mov     ebx, eax
0x180005e65  call    ?IdleDecommit@IdleDecommitPageAllocator@@QEAAKXZ; IdleDecommitPageAllocator::IdleDecommit(void)
0x180005e6a  cmp     ebx, eax
0x180005e6c  mov     r9d, eax
0x180005e6f  cmovb   r9d, ebx; dwMilliseconds
0x180005e73  cmp     r9d, 0FFFFFFFFh
0x180005e77  jz      short loc_180005EA5
0x180005e79  xor     r8d, r8d; bWaitAll
0x180005e7c  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180005e84  lea     rdx, [rsp+78h+Handles]; lpHandles
0x180005e89  lea     ecx, [rsi+1]; nCount
0x180005e8c  call    cs:__imp_WaitForMultipleObjectsEx
0x180005e92  test    eax, eax
0x180005e94  jnz     short loc_180005E4C
0x180005e96  cmp     dword ptr [rdi], 4
0x180005e99  jz      short loc_180005EBB
0x180005e9b  mov     rcx, rdi; this
0x180005e9e  call    ?DoBackgroundWork@Recycler@@AEAAX_N@Z; Recycler::DoBackgroundWork(bool)
0x180005ea3  jmp     short loc_180005E4C
0x180005ea5  mov     ecx, 2
0x180005eaa  xor     eax, eax
0x180005eac  lock cmpxchg [rdi+3F18h], ecx
0x180005eb4  cmp     eax, 1
0x180005eb7  jnz     short loc_180005E79
0x180005eb9  jmp     short loc_180005E4C
0x180005ebb  mov     rcx, [rdi+3290h]; hEvent
0x180005ec2  call    cs:__imp_SetEvent
0x180005ec8  mov     rcx, [rsp+78h+phModule]; hLibModule
0x180005ecd  test    rcx, rcx
0x180005ed0  jnz     short loc_180005EDD
0x180005ed2  xor     eax, eax
0x180005ed4  add     rsp, 58h
0x180005ed8  pop     rdi
0x180005ed9  pop     rsi
0x180005eda  pop     rbp
0x180005edb  pop     rbx
0x180005edc  retn
0x180005edd  xor     edx, edx; dwExitCode
0x180005edf  call    cs:__imp_FreeLibraryAndExitThread
```
