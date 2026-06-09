# DhcpCleanupClientToServer

- ea: `0x180053f60`
- end: `0x18005413e`
- name: `DhcpCleanupClientToServer`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180027fc4`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800247c8`
- `0x1800252fc`
- `0x1800347fc`
- `0x180053f60`
- `0x18005e4d8`
- `0x180061d2c`
- `0x1800cc99a`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180054049`
- `KERNEL32!WaitForSingleObject` at `0x180054049`
- `KERNEL32!DeleteCriticalSection` at `0x1800540f6`
- `KERNEL32!DeleteCriticalSection` at `0x180054109`
- `KERNEL32!DeleteCriticalSection` at `0x1800540f6`
- `KERNEL32!DeleteCriticalSection` at `0x180054109`
- `KERNEL32!GetLastError` at `0x180054059`
- `KERNEL32!GetLastError` at `0x180054059`
- `KERNEL32!CloseHandle` at `0x180053f95`
- `KERNEL32!CloseHandle` at `0x180053fbb`
- `KERNEL32!CloseHandle` at `0x180054096`
- `KERNEL32!CloseHandle` at `0x180053f95`
- `KERNEL32!CloseHandle` at `0x180053fbb`
- `KERNEL32!CloseHandle` at `0x180054096`

## pseudocode

```c
__int64 DhcpCleanupClientToServer()
{
  int v0; // eax
  int v1; // eax
  HANDLE v2; // rcx
  DWORD LastError; // eax

  ThreadsStop();
  PingCleanup();
  if ( dword_1800FB180 )
  {
    v0 = --dword_1800FB180;
    if ( qword_1800FB1C0 )
    {
      CloseHandle(qword_1800FB1C0);
      qword_1800FB1C0 = 0;
      v0 = dword_1800FB180;
    }
    if ( CompletionPort )
    {
      CloseHandle(CompletionPort);
      CompletionPort = 0;
      v0 = dword_1800FB180;
    }
    if ( v0 )
    {
      dword_1800FB180 = v0 - 1;
      CleanupQData();
    }
  }
  v1 = InitCount;
  if ( InitCount )
  {
    --InitCount;
    if ( v1 == 1 )
      IpTblCleanup();
  }
  v2 = hHandle;
  if ( hHandle )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids);
      v2 = hHandle;
    }
    if ( WaitForSingleObject(v2, 0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids, LastError);
    }
    CloseHandle(hHandle);
    hHandle = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids);
  memset_0(&DhcpGlobalEndPointTable, 0, 0x60u);
  if ( DhcpQDataInitialized == 1 )
  {
    DeleteCriticalSection(&PacketCritSection);
    DeleteCriticalSection(&QuarDecisionCritSection);
    DhcpQDataInitialized = 0;
  }
  RwLockCleanup(&DhcpGlobalReadWriteLock);
  return RwLockCleanup(&SocketRwLock);
}

