# DhcpOpenSocket

- ea: `0x18001cee0`
- end: `0x18001d01d`
- name: `DhcpOpenSocket`
- size: `317`
- prototype: `__int64 __fastcall(SOCKET *, int, __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c924`
- `0x18001cd90`

## callees

- `0x180001410`
- `0x18001cee0`

## import_xrefs

- `WS2_32!__imp_bind` at `0x18001cfcf`
- `WS2_32!__imp_bind` at `0x18001cfcf`
- `WS2_32!__imp_closesocket` at `0x18001cfee`
- `WS2_32!__imp_closesocket` at `0x18001cfee`
- `WS2_32!__imp_setsockopt` at `0x18001cf53`
- `WS2_32!__imp_setsockopt` at `0x18001cf7c`
- `WS2_32!__imp_setsockopt` at `0x18001cfa7`
- `WS2_32!__imp_setsockopt` at `0x18001cf53`
- `WS2_32!__imp_setsockopt` at `0x18001cf7c`
- `WS2_32!__imp_setsockopt` at `0x18001cfa7`
- `WS2_32!__imp_socket` at `0x18001cf28`
- `WS2_32!__imp_socket` at `0x18001cf28`
- `WS2_32!__imp_WSAGetLastError` at `0x18001cfd9`
- `WS2_32!__imp_WSAGetLastError` at `0x18001cfd9`

## pseudocode

```c
__int64 __fastcall DhcpOpenSocket(SOCKET *a1, int a2, __int16 a3)
{
  SOCKET v6; // rax
  SOCKET v7; // rdi
  unsigned int Error; // ebx
  char optval[8]; // [rsp+30h] [rbp-20h] BYREF
  struct sockaddr name; // [rsp+38h] [rbp-18h] BYREF

  *(_DWORD *)optval = 1;
  name = 0;
  v6 = socket(2, 2, 17);
  v7 = v6;
  if ( v6 == -1
    || setsockopt(v6, 0xFFFF, 4, optval, 4)
    || (*(_DWORD *)optval = 1, setsockopt(v7, 0xFFFF, 32, optval, 4))
    || (*(_DWORD *)optval = 4096, setsockopt(v7, 0xFFFF, 4098, optval, 4))
    || (name.sa_family = 2,
        *(_QWORD *)&name.sa_data[6] = 0,
        *(_WORD *)name.sa_data = a3,
        *(_DWORD *)&name.sa_data[2] = a2,
        bind(v7, &name, 16)) )
  {
    Error = WSAGetLastError();
    if ( Error && v7 != -1 )
      closesocket(v7);
  }
  else
  {
    *a1 = v7;
    return 0;
  }
  return Error;
}

```

## disassembly

```asm
0x18001cee0  mov     [rsp-28h+arg_18], rbx
0x18001cee5  push    rbp
0x18001cee6  push    rsi
0x18001cee7  push    rdi
0x18001cee8  push    r13
0x18001ceea  push    r14
0x18001ceec  mov     rbp, rsp
0x18001ceef  sub     rsp, 50h
0x18001cef3  mov     rax, cs:__security_cookie
0x18001cefa  xor     rax, rsp
0x18001cefd  mov     [rbp+var_8], rax
0x18001cf01  movzx   r14d, r8w
0x18001cf05  mov     dword ptr [rbp+optval], 1
0x18001cf0c  mov     r8d, 11h; protocol
0x18001cf12  mov     esi, edx
0x18001cf14  mov     rbx, rcx
0x18001cf17  xorps   xmm0, xmm0
0x18001cf1a  movups  xmmword ptr [rbp+name.sa_family], xmm0
0x18001cf1e  lea     r13d, [r8-0Fh]
0x18001cf22  mov     edx, r13d; type
0x18001cf25  mov     ecx, r13d; af
0x18001cf28  call    cs:__imp_socket
0x18001cf2e  mov     rdi, rax
0x18001cf31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cf35  jz      loc_18001CFD9
0x18001cf3b  lea     r9, [rbp+optval]; optval
0x18001cf3f  mov     [rsp+50h+optlen], 4; optlen
0x18001cf47  mov     edx, 0FFFFh; level
0x18001cf4c  lea     r8d, [r13+2]; optname
0x18001cf50  mov     rcx, rax; s
0x18001cf53  call    cs:__imp_setsockopt
0x18001cf59  test    eax, eax
0x18001cf5b  jnz     short loc_18001CFD9
0x18001cf5d  lea     r9, [rbp+optval]; optval
0x18001cf61  mov     dword ptr [rbp+optval], 1
0x18001cf68  mov     edx, 0FFFFh; level
0x18001cf6d  mov     [rsp+50h+optlen], 4; optlen
0x18001cf75  lea     r8d, [r13+1Eh]; optname
0x18001cf79  mov     rcx, rdi; s
0x18001cf7c  call    cs:__imp_setsockopt
0x18001cf82  test    eax, eax
0x18001cf84  jnz     short loc_18001CFD9
0x18001cf86  lea     r9, [rbp+optval]; optval
0x18001cf8a  mov     dword ptr [rbp+optval], 1000h
0x18001cf91  mov     edx, 0FFFFh; level
0x18001cf96  mov     [rsp+50h+optlen], 4; optlen
0x18001cf9e  mov     r8d, 1002h; optname
0x18001cfa4  mov     rcx, rdi; s
0x18001cfa7  call    cs:__imp_setsockopt
0x18001cfad  test    eax, eax
0x18001cfaf  jnz     short loc_18001CFD9
0x18001cfb1  xor     eax, eax
0x18001cfb3  mov     [rbp+name.sa_family], r13w
0x18001cfb8  lea     r8d, [r13+0Eh]; namelen
0x18001cfbc  mov     qword ptr [rbp+name.sa_data+6], rax
0x18001cfc0  lea     rdx, [rbp+name]; name
0x18001cfc4  mov     word ptr [rbp+name.sa_data], r14w
0x18001cfc9  mov     rcx, rdi; s
0x18001cfcc  mov     dword ptr [rbp+name.sa_data+2], esi
0x18001cfcf  call    cs:__imp_bind
0x18001cfd5  test    eax, eax
0x18001cfd7  jz      short loc_18001CFF6
0x18001cfd9  call    cs:__imp_WSAGetLastError
0x18001cfdf  mov     ebx, eax
0x18001cfe1  test    eax, eax
0x18001cfe3  jz      short loc_18001CFFB
0x18001cfe5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001cfe9  jz      short loc_18001CFFB
0x18001cfeb  mov     rcx, rdi; s
0x18001cfee  call    cs:__imp_closesocket
0x18001cff4  jmp     short loc_18001CFFB
0x18001cff6  mov     [rbx], rdi
0x18001cff9  xor     ebx, ebx
0x18001cffb  mov     eax, ebx
0x18001cffd  mov     rcx, [rbp+var_8]
0x18001d001  xor     rcx, rsp; StackCookie
0x18001d004  call    __security_check_cookie
0x18001d009  mov     rbx, [rsp+50h+arg_18]
0x18001d011  add     rsp, 50h
0x18001d015  pop     r14
0x18001d017  pop     r13
0x18001d019  pop     rdi
0x18001d01a  pop     rsi
0x18001d01b  pop     rbp
0x18001d01c  retn
```
