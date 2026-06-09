# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Alloc_sentinel_and_proxy(void)

- ea: `0x180017bf4`
- end: `0x180017c21`
- name: `?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ`
- size: `45`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010a30`
- `0x180021454`
- `0x180021ee0`

## callees

- `0x18000181c`

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
0x180017bf4  push    rbx
0x180017bf6  sub     rsp, 20h
0x180017bfa  mov     rbx, rcx
0x180017bfd  mov     ecx, 30h ; '0'; Size
0x180017c02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017c07  mov     [rax], rax
0x180017c0a  mov     [rax+8], rax
0x180017c0e  mov     [rax+10h], rax
0x180017c12  mov     word ptr [rax+18h], 101h
0x180017c18  mov     [rbx], rax
0x180017c1b  add     rsp, 20h
0x180017c1f  pop     rbx
0x180017c20  retn
```
