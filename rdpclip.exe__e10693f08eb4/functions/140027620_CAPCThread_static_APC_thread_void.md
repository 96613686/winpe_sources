# CAPCThread::static_APC_thread(void *)

- ea: `0x140027620`
- end: `0x14002766d`
- name: `?static_APC_thread@CAPCThread@@SAKPEAX@Z`
- size: `77`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140027620`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x140027666`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x140027666`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002764e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002764e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002765b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002765b`

## pseudocode

```c
void __fastcall __noreturn CAPCThread::static_APC_thread(_QWORD *Parameter)
{
  void *v1; // rbx
  HMODULE v2; // rdi

  v1 = (void *)Parameter[8];
  v2 = (HMODULE)Parameter[9];
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Parameter[5] + 16LL))(Parameter[5]);
  while ( WaitForSingleObjectEx(v1, 0xFFFFFFFF, 1) )
    ;
  CloseHandle(v1);
  FreeLibraryAndExitThread(v2, 0);
}

```

## disassembly

```asm
0x140027620  mov     [rsp+arg_0], rbx
0x140027625  push    rdi
0x140027626  sub     rsp, 20h
0x14002762a  mov     rbx, [rcx+40h]
0x14002762e  mov     rdi, [rcx+48h]
0x140027632  mov     rcx, [rcx+28h]
0x140027636  mov     rax, [rcx]
0x140027639  mov     rax, [rax+10h]
0x14002763d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027642  mov     r8d, 1; bAlertable
0x140027648  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002764b  mov     rcx, rbx; hHandle
0x14002764e  call    cs:__imp_WaitForSingleObjectEx
0x140027654  test    eax, eax
0x140027656  jnz     short loc_140027642
0x140027658  mov     rcx, rbx; hObject
0x14002765b  call    cs:__imp_CloseHandle
0x140027661  xor     edx, edx; dwExitCode
0x140027663  mov     rcx, rdi; hLibModule
0x140027666  call    cs:__imp_FreeLibraryAndExitThread
```
