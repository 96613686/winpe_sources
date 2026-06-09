# Dns_RegisterIpChangeNotification

- ea: `0x18002c6ac`
- end: `0x18002c96d`
- name: `Dns_RegisterIpChangeNotification`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002c120`

## callees

- `0x18002c6ac`
- `0x180046ec0`
- `0x18008373c`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c7f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c7f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18002c7e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18002c7e0`
- `WS2_32!WSASocketA` at `0x18002c728`
- `WS2_32!WSASocketA` at `0x18002c852`
- `WS2_32!WSASocketA` at `0x18002c728`
- `WS2_32!WSASocketA` at `0x18002c852`
- `WS2_32!WSAIoctl` at `0x18002c7a4`
- `WS2_32!WSAIoctl` at `0x18002c7a4`
- `WS2_32!__imp_closesocket` at `0x18002c70a`
- `WS2_32!__imp_closesocket` at `0x18002c70a`
- `WS2_32!__imp_setsockopt` at `0x18002c757`
- `WS2_32!__imp_setsockopt` at `0x18002c757`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c7ae`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c864`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c90c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c92c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c7ae`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c864`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c90c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002c92c`

## pseudocode

```c
__int64 __fastcall Dns_RegisterIpChangeNotification(__int64 a1, SOCKET *a2, __int64 *a3, struct _OVERLAPPED *a4)
{
  __int64 v7; // rsi
  SOCKET v8; // rax
  SOCKET v9; // rdi
  DWORD LastError; // ebx
  int v11; // r8d
  int v12; // eax
  HANDLE EventA; // rax
  unsigned int Error; // eax
  unsigned int v16; // eax
  char optval[4]; // [rsp+50h] [rbp-48h] BYREF
  DWORD cbBytesReturned; // [rsp+54h] [rbp-44h] BYREF

  cbBytesReturned = 0;
  if ( (xmmword_1800AB5A0 & 4) != 0 )
    WPP_SF_d(1026, 15, WPP_559bd3c959fb3bd1d0c1473e9bc21e61_Traceguids, 23);
  v7 = *a3;
  if ( !*a3 )
  {
    EventA = CreateEventA(0, 1, 0, 0);
    v7 = (__int64)EventA;
    if ( !EventA )
    {
      LastError = GetLastError();
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
        WPP_SF_(1055, 16, WPP_559bd3c959fb3bd1d0c1473e9bc21e61_Traceguids);
LABEL_17:
      if ( !LastError )
        return LastError;
      goto LABEL_26;
    }
    *a3 = (__int64)EventA;
  }
  if ( *a2 != -1 )
  {
    closesocket(*a2);
    *a2 = -1;
  }
  v8 = WSASocketA(23, 2, 0, 0, 0, 1u);
  v9 = v8;
  if ( v8 != -1 )
  {
    *(_DWORD *)optval = 0;
    if ( setsockopt(v8, 41, 27, optval, 4) && (xmmword_1800AB5A0 & 4) != 0 )
    {
      Error = WSAGetLastError();
      WPP_SF_d(1026, 17, WPP_559bd3c959fb3bd1d0c1473e9bc21e61_Traceguids, Error);
    }
    goto LABEL_8;
  }
  if ( (xmmword_1800AB5A0 & 4) != 0 )
  {
    v16 = WSAGetLastError();
    WPP_SF_d(1026, 18, WPP_559bd3c959fb3bd1d0c1473e9bc21e61_Traceguids, v16);
  }
  v9 = WSASocketA(2, 2, 0, 0, 0, 1u);
  if ( v9 == -1 )
  {
    LastError = WSAGetLastError();
    goto LABEL_17;
  }
LABEL_8:
  *a2 = v9;
  a4->Internal = 0;
  a4->InternalHigh = 0;
  LastError = 0;
  a4->Pointer = 0;
  a4->hEvent = (HANDLE)v7;
  if ( WSAIoctl(v9, 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, a4, 0) )
  {
    v12 = WSAGetLastError();
    LastError = v12;
    if ( v12 )
    {
      if ( v12 != 997 && v12 != 10035 )
      {
        if ( (SBYTE3(xmmword_1800AB5A0) & 0x80u) == 0 )
          return LastError;
        WPP_SF_dPq(1055, 20, v11, v12, v9, v7);
LABEL_26:
        if ( SBYTE3(xmmword_1800AB5A0) < 0 )
          WPP_SF_d(1055, 21, WPP_559bd3c959fb3bd1d0c1473e9bc21e61_Traceguids, LastError);
        return LastError;
      }
    }
  }
  if ( (xmmword_1800AB5A0 & 4) != 0 )
    WPP_SF_dPq(1026, 19, v11, LastError, v9, v7);
  return 0;
}

