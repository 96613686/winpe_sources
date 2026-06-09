# wil::details::ResultStringSize(char const *)

- ea: `0x180008710`
- end: `0x18000872a`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `__int64 __fastcall(wil::details *this, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000558c`
- `0x1800088a0`
- `0x180008ac8`

## callees

- `0x180008710`

## pseudocode

```c
__int64 __fastcall wil::details::ResultStringSize(wil::details *this, const char *a2)
{
  __int64 v3; // rax

  if ( !this )
    return 1;
  v3 = -1;
  do
    ++v3;
  while ( *((_BYTE *)this + v3) );
  return v3 + 1;
}

```

## disassembly

```asm
0x180008710  test    rcx, rcx
0x180008713  jnz     short loc_180008719
0x180008715  lea     eax, [rcx+1]
0x180008718  retn
0x180008719  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000871d  inc     rax
0x180008720  cmp     byte ptr [rcx+rax], 0
0x180008724  jnz     short loc_18000871D
0x180008726  inc     rax
0x180008729  retn
```
