# CSafeSet<_bstr_t>::~CSafeSet<_bstr_t>(void)

- ea: `0x140005db8`
- end: `0x140005e0b`
- name: `??1?$CSafeSet@V_bstr_t@@@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(CReadWriteLock *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f150`
- `0x14001f170`
- `0x14001f190`
- `0x14001f1b0`
- `0x14001f1f0`

## callees

- `0x140006f4c`
- `0x14001c7e4`

## import_xrefs

- `msvcrt!free` at `0x140005de2`
- `msvcrt!free` at `0x140005de2`

## pseudocode

```c
void __fastcall CSafeSet<_bstr_t>::~CSafeSet<_bstr_t>(CReadWriteLock *this)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::erase(
    (char *)this + 24,
    &v2,
    **((_QWORD **)this + 4),
    *((_QWORD *)this + 4));
  free(*((void **)this + 4));
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  CReadWriteLock::~CReadWriteLock(this);
}

```

## disassembly

```asm
0x140005db8  mov     [rsp+arg_8], rbx
0x140005dbd  push    rdi
0x140005dbe  sub     rsp, 20h
0x140005dc2  mov     rdi, rcx
0x140005dc5  mov     r8, [rcx+20h]
0x140005dc9  mov     r9, r8
0x140005dcc  mov     r8, [r8]
0x140005dcf  lea     rdx, [rsp+28h+arg_0]
0x140005dd4  add     rcx, 18h
0x140005dd8  call    ?erase@?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::erase(std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::iterator,std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::iterator)
0x140005ddd  nop
0x140005dde  mov     rcx, [rdi+20h]; Block
0x140005de2  call    cs:__imp_free
0x140005de8  nop
0x140005de9  mov     qword ptr [rdi+20h], 0
0x140005df1  mov     qword ptr [rdi+28h], 0
0x140005df9  mov     rcx, rdi; this
0x140005dfc  mov     rbx, [rsp+28h+arg_8]
0x140005e01  add     rsp, 20h
0x140005e05  pop     rdi
0x140005e06  jmp     ??1CReadWriteLock@@QEAA@XZ; CReadWriteLock::~CReadWriteLock(void)
```
