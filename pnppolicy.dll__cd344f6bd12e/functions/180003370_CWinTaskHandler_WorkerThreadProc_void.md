# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180003370`
- end: `0x1800033db`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003370`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800033c9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800033c9`

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
0x180003370  push    rbx
0x180003372  push    rbp
0x180003373  push    rsi
0x180003374  push    rdi
0x180003375  sub     rsp, 28h
0x180003379  mov     rax, [rcx]
0x18000337c  mov     rbx, rcx
0x18000337f  mov     ebp, [rcx+10h]
0x180003382  xor     esi, esi
0x180003384  mov     rax, [rax+40h]
0x180003388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338d  mov     rcx, [rbx+30h]
0x180003391  mov     edi, eax
0x180003393  mov     rdx, [rcx]
0x180003396  mov     rax, [rdx+20h]
0x18000339a  mov     edx, edi
0x18000339c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a1  test    ebp, ebp
0x1800033a3  jz      short loc_1800033B1
0x1800033a5  mov     rsi, [rbx+18h]
0x1800033a9  mov     qword ptr [rbx+18h], 0
0x1800033b1  mov     rax, [rbx]
0x1800033b4  mov     rcx, rbx
0x1800033b7  mov     rax, [rax+10h]
0x1800033bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c0  test    ebp, ebp
0x1800033c2  jz      short loc_1800033D0
0x1800033c4  mov     edx, edi; dwExitCode
0x1800033c6  mov     rcx, rsi; hLibModule
0x1800033c9  call    cs:__imp_FreeLibraryAndExitThread
0x1800033cf  int     3; Trap to Debugger
0x1800033d0  mov     eax, edi
0x1800033d2  add     rsp, 28h
0x1800033d6  pop     rdi
0x1800033d7  pop     rsi
0x1800033d8  pop     rbp
0x1800033d9  pop     rbx
0x1800033da  retn
```
