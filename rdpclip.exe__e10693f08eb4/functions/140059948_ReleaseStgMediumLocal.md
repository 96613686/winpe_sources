# ReleaseStgMediumLocal

- ea: `0x140059948`
- end: `0x140059a2a`
- name: `ReleaseStgMediumLocal`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140053860`
- `0x1400591c0`

## callees

- `0x140059948`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140059987`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140059987`
- `GDI32!DeleteMetaFile` at `0x1400599ea`
- `GDI32!DeleteMetaFile` at `0x1400599ea`
- `GDI32!DeleteObject` at `0x140059a0e`
- `GDI32!DeleteEnhMetaFile` at `0x1400599cb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140059a1e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140059a1e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1400599db`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1400599db`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1400599f4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1400599f4`

## pseudocode

```c
void __fastcall ReleaseStgMediumLocal(__int64 a1)
{
  __int64 v2; // rcx
  const WCHAR *v3; // rcx
  __int64 v4; // rcx
  HENHMETAFILE v5; // rcx
  void *v6; // rcx
  HMETAFILE *v7; // rax
  void *v8; // rcx
  void *v9; // rcx

  if ( *(_DWORD *)a1 == 2 )
  {
    v3 = *(const WCHAR **)(a1 + 8);
    if ( v3 && !*(_QWORD *)(a1 + 16) )
      DeleteFileW(v3);
  }
  else if ( *(_DWORD *)a1 == 4 || *(_DWORD *)a1 == 8 )
  {
    v2 = *(_QWORD *)(a1 + 8);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v4 = *(_QWORD *)(a1 + 16);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    return;
  }
  if ( *(_DWORD *)a1 == 1 )
  {
    v8 = *(void **)(a1 + 8);
    if ( !v8 )
      return;
    goto LABEL_23;
  }
  if ( *(_DWORD *)a1 != 16 )
  {
    if ( *(_DWORD *)a1 != 32 )
    {
      if ( *(_DWORD *)a1 == 64 )
      {
        v5 = *(HENHMETAFILE *)(a1 + 8);
        if ( v5 )
          DeleteEnhMetaFile(v5);
      }
      return;
    }
    v6 = *(void **)(a1 + 8);
    if ( !v6 )
      return;
    v7 = (HMETAFILE *)GlobalLock(v6);
    if ( !v7 )
      return;
    DeleteMetaFile(v7[2]);
    GlobalUnlock(*(HGLOBAL *)(a1 + 8));
    v8 = *(void **)(a1 + 8);
LABEL_23:
    GlobalFree(v8);
    return;
  }
  v9 = *(void **)(a1 + 8);
  if ( v9 )
    DeleteObject(v9);
}

```

## disassembly

```asm
0x140059948  push    rbx
0x14005994a  sub     rsp, 20h
0x14005994e  cmp     dword ptr [rcx], 2
0x140059951  mov     rbx, rcx
0x140059954  jz      short loc_140059977
0x140059956  cmp     dword ptr [rcx], 4
0x140059959  jz      short loc_140059960
0x14005995b  cmp     dword ptr [rcx], 8
0x14005995e  jnz     short loc_14005998D
0x140059960  mov     rcx, [rcx+8]
0x140059964  test    rcx, rcx
0x140059967  jz      short loc_14005998D
0x140059969  mov     rax, [rcx]
0x14005996c  mov     rax, [rax+10h]
0x140059970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059975  jmp     short loc_14005998D
0x140059977  mov     rcx, [rcx+8]; lpFileName
0x14005997b  test    rcx, rcx
0x14005997e  jz      short loc_14005998D
0x140059980  cmp     qword ptr [rbx+10h], 0
0x140059985  jnz     short loc_14005998D
0x140059987  call    cs:__imp_DeleteFileW
0x14005998d  mov     rcx, [rbx+10h]
0x140059991  test    rcx, rcx
0x140059994  jz      short loc_1400599A7
0x140059996  mov     rax, [rcx]
0x140059999  mov     rax, [rax+10h]
0x14005999d  add     rsp, 20h
0x1400599a1  pop     rbx
0x1400599a2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400599a7  mov     ecx, [rbx]
0x1400599a9  sub     ecx, 1
0x1400599ac  jz      short loc_140059A15
0x1400599ae  sub     ecx, 0Fh
0x1400599b1  jz      short loc_140059A00
0x1400599b3  sub     ecx, 10h
0x1400599b6  jz      short loc_1400599D2
0x1400599b8  cmp     ecx, 20h ; ' '
0x1400599bb  jnz     short loc_140059A24
0x1400599bd  mov     rcx, [rbx+8]
0x1400599c1  test    rcx, rcx
0x1400599c4  jz      short loc_140059A24
0x1400599c6  add     rsp, 20h
0x1400599ca  pop     rbx
0x1400599cb  jmp     cs:__imp_DeleteEnhMetaFile
0x1400599d2  mov     rcx, [rbx+8]; hMem
0x1400599d6  test    rcx, rcx
0x1400599d9  jz      short loc_140059A24
0x1400599db  call    cs:__imp_GlobalLock
0x1400599e1  test    rax, rax
0x1400599e4  jz      short loc_140059A24
0x1400599e6  mov     rcx, [rax+10h]; hmf
0x1400599ea  call    cs:__imp_DeleteMetaFile
0x1400599f0  mov     rcx, [rbx+8]; hMem
0x1400599f4  call    cs:__imp_GlobalUnlock
0x1400599fa  mov     rcx, [rbx+8]
0x1400599fe  jmp     short loc_140059A1E
0x140059a00  mov     rcx, [rbx+8]
0x140059a04  test    rcx, rcx
0x140059a07  jz      short loc_140059A24
0x140059a09  add     rsp, 20h
0x140059a0d  pop     rbx
0x140059a0e  jmp     cs:__imp_DeleteObject
0x140059a15  mov     rcx, [rbx+8]; hMem
0x140059a19  test    rcx, rcx
0x140059a1c  jz      short loc_140059A24
0x140059a1e  call    cs:__imp_GlobalFree
0x140059a24  add     rsp, 20h
0x140059a28  pop     rbx
0x140059a29  retn
```
