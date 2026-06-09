# ResolveTarget(ushort const * *,ushort *,ulong)

- ea: `0x18000b920`
- end: `0x18000babb`
- name: `?ResolveTarget@@YAJPEAPEBGPEAGK@Z`
- size: `411`
- prototype: `int(const unsigned __int16 **, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180004220`
- `0x18000b740`

## callees

- `0x180001840`
- `0x18000b920`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x18000ba84`
- `WS2_32!FreeAddrInfoW` at `0x18000ba84`
- `WS2_32!GetAddrInfoW` at `0x18000b9d8`
- `WS2_32!GetAddrInfoW` at `0x18000ba2d`
- `WS2_32!GetAddrInfoW` at `0x18000b9d8`
- `WS2_32!GetAddrInfoW` at `0x18000ba2d`
- `WS2_32!GetNameInfoW` at `0x18000ba08`
- `WS2_32!GetNameInfoW` at `0x18000ba08`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b98d`
- `WS2_32!__imp_WSAGetLastError` at `0x18000ba65`
- `WS2_32!__imp_WSAGetLastError` at `0x18000b98d`
- `WS2_32!__imp_WSAGetLastError` at `0x18000ba65`
- `WS2_32!__imp_WSAStartup` at `0x18000b983`
- `WS2_32!__imp_WSAStartup` at `0x18000b983`
- `WS2_32!__imp_WSACleanup` at `0x18000ba8a`
- `WS2_32!__imp_WSACleanup` at `0x18000ba8a`

## pseudocode

