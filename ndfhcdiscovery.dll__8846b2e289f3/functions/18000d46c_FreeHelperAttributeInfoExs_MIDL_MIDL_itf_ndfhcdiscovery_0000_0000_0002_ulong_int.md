# FreeHelperAttributeInfoExs(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,ulong,int)

- ea: `0x18000d46c`
- end: `0x18000d50a`
- name: `?FreeHelperAttributeInfoExs@@YAXPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@KH@Z`
- size: `158`
- prototype: `void __fastcall(struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b90c`
- `0x18000c978`

## callees

- `0x18000d46c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d4f0`

## pseudocode

```c
void __fastcall FreeHelperAttributeInfoExs(LPVOID *pv, unsigned int a2, int a3)
{
  unsigned int v3; // r15d
  __int64 v7; // rbp
  __int64 v8; // rbx
  void *v9; // rcx
  void *v10; // rcx

  v3 = 0;
  if ( a2 )
  {
    v7 = 0;
    do
    {
      v8 = 4 * v7;
      CoTaskMemFree(pv[4 * v7 + 3]);
      v9 = pv[4 * v7 + 2];
      pv[v8 + 3] = 0;
      CoTaskMemFree(v9);
      v10 = pv[4 * v7];
      pv[v8 + 2] = 0;
      CoTaskMemFree(v10);
      ++v3;
      pv[v8] = 0;
      ++v7;
    }
    while ( v3 < a2 );
  }
  if ( a3 )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18000d46c  push    rbx
0x18000d46e  push    rbp
0x18000d46f  push    rsi
0x18000d470  push    rdi
0x18000d471  push    r14
0x18000d473  push    r15
0x18000d475  sub     rsp, 28h
0x18000d479  xor     r15d, r15d
0x18000d47c  mov     r14d, r8d
0x18000d47f  mov     esi, edx
0x18000d481  mov     rdi, rcx
0x18000d484  test    edx, edx
0x18000d486  jz      short loc_18000D4E8
0x18000d488  xor     ebp, ebp
0x18000d48a  mov     rbx, rbp
0x18000d48d  shl     rbx, 5
0x18000d491  mov     rcx, [rbx+rdi+18h]; pv
0x18000d496  call    cs:__imp_CoTaskMemFree
0x18000d49d  nop     dword ptr [rax+rax+00h]
0x18000d4a2  mov     rcx, [rbx+rdi+10h]; pv
0x18000d4a7  mov     qword ptr [rbx+rdi+18h], 0
0x18000d4b0  call    cs:__imp_CoTaskMemFree
0x18000d4b7  nop     dword ptr [rax+rax+00h]
0x18000d4bc  mov     rcx, [rbx+rdi]; pv
0x18000d4c0  mov     qword ptr [rbx+rdi+10h], 0
0x18000d4c9  call    cs:__imp_CoTaskMemFree
0x18000d4d0  nop     dword ptr [rax+rax+00h]
0x18000d4d5  inc     r15d
0x18000d4d8  mov     qword ptr [rbx+rdi], 0
0x18000d4e0  inc     rbp
0x18000d4e3  cmp     r15d, esi
0x18000d4e6  jb      short loc_18000D48A
0x18000d4e8  test    r14d, r14d
0x18000d4eb  jz      short loc_18000D4FC
0x18000d4ed  mov     rcx, rdi; pv
0x18000d4f0  call    cs:__imp_CoTaskMemFree
0x18000d4f7  nop     dword ptr [rax+rax+00h]
0x18000d4fc  add     rsp, 28h
0x18000d500  pop     r15
0x18000d502  pop     r14
0x18000d504  pop     rdi
0x18000d505  pop     rsi
0x18000d506  pop     rbp
0x18000d507  pop     rbx
0x18000d508  retn
```
