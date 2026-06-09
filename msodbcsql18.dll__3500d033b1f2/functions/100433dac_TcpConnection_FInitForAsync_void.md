# TcpConnection::FInitForAsync(void)

- ea: `0x100433dac`
- end: `0x100433fe2`
- name: `?FInitForAsync@TcpConnection@@QEAAKXZ`
- size: `566`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1004360b8`
- `0x100436dc0`

## callees

- `0x100433dac`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x100433e50`
- `KERNEL32!CreateEventW` at `0x100433e50`
- `KERNEL32!GetLastError` at `0x100433e62`
- `KERNEL32!GetLastError` at `0x100433e62`
- `WS2_32!GetAddrInfoW` at `0x100433ede`
- `WS2_32!GetAddrInfoW` at `0x100433ede`
- `WS2_32!FreeAddrInfoW` at `0x100433f86`
- `WS2_32!FreeAddrInfoW` at `0x100433f86`
- `WS2_32!__imp_bind` at `0x100433f31`
- `WS2_32!__imp_bind` at `0x100433f31`
- `WS2_32!__imp_WSAGetLastError` at `0x100433ee8`
- `WS2_32!__imp_WSAGetLastError` at `0x100433f3c`
- `WS2_32!__imp_WSAGetLastError` at `0x100433ee8`
- `WS2_32!__imp_WSAGetLastError` at `0x100433f3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpConnection::FInitForAsync(TcpConnection *this)
{
  _OWORD *v2; // rax
  unsigned int Error; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v6; // r9
  wchar_t *v7; // r8
  __int64 v8; // rdx
  ADDRINFOW pHints; // [rsp+28h] [rbp-38h] BYREF
  PADDRINFOW ppResult; // [rsp+70h] [rbp+10h] BYREF
  __int64 v12; // [rsp+78h] [rbp+18h] BYREF

  v12 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `TcpConnection::FInitForAsync'::`7'::_bidPtrSA_040_1312[0] )
    bidScopeEnterW(&v12, `TcpConnection::FInitForAsync'::`7'::_bidPtrSA_040_1312[0], *((unsigned int *)this + 11));
  ppResult = 0;
  v2 = (_OWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 32);
  *(_QWORD *)this = v2;
  if ( !v2 )
  {
    Error = 14;
    *((_DWORD *)this + 9) = 14;
    *((_DWORD *)this + 10) = 2;
    goto LABEL_23;
  }
  *v2 = 0;
  v2[1] = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    Error = LastError;
    *((_DWORD *)this + 9) = LastError;
    *((_DWORD *)this + 10) = 3;
    if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`22'::_bidPtrSA_030_1337[0] )
    {
      v6 = LastError;
      v7 = `TcpConnection::FInitForAsync'::`22'::_bidPtrSA_030_1337[0];
      v8 = 1369088;
LABEL_21:
      bidTraceW(0, v8, v7, v6);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  *(_QWORD *)(*(_QWORD *)this + 24LL) = EventW;
  memset(&pHints, 0, sizeof(pHints));
  pHints.ai_family = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL);
  pHints.ai_socktype = 1;
  pHints.ai_flags = 1;
  Error = 0;
  if ( GetAddrInfoW(0, L"0", &pHints, &ppResult) )
    Error = WSAGetLastError();
  if ( Error )
  {
    *((_DWORD *)this + 9) = Error;
    *((_DWORD *)this + 10) = 3;
    if ( (bidGblFlags & 2) == 0 || !`TcpConnection::FInitForAsync'::`32'::_bidPtrSA_030_1362[0] )
      goto LABEL_23;
    v7 = `TcpConnection::FInitForAsync'::`32'::_bidPtrSA_030_1362[0];
    v8 = 1394688;
LABEL_20:
    v6 = Error;
    goto LABEL_21;
  }
  if ( bind(*((_QWORD *)this + 3), ppResult->ai_addr, ppResult->ai_addrlen) != -1 )
  {
    Error = 0;
    goto LABEL_23;
  }
  Error = WSAGetLastError();
  *((_DWORD *)this + 9) = Error;
  *((_DWORD *)this + 10) = 5;
  if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`42'::_bidPtrSA_030_1372[0] )
  {
    v7 = `TcpConnection::FInitForAsync'::`42'::_bidPtrSA_030_1372[0];
    v8 = 1404928;
    goto LABEL_20;
  }
