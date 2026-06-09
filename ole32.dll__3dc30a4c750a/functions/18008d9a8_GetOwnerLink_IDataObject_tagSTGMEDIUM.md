# GetOwnerLink(IDataObject *,tagSTGMEDIUM *)

- ea: `0x18008d9a8`
- end: `0x18008dbb4`
- name: `?GetOwnerLink@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@@Z`
- size: `524`
- prototype: `HRESULT __fastcall(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800376b8`

## callees

- `0x180009374`
- `0x18000b2d4`
- `0x180038034`
- `0x18003ad30`
- `0x1800487b4`
- `0x180052390`
- `0x18008d9a8`
- `0x1800c4651`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18008dadc`
- `KERNELBASE!GlobalAlloc` at `0x18008dadc`
- `KERNELBASE!GlobalFree` at `0x18008db84`
- `KERNELBASE!GlobalFree` at `0x18008db84`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008db33`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008db33`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008daf9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008daf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008db71`

## pseudocode

```c
__int64 __fastcall GetOwnerLink(IDataObject *pDataObj, tagSTGMEDIUM *pmedium)
{
  unsigned int DataFromDescriptor; // esi
  int v4; // eax
  wchar_t *v5; // rcx
  int v6; // eax
  size_t v7; // r14
  size_t v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // edi
  HBITMAP v11; // rax
  char *v12; // rax
  char *v13; // rdi
  char *v14; // rdi
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
  clsid = 0;
  pszSrcOfCopyA = 0;
  pszClassA = 0;
  cbszClassA = 0;
  cbszSrcOfCopyA = 0;
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
0x18008d9a8  mov     [rsp-28h+arg_10], rbx
0x18008d9ad  push    rbp
0x18008d9ae  push    rsi
0x18008d9af  push    rdi
0x18008d9b0  push    r13
0x18008d9b2  push    r14
0x18008d9b4  mov     rbp, rsp
0x18008d9b7  sub     rsp, 70h
0x18008d9bb  mov     rax, cs:__security_cookie
0x18008d9c2  xor     rax, rsp
0x18008d9c5  mov     [rbp+var_8], rax
0x18008d9c9  movzx   r8d, cs:?g_cfObjectDescriptor@@3GA; cf
0x18008d9d1  lea     rax, [rbp+pszSrcOfCopy]
0x18008d9d5  mov     r13, pmedium
0x18008d9d8  mov     [rsp+70h+pdwStatus], 0; pdwStatus
0x18008d9e1  xorps   xmm0, xmm0
0x18008d9e4  mov     [rsp+70h+ppszSrcOfCopy], rax; ppszSrcOfCopy
0x18008d9e9  lea     pmedium, [rbp+clsid]; pclsid
0x18008d9ed  mov     [rbp+pszSrcOfCopy], 0
0x18008d9f5  mov     r9d, 2; fFlags
0x18008d9fb  mov     [rbp+pszClass], 0
0x18008da03  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18008da07  mov     [rbp+pszSrcOfCopyA], 0
0x18008da0f  mov     [rbp+pszClassA], 0
0x18008da17  mov     [rbp+cbszClassA], 0
0x18008da1e  mov     [rbp+cbszSrcOfCopyA], 0
0x18008da25  call    ?GetDataFromDescriptor@@YAJPEAUIDataObject@@PEAU_GUID@@IW4tagGETCLSIDFLAGS@@PEAPEAGPEAK@Z; GetDataFromDescriptor(IDataObject *,_GUID *,uint,tagGETCLSIDFLAGS,ushort * *,ulong *)
0x18008da2a  mov     esi, eax
0x18008da2c  test    eax, eax
0x18008da2e  jnz     $errRtn_125
0x18008da34  lea     pmedium, [rbp+pszClass]; psz
0x18008da38  lea     pDataObj, [rbp+clsid]; clsid
0x18008da3c  call    ?wProgIDFromCLSID@@YAJAEBU_GUID@@PEAPEAG@Z; wProgIDFromCLSID(_GUID const &,ushort * *)
0x18008da41  mov     esi, eax
0x18008da43  test    eax, eax
0x18008da45  jnz     $errRtn_125
0x18008da4b  mov     pDataObj, [rbp+pszClass]; string
0x18008da4f  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008da54  lea     pmedium, [rbp+cbszClassA]
0x18008da58  xor     r9d, r9d; pszOLESTR
0x18008da5b  mov     [rsp+70h+ppszSrcOfCopy], pmedium; pdwResultLen
0x18008da60  lea     r8, [rbp+pszClassA]; pszANSI
0x18008da64  mov     pmedium, pDataObj; str
0x18008da67  lea     ecx, [rax+1]; ulLength
0x18008da6a  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x18008da6f  mov     esi, eax
0x18008da71  test    eax, eax
0x18008da73  jnz     $errRtn_125
0x18008da79  mov     pDataObj, [rbp+pszSrcOfCopy]; string
0x18008da7d  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18008da82  mov     pmedium, [rbp+pszSrcOfCopy]; str
0x18008da86  lea     pDataObj, [rbp+cbszSrcOfCopyA]
0x18008da8a  mov     [rsp+70h+ppszSrcOfCopy], pDataObj; pdwResultLen
0x18008da8f  lea     r8, [rbp+pszSrcOfCopyA]; pszANSI
0x18008da93  xor     r9d, r9d; pszOLESTR
0x18008da96  lea     ecx, [rax+1]; ulLength
0x18008da99  call    ?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z; UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)
0x18008da9e  mov     esi, eax
0x18008daa0  test    eax, eax
0x18008daa2  jnz     $errRtn_125
0x18008daa8  mov     r14d, [rbp+cbszSrcOfCopyA]
0x18008daac  lea     eax, [r14+2]
0x18008dab0  cmp     r14d, eax
0x18008dab3  jbe     short loc_18008DABC
0x18008dab5  mov     esi, 80070057h
0x18008daba  jmp     short $errRtn_125
0x18008dabc  mov     ebx, [rbp+cbszClassA]
0x18008dabf  lea     eax, [rbx+2]
0x18008dac2  add     eax, r14d
0x18008dac5  cmp     ebx, eax
0x18008dac7  ja      short loc_18008DAB5
0x18008dac9  mov     edi, eax
0x18008dacb  call    GetSafeAllocSize
0x18008dad0  cmp     rdi, rax
0x18008dad3  jnb     short loc_18008DAE4
0x18008dad5  mov     edx, edi; dwBytes
0x18008dad7  mov     ecx, 2042h; uFlags
0x18008dadc  call    cs:__imp_GlobalAlloc
0x18008dae2  jmp     short loc_18008DAE6
0x18008dae4  xor     eax, eax
0x18008dae6  mov     [r13+8], rax
0x18008daea  test    rax, rax
0x18008daed  jnz     short loc_18008DAF6
0x18008daef  mov     esi, 8007000Eh
0x18008daf4  jmp     short $errRtn_125
0x18008daf6  mov     pDataObj, rax; hMem
0x18008daf9  call    cs:__imp_GlobalLock
0x18008daff  mov     rdi, rax
0x18008db02  test    rax, rax
0x18008db05  jz      short loc_18008DAEF
0x18008db07  mov     pmedium, [rbp+pszClassA]; Src
0x18008db0b  mov     r8, rbx; Size
0x18008db0e  mov     pDataObj, rax; void *
0x18008db11  call    memcpy_0
0x18008db16  mov     pmedium, [rbp+pszSrcOfCopyA]; Src
0x18008db1a  add     rdi, rbx
0x18008db1d  mov     pDataObj, rdi; void *
0x18008db20  mov     r8, r14; Size
0x18008db23  call    memcpy_0
0x18008db28  mov     word ptr [rdi+r14], 0
0x18008db2f  mov     pDataObj, [r13+8]; hMem
0x18008db33  call    cs:__imp_GlobalUnlock
0x18008db39  mov     pDataObj, [rbp+pszClass]; pv
0x18008db3d  test    pDataObj, pDataObj
0x18008db40  jz      short loc_18008DB48
0x18008db42  call    cs:__imp_CoTaskMemFree
0x18008db48  cmp     [rbp+pszSrcOfCopy], 0
0x18008db4d  jz      short loc_18008DB59
0x18008db4f  mov     pDataObj, [rbp+pszSrcOfCopy]; pv
0x18008db53  call    cs:__imp_CoTaskMemFree
0x18008db59  mov     pDataObj, [rbp+pszClassA]; pv
0x18008db5d  test    pDataObj, pDataObj
0x18008db60  jz      short loc_18008DB68
0x18008db62  call    cs:__imp_CoTaskMemFree
0x18008db68  mov     pDataObj, [rbp+pszSrcOfCopyA]; pv
0x18008db6c  test    pDataObj, pDataObj
0x18008db6f  jz      short loc_18008DB77
0x18008db71  call    cs:__imp_CoTaskMemFree
0x18008db77  test    esi, esi
0x18008db79  jz      short loc_18008DB92
0x18008db7b  mov     pDataObj, [r13+8]; hMem
0x18008db7f  test    pDataObj, pDataObj
0x18008db82  jz      short loc_18008DB92
0x18008db84  call    cs:__imp_GlobalFree
0x18008db8a  mov     qword ptr [r13+8], 0
0x18008db92  mov     eax, esi
0x18008db94  mov     pDataObj, [rbp+var_8]
0x18008db98  xor     pDataObj, rsp; StackCookie
0x18008db9b  call    __security_check_cookie
0x18008dba0  mov     rbx, [rsp+70h+arg_10]
0x18008dba8  add     rsp, 70h
0x18008dbac  pop     r14
0x18008dbae  pop     r13
0x18008dbb0  pop     rdi
0x18008dbb1  pop     rsi
0x18008dbb2  pop     rbp
0x18008dbb3  retn
```
