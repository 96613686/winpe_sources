# std::list<Command,std::allocator<Command>>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)

- ea: `0x1800067a0`
- end: `0x1800068dc`
- name: `??$assign@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@0@Z`
- size: `316`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007360`

## callees

- `0x180006760`
- `0x1800067a0`
- `0x180007b08`
- `0x180007e48`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800068ba`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800068ba`

## pseudocode

```c
__int64 __fastcall std::list<Command>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(
        __int64 *a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v5; // r14
  __int64 *v6; // rdi
  __int64 v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 *v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = a1;
  v5 = a1;
  v6 = *(__int64 **)*a1;
  try
  {
    while ( a2 != a3 )
    {
      if ( v6 == (__int64 *)*v5 )
      {
        while ( a2 != a3 )
        {
          v8 = *v5;
          v9 = std::_List_buy<Command>::_Buynode<Command>(
                 (__int64)a1,
                 *v5,
                 *(_QWORD *)(*v5 + 8),
                 (const struct Command *)(a2 + 2));
          v10 = v5[1];
          a1 = (__int64 *)(0x1FFFFFFFFFFFFFELL - v10);
          if ( v10 == 0x1FFFFFFFFFFFFFELL )
            std::_Xlength_error("list<T> too long");
          v5[1] = v10 + 1;
          *(_QWORD *)(v8 + 8) = v9;
          **(_QWORD **)(v9 + 8) = v9;
          a2 = (__int64 *)*a2;
        }
        return std::list<Command>::erase(v5, &v11, v6, *v5);
      }
      if ( v6 + 2 != a2 + 2 )
        std::wstring::assign(v6 + 2);
      if ( v6 + 6 != a2 + 6 )
        std::wstring::assign(v6 + 6);
      a1 = v6 + 10;
      if ( v6 + 10 != a2 + 10 )
        std::wstring::assign(a1);
      *((_DWORD *)v6 + 28) = *((_DWORD *)a2 + 28);
      *((_DWORD *)v6 + 29) = *((_DWORD *)a2 + 29);
      *((_DWORD *)v6 + 30) = *((_DWORD *)a2 + 30);
      *((_DWORD *)v6 + 31) = *((_DWORD *)a2 + 31);
      a2 = (__int64 *)*a2;
      v6 = (__int64 *)*v6;
    }
  }
  catch ( ... )
  {
    std::list<Command>::clear(v11);
    throw;
  }
  return std::list<Command>::erase(v5, &v11, v6, *v5);
}

```

## disassembly

```asm
0x1800067a0  mov     [rsp+arg_8], rbx
0x1800067a5  mov     [rsp+arg_10], rsi
0x1800067aa  mov     [rsp+arg_0], rcx
0x1800067af  push    rdi
0x1800067b0  push    r12
0x1800067b2  push    r13
0x1800067b4  push    r14
0x1800067b6  push    r15
0x1800067b8  sub     rsp, 20h
0x1800067bc  mov     rsi, r8
0x1800067bf  mov     rbx, rdx
0x1800067c2  mov     r14, rcx
0x1800067c5  mov     rdi, [rcx]
0x1800067c8  mov     rdi, [rdi]
0x1800067cb  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800067cf  cmp     rbx, rsi
0x1800067d2  jz      loc_18000685B
0x1800067d8  cmp     rdi, [r14]
0x1800067db  jz      short loc_180006856
0x1800067dd  lea     r15, [rbx+10h]
0x1800067e1  lea     r13, [rdi+10h]
0x1800067e5  cmp     r13, r15
0x1800067e8  jz      short loc_1800067FB
0x1800067ea  mov     r9, r12
0x1800067ed  xor     r8d, r8d
0x1800067f0  mov     rdx, r15
0x1800067f3  mov     rcx, r13; void *
0x1800067f6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800067fb  lea     rdx, [r15+20h]
0x1800067ff  lea     rcx, [r13+20h]; void *
0x180006803  cmp     rcx, rdx
0x180006806  jz      short loc_180006813
0x180006808  mov     r9, r12
0x18000680b  xor     r8d, r8d
0x18000680e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006813  lea     rdx, [r15+40h]
0x180006817  lea     rcx, [r13+40h]; void *
0x18000681b  cmp     rcx, rdx
0x18000681e  jz      short loc_18000682B
0x180006820  mov     r9, r12
0x180006823  xor     r8d, r8d
0x180006826  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000682b  mov     eax, [r15+60h]
0x18000682f  mov     [r13+60h], eax
0x180006833  mov     eax, [r15+64h]
0x180006837  mov     [r13+64h], eax
0x18000683b  mov     eax, [r15+68h]
0x18000683f  mov     [r13+68h], eax
0x180006843  mov     eax, [r15+6Ch]
0x180006847  mov     [r13+6Ch], eax
0x18000684b  mov     rbx, [rbx]
0x18000684e  mov     rdi, [rdi]
0x180006851  jmp     loc_1800067CF
0x180006856  cmp     rbx, rsi
0x180006859  jnz     short loc_180006886
0x18000685b  mov     r9, [r14]
0x18000685e  mov     r8, rdi
0x180006861  lea     rdx, [rsp+48h+arg_0]
0x180006866  mov     rcx, r14
0x180006869  call    ?erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@0@Z; std::list<Command>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)
0x18000686e  mov     rbx, [rsp+48h+arg_8]
0x180006873  mov     rsi, [rsp+48h+arg_10]
0x180006878  add     rsp, 20h
0x18000687c  pop     r15
0x18000687e  pop     r14
0x180006880  pop     r13
0x180006882  pop     r12
0x180006884  pop     rdi
0x180006885  retn
0x180006886  mov     r15, [r14]
0x180006889  lea     r9, [rbx+10h]
0x18000688d  mov     r8, [r15+8]
0x180006891  mov     rdx, r15
0x180006894  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x180006899  mov     rdx, rax
0x18000689c  mov     rax, [r14+8]
0x1800068a0  mov     rcx, 1FFFFFFFFFFFFFEh
0x1800068aa  sub     rcx, rax
0x1800068ad  cmp     rcx, 1
0x1800068b1  jnb     short loc_1800068C0
0x1800068b3  lea     rcx, aListTTooLong; "list<T> too long"
0x1800068ba  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800068c0  inc     rax
0x1800068c3  mov     [r14+8], rax
0x1800068c7  mov     [r15+8], rdx
0x1800068cb  mov     rax, [rdx+8]
0x1800068cf  mov     [rax], rdx
0x1800068d2  mov     rbx, [rbx]
0x1800068d5  jmp     loc_180006856
```
