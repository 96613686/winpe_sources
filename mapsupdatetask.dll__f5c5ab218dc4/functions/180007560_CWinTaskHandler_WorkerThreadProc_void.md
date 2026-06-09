# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180007560`
- end: `0x1800075cb`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180007560`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800075b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800075b9`

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
0x180007560  push    rbx
0x180007562  push    rbp
0x180007563  push    rsi
0x180007564  push    rdi
0x180007565  sub     rsp, 28h
0x180007569  mov     rax, [rcx]
0x18000756c  mov     rbx, rcx
0x18000756f  mov     ebp, [rcx+10h]
0x180007572  xor     esi, esi
0x180007574  mov     rax, [rax+40h]
0x180007578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000757d  mov     rcx, [rbx+30h]
0x180007581  mov     edi, eax
0x180007583  mov     rdx, [rcx]
0x180007586  mov     rax, [rdx+20h]
0x18000758a  mov     edx, edi
0x18000758c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007591  test    ebp, ebp
0x180007593  jz      short loc_1800075A1
0x180007595  mov     rsi, [rbx+18h]
0x180007599  mov     qword ptr [rbx+18h], 0
0x1800075a1  mov     rax, [rbx]
0x1800075a4  mov     rcx, rbx
0x1800075a7  mov     rax, [rax+10h]
0x1800075ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b0  test    ebp, ebp
0x1800075b2  jz      short loc_1800075C0
0x1800075b4  mov     edx, edi; dwExitCode
0x1800075b6  mov     rcx, rsi; hLibModule
0x1800075b9  call    cs:__imp_FreeLibraryAndExitThread
0x1800075bf  int     3; Trap to Debugger
0x1800075c0  mov     eax, edi
0x1800075c2  add     rsp, 28h
0x1800075c6  pop     rdi
0x1800075c7  pop     rsi
0x1800075c8  pop     rbp
0x1800075c9  pop     rbx
0x1800075ca  retn
```
