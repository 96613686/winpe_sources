# Dns64UdpTransportStart

- ea: `0x18006b974`
- end: `0x18006baf7`
- name: `Dns64UdpTransportStart`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180069b24`

## callees

- `0x1800355d4`
- `0x18004b5f0`
- `0x18006aa10`
- `0x18006ae10`
- `0x18006b828`
- `0x18006b974`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006baac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006baac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006bac5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006bac5`
- `WS2_32!WSASocketW` at `0x18006b9bf`
- `WS2_32!WSASocketW` at `0x18006b9bf`
- `WS2_32!__imp_bind` at `0x18006ba5c`
- `WS2_32!__imp_bind` at `0x18006ba5c`
- `WS2_32!__imp_closesocket` at `0x18006b9ed`
- `WS2_32!__imp_closesocket` at `0x18006b9ed`
- `WS2_32!__imp_htons` at `0x18006ba3e`
- `WS2_32!__imp_htons` at `0x18006ba3e`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b9d5`
- `WS2_32!__imp_WSAGetLastError` at `0x18006b9d5`

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
0x18006b974  mov     [rsp+arg_8], rbx
0x18006b979  mov     [rsp+arg_10], rsi
0x18006b97e  push    rdi
0x18006b97f  sub     rsp, 60h
0x18006b983  mov     rax, cs:__security_cookie
0x18006b98a  xor     rax, rsp
0x18006b98d  mov     [rsp+68h+var_18], rax
0x18006b992  xor     eax, eax
0x18006b994  mov     [rsp+68h+dwFlags], 1; dwFlags
0x18006b99c  xorps   xmm0, xmm0
0x18006b99f  mov     [rsp+68h+g], eax; g
0x18006b9a3  mov     rbx, rcx
0x18006b9a6  xor     r9d, r9d; lpProtocolInfo
0x18006b9a9  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006b9ae  lea     esi, [rax+17h]
0x18006b9b1  mov     ecx, esi; af
0x18006b9b3  lea     edx, [rax+2]; type
0x18006b9b6  lea     r8d, [rax+11h]; protocol
0x18006b9ba  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006b9bf  call    cs:__imp_WSASocketW
0x18006b9c6  nop     dword ptr [rax+rax+00h]
0x18006b9cb  mov     [rbx+8], rax
0x18006b9cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b9d3  jnz     short loc_18006BA1B
0x18006b9d5  call    cs:__imp_WSAGetLastError
0x18006b9dc  nop     dword ptr [rax+rax+00h]
0x18006b9e1  mov     edi, eax
0x18006b9e3  mov     rcx, [rbx+8]; s
0x18006b9e7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006b9eb  jz      short loc_18006B9F9
0x18006b9ed  call    cs:__imp_closesocket
0x18006b9f4  nop     dword ptr [rax+rax+00h]
0x18006b9f9  mov     eax, edi
0x18006b9fb  mov     rcx, [rsp+68h+var_18]
0x18006ba00  xor     rcx, rsp; StackCookie
0x18006ba03  call    __security_check_cookie
0x18006ba08  lea     r11, [rsp+68h+var_8]
0x18006ba0d  mov     rbx, [r11+18h]
0x18006ba11  mov     rsi, [r11+20h]
0x18006ba15  mov     rsp, r11
0x18006ba18  pop     rdi
0x18006ba19  retn
0x18006ba1b  mov     rcx, rbx
0x18006ba1e  call    Dns64UdpTransportGetWinsockPointers
0x18006ba23  mov     edi, eax
0x18006ba25  test    eax, eax
0x18006ba27  jnz     short loc_18006B9E3
0x18006ba29  xorps   xmm0, xmm0
0x18006ba2c  lea     ecx, [rax+35h]; hostshort
0x18006ba2f  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006ba34  mov     [rsp+68h+name.sa_family], si
0x18006ba39  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006ba3e  call    cs:__imp_htons
0x18006ba45  nop     dword ptr [rax+rax+00h]
0x18006ba4a  mov     rcx, [rbx+8]; s
0x18006ba4e  lea     r8d, [rdi+1Ch]; namelen
0x18006ba52  lea     rdx, [rsp+68h+name]; name
0x18006ba57  mov     word ptr [rsp+68h+name.sa_data], ax
0x18006ba5c  call    cs:__imp_bind
0x18006ba63  nop     dword ptr [rax+rax+00h]
0x18006ba68  test    eax, eax
0x18006ba6a  jnz     loc_18006B9D5
0x18006ba70  mov     rcx, rbx
0x18006ba73  call    Dns64UdpTransportSetSocketOptions
0x18006ba78  mov     edi, eax
0x18006ba7a  test    eax, eax
0x18006ba7c  jnz     loc_18006B9E3
0x18006ba82  mov     rdx, [rbx+8]
0x18006ba86  lea     r8, Dns64UdpTransportIoComplete
0x18006ba8d  lea     rcx, [rbx+10h]
0x18006ba91  call    TpclCreateIo
0x18006ba96  test    eax, eax
0x18006ba98  jnz     short loc_18006BAA2
0x18006ba9a  lea     edi, [rax+1Fh]
0x18006ba9d  jmp     loc_18006B9E3
0x18006baa2  xor     r9d, r9d; lpName
0x18006baa5  xor     r8d, r8d; bInitialState
0x18006baa8  xor     edx, edx; bManualReset
0x18006baaa  xor     ecx, ecx; lpEventAttributes
0x18006baac  call    cs:__imp_CreateEventW
0x18006bab3  nop     dword ptr [rax+rax+00h]
0x18006bab8  mov     [rbx+20h], rax
0x18006babc  test    rax, rax
0x18006babf  jnz     short loc_18006BAD6
0x18006bac1  mov     rcx, [rbx+10h]; pio
0x18006bac5  call    cs:__imp_CloseThreadpoolIo
0x18006bacc  nop     dword ptr [rax+rax+00h]
0x18006bad1  jmp     loc_18006B9E3
0x18006bad6  xor     r8d, r8d
0x18006bad9  mov     dword ptr [rbx+18h], 2
0x18006bae0  xor     edx, edx
0x18006bae2  mov     dword ptr [rbx], 1
0x18006bae8  mov     rcx, rbx
0x18006baeb  call    Dns64UdpTransportRefillPostedRequests
0x18006baf0  xor     eax, eax
0x18006baf2  jmp     loc_18006B9FB
```
