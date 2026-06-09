# NhCreateDatagramSocket(sockaddr_storage *,_NH_RCSOCKET *)

- ea: `0x18002f120`
- end: `0x18002f5f3`
- name: `?NhCreateDatagramSocket@@YAKPEAUsockaddr_storage@@PEAU_NH_RCSOCKET@@@Z`
- size: `1235`
- prototype: `unsigned int __fastcall(LPSOCKADDR lpsaAddress, struct _NH_RCSOCKET *)`
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800271d0`
- `0x180028268`
- `0x18002e474`
- `0x18002e804`
- `0x18002eb94`
- `0x180047a30`
- `0x180083f08`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000fde0`
- `0x18002f120`
- `0x18003ea64`
- `0x1800417cc`
- `0x180051f30`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f190`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f446`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f587`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f587`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18002f1f3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18002f1f3`
- `WS2_32!WSASocketW` at `0x18002f1cd`
- `WS2_32!WSASocketW` at `0x18002f1cd`
- `WS2_32!WSAIoctl` at `0x18002f29e`
- `WS2_32!WSAIoctl` at `0x18002f29e`
- `WS2_32!WSAAddressToStringA` at `0x18002f309`
- `WS2_32!WSAAddressToStringA` at `0x18002f523`
- `WS2_32!WSAAddressToStringA` at `0x18002f309`
- `WS2_32!WSAAddressToStringA` at `0x18002f523`
- `WS2_32!__imp_bind` at `0x18002f2c0`
- `WS2_32!__imp_bind` at `0x18002f2c0`
- `WS2_32!__imp_closesocket` at `0x18002f568`
- `WS2_32!__imp_closesocket` at `0x18002f568`
- `WS2_32!__imp_setsockopt` at `0x18002f22a`
- `WS2_32!__imp_setsockopt` at `0x18002f259`
- `WS2_32!__imp_setsockopt` at `0x18002f22a`
- `WS2_32!__imp_setsockopt` at `0x18002f259`
- `WS2_32!__imp_WSAGetLastError` at `0x18002f416`
- `WS2_32!__imp_WSAGetLastError` at `0x18002f4b1`
- `WS2_32!__imp_WSAGetLastError` at `0x18002f416`
- `WS2_32!__imp_WSAGetLastError` at `0x18002f4b1`

## pseudocode

```c
__int64 __fastcall NhCreateDatagramSocket(LPSOCKADDR lpsaAddress, struct _NH_RCSOCKET *a2)
{
  HANDLE EventW; // rax
  void *v5; // rax
  void *v6; // rbx
  DWORD v8; // eax
  unsigned int v9; // ebp
  PVOID *v10; // rcx
  __int64 v11; // rdx
  DWORD LastError; // eax
  unsigned int Error; // eax
  char optval[4]; // [rsp+50h] [rbp-98h] BYREF
  DWORD dwAddressStringLength; // [rsp+54h] [rbp-94h] BYREF
  DWORD cbBytesReturned; // [rsp+58h] [rbp-90h] BYREF
  CHAR szAddressString[80]; // [rsp+60h] [rbp-88h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  *(_DWORD *)optval = 0;
  cbBytesReturned = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a2 + 1) = EventW;
  if ( EventW )
  {
    *(_DWORD *)a2 = 2;
    v5 = (void *)WSASocketW(lpsaAddress->sa_family, 2, 17, 0, 0, 1u);
    v6 = v5;
    if ( v5 != (void *)-1LL )
    {
      if ( BindIoCompletionCallback(v5, NhpIoCompletionRoutine, 0) )
      {
        *(_DWORD *)optval = 1;
        setsockopt((SOCKET)v6, 0xFFFF, 4, optval, 4);
        *(_DWORD *)optval = 1;
        setsockopt((SOCKET)v6, 0xFFFF, 32, optval, 4);
        *(_DWORD *)optval = 1;
        WSAIoctl((SOCKET)v6, 0x98000007, optval, 4u, 0, 0, &cbBytesReturned, 0, 0);
        if ( lpsaAddress->sa_family == 2 && *(_WORD *)lpsaAddress->sa_data == 13568 )
          SetSdOnDnsSocket(v6);
        if ( bind((SOCKET)v6, lpsaAddress, 128) != -1 )
        {
          dwAddressStringLength = 65;
          memset_0(szAddressString, 0, 0x41u);
          WSAAddressToStringA(lpsaAddress, 0x80u, 0, szAddressString, &dwAddressStringLength);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
              szAddressString);
          }
          *((_QWORD *)a2 + 2) = v6;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, 0);
          }
          return 0;
        }
        Error = WSAGetLastError();
        v9 = Error;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, Error);
        }
        dwAddressStringLength = 65;
        memset_0(szAddressString, 0, 0x41u);
        WSAAddressToStringA(lpsaAddress, 0x80u, 0, szAddressString, &dwAddressStringLength);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)&WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
            (unsigned int)szAddressString,
            v9);
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
        }
      }
      closesocket((SOCKET)v6);
      goto LABEL_47;
    }
    v8 = WSAGetLastError();
    v9 = v8;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v11 = 33;
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v11 = 32;
  }
  WPP_SF_d(v10[2], v11, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v8);
