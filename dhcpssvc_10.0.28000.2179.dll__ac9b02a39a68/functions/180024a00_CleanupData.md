# CleanupData

- ea: `0x180024a00`
- end: `0x180024de2`
- name: `CleanupData`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027558`

## callees

- `0x180024a00`
- `0x180032f78`
- `0x180091c7c`
- `0x18009886c`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x180024a40`
- `ntdll!RtlDeleteSecurityObject` at `0x180024a63`
- `ntdll!RtlDeleteSecurityObject` at `0x180024a86`
- `ntdll!RtlDeleteSecurityObject` at `0x180024a40`
- `ntdll!RtlDeleteSecurityObject` at `0x180024a63`
- `ntdll!RtlDeleteSecurityObject` at `0x180024a86`
- `KERNEL32!CloseHandle` at `0x180024ca9`
- `KERNEL32!CloseHandle` at `0x180024cc8`
- `KERNEL32!CloseHandle` at `0x180024ce7`
- `KERNEL32!CloseHandle` at `0x180024d2e`
- `KERNEL32!CloseHandle` at `0x180024d4d`
- `KERNEL32!CloseHandle` at `0x180024d6c`
- `KERNEL32!CloseHandle` at `0x180024ca9`
- `KERNEL32!CloseHandle` at `0x180024cc8`
- `KERNEL32!CloseHandle` at `0x180024ce7`
- `KERNEL32!CloseHandle` at `0x180024d2e`
- `KERNEL32!CloseHandle` at `0x180024d4d`
- `KERNEL32!CloseHandle` at `0x180024d6c`
- `KERNEL32!LocalFree` at `0x180024b30`
- `KERNEL32!LocalFree` at `0x180024b63`
- `KERNEL32!LocalFree` at `0x180024b30`
- `KERNEL32!LocalFree` at `0x180024b63`
- `KERNEL32!HeapFree` at `0x180024aae`
- `KERNEL32!HeapFree` at `0x180024ad6`
- `KERNEL32!HeapFree` at `0x180024afe`
- `KERNEL32!HeapFree` at `0x180024b9a`
- `KERNEL32!HeapFree` at `0x180024bc2`
- `KERNEL32!HeapFree` at `0x180024bea`
- `KERNEL32!HeapFree` at `0x180024c12`
- `KERNEL32!HeapFree` at `0x180024c3a`
- `KERNEL32!HeapFree` at `0x180024c62`
- `KERNEL32!HeapFree` at `0x180024c8a`
- `KERNEL32!HeapFree` at `0x180024d0f`
- `KERNEL32!HeapFree` at `0x180024d94`
- `KERNEL32!HeapFree` at `0x180024aae`
- `KERNEL32!HeapFree` at `0x180024ad6`
- `KERNEL32!HeapFree` at `0x180024afe`
- `KERNEL32!HeapFree` at `0x180024b9a`
- `KERNEL32!HeapFree` at `0x180024bc2`
- `KERNEL32!HeapFree` at `0x180024bea`
- `KERNEL32!HeapFree` at `0x180024c12`
- `KERNEL32!HeapFree` at `0x180024c3a`
- `KERNEL32!HeapFree` at `0x180024c62`
- `KERNEL32!HeapFree` at `0x180024c8a`
- `KERNEL32!HeapFree` at `0x180024d0f`
- `KERNEL32!HeapFree` at `0x180024d94`

## pseudocode

