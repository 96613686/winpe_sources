# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<ushort const *>(std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> * const,ushort const * const &)

- ea: `0x1800107cc`
- end: `0x1800107f9`
- name: `??$_Lower_bound_duplicate@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEBQEBG@Z`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010d9c`
- `0x18001896c`

## callees

- `0x1800107cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800107dd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800107dd`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<unsigned short const *>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  return !*(_BYTE *)(a2 + 25) && (int)_o__wcsicmp(*a3, *(_QWORD *)(a2 + 32)) >= 0;
}

```

## disassembly

```asm
0x1800107cc  sub     rsp, 28h
0x1800107d0  cmp     byte ptr [rdx+19h], 0
0x1800107d4  jnz     short loc_1800107F1
0x1800107d6  mov     rdx, [rdx+20h]
0x1800107da  mov     rcx, [r8]
0x1800107dd  call    cs:__imp__o__wcsicmp
0x1800107e4  nop     dword ptr [rax+rax+00h]
0x1800107e9  test    eax, eax
0x1800107eb  js      short loc_1800107F1
0x1800107ed  mov     al, 1
0x1800107ef  jmp     short loc_1800107F3
0x1800107f1  xor     al, al
0x1800107f3  add     rsp, 28h
0x1800107f7  retn
```
