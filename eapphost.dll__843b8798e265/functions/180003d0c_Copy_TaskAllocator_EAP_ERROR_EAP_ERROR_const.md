# Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)

- ea: `0x180003d0c`
- end: `0x180003dbf`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z`
- size: `179`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003ea0`
- `0x18001f9c4`

## callees

- `0x1800034cc`
- `0x180003a84`
- `0x180003d0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003d98`

## pseudocode

```c
char __fastcall Copy<TaskAllocator>(_OWORD *a1, __int64 a2)
{
  LPVOID *v2; // r14
  LPVOID *v4; // rsi

  v2 = (LPVOID *)a1 + 9;
  v4 = (LPVOID *)(a1 + 5);
  *a1 = *(_OWORD *)a2;
  a1[1] = *(_OWORD *)(a2 + 16);
  a1[2] = *(_OWORD *)(a2 + 32);
  a1[3] = *(_OWORD *)(a2 + 48);
  a1[4] = *(_OWORD *)(a2 + 64);
  *((_QWORD *)a1 + 10) = *(_QWORD *)(a2 + 80);
  *((_QWORD *)a1 + 9) = 0;
  *((_QWORD *)a1 + 10) = 0;
  if ( (unsigned __int8)Copy<TaskAllocator>((char *)a1 + 72, a2 + 72)
    && (unsigned __int8)Copy<TaskAllocator>(v4, a2 + 80) )
  {
    return 1;
  }
  CoTaskMemFree(*v2);
  CoTaskMemFree(*v4);
  memset_0(a1, 0, 0x58u);
  return 0;
}

```

## disassembly

```asm
0x180003d0c  push    rbx
0x180003d0e  push    rsi
0x180003d0f  push    rdi
0x180003d10  push    r14
0x180003d12  sub     rsp, 28h
0x180003d16  movups  xmm0, xmmword ptr [rdx]
0x180003d19  lea     r14, [rcx+48h]
0x180003d1d  mov     rdi, rdx
0x180003d20  lea     rsi, [rcx+50h]
0x180003d24  mov     rbx, rcx
0x180003d27  movups  xmmword ptr [rcx], xmm0
0x180003d2a  movups  xmm1, xmmword ptr [rdx+10h]
0x180003d2e  movups  xmmword ptr [rcx+10h], xmm1
0x180003d32  movups  xmm0, xmmword ptr [rdx+20h]
0x180003d36  movups  xmmword ptr [rcx+20h], xmm0
0x180003d3a  movups  xmm1, xmmword ptr [rdx+30h]
0x180003d3e  movups  xmmword ptr [rcx+30h], xmm1
0x180003d42  movups  xmm0, xmmword ptr [rdx+40h]
0x180003d46  movups  xmmword ptr [rcx+40h], xmm0
0x180003d4a  movsd   xmm1, qword ptr [rdx+50h]
0x180003d4f  add     rdx, 48h ; 'H'
0x180003d53  movsd   qword ptr [rcx+50h], xmm1
0x180003d58  mov     rcx, r14
0x180003d5b  mov     qword ptr [r14], 0
0x180003d62  mov     qword ptr [rsi], 0
0x180003d69  call    ??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z; Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)
0x180003d6e  test    al, al
0x180003d70  jz      short loc_180003D86
0x180003d72  lea     rdx, [rdi+50h]
0x180003d76  mov     rcx, rsi
0x180003d79  call    ??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z; Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)
0x180003d7e  test    al, al
0x180003d80  jz      short loc_180003D86
0x180003d82  mov     al, 1
0x180003d84  jmp     short loc_180003DB4
0x180003d86  mov     rcx, [r14]; pv
0x180003d89  call    cs:__imp_CoTaskMemFree
0x180003d90  nop     dword ptr [rax+rax+00h]
0x180003d95  mov     rcx, [rsi]; pv
0x180003d98  call    cs:__imp_CoTaskMemFree
0x180003d9f  nop     dword ptr [rax+rax+00h]
0x180003da4  xor     edx, edx; Val
0x180003da6  mov     rcx, rbx; void *
0x180003da9  lea     r8d, [rdx+58h]; Size
0x180003dad  call    memset_0
0x180003db2  xor     al, al
0x180003db4  add     rsp, 28h
0x180003db8  pop     r14
0x180003dba  pop     rdi
0x180003dbb  pop     rsi
0x180003dbc  pop     rbx
0x180003dbd  retn
```
