# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180006340`
- end: `0x1800063ab`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006340`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180006399`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180006399`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *lpThreadParameter)
{
  int v2; // ebp
  HMODULE v3; // rsi
  __int64 v4; // rdi

  v2 = lpThreadParameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 64LL))(lpThreadParameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)lpThreadParameter + 6) + 32LL))(
    *((_QWORD *)lpThreadParameter + 6),
    v4);
  if ( v2 )
  {
    v3 = (HMODULE)*((_QWORD *)lpThreadParameter + 3);
    *((_QWORD *)lpThreadParameter + 3) = 0;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006340  push    rbx
0x180006342  push    rbp
0x180006343  push    rsi
0x180006344  push    rdi
0x180006345  sub     rsp, 28h
0x180006349  mov     rax, [rcx]
0x18000634c  mov     rbx, rcx
0x18000634f  mov     ebp, [rcx+10h]
0x180006352  xor     esi, esi
0x180006354  mov     rax, [rax+40h]
0x180006358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635d  mov     rcx, [rbx+30h]
0x180006361  mov     edi, eax
0x180006363  mov     rdx, [rcx]
0x180006366  mov     rax, [rdx+20h]
0x18000636a  mov     edx, edi
0x18000636c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006371  test    ebp, ebp
0x180006373  jz      short loc_180006381
0x180006375  mov     rsi, [rbx+18h]
0x180006379  mov     qword ptr [rbx+18h], 0
0x180006381  mov     rax, [rbx]
0x180006384  mov     rcx, rbx
0x180006387  mov     rax, [rax+10h]
0x18000638b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006390  test    ebp, ebp
0x180006392  jz      short loc_1800063A0
0x180006394  mov     edx, edi; dwExitCode
0x180006396  mov     rcx, rsi; hLibModule
0x180006399  call    cs:__imp_FreeLibraryAndExitThread
0x18000639f  int     3; Trap to Debugger
0x1800063a0  mov     eax, edi
0x1800063a2  add     rsp, 28h
0x1800063a6  pop     rdi
0x1800063a7  pop     rsi
0x1800063a8  pop     rbp
0x1800063a9  pop     rbx
0x1800063aa  retn
```
