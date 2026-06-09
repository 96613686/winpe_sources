# Marshal::Details::ToJsonVoid<Container::Manager::Image::RegistryOperation,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x140012750`
- end: `0x1400127db`
- name: `??$ToJsonVoid@W4RegistryOperation@Image@Manager@Container@@$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400020b0`
- `0x140012750`
- `0x140012884`
- `0x140012934`
- `0x140015838`
- `0x1400198a4`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<enum Container::Manager::Image::RegistryOperation,>(
        Marshal::Details *a1,
        _DWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r8
  _OWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF

  if ( *a2 > 3u )
    Marshal::Details::FailFast(a1);
  v3 = *(_QWORD *)(Container::Manager::Image::RegistryOperation_EnumData + 8LL * (unsigned int)*a2);
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
0x140012750  push    rbx
0x140012752  sub     rsp, 50h
0x140012756  mov     rax, cs:__security_cookie
0x14001275d  xor     rax, rsp
0x140012760  mov     [rsp+58h+var_10], rax
0x140012765  mov     rbx, rcx
0x140012768  xor     r9d, r9d
0x14001276b  cmp     dword ptr [rdx], 3
0x14001276e  ja      short loc_1400127D5
0x140012770  mov     rcx, cs:?RegistryOperation_EnumData@Image@Manager@Container@@3UEnumData@Marshal@@B; Marshal::EnumData const Container::Manager::Image::RegistryOperation_EnumData
0x140012777  mov     eax, [rdx]
0x140012779  mov     rdx, [rcx+rax*8]
0x14001277d  xorps   xmm0, xmm0
0x140012780  movups  [rsp+58h+var_30], xmm0
0x140012785  xorps   xmm1, xmm1
0x140012788  movdqu  [rsp+58h+var_20], xmm1
0x14001278e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012792  inc     r8
0x140012795  cmp     [rdx+r8*2], r9w
0x14001279a  jnz     short loc_140012792
0x14001279c  lea     rcx, [rsp+58h+var_30]
0x1400127a1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400127a6  nop
0x1400127a7  lea     rdx, [rsp+58h+var_30]
0x1400127ac  mov     rcx, rbx
0x1400127af  call    ??$WriteJson@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Details@Marshal@@YAXAEAVJsonWriter@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Marshal::Details::WriteJson<std::wstring>(Marshal::JsonWriter &,std::wstring const &)
0x1400127b4  nop
0x1400127b5  lea     rcx, [rsp+58h+var_30]
0x1400127ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400127bf  mov     al, 1
0x1400127c1  mov     rcx, [rsp+58h+var_10]
0x1400127c6  xor     rcx, rsp; StackCookie
0x1400127c9  call    __security_check_cookie
0x1400127ce  add     rsp, 50h
0x1400127d2  pop     rbx
0x1400127d3  retn
0x1400127d5  call    ?FailFast@Details@Marshal@@YAXXZ; Marshal::Details::FailFast(void)
```
