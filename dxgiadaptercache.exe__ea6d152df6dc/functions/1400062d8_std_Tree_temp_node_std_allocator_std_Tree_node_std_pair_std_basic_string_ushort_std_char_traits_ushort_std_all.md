# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *>>>(void)

- ea: `0x1400062d8`
- end: `0x14000632d`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x140011546`

## callees

- `0x140002578`
- `0x1400062d8`
- `0x140006334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006300`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  HKEY v3; // rcx
  void *v4; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    std::wstring::~wstring(v1 + 104);
    v3 = *(HKEY *)(v1 + 64);
    if ( v3 )
      RegCloseKey(v3);
    std::wstring::~wstring(v1 + 32);
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    operator delete(v4, 0xA8u);
}

```

## disassembly

```asm
0x1400062d8  mov     [rsp+arg_0], rbx
0x1400062dd  push    rdi
0x1400062de  sub     rsp, 20h
0x1400062e2  mov     rbx, [rcx+8]
0x1400062e6  mov     rdi, rcx
0x1400062e9  test    rbx, rbx
0x1400062ec  jz      short loc_14000630F
0x1400062ee  lea     rcx, [rbx+68h]
0x1400062f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400062f7  mov     rcx, [rbx+40h]; hKey
0x1400062fb  test    rcx, rcx
0x1400062fe  jz      short loc_140006306
0x140006300  call    cs:__imp_RegCloseKey
0x140006306  lea     rcx, [rbx+20h]
0x14000630a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000630f  mov     rcx, [rdi+8]; void *
0x140006313  test    rcx, rcx
0x140006316  jz      short loc_140006322
0x140006318  mov     edx, 0A8h; unsigned __int64
0x14000631d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006322  mov     rbx, [rsp+28h+arg_0]
0x140006327  add     rsp, 20h
0x14000632b  pop     rdi
0x14000632c  retn
```
