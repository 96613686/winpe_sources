# MmAllocate(unsigned __int64)

- ea: `0x180014ae8`
- end: `0x180014b2d`
- name: `?MmAllocate@@YAPEAX_K@Z`
- size: `69`
- prototype: `void *__fastcall(size_t)`
- caller_count: `53`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d60`
- `0x180002dbc`
- `0x180003640`
- `0x18000391c`
- `0x180003984`
- `0x180003aa0`
- `0x18000544c`
- `0x180005740`
- `0x180005888`
- `0x180005c10`
- `0x180005d74`
- `0x180009420`
- `0x18000a300`
- `0x18000b760`
- `0x18000df28`
- `0x18000dffc`
- `0x18000e0e4`
- `0x18000e1cc`
- `0x18000e2a0`
- `0x18000e388`
- `0x18000e488`
- `0x18000e570`
- `0x18000e690`
- `0x18000f06c`
- `0x18000fcf0`
- `0x180010590`
- `0x1800119a8`
- `0x1800124f0`
- `0x180012770`
- `0x180013458`
- `0x180014828`
- `0x180014930`
- `0x180015124`
- `0x180015a7c`
- `0x180015acc`
- `0x180016024`
- `0x1800175dc`
- `0x18001792c`
- `0x180017e54`
- `0x180018228`
- `0x1800190c8`
- `0x180019230`
- `0x18001a7c8`
- `0x18001a828`
- `0x18001a860`
- `0x18001a8b0`
- `0x18001b110`
- `0x18001b1d4`
- `0x18001b27c`
- `0x18001b44c`

## callees

- `0x180014ae8`
- `0x180014b4c`
- `0x180014b7c`

## import_xrefs

- `msvcrt!malloc` at `0x180014af1`
- `msvcrt!malloc` at `0x180014af1`

## pseudocode

```c
void *__fastcall MmAllocate(size_t a1)
{
  void *result; // rax
  __int64 v3; // rdx
  __int64 v4; // r8

  result = malloc(a1);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, a1);
    MmThrowBadAlloc();
  }
  return result;
}

```

## disassembly

```asm
0x180014ae8  push    rbx
0x180014aea  sub     rsp, 20h
0x180014aee  mov     rbx, rcx
0x180014af1  call    cs:__imp_malloc
0x180014af7  test    rax, rax
0x180014afa  jnz     short loc_180014B27
0x180014afc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b03  lea     rax, WPP_GLOBAL_Control
0x180014b0a  cmp     rcx, rax
0x180014b0d  jz      short loc_180014B21
0x180014b0f  test    byte ptr [rcx+1Ch], 1
0x180014b13  jz      short loc_180014B21
0x180014b15  mov     rcx, [rcx+10h]
0x180014b19  mov     r9, rbx
0x180014b1c  call    WPP_SF_P
0x180014b21  call    ?MmThrowBadAlloc@@YAXXZ; MmThrowBadAlloc(void)
0x180014b27  add     rsp, 20h
0x180014b2b  pop     rbx
0x180014b2c  retn
```
