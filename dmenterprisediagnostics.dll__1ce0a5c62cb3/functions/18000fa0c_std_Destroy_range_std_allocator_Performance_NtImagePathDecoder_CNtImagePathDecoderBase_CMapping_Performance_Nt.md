# std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)

- ea: `0x18000fa0c`
- end: `0x18000fa3d`
- name: `??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z`
- size: `49`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *this, Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fbc0`
- `0x18001070c`
- `0x180011988`
- `0x180011a58`
- `0x180014f08`

## callees

- `0x18000fa0c`
- `0x180011960`

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
0x18000fa0c  cmp     rcx, rdx
0x18000fa0f  jz      short locret_18000FA3C
0x18000fa11  mov     [rsp+arg_0], rbx
0x18000fa16  push    rdi
0x18000fa17  sub     rsp, 20h
0x18000fa1b  mov     rdi, rdx
0x18000fa1e  mov     rbx, rcx
0x18000fa21  mov     rcx, rbx; this
0x18000fa24  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x18000fa29  add     rbx, 40h ; '@'
0x18000fa2d  cmp     rbx, rdi
0x18000fa30  jnz     short loc_18000FA21
0x18000fa32  mov     rbx, [rsp+28h+arg_0]
0x18000fa37  add     rsp, 20h
0x18000fa3b  pop     rdi
0x18000fa3c  retn
```
