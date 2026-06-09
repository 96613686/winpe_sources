# mwCloseFile

- ea: `0x180003bc0`
- end: `0x180003c5f`
- name: `mwCloseFile`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004318`
- `0x180005170`

## callees

- `0x180003bc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003bfd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003bfd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003c20`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003c20`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003c14`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003c14`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003c29`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003c29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bf0`
- `WINMM!mmioClose` at `0x180003bd8`
- `WINMM!mmioClose` at `0x180003bd8`

## pseudocode

```c
void __fastcall mwCloseFile(__int64 a1)
{
  HMMIO v2; // rcx
  void *v3; // rcx
  const void *v4; // rcx
  HGLOBAL v5; // rbx
  void *v6; // rcx

  v2 = *(HMMIO *)(a1 + 80);
  if ( v2 )
  {
    mmioClose(v2, 0);
    *(_QWORD *)(a1 + 80) = 0;
  }
  v3 = *(void **)(a1 + 88);
  if ( v3 != (void *)-1LL )
  {
    CloseHandle(v3);
    DeleteFileW((LPCWSTR)(a1 + 776));
    *(_QWORD *)(a1 + 88) = 0;
  }
  v4 = *(const void **)(a1 + 104);
  if ( v4 )
  {
    v5 = GlobalHandle(v4);
    GlobalUnlock(v5);
    GlobalFree(v5);
    *(_QWORD *)(a1 + 104) = 0;
  }
  v6 = *(void **)(a1 + 168);
  if ( v6 )
  {
    LocalFree(v6);
    *(_QWORD *)(a1 + 168) = 0;
  }
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_0], rbx
0x180003bc5  push    rdi
0x180003bc6  sub     rsp, 20h
0x180003bca  mov     rdi, rcx
0x180003bcd  mov     rcx, [rcx+50h]; hmmio
0x180003bd1  test    rcx, rcx
0x180003bd4  jz      short loc_180003BE6
0x180003bd6  xor     edx, edx; fuClose
0x180003bd8  call    cs:__imp_mmioClose
0x180003bde  mov     qword ptr [rdi+50h], 0
0x180003be6  mov     rcx, [rdi+58h]; hObject
0x180003bea  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003bee  jz      short loc_180003C0B
0x180003bf0  call    cs:__imp_CloseHandle
0x180003bf6  lea     rcx, [rdi+308h]; lpFileName
0x180003bfd  call    cs:__imp_DeleteFileW
0x180003c03  mov     qword ptr [rdi+58h], 0
0x180003c0b  mov     rcx, [rdi+68h]; pMem
0x180003c0f  test    rcx, rcx
0x180003c12  jz      short loc_180003C37
0x180003c14  call    cs:__imp_GlobalHandle
0x180003c1a  mov     rcx, rax; hMem
0x180003c1d  mov     rbx, rax
0x180003c20  call    cs:__imp_GlobalUnlock
0x180003c26  mov     rcx, rbx; hMem
0x180003c29  call    cs:__imp_GlobalFree
0x180003c2f  mov     qword ptr [rdi+68h], 0
0x180003c37  mov     rcx, [rdi+0A8h]; hMem
0x180003c3e  test    rcx, rcx
0x180003c41  jz      short loc_180003C54
0x180003c43  call    cs:__imp_LocalFree
0x180003c49  mov     qword ptr [rdi+0A8h], 0
0x180003c54  mov     rbx, [rsp+28h+arg_0]
0x180003c59  add     rsp, 20h
0x180003c5d  pop     rdi
0x180003c5e  retn
```