LABEL_47:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( *((_QWORD *)a2 + 1) )
  {
    _InterlockedDecrement((volatile signed __int32 *)a2);
    CloseHandle(*((HANDLE *)a2 + 1));
    *((_QWORD *)a2 + 1) = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 38, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002f120  push    rsi
0x18002f122  push    rdi
0x18002f123  push    r14
0x18002f125  push    r15
0x18002f127  sub     rsp, 0C8h
0x18002f12e  mov     rax, cs:__security_cookie
0x18002f135  xor     rax, rsp
0x18002f138  mov     [rsp+0E8h+var_38], rax
0x18002f140  mov     rdi, rdx
0x18002f143  mov     rsi, rcx
0x18002f146  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f14d  lea     r15, WPP_GLOBAL_Control
0x18002f154  cmp     rcx, r15
0x18002f157  jz      short loc_18002F169
0x18002f159  test    byte ptr [rcx+1Ch], 8
0x18002f15d  jz      short loc_18002F169
0x18002f15f  cmp     byte ptr [rcx+19h], 6
0x18002f163  jnb     loc_18002F3CC
0x18002f169  xor     r14d, r14d
0x18002f16c  mov     [rsp+0E8h+arg_10], rbx
0x18002f174  xor     r9d, r9d; lpName
0x18002f177  mov     dword ptr [rsp+0E8h+optval], r14d
0x18002f17c  xor     r8d, r8d; bInitialState
0x18002f17f  mov     [rsp+0E8h+cbBytesReturned], r14d
0x18002f184  xor     edx, edx; bManualReset
0x18002f186  mov     [rsp+0E8h+var_28], rbp
0x18002f18e  xor     ecx, ecx; lpEventAttributes
0x18002f190  call    cs:__imp_CreateEventW
0x18002f197  nop     dword ptr [rax+rax+00h]
0x18002f19c  mov     [rdi+8], rax
0x18002f1a0  test    rax, rax
0x18002f1a3  jz      loc_18002F398
0x18002f1a9  mov     dword ptr [rdi], 2
0x18002f1af  xor     r9d, r9d; lpProtocolInfo
0x18002f1b2  movzx   ecx, word ptr [rsi]; af
0x18002f1b5  mov     edx, 2; type
0x18002f1ba  mov     [rsp+0E8h+dwFlags], 1; dwFlags
0x18002f1c2  mov     r8d, 11h; protocol
0x18002f1c8  mov     [rsp+0E8h+g], r14d; g
0x18002f1cd  call    cs:__imp_WSASocketW
0x18002f1d4  nop     dword ptr [rax+rax+00h]
0x18002f1d9  mov     rbx, rax
0x18002f1dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002f1e0  jz      loc_18002F416
0x18002f1e6  xor     r8d, r8d; Flags
0x18002f1e9  lea     rdx, ?NhpIoCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x18002f1f0  mov     rcx, rax; FileHandle
0x18002f1f3  call    cs:__imp_BindIoCompletionCallback
0x18002f1fa  nop     dword ptr [rax+rax+00h]
0x18002f1ff  test    eax, eax
0x18002f201  jz      loc_18002F446
0x18002f207  lea     r9, [rsp+0E8h+optval]; optval
0x18002f20c  mov     dword ptr [rsp+0E8h+optval], 1
0x18002f214  mov     edx, 0FFFFh; level
0x18002f219  mov     [rsp+0E8h+g], 4; optlen
0x18002f221  mov     r8d, 4; optname
0x18002f227  mov     rcx, rbx; s
0x18002f22a  call    cs:__imp_setsockopt
0x18002f231  nop     dword ptr [rax+rax+00h]
0x18002f236  lea     r9, [rsp+0E8h+optval]; optval
0x18002f23b  mov     dword ptr [rsp+0E8h+optval], 1
0x18002f243  mov     edx, 0FFFFh; level
0x18002f248  mov     [rsp+0E8h+g], 4; optlen
0x18002f250  mov     r8d, 20h ; ' '; optname
0x18002f256  mov     rcx, rbx; s
0x18002f259  call    cs:__imp_setsockopt
0x18002f260  nop     dword ptr [rax+rax+00h]
0x18002f265  mov     [rsp+0E8h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002f26a  lea     rax, [rsp+0E8h+cbBytesReturned]
0x18002f26f  mov     [rsp+0E8h+lpOverlapped], r14; lpOverlapped
0x18002f274  lea     r8, [rsp+0E8h+optval]; lpvInBuffer
0x18002f279  mov     [rsp+0E8h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18002f27e  mov     r9d, 4; cbInBuffer
0x18002f284  mov     [rsp+0E8h+dwFlags], r14d; cbOutBuffer
0x18002f289  mov     edx, 98000007h; dwIoControlCode
0x18002f28e  mov     rcx, rbx; s
0x18002f291  mov     qword ptr [rsp+0E8h+g], r14; lpvOutBuffer
0x18002f296  mov     dword ptr [rsp+0E8h+optval], 1
0x18002f29e  call    cs:__imp_WSAIoctl
0x18002f2a5  nop     dword ptr [rax+rax+00h]
0x18002f2aa  cmp     word ptr [rsi], 2
0x18002f2ae  jz      loc_18002F495
0x18002f2b4  mov     r8d, 80h; namelen
0x18002f2ba  mov     rdx, rsi; name
0x18002f2bd  mov     rcx, rbx; s
0x18002f2c0  call    cs:__imp_bind
0x18002f2c7  nop     dword ptr [rax+rax+00h]
0x18002f2cc  cmp     eax, 0FFFFFFFFh
0x18002f2cf  jz      loc_18002F4B1
0x18002f2d5  xor     edx, edx; Val
0x18002f2d7  mov     [rsp+0E8h+dwAddressStringLength], 41h ; 'A'
0x18002f2df  mov     r8d, 41h ; 'A'; Size
0x18002f2e5  lea     rcx, [rsp+0E8h+szAddressString]; void *
0x18002f2ea  call    memset_0
0x18002f2ef  lea     rax, [rsp+0E8h+dwAddressStringLength]
0x18002f2f4  xor     r8d, r8d; lpProtocolInfo
0x18002f2f7  lea     r9, [rsp+0E8h+szAddressString]; lpszAddressString
0x18002f2fc  mov     qword ptr [rsp+0E8h+g], rax; lpdwAddressStringLength
0x18002f301  mov     edx, 80h; dwAddressLength
0x18002f306  mov     rcx, rsi; lpsaAddress
0x18002f309  call    cs:__imp_WSAAddressToStringA
0x18002f310  nop     dword ptr [rax+rax+00h]
0x18002f315  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f31c  cmp     rcx, r15
0x18002f31f  jz      short loc_18002F331
0x18002f321  test    byte ptr [rcx+1Ch], 8
0x18002f325  jz      short loc_18002F331
0x18002f327  cmp     byte ptr [rcx+19h], 5
0x18002f32b  jnb     loc_18002F5D4
0x18002f331  mov     [rdi+10h], rbx
0x18002f335  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f33c  cmp     rcx, r15
0x18002f33f  jnz     short loc_18002F372
0x18002f341  xor     eax, eax
0x18002f343  mov     rbp, [rsp+0E8h+var_28]
0x18002f34b  mov     rbx, [rsp+0E8h+arg_10]
0x18002f353  mov     rcx, [rsp+0E8h+var_38]
0x18002f35b  xor     rcx, rsp; StackCookie
0x18002f35e  call    __security_check_cookie
0x18002f363  add     rsp, 0C8h
0x18002f36a  pop     r15
0x18002f36c  pop     r14
0x18002f36e  pop     rdi
0x18002f36f  pop     rsi
0x18002f370  retn
0x18002f372  test    byte ptr [rcx+1Ch], 8
0x18002f376  jz      short loc_18002F341
0x18002f378  cmp     byte ptr [rcx+19h], 6
0x18002f37c  jb      short loc_18002F341
0x18002f37e  mov     rcx, [rcx+10h]
0x18002f382  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f389  mov     edx, 25h ; '%'
0x18002f38e  xor     r9d, r9d
0x18002f391  call    WPP_SF_d
0x18002f396  jmp     short loc_18002F341
0x18002f398  call    cs:__imp_GetLastError
0x18002f39f  nop     dword ptr [rax+rax+00h]
0x18002f3a4  mov     ebp, eax
0x18002f3a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3ad  cmp     rcx, r15
0x18002f3b0  jnz     short loc_18002F3E6
0x18002f3b2  cmp     [rdi+8], r14
0x18002f3b6  jnz     loc_18002F580
0x18002f3bc  cmp     rcx, r15
0x18002f3bf  jnz     loc_18002F5A3
0x18002f3c5  mov     eax, ebp
0x18002f3c7  jmp     loc_18002F343
0x18002f3cc  mov     rcx, [rcx+10h]
0x18002f3d0  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f3d7  mov     edx, 1Fh
0x18002f3dc  call    WPP_SF_
0x18002f3e1  jmp     loc_18002F169
0x18002f3e6  test    byte ptr [rcx+1Ch], 8
0x18002f3ea  jz      short loc_18002F3B2
0x18002f3ec  cmp     byte ptr [rcx+19h], 2
0x18002f3f0  jb      short loc_18002F3B2
0x18002f3f2  mov     edx, 20h ; ' '
0x18002f3f7  jmp     short loc_18002F3FE
0x18002f3f9  mov     edx, 21h ; '!'
0x18002f3fe  mov     rcx, [rcx+10h]
0x18002f402  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f409  mov     r9d, eax
0x18002f40c  call    WPP_SF_d
0x18002f411  jmp     loc_18002F574
0x18002f416  call    cs:__imp_WSAGetLastError
0x18002f41d  nop     dword ptr [rax+rax+00h]
0x18002f422  mov     ebp, eax
0x18002f424  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f42b  cmp     rcx, r15
0x18002f42e  jz      short loc_18002F3B2
0x18002f430  test    byte ptr [rcx+1Ch], 8
0x18002f434  jz      loc_18002F3B2
0x18002f43a  cmp     byte ptr [rcx+19h], 2
0x18002f43e  jb      loc_18002F3B2
0x18002f444  jmp     short loc_18002F3F9
0x18002f446  call    cs:__imp_GetLastError
0x18002f44d  nop     dword ptr [rax+rax+00h]
0x18002f452  mov     ebp, eax
0x18002f454  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f45b  cmp     rcx, r15
0x18002f45e  jz      loc_18002F565
0x18002f464  test    byte ptr [rcx+1Ch], 8
0x18002f468  jz      loc_18002F565
0x18002f46e  cmp     byte ptr [rcx+19h], 2
0x18002f472  jb      loc_18002F565
0x18002f478  mov     rcx, [rcx+10h]
0x18002f47c  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f483  mov     edx, 22h ; '"'
0x18002f488  mov     r9d, eax
0x18002f48b  call    WPP_SF_d
0x18002f490  jmp     loc_18002F565
0x18002f495  mov     eax, 3500h
0x18002f49a  cmp     [rsi+2], ax
0x18002f49e  jnz     loc_18002F2B4
0x18002f4a4  mov     rcx, rbx; Handle
0x18002f4a7  call    ?SetSdOnDnsSocket@@YAK_K@Z; SetSdOnDnsSocket(unsigned __int64)
0x18002f4ac  jmp     loc_18002F2B4
0x18002f4b1  call    cs:__imp_WSAGetLastError
0x18002f4b8  nop     dword ptr [rax+rax+00h]
0x18002f4bd  mov     ebp, eax
0x18002f4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4c6  cmp     rcx, r15
0x18002f4c9  jz      short loc_18002F4EF
0x18002f4cb  test    byte ptr [rcx+1Ch], 8
0x18002f4cf  jz      short loc_18002F4EF
0x18002f4d1  cmp     byte ptr [rcx+19h], 2
0x18002f4d5  jb      short loc_18002F4EF
0x18002f4d7  mov     rcx, [rcx+10h]
0x18002f4db  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f4e2  mov     edx, 23h ; '#'
0x18002f4e7  mov     r9d, eax
0x18002f4ea  call    WPP_SF_d
0x18002f4ef  xor     edx, edx; Val
0x18002f4f1  mov     [rsp+0E8h+dwAddressStringLength], 41h ; 'A'
0x18002f4f9  mov     r8d, 41h ; 'A'; Size
0x18002f4ff  lea     rcx, [rsp+0E8h+szAddressString]; void *
0x18002f504  call    memset_0
0x18002f509  lea     rax, [rsp+0E8h+dwAddressStringLength]
0x18002f50e  xor     r8d, r8d; lpProtocolInfo
0x18002f511  lea     r9, [rsp+0E8h+szAddressString]; lpszAddressString
0x18002f516  mov     qword ptr [rsp+0E8h+g], rax; lpdwAddressStringLength
0x18002f51b  mov     edx, 80h; dwAddressLength
0x18002f520  mov     rcx, rsi; lpsaAddress
0x18002f523  call    cs:__imp_WSAAddressToStringA
0x18002f52a  nop     dword ptr [rax+rax+00h]
0x18002f52f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f536  cmp     rcx, r15
0x18002f539  jz      short loc_18002F565
0x18002f53b  test    byte ptr [rcx+1Ch], 8
0x18002f53f  jz      short loc_18002F565
0x18002f541  cmp     byte ptr [rcx+19h], 2
0x18002f545  jb      short loc_18002F565
0x18002f547  mov     rcx, [rcx+10h]
0x18002f54b  lea     r9, [rsp+0E8h+szAddressString]
0x18002f550  mov     edx, 24h ; '$'
0x18002f555  mov     [rsp+0E8h+g], ebp
0x18002f559  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f560  call    WPP_SF_sD
0x18002f565  mov     rcx, rbx; s
0x18002f568  call    cs:__imp_closesocket
0x18002f56f  nop     dword ptr [rax+rax+00h]
0x18002f574  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f57b  jmp     loc_18002F3B2
0x18002f580  lock dec dword ptr [rdi]
0x18002f583  mov     rcx, [rdi+8]; hObject
0x18002f587  call    cs:__imp_CloseHandle
0x18002f58e  nop     dword ptr [rax+rax+00h]
0x18002f593  mov     [rdi+8], r14
0x18002f597  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f59e  jmp     loc_18002F3BC
0x18002f5a3  test    byte ptr [rcx+1Ch], 8
0x18002f5a7  jz      loc_18002F3C5
0x18002f5ad  cmp     byte ptr [rcx+19h], 6
0x18002f5b1  jb      loc_18002F3C5
0x18002f5b7  mov     rcx, [rcx+10h]
0x18002f5bb  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f5c2  mov     edx, 26h ; '&'
0x18002f5c7  mov     r9d, ebp
0x18002f5ca  call    WPP_SF_d
0x18002f5cf  jmp     loc_18002F3C5
0x18002f5d4  mov     rcx, [rcx+10h]
0x18002f5d8  lea     r9, [rsp+0E8h+szAddressString]
0x18002f5dd  mov     edx, 85h
0x18002f5e2  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002f5e9  call    WPP_SF_s
0x18002f5ee  jmp     loc_18002F331
```
