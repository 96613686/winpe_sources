# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180011a58`
- end: `0x180011a8c`
- name: `??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fbc0`
- `0x180024de4`

## callees

- `0x1800035c4`
- `0x18000fa0c`
- `0x180011a58`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)(a1 + 24),
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)(a1 + 32));
    std::_Deallocate<16>(*(void **)(a1 + 8), *(_QWORD *)(a1 + 16) << 6);
  }
}

```

## disassembly

```asm
0x180011a58  push    rbx
0x180011a5a  sub     rsp, 20h
0x180011a5e  cmp     qword ptr [rcx+8], 0
0x180011a63  mov     rbx, rcx
0x180011a66  jz      short loc_180011A86
0x180011a68  mov     rdx, [rcx+20h]
0x180011a6c  mov     rcx, [rcx+18h]; this
0x180011a70  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x180011a75  mov     rdx, [rbx+10h]
0x180011a79  mov     rcx, [rbx+8]
0x180011a7d  shl     rdx, 6
0x180011a81  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011a86  add     rsp, 20h
0x180011a8a  pop     rbx
0x180011a8b  retn
```
