# CDXGISwapChain::ComposePartialPresentation(_D3DKMT_DIRTYREGIONS &,ulong,uint &,uint,tagRECT const *,DXGI_SCROLL_RECT const *)

- ea: `0x180033bd0`
- end: `0x1800346e3`
- name: `?ComposePartialPresentation@CDXGISwapChain@@QEAAJAEAU_D3DKMT_DIRTYREGIONS@@KAEAIIPEBUtagRECT@@PEBUDXGI_SCROLL_RECT@@@Z`
- size: `2835`
- prototype: `__int64 __usercall@<rax>(CDXGISwapChain *__hidden this@<rcx>, struct _D3DKMT_DIRTYREGIONS *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int, const struct tagRECT *, const struct DXGI_SCROLL_RECT *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180008d40`
- `0x1800111c8`

## callees

- `0x18000c6b0`
- `0x18002f830`
- `0x180033bd0`
- `0x1800346f0`
- `0x1800347a0`
- `0x1800347f8`
- `0x1800348c0`
- `0x180075fa0`
- `0x180076f20`
- `0x18007bf63`
- `0x1800cb010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x180034462`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x180034613`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x180034462`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!UnionRect` at `0x180034613`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x180033fe1`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x180034277`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x18003429e`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x180033fe1`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x180034277`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x18003429e`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180033e5a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180033f5a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180034035`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180033e5a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180033f5a`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!SetRectRgn` at `0x180034035`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x1800340ab`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x1800342e2`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x1800340ab`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CombineRgn` at `0x1800342e2`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!EqualRgn` at `0x180033ffa`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!EqualRgn` at `0x180033ffa`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x1800340d4`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x18003412c`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x1800340d4`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!GetRegionData` at `0x18003412c`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CDXGISwapChain::ComposePartialPresentation(
        CDXGISwapChain *this,
        struct _D3DKMT_DIRTYREGIONS *a2,
        char a3,
        unsigned int *a4,
        unsigned int a5,
        struct IDXGIResource *lprect,
        const struct DXGI_SCROLL_RECT *a7)
{
  struct _D3DKMT_DIRTYREGIONS *v8; // r10
  int v10; // r8d
  unsigned int v11; // r13d
  int v12; // edx
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  int *v16; // r9
  char v17; // r11
  int v18; // r8d
  char v19; // r13
  unsigned int v20; // ecx
  unsigned __int64 v21; // rdx
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // r15d
  HRGN *v25; // rsi
  AutoHRGN *v26; // r8
  unsigned int v27; // r12d
  unsigned int i; // esi
  __int128 v29; // xmm0
  int v30; // esi
  __int64 *v31; // r13
  HRGN *v32; // r13
  HRGN *v33; // rdi
  __int64 v34; // rax
  int v36; // eax
  int v37; // ecx
  HRGN v38; // rax
  BOOL v39; // r13d
  int v40; // eax
  HRGN v41; // r13
  DWORD RegionData; // eax
  __int64 v43; // rdx
  __int64 v44; // r12
  unsigned __int64 v45; // rcx
  size_t v46; // rax
  unsigned __int64 v47; // rsi
  __int64 v48; // r12
  unsigned __int64 v49; // rcx
  struct _RGNDATA *v50; // rdi
  DWORD v51; // esi
  struct IDXGIResource *v52; // r13
  unsigned int v53; // eax
  CModule *v54; // rcx
  bool v55; // r9
  size_t v56; // rsi
  size_t v57; // rsi
  HRGN RectRgnIndirect; // rax
  HRGN v59; // rax
  unsigned int k; // edi
  HRGN *v61; // rax
  HRGN *v62; // rax
  RECT *v63; // r12
  unsigned int j; // eax
  const struct tagRECT *v65; // rsi
  HRGN *v66; // rax
  unsigned int v67; // ecx
  bool v68; // al
  bool v69; // cl
  char v70; // dl
  int v71; // eax
  bool v72; // al
  unsigned __int8 v73; // cl
  char v74; // [rsp+60h] [rbp-168h]
  AutoHRGN *v75; // [rsp+70h] [rbp-158h]
  __int64 *v77; // [rsp+78h] [rbp-150h]
  struct IDXGIResource *v79; // [rsp+80h] [rbp-148h]
  int v80; // [rsp+88h] [rbp-140h] BYREF
  int v81; // [rsp+8Ch] [rbp-13Ch]
  struct IDXGIResource *v82; // [rsp+90h] [rbp-138h]
  int *v83; // [rsp+98h] [rbp-130h]
  _QWORD v84[3]; // [rsp+A0h] [rbp-128h] BYREF
  _QWORD v85[3]; // [rsp+B8h] [rbp-110h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+D0h] [rbp-F8h] BYREF
  _QWORD v87[3]; // [rsp+E8h] [rbp-E0h] BYREF
  _QWORD v88[3]; // [rsp+100h] [rbp-C8h] BYREF
  _QWORD v89[3]; // [rsp+118h] [rbp-B0h] BYREF
  _QWORD v90[3]; // [rsp+130h] [rbp-98h] BYREF
  _QWORD v91[3]; // [rsp+148h] [rbp-80h] BYREF
  int left[4]; // [rsp+160h] [rbp-68h] BYREF
  RECT rect; // [rsp+170h] [rbp-58h] BYREF

  v8 = a2;
  v82 = lprect;
  if ( (*((_BYTE *)this + 440) & 4) != 0 || (*((_DWORD *)this + 109) & 0x200) != 0 )
  {
    *(_DWORD *)a2 = 1;
    v36 = *((_DWORD *)this + 94);
    v37 = *((_DWORD *)this + 95);
    *(_QWORD *)((char *)a2 + 4) = 0;
    *((_DWORD *)a2 + 3) = v36;
    *((_DWORD *)a2 + 4) = v37;
    return 0;
  }
  v10 = *a4;
  v11 = *a4 & 1;
  if ( v11
    && (v12 = a3 & 2, (a3 & 2) == 0)
    && (v13 = *((_DWORD *)this + 1140)) != 0
    && ((v14 = v13 - 1) == 0 || v14 == 2) )
  {
    *a4 = v10 & 0xFFFFFFFC;
    v16 = (int *)((char *)this + 1560);
    v15 = *((_DWORD *)this + 390);
    v17 = 1;
    *(_QWORD *)&rect.left = (char *)this + 1560;
  }
  else
  {
    *a4 = v10 & 0xFFFFFFFC;
    *(_QWORD *)&rect.left = (char *)this + 1560;
    v15 = *((_DWORD *)this + 390);
    v16 = &v80;
    v17 = 0;
    v12 = a3 & 2;
  }
  v18 = v10 & 2;
  v74 = v17;
  v83 = v16;
  v80 = v15;
  if ( *((_DWORD *)this + 111) != 1 || *((_DWORD *)this + 82) == 1 )
  {
    *v16 |= 1 << *((_DWORD *)this + 310);
    return 0;
  }
  if ( v12 )
  {
    *(_DWORD *)v8 = 0;
    return 0;
  }
  v19 = v11 ^ 1;
  v20 = *((_DWORD *)this + 1140);
  v21 = v20;
  if ( !v20 )
    goto LABEL_15;
  v21 = v20 - 1;
  if ( v20 == 1 )
    goto LABEL_15;
  v21 = v20 - 3;
  if ( (unsigned int)v21 >= 2 )
    goto LABEL_15;
  v68 = ((v21 = *((unsigned __int8 *)this + 2530), (v67 = v20 - 1) == 0) || v67 == 2) && *((_DWORD *)this + 105) == 1;
  v69 = *((_DWORD *)this + 102) > 1u || *((_DWORD *)this + 103);
  v70 = v68 | v21;
  v72 = 0;
  if ( (*((_BYTE *)this + 440) & 4) == 0 && (*((_DWORD *)this + 109) & 0x200) == 0 )
  {
    v71 = *((_DWORD *)this + 98);
    if ( v71 != 87 && v71 != 10 && v71 != 24 && v71 != 28 && v71 != 67 )
      v72 = 1;
  }
  v73 = v70 | v69;
  LOBYTE(v21) = (*((_BYTE *)this + 3920) & 3) != 0;
  if ( v73 | (unsigned __int8)(v21 | v72) )
  {
    v22 = *((_DWORD *)this + 936);
    v23 = *((_DWORD *)this + 937);
  }
  else
  {
LABEL_15:
    v22 = *((_DWORD *)this + 94);
    v23 = *((_DWORD *)this + 95);
  }
  *(_QWORD *)left = 0;
  left[2] = v22;
  left[3] = v23;
  v24 = a5;
  if ( a7 && v18 )
    v24 = a5 + 1;
  v25 = (HRGN *)((char *)this + 8 * *((unsigned int *)this + 310) + 1432);
  v75 = (AutoHRGN *)v25;
  if ( a5 && v17 )
  {
    if ( *v25 )
    {
      if ( !SetRectRgn(
              *v25,
              (int)lprect->lpVtbl,
              HIDWORD(lprect->lpVtbl),
              (int)lprect[1].lpVtbl,
              HIDWORD(lprect[1].lpVtbl)) )
      {
        v84[2] = 0;
        v84[1] = "bad allocation";
        v84[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)v84;
      }
    }
    else
    {
      RectRgnIndirect = CreateRectRgnIndirect((const RECT *)lprect);
      *v25 = RectRgnIndirect;
      if ( !RectRgnIndirect )
      {
        v85[2] = 0;
        v85[1] = "bad allocation";
        v85[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)v85;
      }
    }
    v8 = a2;
  }
  v26 = (CDXGISwapChain *)((char *)this + 792);
  v81 = 16;
  v27 = 16;
  if ( v24 < 0x10 )
    v27 = v24;
  *(_DWORD *)v8 = v27;
  for ( i = 0; i < v27; ++i )
  {
    v34 = 2LL * i;
    if ( i >= a5 )
    {
      *(_OWORD *)((char *)v8 + v34 * 8 + 4) = *(_OWORD *)((char *)a7 + 8);
    }
    else
    {
      v21 = (unsigned __int64)&v82[v34];
      *(_OWORD *)((char *)v8 + v34 * 8 + 4) = *(_OWORD *)&v82[v34].lpVtbl;
      if ( i && v74 )
      {
        v61 = (HRGN *)AutoHRGN::Set(v26, (const struct tagRECT *)v21);
        AutoHRGN::Combine(v75, *v61, 2);
        v26 = (CDXGISwapChain *)((char *)this + 792);
        v8 = a2;
      }
    }
  }
  if ( v24 > 0x10 )
  {
    v63 = (RECT *)((char *)v8 + 244);
    for ( j = 16; j < v24; j = ++v81 )
    {
      if ( j >= a5 )
      {
        UnionRect(v63, v63, (const RECT *)((char *)a7 + 8));
      }
      else
      {
        v65 = (const struct tagRECT *)&v82[2 * j];
        UnionRect(v63, v63, v65);
        if ( v74 )
        {
          v66 = (HRGN *)AutoHRGN::Set((CDXGISwapChain *)((char *)this + 792), v65);
          AutoHRGN::Combine(v75, *v66, 2);
        }
      }
    }
    v26 = (CDXGISwapChain *)((char *)this + 792);
    v8 = a2;
  }
  if ( v19 && (unsigned __int8)CDXGISwapChain::IsSequential<0>(this, v21, v26) )
  {
    *(_DWORD *)v8 = 1;
    v29 = *(_OWORD *)left;
    *(_OWORD *)((char *)v8 + 4) = *(_OWORD *)left;
  }
  else
  {
    v29 = *(_OWORD *)left;
  }
  if ( v74 )
  {
    if ( !a5 && !a7 )
    {
      *v83 |= 1 << *((_DWORD *)this + 310);
      *(_DWORD *)v8 = 1;
      *(_OWORD *)((char *)v8 + 4) = v29;
      return 0;
    }
    v82 = (struct IDXGIResource *)*((_QWORD *)this + 220);
    v30 = *((_DWORD *)this + 310);
    if ( *((_BYTE *)this + 1964) && (a3 & 0x20) == 0 )
    {
      if ( *((_DWORD *)this + 178) == 1 )
      {
        v31 = qword_1800D6FA0;
        goto LABEL_29;
      }
      if ( *((_DWORD *)this + 178) == 2 )
      {
        v31 = qword_1800D5830;
LABEL_29:
        v77 = v31;
        v79 = (struct IDXGIResource *)*((_QWORD *)this + (unsigned int)(*((_DWORD *)this + 529) - 1) + 220);
        *v83 &= ~(1 << v30);
        if ( a7 )
        {
          AutoHRGN::Set(v26, (const struct tagRECT *)((char *)a7 + 8));
          if ( a5 && AutoHRGN::Combine((CDXGISwapChain *)((char *)this + 792), *(HRGN *)v75, 4) == 1
            || (CDXGISwapChain::BltRegion(
                  this,
                  v79,
                  v82,
                  (const struct SUBRESOURCE_BLT_MAP *)v31,
                  *((HRGN *)this + 99),
                  (const struct tagPOINT *)a7),
                a5) )
          {
            v33 = (HRGN *)((char *)this + 792);
            v62 = (HRGN *)AutoHRGN::Set(
                            (CDXGISwapChain *)((char *)this + 792),
                            (const struct tagRECT *)((char *)a7 + 8));
            v32 = (HRGN *)v75;
            AutoHRGN::Combine(v75, *v62, 2);
LABEL_32:
            if ( *v33 )
            {
              if ( !SetRectRgn(*v33, left[0], left[1], left[2], left[3]) )
              {
                pExceptionObject[2] = 0;
                pExceptionObject[1] = "bad allocation";
                pExceptionObject[0] = &std::bad_alloc::`vftable';
                throw (std::bad_alloc *)pExceptionObject;
              }
            }
            else
            {
              v38 = CreateRectRgnIndirect((const RECT *)left);
              *v33 = v38;
              if ( !v38 )
              {
                v87[2] = 0;
                v87[1] = "bad allocation";
                v87[0] = &std::bad_alloc::`vftable';
                throw (std::bad_alloc *)v87;
              }
            }
            v39 = EqualRgn(*v32, *v33);
            if ( !**(_DWORD **)&rect.left )
            {
              rect = 0;
              if ( *v33 )
              {
                if ( !SetRectRgn(*v33, 0, 0, 0, 0) )
                {
                  v88[2] = 0;
                  v88[1] = "bad allocation";
                  v88[0] = &std::bad_alloc::`vftable';
                  throw (std::bad_alloc *)v88;
                }
              }
              else
              {
                v59 = CreateRectRgnIndirect(&rect);
                *v33 = v59;
                if ( !v59 )
                {
                  v89[2] = 0;
                  v89[1] = "bad allocation";
                  v89[0] = &std::bad_alloc::`vftable';
                  throw (std::bad_alloc *)v89;
                }
              }
              for ( k = 0; k < *((_DWORD *)this + 529); ++k )
              {
                if ( k != v30 && !CombineRgn(*((HRGN *)this + 99), *((HRGN *)this + 99), *((HRGN *)this + k + 179), 2) )
                {
                  v90[2] = 0;
                  v90[1] = "bad allocation";
                  v90[0] = &std::bad_alloc::`vftable';
                  throw (std::bad_alloc *)v90;
                }
              }
              v33 = (HRGN *)((char *)this + 792);
            }
            if ( v39 )
              *v83 |= 1 << v30;
            v40 = CombineRgn(*v33, *v33, *(HRGN *)v75, 4);
            if ( !v40 )
            {
              v91[2] = 0;
              v91[1] = "bad allocation";
              v91[0] = &std::bad_alloc::`vftable';
              throw (std::bad_alloc *)v91;
            }
            if ( v40 == 1 )
              return 0;
            v41 = *v33;
            RegionData = GetRegionData(*v33, 0, 0);
            v43 = *((_QWORD *)this + 100);
            v44 = *((_QWORD *)this + 101);
            v45 = v44 - v43;
            if ( RegionData >= (unsigned __int64)(v44 - v43) )
            {
              if ( RegionData <= v45 )
                goto LABEL_62;
              if ( RegionData > (unsigned __int64)(*((_QWORD *)this + 102) - v43) )
              {
                std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 800, RegionData);
                goto LABEL_62;
              }
              v56 = RegionData - v45;
              memset_0(*((void **)this + 101), 0, v56);
              v46 = v56 + v44;
            }
            else
            {
              v46 = RegionData + v43;
            }
            *((_QWORD *)this + 101) = v46;
LABEL_62:
            v47 = *((_QWORD *)this + 102) - *((_QWORD *)this + 100);
            v48 = *((_QWORD *)this + 101);
            v49 = v48 - *((_QWORD *)this + 100);
            if ( v47 >= v49 )
            {
              if ( v47 > v49 )
              {
                v57 = v47 - v49;
                memset_0(*((void **)this + 101), 0, v57);
                *((_QWORD *)this + 101) = v48 + v57;
              }
            }
            else
            {
              *((_QWORD *)this + 101) = *((_QWORD *)this + 102);
            }
            v50 = (struct _RGNDATA *)*((_QWORD *)this + 100);
            GetRegionData(v41, *((_DWORD *)this + 202) - (_DWORD)v50, v50);
            v51 = 0;
            v52 = v82;
            while ( v51 < v50->rdh.nCount )
            {
              rect = 0;
              v53 = (*(__int64 (__fastcall **)(_QWORD, struct IDXGIResource *, char *, _QWORD, _DWORD, struct IDXGIResource *, char *, __int64 *, _QWORD, _DWORD, int))(**((_QWORD **)this + 33) + 56LL))(
                      *((_QWORD *)this + 33),
                      v79,
                      &v50->Buffer[16 * v51],
                      0,
                      0,
                      v52,
                      &v50->Buffer[16 * v51],
                      v77,
                      0,
                      0,
                      1);
              if ( v53 && v53 != -2147467263 && v53 != -2147024809 && v53 != -2005270523 && v53 != -2005270527 )
                CModule::RecordJournalImpl(v54, v53, "Contract breached!", v55);
              ++v51;
            }
            return 0;
          }
          v32 = (HRGN *)v75;
          AutoHRGN::Set(v75, (const struct tagRECT *)((char *)a7 + 8));
        }
        else
        {
          v32 = (HRGN *)v75;
        }
        v33 = (HRGN *)((char *)this + 792);
        goto LABEL_32;
      }
    }
    v31 = qword_1800D57B0;
    goto LABEL_29;
  }
  return 0;
}

```

## disassembly

```asm
0x180033bd0  push    rbx
0x180033bd2  push    rsi
0x180033bd3  push    rdi
0x180033bd4  push    r12
0x180033bd6  push    r13
0x180033bd8  push    r14
0x180033bda  push    r15
0x180033bdc  sub     rsp, 190h
0x180033be3  mov     rax, cs:__security_cookie
0x180033bea  xor     rax, rsp
0x180033bed  mov     [rsp+1C8h+var_48], rax
0x180033bf5  mov     edi, r8d
0x180033bf8  mov     dword ptr [rsp+1C8h+var_150], r8d
0x180033bfd  mov     r10, rdx
0x180033c00  mov     [rsp+1C8h+var_148], rdx
0x180033c08  mov     rbx, rcx
0x180033c0b  mov     r12, [rsp+1C8h+lprect]
0x180033c13  mov     [rsp+1C8h+var_138], r12
0x180033c1b  mov     rsi, [rsp+1C8h+arg_30]
0x180033c23  mov     [rsp+1C8h+var_160], rsi
0x180033c28  test    byte ptr [rcx+1B8h], 4
0x180033c2f  jnz     loc_180033F0D
0x180033c35  test    dword ptr [rcx+1B4h], 200h
0x180033c3f  jnz     loc_180033F0D
0x180033c45  mov     r8d, [r9]
0x180033c48  mov     r13d, r8d
0x180033c4b  and     r13d, 1
0x180033c4f  jz      short loc_180033C74
0x180033c51  mov     edx, edi
0x180033c53  and     edx, 2
0x180033c56  jnz     short loc_180033C74
0x180033c58  mov     ecx, [rcx+11D0h]
0x180033c5e  test    ecx, ecx
0x180033c60  jz      short loc_180033C74
0x180033c62  sub     ecx, 1
0x180033c65  jz      loc_18003432A
0x180033c6b  cmp     ecx, 2
0x180033c6e  jz      loc_18003432A
0x180033c74  mov     eax, r8d
0x180033c77  and     eax, 0FFFFFFFCh
0x180033c7a  mov     [r9], eax
0x180033c7d  lea     rcx, [rbx+618h]
0x180033c84  mov     qword ptr [rsp+1C8h+rect.left], rcx
0x180033c8c  mov     eax, [rcx]
0x180033c8e  lea     r9, [rsp+1C8h+var_140]
0x180033c96  xor     r11b, r11b
0x180033c99  mov     edx, edi
0x180033c9b  and     edx, 2
0x180033c9e  and     r8d, 2
0x180033ca2  mov     [rsp+1C8h+var_168], r11b
0x180033ca7  mov     [rsp+1C8h+var_130], r9
0x180033caf  mov     [rsp+1C8h+var_140], eax
0x180033cb6  cmp     dword ptr [rbx+1BCh], 1
0x180033cbd  jnz     loc_180033ED6
0x180033cc3  cmp     dword ptr [rbx+148h], 1
0x180033cca  jz      loc_180033ED6
0x180033cd0  test    edx, edx
0x180033cd2  jnz     loc_180034269
0x180033cd8  xor     r13b, 1
0x180033cdc  mov     ecx, [rbx+11D0h]
0x180033ce2  mov     edx, ecx
0x180033ce4  test    ecx, ecx
0x180033ce6  jz      short loc_180033CFF
0x180033ce8  sub     edx, 1
0x180033ceb  jz      short loc_180033CFF
0x180033ced  sub     edx, 2
0x180033cf0  jz      loc_1800344DD
0x180033cf6  cmp     edx, 1
0x180033cf9  jz      loc_1800344DD
0x180033cff  mov     eax, [rbx+178h]
0x180033d05  mov     ecx, [rbx+17Ch]
0x180033d0b  xor     r14d, r14d
0x180033d0e  mov     qword ptr [rsp+1C8h+left], r14
0x180033d16  mov     [rsp+1C8h+left+8], eax
0x180033d1d  mov     [rsp+1C8h+left+0Ch], ecx
0x180033d24  mov     edi, [rsp+1C8h+arg_20]
0x180033d2b  mov     r15d, edi
0x180033d2e  test    rsi, rsi
0x180033d31  jnz     loc_180034588
0x180033d37  mov     esi, [rbx+4D8h]
0x180033d3d  add     rsi, 0B3h
0x180033d44  lea     rsi, [rbx+rsi*8]
0x180033d48  mov     [rsp+1C8h+var_158], rsi
0x180033d4d  test    edi, edi
0x180033d4f  jnz     loc_180033F2E
0x180033d55  lea     r8, [rbx+318h]
0x180033d5c  mov     eax, 10h
0x180033d61  mov     [rsp+1C8h+var_13C], eax
0x180033d68  mov     r12d, eax
0x180033d6b  cmp     r15d, eax
0x180033d6e  cmovb   r12d, r15d
0x180033d72  mov     [r10], r12d
0x180033d75  mov     esi, r14d
0x180033d78  cmp     esi, r12d
0x180033d7b  jb      loc_180033EA5
0x180033d81  cmp     r15d, 10h
0x180033d85  ja      loc_180034432
0x180033d8b  test    r13b, r13b
0x180033d8e  jnz     loc_18003461E
0x180033d94  mov     r15d, 1
0x180033d9a  movups  xmm0, xmmword ptr [rsp+1C8h+left]
0x180033da2  cmp     [rsp+1C8h+var_168], 0
0x180033da7  jz      loc_180033FD2
0x180033dad  mov     rdx, [rsp+1C8h+var_160]
0x180033db2  test    edi, edi
0x180033db4  jz      loc_180033FA5
0x180033dba  mov     rax, [rbx+6E0h]
0x180033dc1  mov     [rsp+1C8h+var_138], rax
0x180033dc9  mov     esi, [rbx+4D8h]
0x180033dcf  cmp     byte ptr [rbx+7ACh], 0
0x180033dd6  jnz     loc_1800344B7
0x180033ddc  lea     r13, qword_1800D57B0
0x180033de3  mov     [rsp+1C8h+var_150], r13
0x180033de8  mov     eax, [rbx+844h]
0x180033dee  dec     eax
0x180033df0  mov     rax, [rbx+rax*8+6E0h]
0x180033df8  mov     [rsp+1C8h+var_148], rax
0x180033e00  mov     ecx, esi
0x180033e02  mov     r12d, r15d
0x180033e05  shl     r12d, cl
0x180033e08  mov     eax, r12d
0x180033e0b  not     eax
0x180033e0d  mov     rcx, [rsp+1C8h+var_130]
0x180033e15  and     [rcx], eax
0x180033e17  test    rdx, rdx
0x180033e1a  jnz     loc_180034397
0x180033e20  mov     r13, [rsp+1C8h+var_158]
0x180033e25  lea     rdi, [rbx+318h]
0x180033e2c  mov     rcx, [rdi]; hrgn
0x180033e2f  test    rcx, rcx
0x180033e32  jz      loc_180033FD9
0x180033e38  mov     eax, [rsp+1C8h+left+0Ch]
0x180033e3f  mov     [rsp+1C8h+bottom], eax; bottom
0x180033e43  mov     r9d, [rsp+1C8h+left+8]; right
0x180033e4b  mov     r8d, [rsp+1C8h+left+4]; top
0x180033e53  mov     edx, [rsp+1C8h+left]; left
0x180033e5a  call    cs:__imp_SetRectRgn
0x180033e60  test    eax, eax
0x180033e62  jnz     loc_180033FF3
0x180033e68  xorps   xmm0, xmm0
0x180033e6b  movups  [rsp+1C8h+var_F0], xmm0
0x180033e73  lea     rax, aBadAllocation; "bad allocation"
0x180033e7a  mov     qword ptr [rsp+1C8h+var_F0], rax
0x180033e82  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180033e89  mov     [rsp+1C8h+pExceptionObject], rax
0x180033e91  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180033e98  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x180033ea0  call    _CxxThrowException_0
0x180033ea5  mov     eax, esi
0x180033ea7  shl     rax, 4
0x180033eab  cmp     esi, edi
0x180033ead  jnb     loc_1800345F6
0x180033eb3  mov     rdx, [rsp+1C8h+var_138]
0x180033ebb  add     rdx, rax; struct tagRECT *
0x180033ebe  movups  xmm0, xmmword ptr [rdx]
0x180033ec1  movups  xmmword ptr [r10+rax+4], xmm0
0x180033ec7  test    esi, esi
0x180033ec9  jnz     loc_18003435D
0x180033ecf  inc     esi
0x180033ed1  jmp     loc_180033D78
0x180033ed6  mov     ecx, [rbx+4D8h]
0x180033edc  mov     r15d, 1
0x180033ee2  shl     r15d, cl
0x180033ee5  or      [r9], r15d
0x180033ee8  xor     eax, eax
0x180033eea  mov     rcx, [rsp+1C8h+var_48]
0x180033ef2  xor     rcx, rsp; StackCookie
0x180033ef5  call    __security_check_cookie
0x180033efa  add     rsp, 190h
0x180033f01  pop     r15
0x180033f03  pop     r14
0x180033f05  pop     r13
0x180033f07  pop     r12
0x180033f09  pop     rdi
0x180033f0a  pop     rsi
0x180033f0b  pop     rbx
0x180033f0c  retn
0x180033f0d  mov     dword ptr [rdx], 1
0x180033f13  mov     eax, [rcx+178h]
0x180033f19  mov     ecx, [rcx+17Ch]
0x180033f1f  xor     r14d, r14d
0x180033f22  mov     [rdx+4], r14
0x180033f26  mov     [rdx+0Ch], eax
0x180033f29  mov     [rdx+10h], ecx
0x180033f2c  jmp     short loc_180033EE8
0x180033f2e  test    r11b, r11b
0x180033f31  jz      loc_180033D55
0x180033f37  mov     rcx, [rsi]; hrgn
0x180033f3a  test    rcx, rcx
0x180033f3d  jz      loc_180034274
0x180033f43  mov     eax, [r12+0Ch]
0x180033f48  mov     [rsp+1C8h+bottom], eax; bottom
0x180033f4c  mov     r9d, [r12+8]; right
0x180033f51  mov     r8d, [r12+4]; top
0x180033f56  mov     edx, [r12]; left
0x180033f5a  call    cs:__imp_SetRectRgn
0x180033f60  test    eax, eax
0x180033f62  jnz     loc_180034289
0x180033f68  xorps   xmm0, xmm0
0x180033f6b  movups  [rsp+1C8h+var_120], xmm0
0x180033f73  lea     rax, aBadAllocation; "bad allocation"
0x180033f7a  mov     qword ptr [rsp+1C8h+var_120], rax
0x180033f82  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180033f89  mov     [rsp+1C8h+var_128], rax
0x180033f91  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180033f98  lea     rcx, [rsp+1C8h+var_128]; pExceptionObject
0x180033fa0  call    _CxxThrowException_0
0x180033fa5  test    rdx, rdx
0x180033fa8  jnz     loc_180033DBA
0x180033fae  mov     ecx, [rbx+4D8h]
0x180033fb4  mov     eax, r15d
0x180033fb7  shl     eax, cl
0x180033fb9  mov     rcx, [rsp+1C8h+var_130]
0x180033fc1  or      [rcx], eax
0x180033fc3  mov     [r10], r15d
0x180033fc6  movups  xmmword ptr [r10+4], xmm0
0x180033fcb  xor     eax, eax
0x180033fcd  jmp     loc_180033EEA
0x180033fd2  xor     eax, eax
0x180033fd4  jmp     loc_180033EEA
0x180033fd9  lea     rcx, [rsp+1C8h+left]; lprect
0x180033fe1  call    cs:__imp_CreateRectRgnIndirect
0x180033fe7  mov     [rdi], rax
0x180033fea  test    rax, rax
0x180033fed  jz      loc_18003465E
0x180033ff3  mov     rdx, [rdi]; hrgn2
0x180033ff6  mov     rcx, [r13+0]; hrgn1
0x180033ffa  call    cs:__imp_EqualRgn
0x180034000  mov     r13d, eax
0x180034003  mov     rax, qword ptr [rsp+1C8h+rect.left]
0x18003400b  cmp     dword ptr [rax], 0
0x18003400e  jnz     short loc_180034087
0x180034010  xorps   xmm0, xmm0
0x180034013  movdqu  xmmword ptr [rsp+1C8h+rect.left], xmm0
0x18003401c  mov     rcx, [rdi]; hrgn
0x18003401f  test    rcx, rcx
0x180034022  jz      loc_180034296
0x180034028  mov     [rsp+1C8h+bottom], r14d; bottom
0x18003402d  xor     r9d, r9d; right
0x180034030  xor     r8d, r8d; top
0x180034033  xor     edx, edx; left
0x180034035  call    cs:__imp_SetRectRgn
0x18003403b  test    eax, eax
0x18003403d  jnz     loc_1800342B0
0x180034043  xorps   xmm0, xmm0
0x180034046  movups  [rsp+1C8h+var_C0], xmm0
0x18003404e  lea     rax, aBadAllocation; "bad allocation"
0x180034055  mov     qword ptr [rsp+1C8h+var_C0], rax
0x18003405d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180034064  mov     [rsp+1C8h+var_C8], rax
0x18003406c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180034073  lea     rcx, [rsp+1C8h+var_C8]; pExceptionObject
0x18003407b  call    _CxxThrowException_0
0x180034080  lea     rdi, [rbx+318h]
0x180034087  test    r13d, r13d
0x18003408a  jz      short loc_180034097
0x18003408c  mov     rax, [rsp+1C8h+var_130]
0x180034094  or      [rax], r12d
0x180034097  mov     rcx, [rdi]; hrgnDst
0x18003409a  mov     r9d, 4; iMode
0x1800340a0  mov     rax, [rsp+1C8h+var_158]
0x1800340a5  mov     r8, [rax]; hrgnSrc2
0x1800340a8  mov     rdx, rcx; hrgnSrc1
0x1800340ab  call    cs:__imp_CombineRgn
0x1800340b1  test    eax, eax
0x1800340b3  jz      loc_1800341DA
0x1800340b9  cmp     eax, 1
0x1800340bc  jz      loc_180033FCB
0x1800340c2  mov     r13, [rdi]
0x1800340c5  lea     rdi, [rbx+320h]
0x1800340cc  xor     r8d, r8d; lpRgnData
0x1800340cf  xor     edx, edx; nCount
0x1800340d1  mov     rcx, r13; hrgn
0x1800340d4  call    cs:__imp_GetRegionData
0x1800340da  mov     esi, eax
0x1800340dc  mov     rdx, [rdi]
0x1800340df  mov     r12, [rdi+8]
0x1800340e3  mov     rcx, r12
0x1800340e6  sub     rcx, rdx
0x1800340e9  cmp     rsi, rcx
0x1800340ec  jnb     loc_180034217
0x1800340f2  lea     rax, [rsi+rdx]
0x1800340f6  mov     [rdi+8], rax
0x1800340fa  mov     rdx, [rdi+10h]
0x1800340fe  mov     rsi, rdx
0x180034101  sub     rsi, [rdi]
0x180034104  mov     r12, [rdi+8]
0x180034108  mov     rcx, r12
0x18003410b  sub     rcx, [rdi]
0x18003410e  cmp     rsi, rcx
0x180034111  jnb     loc_180034246
0x180034117  mov     [rdi+8], rdx
0x18003411b  mov     rdi, [rdi]
0x18003411e  mov     edx, [rbx+328h]
0x180034124  sub     edx, edi; nCount
0x180034126  mov     r8, rdi; lpRgnData
0x180034129  mov     rcx, r13; hrgn
0x18003412c  call    cs:__imp_GetRegionData
0x180034132  mov     esi, r14d
0x180034135  mov     r12, [rsp+1C8h+var_150]
  ... truncated ...
```
