# DhcpV6WaitForMessageThreadToQuit

- ea: `0x180074510`
- end: `0x18007473a`
- name: `DhcpV6WaitForMessageThreadToQuit`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180069658`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000f144`
- `0x1800252fc`
- `0x180074510`

## import_xrefs

- `ESENT!JetEndSession` at `0x180074691`
- `ESENT!JetEndSession` at `0x180074691`
- `KERNEL32!WaitForSingleObject` at `0x1800745a0`
- `KERNEL32!WaitForSingleObject` at `0x1800745a0`
- `KERNEL32!DeleteCriticalSection` at `0x180074673`
- `KERNEL32!DeleteCriticalSection` at `0x180074673`
- `KERNEL32!GetLastError` at `0x1800745b0`
- `KERNEL32!GetLastError` at `0x1800745b0`
- `KERNEL32!CloseHandle` at `0x1800745e9`
- `KERNEL32!CloseHandle` at `0x1800745e9`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180074623`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180074623`
- `KERNEL32!CloseThreadpool` at `0x180074643`
- `KERNEL32!CloseThreadpool` at `0x180074643`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180074610`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x180074610`
- `KERNEL32!HeapFree` at `0x1800746c5`
- `KERNEL32!HeapFree` at `0x1800746c5`

## pseudocode