```c
__int64 __fastcall ResolveTarget(const unsigned __int16 **a1, unsigned __int16 *a2)
{
  int v4; // eax
  signed int v5; // ebx
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx
  const unsigned __int16 *ai_canonname; // r8
  int Error; // eax
  PADDRINFOW ppResult; // [rsp+40h] [rbp-C0h] BYREF
  ADDRINFOW pHints; // [rsp+48h] [rbp-B8h] BYREF
  WSAData WSAData; // [rsp+80h] [rbp-80h] BYREF

  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( !WSAStartup(0x101u, &WSAData) )
  {
    *a2 = 0;
    v6 = *a1;
    memset(&pHints, 0, sizeof(pHints));
    pHints.ai_flags = 4;
    if ( GetAddrInfoW(v6, 0, &pHints, &ppResult) )
    {
      v7 = *a1;
      pHints.ai_flags = 2;
      if ( !GetAddrInfoW(v7, 0, &pHints, &ppResult) )
      {
        if ( !ppResult )
        {
          v5 = -2147418113;
LABEL_17:
          WSACleanup();
          goto LABEL_18;
        }
        ai_canonname = ppResult->ai_canonname;
        if ( !ai_canonname )
          ai_canonname = *a1;
        v5 = StringCchCopyW(a2, 0x105u, ai_canonname);
LABEL_15:
        if ( ppResult )
          FreeAddrInfoW(ppResult);
        goto LABEL_17;
      }
    }
    else if ( !GetNameInfoW(ppResult->ai_addr, ppResult->ai_addrlen, a2, 0x105u, 0, 0, 4) )
    {
      v5 = 0;
      goto LABEL_15;
    }
    Error = WSAGetLastError();
    v5 = Error;
    if ( Error > 0 )
      v5 = (unsigned __int16)Error | 0x80070000;
    goto LABEL_15;
  }
  v4 = WSAGetLastError();
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
LABEL_18:
  if ( v5 >= 0 )
    *a1 = a2;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b920  mov     [rsp-8+arg_10], rbx
0x18000b925  push    rbp
0x18000b926  push    rsi
0x18000b927  push    rdi
0x18000b928  lea     rbp, [rsp-130h]
0x18000b930  sub     rsp, 230h
0x18000b937  mov     rax, cs:__security_cookie
0x18000b93e  xor     rax, rsp
0x18000b941  mov     [rbp+140h+var_20], rax
0x18000b948  xorps   xmm0, xmm0
0x18000b94b  mov     [rsp+240h+ppResult], 0
0x18000b954  mov     rsi, rdx
0x18000b957  mov     rdi, rcx
0x18000b95a  xor     edx, edx; Val
0x18000b95c  lea     rcx, [rbp+140h+WSAData]; void *
0x18000b960  mov     r8d, 198h; Size
0x18000b966  movups  xmmword ptr [rsp+240h+pHints.ai_flags], xmm0
0x18000b96b  movups  xmmword ptr [rsp+240h+pHints.ai_addrlen], xmm0
0x18000b970  movups  xmmword ptr [rsp+240h+pHints.ai_addr], xmm0
0x18000b975  call    memset_0
0x18000b97a  mov     ecx, 101h; wVersionRequested
0x18000b97f  lea     rdx, [rbp+140h+WSAData]; lpWSAData
0x18000b983  call    cs:__imp_WSAStartup
0x18000b989  test    eax, eax
0x18000b98b  jz      short loc_18000B9AB
0x18000b98d  call    cs:__imp_WSAGetLastError
0x18000b993  mov     ebx, eax
0x18000b995  test    eax, eax
0x18000b997  jle     loc_18000BA90
0x18000b99d  movzx   ebx, ax
0x18000b9a0  or      ebx, 80070000h
0x18000b9a6  jmp     loc_18000BA90
0x18000b9ab  xorps   xmm0, xmm0
0x18000b9ae  lea     r9, [rsp+240h+ppResult]; ppResult
0x18000b9b3  xor     eax, eax
0x18000b9b5  lea     r8, [rsp+240h+pHints]; pHints
0x18000b9ba  mov     [rsi], ax
0x18000b9bd  xor     edx, edx; pServiceName
0x18000b9bf  mov     rcx, [rdi]; pNodeName
0x18000b9c2  movups  xmmword ptr [rsp+240h+pHints.ai_flags], xmm0
0x18000b9c7  lea     ebx, [rax+4]
0x18000b9ca  mov     [rsp+240h+pHints.ai_flags], ebx
0x18000b9ce  movups  xmmword ptr [rsp+240h+pHints.ai_addrlen], xmm0
0x18000b9d3  movups  xmmword ptr [rsp+240h+pHints.ai_addr], xmm0
0x18000b9d8  call    cs:__imp_GetAddrInfoW
0x18000b9de  test    eax, eax
0x18000b9e0  jnz     short loc_18000BA16
0x18000b9e2  mov     rcx, [rsp+240h+ppResult]
0x18000b9e7  mov     r9d, 105h; NodeBufferSize
0x18000b9ed  mov     [rsp+240h+Flags], ebx; Flags
0x18000b9f1  mov     r8, rsi; pNodeBuffer
0x18000b9f4  mov     [rsp+240h+ServiceBufferSize], eax; ServiceBufferSize
0x18000b9f8  mov     [rsp+240h+pServiceBuffer], 0; pServiceBuffer
0x18000ba01  mov     edx, [rcx+10h]; SockaddrLength
0x18000ba04  mov     rcx, [rcx+20h]; pSockaddr
0x18000ba08  call    cs:__imp_GetNameInfoW
0x18000ba0e  test    eax, eax
0x18000ba10  jnz     short loc_18000BA65
0x18000ba12  xor     ebx, ebx
0x18000ba14  jmp     short loc_18000BA7A
0x18000ba16  mov     rcx, [rdi]; pNodeName
0x18000ba19  lea     r9, [rsp+240h+ppResult]; ppResult
0x18000ba1e  lea     r8, [rsp+240h+pHints]; pHints
0x18000ba23  mov     [rsp+240h+pHints.ai_flags], 2
0x18000ba2b  xor     edx, edx; pServiceName
0x18000ba2d  call    cs:__imp_GetAddrInfoW
0x18000ba33  test    eax, eax
0x18000ba35  jnz     short loc_18000BA65
0x18000ba37  mov     r8, [rsp+240h+ppResult]
0x18000ba3c  test    r8, r8
0x18000ba3f  jnz     short loc_18000BA48
0x18000ba41  mov     ebx, 8000FFFFh
0x18000ba46  jmp     short loc_18000BA8A
0x18000ba48  mov     r8, [r8+18h]
0x18000ba4c  test    r8, r8
0x18000ba4f  jnz     short loc_18000BA54
0x18000ba51  mov     r8, [rdi]; unsigned __int16 *
0x18000ba54  mov     edx, 105h; unsigned __int64
0x18000ba59  mov     rcx, rsi; unsigned __int16 *
0x18000ba5c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ba61  mov     ebx, eax
0x18000ba63  jmp     short loc_18000BA7A
0x18000ba65  call    cs:__imp_WSAGetLastError
0x18000ba6b  mov     ebx, eax
0x18000ba6d  test    eax, eax
0x18000ba6f  jle     short loc_18000BA7A
0x18000ba71  movzx   ebx, ax
0x18000ba74  or      ebx, 80070000h
0x18000ba7a  mov     rcx, [rsp+240h+ppResult]; pAddrInfo
0x18000ba7f  test    rcx, rcx
0x18000ba82  jz      short loc_18000BA8A
0x18000ba84  call    cs:__imp_FreeAddrInfoW
0x18000ba8a  call    cs:__imp_WSACleanup
0x18000ba90  test    ebx, ebx
0x18000ba92  js      short loc_18000BA97
0x18000ba94  mov     [rdi], rsi
0x18000ba97  mov     eax, ebx
0x18000ba99  mov     rcx, [rbp+140h+var_20]
0x18000baa0  xor     rcx, rsp; StackCookie
0x18000baa3  call    __security_check_cookie
0x18000baa8  mov     rbx, [rsp+240h+arg_10]
0x18000bab0  add     rsp, 230h
0x18000bab7  pop     rdi
0x18000bab8  pop     rsi
0x18000bab9  pop     rbp
0x18000baba  retn
```
