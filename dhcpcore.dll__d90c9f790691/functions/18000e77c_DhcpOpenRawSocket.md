# DhcpOpenRawSocket

- ea: `0x18000e77c`
- end: `0x18000e922`
- name: `DhcpOpenRawSocket`
- size: `422`
- prototype: `__int64 __fastcall(SOCKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e714`

## callees

- `0x18000e77c`
- `0x18001cef0`
- `0x18004d1a0`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x18000e848`
- `WS2_32!WSAIoctl` at `0x18000e848`
- `WS2_32!__imp_bind` at `0x18000e89c`
- `WS2_32!__imp_bind` at `0x18000e89c`
- `WS2_32!__imp_closesocket` at `0x18000e8f4`
- `WS2_32!__imp_closesocket` at `0x18000e8f4`
- `WS2_32!__imp_htons` at `0x18000e87e`
- `WS2_32!__imp_htons` at `0x18000e87e`
- `WS2_32!__imp_setsockopt` at `0x18000e7fd`
- `WS2_32!__imp_setsockopt` at `0x18000e86c`
- `WS2_32!__imp_setsockopt` at `0x18000e7fd`
- `WS2_32!__imp_setsockopt` at `0x18000e86c`
- `WS2_32!__imp_socket` at `0x18000e7c7`
- `WS2_32!__imp_socket` at `0x18000e7c7`
- `WS2_32!__imp_WSAGetLastError` at `0x18000e8ce`
- `WS2_32!__imp_WSAGetLastError` at `0x18000e8df`
- `WS2_32!__imp_WSAGetLastError` at `0x18000e8ce`
- `WS2_32!__imp_WSAGetLastError` at `0x18000e8df`

## pseudocode

```c
__int64 __fastcall DhcpOpenRawSocket(SOCKET *a1)
{
  SOCKET v2; // rdi
  u_short v3; // ax
  unsigned int Error; // ebx
  char optval[4]; // [rsp+50h] [rbp-20h] BYREF
  DWORD cbBytesReturned; // [rsp+54h] [rbp-1Ch] BYREF
  struct sockaddr name; // [rsp+58h] [rbp-18h] BYREF

  *(_DWORD *)optval = 0;
  cbBytesReturned = 0;
  name = 0;
  v2 = socket(2, 3, 17);
  if ( v2 != -1 || (Error = WSAGetLastError()) == 0 )
  {
    *(_DWORD *)optval = 1;
    setsockopt(v2, 0xFFFF, 4, optval, 4);
    *(_DWORD *)optval = 1;
    WSAIoctl(v2, 0x98000007, optval, 4u, 0, 0, &cbBytesReturned, 0, 0);
    *(_DWORD *)optval = 1;
    setsockopt(v2, 0xFFFF, 32, optval, 4);
    name.sa_family = 2;
    v3 = htons(DhcpGlobalClientPort);
    *(_DWORD *)&name.sa_data[2] = 0;
    *(_WORD *)name.sa_data = v3;
    Error = bind(v2, &name, 16);
    if ( !Error )
      goto LABEL_3;
    Error = WSAGetLastError();
    if ( !Error )
      goto LABEL_3;
    if ( v2 != -1 )
    {
      closesocket(v2);
      v2 = -1;
    }
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 71, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, Error);
LABEL_3:
  *a1 = v2;
  return Error;
}

