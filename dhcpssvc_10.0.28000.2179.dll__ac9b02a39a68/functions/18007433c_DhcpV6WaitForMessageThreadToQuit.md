# DhcpV6WaitForMessageThreadToQuit

- ea: `0x18007433c`
- end: `0x18007456f`
- name: `DhcpV6WaitForMessageThreadToQuit`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180069400`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000e814`
- `0x180024838`
- `0x18007433c`

## import_xrefs

- `ESENT!JetEndSession` at `0x1800744c6`
- `ESENT!JetEndSession` at `0x1800744c6`
- `KERNEL32!WaitForSingleObject` at `0x1800743cc`
- `KERNEL32!WaitForSingleObject` at `0x1800743cc`
- `KERNEL32!DeleteCriticalSection` at `0x1800744a8`
- `KERNEL32!DeleteCriticalSection` at `0x1800744a8`
- `KERNEL32!GetLastError` at `0x1800743dc`
- `KERNEL32!GetLastError` at `0x1800743dc`
- `KERNEL32!CloseHandle` at `0x180074415`
- `KERNEL32!CloseHandle` at `0x180074415`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180074452`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x180074452`
- `KERNEL32!CloseThreadpool` at `0x180074475`
- `KERNEL32!CloseThreadpool` at `0x180074475`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x18007443f`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x18007443f`
- `KERNEL32!HeapFree` at `0x1800744fa`
- `KERNEL32!HeapFree` at `0x1800744fa`

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
  v1 = qword_1800FD220;
  if ( qword_1800FD220 )
  {
    if ( v0 != &WPP_GLOBAL_Control && (*((_DWORD *)v0 + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(v0[2], 45, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids);
      v1 = qword_1800FD220;
    }
    if ( WaitForSingleObject(v1, 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids, LastError);
    }
    CloseHandle(qword_1800FD220);
    qword_1800FD220 = 0;
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
0x18007433c  mov     rax, rsp
0x18007433f  mov     [rax+8], rbx
0x180074343  mov     [rax+10h], rbp
0x180074347  mov     [rax+18h], rdi
0x18007434b  mov     [rax+20h], r14
0x18007434f  push    r15
0x180074351  sub     rsp, 20h
0x180074355  mov     rcx, cs:WPP_GLOBAL_Control
0x18007435c  lea     rbp, WPP_GLOBAL_Control
0x180074363  lea     r14, WPP_7393b155433f392c1624c7b14fc47429_Traceguids
0x18007436a  mov     r15d, 8000000h
0x180074370  cmp     rcx, rbp
0x180074373  jz      short loc_180074393
0x180074375  test    [rcx+1Ch], r15d
0x180074379  jz      short loc_180074393
0x18007437b  mov     rcx, [rcx+10h]
0x18007437f  mov     edx, 2Ch ; ','
0x180074384  mov     r8, r14
0x180074387  call    WPP_SF_
0x18007438c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074393  mov     rax, cs:qword_1800FD220
0x18007439a  test    rax, rax
0x18007439d  jz      loc_18007442C
0x1800743a3  cmp     rcx, rbp
0x1800743a6  jz      short loc_1800743C6
0x1800743a8  test    [rcx+1Ch], r15d
0x1800743ac  jz      short loc_1800743C6
0x1800743ae  mov     rcx, [rcx+10h]
0x1800743b2  mov     edx, 2Dh ; '-'
0x1800743b7  mov     r8, r14
0x1800743ba  call    WPP_SF_
0x1800743bf  mov     rax, cs:qword_1800FD220
0x1800743c6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800743c9  mov     rcx, rax; hHandle
0x1800743cc  call    cs:__imp_WaitForSingleObject
0x1800743d3  nop     dword ptr [rax+rax+00h]
0x1800743d8  test    eax, eax
0x1800743da  jz      short loc_18007440E
0x1800743dc  call    cs:__imp_GetLastError
0x1800743e3  nop     dword ptr [rax+rax+00h]
0x1800743e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743ef  cmp     rcx, rbp
0x1800743f2  jz      short loc_18007440E
0x1800743f4  test    byte ptr [rcx+1Ch], 10h
0x1800743f8  jz      short loc_18007440E
0x1800743fa  mov     rcx, [rcx+10h]
0x1800743fe  mov     edx, 2Eh ; '.'
0x180074403  mov     r9d, eax
0x180074406  mov     r8, r14
0x180074409  call    WPP_SF_D
0x18007440e  mov     rcx, cs:qword_1800FD220; hObject
0x180074415  call    cs:__imp_CloseHandle
0x18007441c  nop     dword ptr [rax+rax+00h]
0x180074421  mov     cs:qword_1800FD220, 0
0x18007442c  mov     rcx, cs:DhcpAddressCacherCleanupGroup; ptpcg
0x180074433  test    rcx, rcx
0x180074436  jz      short loc_180074469
0x180074438  xor     r8d, r8d; pvCleanupContext
0x18007443b  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18007443f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180074446  nop     dword ptr [rax+rax+00h]
0x18007444b  mov     rcx, cs:DhcpAddressCacherCleanupGroup; ptpcg
0x180074452  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180074459  nop     dword ptr [rax+rax+00h]
0x18007445e  mov     cs:DhcpAddressCacherCleanupGroup, 0
0x180074469  mov     rcx, cs:DhcpAddressCacherThreadPool; ptpp
0x180074470  test    rcx, rcx
0x180074473  jz      short loc_18007448C
0x180074475  call    cs:__imp_CloseThreadpool
0x18007447c  nop     dword ptr [rax+rax+00h]
0x180074481  mov     cs:DhcpAddressCacherThreadPool, 0
0x18007448c  lea     rcx, DhcpAddressCacherReadWriteLock
0x180074493  call    RwLockCleanup
0x180074498  mov     rcx, cs:DhcpGlobalSessionPool
0x18007449f  test    rcx, rcx
0x1800744a2  jz      short loc_18007450D
0x1800744a4  add     rcx, 40h ; '@'; lpCriticalSection
0x1800744a8  call    cs:__imp_DeleteCriticalSection
0x1800744af  nop     dword ptr [rax+rax+00h]
0x1800744b4  xor     ebx, ebx
0x1800744b6  lea     edi, [rbx+5]
0x1800744b9  mov     rcx, cs:DhcpGlobalSessionPool
0x1800744c0  xor     edx, edx; grbit
0x1800744c2  mov     rcx, [rbx+rcx]; sesid
0x1800744c6  call    cs:__imp_JetEndSession
0x1800744cd  nop     dword ptr [rax+rax+00h]
0x1800744d2  mov     ecx, eax
0x1800744d4  lea     rdx, aDhcpendsession; "DhcpEndSession"
0x1800744db  call    DhcpMapJetError
0x1800744e0  lea     rbx, [rbx+8]
0x1800744e4  sub     rdi, 1
0x1800744e8  jnz     short loc_1800744B9
0x1800744ea  mov     r8, cs:DhcpGlobalSessionPool; lpMem
0x1800744f1  xor     edx, edx; dwFlags
0x1800744f3  mov     rcx, cs:gDhcpHeap; hHeap
0x1800744fa  call    cs:__imp_HeapFree
0x180074501  nop     dword ptr [rax+rax+00h]
0x180074506  mov     cs:DhcpGlobalSessionPool, rdi
0x18007450d  mov     rcx, cs:WPP_GLOBAL_Control
0x180074514  cmp     rcx, rbp
0x180074517  jz      short loc_180074553
0x180074519  test    [rcx+1Ch], r15d
0x18007451d  jz      short loc_180074537
0x18007451f  mov     rcx, [rcx+10h]
0x180074523  mov     edx, 2Fh ; '/'
0x180074528  mov     r8, r14
0x18007452b  call    WPP_SF_
0x180074530  mov     rcx, cs:WPP_GLOBAL_Control
0x180074537  cmp     rcx, rbp
0x18007453a  jz      short loc_180074553
0x18007453c  test    [rcx+1Ch], r15d
0x180074540  jz      short loc_180074553
0x180074542  mov     rcx, [rcx+10h]
0x180074546  mov     edx, 30h ; '0'
0x18007454b  mov     r8, r14
0x18007454e  call    WPP_SF_
0x180074553  mov     rbx, [rsp+28h+arg_0]
0x180074558  mov     rbp, [rsp+28h+arg_8]
0x18007455d  mov     rdi, [rsp+28h+arg_10]
0x180074562  mov     r14, [rsp+28h+arg_18]
0x180074567  add     rsp, 20h
0x18007456b  pop     r15
0x18007456d  retn
```
