# Edit_ImmSetCompositionWindow(tagED *,long,long)

- ea: `0x18005d8bc`
- end: `0x18005da1e`
- name: `?Edit_ImmSetCompositionWindow@@YAXPEAUtagED@@JJ@Z`
- size: `354`
- prototype: `void __fastcall(struct tagED *, int, int)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180057158`
- `0x180059720`
- `0x18005d448`
- `0x18005d728`
- `0x1800c2ee8`
- `0x1800f2e80`
- `0x18013b924`

## callees

- `0x18005d8bc`
- `0x180114520`
- `0x1801d0c3c`

## import_xrefs

- `USER32!SetRectEmpty` at `0x18005d965`
- `USER32!SetRectEmpty` at `0x18005d965`
- `USER32!MapWindowPoints` at `0x18005d93d`
- `USER32!MapWindowPoints` at `0x18005d93d`
- `USER32!GetWindowRect` at `0x18005d927`
- `USER32!GetWindowRect` at `0x18005d927`
- `USER32!SendMessageW` at `0x18005da09`
- `USER32!SendMessageW` at `0x18005da09`
- `IMM32!ImmGetContext` at `0x18005d903`
- `IMM32!ImmGetContext` at `0x18005d903`
- `IMM32!ImmReleaseContext` at `0x18005d9b5`
- `IMM32!ImmReleaseContext` at `0x18005d9b5`
- `IMM32!ImmGetCompositionWindow` at `0x18005d972`
- `IMM32!ImmGetCompositionWindow` at `0x18005d972`
- `IMM32!ImmSetCompositionWindow` at `0x18005d9a8`
- `IMM32!ImmSetCompositionWindow` at `0x18005d9a8`

## pseudocode

```c
void __fastcall Edit_ImmSetCompositionWindow(struct tagED *a1, LONG a2, LONG a3)
{
  HWND v4; // rcx
  HIMC Context; // rdi
  bool v8; // zf
  int v9; // eax
  LONG top; // ecx
  RECT v11; // xmm0
  int v12; // eax
  struct tagCOMPOSITIONFORM rc; // [rsp+20h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-40h] BYREF
  tagCOMPOSITIONFORM CompForm; // [rsp+50h] [rbp-30h] BYREF

  v4 = (HWND)*((_QWORD *)a1 + 8);
  memset(&rc, 0, sizeof(rc));
  memset(&CompForm, 0, sizeof(CompForm));
  Rect = 0;
  Context = ImmGetContext(v4);
  if ( Context )
  {
    if ( (*((_BYTE *)a1 + 116) & 8) != 0 )
    {
      GetWindowRect(*((HWND *)a1 + 8), &Rect);
      MapWindowPoints(*((HWND *)a1 + 8), 0, (LPPOINT)&Rect, 2u);
      if ( (*((_BYTE *)a1 + 120) & 0x20) != 0 )
      {
        v12 = SendMessageW(*((HWND *)a1 + 8), 0xD6u, *((unsigned int *)a1 + 6), 0);
        a2 = (__int16)v12;
        a3 = SHIWORD(v12);
      }
      v8 = (*((_BYTE *)a1 + 116) & 1) == 0;
      rc.ptCurrentPos.x = a2;
      rc.ptCurrentPos.y = a3;
      if ( v8 )
      {
        v11 = (RECT)*((_OWORD *)a1 + 5);
        rc.dwStyle = 1;
        rc.rcArea = v11;
      }
      else
      {
        rc.dwStyle = 2;
        SetRectEmpty(&rc.rcArea);
      }
      ImmGetCompositionWindow(Context, &CompForm);
      v9 = memcmp_0(&rc, &CompForm, 0x1Cu);
      top = Rect.top;
      if ( v9 || *((_DWORD *)a1 + 88) != Rect.left || *((_DWORD *)a1 + 89) != Rect.top )
      {
        *((_DWORD *)a1 + 88) = Rect.left;
        *((_DWORD *)a1 + 89) = top;
        ImmSetCompositionWindow(Context, &rc);
      }
    }
    ImmReleaseContext(*((HWND *)a1 + 8), Context);
  }
}

```

## disassembly

