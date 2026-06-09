# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002aa0`
- end: `0x180002b0b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002aa0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002af9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002af9`

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
0x180002aa0  push    rbx
0x180002aa2  push    rbp
0x180002aa3  push    rsi
0x180002aa4  push    rdi
0x180002aa5  sub     rsp, 28h
0x180002aa9  mov     rax, [rcx]
0x180002aac  mov     rbx, rcx
0x180002aaf  mov     ebp, [rcx+10h]
0x180002ab2  xor     esi, esi
0x180002ab4  mov     rax, [rax+40h]
0x180002ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abd  mov     rcx, [rbx+30h]
0x180002ac1  mov     edi, eax
0x180002ac3  mov     rdx, [rcx]
0x180002ac6  mov     rax, [rdx+20h]
0x180002aca  mov     edx, edi
0x180002acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad1  test    ebp, ebp
0x180002ad3  jz      short loc_180002AE1
0x180002ad5  mov     rsi, [rbx+18h]
0x180002ad9  mov     qword ptr [rbx+18h], 0
0x180002ae1  mov     rax, [rbx]
0x180002ae4  mov     rcx, rbx
0x180002ae7  mov     rax, [rax+10h]
0x180002aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af0  test    ebp, ebp
0x180002af2  jz      short loc_180002B00
0x180002af4  mov     edx, edi; dwExitCode
0x180002af6  mov     rcx, rsi; hLibModule
0x180002af9  call    cs:__imp_FreeLibraryAndExitThread
0x180002aff  int     3; Trap to Debugger
0x180002b00  mov     eax, edi
0x180002b02  add     rsp, 28h
0x180002b06  pop     rdi
0x180002b07  pop     rsi
0x180002b08  pop     rbp
0x180002b09  pop     rbx
0x180002b0a  retn
```