```

## disassembly

```asm
0x180053f60  mov     [rsp+arg_0], rsi
0x180053f65  push    rdi
0x180053f66  sub     rsp, 20h
0x180053f6a  call    ThreadsStop
0x180053f6f  call    PingCleanup
0x180053f74  mov     eax, cs:dword_1800FB180
0x180053f7a  or      edi, 0FFFFFFFFh
0x180053f7d  test    eax, eax
0x180053f7f  jz      short loc_180053FE6
0x180053f81  mov     rcx, cs:qword_1800FB1C0; hObject
0x180053f88  add     eax, edi
0x180053f8a  mov     cs:dword_1800FB180, eax
0x180053f90  test    rcx, rcx
0x180053f93  jz      short loc_180053FAF
0x180053f95  call    cs:__imp_CloseHandle
0x180053f9c  nop     dword ptr [rax+rax+00h]
0x180053fa1  and     cs:qword_1800FB1C0, 0
0x180053fa9  mov     eax, cs:dword_1800FB180
0x180053faf  mov     rcx, cs:CompletionPort; hObject
0x180053fb6  test    rcx, rcx
0x180053fb9  jz      short loc_180053FD5
0x180053fbb  call    cs:__imp_CloseHandle
0x180053fc2  nop     dword ptr [rax+rax+00h]
0x180053fc7  and     cs:CompletionPort, 0
0x180053fcf  mov     eax, cs:dword_1800FB180
0x180053fd5  test    eax, eax
0x180053fd7  jz      short loc_180053FE6
0x180053fd9  add     eax, edi
0x180053fdb  mov     cs:dword_1800FB180, eax
0x180053fe1  call    CleanupQData
0x180053fe6  mov     eax, cs:InitCount
0x180053fec  test    eax, eax
0x180053fee  jz      short loc_180053FFF
0x180053ff0  add     eax, edi
0x180053ff2  mov     cs:InitCount, eax
0x180053ff8  jnz     short loc_180053FFF
0x180053ffa  call    IpTblCleanup
0x180053fff  mov     rcx, cs:hHandle
0x180054006  lea     rsi, WPP_GLOBAL_Control
0x18005400d  test    rcx, rcx
0x180054010  jz      loc_1800540AA
0x180054016  mov     rax, cs:WPP_GLOBAL_Control
0x18005401d  cmp     rax, rsi
0x180054020  jz      short loc_180054047
0x180054022  test    dword ptr [rax+1Ch], 8000000h
0x180054029  jz      short loc_180054047
0x18005402b  mov     rcx, [rax+10h]
0x18005402f  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180054036  mov     edx, 47h ; 'G'
0x18005403b  call    WPP_SF_
0x180054040  mov     rcx, cs:hHandle; hHandle
0x180054047  mov     edx, edi; dwMilliseconds
0x180054049  call    cs:__imp_WaitForSingleObject
0x180054050  nop     dword ptr [rax+rax+00h]
0x180054055  test    eax, eax
0x180054057  jz      short loc_18005408F
0x180054059  call    cs:__imp_GetLastError
0x180054060  nop     dword ptr [rax+rax+00h]
0x180054065  mov     rcx, cs:WPP_GLOBAL_Control
0x18005406c  cmp     rcx, rsi
0x18005406f  jz      short loc_18005408F
0x180054071  test    byte ptr [rcx+1Ch], 10h
0x180054075  jz      short loc_18005408F
0x180054077  mov     rcx, [rcx+10h]
0x18005407b  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180054082  mov     edx, 48h ; 'H'
0x180054087  mov     r9d, eax
0x18005408a  call    WPP_SF_D
0x18005408f  mov     rcx, cs:hHandle; hObject
0x180054096  call    cs:__imp_CloseHandle
0x18005409d  nop     dword ptr [rax+rax+00h]
0x1800540a2  and     cs:hHandle, 0
0x1800540aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540b1  cmp     rcx, rsi
0x1800540b4  jz      short loc_1800540D4
0x1800540b6  test    dword ptr [rcx+1Ch], 8000000h
0x1800540bd  jz      short loc_1800540D4
0x1800540bf  mov     rcx, [rcx+10h]
0x1800540c3  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x1800540ca  mov     edx, 49h ; 'I'
0x1800540cf  call    WPP_SF_
0x1800540d4  xor     edx, edx; Val
0x1800540d6  lea     rcx, DhcpGlobalEndPointTable; void *
0x1800540dd  lea     r8d, [rdx+60h]; Size
0x1800540e1  call    memset_0
0x1800540e6  cmp     cs:DhcpQDataInitialized, 1
0x1800540ed  jnz     short loc_18005411C
0x1800540ef  lea     rcx, PacketCritSection; lpCriticalSection
0x1800540f6  call    cs:__imp_DeleteCriticalSection
0x1800540fd  nop     dword ptr [rax+rax+00h]
0x180054102  lea     rcx, QuarDecisionCritSection; lpCriticalSection
0x180054109  call    cs:__imp_DeleteCriticalSection
0x180054110  nop     dword ptr [rax+rax+00h]
0x180054115  and     cs:DhcpQDataInitialized, 0
0x18005411c  lea     rcx, DhcpGlobalReadWriteLock
0x180054123  call    RwLockCleanup
0x180054128  lea     rcx, SocketRwLock
0x18005412f  mov     rsi, [rsp+28h+arg_0]
0x180054134  add     rsp, 20h
0x180054138  pop     rdi
0x180054139  jmp     RwLockCleanup
```
