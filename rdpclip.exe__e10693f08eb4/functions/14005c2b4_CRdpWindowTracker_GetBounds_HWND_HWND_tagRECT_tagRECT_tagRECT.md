# CRdpWindowTracker::GetBounds(HWND__ *,HWND__ *,tagRECT *,tagRECT *,tagRECT *)

- ea: `0x14005c2b4`
- end: `0x14005c5d5`
- name: `?GetBounds@CRdpWindowTracker@@AEAAJPEAUHWND__@@0PEAUtagRECT@@11@Z`
- size: `801`
- prototype: `int(CRdpWindowTracker *__hidden this, HWND, HWND, struct tagRECT *, struct tagRECT *, struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14005ca44`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x14005b5dc`
- `0x14005c2b4`
- `0x14006a120`

## import_xrefs

- `USER32!CopyRect` at `0x14005c58f`
- `USER32!CopyRect` at `0x14005c59c`
- `USER32!CopyRect` at `0x14005c5a9`
- `USER32!CopyRect` at `0x14005c58f`
- `USER32!CopyRect` at `0x14005c59c`
- `USER32!CopyRect` at `0x14005c5a9`
- `USER32!OffsetRect` at `0x14005c533`
- `USER32!OffsetRect` at `0x14005c533`
- `USER32!GetWindowRect` at `0x14005c382`
- `USER32!GetWindowRect` at `0x14005c413`
- `USER32!GetWindowRect` at `0x14005c382`
- `USER32!GetWindowRect` at `0x14005c413`
- `USER32!SetRectEmpty` at `0x14005c361`
- `USER32!SetRectEmpty` at `0x14005c36b`
- `USER32!SetRectEmpty` at `0x14005c375`
- `USER32!SetRectEmpty` at `0x14005c361`
- `USER32!SetRectEmpty` at `0x14005c36b`
- `USER32!SetRectEmpty` at `0x14005c375`
- `USER32!GetClientRect` at `0x14005c474`
- `USER32!GetClientRect` at `0x14005c474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c47e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c47e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c53d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14005c352`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14005c352`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::GetBounds(
        CRdpWindowTracker *this,
        HWND a2,
        HWND a3,
        struct tagRECT *a4,
        struct tagRECT *lprcDst,
        struct tagRECT *a6)
{
  signed int v9; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int LastError; // eax
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  int dy[2]; // [rsp+30h] [rbp-40h] BYREF
  RECT rcSrc; // [rsp+38h] [rbp-38h] BYREF
  struct tagRECT rc; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-18h] BYREF

  *(_QWORD *)dy = 0;
  rc = 0;
  rcSrc = 0;
  Rect = 0;
  if ( !a2 )
  {
    v9 = -2147467261;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    DebugBreak();
    return (unsigned int)v9;
  }
  SetRectEmpty(&rc);
  SetRectEmpty(&rcSrc);
  SetRectEmpty(&Rect);
  if ( !GetWindowRect(a2, &rc) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v9;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 53;
LABEL_15:
      v14 = "GetWindowRect() failed";
      goto LABEL_16;
    }
  }
  if ( !GetWindowRect(a3, &Rect) )
  {
    v15 = GetLastError();
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v9;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 54;
      goto LABEL_15;
    }
  }
  if ( !GetClientRect(a2, &rcSrc) )
  {
    v16 = GetLastError();
    v9 = v16;
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v9;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 55;
      v14 = "GetClientRect() failed";
      goto LABEL_16;
    }
  }
  v9 = CRdpWindowTracker::ClientTopLeftToScreen(a2, (struct tagPOINT *)dy);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v9;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 56;
    v14 = "CRdpWindowTracker::ClientTopLeftToScreen() failed";
LABEL_16:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v12,
      (__int64)v14,
      v9);
    return (unsigned int)v9;
  }
  if ( OffsetRect(&rcSrc, dy[0], dy[1]) )
    goto LABEL_46;
  v17 = GetLastError();
  v9 = v17;
  if ( v17 > 0 )
    v9 = (unsigned __int16)v17 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_46:
    CopyRect(a4, &rc);
    CopyRect(lprcDst, &rcSrc);
    CopyRect(a6, &Rect);
    return (unsigned int)v9;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 57;
    v14 = "OffsetRect() failed";
    goto LABEL_16;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14005c2b4  mov     [rsp-38h+arg_0], rbx
