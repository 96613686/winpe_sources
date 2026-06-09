# NhCreateRawDatagramSocket(_NH_RCSOCKET *)

- ea: `0x180055d08`
- end: `0x180055fb0`
- name: `?NhCreateRawDatagramSocket@@YAKPEAU_NH_RCSOCKET@@@Z`
- size: `680`
- prototype: `unsigned int __fastcall(struct _NH_RCSOCKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007dad0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180055d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055d6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055d6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055ee0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055ee0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180055e34`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180055e34`
- `WS2_32!WSASocketW` at `0x180055de7`
- `WS2_32!WSASocketW` at `0x180055de7`
- `WS2_32!WSAIoctl` at `0x180055f62`
- `WS2_32!WSAIoctl` at `0x180055f62`
- `WS2_32!__imp_closesocket` at `0x180055ec5`
- `WS2_32!__imp_closesocket` at `0x180055ec5`
- `WS2_32!__imp_setsockopt` at `0x180055e7f`
- `WS2_32!__imp_setsockopt` at `0x180055e7f`
- `WS2_32!__imp_WSAGetLastError` at `0x180055df6`
- `WS2_32!__imp_WSAGetLastError` at `0x180055e8e`
- `WS2_32!__imp_WSAGetLastError` at `0x180055df6`
- `WS2_32!__imp_WSAGetLastError` at `0x180055e8e`

## pseudocode

```c
__int64 __fastcall NhCreateRawDatagramSocket(struct _NH_RCSOCKET *a1)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  DWORD v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  void *v7; // rax
  SOCKET v8; // rbp
  DWORD Error; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int optval; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbBytesReturned; // [rsp+78h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  optval = 0;
  cbBytesReturned = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a1 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v6 = 40;
    goto LABEL_10;
  }
  *(_DWORD *)a1 = 2;
  v7 = (void *)WSASocketW(2, 3, 17, 0, 0, 1u);
  v8 = (SOCKET)v7;
  if ( v7 == (void *)-1LL )
  {
    LastError = WSAGetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v6 = 41;
LABEL_10:
    WPP_SF_d(v5[2], v6, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
LABEL_28:
    v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_29:
    if ( *((_QWORD *)a1 + 1) )
    {
      _InterlockedDecrement((volatile signed __int32 *)a1);
      CloseHandle(*((HANDLE *)a1 + 1));
      *((_QWORD *)a1 + 1) = 0;
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 6u )
      WPP_SF_d(v5[2], 45, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v4);
    return v4;
  }
  if ( !BindIoCompletionCallback(v7, NhpIoCompletionRoutine, 0) )
  {
    Error = GetLastError();
    v4 = Error;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v11 = 42;
LABEL_26:
    WPP_SF_d(v10[2], v11, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, Error);
LABEL_27:
    closesocket(v8);
    goto LABEL_28;
  }
  optval = 1;
  if ( setsockopt(v8, 0, 2, (const char *)&optval, 4) == -1 )
  {
    Error = WSAGetLastError();
    v4 = Error;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_27;
    }
    v11 = 43;
    goto LABEL_26;
  }
  optval = 1;
  WSAIoctl(v8, 0x98000007, &optval, 4u, 0, 0, &cbBytesReturned, 0, 0);
  *((_QWORD *)a1 + 2) = v8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180055d08  mov     [rsp+arg_10], rbx
