# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x14000d124`
- end: `0x14000d22b`
- name: `?insert@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `263`
- prototype: `char **__fastcall(_QWORD *, char **, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140003260`
- `0x14000dd80`
- `0x14000eeb8`

## callees

- `0x140004390`
- `0x140005020`
- `0x140005a04`
- `0x14000d124`

## pseudocode

```c
char **__fastcall std::vector<std::wstring>::insert(_QWORD *a1, char **a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  char *v5; // rdi
  char *v7; // rax
  __int64 v8; // rsi
  char *v9; // xmm1_8
  __int128 v10; // xmm0
  __int128 v11; // xmm0
  char *v13[10]; // [rsp+28h] [rbp-50h] BYREF

  v4 = a1[1];
  v5 = (char *)a3;
  if ( v4 == a1[2] )
  {
    v5 = std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, a3, (__int128 *)a4);
  }
  else if ( a3 == v4 )
  {
    *(_OWORD *)v4 = 0;
    *(_QWORD *)(v4 + 16) = 0;
    *(_QWORD *)(v4 + 24) = 0;
    *(_OWORD *)v4 = *(_OWORD *)a4;
    *(_OWORD *)(v4 + 16) = *(_OWORD *)(a4 + 16);
    *(_QWORD *)(a4 + 16) = 0;
    *(_QWORD *)(a4 + 24) = 7;
    *(_WORD *)a4 = 0;
    a1[1] += 32LL;
  }
  else
  {
    v7 = *(char **)a4;
    v8 = v4 - 32;
    v9 = *(char **)(a4 + 24);
    v13[1] = 0;
    v13[0] = v7;
    v10 = *(_OWORD *)(a4 + 8);
    *(_QWORD *)(a4 + 16) = 0;
    *(_WORD *)a4 = 0;
    *(_QWORD *)(a4 + 24) = 7;
    *(_OWORD *)&v13[1] = v10;
    v11 = *(_OWORD *)(v4 - 32);
    v13[3] = v9;
    *(_OWORD *)v4 = v11;
    *(_OWORD *)(v4 + 16) = *(_OWORD *)(v4 - 32 + 16);
    *(_QWORD *)(v8 + 16) = 0;
    *(_QWORD *)(v8 + 24) = 7;
    *(_WORD *)v8 = 0;
    a1[1] += 32LL;
    while ( (char *)v8 != v5 )
    {
      v8 -= 32;
      v4 -= 32;
      std::wstring::operator=((char **)v4, v8);
    }
    std::wstring::operator=((char **)v5, (__int64)v13);
    std::wstring::~wstring(v13);
  }
  *a2 = v5;
  return a2;
}

```

## disassembly

```asm
0x14000d124  push    rbx
0x14000d126  push    rsi
0x14000d127  push    rdi
0x14000d128  push    r14
0x14000d12a  sub     rsp, 58h
0x14000d12e  mov     rbx, [rcx+8]
0x14000d132  mov     rdi, r8
0x14000d135  mov     r14, rdx
0x14000d138  cmp     rbx, [rcx+10h]
0x14000d13c  jz      loc_14000D20D
0x14000d142  xorps   xmm0, xmm0
0x14000d145  mov     edx, 7
0x14000d14a  cmp     r8, rbx
0x14000d14d  jnz     short loc_14000D182
0x14000d14f  movups  xmmword ptr [rbx], xmm0
0x14000d152  xor     eax, eax
0x14000d154  mov     [rbx+10h], rax
0x14000d158  mov     [rbx+18h], rax
0x14000d15c  movups  xmm0, xmmword ptr [r9]
0x14000d160  movups  xmmword ptr [rbx], xmm0
0x14000d163  movups  xmm1, xmmword ptr [r9+10h]
0x14000d168  movups  xmmword ptr [rbx+10h], xmm1
0x14000d16c  mov     [r9+10h], rax
0x14000d170  mov     [r9+18h], rdx
0x14000d174  mov     [r9], ax
0x14000d178  add     qword ptr [rcx+8], 20h ; ' '
0x14000d17d  jmp     loc_14000D21B
0x14000d182  mov     rax, [r9]
0x14000d185  lea     rsi, [rbx-20h]
0x14000d189  movsd   xmm1, qword ptr [r9+18h]
0x14000d18f  movups  xmmword ptr [rsp+78h+var_50], xmm0
0x14000d194  mov     qword ptr [rsp+78h+var_50], rax
0x14000d199  xor     eax, eax
0x14000d19b  movups  xmm0, xmmword ptr [r9+8]
0x14000d1a0  mov     [r9+10h], rax
0x14000d1a4  mov     [r9], ax
0x14000d1a8  mov     [r9+18h], rdx
0x14000d1ac  movups  xmmword ptr [rsp+78h+var_50+8], xmm0
0x14000d1b1  mov     [rsp+78h+var_58], rcx
0x14000d1b6  movups  xmm0, xmmword ptr [rsi]
0x14000d1b9  movsd   [rsp+78h+var_38], xmm1
0x14000d1bf  movups  xmmword ptr [rbx], xmm0
0x14000d1c2  movups  xmm1, xmmword ptr [rsi+10h]
0x14000d1c6  movups  xmmword ptr [rbx+10h], xmm1
0x14000d1ca  mov     [rsi+10h], rax
0x14000d1ce  mov     [rsi+18h], rdx
0x14000d1d2  mov     [rsi], ax
0x14000d1d5  add     qword ptr [rcx+8], 20h ; ' '
0x14000d1da  jmp     short loc_14000D1EF
0x14000d1dc  sub     rsi, 20h ; ' '
0x14000d1e0  sub     rbx, 20h ; ' '
0x14000d1e4  mov     rdx, rsi
0x14000d1e7  mov     rcx, rbx
0x14000d1ea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000d1ef  cmp     rsi, rdi
0x14000d1f2  jnz     short loc_14000D1DC
0x14000d1f4  lea     rdx, [rsp+78h+var_50]
0x14000d1f9  mov     rcx, rdi
0x14000d1fc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000d201  lea     rcx, [rsp+78h+var_50]
0x14000d206  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d20b  jmp     short loc_14000D21B
0x14000d20d  mov     r8, r9
0x14000d210  mov     rdx, rdi
0x14000d213  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14000d218  mov     rdi, rax
0x14000d21b  mov     [r14], rdi
0x14000d21e  mov     rax, r14
0x14000d221  add     rsp, 58h
0x14000d225  pop     r14
0x14000d227  pop     rdi
0x14000d228  pop     rsi
0x14000d229  pop     rbx
0x14000d22a  retn
```
