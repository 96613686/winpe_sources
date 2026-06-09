# CDlgBase::CenterWindow(HWND__ *,int,int)

- ea: `0x1400a58f8`
- end: `0x1400a5b9c`
- name: `?CenterWindow@CDlgBase@@IEAAXPEAUHWND__@@HH@Z`
- size: `676`
- prototype: `void(CDlgBase *__hidden this, HWND, int, int)`
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x14002a870`
- `0x14002af70`
- `0x140049fa0`
- `0x14004fff4`
- `0x14005241c`
- `0x140055754`
- `0x140058ecc`
- `0x140059a70`
- `0x140059b1c`
- `0x1400b4870`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14001e158`
- `0x1400a2170`
- `0x1400a58f8`
- `0x1400a626c`
- `0x140113390`

## import_xrefs

- `USER32!PtInRect` at `0x1400a59a9`
- `USER32!PtInRect` at `0x1400a59bb`
- `USER32!PtInRect` at `0x1400a59a9`
- `USER32!PtInRect` at `0x1400a59bb`
- `USER32!IsWindow` at `0x1400a5955`
- `USER32!IsWindow` at `0x1400a5955`
- `USER32!CopyRect` at `0x1400a5a8a`
- `USER32!CopyRect` at `0x1400a5a8a`
- `USER32!SetWindowPos` at `0x1400a5b7c`
- `USER32!SetWindowPos` at `0x1400a5b7c`
- `USER32!GetWindowRect` at `0x1400a5943`
- `USER32!GetWindowRect` at `0x1400a5998`
- `USER32!GetWindowRect` at `0x1400a5943`
- `USER32!GetWindowRect` at `0x1400a5998`
- `USER32!IsIconic` at `0x1400a5966`
- `USER32!IsIconic` at `0x1400a5966`
- `USER32!GetSystemMetrics` at `0x1400a5976`
- `USER32!GetSystemMetrics` at `0x1400a5986`
- `USER32!GetSystemMetrics` at `0x1400a5976`
- `USER32!GetSystemMetrics` at `0x1400a5986`
- `USER32!SystemParametersInfoW` at `0x1400a5a20`
- `USER32!SystemParametersInfoW` at `0x1400a5a20`

## pseudocode

