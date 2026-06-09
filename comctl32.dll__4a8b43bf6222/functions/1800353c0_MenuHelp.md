# MenuHelp

- ea: `0x1800353c0`
- end: `0x1800355d0`
- name: `MenuHelp`
- size: `528`
- prototype: `void __stdcall(UINT uMsg, WPARAM wParam, LPARAM lParam, HMENU hMainMenu, HINSTANCE hInst, HWND hwndStatus, UINT *lpwIDs)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800115f0`
- `0x18001d894`
- `0x1800353c0`
- `0x18008ea60`

## import_xrefs

- `USER32!SendMessageW` at `0x18003543b`
- `USER32!SendMessageW` at `0x18003557b`
- `USER32!SendMessageW` at `0x180035590`
- `USER32!SendMessageW` at `0x18003543b`
- `USER32!SendMessageW` at `0x18003557b`
- `USER32!SendMessageW` at `0x180035590`
- `USER32!LoadStringW` at `0x18003555d`
- `USER32!LoadStringW` at `0x18003555d`
- `USER32!UpdateWindow` at `0x1800355a0`
- `USER32!UpdateWindow` at `0x1800355a0`
- `USER32!GetMenuItemID` at `0x1800354e7`
- `USER32!GetMenuItemID` at `0x1800354e7`
- `USER32!GetMenuItemCount` at `0x1800354db`
- `USER32!GetMenuItemCount` at `0x1800354db`
- `USER32!GetMenuItemInfoW` at `0x18003548f`
- `USER32!GetMenuItemInfoW` at `0x18003548f`

## pseudocode

```c
void __stdcall MenuHelp(
        UINT uMsg,
        WPARAM wParam,
        LPARAM lParam,
        HMENU hMainMenu,
        HINSTANCE hInst,
        HWND hwndStatus,
        UINT *lpwIDs)
{
  WPARAM v9; // rdi
  int v11; // ebx
  UINT *i; // rax
  int MenuItemCount; // eax
  UINT v14; // eax
  UINT v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  tagMENUITEMINFOW mii; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF

  if ( uMsg == 287 )
  {
    v9 = wParam >> 16;
    LOWORD(v11) = wParam;
    if ( WORD1(wParam) == 0xFFFF && !lParam )
    {
      SendMessageW(hwndStatus, 0x409u, 0, 0);
      return;
    }
    v16 = 1;
    Buffer[0] = 0;
    memset(&mii, 0, sizeof(mii));
    v11 = (unsigned __int16)v11;
    mii.cbSize = 80;
    mii.fMask = 16;
    mii.cch = 0;
    if ( GetMenuItemInfoW((HMENU)lParam, (unsigned __int16)v11, 1, &mii) )
      mii.fState = (mii.fType >> 3) & 0x400;
    if ( (v9 & 0x800) == 0 )
    {
      if ( (v9 & 0x10) != 0 )
      {
        v16 = 0;
        for ( i = lpwIDs + 2; *i; i += 2 )
        {
          if ( i[1] == (unsigned __int16)v11 )
          {
            v14 = *i;
            goto LABEL_27;
          }
        }
        if ( (HMENU)lParam == hMainMenu )
        {
          MenuItemCount = GetMenuItemCount(hMainMenu);
          if ( GetMenuItemID(hMainMenu, MenuItemCount - 1) == 61728 )
          {
            if ( !(_WORD)v11 )
            {
LABEL_16:
              v14 = -28688;
              goto LABEL_17;
            }
            v11 = (unsigned __int16)v11 - 1;
          }
          v15 = lpwIDs[1];
LABEL_26:
          v14 = v11 + v15;
          goto LABEL_27;
        }
        if ( (v9 & 0x2000) != 0 )
          goto LABEL_16;
      }
      else
      {
        if ( (unsigned __int16)v11 < 0xF000u )
        {
          v15 = *lpwIDs;
          goto LABEL_26;
        }
        v14 = (unsigned __int16)v11 - 28672;
LABEL_17:
        hInst = g_hinst;
LABEL_27:
        if ( hInst == g_hinst )
          LocalizedLoadString(v14, Buffer, 256);
        else
          LoadStringW(hInst, v14, Buffer, 256);
      }
    }
    SendMessageW(hwndStatus, 0x40Bu, mii.fState | 0x1FFLL, (LPARAM)Buffer);
    SendMessageW(hwndStatus, 0x409u, 1u, 0);
    if ( v16 )
      UpdateWindow(hwndStatus);
  }
}

```

