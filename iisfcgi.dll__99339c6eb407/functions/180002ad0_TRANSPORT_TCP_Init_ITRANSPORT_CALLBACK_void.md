# TRANSPORT_TCP::Init(ITRANSPORT_CALLBACK *,void * *)

- ea: `0x180002ad0`
- end: `0x180002d3f`
- name: `?Init@TRANSPORT_TCP@@UEAAJPEAVITRANSPORT_CALLBACK@@PEAPEAX@Z`
- size: `623`
- prototype: `__int64 __fastcall(TRANSPORT_TCP *__hidden this, struct ITRANSPORT_CALLBACK *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cab`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b49`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002b49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002cc4`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180002c7f`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180002c7f`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180002c9c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180002c9c`
- `WS2_32!WSASocketW` at `0x180002b7b`
- `WS2_32!WSASocketW` at `0x180002bb0`
- `WS2_32!WSASocketW` at `0x180002b7b`
- `WS2_32!WSASocketW` at `0x180002bb0`
- `WS2_32!__imp_bind` at `0x180002c2b`
- `WS2_32!__imp_bind` at `0x180002c2b`
- `WS2_32!__imp_closesocket` at `0x180002cd3`
- `WS2_32!__imp_closesocket` at `0x180002ce2`
- `WS2_32!__imp_closesocket` at `0x180002cd3`
- `WS2_32!__imp_closesocket` at `0x180002ce2`
- `WS2_32!__imp_getsockname` at `0x180002c64`
- `WS2_32!__imp_getsockname` at `0x180002c64`
- `WS2_32!__imp_listen` at `0x180002c41`
- `WS2_32!__imp_listen` at `0x180002c41`
- `WS2_32!__imp_setsockopt` at `0x180002bdb`
- `WS2_32!__imp_setsockopt` at `0x180002c02`
- `WS2_32!__imp_setsockopt` at `0x180002bdb`
- `WS2_32!__imp_setsockopt` at `0x180002c02`
- `WS2_32!__imp_WSAGetLastError` at `0x180002b89`
- `WS2_32!__imp_WSAGetLastError` at `0x180002b89`

## pseudocode

```c
__int64 __fastcall TRANSPORT_TCP::Init(TRANSPORT_TCP *this, struct ITRANSPORT_CALLBACK *a2, SOCKET *a3)
{
  HANDLE EventW; // r12
  DWORD LastError; // ebx
  SOCKET v7; // rsi
  HANDLE v8; // r15
  SOCKET v9; // rdi
  DWORD Error; // eax
  char optval[4]; // [rsp+30h] [rbp-20h] BYREF
  int namelen; // [rsp+34h] [rbp-1Ch] BYREF
  sockaddr name; // [rsp+38h] [rbp-18h] BYREF

  namelen = 0;
  *a3 = -1;
  *((_QWORD *)this + 1) = a2;
  name = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    v7 = -1;
    v8 = CreateEventW(0, 1, 0, 0);
    if ( v8 )
    {
      v9 = WSASocketW(2, 1, 0, 0, 0, 0);
      if ( v9 == -1
        || (v7 = WSASocketW(2, 1, 0, 0, 0, 1u), v7 == -1)
        || (*(_DWORD *)optval = 1, setsockopt(v7, 6, 1, optval, 4) == -1)
        || (*(_DWORD *)optval = 1, setsockopt(v9, 6, 1, optval, 4) == -1)
        || (*(_DWORD *)&name.sa_family = 2, *(_DWORD *)&name.sa_data[2] = 16777343, bind(v9, &name, 16) == -1)
        || listen(v9, 1) == -1
        || (namelen = 16, getsockname(v9, (struct sockaddr *)this + 11, &namelen) == -1) )
      {
        Error = WSAGetLastError();
LABEL_16:
        LastError = Error;
        CloseHandle(EventW);
        if ( v8 )
          CloseHandle(v8);
        if ( v9 != -1 )
          closesocket(v9);
        if ( v7 != -1 )
          closesocket(v7);
        goto LABEL_22;
      }
      if ( SetHandleInformation((HANDLE)v9, 1u, 1u)
        && TRANSPORT::sm_hCompletionPort == CreateIoCompletionPort(
                                              (HANDLE)v7,
                                              TRANSPORT::sm_hCompletionPort,
                                              0xABCDDCBA,
                                              0) )
      {
        *((_QWORD *)this + 24) = EventW;
        LastError = 0;
        *((_QWORD *)this + 25) = v8;
        *((_QWORD *)this + 20) = v9;
        *((_QWORD *)this + 21) = v7;
        *a3 = v9;
        return LastError;
      }
    }
    else
    {
      v9 = -1;
    }
    Error = GetLastError();
    goto LABEL_16;
  }
  LastError = GetLastError();
