# CAPCThread::static_APC_thread(void *)

- ea: `0x180021370`
- end: `0x1800213bd`
- name: `?static_APC_thread@CAPCThread@@SAKPEAX@Z`
- size: `77`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180021370`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800213ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800213ab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002139e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002139e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800213b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800213b6`

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
0x180021370  mov     [rsp+arg_0], rbx
0x180021375  push    rdi
0x180021376  sub     rsp, 20h
0x18002137a  mov     rbx, [rcx+40h]
0x18002137e  mov     rdi, [rcx+48h]
0x180021382  mov     rcx, [rcx+28h]
0x180021386  mov     rax, [rcx]
0x180021389  mov     rax, [rax+10h]
0x18002138d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021392  mov     r8d, 1; bAlertable
0x180021398  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002139b  mov     rcx, rbx; hHandle
0x18002139e  call    cs:__imp_WaitForSingleObjectEx
0x1800213a4  test    eax, eax
0x1800213a6  jnz     short loc_180021392
0x1800213a8  mov     rcx, rbx; hObject
0x1800213ab  call    cs:__imp_CloseHandle
0x1800213b1  xor     edx, edx; dwExitCode
0x1800213b3  mov     rcx, rdi; hLibModule
0x1800213b6  call    cs:__imp_FreeLibraryAndExitThread
```
