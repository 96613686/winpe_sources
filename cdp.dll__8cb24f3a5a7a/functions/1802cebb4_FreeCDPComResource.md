# FreeCDPComResource

- ea: `0x1802cebb4`
- end: `0x1802cec3c`
- name: `FreeCDPComResource`
- size: `136`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801eb190`
- `0x1802cea88`
- `0x1802d2374`

## callees

- `0x1802cebb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cebc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cebda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cebf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cec0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cec1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cebc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cebda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cebf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cec0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cec1e`

## pseudocode

```c
void __fastcall FreeCDPComResource(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rax
  LPVOID *v4; // rdi
  LPVOID *v5; // rsi
  void *v6; // rcx

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *(unsigned __int16 *)(a1 + 32);
  v4 = *(LPVOID **)(a1 + 24);
  *(_QWORD *)(a1 + 8) = 0;
  v5 = &v4[v3];
  while ( v4 != v5 )
    CoTaskMemFree(*v4++);
  CoTaskMemFree(*(LPVOID *)(a1 + 24));
  v6 = *(void **)(a1 + 16);
  *(_QWORD *)(a1 + 24) = 0;
  CoTaskMemFree(v6);
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x1802cebb4  mov     [rsp+arg_0], rbx
0x1802cebb9  mov     [rsp+arg_8], rsi
0x1802cebbe  push    rdi
0x1802cebbf  sub     rsp, 20h
0x1802cebc3  mov     rbx, rcx
0x1802cebc6  mov     rcx, [rcx]; pv
0x1802cebc9  call    cs:__imp_CoTaskMemFree
0x1802cebcf  mov     rcx, [rbx+8]; pv
0x1802cebd3  mov     qword ptr [rbx], 0
0x1802cebda  call    cs:__imp_CoTaskMemFree
0x1802cebe0  movzx   eax, word ptr [rbx+20h]
0x1802cebe4  mov     rdi, [rbx+18h]
0x1802cebe8  mov     qword ptr [rbx+8], 0
0x1802cebf0  lea     rsi, [rdi+rax*8]
0x1802cebf4  jmp     short loc_1802CEC03
0x1802cebf6  mov     rcx, [rdi]; pv
0x1802cebf9  call    cs:__imp_CoTaskMemFree
0x1802cebff  add     rdi, 8
0x1802cec03  cmp     rdi, rsi
0x1802cec06  jnz     short loc_1802CEBF6
0x1802cec08  mov     rcx, [rbx+18h]; pv
0x1802cec0c  call    cs:__imp_CoTaskMemFree
0x1802cec12  mov     rcx, [rbx+10h]; pv
0x1802cec16  mov     qword ptr [rbx+18h], 0
0x1802cec1e  call    cs:__imp_CoTaskMemFree
0x1802cec24  mov     rsi, [rsp+28h+arg_8]
0x1802cec29  mov     qword ptr [rbx+10h], 0
0x1802cec31  mov     rbx, [rsp+28h+arg_0]
0x1802cec36  add     rsp, 20h
0x1802cec3a  pop     rdi
0x1802cec3b  retn
```
