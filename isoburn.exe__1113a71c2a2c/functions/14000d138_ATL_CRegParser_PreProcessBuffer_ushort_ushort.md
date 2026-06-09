# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x14000d138`
- end: `0x14000d406`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000d578`

## callees

- `0x140001fa0`
- `0x1400045e4`
- `0x140009858`
- `0x14000cb8c`
- `0x14000d138`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000d2a2`
- `KERNEL32!EnterCriticalSection` at `0x14000d2a2`
- `KERNEL32!LeaveCriticalSection` at `0x14000d2d9`
- `KERNEL32!LeaveCriticalSection` at `0x14000d2d9`
- `KERNEL32!lstrcmpiW` at `0x14000d2c1`
- `KERNEL32!lstrcmpiW` at `0x14000d2c1`
- `USER32!CharNextW` at `0x14000d1fc`
- `USER32!CharNextW` at `0x14000d22d`
- `USER32!CharNextW` at `0x14000d336`
- `USER32!CharNextW` at `0x14000d360`
- `USER32!CharNextW` at `0x14000d1fc`
- `USER32!CharNextW` at `0x14000d22d`
- `USER32!CharNextW` at `0x14000d336`
- `USER32!CharNextW` at `0x14000d360`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000d26c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000d26c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d1c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d1c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d38d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d38d`

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
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  WCHAR String2[32]; // [rsp+30h] [rbp-78h] BYREF

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
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17);
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
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
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
0x14000d138  mov     [rsp+arg_8], rbx
0x14000d13d  mov     [rsp+arg_18], rbp
0x14000d142  push    rsi
0x14000d143  push    rdi
0x14000d144  push    r12
0x14000d146  push    r14
0x14000d148  push    r15
0x14000d14a  sub     rsp, 80h
0x14000d151  mov     rax, cs:__security_cookie
0x14000d158  xor     rax, rsp
0x14000d15b  mov     [rsp+0A8h+var_38], rax
0x14000d160  xor     r12d, r12d
0x14000d163  mov     r15, r8
0x14000d166  mov     rbx, rdx
0x14000d169  mov     r14, rcx
0x14000d16c  test    rdx, rdx
0x14000d16f  jz      loc_14000D3AC
0x14000d175  test    r8, r8
0x14000d178  jz      loc_14000D3AC
0x14000d17e  mov     [r8], r12
0x14000d181  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d185  inc     rax
0x14000d188  cmp     [rdx+rax*2], r12w
0x14000d18d  jnz     short loc_14000D185
0x14000d18f  add     eax, eax
0x14000d191  mov     [rsp+0A8h+var_88], r12d
0x14000d196  cmp     eax, 64h ; 'd'
0x14000d199  mov     ecx, 3E8h
0x14000d19e  cmovl   eax, ecx
0x14000d1a1  mov     ecx, eax
0x14000d1a3  mov     [rsp+0A8h+var_84], eax
0x14000d1a7  add     rcx, rcx
0x14000d1aa  mov     eax, 0FFFFFFFFh
0x14000d1af  cmp     rcx, rax
0x14000d1b2  jbe     short loc_14000D1C7
0x14000d1b4  mov     rcx, r12; pv
0x14000d1b7  call    cs:__imp_CoTaskMemFree
0x14000d1bd  mov     eax, 8007000Eh
0x14000d1c2  jmp     loc_14000D3B1
0x14000d1c7  mov     ecx, ecx; cb
0x14000d1c9  call    cs:__imp_CoTaskMemAlloc
0x14000d1cf  mov     [rsp+0A8h+pv], rax
0x14000d1d4  mov     rcx, rax
0x14000d1d7  test    rax, rax
0x14000d1da  jz      short loc_14000D1B7
0x14000d1dc  mov     [rax], r12w
0x14000d1e0  mov     [r14], rbx
0x14000d1e3  movzx   eax, word ptr [rbx]
0x14000d1e6  test    ax, ax
0x14000d1e9  jz      loc_14000D37D
0x14000d1ef  cmp     ax, 25h ; '%'
0x14000d1f3  jnz     loc_14000D346
0x14000d1f9  mov     rcx, rbx; lpsz
0x14000d1fc  call    cs:__imp_CharNextW
0x14000d202  mov     [r14], rax
0x14000d205  movzx   ecx, word ptr [rax]
0x14000d208  cmp     cx, 25h ; '%'
0x14000d20c  jnz     short loc_14000D216
0x14000d20e  mov     rdx, rax
0x14000d211  jmp     loc_14000D349
0x14000d216  test    rax, rax
0x14000d219  jz      loc_14000D39E
0x14000d21f  mov     rdi, r12
0x14000d222  jmp     short loc_14000D236
0x14000d224  cmp     cx, 25h ; '%'
0x14000d228  jz      short loc_14000D23D
0x14000d22a  mov     rcx, rax; lpsz
0x14000d22d  call    cs:__imp_CharNextW
0x14000d233  movzx   ecx, word ptr [rax]
0x14000d236  test    cx, cx
0x14000d239  jnz     short loc_14000D224
0x14000d23b  jmp     short loc_14000D240
0x14000d23d  mov     rdi, rax
0x14000d240  test    rdi, rdi
0x14000d243  jz      loc_14000D39E
0x14000d249  mov     rax, rdi
0x14000d24c  sub     rax, [r14]
0x14000d24f  sar     rax, 1
0x14000d252  cmp     rax, 1Fh
0x14000d256  jg      loc_14000D397
0x14000d25c  mov     r8, [r14]
0x14000d25f  lea     rcx, [rsp+0A8h+String2]
0x14000d264  movsxd  r9, eax
0x14000d267  mov     edx, 20h ; ' '
0x14000d26c  call    cs:__imp__o_wcsncpy_s
0x14000d272  test    eax, eax
0x14000d274  jz      short loc_14000D29A
0x14000d276  cmp     eax, 0Ch
0x14000d279  jz      loc_14000D3FB
0x14000d27f  cmp     eax, 16h
0x14000d282  jz      loc_14000D3F0
0x14000d288  cmp     eax, 22h ; '"'
0x14000d28b  jz      loc_14000D3F0
0x14000d291  cmp     eax, 50h ; 'P'
0x14000d294  jnz     loc_14000D3E5
0x14000d29a  mov     rsi, [r14+8]
0x14000d29e  lea     rcx, [rsi+20h]; lpCriticalSection
0x14000d2a2  call    cs:__imp_EnterCriticalSection
0x14000d2a8  mov     ebx, r12d
0x14000d2ab  cmp     [rsi+18h], r12d
0x14000d2af  jle     short loc_14000D2D2
0x14000d2b1  mov     rcx, [rsi+8]
0x14000d2b5  lea     rdx, [rsp+0A8h+String2]; lpString2
0x14000d2ba  movsxd  rax, ebx
0x14000d2bd  mov     rcx, [rcx+rax*8]; lpString1
0x14000d2c1  call    cs:__imp_lstrcmpiW
0x14000d2c7  test    eax, eax
0x14000d2c9  jz      short loc_14000D310
0x14000d2cb  inc     ebx
0x14000d2cd  cmp     ebx, [rsi+18h]
0x14000d2d0  jl      short loc_14000D2B1
0x14000d2d2  mov     rbx, r12
0x14000d2d5  lea     rcx, [rsi+20h]; lpCriticalSection
0x14000d2d9  call    cs:__imp_LeaveCriticalSection
0x14000d2df  test    rbx, rbx
0x14000d2e2  jz      loc_14000D39E
0x14000d2e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000d2ec  inc     r8; int
0x14000d2ef  cmp     [rbx+r8*2], r12w
0x14000d2f4  jnz     short loc_14000D2EC
0x14000d2f6  mov     rdx, rbx; unsigned __int16 *
0x14000d2f9  lea     rcx, [rsp+0A8h+var_88]; this
0x14000d2fe  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14000d303  test    eax, eax
0x14000d305  jz      loc_14000D3A5
0x14000d30b  mov     rax, [r14]
0x14000d30e  jmp     short loc_14000D33F
0x14000d310  cmp     ebx, 0FFFFFFFFh
0x14000d313  jz      short loc_14000D2D2
0x14000d315  test    ebx, ebx
0x14000d317  js      loc_14000D3DA
0x14000d31d  cmp     ebx, [rsi+18h]
0x14000d320  jge     loc_14000D3DA
0x14000d326  mov     rax, [rsi+10h]
0x14000d32a  movsxd  rcx, ebx
0x14000d32d  mov     rbx, [rax+rcx*8]
0x14000d331  jmp     short loc_14000D2D5
0x14000d333  mov     rcx, rax; lpsz
0x14000d336  call    cs:__imp_CharNextW
0x14000d33c  mov     [r14], rax
0x14000d33f  cmp     rax, rdi
0x14000d342  jnz     short loc_14000D333
0x14000d344  jmp     short loc_14000D35D
0x14000d346  mov     rdx, rbx; unsigned __int16 *
0x14000d349  mov     r8d, 1; int
0x14000d34f  lea     rcx, [rsp+0A8h+var_88]; this
0x14000d354  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14000d359  test    eax, eax
0x14000d35b  jz      short loc_14000D3A5
0x14000d35d  mov     rcx, [r14]; lpsz
0x14000d360  call    cs:__imp_CharNextW
0x14000d366  mov     rbx, rax
0x14000d369  mov     [r14], rax
0x14000d36c  movzx   eax, word ptr [rax]
0x14000d36f  test    ax, ax
0x14000d372  jnz     loc_14000D1EF
0x14000d378  mov     rcx, [rsp+0A8h+pv]
0x14000d37d  mov     ebx, r12d
0x14000d380  mov     [rsp+0A8h+pv], r12
0x14000d385  mov     [r15], rcx
0x14000d388  mov     rcx, [rsp+0A8h+pv]; pv
0x14000d38d  call    cs:__imp_CoTaskMemFree
0x14000d393  mov     eax, ebx
0x14000d395  jmp     short loc_14000D3B1
0x14000d397  mov     ebx, 80004005h
0x14000d39c  jmp     short loc_14000D388
0x14000d39e  mov     ebx, 80020009h
0x14000d3a3  jmp     short loc_14000D388
0x14000d3a5  mov     ebx, 8007000Eh
0x14000d3aa  jmp     short loc_14000D388
0x14000d3ac  mov     eax, 80004003h
0x14000d3b1  mov     rcx, [rsp+0A8h+var_38]
0x14000d3b6  xor     rcx, rsp; StackCookie
0x14000d3b9  call    __security_check_cookie
0x14000d3be  lea     r11, [rsp+0A8h+var_28]
0x14000d3c6  mov     rbx, [r11+38h]
0x14000d3ca  mov     rbp, [r11+48h]
0x14000d3ce  mov     rsp, r11
0x14000d3d1  pop     r15
0x14000d3d3  pop     r14
0x14000d3d5  pop     r12
0x14000d3d7  pop     rdi
0x14000d3d8  pop     rsi
0x14000d3d9  retn
0x14000d3da  mov     ecx, 0C000008Ch; unsigned int
0x14000d3df  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x14000d3e4  int     3; Trap to Debugger
0x14000d3e5  mov     ecx, 80004005h; int
0x14000d3ea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000d3f0  mov     ecx, 80070057h; int
0x14000d3f5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000d3fb  mov     ecx, 8007000Eh; int
0x14000d400  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
