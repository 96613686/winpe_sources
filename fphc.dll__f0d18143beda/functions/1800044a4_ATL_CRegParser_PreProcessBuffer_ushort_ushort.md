# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800044a4`
- end: `0x18000477f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800048f8`

## callees

- `0x1800036bc`
- `0x180004048`
- `0x1800044a4`
- `0x180005950`
- `0x180011340`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800045e7`
- `msvcrt!wcsncpy_s` at `0x1800045e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000454c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000454c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000452e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000452e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004578`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800046b4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800046dd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004578`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800045a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800046b4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800046dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000463b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000463b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004653`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004653`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000461d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000461d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
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
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  v26[0] = 0;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v25 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
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
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_52;
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
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
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
LABEL_54:
    v25 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v25 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x1800044a4  mov     [rsp-8+arg_8], rbx
0x1800044a9  push    rbp
0x1800044aa  push    rsi
0x1800044ab  push    rdi
0x1800044ac  push    r12
0x1800044ae  push    r13
0x1800044b0  push    r14
0x1800044b2  push    r15
0x1800044b4  lea     rbp, [rsp-27h]
0x1800044b9  sub     rsp, 90h
0x1800044c0  mov     rax, cs:__security_cookie
0x1800044c7  xor     rax, rsp
0x1800044ca  mov     [rbp+57h+var_40], rax
0x1800044ce  mov     r12, r8
0x1800044d1  mov     rbx, rdx
0x1800044d4  mov     r14, rcx
0x1800044d7  xor     r13d, r13d
0x1800044da  test    rdx, rdx
0x1800044dd  jz      loc_180004727
0x1800044e3  test    r8, r8
0x1800044e6  jz      loc_180004727
0x1800044ec  mov     [r8], r13
0x1800044ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800044f3  inc     rax
0x1800044f6  cmp     [rdx+rax*2], r13w
0x1800044fb  jnz     short loc_1800044F3
0x1800044fd  add     eax, eax
0x1800044ff  mov     ecx, 3E8h
0x180004504  cmp     eax, 64h ; 'd'
0x180004507  cmovl   eax, ecx
0x18000450a  mov     [rbp+57h+var_A0], r13d
0x18000450e  mov     [rbp+57h+var_9C], eax
0x180004511  mov     ecx, eax
0x180004513  add     rcx, rcx
0x180004516  mov     eax, 0FFFFFFFFh
0x18000451b  cmp     rcx, rax
0x18000451e  jbe     short loc_18000452C
0x180004520  mov     rax, r13
0x180004523  mov     rdx, r13
0x180004526  mov     [rbp+57h+pv], rdx
0x18000452a  jmp     short loc_180004544
0x18000452c  mov     ecx, ecx; cb
0x18000452e  call    cs:__imp_CoTaskMemAlloc
0x180004534  mov     rdx, rax
0x180004537  mov     [rbp+57h+pv], rax
0x18000453b  test    rax, rax
0x18000453e  jz      short loc_180004544
0x180004540  mov     [rax], r13w
0x180004544  test    rax, rax
0x180004547  jnz     short loc_18000455C
0x180004549  mov     rcx, rax; pv
0x18000454c  call    cs:__imp_CoTaskMemFree
0x180004552  mov     eax, 8007000Eh
0x180004557  jmp     loc_18000472C
0x18000455c  mov     [r14], rbx
0x18000455f  movzx   eax, word ptr [rbx]
0x180004562  test    ax, ax
0x180004565  jz      loc_1800046F9
0x18000456b  cmp     ax, 25h ; '%'
0x18000456f  jnz     loc_1800046C4
0x180004575  mov     rcx, rbx; lpsz
0x180004578  call    cs:__imp_CharNextW
0x18000457e  mov     [r14], rax
0x180004581  movzx   ecx, word ptr [rax]
0x180004584  cmp     cx, 25h ; '%'
0x180004588  jnz     short loc_180004592
0x18000458a  mov     rdx, rax
0x18000458d  jmp     loc_1800046C7
0x180004592  test    rax, rax
0x180004595  jz      loc_180004719
0x18000459b  mov     rdi, r13
0x18000459e  jmp     short loc_1800045B2
0x1800045a0  cmp     cx, 25h ; '%'
0x1800045a4  jz      short loc_1800045B9
0x1800045a6  mov     rcx, rax; lpsz
0x1800045a9  call    cs:__imp_CharNextW
0x1800045af  movzx   ecx, word ptr [rax]
0x1800045b2  test    cx, cx
0x1800045b5  jnz     short loc_1800045A0
0x1800045b7  jmp     short loc_1800045BC
0x1800045b9  mov     rdi, rax
0x1800045bc  test    rdi, rdi
0x1800045bf  jz      loc_180004719
0x1800045c5  mov     rax, rdi
0x1800045c8  sub     rax, [r14]
0x1800045cb  sar     rax, 1
0x1800045ce  cmp     rax, 1Fh
0x1800045d2  jg      loc_180004712
0x1800045d8  movsxd  r9, eax; MaxCount
0x1800045db  mov     r8, [r14]; Source
0x1800045de  mov     edx, 20h ; ' '; SizeInWords
0x1800045e3  lea     rcx, [rbp+57h+Destination]; Destination
0x1800045e7  call    cs:__imp_wcsncpy_s
0x1800045ed  test    eax, eax
0x1800045ef  jz      short loc_180004615
0x1800045f1  cmp     eax, 0Ch
0x1800045f4  jz      loc_180004774
0x1800045fa  cmp     eax, 16h
0x1800045fd  jz      loc_180004769
0x180004603  cmp     eax, 22h ; '"'
0x180004606  jz      loc_180004769
0x18000460c  cmp     eax, 50h ; 'P'
0x18000460f  jnz     loc_18000475E
0x180004615  mov     rsi, [r14+8]
0x180004619  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000461d  call    cs:__imp_EnterCriticalSection
0x180004623  mov     ebx, r13d
0x180004626  cmp     [rsi+18h], r13d
0x18000462a  jle     short loc_18000464C
0x18000462c  movsxd  rax, ebx
0x18000462f  mov     rcx, [rsi+8]
0x180004633  lea     rdx, [rbp+57h+Destination]; lpString2
0x180004637  mov     rcx, [rcx+rax*8]; lpString1
0x18000463b  call    cs:__imp_lstrcmpiW
0x180004641  test    eax, eax
0x180004643  jz      short loc_18000468E
0x180004645  inc     ebx
0x180004647  cmp     ebx, [rsi+18h]
0x18000464a  jl      short loc_18000462C
0x18000464c  mov     rbx, r13
0x18000464f  lea     rcx, [rsi+20h]; lpCriticalSection
0x180004653  call    cs:__imp_LeaveCriticalSection
0x180004659  test    rbx, rbx
0x18000465c  jz      loc_180004719
0x180004662  mov     [rbp+57h+var_90], r13
0x180004666  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000466a  inc     r8; int
0x18000466d  cmp     [rbx+r8*2], r13w
0x180004672  jnz     short loc_18000466A
0x180004674  mov     rdx, rbx; unsigned __int16 *
0x180004677  lea     rcx, [rbp+57h+var_A0]; this
0x18000467b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004680  nop
0x180004681  test    eax, eax
0x180004683  jz      loc_180004720
0x180004689  mov     rax, [r14]
0x18000468c  jmp     short loc_1800046BD
0x18000468e  cmp     ebx, 0FFFFFFFFh
0x180004691  jz      short loc_18000464C
0x180004693  test    ebx, ebx
0x180004695  js      loc_180004753
0x18000469b  cmp     ebx, [rsi+18h]
0x18000469e  jge     loc_180004753
0x1800046a4  movsxd  rcx, ebx
0x1800046a7  mov     rax, [rsi+10h]
0x1800046ab  mov     rbx, [rax+rcx*8]
0x1800046af  jmp     short loc_18000464F
0x1800046b1  mov     rcx, rax; lpsz
0x1800046b4  call    cs:__imp_CharNextW
0x1800046ba  mov     [r14], rax
0x1800046bd  cmp     rax, rdi
0x1800046c0  jnz     short loc_1800046B1
0x1800046c2  jmp     short loc_1800046DA
0x1800046c4  mov     rdx, rbx; unsigned __int16 *
0x1800046c7  mov     r8d, 1; int
0x1800046cd  lea     rcx, [rbp+57h+var_A0]; this
0x1800046d1  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800046d6  test    eax, eax
0x1800046d8  jz      short loc_180004720
0x1800046da  mov     rcx, [r14]; lpsz
0x1800046dd  call    cs:__imp_CharNextW
0x1800046e3  mov     rbx, rax
0x1800046e6  mov     [r14], rax
0x1800046e9  movzx   eax, word ptr [rax]
0x1800046ec  test    ax, ax
0x1800046ef  jnz     loc_18000456B
0x1800046f5  mov     rdx, [rbp+57h+pv]
0x1800046f9  mov     ebx, r13d
0x1800046fc  mov     [rbp+57h+pv], r13
0x180004700  mov     [r12], rdx
0x180004704  mov     rcx, [rbp+57h+pv]; pv
0x180004708  call    cs:__imp_CoTaskMemFree
0x18000470e  mov     eax, ebx
0x180004710  jmp     short loc_18000472C
0x180004712  mov     ebx, 80004005h
0x180004717  jmp     short loc_180004704
0x180004719  mov     ebx, 80020009h
0x18000471e  jmp     short loc_180004704
0x180004720  mov     ebx, 8007000Eh
0x180004725  jmp     short loc_180004704
0x180004727  mov     eax, 80004003h
0x18000472c  mov     rcx, [rbp+57h+var_40]
0x180004730  xor     rcx, rsp; StackCookie
0x180004733  call    __security_check_cookie
0x180004738  mov     rbx, [rsp+0C0h+arg_8]
0x180004740  add     rsp, 90h
0x180004747  pop     r15
0x180004749  pop     r14
0x18000474b  pop     r13
0x18000474d  pop     r12
0x18000474f  pop     rdi
0x180004750  pop     rsi
0x180004751  pop     rbp
0x180004752  retn
0x180004753  mov     ecx, 0C000008Ch; unsigned int
0x180004758  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000475d  int     3; Trap to Debugger
0x18000475e  mov     ecx, 80004005h; int
0x180004763  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004769  mov     ecx, 80070057h; int
0x18000476e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004774  mov     ecx, 8007000Eh; int
0x180004779  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
