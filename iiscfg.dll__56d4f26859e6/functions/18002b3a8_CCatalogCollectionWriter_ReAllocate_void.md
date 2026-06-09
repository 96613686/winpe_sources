# CCatalogCollectionWriter::ReAllocate(void)

- ea: `0x18002b3a8`
- end: `0x18002b452`
- name: `?ReAllocate@CCatalogCollectionWriter@@AEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(CCatalogCollectionWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002b22c`

## callees

- `0x18002b3a8`
- `0x18002e0b2`
- `0x18002e0ca`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002b42e`
- `ole32!CoTaskMemFree` at `0x18002b42e`
- `ole32!CoTaskMemAlloc` at `0x18002b3d7`
- `ole32!CoTaskMemAlloc` at `0x18002b3d7`

## pseudocode

```c
__int64 __fastcall CCatalogCollectionWriter::ReAllocate(CCatalogCollectionWriter *this)
{
  void *v2; // rax
  void *v3; // rdi
  __int64 result; // rax
  const void *v5; // rdx

  v2 = CoTaskMemAlloc(saturated_mul((unsigned int)(*((_DWORD *)this + 38) + 700), 8u));
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  memset_0(v2, 0, 8LL * (unsigned int)(*((_DWORD *)this + 38) + 700));
  v5 = (const void *)*((_QWORD *)this + 18);
  if ( v5 )
  {
    memcpy_0(v3, v5, 8LL * *((unsigned int *)this + 38));
    CoTaskMemFree(*((LPVOID *)this + 18));
  }
  *((_DWORD *)this + 38) += 700;
  result = 0;
  *((_QWORD *)this + 18) = v3;
  return result;
}

```

## disassembly

```asm
0x18002b3a8  mov     [rsp+arg_0], rbx
0x18002b3ad  push    rdi
0x18002b3ae  sub     rsp, 20h
0x18002b3b2  mov     edx, [rcx+98h]
0x18002b3b8  mov     rbx, rcx
0x18002b3bb  add     edx, 2BCh
0x18002b3c1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002b3c8  mov     eax, 8
0x18002b3cd  mul     rdx
0x18002b3d0  cmovb   rax, rcx
0x18002b3d4  mov     rcx, rax; cb
0x18002b3d7  call    cs:__imp_CoTaskMemAlloc
0x18002b3dd  mov     rdi, rax
0x18002b3e0  test    rax, rax
0x18002b3e3  jnz     short loc_18002B3EC
0x18002b3e5  mov     eax, 8007000Eh
0x18002b3ea  jmp     short loc_18002B447
0x18002b3ec  mov     r8d, [rbx+98h]
0x18002b3f3  xor     edx, edx; Val
0x18002b3f5  add     r8d, 2BCh
0x18002b3fc  mov     rcx, rdi; void *
0x18002b3ff  shl     r8, 3; Size
0x18002b403  call    memset_0
0x18002b408  mov     rdx, [rbx+90h]; Src
0x18002b40f  test    rdx, rdx
0x18002b412  jz      short loc_18002B434
0x18002b414  mov     r8d, [rbx+98h]
0x18002b41b  mov     rcx, rdi; void *
0x18002b41e  shl     r8, 3; Size
0x18002b422  call    memcpy_0
0x18002b427  mov     rcx, [rbx+90h]; pv
0x18002b42e  call    cs:__imp_CoTaskMemFree
0x18002b434  add     dword ptr [rbx+98h], 2BCh
0x18002b43e  xor     eax, eax
0x18002b440  mov     [rbx+90h], rdi
0x18002b447  mov     rbx, [rsp+28h+arg_0]
0x18002b44c  add     rsp, 20h
0x18002b450  pop     rdi
0x18002b451  retn
```
