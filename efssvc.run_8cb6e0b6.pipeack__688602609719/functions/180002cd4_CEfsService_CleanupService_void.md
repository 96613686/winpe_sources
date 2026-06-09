# CEfsService::CleanupService(void)

- ea: `0x180002cd4`
- end: `0x180002e0a`
- name: `?CleanupService@CEfsService@@QEAAXXZ`
- size: `310`
- prototype: `void __fastcall(LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180002f60`
- `0x180002fb0`

## callees

- `0x1800018a4`
- `0x180002cd4`
- `0x180003320`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002d00`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180002d41`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180002d41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002d78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002d64`
- `ntdll!EtwEventUnregister` at `0x180002de1`
- `ntdll!EtwEventUnregister` at `0x180002de1`
- `ntdll!NtClose` at `0x180002d15`
- `ntdll!NtClose` at `0x180002d15`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002da9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002da9`
- `EFSCORE!EfsUnInitialize` at `0x180002d8f`
- `EFSCORE!EfsUnInitialize` at `0x180002d8f`

## pseudocode

```c
void __fastcall CEfsService::CleanupService(LPSERVICE_STATUS lpServiceStatus)
{
  void *v2; // rcx
  void *v3; // rcx
  PSID v4; // rdi
  HANDLE ProcessHeap; // rax

  if ( *(_QWORD *)&lpServiceStatus[1].dwCurrentState )
    CEfsService::UpdateServiceStatus(lpServiceStatus, 0, 3u);
  v2 = *(void **)&lpServiceStatus[1].dwWin32ExitCode;
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)&lpServiceStatus[1].dwCheckPoint;
  if ( v3 )
    NtClose(v3);
  if ( *(_QWORD *)&lpServiceStatus[1].dwCurrentState )
    CEfsService::UpdateServiceStatus(lpServiceStatus, 0, 3u);
  if ( qword_180018868 )
  {
    RpcServerInterfaceGroupClose();
    qword_180018868 = 0;
  }
  v4 = g_AdminSid;
  if ( g_AdminSid )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    g_AdminSid = 0;
  }
  EfsUnInitialize();
  if ( g_hSha256Alg )
  {
    BCryptCloseAlgorithmProvider(g_hSha256Alg, 0);
    g_hSha256Alg = 0;
  }
  if ( *(_QWORD *)&lpServiceStatus[1].dwCurrentState )
    CEfsService::UpdateServiceStatus(lpServiceStatus, 0, 1u);
  if ( g_hPublisher )
  {
    EtwEventUnregister();
    g_hPublisher = 0;
  }
  operator delete(lpServiceStatus);
}

```

## disassembly

```asm
0x180002cd4  mov     [rsp+arg_0], rbx
0x180002cd9  push    rdi
0x180002cda  sub     rsp, 20h
0x180002cde  cmp     qword ptr [rcx+20h], 0
0x180002ce3  mov     rbx, rcx
0x180002ce6  mov     edi, 3
0x180002ceb  jz      short loc_180002CF7
0x180002ced  mov     r8d, edi; unsigned int
0x180002cf0  xor     edx, edx; unsigned int
0x180002cf2  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002cf7  mov     rcx, [rbx+28h]; hObject
0x180002cfb  test    rcx, rcx
0x180002cfe  jz      short loc_180002D0C
0x180002d00  call    cs:__imp_CloseHandle
0x180002d07  nop     dword ptr [rax+rax+00h]
0x180002d0c  mov     rcx, [rbx+30h]; Handle
0x180002d10  test    rcx, rcx
0x180002d13  jz      short loc_180002D21
0x180002d15  call    cs:__imp_NtClose
0x180002d1c  nop     dword ptr [rax+rax+00h]
0x180002d21  cmp     qword ptr [rbx+20h], 0
0x180002d26  jz      short loc_180002D35
0x180002d28  mov     r8d, edi; unsigned int
0x180002d2b  xor     edx, edx; unsigned int
0x180002d2d  mov     rcx, rbx; lpServiceStatus
0x180002d30  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002d35  mov     rcx, cs:qword_180018868
0x180002d3c  test    rcx, rcx
0x180002d3f  jz      short loc_180002D58
0x180002d41  call    cs:__imp_RpcServerInterfaceGroupClose
0x180002d48  nop     dword ptr [rax+rax+00h]
0x180002d4d  mov     cs:qword_180018868, 0
0x180002d58  mov     rdi, cs:g_AdminSid
0x180002d5f  test    rdi, rdi
0x180002d62  jz      short loc_180002D8F
0x180002d64  call    cs:__imp_GetProcessHeap
0x180002d6b  nop     dword ptr [rax+rax+00h]
0x180002d70  mov     r8, rdi; lpMem
0x180002d73  xor     edx, edx; dwFlags
0x180002d75  mov     rcx, rax; hHeap
0x180002d78  call    cs:__imp_HeapFree
0x180002d7f  nop     dword ptr [rax+rax+00h]
0x180002d84  mov     cs:g_AdminSid, 0
0x180002d8f  call    cs:__imp_EfsUnInitialize
0x180002d96  nop     dword ptr [rax+rax+00h]
0x180002d9b  mov     rcx, cs:g_hSha256Alg; hAlgorithm
0x180002da2  test    rcx, rcx
0x180002da5  jz      short loc_180002DC0
0x180002da7  xor     edx, edx; dwFlags
0x180002da9  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002db0  nop     dword ptr [rax+rax+00h]
0x180002db5  mov     cs:g_hSha256Alg, 0
0x180002dc0  cmp     qword ptr [rbx+20h], 0
0x180002dc5  jz      short loc_180002DD5
0x180002dc7  xor     edx, edx; unsigned int
0x180002dc9  mov     rcx, rbx; lpServiceStatus
0x180002dcc  lea     r8d, [rdx+1]; unsigned int
0x180002dd0  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002dd5  mov     rcx, cs:g_hPublisher
0x180002ddc  test    rcx, rcx
0x180002ddf  jz      short loc_180002DF8
0x180002de1  call    cs:__imp_EtwEventUnregister
0x180002de8  nop     dword ptr [rax+rax+00h]
0x180002ded  mov     cs:g_hPublisher, 0
0x180002df8  mov     rcx, rbx; Block
0x180002dfb  mov     rbx, [rsp+28h+arg_0]
0x180002e00  add     rsp, 20h
0x180002e04  pop     rdi
0x180002e05  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
