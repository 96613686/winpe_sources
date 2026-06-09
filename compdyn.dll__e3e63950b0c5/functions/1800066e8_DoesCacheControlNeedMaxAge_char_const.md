# DoesCacheControlNeedMaxAge(char const *)

- ea: `0x1800066e8`
- end: `0x180006743`
- name: `?DoesCacheControlNeedMaxAge@@YAHPEBD@Z`
- size: `91`
- prototype: `__int64 __fastcall(const char *Str)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001eb0`

## callees

- `0x1800066e8`

## import_xrefs

- `msvcrt!strstr` at `0x1800066f8`
- `msvcrt!strstr` at `0x18000670d`
- `msvcrt!strstr` at `0x180006729`
- `msvcrt!strstr` at `0x1800066f8`
- `msvcrt!strstr` at `0x18000670d`
- `msvcrt!strstr` at `0x180006729`

## string_xrefs

- `0x180006703`: `no-cache`
- `0x180006722`: `no-cache`

## pseudocode

```c
__int64 __fastcall DoesCacheControlNeedMaxAge(const char *Str)
{
  char *v2; // rax

  if ( !strstr(Str, "max-age") )
  {
    v2 = strstr(Str, "no-cache");
    if ( !v2 )
      return 1;
    while ( v2[8] == 61 )
    {
      v2 = strstr(v2 + 8, "no-cache");
      if ( !v2 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800066e8  push    rbx
0x1800066ea  sub     rsp, 20h
0x1800066ee  lea     rdx, SubStr; "max-age"
0x1800066f5  mov     rbx, rcx
0x1800066f8  call    cs:__imp_strstr
0x1800066fe  test    rax, rax
0x180006701  jnz     short loc_18000673B
0x180006703  lea     rdx, aNoCache; "no-cache"
0x18000670a  mov     rcx, rbx; Str
0x18000670d  call    cs:__imp_strstr
0x180006713  test    rax, rax
0x180006716  jz      short loc_180006734
0x180006718  cmp     byte ptr [rax+8], 3Dh ; '='
0x18000671c  lea     rcx, [rax+8]; Str
0x180006720  jnz     short loc_18000673B
0x180006722  lea     rdx, aNoCache; "no-cache"
0x180006729  call    cs:__imp_strstr
0x18000672f  test    rax, rax
0x180006732  jnz     short loc_180006718
0x180006734  mov     eax, 1
0x180006739  jmp     short loc_18000673D
0x18000673b  xor     eax, eax
0x18000673d  add     rsp, 20h
0x180006741  pop     rbx
0x180006742  retn
```
