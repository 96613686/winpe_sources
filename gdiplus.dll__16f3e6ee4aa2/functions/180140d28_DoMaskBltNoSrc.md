# DoMaskBltNoSrc

- ea: `0x180140d28`
- end: `0x180140f23`
- name: `DoMaskBltNoSrc`
- size: `507`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, __int64, int, int, UINT ColorUse, BITMAPINFO *lpbmi, int, void *lpBits)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800f7f28`

## callees

- `0x1800c3bb8`
- `0x1800fe680`
- `0x18013e580`
- `0x180140d28`
- `0x1801414e8`

## import_xrefs

- `GDI32!DeleteDC` at `0x180140efb`
- `GDI32!DeleteDC` at `0x180140efb`
- `GDI32!SelectObject` at `0x180140db6`
- `GDI32!SelectObject` at `0x180140ee9`
- `GDI32!SelectObject` at `0x180140db6`
- `GDI32!SelectObject` at `0x180140ee9`
- `GDI32!CreateCompatibleDC` at `0x180140d84`
- `GDI32!CreateCompatibleDC` at `0x180140d84`
- `GDI32!DeleteObject` at `0x180140ef2`
- `GDI32!DeleteObject` at `0x180140ef2`

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
0x180140d28  push    rbp
0x180140d2a  push    rbx
0x180140d2b  push    rsi
0x180140d2c  push    rdi
0x180140d2d  push    r12
0x180140d2f  push    r13
0x180140d31  push    r14
0x180140d33  push    r15
0x180140d35  lea     rbp, [rsp-7]
0x180140d3a  sub     rsp, 0B8h
0x180140d41  mov     rax, cs:__security_cookie
0x180140d48  xor     rax, rsp
0x180140d4b  mov     [rbp+3Fh+var_50], rax
0x180140d4f  mov     rax, [rbp+3Fh+arg_30]
0x180140d53  xor     edi, edi
0x180140d55  mov     esi, [rbp+3Fh+ColorUse]
0x180140d5b  mov     r12d, r9d
0x180140d5e  mov     r14, [rbp+3Fh+lpbmi]
0x180140d65  mov     r15, [rbp+3Fh+lpBits]
0x180140d6c  mov     qword ptr [rbp+3Fh+var_70], rcx
0x180140d70  xor     ecx, ecx; hdc
0x180140d72  mov     [rbp+3Fh+var_68], rax
0x180140d76  mov     [rbp+3Fh+var_74], edi
0x180140d79  mov     [rbp+3Fh+var_80], r9d
0x180140d7d  mov     [rbp+3Fh+var_7C], r8d
0x180140d81  mov     [rbp+3Fh+var_78], edx
0x180140d84  call    cs:__imp_CreateCompatibleDC
0x180140d8a  mov     rbx, rax
0x180140d8d  test    rax, rax
0x180140d90  jz      loc_180140F01
0x180140d96  mov     r8d, esi; ColorUse
0x180140d99  mov     rdx, r15; lpBits
0x180140d9c  mov     rcx, r14; lpbmi
0x180140d9f  call    CreateMonoDib
0x180140da4  mov     r14, rax
0x180140da7  test    rax, rax
0x180140daa  jz      loc_180140EF8
0x180140db0  mov     rdx, rax; h
0x180140db3  mov     rcx, rbx; hdc
0x180140db6  call    cs:__imp_SelectObject
0x180140dbc  mov     r13, rax
0x180140dbf  test    rax, rax
0x180140dc2  jz      loc_180140EEF
0x180140dc8  mov     eax, [rbp+3Fh+arg_20]
0x180140dcb  lea     edx, [rdi+2]
0x180140dce  mov     r8, [rbp+3Fh+var_68]
0x180140dd2  lea     rcx, [rbp+3Fh+var_60]
0x180140dd6  mov     [rbp+3Fh+var_54], eax
0x180140dd9  mov     [rbp+3Fh+var_60], rdi
0x180140ddd  mov     [rbp+3Fh+var_58], r12d
0x180140de1  call    bXformWorkhorse
0x180140de6  test    eax, eax
0x180140de8  jz      loc_180140EE3
0x180140dee  mov     edi, [rbp+3Fh+var_54]
0x180140df1  mov     eax, 1
0x180140df6  sub     edi, dword ptr [rbp+3Fh+var_60+4]
0x180140df9  mov     esi, [rbp+3Fh+var_58]
0x180140dfc  sub     esi, dword ptr [rbp+3Fh+var_60]
0x180140dff  mov     r12d, [rbp+3Fh+arg_38]
0x180140e06  jns     short loc_180140E12
0x180140e08  sub     eax, esi
0x180140e0a  add     r12d, eax
0x180140e0d  mov     eax, 1
0x180140e12  mov     r15d, [rbp+3Fh+arg_40]
0x180140e19  test    edi, edi
0x180140e1b  jns     short loc_180140E22
0x180140e1d  sub     eax, edi
0x180140e1f  add     r15d, eax
0x180140e22  mov     eax, [rbp+3Fh+arg_28]
0x180140e25  lea     rcx, xformIdentity
0x180140e2c  mov     r9d, [rbp+3Fh+var_80]; int
0x180140e30  and     eax, 0CC0000h
0x180140e35  mov     r8d, [rbp+3Fh+var_7C]; int
0x180140e39  or      eax, 220000h
0x180140e3e  mov     edx, [rbp+3Fh+var_78]; int
0x180140e41  mov     [rsp+0F0h+var_90], rcx; __int64
0x180140e46  mov     rcx, qword ptr [rbp+3Fh+var_70]; int
0x180140e4a  mov     [rsp+0F0h+hbm], r14; hbm
0x180140e4f  mov     [rsp+0F0h+hdc], rbx; hdc
0x180140e54  mov     [rsp+0F0h+var_A8], edi; int
0x180140e58  mov     [rsp+0F0h+var_B0], esi; int
0x180140e5c  mov     [rsp+0F0h+var_B8], r15d; int
0x180140e61  mov     [rsp+0F0h+var_C0], r12d; int
0x180140e66  mov     [rsp+0F0h+var_C8], eax; int
0x180140e6a  mov     eax, [rbp+3Fh+arg_20]
0x180140e6d  mov     [rsp+0F0h+hDest], eax; hDest
0x180140e71  call    DoStretchBltAlt
0x180140e76  test    eax, eax
0x180140e78  jz      short loc_180140EE0
0x180140e7a  mov     eax, [rbp+3Fh+arg_28]
0x180140e7d  lea     rcx, xformIdentity
0x180140e84  mov     r9d, [rbp+3Fh+var_80]; int
0x180140e88  and     eax, 33000000h
0x180140e8d  mov     r8d, [rbp+3Fh+var_7C]; int
0x180140e91  or      eax, 880000FFh
0x180140e96  mov     edx, [rbp+3Fh+var_78]; int
0x180140e99  mov     [rsp+0F0h+var_90], rcx; __int64
0x180140e9e  mov     rcx, qword ptr [rbp+3Fh+var_70]; int
0x180140ea2  mov     [rsp+0F0h+hbm], r14; hbm
0x180140ea7  mov     [rsp+0F0h+hdc], rbx; hdc
0x180140eac  mov     [rsp+0F0h+var_A8], edi; int
0x180140eb0  mov     [rsp+0F0h+var_B0], esi; int
0x180140eb4  mov     [rsp+0F0h+var_B8], r15d; int
0x180140eb9  shr     eax, 8
0x180140ebc  mov     [rsp+0F0h+var_C0], r12d; int
0x180140ec1  mov     [rsp+0F0h+var_C8], eax; int
0x180140ec5  mov     eax, [rbp+3Fh+arg_20]
0x180140ec8  mov     [rsp+0F0h+hDest], eax; hDest
0x180140ecc  call    DoStretchBltAlt
0x180140ed1  mov     edi, [rbp+3Fh+var_74]
0x180140ed4  test    eax, eax
0x180140ed6  mov     eax, 1
0x180140edb  cmovnz  edi, eax
0x180140ede  jmp     short loc_180140EE3
0x180140ee0  mov     edi, [rbp+3Fh+var_74]
0x180140ee3  mov     rdx, r13; h
0x180140ee6  mov     rcx, rbx; hdc
0x180140ee9  call    cs:__imp_SelectObject
0x180140eef  mov     rcx, r14; ho
0x180140ef2  call    cs:__imp_DeleteObject
0x180140ef8  mov     rcx, rbx; hdc
0x180140efb  call    cs:__imp_DeleteDC
0x180140f01  mov     eax, edi
0x180140f03  mov     rcx, [rbp+3Fh+var_50]
0x180140f07  xor     rcx, rsp; StackCookie
0x180140f0a  call    __security_check_cookie
0x180140f0f  add     rsp, 0B8h
0x180140f16  pop     r15
0x180140f18  pop     r14
0x180140f1a  pop     r13
0x180140f1c  pop     r12
0x180140f1e  pop     rdi
0x180140f1f  pop     rsi
0x180140f20  pop     rbx
0x180140f21  pop     rbp
0x180140f22  retn
```
