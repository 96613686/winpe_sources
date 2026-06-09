# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180007310`
- end: `0x1800075de`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180008a7c`

## callees

- `0x18000484c`
- `0x180004a90`
- `0x180007310`
- `0x18000b3dc`
- `0x180018500`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007444`
- `msvcrt!wcsncpy_s` at `0x180007444`
- `KERNEL32!EnterCriticalSection` at `0x18000747a`
- `KERNEL32!EnterCriticalSection` at `0x18000747a`
- `KERNEL32!LeaveCriticalSection` at `0x1800074b1`
- `KERNEL32!LeaveCriticalSection` at `0x1800074b1`
- `KERNEL32!lstrcmpiW` at `0x180007499`
- `KERNEL32!lstrcmpiW` at `0x180007499`
- `USER32!CharNextW` at `0x1800073d4`
- `USER32!CharNextW` at `0x180007405`
- `USER32!CharNextW` at `0x18000750e`
- `USER32!CharNextW` at `0x180007538`
- `USER32!CharNextW` at `0x1800073d4`
- `USER32!CharNextW` at `0x180007405`
- `USER32!CharNextW` at `0x18000750e`
- `USER32!CharNextW` at `0x180007538`
- `ole32!CoTaskMemAlloc` at `0x1800073a1`
- `ole32!CoTaskMemAlloc` at `0x1800073a1`
- `ole32!CoTaskMemFree` at `0x18000738f`
- `ole32!CoTaskMemFree` at `0x180007565`
- `ole32!CoTaskMemFree` at `0x18000738f`
- `ole32!CoTaskMemFree` at `0x180007565`

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
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  const WCHAR *i; // rax
  unsigned int v24; // ebx
  _DWORD v25[2]; // [rsp+20h] [rbp-88h] BYREF
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
  v25[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v25[1] = v7;
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
    v24 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v15, 1) )
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
    v24 = -2147467259;
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
    v21 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    v21 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v21 )
  {
LABEL_52:
    v24 = -2147352567;
    goto LABEL_50;
  }
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v21, v22) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v24 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v24;
}

