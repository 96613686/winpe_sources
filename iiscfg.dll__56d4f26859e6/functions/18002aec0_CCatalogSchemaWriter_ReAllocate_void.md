# CCatalogSchemaWriter::ReAllocate(void)

- ea: `0x18002aec0`
- end: `0x18002af49`
- name: `?ReAllocate@CCatalogSchemaWriter@@AEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(CCatalogSchemaWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002adcc`

## callees

- `0x18002aec0`
- `0x18002e0b2`
- `0x18002e0ca`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002af2f`
- `ole32!CoTaskMemFree` at `0x18002af2f`
- `ole32!CoTaskMemAlloc` at `0x18002aee9`
- `ole32!CoTaskMemAlloc` at `0x18002aee9`

## pseudocode

```c
__int64 __fastcall CCatalogSchemaWriter::ReAllocate(CCatalogSchemaWriter *this)
{
  void *v2; // rax
  void *v3; // rdi
  __int64 result; // rax

  v2 = CoTaskMemAlloc(saturated_mul((unsigned int)(*((_DWORD *)this + 2) + 50), 8u));
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  memset_0(v2, 0, 8LL * (unsigned int)(*((_DWORD *)this + 2) + 50));
  if ( *(_QWORD *)this )
  {
    memcpy_0(v3, *(const void **)this, 8LL * *((unsigned int *)this + 2));
    CoTaskMemFree(*(LPVOID *)this);
  }
  *((_DWORD *)this + 2) += 50;
  result = 0;
  *(_QWORD *)this = v3;
  return result;
}

```

## disassembly

```asm
0x18002aec0  mov     [rsp+arg_0], rbx
0x18002aec5  push    rdi
0x18002aec6  sub     rsp, 20h
0x18002aeca  mov     edx, [rcx+8]
0x18002aecd  mov     rbx, rcx
0x18002aed0  add     edx, 32h ; '2'
0x18002aed3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002aeda  mov     eax, 8
0x18002aedf  mul     rdx
0x18002aee2  cmovb   rax, rcx
0x18002aee6  mov     rcx, rax; cb
0x18002aee9  call    cs:__imp_CoTaskMemAlloc
0x18002aeef  mov     rdi, rax
0x18002aef2  test    rax, rax
0x18002aef5  jnz     short loc_18002AEFE
0x18002aef7  mov     eax, 8007000Eh
0x18002aefc  jmp     short loc_18002AF3E
0x18002aefe  mov     r8d, [rbx+8]
0x18002af02  xor     edx, edx; Val
0x18002af04  add     r8d, 32h ; '2'
0x18002af08  mov     rcx, rdi; void *
0x18002af0b  shl     r8, 3; Size
0x18002af0f  call    memset_0
0x18002af14  mov     rdx, [rbx]; Src
0x18002af17  test    rdx, rdx
0x18002af1a  jz      short loc_18002AF35
0x18002af1c  mov     r8d, [rbx+8]
0x18002af20  mov     rcx, rdi; void *
0x18002af23  shl     r8, 3; Size
0x18002af27  call    memcpy_0
0x18002af2c  mov     rcx, [rbx]; pv
0x18002af2f  call    cs:__imp_CoTaskMemFree
0x18002af35  add     dword ptr [rbx+8], 32h ; '2'
0x18002af39  xor     eax, eax
0x18002af3b  mov     [rbx], rdi
0x18002af3e  mov     rbx, [rsp+28h+arg_0]
0x18002af43  add     rsp, 20h
0x18002af47  pop     rdi
0x18002af48  retn
```
