# FreeCDPComDeviceInfo

- ea: `0x1802cea88`
- end: `0x1802cebae`
- name: `FreeCDPComDeviceInfo`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180114cf4`
- `0x18012b3fc`

## callees

- `0x180104d30`
- `0x1802cea88`
- `0x1802cebb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cea9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceaae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cead2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cea9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceaae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceac0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802cead2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceae4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802ceb90`

## pseudocode

```c
void __fastcall FreeCDPComDeviceInfo(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rsi
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(void **)(a1 + 8);
  *(_QWORD *)a1 = 0;
  CoTaskMemFree(v2);
  v3 = *(void **)(a1 + 40);
  *(_QWORD *)(a1 + 8) = 0;
  CoTaskMemFree(v3);
  v4 = *(void **)(a1 + 64);
  *(_QWORD *)(a1 + 40) = 0;
  CoTaskMemFree(v4);
  v5 = *(void **)(a1 + 72);
  *(_QWORD *)(a1 + 64) = 0;
  CoTaskMemFree(v5);
  v6 = *(unsigned __int16 *)(a1 + 24);
  v7 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 72) = 0;
  v8 = v7 + 40 * v6;
  while ( v7 != v8 )
  {
    FreeCDPComEndpoint(v7);
    v7 += 40;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 16));
  v9 = *(_QWORD *)(a1 + 88);
  *(_WORD *)(a1 + 24) = 0;
  v10 = *(unsigned __int16 *)(a1 + 96);
  *(_QWORD *)(a1 + 16) = 0;
  v11 = v9 + 40 * v10;
  while ( v9 != v11 )
  {
    FreeCDPComResource(v9);
    v9 += 40;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 88));
  v12 = *(void **)(a1 + 104);
  *(_WORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  CoTaskMemFree(v12);
  v13 = *(void **)(a1 + 80);
  *(_QWORD *)(a1 + 104) = 0;
  CoTaskMemFree(v13);
  v14 = *(void **)(a1 + 112);
  *(_QWORD *)(a1 + 80) = 0;
  CoTaskMemFree(v14);
  *(_QWORD *)(a1 + 112) = 0;
}

```

## disassembly

```asm
0x1802cea88  mov     [rsp+arg_0], rbx
0x1802cea8d  mov     [rsp+arg_8], rsi
0x1802cea92  push    rdi
0x1802cea93  sub     rsp, 20h
0x1802cea97  mov     rbx, rcx
0x1802cea9a  mov     rcx, [rcx]; pv
0x1802cea9d  call    cs:__imp_CoTaskMemFree
0x1802ceaa3  mov     rcx, [rbx+8]; pv
0x1802ceaa7  mov     qword ptr [rbx], 0
0x1802ceaae  call    cs:__imp_CoTaskMemFree
0x1802ceab4  mov     rcx, [rbx+28h]; pv
0x1802ceab8  mov     qword ptr [rbx+8], 0
0x1802ceac0  call    cs:__imp_CoTaskMemFree
0x1802ceac6  mov     rcx, [rbx+40h]; pv
0x1802ceaca  mov     qword ptr [rbx+28h], 0
0x1802cead2  call    cs:__imp_CoTaskMemFree
0x1802cead8  mov     rcx, [rbx+48h]; pv
0x1802ceadc  mov     qword ptr [rbx+40h], 0
0x1802ceae4  call    cs:__imp_CoTaskMemFree
0x1802ceaea  movzx   eax, word ptr [rbx+18h]
0x1802ceaee  mov     rdi, [rbx+10h]
0x1802ceaf2  mov     qword ptr [rbx+48h], 0
0x1802ceafa  lea     rcx, [rax+rax*4]
0x1802ceafe  lea     rsi, [rdi+rcx*8]
0x1802ceb02  jmp     short loc_1802CEB10
0x1802ceb04  mov     rcx, rdi
0x1802ceb07  call    FreeCDPComEndpoint
0x1802ceb0c  add     rdi, 28h ; '('
0x1802ceb10  cmp     rdi, rsi
0x1802ceb13  jnz     short loc_1802CEB04
0x1802ceb15  mov     rcx, [rbx+10h]; pv
0x1802ceb19  call    cs:__imp_CoTaskMemFree
0x1802ceb1f  mov     rdi, [rbx+58h]
0x1802ceb23  xor     eax, eax
0x1802ceb25  mov     [rbx+18h], ax
0x1802ceb29  movzx   eax, word ptr [rbx+60h]
0x1802ceb2d  mov     qword ptr [rbx+10h], 0
0x1802ceb35  lea     rcx, [rax+rax*4]
0x1802ceb39  lea     rsi, [rdi+rcx*8]
0x1802ceb3d  jmp     short loc_1802CEB4B
0x1802ceb3f  mov     rcx, rdi
0x1802ceb42  call    FreeCDPComResource
0x1802ceb47  add     rdi, 28h ; '('
0x1802ceb4b  cmp     rdi, rsi
0x1802ceb4e  jnz     short loc_1802CEB3F
0x1802ceb50  mov     rcx, [rbx+58h]; pv
0x1802ceb54  call    cs:__imp_CoTaskMemFree
0x1802ceb5a  mov     rcx, [rbx+68h]; pv
0x1802ceb5e  xor     eax, eax
0x1802ceb60  mov     [rbx+60h], ax
0x1802ceb64  mov     qword ptr [rbx+58h], 0
0x1802ceb6c  call    cs:__imp_CoTaskMemFree
0x1802ceb72  mov     rcx, [rbx+50h]; pv
0x1802ceb76  mov     qword ptr [rbx+68h], 0
0x1802ceb7e  call    cs:__imp_CoTaskMemFree
0x1802ceb84  mov     rcx, [rbx+70h]; pv
0x1802ceb88  mov     qword ptr [rbx+50h], 0
0x1802ceb90  call    cs:__imp_CoTaskMemFree
0x1802ceb96  mov     rsi, [rsp+28h+arg_8]
0x1802ceb9b  mov     qword ptr [rbx+70h], 0
0x1802ceba3  mov     rbx, [rsp+28h+arg_0]
0x1802ceba8  add     rsp, 20h
0x1802cebac  pop     rdi
0x1802cebad  retn
```
