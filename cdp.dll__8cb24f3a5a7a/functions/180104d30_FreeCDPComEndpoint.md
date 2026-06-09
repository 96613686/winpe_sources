# FreeCDPComEndpoint

- ea: `0x180104d30`
- end: `0x180104db0`
- name: `FreeCDPComEndpoint`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18012b3fc`
- `0x1802ce7d0`
- `0x1802cea88`

## callees

- `0x180104d30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180104d92`

## pseudocode

```c
void __fastcall FreeCDPComEndpoint(__int64 a1)
{
  void *v2; // rcx
  LPVOID *v3; // rbx
  LPVOID *v4; // rsi

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *(LPVOID **)(a1 + 24);
  v4 = &v3[2 * *(unsigned __int16 *)(a1 + 32)];
  *(_QWORD *)(a1 + 8) = 0;
  while ( v3 != v4 )
  {
    CoTaskMemFree(*v3);
    *v3 = 0;
    v3 += 2;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 24));
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x180104d30  mov     [rsp+arg_0], rbx
0x180104d35  mov     [rsp+arg_8], rsi
0x180104d3a  push    rdi
0x180104d3b  sub     rsp, 20h
0x180104d3f  mov     rdi, rcx
0x180104d42  mov     rcx, [rcx]; pv
0x180104d45  call    cs:__imp_CoTaskMemFree
0x180104d4b  mov     rcx, [rdi+8]; pv
0x180104d4f  mov     qword ptr [rdi], 0
0x180104d56  call    cs:__imp_CoTaskMemFree
0x180104d5c  movzx   esi, word ptr [rdi+20h]
0x180104d60  mov     rbx, [rdi+18h]
0x180104d64  shl     rsi, 4
0x180104d68  add     rsi, rbx
0x180104d6b  mov     qword ptr [rdi+8], 0
0x180104d73  jmp     short loc_180104D89
0x180104d75  mov     rcx, [rbx]; pv
0x180104d78  call    cs:__imp_CoTaskMemFree
0x180104d7e  mov     qword ptr [rbx], 0
0x180104d85  add     rbx, 10h
0x180104d89  cmp     rbx, rsi
0x180104d8c  jnz     short loc_180104D75
0x180104d8e  mov     rcx, [rdi+18h]; pv
0x180104d92  call    cs:__imp_CoTaskMemFree
0x180104d98  mov     rbx, [rsp+28h+arg_0]
0x180104d9d  mov     rsi, [rsp+28h+arg_8]
0x180104da2  mov     qword ptr [rdi+18h], 0
0x180104daa  add     rsp, 20h
0x180104dae  pop     rdi
0x180104daf  retn
```
