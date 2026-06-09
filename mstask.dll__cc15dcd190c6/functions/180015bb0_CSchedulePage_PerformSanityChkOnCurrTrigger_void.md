# CSchedulePage::_PerformSanityChkOnCurrTrigger(void)

- ea: `0x180015bb0`
- end: `0x180015daf`
- name: `?_PerformSanityChkOnCurrTrigger@CSchedulePage@@AEAAHXZ`
- size: `511`
- prototype: `__int64 __fastcall(CSchedulePage *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014620`
- `0x180014aa0`
- `0x1800158d0`

## callees

- `0x18000d470`
- `0x180015bb0`
- `0x180017df4`

## import_xrefs

- `USER32!SendMessageW` at `0x180015bf8`
- `USER32!SendMessageW` at `0x180015bf8`
- `USER32!GetDlgItem` at `0x180015bd8`
- `USER32!GetDlgItem` at `0x180015bd8`
- `USER32!SendDlgItemMessageW` at `0x180015c62`
- `USER32!SendDlgItemMessageW` at `0x180015c92`
- `USER32!SendDlgItemMessageW` at `0x180015d1a`
- `USER32!SendDlgItemMessageW` at `0x180015d83`
- `USER32!SendDlgItemMessageW` at `0x180015c62`
- `USER32!SendDlgItemMessageW` at `0x180015c92`
- `USER32!SendDlgItemMessageW` at `0x180015d1a`
- `USER32!SendDlgItemMessageW` at `0x180015d83`
- `USER32!GetDlgItemInt` at `0x180015c3f`
- `USER32!GetDlgItemInt` at `0x180015cf9`
- `USER32!GetDlgItemInt` at `0x180015d62`
- `USER32!GetDlgItemInt` at `0x180015c3f`
- `USER32!GetDlgItemInt` at `0x180015cf9`
- `USER32!GetDlgItemInt` at `0x180015d62`
- `USER32!IsDlgButtonChecked` at `0x180015c22`
- `USER32!IsDlgButtonChecked` at `0x180015d45`
- `USER32!IsDlgButtonChecked` at `0x180015c22`
- `USER32!IsDlgButtonChecked` at `0x180015d45`

## pseudocode

