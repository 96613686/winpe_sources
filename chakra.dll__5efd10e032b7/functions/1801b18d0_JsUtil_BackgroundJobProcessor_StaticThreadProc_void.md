# JsUtil::BackgroundJobProcessor::StaticThreadProc(void *)

- ea: `0x1801b18d0`
- end: `0x1801b198b`
- name: `?StaticThreadProc@BackgroundJobProcessor@JsUtil@@CAIPEAX@Z`
- size: `187`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1801b18d0`
- `0x1801b1994`
- `0x1801b34e4`
- `0x180395ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801b1931`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801b1953`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801b1931`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801b1953`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1801b1900`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1801b1900`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibraryAndExitThread` at `0x1801b196b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibraryAndExitThread` at `0x1801b196b`

## pseudocode

```c
__int64 __fastcall JsUtil::BackgroundJobProcessor::StaticThreadProc(HANDLE *a1)
{
  JsUtil::BackgroundJobProcessor *v1; // rsi
  HMODULE phModule[4]; // [rsp+28h] [rbp-20h] BYREF

  Memory::X64WriteBarrierCardTableManager::OnThreadInit((Memory::X64WriteBarrierCardTableManager *)a1);
  phModule[0] = 0;
  if ( !GetModuleHandleExW(0, &Filename, phModule) )
    phModule[0] = 0;
  v1 = (JsUtil::BackgroundJobProcessor *)a1[37];
  phModule[1] = (HMODULE)(a1 + 3);
  SetEvent(a1[3]);
  JsUtil::BackgroundJobProcessor::Run(v1, (struct JsUtil::ParallelThreadData *)a1);
  SetEvent(a1[3]);
  if ( phModule[0] )
    FreeLibraryAndExitThread(phModule[0], 0);
  return 0;
}

```

## disassembly

```asm
0x1801b18d0  mov     [rsp+arg_8], rbx
0x1801b18d5  mov     [rsp+arg_10], rsi
0x1801b18da  mov     [rsp+arg_0], rcx
0x1801b18df  push    rdi
0x1801b18e0  sub     rsp, 40h
0x1801b18e4  call    ?OnThreadInit@X64WriteBarrierCardTableManager@Memory@@QEAA_NXZ; Memory::X64WriteBarrierCardTableManager::OnThreadInit(void)
0x1801b18e9  mov     [rsp+48h+phModule], 0
0x1801b18f2  lea     r8, [rsp+48h+phModule]; phModule
0x1801b18f7  lea     rdx, Filename; lpModuleName
0x1801b18fe  xor     ecx, ecx; dwFlags
0x1801b1900  call    cs:__imp_GetModuleHandleExW
0x1801b1907  nop     dword ptr [rax+rax+00h]
0x1801b190c  test    eax, eax
0x1801b190e  jnz     short loc_1801B1919
0x1801b1910  mov     [rsp+48h+phModule], 0
0x1801b1919  mov     rdi, [rsp+48h+arg_0]
0x1801b191e  mov     rsi, [rdi+128h]
0x1801b1925  lea     rbx, [rdi+18h]
0x1801b1929  mov     [rsp+48h+var_18], rbx
0x1801b192e  mov     rcx, [rbx]; hEvent
0x1801b1931  call    cs:__imp_SetEvent
0x1801b1938  nop     dword ptr [rax+rax+00h]
0x1801b193d  nop
0x1801b193e  mov     rdx, rdi; struct JsUtil::ParallelThreadData *
0x1801b1941  mov     rcx, rsi; this
0x1801b1944  call    ?Run@BackgroundJobProcessor@JsUtil@@AEAAXPEAUParallelThreadData@2@@Z; JsUtil::BackgroundJobProcessor::Run(JsUtil::ParallelThreadData *)
0x1801b1949  jmp     short loc_1801B1950
0x1801b194b  mov     rbx, [rsp+48h+var_18]
0x1801b1950  mov     rcx, [rbx]; hEvent
0x1801b1953  call    cs:__imp_SetEvent
0x1801b195a  nop     dword ptr [rax+rax+00h]
0x1801b195f  mov     rcx, [rsp+48h+phModule]; hLibModule
0x1801b1964  test    rcx, rcx
0x1801b1967  jz      short loc_1801B1978
0x1801b1969  xor     edx, edx; dwExitCode
0x1801b196b  call    cs:__imp_FreeLibraryAndExitThread
0x1801b1972  nop     dword ptr [rax+rax+00h]
0x1801b1977  int     3; Trap to Debugger
0x1801b1978  xor     eax, eax
0x1801b197a  mov     rbx, [rsp+48h+arg_8]
0x1801b197f  mov     rsi, [rsp+48h+arg_10]
0x1801b1984  add     rsp, 40h
0x1801b1988  pop     rdi
0x1801b1989  retn
0x1805aebde  mov     [rsp+arg_0], rcx
0x1805aebe3  mov     [rsp+arg_8], rdx
0x1805aebe8  push    rbp
0x1805aebe9  sub     rsp, 20h
0x1805aebed  mov     rbp, rdx
0x1805aebf0  mov     [rbp+38h], rcx
0x1805aebf4  call    ?Flush@Output@@SAXXZ; Output::Flush(void)
0x1805aebf9  mov     dword ptr [rbp+20h], 0
0x1805aec00  mov     eax, [rbp+20h]
0x1805aec03  add     rsp, 20h
0x1805aec07  pop     rbp
0x1805aec08  retn
```
