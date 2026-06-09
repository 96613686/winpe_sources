# CreatePen

- ea: `0x18005fda0`
- end: `0x18005fef8`
- name: `CreatePen`
- size: `344`
- prototype: `HPEN __stdcall(int iStyle, int cWidth, COLORREF color)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180024c40`
- `0x1800479b0`
- `0x18005fcd0`
- `0x18005fd80`
- `0x180079700`

## callees

- `0x18002e130`
- `0x18002fda0`
- `0x18005fda0`
- `0x1800756cc`

## import_xrefs

- `GDI32!hGetPEBHandle` at `0x18005fdf6`
- `GDI32!hGetPEBHandle` at `0x18005fdf6`
- `GDI32!GdiGetEntry` at `0x18005fe3b`
- `GDI32!GdiGetEntry` at `0x18005fe3b`
- `GDI32!gW32PID` at `0x18005fe6d`
- `GDI32!gCookie` at `0x18005fe89`
- `GDI32!gMaxGdiHandleCount` at `0x18005fe16`
- `GDI32!DeleteObject` at `0x18005fec4`
- `GDI32!DeleteObject` at `0x18005fec4`
- `win32u!NtGdiCreatePen` at `0x18005feda`
- `win32u!NtGdiCreatePen` at `0x18005feda`

## pseudocode

```c
HPEN __stdcall CreatePen(int iStyle, int cWidth, COLORREF color)
{
  unsigned int v5; // edi
  __int64 v6; // r9
  __int64 PEBHandle; // rax
  void *v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // r8
  __int64 Pen; // rcx
  __int128 v13; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-38h]

  v5 = iStyle;
  v6 = (unsigned int)iStyle;
  if ( iStyle )
  {
    v6 = (unsigned int)(iStyle - 1);
    if ( iStyle != 1 )
    {
      v6 = (unsigned int)(iStyle - 2);
      if ( iStyle != 2 )
      {
        v6 = (unsigned int)(iStyle - 3);
        if ( iStyle != 3 )
        {
          v6 = (unsigned int)(iStyle - 4);
          if ( iStyle != 4 )
          {
            v6 = (unsigned int)(iStyle - 5);
            if ( iStyle == 5 )
              return (HPEN)GetStockObject(8);
            if ( iStyle != 6 )
              v5 = 0;
          }
        }
      }
    }
  }
  if ( !cWidth && !v5 )
  {
    PEBHandle = hGetPEBHandle(1, 0, color, v6);
    v8 = (void *)PEBHandle;
    if ( PEBHandle )
    {
      v9 = HANDLE_TO_INDEX(PEBHandle);
      if ( v9 < gMaxGdiHandleCount )
      {
        v14 = 0;
        v13 = 0;
        if ( (int)GdiGetEntry(v9, &v13) >= 0
          && BYTE14(v13) == 16
          && WORD6(v13) == WORD1(v8)
          && (DWORD2(v13) & 0xFFFFFFFE) == gW32PID )
        {
          if ( v14 )
          {
            v10 = __ROR8__(v14, 64 - (gCookie & 0x3Fu));
            if ( v10 != gCookie )
            {
              if ( *(_DWORD *)((v10 ^ gCookie) + 4) != color )
              {
                *(_DWORD *)(v10 ^ gCookie) |= 4u;
                *(_DWORD *)((v10 ^ gCookie) + 4) = color;
              }
              Pen = (__int64)v8;
              return (HPEN)GdiTrackHCreate(Pen);
            }
          }
        }
      }
      DeleteObject(v8);
    }
  }
  Pen = NtGdiCreatePen(v5, (unsigned int)cWidth, color, 0);
  return (HPEN)GdiTrackHCreate(Pen);
}

```

## disassembly