```c
int CleanupData()
{
  void **v0; // rax
  void ***v1; // rdi
  __int64 v2; // rsi
  void *v3; // rcx
  void ***v4; // rdi
  __int64 v5; // rsi
  void *v6; // rcx

  LODWORD(v0) = dword_1800FD110;
  if ( dword_1800FD110 )
  {
    --dword_1800FD110;
    LODWORD(v0) = DhcpDeleteExpiredCtxt(0);
    nPendingReqs = 0;
  }
  if ( DhcpGlobalDirSecurityDescriptor )
  {
    LODWORD(v0) = RtlDeleteSecurityObject(&DhcpGlobalDirSecurityDescriptor);
    DhcpGlobalDirSecurityDescriptor = 0;
  }
  if ( DhcpGlobalRegSecurityDescriptor )
  {
    LODWORD(v0) = RtlDeleteSecurityObject(&DhcpGlobalRegSecurityDescriptor);
    DhcpGlobalRegSecurityDescriptor = 0;
  }
  if ( DhcpGlobalServiceSecurityDescriptor )
  {
    LODWORD(v0) = RtlDeleteSecurityObject(&DhcpGlobalServiceSecurityDescriptor);
    DhcpGlobalServiceSecurityDescriptor = 0;
  }
  if ( DhcpSid )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, DhcpSid);
    DhcpSid = 0;
  }
  if ( DhcpAdminSid )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, DhcpAdminSid);
    DhcpAdminSid = 0;
  }
  if ( DhcpServiceSid )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, DhcpServiceSid);
    DhcpServiceSid = 0;
  }
  if ( DhcpGlobalWellKnownSIDsMade )
  {
    v1 = (void ***)&SidData;
    v2 = 11;
    do
    {
      v3 = **v1;
      if ( v3 )
      {
        LocalFree(v3);
        **v1 = 0;
      }
      v1 += 4;
      --v2;
    }
    while ( v2 );
    v4 = (void ***)&BuiltinDomainSidData;
    v5 = 9;
    do
    {
      v0 = *v4;
      v6 = **v4;
      if ( v6 )
      {
        LocalFree(v6);
        v0 = *v4;
        **v4 = 0;
      }
      v4 += 2;
      --v5;
    }
    while ( v5 );
    DhcpGlobalWellKnownSIDsMade = 0;
  }
  if ( DhcpGlobalOemDatabasePath )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemDatabasePath);
    DhcpGlobalOemDatabasePath = 0;
  }
  if ( DhcpGlobalOemDatabaseName )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemDatabaseName);
    DhcpGlobalOemDatabaseName = 0;
  }
  if ( DhcpGlobalOemBackupPath )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemBackupPath);
    DhcpGlobalOemBackupPath = 0;
  }
  if ( DhcpGlobalOemRestorePath )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, DhcpGlobalOemRestorePath);
    DhcpGlobalOemRestorePath = 0;
  }
  if ( DhcpGlobalOemJetBackupPath )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemJetBackupPath);
    DhcpGlobalOemJetBackupPath = 0;
  }
  if ( DhcpGlobalOemJetRestorePath )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalOemJetRestorePath);
    DhcpGlobalOemJetRestorePath = 0;
  }
  if ( DhcpGlobalBackupConfigFileName )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, (LPVOID)DhcpGlobalBackupConfigFileName);
    DhcpGlobalBackupConfigFileName = 0;
  }
  if ( DhcpGlobalRecomputeTimerEvent )
  {
    LODWORD(v0) = CloseHandle(DhcpGlobalRecomputeTimerEvent);
    DhcpGlobalRecomputeTimerEvent = 0;
  }
  if ( DhcpGlobalProcessTerminationEvent )
  {
    LODWORD(v0) = CloseHandle(DhcpGlobalProcessTerminationEvent);
    DhcpGlobalProcessTerminationEvent = 0;
  }
  if ( DhcpGlobalRogueWaitEvent )
  {
    LODWORD(v0) = CloseHandle(DhcpGlobalRogueWaitEvent);
    DhcpGlobalRogueWaitEvent = 0;
  }
  if ( DhcpGlobalAddrToInstTable )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, DhcpGlobalAddrToInstTable);
    DhcpGlobalAddrToInstTable = 0;
  }
  if ( DhcpGlobalTCPHandle )
  {
    LODWORD(v0) = CloseHandle(DhcpGlobalTCPHandle);
    DhcpGlobalTCPHandle = 0;
  }
  if ( DhcpGlobalEndpointReadyEvent )
  {
    LODWORD(v0) = CloseHandle(DhcpGlobalEndpointReadyEvent);
    DhcpGlobalEndpointReadyEvent = 0;
  }
  if ( DhcpGlobalGenericEndpointReadyEvent )
  {
    LODWORD(v0) = CloseHandle(DhcpGlobalGenericEndpointReadyEvent);
    DhcpGlobalGenericEndpointReadyEvent = 0;
  }
  if ( DhcpGlobalAlternateDnsServers )
  {
    LODWORD(v0) = HeapFree(gDhcpHeap, 0, DhcpGlobalAlternateDnsServers);
    DhcpGlobalAlternateDnsServers = 0;
  }
  if ( DhcpGlobalThisServer )
  {
    LODWORD(v0) = MemServerFree();
    DhcpGlobalThisServer = 0;
  }
  if ( DhcpGlobalThisServerV6 )
  {
    LODWORD(v0) = MemServer6Cleanup();
    DhcpGlobalThisServerV6 = 0;
  }
  return (int)v0;
}

```

