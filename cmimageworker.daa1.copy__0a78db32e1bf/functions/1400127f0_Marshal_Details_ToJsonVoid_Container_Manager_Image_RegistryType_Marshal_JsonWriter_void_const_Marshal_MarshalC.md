# Marshal::Details::ToJsonVoid<Container::Manager::Image::RegistryType,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x1400127f0`
- end: `0x14001287b`
- name: `??$ToJsonVoid@W4RegistryType@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400020b0`
- `0x1400127f0`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::RegistryType,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r8
  _OWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 6u )
    Marshal::Details::FailFast(a1);
  v3 = *(_QWORD *)(Container::Manager::Image::RegistryType_EnumData + 8LL * (unsigned int)*a2);
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
0x1400127f0  push    rbx
0x1400127f2  sub     rsp, 50h
0x1400127f6  mov     rax, cs:__security_cookie
0x1400127fd  xor     rax, rsp
0x140012800  mov     [rsp+58h+var_10], rax
0x140012805  mov     rbx, rcx
0x140012808  xor     r9d, r9d
0x14001280b  cmp     dword ptr [rdx], 6
0x14001280e  ja      short loc_140012875
0x140012810  mov     rcx, cs:?RegistryType_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::RegistryType_EnumData
0x140012817  mov     eax, [rdx]
0x140012819  mov     rdx, [rcx+rax*8]
0x14001281d  xorps   xmm0, xmm0
0x140012820  movups  [rsp+58h+var_30], xmm0
0x140012825  xorps   xmm1, xmm1
0x140012828  movdqu  [rsp+58h+var_20], xmm1
0x14001282e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012832  inc     r8
0x140012835  cmp     [rdx+r8*2], r9w
0x14001283a  jnz     short loc_140012832
0x14001283c  lea     rcx, [rsp+58h+var_30]
0x140012841  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140012846  nop
0x140012847  lea     rdx, [rsp+58h+var_30]
0x14001284c  mov     rcx, rbx
0x14001284f  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x140012854  nop
0x140012855  lea     rcx, [rsp+58h+var_30]
0x14001285a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001285f  mov     al, 1
0x140012861  mov     rcx, [rsp+58h+var_10]
0x140012866  xor     rcx, rsp; StackCookie
0x140012869  call    __security_check_cookie
0x14001286e  add     rsp, 50h
0x140012872  pop     rbx
0x140012873  retn
0x140012875  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
