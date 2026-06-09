# CStringTokens::Parse(_bstr_t const &,wchar_t)

- ea: `0x1800158cc`
- end: `0x180015a75`
- name: `?Parse@CStringTokens@@QEAAXAEBV_bstr_t@@_W@Z`
- size: `425`
- prototype: `void __fastcall(CStringTokens *this, const wchar_t **, wchar_t)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180005df4`
- `0x180008380`

## callees

- `0x180001ce6`
- `0x1800041ec`
- `0x180004d20`
- `0x1800158cc`
- `0x180015af8`
- `0x180015c74`
- `0x180015db0`
- `0x18001e380`

## import_xrefs

- `msvcrt!wcschr` at `0x180015942`
- `msvcrt!wcschr` at `0x180015998`
- `msvcrt!wcschr` at `0x1800159b3`
- `msvcrt!wcschr` at `0x1800159cd`
- `msvcrt!wcschr` at `0x180015942`
- `msvcrt!wcschr` at `0x180015998`
- `msvcrt!wcschr` at `0x1800159b3`
- `msvcrt!wcschr` at `0x1800159cd`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800159e3`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800159e3`

## pseudocode

```c
void __fastcall CStringTokens::Parse(CStringTokens *this, const wchar_t **a2, wchar_t a3)
{
  char *v5; // r14
  const wchar_t *v6; // rbx
  wchar_t *v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  char v10; // si
  wchar_t *v11; // rax
  __int64 v12; // rax
  _BYTE v13[8]; // [rsp+20h] [rbp-50h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-48h] BYREF
  _BYTE v15[8]; // [rsp+40h] [rbp-30h] BYREF
  __int16 v16; // [rsp+48h] [rbp-28h]
  __int64 v17; // [rsp+58h] [rbp-18h]
  __int64 v18; // [rsp+60h] [rbp-10h]

  v5 = (char *)this + 8;
  std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::erase(
    (char *)this + 8,
    v13,
    **((_QWORD **)this + 2),
    *((_QWORD *)this + 2));
  v6 = *a2;
  if ( v6 )
    v6 = *(const wchar_t **)v6;
  while ( v6 )
  {
    v18 = 7;
    v17 = 0;
    v16 = 0;
LABEL_5:
    v7 = (wchar_t *)v6;
    while ( 1 )
    {
      v8 = wcschr(v7, a3);
      v9 = v8;
      if ( !v8 )
        break;
      if ( v7 != v8 && *(v8 - 1) == 92 )
      {
        std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(
          v15,
          v6,
          (unsigned int)(v8 - v6) - 1);
        std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(v15, v9, 1);
        v6 = v9 + 1;
        goto LABEL_5;
      }
      v10 = 0;
      v11 = wcschr(v6, 0x22u);
      if ( !v11 )
        goto LABEL_16;
      do
      {
        if ( v11 >= v9 )
          break;
        ++v10;
        v11 = wcschr(v11 + 1, 0x22u);
      }
      while ( v11 );
      if ( (v10 & 1) == 0 )
      {
LABEL_16:
        v12 = v9 - v6;
        goto LABEL_18;
      }
      v7 = wcschr(v9 + 1, 0x22u);
      if ( !v7 )
      {
        exception::exception((exception *)pExceptionObject);
        throw (exception *)pExceptionObject;
      }
    }
    LODWORD(v12) = mqwcslen(v6);
LABEL_18:
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(
      v15,
      v6,
      (unsigned int)v12);
    if ( v17 )
      std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::_Insert(
        v5,
        *((_QWORD *)v5 + 1),
        v15);
    v6 = (const wchar_t *)((unsigned __int64)(v9 + 1) & -(__int64)(v9 != 0));
    std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(
      (__int64)v15,
      1,
      0);
  }
}

```

## disassembly