```asm
0x18005fda0  push    rbx
0x18005fda2  push    rbp
0x18005fda3  push    rsi
0x18005fda4  push    rdi
0x18005fda5  sub     rsp, 48h
0x18005fda9  mov     esi, r8d
0x18005fdac  mov     ebp, edx
0x18005fdae  mov     edi, ecx
0x18005fdb0  mov     r9d, ecx
0x18005fdb3  test    ecx, ecx
0x18005fdb5  jz      short loc_18005FDE1
0x18005fdb7  sub     r9d, 1
0x18005fdbb  jz      short loc_18005FDE1
0x18005fdbd  sub     r9d, 1
0x18005fdc1  jz      short loc_18005FDE1
0x18005fdc3  sub     r9d, 1
0x18005fdc7  jz      short loc_18005FDE1
0x18005fdc9  sub     r9d, 1
0x18005fdcd  jz      short loc_18005FDE1
0x18005fdcf  sub     r9d, 1
0x18005fdd3  jz      loc_18005FEB5
0x18005fdd9  cmp     r9d, 1
0x18005fddd  jz      short loc_18005FDE1
0x18005fddf  xor     edi, edi
0x18005fde1  test    ebp, ebp
0x18005fde3  jnz     loc_18005FED0
0x18005fde9  test    edi, edi
0x18005fdeb  jnz     loc_18005FED0
0x18005fdf1  xor     edx, edx
0x18005fdf3  lea     ecx, [rbp+1]
0x18005fdf6  call    cs:__imp_hGetPEBHandle
0x18005fdfd  nop     dword ptr [rax+rax+00h]
0x18005fe02  mov     rbx, rax
0x18005fe05  test    rax, rax
0x18005fe08  jz      loc_18005FED0
0x18005fe0e  mov     rcx, rax
0x18005fe11  call    HANDLE_TO_INDEX
0x18005fe16  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18005fe1d  cmp     eax, [rcx]
0x18005fe1f  jnb     loc_18005FEC1
0x18005fe25  xor     ecx, ecx
0x18005fe27  lea     rdx, [rsp+68h+var_48]
0x18005fe2c  mov     [rsp+68h+var_38], rcx
0x18005fe31  xorps   xmm0, xmm0
0x18005fe34  mov     ecx, eax
0x18005fe36  movups  [rsp+68h+var_48], xmm0
0x18005fe3b  call    cs:__imp_GdiGetEntry
0x18005fe42  nop     dword ptr [rax+rax+00h]
0x18005fe47  test    eax, eax
0x18005fe49  js      short loc_18005FEC1
0x18005fe4b  cmp     byte ptr [rsp+68h+var_48+0Eh], 10h
0x18005fe50  jnz     short loc_18005FEC1
0x18005fe52  movzx   eax, byte ptr [rsp+68h+var_48+0Ch]
0x18005fe57  movzx   ecx, byte ptr [rsp+68h+var_48+0Dh]
0x18005fe5c  shl     cx, 8
0x18005fe60  or      cx, ax
0x18005fe63  mov     eax, ebx
0x18005fe65  shr     eax, 10h
0x18005fe68  cmp     cx, ax
0x18005fe6b  jnz     short loc_18005FEC1
0x18005fe6d  mov     rax, cs:__imp_gW32PID
0x18005fe74  mov     ecx, dword ptr [rsp+68h+var_48+8]
0x18005fe78  and     ecx, 0FFFFFFFEh
0x18005fe7b  cmp     ecx, [rax]
0x18005fe7d  jnz     short loc_18005FEC1
0x18005fe7f  mov     r8, [rsp+68h+var_38]
0x18005fe84  test    r8, r8
0x18005fe87  jz      short loc_18005FEC1
0x18005fe89  mov     rax, cs:__imp_gCookie
0x18005fe90  lea     ecx, [rbp+40h]
0x18005fe93  mov     rdx, [rax]
0x18005fe96  mov     eax, edx
0x18005fe98  and     eax, 3Fh
0x18005fe9b  sub     ecx, eax
0x18005fe9d  ror     r8, cl
0x18005fea0  xor     rdx, r8
0x18005fea3  jz      short loc_18005FEC1
0x18005fea5  cmp     [rdx+4], esi
0x18005fea8  jz      short loc_18005FEB0
0x18005feaa  or      dword ptr [rdx], 4
0x18005fead  mov     [rdx+4], esi
0x18005feb0  mov     rcx, rbx
0x18005feb3  jmp     short loc_18005FEE9
0x18005feb5  mov     ecx, 8; i
0x18005feba  call    GetStockObject
0x18005febf  jmp     short loc_18005FEEE
0x18005fec1  mov     rcx, rbx; ho
0x18005fec4  call    cs:__imp_DeleteObject
0x18005fecb  nop     dword ptr [rax+rax+00h]
0x18005fed0  xor     r9d, r9d
0x18005fed3  mov     r8d, esi
0x18005fed6  mov     edx, ebp
0x18005fed8  mov     ecx, edi
0x18005feda  call    cs:__imp_NtGdiCreatePen
0x18005fee1  nop     dword ptr [rax+rax+00h]
0x18005fee6  mov     rcx, rax
0x18005fee9  call    GdiTrackHCreate
0x18005feee  add     rsp, 48h
0x18005fef2  pop     rdi
0x18005fef3  pop     rsi
0x18005fef4  pop     rbp
0x18005fef5  pop     rbx
0x18005fef6  retn
```