## disassembly

```asm
0x1800353c0  cmp     ecx, 11Fh
0x1800353c6  jnz     locret_1800355CF
0x1800353cc  mov     [rsp-8+arg_0], rbx
0x1800353d1  push    rbp
0x1800353d2  push    rsi
0x1800353d3  push    rdi
0x1800353d4  push    r12
0x1800353d6  push    r13
0x1800353d8  push    r14
0x1800353da  push    r15
0x1800353dc  lea     rbp, [rsp-190h]
0x1800353e4  sub     rsp, 290h
0x1800353eb  mov     rax, cs:__security_cookie
0x1800353f2  xor     rax, rsp
0x1800353f5  mov     [rbp+1C0h+var_40], rax
0x1800353fc  mov     rsi, [rbp+1C0h+arg_20]
0x180035403  mov     rdi, rdx
0x180035406  mov     r14, [rbp+1C0h+hWnd]
0x18003540d  mov     eax, 0FFFFh
0x180035412  mov     r15, [rbp+1C0h+arg_30]
0x180035419  mov     r13, r9
0x18003541c  shr     rdi, 10h
0x180035420  mov     r12, r8
0x180035423  mov     rbx, rdx
0x180035426  cmp     di, ax
0x180035429  jnz     short loc_180035446
0x18003542b  test    r8, r8
0x18003542e  jnz     short loc_180035446
0x180035430  xor     r9d, r9d; lParam
0x180035433  mov     edx, 409h; Msg
0x180035438  mov     rcx, r14; hWnd
0x18003543b  call    cs:__imp_SendMessageW
0x180035441  jmp     loc_1800355A6
0x180035446  xor     eax, eax
0x180035448  mov     [rsp+2C0h+var_2A0], 1
0x180035450  xor     edx, edx; Val
0x180035452  mov     [rbp+1C0h+Buffer], ax
0x180035456  lea     rcx, [rsp+2C0h+mii]; void *
0x18003545b  lea     r8d, [rax+50h]; Size
0x18003545f  call    memset
0x180035464  movzx   ebx, bx
0x180035467  lea     r9, [rsp+2C0h+mii]; lpmii
0x18003546c  mov     edx, ebx; item
0x18003546e  mov     [rsp+2C0h+mii.cbSize], 50h ; 'P'
0x180035476  mov     r8d, 1; fByPosition
0x18003547c  mov     [rsp+2C0h+mii.fMask], 10h
0x180035484  mov     rcx, r12; hmenu
0x180035487  mov     [rsp+2C0h+mii.cch], 0
0x18003548f  call    cs:__imp_GetMenuItemInfoW
0x180035495  xor     ecx, ecx
0x180035497  test    eax, eax
0x180035499  jz      short loc_1800354AB
0x18003549b  mov     eax, [rsp+2C0h+mii.fType]
0x18003549f  shr     eax, 3
0x1800354a2  and     eax, 400h
0x1800354a7  mov     [rsp+2C0h+mii.fState], eax
0x1800354ab  bt      di, 0Bh
0x1800354b0  jb      loc_180035563
0x1800354b6  test    dil, 10h
0x1800354ba  jz      short loc_18003551B
0x1800354bc  mov     [rsp+2C0h+var_2A0], ecx
0x1800354c0  lea     rax, [r15+8]
0x1800354c4  jmp     short loc_1800354CF
0x1800354c6  cmp     [rax+4], ebx
0x1800354c9  jz      short loc_180035506
0x1800354cb  add     rax, 8
0x1800354cf  cmp     [rax], ecx
0x1800354d1  jnz     short loc_1800354C6
0x1800354d3  cmp     r12, r13
0x1800354d6  jnz     short loc_180035512
0x1800354d8  mov     rcx, r13; hMenu
0x1800354db  call    cs:__imp_GetMenuItemCount
0x1800354e1  mov     rcx, r13; hMenu
0x1800354e4  lea     edx, [rax-1]; nPos
0x1800354e7  call    cs:__imp_GetMenuItemID
0x1800354ed  cmp     eax, 0F120h
0x1800354f2  jnz     short loc_18003550C
0x1800354f4  test    ebx, ebx
0x1800354f6  jnz     short loc_18003550A
0x1800354f8  mov     eax, 0FFFF8FF0h
0x1800354fd  mov     rsi, cs:g_hinst
0x180035504  jmp     short loc_180035532
0x180035506  mov     eax, [rax]
0x180035508  jmp     short loc_180035532
0x18003550a  dec     ebx
0x18003550c  mov     eax, [r15+4]
0x180035510  jmp     short loc_180035530
0x180035512  bt      di, 0Dh
0x180035517  jnb     short loc_180035563
0x180035519  jmp     short loc_1800354F8
0x18003551b  mov     eax, 0F000h
0x180035520  cmp     bx, ax
0x180035523  jb      short loc_18003552D
0x180035525  lea     eax, [rbx-7000h]
0x18003552b  jmp     short loc_1800354FD
0x18003552d  mov     eax, [r15]
0x180035530  add     eax, ebx
0x180035532  cmp     rsi, cs:g_hinst
0x180035539  jnz     short loc_18003554E
0x18003553b  mov     r8d, 100h
0x180035541  lea     rdx, [rbp+1C0h+Buffer]
0x180035545  mov     ecx, eax
0x180035547  call    LocalizedLoadString
0x18003554c  jmp     short loc_180035563
0x18003554e  mov     r9d, 100h; cchBufferMax
0x180035554  lea     r8, [rbp+1C0h+Buffer]; lpBuffer
0x180035558  mov     edx, eax; uID
0x18003555a  mov     rcx, rsi; hInstance
0x18003555d  call    cs:__imp_LoadStringW
0x180035563  mov     r8d, [rsp+2C0h+mii.fState]
0x180035568  lea     r9, [rbp+1C0h+Buffer]; lParam
0x18003556c  or      r8, 1FFh; wParam
0x180035573  mov     edx, 40Bh; Msg
0x180035578  mov     rcx, r14; hWnd
0x18003557b  call    cs:__imp_SendMessageW
0x180035581  xor     r9d, r9d; lParam
0x180035584  mov     edx, 409h; Msg
0x180035589  mov     rcx, r14; hWnd
0x18003558c  lea     r8d, [r9+1]; wParam
0x180035590  call    cs:__imp_SendMessageW
0x180035596  cmp     [rsp+2C0h+var_2A0], 0
0x18003559b  jz      short loc_1800355A6
0x18003559d  mov     rcx, r14; hWnd
0x1800355a0  call    cs:__imp_UpdateWindow
0x1800355a6  mov     rcx, [rbp+1C0h+var_40]
0x1800355ad  xor     rcx, rsp; StackCookie
0x1800355b0  call    __security_check_cookie
0x1800355b5  mov     rbx, [rsp+2C0h+arg_0]
0x1800355bd  add     rsp, 290h
0x1800355c4  pop     r15
0x1800355c6  pop     r14
0x1800355c8  pop     r13
0x1800355ca  pop     r12
0x1800355cc  pop     rdi
0x1800355cd  pop     rsi
0x1800355ce  pop     rbp
0x1800355cf  retn
```
