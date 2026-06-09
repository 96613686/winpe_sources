# SetClipboardFormats(HWND__ *,IDataObject *)

- ea: `0x180011330`
- end: `0x18001194f`
- name: `?SetClipboardFormats@@YAJPEAUHWND__@@PEAUIDataObject@@@Z`
- size: `1567`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, IDataObject *pDataObj)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f900`

## callees

- `0x18000b2d4`
- `0x180011330`
- `0x18003ad30`
- `0x180053014`
- `0x1800c4645`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800114a5`
- `KERNELBASE!GlobalAlloc` at `0x1800114a5`
- `KERNELBASE!GlobalFree` at `0x180011912`
- `KERNELBASE!GlobalFree` at `0x180011912`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800118f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800118f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001147d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001147d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800118c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180011904`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800118c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180011904`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800114ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800114ba`
- `USER32!SetWindowLongPtrW` at `0x1800118b9`
- `USER32!SetWindowLongPtrW` at `0x1800118b9`
- `USER32!IsClipboardFormatAvailable` at `0x180011638`
- `USER32!IsClipboardFormatAvailable` at `0x180011854`
- `USER32!IsClipboardFormatAvailable` at `0x180011638`
- `USER32!IsClipboardFormatAvailable` at `0x180011854`
- `USER32!SetClipboardData` at `0x180011654`
- `USER32!SetClipboardData` at `0x1800116dc`
- `USER32!SetClipboardData` at `0x1800117bc`
- `USER32!SetClipboardData` at `0x1800117cb`
- `USER32!SetClipboardData` at `0x180011895`
- `USER32!SetClipboardData` at `0x1800118d2`
- `USER32!SetClipboardData` at `0x180011654`
- `USER32!SetClipboardData` at `0x1800116dc`
- `USER32!SetClipboardData` at `0x1800117bc`
- `USER32!SetClipboardData` at `0x1800117cb`
- `USER32!SetClipboardData` at `0x180011895`
- `USER32!SetClipboardData` at `0x1800118d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800117df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800117df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011805`

## pseudocode

```c
__int64 __fastcall SetClipboardFormats(HWND hClipWnd, IDataObject *pDataObj)
{
  struct IUnknownVtbl *lpVtbl; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rax
  signed int v4; // ebx
  int v5; // ebx
  unsigned int v6; // edi
  unsigned int v7; // r13d
  unsigned int v8; // ecx
  unsigned int v9; // edx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // edx
  int v13; // eax
  unsigned int v14; // ebx
  size_t v15; // r12
  void *v16; // r15
  HGLOBAL v17; // rax
  void *v18; // rdi
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rsi
  unsigned __int16 *v21; // r14
  unsigned int v22; // ebx
  _DWORD *v23; // rcx
  unsigned int v24; // eax
  char *v25; // rbx
  size_t v26; // r8
  const void *v27; // rdx
  UINT v28; // eax
  UINT v29; // ecx
  struct IUnknownVtbl *v30; // rax
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  unsigned int v33; // eax
  IEnumFORMATETC *pIEnum; // [rsp+30h] [rbp-69h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-61h]
  unsigned int v37; // [rsp+3Ch] [rbp-5Dh]
  int v38; // [rsp+40h] [rbp-59h]
  int v39; // [rsp+44h] [rbp-55h]
  int v40; // [rsp+48h] [rbp-51h]
  unsigned int dwStatus; // [rsp+4Ch] [rbp-4Dh] BYREF
  unsigned int v42; // [rsp+50h] [rbp-49h]
  unsigned int v43; // [rsp+54h] [rbp-45h]
  void *v44; // [rsp+58h] [rbp-41h]
  tagFORMATETC fetcObjDescriptor; // [rsp+60h] [rbp-39h] BYREF
  _GUID clsid; // [rsp+80h] [rbp-19h] BYREF
  tagFORMATETC formatetc; // [rsp+90h] [rbp-9h] BYREF
  int v50; // [rsp+110h] [rbp+77h]
  int v51; // [rsp+118h] [rbp+7Fh]

  lpVtbl = pDataObj->lpVtbl;
  pIEnum = 0;
  memset(&formatetc, 0, sizeof(formatetc));
  Release = lpVtbl[2].Release;
  dwStatus = 0;
  clsid = 0;
  v4 = ((__int64 (__fastcall *)(IDataObject *, __int64, IEnumFORMATETC **))Release)(pDataObj, 1, &pIEnum);
  if ( v4 )
    goto LABEL_82;
  v5 = 0;
  v6 = 0;
  v50 = 0;
  v7 = 0;
  ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl[1].Release)(pIEnum);
  while ( !((unsigned int (__fastcall *)(IEnumFORMATETC *, __int64, tagFORMATETC *, _QWORD))pIEnum->lpVtbl[1].QueryInterface)(
             pIEnum,
             1,
             &formatetc,
             0) )
  {
    v8 = v6 + 48;
    v9 = v6;
    v10 = -1;
    if ( v6 + 48 >= v6 )
      v10 = v6 + 48;
    v6 = v10;
    v4 = v8 < v9 ? 0x80070216 : 0;
    if ( formatetc.ptd )
    {
      if ( v8 >= v9 )
      {
        v11 = v10;
        v12 = v10 + formatetc.ptd->tdSize;
        v13 = -1;
        if ( v12 >= v11 )
          v13 = v12;
        v6 = v13;
        v4 = v12 < v11 ? 0x80070216 : 0;
      }
      CoTaskMemFree(formatetc.ptd);
    }
    if ( v4 < 0 )
      goto LABEL_82;
    ++v7;
    v5 = v50;
    if ( g_cfObjectDescriptor == formatetc.cfFormat )
    {
      v5 = 1;
      v50 = 1;
    }
  }
  if ( !v5 )
  {
    if ( v6 + 48 < v6 )
    {
LABEL_81:
      v4 = -2147024362;
      goto LABEL_82;
    }
    ++v7;
    v6 += 48;
  }
  v14 = v6 + 72;
  v43 = v6 + 72;
  if ( v6 + 72 < v6 )
    goto LABEL_81;
  v15 = v14;
  if ( v14 >= GetSafeAllocSize() || (v16 = HeapAlloc(g_hHeap, 0, v14)) == 0 )
  {
    v4 = -2147024882;
    goto LABEL_82;
  }
  if ( v14 >= GetSafeAllocSize() )
  {
    v18 = 0;
    goto LABEL_74;
  }
  v17 = GlobalAlloc(0x2002u, v14);
  v18 = v17;
  if ( !v17 )
  {
LABEL_74:
    v20 = 0;
    goto LABEL_75;
  }
  v19 = (unsigned __int16 *)GlobalLock(v17);
  v20 = v19;
  if ( v19 )
  {
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v51 = 0;
    memset_0(v19, 0, v14);
    v36 = 0;
    v21 = v20 + 12;
    v44 = &v20[24 * v7 + 36];
    v42 = v14 - (48 * (v7 + 1) + 24);
    v22 = 0;
    v37 = 0;
    ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl[1].Release)(pIEnum);
    while ( 1 )
    {
      do
      {
        if ( ((unsigned int (__fastcall *)(IEnumFORMATETC *, __int64, unsigned __int16 *))pIEnum->lpVtbl[1].QueryInterface)(
               pIEnum,
               1,
               v21) )
        {
          v33 = v43;
          *((_DWORD *)v20 + 3) = v22;
          *(_DWORD *)v20 = 0;
          *((_DWORD *)v20 + 1) = v33;
          *((_DWORD *)v20 + 2) = 1;
          *((_DWORD *)v20 + 5) = 1;
          if ( v51 )
            *((_DWORD *)v20 + 4) |= 4u;
          ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl->Release)(pIEnum);
          pIEnum = 0;
          if ( v40
            && !IsClipboardFormatAvailable(g_cfObjectLink)
            && !GetDataFromDescriptor(pDataObj, 0, g_cfLinkSrcDescriptor, USE_NORMAL_CLSID, 0, &dwStatus)
            && (dwStatus & 0x20) != 0 )
          {
            SetClipboardData(g_cfObjectLink, 0);
            *((_DWORD *)v20 + 4) |= 2u;
          }
          v4 = 0;
          memcpy_0(v16, v20, v15);
          SetWindowLongPtrW(hClipWnd, 0, (LONG_PTR)v16);
          GlobalUnlock(v18);
          if ( !SetClipboardData(g_cfOlePrivateData, v18) )
            goto LABEL_79;
          goto LABEL_82;
        }
        v23 = (_DWORD *)*((_QWORD *)v21 + 1);
        if ( v22 >= v7 )
        {
          v4 = -2147467259;
          if ( v23 )
            CoTaskMemFree(v23);
          goto LABEL_76;
        }
        if ( v23 )
        {
          v24 = *v23 + v36;
          if ( v24 < v36 )
          {
            v4 = -2147024362;
LABEL_60:
            CoTaskMemFree(v23);
            if ( v4 < 0 )
              goto LABEL_76;
LABEL_61:
            v4 = -2147467259;
            goto LABEL_76;
          }
          v4 = 0;
          if ( v24 > v42 )
            goto LABEL_60;
          v25 = (char *)v44;
          v26 = (unsigned int)*v23;
          v27 = (const void *)*((_QWORD *)v21 + 1);
          v36 += *v23;
          memcpy_0(v44, v27, v26);
          CoTaskMemFree(*((LPVOID *)v21 + 1));
          *((_QWORD *)v21 + 1) = v25 - (char *)v20;
          v44 = &v25[*(unsigned int *)v25];
          v22 = v37;
        }
        v28 = *v21;
      }
      while ( (unsigned __int16)v28 >= 0x300u && (unsigned __int16)v28 <= 0x3FFu );
      if ( (_WORD)v28 == g_cfEmbeddedObject || (_WORD)v28 == g_cfEmbedSource )
      {
        v38 = 1;
        goto LABEL_44;
      }
      if ( (_WORD)v28 == g_cfLinkSource )
      {
        v40 = 1;
        goto LABEL_44;
      }
      if ( (_WORD)v28 == g_cfOleClipboardPersistOnFlush )
      {
        if ( !v51 )
          v51 = 1;
LABEL_44:
        if ( !*((_DWORD *)v21 + 5) )
          *((_DWORD *)v21 + 5) = -1;
        if ( !IsClipboardFormatAvailable(v28) )
        {
          v29 = *v21;
          *((_DWORD *)v21 + 8) = 1;
          SetClipboardData(v29, 0);
          if ( *v21 == g_cfEmbedSource && !v50 )
          {
            *(_DWORD *)(&fetcObjDescriptor.cfFormat + 1) = 0;
            *(&fetcObjDescriptor.cfFormat + 3) = 0;
            fetcObjDescriptor.cfFormat = g_cfObjectDescriptor;
            fetcObjDescriptor.dwAspect = 1;
            v30 = pDataObj->lpVtbl;
            *(_QWORD *)&fetcObjDescriptor.tymed = 1;
            fetcObjDescriptor.ptd = 0;
            fetcObjDescriptor.lindex = -1;
            if ( !((unsigned int (__fastcall *)(IDataObject *, tagFORMATETC *))v30[1].Release)(
                    pDataObj,
                    &fetcObjDescriptor) )
            {
              if ( ++v22 >= v7 )
                goto LABEL_61;
              v21 += 24;
              SetClipboardData(g_cfObjectDescriptor, 0);
              v31 = *(_OWORD *)&fetcObjDescriptor.cfFormat;
              *((_DWORD *)v21 + 8) = 1;
              v32 = *(_OWORD *)&fetcObjDescriptor.dwAspect;
              v50 = 1;
              *(_OWORD *)v21 = v31;
              *((_OWORD *)v21 + 1) = v32;
            }
          }
        }
        ++v22;
        v21 += 24;
        v37 = v22;
        if ( v38 )
        {
          if ( !v39 )
          {
            v39 = 1;
            if ( !GetDataFromDescriptor(pDataObj, &clsid, g_cfObjectDescriptor, USE_NORMAL_CLSID, 0, 0)
              && memcmp_0(&clsid, &CLSID_Picture_Metafile, 0x10u)
              && memcmp_0(&clsid, &CLSID_Picture_Dib, 0x10u)
              && memcmp_0(&clsid, &CLSID_Picture_EnhMetafile, 0x10u) )
            {
              SetClipboardData(g_cfNative, 0);
              SetClipboardData(g_cfOwnerLink, 0);
              *((_DWORD *)v20 + 4) |= 1u;
            }
          }
        }
      }
      else if ( (_WORD)v28 != g_cfMoreOlePrivateData || !g_fIsClipboardBrokerHost )
      {
        goto LABEL_44;
      }
    }
  }
