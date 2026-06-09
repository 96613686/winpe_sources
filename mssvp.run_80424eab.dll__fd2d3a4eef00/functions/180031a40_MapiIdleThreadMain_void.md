# MapiIdleThreadMain(void *)

- ea: `0x180031a40`
- end: `0x180031a6c`
- name: `?MapiIdleThreadMain@@YAKPEAX@Z`
- size: `44`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800320e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031a49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180031a49`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180031a59`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180031a59`

## string_xrefs

- `0x180031a52`: `MapiIdleThreadMain`

## pseudocode

```c
ULONG __fastcall MapiIdleThreadMain(CMapiManager *Parameter)
{
  HANDLE CurrentThread; // rax

  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, L"MapiIdleThreadMain");
  return CMapiManager::RunMapiIdleThread(Parameter);
}

```

## disassembly

```asm
0x180031a40  push    rbx
0x180031a42  sub     rsp, 20h
0x180031a46  mov     rbx, rcx
0x180031a49  call    cs:__imp_GetCurrentThread
0x180031a4f  mov     rcx, rax; hThread
0x180031a52  lea     rdx, ThreadDescription; "MapiIdleThreadMain"
0x180031a59  call    cs:__imp_SetThreadDescription
0x180031a5f  mov     rcx, rbx; this
0x180031a62  add     rsp, 20h
0x180031a66  pop     rbx
0x180031a67  jmp     ?RunMapiIdleThread@CMapiManager@@QEAAKXZ; CMapiManager::RunMapiIdleThread(void)
```
