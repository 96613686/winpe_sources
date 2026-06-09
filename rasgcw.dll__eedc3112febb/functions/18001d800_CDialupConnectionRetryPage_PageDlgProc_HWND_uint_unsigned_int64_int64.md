# CDialupConnectionRetryPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001d800`
- end: `0x18001dab6`
- name: `?PageDlgProc@CDialupConnectionRetryPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `694`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180010c38`
- `0x18001d51c`
- `0x18001d754`
- `0x18001d800`
- `0x18001e0a0`
- `0x18002f382`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da66`
- `USER32!PostMessageW` at `0x18001d9aa`
- `USER32!PostMessageW` at `0x18001d9aa`
- `USER32!GetPropW` at `0x18001d857`
- `USER32!GetPropW` at `0x18001d857`
- `USER32!RemovePropW` at `0x18001d84c`
- `USER32!RemovePropW` at `0x18001d84c`
- `USER32!SetPropW` at `0x18001d835`
- `USER32!SetPropW` at `0x18001d835`
- `USER32!SetWindowLongW` at `0x18001da9d`
- `USER32!SetWindowLongW` at `0x18001da9d`
- `USER32!GetDlgItem` at `0x18001d970`
- `USER32!GetDlgItem` at `0x18001d9cd`
- `USER32!GetDlgItem` at `0x18001da25`
- `USER32!GetDlgItem` at `0x18001d970`
- `USER32!GetDlgItem` at `0x18001d9cd`
- `USER32!GetDlgItem` at `0x18001da25`
- `USER32!SendMessageW` at `0x18001d91c`
- `USER32!SendMessageW` at `0x18001d984`
- `USER32!SendMessageW` at `0x18001d9e5`
- `USER32!SendMessageW` at `0x18001da3b`
- `USER32!SendMessageW` at `0x18001d91c`
- `USER32!SendMessageW` at `0x18001d984`
- `USER32!SendMessageW` at `0x18001d9e5`
- `USER32!SendMessageW` at `0x18001da3b`
- `USER32!GetParent` at `0x18001d907`
- `USER32!GetParent` at `0x18001d995`
- `USER32!GetParent` at `0x18001d907`
- `USER32!GetParent` at `0x18001d995`
- `rtutils!TracePrintfExA` at `0x18001da81`
- `rtutils!TracePrintfExA` at `0x18001da81`

## pseudocode

```c
__int64 __fastcall CDialupConnectionRetryPage::PageDlgProc(
        HWND a1,
        int a2,
        unsigned __int16 a3,
        CDialupConnectionRetryPage *a4)
{
  CDialupConnectionRetryPage *v4; // rbx
  CDialupConnectionRetryPage *PropW; // rax
  CDialupConnectionRetryPage *v9; // rbp
  int v10; // esi
  int v11; // esi
  unsigned __int16 *v12; // r8
  HWND Parent; // rax
  HWND v15; // rax
  HWND v16; // rax
  HWND DlgItem; // rax
  __int64 v18; // rax
  HWND v19; // rax
  DWORD v20; // eax
  DWORD LastError; // eax
  int lParam; // [rsp+30h] [rbp-88h] BYREF
  int lParam_4; // [rsp+34h] [rbp-84h]
  int v24; // [rsp+40h] [rbp-78h]
  __int64 v25; // [rsp+48h] [rbp-70h]
  int v26; // [rsp+50h] [rbp-68h]

  v4 = a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = (CDialupConnectionRetryPage *)*((_QWORD *)a4 + 6);
    SetPropW(a1, L"_Win32_this_", v4);
    goto LABEL_24;
  }
  if ( a2 == 2 )
  {
    RemovePropW(a1, L"_Win32_this_");
    return 0;
  }
  PropW = (CDialupConnectionRetryPage *)GetPropW(a1, L"_Win32_this_");
  v9 = PropW;
  v10 = a2 - 78;
  if ( v10 )
  {
    v11 = v10 - 194;
    if ( !v11 )
    {
      v4 = PropW;
LABEL_24:
      CDialupConnectionRetryPage::InitDialogControls(v4, a1);
      return 1;
    }
    if ( v11 == 1 )
    {
      switch ( a3 )
      {
        case 0x41Bu:
        case 0x41Cu:
        case 0x41Du:
        case 0x41Eu:
          v12 = (unsigned __int16 *)(*((_QWORD *)PropW + 13) + 264 * (a3 - 1051LL));
          break;
        case 0x425u:
          CDialupConnectionRetryPage::EnumerateRasModemDevices(PropW);
          if ( *((_DWORD *)v9 + 28) != 1 )
          {
            CDialupConnectionRetryPage::UpdateDialogControls(v9, a1);
            return 0;
          }
          v12 = (unsigned __int16 *)*((_QWORD *)v9 + 13);
          break;
        case 0x426u:
          memset_0((void *)(*((_QWORD *)PropW + 12) + 4436LL), 0, 0x202u);
LABEL_22:
          Parent = GetParent(a1);
          SendMessageW(Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, 0);
          return 0;
        default:
          return 0;
      }
      StringCchCopyW((unsigned __int16 *)(*((_QWORD *)v9 + 12) + 4436LL), 0x101u, v12);
      goto LABEL_22;
    }
    return 0;
  }
  if ( *((_DWORD *)v4 + 4) == -207 )
  {
    memset_0(&lParam, 0, 0x58u);
    DlgItem = GetDlgItem(a1, 1055);
    lParam_4 = SendMessageW(DlgItem, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
    if ( lParam_4 == -1 )
    {
      if ( g_dwTraceId != -1 )
      {
        LastError = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get selected item. Error = %d", LastError);
      }
    }
    else
    {
      v18 = *((_QWORD *)v9 + 12) + 4436LL;
      lParam = 9;
      v25 = v18;
      v24 = 2;
      v26 = 257;
      v19 = GetDlgItem(a1, 1055);
      if ( !(unsigned int)SendMessageW(v19, 0x104Bu, 0, (LPARAM)&lParam) && g_dwTraceId != -1 )
      {
        v20 = GetLastError();
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get selected item contents. Error = %d", v20);
      }
    }
    if ( !*(_WORD *)(*((_QWORD *)v9 + 12) + 4436LL) )
      SetWindowLongW(a1, 0, -1);
    return 1;
  }
  if ( *((_DWORD *)v4 + 4) != -200 )
  {
    if ( *((_DWORD *)v4 + 4) == -3 )
    {
      if ( *((_QWORD *)v4 + 1) == 1055 )
      {
        v15 = GetDlgItem(a1, 1055);
        if ( (unsigned int)SendMessageW(v15, 0x1032u, 0, 0) )
        {
          v16 = GetParent(a1);
          PostMessageW(v16, 0x471u, 1u, 0);
        }
      }
      return 1;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001d800  push    rbx
0x18001d802  push    rbp
0x18001d803  push    rsi
0x18001d804  push    rdi
0x18001d805  push    r14
0x18001d807  sub     rsp, 90h
0x18001d80e  mov     rbx, r9
0x18001d811  mov     r14, r8
0x18001d814  mov     esi, edx
0x18001d816  mov     rdi, rcx
0x18001d819  cmp     edx, 110h
0x18001d81f  jnz     short loc_18001D840
0x18001d821  cmp     dword ptr [r9], 68h ; 'h'
0x18001d825  jnz     short loc_18001D82B
0x18001d827  mov     rbx, [r9+30h]
0x18001d82b  mov     r8, rbx; hData
0x18001d82e  lea     rdx, aWin32This_9; "_Win32_this_"
0x18001d835  call    cs:__imp_SetPropW
0x18001d83b  jmp     loc_18001D927
0x18001d840  lea     rdx, aWin32This_9; "_Win32_this_"
0x18001d847  cmp     esi, 2
0x18001d84a  jnz     short loc_18001D857
0x18001d84c  call    cs:__imp_RemovePropW
0x18001d852  jmp     loc_18001D953
0x18001d857  call    cs:__imp_GetPropW
0x18001d85d  mov     rbp, rax
0x18001d860  sub     esi, 4Eh ; 'N'
0x18001d863  jz      loc_18001D937
0x18001d869  sub     esi, 0C2h
0x18001d86f  jz      loc_18001D924
0x18001d875  cmp     esi, 1
0x18001d878  jnz     loc_18001D953
0x18001d87e  movzx   eax, r14w
0x18001d882  mov     ecx, 41Bh
0x18001d887  mov     edx, eax
0x18001d889  sub     edx, ecx
0x18001d88b  jz      short loc_18001D8E1
0x18001d88d  sub     edx, esi
0x18001d88f  jz      short loc_18001D8E1
0x18001d891  sub     edx, esi
0x18001d893  jz      short loc_18001D8E1
0x18001d895  sub     edx, esi
0x18001d897  jz      short loc_18001D8E1
0x18001d899  sub     edx, 7
0x18001d89c  jz      short loc_18001D8C0
0x18001d89e  cmp     edx, esi
0x18001d8a0  jnz     loc_18001D953
0x18001d8a6  mov     rcx, [rbp+60h]
0x18001d8aa  xor     edx, edx; Val
0x18001d8ac  add     rcx, 1154h; void *
0x18001d8b3  mov     r8d, 202h; Size
0x18001d8b9  call    memset_0
0x18001d8be  jmp     short loc_18001D904
0x18001d8c0  mov     rcx, rbp; this
0x18001d8c3  call    ?EnumerateRasModemDevices@CDialupConnectionRetryPage@@AEAAXXZ; CDialupConnectionRetryPage::EnumerateRasModemDevices(void)
0x18001d8c8  cmp     dword ptr [rbp+70h], 1
0x18001d8cc  jnz     short loc_18001D8D4
0x18001d8ce  mov     r8, [rbp+68h]
0x18001d8d2  jmp     short loc_18001D8EF
0x18001d8d4  mov     rdx, rdi; HWND
0x18001d8d7  mov     rcx, rbp; this
0x18001d8da  call    ?UpdateDialogControls@CDialupConnectionRetryPage@@AEAAXPEAUHWND__@@@Z; CDialupConnectionRetryPage::UpdateDialogControls(HWND__ *)
0x18001d8df  jmp     short loc_18001D953
0x18001d8e1  sub     rax, rcx
0x18001d8e4  imul    r8, rax, 108h
0x18001d8eb  add     r8, [rbp+68h]; unsigned __int16 *
0x18001d8ef  mov     rcx, [rbp+60h]
0x18001d8f3  mov     edx, 101h; unsigned __int64
0x18001d8f8  add     rcx, 1154h; unsigned __int16 *
0x18001d8ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d904  mov     rcx, rdi; hWnd
0x18001d907  call    cs:__imp_GetParent
0x18001d90d  xor     r9d, r9d; lParam
0x18001d910  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001d914  mov     rcx, rax; hWnd
0x18001d917  mov     edx, 465h; Msg
0x18001d91c  call    cs:__imp_SendMessageW
0x18001d922  jmp     short loc_18001D953
0x18001d924  mov     rbx, rbp
0x18001d927  mov     rdx, rdi; HWND
0x18001d92a  mov     rcx, rbx; this
0x18001d92d  call    ?InitDialogControls@CDialupConnectionRetryPage@@AEAAXPEAUHWND__@@@Z; CDialupConnectionRetryPage::InitDialogControls(HWND__ *)
0x18001d932  jmp     loc_18001DAA3
0x18001d937  cmp     dword ptr [rbx+10h], 0FFFFFF31h
0x18001d93e  jz      short loc_18001D9B5
0x18001d940  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x18001d947  jz      loc_18001DAA3
0x18001d94d  cmp     dword ptr [rbx+10h], 0FFFFFFFDh
0x18001d951  jz      short loc_18001D95A
0x18001d953  xor     eax, eax
0x18001d955  jmp     loc_18001DAA8
0x18001d95a  cmp     qword ptr [rbx+8], 41Fh
0x18001d962  jnz     loc_18001DAA3
0x18001d968  mov     edx, 41Fh; nIDDlgItem
0x18001d96d  mov     rcx, rdi; hDlg
0x18001d970  call    cs:__imp_GetDlgItem
0x18001d976  xor     r9d, r9d; lParam
0x18001d979  xor     r8d, r8d; wParam
0x18001d97c  mov     rcx, rax; hWnd
0x18001d97f  mov     edx, 1032h; Msg
0x18001d984  call    cs:__imp_SendMessageW
0x18001d98a  test    eax, eax
0x18001d98c  jz      loc_18001DAA3
0x18001d992  mov     rcx, rdi; hWnd
0x18001d995  call    cs:__imp_GetParent
0x18001d99b  xor     r9d, r9d; lParam
0x18001d99e  mov     edx, 471h; Msg
0x18001d9a3  mov     rcx, rax; hWnd
0x18001d9a6  lea     r8d, [r9+1]; wParam
0x18001d9aa  call    cs:__imp_PostMessageW
0x18001d9b0  jmp     loc_18001DAA3
0x18001d9b5  xor     edx, edx; Val
0x18001d9b7  lea     rcx, [rsp+0B8h+lParam]; void *
0x18001d9bc  lea     r8d, [rdx+58h]; Size
0x18001d9c0  call    memset_0
0x18001d9c5  mov     edx, 41Fh; nIDDlgItem
0x18001d9ca  mov     rcx, rdi; hDlg
0x18001d9cd  call    cs:__imp_GetDlgItem
0x18001d9d3  mov     r9d, 2; lParam
0x18001d9d9  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001d9dd  mov     rcx, rax; hWnd
0x18001d9e0  mov     edx, 100Ch; Msg
0x18001d9e5  call    cs:__imp_SendMessageW
0x18001d9eb  xor     ebx, ebx
0x18001d9ed  mov     dword ptr [rsp+0B8h+lParam+4], eax
0x18001d9f1  cmp     eax, 0FFFFFFFFh
0x18001d9f4  jz      short loc_18001DA5D
0x18001d9f6  mov     rax, [rbp+60h]
0x18001d9fa  mov     edx, 41Fh; nIDDlgItem
0x18001d9ff  add     rax, 1154h
0x18001da05  mov     dword ptr [rsp+0B8h+lParam], 9
0x18001da0d  mov     rcx, rdi; hDlg
0x18001da10  mov     [rsp+0B8h+var_70], rax
0x18001da15  mov     [rsp+0B8h+var_78], 2
0x18001da1d  mov     [rsp+0B8h+var_68], 101h
0x18001da25  call    cs:__imp_GetDlgItem
0x18001da2b  lea     r9, [rsp+0B8h+lParam]; lParam
0x18001da30  xor     r8d, r8d; wParam
0x18001da33  mov     rcx, rax; hWnd
0x18001da36  mov     edx, 104Bh; Msg
0x18001da3b  call    cs:__imp_SendMessageW
0x18001da41  test    eax, eax
0x18001da43  jnz     short loc_18001DA87
0x18001da45  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18001da4c  jz      short loc_18001DA87
0x18001da4e  call    cs:__imp_GetLastError
0x18001da54  lea     r8, aFailedToGetSel; "Failed to get selected item contents. E"...
0x18001da5b  jmp     short loc_18001DA73
0x18001da5d  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18001da64  jz      short loc_18001DA87
0x18001da66  call    cs:__imp_GetLastError
0x18001da6c  lea     r8, aFailedToGetSel_0; "Failed to get selected item. Error = %d"
0x18001da73  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001da79  mov     r9d, eax
0x18001da7c  mov     edx, 0Ch; dwFlags
0x18001da81  call    cs:__imp_TracePrintfExA
0x18001da87  mov     rax, [rbp+60h]
0x18001da8b  cmp     [rax+1154h], bx
0x18001da92  jnz     short loc_18001DAA3
0x18001da94  or      r8d, 0FFFFFFFFh; dwNewLong
0x18001da98  xor     edx, edx; nIndex
0x18001da9a  mov     rcx, rdi; hWnd
0x18001da9d  call    cs:__imp_SetWindowLongW
0x18001daa3  mov     eax, 1
0x18001daa8  add     rsp, 90h
0x18001daaf  pop     r14
0x18001dab1  pop     rdi
0x18001dab2  pop     rsi
0x18001dab3  pop     rbp
0x18001dab4  pop     rbx
0x18001dab5  retn
```