```asm
0x1800158cc  mov     [rsp-28h+arg_18], rbx
0x1800158d1  push    rbp
0x1800158d2  push    rsi
0x1800158d3  push    rdi
0x1800158d4  push    r14
0x1800158d6  push    r15
0x1800158d8  mov     rbp, rsp
0x1800158db  sub     rsp, 70h
0x1800158df  mov     rax, cs:__security_cookie
0x1800158e6  xor     rax, rsp
0x1800158e9  mov     [rbp+var_8], rax
0x1800158ed  movzx   r15d, r8w
0x1800158f1  mov     rbx, rdx
0x1800158f4  mov     r8, [rcx+10h]
0x1800158f8  lea     r14, [rcx+8]
0x1800158fc  mov     r9, r8
0x1800158ff  mov     r8, [r8]
0x180015902  lea     rdx, [rbp+var_50]
0x180015906  mov     rcx, r14
0x180015909  call    ?erase@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@@std@@QEAA?AViterator@12@V312@0@Z; std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::erase(std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::iterator,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::iterator)
0x18001590e  mov     rbx, [rbx]
0x180015911  test    rbx, rbx
0x180015914  jz      short loc_180015919
0x180015916  mov     rbx, [rbx]
0x180015919  test    rbx, rbx
0x18001591c  jz      loc_180015A55
0x180015922  mov     [rbp+var_10], 7
0x18001592a  mov     [rbp+var_18], 0
0x180015932  xor     eax, eax
0x180015934  mov     [rbp+var_28], ax
0x180015938  mov     rsi, rbx
0x18001593b  movzx   edx, r15w; Ch
0x18001593f  mov     rcx, rsi; Str
0x180015942  call    cs:__imp_wcschr
0x180015948  mov     rdi, rax
0x18001594b  test    rax, rax
0x18001594e  jz      loc_180015A05
0x180015954  cmp     rsi, rax
0x180015957  jz      short loc_180015990
0x180015959  cmp     word ptr [rax-2], 5Ch ; '\'
0x18001595e  jnz     short loc_180015990
0x180015960  mov     r8, rax
0x180015963  sub     r8, rbx
0x180015966  sar     r8, 1
0x180015969  dec     r8d
0x18001596c  mov     rdx, rbx
0x18001596f  lea     rcx, [rbp+var_30]
0x180015973  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(wchar_t const *,unsigned __int64)
0x180015978  mov     r8d, 1
0x18001597e  mov     rdx, rdi
0x180015981  lea     rcx, [rbp+var_30]
0x180015985  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(wchar_t const *,unsigned __int64)
0x18001598a  lea     rbx, [rdi+2]
0x18001598e  jmp     short loc_180015938
0x180015990  xor     esi, esi
0x180015992  lea     edx, [rsi+22h]; Ch
0x180015995  mov     rcx, rbx; Str
0x180015998  call    cs:__imp_wcschr
0x18001599e  test    rax, rax
0x1800159a1  jz      short loc_1800159FA
0x1800159a3  cmp     rax, rdi
0x1800159a6  jnb     short loc_1800159BE
0x1800159a8  inc     esi
0x1800159aa  mov     edx, 22h ; '"'; Ch
0x1800159af  lea     rcx, [rax+2]; Str
0x1800159b3  call    cs:__imp_wcschr
0x1800159b9  test    rax, rax
0x1800159bc  jnz     short loc_1800159A3
0x1800159be  test    sil, 1
0x1800159c2  jz      short loc_1800159FA
0x1800159c4  mov     edx, 22h ; '"'; Ch
0x1800159c9  lea     rcx, [rdi+2]; Str
0x1800159cd  call    cs:__imp_wcschr
0x1800159d3  mov     rsi, rax
0x1800159d6  test    rax, rax
0x1800159d9  jnz     loc_18001593B
0x1800159df  lea     rcx, [rbp+pExceptionObject]
0x1800159e3  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800159e9  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800159f0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800159f4  call    _CxxThrowException_0
0x1800159fa  mov     rax, rdi
0x1800159fd  sub     rax, rbx
0x180015a00  sar     rax, 1
0x180015a03  jmp     short loc_180015A0D
0x180015a05  mov     rcx, rbx; wchar_t *
0x180015a08  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180015a0d  mov     r8d, eax
0x180015a10  mov     rdx, rbx
0x180015a13  lea     rcx, [rbp+var_30]
0x180015a17  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::append(wchar_t const *,unsigned __int64)
0x180015a1c  cmp     [rbp+var_18], 0
0x180015a21  jbe     short loc_180015A34
0x180015a23  lea     r8, [rbp+var_30]
0x180015a27  mov     rdx, [r14+8]
0x180015a2b  mov     rcx, r14
0x180015a2e  call    ?_Insert@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@@std@@QEAAXViterator@12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@2@@Z; std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::_Insert(std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::iterator,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70> const &)
0x180015a33  nop
0x180015a34  lea     rax, [rdi+2]
0x180015a38  neg     rdi
0x180015a3b  sbb     rbx, rbx
0x180015a3e  and     rbx, rax
0x180015a41  xor     r8d, r8d
0x180015a44  mov     dl, 1
0x180015a46  lea     rcx, [rbp+var_30]
0x180015a4a  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::_Tidy(bool,unsigned __int64)
0x180015a4f  nop
0x180015a50  jmp     loc_180015919
0x180015a55  mov     rcx, [rbp+var_8]
0x180015a59  xor     rcx, rsp; StackCookie
0x180015a5c  call    __security_check_cookie
0x180015a61  mov     rbx, [rsp+70h+arg_18]
0x180015a69  add     rsp, 70h
0x180015a6d  pop     r15
0x180015a6f  pop     r14
0x180015a71  pop     rdi
0x180015a72  pop     rsi
0x180015a73  pop     rbp
0x180015a74  retn
```