```c
int DhcpV6WaitForMessageThreadToQuit()
{
  _QWORD *v0; // rcx
  HANDLE v1; // rax
  DWORD LastError; // eax
  int result; // eax
  __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // eax
  _QWORD *v7; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  v1 = qword_1800FB268;
  if ( qword_1800FB268 )
  {
    if ( v0 != &WPP_GLOBAL_Control && (*((_DWORD *)v0 + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(v0[2], 45, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids);
      v1 = qword_1800FB268;
    }
    if ( WaitForSingleObject(v1, 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids, LastError);
    }
    CloseHandle(qword_1800FB268);
    qword_1800FB268 = 0;
  }
  if ( DhcpAddressCacherCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(DhcpAddressCacherCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(DhcpAddressCacherCleanupGroup);
    DhcpAddressCacherCleanupGroup = 0;
  }
  if ( DhcpAddressCacherThreadPool )
  {
    CloseThreadpool(DhcpAddressCacherThreadPool);
    DhcpAddressCacherThreadPool = 0;
  }
  result = RwLockCleanup(&DhcpAddressCacherReadWriteLock);
  if ( DhcpGlobalSessionPool )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)DhcpGlobalSessionPool + 64));
    v4 = 0;
    v5 = 5;
    do
    {
      v6 = JetEndSession(*(_QWORD *)((char *)DhcpGlobalSessionPool + v4), 0);
      DhcpMapJetError(v6, "DhcpEndSession");
      v4 += 8;
      --v5;
    }
    while ( v5 );
    result = HeapFree(gDhcpHeap, 0, DhcpGlobalSessionPool);
    DhcpGlobalSessionPool = 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x8000000) != 0 )
      return WPP_SF_(v7[2], 48, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180074510  mov     rax, rsp
0x180074513  mov     [rax+8], rbx
0x180074517  mov     [rax+10h], rbp
0x18007451b  mov     [rax+18h], rdi
0x18007451f  mov     [rax+20h], r14
0x180074523  push    r15
0x180074525  sub     rsp, 20h
0x180074529  mov     rcx, cs:WPP_GLOBAL_Control
0x180074530  lea     rbp, WPP_GLOBAL_Control
0x180074537  lea     r14, WPP_7393b155433f392c1624c7b14fc47429_Traceguids
0x18007453e  mov     r15d, 8000000h
0x180074544  cmp     rcx, rbp
0x180074547  jz      short loc_180074567
0x180074549  test    [rcx+1Ch], r15d
0x18007454d  jz      short loc_180074567
0x18007454f  mov     rcx, [rcx+10h]
0x180074553  mov     edx, 2Ch ; ','
0x180074558  mov     r8, r14
0x18007455b  call    WPP_SF_
0x180074560  mov     rcx, cs:WPP_GLOBAL_Control
0x180074567  mov     rax, cs:qword_1800FB268
0x18007456e  test    rax, rax
0x180074571  jz      loc_1800745FD
0x180074577  cmp     rcx, rbp
0x18007457a  jz      short loc_18007459A
0x18007457c  test    [rcx+1Ch], r15d
0x180074580  jz      short loc_18007459A
0x180074582  mov     rcx, [rcx+10h]
0x180074586  mov     edx, 2Dh ; '-'
0x18007458b  mov     r8, r14
0x18007458e  call    WPP_SF_
0x180074593  mov     rax, cs:qword_1800FB268
0x18007459a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18007459d  mov     rcx, rax; hHandle
0x1800745a0  call    cs:__imp_WaitForSingleObject
0x1800745a7  nop     dword ptr [rax+rax+00h]
0x1800745ac  test    eax, eax
0x1800745ae  jz      short loc_1800745E2
0x1800745b0  call    cs:__imp_GetLastError
0x1800745b7  nop     dword ptr [rax+rax+00h]
0x1800745bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800745c3  cmp     rcx, rbp
0x1800745c6  jz      short loc_1800745E2
0x1800745c8  test    byte ptr [rcx+1Ch], 10h
0x1800745cc  jz      short loc_1800745E2
0x1800745ce  mov     rcx, [rcx+10h]
0x1800745d2  mov     edx, 2Eh ; '.'
0x1800745d7  mov     r9d, eax
0x1800745da  mov     r8, r14
0x1800745dd  call    WPP_SF_D
0x1800745e2  mov     rcx, cs:qword_1800FB268; hObject
0x1800745e9  call    cs:__imp_CloseHandle
0x1800745f0  nop     dword ptr [rax+rax+00h]
0x1800745f5  and     cs:qword_1800FB268, 0
0x1800745fd  mov     rcx, cs:DhcpAddressCacherCleanupGroup; ptpcg
0x180074604  test    rcx, rcx
0x180074607  jz      short loc_180074637
0x180074609  xor     r8d, r8d; pvCleanupContext
0x18007460c  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180074610  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180074617  nop     dword ptr [rax+rax+00h]
0x18007461c  mov     rcx, cs:DhcpAddressCacherCleanupGroup; ptpcg
0x180074623  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18007462a  nop     dword ptr [rax+rax+00h]
0x18007462f  and     cs:DhcpAddressCacherCleanupGroup, 0
0x180074637  mov     rcx, cs:DhcpAddressCacherThreadPool; ptpp
0x18007463e  test    rcx, rcx
0x180074641  jz      short loc_180074657
0x180074643  call    cs:__imp_CloseThreadpool
0x18007464a  nop     dword ptr [rax+rax+00h]
0x18007464f  and     cs:DhcpAddressCacherThreadPool, 0
0x180074657  lea     rcx, DhcpAddressCacherReadWriteLock
0x18007465e  call    RwLockCleanup
0x180074663  mov     rcx, cs:DhcpGlobalSessionPool
0x18007466a  test    rcx, rcx
0x18007466d  jz      short loc_1800746D8
0x18007466f  add     rcx, 40h ; '@'; lpCriticalSection
0x180074673  call    cs:__imp_DeleteCriticalSection
0x18007467a  nop     dword ptr [rax+rax+00h]
0x18007467f  xor     ebx, ebx
0x180074681  lea     edi, [rbx+5]
0x180074684  mov     rcx, cs:DhcpGlobalSessionPool
0x18007468b  xor     edx, edx; grbit
0x18007468d  mov     rcx, [rbx+rcx]; sesid
0x180074691  call    cs:__imp_JetEndSession
0x180074698  nop     dword ptr [rax+rax+00h]
0x18007469d  mov     ecx, eax
0x18007469f  lea     rdx, aDhcpendsession; "DhcpEndSession"
0x1800746a6  call    DhcpMapJetError
0x1800746ab  lea     rbx, [rbx+8]
0x1800746af  sub     rdi, 1
0x1800746b3  jnz     short loc_180074684
0x1800746b5  mov     r8, cs:DhcpGlobalSessionPool; lpMem
0x1800746bc  xor     edx, edx; dwFlags
0x1800746be  mov     rcx, cs:gDhcpHeap; hHeap
0x1800746c5  call    cs:__imp_HeapFree
0x1800746cc  nop     dword ptr [rax+rax+00h]
0x1800746d1  and     cs:DhcpGlobalSessionPool, rdi
0x1800746d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800746df  cmp     rcx, rbp
0x1800746e2  jz      short loc_18007471E
0x1800746e4  test    [rcx+1Ch], r15d
0x1800746e8  jz      short loc_180074702
0x1800746ea  mov     rcx, [rcx+10h]
0x1800746ee  mov     edx, 2Fh ; '/'
0x1800746f3  mov     r8, r14
0x1800746f6  call    WPP_SF_
0x1800746fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180074702  cmp     rcx, rbp
0x180074705  jz      short loc_18007471E
0x180074707  test    [rcx+1Ch], r15d
0x18007470b  jz      short loc_18007471E
0x18007470d  mov     rcx, [rcx+10h]
0x180074711  mov     edx, 30h ; '0'
0x180074716  mov     r8, r14
0x180074719  call    WPP_SF_
0x18007471e  mov     rbx, [rsp+28h+arg_0]
0x180074723  mov     rbp, [rsp+28h+arg_8]
0x180074728  mov     rdi, [rsp+28h+arg_10]
0x18007472d  mov     r14, [rsp+28h+arg_18]
0x180074732  add     rsp, 20h
0x180074736  pop     r15
0x180074738  retn
```
