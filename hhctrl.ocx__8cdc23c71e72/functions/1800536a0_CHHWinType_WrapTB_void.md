# CHHWinType::WrapTB(void)

- ea: `0x1800536a0`
- end: `0x18005383f`
- name: `?WrapTB@CHHWinType@@QEAAXXZ`
- size: `415`
- prototype: `void __fastcall(CHHWinType *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18006eaf4`
- `0x180070230`

## callees

- `0x1800536a0`
- `0x180075c90`

## import_xrefs

- `USER32!MoveWindow` at `0x18005381f`
- `USER32!MoveWindow` at `0x18005381f`
- `USER32!GetClientRect` at `0x1800537bd`
- `USER32!GetClientRect` at `0x1800537bd`
- `USER32!GetWindowRect` at `0x1800536fe`
- `USER32!GetWindowRect` at `0x1800536fe`
- `USER32!SendMessageA` at `0x1800536d6`
- `USER32!SendMessageA` at `0x18005371f`
- `USER32!SendMessageA` at `0x1800537b0`
- `USER32!SendMessageA` at `0x1800536d6`
- `USER32!SendMessageA` at `0x18005371f`
- `USER32!SendMessageA` at `0x1800537b0`

## pseudocode

```c
void __fastcall CHHWinType::WrapTB(CHHWinType *this)
{
  HWND v2; // rcx
  int v3; // eax
  int v4; // ebp
  int v5; // edi
  int v6; // esi
  int v7; // ecx
  int v8; // esi
  int *v9; // rdi
  int v10; // eax
  WPARAM v11; // r8
  int v12; // ecx
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  int nHeight; // r10d
  LPARAM lParam[2]; // [rsp+30h] [rbp-58h] BYREF

  v2 = (HWND)*((_QWORD *)this + 11);
  *(_OWORD *)lParam = 0;
  v3 = SendMessageA(v2, 0x418u, 0, 0);
  if ( v3 )
  {
    v4 = v3 - 1;
    v5 = 0;
    if ( (*((_BYTE *)this + 168) & 2) == 0 )
      v4 = v3;
    GetWindowRect(*((HWND *)this + 8), (LPRECT)((char *)this + 40));
    v6 = 0;
    while ( v6 < v4 )
    {
      if ( SendMessageA(*((HWND *)this + 11), 0x41Du, v6, (LPARAM)lParam) )
        v5 = LODWORD(lParam[1]) - LODWORD(lParam[0]);
      ++v6;
      if ( v5 )
        goto LABEL_11;
    }
    v5 = 20;
LABEL_11:
    v7 = (*((_DWORD *)this + 12) - g_tbRightMargin - g_tbLeftMargin - *((_DWORD *)this + 10)) / v5;
    if ( !v7 )
      v7 = 1;
    v8 = v4 / v7 + 1;
    if ( !(v4 % v7) )
      v8 = v4 / v7;
    if ( HIDWORD(lParam[1]) != HIDWORD(lParam[0]) )
    {
      v9 = (int *)((char *)this + 528);
      v10 = (*((_DWORD *)this + 135) - *((_DWORD *)this + 133)) / (HIDWORD(lParam[1]) - HIDWORD(lParam[0]));
      if ( v8 >= v10 )
      {
        if ( v8 <= v10 )
        {
LABEL_21:
          GetClientRect(*((HWND *)this + 11), (LPRECT)this + 33);
          v12 = g_tbLeftMargin;
          v13 = *((_DWORD *)this + 133);
          v14 = *v9;
          v15 = v13 + v8 * (HIDWORD(lParam[1]) - HIDWORD(lParam[0]));
          v16 = g_tbLeftMargin + v13;
          *((_DWORD *)this + 135) = v15;
          nHeight = *((_DWORD *)this + 135) - *((_DWORD *)this + 133);
          *((_DWORD *)this + 134) = *((_DWORD *)this + 12) - *((_DWORD *)this + 10);
          MoveWindow(*((HWND *)this + 11), v16, v14, *((_DWORD *)this + 134) - g_tbRightMargin - *v9 - v12, nHeight, 1);
          return;
        }
        v11 = (unsigned __int16)v8 | 0x10000LL;
      }
      else
      {
        v11 = (unsigned __int16)v8;
      }
      SendMessageA(*((HWND *)this + 11), 0x427u, v11, (LPARAM)this + 528);
      goto LABEL_21;
    }
  }
}

```

## disassembly

