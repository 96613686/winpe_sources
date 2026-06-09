# ReleaseStgMediumLocal

- ea: `0x1800d8618`
- end: `0x1800d86fa`
- name: `ReleaseStgMediumLocal`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800d2560`
- `0x1800d7e90`

## callees

- `0x1800d8618`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d86ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800d86ee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d8657`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d8657`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800d86c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800d86c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800d86ab`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800d86ab`
- `GDI32!DeleteObject` at `0x1800d86de`
- `GDI32!DeleteEnhMetaFile` at `0x1800d869b`
- `GDI32!DeleteMetaFile` at `0x1800d86ba`
- `GDI32!DeleteMetaFile` at `0x1800d86ba`

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
0x1800d8618  push    rbx
0x1800d861a  sub     rsp, 20h
0x1800d861e  cmp     dword ptr [rcx], 2
0x1800d8621  mov     rbx, rcx
0x1800d8624  jz      short loc_1800D8647
0x1800d8626  cmp     dword ptr [rcx], 4
0x1800d8629  jz      short loc_1800D8630
0x1800d862b  cmp     dword ptr [rcx], 8
0x1800d862e  jnz     short loc_1800D865D
0x1800d8630  mov     rcx, [rcx+8]
0x1800d8634  test    rcx, rcx
0x1800d8637  jz      short loc_1800D865D
0x1800d8639  mov     rax, [rcx]
0x1800d863c  mov     rax, [rax+10h]
0x1800d8640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8645  jmp     short loc_1800D865D
0x1800d8647  mov     rcx, [rcx+8]; lpFileName
0x1800d864b  test    rcx, rcx
0x1800d864e  jz      short loc_1800D865D
0x1800d8650  cmp     qword ptr [rbx+10h], 0
0x1800d8655  jnz     short loc_1800D865D
0x1800d8657  call    cs:__imp_DeleteFileW
0x1800d865d  mov     rcx, [rbx+10h]
0x1800d8661  test    rcx, rcx
0x1800d8664  jz      short loc_1800D8677
0x1800d8666  mov     rax, [rcx]
0x1800d8669  mov     rax, [rax+10h]
0x1800d866d  add     rsp, 20h
0x1800d8671  pop     rbx
0x1800d8672  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8677  mov     ecx, [rbx]
0x1800d8679  sub     ecx, 1
0x1800d867c  jz      short loc_1800D86E5
0x1800d867e  sub     ecx, 0Fh
0x1800d8681  jz      short loc_1800D86D0
0x1800d8683  sub     ecx, 10h
0x1800d8686  jz      short loc_1800D86A2
0x1800d8688  cmp     ecx, 20h ; ' '
0x1800d868b  jnz     short loc_1800D86F4
0x1800d868d  mov     rcx, [rbx+8]
0x1800d8691  test    rcx, rcx
0x1800d8694  jz      short loc_1800D86F4
0x1800d8696  add     rsp, 20h
0x1800d869a  pop     rbx
0x1800d869b  jmp     cs:__imp_DeleteEnhMetaFile
0x1800d86a2  mov     rcx, [rbx+8]; hMem
0x1800d86a6  test    rcx, rcx
0x1800d86a9  jz      short loc_1800D86F4
0x1800d86ab  call    cs:__imp_GlobalLock
0x1800d86b1  test    rax, rax
0x1800d86b4  jz      short loc_1800D86F4
0x1800d86b6  mov     rcx, [rax+10h]; hmf
0x1800d86ba  call    cs:__imp_DeleteMetaFile
0x1800d86c0  mov     rcx, [rbx+8]; hMem
0x1800d86c4  call    cs:__imp_GlobalUnlock
0x1800d86ca  mov     rcx, [rbx+8]
0x1800d86ce  jmp     short loc_1800D86EE
0x1800d86d0  mov     rcx, [rbx+8]
0x1800d86d4  test    rcx, rcx
0x1800d86d7  jz      short loc_1800D86F4
0x1800d86d9  add     rsp, 20h
0x1800d86dd  pop     rbx
0x1800d86de  jmp     cs:__imp_DeleteObject
0x1800d86e5  mov     rcx, [rbx+8]; hMem
0x1800d86e9  test    rcx, rcx
0x1800d86ec  jz      short loc_1800D86F4
0x1800d86ee  call    cs:__imp_GlobalFree
0x1800d86f4  add     rsp, 20h
0x1800d86f8  pop     rbx
0x1800d86f9  retn
```
