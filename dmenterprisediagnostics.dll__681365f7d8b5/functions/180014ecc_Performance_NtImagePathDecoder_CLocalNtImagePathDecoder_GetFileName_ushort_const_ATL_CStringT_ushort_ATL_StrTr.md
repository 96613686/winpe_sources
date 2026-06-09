# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180014ecc`
- end: `0x180014f0c`
- name: `?GetFileName@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800129cc`
- `0x180016758`

## callees

- `0x180014ecc`
- `0x180014f14`
- `0x180015804`

## pseudocode

```c
char __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::GetFileName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  if ( !*(_BYTE *)(a1 + 112) )
    Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize((Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)a1);
  return Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(a1, a2, a3);
}

```

## disassembly

```asm
0x180014ecc  mov     [rsp+arg_0], rbx
0x180014ed1  mov     [rsp+arg_8], rsi
0x180014ed6  push    rdi
0x180014ed7  sub     rsp, 20h
0x180014edb  cmp     byte ptr [rcx+70h], 0
0x180014edf  mov     rdi, r8
0x180014ee2  mov     rsi, rdx
0x180014ee5  mov     rbx, rcx
0x180014ee8  jnz     short loc_180014EEF
0x180014eea  call    ?Initialize@CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@AEAAXXZ; Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::Initialize(void)
0x180014eef  mov     r8, rdi
0x180014ef2  mov     rdx, rsi
0x180014ef5  mov     rcx, rbx
0x180014ef8  mov     rbx, [rsp+28h+arg_0]
0x180014efd  mov     rsi, [rsp+28h+arg_8]
0x180014f02  add     rsp, 20h
0x180014f06  pop     rdi
0x180014f07  jmp     ?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
```
