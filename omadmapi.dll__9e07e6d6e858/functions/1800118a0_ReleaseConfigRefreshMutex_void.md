# ReleaseConfigRefreshMutex(void *)

- ea: `0x1800118a0`
- end: `0x180011917`
- name: `?ReleaseConfigRefreshMutex@@YAXPEAX@Z`
- size: `119`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800118a0`
- `0x180021ec4`
- `0x18002206c`
- `0x180022160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800118c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800118c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118f2`

## pseudocode

```c
void __fastcall ReleaseConfigRefreshMutex(HANDLE hObject)
{
  CConfigRefreshLogger *Logger; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  CConfigRefreshLogger *v5; // rax
  __int64 v6; // r8
  int v7; // r9d

  Logger = CConfigRefreshLogger::GetLogger();
  CConfigRefreshLogger::LogConfigRefreshMutexReleaseStart(Logger);
  v3 = 0;
  if ( hObject )
  {
    if ( !ReleaseMutex(hObject) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(hObject);
  }
  v5 = CConfigRefreshLogger::GetLogger();
  CConfigRefreshLogger::LogConfigRefreshMutexReleaseEnd(v5, v3, v6, v7);
}

```

## disassembly

```asm
0x1800118a0  mov     [rsp+arg_0], rbx
0x1800118a5  push    rdi
0x1800118a6  sub     rsp, 20h
0x1800118aa  mov     rdi, rcx
0x1800118ad  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x1800118b2  mov     rcx, rax; this
0x1800118b5  call    ?LogConfigRefreshMutexReleaseStart@CConfigRefreshLogger@@QEAAXXZ; CConfigRefreshLogger::LogConfigRefreshMutexReleaseStart(void)
0x1800118ba  xor     ebx, ebx
0x1800118bc  test    rdi, rdi
0x1800118bf  jz      short loc_1800118FE
0x1800118c1  mov     rcx, rdi; hMutex
0x1800118c4  call    cs:__imp_ReleaseMutex
0x1800118cb  nop     dword ptr [rax+rax+00h]
0x1800118d0  test    eax, eax
0x1800118d2  jnz     short loc_1800118EF
0x1800118d4  call    cs:__imp_GetLastError
0x1800118db  nop     dword ptr [rax+rax+00h]
0x1800118e0  mov     ebx, eax
0x1800118e2  test    eax, eax
0x1800118e4  jle     short loc_1800118EF
0x1800118e6  movzx   ebx, ax
0x1800118e9  or      ebx, 80070000h
0x1800118ef  mov     rcx, rdi; hObject
0x1800118f2  call    cs:__imp_CloseHandle
0x1800118f9  nop     dword ptr [rax+rax+00h]
0x1800118fe  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x180011903  mov     edx, ebx; int
0x180011905  mov     rcx, rax; this
0x180011908  mov     rbx, [rsp+28h+arg_0]
0x18001190d  add     rsp, 20h
0x180011911  pop     rdi
0x180011912  jmp     ?LogConfigRefreshMutexReleaseEnd@CConfigRefreshLogger@@QEAAXJ@Z; CConfigRefreshLogger::LogConfigRefreshMutexReleaseEnd(long)
```
