# IP_RESTRICTION_LIST::ConvertSockAddrToString(sockaddr *,STRU *,STRU *)

- ea: `0x180003c18`
- end: `0x180003ce1`
- name: `?ConvertSockAddrToString@IP_RESTRICTION_LIST@@QEAAJPEAUsockaddr@@PEAVSTRU@@1@Z`
- size: `201`
- prototype: `int(IP_RESTRICTION_LIST *__hidden this, struct sockaddr *, struct STRU *, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000369c`

## callees

- `0x180003c18`

## import_xrefs

- `WS2_32!GetNameInfoW` at `0x180003c9c`
- `WS2_32!GetNameInfoW` at `0x180003c9c`
- `WS2_32!__imp_WSAGetLastError` at `0x180003ca6`
- `WS2_32!__imp_WSAGetLastError` at `0x180003ca6`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003cc0`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003cc9`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003cc0`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180003cc9`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003c32`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003c48`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003c32`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180003c48`

## pseudocode

```c
int __fastcall IP_RESTRICTION_LIST::ConvertSockAddrToString(
        IP_RESTRICTION_LIST *this,
        struct sockaddr *a2,
        PWCHAR *a3,
        struct STRU *a4)
{
  int result; // eax
  int v8; // ebx
  socklen_t v9; // edx
  int Error; // eax

  result = STRU::Resize((STRU *)a3, 0x401u);
  if ( result >= 0 )
  {
    result = STRU::Resize(a4, 0x20u);
    v8 = result;
    if ( result >= 0 )
    {
      if ( a2->sa_family == 2 )
      {
        v9 = 16;
      }
      else
      {
        if ( a2->sa_family != 23 )
          return -2147024809;
        v9 = 28;
      }
      if ( GetNameInfoW(a2, v9, a3[4], *((_DWORD *)a3 + 10) >> 1, *((PWCHAR *)a4 + 4), *((_DWORD *)a4 + 10), 10) )
      {
        Error = WSAGetLastError();
        v8 = Error;
        if ( Error > 0 )
          return (unsigned __int16)Error | 0x80070000;
      }
      else
      {
        STRU::SyncWithBuffer((STRU *)a3);
        STRU::SyncWithBuffer(a4);
      }
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003c18  push    rbx
0x180003c1a  push    rbp
0x180003c1b  push    rsi
0x180003c1c  push    rdi
0x180003c1d  sub     rsp, 48h
0x180003c21  mov     rbp, rdx
0x180003c24  mov     rcx, r8
0x180003c27  mov     edx, 401h
0x180003c2c  mov     rdi, r9
0x180003c2f  mov     rsi, r8
0x180003c32  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003c38  test    eax, eax
0x180003c3a  js      loc_180003CD8
0x180003c40  mov     edx, 20h ; ' '
0x180003c45  mov     rcx, rdi
0x180003c48  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180003c4e  mov     ebx, eax
0x180003c50  test    eax, eax
0x180003c52  js      loc_180003CD8
0x180003c58  mov     eax, 2
0x180003c5d  cmp     ax, [rbp+0]
0x180003c61  jnz     short loc_180003C68
0x180003c63  lea     edx, [rax+0Eh]
0x180003c66  jmp     short loc_180003C76
0x180003c68  mov     eax, 17h
0x180003c6d  cmp     ax, [rbp+0]
0x180003c71  jnz     short loc_180003CD1
0x180003c73  lea     edx, [rax+5]; SockaddrLength
0x180003c76  mov     eax, [rdi+28h]
0x180003c79  mov     rcx, rbp; pSockaddr
0x180003c7c  mov     r9d, [rsi+28h]
0x180003c80  mov     r8, [rsi+20h]; pNodeBuffer
0x180003c84  mov     [rsp+68h+Flags], 0Ah; Flags
0x180003c8c  mov     [rsp+68h+ServiceBufferSize], eax; ServiceBufferSize
0x180003c90  mov     rax, [rdi+20h]
0x180003c94  shr     r9d, 1; NodeBufferSize
0x180003c97  mov     [rsp+68h+pServiceBuffer], rax; pServiceBuffer
0x180003c9c  call    cs:__imp_GetNameInfoW
0x180003ca2  test    eax, eax
0x180003ca4  jz      short loc_180003CBD
0x180003ca6  call    cs:__imp_WSAGetLastError
0x180003cac  mov     ebx, eax
0x180003cae  test    eax, eax
0x180003cb0  jle     short loc_180003CD6
0x180003cb2  movzx   ebx, ax
0x180003cb5  or      ebx, 80070000h
0x180003cbb  jmp     short loc_180003CD6
0x180003cbd  mov     rcx, rsi
0x180003cc0  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003cc6  mov     rcx, rdi
0x180003cc9  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003ccf  jmp     short loc_180003CD6
0x180003cd1  mov     ebx, 80070057h
0x180003cd6  mov     eax, ebx
0x180003cd8  add     rsp, 48h
0x180003cdc  pop     rdi
0x180003cdd  pop     rsi
0x180003cde  pop     rbp
0x180003cdf  pop     rbx
0x180003ce0  retn
```
