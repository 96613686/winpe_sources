# CRasNewConnectionPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019080`
- end: `0x180019197`
- name: `?PageDlgProc@CRasNewConnectionPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `279`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180019080`

## import_xrefs

- `USER32!PostMessageW` at `0x180019163`
- `USER32!PostMessageW` at `0x180019183`
- `USER32!PostMessageW` at `0x180019163`
- `USER32!PostMessageW` at `0x180019183`
- `USER32!GetPropW` at `0x1800190cf`
- `USER32!GetPropW` at `0x1800190cf`
- `USER32!RemovePropW` at `0x1800190c7`
- `USER32!RemovePropW` at `0x1800190c7`
- `USER32!SetPropW` at `0x1800190b0`
- `USER32!SetPropW` at `0x1800190b0`
- `USER32!SendMessageW` at `0x180019125`
- `USER32!SendMessageW` at `0x180019125`
- `USER32!GetParent` at `0x1800190fa`
- `USER32!GetParent` at `0x18001910c`
- `USER32!GetParent` at `0x180019130`
- `USER32!GetParent` at `0x18001914f`
- `USER32!GetParent` at `0x18001916c`
- `USER32!GetParent` at `0x1800190fa`
- `USER32!GetParent` at `0x18001910c`
- `USER32!GetParent` at `0x180019130`
- `USER32!GetParent` at `0x18001914f`
- `USER32!GetParent` at `0x18001916c`

## pseudocode

```c
__int64 __fastcall CRasNewConnectionPage::PageDlgProc(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // rdi
  __int64 v8; // rbx
  __int64 v9; // rbx
  HWND Parent; // rax
  GUID *v11; // r9
  HWND v13; // rax
  HWND v14; // rax

  v4 = (_DWORD *)a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = *(_DWORD **)(a4 + 48);
    SetPropW(hWnd, L"_Win32_this_", v4);
    return 0;
  }
  if ( a2 == 2 )
  {
    RemovePropW(hWnd, L"_Win32_this_");
    return 0;
  }
  GetPropW(hWnd, L"_Win32_this_");
  if ( a2 != 78 )
  {
    if ( a2 == 273 )
    {
      v8 = a3 - 2051;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          if ( v9 != 1 )
            return 0;
          Parent = GetParent(hWnd);
          v11 = &CLSID_PPPoEHookPage;
        }
        else
        {
          Parent = GetParent(hWnd);
          v11 = &CLSID_VPNHookPage;
        }
      }
      else
      {
        Parent = GetParent(hWnd);
        v11 = &CLSID_DialupCTWHookPage;
      }
      SendMessageW(Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)v11);
    }
    return 0;
  }
  if ( v4[4] != -200 )
    return 0;
  v13 = GetParent(hWnd);
  PostMessageW(v13, 0x470u, 0, 0);
  v14 = GetParent(hWnd);
  PostMessageW(v14, 0x48Au, 0, 6);
  return 1;
}

```

## disassembly

```asm
0x180019080  push    rbx
0x180019082  push    rbp
0x180019083  push    rsi
0x180019084  push    rdi
0x180019085  sub     rsp, 28h
0x180019089  mov     rdi, r9
0x18001908c  mov     rbx, r8
0x18001908f  mov     ebp, edx
0x180019091  mov     rsi, rcx
0x180019094  cmp     edx, 110h
0x18001909a  jnz     short loc_1800190BB
0x18001909c  cmp     dword ptr [r9], 68h ; 'h'
0x1800190a0  jnz     short loc_1800190A6
0x1800190a2  mov     rdi, [r9+30h]
0x1800190a6  mov     r8, rdi; hData
0x1800190a9  lea     rdx, aWin32This_3; "_Win32_this_"
0x1800190b0  call    cs:__imp_SetPropW
0x1800190b6  jmp     loc_180019148
0x1800190bb  lea     rdx, aWin32This_3; "_Win32_this_"
0x1800190c2  cmp     ebp, 2
0x1800190c5  jnz     short loc_1800190CF
0x1800190c7  call    cs:__imp_RemovePropW
0x1800190cd  jmp     short loc_180019148
0x1800190cf  call    cs:__imp_GetPropW
0x1800190d5  cmp     ebp, 4Eh ; 'N'
0x1800190d8  jz      short loc_18001913F
0x1800190da  cmp     ebp, 111h
0x1800190e0  jnz     short loc_180019148
0x1800190e2  sub     rbx, 803h
0x1800190e9  jz      short loc_18001912D
0x1800190eb  sub     rbx, 1
0x1800190ef  jz      short loc_180019109
0x1800190f1  cmp     rbx, 1
0x1800190f5  jnz     short loc_180019148
0x1800190f7  mov     rcx, rsi; hWnd
0x1800190fa  call    cs:__imp_GetParent
0x180019100  lea     r9, CLSID_PPPoEHookPage
0x180019107  jmp     short loc_180019119
0x180019109  mov     rcx, rsi; hWnd
0x18001910c  call    cs:__imp_GetParent
0x180019112  lea     r9, CLSID_VPNHookPage; lParam
0x180019119  mov     rcx, rax; hWnd
0x18001911c  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180019120  mov     edx, 465h; Msg
0x180019125  call    cs:__imp_SendMessageW
0x18001912b  jmp     short loc_180019148
0x18001912d  mov     rcx, rsi; hWnd
0x180019130  call    cs:__imp_GetParent
0x180019136  lea     r9, CLSID_DialupCTWHookPage
0x18001913d  jmp     short loc_180019119
0x18001913f  cmp     dword ptr [rdi+10h], 0FFFFFF38h
0x180019146  jz      short loc_18001914C
0x180019148  xor     eax, eax
0x18001914a  jmp     short loc_18001918E
0x18001914c  mov     rcx, rsi; hWnd
0x18001914f  call    cs:__imp_GetParent
0x180019155  xor     r9d, r9d; lParam
0x180019158  xor     r8d, r8d; wParam
0x18001915b  mov     rcx, rax; hWnd
0x18001915e  mov     edx, 470h; Msg
0x180019163  call    cs:__imp_PostMessageW
0x180019169  mov     rcx, rsi; hWnd
0x18001916c  call    cs:__imp_GetParent
0x180019172  mov     r9d, 6; lParam
0x180019178  xor     r8d, r8d; wParam
0x18001917b  mov     rcx, rax; hWnd
0x18001917e  mov     edx, 48Ah; Msg
0x180019183  call    cs:__imp_PostMessageW
0x180019189  mov     eax, 1
0x18001918e  add     rsp, 28h
0x180019192  pop     rdi
0x180019193  pop     rsi
0x180019194  pop     rbp
0x180019195  pop     rbx
0x180019196  retn
```
