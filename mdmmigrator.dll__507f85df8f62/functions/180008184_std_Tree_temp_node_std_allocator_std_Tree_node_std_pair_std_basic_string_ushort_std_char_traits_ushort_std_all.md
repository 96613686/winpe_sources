# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *>>>(void)

- ea: `0x180008184`
- end: `0x1800081ca`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001f217`

## callees

- `0x1800026b0`
- `0x180007720`
- `0x180008184`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    std::wstring::~wstring((void *)(v1 + 64));
    std::wstring::~wstring((void *)(v1 + 32));
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3, (const struct std::nothrow_t *)0x60);
}

```

## disassembly

```asm
0x180008184  mov     [rsp+arg_0], rbx
0x180008189  push    rdi
0x18000818a  sub     rsp, 20h
0x18000818e  mov     rbx, [rcx+8]
0x180008192  mov     rdi, rcx
0x180008195  test    rbx, rbx
0x180008198  jz      short loc_1800081AC
0x18000819a  lea     rcx, [rbx+40h]; void *
0x18000819e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800081a3  lea     rcx, [rbx+20h]; void *
0x1800081a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800081ac  mov     rcx, [rdi+8]; void *
0x1800081b0  test    rcx, rcx
0x1800081b3  jz      short loc_1800081BF
0x1800081b5  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x1800081ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800081bf  mov     rbx, [rsp+28h+arg_0]
0x1800081c4  add     rsp, 20h
0x1800081c8  pop     rdi
0x1800081c9  retn
```
