# vFreeMF(MF *)

- ea: `0x180029cc0`
- end: `0x180029d88`
- name: `?vFreeMF@@YAXPEAVMF@@@Z`
- size: `200`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180028ae0`
- `0x180028bac`
- `0x180028f18`
- `0x180029c30`
- `0x18002a8b0`

## callees

- `0x180029cc0`
- `0x180029d90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d74`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180029d64`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180029d64`
- `GDI32!DeleteDC` at `0x180029cde`
- `GDI32!DeleteDC` at `0x180029cde`

## pseudocode

```c
void __fastcall vFreeMF(_QWORD *hMem)
{
  HDC v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  const void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  if ( !gbDisableMetaFiles )
  {
    v2 = (HDC)hMem[91];
    if ( v2 )
      DeleteDC(v2);
    EMFContainer::Term((EMFContainer *)(hMem + 5));
    v3 = (void *)hMem[86];
    if ( v3 )
      LocalFree(v3);
    if ( (hMem[85] & 1) != 0 )
    {
      v5 = (const void *)hMem[3];
      if ( v5 )
        UnmapViewOfFile(v5);
      v6 = (void *)hMem[2];
      if ( v6 && CloseHandle(v6) )
        hMem[2] = 0;
    }
    else
    {
      v4 = (void *)hMem[4];
      if ( v4 )
        LocalFree(v4);
      if ( hMem[16] )
        goto LABEL_15;
    }
    v7 = (void *)hMem[1];
    if ( v7 != (void *)-1LL )
    {
      if ( CloseHandle(v7) )
        hMem[1] = 0;
    }
LABEL_15:
    *(_DWORD *)hMem = 0;
    LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x180029cc0  push    rbx
0x180029cc2  sub     rsp, 20h
0x180029cc6  cmp     cs:gbDisableMetaFiles, 0
0x180029ccd  mov     rbx, rcx
0x180029cd0  jnz     short loc_180029D42
0x180029cd2  mov     rcx, [rcx+2D8h]; hdc
0x180029cd9  test    rcx, rcx
0x180029cdc  jz      short loc_180029CE4
0x180029cde  call    cs:__imp_DeleteDC
0x180029ce4  lea     rcx, [rbx+28h]; this
0x180029ce8  call    ?Term@EMFContainer@@QEAAXXZ; EMFContainer::Term(void)
0x180029ced  mov     rcx, [rbx+2B0h]; hMem
0x180029cf4  test    rcx, rcx
0x180029cf7  jnz     short loc_180029D48
0x180029cf9  test    byte ptr [rbx+2A8h], 1
0x180029d00  jnz     short loc_180029D17
0x180029d02  mov     rcx, [rbx+20h]; hMem
0x180029d06  test    rcx, rcx
0x180029d09  jnz     short loc_180029D6C
0x180029d0b  cmp     qword ptr [rbx+80h], 0
0x180029d13  jz      short loc_180029D29
0x180029d15  jmp     short loc_180029D33
0x180029d17  mov     rcx, [rbx+18h]; lpBaseAddress
0x180029d1b  test    rcx, rcx
0x180029d1e  jnz     short loc_180029D64
0x180029d20  mov     rcx, [rbx+10h]; hObject
0x180029d24  test    rcx, rcx
0x180029d27  jnz     short loc_180029D50
0x180029d29  mov     rcx, [rbx+8]; hObject
0x180029d2d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029d31  jnz     short loc_180029D74
0x180029d33  mov     rcx, rbx; hMem
0x180029d36  mov     dword ptr [rbx], 0
0x180029d3c  call    cs:__imp_LocalFree
0x180029d42  add     rsp, 20h
0x180029d46  pop     rbx
0x180029d47  retn
0x180029d48  call    cs:__imp_LocalFree
0x180029d4e  jmp     short loc_180029CF9
0x180029d50  call    cs:__imp_CloseHandle
0x180029d56  test    eax, eax
0x180029d58  jz      short loc_180029D29
0x180029d5a  mov     qword ptr [rbx+10h], 0
0x180029d62  jmp     short loc_180029D29
0x180029d64  call    cs:__imp_UnmapViewOfFile
0x180029d6a  jmp     short loc_180029D20
0x180029d6c  call    cs:__imp_LocalFree
0x180029d72  jmp     short loc_180029D0B
0x180029d74  call    cs:__imp_CloseHandle
0x180029d7a  test    eax, eax
0x180029d7c  jz      short loc_180029D33
0x180029d7e  mov     qword ptr [rbx+8], 0
0x180029d86  jmp     short loc_180029D33
```
