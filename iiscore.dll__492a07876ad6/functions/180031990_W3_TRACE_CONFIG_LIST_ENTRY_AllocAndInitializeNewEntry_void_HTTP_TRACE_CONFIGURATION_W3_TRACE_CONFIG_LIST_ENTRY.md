# W3_TRACE_CONFIG_LIST_ENTRY::AllocAndInitializeNewEntry(void *,HTTP_TRACE_CONFIGURATION *,W3_TRACE_CONFIG_LIST_ENTRY *,bool *)

- ea: `0x180031990`
- end: `0x180031a31`
- name: `?AllocAndInitializeNewEntry@W3_TRACE_CONFIG_LIST_ENTRY@@SAPEAV1@PEAXPEAUHTTP_TRACE_CONFIGURATION@@PEAV1@PEA_N@Z`
- size: `161`
- prototype: `struct W3_TRACE_CONFIG_LIST_ENTRY *__fastcall(void *, struct HTTP_TRACE_CONFIGURATION *, struct W3_TRACE_CONFIG_LIST_ENTRY *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180032774`

## callees

- `0x180031990`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800319bd`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800319bd`

## pseudocode

```c
struct W3_TRACE_CONFIG_LIST_ENTRY *__fastcall W3_TRACE_CONFIG_LIST_ENTRY::AllocAndInitializeNewEntry(
        void *a1,
        struct HTTP_TRACE_CONFIGURATION *a2,
        struct W3_TRACE_CONFIG_LIST_ENTRY *a3,
        bool *a4)
{
  struct W3_TRACE_CONFIG_LIST_ENTRY *result; // rax

  if ( *a4 || !a3 )
  {
    result = (struct W3_TRACE_CONFIG_LIST_ENTRY *)ALLOC_CACHE_HANDLER::Alloc(W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries);
    a3 = result;
    if ( !result )
      return result;
    *(_OWORD *)result = 0;
    *((_QWORD *)result + 2) = 0;
    *(_OWORD *)((char *)result + 24) = 0;
    *((_QWORD *)result + 5) = 0;
    *((_OWORD *)result + 3) = 0;
    *((_BYTE *)result + 64) = 1;
  }
  else
  {
    *a4 = 1;
    *((_BYTE *)a3 + 64) = 0;
  }
  *((_QWORD *)a3 + 2) = a1;
  if ( a2 )
  {
    *((_OWORD *)a3 + 3) = *a2->pProviderGuid;
    *(_OWORD *)((char *)a3 + 24) = *(_OWORD *)&a2->pProviderGuid;
    *((_QWORD *)a3 + 5) = *(_QWORD *)&a2->fProviderEnabled;
    *((_QWORD *)a3 + 3) = (char *)a3 + 48;
  }
  return a3;
}

```

## disassembly

```asm
0x180031990  mov     [rsp+arg_0], rbx
0x180031995  push    rdi
0x180031996  sub     rsp, 20h
0x18003199a  cmp     byte ptr [r9], 0
0x18003199e  mov     rbx, rdx
0x1800319a1  mov     rdi, rcx
0x1800319a4  jnz     short loc_1800319B6
0x1800319a6  test    r8, r8
0x1800319a9  jz      short loc_1800319B6
0x1800319ab  mov     byte ptr [r9], 1
0x1800319af  mov     byte ptr [r8+40h], 0
0x1800319b4  jmp     short loc_1800319F4
0x1800319b6  mov     rcx, cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x1800319bd  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800319c4  nop     dword ptr [rax+rax+00h]
0x1800319c9  mov     r8, rax
0x1800319cc  test    rax, rax
0x1800319cf  jz      short loc_180031A25
0x1800319d1  xorps   xmm0, xmm0
0x1800319d4  movups  xmmword ptr [rax], xmm0
0x1800319d7  mov     qword ptr [rax+10h], 0
0x1800319df  xor     eax, eax
0x1800319e1  movups  xmmword ptr [r8+18h], xmm0
0x1800319e6  mov     [r8+28h], rax
0x1800319ea  movups  xmmword ptr [r8+30h], xmm0
0x1800319ef  mov     byte ptr [r8+40h], 1
0x1800319f4  mov     [r8+10h], rdi
0x1800319f8  test    rbx, rbx
0x1800319fb  jz      short loc_180031A22
0x1800319fd  mov     rcx, [rbx]
0x180031a00  lea     rdx, [r8+30h]
0x180031a04  movups  xmm0, xmmword ptr [rcx]
0x180031a07  movdqu  xmmword ptr [rdx], xmm0
0x180031a0b  movups  xmm0, xmmword ptr [rbx]
0x180031a0e  movups  xmmword ptr [r8+18h], xmm0
0x180031a13  movsd   xmm1, qword ptr [rbx+10h]
0x180031a18  movsd   qword ptr [r8+28h], xmm1
0x180031a1e  mov     [r8+18h], rdx
0x180031a22  mov     rax, r8
0x180031a25  mov     rbx, [rsp+28h+arg_0]
0x180031a2a  add     rsp, 20h
0x180031a2e  pop     rdi
0x180031a2f  retn
```
