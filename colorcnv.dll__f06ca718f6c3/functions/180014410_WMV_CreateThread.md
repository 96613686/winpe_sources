# WMV_CreateThread

- ea: `0x180014410`
- end: `0x180014472`
- name: `WMV_CreateThread`
- size: `98`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD ExitCode, LPDWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010f28`

## callees

- `0x180014410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001444a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001444a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180014434`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180014434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014461`

## pseudocode

```c
void *__fastcall WMV_CreateThread(
        __int64 a1,
        __int64 a2,
        DWORD (__stdcall *a3)(LPVOID lpThreadParameter),
        void *a4,
        DWORD ExitCode,
        LPDWORD lpThreadId)
{
  HANDLE Thread; // rax
  void *v7; // rbx

  ExitCode = 0;
  Thread = CreateThread(0, 0, a3, a4, 0, lpThreadId);
  v7 = Thread;
  if ( Thread && (!GetExitCodeThread(Thread, &ExitCode) || ExitCode != 259) )
  {
    CloseHandle(v7);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180014410  push    rbx
0x180014412  sub     rsp, 30h
0x180014416  mov     rax, [rsp+38h+arg_28]
0x18001441b  xor     edx, edx; dwStackSize
0x18001441d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180014422  xor     ecx, ecx; lpThreadAttributes
0x180014424  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001442c  mov     [rsp+38h+ExitCode], 0
0x180014434  call    cs:__imp_CreateThread
0x18001443a  mov     rbx, rax
0x18001443d  test    rax, rax
0x180014440  jz      short loc_180014469
0x180014442  lea     rdx, [rsp+38h+ExitCode]; lpExitCode
0x180014447  mov     rcx, rax; hThread
0x18001444a  call    cs:__imp_GetExitCodeThread
0x180014450  test    eax, eax
0x180014452  jz      short loc_18001445E
0x180014454  cmp     [rsp+38h+ExitCode], 103h
0x18001445c  jz      short loc_180014469
0x18001445e  mov     rcx, rbx; hObject
0x180014461  call    cs:__imp_CloseHandle
0x180014467  xor     ebx, ebx
0x180014469  mov     rax, rbx
0x18001446c  add     rsp, 30h
0x180014470  pop     rbx
0x180014471  retn
```
