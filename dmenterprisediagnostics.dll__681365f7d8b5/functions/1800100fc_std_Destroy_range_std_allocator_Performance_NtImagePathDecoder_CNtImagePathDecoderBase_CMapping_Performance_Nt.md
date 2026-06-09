# std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)

- ea: `0x1800100fc`
- end: `0x18001012e`
- name: `??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z`
- size: `50`
- prototype: `__int64 __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180010348`
- `0x180010e94`
- `0x180012154`
- `0x180012228`
- `0x180015804`

## callees

- `0x1800100fc`
- `0x18001212c`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *this,
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *a2)
{
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v3; // rbx

  if ( this != a2 )
  {
    v3 = this;
    do
    {
      Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(v3);
      v3 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)((char *)v3 + 64);
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x1800100fc  cmp     rcx, rdx
0x1800100ff  jz      short locret_18001012C
0x180010101  mov     [rsp+arg_0], rbx
0x180010106  push    rdi
0x180010107  sub     rsp, 20h
0x18001010b  mov     rdi, rdx
0x18001010e  mov     rbx, rcx
0x180010111  mov     rcx, rbx; this
0x180010114  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x180010119  add     rbx, 40h ; '@'
0x18001011d  cmp     rbx, rdi
0x180010120  jnz     short loc_180010111
0x180010122  mov     rbx, [rsp+28h+arg_0]
0x180010127  add     rsp, 20h
0x18001012b  pop     rdi
0x18001012c  retn
```