LABEL_22:
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180002ad0  mov     [rsp-38h+arg_8], rbx
0x180002ad5  push    rbp
0x180002ad6  push    rsi
0x180002ad7  push    rdi
0x180002ad8  push    r12
0x180002ada  push    r13
0x180002adc  push    r14
0x180002ade  push    r15
0x180002ae0  mov     rbp, rsp
0x180002ae3  sub     rsp, 50h
0x180002ae7  mov     rax, cs:__security_cookie
0x180002aee  xor     rax, rsp
0x180002af1  mov     [rbp+var_8], rax
0x180002af5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002af9  mov     [rbp+namelen], 0
0x180002b00  mov     [r8], rbx
0x180002b03  mov     r13, r8
0x180002b06  mov     [rcx+8], rdx
0x180002b0a  mov     r14, rcx
0x180002b0d  xorps   xmm0, xmm0
0x180002b10  xor     r9d, r9d; lpName
0x180002b13  lea     edi, [rbx+2]
0x180002b16  xor     r8d, r8d; bInitialState
0x180002b19  mov     edx, edi; bManualReset
0x180002b1b  xor     ecx, ecx; lpEventAttributes
0x180002b1d  movups  xmmword ptr [rbp+name.sa_family], xmm0
0x180002b21  call    cs:__imp_CreateEventW
0x180002b27  mov     r12, rax
0x180002b2a  test    rax, rax
0x180002b2d  jnz     short loc_180002B3C
0x180002b2f  call    cs:__imp_GetLastError
0x180002b35  mov     ebx, eax
0x180002b37  jmp     loc_180002CE8
0x180002b3c  xor     r9d, r9d; lpName
0x180002b3f  xor     r8d, r8d; bInitialState
0x180002b42  mov     edx, edi; bManualReset
0x180002b44  xor     ecx, ecx; lpEventAttributes
0x180002b46  mov     rsi, rbx
0x180002b49  call    cs:__imp_CreateEventW
0x180002b4f  mov     r15, rax
0x180002b52  test    rax, rax
0x180002b55  jnz     short loc_180002B5F
0x180002b57  mov     rdi, rbx
0x180002b5a  jmp     loc_180002CAB
0x180002b5f  xor     r9d, r9d; lpProtocolInfo
0x180002b62  mov     [rsp+50h+dwFlags], 0; dwFlags
0x180002b6a  xor     r8d, r8d; protocol
0x180002b6d  mov     [rsp+50h+g], 0; g
0x180002b75  mov     edx, edi; type
0x180002b77  lea     ecx, [r9+2]; af
0x180002b7b  call    cs:__imp_WSASocketW
0x180002b81  mov     rdi, rax
0x180002b84  cmp     rax, rbx
0x180002b87  jnz     short loc_180002B94
0x180002b89  call    cs:__imp_WSAGetLastError
0x180002b8f  jmp     loc_180002CB1
0x180002b94  mov     eax, 1
0x180002b99  xor     r9d, r9d; lpProtocolInfo
0x180002b9c  mov     [rsp+50h+dwFlags], eax; dwFlags
0x180002ba0  xor     r8d, r8d; protocol
0x180002ba3  mov     edx, eax; type
0x180002ba5  mov     [rsp+50h+g], 0; g
0x180002bad  lea     ecx, [rax+1]; af
0x180002bb0  call    cs:__imp_WSASocketW
0x180002bb6  mov     rsi, rax
0x180002bb9  cmp     rax, rbx
0x180002bbc  jz      short loc_180002B89
0x180002bbe  mov     eax, 1
0x180002bc3  mov     [rsp+50h+g], 4; optlen
0x180002bcb  lea     r9, [rbp+optval]; optval
0x180002bcf  mov     dword ptr [rbp+optval], eax
0x180002bd2  mov     r8d, eax; optname
0x180002bd5  mov     rcx, rsi; s
0x180002bd8  lea     edx, [rax+5]; level
0x180002bdb  call    cs:__imp_setsockopt
0x180002be1  cmp     eax, ebx
0x180002be3  jz      short loc_180002B89
0x180002be5  mov     eax, 1
0x180002bea  mov     [rsp+50h+g], 4; optlen
0x180002bf2  lea     r9, [rbp+optval]; optval
0x180002bf6  mov     dword ptr [rbp+optval], eax
0x180002bf9  mov     r8d, eax; optname
0x180002bfc  mov     rcx, rdi; s
0x180002bff  lea     edx, [rax+5]; level
0x180002c02  call    cs:__imp_setsockopt
0x180002c08  cmp     eax, ebx
0x180002c0a  jz      loc_180002B89
0x180002c10  mov     r8d, 10h; namelen
0x180002c16  mov     dword ptr [rbp+name.sa_family], 2
0x180002c1d  lea     rdx, [rbp+name]; name
0x180002c21  mov     dword ptr [rbp+name.sa_data+2], 100007Fh
0x180002c28  mov     rcx, rdi; s
0x180002c2b  call    cs:__imp_bind
0x180002c31  cmp     eax, ebx
0x180002c33  jz      loc_180002B89
0x180002c39  mov     edx, 1; backlog
0x180002c3e  mov     rcx, rdi; s
0x180002c41  call    cs:__imp_listen
0x180002c47  cmp     eax, ebx
0x180002c49  jz      loc_180002B89
0x180002c4f  lea     rdx, [r14+0B0h]; name
0x180002c56  mov     [rbp+namelen], 10h
0x180002c5d  lea     r8, [rbp+namelen]; namelen
0x180002c61  mov     rcx, rdi; s
0x180002c64  call    cs:__imp_getsockname
0x180002c6a  cmp     eax, ebx
0x180002c6c  jz      loc_180002B89
0x180002c72  mov     eax, 1
0x180002c77  mov     rcx, rdi; hObject
0x180002c7a  mov     r8d, eax; dwFlags
0x180002c7d  mov     edx, eax; dwMask
0x180002c7f  call    cs:__imp_SetHandleInformation
0x180002c85  test    eax, eax
0x180002c87  jz      short loc_180002CAB
0x180002c89  mov     rdx, cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA; ExistingCompletionPort
0x180002c90  xor     r9d, r9d; NumberOfConcurrentThreads
0x180002c93  mov     r8d, 0ABCDDCBAh; CompletionKey
0x180002c99  mov     rcx, rsi; FileHandle
0x180002c9c  call    cs:__imp_CreateIoCompletionPort
0x180002ca2  cmp     cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA, rax; void * TRANSPORT::sm_hCompletionPort
0x180002ca9  jz      short loc_180002CF7
0x180002cab  call    cs:__imp_GetLastError
0x180002cb1  mov     rcx, r12; hObject
0x180002cb4  mov     ebx, eax
0x180002cb6  call    cs:__imp_CloseHandle
0x180002cbc  test    r15, r15
0x180002cbf  jz      short loc_180002CCA
0x180002cc1  mov     rcx, r15; hObject
0x180002cc4  call    cs:__imp_CloseHandle
0x180002cca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180002cce  jz      short loc_180002CD9
0x180002cd0  mov     rcx, rdi; s
0x180002cd3  call    cs:__imp_closesocket
0x180002cd9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180002cdd  jz      short loc_180002CE8
0x180002cdf  mov     rcx, rsi; s
0x180002ce2  call    cs:__imp_closesocket
0x180002ce8  test    ebx, ebx
0x180002cea  jle     short loc_180002D19
0x180002cec  movzx   ebx, bx
0x180002cef  or      ebx, 80070000h
0x180002cf5  jmp     short loc_180002D19
0x180002cf7  mov     [r14+0C0h], r12
0x180002cfe  xor     ebx, ebx
0x180002d00  mov     [r14+0C8h], r15
0x180002d07  mov     [r14+0A0h], rdi
0x180002d0e  mov     [r14+0A8h], rsi
0x180002d15  mov     [r13+0], rdi
0x180002d19  mov     eax, ebx
0x180002d1b  mov     rcx, [rbp+var_8]
0x180002d1f  xor     rcx, rsp; StackCookie
0x180002d22  call    __security_check_cookie
0x180002d27  mov     rbx, [rsp+50h+arg_8]
0x180002d2f  add     rsp, 50h
0x180002d33  pop     r15
0x180002d35  pop     r14
0x180002d37  pop     r13
0x180002d39  pop     r12
0x180002d3b  pop     rdi
0x180002d3c  pop     rsi
0x180002d3d  pop     rbp
0x180002d3e  retn
```
