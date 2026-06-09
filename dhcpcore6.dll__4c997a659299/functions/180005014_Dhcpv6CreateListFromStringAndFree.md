# Dhcpv6CreateListFromStringAndFree

- ea: `0x180005014`
- end: `0x1800051f8`
- name: `Dhcpv6CreateListFromStringAndFree`
- size: `484`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d78`

## callees

- `0x180005014`
- `0x180007564`
- `0x18000c740`
- `0x180019ad0`
- `0x18001e060`
- `0x180027bf0`
- `0x1800337d0`

## import_xrefs

- `WS2_32!getaddrinfo` at `0x18000514a`
- `WS2_32!getaddrinfo` at `0x18000514a`

## pseudocode

```c
char *__fastcall Dhcpv6CreateListFromStringAndFree(PCWSTR SourceString, __int64 a2, _DWORD *a3)
{
  const WCHAR *v4; // rdi
  char *result; // rax
  __int64 v6; // rax
  PCWSTR v7; // rbx
  unsigned int v8; // esi
  _WORD *v9; // rax
  char *v10; // rbx
  int v11; // r14d
  unsigned int v12; // r15d
  const CHAR *v13; // rax
  PADDRINFOA v14; // rax
  __int64 v15; // rax
  PADDRINFOA ppResult; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  ADDRINFOA pHints; // [rsp+38h] [rbp-C8h] BYREF
  CHAR v20[1008]; // [rsp+70h] [rbp-90h] BYREF

  v17 = (LPVOID)SourceString;
  ppResult = 0;
  *a3 = 0;
  v4 = SourceString;
  memset(&pHints, 0, sizeof(pHints));
  if ( !SourceString )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( SourceString[v6] );
  v7 = SourceString;
  v8 = v6 != 0;
  while ( x_wcschr(v7) )
  {
    v9 = (_WORD *)x_wcschr(v7);
    if ( !v9 )
      goto LABEL_12;
    v7 = v9 + 1;
    *v9 = 0;
    ++v8;
  }
  if ( !v8 )
  {
    DhcpFree(&v17);
    return 0;
  }
  v18 = DhcpAlloc(16 * v8);
  v10 = (char *)v18;
  if ( !v18 )
  {
LABEL_12:
    v11 = 0;
LABEL_24:
    v10 = 0;
    goto LABEL_25;
  }
  v11 = 0;
  v12 = 0;
  *(__m128i *)&pHints.ai_flags = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    v13 = Dhcpv6UnicodeToOem(v4, v20);
    if ( v13 )
    {
      if ( !getaddrinfo(v13, 0, &pHints, &ppResult) )
      {
        ++v11;
        *(_OWORD *)&v10[16 * v12] = *(_OWORD *)&ppResult->ai_addr->sa_data[6];
        v14 = ppResult;
        *(_OWORD *)&ppResult->ai_flags = 0;
        *(_OWORD *)&v14->ai_addrlen = 0;
        *(_OWORD *)&v14->ai_addr = 0;
      }
    }
    else if ( (xmmword_1800423E0 & 2) != 0 )
    {
      WPP_SF_S(1025, 12, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, v4);
    }
    v15 = -1;
    do
      ++v15;
    while ( v4[v15] );
    ++v12;
    v4 += v15 + 1;
  }
  while ( v12 < v8 );
  if ( !v11 )
  {
    DhcpFree((LPVOID *)&v18);
    goto LABEL_24;
  }
LABEL_25:
  DhcpFree(&v17);
  result = v10;
  *a3 = v11;
  return result;
}

