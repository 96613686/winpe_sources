# DoClipRect

- ea: `0x1800c2194`
- end: `0x1800c23fb`
- name: `DoClipRect`
- size: `615`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800c2140`
- `0x1800c320c`
- `0x18013f1f0`
- `0x180140f2c`

## callees

- `0x1800c1bd4`
- `0x1800c2194`
- `0x1800c2404`
- `0x1800c2474`
- `0x1800c3bb8`
- `0x18014201c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2277`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c2277`
- `GDI32!ExcludeClipRect` at `0x1800c23c3`
- `GDI32!ExcludeClipRect` at `0x1800c23c3`
- `GDI32!ExtSelectClipRgn` at `0x1800c2330`
- `GDI32!ExtSelectClipRgn` at `0x1800c2330`
- `GDI32!IntersectClipRect` at `0x1800c23af`
- `GDI32!IntersectClipRect` at `0x1800c23af`
- `GDI32!DeleteObject` at `0x1800c233b`
- `GDI32!DeleteObject` at `0x1800c233b`
- `GDI32!CreateRectRgn` at `0x1800c2315`
- `GDI32!CreateRectRgn` at `0x1800c2315`

## pseudocode

```c
__int64 __fastcall DoClipRect(__int64 a1, int a2, int a3, int a4, int a5, int a6)
{
  int v10; // edx
  int v11; // ecx
  int v12; // esi
  int v13; // ecx
  int bottom; // r8d
  int v15; // r9d
  int i; // edx
  unsigned __int16 v17; // r10
  __int16 v18; // cx
  int v19; // r9d
  __int16 v20; // r8
  int v21; // edx
  HRGN RectRgn; // rax
  HRGN v24; // r12
  int v25; // ebx
  int v26; // eax
  int v27; // [rsp+30h] [rbp-20h] BYREF
  int v28; // [rsp+34h] [rbp-1Ch] BYREF
  int v29; // [rsp+38h] [rbp-18h] BYREF
  int v30; // [rsp+3Ch] [rbp-14h] BYREF
  int v31; // [rsp+40h] [rbp-10h] BYREF
  int v32; // [rsp+44h] [rbp-Ch]
  int v33; // [rsp+48h] [rbp-8h]
  int v34; // [rsp+4Ch] [rbp-4h]

  if ( (unsigned int)bNoDCRgn(a1, 1) )
  {
    RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
    v24 = RectRgn;
    if ( !RectRgn )
      return 0;
    v25 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
    DeleteObject(v24);
    if ( !v25 )
      return 0;
  }
  v10 = a2;
  v27 = a2;
  v11 = a5;
  v28 = a3;
  if ( a2 > a4 )
  {
    v10 = a4;
    a4 = a2;
    v27 = v10;
  }
  if ( a3 > a5 )
  {
    v11 = a3;
    v28 = a5;
    a3 = a5;
  }
  v12 = a4 - 1;
  v31 = v10;
  v13 = v11 - 1;
  v29 = v12;
  v30 = v13;
  v32 = a3;
  v33 = v12;
  v34 = v13;
  if ( !pfnSetVirtualResolution )
  {
    if ( !(unsigned int)bXformWorkhorse(&v31, 2, a1 + 84) )
      return 0;
    v10 = v31;
    v12 = v33;
    if ( v31 > v33 )
    {
      v10 = v33;
      v12 = v31;
    }
    a3 = v32;
    v13 = v34;
    if ( v32 > v34 )
    {
      a3 = v34;
      v13 = v32;
    }
  }
  bottom = v13 + 1;
  v15 = v12 + 1;
  if ( a6 == 29 )
  {
    v26 = ExcludeClipRect(*(HDC *)(a1 + 40), v10, a3, v15, bottom);
  }
  else
  {
    if ( a6 != 30 )
      goto LABEL_9;
    v26 = IntersectClipRect(*(HDC *)(a1 + 40), v10, a3, v15, bottom);
  }
  if ( !v26 )
    return 0;
LABEL_9:
  if ( (*(_BYTE *)(a1 + 4) & 4) != 0 )
    return bDumpDCClipping(a1);
  if ( !(unsigned int)bXformWorkhorse(&v27, 2, a1 + 228) )
    return 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( (unsigned int)(*(&v27 + i) + 0x8000) > 0xFFFF )
    {
      SetLastError(0x216u);
      FixOverflow(&v27);
      FixOverflow(&v28);
      FixOverflow(&v29);
      FixOverflow(&v30);
      break;
    }
  }
  v17 = v27;
  v18 = v29;
  if ( v27 > v29 )
  {
    v17 = v29;
    v18 = v27;
  }
  v19 = v28;
  v20 = v30;
  if ( v28 > v30 )
  {
    v19 = v30;
    v20 = v28;
  }
  if ( a6 == 30 )
    v21 = 1046;
  else
    v21 = 1045;
  return bW16Emit4(a1, v21, v17, v19, v18 + 1, v20 + 1);
}

```

