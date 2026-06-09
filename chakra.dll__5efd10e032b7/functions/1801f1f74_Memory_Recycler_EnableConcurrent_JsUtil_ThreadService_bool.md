# Memory::Recycler::EnableConcurrent(JsUtil::ThreadService *,bool)

- ea: `0x1801f1f74`
- end: `0x1801f21c6`
- name: `?EnableConcurrent@Recycler@Memory@@QEAA_NPEAVThreadService@JsUtil@@_N@Z`
- size: `594`
- prototype: `bool __fastcall(Memory::Recycler *__hidden this, struct JsUtil::ThreadService *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1801f1eec`
- `0x1802f1324`

## callees

- `0x180167544`
- `0x1801f1f74`
- `0x1801f21cc`
- `0x1801f22a4`
- `0x18032e784`
- `0x18038d124`
- `0x1805cd010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x1801f206e`
- `msvcrt!_beginthreadex` at `0x1801f206e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1801f20f5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1801f20f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f21a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f2182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f21a1`

## string_xrefs

- `0x1801f209b`: `SetThreadDescription`

## pseudocode

```c
char __fastcall Memory::Recycler::EnableConcurrent(Memory::Recycler *this, struct JsUtil::ThreadService *a2, char a3)
{
  int v5; // r8d
  char v6; // dl
  unsigned int v7; // r8d
  char v9; // r14
  char v10; // r15
  Memory::RecyclerParallelThread *v11; // rbp
  Memory::RecyclerParallelThread *v12; // rdi
  void *v13; // rdi
  __int64 (*Function)(void); // rax
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( !*((_BYTE *)this + 2148) && Memory::Recycler::InitializeConcurrent(this, a2) )
  {
    v5 = *((_DWORD *)this + 538);
    *(_WORD *)((char *)this + 2149) = 257;
    *((_BYTE *)this + 2151) = 1;
    if ( v5 == 1 )
      *((_BYTE *)this + 2150) = 0;
    if ( JsUtil::ThreadService::HasCallback(a2) )
      goto LABEL_6;
    v9 = 0;
    v10 = 0;
    if ( a3 && v6 && v7 > 2 )
    {
      v11 = (Memory::Recycler *)((char *)this + 2192);
      if ( !Memory::RecyclerParallelThread::EnableConcurrent((Memory::Recycler *)((char *)this + 2192), 1) )
      {
LABEL_27:
        v15 = (void *)*((_QWORD *)this + 271);
        *(_WORD *)((char *)this + 2149) = 0;
        *((_BYTE *)this + 2151) = 0;
        if ( v15 )
        {
          CloseHandle(v15);
          *((_QWORD *)this + 271) = 0;
        }
        v16 = (void *)*((_QWORD *)this + 272);
        if ( v16 )
        {
          CloseHandle(v16);
          *((_QWORD *)this + 272) = 0;
        }
        v17 = (void *)*((_QWORD *)this + 2166);
        if ( v17 )
        {
          CloseHandle(v17);
          *((_QWORD *)this + 2166) = 0;
        }
        return 0;
      }
      v9 = 1;
      if ( *((_DWORD *)this + 538) > 3u )
      {
        v12 = (Memory::Recycler *)((char *)this + 2256);
        if ( !Memory::RecyclerParallelThread::EnableConcurrent((Memory::Recycler *)((char *)this + 2256), 1) )
        {
LABEL_25:
          Memory::RecyclerParallelThread::Shutdown(v11);
          if ( v10 )
            Memory::RecyclerParallelThread::Shutdown(v12);
          goto LABEL_27;
        }
        v10 = 1;
      }
    }
    v13 = (void *)_beginthreadex(0, 0x493E0u, Memory::Recycler::StaticThreadProc, this, 0x10000u, 0);
    if ( v13 )
    {
      if ( qword_180737FD0 )
      {
        Function = (__int64 (*)(void))qword_180737FE0;
        if ( qword_180737FE0
          || (Function = DelayLoadLibrary::GetFunction((DelayLoadLibrary *)&off_180737FC8, "SetThreadDescription"),
              (qword_180737FE0 = (__int64)Function) != 0) )
        {
          ((void (__fastcall *)(void *, const wchar_t *))Function)(v13, L"Chakra Background Recycler");
        }
      }
      if ( v13 != (void *)-1LL )
      {
        Handles[0] = *((HANDLE *)this + 272);
        Handles[1] = v13;
        if ( !WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
        {
          *((_QWORD *)this + 273) = v13;
LABEL_6:
          *((_QWORD *)this + 6) = a2;
          return 1;
        }
        CloseHandle(v13);
      }
    }
    if ( !v9 )
      goto LABEL_27;
    v11 = (Memory::Recycler *)((char *)this + 2192);
    v12 = (Memory::Recycler *)((char *)this + 2256);
    goto LABEL_25;
  }
  return 0;
}

```

