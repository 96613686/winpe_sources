# DirectUI::FlipRgn(HRGN__ *,tagRECT const *)

- ea: `0x180177ed4`
- end: `0x18017803a`
- name: `?FlipRgn@DirectUI@@YAXPEAUHRGN__@@PEBUtagRECT@@@Z`
- size: `358`
- prototype: `void __fastcall(HRGN hrgnDst, HRGN, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007e778`

## callees

- `0x1800a9f20`
- `0x180114520`
- `0x180177ed4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180177f37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180177f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017801e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18017801e`
- `GDI32!DeleteObject` at `0x18017800b`
- `GDI32!DeleteObject` at `0x18017800b`
- `GDI32!ExtCreateRegion` at `0x180177fe5`
- `GDI32!ExtCreateRegion` at `0x180177fe5`
- `GDI32!GetRegionData` at `0x180177f13`
- `GDI32!GetRegionData` at `0x180177f27`
- `GDI32!GetRegionData` at `0x180177f4d`
- `GDI32!GetRegionData` at `0x180177f13`
- `GDI32!GetRegionData` at `0x180177f27`
- `GDI32!GetRegionData` at `0x180177f4d`
- `GDI32!CombineRgn` at `0x180178002`
- `GDI32!CombineRgn` at `0x180178002`

## pseudocode

```c
void __fastcall DirectUI::FlipRgn(HRGN hrgnDst, _DWORD *a2, const struct tagRECT *a3)
{
  RGNDATA *v4; // rbx
  DWORD RegionData; // edi
  DWORD v7; // eax
  struct _RGNDATA *v8; // rax
  ULONGLONG nCount; // rdx
  ULONGLONG dwSize; // rcx
  char *v11; // r9
  int v12; // r8d
  DWORD i; // r10d
  __int64 v14; // rdx
  int v15; // ecx
  HRGN Region; // rax
  HRGN v17; // rdi
  ULONGLONG pullResult; // [rsp+20h] [rbp-68h] BYREF
  _BYTE RgnData[48]; // [rsp+28h] [rbp-60h] BYREF

  v4 = (RGNDATA *)RgnData;
  memset(RgnData, 0, sizeof(RgnData));
  RegionData = GetRegionData(hrgnDst, 0x30u, (LPRGNDATA)RgnData);
  if ( !RegionData )
  {
    v7 = GetRegionData(hrgnDst, 0, 0);
    RegionData = v7;
    if ( v7 )
    {
      v8 = (struct _RGNDATA *)LocalAlloc(0, v7);
      v4 = v8;
      if ( v8 )
        RegionData = GetRegionData(hrgnDst, RegionData, v8);
    }
  }
  if ( RegionData >= 0x20 && v4->rdh.iType == 1 )
  {
    nCount = v4->rdh.nCount;
    pullResult = 0;
    if ( ULongLongMult(0x10u, nCount, &pullResult) >= 0 )
    {
      dwSize = v4->rdh.dwSize;
      if ( dwSize + pullResult >= dwSize && dwSize + pullResult <= RegionData )
      {
        v11 = (char *)v4 + dwSize;
        v12 = *a2 + a2[2];
        for ( i = 0; i < v4->rdh.nCount; *(_DWORD *)&v11[v14 + 8] = v15 )
        {
          v14 = 16LL * i++;
          v15 = v12 - *(_DWORD *)&v11[v14];
          *(_DWORD *)&v11[v14] = v12 - *(_DWORD *)&v11[v14 + 8];
        }
        Region = ExtCreateRegion(0, RegionData, v4);
        v17 = Region;
        if ( Region )
        {
          CombineRgn(hrgnDst, Region, 0, 5);
          DeleteObject(v17);
        }
      }
    }
  }
  if ( v4 != (RGNDATA *)RgnData )
    LocalFree(v4);
}

```

## disassembly

