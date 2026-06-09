# CddBitmapHw::StartGdiAccessNoUpdate(tagRECT const *,int,CDDBITMAP_GDIDESC *)

- ea: `0x14000c2e0`
- end: `0x14000c333`
- name: `?StartGdiAccessNoUpdate@CddBitmapHw@@UEAAJPEBUtagRECT@@HPEAUCDDBITMAP_GDIDESC@@@Z`
- size: `83`
- prototype: `int(CddBitmapHw *__hidden this, const struct tagRECT *, int, struct CDDBITMAP_GDIDESC *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x14000c2e0`
- `0x14000c33c`

## pseudocode

```c
__int64 __fastcall CddBitmapHw::StartGdiAccessNoUpdate(
        CddBitmapHw *this,
        const struct tagRECT *a2,
        int a3,
        struct CDDBITMAP_GDIDESC *a4)
{
  CStagingPool *v5; // rax
  LONG right; // edx
  LONG bottom; // r8d
  int GdiSurface; // eax
  unsigned int v9; // ecx

  v5 = (CStagingPool *)(*((_QWORD *)this + 1) + 5504LL);
  *((_QWORD *)a4 + 7) = v5;
  if ( a3 )
  {
    right = *((_DWORD *)this + 4);
    bottom = *((_DWORD *)this + 5);
  }
  else
  {
    right = a2->right;
    bottom = a2->bottom;
  }
  GdiSurface = CStagingPool::GetGdiSurface(v5, right, bottom, a2, a4, 1u);
  v9 = 0;
  if ( GdiSurface < 0 )
    return (unsigned int)-1073741823;
  return v9;
}

```

## disassembly

```asm
0x14000c2e0  sub     rsp, 38h
0x14000c2e4  mov     rax, [rcx+8]
0x14000c2e8  mov     r10, rdx
0x14000c2eb  add     rax, 1580h
0x14000c2f1  mov     [r9+38h], rax
0x14000c2f5  test    r8d, r8d
0x14000c2f8  jz      short loc_14000C32A
0x14000c2fa  mov     edx, [rcx+10h]; int
0x14000c2fd  mov     r8d, [rcx+14h]; int
0x14000c301  mov     [rsp+38h+var_10], 1; unsigned __int8
0x14000c306  mov     rcx, rax; this
0x14000c309  mov     [rsp+38h+var_18], r9; struct CDDBITMAP_GDIDESC *
0x14000c30e  mov     r9, r10; struct tagRECT *
0x14000c311  call    ?GetGdiSurface@CStagingPool@@QEAAJHHPEBUtagRECT@@PEAUCDDBITMAP_GDIDESC@@E@Z; CStagingPool::GetGdiSurface(int,int,tagRECT const *,CDDBITMAP_GDIDESC *,uchar)
0x14000c316  xor     ecx, ecx
0x14000c318  mov     edx, 0C0000001h
0x14000c31d  test    eax, eax
0x14000c31f  cmovs   ecx, edx
0x14000c322  mov     eax, ecx
0x14000c324  add     rsp, 38h
0x14000c328  retn
0x14000c32a  mov     edx, [rdx+8]
0x14000c32d  mov     r8d, [r10+0Ch]
0x14000c331  jmp     short loc_14000C301
```
