# Memory::RecyclerParallelThread::EnableConcurrent(bool)

- ea: `0x1801f22a4`
- end: `0x1801f244e`
- name: `?EnableConcurrent@RecyclerParallelThread@Memory@@QEAA_N_N@Z`
- size: `426`
- prototype: `bool __fastcall(Memory::RecyclerParallelThread *__hidden this, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801f0604`
- `0x1801f1f74`

## callees

- `0x1801f22a4`
- `0x18032e784`
- `0x1805cd010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1801f2345`
- `msvcrt!_beginthreadex` at `0x1801f2345`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1801f23df`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1801f23df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f22ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f22f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f22ce`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801f22f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f230a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f23f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f240b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f230a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f23f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f240b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2423`

## string_xrefs

- `0x1801f238e`: `Chakra Recycler Parallel Thread`
- `0x1801f236f`: `SetThreadDescription`

## pseudocode

```c
char __fastcall Memory::RecyclerParallelThread::EnableConcurrent(Memory::RecyclerParallelThread *this, char a2)
{
  HANDLE EventW; // rax
  HANDLE v5; // rax
  uintptr_t v6; // rdi
  __int64 (*Function)(void); // rax
  void *v8; // rax
  void *v9; // rcx
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  *((_BYTE *)this + 56) = a2;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( !EventW )
    return 0;
  v5 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 4) = v5;
  if ( !v5 )
  {
    CloseHandle(*((HANDLE *)this + 5));
    *((_QWORD *)this + 5) = 0;
    return 0;
  }
  v6 = _beginthreadex(0, 0x493E0u, Memory::RecyclerParallelThread::StaticThreadProc, this, 0x10000u, 0);
  if ( v6 )
  {
    if ( qword_180737FD0 )
    {
      Function = (__int64 (*)(void))qword_180737FE0;
      if ( qword_180737FE0
        || (Function = DelayLoadLibrary::GetFunction((DelayLoadLibrary *)&off_180737FC8, "SetThreadDescription"),
            (qword_180737FE0 = (__int64)Function) != 0) )
      {
        ((void (__fastcall *)(uintptr_t, const wchar_t *))Function)(v6, L"Chakra Recycler Parallel Thread");
      }
    }
    if ( v6 != -1 )
      *((_QWORD *)this + 6) = v6;
  }
  if ( !*((_QWORD *)this + 6) )
  {
LABEL_15:
    CloseHandle(*((HANDLE *)this + 5));
    v9 = (void *)*((_QWORD *)this + 4);
    *((_QWORD *)this + 5) = 0;
    CloseHandle(v9);
    *((_QWORD *)this + 4) = 0;
    return 0;
  }
  if ( a2 )
  {
    v8 = (void *)*((_QWORD *)this + 5);
    Handles[1] = *((HANDLE *)this + 6);
    Handles[0] = v8;
    if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
    {
      CloseHandle(*((HANDLE *)this + 6));
      *((_QWORD *)this + 6) = 0;
      goto LABEL_15;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1801f22a4  mov     rax, rsp
0x1801f22a7  mov     [rax+18h], rbx
0x1801f22ab  mov     [rax+20h], rsi
0x1801f22af  mov     [rax+10h], dl
0x1801f22b2  mov     [rax+8], rcx
0x1801f22b6  push    rdi
0x1801f22b7  sub     rsp, 40h
0x1801f22bb  mov     [rcx+38h], dl
0x1801f22be  mov     sil, dl
0x1801f22c1  mov     rbx, rcx
0x1801f22c4  xor     edx, edx; bManualReset
0x1801f22c6  xor     ecx, ecx; lpEventAttributes
0x1801f22c8  xor     r9d, r9d; lpName
0x1801f22cb  xor     r8d, r8d; bInitialState
0x1801f22ce  call    cs:__imp_CreateEventW
0x1801f22d5  nop     dword ptr [rax+rax+00h]
0x1801f22da  mov     [rbx+28h], rax
0x1801f22de  test    rax, rax
0x1801f22e1  jz      loc_1801F2437
0x1801f22e7  xor     r9d, r9d; lpName
0x1801f22ea  xor     r8d, r8d; bInitialState
0x1801f22ed  xor     edx, edx; bManualReset
0x1801f22ef  xor     ecx, ecx; lpEventAttributes
0x1801f22f1  call    cs:__imp_CreateEventW
0x1801f22f8  nop     dword ptr [rax+rax+00h]
0x1801f22fd  mov     [rbx+20h], rax
0x1801f2301  test    rax, rax
0x1801f2304  jnz     short loc_1801F2323
0x1801f2306  mov     rcx, [rbx+28h]; hObject
0x1801f230a  call    cs:__imp_CloseHandle
0x1801f2311  nop     dword ptr [rax+rax+00h]
0x1801f2316  mov     qword ptr [rbx+28h], 0
0x1801f231e  jmp     loc_1801F2437
0x1801f2323  mov     [rsp+48h+ThrdAddr], 0; ThrdAddr
0x1801f232c  lea     r8, ?StaticThreadProc@RecyclerParallelThread@Memory@@CAIPEAX@Z; StartAddress
0x1801f2333  mov     r9, rbx; ArgList
0x1801f2336  mov     [rsp+48h+InitFlag], 10000h; InitFlag
0x1801f233e  mov     edx, 493E0h; StackSize
0x1801f2343  xor     ecx, ecx; Security
0x1801f2345  call    cs:__imp__beginthreadex
0x1801f234c  nop     dword ptr [rax+rax+00h]
0x1801f2351  mov     rdi, rax
0x1801f2354  test    rax, rax
0x1801f2357  jz      short loc_1801F23A7
0x1801f2359  cmp     cs:qword_180737FD0, 0
0x1801f2361  jz      short loc_1801F239D
0x1801f2363  mov     rax, cs:qword_180737FE0
0x1801f236a  test    rax, rax
0x1801f236d  jnz     short loc_1801F238E
0x1801f236f  lea     rdx, aSetthreaddescr; "SetThreadDescription"
0x1801f2376  lea     rcx, off_180737FC8; this
0x1801f237d  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x1801f2382  mov     cs:qword_180737FE0, rax
0x1801f2389  test    rax, rax
0x1801f238c  jz      short loc_1801F239D
0x1801f238e  lea     rdx, aChakraRecycler; "Chakra Recycler Parallel Thread"
0x1801f2395  mov     rcx, rdi
0x1801f2398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f239d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801f23a1  jz      short loc_1801F23A7
0x1801f23a3  mov     [rbx+30h], rdi
0x1801f23a7  mov     rcx, [rbx+30h]
0x1801f23ab  test    rcx, rcx
0x1801f23ae  jz      short loc_1801F2407
0x1801f23b0  test    sil, sil
0x1801f23b3  jz      loc_1801F244A
0x1801f23b9  mov     rax, [rbx+28h]
0x1801f23bd  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1801f23c2  xor     r8d, r8d; bWaitAll
0x1801f23c5  mov     [rsp+48h+var_10], rcx
0x1801f23ca  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1801f23ce  mov     [rsp+48h+Handles], rax
0x1801f23d3  mov     [rsp+48h+InitFlag], 0; bAlertable
0x1801f23db  lea     ecx, [r8+2]; nCount
0x1801f23df  call    cs:__imp_WaitForMultipleObjectsEx
0x1801f23e6  nop     dword ptr [rax+rax+00h]
0x1801f23eb  test    eax, eax
0x1801f23ed  jz      short loc_1801F244A
0x1801f23ef  mov     rcx, [rbx+30h]; hObject
0x1801f23f3  call    cs:__imp_CloseHandle
0x1801f23fa  nop     dword ptr [rax+rax+00h]
0x1801f23ff  mov     qword ptr [rbx+30h], 0
0x1801f2407  mov     rcx, [rbx+28h]; hObject
0x1801f240b  call    cs:__imp_CloseHandle
0x1801f2412  nop     dword ptr [rax+rax+00h]
0x1801f2417  mov     rcx, [rbx+20h]; hObject
0x1801f241b  mov     qword ptr [rbx+28h], 0
0x1801f2423  call    cs:__imp_CloseHandle
0x1801f242a  nop     dword ptr [rax+rax+00h]
0x1801f242f  mov     qword ptr [rbx+20h], 0
0x1801f2437  xor     al, al
0x1801f2439  mov     rbx, [rsp+48h+arg_10]
0x1801f243e  mov     rsi, [rsp+48h+arg_18]
0x1801f2443  add     rsp, 40h
0x1801f2447  pop     rdi
0x1801f2448  retn
0x1801f244a  mov     al, 1
0x1801f244c  jmp     short loc_1801F2439
```
