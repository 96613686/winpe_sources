# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>>)

- ea: `0x140004f00`
- end: `0x140004f9c`
- name: `??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@@1@V21@@Z`
- size: `156`
- prototype: `__int64 **__fastcall(__int64, __int64 **, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x14000893c`
- `0x14000e174`

## callees

- `0x140002578`
- `0x140004f00`
- `0x140006334`
- `0x14000fc78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004f70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004f70`

## pseudocode

```c
__int64 **__fastcall std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>>,0>(
        __int64 a1,
        __int64 **a2,
        __int64 *a3)
{
  __int64 *v3; // rbx
  __int64 *v6; // rax
  __int64 *v7; // rcx
  _QWORD *v8; // rsi
  HKEY v9; // rcx
  __int64 **result; // rax

  v3 = (__int64 *)a3[2];
  if ( *((_BYTE *)v3 + 25) )
  {
    v3 = (__int64 *)a3[1];
    v6 = a3;
    while ( !*((_BYTE *)v3 + 25) && v6 == (__int64 *)v3[2] )
    {
      v6 = v3;
      v3 = (__int64 *)v3[1];
    }
  }
  else
  {
    v7 = (__int64 *)*v3;
    if ( !*(_BYTE *)(*v3 + 25) )
    {
      do
      {
        v3 = v7;
        v7 = (__int64 *)*v7;
      }
      while ( !*((_BYTE *)v7 + 25) );
    }
  }
  v8 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Extract(
                   a1,
                   a3);
  std::wstring::~wstring(v8 + 13);
  v9 = (HKEY)v8[8];
  if ( v9 )
    RegCloseKey(v9);
  std::wstring::~wstring(v8 + 4);
  operator delete(v8, 0xA8u);
  result = a2;
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x140004f00  push    rbx
0x140004f02  push    rsi
0x140004f03  push    rdi
0x140004f04  push    r14
0x140004f06  sub     rsp, 28h
0x140004f0a  mov     rbx, [r8+10h]
0x140004f0e  mov     r14, rdx
0x140004f11  mov     r9, rcx
0x140004f14  cmp     byte ptr [rbx+19h], 0
0x140004f18  jz      short loc_140004F38
0x140004f1a  mov     rbx, [r8+8]
0x140004f1e  mov     rax, r8
0x140004f21  jmp     short loc_140004F30
0x140004f23  cmp     rax, [rbx+10h]
0x140004f27  jnz     short loc_140004F50
0x140004f29  mov     rax, rbx
0x140004f2c  mov     rbx, [rbx+8]
0x140004f30  cmp     byte ptr [rbx+19h], 0
0x140004f34  jz      short loc_140004F23
0x140004f36  jmp     short loc_140004F50
0x140004f38  mov     rcx, [rbx]
0x140004f3b  cmp     byte ptr [rcx+19h], 0
0x140004f3f  jnz     short loc_140004F50
0x140004f41  mov     rax, [rcx]
0x140004f44  mov     rbx, rcx
0x140004f47  mov     rcx, rax
0x140004f4a  cmp     byte ptr [rax+19h], 0
0x140004f4e  jz      short loc_140004F41
0x140004f50  mov     rdx, r8
0x140004f53  mov     rcx, r9
0x140004f56  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>,std::_Iterator_base0>)
0x140004f5b  mov     rsi, rax
0x140004f5e  lea     rcx, [rax+68h]
0x140004f62  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004f67  mov     rcx, [rsi+40h]; hKey
0x140004f6b  test    rcx, rcx
0x140004f6e  jz      short loc_140004F76
0x140004f70  call    cs:__imp_RegCloseKey
0x140004f76  lea     rcx, [rsi+20h]
0x140004f7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004f7f  mov     edx, 0A8h; unsigned __int64
0x140004f84  mov     rcx, rsi; void *
0x140004f87  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004f8c  mov     rax, r14
0x140004f8f  mov     [r14], rbx
0x140004f92  add     rsp, 28h
0x140004f96  pop     r14
0x140004f98  pop     rdi
0x140004f99  pop     rsi
0x140004f9a  pop     rbx
0x140004f9b  retn
```