```

## disassembly

```asm
0x18000e77c  mov     [rsp-18h+arg_8], rbx
0x18000e781  mov     [rsp-18h+arg_10], rsi
0x18000e786  push    rbp
0x18000e787  push    rdi
0x18000e788  push    r13
0x18000e78a  mov     rbp, rsp
0x18000e78d  sub     rsp, 70h
0x18000e791  mov     rax, cs:__security_cookie
0x18000e798  xor     rax, rsp
0x18000e79b  mov     [rbp+var_8], rax
0x18000e79f  mov     edx, 3; type
0x18000e7a4  mov     dword ptr [rbp+optval], 0
0x18000e7ab  mov     rsi, rcx
0x18000e7ae  mov     [rbp+cbBytesReturned], 0
0x18000e7b5  xorps   xmm0, xmm0
0x18000e7b8  movups  xmmword ptr [rbp+name.sa_family], xmm0
0x18000e7bc  lea     r13d, [rdx-1]
0x18000e7c0  mov     ecx, r13d; af
0x18000e7c3  lea     r8d, [rdx+0Eh]; protocol
0x18000e7c7  call    cs:__imp_socket
0x18000e7cd  mov     rdi, rax
0x18000e7d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e7d4  jz      loc_18000E8CE
0x18000e7da  mov     ebx, 0FFFFh
0x18000e7df  mov     dword ptr [rbp+optval], 1
0x18000e7e6  mov     edx, ebx; level
0x18000e7e8  mov     [rsp+70h+optlen], 4; optlen
0x18000e7f0  lea     r9, [rbp+optval]; optval
0x18000e7f4  mov     r8d, 4; optname
0x18000e7fa  mov     rcx, rdi; s
0x18000e7fd  call    cs:__imp_setsockopt
0x18000e803  mov     [rsp+70h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18000e80c  lea     rax, [rbp+cbBytesReturned]
0x18000e810  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x18000e819  lea     r8, [rbp+optval]; lpvInBuffer
0x18000e81d  mov     [rsp+70h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18000e822  mov     r9d, 4; cbInBuffer
0x18000e828  mov     [rsp+70h+cbOutBuffer], 0; cbOutBuffer
0x18000e830  mov     edx, 98000007h; dwIoControlCode
0x18000e835  mov     rcx, rdi; s
0x18000e838  mov     qword ptr [rsp+70h+optlen], 0; lpvOutBuffer
0x18000e841  mov     dword ptr [rbp+optval], 1
0x18000e848  call    cs:__imp_WSAIoctl
0x18000e84e  lea     r9, [rbp+optval]; optval
0x18000e852  mov     dword ptr [rbp+optval], 1
0x18000e859  mov     r8d, 20h ; ' '; optname
0x18000e85f  mov     [rsp+70h+optlen], 4; optlen
0x18000e867  mov     edx, ebx; level
0x18000e869  mov     rcx, rdi; s
0x18000e86c  call    cs:__imp_setsockopt
0x18000e872  movzx   ecx, cs:DhcpGlobalClientPort; hostshort
0x18000e879  mov     [rbp+name.sa_family], r13w
0x18000e87e  call    cs:__imp_htons
0x18000e884  mov     r8d, 10h; namelen
0x18000e88a  mov     dword ptr [rbp+name.sa_data+2], 0
0x18000e891  lea     rdx, [rbp+name]; name
0x18000e895  mov     word ptr [rbp+name.sa_data], ax
0x18000e899  mov     rcx, rdi; s
0x18000e89c  call    cs:__imp_bind
0x18000e8a2  mov     ebx, eax
0x18000e8a4  test    eax, eax
0x18000e8a6  jnz     short loc_18000E8DF
0x18000e8a8  mov     [rsi], rdi
0x18000e8ab  mov     eax, ebx
0x18000e8ad  mov     rcx, [rbp+var_8]
0x18000e8b1  xor     rcx, rsp; StackCookie
0x18000e8b4  call    __security_check_cookie
0x18000e8b9  lea     r11, [rsp+70h+var_s0]
0x18000e8be  mov     rbx, [r11+28h]
0x18000e8c2  mov     rsi, [r11+30h]
0x18000e8c6  mov     rsp, r11
0x18000e8c9  pop     r13
0x18000e8cb  pop     rdi
0x18000e8cc  pop     rbp
0x18000e8cd  retn
0x18000e8ce  call    cs:__imp_WSAGetLastError
0x18000e8d4  mov     ebx, eax
0x18000e8d6  test    eax, eax
0x18000e8d8  jnz     short loc_18000E8FE
0x18000e8da  jmp     loc_18000E7DA
0x18000e8df  call    cs:__imp_WSAGetLastError
0x18000e8e5  mov     ebx, eax
0x18000e8e7  test    eax, eax
0x18000e8e9  jz      short loc_18000E8A8
0x18000e8eb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000e8ef  jz      short loc_18000E8FE
0x18000e8f1  mov     rcx, rdi; s
0x18000e8f4  call    cs:__imp_closesocket
0x18000e8fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e8fe  test    byte ptr cs:xmmword_1800616A0, r13b
0x18000e905  jz      short loc_18000E8A8
0x18000e907  mov     edx, 47h ; 'G'
0x18000e90c  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000e913  mov     ecx, 401h
0x18000e918  mov     r9d, ebx
0x18000e91b  call    WPP_SF_D
0x18000e920  jmp     short loc_18000E8A8
```
