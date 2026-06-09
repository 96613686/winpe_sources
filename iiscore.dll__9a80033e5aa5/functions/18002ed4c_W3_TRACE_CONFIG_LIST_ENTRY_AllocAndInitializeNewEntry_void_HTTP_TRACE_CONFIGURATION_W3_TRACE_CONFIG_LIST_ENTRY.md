# W3_TRACE_CONFIG_LIST_ENTRY::AllocAndInitializeNewEntry(void *,HTTP_TRACE_CONFIGURATION *,W3_TRACE_CONFIG_LIST_ENTRY *,bool *)

- ea: `0x18002ed4c`
- end: `0x18002ede6`
- name: `?AllocAndInitializeNewEntry@W3_TRACE_CONFIG_LIST_ENTRY@@SAPEAV1@PEAXPEAUHTTP_TRACE_CONFIGURATION@@PEAV1@PEA_N@Z`
- size: `154`
- prototype: `struct W3_TRACE_CONFIG_LIST_ENTRY *__fastcall(void *, struct HTTP_TRACE_CONFIGURATION *, struct W3_TRACE_CONFIG_LIST_ENTRY *, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002fb14`

## callees

- `0x18002ed4c`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18002ed79`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18002ed79`

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
0x18002ed4c  mov     [rsp+arg_0], rbx
0x18002ed51  push    rdi
0x18002ed52  sub     rsp, 20h
0x18002ed56  cmp     byte ptr [r9], 0
0x18002ed5a  mov     rbx, rdx
0x18002ed5d  mov     rdi, rcx
0x18002ed60  jnz     short loc_18002ED72
0x18002ed62  test    r8, r8
0x18002ed65  jz      short loc_18002ED72
0x18002ed67  mov     byte ptr [r9], 1
0x18002ed6b  mov     byte ptr [r8+40h], 0
0x18002ed70  jmp     short loc_18002EDAA
0x18002ed72  mov     rcx, cs:?sm_pachTraceConfigListEntries@W3_TRACE_CONFIG_LIST_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_TRACE_CONFIG_LIST_ENTRY::sm_pachTraceConfigListEntries
0x18002ed79  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18002ed7f  mov     r8, rax
0x18002ed82  test    rax, rax
0x18002ed85  jz      short loc_18002EDDB
0x18002ed87  xorps   xmm0, xmm0
0x18002ed8a  movups  xmmword ptr [rax], xmm0
0x18002ed8d  mov     qword ptr [rax+10h], 0
0x18002ed95  xor     eax, eax
0x18002ed97  movups  xmmword ptr [r8+18h], xmm0
0x18002ed9c  mov     [r8+28h], rax
0x18002eda0  movups  xmmword ptr [r8+30h], xmm0
0x18002eda5  mov     byte ptr [r8+40h], 1
0x18002edaa  mov     [r8+10h], rdi
0x18002edae  test    rbx, rbx
0x18002edb1  jz      short loc_18002EDD8
0x18002edb3  mov     rcx, [rbx]
0x18002edb6  lea     rdx, [r8+30h]
0x18002edba  movups  xmm0, xmmword ptr [rcx]
0x18002edbd  movdqu  xmmword ptr [rdx], xmm0
0x18002edc1  movups  xmm0, xmmword ptr [rbx]
0x18002edc4  movups  xmmword ptr [r8+18h], xmm0
0x18002edc9  movsd   xmm1, qword ptr [rbx+10h]
0x18002edce  movsd   qword ptr [r8+28h], xmm1
0x18002edd4  mov     [r8+18h], rdx
0x18002edd8  mov     rax, r8
0x18002eddb  mov     rbx, [rsp+28h+arg_0]
0x18002ede0  add     rsp, 20h
0x18002ede4  pop     rdi
0x18002ede5  retn
```
