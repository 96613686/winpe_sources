# WorkThreadManager::CThread::RunCurrentTaskUnderLock(void)

- ea: `0x180007620`
- end: `0x18000777d`
- name: `?RunCurrentTaskUnderLock@CThread@WorkThreadManager@@QEAAXXZ`
- size: `349`
- prototype: `void __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c994`

## callees

- `0x180007620`
- `0x18001267f`
- `0x180012716`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000773b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000773b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800076ee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180007755`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800076ee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180007755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800076d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800076e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000774a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800076d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800076e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000774a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800076db`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800076db`

## pseudocode

```c
void __fastcall WorkThreadManager::CThread::RunCurrentTaskUnderLock(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  unsigned int v3; // eax
  int v4; // esi
  int ThreadPriority; // ebp
  HANDLE CurrentThread; // rax
  HANDLE v7; // rax
  BOOL v8; // esi
  PVOID Ptr; // rcx
  HANDLE v10; // rax

  v1 = this + 28;
  AcquireSRWLockShared_0(this + 28);
  if ( !this[24].Ptr )
    goto LABEL_24;
  v3 = HIDWORD(this[18].Ptr) & 0xF000;
  if ( v3 == 20480 )
    goto LABEL_18;
  if ( v3 > 0x4000 )
  {
    switch ( v3 )
    {
      case 0x6000u:
        v4 = 1;
        goto LABEL_19;
      case 0x7000u:
        v4 = 2;
        goto LABEL_19;
      case 0x8000u:
        v4 = 15;
        goto LABEL_19;
    }
    goto LABEL_18;
  }
  if ( v3 == 0x4000 )
  {
    v4 = -1;
    goto LABEL_19;
  }
  if ( v3 != 4096 )
  {
    if ( v3 == 0x2000 )
    {
      v4 = -15;
      goto LABEL_19;
    }
    if ( v3 == 12288 )
    {
      v4 = -2;
LABEL_19:
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      goto LABEL_20;
    }
LABEL_18:
    v4 = 0;
    goto LABEL_19;
  }
  v4 = 0x10000;
  ThreadPriority = 0x20000;
LABEL_20:
  v7 = GetCurrentThread();
  v8 = SetThreadPriority(v7, v4);
  LODWORD(this[16].Ptr) = (HIDWORD(this[9].Ptr) | (LODWORD(this[9].Ptr) << 24) | 0x800000) + 1;
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[24].Ptr + 24LL))(this[24].Ptr);
  Ptr = this[20].Ptr;
  LODWORD(this[16].Ptr) = (HIDWORD(this[9].Ptr) | (LODWORD(this[9].Ptr) << 24)) + 1;
  if ( Ptr )
    SetEvent(Ptr);
  if ( v8 )
  {
    v10 = GetCurrentThread();
    SetThreadPriority(v10, ThreadPriority);
  }
LABEL_24:
  if ( v1 )
    ReleaseSRWLockShared_0(v1);
}

```

## disassembly

```asm
0x180007620  push    rdi
0x180007622  sub     rsp, 20h
0x180007626  lea     rdi, [rcx+0E0h]
0x18000762d  mov     [rsp+28h+arg_0], rbx
0x180007632  mov     rbx, rcx
0x180007635  mov     rcx, rdi; SRWLock
0x180007638  call    AcquireSRWLockShared_0
0x18000763d  cmp     qword ptr [rbx+0C0h], 0
0x180007645  jz      loc_180007760
0x18000764b  mov     eax, [rbx+94h]
0x180007651  and     eax, 0F000h
0x180007656  mov     [rsp+28h+arg_10], rsi
0x18000765b  mov     [rsp+28h+arg_8], rbp
0x180007660  cmp     eax, 5000h
0x180007665  jz      short loc_1800076D0
0x180007667  cmp     eax, 4000h
0x18000766c  ja      short loc_1800076A6
0x18000766e  jz      short loc_18000769F
0x180007670  cmp     eax, 1000h
0x180007675  jz      short loc_180007693
0x180007677  cmp     eax, 2000h
0x18000767c  jz      short loc_18000768C
0x18000767e  cmp     eax, 3000h
0x180007683  jnz     short loc_1800076D0
0x180007685  mov     esi, 0FFFFFFFEh
0x18000768a  jmp     short loc_1800076D2
0x18000768c  mov     esi, 0FFFFFFF1h
0x180007691  jmp     short loc_1800076D2
0x180007693  mov     esi, 10000h
0x180007698  mov     ebp, 20000h
0x18000769d  jmp     short loc_1800076E3
0x18000769f  mov     esi, 0FFFFFFFFh
0x1800076a4  jmp     short loc_1800076D2
0x1800076a6  cmp     eax, 6000h
0x1800076ab  jz      short loc_1800076C9
0x1800076ad  cmp     eax, 7000h
0x1800076b2  jz      short loc_1800076C2
0x1800076b4  cmp     eax, 8000h
0x1800076b9  jnz     short loc_1800076D0
0x1800076bb  mov     esi, 0Fh
0x1800076c0  jmp     short loc_1800076D2
0x1800076c2  mov     esi, 2
0x1800076c7  jmp     short loc_1800076D2
0x1800076c9  mov     esi, 1
0x1800076ce  jmp     short loc_1800076D2
0x1800076d0  xor     esi, esi
0x1800076d2  call    cs:__imp_GetCurrentThread
0x1800076d8  mov     rcx, rax; hThread
0x1800076db  call    cs:__imp_GetThreadPriority
0x1800076e1  mov     ebp, eax
0x1800076e3  call    cs:__imp_GetCurrentThread
0x1800076e9  mov     rcx, rax; hThread
0x1800076ec  mov     edx, esi; nPriority
0x1800076ee  call    cs:__imp_SetThreadPriority
0x1800076f4  mov     ecx, [rbx+48h]
0x1800076f7  mov     esi, eax
0x1800076f9  shl     ecx, 18h
0x1800076fc  or      ecx, [rbx+4Ch]
0x1800076ff  bts     ecx, 17h
0x180007703  inc     ecx
0x180007705  mov     [rbx+80h], ecx
0x18000770b  mov     rcx, [rbx+0C0h]
0x180007712  mov     rdx, [rcx]
0x180007715  mov     rax, [rdx+18h]
0x180007719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771e  mov     eax, [rbx+48h]
0x180007721  mov     rcx, [rbx+0A0h]; hEvent
0x180007728  shl     eax, 18h
0x18000772b  or      eax, [rbx+4Ch]
0x18000772e  inc     eax
0x180007730  mov     [rbx+80h], eax
0x180007736  test    rcx, rcx
0x180007739  jz      short loc_180007741
0x18000773b  call    cs:__imp_SetEvent
0x180007741  test    esi, esi
0x180007743  mov     rsi, [rsp+28h+arg_10]
0x180007748  jz      short loc_18000775B
0x18000774a  call    cs:__imp_GetCurrentThread
0x180007750  mov     rcx, rax; hThread
0x180007753  mov     edx, ebp; nPriority
0x180007755  call    cs:__imp_SetThreadPriority
0x18000775b  mov     rbp, [rsp+28h+arg_8]
0x180007760  mov     rbx, [rsp+28h+arg_0]
0x180007765  test    rdi, rdi
0x180007768  jz      short loc_180007777
0x18000776a  mov     rcx, rdi; SRWLock
0x18000776d  add     rsp, 20h
0x180007771  pop     rdi
0x180007772  jmp     ReleaseSRWLockShared_0
0x180007777  add     rsp, 20h
0x18000777b  pop     rdi
0x18000777c  retn
```
