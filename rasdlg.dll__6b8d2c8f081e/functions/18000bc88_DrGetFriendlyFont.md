# DrGetFriendlyFont

- ea: `0x18000bc88`
- end: `0x18000bd6b`
- name: `DrGetFriendlyFont`
- size: `227`
- prototype: `int __fastcall(HWND hWnd, int, HFONT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd74`

## callees

- `0x18000bc88`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x18000bd31`
- `GDI32!CreateFontIndirectW` at `0x18000bd31`
- `GDI32!GetObjectW` at `0x18000bcfe`
- `GDI32!GetObjectW` at `0x18000bcfe`
- `GDI32!GetStockObject` at `0x18000bce6`
- `GDI32!GetStockObject` at `0x18000bce6`
- `USER32!GetDC` at `0x18000bd1e`
- `USER32!GetDC` at `0x18000bd1e`
- `USER32!ReleaseDC` at `0x18000bd40`
- `USER32!ReleaseDC` at `0x18000bd40`
- `USER32!SendMessageW` at `0x18000bcd8`
- `USER32!SendMessageW` at `0x18000bcd8`

## pseudocode

```c
int __fastcall DrGetFriendlyFont(HWND hWnd, int a2, HFONT *a3)
{
  HDC DC; // rax
  BYTE lfItalic; // al
  HDC v8; // rbx
  LOGFONTW pv; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&pv, 0, sizeof(pv));
  *a3 = 0;
  DC = (HDC)SendMessageW(hWnd, 0x31u, 0, 0);
  if ( DC || (DC = (HDC)GetStockObject(13)) != 0 )
  {
    LODWORD(DC) = GetObjectW(DC, 92, &pv);
    if ( (_DWORD)DC )
    {
      lfItalic = pv.lfItalic;
      if ( a2 )
        lfItalic = 1;
      pv.lfItalic = lfItalic;
      DC = GetDC(hWnd);
      v8 = DC;
      if ( DC )
      {
        *a3 = CreateFontIndirectW(&pv);
        LODWORD(DC) = ReleaseDC(hWnd, v8);
      }
    }
  }
  return (int)DC;
}

```

## disassembly

```asm
0x18000bc88  mov     [rsp+arg_8], rbx
0x18000bc8d  mov     [rsp+arg_18], rsi
0x18000bc92  push    rdi
0x18000bc93  sub     rsp, 90h
0x18000bc9a  mov     rax, cs:__security_cookie
0x18000bca1  xor     rax, rsp
0x18000bca4  mov     [rsp+98h+var_18], rax
0x18000bcac  mov     ebx, edx
0x18000bcae  mov     rsi, r8
0x18000bcb1  xor     edx, edx; Val
0x18000bcb3  mov     rdi, rcx
0x18000bcb6  lea     rcx, [rsp+98h+pv]; void *
0x18000bcbb  lea     r8d, [rdx+5Ch]; Size
0x18000bcbf  call    memset_0
0x18000bcc4  xor     r9d, r9d; lParam
0x18000bcc7  mov     qword ptr [rsi], 0
0x18000bcce  xor     r8d, r8d; wParam
0x18000bcd1  mov     rcx, rdi; hWnd
0x18000bcd4  lea     edx, [r9+31h]; Msg
0x18000bcd8  call    cs:__imp_SendMessageW
0x18000bcde  test    rax, rax
0x18000bce1  jnz     short loc_18000BCF1
0x18000bce3  lea     ecx, [rax+0Dh]; i
0x18000bce6  call    cs:__imp_GetStockObject
0x18000bcec  test    rax, rax
0x18000bcef  jz      short loc_18000BD46
0x18000bcf1  lea     r8, [rsp+98h+pv]; pv
0x18000bcf6  mov     edx, 5Ch ; '\'; c
0x18000bcfb  mov     rcx, rax; h
0x18000bcfe  call    cs:__imp_GetObjectW
0x18000bd04  test    eax, eax
0x18000bd06  jz      short loc_18000BD46
0x18000bd08  movzx   eax, [rsp+98h+var_64]
0x18000bd0d  mov     ecx, 1
0x18000bd12  test    ebx, ebx
0x18000bd14  cmovnz  eax, ecx
0x18000bd17  mov     rcx, rdi; hWnd
0x18000bd1a  mov     [rsp+98h+var_64], al
0x18000bd1e  call    cs:__imp_GetDC
0x18000bd24  mov     rbx, rax
0x18000bd27  test    rax, rax
0x18000bd2a  jz      short loc_18000BD46
0x18000bd2c  lea     rcx, [rsp+98h+pv]; lplf
0x18000bd31  call    cs:__imp_CreateFontIndirectW
0x18000bd37  mov     rdx, rbx; hDC
0x18000bd3a  mov     rcx, rdi; hWnd
0x18000bd3d  mov     [rsi], rax
0x18000bd40  call    cs:__imp_ReleaseDC
0x18000bd46  mov     rcx, [rsp+98h+var_18]
0x18000bd4e  xor     rcx, rsp; StackCookie
0x18000bd51  call    __security_check_cookie
0x18000bd56  lea     r11, [rsp+98h+var_8]
0x18000bd5e  mov     rbx, [r11+18h]
0x18000bd62  mov     rsi, [r11+28h]
0x18000bd66  mov     rsp, r11
0x18000bd69  pop     rdi
0x18000bd6a  retn
```
