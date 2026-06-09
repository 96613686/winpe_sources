# CTscServerNotAuthenticatedDialog::CalcTextRect(ushort const *,HWND__ *,tagRECT *)

- ea: `0x1804de164`
- end: `0x1804de45a`
- name: `?CalcTextRect@CTscServerNotAuthenticatedDialog@@AEAAJPEBGPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `758`
- prototype: `int(CTscServerNotAuthenticatedDialog *__hidden this, const unsigned __int16 *, HWND, struct tagRECT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1804e029c`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1804de164`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804de1a6`
- `KERNEL32!GetLastError` at `0x1804de28d`
- `KERNEL32!GetLastError` at `0x1804de311`
- `KERNEL32!GetLastError` at `0x1804de399`
- `KERNEL32!GetLastError` at `0x1804de1a6`
- `KERNEL32!GetLastError` at `0x1804de28d`
- `KERNEL32!GetLastError` at `0x1804de311`
- `KERNEL32!GetLastError` at `0x1804de399`
- `GDI32!DeleteObject` at `0x1804de42e`
- `GDI32!DeleteObject` at `0x1804de42e`
- `GDI32!SelectObject` at `0x1804de303`
- `GDI32!SelectObject` at `0x1804de40e`
- `GDI32!SelectObject` at `0x1804de303`
- `GDI32!SelectObject` at `0x1804de40e`
- `GDI32!CreateFontIndirectW` at `0x1804de267`
- `GDI32!CreateFontIndirectW` at `0x1804de267`
- `USER32!GetWindowRect` at `0x1804de19c`
- `USER32!GetWindowRect` at `0x1804de19c`
- `USER32!GetWindowDC` at `0x1804de27f`
- `USER32!GetWindowDC` at `0x1804de27f`
- `USER32!SendMessageW` at `0x1804de221`
- `USER32!SendMessageW` at `0x1804de221`
- `USER32!ReleaseDC` at `0x1804de41b`
- `USER32!ReleaseDC` at `0x1804de41b`
- `USER32!DrawTextW` at `0x1804de38f`
- `USER32!DrawTextW` at `0x1804de38f`
- `USER32!SystemParametersInfoW` at `0x1804de255`
- `USER32!SystemParametersInfoW` at `0x1804de255`

## pseudocode

```c
__int64 __fastcall CTscServerNotAuthenticatedDialog::CalcTextRect(
        HWND *this,
        const unsigned __int16 *a2,
        HWND a3,
        struct tagRECT *a4)
{
  signed int LastError; // ebx
  unsigned int v9; // eax
  BOOL v10; // r14d
  void *v11; // rdi
  HDC WindowDC; // rax
  HDC v13; // rbp
  unsigned int v14; // eax
  HGDIOBJ v15; // rsi
  unsigned int v16; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int pvParam; // [rsp+30h] [rbp-258h] BYREF
  _BYTE v20[404]; // [rsp+34h] [rbp-254h] BYREF
  LOGFONTW lf; // [rsp+1C8h] [rbp-C0h] BYREF

  if ( GetWindowRect(a3, a4) )
  {
    v10 = 0;
    v11 = (void *)SendMessageW(a3, 0x31u, 0, 0);
    if ( !v11 )
    {
      memset_0(v20, 0, 0x1F4u);
      pvParam = 504;
      if ( SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
      {
        v11 = CreateFontIndirectW(&lf);
        v10 = v11 != 0;
      }
    }
    WindowDC = GetWindowDC(this[1]);
    v13 = WindowDC;
    if ( WindowDC )
    {
      v15 = 0;
      if ( !v11 || (v15 = SelectObject(WindowDC, v11)) != 0 )
      {
        if ( DrawTextW(v13, a2, -1, a4, 0x410u) )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              103,
              WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids,
              CurrentThreadActivityIdPrefix,
              LastError);
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( LastError >= 0 )
            LastError = -2147467259;
        }
        if ( v15 )
          SelectObject(v13, v15);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids,
            v16,
            LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
      }
      ReleaseDC(this[1], v13);
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          101,
          WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids,
          v14,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
    if ( v10 && v11 )
      DeleteObject(v11);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        100,
        WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids,
        v9,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1804de164  push    rbx
0x1804de166  push    rbp
0x1804de167  push    rsi
0x1804de168  push    rdi
0x1804de169  push    r12
0x1804de16b  push    r13
0x1804de16d  push    r14
0x1804de16f  push    r15
0x1804de171  sub     rsp, 248h
0x1804de178  mov     rax, cs:__security_cookie
0x1804de17f  xor     rax, rsp
0x1804de182  mov     [rsp+288h+var_58], rax
0x1804de18a  mov     r12, rdx
0x1804de18d  mov     r13, rcx
0x1804de190  mov     rdx, r9; lpRect
0x1804de193  mov     rcx, r8; hWnd
0x1804de196  mov     r15, r9
0x1804de199  mov     rbx, r8
0x1804de19c  call    cs:__imp_GetWindowRect
0x1804de1a2  test    eax, eax
0x1804de1a4  jnz     short loc_1804DE211
0x1804de1a6  call    cs:__imp_GetLastError
0x1804de1ac  mov     ebx, eax
0x1804de1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de1b5  lea     rax, WPP_GLOBAL_Control
0x1804de1bc  cmp     rcx, rax
0x1804de1bf  jz      short loc_1804DE1F5
0x1804de1c1  test    byte ptr [rcx+1Ch], 8
0x1804de1c5  jz      short loc_1804DE1F5
0x1804de1c7  cmp     byte ptr [rcx+19h], 2
0x1804de1cb  jb      short loc_1804DE1F5
0x1804de1cd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804de1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de1d9  lea     r8, WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids
0x1804de1e0  mov     edx, 64h ; 'd'
0x1804de1e5  mov     [rsp+288h+format], ebx
0x1804de1e9  mov     r9d, eax
0x1804de1ec  mov     rcx, [rcx+10h]
0x1804de1f0  call    WPP_SF_Dd
0x1804de1f5  test    ebx, ebx
0x1804de1f7  jle     short loc_1804DE202
0x1804de1f9  movzx   ebx, bx
0x1804de1fc  or      ebx, 80070000h
0x1804de202  test    ebx, ebx
0x1804de204  mov     eax, 80004005h
0x1804de209  cmovns  ebx, eax
0x1804de20c  jmp     loc_1804DE434
0x1804de211  xor     r14d, r14d
0x1804de214  xor     r9d, r9d; lParam
0x1804de217  xor     r8d, r8d; wParam
0x1804de21a  mov     rcx, rbx; hWnd
0x1804de21d  lea     edx, [r14+31h]; Msg
0x1804de221  call    cs:__imp_SendMessageW
0x1804de227  mov     rdi, rax
0x1804de22a  test    rax, rax
0x1804de22d  jnz     short loc_1804DE27B
0x1804de22f  xor     edx, edx; Val
0x1804de231  lea     rcx, [rsp+288h+var_254]; void *
0x1804de236  mov     r8d, 1F4h; Size
0x1804de23c  call    memset_0
0x1804de241  mov     edx, 1F8h; uiParam
0x1804de246  lea     r8, [rsp+288h+pvParam]; pvParam
0x1804de24b  xor     r9d, r9d; fWinIni
0x1804de24e  mov     [rsp+288h+pvParam], edx
0x1804de252  lea     ecx, [rdi+29h]; uiAction
0x1804de255  call    cs:__imp_SystemParametersInfoW
0x1804de25b  test    eax, eax
0x1804de25d  jz      short loc_1804DE27B
0x1804de25f  lea     rcx, [rsp+288h+lf]; lplf
0x1804de267  call    cs:__imp_CreateFontIndirectW
0x1804de26d  mov     rdi, rax
0x1804de270  lea     eax, [r14+1]
0x1804de274  test    rdi, rdi
0x1804de277  cmovnz  r14d, eax
0x1804de27b  mov     rcx, [r13+8]; hWnd
0x1804de27f  call    cs:__imp_GetWindowDC
0x1804de285  mov     rbp, rax
0x1804de288  test    rax, rax
0x1804de28b  jnz     short loc_1804DE2F6
0x1804de28d  call    cs:__imp_GetLastError
0x1804de293  mov     ebx, eax
0x1804de295  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de29c  lea     rax, WPP_GLOBAL_Control
0x1804de2a3  cmp     rcx, rax
0x1804de2a6  jz      short loc_1804DE2DA
0x1804de2a8  test    byte ptr [rcx+1Ch], 8
0x1804de2ac  jz      short loc_1804DE2DA
0x1804de2ae  cmp     byte ptr [rcx+19h], 2
0x1804de2b2  jb      short loc_1804DE2DA
0x1804de2b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804de2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de2c0  lea     edx, [rbp+65h]
0x1804de2c3  mov     r9d, eax
0x1804de2c6  mov     [rsp+288h+format], ebx
0x1804de2ca  lea     r8, WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids
0x1804de2d1  mov     rcx, [rcx+10h]
0x1804de2d5  call    WPP_SF_Dd
0x1804de2da  test    ebx, ebx
0x1804de2dc  jle     short loc_1804DE2E7
0x1804de2de  movzx   ebx, bx
0x1804de2e1  or      ebx, 80070000h
0x1804de2e7  test    ebx, ebx
0x1804de2e9  mov     eax, 80004005h
0x1804de2ee  cmovns  ebx, eax
0x1804de2f1  jmp     loc_1804DE421
0x1804de2f6  xor     esi, esi
0x1804de2f8  test    rdi, rdi
0x1804de2fb  jz      short loc_1804DE37A
0x1804de2fd  mov     rdx, rdi; h
0x1804de300  mov     rcx, rbp; hdc
0x1804de303  call    cs:__imp_SelectObject
0x1804de309  mov     rsi, rax
0x1804de30c  test    rax, rax
0x1804de30f  jnz     short loc_1804DE37A
0x1804de311  call    cs:__imp_GetLastError
0x1804de317  mov     ebx, eax
0x1804de319  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de320  lea     rax, WPP_GLOBAL_Control
0x1804de327  cmp     rcx, rax
0x1804de32a  jz      short loc_1804DE35E
0x1804de32c  test    byte ptr [rcx+1Ch], 8
0x1804de330  jz      short loc_1804DE35E
0x1804de332  cmp     byte ptr [rcx+19h], 2
0x1804de336  jb      short loc_1804DE35E
0x1804de338  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804de33d  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de344  lea     edx, [rsi+66h]
0x1804de347  mov     r9d, eax
0x1804de34a  mov     [rsp+288h+format], ebx
0x1804de34e  lea     r8, WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids
0x1804de355  mov     rcx, [rcx+10h]
0x1804de359  call    WPP_SF_Dd
0x1804de35e  test    ebx, ebx
0x1804de360  jle     short loc_1804DE36B
0x1804de362  movzx   ebx, bx
0x1804de365  or      ebx, 80070000h
0x1804de36b  test    ebx, ebx
0x1804de36d  mov     eax, 80004005h
0x1804de372  cmovns  ebx, eax
0x1804de375  jmp     loc_1804DE414
0x1804de37a  mov     r9, r15; lprc
0x1804de37d  mov     [rsp+288h+format], 410h; format
0x1804de385  or      r8d, 0FFFFFFFFh; cchText
0x1804de389  mov     rdx, r12; lpchText
0x1804de38c  mov     rcx, rbp; hdc
0x1804de38f  call    cs:__imp_DrawTextW
0x1804de395  test    eax, eax
0x1804de397  jnz     short loc_1804DE401
0x1804de399  call    cs:__imp_GetLastError
0x1804de39f  mov     ebx, eax
0x1804de3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de3a8  lea     rax, WPP_GLOBAL_Control
0x1804de3af  cmp     rcx, rax
0x1804de3b2  jz      short loc_1804DE3E8
0x1804de3b4  test    byte ptr [rcx+1Ch], 8
0x1804de3b8  jz      short loc_1804DE3E8
0x1804de3ba  cmp     byte ptr [rcx+19h], 2
0x1804de3be  jb      short loc_1804DE3E8
0x1804de3c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804de3c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1804de3cc  lea     r8, WPP_f9e5d225df8f3623bff81c2bb5091cbc_Traceguids
0x1804de3d3  mov     edx, 67h ; 'g'
0x1804de3d8  mov     [rsp+288h+format], ebx
0x1804de3dc  mov     r9d, eax
0x1804de3df  mov     rcx, [rcx+10h]
0x1804de3e3  call    WPP_SF_Dd
0x1804de3e8  test    ebx, ebx
0x1804de3ea  jle     short loc_1804DE3F5
0x1804de3ec  movzx   ebx, bx
0x1804de3ef  or      ebx, 80070000h
0x1804de3f5  test    ebx, ebx
0x1804de3f7  mov     eax, 80004005h
0x1804de3fc  cmovns  ebx, eax
0x1804de3ff  jmp     short loc_1804DE403
0x1804de401  xor     ebx, ebx
0x1804de403  test    rsi, rsi
0x1804de406  jz      short loc_1804DE414
0x1804de408  mov     rdx, rsi; h
0x1804de40b  mov     rcx, rbp; hdc
0x1804de40e  call    cs:__imp_SelectObject
0x1804de414  mov     rcx, [r13+8]; hWnd
0x1804de418  mov     rdx, rbp; hDC
0x1804de41b  call    cs:__imp_ReleaseDC
0x1804de421  test    r14d, r14d
0x1804de424  jz      short loc_1804DE434
0x1804de426  test    rdi, rdi
0x1804de429  jz      short loc_1804DE434
0x1804de42b  mov     rcx, rdi; ho
0x1804de42e  call    cs:__imp_DeleteObject
0x1804de434  mov     eax, ebx
0x1804de436  mov     rcx, [rsp+288h+var_58]
0x1804de43e  xor     rcx, rsp; StackCookie
0x1804de441  call    __security_check_cookie
0x1804de446  add     rsp, 248h
0x1804de44d  pop     r15
0x1804de44f  pop     r14
0x1804de451  pop     r13
0x1804de453  pop     r12
0x1804de455  pop     rdi
0x1804de456  pop     rsi
0x1804de457  pop     rbp
0x1804de458  pop     rbx
0x1804de459  retn
```
