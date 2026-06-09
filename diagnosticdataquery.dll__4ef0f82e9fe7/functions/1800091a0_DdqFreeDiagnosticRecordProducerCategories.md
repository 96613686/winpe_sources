# DdqFreeDiagnosticRecordProducerCategories

- ea: `0x1800091a0`
- end: `0x1800091f1`
- name: `DdqFreeDiagnosticRecordProducerCategories`
- size: `81`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800018d0`
- `0x1800091a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800091d3`

## pseudocode

```c
__int64 __fastcall DdqFreeDiagnosticRecordProducerCategories(void *a1)
{
  unsigned int v1; // ebp
  unsigned int i; // esi

  v1 = *((_DWORD *)a1 + 4);
  for ( i = 0; i < v1; ++i )
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 1) + 16LL * i + 8));
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x1800091a0  push    rbx
0x1800091a2  push    rbp
0x1800091a3  push    rsi
0x1800091a4  push    rdi
0x1800091a5  sub     rsp, 28h
0x1800091a9  mov     ebp, [rcx+10h]
0x1800091ac  xor     esi, esi
0x1800091ae  mov     rdi, rcx
0x1800091b1  test    ebp, ebp
0x1800091b3  jz      short loc_1800091CF
0x1800091b5  mov     rcx, [rdi+8]
0x1800091b9  mov     eax, esi
0x1800091bb  add     rax, rax
0x1800091be  mov     rcx, [rcx+rax*8+8]; pv
0x1800091c3  call    cs:__imp_CoTaskMemFree
0x1800091c9  inc     esi
0x1800091cb  cmp     esi, ebp
0x1800091cd  jb      short loc_1800091B5
0x1800091cf  mov     rcx, [rdi+8]; pv
0x1800091d3  call    cs:__imp_CoTaskMemFree
0x1800091d9  mov     edx, 4; unsigned __int64
0x1800091de  mov     rcx, rdi; void *
0x1800091e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800091e6  xor     eax, eax
0x1800091e8  add     rsp, 28h
0x1800091ec  pop     rdi
0x1800091ed  pop     rsi
0x1800091ee  pop     rbp
0x1800091ef  pop     rbx
0x1800091f0  retn
```
