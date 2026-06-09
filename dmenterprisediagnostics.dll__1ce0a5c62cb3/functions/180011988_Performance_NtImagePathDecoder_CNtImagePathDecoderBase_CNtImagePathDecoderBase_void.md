# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)

- ea: `0x180011988`
- end: `0x180011a22`
- name: `??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001182c`
- `0x180011954`
- `0x18001aa68`
- `0x18001accc`
- `0x18002538e`

## callees

- `0x1800035c4`
- `0x180003b10`
- `0x18000fa0c`
- `0x18000fa44`
- `0x180011988`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this)
{
  __int64 v2; // rcx

  std::wstring::~wstring((__int64)this + 80);
  std::wstring::~wstring((__int64)this + 48);
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
      v2,
      *((_QWORD *)this + 4));
    std::_Deallocate<16>(*((void **)this + 3), (*((_QWORD *)this + 5) - *((_QWORD *)this + 3)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  if ( *(_QWORD *)this )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      *(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this,
      *((Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this + 1));
    std::_Deallocate<16>(*(void **)this, (*((_QWORD *)this + 2) - *(_QWORD *)this) & 0xFFFFFFFFFFFFFFC0uLL);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180011988  push    rbx
0x18001198a  sub     rsp, 20h
0x18001198e  mov     rbx, rcx
0x180011991  add     rcx, 50h ; 'P'
0x180011995  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001199a  lea     rcx, [rbx+30h]
0x18001199e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800119a3  mov     rcx, [rbx+18h]
0x1800119a7  test    rcx, rcx
0x1800119aa  jz      short loc_1800119E1
0x1800119ac  mov     rdx, [rbx+20h]
0x1800119b0  call    ??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x1800119b5  mov     rcx, [rbx+18h]
0x1800119b9  mov     rdx, [rbx+28h]
0x1800119bd  sub     rdx, rcx
0x1800119c0  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800119c4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800119c9  mov     qword ptr [rbx+18h], 0
0x1800119d1  mov     qword ptr [rbx+20h], 0
0x1800119d9  mov     qword ptr [rbx+28h], 0
0x1800119e1  mov     rcx, [rbx]; this
0x1800119e4  test    rcx, rcx
0x1800119e7  jz      short loc_180011A1C
0x1800119e9  mov     rdx, [rbx+8]
0x1800119ed  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x1800119f2  mov     rdx, [rbx+10h]
0x1800119f6  sub     rdx, [rbx]
0x1800119f9  mov     rcx, [rbx]
0x1800119fc  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180011a00  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011a05  mov     qword ptr [rbx], 0
0x180011a0c  mov     qword ptr [rbx+8], 0
0x180011a14  mov     qword ptr [rbx+10h], 0
0x180011a1c  add     rsp, 20h
0x180011a20  pop     rbx
0x180011a21  retn
```
