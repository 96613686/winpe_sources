# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<ProviderContext>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<ProviderContext>>,void *>>>(void)

- ea: `0x140011a10`
- end: `0x140011a9a`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VProviderContext@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `138`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140012c08`

## callees

- `0x1400018d4`
- `0x1400106b4`
- `0x140011a10`
- `0x14001c010`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ProviderContext>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rdi
  volatile signed __int32 *v4; // rbx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = v1 + 32;
    v4 = *(volatile signed __int32 **)(v1 + 72);
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    std::wstring::~wstring(v3);
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5, 0x50u);
}

```

## disassembly

```asm
0x140011a10  mov     [rsp+arg_0], rbx
0x140011a15  mov     [rsp+arg_8], rsi
0x140011a1a  push    rdi
0x140011a1b  sub     rsp, 20h
0x140011a1f  mov     rax, [rcx+8]
0x140011a23  mov     rsi, rcx
0x140011a26  test    rax, rax
0x140011a29  jz      short loc_140011A77
0x140011a2b  lea     rdi, [rax+20h]
0x140011a2f  mov     rbx, [rdi+28h]
0x140011a33  test    rbx, rbx
0x140011a36  jz      short loc_140011A6F
0x140011a38  or      eax, 0FFFFFFFFh
0x140011a3b  lock xadd [rbx+8], eax
0x140011a40  cmp     eax, 1
0x140011a43  jnz     short loc_140011A6F
0x140011a45  mov     rax, [rbx]
0x140011a48  mov     rcx, rbx
0x140011a4b  mov     rax, [rax]
0x140011a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a53  or      eax, 0FFFFFFFFh
0x140011a56  lock xadd [rbx+0Ch], eax
0x140011a5b  cmp     eax, 1
0x140011a5e  jnz     short loc_140011A6F
0x140011a60  mov     rax, [rbx]
0x140011a63  mov     rcx, rbx
0x140011a66  mov     rax, [rax+8]
0x140011a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a6f  mov     rcx, rdi
0x140011a72  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011a77  mov     rcx, [rsi+8]; void *
0x140011a7b  test    rcx, rcx
0x140011a7e  jz      short loc_140011A8A
0x140011a80  mov     edx, 50h ; 'P'; unsigned __int64
0x140011a85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011a8a  mov     rbx, [rsp+28h+arg_0]
0x140011a8f  mov     rsi, [rsp+28h+arg_8]
0x140011a94  add     rsp, 20h
0x140011a98  pop     rdi
0x140011a99  retn
```
