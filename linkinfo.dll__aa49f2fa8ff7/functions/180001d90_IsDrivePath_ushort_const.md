# IsDrivePath(ushort const *)

- ea: `0x180001d90`
- end: `0x180001dd0`
- name: `?IsDrivePath@@YAHPEBG@Z`
- size: `64`
- prototype: `_BOOL8 __fastcall(WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ce0`
- `0x1800033c0`

## callees

- `0x180001d90`
- `0x1800023d0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180001d9c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180001d9c`

## pseudocode

```c
_BOOL8 __fastcall IsDrivePath(WCHAR *a1)
{
  return IsCharAlphaW(*a1) && a1[1] == 58 && CharIsSlash(a1[2]);
}

```

## disassembly

```asm
0x180001d90  push    rbx
0x180001d92  sub     rsp, 20h
0x180001d96  mov     rbx, rcx
0x180001d99  movzx   ecx, word ptr [rcx]; ch
0x180001d9c  call    cs:__imp_IsCharAlphaW
0x180001da3  nop     dword ptr [rax+rax+00h]
0x180001da8  test    eax, eax
0x180001daa  jz      short loc_180001DCC
0x180001dac  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180001db1  jnz     short loc_180001DCC
0x180001db3  movzx   ecx, word ptr [rbx+4]; unsigned __int16
0x180001db7  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180001dbc  test    eax, eax
0x180001dbe  jz      short loc_180001DCC
0x180001dc0  mov     eax, 1
0x180001dc5  add     rsp, 20h
0x180001dc9  pop     rbx
0x180001dca  retn
0x180001dcc  xor     eax, eax
0x180001dce  jmp     short loc_180001DC5
```
