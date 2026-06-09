# GetObjectLink(IDataObject *,tagSTGMEDIUM *)

- ea: `0x180088adc`
- end: `0x180088efb`
- name: `?GetObjectLink@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@@Z`
- size: `1055`
- prototype: `HRESULT __fastcall(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b5f8`

## callees

- `0x1800077fc`
- `0x18000a574`
- `0x18003bf64`
- `0x18003f034`
- `0x18003f420`
- `0x180046460`
- `0x180088550`
- `0x180088adc`
- `0x1800cdb48`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180088d43`
- `KERNELBASE!GlobalAlloc` at `0x180088d43`
- `KERNELBASE!GlobalFree` at `0x180088e46`
- `KERNELBASE!GlobalFree` at `0x180088e46`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180088ed3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180088ed3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180088d6d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180088d6d`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180088c3e`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x180088c3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088e05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088e05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088e19`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x180088bfb`
- `api-ms-win-core-com-l2-1-1!ReadClassStm` at `0x180088bfb`

## pseudocode

```c
__int64 __fastcall GetObjectLink(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)
{
  __int64 v2; // r13
  wchar_t *v4; // r15
  wchar_t *v5; // rsi
  char *v6; // r12
  unsigned int DataFromStream; // edi
  IStream *v8; // r14
  int v9; // eax
  wchar_t *v10; // rcx
  HRESULT v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  size_t v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // ecx
  HBITMAP v18; // rax
  tagSTGMEDIUM *v19; // rcx
  tagSTGMEDIUM *v20; // r13
  char *v21; // rax
  char *v22; // r14
  char *v23; // rbx
  HBITMAP hBitmap; // rcx
  char *v26; // r14
  __int64 v27; // rbx
  char *v28; // r14
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

  formatetc.lindex = -1;
  v30 = pmedium;
  pstm = 0;
  pmk = 0;
  v2 = 1;
  pszFile = 0;
  formatetc.dwAspect = 1;
  clsid = 0;
  v4 = 0;
  pszClass = 0;
  v5 = 0;
  pszItem = 0;
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
  formatetc.cfFormat = g_cfLinkSource;
  DataFromStream = GetDataFromStream(pDataObj, &formatetc, 0, &pstm);
  if ( DataFromStream )
    goto LABEL_25;
  li.QuadPart = 0;
  v8 = pstm;
  DataFromStream = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))pstm->lpVtbl->Seek)(pstm, 0, 0, 0);
  if ( DataFromStream )
    goto LABEL_26;
  DataFromStream = OleLoadFromStream(v8, &IID_IMoniker, (LPVOID *)&pmk);
  if ( DataFromStream )
    goto LABEL_26;
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
LABEL_26:
    v20 = v30;
    goto LABEL_27;
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
    goto LABEL_26;
  if ( pszItem )
  {
    v14 = safe_lstrlenW(pszItem);
    DataFromStream = UtPutUNICODEData(v14 + 1, v5, &pszItemA, 0, &cbszItemA);
    if ( DataFromStream )
      goto LABEL_26;
  }
  v15 = cbszClassA;
  v16 = cbszClassA + cbszFileA;
  if ( cbszClassA + cbszFileA < cbszClassA || (v17 = v16 + cbszItemA, v16 + cbszItemA < v16) || v17 + 2 < v17 )
  {
    DataFromStream = -2147024362;
    goto LABEL_26;
  }
  li.QuadPart = v17 + 2;
  DataFromStream = 0;
  if ( li.QuadPart >= GetSafeAllocSize() )
    v18 = 0;
  else
    v18 = (HBITMAP)GlobalAlloc(0x2002u, li.QuadPart);
  v19 = v30;
  v30->hBitmap = v18;
  if ( !v18 )
  {
    DataFromStream = -2147024882;
    v20 = v19;
LABEL_27:
    v23 = pszItemA;
    goto $errRtn_97;
  }
  v21 = (char *)GlobalLock(v18);
  v22 = v21;
  if ( !v21 )
  {
    DataFromStream = -2147024882;
LABEL_25:
    v8 = pstm;
    goto LABEL_26;
  }
  memcpy_0(v21, v6, v15);
  v26 = &v22[v15];
  v27 = cbszFileA;
  memcpy_0(v26, pszFileA, cbszFileA);
  v28 = &v26[v27];
  v23 = pszItemA;
  if ( pszItemA )
  {
    v2 = cbszItemA;
    memcpy_0(v28, pszItemA, cbszItemA);
  }
  else
  {
    *v28 = 0;
  }
  v28[v2] = 0;
  v20 = v30;
  GlobalUnlock(v30->hBitmap);
  v8 = pstm;