LABEL_75:
  v4 = -2147024882;
LABEL_76:
  HeapFree(g_hHeap, 0, v16);
  if ( v20 )
    GlobalUnlock(v18);
  if ( v18 )
LABEL_79:
    GlobalFree(v18);
LABEL_82:
  if ( pIEnum )
    ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl->Release)(pIEnum);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011330  mov     [rsp-8+arg_8], pDataObj
0x180011335  mov     [rsp-8+hWnd], hClipWnd
0x18001133a  push    rbp
0x18001133b  push    rbx
0x18001133c  push    rsi
0x18001133d  push    rdi
0x18001133e  push    r12
0x180011340  push    r13
0x180011342  push    r14
0x180011344  push    r15
0x180011346  lea     rbp, [rsp-1Fh]
0x18001134b  sub     rsp, 0B8h
0x180011352  mov     rax, [pDataObj]
0x180011355  lea     r8, [rbp+57h+pIEnum]
0x180011359  xorps   xmm0, xmm0
0x18001135c  xor     r14d, r14d
0x18001135f  mov     hClipWnd, pDataObj
0x180011362  mov     [rbp+57h+pIEnum], r14
0x180011366  movups  xmmword ptr [rbp+57h+formatetc.cfFormat], xmm0
0x18001136a  mov     rax, [rax+40h]
0x18001136e  lea     esi, [r14+1]
0x180011372  mov     [rbp+57h+dwStatus], r14d
0x180011376  mov     edx, esi
0x180011378  movups  xmmword ptr [rbp+57h+formatetc.dwAspect], xmm0
0x18001137c  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x180011380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011385  mov     ebx, eax
0x180011387  test    eax, eax
0x180011389  jnz     loc_180011924
0x18001138f  mov     hClipWnd, [rbp+57h+pIEnum]
0x180011393  mov     ebx, r14d
0x180011396  mov     edi, r14d
0x180011399  mov     [rbp+57h+arg_10], ebx
0x18001139c  mov     r13d, r14d
0x18001139f  mov     rax, [hClipWnd]
0x1800113a2  mov     rax, [rax+28h]
0x1800113a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ab  or      r15d, 0FFFFFFFFh
0x1800113af  mov     r12d, 80070216h
0x1800113b5  mov     hClipWnd, [rbp+57h+pIEnum]
0x1800113b9  lea     r8, [rbp+57h+formatetc]
0x1800113bd  xor     r9d, r9d
0x1800113c0  mov     edx, esi
0x1800113c2  mov     rax, [hClipWnd]
0x1800113c5  mov     rax, [rax+18h]
0x1800113c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ce  test    eax, eax
0x1800113d0  jnz     short loc_18001143E
0x1800113d2  mov     r9, [rbp+57h+formatetc.ptd]
0x1800113d6  lea     ecx, [rdi+30h]
0x1800113d9  cmp     ecx, edi
0x1800113db  mov     edx, edi
0x1800113dd  mov     eax, r15d
0x1800113e0  cmovnb  eax, ecx
0x1800113e3  cmp     ecx, edx
0x1800113e5  mov     edi, eax
0x1800113e7  sbb     ebx, ebx
0x1800113e9  and     ebx, r12d
0x1800113ec  test    r9, r9
0x1800113ef  jz      short loc_180011419
0x1800113f1  cmp     ecx, edx
0x1800113f3  jb      short loc_180011410
0x1800113f5  mov     edx, [r9]
0x1800113f8  mov     r8d, eax
0x1800113fb  add     edx, eax
0x1800113fd  mov     eax, r15d
0x180011400  cmp     edx, r8d
0x180011403  cmovnb  eax, edx
0x180011406  cmp     edx, r8d
0x180011409  mov     edi, eax
0x18001140b  sbb     ebx, ebx
0x18001140d  and     ebx, r12d
0x180011410  mov     hClipWnd, r9; pv
0x180011413  call    cs:__imp_CoTaskMemFree
0x180011419  test    ebx, ebx
0x18001141b  js      loc_180011924
0x180011421  movzx   eax, [rbp+57h+formatetc.cfFormat]
0x180011425  add     r13d, esi
0x180011428  cmp     cs:?g_cfObjectDescriptor@@3GA, ax; ushort g_cfObjectDescriptor
0x18001142f  mov     ebx, [rbp+57h+arg_10]
0x180011432  jnz     short loc_1800113B5
0x180011434  mov     ebx, esi
0x180011436  mov     [rbp+57h+arg_10], ebx
0x180011439  jmp     loc_1800113B5
0x18001143e  test    ebx, ebx
0x180011440  jnz     short loc_180011452
0x180011442  lea     eax, [rdi+30h]
0x180011445  cmp     eax, edi
0x180011447  jb      loc_180011921
0x18001144d  add     r13d, esi
0x180011450  mov     edi, eax
0x180011452  lea     ebx, [rdi+48h]
0x180011455  mov     [rbp+57h+var_9C], ebx
0x180011458  cmp     ebx, edi
0x18001145a  jb      loc_180011921
0x180011460  mov     r12d, ebx
0x180011463  call    GetSafeAllocSize
0x180011468  cmp     r12, rax
0x18001146b  jnb     loc_18001191A
0x180011471  mov     hClipWnd, cs:?g_hHeap@@3QEAXEA; hHeap
0x180011478  mov     r8d, r12d; dwBytes
0x18001147b  xor     edx, edx; dwFlags
0x18001147d  call    cs:__imp_HeapAlloc
0x180011483  mov     r15, rax
0x180011486  test    rax, rax
0x180011489  jz      loc_18001191A
0x18001148f  call    GetSafeAllocSize
0x180011494  cmp     r12, rax
0x180011497  jnb     loc_1800118DF
0x18001149d  mov     edx, r12d; dwBytes
0x1800114a0  mov     ecx, 2002h; uFlags
0x1800114a5  call    cs:__imp_GlobalAlloc
0x1800114ab  mov     rdi, rax
0x1800114ae  test    rax, rax
0x1800114b1  jz      loc_1800118E2
0x1800114b7  mov     hClipWnd, rax; hMem
0x1800114ba  call    cs:__imp_GlobalLock
0x1800114c0  mov     rsi, rax
0x1800114c3  test    rax, rax
0x1800114c6  jz      loc_1800118E5
0x1800114cc  mov     r8d, r12d; Size
0x1800114cf  mov     [rbp+57h+var_B0], r14d
0x1800114d3  xor     edx, edx; Val
0x1800114d5  mov     [rbp+57h+var_AC], r14d
0x1800114d9  mov     hClipWnd, rax; void *
0x1800114dc  mov     [rbp+57h+var_A8], r14d
0x1800114e0  mov     [rbp+57h+arg_18], r14d
0x1800114e4  call    memset_0
0x1800114e9  lea     eax, [r13+1]
0x1800114ed  mov     [rbp+57h+var_B8], 0
0x1800114f4  lea     r14, [rsi+18h]
0x1800114f8  lea     hClipWnd, [rax+rax*2]
0x1800114fc  mov     eax, esi
0x1800114fe  shl     hClipWnd, 4
0x180011502  add     hClipWnd, 18h
0x180011506  add     hClipWnd, rsi
0x180011509  sub     eax, ecx
0x18001150b  mov     [rbp+57h+var_98], hClipWnd
0x18001150f  mov     hClipWnd, [rbp+57h+pIEnum]
0x180011513  add     eax, ebx
0x180011515  mov     [rbp+57h+var_A0], eax
0x180011518  xor     ebx, ebx
0x18001151a  mov     [rbp+57h+var_B4], ebx
0x18001151d  mov     rax, [hClipWnd]
0x180011520  mov     rax, [rax+28h]
0x180011524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011529  mov     hClipWnd, [rbp+57h+pIEnum]
0x18001152d  xor     r9d, r9d
0x180011530  mov     r8, r14
0x180011533  mov     rax, [hClipWnd]
0x180011536  lea     edx, [r9+1]
0x18001153a  mov     rax, [rax+18h]
0x18001153e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011543  test    eax, eax
0x180011545  jnz     loc_180011810
0x18001154b  mov     hClipWnd, [r14+8]; pv
0x18001154f  cmp     ebx, r13d
0x180011552  jnb     loc_1800117F7
0x180011558  test    hClipWnd, hClipWnd
0x18001155b  jz      short loc_1800115B0
0x18001155d  mov     r8d, [rbp+57h+var_B8]
0x180011561  mov     edx, [hClipWnd]
0x180011563  lea     eax, [pDataObj+r8]
0x180011567  cmp     eax, r8d
0x18001156a  jb      loc_1800117DA
0x180011570  xor     ebx, ebx
0x180011572  cmp     eax, [rbp+57h+var_A0]
0x180011575  ja      loc_1800117DF
0x18001157b  mov     rbx, [rbp+57h+var_98]
0x18001157f  mov     r8d, edx; Size
0x180011582  mov     pDataObj, hClipWnd; Src
0x180011585  mov     [rbp+57h+var_B8], eax
0x180011588  mov     hClipWnd, rbx; void *
0x18001158b  call    memcpy_0
0x180011590  mov     hClipWnd, [r14+8]; pv
0x180011594  call    cs:__imp_CoTaskMemFree
0x18001159a  mov     rax, rbx
0x18001159d  sub     rax, rsi
0x1800115a0  mov     [r14+8], rax
0x1800115a4  mov     eax, [rbx]
0x1800115a6  add     rbx, rax
0x1800115a9  mov     [rbp+57h+var_98], rbx
0x1800115ad  mov     ebx, [rbp+57h+var_B4]
0x1800115b0  movzx   eax, word ptr [r14]
0x1800115b4  mov     ecx, 300h
0x1800115b9  cmp     ax, cx
0x1800115bc  jb      short loc_1800115CC
0x1800115be  mov     ecx, 3FFh
0x1800115c3  cmp     ax, cx
0x1800115c6  jbe     loc_180011529
0x1800115cc  cmp     ax, cs:?g_cfEmbeddedObject@@3GA; ushort g_cfEmbeddedObject
0x1800115d3  jz      short loc_180011620
0x1800115d5  cmp     ax, cs:?g_cfEmbedSource@@3GA; ushort g_cfEmbedSource
0x1800115dc  jz      short loc_180011620
0x1800115de  cmp     ax, cs:?g_cfLinkSource@@3GA; ushort g_cfLinkSource
0x1800115e5  jnz     short loc_1800115F0
0x1800115e7  mov     [rbp+57h+var_A8], 1
0x1800115ee  jmp     short loc_180011627
0x1800115f0  cmp     ax, cs:?g_cfOleClipboardPersistOnFlush@@3GA; ushort g_cfOleClipboardPersistOnFlush
0x1800115f7  jnz     short loc_180011608
0x1800115f9  cmp     [rbp+57h+arg_18], 0
0x1800115fd  jnz     short loc_180011627
0x1800115ff  mov     [rbp+57h+arg_18], 1
0x180011606  jmp     short loc_180011627
0x180011608  cmp     ax, cs:?g_cfMoreOlePrivateData@@3GA; ushort g_cfMoreOlePrivateData
0x18001160f  jnz     short loc_180011627
0x180011611  cmp     cs:?g_fIsClipboardBrokerHost@@3_NA, 0; bool g_fIsClipboardBrokerHost
0x180011618  jnz     loc_180011529
0x18001161e  jmp     short loc_180011627
0x180011620  mov     [rbp+57h+var_B0], 1
0x180011627  cmp     dword ptr [r14+14h], 0
0x18001162c  jnz     short loc_180011636
0x18001162e  mov     dword ptr [r14+14h], 0FFFFFFFFh
0x180011636  mov     ecx, eax; format
0x180011638  call    cs:__imp_IsClipboardFormatAvailable
0x18001163e  test    eax, eax
0x180011640  jnz     loc_180011702
0x180011646  movzx   ecx, word ptr [r14]; uFormat
0x18001164a  xor     edx, edx; hMem
0x18001164c  mov     dword ptr [r14+20h], 1
0x180011654  call    cs:__imp_SetClipboardData
0x18001165a  movzx   eax, cs:?g_cfEmbedSource@@3GA; ushort g_cfEmbedSource
0x180011661  cmp     [r14], ax
0x180011665  jnz     loc_180011702
0x18001166b  cmp     [rbp+57h+arg_10], 0
0x18001166f  jnz     loc_180011702
0x180011675  mov     hClipWnd, [rbp+57h+arg_8]
0x180011679  lea     pDataObj, [rbp+57h+fetcObjDescriptor]
0x18001167d  xor     eax, eax
0x18001167f  mov     dword ptr [rbp+57h+fetcObjDescriptor+2], 0
0x180011686  mov     word ptr [rbp+57h+fetcObjDescriptor+6], ax
0x18001168a  movzx   eax, cs:?g_cfObjectDescriptor@@3GA; ushort g_cfObjectDescriptor
0x180011691  mov     [rbp+57h+fetcObjDescriptor.cfFormat], ax
0x180011695  mov     eax, 1
0x18001169a  mov     [rbp+57h+fetcObjDescriptor.dwAspect], eax
0x18001169d  mov     rax, [hClipWnd]
0x1800116a0  mov     qword ptr [rbp+57h+fetcObjDescriptor.tymed], 1
0x1800116a8  mov     [rbp+57h+fetcObjDescriptor.ptd], 0
0x1800116b0  mov     [rbp+57h+fetcObjDescriptor.lindex], 0FFFFFFFFh
0x1800116b7  mov     rax, [rax+28h]
0x1800116bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c0  test    eax, eax
0x1800116c2  jnz     short loc_180011702
0x1800116c4  inc     ebx
0x1800116c6  cmp     ebx, r13d
0x1800116c9  jnb     loc_1800117ED
0x1800116cf  movzx   ecx, cs:?g_cfObjectDescriptor@@3GA; uFormat
0x1800116d6  add     r14, 30h ; '0'
0x1800116da  xor     edx, edx; hMem
0x1800116dc  call    cs:__imp_SetClipboardData
0x1800116e2  movups  xmm0, xmmword ptr [rbp+57h+fetcObjDescriptor.cfFormat]
0x1800116e6  mov     dword ptr [r14+20h], 1
0x1800116ee  movups  xmm1, xmmword ptr [rbp+57h+fetcObjDescriptor.dwAspect]
0x1800116f2  mov     [rbp+57h+arg_10], 1
0x1800116f9  movups  xmmword ptr [r14], xmm0
0x1800116fd  movups  xmmword ptr [r14+10h], xmm1
0x180011702  inc     ebx
0x180011704  add     r14, 30h ; '0'
0x180011708  cmp     [rbp+57h+var_B0], 0
0x18001170c  mov     [rbp+57h+var_B4], ebx
0x18001170f  jz      loc_180011529
0x180011715  cmp     [rbp+57h+var_AC], 0
0x180011719  jnz     loc_180011529
0x18001171f  movzx   r8d, cs:?g_cfObjectDescriptor@@3GA; cf
0x180011727  lea     pDataObj, [rbp+57h+clsid]; pclsid
0x18001172b  mov     hClipWnd, [rbp+57h+arg_8]; pDataObj
0x18001172f  mov     r9d, 1; fFlags
0x180011735  mov     [rsp+0F0h+pdwStatus], 0; pdwStatus
0x18001173e  mov     [rsp+0F0h+ppszSrcOfCopy], 0; ppszSrcOfCopy
0x180011747  mov     [rbp+57h+var_AC], 1
0x18001174e  call    ?GetDataFromDescriptor@@YAJPEAUIDataObject@@PEAU_GUID@@IW4tagGETCLSIDFLAGS@@PEAPEAGPEAK@Z; GetDataFromDescriptor(IDataObject *,_GUID *,uint,tagGETCLSIDFLAGS,ushort * *,ulong *)
0x180011753  test    eax, eax
0x180011755  jnz     loc_180011529
0x18001175b  lea     r8d, [rax+10h]; Size
0x18001175f  lea     pDataObj, CLSID_Picture_Metafile; Buf2
0x180011766  lea     hClipWnd, [rbp+57h+clsid]; Buf1
0x18001176a  call    memcmp_0
0x18001176f  test    eax, eax
0x180011771  jz      loc_180011529
0x180011777  mov     r8d, 10h; Size
0x18001177d  lea     pDataObj, CLSID_Picture_Dib; Buf2
0x180011784  lea     hClipWnd, [rbp+57h+clsid]; Buf1
0x180011788  call    memcmp_0
0x18001178d  test    eax, eax
0x18001178f  jz      loc_180011529
0x180011795  mov     r8d, 10h; Size
0x18001179b  lea     pDataObj, CLSID_Picture_EnhMetafile; Buf2
0x1800117a2  lea     hClipWnd, [rbp+57h+clsid]; Buf1
0x1800117a6  call    memcmp_0
0x1800117ab  test    eax, eax
0x1800117ad  jz      loc_180011529
0x1800117b3  movzx   ecx, cs:?g_cfNative@@3GA; uFormat
0x1800117ba  xor     edx, edx; hMem
0x1800117bc  call    cs:__imp_SetClipboardData
0x1800117c2  movzx   ecx, cs:?g_cfOwnerLink@@3GA; uFormat
0x1800117c9  xor     edx, edx; hMem
0x1800117cb  call    cs:__imp_SetClipboardData
0x1800117d1  or      dword ptr [rsi+10h], 1
0x1800117d5  jmp     loc_180011529
0x1800117da  mov     ebx, 80070216h
  ... truncated ...
```
