# CAdvScheduleDlg::_OnOK(void)

- ea: `0x180018edc`
- end: `0x180019235`
- name: `?_OnOK@CAdvScheduleDlg@@AEAAHXZ`
- size: `857`
- prototype: `__int64 __fastcall(CAdvScheduleDlg *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180018780`

## callees

- `0x180017df4`
- `0x180018edc`
- `0x18001aac0`

## import_xrefs

- `USER32!SendMessageW` at `0x180018f2e`
- `USER32!SendMessageW` at `0x180018f94`
- `USER32!SendMessageW` at `0x1800190a0`
- `USER32!SendMessageW` at `0x1800190f5`
- `USER32!SendMessageW` at `0x180018f2e`
- `USER32!SendMessageW` at `0x180018f94`
- `USER32!SendMessageW` at `0x1800190a0`
- `USER32!SendMessageW` at `0x1800190f5`
- `USER32!GetDlgItem` at `0x180018f10`
- `USER32!GetDlgItem` at `0x180018f7d`
- `USER32!GetDlgItem` at `0x180019087`
- `USER32!GetDlgItem` at `0x1800190da`
- `USER32!GetDlgItem` at `0x180018f10`
- `USER32!GetDlgItem` at `0x180018f7d`
- `USER32!GetDlgItem` at `0x180019087`
- `USER32!GetDlgItem` at `0x1800190da`
- `USER32!SendDlgItemMessageW` at `0x18001905c`
- `USER32!SendDlgItemMessageW` at `0x18001914f`
- `USER32!SendDlgItemMessageW` at `0x18001917f`
- `USER32!SendDlgItemMessageW` at `0x1800191fa`
- `USER32!SendDlgItemMessageW` at `0x18001905c`
- `USER32!SendDlgItemMessageW` at `0x18001914f`
- `USER32!SendDlgItemMessageW` at `0x18001917f`
- `USER32!SendDlgItemMessageW` at `0x1800191fa`
- `USER32!IsDlgButtonChecked` at `0x180018f65`
- `USER32!IsDlgButtonChecked` at `0x180019036`
- `USER32!IsDlgButtonChecked` at `0x1800190bf`
- `USER32!IsDlgButtonChecked` at `0x1800191b0`
- `USER32!IsDlgButtonChecked` at `0x180018f65`
- `USER32!IsDlgButtonChecked` at `0x180019036`
- `USER32!IsDlgButtonChecked` at `0x1800190bf`
- `USER32!IsDlgButtonChecked` at `0x1800191b0`

## pseudocode

