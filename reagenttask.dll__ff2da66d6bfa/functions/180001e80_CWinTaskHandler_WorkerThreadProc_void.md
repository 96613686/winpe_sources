# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180001e80`
- end: `0x180001f06`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `134`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001e80`
- `0x180003010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180001ee1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180001ee1`

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
0x180001e80  mov     [rsp+arg_0], rbx
0x180001e85  mov     [rsp+arg_8], rbp
0x180001e8a  mov     [rsp+arg_10], rsi
0x180001e8f  push    rdi
0x180001e90  sub     rsp, 20h
0x180001e94  mov     rax, [rcx]
0x180001e97  mov     rbx, rcx
0x180001e9a  mov     ebp, [rcx+10h]
0x180001e9d  xor     esi, esi
0x180001e9f  mov     rax, [rax+40h]
0x180001ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ea8  mov     rcx, [rbx+30h]
0x180001eac  mov     edi, eax
0x180001eae  mov     rdx, [rcx]
0x180001eb1  mov     rax, [rdx+20h]
0x180001eb5  mov     edx, edi
0x180001eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ebc  test    ebp, ebp
0x180001ebe  jz      short loc_180001EC9
0x180001ec0  mov     rsi, [rbx+18h]
0x180001ec4  and     qword ptr [rbx+18h], 0
0x180001ec9  mov     rax, [rbx]
0x180001ecc  mov     rcx, rbx
0x180001ecf  mov     rax, [rax+10h]
0x180001ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ed8  test    ebp, ebp
0x180001eda  jz      short loc_180001EEE
0x180001edc  mov     edx, edi; dwExitCode
0x180001ede  mov     rcx, rsi; hLibModule
0x180001ee1  call    cs:__imp_FreeLibraryAndExitThread
0x180001ee8  nop     dword ptr [rax+rax+00h]
0x180001eed  int     3; Trap to Debugger
0x180001eee  mov     rbx, [rsp+28h+arg_0]
0x180001ef3  mov     eax, edi
0x180001ef5  mov     rbp, [rsp+28h+arg_8]
0x180001efa  mov     rsi, [rsp+28h+arg_10]
0x180001eff  add     rsp, 20h
0x180001f03  pop     rdi
0x180001f04  retn
```
