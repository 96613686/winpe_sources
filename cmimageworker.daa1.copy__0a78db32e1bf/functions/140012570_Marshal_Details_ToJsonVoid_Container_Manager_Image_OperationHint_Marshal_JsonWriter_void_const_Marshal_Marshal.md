# Marshal::Details::ToJsonVoid<Container::Manager::Image::OperationHint,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x140012570`
- end: `0x1400125fb`
- name: `??$ToJsonVoid@W4OperationHint@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400020b0`
- `0x140012570`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::OperationHint,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r8
  _OWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 2u )
    Marshal::Details::FailFast(a1);
  v3 = *(_QWORD *)(Container::Manager::Image::OperationHint_EnumData + 8LL * (unsigned int)*a2);
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
0x140012570  push    rbx
0x140012572  sub     rsp, 50h
0x140012576  mov     rax, cs:__security_cookie
0x14001257d  xor     rax, rsp
0x140012580  mov     [rsp+58h+var_10], rax
0x140012585  mov     rbx, rcx
0x140012588  xor     r9d, r9d
0x14001258b  cmp     dword ptr [rdx], 2
0x14001258e  ja      short loc_1400125F5
0x140012590  mov     rcx, cs:?OperationHint_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::OperationHint_EnumData
0x140012597  mov     eax, [rdx]
0x140012599  mov     rdx, [rcx+rax*8]
0x14001259d  xorps   xmm0, xmm0
0x1400125a0  movups  [rsp+58h+var_30], xmm0
0x1400125a5  xorps   xmm1, xmm1
0x1400125a8  movdqu  [rsp+58h+var_20], xmm1
0x1400125ae  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400125b2  inc     r8
0x1400125b5  cmp     [rdx+r8*2], r9w
0x1400125ba  jnz     short loc_1400125B2
0x1400125bc  lea     rcx, [rsp+58h+var_30]
0x1400125c1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400125c6  nop
0x1400125c7  lea     rdx, [rsp+58h+var_30]
0x1400125cc  mov     rcx, rbx
0x1400125cf  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x1400125d4  nop
0x1400125d5  lea     rcx, [rsp+58h+var_30]
0x1400125da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400125df  mov     al, 1
0x1400125e1  mov     rcx, [rsp+58h+var_10]
0x1400125e6  xor     rcx, rsp; StackCookie
0x1400125e9  call    __security_check_cookie
0x1400125ee  add     rsp, 50h
0x1400125f2  pop     rbx
0x1400125f3  retn
0x1400125f5  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
