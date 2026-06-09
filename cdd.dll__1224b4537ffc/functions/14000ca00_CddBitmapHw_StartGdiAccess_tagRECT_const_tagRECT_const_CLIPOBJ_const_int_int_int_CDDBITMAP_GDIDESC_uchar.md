# CddBitmapHw::StartGdiAccess(tagRECT const *,tagRECT const *,_CLIPOBJ const *,int,int,int *,CDDBITMAP_GDIDESC *,uchar)

- ea: `0x14000ca00`
- end: `0x14000cb3d`
- name: `?StartGdiAccess@CddBitmapHw@@UEAAJPEBUtagRECT@@0PEBU_CLIPOBJ@@HHPEAHPEAUCDDBITMAP_GDIDESC@@E@Z`
- size: `317`
- prototype: `int(CddBitmapHw *__hidden this, const struct tagRECT *, const struct tagRECT *, const struct _CLIPOBJ *, int, int, int *, struct CDDBITMAP_GDIDESC *, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000be40`
- `0x14000c33c`
- `0x14000ca00`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000cadc`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000cadc`
- `watchdog!WdLogSingleEntry0` at `0x14000cac7`
- `watchdog!WdLogSingleEntry0` at `0x14000cac7`

## pseudocode

```c
__int64 __fastcall CddBitmapHw::StartGdiAccess(
        CddBitmapHw *this,
        const struct tagRECT *a2,
        const struct tagRECT *a3,
        const struct _CLIPOBJ *a4,
        int a5,
        int a6,
        int *a7,
        struct CDDBITMAP_GDIDESC *a8,
        unsigned __int8 a9)
{
  __int64 v10; // rcx
  CStagingPool *v14; // rcx
  LONG right; // edx
  LONG bottom; // r8d
  int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  CStagingPool *v21; // rcx

  v10 = *((_QWORD *)this + 1);
  if ( a6 )
    v14 = *(CStagingPool **)(v10 + 7136);
  else
    v14 = (CStagingPool *)(v10 + 5504);
  *((_QWORD *)a8 + 7) = v14;
  if ( a5 )
  {
    right = *((_DWORD *)this + 4);
    bottom = *((_DWORD *)this + 5);
  }
  else
  {
    right = a2->right;
    bottom = a2->bottom;
  }
  if ( (int)CStagingPool::GetGdiSurface(v14, right, bottom, a2, a8, a9) >= 0 )
  {
    if ( a6 && *((_DWORD *)this + 10) )
    {
      v17 = (*(__int64 (__fastcall **)(CddBitmapHw *, struct CDDBITMAP_GDIDESC *, const struct tagRECT *, const struct tagRECT *, const struct _CLIPOBJ *, int *))(*(_QWORD *)this + 144LL))(
              this,
              a8,
              a3,
              a2,
              a4,
              a7);
    }
    else
    {
      v17 = 0;
      if ( *((_DWORD *)a8 + 8) )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 81;
        v20 = (_QWORD *)WdLogNewEntry5_WdAssertion(v19, v18);
        v20[3] = gCddImageInfo;
        v20[4] = (unsigned int)dword_14003E570;
        v20[5] = 215857758;
        WdLogGlobalForLineNumber = 81;
      }
    }
    v21 = (CStagingPool *)*((_QWORD *)a8 + 7);
    if ( *((_DWORD *)v21 + 2) && *((_DWORD *)a8 + 4) && v17 >= 0 )
      return 0;
    CStagingPool::ReleaseGdiSurface(v21, a8);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14000ca00  push    rbx
0x14000ca02  push    rsi
0x14000ca03  push    rdi
0x14000ca04  push    r14
0x14000ca06  push    r15
0x14000ca08  sub     rsp, 40h
0x14000ca0c  cmp     [rsp+68h+arg_28], 0
0x14000ca14  mov     rdi, rcx
0x14000ca17  mov     rcx, [rcx+8]
0x14000ca1b  mov     r14, r9
0x14000ca1e  mov     r15, r8
0x14000ca21  mov     rsi, rdx
0x14000ca24  jz      short loc_14000CA2F
0x14000ca26  mov     rcx, [rcx+1BE0h]
0x14000ca2d  jmp     short loc_14000CA36
0x14000ca2f  add     rcx, 1580h; this
0x14000ca36  cmp     [rsp+68h+arg_20], 0
0x14000ca3e  mov     rbx, [rsp+68h+arg_38]
0x14000ca46  mov     [rbx+38h], rcx
0x14000ca4a  jz      short loc_14000CA55
0x14000ca4c  mov     edx, [rdi+10h]
0x14000ca4f  mov     r8d, [rdi+14h]
0x14000ca53  jmp     short loc_14000CA5C
0x14000ca55  mov     edx, [rdx+8]; int
0x14000ca58  mov     r8d, [rsi+0Ch]; int
0x14000ca5c  mov     al, [rsp+68h+arg_40]
0x14000ca63  mov     r9, rsi; struct tagRECT *
0x14000ca66  mov     [rsp+68h+var_40], al; unsigned __int8
0x14000ca6a  mov     [rsp+68h+var_48], rbx; struct CDDBITMAP_GDIDESC *
0x14000ca6f  call    ?GetGdiSurface@CStagingPool@@QEAAJHHPEBUtagRECT@@PEAUCDDBITMAP_GDIDESC@@E@Z; CStagingPool::GetGdiSurface(int,int,tagRECT const *,CDDBITMAP_GDIDESC *,uchar)
0x14000ca74  test    eax, eax
0x14000ca76  js      loc_14000CB2B
0x14000ca7c  cmp     [rsp+68h+arg_28], 0
0x14000ca84  jz      short loc_14000CABD
0x14000ca86  cmp     dword ptr [rdi+28h], 0
0x14000ca8a  jz      short loc_14000CABD
0x14000ca8c  mov     rax, [rdi]
0x14000ca8f  mov     r9, rsi
0x14000ca92  mov     rcx, [rsp+68h+arg_30]
0x14000ca9a  mov     r8, r15
0x14000ca9d  mov     qword ptr [rsp+68h+var_40], rcx
0x14000caa2  mov     rdx, rbx
0x14000caa5  mov     rcx, rdi
0x14000caa8  mov     [rsp+68h+var_48], r14
0x14000caad  mov     rax, [rax+90h]
0x14000cab4  call    _guard_dispatch_icall
0x14000cab9  mov     edi, eax
0x14000cabb  jmp     short loc_14000CB0B
0x14000cabd  xor     edi, edi
0x14000cabf  cmp     [rbx+20h], edi
0x14000cac2  jz      short loc_14000CB0B
0x14000cac4  lea     ecx, [rdi+1]
0x14000cac7  call    cs:__imp_WdLogSingleEntry0
0x14000cace  nop     dword ptr [rax+rax+00h]
0x14000cad3  lea     esi, [rdi+51h]
0x14000cad6  mov     cs:WdLogGlobalForLineNumber, esi
0x14000cadc  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14000cae3  nop     dword ptr [rax+rax+00h]
0x14000cae8  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000caef  mov     [rax+18h], rcx
0x14000caf3  mov     ecx, cs:dword_14003E570
0x14000caf9  mov     [rax+20h], rcx
0x14000cafd  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000cb05  mov     cs:WdLogGlobalForLineNumber, esi
0x14000cb0b  mov     rcx, [rbx+38h]; this
0x14000cb0f  cmp     dword ptr [rcx+8], 0
0x14000cb13  jz      short loc_14000CB23
0x14000cb15  cmp     dword ptr [rbx+10h], 0
0x14000cb19  jz      short loc_14000CB23
0x14000cb1b  test    edi, edi
0x14000cb1d  js      short loc_14000CB23
0x14000cb1f  xor     eax, eax
0x14000cb21  jmp     short loc_14000CB30
0x14000cb23  mov     rdx, rbx; struct CDDBITMAP_GDIDESC *
0x14000cb26  call    ?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z; CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)
0x14000cb2b  mov     eax, 0C0000001h
0x14000cb30  add     rsp, 40h
0x14000cb34  pop     r15
0x14000cb36  pop     r14
0x14000cb38  pop     rdi
0x14000cb39  pop     rsi
0x14000cb3a  pop     rbx
0x14000cb3b  retn
```
