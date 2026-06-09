# CreateCompatibleBitmap

- ea: `0x18001da40`
- end: `0x18001dbe8`
- name: `CreateCompatibleBitmap`
- size: `424`
- prototype: `HBITMAP __stdcall(HDC hdc, int cx, int cy)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001de14`
- `0x180020a00`
- `0x1800858e0`
- `0x18008e84c`

## callees

- `0x18000d6c0`
- `0x18000e5a0`
- `0x18001da40`
- `0x180025090`
- `0x180026790`
- `0x180026cf0`
- `0x18003a970`
- `0x180052830`
- `0x1800710c4`
- `0x18007ac50`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18001da9a`
- `GDI32!GdiGetEntry` at `0x18001da9a`
- `GDI32!gW32PID` at `0x18001dad2`
- `GDI32!gCookie` at `0x18001daf6`
- `GDI32!gMaxGdiHandleCount` at `0x18001da75`
- `win32u!NtGdiCreateCompatibleBitmap` at `0x18001dba8`
- `win32u!NtGdiCreateCompatibleBitmap` at `0x18001dba8`

## pseudocode

```c
HBITMAP __stdcall CreateCompatibleBitmap(HDC hdc, int cx, int cy)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  void *DCObject; // rax
  HDC CompatibleBitmap; // rax
  const BITMAPINFOHEADER *v11; // rdx
  DWORD v12; // r8d
  const void *v13; // r9
  __int128 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-C0h]
  _BYTE pv[18]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v17; // [rsp+62h] [rbp-9Eh]
  BITMAPINFO pbmi; // [rsp+70h] [rbp-90h] BYREF

  v6 = HANDLE_TO_INDEX(hdc);
  if ( v6 >= gMaxGdiHandleCount )
    return 0;
  v15 = 0;
  v14 = 0;
  if ( (int)GdiGetEntry(v6, &v14) < 0 )
    return 0;
  if ( BYTE14(v14) != 1 )
    return 0;
  if ( WORD6(v14) != WORD1(hdc) )
    return 0;
  if ( (DWORD2(v14) & 0xFFFFFFFE) != gW32PID )
    return 0;
  if ( !v15 )
    return 0;
  v7 = __ROR8__(v15, 64 - (gCookie & 0x3Fu));
  if ( v7 == gCookie )
    return 0;
  if ( !cx || !cy )
    return (HBITMAP)GetStockObject(21);
  if ( !(unsigned int)bDIBSectionSelected(v7 ^ gCookie) )
  {
    CompatibleBitmap = (HDC)NtGdiCreateCompatibleBitmap(hdc, (unsigned int)cx, (unsigned int)cy);
    return GdiTrackHCreate(CompatibleBitmap, v11, v12, v13);
  }
  DCObject = (void *)GetDCObject(hdc, 327680);
  if ( GetObjectA(DCObject, 104, pv) != 104 )
    return 0;
  if ( v17 <= 8u )
    GetDIBColorTable(hdc, 0, 0x100u, pbmi.bmiColors);
  pbmi.bmiHeader.biWidth = cx;
  pbmi.bmiHeader.biHeight = cy;
  return CreateDIBSection(hdc, &pbmi, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x18001da40  mov     [rsp-8+arg_18], rbx
0x18001da45  push    rbp
0x18001da46  push    rsi
0x18001da47  push    rdi
0x18001da48  lea     rbp, [rsp-3D0h]
0x18001da50  sub     rsp, 4D0h
0x18001da57  mov     rax, cs:__security_cookie
0x18001da5e  xor     rax, rsp
0x18001da61  mov     [rbp+3E0h+var_20], rax
0x18001da68  mov     esi, r8d
0x18001da6b  mov     edi, edx
0x18001da6d  mov     rbx, rcx
0x18001da70  call    HANDLE_TO_INDEX
0x18001da75  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18001da7c  cmp     eax, [rcx]
0x18001da7e  jnb     loc_18001DBC4
0x18001da84  xor     ecx, ecx
0x18001da86  lea     rdx, [rsp+4E0h+var_4B0]
0x18001da8b  mov     [rsp+4E0h+var_4A0], rcx
0x18001da90  xorps   xmm0, xmm0
0x18001da93  mov     ecx, eax
0x18001da95  movups  [rsp+4E0h+var_4B0], xmm0
0x18001da9a  call    cs:__imp_GdiGetEntry
0x18001daa0  test    eax, eax
0x18001daa2  js      loc_18001DBC4
0x18001daa8  cmp     byte ptr [rsp+4E0h+var_4B0+0Eh], 1
0x18001daad  jnz     loc_18001DBC4
0x18001dab3  movzx   eax, byte ptr [rsp+4E0h+var_4B0+0Ch]
0x18001dab8  movzx   ecx, byte ptr [rsp+4E0h+var_4B0+0Dh]
0x18001dabd  shl     cx, 8
0x18001dac1  or      cx, ax
0x18001dac4  mov     eax, ebx
0x18001dac6  shr     eax, 10h
0x18001dac9  cmp     cx, ax
0x18001dacc  jnz     loc_18001DBC4
0x18001dad2  mov     rax, cs:__imp_gW32PID
0x18001dad9  mov     ecx, dword ptr [rsp+4E0h+var_4B0+8]
0x18001dadd  and     ecx, 0FFFFFFFEh
0x18001dae0  cmp     ecx, [rax]
0x18001dae2  jnz     loc_18001DBC4
0x18001dae8  mov     rdx, [rsp+4E0h+var_4A0]
0x18001daed  test    rdx, rdx
0x18001daf0  jz      loc_18001DBC4
0x18001daf6  mov     rax, cs:__imp_gCookie
0x18001dafd  mov     ecx, 40h ; '@'
0x18001db02  mov     r8, [rax]
0x18001db05  mov     eax, r8d
0x18001db08  and     eax, 3Fh
0x18001db0b  sub     ecx, eax
0x18001db0d  ror     rdx, cl
0x18001db10  xor     r8, rdx
0x18001db13  jz      loc_18001DBC4
0x18001db19  test    edi, edi
0x18001db1b  jz      loc_18001DBB8
0x18001db21  test    esi, esi
0x18001db23  jz      loc_18001DBB8
0x18001db29  mov     rcx, r8
0x18001db2c  call    bDIBSectionSelected
0x18001db31  mov     rcx, rbx
0x18001db34  test    eax, eax
0x18001db36  jz      short loc_18001DBA3
0x18001db38  mov     edx, 50000h
0x18001db3d  call    GetDCObject
0x18001db42  mov     rcx, rax; h
0x18001db45  lea     r8, [rsp+4E0h+pv]; pv
0x18001db4a  mov     edx, 68h ; 'h'; c
0x18001db4f  call    GetObjectA
0x18001db54  cmp     eax, 68h ; 'h'
0x18001db57  jnz     short loc_18001DBC4
0x18001db59  cmp     [rsp+4E0h+var_47E], 8
0x18001db5f  ja      short loc_18001DB75
0x18001db61  lea     r9, [rbp+3E0h+pbmi.bmiColors]; prgbq
0x18001db65  xor     edx, edx; iStart
0x18001db67  mov     r8d, 100h; cEntries
0x18001db6d  mov     rcx, rbx; hdc
0x18001db70  call    GetDIBColorTable
0x18001db75  mov     [rsp+4E0h+offset], 0; offset
0x18001db7d  lea     rdx, [rsp+4E0h+pbmi]; pbmi
0x18001db82  xor     r9d, r9d; ppvBits
0x18001db85  mov     [rsp+4E0h+hSection], 0; hSection
0x18001db8e  xor     r8d, r8d; usage
0x18001db91  mov     [rsp+4E0h+pbmi.bmiHeader.biWidth], edi
0x18001db95  mov     rcx, rbx; hdc
0x18001db98  mov     [rsp+4E0h+pbmi.bmiHeader.biHeight], esi
0x18001db9c  call    CreateDIBSection
0x18001dba1  jmp     short loc_18001DBC6
0x18001dba3  mov     r8d, esi
0x18001dba6  mov     edx, edi
0x18001dba8  call    cs:__imp_NtGdiCreateCompatibleBitmap
0x18001dbae  mov     rcx, rax
0x18001dbb1  call    GdiTrackHCreate
0x18001dbb6  jmp     short loc_18001DBC6
0x18001dbb8  mov     ecx, 15h; i
0x18001dbbd  call    GetStockObject
0x18001dbc2  jmp     short loc_18001DBC6
0x18001dbc4  xor     eax, eax
0x18001dbc6  mov     rcx, [rbp+3E0h+var_20]
0x18001dbcd  xor     rcx, rsp; StackCookie
0x18001dbd0  call    __security_check_cookie
0x18001dbd5  mov     rbx, [rsp+4E0h+arg_18]
0x18001dbdd  add     rsp, 4D0h
0x18001dbe4  pop     rdi
0x18001dbe5  pop     rsi
0x18001dbe6  pop     rbp
0x18001dbe7  retn
```
