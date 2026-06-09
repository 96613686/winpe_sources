# CUIFWindow::AnimateShow(int)

- ea: `0x1801041b0`
- end: `0x18010433f`
- name: `?AnimateShow@CUIFWindow@@UEAAXH@Z`
- size: `399`
- prototype: `void __fastcall(CUIFWindow *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1801041b0`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `USER32!GetMessagePos` at `0x1801042ae`
- `USER32!GetMessagePos` at `0x1801042ae`
- `USER32!SetWindowPos` at `0x180104228`
- `USER32!SetWindowPos` at `0x180104228`
- `USER32!GetWindowRect` at `0x1801042a8`
- `USER32!GetWindowRect` at `0x1801042a8`
- `USER32!AnimateWindow` at `0x1801042fc`
- `USER32!AnimateWindow` at `0x1801042fc`
- `USER32!SystemParametersInfoW` at `0x18010423d`
- `USER32!SystemParametersInfoW` at `0x180104265`
- `USER32!SystemParametersInfoW` at `0x18010423d`
- `USER32!SystemParametersInfoW` at `0x180104265`
- `USER32!IsWindow` at `0x1801041e3`
- `USER32!IsWindow` at `0x1801041e3`

## pseudocode

```c
void __fastcall CUIFWindow::AnimateShow(HWND *this, unsigned int a2)
{
  HWND v4; // rcx
  DWORD v5; // r8d
  int v6; // ecx
  int v7; // r8d
  int pvParam; // [rsp+40h] [rbp-28h] BYREF
  int v9; // [rsp+44h] [rbp-24h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-20h] BYREF

  pvParam = 1;
  if ( IsWindow(this[21]) )
  {
    if ( a2 && (*((_BYTE *)this + 84) & 2) != 0 )
      SetWindowPos(this[21], 0, 0, 0, 0, 0, 0x213u);
    SystemParametersInfoW(0x1016u, 0, &pvParam, 0);
    if ( pvParam )
    {
      v9 = 0;
      SystemParametersInfoW(0x1018u, 0, &v9, 0);
      if ( a2 )
        *((_DWORD *)this + 27) = 1;
      v4 = this[21];
      if ( v9 )
      {
        v5 = a2 != 0 ? 0x80000 : 589824;
      }
      else
      {
        Rect = 0;
        GetWindowRect(v4, &Rect);
        v6 = (__int16)(GetMessagePos() >> 16);
        v7 = 8;
        if ( v6 <= Rect.top + (Rect.bottom - Rect.top) / 2 )
          v7 = 4;
        v5 = (a2 != 0 ? 0x40000 : 327680) | v7;
        v4 = this[21];
      }
      AnimateWindow(v4, 0x87u, v5);
      if ( !a2 )
        *((_DWORD *)this + 27) = 0;
    }
    else
    {
      (*((void (__fastcall **)(HWND *, _QWORD))*this + 37))(this, a2);
    }
  }
}

```

## disassembly

