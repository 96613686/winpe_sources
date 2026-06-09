# FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)

- ea: `0x18000d5d8`
- end: `0x18000d65e`
- name: `?FreeHelperBasicRootCauseInfos@@YAXPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@KH@Z`
- size: `134`
- prototype: `void __fastcall(struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *pv, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bb4c`
- `0x18000c9d0`

## callees

- `0x18000d5d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d61c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d61c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d644`

## pseudocode

```c
void __fastcall FreeHelperBasicRootCauseInfos(LPVOID *pv, unsigned int a2, int a3)
{
  unsigned int v3; // r15d
  __int64 v7; // rsi
  __int64 v8; // rbx
  void *v9; // rcx

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
      ++v3;
      pv[v8 + 2] = 0;
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
0x18000d5d8  push    rbx
0x18000d5da  push    rbp
0x18000d5db  push    rsi
0x18000d5dc  push    rdi
0x18000d5dd  push    r14
0x18000d5df  push    r15
0x18000d5e1  sub     rsp, 28h
0x18000d5e5  xor     r15d, r15d
0x18000d5e8  mov     r14d, r8d
0x18000d5eb  mov     ebp, edx
0x18000d5ed  mov     rdi, rcx
0x18000d5f0  test    edx, edx
0x18000d5f2  jz      short loc_18000D63C
0x18000d5f4  xor     esi, esi
0x18000d5f6  mov     rbx, rsi
0x18000d5f9  shl     rbx, 5
0x18000d5fd  mov     rcx, [rbx+rdi+18h]; pv
0x18000d602  call    cs:__imp_CoTaskMemFree
0x18000d609  nop     dword ptr [rax+rax+00h]
0x18000d60e  mov     rcx, [rbx+rdi+10h]; pv
0x18000d613  mov     qword ptr [rbx+rdi+18h], 0
0x18000d61c  call    cs:__imp_CoTaskMemFree
0x18000d623  nop     dword ptr [rax+rax+00h]
0x18000d628  inc     r15d
0x18000d62b  mov     qword ptr [rbx+rdi+10h], 0
0x18000d634  inc     rsi
0x18000d637  cmp     r15d, ebp
0x18000d63a  jb      short loc_18000D5F6
0x18000d63c  test    r14d, r14d
0x18000d63f  jz      short loc_18000D650
0x18000d641  mov     rcx, rdi; pv
0x18000d644  call    cs:__imp_CoTaskMemFree
0x18000d64b  nop     dword ptr [rax+rax+00h]
0x18000d650  add     rsp, 28h
0x18000d654  pop     r15
0x18000d656  pop     r14
0x18000d658  pop     rdi
0x18000d659  pop     rsi
0x18000d65a  pop     rbp
0x18000d65b  pop     rbx
0x18000d65c  retn
```
