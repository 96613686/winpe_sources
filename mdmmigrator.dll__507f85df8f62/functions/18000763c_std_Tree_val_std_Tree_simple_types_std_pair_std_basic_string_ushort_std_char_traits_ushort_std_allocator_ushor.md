# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *)

- ea: `0x18000763c`
- end: `0x18000769c`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z`
- size: `96`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000763c`
- `0x1800076a4`
- `0x18000c634`
- `0x18000c69c`
- `0x18000de8c`

## callees

- `0x1800026b0`
- `0x18000763c`
- `0x180007720`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rsi
  __int64 *v6; // rdi

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    std::wstring::~wstring(v6 + 8);
    std::wstring::~wstring(v6 + 4);
    operator delete(v6, (const struct std::nothrow_t *)0x60);
  }
}

```

## disassembly

```asm
0x18000763c  push    rbx
0x18000763e  push    rbp
0x18000763f  push    rsi
0x180007640  push    rdi
0x180007641  push    r14
0x180007643  sub     rsp, 20h
0x180007647  cmp     byte ptr [r8+19h], 0
0x18000764c  mov     rsi, r8
0x18000764f  mov     rbp, rdx
0x180007652  mov     r14, rcx
0x180007655  jnz     short loc_180007691
0x180007657  mov     r8, [rsi+10h]
0x18000765b  mov     rdx, rbp
0x18000765e  mov     rcx, r14
0x180007661  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180007666  mov     rdi, rsi
0x180007669  mov     rsi, [rsi]
0x18000766c  lea     rcx, [rdi+40h]; void *
0x180007670  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007675  lea     rcx, [rdi+20h]; void *
0x180007679  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000767e  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x180007683  mov     rcx, rdi; void *
0x180007686  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000768b  cmp     byte ptr [rsi+19h], 0
0x18000768f  jz      short loc_180007657
0x180007691  add     rsp, 20h
0x180007695  pop     r14
0x180007697  pop     rdi
0x180007698  pop     rsi
0x180007699  pop     rbp
0x18000769a  pop     rbx
0x18000769b  retn
```
