# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140013c50`
- end: `0x140013f43`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `755`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140015830`

## callees

- `0x1400044f8`
- `0x14000da34`
- `0x140013c50`
- `0x1400187b0`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x140013dfd`
- `KERNEL32!lstrcmpiW` at `0x140013dfd`
- `USER32!CharNextW` at `0x140013d32`
- `USER32!CharNextW` at `0x140013d69`
- `USER32!CharNextW` at `0x140013e6c`
- `USER32!CharNextW` at `0x140013e9b`
- `USER32!CharNextW` at `0x140013d32`
- `USER32!CharNextW` at `0x140013d69`
- `USER32!CharNextW` at `0x140013e6c`
- `USER32!CharNextW` at `0x140013e9b`
- `msvcrt!wcsncpy_s` at `0x140013dad`
- `msvcrt!wcsncpy_s` at `0x140013dad`
- `ole32!CoTaskMemFree` at `0x140013d00`
- `ole32!CoTaskMemFree` at `0x140013ecb`
- `ole32!CoTaskMemFree` at `0x140013d00`
- `ole32!CoTaskMemFree` at `0x140013ecb`
- `ole32!CoTaskMemAlloc` at `0x140013cdc`
- `ole32!CoTaskMemAlloc` at `0x140013cdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  const WCHAR *v16; // rsi
  __int64 v17; // rax
  errno_t v18; // eax
  const wchar_t *v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
  _DWORD v26[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v28; // [rsp+30h] [rbp-29h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

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
LABEL_50:
    v22 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_51;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_47:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
        break;
      goto LABEL_48;
    }
    v13 = CharNextW(v4);
    *this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_47;
    }
    if ( !v13 )
      goto LABEL_34;
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
    {
LABEL_34:
      v22 = -2147352567;
      goto LABEL_51;
    }
    v17 = v16 - *this;
    if ( v17 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_51;
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
    v20 = 0;
    if ( *((int *)v19 + 6) <= 0 )
      goto LABEL_34;
    while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
    {
      if ( ++v20 >= *((_DWORD *)v19 + 6) )
        goto LABEL_34;
    }
    if ( v20 == -1 )
      goto LABEL_34;
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
    if ( !v23 )
      goto LABEL_34;
    v28 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v23, v24) )
      break;
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
LABEL_48:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_50;
    }
  }
  v22 = -2147024882;
LABEL_51:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x140013c50  mov     [rsp-8+arg_8], rbx
0x140013c55  mov     [rsp-8+arg_18], rsi
0x140013c5a  push    rbp
0x140013c5b  push    rdi
0x140013c5c  push    r12
0x140013c5e  push    r14
0x140013c60  push    r15
0x140013c62  lea     rbp, [rsp-37h]
0x140013c67  sub     rsp, 90h
0x140013c6e  mov     rax, cs:__security_cookie
0x140013c75  xor     rax, rsp
0x140013c78  mov     [rbp+57h+var_30], rax
0x140013c7c  mov     r15, r8
0x140013c7f  mov     rbx, rdx
0x140013c82  mov     r14, rcx
0x140013c85  xor     r12d, r12d
0x140013c88  test    rdx, rdx
0x140013c8b  jz      loc_140013EE9
0x140013c91  test    r8, r8
0x140013c94  jz      loc_140013EE9
0x140013c9a  mov     [r8], r12
0x140013c9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013ca1  inc     rax
0x140013ca4  cmp     [rdx+rax*2], r12w
0x140013ca9  jnz     short loc_140013CA1
0x140013cab  add     eax, eax
0x140013cad  mov     ecx, 3E8h
0x140013cb2  cmp     eax, 64h ; 'd'
0x140013cb5  cmovl   eax, ecx
0x140013cb8  mov     [rbp+57h+var_90], r12d
0x140013cbc  mov     [rbp+57h+var_8C], eax
0x140013cbf  mov     ecx, eax
0x140013cc1  add     rcx, rcx
0x140013cc4  mov     eax, 0FFFFFFFFh
0x140013cc9  cmp     rcx, rax
0x140013ccc  jbe     short loc_140013CDA
0x140013cce  mov     rax, r12
0x140013cd1  mov     rdx, r12
0x140013cd4  mov     [rbp+57h+pv], rdx
0x140013cd8  jmp     short loc_140013CF8
0x140013cda  mov     ecx, ecx; cb
0x140013cdc  call    cs:__imp_CoTaskMemAlloc
0x140013ce3  nop     dword ptr [rax+rax+00h]
0x140013ce8  mov     rdx, rax
0x140013ceb  mov     [rbp+57h+pv], rax
0x140013cef  test    rax, rax
0x140013cf2  jz      short loc_140013CF8
0x140013cf4  mov     [rax], r12w
0x140013cf8  test    rax, rax
0x140013cfb  jnz     short loc_140013D16
0x140013cfd  mov     rcx, rax; pv
0x140013d00  call    cs:__imp_CoTaskMemFree
0x140013d07  nop     dword ptr [rax+rax+00h]
0x140013d0c  mov     eax, 8007000Eh
0x140013d11  jmp     loc_140013EEE
0x140013d16  mov     [r14], rbx
0x140013d19  movzx   eax, word ptr [rbx]
0x140013d1c  test    ax, ax
0x140013d1f  jz      loc_140013EBD
0x140013d25  cmp     ax, 25h ; '%'
0x140013d29  jnz     loc_140013E82
0x140013d2f  mov     rcx, rbx; lpsz
0x140013d32  call    cs:__imp_CharNextW
0x140013d39  nop     dword ptr [rax+rax+00h]
0x140013d3e  mov     [r14], rax
0x140013d41  movzx   ecx, word ptr [rax]
0x140013d44  cmp     cx, 25h ; '%'
0x140013d48  jnz     short loc_140013D52
0x140013d4a  mov     rdx, rax
0x140013d4d  jmp     loc_140013E85
0x140013d52  test    rax, rax
0x140013d55  jz      loc_140013E14
0x140013d5b  mov     rsi, r12
0x140013d5e  jmp     short loc_140013D78
0x140013d60  cmp     cx, 25h ; '%'
0x140013d64  jz      short loc_140013D7F
0x140013d66  mov     rcx, rax; lpsz
0x140013d69  call    cs:__imp_CharNextW
0x140013d70  nop     dword ptr [rax+rax+00h]
0x140013d75  movzx   ecx, word ptr [rax]
0x140013d78  test    cx, cx
0x140013d7b  jnz     short loc_140013D60
0x140013d7d  jmp     short loc_140013D82
0x140013d7f  mov     rsi, rax
0x140013d82  test    rsi, rsi
0x140013d85  jz      loc_140013E14
0x140013d8b  mov     rax, rsi
0x140013d8e  sub     rax, [r14]
0x140013d91  sar     rax, 1
0x140013d94  cmp     rax, 1Fh
0x140013d98  jg      loc_140013EDB
0x140013d9e  movsxd  r9, eax; MaxCount
0x140013da1  mov     r8, [r14]; Source
0x140013da4  mov     edx, 20h ; ' '; SizeInWords
0x140013da9  lea     rcx, [rbp+57h+Destination]; Destination
0x140013dad  call    cs:__imp_wcsncpy_s
0x140013db4  nop     dword ptr [rax+rax+00h]
0x140013db9  test    eax, eax
0x140013dbb  jz      short loc_140013DE1
0x140013dbd  cmp     eax, 0Ch
0x140013dc0  jz      loc_140013F38
0x140013dc6  cmp     eax, 16h
0x140013dc9  jz      loc_140013F2D
0x140013dcf  cmp     eax, 22h ; '"'
0x140013dd2  jz      loc_140013F2D
0x140013dd8  cmp     eax, 50h ; 'P'
0x140013ddb  jnz     loc_140013F22
0x140013de1  mov     rdi, [r14+8]
0x140013de5  mov     ebx, r12d
0x140013de8  cmp     [rdi+18h], r12d
0x140013dec  jle     short loc_140013E14
0x140013dee  movsxd  rax, ebx
0x140013df1  mov     rcx, [rdi+8]
0x140013df5  lea     rdx, [rbp+57h+Destination]; lpString2
0x140013df9  mov     rcx, [rcx+rax*8]; lpString1
0x140013dfd  call    cs:__imp_lstrcmpiW
0x140013e04  nop     dword ptr [rax+rax+00h]
0x140013e09  test    eax, eax
0x140013e0b  jz      short loc_140013E1E
0x140013e0d  inc     ebx
0x140013e0f  cmp     ebx, [rdi+18h]
0x140013e12  jl      short loc_140013DEE
0x140013e14  mov     ebx, 80020009h
0x140013e19  jmp     loc_140013EC7
0x140013e1e  cmp     ebx, 0FFFFFFFFh
0x140013e21  jz      short loc_140013E14
0x140013e23  test    ebx, ebx
0x140013e25  js      loc_140013F17
0x140013e2b  cmp     ebx, [rdi+18h]
0x140013e2e  jge     loc_140013F17
0x140013e34  movsxd  rcx, ebx
0x140013e37  mov     rax, [rdi+10h]
0x140013e3b  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x140013e3f  test    rdx, rdx
0x140013e42  jz      short loc_140013E14
0x140013e44  mov     [rbp+57h+var_80], r12
0x140013e48  or      r8, 0FFFFFFFFFFFFFFFFh
0x140013e4c  inc     r8; int
0x140013e4f  cmp     [rdx+r8*2], r12w
0x140013e54  jnz     short loc_140013E4C
0x140013e56  lea     rcx, [rbp+57h+var_90]; this
0x140013e5a  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140013e5f  nop
0x140013e60  test    eax, eax
0x140013e62  jz      short loc_140013EE2
0x140013e64  mov     rax, [r14]
0x140013e67  jmp     short loc_140013E7B
0x140013e69  mov     rcx, rax; lpsz
0x140013e6c  call    cs:__imp_CharNextW
0x140013e73  nop     dword ptr [rax+rax+00h]
0x140013e78  mov     [r14], rax
0x140013e7b  cmp     rax, rsi
0x140013e7e  jnz     short loc_140013E69
0x140013e80  jmp     short loc_140013E98
0x140013e82  mov     rdx, rbx; unsigned __int16 *
0x140013e85  mov     r8d, 1; int
0x140013e8b  lea     rcx, [rbp+57h+var_90]; this
0x140013e8f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140013e94  test    eax, eax
0x140013e96  jz      short loc_140013EE2
0x140013e98  mov     rcx, [r14]; lpsz
0x140013e9b  call    cs:__imp_CharNextW
0x140013ea2  nop     dword ptr [rax+rax+00h]
0x140013ea7  mov     rbx, rax
0x140013eaa  mov     [r14], rax
0x140013ead  movzx   eax, word ptr [rax]
0x140013eb0  test    ax, ax
0x140013eb3  jnz     loc_140013D25
0x140013eb9  mov     rdx, [rbp+57h+pv]
0x140013ebd  mov     ebx, r12d
0x140013ec0  mov     [rbp+57h+pv], r12
0x140013ec4  mov     [r15], rdx
0x140013ec7  mov     rcx, [rbp+57h+pv]; pv
0x140013ecb  call    cs:__imp_CoTaskMemFree
0x140013ed2  nop     dword ptr [rax+rax+00h]
0x140013ed7  mov     eax, ebx
0x140013ed9  jmp     short loc_140013EEE
0x140013edb  mov     ebx, 80004005h
0x140013ee0  jmp     short loc_140013EC7
0x140013ee2  mov     ebx, 8007000Eh
0x140013ee7  jmp     short loc_140013EC7
0x140013ee9  mov     eax, 80004003h
0x140013eee  mov     rcx, [rbp+57h+var_30]
0x140013ef2  xor     rcx, rsp; StackCookie
0x140013ef5  call    __security_check_cookie
0x140013efa  lea     r11, [rsp+0B0h+var_20]
0x140013f02  mov     rbx, [r11+38h]
0x140013f06  mov     rsi, [r11+48h]
0x140013f0a  mov     rsp, r11
0x140013f0d  pop     r15
0x140013f0f  pop     r14
0x140013f11  pop     r12
0x140013f13  pop     rdi
0x140013f14  pop     rbp
0x140013f15  retn
0x140013f17  mov     ecx, 0C000008Ch; unsigned int
0x140013f1c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140013f21  int     3; Trap to Debugger
0x140013f22  mov     ecx, 80004005h; int
0x140013f27  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140013f2d  mov     ecx, 80070057h; int
0x140013f32  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140013f38  mov     ecx, 8007000Eh; int
0x140013f3d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
