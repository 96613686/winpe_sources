# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000b8c0`
- end: `0x18000b92b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000b8c0`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000b919`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000b919`

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
0x18000b8c0  push    rbx
0x18000b8c2  push    rbp
0x18000b8c3  push    rsi
0x18000b8c4  push    rdi
0x18000b8c5  sub     rsp, 28h
0x18000b8c9  mov     rax, [rcx]
0x18000b8cc  mov     rbx, rcx
0x18000b8cf  mov     ebp, [rcx+10h]
0x18000b8d2  xor     esi, esi
0x18000b8d4  mov     rax, [rax+40h]
0x18000b8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8dd  mov     rcx, [rbx+30h]
0x18000b8e1  mov     edi, eax
0x18000b8e3  mov     rdx, [rcx]
0x18000b8e6  mov     rax, [rdx+20h]
0x18000b8ea  mov     edx, edi
0x18000b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f1  test    ebp, ebp
0x18000b8f3  jz      short loc_18000B901
0x18000b8f5  mov     rsi, [rbx+18h]
0x18000b8f9  mov     qword ptr [rbx+18h], 0
0x18000b901  mov     rax, [rbx]
0x18000b904  mov     rcx, rbx
0x18000b907  mov     rax, [rax+10h]
0x18000b90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b910  test    ebp, ebp
0x18000b912  jz      short loc_18000B920
0x18000b914  mov     edx, edi; dwExitCode
0x18000b916  mov     rcx, rsi; hLibModule
0x18000b919  call    cs:__imp_FreeLibraryAndExitThread
0x18000b91f  int     3; Trap to Debugger
0x18000b920  mov     eax, edi
0x18000b922  add     rsp, 28h
0x18000b926  pop     rdi
0x18000b927  pop     rsi
0x18000b928  pop     rbp
0x18000b929  pop     rbx
0x18000b92a  retn
```
