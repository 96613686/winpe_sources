# SetDCPenColor

- ea: `0x180079700`
- end: `0x180079930`
- name: `SetDCPenColor`
- size: `560`
- prototype: `COLORREF __stdcall(HDC hdc, COLORREF color)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18005fda0`
- `0x1800756cc`
- `0x180079700`
- `0x18008f324`
- `0x180092a2c`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x180079742`
- `GDI32!GdiGetEntry` at `0x180079742`
- `GDI32!gW32PID` at `0x180079780`
- `GDI32!gCookie` at `0x1800797a4`
- `GDI32!gMaxGdiHandleCount` at `0x18007971c`
- `GDI32!pldcGet` at `0x1800797e6`
- `GDI32!pldcGet` at `0x1800797e6`
- `GDI32!GdiSetLastError` at `0x1800798f5`
- `GDI32!GdiSetLastError` at `0x18007990e`
- `GDI32!GdiSetLastError` at `0x1800798f5`
- `GDI32!GdiSetLastError` at `0x18007990e`
- `GDI32!DeleteObject` at `0x18007984c`
- `GDI32!DeleteObject` at `0x18007984c`

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
0x180079700  mov     [rsp+arg_0], rbx
0x180079705  mov     [rsp+arg_8], rbp
0x18007970a  push    rsi
0x18007970b  push    rdi
0x18007970c  push    r14
0x18007970e  sub     rsp, 50h
0x180079712  mov     esi, edx
0x180079714  mov     rbp, rcx
0x180079717  call    HANDLE_TO_INDEX
0x18007971c  mov     r8, cs:__imp_gMaxGdiHandleCount
0x180079723  cmp     eax, [r8]
0x180079726  jnb     loc_180079906
0x18007972c  xor     ecx, ecx
0x18007972e  lea     rdx, [rsp+68h+var_38]
0x180079733  mov     [rsp+68h+var_28], rcx
0x180079738  xorps   xmm0, xmm0
0x18007973b  mov     ecx, eax
0x18007973d  movups  [rsp+68h+var_38], xmm0
0x180079742  call    cs:__imp_GdiGetEntry
0x180079749  nop     dword ptr [rax+rax+00h]
0x18007974e  test    eax, eax
0x180079750  js      loc_180079906
0x180079756  cmp     byte ptr [rsp+68h+var_38+0Eh], 1
0x18007975b  jnz     loc_180079906
0x180079761  movzx   eax, byte ptr [rsp+68h+var_38+0Ch]
0x180079766  movzx   ecx, byte ptr [rsp+68h+var_38+0Dh]
0x18007976b  shl     cx, 8
0x18007976f  or      cx, ax
0x180079772  mov     eax, ebp
0x180079774  shr     eax, 10h
0x180079777  cmp     cx, ax
0x18007977a  jnz     loc_180079906
0x180079780  mov     rax, cs:__imp_gW32PID
0x180079787  mov     ecx, dword ptr [rsp+68h+var_38+8]
0x18007978b  and     ecx, 0FFFFFFFEh
0x18007978e  cmp     ecx, [rax]
0x180079790  jnz     loc_180079906
0x180079796  mov     rdx, [rsp+68h+var_28]
0x18007979b  test    rdx, rdx
0x18007979e  jz      loc_180079906
0x1800797a4  mov     rax, cs:__imp_gCookie
0x1800797ab  mov     ecx, 40h ; '@'
0x1800797b0  mov     rbx, [rax]
0x1800797b3  mov     eax, ebx
0x1800797b5  and     eax, 3Fh
0x1800797b8  sub     ecx, eax
0x1800797ba  ror     rdx, cl
0x1800797bd  xor     rbx, rdx
0x1800797c0  jz      loc_180079906
0x1800797c6  mov     eax, ebp
0x1800797c8  and     eax, 7F0000h
0x1800797cd  cmp     eax, 10000h
0x1800797d2  jz      loc_180079878
0x1800797d8  cmp     eax, 660000h
0x1800797dd  jz      loc_180079878
0x1800797e3  mov     rcx, rbp
0x1800797e6  call    cs:__imp_pldcGet
0x1800797ed  nop     dword ptr [rax+rax+00h]
0x1800797f2  mov     rdi, rax
0x1800797f5  test    rax, rax
0x1800797f8  jz      loc_1800798F0
0x1800797fe  cmp     dword ptr [rax+0Ch], 2
0x180079802  jnz     short loc_180079878
0x180079804  mov     eax, esi
0x180079806  mov     ecx, 0FFFFFFh
0x18007980b  and     eax, ecx
0x18007980d  jz      short loc_180079818
0x18007980f  cmp     eax, ecx
0x180079811  jz      short loc_180079818
0x180079813  bts     dword ptr [rdi+8], 1Dh
0x180079818  mov     rax, cs:ghbrDCPen
0x18007981f  cmp     [rbx+0A8h], rax
0x180079826  jnz     short loc_180079878
0x180079828  mov     r8d, esi; color
0x18007982b  xor     edx, edx; cWidth
0x18007982d  xor     ecx, ecx; iStyle
0x18007982f  call    CreatePen
0x180079834  mov     r14, rax
0x180079837  test    rax, rax
0x18007983a  jz      loc_180079901
0x180079840  mov     rcx, [rdi+138h]; ho
0x180079847  test    rcx, rcx
0x18007984a  jz      short loc_180079858
0x18007984c  call    cs:__imp_DeleteObject
0x180079853  nop     dword ptr [rax+rax+00h]
0x180079858  mov     r8d, 25h ; '%'
0x18007985e  mov     rdx, r14; void *
0x180079861  mov     rcx, rbp; void *
0x180079864  call    MF_SelectAnyObject
0x180079869  mov     [rdi+138h], r14
0x180079870  test    eax, eax
0x180079872  jz      loc_180079901
0x180079878  mov     edi, [rbx+0CCh]
0x18007987e  mov     [rbx+0CCh], esi
0x180079884  and     esi, 13FFFFFFh
0x18007988a  bt      esi, 18h
0x18007988e  jb      short loc_1800798D9
0x180079890  mov     eax, [rbx+0F0h]
0x180079896  and     al, 11h
0x180079898  cmp     al, 1
0x18007989a  jnz     short loc_1800798D9
0x18007989c  cmp     qword ptr [rbx+0F8h], 0
0x1800798a4  jz      short loc_1800798D9
0x1800798a6  lea     r9, [rsp+68h+arg_10]
0x1800798ae  mov     [rsp+68h+arg_10], 0
0x1800798b9  mov     r8d, esi
0x1800798bc  mov     [rsp+68h+var_48], 1
0x1800798c4  mov     rdx, rbx
0x1800798c7  mov     rcx, rbp
0x1800798ca  call    IcmTranslateCOLORREF
0x1800798cf  test    eax, eax
0x1800798d1  cmovnz  esi, [rsp+68h+arg_10]
0x1800798d9  cmp     esi, [rbx+0C8h]
0x1800798df  jz      short loc_18007991A
0x1800798e1  mov     [rbx+0C8h], esi
0x1800798e7  or      dword ptr [rbx+98h], 2
0x1800798ee  jmp     short loc_18007991A
0x1800798f0  mov     ecx, 6
0x1800798f5  call    cs:__imp_GdiSetLastError
0x1800798fc  nop     dword ptr [rax+rax+00h]
0x180079901  or      eax, 0FFFFFFFFh
0x180079904  jmp     short loc_18007991C
0x180079906  or      edi, 0FFFFFFFFh
0x180079909  mov     ecx, 57h ; 'W'
0x18007990e  call    cs:__imp_GdiSetLastError
0x180079915  nop     dword ptr [rax+rax+00h]
0x18007991a  mov     eax, edi
0x18007991c  mov     rbx, [rsp+68h+arg_0]
0x180079921  mov     rbp, [rsp+68h+arg_8]
0x180079926  add     rsp, 50h
0x18007992a  pop     r14
0x18007992c  pop     rdi
0x18007992d  pop     rsi
0x18007992e  retn
```
