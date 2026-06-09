# std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(IUnknown * const &,unsigned __int64)

- ea: `0x18001c408`
- end: `0x18001c45c`
- name: `??$_Find_last@PEAUIUnknown@@@?$_Hash@V?$_Umap_traits@PEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@V?$_Uhash_compare@PEAUIUnknown@@U?$hash@PEAUIUnknown@@@std@@U?$equal_to@PEAUIUnknown@@@3@@3@V?$allocator@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@PEAX@std@@@1@AEBQEAUIUnknown@@_K@Z`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c52c`
- `0x18001ce84`
- `0x18001f35c`
- `0x18001f41c`
- `0x18001f55c`
- `0x18001f704`
- `0x18001f8ac`
- `0x180020fdc`
- `0x180021048`
- `0x1800220b0`

## callees

- `0x18001c408`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<IUnknown *,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>,std::_Uhash_compare<IUnknown *,std::hash<IUnknown *>,std::equal_to<IUnknown *>>,std::allocator<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>,0>>::_Find_last<IUnknown *>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v4; // r11
  _QWORD *v5; // r10
  __int64 v6; // rax
  _QWORD *v7; // r9

  v4 = a1[3];
  v5 = (_QWORD *)a1[1];
  v6 = 2 * (a4 & a1[6]);
  v7 = *(_QWORD **)(v4 + 16 * (a4 & a1[6]) + 8);
  if ( v7 == v5 )
  {
    *a2 = v5;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    while ( *a3 != v7[2] )
    {
      if ( v7 == *(_QWORD **)(v4 + 8 * v6) )
      {
        *a2 = v7;
        goto LABEL_3;
      }
      v7 = (_QWORD *)v7[1];
    }
    *a2 = *v7;
    a2[1] = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x18001c408  mov     rax, [rcx+30h]
0x18001c40c  mov     r11, [rcx+18h]
0x18001c410  and     rax, r9
0x18001c413  mov     r10, [rcx+8]
0x18001c417  add     rax, rax
0x18001c41a  mov     r9, [r11+rax*8+8]
0x18001c41f  cmp     r9, r10
0x18001c422  jnz     short loc_18001C431
0x18001c424  mov     [rdx], r10
0x18001c427  mov     qword ptr [rdx+8], 0
0x18001c42f  jmp     short loc_18001C458
0x18001c431  mov     rcx, [r11+rax*8]
0x18001c435  mov     rax, [r8]
0x18001c438  cmp     rax, [r9+10h]
0x18001c43c  jz      short loc_18001C44E
0x18001c43e  cmp     r9, rcx
0x18001c441  jz      short loc_18001C449
0x18001c443  mov     r9, [r9+8]
0x18001c447  jmp     short loc_18001C438
0x18001c449  mov     [rdx], r9
0x18001c44c  jmp     short loc_18001C427
0x18001c44e  mov     rax, [r9]
0x18001c451  mov     [rdx], rax
0x18001c454  mov     [rdx+8], r9
0x18001c458  mov     rax, rdx
0x18001c45b  retn
```
