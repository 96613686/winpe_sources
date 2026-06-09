# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ESIMPM::EsimProfile,std::default_delete<ESIMPM::EsimProfile>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ESIMPM::EsimProfile,std::default_delete<ESIMPM::EsimProfile>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ESIMPM::EsimProfile,std::default_delete<ESIMPM::EsimProfile>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ESIMPM::EsimProfile,std::default_delete<ESIMPM::EsimProfile>>>>,0>>(void)

- ea: `0x140023868`
- end: `0x1400238d0`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400236ec`
- `0x140023a1c`
- `0x14002f35c`
- `0x1400312d4`
- `0x14003154c`

## callees

- `0x140003244`
- `0x14002377c`
- `0x140023868`
- `0x140023974`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::EsimProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ESIMPM::EsimProfile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>,0>>(
        void **a1)
{
  char *v2; // rdi
  char *v3; // rbx

  v2 = (char *)*((_QWORD *)*a1 + 1);
  while ( !v2[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      *((char **)v2 + 2));
    v3 = v2;
    v2 = *(char **)v2;
    std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>::~pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>(v3 + 32);
    operator delete(v3);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x140023868  mov     [rsp+arg_0], rbx
0x14002386d  mov     [rsp+arg_8], rsi
0x140023872  push    rdi
0x140023873  sub     rsp, 20h
0x140023877  mov     rax, [rcx]
0x14002387a  mov     rsi, rcx
0x14002387d  mov     rdi, [rax+8]
0x140023881  jmp     short loc_1400238AE
0x140023883  mov     r8, [rdi+10h]
0x140023887  mov     rdx, rsi
0x14002388a  mov     rcx, rsi
0x14002388d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>,void *> *)
0x140023892  mov     rbx, rdi
0x140023895  mov     rdi, [rdi]
0x140023898  lea     rcx, [rbx+20h]
0x14002389c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VEsimProfile@ESIMPM@@U?$default_delete@VEsimProfile@ESIMPM@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>::~pair<std::wstring const,std::unique_ptr<ESIMPM::EsimProfile>>(void)
0x1400238a1  mov     edx, 48h ; 'H'
0x1400238a6  mov     rcx, rbx; Block
0x1400238a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400238ae  cmp     byte ptr [rdi+19h], 0
0x1400238b2  jz      short loc_140023883
0x1400238b4  mov     rcx, [rsi]; Block
0x1400238b7  mov     edx, 48h ; 'H'
0x1400238bc  mov     rbx, [rsp+28h+arg_0]
0x1400238c1  mov     rsi, [rsp+28h+arg_8]
0x1400238c6  add     rsp, 20h
0x1400238ca  pop     rdi
0x1400238cb  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
