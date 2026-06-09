# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>,void *>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>,void *> *,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY> &&)

- ea: `0x18000f238`
- end: `0x18000f422`
- name: `??$?0U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@PEAX@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@1@@Z`
- size: `490`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fcfc`

## callees

- `0x180002a80`
- `0x18000f238`
- `0x1800118bc`
- `0x1800118fc`
- `0x180011c6c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>,void *>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v7; // rax
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rsi
  _OWORD *v10; // rbp
  __int64 v11; // rdi
  size_t v12; // rcx
  void *v13; // rax
  void *v14; // rcx
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 i; // rcx

  *a1 = a2;
  a1[1] = 0;
  v7 = (char *)operator new(0x60u);
  a1[1] = v7;
  v8 = v7 + 32;
  *((_OWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  v9 = *(_QWORD *)(a4 + 16);
  if ( *(_QWORD *)(a4 + 24) <= 7u )
    v10 = (_OWORD *)a4;
  else
    v10 = *(_OWORD **)a4;
  v11 = 0x7FFFFFFFFFFFFFFELL;
  if ( v9 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v9 > 7 )
  {
    if ( (v9 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v11 = v9 | 7;
      if ( (v9 | 7) < 0xA )
        v11 = 10;
      if ( (unsigned __int64)(v11 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_25;
      v12 = 2 * (v11 + 1);
      if ( !v12 )
      {
        v15 = 0;
        goto LABEL_20;
      }
    }
    else
    {
      v12 = -2;
    }
    if ( v12 >= 0x1000 )
    {
      if ( v12 + 39 >= v12 )
      {
        v13 = operator new(v12 + 39);
        v14 = v13;
        if ( !v13 )
          __fastfail(5u);
        v15 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v15 - 1) = v14;
        goto LABEL_20;
      }
LABEL_25:
      __scrt_throw_std_bad_array_new_length();
    }
    v15 = operator new(v12);
LABEL_20:
    *v8 = v15;
    v8[2] = v9;
    v8[3] = v11;
    memcpy_0(v15, v10, 2 * v9 + 2);
    goto LABEL_21;
  }
  *((_QWORD *)v7 + 6) = v9;
  *((_QWORD *)v7 + 7) = 7;
  *(_OWORD *)v8 = *v10;
LABEL_21:
  v8[4] = *(_QWORD *)(a4 + 32);
  v8[5] = *(_QWORD *)(a4 + 40);
  v8[6] = 0;
  v8[7] = 0;
  v16 = operator new(0x20u);
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  v8[6] = v16;
  v8[6] = *(_QWORD *)(a4 + 48);
  *(_QWORD *)(a4 + 48) = v16;
  v17 = v8[7];
  v8[7] = *(_QWORD *)(a4 + 56);
  *(_QWORD *)(a4 + 56) = v17;
  *(_QWORD *)a1[1] = a3;
  *(_QWORD *)(a1[1] + 8LL) = a3;
  *(_QWORD *)(a1[1] + 16LL) = a3;
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(a1[1] + i + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x18000f238  mov     [rsp+arg_10], rbx
0x18000f23d  mov     [rsp+arg_18], rbp
0x18000f242  mov     [rsp+arg_0], rcx
0x18000f247  push    rsi
0x18000f248  push    rdi
0x18000f249  push    r12
0x18000f24b  push    r14
0x18000f24d  push    r15
0x18000f24f  sub     rsp, 20h
0x18000f253  mov     r15, r9
0x18000f256  mov     r12, r8
0x18000f259  mov     r14, rcx
0x18000f25c  mov     [rcx], rdx
0x18000f25f  mov     qword ptr [rcx+8], 0
0x18000f267  mov     ecx, 60h ; '`'; Size
0x18000f26c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f271  mov     [r14+8], rax
0x18000f275  lea     rbx, [rax+20h]
0x18000f279  mov     [rsp+48h+arg_8], rbx
0x18000f27e  xorps   xmm0, xmm0
0x18000f281  movups  xmmword ptr [rbx], xmm0
0x18000f284  mov     qword ptr [rbx+10h], 0
0x18000f28c  mov     qword ptr [rbx+18h], 0
0x18000f294  mov     rsi, [r15+10h]
0x18000f298  mov     ecx, 7
0x18000f29d  cmp     [r15+18h], rcx
0x18000f2a1  jbe     short loc_18000F2A8
0x18000f2a3  mov     rbp, [r15]
0x18000f2a6  jmp     short loc_18000F2AB
0x18000f2a8  mov     rbp, r15
0x18000f2ab  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18000f2b5  cmp     rsi, rdi
0x18000f2b8  ja      loc_18000F416
0x18000f2be  cmp     rsi, rcx
0x18000f2c1  ja      short loc_18000F2D8
0x18000f2c3  mov     [rbx+10h], rsi
0x18000f2c7  mov     [rbx+18h], rcx
0x18000f2cb  movups  xmm0, xmmword ptr [rbp+0]
0x18000f2cf  movdqu  xmmword ptr [rbx], xmm0
0x18000f2d3  jmp     loc_18000F376
0x18000f2d8  mov     rax, rsi
0x18000f2db  or      rax, rcx
0x18000f2de  cmp     rax, rdi
0x18000f2e1  jbe     short loc_18000F315
0x18000f2e3  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000f2ea  cmp     rcx, 1000h
0x18000f2f1  jb      short loc_18000F352
0x18000f2f3  lea     rax, [rcx+27h]
0x18000f2f7  cmp     rax, rcx
0x18000f2fa  jbe     loc_18000F41C
0x18000f300  mov     rcx, rax; Size
0x18000f303  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f308  mov     rcx, rax
0x18000f30b  test    rax, rax
0x18000f30e  jnz     short loc_18000F344
0x18000f310  lea     ecx, [rax+5]
0x18000f313  int     29h; Win8: RtlFailFast(ecx)
0x18000f315  mov     rdi, rax
0x18000f318  mov     ecx, 0Ah
0x18000f31d  cmp     rax, rcx
0x18000f320  cmovb   rdi, rcx
0x18000f324  lea     rcx, [rdi+1]
0x18000f328  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f332  cmp     rcx, rax
0x18000f335  ja      loc_18000F41C
0x18000f33b  add     rcx, rcx
0x18000f33e  jnz     short loc_18000F2EA
0x18000f340  xor     eax, eax
0x18000f342  jmp     short loc_18000F357
0x18000f344  add     rax, 27h ; '''
0x18000f348  and     rax, 0FFFFFFFFFFFFFFE0h
0x18000f34c  mov     [rax-8], rcx
0x18000f350  jmp     short loc_18000F357
0x18000f352  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f357  mov     [rbx], rax
0x18000f35a  mov     [rbx+10h], rsi
0x18000f35e  mov     [rbx+18h], rdi
0x18000f362  lea     r8, ds:2[rsi*2]; Size
0x18000f36a  mov     rdx, rbp; Src
0x18000f36d  mov     rcx, rax; void *
0x18000f370  call    memcpy_0
0x18000f375  nop
0x18000f376  mov     rax, [r15+20h]
0x18000f37a  mov     [rbx+20h], rax
0x18000f37e  mov     rax, [r15+28h]
0x18000f382  mov     [rbx+28h], rax
0x18000f386  mov     qword ptr [rbx+30h], 0
0x18000f38e  mov     qword ptr [rbx+38h], 0
0x18000f396  mov     ecx, 20h ; ' '; Size
0x18000f39b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f3a0  mov     [rax], rax
0x18000f3a3  mov     [rax+8], rax
0x18000f3a7  mov     [rax+10h], rax
0x18000f3ab  mov     word ptr [rax+18h], 101h
0x18000f3b1  mov     [rbx+30h], rax
0x18000f3b5  mov     rcx, [r15+30h]
0x18000f3b9  mov     [rbx+30h], rcx
0x18000f3bd  mov     [r15+30h], rax
0x18000f3c1  mov     rcx, [rbx+38h]
0x18000f3c5  mov     rax, [r15+38h]
0x18000f3c9  mov     [rbx+38h], rax
0x18000f3cd  mov     [r15+38h], rcx
0x18000f3d1  mov     rax, [r14+8]
0x18000f3d5  mov     [rax], r12
0x18000f3d8  mov     rax, [r14+8]
0x18000f3dc  mov     [rax+8], r12
0x18000f3e0  mov     rax, [r14+8]
0x18000f3e4  mov     [rax+10h], r12
0x18000f3e8  xor     ecx, ecx
0x18000f3ea  mov     rax, [r14+8]
0x18000f3ee  mov     byte ptr [rax+rcx+18h], 0
0x18000f3f3  inc     rcx
0x18000f3f6  cmp     rcx, 2
0x18000f3fa  jnz     short loc_18000F3EA
0x18000f3fc  mov     rax, r14
0x18000f3ff  mov     rbx, [rsp+48h+arg_10]
0x18000f404  mov     rbp, [rsp+48h+arg_18]
0x18000f409  add     rsp, 20h
0x18000f40d  pop     r15
0x18000f40f  pop     r14
0x18000f411  pop     r12
0x18000f413  pop     rdi
0x18000f414  pop     rsi
0x18000f415  retn
0x18000f416  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000f41c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
