# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003cec`
- end: `0x180003fc7`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004298`

## callees

- `0x180002f7c`
- `0x1800030b4`
- `0x180003cec`
- `0x180005328`
- `0x180009a00`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180003e2f`
- `msvcrt!wcsncpy_s` at `0x180003e2f`
- `KERNEL32!EnterCriticalSection` at `0x180003e65`
- `KERNEL32!EnterCriticalSection` at `0x180003e65`
- `KERNEL32!LeaveCriticalSection` at `0x180003e9b`
- `KERNEL32!LeaveCriticalSection` at `0x180003e9b`
- `KERNEL32!lstrcmpiW` at `0x180003e83`
- `KERNEL32!lstrcmpiW` at `0x180003e83`
- `USER32!CharNextW` at `0x180003dc0`
- `USER32!CharNextW` at `0x180003df1`
- `USER32!CharNextW` at `0x180003efc`
- `USER32!CharNextW` at `0x180003f25`
- `USER32!CharNextW` at `0x180003dc0`
- `USER32!CharNextW` at `0x180003df1`
- `USER32!CharNextW` at `0x180003efc`
- `USER32!CharNextW` at `0x180003f25`
- `ole32!CoTaskMemFree` at `0x180003d94`
- `ole32!CoTaskMemFree` at `0x180003f50`
- `ole32!CoTaskMemFree` at `0x180003d94`
- `ole32!CoTaskMemFree` at `0x180003f50`
- `ole32!CoTaskMemAlloc` at `0x180003d76`
- `ole32!CoTaskMemAlloc` at `0x180003d76`

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
0x180003cec  mov     [rsp-8+arg_8], rbx
0x180003cf1  push    rbp
0x180003cf2  push    rsi
0x180003cf3  push    rdi
0x180003cf4  push    r12
0x180003cf6  push    r13
0x180003cf8  push    r14
0x180003cfa  push    r15
0x180003cfc  lea     rbp, [rsp-27h]
0x180003d01  sub     rsp, 90h
0x180003d08  mov     rax, cs:__security_cookie
0x180003d0f  xor     rax, rsp
0x180003d12  mov     [rbp+57h+var_40], rax
0x180003d16  mov     r12, r8
0x180003d19  mov     rbx, rdx
0x180003d1c  mov     r14, rcx
0x180003d1f  xor     r13d, r13d
0x180003d22  test    rdx, rdx
0x180003d25  jz      loc_180003F6F
0x180003d2b  test    r8, r8
0x180003d2e  jz      loc_180003F6F
0x180003d34  mov     [r8], r13
0x180003d37  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003d3b  inc     rax
0x180003d3e  cmp     [rdx+rax*2], r13w
0x180003d43  jnz     short loc_180003D3B
0x180003d45  add     eax, eax
0x180003d47  mov     ecx, 3E8h
0x180003d4c  cmp     eax, 64h ; 'd'
0x180003d4f  cmovl   eax, ecx
0x180003d52  mov     [rbp+57h+var_A0], r13d
0x180003d56  mov     [rbp+57h+var_9C], eax
0x180003d59  mov     ecx, eax
0x180003d5b  add     rcx, rcx
0x180003d5e  mov     eax, 0FFFFFFFFh
0x180003d63  cmp     rcx, rax
0x180003d66  jbe     short loc_180003D74
0x180003d68  mov     rax, r13
0x180003d6b  mov     rdx, r13
0x180003d6e  mov     [rbp+57h+pv], rdx
0x180003d72  jmp     short loc_180003D8C
0x180003d74  mov     ecx, ecx; cb
0x180003d76  call    cs:__imp_CoTaskMemAlloc
0x180003d7c  mov     rdx, rax
0x180003d7f  mov     [rbp+57h+pv], rax
0x180003d83  test    rax, rax
0x180003d86  jz      short loc_180003D8C
0x180003d88  mov     [rax], r13w
0x180003d8c  test    rax, rax
0x180003d8f  jnz     short loc_180003DA4
0x180003d91  mov     rcx, rax; pv
0x180003d94  call    cs:__imp_CoTaskMemFree
0x180003d9a  mov     eax, 8007000Eh
0x180003d9f  jmp     loc_180003F74
0x180003da4  mov     [r14], rbx
0x180003da7  movzx   eax, word ptr [rbx]
0x180003daa  test    ax, ax
0x180003dad  jz      loc_180003F41
0x180003db3  cmp     ax, 25h ; '%'
0x180003db7  jnz     loc_180003F0C
0x180003dbd  mov     rcx, rbx; lpsz
0x180003dc0  call    cs:__imp_CharNextW
0x180003dc6  mov     [r14], rax
0x180003dc9  movzx   ecx, word ptr [rax]
0x180003dcc  cmp     cx, 25h ; '%'
0x180003dd0  jnz     short loc_180003DDA
0x180003dd2  mov     rdx, rax
0x180003dd5  jmp     loc_180003F0F
0x180003dda  test    rax, rax
0x180003ddd  jz      loc_180003F61
0x180003de3  mov     rdi, r13
0x180003de6  jmp     short loc_180003DFA
0x180003de8  cmp     cx, 25h ; '%'
0x180003dec  jz      short loc_180003E01
0x180003dee  mov     rcx, rax; lpsz
0x180003df1  call    cs:__imp_CharNextW
0x180003df7  movzx   ecx, word ptr [rax]
0x180003dfa  test    cx, cx
0x180003dfd  jnz     short loc_180003DE8
0x180003dff  jmp     short loc_180003E04
0x180003e01  mov     rdi, rax
0x180003e04  test    rdi, rdi
0x180003e07  jz      loc_180003F61
0x180003e0d  mov     rax, rdi
0x180003e10  sub     rax, [r14]
0x180003e13  sar     rax, 1
0x180003e16  cmp     rax, 1Fh
0x180003e1a  jg      loc_180003F5A
0x180003e20  movsxd  r9, eax; MaxCount
0x180003e23  mov     r8, [r14]; Source
0x180003e26  mov     edx, 20h ; ' '; SizeInWords
0x180003e2b  lea     rcx, [rbp+57h+Destination]; Destination
0x180003e2f  call    cs:__imp_wcsncpy_s
0x180003e35  test    eax, eax
0x180003e37  jz      short loc_180003E5D
0x180003e39  cmp     eax, 0Ch
0x180003e3c  jz      loc_180003FBC
0x180003e42  cmp     eax, 16h
0x180003e45  jz      loc_180003FB1
0x180003e4b  cmp     eax, 22h ; '"'
0x180003e4e  jz      loc_180003FB1
0x180003e54  cmp     eax, 50h ; 'P'
0x180003e57  jnz     loc_180003FA6
0x180003e5d  mov     rsi, [r14+8]
0x180003e61  lea     rcx, [rsi+20h]; lpCriticalSection
0x180003e65  call    cs:__imp_EnterCriticalSection
0x180003e6b  mov     ebx, r13d
0x180003e6e  cmp     [rsi+18h], r13d
0x180003e72  jle     short loc_180003E94
0x180003e74  movsxd  rax, ebx
0x180003e77  mov     rcx, [rsi+8]
0x180003e7b  lea     rdx, [rbp+57h+Destination]; lpString2
0x180003e7f  mov     rcx, [rcx+rax*8]; lpString1
0x180003e83  call    cs:__imp_lstrcmpiW
0x180003e89  test    eax, eax
0x180003e8b  jz      short loc_180003ED6
0x180003e8d  inc     ebx
0x180003e8f  cmp     ebx, [rsi+18h]
0x180003e92  jl      short loc_180003E74
0x180003e94  mov     rbx, r13
0x180003e97  lea     rcx, [rsi+20h]; lpCriticalSection
0x180003e9b  call    cs:__imp_LeaveCriticalSection
0x180003ea1  test    rbx, rbx
0x180003ea4  jz      loc_180003F61
0x180003eaa  mov     [rbp+57h+var_90], r13
0x180003eae  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003eb2  inc     r8; int
0x180003eb5  cmp     [rbx+r8*2], r13w
0x180003eba  jnz     short loc_180003EB2
0x180003ebc  mov     rdx, rbx; unsigned __int16 *
0x180003ebf  lea     rcx, [rbp+57h+var_A0]; this
0x180003ec3  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003ec8  nop
0x180003ec9  test    eax, eax
0x180003ecb  jz      loc_180003F68
0x180003ed1  mov     rax, [r14]
0x180003ed4  jmp     short loc_180003F05
0x180003ed6  cmp     ebx, 0FFFFFFFFh
0x180003ed9  jz      short loc_180003E94
0x180003edb  test    ebx, ebx
0x180003edd  js      loc_180003F9B
0x180003ee3  cmp     ebx, [rsi+18h]
0x180003ee6  jge     loc_180003F9B
0x180003eec  movsxd  rcx, ebx
0x180003eef  mov     rax, [rsi+10h]
0x180003ef3  mov     rbx, [rax+rcx*8]
0x180003ef7  jmp     short loc_180003E97
0x180003ef9  mov     rcx, rax; lpsz
0x180003efc  call    cs:__imp_CharNextW
0x180003f02  mov     [r14], rax
0x180003f05  cmp     rax, rdi
0x180003f08  jnz     short loc_180003EF9
0x180003f0a  jmp     short loc_180003F22
0x180003f0c  mov     rdx, rbx; unsigned __int16 *
0x180003f0f  mov     r8d, 1; int
0x180003f15  lea     rcx, [rbp+57h+var_A0]; this
0x180003f19  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003f1e  test    eax, eax
0x180003f20  jz      short loc_180003F68
0x180003f22  mov     rcx, [r14]; lpsz
0x180003f25  call    cs:__imp_CharNextW
0x180003f2b  mov     rbx, rax
0x180003f2e  mov     [r14], rax
0x180003f31  movzx   eax, word ptr [rax]
0x180003f34  test    ax, ax
0x180003f37  jnz     loc_180003DB3
0x180003f3d  mov     rdx, [rbp+57h+pv]
0x180003f41  mov     ebx, r13d
0x180003f44  mov     [rbp+57h+pv], r13
0x180003f48  mov     [r12], rdx
0x180003f4c  mov     rcx, [rbp+57h+pv]; pv
0x180003f50  call    cs:__imp_CoTaskMemFree
0x180003f56  mov     eax, ebx
0x180003f58  jmp     short loc_180003F74
0x180003f5a  mov     ebx, 80004005h
0x180003f5f  jmp     short loc_180003F4C
0x180003f61  mov     ebx, 80020009h
0x180003f66  jmp     short loc_180003F4C
0x180003f68  mov     ebx, 8007000Eh
0x180003f6d  jmp     short loc_180003F4C
0x180003f6f  mov     eax, 80004003h
0x180003f74  mov     rcx, [rbp+57h+var_40]
0x180003f78  xor     rcx, rsp; StackCookie
0x180003f7b  call    __security_check_cookie
0x180003f80  mov     rbx, [rsp+0C0h+arg_8]
0x180003f88  add     rsp, 90h
0x180003f8f  pop     r15
0x180003f91  pop     r14
0x180003f93  pop     r13
0x180003f95  pop     r12
0x180003f97  pop     rdi
0x180003f98  pop     rsi
0x180003f99  pop     rbp
0x180003f9a  retn
0x180003f9b  mov     ecx, 0C000008Ch; unsigned int
0x180003fa0  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003fa5  int     3; Trap to Debugger
0x180003fa6  mov     ecx, 80004005h; int
0x180003fab  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003fb1  mov     ecx, 80070057h; int
0x180003fb6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003fbc  mov     ecx, 8007000Eh; int
0x180003fc1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
