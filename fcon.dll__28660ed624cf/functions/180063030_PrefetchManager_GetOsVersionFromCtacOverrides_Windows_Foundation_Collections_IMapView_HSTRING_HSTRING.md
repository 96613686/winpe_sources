# PrefetchManager::GetOsVersionFromCtacOverrides(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)

- ea: `0x180063030`
- end: `0x18006313f`
- name: `?GetOsVersionFromCtacOverrides@PrefetchManager@@UEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003220`
- `0x1800107e4`
- `0x180010810`
- `0x18001091c`
- `0x1800109ac`
- `0x180015af4`
- `0x180063030`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063067`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800630f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063067`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800630f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800630de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800630de`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrefetchManager::GetOsVersionFromCtacOverrides(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rbp
  int v6; // edx
  unsigned int v7; // r8d
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  int v10; // eax
  HSTRING string[2]; // [rsp+20h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-58h] BYREF
  __int64 v14; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  string[0] = 0;
  v5 = *a3;
  WindowsDeleteString(0);
  string[0] = 0;
  v14 = 0;
  v8 = -1;
  do
    ++v8;
  while ( aOsversion[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, v7);
    JUMPOUT(0x18006313ELL);
  }
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"OSVersion", v9, v8);
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, HSTRING *))(v5 + 48))(a3, v14, string);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\prefetchmanager.cpp",
      (const char *)(unsigned int)v10,
      (int)string[0]);
  WindowsGetStringRawBuffer(string[0], 0);
  std::wstring::wstring(a2);
  WindowsDeleteString(string[0]);
  return a2;
}

```

## disassembly

```asm
0x180063030  mov     [rsp+arg_0], rbx
0x180063035  push    rbp
0x180063036  push    rsi
0x180063037  push    rdi
0x180063038  push    r14
0x18006303a  push    r15
0x18006303c  sub     rsp, 60h
0x180063040  mov     rax, cs:__security_cookie
0x180063047  xor     rax, rsp
0x18006304a  mov     [rsp+88h+var_38], rax
0x18006304f  mov     r14, r8
0x180063052  mov     rdi, rdx
0x180063055  mov     [rsp+88h+string], rdx
0x18006305a  xor     r15d, r15d
0x18006305d  mov     [rsp+88h+string], r15
0x180063062  mov     rbp, [r8]
0x180063065  xor     ecx, ecx; string
0x180063067  call    cs:__imp_WindowsDeleteString
0x18006306d  mov     [rsp+88h+string], r15; int
0x180063072  mov     [rsp+88h+var_40], r15
0x180063077  mov     rsi, cs:off_1800BDDA0; "OSVersion"
0x18006307e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180063082  inc     rbx
0x180063085  cmp     [rsi+rbx*2], r15w
0x18006308a  jnz     short loc_180063082
0x18006308c  mov     eax, 0FFFFFFFFh
0x180063091  cmp     rbx, rax
0x180063094  ja      loc_180063134
0x18006309a  mov     ecx, ebx; unsigned int
0x18006309c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800630a1  mov     r9d, ebx; unsigned int
0x1800630a4  mov     r8d, eax; unsigned int
0x1800630a7  mov     rdx, rsi; sourceString
0x1800630aa  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x1800630af  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800630b4  nop
0x1800630b5  lea     r8, [rsp+88h+string]
0x1800630ba  mov     rdx, [rsp+88h+var_40]
0x1800630bf  mov     rcx, r14
0x1800630c2  mov     rax, [rbp+30h]
0x1800630c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630cb  mov     rcx, [rsp+88h]; this
0x1800630d3  test    eax, eax
0x1800630d5  js      short loc_18006311F
0x1800630d7  xor     edx, edx; length
0x1800630d9  mov     rcx, [rsp+88h+string]; string
0x1800630de  call    cs:__imp_WindowsGetStringRawBuffer
0x1800630e4  mov     rdx, rax
0x1800630e7  mov     rcx, rdi
0x1800630ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800630ef  nop
0x1800630f0  mov     rcx, [rsp+88h+string]; string
0x1800630f5  call    cs:__imp_WindowsDeleteString
0x1800630fb  mov     rax, rdi
0x1800630fe  mov     rcx, [rsp+88h+var_38]
0x180063103  xor     rcx, rsp; StackCookie
0x180063106  call    __security_check_cookie
0x18006310b  mov     rbx, [rsp+88h+arg_0]
0x180063113  add     rsp, 60h
0x180063117  pop     r15
0x180063119  pop     r14
0x18006311b  pop     rdi
0x18006311c  pop     rsi
0x18006311d  pop     rbp
0x18006311e  retn
0x18006311f  mov     r9d, eax; char *
0x180063122  lea     r8, aOnecoreBaseFli_19; "onecore\\base\\flighting\\featuremanage"...
0x180063129  mov     edx, 5Ah ; 'Z'; void *
0x18006312e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180063134  mov     ecx, 80070216h; this
0x180063139  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
