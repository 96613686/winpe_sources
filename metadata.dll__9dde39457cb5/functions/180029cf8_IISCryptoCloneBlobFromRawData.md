# IISCryptoCloneBlobFromRawData

- ea: `0x180029cf8`
- end: `0x180029d6b`
- name: `IISCryptoCloneBlobFromRawData`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001f8e4`
- `0x18002267c`
- `0x1800228b8`

## callees

- `0x180029cf8`
- `0x180029e8c`
- `0x18003098e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180029d1e`
- `ole32!CoTaskMemAlloc` at `0x180029d1e`
- `ole32!CoTaskMemFree` at `0x180029d50`
- `ole32!CoTaskMemFree` at `0x180029d50`

## pseudocode

```c
__int64 __fastcall IISCryptoCloneBlobFromRawData(_QWORD *a1, _DWORD *a2, int a3)
{
  unsigned int v3; // eax
  unsigned int v6; // r9d
  unsigned int v7; // edi
  void *v8; // rax
  void *v9; // rbx

  v3 = a2[1];
  v6 = v3 + 8;
  if ( v3 + 8 < v3 || v6 != a3 )
    return 2147942413LL;
  v7 = v3 + 8;
  v8 = CoTaskMemAlloc(v6);
  v9 = v8;
  if ( v8 )
  {
    memcpy_0(v8, a2, v7);
    if ( (unsigned int)IISCryptoIsValidBlob(v9) )
    {
      *a1 = v9;
      return 0;
    }
    CoTaskMemFree(v9);
    return 2147942413LL;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180029cf8  push    rbx
0x180029cfa  push    rbp
0x180029cfb  push    rsi
0x180029cfc  push    rdi
0x180029cfd  sub     rsp, 28h
0x180029d01  mov     eax, [rdx+4]
0x180029d04  mov     rbp, rdx
0x180029d07  mov     rsi, rcx
0x180029d0a  lea     r9d, [rax+8]
0x180029d0e  cmp     r9d, eax
0x180029d11  jb      short loc_180029D56
0x180029d13  cmp     r9d, r8d
0x180029d16  jnz     short loc_180029D56
0x180029d18  mov     ecx, r9d; cb
0x180029d1b  mov     edi, r9d
0x180029d1e  call    cs:__imp_CoTaskMemAlloc
0x180029d24  mov     rbx, rax
0x180029d27  test    rax, rax
0x180029d2a  jz      short loc_180029D64
0x180029d2c  mov     r8d, edi; Size
0x180029d2f  mov     rdx, rbp; Src
0x180029d32  mov     rcx, rax; void *
0x180029d35  call    memcpy_0
0x180029d3a  mov     rcx, rbx
0x180029d3d  call    IISCryptoIsValidBlob
0x180029d42  test    eax, eax
0x180029d44  jz      short loc_180029D4D
0x180029d46  mov     [rsi], rbx
0x180029d49  xor     eax, eax
0x180029d4b  jmp     short loc_180029D5B
0x180029d4d  mov     rcx, rbx; pv
0x180029d50  call    cs:__imp_CoTaskMemFree
0x180029d56  mov     eax, 8007000Dh
0x180029d5b  add     rsp, 28h
0x180029d5f  pop     rdi
0x180029d60  pop     rsi
0x180029d61  pop     rbp
0x180029d62  pop     rbx
0x180029d63  retn
0x180029d64  mov     eax, 80070008h
0x180029d69  jmp     short loc_180029D5B
```
