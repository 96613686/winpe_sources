# MirrorRgnByWidth(HRGN__ *,int,HRGN__ * *)

- ea: `0x1800609bc`
- end: `0x180060ac1`
- name: `?MirrorRgnByWidth@@YAHPEAUHRGN__@@HPEAPEAU1@@Z`
- size: `261`
- prototype: `__int64 __fastcall(HRGN hrgnDst, int, HRGN *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003baec`
- `0x180060960`

## callees

- `0x1800609bc`
- `0x180086300`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800609f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800609f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060aac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180060aac`
- `GDI32!GetRegionData` at `0x1800609d9`
- `GDI32!GetRegionData` at `0x180060a0d`
- `GDI32!GetRegionData` at `0x1800609d9`
- `GDI32!GetRegionData` at `0x180060a0d`
- `GDI32!DeleteObject` at `0x180060a99`
- `GDI32!DeleteObject` at `0x180060a99`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x180060a90`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x180060a90`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180060a70`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180060a70`

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
0x1800609bc  push    rbx
0x1800609be  push    rbp
0x1800609bf  push    rsi
0x1800609c0  push    rdi
0x1800609c1  push    r14
0x1800609c3  push    r15
0x1800609c5  sub     rsp, 28h
0x1800609c9  mov     r14, r8
0x1800609cc  mov     r15d, edx
0x1800609cf  xor     r8d, r8d; lpRgnData
0x1800609d2  xor     edx, edx; nCount
0x1800609d4  mov     rbp, rcx
0x1800609d7  xor     esi, esi
0x1800609d9  call    cs:__imp_GetRegionData
0x1800609df  movsxd  rdi, eax
0x1800609e2  test    eax, eax
0x1800609e4  jz      loc_180060AB2
0x1800609ea  mov     rdx, rdi
0x1800609ed  xor     ecx, ecx; uFlags
0x1800609ef  shl     rdx, 2; uBytes
0x1800609f3  call    cs:__imp_LocalAlloc
0x1800609f9  mov     rbx, rax
0x1800609fc  test    rax, rax
0x1800609ff  jz      loc_180060AB2
0x180060a05  mov     r8, rax; lpRgnData
0x180060a08  mov     edx, edi; nCount
0x180060a0a  mov     rcx, rbp; hrgn
0x180060a0d  call    cs:__imp_GetRegionData
0x180060a13  test    eax, eax
0x180060a15  jz      loc_180060AA9
0x180060a1b  mov     ecx, [rbx+10h]
0x180060a1e  lea     r9, [rbx+20h]
0x180060a22  mov     edx, [rbx+8]; int
0x180060a25  mov     eax, r15d
0x180060a28  sub     eax, [rbx+18h]
0x180060a2b  xor     r10d, r10d
0x180060a2e  mov     [rbx+10h], eax
0x180060a31  mov     eax, r15d
0x180060a34  sub     eax, ecx
0x180060a36  mov     [rbx+18h], eax
0x180060a39  test    edx, edx
0x180060a3b  jle     short loc_180060A60
0x180060a3d  mov     r8d, [r9]
0x180060a40  mov     eax, r15d
0x180060a43  sub     eax, [r9+8]
0x180060a47  inc     r10d
0x180060a4a  mov     [r9], eax
0x180060a4d  mov     eax, r15d
0x180060a50  sub     eax, r8d
0x180060a53  mov     [r9+8], eax
0x180060a57  lea     r9, [r9+10h]
0x180060a5b  cmp     r10d, edx
0x180060a5e  jl      short loc_180060A3D
0x180060a60  lea     rcx, [rbx+20h]; struct tagRECT *
0x180060a64  call    ?OrderRects@@YAXPEAUtagRECT@@H@Z; OrderRects(tagRECT *,int)
0x180060a69  mov     r8, rbx; lpData
0x180060a6c  mov     edx, edi; nCount
0x180060a6e  xor     ecx, ecx; lpx
0x180060a70  call    cs:__imp_ExtCreateRegion
0x180060a76  mov     rdi, rax
0x180060a79  test    rax, rax
0x180060a7c  jz      short loc_180060AA9
0x180060a7e  test    r14, r14
0x180060a81  jnz     short loc_180060AA1
0x180060a83  lea     r9d, [r14+5]; iMode
0x180060a87  xor     r8d, r8d; hrgnSrc2
0x180060a8a  mov     rdx, rax; hrgnSrc1
0x180060a8d  mov     rcx, rbp; hrgnDst
0x180060a90  call    cs:__imp_CombineRgn
0x180060a96  mov     rcx, rdi; ho
0x180060a99  call    cs:__imp_DeleteObject
0x180060a9f  jmp     short loc_180060AA4
0x180060aa1  mov     [r14], rdi
0x180060aa4  mov     esi, 1
0x180060aa9  mov     rcx, rbx; hMem
0x180060aac  call    cs:__imp_LocalFree
0x180060ab2  mov     eax, esi
0x180060ab4  add     rsp, 28h
0x180060ab8  pop     r15
0x180060aba  pop     r14
0x180060abc  pop     rdi
0x180060abd  pop     rsi
0x180060abe  pop     rbp
0x180060abf  pop     rbx
0x180060ac0  retn
```
