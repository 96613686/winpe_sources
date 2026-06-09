# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000326c`
- end: `0x18000353a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800036e8`

## callees

- `0x18000298c`
- `0x180002ac4`
- `0x18000326c`
- `0x1800046fc`
- `0x180018500`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800033a0`
- `msvcrt!wcsncpy_s` at `0x1800033a0`
- `USER32!CharNextW` at `0x180003330`
- `USER32!CharNextW` at `0x180003361`
- `USER32!CharNextW` at `0x18000346a`
- `USER32!CharNextW` at `0x180003494`
- `USER32!CharNextW` at `0x180003330`
- `USER32!CharNextW` at `0x180003361`
- `USER32!CharNextW` at `0x18000346a`
- `USER32!CharNextW` at `0x180003494`
- `ole32!CoTaskMemFree` at `0x1800032eb`
- `ole32!CoTaskMemFree` at `0x1800034c1`
- `ole32!CoTaskMemFree` at `0x1800032eb`
- `ole32!CoTaskMemFree` at `0x1800034c1`
- `ole32!CoTaskMemAlloc` at `0x1800032fd`
- `ole32!CoTaskMemAlloc` at `0x1800032fd`
- `KERNEL32!lstrcmpiW` at `0x1800033f5`
- `KERNEL32!lstrcmpiW` at `0x1800033f5`
- `KERNEL32!LeaveCriticalSection` at `0x18000340d`
- `KERNEL32!LeaveCriticalSection` at `0x18000340d`
- `KERNEL32!EnterCriticalSection` at `0x1800033d6`
- `KERNEL32!EnterCriticalSection` at `0x1800033d6`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_49:
    v25 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_53;
LABEL_47:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_49;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_46;
  }
  if ( !v13 )
    goto LABEL_52;
  v16 = 0;
  while ( v14 )
  {
    if ( v14 == 37 )
    {
      v16 = v13;
      break;
    }
    v13 = CharNextW(v13);
    v14 = *v13;
  }
  if ( !v16 )
    goto LABEL_52;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_50;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_32;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_32;
  }
  if ( v20 == -1 )
  {
LABEL_32:
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_52:
    v25 = -2147352567;
    goto LABEL_50;
  }
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v25 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x18000326c  mov     [rsp+arg_8], rbx
0x180003271  mov     [rsp+arg_18], rbp
0x180003276  push    rsi
0x180003277  push    rdi
0x180003278  push    r12
0x18000327a  push    r14
0x18000327c  push    r15
0x18000327e  sub     rsp, 80h
0x180003285  mov     rax, cs:__security_cookie
0x18000328c  xor     rax, rsp
0x18000328f  mov     [rsp+0A8h+var_38], rax
0x180003294  xor     r12d, r12d
0x180003297  mov     r15, r8
0x18000329a  mov     rbx, rdx
0x18000329d  mov     r14, rcx
0x1800032a0  test    rdx, rdx
0x1800032a3  jz      loc_1800034E0
0x1800032a9  test    r8, r8
0x1800032ac  jz      loc_1800034E0
0x1800032b2  mov     [r8], r12
0x1800032b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800032b9  inc     rax
0x1800032bc  cmp     [rdx+rax*2], r12w
0x1800032c1  jnz     short loc_1800032B9
0x1800032c3  add     eax, eax
0x1800032c5  mov     [rsp+0A8h+var_88], r12d
0x1800032ca  cmp     eax, 64h ; 'd'
0x1800032cd  mov     ecx, 3E8h
0x1800032d2  cmovl   eax, ecx
0x1800032d5  mov     ecx, eax
0x1800032d7  mov     [rsp+0A8h+var_84], eax
0x1800032db  add     rcx, rcx
0x1800032de  mov     eax, 0FFFFFFFFh
0x1800032e3  cmp     rcx, rax
0x1800032e6  jbe     short loc_1800032FB
0x1800032e8  mov     rcx, r12; pv
0x1800032eb  call    cs:__imp_CoTaskMemFree
0x1800032f1  mov     eax, 8007000Eh
0x1800032f6  jmp     loc_1800034E5
0x1800032fb  mov     ecx, ecx; cb
0x1800032fd  call    cs:__imp_CoTaskMemAlloc
0x180003303  mov     [rsp+0A8h+pv], rax
0x180003308  mov     rcx, rax
0x18000330b  test    rax, rax
0x18000330e  jz      short loc_1800032EB
0x180003310  mov     [rax], r12w
0x180003314  mov     [r14], rbx
0x180003317  movzx   eax, word ptr [rbx]
0x18000331a  test    ax, ax
0x18000331d  jz      loc_1800034B1
0x180003323  cmp     ax, 25h ; '%'
0x180003327  jnz     loc_18000347A
0x18000332d  mov     rcx, rbx; lpsz
0x180003330  call    cs:__imp_CharNextW
0x180003336  mov     [r14], rax
0x180003339  movzx   ecx, word ptr [rax]
0x18000333c  cmp     cx, 25h ; '%'
0x180003340  jnz     short loc_18000334A
0x180003342  mov     rdx, rax
0x180003345  jmp     loc_18000347D
0x18000334a  test    rax, rax
0x18000334d  jz      loc_1800034D2
0x180003353  mov     rdi, r12
0x180003356  jmp     short loc_18000336A
0x180003358  cmp     cx, 25h ; '%'
0x18000335c  jz      short loc_180003371
0x18000335e  mov     rcx, rax; lpsz
0x180003361  call    cs:__imp_CharNextW
0x180003367  movzx   ecx, word ptr [rax]
0x18000336a  test    cx, cx
0x18000336d  jnz     short loc_180003358
0x18000336f  jmp     short loc_180003374
0x180003371  mov     rdi, rax
0x180003374  test    rdi, rdi
0x180003377  jz      loc_1800034D2
0x18000337d  mov     rax, rdi
0x180003380  sub     rax, [r14]
0x180003383  sar     rax, 1
0x180003386  cmp     rax, 1Fh
0x18000338a  jg      loc_1800034CB
0x180003390  mov     r8, [r14]; Source
0x180003393  lea     rcx, [rsp+0A8h+Destination]; Destination
0x180003398  movsxd  r9, eax; MaxCount
0x18000339b  mov     edx, 20h ; ' '; SizeInWords
0x1800033a0  call    cs:__imp_wcsncpy_s
0x1800033a6  test    eax, eax
0x1800033a8  jz      short loc_1800033CE
0x1800033aa  cmp     eax, 0Ch
0x1800033ad  jz      loc_18000352F
0x1800033b3  cmp     eax, 16h
0x1800033b6  jz      loc_180003524
0x1800033bc  cmp     eax, 22h ; '"'
0x1800033bf  jz      loc_180003524
0x1800033c5  cmp     eax, 50h ; 'P'
0x1800033c8  jnz     loc_180003519
0x1800033ce  mov     rsi, [r14+8]
0x1800033d2  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800033d6  call    cs:__imp_EnterCriticalSection
0x1800033dc  mov     ebx, r12d
0x1800033df  cmp     [rsi+18h], r12d
0x1800033e3  jle     short loc_180003406
0x1800033e5  mov     rcx, [rsi+8]
0x1800033e9  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x1800033ee  movsxd  rax, ebx
0x1800033f1  mov     rcx, [rcx+rax*8]; lpString1
0x1800033f5  call    cs:__imp_lstrcmpiW
0x1800033fb  test    eax, eax
0x1800033fd  jz      short loc_180003444
0x1800033ff  inc     ebx
0x180003401  cmp     ebx, [rsi+18h]
0x180003404  jl      short loc_1800033E5
0x180003406  mov     rbx, r12
0x180003409  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000340d  call    cs:__imp_LeaveCriticalSection
0x180003413  test    rbx, rbx
0x180003416  jz      loc_1800034D2
0x18000341c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003420  inc     r8; int
0x180003423  cmp     [rbx+r8*2], r12w
0x180003428  jnz     short loc_180003420
0x18000342a  mov     rdx, rbx; unsigned __int16 *
0x18000342d  lea     rcx, [rsp+0A8h+var_88]; this
0x180003432  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003437  test    eax, eax
0x180003439  jz      loc_1800034D9
0x18000343f  mov     rax, [r14]
0x180003442  jmp     short loc_180003473
0x180003444  cmp     ebx, 0FFFFFFFFh
0x180003447  jz      short loc_180003406
0x180003449  test    ebx, ebx
0x18000344b  js      loc_18000350E
0x180003451  cmp     ebx, [rsi+18h]
0x180003454  jge     loc_18000350E
0x18000345a  mov     rax, [rsi+10h]
0x18000345e  movsxd  rcx, ebx
0x180003461  mov     rbx, [rax+rcx*8]
0x180003465  jmp     short loc_180003409
0x180003467  mov     rcx, rax; lpsz
0x18000346a  call    cs:__imp_CharNextW
0x180003470  mov     [r14], rax
0x180003473  cmp     rax, rdi
0x180003476  jnz     short loc_180003467
0x180003478  jmp     short loc_180003491
0x18000347a  mov     rdx, rbx; unsigned __int16 *
0x18000347d  mov     r8d, 1; int
0x180003483  lea     rcx, [rsp+0A8h+var_88]; this
0x180003488  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000348d  test    eax, eax
0x18000348f  jz      short loc_1800034D9
0x180003491  mov     rcx, [r14]; lpsz
0x180003494  call    cs:__imp_CharNextW
0x18000349a  mov     rbx, rax
0x18000349d  mov     [r14], rax
0x1800034a0  movzx   eax, word ptr [rax]
0x1800034a3  test    ax, ax
0x1800034a6  jnz     loc_180003323
0x1800034ac  mov     rcx, [rsp+0A8h+pv]
0x1800034b1  mov     ebx, r12d
0x1800034b4  mov     [rsp+0A8h+pv], r12
0x1800034b9  mov     [r15], rcx
0x1800034bc  mov     rcx, [rsp+0A8h+pv]; pv
0x1800034c1  call    cs:__imp_CoTaskMemFree
0x1800034c7  mov     eax, ebx
0x1800034c9  jmp     short loc_1800034E5
0x1800034cb  mov     ebx, 80004005h
0x1800034d0  jmp     short loc_1800034BC
0x1800034d2  mov     ebx, 80020009h
0x1800034d7  jmp     short loc_1800034BC
0x1800034d9  mov     ebx, 8007000Eh
0x1800034de  jmp     short loc_1800034BC
0x1800034e0  mov     eax, 80004003h
0x1800034e5  mov     rcx, [rsp+0A8h+var_38]
0x1800034ea  xor     rcx, rsp; StackCookie
0x1800034ed  call    __security_check_cookie
0x1800034f2  lea     r11, [rsp+0A8h+var_28]
0x1800034fa  mov     rbx, [r11+38h]
0x1800034fe  mov     rbp, [r11+48h]
0x180003502  mov     rsp, r11
0x180003505  pop     r15
0x180003507  pop     r14
0x180003509  pop     r12
0x18000350b  pop     rdi
0x18000350c  pop     rsi
0x18000350d  retn
0x18000350e  mov     ecx, 0C000008Ch; unsigned int
0x180003513  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003518  int     3; Trap to Debugger
0x180003519  mov     ecx, 80004005h; int
0x18000351e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003524  mov     ecx, 80070057h; int
0x180003529  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000352f  mov     ecx, 8007000Eh; int
0x180003534  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
