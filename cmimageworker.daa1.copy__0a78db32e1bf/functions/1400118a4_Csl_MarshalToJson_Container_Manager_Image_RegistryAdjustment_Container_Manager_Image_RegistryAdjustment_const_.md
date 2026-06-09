# Csl::MarshalToJson<Container::Manager::Image::RegistryAdjustment>(Container::Manager::Image::RegistryAdjustment const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1400118a4`
- end: `0x140011999`
- name: `??$MarshalToJson@URegistryAdjustment@Image@Manager@Container@@@Csl@@YAJAEBURegistryAdjustment@Image@Manager@Container@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14001b938`

## callees

- `0x1400020b0`
- `0x14000cd84`
- `0x1400118a4`
- `0x140011ffc`
- `0x140015838`
- `0x14001ffac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Csl::MarshalToJson<Container::Manager::Image::RegistryAdjustment>(__int64 a1, __int64 a2)
{
  __int128 *v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 result; // rax
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v8) = 0;
  try
  {
    Marshal::ToJsonValue<Container::Manager::Image::RegistryAdjustment,>();
    if ( si128.m128i_i64[1] <= 7uLL )
    {
      v3 = &v8;
    }
    else
    {
      v3 = (__int128 *)v8;
      if ( !(_QWORD)v8 )
      {
        v4 = 0;
LABEL_8:
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 a2,
                                 v3,
                                 v4) )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslMarshal.h",
            (const char *)0x8007000ELL,
            0);
        std::wstring::~wstring(&v8);
        return 0;
      }
    }
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)v3 + v4) );
    goto LABEL_8;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x68, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1400118a4  mov     r11, rsp
0x1400118a7  mov     [r11+18h], rbx
0x1400118ab  mov     [r11+20h], rsi
0x1400118af  push    rdi
0x1400118b0  sub     rsp, 60h
0x1400118b4  mov     rax, cs:__security_cookie
0x1400118bb  xor     rax, rsp
0x1400118be  mov     [rsp+68h+var_10], rax
0x1400118c3  mov     rdi, rdx
0x1400118c6  xor     esi, esi
0x1400118c8  mov     [rsp+68h+var_44], esi
0x1400118cc  mov     [rsp+68h+var_48], esi; int
0x1400118d0  xorps   xmm0, xmm0
0x1400118d3  movups  [rsp+68h+var_30], xmm0
0x1400118d8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400118e0  movdqu  [rsp+68h+var_20], xmm1
0x1400118e6  mov     word ptr [rsp+68h+var_30], si
0x1400118eb  mov     [rsp+68h+var_44], 1
0x1400118f3  lea     rax, [r11-30h]
0x1400118f7  mov     [r11-40h], rax
0x1400118fb  mov     [rsp+68h+var_38], sil
0x140011900  lea     r8, [r11-48h]
0x140011904  mov     rdx, rcx
0x140011907  lea     rcx, [r11-40h]
0x14001190b  call    ??$ToJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonWriter@0@AEBURegistryAdjustment@Image@Manager@Container@@AEBVMarshalContext@0@@Z; Marshal::ToJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonWriter &,Container::Manager::Image::RegistryAdjustment const &,Marshal::MarshalContext const &)
0x140011910  cmp     qword ptr [rsp+68h+var_20+8], 7
0x140011916  jbe     short loc_140011927
0x140011918  mov     rdx, qword ptr [rsp+68h+var_30]
0x14001191d  test    rdx, rdx
0x140011920  jnz     short loc_14001192C
0x140011922  mov     r8d, esi
0x140011925  jmp     short loc_14001193A
0x140011927  lea     rdx, [rsp+68h+var_30]
0x14001192c  or      r8, 0FFFFFFFFFFFFFFFFh
0x140011930  inc     r8
0x140011933  cmp     [rdx+r8*2], si
0x140011938  jnz     short loc_140011930
0x14001193a  mov     rbx, [rsp+68h]
0x14001193f  mov     rcx, rdi
0x140011942  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140011947  test    al, al
0x140011949  jz      short loc_14001197D
0x14001194b  lea     rcx, [rsp+68h+var_30]
0x140011950  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011955  xor     eax, eax
0x140011957  jmp     short loc_14001195D
0x140011959  mov     eax, [rsp+68h+var_48]
0x14001195d  mov     rcx, [rsp+68h+var_10]
0x140011962  xor     rcx, rsp; StackCookie
0x140011965  call    __security_check_cookie
0x14001196a  lea     r11, [rsp+68h+var_8]
0x14001196f  mov     rbx, [r11+20h]
0x140011973  mov     rsi, [r11+28h]
0x140011977  mov     rsp, r11
0x14001197a  pop     rdi
0x14001197b  retn
0x14001197d  mov     r9d, 8007000Eh; char *
0x140011983  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14001198a  mov     edx, 65h ; 'e'; void *
0x14001198f  mov     rcx, rbx; this
0x140011992  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
