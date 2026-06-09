# CCatalogPropertyWriter::ReAllocate(void)

- ea: `0x18002bb54`
- end: `0x18002bbfa`
- name: `?ReAllocate@CCatalogPropertyWriter@@AEAAJXZ`
- size: `166`
- prototype: `__int64 __fastcall(CCatalogPropertyWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180023e00`

## callees

- `0x18002bb54`
- `0x18002e0b2`
- `0x18002e0ca`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002bbd9`
- `ole32!CoTaskMemFree` at `0x18002bbd9`
- `ole32!CoTaskMemAlloc` at `0x18002bb80`
- `ole32!CoTaskMemAlloc` at `0x18002bb80`

## pseudocode

```c
__int64 __fastcall CCatalogPropertyWriter::ReAllocate(CCatalogPropertyWriter *this)
{
  void *v2; // rdi
  __int64 result; // rax
  const void *v4; // rdx

  v2 = CoTaskMemAlloc(saturated_mul((unsigned int)(*((_DWORD *)this + 60) + 32), 0x30u));
  if ( !v2 )
    return 2147942414LL;
  memset_0(v2, 0, 48LL * (unsigned int)(*((_DWORD *)this + 60) + 32));
  v4 = (const void *)*((_QWORD *)this + 29);
  if ( v4 )
  {
    memcpy_0(v2, v4, 48LL * *((unsigned int *)this + 60));
    CoTaskMemFree(*((LPVOID *)this + 29));
  }
  *((_DWORD *)this + 60) += 32;
  result = 0;
  *((_QWORD *)this + 29) = v2;
  return result;
}

```

## disassembly

```asm
0x18002bb54  mov     [rsp+arg_0], rbx
0x18002bb59  push    rdi
0x18002bb5a  sub     rsp, 20h
0x18002bb5e  mov     edx, [rcx+0F0h]
0x18002bb64  mov     rbx, rcx
0x18002bb67  add     edx, 20h ; ' '
0x18002bb6a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002bb71  mov     eax, 30h ; '0'
0x18002bb76  mul     rdx
0x18002bb79  cmovb   rax, rcx
0x18002bb7d  mov     rcx, rax; cb
0x18002bb80  call    cs:__imp_CoTaskMemAlloc
0x18002bb86  mov     rdi, rax
0x18002bb89  test    rax, rax
0x18002bb8c  jnz     short loc_18002BB95
0x18002bb8e  mov     eax, 8007000Eh
0x18002bb93  jmp     short loc_18002BBEF
0x18002bb95  mov     eax, [rbx+0F0h]
0x18002bb9b  xor     edx, edx; Val
0x18002bb9d  add     eax, 20h ; ' '
0x18002bba0  mov     rcx, rdi; void *
0x18002bba3  lea     r8, [rax+rax*2]
0x18002bba7  shl     r8, 4; Size
0x18002bbab  call    memset_0
0x18002bbb0  mov     rdx, [rbx+0E8h]; Src
0x18002bbb7  test    rdx, rdx
0x18002bbba  jz      short loc_18002BBDF
0x18002bbbc  mov     eax, [rbx+0F0h]
0x18002bbc2  mov     rcx, rdi; void *
0x18002bbc5  lea     r8, [rax+rax*2]
0x18002bbc9  shl     r8, 4; Size
0x18002bbcd  call    memcpy_0
0x18002bbd2  mov     rcx, [rbx+0E8h]; pv
0x18002bbd9  call    cs:__imp_CoTaskMemFree
0x18002bbdf  add     dword ptr [rbx+0F0h], 20h ; ' '
0x18002bbe6  xor     eax, eax
0x18002bbe8  mov     [rbx+0E8h], rdi
0x18002bbef  mov     rbx, [rsp+28h+arg_0]
0x18002bbf4  add     rsp, 20h
0x18002bbf8  pop     rdi
0x18002bbf9  retn
```
