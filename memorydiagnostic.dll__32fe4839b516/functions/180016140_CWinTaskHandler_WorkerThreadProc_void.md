# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180016140`
- end: `0x1800161c6`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `134`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180016140`
- `0x180024010`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x1800161a1`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1800161a1`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *Parameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = Parameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 64LL))(Parameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)Parameter + 6) + 32LL))(*((_QWORD *)Parameter + 6), v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)Parameter + 3);
    *((_QWORD *)Parameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016140  mov     [rsp+arg_0], rbx
0x180016145  mov     [rsp+arg_8], rbp
0x18001614a  mov     [rsp+arg_10], rsi
0x18001614f  push    rdi
0x180016150  sub     rsp, 20h
0x180016154  mov     rax, [rcx]
0x180016157  mov     rbx, rcx
0x18001615a  mov     ebp, [rcx+10h]
0x18001615d  xor     esi, esi
0x18001615f  mov     rax, [rax+40h]
0x180016163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016168  mov     rcx, [rbx+30h]
0x18001616c  mov     edi, eax
0x18001616e  mov     rdx, [rcx]
0x180016171  mov     rax, [rdx+20h]
0x180016175  mov     edx, edi
0x180016177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001617c  test    ebp, ebp
0x18001617e  jz      short loc_180016189
0x180016180  mov     rsi, [rbx+18h]
0x180016184  and     qword ptr [rbx+18h], 0
0x180016189  mov     rax, [rbx]
0x18001618c  mov     rcx, rbx
0x18001618f  mov     rax, [rax+10h]
0x180016193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016198  test    ebp, ebp
0x18001619a  jz      short loc_1800161AE
0x18001619c  mov     edx, edi; dwExitCode
0x18001619e  mov     rcx, rsi; hLibModule
0x1800161a1  call    cs:__imp_FreeLibraryAndExitThread
0x1800161ae  mov     rbx, [rsp+28h+arg_0]
0x1800161b3  mov     eax, edi
0x1800161b5  mov     rbp, [rsp+28h+arg_8]
0x1800161ba  mov     rsi, [rsp+28h+arg_10]
0x1800161bf  add     rsp, 20h
0x1800161c3  pop     rdi
0x1800161c4  retn
```
