# CL21DispDDraw::CreateFontCache(IDirectDrawSurface7 * *,ulong,ulong,ulong,int,int)

- ea: `0x180129fd4`
- end: `0x18012a230`
- name: `?CreateFontCache@CL21DispDDraw@@AEAA_NPEAPEAUIDirectDrawSurface7@@KKKHH@Z`
- size: `604`
- prototype: `bool __usercall@<al>(CL21DispDDraw *__hidden this@<rcx>, struct IDirectDrawSurface7 **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int mode, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180129950`
- `0x18012b470`

## callees

- `0x18002d864`
- `0x180129c90`
- `0x180129fd4`
- `0x18012a30c`
- `0x18012a510`
- `0x18012bd50`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18012a1fd`
- `KERNEL32!LeaveCriticalSection` at `0x18012a210`
- `KERNEL32!LeaveCriticalSection` at `0x18012a1fd`
- `KERNEL32!LeaveCriticalSection` at `0x18012a210`
- `KERNEL32!EnterCriticalSection` at `0x180129ff8`
- `KERNEL32!EnterCriticalSection` at `0x180129ff8`
- `GDI32!DeleteObject` at `0x18012a1df`
- `GDI32!DeleteObject` at `0x18012a1df`
- `GDI32!SelectObject` at `0x18012a0e7`
- `GDI32!SelectObject` at `0x18012a1b7`
- `GDI32!SelectObject` at `0x18012a0e7`
- `GDI32!SelectObject` at `0x18012a1b7`
- `GDI32!ExtTextOutW` at `0x18012a19d`
- `GDI32!ExtTextOutW` at `0x18012a19d`
- `GDI32!SetBkColor` at `0x18012a138`
- `GDI32!SetBkColor` at `0x18012a138`
- `GDI32!SetTextCharacterExtra` at `0x18012a0cb`
- `GDI32!SetTextCharacterExtra` at `0x18012a0cb`
- `GDI32!SetBkMode` at `0x18012a14b`
- `GDI32!SetBkMode` at `0x18012a14b`
- `GDI32!SetTextColor` at `0x18012a10b`
- `GDI32!SetTextColor` at `0x18012a123`
- `GDI32!SetTextColor` at `0x18012a10b`
- `GDI32!SetTextColor` at `0x18012a123`

## pseudocode

```c
char __fastcall CL21DispDDraw::CreateFontCache(
        CL21DispDDraw *this,
        struct IDirectDrawSurface7 **a2,
        unsigned int a3,
        __int64 a4,
        unsigned int mode,
        int a6,
        int a7)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  __int64 v8; // r15
  struct IDirectDrawSurface7 **v11; // r14
  struct IDirectDrawSurface7 *v12; // rcx
  int v13; // r8d
  HFONT CCFont; // rax
  int v15; // edx
  HFONT v16; // rdi
  HGDIOBJ v17; // r13
  COLORREF v18; // edx
  int i; // edi
  HGDIOBJ v20; // rdi
  HDC hdc; // [rsp+90h] [rbp+48h] BYREF

  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v8 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v11 = (struct IDirectDrawSurface7 **)((char *)this + 456);
  if ( !*((_QWORD *)this + 57) && !CL21DispDDraw::CreateScratchFontCache(this, (struct IDirectDrawSurface7 **)this + 57) )
    goto LABEL_14;
  RELEASE<IDDVideoAcceleratorContainer>(a2);
  if ( (int)CL21DispDDraw::DDrawARGBSurfaceInit(
              this,
              a2,
              0,
              1,
              40 * (*((_DWORD *)this + 98) + 4),
              3 * *((_DWORD *)this + 99)) < 0 )
    goto LABEL_14;
  v12 = *v11;
  hdc = 0;
  ((void (__fastcall *)(struct IDirectDrawSurface7 *, HDC *))v12->lpVtbl->GetDC)(v12, &hdc);
  v13 = *((_DWORD *)this + 99);
  if ( a6 )
  {
    CCFont = CBaseL21Disp::CreateCCFont(this, *((_DWORD *)this + 98) - 2, v13, a6, a7);
    v15 = 6;
  }
  else
  {
    CCFont = CBaseL21Disp::CreateCCFont(this, 0, v13, 0, a7);
    v15 = 4;
  }
  v16 = CCFont;
  SetTextCharacterExtra(hdc, v15);
  if ( v16 )
  {
    v17 = SelectObject(hdc, v16);
    if ( *((_DWORD *)this + 84) == 1448433985 )
    {
      SetTextColor(hdc, 0xFFFFFFu);
      v18 = 0;
    }
    else
    {
      SetTextColor(hdc, *((_DWORD *)this + v8 + 86));
      v18 = -16777216;
    }
    SetBkColor(hdc, v18);
    SetBkMode(hdc, mode);
    for ( i = 0; i < 3; ++i )
      ExtTextOutW(hdc, 0, *((_DWORD *)this + 99) * i, 2u, 0, (LPCWSTR)this + 40 * i + 28, 0x28u, 0);
    v20 = SelectObject(hdc, v17);
    ((void (__fastcall *)(struct IDirectDrawSurface7 *, HDC))(*v11)->lpVtbl->ReleaseDC)(*v11, hdc);
    DeleteObject(v20);
    CL21DispDDraw::SetFontCacheAlpha(this, *v11, *a2);
    LeaveCriticalSection(v7);
    return 1;
  }
  else
  {
LABEL_14:
    LeaveCriticalSection(v7);
    return 0;
  }
}