```

## disassembly

```asm
0x180005014  mov     [rsp-8+arg_8], rbx
0x180005019  push    rbp
0x18000501a  push    rsi
0x18000501b  push    rdi
0x18000501c  push    r12
0x18000501e  push    r13
0x180005020  push    r14
0x180005022  push    r15
0x180005024  lea     rbp, [rsp-370h]
0x18000502c  sub     rsp, 470h
0x180005033  mov     rax, cs:__security_cookie
0x18000503a  xor     rax, rsp
0x18000503d  mov     [rbp+3A0h+var_40], rax
0x180005044  xor     r13d, r13d
0x180005047  mov     [rsp+4A0h+var_478], rcx
0x18000504c  mov     [rsp+4A0h+ppResult], r13
0x180005051  xorps   xmm0, xmm0
0x180005054  mov     [r8], r13d
0x180005057  mov     r12, r8
0x18000505a  mov     rdi, rcx
0x18000505d  movups  xmmword ptr [rsp+4A0h+pHints.ai_flags], xmm0
0x180005062  movups  xmmword ptr [rsp+4A0h+pHints.ai_addrlen], xmm0
0x180005067  movups  xmmword ptr [rsp+4A0h+pHints.ai_addr], xmm0
0x18000506c  test    rcx, rcx
0x18000506f  jnz     short loc_180005078
0x180005071  xor     eax, eax
0x180005073  jmp     loc_1800051CD
0x180005078  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000507c  inc     rax
0x18000507f  cmp     [rcx+rax*2], r13w
0x180005084  jnz     short loc_18000507C
0x180005086  test    rax, rax
0x180005089  mov     esi, r13d
0x18000508c  mov     rbx, rcx
0x18000508f  setnz   sil
0x180005093  mov     rcx, rbx
0x180005096  call    x_wcschr
0x18000509b  test    rax, rax
0x18000509e  jz      short loc_1800050BC
0x1800050a0  mov     rcx, rbx
0x1800050a3  call    x_wcschr
0x1800050a8  mov     rbx, rax
0x1800050ab  test    rax, rax
0x1800050ae  jz      short loc_1800050E3
0x1800050b0  add     rbx, 2
0x1800050b4  mov     [rax], r13w
0x1800050b8  inc     esi
0x1800050ba  jmp     short loc_180005093
0x1800050bc  test    esi, esi
0x1800050be  jnz     short loc_1800050CC
0x1800050c0  lea     rcx, [rsp+4A0h+var_478]
0x1800050c5  call    DhcpFree
0x1800050ca  jmp     short loc_180005071
0x1800050cc  mov     ecx, esi
0x1800050ce  shl     ecx, 4
0x1800050d1  call    DhcpAlloc
0x1800050d6  mov     [rsp+4A0h+var_470], rax
0x1800050db  mov     rbx, rax
0x1800050de  test    rax, rax
0x1800050e1  jnz     short loc_1800050EB
0x1800050e3  mov     r14d, r13d
0x1800050e6  jmp     loc_1800051B9
0x1800050eb  movdqa  xmm0, cs:__xmm@00000011000000020000001700000004
0x1800050f3  mov     r14d, r13d
0x1800050f6  mov     r15d, r13d
0x1800050f9  movdqu  xmmword ptr [rsp+4A0h+pHints.ai_flags], xmm0
0x1800050ff  test    esi, esi
0x180005101  jz      loc_1800051AF
0x180005107  lea     rdx, [rsp+4A0h+var_430]
0x18000510c  mov     rcx, rdi; SourceString
0x18000510f  call    Dhcpv6UnicodeToOem
0x180005114  test    rax, rax
0x180005117  jnz     short loc_18000513B
0x180005119  test    byte ptr cs:xmmword_1800423E0, 2
0x180005120  jz      short loc_180005188
0x180005122  lea     edx, [rax+0Ch]
0x180005125  mov     ecx, 401h
0x18000512a  mov     r9, rdi
0x18000512d  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180005134  call    WPP_SF_S
0x180005139  jmp     short loc_180005188
0x18000513b  lea     r9, [rsp+4A0h+ppResult]; ppResult
0x180005140  xor     edx, edx; pServiceName
0x180005142  lea     r8, [rsp+4A0h+pHints]; pHints
0x180005147  mov     rcx, rax; pNodeName
0x18000514a  call    cs:__imp_getaddrinfo
0x180005151  nop     dword ptr [rax+rax+00h]
0x180005156  test    eax, eax
0x180005158  jnz     short loc_180005188
0x18000515a  mov     rax, [rsp+4A0h+ppResult]
0x18000515f  xorps   xmm1, xmm1
0x180005162  mov     rdx, [rax+20h]
0x180005166  mov     eax, r15d
0x180005169  shl     eax, 4
0x18000516c  inc     r14d
0x18000516f  movups  xmm0, xmmword ptr [rdx+8]
0x180005173  movdqu  xmmword ptr [rax+rbx], xmm0
0x180005178  mov     rax, [rsp+4A0h+ppResult]
0x18000517d  movups  xmmword ptr [rax], xmm1
0x180005180  movups  xmmword ptr [rax+10h], xmm1
0x180005184  movups  xmmword ptr [rax+20h], xmm1
0x180005188  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000518c  inc     rax
0x18000518f  cmp     [rdi+rax*2], r13w
0x180005194  jnz     short loc_18000518C
0x180005196  lea     rdi, [rdi+rax*2]
0x18000519a  inc     r15d
0x18000519d  add     rdi, 2
0x1800051a1  cmp     r15d, esi
0x1800051a4  jb      loc_180005107
0x1800051aa  test    r14d, r14d
0x1800051ad  jnz     short loc_1800051BC
0x1800051af  lea     rcx, [rsp+4A0h+var_470]
0x1800051b4  call    DhcpFree
0x1800051b9  mov     rbx, r13
0x1800051bc  lea     rcx, [rsp+4A0h+var_478]
0x1800051c1  call    DhcpFree
0x1800051c6  mov     rax, rbx
0x1800051c9  mov     [r12], r14d
0x1800051cd  mov     rcx, [rbp+3A0h+var_40]
0x1800051d4  xor     rcx, rsp; StackCookie
0x1800051d7  call    __security_check_cookie
0x1800051dc  mov     rbx, [rsp+4A0h+arg_8]
0x1800051e4  add     rsp, 470h
0x1800051eb  pop     r15
0x1800051ed  pop     r14
0x1800051ef  pop     r13
0x1800051f1  pop     r12
0x1800051f3  pop     rdi
0x1800051f4  pop     rsi
0x1800051f5  pop     rbp
0x1800051f6  retn
```
