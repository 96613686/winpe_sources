# IASTL::IASAttributeVector::reserve(ulong)

- ea: `0x18000be24`
- end: `0x18000bea2`
- name: `?reserve@IASAttributeVector@IASTL@@QEAAXK@Z`
- size: `126`
- prototype: `void __fastcall(IASTL::IASAttributeVector *__hidden this, unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000baa8`
- `0x18000bb10`
- `0x18000bbf8`
- `0x18000bd84`
- `0x18001a738`
- `0x18001b7bc`
- `0x1800241e0`
- `0x180024dcc`

## callees

- `0x180001f26`
- `0x18000b81c`
- `0x18000be24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be80`

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
0x18000be24  push    rbx
0x18000be26  push    rsi
0x18000be27  push    rdi
0x18000be28  push    r14
0x18000be2a  sub     rsp, 28h
0x18000be2e  mov     rbx, rcx
0x18000be31  mov     edi, edx
0x18000be33  cmp     edx, [rcx+10h]
0x18000be36  jbe     short loc_18000BE98
0x18000be38  mov     ecx, edi
0x18000be3a  shl     rcx, 4; cb
0x18000be3e  call    cs:__imp_CoTaskMemAlloc
0x18000be44  mov     rsi, rax
0x18000be47  test    rax, rax
0x18000be4a  jnz     short loc_18000BE57
0x18000be4c  mov     ecx, 8007000Eh; this
0x18000be51  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18000be57  mov     r14, [rbx+8]
0x18000be5b  mov     rcx, rsi; void *
0x18000be5e  sub     r14, [rbx]
0x18000be61  mov     rdx, [rbx]; Src
0x18000be64  sar     r14, 4
0x18000be68  mov     r14d, r14d
0x18000be6b  shl     r14, 4
0x18000be6f  mov     r8, r14; Size
0x18000be72  call    memcpy_0
0x18000be77  cmp     byte ptr [rbx+14h], 0
0x18000be7b  jz      short loc_18000BE86
0x18000be7d  mov     rcx, [rbx]; pv
0x18000be80  call    cs:__imp_CoTaskMemFree
0x18000be86  lea     rax, [r14+rsi]
0x18000be8a  mov     [rbx], rsi
0x18000be8d  mov     [rbx+8], rax
0x18000be91  mov     [rbx+10h], edi
0x18000be94  mov     byte ptr [rbx+14h], 1
0x18000be98  add     rsp, 28h
0x18000be9c  pop     r14
0x18000be9e  pop     rdi
0x18000be9f  pop     rsi
0x18000bea0  pop     rbx
0x18000bea1  retn
```
