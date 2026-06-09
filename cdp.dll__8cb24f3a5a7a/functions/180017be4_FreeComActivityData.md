# FreeComActivityData

- ea: `0x180017be4`
- end: `0x180017cd3`
- name: `FreeComActivityData`
- size: `239`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016fc4`
- `0x180017674`
- `0x1800f6a2c`
- `0x180103e30`
- `0x18014c164`
- `0x18014c560`
- `0x18015b0d0`
- `0x18015cf78`
- `0x18015cfd0`
- `0x18015d478`
- `0x18015d710`
- `0x18015d9e0`
- `0x18015dfd0`
- `0x18015e030`
- `0x18030185c`

## callees

- `0x180017cdc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017ca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017c93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017ca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017cbb`

## pseudocode

```c
void __fastcall FreeComActivityData(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx

  FreeCDPComCrossPlatformAppId(a1 + 40);
  CoTaskMemFree(*(LPVOID *)(a1 + 72));
  v2 = *(void **)(a1 + 80);
  *(_QWORD *)(a1 + 72) = 0;
  CoTaskMemFree(v2);
  v3 = *(void **)(a1 + 88);
  *(_QWORD *)(a1 + 80) = 0;
  CoTaskMemFree(v3);
  v4 = *(void **)(a1 + 120);
  *(_QWORD *)(a1 + 88) = 0;
  CoTaskMemFree(v4);
  v5 = *(void **)(a1 + 128);
  *(_QWORD *)(a1 + 120) = 0;
  CoTaskMemFree(v5);
  v6 = *(void **)(a1 + 136);
  *(_QWORD *)(a1 + 128) = 0;
  CoTaskMemFree(v6);
  v7 = *(void **)(a1 + 144);
  *(_QWORD *)(a1 + 136) = 0;
  CoTaskMemFree(v7);
  v8 = *(void **)(a1 + 56);
  *(_QWORD *)(a1 + 144) = 0;
  CoTaskMemFree(v8);
  v9 = *(void **)(a1 + 64);
  *(_QWORD *)(a1 + 56) = 0;
  CoTaskMemFree(v9);
  v10 = *(void **)(a1 + 200);
  *(_QWORD *)(a1 + 64) = 0;
  CoTaskMemFree(v10);
  v11 = *(void **)(a1 + 208);
  *(_QWORD *)(a1 + 200) = 0;
  CoTaskMemFree(v11);
  v12 = *(void **)(a1 + 224);
  *(_QWORD *)(a1 + 208) = 0;
  CoTaskMemFree(v12);
  *(_QWORD *)(a1 + 224) = 0;
}

```

## disassembly

```asm
0x180017be4  mov     [rsp+arg_0], rbx
0x180017be9  push    rdi
0x180017bea  sub     rsp, 20h
0x180017bee  mov     rbx, rcx
0x180017bf1  add     rcx, 28h ; '('
0x180017bf5  call    FreeCDPComCrossPlatformAppId
0x180017bfa  mov     rcx, [rbx+48h]; pv
0x180017bfe  call    cs:__imp_CoTaskMemFree
0x180017c04  mov     rcx, [rbx+50h]; pv
0x180017c08  xor     edi, edi
0x180017c0a  mov     [rbx+48h], rdi
0x180017c0e  call    cs:__imp_CoTaskMemFree
0x180017c14  mov     rcx, [rbx+58h]; pv
0x180017c18  mov     [rbx+50h], rdi
0x180017c1c  call    cs:__imp_CoTaskMemFree
0x180017c22  mov     rcx, [rbx+78h]; pv
0x180017c26  mov     [rbx+58h], rdi
0x180017c2a  call    cs:__imp_CoTaskMemFree
0x180017c30  mov     rcx, [rbx+80h]; pv
0x180017c37  mov     [rbx+78h], rdi
0x180017c3b  call    cs:__imp_CoTaskMemFree
0x180017c41  mov     rcx, [rbx+88h]; pv
0x180017c48  mov     [rbx+80h], rdi
0x180017c4f  call    cs:__imp_CoTaskMemFree
0x180017c55  mov     rcx, [rbx+90h]; pv
0x180017c5c  mov     [rbx+88h], rdi
0x180017c63  call    cs:__imp_CoTaskMemFree
0x180017c69  mov     rcx, [rbx+38h]; pv
0x180017c6d  mov     [rbx+90h], rdi
0x180017c74  call    cs:__imp_CoTaskMemFree
0x180017c7a  mov     rcx, [rbx+40h]; pv
0x180017c7e  mov     [rbx+38h], rdi
0x180017c82  call    cs:__imp_CoTaskMemFree
0x180017c88  mov     rcx, [rbx+0C8h]; pv
0x180017c8f  mov     [rbx+40h], rdi
0x180017c93  call    cs:__imp_CoTaskMemFree
0x180017c99  mov     rcx, [rbx+0D0h]; pv
0x180017ca0  mov     [rbx+0C8h], rdi
0x180017ca7  call    cs:__imp_CoTaskMemFree
0x180017cad  mov     rcx, [rbx+0E0h]; pv
0x180017cb4  mov     [rbx+0D0h], rdi
0x180017cbb  call    cs:__imp_CoTaskMemFree
0x180017cc1  mov     [rbx+0E0h], rdi
0x180017cc8  mov     rbx, [rsp+28h+arg_0]
0x180017ccd  add     rsp, 20h
0x180017cd1  pop     rdi
0x180017cd2  retn
```
