# vFreeMFAlt(MF *,int)

- ea: `0x18007e4d0`
- end: `0x18007e5d0`
- name: `?vFreeMFAlt@@YAXPEAVMF@@H@Z`
- size: `256`
- prototype: `void __fastcall(HLOCAL hMem, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180070a48`

## callees

- `0x1800335b4`
- `0x18007e4d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e53f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e5b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e53f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e5b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e575`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e575`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007e597`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007e560`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007e560`
- `GDI32!DeleteDC` at `0x18007e4f8`
- `GDI32!DeleteDC` at `0x18007e4f8`

## pseudocode

```c
void __fastcall vFreeMFAlt(_QWORD *hMem, int a2)
{
  HDC v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  const void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  if ( !gbDisableMetaFiles )
  {
    v4 = (HDC)hMem[91];
    if ( v4 )
      DeleteDC(v4);
    EMFContainer::Term((EMFContainer *)(hMem + 5));
    v5 = (void *)hMem[86];
    if ( v5 )
      LocalFree(v5);
    if ( !a2 )
      goto LABEL_20;
    if ( (hMem[85] & 1) != 0 )
    {
      v7 = (const void *)hMem[3];
      if ( v7 )
        UnmapViewOfFile(v7);
      v8 = (void *)hMem[2];
      if ( v8 && CloseHandle(v8) )
        hMem[2] = 0;
    }
    else
    {
      v6 = (void *)hMem[4];
      if ( v6 )
        LocalFree(v6);
      if ( hMem[16] )
        goto LABEL_20;
    }
    v9 = (void *)hMem[1];
    if ( v9 != (void *)-1LL )
    {
      if ( CloseHandle(v9) )
        hMem[1] = 0;
    }
LABEL_20:
    *(_DWORD *)hMem = 0;
    LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x18007e4d0  mov     [rsp+arg_0], rbx
0x18007e4d5  push    rdi
0x18007e4d6  sub     rsp, 20h
0x18007e4da  cmp     cs:gbDisableMetaFiles, 0
0x18007e4e1  mov     edi, edx
0x18007e4e3  mov     rbx, rcx
0x18007e4e6  jnz     loc_18007E5C4
0x18007e4ec  mov     rcx, [rcx+2D8h]; hdc
0x18007e4f3  test    rcx, rcx
0x18007e4f6  jz      short loc_18007E504
0x18007e4f8  call    cs:__imp_DeleteDC
0x18007e4ff  nop     dword ptr [rax+rax+00h]
0x18007e504  lea     rcx, [rbx+28h]; this
0x18007e508  call    ?Term@EMFContainer@@QEAAXXZ; EMFContainer::Term(void)
0x18007e50d  mov     rcx, [rbx+2B0h]; hMem
0x18007e514  test    rcx, rcx
0x18007e517  jz      short loc_18007E525
0x18007e519  call    cs:__imp_LocalFree
0x18007e520  nop     dword ptr [rax+rax+00h]
0x18007e525  test    edi, edi
0x18007e527  jz      loc_18007E5AF
0x18007e52d  test    byte ptr [rbx+2A8h], 1
0x18007e534  jnz     short loc_18007E557
0x18007e536  mov     rcx, [rbx+20h]; hMem
0x18007e53a  test    rcx, rcx
0x18007e53d  jz      short loc_18007E54B
0x18007e53f  call    cs:__imp_LocalFree
0x18007e546  nop     dword ptr [rax+rax+00h]
0x18007e54b  cmp     qword ptr [rbx+80h], 0
0x18007e553  jnz     short loc_18007E5AF
0x18007e555  jmp     short loc_18007E58D
0x18007e557  mov     rcx, [rbx+18h]; lpBaseAddress
0x18007e55b  test    rcx, rcx
0x18007e55e  jz      short loc_18007E56C
0x18007e560  call    cs:__imp_UnmapViewOfFile
0x18007e567  nop     dword ptr [rax+rax+00h]
0x18007e56c  mov     rcx, [rbx+10h]; hObject
0x18007e570  test    rcx, rcx
0x18007e573  jz      short loc_18007E58D
0x18007e575  call    cs:__imp_CloseHandle
0x18007e57c  nop     dword ptr [rax+rax+00h]
0x18007e581  test    eax, eax
0x18007e583  jz      short loc_18007E58D
0x18007e585  mov     qword ptr [rbx+10h], 0
0x18007e58d  mov     rcx, [rbx+8]; hObject
0x18007e591  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007e595  jz      short loc_18007E5AF
0x18007e597  call    cs:__imp_CloseHandle
0x18007e59e  nop     dword ptr [rax+rax+00h]
0x18007e5a3  test    eax, eax
0x18007e5a5  jz      short loc_18007E5AF
0x18007e5a7  mov     qword ptr [rbx+8], 0
0x18007e5af  mov     rcx, rbx; hMem
0x18007e5b2  mov     dword ptr [rbx], 0
0x18007e5b8  call    cs:__imp_LocalFree
0x18007e5bf  nop     dword ptr [rax+rax+00h]
0x18007e5c4  mov     rbx, [rsp+28h+arg_0]
0x18007e5c9  add     rsp, 20h
0x18007e5cd  pop     rdi
0x18007e5ce  retn
```
