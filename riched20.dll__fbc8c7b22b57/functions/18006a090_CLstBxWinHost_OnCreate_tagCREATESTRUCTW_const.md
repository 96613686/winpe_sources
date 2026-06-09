# CLstBxWinHost::OnCreate(tagCREATESTRUCTW const *)

- ea: `0x18006a090`
- end: `0x18006a232`
- name: `?OnCreate@CLstBxWinHost@@UEAA_JPEBUtagCREATESTRUCTW@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180041200`
- `0x18006a090`
- `0x18006ba88`
- `0x18006d550`
- `0x18006ddb0`
- `0x1800932f4`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!SetScrollRange` at `0x18006a176`
- `USER32!SetScrollRange` at `0x18006a192`
- `USER32!SetScrollRange` at `0x18006a176`
- `USER32!SetScrollRange` at `0x18006a192`

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
0x18006a090  mov     [rsp+arg_10], rbx
0x18006a095  push    rsi
0x18006a096  push    rdi
0x18006a097  push    r14
0x18006a099  sub     rsp, 50h
0x18006a09d  mov     rax, cs:__security_cookie
0x18006a0a4  xor     rax, rsp
0x18006a0a7  mov     [rsp+68h+var_28], rax
0x18006a0ac  mov     r8d, [rdx+28h]
0x18006a0b0  xor     eax, eax
0x18006a0b2  cmp     [rdx+20h], eax
0x18006a0b5  mov     rdi, rcx
0x18006a0b8  mov     ecx, [rdx+2Ch]
0x18006a0bb  mov     rbx, rdx
0x18006a0be  cmovge  eax, [rdx+20h]
0x18006a0c2  add     eax, r8d
0x18006a0c5  mov     [rsp+68h+var_38], ecx
0x18006a0c9  mov     [rsp+68h+var_2C], eax
0x18006a0cd  xor     eax, eax
0x18006a0cf  cmp     [rdx+24h], eax
0x18006a0d2  mov     [rsp+68h+var_34], r8d
0x18006a0d7  cmovge  eax, [rdx+24h]
0x18006a0db  mov     edx, 0FFFFFFF0h; int
0x18006a0e0  add     eax, ecx
0x18006a0e2  mov     rcx, [rdi+10h]; HWND
0x18006a0e6  mov     [rsp+68h+var_30], eax
0x18006a0ea  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x18006a0ef  mov     rcx, rdi; this
0x18006a0f2  mov     esi, eax
0x18006a0f4  call    ?UpdateSysColors@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::UpdateSysColors(void)
0x18006a0f9  mov     eax, [rbx+10h]
0x18006a0fc  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006a100  and     dword ptr [rdi+80h], 0FFFFFDBFh
0x18006a10a  and     dword ptr [rdi+34h], 0FFFF8FFFh
0x18006a111  bts     dword ptr [rdi+80h], 0Bh
0x18006a119  mov     rcx, [rdi+10h]; hWnd
0x18006a11d  lea     ebx, [r14+2]
0x18006a121  mov     [rdi+90h], eax
0x18006a127  xor     eax, eax
0x18006a129  mov     [rdi+0B8h], ebx
0x18006a12f  mov     [rdi+0B4h], ebx
0x18006a135  mov     [rdi+0C8h], r14d
0x18006a13c  mov     [rdi+0C4h], r14d
0x18006a143  mov     [rdi+0CCh], r14d
0x18006a14a  mov     dword ptr [rdi+7Ch], 0
0x18006a151  mov     [rdi+0D0h], r14d
0x18006a158  mov     [rdi+78h], ax
0x18006a15c  test    rcx, rcx
0x18006a15f  jz      short loc_18006A1B0
0x18006a161  test    byte ptr [rdi+80h], 8
0x18006a168  jnz     short loc_18006A1B0
0x18006a16a  xor     r9d, r9d; nMaxPos
0x18006a16d  mov     [rsp+68h+bRedraw], ebx; bRedraw
0x18006a171  xor     r8d, r8d; nMinPos
0x18006a174  mov     edx, ebx; nBar
0x18006a176  call    cs:__imp_SetScrollRange
0x18006a17d  nop     dword ptr [rax+rax+00h]
0x18006a182  mov     rcx, [rdi+10h]; hWnd
0x18006a186  xor     r9d, r9d; nMaxPos
0x18006a189  xor     r8d, r8d; nMinPos
0x18006a18c  mov     [rsp+68h+bRedraw], ebx; bRedraw
0x18006a190  xor     edx, edx; nBar
0x18006a192  call    cs:__imp_SetScrollRange
0x18006a199  nop     dword ptr [rax+rax+00h]
0x18006a19e  mov     rcx, [rdi+10h]; HWND
0x18006a1a2  and     esi, 0FFCFFFFFh
0x18006a1a8  mov     r8d, esi; int
0x18006a1ab  call    ?SetWindowLong@CW32System@@SAJPEAUHWND__@@HJ@Z; CW32System::SetWindowLong(HWND__ *,int,long)
0x18006a1b0  mov     rcx, [rdi+20h]
0x18006a1b4  mov     rdx, [rcx]
0x18006a1b7  mov     rax, [rdx+48h]
0x18006a1bb  lea     rdx, [rsp+68h+var_38]
0x18006a1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1c5  test    eax, eax
0x18006a1c7  jns     short loc_18006A1CE
0x18006a1c9  mov     rax, r14
0x18006a1cc  jmp     short loc_18006A213
0x18006a1ce  mov     rcx, rdi; this
0x18006a1d1  call    ?ResizeInset@CLstBxWinHost@@QEAAXXZ; CLstBxWinHost::ResizeInset(void)
0x18006a1d6  mov     rcx, [rdi+20h]
0x18006a1da  xor     r9d, r9d
0x18006a1dd  mov     r8, rbx
0x18006a1e0  mov     qword ptr [rsp+68h+bRedraw], 0
0x18006a1e9  mov     edx, 43Fh
0x18006a1ee  mov     rax, [rcx]
0x18006a1f1  mov     rax, [rax+18h]
0x18006a1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1fa  mov     rcx, rdi; this
0x18006a1fd  call    ?SetListIndent@CLstBxWinHost@@QEAAHH@Z; CLstBxWinHost::SetListIndent(int)
0x18006a202  btr     dword ptr [rdi+80h], 0Bh
0x18006a20a  xor     eax, eax
0x18006a20c  mov     dword ptr [rdi+50h], 80000h
0x18006a213  mov     rcx, [rsp+68h+var_28]
0x18006a218  xor     rcx, rsp; StackCookie
0x18006a21b  call    __security_check_cookie
0x18006a220  mov     rbx, [rsp+68h+arg_10]
0x18006a228  add     rsp, 50h
0x18006a22c  pop     r14
0x18006a22e  pop     rdi
0x18006a22f  pop     rsi
0x18006a230  retn
```
