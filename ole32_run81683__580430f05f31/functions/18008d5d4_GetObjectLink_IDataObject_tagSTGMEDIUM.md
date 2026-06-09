# GetObjectLink(IDataObject *,tagSTGMEDIUM *)

- ea: `0x18008d5d4`
- end: `0x18008d9a0`
- name: `?GetObjectLink@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@@Z`
- size: `972`
- prototype: `HRESULT __fastcall(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800376b8`

## callees

- `0x180009374`
- `0x18000b2d4`
- `0x180038034`
- `0x18003ad30`
- `0x18003b400`
- `0x180052390`
- `0x18008d05c`
- `0x18008d5d4`
- `0x1800c3ab4`
- `0x1800c4651`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18008d824`
- `KERNELBASE!GlobalAlloc` at `0x18008d824`
- `KERNELBASE!GlobalFree` at `0x18008d968`
- `KERNELBASE!GlobalFree` at `0x18008d968`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008d8ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008d8ba`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008d84b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008d84b`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18008d72d`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x18008d72d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d907`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d8f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d907`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d940`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x18008d6f0`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x18008d6f0`

## pseudocode

```c
__int64 __fastcall GetObjectLink(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)
{
  __int64 v2; // r12
  wchar_t *v4; // r15
  wchar_t *v5; // r14
  char *v6; // r13
  unsigned int DataFromStream; // esi
  IStream *v8; // rdi
  int v9; // eax
  wchar_t *v10; // rcx
  HRESULT v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  size_t v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // ecx
  unsigned int v18; // esi
  HBITMAP v19; // rax
  tagSTGMEDIUM *v20; // rcx
  tagSTGMEDIUM *v21; // r12
  void *v22; // rax
  char *v23; // rdi
  __int64 v24; // rbx
  char *v25; // rdi
  char *v26; // rbx
  HBITMAP hBitmap; // rcx
  char *pszItemA; // [rsp+30h] [rbp-79h] BYREF
  tagSTGMEDIUM *v30; // [rsp+38h] [rbp-71h]
  unsigned int cbszFileA; // [rsp+40h] [rbp-69h] BYREF
  unsigned int cbszItemA; // [rsp+44h] [rbp-65h] BYREF
  wchar_t *pszItem; // [rsp+48h] [rbp-61h] BYREF
  unsigned int cbszClassA; // [rsp+50h] [rbp-59h] BYREF
  wchar_t *pszFile; // [rsp+58h] [rbp-51h] BYREF
  IStream *pstm; // [rsp+60h] [rbp-49h] BYREF
  _LARGE_INTEGER li; // [rsp+68h] [rbp-41h]
  char *pszClassA; // [rsp+70h] [rbp-39h] BYREF
  IMoniker *pmk; // [rsp+78h] [rbp-31h] BYREF
  wchar_t *pszClass; // [rsp+80h] [rbp-29h] BYREF
  char *pszFileA; // [rsp+88h] [rbp-21h] BYREF
  tagFORMATETC formatetc; // [rsp+90h] [rbp-19h] BYREF
  _GUID clsid; // [rsp+B0h] [rbp+7h] BYREF

  v30 = pmedium;
  pstm = 0;
  pmk = 0;
  pszFile = 0;
  v2 = 1;
  pszClass = 0;
  formatetc.dwAspect = 1;
  clsid = 0;
  v4 = 0;
  pszItem = 0;
  v5 = 0;
  pszFileA = 0;
  v6 = 0;
  pszClassA = 0;
  pszItemA = 0;
  cbszFileA = 0;
  cbszClassA = 0;
  cbszItemA = 0;
  *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
  *(&formatetc.cfFormat + 3) = 0;
  *(_QWORD *)&formatetc.tymed = 4;
  formatetc.ptd = 0;
  formatetc.lindex = -1;
  formatetc.cfFormat = g_cfLinkSource;
  DataFromStream = GetDataFromStream(pDataObj, &formatetc, 0, &pstm);
  if ( DataFromStream )
  {
    v8 = pstm;
    goto LABEL_32;
  }
  li.QuadPart = 0;
  v8 = pstm;
  DataFromStream = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))pstm->lpVtbl->Seek)(pstm, 0, 0, 0);
  if ( DataFromStream )
    goto LABEL_32;
  DataFromStream = OleLoadFromStream(v8, &IID_IMoniker, (LPVOID *)&pmk);
  if ( DataFromStream )
    goto LABEL_32;
  DataFromStream = Ole10_ParseMoniker(pmk, &pszFile, &pszItem);
  if ( DataFromStream
    || ReadClassStm(v8, &clsid)
    && (DataFromStream = GetDataFromDescriptor(pDataObj, &clsid, g_cfLinkSrcDescriptor, USE_NORMAL_CLSID, 0, 0)) != 0
    || (DataFromStream = ProgIDFromCLSID(&clsid, &pszClass)) != 0 )
  {
    v4 = pszFile;
    goto LABEL_11;
  }
  v9 = safe_lstrlenW(pszClass);
  v11 = UtPutUNICODEData(v9 + 1, v10, &pszClassA, 0, &cbszClassA);
  v6 = pszClassA;
  DataFromStream = v11;
  v4 = pszFile;
  if ( v11 )
  {
LABEL_11:
    v5 = pszItem;
LABEL_32:
    v21 = v30;
    goto LABEL_33;
  }
  if ( !pszClassA )
  {
    DataFromStream = -2147467259;
    goto LABEL_11;
  }
  v12 = safe_lstrlenW(pszFile);
  v13 = UtPutUNICODEData(v12 + 1, v4, &pszFileA, 0, &cbszFileA);
  v5 = pszItem;
  DataFromStream = v13;
  if ( v13 )
    goto LABEL_32;
  if ( pszItem )
  {
    v14 = safe_lstrlenW(pszItem);
    DataFromStream = UtPutUNICODEData(v14 + 1, v5, &pszItemA, 0, &cbszItemA);
    if ( DataFromStream )
      goto LABEL_32;
  }
  v15 = cbszClassA;
  v16 = cbszClassA + cbszFileA;
  if ( cbszClassA + cbszFileA < cbszClassA || (v17 = v16 + cbszItemA, v16 + cbszItemA < v16) || v17 + 2 < v17 )
  {
    DataFromStream = -2147024362;
    goto LABEL_32;
  }
  v18 = v17 + 2;
  if ( v17 + 2 >= GetSafeAllocSize() )
    v19 = 0;
  else
    v19 = (HBITMAP)GlobalAlloc(0x2002u, v18);
  v20 = v30;
  v30->hBitmap = v19;
  if ( !v19 )
  {
    DataFromStream = -2147024882;
    v21 = v20;
LABEL_33:
    v26 = pszItemA;
    goto $errRtn_124;
  }
  v22 = GlobalLock(v19);
  li.QuadPart = (LONGLONG)v22;
  if ( !v22 )
  {
    DataFromStream = -2147024882;
    goto LABEL_32;
  }
  DataFromStream = 0;
  memcpy_0(v22, v6, v15);
  v23 = (char *)(v15 + li.QuadPart);
  v24 = cbszFileA;
  memcpy_0(v23, pszFileA, cbszFileA);
  v25 = &v23[v24];
  v26 = pszItemA;
  if ( pszItemA )
  {
    v2 = cbszItemA;
    memcpy_0(v25, pszItemA, cbszItemA);
  }
  else
  {
    *v25 = 0;
  }
  v25[v2] = 0;
  v21 = v30;
  GlobalUnlock(v30->hBitmap);
  v8 = pstm;
