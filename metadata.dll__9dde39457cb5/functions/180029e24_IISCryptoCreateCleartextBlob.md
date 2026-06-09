# IISCryptoCreateCleartextBlob

- ea: `0x180029e24`
- end: `0x180029e85`
- name: `IISCryptoCreateCleartextBlob`
- size: `97`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002a710`
- `0x18002a9c0`
- `0x18002b580`
- `0x18002b794`

## callees

- `0x180029e24`
- `0x18003098e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180029e48`
- `ole32!CoTaskMemAlloc` at `0x180029e48`

## pseudocode

```c
__int64 __fastcall IISCryptoCreateCleartextBlob(_QWORD *a1, const void *a2, unsigned int a3)
{
  unsigned __int64 v6; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  __int64 result; // rax

  v6 = a3 + 8LL;
  if ( v6 > 0xFFFFFFFF )
    return 2147942414LL;
  v7 = CoTaskMemAlloc((unsigned int)v6);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  *v7 = 1648583497;
  v7[1] = a3;
  memcpy_0(v7 + 2, a2, a3);
  result = 0;
  *a1 = v8;
  return result;
}

```

## disassembly

```asm
0x180029e24  push    rbx
0x180029e26  push    rbp
0x180029e27  push    rsi
0x180029e28  push    rdi
0x180029e29  push    r14
0x180029e2b  sub     rsp, 20h
0x180029e2f  mov     edi, r8d
0x180029e32  mov     r14, rcx
0x180029e35  mov     ecx, 0FFFFFFFFh
0x180029e3a  mov     rbp, rdx
0x180029e3d  lea     rax, [rdi+8]
0x180029e41  cmp     rax, rcx
0x180029e44  ja      short loc_180029E75
0x180029e46  mov     ecx, eax; cb
0x180029e48  call    cs:__imp_CoTaskMemAlloc
0x180029e4e  mov     rbx, rax
0x180029e51  test    rax, rax
0x180029e54  jz      short loc_180029E75
0x180029e56  lea     rcx, [rax+8]; void *
0x180029e5a  mov     dword ptr [rax], 62436349h
0x180029e60  mov     r8d, edi; Size
0x180029e63  mov     [rax+4], edi
0x180029e66  mov     rdx, rbp; Src
0x180029e69  call    memcpy_0
0x180029e6e  xor     eax, eax
0x180029e70  mov     [r14], rbx
0x180029e73  jmp     short loc_180029E7A
0x180029e75  mov     eax, 8007000Eh
0x180029e7a  add     rsp, 20h
0x180029e7e  pop     r14
0x180029e80  pop     rdi
0x180029e81  pop     rsi
0x180029e82  pop     rbp
0x180029e83  pop     rbx
0x180029e84  retn
```
