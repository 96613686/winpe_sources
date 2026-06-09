# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180011a94`
- end: `0x180011ac8`
- name: `??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fd0c`
- `0x180024df6`

## callees

- `0x1800035c4`
- `0x18000fa44`
- `0x180011a94`

## pseudocode

```c
void __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
      *(_QWORD *)(a1 + 24),
      *(_QWORD *)(a1 + 32));
    std::_Deallocate<16>(*(void **)(a1 + 8), 32LL * *(_QWORD *)(a1 + 16));
  }
}

```

## disassembly

```asm
0x180011a94  push    rbx
0x180011a96  sub     rsp, 20h
0x180011a9a  cmp     qword ptr [rcx+8], 0
0x180011a9f  mov     rbx, rcx
0x180011aa2  jz      short loc_180011AC2
0x180011aa4  mov     rdx, [rcx+20h]
0x180011aa8  mov     rcx, [rcx+18h]
0x180011aac  call    ??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x180011ab1  mov     rdx, [rbx+10h]
0x180011ab5  mov     rcx, [rbx+8]
0x180011ab9  shl     rdx, 5
0x180011abd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011ac2  add     rsp, 20h
0x180011ac6  pop     rbx
0x180011ac7  retn
```
