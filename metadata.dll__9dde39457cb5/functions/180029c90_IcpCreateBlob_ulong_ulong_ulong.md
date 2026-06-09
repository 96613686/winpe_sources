# IcpCreateBlob(ulong,ulong,ulong)

- ea: `0x180029c90`
- end: `0x180029cf1`
- name: `?IcpCreateBlob@@YAPEFAU_IC_BLOB@@KKK@Z`
- size: `97`
- prototype: `struct _IC_BLOB *(unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002a710`
- `0x18002b580`
- `0x18002b794`

## callees

- `0x180029c64`
- `0x180029c90`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180029cbc`
- `ole32!CoTaskMemAlloc` at `0x180029cbc`
- `KERNEL32!SetLastError` at `0x180029cdd`
- `KERNEL32!SetLastError` at `0x180029cdd`

## pseudocode

```c
struct _IC_BLOB *__fastcall IcpCreateBlob(int a1, unsigned int a2, unsigned int a3)
{
  unsigned int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // eax
  _DWORD *v9; // rax
  _DWORD *v10; // rbx

  v6 = CALC_BLOB_DATA_LENGTH(a2, a3);
  v7 = v6;
  if ( v6 && (v8 = v6 + 8, v8 >= v7) )
  {
    v9 = CoTaskMemAlloc(v8);
    v10 = v9;
    if ( v9 )
    {
      *v9 = a1;
      v9[1] = v7;
      v9[2] = a2;
      v9[3] = a3;
    }
  }
  else
  {
    v10 = 0;
    SetLastError(8u);
  }
  return (struct _IC_BLOB *)v10;
}

```

## disassembly

```asm
0x180029c90  push    rbx
0x180029c92  push    rbp
0x180029c93  push    rsi
0x180029c94  push    rdi
0x180029c95  push    r14
0x180029c97  sub     rsp, 20h
0x180029c9b  mov     ebp, edx
0x180029c9d  mov     r14d, ecx
0x180029ca0  mov     ecx, ebp; unsigned int
0x180029ca2  mov     edx, r8d; unsigned int
0x180029ca5  mov     esi, r8d
0x180029ca8  call    ?CALC_BLOB_DATA_LENGTH@@YAKKK@Z; CALC_BLOB_DATA_LENGTH(ulong,ulong)
0x180029cad  mov     edi, eax
0x180029caf  test    eax, eax
0x180029cb1  jz      short loc_180029CD8
0x180029cb3  add     eax, 8
0x180029cb6  cmp     eax, edi
0x180029cb8  jb      short loc_180029CD8
0x180029cba  mov     ecx, eax; cb
0x180029cbc  call    cs:__imp_CoTaskMemAlloc
0x180029cc2  mov     rbx, rax
0x180029cc5  test    rax, rax
0x180029cc8  jz      short loc_180029CE3
0x180029cca  mov     [rax], r14d
0x180029ccd  mov     [rax+4], edi
0x180029cd0  mov     [rax+8], ebp
0x180029cd3  mov     [rax+0Ch], esi
0x180029cd6  jmp     short loc_180029CE3
0x180029cd8  xor     ebx, ebx
0x180029cda  lea     ecx, [rbx+8]; dwErrCode
0x180029cdd  call    cs:__imp_SetLastError
0x180029ce3  mov     rax, rbx
0x180029ce6  add     rsp, 20h
0x180029cea  pop     r14
0x180029cec  pop     rdi
0x180029ced  pop     rsi
0x180029cee  pop     rbp
0x180029cef  pop     rbx
0x180029cf0  retn
```
