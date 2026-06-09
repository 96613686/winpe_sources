# GetOwnerLink(IDataObject *,tagSTGMEDIUM *)

- ea: `0x180088f04`
- end: `0x180089129`
- name: `?GetOwnerLink@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@@Z`
- size: `549`
- prototype: `HRESULT __fastcall(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003b5f8`

## callees

- `0x1800077fc`
- `0x18000a574`
- `0x18003bf64`
- `0x18003f034`
- `0x180046460`
- `0x180088f04`
- `0x1800aa624`
- `0x1800ce967`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180089024`
- `KERNELBASE!GlobalAlloc` at `0x180089024`
- `KERNELBASE!GlobalFree` at `0x1800890f5`
- `KERNELBASE!GlobalFree` at `0x1800890f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180089086`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180089086`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180089047`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180089047`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008909b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008909b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800890dc`

## pseudocode

```c
__int64 __fastcall GetOwnerLink(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)
{
  unsigned int DataFromDescriptor; // edi
  int v4; // eax
  wchar_t *v5; // rcx
  int v6; // eax
  size_t v7; // rsi
  size_t v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // r14d
  HBITMAP v11; // rax
  char *v12; // rax
  char *v13; // r14
  char *v14; // r14
  HBITMAP hBitmap; // rcx
  unsigned int cbszSrcOfCopyA; // [rsp+30h] [rbp-40h] BYREF
  unsigned int cbszClassA; // [rsp+34h] [rbp-3Ch] BYREF
  wchar_t *pszSrcOfCopy; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *pszClass; // [rsp+40h] [rbp-30h] BYREF
  char *pszClassA; // [rsp+48h] [rbp-28h] BYREF
  char *pszSrcOfCopyA; // [rsp+50h] [rbp-20h] BYREF
  _GUID clsid; // [rsp+58h] [rbp-18h] BYREF

  pszSrcOfCopy = 0;
  pszClass = 0;
  pszSrcOfCopyA = 0;
  pszClassA = 0;
  cbszClassA = 0;
  cbszSrcOfCopyA = 0;
  clsid = 0;
  DataFromDescriptor = GetDataFromDescriptor(
                         pDataObj,
                         &clsid,
                         g_cfObjectDescriptor,
                         USE_STANDARD_LINK,
                         &pszSrcOfCopy,
                         0);
  if ( !DataFromDescriptor )
  {
    DataFromDescriptor = wProgIDFromCLSID(&clsid, &pszClass);
    if ( !DataFromDescriptor )
    {
      v4 = safe_lstrlenW(pszClass);
      DataFromDescriptor = UtPutUNICODEData(v4 + 1, v5, (LPVOID *)&pszClassA, 0, &cbszClassA);
      if ( !DataFromDescriptor )
      {
        v6 = safe_lstrlenW(pszSrcOfCopy);
        DataFromDescriptor = UtPutUNICODEData(v6 + 1, pszSrcOfCopy, (LPVOID *)&pszSrcOfCopyA, 0, &cbszSrcOfCopyA);
        if ( !DataFromDescriptor )
        {
          v7 = cbszSrcOfCopyA;
          if ( cbszSrcOfCopyA > cbszSrcOfCopyA + 2
            || (v8 = cbszClassA, v9 = cbszSrcOfCopyA + cbszClassA + 2, cbszClassA > v9) )
          {
            DataFromDescriptor = -2147024809;
          }
          else
          {
            v10 = cbszSrcOfCopyA + cbszClassA + 2;
            if ( v9 >= GetSafeAllocSize() )
              v11 = 0;
            else
              v11 = (HBITMAP)GlobalAlloc(0x2042u, v10);
            pmedium->hBitmap = v11;
            if ( v11 && (v12 = (char *)GlobalLock(v11), (v13 = v12) != 0) )
            {
              memcpy_0(v12, pszClassA, v8);
              v14 = &v13[v8];
              memcpy_0(v14, pszSrcOfCopyA, v7);
              *(_WORD *)&v14[v7] = 0;
              GlobalUnlock(pmedium->hBitmap);
            }
            else
            {
              DataFromDescriptor = -2147024882;
            }
          }
        }
      }
    }
  }
  if ( pszClass )
    CoTaskMemFree(pszClass);
  if ( pszSrcOfCopy )
    CoTaskMemFree(pszSrcOfCopy);
  if ( pszClassA )
    CoTaskMemFree(pszClassA);
  if ( pszSrcOfCopyA )
    CoTaskMemFree(pszSrcOfCopyA);
  if ( DataFromDescriptor )
  {
    hBitmap = pmedium->hBitmap;
    if ( hBitmap )
    {
      GlobalFree(hBitmap);
      pmedium->hBitmap = 0;
    }
  }
  return DataFromDescriptor;
}

