# NcaUserStoreClose(NCA_USER_ *)

- ea: `0x1800175c8`
- end: `0x180017600`
- name: `?NcaUserStoreClose@@YAXPEAUNCA_USER_@@@Z`
- size: `56`
- prototype: `void __fastcall(struct NCA_USER_ *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180017610`
- `0x180018170`
- `0x180018354`

## callees

- `0x180003770`
- `0x180018fd4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800175d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800175d5`

## pseudocode

```c
void __fastcall NcaUserStoreClose(struct NCA_USER_ *lpMem)
{
  CloseThreadpoolWork(*((PTP_WORK *)lpMem + 5));
  NcaCloseHandle(*((_QWORD *)lpMem + 4));
  NcaFree(*((LPVOID *)lpMem + 3));
  NcaFree(lpMem);
}

```

## disassembly

```asm
0x1800175c8  push    rbx
0x1800175ca  sub     rsp, 20h
0x1800175ce  mov     rbx, rcx
0x1800175d1  mov     rcx, [rcx+28h]; pwk
0x1800175d5  call    cs:__imp_CloseThreadpoolWork
0x1800175dc  nop     dword ptr [rax+rax+00h]
0x1800175e1  mov     rcx, [rbx+20h]
0x1800175e5  call    NcaCloseHandle
0x1800175ea  mov     rcx, [rbx+18h]; lpMem
0x1800175ee  call    NcaFree
0x1800175f3  mov     rcx, rbx; lpMem
0x1800175f6  add     rsp, 20h
0x1800175fa  pop     rbx
0x1800175fb  jmp     NcaFree
```
