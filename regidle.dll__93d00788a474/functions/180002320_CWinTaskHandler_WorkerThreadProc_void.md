# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002320`
- end: `0x18000238b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002320`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002379`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002379`

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
0x180002320  push    rbx
0x180002322  push    rbp
0x180002323  push    rsi
0x180002324  push    rdi
0x180002325  sub     rsp, 28h
0x180002329  mov     rax, [rcx]
0x18000232c  mov     rbx, rcx
0x18000232f  mov     ebp, [rcx+10h]
0x180002332  xor     esi, esi
0x180002334  mov     rax, [rax+40h]
0x180002338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233d  mov     rcx, [rbx+30h]
0x180002341  mov     edi, eax
0x180002343  mov     rdx, [rcx]
0x180002346  mov     rax, [rdx+20h]
0x18000234a  mov     edx, edi
0x18000234c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002351  test    ebp, ebp
0x180002353  jz      short loc_180002361
0x180002355  mov     rsi, [rbx+18h]
0x180002359  mov     qword ptr [rbx+18h], 0
0x180002361  mov     rax, [rbx]
0x180002364  mov     rcx, rbx
0x180002367  mov     rax, [rax+10h]
0x18000236b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002370  test    ebp, ebp
0x180002372  jz      short loc_180002380
0x180002374  mov     edx, edi; dwExitCode
0x180002376  mov     rcx, rsi; hLibModule
0x180002379  call    cs:__imp_FreeLibraryAndExitThread
0x18000237f  int     3; Trap to Debugger
0x180002380  mov     eax, edi
0x180002382  add     rsp, 28h
0x180002386  pop     rdi
0x180002387  pop     rsi
0x180002388  pop     rbp
0x180002389  pop     rbx
0x18000238a  retn
```
