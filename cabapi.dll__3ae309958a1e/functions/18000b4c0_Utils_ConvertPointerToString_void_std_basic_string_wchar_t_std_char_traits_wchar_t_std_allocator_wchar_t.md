# Utils::ConvertPointerToString(void *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> *)

- ea: `0x18000b4c0`
- end: `0x18000b5a6`
- name: `?ConvertPointerToString@Utils@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x1800085ac`
- `0x1800088dc`
- `0x180008fd8`
- `0x18000a09c`
- `0x18000a400`

## callees

- `0x180001540`
- `0x180002e54`
- `0x18000553c`
- `0x18000607c`
- `0x18000b24c`
- `0x18000b4c0`
- `0x18000c728`

## pseudocode

```c
__int64 __fastcall Utils::ConvertPointerToString(__int64 a1, __int64 a2)
{
  _WORD *v4; // rcx
  int v5; // eax
  unsigned int v6; // edi
  unsigned __int64 v7; // r8
  int v9; // [rsp+20h] [rbp-38h]
  wchar_t *v10[2]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v10 = 0;
  v11 = 0;
  std::vector<wchar_t>::resize(v10, 19);
  *(_QWORD *)(a2 + 16) = 0;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v4 = (_WORD *)a2;
  else
    v4 = *(_WORD **)a2;
  *v4 = 0;
  v5 = StringCchPrintfW(v10[0], (signed __int64)(v11 - (unsigned __int64)v10[0]) >> 1, L"0x%p", a1, -2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v10[0][v7] );
    std::wstring::_Assign<wchar_t>((void **)a2, v10[0], v7);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecore\\base\\cbs\\mobile\\cabapi\\privlib\\utils.cpp",
      (const char *)(unsigned int)v5,
      v9);
  }
  std::vector<wchar_t>::~vector<wchar_t>((char **)v10);
  return v6;
}

```

## disassembly

```asm
0x18000b4c0  mov     r11, rsp
0x18000b4c3  push    rdi
0x18000b4c4  sub     rsp, 50h
0x18000b4c8  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x18000b4d0  mov     [r11+18h], rbx
0x18000b4d4  mov     [r11+20h], rsi
0x18000b4d8  mov     rax, cs:__security_cookie
0x18000b4df  xor     rax, rsp
0x18000b4e2  mov     [rsp+58h+var_18], rax
0x18000b4e7  mov     rbx, rdx
0x18000b4ea  mov     rdi, rcx
0x18000b4ed  xorps   xmm0, xmm0
0x18000b4f0  movdqu  xmmword ptr [rsp+58h+var_30], xmm0
0x18000b4f6  xor     esi, esi
0x18000b4f8  mov     [r11-20h], rsi
0x18000b4fc  lea     edx, [rsi+13h]
0x18000b4ff  lea     rcx, [r11-30h]
0x18000b503  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_K@Z; std::vector<wchar_t>::resize(unsigned __int64)
0x18000b508  mov     [rbx+10h], rsi
0x18000b50c  cmp     qword ptr [rbx+18h], 7
0x18000b511  jbe     short loc_18000B518
0x18000b513  mov     rcx, [rbx]
0x18000b516  jmp     short loc_18000B51B
0x18000b518  mov     rcx, rbx
0x18000b51b  mov     [rcx], si
0x18000b51e  mov     rcx, [rsp+58h+var_30]; wchar_t *
0x18000b523  mov     rdx, [rsp+58h+var_20]
0x18000b528  sub     rdx, rcx
0x18000b52b  sar     rdx, 1; unsigned __int64
0x18000b52e  mov     r9, rdi
0x18000b531  lea     r8, a0xP; "0x%p"
0x18000b538  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000b53d  mov     edi, eax
0x18000b53f  test    eax, eax
0x18000b541  jns     short loc_18000B55F
0x18000b543  mov     rcx, [rsp+58h]; this
0x18000b548  mov     r9d, eax; char *
0x18000b54b  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\mobile\\cabapi\\pri"...
0x18000b552  mov     edx, 7Eh ; '~'; void *
0x18000b557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b55c  nop
0x18000b55d  jmp     short loc_18000B57D
0x18000b55f  mov     rdx, [rsp+58h+var_30]
0x18000b564  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b568  inc     r8
0x18000b56b  cmp     [rdx+r8*2], si
0x18000b570  jnz     short loc_18000B568
0x18000b572  mov     rcx, rbx
0x18000b575  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000b57a  nop
0x18000b57b  mov     edi, esi
0x18000b57d  lea     rcx, [rsp+58h+var_30]
0x18000b582  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18000b587  mov     eax, edi
0x18000b589  mov     rcx, [rsp+58h+var_18]
0x18000b58e  xor     rcx, rsp; StackCookie
0x18000b591  call    __security_check_cookie
0x18000b596  mov     rbx, [rsp+58h+arg_10]
0x18000b59b  mov     rsi, [rsp+58h+arg_18]
0x18000b5a0  add     rsp, 50h
0x18000b5a4  pop     rdi
0x18000b5a5  retn
```
