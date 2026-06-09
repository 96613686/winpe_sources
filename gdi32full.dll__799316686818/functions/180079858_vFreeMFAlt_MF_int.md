# vFreeMFAlt(MF *,int)

- ea: `0x180079858`
- end: `0x180079929`
- name: `?vFreeMFAlt@@YAXPEAVMF@@H@Z`
- size: `209`
- prototype: `void __fastcall(HLOCAL hMem, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006c0ec`

## callees

- `0x180029d90`
- `0x180079858`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007989b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800798b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007989b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800798b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079918`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800798fd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800798d2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800798d2`
- `GDI32!DeleteDC` at `0x180079880`
- `GDI32!DeleteDC` at `0x180079880`

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
0x180079858  mov     [rsp+arg_0], rbx
0x18007985d  push    rdi
0x18007985e  sub     rsp, 20h
0x180079862  cmp     cs:gbDisableMetaFiles, 0
0x180079869  mov     edi, edx
0x18007986b  mov     rbx, rcx
0x18007986e  jnz     loc_18007991E
0x180079874  mov     rcx, [rcx+2D8h]; hdc
0x18007987b  test    rcx, rcx
0x18007987e  jz      short loc_180079886
0x180079880  call    cs:__imp_DeleteDC
0x180079886  lea     rcx, [rbx+28h]; this
0x18007988a  call    ?Term@EMFContainer@@QEAAXXZ; EMFContainer::Term(void)
0x18007988f  mov     rcx, [rbx+2B0h]; hMem
0x180079896  test    rcx, rcx
0x180079899  jz      short loc_1800798A1
0x18007989b  call    cs:__imp_LocalFree
0x1800798a1  test    edi, edi
0x1800798a3  jz      short loc_18007990F
0x1800798a5  test    byte ptr [rbx+2A8h], 1
0x1800798ac  jnz     short loc_1800798C9
0x1800798ae  mov     rcx, [rbx+20h]; hMem
0x1800798b2  test    rcx, rcx
0x1800798b5  jz      short loc_1800798BD
0x1800798b7  call    cs:__imp_LocalFree
0x1800798bd  cmp     qword ptr [rbx+80h], 0
0x1800798c5  jnz     short loc_18007990F
0x1800798c7  jmp     short loc_1800798F3
0x1800798c9  mov     rcx, [rbx+18h]; lpBaseAddress
0x1800798cd  test    rcx, rcx
0x1800798d0  jz      short loc_1800798D8
0x1800798d2  call    cs:__imp_UnmapViewOfFile
0x1800798d8  mov     rcx, [rbx+10h]; hObject
0x1800798dc  test    rcx, rcx
0x1800798df  jz      short loc_1800798F3
0x1800798e1  call    cs:__imp_CloseHandle
0x1800798e7  test    eax, eax
0x1800798e9  jz      short loc_1800798F3
0x1800798eb  mov     qword ptr [rbx+10h], 0
0x1800798f3  mov     rcx, [rbx+8]; hObject
0x1800798f7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800798fb  jz      short loc_18007990F
0x1800798fd  call    cs:__imp_CloseHandle
0x180079903  test    eax, eax
0x180079905  jz      short loc_18007990F
0x180079907  mov     qword ptr [rbx+8], 0
0x18007990f  mov     rcx, rbx; hMem
0x180079912  mov     dword ptr [rbx], 0
0x180079918  call    cs:__imp_LocalFree
0x18007991e  mov     rbx, [rsp+28h+arg_0]
0x180079923  add     rsp, 20h
0x180079927  pop     rdi
0x180079928  retn
```
