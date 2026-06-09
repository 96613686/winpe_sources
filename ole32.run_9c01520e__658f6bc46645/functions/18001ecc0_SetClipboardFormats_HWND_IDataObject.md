# SetClipboardFormats(HWND__ *,IDataObject *)

- ea: `0x18001ecc0`
- end: `0x18001f3b9`
- name: `?SetClipboardFormats@@YAJPEAUHWND__@@PEAUIDataObject@@@Z`
- size: `1785`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, IDataObject *pDataObj)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001e5b4`

## callees

- `0x18000a574`
- `0x18001ecc0`
- `0x18003f034`
- `0x180046460`
- `0x180047484`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18001ee85`
- `KERNELBASE!GlobalAlloc` at `0x18001ee85`
- `KERNELBASE!GlobalFree` at `0x18001f35f`
- `KERNELBASE!GlobalFree` at `0x18001f35f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f337`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f337`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ee55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ee55`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001f2f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001f34b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001f2f1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001f34b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001eea0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001eea0`
- `USER32!SetWindowLongPtrW` at `0x18001f2e2`
- `USER32!SetWindowLongPtrW` at `0x18001f2e2`
- `USER32!IsClipboardFormatAvailable` at `0x18001f029`
- `USER32!IsClipboardFormatAvailable` at `0x18001f274`
- `USER32!IsClipboardFormatAvailable` at `0x18001f029`
- `USER32!IsClipboardFormatAvailable` at `0x18001f274`
- `USER32!SetClipboardData` at `0x18001f04d`
- `USER32!SetClipboardData` at `0x18001f0d0`
- `USER32!SetClipboardData` at `0x18001f1bb`
- `USER32!SetClipboardData` at `0x18001f1d0`
- `USER32!SetClipboardData` at `0x18001f2bb`
- `USER32!SetClipboardData` at `0x18001f30d`
- `USER32!SetClipboardData` at `0x18001f04d`
- `USER32!SetClipboardData` at `0x18001f0d0`
- `USER32!SetClipboardData` at `0x18001f1bb`
- `USER32!SetClipboardData` at `0x18001f1d0`
- `USER32!SetClipboardData` at `0x18001f2bb`
- `USER32!SetClipboardData` at `0x18001f30d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001edde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f1ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f21c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001edde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f1ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f21c`

## pseudocode

```c
__int64 __fastcall SetClipboardFormats(HWND hClipWnd, IDataObject *pDataObj)
{
  struct IUnknownVtbl *lpVtbl; // rax
  ULONG (__stdcall *Release)(IUnknown *); // rax
  unsigned __int16 *v4; // rsi
  unsigned int v5; // edi
  unsigned int v6; // r13d
  int v7; // r15d
  signed int v8; // ebx
  unsigned int v9; // edx
  int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // edx
  unsigned int v13; // ecx
  int v14; // eax
  unsigned int v15; // eax
  size_t v16; // r14
  unsigned int v17; // ebx
  void *v18; // r12
  HGLOBAL v19; // rax
  void *v20; // rdi
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // r15
  __int64 v23; // rdx
  __int64 v24; // r8
  _DWORD *v25; // rcx
  unsigned int v26; // edx
  unsigned int v27; // eax
  int v28; // r13d
  char *v29; // rbx
  UINT v30; // eax
  UINT v31; // ecx
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  IEnumFORMATETC *pIEnum; // [rsp+30h] [rbp-99h] BYREF
  int v39; // [rsp+38h] [rbp-91h]
  int v40; // [rsp+3Ch] [rbp-8Dh]
  int v41; // [rsp+40h] [rbp-89h]
  unsigned int v42; // [rsp+44h] [rbp-85h]
  int v43; // [rsp+48h] [rbp-81h]
  int v44; // [rsp+4Ch] [rbp-7Dh]
  int v45; // [rsp+50h] [rbp-79h]
  int v46; // [rsp+54h] [rbp-75h]
  unsigned int dwStatus[6]; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v48; // [rsp+70h] [rbp-59h]
  IDataObject *v49; // [rsp+78h] [rbp-51h]
  void *v50; // [rsp+80h] [rbp-49h]
  tagFORMATETC fetcObjDescriptor; // [rsp+88h] [rbp-41h] BYREF
  HWND hWnd; // [rsp+A8h] [rbp-21h]
  tagFORMATETC formatetc; // [rsp+B0h] [rbp-19h] BYREF
  _GUID clsid; // [rsp+D0h] [rbp+7h] BYREF

  lpVtbl = pDataObj->lpVtbl;
  v49 = pDataObj;
  hWnd = hClipWnd;
  pIEnum = 0;
  Release = lpVtbl[2].Release;
  v39 = 0;
  memset(&formatetc, 0, sizeof(formatetc));
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v44 = 0;
  v45 = 0;
  v7 = 0;
  v46 = 0;
  clsid = 0;
  dwStatus[0] = 0;
  v40 = 0;
  v41 = 0;
  v8 = ((__int64 (__fastcall *)(IDataObject *, __int64, IEnumFORMATETC **))Release)(pDataObj, 1, &pIEnum);
  if ( v8 )
    goto LABEL_88;
  ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl[1].Release)(pIEnum);
  while ( !((unsigned int (__fastcall *)(IEnumFORMATETC *, __int64, tagFORMATETC *))pIEnum->lpVtbl[1].QueryInterface)(
             pIEnum,
             1,
             &formatetc) )
  {
    v9 = v5 + 48;
    ++v6;
    v10 = -1;
    v39 = v6;
    v11 = v5;
    if ( v5 + 48 >= v5 )
      v10 = v5 + 48;
    v5 = v10;
    v8 = v9 < v11 ? 0x80070216 : 0;
    if ( formatetc.ptd )
    {
      if ( v9 >= v11 )
      {
        v12 = v10;
        v13 = v10 + formatetc.ptd->tdSize;
        v14 = -1;
        if ( v13 >= v12 )
          v14 = v13;
        v5 = v14;
        v8 = v13 < v12 ? 0x80070216 : 0;
      }
      CoTaskMemFree(formatetc.ptd);
    }
    if ( v8 < 0 )
      goto LABEL_88;
    if ( g_cfObjectDescriptor == formatetc.cfFormat )
    {
      v7 = 1;
      v40 = 1;
    }
  }
  if ( !v7 )
  {
    v39 = ++v6;
    if ( v5 + 48 < v5 )
    {
LABEL_87:
      v8 = -2147024362;
      goto LABEL_88;
    }
    v5 += 48;
  }
  v15 = v5 + 72;
  if ( v5 + 72 < v5 )
    goto LABEL_87;
  v16 = v15;
  if ( v15 < GetSafeAllocSize() && (v17 = 0, (v18 = HeapAlloc(g_hHeap, 0, (unsigned int)v16)) != 0) )
  {
    if ( v16 >= GetSafeAllocSize() )
    {
      v20 = 0;
    }
    else
    {
      v19 = GlobalAlloc(0x2002u, (unsigned int)v16);
      v20 = v19;
      if ( v19 )
      {
        v21 = (unsigned __int16 *)GlobalLock(v19);
        v4 = v21;
        if ( v21 )
        {
          memset_0(v21, 0, (unsigned int)v16);
          v42 = 0;
          v22 = v4 + 12;
          v43 = 0;
          v50 = &v4[24 * v6 + 36];
          v48 = v16 - (48 * (v6 + 1) + 24);
          ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl[1].Release)(pIEnum);
          while ( 1 )
          {
            do
            {
              if ( ((unsigned int (__fastcall *)(IEnumFORMATETC *, __int64, unsigned __int16 *))pIEnum->lpVtbl[1].QueryInterface)(
                     pIEnum,
                     1,
                     v22) )
              {
                *((_DWORD *)v4 + 3) = v17;
                *((_DWORD *)v4 + 2) = 1;
                *((_DWORD *)v4 + 5) = 1;
                *(_DWORD *)v4 = 0;
                *((_DWORD *)v4 + 1) = v16;
                if ( v41 )
                  *((_DWORD *)v4 + 4) |= 4u;
                ((void (__fastcall *)(IEnumFORMATETC *, __int64, __int64, _QWORD))pIEnum->lpVtbl->Release)(
                  pIEnum,
                  v23,
                  v24,
                  0);
                v8 = 0;
                pIEnum = 0;
                if ( v46
                  && !IsClipboardFormatAvailable(g_cfObjectLink)
                  && !GetDataFromDescriptor(v49, 0, g_cfLinkSrcDescriptor, USE_NORMAL_CLSID, 0, dwStatus)
                  && (dwStatus[0] & 0x20) != 0 )
                {
                  SetClipboardData(g_cfObjectLink, 0);
                  *((_DWORD *)v4 + 4) |= 2u;
                }
                memcpy_0(v18, v4, v16);
                SetWindowLongPtrW(hWnd, 0, (LONG_PTR)v18);
                GlobalUnlock(v20);
                v4 = 0;
                if ( SetClipboardData(g_cfOlePrivateData, v20) )
                {
                  v20 = 0;
                  goto LABEL_82;
                }
                goto LABEL_85;
              }
              v25 = (_DWORD *)*((_QWORD *)v22 + 1);
              if ( v17 >= v6 )
              {
                v8 = -2147467259;
                if ( v25 )
                  CoTaskMemFree(v25);
                goto LABEL_81;
              }
              if ( v25 )
              {
                v26 = *v25;
                v27 = *v25 + v42;
                if ( v27 < v42 )
                {
                  v28 = -2147024362;
                  v8 = -2147024362;
LABEL_66:
                  CoTaskMemFree(v25);
                  if ( v28 < 0 )
                    goto LABEL_81;
LABEL_67:
                  v8 = -2147467259;
                  goto LABEL_81;
                }
                v28 = 0;
                v42 += *v25;
                v8 = 0;
                if ( v27 > v48 )
                  goto LABEL_66;
                v29 = (char *)v50;
                memcpy_0(v50, v25, v26);
                CoTaskMemFree(*((LPVOID *)v22 + 1));
                v6 = v39;
                *((_QWORD *)v22 + 1) = v29 - (char *)v4;
                v50 = &v29[*(unsigned int *)v29];
                v17 = v43;
              }
              v30 = *v22;
            }
            while ( (unsigned __int16)v30 >= 0x300u && (unsigned __int16)v30 <= 0x3FFu );
            if ( (_WORD)v30 == g_cfEmbeddedObject || (_WORD)v30 == g_cfEmbedSource )
            {
              v44 = 1;
              goto LABEL_44;
            }
            if ( (_WORD)v30 == g_cfLinkSource )
            {
              v46 = 1;
              goto LABEL_44;
            }
            if ( (_WORD)v30 == g_cfOleClipboardPersistOnFlush )
            {
              if ( !v41 )
                v41 = 1;
LABEL_44:
              if ( !*((_DWORD *)v22 + 5) )
                *((_DWORD *)v22 + 5) = -1;
              if ( !IsClipboardFormatAvailable(v30) )
              {
                v31 = *v22;
                *((_DWORD *)v22 + 8) = 1;
                SetClipboardData(v31, 0);
                if ( *v22 == g_cfEmbedSource && !v40 )
                {
                  fetcObjDescriptor.lindex = -1;
                  fetcObjDescriptor.cfFormat = g_cfObjectDescriptor;
                  fetcObjDescriptor.dwAspect = 1;
                  *(_DWORD *)(&fetcObjDescriptor.cfFormat + 1) = 0;
                  *(&fetcObjDescriptor.cfFormat + 3) = 0;
                  fetcObjDescriptor.ptd = 0;
                  *(_QWORD *)&fetcObjDescriptor.tymed = 1;
                  if ( !((unsigned int (__fastcall *)(IDataObject *, tagFORMATETC *))v49->lpVtbl[1].Release)(
                          v49,
                          &fetcObjDescriptor) )
                  {
                    if ( ++v17 >= v6 )
                      goto LABEL_67;
                    v22 += 24;
                    SetClipboardData(g_cfObjectDescriptor, 0);
                    v32 = *(_OWORD *)&fetcObjDescriptor.cfFormat;
                    v33 = *(_OWORD *)&fetcObjDescriptor.dwAspect;
                    *((_DWORD *)v22 + 8) = 1;
                    *(_OWORD *)v22 = v32;
                    v40 = 1;
                    *((_OWORD *)v22 + 1) = v33;
                  }
                }
              }
              v22 += 24;
              v43 = ++v17;
              if ( v44 )
              {
                if ( !v45 )
                {
                  v45 = 1;
                  if ( !GetDataFromDescriptor(v49, &clsid, g_cfObjectDescriptor, USE_NORMAL_CLSID, 0, 0) )
                  {
                    v34 = *(_QWORD *)&clsid.Data1 - *(_QWORD *)&CLSID_Picture_Metafile.Data1;
                    if ( *(_QWORD *)&clsid.Data1 == *(_QWORD *)&CLSID_Picture_Metafile.Data1 )
                      v34 = *(_QWORD *)clsid.Data4 - *(_QWORD *)CLSID_Picture_Metafile.Data4;
                    if ( v34 )
                    {
                      v35 = *(_QWORD *)&clsid.Data1 - *(_QWORD *)&CLSID_Picture_Dib.Data1;
                      if ( *(_QWORD *)&clsid.Data1 == *(_QWORD *)&CLSID_Picture_Dib.Data1 )
                        v35 = *(_QWORD *)clsid.Data4 - *(_QWORD *)CLSID_Picture_Dib.Data4;
                      if ( v35 )
                      {
                        v36 = *(_QWORD *)&clsid.Data1 - *(_QWORD *)&CLSID_Picture_EnhMetafile.Data1;
                        if ( *(_QWORD *)&clsid.Data1 == *(_QWORD *)&CLSID_Picture_EnhMetafile.Data1 )
                          v36 = *(_QWORD *)clsid.Data4 - *(_QWORD *)CLSID_Picture_EnhMetafile.Data4;
                        if ( v36 )
                        {
                          SetClipboardData(g_cfNative, 0);
                          SetClipboardData(g_cfOwnerLink, 0);
                          *((_DWORD *)v4 + 4) |= 1u;
                        }
                      }
                    }
                  }
                }
              }
            }
            else if ( (_WORD)v30 != g_cfMoreOlePrivateData || !g_fIsClipboardBrokerHost )
            {
              goto LABEL_44;
            }
          }
        }
      }
    }
    v8 = -2147024882;
