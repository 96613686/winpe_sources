# CCmbBxWinHost::OnCreate(tagCREATESTRUCTW const *)

- ea: `0x18004f8e0`
- end: `0x18004fc47`
- name: `?OnCreate@CCmbBxWinHost@@UEAA_JPEBUtagCREATESTRUCTW@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(CCmbBxWinHost *__hidden this, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18004e5a4`
- `0x18004f8e0`
- `0x180051788`
- `0x18005d0bc`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18004fae5`
- `USER32!GetWindowLongPtrW` at `0x18004fae5`
- `USER32!SetParent` at `0x18004fb3a`
- `USER32!SetParent` at `0x18004fb3a`
- `USER32!ShowWindow` at `0x18004fb25`
- `USER32!ShowWindow` at `0x18004fb25`
- `USER32!CreateWindowExA` at `0x18004facd`
- `USER32!CreateWindowExA` at `0x18004facd`
- `USER32!CreateWindowExW` at `0x18004fab8`
- `USER32!CreateWindowExW` at `0x18004fab8`
- `USER32!ReleaseDC` at `0x18004f9ad`
- `USER32!ReleaseDC` at `0x18004f9ad`
- `USER32!GetDC` at `0x18004f96a`
- `USER32!GetDC` at `0x18004f96a`

## pseudocode

```c
__int64 __fastcall CCmbBxWinHost::OnCreate(CCmbBxWinHost *this, const struct tagCREATESTRUCTW *a2)
{
  LONG v3; // ecx
  int cy; // eax
  bool v5; // sf
  LONG v7; // eax
  LONG v8; // ecx
  int cx; // eax
  LONG v10; // eax
  __int64 v11; // rcx
  HDC DC; // rbx
  HDC v13; // rdx
  int v14; // r8d
  int v15; // r9d
  int ECDefaultHeightAndWidth; // eax
  HWND v17; // rcx
  unsigned int v18; // r8d
  int Y; // r10d
  int X; // r11d
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  int v24; // r9d
  DWORD v25; // r9d
  DWORD v26; // ecx
  HWND v27; // rax
  LONG_PTR WindowLongPtrW; // rax
  __int64 v29; // rcx
  void (__fastcall *v30)(__int64, __int64, __int64); // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  int nWidth; // [rsp+30h] [rbp-D0h]
  int nHeight; // [rsp+38h] [rbp-C8h]
  HWND hWndParent; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT v38; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v39[48]; // [rsp+80h] [rbp-80h] BYREF

  v3 = a2->y;
  cy = 0;
  v5 = a2->cy < 0;
  v38.top = v3;
  if ( !v5 )
    cy = a2->cy;
  v7 = v3 + cy;
  v8 = a2->x;
  v5 = a2->cx < 0;
  v38.bottom = v7;
  cx = 0;
  if ( !v5 )
    cx = a2->cx;
  v10 = v8 + cx;
  v38.left = v8;
  v11 = *((_QWORD *)this + 4);
  v38.right = v10;
  if ( (*(int (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v11 + 72LL))(v11, &v38) < 0 )
    return -1;
  DC = GetDC(*((HWND *)this + 2));
  ECDefaultHeightAndWidth = GetECDefaultHeightAndWidth(
                              *((struct ITextServices **)this + 4),
                              v13,
                              v14,
                              v15,
                              (int)CW32System::_yPerInchScreenDC,
                              &v37,
                              0,
                              0);
  v17 = (HWND)*((_QWORD *)this + 2);
  *((_DWORD *)this + 52) = ECDefaultHeightAndWidth;
  ReleaseDC(v17, DC);
  *((_DWORD *)this + 59) = a2->hMenu;
  *((_DWORD *)this + 40) = 0;
  *((_DWORD *)this + 53) = 0;
  *((_DWORD *)this + 56) = -1;
  CCmbBxWinHost::CbCalcControlRects(this, &v38, 1);
  v18 = *((_DWORD *)this + 11);
  Y = *((_DWORD *)this + 45);
  X = *((_DWORD *)this + 44);
  v21 = (v18 >> 3) & 0x40 | 0x54808003;
  hWndParent = (HWND)*((_QWORD *)this + 2);
  if ( (v18 & 0x100) == 0 )
    v21 = (*((_DWORD *)this + 11) >> 3) & 0x40 | 0x54808001;
  v22 = v21 | 0x1000;
  if ( (v18 & 0x800) == 0 )
    v22 = v21;
  v23 = v22 | 0x100;
  if ( (v18 & 0x400) == 0 )
    v23 = v22;
  v24 = v23 | 0x10;
  if ( (v18 & 0x10) == 0 )
    v24 = v23;
  v25 = v18 & 0x8200000 | v24;
  v26 = *((_DWORD *)this + 12) & 0x7000 | 0x80;
  nHeight = *((_DWORD *)this + 47) - Y;
  nWidth = *((_DWORD *)this + 46) - X;
  v27 = CW32System::_dwPlatformId == 1
      ? CreateWindowExA(v26, "REListBox20W", 0, v25, X, Y, nWidth, nHeight, hWndParent, (HMENU)0x3E8, 0, this)
      : CreateWindowExW(v26, L"REListBox20W", 0, v25, X, Y, nWidth, nHeight, hWndParent, (HMENU)0x3E8, 0, this);
  *((_QWORD *)this + 16) = v27;
  WindowLongPtrW = GetWindowLongPtrW(v27, 0);
  *((_QWORD *)this + 31) = WindowLongPtrW;
  if ( !WindowLongPtrW )
    return -1;
  (*(void (__fastcall **)(LONG_PTR))(*(_QWORD *)WindowLongPtrW + 8LL))(WindowLongPtrW);
  if ( *((_DWORD *)this + 60) != 1 )
    ShowWindow(*((HWND *)this + 16), 0);
  SetParent(*((HWND *)this + 16), 0);
  v29 = *((_QWORD *)this + 4);
  v30 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v29 + 24LL);
  if ( *((_DWORD *)this + 60) == 3 )
  {
    ((void (__fastcall *)(__int64, __int64, __int64, __int64, _QWORD))v30)(v29, 1228, 4, 4, 0);
    memset_0(v39, 0, 0xBCu);
    v31 = *((_QWORD *)this + 4);
    v39[0] = 188;
    v39[1] = 1;
    v39[3] = (int)(1440.0 / (double)CW32System::_xPerInchScreenDC);
    (*(void (__fastcall **)(__int64, __int64, __int64, _DWORD *, _QWORD))(*(_QWORD *)v31 + 24LL))(v31, 1095, 4, v39, 0);
    v32 = *((_QWORD *)this + 4);
    *((_DWORD *)this + 20) = 0x80000;
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v32 + 24LL))(v32, 1228, 128);
  }
  else
  {
    v30(v29, 1228, 1);
  }
  if ( *((_DWORD *)this + 60) != 1 )
    CCmbBxWinHost::SetDropSize(this, (struct tagRECT *)this + 11);
  return 0;
}

