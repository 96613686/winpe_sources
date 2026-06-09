# AutoThreadpool::QueueThreadpoolWork(void (*)(void *),void *)

- ea: `0x140015294`
- end: `0x1400153ec`
- name: `?QueueThreadpoolWork@AutoThreadpool@@QEAAJP6AXPEAX@Z0@Z`
- size: `344`
- prototype: `__int64 __fastcall(AutoThreadpool *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400147f0`

## callees

- `0x140001c34`
- `0x140015294`
- `0x1400154e0`
- `0x1400154fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400152b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400152b9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1400152d1`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1400152d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001536d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015387`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001539e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400153b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001536d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015387`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001539e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400153b8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140015348`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140015348`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14001532b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14001532b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AutoThreadpool::QueueThreadpoolWork(AutoThreadpool *this, void (*a2)(void *), void *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  wil *v13; // rcx
  __int64 result; // rax
  int v15; // [rsp+20h] [rbp-38h]
  _QWORD *v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v18; // [rsp+68h] [rbp+10h]
  struct _RTL_CRITICAL_SECTION *v19; // [rsp+78h] [rbp+20h]

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v19 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v6 = -TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v9 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 8) & -(__int64)(v6 != 0));
  if ( v9 )
  {
    try
    {
      if ( !*((_QWORD *)this + 6) )
        wil::details::in1diag3::_Throw_Hr(retaddr, v7, v8, (const char *)0x8007139FLL, v15);
      v16 = operator new(0x10u);
      *v16 = ThreadpoolManager::ThreadpoolWorkItemCallback;
      v16[1] = a3;
      ThreadpoolWork = CreateThreadpoolWork(
                         AutoThreadpool::ThreadpoolWorkItemCallback,
                         v16,
                         (PTP_CALLBACK_ENVIRON)((char *)this + 56));
      if ( !ThreadpoolWork )
        wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x71, v11, v12);
      SubmitThreadpoolWork(ThreadpoolWork);
      LeaveCriticalSection(v9);
      if ( v5 )
        LeaveCriticalSection(v5);
      result = 0;
    }
    catch ( ... )
    {
      v18 = wil::ResultFromCaughtException(v13);
      LeaveCriticalSection(v9);
      if ( v19 )
        LeaveCriticalSection(v19);
      return v18;
    }
  }
  else
  {
    if ( v5 )
      LeaveCriticalSection(v5);
    return 2147500036LL;
  }
  return result;
}

```

## disassembly

```asm
0x140015294  mov     [rsp+arg_8], rdx
0x140015299  push    rbx
0x14001529a  push    rsi
0x14001529b  push    rdi
0x14001529c  push    r14
0x14001529e  push    r15
0x1400152a0  sub     rsp, 30h
0x1400152a4  mov     r15, r8
0x1400152a7  mov     r14, rcx
0x1400152aa  lea     rsi, [rcx+88h]
0x1400152b1  mov     [rsp+58h+arg_18], rsi
0x1400152b6  mov     rcx, rsi; lpCriticalSection
0x1400152b9  call    cs:__imp_EnterCriticalSection
0x1400152c0  nop     dword ptr [rax+rax+00h]
0x1400152c5  mov     [rsp+58h+arg_8], rsi
0x1400152ca  lea     rdi, [r14+8]
0x1400152ce  mov     rcx, rdi; lpCriticalSection
0x1400152d1  call    cs:__imp_TryEnterCriticalSection
0x1400152d8  nop     dword ptr [rax+rax+00h]
0x1400152dd  neg     eax
0x1400152df  sbb     rbx, rbx
0x1400152e2  and     rbx, rdi
0x1400152e5  mov     [rsp+58h+lpCriticalSection], rbx
0x1400152ea  jz      loc_1400153B0
0x1400152f0  mov     rcx, [rsp+58h]; this
0x1400152f5  cmp     qword ptr [r14+30h], 0
0x1400152fa  jz      loc_1400153D6
0x140015300  mov     ecx, 10h; Size
0x140015305  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001530a  mov     qword ptr [rsp+58h+var_38], rax
0x14001530f  lea     rcx, ?ThreadpoolWorkItemCallback@ThreadpoolManager@@CAXPEAX@Z; ThreadpoolManager::ThreadpoolWorkItemCallback(void *)
0x140015316  mov     [rax], rcx
0x140015319  mov     [rax+8], r15
0x14001531d  lea     r8, [r14+38h]; pcbe
0x140015321  mov     rdx, rax; pv
0x140015324  lea     rcx, ?ThreadpoolWorkItemCallback@AutoThreadpool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14001532b  call    cs:__imp_CreateThreadpoolWork
0x140015332  nop     dword ptr [rax+rax+00h]
0x140015337  mov     rcx, [rsp+58h]; this
0x14001533c  test    rax, rax
0x14001533f  jz      loc_1400153E2
0x140015345  mov     rcx, rax; pwk
0x140015348  call    cs:__imp_SubmitThreadpoolWork
0x14001534f  nop     dword ptr [rax+rax+00h]
0x140015354  nop
0x140015355  mov     rcx, rbx; lpCriticalSection
0x140015358  call    cs:__imp_LeaveCriticalSection
0x14001535f  nop     dword ptr [rax+rax+00h]
0x140015364  nop
0x140015365  test    rsi, rsi
0x140015368  jz      short loc_140015379
0x14001536a  mov     rcx, rsi; lpCriticalSection
0x14001536d  call    cs:__imp_LeaveCriticalSection
0x140015374  nop     dword ptr [rax+rax+00h]
0x140015379  xor     eax, eax
0x14001537b  jmp     short loc_1400153C9
0x14001537d  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x140015382  test    rcx, rcx
0x140015385  jz      short loc_140015394
0x140015387  call    cs:__imp_LeaveCriticalSection
0x14001538e  nop     dword ptr [rax+rax+00h]
0x140015393  nop
0x140015394  mov     rcx, [rsp+58h+arg_18]; lpCriticalSection
0x140015399  test    rcx, rcx
0x14001539c  jz      short loc_1400153AA
0x14001539e  call    cs:__imp_LeaveCriticalSection
0x1400153a5  nop     dword ptr [rax+rax+00h]
0x1400153aa  mov     eax, dword ptr [rsp+58h+arg_8]
0x1400153ae  jmp     short loc_1400153C9
0x1400153b0  test    rsi, rsi
0x1400153b3  jz      short loc_1400153C4
0x1400153b5  mov     rcx, rsi; lpCriticalSection
0x1400153b8  call    cs:__imp_LeaveCriticalSection
0x1400153bf  nop     dword ptr [rax+rax+00h]
0x1400153c4  mov     eax, 80004004h
0x1400153c9  add     rsp, 30h
0x1400153cd  pop     r15
0x1400153cf  pop     r14
0x1400153d1  pop     rdi
0x1400153d2  pop     rsi
0x1400153d3  pop     rbx
0x1400153d4  retn
0x1400153d6  mov     r9d, 8007139Fh; char *
0x1400153dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400153e2  lea     edx, [rax+71h]; void *
0x1400153e5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
