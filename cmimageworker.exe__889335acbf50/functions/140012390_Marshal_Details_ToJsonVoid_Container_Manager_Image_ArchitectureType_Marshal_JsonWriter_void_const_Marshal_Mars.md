# Marshal::Details::ToJsonVoid<Container::Manager::Image::ArchitectureType,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x140012390`
- end: `0x14001241b`
- name: `??$ToJsonVoid@W4ArchitectureType@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: `char __fastcall(Marshal::Details *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400020b0`
- `0x140012390`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::ArchitectureType,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  _WORD *v3; // rdx
  unsigned __int64 v4; // r8
  _OWORD v6[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 2u )
    Marshal::Details::FailFast(a1);
  v3 = *(_WORD **)(Container::Manager::Image::ArchitectureType_EnumData + 8LL * (unsigned int)*a2);
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
0x140012390  push    rbx
0x140012392  sub     rsp, 50h
0x140012396  mov     rax, cs:__security_cookie
0x14001239d  xor     rax, rsp
0x1400123a0  mov     [rsp+58h+var_10], rax
0x1400123a5  mov     rbx, rcx
0x1400123a8  xor     r9d, r9d
0x1400123ab  cmp     dword ptr [rdx], 2
0x1400123ae  ja      short loc_140012415
0x1400123b0  mov     rcx, cs:?ArchitectureType_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::ArchitectureType_EnumData
0x1400123b7  mov     eax, [rdx]
0x1400123b9  mov     rdx, [rcx+rax*8]
0x1400123bd  xorps   xmm0, xmm0
0x1400123c0  movups  [rsp+58h+var_30], xmm0
0x1400123c5  xorps   xmm1, xmm1
0x1400123c8  movdqu  [rsp+58h+var_20], xmm1
0x1400123ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400123d2  inc     r8
0x1400123d5  cmp     [rdx+r8*2], r9w
0x1400123da  jnz     short loc_1400123D2
0x1400123dc  lea     rcx, [rsp+58h+var_30]
0x1400123e1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400123e6  nop
0x1400123e7  lea     rdx, [rsp+58h+var_30]
0x1400123ec  mov     rcx, rbx
0x1400123ef  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x1400123f4  nop
0x1400123f5  lea     rcx, [rsp+58h+var_30]
0x1400123fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400123ff  mov     al, 1
0x140012401  mov     rcx, [rsp+58h+var_10]
0x140012406  xor     rcx, rsp; StackCookie
0x140012409  call    __security_check_cookie
0x14001240e  add     rsp, 50h
0x140012412  pop     rbx
0x140012413  retn
0x140012415  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
