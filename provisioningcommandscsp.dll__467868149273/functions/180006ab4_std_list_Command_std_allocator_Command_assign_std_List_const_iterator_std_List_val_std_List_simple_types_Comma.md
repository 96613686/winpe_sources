# std::list<Command,std::allocator<Command>>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)

- ea: `0x180006ab4`
- end: `0x180006bf7`
- name: `??$assign@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@1@0@Z`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800076ac`

## callees

- `0x180006a70`
- `0x180006ab4`
- `0x180007e9c`
- `0x1800081f0`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006bcf`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180006bcf`

## pseudocode

```c
__int64 __fastcall std::list<Command>::assign<std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>>(
        _QWORD **a1,
        __int64 *a2,
        __int64 *a3)
{
  _QWORD *v5; // r14
  __int64 *v6; // rdi
  __int64 v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rax
  _QWORD **v11; // [rsp+50h] [rbp+8h] BYREF

  v11 = a1;
  v5 = a1;
  v6 = (__int64 *)**a1;
  try
  {
    while ( a2 != a3 )
    {
      if ( v6 == (__int64 *)*v5 )
      {
        while ( a2 != a3 )
        {
          v8 = *v5;
          v9 = std::_List_buy<Command>::_Buynode<Command>(a1, *v5, *(_QWORD *)(*v5 + 8LL), a2 + 2);
          v10 = v5[1];
          a1 = (_QWORD **)(0x1FFFFFFFFFFFFFELL - v10);
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
      a1 = (_QWORD **)(v6 + 10);
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
0x180006ab4  mov     [rsp+arg_8], rbx
0x180006ab9  mov     [rsp+arg_10], rsi
0x180006abe  mov     [rsp+arg_0], rcx
0x180006ac3  push    rdi
0x180006ac4  push    r12
0x180006ac6  push    r13
0x180006ac8  push    r14
0x180006aca  push    r15
0x180006acc  sub     rsp, 20h
0x180006ad0  mov     rsi, r8
0x180006ad3  mov     rbx, rdx
0x180006ad6  mov     r14, rcx
0x180006ad9  mov     rdi, [rcx]
0x180006adc  mov     rdi, [rdi]
0x180006adf  or      r12, 0FFFFFFFFFFFFFFFFh
0x180006ae3  cmp     rbx, rsi
0x180006ae6  jz      loc_180006B6F
0x180006aec  cmp     rdi, [r14]
0x180006aef  jz      short loc_180006B6A
0x180006af1  lea     r15, [rbx+10h]
0x180006af5  lea     r13, [rdi+10h]
0x180006af9  cmp     r13, r15
0x180006afc  jz      short loc_180006B0F
0x180006afe  mov     r9, r12
0x180006b01  xor     r8d, r8d
0x180006b04  mov     rdx, r15
0x180006b07  mov     rcx, r13; void *
0x180006b0a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006b0f  lea     rdx, [r15+20h]
0x180006b13  lea     rcx, [r13+20h]; void *
0x180006b17  cmp     rcx, rdx
0x180006b1a  jz      short loc_180006B27
0x180006b1c  mov     r9, r12
0x180006b1f  xor     r8d, r8d
0x180006b22  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006b27  lea     rdx, [r15+40h]
0x180006b2b  lea     rcx, [r13+40h]; void *
0x180006b2f  cmp     rcx, rdx
0x180006b32  jz      short loc_180006B3F
0x180006b34  mov     r9, r12
0x180006b37  xor     r8d, r8d
0x180006b3a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006b3f  mov     eax, [r15+60h]
0x180006b43  mov     [r13+60h], eax
0x180006b47  mov     eax, [r15+64h]
0x180006b4b  mov     [r13+64h], eax
0x180006b4f  mov     eax, [r15+68h]
0x180006b53  mov     [r13+68h], eax
0x180006b57  mov     eax, [r15+6Ch]
0x180006b5b  mov     [r13+6Ch], eax
0x180006b5f  mov     rbx, [rbx]
0x180006b62  mov     rdi, [rdi]
0x180006b65  jmp     loc_180006AE3
0x180006b6a  cmp     rbx, rsi
0x180006b6d  jnz     short loc_180006B9B
0x180006b6f  mov     r9, [r14]
0x180006b72  mov     r8, rdi
0x180006b75  lea     rdx, [rsp+48h+arg_0]
0x180006b7a  mov     rcx, r14
0x180006b7d  call    ?erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@2@0@Z; std::list<Command>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>,std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>)
0x180006b82  mov     rbx, [rsp+48h+arg_8]
0x180006b87  mov     rsi, [rsp+48h+arg_10]
0x180006b8c  add     rsp, 20h
0x180006b90  pop     r15
0x180006b92  pop     r14
0x180006b94  pop     r13
0x180006b96  pop     r12
0x180006b98  pop     rdi
0x180006b99  retn
0x180006b9b  mov     r15, [r14]
0x180006b9e  lea     r9, [rbx+10h]
0x180006ba2  mov     r8, [r15+8]
0x180006ba6  mov     rdx, r15
0x180006ba9  call    ??$_Buynode@UCommand@@@?$_List_buy@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@1@PEAU21@0$$QEAUCommand@@@Z; std::_List_buy<Command>::_Buynode<Command>(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *,Command &&)
0x180006bae  mov     rdx, rax
0x180006bb1  mov     rax, [r14+8]
0x180006bb5  mov     rcx, 1FFFFFFFFFFFFFEh
0x180006bbf  sub     rcx, rax
0x180006bc2  cmp     rcx, 1
0x180006bc6  jnb     short loc_180006BDB
0x180006bc8  lea     rcx, aListTTooLong; "list<T> too long"
0x180006bcf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180006bdb  inc     rax
0x180006bde  mov     [r14+8], rax
0x180006be2  mov     [r15+8], rdx
0x180006be6  mov     rax, [rdx+8]
0x180006bea  mov     [rax], rdx
0x180006bed  mov     rbx, [rbx]
0x180006bf0  jmp     loc_180006B6A
```
