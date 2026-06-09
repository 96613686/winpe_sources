# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180005ae4`
- end: `0x180005dbf`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180005f38`

## callees

- `0x180004cfc`
- `0x180005688`
- `0x180005ae4`
- `0x180006f84`
- `0x18001f690`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005c27`
- `msvcrt!wcsncpy_s` at `0x180005c27`
- `KERNEL32!EnterCriticalSection` at `0x180005c5d`
- `KERNEL32!EnterCriticalSection` at `0x180005c5d`
- `KERNEL32!lstrcmpiW` at `0x180005c7b`
- `KERNEL32!lstrcmpiW` at `0x180005c7b`
- `KERNEL32!LeaveCriticalSection` at `0x180005c93`
- `KERNEL32!LeaveCriticalSection` at `0x180005c93`
- `USER32!CharNextW` at `0x180005bb8`
- `USER32!CharNextW` at `0x180005be9`
- `USER32!CharNextW` at `0x180005cf4`
- `USER32!CharNextW` at `0x180005d1d`
- `USER32!CharNextW` at `0x180005bb8`
- `USER32!CharNextW` at `0x180005be9`
- `USER32!CharNextW` at `0x180005cf4`
- `USER32!CharNextW` at `0x180005d1d`
- `ole32!CoTaskMemAlloc` at `0x180005b6e`
- `ole32!CoTaskMemAlloc` at `0x180005b6e`
- `ole32!CoTaskMemFree` at `0x180005b8c`
- `ole32!CoTaskMemFree` at `0x180005d48`
- `ole32!CoTaskMemFree` at `0x180005b8c`
- `ole32!CoTaskMemFree` at `0x180005d48`

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
0x180005ae4  mov     [rsp-8+arg_8], rbx
0x180005ae9  push    rbp
0x180005aea  push    rsi
0x180005aeb  push    rdi
0x180005aec  push    r12
0x180005aee  push    r13
0x180005af0  push    r14
0x180005af2  push    r15
0x180005af4  lea     rbp, [rsp-27h]
0x180005af9  sub     rsp, 90h
0x180005b00  mov     rax, cs:__security_cookie
0x180005b07  xor     rax, rsp
0x180005b0a  mov     [rbp+57h+var_40], rax
0x180005b0e  mov     r12, r8
0x180005b11  mov     rbx, rdx
0x180005b14  mov     r14, rcx
0x180005b17  xor     r13d, r13d
0x180005b1a  test    rdx, rdx
0x180005b1d  jz      loc_180005D67
0x180005b23  test    r8, r8
0x180005b26  jz      loc_180005D67
0x180005b2c  mov     [r8], r13
0x180005b2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005b33  inc     rax
0x180005b36  cmp     [rdx+rax*2], r13w
0x180005b3b  jnz     short loc_180005B33
0x180005b3d  add     eax, eax
0x180005b3f  mov     ecx, 3E8h
0x180005b44  cmp     eax, 64h ; 'd'
0x180005b47  cmovl   eax, ecx
0x180005b4a  mov     [rbp+57h+var_A0], r13d
0x180005b4e  mov     [rbp+57h+var_9C], eax
0x180005b51  mov     ecx, eax
0x180005b53  add     rcx, rcx
0x180005b56  mov     eax, 0FFFFFFFFh
0x180005b5b  cmp     rcx, rax
0x180005b5e  jbe     short loc_180005B6C
0x180005b60  mov     rax, r13
0x180005b63  mov     rdx, r13
0x180005b66  mov     [rbp+57h+pv], rdx
0x180005b6a  jmp     short loc_180005B84
0x180005b6c  mov     ecx, ecx; cb
0x180005b6e  call    cs:__imp_CoTaskMemAlloc
0x180005b74  mov     rdx, rax
0x180005b77  mov     [rbp+57h+pv], rax
0x180005b7b  test    rax, rax
0x180005b7e  jz      short loc_180005B84
0x180005b80  mov     [rax], r13w
0x180005b84  test    rax, rax
0x180005b87  jnz     short loc_180005B9C
0x180005b89  mov     rcx, rax; pv
0x180005b8c  call    cs:__imp_CoTaskMemFree
0x180005b92  mov     eax, 8007000Eh
0x180005b97  jmp     loc_180005D6C
0x180005b9c  mov     [r14], rbx
0x180005b9f  movzx   eax, word ptr [rbx]
0x180005ba2  test    ax, ax
0x180005ba5  jz      loc_180005D39
0x180005bab  cmp     ax, 25h ; '%'
0x180005baf  jnz     loc_180005D04
0x180005bb5  mov     rcx, rbx; lpsz
0x180005bb8  call    cs:__imp_CharNextW
0x180005bbe  mov     [r14], rax
0x180005bc1  movzx   ecx, word ptr [rax]
0x180005bc4  cmp     cx, 25h ; '%'
0x180005bc8  jnz     short loc_180005BD2
0x180005bca  mov     rdx, rax
0x180005bcd  jmp     loc_180005D07
0x180005bd2  test    rax, rax
0x180005bd5  jz      loc_180005D59
0x180005bdb  mov     rdi, r13
0x180005bde  jmp     short loc_180005BF2
0x180005be0  cmp     cx, 25h ; '%'
0x180005be4  jz      short loc_180005BF9
0x180005be6  mov     rcx, rax; lpsz
0x180005be9  call    cs:__imp_CharNextW
0x180005bef  movzx   ecx, word ptr [rax]
0x180005bf2  test    cx, cx
0x180005bf5  jnz     short loc_180005BE0
0x180005bf7  jmp     short loc_180005BFC
0x180005bf9  mov     rdi, rax
0x180005bfc  test    rdi, rdi
0x180005bff  jz      loc_180005D59
0x180005c05  mov     rax, rdi
0x180005c08  sub     rax, [r14]
0x180005c0b  sar     rax, 1
0x180005c0e  cmp     rax, 1Fh
0x180005c12  jg      loc_180005D52
0x180005c18  movsxd  r9, eax; MaxCount
0x180005c1b  mov     r8, [r14]; Source
0x180005c1e  mov     edx, 20h ; ' '; SizeInWords
0x180005c23  lea     rcx, [rbp+57h+Destination]; Destination
0x180005c27  call    cs:__imp_wcsncpy_s
0x180005c2d  test    eax, eax
0x180005c2f  jz      short loc_180005C55
0x180005c31  cmp     eax, 0Ch
0x180005c34  jz      loc_180005DB4
0x180005c3a  cmp     eax, 16h
0x180005c3d  jz      loc_180005DA9
0x180005c43  cmp     eax, 22h ; '"'
0x180005c46  jz      loc_180005DA9
0x180005c4c  cmp     eax, 50h ; 'P'
0x180005c4f  jnz     loc_180005D9E
0x180005c55  mov     rsi, [r14+8]
0x180005c59  lea     rcx, [rsi+20h]; lpCriticalSection
0x180005c5d  call    cs:__imp_EnterCriticalSection
0x180005c63  mov     ebx, r13d
0x180005c66  cmp     [rsi+18h], r13d
0x180005c6a  jle     short loc_180005C8C
0x180005c6c  movsxd  rax, ebx
0x180005c6f  mov     rcx, [rsi+8]
0x180005c73  lea     rdx, [rbp+57h+Destination]; lpString2
0x180005c77  mov     rcx, [rcx+rax*8]; lpString1
0x180005c7b  call    cs:__imp_lstrcmpiW
0x180005c81  test    eax, eax
0x180005c83  jz      short loc_180005CCE
0x180005c85  inc     ebx
0x180005c87  cmp     ebx, [rsi+18h]
0x180005c8a  jl      short loc_180005C6C
0x180005c8c  mov     rbx, r13
0x180005c8f  lea     rcx, [rsi+20h]; lpCriticalSection
0x180005c93  call    cs:__imp_LeaveCriticalSection
0x180005c99  test    rbx, rbx
0x180005c9c  jz      loc_180005D59
0x180005ca2  mov     [rbp+57h+var_90], r13
0x180005ca6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005caa  inc     r8; int
0x180005cad  cmp     [rbx+r8*2], r13w
0x180005cb2  jnz     short loc_180005CAA
0x180005cb4  mov     rdx, rbx; unsigned __int16 *
0x180005cb7  lea     rcx, [rbp+57h+var_A0]; this
0x180005cbb  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180005cc0  nop
0x180005cc1  test    eax, eax
0x180005cc3  jz      loc_180005D60
0x180005cc9  mov     rax, [r14]
0x180005ccc  jmp     short loc_180005CFD
0x180005cce  cmp     ebx, 0FFFFFFFFh
0x180005cd1  jz      short loc_180005C8C
0x180005cd3  test    ebx, ebx
0x180005cd5  js      loc_180005D93
0x180005cdb  cmp     ebx, [rsi+18h]
0x180005cde  jge     loc_180005D93
0x180005ce4  movsxd  rcx, ebx
0x180005ce7  mov     rax, [rsi+10h]
0x180005ceb  mov     rbx, [rax+rcx*8]
0x180005cef  jmp     short loc_180005C8F
0x180005cf1  mov     rcx, rax; lpsz
0x180005cf4  call    cs:__imp_CharNextW
0x180005cfa  mov     [r14], rax
0x180005cfd  cmp     rax, rdi
0x180005d00  jnz     short loc_180005CF1
0x180005d02  jmp     short loc_180005D1A
0x180005d04  mov     rdx, rbx; unsigned __int16 *
0x180005d07  mov     r8d, 1; int
0x180005d0d  lea     rcx, [rbp+57h+var_A0]; this
0x180005d11  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180005d16  test    eax, eax
0x180005d18  jz      short loc_180005D60
0x180005d1a  mov     rcx, [r14]; lpsz
0x180005d1d  call    cs:__imp_CharNextW
0x180005d23  mov     rbx, rax
0x180005d26  mov     [r14], rax
0x180005d29  movzx   eax, word ptr [rax]
0x180005d2c  test    ax, ax
0x180005d2f  jnz     loc_180005BAB
0x180005d35  mov     rdx, [rbp+57h+pv]
0x180005d39  mov     ebx, r13d
0x180005d3c  mov     [rbp+57h+pv], r13
0x180005d40  mov     [r12], rdx
0x180005d44  mov     rcx, [rbp+57h+pv]; pv
0x180005d48  call    cs:__imp_CoTaskMemFree
0x180005d4e  mov     eax, ebx
0x180005d50  jmp     short loc_180005D6C
0x180005d52  mov     ebx, 80004005h
0x180005d57  jmp     short loc_180005D44
0x180005d59  mov     ebx, 80020009h
0x180005d5e  jmp     short loc_180005D44
0x180005d60  mov     ebx, 8007000Eh
0x180005d65  jmp     short loc_180005D44
0x180005d67  mov     eax, 80004003h
0x180005d6c  mov     rcx, [rbp+57h+var_40]
0x180005d70  xor     rcx, rsp; StackCookie
0x180005d73  call    __security_check_cookie
0x180005d78  mov     rbx, [rsp+0C0h+arg_8]
0x180005d80  add     rsp, 90h
0x180005d87  pop     r15
0x180005d89  pop     r14
0x180005d8b  pop     r13
0x180005d8d  pop     r12
0x180005d8f  pop     rdi
0x180005d90  pop     rsi
0x180005d91  pop     rbp
0x180005d92  retn
0x180005d93  mov     ecx, 0C000008Ch; unsigned int
0x180005d98  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180005d9d  int     3; Trap to Debugger
0x180005d9e  mov     ecx, 80004005h; int
0x180005da3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005da9  mov     ecx, 80070057h; int
0x180005dae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005db4  mov     ecx, 8007000Eh; int
0x180005db9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
