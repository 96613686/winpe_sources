# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000420c`
- end: `0x1800044da`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004688`

## callees

- `0x18000327c`
- `0x18000397c`
- `0x18000420c`
- `0x180005afc`
- `0x180006030`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004340`
- `msvcrt!wcsncpy_s` at `0x180004340`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004376`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004376`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000429d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000428b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000428b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004461`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800042d0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004301`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000440a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004434`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800042d0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004301`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000440a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004434`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004395`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180004395`

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
0x18000420c  mov     [rsp+arg_8], rbx
0x180004211  mov     [rsp+arg_18], rbp
0x180004216  push    rsi
0x180004217  push    rdi
0x180004218  push    r12
0x18000421a  push    r14
0x18000421c  push    r15
0x18000421e  sub     rsp, 80h
0x180004225  mov     rax, cs:__security_cookie
0x18000422c  xor     rax, rsp
0x18000422f  mov     [rsp+0A8h+var_38], rax
0x180004234  xor     r12d, r12d
0x180004237  mov     r15, r8
0x18000423a  mov     rbx, rdx
0x18000423d  mov     r14, rcx
0x180004240  test    rdx, rdx
0x180004243  jz      loc_180004480
0x180004249  test    r8, r8
0x18000424c  jz      loc_180004480
0x180004252  mov     [r8], r12
0x180004255  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004259  inc     rax
0x18000425c  cmp     [rdx+rax*2], r12w
0x180004261  jnz     short loc_180004259
0x180004263  add     eax, eax
0x180004265  mov     [rsp+0A8h+var_88], r12d
0x18000426a  cmp     eax, 64h ; 'd'
0x18000426d  mov     ecx, 3E8h
0x180004272  cmovl   eax, ecx
0x180004275  mov     ecx, eax
0x180004277  mov     [rsp+0A8h+var_84], eax
0x18000427b  add     rcx, rcx
0x18000427e  mov     eax, 0FFFFFFFFh
0x180004283  cmp     rcx, rax
0x180004286  jbe     short loc_18000429B
0x180004288  mov     rcx, r12; pv
0x18000428b  call    cs:__imp_CoTaskMemFree
0x180004291  mov     eax, 8007000Eh
0x180004296  jmp     loc_180004485
0x18000429b  mov     ecx, ecx; cb
0x18000429d  call    cs:__imp_CoTaskMemAlloc
0x1800042a3  mov     [rsp+0A8h+pv], rax
0x1800042a8  mov     rcx, rax
0x1800042ab  test    rax, rax
0x1800042ae  jz      short loc_18000428B
0x1800042b0  mov     [rax], r12w
0x1800042b4  mov     [r14], rbx
0x1800042b7  movzx   eax, word ptr [rbx]
0x1800042ba  test    ax, ax
0x1800042bd  jz      loc_180004451
0x1800042c3  cmp     ax, 25h ; '%'
0x1800042c7  jnz     loc_18000441A
0x1800042cd  mov     rcx, rbx; lpsz
0x1800042d0  call    cs:__imp_CharNextW
0x1800042d6  mov     [r14], rax
0x1800042d9  movzx   ecx, word ptr [rax]
0x1800042dc  cmp     cx, 25h ; '%'
0x1800042e0  jnz     short loc_1800042EA
0x1800042e2  mov     rdx, rax
0x1800042e5  jmp     loc_18000441D
0x1800042ea  test    rax, rax
0x1800042ed  jz      loc_180004472
0x1800042f3  mov     rdi, r12
0x1800042f6  jmp     short loc_18000430A
0x1800042f8  cmp     cx, 25h ; '%'
0x1800042fc  jz      short loc_180004311
0x1800042fe  mov     rcx, rax; lpsz
0x180004301  call    cs:__imp_CharNextW
0x180004307  movzx   ecx, word ptr [rax]
0x18000430a  test    cx, cx
0x18000430d  jnz     short loc_1800042F8
0x18000430f  jmp     short loc_180004314
0x180004311  mov     rdi, rax
0x180004314  test    rdi, rdi
0x180004317  jz      loc_180004472
0x18000431d  mov     rax, rdi
0x180004320  sub     rax, [r14]
0x180004323  sar     rax, 1
0x180004326  cmp     rax, 1Fh
0x18000432a  jg      loc_18000446B
0x180004330  mov     r8, [r14]; Source
0x180004333  lea     rcx, [rsp+0A8h+Destination]; Destination
0x180004338  movsxd  r9, eax; MaxCount
0x18000433b  mov     edx, 20h ; ' '; SizeInWords
0x180004340  call    cs:__imp_wcsncpy_s
0x180004346  test    eax, eax
0x180004348  jz      short loc_18000436E
0x18000434a  cmp     eax, 0Ch
0x18000434d  jz      loc_1800044CF
0x180004353  cmp     eax, 16h
0x180004356  jz      loc_1800044C4
0x18000435c  cmp     eax, 22h ; '"'
0x18000435f  jz      loc_1800044C4
0x180004365  cmp     eax, 50h ; 'P'
0x180004368  jnz     loc_1800044B9
0x18000436e  mov     rsi, [r14+8]
0x180004372  lea     rcx, [rsi+20h]; lpCriticalSection
0x180004376  call    cs:__imp_EnterCriticalSection
0x18000437c  mov     ebx, r12d
0x18000437f  cmp     [rsi+18h], r12d
0x180004383  jle     short loc_1800043A6
0x180004385  mov     rcx, [rsi+8]
0x180004389  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x18000438e  movsxd  rax, ebx
0x180004391  mov     rcx, [rcx+rax*8]; lpString1
0x180004395  call    cs:__imp_lstrcmpiW
0x18000439b  test    eax, eax
0x18000439d  jz      short loc_1800043E4
0x18000439f  inc     ebx
0x1800043a1  cmp     ebx, [rsi+18h]
0x1800043a4  jl      short loc_180004385
0x1800043a6  mov     rbx, r12
0x1800043a9  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800043ad  call    cs:__imp_LeaveCriticalSection
0x1800043b3  test    rbx, rbx
0x1800043b6  jz      loc_180004472
0x1800043bc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800043c0  inc     r8; int
0x1800043c3  cmp     [rbx+r8*2], r12w
0x1800043c8  jnz     short loc_1800043C0
0x1800043ca  mov     rdx, rbx; unsigned __int16 *
0x1800043cd  lea     rcx, [rsp+0A8h+var_88]; this
0x1800043d2  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800043d7  test    eax, eax
0x1800043d9  jz      loc_180004479
0x1800043df  mov     rax, [r14]
0x1800043e2  jmp     short loc_180004413
0x1800043e4  cmp     ebx, 0FFFFFFFFh
0x1800043e7  jz      short loc_1800043A6
0x1800043e9  test    ebx, ebx
0x1800043eb  js      loc_1800044AE
0x1800043f1  cmp     ebx, [rsi+18h]
0x1800043f4  jge     loc_1800044AE
0x1800043fa  mov     rax, [rsi+10h]
0x1800043fe  movsxd  rcx, ebx
0x180004401  mov     rbx, [rax+rcx*8]
0x180004405  jmp     short loc_1800043A9
0x180004407  mov     rcx, rax; lpsz
0x18000440a  call    cs:__imp_CharNextW
0x180004410  mov     [r14], rax
0x180004413  cmp     rax, rdi
0x180004416  jnz     short loc_180004407
0x180004418  jmp     short loc_180004431
0x18000441a  mov     rdx, rbx; unsigned __int16 *
0x18000441d  mov     r8d, 1; int
0x180004423  lea     rcx, [rsp+0A8h+var_88]; this
0x180004428  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000442d  test    eax, eax
0x18000442f  jz      short loc_180004479
0x180004431  mov     rcx, [r14]; lpsz
0x180004434  call    cs:__imp_CharNextW
0x18000443a  mov     rbx, rax
0x18000443d  mov     [r14], rax
0x180004440  movzx   eax, word ptr [rax]
0x180004443  test    ax, ax
0x180004446  jnz     loc_1800042C3
0x18000444c  mov     rcx, [rsp+0A8h+pv]
0x180004451  mov     ebx, r12d
0x180004454  mov     [rsp+0A8h+pv], r12
0x180004459  mov     [r15], rcx
0x18000445c  mov     rcx, [rsp+0A8h+pv]; pv
0x180004461  call    cs:__imp_CoTaskMemFree
0x180004467  mov     eax, ebx
0x180004469  jmp     short loc_180004485
0x18000446b  mov     ebx, 80004005h
0x180004470  jmp     short loc_18000445C
0x180004472  mov     ebx, 80020009h
0x180004477  jmp     short loc_18000445C
0x180004479  mov     ebx, 8007000Eh
0x18000447e  jmp     short loc_18000445C
0x180004480  mov     eax, 80004003h
0x180004485  mov     rcx, [rsp+0A8h+var_38]
0x18000448a  xor     rcx, rsp; StackCookie
0x18000448d  call    __security_check_cookie
0x180004492  lea     r11, [rsp+0A8h+var_28]
0x18000449a  mov     rbx, [r11+38h]
0x18000449e  mov     rbp, [r11+48h]
0x1800044a2  mov     rsp, r11
0x1800044a5  pop     r15
0x1800044a7  pop     r14
0x1800044a9  pop     r12
0x1800044ab  pop     rdi
0x1800044ac  pop     rsi
0x1800044ad  retn
0x1800044ae  mov     ecx, 0C000008Ch; unsigned int
0x1800044b3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800044b8  int     3; Trap to Debugger
0x1800044b9  mov     ecx, 80004005h; int
0x1800044be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800044c4  mov     ecx, 80070057h; int
0x1800044c9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800044cf  mov     ecx, 8007000Eh; int
0x1800044d4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
