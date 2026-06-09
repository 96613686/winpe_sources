# DhcpV6InitializeClientToServer

- ea: `0x180069d98`
- end: `0x18006a034`
- name: `DhcpV6InitializeClientToServer`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800660dc`

## callees

- `0x18000282c`
- `0x1800029d8`
- `0x180003228`
- `0x180024838`
- `0x18002489c`
- `0x180069d98`
- `0x180073914`
- `0x1800770a4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180069e0f`
- `KERNEL32!CreateEventW` at `0x180069e0f`
- `KERNEL32!GetProcessHeap` at `0x180069e76`
- `KERNEL32!GetProcessHeap` at `0x180069ed6`
- `KERNEL32!GetProcessHeap` at `0x180069e76`
- `KERNEL32!GetProcessHeap` at `0x180069ed6`
- `KERNEL32!GetLastError` at `0x180069e4d`
- `KERNEL32!GetLastError` at `0x180069eee`
- `KERNEL32!GetLastError` at `0x180069f61`
- `KERNEL32!GetLastError` at `0x180069e4d`
- `KERNEL32!GetLastError` at `0x180069eee`
- `KERNEL32!GetLastError` at `0x180069f61`
- `KERNEL32!CreateThread` at `0x180069f49`
- `KERNEL32!CreateThread` at `0x180069f49`

## pseudocode

```c
__int64 DhcpV6InitializeClientToServer()
{
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  DWORD v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 result; // rax
  DWORD v10; // eax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids);
  LastError = RwLockInit(&DhcpV6GlobalReadWriteLock);
  if ( LastError || (LastError = RwLockInit(&DhcpV6SocketRwLock)) != 0 )
  {
    RwLockCleanup(&DhcpV6GlobalReadWriteLock);
    RwLockCleanup(&DhcpV6SocketRwLock);
    goto LABEL_37;
  }
  DhcpV6GlobalEndpointReadyEvent = CreateEventW(0, 1, 0, 0);
  if ( !DhcpV6GlobalEndpointReadyEvent )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids, LastError);
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_37;
  }
  if ( ++DhcpV6InitCount == 1
    && (ProcessHeap = GetProcessHeap(), v5 = DhcpV6IpTblInitialize(v3, v2, v4, ProcessHeap), (LastError = v5) != 0) )
  {
    --DhcpV6InitCount;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_38;
      v7 = 160;
LABEL_16:
      v8 = v5;
LABEL_17:
      WPP_SF_D(v6[2], v7, &WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids, v8);
LABEL_37:
      v6 = WPP_GLOBAL_Control;
LABEL_38:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        WPP_SF_D(v6[2], 164, &WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids, LastError);
    }
  }
  else
  {
    result = DhcpV6InitQData();
    if ( (_DWORD)result )
      return result;
    GlobalProcessHeap = GetProcessHeap();
    if ( GlobalProcessHeap || (v5 = GetLastError(), (LastError = v5) == 0) )
    {
      ThreadId = 0;
      qword_1800FD220 = CreateThread(0, 0, DhcpV6MessageLoop, 0, 0, &ThreadId);
      if ( qword_1800FD220 )
        goto LABEL_32;
      v10 = GetLastError();
      LastError = v10;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_7393b155433f392c1624c7b14fc47429_Traceguids, v10);
        v6 = WPP_GLOBAL_Control;
      }
      if ( !LastError )
      {
LABEL_32:
        v5 = AddressCacherInit();
        LastError = v5;
        if ( !v5 )
          goto LABEL_37;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            goto LABEL_38;
          v7 = 163;
          goto LABEL_16;
        }
      }
      else if ( v6 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v6 + 28) & 0x10) == 0 )
          goto LABEL_38;
        v7 = 162;
        v8 = LastError;
        goto LABEL_17;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_38;
        v7 = 161;
        goto LABEL_16;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180069d98  mov     [rsp+arg_8], rbx
