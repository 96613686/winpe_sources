# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800086fc`
- end: `0x180008a1a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `798`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008d5c`

## callees

- `0x1800067a0`
- `0x1800068ec`
- `0x1800086fc`
- `0x180009fb0`
- `0x1800136b0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008857`
- `msvcrt!wcsncpy_s` at `0x180008857`
- `KERNEL32!EnterCriticalSection` at `0x180008893`
- `KERNEL32!EnterCriticalSection` at `0x180008893`
- `KERNEL32!LeaveCriticalSection` at `0x1800088d5`
- `KERNEL32!LeaveCriticalSection` at `0x1800088d5`
- `KERNEL32!lstrcmpiW` at `0x1800088b7`
- `KERNEL32!lstrcmpiW` at `0x1800088b7`
- `USER32!CharNextW` at `0x1800087dc`
- `USER32!CharNextW` at `0x180008813`
- `USER32!CharNextW` at `0x18000893c`
- `USER32!CharNextW` at `0x18000896b`
- `USER32!CharNextW` at `0x1800087dc`
- `USER32!CharNextW` at `0x180008813`
- `USER32!CharNextW` at `0x18000893c`
- `USER32!CharNextW` at `0x18000896b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000899c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000899c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008786`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008786`

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
  errno_t v18; // eax
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
0x1800086fc  mov     [rsp-8+arg_8], rbx
0x180008701  push    rbp
0x180008702  push    rsi
0x180008703  push    rdi
0x180008704  push    r12
0x180008706  push    r13
0x180008708  push    r14
0x18000870a  push    r15
0x18000870c  lea     rbp, [rsp-27h]
0x180008711  sub     rsp, 90h
0x180008718  mov     rax, cs:__security_cookie
0x18000871f  xor     rax, rsp
0x180008722  mov     [rbp+57h+var_40], rax
0x180008726  mov     r12, r8
0x180008729  mov     rbx, rdx
0x18000872c  mov     r14, rcx
0x18000872f  xor     r13d, r13d
0x180008732  test    rdx, rdx
0x180008735  jz      loc_1800089C1
0x18000873b  test    r8, r8
0x18000873e  jz      loc_1800089C1
0x180008744  mov     [r8], r13
0x180008747  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000874b  inc     rax
0x18000874e  cmp     [rdx+rax*2], r13w
0x180008753  jnz     short loc_18000874B
0x180008755  add     eax, eax
0x180008757  mov     ecx, 3E8h
0x18000875c  cmp     eax, 64h ; 'd'
0x18000875f  cmovl   eax, ecx
0x180008762  mov     [rbp+57h+var_A0], r13d
0x180008766  mov     [rbp+57h+var_9C], eax
0x180008769  mov     ecx, eax
0x18000876b  add     rcx, rcx
0x18000876e  mov     eax, 0FFFFFFFFh
0x180008773  cmp     rcx, rax
0x180008776  jbe     short loc_180008784
0x180008778  mov     rax, r13
0x18000877b  mov     rdx, r13
0x18000877e  mov     [rbp+57h+pv], rdx
0x180008782  jmp     short loc_1800087A2
0x180008784  mov     ecx, ecx; cb
0x180008786  call    cs:__imp_CoTaskMemAlloc
0x18000878d  nop     dword ptr [rax+rax+00h]
0x180008792  mov     rdx, rax
0x180008795  mov     [rbp+57h+pv], rax
0x180008799  test    rax, rax
0x18000879c  jz      short loc_1800087A2
0x18000879e  mov     [rax], r13w
0x1800087a2  test    rax, rax
0x1800087a5  jnz     short loc_1800087C0
0x1800087a7  mov     rcx, rax; pv
0x1800087aa  call    cs:__imp_CoTaskMemFree
0x1800087b1  nop     dword ptr [rax+rax+00h]
0x1800087b6  mov     eax, 8007000Eh
0x1800087bb  jmp     loc_1800089C6
0x1800087c0  mov     [r14], rbx
0x1800087c3  movzx   eax, word ptr [rbx]
0x1800087c6  test    ax, ax
0x1800087c9  jz      loc_18000898D
0x1800087cf  cmp     ax, 25h ; '%'
0x1800087d3  jnz     loc_180008952
0x1800087d9  mov     rcx, rbx; lpsz
0x1800087dc  call    cs:__imp_CharNextW
0x1800087e3  nop     dword ptr [rax+rax+00h]
0x1800087e8  mov     [r14], rax
0x1800087eb  movzx   ecx, word ptr [rax]
0x1800087ee  cmp     cx, 25h ; '%'
0x1800087f2  jnz     short loc_1800087FC
0x1800087f4  mov     rdx, rax
0x1800087f7  jmp     loc_180008955
0x1800087fc  test    rax, rax
0x1800087ff  jz      loc_1800089B3
0x180008805  mov     rdi, r13
0x180008808  jmp     short loc_180008822
0x18000880a  cmp     cx, 25h ; '%'
0x18000880e  jz      short loc_180008829
0x180008810  mov     rcx, rax; lpsz
0x180008813  call    cs:__imp_CharNextW
0x18000881a  nop     dword ptr [rax+rax+00h]
0x18000881f  movzx   ecx, word ptr [rax]
0x180008822  test    cx, cx
0x180008825  jnz     short loc_18000880A
0x180008827  jmp     short loc_18000882C
0x180008829  mov     rdi, rax
0x18000882c  test    rdi, rdi
0x18000882f  jz      loc_1800089B3
0x180008835  mov     rax, rdi
0x180008838  sub     rax, [r14]
0x18000883b  sar     rax, 1
0x18000883e  cmp     rax, 1Fh
0x180008842  jg      loc_1800089AC
0x180008848  movsxd  r9, eax; MaxCount
0x18000884b  mov     r8, [r14]; Source
0x18000884e  mov     edx, 20h ; ' '; SizeInWords
0x180008853  lea     rcx, [rbp+57h+Destination]; Destination
0x180008857  call    cs:__imp_wcsncpy_s
0x18000885e  nop     dword ptr [rax+rax+00h]
0x180008863  test    eax, eax
0x180008865  jz      short loc_18000888B
0x180008867  cmp     eax, 0Ch
0x18000886a  jz      loc_180008A0F
0x180008870  cmp     eax, 16h
0x180008873  jz      loc_180008A04
0x180008879  cmp     eax, 22h ; '"'
0x18000887c  jz      loc_180008A04
0x180008882  cmp     eax, 50h ; 'P'
0x180008885  jnz     loc_1800089F9
0x18000888b  mov     rsi, [r14+8]
0x18000888f  lea     rcx, [rsi+20h]; lpCriticalSection
0x180008893  call    cs:__imp_EnterCriticalSection
0x18000889a  nop     dword ptr [rax+rax+00h]
0x18000889f  mov     ebx, r13d
0x1800088a2  cmp     [rsi+18h], r13d
0x1800088a6  jle     short loc_1800088CE
0x1800088a8  movsxd  rax, ebx
0x1800088ab  mov     rcx, [rsi+8]
0x1800088af  lea     rdx, [rbp+57h+Destination]; lpString2
0x1800088b3  mov     rcx, [rcx+rax*8]; lpString1
0x1800088b7  call    cs:__imp_lstrcmpiW
0x1800088be  nop     dword ptr [rax+rax+00h]
0x1800088c3  test    eax, eax
0x1800088c5  jz      short loc_180008916
0x1800088c7  inc     ebx
0x1800088c9  cmp     ebx, [rsi+18h]
0x1800088cc  jl      short loc_1800088A8
0x1800088ce  mov     rbx, r13
0x1800088d1  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800088d5  call    cs:__imp_LeaveCriticalSection
0x1800088dc  nop     dword ptr [rax+rax+00h]
0x1800088e1  test    rbx, rbx
0x1800088e4  jz      loc_1800089B3
0x1800088ea  mov     [rbp+57h+var_90], r13
0x1800088ee  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800088f2  inc     r8; int
0x1800088f5  cmp     [rbx+r8*2], r13w
0x1800088fa  jnz     short loc_1800088F2
0x1800088fc  mov     rdx, rbx; unsigned __int16 *
0x1800088ff  lea     rcx, [rbp+57h+var_A0]; this
0x180008903  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008908  nop
0x180008909  test    eax, eax
0x18000890b  jz      loc_1800089BA
0x180008911  mov     rax, [r14]
0x180008914  jmp     short loc_18000894B
0x180008916  cmp     ebx, 0FFFFFFFFh
0x180008919  jz      short loc_1800088CE
0x18000891b  test    ebx, ebx
0x18000891d  js      loc_1800089EE
0x180008923  cmp     ebx, [rsi+18h]
0x180008926  jge     loc_1800089EE
0x18000892c  movsxd  rcx, ebx
0x18000892f  mov     rax, [rsi+10h]
0x180008933  mov     rbx, [rax+rcx*8]
0x180008937  jmp     short loc_1800088D1
0x180008939  mov     rcx, rax; lpsz
0x18000893c  call    cs:__imp_CharNextW
0x180008943  nop     dword ptr [rax+rax+00h]
0x180008948  mov     [r14], rax
0x18000894b  cmp     rax, rdi
0x18000894e  jnz     short loc_180008939
0x180008950  jmp     short loc_180008968
0x180008952  mov     rdx, rbx; unsigned __int16 *
0x180008955  mov     r8d, 1; int
0x18000895b  lea     rcx, [rbp+57h+var_A0]; this
0x18000895f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180008964  test    eax, eax
0x180008966  jz      short loc_1800089BA
0x180008968  mov     rcx, [r14]; lpsz
0x18000896b  call    cs:__imp_CharNextW
0x180008972  nop     dword ptr [rax+rax+00h]
0x180008977  mov     rbx, rax
0x18000897a  mov     [r14], rax
0x18000897d  movzx   eax, word ptr [rax]
0x180008980  test    ax, ax
0x180008983  jnz     loc_1800087CF
0x180008989  mov     rdx, [rbp+57h+pv]
0x18000898d  mov     ebx, r13d
0x180008990  mov     [rbp+57h+pv], r13
0x180008994  mov     [r12], rdx
0x180008998  mov     rcx, [rbp+57h+pv]; pv
0x18000899c  call    cs:__imp_CoTaskMemFree
0x1800089a3  nop     dword ptr [rax+rax+00h]
0x1800089a8  mov     eax, ebx
0x1800089aa  jmp     short loc_1800089C6
0x1800089ac  mov     ebx, 80004005h
0x1800089b1  jmp     short loc_180008998
0x1800089b3  mov     ebx, 80020009h
0x1800089b8  jmp     short loc_180008998
0x1800089ba  mov     ebx, 8007000Eh
0x1800089bf  jmp     short loc_180008998
0x1800089c1  mov     eax, 80004003h
0x1800089c6  mov     rcx, [rbp+57h+var_40]
0x1800089ca  xor     rcx, rsp; StackCookie
0x1800089cd  call    __security_check_cookie
0x1800089d2  mov     rbx, [rsp+0C0h+arg_8]
0x1800089da  add     rsp, 90h
0x1800089e1  pop     r15
0x1800089e3  pop     r14
0x1800089e5  pop     r13
0x1800089e7  pop     r12
0x1800089e9  pop     rdi
0x1800089ea  pop     rsi
0x1800089eb  pop     rbp
0x1800089ec  retn
0x1800089ee  mov     ecx, 0C000008Ch; unsigned int
0x1800089f3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800089f8  int     3; Trap to Debugger
0x1800089f9  mov     ecx, 80004005h; int
0x1800089fe  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008a04  mov     ecx, 80070057h; int
0x180008a09  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008a0f  mov     ecx, 8007000Eh; int
0x180008a14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
