# CSchedulePage::_SaveTriggerSettings(void)

- ea: `0x1800161c0`
- end: `0x180016590`
- name: `?_SaveTriggerSettings@CSchedulePage@@AEAAXXZ`
- size: `976`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014aa0`
- `0x1800158d0`
- `0x180015af0`

## callees

- `0x1800161c0`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `USER32!SendMessageW` at `0x18001621a`
- `USER32!SendMessageW` at `0x180016251`
- `USER32!SendMessageW` at `0x18001638e`
- `USER32!SendMessageW` at `0x180016454`
- `USER32!SendMessageW` at `0x180016494`
- `USER32!SendMessageW` at `0x18001621a`
- `USER32!SendMessageW` at `0x180016251`
- `USER32!SendMessageW` at `0x18001638e`
- `USER32!SendMessageW` at `0x180016454`
- `USER32!SendMessageW` at `0x180016494`
- `USER32!GetDlgItem` at `0x1800161f9`
- `USER32!GetDlgItem` at `0x180016233`
- `USER32!GetDlgItem` at `0x180016372`
- `USER32!GetDlgItem` at `0x180016436`
- `USER32!GetDlgItem` at `0x180016479`
- `USER32!GetDlgItem` at `0x1800161f9`
- `USER32!GetDlgItem` at `0x180016233`
- `USER32!GetDlgItem` at `0x180016372`
- `USER32!GetDlgItem` at `0x180016436`
- `USER32!GetDlgItem` at `0x180016479`
- `USER32!SendDlgItemMessageW` at `0x1800162dc`
- `USER32!SendDlgItemMessageW` at `0x18001640b`
- `USER32!SendDlgItemMessageW` at `0x1800164df`
- `USER32!SendDlgItemMessageW` at `0x180016566`
- `USER32!SendDlgItemMessageW` at `0x1800162dc`
- `USER32!SendDlgItemMessageW` at `0x18001640b`
- `USER32!SendDlgItemMessageW` at `0x1800164df`
- `USER32!SendDlgItemMessageW` at `0x180016566`
- `USER32!IsDlgButtonChecked` at `0x1800163d7`
- `USER32!IsDlgButtonChecked` at `0x18001651a`
- `USER32!IsDlgButtonChecked` at `0x1800163d7`
- `USER32!IsDlgButtonChecked` at `0x18001651a`

## pseudocode

```c
void __fastcall CSchedulePage::_SaveTriggerSettings(HWND *this)
{
  unsigned int v1; // esi
  HWND DlgItem; // rax
  int v4; // eax
  HWND v5; // rcx
  int v6; // edi
  HWND v7; // rax
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // eax
  HWND v14; // rcx
  int v15; // edi
  __int64 v16; // rdx
  HWND v17; // rax
  UINT v18; // eax
  HWND v19; // rcx
  HWND v20; // rax
  HWND v21; // rax
  _WORD v22[2]; // [rsp+30h] [rbp-28h] BYREF
  __int16 v23; // [rsp+34h] [rbp-24h] BYREF
  LPARAM lParam[2]; // [rsp+38h] [rbp-20h] BYREF

  v1 = 0;
  if ( this[91] )
  {
    DlgItem = GetDlgItem(this[14], 1690);
    if ( DlgItem )
    {
      v4 = SendMessageW(DlgItem, 0x147u, 0, 0);
      v5 = this[14];
      v6 = v4;
      *(_OWORD *)lParam = 0;
      v7 = GetDlgItem(v5, 1691);
      if ( v7 && !(unsigned int)SendMessageW(v7, 0x1001u, 0, (LPARAM)lParam) )
        *((_DWORD *)this[91] + 10) = lParam[1];
      if ( v6 )
      {
        v8 = v6 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                v12 = v11 - 1;
                if ( v12 )
                {
                  if ( v12 == 1 )
                  {
                    *((_DWORD *)this[91] + 14) = 5;
                    v13 = SendDlgItemMessageW(this[14], 1767, 0x468u, 0, 0);
                    v14 = this[83];
                    v23 = 0;
                    v15 = v13;
                    v22[0] = 0;
                    (*(void (__fastcall **)(HWND, __int16 *, _WORD *))(*(_QWORD *)v14 + 88LL))(v14, &v23, v22);
                    if ( HIWORD(v15) )
                      v16 = 10;
                    else
                      v16 = (unsigned __int16)v15;
                    (*(void (__fastcall **)(HWND, __int64, _QWORD))(*(_QWORD *)this[83] + 80LL))(this[83], v16, v22[0]);
                  }
                }
                else
                {
                  *((_DWORD *)this[91] + 14) = 7;
                }
              }
              else
              {
                *((_DWORD *)this[91] + 14) = 6;
              }
            }
            else
            {
              *((_DWORD *)this[91] + 14) = 0;
              v17 = GetDlgItem(this[14], 1763);
              if ( v17 && !(unsigned int)SendMessageW(v17, 0x1001u, 0, (LPARAM)lParam) )
              {
                *((_DWORD *)this[91] + 7) = lParam[0];
                *((_WORD *)this[91] + 16) = HIWORD(lParam[0]);
              }
            }
          }
          else
          {
            v18 = IsDlgButtonChecked(this[14], 1732);
            v19 = this[91];
            if ( v18 == 1 )
            {
              *((_DWORD *)v19 + 14) = 3;
              *((_DWORD *)this[91] + 15) = 1 << (SendDlgItemMessageW(this[14], 1734, 0x468u, 0, 0) - 1);
            }
            else
            {
              *((_DWORD *)v19 + 14) = 4;
              v20 = GetDlgItem(this[14], 1737);
              if ( v20 )
                *((_WORD *)this[91] + 30) = dword_180023474[2 * (int)SendMessageW(v20, 0x147u, 0, 0)];
              v21 = GetDlgItem(this[14], 1738);
              if ( v21 )
                *((_WORD *)this[91] + 31) = dword_180023418[3 * (int)SendMessageW(v21, 0x147u, 0, 0)];
            }
          }
        }
        else
        {
          *((_DWORD *)this[91] + 14) = 2;
          *((_WORD *)this[91] + 30) = SendDlgItemMessageW(this[14], 1714, 0x468u, 0, 0);
          *((_WORD *)this[91] + 31) = 0;
          do
          {
            if ( IsDlgButtonChecked(this[14], *(&g_aDayData + 3 * (int)v1)) == 1 )
              *((_WORD *)this[91] + 31) |= LOWORD(dword_180023418[3 * v1]);
            ++v1;
          }
          while ( v1 < 7 );
        }
      }
      else
      {
        *((_DWORD *)this[91] + 14) = 1;
        *((_WORD *)this[91] + 30) = SendDlgItemMessageW(this[14], 1704, 0x468u, 0, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x1800161c0  push    rbp
0x1800161c2  push    rbx
0x1800161c3  push    rsi
0x1800161c4  push    rdi
0x1800161c5  push    r14
0x1800161c7  push    r15
0x1800161c9  mov     rbp, rsp
0x1800161cc  sub     rsp, 58h
0x1800161d0  mov     rax, cs:__security_cookie
0x1800161d7  xor     rax, rsp
0x1800161da  mov     [rbp+var_10], rax
0x1800161de  xor     esi, esi
0x1800161e0  mov     rbx, rcx
0x1800161e3  cmp     [rcx+2D8h], rsi
0x1800161ea  jz      loc_180016577
0x1800161f0  mov     rcx, [rcx+70h]; hDlg
0x1800161f4  mov     edx, 69Ah; nIDDlgItem
0x1800161f9  call    cs:__imp_GetDlgItem
0x1800161ff  test    rax, rax
0x180016202  jz      loc_180016577
0x180016208  mov     r15d, 147h
0x18001620e  xor     r9d, r9d; lParam
0x180016211  mov     edx, r15d; Msg
0x180016214  xor     r8d, r8d; wParam
0x180016217  mov     rcx, rax; hWnd
0x18001621a  call    cs:__imp_SendMessageW
0x180016220  mov     rcx, [rbx+70h]; hDlg
0x180016224  xorps   xmm0, xmm0
0x180016227  mov     edx, 69Bh; nIDDlgItem
0x18001622c  mov     rdi, rax
0x18001622f  movups  xmmword ptr [rbp+lParam], xmm0
0x180016233  call    cs:__imp_GetDlgItem
0x180016239  mov     r14d, 1001h
0x18001623f  test    rax, rax
0x180016242  jz      short loc_180016279
0x180016244  lea     r9, [rbp+lParam]; lParam
0x180016248  xor     r8d, r8d; wParam
0x18001624b  mov     edx, r14d; Msg
0x18001624e  mov     rcx, rax; hWnd
0x180016251  call    cs:__imp_SendMessageW
0x180016257  test    eax, eax
0x180016259  jnz     short loc_180016279
0x18001625b  mov     rcx, [rbx+2D8h]
0x180016262  movzx   eax, word ptr [rbp+lParam+8]
0x180016266  mov     [rcx+28h], ax
0x18001626a  mov     rcx, [rbx+2D8h]
0x180016271  movzx   eax, word ptr [rbp+lParam+0Ah]
0x180016275  mov     [rcx+2Ah], ax
0x180016279  test    edi, edi
0x18001627b  jz      loc_180016541
0x180016281  sub     edi, 1
0x180016284  jz      loc_1800164BA
0x18001628a  sub     edi, 1
0x18001628d  jz      loc_1800163CE
0x180016293  sub     edi, 1
0x180016296  jz      loc_18001635F
0x18001629c  sub     edi, 1
0x18001629f  jz      loc_18001634C
0x1800162a5  sub     edi, 1
0x1800162a8  jz      loc_180016339
0x1800162ae  cmp     edi, 1
0x1800162b1  jnz     loc_180016577
0x1800162b7  mov     rax, [rbx+2D8h]
0x1800162be  xor     r9d, r9d; wParam
0x1800162c1  mov     edx, 6E7h; nIDDlgItem
0x1800162c6  mov     [rsp+58h+var_38], rsi; lParam
0x1800162cb  mov     r8d, 468h; Msg
0x1800162d1  mov     dword ptr [rax+38h], 5
0x1800162d8  mov     rcx, [rbx+70h]; hDlg
0x1800162dc  call    cs:__imp_SendDlgItemMessageW
0x1800162e2  mov     rcx, [rbx+298h]
0x1800162e9  lea     r8, [rbp+var_28]
0x1800162ed  mov     [rbp+var_24], si
0x1800162f1  mov     rdi, rax
0x1800162f4  mov     [rbp+var_28], si
0x1800162f8  mov     rdx, [rcx]
0x1800162fb  mov     rax, [rdx+58h]
0x1800162ff  lea     rdx, [rbp+var_24]
0x180016303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016308  mov     rcx, [rbx+298h]
0x18001630f  mov     eax, edi
0x180016311  movzx   r8d, [rbp+var_28]
0x180016316  shr     eax, 10h
0x180016319  test    ax, ax
0x18001631c  mov     r9, [rcx]
0x18001631f  mov     rax, [r9+50h]
0x180016323  jz      short loc_18001632C
0x180016325  mov     edx, 0Ah
0x18001632a  jmp     short loc_18001632F
0x18001632c  movzx   edx, di
0x18001632f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016334  jmp     loc_180016577
0x180016339  mov     rax, [rbx+2D8h]
0x180016340  mov     dword ptr [rax+38h], 7
0x180016347  jmp     loc_180016577
0x18001634c  mov     rax, [rbx+2D8h]
0x180016353  mov     dword ptr [rax+38h], 6
0x18001635a  jmp     loc_180016577
0x18001635f  mov     rax, [rbx+2D8h]
0x180016366  mov     edx, 6E3h; nIDDlgItem
0x18001636b  mov     [rax+38h], esi
0x18001636e  mov     rcx, [rbx+70h]; hDlg
0x180016372  call    cs:__imp_GetDlgItem
0x180016378  test    rax, rax
0x18001637b  jz      loc_180016577
0x180016381  lea     r9, [rbp+lParam]; lParam
0x180016385  xor     r8d, r8d; wParam
0x180016388  mov     edx, r14d; Msg
0x18001638b  mov     rcx, rax; hWnd
0x18001638e  call    cs:__imp_SendMessageW
0x180016394  test    eax, eax
0x180016396  jnz     loc_180016577
0x18001639c  mov     rcx, [rbx+2D8h]
0x1800163a3  movzx   eax, word ptr [rbp+lParam]
0x1800163a7  mov     [rcx+1Ch], ax
0x1800163ab  mov     rcx, [rbx+2D8h]
0x1800163b2  movzx   eax, word ptr [rbp+lParam+2]
0x1800163b6  mov     [rcx+1Eh], ax
0x1800163ba  mov     rcx, [rbx+2D8h]
0x1800163c1  movzx   eax, word ptr [rbp+lParam+6]
0x1800163c5  mov     [rcx+20h], ax
0x1800163c9  jmp     loc_180016577
0x1800163ce  mov     rcx, [rbx+70h]; hDlg
0x1800163d2  mov     edx, 6C4h; nIDButton
0x1800163d7  call    cs:__imp_IsDlgButtonChecked
0x1800163dd  mov     rcx, [rbx+2D8h]
0x1800163e4  mov     edi, 1
0x1800163e9  cmp     eax, edi
0x1800163eb  jnz     short loc_180016426
0x1800163ed  mov     dword ptr [rcx+38h], 3
0x1800163f4  xor     r9d, r9d; wParam
0x1800163f7  mov     rcx, [rbx+70h]; hDlg
0x1800163fb  mov     edx, 6C6h; nIDDlgItem
0x180016400  mov     r8d, 468h; Msg
0x180016406  mov     [rsp+58h+var_38], rsi; lParam
0x18001640b  call    cs:__imp_SendDlgItemMessageW
0x180016411  sub     eax, edi
0x180016413  mov     cl, al
0x180016415  mov     rax, [rbx+2D8h]
0x18001641c  shl     edi, cl
0x18001641e  mov     [rax+3Ch], edi
0x180016421  jmp     loc_180016577
0x180016426  mov     dword ptr [rcx+38h], 4
0x18001642d  mov     edx, 6C9h; nIDDlgItem
0x180016432  mov     rcx, [rbx+70h]; hDlg
0x180016436  call    cs:__imp_GetDlgItem
0x18001643c  lea     r14, __ImageBase
0x180016443  test    rax, rax
0x180016446  jz      short loc_180016470
0x180016448  xor     r9d, r9d; lParam
0x18001644b  xor     r8d, r8d; wParam
0x18001644e  mov     edx, r15d; Msg
0x180016451  mov     rcx, rax; hWnd
0x180016454  call    cs:__imp_SendMessageW
0x18001645a  mov     rcx, [rbx+2D8h]
0x180016461  cdqe
0x180016463  movzx   eax, word ptr rva dword_180023474[r14+rax*8]
0x18001646c  mov     [rcx+3Ch], ax
0x180016470  mov     rcx, [rbx+70h]; hDlg
0x180016474  mov     edx, 6CAh; nIDDlgItem
0x180016479  call    cs:__imp_GetDlgItem
0x18001647f  test    rax, rax
0x180016482  jz      loc_180016577
0x180016488  xor     r9d, r9d; lParam
0x18001648b  xor     r8d, r8d; wParam
0x18001648e  mov     edx, r15d; Msg
0x180016491  mov     rcx, rax; hWnd
0x180016494  call    cs:__imp_SendMessageW
0x18001649a  movsxd  rcx, eax
0x18001649d  lea     rax, [rcx+rcx*2]
0x1800164a1  mov     rcx, [rbx+2D8h]
0x1800164a8  movzx   eax, word ptr rva dword_180023418[r14+rax*4]
0x1800164b1  mov     [rcx+3Eh], ax
0x1800164b5  jmp     loc_180016577
0x1800164ba  mov     rax, [rbx+2D8h]
0x1800164c1  xor     r9d, r9d; wParam
0x1800164c4  mov     edx, 6B2h; nIDDlgItem
0x1800164c9  mov     [rsp+58h+var_38], rsi; lParam
0x1800164ce  mov     r8d, 468h; Msg
0x1800164d4  mov     dword ptr [rax+38h], 2
0x1800164db  mov     rcx, [rbx+70h]; hDlg
0x1800164df  call    cs:__imp_SendDlgItemMessageW
0x1800164e5  mov     rcx, [rbx+2D8h]
0x1800164ec  lea     r14, __ImageBase
0x1800164f3  mov     edi, 1
0x1800164f8  mov     [rcx+3Ch], ax
0x1800164fc  mov     rcx, [rbx+2D8h]
0x180016503  mov     [rcx+3Eh], si
0x180016507  mov     rcx, [rbx+70h]; hDlg
0x18001650b  movsxd  rax, esi
0x18001650e  lea     r15, [rax+rax*2]
0x180016512  mov     edx, rva ?g_aDayData@@3PAUSDayData@@A[r14+r15*4]; nIDButton
0x18001651a  call    cs:__imp_IsDlgButtonChecked
0x180016520  cmp     eax, edi
0x180016522  jnz     short loc_180016538
0x180016524  mov     rcx, [rbx+2D8h]
0x18001652b  movzx   eax, word ptr rva dword_180023418[r14+r15*4]
0x180016534  or      [rcx+3Eh], ax
0x180016538  add     esi, edi
0x18001653a  cmp     esi, 7
0x18001653d  jb      short loc_180016507
0x18001653f  jmp     short loc_180016577
0x180016541  mov     rax, [rbx+2D8h]
0x180016548  xor     r9d, r9d; wParam
0x18001654b  mov     edx, 6A8h; nIDDlgItem
0x180016550  mov     [rsp+58h+var_38], rsi; lParam
0x180016555  mov     r8d, 468h; Msg
0x18001655b  mov     dword ptr [rax+38h], 1
0x180016562  mov     rcx, [rbx+70h]; hDlg
0x180016566  call    cs:__imp_SendDlgItemMessageW
0x18001656c  mov     rcx, [rbx+2D8h]
0x180016573  mov     [rcx+3Ch], ax
0x180016577  mov     rcx, [rbp+var_10]
0x18001657b  xor     rcx, rsp; StackCookie
0x18001657e  call    __security_check_cookie
0x180016583  add     rsp, 58h
0x180016587  pop     r15
0x180016589  pop     r14
0x18001658b  pop     rdi
0x18001658c  pop     rsi
0x18001658d  pop     rbx
0x18001658e  pop     rbp
0x18001658f  retn
```
