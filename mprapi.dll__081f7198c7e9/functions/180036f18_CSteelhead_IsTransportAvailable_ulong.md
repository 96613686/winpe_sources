# CSteelhead::IsTransportAvailable(ulong)

- ea: `0x180036f18`
- end: `0x180037014`
- name: `?IsTransportAvailable@CSteelhead@@AEAAHK@Z`
- size: `252`
- prototype: `__int64 __fastcall(CSteelhead *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800356d0`

## callees

- `0x180036f18`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `rtutils!TracePrintfW` at `0x180036f78`
- `rtutils!TracePrintfW` at `0x180036fca`
- `rtutils!TracePrintfW` at `0x180036feb`
- `rtutils!TracePrintfW` at `0x180036f78`
- `rtutils!TracePrintfW` at `0x180036fca`
- `rtutils!TracePrintfW` at `0x180036feb`
- `WS2_32!__imp_closesocket` at `0x180036fa9`
- `WS2_32!__imp_closesocket` at `0x180036fa9`
- `WS2_32!__imp_socket` at `0x180036f9a`
- `WS2_32!__imp_socket` at `0x180036f9a`
- `WS2_32!__imp_WSAGetLastError` at `0x180036f62`
- `WS2_32!__imp_WSAGetLastError` at `0x180036fb1`
- `WS2_32!__imp_WSAGetLastError` at `0x180036f62`
- `WS2_32!__imp_WSAGetLastError` at `0x180036fb1`
- `WS2_32!__imp_WSAStartup` at `0x180036f58`
- `WS2_32!__imp_WSAStartup` at `0x180036f58`
- `WS2_32!__imp_WSACleanup` at `0x180036fd2`
- `WS2_32!__imp_WSACleanup` at `0x180036fd2`

## pseudocode

```c
__int64 __fastcall CSteelhead::IsTransportAvailable(CSteelhead *this, unsigned int a2)
{
  unsigned int v3; // edi
  unsigned int v4; // eax
  int v5; // ecx
  SOCKET v6; // rax
  unsigned int Error; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  v3 = 1;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( !WSAStartup(2u, &WSAData) )
  {
    if ( a2 == 33 )
    {
      v5 = 2;
    }
    else
    {
      if ( a2 != 87 )
        goto LABEL_9;
      v5 = 23;
    }
    v6 = socket(v5, 2, 0);
    if ( v6 != -1 )
    {
      closesocket(v6);
LABEL_10:
      WSACleanup();
      goto LABEL_11;
    }
LABEL_9:
    Error = WSAGetLastError();
    TracePrintfW(g_dwTraceHandle, L"CSteelhead::IsTransportAvailable for transport id %d failed. Eror: %d", a2, Error);
    v3 = 0;
    goto LABEL_10;
  }
  v4 = WSAGetLastError();
  TracePrintfW(g_dwTraceHandle, L"CSteelhead::IsTransportAvailable: WSAStartup failed. Error %d", v4);
LABEL_11:
  TracePrintfW(g_dwTraceHandle, L"CSteelhead::IsTransportAvailable for transport id %d is: %d", a2, v3);
  return v3;
}

```

## disassembly

```asm
0x180036f18  mov     [rsp+arg_0], rbx
0x180036f1d  push    rdi
0x180036f1e  sub     rsp, 1D0h
0x180036f25  mov     rax, cs:__security_cookie
0x180036f2c  xor     rax, rsp
0x180036f2f  mov     [rsp+1D8h+var_18], rax
0x180036f37  mov     ebx, edx
0x180036f39  lea     rcx, [rsp+1D8h+WSAData]; void *
0x180036f3e  xor     edx, edx; Val
0x180036f40  mov     r8d, 198h; Size
0x180036f46  mov     edi, 1
0x180036f4b  call    memset_0
0x180036f50  lea     ecx, [rdi+1]; wVersionRequested
0x180036f53  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x180036f58  call    cs:__imp_WSAStartup
0x180036f5e  test    eax, eax
0x180036f60  jz      short loc_180036F80
0x180036f62  call    cs:__imp_WSAGetLastError
0x180036f68  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036f6e  lea     rdx, aCsteelheadIstr_1; "CSteelhead::IsTransportAvailable: WSASt"...
0x180036f75  mov     r8d, eax
0x180036f78  call    cs:__imp_TracePrintfW
0x180036f7e  jmp     short loc_180036FD8
0x180036f80  cmp     ebx, 21h ; '!'
0x180036f83  jnz     short loc_180036F8C
0x180036f85  lea     edx, [rbx-1Fh]
0x180036f88  mov     ecx, edx
0x180036f8a  jmp     short loc_180036F97
0x180036f8c  cmp     ebx, 57h ; 'W'
0x180036f8f  jnz     short loc_180036FB1
0x180036f91  lea     edx, [rbx-55h]; type
0x180036f94  lea     ecx, [rbx-40h]; af
0x180036f97  xor     r8d, r8d; protocol
0x180036f9a  call    cs:__imp_socket
0x180036fa0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036fa4  jz      short loc_180036FB1
0x180036fa6  mov     rcx, rax; s
0x180036fa9  call    cs:__imp_closesocket
0x180036faf  jmp     short loc_180036FD2
0x180036fb1  call    cs:__imp_WSAGetLastError
0x180036fb7  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036fbd  lea     rdx, aCsteelheadIstr_0; "CSteelhead::IsTransportAvailable for tr"...
0x180036fc4  mov     r9d, eax
0x180036fc7  mov     r8d, ebx
0x180036fca  call    cs:__imp_TracePrintfW
0x180036fd0  xor     edi, edi
0x180036fd2  call    cs:__imp_WSACleanup
0x180036fd8  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036fde  lea     rdx, aCsteelheadIstr; "CSteelhead::IsTransportAvailable for tr"...
0x180036fe5  mov     r9d, edi
0x180036fe8  mov     r8d, ebx
0x180036feb  call    cs:__imp_TracePrintfW
0x180036ff1  mov     eax, edi
0x180036ff3  mov     rcx, [rsp+1D8h+var_18]
0x180036ffb  xor     rcx, rsp; StackCookie
0x180036ffe  call    __security_check_cookie
0x180037003  mov     rbx, [rsp+1D8h+arg_0]
0x18003700b  add     rsp, 1D0h
0x180037012  pop     rdi
0x180037013  retn
```
