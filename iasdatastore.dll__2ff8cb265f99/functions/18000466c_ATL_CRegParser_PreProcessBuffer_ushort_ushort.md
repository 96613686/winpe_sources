# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000466c`
- end: `0x180004947`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004b88`

## callees

- `0x180002f0c`
- `0x1800039a4`
- `0x18000466c`
- `0x18000619c`
- `0x18000dd10`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800047af`
- `msvcrt!wcsncpy_s` at `0x1800047af`
- `KERNEL32!EnterCriticalSection` at `0x1800047e5`
- `KERNEL32!EnterCriticalSection` at `0x1800047e5`
- `KERNEL32!LeaveCriticalSection` at `0x18000481b`
- `KERNEL32!LeaveCriticalSection` at `0x18000481b`
- `KERNEL32!lstrcmpiW` at `0x180004803`
- `KERNEL32!lstrcmpiW` at `0x180004803`
- `ole32!CoTaskMemFree` at `0x180004714`
- `ole32!CoTaskMemFree` at `0x1800048d0`
- `ole32!CoTaskMemFree` at `0x180004714`
- `ole32!CoTaskMemFree` at `0x1800048d0`
- `ole32!CoTaskMemAlloc` at `0x1800046f6`
- `ole32!CoTaskMemAlloc` at `0x1800046f6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004740`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004771`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000487c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800048a5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004740`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004771`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000487c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800048a5`

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
0x18000466c  mov     [rsp-8+arg_8], rbx
0x180004671  push    rbp
0x180004672  push    rsi
0x180004673  push    rdi
0x180004674  push    r12
0x180004676  push    r13
0x180004678  push    r14
0x18000467a  push    r15
0x18000467c  lea     rbp, [rsp-27h]
0x180004681  sub     rsp, 90h
0x180004688  mov     rax, cs:__security_cookie
0x18000468f  xor     rax, rsp
0x180004692  mov     [rbp+57h+var_40], rax
0x180004696  mov     r12, r8
0x180004699  mov     rbx, rdx
0x18000469c  mov     r14, rcx
0x18000469f  xor     r13d, r13d
0x1800046a2  test    rdx, rdx
0x1800046a5  jz      loc_1800048EF
0x1800046ab  test    r8, r8
0x1800046ae  jz      loc_1800048EF
0x1800046b4  mov     [r8], r13
0x1800046b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800046bb  inc     rax
0x1800046be  cmp     [rdx+rax*2], r13w
0x1800046c3  jnz     short loc_1800046BB
0x1800046c5  add     eax, eax
0x1800046c7  mov     ecx, 3E8h
0x1800046cc  cmp     eax, 64h ; 'd'
0x1800046cf  cmovl   eax, ecx
0x1800046d2  mov     [rbp+57h+var_A0], r13d
0x1800046d6  mov     [rbp+57h+var_9C], eax
0x1800046d9  mov     ecx, eax
0x1800046db  add     rcx, rcx
0x1800046de  mov     eax, 0FFFFFFFFh
0x1800046e3  cmp     rcx, rax
0x1800046e6  jbe     short loc_1800046F4
0x1800046e8  mov     rax, r13
0x1800046eb  mov     rdx, r13
0x1800046ee  mov     [rbp+57h+pv], rdx
0x1800046f2  jmp     short loc_18000470C
0x1800046f4  mov     ecx, ecx; cb
0x1800046f6  call    cs:__imp_CoTaskMemAlloc
0x1800046fc  mov     rdx, rax
0x1800046ff  mov     [rbp+57h+pv], rax
0x180004703  test    rax, rax
0x180004706  jz      short loc_18000470C
0x180004708  mov     [rax], r13w
0x18000470c  test    rax, rax
0x18000470f  jnz     short loc_180004724
0x180004711  mov     rcx, rax; pv
0x180004714  call    cs:__imp_CoTaskMemFree
0x18000471a  mov     eax, 8007000Eh
0x18000471f  jmp     loc_1800048F4
0x180004724  mov     [r14], rbx
0x180004727  movzx   eax, word ptr [rbx]
0x18000472a  test    ax, ax
0x18000472d  jz      loc_1800048C1
0x180004733  cmp     ax, 25h ; '%'
0x180004737  jnz     loc_18000488C
0x18000473d  mov     rcx, rbx; lpsz
0x180004740  call    cs:__imp_CharNextW
0x180004746  mov     [r14], rax
0x180004749  movzx   ecx, word ptr [rax]
0x18000474c  cmp     cx, 25h ; '%'
0x180004750  jnz     short loc_18000475A
0x180004752  mov     rdx, rax
0x180004755  jmp     loc_18000488F
0x18000475a  test    rax, rax
0x18000475d  jz      loc_1800048E1
0x180004763  mov     rdi, r13
0x180004766  jmp     short loc_18000477A
0x180004768  cmp     cx, 25h ; '%'
0x18000476c  jz      short loc_180004781
0x18000476e  mov     rcx, rax; lpsz
0x180004771  call    cs:__imp_CharNextW
0x180004777  movzx   ecx, word ptr [rax]
0x18000477a  test    cx, cx
0x18000477d  jnz     short loc_180004768
0x18000477f  jmp     short loc_180004784
0x180004781  mov     rdi, rax
0x180004784  test    rdi, rdi
0x180004787  jz      loc_1800048E1
0x18000478d  mov     rax, rdi
0x180004790  sub     rax, [r14]
0x180004793  sar     rax, 1
0x180004796  cmp     rax, 1Fh
0x18000479a  jg      loc_1800048DA
0x1800047a0  movsxd  r9, eax; MaxCount
0x1800047a3  mov     r8, [r14]; Source
0x1800047a6  mov     edx, 20h ; ' '; SizeInWords
0x1800047ab  lea     rcx, [rbp+57h+Destination]; Destination
0x1800047af  call    cs:__imp_wcsncpy_s
0x1800047b5  test    eax, eax
0x1800047b7  jz      short loc_1800047DD
0x1800047b9  cmp     eax, 0Ch
0x1800047bc  jz      loc_18000493C
0x1800047c2  cmp     eax, 16h
0x1800047c5  jz      loc_180004931
0x1800047cb  cmp     eax, 22h ; '"'
0x1800047ce  jz      loc_180004931
0x1800047d4  cmp     eax, 50h ; 'P'
0x1800047d7  jnz     loc_180004926
0x1800047dd  mov     rsi, [r14+8]
0x1800047e1  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800047e5  call    cs:__imp_EnterCriticalSection
0x1800047eb  mov     ebx, r13d
0x1800047ee  cmp     [rsi+18h], r13d
0x1800047f2  jle     short loc_180004814
0x1800047f4  movsxd  rax, ebx
0x1800047f7  mov     rcx, [rsi+8]
0x1800047fb  lea     rdx, [rbp+57h+Destination]; lpString2
0x1800047ff  mov     rcx, [rcx+rax*8]; lpString1
0x180004803  call    cs:__imp_lstrcmpiW
0x180004809  test    eax, eax
0x18000480b  jz      short loc_180004856
0x18000480d  inc     ebx
0x18000480f  cmp     ebx, [rsi+18h]
0x180004812  jl      short loc_1800047F4
0x180004814  mov     rbx, r13
0x180004817  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000481b  call    cs:__imp_LeaveCriticalSection
0x180004821  test    rbx, rbx
0x180004824  jz      loc_1800048E1
0x18000482a  mov     [rbp+57h+var_90], r13
0x18000482e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004832  inc     r8; int
0x180004835  cmp     [rbx+r8*2], r13w
0x18000483a  jnz     short loc_180004832
0x18000483c  mov     rdx, rbx; unsigned __int16 *
0x18000483f  lea     rcx, [rbp+57h+var_A0]; this
0x180004843  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004848  nop
0x180004849  test    eax, eax
0x18000484b  jz      loc_1800048E8
0x180004851  mov     rax, [r14]
0x180004854  jmp     short loc_180004885
0x180004856  cmp     ebx, 0FFFFFFFFh
0x180004859  jz      short loc_180004814
0x18000485b  test    ebx, ebx
0x18000485d  js      loc_18000491B
0x180004863  cmp     ebx, [rsi+18h]
0x180004866  jge     loc_18000491B
0x18000486c  movsxd  rcx, ebx
0x18000486f  mov     rax, [rsi+10h]
0x180004873  mov     rbx, [rax+rcx*8]
0x180004877  jmp     short loc_180004817
0x180004879  mov     rcx, rax; lpsz
0x18000487c  call    cs:__imp_CharNextW
0x180004882  mov     [r14], rax
0x180004885  cmp     rax, rdi
0x180004888  jnz     short loc_180004879
0x18000488a  jmp     short loc_1800048A2
0x18000488c  mov     rdx, rbx; unsigned __int16 *
0x18000488f  mov     r8d, 1; int
0x180004895  lea     rcx, [rbp+57h+var_A0]; this
0x180004899  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000489e  test    eax, eax
0x1800048a0  jz      short loc_1800048E8
0x1800048a2  mov     rcx, [r14]; lpsz
0x1800048a5  call    cs:__imp_CharNextW
0x1800048ab  mov     rbx, rax
0x1800048ae  mov     [r14], rax
0x1800048b1  movzx   eax, word ptr [rax]
0x1800048b4  test    ax, ax
0x1800048b7  jnz     loc_180004733
0x1800048bd  mov     rdx, [rbp+57h+pv]
0x1800048c1  mov     ebx, r13d
0x1800048c4  mov     [rbp+57h+pv], r13
0x1800048c8  mov     [r12], rdx
0x1800048cc  mov     rcx, [rbp+57h+pv]; pv
0x1800048d0  call    cs:__imp_CoTaskMemFree
0x1800048d6  mov     eax, ebx
0x1800048d8  jmp     short loc_1800048F4
0x1800048da  mov     ebx, 80004005h
0x1800048df  jmp     short loc_1800048CC
0x1800048e1  mov     ebx, 80020009h
0x1800048e6  jmp     short loc_1800048CC
0x1800048e8  mov     ebx, 8007000Eh
0x1800048ed  jmp     short loc_1800048CC
0x1800048ef  mov     eax, 80004003h
0x1800048f4  mov     rcx, [rbp+57h+var_40]
0x1800048f8  xor     rcx, rsp; StackCookie
0x1800048fb  call    __security_check_cookie
0x180004900  mov     rbx, [rsp+0C0h+arg_8]
0x180004908  add     rsp, 90h
0x18000490f  pop     r15
0x180004911  pop     r14
0x180004913  pop     r13
0x180004915  pop     r12
0x180004917  pop     rdi
0x180004918  pop     rsi
0x180004919  pop     rbp
0x18000491a  retn
0x18000491b  mov     ecx, 0C000008Ch; unsigned int
0x180004920  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004925  int     3; Trap to Debugger
0x180004926  mov     ecx, 80004005h; int
0x18000492b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004931  mov     ecx, 80070057h; int
0x180004936  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000493c  mov     ecx, 8007000Eh; int
0x180004941  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