0x180069d9d  mov     [rsp+arg_10], rbp
0x180069da2  push    rdi
0x180069da3  sub     rsp, 30h
0x180069da7  mov     rcx, cs:WPP_GLOBAL_Control
0x180069dae  lea     rdi, WPP_GLOBAL_Control
0x180069db5  lea     rbp, WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids
0x180069dbc  cmp     rcx, rdi
0x180069dbf  jz      short loc_180069DD8
0x180069dc1  test    byte ptr [rcx+1Ch], 20h
0x180069dc5  jz      short loc_180069DD8
0x180069dc7  mov     rcx, [rcx+10h]
0x180069dcb  mov     edx, 9Eh
0x180069dd0  mov     r8, rbp
0x180069dd3  call    WPP_SF_
0x180069dd8  lea     rcx, DhcpV6GlobalReadWriteLock
0x180069ddf  call    RwLockInit
0x180069de4  mov     ebx, eax
0x180069de6  test    eax, eax
0x180069de8  jnz     loc_180069FE3
0x180069dee  lea     rcx, DhcpV6SocketRwLock
0x180069df5  call    RwLockInit
0x180069dfa  mov     ebx, eax
0x180069dfc  test    eax, eax
0x180069dfe  jnz     loc_180069FE3
0x180069e04  xor     r9d, r9d; lpName
0x180069e07  lea     edx, [rax+1]; bManualReset
0x180069e0a  xor     r8d, r8d; bInitialState
0x180069e0d  xor     ecx, ecx; lpEventAttributes
0x180069e0f  call    cs:__imp_CreateEventW
0x180069e16  nop     dword ptr [rax+rax+00h]
0x180069e1b  mov     cs:DhcpV6GlobalEndpointReadyEvent, rax
0x180069e22  test    rax, rax
0x180069e25  jnz     short loc_180069E63
0x180069e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e2e  cmp     rcx, rdi
0x180069e31  jz      short loc_180069E4D
0x180069e33  test    byte ptr [rcx+1Ch], 10h
0x180069e37  jz      short loc_180069E4D
0x180069e39  mov     rcx, [rcx+10h]
0x180069e3d  mov     edx, 9Fh
0x180069e42  mov     r9d, ebx
0x180069e45  mov     r8, rbp
0x180069e48  call    WPP_SF_D
0x180069e4d  call    cs:__imp_GetLastError
0x180069e54  nop     dword ptr [rax+rax+00h]
0x180069e59  mov     ebx, eax
0x180069e5b  test    eax, eax
0x180069e5d  jnz     loc_180069FFB
0x180069e63  mov     eax, cs:DhcpV6InitCount
0x180069e69  inc     eax
0x180069e6b  mov     cs:DhcpV6InitCount, eax
0x180069e71  cmp     eax, 1
0x180069e74  jnz     short loc_180069EC9
0x180069e76  call    cs:__imp_GetProcessHeap
0x180069e7d  nop     dword ptr [rax+rax+00h]
0x180069e82  mov     r9, rax
0x180069e85  call    DhcpV6IpTblInitialize
0x180069e8a  mov     ebx, eax
0x180069e8c  test    eax, eax
0x180069e8e  jz      short loc_180069EC9
0x180069e90  dec     cs:DhcpV6InitCount
0x180069e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e9d  cmp     rcx, rdi
0x180069ea0  jz      loc_18006A021
0x180069ea6  test    byte ptr [rcx+1Ch], 10h
0x180069eaa  jz      loc_18006A002
0x180069eb0  mov     edx, 0A0h
0x180069eb5  mov     r9d, eax
0x180069eb8  mov     rcx, [rcx+10h]
0x180069ebc  mov     r8, rbp
0x180069ebf  call    WPP_SF_D
0x180069ec4  jmp     loc_180069FFB
0x180069ec9  call    DhcpV6InitQData
0x180069ece  test    eax, eax
0x180069ed0  jnz     loc_18006A023
0x180069ed6  call    cs:__imp_GetProcessHeap
0x180069edd  nop     dword ptr [rax+rax+00h]
0x180069ee2  mov     cs:GlobalProcessHeap, rax
0x180069ee9  test    rax, rax
0x180069eec  jnz     short loc_180069F21
0x180069eee  call    cs:__imp_GetLastError
0x180069ef5  nop     dword ptr [rax+rax+00h]
0x180069efa  mov     ebx, eax
0x180069efc  test    eax, eax
0x180069efe  jz      short loc_180069F21
0x180069f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180069f07  cmp     rcx, rdi
0x180069f0a  jz      loc_18006A021
0x180069f10  test    byte ptr [rcx+1Ch], 10h
0x180069f14  jz      loc_18006A002
0x180069f1a  mov     edx, 0A1h
0x180069f1f  jmp     short loc_180069EB5
0x180069f21  lea     rax, [rsp+38h+ThreadId]
0x180069f26  mov     [rsp+38h+ThreadId], 0
0x180069f2e  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180069f33  lea     r8, DhcpV6MessageLoop; lpStartAddress
0x180069f3a  xor     r9d, r9d; lpParameter
0x180069f3d  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180069f45  xor     edx, edx; dwStackSize
0x180069f47  xor     ecx, ecx; lpThreadAttributes
0x180069f49  call    cs:__imp_CreateThread
0x180069f50  nop     dword ptr [rax+rax+00h]
0x180069f55  mov     cs:qword_1800FD220, rax
0x180069f5c  test    rax, rax
0x180069f5f  jnz     short loc_180069FBC
0x180069f61  call    cs:__imp_GetLastError
0x180069f68  nop     dword ptr [rax+rax+00h]
0x180069f6d  mov     ebx, eax
0x180069f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069f76  cmp     rcx, rdi
0x180069f79  jz      short loc_180069FA0
0x180069f7b  test    byte ptr [rcx+1Ch], 10h
0x180069f7f  jz      short loc_180069FA0
0x180069f81  mov     rcx, [rcx+10h]
0x180069f85  lea     r8, WPP_7393b155433f392c1624c7b14fc47429_Traceguids
0x180069f8c  mov     edx, 2Bh ; '+'
0x180069f91  mov     r9d, eax
0x180069f94  call    WPP_SF_D
0x180069f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180069fa0  test    ebx, ebx
0x180069fa2  jz      short loc_180069FBC
0x180069fa4  cmp     rcx, rdi
0x180069fa7  jz      short loc_18006A021
0x180069fa9  test    byte ptr [rcx+1Ch], 10h
0x180069fad  jz      short loc_18006A002
0x180069faf  mov     edx, 0A2h
0x180069fb4  mov     r9d, ebx
0x180069fb7  jmp     loc_180069EB8
0x180069fbc  call    AddressCacherInit
0x180069fc1  mov     ebx, eax
0x180069fc3  test    eax, eax
0x180069fc5  jz      short loc_180069FFB
0x180069fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180069fce  cmp     rcx, rdi
0x180069fd1  jz      short loc_18006A021
0x180069fd3  test    byte ptr [rcx+1Ch], 10h
0x180069fd7  jz      short loc_18006A002
0x180069fd9  mov     edx, 0A3h
0x180069fde  jmp     loc_180069EB5
0x180069fe3  lea     rcx, DhcpV6GlobalReadWriteLock
0x180069fea  call    RwLockCleanup
0x180069fef  lea     rcx, DhcpV6SocketRwLock
0x180069ff6  call    RwLockCleanup
0x180069ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a002  cmp     rcx, rdi
0x18006a005  jz      short loc_18006A021
0x18006a007  test    byte ptr [rcx+1Ch], 20h
0x18006a00b  jz      short loc_18006A021
0x18006a00d  mov     rcx, [rcx+10h]
0x18006a011  mov     edx, 0A4h
0x18006a016  mov     r9d, ebx
0x18006a019  mov     r8, rbp
0x18006a01c  call    WPP_SF_D
0x18006a021  mov     eax, ebx
0x18006a023  mov     rbx, [rsp+38h+arg_8]
0x18006a028  mov     rbp, [rsp+38h+arg_10]
0x18006a02d  add     rsp, 30h
0x18006a031  pop     rdi
0x18006a032  retn
```