```c
__int64 __fastcall CSchedulePage::_PerformSanityChkOnCurrTrigger(HWND *this)
{
  HWND DlgItem; // rax
  int v4; // eax
  UINT DlgItemInt; // ecx
  UINT v6; // edi
  HWND v7; // rax
  __int128 v8; // xmm1
  __int64 i; // rsi
  _TASK_TRIGGER v10; // [rsp+30h] [rbp-58h] BYREF

  if ( this[91] )
  {
    DlgItem = GetDlgItem(this[14], 1690);
    if ( !DlgItem )
      return 0;
    v4 = SendMessageW(DlgItem, 0x147u, 0, 0);
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        if ( GetDlgItemInt(this[14], 1713, 0, 0) )
        {
          v6 = 4143;
          for ( i = 0; (unsigned int)i < 7; i = (unsigned int)(i + 1) )
          {
            if ( IsDlgButtonChecked(this[14], *(&g_aDayData + 3 * i)) == 1 )
              return 1;
          }
        }
        else
        {
          SendDlgItemMessageW(this[14], 1714, 0x467u, 0, 1);
          v6 = 4140;
        }
        goto LABEL_22;
      }
      if ( v4 == 2 && IsDlgButtonChecked(this[14], 1732) == 1 )
      {
        DlgItemInt = GetDlgItemInt(this[14], 1733, 0, 0);
        if ( !DlgItemInt )
        {
          SendDlgItemMessageW(this[14], 1734, 0x467u, 0, 1);
          v6 = 4141;
LABEL_22:
          SchedUIErrorDialog(this[14], v6, 0, 0);
          return 0;
        }
        if ( DlgItemInt > 0x1F )
        {
          SendDlgItemMessageW(this[14], 1734, 0x467u, 0, 31);
          v6 = 4142;
          goto LABEL_22;
        }
        v7 = this[91];
        v8 = *(_OWORD *)(v7 + 10);
        *(_OWORD *)&v10.cbTriggerSize = *(_OWORD *)(v7 + 6);
        *(_OWORD *)&v10.TriggerType = *(_OWORD *)(v7 + 14);
        v10.Type.MonthlyDate.rgfDays = 1 << (DlgItemInt - 1);
        *(_OWORD *)&v10.wStartHour = v8;
        if ( !IsValidMonthlyDateTrigger(&v10) )
        {
          v6 = 4152;
          goto LABEL_22;
        }
      }
    }
    else if ( !GetDlgItemInt(this[14], 1703, 0, 0) )
    {
      SendDlgItemMessageW(this[14], 1704, 0x467u, 0, 1);
      v6 = 4139;
      goto LABEL_22;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180015bb0  push    rbx
0x180015bb2  push    rbp
0x180015bb3  push    rsi
0x180015bb4  push    rdi
0x180015bb5  sub     rsp, 68h
0x180015bb9  cmp     qword ptr [rcx+2D8h], 0
0x180015bc1  mov     rbx, rcx
0x180015bc4  mov     ebp, 1
0x180015bc9  jz      loc_180015DA4
0x180015bcf  mov     rcx, [rcx+70h]; hDlg
0x180015bd3  mov     edx, 69Ah; nIDDlgItem
0x180015bd8  call    cs:__imp_GetDlgItem
0x180015bde  test    rax, rax
0x180015be1  jnz     short loc_180015BEA
0x180015be3  xor     eax, eax
0x180015be5  jmp     loc_180015DA6
0x180015bea  xor     r9d, r9d; lParam
0x180015bed  xor     r8d, r8d; wParam
0x180015bf0  mov     edx, 147h; Msg
0x180015bf5  mov     rcx, rax; hWnd
0x180015bf8  call    cs:__imp_SendMessageW
0x180015bfe  mov     rcx, rax
0x180015c01  test    eax, eax
0x180015c03  jz      loc_180015D53
0x180015c09  sub     ecx, ebp
0x180015c0b  jz      loc_180015CEA
0x180015c11  cmp     ecx, ebp
0x180015c13  jnz     loc_180015DA4
0x180015c19  mov     rcx, [rbx+70h]; hDlg
0x180015c1d  mov     edx, 6C4h; nIDButton
0x180015c22  call    cs:__imp_IsDlgButtonChecked
0x180015c28  cmp     eax, ebp
0x180015c2a  jnz     loc_180015DA4
0x180015c30  mov     rcx, [rbx+70h]; hDlg
0x180015c34  xor     r9d, r9d; bSigned
0x180015c37  xor     r8d, r8d; lpTranslated
0x180015c3a  mov     edx, 6C5h; nIDDlgItem
0x180015c3f  call    cs:__imp_GetDlgItemInt
0x180015c45  mov     ecx, eax
0x180015c47  test    eax, eax
0x180015c49  jnz     short loc_180015C72
0x180015c4b  mov     rcx, [rbx+70h]; hDlg
0x180015c4f  xor     r9d, r9d; wParam
0x180015c52  mov     edx, 6C6h; nIDDlgItem
0x180015c57  mov     [rsp+88h+lParam], rbp; lParam
0x180015c5c  mov     r8d, 467h; Msg
0x180015c62  call    cs:__imp_SendDlgItemMessageW
0x180015c68  mov     edi, 102Dh
0x180015c6d  jmp     loc_180015D8E
0x180015c72  cmp     ecx, 1Fh
0x180015c75  jbe     short loc_180015CA2
0x180015c77  mov     rcx, [rbx+70h]; hDlg
0x180015c7b  xor     r9d, r9d; wParam
0x180015c7e  mov     edx, 6C6h; nIDDlgItem
0x180015c83  mov     [rsp+88h+lParam], 1Fh; lParam
0x180015c8c  mov     r8d, 467h; Msg
0x180015c92  call    cs:__imp_SendDlgItemMessageW
0x180015c98  mov     edi, 102Eh
0x180015c9d  jmp     loc_180015D8E
0x180015ca2  mov     rax, [rbx+2D8h]
0x180015ca9  dec     ecx
0x180015cab  movups  xmm0, xmmword ptr [rax+18h]
0x180015caf  movups  xmm1, xmmword ptr [rax+28h]
0x180015cb3  movups  xmmword ptr [rsp+88h+var_58.cbTriggerSize], xmm0
0x180015cb8  movups  xmm0, xmmword ptr [rax+38h]
0x180015cbc  mov     eax, ebp
0x180015cbe  shl     eax, cl
0x180015cc0  lea     rcx, [rsp+88h+var_58]; struct _TASK_TRIGGER *
0x180015cc5  movups  xmmword ptr [rsp+88h+var_58.TriggerType], xmm0
0x180015cca  mov     dword ptr [rsp+88h+var_58.Type], eax
0x180015cce  movups  xmmword ptr [rsp+88h+var_58.wStartHour], xmm1
0x180015cd3  call    ?IsValidMonthlyDateTrigger@@YAHPEAU_TASK_TRIGGER@@@Z; IsValidMonthlyDateTrigger(_TASK_TRIGGER *)
0x180015cd8  test    eax, eax
0x180015cda  jnz     loc_180015DA4
0x180015ce0  mov     edi, 1038h
0x180015ce5  jmp     loc_180015D8E
0x180015cea  mov     rcx, [rbx+70h]; hDlg
0x180015cee  xor     r9d, r9d; bSigned
0x180015cf1  xor     r8d, r8d; lpTranslated
0x180015cf4  mov     edx, 6B1h; nIDDlgItem
0x180015cf9  call    cs:__imp_GetDlgItemInt
0x180015cff  test    eax, eax
0x180015d01  jnz     short loc_180015D27
0x180015d03  mov     rcx, [rbx+70h]; hDlg
0x180015d07  xor     r9d, r9d; wParam
0x180015d0a  mov     edx, 6B2h; nIDDlgItem
0x180015d0f  mov     [rsp+88h+lParam], rbp; lParam
0x180015d14  mov     r8d, 467h; Msg
0x180015d1a  call    cs:__imp_SendDlgItemMessageW
0x180015d20  mov     edi, 102Ch
0x180015d25  jmp     short loc_180015D8E
0x180015d27  mov     edi, 102Fh
0x180015d2c  xor     esi, esi
0x180015d2e  cmp     esi, 7
0x180015d31  jnb     short loc_180015D8E
0x180015d33  mov     rcx, [rbx+70h]; hDlg
0x180015d37  lea     rdx, [rsi+rsi*2]
0x180015d3b  lea     rax, ?g_aDayData@@3PAUSDayData@@A; SDayData near * g_aDayData
0x180015d42  mov     edx, [rax+rdx*4]; nIDButton
0x180015d45  call    cs:__imp_IsDlgButtonChecked
0x180015d4b  cmp     eax, ebp
0x180015d4d  jz      short loc_180015DA4
0x180015d4f  add     esi, ebp
0x180015d51  jmp     short loc_180015D2E
0x180015d53  mov     rcx, [rbx+70h]; hDlg
0x180015d57  xor     r9d, r9d; bSigned
0x180015d5a  xor     r8d, r8d; lpTranslated
0x180015d5d  mov     edx, 6A7h; nIDDlgItem
0x180015d62  call    cs:__imp_GetDlgItemInt
0x180015d68  test    eax, eax
0x180015d6a  jnz     short loc_180015DA4
0x180015d6c  mov     rcx, [rbx+70h]; hDlg
0x180015d70  xor     r9d, r9d; wParam
0x180015d73  mov     edx, 6A8h; nIDDlgItem
0x180015d78  mov     [rsp+88h+lParam], rbp; lParam
0x180015d7d  mov     r8d, 467h; Msg
0x180015d83  call    cs:__imp_SendDlgItemMessageW
0x180015d89  mov     edi, 102Bh
0x180015d8e  mov     rcx, [rbx+70h]; hWnd
0x180015d92  xor     r9d, r9d; UINT
0x180015d95  xor     r8d, r8d; int
0x180015d98  mov     edx, edi; uID
0x180015d9a  call    ?SchedUIErrorDialog@@YAXPEAUHWND__@@HJI@Z; SchedUIErrorDialog(HWND__ *,int,long,uint)
0x180015d9f  jmp     loc_180015BE3
0x180015da4  mov     eax, ebp
0x180015da6  add     rsp, 68h
0x180015daa  pop     rdi
0x180015dab  pop     rsi
0x180015dac  pop     rbp
0x180015dad  pop     rbx
0x180015dae  retn
```
