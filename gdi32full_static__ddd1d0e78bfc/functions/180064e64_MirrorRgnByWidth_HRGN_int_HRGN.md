# MirrorRgnByWidth(HRGN__ *,int,HRGN__ * *)

- ea: `0x180064e64`
- end: `0x180064f94`
- name: `?MirrorRgnByWidth@@YAHPEAUHRGN__@@HPEAPEAU1@@Z`
- size: `304`
- prototype: `__int64 __fastcall(HRGN hrgnDst, int, HRGN *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800473e4`
- `0x180064e00`

## callees

- `0x180064e64`
- `0x18008b5f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064ea1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064ea1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064f78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064f78`
- `GDI32!GetRegionData` at `0x180064e81`
- `GDI32!GetRegionData` at `0x180064ec1`
- `GDI32!GetRegionData` at `0x180064e81`
- `GDI32!GetRegionData` at `0x180064ec1`
- `GDI32!DeleteObject` at `0x180064f5f`
- `GDI32!DeleteObject` at `0x180064f5f`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x180064f50`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x180064f50`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180064f2a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180064f2a`

## pseudocode

```c
__int64 __fastcall MirrorRgnByWidth(HRGN hrgnDst, int a2, HRGN *a3)
{
  unsigned int v6; // esi
  signed int RegionData; // eax
  DWORD v8; // edi
  struct _RGNDATA *v9; // rax
  struct _RGNDATA *v10; // rbx
  LONG left; // ecx
  char *Buffer; // r9
  int nCount; // edx
  int v14; // r10d
  int v15; // r8d
  HRGN Region; // rax
  HRGN v17; // rdi

  v6 = 0;
  RegionData = GetRegionData(hrgnDst, 0, 0);
  v8 = RegionData;
  if ( RegionData )
  {
    v9 = (struct _RGNDATA *)LocalAlloc(0, 4LL * RegionData);
    v10 = v9;
    if ( v9 )
    {
      if ( GetRegionData(hrgnDst, v8, v9) )
      {
        left = v10->rdh.rcBound.left;
        Buffer = v10->Buffer;
        nCount = v10->rdh.nCount;
        v14 = 0;
        v10->rdh.rcBound.left = a2 - v10->rdh.rcBound.right;
        for ( v10->rdh.rcBound.right = a2 - left; v14 < nCount; Buffer += 16 )
        {
          v15 = *(_DWORD *)Buffer;
          ++v14;
          *(_DWORD *)Buffer = a2 - *((_DWORD *)Buffer + 2);
          *((_DWORD *)Buffer + 2) = a2 - v15;
        }
        OrderRects((struct tagRECT *)v10->Buffer, nCount);
        Region = ExtCreateRegion(0, v8, v10);
        v17 = Region;
        if ( Region )
        {
          if ( a3 )
          {
            *a3 = Region;
          }
          else
          {
            CombineRgn(hrgnDst, Region, 0, 5);
            DeleteObject(v17);
          }
          v6 = 1;
        }
      }
      LocalFree(v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180064e64  push    rbx
0x180064e66  push    rbp
0x180064e67  push    rsi
0x180064e68  push    rdi
0x180064e69  push    r14
0x180064e6b  push    r15
0x180064e6d  sub     rsp, 28h
0x180064e71  mov     r14, r8
0x180064e74  mov     r15d, edx
0x180064e77  xor     r8d, r8d; lpRgnData
0x180064e7a  xor     edx, edx; nCount
0x180064e7c  mov     rbp, rcx
0x180064e7f  xor     esi, esi
0x180064e81  call    cs:__imp_GetRegionData
0x180064e88  nop     dword ptr [rax+rax+00h]
0x180064e8d  movsxd  rdi, eax
0x180064e90  test    eax, eax
0x180064e92  jz      loc_180064F84
0x180064e98  mov     rdx, rdi
0x180064e9b  xor     ecx, ecx; uFlags
0x180064e9d  shl     rdx, 2; uBytes
0x180064ea1  call    cs:__imp_LocalAlloc
0x180064ea8  nop     dword ptr [rax+rax+00h]
0x180064ead  mov     rbx, rax
0x180064eb0  test    rax, rax
0x180064eb3  jz      loc_180064F84
0x180064eb9  mov     r8, rax; lpRgnData
0x180064ebc  mov     edx, edi; nCount
0x180064ebe  mov     rcx, rbp; hrgn
0x180064ec1  call    cs:__imp_GetRegionData
0x180064ec8  nop     dword ptr [rax+rax+00h]
0x180064ecd  test    eax, eax
0x180064ecf  jz      loc_180064F75
0x180064ed5  mov     ecx, [rbx+10h]
0x180064ed8  lea     r9, [rbx+20h]
0x180064edc  mov     edx, [rbx+8]; int
0x180064edf  mov     eax, r15d
0x180064ee2  sub     eax, [rbx+18h]
0x180064ee5  xor     r10d, r10d
0x180064ee8  mov     [rbx+10h], eax
0x180064eeb  mov     eax, r15d
0x180064eee  sub     eax, ecx
0x180064ef0  mov     [rbx+18h], eax
0x180064ef3  test    edx, edx
0x180064ef5  jle     short loc_180064F1A
0x180064ef7  mov     r8d, [r9]
0x180064efa  mov     eax, r15d
0x180064efd  sub     eax, [r9+8]
0x180064f01  inc     r10d
0x180064f04  mov     [r9], eax
0x180064f07  mov     eax, r15d
0x180064f0a  sub     eax, r8d
0x180064f0d  mov     [r9+8], eax
0x180064f11  lea     r9, [r9+10h]
0x180064f15  cmp     r10d, edx
0x180064f18  jl      short loc_180064EF7
0x180064f1a  lea     rcx, [rbx+20h]; struct tagRECT *
0x180064f1e  call    ?OrderRects@@YAXPEAUtagRECT@@H@Z; OrderRects(tagRECT *,int)
0x180064f23  mov     r8, rbx; lpData
0x180064f26  mov     edx, edi; nCount
0x180064f28  xor     ecx, ecx; lpx
0x180064f2a  call    cs:__imp_ExtCreateRegion
0x180064f31  nop     dword ptr [rax+rax+00h]
0x180064f36  mov     rdi, rax
0x180064f39  test    rax, rax
0x180064f3c  jz      short loc_180064F75
0x180064f3e  test    r14, r14
0x180064f41  jnz     short loc_180064F6D
0x180064f43  lea     r9d, [r14+5]; iMode
0x180064f47  xor     r8d, r8d; hrgnSrc2
0x180064f4a  mov     rdx, rax; hrgnSrc1
0x180064f4d  mov     rcx, rbp; hrgnDst
0x180064f50  call    cs:__imp_CombineRgn
0x180064f57  nop     dword ptr [rax+rax+00h]
0x180064f5c  mov     rcx, rdi; ho
0x180064f5f  call    cs:__imp_DeleteObject
0x180064f66  nop     dword ptr [rax+rax+00h]
0x180064f6b  jmp     short loc_180064F70
0x180064f6d  mov     [r14], rdi
0x180064f70  mov     esi, 1
0x180064f75  mov     rcx, rbx; hMem
0x180064f78  call    cs:__imp_LocalFree
0x180064f7f  nop     dword ptr [rax+rax+00h]
0x180064f84  mov     eax, esi
0x180064f86  add     rsp, 28h
0x180064f8a  pop     r15
0x180064f8c  pop     r14
0x180064f8e  pop     rdi
0x180064f8f  pop     rsi
0x180064f90  pop     rbp
0x180064f91  pop     rbx
0x180064f92  retn
```