```c
void __fastcall CDlgBase::CenterWindow(CDlgBase *this, HWND a2, __int64 a3, int a4)
{
  HWND v5; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v9; // rdx
  LONG v10; // edi
  LONG v11; // ebx
  int PaddedBorderWidth; // edx
  unsigned int v13; // eax
  POINT pt; // [rsp+40h] [rbp-40h]
  struct tagRECT Rect; // [rsp+48h] [rbp-38h] BYREF
  RECT rc; // [rsp+58h] [rbp-28h] BYREF
  struct tagRECT pvParam; // [rsp+68h] [rbp-18h] BYREF

  v5 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  rc = 0;
  pvParam = 0;
  if ( !v5 )
    return;
  GetWindowRect(v5, &Rect);
  if ( a2 )
  {
    if ( IsWindow(a2) )
    {
      if ( !IsIconic(a2) )
      {
        pt.x = GetSystemMetrics(0) - 1;
        pt.y = GetSystemMetrics(1) - 1;
        GetWindowRect(a2, &rc);
        if ( !PtInRect(&rc, 0) || !PtInRect(&rc, pt) )
        {
          if ( !CClientUtilsWin32::WorkRectFromHwnd(a2, &pvParam) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v9 = 19;
LABEL_17:
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v9,
                WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids,
                CurrentThreadActivityIdPrefix);
              return;
            }
            return;
          }
LABEL_19:
          v10 = (rc.right + rc.left + Rect.left - Rect.right) / 2;
          v11 = (rc.bottom + rc.top + Rect.top - Rect.bottom) / a4;
          PaddedBorderWidth = GetPaddedBorderWidth(*((HWND *)this + 1));
          if ( v10 >= pvParam.left )
          {
            if ( v10 > pvParam.right - Rect.right + Rect.left )
              v10 = Rect.left + pvParam.right - Rect.right - PaddedBorderWidth;
          }
          else
          {
            v10 = pvParam.left + PaddedBorderWidth;
          }
          if ( v11 >= pvParam.top )
          {
            if ( v11 > pvParam.bottom - Rect.bottom + Rect.top )
              v11 = Rect.top + pvParam.bottom - Rect.bottom - PaddedBorderWidth;
          }
          else
          {
            v11 = pvParam.top + PaddedBorderWidth;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v13 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DLD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids,
              v13,
              v10,
              v11);
          }
          SetWindowPos(*((HWND *)this + 1), 0, v10, v11, 0, 0, 0x15u);
          return;
        }
      }
    }
  }
  if ( SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
  {
    CopyRect(&rc, &pvParam);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 18;
    goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1400a58f8  push    rbp
0x1400a58fa  push    rbx
0x1400a58fb  push    rsi
0x1400a58fc  push    rdi
0x1400a58fd  push    r14
0x1400a58ff  mov     rbp, rsp
0x1400a5902  sub     rsp, 80h
0x1400a5909  mov     rax, cs:__security_cookie
0x1400a5910  xor     rax, rsp
0x1400a5913  mov     [rbp+var_8], rax
0x1400a5917  xorps   xmm0, xmm0
0x1400a591a  mov     rsi, rcx
0x1400a591d  mov     rcx, [rcx+8]; hWnd
0x1400a5921  xorps   xmm1, xmm1
0x1400a5924  mov     r14d, r9d
0x1400a5927  mov     rbx, rdx
0x1400a592a  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1400a592e  movups  xmmword ptr [rbp+rc.left], xmm1
0x1400a5932  movups  [rbp+pvParam], xmm0
0x1400a5936  test    rcx, rcx
0x1400a5939  jz      loc_1400A5B82
0x1400a593f  lea     rdx, [rbp+Rect]; lpRect
0x1400a5943  call    cs:__imp_GetWindowRect
0x1400a5949  test    rbx, rbx
0x1400a594c  jz      loc_1400A5A14
0x1400a5952  mov     rcx, rbx; hWnd
0x1400a5955  call    cs:__imp_IsWindow
0x1400a595b  test    eax, eax
0x1400a595d  jz      loc_1400A5A14
0x1400a5963  mov     rcx, rbx; hWnd
0x1400a5966  call    cs:__imp_IsIconic
0x1400a596c  test    eax, eax
0x1400a596e  jnz     loc_1400A5A14
0x1400a5974  xor     ecx, ecx; nIndex
0x1400a5976  call    cs:__imp_GetSystemMetrics
0x1400a597c  dec     eax
0x1400a597e  mov     ecx, 1; nIndex
0x1400a5983  mov     [rbp+pt.x], eax
0x1400a5986  call    cs:__imp_GetSystemMetrics
0x1400a598c  lea     rdx, [rbp+rc]; lpRect
0x1400a5990  mov     rcx, rbx; hWnd
0x1400a5993  dec     eax
0x1400a5995  mov     [rbp+pt.y], eax
0x1400a5998  call    cs:__imp_GetWindowRect
0x1400a599e  mov     rdx, qword ptr cs:pt.x; pt
0x1400a59a5  lea     rcx, [rbp+rc]; lprc
0x1400a59a9  call    cs:__imp_PtInRect
0x1400a59af  test    eax, eax
0x1400a59b1  jz      short loc_1400A59C5
0x1400a59b3  mov     rdx, qword ptr [rbp+pt.x]; pt
0x1400a59b7  lea     rcx, [rbp+rc]; lprc
0x1400a59bb  call    cs:__imp_PtInRect
0x1400a59c1  test    eax, eax
0x1400a59c3  jnz     short loc_1400A5A14
0x1400a59c5  lea     rdx, [rbp+pvParam]; struct tagRECT *
0x1400a59c9  mov     rcx, rbx; HWND
0x1400a59cc  call    ?WorkRectFromHwnd@CClientUtilsWin32@@SAHPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::WorkRectFromHwnd(HWND__ *,tagRECT *)
0x1400a59d1  test    eax, eax
0x1400a59d3  jnz     loc_1400A5A90
0x1400a59d9  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a59e0  lea     rax, WPP_GLOBAL_Control
0x1400a59e7  cmp     rdx, rax
0x1400a59ea  jz      loc_1400A5B82
0x1400a59f0  test    byte ptr [rdx+1Ch], 8
0x1400a59f4  jz      loc_1400A5B82
0x1400a59fa  mov     ecx, 2
0x1400a59ff  cmp     [rdx+19h], cl
0x1400a5a02  jb      loc_1400A5B82
0x1400a5a08  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a5a0d  mov     edx, 13h
0x1400a5a12  jmp     short loc_1400A5A63
0x1400a5a14  xor     edx, edx; uiParam
0x1400a5a16  lea     r8, [rbp+pvParam]; pvParam
0x1400a5a1a  xor     r9d, r9d; fWinIni
0x1400a5a1d  lea     ecx, [rdx+30h]; uiAction
0x1400a5a20  call    cs:__imp_SystemParametersInfoW
0x1400a5a26  test    eax, eax
0x1400a5a28  jnz     short loc_1400A5A82
0x1400a5a2a  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a5a31  lea     rax, WPP_GLOBAL_Control
0x1400a5a38  cmp     rdx, rax
0x1400a5a3b  jz      loc_1400A5B82
0x1400a5a41  test    byte ptr [rdx+1Ch], 8
0x1400a5a45  jz      loc_1400A5B82
0x1400a5a4b  mov     ecx, 2
0x1400a5a50  cmp     [rdx+19h], cl
0x1400a5a53  jb      loc_1400A5B82
0x1400a5a59  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a5a5e  mov     edx, 12h
0x1400a5a63  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5a6a  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x1400a5a71  mov     r9d, eax
0x1400a5a74  mov     rcx, [rcx+10h]
0x1400a5a78  call    WPP_SF_d
0x1400a5a7d  jmp     loc_1400A5B82
0x1400a5a82  lea     rdx, [rbp+pvParam]; lprcSrc
0x1400a5a86  lea     rcx, [rbp+rc]; lprcDst
0x1400a5a8a  call    cs:__imp_CopyRect
0x1400a5a90  mov     eax, [rbp+Rect.left]
0x1400a5a93  mov     ecx, 2
0x1400a5a98  sub     eax, [rbp+Rect.right]
0x1400a5a9b  add     eax, [rbp+rc.left]
0x1400a5a9e  add     eax, [rbp+rc.right]
0x1400a5aa1  cdq
0x1400a5aa2  idiv    ecx
0x1400a5aa4  mov     rcx, [rsi+8]; hWnd
0x1400a5aa8  mov     edi, eax
0x1400a5aaa  mov     eax, [rbp+Rect.top]
0x1400a5aad  sub     eax, [rbp+Rect.bottom]
0x1400a5ab0  add     eax, [rbp+rc.top]
0x1400a5ab3  add     eax, [rbp+rc.bottom]
0x1400a5ab6  cdq
0x1400a5ab7  idiv    r14d
0x1400a5aba  mov     ebx, eax
0x1400a5abc  call    ?GetPaddedBorderWidth@@YAHPEAUHWND__@@@Z; GetPaddedBorderWidth(HWND__ *)
0x1400a5ac1  mov     edx, eax
0x1400a5ac3  mov     eax, dword ptr [rbp+pvParam]
0x1400a5ac6  cmp     edi, eax
0x1400a5ac8  jge     short loc_1400A5ACF
0x1400a5aca  lea     edi, [rax+rdx]
0x1400a5acd  jmp     short loc_1400A5AE8
0x1400a5acf  mov     ecx, dword ptr [rbp+pvParam+8]
0x1400a5ad2  sub     ecx, [rbp+Rect.right]
0x1400a5ad5  mov     r8d, [rbp+Rect.left]
0x1400a5ad9  lea     eax, [rcx+r8]
0x1400a5add  cmp     edi, eax
0x1400a5adf  jle     short loc_1400A5AE8
0x1400a5ae1  mov     edi, ecx
0x1400a5ae3  sub     edi, edx
0x1400a5ae5  add     edi, r8d
0x1400a5ae8  mov     eax, dword ptr [rbp+pvParam+4]
0x1400a5aeb  cmp     ebx, eax
0x1400a5aed  jge     short loc_1400A5AF4
0x1400a5aef  lea     ebx, [rax+rdx]
0x1400a5af2  jmp     short loc_1400A5B0D
0x1400a5af4  mov     ecx, dword ptr [rbp+pvParam+0Ch]
0x1400a5af7  sub     ecx, [rbp+Rect.bottom]
0x1400a5afa  mov     r8d, [rbp+Rect.top]
0x1400a5afe  lea     eax, [rcx+r8]
0x1400a5b02  cmp     ebx, eax
0x1400a5b04  jle     short loc_1400A5B0D
0x1400a5b06  mov     ebx, ecx
0x1400a5b08  sub     ebx, edx
0x1400a5b0a  add     ebx, r8d
0x1400a5b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5b14  lea     rax, WPP_GLOBAL_Control
0x1400a5b1b  cmp     rcx, rax
0x1400a5b1e  jz      short loc_1400A5B58
0x1400a5b20  test    byte ptr [rcx+1Ch], 1
0x1400a5b24  jz      short loc_1400A5B58
0x1400a5b26  cmp     byte ptr [rcx+19h], 5
0x1400a5b2a  jb      short loc_1400A5B58
0x1400a5b2c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a5b31  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a5b38  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x1400a5b3f  mov     edx, 14h
0x1400a5b44  mov     [rsp+80h+cy], ebx
0x1400a5b48  mov     r9d, eax
0x1400a5b4b  mov     [rsp+80h+var_60], edi
0x1400a5b4f  mov     rcx, [rcx+10h]
0x1400a5b53  call    WPP_SF_DLD
0x1400a5b58  mov     rcx, [rsi+8]; hWnd
0x1400a5b5c  mov     r9d, ebx; Y
0x1400a5b5f  mov     [rsp+80h+uFlags], 15h; uFlags
0x1400a5b67  mov     r8d, edi; X
0x1400a5b6a  mov     [rsp+80h+cy], 0; cy
0x1400a5b72  xor     edx, edx; hWndInsertAfter
0x1400a5b74  mov     [rsp+80h+var_60], 0; cx
0x1400a5b7c  call    cs:__imp_SetWindowPos
0x1400a5b82  mov     rcx, [rbp+var_8]
0x1400a5b86  xor     rcx, rsp; StackCookie
0x1400a5b89  call    __security_check_cookie
0x1400a5b8e  add     rsp, 80h
0x1400a5b95  pop     r14
0x1400a5b97  pop     rdi
0x1400a5b98  pop     rsi
0x1400a5b99  pop     rbx
0x1400a5b9a  pop     rbp
0x1400a5b9b  retn
```
