# Dns64UdpTransportStart

- ea: `0x18006b954`
- end: `0x18006bad7`
- name: `Dns64UdpTransportStart`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180069b04`

## callees

- `0x1800355c4`
- `0x18004b630`
- `0x18006a9f0`
- `0x18006adf0`
- `0x18006b808`
- `0x18006b954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ba8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006ba8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006baa5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006baa5`
- `WS2_32!WSASocketW` at `0x18006b99f`
- `WS2_32!WSASocketW` at `0x18006b99f`
- `WS2_32!__imp_bind` at `0x18006ba3c`
- `WS2_32!__imp_bind` at `0x18006ba3c`
- `WS2_32!__imp_closesocket` at `0x18006b9cd`
- `WS2_32!__imp_closesocket` at `0x18006b9cd`
- `WS2_32!__imp_htons` at `0x18006ba1e`
- `WS2_32!__imp_htons` at `0x18006ba1e`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b9b5`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b9b5`

## pseudocode

```c
__int64 __fastcall Dns64UdpTransportStart(__int64 a1)
{
  SOCKET v2; // rax
  unsigned int WinsockPointers; // edi
  SOCKET v4; // rcx
  u_short v6; // ax
  SOCKET v7; // rcx
  HANDLE EventW; // rax
  struct sockaddr name; // [rsp+30h] [rbp-38h] BYREF

  memset(&name, 0, 28);
  v2 = WSASocketW(23, 2, 17, 0, 0, 1u);
  *(_QWORD *)(a1 + 8) = v2;
  if ( v2 == -1 )
    goto LABEL_2;
  WinsockPointers = Dns64UdpTransportGetWinsockPointers(a1);
  if ( WinsockPointers )
    goto LABEL_3;
  memset(&name, 0, 28);
  name.sa_family = 23;
  v6 = htons(0x35u);
  v7 = *(_QWORD *)(a1 + 8);
  *(_WORD *)name.sa_data = v6;
  if ( bind(v7, &name, 28) )
  {
LABEL_2:
    WinsockPointers = WSAGetLastError();
  }
  else
  {
    WinsockPointers = Dns64UdpTransportSetSocketOptions(a1);
    if ( !WinsockPointers )
    {
      if ( (unsigned int)TpclCreateIo(a1 + 16, *(_QWORD *)(a1 + 8), Dns64UdpTransportIoComplete) )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)(a1 + 32) = EventW;
        if ( EventW )
        {
          *(_DWORD *)(a1 + 24) = 2;
          *(_DWORD *)a1 = 1;
          Dns64UdpTransportRefillPostedRequests(a1, 0, 0);
          return 0;
        }
        CloseThreadpoolIo(*(PTP_IO *)(a1 + 16));
      }
      else
      {
        WinsockPointers = 31;
      }
    }
  }
LABEL_3:
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 != -1 )
    closesocket(v4);
  return WinsockPointers;
}

