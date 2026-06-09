# CStringTokens::~CStringTokens(void)

- ea: `0x1800157fc`
- end: `0x180015849`
- name: `??1CStringTokens@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(CStringTokens *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000561c`
- `0x180005df4`
- `0x180015850`
- `0x18001eb48`
- `0x18001eb5e`
- `0x18001ec95`

## callees

- `0x180015d40`
- `0x180015db0`

## import_xrefs

- `msvcrt!free` at `0x180015834`
- `msvcrt!free` at `0x180015834`

## pseudocode

```c
void __fastcall CStringTokens::~CStringTokens(CStringTokens *this)
{
  void **v1; // rbx
  char v2; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CStringTokens::`vftable';
  v1 = (void **)((char *)this + 8);
  std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::erase(
    (char *)this + 8,
    &v2,
    **((_QWORD **)this + 2),
    *((_QWORD *)this + 2));
  std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::clear(v1);
  free(v1[1]);
  v1[1] = 0;
}

```

## disassembly

```asm
0x1800157fc  push    rbx
0x1800157fe  sub     rsp, 20h
0x180015802  lea     rax, ??_7CStringTokens@@6B@; const CStringTokens::`vftable'
0x180015809  mov     [rcx], rax
0x18001580c  mov     r8, [rcx+10h]
0x180015810  lea     rbx, [rcx+8]
0x180015814  mov     r9, r8
0x180015817  mov     r8, [r8]
0x18001581a  lea     rdx, [rsp+28h+arg_0]
0x18001581f  mov     rcx, rbx
0x180015822  call    ?erase@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@@std@@QEAA?AViterator@12@V312@0@Z; std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::erase(std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::iterator,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::iterator)
0x180015827  mov     rcx, rbx
0x18001582a  call    ?clear@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@@2@@std@@QEAAXXZ; std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>>::clear(void)
0x18001582f  nop
0x180015830  mov     rcx, [rbx+8]; Block
0x180015834  call    cs:__imp_free
0x18001583a  nop
0x18001583b  mov     qword ptr [rbx+8], 0
0x180015843  add     rsp, 20h
0x180015847  pop     rbx
0x180015848  retn
```
