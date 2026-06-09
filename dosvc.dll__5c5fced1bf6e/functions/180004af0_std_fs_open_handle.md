# __std_fs_open_handle

- ea: `0x180004af0`
- end: `0x180004b43`
- name: `__std_fs_open_handle`
- size: `83`
- prototype: `DWORD __fastcall(__int64 *, int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004764`

## callees

- `0x18000460c`
- `0x180004af0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b3c`

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
0x180004af0  push    rbx
0x180004af2  sub     rsp, 40h
0x180004af6  mov     eax, r8d
0x180004af9  mov     [rsp+48h+var_18], 0
0x180004b02  mov     [rsp+48h+var_20], r9d
0x180004b07  mov     r10, rdx
0x180004b0a  xor     r9d, r9d
0x180004b0d  mov     [rsp+48h+var_28], 3
0x180004b15  mov     rbx, rcx
0x180004b18  mov     edx, eax
0x180004b1a  mov     rcx, r10
0x180004b1d  lea     r8d, [r9+7]
0x180004b21  call    _anonymous_namespace_____vcp_CreateFile
0x180004b26  mov     [rbx], rax
0x180004b29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004b2d  jz      short loc_180004B37
0x180004b2f  xor     eax, eax
0x180004b31  add     rsp, 40h
0x180004b35  pop     rbx
0x180004b36  retn
0x180004b37  add     rsp, 40h
0x180004b3b  pop     rbx
0x180004b3c  jmp     cs:__imp_GetLastError
```
