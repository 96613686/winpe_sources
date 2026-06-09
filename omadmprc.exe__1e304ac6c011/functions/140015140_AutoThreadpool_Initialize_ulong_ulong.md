# AutoThreadpool::Initialize(ulong,ulong)

- ea: `0x140015140`
- end: `0x14001528b`
- name: `?Initialize@AutoThreadpool@@QEAAJKK@Z`
- size: `331`
- prototype: `int(AutoThreadpool *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400107ec`

## callees

- `0x140015140`
- `0x1400154e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015163`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140015163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001523d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015257`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001523d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140015257`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1400151e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1400151e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140015200`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x140015200`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140015176`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x140015176`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14001520c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14001520c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoThreadpool::Initialize(AutoThreadpool *this, __int64 a2, DWORD a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  struct _TP_POOL *Threadpool; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v9; // r8d
  const char *v10; // r9
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  _QWORD *v16; // rbp
  wil *v17; // rcx
  _QWORD *v18; // rdx
  _QWORD v19[9]; // [rsp+0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v21; // [rsp+58h] [rbp+10h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp+20h]

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v19[4] = v5;
  Threadpool = CreateThreadpool(0);
  *((_QWORD *)this + 6) = Threadpool;
  if ( !Threadpool )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x20, v7, v8);
    }
    catch ( ... )
    {
      v18 = v19;
      v16 = v18;
      AutoThreadpool::UninitializeAndWaitForPendingWorkItems((AutoThreadpool *)v18[10]);
      *((_DWORD *)v16 + 22) = wil::ResultFromCaughtException(v17);
      v15 = lpCriticalSection;
      if ( lpCriticalSection )
        LeaveCriticalSection(v15);
      return v21;
    }
  }
  *((_DWORD *)this + 14) = 3;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = 1;
  *((_DWORD *)this + 30) = 72;
  *((_QWORD *)this + 8) = Threadpool;
  if ( !SetThreadpoolThreadMinimum(Threadpool, 1u) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x25, v9, v10);
  SetThreadpoolThreadMaximum(*((PTP_POOL *)this + 6), a3);
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)this + 16) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x2A, v12, v13);
  *((_QWORD *)this + 9) = ThreadpoolCleanupGroup;
  *((_QWORD *)this + 10) = 0;
  if ( v5 )
    LeaveCriticalSection(v5);
  return 0;
}

```

## disassembly

```asm
0x140015140  mov     [rsp+arg_8], edx
0x140015144  mov     [rsp+arg_0], rcx
0x140015149  push    rbx
0x14001514a  push    rsi
0x14001514b  push    r14
0x14001514d  sub     rsp, 30h
0x140015151  mov     r14d, r8d
0x140015154  mov     rbx, rcx
0x140015157  lea     rsi, [rcx+8]
0x14001515b  mov     [rsp+48h+lpCriticalSection], rsi
0x140015160  mov     rcx, rsi; lpCriticalSection
0x140015163  call    cs:__imp_EnterCriticalSection
0x14001516a  nop     dword ptr [rax+rax+00h]
0x14001516f  mov     [rsp+48h+var_28], rsi
0x140015174  xor     ecx, ecx; reserved
0x140015176  call    cs:__imp_CreateThreadpool
0x14001517d  nop     dword ptr [rax+rax+00h]
0x140015182  mov     [rbx+30h], rax
0x140015186  mov     rcx, [rsp+48h]; this
0x14001518b  test    rax, rax
0x14001518e  jz      loc_140015271
0x140015194  mov     dword ptr [rbx+38h], 3
0x14001519b  mov     qword ptr [rbx+48h], 0
0x1400151a3  mov     qword ptr [rbx+50h], 0
0x1400151ab  mov     qword ptr [rbx+58h], 0
0x1400151b3  mov     qword ptr [rbx+60h], 0
0x1400151bb  mov     qword ptr [rbx+68h], 0
0x1400151c3  mov     dword ptr [rbx+70h], 0
0x1400151ca  mov     edx, 1; cthrdMic
0x1400151cf  mov     [rbx+74h], edx
0x1400151d2  mov     dword ptr [rbx+78h], 48h ; 'H'
0x1400151d9  mov     rcx, rax; ptpp
0x1400151dc  mov     [rbx+40h], rax
0x1400151e0  call    cs:__imp_SetThreadpoolThreadMinimum
0x1400151e7  nop     dword ptr [rax+rax+00h]
0x1400151ec  mov     rcx, [rsp+48h]; this
0x1400151f1  test    eax, eax
0x1400151f3  jz      loc_140015279
0x1400151f9  mov     edx, r14d; cthrdMost
0x1400151fc  mov     rcx, [rbx+30h]; ptpp
0x140015200  call    cs:__imp_SetThreadpoolThreadMaximum
0x140015207  nop     dword ptr [rax+rax+00h]
0x14001520c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140015213  nop     dword ptr [rax+rax+00h]
0x140015218  mov     [rbx+80h], rax
0x14001521f  mov     rcx, [rsp+48h]; this
0x140015224  test    rax, rax
0x140015227  jz      short loc_140015281
0x140015229  mov     [rbx+48h], rax
0x14001522d  mov     qword ptr [rbx+50h], 0
0x140015235  test    rsi, rsi
0x140015238  jz      short loc_140015249
0x14001523a  mov     rcx, rsi; lpCriticalSection
0x14001523d  call    cs:__imp_LeaveCriticalSection
0x140015244  nop     dword ptr [rax+rax+00h]
0x140015249  xor     eax, eax
0x14001524b  jmp     short loc_140015267
0x14001524d  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x140015252  test    rcx, rcx
0x140015255  jz      short loc_140015263
0x140015257  call    cs:__imp_LeaveCriticalSection
0x14001525e  nop     dword ptr [rax+rax+00h]
0x140015263  mov     eax, [rsp+48h+arg_8]
0x140015267  add     rsp, 30h
0x14001526b  pop     r14
0x14001526d  pop     rsi
0x14001526e  pop     rbx
0x14001526f  retn
0x140015271  lea     edx, [rax+20h]; void *
0x140015274  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140015279  lea     edx, [rax+25h]; void *
0x14001527c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x140015281  lea     edx, [rax+2Ah]; void *
0x140015284  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