```asm
0x18005d8bc  push    rbp
0x18005d8be  push    rbx
0x18005d8bf  push    rsi
0x18005d8c0  push    rdi
0x18005d8c1  push    r14
0x18005d8c3  mov     rbp, rsp
0x18005d8c6  sub     rsp, 80h
0x18005d8cd  mov     rax, cs:__security_cookie
0x18005d8d4  xor     rax, rsp
0x18005d8d7  mov     [rbp+var_10], rax
0x18005d8db  xorps   xmm0, xmm0
0x18005d8de  xorps   xmm1, xmm1
0x18005d8e1  mov     rbx, rcx
0x18005d8e4  xor     eax, eax
0x18005d8e6  mov     rcx, [rcx+40h]; HWND
0x18005d8ea  mov     r14d, r8d
0x18005d8ed  movups  xmmword ptr [rbp+rc.left], xmm0
0x18005d8f1  mov     esi, edx
0x18005d8f3  movups  xmmword ptr [rbp+CompForm.dwStyle], xmm1
0x18005d8f7  movups  xmmword ptr [rbp+rc.bottom], xmm0
0x18005d8fb  movups  xmmword ptr [rbp+CompForm.rcArea.left], xmm1
0x18005d8ff  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18005d903  call    cs:__imp_ImmGetContext
0x18005d909  mov     rdi, rax
0x18005d90c  test    rax, rax
0x18005d90f  jz      loc_18005D9BB
0x18005d915  test    byte ptr [rbx+74h], 8
0x18005d919  jz      loc_18005D9AE
0x18005d91f  mov     rcx, [rbx+40h]; hWnd
0x18005d923  lea     rdx, [rbp+Rect]; lpRect
0x18005d927  call    cs:__imp_GetWindowRect
0x18005d92d  mov     rcx, [rbx+40h]; hWndFrom
0x18005d931  lea     r8, [rbp+Rect]; lpPoints
0x18005d935  mov     r9d, 2; cPoints
0x18005d93b  xor     edx, edx; hWndTo
0x18005d93d  call    cs:__imp_MapWindowPoints
0x18005d943  test    byte ptr [rbx+78h], 20h
0x18005d947  jnz     loc_18005D9F9
0x18005d94d  test    byte ptr [rbx+74h], 1
0x18005d951  mov     [rbp+rc.top], esi
0x18005d954  mov     [rbp+rc.right], r14d
0x18005d958  jz      short loc_18005D9D5
0x18005d95a  lea     rcx, [rbp+rc.bottom]; lprc
0x18005d95e  mov     [rbp+rc.left], 2
0x18005d965  call    cs:__imp_SetRectEmpty
0x18005d96b  lea     rdx, [rbp+CompForm]; lpCompForm
0x18005d96f  mov     rcx, rdi; HIMC
0x18005d972  call    cs:__imp_ImmGetCompositionWindow
0x18005d978  mov     r8d, 1Ch; Size
0x18005d97e  lea     rdx, [rbp+CompForm]; Buf2
0x18005d982  lea     rcx, [rbp+rc]; Buf1
0x18005d986  call    memcmp_0
0x18005d98b  mov     ecx, [rbp+Rect.top]
0x18005d98e  mov     edx, [rbp+Rect.left]
0x18005d991  test    eax, eax
0x18005d993  jz      short loc_18005D9E7
0x18005d995  mov     [rbx+160h], edx
0x18005d99b  lea     rdx, [rbp+rc]; lpCompForm
0x18005d99f  mov     [rbx+164h], ecx
0x18005d9a5  mov     rcx, rdi; HIMC
0x18005d9a8  call    cs:__imp_ImmSetCompositionWindow
0x18005d9ae  mov     rcx, [rbx+40h]; HWND
0x18005d9b2  mov     rdx, rdi; HIMC
0x18005d9b5  call    cs:__imp_ImmReleaseContext
0x18005d9bb  mov     rcx, [rbp+var_10]
0x18005d9bf  xor     rcx, rsp; StackCookie
0x18005d9c2  call    __security_check_cookie
0x18005d9c7  add     rsp, 80h
0x18005d9ce  pop     r14
0x18005d9d0  pop     rdi
0x18005d9d1  pop     rsi
0x18005d9d2  pop     rbx
0x18005d9d3  pop     rbp
0x18005d9d4  retn
0x18005d9d5  movups  xmm0, xmmword ptr [rbx+50h]
0x18005d9d9  mov     [rbp+rc.left], 1
0x18005d9e0  movdqu  xmmword ptr [rbp+rc.bottom], xmm0
0x18005d9e5  jmp     short loc_18005D96B
0x18005d9e7  cmp     [rbx+160h], edx
0x18005d9ed  jnz     short loc_18005D995
0x18005d9ef  cmp     [rbx+164h], ecx
0x18005d9f5  jz      short loc_18005D9AE
0x18005d9f7  jmp     short loc_18005D995
0x18005d9f9  mov     r8d, [rbx+18h]; wParam
0x18005d9fd  xor     r9d, r9d; lParam
0x18005da00  mov     rcx, [rbx+40h]; hWnd
0x18005da04  mov     edx, 0D6h; Msg
0x18005da09  call    cs:__imp_SendMessageW
0x18005da0f  movsx   esi, ax
0x18005da12  shr     eax, 10h
0x18005da15  movsx   r14d, ax
0x18005da19  jmp     loc_18005D94D
```
