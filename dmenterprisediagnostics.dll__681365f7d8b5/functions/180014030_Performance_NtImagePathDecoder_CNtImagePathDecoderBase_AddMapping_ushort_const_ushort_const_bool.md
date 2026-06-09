# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)

- ea: `0x180014030`
- end: `0x18001410b`
- name: `?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z`
- size: `219`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180015804`
- `0x180016758`

## callees

- `0x180001800`
- `0x180003768`
- `0x180010348`
- `0x180010f2c`
- `0x18001212c`
- `0x180014030`
- `0x180018a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v10; // rdx
  _QWORD v11[2]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v12; // [rsp+30h] [rbp-40h]
  unsigned __int64 v13; // [rsp+38h] [rbp-38h]
  _QWORD v14[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h]
  unsigned __int64 v16; // [rsp+58h] [rbp-18h]

  std::wstring::wstring(v11, a2);
  std::wstring::wstring(v14, a3);
  if ( a4 )
  {
    if ( !v12 )
      goto LABEL_6;
    v8 = v11;
    if ( v13 > 7 )
      v8 = (_QWORD *)v11[0];
    if ( *((_WORD *)v8 + v12 - 1) != 92 )
LABEL_6:
      std::wstring::push_back(v11);
    v7 = v15;
    if ( !v15 )
      goto LABEL_11;
    v9 = v14;
    if ( v16 > 7 )
      v9 = (_QWORD *)v14[0];
    if ( *((_WORD *)v9 + v15 - 1) != 92 )
LABEL_11:
      std::wstring::push_back(v14);
  }
  v10 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*((_QWORD *)this + 1);
  if ( v10 == *((Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping **)this + 2) )
  {
    std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
      (__int64 *)this,
      v10,
      (__int64)v11);
  }
  else
  {
    std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
      v7,
      v10,
      v11);
    *((_QWORD *)this + 1) += 64LL;
  }
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping((Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)v11);
}

```

## disassembly

```asm
0x180014030  mov     [rsp-18h+arg_18], rbx
0x180014035  push    rbp
0x180014036  push    rsi
0x180014037  push    rdi
0x180014038  mov     rbp, rsp
0x18001403b  sub     rsp, 70h
0x18001403f  mov     rax, cs:__security_cookie
0x180014046  xor     rax, rsp
0x180014049  mov     [rbp+var_10], rax
0x18001404d  mov     dil, r9b
0x180014050  mov     rbx, r8
0x180014053  mov     rsi, rcx
0x180014056  lea     rcx, [rbp+var_50]
0x18001405a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001405f  nop
0x180014060  mov     rdx, rbx
0x180014063  lea     rcx, [rbp+var_30]
0x180014067  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001406c  nop
0x18001406d  test    dil, dil
0x180014070  jz      short loc_1800140C2
0x180014072  mov     rcx, [rbp+var_40]
0x180014076  test    rcx, rcx
0x180014079  jz      short loc_180014091
0x18001407b  lea     rax, [rbp+var_50]
0x18001407f  cmp     [rbp+var_38], 7
0x180014084  cmova   rax, [rbp+var_50]
0x180014089  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18001408f  jz      short loc_18001409A
0x180014091  lea     rcx, [rbp+var_50]
0x180014095  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x18001409a  mov     rcx, [rbp+var_20]
0x18001409e  test    rcx, rcx
0x1800140a1  jz      short loc_1800140B9
0x1800140a3  lea     rax, [rbp+var_30]
0x1800140a7  cmp     [rbp+var_18], 7
0x1800140ac  cmova   rax, [rbp+var_30]
0x1800140b1  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800140b7  jz      short loc_1800140C2
0x1800140b9  lea     rcx, [rbp+var_30]
0x1800140bd  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800140c2  mov     rdx, [rsi+8]
0x1800140c6  lea     r8, [rbp+var_50]
0x1800140ca  cmp     rdx, [rsi+10h]
0x1800140ce  jz      short loc_1800140DC
0x1800140d0  call    ??$construct@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@SAXAEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@1@QEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x1800140d5  add     qword ptr [rsi+8], 40h ; '@'
0x1800140da  jmp     short loc_1800140E5
0x1800140dc  mov     rcx, rsi
0x1800140df  call    ??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x1800140e4  nop
0x1800140e5  lea     rcx, [rbp+var_50]; this
0x1800140e9  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x1800140ee  mov     rcx, [rbp+var_10]
0x1800140f2  xor     rcx, rsp; StackCookie
0x1800140f5  call    __security_check_cookie
0x1800140fa  mov     rbx, [rsp+70h+arg_18]
0x180014102  add     rsp, 70h
0x180014106  pop     rdi
0x180014107  pop     rsi
0x180014108  pop     rbp
0x180014109  retn
```
