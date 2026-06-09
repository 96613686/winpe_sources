# SetString

- ea: `0x18000a378`
- end: `0x18000a3a5`
- name: `SetString`
- size: `45`
- prototype: `int __fastcall(LPWSTR lpBuffer, int cchBufferMax, unsigned __int16)`
- caller_count: `16`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004c14`
- `0x180004e80`
- `0x180005530`
- `0x180005aec`
- `0x180005c00`
- `0x180006afc`
- `0x180007594`
- `0x180007628`
- `0x180007c0c`
- `0x1800080c4`
- `0x1800085c8`
- `0x180009e8c`
- `0x18000a66c`
- `0x18000ac40`
- `0x18000b9c0`
- `0x18000cfc4`

## callees

- `0x18000a378`

## import_xrefs

- `USER32!LoadStringW` at `0x18000a392`
- `USER32!LoadStringW` at `0x18000a392`

## pseudocode

```c
int __fastcall SetString(LPWSTR lpBuffer, int cchBufferMax, unsigned __int16 a3)
{
  int result; // eax

  result = LoadStringW(g_hResDLL, a3, lpBuffer, cchBufferMax);
  if ( !result )
    *lpBuffer = 0;
  return result;
}

```

## disassembly

```asm
0x18000a378  push    rbx
0x18000a37a  sub     rsp, 20h
0x18000a37e  mov     r9d, edx; cchBufferMax
0x18000a381  mov     rbx, rcx
0x18000a384  movzx   edx, r8w; uID
0x18000a388  mov     r8, rcx; lpBuffer
0x18000a38b  mov     rcx, cs:g_hResDLL; hInstance
0x18000a392  call    cs:__imp_LoadStringW
0x18000a398  test    eax, eax
0x18000a39a  jnz     short loc_18000A39F
0x18000a39c  mov     [rbx], ax
0x18000a39f  add     rsp, 20h
0x18000a3a3  pop     rbx
0x18000a3a4  retn
```