```c
__int64 __fastcall CAdvScheduleDlg::_OnOK(CAdvScheduleDlg *this)
{
  HWND v2; // rcx
  HWND DlgItem; // rax
  HWND v4; // rax
  HWND v5; // rcx
  UINT v6; // edx
  HWND v8; // rcx
  HWND v9; // rax
  UINT v10; // eax
  HWND v11; // rcx
  HWND v12; // rax
  __int64 v13; // r9
  unsigned int v14; // r8d
  unsigned int v15; // ecx
  int v16; // ebx
  UINT v17; // eax
  __int64 v18; // rdx
  int v19; // ecx
  unsigned int v20; // ecx
  LPARAM v21[2]; // [rsp+30h] [rbp-48h] BYREF
  LPARAM lParam[2]; // [rsp+40h] [rbp-38h] BYREF
  LPARAM v23[2]; // [rsp+50h] [rbp-28h] BYREF

  v2 = (HWND)*((_QWORD *)this + 1);
  *(_OWORD *)lParam = 0;
  *(_OWORD *)v21 = 0;
  DlgItem = GetDlgItem(v2, 1773);
  if ( DlgItem && !(unsigned int)SendMessageW(DlgItem, 0x1001u, 0, (LPARAM)lParam) )
  {
    *(_DWORD *)(*((_QWORD *)this + 2) + 4LL) = lParam[0];
    *(_WORD *)(*((_QWORD *)this + 2) + 8LL) = HIWORD(lParam[0]);
  }
  if ( IsDlgButtonChecked(*((HWND *)this + 1), 1790) == 1 )
  {
    v4 = GetDlgItem(*((HWND *)this + 1), 1778);
    if ( v4 && !(unsigned int)SendMessageW(v4, 0x1001u, 0, (LPARAM)v21) )
    {
      *(_DWORD *)(*((_QWORD *)this + 2) + 10LL) = v21[0];
      *(_WORD *)(*((_QWORD *)this + 2) + 14LL) = HIWORD(v21[0]);
    }
    *(_DWORD *)(*((_QWORD *)this + 2) + 28LL) |= 1u;
    WORD2(lParam[0]) = 0;
    WORD2(v21[0]) = 0;
    if ( (BYTE6(lParam[0]) | (LOWORD(lParam[0]) << 16) | (unsigned __int16)(BYTE2(lParam[0]) << 8)) > (BYTE6(v21[0]) | (LOWORD(v21[0]) << 16) | (unsigned __int16)(BYTE2(v21[0]) << 8)) )
    {
      v5 = (HWND)*((_QWORD *)this + 1);
      v6 = 4131;
LABEL_10:
      SchedUIErrorDialog(v5, v6, 0, 0);
      return 0;
    }
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 2) + 28LL) &= ~1u;
  }
  if ( IsDlgButtonChecked(*((HWND *)this + 1), 1774) == 1 )
  {
    *(_DWORD *)(*((_QWORD *)this + 2) + 24LL) = SendDlgItemMessageW(*((HWND *)this + 1), 1776, 0x468u, 0, 0);
    v8 = (HWND)*((_QWORD *)this + 1);
    if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)this + 2) + 24LL) - 1) > 0x270E )
    {
      SchedUIErrorDialog(v8, 0x1039u, 0, 0);
      SendDlgItemMessageW(*((HWND *)this + 1), 1776, 0x467u, 0, 1);
      return 0;
    }
    v9 = GetDlgItem(v8, 1777);
    if ( v9 && (unsigned int)SendMessageW(v9, 0x147u, 0, 0) == 1 )
      *(_DWORD *)(*((_QWORD *)this + 2) + 24LL) *= 60;
    v10 = IsDlgButtonChecked(*((HWND *)this + 1), 1780);
    v11 = (HWND)*((_QWORD *)this + 1);
    if ( v10 == 1 )
    {
      *(_OWORD *)v23 = 0;
      v12 = GetDlgItem(v11, 1782);
      if ( v12 && !(unsigned int)SendMessageW(v12, 0x1001u, 0, (LPARAM)v23) )
      {
        v13 = *((_QWORD *)this + 2);
        v14 = *(unsigned __int16 *)(v13 + 18) + 60 * *(unsigned __int16 *)(v13 + 16);
        v15 = WORD1(v23[1]) + 60 * LOWORD(v23[1]) - v14;
        if ( WORD1(v23[1]) + 60 * (unsigned int)LOWORD(v23[1]) <= v14 )
          v15 += 1440;
        *(_DWORD *)(v13 + 20) = v15;
      }
    }
    else
    {
      v16 = SendDlgItemMessageW(v11, 1786, 0x468u, 0, 0);
      if ( HIWORD(v16) )
        v16 = 59;
      *(_DWORD *)(*((_QWORD *)this + 2) + 20LL) = v16
                                                + 60 * SendDlgItemMessageW(*((HWND *)this + 1), 1784, 0x468u, 0, 0);
    }
    v5 = (HWND)*((_QWORD *)this + 1);
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 20LL) <= *(_DWORD *)(*((_QWORD *)this + 2) + 24LL) )
    {
      v6 = 4132;
      goto LABEL_10;
    }
    v17 = IsDlgButtonChecked(v5, 1779);
    v18 = *((_QWORD *)this + 2);
    v19 = *(_DWORD *)(v18 + 28);
    if ( v17 == 1 )
      v20 = v19 | 2;
    else
      v20 = v19 & 0xFFFFFFFD;
    *(_DWORD *)(v18 + 28) = v20;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 2) + 24LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 2) + 20LL) = 0;
    *(_DWORD *)(*((_QWORD *)this + 2) + 28LL) &= ~2u;
  }
  return 1;
}

```

## disassembly

