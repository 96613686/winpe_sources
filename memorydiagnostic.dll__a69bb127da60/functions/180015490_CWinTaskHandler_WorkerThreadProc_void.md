# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180015490`
- end: `0x1800154fb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180015490`
- `0x180023010`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x1800154e9`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1800154e9`

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
0x180015490  push    rbx
0x180015492  push    rbp
0x180015493  push    rsi
0x180015494  push    rdi
0x180015495  sub     rsp, 28h
0x180015499  mov     rax, [rcx]
0x18001549c  mov     rbx, rcx
0x18001549f  mov     ebp, [rcx+10h]
0x1800154a2  xor     esi, esi
0x1800154a4  mov     rax, [rax+40h]
0x1800154a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ad  mov     rcx, [rbx+30h]
0x1800154b1  mov     edi, eax
0x1800154b3  mov     rdx, [rcx]
0x1800154b6  mov     rax, [rdx+20h]
0x1800154ba  mov     edx, edi
0x1800154bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c1  test    ebp, ebp
0x1800154c3  jz      short loc_1800154D1
0x1800154c5  mov     rsi, [rbx+18h]
0x1800154c9  mov     qword ptr [rbx+18h], 0
0x1800154d1  mov     rax, [rbx]
0x1800154d4  mov     rcx, rbx
0x1800154d7  mov     rax, [rax+10h]
0x1800154db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154e0  test    ebp, ebp
0x1800154e2  jz      short loc_1800154F0
0x1800154e4  mov     edx, edi; dwExitCode
0x1800154e6  mov     rcx, rsi; hLibModule
0x1800154e9  call    cs:__imp_FreeLibraryAndExitThread
0x1800154f0  mov     eax, edi
0x1800154f2  add     rsp, 28h
0x1800154f6  pop     rdi
0x1800154f7  pop     rsi
0x1800154f8  pop     rbp
0x1800154f9  pop     rbx
0x1800154fa  retn
```
