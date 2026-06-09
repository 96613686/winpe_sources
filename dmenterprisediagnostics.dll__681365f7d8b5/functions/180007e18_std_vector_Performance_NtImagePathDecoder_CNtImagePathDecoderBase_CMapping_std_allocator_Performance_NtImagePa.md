# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x180007e18`
- end: `0x180007e29`
- name: `??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `17`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800081e4`
- `0x18001135c`
- `0x180011560`
- `0x180011b64`
- `0x180018eb4`

## pseudocode

```c
_QWORD *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(
        _QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x180007e18  xor     eax, eax
0x180007e1a  mov     [rcx], rax
0x180007e1d  mov     [rcx+8], rax
0x180007e21  mov     [rcx+10h], rax
0x180007e25  mov     rax, rcx
0x180007e28  retn
```
