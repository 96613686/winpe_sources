# DoMaskBltNoSrc

- ea: `0x1801495cc`
- end: `0x1801497e6`
- name: `DoMaskBltNoSrc`
- size: `538`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, __int64, int, int, UINT ColorUse, BITMAPINFO *lpbmi, int, void *lpBits)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800ff3c0`

## callees

- `0x1800c790c`
- `0x180105d40`
- `0x180146ce0`
- `0x1801495cc`
- `0x180149e00`

## import_xrefs

- `GDI32!DeleteDC` at `0x1801497b7`
- `GDI32!DeleteDC` at `0x1801497b7`
- `GDI32!SelectObject` at `0x180149660`
- `GDI32!SelectObject` at `0x180149799`
- `GDI32!SelectObject` at `0x180149660`
- `GDI32!SelectObject` at `0x180149799`
- `GDI32!CreateCompatibleDC` at `0x180149628`
- `GDI32!CreateCompatibleDC` at `0x180149628`
- `GDI32!DeleteObject` at `0x1801497a8`
- `GDI32!DeleteObject` at `0x1801497a8`

## pseudocode

```c
_BOOL8 __fastcall DoMaskBltNoSrc(
        int a1,
        int a2,
        int a3,
        int a4,
        int hDest,
        int a6,
        __int64 a7,
        int a8,
        int a9,
        UINT ColorUse,
        BITMAPINFO *lpbmi,
        int a12,
        void *lpBits)
{
  BOOL v13; // edi
  HDC hdc; // rbx
  HBITMAP MonoDib; // rax
  HBITMAP hbm; // r14
  HGDIOBJ v18; // r13
  int v19; // edi
  int v20; // esi
  int v21; // r12d
  int v22; // r15d
  __int64 v28; // [rsp+90h] [rbp-21h] BYREF
  int v29; // [rsp+98h] [rbp-19h]
  int v30; // [rsp+9Ch] [rbp-15h]

  v13 = 0;
  hdc = CreateCompatibleDC(0);
  if ( hdc )
  {
    MonoDib = (HBITMAP)CreateMonoDib(lpbmi, lpBits, ColorUse);
    hbm = MonoDib;
    if ( MonoDib )
    {
      v18 = SelectObject(hdc, MonoDib);
      if ( v18 )
      {
        v30 = hDest;
        v28 = 0;
        v29 = a4;
        if ( (unsigned int)bXformWorkhorse(&v28, 2, a7) )
        {
          v19 = v30 - HIDWORD(v28);
          v20 = v29 - v28;
          v21 = a8;
          if ( v29 - (int)v28 < 0 )
            v21 = 1 - v20 + a8;
          v22 = a9;
          if ( v19 < 0 )
            v22 = 1 - v19 + a9;
          if ( (unsigned int)DoStretchBltAlt(
                               a1,
                               a2,
                               a3,
                               a4,
                               hDest,
                               a6 & 0xCC0000 | 0x220000u,
                               v21,
                               v22,
                               v29 - (int)v28,
                               v30 - HIDWORD(v28),
                               hdc,
                               hbm,
                               (__int64)&xformIdentity) )
            v13 = DoStretchBltAlt(
                    a1,
                    a2,
                    a3,
                    a4,
                    hDest,
                    (a6 & 0x33000000 | 0x880000FF) >> 8,
                    v21,
                    v22,
                    v20,
                    v19,
                    hdc,
                    hbm,
                    (__int64)&xformIdentity) != 0;
          else
            v13 = 0;
        }
        SelectObject(hdc, v18);
      }
      DeleteObject(hbm);
    }
    DeleteDC(hdc);
  }
  return v13;
}

