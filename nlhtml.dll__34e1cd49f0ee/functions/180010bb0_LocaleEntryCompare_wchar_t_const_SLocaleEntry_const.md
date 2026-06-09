# LocaleEntryCompare(wchar_t const *,SLocaleEntry const *)

- ea: `0x180010bb0`
- end: `0x180010bd2`
- name: `?LocaleEntryCompare@@YAHPEB_WPEBUSLocaleEntry@@@Z`
- size: `34`
- prototype: `__int64 __fastcall(const wchar_t *, const struct SLocaleEntry *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010bb0`

## pseudocode

```c
__int64 __fastcall LocaleEntryCompare(wchar_t *a1, const struct SLocaleEntry *a2)
{
  __int64 v2; // r8
  wchar_t v3; // ax

  v2 = *(_QWORD *)a2 - (_QWORD)a1;
  while ( 1 )
  {
    v3 = *a1;
    if ( *a1 != *(wchar_t *)((char *)a1 + v2) )
      break;
    ++a1;
    if ( !v3 )
      return 0;
  }
  return v3 < *(wchar_t *)((char *)a1 + v2) ? -1 : 1;
}

```

## disassembly

```asm
0x180010bb0  mov     r8, [rdx]
0x180010bb3  sub     r8, rcx
0x180010bb6  movzx   eax, word ptr [rcx]
0x180010bb9  cmp     ax, [rcx+r8]
0x180010bbe  jnz     short loc_180010BCC
0x180010bc0  add     rcx, 2
0x180010bc4  test    ax, ax
0x180010bc7  jnz     short loc_180010BB6
0x180010bc9  xor     eax, eax
0x180010bcb  retn
0x180010bcc  sbb     eax, eax
0x180010bce  or      eax, 1
0x180010bd1  retn
```
