# Marshal::Details::ToJsonVoid<Container::Manager::Image::CommandType,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x140012430`
- end: `0x1400124bb`
- name: `??$ToJsonVoid@W4CommandType@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: `char __fastcall(Marshal::Details *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400020b0`
- `0x140012430`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::CommandType,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  _WORD *v3; // rdx
  unsigned __int64 v4; // r8
  _OWORD v6[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 1u )
    Marshal::Details::FailFast(a1);
  v3 = *(_WORD **)(Container::Manager::Image::CommandType_EnumData + 8LL * (unsigned int)*a2);
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
0x140012430  push    rbx
0x140012432  sub     rsp, 50h
0x140012436  mov     rax, cs:__security_cookie
0x14001243d  xor     rax, rsp
0x140012440  mov     [rsp+58h+var_10], rax
0x140012445  mov     rbx, rcx
0x140012448  xor     r9d, r9d
0x14001244b  cmp     dword ptr [rdx], 1
0x14001244e  ja      short loc_1400124B5
0x140012450  mov     rcx, cs:?CommandType_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::CommandType_EnumData
0x140012457  mov     eax, [rdx]
0x140012459  mov     rdx, [rcx+rax*8]
0x14001245d  xorps   xmm0, xmm0
0x140012460  movups  [rsp+58h+var_30], xmm0
0x140012465  xorps   xmm1, xmm1
0x140012468  movdqu  [rsp+58h+var_20], xmm1
0x14001246e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012472  inc     r8
0x140012475  cmp     [rdx+r8*2], r9w
0x14001247a  jnz     short loc_140012472
0x14001247c  lea     rcx, [rsp+58h+var_30]
0x140012481  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140012486  nop
0x140012487  lea     rdx, [rsp+58h+var_30]
0x14001248c  mov     rcx, rbx
0x14001248f  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x140012494  nop
0x140012495  lea     rcx, [rsp+58h+var_30]
0x14001249a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001249f  mov     al, 1
0x1400124a1  mov     rcx, [rsp+58h+var_10]
0x1400124a6  xor     rcx, rsp; StackCookie
0x1400124a9  call    __security_check_cookie
0x1400124ae  add     rsp, 50h
0x1400124b2  pop     rbx
0x1400124b3  retn
0x1400124b5  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
