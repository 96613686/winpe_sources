# DhcpCleanupClientToServer

- ea: `0x180053c80`
- end: `0x180053e6a`
- name: `DhcpCleanupClientToServer`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180027558`

## callees

- `0x18000282c`
- `0x180003228`
- `0x180023cf0`
- `0x180024838`
- `0x180033e3c`
- `0x180053c80`
- `0x18005e1f8`
- `0x180061aa0`
- `0x1800cda7a`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180053d6f`
- `KERNEL32!WaitForSingleObject` at `0x180053d6f`
- `KERNEL32!DeleteCriticalSection` at `0x180053e1f`
- `KERNEL32!DeleteCriticalSection` at `0x180053e32`
- `KERNEL32!DeleteCriticalSection` at `0x180053e1f`
- `KERNEL32!DeleteCriticalSection` at `0x180053e32`
- `KERNEL32!GetLastError` at `0x180053d7f`
- `KERNEL32!GetLastError` at `0x180053d7f`
- `KERNEL32!CloseHandle` at `0x180053cb5`
- `KERNEL32!CloseHandle` at `0x180053cde`
- `KERNEL32!CloseHandle` at `0x180053dbc`
- `KERNEL32!CloseHandle` at `0x180053cb5`
- `KERNEL32!CloseHandle` at `0x180053cde`
- `KERNEL32!CloseHandle` at `0x180053dbc`

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
  if ( dword_1800FD150 )
  {
    v0 = --dword_1800FD150;
    if ( qword_1800FD188 )
    {
      CloseHandle(qword_1800FD188);
      v0 = dword_1800FD150;
      qword_1800FD188 = 0;
    }
    if ( CompletionPort )
    {
      CloseHandle(CompletionPort);
      v0 = dword_1800FD150;
      CompletionPort = 0;
    }
    if ( v0 )
    {
      dword_1800FD150 = v0 - 1;
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
0x180053c80  mov     [rsp+arg_8], rsi
0x180053c85  push    rdi
0x180053c86  sub     rsp, 20h
0x180053c8a  call    ThreadsStop
0x180053c8f  call    PingCleanup
0x180053c94  mov     eax, cs:dword_1800FD150
0x180053c9a  or      edi, 0FFFFFFFFh
0x180053c9d  test    eax, eax
0x180053c9f  jz      short loc_180053D0C
0x180053ca1  mov     rcx, cs:qword_1800FD188; hObject
0x180053ca8  add     eax, edi
0x180053caa  mov     cs:dword_1800FD150, eax
0x180053cb0  test    rcx, rcx
0x180053cb3  jz      short loc_180053CD2
0x180053cb5  call    cs:__imp_CloseHandle
0x180053cbc  nop     dword ptr [rax+rax+00h]
0x180053cc1  mov     eax, cs:dword_1800FD150
0x180053cc7  mov     cs:qword_1800FD188, 0
0x180053cd2  mov     rcx, cs:CompletionPort; hObject
0x180053cd9  test    rcx, rcx
0x180053cdc  jz      short loc_180053CFB
0x180053cde  call    cs:__imp_CloseHandle
0x180053ce5  nop     dword ptr [rax+rax+00h]
0x180053cea  mov     eax, cs:dword_1800FD150
0x180053cf0  mov     cs:CompletionPort, 0
0x180053cfb  test    eax, eax
0x180053cfd  jz      short loc_180053D0C
0x180053cff  add     eax, edi
0x180053d01  mov     cs:dword_1800FD150, eax
0x180053d07  call    CleanupQData
0x180053d0c  mov     eax, cs:InitCount
0x180053d12  test    eax, eax
0x180053d14  jz      short loc_180053D25
0x180053d16  add     eax, edi
0x180053d18  mov     cs:InitCount, eax
0x180053d1e  jnz     short loc_180053D25
0x180053d20  call    IpTblCleanup
0x180053d25  mov     rcx, cs:hHandle
0x180053d2c  lea     rsi, WPP_GLOBAL_Control
0x180053d33  test    rcx, rcx
0x180053d36  jz      loc_180053DD3
0x180053d3c  mov     rax, cs:WPP_GLOBAL_Control
0x180053d43  cmp     rax, rsi
0x180053d46  jz      short loc_180053D6D
0x180053d48  test    dword ptr [rax+1Ch], 8000000h
0x180053d4f  jz      short loc_180053D6D
0x180053d51  mov     rcx, [rax+10h]
0x180053d55  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180053d5c  mov     edx, 47h ; 'G'
0x180053d61  call    WPP_SF_
0x180053d66  mov     rcx, cs:hHandle; hHandle
0x180053d6d  mov     edx, edi; dwMilliseconds
0x180053d6f  call    cs:__imp_WaitForSingleObject
0x180053d76  nop     dword ptr [rax+rax+00h]
0x180053d7b  test    eax, eax
0x180053d7d  jz      short loc_180053DB5
0x180053d7f  call    cs:__imp_GetLastError
0x180053d86  nop     dword ptr [rax+rax+00h]
0x180053d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d92  cmp     rcx, rsi
0x180053d95  jz      short loc_180053DB5
0x180053d97  test    byte ptr [rcx+1Ch], 10h
0x180053d9b  jz      short loc_180053DB5
0x180053d9d  mov     rcx, [rcx+10h]
0x180053da1  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180053da8  mov     edx, 48h ; 'H'
0x180053dad  mov     r9d, eax
0x180053db0  call    WPP_SF_D
0x180053db5  mov     rcx, cs:hHandle; hObject
0x180053dbc  call    cs:__imp_CloseHandle
0x180053dc3  nop     dword ptr [rax+rax+00h]
0x180053dc8  mov     cs:hHandle, 0
0x180053dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180053dda  cmp     rcx, rsi
0x180053ddd  jz      short loc_180053DFD
0x180053ddf  test    dword ptr [rcx+1Ch], 8000000h
0x180053de6  jz      short loc_180053DFD
0x180053de8  mov     rcx, [rcx+10h]
0x180053dec  lea     r8, WPP_4f15ae1d903a34335f86842f001cf84b_Traceguids
0x180053df3  mov     edx, 49h ; 'I'
0x180053df8  call    WPP_SF_
0x180053dfd  xor     edx, edx; Val
0x180053dff  lea     rcx, DhcpGlobalEndPointTable; void *
0x180053e06  lea     r8d, [rdx+60h]; Size
0x180053e0a  call    memset_0
0x180053e0f  cmp     cs:DhcpQDataInitialized, 1
0x180053e16  jnz     short loc_180053E48
0x180053e18  lea     rcx, PacketCritSection; lpCriticalSection
0x180053e1f  call    cs:__imp_DeleteCriticalSection
0x180053e26  nop     dword ptr [rax+rax+00h]
0x180053e2b  lea     rcx, QuarDecisionCritSection; lpCriticalSection
0x180053e32  call    cs:__imp_DeleteCriticalSection
0x180053e39  nop     dword ptr [rax+rax+00h]
0x180053e3e  mov     cs:DhcpQDataInitialized, 0
0x180053e48  lea     rcx, DhcpGlobalReadWriteLock
0x180053e4f  call    RwLockCleanup
0x180053e54  lea     rcx, SocketRwLock
0x180053e5b  mov     rsi, [rsp+28h+arg_8]
0x180053e60  add     rsp, 20h
0x180053e64  pop     rdi
0x180053e65  jmp     RwLockCleanup
```
