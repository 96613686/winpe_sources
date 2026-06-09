# CLegacySurfaceManager::ProcessToken(_D3DKMT_PRESENTHISTORYTOKEN const *,uint *,bool *)

- ea: `0x1801324d0`
- end: `0x1801328a8`
- name: `?ProcessToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAIPEA_N@Z`
- size: `984`
- prototype: `__int64 __fastcall(CLegacySurfaceManager *__hidden this, const struct _D3DKMT_PRESENTHISTORYTOKEN *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180131690`

## callees

- `0x180050270`
- `0x18006f610`
- `0x180072230`
- `0x180073b80`
- `0x180073e10`
- `0x1801324d0`
- `0x1801a68a8`
- `0x1801c24d8`
- `0x1801c2a90`
- `0x1801cc9a0`
- `0x180200468`
- `0x1802284b0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180132649`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180132649`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180132657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180132657`
- `ntdll!RtlLookupElementGenericTable` at `0x18013269d`
- `ntdll!RtlLookupElementGenericTable` at `0x180132779`
- `ntdll!RtlLookupElementGenericTable` at `0x18013269d`
- `ntdll!RtlLookupElementGenericTable` at `0x180132779`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801327e4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801327e4`

## string_xrefs

- `0x1801326ec`: `onecoreuap\windows\DWM\common\shared\Region.h`
- `0x180132709`: `onecoreuap\windows\DWM\common\shared\Region.h`

## pseudocode

```c
__int64 __fastcall CLegacySurfaceManager::ProcessToken(
        CLegacySurfaceManager *this,
        const struct _D3DKMT_PRESENTHISTORYTOKEN *a2,
        unsigned int *a3,
        bool *a4)
{
  unsigned int v4; // ebp
  int v6; // ecx
  const struct _D3DKMT_PRESENTHISTORYTOKEN *v8; // rdi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  unsigned __int64 *v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  int v15; // eax
  __int64 v16; // rax
  int v17; // r9d
  int v18; // r10d
  int v19; // ecx
  int v20; // edx
  int v21; // r8d
  int v22; // eax
  int v23; // eax
  void *v24; // rdi
  HANDLE ProcessHeap; // rax
  _QWORD *v27; // rcx
  PVOID v28; // rax
  CGdiSpriteBitmap *v29; // rbx
  int v30; // eax
  _QWORD *v31; // rax
  CGdiSpriteBitmap *v32; // rbx
  unsigned __int64 v33; // rdx
  CRedirectedGDISurface *v34; // rcx
  int v35; // eax
  int v36; // [rsp+20h] [rbp-D8h]
  HGDIOBJ ho; // [rsp+40h] [rbp-B8h] BYREF
  __int64 Buffer; // [rsp+48h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+50h] [rbp-A8h]
  LPVOID lpMem; // [rsp+60h] [rbp-98h] BYREF
  _DWORD v41[18]; // [rsp+68h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v4 = 0;
  lpMem = v41;
  *a4 = 0;
  v6 = *(_DWORD *)a2;
  v41[0] = 0;
  v8 = a2;
  if ( v6 == 5 )
  {
    v27 = (_QWORD *)*((_QWORD *)this + 26);
    LOBYTE(a2) = 0;
    if ( v27 && v27[7] == *((_QWORD *)v8 + 2) && *((_BYTE *)this + 220) )
    {
      (*(void (__fastcall **)(_QWORD *, const struct _D3DKMT_PRESENTHISTORYTOKEN *, unsigned int *))(*v27 + 40LL))(
        v27,
        a2,
        a3);
      LOBYTE(a2) = 1;
      *((_BYTE *)this + 220) = 0;
    }
    *a4 = (char)a2;
    goto LABEL_23;
  }
  v9 = v6 - 1;
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( !v10 )
      goto LABEL_47;
    v11 = v10 - 1;
    if ( !v11 )
    {
      v12 = (unsigned __int64 *)((char *)a2 + 32);
      if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
        McTemplateU0xxxqNR3_EventWriteTransfer(
          0,
          (_DWORD)a2,
          *((_QWORD *)a2 + 2),
          *((_QWORD *)a2 + 3),
          *v12,
          *((_DWORD *)a2 + 10));
      v13 = (_QWORD *)*((_QWORD *)this + 11);
      while ( v13 != (_QWORD *)((char *)this + 80) )
      {
        v14 = v13 - 20;
        v13 = (_QWORD *)v13[1];
        if ( v14[52] == *((_QWORD *)v8 + 3) )
        {
          v15 = CRegion::TryAddRectangles(
                  (struct FastRegion::Internal::CRgnData **)&lpMem,
                  (const struct tagRECT *)((char *)v8 + 44),
                  *((_DWORD *)v8 + 10));
          if ( v15 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x1D1,
              (unsigned int)"onecoreuap\\windows\\DWM\\common\\shared\\Region.h",
              (const char *)(unsigned int)v15,
              v36);
          v16 = *(int *)lpMem;
          if ( (_DWORD)v16 )
          {
            v17 = *((_DWORD *)lpMem + 2 * v16 + 1);
            v18 = -1;
            v19 = -1;
            v20 = *((_DWORD *)lpMem + 3);
            v21 = *((_DWORD *)lpMem + 2);
            if ( *((int *)lpMem + 1) >= 0 )
              v19 = *((_DWORD *)lpMem + 1);
            *((_DWORD *)v14 + 86) = v19;
            v22 = -1;
            if ( v20 >= 0 )
              v22 = v20;
            *((_DWORD *)v14 + 87) = v22;
            v23 = -1;
            if ( v21 >= 0 )
              v23 = v21;
            *((_DWORD *)v14 + 88) = v23;
            if ( v17 >= 0 )
              v18 = v17;
            *((_DWORD *)v14 + 89) = v18;
            CGdiSpriteBitmap::AddDirtyRegion((CGdiSpriteBitmap *)v14, (struct CRegion *)&lpMem, 1);
          }
          break;
        }
      }
      if ( *v12 )
      {
        v35 = CLegacySurfaceManager::AddIntervalOneDxBltEventId(this, *v12);
        v4 = v35;
        if ( v35 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v35, 0xB7u, 0);
          goto LABEL_23;
        }
      }
      goto LABEL_22;
    }
    if ( v11 != 3 )
    {
LABEL_47:
      *a4 = 1;
      return v4;
    }
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
      McTemplateU0xxq_EventWriteTransfer(
        3,
        (unsigned int)"X",
        *((_QWORD *)a2 + 2),
        *((_QWORD *)a2 + 4),
        *((_DWORD *)a2 + 6));
    Buffer = *((_QWORD *)v8 + 2);
    v39 = 0;
    v31 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), &Buffer);
    if ( v31 )
    {
      v32 = (CGdiSpriteBitmap *)v31[2];
      if ( v32 )
      {
        v33 = *((_QWORD *)v8 + 4);
        v34 = (CRedirectedGDISurface *)*((_QWORD *)v32 + 16);
        ho = 0;
        if ( (int)CRedirectedGDISurface::GetDirtyRegion(v34, v33, (HRGN *)&ho) >= 0 )
        {
          if ( ho )
          {
            CRegion::SetHRGN((CRegion *)&lpMem, (HRGN)ho);
            CGdiSpriteBitmap::AddDirtyRegion(v32, (struct CRegion *)&lpMem, 1);
            DeleteObject(ho);
            *a4 = 1;
            goto LABEL_23;
          }
        }
      }
    }
  }
  else
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
      McTemplateU0xxqNR2_EventWriteTransfer(
        0,
        (_DWORD)a2,
        *((_QWORD *)a2 + 2),
        *((_QWORD *)a2 + 3),
        *((_DWORD *)a2 + 14));
    Buffer = *((_QWORD *)v8 + 2);
    v39 = 0;
    v28 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), &Buffer);
    if ( v28 )
    {
      v29 = (CGdiSpriteBitmap *)*((_QWORD *)v28 + 2);
      if ( v29 )
      {
        v30 = CRegion::TryAddRectangles(
                (struct FastRegion::Internal::CRgnData **)&lpMem,
                (const struct tagRECT *)((char *)v8 + 60),
                *((_DWORD *)v8 + 14));
        if ( v30 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x1D1,
            (unsigned int)"onecoreuap\\windows\\DWM\\common\\shared\\Region.h",
            (const char *)(unsigned int)v30,
            v36);
        CGdiSpriteBitmap::AddDirtyRegion(v29, (struct CRegion *)&lpMem, 1);
      }
    }
  }
