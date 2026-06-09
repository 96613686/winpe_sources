# Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)

- ea: `0x18001322c`
- end: `0x1800132d2`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z`
- size: `166`
- prototype: `char __fastcall(_OWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180013d44`

## callees

- `0x18000213c`
- `0x1800131c0`
- `0x18001322c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800132b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( Copy<TaskAllocator>((_QWORD *)a1 + 9, (_QWORD *)(a2 + 72)) && Copy<TaskAllocator>(v4, (_QWORD *)(a2 + 80)) )
    return 1;
  CoTaskMemFree(*v2);
  CoTaskMemFree(*v4);
  memset_0(a1, 0, 0x58u);
  return 0;
}

```

## disassembly

```asm
0x18001322c  push    rbx
0x18001322e  push    rsi
0x18001322f  push    rdi
0x180013230  push    r14
0x180013232  sub     rsp, 28h
0x180013236  movups  xmm0, xmmword ptr [rdx]
0x180013239  lea     r14, [rcx+48h]
0x18001323d  mov     rdi, rdx
0x180013240  lea     rsi, [rcx+50h]
0x180013244  mov     rbx, rcx
0x180013247  movups  xmmword ptr [rcx], xmm0
0x18001324a  movups  xmm1, xmmword ptr [rdx+10h]
0x18001324e  movups  xmmword ptr [rcx+10h], xmm1
0x180013252  movups  xmm0, xmmword ptr [rdx+20h]
0x180013256  movups  xmmword ptr [rcx+20h], xmm0
0x18001325a  movups  xmm1, xmmword ptr [rdx+30h]
0x18001325e  movups  xmmword ptr [rcx+30h], xmm1
0x180013262  movups  xmm0, xmmword ptr [rdx+40h]
0x180013266  movups  xmmword ptr [rcx+40h], xmm0
0x18001326a  movsd   xmm1, qword ptr [rdx+50h]
0x18001326f  add     rdx, 48h ; 'H'
0x180013273  movsd   qword ptr [rcx+50h], xmm1
0x180013278  mov     rcx, r14
0x18001327b  mov     qword ptr [r14], 0
0x180013282  mov     qword ptr [rsi], 0
0x180013289  call    ??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z; Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)
0x18001328e  test    al, al
0x180013290  jz      short loc_1800132A6
0x180013292  lea     rdx, [rdi+50h]
0x180013296  mov     rcx, rsi
0x180013299  call    ??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z; Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)
0x18001329e  test    al, al
0x1800132a0  jz      short loc_1800132A6
0x1800132a2  mov     al, 1
0x1800132a4  jmp     short loc_1800132C8
0x1800132a6  mov     rcx, [r14]; pv
0x1800132a9  call    cs:__imp_CoTaskMemFree
0x1800132af  mov     rcx, [rsi]; pv
0x1800132b2  call    cs:__imp_CoTaskMemFree
0x1800132b8  xor     edx, edx; Val
0x1800132ba  mov     rcx, rbx; void *
0x1800132bd  lea     r8d, [rdx+58h]; Size
0x1800132c1  call    memset_0
0x1800132c6  xor     al, al
0x1800132c8  add     rsp, 28h
0x1800132cc  pop     r14
0x1800132ce  pop     rdi
0x1800132cf  pop     rsi
0x1800132d0  pop     rbx
0x1800132d1  retn
```
