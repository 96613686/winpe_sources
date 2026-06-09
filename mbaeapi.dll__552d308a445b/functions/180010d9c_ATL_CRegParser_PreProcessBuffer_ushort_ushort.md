# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180010d9c`
- end: `0x180011054`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011758`

## callees

- `0x1800024e0`
- `0x18000e300`
- `0x18000ec4c`
- `0x180010d9c`
- `0x180013354`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010edd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010edd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010e46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010e46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fe3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010e72`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010ea3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010f90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010fb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010e72`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010ea3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010f90`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010fb9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010f27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010f27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
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
  int v17; // eax
  __int64 v18; // rdi
  int v19; // ebx
  int v20; // edx
  unsigned int v21; // r8d
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
  _DWORD v26[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v28; // [rsp+30h] [rbp-29h]
  WCHAR String2[32]; // [rsp+40h] [rbp-19h] BYREF

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
  *(_QWORD *)this = v4;
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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
        break;
      goto LABEL_48;
    }
    v13 = CharNextW(v4);
    *(_QWORD *)this = v13;
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
    if ( ((__int64)v16 - *(_QWORD *)this) >> 1 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_51;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this);
    if ( v17 )
    {
      if ( v17 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v17 == 22 || v17 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v17 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v18 = *((_QWORD *)this + 1);
    v19 = 0;
    if ( *(int *)(v18 + 24) <= 0 )
      goto LABEL_34;
    while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)(v18 + 8) + 8LL * v19), String2) )
    {
      if ( ++v19 >= *(_DWORD *)(v18 + 24) )
        goto LABEL_34;
    }
    if ( v19 == -1 )
      goto LABEL_34;
    if ( v19 < 0 || v19 >= *(_DWORD *)(v18 + 24) )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v20, v21);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*(_QWORD *)(v18 + 16) + 8LL * v19);
    if ( !v23 )
      goto LABEL_34;
    v28 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v23, v24) )
      break;
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_48:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
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
0x180010d9c  mov     [rsp-8+arg_8], rbx
0x180010da1  mov     [rsp-8+arg_18], rsi
0x180010da6  push    rbp
0x180010da7  push    rdi
0x180010da8  push    r12
0x180010daa  push    r14
0x180010dac  push    r15
0x180010dae  lea     rbp, [rsp-37h]
0x180010db3  sub     rsp, 90h
0x180010dba  mov     rax, cs:__security_cookie
0x180010dc1  xor     rax, rsp
0x180010dc4  mov     [rbp+57h+var_30], rax
0x180010dc8  mov     r15, r8
0x180010dcb  mov     rbx, rdx
0x180010dce  mov     r14, rcx
0x180010dd1  xor     r12d, r12d
0x180010dd4  test    rdx, rdx
0x180010dd7  jz      loc_180010FFB
0x180010ddd  test    r8, r8
0x180010de0  jz      loc_180010FFB
0x180010de6  mov     [r8], r12
0x180010de9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ded  inc     rax
0x180010df0  cmp     [rdx+rax*2], r12w
0x180010df5  jnz     short loc_180010DED
0x180010df7  add     eax, eax
0x180010df9  mov     ecx, 3E8h
0x180010dfe  cmp     eax, 64h ; 'd'
0x180010e01  cmovl   eax, ecx
0x180010e04  mov     [rbp+57h+var_90], r12d
0x180010e08  mov     [rbp+57h+var_8C], eax
0x180010e0b  mov     ecx, eax
0x180010e0d  add     rcx, rcx
0x180010e10  mov     eax, 0FFFFFFFFh
0x180010e15  cmp     rcx, rax
0x180010e18  jbe     short loc_180010E26
0x180010e1a  mov     rax, r12
0x180010e1d  mov     rdx, r12
0x180010e20  mov     [rbp+57h+pv], rdx
0x180010e24  jmp     short loc_180010E3E
0x180010e26  mov     ecx, ecx; cb
0x180010e28  call    cs:__imp_CoTaskMemAlloc
0x180010e2e  mov     rdx, rax
0x180010e31  mov     [rbp+57h+pv], rax
0x180010e35  test    rax, rax
0x180010e38  jz      short loc_180010E3E
0x180010e3a  mov     [rax], r12w
0x180010e3e  test    rax, rax
0x180010e41  jnz     short loc_180010E56
0x180010e43  mov     rcx, rax; pv
0x180010e46  call    cs:__imp_CoTaskMemFree
0x180010e4c  mov     eax, 8007000Eh
0x180010e51  jmp     loc_180011000
0x180010e56  mov     [r14], rbx
0x180010e59  movzx   eax, word ptr [rbx]
0x180010e5c  test    ax, ax
0x180010e5f  jz      loc_180010FD5
0x180010e65  cmp     ax, 25h ; '%'
0x180010e69  jnz     loc_180010FA0
0x180010e6f  mov     rcx, rbx; lpsz
0x180010e72  call    cs:__imp_CharNextW
0x180010e78  mov     [r14], rax
0x180010e7b  movzx   ecx, word ptr [rax]
0x180010e7e  cmp     cx, 25h ; '%'
0x180010e82  jnz     short loc_180010E8C
0x180010e84  mov     rdx, rax
0x180010e87  jmp     loc_180010FA3
0x180010e8c  test    rax, rax
0x180010e8f  jz      loc_180010F38
0x180010e95  mov     rsi, r12
0x180010e98  jmp     short loc_180010EAC
0x180010e9a  cmp     cx, 25h ; '%'
0x180010e9e  jz      short loc_180010EB3
0x180010ea0  mov     rcx, rax; lpsz
0x180010ea3  call    cs:__imp_CharNextW
0x180010ea9  movzx   ecx, word ptr [rax]
0x180010eac  test    cx, cx
0x180010eaf  jnz     short loc_180010E9A
0x180010eb1  jmp     short loc_180010EB6
0x180010eb3  mov     rsi, rax
0x180010eb6  test    rsi, rsi
0x180010eb9  jz      short loc_180010F38
0x180010ebb  mov     rax, rsi
0x180010ebe  sub     rax, [r14]
0x180010ec1  sar     rax, 1
0x180010ec4  cmp     rax, 1Fh
0x180010ec8  jg      loc_180010FED
0x180010ece  movsxd  r9, eax
0x180010ed1  mov     r8, [r14]
0x180010ed4  mov     edx, 20h ; ' '
0x180010ed9  lea     rcx, [rbp+57h+String2]
0x180010edd  call    cs:__imp__o_wcsncpy_s
0x180010ee3  test    eax, eax
0x180010ee5  jz      short loc_180010F0B
0x180010ee7  cmp     eax, 0Ch
0x180010eea  jz      loc_180011049
0x180010ef0  cmp     eax, 16h
0x180010ef3  jz      loc_18001103E
0x180010ef9  cmp     eax, 22h ; '"'
0x180010efc  jz      loc_18001103E
0x180010f02  cmp     eax, 50h ; 'P'
0x180010f05  jnz     loc_180011033
0x180010f0b  mov     rdi, [r14+8]
0x180010f0f  mov     ebx, r12d
0x180010f12  cmp     [rdi+18h], r12d
0x180010f16  jle     short loc_180010F38
0x180010f18  movsxd  rax, ebx
0x180010f1b  mov     rcx, [rdi+8]
0x180010f1f  lea     rdx, [rbp+57h+String2]; lpString2
0x180010f23  mov     rcx, [rcx+rax*8]; lpString1
0x180010f27  call    cs:__imp_lstrcmpiW
0x180010f2d  test    eax, eax
0x180010f2f  jz      short loc_180010F42
0x180010f31  inc     ebx
0x180010f33  cmp     ebx, [rdi+18h]
0x180010f36  jl      short loc_180010F18
0x180010f38  mov     ebx, 80020009h
0x180010f3d  jmp     loc_180010FDF
0x180010f42  cmp     ebx, 0FFFFFFFFh
0x180010f45  jz      short loc_180010F38
0x180010f47  test    ebx, ebx
0x180010f49  js      loc_180011028
0x180010f4f  cmp     ebx, [rdi+18h]
0x180010f52  jge     loc_180011028
0x180010f58  movsxd  rcx, ebx
0x180010f5b  mov     rax, [rdi+10h]
0x180010f5f  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180010f63  test    rdx, rdx
0x180010f66  jz      short loc_180010F38
0x180010f68  mov     [rbp+57h+var_80], r12
0x180010f6c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010f70  inc     r8; int
0x180010f73  cmp     [rdx+r8*2], r12w
0x180010f78  jnz     short loc_180010F70
0x180010f7a  lea     rcx, [rbp+57h+var_90]; this
0x180010f7e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180010f83  nop
0x180010f84  test    eax, eax
0x180010f86  jz      short loc_180010FF4
0x180010f88  mov     rax, [r14]
0x180010f8b  jmp     short loc_180010F99
0x180010f8d  mov     rcx, rax; lpsz
0x180010f90  call    cs:__imp_CharNextW
0x180010f96  mov     [r14], rax
0x180010f99  cmp     rax, rsi
0x180010f9c  jnz     short loc_180010F8D
0x180010f9e  jmp     short loc_180010FB6
0x180010fa0  mov     rdx, rbx; unsigned __int16 *
0x180010fa3  mov     r8d, 1; int
0x180010fa9  lea     rcx, [rbp+57h+var_90]; this
0x180010fad  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180010fb2  test    eax, eax
0x180010fb4  jz      short loc_180010FF4
0x180010fb6  mov     rcx, [r14]; lpsz
0x180010fb9  call    cs:__imp_CharNextW
0x180010fbf  mov     rbx, rax
0x180010fc2  mov     [r14], rax
0x180010fc5  movzx   eax, word ptr [rax]
0x180010fc8  test    ax, ax
0x180010fcb  jnz     loc_180010E65
0x180010fd1  mov     rdx, [rbp+57h+pv]
0x180010fd5  mov     ebx, r12d
0x180010fd8  mov     [rbp+57h+pv], r12
0x180010fdc  mov     [r15], rdx
0x180010fdf  mov     rcx, [rbp+57h+pv]; pv
0x180010fe3  call    cs:__imp_CoTaskMemFree
0x180010fe9  mov     eax, ebx
0x180010feb  jmp     short loc_180011000
0x180010fed  mov     ebx, 80004005h
0x180010ff2  jmp     short loc_180010FDF
0x180010ff4  mov     ebx, 8007000Eh
0x180010ff9  jmp     short loc_180010FDF
0x180010ffb  mov     eax, 80004003h
0x180011000  mov     rcx, [rbp+57h+var_30]
0x180011004  xor     rcx, rsp; StackCookie
0x180011007  call    __security_check_cookie
0x18001100c  lea     r11, [rsp+0B0h+var_20]
0x180011014  mov     rbx, [r11+38h]
0x180011018  mov     rsi, [r11+48h]
0x18001101c  mov     rsp, r11
0x18001101f  pop     r15
0x180011021  pop     r14
0x180011023  pop     r12
0x180011025  pop     rdi
0x180011026  pop     rbp
0x180011027  retn
0x180011028  mov     ecx, 0C000008Ch; this
0x18001102d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180011032  int     3; Trap to Debugger
0x180011033  mov     ecx, 80004005h; int
0x180011038  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001103e  mov     ecx, 80070057h; int
0x180011043  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011049  mov     ecx, 8007000Eh; int
0x18001104e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
