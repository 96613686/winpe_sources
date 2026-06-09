# Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)

- ea: `0x180003c40`
- end: `0x180003ce6`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z`
- size: `166`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003dbc`
- `0x18001ee94`

## callees

- `0x18000343c`
- `0x1800039e0`
- `0x180003c40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003cc6`

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
0x180003c40  push    rbx
0x180003c42  push    rsi
0x180003c43  push    rdi
0x180003c44  push    r14
0x180003c46  sub     rsp, 28h
0x180003c4a  movups  xmm0, xmmword ptr [rdx]
0x180003c4d  lea     r14, [rcx+48h]
0x180003c51  mov     rdi, rdx
0x180003c54  lea     rsi, [rcx+50h]
0x180003c58  mov     rbx, rcx
0x180003c5b  movups  xmmword ptr [rcx], xmm0
0x180003c5e  movups  xmm1, xmmword ptr [rdx+10h]
0x180003c62  movups  xmmword ptr [rcx+10h], xmm1
0x180003c66  movups  xmm0, xmmword ptr [rdx+20h]
0x180003c6a  movups  xmmword ptr [rcx+20h], xmm0
0x180003c6e  movups  xmm1, xmmword ptr [rdx+30h]
0x180003c72  movups  xmmword ptr [rcx+30h], xmm1
0x180003c76  movups  xmm0, xmmword ptr [rdx+40h]
0x180003c7a  movups  xmmword ptr [rcx+40h], xmm0
0x180003c7e  movsd   xmm1, qword ptr [rdx+50h]
0x180003c83  add     rdx, 48h ; 'H'
0x180003c87  movsd   qword ptr [rcx+50h], xmm1
0x180003c8c  mov     rcx, r14
0x180003c8f  mov     qword ptr [r14], 0
0x180003c96  mov     qword ptr [rsi], 0
0x180003c9d  call    ??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z; Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)
0x180003ca2  test    al, al
0x180003ca4  jz      short loc_180003CBA
0x180003ca6  lea     rdx, [rdi+50h]
0x180003caa  mov     rcx, rsi
0x180003cad  call    ??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z; Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)
0x180003cb2  test    al, al
0x180003cb4  jz      short loc_180003CBA
0x180003cb6  mov     al, 1
0x180003cb8  jmp     short loc_180003CDC
0x180003cba  mov     rcx, [r14]; pv
0x180003cbd  call    cs:__imp_CoTaskMemFree
0x180003cc3  mov     rcx, [rsi]; pv
0x180003cc6  call    cs:__imp_CoTaskMemFree
0x180003ccc  xor     edx, edx; Val
0x180003cce  mov     rcx, rbx; void *
0x180003cd1  lea     r8d, [rdx+58h]; Size
0x180003cd5  call    memset_0
0x180003cda  xor     al, al
0x180003cdc  add     rsp, 28h
0x180003ce0  pop     r14
0x180003ce2  pop     rdi
0x180003ce3  pop     rsi
0x180003ce4  pop     rbx
0x180003ce5  retn
```
