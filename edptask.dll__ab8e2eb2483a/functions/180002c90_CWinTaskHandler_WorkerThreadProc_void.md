# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002c90`
- end: `0x180002cfb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002c90`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002ce9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180002ce9`

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
0x180002c90  push    rbx
0x180002c92  push    rbp
0x180002c93  push    rsi
0x180002c94  push    rdi
0x180002c95  sub     rsp, 28h
0x180002c99  mov     rax, [rcx]
0x180002c9c  mov     rbx, rcx
0x180002c9f  mov     ebp, [rcx+10h]
0x180002ca2  xor     esi, esi
0x180002ca4  mov     rax, [rax+40h]
0x180002ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cad  mov     rcx, [rbx+30h]
0x180002cb1  mov     edi, eax
0x180002cb3  mov     rdx, [rcx]
0x180002cb6  mov     rax, [rdx+20h]
0x180002cba  mov     edx, edi
0x180002cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc1  test    ebp, ebp
0x180002cc3  jz      short loc_180002CD1
0x180002cc5  mov     rsi, [rbx+18h]
0x180002cc9  mov     qword ptr [rbx+18h], 0
0x180002cd1  mov     rax, [rbx]
0x180002cd4  mov     rcx, rbx
0x180002cd7  mov     rax, [rax+10h]
0x180002cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce0  test    ebp, ebp
0x180002ce2  jz      short loc_180002CF0
0x180002ce4  mov     edx, edi; dwExitCode
0x180002ce6  mov     rcx, rsi; hLibModule
0x180002ce9  call    cs:__imp_FreeLibraryAndExitThread
0x180002cef  int     3; Trap to Debugger
0x180002cf0  mov     eax, edi
0x180002cf2  add     rsp, 28h
0x180002cf6  pop     rdi
0x180002cf7  pop     rsi
0x180002cf8  pop     rbp
0x180002cf9  pop     rbx
0x180002cfa  retn
```
