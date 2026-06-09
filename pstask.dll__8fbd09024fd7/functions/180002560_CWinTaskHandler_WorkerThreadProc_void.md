# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180002560`
- end: `0x1800025cb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002560`
- `0x180003010`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x1800025b9`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1800025b9`

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
0x180002560  push    rbx
0x180002562  push    rbp
0x180002563  push    rsi
0x180002564  push    rdi
0x180002565  sub     rsp, 28h
0x180002569  mov     rax, [rcx]
0x18000256c  mov     rbx, rcx
0x18000256f  mov     ebp, [rcx+10h]
0x180002572  xor     esi, esi
0x180002574  mov     rax, [rax+40h]
0x180002578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257d  mov     rcx, [rbx+30h]
0x180002581  mov     edi, eax
0x180002583  mov     rdx, [rcx]
0x180002586  mov     rax, [rdx+20h]
0x18000258a  mov     edx, edi
0x18000258c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002591  test    ebp, ebp
0x180002593  jz      short loc_1800025A1
0x180002595  mov     rsi, [rbx+18h]
0x180002599  mov     qword ptr [rbx+18h], 0
0x1800025a1  mov     rax, [rbx]
0x1800025a4  mov     rcx, rbx
0x1800025a7  mov     rax, [rax+10h]
0x1800025ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b0  test    ebp, ebp
0x1800025b2  jz      short loc_1800025C0
0x1800025b4  mov     edx, edi; dwExitCode
0x1800025b6  mov     rcx, rsi; hLibModule
0x1800025b9  call    cs:__imp_FreeLibraryAndExitThread
0x1800025c0  mov     eax, edi
0x1800025c2  add     rsp, 28h
0x1800025c6  pop     rdi
0x1800025c7  pop     rsi
0x1800025c8  pop     rbp
0x1800025c9  pop     rbx
0x1800025ca  retn
```
