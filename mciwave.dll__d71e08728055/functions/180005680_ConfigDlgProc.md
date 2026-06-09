# ConfigDlgProc

- ea: `0x180005680`
- end: `0x180005854`
- name: `ConfigDlgProc`
- size: `468`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005680`
- `0x18000585c`
- `0x180005998`

## import_xrefs

- `USER32!SetDlgItemInt` at `0x18000581b`
- `USER32!SetDlgItemInt` at `0x18000581b`
- `USER32!SetScrollPos` at `0x18000575a`
- `USER32!SetScrollPos` at `0x180005807`
- `USER32!SetScrollPos` at `0x18000575a`
- `USER32!SetScrollPos` at `0x180005807`
- `USER32!GetDlgItem` at `0x1800057d5`
- `USER32!GetDlgItem` at `0x1800057d5`
- `USER32!SetScrollRange` at `0x1800057f5`
- `USER32!SetScrollRange` at `0x1800057f5`
- `USER32!GetDlgItemInt` at `0x1800056e6`
- `USER32!GetDlgItemInt` at `0x1800057ad`
- `USER32!GetDlgItemInt` at `0x1800056e6`
- `USER32!GetDlgItemInt` at `0x1800057ad`
- `USER32!WinHelpW` at `0x18000583d`
- `USER32!WinHelpW` at `0x18000583d`
- `USER32!EndDialog` at `0x18000577e`
- `USER32!EndDialog` at `0x18000577e`

## pseudocode

```c
INT_PTR __fastcall ConfigDlgProc(HWND a1, int a2, HWND a3, HWND a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  UINT v12; // eax
  UINT v13; // edx
  int v14; // esi
  unsigned int v15; // eax
  UINT v16; // r8d
  INT_PTR v18; // rdx
  UINT DlgItemInt; // eax
  __int64 v20; // rcx
  int CmdParm; // edi
  HWND DlgItem; // rbx
  UINT v23; // r8d
  HWND v24; // rcx
  BOOL Translated; // [rsp+78h] [rbp+10h] BYREF

  Translated = 0;
  v7 = a2 - 16;
  if ( !v7 )
    goto LABEL_28;
  v8 = v7 - 67;
  if ( !v8 )
  {
    v24 = (HWND)*((_QWORD *)a4 + 2);
    v23 = 12;
    goto LABEL_37;
  }
  v9 = v8 - 40;
  if ( !v9 )
  {
    v23 = 10;
    v24 = a3;
LABEL_37:
    WinHelpW(v24, L"MMDRV.HLP", v23, (ULONG_PTR)&dwData);
    return 1;
  }
  v10 = v9 - 149;
  if ( !v10 )
  {
    qword_1800085B8 = (__int64)a4;
    CmdParm = GetCmdParm();
    DlgItem = GetDlgItem(a1, 256);
    SetScrollRange(DlgItem, 2, 2, 9, 0);
    SetScrollPos(DlgItem, 2, CmdParm, 0);
    v16 = CmdParm;
    goto LABEL_35;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( (unsigned __int16)a3 == 1 )
    {
      if ( qword_1800085B8 )
      {
        DlgItemInt = GetDlgItemInt(a1, 257, &Translated, 0);
        PutCmdParm(v20, DlgItemInt);
      }
      v18 = 1;
      goto LABEL_29;
    }
    if ( (unsigned __int16)a3 != 2 )
      return 1;
LABEL_28:
    v18 = 0;
LABEL_29:
    EndDialog(a1, v18);
    return 1;
  }
  if ( v11 != 3 )
    return 0;
  v12 = GetDlgItemInt(a1, 257, &Translated, 0);
  v13 = v12;
  if ( !(_WORD)a3 )
    goto LABEL_21;
  switch ( (unsigned __int16)a3 )
  {
    case 1u:
LABEL_18:
      v15 = v12 + 1;
      if ( v15 > 9 )
        v15 = 9;
      v14 = v15;
      break;
    case 2u:
LABEL_21:
      v14 = v12 - 1;
      if ( v12 - 1 < 2 )
        v14 = 2;
      break;
    case 3u:
      goto LABEL_18;
    case 4u:
    case 5u:
      v14 = WORD1(a3);
      break;
    case 6u:
      v14 = 2;
      break;
    case 7u:
      v14 = 9;
      break;
    default:
      return 0;
  }
  if ( v14 != v13 )
  {
    SetScrollPos(a4, 2, v14, 1);
    v16 = v14;
LABEL_35:
    SetDlgItemInt(a1, 257, v16, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x180005680  push    rbx
0x180005682  push    rbp
0x180005683  push    rsi
0x180005684  push    rdi
0x180005685  push    r14
0x180005687  push    r15
0x180005689  sub     rsp, 38h
0x18000568d  xor     esi, esi
0x18000568f  mov     rdi, r9
0x180005692  mov     [rsp+68h+Translated], esi
0x180005696  mov     rbx, r8
0x180005699  mov     rbp, rcx
0x18000569c  lea     r15d, [rsi+1]
0x1800056a0  sub     edx, 10h
0x1800056a3  jz      loc_180005779
0x1800056a9  sub     edx, 43h ; 'C'
0x1800056ac  jz      loc_180005848
0x1800056b2  sub     edx, 28h ; '('
0x1800056b5  jz      loc_180005826
0x1800056bb  sub     edx, 95h
0x1800056c1  jz      loc_1800057BF
0x1800056c7  sub     edx, r15d
0x1800056ca  jz      loc_18000576C
0x1800056d0  cmp     edx, 3
0x1800056d3  jnz     loc_180005768
0x1800056d9  xor     r9d, r9d; bSigned
0x1800056dc  lea     r8, [rsp+68h+Translated]; lpTranslated
0x1800056e1  mov     edx, 101h; nIDDlgItem
0x1800056e6  call    cs:__imp_GetDlgItemInt
0x1800056ec  movzx   ecx, bx
0x1800056ef  lea     r14d, [rsi+2]
0x1800056f3  mov     edx, eax
0x1800056f5  test    ecx, ecx
0x1800056f7  jz      short loc_180005740
0x1800056f9  sub     ecx, r15d
0x1800056fc  jz      short loc_180005730
0x1800056fe  sub     ecx, r15d
0x180005701  jz      short loc_180005740
0x180005703  sub     ecx, r15d
0x180005706  jz      short loc_180005730
0x180005708  sub     ecx, r15d
0x18000570b  jz      short loc_180005727
0x18000570d  sub     ecx, r15d
0x180005710  jz      short loc_180005727
0x180005712  sub     ecx, r15d
0x180005715  jz      short loc_180005722
0x180005717  cmp     ecx, r15d
0x18000571a  jnz     short loc_180005768
0x18000571c  lea     esi, [r15+8]
0x180005720  jmp     short loc_18000574A
0x180005722  mov     esi, r14d
0x180005725  jmp     short loc_18000574A
0x180005727  shr     rbx, 10h
0x18000572b  movzx   esi, bx
0x18000572e  jmp     short loc_18000574A
0x180005730  mov     esi, 9
0x180005735  inc     eax
0x180005737  cmp     eax, esi
0x180005739  cmova   eax, esi
0x18000573c  mov     esi, eax
0x18000573e  jmp     short loc_18000574A
0x180005740  lea     esi, [rax-1]
0x180005743  cmp     esi, r14d
0x180005746  cmovb   esi, r14d
0x18000574a  cmp     esi, edx
0x18000574c  jz      short loc_180005784
0x18000574e  mov     r9d, r15d; bRedraw
0x180005751  mov     r8d, esi; nPos
0x180005754  mov     edx, r14d; nBar
0x180005757  mov     rcx, rdi; hWnd
0x18000575a  call    cs:__imp_SetScrollPos
0x180005760  mov     r8d, esi
0x180005763  jmp     loc_180005810
0x180005768  xor     eax, eax
0x18000576a  jmp     short loc_180005787
0x18000576c  movzx   ecx, bx
0x18000576f  sub     ecx, r15d
0x180005772  jz      short loc_180005794
0x180005774  cmp     ecx, r15d
0x180005777  jnz     short loc_180005784
0x180005779  xor     edx, edx; nResult
0x18000577b  mov     rcx, rbp; hDlg
0x18000577e  call    cs:__imp_EndDialog
0x180005784  mov     rax, r15
0x180005787  add     rsp, 38h
0x18000578b  pop     r15
0x18000578d  pop     r14
0x18000578f  pop     rdi
0x180005790  pop     rsi
0x180005791  pop     rbp
0x180005792  pop     rbx
0x180005793  retn
0x180005794  cmp     cs:qword_1800085B8, rsi
0x18000579b  jz      short loc_1800057BA
0x18000579d  xor     r9d, r9d; bSigned
0x1800057a0  lea     r8, [rsp+68h+Translated]; lpTranslated
0x1800057a5  mov     edx, 101h; nIDDlgItem
0x1800057aa  mov     rcx, rbp; hDlg
0x1800057ad  call    cs:__imp_GetDlgItemInt
0x1800057b3  mov     edx, eax
0x1800057b5  call    PutCmdParm
0x1800057ba  mov     rdx, r15
0x1800057bd  jmp     short loc_18000577B
0x1800057bf  mov     cs:qword_1800085B8, rdi
0x1800057c6  call    GetCmdParm
0x1800057cb  mov     edx, 100h; nIDDlgItem
0x1800057d0  mov     rcx, rbp; hDlg
0x1800057d3  mov     edi, eax
0x1800057d5  call    cs:__imp_GetDlgItem
0x1800057db  mov     r9d, 9; nMaxPos
0x1800057e1  mov     [rsp+68h+bRedraw], esi; bRedraw
0x1800057e5  mov     rcx, rax; hWnd
0x1800057e8  mov     rbx, rax
0x1800057eb  lea     r14d, [r9-7]
0x1800057ef  mov     r8d, r14d; nMinPos
0x1800057f2  mov     edx, r14d; nBar
0x1800057f5  call    cs:__imp_SetScrollRange
0x1800057fb  xor     r9d, r9d; bRedraw
0x1800057fe  mov     r8d, edi; nPos
0x180005801  mov     edx, r14d; nBar
0x180005804  mov     rcx, rbx; hWnd
0x180005807  call    cs:__imp_SetScrollPos
0x18000580d  mov     r8d, edi; uValue
0x180005810  xor     r9d, r9d; bSigned
0x180005813  mov     edx, 101h; nIDDlgItem
0x180005818  mov     rcx, rbp; hDlg
0x18000581b  call    cs:__imp_SetDlgItemInt
0x180005821  jmp     loc_180005784
0x180005826  mov     r8d, 0Ah; uCommand
0x18000582c  mov     rcx, rbx; hWndMain
0x18000582f  lea     rdx, szHelp; "MMDRV.HLP"
0x180005836  lea     r9, dwData; dwData
0x18000583d  call    cs:__imp_WinHelpW
0x180005843  jmp     loc_180005784
0x180005848  mov     rcx, [rdi+10h]
0x18000584c  mov     r8d, 0Ch
0x180005852  jmp     short loc_18000582F
```
