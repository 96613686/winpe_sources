# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::~_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>(void)

- ea: `0x180010ae8`
- end: `0x180010b65`
- name: `??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA@XZ`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004b00`
- `0x18002412c`
- `0x18002882c`

## callees

- `0x180010ae8`
- `0x180011ec4`
- `0x1800146e4`
- `0x180017bc4`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(
        __int64 a1)
{
  __int64 v2; // rcx
  _QWORD **v3; // rcx
  _QWORD *v4; // rdx
  _QWORD *v5; // rbx

  v2 = *(_QWORD *)(a1 + 24);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*(_QWORD *)(a1 + 40) - v2) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
  }
  v3 = *(_QWORD ***)(a1 + 8);
  *v3[1] = 0;
  v4 = *v3;
  if ( *v3 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>();
      v4 = v5;
    }
    while ( v5 );
  }
  operator delete(*(void **)(a1 + 8), (const struct std::nothrow_t *)0x50);
}

```

## disassembly

```asm
0x180010ae8  mov     [rsp+arg_0], rbx
0x180010aed  push    rdi
0x180010aee  sub     rsp, 20h
0x180010af2  mov     rdi, rcx
0x180010af5  mov     rcx, [rcx+18h]
0x180010af9  test    rcx, rcx
0x180010afc  jz      short loc_180010B26
0x180010afe  mov     rdx, [rdi+28h]
0x180010b02  sub     rdx, rcx
0x180010b05  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180010b09  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010b0e  mov     qword ptr [rdi+18h], 0
0x180010b16  mov     qword ptr [rdi+20h], 0
0x180010b1e  mov     qword ptr [rdi+28h], 0
0x180010b26  mov     rcx, [rdi+8]
0x180010b2a  mov     rax, [rcx+8]
0x180010b2e  mov     qword ptr [rax], 0
0x180010b35  mov     rdx, [rcx]
0x180010b38  test    rdx, rdx
0x180010b3b  jz      short loc_180010B4D
0x180010b3d  mov     rbx, [rdx]
0x180010b40  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180010b45  mov     rdx, rbx
0x180010b48  test    rbx, rbx
0x180010b4b  jnz     short loc_180010B3D
0x180010b4d  mov     rcx, [rdi+8]; void *
0x180010b51  mov     edx, 50h ; 'P'; struct std::nothrow_t *
0x180010b56  mov     rbx, [rsp+28h+arg_0]
0x180010b5b  add     rsp, 20h
0x180010b5f  pop     rdi
0x180010b60  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
