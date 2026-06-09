# Marshal::Details::ToJsonVoid<Container::Manager::Image::PackageType,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x140012610`
- end: `0x14001269b`
- name: `??$ToJsonVoid@W4PackageType@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400020b0`
- `0x140012610`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::PackageType,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r8
  _OWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 2u )
    Marshal::Details::FailFast(a1);
  v3 = *(_QWORD *)(Container::Manager::Image::PackageType_EnumData + 8LL * (unsigned int)*a2);
  memset(v7, 0, sizeof(v7));
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  std::wstring::_Construct<1,unsigned short const *>(v7, v3, v4);
  Marshal::Details::WriteJson<std::wstring>((__int64)a1, v7, v5);
  std::wstring::~wstring(v7);
  return 1;
}

```

## disassembly

```asm
0x140012610  push    rbx
0x140012612  sub     rsp, 50h
0x140012616  mov     rax, cs:__security_cookie
0x14001261d  xor     rax, rsp
0x140012620  mov     [rsp+58h+var_10], rax
0x140012625  mov     rbx, rcx
0x140012628  xor     r9d, r9d
0x14001262b  cmp     dword ptr [rdx], 2
0x14001262e  ja      short loc_140012695
0x140012630  mov     rcx, cs:?PackageType_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::PackageType_EnumData
0x140012637  mov     eax, [rdx]
0x140012639  mov     rdx, [rcx+rax*8]
0x14001263d  xorps   xmm0, xmm0
0x140012640  movups  [rsp+58h+var_30], xmm0
0x140012645  xorps   xmm1, xmm1
0x140012648  movdqu  [rsp+58h+var_20], xmm1
0x14001264e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012652  inc     r8
0x140012655  cmp     [rdx+r8*2], r9w
0x14001265a  jnz     short loc_140012652
0x14001265c  lea     rcx, [rsp+58h+var_30]
0x140012661  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140012666  nop
0x140012667  lea     rdx, [rsp+58h+var_30]
0x14001266c  mov     rcx, rbx
0x14001266f  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x140012674  nop
0x140012675  lea     rcx, [rsp+58h+var_30]
0x14001267a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001267f  mov     al, 1
0x140012681  mov     rcx, [rsp+58h+var_10]
0x140012686  xor     rcx, rsp; StackCookie
0x140012689  call    __security_check_cookie
0x14001268e  add     rsp, 50h
0x140012692  pop     rbx
0x140012693  retn
0x140012695  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
