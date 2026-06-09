# CL21DispD3D::CreateFontCache(IDirect3DSurface9 * *,ulong,ulong,ulong,int,int)

- ea: `0x180129d84`
- end: `0x180129fcc`
- name: `?CreateFontCache@CL21DispD3D@@AEAA_NPEAPEAUIDirect3DSurface9@@KKKHH@Z`
- size: `584`
- prototype: `bool __usercall@<al>(CL21DispD3D *__hidden this@<rcx>, struct IDirect3DSurface9 **@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int mode, int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1801297d0`
- `0x18012b180`

## callees

- `0x18002d864`
- `0x180129c90`
- `0x180129d84`
- `0x18012a238`
- `0x18012a3e8`
- `0x18012bb88`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180129f99`
- `KERNEL32!LeaveCriticalSection` at `0x180129fac`
- `KERNEL32!LeaveCriticalSection` at `0x180129f99`
- `KERNEL32!LeaveCriticalSection` at `0x180129fac`
- `KERNEL32!EnterCriticalSection` at `0x180129da8`
- `KERNEL32!EnterCriticalSection` at `0x180129da8`
- `GDI32!DeleteObject` at `0x180129f7b`
- `GDI32!DeleteObject` at `0x180129f7b`
- `GDI32!SelectObject` at `0x180129e94`
- `GDI32!SelectObject` at `0x180129f53`
- `GDI32!SelectObject` at `0x180129e94`
- `GDI32!SelectObject` at `0x180129f53`
- `GDI32!ExtTextOutW` at `0x180129f39`
- `GDI32!ExtTextOutW` at `0x180129f39`
- `GDI32!SetBkColor` at `0x180129ed4`
- `GDI32!SetBkColor` at `0x180129ed4`
- `GDI32!SetTextCharacterExtra` at `0x180129e78`
- `GDI32!SetTextCharacterExtra` at `0x180129e78`
- `GDI32!SetBkMode` at `0x180129ee7`
- `GDI32!SetBkMode` at `0x180129ee7`
- `GDI32!SetTextColor` at `0x180129eaf`
- `GDI32!SetTextColor` at `0x180129eaf`

## pseudocode

```c
char __fastcall CL21DispD3D::CreateFontCache(
        CL21DispD3D *this,
        struct IDirect3DSurface9 **a2,
        unsigned int a3,
        __int64 a4,
        unsigned int mode,
        int a6,
        int a7)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  __int64 v8; // r15
  struct IDirect3DSurface9 **v11; // r14
  struct IDirect3DSurface9 *v12; // rcx
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
  v11 = (struct IDirect3DSurface9 **)((char *)this + 456);
  if ( !*((_QWORD *)this + 57) && !CL21DispD3D::CreateScratchFontCache(this, (struct IDirect3DSurface9 **)this + 57) )
    goto LABEL_14;
  RELEASE<IDDVideoAcceleratorContainer>(a2);
  if ( (int)CL21DispD3D::D3DARGBSurfaceInit(
              this,
              a2,
              0,
              1,
              40 * (*((_DWORD *)this + 98) + 4),
              3 * *((_DWORD *)this + 99)) < 0 )
    goto LABEL_14;
  v12 = *v11;
  hdc = 0;
  ((void (__fastcall *)(struct IDirect3DSurface9 *, HDC *))v12->lpVtbl->GetDC)(v12, &hdc);
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
    SetTextColor(hdc, *((_DWORD *)this + v8 + 86));
    if ( *((_DWORD *)this + 84) == 1448433985 )
      v18 = 0;
    else
      v18 = -16777216;
    SetBkColor(hdc, v18);
    SetBkMode(hdc, mode);
    for ( i = 0; i < 3; ++i )
      ExtTextOutW(hdc, 0, *((_DWORD *)this + 99) * i, 2u, 0, (LPCWSTR)this + 40 * i + 28, 0x28u, 0);
    v20 = SelectObject(hdc, v17);
    ((void (__fastcall *)(struct IDirect3DSurface9 *, HDC))(*v11)->lpVtbl->ReleaseDC)(*v11, hdc);
    DeleteObject(v20);
    CL21DispD3D::SetFontCacheAlpha(this, *v11, *a2);
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
0x180129d84  push    rbp
0x180129d86  push    rbx
0x180129d87  push    rsi
0x180129d88  push    rdi
0x180129d89  push    r12
0x180129d8b  push    r13
0x180129d8d  push    r14
0x180129d8f  push    r15
0x180129d91  mov     rbp, rsp
0x180129d94  sub     rsp, 48h
0x180129d98  lea     rbx, [rcx+10h]
0x180129d9c  mov     r15d, r8d
0x180129d9f  mov     rsi, rcx
0x180129da2  mov     r12, rdx
0x180129da5  mov     rcx, rbx; lpCriticalSection
0x180129da8  call    cs:__imp_EnterCriticalSection
0x180129daf  nop     dword ptr [rax+rax+00h]
0x180129db4  lea     r14, [rsi+1C8h]
0x180129dbb  cmp     qword ptr [r14], 0
0x180129dbf  jnz     short loc_180129DD4
0x180129dc1  mov     rdx, r14; struct IDirect3DSurface9 **
0x180129dc4  mov     rcx, rsi; this
0x180129dc7  call    ?CreateScratchFontCache@CL21DispD3D@@AEAA_NPEAPEAUIDirect3DSurface9@@@Z; CL21DispD3D::CreateScratchFontCache(IDirect3DSurface9 * *)
0x180129dcc  test    al, al
0x180129dce  jz      loc_180129FA9
0x180129dd4  mov     rcx, r12
0x180129dd7  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x180129ddc  mov     eax, [rsi+18Ch]
0x180129de2  mov     r9d, 1; int
0x180129de8  xor     r8d, r8d; int
0x180129deb  mov     rdx, r12; struct IDirect3DSurface9 **
0x180129dee  lea     ecx, [rax+rax*2]
0x180129df1  mov     eax, [rsi+188h]
0x180129df7  add     eax, 4
0x180129dfa  mov     dword ptr [rsp+48h+lpString], ecx; unsigned int
0x180129dfe  mov     rcx, rsi; this
0x180129e01  lea     eax, [rax+rax*4]
0x180129e04  shl     eax, 3
0x180129e07  mov     dword ptr [rsp+48h+lprect], eax; unsigned int
0x180129e0b  call    ?D3DARGBSurfaceInit@CL21DispD3D@@AEAAJPEAPEAUIDirect3DSurface9@@HHKK@Z; CL21DispD3D::D3DARGBSurfaceInit(IDirect3DSurface9 * *,int,int,ulong,ulong)
0x180129e10  test    eax, eax
0x180129e12  js      loc_180129FA9
0x180129e18  mov     rcx, [r14]
0x180129e1b  lea     rdx, [rbp+hdc]
0x180129e1f  mov     [rbp+hdc], 0
0x180129e27  mov     rax, [rcx]
0x180129e2a  mov     rax, [rax+78h]
0x180129e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129e33  mov     r9d, [rbp+arg_28]; int
0x180129e37  mov     rcx, rsi; this
0x180129e3a  mov     eax, [rbp+arg_30]
0x180129e3d  mov     r8d, [rsi+18Ch]; int
0x180129e44  mov     dword ptr [rsp+48h+lprect], eax; int
0x180129e48  test    r9d, r9d
0x180129e4b  jz      short loc_180129E62
0x180129e4d  mov     edx, [rsi+188h]
0x180129e53  sub     edx, 2; int
0x180129e56  call    ?CreateCCFont@CBaseL21Disp@@IEAAPEAUHFONT__@@HHHH@Z; CBaseL21Disp::CreateCCFont(int,int,int,int)
0x180129e5b  mov     edx, 6
0x180129e60  jmp     short loc_180129E71
0x180129e62  xor     r9d, r9d; int
0x180129e65  xor     edx, edx; int
0x180129e67  call    ?CreateCCFont@CBaseL21Disp@@IEAAPEAUHFONT__@@HHHH@Z; CBaseL21Disp::CreateCCFont(int,int,int,int)
0x180129e6c  mov     edx, 4; extra
0x180129e71  mov     rcx, [rbp+hdc]; hdc
0x180129e75  mov     rdi, rax
0x180129e78  call    cs:__imp_SetTextCharacterExtra
0x180129e7f  nop     dword ptr [rax+rax+00h]
0x180129e84  test    rdi, rdi
0x180129e87  jz      loc_180129FA9
0x180129e8d  mov     rcx, [rbp+hdc]; hdc
0x180129e91  mov     rdx, rdi; h
0x180129e94  call    cs:__imp_SelectObject
0x180129e9b  nop     dword ptr [rax+rax+00h]
0x180129ea0  mov     edx, [rsi+r15*4+158h]; color
0x180129ea8  mov     r13, rax
0x180129eab  mov     rcx, [rbp+hdc]; hdc
0x180129eaf  call    cs:__imp_SetTextColor
0x180129eb6  nop     dword ptr [rax+rax+00h]
0x180129ebb  cmp     dword ptr [rsi+150h], 56555941h
0x180129ec5  mov     rcx, [rbp+hdc]; hdc
0x180129ec9  jnz     short loc_180129ECF
0x180129ecb  xor     edx, edx
0x180129ecd  jmp     short loc_180129ED4
0x180129ecf  mov     edx, 0FF000000h; color
0x180129ed4  call    cs:__imp_SetBkColor
0x180129edb  nop     dword ptr [rax+rax+00h]
0x180129ee0  mov     edx, [rbp+mode]; mode
0x180129ee3  mov     rcx, [rbp+hdc]; hdc
0x180129ee7  call    cs:__imp_SetBkMode
0x180129eee  nop     dword ptr [rax+rax+00h]
0x180129ef3  xor     edi, edi
0x180129ef5  mov     [rsp+48h+lpDx], 0; lpDx
0x180129efe  lea     eax, [rdi+rdi*4]
0x180129f01  shl     eax, 3
0x180129f04  mov     r8d, edi
0x180129f07  imul    r8d, [rsi+18Ch]; y
0x180129f0f  xor     edx, edx; x
0x180129f11  cdqe
0x180129f13  add     rax, 1Ch
0x180129f17  mov     [rsp+48h+c], 28h ; '('; c
0x180129f1f  lea     r9d, [rdx+2]; options
0x180129f23  lea     rcx, [rsi+rax*2]
0x180129f27  mov     [rsp+48h+lpString], rcx; lpString
0x180129f2c  mov     rcx, [rbp+hdc]; hdc
0x180129f30  mov     [rsp+48h+lprect], 0; lprect
0x180129f39  call    cs:__imp_ExtTextOutW
0x180129f40  nop     dword ptr [rax+rax+00h]
0x180129f45  inc     edi
0x180129f47  cmp     edi, 3
0x180129f4a  jl      short loc_180129EF5
0x180129f4c  mov     rcx, [rbp+hdc]; hdc
0x180129f50  mov     rdx, r13; h
0x180129f53  call    cs:__imp_SelectObject
0x180129f5a  nop     dword ptr [rax+rax+00h]
0x180129f5f  mov     rcx, [r14]
0x180129f62  mov     rdi, rax
0x180129f65  mov     rdx, [rbp+hdc]
0x180129f69  mov     r8, [rcx]
0x180129f6c  mov     rax, [r8+80h]
0x180129f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180129f78  mov     rcx, rdi; ho
0x180129f7b  call    cs:__imp_DeleteObject
0x180129f82  nop     dword ptr [rax+rax+00h]
0x180129f87  mov     r8, [r12]; struct IDirect3DSurface9 *
0x180129f8b  mov     rcx, rsi; this
0x180129f8e  mov     rdx, [r14]; struct IDirect3DSurface9 *
0x180129f91  call    ?SetFontCacheAlpha@CL21DispD3D@@AEAAXPEAUIDirect3DSurface9@@0@Z; CL21DispD3D::SetFontCacheAlpha(IDirect3DSurface9 *,IDirect3DSurface9 *)
0x180129f96  mov     rcx, rbx; lpCriticalSection
0x180129f99  call    cs:__imp_LeaveCriticalSection
0x180129fa0  nop     dword ptr [rax+rax+00h]
0x180129fa5  mov     al, 1
0x180129fa7  jmp     short loc_180129FBA
0x180129fa9  mov     rcx, rbx; lpCriticalSection
0x180129fac  call    cs:__imp_LeaveCriticalSection
0x180129fb3  nop     dword ptr [rax+rax+00h]
0x180129fb8  xor     al, al
0x180129fba  add     rsp, 48h
0x180129fbe  pop     r15
0x180129fc0  pop     r14
0x180129fc2  pop     r13
0x180129fc4  pop     r12
0x180129fc6  pop     rdi
0x180129fc7  pop     rsi
0x180129fc8  pop     rbx
0x180129fc9  pop     rbp
0x180129fca  retn
```
