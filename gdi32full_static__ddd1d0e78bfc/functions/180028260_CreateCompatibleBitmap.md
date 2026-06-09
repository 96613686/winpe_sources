# CreateCompatibleBitmap

- ea: `0x180028260`
- end: `0x180028415`
- name: `CreateCompatibleBitmap`
- size: `437`
- prototype: `HBITMAP __stdcall(HDC hdc, int cx, int cy)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001eb10`
- `0x180029730`
- `0x18008ab10`
- `0x180094210`

## callees

- `0x180004c00`
- `0x180006a28`
- `0x180028260`
- `0x18002e130`
- `0x18002f7e0`
- `0x18002fda0`
- `0x1800446d0`
- `0x1800583e0`
- `0x1800756cc`
- `0x18007f800`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x1800282ba`
- `GDI32!GdiGetEntry` at `0x1800282ba`
- `GDI32!gW32PID` at `0x1800282f8`
- `GDI32!gCookie` at `0x18002831c`
- `GDI32!gMaxGdiHandleCount` at `0x180028295`
- `win32u!NtGdiCreateCompatibleBitmap` at `0x1800283ce`
- `win32u!NtGdiCreateCompatibleBitmap` at `0x1800283ce`

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
0x180028260  mov     [rsp-8+arg_18], rbx
0x180028265  push    rbp
0x180028266  push    rsi
0x180028267  push    rdi
0x180028268  lea     rbp, [rsp-3D0h]
0x180028270  sub     rsp, 4D0h
0x180028277  mov     rax, cs:__security_cookie
0x18002827e  xor     rax, rsp
0x180028281  mov     [rbp+3E0h+var_20], rax
0x180028288  mov     esi, r8d
0x18002828b  mov     edi, edx
0x18002828d  mov     rbx, rcx
0x180028290  call    HANDLE_TO_INDEX
0x180028295  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18002829c  cmp     eax, [rcx]
0x18002829e  jnb     loc_1800283F0
0x1800282a4  xor     ecx, ecx
0x1800282a6  lea     rdx, [rsp+4E0h+var_4B0]
0x1800282ab  mov     [rsp+4E0h+var_4A0], rcx
0x1800282b0  xorps   xmm0, xmm0
0x1800282b3  mov     ecx, eax
0x1800282b5  movups  [rsp+4E0h+var_4B0], xmm0
0x1800282ba  call    cs:__imp_GdiGetEntry
0x1800282c1  nop     dword ptr [rax+rax+00h]
0x1800282c6  test    eax, eax
0x1800282c8  js      loc_1800283F0
0x1800282ce  cmp     byte ptr [rsp+4E0h+var_4B0+0Eh], 1
0x1800282d3  jnz     loc_1800283F0
0x1800282d9  movzx   eax, byte ptr [rsp+4E0h+var_4B0+0Ch]
0x1800282de  movzx   ecx, byte ptr [rsp+4E0h+var_4B0+0Dh]
0x1800282e3  shl     cx, 8
0x1800282e7  or      cx, ax
0x1800282ea  mov     eax, ebx
0x1800282ec  shr     eax, 10h
0x1800282ef  cmp     cx, ax
0x1800282f2  jnz     loc_1800283F0
0x1800282f8  mov     rax, cs:__imp_gW32PID
0x1800282ff  mov     ecx, dword ptr [rsp+4E0h+var_4B0+8]
0x180028303  and     ecx, 0FFFFFFFEh
0x180028306  cmp     ecx, [rax]
0x180028308  jnz     loc_1800283F0
0x18002830e  mov     rdx, [rsp+4E0h+var_4A0]
0x180028313  test    rdx, rdx
0x180028316  jz      loc_1800283F0
0x18002831c  mov     rax, cs:__imp_gCookie
0x180028323  mov     ecx, 40h ; '@'
0x180028328  mov     r8, [rax]
0x18002832b  mov     eax, r8d
0x18002832e  and     eax, 3Fh
0x180028331  sub     ecx, eax
0x180028333  ror     rdx, cl
0x180028336  xor     r8, rdx
0x180028339  jz      loc_1800283F0
0x18002833f  test    edi, edi
0x180028341  jz      loc_1800283E4
0x180028347  test    esi, esi
0x180028349  jz      loc_1800283E4
0x18002834f  mov     rcx, r8
0x180028352  call    bDIBSectionSelected
0x180028357  mov     rcx, rbx
0x18002835a  test    eax, eax
0x18002835c  jz      short loc_1800283C9
0x18002835e  mov     edx, 50000h
0x180028363  call    GetDCObject
0x180028368  mov     rcx, rax; h
0x18002836b  lea     r8, [rsp+4E0h+pv]; pv
0x180028370  mov     edx, 68h ; 'h'; c
0x180028375  call    GetObjectA
0x18002837a  cmp     eax, 68h ; 'h'
0x18002837d  jnz     short loc_1800283F0
0x18002837f  cmp     [rsp+4E0h+var_47E], 8
0x180028385  ja      short loc_18002839B
0x180028387  lea     r9, [rbp+3E0h+pbmi.bmiColors]; prgbq
0x18002838b  xor     edx, edx; iStart
0x18002838d  mov     r8d, 100h; cEntries
0x180028393  mov     rcx, rbx; hdc
0x180028396  call    GetDIBColorTable
0x18002839b  mov     [rsp+4E0h+offset], 0; offset
0x1800283a3  lea     rdx, [rsp+4E0h+pbmi]; pbmi
0x1800283a8  xor     r9d, r9d; ppvBits
0x1800283ab  mov     [rsp+4E0h+hSection], 0; hSection
0x1800283b4  xor     r8d, r8d; usage
0x1800283b7  mov     [rsp+4E0h+pbmi.bmiHeader.biWidth], edi
0x1800283bb  mov     rcx, rbx; hdc
0x1800283be  mov     [rsp+4E0h+pbmi.bmiHeader.biHeight], esi
0x1800283c2  call    CreateDIBSection
0x1800283c7  jmp     short loc_1800283F2
0x1800283c9  mov     r8d, esi
0x1800283cc  mov     edx, edi
0x1800283ce  call    cs:__imp_NtGdiCreateCompatibleBitmap
0x1800283d5  nop     dword ptr [rax+rax+00h]
0x1800283da  mov     rcx, rax
0x1800283dd  call    GdiTrackHCreate
0x1800283e2  jmp     short loc_1800283F2
0x1800283e4  mov     ecx, 15h; i
0x1800283e9  call    GetStockObject
0x1800283ee  jmp     short loc_1800283F2
0x1800283f0  xor     eax, eax
0x1800283f2  mov     rcx, [rbp+3E0h+var_20]
0x1800283f9  xor     rcx, rsp; StackCookie
0x1800283fc  call    __security_check_cookie
0x180028401  mov     rbx, [rsp+4E0h+arg_18]
0x180028409  add     rsp, 4D0h
0x180028410  pop     rdi
0x180028411  pop     rsi
0x180028412  pop     rbp
0x180028413  retn
```
