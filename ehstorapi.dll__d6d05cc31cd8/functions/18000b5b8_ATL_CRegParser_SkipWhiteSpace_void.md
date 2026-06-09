# ATL::CRegParser::SkipWhiteSpace(void)

- ea: `0x18000b5b8`
- end: `0x18000b5ec`
- name: `?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ`
- size: `52`
- prototype: `void __fastcall(ATL::CRegParser *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000919c`
- `0x18000a570`
- `0x18000ab0c`
- `0x18000b524`

## callees

- `0x18000b5b8`

## import_xrefs

- `USER32!CharNextW` at `0x18000b5db`
- `USER32!CharNextW` at `0x18000b5db`

## pseudocode

```c
void __fastcall ATL::CRegParser::SkipWhiteSpace(LPCWSTR *this)
{
  while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
    *this = CharNextW(*this);
}

```

## disassembly

```asm
0x18000b5b8  push    rbx
0x18000b5ba  sub     rsp, 20h
0x18000b5be  mov     rbx, rcx
0x18000b5c1  mov     rcx, [rbx]; lpsz
0x18000b5c4  movzx   edx, word ptr [rcx]
0x18000b5c7  sub     edx, 9
0x18000b5ca  jz      short loc_18000B5DB
0x18000b5cc  sub     edx, 1
0x18000b5cf  jz      short loc_18000B5DB
0x18000b5d1  sub     edx, 3
0x18000b5d4  jz      short loc_18000B5DB
0x18000b5d6  cmp     edx, 13h
0x18000b5d9  jnz     short loc_18000B5E6
0x18000b5db  call    cs:__imp_CharNextW
0x18000b5e1  mov     [rbx], rax
0x18000b5e4  jmp     short loc_18000B5C1
0x18000b5e6  add     rsp, 20h
0x18000b5ea  pop     rbx
0x18000b5eb  retn
```
