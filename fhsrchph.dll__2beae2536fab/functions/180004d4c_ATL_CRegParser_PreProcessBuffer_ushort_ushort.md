# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180004d4c`
- end: `0x180005027`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800052f8`

## callees

- `0x18000278c`
- `0x180002964`
- `0x180003dbc`
- `0x180004d4c`
- `0x18000ab60`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004e8f`
- `msvcrt!wcsncpy_s` at `0x180004e8f`
- `KERNEL32!EnterCriticalSection` at `0x180004ec5`
- `KERNEL32!EnterCriticalSection` at `0x180004ec5`
- `KERNEL32!LeaveCriticalSection` at `0x180004efb`
- `KERNEL32!LeaveCriticalSection` at `0x180004efb`
- `KERNEL32!lstrcmpiW` at `0x180004ee3`
- `KERNEL32!lstrcmpiW` at `0x180004ee3`
- `USER32!CharNextW` at `0x180004e20`
- `USER32!CharNextW` at `0x180004e51`
- `USER32!CharNextW` at `0x180004f5c`
- `USER32!CharNextW` at `0x180004f85`
- `USER32!CharNextW` at `0x180004e20`
- `USER32!CharNextW` at `0x180004e51`
- `USER32!CharNextW` at `0x180004f5c`
- `USER32!CharNextW` at `0x180004f85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004df4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004dd6`

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
0x180004d4c  mov     [rsp-8+arg_8], rbx
0x180004d51  push    rbp
0x180004d52  push    rsi
0x180004d53  push    rdi
0x180004d54  push    r12
0x180004d56  push    r13
0x180004d58  push    r14
0x180004d5a  push    r15
0x180004d5c  lea     rbp, [rsp-27h]
0x180004d61  sub     rsp, 90h
0x180004d68  mov     rax, cs:__security_cookie
0x180004d6f  xor     rax, rsp
0x180004d72  mov     [rbp+57h+var_40], rax
0x180004d76  mov     r12, r8
0x180004d79  mov     rbx, rdx
0x180004d7c  mov     r14, rcx
0x180004d7f  xor     r13d, r13d
0x180004d82  test    rdx, rdx
0x180004d85  jz      loc_180004FCF
0x180004d8b  test    r8, r8
0x180004d8e  jz      loc_180004FCF
0x180004d94  mov     [r8], r13
0x180004d97  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004d9b  inc     rax
0x180004d9e  cmp     [rdx+rax*2], r13w
0x180004da3  jnz     short loc_180004D9B
0x180004da5  add     eax, eax
0x180004da7  mov     ecx, 3E8h
0x180004dac  cmp     eax, 64h ; 'd'
0x180004daf  cmovl   eax, ecx
0x180004db2  mov     [rbp+57h+var_A0], r13d
0x180004db6  mov     [rbp+57h+var_9C], eax
0x180004db9  mov     ecx, eax
0x180004dbb  add     rcx, rcx
0x180004dbe  mov     eax, 0FFFFFFFFh
0x180004dc3  cmp     rcx, rax
0x180004dc6  jbe     short loc_180004DD4
0x180004dc8  mov     rax, r13
0x180004dcb  mov     rdx, r13
0x180004dce  mov     [rbp+57h+pv], rdx
0x180004dd2  jmp     short loc_180004DEC
0x180004dd4  mov     ecx, ecx; cb
0x180004dd6  call    cs:__imp_CoTaskMemAlloc
0x180004ddc  mov     rdx, rax
0x180004ddf  mov     [rbp+57h+pv], rax
0x180004de3  test    rax, rax
0x180004de6  jz      short loc_180004DEC
0x180004de8  mov     [rax], r13w
0x180004dec  test    rax, rax
0x180004def  jnz     short loc_180004E04
0x180004df1  mov     rcx, rax; pv
0x180004df4  call    cs:__imp_CoTaskMemFree
0x180004dfa  mov     eax, 8007000Eh
0x180004dff  jmp     loc_180004FD4
0x180004e04  mov     [r14], rbx
0x180004e07  movzx   eax, word ptr [rbx]
0x180004e0a  test    ax, ax
0x180004e0d  jz      loc_180004FA1
0x180004e13  cmp     ax, 25h ; '%'
0x180004e17  jnz     loc_180004F6C
0x180004e1d  mov     rcx, rbx; lpsz
0x180004e20  call    cs:__imp_CharNextW
0x180004e26  mov     [r14], rax
0x180004e29  movzx   ecx, word ptr [rax]
0x180004e2c  cmp     cx, 25h ; '%'
0x180004e30  jnz     short loc_180004E3A
0x180004e32  mov     rdx, rax
0x180004e35  jmp     loc_180004F6F
0x180004e3a  test    rax, rax
0x180004e3d  jz      loc_180004FC1
0x180004e43  mov     rdi, r13
0x180004e46  jmp     short loc_180004E5A
0x180004e48  cmp     cx, 25h ; '%'
0x180004e4c  jz      short loc_180004E61
0x180004e4e  mov     rcx, rax; lpsz
0x180004e51  call    cs:__imp_CharNextW
0x180004e57  movzx   ecx, word ptr [rax]
0x180004e5a  test    cx, cx
0x180004e5d  jnz     short loc_180004E48
0x180004e5f  jmp     short loc_180004E64
0x180004e61  mov     rdi, rax
0x180004e64  test    rdi, rdi
0x180004e67  jz      loc_180004FC1
0x180004e6d  mov     rax, rdi
0x180004e70  sub     rax, [r14]
0x180004e73  sar     rax, 1
0x180004e76  cmp     rax, 1Fh
0x180004e7a  jg      loc_180004FBA
0x180004e80  movsxd  r9, eax; MaxCount
0x180004e83  mov     r8, [r14]; Source
0x180004e86  mov     edx, 20h ; ' '; SizeInWords
0x180004e8b  lea     rcx, [rbp+57h+Destination]; Destination
0x180004e8f  call    cs:__imp_wcsncpy_s
0x180004e95  test    eax, eax
0x180004e97  jz      short loc_180004EBD
0x180004e99  cmp     eax, 0Ch
0x180004e9c  jz      loc_18000501C
0x180004ea2  cmp     eax, 16h
0x180004ea5  jz      loc_180005011
0x180004eab  cmp     eax, 22h ; '"'
0x180004eae  jz      loc_180005011
0x180004eb4  cmp     eax, 50h ; 'P'
0x180004eb7  jnz     loc_180005006
0x180004ebd  mov     rsi, [r14+8]
0x180004ec1  lea     rcx, [rsi+20h]; lpCriticalSection
0x180004ec5  call    cs:__imp_EnterCriticalSection
0x180004ecb  mov     ebx, r13d
0x180004ece  cmp     [rsi+18h], r13d
0x180004ed2  jle     short loc_180004EF4
0x180004ed4  movsxd  rax, ebx
0x180004ed7  mov     rcx, [rsi+8]
0x180004edb  lea     rdx, [rbp+57h+Destination]; lpString2
0x180004edf  mov     rcx, [rcx+rax*8]; lpString1
0x180004ee3  call    cs:__imp_lstrcmpiW
0x180004ee9  test    eax, eax
0x180004eeb  jz      short loc_180004F36
0x180004eed  inc     ebx
0x180004eef  cmp     ebx, [rsi+18h]
0x180004ef2  jl      short loc_180004ED4
0x180004ef4  mov     rbx, r13
0x180004ef7  lea     rcx, [rsi+20h]; lpCriticalSection
0x180004efb  call    cs:__imp_LeaveCriticalSection
0x180004f01  test    rbx, rbx
0x180004f04  jz      loc_180004FC1
0x180004f0a  mov     [rbp+57h+var_90], r13
0x180004f0e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004f12  inc     r8; int
0x180004f15  cmp     [rbx+r8*2], r13w
0x180004f1a  jnz     short loc_180004F12
0x180004f1c  mov     rdx, rbx; unsigned __int16 *
0x180004f1f  lea     rcx, [rbp+57h+var_A0]; this
0x180004f23  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004f28  nop
0x180004f29  test    eax, eax
0x180004f2b  jz      loc_180004FC8
0x180004f31  mov     rax, [r14]
0x180004f34  jmp     short loc_180004F65
0x180004f36  cmp     ebx, 0FFFFFFFFh
0x180004f39  jz      short loc_180004EF4
0x180004f3b  test    ebx, ebx
0x180004f3d  js      loc_180004FFB
0x180004f43  cmp     ebx, [rsi+18h]
0x180004f46  jge     loc_180004FFB
0x180004f4c  movsxd  rcx, ebx
0x180004f4f  mov     rax, [rsi+10h]
0x180004f53  mov     rbx, [rax+rcx*8]
0x180004f57  jmp     short loc_180004EF7
0x180004f59  mov     rcx, rax; lpsz
0x180004f5c  call    cs:__imp_CharNextW
0x180004f62  mov     [r14], rax
0x180004f65  cmp     rax, rdi
0x180004f68  jnz     short loc_180004F59
0x180004f6a  jmp     short loc_180004F82
0x180004f6c  mov     rdx, rbx; unsigned __int16 *
0x180004f6f  mov     r8d, 1; int
0x180004f75  lea     rcx, [rbp+57h+var_A0]; this
0x180004f79  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004f7e  test    eax, eax
0x180004f80  jz      short loc_180004FC8
0x180004f82  mov     rcx, [r14]; lpsz
0x180004f85  call    cs:__imp_CharNextW
0x180004f8b  mov     rbx, rax
0x180004f8e  mov     [r14], rax
0x180004f91  movzx   eax, word ptr [rax]
0x180004f94  test    ax, ax
0x180004f97  jnz     loc_180004E13
0x180004f9d  mov     rdx, [rbp+57h+pv]
0x180004fa1  mov     ebx, r13d
0x180004fa4  mov     [rbp+57h+pv], r13
0x180004fa8  mov     [r12], rdx
0x180004fac  mov     rcx, [rbp+57h+pv]; pv
0x180004fb0  call    cs:__imp_CoTaskMemFree
0x180004fb6  mov     eax, ebx
0x180004fb8  jmp     short loc_180004FD4
0x180004fba  mov     ebx, 80004005h
0x180004fbf  jmp     short loc_180004FAC
0x180004fc1  mov     ebx, 80020009h
0x180004fc6  jmp     short loc_180004FAC
0x180004fc8  mov     ebx, 8007000Eh
0x180004fcd  jmp     short loc_180004FAC
0x180004fcf  mov     eax, 80004003h
0x180004fd4  mov     rcx, [rbp+57h+var_40]
0x180004fd8  xor     rcx, rsp; StackCookie
0x180004fdb  call    __security_check_cookie
0x180004fe0  mov     rbx, [rsp+0C0h+arg_8]
0x180004fe8  add     rsp, 90h
0x180004fef  pop     r15
0x180004ff1  pop     r14
0x180004ff3  pop     r13
0x180004ff5  pop     r12
0x180004ff7  pop     rdi
0x180004ff8  pop     rsi
0x180004ff9  pop     rbp
0x180004ffa  retn
0x180004ffb  mov     ecx, 0C000008Ch; unsigned int
0x180005000  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180005005  int     3; Trap to Debugger
0x180005006  mov     ecx, 80004005h; int
0x18000500b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005011  mov     ecx, 80070057h; int
0x180005016  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000501c  mov     ecx, 8007000Eh; int
0x180005021  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
