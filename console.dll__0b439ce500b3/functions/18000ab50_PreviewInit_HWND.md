# PreviewInit(HWND__ *)

- ea: `0x18000ab50`
- end: `0x18000ac5f`
- name: `?PreviewInit@@YAHPEAUHWND__@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009980`

## callees

- `0x180005e60`
- `0x180009578`
- `0x18000ab50`
- `0x18000b020`
- `0x18000b254`

## import_xrefs

- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000ac33`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000ac33`

## string_xrefs

- `0x18000ab97`: `onecore\windows\core\console\open\src\propsheet\fontdlg.cpp`

## pseudocode

```c
__int64 __fastcall PreviewInit(HWND hWnd)
{
  unsigned int Font; // eax
  const char *v3; // r9
  __int64 v4; // rbx
  unsigned int v5; // edi
  _DWORD *v6; // r8
  struct _CONSOLE_STATE_INFO *v7; // rcx
  WCHAR *lParam; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Font = FindCreateFont(
           *((_DWORD *)gpStateInfo + 5),
           (wchar_t *)gpStateInfo + 14,
           *(struct _COORD *)((char *)gpStateInfo + 16),
           *((_DWORD *)gpStateInfo + 6),
           *((_DWORD *)gpStateInfo + 52));
  v4 = (int)Font;
  if ( Font >= NumberOfFonts )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x5DA,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\fontdlg.cpp",
      v3);
  v5 = 0;
  g_currentFontIndex = Font;
  if ( g_fHostedInFileProperties )
  {
    v6 = FontInfo;
    v7 = gpStateInfo;
    *((_DWORD *)gpStateInfo + 5) = *((unsigned __int8 *)FontInfo + 40 * Font + 32);
    *((_DWORD *)v7 + 4) = v6[10 * Font + 2];
    *((_DWORD *)v7 + 6) = v6[10 * Font + 4];
    StringCchCopyW((wchar_t *)v7 + 14, 0x20u, *(const wchar_t **)&v6[10 * Font + 6]);
  }
  if ( (*((_BYTE *)FontInfo + 40 * v4 + 32) & 4) != 0 )
  {
    lParam = (WCHAR *)*((_QWORD *)FontInfo + 5 * v4 + 3);
  }
  else
  {
    v5 = 1;
    lParam = &wszRasterFonts;
  }
  SendDlgItemMessageW(hWnd, 202, 0x18Cu, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
  SelectCurrentSize(hWnd, v5, v4);
  return v5;
}

```

## disassembly

```asm
0x18000ab50  mov     [rsp+arg_0], rbx
0x18000ab55  mov     [rsp+arg_8], rsi
0x18000ab5a  push    rdi
0x18000ab5b  sub     rsp, 30h
0x18000ab5f  mov     rsi, rcx
0x18000ab62  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000ab69  mov     eax, [rcx+0D0h]
0x18000ab6f  lea     rdx, [rcx+1Ch]; wchar_t *
0x18000ab73  mov     r9d, [rcx+18h]; int
0x18000ab77  mov     r8d, [rcx+10h]; struct _COORD
0x18000ab7b  mov     ecx, [rcx+14h]; unsigned int
0x18000ab7e  mov     dword ptr [rsp+38h+lParam], eax; unsigned int
0x18000ab82  call    ?FindCreateFont@@YAHKPEA_WU_COORD@@JI@Z; FindCreateFont(ulong,wchar_t *,_COORD,long,uint)
0x18000ab87  movsxd  rbx, eax
0x18000ab8a  cmp     ebx, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000ab90  jb      short loc_18000ABA9
0x18000ab92  mov     rcx, [rsp+38h]; this
0x18000ab97  lea     r8, aOnecoreWindows_2; "onecore\\windows\\core\\console\\open\\"...
0x18000ab9e  mov     edx, 5DAh; void *
0x18000aba3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000aba9  xor     edi, edi
0x18000abab  mov     cs:?g_currentFontIndex@@3KA, ebx; ulong g_currentFontIndex
0x18000abb1  cmp     cs:?g_fHostedInFileProperties@@3HA, edi; int g_fHostedInFileProperties
0x18000abb7  jz      short loc_18000ABF7
0x18000abb9  mov     r8, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000abc0  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000abc7  mov     eax, ebx
0x18000abc9  lea     rdx, [rax+rax*4]
0x18000abcd  movzx   eax, byte ptr [r8+rdx*8+20h]
0x18000abd3  mov     [rcx+14h], eax
0x18000abd6  mov     eax, [r8+rdx*8+8]
0x18000abdb  mov     [rcx+10h], eax
0x18000abde  mov     eax, [r8+rdx*8+10h]
0x18000abe3  mov     [rcx+18h], eax
0x18000abe6  add     rcx, 1Ch; wchar_t *
0x18000abea  mov     r8, [r8+rdx*8+18h]; wchar_t *
0x18000abef  lea     edx, [rdi+20h]; unsigned __int64
0x18000abf2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000abf7  mov     rcx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000abfe  lea     rax, [rbx+rbx*4]
0x18000ac02  test    byte ptr [rcx+rax*8+20h], 4
0x18000ac07  jnz     short loc_18000AC17
0x18000ac09  mov     edi, 1
0x18000ac0e  lea     rax, ?wszRasterFonts@@3PA_WA; wchar_t near * wszRasterFonts
0x18000ac15  jmp     short loc_18000AC1C
0x18000ac17  mov     rax, [rcx+rax*8+18h]
0x18000ac1c  or      r9, 0FFFFFFFFFFFFFFFFh; wParam
0x18000ac20  mov     [rsp+38h+lParam], rax; lParam
0x18000ac25  mov     edx, 0CAh; nIDDlgItem
0x18000ac2a  mov     r8d, 18Ch; Msg
0x18000ac30  mov     rcx, rsi; hDlg
0x18000ac33  call    cs:__imp_SendDlgItemMessageW
0x18000ac3a  nop     dword ptr [rax+rax+00h]
0x18000ac3f  mov     r8d, ebx; int
0x18000ac42  mov     edx, edi; int
0x18000ac44  mov     rcx, rsi; hWnd
0x18000ac47  call    ?SelectCurrentSize@@YAHPEAUHWND__@@HH@Z; SelectCurrentSize(HWND__ *,int,int)
0x18000ac4c  mov     rbx, [rsp+38h+arg_0]
0x18000ac51  mov     eax, edi
0x18000ac53  mov     rsi, [rsp+38h+arg_8]
0x18000ac58  add     rsp, 30h
0x18000ac5c  pop     rdi
0x18000ac5d  retn
```
