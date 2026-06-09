# CClipDataObject::GetObjectDescriptorFromOle1(uint,tagSTGMEDIUM *)

- ea: `0x180091294`
- end: `0x1800914d5`
- name: `?GetObjectDescriptorFromOle1@CClipDataObject@@AEAAJIPEAUtagSTGMEDIUM@@@Z`
- size: `577`
- prototype: `HRESULT __fastcall(CClipDataObject *this, unsigned int cf, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800914dc`

## callees

- `0x180009374`
- `0x18000b2d4`
- `0x18001248c`
- `0x18001b810`
- `0x180052390`
- `0x180053014`
- `0x180084a38`
- `0x180090608`
- `0x180091294`
- `0x1800bf6c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800914ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800913cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800913cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091487`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091495`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x180091344`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x180091344`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetObjectDescriptorFromOle1(
        CClipDataObject *this,
        unsigned int cf,
        tagSTGMEDIUM *pmedium)
{
  wchar_t *v5; // rdi
  CClipDataObject *v6; // rcx
  HRESULT v7; // eax
  wchar_t *v8; // rsi
  unsigned int v9; // ebx
  wchar_t *v10; // r14
  int v12; // eax
  int v13; // r8d
  unsigned __int64 v14; // r15
  wchar_t *v15; // rax
  unsigned int v16; // edx
  __int16 v17; // r10
  HBITMAP v18; // rax
  unsigned int ppszItem; // [rsp+20h] [rbp-E0h]
  wchar_t *pszFile; // [rsp+40h] [rbp-C0h] BYREF
  int cb; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *pszClass; // [rsp+50h] [rbp-B0h] BYREF
  _POINTL pointl; // [rsp+58h] [rbp-A8h] BYREF
  tagSIZE sizel; // [rsp+60h] [rbp-A0h] BYREF
  _GUID pszItem; // [rsp+70h] [rbp-90h] BYREF
  tagSTGMEDIUM *v26; // [rsp+80h] [rbp-80h]
  _GUID clsid; // [rsp+90h] [rbp-70h] BYREF
  wchar_t szFullName[400]; // [rsp+A0h] [rbp-60h] BYREF

  v26 = pmedium;
  pszClass = 0;
  pszFile = 0;
  *(_QWORD *)&pszItem.Data1 = 0;
  sizel = 0;
  pointl = 0;
  v5 = 0;
  clsid = 0;
  memset_0(szFullName, 0, sizeof(szFullName));
  cb = 800;
  v7 = CClipDataObject::GetAndTranslateOle1(v6, cf, &pszClass, &pszFile, (wchar_t **)&pszItem, 0);
  v8 = pszClass;
  v9 = v7;
  v10 = *(wchar_t **)&pszItem.Data1;
  if ( v7 )
    goto $errRtn_131;
  v9 = CLSIDFromOle1Class(pszClass, &clsid, 1);
  if ( v9 )
    goto $errRtn_131;
  if ( QueryClassesRootValueW(v8, szFullName, &cb) )
  {
    if ( (unsigned int)safe_lstrlenW(v8) >= 0x190 )
      return 2147942487LL;
    StringCchCopyW(szFullName, 0x190u, v8);
  }
  safe_lstrlenW(v10);
  v12 = safe_lstrlenW(pszFile);
  v14 = v13 + v12 + 2;
  if ( 2 * v14 >= GetSafeAllocSize() )
  {
    v5 = 0;
LABEL_15:
    v9 = -2147024882;
    goto $errRtn_131;
  }
  v15 = (wchar_t *)HeapAlloc(g_hHeap, 0, 2 * v14);
  v5 = v15;
  if ( !v15 )
    goto LABEL_15;
  StringCchCopyW(v15, v14, pszFile);
  if ( v10 && *v10 != v17 )
  {
    StringCchCatW(v5, v14, L"\\");
    StringCchCatW(v5, v14, v10);
  }
  pszItem = clsid;
  v18 = (HBITMAP)CreateObjectDescriptor(&pszItem, v16, &sizel, &pointl, ppszItem, szFullName, v5);
  if ( !v18 )
    goto LABEL_15;
  v26->hBitmap = v18;
  this->m_hOle1 = v18;
$errRtn_131:
  if ( v8 )
    CoTaskMemFree(v8);
  if ( pszFile )
    CoTaskMemFree(pszFile);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v5 )
    HeapFree(g_hHeap, 0, v5);
  return v9;
}

```

