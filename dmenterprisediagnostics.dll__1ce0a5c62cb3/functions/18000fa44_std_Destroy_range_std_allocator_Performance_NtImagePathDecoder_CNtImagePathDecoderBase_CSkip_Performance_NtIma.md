# std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)

- ea: `0x18000fa44`
- end: `0x18000fa75`
- name: `??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fd0c`
- `0x180010760`
- `0x180011988`
- `0x180011a94`

## callees

- `0x180003b10`
- `0x18000fa44`

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
0x18000fa44  cmp     rcx, rdx
0x18000fa47  jz      short locret_18000FA74
0x18000fa49  mov     [rsp+arg_0], rbx
0x18000fa4e  push    rdi
0x18000fa4f  sub     rsp, 20h
0x18000fa53  mov     rdi, rdx
0x18000fa56  mov     rbx, rcx
0x18000fa59  mov     rcx, rbx
0x18000fa5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fa61  add     rbx, 20h ; ' '
0x18000fa65  cmp     rbx, rdi
0x18000fa68  jnz     short loc_18000FA59
0x18000fa6a  mov     rbx, [rsp+28h+arg_0]
0x18000fa6f  add     rsp, 20h
0x18000fa73  pop     rdi
0x18000fa74  retn
```