```

## disassembly

```asm
0x180129fd4  push    rbp
0x180129fd6  push    rbx
0x180129fd7  push    rsi
0x180129fd8  push    rdi
0x180129fd9  push    r12
0x180129fdb  push    r13
0x180129fdd  push    r14
0x180129fdf  push    r15
0x180129fe1  mov     rbp, rsp
0x180129fe4  sub     rsp, 48h
0x180129fe8  lea     rbx, [rcx+10h]
0x180129fec  mov     r15d, r8d
0x180129fef  mov     rsi, rcx
0x180129ff2  mov     r12, rdx
0x180129ff5  mov     rcx, rbx; lpCriticalSection
0x180129ff8  call    cs:__imp_EnterCriticalSection
0x180129fff  nop     dword ptr [rax+rax+00h]
0x18012a004  lea     r14, [rsi+1C8h]
0x18012a00b  cmp     qword ptr [r14], 0
0x18012a00f  jnz     short loc_18012A024
0x18012a011  mov     rdx, r14; struct IDirectDrawSurface7 **
0x18012a014  mov     rcx, rsi; this
0x18012a017  call    ?CreateScratchFontCache@CL21DispDDraw@@AEAA_NPEAPEAUIDirectDrawSurface7@@@Z; CL21DispDDraw::CreateScratchFontCache(IDirectDrawSurface7 * *)
0x18012a01c  test    al, al
0x18012a01e  jz      loc_18012A20D
0x18012a024  mov     rcx, r12
0x18012a027  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x18012a02c  mov     eax, [rsi+18Ch]
0x18012a032  mov     r9d, 1; int
0x18012a038  xor     r8d, r8d; int
0x18012a03b  mov     rdx, r12; struct IDirectDrawSurface7 **
0x18012a03e  lea     ecx, [rax+rax*2]
0x18012a041  mov     eax, [rsi+188h]
0x18012a047  add     eax, 4
0x18012a04a  mov     dword ptr [rsp+48h+lpString], ecx; unsigned int
0x18012a04e  mov     rcx, rsi; this
0x18012a051  lea     eax, [rax+rax*4]
0x18012a054  shl     eax, 3
0x18012a057  mov     dword ptr [rsp+48h+lprect], eax; unsigned int
0x18012a05b  call    ?DDrawARGBSurfaceInit@CL21DispDDraw@@AEAAJPEAPEAUIDirectDrawSurface7@@HHKK@Z; CL21DispDDraw::DDrawARGBSurfaceInit(IDirectDrawSurface7 * *,int,int,ulong,ulong)
0x18012a060  test    eax, eax
0x18012a062  js      loc_18012A20D
0x18012a068  mov     rcx, [r14]
0x18012a06b  lea     rdx, [rbp+hdc]
0x18012a06f  mov     [rbp+hdc], 0
0x18012a077  mov     rax, [rcx]
0x18012a07a  mov     rax, [rax+88h]
0x18012a081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a086  mov     r9d, [rbp+arg_28]; int
0x18012a08a  mov     rcx, rsi; this
0x18012a08d  mov     eax, [rbp+arg_30]
0x18012a090  mov     r8d, [rsi+18Ch]; int
0x18012a097  mov     dword ptr [rsp+48h+lprect], eax; int
0x18012a09b  test    r9d, r9d
0x18012a09e  jz      short loc_18012A0B5
0x18012a0a0  mov     edx, [rsi+188h]
0x18012a0a6  sub     edx, 2; int
0x18012a0a9  call    ?CreateCCFont@CBaseL21Disp@@IEAAPEAUHFONT__@@HHHH@Z; CBaseL21Disp::CreateCCFont(int,int,int,int)
0x18012a0ae  mov     edx, 6
0x18012a0b3  jmp     short loc_18012A0C4
0x18012a0b5  xor     r9d, r9d; int
0x18012a0b8  xor     edx, edx; int
0x18012a0ba  call    ?CreateCCFont@CBaseL21Disp@@IEAAPEAUHFONT__@@HHHH@Z; CBaseL21Disp::CreateCCFont(int,int,int,int)
0x18012a0bf  mov     edx, 4; extra
0x18012a0c4  mov     rcx, [rbp+hdc]; hdc
0x18012a0c8  mov     rdi, rax
0x18012a0cb  call    cs:__imp_SetTextCharacterExtra
0x18012a0d2  nop     dword ptr [rax+rax+00h]
0x18012a0d7  test    rdi, rdi
0x18012a0da  jz      loc_18012A20D
0x18012a0e0  mov     rcx, [rbp+hdc]; hdc
0x18012a0e4  mov     rdx, rdi; h
0x18012a0e7  call    cs:__imp_SelectObject
0x18012a0ee  nop     dword ptr [rax+rax+00h]
0x18012a0f3  cmp     dword ptr [rsi+150h], 56555941h
0x18012a0fd  mov     r13, rax
0x18012a100  mov     rcx, [rbp+hdc]; hdc
0x18012a104  jnz     short loc_18012A11B
0x18012a106  mov     edx, 0FFFFFFh; color
0x18012a10b  call    cs:__imp_SetTextColor
0x18012a112  nop     dword ptr [rax+rax+00h]
0x18012a117  xor     edx, edx
0x18012a119  jmp     short loc_18012A134
0x18012a11b  mov     edx, [rsi+r15*4+158h]; color
0x18012a123  call    cs:__imp_SetTextColor
0x18012a12a  nop     dword ptr [rax+rax+00h]
0x18012a12f  mov     edx, 0FF000000h; color
0x18012a134  mov     rcx, [rbp+hdc]; hdc
0x18012a138  call    cs:__imp_SetBkColor
0x18012a13f  nop     dword ptr [rax+rax+00h]
0x18012a144  mov     edx, [rbp+mode]; mode
0x18012a147  mov     rcx, [rbp+hdc]; hdc
0x18012a14b  call    cs:__imp_SetBkMode
0x18012a152  nop     dword ptr [rax+rax+00h]
0x18012a157  xor     edi, edi
0x18012a159  mov     [rsp+48h+lpDx], 0; lpDx
0x18012a162  lea     eax, [rdi+rdi*4]
0x18012a165  shl     eax, 3
0x18012a168  mov     r8d, edi
0x18012a16b  imul    r8d, [rsi+18Ch]; y
0x18012a173  xor     edx, edx; x
0x18012a175  cdqe
0x18012a177  add     rax, 1Ch
0x18012a17b  mov     [rsp+48h+c], 28h ; '('; c
0x18012a183  lea     r9d, [rdx+2]; options
0x18012a187  lea     rcx, [rsi+rax*2]
0x18012a18b  mov     [rsp+48h+lpString], rcx; lpString
0x18012a190  mov     rcx, [rbp+hdc]; hdc
0x18012a194  mov     [rsp+48h+lprect], 0; lprect
0x18012a19d  call    cs:__imp_ExtTextOutW
0x18012a1a4  nop     dword ptr [rax+rax+00h]
0x18012a1a9  inc     edi
0x18012a1ab  cmp     edi, 3
0x18012a1ae  jl      short loc_18012A159
0x18012a1b0  mov     rcx, [rbp+hdc]; hdc
0x18012a1b4  mov     rdx, r13; h
0x18012a1b7  call    cs:__imp_SelectObject
0x18012a1be  nop     dword ptr [rax+rax+00h]
0x18012a1c3  mov     rcx, [r14]
0x18012a1c6  mov     rdi, rax
0x18012a1c9  mov     rdx, [rbp+hdc]
0x18012a1cd  mov     r8, [rcx]
0x18012a1d0  mov     rax, [r8+0D0h]
0x18012a1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a1dc  mov     rcx, rdi; ho
0x18012a1df  call    cs:__imp_DeleteObject
0x18012a1e6  nop     dword ptr [rax+rax+00h]
0x18012a1eb  mov     r8, [r12]; struct IDirectDrawSurface7 *
0x18012a1ef  mov     rcx, rsi; this
0x18012a1f2  mov     rdx, [r14]; struct IDirectDrawSurface7 *
0x18012a1f5  call    ?SetFontCacheAlpha@CL21DispDDraw@@AEAAXPEAUIDirectDrawSurface7@@0@Z; CL21DispDDraw::SetFontCacheAlpha(IDirectDrawSurface7 *,IDirectDrawSurface7 *)
0x18012a1fa  mov     rcx, rbx; lpCriticalSection
0x18012a1fd  call    cs:__imp_LeaveCriticalSection
0x18012a204  nop     dword ptr [rax+rax+00h]
0x18012a209  mov     al, 1
0x18012a20b  jmp     short loc_18012A21E
0x18012a20d  mov     rcx, rbx; lpCriticalSection
0x18012a210  call    cs:__imp_LeaveCriticalSection
0x18012a217  nop     dword ptr [rax+rax+00h]
0x18012a21c  xor     al, al
0x18012a21e  add     rsp, 48h
0x18012a222  pop     r15
0x18012a224  pop     r14
0x18012a226  pop     r13
0x18012a228  pop     r12
0x18012a22a  pop     rdi
0x18012a22b  pop     rsi
0x18012a22c  pop     rbx
0x18012a22d  pop     rbp
0x18012a22e  retn
```
