# ReleaseStgMedium

- ea: `0x18000aab0`
- end: `0x18000ac28`
- name: `ReleaseStgMedium`
- size: `376`
- prototype: `void __stdcall(LPSTGMEDIUM)`
- caller_count: `29`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000b040`
- `0x18000d470`
- `0x18002c210`
- `0x18002e680`
- `0x180033878`
- `0x1800381e0`
- `0x18003ad30`
- `0x180040bbc`
- `0x180049410`
- `0x1800797d0`
- `0x180079970`
- `0x18007f708`
- `0x180082718`
- `0x180082c18`
- `0x180082cf8`
- `0x180083360`
- `0x1800845a0`
- `0x1800896e0`
- `0x18008a8fc`
- `0x18008c6f8`
- `0x18008cd00`
- `0x18008ce9c`
- `0x18008d05c`
- `0x18008d380`
- `0x180093428`
- `0x18009d280`
- `0x18009de50`
- `0x1800b2da0`
- `0x1800bbcc4`

## callees

- `0x180009de0`
- `0x18000aab0`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18000ab1d`
- `KERNELBASE!GlobalFree` at `0x18000ab1d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ac1d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000ac1d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000abdf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000abdf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000abc2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000abc2`
- `GDI32!DeleteMetaFile` at `0x18000abd5`
- `GDI32!DeleteMetaFile` at `0x18000abd5`
- `GDI32!DeleteObject` at `0x18000ab80`
- `GDI32!DeleteObject` at `0x18000ab80`
- `GDI32!DeleteEnhMetaFile` at `0x18000aba1`
- `GDI32!DeleteEnhMetaFile` at `0x18000aba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ab5e`

## pseudocode

```c
void __stdcall ReleaseStgMedium(LPSTGMEDIUM a1)
{
  IUnknown *pUnkForRelease; // rdx
  DWORD v3; // ecx
  DWORD v4; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx
  DWORD v8; // ecx
  IUnknown *v9; // rcx
  HBITMAP hBitmap; // rcx
  const wchar_t *lpszFileName; // rcx
  HBITMAP v12; // rcx
  HBITMAP v13; // rcx
  HBITMAP v14; // rcx
  HMETAFILE *v15; // rax
  HBITMAP v16; // rcx

  if ( !a1 )
    return;
  pUnkForRelease = a1->pUnkForRelease;
  v3 = a1->tymed - 1;
  if ( !v3 )
  {
    hBitmap = a1->hBitmap;
    if ( !hBitmap || pUnkForRelease )
      goto LABEL_9;
    goto LABEL_14;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    lpszFileName = a1->lpszFileName;
    if ( lpszFileName )
    {
      if ( !pUnkForRelease )
        DeleteFileW(lpszFileName);
      CoTaskMemFree(a1->hBitmap);
      a1->hBitmap = 0;
    }
    goto LABEL_9;
  }
  v5 = v4 - 2;
  if ( !v5 || (v6 = v5 - 4) == 0 )
  {
    v16 = a1->hBitmap;
    if ( v16 && IsValidInterface(v16) )
      (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)a1->hBitmap + 16LL))(a1->hBitmap);
    goto LABEL_9;
  }
  v7 = v6 - 8;
  if ( !v7 )
  {
    v12 = a1->hBitmap;
    if ( v12 && !pUnkForRelease )
      DeleteObject(v12);
    goto LABEL_9;
  }
  v8 = v7 - 16;
  if ( v8 )
  {
    if ( v8 == 32 )
    {
      v13 = a1->hBitmap;
      if ( v13 )
      {
        if ( !pUnkForRelease )
          DeleteEnhMetaFile((HENHMETAFILE)v13);
      }
    }
    goto LABEL_9;
  }
  v14 = a1->hBitmap;
  if ( v14 )
  {
    if ( !pUnkForRelease )
    {
      v15 = (HMETAFILE *)GlobalLock(v14);
      if ( v15 )
      {
        DeleteMetaFile(v15[2]);
        GlobalUnlock(a1->hBitmap);
        hBitmap = a1->hBitmap;
LABEL_14:
        GlobalFree(hBitmap);
      }
    }
  }
LABEL_9:
  v9 = a1->pUnkForRelease;
  if ( v9 )
  {
    if ( IsValidInterface(v9) )
      ((void (__fastcall *)(IUnknown *))a1->pUnkForRelease->lpVtbl->Release)(a1->pUnkForRelease);
    a1->pUnkForRelease = 0;
  }
  a1->tymed = 0;
}

```

## disassembly

