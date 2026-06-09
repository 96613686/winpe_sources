# CDlgBase::CenterWindow(HWND__ *,int,int)

- ea: `0x1400a3788`
- end: `0x1400a3a2c`
- name: `?CenterWindow@CDlgBase@@IEAAXPEAUHWND__@@HH@Z`
- size: `676`
- prototype: `void(CDlgBase *__hidden this, HWND, int, int)`
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x14002a870`
- `0x14002af70`
- `0x140047e30`
- `0x14004de84`
- `0x1400502ac`
- `0x1400535e4`
- `0x140056d5c`
- `0x140057900`
- `0x1400579ac`
- `0x1400b2700`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14001e158`
- `0x1400a0000`
- `0x1400a3788`
- `0x1400a40fc`
- `0x140111220`

## import_xrefs

- `USER32!PtInRect` at `0x1400a3839`
- `USER32!PtInRect` at `0x1400a384b`
- `USER32!PtInRect` at `0x1400a3839`
- `USER32!PtInRect` at `0x1400a384b`
- `USER32!IsWindow` at `0x1400a37e5`
- `USER32!IsWindow` at `0x1400a37e5`
- `USER32!CopyRect` at `0x1400a391a`
- `USER32!CopyRect` at `0x1400a391a`
- `USER32!SetWindowPos` at `0x1400a3a0c`
- `USER32!SetWindowPos` at `0x1400a3a0c`
- `USER32!GetWindowRect` at `0x1400a37d3`
- `USER32!GetWindowRect` at `0x1400a3828`
- `USER32!GetWindowRect` at `0x1400a37d3`
- `USER32!GetWindowRect` at `0x1400a3828`
- `USER32!IsIconic` at `0x1400a37f6`
- `USER32!IsIconic` at `0x1400a37f6`
- `USER32!GetSystemMetrics` at `0x1400a3806`
- `USER32!GetSystemMetrics` at `0x1400a3816`
- `USER32!GetSystemMetrics` at `0x1400a3806`
- `USER32!GetSystemMetrics` at `0x1400a3816`
- `USER32!SystemParametersInfoW` at `0x1400a38b0`
- `USER32!SystemParametersInfoW` at `0x1400a38b0`

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
0x1400a3788  push    rbp
0x1400a378a  push    rbx
0x1400a378b  push    rsi
0x1400a378c  push    rdi
0x1400a378d  push    r14
0x1400a378f  mov     rbp, rsp
0x1400a3792  sub     rsp, 80h
0x1400a3799  mov     rax, cs:__security_cookie
0x1400a37a0  xor     rax, rsp
0x1400a37a3  mov     [rbp+var_8], rax
0x1400a37a7  xorps   xmm0, xmm0
0x1400a37aa  mov     rsi, rcx
0x1400a37ad  mov     rcx, [rcx+8]; hWnd
0x1400a37b1  xorps   xmm1, xmm1
0x1400a37b4  mov     r14d, r9d
0x1400a37b7  mov     rbx, rdx
0x1400a37ba  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1400a37be  movups  xmmword ptr [rbp+rc.left], xmm1
0x1400a37c2  movups  [rbp+pvParam], xmm0
0x1400a37c6  test    rcx, rcx
0x1400a37c9  jz      loc_1400A3A12
0x1400a37cf  lea     rdx, [rbp+Rect]; lpRect
0x1400a37d3  call    cs:__imp_GetWindowRect
0x1400a37d9  test    rbx, rbx
0x1400a37dc  jz      loc_1400A38A4
0x1400a37e2  mov     rcx, rbx; hWnd
0x1400a37e5  call    cs:__imp_IsWindow
0x1400a37eb  test    eax, eax
0x1400a37ed  jz      loc_1400A38A4
0x1400a37f3  mov     rcx, rbx; hWnd
0x1400a37f6  call    cs:__imp_IsIconic
0x1400a37fc  test    eax, eax
0x1400a37fe  jnz     loc_1400A38A4
0x1400a3804  xor     ecx, ecx; nIndex
0x1400a3806  call    cs:__imp_GetSystemMetrics
0x1400a380c  dec     eax
0x1400a380e  mov     ecx, 1; nIndex
0x1400a3813  mov     [rbp+pt.x], eax
0x1400a3816  call    cs:__imp_GetSystemMetrics
0x1400a381c  lea     rdx, [rbp+rc]; lpRect
0x1400a3820  mov     rcx, rbx; hWnd
0x1400a3823  dec     eax
0x1400a3825  mov     [rbp+pt.y], eax
0x1400a3828  call    cs:__imp_GetWindowRect
0x1400a382e  mov     rdx, qword ptr cs:pt.x; pt
0x1400a3835  lea     rcx, [rbp+rc]; lprc
0x1400a3839  call    cs:__imp_PtInRect
0x1400a383f  test    eax, eax
0x1400a3841  jz      short loc_1400A3855
0x1400a3843  mov     rdx, qword ptr [rbp+pt.x]; pt
0x1400a3847  lea     rcx, [rbp+rc]; lprc
0x1400a384b  call    cs:__imp_PtInRect
0x1400a3851  test    eax, eax
0x1400a3853  jnz     short loc_1400A38A4
0x1400a3855  lea     rdx, [rbp+pvParam]; struct tagRECT *
0x1400a3859  mov     rcx, rbx; HWND
0x1400a385c  call    ?WorkRectFromHwnd@CClientUtilsWin32@@SAHPEAUHWND__@@PEAUtagRECT@@@Z; CClientUtilsWin32::WorkRectFromHwnd(HWND__ *,tagRECT *)
0x1400a3861  test    eax, eax
0x1400a3863  jnz     loc_1400A3920
0x1400a3869  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a3870  lea     rax, WPP_GLOBAL_Control
0x1400a3877  cmp     rdx, rax
0x1400a387a  jz      loc_1400A3A12
0x1400a3880  test    byte ptr [rdx+1Ch], 8
0x1400a3884  jz      loc_1400A3A12
0x1400a388a  mov     ecx, 2
0x1400a388f  cmp     [rdx+19h], cl
0x1400a3892  jb      loc_1400A3A12
0x1400a3898  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a389d  mov     edx, 13h
0x1400a38a2  jmp     short loc_1400A38F3
0x1400a38a4  xor     edx, edx; uiParam
0x1400a38a6  lea     r8, [rbp+pvParam]; pvParam
0x1400a38aa  xor     r9d, r9d; fWinIni
0x1400a38ad  lea     ecx, [rdx+30h]; uiAction
0x1400a38b0  call    cs:__imp_SystemParametersInfoW
0x1400a38b6  test    eax, eax
0x1400a38b8  jnz     short loc_1400A3912
0x1400a38ba  mov     rdx, cs:WPP_GLOBAL_Control
0x1400a38c1  lea     rax, WPP_GLOBAL_Control
0x1400a38c8  cmp     rdx, rax
0x1400a38cb  jz      loc_1400A3A12
0x1400a38d1  test    byte ptr [rdx+1Ch], 8
0x1400a38d5  jz      loc_1400A3A12
0x1400a38db  mov     ecx, 2
0x1400a38e0  cmp     [rdx+19h], cl
0x1400a38e3  jb      loc_1400A3A12
0x1400a38e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a38ee  mov     edx, 12h
0x1400a38f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a38fa  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x1400a3901  mov     r9d, eax
0x1400a3904  mov     rcx, [rcx+10h]
0x1400a3908  call    WPP_SF_d
0x1400a390d  jmp     loc_1400A3A12
0x1400a3912  lea     rdx, [rbp+pvParam]; lprcSrc
0x1400a3916  lea     rcx, [rbp+rc]; lprcDst
0x1400a391a  call    cs:__imp_CopyRect
0x1400a3920  mov     eax, [rbp+Rect.left]
0x1400a3923  mov     ecx, 2
0x1400a3928  sub     eax, [rbp+Rect.right]
0x1400a392b  add     eax, [rbp+rc.left]
0x1400a392e  add     eax, [rbp+rc.right]
0x1400a3931  cdq
0x1400a3932  idiv    ecx
0x1400a3934  mov     rcx, [rsi+8]; hWnd
0x1400a3938  mov     edi, eax
0x1400a393a  mov     eax, [rbp+Rect.top]
0x1400a393d  sub     eax, [rbp+Rect.bottom]
0x1400a3940  add     eax, [rbp+rc.top]
0x1400a3943  add     eax, [rbp+rc.bottom]
0x1400a3946  cdq
0x1400a3947  idiv    r14d
0x1400a394a  mov     ebx, eax
0x1400a394c  call    ?GetPaddedBorderWidth@@YAHPEAUHWND__@@@Z; GetPaddedBorderWidth(HWND__ *)
0x1400a3951  mov     edx, eax
0x1400a3953  mov     eax, dword ptr [rbp+pvParam]
0x1400a3956  cmp     edi, eax
0x1400a3958  jge     short loc_1400A395F
0x1400a395a  lea     edi, [rax+rdx]
0x1400a395d  jmp     short loc_1400A3978
0x1400a395f  mov     ecx, dword ptr [rbp+pvParam+8]
0x1400a3962  sub     ecx, [rbp+Rect.right]
0x1400a3965  mov     r8d, [rbp+Rect.left]
0x1400a3969  lea     eax, [rcx+r8]
0x1400a396d  cmp     edi, eax
0x1400a396f  jle     short loc_1400A3978
0x1400a3971  mov     edi, ecx
0x1400a3973  sub     edi, edx
0x1400a3975  add     edi, r8d
0x1400a3978  mov     eax, dword ptr [rbp+pvParam+4]
0x1400a397b  cmp     ebx, eax
0x1400a397d  jge     short loc_1400A3984
0x1400a397f  lea     ebx, [rax+rdx]
0x1400a3982  jmp     short loc_1400A399D
0x1400a3984  mov     ecx, dword ptr [rbp+pvParam+0Ch]
0x1400a3987  sub     ecx, [rbp+Rect.bottom]
0x1400a398a  mov     r8d, [rbp+Rect.top]
0x1400a398e  lea     eax, [rcx+r8]
0x1400a3992  cmp     ebx, eax
0x1400a3994  jle     short loc_1400A399D
0x1400a3996  mov     ebx, ecx
0x1400a3998  sub     ebx, edx
0x1400a399a  add     ebx, r8d
0x1400a399d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a39a4  lea     rax, WPP_GLOBAL_Control
0x1400a39ab  cmp     rcx, rax
0x1400a39ae  jz      short loc_1400A39E8
0x1400a39b0  test    byte ptr [rcx+1Ch], 1
0x1400a39b4  jz      short loc_1400A39E8
0x1400a39b6  cmp     byte ptr [rcx+19h], 5
0x1400a39ba  jb      short loc_1400A39E8
0x1400a39bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400a39c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a39c8  lea     r8, WPP_26668ec9d1183481e5fb81b64c4b74bc_Traceguids
0x1400a39cf  mov     edx, 14h
0x1400a39d4  mov     [rsp+80h+cy], ebx
0x1400a39d8  mov     r9d, eax
0x1400a39db  mov     [rsp+80h+var_60], edi
0x1400a39df  mov     rcx, [rcx+10h]
0x1400a39e3  call    WPP_SF_DLD
0x1400a39e8  mov     rcx, [rsi+8]; hWnd
0x1400a39ec  mov     r9d, ebx; Y
0x1400a39ef  mov     [rsp+80h+uFlags], 15h; uFlags
0x1400a39f7  mov     r8d, edi; X
0x1400a39fa  mov     [rsp+80h+cy], 0; cy
0x1400a3a02  xor     edx, edx; hWndInsertAfter
0x1400a3a04  mov     [rsp+80h+var_60], 0; cx
0x1400a3a0c  call    cs:__imp_SetWindowPos
0x1400a3a12  mov     rcx, [rbp+var_8]
0x1400a3a16  xor     rcx, rsp; StackCookie
0x1400a3a19  call    __security_check_cookie
0x1400a3a1e  add     rsp, 80h
0x1400a3a25  pop     r14
0x1400a3a27  pop     rdi
0x1400a3a28  pop     rsi
0x1400a3a29  pop     rbx
0x1400a3a2a  pop     rbp
0x1400a3a2b  retn
```
