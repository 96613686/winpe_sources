# DpspFreeSpecificInstanceSID

- ea: `0x1800060a0`
- end: `0x180006181`
- name: `DpspFreeSpecificInstanceSID`
- size: `225`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180002510`
- `0x180005ec0`
- `0x18000c21c`

## callees

- `0x1800060a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006122`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000615b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006122`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000615b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000614d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000614d`

## pseudocode

```c
void __fastcall DpspFreeSpecificInstanceSID(_QWORD *a1)
{
  PSID v1; // rdi
  PSID v2; // rbp
  HANDLE ProcessHeap; // rax
  PSID v5; // rsi
  HANDLE v6; // rax
  PSID v7; // rdi
  HANDLE v8; // rax

  v1 = (PSID)a1[96];
  v2 = (PSID)a1[97];
  if ( v1 && v1 != g_pAdminSid && v1 != g_pEveryoneSid )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    a1[96] = 0;
  }
  v5 = (PSID)a1[97];
  if ( v5 && v5 != g_pAdminSid && v5 != g_pEveryoneSid && v1 != v2 )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
    a1[97] = 0;
  }
  v7 = (PSID)a1[95];
  if ( v7 && v7 != g_pAdminSid && v7 != g_pEveryoneSid )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
  }
  a1[96] = 0;
  a1[97] = 0;
  a1[95] = 0;
}

```

## disassembly

```asm
0x1800060a0  push    rbx
0x1800060a2  push    rbp
0x1800060a3  push    rsi
0x1800060a4  push    rdi
0x1800060a5  push    r14
0x1800060a7  sub     rsp, 20h
0x1800060ab  mov     rdi, [rcx+300h]
0x1800060b2  xor     r14d, r14d
0x1800060b5  mov     rbp, [rcx+308h]
0x1800060bc  mov     rbx, rcx
0x1800060bf  test    rdi, rdi
0x1800060c2  jz      short loc_1800060F1
0x1800060c4  cmp     rdi, cs:g_pAdminSid
0x1800060cb  jz      short loc_1800060F1
0x1800060cd  cmp     rdi, cs:g_pEveryoneSid
0x1800060d4  jz      short loc_1800060F1
0x1800060d6  call    cs:__imp_GetProcessHeap
0x1800060dc  mov     r8, rdi; lpMem
0x1800060df  xor     edx, edx; dwFlags
0x1800060e1  mov     rcx, rax; hHeap
0x1800060e4  call    cs:__imp_HeapFree
0x1800060ea  mov     [rbx+300h], r14
0x1800060f1  mov     rsi, [rbx+308h]
0x1800060f8  test    rsi, rsi
0x1800060fb  jz      short loc_18000612F
0x1800060fd  cmp     rsi, cs:g_pAdminSid
0x180006104  jz      short loc_18000612F
0x180006106  cmp     rsi, cs:g_pEveryoneSid
0x18000610d  jz      short loc_18000612F
0x18000610f  cmp     rdi, rbp
0x180006112  jz      short loc_18000612F
0x180006114  call    cs:__imp_GetProcessHeap
0x18000611a  mov     r8, rsi; lpMem
0x18000611d  xor     edx, edx; dwFlags
0x18000611f  mov     rcx, rax; hHeap
0x180006122  call    cs:__imp_HeapFree
0x180006128  mov     [rbx+308h], r14
0x18000612f  mov     rdi, [rbx+2F8h]
0x180006136  test    rdi, rdi
0x180006139  jz      short loc_180006161
0x18000613b  cmp     rdi, cs:g_pAdminSid
0x180006142  jz      short loc_180006161
0x180006144  cmp     rdi, cs:g_pEveryoneSid
0x18000614b  jz      short loc_180006161
0x18000614d  call    cs:__imp_GetProcessHeap
0x180006153  mov     r8, rdi; lpMem
0x180006156  xor     edx, edx; dwFlags
0x180006158  mov     rcx, rax; hHeap
0x18000615b  call    cs:__imp_HeapFree
0x180006161  mov     [rbx+300h], r14
0x180006168  mov     [rbx+308h], r14
0x18000616f  mov     [rbx+2F8h], r14
0x180006176  add     rsp, 20h
0x18000617a  pop     r14
0x18000617c  pop     rdi
0x18000617d  pop     rsi
0x18000617e  pop     rbp
0x18000617f  pop     rbx
0x180006180  retn
```
