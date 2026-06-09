# wil::details::ResultStringSize(char const *)

- ea: `0x14000496c`
- end: `0x140004986`
- name: `?ResultStringSize@details@wil@@YA_KPEBD@Z`
- size: `26`
- prototype: `unsigned __int64 __fastcall(wil::details *__hidden this, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ccc`
- `0x140004a9c`

## callees

- `0x14000496c`

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
0x14000496c  test    rcx, rcx
0x14000496f  jnz     short loc_140004975
0x140004971  lea     eax, [rcx+1]
0x140004974  retn
0x140004975  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004979  inc     rax
0x14000497c  cmp     byte ptr [rcx+rax], 0
0x140004980  jnz     short loc_140004979
0x140004982  inc     rax
0x140004985  retn
```
