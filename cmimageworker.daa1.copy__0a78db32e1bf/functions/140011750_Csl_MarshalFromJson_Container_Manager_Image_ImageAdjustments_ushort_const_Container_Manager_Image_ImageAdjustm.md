# Csl::MarshalFromJson<Container::Manager::Image::ImageAdjustments>(ushort const *,Container::Manager::Image::ImageAdjustments &)

- ea: `0x140011750`
- end: `0x14001189b`
- name: `??$MarshalFromJson@UImageAdjustments@Image@Manager@Container@@@Csl@@YAJPEBGAEAUImageAdjustments@Image@Manager@Container@@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14001694c`

## callees

- `0x1400020b0`
- `0x14000fccc`
- `0x140011750`
- `0x140015838`
- `0x14001ffac`
- `0x14001fff4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::MarshalFromJson<Container::Manager::Image::ImageAdjustments>(__int64 a1)
{
  unsigned __int64 v1; // rdx
  unsigned __int64 v2; // r9
  unsigned __int64 v3; // r8
  bool v4; // cf
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-A8h]
  char v9; // [rsp+28h] [rbp-A0h]
  char v10[32]; // [rsp+30h] [rbp-98h] BYREF
  __int64 v11; // [rsp+50h] [rbp-78h]
  unsigned __int64 v12; // [rsp+58h] [rbp-70h]
  unsigned __int64 v13; // [rsp+60h] [rbp-68h]
  __int64 v14; // [rsp+68h] [rbp-60h]
  __int128 v15; // [rsp+70h] [rbp-58h] BYREF
  __m128i si128; // [rsp+80h] [rbp-48h]
  _OWORD v17[2]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v1 = -1;
  do
    ++v1;
  while ( *(_WORD *)(a1 + 2 * v1) );
  v11 = a1;
  v12 = v1;
  v13 = 0;
  v15 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v15) = 0;
  v17[0] = 0;
  v17[1] = si128;
  LOWORD(v17[0]) = 0;
  v2 = 0;
  v14 = 0;
  while ( 1 )
  {
    v3 = v2;
    v4 = v1 < v2;
    if ( v1 <= v2 )
      break;
    if ( *(_WORD *)(a1 + 2 * v2) != 9
      && *(_WORD *)(a1 + 2 * v2) != 10
      && *(_WORD *)(a1 + 2 * v2) != 13
      && *(_WORD *)(a1 + 2 * v2) != 32 )
    {
      v4 = v1 < v2;
      break;
    }
    ++v2;
  }
  if ( v4 )
    v3 = v1;
  v13 = v3;
  try
  {
    Marshal::FromJson<Container::Manager::Image::ImageAdjustments,>();
    std::wstring::~wstring(v17);
    std::wstring::~wstring(&v15);
    if ( !v9 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslMarshal.h",
        (const char *)0x8007000DLL,
        v8);
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x37, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x140011750  mov     [rsp+arg_0], rbx
0x140011755  push    rdi
0x140011756  sub     rsp, 0C0h
0x14001175d  mov     rax, cs:__security_cookie
0x140011764  xor     rax, rsp
0x140011767  mov     [rsp+0C8h+var_18], rax
0x14001176f  mov     rbx, rdx
0x140011772  mov     r10, rcx
0x140011775  xor     edi, edi
0x140011777  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001177b  inc     rdx
0x14001177e  cmp     [rcx+rdx*2], di
0x140011782  jnz     short loc_14001177B
0x140011784  mov     [rsp+0C8h+var_78], r10
0x140011789  mov     [rsp+0C8h+var_70], rdx
0x14001178e  mov     [rsp+0C8h+var_68], rdi
0x140011793  xorps   xmm0, xmm0
0x140011796  movups  [rsp+0C8h+var_58], xmm0
0x14001179b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400117a3  movdqa  [rsp+0C8h+var_48], xmm1
0x1400117ac  mov     word ptr [rsp+0C8h+var_58], di
0x1400117b1  movups  [rsp+0C8h+var_38], xmm0
0x1400117b9  movdqa  [rsp+0C8h+var_28], xmm1
0x1400117c2  mov     word ptr [rsp+0C8h+var_38], di
0x1400117ca  mov     r9, rdi
0x1400117cd  mov     rax, rdx
0x1400117d0  cmp     rdx, rdi
0x1400117d3  cmovnb  rax, rdi
0x1400117d7  mov     [rsp+0C8h+var_60], rax
0x1400117dc  lea     r8, [r9+rdi]
0x1400117e0  cmp     rdx, r8
0x1400117e3  jbe     short loc_140011806
0x1400117e5  movzx   ecx, word ptr [r10+r8*2]
0x1400117ea  sub     ecx, 9
0x1400117ed  jz      short loc_1400117FE
0x1400117ef  sub     ecx, 1
0x1400117f2  jz      short loc_1400117FE
0x1400117f4  sub     ecx, 3
0x1400117f7  jz      short loc_1400117FE
0x1400117f9  cmp     ecx, 13h
0x1400117fc  jnz     short loc_140011803
0x1400117fe  inc     r9
0x140011801  jmp     short loc_1400117DC
0x140011803  cmp     rdx, r8
0x140011806  cmovb   r8, rdx
0x14001180a  mov     [rsp+0C8h+var_68], r8
0x14001180f  mov     r8, rbx
0x140011812  lea     rdx, [rsp+0C8h+var_78]
0x140011817  lea     rcx, [rsp+0C8h+var_A0]
0x14001181c  call    ??$FromJson@UImageAdjustments@Image@Manager@Container@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUImageAdjustments@Image@Manager@Container@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Container::Manager::Image::ImageAdjustments,>(Marshal::JsonParser &,Container::Manager::Image::ImageAdjustments *,Marshal::UnmarshalFlags)
0x140011821  nop
0x140011822  lea     rcx, [rsp+0C8h+var_38]
0x14001182a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001182f  lea     rcx, [rsp+0C8h+var_58]
0x140011834  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011839  nop
0x14001183a  cmp     [rsp+0C8h+var_A0], dil
0x14001183f  setz    al
0x140011842  mov     rcx, [rsp+0C8h]; this
0x14001184a  test    al, al
0x14001184c  jnz     short loc_140011882
0x14001184e  lea     rcx, [rsp+0C8h+var_98]
0x140011853  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140011858  xor     eax, eax
0x14001185a  jmp     short loc_140011860
0x14001185c  mov     eax, [rsp+0C8h+var_A8]
0x140011860  mov     rcx, [rsp+0C8h+var_18]
0x140011868  xor     rcx, rsp; StackCookie
0x14001186b  call    __security_check_cookie
0x140011870  mov     rbx, [rsp+0C8h+arg_0]
0x140011878  add     rsp, 0C0h
0x14001187f  pop     rdi
0x140011880  retn
0x140011882  mov     r9d, 8007000Dh; char *
0x140011888  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14001188f  mov     edx, 34h ; '4'; void *
0x140011894  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
