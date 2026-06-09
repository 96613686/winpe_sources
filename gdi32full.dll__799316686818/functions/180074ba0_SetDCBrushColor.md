# SetDCBrushColor

- ea: `0x180074ba0`
- end: `0x180074dac`
- name: `SetDCBrushColor`
- size: `524`
- prototype: `COLORREF __stdcall(HDC hdc, COLORREF color)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180047580`
- `0x1800710c4`
- `0x180074ba0`
- `0x180089c9c`
- `0x18008d1ac`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180074be2`
- `GDI32!GdiGetEntry` at `0x180074be2`
- `GDI32!gW32PID` at `0x180074c1a`
- `GDI32!gCookie` at `0x180074c3e`
- `GDI32!gMaxGdiHandleCount` at `0x180074bbc`
- `GDI32!pldcGet` at `0x180074c80`
- `GDI32!pldcGet` at `0x180074c80`
- `GDI32!GdiSetLastError` at `0x180074d7e`
- `GDI32!GdiSetLastError` at `0x180074d91`
- `GDI32!GdiSetLastError` at `0x180074d7e`
- `GDI32!GdiSetLastError` at `0x180074d91`
- `GDI32!DeleteObject` at `0x180074cdb`
- `GDI32!DeleteObject` at `0x180074cdb`

## pseudocode

```c
COLORREF __stdcall SetDCBrushColor(HDC hdc, COLORREF color)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  HBRUSH SolidBrush; // r14
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
              if ( *(_QWORD *)(v5 + 160) != ghbrDCBrush )
                goto LABEL_20;
              SolidBrush = CreateSolidBrush(color);
              if ( SolidBrush )
              {
                v9 = *(void **)(v7 + 304);
                if ( v9 )
                  DeleteObject(v9);
                v10 = MF_SelectAnyObject(hdc, SolidBrush);
                *(_QWORD *)(v7 + 304) = SolidBrush;
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
          v11 = *(_DWORD *)(v5 + 196);
          *(_DWORD *)(v5 + 196) = color;
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
          if ( v12 != *(_DWORD *)(v5 + 192) )
          {
            *(_DWORD *)(v5 + 192) = v12;
            *(_DWORD *)(v5 + 152) |= 1u;
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
0x180074ba0  mov     [rsp+arg_0], rbx
0x180074ba5  mov     [rsp+arg_8], rbp
0x180074baa  push    rsi
0x180074bab  push    rdi
0x180074bac  push    r14
0x180074bae  sub     rsp, 50h
0x180074bb2  mov     esi, edx
0x180074bb4  mov     rbp, rcx
0x180074bb7  call    HANDLE_TO_INDEX
0x180074bbc  mov     r8, cs:__imp_gMaxGdiHandleCount
0x180074bc3  cmp     eax, [r8]
0x180074bc6  jnb     loc_180074D89
0x180074bcc  xor     ecx, ecx
0x180074bce  lea     rdx, [rsp+68h+var_38]
0x180074bd3  mov     [rsp+68h+var_28], rcx
0x180074bd8  xorps   xmm0, xmm0
0x180074bdb  mov     ecx, eax
0x180074bdd  movups  [rsp+68h+var_38], xmm0
0x180074be2  call    cs:__imp_GdiGetEntry
0x180074be8  test    eax, eax
0x180074bea  js      loc_180074D89
0x180074bf0  cmp     byte ptr [rsp+68h+var_38+0Eh], 1
0x180074bf5  jnz     loc_180074D89
0x180074bfb  movzx   eax, byte ptr [rsp+68h+var_38+0Ch]
0x180074c00  movzx   ecx, byte ptr [rsp+68h+var_38+0Dh]
0x180074c05  shl     cx, 8
0x180074c09  or      cx, ax
0x180074c0c  mov     eax, ebp
0x180074c0e  shr     eax, 10h
0x180074c11  cmp     cx, ax
0x180074c14  jnz     loc_180074D89
0x180074c1a  mov     rax, cs:__imp_gW32PID
0x180074c21  mov     ecx, dword ptr [rsp+68h+var_38+8]
0x180074c25  and     ecx, 0FFFFFFFEh
0x180074c28  cmp     ecx, [rax]
0x180074c2a  jnz     loc_180074D89
0x180074c30  mov     rdx, [rsp+68h+var_28]
0x180074c35  test    rdx, rdx
0x180074c38  jz      loc_180074D89
0x180074c3e  mov     rax, cs:__imp_gCookie
0x180074c45  mov     ecx, 40h ; '@'
0x180074c4a  mov     rbx, [rax]
0x180074c4d  mov     eax, ebx
0x180074c4f  and     eax, 3Fh
0x180074c52  sub     ecx, eax
0x180074c54  ror     rdx, cl
0x180074c57  xor     rbx, rdx
0x180074c5a  jz      loc_180074D89
0x180074c60  mov     eax, ebp
0x180074c62  and     eax, 7F0000h
0x180074c67  cmp     eax, 10000h
0x180074c6c  jz      loc_180074D01
0x180074c72  cmp     eax, 660000h
0x180074c77  jz      loc_180074D01
0x180074c7d  mov     rcx, rbp
0x180074c80  call    cs:__imp_pldcGet
0x180074c86  mov     rdi, rax
0x180074c89  test    rax, rax
0x180074c8c  jz      loc_180074D79
0x180074c92  cmp     dword ptr [rax+0Ch], 2
0x180074c96  jnz     short loc_180074D01
0x180074c98  mov     eax, esi
0x180074c9a  mov     ecx, 0FFFFFFh
0x180074c9f  and     eax, ecx
0x180074ca1  jz      short loc_180074CAC
0x180074ca3  cmp     eax, ecx
0x180074ca5  jz      short loc_180074CAC
0x180074ca7  bts     dword ptr [rdi+8], 1Dh
0x180074cac  mov     rax, cs:ghbrDCBrush
0x180074cb3  cmp     [rbx+0A0h], rax
0x180074cba  jnz     short loc_180074D01
0x180074cbc  mov     ecx, esi; color
0x180074cbe  call    CreateSolidBrush
0x180074cc3  mov     r14, rax
0x180074cc6  test    rax, rax
0x180074cc9  jz      loc_180074D84
0x180074ccf  mov     rcx, [rdi+130h]; ho
0x180074cd6  test    rcx, rcx
0x180074cd9  jz      short loc_180074CE1
0x180074cdb  call    cs:__imp_DeleteObject
0x180074ce1  mov     r8d, 25h ; '%'
0x180074ce7  mov     rdx, r14; void *
0x180074cea  mov     rcx, rbp; void *
0x180074ced  call    MF_SelectAnyObject
0x180074cf2  mov     [rdi+130h], r14
0x180074cf9  test    eax, eax
0x180074cfb  jz      loc_180074D84
0x180074d01  mov     edi, [rbx+0C4h]
0x180074d07  mov     [rbx+0C4h], esi
0x180074d0d  and     esi, 13FFFFFFh
0x180074d13  bt      esi, 18h
0x180074d17  jb      short loc_180074D62
0x180074d19  mov     eax, [rbx+0F0h]
0x180074d1f  and     al, 11h
0x180074d21  cmp     al, 1
0x180074d23  jnz     short loc_180074D62
0x180074d25  cmp     qword ptr [rbx+0F8h], 0
0x180074d2d  jz      short loc_180074D62
0x180074d2f  lea     r9, [rsp+68h+arg_10]
0x180074d37  mov     [rsp+68h+arg_10], 0
0x180074d42  mov     r8d, esi
0x180074d45  mov     [rsp+68h+var_48], 1
0x180074d4d  mov     rdx, rbx
0x180074d50  mov     rcx, rbp
0x180074d53  call    IcmTranslateCOLORREF
0x180074d58  test    eax, eax
0x180074d5a  cmovnz  esi, [rsp+68h+arg_10]
0x180074d62  cmp     esi, [rbx+0C0h]
0x180074d68  jz      short loc_180074D97
0x180074d6a  mov     [rbx+0C0h], esi
0x180074d70  or      dword ptr [rbx+98h], 1
0x180074d77  jmp     short loc_180074D97
0x180074d79  mov     ecx, 6
0x180074d7e  call    cs:__imp_GdiSetLastError
0x180074d84  or      eax, 0FFFFFFFFh
0x180074d87  jmp     short loc_180074D99
0x180074d89  or      edi, 0FFFFFFFFh
0x180074d8c  mov     ecx, 57h ; 'W'
0x180074d91  call    cs:__imp_GdiSetLastError
0x180074d97  mov     eax, edi
0x180074d99  mov     rbx, [rsp+68h+arg_0]
0x180074d9e  mov     rbp, [rsp+68h+arg_8]
0x180074da3  add     rsp, 50h
0x180074da7  pop     r14
0x180074da9  pop     rdi
0x180074daa  pop     rsi
0x180074dab  retn
```
