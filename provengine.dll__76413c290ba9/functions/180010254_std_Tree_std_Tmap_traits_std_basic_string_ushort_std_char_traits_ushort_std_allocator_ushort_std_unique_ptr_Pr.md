# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ProvResults,std::default_delete<ProvResults>>>>,0>>(void)

- ea: `0x180010254`
- end: `0x180010300`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `172`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800105ac`
- `0x180010d34`

## callees

- `0x180010254`
- `0x180011328`
- `0x1800212f4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010293`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010293`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>(
        void **a1)
{
  __int64 *v2; // rbx
  __int64 *i; // rsi
  void *v4; // rbp

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Erase(
      a1,
      i[2]);
    i = (__int64 *)*i;
    v4 = (void *)v2[8];
    if ( v4 )
    {
      ProvResults::~ProvResults((ProvResults *)v2[8]);
      operator delete(v4);
    }
    if ( (unsigned __int64)v2[7] >= 8 )
      operator delete((void *)v2[4]);
    v2[7] = 7;
    v2[6] = 0;
    *((_WORD *)v2 + 16) = 0;
    operator delete(v2);
  }
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  operator delete(*a1);
}

```

## disassembly

```asm
0x180010254  push    rbx
0x180010256  push    rbp
0x180010257  push    rsi
0x180010258  push    rdi
0x180010259  sub     rsp, 28h
0x18001025d  mov     rdi, rcx
0x180010260  mov     rax, [rcx]
0x180010263  mov     rbx, [rax+8]
0x180010267  mov     rsi, rbx
0x18001026a  cmp     byte ptr [rbx+19h], 0
0x18001026e  jnz     short loc_1800102D2
0x180010270  mov     rdx, [rsi+10h]
0x180010274  mov     rcx, rdi
0x180010277  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<ProvResults>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ProvResults>>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<ProvResults>>,void *> *)
0x18001027c  mov     rsi, [rsi]
0x18001027f  mov     rbp, [rbx+40h]
0x180010283  test    rbp, rbp
0x180010286  jz      short loc_180010299
0x180010288  mov     rcx, rbp; this
0x18001028b  call    ??1ProvResults@@QEAA@XZ; ProvResults::~ProvResults(void)
0x180010290  mov     rcx, rbp
0x180010293  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010299  cmp     qword ptr [rbx+38h], 8
0x18001029e  jb      short loc_1800102AA
0x1800102a0  mov     rcx, [rbx+20h]
0x1800102a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800102aa  mov     qword ptr [rbx+38h], 7
0x1800102b2  mov     qword ptr [rbx+30h], 0
0x1800102ba  xor     eax, eax
0x1800102bc  mov     [rbx+20h], ax
0x1800102c0  mov     rcx, rbx
0x1800102c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800102c9  mov     rbx, rsi
0x1800102cc  cmp     byte ptr [rsi+19h], 0
0x1800102d0  jz      short loc_180010270
0x1800102d2  mov     rax, [rdi]
0x1800102d5  mov     [rax+8], rax
0x1800102d9  mov     rax, [rdi]
0x1800102dc  mov     [rax], rax
0x1800102df  mov     rax, [rdi]
0x1800102e2  mov     [rax+10h], rax
0x1800102e6  mov     qword ptr [rdi+8], 0
0x1800102ee  mov     rcx, [rdi]
0x1800102f1  add     rsp, 28h
0x1800102f5  pop     rdi
0x1800102f6  pop     rsi
0x1800102f7  pop     rbp
0x1800102f8  pop     rbx
0x1800102f9  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