## disassembly

```asm
0x180091294  push    rbp
0x180091296  push    rbx
0x180091297  push    rsi
0x180091298  push    rdi
0x180091299  push    r13
0x18009129b  push    r14
0x18009129d  push    r15
0x18009129f  lea     rbp, [rsp-2D0h]
0x1800912a7  sub     rsp, 3D0h
0x1800912ae  mov     rax, cs:__security_cookie
0x1800912b5  xor     rax, rsp
0x1800912b8  mov     [rbp+300h+var_40], rax
0x1800912bf  xor     r15d, r15d
0x1800912c2  mov     [rbp+300h+var_380], pmedium
0x1800912c6  mov     ebx, edx
0x1800912c8  mov     [rsp+400h+pszClass], r15
0x1800912cd  mov     r13, this
0x1800912d0  mov     [rsp+400h+pszFile], r15
0x1800912d5  xorps   xmm0, xmm0
0x1800912d8  mov     qword ptr [rsp+400h+pszItem], r15
0x1800912dd  mov     esi, 320h
0x1800912e2  mov     qword ptr [rsp+400h+sizel.cx], r15
0x1800912e7  mov     r8d, esi; Size
0x1800912ea  mov     qword ptr [rsp+400h+pointl.x], r15
0x1800912ef  xor     edx, edx; Val
0x1800912f1  lea     this, [rbp+300h+szFullName]; void *
0x1800912f5  mov     edi, r15d
0x1800912f8  movups  xmmword ptr [rbp+300h+clsid.Data1], xmm0
0x1800912fc  call    memset_0
0x180091301  lea     rax, [rsp+400h+pszItem]
0x180091306  mov     [rsp+400h+ppszItemA], r15; ppszItemA
0x18009130b  lea     r9, [rsp+400h+pszFile]; ppszFile
0x180091310  mov     [rsp+400h+ppszItem], rax; ppszItem
0x180091315  lea     pmedium, [rsp+400h+pszClass]; ppszClass
0x18009131a  mov     [rsp+400h+cb], esi
0x18009131e  mov     edx, ebx; cf
0x180091320  call    ?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z; CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)
0x180091325  mov     rsi, [rsp+400h+pszClass]
0x18009132a  mov     ebx, eax
0x18009132c  mov     r14, qword ptr [rsp+400h+pszItem]
0x180091331  test    eax, eax
0x180091333  jnz     $errRtn_131
0x180091339  lea     r8d, [r15+1]
0x18009133d  mov     this, rsi
0x180091340  lea     rdx, [rbp+300h+clsid]
0x180091344  call    cs:__imp_CLSIDFromOle1Class
0x18009134a  mov     ebx, eax
0x18009134c  test    eax, eax
0x18009134e  jnz     $errRtn_131
0x180091354  lea     pmedium, [rsp+400h+cb]; lpcbValue
0x180091359  mov     this, rsi; pszSubKey
0x18009135c  lea     rdx, [rbp+300h+szFullName]; pszValue
0x180091360  call    QueryClassesRootValueW
0x180091365  test    eax, eax
0x180091367  jz      short loc_180091390
0x180091369  mov     this, rsi; string
0x18009136c  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180091371  mov     edx, 190h; cchDest
0x180091376  cmp     eax, edx
0x180091378  jb      short loc_180091384
0x18009137a  mov     eax, 80070057h
0x18009137f  jmp     loc_1800914B4
0x180091384  mov     pmedium, rsi; pszSrc
0x180091387  lea     this, [rbp+300h+szFullName]; pszDest
0x18009138b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180091390  mov     this, r14; string
0x180091393  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180091398  mov     this, [rsp+400h+pszFile]; string
0x18009139d  mov     r8d, eax
0x1800913a0  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800913a5  lea     ecx, [rax+2]
0x1800913a8  add     ecx, r8d
0x1800913ab  movsxd  r15, ecx
0x1800913ae  lea     rdi, [r15+r15]
0x1800913b2  call    GetSafeAllocSize
0x1800913b7  cmp     rdi, rax
0x1800913ba  jnb     loc_180091462
0x1800913c0  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800913c7  mov     pmedium, rdi; dwBytes
0x1800913ca  xor     edx, edx; dwFlags
0x1800913cc  call    cs:__imp_HeapAlloc
0x1800913d2  xor     r10d, r10d
0x1800913d5  mov     rdi, rax
0x1800913d8  test    rax, rax
0x1800913db  jnz     short loc_1800913E5
0x1800913dd  xor     r15d, r15d
0x1800913e0  jmp     loc_180091468
0x1800913e5  mov     pmedium, [rsp+400h+pszFile]; pszSrc
0x1800913ea  mov     rdx, r15; cchDest
0x1800913ed  mov     this, rdi; pszDest
0x1800913f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800913f5  test    r14, r14
0x1800913f8  jz      short loc_180091420
0x1800913fa  cmp     [r14], r10w
0x1800913fe  jz      short loc_180091420
0x180091400  lea     pmedium, asc_1800DDB08; "\\"
0x180091407  mov     rdx, r15; cchDest
0x18009140a  mov     this, rdi; pszDest
0x18009140d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180091412  mov     pmedium, r14; pszSrc
0x180091415  mov     rdx, r15; cchDest
0x180091418  mov     this, rdi; pszDest
0x18009141b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180091420  movaps  xmm0, xmmword ptr [rbp+300h+clsid.Data1]
0x180091424  lea     rax, [rbp+300h+szFullName]
0x180091428  mov     [rsp+400h+var_3D0], rdi
0x18009142d  lea     r9, [rsp+400h+pointl]
0x180091432  lea     pmedium, [rsp+400h+sizel]
0x180091437  movdqa  [rsp+400h+pszItem], xmm0
0x18009143d  lea     this, [rsp+400h+pszItem]
0x180091442  mov     [rsp+400h+ppszItemA], rax
0x180091447  call    ?CreateObjectDescriptor@@YAPEAXU_GUID@@KPEBUtagSIZE@@PEBU_POINTL@@KPEAG3@Z; CreateObjectDescriptor(_GUID,ulong,tagSIZE const *,_POINTL const *,ulong,ushort *,ushort *)
0x18009144c  xor     r15d, r15d
0x18009144f  test    rax, rax
0x180091452  jz      short loc_180091468
0x180091454  mov     this, [rbp+300h+var_380]
0x180091458  mov     [this+8], rax
0x18009145c  mov     [r13+18h], rax
0x180091460  jmp     short $errRtn_131
0x180091462  xor     r15d, r15d
0x180091465  mov     edi, r15d
0x180091468  mov     ebx, 8007000Eh
0x18009146d  test    rsi, rsi
0x180091470  jz      short loc_18009147B
0x180091472  mov     this, rsi; pv
0x180091475  call    cs:__imp_CoTaskMemFree
0x18009147b  cmp     [rsp+400h+pszFile], r15
0x180091480  jz      short loc_18009148D
0x180091482  mov     this, [rsp+400h+pszFile]; pv
0x180091487  call    cs:__imp_CoTaskMemFree
0x18009148d  test    r14, r14
0x180091490  jz      short loc_18009149B
0x180091492  mov     this, r14; pv
0x180091495  call    cs:__imp_CoTaskMemFree
0x18009149b  test    rdi, rdi
0x18009149e  jz      short loc_1800914B2
0x1800914a0  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800914a7  mov     pmedium, rdi; lpMem
0x1800914aa  xor     edx, edx; dwFlags
0x1800914ac  call    cs:__imp_HeapFree
0x1800914b2  mov     eax, ebx
0x1800914b4  mov     this, [rbp+300h+var_40]
0x1800914bb  xor     this, rsp; StackCookie
0x1800914be  call    __security_check_cookie
0x1800914c3  add     rsp, 3D0h
0x1800914ca  pop     r15
0x1800914cc  pop     r14
0x1800914ce  pop     r13
0x1800914d0  pop     rdi
0x1800914d1  pop     rsi
0x1800914d2  pop     rbx
0x1800914d3  pop     rbp
0x1800914d4  retn
```
