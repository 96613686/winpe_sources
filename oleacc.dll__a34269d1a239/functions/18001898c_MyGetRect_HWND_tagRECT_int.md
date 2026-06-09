# MyGetRect(HWND__ *,tagRECT *,int)

- ea: `0x18001898c`
- end: `0x1800189d5`
- name: `?MyGetRect@@YAXPEAUHWND__@@PEAUtagRECT@@H@Z`
- size: `73`
- prototype: `void __fastcall(HWND hWnd, LPRECT lpRect, int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180026c00`
- `0x1800281f4`
- `0x180028a10`
- `0x180028ba0`
- `0x18002df80`
- `0x180039390`
- `0x180044b60`
- `0x180044c30`

## callees

- `0x18001898c`

## import_xrefs

- `USER32!SetRectEmpty` at `0x1800189a7`
- `USER32!SetRectEmpty` at `0x1800189a7`
- `USER32!GetWindowRect` at `0x1800189cd`
- `USER32!GetWindowRect` at `0x1800189cd`
- `USER32!GetClientRect` at `0x1800189b7`
- `USER32!GetClientRect` at `0x1800189b7`

## pseudocode

```c
void __fastcall MyGetRect(HWND hWnd, LPRECT lpRect, int a3)
{
  SetRectEmpty(lpRect);
  if ( a3 )
    GetWindowRect(hWnd, lpRect);
  else
    GetClientRect(hWnd, lpRect);
}

```

## disassembly

```asm
0x18001898c  mov     [rsp+arg_0], rbx
0x180018991  mov     [rsp+arg_8], rsi
0x180018996  push    rdi
0x180018997  sub     rsp, 20h
0x18001899b  mov     rsi, rcx
0x18001899e  mov     ebx, r8d
0x1800189a1  mov     rcx, rdx; lprc
0x1800189a4  mov     rdi, rdx
0x1800189a7  call    cs:__imp_SetRectEmpty
0x1800189ad  mov     rdx, rdi; lpRect
0x1800189b0  mov     rcx, rsi; hWnd
0x1800189b3  test    ebx, ebx
0x1800189b5  jnz     short loc_1800189CD
0x1800189b7  call    cs:__imp_GetClientRect
0x1800189bd  mov     rbx, [rsp+28h+arg_0]
0x1800189c2  mov     rsi, [rsp+28h+arg_8]
0x1800189c7  add     rsp, 20h
0x1800189cb  pop     rdi
0x1800189cc  retn
0x1800189cd  call    cs:__imp_GetWindowRect
0x1800189d3  jmp     short loc_1800189BD
```
