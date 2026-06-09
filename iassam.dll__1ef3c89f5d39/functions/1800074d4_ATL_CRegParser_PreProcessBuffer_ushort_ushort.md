# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800074d4`
- end: `0x1800076f7`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `547`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800079dc`

## callees

- `0x180002b00`
- `0x1800041ec`
- `0x180004430`
- `0x1800074d4`
- `0x180008800`
- `0x180008858`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180007600`
- `msvcrt!wcsncpy_s` at `0x180007600`
- `USER32!CharNextW` at `0x1800075b0`
- `USER32!CharNextW` at `0x180007658`
- `USER32!CharNextW` at `0x180007681`
- `USER32!CharNextW` at `0x1800075b0`
- `USER32!CharNextW` at `0x180007658`
- `USER32!CharNextW` at `0x180007681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000757e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000757e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076ab`

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
  const unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rsi
  __int64 v17; // rcx
  errno_t v18; // eax
  const unsigned __int16 *v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v26; // [rsp+30h] [rbp-29h] BYREF
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
  v24[0] = 0;
  v24[1] = v7;
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
LABEL_31:
    v23 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_32;
  }
  while ( v12 != 37 )
  {
    v14 = v4;
LABEL_28:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v14, 1) )
      goto LABEL_35;
LABEL_29:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_31;
    }
  }
  v13 = CharNextW(v4);
  *(_QWORD *)this = v13;
  if ( *v13 == 37 )
  {
    v14 = v13;
    goto LABEL_28;
  }
  v15 = ATL::CRegParser::StrChrW(v13, 0x25u);
  v16 = v15;
  if ( !v15 )
    goto LABEL_34;
  v17 = ((__int64)v15 - *(_QWORD *)this) >> 1;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_32;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *(const wchar_t **)this, (int)v17);
  ATL::AtlCrtErrorCheck(v18);
  v19 = ATL::CRegObject::StrFromMap(*((ATL::CRegObject **)this + 1), Destination);
  if ( !v19 )
  {
LABEL_34:
    v23 = -2147352567;
    goto LABEL_32;
  }
  v26 = 0;
  v20 = -1;
  do
    ++v20;
  while ( v19[v20] );
  v21 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v19, v20);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v26);
  if ( v21 )
  {
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
    goto LABEL_29;
  }
LABEL_35:
  v23 = -2147024882;
