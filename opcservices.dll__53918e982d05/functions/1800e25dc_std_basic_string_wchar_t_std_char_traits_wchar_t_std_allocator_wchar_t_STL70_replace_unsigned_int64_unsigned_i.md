# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::replace(unsigned __int64,unsigned __int64,unsigned __int64,wchar_t)

- ea: `0x1800e25dc`
- end: `0x1800e26d7`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K00_W@Z`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013cf4`
- `0x180015778`

## callees

- `0x180018fc0`
- `0x18006f770`
- `0x1800cded0`
- `0x1800e25dc`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800e2645`
- `msvcrt!memmove_s` at `0x1800e269d`
- `msvcrt!memmove_s` at `0x1800e2645`
- `msvcrt!memmove_s` at `0x1800e269d`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(_QWORD *a1)
{
  __int64 v1; // rax
  _BOOL8 v3; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rbp
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax

  v1 = a1[3];
  v3 = v1 != 0;
  if ( (unsigned __int64)(v1 - v3) >= 0xFFFFFFFFFFFFFFFEuLL )
    std::_String_base::_Xlen();
  v4 = a1 + 1;
  v5 = a1[3] - v3;
  v6 = v5 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(a1, v5 + 1, 0) )
  {
    if ( !v3 )
    {
      v7 = a1[4];
      v4 = a1 + 1;
      if ( v7 < 8 )
      {
        v8 = a1 + 1;
        v9 = a1 + 1;
      }
      else
      {
        v8 = (_QWORD *)*v4;
        v9 = (_QWORD *)*v4;
      }
      memmove_s((char *)v8 + 2, 2 * v7 - 2, v9, 2 * v5);
    }
    std::wstring::_Chassign(a1, 0, 1, 47);
    if ( a1[4] >= 8u )
      v4 = (_QWORD *)*v4;
    a1[3] = v6;
    *((_WORD *)v4 + v6) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800e25dc  push    rbx
0x1800e25de  push    rbp
0x1800e25df  push    rsi
0x1800e25e0  push    rdi
0x1800e25e1  push    r14
0x1800e25e3  sub     rsp, 20h
0x1800e25e7  mov     rax, [rcx+18h]
0x1800e25eb  mov     esi, 1
0x1800e25f0  cmp     rax, rsi
0x1800e25f3  mov     rdi, rcx
0x1800e25f6  cmovb   rsi, rax
0x1800e25fa  sub     rax, rsi
0x1800e25fd  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800e2601  jb      short loc_1800E2608
0x1800e2603  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800e2608  mov     r14, [rdi+18h]
0x1800e260c  lea     rbx, [rdi+8]
0x1800e2610  sub     r14, rsi
0x1800e2613  cmp     rsi, 1
0x1800e2617  jbe     short loc_1800E264B
0x1800e2619  mov     rdx, [rdi+20h]
0x1800e261d  cmp     rdx, 8
0x1800e2621  jb      short loc_1800E262B
0x1800e2623  mov     rcx, [rbx]
0x1800e2626  mov     rax, rcx
0x1800e2629  jmp     short loc_1800E2631
0x1800e262b  mov     rcx, rbx
0x1800e262e  mov     rax, rbx
0x1800e2631  lea     r9, [r14+r14]; SourceSize
0x1800e2635  add     rcx, 2; Destination
0x1800e2639  lea     r8, [rax+rsi*2]; Source
0x1800e263d  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]; DestinationSize
0x1800e2645  call    cs:__imp_memmove_s
0x1800e264b  mov     rbp, [rdi+18h]
0x1800e264f  xor     r8d, r8d
0x1800e2652  sub     rbp, rsi
0x1800e2655  mov     rcx, rdi
0x1800e2658  inc     rbp
0x1800e265b  mov     rdx, rbp
0x1800e265e  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800e2663  test    al, al
0x1800e2665  jz      short loc_1800E26C9
0x1800e2667  cmp     rsi, 1
0x1800e266b  jnb     short loc_1800E26A3
0x1800e266d  mov     rdx, [rdi+20h]
0x1800e2671  lea     rbx, [rdi+8]
0x1800e2675  cmp     rdx, 8
0x1800e2679  jb      short loc_1800E2683
0x1800e267b  mov     rcx, [rbx]
0x1800e267e  mov     rax, rcx
0x1800e2681  jmp     short loc_1800E2689
0x1800e2683  mov     rcx, rbx
0x1800e2686  mov     rax, rbx
0x1800e2689  lea     r9, [r14+r14]; SourceSize
0x1800e268d  add     rcx, 2; Destination
0x1800e2691  lea     r8, [rax+rsi*2]; Source
0x1800e2695  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]; DestinationSize
0x1800e269d  call    cs:__imp_memmove_s
0x1800e26a3  xor     edx, edx
0x1800e26a5  mov     rcx, rdi
0x1800e26a8  lea     r9d, [rdx+2Fh]
0x1800e26ac  lea     r8d, [rdx+1]
0x1800e26b0  call    ?_Chassign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0_W@Z; std::wstring::_Chassign(unsigned __int64,unsigned __int64,wchar_t)
0x1800e26b5  cmp     qword ptr [rdi+20h], 8
0x1800e26ba  jb      short loc_1800E26BF
0x1800e26bc  mov     rbx, [rbx]
0x1800e26bf  xor     eax, eax
0x1800e26c1  mov     [rdi+18h], rbp
0x1800e26c5  mov     [rbx+rbp*2], ax
0x1800e26c9  mov     rax, rdi
0x1800e26cc  add     rsp, 20h
0x1800e26d0  pop     r14
0x1800e26d2  pop     rdi
0x1800e26d3  pop     rsi
0x1800e26d4  pop     rbp
0x1800e26d5  pop     rbx
0x1800e26d6  retn
```
