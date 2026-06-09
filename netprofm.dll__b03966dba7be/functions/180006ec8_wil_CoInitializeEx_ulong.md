# wil::CoInitializeEx(ulong)

- ea: `0x180006ec8`
- end: `0x180006f03`
- name: `?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z`
- size: `59`
- prototype: `_BYTE *__fastcall(_BYTE *, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006da0`
- `0x180021360`

## callees

- `0x180006ec8`
- `0x18002a928`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006ed3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006ed3`

## string_xrefs

- `0x180006eee`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_BYTE *__fastcall wil::CoInitializeEx(_BYTE *a1, DWORD a2)
{
  HRESULT v3; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = CoInitializeEx(0, a2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v3,
      v5);
  *a1 = 1;
  return a1;
}

```

## disassembly

```asm
0x180006ec8  push    rbx
0x180006eca  sub     rsp, 30h
0x180006ece  mov     rbx, rcx
0x180006ed1  xor     ecx, ecx; pvReserved
0x180006ed3  call    cs:__imp_CoInitializeEx
0x180006ed9  test    eax, eax
0x180006edb  js      short loc_180006EE9
0x180006edd  mov     byte ptr [rbx], 1
0x180006ee0  mov     rax, rbx
0x180006ee3  add     rsp, 30h
0x180006ee7  pop     rbx
0x180006ee8  retn
0x180006ee9  mov     rcx, [rsp+38h]; this
0x180006eee  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006ef5  mov     r9d, eax; char *
0x180006ef8  mov     edx, 14D3h; void *
0x180006efd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