```

## disassembly

```asm
0x1801495cc  push    rbp
0x1801495ce  push    rbx
0x1801495cf  push    rsi
0x1801495d0  push    rdi
0x1801495d1  push    r12
0x1801495d3  push    r13
0x1801495d5  push    r14
0x1801495d7  push    r15
0x1801495d9  lea     rbp, [rsp-7]
0x1801495de  sub     rsp, 0B8h
0x1801495e5  mov     rax, cs:__security_cookie
0x1801495ec  xor     rax, rsp
0x1801495ef  mov     [rbp+3Fh+var_50], rax
0x1801495f3  mov     rax, [rbp+3Fh+arg_30]
0x1801495f7  xor     edi, edi
0x1801495f9  mov     esi, [rbp+3Fh+ColorUse]
0x1801495ff  mov     r12d, r9d
0x180149602  mov     r14, [rbp+3Fh+lpbmi]
0x180149609  mov     r15, [rbp+3Fh+lpBits]
0x180149610  mov     qword ptr [rbp+3Fh+var_70], rcx
0x180149614  xor     ecx, ecx; hdc
0x180149616  mov     [rbp+3Fh+var_68], rax
0x18014961a  mov     [rbp+3Fh+var_74], edi
0x18014961d  mov     [rbp+3Fh+var_80], r9d
0x180149621  mov     [rbp+3Fh+var_7C], r8d
0x180149625  mov     [rbp+3Fh+var_78], edx
0x180149628  call    cs:__imp_CreateCompatibleDC
0x18014962f  nop     dword ptr [rax+rax+00h]
0x180149634  mov     rbx, rax
0x180149637  test    rax, rax
0x18014963a  jz      loc_1801497C3
0x180149640  mov     r8d, esi; ColorUse
0x180149643  mov     rdx, r15; lpBits
0x180149646  mov     rcx, r14; lpbmi
0x180149649  call    CreateMonoDib
0x18014964e  mov     r14, rax
0x180149651  test    rax, rax
0x180149654  jz      loc_1801497B4
0x18014965a  mov     rdx, rax; h
0x18014965d  mov     rcx, rbx; hdc
0x180149660  call    cs:__imp_SelectObject
0x180149667  nop     dword ptr [rax+rax+00h]
0x18014966c  mov     r13, rax
0x18014966f  test    rax, rax
0x180149672  jz      loc_1801497A5
0x180149678  mov     eax, [rbp+3Fh+arg_20]
0x18014967b  lea     edx, [rdi+2]
0x18014967e  mov     r8, [rbp+3Fh+var_68]
0x180149682  lea     rcx, [rbp+3Fh+var_60]
0x180149686  mov     [rbp+3Fh+var_54], eax
0x180149689  mov     [rbp+3Fh+var_60], rdi
0x18014968d  mov     [rbp+3Fh+var_58], r12d
0x180149691  call    bXformWorkhorse
0x180149696  test    eax, eax
0x180149698  jz      loc_180149793
0x18014969e  mov     edi, [rbp+3Fh+var_54]
0x1801496a1  mov     eax, 1
0x1801496a6  sub     edi, dword ptr [rbp+3Fh+var_60+4]
0x1801496a9  mov     esi, [rbp+3Fh+var_58]
0x1801496ac  sub     esi, dword ptr [rbp+3Fh+var_60]
0x1801496af  mov     r12d, [rbp+3Fh+arg_38]
0x1801496b6  jns     short loc_1801496C2
0x1801496b8  sub     eax, esi
0x1801496ba  add     r12d, eax
0x1801496bd  mov     eax, 1
0x1801496c2  mov     r15d, [rbp+3Fh+arg_40]
0x1801496c9  test    edi, edi
0x1801496cb  jns     short loc_1801496D2
0x1801496cd  sub     eax, edi
0x1801496cf  add     r15d, eax
0x1801496d2  mov     eax, [rbp+3Fh+arg_28]
0x1801496d5  lea     rcx, xformIdentity
0x1801496dc  mov     r9d, [rbp+3Fh+var_80]; int
0x1801496e0  and     eax, 0CC0000h
0x1801496e5  mov     r8d, [rbp+3Fh+var_7C]; int
0x1801496e9  or      eax, 220000h
0x1801496ee  mov     edx, [rbp+3Fh+var_78]; int
0x1801496f1  mov     [rsp+0F0h+var_90], rcx; __int64
0x1801496f6  mov     rcx, qword ptr [rbp+3Fh+var_70]; int
0x1801496fa  mov     [rsp+0F0h+hbm], r14; hbm
0x1801496ff  mov     [rsp+0F0h+hdc], rbx; hdc
0x180149704  mov     [rsp+0F0h+var_A8], edi; int
0x180149708  mov     [rsp+0F0h+var_B0], esi; int
0x18014970c  mov     [rsp+0F0h+var_B8], r15d; int
0x180149711  mov     [rsp+0F0h+var_C0], r12d; int
0x180149716  mov     [rsp+0F0h+var_C8], eax; int
0x18014971a  mov     eax, [rbp+3Fh+arg_20]
0x18014971d  mov     [rsp+0F0h+hDest], eax; hDest
0x180149721  call    DoStretchBltAlt
0x180149726  test    eax, eax
0x180149728  jz      short loc_180149790
0x18014972a  mov     eax, [rbp+3Fh+arg_28]
0x18014972d  lea     rcx, xformIdentity
0x180149734  mov     r9d, [rbp+3Fh+var_80]; int
0x180149738  and     eax, 33000000h
0x18014973d  mov     r8d, [rbp+3Fh+var_7C]; int
0x180149741  or      eax, 880000FFh
0x180149746  mov     edx, [rbp+3Fh+var_78]; int
0x180149749  mov     [rsp+0F0h+var_90], rcx; __int64
0x18014974e  mov     rcx, qword ptr [rbp+3Fh+var_70]; int
0x180149752  mov     [rsp+0F0h+hbm], r14; hbm
0x180149757  mov     [rsp+0F0h+hdc], rbx; hdc
0x18014975c  mov     [rsp+0F0h+var_A8], edi; int
0x180149760  mov     [rsp+0F0h+var_B0], esi; int
0x180149764  mov     [rsp+0F0h+var_B8], r15d; int
0x180149769  shr     eax, 8
0x18014976c  mov     [rsp+0F0h+var_C0], r12d; int
0x180149771  mov     [rsp+0F0h+var_C8], eax; int
0x180149775  mov     eax, [rbp+3Fh+arg_20]
0x180149778  mov     [rsp+0F0h+hDest], eax; hDest
0x18014977c  call    DoStretchBltAlt
0x180149781  mov     edi, [rbp+3Fh+var_74]
0x180149784  test    eax, eax
0x180149786  mov     eax, 1
0x18014978b  cmovnz  edi, eax
0x18014978e  jmp     short loc_180149793
0x180149790  mov     edi, [rbp+3Fh+var_74]
0x180149793  mov     rdx, r13; h
0x180149796  mov     rcx, rbx; hdc
0x180149799  call    cs:__imp_SelectObject
0x1801497a0  nop     dword ptr [rax+rax+00h]
0x1801497a5  mov     rcx, r14; ho
0x1801497a8  call    cs:__imp_DeleteObject
0x1801497af  nop     dword ptr [rax+rax+00h]
0x1801497b4  mov     rcx, rbx; hdc
0x1801497b7  call    cs:__imp_DeleteDC
0x1801497be  nop     dword ptr [rax+rax+00h]
0x1801497c3  mov     eax, edi
0x1801497c5  mov     rcx, [rbp+3Fh+var_50]
0x1801497c9  xor     rcx, rsp; StackCookie
0x1801497cc  call    __security_check_cookie
0x1801497d1  add     rsp, 0B8h
0x1801497d8  pop     r15
0x1801497da  pop     r14
0x1801497dc  pop     r13
0x1801497de  pop     r12
0x1801497e0  pop     rdi
0x1801497e1  pop     rsi
0x1801497e2  pop     rbx
0x1801497e3  pop     rbp
0x1801497e4  retn
```
