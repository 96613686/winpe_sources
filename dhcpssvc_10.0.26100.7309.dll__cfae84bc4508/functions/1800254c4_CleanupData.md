# CleanupData

- ea: `0x1800254c4`
- end: `0x1800258a6`
- name: `CleanupData`
- size: `994`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027fc4`

## callees

- `0x1800254c4`
- `0x180033948`
- `0x180091a98`
- `0x1800985ac`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x180025504`
- `ntdll!RtlDeleteSecurityObject` at `0x180025527`
- `ntdll!RtlDeleteSecurityObject` at `0x18002554a`
- `ntdll!RtlDeleteSecurityObject` at `0x180025504`
- `ntdll!RtlDeleteSecurityObject` at `0x180025527`
- `ntdll!RtlDeleteSecurityObject` at `0x18002554a`
- `KERNEL32!CloseHandle` at `0x18002576d`
- `KERNEL32!CloseHandle` at `0x18002578c`
- `KERNEL32!CloseHandle` at `0x1800257ab`
- `KERNEL32!CloseHandle` at `0x1800257f2`
- `KERNEL32!CloseHandle` at `0x180025811`
- `KERNEL32!CloseHandle` at `0x180025830`
- `KERNEL32!CloseHandle` at `0x18002576d`
- `KERNEL32!CloseHandle` at `0x18002578c`
- `KERNEL32!CloseHandle` at `0x1800257ab`
- `KERNEL32!CloseHandle` at `0x1800257f2`
- `KERNEL32!CloseHandle` at `0x180025811`
- `KERNEL32!CloseHandle` at `0x180025830`
- `KERNEL32!LocalFree` at `0x1800255f4`
- `KERNEL32!LocalFree` at `0x180025627`
- `KERNEL32!LocalFree` at `0x1800255f4`
- `KERNEL32!LocalFree` at `0x180025627`
- `KERNEL32!HeapFree` at `0x180025572`
- `KERNEL32!HeapFree` at `0x18002559a`
- `KERNEL32!HeapFree` at `0x1800255c2`
- `KERNEL32!HeapFree` at `0x18002565e`
- `KERNEL32!HeapFree` at `0x180025686`
- `KERNEL32!HeapFree` at `0x1800256ae`
- `KERNEL32!HeapFree` at `0x1800256d6`
- `KERNEL32!HeapFree` at `0x1800256fe`
- `KERNEL32!HeapFree` at `0x180025726`
- `KERNEL32!HeapFree` at `0x18002574e`
- `KERNEL32!HeapFree` at `0x1800257d3`
- `KERNEL32!HeapFree` at `0x180025858`
- `KERNEL32!HeapFree` at `0x180025572`
- `KERNEL32!HeapFree` at `0x18002559a`
- `KERNEL32!HeapFree` at `0x1800255c2`
- `KERNEL32!HeapFree` at `0x18002565e`
- `KERNEL32!HeapFree` at `0x180025686`
- `KERNEL32!HeapFree` at `0x1800256ae`
- `KERNEL32!HeapFree` at `0x1800256d6`
- `KERNEL32!HeapFree` at `0x1800256fe`
- `KERNEL32!HeapFree` at `0x180025726`
- `KERNEL32!HeapFree` at `0x18002574e`
- `KERNEL32!HeapFree` at `0x1800257d3`
- `KERNEL32!HeapFree` at `0x180025858`

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

  LODWORD(v0) = dword_1800FB130;
  if ( dword_1800FB130 )
  {
    --dword_1800FB130;
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
0x1800254c4  mov     [rsp+arg_0], rbx
0x1800254c9  mov     [rsp+arg_8], rsi
0x1800254ce  push    rdi
0x1800254cf  sub     rsp, 20h
0x1800254d3  mov     eax, cs:dword_1800FB130
0x1800254d9  xor     ebx, ebx
0x1800254db  test    eax, eax
0x1800254dd  jz      short loc_1800254F4
0x1800254df  dec     eax
0x1800254e1  mov     ecx, ebx
0x1800254e3  mov     cs:dword_1800FB130, eax
0x1800254e9  call    DhcpDeleteExpiredCtxt
0x1800254ee  mov     cs:nPendingReqs, ebx
0x1800254f4  cmp     cs:DhcpGlobalDirSecurityDescriptor, rbx
0x1800254fb  jz      short loc_180025517
0x1800254fd  lea     rcx, DhcpGlobalDirSecurityDescriptor; ObjectDescriptor
0x180025504  call    cs:__imp_RtlDeleteSecurityObject
0x18002550b  nop     dword ptr [rax+rax+00h]
0x180025510  mov     cs:DhcpGlobalDirSecurityDescriptor, rbx
0x180025517  cmp     cs:DhcpGlobalRegSecurityDescriptor, rbx
0x18002551e  jz      short loc_18002553A
0x180025520  lea     rcx, DhcpGlobalRegSecurityDescriptor; ObjectDescriptor
0x180025527  call    cs:__imp_RtlDeleteSecurityObject
0x18002552e  nop     dword ptr [rax+rax+00h]
0x180025533  mov     cs:DhcpGlobalRegSecurityDescriptor, rbx
0x18002553a  cmp     cs:DhcpGlobalServiceSecurityDescriptor, rbx
0x180025541  jz      short loc_18002555D
0x180025543  lea     rcx, DhcpGlobalServiceSecurityDescriptor; ObjectDescriptor
0x18002554a  call    cs:__imp_RtlDeleteSecurityObject
0x180025551  nop     dword ptr [rax+rax+00h]
0x180025556  mov     cs:DhcpGlobalServiceSecurityDescriptor, rbx
0x18002555d  mov     r8, cs:DhcpSid; lpMem
0x180025564  test    r8, r8
0x180025567  jz      short loc_180025585
0x180025569  mov     rcx, cs:gDhcpHeap; hHeap
0x180025570  xor     edx, edx; dwFlags
0x180025572  call    cs:__imp_HeapFree
0x180025579  nop     dword ptr [rax+rax+00h]
0x18002557e  mov     cs:DhcpSid, rbx
0x180025585  mov     r8, cs:DhcpAdminSid; lpMem
0x18002558c  test    r8, r8
0x18002558f  jz      short loc_1800255AD
0x180025591  mov     rcx, cs:gDhcpHeap; hHeap
0x180025598  xor     edx, edx; dwFlags
0x18002559a  call    cs:__imp_HeapFree
0x1800255a1  nop     dword ptr [rax+rax+00h]
0x1800255a6  mov     cs:DhcpAdminSid, rbx
0x1800255ad  mov     r8, cs:DhcpServiceSid; lpMem
0x1800255b4  test    r8, r8
0x1800255b7  jz      short loc_1800255D5
0x1800255b9  mov     rcx, cs:gDhcpHeap; hHeap
0x1800255c0  xor     edx, edx; dwFlags
0x1800255c2  call    cs:__imp_HeapFree
0x1800255c9  nop     dword ptr [rax+rax+00h]
0x1800255ce  mov     cs:DhcpServiceSid, rbx
0x1800255d5  cmp     cs:DhcpGlobalWellKnownSIDsMade, ebx
0x1800255db  jz      short loc_180025649
0x1800255dd  lea     rdi, SidData
0x1800255e4  mov     esi, 0Bh
0x1800255e9  mov     rax, [rdi]
0x1800255ec  mov     rcx, [rax]; hMem
0x1800255ef  test    rcx, rcx
0x1800255f2  jz      short loc_180025606
0x1800255f4  call    cs:__imp_LocalFree
0x1800255fb  nop     dword ptr [rax+rax+00h]
0x180025600  mov     rax, [rdi]
0x180025603  mov     [rax], rbx
0x180025606  add     rdi, 20h ; ' '
0x18002560a  sub     rsi, 1
0x18002560e  jnz     short loc_1800255E9
0x180025610  lea     rdi, BuiltinDomainSidData
0x180025617  mov     esi, 9
0x18002561c  mov     rax, [rdi]
0x18002561f  mov     rcx, [rax]; hMem
0x180025622  test    rcx, rcx
0x180025625  jz      short loc_180025639
0x180025627  call    cs:__imp_LocalFree
0x18002562e  nop     dword ptr [rax+rax+00h]
0x180025633  mov     rax, [rdi]
0x180025636  mov     [rax], rbx
0x180025639  add     rdi, 10h
0x18002563d  sub     rsi, 1
0x180025641  jnz     short loc_18002561C
0x180025643  mov     cs:DhcpGlobalWellKnownSIDsMade, ebx
0x180025649  mov     r8, cs:DhcpGlobalOemDatabasePath; lpMem
0x180025650  test    r8, r8
0x180025653  jz      short loc_180025671
0x180025655  mov     rcx, cs:gDhcpHeap; hHeap
0x18002565c  xor     edx, edx; dwFlags
0x18002565e  call    cs:__imp_HeapFree
0x180025665  nop     dword ptr [rax+rax+00h]
0x18002566a  mov     cs:DhcpGlobalOemDatabasePath, rbx
0x180025671  mov     r8, cs:DhcpGlobalOemDatabaseName; lpMem
0x180025678  test    r8, r8
0x18002567b  jz      short loc_180025699
0x18002567d  mov     rcx, cs:gDhcpHeap; hHeap
0x180025684  xor     edx, edx; dwFlags
0x180025686  call    cs:__imp_HeapFree
0x18002568d  nop     dword ptr [rax+rax+00h]
0x180025692  mov     cs:DhcpGlobalOemDatabaseName, rbx
0x180025699  mov     r8, cs:DhcpGlobalOemBackupPath; lpMem
0x1800256a0  test    r8, r8
0x1800256a3  jz      short loc_1800256C1
0x1800256a5  mov     rcx, cs:gDhcpHeap; hHeap
0x1800256ac  xor     edx, edx; dwFlags
0x1800256ae  call    cs:__imp_HeapFree
0x1800256b5  nop     dword ptr [rax+rax+00h]
0x1800256ba  mov     cs:DhcpGlobalOemBackupPath, rbx
0x1800256c1  mov     r8, cs:DhcpGlobalOemRestorePath; lpMem
0x1800256c8  test    r8, r8
0x1800256cb  jz      short loc_1800256E9
0x1800256cd  mov     rcx, cs:gDhcpHeap; hHeap
0x1800256d4  xor     edx, edx; dwFlags
0x1800256d6  call    cs:__imp_HeapFree
0x1800256dd  nop     dword ptr [rax+rax+00h]
0x1800256e2  mov     cs:DhcpGlobalOemRestorePath, rbx
0x1800256e9  mov     r8, cs:DhcpGlobalOemJetBackupPath; lpMem
0x1800256f0  test    r8, r8
0x1800256f3  jz      short loc_180025711
0x1800256f5  mov     rcx, cs:gDhcpHeap; hHeap
0x1800256fc  xor     edx, edx; dwFlags
0x1800256fe  call    cs:__imp_HeapFree
0x180025705  nop     dword ptr [rax+rax+00h]
0x18002570a  mov     cs:DhcpGlobalOemJetBackupPath, rbx
0x180025711  mov     r8, cs:DhcpGlobalOemJetRestorePath; lpMem
0x180025718  test    r8, r8
0x18002571b  jz      short loc_180025739
0x18002571d  mov     rcx, cs:gDhcpHeap; hHeap
0x180025724  xor     edx, edx; dwFlags
0x180025726  call    cs:__imp_HeapFree
0x18002572d  nop     dword ptr [rax+rax+00h]
0x180025732  mov     cs:DhcpGlobalOemJetRestorePath, rbx
0x180025739  mov     r8, cs:DhcpGlobalBackupConfigFileName; lpMem
0x180025740  test    r8, r8
0x180025743  jz      short loc_180025761
0x180025745  mov     rcx, cs:gDhcpHeap; hHeap
0x18002574c  xor     edx, edx; dwFlags
0x18002574e  call    cs:__imp_HeapFree
0x180025755  nop     dword ptr [rax+rax+00h]
0x18002575a  mov     cs:DhcpGlobalBackupConfigFileName, rbx
0x180025761  mov     rcx, cs:DhcpGlobalRecomputeTimerEvent; hObject
0x180025768  test    rcx, rcx
0x18002576b  jz      short loc_180025780
0x18002576d  call    cs:__imp_CloseHandle
0x180025774  nop     dword ptr [rax+rax+00h]
0x180025779  mov     cs:DhcpGlobalRecomputeTimerEvent, rbx
0x180025780  mov     rcx, cs:DhcpGlobalProcessTerminationEvent; hObject
0x180025787  test    rcx, rcx
0x18002578a  jz      short loc_18002579F
0x18002578c  call    cs:__imp_CloseHandle
0x180025793  nop     dword ptr [rax+rax+00h]
0x180025798  mov     cs:DhcpGlobalProcessTerminationEvent, rbx
0x18002579f  mov     rcx, cs:DhcpGlobalRogueWaitEvent; hObject
0x1800257a6  test    rcx, rcx
0x1800257a9  jz      short loc_1800257BE
0x1800257ab  call    cs:__imp_CloseHandle
0x1800257b2  nop     dword ptr [rax+rax+00h]
0x1800257b7  mov     cs:DhcpGlobalRogueWaitEvent, rbx
0x1800257be  mov     r8, cs:DhcpGlobalAddrToInstTable; lpMem
0x1800257c5  test    r8, r8
0x1800257c8  jz      short loc_1800257E6
0x1800257ca  mov     rcx, cs:gDhcpHeap; hHeap
0x1800257d1  xor     edx, edx; dwFlags
0x1800257d3  call    cs:__imp_HeapFree
0x1800257da  nop     dword ptr [rax+rax+00h]
0x1800257df  mov     cs:DhcpGlobalAddrToInstTable, rbx
0x1800257e6  mov     rcx, cs:DhcpGlobalTCPHandle; hObject
0x1800257ed  test    rcx, rcx
0x1800257f0  jz      short loc_180025805
0x1800257f2  call    cs:__imp_CloseHandle
0x1800257f9  nop     dword ptr [rax+rax+00h]
0x1800257fe  mov     cs:DhcpGlobalTCPHandle, rbx
0x180025805  mov     rcx, cs:DhcpGlobalEndpointReadyEvent; hObject
0x18002580c  test    rcx, rcx
0x18002580f  jz      short loc_180025824
0x180025811  call    cs:__imp_CloseHandle
0x180025818  nop     dword ptr [rax+rax+00h]
0x18002581d  mov     cs:DhcpGlobalEndpointReadyEvent, rbx
0x180025824  mov     rcx, cs:DhcpGlobalGenericEndpointReadyEvent; hObject
0x18002582b  test    rcx, rcx
0x18002582e  jz      short loc_180025843
0x180025830  call    cs:__imp_CloseHandle
0x180025837  nop     dword ptr [rax+rax+00h]
0x18002583c  mov     cs:DhcpGlobalGenericEndpointReadyEvent, rbx
0x180025843  mov     r8, cs:DhcpGlobalAlternateDnsServers; lpMem
0x18002584a  test    r8, r8
0x18002584d  jz      short loc_18002586B
0x18002584f  mov     rcx, cs:gDhcpHeap; hHeap
0x180025856  xor     edx, edx; dwFlags
0x180025858  call    cs:__imp_HeapFree
0x18002585f  nop     dword ptr [rax+rax+00h]
0x180025864  mov     cs:DhcpGlobalAlternateDnsServers, rbx
0x18002586b  cmp     cs:DhcpGlobalThisServer, rbx
0x180025872  jz      short loc_180025880
0x180025874  call    MemServerFree
0x180025879  mov     cs:DhcpGlobalThisServer, rbx
0x180025880  cmp     cs:DhcpGlobalThisServerV6, rbx
0x180025887  jz      short loc_180025895
0x180025889  call    MemServer6Cleanup
0x18002588e  mov     cs:DhcpGlobalThisServerV6, rbx
0x180025895  mov     rbx, [rsp+28h+arg_0]
0x18002589a  mov     rsi, [rsp+28h+arg_8]
0x18002589f  add     rsp, 20h
0x1800258a3  pop     rdi
0x1800258a4  retn
```
