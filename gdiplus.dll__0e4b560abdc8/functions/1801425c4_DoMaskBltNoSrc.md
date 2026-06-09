# DoMaskBltNoSrc

- ea: `0x1801425c4`
- end: `0x1801427d7`
- name: `DoMaskBltNoSrc`
- size: `531`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, __int64, __int16, __int16, UINT ColorUse, BITMAPINFO *lpbmi, int, void *lpBits)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180141ed8`

## callees

- `0x1800b1ee8`
- `0x1800e9380`
- `0x18013e4d8`
- `0x1801425c4`
- `0x180143a78`

## import_xrefs

- `GDI32!DeleteDC` at `0x1801427a8`
- `GDI32!DeleteDC` at `0x1801427a8`
- `GDI32!SelectObject` at `0x18014265a`
- `GDI32!SelectObject` at `0x18014278a`
- `GDI32!SelectObject` at `0x18014265a`
- `GDI32!SelectObject` at `0x18014278a`
- `GDI32!CreateCompatibleDC` at `0x180142622`
- `GDI32!CreateCompatibleDC` at `0x180142622`
- `GDI32!DeleteObject` at `0x180142799`
- `GDI32!DeleteObject` at `0x180142799`

## pseudocode

```c
__int64 __fastcall DoMaskBltNoSrc(
        int a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int hDest,
        unsigned int a6,
        __int64 a7,
        __int16 a8,
        __int16 a9,
        UINT ColorUse,
        BITMAPINFO *lpbmi,
        int a12,
        void *lpBits)
{
  unsigned int v14; // ebx
  HDC hdc; // rdi
  HBITMAP MonoDib; // rax
  HBITMAP hbm; // r15
  int v18; // esi
  int v19; // r14d
  __int16 v20; // r13
  __int16 v21; // r12
  HGDIOBJ h; // [rsp+88h] [rbp-29h]
  __int64 v25; // [rsp+90h] [rbp-21h] BYREF
  int v26; // [rsp+98h] [rbp-19h]
  int v27; // [rsp+9Ch] [rbp-15h]

  v14 = 0;
  hdc = CreateCompatibleDC(0);
  if ( hdc )
  {
    MonoDib = (HBITMAP)CreateMonoDib(lpbmi, lpBits, ColorUse);
    hbm = MonoDib;
    if ( MonoDib )
    {
      h = SelectObject(hdc, MonoDib);
      if ( h )
      {
        v27 = hDest;
        v25 = 0;
        v26 = a4;
        if ( (unsigned int)bXformWorkhorse(&v25, 2, a7) )
        {
          v18 = v27 - HIDWORD(v25);
          v19 = v26 - v25;
          v20 = a8;
          if ( v26 - (int)v25 < 0 )
            v20 = 1 - v19 + a8;
          v21 = a9;
          if ( v18 < 0 )
            v21 = 1 - v18 + a9;
          if ( (unsigned int)DoStretchBltAlt(
                               a1,
                               hDest,
                               a6 & 0xCC0000 | 0x220000,
                               v20,
                               v21,
                               v26 - (int)v25,
                               v27 - HIDWORD(v25),
                               hdc,
                               hbm,
                               (__int64)&xformIdentity)
            && (unsigned int)DoStretchBltAlt(
                               a1,
                               hDest,
                               (a6 >> 8) & 0x330000 | 0x880000,
                               v20,
                               v21,
                               v19,
                               v18,
                               hdc,
                               hbm,
                               (__int64)&xformIdentity) )
          {
            v14 = 1;
          }
        }
        SelectObject(hdc, h);
      }
      DeleteObject(hbm);
    }
    DeleteDC(hdc);
  }
  return v14;
}

