# CCmbBxWinHost::OnCreate(tagCREATESTRUCTW const *)

- ea: `0x18004e640`
- end: `0x18004e97c`
- name: `?OnCreate@CCmbBxWinHost@@UEAA_JPEBUtagCREATESTRUCTW@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(CCmbBxWinHost *__hidden this, const struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18004d3b0`
- `0x18004e640`
- `0x1800503fc`
- `0x18005ba50`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x18004e82d`
- `USER32!GetWindowLongPtrW` at `0x18004e82d`
- `USER32!SetParent` at `0x18004e876`
- `USER32!SetParent` at `0x18004e876`
- `USER32!ShowWindow` at `0x18004e867`
- `USER32!ShowWindow` at `0x18004e867`
- `USER32!CreateWindowExA` at `0x18004e81b`
- `USER32!CreateWindowExA` at `0x18004e81b`
- `USER32!CreateWindowExW` at `0x18004e80c`
- `USER32!CreateWindowExW` at `0x18004e80c`
- `USER32!ReleaseDC` at `0x18004e707`
- `USER32!ReleaseDC` at `0x18004e707`
- `USER32!GetDC` at `0x18004e6ca`
- `USER32!GetDC` at `0x18004e6ca`

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
0x18004e640  mov     [rsp-8+arg_10], rbx
0x18004e645  mov     [rsp-8+arg_18], rsi
0x18004e64a  push    rbp
0x18004e64b  push    rdi
0x18004e64c  push    r12
0x18004e64e  push    r14
0x18004e650  push    r15
0x18004e652  lea     rbp, [rsp-50h]
0x18004e657  sub     rsp, 150h
0x18004e65e  mov     rax, cs:__security_cookie
0x18004e665  xor     rax, rsp
0x18004e668  mov     [rbp+70h+var_30], rax
0x18004e66c  xor     r15d, r15d
0x18004e66f  mov     rdi, rcx
0x18004e672  mov     ecx, [rdx+28h]
0x18004e675  mov     eax, r15d
0x18004e678  cmp     [rdx+20h], r15d
0x18004e67c  mov     rsi, rdx
0x18004e67f  mov     [rsp+170h+var_108.top], ecx
0x18004e683  cmovge  eax, [rdx+20h]
0x18004e687  add     eax, ecx
0x18004e689  mov     ecx, [rdx+2Ch]
0x18004e68c  cmp     [rdx+24h], r15d
0x18004e690  mov     [rsp+170h+var_108.bottom], eax
0x18004e694  mov     eax, r15d
0x18004e697  cmovge  eax, [rdx+24h]
0x18004e69b  lea     rdx, [rsp+170h+var_108]
0x18004e6a0  add     eax, ecx
0x18004e6a2  mov     [rsp+170h+var_108.left], ecx
0x18004e6a6  mov     rcx, [rdi+20h]
0x18004e6aa  mov     [rsp+170h+var_108.right], eax
0x18004e6ae  mov     rax, [rcx]
0x18004e6b1  mov     rax, [rax+48h]
0x18004e6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e6ba  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004e6be  test    eax, eax
0x18004e6c0  js      loc_18004E951
0x18004e6c6  mov     rcx, [rdi+10h]; hWnd
0x18004e6ca  call    cs:__imp_GetDC
0x18004e6d0  mov     ecx, cs:?_yPerInchScreenDC@CW32System@@0JA; long CW32System::_yPerInchScreenDC
0x18004e6d6  mov     rbx, rax
0x18004e6d9  mov     qword ptr [rsp+170h+nHeight], r15; int *
0x18004e6de  lea     rax, [rsp+170h+var_110]
0x18004e6e3  mov     qword ptr [rsp+170h+nWidth], r15; int *
0x18004e6e8  mov     qword ptr [rsp+170h+Y], rax; int *
0x18004e6ed  mov     [rsp+170h+X], ecx; int
0x18004e6f1  mov     rcx, [rdi+20h]; this
0x18004e6f5  call    ?GetECDefaultHeightAndWidth@@YAJPEAVITextServices@@PEAUHDC__@@JJJPEAJ22@Z; GetECDefaultHeightAndWidth(ITextServices *,HDC__ *,long,long,long,long *,long *,long *)
0x18004e6fa  mov     rcx, [rdi+10h]; hWnd
0x18004e6fe  mov     rdx, rbx; hDC
0x18004e701  mov     [rdi+0D0h], eax
0x18004e707  call    cs:__imp_ReleaseDC
0x18004e70d  mov     eax, [rsi+10h]
0x18004e710  lea     r12d, [r15+1]
0x18004e714  mov     r8d, r12d; int
0x18004e717  mov     [rdi+0ECh], eax
0x18004e71d  lea     rdx, [rsp+170h+var_108]; struct tagRECT *
0x18004e722  mov     [rdi+0A0h], r15d
0x18004e729  mov     rcx, rdi; this
0x18004e72c  mov     [rdi+0D4h], r15d
0x18004e733  mov     [rdi+0E0h], r14d
0x18004e73a  call    ?CbCalcControlRects@CCmbBxWinHost@@QEAAHPEAUtagRECT@@H@Z; CCmbBxWinHost::CbCalcControlRects(tagRECT *,int)
0x18004e73f  mov     r8d, [rdi+2Ch]
0x18004e743  lea     rsi, [rdi+0B0h]
0x18004e74a  mov     r10d, [rsi+4]
0x18004e74e  mov     edx, r8d
0x18004e751  mov     r11d, [rsi]
0x18004e754  mov     r9d, 100h
0x18004e75a  mov     rbx, [rdi+10h]
0x18004e75e  shr     edx, 3
0x18004e761  and     edx, 40h
0x18004e764  mov     [rsp+170h+lpParam], rdi; lpParam
0x18004e769  or      edx, 54808001h
0x18004e76f  mov     [rsp+170h+hInstance], r15; hInstance
0x18004e774  mov     ecx, edx
0x18004e776  mov     [rsp+170h+hMenu], 3E8h; hMenu
0x18004e77f  or      ecx, 2
0x18004e782  mov     [rsp+170h+hWndParent], rbx; hWndParent
0x18004e787  test    r9d, r8d
0x18004e78a  cmovz   ecx, edx
0x18004e78d  mov     edx, ecx
0x18004e78f  bts     edx, 0Ch
0x18004e793  bt      r8d, 0Bh
0x18004e798  cmovnb  edx, ecx
0x18004e79b  mov     ecx, edx
0x18004e79d  or      ecx, r9d
0x18004e7a0  bt      r8d, 0Ah
0x18004e7a5  cmovnb  ecx, edx
0x18004e7a8  mov     edx, [rdi+0BCh]
0x18004e7ae  mov     r9d, ecx
0x18004e7b1  or      r9d, 10h
0x18004e7b5  test    r8b, 10h
0x18004e7b9  cmovz   r9d, ecx
0x18004e7bd  mov     ecx, [rdi+30h]
0x18004e7c0  and     r8d, 8200000h
0x18004e7c7  and     ecx, 7000h
0x18004e7cd  or      r9d, r8d; dwStyle
0x18004e7d0  mov     r8d, [rdi+0B8h]
0x18004e7d7  cmp     cs:?_dwPlatformId@CW32System@@0KA, r12d; ulong CW32System::_dwPlatformId
0x18004e7de  setz    al
0x18004e7e1  sub     r8d, r11d
0x18004e7e4  sub     edx, r10d
0x18004e7e7  bts     ecx, 7; dwExStyle
0x18004e7eb  mov     [rsp+170h+nHeight], edx; nHeight
0x18004e7ef  mov     [rsp+170h+nWidth], r8d; nWidth
0x18004e7f4  xor     r8d, r8d; lpWindowName
0x18004e7f7  mov     [rsp+170h+Y], r10d; Y
0x18004e7fc  mov     [rsp+170h+X], r11d; X
0x18004e801  test    al, al
0x18004e803  jnz     short loc_18004E814
0x18004e805  lea     rdx, aRelistbox20w; "REListBox20W"
0x18004e80c  call    cs:__imp_CreateWindowExW
0x18004e812  jmp     short loc_18004E821
0x18004e814  lea     rdx, aRelistbox20w_0; "REListBox20W"
0x18004e81b  call    cs:__imp_CreateWindowExA
0x18004e821  xor     edx, edx; nIndex
0x18004e823  mov     [rdi+80h], rax
0x18004e82a  mov     rcx, rax; hWnd
0x18004e82d  call    cs:__imp_GetWindowLongPtrW
0x18004e833  mov     [rdi+0F8h], rax
0x18004e83a  mov     rdx, rax
0x18004e83d  test    rax, rax
0x18004e840  jz      loc_18004E951
0x18004e846  mov     rcx, [rax]
0x18004e849  mov     rax, [rcx+8]
0x18004e84d  mov     rcx, rdx
0x18004e850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e855  cmp     [rdi+0F0h], r12d
0x18004e85c  jz      short loc_18004E86D
0x18004e85e  mov     rcx, [rdi+80h]; hWnd
0x18004e865  xor     edx, edx; nCmdShow
0x18004e867  call    cs:__imp_ShowWindow
0x18004e86d  mov     rcx, [rdi+80h]; hWndChild
0x18004e874  xor     edx, edx; hWndNewParent
0x18004e876  call    cs:__imp_SetParent
0x18004e87c  cmp     dword ptr [rdi+0F0h], 3
0x18004e883  mov     edx, 4CCh
0x18004e888  mov     rcx, [rdi+20h]
0x18004e88c  mov     qword ptr [rsp+170h+X], r15
0x18004e891  mov     rax, [rcx]
0x18004e894  mov     rax, [rax+18h]
0x18004e898  jnz     loc_18004E92E
0x18004e89e  mov     r14d, 4
0x18004e8a4  mov     r9d, r14d
0x18004e8a7  mov     r8d, r14d
0x18004e8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8af  mov     ebx, 0BCh
0x18004e8b4  lea     rcx, [rbp+70h+var_F0]; void *
0x18004e8b8  mov     r8d, ebx; Size
0x18004e8bb  xor     edx, edx; Val
0x18004e8bd  call    memset_0
0x18004e8c2  movd    xmm0, cs:?_xPerInchScreenDC@CW32System@@0JA; long CW32System::_xPerInchScreenDC
0x18004e8ca  lea     r9, [rbp+70h+var_F0]
0x18004e8ce  movsd   xmm1, cs:__real@4096800000000000
0x18004e8d6  mov     r8d, r14d
0x18004e8d9  mov     rcx, [rdi+20h]
0x18004e8dd  mov     edx, 447h
0x18004e8e2  cvtdq2pd xmm0, xmm0
0x18004e8e6  mov     [rbp+70h+var_F0], ebx
0x18004e8e9  mov     [rbp+70h+var_EC], r12d
0x18004e8ed  mov     qword ptr [rsp+170h+X], r15
0x18004e8f2  divsd   xmm1, xmm0
0x18004e8f6  cvttsd2si eax, xmm1
0x18004e8fa  mov     [rbp+70h+var_E4], eax
0x18004e8fd  mov     rax, [rcx]
0x18004e900  mov     rax, [rax+18h]
0x18004e904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e909  mov     rcx, [rdi+20h]
0x18004e90d  lea     r9d, [r14+7Ch]
0x18004e911  mov     dword ptr [rdi+50h], 80000h
0x18004e918  mov     edx, 4CCh
0x18004e91d  mov     qword ptr [rsp+170h+X], r15
0x18004e922  mov     r8d, r9d
0x18004e925  mov     rax, [rcx]
0x18004e928  mov     rax, [rax+18h]
0x18004e92c  jmp     short loc_18004E934
0x18004e92e  mov     r9, r12
0x18004e931  mov     r8, r12
0x18004e934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e939  cmp     [rdi+0F0h], r12d
0x18004e940  jz      short loc_18004E94D
0x18004e942  mov     rdx, rsi; struct tagRECT *
0x18004e945  mov     rcx, rdi; this
0x18004e948  call    ?SetDropSize@CCmbBxWinHost@@IEAAXPEAUtagRECT@@@Z; CCmbBxWinHost::SetDropSize(tagRECT *)
0x18004e94d  xor     eax, eax
0x18004e94f  jmp     short loc_18004E954
0x18004e951  mov     rax, r14
0x18004e954  mov     rcx, [rbp+70h+var_30]
0x18004e958  xor     rcx, rsp; StackCookie
0x18004e95b  call    __security_check_cookie
0x18004e960  lea     r11, [rsp+170h+var_20]
0x18004e968  mov     rbx, [r11+40h]
0x18004e96c  mov     rsi, [r11+48h]
0x18004e970  mov     rsp, r11
0x18004e973  pop     r15
0x18004e975  pop     r14
0x18004e977  pop     r12
0x18004e979  pop     rdi
0x18004e97a  pop     rbp
0x18004e97b  retn
```