```asm
0x1801041b0  mov     [rsp+arg_10], rbx
0x1801041b5  mov     [rsp+arg_18], rdi
0x1801041ba  push    r14
0x1801041bc  sub     rsp, 60h
0x1801041c0  mov     rax, cs:__security_cookie
0x1801041c7  xor     rax, rsp
0x1801041ca  mov     [rsp+68h+var_10], rax
0x1801041cf  mov     rbx, rcx
0x1801041d2  mov     [rsp+68h+pvParam], 1
0x1801041da  mov     rcx, [rcx+0A8h]; hWnd
0x1801041e1  mov     edi, edx
0x1801041e3  call    cs:__imp_IsWindow
0x1801041e9  test    eax, eax
0x1801041eb  jz      loc_18010431F
0x1801041f1  mov     r14d, 2
0x1801041f7  test    edi, edi
0x1801041f9  jz      short loc_18010422E
0x1801041fb  test    [rbx+54h], r14b
0x1801041ff  jz      short loc_18010422E
0x180104201  mov     rcx, [rbx+0A8h]; hWnd
0x180104208  xor     r9d, r9d; Y
0x18010420b  mov     [rsp+68h+uFlags], 213h; uFlags
0x180104213  xor     r8d, r8d; X
0x180104216  mov     [rsp+68h+cy], 0; cy
0x18010421e  xor     edx, edx; hWndInsertAfter
0x180104220  mov     [rsp+68h+var_48], 0; cx
0x180104228  call    cs:__imp_SetWindowPos
0x18010422e  xor     r9d, r9d; fWinIni
0x180104231  lea     r8, [rsp+68h+pvParam]; pvParam
0x180104236  xor     edx, edx; uiParam
0x180104238  mov     ecx, 1016h; uiAction
0x18010423d  call    cs:__imp_SystemParametersInfoW
0x180104243  cmp     [rsp+68h+pvParam], 0
0x180104248  jz      loc_18010430B
0x18010424e  xor     r9d, r9d; fWinIni
0x180104251  mov     [rsp+68h+var_24], 0
0x180104259  lea     r8, [rsp+68h+var_24]; pvParam
0x18010425e  xor     edx, edx; uiParam
0x180104260  mov     ecx, 1018h; uiAction
0x180104265  call    cs:__imp_SystemParametersInfoW
0x18010426b  test    edi, edi
0x18010426d  jz      short loc_180104276
0x18010426f  mov     dword ptr [rbx+6Ch], 1
0x180104276  cmp     [rsp+68h+var_24], 0
0x18010427b  mov     rcx, [rbx+0A8h]; hWnd
0x180104282  jz      short loc_18010429B
0x180104284  mov     eax, edi
0x180104286  neg     eax
0x180104288  sbb     r8d, r8d
0x18010428b  and     r8d, 0FFFF0000h
0x180104292  add     r8d, 90000h
0x180104299  jmp     short loc_1801042F7
0x18010429b  xorps   xmm0, xmm0
0x18010429e  lea     rdx, [rsp+68h+Rect]; lpRect
0x1801042a3  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1801042a8  call    cs:__imp_GetWindowRect
0x1801042ae  call    cs:__imp_GetMessagePos
0x1801042b4  mov     ecx, eax
0x1801042b6  mov     eax, [rsp+68h+Rect.bottom]
0x1801042ba  sub     eax, [rsp+68h+Rect.top]
0x1801042be  shr     ecx, 10h
0x1801042c1  cdq
0x1801042c2  idiv    r14d
0x1801042c5  movsx   ecx, cx
0x1801042c8  mov     edx, 4
0x1801042cd  add     eax, [rsp+68h+Rect.top]
0x1801042d1  cmp     ecx, eax
0x1801042d3  mov     eax, edi
0x1801042d5  lea     r8d, [rdx+4]
0x1801042d9  cmovle  r8d, edx
0x1801042dd  neg     eax
0x1801042df  sbb     ecx, ecx
0x1801042e1  and     ecx, 0FFFF0000h
0x1801042e7  add     ecx, 50000h
0x1801042ed  or      r8d, ecx; dwFlags
0x1801042f0  mov     rcx, [rbx+0A8h]; hWnd
0x1801042f7  mov     edx, 87h; dwTime
0x1801042fc  call    cs:__imp_AnimateWindow
0x180104302  test    edi, edi
0x180104304  jnz     short loc_18010431F
0x180104306  mov     [rbx+6Ch], edi
0x180104309  jmp     short loc_18010431F
0x18010430b  mov     rax, [rbx]
0x18010430e  mov     edx, edi
0x180104310  mov     rcx, rbx
0x180104313  mov     rax, [rax+128h]
0x18010431a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010431f  mov     rcx, [rsp+68h+var_10]
0x180104324  xor     rcx, rsp; StackCookie
0x180104327  call    __security_check_cookie
0x18010432c  lea     r11, [rsp+68h+var_8]
0x180104331  mov     rbx, [r11+20h]
0x180104335  mov     rdi, [r11+28h]
0x180104339  mov     rsp, r11
0x18010433c  pop     r14
0x18010433e  retn
```
