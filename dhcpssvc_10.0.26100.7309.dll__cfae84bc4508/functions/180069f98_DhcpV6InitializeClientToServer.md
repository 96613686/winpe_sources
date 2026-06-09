# DhcpV6InitializeClientToServer

- ea: `0x180069f98`
- end: `0x18006a22e`
- name: `DhcpV6InitializeClientToServer`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006632c`

## callees

- `0x180002854`
- `0x180002a00`
- `0x18000323c`
- `0x1800252fc`
- `0x180025360`
- `0x180069f98`
- `0x180073b00`
- `0x18007723c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18006a00f`
- `KERNEL32!CreateEventW` at `0x18006a00f`
- `KERNEL32!GetProcessHeap` at `0x18006a076`
- `KERNEL32!GetProcessHeap` at `0x18006a0d6`
- `KERNEL32!GetProcessHeap` at `0x18006a076`
- `KERNEL32!GetProcessHeap` at `0x18006a0d6`
- `KERNEL32!CreateThread` at `0x18006a143`
- `KERNEL32!CreateThread` at `0x18006a143`
- `KERNEL32!GetLastError` at `0x18006a04d`
- `KERNEL32!GetLastError` at `0x18006a0ee`
- `KERNEL32!GetLastError` at `0x18006a15b`
- `KERNEL32!GetLastError` at `0x18006a04d`
- `KERNEL32!GetLastError` at `0x18006a0ee`
- `KERNEL32!GetLastError` at `0x18006a15b`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_c478ec705b883cfeef20aad3be309da3_Traceguids);
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
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_c478ec705b883cfeef20aad3be309da3_Traceguids, LastError);
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
      WPP_SF_D(v6[2], v7, &WPP_c478ec705b883cfeef20aad3be309da3_Traceguids, v8);
LABEL_37:
      v6 = WPP_GLOBAL_Control;
LABEL_38:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        WPP_SF_D(v6[2], 164, &WPP_c478ec705b883cfeef20aad3be309da3_Traceguids, LastError);
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
      qword_1800FB268 = CreateThread(0, 0, DhcpV6MessageLoop, 0, 0, &ThreadId);
      if ( qword_1800FB268 )
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
0x180069f98  mov     [rsp+arg_8], rbx
0x180069f9d  mov     [rsp+arg_10], rbp
0x180069fa2  push    rdi
0x180069fa3  sub     rsp, 30h
0x180069fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180069fae  lea     rdi, WPP_GLOBAL_Control
0x180069fb5  lea     rbp, WPP_c478ec705b883cfeef20aad3be309da3_Traceguids
0x180069fbc  cmp     rcx, rdi
0x180069fbf  jz      short loc_180069FD8
0x180069fc1  test    byte ptr [rcx+1Ch], 20h
0x180069fc5  jz      short loc_180069FD8
0x180069fc7  mov     rcx, [rcx+10h]
0x180069fcb  mov     edx, 9Eh
0x180069fd0  mov     r8, rbp
0x180069fd3  call    WPP_SF_
0x180069fd8  lea     rcx, DhcpV6GlobalReadWriteLock
0x180069fdf  call    RwLockInit
0x180069fe4  mov     ebx, eax
0x180069fe6  test    eax, eax
0x180069fe8  jnz     loc_18006A1DD
0x180069fee  lea     rcx, DhcpV6SocketRwLock
0x180069ff5  call    RwLockInit
0x180069ffa  mov     ebx, eax
0x180069ffc  test    eax, eax
0x180069ffe  jnz     loc_18006A1DD
0x18006a004  xor     r9d, r9d; lpName
0x18006a007  lea     edx, [rax+1]; bManualReset
0x18006a00a  xor     r8d, r8d; bInitialState
0x18006a00d  xor     ecx, ecx; lpEventAttributes
0x18006a00f  call    cs:__imp_CreateEventW
0x18006a016  nop     dword ptr [rax+rax+00h]
0x18006a01b  mov     cs:DhcpV6GlobalEndpointReadyEvent, rax
0x18006a022  test    rax, rax
0x18006a025  jnz     short loc_18006A063
0x18006a027  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a02e  cmp     rcx, rdi
0x18006a031  jz      short loc_18006A04D
0x18006a033  test    byte ptr [rcx+1Ch], 10h
0x18006a037  jz      short loc_18006A04D
0x18006a039  mov     rcx, [rcx+10h]
0x18006a03d  mov     edx, 9Fh
0x18006a042  mov     r9d, ebx
0x18006a045  mov     r8, rbp
0x18006a048  call    WPP_SF_D
0x18006a04d  call    cs:__imp_GetLastError
0x18006a054  nop     dword ptr [rax+rax+00h]
0x18006a059  mov     ebx, eax
0x18006a05b  test    eax, eax
0x18006a05d  jnz     loc_18006A1F5
0x18006a063  mov     eax, cs:DhcpV6InitCount
0x18006a069  inc     eax
0x18006a06b  mov     cs:DhcpV6InitCount, eax
0x18006a071  cmp     eax, 1
0x18006a074  jnz     short loc_18006A0C9
0x18006a076  call    cs:__imp_GetProcessHeap
0x18006a07d  nop     dword ptr [rax+rax+00h]
0x18006a082  mov     r9, rax
0x18006a085  call    DhcpV6IpTblInitialize
0x18006a08a  mov     ebx, eax
0x18006a08c  test    eax, eax
0x18006a08e  jz      short loc_18006A0C9
0x18006a090  dec     cs:DhcpV6InitCount
0x18006a096  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a09d  cmp     rcx, rdi
0x18006a0a0  jz      loc_18006A21B
0x18006a0a6  test    byte ptr [rcx+1Ch], 10h
0x18006a0aa  jz      loc_18006A1FC
0x18006a0b0  mov     edx, 0A0h
0x18006a0b5  mov     r9d, eax
0x18006a0b8  mov     rcx, [rcx+10h]
0x18006a0bc  mov     r8, rbp
0x18006a0bf  call    WPP_SF_D
0x18006a0c4  jmp     loc_18006A1F5
0x18006a0c9  call    DhcpV6InitQData
0x18006a0ce  test    eax, eax
0x18006a0d0  jnz     loc_18006A21D
0x18006a0d6  call    cs:__imp_GetProcessHeap
0x18006a0dd  nop     dword ptr [rax+rax+00h]
0x18006a0e2  mov     cs:GlobalProcessHeap, rax
0x18006a0e9  test    rax, rax
0x18006a0ec  jnz     short loc_18006A121
0x18006a0ee  call    cs:__imp_GetLastError
0x18006a0f5  nop     dword ptr [rax+rax+00h]
0x18006a0fa  mov     ebx, eax
0x18006a0fc  test    eax, eax
0x18006a0fe  jz      short loc_18006A121
0x18006a100  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a107  cmp     rcx, rdi
0x18006a10a  jz      loc_18006A21B
0x18006a110  test    byte ptr [rcx+1Ch], 10h
0x18006a114  jz      loc_18006A1FC
0x18006a11a  mov     edx, 0A1h
0x18006a11f  jmp     short loc_18006A0B5
0x18006a121  and     [rsp+38h+ThreadId], 0
0x18006a126  lea     rax, [rsp+38h+ThreadId]
0x18006a12b  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18006a130  lea     r8, DhcpV6MessageLoop; lpStartAddress
0x18006a137  and     [rsp+38h+var_18], 0
0x18006a13c  xor     r9d, r9d; lpParameter
0x18006a13f  xor     edx, edx; dwStackSize
0x18006a141  xor     ecx, ecx; lpThreadAttributes
0x18006a143  call    cs:__imp_CreateThread
0x18006a14a  nop     dword ptr [rax+rax+00h]
0x18006a14f  mov     cs:qword_1800FB268, rax
0x18006a156  test    rax, rax
0x18006a159  jnz     short loc_18006A1B6
0x18006a15b  call    cs:__imp_GetLastError
0x18006a162  nop     dword ptr [rax+rax+00h]
0x18006a167  mov     ebx, eax
0x18006a169  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a170  cmp     rcx, rdi
0x18006a173  jz      short loc_18006A19A
0x18006a175  test    byte ptr [rcx+1Ch], 10h
0x18006a179  jz      short loc_18006A19A
0x18006a17b  mov     rcx, [rcx+10h]
0x18006a17f  lea     r8, WPP_7393b155433f392c1624c7b14fc47429_Traceguids
0x18006a186  mov     edx, 2Bh ; '+'
0x18006a18b  mov     r9d, eax
0x18006a18e  call    WPP_SF_D
0x18006a193  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a19a  test    ebx, ebx
0x18006a19c  jz      short loc_18006A1B6
0x18006a19e  cmp     rcx, rdi
0x18006a1a1  jz      short loc_18006A21B
0x18006a1a3  test    byte ptr [rcx+1Ch], 10h
0x18006a1a7  jz      short loc_18006A1FC
0x18006a1a9  mov     edx, 0A2h
0x18006a1ae  mov     r9d, ebx
0x18006a1b1  jmp     loc_18006A0B8
0x18006a1b6  call    AddressCacherInit
0x18006a1bb  mov     ebx, eax
0x18006a1bd  test    eax, eax
0x18006a1bf  jz      short loc_18006A1F5
0x18006a1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a1c8  cmp     rcx, rdi
0x18006a1cb  jz      short loc_18006A21B
0x18006a1cd  test    byte ptr [rcx+1Ch], 10h
0x18006a1d1  jz      short loc_18006A1FC
0x18006a1d3  mov     edx, 0A3h
0x18006a1d8  jmp     loc_18006A0B5
0x18006a1dd  lea     rcx, DhcpV6GlobalReadWriteLock
0x18006a1e4  call    RwLockCleanup
0x18006a1e9  lea     rcx, DhcpV6SocketRwLock
0x18006a1f0  call    RwLockCleanup
0x18006a1f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a1fc  cmp     rcx, rdi
0x18006a1ff  jz      short loc_18006A21B
0x18006a201  test    byte ptr [rcx+1Ch], 20h
0x18006a205  jz      short loc_18006A21B
0x18006a207  mov     rcx, [rcx+10h]
0x18006a20b  mov     edx, 0A4h
0x18006a210  mov     r9d, ebx
0x18006a213  mov     r8, rbp
0x18006a216  call    WPP_SF_D
0x18006a21b  mov     eax, ebx
0x18006a21d  mov     rbx, [rsp+38h+arg_8]
0x18006a222  mov     rbp, [rsp+38h+arg_10]
0x18006a227  add     rsp, 30h
0x18006a22b  pop     rdi
0x18006a22c  retn
```
