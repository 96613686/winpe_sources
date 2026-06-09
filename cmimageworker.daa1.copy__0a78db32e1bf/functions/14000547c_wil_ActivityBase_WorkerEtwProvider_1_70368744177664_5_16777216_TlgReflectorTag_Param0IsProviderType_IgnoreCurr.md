# wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x14000547c`
- end: `0x1400054f7`
- name: `?IgnoreCurrentThread@?$ActivityBase@VWorkerEtwProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `123`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140007d1c`
- `0x140007e60`
- `0x140008100`
- `0x1400083a0`
- `0x140008640`

## callees

- `0x14000547c`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005492`

## string_xrefs

- `0x1400054b4`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall wil::ActivityBase<WorkerEtwProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rax
  void *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v1 + 24) = 0;
    v2 = *(__int64 **)v1;
    while ( 1 )
    {
      v3 = *v2;
      if ( !*v2 )
        break;
      if ( v3 == v1 )
      {
        *v2 = *(_QWORD *)(v1 + 16);
        break;
      }
      v2 = (__int64 *)(v3 + 16);
      *(_QWORD *)v1 = v3 + 16;
    }
    *(_QWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x14000547c  push    rbx
0x14000547e  sub     rsp, 20h
0x140005482  cmp     dword ptr [rcx+138h], 0
0x140005489  jz      short loc_1400054F0
0x14000548b  lea     rbx, [rcx+120h]
0x140005492  call    cs:__imp_GetCurrentThreadId
0x140005499  nop     dword ptr [rax+rax+00h]
0x14000549e  cmp     [rbx+18h], eax
0x1400054a1  jz      short loc_1400054C0
0x1400054a3  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1400054aa  test    rax, rax
0x1400054ad  jz      short loc_1400054C0
0x1400054af  mov     rdx, [rsp+28h]
0x1400054b4  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1400054bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054c0  mov     dword ptr [rbx+18h], 0
0x1400054c7  mov     rcx, [rbx]
0x1400054ca  jmp     short loc_1400054D8
0x1400054cc  cmp     rax, rbx
0x1400054cf  jz      short loc_1400054E2
0x1400054d1  lea     rcx, [rax+10h]
0x1400054d5  mov     [rbx], rcx
0x1400054d8  mov     rax, [rcx]
0x1400054db  test    rax, rax
0x1400054de  jnz     short loc_1400054CC
0x1400054e0  jmp     short loc_1400054E9
0x1400054e2  mov     rax, [rbx+10h]
0x1400054e6  mov     [rcx], rax
0x1400054e9  mov     qword ptr [rbx], 0
0x1400054f0  add     rsp, 20h
0x1400054f4  pop     rbx
0x1400054f5  retn
```