## disassembly

```asm
0x1800c2194  push    rbp
0x1800c2196  push    rbx
0x1800c2197  push    rsi
0x1800c2198  push    rdi
0x1800c2199  push    r12
0x1800c219b  push    r14
0x1800c219d  push    r15
0x1800c219f  mov     rbp, rsp
0x1800c21a2  sub     rsp, 50h
0x1800c21a6  mov     r15d, edx
0x1800c21a9  mov     esi, r9d
0x1800c21ac  mov     edx, 1
0x1800c21b1  mov     edi, r8d
0x1800c21b4  mov     r14, rcx
0x1800c21b7  call    bNoDCRgn
0x1800c21bc  test    eax, eax
0x1800c21be  jnz     loc_1800C2305
0x1800c21c4  mov     eax, [rbp+arg_20]
0x1800c21c7  mov     edx, r15d; left
0x1800c21ca  mov     [rbp+var_20], edx
0x1800c21cd  mov     ecx, eax
0x1800c21cf  mov     [rbp+var_1C], edi
0x1800c21d2  cmp     r15d, esi
0x1800c21d5  jg      loc_1800C234D
0x1800c21db  cmp     edi, eax
0x1800c21dd  jg      loc_1800C235A
0x1800c21e3  dec     esi
0x1800c21e5  mov     [rbp+var_10], edx
0x1800c21e8  dec     ecx
0x1800c21ea  mov     [rbp+var_18], esi
0x1800c21ed  cmp     cs:pfnSetVirtualResolution, 0
0x1800c21f5  mov     r15d, 2
0x1800c21fb  mov     [rbp+var_14], ecx
0x1800c21fe  mov     [rbp+var_C], edi
0x1800c2201  mov     [rbp+var_8], esi
0x1800c2204  mov     [rbp+var_4], ecx
0x1800c2207  jz      loc_1800C2366
0x1800c220d  mov     ebx, [rbp+arg_28]
0x1800c2210  lea     r8d, [rcx+1]
0x1800c2214  mov     ecx, ebx
0x1800c2216  lea     r9d, [rsi+1]; right
0x1800c221a  sub     ecx, 1Dh
0x1800c221d  jz      loc_1800C23B7
0x1800c2223  cmp     ecx, 1
0x1800c2226  jz      loc_1800C23A3
0x1800c222c  test    byte ptr [r14+4], 4
0x1800c2231  jnz     loc_1800C22FB
0x1800c2237  lea     r8, [r14+0E4h]
0x1800c223e  mov     edx, r15d
0x1800c2241  lea     rcx, [rbp+var_20]
0x1800c2245  call    bXformWorkhorse
0x1800c224a  test    eax, eax
0x1800c224c  jz      loc_1800C2349
0x1800c2252  xor     edx, edx
0x1800c2254  cmp     edx, 4
0x1800c2257  jge     short loc_1800C22A1
0x1800c2259  movsxd  rax, edx
0x1800c225c  mov     ecx, [rbp+rax*4+var_20]
0x1800c2260  add     ecx, 8000h
0x1800c2266  cmp     ecx, 0FFFFh
0x1800c226c  ja      short loc_1800C2272
0x1800c226e  inc     edx
0x1800c2270  jmp     short loc_1800C2254
0x1800c2272  mov     ecx, 216h; dwErrCode
0x1800c2277  call    cs:__imp_SetLastError
0x1800c227d  lea     rcx, [rbp+var_20]
0x1800c2281  call    FixOverflow
0x1800c2286  lea     rcx, [rbp+var_1C]
0x1800c228a  call    FixOverflow
0x1800c228f  lea     rcx, [rbp+var_18]
0x1800c2293  call    FixOverflow
0x1800c2298  lea     rcx, [rbp+var_14]
0x1800c229c  call    FixOverflow
0x1800c22a1  mov     r10d, [rbp+var_20]
0x1800c22a5  mov     ecx, [rbp+var_18]
0x1800c22a8  cmp     r10d, ecx
0x1800c22ab  jg      loc_1800C23D6
0x1800c22b1  mov     r9d, [rbp+var_1C]
0x1800c22b5  mov     r8d, [rbp+var_14]
0x1800c22b9  cmp     r9d, r8d
0x1800c22bc  jg      loc_1800C23E3
0x1800c22c2  inc     r8d
0x1800c22c5  inc     ecx
0x1800c22c7  mov     [rsp+50h+var_28], r8w
0x1800c22cd  movzx   r8d, r10w
0x1800c22d1  mov     word ptr [rsp+50h+bottom], cx
0x1800c22d6  mov     rcx, r14
0x1800c22d9  cmp     ebx, 1Eh
0x1800c22dc  jnz     loc_1800C23F1
0x1800c22e2  mov     edx, 416h
0x1800c22e7  call    bW16Emit4
0x1800c22ec  add     rsp, 50h
0x1800c22f0  pop     r15
0x1800c22f2  pop     r14
0x1800c22f4  pop     r12
0x1800c22f6  pop     rdi
0x1800c22f7  pop     rsi
0x1800c22f8  pop     rbx
0x1800c22f9  pop     rbp
0x1800c22fa  retn
0x1800c22fb  mov     rcx, r14
0x1800c22fe  call    bDumpDCClipping
0x1800c2303  jmp     short loc_1800C22EC
0x1800c2305  mov     r8d, 7FFFh; x2
0x1800c230b  mov     ecx, 0FFFF8000h; x1
0x1800c2310  mov     r9d, r8d; y2
0x1800c2313  mov     edx, ecx; y1
0x1800c2315  call    cs:__imp_CreateRectRgn
0x1800c231b  mov     r12, rax
0x1800c231e  test    rax, rax
0x1800c2321  jz      short loc_1800C2349
0x1800c2323  mov     rcx, [r14+28h]; hdc
0x1800c2327  mov     r8d, 5; mode
0x1800c232d  mov     rdx, rax; hrgn
0x1800c2330  call    cs:__imp_ExtSelectClipRgn
0x1800c2336  mov     rcx, r12; ho
0x1800c2339  mov     ebx, eax
0x1800c233b  call    cs:__imp_DeleteObject
0x1800c2341  test    ebx, ebx
0x1800c2343  jnz     loc_1800C21C4
0x1800c2349  xor     eax, eax
0x1800c234b  jmp     short loc_1800C22EC
0x1800c234d  mov     edx, esi
0x1800c234f  mov     esi, r15d
0x1800c2352  mov     [rbp+var_20], edx
0x1800c2355  jmp     loc_1800C21DB
0x1800c235a  mov     ecx, edi
0x1800c235c  mov     [rbp+var_1C], eax
0x1800c235f  mov     edi, eax
0x1800c2361  jmp     loc_1800C21E3
0x1800c2366  lea     r8, [r14+54h]
0x1800c236a  mov     edx, r15d
0x1800c236d  lea     rcx, [rbp+var_10]
0x1800c2371  call    bXformWorkhorse
0x1800c2376  test    eax, eax
0x1800c2378  jz      short loc_1800C2349
0x1800c237a  mov     edx, [rbp+var_10]
0x1800c237d  mov     esi, [rbp+var_8]
0x1800c2380  cmp     edx, esi
0x1800c2382  jle     short loc_1800C238A
0x1800c2384  mov     eax, edx
0x1800c2386  mov     edx, esi
0x1800c2388  mov     esi, eax
0x1800c238a  mov     edi, [rbp+var_C]
0x1800c238d  mov     ecx, [rbp+var_4]
0x1800c2390  cmp     edi, ecx
0x1800c2392  jle     loc_1800C220D
0x1800c2398  mov     eax, edi
0x1800c239a  mov     edi, ecx
0x1800c239c  mov     ecx, eax
0x1800c239e  jmp     loc_1800C220D
0x1800c23a3  mov     rcx, [r14+28h]; hdc
0x1800c23a7  mov     [rsp+50h+bottom], r8d; bottom
0x1800c23ac  mov     r8d, edi; top
0x1800c23af  call    cs:__imp_IntersectClipRect
0x1800c23b5  jmp     short loc_1800C23C9
0x1800c23b7  mov     rcx, [r14+28h]; hdc
0x1800c23bb  mov     [rsp+50h+bottom], r8d; bottom
0x1800c23c0  mov     r8d, edi; top
0x1800c23c3  call    cs:__imp_ExcludeClipRect
0x1800c23c9  test    eax, eax
0x1800c23cb  jz      loc_1800C2349
0x1800c23d1  jmp     loc_1800C222C
0x1800c23d6  mov     eax, r10d
0x1800c23d9  mov     r10d, ecx
0x1800c23dc  mov     ecx, eax
0x1800c23de  jmp     loc_1800C22B1
0x1800c23e3  mov     eax, r9d
0x1800c23e6  mov     r9d, r8d
0x1800c23e9  mov     r8d, eax
0x1800c23ec  jmp     loc_1800C22C2
0x1800c23f1  mov     edx, 415h
0x1800c23f6  jmp     loc_1800C22E7
```
