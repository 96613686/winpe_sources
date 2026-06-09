# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x140003abc`
- end: `0x140003d5a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `670`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140003f98`

## callees

- `0x140002adc`
- `0x140002c14`
- `0x140003abc`
- `0x14000522c`
- `0x1400065f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x140003c31`
- `KERNEL32!lstrcmpiW` at `0x140003c31`
- `USER32!CharNextW` at `0x140003b7a`
- `USER32!CharNextW` at `0x140003bab`
- `USER32!CharNextW` at `0x140003c96`
- `USER32!CharNextW` at `0x140003cc0`
- `USER32!CharNextW` at `0x140003b7a`
- `USER32!CharNextW` at `0x140003bab`
- `USER32!CharNextW` at `0x140003c96`
- `USER32!CharNextW` at `0x140003cc0`
- `msvcrt!wcsncpy_s` at `0x140003be6`
- `msvcrt!wcsncpy_s` at `0x140003be6`
- `ole32!CoTaskMemAlloc` at `0x140003b47`
- `ole32!CoTaskMemAlloc` at `0x140003b47`
- `ole32!CoTaskMemFree` at `0x140003b35`
- `ole32!CoTaskMemFree` at `0x140003ced`
- `ole32!CoTaskMemFree` at `0x140003b35`
- `ole32!CoTaskMemFree` at `0x140003ced`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  const WCHAR *v16; // rbp
  __int64 v17; // rax
  errno_t v18; // eax
  const wchar_t *v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
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
LABEL_48:
    v22 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_49;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_45:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
        break;
      goto LABEL_46;
    }
    v13 = CharNextW(v4);
    *this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_45;
    }
    if ( !v13 )
      goto LABEL_32;
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
LABEL_32:
      v22 = -2147352567;
      goto LABEL_49;
    }
    v17 = v16 - *this;
    if ( v17 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_49;
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
      goto LABEL_32;
    while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
    {
      if ( ++v20 >= *((_DWORD *)v19 + 6) )
        goto LABEL_32;
    }
    if ( v20 == -1 )
      goto LABEL_32;
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
    if ( !v23 )
      goto LABEL_32;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v23, v24) )
      break;
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
LABEL_46:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_48;
    }
  }
  v22 = -2147024882;