```

## disassembly

```asm
0x180088f04  mov     [rsp-28h+arg_10], rbx
0x180088f09  push    rbp
0x180088f0a  push    rsi
0x180088f0b  push    rdi
0x180088f0c  push    r13
0x180088f0e  push    r14
0x180088f10  mov     rbp, rsp
0x180088f13  sub     rsp, 70h
0x180088f17  mov     rax, cs:__security_cookie
0x180088f1e  xor     rax, rsp
0x180088f21  mov     [rbp+var_8], rax
0x180088f25  movzx   r8d, cs:?g_cfObjectDescriptor@@3GA; cf
0x180088f2d  lea     rax, [rbp+pszSrcOfCopy]
0x180088f31  and     [rsp+70h+var_48], 0
0x180088f37  mov     r13, pmedium
0x180088f3a  and     [rbp+pszSrcOfCopy], 0
0x180088f3f  lea     pmedium, [rbp+clsid]; pclsid
0x180088f43  and     [rbp+pszClass], 0
0x180088f48  xorps   xmm0, xmm0
0x180088f4b  and     [rbp+pszSrcOfCopyA], 0
0x180088f50  mov     r9d, 2; fFlags
0x180088f56  and     [rbp+pszClassA], 0
0x180088f5b  and     [rbp+cbszClassA], 0
0x180088f5f  and     [rbp+cbszSrcOfCopyA], 0
0x180088f63  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180088f67  mov     [rsp+70h+ppszSrcOfCopy], rax; ppszSrcOfCopy
0x180088f6c  call    ?GetDataFromDescriptor@@YAJPEAUIDataObject@@PEAU_GUID@@IW4tagGETCLSIDFLAGS@@PEAPEAGPEAK@Z; GetDataFromDescriptor(IDataObject *,_GUID *,uint,tagGETCLSIDFLAGS,ushort * *,ulong *)
0x180088f71  mov     edi, eax
0x180088f73  test    eax, eax
0x180088f75  jnz     $errRtn_98
0x180088f7b  lea     pmedium, [rbp+pszClass]; psz
0x180088f7f  lea     pDataObj, [rbp+clsid]; clsid
0x180088f83  call    ?wProgIDFromCLSID@@YAJAEBU_GUID@@PEAPEAG@Z; wProgIDFromCLSID(_GUID const &,ushort * *)
0x180088f88  mov     edi, eax
0x180088f8a  test    eax, eax
0x180088f8c  jnz     $errRtn_98
0x180088f92  mov     pDataObj, [rbp+pszClass]; string
0x180088f96  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180088f9b  lea     pmedium, [rbp+cbszClassA]
0x180088f9f  xor     r9d, r9d; pszOLESTR
0x180088fa2  mov     [rsp+70h+ppszSrcOfCopy], pmedium; pdwResultLen
0x180088fa7  lea     r8, [rbp+pszClassA]; pszANSI
0x180088fab  mov     pmedium, pDataObj; str
0x180088fae  lea     ecx, [rax+1]; ulLength
0x180088fb1  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x180088fb6  mov     edi, eax
0x180088fb8  test    eax, eax
0x180088fba  jnz     $errRtn_98
0x180088fc0  mov     pDataObj, [rbp+pszSrcOfCopy]; string
0x180088fc4  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180088fc9  mov     pmedium, [rbp+pszSrcOfCopy]; str
0x180088fcd  lea     pDataObj, [rbp+cbszSrcOfCopyA]
0x180088fd1  mov     [rsp+70h+ppszSrcOfCopy], pDataObj; pdwResultLen
0x180088fd6  lea     r8, [rbp+pszSrcOfCopyA]; pszANSI
0x180088fda  xor     r9d, r9d; pszOLESTR
0x180088fdd  lea     ecx, [rax+1]; ulLength
0x180088fe0  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x180088fe5  mov     edi, eax
0x180088fe7  test    eax, eax
0x180088fe9  jnz     $errRtn_98
0x180088fef  mov     esi, [rbp+cbszSrcOfCopyA]
0x180088ff2  lea     eax, [rsi+2]
0x180088ff5  cmp     esi, eax
0x180088ff7  jbe     short loc_180089003
0x180088ff9  mov     edi, 80070057h
0x180088ffe  jmp     $errRtn_98
0x180089003  mov     ebx, [rbp+cbszClassA]
0x180089006  lea     eax, [rbx+2]
0x180089009  add     eax, esi
0x18008900b  cmp     ebx, eax
0x18008900d  ja      short loc_180088FF9
0x18008900f  mov     r14d, eax
0x180089012  call    GetSafeAllocSize
0x180089017  cmp     r14, rax
0x18008901a  jnb     short loc_180089032
0x18008901c  mov     edx, r14d; dwBytes
0x18008901f  mov     ecx, 2042h; uFlags
0x180089024  call    cs:__imp_GlobalAlloc
0x18008902b  nop     dword ptr [rax+rax+00h]
0x180089030  jmp     short loc_180089034
0x180089032  xor     eax, eax
0x180089034  mov     [r13+8], rax
0x180089038  test    rax, rax
0x18008903b  jnz     short loc_180089044
0x18008903d  mov     edi, 8007000Eh
0x180089042  jmp     short $errRtn_98
0x180089044  mov     pDataObj, rax; hMem
0x180089047  call    cs:__imp_GlobalLock
0x18008904e  nop     dword ptr [rax+rax+00h]
0x180089053  mov     r14, rax
0x180089056  test    rax, rax
0x180089059  jz      short loc_18008903D
0x18008905b  mov     pmedium, [rbp+pszClassA]; Src
0x18008905f  mov     r8, rbx; Size
0x180089062  mov     pDataObj, rax; void *
0x180089065  call    memcpy_0
0x18008906a  mov     pmedium, [rbp+pszSrcOfCopyA]; Src
0x18008906e  add     r14, rbx
0x180089071  mov     pDataObj, r14; void *
0x180089074  mov     r8, rsi; Size
0x180089077  call    memcpy_0
0x18008907c  and     word ptr [r14+rsi], 0
0x180089082  mov     pDataObj, [r13+8]; hMem
0x180089086  call    cs:__imp_GlobalUnlock
0x18008908d  nop     dword ptr [rax+rax+00h]
0x180089092  mov     pDataObj, [rbp+pszClass]; pv
0x180089096  test    pDataObj, pDataObj
0x180089099  jz      short loc_1800890A7
0x18008909b  call    cs:__imp_CoTaskMemFree
0x1800890a2  nop     dword ptr [rax+rax+00h]
0x1800890a7  cmp     [rbp+pszSrcOfCopy], 0
0x1800890ac  jz      short loc_1800890BE
0x1800890ae  mov     pDataObj, [rbp+pszSrcOfCopy]; pv
0x1800890b2  call    cs:__imp_CoTaskMemFree
0x1800890b9  nop     dword ptr [rax+rax+00h]
0x1800890be  mov     pDataObj, [rbp+pszClassA]; pv
0x1800890c2  test    pDataObj, pDataObj
0x1800890c5  jz      short loc_1800890D3
0x1800890c7  call    cs:__imp_CoTaskMemFree
0x1800890ce  nop     dword ptr [rax+rax+00h]
0x1800890d3  mov     pDataObj, [rbp+pszSrcOfCopyA]; pv
0x1800890d7  test    pDataObj, pDataObj
0x1800890da  jz      short loc_1800890E8
0x1800890dc  call    cs:__imp_CoTaskMemFree
0x1800890e3  nop     dword ptr [rax+rax+00h]
0x1800890e8  test    edi, edi
0x1800890ea  jz      short loc_180089106
0x1800890ec  mov     pDataObj, [r13+8]; hMem
0x1800890f0  test    pDataObj, pDataObj
0x1800890f3  jz      short loc_180089106
0x1800890f5  call    cs:__imp_GlobalFree
0x1800890fc  nop     dword ptr [rax+rax+00h]
0x180089101  and     qword ptr [r13+8], 0
0x180089106  mov     eax, edi
0x180089108  mov     pDataObj, [rbp+var_8]
0x18008910c  xor     pDataObj, rsp; StackCookie
0x18008910f  call    __security_check_cookie
0x180089114  mov     rbx, [rsp+70h+arg_10]
0x18008911c  add     rsp, 70h
0x180089120  pop     r14
0x180089122  pop     r13
0x180089124  pop     rdi
0x180089125  pop     rsi
0x180089126  pop     rbp
0x180089127  retn
```
