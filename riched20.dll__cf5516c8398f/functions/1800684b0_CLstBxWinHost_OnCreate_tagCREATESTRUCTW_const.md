# CLstBxWinHost::OnCreate(tagCREATESTRUCTW const *)

- ea: `0x1800684b0`
- end: `0x180068645`
- name: `?OnCreate@CLstBxWinHost@@UEAA_JPEBUtagCREATESTRUCTW@@@Z`
- size: `405`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1800404ac`
- `0x1800684b0`
- `0x180069e28`
- `0x18006b898`
- `0x18006c0cc`
- `0x1800908dc`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!SetScrollRange` at `0x180068596`
- `USER32!SetScrollRange` at `0x1800685ac`
- `USER32!SetScrollRange` at `0x180068596`
- `USER32!SetScrollRange` at `0x1800685ac`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::OnCreate(CLstBxWinHost *this, const struct tagCREATESTRUCTW *a2)
{
  int y; // r8d
  int cy; // eax
  int x; // ecx
  int cx; // eax
  bool v8; // sf
  int v9; // eax
  HWND v10; // rcx
  int WindowLong; // esi
  int hMenu; // eax
  HWND v13; // rcx
  int v14; // edx
  __int64 result; // rax
  int v16; // edx
  _DWORD v17[4]; // [rsp+30h] [rbp-38h] BYREF

  y = a2->y;
  cy = 0;
  x = a2->x;
  if ( a2->cy >= 0 )
    cy = a2->cy;
  v17[0] = a2->x;
  v17[3] = y + cy;
  cx = 0;
  v8 = a2->cx < 0;
  v17[1] = y;
  if ( !v8 )
    cx = a2->cx;
  v9 = x + cx;
  v10 = (HWND)*((_QWORD *)this + 2);
  v17[2] = v9;
  WindowLong = CW32System::GetWindowLong(v10, -16);
  CLstBxWinHost::UpdateSysColors(this);
  hMenu = (int)a2->hMenu;
  *((_DWORD *)this + 32) &= 0xFFFFFDBF;
  *((_DWORD *)this + 13) &= 0xFFFF8FFF;
  *((_DWORD *)this + 32) |= 0x800u;
  v13 = (HWND)*((_QWORD *)this + 2);
  *((_DWORD *)this + 36) = hMenu;
  *((_DWORD *)this + 46) = 1;
  *((_DWORD *)this + 45) = 1;
  *((_DWORD *)this + 50) = -1;
  *((_DWORD *)this + 49) = -1;
  *((_DWORD *)this + 51) = -1;
  *((_DWORD *)this + 31) = 0;
  *((_DWORD *)this + 52) = -1;
  *((_WORD *)this + 60) = 0;
  if ( v13 && (*((_BYTE *)this + 128) & 8) == 0 )
  {
    SetScrollRange(v13, 1, 0, 0, 1);
    SetScrollRange(*((HWND *)this + 2), 0, 0, 0, 1);
    CW32System::SetWindowLong(*((HWND *)this + 2), v14, WindowLong & 0xFFCFFFFF);
  }
  if ( (*(int (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 4) + 72LL))(*((_QWORD *)this + 4), v17) < 0 )
    return -1;
  CLstBxWinHost::ResizeInset(this);
  (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 24LL))(
    *((_QWORD *)this + 4),
    1087,
    1,
    0,
    0);
  CLstBxWinHost::SetListIndent(this, v16);
  *((_DWORD *)this + 32) &= ~0x800u;
  result = 0;
  *((_DWORD *)this + 20) = 0x80000;
  return result;
}

