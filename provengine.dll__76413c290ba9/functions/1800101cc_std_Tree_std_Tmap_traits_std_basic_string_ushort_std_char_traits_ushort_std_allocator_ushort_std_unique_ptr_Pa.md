# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<PackageContext,std::default_delete<PackageContext>>>>,0>>(void)

- ea: `0x1800101cc`
- end: `0x18001024d`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800105a0`
- `0x1800113a8`

## callees

- `0x1800101cc`
- `0x180010628`
- `0x180021294`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010209`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010209`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010246`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>(
        void **a1)
{
  char *v2; // rdi
  char *i; // rsi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9

  v2 = (char *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !i[25]; v2 = i )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Erase(
      a1,
      *((_QWORD *)i + 2));
    i = *(char **)i;
    std::pair<std::wstring const,std::unique_ptr<PackageContext>>::~pair<std::wstring const,std::unique_ptr<PackageContext>>(
      v2 + 32,
      v4,
      v5,
      v6);
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
0x1800101cc  mov     [rsp+arg_0], rbx
0x1800101d1  mov     [rsp+arg_8], rsi
0x1800101d6  push    rdi
0x1800101d7  sub     rsp, 20h
0x1800101db  mov     rbx, rcx
0x1800101de  mov     rax, [rcx]
0x1800101e1  mov     rdi, [rax+8]
0x1800101e5  mov     rsi, rdi
0x1800101e8  cmp     byte ptr [rdi+19h], 0
0x1800101ec  jnz     short loc_180010218
0x1800101ee  mov     rdx, [rsi+10h]
0x1800101f2  mov     rcx, rbx
0x1800101f5  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PackageContext>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PackageContext>>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::unique_ptr<PackageContext>>,void *> *)
0x1800101fa  mov     rsi, [rsi]
0x1800101fd  lea     rcx, [rdi+20h]
0x180010201  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPackageContext@@U?$default_delete@UPackageContext@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::unique_ptr<PackageContext>>::~pair<std::wstring const,std::unique_ptr<PackageContext>>(void)
0x180010206  mov     rcx, rdi
0x180010209  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001020f  mov     rdi, rsi
0x180010212  cmp     byte ptr [rsi+19h], 0
0x180010216  jz      short loc_1800101EE
0x180010218  mov     rax, [rbx]
0x18001021b  mov     [rax+8], rax
0x18001021f  mov     rax, [rbx]
0x180010222  mov     [rax], rax
0x180010225  mov     rax, [rbx]
0x180010228  mov     [rax+10h], rax
0x18001022c  mov     qword ptr [rbx+8], 0
0x180010234  mov     rcx, [rbx]
0x180010237  mov     rbx, [rsp+28h+arg_0]
0x18001023c  mov     rsi, [rsp+28h+arg_8]
0x180010241  add     rsp, 20h
0x180010245  pop     rdi
0x180010246  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
