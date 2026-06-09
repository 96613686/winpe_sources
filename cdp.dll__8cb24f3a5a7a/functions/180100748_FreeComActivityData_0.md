# FreeComActivityData_0

- ea: `0x180100748`
- end: `0x180100837`
- name: `FreeComActivityData_0`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ccee0`

## callees

- `0x180148e28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010078e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010079f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010080b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010081f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100762`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180100780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010078e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010079f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801007f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010080b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010081f`

## pseudocode

```c
void __fastcall FreeComActivityData_0(__int64 a1)
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

  FreeCDPComCrossPlatformAppId_0(a1 + 40);
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
0x180100748  mov     [rsp+arg_0], rbx
0x18010074d  push    rdi
0x18010074e  sub     rsp, 20h
0x180100752  mov     rbx, rcx
0x180100755  add     rcx, 28h ; '('
0x180100759  call    FreeCDPComCrossPlatformAppId_0
0x18010075e  mov     rcx, [rbx+48h]; pv
0x180100762  call    cs:__imp_CoTaskMemFree
0x180100768  mov     rcx, [rbx+50h]; pv
0x18010076c  xor     edi, edi
0x18010076e  mov     [rbx+48h], rdi
0x180100772  call    cs:__imp_CoTaskMemFree
0x180100778  mov     rcx, [rbx+58h]; pv
0x18010077c  mov     [rbx+50h], rdi
0x180100780  call    cs:__imp_CoTaskMemFree
0x180100786  mov     rcx, [rbx+78h]; pv
0x18010078a  mov     [rbx+58h], rdi
0x18010078e  call    cs:__imp_CoTaskMemFree
0x180100794  mov     rcx, [rbx+80h]; pv
0x18010079b  mov     [rbx+78h], rdi
0x18010079f  call    cs:__imp_CoTaskMemFree
0x1801007a5  mov     rcx, [rbx+88h]; pv
0x1801007ac  mov     [rbx+80h], rdi
0x1801007b3  call    cs:__imp_CoTaskMemFree
0x1801007b9  mov     rcx, [rbx+90h]; pv
0x1801007c0  mov     [rbx+88h], rdi
0x1801007c7  call    cs:__imp_CoTaskMemFree
0x1801007cd  mov     rcx, [rbx+38h]; pv
0x1801007d1  mov     [rbx+90h], rdi
0x1801007d8  call    cs:__imp_CoTaskMemFree
0x1801007de  mov     rcx, [rbx+40h]; pv
0x1801007e2  mov     [rbx+38h], rdi
0x1801007e6  call    cs:__imp_CoTaskMemFree
0x1801007ec  mov     rcx, [rbx+0C8h]; pv
0x1801007f3  mov     [rbx+40h], rdi
0x1801007f7  call    cs:__imp_CoTaskMemFree
0x1801007fd  mov     rcx, [rbx+0D0h]; pv
0x180100804  mov     [rbx+0C8h], rdi
0x18010080b  call    cs:__imp_CoTaskMemFree
0x180100811  mov     rcx, [rbx+0E0h]; pv
0x180100818  mov     [rbx+0D0h], rdi
0x18010081f  call    cs:__imp_CoTaskMemFree
0x180100825  mov     [rbx+0E0h], rdi
0x18010082c  mov     rbx, [rsp+28h+arg_0]
0x180100831  add     rsp, 20h
0x180100835  pop     rdi
0x180100836  retn
```