```

## disassembly

```asm
0x18004f8e0  mov     [rsp-8+arg_10], rbx
0x18004f8e5  mov     [rsp-8+arg_18], rsi
0x18004f8ea  push    rbp
0x18004f8eb  push    rdi
0x18004f8ec  push    r12
0x18004f8ee  push    r14
0x18004f8f0  push    r15
0x18004f8f2  lea     rbp, [rsp-50h]
0x18004f8f7  sub     rsp, 150h
0x18004f8fe  mov     rax, cs:__security_cookie
0x18004f905  xor     rax, rsp
0x18004f908  mov     [rbp+70h+var_30], rax
0x18004f90c  xor     r15d, r15d
0x18004f90f  mov     rdi, rcx
0x18004f912  mov     ecx, [rdx+28h]
0x18004f915  mov     eax, r15d
0x18004f918  cmp     [rdx+20h], r15d
0x18004f91c  mov     rsi, rdx
0x18004f91f  mov     [rsp+170h+var_108.top], ecx
0x18004f923  cmovge  eax, [rdx+20h]
0x18004f927  add     eax, ecx
0x18004f929  mov     ecx, [rdx+2Ch]
0x18004f92c  cmp     [rdx+24h], r15d
0x18004f930  mov     [rsp+170h+var_108.bottom], eax
0x18004f934  mov     eax, r15d
0x18004f937  cmovge  eax, [rdx+24h]
0x18004f93b  lea     rdx, [rsp+170h+var_108]
0x18004f940  add     eax, ecx
0x18004f942  mov     [rsp+170h+var_108.left], ecx
0x18004f946  mov     rcx, [rdi+20h]
0x18004f94a  mov     [rsp+170h+var_108.right], eax
0x18004f94e  mov     rax, [rcx]
0x18004f951  mov     rax, [rax+48h]
0x18004f955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f95a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004f95e  test    eax, eax
0x18004f960  js      loc_18004FC1B
0x18004f966  mov     rcx, [rdi+10h]; hWnd
0x18004f96a  call    cs:__imp_GetDC
0x18004f971  nop     dword ptr [rax+rax+00h]
0x18004f976  mov     ecx, cs:?_yPerInchScreenDC@CW32System@@0JA; long CW32System::_yPerInchScreenDC
0x18004f97c  mov     rbx, rax
0x18004f97f  mov     qword ptr [rsp+170h+nHeight], r15; int *
0x18004f984  lea     rax, [rsp+170h+var_110]
0x18004f989  mov     qword ptr [rsp+170h+nWidth], r15; int *
0x18004f98e  mov     qword ptr [rsp+170h+Y], rax; int *
0x18004f993  mov     [rsp+170h+X], ecx; int
0x18004f997  mov     rcx, [rdi+20h]; this
0x18004f99b  call    ?GetECDefaultHeightAndWidth@@YAJPEAVITextServices@@PEAUHDC__@@JJJPEAJ22@Z; GetECDefaultHeightAndWidth(ITextServices *,HDC__ *,long,long,long,long *,long *,long *)
0x18004f9a0  mov     rcx, [rdi+10h]; hWnd
0x18004f9a4  mov     rdx, rbx; hDC
0x18004f9a7  mov     [rdi+0D0h], eax
0x18004f9ad  call    cs:__imp_ReleaseDC
0x18004f9b4  nop     dword ptr [rax+rax+00h]
0x18004f9b9  mov     eax, [rsi+10h]
0x18004f9bc  lea     r12d, [r15+1]
0x18004f9c0  mov     r8d, r12d; int
0x18004f9c3  mov     [rdi+0ECh], eax
0x18004f9c9  lea     rdx, [rsp+170h+var_108]; struct tagRECT *
0x18004f9ce  mov     [rdi+0A0h], r15d
0x18004f9d5  mov     rcx, rdi; this
0x18004f9d8  mov     [rdi+0D4h], r15d
0x18004f9df  mov     [rdi+0E0h], r14d
0x18004f9e6  call    ?CbCalcControlRects@CCmbBxWinHost@@QEAAHPEAUtagRECT@@H@Z; CCmbBxWinHost::CbCalcControlRects(tagRECT *,int)
0x18004f9eb  mov     r8d, [rdi+2Ch]
0x18004f9ef  lea     rsi, [rdi+0B0h]
0x18004f9f6  mov     r10d, [rsi+4]
0x18004f9fa  mov     edx, r8d
0x18004f9fd  mov     r11d, [rsi]
0x18004fa00  mov     r9d, 100h
0x18004fa06  mov     rbx, [rdi+10h]
0x18004fa0a  shr     edx, 3
0x18004fa0d  and     edx, 40h
0x18004fa10  mov     [rsp+170h+lpParam], rdi; lpParam
0x18004fa15  or      edx, 54808001h
0x18004fa1b  mov     [rsp+170h+hInstance], r15; hInstance
0x18004fa20  mov     ecx, edx
0x18004fa22  mov     [rsp+170h+hMenu], 3E8h; hMenu
0x18004fa2b  or      ecx, 2
0x18004fa2e  mov     [rsp+170h+hWndParent], rbx; hWndParent
0x18004fa33  test    r9d, r8d
0x18004fa36  cmovz   ecx, edx
0x18004fa39  mov     edx, ecx
0x18004fa3b  bts     edx, 0Ch
0x18004fa3f  bt      r8d, 0Bh
0x18004fa44  cmovnb  edx, ecx
0x18004fa47  mov     ecx, edx
0x18004fa49  or      ecx, r9d
0x18004fa4c  bt      r8d, 0Ah
0x18004fa51  cmovnb  ecx, edx
0x18004fa54  mov     edx, [rdi+0BCh]
0x18004fa5a  mov     r9d, ecx
0x18004fa5d  or      r9d, 10h
0x18004fa61  test    r8b, 10h
0x18004fa65  cmovz   r9d, ecx
0x18004fa69  mov     ecx, [rdi+30h]
0x18004fa6c  and     r8d, 8200000h
0x18004fa73  and     ecx, 7000h
0x18004fa79  or      r9d, r8d; dwStyle
0x18004fa7c  mov     r8d, [rdi+0B8h]
0x18004fa83  cmp     cs:?_dwPlatformId@CW32System@@0KA, r12d; ulong CW32System::_dwPlatformId
0x18004fa8a  setz    al
0x18004fa8d  sub     r8d, r11d
0x18004fa90  sub     edx, r10d
0x18004fa93  bts     ecx, 7; dwExStyle
0x18004fa97  mov     [rsp+170h+nHeight], edx; nHeight
0x18004fa9b  mov     [rsp+170h+nWidth], r8d; nWidth
0x18004faa0  xor     r8d, r8d; lpWindowName
0x18004faa3  mov     [rsp+170h+Y], r10d; Y
0x18004faa8  mov     [rsp+170h+X], r11d; X
0x18004faad  test    al, al
0x18004faaf  jnz     short loc_18004FAC6
0x18004fab1  lea     rdx, aRelistbox20w; "REListBox20W"
0x18004fab8  call    cs:__imp_CreateWindowExW
0x18004fabf  nop     dword ptr [rax+rax+00h]
0x18004fac4  jmp     short loc_18004FAD9
0x18004fac6  lea     rdx, aRelistbox20w_0; "REListBox20W"
0x18004facd  call    cs:__imp_CreateWindowExA
0x18004fad4  nop     dword ptr [rax+rax+00h]
0x18004fad9  xor     edx, edx; nIndex
0x18004fadb  mov     [rdi+80h], rax
0x18004fae2  mov     rcx, rax; hWnd
0x18004fae5  call    cs:__imp_GetWindowLongPtrW
0x18004faec  nop     dword ptr [rax+rax+00h]
0x18004faf1  mov     [rdi+0F8h], rax
0x18004faf8  mov     rdx, rax
0x18004fafb  test    rax, rax
0x18004fafe  jz      loc_18004FC1B
0x18004fb04  mov     rcx, [rax]
0x18004fb07  mov     rax, [rcx+8]
0x18004fb0b  mov     rcx, rdx
0x18004fb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb13  cmp     [rdi+0F0h], r12d
0x18004fb1a  jz      short loc_18004FB31
0x18004fb1c  mov     rcx, [rdi+80h]; hWnd
0x18004fb23  xor     edx, edx; nCmdShow
0x18004fb25  call    cs:__imp_ShowWindow
0x18004fb2c  nop     dword ptr [rax+rax+00h]
0x18004fb31  mov     rcx, [rdi+80h]; hWndChild
0x18004fb38  xor     edx, edx; hWndNewParent
0x18004fb3a  call    cs:__imp_SetParent
0x18004fb41  nop     dword ptr [rax+rax+00h]
0x18004fb46  cmp     dword ptr [rdi+0F0h], 3
0x18004fb4d  mov     edx, 4CCh
0x18004fb52  mov     rcx, [rdi+20h]
0x18004fb56  mov     qword ptr [rsp+170h+X], r15
0x18004fb5b  mov     rax, [rcx]
0x18004fb5e  mov     rax, [rax+18h]
0x18004fb62  jnz     loc_18004FBF8
0x18004fb68  mov     r14d, 4
0x18004fb6e  mov     r9d, r14d
0x18004fb71  mov     r8d, r14d
0x18004fb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fb79  mov     ebx, 0BCh
0x18004fb7e  lea     rcx, [rbp+70h+var_F0]; void *
0x18004fb82  mov     r8d, ebx; Size
0x18004fb85  xor     edx, edx; Val
0x18004fb87  call    memset_0
0x18004fb8c  movd    xmm0, cs:?_xPerInchScreenDC@CW32System@@0JA; long CW32System::_xPerInchScreenDC
0x18004fb94  lea     r9, [rbp+70h+var_F0]
0x18004fb98  movsd   xmm1, cs:__real@4096800000000000
0x18004fba0  mov     r8d, r14d
0x18004fba3  mov     rcx, [rdi+20h]
0x18004fba7  mov     edx, 447h
0x18004fbac  cvtdq2pd xmm0, xmm0
0x18004fbb0  mov     [rbp+70h+var_F0], ebx
0x18004fbb3  mov     [rbp+70h+var_EC], r12d
0x18004fbb7  mov     qword ptr [rsp+170h+X], r15
0x18004fbbc  divsd   xmm1, xmm0
0x18004fbc0  cvttsd2si eax, xmm1
0x18004fbc4  mov     [rbp+70h+var_E4], eax
0x18004fbc7  mov     rax, [rcx]
0x18004fbca  mov     rax, [rax+18h]
0x18004fbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fbd3  mov     rcx, [rdi+20h]
0x18004fbd7  lea     r9d, [r14+7Ch]
0x18004fbdb  mov     dword ptr [rdi+50h], 80000h
0x18004fbe2  mov     edx, 4CCh
0x18004fbe7  mov     qword ptr [rsp+170h+X], r15
0x18004fbec  mov     r8d, r9d
0x18004fbef  mov     rax, [rcx]
0x18004fbf2  mov     rax, [rax+18h]
0x18004fbf6  jmp     short loc_18004FBFE
0x18004fbf8  mov     r9, r12
0x18004fbfb  mov     r8, r12
0x18004fbfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc03  cmp     [rdi+0F0h], r12d
0x18004fc0a  jz      short loc_18004FC17
0x18004fc0c  mov     rdx, rsi; struct tagRECT *
0x18004fc0f  mov     rcx, rdi; this
0x18004fc12  call    ?SetDropSize@CCmbBxWinHost@@IEAAXPEAUtagRECT@@@Z; CCmbBxWinHost::SetDropSize(tagRECT *)
0x18004fc17  xor     eax, eax
0x18004fc19  jmp     short loc_18004FC1E
0x18004fc1b  mov     rax, r14
0x18004fc1e  mov     rcx, [rbp+70h+var_30]
0x18004fc22  xor     rcx, rsp; StackCookie
0x18004fc25  call    __security_check_cookie
0x18004fc2a  lea     r11, [rsp+170h+var_20]
0x18004fc32  mov     rbx, [r11+40h]
0x18004fc36  mov     rsi, [r11+48h]
0x18004fc3a  mov     rsp, r11
0x18004fc3d  pop     r15
0x18004fc3f  pop     r14
0x18004fc41  pop     r12
0x18004fc43  pop     rdi
0x18004fc44  pop     rbp
0x18004fc45  retn
```