## disassembly

```asm
0x180024a00  mov     [rsp+arg_0], rbx
0x180024a05  mov     [rsp+arg_8], rsi
0x180024a0a  push    rdi
0x180024a0b  sub     rsp, 20h
0x180024a0f  mov     eax, cs:dword_1800FD110
0x180024a15  xor     ebx, ebx
0x180024a17  test    eax, eax
0x180024a19  jz      short loc_180024A30
0x180024a1b  dec     eax
0x180024a1d  mov     ecx, ebx
0x180024a1f  mov     cs:dword_1800FD110, eax
0x180024a25  call    DhcpDeleteExpiredCtxt
0x180024a2a  mov     cs:nPendingReqs, ebx
0x180024a30  cmp     cs:DhcpGlobalDirSecurityDescriptor, rbx
0x180024a37  jz      short loc_180024A53
0x180024a39  lea     rcx, DhcpGlobalDirSecurityDescriptor; ObjectDescriptor
0x180024a40  call    cs:__imp_RtlDeleteSecurityObject
0x180024a47  nop     dword ptr [rax+rax+00h]
0x180024a4c  mov     cs:DhcpGlobalDirSecurityDescriptor, rbx
0x180024a53  cmp     cs:DhcpGlobalRegSecurityDescriptor, rbx
0x180024a5a  jz      short loc_180024A76
0x180024a5c  lea     rcx, DhcpGlobalRegSecurityDescriptor; ObjectDescriptor
0x180024a63  call    cs:__imp_RtlDeleteSecurityObject
0x180024a6a  nop     dword ptr [rax+rax+00h]
0x180024a6f  mov     cs:DhcpGlobalRegSecurityDescriptor, rbx
0x180024a76  cmp     cs:DhcpGlobalServiceSecurityDescriptor, rbx
0x180024a7d  jz      short loc_180024A99
0x180024a7f  lea     rcx, DhcpGlobalServiceSecurityDescriptor; ObjectDescriptor
0x180024a86  call    cs:__imp_RtlDeleteSecurityObject
0x180024a8d  nop     dword ptr [rax+rax+00h]
0x180024a92  mov     cs:DhcpGlobalServiceSecurityDescriptor, rbx
0x180024a99  mov     r8, cs:DhcpSid; lpMem
0x180024aa0  test    r8, r8
0x180024aa3  jz      short loc_180024AC1
0x180024aa5  mov     rcx, cs:gDhcpHeap; hHeap
0x180024aac  xor     edx, edx; dwFlags
0x180024aae  call    cs:__imp_HeapFree
0x180024ab5  nop     dword ptr [rax+rax+00h]
0x180024aba  mov     cs:DhcpSid, rbx
0x180024ac1  mov     r8, cs:DhcpAdminSid; lpMem
0x180024ac8  test    r8, r8
0x180024acb  jz      short loc_180024AE9
0x180024acd  mov     rcx, cs:gDhcpHeap; hHeap
0x180024ad4  xor     edx, edx; dwFlags
0x180024ad6  call    cs:__imp_HeapFree
0x180024add  nop     dword ptr [rax+rax+00h]
0x180024ae2  mov     cs:DhcpAdminSid, rbx
0x180024ae9  mov     r8, cs:DhcpServiceSid; lpMem
0x180024af0  test    r8, r8
0x180024af3  jz      short loc_180024B11
0x180024af5  mov     rcx, cs:gDhcpHeap; hHeap
0x180024afc  xor     edx, edx; dwFlags
0x180024afe  call    cs:__imp_HeapFree
0x180024b05  nop     dword ptr [rax+rax+00h]
0x180024b0a  mov     cs:DhcpServiceSid, rbx
0x180024b11  cmp     cs:DhcpGlobalWellKnownSIDsMade, ebx
0x180024b17  jz      short loc_180024B85
0x180024b19  lea     rdi, SidData
0x180024b20  mov     esi, 0Bh
0x180024b25  mov     rax, [rdi]
0x180024b28  mov     rcx, [rax]; hMem
0x180024b2b  test    rcx, rcx
0x180024b2e  jz      short loc_180024B42
0x180024b30  call    cs:__imp_LocalFree
0x180024b37  nop     dword ptr [rax+rax+00h]
0x180024b3c  mov     rax, [rdi]
0x180024b3f  mov     [rax], rbx
0x180024b42  add     rdi, 20h ; ' '
0x180024b46  sub     rsi, 1
0x180024b4a  jnz     short loc_180024B25
0x180024b4c  lea     rdi, BuiltinDomainSidData
0x180024b53  mov     esi, 9
0x180024b58  mov     rax, [rdi]
0x180024b5b  mov     rcx, [rax]; hMem
0x180024b5e  test    rcx, rcx
0x180024b61  jz      short loc_180024B75
0x180024b63  call    cs:__imp_LocalFree
0x180024b6a  nop     dword ptr [rax+rax+00h]
0x180024b6f  mov     rax, [rdi]
0x180024b72  mov     [rax], rbx
0x180024b75  add     rdi, 10h
0x180024b79  sub     rsi, 1
0x180024b7d  jnz     short loc_180024B58
0x180024b7f  mov     cs:DhcpGlobalWellKnownSIDsMade, ebx
0x180024b85  mov     r8, cs:DhcpGlobalOemDatabasePath; lpMem
0x180024b8c  test    r8, r8
0x180024b8f  jz      short loc_180024BAD
0x180024b91  mov     rcx, cs:gDhcpHeap; hHeap
0x180024b98  xor     edx, edx; dwFlags
0x180024b9a  call    cs:__imp_HeapFree
0x180024ba1  nop     dword ptr [rax+rax+00h]
0x180024ba6  mov     cs:DhcpGlobalOemDatabasePath, rbx
0x180024bad  mov     r8, cs:DhcpGlobalOemDatabaseName; lpMem
0x180024bb4  test    r8, r8
0x180024bb7  jz      short loc_180024BD5
0x180024bb9  mov     rcx, cs:gDhcpHeap; hHeap
0x180024bc0  xor     edx, edx; dwFlags
0x180024bc2  call    cs:__imp_HeapFree
0x180024bc9  nop     dword ptr [rax+rax+00h]
0x180024bce  mov     cs:DhcpGlobalOemDatabaseName, rbx
0x180024bd5  mov     r8, cs:DhcpGlobalOemBackupPath; lpMem
0x180024bdc  test    r8, r8
0x180024bdf  jz      short loc_180024BFD
0x180024be1  mov     rcx, cs:gDhcpHeap; hHeap
0x180024be8  xor     edx, edx; dwFlags
0x180024bea  call    cs:__imp_HeapFree
0x180024bf1  nop     dword ptr [rax+rax+00h]
0x180024bf6  mov     cs:DhcpGlobalOemBackupPath, rbx
0x180024bfd  mov     r8, cs:DhcpGlobalOemRestorePath; lpMem
0x180024c04  test    r8, r8
0x180024c07  jz      short loc_180024C25
0x180024c09  mov     rcx, cs:gDhcpHeap; hHeap
0x180024c10  xor     edx, edx; dwFlags
0x180024c12  call    cs:__imp_HeapFree
0x180024c19  nop     dword ptr [rax+rax+00h]
0x180024c1e  mov     cs:DhcpGlobalOemRestorePath, rbx
0x180024c25  mov     r8, cs:DhcpGlobalOemJetBackupPath; lpMem
0x180024c2c  test    r8, r8
0x180024c2f  jz      short loc_180024C4D
0x180024c31  mov     rcx, cs:gDhcpHeap; hHeap
0x180024c38  xor     edx, edx; dwFlags
0x180024c3a  call    cs:__imp_HeapFree
0x180024c41  nop     dword ptr [rax+rax+00h]
0x180024c46  mov     cs:DhcpGlobalOemJetBackupPath, rbx
0x180024c4d  mov     r8, cs:DhcpGlobalOemJetRestorePath; lpMem
0x180024c54  test    r8, r8
0x180024c57  jz      short loc_180024C75
0x180024c59  mov     rcx, cs:gDhcpHeap; hHeap
0x180024c60  xor     edx, edx; dwFlags
0x180024c62  call    cs:__imp_HeapFree
0x180024c69  nop     dword ptr [rax+rax+00h]
0x180024c6e  mov     cs:DhcpGlobalOemJetRestorePath, rbx
0x180024c75  mov     r8, cs:DhcpGlobalBackupConfigFileName; lpMem
0x180024c7c  test    r8, r8
0x180024c7f  jz      short loc_180024C9D
0x180024c81  mov     rcx, cs:gDhcpHeap; hHeap
0x180024c88  xor     edx, edx; dwFlags
0x180024c8a  call    cs:__imp_HeapFree
0x180024c91  nop     dword ptr [rax+rax+00h]
0x180024c96  mov     cs:DhcpGlobalBackupConfigFileName, rbx
0x180024c9d  mov     rcx, cs:DhcpGlobalRecomputeTimerEvent; hObject
0x180024ca4  test    rcx, rcx
0x180024ca7  jz      short loc_180024CBC
0x180024ca9  call    cs:__imp_CloseHandle
0x180024cb0  nop     dword ptr [rax+rax+00h]
0x180024cb5  mov     cs:DhcpGlobalRecomputeTimerEvent, rbx
0x180024cbc  mov     rcx, cs:DhcpGlobalProcessTerminationEvent; hObject
0x180024cc3  test    rcx, rcx
0x180024cc6  jz      short loc_180024CDB
0x180024cc8  call    cs:__imp_CloseHandle
0x180024ccf  nop     dword ptr [rax+rax+00h]
0x180024cd4  mov     cs:DhcpGlobalProcessTerminationEvent, rbx
0x180024cdb  mov     rcx, cs:DhcpGlobalRogueWaitEvent; hObject
0x180024ce2  test    rcx, rcx
0x180024ce5  jz      short loc_180024CFA
0x180024ce7  call    cs:__imp_CloseHandle
0x180024cee  nop     dword ptr [rax+rax+00h]
0x180024cf3  mov     cs:DhcpGlobalRogueWaitEvent, rbx
0x180024cfa  mov     r8, cs:DhcpGlobalAddrToInstTable; lpMem
0x180024d01  test    r8, r8
0x180024d04  jz      short loc_180024D22
0x180024d06  mov     rcx, cs:gDhcpHeap; hHeap
0x180024d0d  xor     edx, edx; dwFlags
0x180024d0f  call    cs:__imp_HeapFree
0x180024d16  nop     dword ptr [rax+rax+00h]
0x180024d1b  mov     cs:DhcpGlobalAddrToInstTable, rbx
0x180024d22  mov     rcx, cs:DhcpGlobalTCPHandle; hObject
0x180024d29  test    rcx, rcx
0x180024d2c  jz      short loc_180024D41
0x180024d2e  call    cs:__imp_CloseHandle
0x180024d35  nop     dword ptr [rax+rax+00h]
0x180024d3a  mov     cs:DhcpGlobalTCPHandle, rbx
0x180024d41  mov     rcx, cs:DhcpGlobalEndpointReadyEvent; hObject
0x180024d48  test    rcx, rcx
0x180024d4b  jz      short loc_180024D60
0x180024d4d  call    cs:__imp_CloseHandle
0x180024d54  nop     dword ptr [rax+rax+00h]
0x180024d59  mov     cs:DhcpGlobalEndpointReadyEvent, rbx
0x180024d60  mov     rcx, cs:DhcpGlobalGenericEndpointReadyEvent; hObject
0x180024d67  test    rcx, rcx
0x180024d6a  jz      short loc_180024D7F
0x180024d6c  call    cs:__imp_CloseHandle
0x180024d73  nop     dword ptr [rax+rax+00h]
0x180024d78  mov     cs:DhcpGlobalGenericEndpointReadyEvent, rbx
0x180024d7f  mov     r8, cs:DhcpGlobalAlternateDnsServers; lpMem
0x180024d86  test    r8, r8
0x180024d89  jz      short loc_180024DA7
0x180024d8b  mov     rcx, cs:gDhcpHeap; hHeap
0x180024d92  xor     edx, edx; dwFlags
0x180024d94  call    cs:__imp_HeapFree
0x180024d9b  nop     dword ptr [rax+rax+00h]
0x180024da0  mov     cs:DhcpGlobalAlternateDnsServers, rbx
0x180024da7  cmp     cs:DhcpGlobalThisServer, rbx
0x180024dae  jz      short loc_180024DBC
0x180024db0  call    MemServerFree
0x180024db5  mov     cs:DhcpGlobalThisServer, rbx
0x180024dbc  cmp     cs:DhcpGlobalThisServerV6, rbx
0x180024dc3  jz      short loc_180024DD1
0x180024dc5  call    MemServer6Cleanup
0x180024dca  mov     cs:DhcpGlobalThisServerV6, rbx
0x180024dd1  mov     rbx, [rsp+28h+arg_0]
0x180024dd6  mov     rsi, [rsp+28h+arg_8]
0x180024ddb  add     rsp, 20h
0x180024ddf  pop     rdi
0x180024de0  retn
```
