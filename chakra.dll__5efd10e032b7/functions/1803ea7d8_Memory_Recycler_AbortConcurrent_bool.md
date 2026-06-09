# Memory::Recycler::AbortConcurrent(bool)

- ea: `0x1803ea7d8`
- end: `0x1803ea9e4`
- name: `?AbortConcurrent@Recycler@Memory@@AEAA_N_N@Z`
- size: `524`
- prototype: `bool __fastcall(Memory::Recycler *__hidden this, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18038cf78`

## callees

- `0x1802ce640`
- `0x1803bcf80`
- `0x1803c2584`
- `0x1803ea7d8`
- `0x1803eaa74`
- `0x1803eab38`
- `0x1803eacc0`
- `0x1804113d8`
- `0x18048a6ec`
- `0x18048aa00`
- `0x180490f10`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1803ea859`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1803ea859`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1803ea988`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1803ea988`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1803ea83a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1803ea83a`

## pseudocode

```c
bool __fastcall Memory::Recycler::AbortConcurrent(Memory::Recycler *this, char a2)
{
  char *v3; // rdi
  void *v4; // rcx
  DWORD v5; // r14d
  BOOL v6; // esi
  DWORD v7; // eax
  void (__fastcall ***v8)(_QWORD, int *, char *); // rcx
  int v9; // eax
  __int64 *v10; // rdx
  void (__fastcall ***v11)(_QWORD, int *, char *); // rcx
  int v12; // eax
  int v14; // [rsp+30h] [rbp-20h] BYREF
  HANDLE Handles[3]; // [rsp+38h] [rbp-18h] BYREF

  v3 = (char *)this + 32;
  v4 = (void *)*((_QWORD *)this + 273);
  Handles[0] = *((HANDLE *)this + 272);
  Handles[1] = v4;
  v5 = 0;
  v6 = v4 != 0;
  if ( (*((_DWORD *)this + 8) & 0x2000) != 0 )
  {
    *((_BYTE *)this + 2324) = 1;
    if ( v4 )
      SetThreadPriority(v4, 0);
    v7 = WaitForMultipleObjectsEx(v6 + 1, Handles, 0, 0xFFFFFFFF, 0);
    *((_BYTE *)this + 2324) = 0;
    v5 = v7;
    if ( v7 )
    {
      if ( !a2 && v7 == -1 )
      {
        Js::Throw::FatalInternalError(-2147467259);
        __debugbreak();
      }
    }
    else if ( a2 )
    {
      if ( *(_DWORD *)v3 == 40961 )
      {
        Memory::Recycler::ResetMarkCollectionState(this);
        return v5 == 0;
      }
      if ( *(_DWORD *)v3 != 2138114 )
      {
        if ( *(_DWORD *)v3 != 40962 )
          return v5 == 0;
        *((_BYTE *)this + 2124) = 0;
LABEL_24:
        SetEvent(*((HANDLE *)this + 272));
        Memory::Recycler::FinishConcurrent<147456>(this);
        return v5 == 0;
      }
      *((_BYTE *)this + 2124) = 0;
      Memory::Recycler::FinishSweepPrep(this);
      Memory::Recycler::FinishConcurrentSweepPass1(this);
      v8 = (void (__fastcall ***)(_QWORD, int *, char *))*((_QWORD *)v3 + 1);
      v9 = 4218882;
      v14 = 4218882;
      if ( v8 && *(_DWORD *)v3 != 4218882 )
      {
        (**v8)(v8, &v14, v3);
        v9 = v14;
      }
      *(_DWORD *)v3 = v9;
      Memory::RecyclerSweepManager::FinishSweep(*((Memory::RecyclerSweepManager **)this + 2165));
      Memory::Recycler::FinishConcurrentSweep(this);
      *(_BYTE *)(*((_QWORD *)this + 2165) + 14920LL) = 0;
      if ( *((_BYTE *)this + 2138) )
      {
        if ( (Microsoft_JScriptEnableBits & 0x200000) == 0 )
          goto LABEL_18;
        v10 = MEMPROTECT_GC_BACKGROUNDSWEEP_STOP;
      }
      else
      {
        if ( (Microsoft_JScriptEnableBits & 0x20) == 0 )
          goto LABEL_18;
        v10 = JSCRIPT_GC_BACKGROUNDSWEEP_STOP;
      }
      McTemplateU0pq_EventWriteTransfer(&PROVIDER_JSCRIPT9_Context, v10, this, 0);
LABEL_18:
      v11 = (void (__fastcall ***)(_QWORD, int *, char *))*((_QWORD *)v3 + 1);
      v12 = 40962;
      v14 = 40962;
      if ( v11 && *(_DWORD *)v3 != 40962 )
      {
        (**v11)(v11, &v14, v3);
        v12 = v14;
      }
      *(_DWORD *)v3 = v12;
      goto LABEL_24;
    }
    Memory::Recycler::CleanupPendingUnroot(this);
    Memory::MarkContext::Abort((Memory::Recycler *)((char *)this + 232));
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x1803ea7d8  mov     rax, rsp
0x1803ea7db  mov     [rax+18h], rbx
0x1803ea7df  mov     [rax+20h], rsi
0x1803ea7e3  mov     [rax+10h], dl
0x1803ea7e6  mov     [rax+8], rcx
0x1803ea7ea  push    rbp
0x1803ea7eb  push    rdi
0x1803ea7ec  push    r14
0x1803ea7ee  mov     rbp, rsp
0x1803ea7f1  sub     rsp, 50h
0x1803ea7f5  mov     rbx, [rbp+arg_0]
0x1803ea7f9  mov     rax, [rbx+880h]
0x1803ea800  lea     rdi, [rbx+20h]
0x1803ea804  mov     rcx, [rbx+888h]; hThread
0x1803ea80b  mov     [rbp+Handles], rax
0x1803ea80f  mov     rax, rcx
0x1803ea812  neg     rax
0x1803ea815  mov     [rbp+var_10], rcx
0x1803ea819  sbb     esi, esi
0x1803ea81b  xor     r14d, r14d
0x1803ea81e  neg     esi
0x1803ea820  test    dword ptr [rdi], 2000h
0x1803ea826  jz      loc_1803EA9C8
0x1803ea82c  mov     byte ptr [rbx+914h], 1
0x1803ea833  test    rcx, rcx
0x1803ea836  jz      short loc_1803EA846
0x1803ea838  xor     edx, edx; nPriority
0x1803ea83a  call    cs:__imp_SetThreadPriority
0x1803ea841  nop     dword ptr [rax+rax+00h]
0x1803ea846  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1803ea84a  mov     [rsp+50h+bAlertable], r14d; bAlertable
0x1803ea84f  xor     r8d, r8d; bWaitAll
0x1803ea852  lea     rdx, [rbp+Handles]; lpHandles
0x1803ea856  lea     ecx, [rsi+1]; nCount
0x1803ea859  call    cs:__imp_WaitForMultipleObjectsEx
0x1803ea860  nop     dword ptr [rax+rax+00h]
0x1803ea865  mov     byte ptr [rbx+914h], 0
0x1803ea86c  mov     r14d, eax
0x1803ea86f  test    eax, eax
0x1803ea871  jnz     loc_1803EA99E
0x1803ea877  cmp     [rbp+arg_8], al
0x1803ea87a  jz      loc_1803EA9B4
0x1803ea880  cmp     dword ptr [rdi], 0A001h
0x1803ea886  jnz     short loc_1803EA895
0x1803ea888  mov     rcx, rbx; this
0x1803ea88b  call    ?ResetMarkCollectionState@Recycler@Memory@@AEAAXXZ; Memory::Recycler::ResetMarkCollectionState(void)
0x1803ea890  jmp     loc_1803EA9C8
0x1803ea895  cmp     dword ptr [rdi], 20A002h
0x1803ea89b  jnz     loc_1803EA971
0x1803ea8a1  mov     rcx, rbx; this
0x1803ea8a4  mov     byte ptr [rbx+84Ch], 0
0x1803ea8ab  call    ?FinishSweepPrep@Recycler@Memory@@AEAAXXZ; Memory::Recycler::FinishSweepPrep(void)
0x1803ea8b0  mov     rcx, rbx; this
0x1803ea8b3  call    ?FinishConcurrentSweepPass1@Recycler@Memory@@AEAAXXZ; Memory::Recycler::FinishConcurrentSweepPass1(void)
0x1803ea8b8  mov     rcx, [rdi+8]
0x1803ea8bc  mov     eax, 406002h
0x1803ea8c1  mov     [rbp+var_20], eax
0x1803ea8c4  test    rcx, rcx
0x1803ea8c7  jz      short loc_1803EA8E2
0x1803ea8c9  cmp     [rdi], eax
0x1803ea8cb  jz      short loc_1803EA8E2
0x1803ea8cd  mov     rax, [rcx]
0x1803ea8d0  lea     rdx, [rbp+var_20]
0x1803ea8d4  mov     r8, rdi
0x1803ea8d7  mov     rax, [rax]
0x1803ea8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ea8df  mov     eax, [rbp+var_20]
0x1803ea8e2  mov     [rdi], eax
0x1803ea8e4  mov     rcx, [rbx+43A8h]; this
0x1803ea8eb  call    ?FinishSweep@RecyclerSweepManager@Memory@@QEAAXXZ; Memory::RecyclerSweepManager::FinishSweep(void)
0x1803ea8f0  mov     rcx, rbx; this
0x1803ea8f3  call    ?FinishConcurrentSweep@Recycler@Memory@@AEAAXXZ; Memory::Recycler::FinishConcurrentSweep(void)
0x1803ea8f8  mov     rax, [rbx+43A8h]
0x1803ea8ff  mov     byte ptr [rax+3A48h], 0
0x1803ea906  cmp     byte ptr [rbx+85Ah], 0
0x1803ea90d  jz      short loc_1803EA921
0x1803ea90f  test    byte ptr cs:Microsoft_JScriptEnableBits+2, 20h
0x1803ea916  jz      short loc_1803EA943
0x1803ea918  lea     rdx, MEMPROTECT_GC_BACKGROUNDSWEEP_STOP
0x1803ea91f  jmp     short loc_1803EA931
0x1803ea921  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x1803ea928  jz      short loc_1803EA943
0x1803ea92a  lea     rdx, JSCRIPT_GC_BACKGROUNDSWEEP_STOP
0x1803ea931  xor     r9d, r9d
0x1803ea934  lea     rcx, PROVIDER_JSCRIPT9_Context
0x1803ea93b  mov     r8, rbx
0x1803ea93e  call    McTemplateU0pq_EventWriteTransfer
0x1803ea943  mov     rcx, [rdi+8]
0x1803ea947  mov     eax, 0A002h
0x1803ea94c  mov     [rbp+var_20], eax
0x1803ea94f  test    rcx, rcx
0x1803ea952  jz      short loc_1803EA96D
0x1803ea954  cmp     [rdi], eax
0x1803ea956  jz      short loc_1803EA96D
0x1803ea958  mov     rax, [rcx]
0x1803ea95b  lea     rdx, [rbp+var_20]
0x1803ea95f  mov     r8, rdi
0x1803ea962  mov     rax, [rax]
0x1803ea965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803ea96a  mov     eax, [rbp+var_20]
0x1803ea96d  mov     [rdi], eax
0x1803ea96f  jmp     short loc_1803EA981
0x1803ea971  mov     eax, 0A002h
0x1803ea976  cmp     [rdi], eax
0x1803ea978  jnz     short loc_1803EA9C8
0x1803ea97a  mov     byte ptr [rbx+84Ch], 0
0x1803ea981  mov     rcx, [rbx+880h]; hEvent
0x1803ea988  call    cs:__imp_SetEvent
0x1803ea98f  nop     dword ptr [rax+rax+00h]
0x1803ea994  mov     rcx, rbx
0x1803ea997  call    ??$FinishConcurrent@$0CEAAA@@Recycler@Memory@@QEAAHXZ; Memory::Recycler::FinishConcurrent<147456>(void)
0x1803ea99c  jmp     short loc_1803EA9C8
0x1803ea99e  cmp     [rbp+arg_8], 0
0x1803ea9a2  jnz     short loc_1803EA9B4
0x1803ea9a4  cmp     eax, 0FFFFFFFFh
0x1803ea9a7  jnz     short loc_1803EA9B4
0x1803ea9a9  mov     ecx, 80004005h; int
0x1803ea9ae  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x1803ea9b3  int     3; Trap to Debugger
0x1803ea9b4  mov     rcx, rbx; this
0x1803ea9b7  call    ?CleanupPendingUnroot@Recycler@Memory@@AEAAXXZ; Memory::Recycler::CleanupPendingUnroot(void)
0x1803ea9bc  lea     rcx, [rbx+0E8h]; this
0x1803ea9c3  call    ?Abort@MarkContext@Memory@@QEAAXXZ; Memory::MarkContext::Abort(void)
0x1803ea9c8  lea     r11, [rsp+50h+var_s0]
0x1803ea9cd  test    r14d, r14d
0x1803ea9d0  mov     rbx, [r11+30h]
0x1803ea9d4  mov     rsi, [r11+38h]
0x1803ea9d8  setz    al
0x1803ea9db  mov     rsp, r11
0x1803ea9de  pop     r14
0x1803ea9e0  pop     rdi
0x1803ea9e1  pop     rbp
0x1803ea9e2  retn
```