LABEL_22:
  *a4 = 1;
LABEL_23:
  v24 = lpMem;
  if ( v41 != lpMem && lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  return v4;
}

```

## disassembly

```asm
0x1801324d0  push    rbx
0x1801324d2  push    rbp
0x1801324d3  push    rsi
0x1801324d4  push    rdi
0x1801324d5  push    r12
0x1801324d7  push    r14
0x1801324d9  push    r15
0x1801324db  sub     rsp, 0C0h
0x1801324e2  mov     rax, cs:__security_cookie
0x1801324e9  xor     rax, rsp
0x1801324ec  mov     [rsp+0F8h+var_48], rax
0x1801324f4  xor     r12d, r12d
0x1801324f7  lea     rax, [rsp+0F8h+var_90]
0x1801324fc  mov     ebp, r12d
0x1801324ff  mov     [rsp+0F8h+lpMem], rax
0x180132504  mov     [r9], bpl
0x180132507  mov     r14, rcx
0x18013250a  mov     ecx, [rdx]
0x18013250c  mov     rsi, r9
0x18013250f  mov     [rsp+0F8h+var_90], r12d
0x180132514  mov     rdi, rdx
0x180132517  cmp     ecx, 5
0x18013251a  jz      loc_18013265F
0x180132520  sub     ecx, 1
0x180132523  jz      loc_180132675
0x180132529  sub     ecx, 1
0x18013252c  jz      loc_18013286A
0x180132532  sub     ecx, 1
0x180132535  jnz     loc_180132748
0x18013253b  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180132542  lea     r15, [rdx+20h]
0x180132546  jnz     loc_18013271E
0x18013254c  mov     rdx, [rdi+18h]
0x180132550  lea     rcx, [r14+50h]
0x180132554  mov     rax, [r14+58h]
0x180132558  nop     dword ptr [rax+rax+00000000h]
0x180132560  cmp     rax, rcx
0x180132563  jz      loc_180132602
0x180132569  lea     rbx, [rax-0A0h]
0x180132570  mov     rax, [rax+8]
0x180132574  cmp     [rbx+1A0h], rdx
0x18013257b  jnz     short loc_180132560
0x18013257d  mov     r8d, [rdi+28h]; unsigned int
0x180132581  lea     rdx, [rdi+2Ch]; struct tagRECT *
0x180132585  lea     rcx, [rsp+0F8h+lpMem]; this
0x18013258a  call    ?TryAddRectangles@CRegion@@QEAAJPEBUtagRECT@@I@Z; CRegion::TryAddRectangles(tagRECT const *,uint)
0x18013258f  test    eax, eax
0x180132591  js      loc_1801326E4
0x180132597  mov     rdi, [rsp+0F8h+lpMem]
0x18013259c  movsxd  rax, dword ptr [rdi]
0x18013259f  test    eax, eax
0x1801325a1  jz      short loc_180132602
0x1801325a3  mov     r9d, [rdi+rax*8+4]
0x1801325a8  mov     r10d, 0FFFFFFFFh
0x1801325ae  mov     eax, [rdi+4]
0x1801325b1  mov     ecx, r10d
0x1801325b4  mov     edx, [rdi+0Ch]
0x1801325b7  test    eax, eax
0x1801325b9  mov     r8d, [rdi+8]
0x1801325bd  cmovns  ecx, eax
0x1801325c0  test    edx, edx
0x1801325c2  mov     [rbx+158h], ecx
0x1801325c8  mov     eax, r10d
0x1801325cb  cmovns  eax, edx
0x1801325ce  mov     rcx, rbx; this
0x1801325d1  mov     [rbx+15Ch], eax
0x1801325d7  lea     rdx, [rsp+0F8h+lpMem]; struct CRegion *
0x1801325dc  test    r8d, r8d
0x1801325df  mov     eax, r10d
0x1801325e2  cmovns  eax, r8d
0x1801325e6  test    r9d, r9d
0x1801325e9  mov     [rbx+160h], eax
0x1801325ef  mov     r8b, 1; bool
0x1801325f2  cmovns  r10d, r9d
0x1801325f6  mov     [rbx+164h], r10d
0x1801325fd  call    ?AddDirtyRegion@CGdiSpriteBitmap@@AEAAXAEAVCRegion@@_N@Z; CGdiSpriteBitmap::AddDirtyRegion(CRegion &,bool)
0x180132602  mov     rdx, [r15]; unsigned __int64
0x180132605  test    rdx, rdx
0x180132608  jnz     loc_1801327F2
0x18013260e  mov     byte ptr [rsi], 1
0x180132611  mov     rdi, [rsp+0F8h+lpMem]
0x180132616  lea     rax, [rsp+0F8h+var_90]
0x18013261b  cmp     rax, rdi
0x18013261e  jz      short loc_180132625
0x180132620  test    rdi, rdi
0x180132623  jnz     short loc_180132649
0x180132625  mov     eax, ebp
0x180132627  mov     rcx, [rsp+0F8h+var_48]
0x18013262f  xor     rcx, rsp; StackCookie
0x180132632  call    __security_check_cookie
0x180132637  add     rsp, 0C0h
0x18013263e  pop     r15
0x180132640  pop     r14
0x180132642  pop     r12
0x180132644  pop     rdi
0x180132645  pop     rsi
0x180132646  pop     rbp
0x180132647  pop     rbx
0x180132648  retn
0x180132649  call    cs:__imp_GetProcessHeap
0x18013264f  mov     r8, rdi; lpMem
0x180132652  xor     edx, edx; dwFlags
0x180132654  mov     rcx, rax; hHeap
0x180132657  call    cs:__imp_HeapFree
0x18013265d  jmp     short loc_180132625
0x18013265f  mov     rcx, [r14+0D0h]
0x180132666  xor     dl, dl
0x180132668  test    rcx, rcx
0x18013266b  jnz     loc_180132873
0x180132671  mov     [rsi], dl
0x180132673  jmp     short loc_180132611
0x180132675  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x18013267c  jnz     loc_180132828
0x180132682  mov     rax, [rdi+10h]
0x180132686  lea     rcx, [r14+8]; Table
0x18013268a  xorps   xmm0, xmm0
0x18013268d  mov     [rsp+0F8h+Buffer], rax
0x180132692  lea     rdx, [rsp+0F8h+Buffer]; Buffer
0x180132697  movdqu  [rsp+0F8h+var_A8], xmm0
0x18013269d  call    cs:__imp_RtlLookupElementGenericTable
0x1801326a3  test    rax, rax
0x1801326a6  jz      loc_18013260E
0x1801326ac  mov     rbx, [rax+10h]
0x1801326b0  test    rbx, rbx
0x1801326b3  jz      loc_18013260E
0x1801326b9  mov     r8d, [rdi+38h]; unsigned int
0x1801326bd  lea     rdx, [rdi+3Ch]; struct tagRECT *
0x1801326c1  lea     rcx, [rsp+0F8h+lpMem]; this
0x1801326c6  call    ?TryAddRectangles@CRegion@@QEAAJPEBUtagRECT@@I@Z; CRegion::TryAddRectangles(tagRECT const *,uint)
0x1801326cb  test    eax, eax
0x1801326cd  js      short loc_180132701
0x1801326cf  mov     r8b, 1; bool
0x1801326d2  lea     rdx, [rsp+0F8h+lpMem]; struct CRegion *
0x1801326d7  mov     rcx, rbx; this
0x1801326da  call    ?AddDirtyRegion@CGdiSpriteBitmap@@AEAAXAEAVCRegion@@_N@Z; CGdiSpriteBitmap::AddDirtyRegion(CRegion &,bool)
0x1801326df  jmp     loc_18013260E
0x1801326e4  mov     rcx, [rsp+0F8h]; this
0x1801326ec  lea     r8, aOnecoreuapWind_215; "onecoreuap\\windows\\DWM\\common\\share"...
0x1801326f3  mov     r9d, eax; char *
0x1801326f6  mov     edx, 1D1h; void *
0x1801326fb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180132701  mov     rcx, [rsp+0F8h]; this
0x180132709  lea     r8, aOnecoreuapWind_215; "onecoreuap\\windows\\DWM\\common\\share"...
0x180132710  mov     r9d, eax; char *
0x180132713  mov     edx, 1D1h; void *
0x180132718  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18013271e  mov     r9, [rdx+18h]
0x180132722  lea     rax, [rdx+2Ch]
0x180132726  mov     r8, [rdx+10h]
0x18013272a  mov     [rsp+0F8h+var_C0], rax
0x18013272f  mov     eax, [rdx+28h]
0x180132732  mov     dword ptr [rsp+0F8h+var_D0], eax
0x180132736  mov     rax, [r15]
0x180132739  mov     qword ptr [rsp+0F8h+var_D8], rax
0x18013273e  call    McTemplateU0xxxqNR3_EventWriteTransfer
0x180132743  jmp     loc_18013254C
0x180132748  cmp     ecx, 3
0x18013274b  jnz     loc_18013286A
0x180132751  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180132758  jnz     loc_18013284A
0x18013275e  mov     rax, [rdi+10h]
0x180132762  lea     rcx, [r14+8]; Table
0x180132766  xorps   xmm0, xmm0
0x180132769  mov     [rsp+0F8h+Buffer], rax
0x18013276e  lea     rdx, [rsp+0F8h+Buffer]; Buffer
0x180132773  movdqu  [rsp+0F8h+var_A8], xmm0
0x180132779  call    cs:__imp_RtlLookupElementGenericTable
0x18013277f  test    rax, rax
0x180132782  jz      loc_18013260E
0x180132788  mov     rbx, [rax+10h]
0x18013278c  test    rbx, rbx
0x18013278f  jz      loc_18013260E
0x180132795  mov     rdx, [rdi+20h]; unsigned __int64
0x180132799  lea     r8, [rsp+0F8h+ho]; HRGN *
0x18013279e  mov     rcx, [rbx+80h]; this
0x1801327a5  mov     [rsp+0F8h+ho], r12
0x1801327aa  call    ?GetDirtyRegion@CRedirectedGDISurface@@QEAAJ_KPEAPEAUHRGN__@@@Z; CRedirectedGDISurface::GetDirtyRegion(unsigned __int64,HRGN__ * *)
0x1801327af  test    eax, eax
0x1801327b1  js      loc_18013260E
0x1801327b7  mov     rdx, [rsp+0F8h+ho]; hrgn
0x1801327bc  test    rdx, rdx
0x1801327bf  jz      loc_18013260E
0x1801327c5  lea     rcx, [rsp+0F8h+lpMem]; this
0x1801327ca  call    ?SetHRGN@CRegion@@QEAAXQEAUHRGN__@@@Z; CRegion::SetHRGN(HRGN__ * const)
0x1801327cf  mov     r8b, 1; bool
0x1801327d2  lea     rdx, [rsp+0F8h+lpMem]; struct CRegion *
0x1801327d7  mov     rcx, rbx; this
0x1801327da  call    ?AddDirtyRegion@CGdiSpriteBitmap@@AEAAXAEAVCRegion@@_N@Z; CGdiSpriteBitmap::AddDirtyRegion(CRegion &,bool)
0x1801327df  mov     rcx, [rsp+0F8h+ho]; ho
0x1801327e4  call    cs:__imp_DeleteObject
0x1801327ea  mov     byte ptr [rsi], 1
0x1801327ed  jmp     loc_180132611
0x1801327f2  mov     rcx, r14; this
0x1801327f5  call    ?AddIntervalOneDxBltEventId@CLegacySurfaceManager@@QEAAJ_K@Z; CLegacySurfaceManager::AddIntervalOneDxBltEventId(unsigned __int64)
0x1801327fa  mov     ebp, eax
0x1801327fc  test    eax, eax
0x1801327fe  jns     loc_18013260E
0x180132804  mov     [rsp+0F8h+var_D0], r12; void *
0x180132809  mov     r9d, eax; int
0x18013280c  xor     r8d, r8d; unsigned int
0x18013280f  mov     [rsp+0F8h+var_D8], 0B7h; unsigned int
0x180132817  xor     edx, edx; int *
0x180132819  mov     ecx, 14h; unsigned int
0x18013281e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180132823  jmp     loc_180132611
0x180132828  mov     r9, [rdx+18h]
0x18013282c  lea     rax, [rdx+3Ch]
0x180132830  mov     r8, [rdx+10h]
0x180132834  mov     [rsp+0F8h+var_C8], rax
0x180132839  mov     eax, [rdx+38h]
0x18013283c  mov     [rsp+0F8h+var_D8], eax
0x180132840  call    McTemplateU0xxqNR2_EventWriteTransfer
0x180132845  jmp     loc_180132682
0x18013284a  mov     eax, [rdx+18h]
0x18013284d  mov     r9, [rdx+20h]
0x180132851  mov     r8, [rdx+10h]
0x180132855  lea     rdx, EVTDESC_SCHEDULE_PRESENTHISTORYTOKEN_GDISYSMEM; "X"
0x18013285c  mov     [rsp+0F8h+var_D8], eax
0x180132860  call    McTemplateU0xxq_EventWriteTransfer
0x180132865  jmp     loc_18013275E
0x18013286a  mov     byte ptr [r9], 1
0x18013286e  jmp     loc_180132625
0x180132873  mov     rax, [rdi+10h]
0x180132877  cmp     [rcx+38h], rax
0x18013287b  jnz     loc_180132671
0x180132881  cmp     [r14+0DCh], dl
0x180132888  jz      loc_180132671
0x18013288e  mov     rax, [rcx]
0x180132891  mov     rax, [rax+28h]
0x180132895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013289a  mov     dl, 1
0x18013289c  mov     [r14+0DCh], bpl
0x1801328a3  jmp     loc_180132671
```