```asm
0x1800536a0  push    rbx
0x1800536a2  push    rbp
0x1800536a3  push    rsi
0x1800536a4  push    rdi
0x1800536a5  push    r14
0x1800536a7  push    r15
0x1800536a9  sub     rsp, 58h
0x1800536ad  mov     rax, cs:__security_cookie
0x1800536b4  xor     rax, rsp
0x1800536b7  mov     [rsp+88h+var_48], rax
0x1800536bc  mov     rbx, rcx
0x1800536bf  xorps   xmm0, xmm0
0x1800536c2  mov     rcx, [rcx+58h]; hWnd
0x1800536c6  xor     r9d, r9d; lParam
0x1800536c9  xor     r8d, r8d; wParam
0x1800536cc  mov     edx, 418h; Msg
0x1800536d1  movups  xmmword ptr [rsp+88h+lParam], xmm0
0x1800536d6  call    cs:__imp_SendMessageA
0x1800536dc  test    eax, eax
0x1800536de  jz      loc_180053825
0x1800536e4  mov     rcx, [rbx+40h]; hWnd
0x1800536e8  lea     ebp, [rax-1]
0x1800536eb  xor     edi, edi
0x1800536ed  lea     r14, [rbx+28h]
0x1800536f1  test    byte ptr [rbx+0A8h], 2
0x1800536f8  mov     rdx, r14; lpRect
0x1800536fb  cmovz   ebp, eax
0x1800536fe  call    cs:__imp_GetWindowRect
0x180053704  xor     esi, esi
0x180053706  lea     r15d, [rdi+1]
0x18005370a  cmp     esi, ebp
0x18005370c  jge     short loc_18005373B
0x18005370e  mov     rcx, [rbx+58h]; hWnd
0x180053712  lea     r9, [rsp+88h+lParam]; lParam
0x180053717  movsxd  r8, esi; wParam
0x18005371a  mov     edx, 41Dh; Msg
0x18005371f  call    cs:__imp_SendMessageA
0x180053725  test    rax, rax
0x180053728  jz      short loc_180053732
0x18005372a  mov     edi, dword ptr [rsp+88h+lParam+8]
0x18005372e  sub     edi, dword ptr [rsp+88h+lParam]
0x180053732  add     esi, r15d
0x180053735  test    edi, edi
0x180053737  jz      short loc_18005370A
0x180053739  jmp     short loc_180053740
0x18005373b  mov     edi, 14h
0x180053740  movsx   ecx, cs:?g_tbRightMargin@@3FA; short g_tbRightMargin
0x180053747  mov     eax, [r14+8]
0x18005374b  sub     eax, ecx
0x18005374d  movsx   ecx, cs:?g_tbLeftMargin@@3FA; short g_tbLeftMargin
0x180053754  sub     eax, ecx
0x180053756  sub     eax, [r14]
0x180053759  cdq
0x18005375a  idiv    edi
0x18005375c  test    eax, eax
0x18005375e  mov     ecx, eax
0x180053760  mov     eax, ebp
0x180053762  cmovz   ecx, r15d
0x180053766  cdq
0x180053767  idiv    ecx
0x180053769  mov     ecx, dword ptr [rsp+88h+lParam+0Ch]
0x18005376d  test    edx, edx
0x18005376f  lea     esi, [rax+1]
0x180053772  cmovz   esi, eax
0x180053775  sub     ecx, dword ptr [rsp+88h+lParam+4]
0x180053779  jz      loc_180053825
0x18005377f  lea     rdi, [rbx+210h]
0x180053786  mov     eax, [rdi+0Ch]
0x180053789  sub     eax, [rdi+4]
0x18005378c  cdq
0x18005378d  idiv    ecx
0x18005378f  cmp     esi, eax
0x180053791  jge     short loc_180053799
0x180053793  movzx   r8d, si
0x180053797  jmp     short loc_1800537A4
0x180053799  jle     short loc_1800537B6
0x18005379b  movzx   r8d, si
0x18005379f  bts     r8, 10h; wParam
0x1800537a4  mov     rcx, [rbx+58h]; hWnd
0x1800537a8  mov     r9, rdi; lParam
0x1800537ab  mov     edx, 427h; Msg
0x1800537b0  call    cs:__imp_SendMessageA
0x1800537b6  mov     rcx, [rbx+58h]; hWnd
0x1800537ba  mov     rdx, rdi; lpRect
0x1800537bd  call    cs:__imp_GetClientRect
0x1800537c3  movsx   ecx, cs:?g_tbLeftMargin@@3FA; short g_tbLeftMargin
0x1800537ca  mov     edx, [rbx+214h]
0x1800537d0  mov     eax, dword ptr [rsp+88h+lParam+0Ch]
0x1800537d4  sub     eax, dword ptr [rsp+88h+lParam+4]
0x1800537d8  mov     r8d, [rdi]; Y
0x1800537db  imul    eax, esi
0x1800537de  mov     [rsp+88h+bRepaint], r15d; bRepaint
0x1800537e3  add     eax, edx
0x1800537e5  add     edx, ecx; X
0x1800537e7  mov     [rbx+21Ch], eax
0x1800537ed  mov     eax, [r14+8]
0x1800537f1  sub     eax, [r14]
0x1800537f4  mov     r10d, [rdi+0Ch]
0x1800537f8  sub     r10d, [rdi+4]
0x1800537fc  mov     [rbx+218h], eax
0x180053802  movsx   eax, cs:?g_tbRightMargin@@3FA; short g_tbRightMargin
0x180053809  mov     r9d, [rdi+8]
0x18005380d  sub     r9d, eax
0x180053810  mov     [rsp+88h+nHeight], r10d; nHeight
0x180053815  sub     r9d, [rdi]
0x180053818  sub     r9d, ecx; nWidth
0x18005381b  mov     rcx, [rbx+58h]; hWnd
0x18005381f  call    cs:__imp_MoveWindow
0x180053825  mov     rcx, [rsp+88h+var_48]
0x18005382a  xor     rcx, rsp; StackCookie
0x18005382d  call    __security_check_cookie
0x180053832  add     rsp, 58h
0x180053836  pop     r15
0x180053838  pop     r14
0x18005383a  pop     rdi
0x18005383b  pop     rsi
0x18005383c  pop     rbp
0x18005383d  pop     rbx
0x18005383e  retn
```
