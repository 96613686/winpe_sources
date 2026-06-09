# uus::Session::Session(ushort const *)

- ea: `0x1800084c8`
- end: `0x1800085f3`
- name: `??0Session@uus@@QEAA@PEBG@Z`
- size: `299`
- prototype: `uus::Session *__fastcall(uus::Session *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008334`

## callees

- `0x180001ba0`
- `0x180006aa0`
- `0x180006ccc`
- `0x180007504`
- `0x1800084c8`
- `0x180008d88`
- `0x180008ef4`
- `0x180009774`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008571`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008571`

## pseudocode

```c
uus::Session *__fastcall uus::Session::Session(uus::Session *this, const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  LPVOID pv[4]; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v7[4]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v8[32]; // [rsp+60h] [rbp-19h] BYREF
  char v9; // [rsp+80h] [rbp+7h]
  _OWORD v10[2]; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v11[32]; // [rsp+A8h] [rbp+2Fh] BYREF

  pv[0] = this;
  v3 = 0;
  *(_QWORD *)this = &uus::Session::`vftable';
  v7[0] = 32;
  v7[1] = 3;
  v7[2] = &_ImageBase;
  v7[3] = a2;
  v10[0] = 0;
  v10[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v10[0]) = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(pv);
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)pv[0] + v4) );
  pv[2] = pv[0];
  pv[3] = (LPVOID)v4;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v11);
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  uus::Utility::FindFileInArchFolder(v8, v11);
  std::wstring::~wstring(v11);
  if ( v9 )
  {
    std::wstring::operator=(v10, v8);
    if ( v9 )
      std::wstring::~wstring(v8);
    v3 = uus::Utility::GetBrainSession<uus::Brain3>((char *)v10, (__int64)v7);
  }
  std::wstring::~wstring(v10);
  *((_QWORD *)this + 1) = v3;
  return this;
}

```

## disassembly

```asm
0x1800084c8  mov     [rsp-8+arg_10], rbx
0x1800084cd  mov     [rsp-8+arg_18], rdi
0x1800084d2  push    rbp
0x1800084d3  lea     rbp, [rsp-57h]
0x1800084d8  sub     rsp, 0D0h
0x1800084df  mov     rax, cs:__security_cookie
0x1800084e6  xor     rax, rsp
0x1800084e9  mov     [rbp+57h+var_8], rax
0x1800084ed  mov     rdi, rcx
0x1800084f0  mov     [rbp+57h+pv], rcx
0x1800084f4  xor     ebx, ebx
0x1800084f6  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x1800084fd  mov     [rcx], rax
0x180008500  mov     [rbp+57h+var_90], 20h ; ' '
0x180008508  mov     [rbp+57h+var_88], 3
0x180008510  lea     rax, __ImageBase
0x180008517  mov     [rbp+57h+var_80], rax
0x18000851b  mov     [rbp+57h+var_78], rdx
0x18000851f  xorps   xmm0, xmm0
0x180008522  movups  [rbp+57h+var_48], xmm0
0x180008526  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000852e  movdqu  [rbp+57h+var_38], xmm1
0x180008533  mov     word ptr [rbp+57h+var_48], bx
0x180008537  lea     rcx, [rbp+57h+pv]
0x18000853b  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x180008540  nop
0x180008541  mov     rcx, [rbp+57h+pv]
0x180008545  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008549  inc     rax
0x18000854c  cmp     [rcx+rax*2], bx
0x180008550  jnz     short loc_180008549
0x180008552  mov     [rbp+57h+var_A0], rcx
0x180008556  mov     [rbp+57h+var_98], rax
0x18000855a  lea     rdx, [rbp+57h+var_A0]
0x18000855e  lea     rcx, [rbp+57h+var_28]; void *
0x180008562  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180008567  nop
0x180008568  mov     rcx, [rbp+57h+pv]; pv
0x18000856c  test    rcx, rcx
0x18000856f  jz      short loc_180008578
0x180008571  call    cs:__imp_CoTaskMemFree
0x180008577  nop
0x180008578  lea     rdx, [rbp+57h+var_28]
0x18000857c  lea     rcx, [rbp+57h+var_70]
0x180008580  call    ?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)
0x180008585  nop
0x180008586  lea     rcx, [rbp+57h+var_28]
0x18000858a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000858f  cmp     [rbp+57h+var_50], bl
0x180008592  jnz     short loc_180008596
0x180008594  jmp     short loc_1800085C2
0x180008596  lea     rdx, [rbp+57h+var_70]
0x18000859a  lea     rcx, [rbp+57h+var_48]
0x18000859e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800085a3  nop
0x1800085a4  cmp     [rbp+57h+var_50], bl
0x1800085a7  jz      short loc_1800085B2
0x1800085a9  lea     rcx, [rbp+57h+var_70]
0x1800085ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800085b2  lea     rdx, [rbp+57h+var_90]
0x1800085b6  lea     rcx, [rbp+57h+var_48]
0x1800085ba  call    ??$GetBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@AEBVpath@filesystem@std@@AEBUPinkyContext@1@@Z; uus::Utility::GetBrainSession<uus::Brain3>(std::filesystem::path const &,uus::PinkyContext const &)
0x1800085bf  mov     rbx, rax
0x1800085c2  lea     rcx, [rbp+57h+var_48]
0x1800085c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800085cb  mov     [rdi+8], rbx
0x1800085cf  mov     rax, rdi
0x1800085d2  mov     rcx, [rbp+57h+var_8]
0x1800085d6  xor     rcx, rsp; StackCookie
0x1800085d9  call    __security_check_cookie
0x1800085de  lea     r11, [rsp+0D0h+var_s0]
0x1800085e6  mov     rbx, [r11+20h]
0x1800085ea  mov     rdi, [r11+28h]
0x1800085ee  mov     rsp, r11
0x1800085f1  pop     rbp
0x1800085f2  retn
```