```asm
0x18000aab0  test    pMedium, pMedium
0x18000aab3  jz      short locret_18000AB0E
0x18000aab5  push    rbx
0x18000aab6  sub     rsp, 20h
0x18000aaba  mov     rdx, [pMedium+10h]
0x18000aabe  mov     rbx, pMedium
0x18000aac1  mov     ecx, [pMedium]
0x18000aac3  sub     ecx, 1
0x18000aac6  jz      short loc_18000AB0F
0x18000aac8  sub     ecx, 1
0x18000aacb  jz      short loc_18000AB48
0x18000aacd  sub     ecx, 2
0x18000aad0  jz      loc_18000ABEE
0x18000aad6  sub     ecx, 4
0x18000aad9  jz      loc_18000ABEE
0x18000aadf  sub     ecx, 8
0x18000aae2  jz      loc_18000AB6E
0x18000aae8  sub     ecx, 10h
0x18000aaeb  jz      loc_18000ABAC
0x18000aaf1  cmp     ecx, 20h ; ' '
0x18000aaf4  jz      loc_18000AB8B
0x18000aafa  mov     pMedium, [rbx+10h]; pv
0x18000aafe  test    pMedium, pMedium
0x18000ab01  jnz     short loc_18000AB25
0x18000ab03  mov     dword ptr [rbx], 0
0x18000ab09  add     rsp, 20h
0x18000ab0d  pop     rbx
0x18000ab0e  retn
0x18000ab0f  mov     pMedium, [rbx+8]; hMem
0x18000ab13  test    pMedium, pMedium
0x18000ab16  jz      short loc_18000AAFA
0x18000ab18  test    rdx, rdx
0x18000ab1b  jnz     short loc_18000AAFA
0x18000ab1d  call    cs:__imp_GlobalFree
0x18000ab23  jmp     short loc_18000AAFA
0x18000ab25  call    IsValidInterface
0x18000ab2a  test    eax, eax
0x18000ab2c  jz      short loc_18000AB3E
0x18000ab2e  mov     pMedium, [rbx+10h]
0x18000ab32  mov     rax, [pMedium]
0x18000ab35  mov     rax, [rax+10h]
0x18000ab39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab3e  mov     qword ptr [rbx+10h], 0
0x18000ab46  jmp     short loc_18000AB03
0x18000ab48  mov     pMedium, [rbx+8]; lpFileName
0x18000ab4c  test    pMedium, pMedium
0x18000ab4f  jz      short loc_18000AAFA
0x18000ab51  test    rdx, rdx
0x18000ab54  jz      loc_18000AC1D
0x18000ab5a  mov     pMedium, [rbx+8]; pv
0x18000ab5e  call    cs:__imp_CoTaskMemFree
0x18000ab64  mov     qword ptr [rbx+8], 0
0x18000ab6c  jmp     short loc_18000AAFA
0x18000ab6e  mov     pMedium, [rbx+8]; ho
0x18000ab72  test    pMedium, pMedium
0x18000ab75  jz      short loc_18000AAFA
0x18000ab77  test    rdx, rdx
0x18000ab7a  jnz     loc_18000AAFA
0x18000ab80  call    cs:__imp_DeleteObject
0x18000ab86  jmp     loc_18000AAFA
0x18000ab8b  mov     pMedium, [rbx+8]; hmf
0x18000ab8f  test    pMedium, pMedium
0x18000ab92  jz      loc_18000AAFA
0x18000ab98  test    rdx, rdx
0x18000ab9b  jnz     loc_18000AAFA
0x18000aba1  call    cs:__imp_DeleteEnhMetaFile
0x18000aba7  jmp     loc_18000AAFA
0x18000abac  mov     pMedium, [rbx+8]; hMem
0x18000abb0  test    pMedium, pMedium
0x18000abb3  jz      loc_18000AAFA
0x18000abb9  test    rdx, rdx
0x18000abbc  jnz     loc_18000AAFA
0x18000abc2  call    cs:__imp_GlobalLock
0x18000abc8  test    rax, rax
0x18000abcb  jz      loc_18000AAFA
0x18000abd1  mov     pMedium, [rax+10h]; hmf
0x18000abd5  call    cs:__imp_DeleteMetaFile
0x18000abdb  mov     pMedium, [rbx+8]; hMem
0x18000abdf  call    cs:__imp_GlobalUnlock
0x18000abe5  mov     pMedium, [rbx+8]
0x18000abe9  jmp     loc_18000AB1D
0x18000abee  mov     pMedium, [rbx+8]; pv
0x18000abf2  test    pMedium, pMedium
0x18000abf5  jz      loc_18000AAFA
0x18000abfb  call    IsValidInterface
0x18000ac00  test    eax, eax
0x18000ac02  jz      loc_18000AAFA
0x18000ac08  mov     pMedium, [rbx+8]
0x18000ac0c  mov     rax, [pMedium]
0x18000ac0f  mov     rax, [rax+10h]
0x18000ac13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac18  jmp     loc_18000AAFA
0x18000ac1d  call    cs:__imp_DeleteFileW
0x18000ac23  jmp     loc_18000AB5A
```
