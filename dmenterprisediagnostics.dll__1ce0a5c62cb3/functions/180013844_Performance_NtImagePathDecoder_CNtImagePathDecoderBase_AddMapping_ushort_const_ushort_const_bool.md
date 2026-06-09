# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::AddMapping(ushort const *,ushort const *,bool)

- ea: `0x180013844`
- end: `0x18001391e`
- name: `?AddMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@IEAAXPEBG0_N@Z`
- size: `218`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase *this, const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180014f08`
- `0x180015d78`

## callees

- `0x1800017e0`
- `0x180003714`
- `0x18000fbc0`
- `0x1800107a4`
- `0x180011960`
- `0x180013844`
- `0x180017fdc`

## pseudocode

```c
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

  std::wstring::wstring((__int64)v11, (__int64)a2);
  std::wstring::wstring((__int64)v14, (__int64)a3);
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
      (__int64)v10,
      (__int64)v11);
    *((_QWORD *)this + 1) += 64LL;
  }
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping((Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)v11);
}

```

## disassembly

```asm
0x180013844  mov     [rsp-18h+arg_18], rbx
0x180013849  push    rbp
0x18001384a  push    rsi
0x18001384b  push    rdi
0x18001384c  mov     rbp, rsp
0x18001384f  sub     rsp, 70h
0x180013853  mov     rax, cs:__security_cookie
0x18001385a  xor     rax, rsp
0x18001385d  mov     [rbp+var_10], rax
0x180013861  mov     dil, r9b
0x180013864  mov     rbx, r8
0x180013867  mov     rsi, rcx
0x18001386a  lea     rcx, [rbp+var_50]
0x18001386e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013873  nop
0x180013874  mov     rdx, rbx
0x180013877  lea     rcx, [rbp+var_30]
0x18001387b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180013880  nop
0x180013881  test    dil, dil
0x180013884  jz      short loc_1800138D6
0x180013886  mov     rcx, [rbp+var_40]
0x18001388a  test    rcx, rcx
0x18001388d  jz      short loc_1800138A5
0x18001388f  lea     rax, [rbp+var_50]
0x180013893  cmp     [rbp+var_38], 7
0x180013898  cmova   rax, [rbp+var_50]
0x18001389d  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800138a3  jz      short loc_1800138AE
0x1800138a5  lea     rcx, [rbp+var_50]
0x1800138a9  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800138ae  mov     rcx, [rbp+var_20]
0x1800138b2  test    rcx, rcx
0x1800138b5  jz      short loc_1800138CD
0x1800138b7  lea     rax, [rbp+var_30]
0x1800138bb  cmp     [rbp+var_18], 7
0x1800138c0  cmova   rax, [rbp+var_30]
0x1800138c5  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800138cb  jz      short loc_1800138D6
0x1800138cd  lea     rcx, [rbp+var_30]
0x1800138d1  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800138d6  mov     rdx, [rsi+8]
0x1800138da  lea     r8, [rbp+var_50]
0x1800138de  cmp     rdx, [rsi+10h]
0x1800138e2  jz      short loc_1800138F0
0x1800138e4  call    ??$construct@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@SAXAEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@1@QEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x1800138e9  add     qword ptr [rsi+8], 40h ; '@'
0x1800138ee  jmp     short loc_1800138F9
0x1800138f0  mov     rcx, rsi
0x1800138f3  call    ??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x1800138f8  nop
0x1800138f9  lea     rcx, [rbp+var_50]; this
0x1800138fd  call    ??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)
0x180013902  mov     rcx, [rbp+var_10]
0x180013906  xor     rcx, rsp; StackCookie
0x180013909  call    __security_check_cookie
0x18001390e  mov     rbx, [rsp+70h+arg_18]
0x180013916  add     rsp, 70h
0x18001391a  pop     rdi
0x18001391b  pop     rsi
0x18001391c  pop     rbp
0x18001391d  retn
```
