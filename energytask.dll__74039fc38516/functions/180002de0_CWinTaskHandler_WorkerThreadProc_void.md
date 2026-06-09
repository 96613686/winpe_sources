# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002de0`
- end: `0x180002e4b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002de0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002e39`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002e39`

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
0x180002de0  push    rbx
0x180002de2  push    rbp
0x180002de3  push    rsi
0x180002de4  push    rdi
0x180002de5  sub     rsp, 28h
0x180002de9  mov     rax, [rcx]
0x180002dec  mov     rbx, rcx
0x180002def  mov     ebp, [rcx+10h]
0x180002df2  xor     esi, esi
0x180002df4  mov     rax, [rax+40h]
0x180002df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dfd  mov     rcx, [rbx+30h]
0x180002e01  mov     edi, eax
0x180002e03  mov     rdx, [rcx]
0x180002e06  mov     rax, [rdx+20h]
0x180002e0a  mov     edx, edi
0x180002e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e11  test    ebp, ebp
0x180002e13  jz      short loc_180002E21
0x180002e15  mov     rsi, [rbx+18h]
0x180002e19  mov     qword ptr [rbx+18h], 0
0x180002e21  mov     rax, [rbx]
0x180002e24  mov     rcx, rbx
0x180002e27  mov     rax, [rax+10h]
0x180002e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e30  test    ebp, ebp
0x180002e32  jz      short loc_180002E40
0x180002e34  mov     edx, edi; dwExitCode
0x180002e36  mov     rcx, rsi; hLibModule
0x180002e39  call    cs:__imp_FreeLibraryAndExitThread
0x180002e3f  int     3; Trap to Debugger
0x180002e40  mov     eax, edi
0x180002e42  add     rsp, 28h
0x180002e46  pop     rdi
0x180002e47  pop     rsi
0x180002e48  pop     rbp
0x180002e49  pop     rbx
0x180002e4a  retn
```
