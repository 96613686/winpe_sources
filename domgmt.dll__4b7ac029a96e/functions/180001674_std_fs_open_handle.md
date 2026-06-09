# __std_fs_open_handle

- ea: `0x180001674`
- end: `0x1800016c7`
- name: `__std_fs_open_handle`
- size: `83`
- prototype: `DWORD __fastcall(__int64 *, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800012e8`

## callees

- `0x180001190`
- `0x180001674`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016c0`

## pseudocode

```c
DWORD __fastcall _std_fs_open_handle(__int64 *a1, int a2, int a3, int a4)
{
  __int64 File; // rax

  File = anonymous_namespace_::__vcp_CreateFile(a2, a3, 7, 0, 3, a4, 0);
  *a1 = File;
  if ( File == -1 )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x180001674  push    rbx
0x180001676  sub     rsp, 40h
0x18000167a  mov     eax, r8d
0x18000167d  mov     [rsp+48h+var_18], 0
0x180001686  mov     [rsp+48h+var_20], r9d
0x18000168b  mov     r10, rdx
0x18000168e  xor     r9d, r9d
0x180001691  mov     [rsp+48h+var_28], 3
0x180001699  mov     rbx, rcx
0x18000169c  mov     edx, eax
0x18000169e  mov     rcx, r10
0x1800016a1  lea     r8d, [r9+7]
0x1800016a5  call    _anonymous_namespace_____vcp_CreateFile
0x1800016aa  mov     [rbx], rax
0x1800016ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800016b1  jz      short loc_1800016BB
0x1800016b3  xor     eax, eax
0x1800016b5  add     rsp, 40h
0x1800016b9  pop     rbx
0x1800016ba  retn
0x1800016bb  add     rsp, 40h
0x1800016bf  pop     rbx
0x1800016c0  jmp     cs:__imp_GetLastError
```
