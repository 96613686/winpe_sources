# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180014ae0`
- end: `0x180014b4b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180014ae0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180014b39`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180014b39`

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
0x180014ae0  push    rbx
0x180014ae2  push    rbp
0x180014ae3  push    rsi
0x180014ae4  push    rdi
0x180014ae5  sub     rsp, 28h
0x180014ae9  mov     rax, [rcx]
0x180014aec  mov     rbx, rcx
0x180014aef  mov     ebp, [rcx+10h]
0x180014af2  xor     esi, esi
0x180014af4  mov     rax, [rax+40h]
0x180014af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014afd  mov     rcx, [rbx+30h]
0x180014b01  mov     edi, eax
0x180014b03  mov     rdx, [rcx]
0x180014b06  mov     rax, [rdx+20h]
0x180014b0a  mov     edx, edi
0x180014b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b11  test    ebp, ebp
0x180014b13  jz      short loc_180014B21
0x180014b15  mov     rsi, [rbx+18h]
0x180014b19  mov     qword ptr [rbx+18h], 0
0x180014b21  mov     rax, [rbx]
0x180014b24  mov     rcx, rbx
0x180014b27  mov     rax, [rax+10h]
0x180014b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b30  test    ebp, ebp
0x180014b32  jz      short loc_180014B40
0x180014b34  mov     edx, edi; dwExitCode
0x180014b36  mov     rcx, rsi; hLibModule
0x180014b39  call    cs:__imp_FreeLibraryAndExitThread
0x180014b3f  int     3; Trap to Debugger
0x180014b40  mov     eax, edi
0x180014b42  add     rsp, 28h
0x180014b46  pop     rdi
0x180014b47  pop     rsi
0x180014b48  pop     rbp
0x180014b49  pop     rbx
0x180014b4a  retn
```
