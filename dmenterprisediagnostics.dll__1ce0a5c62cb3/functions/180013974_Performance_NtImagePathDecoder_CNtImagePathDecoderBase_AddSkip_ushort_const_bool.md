# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(ushort const *,bool)

- ea: `0x180013974`
- end: `0x180013a11`
- name: `?AddSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG_N@Z`
- size: `157`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014f08`

## callees

- `0x1800017e0`
- `0x180003714`
- `0x180003b10`
- `0x18000fd0c`
- `0x180010988`
- `0x180013974`
- `0x180017fdc`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddSkip(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2)
{
  _QWORD *v3; // rax
  _QWORD v4[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v5; // [rsp+30h] [rbp-28h]
  unsigned __int64 v6; // [rsp+38h] [rbp-20h]

  std::wstring::wstring((__int64)v4, (__int64)a2);
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
  std::wstring::~wstring((__int64)v4);
}

```

## disassembly

```asm
0x180013974  push    rbx
0x180013976  sub     rsp, 50h
0x18001397a  mov     rax, cs:__security_cookie
0x180013981  xor     rax, rsp
0x180013984  mov     [rsp+58h+var_18], rax
0x180013989  mov     rbx, rcx
0x18001398c  lea     rcx, [rsp+58h+var_38]
0x180013991  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013996  nop
0x180013997  mov     rdx, [rsp+58h+var_28]
0x18001399c  test    rdx, rdx
0x18001399f  jz      short loc_1800139BA
0x1800139a1  lea     rax, [rsp+58h+var_38]
0x1800139a6  cmp     [rsp+58h+var_20], 7
0x1800139ac  cmova   rax, [rsp+58h+var_38]
0x1800139b2  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x1800139b8  jz      short loc_1800139C4
0x1800139ba  lea     rcx, [rsp+58h+var_38]
0x1800139bf  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800139c4  mov     rax, [rbx+20h]
0x1800139c8  cmp     rax, [rbx+28h]
0x1800139cc  jz      short loc_1800139E2
0x1800139ce  lea     rdx, [rsp+58h+var_38]
0x1800139d3  mov     rcx, rax
0x1800139d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800139db  add     qword ptr [rbx+20h], 20h ; ' '
0x1800139e0  jmp     short loc_1800139F4
0x1800139e2  lea     r8, [rsp+58h+var_38]
0x1800139e7  mov     rdx, rax
0x1800139ea  lea     rcx, [rbx+18h]
0x1800139ee  call    ??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)
0x1800139f3  nop
0x1800139f4  lea     rcx, [rsp+58h+var_38]
0x1800139f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800139fe  mov     rcx, [rsp+58h+var_18]
0x180013a03  xor     rcx, rsp; StackCookie
0x180013a06  call    __security_check_cookie
0x180013a0b  add     rsp, 50h
0x180013a0f  pop     rbx
0x180013a10  retn
```
