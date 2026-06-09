# MCHandleSetFont

- ea: `0x180043fe4`
- end: `0x1800440e1`
- name: `MCHandleSetFont`
- size: `253`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180042bec`
- `0x180046d90`

## callees

- `0x1800115f0`
- `0x180018ab8`
- `0x180042794`
- `0x180043fe4`
- `0x18008ea60`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004407b`
- `GDI32!DeleteObject` at `0x18004407b`
- `GDI32!GetStockObject` at `0x18004402a`
- `GDI32!GetStockObject` at `0x18004402a`
- `GDI32!GetObjectW` at `0x18004403d`
- `GDI32!GetObjectW` at `0x18004403d`
- `GDI32!CreateFontIndirectW` at `0x180044061`
- `GDI32!CreateFontIndirectW` at `0x180044061`
- `USER32!InvalidateRect` at `0x1800440af`
- `USER32!InvalidateRect` at `0x1800440af`
- `USER32!UpdateWindow` at `0x1800440b8`
- `USER32!UpdateWindow` at `0x1800440b8`

## pseudocode

```c
int __fastcall MCHandleSetFont(__int64 a1, HGDIOBJ StockObject, int a3)
{
  LONG v6; // ecx
  HFONT v7; // rax
  HFONT v8; // rsi
  void *v9; // rcx
  LOGFONTW pv; // [rsp+20h] [rbp-88h] BYREF

  memset(&pv, 0, sizeof(pv));
  if ( !StockObject )
    StockObject = GetStockObject(13);
  GetObjectW(StockObject, 92, &pv);
  v6 = 800;
  if ( pv.lfWeight >= 700 )
    v6 = 1000;
  pv.lfWeight = v6;
  v7 = CreateFontIndirectW(&pv);
  v8 = v7;
  if ( v7 )
  {
    v9 = *(void **)(a1 + 1680);
    if ( v9 )
      DeleteObject(v9);
    *(_QWORD *)(a1 + 1672) = StockObject;
    *(_QWORD *)(a1 + 1680) = v8;
    *(_DWORD *)(a1 + 28) = GetCodePageForFont(StockObject);
    LODWORD(v7) = MCCalcSizes(a1);
    if ( a3 )
    {
      InvalidateRect(*(HWND *)a1, 0, 1);
      LODWORD(v7) = UpdateWindow(*(HWND *)a1);
    }
  }
  return (int)v7;
}

```

## disassembly

```asm
0x180043fe4  mov     [rsp+arg_10], rbx
0x180043fe9  push    rbp
0x180043fea  push    rsi
0x180043feb  push    rdi
0x180043fec  sub     rsp, 90h
0x180043ff3  mov     rax, cs:__security_cookie
0x180043ffa  xor     rax, rsp
0x180043ffd  mov     [rsp+0A8h+var_28], rax
0x180044005  mov     ebp, r8d
0x180044008  mov     rdi, rdx
0x18004400b  mov     rbx, rcx
0x18004400e  mov     esi, 5Ch ; '\'
0x180044013  mov     r8d, esi; Size
0x180044016  lea     rcx, [rsp+0A8h+pv]; void *
0x18004401b  xor     edx, edx; Val
0x18004401d  call    memset
0x180044022  test    rdi, rdi
0x180044025  jnz     short loc_180044033
0x180044027  lea     ecx, [rsi-4Fh]; i
0x18004402a  call    cs:__imp_GetStockObject
0x180044030  mov     rdi, rax
0x180044033  lea     r8, [rsp+0A8h+pv]; pv
0x180044038  mov     edx, esi; c
0x18004403a  mov     rcx, rdi; h
0x18004403d  call    cs:__imp_GetObjectW
0x180044043  cmp     [rsp+0A8h+var_78], 2BCh
0x18004404b  mov     ecx, 320h
0x180044050  mov     eax, 3E8h
0x180044055  cmovge  ecx, eax
0x180044058  mov     [rsp+0A8h+var_78], ecx
0x18004405c  lea     rcx, [rsp+0A8h+pv]; lplf
0x180044061  call    cs:__imp_CreateFontIndirectW
0x180044067  mov     rsi, rax
0x18004406a  test    rax, rax
0x18004406d  jz      short loc_1800440BE
0x18004406f  mov     rcx, [rbx+690h]; ho
0x180044076  test    rcx, rcx
0x180044079  jz      short loc_180044081
0x18004407b  call    cs:__imp_DeleteObject
0x180044081  mov     rcx, rdi; h
0x180044084  mov     [rbx+688h], rdi
0x18004408b  mov     [rbx+690h], rsi
0x180044092  call    GetCodePageForFont
0x180044097  mov     rcx, rbx
0x18004409a  mov     [rbx+1Ch], eax
0x18004409d  call    MCCalcSizes
0x1800440a2  test    ebp, ebp
0x1800440a4  jz      short loc_1800440BE
0x1800440a6  mov     rcx, [rbx]; hWnd
0x1800440a9  xor     edx, edx; lpRect
0x1800440ab  lea     r8d, [rdx+1]; bErase
0x1800440af  call    cs:__imp_InvalidateRect
0x1800440b5  mov     rcx, [rbx]; hWnd
0x1800440b8  call    cs:__imp_UpdateWindow
0x1800440be  mov     rcx, [rsp+0A8h+var_28]
0x1800440c6  xor     rcx, rsp; StackCookie
0x1800440c9  call    __security_check_cookie
0x1800440ce  mov     rbx, [rsp+0A8h+arg_10]
0x1800440d6  add     rsp, 90h
0x1800440dd  pop     rdi
0x1800440de  pop     rsi
0x1800440df  pop     rbp
0x1800440e0  retn
```
