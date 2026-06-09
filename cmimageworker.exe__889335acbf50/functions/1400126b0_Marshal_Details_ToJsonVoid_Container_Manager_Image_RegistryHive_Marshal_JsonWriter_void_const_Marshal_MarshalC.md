# Marshal::Details::ToJsonVoid<Container::Manager::Image::RegistryHive,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x1400126b0`
- end: `0x14001273b`
- name: `??$ToJsonVoid@W4RegistryHive@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: `char __fastcall(Marshal::Details *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400020b0`
- `0x1400126b0`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::RegistryHive,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  _WORD *v3; // rdx
  unsigned __int64 v4; // r8
  _OWORD v6[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 5u )
    Marshal::Details::FailFast(a1);
  v3 = *(_WORD **)(Container::Manager::Image::RegistryHive_EnumData + 8LL * (unsigned int)*a2);
  memset(v6, 0, sizeof(v6));
  v4 = -1;
  do
    ++v4;
  while ( v3[v4] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v6, v3, v4);
  Marshal::Details::WriteJson<std::wstring>(a1, v6);
  std::wstring::~wstring(v6);
  return 1;
}

```

## disassembly

```asm
0x1400126b0  push    rbx
0x1400126b2  sub     rsp, 50h
0x1400126b6  mov     rax, cs:__security_cookie
0x1400126bd  xor     rax, rsp
0x1400126c0  mov     [rsp+58h+var_10], rax
0x1400126c5  mov     rbx, rcx
0x1400126c8  xor     r9d, r9d
0x1400126cb  cmp     dword ptr [rdx], 5
0x1400126ce  ja      short loc_140012735
0x1400126d0  mov     rcx, cs:?RegistryHive_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::RegistryHive_EnumData
0x1400126d7  mov     eax, [rdx]
0x1400126d9  mov     rdx, [rcx+rax*8]
0x1400126dd  xorps   xmm0, xmm0
0x1400126e0  movups  [rsp+58h+var_30], xmm0
0x1400126e5  xorps   xmm1, xmm1
0x1400126e8  movdqu  [rsp+58h+var_20], xmm1
0x1400126ee  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400126f2  inc     r8
0x1400126f5  cmp     [rdx+r8*2], r9w
0x1400126fa  jnz     short loc_1400126F2
0x1400126fc  lea     rcx, [rsp+58h+var_30]
0x140012701  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140012706  nop
0x140012707  lea     rdx, [rsp+58h+var_30]
0x14001270c  mov     rcx, rbx
0x14001270f  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x140012714  nop
0x140012715  lea     rcx, [rsp+58h+var_30]
0x14001271a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001271f  mov     al, 1
0x140012721  mov     rcx, [rsp+58h+var_10]
0x140012726  xor     rcx, rsp; StackCookie
0x140012729  call    __security_check_cookie
0x14001272e  add     rsp, 50h
0x140012732  pop     rbx
0x140012733  retn
0x140012735  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
