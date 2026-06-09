# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140007110`
- end: `0x14000742e`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `798`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400076dc`

## callees

- `0x140001500`
- `0x140006800`
- `0x140006940`
- `0x140007110`
- `0x140008afc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000726b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14000726b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400072a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400072a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400072e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400072e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000719a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000719a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400071be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400073b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400071be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400073b0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400071f0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007227`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007350`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000737f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400071f0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007227`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140007350`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000737f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400072cb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400072cb`

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
  int v18; // eax
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
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
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
0x140007110  mov     [rsp-8+arg_8], rbx
0x140007115  push    rbp
0x140007116  push    rsi
0x140007117  push    rdi
0x140007118  push    r12
0x14000711a  push    r13
0x14000711c  push    r14
0x14000711e  push    r15
0x140007120  lea     rbp, [rsp-27h]
0x140007125  sub     rsp, 90h
0x14000712c  mov     rax, cs:__security_cookie
0x140007133  xor     rax, rsp
0x140007136  mov     [rbp+57h+var_40], rax
0x14000713a  mov     r12, r8
0x14000713d  mov     rbx, rdx
0x140007140  mov     r14, rcx
0x140007143  xor     r13d, r13d
0x140007146  test    rdx, rdx
0x140007149  jz      loc_1400073D5
0x14000714f  test    r8, r8
0x140007152  jz      loc_1400073D5
0x140007158  mov     [r8], r13
0x14000715b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000715f  inc     rax
0x140007162  cmp     [rdx+rax*2], r13w
0x140007167  jnz     short loc_14000715F
0x140007169  add     eax, eax
0x14000716b  mov     ecx, 3E8h
0x140007170  cmp     eax, 64h ; 'd'
0x140007173  cmovl   eax, ecx
0x140007176  mov     [rbp+57h+var_A0], r13d
0x14000717a  mov     [rbp+57h+var_9C], eax
0x14000717d  mov     ecx, eax
0x14000717f  add     rcx, rcx
0x140007182  mov     eax, 0FFFFFFFFh
0x140007187  cmp     rcx, rax
0x14000718a  jbe     short loc_140007198
0x14000718c  mov     rax, r13
0x14000718f  mov     rdx, r13
0x140007192  mov     [rbp+57h+pv], rdx
0x140007196  jmp     short loc_1400071B6
0x140007198  mov     ecx, ecx; cb
0x14000719a  call    cs:__imp_CoTaskMemAlloc
0x1400071a1  nop     dword ptr [rax+rax+00h]
0x1400071a6  mov     rdx, rax
0x1400071a9  mov     [rbp+57h+pv], rax
0x1400071ad  test    rax, rax
0x1400071b0  jz      short loc_1400071B6
0x1400071b2  mov     [rax], r13w
0x1400071b6  test    rax, rax
0x1400071b9  jnz     short loc_1400071D4
0x1400071bb  mov     rcx, rax; pv
0x1400071be  call    cs:__imp_CoTaskMemFree
0x1400071c5  nop     dword ptr [rax+rax+00h]
0x1400071ca  mov     eax, 8007000Eh
0x1400071cf  jmp     loc_1400073DA
0x1400071d4  mov     [r14], rbx
0x1400071d7  movzx   eax, word ptr [rbx]
0x1400071da  test    ax, ax
0x1400071dd  jz      loc_1400073A1
0x1400071e3  cmp     ax, 25h ; '%'
0x1400071e7  jnz     loc_140007366
0x1400071ed  mov     rcx, rbx; lpsz
0x1400071f0  call    cs:__imp_CharNextW
0x1400071f7  nop     dword ptr [rax+rax+00h]
0x1400071fc  mov     [r14], rax
0x1400071ff  movzx   ecx, word ptr [rax]
0x140007202  cmp     cx, 25h ; '%'
0x140007206  jnz     short loc_140007210
0x140007208  mov     rdx, rax
0x14000720b  jmp     loc_140007369
0x140007210  test    rax, rax
0x140007213  jz      loc_1400073C7
0x140007219  mov     rdi, r13
0x14000721c  jmp     short loc_140007236
0x14000721e  cmp     cx, 25h ; '%'
0x140007222  jz      short loc_14000723D
0x140007224  mov     rcx, rax; lpsz
0x140007227  call    cs:__imp_CharNextW
0x14000722e  nop     dword ptr [rax+rax+00h]
0x140007233  movzx   ecx, word ptr [rax]
0x140007236  test    cx, cx
0x140007239  jnz     short loc_14000721E
0x14000723b  jmp     short loc_140007240
0x14000723d  mov     rdi, rax
0x140007240  test    rdi, rdi
0x140007243  jz      loc_1400073C7
0x140007249  mov     rax, rdi
0x14000724c  sub     rax, [r14]
0x14000724f  sar     rax, 1
0x140007252  cmp     rax, 1Fh
0x140007256  jg      loc_1400073C0
0x14000725c  movsxd  r9, eax
0x14000725f  mov     r8, [r14]
0x140007262  mov     edx, 20h ; ' '
0x140007267  lea     rcx, [rbp+57h+String2]
0x14000726b  call    cs:__imp__o_wcsncpy_s
0x140007272  nop     dword ptr [rax+rax+00h]
0x140007277  test    eax, eax
0x140007279  jz      short loc_14000729F
0x14000727b  cmp     eax, 0Ch
0x14000727e  jz      loc_140007423
0x140007284  cmp     eax, 16h
0x140007287  jz      loc_140007418
0x14000728d  cmp     eax, 22h ; '"'
0x140007290  jz      loc_140007418
0x140007296  cmp     eax, 50h ; 'P'
0x140007299  jnz     loc_14000740D
0x14000729f  mov     rsi, [r14+8]
0x1400072a3  lea     rcx, [rsi+20h]; lpCriticalSection
0x1400072a7  call    cs:__imp_EnterCriticalSection
0x1400072ae  nop     dword ptr [rax+rax+00h]
0x1400072b3  mov     ebx, r13d
0x1400072b6  cmp     [rsi+18h], r13d
0x1400072ba  jle     short loc_1400072E2
0x1400072bc  movsxd  rax, ebx
0x1400072bf  mov     rcx, [rsi+8]
0x1400072c3  lea     rdx, [rbp+57h+String2]; lpString2
0x1400072c7  mov     rcx, [rcx+rax*8]; lpString1
0x1400072cb  call    cs:__imp_lstrcmpiW
0x1400072d2  nop     dword ptr [rax+rax+00h]
0x1400072d7  test    eax, eax
0x1400072d9  jz      short loc_14000732A
0x1400072db  inc     ebx
0x1400072dd  cmp     ebx, [rsi+18h]
0x1400072e0  jl      short loc_1400072BC
0x1400072e2  mov     rbx, r13
0x1400072e5  lea     rcx, [rsi+20h]; lpCriticalSection
0x1400072e9  call    cs:__imp_LeaveCriticalSection
0x1400072f0  nop     dword ptr [rax+rax+00h]
0x1400072f5  test    rbx, rbx
0x1400072f8  jz      loc_1400073C7
0x1400072fe  mov     [rbp+57h+var_90], r13
0x140007302  or      r8, 0FFFFFFFFFFFFFFFFh
0x140007306  inc     r8; int
0x140007309  cmp     [rbx+r8*2], r13w
0x14000730e  jnz     short loc_140007306
0x140007310  mov     rdx, rbx; unsigned __int16 *
0x140007313  lea     rcx, [rbp+57h+var_A0]; this
0x140007317  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x14000731c  nop
0x14000731d  test    eax, eax
0x14000731f  jz      loc_1400073CE
0x140007325  mov     rax, [r14]
0x140007328  jmp     short loc_14000735F
0x14000732a  cmp     ebx, 0FFFFFFFFh
0x14000732d  jz      short loc_1400072E2
0x14000732f  test    ebx, ebx
0x140007331  js      loc_140007402
0x140007337  cmp     ebx, [rsi+18h]
0x14000733a  jge     loc_140007402
0x140007340  movsxd  rcx, ebx
0x140007343  mov     rax, [rsi+10h]
0x140007347  mov     rbx, [rax+rcx*8]
0x14000734b  jmp     short loc_1400072E5
0x14000734d  mov     rcx, rax; lpsz
0x140007350  call    cs:__imp_CharNextW
0x140007357  nop     dword ptr [rax+rax+00h]
0x14000735c  mov     [r14], rax
0x14000735f  cmp     rax, rdi
0x140007362  jnz     short loc_14000734D
0x140007364  jmp     short loc_14000737C
0x140007366  mov     rdx, rbx; unsigned __int16 *
0x140007369  mov     r8d, 1; int
0x14000736f  lea     rcx, [rbp+57h+var_A0]; this
0x140007373  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140007378  test    eax, eax
0x14000737a  jz      short loc_1400073CE
0x14000737c  mov     rcx, [r14]; lpsz
0x14000737f  call    cs:__imp_CharNextW
0x140007386  nop     dword ptr [rax+rax+00h]
0x14000738b  mov     rbx, rax
0x14000738e  mov     [r14], rax
0x140007391  movzx   eax, word ptr [rax]
0x140007394  test    ax, ax
0x140007397  jnz     loc_1400071E3
0x14000739d  mov     rdx, [rbp+57h+pv]
0x1400073a1  mov     ebx, r13d
0x1400073a4  mov     [rbp+57h+pv], r13
0x1400073a8  mov     [r12], rdx
0x1400073ac  mov     rcx, [rbp+57h+pv]; pv
0x1400073b0  call    cs:__imp_CoTaskMemFree
0x1400073b7  nop     dword ptr [rax+rax+00h]
0x1400073bc  mov     eax, ebx
0x1400073be  jmp     short loc_1400073DA
0x1400073c0  mov     ebx, 80004005h
0x1400073c5  jmp     short loc_1400073AC
0x1400073c7  mov     ebx, 80020009h
0x1400073cc  jmp     short loc_1400073AC
0x1400073ce  mov     ebx, 8007000Eh
0x1400073d3  jmp     short loc_1400073AC
0x1400073d5  mov     eax, 80004003h
0x1400073da  mov     rcx, [rbp+57h+var_40]
0x1400073de  xor     rcx, rsp; StackCookie
0x1400073e1  call    __security_check_cookie
0x1400073e6  mov     rbx, [rsp+0C0h+arg_8]
0x1400073ee  add     rsp, 90h
0x1400073f5  pop     r15
0x1400073f7  pop     r14
0x1400073f9  pop     r13
0x1400073fb  pop     r12
0x1400073fd  pop     rdi
0x1400073fe  pop     rsi
0x1400073ff  pop     rbp
0x140007400  retn
0x140007402  mov     ecx, 0C000008Ch; unsigned int
0x140007407  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x14000740c  int     3; Trap to Debugger
0x14000740d  mov     ecx, 80004005h; int
0x140007412  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007418  mov     ecx, 80070057h; int
0x14000741d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007423  mov     ecx, 8007000Eh; int
0x140007428  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