LABEL_23:
  if ( ppResult )
  {
    FreeAddrInfoW(ppResult);
    ppResult = 0;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && `TcpConnection::FInitForAsync'::`52'::_bidPtrSA_030_1392[0] )
    bidTraceW(0, 1425408, `TcpConnection::FInitForAsync'::`52'::_bidPtrSA_030_1392[0], Error);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v12);
  return Error;
}

```

## disassembly

```asm
0x100433dac  mov     rax, rsp
0x100433daf  push    rbp
0x100433db0  mov     rbp, rsp
0x100433db3  sub     rsp, 60h
0x100433db7  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x100433dbf  mov     [rax+18h], rbx
0x100433dc3  mov     [rax+20h], rdi
0x100433dc7  mov     rdi, rcx
0x100433dca  or      [rbp+arg_8], 0FFFFFFFFFFFFFFFFh
0x100433dcf  mov     eax, cs:_bidGblFlags
0x100433dd5  mov     ecx, 20004h
0x100433dda  and     eax, ecx
0x100433ddc  cmp     eax, ecx
0x100433dde  jnz     short loc_100433E00
0x100433de0  mov     rax, cs:?_bidPtrSA_040_1312@?6??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`7'::_bidPtrSA_040_1312
0x100433de7  test    rax, rax
0x100433dea  jz      short loc_100433E00
0x100433dec  mov     r8d, [rdi+2Ch]
0x100433df0  mov     rdx, cs:?_bidPtrSA_040_1312@?6??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`7'::_bidPtrSA_040_1312
0x100433df7  lea     rcx, [rbp+arg_8]
0x100433dfb  call    _bidScopeEnterW
0x100433e00  and     [rbp+ppResult], 0
0x100433e05  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x100433e0c  mov     rax, [rcx]
0x100433e0f  mov     edx, 20h ; ' '
0x100433e14  mov     rax, [rax+58h]
0x100433e18  call    cs:__guard_dispatch_icall_fptr
0x100433e1e  mov     [rdi], rax
0x100433e21  test    rax, rax
0x100433e24  jnz     short loc_100433E38
0x100433e26  lea     ebx, [rax+0Eh]
0x100433e29  mov     [rdi+24h], ebx
0x100433e2c  mov     dword ptr [rdi+28h], 2
0x100433e33  jmp     loc_100433F7D
0x100433e38  xorps   xmm0, xmm0
0x100433e3b  movups  xmmword ptr [rax], xmm0
0x100433e3e  movups  xmmword ptr [rax+10h], xmm0
0x100433e42  xor     r9d, r9d; lpName
0x100433e45  xor     r8d, r8d; bInitialState
0x100433e48  lea     ebx, [r9+1]
0x100433e4c  mov     edx, ebx; bManualReset
0x100433e4e  xor     ecx, ecx; lpEventAttributes
0x100433e50  call    cs:__imp_CreateEventW
0x100433e56  mov     rcx, rax
0x100433e59  mov     [rdi+10h], rax
0x100433e5d  test    rax, rax
0x100433e60  jnz     short loc_100433EA5
0x100433e62  call    cs:__imp_GetLastError
0x100433e68  mov     ebx, eax
0x100433e6a  mov     [rdi+24h], eax
0x100433e6d  mov     dword ptr [rdi+28h], 3
0x100433e74  test    byte ptr cs:_bidGblFlags, 2
0x100433e7b  jz      loc_100433F7D
0x100433e81  mov     rcx, cs:?_bidPtrSA_030_1337@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidPtrSA_030_1337
0x100433e88  test    rcx, rcx
0x100433e8b  jz      loc_100433F7D
0x100433e91  mov     r9d, eax
0x100433e94  mov     r8, cs:?_bidPtrSA_030_1337@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidPtrSA_030_1337
0x100433e9b  mov     edx, 14E400h
0x100433ea0  jmp     loc_100433F72
0x100433ea5  mov     rax, [rdi]
0x100433ea8  mov     [rax+18h], rcx
0x100433eac  xorps   xmm0, xmm0
0x100433eaf  movups  xmmword ptr [rbp+pHints.ai_flags], xmm0
0x100433eb3  movups  xmmword ptr [rbp+pHints.ai_addrlen], xmm0
0x100433eb7  movups  xmmword ptr [rbp+pHints.ai_addr], xmm0
0x100433ebb  mov     rax, [rdi+8]
0x100433ebf  mov     ecx, [rax+4]
0x100433ec2  mov     [rbp+pHints.ai_family], ecx
0x100433ec5  mov     [rbp+pHints.ai_socktype], ebx
0x100433ec8  mov     [rbp+pHints.ai_flags], ebx
0x100433ecb  xor     ebx, ebx
0x100433ecd  lea     r9, [rbp+ppResult]; ppResult
0x100433ed1  lea     r8, [rbp+pHints]; pHints
0x100433ed5  lea     rdx, pServiceName; "0"
0x100433edc  xor     ecx, ecx; pNodeName
0x100433ede  call    cs:__imp_GetAddrInfoW
0x100433ee4  test    eax, eax
0x100433ee6  jz      short loc_100433EF0
0x100433ee8  call    cs:__imp_WSAGetLastError
0x100433eee  mov     ebx, eax
0x100433ef0  test    ebx, ebx
0x100433ef2  jz      short loc_100433F21
0x100433ef4  mov     [rdi+24h], ebx
0x100433ef7  mov     dword ptr [rdi+28h], 3
0x100433efe  test    byte ptr cs:_bidGblFlags, 2
0x100433f05  jz      short loc_100433F7D
0x100433f07  mov     rax, cs:?_bidPtrSA_030_1362@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidPtrSA_030_1362
0x100433f0e  test    rax, rax
0x100433f11  jz      short loc_100433F7D
0x100433f13  mov     r8, cs:?_bidPtrSA_030_1362@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidPtrSA_030_1362
0x100433f1a  mov     edx, 154800h
0x100433f1f  jmp     short loc_100433F6F
0x100433f21  mov     rdx, [rbp+ppResult]
0x100433f25  mov     r8d, [rdx+10h]; namelen
0x100433f29  mov     rdx, [rdx+20h]; name
0x100433f2d  mov     rcx, [rdi+18h]; s
0x100433f31  call    cs:__imp_bind
0x100433f37  cmp     eax, 0FFFFFFFFh
0x100433f3a  jnz     short loc_100433F7B
0x100433f3c  call    cs:__imp_WSAGetLastError
0x100433f42  mov     ebx, eax
0x100433f44  mov     [rdi+24h], eax
0x100433f47  mov     dword ptr [rdi+28h], 5
0x100433f4e  test    byte ptr cs:_bidGblFlags, 2
0x100433f55  jz      short loc_100433F7D
0x100433f57  mov     rax, cs:?_bidPtrSA_030_1372@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidPtrSA_030_1372
0x100433f5e  test    rax, rax
0x100433f61  jz      short loc_100433F7D
0x100433f63  mov     r8, cs:?_bidPtrSA_030_1372@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidPtrSA_030_1372
0x100433f6a  mov     edx, 157000h
0x100433f6f  mov     r9d, ebx
0x100433f72  xor     ecx, ecx
0x100433f74  call    _bidTraceW
0x100433f79  jmp     short loc_100433F7D
0x100433f7b  xor     ebx, ebx
0x100433f7d  mov     rcx, [rbp+ppResult]; pAddrInfo
0x100433f81  test    rcx, rcx
0x100433f84  jz      short loc_100433F91
0x100433f86  call    cs:__imp_FreeAddrInfoW
0x100433f8c  and     [rbp+ppResult], 0
0x100433f91  mov     eax, cs:_bidGblFlags
0x100433f97  mov     ecx, 20002h
0x100433f9c  and     eax, ecx
0x100433f9e  cmp     eax, ecx
0x100433fa0  jnz     short loc_100433FC5
0x100433fa2  mov     rax, cs:?_bidPtrSA_030_1392@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidPtrSA_030_1392
0x100433fa9  test    rax, rax
0x100433fac  jz      short loc_100433FC5
0x100433fae  mov     r9d, ebx
0x100433fb1  mov     r8, cs:?_bidPtrSA_030_1392@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBGEB; ushort const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidPtrSA_030_1392
0x100433fb8  mov     edx, 15C000h
0x100433fbd  xor     ecx, ecx
0x100433fbf  call    _bidTraceW
0x100433fc4  nop
0x100433fc5  lea     rcx, [rbp+arg_8]; this
0x100433fc9  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100433fce  mov     eax, ebx
0x100433fd0  lea     r11, [rsp+60h+var_s0]
0x100433fd5  mov     rbx, [r11+20h]
0x100433fd9  mov     rdi, [r11+28h]
0x100433fdd  mov     rsp, r11
0x100433fe0  pop     rbp
0x100433fe1  retn
```
