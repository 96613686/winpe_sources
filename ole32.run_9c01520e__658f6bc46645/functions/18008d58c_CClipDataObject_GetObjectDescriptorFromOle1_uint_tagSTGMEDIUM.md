# CClipDataObject::GetObjectDescriptorFromOle1(uint,tagSTGMEDIUM *)

- ea: `0x18008d58c`
- end: `0x18008d7f3`
- name: `?GetObjectDescriptorFromOle1@CClipDataObject@@AEAAJIPEAUtagSTGMEDIUM@@@Z`
- size: `615`
- prototype: `HRESULT __fastcall(CClipDataObject *this, unsigned int cf, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008d7fc`

## callees

- `0x1800077fc`
- `0x18000a574`
- `0x18000fc2c`
- `0x18001a630`
- `0x180046460`
- `0x180047484`
- `0x18007f120`
- `0x18008c7c8`
- `0x18008d58c`
- `0x1800c8934`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d7c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d7c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008d6ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008d6ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d77a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d77a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d7a6`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18008d63c`
- `api-ms-win-core-com-private-l1-1-0!CLSIDFromOle1Class` at `0x18008d63c`

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
    goto $errRtn_104;
  v9 = CLSIDFromOle1Class(pszClass, &clsid, 1);
  if ( v9 )
    goto $errRtn_104;
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
    goto $errRtn_104;
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
$errRtn_104:
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
0x18008d58c  push    rbp
0x18008d58e  push    rbx
0x18008d58f  push    rsi
0x18008d590  push    rdi
0x18008d591  push    r13
0x18008d593  push    r14
0x18008d595  push    r15
0x18008d597  lea     rbp, [rsp-2D0h]
0x18008d59f  sub     rsp, 3D0h
0x18008d5a6  mov     rax, cs:__security_cookie
0x18008d5ad  xor     rax, rsp
0x18008d5b0  mov     [rbp+300h+var_40], rax
0x18008d5b7  xor     r15d, r15d
0x18008d5ba  mov     [rbp+300h+var_380], pmedium
0x18008d5be  mov     ebx, edx
0x18008d5c0  mov     [rsp+400h+pszClass], r15
0x18008d5c5  mov     r13, this
0x18008d5c8  mov     [rsp+400h+pszFile], r15
0x18008d5cd  xorps   xmm0, xmm0
0x18008d5d0  mov     qword ptr [rsp+400h+pszItem], r15
0x18008d5d5  mov     esi, 320h
0x18008d5da  mov     qword ptr [rsp+400h+sizel.cx], r15
0x18008d5df  mov     r8d, esi; Size
0x18008d5e2  mov     qword ptr [rsp+400h+pointl.x], r15
0x18008d5e7  xor     edx, edx; Val
0x18008d5e9  lea     this, [rbp+300h+szFullName]; void *
0x18008d5ed  mov     edi, r15d
0x18008d5f0  movups  xmmword ptr [rbp+300h+clsid.Data1], xmm0
0x18008d5f4  call    memset_0
0x18008d5f9  lea     rax, [rsp+400h+pszItem]
0x18008d5fe  mov     [rsp+400h+ppszItemA], r15; ppszItemA
0x18008d603  lea     r9, [rsp+400h+pszFile]; ppszFile
0x18008d608  mov     [rsp+400h+ppszItem], rax; ppszItem
0x18008d60d  lea     pmedium, [rsp+400h+pszClass]; ppszClass
0x18008d612  mov     [rsp+400h+cb], esi
0x18008d616  mov     edx, ebx; cf
0x18008d618  call    ?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z; CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)
0x18008d61d  mov     rsi, [rsp+400h+pszClass]
0x18008d622  mov     ebx, eax
0x18008d624  mov     r14, qword ptr [rsp+400h+pszItem]
0x18008d629  test    eax, eax
0x18008d62b  jnz     $errRtn_104
0x18008d631  lea     r8d, [r15+1]
0x18008d635  mov     this, rsi
0x18008d638  lea     rdx, [rbp+300h+clsid]
0x18008d63c  call    cs:__imp_CLSIDFromOle1Class
0x18008d643  nop     dword ptr [rax+rax+00h]
0x18008d648  mov     ebx, eax
0x18008d64a  test    eax, eax
0x18008d64c  jnz     $errRtn_104
0x18008d652  lea     pmedium, [rsp+400h+cb]; lpcbValue
0x18008d657  mov     this, rsi; pszSubKey
0x18008d65a  lea     rdx, [rbp+300h+szFullName]; pszValue
0x18008d65e  call    QueryClassesRootValueW
0x18008d663  test    eax, eax
0x18008d665  jz      short loc_18008D68E
0x18008d667  mov     this, rsi; string
0x18008d66a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008d66f  mov     edx, 190h; cchDest
0x18008d674  cmp     eax, edx
0x18008d676  jb      short loc_18008D682
0x18008d678  mov     eax, 80070057h
0x18008d67d  jmp     loc_18008D7D1
0x18008d682  mov     pmedium, rsi; pszSrc
0x18008d685  lea     this, [rbp+300h+szFullName]; pszDest
0x18008d689  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d68e  mov     this, r14; string
0x18008d691  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008d696  mov     this, [rsp+400h+pszFile]; string
0x18008d69b  mov     r8d, eax
0x18008d69e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008d6a3  lea     ecx, [rax+2]
0x18008d6a6  add     ecx, r8d
0x18008d6a9  movsxd  r15, ecx
0x18008d6ac  lea     rdi, [r15+r15]
0x18008d6b0  call    GetSafeAllocSize
0x18008d6b5  cmp     rdi, rax
0x18008d6b8  jnb     loc_18008D762
0x18008d6be  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008d6c5  mov     pmedium, rdi; dwBytes
0x18008d6c8  xor     edx, edx; dwFlags
0x18008d6ca  call    cs:__imp_HeapAlloc
0x18008d6d1  nop     dword ptr [rax+rax+00h]
0x18008d6d6  xor     r10d, r10d
0x18008d6d9  mov     rdi, rax
0x18008d6dc  test    rax, rax
0x18008d6df  jz      loc_18008D76A
0x18008d6e5  mov     pmedium, [rsp+400h+pszFile]; pszSrc
0x18008d6ea  mov     rdx, r15; cchDest
0x18008d6ed  mov     this, rax; pszDest
0x18008d6f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008d6f5  test    r14, r14
0x18008d6f8  jz      short loc_18008D720
0x18008d6fa  cmp     [r14], r10w
0x18008d6fe  jz      short loc_18008D720
0x18008d700  lea     pmedium, asc_1800E8258; "\\"
0x18008d707  mov     rdx, r15; cchDest
0x18008d70a  mov     this, rdi; pszDest
0x18008d70d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008d712  mov     pmedium, r14; pszSrc
0x18008d715  mov     rdx, r15; cchDest
0x18008d718  mov     this, rdi; pszDest
0x18008d71b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008d720  movaps  xmm0, xmmword ptr [rbp+300h+clsid.Data1]
0x18008d724  lea     rax, [rbp+300h+szFullName]
0x18008d728  mov     [rsp+400h+var_3D0], rdi
0x18008d72d  lea     r9, [rsp+400h+pointl]
0x18008d732  lea     pmedium, [rsp+400h+sizel]
0x18008d737  movdqa  [rsp+400h+pszItem], xmm0
0x18008d73d  lea     this, [rsp+400h+pszItem]
0x18008d742  mov     [rsp+400h+ppszItemA], rax
0x18008d747  call    ?CreateObjectDescriptor@@YAPEAXU_GUID@@KPEBUtagSIZE@@PEBU_POINTL@@KPEAG3@Z; CreateObjectDescriptor(_GUID,ulong,tagSIZE const *,_POINTL const *,ulong,ushort *,ushort *)
0x18008d74c  xor     r15d, r15d
0x18008d74f  test    rax, rax
0x18008d752  jz      short loc_18008D76D
0x18008d754  mov     this, [rbp+300h+var_380]
0x18008d758  mov     [this+8], rax
0x18008d75c  mov     [r13+18h], rax
0x18008d760  jmp     short $errRtn_104
0x18008d762  xor     r15d, r15d
0x18008d765  mov     edi, r15d
0x18008d768  jmp     short loc_18008D76D
0x18008d76a  xor     r15d, r15d
0x18008d76d  mov     ebx, 8007000Eh
0x18008d772  test    rsi, rsi
0x18008d775  jz      short loc_18008D786
0x18008d777  mov     this, rsi; pv
0x18008d77a  call    cs:__imp_CoTaskMemFree
0x18008d781  nop     dword ptr [rax+rax+00h]
0x18008d786  cmp     [rsp+400h+pszFile], r15
0x18008d78b  jz      short loc_18008D79E
0x18008d78d  mov     this, [rsp+400h+pszFile]; pv
0x18008d792  call    cs:__imp_CoTaskMemFree
0x18008d799  nop     dword ptr [rax+rax+00h]
0x18008d79e  test    r14, r14
0x18008d7a1  jz      short loc_18008D7B2
0x18008d7a3  mov     this, r14; pv
0x18008d7a6  call    cs:__imp_CoTaskMemFree
0x18008d7ad  nop     dword ptr [rax+rax+00h]
0x18008d7b2  test    rdi, rdi
0x18008d7b5  jz      short loc_18008D7CF
0x18008d7b7  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008d7be  mov     pmedium, rdi; lpMem
0x18008d7c1  xor     edx, edx; dwFlags
0x18008d7c3  call    cs:__imp_HeapFree
0x18008d7ca  nop     dword ptr [rax+rax+00h]
0x18008d7cf  mov     eax, ebx
0x18008d7d1  mov     this, [rbp+300h+var_40]
0x18008d7d8  xor     this, rsp; StackCookie
0x18008d7db  call    __security_check_cookie
0x18008d7e0  add     rsp, 3D0h
0x18008d7e7  pop     r15
0x18008d7e9  pop     r14
0x18008d7eb  pop     r13
0x18008d7ed  pop     rdi
0x18008d7ee  pop     rsi
0x18008d7ef  pop     rbx
0x18008d7f0  pop     rbp
0x18008d7f1  retn
```
