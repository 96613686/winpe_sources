# CAdvScheduleDlg::_EnableRepeatCtrls(int)

- ea: `0x1800185d8`
- end: `0x180018778`
- name: `?_EnableRepeatCtrls@CAdvScheduleDlg@@AEAAXH@Z`
- size: `416`
- prototype: `void(CAdvScheduleDlg *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180018780`
- `0x180018a14`

## callees

- `0x1800185d8`

## import_xrefs

- `USER32!SendMessageW` at `0x18001864d`
- `USER32!SendMessageW` at `0x1800186ed`
- `USER32!SendMessageW` at `0x18001864d`
- `USER32!SendMessageW` at `0x1800186ed`
- `USER32!EnableWindow` at `0x180018763`
- `USER32!EnableWindow` at `0x180018763`
- `USER32!GetDlgItem` at `0x180018630`
- `USER32!GetDlgItem` at `0x1800186d4`
- `USER32!GetDlgItem` at `0x180018753`
- `USER32!GetDlgItem` at `0x180018630`
- `USER32!GetDlgItem` at `0x1800186d4`
- `USER32!GetDlgItem` at `0x180018753`
- `USER32!SendDlgItemMessageW` at `0x1800186c5`
- `USER32!SendDlgItemMessageW` at `0x180018722`
- `USER32!SendDlgItemMessageW` at `0x180018740`
- `USER32!SendDlgItemMessageW` at `0x1800186c5`
- `USER32!SendDlgItemMessageW` at `0x180018722`
- `USER32!SendDlgItemMessageW` at `0x180018740`
- `USER32!SetDlgItemTextW` at `0x180018666`
- `USER32!SetDlgItemTextW` at `0x180018678`
- `USER32!SetDlgItemTextW` at `0x18001868a`
- `USER32!SetDlgItemTextW` at `0x18001869c`
- `USER32!SetDlgItemTextW` at `0x180018666`
- `USER32!SetDlgItemTextW` at `0x180018678`
- `USER32!SetDlgItemTextW` at `0x18001868a`
- `USER32!SetDlgItemTextW` at `0x18001869c`
- `USER32!CheckRadioButton` at `0x180018704`
- `USER32!CheckRadioButton` at `0x180018704`

## pseudocode

```c
void __fastcall CAdvScheduleDlg::_EnableRepeatCtrls(CAdvScheduleDlg *this, BOOL a2)
{
  HWND v4; // rcx
  int v5; // esi
  HWND v6; // rax
  HWND DlgItem; // rax
  int i; // ebx
  HWND v9; // rax
  __m128i nIDDlgItem; // [rsp+30h] [rbp-68h]
  __m128i v11; // [rsp+40h] [rbp-58h]
  __m128i si128; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+60h] [rbp-38h]
  int v14; // [rsp+64h] [rbp-34h]
  int v15; // [rsp+68h] [rbp-30h]

  v13 = 1789;
  v4 = (HWND)*((_QWORD *)this + 1);
  v14 = 1779;
  v15 = 1782;
  nIDDlgItem = _mm_load_si128((const __m128i *)&_xmm);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v11 = _mm_load_si128((const __m128i *)&_xmm);
  if ( a2 )
  {
    v5 = 14;
    SendDlgItemMessageW(v4, 1776, 0x467u, 0, 10);
    DlgItem = GetDlgItem(*((HWND *)this + 1), 1777);
    if ( DlgItem )
      SendMessageW(DlgItem, 0x14Eu, 0, 0);
    CheckRadioButton(*((HWND *)this + 1), 1780, 1781, 1781);
    SendDlgItemMessageW(*((HWND *)this + 1), 1784, 0x467u, 0, 1);
    SendDlgItemMessageW(*((HWND *)this + 1), 1786, 0x467u, 0, 0);
  }
  else
  {
    v5 = 15;
    v6 = GetDlgItem(v4, 1782);
    if ( v6 )
      SendMessageW(v6, 0x1032u, 0, (LPARAM)L" ");
    SetDlgItemTextW(*((HWND *)this + 1), 1775, &String);
    SetDlgItemTextW(*((HWND *)this + 1), 1783, &String);
    SetDlgItemTextW(*((HWND *)this + 1), 1785, &String);
    SetDlgItemTextW(*((HWND *)this + 1), 1777, &String);
  }
  for ( i = 0; i < v5; ++i )
  {
    v9 = GetDlgItem(*((HWND *)this + 1), nIDDlgItem.m128i_i32[i]);
    if ( v9 )
      EnableWindow(v9, a2);
  }
}

```

## disassembly

