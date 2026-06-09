# CContainerWnd::ResizeAxHostWnd(int)

- ea: `0x1400197d4`
- end: `0x140019c87`
- name: `?ResizeAxHostWnd@CContainerWnd@@AEAAJH@Z`
- size: `1203`
- prototype: `__int64 __fastcall(CContainerWnd *__hidden this, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400179ec`
- `0x140017fe4`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x140013b28`
- `0x1400197d4`
- `0x14001e2f4`
- `0x140113316`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!RedrawWindow` at `0x140019bb9`
- `USER32!RedrawWindow` at `0x140019bb9`
- `USER32!MoveWindow` at `0x140019ba4`
- `USER32!MoveWindow` at `0x140019c5f`
- `USER32!MoveWindow` at `0x140019ba4`
- `USER32!MoveWindow` at `0x140019c5f`
- `USER32!GetClientRect` at `0x14001990c`
- `USER32!GetClientRect` at `0x14001990c`
- `USER32!GetWindowRect` at `0x140019a2b`
- `USER32!GetWindowRect` at `0x140019a2b`
- `KERNEL32!GetLastError` at `0x140019916`
- `KERNEL32!GetLastError` at `0x140019a35`
- `KERNEL32!GetLastError` at `0x140019916`
- `KERNEL32!GetLastError` at `0x140019a35`

## string_xrefs

- `0x1400198a9`: `_pContWndExtension`

## pseudocode

