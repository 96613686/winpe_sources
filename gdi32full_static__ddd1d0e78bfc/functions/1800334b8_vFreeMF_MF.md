# vFreeMF(MF *)

- ea: `0x1800334b8`
- end: `0x1800335ae`
- name: `?vFreeMF@@YAXPEAVMF@@@Z`
- size: `246`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180031f30`
- `0x180032004`
- `0x18003261c`
- `0x180033420`
- `0x1800343a0`

## callees

- `0x1800334b8`
- `0x1800335b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003353a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003354d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033583`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003353a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003354d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003355b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033594`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003355b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033594`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180033575`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180033575`
- `GDI32!DeleteDC` at `0x1800334d6`
- `GDI32!DeleteDC` at `0x1800334d6`

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
0x1800334b8  push    rbx
0x1800334ba  sub     rsp, 20h
0x1800334be  cmp     cs:gbDisableMetaFiles, 0
0x1800334c5  mov     rbx, rcx
0x1800334c8  jnz     short loc_180033546
0x1800334ca  mov     rcx, [rcx+2D8h]; hdc
0x1800334d1  test    rcx, rcx
0x1800334d4  jz      short loc_1800334E2
0x1800334d6  call    cs:__imp_DeleteDC
0x1800334dd  nop     dword ptr [rax+rax+00h]
0x1800334e2  lea     rcx, [rbx+28h]; this
0x1800334e6  call    ?Term@EMFContainer@@QEAAXXZ; EMFContainer::Term(void)
0x1800334eb  mov     rcx, [rbx+2B0h]; hMem
0x1800334f2  test    rcx, rcx
0x1800334f5  jnz     short loc_18003354D
0x1800334f7  test    byte ptr [rbx+2A8h], 1
0x1800334fe  jnz     short loc_180033515
0x180033500  mov     rcx, [rbx+20h]; hMem
0x180033504  test    rcx, rcx
0x180033507  jnz     short loc_180033583
0x180033509  cmp     qword ptr [rbx+80h], 0
0x180033511  jz      short loc_180033527
0x180033513  jmp     short loc_180033531
0x180033515  mov     rcx, [rbx+18h]; lpBaseAddress
0x180033519  test    rcx, rcx
0x18003351c  jnz     short loc_180033575
0x18003351e  mov     rcx, [rbx+10h]; hObject
0x180033522  test    rcx, rcx
0x180033525  jnz     short loc_18003355B
0x180033527  mov     rcx, [rbx+8]; hObject
0x18003352b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003352f  jnz     short loc_180033594
0x180033531  mov     rcx, rbx; hMem
0x180033534  mov     dword ptr [rbx], 0
0x18003353a  call    cs:__imp_LocalFree
0x180033541  nop     dword ptr [rax+rax+00h]
0x180033546  add     rsp, 20h
0x18003354a  pop     rbx
0x18003354b  retn
0x18003354d  call    cs:__imp_LocalFree
0x180033554  nop     dword ptr [rax+rax+00h]
0x180033559  jmp     short loc_1800334F7
0x18003355b  call    cs:__imp_CloseHandle
0x180033562  nop     dword ptr [rax+rax+00h]
0x180033567  test    eax, eax
0x180033569  jz      short loc_180033527
0x18003356b  mov     qword ptr [rbx+10h], 0
0x180033573  jmp     short loc_180033527
0x180033575  call    cs:__imp_UnmapViewOfFile
0x18003357c  nop     dword ptr [rax+rax+00h]
0x180033581  jmp     short loc_18003351E
0x180033583  call    cs:__imp_LocalFree
0x18003358a  nop     dword ptr [rax+rax+00h]
0x18003358f  jmp     loc_180033509
0x180033594  call    cs:__imp_CloseHandle
0x18003359b  nop     dword ptr [rax+rax+00h]
0x1800335a0  test    eax, eax
0x1800335a2  jz      short loc_180033531
0x1800335a4  mov     qword ptr [rbx+8], 0
0x1800335ac  jmp     short loc_180033531
```
