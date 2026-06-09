# GetCanonicalName

- ea: `0x140092e5c`
- end: `0x1400931b1`
- name: `GetCanonicalName`
- size: `853`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140093644`

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
- `0x140042438`
- `0x140092e5c`
- `0x140113390`

## import_xrefs

- `WS2_32!GetAddrInfoExW` at `0x140092f81`
- `WS2_32!GetAddrInfoExW` at `0x140092f81`
- `WS2_32!FreeAddrInfoExW` at `0x140093178`
- `WS2_32!FreeAddrInfoExW` at `0x140093178`
- `WS2_32!__imp_WSAStartup` at `0x140092eca`
- `WS2_32!__imp_WSAStartup` at `0x140092eca`
- `WS2_32!__imp_WSACleanup` at `0x140093183`
- `WS2_32!__imp_WSACleanup` at `0x140093183`

## string_xrefs

- `0x140093132`: `StringCchCopy failed`

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
0x140092e5c  mov     [rsp-8+arg_10], rbx
0x140092e61  push    rbp
0x140092e62  push    rsi
0x140092e63  push    rdi
0x140092e64  push    r14
0x140092e66  push    r15
0x140092e68  lea     rbp, [rsp-160h]
0x140092e70  sub     rsp, 260h
0x140092e77  mov     rax, cs:__security_cookie
0x140092e7e  xor     rax, rsp
0x140092e81  mov     [rbp+180h+var_30], rax
0x140092e88  mov     r14, rdx
0x140092e8b  mov     rsi, rcx
0x140092e8e  xor     edx, edx; Val
0x140092e90  lea     rcx, [rbp+180h+WSAData]; void *
0x140092e94  mov     r8d, 198h; Size
0x140092e9a  call    memset_0
0x140092e9f  xor     edx, edx; Val
0x140092ea1  mov     [rsp+280h+pAddrInfoEx], 0
0x140092eaa  lea     rcx, [rsp+280h+var_220]; void *
0x140092eaf  lea     r8d, [rdx+48h]; Size
0x140092eb3  call    memset_0
0x140092eb8  mov     ecx, 202h; wVersionRequested
0x140092ebd  mov     [rsp+280h+var_228], 0
0x140092ec6  lea     rdx, [rbp+180h+WSAData]; lpWSAData
0x140092eca  call    cs:__imp_WSAStartup
0x140092ed0  mov     ebx, eax
0x140092ed2  test    eax, eax
0x140092ed4  jz      short loc_140092F29
0x140092ed6  xor     r15d, r15d
0x140092ed9  mov     rdx, cs:WPP_GLOBAL_Control
0x140092ee0  lea     rcx, WPP_GLOBAL_Control
0x140092ee7  cmp     rdx, rcx
0x140092eea  jz      short loc_140092F1F
0x140092eec  test    byte ptr [rdx+1Ch], 1
0x140092ef0  jz      short loc_140092F1F
0x140092ef2  cmp     byte ptr [rdx+19h], 2
0x140092ef6  jb      short loc_140092F1F
0x140092ef8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092efd  lea     edx, [r15+20h]
0x140092f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140092f08  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140092f0f  mov     r9d, eax
0x140092f12  mov     dword ptr [rsp+280h+hints], ebx
0x140092f16  mov     rcx, [rcx+10h]
0x140092f1a  call    WPP_SF_Dd
0x140092f1f  mov     ebx, 80004005h
0x140092f24  jmp     loc_14009316E
0x140092f29  movdqa  xmm0, cs:__xmm@00000006000000010000000000020002
0x140092f31  lea     rax, [rsp+280h+pAddrInfoEx]
0x140092f36  mov     [rsp+280h+lpHandle], 0; lpHandle
0x140092f3f  mov     r15d, 1
0x140092f45  mov     [rsp+280h+lpCompletionRoutine], 0; lpCompletionRoutine
0x140092f4e  xor     r9d, r9d; lpNspId
0x140092f51  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x140092f5a  xor     edx, edx; pServiceName
0x140092f5c  mov     [rsp+280h+timeout], 0; timeout
0x140092f65  mov     rcx, rsi; pName
0x140092f68  mov     [rsp+280h+ppResult], rax; ppResult
0x140092f6d  lea     r8d, [r15+0Bh]; dwNameSpace
0x140092f71  lea     rax, [rsp+280h+var_220]
0x140092f76  movdqa  xmmword ptr [rsp+280h+var_220.ai_flags], xmm0
0x140092f7c  mov     [rsp+280h+hints], rax; hints
0x140092f81  call    cs:__imp_GetAddrInfoExW
0x140092f87  mov     ebx, eax
0x140092f89  test    eax, eax
0x140092f8b  jz      short loc_140092FC6
0x140092f8d  mov     rdx, cs:WPP_GLOBAL_Control
0x140092f94  lea     rcx, WPP_GLOBAL_Control
0x140092f9b  cmp     rdx, rcx
0x140092f9e  jz      loc_140092F1F
0x140092fa4  test    [rdx+1Ch], r15b
0x140092fa8  jz      loc_140092F1F
0x140092fae  cmp     byte ptr [rdx+19h], 2
0x140092fb2  jb      loc_140092F1F
0x140092fb8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140092fbd  lea     edx, [r15+20h]
0x140092fc1  jmp     loc_140092F01
0x140092fc6  mov     rcx, [rsp+280h+pAddrInfoEx]
0x140092fcb  xor     edi, edi
0x140092fcd  xor     ebx, ebx
0x140092fcf  test    rcx, rcx
0x140092fd2  jz      loc_14009316B
0x140092fd8  mov     rdx, [rcx+18h]; String2
0x140092fdc  test    rdx, rdx
0x140092fdf  jz      loc_14009316B
0x140092fe5  mov     rcx, rsi; String1
0x140092fe8  call    _wcsicmp_0
0x140092fed  test    eax, eax
0x140092fef  jz      loc_14009316B
0x140092ff5  mov     rcx, [rsp+280h+pAddrInfoEx]
0x140092ffa  lea     r8, [rsp+280h+var_228]; unsigned __int64 *
0x140092fff  mov     edx, 104h; unsigned __int64
0x140093004  mov     rcx, [rcx+18h]; unsigned __int16 *
0x140093008  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14009300d  mov     ebx, eax
0x14009300f  test    eax, eax
0x140093011  jns     short loc_140093075
0x140093013  mov     rax, cs:WPP_GLOBAL_Control
0x14009301a  lea     rcx, WPP_GLOBAL_Control
0x140093021  cmp     rax, rcx
0x140093024  jz      loc_14009316E
0x14009302a  test    byte ptr [rax+1Ch], 8
0x14009302e  jz      loc_14009316E
0x140093034  cmp     byte ptr [rax+19h], 2
0x140093038  jb      loc_14009316E
0x14009303e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093043  lea     rcx, aStringcchlengt_0; "StringCchLength failed"
0x14009304a  mov     dword ptr [rsp+280h+ppResult], ebx
0x14009304e  mov     [rsp+280h+hints], rcx
0x140093053  lea     edx, [rdi+22h]
0x140093056  mov     rcx, cs:WPP_GLOBAL_Control
0x14009305d  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140093064  mov     r9d, eax
0x140093067  mov     rcx, [rcx+10h]
0x14009306b  call    WPP_SF_DsD
0x140093070  jmp     loc_14009316E
0x140093075  mov     rbx, [rsp+280h+var_228]
0x14009307a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140093081  inc     rbx
0x140093084  mov     eax, 2
0x140093089  mul     rbx
0x14009308c  cmovb   rax, rcx
0x140093090  mov     rcx, rax; Size
0x140093093  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140093098  mov     rdi, rax
0x14009309b  test    rax, rax
0x14009309e  jnz     short loc_1400930F4
0x1400930a0  mov     rax, cs:WPP_GLOBAL_Control
0x1400930a7  lea     rcx, WPP_GLOBAL_Control
0x1400930ae  cmp     rax, rcx
0x1400930b1  jz      short loc_1400930ED
0x1400930b3  test    byte ptr [rax+1Ch], 8
0x1400930b7  jz      short loc_1400930ED
0x1400930b9  cmp     byte ptr [rax+19h], 2
0x1400930bd  jb      short loc_1400930ED
0x1400930bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400930c4  lea     rcx, aWchar_0; "WCHAR[]"
0x1400930cb  mov     r9d, eax
0x1400930ce  mov     [rsp+280h+hints], rcx
0x1400930d3  lea     edx, [rdi+23h]
0x1400930d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400930dd  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x1400930e4  mov     rcx, [rcx+10h]
0x1400930e8  call    WPP_SF_Ds
0x1400930ed  mov     ebx, 8007000Eh
0x1400930f2  jmp     short loc_14009316E
0x1400930f4  mov     r8, [rsp+280h+pAddrInfoEx]
0x1400930f9  mov     rdx, rbx; unsigned __int64
0x1400930fc  mov     rcx, rdi; unsigned __int16 *
0x1400930ff  mov     r8, [r8+18h]; unsigned __int16 *
0x140093103  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140093108  mov     ebx, eax
0x14009310a  test    eax, eax
0x14009310c  jns     short loc_14009316B
0x14009310e  mov     rax, cs:WPP_GLOBAL_Control
0x140093115  lea     rcx, WPP_GLOBAL_Control
0x14009311c  cmp     rax, rcx
0x14009311f  jz      short loc_140093161
0x140093121  test    byte ptr [rax+1Ch], 8
0x140093125  jz      short loc_140093161
0x140093127  cmp     byte ptr [rax+19h], 2
0x14009312b  jb      short loc_140093161
0x14009312d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093132  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x140093139  mov     dword ptr [rsp+280h+ppResult], ebx
0x14009313d  mov     [rsp+280h+hints], rcx
0x140093142  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140093149  mov     rcx, cs:WPP_GLOBAL_Control
0x140093150  mov     edx, 24h ; '$'
0x140093155  mov     r9d, eax
0x140093158  mov     rcx, [rcx+10h]
0x14009315c  call    WPP_SF_DsD
0x140093161  mov     rcx, rdi; Block
0x140093164  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140093169  jmp     short loc_14009316E
0x14009316b  mov     [r14], rdi
0x14009316e  mov     rcx, [rsp+280h+pAddrInfoEx]; pAddrInfoEx
0x140093173  test    rcx, rcx
0x140093176  jz      short loc_14009317E
0x140093178  call    cs:__imp_FreeAddrInfoExW
0x14009317e  test    r15d, r15d
0x140093181  jz      short loc_140093189
0x140093183  call    cs:__imp_WSACleanup
0x140093189  mov     eax, ebx
0x14009318b  mov     rcx, [rbp+180h+var_30]
0x140093192  xor     rcx, rsp; StackCookie
0x140093195  call    __security_check_cookie
0x14009319a  mov     rbx, [rsp+280h+arg_10]
0x1400931a2  add     rsp, 260h
0x1400931a9  pop     r15
0x1400931ab  pop     r14
0x1400931ad  pop     rdi
0x1400931ae  pop     rsi
0x1400931af  pop     rbp
0x1400931b0  retn
```
