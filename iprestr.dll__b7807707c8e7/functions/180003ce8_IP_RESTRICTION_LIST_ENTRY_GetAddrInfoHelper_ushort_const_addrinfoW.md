# IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(ushort const *,addrinfoW * *)

- ea: `0x180003ce8`
- end: `0x180003ded`
- name: `?GetAddrInfoHelper@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBGPEAPEAUaddrinfoW@@@Z`
- size: `261`
- prototype: `int(IP_RESTRICTION_LIST_ENTRY *__hidden this, const unsigned __int16 *, struct addrinfoW **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800034fc`
- `0x180004608`
- `0x18000474c`

## callees

- `0x180003ce8`
- `0x180004aa6`
- `0x180004ad0`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x180003d9d`
- `WS2_32!GetAddrInfoW` at `0x180003d9d`
- `WS2_32!__imp_WSAGetLastError` at `0x180003da7`
- `WS2_32!__imp_WSAGetLastError` at `0x180003da7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003d53`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003d53`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003dc4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003dc4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003d45`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003d45`

## pseudocode

```c
__int64 __fastcall IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(
        IP_RESTRICTION_LIST_ENTRY *this,
        const unsigned __int16 *a2,
        struct addrinfoW **a3)
{
  int v5; // ebx
  int Error; // eax
  ADDRINFOW pHints; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pNodeName; // [rsp+70h] [rbp-90h]
  unsigned __int16 v11[64]; // [rsp+90h] [rbp-70h] BYREF

  memset(&pHints, 0, sizeof(pHints));
  memset_0(v11, 0, sizeof(v11));
  STRU::STRU((STRU *)v9, v11, 0x40u);
  v5 = STRU::Copy((STRU *)v9, a2);
  if ( v5 >= 0 )
  {
    pHints.ai_family = 0;
    pHints.ai_socktype = 1;
    pHints.ai_protocol = 6;
    pHints.ai_flags = 4;
    memset(&pHints.ai_addrlen, 0, 32);
    if ( GetAddrInfoW(pNodeName, L"80", &pHints, a3) )
    {
      Error = WSAGetLastError();
      if ( Error > 0 )
        Error = (unsigned __int16)Error | 0x80070000;
      v5 = Error;
    }
    else
    {
      v5 = 0;
    }
  }
  STRU::~STRU((STRU *)v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003ce8  mov     [rsp-8+arg_0], rbx
0x180003ced  mov     [rsp-8+arg_18], rdi
0x180003cf2  push    rbp
0x180003cf3  lea     rbp, [rsp-20h]
0x180003cf8  sub     rsp, 120h
0x180003cff  mov     rax, cs:__security_cookie
0x180003d06  xor     rax, rsp
0x180003d09  mov     [rbp+20h+var_10], rax
0x180003d0d  xorps   xmm0, xmm0
0x180003d10  lea     rcx, [rbp+20h+var_90]; void *
0x180003d14  mov     rdi, r8
0x180003d17  mov     rbx, rdx
0x180003d1a  xor     edx, edx; Val
0x180003d1c  mov     r8d, 80h; Size
0x180003d22  movups  xmmword ptr [rsp+120h+pHints.ai_flags], xmm0
0x180003d27  movups  xmmword ptr [rsp+120h+pHints.ai_addrlen], xmm0
0x180003d2c  movups  xmmword ptr [rsp+120h+pHints.ai_addr], xmm0
0x180003d31  call    memset_0
0x180003d36  mov     r8d, 40h ; '@'
0x180003d3c  lea     rdx, [rbp+20h+var_90]
0x180003d40  lea     rcx, [rsp+120h+var_D0]
0x180003d45  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003d4b  mov     rdx, rbx
0x180003d4e  lea     rcx, [rsp+120h+var_D0]
0x180003d53  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003d59  mov     ebx, eax
0x180003d5b  test    eax, eax
0x180003d5d  js      short loc_180003DBF
0x180003d5f  mov     rcx, [rsp+120h+pNodeName]; pNodeName
0x180003d64  lea     r8, [rsp+120h+pHints]; pHints
0x180003d69  xorps   xmm0, xmm0
0x180003d6c  lea     rdx, pServiceName; "80"
0x180003d73  movups  xmmword ptr [rsp+120h+pHints.ai_flags], xmm0
0x180003d78  mov     r9, rdi; ppResult
0x180003d7b  mov     [rsp+120h+pHints.ai_socktype], 1
0x180003d83  mov     [rsp+120h+pHints.ai_protocol], 6
0x180003d8b  mov     [rsp+120h+pHints.ai_flags], 4
0x180003d93  movups  xmmword ptr [rsp+120h+pHints.ai_addrlen], xmm0
0x180003d98  movups  xmmword ptr [rsp+120h+pHints.ai_addr], xmm0
0x180003d9d  call    cs:__imp_GetAddrInfoW
0x180003da3  test    eax, eax
0x180003da5  jz      short loc_180003DBD
0x180003da7  call    cs:__imp_WSAGetLastError
0x180003dad  test    eax, eax
0x180003daf  jle     short loc_180003DB9
0x180003db1  movzx   eax, ax
0x180003db4  or      eax, 80070000h
0x180003db9  mov     ebx, eax
0x180003dbb  jmp     short loc_180003DBF
0x180003dbd  xor     ebx, ebx
0x180003dbf  lea     rcx, [rsp+120h+var_D0]
0x180003dc4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003dca  mov     eax, ebx
0x180003dcc  mov     rcx, [rbp+20h+var_10]
0x180003dd0  xor     rcx, rsp; StackCookie
0x180003dd3  call    __security_check_cookie
0x180003dd8  lea     r11, [rsp+120h+var_s0]
0x180003de0  mov     rbx, [r11+10h]
0x180003de4  mov     rdi, [r11+28h]
0x180003de8  mov     rsp, r11
0x180003deb  pop     rbp
0x180003dec  retn
```