```

## disassembly

```asm
0x180007310  mov     [rsp+arg_8], rbx
0x180007315  mov     [rsp+arg_18], rbp
0x18000731a  push    rsi
0x18000731b  push    rdi
0x18000731c  push    r12
0x18000731e  push    r14
0x180007320  push    r15
0x180007322  sub     rsp, 80h
0x180007329  mov     rax, cs:__security_cookie
0x180007330  xor     rax, rsp
0x180007333  mov     [rsp+0A8h+var_38], rax
0x180007338  xor     r12d, r12d
0x18000733b  mov     r15, r8
0x18000733e  mov     rbx, rdx
0x180007341  mov     r14, rcx
0x180007344  test    rdx, rdx
0x180007347  jz      loc_180007584
0x18000734d  test    r8, r8
0x180007350  jz      loc_180007584
0x180007356  mov     [r8], r12
0x180007359  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000735d  inc     rax
0x180007360  cmp     [rdx+rax*2], r12w
0x180007365  jnz     short loc_18000735D
0x180007367  add     eax, eax
0x180007369  mov     [rsp+0A8h+var_88], r12d
0x18000736e  cmp     eax, 64h ; 'd'
0x180007371  mov     ecx, 3E8h
0x180007376  cmovl   eax, ecx
0x180007379  mov     ecx, eax
0x18000737b  mov     [rsp+0A8h+var_84], eax
0x18000737f  add     rcx, rcx
0x180007382  mov     eax, 0FFFFFFFFh
0x180007387  cmp     rcx, rax
0x18000738a  jbe     short loc_18000739F
0x18000738c  mov     rcx, r12; pv
0x18000738f  call    cs:__imp_CoTaskMemFree
0x180007395  mov     eax, 8007000Eh
0x18000739a  jmp     loc_180007589
0x18000739f  mov     ecx, ecx; cb
0x1800073a1  call    cs:__imp_CoTaskMemAlloc
0x1800073a7  mov     [rsp+0A8h+pv], rax
0x1800073ac  mov     rcx, rax
0x1800073af  test    rax, rax
0x1800073b2  jz      short loc_18000738F
0x1800073b4  mov     [rax], r12w
0x1800073b8  mov     [r14], rbx
0x1800073bb  movzx   eax, word ptr [rbx]
0x1800073be  test    ax, ax
0x1800073c1  jz      loc_180007555
0x1800073c7  cmp     ax, 25h ; '%'
0x1800073cb  jnz     loc_18000751E
0x1800073d1  mov     rcx, rbx; lpsz
0x1800073d4  call    cs:__imp_CharNextW
0x1800073da  mov     [r14], rax
0x1800073dd  movzx   ecx, word ptr [rax]
0x1800073e0  cmp     cx, 25h ; '%'
0x1800073e4  jnz     short loc_1800073EE
0x1800073e6  mov     rdx, rax
0x1800073e9  jmp     loc_180007521
0x1800073ee  test    rax, rax
0x1800073f1  jz      loc_180007576
0x1800073f7  mov     rdi, r12
0x1800073fa  jmp     short loc_18000740E
0x1800073fc  cmp     cx, 25h ; '%'
0x180007400  jz      short loc_180007415
0x180007402  mov     rcx, rax; lpsz
0x180007405  call    cs:__imp_CharNextW
0x18000740b  movzx   ecx, word ptr [rax]
0x18000740e  test    cx, cx
0x180007411  jnz     short loc_1800073FC
0x180007413  jmp     short loc_180007418
0x180007415  mov     rdi, rax
0x180007418  test    rdi, rdi
0x18000741b  jz      loc_180007576
0x180007421  mov     rax, rdi
0x180007424  sub     rax, [r14]
0x180007427  sar     rax, 1
0x18000742a  cmp     rax, 1Fh
0x18000742e  jg      loc_18000756F
0x180007434  mov     r8, [r14]; Source
0x180007437  lea     rcx, [rsp+0A8h+Destination]; Destination
0x18000743c  movsxd  r9, eax; MaxCount
0x18000743f  mov     edx, 20h ; ' '; SizeInWords
0x180007444  call    cs:__imp_wcsncpy_s
0x18000744a  test    eax, eax
0x18000744c  jz      short loc_180007472
0x18000744e  cmp     eax, 0Ch
0x180007451  jz      loc_1800075D3
0x180007457  cmp     eax, 16h
0x18000745a  jz      loc_1800075C8
0x180007460  cmp     eax, 22h ; '"'
0x180007463  jz      loc_1800075C8
0x180007469  cmp     eax, 50h ; 'P'
0x18000746c  jnz     loc_1800075BD
0x180007472  mov     rsi, [r14+8]
0x180007476  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000747a  call    cs:__imp_EnterCriticalSection
0x180007480  mov     ebx, r12d
0x180007483  cmp     [rsi+18h], r12d
0x180007487  jle     short loc_1800074AA
0x180007489  mov     rcx, [rsi+8]
0x18000748d  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x180007492  movsxd  rax, ebx
0x180007495  mov     rcx, [rcx+rax*8]; lpString1
0x180007499  call    cs:__imp_lstrcmpiW
0x18000749f  test    eax, eax
0x1800074a1  jz      short loc_1800074E8
0x1800074a3  inc     ebx
0x1800074a5  cmp     ebx, [rsi+18h]
0x1800074a8  jl      short loc_180007489
0x1800074aa  mov     rbx, r12
0x1800074ad  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800074b1  call    cs:__imp_LeaveCriticalSection
0x1800074b7  test    rbx, rbx
0x1800074ba  jz      loc_180007576
0x1800074c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800074c4  inc     r8; int
0x1800074c7  cmp     [rbx+r8*2], r12w
0x1800074cc  jnz     short loc_1800074C4
0x1800074ce  mov     rdx, rbx; unsigned __int16 *
0x1800074d1  lea     rcx, [rsp+0A8h+var_88]; this
0x1800074d6  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800074db  test    eax, eax
0x1800074dd  jz      loc_18000757D
0x1800074e3  mov     rax, [r14]
0x1800074e6  jmp     short loc_180007517
0x1800074e8  cmp     ebx, 0FFFFFFFFh
0x1800074eb  jz      short loc_1800074AA
0x1800074ed  test    ebx, ebx
0x1800074ef  js      loc_1800075B2
0x1800074f5  cmp     ebx, [rsi+18h]
0x1800074f8  jge     loc_1800075B2
0x1800074fe  mov     rax, [rsi+10h]
0x180007502  movsxd  rcx, ebx
0x180007505  mov     rbx, [rax+rcx*8]
0x180007509  jmp     short loc_1800074AD
0x18000750b  mov     rcx, rax; lpsz
0x18000750e  call    cs:__imp_CharNextW
0x180007514  mov     [r14], rax
0x180007517  cmp     rax, rdi
0x18000751a  jnz     short loc_18000750B
0x18000751c  jmp     short loc_180007535
0x18000751e  mov     rdx, rbx; unsigned __int16 *
0x180007521  mov     r8d, 1; int
0x180007527  lea     rcx, [rsp+0A8h+var_88]; this
0x18000752c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007531  test    eax, eax
0x180007533  jz      short loc_18000757D
0x180007535  mov     rcx, [r14]; lpsz
0x180007538  call    cs:__imp_CharNextW
0x18000753e  mov     rbx, rax
0x180007541  mov     [r14], rax
0x180007544  movzx   eax, word ptr [rax]
0x180007547  test    ax, ax
0x18000754a  jnz     loc_1800073C7
0x180007550  mov     rcx, [rsp+0A8h+pv]
0x180007555  mov     ebx, r12d
0x180007558  mov     [rsp+0A8h+pv], r12
0x18000755d  mov     [r15], rcx
0x180007560  mov     rcx, [rsp+0A8h+pv]; pv
0x180007565  call    cs:__imp_CoTaskMemFree
0x18000756b  mov     eax, ebx
0x18000756d  jmp     short loc_180007589
0x18000756f  mov     ebx, 80004005h
0x180007574  jmp     short loc_180007560
0x180007576  mov     ebx, 80020009h
0x18000757b  jmp     short loc_180007560
0x18000757d  mov     ebx, 8007000Eh
0x180007582  jmp     short loc_180007560
0x180007584  mov     eax, 80004003h
0x180007589  mov     rcx, [rsp+0A8h+var_38]
0x18000758e  xor     rcx, rsp; StackCookie
0x180007591  call    __security_check_cookie
0x180007596  lea     r11, [rsp+0A8h+var_28]
0x18000759e  mov     rbx, [r11+38h]
0x1800075a2  mov     rbp, [r11+48h]
0x1800075a6  mov     rsp, r11
0x1800075a9  pop     r15
0x1800075ab  pop     r14
0x1800075ad  pop     r12
0x1800075af  pop     rdi
0x1800075b0  pop     rsi
0x1800075b1  retn
0x1800075b2  mov     ecx, 0C000008Ch; unsigned int
0x1800075b7  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800075bc  int     3; Trap to Debugger
0x1800075bd  mov     ecx, 80004005h; int
0x1800075c2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800075c8  mov     ecx, 80070057h; int
0x1800075cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800075d3  mov     ecx, 8007000Eh; int
0x1800075d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
