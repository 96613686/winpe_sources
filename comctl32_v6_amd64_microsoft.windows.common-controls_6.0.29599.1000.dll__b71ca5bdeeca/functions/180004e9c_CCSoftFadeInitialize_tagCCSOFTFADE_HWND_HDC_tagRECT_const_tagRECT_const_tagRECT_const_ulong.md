# CCSoftFadeInitialize(tagCCSOFTFADE *,HWND__ *,HDC__ *,tagRECT const *,tagRECT const *,tagRECT const *,ulong)

- ea: `0x180004e9c`
- end: `0x1800050f3`
- name: `?CCSoftFadeInitialize@@YAPEAUHDC__@@PEAUtagCCSOFTFADE@@PEAUHWND__@@PEAU1@PEBUtagRECT@@33K@Z`
- size: `599`
- prototype: `HDC __fastcall(UINT_PTR uIDEvent, HWND hWnd, HDC hdc, RECT *lprc2, const struct tagRECT *, const struct tagRECT *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004528`
- `0x180005464`
- `0x1800d6054`
- `0x180117e94`

## callees

- `0x180004e9c`
- `0x1800052e8`
- `0x180005e7c`
- `0x180114520`
- `0x180114ebc`

## import_xrefs

- `GDI32!SelectClipRgn` at `0x18000507c`
- `GDI32!SelectClipRgn` at `0x18000507c`
- `GDI32!CreateRectRgn` at `0x1800050e1`
- `GDI32!CreateRectRgn` at `0x1800050e1`
- `GDI32!CreateRectRgnIndirect` at `0x1800050cd`
- `GDI32!CreateRectRgnIndirect` at `0x1800050cd`
- `USER32!GetWindowDC` at `0x18000500d`
- `USER32!GetWindowDC` at `0x18000500d`
- `USER32!IsRectEmpty` at `0x180004f5d`
- `USER32!IsRectEmpty` at `0x180004f5d`
- `USER32!KillTimer` at `0x180005095`
- `USER32!KillTimer` at `0x180005095`
- `USER32!GetParent` at `0x180004ee9`
- `USER32!GetParent` at `0x180004fac`
- `USER32!GetParent` at `0x180004ee9`
- `USER32!GetParent` at `0x180004fac`
- `USER32!GetWindowLongW` at `0x180004f9d`
- `USER32!GetWindowLongW` at `0x180004f9d`
- `USER32!IsWindow` at `0x180004ef5`
- `USER32!IsWindow` at `0x180004fb8`
- `USER32!IsWindow` at `0x180004ef5`
- `USER32!IsWindow` at `0x180004fb8`
- `USER32!ReleaseDC` at `0x180005029`
- `USER32!ReleaseDC` at `0x180005029`
- `USER32!EqualRect` at `0x180004ff0`
- `USER32!EqualRect` at `0x180005046`
- `USER32!EqualRect` at `0x180005059`
- `USER32!EqualRect` at `0x18000506c`
- `USER32!EqualRect` at `0x180004ff0`
- `USER32!EqualRect` at `0x180005046`
- `USER32!EqualRect` at `0x180005059`
- `USER32!EqualRect` at `0x18000506c`

## pseudocode

```c
HDC __fastcall CCSoftFadeInitialize(
        _DWORD *uIDEvent,
        HWND hWnd,
        HDC hdc,
        RECT *lprc2,
        struct tagRECT *a5,
        const struct tagRECT *a6,
        unsigned int a7)
{
  RECT *v7; // rax
  HWND Parent; // rsi
  BOOL i; // eax
  RECT v15; // xmm0
  HDC WindowDC; // rax
  __int64 v18; // rdi
  HDC v19; // rdx
  RECT rc2; // [rsp+20h] [rbp-68h] BYREF
  RECT v21; // [rsp+30h] [rbp-58h] BYREF

  v7 = a5;
  if ( !a5 )
    v7 = lprc2;
  v21 = 0;
  rc2 = *v7;
  Parent = GetParent(hWnd);
  for ( i = IsWindow(Parent); i && a7; i = IsWindow(Parent) )
  {
    if ( (GetWindowLongW(Parent, -20) & 0x2000000) != 0 )
      a7 = 0;
    else
      Parent = GetParent(Parent);
  }
  if ( !uIDEvent[36] )
    goto LABEL_6;
  if ( !*uIDEvent
    || *((HWND *)uIDEvent + 7) != hWnd
    || !EqualRect((const RECT *)(uIDEvent + 18), lprc2)
    || !EqualRect((const RECT *)(uIDEvent + 22), &rc2)
    || !EqualRect((const RECT *)(uIDEvent + 26), &v21) )
  {
    if ( uIDEvent[36] )
      _SoftFadeEnd((UINT_PTR)uIDEvent);
LABEL_6:
    memset_0(uIDEvent, 0, 0x98u);
    *((_QWORD *)uIDEvent + 7) = hWnd;
    uIDEvent[35] = a7;
    *(RECT *)(uIDEvent + 18) = *lprc2;
    if ( a7 )
      v15 = rc2;
    else
      v15 = *lprc2;
    *(RECT *)(uIDEvent + 22) = v15;
    *(RECT *)(uIDEvent + 26) = v21;
    if ( !IsRectEmpty(lprc2) )
    {
      if ( a7 )
      {
        WindowDC = GetWindowDC(hWnd);
        *((_QWORD *)uIDEvent + 8) = WindowDC;
      }
      else
      {
        WindowDC = hdc;
      }
      if ( WindowDC )
      {
        v18 = CCBeginDoubleBuffer(WindowDC);
        if ( v18 && *uIDEvent )
        {
          if ( !EqualRect((const RECT *)(uIDEvent + 22), (const RECT *)(uIDEvent + 18)) )
          {
            *((_QWORD *)uIDEvent + 15) = CreateRectRgnIndirect((const RECT *)(uIDEvent + 22));
            *((_QWORD *)uIDEvent + 16) = CreateRectRgn(0, 0, 0, 0);
          }
          return (HDC)v18;
        }
        else
        {
          v19 = (HDC)*((_QWORD *)uIDEvent + 8);
          if ( v19 )
            ReleaseDC(hWnd, v19);
        }
      }
    }
    return hdc;
  }
  SelectClipRgn(*((HDC *)uIDEvent + 1), 0);
  hdc = (HDC)*((_QWORD *)uIDEvent + 1);
  if ( a7 )
  {
    KillTimer(*((HWND *)uIDEvent + 7), (UINT_PTR)uIDEvent);
    uIDEvent[36] = 0;
    uIDEvent[35] = a7;
  }
  return hdc;
}

```