LABEL_81:
    HeapFree(g_hHeap, 0, v18);
LABEL_82:
    if ( v4 )
      GlobalUnlock(v20);
    if ( v20 )
LABEL_85:
      GlobalFree(v20);
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_88:
  if ( pIEnum )
    ((void (__fastcall *)(IEnumFORMATETC *))pIEnum->lpVtbl->Release)(pIEnum);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ecc0  mov     [rsp-8+arg_10], rbx
0x18001ecc5  push    rbp
0x18001ecc6  push    rsi
0x18001ecc7  push    rdi
0x18001ecc8  push    r12
0x18001ecca  push    r13
0x18001eccc  push    r14
0x18001ecce  push    r15
0x18001ecd0  lea     rbp, [rsp-27h]
0x18001ecd5  sub     rsp, 0F0h
0x18001ecdc  mov     rax, cs:__security_cookie
0x18001ece3  xor     rax, rsp
0x18001ece6  mov     [rbp+57h+var_40], rax
0x18001ecea  mov     rax, [pDataObj]
0x18001eced  lea     r8, [rsp+120h+pIEnum]
0x18001ecf2  xor     r12d, r12d
0x18001ecf5  mov     [rbp+57h+var_A8], pDataObj
0x18001ecf9  xorps   xmm0, xmm0
0x18001ecfc  mov     [rbp+57h+hWnd], hClipWnd
0x18001ed00  mov     r9, pDataObj
0x18001ed03  mov     [rsp+120h+pIEnum], r12
0x18001ed08  mov     rax, [rax+40h]
0x18001ed0c  mov     hClipWnd, r9
0x18001ed0f  lea     edx, [r12+1]
0x18001ed14  mov     [rsp+120h+var_E8], r12d
0x18001ed19  movups  xmmword ptr [rbp+57h+formatetc.cfFormat], xmm0
0x18001ed1d  mov     esi, r12d
0x18001ed20  mov     edi, r12d
0x18001ed23  movups  xmmword ptr [rbp+57h+formatetc.dwAspect], xmm0
0x18001ed27  mov     r13d, r12d
0x18001ed2a  mov     [rbp+57h+var_D4], r12d
0x18001ed2e  mov     [rbp+57h+var_D0], r12d
0x18001ed32  mov     r15d, r12d
0x18001ed35  mov     [rbp+57h+var_CC], r12d
0x18001ed39  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x18001ed3d  mov     [rbp+57h+dwStatus], r12d
0x18001ed41  mov     [rsp+120h+var_E4], r12d
0x18001ed46  mov     [rsp+120h+var_E0], r12d
0x18001ed4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed50  mov     ebx, eax
0x18001ed52  test    eax, eax
0x18001ed54  jnz     loc_18001F379
0x18001ed5a  mov     hClipWnd, [rsp+120h+pIEnum]
0x18001ed5f  mov     rax, [hClipWnd]
0x18001ed62  mov     rax, [rax+28h]
0x18001ed66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed6b  mov     hClipWnd, [rsp+120h+pIEnum]
0x18001ed70  lea     r8, [rbp+57h+formatetc]
0x18001ed74  xor     r9d, r9d
0x18001ed77  mov     r14d, edi
0x18001ed7a  mov     rax, [hClipWnd]
0x18001ed7d  lea     edx, [r9+1]
0x18001ed81  mov     rax, [rax+18h]
0x18001ed85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed8a  test    eax, eax
0x18001ed8c  jnz     loc_18001EE13
0x18001ed92  mov     r8, [rbp+57h+formatetc.ptd]
0x18001ed96  lea     edx, [rdi+30h]
0x18001ed99  inc     r13d
0x18001ed9c  or      eax, 0FFFFFFFFh
0x18001ed9f  cmp     edx, edi
0x18001eda1  mov     [rsp+120h+var_E8], r13d
0x18001eda6  mov     ecx, edi
0x18001eda8  mov     r9d, 80070216h
0x18001edae  cmovnb  eax, edx
0x18001edb1  cmp     edx, ecx
0x18001edb3  mov     edi, eax
0x18001edb5  sbb     ebx, ebx
0x18001edb7  and     ebx, r9d
0x18001edba  test    r8, r8
0x18001edbd  jz      short loc_18001EDEA
0x18001edbf  cmp     edx, ecx
0x18001edc1  jb      short loc_18001EDDB
0x18001edc3  mov     ecx, [r8]
0x18001edc6  mov     edx, eax
0x18001edc8  add     ecx, eax
0x18001edca  or      eax, 0FFFFFFFFh
0x18001edcd  cmp     ecx, edx
0x18001edcf  cmovnb  eax, ecx
0x18001edd2  cmp     ecx, edx
0x18001edd4  mov     edi, eax
0x18001edd6  sbb     ebx, ebx
0x18001edd8  and     ebx, r9d
0x18001eddb  mov     hClipWnd, r8; pv
0x18001edde  call    cs:__imp_CoTaskMemFree
0x18001ede5  nop     dword ptr [rax+rax+00h]
0x18001edea  test    ebx, ebx
0x18001edec  js      loc_18001F379
0x18001edf2  movzx   eax, [rbp+57h+formatetc.cfFormat]
0x18001edf6  cmp     cs:?g_cfObjectDescriptor@@3GA, ax; ushort g_cfObjectDescriptor
0x18001edfd  jnz     loc_18001ED6B
0x18001ee03  mov     r15d, 1
0x18001ee09  mov     [rsp+120h+var_E4], r15d
0x18001ee0e  jmp     loc_18001ED6B
0x18001ee13  test    r15d, r15d
0x18001ee16  jnz     short loc_18001EE2D
0x18001ee18  inc     r13d
0x18001ee1b  lea     eax, [rdi+30h]
0x18001ee1e  mov     [rsp+120h+var_E8], r13d
0x18001ee23  cmp     eax, edi
0x18001ee25  jb      loc_18001F374
0x18001ee2b  mov     edi, eax
0x18001ee2d  lea     eax, [rdi+48h]
0x18001ee30  cmp     eax, edi
0x18001ee32  jb      loc_18001F374
0x18001ee38  mov     r14d, eax
0x18001ee3b  call    GetSafeAllocSize
0x18001ee40  cmp     r14, rax
0x18001ee43  jnb     loc_18001F36D
0x18001ee49  mov     hClipWnd, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001ee50  mov     r8d, r14d; dwBytes
0x18001ee53  xor     edx, edx; dwFlags
0x18001ee55  call    cs:__imp_HeapAlloc
0x18001ee5c  nop     dword ptr [rax+rax+00h]
0x18001ee61  xor     ebx, ebx
0x18001ee63  mov     r12, rax
0x18001ee66  test    rax, rax
0x18001ee69  jz      loc_18001F36D
0x18001ee6f  call    GetSafeAllocSize
0x18001ee74  cmp     r14, rax
0x18001ee77  jnb     loc_18001F323
0x18001ee7d  mov     edx, r14d; dwBytes
0x18001ee80  mov     ecx, 2002h; uFlags
0x18001ee85  call    cs:__imp_GlobalAlloc
0x18001ee8c  nop     dword ptr [rax+rax+00h]
0x18001ee91  mov     rdi, rax
0x18001ee94  test    rax, rax
0x18001ee97  jz      loc_18001F326
0x18001ee9d  mov     hClipWnd, rax; hMem
0x18001eea0  call    cs:__imp_GlobalLock
0x18001eea7  nop     dword ptr [rax+rax+00h]
0x18001eeac  mov     rsi, rax
0x18001eeaf  test    rax, rax
0x18001eeb2  jz      loc_18001F326
0x18001eeb8  mov     r8d, r14d; Size
0x18001eebb  xor     edx, edx; Val
0x18001eebd  mov     hClipWnd, rax; void *
0x18001eec0  call    memset_0
0x18001eec5  lea     eax, [r13+1]
0x18001eec9  mov     [rsp+120h+var_DC], ebx
0x18001eecd  lea     r15, [rsi+18h]
0x18001eed1  mov     [rsp+120h+var_D8], ebx
0x18001eed5  lea     hClipWnd, [rax+rax*2]
0x18001eed9  mov     eax, esi
0x18001eedb  shl     hClipWnd, 4
0x18001eedf  add     hClipWnd, 18h
0x18001eee3  add     hClipWnd, rsi
0x18001eee6  sub     eax, ecx
0x18001eee8  mov     [rbp+57h+var_A0], hClipWnd
0x18001eeec  mov     hClipWnd, [rsp+120h+pIEnum]
0x18001eef1  add     eax, r14d
0x18001eef4  mov     [rbp+57h+var_B0], eax
0x18001eef7  mov     rax, [hClipWnd]
0x18001eefa  mov     rax, [rax+28h]
0x18001eefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef03  mov     hClipWnd, [rsp+120h+pIEnum]
0x18001ef08  xor     r9d, r9d
0x18001ef0b  mov     r8, r15
0x18001ef0e  mov     rax, [hClipWnd]
0x18001ef11  lea     edx, [r9+1]
0x18001ef15  mov     rax, [rax+18h]
0x18001ef19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef1e  xor     r9d, r9d
0x18001ef21  test    eax, eax
0x18001ef23  jnz     loc_18001F22D
0x18001ef29  mov     hClipWnd, [r15+8]; pv
0x18001ef2d  cmp     ebx, r13d
0x18001ef30  jnb     loc_18001F20E
0x18001ef36  test    hClipWnd, hClipWnd
0x18001ef39  jz      short loc_18001EFA3
0x18001ef3b  mov     r8d, [rsp+120h+var_DC]
0x18001ef40  mov     edx, [hClipWnd]
0x18001ef42  lea     eax, [pDataObj+r8]
0x18001ef46  cmp     eax, r8d
0x18001ef49  jb      loc_18001F1E5
0x18001ef4f  mov     r13d, r9d
0x18001ef52  mov     [rsp+120h+var_DC], eax
0x18001ef56  mov     ebx, r9d
0x18001ef59  cmp     eax, [rbp+57h+var_B0]
0x18001ef5c  ja      loc_18001F1EF
0x18001ef62  mov     rbx, [rbp+57h+var_A0]
0x18001ef66  mov     r8d, edx; Size
0x18001ef69  mov     pDataObj, hClipWnd; Src
0x18001ef6c  mov     hClipWnd, rbx; void *
0x18001ef6f  call    memcpy_0
0x18001ef74  mov     hClipWnd, [r15+8]; pv
0x18001ef78  call    cs:__imp_CoTaskMemFree
0x18001ef7f  nop     dword ptr [rax+rax+00h]
0x18001ef84  mov     r13d, [rsp+120h+var_E8]
0x18001ef89  mov     rax, rbx
0x18001ef8c  sub     rax, rsi
0x18001ef8f  mov     [r15+8], rax
0x18001ef93  mov     eax, [rbx]
0x18001ef95  add     rbx, rax
0x18001ef98  mov     [rbp+57h+var_A0], rbx
0x18001ef9c  xor     r9d, r9d
0x18001ef9f  mov     ebx, [rsp+120h+var_D8]
0x18001efa3  movzx   eax, word ptr [r15]
0x18001efa7  mov     ecx, 300h
0x18001efac  cmp     ax, cx
0x18001efaf  jb      short loc_18001EFBF
0x18001efb1  mov     ecx, 3FFh
0x18001efb6  cmp     ax, cx
0x18001efb9  jbe     loc_18001EF03
0x18001efbf  cmp     ax, cs:?g_cfEmbeddedObject@@3GA; ushort g_cfEmbeddedObject
0x18001efc6  jz      short loc_18001F015
0x18001efc8  cmp     ax, cs:?g_cfEmbedSource@@3GA; ushort g_cfEmbedSource
0x18001efcf  jz      short loc_18001F015
0x18001efd1  cmp     ax, cs:?g_cfLinkSource@@3GA; ushort g_cfLinkSource
0x18001efd8  jnz     short loc_18001EFE3
0x18001efda  mov     [rbp+57h+var_CC], 1
0x18001efe1  jmp     short loc_18001F01C
0x18001efe3  cmp     ax, cs:?g_cfOleClipboardPersistOnFlush@@3GA; ushort g_cfOleClipboardPersistOnFlush
0x18001efea  jnz     short loc_18001EFFD
0x18001efec  cmp     [rsp+120h+var_E0], r9d
0x18001eff1  jnz     short loc_18001F01C
0x18001eff3  mov     [rsp+120h+var_E0], 1
0x18001effb  jmp     short loc_18001F01C
0x18001effd  cmp     ax, cs:?g_cfMoreOlePrivateData@@3GA; ushort g_cfMoreOlePrivateData
0x18001f004  jnz     short loc_18001F01C
0x18001f006  cmp     cs:?g_fIsClipboardBrokerHost@@3_NA, r9b; bool g_fIsClipboardBrokerHost
0x18001f00d  jnz     loc_18001EF03
0x18001f013  jmp     short loc_18001F01C
0x18001f015  mov     [rbp+57h+var_D4], 1
0x18001f01c  cmp     [r15+14h], r9d
0x18001f020  jnz     short loc_18001F027
0x18001f022  or      dword ptr [r15+14h], 0FFFFFFFFh
0x18001f027  mov     ecx, eax; format
0x18001f029  call    cs:__imp_IsClipboardFormatAvailable
0x18001f030  nop     dword ptr [rax+rax+00h]
0x18001f035  xor     ecx, ecx
0x18001f037  test    eax, eax
0x18001f039  jnz     loc_18001F0FC
0x18001f03f  movzx   ecx, word ptr [r15]; uFormat
0x18001f043  xor     edx, edx; hMem
0x18001f045  mov     dword ptr [r15+20h], 1
0x18001f04d  call    cs:__imp_SetClipboardData
0x18001f054  nop     dword ptr [rax+rax+00h]
0x18001f059  movzx   eax, cs:?g_cfEmbedSource@@3GA; ushort g_cfEmbedSource
0x18001f060  xor     ecx, ecx
0x18001f062  cmp     [r15], ax
0x18001f066  jnz     loc_18001F0FC
0x18001f06c  cmp     [rsp+120h+var_E4], ecx
0x18001f070  jnz     loc_18001F0FC
0x18001f076  movzx   eax, cs:?g_cfObjectDescriptor@@3GA; ushort g_cfObjectDescriptor
0x18001f07d  lea     pDataObj, [rbp+57h+fetcObjDescriptor]
0x18001f081  or      [rbp+57h+fetcObjDescriptor.lindex], 0FFFFFFFFh
0x18001f085  mov     [rbp+57h+fetcObjDescriptor.cfFormat], ax
0x18001f089  lea     eax, [hClipWnd+1]
0x18001f08c  mov     [rbp+57h+fetcObjDescriptor.dwAspect], eax
0x18001f08f  mov     dword ptr [rbp+57h+fetcObjDescriptor+2], ecx
0x18001f092  mov     word ptr [rbp+57h+fetcObjDescriptor+6], cx
0x18001f096  mov     [rbp+57h+fetcObjDescriptor.ptd], hClipWnd
0x18001f09a  mov     hClipWnd, [rbp+57h+var_A8]
0x18001f09e  mov     qword ptr [rbp+57h+fetcObjDescriptor.tymed], 1
0x18001f0a6  mov     rax, [hClipWnd]
0x18001f0a9  mov     rax, [rax+28h]
0x18001f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b2  xor     ecx, ecx
0x18001f0b4  test    eax, eax
0x18001f0b6  jnz     short loc_18001F0FC
0x18001f0b8  inc     ebx
0x18001f0ba  cmp     ebx, r13d
0x18001f0bd  jnb     loc_18001F204
0x18001f0c3  movzx   ecx, cs:?g_cfObjectDescriptor@@3GA; uFormat
0x18001f0ca  xor     edx, edx; hMem
0x18001f0cc  add     r15, 30h ; '0'
0x18001f0d0  call    cs:__imp_SetClipboardData
0x18001f0d7  nop     dword ptr [rax+rax+00h]
0x18001f0dc  movups  xmm0, xmmword ptr [rbp+57h+fetcObjDescriptor.cfFormat]
0x18001f0e0  mov     ecx, 1
0x18001f0e5  movups  xmm1, xmmword ptr [rbp+57h+fetcObjDescriptor.dwAspect]
0x18001f0e9  mov     [r15+20h], ecx
0x18001f0ed  movups  xmmword ptr [r15], xmm0
0x18001f0f1  mov     [rsp+120h+var_E4], ecx
0x18001f0f5  xor     ecx, ecx
0x18001f0f7  movups  xmmword ptr [r15+10h], xmm1
0x18001f0fc  mov     eax, 1
0x18001f101  add     r15, 30h ; '0'
0x18001f105  add     ebx, eax
0x18001f107  mov     [rsp+120h+var_D8], ebx
0x18001f10b  cmp     [rbp+57h+var_D4], ecx
0x18001f10e  jz      loc_18001EF03
0x18001f114  cmp     [rbp+57h+var_D0], ecx
0x18001f117  jnz     loc_18001EF03
0x18001f11d  movzx   r8d, cs:?g_cfObjectDescriptor@@3GA; cf
0x18001f125  lea     pDataObj, [rbp+57h+clsid]; pclsid
0x18001f129  mov     [rsp+120h+pdwStatus], hClipWnd; pdwStatus
0x18001f12e  mov     r9d, eax; fFlags
0x18001f131  mov     [rsp+120h+ppszSrcOfCopy], hClipWnd; ppszSrcOfCopy
0x18001f136  mov     hClipWnd, [rbp+57h+var_A8]; pDataObj
0x18001f13a  mov     [rbp+57h+var_D0], eax
0x18001f13d  call    ?GetDataFromDescriptor@@YAJPEAUIDataObject@@PEAU_GUID@@IW4tagGETCLSIDFLAGS@@PEAPEAGPEAK@Z; GetDataFromDescriptor(IDataObject *,_GUID *,uint,tagGETCLSIDFLAGS,ushort * *,ulong *)
0x18001f142  test    eax, eax
0x18001f144  jnz     loc_18001EF03
0x18001f14a  mov     rax, qword ptr [rbp+57h+clsid.Data1]
0x18001f14e  mov     pDataObj, qword ptr [rbp+57h+clsid.Data4]
0x18001f152  mov     hClipWnd, rax
0x18001f155  sub     hClipWnd, qword ptr cs:CLSID_Picture_Metafile.Data1
0x18001f15c  jnz     short loc_18001F168
  ... truncated ...
```
