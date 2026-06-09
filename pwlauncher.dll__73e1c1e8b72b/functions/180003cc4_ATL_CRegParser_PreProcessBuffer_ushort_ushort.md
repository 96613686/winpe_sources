# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003cc4`
- end: `0x180003f9f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004118`

## callees

- `0x18000314c`
- `0x18000374c`
- `0x180003cc4`
- `0x180005028`
- `0x18000fe10`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180003e07`
- `msvcrt!wcsncpy_s` at `0x180003e07`
- `USER32!CharNextW` at `0x180003d98`
- `USER32!CharNextW` at `0x180003dc9`
- `USER32!CharNextW` at `0x180003ed4`
- `USER32!CharNextW` at `0x180003efd`
- `USER32!CharNextW` at `0x180003d98`
- `USER32!CharNextW` at `0x180003dc9`
- `USER32!CharNextW` at `0x180003ed4`
- `USER32!CharNextW` at `0x180003efd`
- `KERNEL32!EnterCriticalSection` at `0x180003e3d`
- `KERNEL32!EnterCriticalSection` at `0x180003e3d`
- `KERNEL32!LeaveCriticalSection` at `0x180003e73`
- `KERNEL32!LeaveCriticalSection` at `0x180003e73`
- `KERNEL32!lstrcmpiW` at `0x180003e5b`
- `KERNEL32!lstrcmpiW` at `0x180003e5b`
- `ole32!CoTaskMemAlloc` at `0x180003d4e`
- `ole32!CoTaskMemAlloc` at `0x180003d4e`
- `ole32!CoTaskMemFree` at `0x180003d6c`
- `ole32!CoTaskMemFree` at `0x180003f28`
- `ole32!CoTaskMemFree` at `0x180003d6c`
- `ole32!CoTaskMemFree` at `0x180003f28`

## pseudocode

```c
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
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  const WCHAR *i; // rax
  unsigned int v24; // ebx
  _DWORD v25[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h]
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
  v25[0] = 0;
  v25[1] = v7;
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
    v24 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v15, 1) )
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
    v24 = -2147467259;
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
LABEL_54:
    v24 = -2147352567;
    goto LABEL_52;
  }
  v27 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v21, v22) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v24 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v24;
}