LABEL_32:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x1800074d4  mov     [rsp-8+arg_8], rbx
0x1800074d9  mov     [rsp-8+arg_18], rsi
0x1800074de  push    rbp
0x1800074df  push    rdi
0x1800074e0  push    r12
0x1800074e2  push    r14
0x1800074e4  push    r15
0x1800074e6  lea     rbp, [rsp-37h]
0x1800074eb  sub     rsp, 90h
0x1800074f2  mov     rax, cs:__security_cookie
0x1800074f9  xor     rax, rsp
0x1800074fc  mov     [rbp+57h+var_30], rax
0x180007500  mov     r14, r8
0x180007503  mov     rbx, rdx
0x180007506  mov     rdi, rcx
0x180007509  xor     r15d, r15d
0x18000750c  test    rdx, rdx
0x18000750f  jz      loc_1800076CA
0x180007515  test    r8, r8
0x180007518  jz      loc_1800076CA
0x18000751e  mov     [r8], r15
0x180007521  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007525  inc     rax
0x180007528  cmp     [rdx+rax*2], r15w
0x18000752d  jnz     short loc_180007525
0x18000752f  add     eax, eax
0x180007531  mov     ecx, 3E8h
0x180007536  cmp     eax, 64h ; 'd'
0x180007539  cmovl   eax, ecx
0x18000753c  mov     [rbp+57h+var_90], r15d
0x180007540  mov     [rbp+57h+var_8C], eax
0x180007543  mov     ecx, eax
0x180007545  add     rcx, rcx
0x180007548  mov     eax, 0FFFFFFFFh
0x18000754d  cmp     rcx, rax
0x180007550  jbe     short loc_18000755E
0x180007552  mov     rax, r15
0x180007555  mov     rdx, r15
0x180007558  mov     [rbp+57h+pv], rdx
0x18000755c  jmp     short loc_180007576
0x18000755e  mov     ecx, ecx; cb
0x180007560  call    cs:__imp_CoTaskMemAlloc
0x180007566  mov     rdx, rax
0x180007569  mov     [rbp+57h+pv], rax
0x18000756d  test    rax, rax
0x180007570  jz      short loc_180007576
0x180007572  mov     [rax], r15w
0x180007576  test    rax, rax
0x180007579  jnz     short loc_18000758E
0x18000757b  mov     rcx, rax; pv
0x18000757e  call    cs:__imp_CoTaskMemFree
0x180007584  mov     eax, 8007000Eh
0x180007589  jmp     loc_1800076CF
0x18000758e  mov     [rdi], rbx
0x180007591  movzx   eax, word ptr [rbx]
0x180007594  test    ax, ax
0x180007597  jz      loc_18000769D
0x18000759d  mov     r12d, 25h ; '%'
0x1800075a3  cmp     ax, r12w
0x1800075a7  jnz     loc_180007668
0x1800075ad  mov     rcx, rbx; lpsz
0x1800075b0  call    cs:__imp_CharNextW
0x1800075b6  mov     [rdi], rax
0x1800075b9  cmp     [rax], r12w
0x1800075bd  jnz     short loc_1800075C7
0x1800075bf  mov     rdx, rax
0x1800075c2  jmp     loc_18000766B
0x1800075c7  mov     edx, r12d; unsigned __int16
0x1800075ca  mov     rcx, rax; lpsz
0x1800075cd  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800075d2  mov     rsi, rax
0x1800075d5  test    rax, rax
0x1800075d8  jz      loc_1800076BC
0x1800075de  mov     rcx, rax
0x1800075e1  sub     rcx, [rdi]
0x1800075e4  sar     rcx, 1
0x1800075e7  cmp     rcx, 1Fh
0x1800075eb  jg      loc_1800076B5
0x1800075f1  movsxd  r9, ecx; MaxCount
0x1800075f4  mov     r8, [rdi]; Source
0x1800075f7  mov     edx, 20h ; ' '; SizeInWords
0x1800075fc  lea     rcx, [rbp+57h+Destination]; Destination
0x180007600  call    cs:__imp_wcsncpy_s
0x180007606  mov     ecx, eax; int
0x180007608  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000760d  lea     rdx, [rbp+57h+Destination]; unsigned __int16 *
0x180007611  mov     rcx, [rdi+8]; this
0x180007615  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x18000761a  test    rax, rax
0x18000761d  jz      loc_1800076BC
0x180007623  mov     [rbp+57h+var_80], r15
0x180007627  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000762b  inc     r8; int
0x18000762e  cmp     [rax+r8*2], r15w
0x180007633  jnz     short loc_18000762B
0x180007635  mov     rdx, rax; unsigned __int16 *
0x180007638  lea     rcx, [rbp+57h+var_90]; this
0x18000763c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007641  mov     ebx, eax
0x180007643  lea     rcx, [rbp+57h+var_80]
0x180007647  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000764c  test    ebx, ebx
0x18000764e  jz      short loc_1800076C3
0x180007650  mov     rax, [rdi]
0x180007653  jmp     short loc_180007661
0x180007655  mov     rcx, rax; lpsz
0x180007658  call    cs:__imp_CharNextW
0x18000765e  mov     [rdi], rax
0x180007661  cmp     rax, rsi
0x180007664  jnz     short loc_180007655
0x180007666  jmp     short loc_18000767E
0x180007668  mov     rdx, rbx; unsigned __int16 *
0x18000766b  mov     r8d, 1; int
0x180007671  lea     rcx, [rbp+57h+var_90]; this
0x180007675  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000767a  test    eax, eax
0x18000767c  jz      short loc_1800076C3
0x18000767e  mov     rcx, [rdi]; lpsz
0x180007681  call    cs:__imp_CharNextW
0x180007687  mov     rbx, rax
0x18000768a  mov     [rdi], rax
0x18000768d  movzx   eax, word ptr [rax]
0x180007690  test    ax, ax
0x180007693  jnz     loc_1800075A3
0x180007699  mov     rdx, [rbp+57h+pv]
0x18000769d  mov     ebx, r15d
0x1800076a0  mov     [rbp+57h+pv], r15
0x1800076a4  mov     [r14], rdx
0x1800076a7  mov     rcx, [rbp+57h+pv]; pv
0x1800076ab  call    cs:__imp_CoTaskMemFree
0x1800076b1  mov     eax, ebx
0x1800076b3  jmp     short loc_1800076CF
0x1800076b5  mov     ebx, 80004005h
0x1800076ba  jmp     short loc_1800076A7
0x1800076bc  mov     ebx, 80020009h
0x1800076c1  jmp     short loc_1800076A7
0x1800076c3  mov     ebx, 8007000Eh
0x1800076c8  jmp     short loc_1800076A7
0x1800076ca  mov     eax, 80004003h
0x1800076cf  mov     rcx, [rbp+57h+var_30]
0x1800076d3  xor     rcx, rsp; StackCookie
0x1800076d6  call    __security_check_cookie
0x1800076db  lea     r11, [rsp+0B0h+var_20]
0x1800076e3  mov     rbx, [r11+38h]
0x1800076e7  mov     rsi, [r11+48h]
0x1800076eb  mov     rsp, r11
0x1800076ee  pop     r15
0x1800076f0  pop     r14
0x1800076f2  pop     r12
0x1800076f4  pop     rdi
0x1800076f5  pop     rbp
0x1800076f6  retn
```
