# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)

- ea: `0x180014168`
- end: `0x180014206`
- name: `?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z`
- size: `158`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015804`

## callees

- `0x180001800`
- `0x180003768`
- `0x180003b14`
- `0x180010494`
- `0x180011118`
- `0x180014168`
- `0x180018a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2)
{
  _QWORD *v3; // rax
  _QWORD v4[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v5; // [rsp+30h] [rbp-28h]
  unsigned __int64 v6; // [rsp+38h] [rbp-20h]

  std::wstring::wstring(v4, a2);
  if ( !v5 )
    goto LABEL_5;
  v3 = v4;
  if ( v6 > 7 )
    v3 = (_QWORD *)v4[0];
  if ( *((_WORD *)v3 + v5 - 1) != 92 )
LABEL_5:
    std::wstring::push_back(v4);
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(
      (__int64 *)this + 3,
      *((_QWORD *)this + 4),
      (__int64)v4);
  }
  else
  {
    std::wstring::wstring(*((_QWORD *)this + 4), v4);
    *((_QWORD *)this + 4) += 32LL;
  }
  std::wstring::~wstring(v4);
}

```

## disassembly

```asm
0x180014168  push    rbx
0x18001416a  sub     rsp, 50h
0x18001416e  mov     rax, cs:__security_cookie
0x180014175  xor     rax, rsp
0x180014178  mov     [rsp+58h+var_18], rax
0x18001417d  mov     rbx, rcx
0x180014180  lea     rcx, [rsp+58h+var_38]
0x180014185  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001418a  nop
0x18001418b  mov     rdx, [rsp+58h+var_28]
0x180014190  test    rdx, rdx
0x180014193  jz      short loc_1800141AE
0x180014195  lea     rax, [rsp+58h+var_38]
0x18001419a  cmp     [rsp+58h+var_20], 7
0x1800141a0  cmova   rax, [rsp+58h+var_38]
0x1800141a6  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1800141ac  jz      short loc_1800141B8
0x1800141ae  lea     rcx, [rsp+58h+var_38]
0x1800141b3  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800141b8  mov     rax, [rbx+20h]
0x1800141bc  cmp     rax, [rbx+28h]
0x1800141c0  jz      short loc_1800141D6
0x1800141c2  lea     rdx, [rsp+58h+var_38]
0x1800141c7  mov     rcx, rax
0x1800141ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800141cf  add     qword ptr [rbx+20h], 20h ; ' '
0x1800141d4  jmp     short loc_1800141E8
0x1800141d6  lea     r8, [rsp+58h+var_38]
0x1800141db  mov     rdx, rax
0x1800141de  lea     rcx, [rbx+18h]
0x1800141e2  call    ??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)
0x1800141e7  nop
0x1800141e8  lea     rcx, [rsp+58h+var_38]
0x1800141ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800141f2  mov     rcx, [rsp+58h+var_18]
0x1800141f7  xor     rcx, rsp; StackCookie
0x1800141fa  call    __security_check_cookie
0x1800141ff  add     rsp, 50h
0x180014203  pop     rbx
0x180014204  retn
```