## disassembly

```asm
0x1801f1f74  mov     rax, rsp
0x1801f1f77  mov     [rax+18h], r8b
0x1801f1f7b  mov     [rax+10h], rdx
0x1801f1f7f  mov     [rax+8], rcx
0x1801f1f83  push    rbx
0x1801f1f84  push    rbp
0x1801f1f85  push    rsi
0x1801f1f86  push    rdi
0x1801f1f87  push    r12
0x1801f1f89  push    r14
0x1801f1f8b  push    r15
0x1801f1f8d  sub     rsp, 40h
0x1801f1f91  xor     r12d, r12d
0x1801f1f94  mov     rbx, rcx
0x1801f1f97  cmp     [rcx+864h], r12b
0x1801f1f9e  jnz     loc_1801F21B4
0x1801f1fa4  mov     rsi, rdx
0x1801f1fa7  call    ?InitializeConcurrent@Recycler@Memory@@AEAA_NPEAVThreadService@JsUtil@@@Z; Memory::Recycler::InitializeConcurrent(JsUtil::ThreadService *)
0x1801f1fac  test    al, al
0x1801f1fae  jz      loc_1801F21B4
0x1801f1fb4  mov     r8d, [rbx+868h]
0x1801f1fbb  mov     dl, 1
0x1801f1fbd  mov     word ptr [rbx+865h], 101h
0x1801f1fc6  mov     byte ptr [rbx+867h], 1
0x1801f1fcd  cmp     r8d, 1
0x1801f1fd1  jnz     short loc_1801F1FDD
0x1801f1fd3  mov     [rbx+866h], r12b
0x1801f1fda  mov     dl, r12b
0x1801f1fdd  mov     rcx, rsi; this
0x1801f1fe0  call    ?HasCallback@ThreadService@JsUtil@@QEBA_NXZ; JsUtil::ThreadService::HasCallback(void)
0x1801f1fe5  test    al, al
0x1801f1fe7  jz      short loc_1801F1FF4
0x1801f1fe9  mov     [rbx+30h], rsi
0x1801f1fed  mov     al, 1
0x1801f1fef  jmp     loc_1801F21B6
0x1801f1ff4  mov     r14b, r12b
0x1801f1ff7  mov     r15b, r12b
0x1801f1ffa  cmp     [rsp+78h+arg_10], r12b
0x1801f2002  jz      short loc_1801F2050
0x1801f2004  test    dl, dl
0x1801f2006  jz      short loc_1801F2050
0x1801f2008  cmp     r8d, 2
0x1801f200c  jbe     short loc_1801F2050
0x1801f200e  lea     rbp, [rbx+890h]
0x1801f2015  mov     dl, 1; bool
0x1801f2017  mov     rcx, rbp; this
0x1801f201a  call    ?EnableConcurrent@RecyclerParallelThread@Memory@@QEAA_N_N@Z; Memory::RecyclerParallelThread::EnableConcurrent(bool)
0x1801f201f  test    al, al
0x1801f2021  jz      loc_1801F2148
0x1801f2027  cmp     dword ptr [rbx+868h], 3
0x1801f202e  mov     r14b, 1
0x1801f2031  jbe     short loc_1801F2050
0x1801f2033  lea     rdi, [rbx+8D0h]
0x1801f203a  mov     dl, r14b; bool
0x1801f203d  mov     rcx, rdi; this
0x1801f2040  call    ?EnableConcurrent@RecyclerParallelThread@Memory@@QEAA_N_N@Z; Memory::RecyclerParallelThread::EnableConcurrent(bool)
0x1801f2045  test    al, al
0x1801f2047  jz      loc_1801F2133
0x1801f204d  mov     r15b, r14b
0x1801f2050  mov     [rsp+78h+ThrdAddr], r12; ThrdAddr
0x1801f2055  lea     r8, ?StaticThreadProc@Recycler@Memory@@CAIPEAX@Z; StartAddress
0x1801f205c  mov     r9, rbx; ArgList
0x1801f205f  mov     [rsp+78h+InitFlag], 10000h; InitFlag
0x1801f2067  mov     edx, 493E0h; StackSize
0x1801f206c  xor     ecx, ecx; Security
0x1801f206e  call    cs:__imp__beginthreadex
0x1801f2075  nop     dword ptr [rax+rax+00h]
0x1801f207a  mov     rdi, rax
0x1801f207d  test    rax, rax
0x1801f2080  jz      loc_1801F2120
0x1801f2086  cmp     cs:qword_180737FD0, r12
0x1801f208d  jz      short loc_1801F20C9
0x1801f208f  mov     rax, cs:qword_180737FE0
0x1801f2096  test    rax, rax
0x1801f2099  jnz     short loc_1801F20BA
0x1801f209b  lea     rdx, aSetthreaddescr; "SetThreadDescription"
0x1801f20a2  lea     rcx, off_180737FC8; this
0x1801f20a9  call    ?GetFunction@DelayLoadLibrary@@QEAAP6A_JXZPEBD@Z; DelayLoadLibrary::GetFunction(char const *)
0x1801f20ae  mov     cs:qword_180737FE0, rax
0x1801f20b5  test    rax, rax
0x1801f20b8  jz      short loc_1801F20C9
0x1801f20ba  lea     rdx, aChakraBackgrou; "Chakra Background Recycler"
0x1801f20c1  mov     rcx, rdi
0x1801f20c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f20c9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801f20cd  jz      short loc_1801F2120
0x1801f20cf  mov     rax, [rbx+880h]
0x1801f20d6  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1801f20db  xor     r8d, r8d; bWaitAll
0x1801f20de  mov     [rsp+78h+Handles], rax
0x1801f20e3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1801f20e7  mov     [rsp+78h+var_40], rdi
0x1801f20ec  mov     [rsp+78h+InitFlag], r12d; bAlertable
0x1801f20f1  lea     ecx, [r8+2]; nCount
0x1801f20f5  call    cs:__imp_WaitForMultipleObjectsEx
0x1801f20fc  nop     dword ptr [rax+rax+00h]
0x1801f2101  test    eax, eax
0x1801f2103  jnz     short loc_1801F2111
0x1801f2105  mov     [rbx+888h], rdi
0x1801f210c  jmp     loc_1801F1FE9
0x1801f2111  mov     rcx, rdi; hObject
0x1801f2114  call    cs:__imp_CloseHandle
0x1801f211b  nop     dword ptr [rax+rax+00h]
0x1801f2120  test    r14b, r14b
0x1801f2123  jz      short loc_1801F2148
0x1801f2125  lea     rbp, [rbx+890h]
0x1801f212c  lea     rdi, [rbx+8D0h]
0x1801f2133  mov     rcx, rbp; this
0x1801f2136  call    ?Shutdown@RecyclerParallelThread@Memory@@QEAAXXZ; Memory::RecyclerParallelThread::Shutdown(void)
0x1801f213b  test    r15b, r15b
0x1801f213e  jz      short loc_1801F2148
0x1801f2140  mov     rcx, rdi; this
0x1801f2143  call    ?Shutdown@RecyclerParallelThread@Memory@@QEAAXXZ; Memory::RecyclerParallelThread::Shutdown(void)
0x1801f2148  mov     rcx, [rbx+878h]; hObject
0x1801f214f  mov     [rbx+865h], r12w
0x1801f2157  mov     [rbx+867h], r12b
0x1801f215e  test    rcx, rcx
0x1801f2161  jz      short loc_1801F2176
0x1801f2163  call    cs:__imp_CloseHandle
0x1801f216a  nop     dword ptr [rax+rax+00h]
0x1801f216f  mov     [rbx+878h], r12
0x1801f2176  mov     rcx, [rbx+880h]; hObject
0x1801f217d  test    rcx, rcx
0x1801f2180  jz      short loc_1801F2195
0x1801f2182  call    cs:__imp_CloseHandle
0x1801f2189  nop     dword ptr [rax+rax+00h]
0x1801f218e  mov     [rbx+880h], r12
0x1801f2195  mov     rcx, [rbx+43B0h]; hObject
0x1801f219c  test    rcx, rcx
0x1801f219f  jz      short loc_1801F21B4
0x1801f21a1  call    cs:__imp_CloseHandle
0x1801f21a8  nop     dword ptr [rax+rax+00h]
0x1801f21ad  mov     [rbx+43B0h], r12
0x1801f21b4  xor     al, al
0x1801f21b6  add     rsp, 40h
0x1801f21ba  pop     r15
0x1801f21bc  pop     r14
0x1801f21be  pop     r12
0x1801f21c0  pop     rdi
0x1801f21c1  pop     rsi
0x1801f21c2  pop     rbp
0x1801f21c3  pop     rbx
0x1801f21c4  retn
```
