# CSrApiViewerAxHost::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x1400afec0`
- end: `0x1400b0122`
- name: `?GetWindowContext@CSrApiViewerAxHost@@UEAAJPEAPEAUIOleInPlaceFrame@@PEAPEAUIOleInPlaceUIWindow@@PEAUtagRECT@@2PEAUtagOIFI@@@Z`
- size: `610`
- prototype: `int(CSrApiViewerAxHost *__hidden this, struct IOleInPlaceFrame **, struct IOleInPlaceUIWindow **, struct tagRECT *, struct tagRECT *, struct tagOIFI *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14001e2f4`
- `0x1400afec0`
- `0x140113390`

## import_xrefs

- `USER32!GetClientRect` at `0x1400aff8b`
- `USER32!GetClientRect` at `0x1400aff8b`
- `USER32!CopyRect` at `0x1400b006f`
- `USER32!CopyRect` at `0x1400b00a7`
- `USER32!CopyRect` at `0x1400b006f`
- `USER32!CopyRect` at `0x1400b00a7`
- `KERNEL32!GetLastError` at `0x1400aff95`
- `KERNEL32!GetLastError` at `0x1400aff95`

## pseudocode

```c
__int64 __fastcall CSrApiViewerAxHost::GetWindowContext(
        HWND *this,
        struct IOleInPlaceFrame **a2,
        struct IOleInPlaceUIWindow **a3,
        struct tagRECT *a4,
        struct tagRECT *lprcDst)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  signed int LastError; // ebx
  unsigned int v9; // eax
  LONG top; // ebp
  LONG bottom; // edi
  LONG left; // esi
  LONG right; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rdx
  struct tagRECT Rect; // [rsp+40h] [rbp-48h] BYREF

  Rect = 0;
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 132;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147467261);
    return (unsigned int)-2147467261;
  }
  if ( !lprcDst )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 133;
    goto LABEL_6;
  }
  if ( GetClientRect(this[15], &Rect) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      top = Rect.top;
      bottom = Rect.bottom;
      left = Rect.left;
      right = Rect.right;
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        135,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v14,
        left,
        top,
        right - left,
        bottom - top,
        *(_QWORD *)&Rect.left);
    }
    if ( CopyRect(lprcDst, &Rect) )
    {
      LastError = 0;
      if ( CopyRect(a4, &Rect) )
        return (unsigned int)LastError;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147467259;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 137;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147467259;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 136;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      v15,
      -2147467259);
    return (unsigned int)-2147467259;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v9, LastError);
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400afec0  mov     [rsp+arg_8], rbx
0x1400afec5  mov     [rsp+arg_10], rbp
0x1400afeca  push    rsi
0x1400afecb  push    rdi
0x1400afecc  push    r12
0x1400afece  push    r14
0x1400afed0  push    r15
0x1400afed2  sub     rsp, 60h
0x1400afed6  mov     rax, cs:__security_cookie
0x1400afedd  xor     rax, rsp
0x1400afee0  mov     [rsp+88h+var_38], rax
0x1400afee5  mov     r15, [rsp+88h+lprcDst]
0x1400afeed  xorps   xmm0, xmm0
0x1400afef0  mov     r12, r9
0x1400afef3  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x1400afef8  test    r9, r9
0x1400afefb  jnz     short loc_1400AFF52
0x1400afefd  mov     rax, cs:WPP_GLOBAL_Control
0x1400aff04  lea     r14, WPP_GLOBAL_Control
0x1400aff0b  cmp     rax, r14
0x1400aff0e  jz      short loc_1400AFF48
0x1400aff10  test    byte ptr [rax+1Ch], 8
0x1400aff14  jz      short loc_1400AFF48
0x1400aff16  cmp     byte ptr [rax+19h], 2
0x1400aff1a  jb      short loc_1400AFF48
0x1400aff1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aff21  mov     edx, 84h
0x1400aff26  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aff2d  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aff34  mov     r9d, eax
0x1400aff37  mov     [rsp+88h+var_68], 80004003h
0x1400aff3f  mov     rcx, [rcx+10h]
0x1400aff43  call    WPP_SF_Dd
0x1400aff48  mov     ebx, 80004003h
0x1400aff4d  jmp     loc_1400B00FA
0x1400aff52  test    r15, r15
0x1400aff55  jnz     short loc_1400AFF82
0x1400aff57  mov     rax, cs:WPP_GLOBAL_Control
0x1400aff5e  lea     r14, WPP_GLOBAL_Control
0x1400aff65  cmp     rax, r14
0x1400aff68  jz      short loc_1400AFF48
0x1400aff6a  test    byte ptr [rax+1Ch], 8
0x1400aff6e  jz      short loc_1400AFF48
0x1400aff70  cmp     byte ptr [rax+19h], 2
0x1400aff74  jb      short loc_1400AFF48
0x1400aff76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aff7b  mov     edx, 85h
0x1400aff80  jmp     short loc_1400AFF26
0x1400aff82  mov     rcx, [rcx+78h]; hWnd
0x1400aff86  lea     rdx, [rsp+88h+Rect]; lpRect
0x1400aff8b  call    cs:__imp_GetClientRect
0x1400aff91  test    eax, eax
0x1400aff93  jnz     short loc_1400B0000
0x1400aff95  call    cs:__imp_GetLastError
0x1400aff9b  mov     ebx, eax
0x1400aff9d  mov     rax, cs:WPP_GLOBAL_Control
0x1400affa4  lea     r14, WPP_GLOBAL_Control
0x1400affab  cmp     rax, r14
0x1400affae  jz      short loc_1400AFFE4
0x1400affb0  test    byte ptr [rax+1Ch], 8
0x1400affb4  jz      short loc_1400AFFE4
0x1400affb6  cmp     byte ptr [rax+19h], 2
0x1400affba  jb      short loc_1400AFFE4
0x1400affbc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400affc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400affc8  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400affcf  mov     edx, 86h
0x1400affd4  mov     [rsp+88h+var_68], ebx
0x1400affd8  mov     r9d, eax
0x1400affdb  mov     rcx, [rcx+10h]
0x1400affdf  call    WPP_SF_Dd
0x1400affe4  test    ebx, ebx
0x1400affe6  jle     short loc_1400AFFF1
0x1400affe8  movzx   ebx, bx
0x1400affeb  or      ebx, 80070000h
0x1400afff1  test    ebx, ebx
0x1400afff3  mov     eax, 80004005h
0x1400afff8  cmovns  ebx, eax
0x1400afffb  jmp     loc_1400B00FA
0x1400b0000  mov     rax, cs:WPP_GLOBAL_Control
0x1400b0007  lea     r14, WPP_GLOBAL_Control
0x1400b000e  cmp     rax, r14
0x1400b0011  jz      short loc_1400B0067
0x1400b0013  test    byte ptr [rax+1Ch], 1
0x1400b0017  jz      short loc_1400B0067
0x1400b0019  cmp     byte ptr [rax+19h], 5
0x1400b001d  jb      short loc_1400B0067
0x1400b001f  mov     ebp, [rsp+88h+Rect.top]
0x1400b0023  mov     edi, [rsp+88h+Rect.bottom]
0x1400b0027  mov     esi, [rsp+88h+Rect.left]
0x1400b002b  mov     ebx, [rsp+88h+Rect.right]
0x1400b002f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0034  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b003b  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0042  sub     edi, ebp
0x1400b0044  sub     ebx, esi
0x1400b0046  mov     [rsp+88h+var_50], edi
0x1400b004a  mov     edx, 87h
0x1400b004f  mov     [rsp+88h+var_58], ebx
0x1400b0053  mov     r9d, eax
0x1400b0056  mov     rcx, [rcx+10h]
0x1400b005a  mov     [rsp+88h+var_60], ebp
0x1400b005e  mov     [rsp+88h+var_68], esi
0x1400b0062  call    WPP_SF_Ddddd
0x1400b0067  lea     rdx, [rsp+88h+Rect]; lprcSrc
0x1400b006c  mov     rcx, r15; lprcDst
0x1400b006f  call    cs:__imp_CopyRect
0x1400b0075  test    eax, eax
0x1400b0077  jnz     short loc_1400B009D
0x1400b0079  mov     rax, cs:WPP_GLOBAL_Control
0x1400b0080  cmp     rax, r14
0x1400b0083  jz      short loc_1400B00F5
0x1400b0085  test    byte ptr [rax+1Ch], 8
0x1400b0089  jz      short loc_1400B00F5
0x1400b008b  cmp     byte ptr [rax+19h], 2
0x1400b008f  jb      short loc_1400B00F5
0x1400b0091  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0096  mov     edx, 88h
0x1400b009b  jmp     short loc_1400B00D3
0x1400b009d  lea     rdx, [rsp+88h+Rect]; lprcSrc
0x1400b00a2  mov     rcx, r12; lprcDst
0x1400b00a5  xor     ebx, ebx
0x1400b00a7  call    cs:__imp_CopyRect
0x1400b00ad  test    eax, eax
0x1400b00af  jnz     short loc_1400B00FA
0x1400b00b1  mov     rax, cs:WPP_GLOBAL_Control
0x1400b00b8  cmp     rax, r14
0x1400b00bb  jz      short loc_1400B00F5
0x1400b00bd  test    byte ptr [rax+1Ch], 8
0x1400b00c1  jz      short loc_1400B00F5
0x1400b00c3  cmp     byte ptr [rax+19h], 2
0x1400b00c7  jb      short loc_1400B00F5
0x1400b00c9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b00ce  mov     edx, 89h
0x1400b00d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b00da  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b00e1  mov     r9d, eax
0x1400b00e4  mov     [rsp+88h+var_68], 80004005h
0x1400b00ec  mov     rcx, [rcx+10h]
0x1400b00f0  call    WPP_SF_Dd
0x1400b00f5  mov     ebx, 80004005h
0x1400b00fa  mov     eax, ebx
0x1400b00fc  mov     rcx, [rsp+88h+var_38]
0x1400b0101  xor     rcx, rsp; StackCookie
0x1400b0104  call    __security_check_cookie
0x1400b0109  lea     r11, [rsp+88h+var_28]
0x1400b010e  mov     rbx, [r11+38h]
0x1400b0112  mov     rbp, [r11+40h]
0x1400b0116  mov     rsp, r11
0x1400b0119  pop     r15
0x1400b011b  pop     r14
0x1400b011d  pop     r12
0x1400b011f  pop     rdi
0x1400b0120  pop     rsi
0x1400b0121  retn
```
