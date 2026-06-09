# SelectCustomFormat

- ea: `0x1800074d0`
- end: `0x180007689`
- name: `SelectCustomFormat`
- size: `441`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000dff8`
- `0x18000ea7c`
- `0x18000f330`
- `0x18000fba0`
- `0x180011018`
- `0x1800115f0`

## callees

- `0x1800074d0`
- `0x1800084c0`
- `0x18000a250`
- `0x18000df38`

## import_xrefs

- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgCtrlID` at `0x1800075ad`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgCtrlID` at `0x1800075ad`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180007504`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000751c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800075c2`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800075e0`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180007606`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180007626`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180007504`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000751c`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800075c2`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800075e0`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180007606`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180007626`
- `ext-ms-win-ntuser-window-l1-1-4!GetFocus` at `0x18000760c`
- `ext-ms-win-ntuser-window-l1-1-4!GetFocus` at `0x18000760c`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180007636`
- `ext-ms-win-ntuser-window-l1-1-4!EnableWindow` at `0x180007636`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x18000756b`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x180007591`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x18000756b`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x180007591`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x180007581`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x1800075ee`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x180007581`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongW` at `0x1800075ee`

## pseudocode

```c
char __fastcall SelectCustomFormat(__int64 a1)
{
  LRESULT v2; // rax
  int v3; // edi
  HWND *v4; // r14
  LRESULT v5; // rsi
  BOOL v6; // ebp
  HWND *v7; // r15
  unsigned __int16 WindowLongW; // bp
  BOOL v9; // eax
  __int64 v10; // rcx
  HWND v11; // rdi
  int DlgCtrlID; // eax
  unsigned __int16 v13; // ax

  LOBYTE(v2) = IsSendMessageWPresent();
  if ( !(_BYTE)v2 )
    return v2;
  v3 = SendMessageW(*(HWND *)(a1 + 56), 0x147u, 0, 0);
  v2 = SendMessageW(*(HWND *)(a1 + 56), 0x150u, v3, 0);
  v4 = (HWND *)(a1 + 96);
  v5 = v2;
  if ( *(_QWORD *)(a1 + 96) )
  {
    if ( v3 )
    {
      if ( !(unsigned int)IsSystemName(a1, *(_QWORD *)(v2 + 16), 0) )
      {
        v6 = 1;
LABEL_16:
        LOBYTE(v2) = EnableWindow(*v4, v6);
        goto LABEL_17;
      }
      v7 = (HWND *)(a1 + 96);
    }
    else
    {
      v7 = (HWND *)(a1 + 96);
    }
    if ( IsWindowEnabled(*v4) )
    {
      WindowLongW = GetWindowLongW(*v4, -16);
      if ( (WindowLongW & 1) != 0 )
      {
        v9 = IsWindowEnabled(*(HWND *)(a1 + 64));
        v10 = 64;
        if ( !v9 )
          v10 = 72;
        v11 = *(HWND *)(v10 + a1);
        DlgCtrlID = GetDlgCtrlID(v11);
        SendMessageW(*(HWND *)(a1 + 16), 0x401u, DlgCtrlID, 0);
        SendMessageW(*v4, 0xF4u, WindowLongW ^ 1LL, 1);
        v13 = GetWindowLongW(v11, -16);
        SendMessageW(v11, 0xF4u, v13 | 1LL, 1);
      }
      if ( GetFocus() == *v4 )
        SendMessageW(*(HWND *)(a1 + 16), 0x28u, 0, 0);
    }
    v6 = 0;
    v4 = v7;
    goto LABEL_16;
  }
LABEL_17:
  if ( v5 != *(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 8) = v5;
    if ( v5 )
    {
      v2 = (LRESULT)CopyStruct(*(LPCVOID *)(a1 + 192), *(unsigned __int16 **)(v5 + 24), *(_DWORD *)a1);
      if ( v2 )
        *(_QWORD *)(a1 + 192) = v2;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800074d0  push    rbx
0x1800074d2  sub     rsp, 30h
0x1800074d6  mov     rbx, rcx
0x1800074d9  call    IsSendMessageWPresent
0x1800074de  test    al, al
0x1800074e0  jz      loc_180007683
0x1800074e6  mov     rcx, [rbx+38h]; hWnd
0x1800074ea  xor     r9d, r9d; lParam
0x1800074ed  mov     [rsp+38h+arg_8], rsi
0x1800074f2  xor     r8d, r8d; wParam
0x1800074f5  mov     [rsp+38h+arg_10], rdi
0x1800074fa  mov     edx, 147h; Msg
0x1800074ff  mov     [rsp+38h+var_10], r14
0x180007504  call    cs:__imp_SendMessageW
0x18000750a  mov     rcx, [rbx+38h]; hWnd
0x18000750e  xor     r9d, r9d; lParam
0x180007511  movsxd  r8, eax; wParam
0x180007514  mov     edx, 150h; Msg
0x180007519  mov     rdi, rax
0x18000751c  call    cs:__imp_SendMessageW
0x180007522  cmp     qword ptr [rbx+60h], 0
0x180007527  lea     r14, [rbx+60h]
0x18000752b  mov     rsi, rax
0x18000752e  jz      loc_180007646
0x180007534  mov     [rsp+38h+arg_0], rbp
0x180007539  mov     [rsp+38h+var_18], r15
0x18000753e  test    edi, edi
0x180007540  jz      short loc_180007565
0x180007542  mov     rdx, [rax+10h]
0x180007546  xor     r8d, r8d
0x180007549  mov     rcx, rbx
0x18000754c  call    IsSystemName
0x180007551  test    eax, eax
0x180007553  jnz     short loc_18000755F
0x180007555  mov     ebp, 1
0x18000755a  jmp     loc_180007631
0x18000755f  lea     r15, [rbx+60h]
0x180007563  jmp     short loc_180007568
0x180007565  mov     r15, r14
0x180007568  mov     rcx, [r14]; hWnd
0x18000756b  call    cs:__imp_IsWindowEnabled
0x180007571  test    eax, eax
0x180007573  jz      loc_18000762C
0x180007579  mov     rcx, [r14]; hWnd
0x18000757c  mov     edx, 0FFFFFFF0h; nIndex
0x180007581  call    cs:__imp_GetWindowLongW
0x180007587  mov     ebp, eax
0x180007589  test    al, 1
0x18000758b  jz      short loc_18000760C
0x18000758d  mov     rcx, [rbx+40h]; hWnd
0x180007591  call    cs:__imp_IsWindowEnabled
0x180007597  mov     edx, 48h ; 'H'
0x18000759c  mov     ecx, 40h ; '@'
0x1800075a1  test    eax, eax
0x1800075a3  cmovz   ecx, edx
0x1800075a6  mov     rdi, [rcx+rbx]
0x1800075aa  mov     rcx, rdi; hWnd
0x1800075ad  call    cs:__imp_GetDlgCtrlID
0x1800075b3  mov     rcx, [rbx+10h]; hWnd
0x1800075b7  xor     r9d, r9d; lParam
0x1800075ba  movsxd  r8, eax; wParam
0x1800075bd  mov     edx, 401h; Msg
0x1800075c2  call    cs:__imp_SendMessageW
0x1800075c8  mov     rcx, [r14]; hWnd
0x1800075cb  mov     edx, 0F4h; Msg
0x1800075d0  movzx   r8d, bp
0x1800075d4  mov     ebp, 1
0x1800075d9  mov     r9d, ebp; lParam
0x1800075dc  xor     r8, 1; wParam
0x1800075e0  call    cs:__imp_SendMessageW
0x1800075e6  mov     edx, 0FFFFFFF0h; nIndex
0x1800075eb  mov     rcx, rdi; hWnd
0x1800075ee  call    cs:__imp_GetWindowLongW
0x1800075f4  movzx   r8d, ax
0x1800075f8  mov     r9d, ebp; lParam
0x1800075fb  or      r8, rbp; wParam
0x1800075fe  mov     edx, 0F4h; Msg
0x180007603  mov     rcx, rdi; hWnd
0x180007606  call    cs:__imp_SendMessageW
0x18000760c  call    cs:__imp_GetFocus
0x180007612  cmp     rax, [r14]
0x180007615  jnz     short loc_18000762C
0x180007617  mov     rcx, [rbx+10h]; hWnd
0x18000761b  xor     r9d, r9d; lParam
0x18000761e  xor     r8d, r8d; wParam
0x180007621  mov     edx, 28h ; '('; Msg
0x180007626  call    cs:__imp_SendMessageW
0x18000762c  xor     ebp, ebp
0x18000762e  mov     r14, r15
0x180007631  mov     rcx, [r14]; hWnd
0x180007634  mov     edx, ebp; bEnable
0x180007636  call    cs:__imp_EnableWindow
0x18000763c  mov     r15, [rsp+38h+var_18]
0x180007641  mov     rbp, [rsp+38h+arg_0]
0x180007646  mov     r14, [rsp+38h+var_10]
0x18000764b  mov     rdi, [rsp+38h+arg_10]
0x180007650  cmp     rsi, [rbx+8]
0x180007654  jz      short loc_18000767E
0x180007656  mov     [rbx+8], rsi
0x18000765a  test    rsi, rsi
0x18000765d  jz      short loc_18000767E
0x18000765f  mov     r8d, [rbx]
0x180007662  mov     rdx, [rsi+18h]; Src
0x180007666  mov     rcx, [rbx+0C0h]; pMem
0x18000766d  call    CopyStruct
0x180007672  test    rax, rax
0x180007675  jz      short loc_18000767E
0x180007677  mov     [rbx+0C0h], rax
0x18000767e  mov     rsi, [rsp+38h+arg_8]
0x180007683  add     rsp, 30h
0x180007687  pop     rbx
0x180007688  retn
```
