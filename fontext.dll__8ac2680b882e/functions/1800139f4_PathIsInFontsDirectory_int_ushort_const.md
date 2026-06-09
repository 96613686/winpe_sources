# PathIsInFontsDirectory(int,ushort const *)

- ea: `0x1800139f4`
- end: `0x180013a32`
- name: `?PathIsInFontsDirectory@@YA_NHPEBG@Z`
- size: `62`
- prototype: `bool(int, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180008040`
- `0x1800080a0`
- `0x180008120`
- `0x1800081a0`
- `0x180008200`
- `0x1800085ac`
- `0x18001ea2c`
- `0x18001ee80`
- `0x180021954`
- `0x1800220b4`
- `0x180023c7c`
- `0x180023e40`
- `0x180026420`

## callees

- `0x1800135dc`
- `0x1800139f4`

## import_xrefs

- `SHLWAPI!PathIsPrefixW` at `0x180013a1c`
- `SHLWAPI!PathIsPrefixW` at `0x180013a1c`

## pseudocode

```c
bool __fastcall PathIsInFontsDirectory(int a1, const unsigned __int16 *a2)
{
  LPCWSTR pszPrefix; // [rsp+40h] [rbp+18h] BYREF

  pszPrefix = 0;
  return (int)GetFontsDirectory(a1, &pszPrefix) >= 0 && PathIsPrefixW(pszPrefix, a2);
}

```

## disassembly

```asm
0x1800139f4  push    rbx
0x1800139f6  sub     rsp, 20h
0x1800139fa  mov     rbx, rdx
0x1800139fd  mov     [rsp+28h+pszPrefix], 0
0x180013a06  lea     rdx, [rsp+28h+pszPrefix]; unsigned __int16 **
0x180013a0b  call    ?GetFontsDirectory@@YAJHPEAPEBG@Z; GetFontsDirectory(int,ushort const * *)
0x180013a10  test    eax, eax
0x180013a12  js      short loc_180013A2A
0x180013a14  mov     rcx, [rsp+28h+pszPrefix]; pszPrefix
0x180013a19  mov     rdx, rbx; pszPath
0x180013a1c  call    cs:__imp_PathIsPrefixW
0x180013a22  test    eax, eax
0x180013a24  jz      short loc_180013A2A
0x180013a26  mov     al, 1
0x180013a28  jmp     short loc_180013A2C
0x180013a2a  xor     al, al
0x180013a2c  add     rsp, 20h
0x180013a30  pop     rbx
0x180013a31  retn
```
