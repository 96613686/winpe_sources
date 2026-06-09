# std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)

- ea: `0x180010134`
- end: `0x180010166`
- name: `??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z`
- size: `50`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180010494`
- `0x180010ee8`
- `0x180012154`
- `0x180012264`

## callees

- `0x180003b14`
- `0x180010134`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::wstring::~wstring(v3);
      v3 += 32;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180010134  cmp     rcx, rdx
0x180010137  jz      short locret_180010164
0x180010139  mov     [rsp+arg_0], rbx
0x18001013e  push    rdi
0x18001013f  sub     rsp, 20h
0x180010143  mov     rdi, rdx
0x180010146  mov     rbx, rcx
0x180010149  mov     rcx, rbx
0x18001014c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010151  add     rbx, 20h ; ' '
0x180010155  cmp     rbx, rdi
0x180010158  jnz     short loc_180010149
0x18001015a  mov     rbx, [rsp+28h+arg_0]
0x18001015f  add     rsp, 20h
0x180010163  pop     rdi
0x180010164  retn
```