```

## disassembly

```asm
0x18002c6ac  push    rbx
0x18002c6ae  push    rbp
0x18002c6af  push    rsi
0x18002c6b0  push    rdi
0x18002c6b1  push    r12
0x18002c6b3  push    r14
0x18002c6b5  push    r15
0x18002c6b7  sub     rsp, 60h
0x18002c6bb  mov     rax, cs:__security_cookie
0x18002c6c2  xor     rax, rsp
0x18002c6c5  mov     [rsp+98h+var_40], rax
0x18002c6ca  xor     ebp, ebp
0x18002c6cc  mov     r15, r9
0x18002c6cf  mov     [rsp+98h+cbBytesReturned], ebp
0x18002c6d3  mov     rbx, r8
0x18002c6d6  mov     r14, rdx
0x18002c6d9  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18002c6e0  lea     r12, WPP_559bd3c959fb3bd1d0c1473e9bc21e61_Traceguids
0x18002c6e7  jnz     loc_18002C8C5
0x18002c6ed  mov     rsi, [rbx]
0x18002c6f0  mov     edi, 1
0x18002c6f5  test    rsi, rsi
0x18002c6f8  jz      loc_18002C7D6
0x18002c6fe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c702  cmp     [r14], rbx
0x18002c705  jz      short loc_18002C713
0x18002c707  mov     rcx, [r14]; s
0x18002c70a  call    cs:__imp_closesocket
0x18002c710  mov     [r14], rbx
0x18002c713  xor     r9d, r9d; lpProtocolInfo
0x18002c716  mov     [rsp+98h+dwFlags], edi; dwFlags
0x18002c71a  xor     r8d, r8d; protocol
0x18002c71d  mov     [rsp+98h+g], ebp; g
0x18002c721  lea     edx, [r9+2]; type
0x18002c725  lea     ecx, [rdx+15h]; af
0x18002c728  call    cs:__imp_WSASocketA
0x18002c72e  mov     rdi, rax
0x18002c731  cmp     rax, rbx
0x18002c734  jz      loc_18002C82D
0x18002c73a  mov     edx, 29h ; ')'; level
0x18002c73f  mov     dword ptr [rsp+98h+optval], ebp
0x18002c743  lea     r9, [rsp+98h+optval]; optval
0x18002c748  mov     [rsp+98h+g], 4; optlen
0x18002c750  mov     rcx, rax; s
0x18002c753  lea     r8d, [rdx-0Eh]; optname
0x18002c757  call    cs:__imp_setsockopt
0x18002c75d  test    eax, eax
0x18002c75f  jnz     loc_18002C8FF
0x18002c765  mov     [r14], rdi
0x18002c768  lea     rax, [rsp+98h+cbBytesReturned]
0x18002c76d  mov     [rsp+98h+lpCompletionRoutine], rbp; lpCompletionRoutine
0x18002c772  xor     r9d, r9d; cbInBuffer
0x18002c775  mov     [r15], rbp
0x18002c778  xor     r8d, r8d; lpvInBuffer
0x18002c77b  mov     [rsp+98h+lpOverlapped], r15; lpOverlapped
0x18002c780  mov     edx, 28000017h; dwIoControlCode
0x18002c785  mov     [r15+8], rbp
0x18002c789  mov     rcx, rdi; s
0x18002c78c  mov     [rsp+98h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18002c791  mov     ebx, ebp
0x18002c793  mov     [r15+10h], rbp
0x18002c797  mov     [rsp+98h+dwFlags], ebp; cbOutBuffer
0x18002c79b  mov     [r15+18h], rsi
0x18002c79f  mov     qword ptr [rsp+98h+g], rbp; lpvOutBuffer
0x18002c7a4  call    cs:__imp_WSAIoctl
0x18002c7aa  test    eax, eax
0x18002c7ac  jz      short loc_18002C7C5
0x18002c7ae  call    cs:__imp_WSAGetLastError
0x18002c7b4  mov     ebx, eax
0x18002c7b6  test    eax, eax
0x18002c7b8  jz      short loc_18002C7C5
0x18002c7ba  cmp     eax, 3E5h
0x18002c7bf  jnz     loc_18002C86E
0x18002c7c5  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18002c7cc  jnz     loc_18002C94C
0x18002c7d2  mov     ebx, ebp
0x18002c7d4  jmp     short loc_18002C80F
0x18002c7d6  xor     r9d, r9d; lpName
0x18002c7d9  xor     r8d, r8d; bInitialState
0x18002c7dc  mov     edx, edi; bManualReset
0x18002c7de  xor     ecx, ecx; lpEventAttributes
0x18002c7e0  call    cs:__imp_CreateEventA
0x18002c7e6  mov     rsi, rax
0x18002c7e9  test    rax, rax
0x18002c7ec  jnz     loc_18002C8F7
0x18002c7f2  call    cs:__imp_GetLastError
0x18002c7f8  mov     ebx, eax
0x18002c7fa  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x18002c801  jl      loc_18002C8E0
0x18002c807  test    ebx, ebx
0x18002c809  jnz     loc_18002C89E
0x18002c80f  mov     eax, ebx
0x18002c811  mov     rcx, [rsp+98h+var_40]
0x18002c816  xor     rcx, rsp; StackCookie
0x18002c819  call    __security_check_cookie
0x18002c81e  add     rsp, 60h
0x18002c822  pop     r15
0x18002c824  pop     r14
0x18002c826  pop     r12
0x18002c828  pop     rdi
0x18002c829  pop     rsi
0x18002c82a  pop     rbp
0x18002c82b  pop     rbx
0x18002c82c  retn
0x18002c82d  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18002c834  jnz     loc_18002C92C
0x18002c83a  xor     r9d, r9d; lpProtocolInfo
0x18002c83d  mov     [rsp+98h+dwFlags], 1; dwFlags
0x18002c845  xor     r8d, r8d; protocol
0x18002c848  mov     [rsp+98h+g], ebp; g
0x18002c84c  lea     ecx, [r9+2]; af
0x18002c850  mov     edx, ecx; type
0x18002c852  call    cs:__imp_WSASocketA
0x18002c858  mov     rdi, rax
0x18002c85b  cmp     rax, rbx
0x18002c85e  jnz     loc_18002C765
0x18002c864  call    cs:__imp_WSAGetLastError
0x18002c86a  mov     ebx, eax
0x18002c86c  jmp     short loc_18002C807
0x18002c86e  cmp     eax, 2733h
0x18002c873  jz      loc_18002C7C5
0x18002c879  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x18002c880  jge     short loc_18002C80F
0x18002c882  mov     edx, 14h
0x18002c887  mov     qword ptr [rsp+98h+dwFlags], rsi
0x18002c88c  mov     ecx, 41Fh
0x18002c891  mov     qword ptr [rsp+98h+g], rdi
0x18002c896  mov     r9d, eax
0x18002c899  call    WPP_SF_dPq
0x18002c89e  cmp     byte ptr cs:xmmword_1800AB5A0+3, bpl
0x18002c8a5  jge     loc_18002C80F
0x18002c8ab  mov     edx, 15h
0x18002c8b0  mov     ecx, 41Fh
0x18002c8b5  mov     r9d, ebx
0x18002c8b8  mov     r8, r12
0x18002c8bb  call    WPP_SF_d
0x18002c8c0  jmp     loc_18002C80F
0x18002c8c5  mov     edx, 0Fh
0x18002c8ca  mov     ecx, 402h
0x18002c8cf  mov     r8, r12
0x18002c8d2  lea     r9d, [rdx+8]
0x18002c8d6  call    WPP_SF_d
0x18002c8db  jmp     loc_18002C6ED
0x18002c8e0  mov     edx, 10h
0x18002c8e5  mov     ecx, 41Fh
0x18002c8ea  mov     r8, r12
0x18002c8ed  call    WPP_SF_
0x18002c8f2  jmp     loc_18002C807
0x18002c8f7  mov     [rbx], rax
0x18002c8fa  jmp     loc_18002C6FE
0x18002c8ff  test    byte ptr cs:xmmword_1800AB5A0, 4
0x18002c906  jz      loc_18002C765
0x18002c90c  call    cs:__imp_WSAGetLastError
0x18002c912  mov     edx, 11h
0x18002c917  mov     ecx, 402h
0x18002c91c  mov     r9d, eax
0x18002c91f  mov     r8, r12
0x18002c922  call    WPP_SF_d
0x18002c927  jmp     loc_18002C765
0x18002c92c  call    cs:__imp_WSAGetLastError
0x18002c932  mov     edx, 12h
0x18002c937  mov     ecx, 402h
0x18002c93c  mov     r9d, eax
0x18002c93f  mov     r8, r12
0x18002c942  call    WPP_SF_d
0x18002c947  jmp     loc_18002C83A
0x18002c94c  mov     edx, 13h
0x18002c951  mov     qword ptr [rsp+98h+dwFlags], rsi
0x18002c956  mov     ecx, 402h
0x18002c95b  mov     qword ptr [rsp+98h+g], rdi
0x18002c960  mov     r9d, ebx
0x18002c963  call    WPP_SF_dPq
0x18002c968  jmp     loc_18002C7D2
```
