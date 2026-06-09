# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180003fe0`
- end: `0x18000404b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003fe0`
- `0x18000a010`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180004039`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180004039`

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
0x180003fe0  push    rbx
0x180003fe2  push    rbp
0x180003fe3  push    rsi
0x180003fe4  push    rdi
0x180003fe5  sub     rsp, 28h
0x180003fe9  mov     rax, [rcx]
0x180003fec  mov     rbx, rcx
0x180003fef  mov     ebp, [rcx+10h]
0x180003ff2  xor     esi, esi
0x180003ff4  mov     rax, [rax+40h]
0x180003ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ffd  mov     rcx, [rbx+30h]
0x180004001  mov     edi, eax
0x180004003  mov     rdx, [rcx]
0x180004006  mov     rax, [rdx+20h]
0x18000400a  mov     edx, edi
0x18000400c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004011  test    ebp, ebp
0x180004013  jz      short loc_180004021
0x180004015  mov     rsi, [rbx+18h]
0x180004019  mov     qword ptr [rbx+18h], 0
0x180004021  mov     rax, [rbx]
0x180004024  mov     rcx, rbx
0x180004027  mov     rax, [rax+10h]
0x18000402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004030  test    ebp, ebp
0x180004032  jz      short loc_180004040
0x180004034  mov     edx, edi; dwExitCode
0x180004036  mov     rcx, rsi; hLibModule
0x180004039  call    cs:__imp_FreeLibraryAndExitThread
0x180004040  mov     eax, edi
0x180004042  add     rsp, 28h
0x180004046  pop     rdi
0x180004047  pop     rsi
0x180004048  pop     rbp
0x180004049  pop     rbx
0x18000404a  retn
```
