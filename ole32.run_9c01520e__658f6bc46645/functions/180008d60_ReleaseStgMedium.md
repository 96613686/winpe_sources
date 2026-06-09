# ReleaseStgMedium

- ea: `0x180008d60`
- end: `0x180008f04`
- name: `ReleaseStgMedium`
- size: `420`
- prototype: `void __stdcall(LPSTGMEDIUM)`
- caller_count: `29`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009960`
- `0x18000c3c0`
- `0x180017370`
- `0x180018c70`
- `0x1800371a0`
- `0x18003c1b8`
- `0x18003f034`
- `0x1800722b0`
- `0x180072460`
- `0x180078d84`
- `0x18007c2d0`
- `0x18007c7ec`
- `0x18007c8e0`
- `0x18007d268`
- `0x18007e9c0`
- `0x1800812f0`
- `0x1800847ac`
- `0x180085a90`
- `0x180087b24`
- `0x1800881e0`
- `0x180088384`
- `0x180088550`
- `0x180088884`
- `0x18009246c`
- `0x180092f7c`
- `0x18009fff0`
- `0x1800a0d70`
- `0x1800bb120`
- `0x1800c4744`

## callees

- `0x180008280`
- `0x180008d60`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180008dcb`
- `KERNELBASE!GlobalFree` at `0x180008dcb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008ef3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180008ef3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180008eaf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180008eaf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008e86`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180008e86`
- `GDI32!DeleteMetaFile` at `0x180008e9f`
- `GDI32!DeleteMetaFile` at `0x180008e9f`
- `GDI32!DeleteObject` at `0x180008e38`
- `GDI32!DeleteObject` at `0x180008e38`
- `GDI32!DeleteEnhMetaFile` at `0x180008e5f`
- `GDI32!DeleteEnhMetaFile` at `0x180008e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e0f`

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
0x180008d60  test    pMedium, pMedium
0x180008d63  jz      short locret_180008DBB
0x180008d65  push    rbx
0x180008d66  sub     rsp, 20h
0x180008d6a  mov     rdx, [pMedium+10h]
0x180008d6e  mov     rbx, pMedium
0x180008d71  mov     ecx, [pMedium]
0x180008d73  sub     ecx, 1
0x180008d76  jz      short loc_180008DBD
0x180008d78  sub     ecx, 1
0x180008d7b  jz      short loc_180008DF9
0x180008d7d  sub     ecx, 2
0x180008d80  jz      loc_180008EC4
0x180008d86  sub     ecx, 4
0x180008d89  jz      loc_180008EC4
0x180008d8f  sub     ecx, 8
0x180008d92  jz      loc_180008E22
0x180008d98  sub     ecx, 10h
0x180008d9b  jz      loc_180008E70
0x180008da1  cmp     ecx, 20h ; ' '
0x180008da4  jz      loc_180008E49
0x180008daa  mov     pMedium, [rbx+10h]; pv
0x180008dae  test    pMedium, pMedium
0x180008db1  jnz     short loc_180008DD9
0x180008db3  and     dword ptr [rbx], 0
0x180008db6  add     rsp, 20h
0x180008dba  pop     rbx
0x180008dbb  retn
0x180008dbd  mov     pMedium, [rbx+8]; hMem
0x180008dc1  test    pMedium, pMedium
0x180008dc4  jz      short loc_180008DAA
0x180008dc6  test    rdx, rdx
0x180008dc9  jnz     short loc_180008DAA
0x180008dcb  call    cs:__imp_GlobalFree
0x180008dd2  nop     dword ptr [rax+rax+00h]
0x180008dd7  jmp     short loc_180008DAA
0x180008dd9  call    IsValidInterface
0x180008dde  test    eax, eax
0x180008de0  jz      short loc_180008DF2
0x180008de2  mov     pMedium, [rbx+10h]
0x180008de6  mov     rax, [pMedium]
0x180008de9  mov     rax, [rax+10h]
0x180008ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df2  and     qword ptr [rbx+10h], 0
0x180008df7  jmp     short loc_180008DB3
0x180008df9  mov     pMedium, [rbx+8]; lpFileName
0x180008dfd  test    pMedium, pMedium
0x180008e00  jz      short loc_180008DAA
0x180008e02  test    rdx, rdx
0x180008e05  jz      loc_180008EF3
0x180008e0b  mov     pMedium, [rbx+8]; pv
0x180008e0f  call    cs:__imp_CoTaskMemFree
0x180008e16  nop     dword ptr [rax+rax+00h]
0x180008e1b  and     qword ptr [rbx+8], 0
0x180008e20  jmp     short loc_180008DAA
0x180008e22  mov     pMedium, [rbx+8]; ho
0x180008e26  test    pMedium, pMedium
0x180008e29  jz      loc_180008DAA
0x180008e2f  test    rdx, rdx
0x180008e32  jnz     loc_180008DAA
0x180008e38  call    cs:__imp_DeleteObject
0x180008e3f  nop     dword ptr [rax+rax+00h]
0x180008e44  jmp     loc_180008DAA
0x180008e49  mov     pMedium, [rbx+8]; hmf
0x180008e4d  test    pMedium, pMedium
0x180008e50  jz      loc_180008DAA
0x180008e56  test    rdx, rdx
0x180008e59  jnz     loc_180008DAA
0x180008e5f  call    cs:__imp_DeleteEnhMetaFile
0x180008e66  nop     dword ptr [rax+rax+00h]
0x180008e6b  jmp     loc_180008DAA
0x180008e70  mov     pMedium, [rbx+8]; hMem
0x180008e74  test    pMedium, pMedium
0x180008e77  jz      loc_180008DAA
0x180008e7d  test    rdx, rdx
0x180008e80  jnz     loc_180008DAA
0x180008e86  call    cs:__imp_GlobalLock
0x180008e8d  nop     dword ptr [rax+rax+00h]
0x180008e92  test    rax, rax
0x180008e95  jz      loc_180008DAA
0x180008e9b  mov     pMedium, [rax+10h]; hmf
0x180008e9f  call    cs:__imp_DeleteMetaFile
0x180008ea6  nop     dword ptr [rax+rax+00h]
0x180008eab  mov     pMedium, [rbx+8]; hMem
0x180008eaf  call    cs:__imp_GlobalUnlock
0x180008eb6  nop     dword ptr [rax+rax+00h]
0x180008ebb  mov     pMedium, [rbx+8]
0x180008ebf  jmp     loc_180008DCB
0x180008ec4  mov     pMedium, [rbx+8]; pv
0x180008ec8  test    pMedium, pMedium
0x180008ecb  jz      loc_180008DAA
0x180008ed1  call    IsValidInterface
0x180008ed6  test    eax, eax
0x180008ed8  jz      loc_180008DAA
0x180008ede  mov     pMedium, [rbx+8]
0x180008ee2  mov     rax, [pMedium]
0x180008ee5  mov     rax, [rax+10h]
0x180008ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eee  jmp     loc_180008DAA
0x180008ef3  call    cs:__imp_DeleteFileW
0x180008efa  nop     dword ptr [rax+rax+00h]
0x180008eff  jmp     loc_180008E0B
```
