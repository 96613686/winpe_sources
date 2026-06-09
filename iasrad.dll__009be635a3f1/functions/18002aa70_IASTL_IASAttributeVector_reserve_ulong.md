# IASTL::IASAttributeVector::reserve(ulong)

- ea: `0x18002aa70`
- end: `0x18002aaee`
- name: `?reserve@IASAttributeVector@IASTL@@QEAAXK@Z`
- size: `126`
- prototype: `void __fastcall(IASTL::IASAttributeVector *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a85c`
- `0x18002a8c4`
- `0x18002a9e0`

## callees

- `0x180002106`
- `0x18002a6bc`
- `0x18002aa70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aa8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aa8a`

## pseudocode

```c
void __fastcall IASTL::IASAttributeVector::reserve(IASTL::IASAttributeVector *this, unsigned int a2)
{
  char *v4; // rax
  int v5; // edx
  char *v6; // rsi
  size_t v7; // r14

  if ( a2 > *((_DWORD *)this + 4) )
  {
    v4 = (char *)CoTaskMemAlloc(16LL * a2);
    v6 = v4;
    if ( !v4 )
      IASTL::issue_error((IASTL *)0x8007000ELL, v5);
    v7 = 16LL * (unsigned int)((__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 4);
    memcpy_0(v4, *(const void **)this, v7);
    if ( *((_BYTE *)this + 20) )
      CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = v6;
    *((_QWORD *)this + 1) = &v6[v7];
    *((_DWORD *)this + 4) = a2;
    *((_BYTE *)this + 20) = 1;
  }
}

```

## disassembly

```asm
0x18002aa70  push    rbx
0x18002aa72  push    rsi
0x18002aa73  push    rdi
0x18002aa74  push    r14
0x18002aa76  sub     rsp, 28h
0x18002aa7a  mov     rbx, rcx
0x18002aa7d  mov     edi, edx
0x18002aa7f  cmp     edx, [rcx+10h]
0x18002aa82  jbe     short loc_18002AAE4
0x18002aa84  mov     ecx, edi
0x18002aa86  shl     rcx, 4; cb
0x18002aa8a  call    cs:__imp_CoTaskMemAlloc
0x18002aa90  mov     rsi, rax
0x18002aa93  test    rax, rax
0x18002aa96  jnz     short loc_18002AAA3
0x18002aa98  mov     ecx, 8007000Eh; this
0x18002aa9d  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18002aaa3  mov     r14, [rbx+8]
0x18002aaa7  mov     rcx, rsi; void *
0x18002aaaa  sub     r14, [rbx]
0x18002aaad  mov     rdx, [rbx]; Src
0x18002aab0  sar     r14, 4
0x18002aab4  mov     r14d, r14d
0x18002aab7  shl     r14, 4
0x18002aabb  mov     r8, r14; Size
0x18002aabe  call    memcpy_0
0x18002aac3  cmp     byte ptr [rbx+14h], 0
0x18002aac7  jz      short loc_18002AAD2
0x18002aac9  mov     rcx, [rbx]; pv
0x18002aacc  call    cs:__imp_CoTaskMemFree
0x18002aad2  lea     rax, [r14+rsi]
0x18002aad6  mov     [rbx], rsi
0x18002aad9  mov     [rbx+8], rax
0x18002aadd  mov     [rbx+10h], edi
0x18002aae0  mov     byte ptr [rbx+14h], 1
0x18002aae4  add     rsp, 28h
0x18002aae8  pop     r14
0x18002aaea  pop     rdi
0x18002aaeb  pop     rsi
0x18002aaec  pop     rbx
0x18002aaed  retn
```