```

## disassembly

```asm
0x1801425c4  push    rbp
0x1801425c6  push    rbx
0x1801425c7  push    rsi
0x1801425c8  push    rdi
0x1801425c9  push    r12
0x1801425cb  push    r13
0x1801425cd  push    r14
0x1801425cf  push    r15
0x1801425d1  lea     rbp, [rsp-7]
0x1801425d6  sub     rsp, 0B8h
0x1801425dd  mov     rax, cs:__security_cookie
0x1801425e4  xor     rax, rsp
0x1801425e7  mov     [rbp+3Fh+var_50], rax
0x1801425eb  mov     eax, [rbp+3Fh+arg_28]
0x1801425ee  mov     r13d, r9d
0x1801425f1  mov     r12, [rbp+3Fh+arg_30]
0x1801425f5  xor     ebx, ebx
0x1801425f7  mov     esi, [rbp+3Fh+ColorUse]
0x1801425fd  mov     r14, [rbp+3Fh+lpbmi]
0x180142604  mov     r15, [rbp+3Fh+lpBits]
0x18014260b  shr     eax, 8
0x18014260e  mov     qword ptr [rbp+3Fh+var_70], rcx
0x180142612  xor     ecx, ecx; hdc
0x180142614  mov     [rbp+3Fh+var_74], eax
0x180142617  mov     [rbp+3Fh+var_80], r9d
0x18014261b  mov     [rbp+3Fh+var_7C], r8d
0x18014261f  mov     [rbp+3Fh+var_78], edx
0x180142622  call    cs:__imp_CreateCompatibleDC
0x180142629  nop     dword ptr [rax+rax+00h]
0x18014262e  mov     rdi, rax
0x180142631  test    rax, rax
0x180142634  jz      loc_1801427B4
0x18014263a  mov     r8d, esi; ColorUse
0x18014263d  mov     rdx, r15; lpBits
0x180142640  mov     rcx, r14; lpbmi
0x180142643  call    CreateMonoDib
0x180142648  mov     r15, rax
0x18014264b  test    rax, rax
0x18014264e  jz      loc_1801427A5
0x180142654  mov     rdx, rax; h
0x180142657  mov     rcx, rdi; hdc
0x18014265a  call    cs:__imp_SelectObject
0x180142661  nop     dword ptr [rax+rax+00h]
0x180142666  mov     [rbp+3Fh+h], rax
0x18014266a  test    rax, rax
0x18014266d  jz      loc_180142796
0x180142673  mov     eax, [rbp+3Fh+arg_20]
0x180142676  lea     edx, [rbx+2]
0x180142679  mov     r8, r12
0x18014267c  mov     [rbp+3Fh+var_54], eax
0x18014267f  lea     rcx, [rbp+3Fh+var_60]
0x180142683  mov     [rbp+3Fh+var_60], rbx
0x180142687  mov     [rbp+3Fh+var_58], r13d
0x18014268b  call    bXformWorkhorse
0x180142690  test    eax, eax
0x180142692  jz      loc_180142783
0x180142698  mov     esi, [rbp+3Fh+var_54]
0x18014269b  lea     eax, [rbx+1]
0x18014269e  sub     esi, dword ptr [rbp+3Fh+var_60+4]
0x1801426a1  mov     r14d, [rbp+3Fh+var_58]
0x1801426a5  sub     r14d, dword ptr [rbp+3Fh+var_60]
0x1801426a9  mov     r13d, dword ptr [rbp+3Fh+arg_38]
0x1801426b0  jns     short loc_1801426BB
0x1801426b2  sub     eax, r14d
0x1801426b5  add     r13d, eax
0x1801426b8  lea     eax, [rbx+1]
0x1801426bb  mov     r12d, dword ptr [rbp+3Fh+arg_40]
0x1801426c2  test    esi, esi
0x1801426c4  jns     short loc_1801426CB
0x1801426c6  sub     eax, esi
0x1801426c8  add     r12d, eax
0x1801426cb  mov     eax, [rbp+3Fh+arg_28]
0x1801426ce  lea     rcx, xformIdentity
0x1801426d5  mov     r9d, [rbp+3Fh+var_80]
0x1801426d9  and     eax, 0CC0000h
0x1801426de  mov     r8d, [rbp+3Fh+var_7C]
0x1801426e2  or      eax, 220000h
0x1801426e7  mov     edx, [rbp+3Fh+var_78]
0x1801426ea  mov     [rsp+0F0h+var_90], rcx; __int64
0x1801426ef  mov     rcx, qword ptr [rbp+3Fh+var_70]; int
0x1801426f3  mov     [rsp+0F0h+hbm], r15; hbm
0x1801426f8  mov     [rsp+0F0h+hdc], rdi; hdc
0x1801426fd  mov     [rsp+0F0h+var_A8], esi; int
0x180142701  mov     [rsp+0F0h+var_B0], r14d; int
0x180142706  mov     dword ptr [rsp+0F0h+var_B8], r12d; __int16
0x18014270b  mov     dword ptr [rsp+0F0h+var_C0], r13d; __int16
0x180142710  mov     [rsp+0F0h+var_C8], eax; int
0x180142714  mov     eax, [rbp+3Fh+arg_20]
0x180142717  mov     [rsp+0F0h+hDest], eax; hDest
0x18014271b  call    DoStretchBltAlt
0x180142720  test    eax, eax
0x180142722  jz      short loc_180142783
0x180142724  mov     eax, [rbp+3Fh+var_74]
0x180142727  lea     rcx, xformIdentity
0x18014272e  mov     r9d, [rbp+3Fh+var_80]
0x180142732  and     eax, 330000h
0x180142737  mov     r8d, [rbp+3Fh+var_7C]
0x18014273b  or      eax, 880000h
0x180142740  mov     edx, [rbp+3Fh+var_78]
0x180142743  mov     [rsp+0F0h+var_90], rcx; __int64
0x180142748  mov     rcx, qword ptr [rbp+3Fh+var_70]; int
0x18014274c  mov     [rsp+0F0h+hbm], r15; hbm
0x180142751  mov     [rsp+0F0h+hdc], rdi; hdc
0x180142756  mov     [rsp+0F0h+var_A8], esi; int
0x18014275a  mov     [rsp+0F0h+var_B0], r14d; int
0x18014275f  mov     dword ptr [rsp+0F0h+var_B8], r12d; __int16
0x180142764  mov     dword ptr [rsp+0F0h+var_C0], r13d; __int16
0x180142769  mov     [rsp+0F0h+var_C8], eax; int
0x18014276d  mov     eax, [rbp+3Fh+arg_20]
0x180142770  mov     [rsp+0F0h+hDest], eax; hDest
0x180142774  call    DoStretchBltAlt
0x180142779  test    eax, eax
0x18014277b  mov     eax, 1
0x180142780  cmovnz  ebx, eax
0x180142783  mov     rdx, [rbp+3Fh+h]; h
0x180142787  mov     rcx, rdi; hdc
0x18014278a  call    cs:__imp_SelectObject
0x180142791  nop     dword ptr [rax+rax+00h]
0x180142796  mov     rcx, r15; ho
0x180142799  call    cs:__imp_DeleteObject
0x1801427a0  nop     dword ptr [rax+rax+00h]
0x1801427a5  mov     rcx, rdi; hdc
0x1801427a8  call    cs:__imp_DeleteDC
0x1801427af  nop     dword ptr [rax+rax+00h]
0x1801427b4  mov     eax, ebx
0x1801427b6  mov     rcx, [rbp+3Fh+var_50]
0x1801427ba  xor     rcx, rsp; StackCookie
0x1801427bd  call    __security_check_cookie
0x1801427c2  add     rsp, 0B8h
0x1801427c9  pop     r15
0x1801427cb  pop     r14
0x1801427cd  pop     r13
0x1801427cf  pop     r12
0x1801427d1  pop     rdi
0x1801427d2  pop     rsi
0x1801427d3  pop     rbx
0x1801427d4  pop     rbp
0x1801427d5  retn
```