```asm
0x1800185d8  mov     rax, rsp
0x1800185db  push    rbx
0x1800185dc  push    rbp
0x1800185dd  push    rsi
0x1800185de  push    rdi
0x1800185df  sub     rsp, 78h
0x1800185e3  movdqa  xmm0, cs:__xmm@000006f1000006f0000006ef000006ff
0x1800185eb  mov     ebp, edx
0x1800185ed  movdqa  xmm1, cs:__xmm@000006f7000006f5000006f400000700
0x1800185f5  mov     edx, 6F6h; nIDDlgItem
0x1800185fa  mov     dword ptr [rax-38h], 6FDh
0x180018601  mov     rdi, rcx
0x180018604  mov     rcx, [rcx+8]; hDlg
0x180018608  mov     dword ptr [rax-34h], 6F3h
0x18001860f  mov     [rax-30h], edx
0x180018612  movdqu  xmmword ptr [rax-68h], xmm0
0x180018617  movdqa  xmm0, cs:__xmm@000006fa000006f9000006fc000006f8
0x18001861f  movdqu  xmmword ptr [rax-48h], xmm0
0x180018624  movdqu  xmmword ptr [rax-58h], xmm1
0x180018629  test    ebp, ebp
0x18001862b  jnz     short loc_1800186A7
0x18001862d  lea     esi, [rbp+0Fh]
0x180018630  call    cs:__imp_GetDlgItem
0x180018636  test    rax, rax
0x180018639  jz      short loc_180018653
0x18001863b  lea     r9, lParam; " "
0x180018642  xor     r8d, r8d; wParam
0x180018645  mov     edx, 1032h; Msg
0x18001864a  mov     rcx, rax; hWnd
0x18001864d  call    cs:__imp_SendMessageW
0x180018653  mov     rcx, [rdi+8]; hDlg
0x180018657  lea     rbx, String
0x18001865e  mov     r8, rbx; lpString
0x180018661  mov     edx, 6EFh; nIDDlgItem
0x180018666  call    cs:__imp_SetDlgItemTextW
0x18001866c  mov     rcx, [rdi+8]; hDlg
0x180018670  mov     r8, rbx; lpString
0x180018673  mov     edx, 6F7h; nIDDlgItem
0x180018678  call    cs:__imp_SetDlgItemTextW
0x18001867e  mov     rcx, [rdi+8]; hDlg
0x180018682  mov     r8, rbx; lpString
0x180018685  mov     edx, 6F9h; nIDDlgItem
0x18001868a  call    cs:__imp_SetDlgItemTextW
0x180018690  mov     rcx, [rdi+8]; hDlg
0x180018694  mov     r8, rbx; lpString
0x180018697  mov     edx, 6F1h; nIDDlgItem
0x18001869c  call    cs:__imp_SetDlgItemTextW
0x1800186a2  jmp     loc_180018746
0x1800186a7  mov     ebx, 467h
0x1800186ac  mov     [rsp+98h+lParam], 0Ah; lParam
0x1800186b5  mov     r8d, ebx; Msg
0x1800186b8  xor     r9d, r9d; wParam
0x1800186bb  mov     edx, 6F0h; nIDDlgItem
0x1800186c0  mov     esi, 0Eh
0x1800186c5  call    cs:__imp_SendDlgItemMessageW
0x1800186cb  mov     rcx, [rdi+8]; hDlg
0x1800186cf  mov     edx, 6F1h; nIDDlgItem
0x1800186d4  call    cs:__imp_GetDlgItem
0x1800186da  test    rax, rax
0x1800186dd  jz      short loc_1800186F3
0x1800186df  xor     r9d, r9d; lParam
0x1800186e2  xor     r8d, r8d; wParam
0x1800186e5  mov     edx, 14Eh; Msg
0x1800186ea  mov     rcx, rax; hWnd
0x1800186ed  call    cs:__imp_SendMessageW
0x1800186f3  mov     rcx, [rdi+8]; hDlg
0x1800186f7  mov     r8d, 6F5h; nIDLastButton
0x1800186fd  mov     r9d, r8d; nIDCheckButton
0x180018700  lea     edx, [r8-1]; nIDFirstButton
0x180018704  call    cs:__imp_CheckRadioButton
0x18001870a  mov     rcx, [rdi+8]; hDlg
0x18001870e  xor     r9d, r9d; wParam
0x180018711  mov     r8d, ebx; Msg
0x180018714  mov     [rsp+98h+lParam], 1; lParam
0x18001871d  mov     edx, 6F8h; nIDDlgItem
0x180018722  call    cs:__imp_SendDlgItemMessageW
0x180018728  mov     rcx, [rdi+8]; hDlg
0x18001872c  xor     r9d, r9d; wParam
0x18001872f  mov     r8d, ebx; Msg
0x180018732  mov     [rsp+98h+lParam], 0; lParam
0x18001873b  mov     edx, 6FAh; nIDDlgItem
0x180018740  call    cs:__imp_SendDlgItemMessageW
0x180018746  xor     ebx, ebx
0x180018748  mov     rcx, [rdi+8]; hDlg
0x18001874c  movsxd  rdx, ebx
0x18001874f  mov     edx, dword ptr [rsp+rdx*4+98h+nIDDlgItem]; nIDDlgItem
0x180018753  call    cs:__imp_GetDlgItem
0x180018759  test    rax, rax
0x18001875c  jz      short loc_180018769
0x18001875e  mov     edx, ebp; bEnable
0x180018760  mov     rcx, rax; hWnd
0x180018763  call    cs:__imp_EnableWindow
0x180018769  inc     ebx
0x18001876b  cmp     ebx, esi
0x18001876d  jl      short loc_180018748
0x18001876f  add     rsp, 78h
0x180018773  pop     rdi
0x180018774  pop     rsi
0x180018775  pop     rbp
0x180018776  pop     rbx
0x180018777  retn
```
