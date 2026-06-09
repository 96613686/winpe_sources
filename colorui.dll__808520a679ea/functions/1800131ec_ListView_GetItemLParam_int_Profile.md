# ListView::GetItemLParam(int,Profile * *)

- ea: `0x1800131ec`
- end: `0x180013275`
- name: `?GetItemLParam@ListView@@QEBAJHPEAPEAUProfile@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(HWND *this, int, struct Profile **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e7ac`
- `0x180013160`
- `0x18001330c`
- `0x180013458`
- `0x180016fa8`

## callees

- `0x1800131ec`
- `0x1800184ce`

## import_xrefs

- `USER32!SendMessageW` at `0x180013245`
- `USER32!SendMessageW` at `0x180013245`

## pseudocode

```c
__int64 __fastcall ListView::GetItemLParam(HWND *this, int a2, struct Profile **a3)
{
  HWND v7; // rcx
  LPARAM lParam; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v9[32]; // [rsp+28h] [rbp-60h] BYREF
  struct Profile *v10; // [rsp+48h] [rbp-40h]

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  memset_0(v9, 0, 0x50u);
  v7 = *this;
  HIDWORD(lParam) = a2;
  LODWORD(lParam) = 4;
  if ( !(unsigned int)SendMessageW(v7, 0x104Bu, 0, (LPARAM)&lParam) )
    return 2147500037LL;
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x1800131ec  mov     [rsp+arg_0], rbx
0x1800131f1  mov     [rsp+arg_8], rsi
0x1800131f6  push    rdi
0x1800131f7  sub     rsp, 80h
0x1800131fe  mov     rbx, r8
0x180013201  mov     edi, edx
0x180013203  mov     rsi, rcx
0x180013206  test    r8, r8
0x180013209  jnz     short loc_180013212
0x18001320b  mov     eax, 80070057h
0x180013210  jmp     short loc_180013260
0x180013212  xor     edx, edx; Val
0x180013214  mov     qword ptr [r8], 0
0x18001321b  lea     rcx, [rsp+88h+var_60]; void *
0x180013220  lea     r8d, [rdx+50h]; Size
0x180013224  call    memset_0
0x180013229  mov     rcx, [rsi]; hWnd
0x18001322c  lea     r9, [rsp+88h+lParam]; lParam
0x180013231  xor     r8d, r8d; wParam
0x180013234  mov     dword ptr [rsp+88h+lParam+4], edi
0x180013238  mov     edx, 104Bh; Msg
0x18001323d  mov     dword ptr [rsp+88h+lParam], 4
0x180013245  call    cs:__imp_SendMessageW
0x18001324b  test    eax, eax
0x18001324d  jnz     short loc_180013256
0x18001324f  mov     eax, 80004005h
0x180013254  jmp     short loc_180013260
0x180013256  mov     rax, [rsp+88h+var_40]
0x18001325b  mov     [rbx], rax
0x18001325e  xor     eax, eax
0x180013260  lea     r11, [rsp+88h+var_8]
0x180013268  mov     rbx, [r11+10h]
0x18001326c  mov     rsi, [r11+18h]
0x180013270  mov     rsp, r11
0x180013273  pop     rdi
0x180013274  retn
```