0x14005c2b9  push    rbp
0x14005c2ba  push    rsi
0x14005c2bb  push    rdi
0x14005c2bc  push    r12
0x14005c2be  push    r13
0x14005c2c0  push    r14
0x14005c2c2  push    r15
0x14005c2c4  mov     rbp, rsp
0x14005c2c7  sub     rsp, 70h
0x14005c2cb  mov     rax, cs:__security_cookie
0x14005c2d2  xor     rax, rsp
0x14005c2d5  mov     [rbp+var_8], rax
0x14005c2d9  mov     r15, [rbp+lprcDst]
0x14005c2dd  xorps   xmm0, xmm0
0x14005c2e0  mov     r12, [rbp+arg_28]
0x14005c2e4  xorps   xmm1, xmm1
0x14005c2e7  mov     qword ptr [rbp+dy], 0
0x14005c2ef  mov     r14, r9
0x14005c2f2  mov     rsi, r8
0x14005c2f5  mov     rdi, rdx
0x14005c2f8  movups  xmmword ptr [rbp+rc.left], xmm0
0x14005c2fc  movups  xmmword ptr [rbp+rcSrc.left], xmm1
0x14005c300  movups  xmmword ptr [rbp+Rect.left], xmm0
0x14005c304  test    rdx, rdx
0x14005c307  jnz     short loc_14005C35D
0x14005c309  mov     ebx, 80004003h
0x14005c30e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c315  lea     rax, WPP_GLOBAL_Control
0x14005c31c  cmp     rcx, rax
0x14005c31f  jz      short loc_14005C352
0x14005c321  test    dword ptr [rcx+1Ch], 200h
0x14005c328  jz      short loc_14005C352
0x14005c32a  cmp     byte ptr [rcx+19h], 2
0x14005c32e  jb      short loc_14005C352
0x14005c330  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c335  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c33c  lea     edx, [rdi+31h]
0x14005c33f  mov     r9d, eax
0x14005c342  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c349  mov     rcx, [rcx+10h]
0x14005c34d  call    WPP_SF_d
0x14005c352  call    cs:__imp_DebugBreak
0x14005c358  jmp     loc_14005C5AF
0x14005c35d  lea     rcx, [rbp+rc]; lprc
0x14005c361  call    cs:__imp_SetRectEmpty
0x14005c367  lea     rcx, [rbp+rcSrc]; lprc
0x14005c36b  call    cs:__imp_SetRectEmpty
0x14005c371  lea     rcx, [rbp+Rect]; lprc
0x14005c375  call    cs:__imp_SetRectEmpty
0x14005c37b  lea     rdx, [rbp+rc]; lpRect
0x14005c37f  mov     rcx, rdi; hWnd
0x14005c382  call    cs:__imp_GetWindowRect
0x14005c388  mov     r13d, 80070000h
0x14005c38e  test    eax, eax
0x14005c390  jnz     short loc_14005C40C
0x14005c392  call    cs:__imp_GetLastError
0x14005c398  mov     ebx, eax
0x14005c39a  test    eax, eax
0x14005c39c  jle     short loc_14005C3A4
0x14005c39e  movzx   ebx, ax
0x14005c3a1  or      ebx, r13d
0x14005c3a4  test    ebx, ebx
0x14005c3a6  jns     short loc_14005C40C
0x14005c3a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c3af  lea     rax, WPP_GLOBAL_Control
0x14005c3b6  cmp     rcx, rax
0x14005c3b9  jz      loc_14005C5AF
0x14005c3bf  test    byte ptr [rcx+1Ch], 8
0x14005c3c3  jz      loc_14005C5AF
0x14005c3c9  cmp     byte ptr [rcx+19h], 2
0x14005c3cd  jb      loc_14005C5AF
0x14005c3d3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c3d8  mov     edx, 35h ; '5'
0x14005c3dd  lea     rcx, aGetwindowrectF; "GetWindowRect() failed"
0x14005c3e4  mov     [rsp+70h+var_48], ebx
0x14005c3e8  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005c3ef  mov     [rsp+70h+var_50], rcx
0x14005c3f4  mov     r9d, eax
0x14005c3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c3fe  mov     rcx, [rcx+10h]
0x14005c402  call    WPP_SF_DsD
0x14005c407  jmp     loc_14005C5AF
0x14005c40c  lea     rdx, [rbp+Rect]; lpRect
0x14005c410  mov     rcx, rsi; hWnd
0x14005c413  call    cs:__imp_GetWindowRect
0x14005c419  test    eax, eax
0x14005c41b  jnz     short loc_14005C46D
0x14005c41d  call    cs:__imp_GetLastError
0x14005c423  mov     ebx, eax
0x14005c425  test    eax, eax
0x14005c427  jle     short loc_14005C42F
0x14005c429  movzx   ebx, ax
0x14005c42c  or      ebx, r13d
0x14005c42f  test    ebx, ebx
0x14005c431  jns     short loc_14005C46D
0x14005c433  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c43a  lea     rax, WPP_GLOBAL_Control
0x14005c441  cmp     rcx, rax
0x14005c444  jz      loc_14005C5AF
0x14005c44a  test    byte ptr [rcx+1Ch], 8
0x14005c44e  jz      loc_14005C5AF
0x14005c454  cmp     byte ptr [rcx+19h], 2
0x14005c458  jb      loc_14005C5AF
0x14005c45e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c463  mov     edx, 36h ; '6'
0x14005c468  jmp     loc_14005C3DD
0x14005c46d  lea     rdx, [rbp+rcSrc]; lpRect
0x14005c471  mov     rcx, rdi; hWnd
0x14005c474  call    cs:__imp_GetClientRect
0x14005c47a  test    eax, eax
0x14005c47c  jnz     short loc_14005C4D5
0x14005c47e  call    cs:__imp_GetLastError
0x14005c484  mov     ebx, eax
0x14005c486  test    eax, eax
0x14005c488  jle     short loc_14005C490
0x14005c48a  movzx   ebx, ax
0x14005c48d  or      ebx, r13d
0x14005c490  test    ebx, ebx
0x14005c492  jns     short loc_14005C4D5
0x14005c494  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c49b  lea     rax, WPP_GLOBAL_Control
0x14005c4a2  cmp     rcx, rax
0x14005c4a5  jz      loc_14005C5AF
0x14005c4ab  test    byte ptr [rcx+1Ch], 8
0x14005c4af  jz      loc_14005C5AF
0x14005c4b5  cmp     byte ptr [rcx+19h], 2
0x14005c4b9  jb      loc_14005C5AF
0x14005c4bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c4c4  mov     edx, 37h ; '7'
0x14005c4c9  lea     rcx, aGetclientrectF; "GetClientRect() failed"
0x14005c4d0  jmp     loc_14005C3E4
0x14005c4d5  lea     rdx, [rbp+dy]; struct tagPOINT *
0x14005c4d9  mov     rcx, rdi; hWnd
0x14005c4dc  call    ?ClientTopLeftToScreen@CRdpWindowTracker@@CAJPEAUHWND__@@PEAUtagPOINT@@@Z; CRdpWindowTracker::ClientTopLeftToScreen(HWND__ *,tagPOINT *)
0x14005c4e1  mov     ebx, eax
0x14005c4e3  test    eax, eax
0x14005c4e5  jns     short loc_14005C528
0x14005c4e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c4ee  lea     rax, WPP_GLOBAL_Control
0x14005c4f5  cmp     rcx, rax
0x14005c4f8  jz      loc_14005C5AF
0x14005c4fe  test    byte ptr [rcx+1Ch], 8
0x14005c502  jz      loc_14005C5AF
0x14005c508  cmp     byte ptr [rcx+19h], 2
0x14005c50c  jb      loc_14005C5AF
0x14005c512  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c517  mov     edx, 38h ; '8'
0x14005c51c  lea     rcx, aCrdpwindowtrac; "CRdpWindowTracker::ClientTopLeftToScree"...
0x14005c523  jmp     loc_14005C3E4
0x14005c528  mov     r8d, [rbp+dy+4]; dy
0x14005c52c  lea     rcx, [rbp+rcSrc]; lprc
0x14005c530  mov     edx, [rbp+dy]; dx
0x14005c533  call    cs:__imp_OffsetRect
0x14005c539  test    eax, eax
0x14005c53b  jnz     short loc_14005C588
0x14005c53d  call    cs:__imp_GetLastError
0x14005c543  mov     ebx, eax
0x14005c545  test    eax, eax
0x14005c547  jle     short loc_14005C54F
0x14005c549  movzx   ebx, ax
0x14005c54c  or      ebx, r13d
0x14005c54f  test    ebx, ebx
0x14005c551  jns     short loc_14005C588
0x14005c553  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c55a  lea     rax, WPP_GLOBAL_Control
0x14005c561  cmp     rcx, rax
0x14005c564  jz      short loc_14005C5AF
0x14005c566  test    byte ptr [rcx+1Ch], 8
0x14005c56a  jz      short loc_14005C5AF
0x14005c56c  cmp     byte ptr [rcx+19h], 2
0x14005c570  jb      short loc_14005C5AF
0x14005c572  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005c577  mov     edx, 39h ; '9'
0x14005c57c  lea     rcx, aOffsetrectFail; "OffsetRect() failed"
0x14005c583  jmp     loc_14005C3E4
0x14005c588  lea     rdx, [rbp+rc]; lprcSrc
0x14005c58c  mov     rcx, r14; lprcDst
0x14005c58f  call    cs:__imp_CopyRect
0x14005c595  lea     rdx, [rbp+rcSrc]; lprcSrc
0x14005c599  mov     rcx, r15; lprcDst
0x14005c59c  call    cs:__imp_CopyRect
0x14005c5a2  lea     rdx, [rbp+Rect]; lprcSrc
0x14005c5a6  mov     rcx, r12; lprcDst
0x14005c5a9  call    cs:__imp_CopyRect
0x14005c5af  mov     eax, ebx
0x14005c5b1  mov     rcx, [rbp+var_8]
0x14005c5b5  xor     rcx, rsp; StackCookie
0x14005c5b8  call    __security_check_cookie
0x14005c5bd  mov     rbx, [rsp+70h+arg_0]
0x14005c5c5  add     rsp, 70h
0x14005c5c9  pop     r15
0x14005c5cb  pop     r14
0x14005c5cd  pop     r13
0x14005c5cf  pop     r12
0x14005c5d1  pop     rdi
0x14005c5d2  pop     rsi
0x14005c5d3  pop     rbp
0x14005c5d4  retn
```