0x180055d0d  mov     [rsp+arg_18], rbp
0x180055d12  push    rsi
0x180055d13  push    r12
0x180055d15  push    r13
0x180055d17  sub     rsp, 50h
0x180055d1b  mov     rsi, rcx
0x180055d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d25  lea     r12, WPP_GLOBAL_Control
0x180055d2c  lea     r13, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x180055d33  cmp     rcx, r12
0x180055d36  jz      short loc_180055D55
0x180055d38  test    byte ptr [rcx+1Ch], 8
0x180055d3c  jz      short loc_180055D55
0x180055d3e  cmp     byte ptr [rcx+19h], 6
0x180055d42  jb      short loc_180055D55
0x180055d44  mov     rcx, [rcx+10h]
0x180055d48  mov     edx, 27h ; '''
0x180055d4d  mov     r8, r13
0x180055d50  call    WPP_SF_
0x180055d55  xor     r9d, r9d; lpName
0x180055d58  mov     [rsp+68h+optval], 0
0x180055d60  xor     r8d, r8d; bInitialState
0x180055d63  mov     [rsp+68h+cbBytesReturned], 0
0x180055d6b  xor     edx, edx; bManualReset
0x180055d6d  xor     ecx, ecx; lpEventAttributes
0x180055d6f  call    cs:__imp_CreateEventW
0x180055d75  mov     [rsi+8], rax
0x180055d79  test    rax, rax
0x180055d7c  jnz     short loc_180055DC3
0x180055d7e  call    cs:__imp_GetLastError
0x180055d84  mov     ebx, eax
0x180055d86  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d8d  cmp     rcx, r12
0x180055d90  jz      loc_180055ED2
0x180055d96  test    byte ptr [rcx+1Ch], 8
0x180055d9a  jz      loc_180055ED2
0x180055da0  cmp     byte ptr [rcx+19h], 2
0x180055da4  jb      loc_180055ED2
0x180055daa  mov     edx, 28h ; '('
0x180055daf  mov     rcx, [rcx+10h]
0x180055db3  mov     r9d, eax
0x180055db6  mov     r8, r13
0x180055db9  call    WPP_SF_d
0x180055dbe  jmp     loc_180055ECB
0x180055dc3  mov     ebx, 1
0x180055dc8  mov     dword ptr [rsi], 2
0x180055dce  mov     [rsp+68h+dwFlags], ebx; dwFlags
0x180055dd2  xor     r9d, r9d; lpProtocolInfo
0x180055dd5  mov     [rsp+68h+g], 0; g
0x180055ddd  lea     edx, [rbx+2]; type
0x180055de0  lea     ecx, [rbx+1]; af
0x180055de3  lea     r8d, [rbx+10h]; protocol
0x180055de7  call    cs:__imp_WSASocketW
0x180055ded  mov     rbp, rax
0x180055df0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055df4  jnz     short loc_180055E27
0x180055df6  call    cs:__imp_WSAGetLastError
0x180055dfc  mov     ebx, eax
0x180055dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e05  cmp     rcx, r12
0x180055e08  jz      loc_180055ED2
0x180055e0e  test    byte ptr [rcx+1Ch], 8
0x180055e12  jz      loc_180055ED2
0x180055e18  cmp     byte ptr [rcx+19h], 2
0x180055e1c  jb      loc_180055ED2
0x180055e22  lea     edx, [rbp+2Ah]
0x180055e25  jmp     short loc_180055DAF
0x180055e27  xor     r8d, r8d; Flags
0x180055e2a  lea     rdx, ?NhpIoCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x180055e31  mov     rcx, rbp; FileHandle
0x180055e34  call    cs:__imp_BindIoCompletionCallback
0x180055e3a  test    eax, eax
0x180055e3c  jnz     short loc_180055E65
0x180055e3e  call    cs:__imp_GetLastError
0x180055e44  mov     ebx, eax
0x180055e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e4d  cmp     rcx, r12
0x180055e50  jz      short loc_180055EC2
0x180055e52  test    byte ptr [rcx+1Ch], 8
0x180055e56  jz      short loc_180055EC2
0x180055e58  cmp     byte ptr [rcx+19h], 2
0x180055e5c  jb      short loc_180055EC2
0x180055e5e  mov     edx, 2Ah ; '*'
0x180055e63  jmp     short loc_180055EB3
0x180055e65  xor     edx, edx; level
0x180055e67  mov     [rsp+68h+optval], ebx
0x180055e6b  lea     r9, [rsp+68h+optval]; optval
0x180055e70  mov     [rsp+68h+g], 4; optlen
0x180055e78  mov     rcx, rbp; s
0x180055e7b  lea     r8d, [rdx+2]; optname
0x180055e7f  call    cs:__imp_setsockopt
0x180055e85  cmp     eax, 0FFFFFFFFh
0x180055e88  jnz     loc_180055F1E
0x180055e8e  call    cs:__imp_WSAGetLastError
0x180055e94  mov     ebx, eax
0x180055e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e9d  cmp     rcx, r12
0x180055ea0  jz      short loc_180055EC2
0x180055ea2  test    byte ptr [rcx+1Ch], 8
0x180055ea6  jz      short loc_180055EC2
0x180055ea8  cmp     byte ptr [rcx+19h], 2
0x180055eac  jb      short loc_180055EC2
0x180055eae  mov     edx, 2Bh ; '+'
0x180055eb3  mov     rcx, [rcx+10h]
0x180055eb7  mov     r9d, eax
0x180055eba  mov     r8, r13
0x180055ebd  call    WPP_SF_d
0x180055ec2  mov     rcx, rbp; s
0x180055ec5  call    cs:__imp_closesocket
0x180055ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ed2  cmp     qword ptr [rsi+8], 0
0x180055ed7  jz      short loc_180055EF5
0x180055ed9  lock dec dword ptr [rsi]
0x180055edc  mov     rcx, [rsi+8]; hObject
0x180055ee0  call    cs:__imp_CloseHandle
0x180055ee6  mov     qword ptr [rsi+8], 0
0x180055eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ef5  cmp     rcx, r12
0x180055ef8  jz      short loc_180055F1A
0x180055efa  test    byte ptr [rcx+1Ch], 8
0x180055efe  jz      short loc_180055F1A
0x180055f00  cmp     byte ptr [rcx+19h], 6
0x180055f04  jb      short loc_180055F1A
0x180055f06  mov     rcx, [rcx+10h]
0x180055f0a  mov     edx, 2Dh ; '-'
0x180055f0f  mov     r9d, ebx
0x180055f12  mov     r8, r13
0x180055f15  call    WPP_SF_d
0x180055f1a  mov     eax, ebx
0x180055f1c  jmp     short loc_180055F9A
0x180055f1e  mov     [rsp+68h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180055f27  lea     rax, [rsp+68h+cbBytesReturned]
0x180055f2c  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180055f35  lea     r8, [rsp+68h+optval]; lpvInBuffer
0x180055f3a  mov     [rsp+68h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180055f3f  mov     r9d, 4; cbInBuffer
0x180055f45  mov     [rsp+68h+dwFlags], 0; cbOutBuffer
0x180055f4d  mov     edx, 98000007h; dwIoControlCode
0x180055f52  mov     rcx, rbp; s
0x180055f55  mov     qword ptr [rsp+68h+g], 0; lpvOutBuffer
0x180055f5e  mov     [rsp+68h+optval], ebx
0x180055f62  call    cs:__imp_WSAIoctl
0x180055f68  mov     [rsi+10h], rbp
0x180055f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f73  cmp     rcx, r12
0x180055f76  jz      short loc_180055F98
0x180055f78  test    byte ptr [rcx+1Ch], 8
0x180055f7c  jz      short loc_180055F98
0x180055f7e  cmp     byte ptr [rcx+19h], 6
0x180055f82  jb      short loc_180055F98
0x180055f84  mov     rcx, [rcx+10h]
0x180055f88  mov     edx, 2Ch ; ','
0x180055f8d  xor     r9d, r9d
0x180055f90  mov     r8, r13
0x180055f93  call    WPP_SF_d
0x180055f98  xor     eax, eax
0x180055f9a  lea     r11, [rsp+68h+var_18]
0x180055f9f  mov     rbx, [r11+30h]
0x180055fa3  mov     rbp, [r11+38h]
0x180055fa7  mov     rsp, r11
0x180055faa  pop     r13
0x180055fac  pop     r12
0x180055fae  pop     rsi
0x180055faf  retn
```