```

## disassembly

```asm
0x180003cc4  mov     [rsp-8+arg_8], rbx
0x180003cc9  push    rbp
0x180003cca  push    rsi
0x180003ccb  push    rdi
0x180003ccc  push    r12
0x180003cce  push    r13
0x180003cd0  push    r14
0x180003cd2  push    r15
0x180003cd4  lea     rbp, [rsp-27h]
0x180003cd9  sub     rsp, 90h
0x180003ce0  mov     rax, cs:__security_cookie
0x180003ce7  xor     rax, rsp
0x180003cea  mov     [rbp+57h+var_40], rax
0x180003cee  mov     r12, r8
0x180003cf1  mov     rbx, rdx
0x180003cf4  mov     r14, rcx
0x180003cf7  xor     r13d, r13d
0x180003cfa  test    rdx, rdx
0x180003cfd  jz      loc_180003F47
0x180003d03  test    r8, r8
0x180003d06  jz      loc_180003F47
0x180003d0c  mov     [r8], r13
0x180003d0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d13  inc     rax
0x180003d16  cmp     [rdx+rax*2], r13w
0x180003d1b  jnz     short loc_180003D13
0x180003d1d  add     eax, eax
0x180003d1f  mov     ecx, 3E8h
0x180003d24  cmp     eax, 64h ; 'd'
0x180003d27  cmovl   eax, ecx
0x180003d2a  mov     [rbp+57h+var_A0], r13d
0x180003d2e  mov     [rbp+57h+var_9C], eax
0x180003d31  mov     ecx, eax
0x180003d33  add     rcx, rcx
0x180003d36  mov     eax, 0FFFFFFFFh
0x180003d3b  cmp     rcx, rax
0x180003d3e  jbe     short loc_180003D4C
0x180003d40  mov     rax, r13
0x180003d43  mov     rdx, r13
0x180003d46  mov     [rbp+57h+pv], rdx
0x180003d4a  jmp     short loc_180003D64
0x180003d4c  mov     ecx, ecx; cb
0x180003d4e  call    cs:__imp_CoTaskMemAlloc
0x180003d54  mov     rdx, rax
0x180003d57  mov     [rbp+57h+pv], rax
0x180003d5b  test    rax, rax
0x180003d5e  jz      short loc_180003D64
0x180003d60  mov     [rax], r13w
0x180003d64  test    rax, rax
0x180003d67  jnz     short loc_180003D7C
0x180003d69  mov     rcx, rax; pv
0x180003d6c  call    cs:__imp_CoTaskMemFree
0x180003d72  mov     eax, 8007000Eh
0x180003d77  jmp     loc_180003F4C
0x180003d7c  mov     [r14], rbx
0x180003d7f  movzx   eax, word ptr [rbx]
0x180003d82  test    ax, ax
0x180003d85  jz      loc_180003F19
0x180003d8b  cmp     ax, 25h ; '%'
0x180003d8f  jnz     loc_180003EE4
0x180003d95  mov     rcx, rbx; lpsz
0x180003d98  call    cs:__imp_CharNextW
0x180003d9e  mov     [r14], rax
0x180003da1  movzx   ecx, word ptr [rax]
0x180003da4  cmp     cx, 25h ; '%'
0x180003da8  jnz     short loc_180003DB2
0x180003daa  mov     rdx, rax
0x180003dad  jmp     loc_180003EE7
0x180003db2  test    rax, rax
0x180003db5  jz      loc_180003F39
0x180003dbb  mov     rdi, r13
0x180003dbe  jmp     short loc_180003DD2
0x180003dc0  cmp     cx, 25h ; '%'
0x180003dc4  jz      short loc_180003DD9
0x180003dc6  mov     rcx, rax; lpsz
0x180003dc9  call    cs:__imp_CharNextW
0x180003dcf  movzx   ecx, word ptr [rax]
0x180003dd2  test    cx, cx
0x180003dd5  jnz     short loc_180003DC0
0x180003dd7  jmp     short loc_180003DDC
0x180003dd9  mov     rdi, rax
0x180003ddc  test    rdi, rdi
0x180003ddf  jz      loc_180003F39
0x180003de5  mov     rax, rdi
0x180003de8  sub     rax, [r14]
0x180003deb  sar     rax, 1
0x180003dee  cmp     rax, 1Fh
0x180003df2  jg      loc_180003F32
0x180003df8  movsxd  r9, eax; MaxCount
0x180003dfb  mov     r8, [r14]; Source
0x180003dfe  mov     edx, 20h ; ' '; SizeInWords
0x180003e03  lea     rcx, [rbp+57h+Destination]; Destination
0x180003e07  call    cs:__imp_wcsncpy_s
0x180003e0d  test    eax, eax
0x180003e0f  jz      short loc_180003E35
0x180003e11  cmp     eax, 0Ch
0x180003e14  jz      loc_180003F94
0x180003e1a  cmp     eax, 16h
0x180003e1d  jz      loc_180003F89
0x180003e23  cmp     eax, 22h ; '"'
0x180003e26  jz      loc_180003F89
0x180003e2c  cmp     eax, 50h ; 'P'
0x180003e2f  jnz     loc_180003F7E
0x180003e35  mov     rsi, [r14+8]
0x180003e39  lea     rcx, [rsi+20h]; lpCriticalSection
0x180003e3d  call    cs:__imp_EnterCriticalSection
0x180003e43  mov     ebx, r13d
0x180003e46  cmp     [rsi+18h], r13d
0x180003e4a  jle     short loc_180003E6C
0x180003e4c  movsxd  rax, ebx
0x180003e4f  mov     rcx, [rsi+8]
0x180003e53  lea     rdx, [rbp+57h+Destination]; lpString2
0x180003e57  mov     rcx, [rcx+rax*8]; lpString1
0x180003e5b  call    cs:__imp_lstrcmpiW
0x180003e61  test    eax, eax
0x180003e63  jz      short loc_180003EAE
0x180003e65  inc     ebx
0x180003e67  cmp     ebx, [rsi+18h]
0x180003e6a  jl      short loc_180003E4C
0x180003e6c  mov     rbx, r13
0x180003e6f  lea     rcx, [rsi+20h]; lpCriticalSection
0x180003e73  call    cs:__imp_LeaveCriticalSection
0x180003e79  test    rbx, rbx
0x180003e7c  jz      loc_180003F39
0x180003e82  mov     [rbp+57h+var_90], r13
0x180003e86  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003e8a  inc     r8; int
0x180003e8d  cmp     [rbx+r8*2], r13w
0x180003e92  jnz     short loc_180003E8A
0x180003e94  mov     rdx, rbx; unsigned __int16 *
0x180003e97  lea     rcx, [rbp+57h+var_A0]; this
0x180003e9b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003ea0  nop
0x180003ea1  test    eax, eax
0x180003ea3  jz      loc_180003F40
0x180003ea9  mov     rax, [r14]
0x180003eac  jmp     short loc_180003EDD
0x180003eae  cmp     ebx, 0FFFFFFFFh
0x180003eb1  jz      short loc_180003E6C
0x180003eb3  test    ebx, ebx
0x180003eb5  js      loc_180003F73
0x180003ebb  cmp     ebx, [rsi+18h]
0x180003ebe  jge     loc_180003F73
0x180003ec4  movsxd  rcx, ebx
0x180003ec7  mov     rax, [rsi+10h]
0x180003ecb  mov     rbx, [rax+rcx*8]
0x180003ecf  jmp     short loc_180003E6F
0x180003ed1  mov     rcx, rax; lpsz
0x180003ed4  call    cs:__imp_CharNextW
0x180003eda  mov     [r14], rax
0x180003edd  cmp     rax, rdi
0x180003ee0  jnz     short loc_180003ED1
0x180003ee2  jmp     short loc_180003EFA
0x180003ee4  mov     rdx, rbx; unsigned __int16 *
0x180003ee7  mov     r8d, 1; int
0x180003eed  lea     rcx, [rbp+57h+var_A0]; this
0x180003ef1  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003ef6  test    eax, eax
0x180003ef8  jz      short loc_180003F40
0x180003efa  mov     rcx, [r14]; lpsz
0x180003efd  call    cs:__imp_CharNextW
0x180003f03  mov     rbx, rax
0x180003f06  mov     [r14], rax
0x180003f09  movzx   eax, word ptr [rax]
0x180003f0c  test    ax, ax
0x180003f0f  jnz     loc_180003D8B
0x180003f15  mov     rdx, [rbp+57h+pv]
0x180003f19  mov     ebx, r13d
0x180003f1c  mov     [rbp+57h+pv], r13
0x180003f20  mov     [r12], rdx
0x180003f24  mov     rcx, [rbp+57h+pv]; pv
0x180003f28  call    cs:__imp_CoTaskMemFree
0x180003f2e  mov     eax, ebx
0x180003f30  jmp     short loc_180003F4C
0x180003f32  mov     ebx, 80004005h
0x180003f37  jmp     short loc_180003F24
0x180003f39  mov     ebx, 80020009h
0x180003f3e  jmp     short loc_180003F24
0x180003f40  mov     ebx, 8007000Eh
0x180003f45  jmp     short loc_180003F24
0x180003f47  mov     eax, 80004003h
0x180003f4c  mov     rcx, [rbp+57h+var_40]
0x180003f50  xor     rcx, rsp; StackCookie
0x180003f53  call    __security_check_cookie
0x180003f58  mov     rbx, [rsp+0C0h+arg_8]
0x180003f60  add     rsp, 90h
0x180003f67  pop     r15
0x180003f69  pop     r14
0x180003f6b  pop     r13
0x180003f6d  pop     r12
0x180003f6f  pop     rdi
0x180003f70  pop     rsi
0x180003f71  pop     rbp
0x180003f72  retn
0x180003f73  mov     ecx, 0C000008Ch; unsigned int
0x180003f78  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003f7d  int     3; Trap to Debugger
0x180003f7e  mov     ecx, 80004005h; int
0x180003f83  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f89  mov     ecx, 80070057h; int
0x180003f8e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f94  mov     ecx, 8007000Eh; int
0x180003f99  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
