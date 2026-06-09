# CopyOnWriteBitmap::GetHdc(void)

- ea: `0x180040f74`
- end: `0x180041134`
- name: `?GetHdc@CopyOnWriteBitmap@@AEAAPEAUHDC__@@XZ`
- size: `448`
- prototype: `HDC __fastcall(CopyOnWriteBitmap *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180040f28`

## callees

- `0x180040f74`
- `0x180105d40`
- `0x18010673c`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180041064`
- `GDI32!CreateDIBSection` at `0x180041064`
- `GDI32!DeleteDC` at `0x1800410f5`
- `GDI32!DeleteDC` at `0x1800410f5`
- `GDI32!SelectObject` at `0x1800410af`
- `GDI32!SelectObject` at `0x1800410af`
- `GDI32!CreateCompatibleDC` at `0x180040ff3`
- `GDI32!CreateCompatibleDC` at `0x180040ff3`
- `GDI32!GetObjectA` at `0x180041093`
- `GDI32!GetObjectA` at `0x180041093`
- `GDI32!DeleteObject` at `0x180041110`
- `GDI32!DeleteObject` at `0x180041110`

## pseudocode

```c
HDC __fastcall CopyOnWriteBitmap::GetHdc(CopyOnWriteBitmap *this)
{
  _DWORD *v2; // rcx
  _DWORD *v3; // rdx
  int v4; // eax
  LONG v6; // r14d
  int v7; // r15d
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HBITMAP v10; // rdi
  __int64 v11; // rax
  _DWORD *v12; // rdi
  __int64 i; // rcx
  BITMAPINFO pbmi; // [rsp+30h] [rbp-89h] BYREF
  _BYTE pv[12]; // [rsp+60h] [rbp-59h] BYREF
  int v16; // [rsp+6Ch] [rbp-4Dh]
  int v17; // [rsp+80h] [rbp-39h]

  if ( !*((_QWORD *)this + 27) )
  {
    v6 = *((_DWORD *)this + 41);
    v7 = *((_DWORD *)this + 42);
    CompatibleDC = CreateCompatibleDC(0);
    v9 = CompatibleDC;
    if ( CompatibleDC )
    {
      pbmi.bmiHeader.biHeight = -v7;
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v6;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      v10 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)this + 29, 0, 0);
      memset_0(pv, 0, 0x68u);
      if ( v10 && GetObjectA(v10, 104, pv) && v17 && SelectObject(v9, v10) )
      {
        v11 = v16;
        v3 = (_DWORD *)((char *)this + 248);
        v2 = (_DWORD *)((char *)this + 252);
        *((_DWORD *)this + 62) = v6;
        *((_DWORD *)this + 63) = v7;
        *((_QWORD *)this + 30) = v11;
        *((_QWORD *)this + 27) = v9;
        *((_QWORD *)this + 28) = v10;
        goto LABEL_3;
      }
      DeleteDC(v9);
      if ( v10 )
        DeleteObject(v10);
    }
    return 0;
  }
  v2 = (_DWORD *)((char *)this + 252);
  v3 = (_DWORD *)((char *)this + 248);
LABEL_3:
  v4 = *v3 * *v2;
  if ( v4 )
  {
    v12 = (_DWORD *)*((_QWORD *)this + 29);
    for ( i = v4; i; --i )
      *v12++ = 854796;
  }
  return (HDC)*((_QWORD *)this + 27);
}

