# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000c440`
- end: `0x18000c4ab`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000c440`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000c499`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000c499`

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
0x18000c440  push    rbx
0x18000c442  push    rbp
0x18000c443  push    rsi
0x18000c444  push    rdi
0x18000c445  sub     rsp, 28h
0x18000c449  mov     rax, [rcx]
0x18000c44c  mov     rbx, rcx
0x18000c44f  mov     ebp, [rcx+10h]
0x18000c452  xor     esi, esi
0x18000c454  mov     rax, [rax+40h]
0x18000c458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c45d  mov     rcx, [rbx+30h]
0x18000c461  mov     edi, eax
0x18000c463  mov     rdx, [rcx]
0x18000c466  mov     rax, [rdx+20h]
0x18000c46a  mov     edx, edi
0x18000c46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c471  test    ebp, ebp
0x18000c473  jz      short loc_18000C481
0x18000c475  mov     rsi, [rbx+18h]
0x18000c479  mov     qword ptr [rbx+18h], 0
0x18000c481  mov     rax, [rbx]
0x18000c484  mov     rcx, rbx
0x18000c487  mov     rax, [rax+10h]
0x18000c48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c490  test    ebp, ebp
0x18000c492  jz      short loc_18000C4A0
0x18000c494  mov     edx, edi; dwExitCode
0x18000c496  mov     rcx, rsi; hLibModule
0x18000c499  call    cs:__imp_FreeLibraryAndExitThread
0x18000c49f  int     3; Trap to Debugger
0x18000c4a0  mov     eax, edi
0x18000c4a2  add     rsp, 28h
0x18000c4a6  pop     rdi
0x18000c4a7  pop     rsi
0x18000c4a8  pop     rbp
0x18000c4a9  pop     rbx
0x18000c4aa  retn
```
