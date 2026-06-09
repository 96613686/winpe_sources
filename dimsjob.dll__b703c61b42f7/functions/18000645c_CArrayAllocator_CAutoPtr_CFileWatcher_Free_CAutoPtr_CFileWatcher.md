# _CArrayAllocator<CAutoPtr<CFileWatcher>>::Free(CAutoPtr<CFileWatcher> *)

- ea: `0x18000645c`
- end: `0x18000648e`
- name: `?Free@?$_CArrayAllocator@U?$CAutoPtr@VCFileWatcher@@@@@@SAXPEAU?$CAutoPtr@VCFileWatcher@@@@@Z`
- size: `50`
- prototype: `HLOCAL __fastcall(char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002380`
- `0x1800025b0`
- `0x180003340`

## callees

- `0x180004b88`
- `0x18000645c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006481`

## pseudocode

```c
HLOCAL __fastcall _CArrayAllocator<CAutoPtr<CFileWatcher>>::Free(char *a1)
{
  char *v1; // rbx
  HLOCAL result; // rax

  if ( a1 )
  {
    v1 = a1 - 8;
    `eh vector destructor iterator'(a1, 8u, *((_QWORD *)a1 - 1), CAutoPtr<CFileWatcher>::~CAutoPtr<CFileWatcher>);
    return LocalFree(v1);
  }
  return result;
}

```

## disassembly

```asm
0x18000645c  test    rcx, rcx
0x18000645f  jz      short locret_18000648D
0x180006461  push    rbx
0x180006462  sub     rsp, 20h
0x180006466  lea     rbx, [rcx-8]
0x18000646a  lea     r9, ??1?$CAutoPtr@VCFileWatcher@@@@QEAA@XZ; void (*)(void *)
0x180006471  mov     r8, [rbx]; unsigned __int64
0x180006474  mov     edx, 8; unsigned __int64
0x180006479  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000647e  mov     rcx, rbx; hMem
0x180006481  call    cs:__imp_LocalFree
0x180006487  nop
0x180006488  add     rsp, 20h
0x18000648c  pop     rbx
0x18000648d  retn
```