## disassembly

```asm
0x180004e9c  push    rbx
0x180004e9e  push    rbp
0x180004e9f  push    rsi
0x180004ea0  push    rdi
0x180004ea1  push    r12
0x180004ea3  push    r14
0x180004ea5  push    r15
0x180004ea7  sub     rsp, 50h
0x180004eab  mov     rax, cs:__security_cookie
0x180004eb2  xor     rax, rsp
0x180004eb5  mov     [rsp+88h+var_48], rax
0x180004eba  mov     rax, [rsp+88h+arg_20]
0x180004ec2  mov     rbx, rcx
0x180004ec5  test    rax, rax
0x180004ec8  xorps   xmm1, xmm1
0x180004ecb  mov     rcx, rdx; hWnd
0x180004ece  mov     r12, r9
0x180004ed1  cmovz   rax, r9
0x180004ed5  mov     rbp, r8
0x180004ed8  mov     r15, rdx
0x180004edb  movups  xmmword ptr [rsp+88h+var_58.left], xmm1
0x180004ee0  movups  xmm0, xmmword ptr [rax]
0x180004ee3  movdqu  xmmword ptr [rsp+88h+rc2.left], xmm0
0x180004ee9  call    cs:__imp_GetParent
0x180004eef  mov     rcx, rax; hWnd
0x180004ef2  mov     rsi, rax
0x180004ef5  call    cs:__imp_IsWindow
0x180004efb  mov     edi, [rsp+88h+arg_30]
0x180004f02  test    eax, eax
0x180004f04  jnz     loc_180004F8D
0x180004f0a  cmp     dword ptr [rbx+90h], 0
0x180004f11  jnz     loc_180005034
0x180004f17  xor     edx, edx; Val
0x180004f19  mov     r8d, 98h; Size
0x180004f1f  mov     rcx, rbx; void *
0x180004f22  call    memset_0
0x180004f27  mov     [rbx+38h], r15
0x180004f2b  lea     rsi, [rbx+48h]
0x180004f2f  mov     [rbx+8Ch], edi
0x180004f35  movups  xmm0, xmmword ptr [r12]
0x180004f3a  movdqu  xmmword ptr [rsi], xmm0
0x180004f3e  test    edi, edi
0x180004f40  jz      short loc_180004F86
0x180004f42  movaps  xmm0, xmmword ptr [rsp+88h+rc2.left]
0x180004f47  lea     r14, [rbx+58h]
0x180004f4b  mov     rcx, r12; lprc
0x180004f4e  movdqu  xmmword ptr [r14], xmm0
0x180004f53  movups  xmm0, xmmword ptr [rsp+88h+var_58.left]
0x180004f58  movdqu  xmmword ptr [rbx+68h], xmm0
0x180004f5d  call    cs:__imp_IsRectEmpty
0x180004f63  test    eax, eax
0x180004f65  jz      short loc_180004FC3
0x180004f67  mov     rax, rbp
0x180004f6a  mov     rcx, [rsp+88h+var_48]
0x180004f6f  xor     rcx, rsp; StackCookie
0x180004f72  call    __security_check_cookie
0x180004f77  add     rsp, 50h
0x180004f7b  pop     r15
0x180004f7d  pop     r14
0x180004f7f  pop     r12
0x180004f81  pop     rdi
0x180004f82  pop     rsi
0x180004f83  pop     rbp
0x180004f84  pop     rbx
0x180004f85  retn
0x180004f86  movups  xmm0, xmmword ptr [r12]
0x180004f8b  jmp     short loc_180004F47
0x180004f8d  test    edi, edi
0x180004f8f  jz      loc_180004F0A
0x180004f95  mov     edx, 0FFFFFFECh; nIndex
0x180004f9a  mov     rcx, rsi; hWnd
0x180004f9d  call    cs:__imp_GetWindowLongW
0x180004fa3  bt      eax, 19h
0x180004fa7  jb      short loc_180005006
0x180004fa9  mov     rcx, rsi; hWnd
0x180004fac  call    cs:__imp_GetParent
0x180004fb2  mov     rsi, rax
0x180004fb5  mov     rcx, rsi; hWnd
0x180004fb8  call    cs:__imp_IsWindow
0x180004fbe  jmp     loc_180004F02
0x180004fc3  test    edi, edi
0x180004fc5  jnz     short loc_18000500A
0x180004fc7  mov     rax, rbp
0x180004fca  test    rax, rax
0x180004fcd  jz      short loc_180004F67
0x180004fcf  mov     r8, rbx
0x180004fd2  mov     rdx, rsi
0x180004fd5  mov     rcx, rax; hdc
0x180004fd8  call    CCBeginDoubleBuffer
0x180004fdd  mov     rdi, rax
0x180004fe0  test    rax, rax
0x180004fe3  jz      short loc_180005019
0x180004fe5  cmp     dword ptr [rbx], 0
0x180004fe8  jz      short loc_180005019
0x180004fea  mov     rdx, rsi; lprc2
0x180004fed  mov     rcx, r14; lprc1
0x180004ff0  call    cs:__imp_EqualRect
0x180004ff6  test    eax, eax
0x180004ff8  jz      loc_1800050CA
0x180004ffe  mov     rbp, rdi
0x180005001  jmp     loc_180004F67
0x180005006  xor     edi, edi
0x180005008  jmp     short loc_180004FB5
0x18000500a  mov     rcx, r15; hWnd
0x18000500d  call    cs:__imp_GetWindowDC
0x180005013  mov     [rbx+40h], rax
0x180005017  jmp     short loc_180004FCA
0x180005019  mov     rdx, [rbx+40h]; hDC
0x18000501d  test    rdx, rdx
0x180005020  jz      loc_180004F67
0x180005026  mov     rcx, r15; hWnd
0x180005029  call    cs:__imp_ReleaseDC
0x18000502f  jmp     loc_180004F67
0x180005034  cmp     dword ptr [rbx], 0
0x180005037  jz      short loc_1800050B0
0x180005039  cmp     [rbx+38h], r15
0x18000503d  jnz     short loc_1800050B0
0x18000503f  lea     rcx, [rbx+48h]; lprc1
0x180005043  mov     rdx, r12; lprc2
0x180005046  call    cs:__imp_EqualRect
0x18000504c  test    eax, eax
0x18000504e  jz      short loc_1800050B0
0x180005050  lea     rcx, [rbx+58h]; lprc1
0x180005054  lea     rdx, [rsp+88h+rc2]; lprc2
0x180005059  call    cs:__imp_EqualRect
0x18000505f  test    eax, eax
0x180005061  jz      short loc_1800050B0
0x180005063  lea     rcx, [rbx+68h]; lprc1
0x180005067  lea     rdx, [rsp+88h+var_58]; lprc2
0x18000506c  call    cs:__imp_EqualRect
0x180005072  test    eax, eax
0x180005074  jz      short loc_1800050B0
0x180005076  mov     rcx, [rbx+8]; hdc
0x18000507a  xor     edx, edx; hrgn
0x18000507c  call    cs:__imp_SelectClipRgn
0x180005082  mov     rbp, [rbx+8]
0x180005086  test    edi, edi
0x180005088  jz      loc_180004F67
0x18000508e  mov     rcx, [rbx+38h]; hWnd
0x180005092  mov     rdx, rbx; uIDEvent
0x180005095  call    cs:__imp_KillTimer
0x18000509b  mov     dword ptr [rbx+90h], 0
0x1800050a5  mov     [rbx+8Ch], edi
0x1800050ab  jmp     loc_180004F67
0x1800050b0  cmp     dword ptr [rbx+90h], 0
0x1800050b7  jz      loc_180004F17
0x1800050bd  mov     rcx, rbx; uIDEvent
0x1800050c0  call    ?_SoftFadeEnd@@YAXPEAUtagCCSOFTFADE@@@Z; _SoftFadeEnd(tagCCSOFTFADE *)
0x1800050c5  jmp     loc_180004F17
0x1800050ca  mov     rcx, r14; lprect
0x1800050cd  call    cs:__imp_CreateRectRgnIndirect
0x1800050d3  xor     r9d, r9d; y2
0x1800050d6  xor     r8d, r8d; x2
0x1800050d9  xor     edx, edx; y1
0x1800050db  mov     [rbx+78h], rax
0x1800050df  xor     ecx, ecx; x1
0x1800050e1  call    cs:__imp_CreateRectRgn
0x1800050e7  mov     [rbx+80h], rax
0x1800050ee  jmp     loc_180004FFE
```
