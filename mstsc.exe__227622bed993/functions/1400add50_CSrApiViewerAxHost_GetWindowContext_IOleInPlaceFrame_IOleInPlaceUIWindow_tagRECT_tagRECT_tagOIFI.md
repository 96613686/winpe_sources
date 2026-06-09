# CSrApiViewerAxHost::GetWindowContext(IOleInPlaceFrame * *,IOleInPlaceUIWindow * *,tagRECT *,tagRECT *,tagOIFI *)

- ea: `0x1400add50`
- end: `0x1400adfb2`
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
- `0x1400add50`
- `0x140111220`

## import_xrefs

- `USER32!GetClientRect` at `0x1400ade1b`
- `USER32!GetClientRect` at `0x1400ade1b`
- `USER32!CopyRect` at `0x1400adeff`
- `USER32!CopyRect` at `0x1400adf37`
- `USER32!CopyRect` at `0x1400adeff`
- `USER32!CopyRect` at `0x1400adf37`
- `KERNEL32!GetLastError` at `0x1400ade25`
- `KERNEL32!GetLastError` at `0x1400ade25`

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
0x1400add50  mov     [rsp+arg_8], rbx
0x1400add55  mov     [rsp+arg_10], rbp
0x1400add5a  push    rsi
0x1400add5b  push    rdi
0x1400add5c  push    r12
0x1400add5e  push    r14
0x1400add60  push    r15
0x1400add62  sub     rsp, 60h
0x1400add66  mov     rax, cs:__security_cookie
0x1400add6d  xor     rax, rsp
0x1400add70  mov     [rsp+88h+var_38], rax
0x1400add75  mov     r15, [rsp+88h+lprcDst]
0x1400add7d  xorps   xmm0, xmm0
0x1400add80  mov     r12, r9
0x1400add83  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x1400add88  test    r9, r9
0x1400add8b  jnz     short loc_1400ADDE2
0x1400add8d  mov     rax, cs:WPP_GLOBAL_Control
0x1400add94  lea     r14, WPP_GLOBAL_Control
0x1400add9b  cmp     rax, r14
0x1400add9e  jz      short loc_1400ADDD8
0x1400adda0  test    byte ptr [rax+1Ch], 8
0x1400adda4  jz      short loc_1400ADDD8
0x1400adda6  cmp     byte ptr [rax+19h], 2
0x1400addaa  jb      short loc_1400ADDD8
0x1400addac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400addb1  mov     edx, 84h
0x1400addb6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400addbd  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400addc4  mov     r9d, eax
0x1400addc7  mov     [rsp+88h+var_68], 80004003h
0x1400addcf  mov     rcx, [rcx+10h]
0x1400addd3  call    WPP_SF_Dd
0x1400addd8  mov     ebx, 80004003h
0x1400adddd  jmp     loc_1400ADF8A
0x1400adde2  test    r15, r15
0x1400adde5  jnz     short loc_1400ADE12
0x1400adde7  mov     rax, cs:WPP_GLOBAL_Control
0x1400addee  lea     r14, WPP_GLOBAL_Control
0x1400addf5  cmp     rax, r14
0x1400addf8  jz      short loc_1400ADDD8
0x1400addfa  test    byte ptr [rax+1Ch], 8
0x1400addfe  jz      short loc_1400ADDD8
0x1400ade00  cmp     byte ptr [rax+19h], 2
0x1400ade04  jb      short loc_1400ADDD8
0x1400ade06  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ade0b  mov     edx, 85h
0x1400ade10  jmp     short loc_1400ADDB6
0x1400ade12  mov     rcx, [rcx+78h]; hWnd
0x1400ade16  lea     rdx, [rsp+88h+Rect]; lpRect
0x1400ade1b  call    cs:__imp_GetClientRect
0x1400ade21  test    eax, eax
0x1400ade23  jnz     short loc_1400ADE90
0x1400ade25  call    cs:__imp_GetLastError
0x1400ade2b  mov     ebx, eax
0x1400ade2d  mov     rax, cs:WPP_GLOBAL_Control
0x1400ade34  lea     r14, WPP_GLOBAL_Control
0x1400ade3b  cmp     rax, r14
0x1400ade3e  jz      short loc_1400ADE74
0x1400ade40  test    byte ptr [rax+1Ch], 8
0x1400ade44  jz      short loc_1400ADE74
0x1400ade46  cmp     byte ptr [rax+19h], 2
0x1400ade4a  jb      short loc_1400ADE74
0x1400ade4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ade51  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ade58  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ade5f  mov     edx, 86h
0x1400ade64  mov     [rsp+88h+var_68], ebx
0x1400ade68  mov     r9d, eax
0x1400ade6b  mov     rcx, [rcx+10h]
0x1400ade6f  call    WPP_SF_Dd
0x1400ade74  test    ebx, ebx
0x1400ade76  jle     short loc_1400ADE81
0x1400ade78  movzx   ebx, bx
0x1400ade7b  or      ebx, 80070000h
0x1400ade81  test    ebx, ebx
0x1400ade83  mov     eax, 80004005h
0x1400ade88  cmovns  ebx, eax
0x1400ade8b  jmp     loc_1400ADF8A
0x1400ade90  mov     rax, cs:WPP_GLOBAL_Control
0x1400ade97  lea     r14, WPP_GLOBAL_Control
0x1400ade9e  cmp     rax, r14
0x1400adea1  jz      short loc_1400ADEF7
0x1400adea3  test    byte ptr [rax+1Ch], 1
0x1400adea7  jz      short loc_1400ADEF7
0x1400adea9  cmp     byte ptr [rax+19h], 5
0x1400adead  jb      short loc_1400ADEF7
0x1400adeaf  mov     ebp, [rsp+88h+Rect.top]
0x1400adeb3  mov     edi, [rsp+88h+Rect.bottom]
0x1400adeb7  mov     esi, [rsp+88h+Rect.left]
0x1400adebb  mov     ebx, [rsp+88h+Rect.right]
0x1400adebf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400adec4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adecb  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aded2  sub     edi, ebp
0x1400aded4  sub     ebx, esi
0x1400aded6  mov     [rsp+88h+var_50], edi
0x1400adeda  mov     edx, 87h
0x1400adedf  mov     [rsp+88h+var_58], ebx
0x1400adee3  mov     r9d, eax
0x1400adee6  mov     rcx, [rcx+10h]
0x1400adeea  mov     [rsp+88h+var_60], ebp
0x1400adeee  mov     [rsp+88h+var_68], esi
0x1400adef2  call    WPP_SF_Ddddd
0x1400adef7  lea     rdx, [rsp+88h+Rect]; lprcSrc
0x1400adefc  mov     rcx, r15; lprcDst
0x1400adeff  call    cs:__imp_CopyRect
0x1400adf05  test    eax, eax
0x1400adf07  jnz     short loc_1400ADF2D
0x1400adf09  mov     rax, cs:WPP_GLOBAL_Control
0x1400adf10  cmp     rax, r14
0x1400adf13  jz      short loc_1400ADF85
0x1400adf15  test    byte ptr [rax+1Ch], 8
0x1400adf19  jz      short loc_1400ADF85
0x1400adf1b  cmp     byte ptr [rax+19h], 2
0x1400adf1f  jb      short loc_1400ADF85
0x1400adf21  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400adf26  mov     edx, 88h
0x1400adf2b  jmp     short loc_1400ADF63
0x1400adf2d  lea     rdx, [rsp+88h+Rect]; lprcSrc
0x1400adf32  mov     rcx, r12; lprcDst
0x1400adf35  xor     ebx, ebx
0x1400adf37  call    cs:__imp_CopyRect
0x1400adf3d  test    eax, eax
0x1400adf3f  jnz     short loc_1400ADF8A
0x1400adf41  mov     rax, cs:WPP_GLOBAL_Control
0x1400adf48  cmp     rax, r14
0x1400adf4b  jz      short loc_1400ADF85
0x1400adf4d  test    byte ptr [rax+1Ch], 8
0x1400adf51  jz      short loc_1400ADF85
0x1400adf53  cmp     byte ptr [rax+19h], 2
0x1400adf57  jb      short loc_1400ADF85
0x1400adf59  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400adf5e  mov     edx, 89h
0x1400adf63  mov     rcx, cs:WPP_GLOBAL_Control
0x1400adf6a  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400adf71  mov     r9d, eax
0x1400adf74  mov     [rsp+88h+var_68], 80004005h
0x1400adf7c  mov     rcx, [rcx+10h]
0x1400adf80  call    WPP_SF_Dd
0x1400adf85  mov     ebx, 80004005h
0x1400adf8a  mov     eax, ebx
0x1400adf8c  mov     rcx, [rsp+88h+var_38]
0x1400adf91  xor     rcx, rsp; StackCookie
0x1400adf94  call    __security_check_cookie
0x1400adf99  lea     r11, [rsp+88h+var_28]
0x1400adf9e  mov     rbx, [r11+38h]
0x1400adfa2  mov     rbp, [r11+40h]
0x1400adfa6  mov     rsp, r11
0x1400adfa9  pop     r15
0x1400adfab  pop     r14
0x1400adfad  pop     r12
0x1400adfaf  pop     rdi
0x1400adfb0  pop     rsi
0x1400adfb1  retn
```
