# NhCreateRawDatagramSocket(_NH_RCSOCKET *)

- ea: `0x18005a018`
- end: `0x18005a309`
- name: `?NhCreateRawDatagramSocket@@YAKPEAU_NH_RCSOCKET@@@Z`
- size: `753`
- prototype: `__int64 __fastcall(struct _NH_RCSOCKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180083f08`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18005a018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a07f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a16f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a229`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18005a15f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18005a15f`
- `WS2_32!WSASocketW` at `0x18005a103`
- `WS2_32!WSASocketW` at `0x18005a103`
- `WS2_32!WSAIoctl` at `0x18005a2b4`
- `WS2_32!WSAIoctl` at `0x18005a2b4`
- `WS2_32!__imp_closesocket` at `0x18005a208`
- `WS2_32!__imp_closesocket` at `0x18005a208`
- `WS2_32!__imp_setsockopt` at `0x18005a1b6`
- `WS2_32!__imp_setsockopt` at `0x18005a1b6`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a118`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a1cb`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a118`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a1cb`

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
0x18005a018  mov     [rsp+arg_10], rbx
0x18005a01d  mov     [rsp+arg_18], rbp
0x18005a022  push    rsi
0x18005a023  push    r12
0x18005a025  push    r13
0x18005a027  sub     rsp, 50h
0x18005a02b  mov     rsi, rcx
0x18005a02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a035  lea     r12, WPP_GLOBAL_Control
0x18005a03c  lea     r13, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005a043  cmp     rcx, r12
0x18005a046  jz      short loc_18005A065
0x18005a048  test    byte ptr [rcx+1Ch], 8
0x18005a04c  jz      short loc_18005A065
0x18005a04e  cmp     byte ptr [rcx+19h], 6
0x18005a052  jb      short loc_18005A065
0x18005a054  mov     rcx, [rcx+10h]
0x18005a058  mov     edx, 27h ; '''
0x18005a05d  mov     r8, r13
0x18005a060  call    WPP_SF_
0x18005a065  xor     r9d, r9d; lpName
0x18005a068  mov     [rsp+68h+optval], 0
0x18005a070  xor     r8d, r8d; bInitialState
0x18005a073  mov     [rsp+68h+cbBytesReturned], 0
0x18005a07b  xor     edx, edx; bManualReset
0x18005a07d  xor     ecx, ecx; lpEventAttributes
0x18005a07f  call    cs:__imp_CreateEventW
0x18005a086  nop     dword ptr [rax+rax+00h]
0x18005a08b  mov     [rsi+8], rax
0x18005a08f  test    rax, rax
0x18005a092  jnz     short loc_18005A0DF
0x18005a094  call    cs:__imp_GetLastError
0x18005a09b  nop     dword ptr [rax+rax+00h]
0x18005a0a0  mov     ebx, eax
0x18005a0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0a9  cmp     rcx, r12
0x18005a0ac  jz      loc_18005A21B
0x18005a0b2  test    byte ptr [rcx+1Ch], 8
0x18005a0b6  jz      loc_18005A21B
0x18005a0bc  cmp     byte ptr [rcx+19h], 2
0x18005a0c0  jb      loc_18005A21B
0x18005a0c6  mov     edx, 28h ; '('
0x18005a0cb  mov     rcx, [rcx+10h]
0x18005a0cf  mov     r9d, eax
0x18005a0d2  mov     r8, r13
0x18005a0d5  call    WPP_SF_d
0x18005a0da  jmp     loc_18005A214
0x18005a0df  mov     ebx, 1
0x18005a0e4  mov     dword ptr [rsi], 2
0x18005a0ea  mov     [rsp+68h+dwFlags], ebx; dwFlags
0x18005a0ee  xor     r9d, r9d; lpProtocolInfo
0x18005a0f1  mov     [rsp+68h+g], 0; g
0x18005a0f9  lea     edx, [rbx+2]; type
0x18005a0fc  lea     ecx, [rbx+1]; af
0x18005a0ff  lea     r8d, [rbx+10h]; protocol
0x18005a103  call    cs:__imp_WSASocketW
0x18005a10a  nop     dword ptr [rax+rax+00h]
0x18005a10f  mov     rbp, rax
0x18005a112  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005a116  jnz     short loc_18005A152
0x18005a118  call    cs:__imp_WSAGetLastError
0x18005a11f  nop     dword ptr [rax+rax+00h]
0x18005a124  mov     ebx, eax
0x18005a126  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a12d  cmp     rcx, r12
0x18005a130  jz      loc_18005A21B
0x18005a136  test    byte ptr [rcx+1Ch], 8
0x18005a13a  jz      loc_18005A21B
0x18005a140  cmp     byte ptr [rcx+19h], 2
0x18005a144  jb      loc_18005A21B
0x18005a14a  lea     edx, [rbp+2Ah]
0x18005a14d  jmp     loc_18005A0CB
0x18005a152  xor     r8d, r8d; Flags
0x18005a155  lea     rdx, ?NhpIoCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x18005a15c  mov     rcx, rbp; FileHandle
0x18005a15f  call    cs:__imp_BindIoCompletionCallback
0x18005a166  nop     dword ptr [rax+rax+00h]
0x18005a16b  test    eax, eax
0x18005a16d  jnz     short loc_18005A19C
0x18005a16f  call    cs:__imp_GetLastError
0x18005a176  nop     dword ptr [rax+rax+00h]
0x18005a17b  mov     ebx, eax
0x18005a17d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a184  cmp     rcx, r12
0x18005a187  jz      short loc_18005A205
0x18005a189  test    byte ptr [rcx+1Ch], 8
0x18005a18d  jz      short loc_18005A205
0x18005a18f  cmp     byte ptr [rcx+19h], 2
0x18005a193  jb      short loc_18005A205
0x18005a195  mov     edx, 2Ah ; '*'
0x18005a19a  jmp     short loc_18005A1F6
0x18005a19c  xor     edx, edx; level
0x18005a19e  mov     [rsp+68h+optval], ebx
0x18005a1a2  lea     r9, [rsp+68h+optval]; optval
0x18005a1a7  mov     [rsp+68h+g], 4; optlen
0x18005a1af  mov     rcx, rbp; s
0x18005a1b2  lea     r8d, [rdx+2]; optname
0x18005a1b6  call    cs:__imp_setsockopt
0x18005a1bd  nop     dword ptr [rax+rax+00h]
0x18005a1c2  cmp     eax, 0FFFFFFFFh
0x18005a1c5  jnz     loc_18005A270
0x18005a1cb  call    cs:__imp_WSAGetLastError
0x18005a1d2  nop     dword ptr [rax+rax+00h]
0x18005a1d7  mov     ebx, eax
0x18005a1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a1e0  cmp     rcx, r12
0x18005a1e3  jz      short loc_18005A205
0x18005a1e5  test    byte ptr [rcx+1Ch], 8
0x18005a1e9  jz      short loc_18005A205
0x18005a1eb  cmp     byte ptr [rcx+19h], 2
0x18005a1ef  jb      short loc_18005A205
0x18005a1f1  mov     edx, 2Bh ; '+'
0x18005a1f6  mov     rcx, [rcx+10h]
0x18005a1fa  mov     r9d, eax
0x18005a1fd  mov     r8, r13
0x18005a200  call    WPP_SF_d
0x18005a205  mov     rcx, rbp; s
0x18005a208  call    cs:__imp_closesocket
0x18005a20f  nop     dword ptr [rax+rax+00h]
0x18005a214  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a21b  cmp     qword ptr [rsi+8], 0
0x18005a220  jz      short loc_18005A244
0x18005a222  lock dec dword ptr [rsi]
0x18005a225  mov     rcx, [rsi+8]; hObject
0x18005a229  call    cs:__imp_CloseHandle
0x18005a230  nop     dword ptr [rax+rax+00h]
0x18005a235  mov     qword ptr [rsi+8], 0
0x18005a23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a244  cmp     rcx, r12
0x18005a247  jz      short loc_18005A269
0x18005a249  test    byte ptr [rcx+1Ch], 8
0x18005a24d  jz      short loc_18005A269
0x18005a24f  cmp     byte ptr [rcx+19h], 6
0x18005a253  jb      short loc_18005A269
0x18005a255  mov     rcx, [rcx+10h]
0x18005a259  mov     edx, 2Dh ; '-'
0x18005a25e  mov     r9d, ebx
0x18005a261  mov     r8, r13
0x18005a264  call    WPP_SF_d
0x18005a269  mov     eax, ebx
0x18005a26b  jmp     loc_18005A2F2
0x18005a270  mov     [rsp+68h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18005a279  lea     rax, [rsp+68h+cbBytesReturned]
0x18005a27e  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18005a287  lea     r8, [rsp+68h+optval]; lpvInBuffer
0x18005a28c  mov     [rsp+68h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18005a291  mov     r9d, 4; cbInBuffer
0x18005a297  mov     [rsp+68h+dwFlags], 0; cbOutBuffer
0x18005a29f  mov     edx, 98000007h; dwIoControlCode
0x18005a2a4  mov     rcx, rbp; s
0x18005a2a7  mov     qword ptr [rsp+68h+g], 0; lpvOutBuffer
0x18005a2b0  mov     [rsp+68h+optval], ebx
0x18005a2b4  call    cs:__imp_WSAIoctl
0x18005a2bb  nop     dword ptr [rax+rax+00h]
0x18005a2c0  mov     [rsi+10h], rbp
0x18005a2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2cb  cmp     rcx, r12
0x18005a2ce  jz      short loc_18005A2F0
0x18005a2d0  test    byte ptr [rcx+1Ch], 8
0x18005a2d4  jz      short loc_18005A2F0
0x18005a2d6  cmp     byte ptr [rcx+19h], 6
0x18005a2da  jb      short loc_18005A2F0
0x18005a2dc  mov     rcx, [rcx+10h]
0x18005a2e0  mov     edx, 2Ch ; ','
0x18005a2e5  xor     r9d, r9d
0x18005a2e8  mov     r8, r13
0x18005a2eb  call    WPP_SF_d
0x18005a2f0  xor     eax, eax
0x18005a2f2  lea     r11, [rsp+68h+var_18]
0x18005a2f7  mov     rbx, [r11+30h]
0x18005a2fb  mov     rbp, [r11+38h]
0x18005a2ff  mov     rsp, r11
0x18005a302  pop     r13
0x18005a304  pop     r12
0x18005a306  pop     rsi
0x18005a307  retn
```
