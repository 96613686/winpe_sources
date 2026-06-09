# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Alloc_sentinel_and_proxy(void)

- ea: `0x180018610`
- end: `0x18001863e`
- name: `?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ`
- size: `46`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800111c0`
- `0x180022170`
- `0x180022c80`

## callees

- `0x18000183c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Alloc_sentinel_and_proxy(
        _QWORD *a1)
{
  _QWORD *result; // rax

  result = operator new(0x30u);
  *result = result;
  result[1] = result;
  result[2] = result;
  *((_WORD *)result + 12) = 257;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180018610  push    rbx
0x180018612  sub     rsp, 20h
0x180018616  mov     rbx, rcx
0x180018619  mov     ecx, 30h ; '0'; Size
0x18001861e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018623  mov     [rax], rax
0x180018626  mov     [rax+8], rax
0x18001862a  mov     [rax+10h], rax
0x18001862e  mov     word ptr [rax+18h], 101h
0x180018634  mov     [rbx], rax
0x180018637  add     rsp, 20h
0x18001863b  pop     rbx
0x18001863c  retn
```
