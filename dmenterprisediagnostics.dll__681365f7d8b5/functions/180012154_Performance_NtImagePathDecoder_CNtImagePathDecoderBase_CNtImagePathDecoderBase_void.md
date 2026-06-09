# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)

- ea: `0x180012154`
- end: `0x1800121ef`
- name: `??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180011ff4`
- `0x180012120`
- `0x18001b51c`
- `0x18001b77c`
- `0x18002626b`

## callees

- `0x180003618`
- `0x180003b14`
- `0x1800100fc`
- `0x180010134`
- `0x180012154`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this)
{
  __int64 v2; // rcx

  std::wstring::~wstring((char *)this + 80);
  std::wstring::~wstring((char *)this + 48);
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(
      v2,
      *((_QWORD *)this + 4));
    std::_Deallocate<16>(*((_QWORD *)this + 3), (*((_QWORD *)this + 5) - *((_QWORD *)this + 3)) & 0xFFFFFFFFFFFFFFE0uLL);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  if ( *(_QWORD *)this )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(*(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this);
    std::_Deallocate<16>(*(_QWORD *)this, (*((_QWORD *)this + 2) - *(_QWORD *)this) & 0xFFFFFFFFFFFFFFC0uLL);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180012154  push    rbx
0x180012156  sub     rsp, 20h
0x18001215a  mov     rbx, rcx
0x18001215d  add     rcx, 50h ; 'P'
0x180012161  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012166  lea     rcx, [rbx+30h]
0x18001216a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001216f  mov     rcx, [rbx+18h]
0x180012173  test    rcx, rcx
0x180012176  jz      short loc_1800121AD
0x180012178  mov     rdx, [rbx+20h]
0x18001217c  call    ??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x180012181  mov     rcx, [rbx+18h]
0x180012185  mov     rdx, [rbx+28h]
0x180012189  sub     rdx, rcx
0x18001218c  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180012190  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012195  mov     qword ptr [rbx+18h], 0
0x18001219d  mov     qword ptr [rbx+20h], 0
0x1800121a5  mov     qword ptr [rbx+28h], 0
0x1800121ad  mov     rcx, [rbx]; this
0x1800121b0  test    rcx, rcx
0x1800121b3  jz      short loc_1800121E8
0x1800121b5  mov     rdx, [rbx+8]
0x1800121b9  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x1800121be  mov     rdx, [rbx+10h]
0x1800121c2  sub     rdx, [rbx]
0x1800121c5  mov     rcx, [rbx]
0x1800121c8  and     rdx, 0FFFFFFFFFFFFFFC0h
0x1800121cc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800121d1  mov     qword ptr [rbx], 0
0x1800121d8  mov     qword ptr [rbx+8], 0
0x1800121e0  mov     qword ptr [rbx+10h], 0
0x1800121e8  add     rsp, 20h
0x1800121ec  pop     rbx
0x1800121ed  retn
```