```asm
0x180177ed4  push    rbx
0x180177ed6  push    rbp
0x180177ed7  push    rsi
0x180177ed8  push    rdi
0x180177ed9  sub     rsp, 68h
0x180177edd  mov     rax, cs:__security_cookie
0x180177ee4  xor     rax, rsp
0x180177ee7  mov     [rsp+88h+var_30], rax
0x180177eec  xorps   xmm0, xmm0
0x180177eef  lea     r8, [rsp+88h+RgnData]; lpRgnData
0x180177ef4  mov     rbp, rdx
0x180177ef7  lea     rbx, [rsp+88h+RgnData]
0x180177efc  mov     edx, 30h ; '0'; nCount
0x180177f01  mov     rsi, rcx
0x180177f04  movups  xmmword ptr [rsp+88h+RgnData], xmm0
0x180177f09  movups  xmmword ptr [rsp+88h+RgnData+10h], xmm0
0x180177f0e  movups  xmmword ptr [rsp+88h+RgnData+20h], xmm0
0x180177f13  call    cs:__imp_GetRegionData
0x180177f19  mov     edi, eax
0x180177f1b  test    eax, eax
0x180177f1d  jnz     short loc_180177F55
0x180177f1f  xor     r8d, r8d; lpRgnData
0x180177f22  xor     edx, edx; nCount
0x180177f24  mov     rcx, rsi; hrgn
0x180177f27  call    cs:__imp_GetRegionData
0x180177f2d  mov     edi, eax
0x180177f2f  test    eax, eax
0x180177f31  jz      short loc_180177F55
0x180177f33  mov     edx, edi; uBytes
0x180177f35  xor     ecx, ecx; uFlags
0x180177f37  call    cs:__imp_LocalAlloc
0x180177f3d  mov     rbx, rax
0x180177f40  test    rax, rax
0x180177f43  jz      short loc_180177F55
0x180177f45  mov     r8, rax; lpRgnData
0x180177f48  mov     edx, edi; nCount
0x180177f4a  mov     rcx, rsi; hrgn
0x180177f4d  call    cs:__imp_GetRegionData
0x180177f53  mov     edi, eax
0x180177f55  cmp     edi, 20h ; ' '
0x180177f58  jb      loc_180178011
0x180177f5e  cmp     dword ptr [rbx+4], 1
0x180177f62  jnz     loc_180178011
0x180177f68  mov     edx, [rbx+8]; ullMultiplier
0x180177f6b  lea     r8, [rsp+88h+pullResult]; pullResult
0x180177f70  mov     ecx, 10h; ullMultiplicand
0x180177f75  mov     [rsp+88h+pullResult], 0
0x180177f7e  call    ULongLongMult
0x180177f83  test    eax, eax
0x180177f85  js      loc_180178011
0x180177f8b  mov     ecx, [rbx]
0x180177f8d  mov     rdx, [rsp+88h+pullResult]
0x180177f92  add     rdx, rcx
0x180177f95  cmp     rdx, rcx
0x180177f98  jb      short loc_180178011
0x180177f9a  mov     eax, edi
0x180177f9c  cmp     rdx, rax
0x180177f9f  ja      short loc_180178011
0x180177fa1  mov     r8d, [rbp+8]
0x180177fa5  lea     r9, [rcx+rbx]
0x180177fa9  add     r8d, [rbp+0]
0x180177fad  xor     r10d, r10d
0x180177fb0  cmp     [rbx+8], r10d
0x180177fb4  jbe     short loc_180177FDE
0x180177fb6  mov     edx, r10d
0x180177fb9  mov     ecx, r8d
0x180177fbc  shl     rdx, 4
0x180177fc0  mov     eax, r8d
0x180177fc3  inc     r10d
0x180177fc6  sub     ecx, [rdx+r9]
0x180177fca  sub     eax, [rdx+r9+8]
0x180177fcf  mov     [rdx+r9], eax
0x180177fd3  mov     [rdx+r9+8], ecx
0x180177fd8  cmp     r10d, [rbx+8]
0x180177fdc  jb      short loc_180177FB6
0x180177fde  mov     r8, rbx; lpData
0x180177fe1  mov     edx, edi; nCount
0x180177fe3  xor     ecx, ecx; lpx
0x180177fe5  call    cs:__imp_ExtCreateRegion
0x180177feb  mov     rdi, rax
0x180177fee  test    rax, rax
0x180177ff1  jz      short loc_180178011
0x180177ff3  mov     r9d, 5; iMode
0x180177ff9  xor     r8d, r8d; hrgnSrc2
0x180177ffc  mov     rdx, rax; hrgnSrc1
0x180177fff  mov     rcx, rsi; hrgnDst
0x180178002  call    cs:__imp_CombineRgn
0x180178008  mov     rcx, rdi; ho
0x18017800b  call    cs:__imp_DeleteObject
0x180178011  lea     rax, [rsp+88h+RgnData]
0x180178016  cmp     rbx, rax
0x180178019  jz      short loc_180178024
0x18017801b  mov     rcx, rbx; hMem
0x18017801e  call    cs:__imp_LocalFree
0x180178024  mov     rcx, [rsp+88h+var_30]
0x180178029  xor     rcx, rsp; StackCookie
0x18017802c  call    __security_check_cookie
0x180178031  add     rsp, 68h
0x180178035  pop     rdi
0x180178036  pop     rsi
0x180178037  pop     rbp
0x180178038  pop     rbx
0x180178039  retn
```