LABEL_49:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x140003abc  mov     [rsp+arg_8], rbx
0x140003ac1  push    rbp
0x140003ac2  push    rsi
0x140003ac3  push    rdi
0x140003ac4  push    r14
0x140003ac6  push    r15
0x140003ac8  sub     rsp, 80h
0x140003acf  mov     rax, cs:__security_cookie
0x140003ad6  xor     rax, rsp
0x140003ad9  mov     [rsp+0A8h+var_38], rax
0x140003ade  xor     r15d, r15d
0x140003ae1  mov     r14, r8
0x140003ae4  mov     rbx, rdx
0x140003ae7  mov     rsi, rcx
0x140003aea  test    rdx, rdx
0x140003aed  jz      loc_140003D05
0x140003af3  test    r8, r8
0x140003af6  jz      loc_140003D05
0x140003afc  mov     [r8], r15
0x140003aff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003b03  inc     rax
0x140003b06  cmp     [rdx+rax*2], r15w
0x140003b0b  jnz     short loc_140003B03
0x140003b0d  add     eax, eax
0x140003b0f  mov     [rsp+0A8h+var_88], r15d
0x140003b14  cmp     eax, 64h ; 'd'
0x140003b17  mov     ecx, 3E8h
0x140003b1c  cmovl   eax, ecx
0x140003b1f  mov     ecx, eax
0x140003b21  mov     [rsp+0A8h+var_84], eax
0x140003b25  add     rcx, rcx
0x140003b28  mov     eax, 0FFFFFFFFh
0x140003b2d  cmp     rcx, rax
0x140003b30  jbe     short loc_140003B45
0x140003b32  mov     rcx, r15; pv
0x140003b35  call    cs:__imp_CoTaskMemFree
0x140003b3b  mov     eax, 8007000Eh
0x140003b40  jmp     loc_140003D0A
0x140003b45  mov     ecx, ecx; cb
0x140003b47  call    cs:__imp_CoTaskMemAlloc
0x140003b4d  mov     [rsp+0A8h+pv], rax
0x140003b52  mov     rcx, rax
0x140003b55  test    rax, rax
0x140003b58  jz      short loc_140003B35
0x140003b5a  mov     [rax], r15w
0x140003b5e  mov     [rsi], rbx
0x140003b61  movzx   eax, word ptr [rbx]
0x140003b64  test    ax, ax
0x140003b67  jz      loc_140003CDD
0x140003b6d  cmp     ax, 25h ; '%'
0x140003b71  jnz     loc_140003CA6
0x140003b77  mov     rcx, rbx; lpsz
0x140003b7a  call    cs:__imp_CharNextW
0x140003b80  mov     [rsi], rax
0x140003b83  movzx   ecx, word ptr [rax]
0x140003b86  cmp     cx, 25h ; '%'
0x140003b8a  jnz     short loc_140003B94
0x140003b8c  mov     rdx, rax
0x140003b8f  jmp     loc_140003CA9
0x140003b94  test    rax, rax
0x140003b97  jz      loc_140003C42
0x140003b9d  mov     rbp, r15
0x140003ba0  jmp     short loc_140003BB4
0x140003ba2  cmp     cx, 25h ; '%'
0x140003ba6  jz      short loc_140003BBB
0x140003ba8  mov     rcx, rax; lpsz
0x140003bab  call    cs:__imp_CharNextW
0x140003bb1  movzx   ecx, word ptr [rax]
0x140003bb4  test    cx, cx
0x140003bb7  jnz     short loc_140003BA2
0x140003bb9  jmp     short loc_140003BBE
0x140003bbb  mov     rbp, rax
0x140003bbe  test    rbp, rbp
0x140003bc1  jz      short loc_140003C42
0x140003bc3  mov     rax, rbp
0x140003bc6  sub     rax, [rsi]
0x140003bc9  sar     rax, 1
0x140003bcc  cmp     rax, 1Fh
0x140003bd0  jg      loc_140003CF7
0x140003bd6  mov     r8, [rsi]; Source
0x140003bd9  lea     rcx, [rsp+0A8h+Destination]; Destination
0x140003bde  movsxd  r9, eax; MaxCount
0x140003be1  mov     edx, 20h ; ' '; SizeInWords
0x140003be6  call    cs:__imp_wcsncpy_s
0x140003bec  test    eax, eax
0x140003bee  jz      short loc_140003C14
0x140003bf0  cmp     eax, 0Ch
0x140003bf3  jz      loc_140003D4F
0x140003bf9  cmp     eax, 16h
0x140003bfc  jz      loc_140003D44
0x140003c02  cmp     eax, 22h ; '"'
0x140003c05  jz      loc_140003D44
0x140003c0b  cmp     eax, 50h ; 'P'
0x140003c0e  jnz     loc_140003D39
0x140003c14  mov     rdi, [rsi+8]
0x140003c18  mov     ebx, r15d
0x140003c1b  cmp     [rdi+18h], r15d
0x140003c1f  jle     short loc_140003C42
0x140003c21  mov     rcx, [rdi+8]
0x140003c25  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x140003c2a  movsxd  rax, ebx
0x140003c2d  mov     rcx, [rcx+rax*8]; lpString1
0x140003c31  call    cs:__imp_lstrcmpiW
0x140003c37  test    eax, eax
0x140003c39  jz      short loc_140003C4C
0x140003c3b  inc     ebx
0x140003c3d  cmp     ebx, [rdi+18h]
0x140003c40  jl      short loc_140003C21
0x140003c42  mov     ebx, 80020009h
0x140003c47  jmp     loc_140003CE8
0x140003c4c  cmp     ebx, 0FFFFFFFFh
0x140003c4f  jz      short loc_140003C42
0x140003c51  test    ebx, ebx
0x140003c53  js      loc_140003D2E
0x140003c59  cmp     ebx, [rdi+18h]
0x140003c5c  jge     loc_140003D2E
0x140003c62  mov     rax, [rdi+10h]
0x140003c66  movsxd  rcx, ebx
0x140003c69  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x140003c6d  test    rdx, rdx
0x140003c70  jz      short loc_140003C42
0x140003c72  or      r8, 0FFFFFFFFFFFFFFFFh
0x140003c76  inc     r8; int
0x140003c79  cmp     [rdx+r8*2], r15w
0x140003c7e  jnz     short loc_140003C76
0x140003c80  lea     rcx, [rsp+0A8h+var_88]; this
0x140003c85  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140003c8a  test    eax, eax
0x140003c8c  jz      short loc_140003CFE
0x140003c8e  mov     rax, [rsi]
0x140003c91  jmp     short loc_140003C9F
0x140003c93  mov     rcx, rax; lpsz
0x140003c96  call    cs:__imp_CharNextW
0x140003c9c  mov     [rsi], rax
0x140003c9f  cmp     rax, rbp
0x140003ca2  jnz     short loc_140003C93
0x140003ca4  jmp     short loc_140003CBD
0x140003ca6  mov     rdx, rbx; unsigned __int16 *
0x140003ca9  mov     r8d, 1; int
0x140003caf  lea     rcx, [rsp+0A8h+var_88]; this
0x140003cb4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140003cb9  test    eax, eax
0x140003cbb  jz      short loc_140003CFE
0x140003cbd  mov     rcx, [rsi]; lpsz
0x140003cc0  call    cs:__imp_CharNextW
0x140003cc6  mov     rbx, rax
0x140003cc9  mov     [rsi], rax
0x140003ccc  movzx   eax, word ptr [rax]
0x140003ccf  test    ax, ax
0x140003cd2  jnz     loc_140003B6D
0x140003cd8  mov     rcx, [rsp+0A8h+pv]
0x140003cdd  mov     ebx, r15d
0x140003ce0  mov     [rsp+0A8h+pv], r15
0x140003ce5  mov     [r14], rcx
0x140003ce8  mov     rcx, [rsp+0A8h+pv]; pv
0x140003ced  call    cs:__imp_CoTaskMemFree
0x140003cf3  mov     eax, ebx
0x140003cf5  jmp     short loc_140003D0A
0x140003cf7  mov     ebx, 80004005h
0x140003cfc  jmp     short loc_140003CE8
0x140003cfe  mov     ebx, 8007000Eh
0x140003d03  jmp     short loc_140003CE8
0x140003d05  mov     eax, 80004003h
0x140003d0a  mov     rcx, [rsp+0A8h+var_38]
0x140003d0f  xor     rcx, rsp; StackCookie
0x140003d12  call    __security_check_cookie
0x140003d17  mov     rbx, [rsp+0A8h+arg_8]
0x140003d1f  add     rsp, 80h
0x140003d26  pop     r15
0x140003d28  pop     r14
0x140003d2a  pop     rdi
0x140003d2b  pop     rsi
0x140003d2c  pop     rbp
0x140003d2d  retn
0x140003d2e  mov     ecx, 0C000008Ch; unsigned int
0x140003d33  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140003d38  int     3; Trap to Debugger
0x140003d39  mov     ecx, 80004005h; int
0x140003d3e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140003d44  mov     ecx, 80070057h; int
0x140003d49  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140003d4f  mov     ecx, 8007000Eh; int
0x140003d54  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