```

## disassembly

```asm
0x180040f74  push    rbp
0x180040f76  push    rbx
0x180040f77  push    rsi
0x180040f78  push    rdi
0x180040f79  push    r14
0x180040f7b  push    r15
0x180040f7d  lea     rbp, [rsp-2Fh]
0x180040f82  sub     rsp, 0E8h
0x180040f89  mov     rax, cs:__security_cookie
0x180040f90  xor     rax, rsp
0x180040f93  mov     [rbp+57h+var_40], rax
0x180040f97  cmp     qword ptr [rcx+0D8h], 0
0x180040f9f  mov     rbx, rcx
0x180040fa2  jz      short loc_180040FE3
0x180040fa4  add     rcx, 0FCh
0x180040fab  lea     rdx, [rbx+0F8h]
0x180040fb2  mov     eax, [rcx]
0x180040fb4  imul    eax, [rdx]
0x180040fb7  test    eax, eax
0x180040fb9  jnz     loc_18004111E
0x180040fbf  mov     rax, [rbx+0D8h]
0x180040fc6  mov     rcx, [rbp+57h+var_40]
0x180040fca  xor     rcx, rsp; StackCookie
0x180040fcd  call    __security_check_cookie
0x180040fd2  add     rsp, 0E8h
0x180040fd9  pop     r15
0x180040fdb  pop     r14
0x180040fdd  pop     rdi
0x180040fde  pop     rsi
0x180040fdf  pop     rbx
0x180040fe0  pop     rbp
0x180040fe1  retn
0x180040fe3  mov     r14d, [rcx+0A4h]
0x180040fea  mov     r15d, [rcx+0A8h]
0x180040ff1  xor     ecx, ecx; hdc
0x180040ff3  call    cs:__imp_CreateCompatibleDC
0x180040ffa  nop     dword ptr [rax+rax+00h]
0x180040fff  mov     rsi, rax
0x180041002  test    rax, rax
0x180041005  jz      loc_180041106
0x18004100b  mov     ecx, r15d
0x18004100e  mov     [rsp+110h+offset], 0; offset
0x180041016  neg     ecx
0x180041018  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], 0
0x180041020  mov     [rsp+110h+pbmi.bmiHeader.biHeight], ecx
0x180041024  lea     r9, [rbx+0E8h]; ppvBits
0x18004102b  mov     rcx, rax; hdc
0x18004102e  mov     [rsp+110h+pbmi.bmiHeader.biSize], 28h ; '('
0x180041036  xor     r8d, r8d; usage
0x180041039  mov     [rsp+110h+pbmi.bmiHeader.biWidth], r14d
0x18004103e  lea     rdx, [rsp+110h+pbmi]; pbmi
0x180041043  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18004104b  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], 0
0x180041053  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], 0
0x18004105b  mov     [rsp+110h+hSection], 0; hSection
0x180041064  call    cs:__imp_CreateDIBSection
0x18004106b  nop     dword ptr [rax+rax+00h]
0x180041070  xor     edx, edx; Val
0x180041072  lea     rcx, [rbp+57h+pv]; void *
0x180041076  mov     rdi, rax
0x180041079  lea     r8d, [rdx+68h]; Size
0x18004107d  call    memset_0
0x180041082  test    rdi, rdi
0x180041085  jz      short loc_1800410F2
0x180041087  lea     r8, [rbp+57h+pv]; pv
0x18004108b  mov     edx, 68h ; 'h'; c
0x180041090  mov     rcx, rdi; h
0x180041093  call    cs:__imp_GetObjectA
0x18004109a  nop     dword ptr [rax+rax+00h]
0x18004109f  test    eax, eax
0x1800410a1  jz      short loc_1800410F2
0x1800410a3  cmp     [rbp+57h+var_90], 0
0x1800410a7  jz      short loc_1800410F2
0x1800410a9  mov     rdx, rdi; h
0x1800410ac  mov     rcx, rsi; hdc
0x1800410af  call    cs:__imp_SelectObject
0x1800410b6  nop     dword ptr [rax+rax+00h]
0x1800410bb  test    rax, rax
0x1800410be  jz      short loc_1800410F2
0x1800410c0  movsxd  rax, [rbp+57h+var_A4]
0x1800410c4  lea     rdx, [rbx+0F8h]
0x1800410cb  lea     rcx, [rbx+0FCh]
0x1800410d2  mov     [rdx], r14d
0x1800410d5  mov     [rcx], r15d
0x1800410d8  mov     [rbx+0F0h], rax
0x1800410df  mov     [rbx+0D8h], rsi
0x1800410e6  mov     [rbx+0E0h], rdi
0x1800410ed  jmp     loc_180040FB2
0x1800410f2  mov     rcx, rsi; hdc
0x1800410f5  call    cs:__imp_DeleteDC
0x1800410fc  nop     dword ptr [rax+rax+00h]
0x180041101  test    rdi, rdi
0x180041104  jnz     short loc_18004110D
0x180041106  xor     eax, eax
0x180041108  jmp     loc_180040FC6
0x18004110d  mov     rcx, rdi; ho
0x180041110  call    cs:__imp_DeleteObject
0x180041117  nop     dword ptr [rax+rax+00h]
0x18004111c  jmp     short loc_180041106
0x18004111e  mov     rdi, [rbx+0E8h]
0x180041125  movsxd  rcx, eax
0x180041128  mov     eax, 0D0B0Ch
0x18004112d  rep stosd
0x18004112f  jmp     loc_180040FBF
```