```

## disassembly

```asm
0x1800684b0  mov     [rsp+arg_10], rbx
0x1800684b5  push    rsi
0x1800684b6  push    rdi
0x1800684b7  push    r14
0x1800684b9  sub     rsp, 50h
0x1800684bd  mov     rax, cs:__security_cookie
0x1800684c4  xor     rax, rsp
0x1800684c7  mov     [rsp+68h+var_28], rax
0x1800684cc  mov     r8d, [rdx+28h]
0x1800684d0  xor     eax, eax
0x1800684d2  cmp     [rdx+20h], eax
0x1800684d5  mov     rdi, rcx
0x1800684d8  mov     ecx, [rdx+2Ch]
0x1800684db  mov     rbx, rdx
0x1800684de  cmovge  eax, [rdx+20h]
0x1800684e2  add     eax, r8d
0x1800684e5  mov     [rsp+68h+var_38], ecx
0x1800684e9  mov     [rsp+68h+var_2C], eax
0x1800684ed  xor     eax, eax
0x1800684ef  cmp     [rdx+24h], eax
0x1800684f2  mov     [rsp+68h+var_34], r8d
0x1800684f7  cmovge  eax, [rdx+24h]
0x1800684fb  mov     edx, 0FFFFFFF0h; int
0x180068500  add     eax, ecx
0x180068502  mov     rcx, [rdi+10h]; HWND
0x180068506  mov     [rsp+68h+var_30], eax
0x18006850a  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x18006850f  mov     rcx, rdi; this
0x180068512  mov     esi, eax
0x180068514  call    ?UpdateSysColors@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::UpdateSysColors(void)
0x180068519  mov     eax, [rbx+10h]
0x18006851c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180068520  and     dword ptr [rdi+80h], 0FFFFFDBFh
0x18006852a  and     dword ptr [rdi+34h], 0FFFF8FFFh
0x180068531  bts     dword ptr [rdi+80h], 0Bh
0x180068539  mov     rcx, [rdi+10h]; hWnd
0x18006853d  lea     ebx, [r14+2]
0x180068541  mov     [rdi+90h], eax
0x180068547  xor     eax, eax
0x180068549  mov     [rdi+0B8h], ebx
0x18006854f  mov     [rdi+0B4h], ebx
0x180068555  mov     [rdi+0C8h], r14d
0x18006855c  mov     [rdi+0C4h], r14d
0x180068563  mov     [rdi+0CCh], r14d
0x18006856a  mov     dword ptr [rdi+7Ch], 0
0x180068571  mov     [rdi+0D0h], r14d
0x180068578  mov     [rdi+78h], ax
0x18006857c  test    rcx, rcx
0x18006857f  jz      short loc_1800685C4
0x180068581  test    byte ptr [rdi+80h], 8
0x180068588  jnz     short loc_1800685C4
0x18006858a  xor     r9d, r9d; nMaxPos
0x18006858d  mov     [rsp+68h+bRedraw], ebx; bRedraw
0x180068591  xor     r8d, r8d; nMinPos
0x180068594  mov     edx, ebx; nBar
0x180068596  call    cs:__imp_SetScrollRange
0x18006859c  mov     rcx, [rdi+10h]; hWnd
0x1800685a0  xor     r9d, r9d; nMaxPos
0x1800685a3  xor     r8d, r8d; nMinPos
0x1800685a6  mov     [rsp+68h+bRedraw], ebx; bRedraw
0x1800685aa  xor     edx, edx; nBar
0x1800685ac  call    cs:__imp_SetScrollRange
0x1800685b2  mov     rcx, [rdi+10h]; HWND
0x1800685b6  and     esi, 0FFCFFFFFh
0x1800685bc  mov     r8d, esi; int
0x1800685bf  call    ?SetWindowLong@CW32System@@SAJPEAUHWND__@@HJ@Z; CW32System::SetWindowLong(HWND__ *,int,long)
0x1800685c4  mov     rcx, [rdi+20h]
0x1800685c8  mov     rdx, [rcx]
0x1800685cb  mov     rax, [rdx+48h]
0x1800685cf  lea     rdx, [rsp+68h+var_38]
0x1800685d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800685d9  test    eax, eax
0x1800685db  jns     short loc_1800685E2
0x1800685dd  mov     rax, r14
0x1800685e0  jmp     short loc_180068627
0x1800685e2  mov     rcx, rdi; this
0x1800685e5  call    ?ResizeInset@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::ResizeInset(void)
0x1800685ea  mov     rcx, [rdi+20h]
0x1800685ee  xor     r9d, r9d
0x1800685f1  mov     r8, rbx
0x1800685f4  mov     qword ptr [rsp+68h+bRedraw], 0
0x1800685fd  mov     edx, 43Fh
0x180068602  mov     rax, [rcx]
0x180068605  mov     rax, [rax+18h]
0x180068609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006860e  mov     rcx, rdi; this
0x180068611  call    ?SetListIndent@CLstBxWinHost@@QEAAHH@Z; CLstBxWinHost::SetListIndent(int)
0x180068616  btr     dword ptr [rdi+80h], 0Bh
0x18006861e  xor     eax, eax
0x180068620  mov     dword ptr [rdi+50h], 80000h
0x180068627  mov     rcx, [rsp+68h+var_28]
0x18006862c  xor     rcx, rsp; StackCookie
0x18006862f  call    __security_check_cookie
0x180068634  mov     rbx, [rsp+68h+arg_10]
0x18006863c  add     rsp, 50h
0x180068640  pop     r14
0x180068642  pop     rdi
0x180068643  pop     rsi
0x180068644  retn
```
