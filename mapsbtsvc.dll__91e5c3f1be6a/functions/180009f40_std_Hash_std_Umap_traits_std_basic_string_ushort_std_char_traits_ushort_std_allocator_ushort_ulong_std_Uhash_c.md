# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x180009f40`
- end: `0x180009fb2`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `114`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009d3c`
- `0x180009de8`
- `0x180009e94`
- `0x18000a460`
- `0x18000a564`
- `0x18000a6d8`
- `0x18000a9b8`
- `0x18000aab8`
- `0x180010ed4`

## callees

- `0x1800098b0`
- `0x180009f40`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
              (__int64)a1,
              a3,
              (__int64)(v8 + 2)) )
    {
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    *a2 = *v8;
    a2[1] = v8;
  }
  return a2;
}

```

## disassembly

```asm
0x180009f40  push    rbx
0x180009f42  push    rbp
0x180009f43  push    rsi
0x180009f44  push    rdi
0x180009f45  sub     rsp, 28h
0x180009f49  mov     rax, [rcx+30h]
0x180009f4d  mov     rbx, rdx
0x180009f50  mov     rsi, [rcx+18h]
0x180009f54  and     rax, r9
0x180009f57  mov     rdx, [rcx+8]
0x180009f5b  add     rax, rax
0x180009f5e  mov     rbp, r8
0x180009f61  mov     rdi, [rsi+rax*8+8]
0x180009f66  cmp     rdi, rdx
0x180009f69  jnz     short loc_180009F78
0x180009f6b  mov     [rbx], rdx
0x180009f6e  mov     qword ptr [rbx+8], 0
0x180009f76  jmp     short loc_180009FA6
0x180009f78  mov     rsi, [rsi+rax*8]
0x180009f7c  lea     r8, [rdi+10h]
0x180009f80  mov     rdx, rbp
0x180009f83  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180009f88  test    al, al
0x180009f8a  jz      short loc_180009F9C
0x180009f8c  cmp     rdi, rsi
0x180009f8f  jz      short loc_180009F97
0x180009f91  mov     rdi, [rdi+8]
0x180009f95  jmp     short loc_180009F7C
0x180009f97  mov     [rbx], rdi
0x180009f9a  jmp     short loc_180009F6E
0x180009f9c  mov     rax, [rdi]
0x180009f9f  mov     [rbx], rax
0x180009fa2  mov     [rbx+8], rdi
0x180009fa6  mov     rax, rbx
0x180009fa9  add     rsp, 28h
0x180009fad  pop     rdi
0x180009fae  pop     rsi
0x180009faf  pop     rbp
0x180009fb0  pop     rbx
0x180009fb1  retn
```
