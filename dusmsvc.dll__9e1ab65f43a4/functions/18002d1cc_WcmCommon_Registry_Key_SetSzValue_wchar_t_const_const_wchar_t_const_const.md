# WcmCommon::Registry::Key::SetSzValue(wchar_t const * const,wchar_t const * const)

- ea: `0x18002d1cc`
- end: `0x18002d234`
- name: `?SetSzValue@Key@Registry@WcmCommon@@QEAAXQEB_W0@Z`
- size: `104`
- prototype: `void(WcmCommon::Registry::Key *__hidden this, const wchar_t *const, const wchar_t *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ab28`

## callees

- `0x180020820`
- `0x18002d1cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d1fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d1fe`

## string_xrefs

- `0x18002d219`: `onecore\private\net\inc\wcm\wcm_registry_key.h`

## pseudocode

```c
void __fastcall WcmCommon::Registry::Key::SetSzValue(HKEY *this, const WCHAR *a2, const BYTE *a3)
{
  __int64 v3; // rax
  int v4; // eax
  bool v5; // sf
  int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a3[2 * v3] );
  v4 = RegSetValueExW(*this, a2, 0, 1u, a3, 2 * v3 + 2);
  v5 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = v4 < 0;
  }
  if ( v5 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x11B,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_key.h",
      (const char *)(unsigned int)v4,
      lpData);
}

```

## disassembly

```asm
0x18002d1cc  push    rbx
0x18002d1ce  sub     rsp, 30h
0x18002d1d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d1d6  xor     ebx, ebx
0x18002d1d8  inc     rax
0x18002d1db  cmp     [r8+rax*2], bx
0x18002d1e0  jnz     short loc_18002D1D8
0x18002d1e2  mov     rcx, [rcx]; hKey
0x18002d1e5  lea     eax, ds:2[rax*2]
0x18002d1ec  mov     [rsp+38h+cbData], eax; cbData
0x18002d1f0  mov     r9d, 1; dwType
0x18002d1f6  mov     [rsp+38h+lpData], r8; int
0x18002d1fb  xor     r8d, r8d; Reserved
0x18002d1fe  call    cs:__imp_RegSetValueExW
0x18002d204  test    eax, eax
0x18002d206  jle     short loc_18002D212
0x18002d208  movzx   eax, ax
0x18002d20b  or      eax, 80070000h
0x18002d210  test    eax, eax
0x18002d212  jns     short loc_18002D22E
0x18002d214  mov     rcx, [rsp+38h]; this
0x18002d219  lea     r8, aOnecorePrivate_2; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18002d220  mov     r9d, eax; char *
0x18002d223  mov     edx, 11Bh; void *
0x18002d228  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d22e  add     rsp, 30h
0x18002d232  pop     rbx
0x18002d233  retn
```
