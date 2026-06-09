# GetCanonicalName

- ea: `0x140090cec`
- end: `0x140091041`
- name: `GetCanonicalName`
- size: `853`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400914d4`

## callees

- `0x140003b08`
- `0x140003b2c`
- `0x14000437c`
- `0x140004703`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x140040474`
- `0x140090cec`
- `0x140111220`

## import_xrefs

- `WS2_32!GetAddrInfoExW` at `0x140090e11`
- `WS2_32!GetAddrInfoExW` at `0x140090e11`
- `WS2_32!FreeAddrInfoExW` at `0x140091008`
- `WS2_32!FreeAddrInfoExW` at `0x140091008`
- `WS2_32!__imp_WSAStartup` at `0x140090d5a`
- `WS2_32!__imp_WSAStartup` at `0x140090d5a`
- `WS2_32!__imp_WSACleanup` at `0x140091013`
- `WS2_32!__imp_WSACleanup` at `0x140091013`

## string_xrefs

- `0x140090fc2`: `StringCchCopy failed`

## pseudocode

```c
__int64 __fastcall GetCanonicalName(wchar_t *String1, unsigned __int16 **a2)
{
  int AddrInfo; // ebx
  int v5; // r15d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  int v8; // ebx
  unsigned __int16 *v9; // rdi
  const wchar_t *ai_canonname; // rdx
  unsigned int v11; // eax
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  PADDRINFOEXW *ppResult; // [rsp+28h] [rbp-D8h]
  PADDRINFOEXW pAddrInfoEx; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v19; // [rsp+58h] [rbp-A8h] BYREF
  ADDRINFOEXW hints; // [rsp+60h] [rbp-A0h] BYREF
  struct WSAData WSAData; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  pAddrInfoEx = 0;
  memset_0(&hints, 0, sizeof(hints));
  v19 = 0;
  AddrInfo = WSAStartup(0x202u, &WSAData);
  if ( AddrInfo )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 32;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      CurrentThreadActivityIdPrefix,
      AddrInfo);
LABEL_7:
    v8 = -2147467259;
    goto LABEL_34;
  }
  v5 = 1;
  *(__m128i *)&hints.ai_flags = _mm_load_si128((const __m128i *)&_xmm);
  AddrInfo = GetAddrInfoExW(String1, 0, 0xCu, 0, &hints, &pAddrInfoEx, 0, 0, 0, 0);
  if ( AddrInfo )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 33;
    goto LABEL_6;
  }
  v9 = 0;
  v8 = 0;
  if ( !pAddrInfoEx )
    goto LABEL_33;
  ai_canonname = pAddrInfoEx->ai_canonname;
  if ( !ai_canonname || !wcsicmp_0(String1, ai_canonname) )
    goto LABEL_33;
  v8 = StringCchLengthW(pAddrInfoEx->ai_canonname, 0x104u, &v19);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(ppResult) = v8;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
        v11,
        (__int64)"StringCchLength failed",
        ppResult);
    }
    goto LABEL_34;
  }
  v12 = v19 + 1;
  v13 = (unsigned __int16 *)operator new(saturated_mul(v19 + 1, 2u));
  v9 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
        v14,
        (__int64)"WCHAR[]");
    }
    v8 = -2147024882;
    goto LABEL_34;
  }
  v8 = StringCchCopyW(v13, v12, pAddrInfoEx->ai_canonname);
  if ( v8 >= 0 )
  {
LABEL_33:
    *a2 = v9;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(ppResult) = v8;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      v15,
      (__int64)"StringCchCopy failed",
      ppResult);
  }
  operator delete(v9);
LABEL_34:
  if ( pAddrInfoEx )
    FreeAddrInfoExW(pAddrInfoEx);
  if ( v5 )
    WSACleanup();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140090cec  mov     [rsp-8+arg_10], rbx
0x140090cf1  push    rbp
0x140090cf2  push    rsi
0x140090cf3  push    rdi
0x140090cf4  push    r14
0x140090cf6  push    r15
0x140090cf8  lea     rbp, [rsp-160h]
0x140090d00  sub     rsp, 260h
0x140090d07  mov     rax, cs:__security_cookie
0x140090d0e  xor     rax, rsp
0x140090d11  mov     [rbp+180h+var_30], rax
0x140090d18  mov     r14, rdx
0x140090d1b  mov     rsi, rcx
0x140090d1e  xor     edx, edx; Val
0x140090d20  lea     rcx, [rbp+180h+WSAData]; void *
0x140090d24  mov     r8d, 198h; Size
0x140090d2a  call    memset_0
0x140090d2f  xor     edx, edx; Val
0x140090d31  mov     [rsp+280h+pAddrInfoEx], 0
0x140090d3a  lea     rcx, [rsp+280h+var_220]; void *
0x140090d3f  lea     r8d, [rdx+48h]; Size
0x140090d43  call    memset_0
0x140090d48  mov     ecx, 202h; wVersionRequested
0x140090d4d  mov     [rsp+280h+var_228], 0
0x140090d56  lea     rdx, [rbp+180h+WSAData]; lpWSAData
0x140090d5a  call    cs:__imp_WSAStartup
0x140090d60  mov     ebx, eax
0x140090d62  test    eax, eax
0x140090d64  jz      short loc_140090DB9
0x140090d66  xor     r15d, r15d
0x140090d69  mov     rdx, cs:WPP_GLOBAL_Control
0x140090d70  lea     rcx, WPP_GLOBAL_Control
0x140090d77  cmp     rdx, rcx
0x140090d7a  jz      short loc_140090DAF
0x140090d7c  test    byte ptr [rdx+1Ch], 1
0x140090d80  jz      short loc_140090DAF
0x140090d82  cmp     byte ptr [rdx+19h], 2
0x140090d86  jb      short loc_140090DAF
0x140090d88  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090d8d  lea     edx, [r15+20h]
0x140090d91  mov     rcx, cs:WPP_GLOBAL_Control
0x140090d98  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140090d9f  mov     r9d, eax
0x140090da2  mov     dword ptr [rsp+280h+hints], ebx
0x140090da6  mov     rcx, [rcx+10h]
0x140090daa  call    WPP_SF_Dd
0x140090daf  mov     ebx, 80004005h
0x140090db4  jmp     loc_140090FFE
0x140090db9  movdqa  xmm0, cs:__xmm@00000006000000010000000000020002
0x140090dc1  lea     rax, [rsp+280h+pAddrInfoEx]
0x140090dc6  mov     [rsp+280h+lpHandle], 0; lpHandle
0x140090dcf  mov     r15d, 1
0x140090dd5  mov     [rsp+280h+lpCompletionRoutine], 0; lpCompletionRoutine
0x140090dde  xor     r9d, r9d; lpNspId
0x140090de1  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x140090dea  xor     edx, edx; pServiceName
0x140090dec  mov     [rsp+280h+timeout], 0; timeout
0x140090df5  mov     rcx, rsi; pName
0x140090df8  mov     [rsp+280h+ppResult], rax; ppResult
0x140090dfd  lea     r8d, [r15+0Bh]; dwNameSpace
0x140090e01  lea     rax, [rsp+280h+var_220]
0x140090e06  movdqa  xmmword ptr [rsp+280h+var_220.ai_flags], xmm0
0x140090e0c  mov     [rsp+280h+hints], rax; hints
0x140090e11  call    cs:__imp_GetAddrInfoExW
0x140090e17  mov     ebx, eax
0x140090e19  test    eax, eax
0x140090e1b  jz      short loc_140090E56
0x140090e1d  mov     rdx, cs:WPP_GLOBAL_Control
0x140090e24  lea     rcx, WPP_GLOBAL_Control
0x140090e2b  cmp     rdx, rcx
0x140090e2e  jz      loc_140090DAF
0x140090e34  test    [rdx+1Ch], r15b
0x140090e38  jz      loc_140090DAF
0x140090e3e  cmp     byte ptr [rdx+19h], 2
0x140090e42  jb      loc_140090DAF
0x140090e48  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090e4d  lea     edx, [r15+20h]
0x140090e51  jmp     loc_140090D91
0x140090e56  mov     rcx, [rsp+280h+pAddrInfoEx]
0x140090e5b  xor     edi, edi
0x140090e5d  xor     ebx, ebx
0x140090e5f  test    rcx, rcx
0x140090e62  jz      loc_140090FFB
0x140090e68  mov     rdx, [rcx+18h]; String2
0x140090e6c  test    rdx, rdx
0x140090e6f  jz      loc_140090FFB
0x140090e75  mov     rcx, rsi; String1
0x140090e78  call    _wcsicmp_0
0x140090e7d  test    eax, eax
0x140090e7f  jz      loc_140090FFB
0x140090e85  mov     rcx, [rsp+280h+pAddrInfoEx]
0x140090e8a  lea     r8, [rsp+280h+var_228]; unsigned __int64 *
0x140090e8f  mov     edx, 104h; unsigned __int64
0x140090e94  mov     rcx, [rcx+18h]; unsigned __int16 *
0x140090e98  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140090e9d  mov     ebx, eax
0x140090e9f  test    eax, eax
0x140090ea1  jns     short loc_140090F05
0x140090ea3  mov     rax, cs:WPP_GLOBAL_Control
0x140090eaa  lea     rcx, WPP_GLOBAL_Control
0x140090eb1  cmp     rax, rcx
0x140090eb4  jz      loc_140090FFE
0x140090eba  test    byte ptr [rax+1Ch], 8
0x140090ebe  jz      loc_140090FFE
0x140090ec4  cmp     byte ptr [rax+19h], 2
0x140090ec8  jb      loc_140090FFE
0x140090ece  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090ed3  lea     rcx, aStringcchlengt_0; "StringCchLength failed"
0x140090eda  mov     dword ptr [rsp+280h+ppResult], ebx
0x140090ede  mov     [rsp+280h+hints], rcx
0x140090ee3  lea     edx, [rdi+22h]
0x140090ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x140090eed  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140090ef4  mov     r9d, eax
0x140090ef7  mov     rcx, [rcx+10h]
0x140090efb  call    WPP_SF_DsD
0x140090f00  jmp     loc_140090FFE
0x140090f05  mov     rbx, [rsp+280h+var_228]
0x140090f0a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140090f11  inc     rbx
0x140090f14  mov     eax, 2
0x140090f19  mul     rbx
0x140090f1c  cmovb   rax, rcx
0x140090f20  mov     rcx, rax; Size
0x140090f23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140090f28  mov     rdi, rax
0x140090f2b  test    rax, rax
0x140090f2e  jnz     short loc_140090F84
0x140090f30  mov     rax, cs:WPP_GLOBAL_Control
0x140090f37  lea     rcx, WPP_GLOBAL_Control
0x140090f3e  cmp     rax, rcx
0x140090f41  jz      short loc_140090F7D
0x140090f43  test    byte ptr [rax+1Ch], 8
0x140090f47  jz      short loc_140090F7D
0x140090f49  cmp     byte ptr [rax+19h], 2
0x140090f4d  jb      short loc_140090F7D
0x140090f4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090f54  lea     rcx, aWchar_0; "WCHAR[]"
0x140090f5b  mov     r9d, eax
0x140090f5e  mov     [rsp+280h+hints], rcx
0x140090f63  lea     edx, [rdi+23h]
0x140090f66  mov     rcx, cs:WPP_GLOBAL_Control
0x140090f6d  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140090f74  mov     rcx, [rcx+10h]
0x140090f78  call    WPP_SF_Ds
0x140090f7d  mov     ebx, 8007000Eh
0x140090f82  jmp     short loc_140090FFE
0x140090f84  mov     r8, [rsp+280h+pAddrInfoEx]
0x140090f89  mov     rdx, rbx; unsigned __int64
0x140090f8c  mov     rcx, rdi; unsigned __int16 *
0x140090f8f  mov     r8, [r8+18h]; unsigned __int16 *
0x140090f93  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140090f98  mov     ebx, eax
0x140090f9a  test    eax, eax
0x140090f9c  jns     short loc_140090FFB
0x140090f9e  mov     rax, cs:WPP_GLOBAL_Control
0x140090fa5  lea     rcx, WPP_GLOBAL_Control
0x140090fac  cmp     rax, rcx
0x140090faf  jz      short loc_140090FF1
0x140090fb1  test    byte ptr [rax+1Ch], 8
0x140090fb5  jz      short loc_140090FF1
0x140090fb7  cmp     byte ptr [rax+19h], 2
0x140090fbb  jb      short loc_140090FF1
0x140090fbd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140090fc2  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x140090fc9  mov     dword ptr [rsp+280h+ppResult], ebx
0x140090fcd  mov     [rsp+280h+hints], rcx
0x140090fd2  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140090fd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140090fe0  mov     edx, 24h ; '$'
0x140090fe5  mov     r9d, eax
0x140090fe8  mov     rcx, [rcx+10h]
0x140090fec  call    WPP_SF_DsD
0x140090ff1  mov     rcx, rdi; Block
0x140090ff4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140090ff9  jmp     short loc_140090FFE
0x140090ffb  mov     [r14], rdi
0x140090ffe  mov     rcx, [rsp+280h+pAddrInfoEx]; pAddrInfoEx
0x140091003  test    rcx, rcx
0x140091006  jz      short loc_14009100E
0x140091008  call    cs:__imp_FreeAddrInfoExW
0x14009100e  test    r15d, r15d
0x140091011  jz      short loc_140091019
0x140091013  call    cs:__imp_WSACleanup
0x140091019  mov     eax, ebx
0x14009101b  mov     rcx, [rbp+180h+var_30]
0x140091022  xor     rcx, rsp; StackCookie
0x140091025  call    __security_check_cookie
0x14009102a  mov     rbx, [rsp+280h+arg_10]
0x140091032  add     rsp, 260h
0x140091039  pop     r15
0x14009103b  pop     r14
0x14009103d  pop     rdi
0x14009103e  pop     rsi
0x14009103f  pop     rbp
0x140091040  retn
```