$errRtn_124:
  if ( pmk )
    ((void (__fastcall *)(IMoniker *))pmk->lpVtbl->Release)(pmk);
  if ( pszClass )
    CoTaskMemFree(pszClass);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( pszFileA )
    CoTaskMemFree(pszFileA);
  if ( v26 )
    CoTaskMemFree(v26);
  if ( v8 )
    ((void (__fastcall *)(IStream *))v8->lpVtbl->Release)(v8);
  if ( DataFromStream )
  {
    hBitmap = v21->hBitmap;
    if ( hBitmap )
    {
      GlobalFree(hBitmap);
      v21->hBitmap = 0;
    }
  }
  return DataFromStream;
}

```

## disassembly

```asm
0x18008d5d4  mov     [rsp-8+arg_10], rbx
0x18008d5d9  push    rbp
0x18008d5da  push    rsi
0x18008d5db  push    rdi
0x18008d5dc  push    r12
0x18008d5de  push    r13
0x18008d5e0  push    r14
0x18008d5e2  push    r15
0x18008d5e4  lea     rbp, [rsp-27h]
0x18008d5e9  sub     rsp, 0D0h
0x18008d5f0  mov     rax, cs:__security_cookie
0x18008d5f7  xor     rax, rsp
0x18008d5fa  mov     [rbp+57h+var_40], rax
0x18008d5fe  movzx   eax, cs:?g_cfLinkSource@@3GA; ushort g_cfLinkSource
0x18008d605  lea     r9, [rbp+57h+pstm]; ppstm
0x18008d609  xor     edi, edi
0x18008d60b  mov     [rbp+57h+var_C8], pmedium
0x18008d60f  xorps   xmm0, xmm0
0x18008d612  mov     [rbp+57h+pstm], rdi
0x18008d616  xor     r8d, r8d; pmedium
0x18008d619  mov     [rbp+57h+pmk], rdi
0x18008d61d  lea     pmedium, [rbp+57h+formatetc]; pformatetc
0x18008d621  mov     [rbp+57h+pszFile], rdi
0x18008d625  lea     r12d, [rdi+1]
0x18008d629  mov     [rbp+57h+pszClass], rdi
0x18008d62d  mov     [rbp+57h+formatetc.dwAspect], r12d
0x18008d631  mov     rbx, pDataObj
0x18008d634  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x18008d638  mov     r15d, edi
0x18008d63b  mov     [rbp+57h+pszItem], rdi
0x18008d63f  mov     r14d, edi
0x18008d642  mov     [rbp+57h+pszFileA], rdi
0x18008d646  mov     r13d, edi
0x18008d649  mov     [rbp+57h+pszClassA], rdi
0x18008d64d  mov     [rbp+57h+pszItemA], rdi
0x18008d651  mov     [rbp+57h+cbszFileA], edi
0x18008d654  mov     [rbp+57h+cbszClassA], edi
0x18008d657  mov     [rbp+57h+cbszItemA], edi
0x18008d65a  mov     dword ptr [rbp+57h+formatetc+2], edi
0x18008d65d  mov     word ptr [rbp+57h+formatetc+6], di
0x18008d661  mov     qword ptr [rbp+57h+formatetc.tymed], 4
0x18008d669  mov     [rbp+57h+formatetc.ptd], rdi
0x18008d66d  mov     [rbp+57h+formatetc.lindex], 0FFFFFFFFh
0x18008d674  mov     [rbp+57h+formatetc.cfFormat], ax
0x18008d678  call    ?GetDataFromStream@@YAJPEAUIDataObject@@PEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@PEAPEAUIStream@@@Z; GetDataFromStream(IDataObject *,tagFORMATETC *,tagSTGMEDIUM *,IStream * *)
0x18008d67d  mov     esi, eax
0x18008d67f  test    eax, eax
0x18008d681  jnz     loc_18008D8CF
0x18008d687  mov     qword ptr [rbp+57h+li], rdi
0x18008d68b  xor     r9d, r9d
0x18008d68e  mov     rdi, [rbp+57h+pstm]
0x18008d692  xor     r8d, r8d
0x18008d695  mov     edx, r13d
0x18008d698  mov     pDataObj, rdi
0x18008d69b  mov     rax, [rdi]
0x18008d69e  mov     rax, [rax+28h]
0x18008d6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d6a7  mov     esi, eax
0x18008d6a9  test    eax, eax
0x18008d6ab  jnz     loc_18008D8D3
0x18008d6b1  lea     r8, [rbp+57h+pmk]; ppvObj
0x18008d6b5  mov     pDataObj, rdi; pStm
0x18008d6b8  lea     pmedium, IID_IMoniker; iidInterface
0x18008d6bf  call    OleLoadFromStream
0x18008d6c4  mov     esi, eax
0x18008d6c6  test    eax, eax
0x18008d6c8  jnz     loc_18008D8D3
0x18008d6ce  mov     pDataObj, [rbp+57h+pmk]; pmk
0x18008d6d2  lea     r8, [rbp+57h+pszItem]; pszItem
0x18008d6d6  lea     pmedium, [rbp+57h+pszFile]; pszFile
0x18008d6da  call    ?Ole10_ParseMoniker@@YAJPEAUIMoniker@@PEAPEAG1@Z; Ole10_ParseMoniker(IMoniker *,ushort * *,ushort * *)
0x18008d6df  mov     esi, eax
0x18008d6e1  test    eax, eax
0x18008d6e3  jnz     loc_18008D8C6
0x18008d6e9  lea     pmedium, [rbp+57h+clsid]; pclsid
0x18008d6ed  mov     pDataObj, rdi; pStm
0x18008d6f0  call    cs:__imp_ReadClassStm
0x18008d6f6  test    eax, eax
0x18008d6f8  jz      short loc_18008D725
0x18008d6fa  movzx   r8d, cs:?g_cfLinkSrcDescriptor@@3GA; cf
0x18008d702  lea     pmedium, [rbp+57h+clsid]; pclsid
0x18008d706  mov     [rsp+100h+pdwStatus], r13; pdwStatus
0x18008d70b  mov     r9d, r12d; fFlags
0x18008d70e  mov     pDataObj, rbx; pDataObj
0x18008d711  mov     [rsp+100h+ppszSrcOfCopy], r13; ppszSrcOfCopy
0x18008d716  call    ?GetDataFromDescriptor@@YAJPEAUIDataObject@@PEAU_GUID@@IW4tagGETCLSIDFLAGS@@PEAPEAGPEAK@Z; GetDataFromDescriptor(IDataObject *,_GUID *,uint,tagGETCLSIDFLAGS,ushort * *,ulong *)
0x18008d71b  mov     esi, eax
0x18008d71d  test    eax, eax
0x18008d71f  jnz     loc_18008D8C6
0x18008d725  lea     pmedium, [rbp+57h+pszClass]; lplpszProgID
0x18008d729  lea     pDataObj, [rbp+57h+clsid]; clsid
0x18008d72d  call    cs:__imp_ProgIDFromCLSID
0x18008d733  mov     esi, eax
0x18008d735  test    eax, eax
0x18008d737  jnz     loc_18008D8C6
0x18008d73d  mov     pDataObj, [rbp+57h+pszClass]; string
0x18008d741  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008d746  lea     pmedium, [rbp+57h+cbszClassA]
0x18008d74a  add     eax, r12d
0x18008d74d  mov     [rsp+100h+ppszSrcOfCopy], pmedium; pdwResultLen
0x18008d752  lea     r8, [rbp+57h+pszClassA]; pszANSI
0x18008d756  mov     pmedium, pDataObj; str
0x18008d759  xor     r9d, r9d; pszOLESTR
0x18008d75c  mov     ecx, eax; ulLength
0x18008d75e  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x18008d763  mov     r13, [rbp+57h+pszClassA]
0x18008d767  mov     esi, eax
0x18008d769  mov     r15, [rbp+57h+pszFile]
0x18008d76d  test    eax, eax
0x18008d76f  jnz     short loc_18008D77B
0x18008d771  test    r13, r13
0x18008d774  jnz     short loc_18008D784
0x18008d776  mov     esi, 80004005h
0x18008d77b  mov     r14, [rbp+57h+pszItem]
0x18008d77f  jmp     loc_18008D8D3
0x18008d784  mov     pDataObj, r15; string
0x18008d787  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008d78c  lea     pDataObj, [rbp+57h+cbszFileA]
0x18008d790  add     eax, r12d
0x18008d793  mov     [rsp+100h+ppszSrcOfCopy], pDataObj; pdwResultLen
0x18008d798  lea     r8, [rbp+57h+pszFileA]; pszANSI
0x18008d79c  mov     ecx, eax; ulLength
0x18008d79e  xor     r9d, r9d; pszOLESTR
0x18008d7a1  mov     pmedium, r15; str
0x18008d7a4  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x18008d7a9  mov     r14, [rbp+57h+pszItem]
0x18008d7ad  mov     esi, eax
0x18008d7af  test    eax, eax
0x18008d7b1  jnz     loc_18008D8D3
0x18008d7b7  test    r14, r14
0x18008d7ba  jz      short loc_18008D7EB
0x18008d7bc  mov     pDataObj, r14; string
0x18008d7bf  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008d7c4  lea     pDataObj, [rbp+57h+cbszItemA]
0x18008d7c8  add     eax, r12d
0x18008d7cb  mov     [rsp+100h+ppszSrcOfCopy], pDataObj; pdwResultLen
0x18008d7d0  lea     r8, [rbp+57h+pszItemA]; pszANSI
0x18008d7d4  mov     ecx, eax; ulLength
0x18008d7d6  xor     r9d, r9d; pszOLESTR
0x18008d7d9  mov     pmedium, r14; str
0x18008d7dc  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x18008d7e1  mov     esi, eax
0x18008d7e3  test    eax, eax
0x18008d7e5  jnz     loc_18008D8D3
0x18008d7eb  mov     ebx, [rbp+57h+cbszClassA]
0x18008d7ee  mov     eax, [rbp+57h+cbszFileA]
0x18008d7f1  add     eax, ebx
0x18008d7f3  cmp     eax, ebx
0x18008d7f5  jb      short loc_18008D807
0x18008d7f7  mov     ecx, [rbp+57h+cbszItemA]
0x18008d7fa  add     ecx, eax
0x18008d7fc  cmp     ecx, eax
0x18008d7fe  jb      short loc_18008D807
0x18008d800  lea     eax, [pDataObj+2]
0x18008d803  cmp     eax, ecx
0x18008d805  jnb     short loc_18008D811
0x18008d807  mov     esi, 80070216h
0x18008d80c  jmp     loc_18008D8D3
0x18008d811  mov     esi, eax
0x18008d813  call    GetSafeAllocSize
0x18008d818  cmp     rsi, rax
0x18008d81b  jnb     short loc_18008D82C
0x18008d81d  mov     edx, esi; dwBytes
0x18008d81f  mov     ecx, 2002h; uFlags
0x18008d824  call    cs:__imp_GlobalAlloc
0x18008d82a  jmp     short loc_18008D82E
0x18008d82c  xor     eax, eax
0x18008d82e  mov     pDataObj, [rbp+57h+var_C8]
0x18008d832  mov     [pDataObj+8], rax
0x18008d836  test    rax, rax
0x18008d839  jnz     short loc_18008D848
0x18008d83b  mov     esi, 8007000Eh
0x18008d840  mov     r12, pDataObj
0x18008d843  jmp     loc_18008D8D7
0x18008d848  mov     pDataObj, rax; hMem
0x18008d84b  call    cs:__imp_GlobalLock
0x18008d851  mov     qword ptr [rbp+57h+li], rax
0x18008d855  test    rax, rax
0x18008d858  jnz     short loc_18008D861
0x18008d85a  mov     esi, 8007000Eh
0x18008d85f  jmp     short loc_18008D8D3
0x18008d861  mov     r8, rbx; Size
0x18008d864  mov     pmedium, r13; Src
0x18008d867  mov     pDataObj, rax; void *
0x18008d86a  xor     esi, esi
0x18008d86c  call    memcpy_0
0x18008d871  mov     rdi, qword ptr [rbp+57h+li]
0x18008d875  mov     pmedium, [rbp+57h+pszFileA]; Src
0x18008d879  add     rdi, rbx
0x18008d87c  mov     ebx, [rbp+57h+cbszFileA]
0x18008d87f  mov     pDataObj, rdi; void *
0x18008d882  mov     r8d, ebx; Size
0x18008d885  call    memcpy_0
0x18008d88a  add     rdi, rbx
0x18008d88d  mov     rbx, [rbp+57h+pszItemA]
0x18008d891  test    rbx, rbx
0x18008d894  jz      short loc_18008D8AA
0x18008d896  mov     r12d, [rbp+57h+cbszItemA]
0x18008d89a  mov     pmedium, rbx; Src
0x18008d89d  mov     r8d, r12d; Size
0x18008d8a0  mov     pDataObj, rdi; void *
0x18008d8a3  call    memcpy_0
0x18008d8a8  jmp     short loc_18008D8AD
0x18008d8aa  mov     [rdi], sil
0x18008d8ad  mov     [rdi+r12], sil
0x18008d8b1  mov     r12, [rbp+57h+var_C8]
0x18008d8b5  mov     pDataObj, [r12+8]; hMem
0x18008d8ba  call    cs:__imp_GlobalUnlock
0x18008d8c0  mov     rdi, [rbp+57h+pstm]
0x18008d8c4  jmp     short $errRtn_124
0x18008d8c6  mov     r15, [rbp+57h+pszFile]
0x18008d8ca  jmp     loc_18008D77B
0x18008d8cf  mov     rdi, [rbp+57h+pstm]
0x18008d8d3  mov     r12, [rbp+57h+var_C8]
0x18008d8d7  mov     rbx, [rbp+57h+pszItemA]
0x18008d8db  mov     pDataObj, [rbp+57h+pmk]
0x18008d8df  test    pDataObj, pDataObj
0x18008d8e2  jz      short loc_18008D8F0
0x18008d8e4  mov     rax, [pDataObj]
0x18008d8e7  mov     rax, [rax+10h]
0x18008d8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d8f0  mov     pDataObj, [rbp+57h+pszClass]; pv
0x18008d8f4  test    pDataObj, pDataObj
0x18008d8f7  jz      short loc_18008D8FF
0x18008d8f9  call    cs:__imp_CoTaskMemFree
0x18008d8ff  test    r15, r15
0x18008d902  jz      short loc_18008D90D
0x18008d904  mov     pDataObj, r15; pv
0x18008d907  call    cs:__imp_CoTaskMemFree
0x18008d90d  test    r14, r14
0x18008d910  jz      short loc_18008D91B
0x18008d912  mov     pDataObj, r14; pv
0x18008d915  call    cs:__imp_CoTaskMemFree
0x18008d91b  test    r13, r13
0x18008d91e  jz      short loc_18008D929
0x18008d920  mov     pDataObj, r13; pv
0x18008d923  call    cs:__imp_CoTaskMemFree
0x18008d929  mov     pDataObj, [rbp+57h+pszFileA]; pv
0x18008d92d  test    pDataObj, pDataObj
0x18008d930  jz      short loc_18008D938
0x18008d932  call    cs:__imp_CoTaskMemFree
0x18008d938  test    rbx, rbx
0x18008d93b  jz      short loc_18008D946
0x18008d93d  mov     pDataObj, rbx; pv
0x18008d940  call    cs:__imp_CoTaskMemFree
0x18008d946  test    rdi, rdi
0x18008d949  jz      short loc_18008D95A
0x18008d94b  mov     rax, [rdi]
0x18008d94e  mov     pDataObj, rdi
0x18008d951  mov     rax, [rax+10h]
0x18008d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d95a  test    esi, esi
0x18008d95c  jz      short loc_18008D977
0x18008d95e  mov     pDataObj, [r12+8]; hMem
0x18008d963  test    pDataObj, pDataObj
0x18008d966  jz      short loc_18008D977
0x18008d968  call    cs:__imp_GlobalFree
0x18008d96e  mov     qword ptr [r12+8], 0
0x18008d977  mov     eax, esi
0x18008d979  mov     pDataObj, [rbp+57h+var_40]
0x18008d97d  xor     pDataObj, rsp; StackCookie
0x18008d980  call    __security_check_cookie
0x18008d985  mov     rbx, [rsp+100h+arg_10]
0x18008d98d  add     rsp, 0D0h
0x18008d994  pop     r15
0x18008d996  pop     r14
0x18008d998  pop     r13
0x18008d99a  pop     r12
0x18008d99c  pop     rdi
0x18008d99d  pop     rsi
0x18008d99e  pop     rbp
0x18008d99f  retn
```
