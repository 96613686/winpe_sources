# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *>> &,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *> *)

- ea: `0x140004798`
- end: `0x140004807`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@1@@Z`
- size: `111`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x140004798`
- `0x14000625c`

## callees

- `0x140002578`
- `0x140004798`
- `0x140006334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400047da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400047da`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rbx
  _QWORD *v6; // rsi
  HKEY v7; // rcx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    std::wstring::~wstring(v6 + 13);
    v7 = (HKEY)v6[8];
    if ( v7 )
      RegCloseKey(v7);
    std::wstring::~wstring(v6 + 4);
    operator delete(v6, 0xA8u);
  }
}

```

## disassembly

```asm
0x140004798  push    rbx
0x14000479a  push    rbp
0x14000479b  push    rsi
0x14000479c  push    rdi
0x14000479d  push    r14
0x14000479f  sub     rsp, 20h
0x1400047a3  cmp     byte ptr [r8+19h], 0
0x1400047a8  mov     rbx, r8
0x1400047ab  mov     rbp, rdx
0x1400047ae  mov     r14, rcx
0x1400047b1  jnz     short loc_1400047FC
0x1400047b3  mov     r8, [rbx+10h]
0x1400047b7  mov     rdx, rbp
0x1400047ba  mov     rcx, r14
0x1400047bd  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *> *)
0x1400047c2  mov     rsi, rbx
0x1400047c5  mov     rbx, [rbx]
0x1400047c8  lea     rcx, [rsi+68h]
0x1400047cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400047d1  mov     rcx, [rsi+40h]; hKey
0x1400047d5  test    rcx, rcx
0x1400047d8  jz      short loc_1400047E0
0x1400047da  call    cs:__imp_RegCloseKey
0x1400047e0  lea     rcx, [rsi+20h]
0x1400047e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400047e9  mov     edx, 0A8h; unsigned __int64
0x1400047ee  mov     rcx, rsi; void *
0x1400047f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400047f6  cmp     byte ptr [rbx+19h], 0
0x1400047fa  jz      short loc_1400047B3
0x1400047fc  add     rsp, 20h
0x140004800  pop     r14
0x140004802  pop     rdi
0x140004803  pop     rsi
0x140004804  pop     rbp
0x140004805  pop     rbx
0x140004806  retn
```
