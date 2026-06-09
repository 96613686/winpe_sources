# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CLockTable::CSP_LOCK_ENTRY>(void)

- ea: `0x18000fb94`
- end: `0x18000fbfc`
- name: `??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCSP_LOCK_ENTRY@CLockTable@@@std@@QEAA@XZ`
- size: `104`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f528`
- `0x18000f634`
- `0x18000fa4c`
- `0x18000fcfc`
- `0x180011ec5`

## callees

- `0x180001d14`
- `0x18000f4cc`
- `0x18000fb28`
- `0x18000fb94`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>::~pair<std::wstring const,CLockTable::CSP_LOCK_ENTRY>(
        __int64 a1)
{
  void **v1; // rdi
  _QWORD *v3; // rbx
  void *v4; // rcx

  v1 = (void **)(a1 + 48);
  v3 = *(_QWORD **)(*(_QWORD *)(a1 + 48) + 8LL);
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
      (__int64)v1,
      (__int64)v1,
      v3[2]);
    v4 = v3;
    v3 = (_QWORD *)*v3;
    operator delete(v4);
  }
  operator delete(*v1);
  return std::wstring::~wstring((char **)a1);
}

```

## disassembly

```asm
0x18000fb94  mov     [rsp+arg_0], rbx
0x18000fb99  mov     [rsp+arg_8], rsi
0x18000fb9e  push    rdi
0x18000fb9f  sub     rsp, 20h
0x18000fba3  lea     rdi, [rcx+30h]
0x18000fba7  mov     rsi, rcx
0x18000fbaa  mov     rax, [rdi]
0x18000fbad  mov     rbx, [rax+8]
0x18000fbb1  jmp     short loc_18000FBD2
0x18000fbb3  mov     r8, [rbx+10h]
0x18000fbb7  mov     rdx, rdi
0x18000fbba  mov     rcx, rdi
0x18000fbbd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x18000fbc2  mov     rcx, rbx; Block
0x18000fbc5  mov     edx, 20h ; ' '
0x18000fbca  mov     rbx, [rbx]
0x18000fbcd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fbd2  cmp     byte ptr [rbx+19h], 0
0x18000fbd6  jz      short loc_18000FBB3
0x18000fbd8  mov     rcx, [rdi]; Block
0x18000fbdb  mov     edx, 20h ; ' '
0x18000fbe0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fbe5  mov     rcx, rsi
0x18000fbe8  mov     rbx, [rsp+28h+arg_0]
0x18000fbed  mov     rsi, [rsp+28h+arg_8]
0x18000fbf2  add     rsp, 20h
0x18000fbf6  pop     rdi
0x18000fbf7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