$errRtn_97:
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
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v8 )
    ((void (__fastcall *)(IStream *))v8->lpVtbl->Release)(v8);
  if ( DataFromStream )
  {
    hBitmap = v20->hBitmap;
    if ( hBitmap )
    {
      GlobalFree(hBitmap);
      v20->hBitmap = 0;
    }
  }
  return DataFromStream;
}

```

## disassembly

```asm
0x180088adc  mov     [rsp-8+arg_10], rbx
0x180088ae1  push    rbp
0x180088ae2  push    rsi
0x180088ae3  push    rdi
0x180088ae4  push    r12
0x180088ae6  push    r13
0x180088ae8  push    r14
0x180088aea  push    r15
0x180088aec  lea     rbp, [rsp-27h]
0x180088af1  sub     rsp, 0D0h
0x180088af8  mov     rax, cs:__security_cookie
0x180088aff  xor     rax, rsp
0x180088b02  mov     [rbp+57h+var_40], rax
0x180088b06  movzx   eax, cs:?g_cfLinkSource@@3GA; ushort g_cfLinkSource
0x180088b0d  lea     r9, [rbp+57h+pstm]; ppstm
0x180088b11  or      [rbp+57h+formatetc.lindex], 0FFFFFFFFh
0x180088b15  xor     r14d, r14d
0x180088b18  mov     [rbp+57h+var_C8], pmedium
0x180088b1c  xorps   xmm0, xmm0
0x180088b1f  xor     r8d, r8d; pmedium
0x180088b22  mov     [rbp+57h+pstm], r14
0x180088b26  lea     pmedium, [rbp+57h+formatetc]; pformatetc
0x180088b2a  mov     [rbp+57h+pmk], r14
0x180088b2e  lea     r13d, [r14+1]
0x180088b32  mov     [rbp+57h+pszFile], r14
0x180088b36  mov     [rbp+57h+formatetc.dwAspect], r13d
0x180088b3a  mov     rbx, pDataObj
0x180088b3d  movups  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x180088b41  mov     r15d, r14d
0x180088b44  mov     [rbp+57h+pszClass], r14
0x180088b48  mov     esi, r14d
0x180088b4b  mov     [rbp+57h+pszItem], r14
0x180088b4f  mov     [rbp+57h+pszFileA], r14
0x180088b53  mov     r12d, r14d
0x180088b56  mov     [rbp+57h+pszClassA], r14
0x180088b5a  mov     [rbp+57h+pszItemA], r14
0x180088b5e  mov     [rbp+57h+cbszFileA], r14d
0x180088b62  mov     [rbp+57h+cbszClassA], r14d
0x180088b66  mov     [rbp+57h+cbszItemA], r14d
0x180088b6a  mov     dword ptr [rbp+57h+formatetc+2], r14d
0x180088b6e  mov     word ptr [rbp+57h+formatetc+6], r14w
0x180088b73  mov     qword ptr [rbp+57h+formatetc.tymed], 4
0x180088b7b  mov     [rbp+57h+formatetc.ptd], r14
0x180088b7f  mov     [rbp+57h+formatetc.cfFormat], ax
0x180088b83  call    ?GetDataFromStream@@YAJPEAUIDataObject@@PEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@PEAPEAUIStream@@@Z; GetDataFromStream(IDataObject *,tagFORMATETC *,tagSTGMEDIUM *,IStream * *)
0x180088b88  mov     edi, eax
0x180088b8a  test    eax, eax
0x180088b8c  jnz     loc_180088D8A
0x180088b92  mov     qword ptr [rbp+57h+li], r14
0x180088b96  xor     r9d, r9d
0x180088b99  mov     r14, [rbp+57h+pstm]
0x180088b9d  xor     r8d, r8d
0x180088ba0  mov     edx, r12d
0x180088ba3  mov     pDataObj, r14
0x180088ba6  mov     rax, [r14]
0x180088ba9  mov     rax, [rax+28h]
0x180088bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088bb2  mov     edi, eax
0x180088bb4  test    eax, eax
0x180088bb6  jnz     loc_180088D8E
0x180088bbc  lea     r8, [rbp+57h+pmk]; ppvObj
0x180088bc0  mov     pDataObj, r14; pStm
0x180088bc3  lea     pmedium, IID_IMoniker; iidInterface
0x180088bca  call    OleLoadFromStream
0x180088bcf  mov     edi, eax
0x180088bd1  test    eax, eax
0x180088bd3  jnz     loc_180088D8E
0x180088bd9  mov     pDataObj, [rbp+57h+pmk]; pmk
0x180088bdd  lea     r8, [rbp+57h+pszItem]; pszItem
0x180088be1  lea     pmedium, [rbp+57h+pszFile]; pszFile
0x180088be5  call    ?Ole10_ParseMoniker@@YAJPEAUIMoniker@@PEAPEAG1@Z; Ole10_ParseMoniker(IMoniker *,ushort * *,ushort * *)
0x180088bea  mov     edi, eax
0x180088bec  test    eax, eax
0x180088bee  jnz     loc_180088EF2
0x180088bf4  lea     pmedium, [rbp+57h+clsid]; pclsid
0x180088bf8  mov     pDataObj, r14; pStm
0x180088bfb  call    cs:__imp_ReadClassStm
0x180088c02  nop     dword ptr [rax+rax+00h]
0x180088c07  test    eax, eax
0x180088c09  jz      short loc_180088C36
0x180088c0b  movzx   r8d, cs:?g_cfLinkSrcDescriptor@@3GA; cf
0x180088c13  lea     pmedium, [rbp+57h+clsid]; pclsid
0x180088c17  and     [rsp+100h+var_D8], r12
0x180088c1c  mov     r9d, r13d; fFlags
0x180088c1f  and     [rsp+100h+pdwResultLen], r12
0x180088c24  mov     pDataObj, rbx; pDataObj
0x180088c27  call    ?GetDataFromDescriptor@@YAJPEAUIDataObject@@PEAU_GUID@@IW4tagGETCLSIDFLAGS@@PEAPEAGPEAK@Z; GetDataFromDescriptor(IDataObject *,_GUID *,uint,tagGETCLSIDFLAGS,ushort * *,ulong *)
0x180088c2c  mov     edi, eax
0x180088c2e  test    eax, eax
0x180088c30  jnz     loc_180088EF2
0x180088c36  lea     pmedium, [rbp+57h+pszClass]; lplpszProgID
0x180088c3a  lea     pDataObj, [rbp+57h+clsid]; clsid
0x180088c3e  call    cs:__imp_ProgIDFromCLSID
0x180088c45  nop     dword ptr [rax+rax+00h]
0x180088c4a  mov     edi, eax
0x180088c4c  test    eax, eax
0x180088c4e  jnz     loc_180088EF2
0x180088c54  mov     pDataObj, [rbp+57h+pszClass]; string
0x180088c58  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180088c5d  lea     pmedium, [rbp+57h+cbszClassA]
0x180088c61  add     eax, r13d
0x180088c64  mov     [rsp+100h+pdwResultLen], pmedium; pdwResultLen
0x180088c69  lea     r8, [rbp+57h+pszClassA]; pszANSI
0x180088c6d  mov     pmedium, pDataObj; str
0x180088c70  xor     r9d, r9d; pszOLESTR
0x180088c73  mov     ecx, eax; ulLength
0x180088c75  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x180088c7a  mov     r12, [rbp+57h+pszClassA]
0x180088c7e  mov     edi, eax
0x180088c80  mov     r15, [rbp+57h+pszFile]
0x180088c84  test    eax, eax
0x180088c86  jnz     short loc_180088C92
0x180088c88  test    r12, r12
0x180088c8b  jnz     short loc_180088C9B
0x180088c8d  mov     edi, 80004005h
0x180088c92  mov     rsi, [rbp+57h+pszItem]
0x180088c96  jmp     loc_180088D8E
0x180088c9b  mov     pDataObj, r15; string
0x180088c9e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180088ca3  lea     pDataObj, [rbp+57h+cbszFileA]
0x180088ca7  add     eax, r13d
0x180088caa  mov     [rsp+100h+pdwResultLen], pDataObj; pdwResultLen
0x180088caf  lea     r8, [rbp+57h+pszFileA]; pszANSI
0x180088cb3  mov     ecx, eax; ulLength
0x180088cb5  xor     r9d, r9d; pszOLESTR
0x180088cb8  mov     pmedium, r15; str
0x180088cbb  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x180088cc0  mov     rsi, [rbp+57h+pszItem]
0x180088cc4  mov     edi, eax
0x180088cc6  test    eax, eax
0x180088cc8  jnz     loc_180088D8E
0x180088cce  test    rsi, rsi
0x180088cd1  jz      short loc_180088D02
0x180088cd3  mov     pDataObj, rsi; string
0x180088cd6  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180088cdb  lea     pDataObj, [rbp+57h+cbszItemA]
0x180088cdf  add     eax, r13d
0x180088ce2  mov     [rsp+100h+pdwResultLen], pDataObj; pdwResultLen
0x180088ce7  lea     r8, [rbp+57h+pszItemA]; pszANSI
0x180088ceb  mov     ecx, eax; ulLength
0x180088ced  xor     r9d, r9d; pszOLESTR
0x180088cf0  mov     pmedium, rsi; str
0x180088cf3  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x180088cf8  mov     edi, eax
0x180088cfa  test    eax, eax
0x180088cfc  jnz     loc_180088D8E
0x180088d02  mov     ebx, [rbp+57h+cbszClassA]
0x180088d05  mov     eax, [rbp+57h+cbszFileA]
0x180088d08  add     eax, ebx
0x180088d0a  cmp     eax, ebx
0x180088d0c  jb      loc_180088EE8
0x180088d12  mov     ecx, [rbp+57h+cbszItemA]
0x180088d15  add     ecx, eax
0x180088d17  cmp     ecx, eax
0x180088d19  jb      loc_180088EE8
0x180088d1f  lea     eax, [pDataObj+2]
0x180088d22  cmp     eax, ecx
0x180088d24  jb      loc_180088EE8
0x180088d2a  mov     qword ptr [rbp+57h+li], rax
0x180088d2e  xor     edi, edi
0x180088d30  call    GetSafeAllocSize
0x180088d35  mov     pmedium, qword ptr [rbp+57h+li]; dwBytes
0x180088d39  cmp     pmedium, rax
0x180088d3c  jnb     short loc_180088D51
0x180088d3e  mov     ecx, 2002h; uFlags
0x180088d43  call    cs:__imp_GlobalAlloc
0x180088d4a  nop     dword ptr [rax+rax+00h]
0x180088d4f  jmp     short loc_180088D53
0x180088d51  xor     eax, eax
0x180088d53  mov     pDataObj, [rbp+57h+var_C8]
0x180088d57  mov     [pDataObj+8], rax
0x180088d5b  test    rax, rax
0x180088d5e  jnz     short loc_180088D6A
0x180088d60  mov     edi, 8007000Eh
0x180088d65  mov     r13, pDataObj
0x180088d68  jmp     short loc_180088D92
0x180088d6a  mov     pDataObj, rax; hMem
0x180088d6d  call    cs:__imp_GlobalLock
0x180088d74  nop     dword ptr [rax+rax+00h]
0x180088d79  mov     r14, rax
0x180088d7c  test    rax, rax
0x180088d7f  jnz     loc_180088E81
0x180088d85  mov     edi, 8007000Eh
0x180088d8a  mov     r14, [rbp+57h+pstm]
0x180088d8e  mov     r13, [rbp+57h+var_C8]
0x180088d92  mov     rbx, [rbp+57h+pszItemA]
0x180088d96  mov     pDataObj, [rbp+57h+pmk]
0x180088d9a  test    pDataObj, pDataObj
0x180088d9d  jz      short loc_180088DAB
0x180088d9f  mov     rax, [pDataObj]
0x180088da2  mov     rax, [rax+10h]
0x180088da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088dab  mov     pDataObj, [rbp+57h+pszClass]; pv
0x180088daf  test    pDataObj, pDataObj
0x180088db2  jz      short loc_180088DC0
0x180088db4  call    cs:__imp_CoTaskMemFree
0x180088dbb  nop     dword ptr [rax+rax+00h]
0x180088dc0  test    r15, r15
0x180088dc3  jz      short loc_180088DD4
0x180088dc5  mov     pDataObj, r15; pv
0x180088dc8  call    cs:__imp_CoTaskMemFree
0x180088dcf  nop     dword ptr [rax+rax+00h]
0x180088dd4  test    rsi, rsi
0x180088dd7  jz      short loc_180088DE8
0x180088dd9  mov     pDataObj, rsi; pv
0x180088ddc  call    cs:__imp_CoTaskMemFree
0x180088de3  nop     dword ptr [rax+rax+00h]
0x180088de8  test    r12, r12
0x180088deb  jz      short loc_180088DFC
0x180088ded  mov     pDataObj, r12; pv
0x180088df0  call    cs:__imp_CoTaskMemFree
0x180088df7  nop     dword ptr [rax+rax+00h]
0x180088dfc  mov     pDataObj, [rbp+57h+pszFileA]; pv
0x180088e00  test    pDataObj, pDataObj
0x180088e03  jz      short loc_180088E11
0x180088e05  call    cs:__imp_CoTaskMemFree
0x180088e0c  nop     dword ptr [rax+rax+00h]
0x180088e11  test    rbx, rbx
0x180088e14  jz      short loc_180088E25
0x180088e16  mov     pDataObj, rbx; pv
0x180088e19  call    cs:__imp_CoTaskMemFree
0x180088e20  nop     dword ptr [rax+rax+00h]
0x180088e25  test    r14, r14
0x180088e28  jz      short loc_180088E39
0x180088e2a  mov     rax, [r14]
0x180088e2d  mov     pDataObj, r14
0x180088e30  mov     rax, [rax+10h]
0x180088e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e39  test    edi, edi
0x180088e3b  jz      short loc_180088E57
0x180088e3d  mov     pDataObj, [r13+8]; hMem
0x180088e41  test    pDataObj, pDataObj
0x180088e44  jz      short loc_180088E57
0x180088e46  call    cs:__imp_GlobalFree
0x180088e4d  nop     dword ptr [rax+rax+00h]
0x180088e52  and     qword ptr [r13+8], 0
0x180088e57  mov     eax, edi
0x180088e59  mov     pDataObj, [rbp+57h+var_40]
0x180088e5d  xor     pDataObj, rsp; StackCookie
0x180088e60  call    __security_check_cookie
0x180088e65  mov     rbx, [rsp+100h+arg_10]
0x180088e6d  add     rsp, 0D0h
0x180088e74  pop     r15
0x180088e76  pop     r14
0x180088e78  pop     r13
0x180088e7a  pop     r12
0x180088e7c  pop     rdi
0x180088e7d  pop     rsi
0x180088e7e  pop     rbp
0x180088e7f  retn
0x180088e81  mov     r8, rbx; Size
0x180088e84  mov     pmedium, r12; Src
0x180088e87  mov     pDataObj, r14; void *
0x180088e8a  call    memcpy_0
0x180088e8f  mov     pmedium, [rbp+57h+pszFileA]; Src
0x180088e93  add     r14, rbx
0x180088e96  mov     ebx, [rbp+57h+cbszFileA]
0x180088e99  mov     pDataObj, r14; void *
0x180088e9c  mov     r8d, ebx; Size
0x180088e9f  call    memcpy_0
0x180088ea4  add     r14, rbx
0x180088ea7  mov     rbx, [rbp+57h+pszItemA]
0x180088eab  test    rbx, rbx
0x180088eae  jz      short loc_180088EC4
0x180088eb0  mov     r13d, [rbp+57h+cbszItemA]
0x180088eb4  mov     pmedium, rbx; Src
0x180088eb7  mov     r8d, r13d; Size
0x180088eba  mov     pDataObj, r14; void *
0x180088ebd  call    memcpy_0
0x180088ec2  jmp     short loc_180088EC7
0x180088ec4  mov     [r14], dil
0x180088ec7  mov     [r14+r13], dil
0x180088ecb  mov     r13, [rbp+57h+var_C8]
0x180088ecf  mov     pDataObj, [r13+8]; hMem
0x180088ed3  call    cs:__imp_GlobalUnlock
0x180088eda  nop     dword ptr [rax+rax+00h]
0x180088edf  mov     r14, [rbp+57h+pstm]
0x180088ee3  jmp     $errRtn_97
0x180088ee8  mov     edi, 80070216h
0x180088eed  jmp     loc_180088D8E
0x180088ef2  mov     r15, [rbp+57h+pszFile]
0x180088ef6  jmp     loc_180088C92
```