```asm
0x180018edc  push    rbp
0x180018ede  push    rbx
0x180018edf  push    rsi
0x180018ee0  push    rdi
0x180018ee1  mov     rbp, rsp
0x180018ee4  sub     rsp, 78h
0x180018ee8  mov     rax, cs:__security_cookie
0x180018eef  xor     rax, rsp
0x180018ef2  mov     [rbp+var_18], rax
0x180018ef6  mov     rdi, rcx
0x180018ef9  xorps   xmm0, xmm0
0x180018efc  mov     rcx, [rcx+8]; hDlg
0x180018f00  xorps   xmm1, xmm1
0x180018f03  mov     edx, 6EDh; nIDDlgItem
0x180018f08  movups  xmmword ptr [rbp+lParam], xmm0
0x180018f0c  movups  xmmword ptr [rbp+var_48], xmm1
0x180018f10  call    cs:__imp_GetDlgItem
0x180018f16  xor     esi, esi
0x180018f18  mov     ebx, 1001h
0x180018f1d  test    rax, rax
0x180018f20  jz      short loc_180018F5C
0x180018f22  lea     r9, [rbp+lParam]; lParam
0x180018f26  xor     r8d, r8d; wParam
0x180018f29  mov     edx, ebx; Msg
0x180018f2b  mov     rcx, rax; hWnd
0x180018f2e  call    cs:__imp_SendMessageW
0x180018f34  test    eax, eax
0x180018f36  jnz     short loc_180018F5C
0x180018f38  mov     rcx, [rdi+10h]
0x180018f3c  movzx   eax, word ptr [rbp+lParam]
0x180018f40  mov     [rcx+4], ax
0x180018f44  mov     rcx, [rdi+10h]
0x180018f48  movzx   eax, word ptr [rbp+lParam+2]
0x180018f4c  mov     [rcx+6], ax
0x180018f50  mov     rcx, [rdi+10h]
0x180018f54  movzx   eax, word ptr [rbp+lParam+6]
0x180018f58  mov     [rcx+8], ax
0x180018f5c  mov     rcx, [rdi+8]; hDlg
0x180018f60  mov     edx, 6FEh; nIDButton
0x180018f65  call    cs:__imp_IsDlgButtonChecked
0x180018f6b  cmp     eax, 1
0x180018f6e  jnz     loc_180019025
0x180018f74  mov     rcx, [rdi+8]; hDlg
0x180018f78  mov     edx, 6F2h; nIDDlgItem
0x180018f7d  call    cs:__imp_GetDlgItem
0x180018f83  test    rax, rax
0x180018f86  jz      short loc_180018FC2
0x180018f88  lea     r9, [rbp+var_48]; lParam
0x180018f8c  xor     r8d, r8d; wParam
0x180018f8f  mov     edx, ebx; Msg
0x180018f91  mov     rcx, rax; hWnd
0x180018f94  call    cs:__imp_SendMessageW
0x180018f9a  test    eax, eax
0x180018f9c  jnz     short loc_180018FC2
0x180018f9e  mov     rcx, [rdi+10h]
0x180018fa2  movzx   eax, word ptr [rbp+var_48]
0x180018fa6  mov     [rcx+0Ah], ax
0x180018faa  mov     rcx, [rdi+10h]
0x180018fae  movzx   eax, word ptr [rbp+var_48+2]
0x180018fb2  mov     [rcx+0Ch], ax
0x180018fb6  mov     rcx, [rdi+10h]
0x180018fba  movzx   eax, word ptr [rbp+var_48+6]
0x180018fbe  mov     [rcx+0Eh], ax
0x180018fc2  mov     rax, [rdi+10h]
0x180018fc6  or      dword ptr [rax+1Ch], 1
0x180018fca  movzx   eax, byte ptr [rbp+var_48+2]
0x180018fce  shl     ax, 8
0x180018fd2  movzx   edx, ax
0x180018fd5  movzx   eax, word ptr [rbp+var_48]
0x180018fd9  shl     eax, 10h
0x180018fdc  or      edx, eax
0x180018fde  mov     word ptr [rbp+lParam+4], si
0x180018fe2  movzx   eax, byte ptr [rbp+var_48+6]
0x180018fe6  or      edx, eax
0x180018fe8  mov     word ptr [rbp+var_48+4], si
0x180018fec  movzx   eax, byte ptr [rbp+lParam+2]
0x180018ff0  shl     ax, 8
0x180018ff4  movzx   ecx, ax
0x180018ff7  movzx   eax, word ptr [rbp+lParam]
0x180018ffb  shl     eax, 10h
0x180018ffe  or      ecx, eax
0x180019000  movzx   eax, byte ptr [rbp+lParam+6]
0x180019004  or      ecx, eax
0x180019006  cmp     ecx, edx
0x180019008  jle     short loc_18001902D
0x18001900a  mov     rcx, [rdi+8]; hWnd
0x18001900e  mov     edx, 1023h; uID
0x180019013  xor     r9d, r9d; UINT
0x180019016  xor     r8d, r8d; int
0x180019019  call    ?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z; SchedUIErrorDialog(HWND__ *,int,long,uint)
0x18001901e  xor     eax, eax
0x180019020  jmp     loc_180019220
0x180019025  mov     rax, [rdi+10h]
0x180019029  and     dword ptr [rax+1Ch], 0FFFFFFFEh
0x18001902d  mov     rcx, [rdi+8]; hDlg
0x180019031  mov     edx, 6EEh; nIDButton
0x180019036  call    cs:__imp_IsDlgButtonChecked
0x18001903c  cmp     eax, 1
0x18001903f  jnz     loc_180019205
0x180019045  mov     rcx, [rdi+8]; hDlg
0x180019049  xor     r9d, r9d; wParam
0x18001904c  mov     edx, 6F0h; nIDDlgItem
0x180019051  mov     [rsp+78h+var_58], rsi; lParam
0x180019056  mov     r8d, 468h; Msg
0x18001905c  call    cs:__imp_SendDlgItemMessageW
0x180019062  mov     rcx, [rdi+10h]
0x180019066  mov     [rcx+18h], eax
0x180019069  mov     rax, [rdi+10h]
0x18001906d  mov     ecx, [rax+18h]
0x180019070  dec     ecx
0x180019072  cmp     ecx, 270Eh
0x180019078  mov     rcx, [rdi+8]; hWnd
0x18001907c  ja      loc_1800191CF
0x180019082  mov     edx, 6F1h; nIDDlgItem
0x180019087  call    cs:__imp_GetDlgItem
0x18001908d  test    rax, rax
0x180019090  jz      short loc_1800190B6
0x180019092  xor     r9d, r9d; lParam
0x180019095  xor     r8d, r8d; wParam
0x180019098  mov     edx, 147h; Msg
0x18001909d  mov     rcx, rax; hWnd
0x1800190a0  call    cs:__imp_SendMessageW
0x1800190a6  cmp     eax, 1
0x1800190a9  jnz     short loc_1800190B6
0x1800190ab  mov     rcx, [rdi+10h]
0x1800190af  imul    eax, [rcx+18h], 3Ch ; '<'
0x1800190b3  mov     [rcx+18h], eax
0x1800190b6  mov     rcx, [rdi+8]; hDlg
0x1800190ba  mov     edx, 6F4h; nIDButton
0x1800190bf  call    cs:__imp_IsDlgButtonChecked
0x1800190c5  mov     rcx, [rdi+8]; hDlg
0x1800190c9  cmp     eax, 1
0x1800190cc  jnz     short loc_18001913C
0x1800190ce  xorps   xmm0, xmm0
0x1800190d1  mov     edx, 6F6h; nIDDlgItem
0x1800190d6  movups  xmmword ptr [rbp+var_28], xmm0
0x1800190da  call    cs:__imp_GetDlgItem
0x1800190e0  test    rax, rax
0x1800190e3  jz      loc_180019191
0x1800190e9  lea     r9, [rbp+var_28]; lParam
0x1800190ed  xor     r8d, r8d; wParam
0x1800190f0  mov     edx, ebx; Msg
0x1800190f2  mov     rcx, rax; hWnd
0x1800190f5  call    cs:__imp_SendMessageW
0x1800190fb  test    eax, eax
0x1800190fd  jnz     loc_180019191
0x180019103  mov     r9, [rdi+10h]
0x180019107  movzx   eax, word ptr [r9+10h]
0x18001910c  imul    r8d, eax, 3Ch ; '<'
0x180019110  movzx   eax, word ptr [r9+12h]
0x180019115  add     r8d, eax
0x180019118  movzx   eax, word ptr [rbp+var_28+8]
0x18001911c  imul    edx, eax, 3Ch ; '<'
0x18001911f  movzx   eax, word ptr [rbp+var_28+0Ah]
0x180019123  add     edx, eax
0x180019125  mov     ecx, edx
0x180019127  sub     ecx, r8d
0x18001912a  cmp     edx, r8d
0x18001912d  lea     eax, [rcx+5A0h]
0x180019133  cmovbe  ecx, eax
0x180019136  mov     [r9+14h], ecx
0x18001913a  jmp     short loc_180019191
0x18001913c  xor     r9d, r9d; wParam
0x18001913f  mov     [rsp+78h+var_58], rsi; lParam
0x180019144  mov     edx, 6FAh; nIDDlgItem
0x180019149  mov     r8d, 468h; Msg
0x18001914f  call    cs:__imp_SendDlgItemMessageW
0x180019155  mov     edx, 6F8h; nIDDlgItem
0x18001915a  mov     [rsp+78h+var_58], rsi; lParam
0x18001915f  mov     ecx, eax
0x180019161  mov     rbx, rax
0x180019164  shr     ecx, 10h
0x180019167  mov     eax, 3Bh ; ';'
0x18001916c  test    cx, cx
0x18001916f  mov     r8d, 468h; Msg
0x180019175  mov     rcx, [rdi+8]; hDlg
0x180019179  cmovnz  ebx, eax
0x18001917c  xor     r9d, r9d; wParam
0x18001917f  call    cs:__imp_SendDlgItemMessageW
0x180019185  imul    edx, eax, 3Ch ; '<'
0x180019188  mov     rax, [rdi+10h]
0x18001918c  add     edx, ebx
0x18001918e  mov     [rax+14h], edx
0x180019191  mov     rdx, [rdi+10h]
0x180019195  mov     rcx, [rdi+8]; hDlg
0x180019199  mov     eax, [rdx+18h]
0x18001919c  cmp     [rdx+14h], eax
0x18001919f  ja      short loc_1800191AB
0x1800191a1  mov     edx, 1024h
0x1800191a6  jmp     loc_180019013
0x1800191ab  mov     edx, 6F3h; nIDButton
0x1800191b0  call    cs:__imp_IsDlgButtonChecked
0x1800191b6  mov     rdx, [rdi+10h]
0x1800191ba  mov     ecx, [rdx+1Ch]
0x1800191bd  cmp     eax, 1
0x1800191c0  jnz     short loc_1800191C7
0x1800191c2  or      ecx, 2
0x1800191c5  jmp     short loc_1800191CA
0x1800191c7  and     ecx, 0FFFFFFFDh
0x1800191ca  mov     [rdx+1Ch], ecx
0x1800191cd  jmp     short loc_18001921B
0x1800191cf  xor     r9d, r9d; UINT
0x1800191d2  xor     r8d, r8d; int
0x1800191d5  mov     edx, 1039h; uID
0x1800191da  call    ?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z; SchedUIErrorDialog(HWND__ *,int,long,uint)
0x1800191df  mov     rcx, [rdi+8]; hDlg
0x1800191e3  xor     r9d, r9d; wParam
0x1800191e6  mov     edx, 6F0h; nIDDlgItem
0x1800191eb  mov     [rsp+78h+var_58], 1; lParam
0x1800191f4  mov     r8d, 467h; Msg
0x1800191fa  call    cs:__imp_SendDlgItemMessageW
0x180019200  jmp     loc_18001901E
0x180019205  mov     rcx, [rdi+10h]
0x180019209  mov     [rcx+18h], esi
0x18001920c  mov     rcx, [rdi+10h]
0x180019210  mov     [rcx+14h], esi
0x180019213  mov     rcx, [rdi+10h]
0x180019217  and     dword ptr [rcx+1Ch], 0FFFFFFFDh
0x18001921b  mov     eax, 1
0x180019220  mov     rcx, [rbp+var_18]
0x180019224  xor     rcx, rsp; StackCookie
0x180019227  call    __security_check_cookie
0x18001922c  add     rsp, 78h
0x180019230  pop     rdi
0x180019231  pop     rsi
0x180019232  pop     rbx
0x180019233  pop     rbp
0x180019234  retn
```
