# CEfsService::CleanupService(void)

- ea: `0x180002c60`
- end: `0x180002d66`
- name: `?CleanupService@CEfsService@@QEAAXXZ`
- size: `262`
- prototype: `void __fastcall(LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180002ea0`
- `0x180002ee0`

## callees

- `0x180001894`
- `0x180002c60`
- `0x1800031f4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002c8c`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180002cc1`
- `RPCRT4!RpcServerInterfaceGroupClose` at `0x180002cc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002cec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002cec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002cde`
- `ntdll!EtwEventUnregister` at `0x180002d43`
- `ntdll!EtwEventUnregister` at `0x180002d43`
- `ntdll!NtClose` at `0x180002c9b`
- `ntdll!NtClose` at `0x180002c9b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002d11`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180002d11`
- `EFSCORE!EfsUnInitialize` at `0x180002cfd`
- `EFSCORE!EfsUnInitialize` at `0x180002cfd`

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
  if ( qword_180017868 )
  {
    RpcServerInterfaceGroupClose();
    qword_180017868 = 0;
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
0x180002c60  mov     [rsp+arg_0], rbx
0x180002c65  push    rdi
0x180002c66  sub     rsp, 20h
0x180002c6a  cmp     qword ptr [rcx+20h], 0
0x180002c6f  mov     rbx, rcx
0x180002c72  mov     edi, 3
0x180002c77  jz      short loc_180002C83
0x180002c79  mov     r8d, edi; unsigned int
0x180002c7c  xor     edx, edx; unsigned int
0x180002c7e  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002c83  mov     rcx, [rbx+28h]; hObject
0x180002c87  test    rcx, rcx
0x180002c8a  jz      short loc_180002C92
0x180002c8c  call    cs:__imp_CloseHandle
0x180002c92  mov     rcx, [rbx+30h]; Handle
0x180002c96  test    rcx, rcx
0x180002c99  jz      short loc_180002CA1
0x180002c9b  call    cs:__imp_NtClose
0x180002ca1  cmp     qword ptr [rbx+20h], 0
0x180002ca6  jz      short loc_180002CB5
0x180002ca8  mov     r8d, edi; unsigned int
0x180002cab  xor     edx, edx; unsigned int
0x180002cad  mov     rcx, rbx; lpServiceStatus
0x180002cb0  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002cb5  mov     rcx, cs:qword_180017868
0x180002cbc  test    rcx, rcx
0x180002cbf  jz      short loc_180002CD2
0x180002cc1  call    cs:__imp_RpcServerInterfaceGroupClose
0x180002cc7  mov     cs:qword_180017868, 0
0x180002cd2  mov     rdi, cs:g_AdminSid
0x180002cd9  test    rdi, rdi
0x180002cdc  jz      short loc_180002CFD
0x180002cde  call    cs:__imp_GetProcessHeap
0x180002ce4  mov     r8, rdi; lpMem
0x180002ce7  xor     edx, edx; dwFlags
0x180002ce9  mov     rcx, rax; hHeap
0x180002cec  call    cs:__imp_HeapFree
0x180002cf2  mov     cs:g_AdminSid, 0
0x180002cfd  call    cs:__imp_EfsUnInitialize
0x180002d03  mov     rcx, cs:g_hSha256Alg; hAlgorithm
0x180002d0a  test    rcx, rcx
0x180002d0d  jz      short loc_180002D22
0x180002d0f  xor     edx, edx; dwFlags
0x180002d11  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002d17  mov     cs:g_hSha256Alg, 0
0x180002d22  cmp     qword ptr [rbx+20h], 0
0x180002d27  jz      short loc_180002D37
0x180002d29  xor     edx, edx; unsigned int
0x180002d2b  mov     rcx, rbx; lpServiceStatus
0x180002d2e  lea     r8d, [rdx+1]; unsigned int
0x180002d32  call    ?UpdateServiceStatus@CEfsService@@AEAAJKK@Z; CEfsService::UpdateServiceStatus(ulong,ulong)
0x180002d37  mov     rcx, cs:g_hPublisher
0x180002d3e  test    rcx, rcx
0x180002d41  jz      short loc_180002D54
0x180002d43  call    cs:__imp_EtwEventUnregister
0x180002d49  mov     cs:g_hPublisher, 0
0x180002d54  mov     rcx, rbx; Block
0x180002d57  mov     rbx, [rsp+28h+arg_0]
0x180002d5c  add     rsp, 20h
0x180002d60  pop     rdi
0x180002d61  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
