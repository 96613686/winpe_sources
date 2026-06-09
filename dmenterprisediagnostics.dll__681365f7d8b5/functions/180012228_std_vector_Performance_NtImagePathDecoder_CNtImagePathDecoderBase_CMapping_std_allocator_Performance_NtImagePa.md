# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180012228`
- end: `0x18001225d`
- name: `??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010348`
- `0x180025cb8`

## callees

- `0x180003618`
- `0x1800100fc`
- `0x180012228`

## pseudocode

```c
__int64 __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)(a1 + 24),
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)(a1 + 32));
    return std::_Deallocate<16>(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16) << 6);
  }
  return result;
}

```

## disassembly

```asm
0x180012228  push    rbx
0x18001222a  sub     rsp, 20h
0x18001222e  cmp     qword ptr [rcx+8], 0
0x180012233  mov     rbx, rcx
0x180012236  jz      short loc_180012256
0x180012238  mov     rdx, [rcx+20h]
0x18001223c  mov     rcx, [rcx+18h]; this
0x180012240  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x180012245  mov     rdx, [rbx+10h]
0x180012249  mov     rcx, [rbx+8]
0x18001224d  shl     rdx, 6
0x180012251  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012256  add     rsp, 20h
0x18001225a  pop     rbx
0x18001225b  retn
```
