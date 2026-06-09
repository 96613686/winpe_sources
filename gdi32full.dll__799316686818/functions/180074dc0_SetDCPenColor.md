# SetDCPenColor

- ea: `0x180074dc0`
- end: `0x180074fd1`
- name: `SetDCPenColor`
- size: `529`
- prototype: `COLORREF __stdcall(HDC hdc, COLORREF color)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18005ba70`
- `0x1800710c4`
- `0x180074dc0`
- `0x180089c9c`
- `0x18008d1ac`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180074e02`
- `GDI32!GdiGetEntry` at `0x180074e02`
- `GDI32!gW32PID` at `0x180074e3a`
- `GDI32!gCookie` at `0x180074e5e`
- `GDI32!gMaxGdiHandleCount` at `0x180074ddc`
- `GDI32!pldcGet` at `0x180074ea0`
- `GDI32!pldcGet` at `0x180074ea0`
- `GDI32!GdiSetLastError` at `0x180074fa3`
- `GDI32!GdiSetLastError` at `0x180074fb6`
- `GDI32!GdiSetLastError` at `0x180074fa3`
- `GDI32!GdiSetLastError` at `0x180074fb6`
- `GDI32!DeleteObject` at `0x180074f00`
- `GDI32!DeleteObject` at `0x180074f00`

## pseudocode

```c
COLORREF __stdcall SetDCPenColor(HDC hdc, COLORREF color)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  HPEN Pen; // r14
  void *v9; // rcx
  int v10; // eax
  COLORREF v11; // edi
  COLORREF v12; // esi
  __int128 v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]
  COLORREF v16; // [rsp+80h] [rbp+18h] BYREF

  v4 = HANDLE_TO_INDEX(hdc);
  if ( v4 < gMaxGdiHandleCount )
  {
    v15 = 0;
    v14 = 0;
    if ( (int)GdiGetEntry(v4, &v14) >= 0
      && BYTE14(v14) == 1
      && WORD6(v14) == WORD1(hdc)
      && (DWORD2(v14) & 0xFFFFFFFE) == gW32PID )
    {
      if ( v15 )
      {
        v5 = __ROR8__(v15, 64 - (gCookie & 0x3Fu)) ^ gCookie;
        if ( v5 )
        {
          if ( ((unsigned int)hdc & 0x7F0000) != 0x10000 && ((unsigned int)hdc & 0x7F0000) != 0x660000 )
          {
            v6 = pldcGet(hdc);
            v7 = v6;
            if ( v6 )
            {
              if ( *(_DWORD *)(v6 + 12) != 2 )
                goto LABEL_20;
              if ( (color & 0xFFFFFF) != 0 && (color & 0xFFFFFF) != 0xFFFFFF )
                *(_DWORD *)(v6 + 8) |= 0x20000000u;
              if ( *(_QWORD *)(v5 + 168) != ghbrDCPen )
                goto LABEL_20;
              Pen = CreatePen(0, 0, color);
              if ( Pen )
              {
                v9 = *(void **)(v7 + 312);
                if ( v9 )
                  DeleteObject(v9);
                v10 = MF_SelectAnyObject(hdc, Pen);
                *(_QWORD *)(v7 + 312) = Pen;
                if ( v10 )
                  goto LABEL_20;
              }
            }
            else
            {
              GdiSetLastError(6);
            }
            return -1;
          }
LABEL_20:
          v11 = *(_DWORD *)(v5 + 204);
          *(_DWORD *)(v5 + 204) = color;
          v12 = color & 0x13FFFFFF;
          if ( (v12 & 0x1000000) == 0 && (*(_DWORD *)(v5 + 240) & 0x11) == 1 )
          {
            if ( *(_QWORD *)(v5 + 248) )
            {
              v16 = 0;
              if ( (unsigned int)IcmTranslateCOLORREF((_DWORD)hdc, v5, v12, (unsigned int)&v16, 1) )
                v12 = v16;
            }
          }
          if ( v12 != *(_DWORD *)(v5 + 200) )
          {
            *(_DWORD *)(v5 + 200) = v12;
            *(_DWORD *)(v5 + 152) |= 2u;
          }
          return v11;
        }
      }
    }
  }
  v11 = -1;
  GdiSetLastError(87);
  return v11;
}

