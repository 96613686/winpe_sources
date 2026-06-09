# CReflectedDump::Cleanup(void)

- ea: `0x180046e14`
- end: `0x180046eb0`
- name: `?Cleanup@CReflectedDump@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(CReflectedDump *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180046acc`
- `0x180047adc`

## callees

- `0x180004c9e`
- `0x180004e87`
- `0x180046e14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180046e55`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180046e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046e9a`
- `wer!WerpAddTerminationReason` at `0x180046e6e`
- `wer!WerpAddTerminationReason` at `0x180046e6e`

## pseudocode

```c
void __fastcall CReflectedDump::Cleanup(CReflectedDump *this)
{
  const WCHAR *v1; // rdi
  void *v3; // rcx
  DWORD ProcessId; // eax
  void *v5; // rcx

  v1 = (const WCHAR *)((char *)this + 8);
  if ( *((_WORD *)this + 4) && !*((_DWORD *)this + 135) )
  {
    DeleteFileW_0(v1);
    *v1 = 0;
  }
  v3 = (void *)*((_QWORD *)this + 66);
  if ( (unsigned __int64)v3 + 1 > 1 )
  {
    ProcessId = GetProcessId(v3);
    WerpAddTerminationReason(ProcessId, 4, L"WerReflectedProcessCleanup");
    TerminateProcess_0(*((HANDLE *)this + 66), 0);
    v5 = (void *)*((_QWORD *)this + 66);
    *((_QWORD *)this + 66) = 0;
    if ( (unsigned __int64)v5 + 1 > 1 )
      CloseHandle(v5);
  }
}

```

## disassembly

```asm
0x180046e14  mov     [rsp+arg_0], rbx
0x180046e19  mov     [rsp+arg_8], rsi
0x180046e1e  push    rdi
0x180046e1f  sub     rsp, 20h
0x180046e23  lea     rdi, [rcx+8]
0x180046e27  xor     esi, esi
0x180046e29  mov     rbx, rcx
0x180046e2c  cmp     [rdi], si
0x180046e2f  jz      short loc_180046E44
0x180046e31  cmp     [rcx+21Ch], esi
0x180046e37  jnz     short loc_180046E44
0x180046e39  mov     rcx, rdi; lpFileName
0x180046e3c  call    DeleteFileW_0
0x180046e41  mov     [rdi], si
0x180046e44  mov     rcx, [rbx+210h]; Process
0x180046e4b  lea     rax, [rcx+1]
0x180046e4f  cmp     rax, 1
0x180046e53  jbe     short loc_180046EA0
0x180046e55  call    cs:__imp_GetProcessId
0x180046e5b  mov     r9d, 1
0x180046e61  lea     r8, aWerreflectedpr; "WerReflectedProcessCleanup"
0x180046e68  mov     ecx, eax
0x180046e6a  lea     edx, [r9+3]
0x180046e6e  call    cs:__imp_WerpAddTerminationReason
0x180046e74  mov     rcx, [rbx+210h]; hProcess
0x180046e7b  xor     edx, edx; uExitCode
0x180046e7d  call    TerminateProcess_0
0x180046e82  mov     rcx, [rbx+210h]; hObject
0x180046e89  mov     [rbx+210h], rsi
0x180046e90  lea     rax, [rcx+1]
0x180046e94  cmp     rax, 1
0x180046e98  jbe     short loc_180046EA0
0x180046e9a  call    cs:__imp_CloseHandle
0x180046ea0  mov     rbx, [rsp+28h+arg_0]
0x180046ea5  mov     rsi, [rsp+28h+arg_8]
0x180046eaa  add     rsp, 20h
0x180046eae  pop     rdi
0x180046eaf  retn
```
