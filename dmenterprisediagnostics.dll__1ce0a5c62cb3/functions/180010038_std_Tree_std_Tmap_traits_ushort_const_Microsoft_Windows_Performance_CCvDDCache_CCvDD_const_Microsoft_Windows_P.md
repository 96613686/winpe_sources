# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Lower_bound_duplicate<ushort const *>(std::_Tree_node<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,void *> * const,ushort const * const &)

- ea: `0x180010038`
- end: `0x18001005e`
- name: `??$_Lower_bound_duplicate@PEBG@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@PEAX@1@AEBQEBG@Z`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010610`
- `0x180017f24`

## callees

- `0x180010038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010049`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010049`

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
0x180010038  sub     rsp, 28h
0x18001003c  cmp     byte ptr [rdx+19h], 0
0x180010040  jnz     short loc_180010057
0x180010042  mov     rdx, [rdx+20h]
0x180010046  mov     rcx, [r8]
0x180010049  call    cs:__imp__o__wcsicmp
0x18001004f  test    eax, eax
0x180010051  js      short loc_180010057
0x180010053  mov     al, 1
0x180010055  jmp     short loc_180010059
0x180010057  xor     al, al
0x180010059  add     rsp, 28h
0x18001005d  retn
```