```

## disassembly

```asm
0x180074dc0  mov     [rsp+arg_0], rbx
0x180074dc5  mov     [rsp+arg_8], rbp
0x180074dca  push    rsi
0x180074dcb  push    rdi
0x180074dcc  push    r14
0x180074dce  sub     rsp, 50h
0x180074dd2  mov     esi, edx
0x180074dd4  mov     rbp, rcx
0x180074dd7  call    HANDLE_TO_INDEX
0x180074ddc  mov     r8, cs:__imp_gMaxGdiHandleCount
0x180074de3  cmp     eax, [r8]
0x180074de6  jnb     loc_180074FAE
0x180074dec  xor     ecx, ecx
0x180074dee  lea     rdx, [rsp+68h+var_38]
0x180074df3  mov     [rsp+68h+var_28], rcx
0x180074df8  xorps   xmm0, xmm0
0x180074dfb  mov     ecx, eax
0x180074dfd  movups  [rsp+68h+var_38], xmm0
0x180074e02  call    cs:__imp_GdiGetEntry
0x180074e08  test    eax, eax
0x180074e0a  js      loc_180074FAE
0x180074e10  cmp     byte ptr [rsp+68h+var_38+0Eh], 1
0x180074e15  jnz     loc_180074FAE
0x180074e1b  movzx   eax, byte ptr [rsp+68h+var_38+0Ch]
0x180074e20  movzx   ecx, byte ptr [rsp+68h+var_38+0Dh]
0x180074e25  shl     cx, 8
0x180074e29  or      cx, ax
0x180074e2c  mov     eax, ebp
0x180074e2e  shr     eax, 10h
0x180074e31  cmp     cx, ax
0x180074e34  jnz     loc_180074FAE
0x180074e3a  mov     rax, cs:__imp_gW32PID
0x180074e41  mov     ecx, dword ptr [rsp+68h+var_38+8]
0x180074e45  and     ecx, 0FFFFFFFEh
0x180074e48  cmp     ecx, [rax]
0x180074e4a  jnz     loc_180074FAE
0x180074e50  mov     rdx, [rsp+68h+var_28]
0x180074e55  test    rdx, rdx
0x180074e58  jz      loc_180074FAE
0x180074e5e  mov     rax, cs:__imp_gCookie
0x180074e65  mov     ecx, 40h ; '@'
0x180074e6a  mov     rbx, [rax]
0x180074e6d  mov     eax, ebx
0x180074e6f  and     eax, 3Fh
0x180074e72  sub     ecx, eax
0x180074e74  ror     rdx, cl
0x180074e77  xor     rbx, rdx
0x180074e7a  jz      loc_180074FAE
0x180074e80  mov     eax, ebp
0x180074e82  and     eax, 7F0000h
0x180074e87  cmp     eax, 10000h
0x180074e8c  jz      loc_180074F26
0x180074e92  cmp     eax, 660000h
0x180074e97  jz      loc_180074F26
0x180074e9d  mov     rcx, rbp
0x180074ea0  call    cs:__imp_pldcGet
0x180074ea6  mov     rdi, rax
0x180074ea9  test    rax, rax
0x180074eac  jz      loc_180074F9E
0x180074eb2  cmp     dword ptr [rax+0Ch], 2
0x180074eb6  jnz     short loc_180074F26
0x180074eb8  mov     eax, esi
0x180074eba  mov     ecx, 0FFFFFFh
0x180074ebf  and     eax, ecx
0x180074ec1  jz      short loc_180074ECC
0x180074ec3  cmp     eax, ecx
0x180074ec5  jz      short loc_180074ECC
0x180074ec7  bts     dword ptr [rdi+8], 1Dh
0x180074ecc  mov     rax, cs:ghbrDCPen
0x180074ed3  cmp     [rbx+0A8h], rax
0x180074eda  jnz     short loc_180074F26
0x180074edc  mov     r8d, esi; color
0x180074edf  xor     edx, edx; cWidth
0x180074ee1  xor     ecx, ecx; iStyle
0x180074ee3  call    CreatePen
0x180074ee8  mov     r14, rax
0x180074eeb  test    rax, rax
0x180074eee  jz      loc_180074FA9
0x180074ef4  mov     rcx, [rdi+138h]; ho
0x180074efb  test    rcx, rcx
0x180074efe  jz      short loc_180074F06
0x180074f00  call    cs:__imp_DeleteObject
0x180074f06  mov     r8d, 25h ; '%'
0x180074f0c  mov     rdx, r14; void *
0x180074f0f  mov     rcx, rbp; void *
0x180074f12  call    MF_SelectAnyObject
0x180074f17  mov     [rdi+138h], r14
0x180074f1e  test    eax, eax
0x180074f20  jz      loc_180074FA9
0x180074f26  mov     edi, [rbx+0CCh]
0x180074f2c  mov     [rbx+0CCh], esi
0x180074f32  and     esi, 13FFFFFFh
0x180074f38  bt      esi, 18h
0x180074f3c  jb      short loc_180074F87
0x180074f3e  mov     eax, [rbx+0F0h]
0x180074f44  and     al, 11h
0x180074f46  cmp     al, 1
0x180074f48  jnz     short loc_180074F87
0x180074f4a  cmp     qword ptr [rbx+0F8h], 0
0x180074f52  jz      short loc_180074F87
0x180074f54  lea     r9, [rsp+68h+arg_10]
0x180074f5c  mov     [rsp+68h+arg_10], 0
0x180074f67  mov     r8d, esi
0x180074f6a  mov     [rsp+68h+var_48], 1
0x180074f72  mov     rdx, rbx
0x180074f75  mov     rcx, rbp
0x180074f78  call    IcmTranslateCOLORREF
0x180074f7d  test    eax, eax
0x180074f7f  cmovnz  esi, [rsp+68h+arg_10]
0x180074f87  cmp     esi, [rbx+0C8h]
0x180074f8d  jz      short loc_180074FBC
0x180074f8f  mov     [rbx+0C8h], esi
0x180074f95  or      dword ptr [rbx+98h], 2
0x180074f9c  jmp     short loc_180074FBC
0x180074f9e  mov     ecx, 6
0x180074fa3  call    cs:__imp_GdiSetLastError
0x180074fa9  or      eax, 0FFFFFFFFh
0x180074fac  jmp     short loc_180074FBE
0x180074fae  or      edi, 0FFFFFFFFh
0x180074fb1  mov     ecx, 57h ; 'W'
0x180074fb6  call    cs:__imp_GdiSetLastError
0x180074fbc  mov     eax, edi
0x180074fbe  mov     rbx, [rsp+68h+arg_0]
0x180074fc3  mov     rbp, [rsp+68h+arg_8]
0x180074fc8  add     rsp, 50h
0x180074fcc  pop     r14
0x180074fce  pop     rdi
0x180074fcf  pop     rsi
0x180074fd0  retn
```
