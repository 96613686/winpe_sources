# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>,0>>(void)

- ea: `0x14000625c`
- end: `0x1400062cf`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x14000651c`
- `0x1400066ac`
- `0x14000e174`

## callees

- `0x140002578`
- `0x140004798`
- `0x14000625c`
- `0x140006334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006298`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>(
        void **a1)
{
  __int64 *v2; // rbx
  _QWORD *v3; // rbp
  HKEY v4; // rcx

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      (__int64 *)v2[2]);
    v3 = v2;
    v2 = (__int64 *)*v2;
    std::wstring::~wstring(v3 + 13);
    v4 = (HKEY)v3[8];
    if ( v4 )
      RegCloseKey(v4);
    std::wstring::~wstring(v3 + 4);
    operator delete(v3, 0xA8u);
  }
  operator delete(*a1, 0xA8u);
}

```

## disassembly

```asm
0x14000625c  push    rbx
0x14000625e  push    rbp
0x14000625f  push    rsi
0x140006260  push    rdi
0x140006261  sub     rsp, 28h
0x140006265  mov     rax, [rcx]
0x140006268  mov     rdi, rcx
0x14000626b  mov     rbx, [rax+8]
0x14000626f  jmp     short loc_1400062B4
0x140006271  mov     r8, [rbx+10h]
0x140006275  mov     rdx, rdi
0x140006278  mov     rcx, rdi
0x14000627b  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *> *)
0x140006280  mov     rbp, rbx
0x140006283  mov     rbx, [rbx]
0x140006286  lea     rcx, [rbp+68h]
0x14000628a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000628f  mov     rcx, [rbp+40h]; hKey
0x140006293  test    rcx, rcx
0x140006296  jz      short loc_14000629E
0x140006298  call    cs:__imp_RegCloseKey
0x14000629e  lea     rcx, [rbp+20h]
0x1400062a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400062a7  mov     edx, 0A8h; unsigned __int64
0x1400062ac  mov     rcx, rbp; void *
0x1400062af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400062b4  cmp     byte ptr [rbx+19h], 0
0x1400062b8  jz      short loc_140006271
0x1400062ba  mov     rcx, [rdi]; void *
0x1400062bd  mov     edx, 0A8h; unsigned __int64
0x1400062c2  add     rsp, 28h
0x1400062c6  pop     rdi
0x1400062c7  pop     rsi
0x1400062c8  pop     rbp
0x1400062c9  pop     rbx
0x1400062ca  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