```c
__int64 __fastcall CContainerWnd::ResizeAxHostWnd(CContainerWnd *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v3; // edx
  const char *v4; // rcx
  signed int LastError; // ebx
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rdx
  LONG top; // r10d
  const unsigned __int16 *v11; // r8
  __int64 v12; // rax
  HWND ChildWindowRecursively; // rax
  LONG left; // r15d
  int v15; // r14d
  LONG v16; // r12d
  int v17; // esi
  double v18; // xmm2_8
  double v19; // xmm0_8
  double v20; // xmm3_8
  int v21; // r13d
  int nHeight; // r14d
  unsigned int v23; // eax
  unsigned int v24; // eax
  _QWORD v26[2]; // [rsp+40h] [rbp-29h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-19h] BYREF
  struct tagRECT v28; // [rsp+60h] [rbp-9h] BYREF

  v26[0] = 0;
  Rect = 0;
  if ( !*((_QWORD *)this + 10) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 260;
    v4 = "_pWndView";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v4,
      255);
    return (unsigned int)-2147418113;
  }
  v6 = *((_QWORD *)this + 233);
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 261;
    v4 = "_pContWndExtension";
    goto LABEL_6;
  }
  if ( !*((_QWORD *)this + 95) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 262;
    v4 = "_spTscSet";
    goto LABEL_6;
  }
  (*(void (__fastcall **)(__int64, _QWORD *, char *))(*(_QWORD *)v6 + 88LL))(v6, v26, (char *)v26 + 4);
  if ( !GetClientRect(*((HWND *)this + 1), &Rect) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 263;
LABEL_23:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v8, LastError);
LABEL_24:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  LastError = 0;
  top = LODWORD(v26[0]) + Rect.top;
  v11 = (const unsigned __int16 *)(unsigned int)(Rect.bottom - HIDWORD(v26[0]));
  v12 = *((_QWORD *)this + 95);
  Rect.top += LODWORD(v26[0]);
  Rect.bottom -= HIDWORD(v26[0]);
  if ( !*(_DWORD *)(v12 + 46160) || *(_DWORD *)(v12 + 6260) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        267,
        &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v24,
        Rect.left,
        Rect.top,
        Rect.right - Rect.left,
        Rect.bottom - Rect.top,
        v26[0]);
      LODWORD(v11) = Rect.bottom;
      top = Rect.top;
    }
    MoveWindow(*(HWND *)(*((_QWORD *)this + 10) + 16LL), Rect.left, top, Rect.right - Rect.left, (_DWORD)v11 - top, 1);
  }
  else
  {
    ChildWindowRecursively = (HWND)*((_QWORD *)this + 11);
    v28 = 0;
    if ( !ChildWindowRecursively )
    {
      ChildWindowRecursively = CContainerWnd::FindChildWindowRecursively(
                                 this,
                                 *(HWND *)(*((_QWORD *)this + 10) + 16LL),
                                 v11,
                                 v7);
      *((_QWORD *)this + 11) = ChildWindowRecursively;
      if ( !ChildWindowRecursively )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)-2147418113;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v3 = 264;
        v4 = "_hOPContainer";
        goto LABEL_6;
      }
    }
    if ( !GetWindowRect(ChildWindowRecursively, &v28) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 265;
      goto LABEL_23;
    }
    left = Rect.left;
    v15 = Rect.right - Rect.left;
    v16 = Rect.top;
    v17 = Rect.bottom - Rect.top;
    v18 = (double)(v28.right - v28.left) / (double)(v28.bottom - v28.top);
    v19 = (double)(Rect.right - Rect.left);
    v20 = (double)(Rect.bottom - Rect.top);
    if ( v18 <= v19 / v20 )
    {
      v21 = (int)ceil_0(v20 * v18);
      left = (int)ceil_0((double)(v15 - v21) * 0.5);
      nHeight = v17;
    }
    else
    {
      v21 = Rect.right - Rect.left;
      nHeight = (int)ceil_0(v19 / v18);
      v16 = (int)ceil_0((double)(v17 - nHeight) * 0.5);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        266,
        &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v23,
        left,
        v16,
        v21,
        nHeight,
        v26[0]);
    }
    MoveWindow(*(HWND *)(*((_QWORD *)this + 10) + 16LL), left, v16, v21, nHeight, 1);
    RedrawWindow(*((HWND *)this + 1), 0, 0, 5u);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400197d4  push    rbp
0x1400197d6  push    rbx
0x1400197d7  push    rsi
0x1400197d8  push    rdi
0x1400197d9  push    r12
0x1400197db  push    r13
0x1400197dd  push    r14
0x1400197df  push    r15
0x1400197e1  lea     rbp, [rsp-1Fh]
0x1400197e6  sub     rsp, 88h
0x1400197ed  mov     rax, cs:__security_cookie
0x1400197f4  xor     rax, rsp
0x1400197f7  mov     [rbp+57h+var_50], rax
0x1400197fb  xor     esi, esi
0x1400197fd  xorps   xmm0, xmm0
0x140019800  mov     rdi, rcx
0x140019803  mov     [rbp+57h+var_80], esi
0x140019806  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x14001980a  mov     [rbp+57h+var_7C], esi
0x14001980d  cmp     [rcx+50h], rsi
0x140019811  jnz     short loc_140019874
0x140019813  mov     rcx, cs:WPP_GLOBAL_Control
0x14001981a  lea     rax, WPP_GLOBAL_Control
0x140019821  cmp     rcx, rax
0x140019824  jz      short loc_14001986A
0x140019826  test    byte ptr [rcx+1Ch], 8
0x14001982a  jz      short loc_14001986A
0x14001982c  cmp     byte ptr [rcx+19h], 2
0x140019830  jb      short loc_14001986A
0x140019832  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140019837  mov     edx, 104h
0x14001983c  lea     rcx, aPwndview; "_pWndView"
0x140019843  mov     [rsp+0C0h+bRepaint], 8000FFFFh
0x14001984b  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140019852  mov     qword ptr [rsp+0C0h+nHeight], rcx
0x140019857  mov     r9d, eax
0x14001985a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019861  mov     rcx, [rcx+10h]
0x140019865  call    WPP_SF_DsD
0x14001986a  mov     ebx, 8000FFFFh
0x14001986f  jmp     loc_140019C65
0x140019874  mov     rcx, [rcx+748h]
0x14001987b  test    rcx, rcx
0x14001987e  jnz     short loc_1400198B2
0x140019880  mov     rcx, cs:WPP_GLOBAL_Control
0x140019887  lea     rax, WPP_GLOBAL_Control
0x14001988e  cmp     rcx, rax
0x140019891  jz      short loc_14001986A
0x140019893  test    byte ptr [rcx+1Ch], 8
0x140019897  jz      short loc_14001986A
0x140019899  cmp     byte ptr [rcx+19h], 2
0x14001989d  jb      short loc_14001986A
0x14001989f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400198a4  mov     edx, 105h
0x1400198a9  lea     rcx, aPcontwndextens; "_pContWndExtension"
0x1400198b0  jmp     short loc_140019843
0x1400198b2  cmp     [rdi+2F8h], rsi
0x1400198b9  jnz     short loc_1400198F0
0x1400198bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400198c2  lea     rax, WPP_GLOBAL_Control
0x1400198c9  cmp     rcx, rax
0x1400198cc  jz      short loc_14001986A
0x1400198ce  test    byte ptr [rcx+1Ch], 8
0x1400198d2  jz      short loc_14001986A
0x1400198d4  cmp     byte ptr [rcx+19h], 2
0x1400198d8  jb      short loc_14001986A
0x1400198da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400198df  mov     edx, 106h
0x1400198e4  lea     rcx, aSptscset; "_spTscSet"
0x1400198eb  jmp     loc_140019843
0x1400198f0  mov     rax, [rcx]
0x1400198f3  lea     r8, [rbp+57h+var_7C]
0x1400198f7  lea     rdx, [rbp+57h+var_80]
0x1400198fb  mov     rax, [rax+58h]
0x1400198ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019904  mov     rcx, [rdi+8]; hWnd
0x140019908  lea     rdx, [rbp+57h+Rect]; lpRect
0x14001990c  call    cs:__imp_GetClientRect
0x140019912  test    eax, eax
0x140019914  jnz     short loc_140019981
0x140019916  call    cs:__imp_GetLastError
0x14001991c  mov     ebx, eax
0x14001991e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019925  lea     rax, WPP_GLOBAL_Control
0x14001992c  cmp     rcx, rax
0x14001992f  jz      short loc_140019965
0x140019931  test    byte ptr [rcx+1Ch], 8
0x140019935  jz      short loc_140019965
0x140019937  cmp     byte ptr [rcx+19h], 2
0x14001993b  jb      short loc_140019965
0x14001993d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140019942  mov     edx, 107h
0x140019947  mov     rcx, cs:WPP_GLOBAL_Control
0x14001994e  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140019955  mov     r9d, eax
0x140019958  mov     [rsp+0C0h+nHeight], ebx
0x14001995c  mov     rcx, [rcx+10h]
0x140019960  call    WPP_SF_Dd
0x140019965  test    ebx, ebx
0x140019967  jle     short loc_140019972
0x140019969  movzx   ebx, bx
0x14001996c  or      ebx, 80070000h
0x140019972  test    ebx, ebx
0x140019974  mov     eax, 80004005h
0x140019979  cmovns  ebx, eax
0x14001997c  jmp     loc_140019C65
0x140019981  mov     r10d, [rbp+57h+Rect.top]
0x140019985  mov     ebx, esi
0x140019987  mov     r8d, [rbp+57h+Rect.bottom]
0x14001998b  add     r10d, [rbp+57h+var_80]
0x14001998f  sub     r8d, [rbp+57h+var_7C]; unsigned __int16 *
0x140019993  mov     rax, [rdi+2F8h]
0x14001999a  mov     [rbp+57h+Rect.top], r10d
0x14001999e  mov     [rbp+57h+Rect.bottom], r8d
0x1400199a2  cmp     [rax+0B450h], esi
0x1400199a8  jz      loc_140019BC4
0x1400199ae  cmp     [rax+1874h], esi
0x1400199b4  jnz     loc_140019BC4
0x1400199ba  mov     rax, [rdi+58h]
0x1400199be  xorps   xmm0, xmm0
0x1400199c1  movups  xmmword ptr [rbp+57h+var_60.left], xmm0
0x1400199c5  test    rax, rax
0x1400199c8  jnz     short loc_140019A24
0x1400199ca  mov     rdx, [rdi+50h]
0x1400199ce  mov     rcx, rdi; this
0x1400199d1  mov     rdx, [rdx+10h]; HWND
0x1400199d5  call    ?FindChildWindowRecursively@CContainerWnd@@AEAAPEAUHWND__@@PEAU2@PEBG1@Z; CContainerWnd::FindChildWindowRecursively(HWND__ *,ushort const *,ushort const *)
0x1400199da  mov     [rdi+58h], rax
0x1400199de  test    rax, rax
0x1400199e1  jnz     short loc_140019A24
0x1400199e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199ea  lea     rax, WPP_GLOBAL_Control
0x1400199f1  cmp     rcx, rax
0x1400199f4  jz      loc_14001986A
0x1400199fa  test    byte ptr [rcx+1Ch], 8
0x1400199fe  jz      loc_14001986A
0x140019a04  cmp     byte ptr [rcx+19h], 2
0x140019a08  jb      loc_14001986A
0x140019a0e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140019a13  mov     edx, 108h
0x140019a18  lea     rcx, aHopcontainer; "_hOPContainer"
0x140019a1f  jmp     loc_140019843
0x140019a24  lea     rdx, [rbp+57h+var_60]; lpRect
0x140019a28  mov     rcx, rax; hWnd
0x140019a2b  call    cs:__imp_GetWindowRect
0x140019a31  test    eax, eax
0x140019a33  jnz     short loc_140019A77
0x140019a35  call    cs:__imp_GetLastError
0x140019a3b  mov     ebx, eax
0x140019a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a44  lea     rax, WPP_GLOBAL_Control
0x140019a4b  cmp     rcx, rax
0x140019a4e  jz      loc_140019965
0x140019a54  test    byte ptr [rcx+1Ch], 8
0x140019a58  jz      loc_140019965
0x140019a5e  cmp     byte ptr [rcx+19h], 2
0x140019a62  jb      loc_140019965
0x140019a68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140019a6d  mov     edx, 109h
0x140019a72  jmp     loc_140019947
0x140019a77  mov     eax, [rbp+57h+var_60.right]
0x140019a7a  sub     eax, [rbp+57h+var_60.left]
0x140019a7d  mov     r14d, [rbp+57h+Rect.right]
0x140019a81  mov     r15d, [rbp+57h+Rect.left]
0x140019a85  sub     r14d, r15d
0x140019a88  mov     esi, [rbp+57h+Rect.bottom]
0x140019a8b  mov     r12d, [rbp+57h+Rect.top]
0x140019a8f  sub     esi, r12d
0x140019a92  movd    xmm2, eax
0x140019a96  mov     eax, [rbp+57h+var_60.bottom]
0x140019a99  sub     eax, [rbp+57h+var_60.top]
0x140019a9c  cvtdq2pd xmm2, xmm2
0x140019aa0  movd    xmm0, eax
0x140019aa4  cvtdq2pd xmm0, xmm0
0x140019aa8  movd    xmm3, esi
0x140019aac  divsd   xmm2, xmm0
0x140019ab0  movd    xmm0, r14d
0x140019ab5  cvtdq2pd xmm0, xmm0
0x140019ab9  cvtdq2pd xmm3, xmm3
0x140019abd  movaps  xmm1, xmm0
0x140019ac0  divsd   xmm1, xmm3
0x140019ac4  comisd  xmm2, xmm1
0x140019ac8  jbe     short loc_140019AFA
0x140019aca  divsd   xmm0, xmm2; X
0x140019ace  mov     r13d, r14d
0x140019ad1  call    ceil_0
0x140019ad6  cvttsd2si r14d, xmm0
0x140019adb  sub     esi, r14d
0x140019ade  movd    xmm0, esi
0x140019ae2  cvtdq2pd xmm0, xmm0
0x140019ae6  mulsd   xmm0, cs:__real@3fe0000000000000; X
0x140019aee  call    ceil_0
0x140019af3  cvttsd2si r12d, xmm0
0x140019af8  jmp     short loc_140019B2C
0x140019afa  mulsd   xmm3, xmm2
0x140019afe  movaps  xmm0, xmm3; X
0x140019b01  call    ceil_0
0x140019b06  cvttsd2si r13d, xmm0
0x140019b0b  sub     r14d, r13d
0x140019b0e  movd    xmm0, r14d
0x140019b13  cvtdq2pd xmm0, xmm0
0x140019b17  mulsd   xmm0, cs:__real@3fe0000000000000; X
0x140019b1f  call    ceil_0
0x140019b24  cvttsd2si r15d, xmm0
0x140019b29  mov     r14d, esi
0x140019b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b33  lea     rax, WPP_GLOBAL_Control
0x140019b3a  cmp     rcx, rax
0x140019b3d  jz      short loc_140019B86
0x140019b3f  test    dword ptr [rcx+1Ch], 100h
0x140019b46  jz      short loc_140019B86
0x140019b48  cmp     byte ptr [rcx+19h], 5
0x140019b4c  jb      short loc_140019B86
0x140019b4e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140019b53  mov     rcx, cs:WPP_GLOBAL_Control
0x140019b5a  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140019b61  mov     [rsp+0C0h+var_88], r14d
0x140019b66  mov     edx, 10Ah
0x140019b6b  mov     [rsp+0C0h+var_90], r13d
0x140019b70  mov     r9d, eax
0x140019b73  mov     [rsp+0C0h+bRepaint], r12d
0x140019b78  mov     rcx, [rcx+10h]
0x140019b7c  mov     [rsp+0C0h+nHeight], r15d
0x140019b81  call    WPP_SF_Ddddd
0x140019b86  mov     rcx, [rdi+50h]
0x140019b8a  mov     r9d, r13d; nWidth
0x140019b8d  mov     [rsp+0C0h+bRepaint], 1; bRepaint
0x140019b95  mov     r8d, r12d; Y
0x140019b98  mov     edx, r15d; X
0x140019b9b  mov     [rsp+0C0h+nHeight], r14d; nHeight
0x140019ba0  mov     rcx, [rcx+10h]; hWnd
0x140019ba4  call    cs:__imp_MoveWindow
0x140019baa  mov     rcx, [rdi+8]; hWnd
0x140019bae  mov     r9d, 5; flags
0x140019bb4  xor     r8d, r8d; hrgnUpdate
0x140019bb7  xor     edx, edx; lprcUpdate
0x140019bb9  call    cs:__imp_RedrawWindow
0x140019bbf  jmp     loc_140019C65
0x140019bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140019bcb  lea     rax, WPP_GLOBAL_Control
0x140019bd2  cmp     rcx, rax
0x140019bd5  jz      short loc_140019C3A
0x140019bd7  test    dword ptr [rcx+1Ch], 100h
0x140019bde  jz      short loc_140019C3A
0x140019be0  cmp     byte ptr [rcx+19h], 5
0x140019be4  jb      short loc_140019C3A
0x140019be6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140019beb  mov     r8d, [rbp+57h+Rect.left]
0x140019bef  mov     edx, 10Bh
0x140019bf4  mov     r10d, [rbp+57h+Rect.top]
0x140019bf8  mov     ecx, [rbp+57h+Rect.right]
0x140019bfb  mov     r9d, [rbp+57h+Rect.bottom]
0x140019bff  sub     ecx, r8d
0x140019c02  sub     r9d, r10d
0x140019c05  mov     [rsp+0C0h+var_88], r9d
0x140019c0a  mov     r9d, eax
0x140019c0d  mov     [rsp+0C0h+var_90], ecx
0x140019c11  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c18  mov     [rsp+0C0h+bRepaint], r10d
0x140019c1d  mov     [rsp+0C0h+nHeight], r8d
0x140019c22  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140019c29  mov     rcx, [rcx+10h]
0x140019c2d  call    WPP_SF_Ddddd
0x140019c32  mov     r8d, [rbp+57h+Rect.bottom]
0x140019c36  mov     r10d, [rbp+57h+Rect.top]
0x140019c3a  mov     rcx, [rdi+50h]
0x140019c3e  sub     r8d, r10d
0x140019c41  mov     r9d, [rbp+57h+Rect.right]
0x140019c45  mov     edx, [rbp+57h+Rect.left]; X
0x140019c48  sub     r9d, edx; nWidth
0x140019c4b  mov     [rsp+0C0h+bRepaint], 1; bRepaint
0x140019c53  mov     rcx, [rcx+10h]; hWnd
0x140019c57  mov     [rsp+0C0h+nHeight], r8d; nHeight
0x140019c5c  mov     r8d, r10d; Y
0x140019c5f  call    cs:__imp_MoveWindow
0x140019c65  mov     eax, ebx
0x140019c67  mov     rcx, [rbp+57h+var_50]
0x140019c6b  xor     rcx, rsp; StackCookie
0x140019c6e  call    __security_check_cookie
0x140019c73  add     rsp, 88h
0x140019c7a  pop     r15
0x140019c7c  pop     r14
0x140019c7e  pop     r13
0x140019c80  pop     r12
0x140019c82  pop     rdi
0x140019c83  pop     rsi
0x140019c84  pop     rbx
0x140019c85  pop     rbp
0x140019c86  retn
```
