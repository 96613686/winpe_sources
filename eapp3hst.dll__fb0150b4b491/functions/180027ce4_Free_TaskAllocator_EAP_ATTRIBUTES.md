# Free<TaskAllocator>(_EAP_ATTRIBUTES &)

- ea: `0x180027ce4`
- end: `0x180027d3b`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z`
- size: `87`
- prototype: `void __fastcall(unsigned int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027eb4`
- `0x180027ec0`
- `0x180028a60`
- `0x180028c90`

## callees

- `0x180027ce4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027d1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Free<TaskAllocator>(unsigned int *a1)
{
  unsigned __int64 i; // rsi

  for ( i = 0; i < *a1; CoTaskMemFree(*(LPVOID *)(*((_QWORD *)a1 + 1) + 16 * i++ + 8)) )
    ;
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  *(_OWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180027ce4  mov     [rsp+arg_0], rbx
0x180027ce9  mov     [rsp+arg_8], rsi
0x180027cee  push    rdi
0x180027cef  sub     rsp, 20h
0x180027cf3  xor     esi, esi
0x180027cf5  mov     rdi, rcx
0x180027cf8  cmp     [rcx], esi
0x180027cfa  jbe     short loc_180027D1B
0x180027cfc  mov     rcx, [rdi+8]
0x180027d00  mov     rax, rsi
0x180027d03  add     rax, rax
0x180027d06  mov     rcx, [rcx+rax*8+8]; pv
0x180027d0b  call    cs:__imp_CoTaskMemFree
0x180027d11  mov     eax, [rdi]
0x180027d13  inc     rsi
0x180027d16  cmp     rsi, rax
0x180027d19  jb      short loc_180027CFC
0x180027d1b  mov     rcx, [rdi+8]; pv
0x180027d1f  call    cs:__imp_CoTaskMemFree
0x180027d25  mov     rbx, [rsp+28h+arg_0]
0x180027d2a  xorps   xmm0, xmm0
0x180027d2d  mov     rsi, [rsp+28h+arg_8]
0x180027d32  movups  xmmword ptr [rdi], xmm0
0x180027d35  add     rsp, 20h
0x180027d39  pop     rdi
0x180027d3a  retn
```
