# InMemoryRegRow::MapPropertyBag::CreatePropertyBag(ulong)

- ea: `0x180017c98`
- end: `0x180017d52`
- name: `?CreatePropertyBag@MapPropertyBag@InMemoryRegRow@@SAPEAU12@K@Z`
- size: `186`
- prototype: `struct InMemoryRegRow::MapPropertyBag *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017690`

## callees

- `0x180017c98`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017d28`

## pseudocode

```c
struct InMemoryRegRow::MapPropertyBag *__fastcall InMemoryRegRow::MapPropertyBag::CreatePropertyBag(unsigned int a1)
{
  __int64 v1; // rsi
  unsigned __int64 v2; // rbp
  void *v3; // rbx
  void *v4; // rax
  void *v5; // rdi
  __int64 i; // rdx
  __int64 v7; // rcx
  struct InMemoryRegRow::MapPropertyBag *result; // rax
  void *v9; // rcx

  v1 = a1;
  v2 = a1;
  v3 = CoTaskMemAlloc(saturated_mul(a1, 0x18u));
  if ( !v3 )
    return 0;
  v4 = CoTaskMemAlloc(saturated_mul(v2, 8u));
  v5 = v4;
  if ( !v4 )
  {
    v9 = v3;
    goto LABEL_7;
  }
  memset_0(v4, 0, 8 * v1);
  for ( i = 0; (unsigned int)i < (unsigned int)v1; *((_WORD *)v3 + 4 * v7) = 0 )
  {
    v7 = 3 * i;
    i = (unsigned int)(i + 1);
  }
  result = (struct InMemoryRegRow::MapPropertyBag *)CoTaskMemAlloc(0x20u);
  if ( !result )
  {
    CoTaskMemFree(v3);
    v9 = v5;
LABEL_7:
    CoTaskMemFree(v9);
    return 0;
  }
  *((_DWORD *)result + 4) = v1;
  *(_QWORD *)result = v5;
  *((_QWORD *)result + 1) = v3;
  *((_QWORD *)result + 3) = 0;
  return result;
}

```

## disassembly

```asm
0x180017c98  push    rbx
0x180017c9a  push    rbp
0x180017c9b  push    rsi
0x180017c9c  push    rdi
0x180017c9d  sub     rsp, 28h
0x180017ca1  mov     esi, ecx
0x180017ca3  mov     eax, 18h
0x180017ca8  mul     rsi
0x180017cab  mov     ebp, ecx
0x180017cad  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180017cb4  cmovb   rax, rdi
0x180017cb8  mov     rcx, rax; cb
0x180017cbb  call    cs:__imp_CoTaskMemAlloc
0x180017cc1  mov     rbx, rax
0x180017cc4  test    rax, rax
0x180017cc7  jz      short loc_180017D2E
0x180017cc9  lea     eax, [rdi+9]
0x180017ccc  mul     rbp
0x180017ccf  cmovb   rax, rdi
0x180017cd3  mov     rcx, rax; cb
0x180017cd6  call    cs:__imp_CoTaskMemAlloc
0x180017cdc  mov     rdi, rax
0x180017cdf  test    rax, rax
0x180017ce2  jz      short loc_180017D4D
0x180017ce4  lea     r8, ds:0[rsi*8]; Size
0x180017cec  xor     edx, edx; Val
0x180017cee  mov     rcx, rax; void *
0x180017cf1  call    memset_0
0x180017cf6  xor     edx, edx
0x180017cf8  test    esi, esi
0x180017cfa  jz      short loc_180017D0C
0x180017cfc  lea     rcx, [rdx+rdx*2]
0x180017d00  xor     eax, eax
0x180017d02  inc     edx
0x180017d04  mov     [rbx+rcx*8], ax
0x180017d08  cmp     edx, esi
0x180017d0a  jb      short loc_180017CFC
0x180017d0c  mov     ecx, 20h ; ' '; cb
0x180017d11  call    cs:__imp_CoTaskMemAlloc
0x180017d17  test    rax, rax
0x180017d1a  jnz     short loc_180017D39
0x180017d1c  mov     rcx, rbx; pv
0x180017d1f  call    cs:__imp_CoTaskMemFree
0x180017d25  mov     rcx, rdi; pv
0x180017d28  call    cs:__imp_CoTaskMemFree
0x180017d2e  xor     eax, eax
0x180017d30  add     rsp, 28h
0x180017d34  pop     rdi
0x180017d35  pop     rsi
0x180017d36  pop     rbp
0x180017d37  pop     rbx
0x180017d38  retn
0x180017d39  mov     [rax+10h], esi
0x180017d3c  mov     [rax], rdi
0x180017d3f  mov     [rax+8], rbx
0x180017d43  mov     qword ptr [rax+18h], 0
0x180017d4b  jmp     short loc_180017D30
0x180017d4d  mov     rcx, rbx
0x180017d50  jmp     short loc_180017D28
```
