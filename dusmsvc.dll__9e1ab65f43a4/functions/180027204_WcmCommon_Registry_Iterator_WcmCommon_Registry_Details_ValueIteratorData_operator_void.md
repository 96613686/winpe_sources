# WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::ValueIteratorData>::operator*(void)

- ea: `0x180027204`
- end: `0x18002724d`
- name: `??D?$Iterator@UValueIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@QEBAPEB_WXZ`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027fbc`
- `0x1800282b0`

## callees

- `0x1800172c8`
- `0x180027204`

## string_xrefs

- `0x180027216`: `onecore\private\net\inc\wcm\wcm_registry_iterator.h`

## pseudocode

```c
const WCHAR *__fastcall WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::ValueIteratorData>::operator*(
        __int64 a1)
{
  const WCHAR *result; // rax
  unsigned int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 36) == -1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_iterator.h",
      (const char *)0x103,
      v2);
  result = &LocaleName;
  if ( (unsigned __int64)((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 1) >= 2 )
    return *(const WCHAR **)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x180027204  sub     rsp, 28h
0x180027208  cmp     dword ptr [rcx+24h], 0FFFFFFFFh
0x18002720c  mov     rdx, rcx
0x18002720f  jnz     short loc_18002722D
0x180027211  mov     rcx, [rsp+28h]; this
0x180027216  lea     r8, aOnecorePrivate_1; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18002721d  mov     r9d, 103h; char *
0x180027223  lea     edx, [r9-2Ch]; void *
0x180027227  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002722d  mov     rcx, [rcx+10h]
0x180027231  lea     rax, LocaleName
0x180027238  sub     rcx, [rdx+8]
0x18002723c  sar     rcx, 1
0x18002723f  cmp     rcx, 2
0x180027243  cmovnb  rax, [rdx+8]
0x180027248  add     rsp, 28h
0x18002724c  retn
```