```

## disassembly

```asm
0x18006b954  mov     [rsp+arg_8], rbx
0x18006b959  mov     [rsp+arg_10], rsi
0x18006b95e  push    rdi
0x18006b95f  sub     rsp, 60h
0x18006b963  mov     rax, cs:__security_cookie
0x18006b96a  xor     rax, rsp
0x18006b96d  mov     [rsp+68h+var_18], rax
0x18006b972  xor     eax, eax
0x18006b974  mov     [rsp+68h+dwFlags], 1; dwFlags
0x18006b97c  xorps   xmm0, xmm0
0x18006b97f  mov     [rsp+68h+g], eax; g
0x18006b983  mov     rbx, rcx
0x18006b986  xor     r9d, r9d; lpProtocolInfo
0x18006b989  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006b98e  lea     esi, [rax+17h]
0x18006b991  mov     ecx, esi; af
0x18006b993  lea     edx, [rax+2]; type
0x18006b996  lea     r8d, [rax+11h]; protocol
0x18006b99a  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006b99f  call    cs:__imp_WSASocketW
0x18006b9a6  nop     dword ptr [rax+rax+00h]
0x18006b9ab  mov     [rbx+8], rax
0x18006b9af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b9b3  jnz     short loc_18006B9FB
0x18006b9b5  call    cs:__imp_WSAGetLastError
0x18006b9bc  nop     dword ptr [rax+rax+00h]
0x18006b9c1  mov     edi, eax
0x18006b9c3  mov     rcx, [rbx+8]; s
0x18006b9c7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b9cb  jz      short loc_18006B9D9
0x18006b9cd  call    cs:__imp_closesocket
0x18006b9d4  nop     dword ptr [rax+rax+00h]
0x18006b9d9  mov     eax, edi
0x18006b9db  mov     rcx, [rsp+68h+var_18]
0x18006b9e0  xor     rcx, rsp; StackCookie
0x18006b9e3  call    __security_check_cookie
0x18006b9e8  lea     r11, [rsp+68h+var_8]
0x18006b9ed  mov     rbx, [r11+18h]
0x18006b9f1  mov     rsi, [r11+20h]
0x18006b9f5  mov     rsp, r11
0x18006b9f8  pop     rdi
0x18006b9f9  retn
0x18006b9fb  mov     rcx, rbx
0x18006b9fe  call    Dns64UdpTransportGetWinsockPointers
0x18006ba03  mov     edi, eax
0x18006ba05  test    eax, eax
0x18006ba07  jnz     short loc_18006B9C3
0x18006ba09  xorps   xmm0, xmm0
0x18006ba0c  lea     ecx, [rax+35h]; hostshort
0x18006ba0f  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006ba14  mov     [rsp+68h+name.sa_family], si
0x18006ba19  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006ba1e  call    cs:__imp_htons
0x18006ba25  nop     dword ptr [rax+rax+00h]
0x18006ba2a  mov     rcx, [rbx+8]; s
0x18006ba2e  lea     r8d, [rdi+1Ch]; namelen
0x18006ba32  lea     rdx, [rsp+68h+name]; name
0x18006ba37  mov     word ptr [rsp+68h+name.sa_data], ax
0x18006ba3c  call    cs:__imp_bind
0x18006ba43  nop     dword ptr [rax+rax+00h]
0x18006ba48  test    eax, eax
0x18006ba4a  jnz     loc_18006B9B5
0x18006ba50  mov     rcx, rbx
0x18006ba53  call    Dns64UdpTransportSetSocketOptions
0x18006ba58  mov     edi, eax
0x18006ba5a  test    eax, eax
0x18006ba5c  jnz     loc_18006B9C3
0x18006ba62  mov     rdx, [rbx+8]
0x18006ba66  lea     r8, Dns64UdpTransportIoComplete
0x18006ba6d  lea     rcx, [rbx+10h]
0x18006ba71  call    TpclCreateIo
0x18006ba76  test    eax, eax
0x18006ba78  jnz     short loc_18006BA82
0x18006ba7a  lea     edi, [rax+1Fh]
0x18006ba7d  jmp     loc_18006B9C3
0x18006ba82  xor     r9d, r9d; lpName
0x18006ba85  xor     r8d, r8d; bInitialState
0x18006ba88  xor     edx, edx; bManualReset
0x18006ba8a  xor     ecx, ecx; lpEventAttributes
0x18006ba8c  call    cs:__imp_CreateEventW
0x18006ba93  nop     dword ptr [rax+rax+00h]
0x18006ba98  mov     [rbx+20h], rax
0x18006ba9c  test    rax, rax
0x18006ba9f  jnz     short loc_18006BAB6
0x18006baa1  mov     rcx, [rbx+10h]; pio
0x18006baa5  call    cs:__imp_CloseThreadpoolIo
0x18006baac  nop     dword ptr [rax+rax+00h]
0x18006bab1  jmp     loc_18006B9C3
0x18006bab6  xor     r8d, r8d
0x18006bab9  mov     dword ptr [rbx+18h], 2
0x18006bac0  xor     edx, edx
0x18006bac2  mov     dword ptr [rbx], 1
0x18006bac8  mov     rcx, rbx
0x18006bacb  call    Dns64UdpTransportRefillPostedRequests
0x18006bad0  xor     eax, eax
0x18006bad2  jmp     loc_18006B9DB
```
