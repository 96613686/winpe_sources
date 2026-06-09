# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(void)

- ea: `0x180007ab0`
- end: `0x180007ac1`
- name: `??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ`
- size: `17`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180007e58`
- `0x180010bc8`
- `0x180010dc8`
- `0x1800113b4`
- `0x1800185b0`

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
0x180007ab0  xor     eax, eax
0x180007ab2  mov     [rcx], rax
0x180007ab5  mov     [rcx+8], rax
0x180007ab9  mov     [rcx+10h], rax
0x180007abd  mov     rax, rcx
0x180007ac0  retn
```
