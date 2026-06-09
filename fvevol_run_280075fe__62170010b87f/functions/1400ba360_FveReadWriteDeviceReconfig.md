# FveReadWriteDeviceReconfig

- ea: `0x1400ba360`
- end: `0x1400ba6e0`
- name: `FveReadWriteDeviceReconfig`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140026db8`

## callees

- `0x14000fb78`
- `0x14000fc0c`
- `0x140022220`
- `0x1400ba360`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400ba6bf`
- `ntoskrnl!KeReleaseMutex` at `0x1400ba6bf`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ba49b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400ba49b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba4ca`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba696`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba4ca`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400ba696`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ba45a`
- `ntoskrnl!MmSizeOfMdl` at `0x1400ba45a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ba39d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ba39d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba6aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba6aa`

## pseudocode

```c
LONG __fastcall FveReadWriteDeviceReconfig(
        __int64 a1,
        size_t *a2,
        PNPAGED_LOOKASIDE_LIST *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6)
{
  __int64 v6; // r14
  struct _NPAGED_LOOKASIDE_LIST *v11; // r15
  __int64 v12; // rbp
  bool v13; // bl
  __int64 v14; // rax
  __int128 v15; // xmm0
  __int64 v16; // rax
  unsigned int v17; // ecx
  int v18; // eax
  struct _NPAGED_LOOKASIDE_LIST *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8

  v6 = *(_QWORD *)(a1 + 8);
  v11 = 0;
  KeWaitForSingleObject((PVOID)(v6 + 9608), Executive, 0, 0, 0);
  v12 = a1 + 1592;
  v13 = memcmp((const void *)(a1 + 1592), a2, a2[52]) != 0;
  v14 = 3;
  do
  {
    v15 = *(_OWORD *)a2;
    a2 += 16;
    *(_OWORD *)v12 = v15;
    v12 += 128;
    *(_OWORD *)(v12 - 112) = *((_OWORD *)a2 - 7);
    *(_OWORD *)(v12 - 96) = *((_OWORD *)a2 - 6);
    *(_OWORD *)(v12 - 80) = *((_OWORD *)a2 - 5);
    *(_OWORD *)(v12 - 64) = *((_OWORD *)a2 - 4);
    *(_OWORD *)(v12 - 48) = *((_OWORD *)a2 - 3);
    *(_OWORD *)(v12 - 32) = *((_OWORD *)a2 - 2);
    *(_OWORD *)(v12 - 16) = *((_OWORD *)a2 - 1);
    --v14;
  }
  while ( v14 );
  *(_OWORD *)v12 = *(_OWORD *)a2;
  *(_OWORD *)(v12 + 16) = *((_OWORD *)a2 + 1);
  *(_QWORD *)(v12 + 32) = a2[4];
  v16 = *(unsigned int *)(v6 + 884);
  v17 = *(_DWORD *)(a1 + 4 * v16 + 1592);
  if ( v17 == *(_DWORD *)(v6 + 4 * v16 + 936) )
  {
    v21 = *(_QWORD *)(v6 + 9008);
    if ( *(_QWORD *)(a1 + 2016) != v21 )
      v11 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 2016), v21);
    v20 = *(_QWORD *)(v6 + 9016);
  }
  else
  {
    v18 = MmSizeOfMdl(0, v17);
    ExInitializeNPagedLookasideList(
      *a3,
      0,
      0,
      0x200u,
      (unsigned int)(v18 + *(_DWORD *)(a1 + 4LL * *(unsigned int *)(v6 + 884) + 1592) + 64),
      0x70455646u,
      0);
    v19 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 2016), (__int64)*a3);
    *a3 = v19;
    if ( v19 == *(struct _NPAGED_LOOKASIDE_LIST **)(v6 + 9008) )
    {
      *a3 = 0;
    }
    else if ( v19 )
    {
      ExDeleteNPagedLookasideList(v19);
    }
    v20 = 0;
  }
  *(_QWORD *)(a1 + 2024) = v20;
  *a4 = _InterlockedExchange64((volatile __int64 *)(a1 + 2056), *a4);
  *a5 = _InterlockedExchange64((volatile __int64 *)(a1 + 2104), *a5);
  *a6 = _InterlockedExchange64((volatile __int64 *)(a1 + 2112), *a6);
  if ( v13 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v22 = *(unsigned int *)(v6 + 884);
      WPP_SF_qLDDDDDDDDDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        60,
        v22,
        a1,
        *(_DWORD *)(v6 + 884),
        *(_DWORD *)(a1 + 4 * v22 + 1592),
        *(_DWORD *)(a1 + 4 * v22 + 1604),
        *(_DWORD *)(a1 + 4 * v22 + 1616),
        *(_DWORD *)(a1 + 4 * v22 + 1640),
        *(_DWORD *)(a1 + 4 * v22 + 1652),
        *(_DWORD *)(a1 + 4 * v22 + 1676),
        *(_DWORD *)(a1 + 4 * v22 + 1688),
        *(_DWORD *)(a1 + 4 * v22 + 1700),
        *(_DWORD *)(a1 + 4 * v22 + 1712),
        *(_DWORD *)(a1 + 4 * v22 + 1724),
        *(_DWORD *)(a1 + 4 * v22 + 1736),
        *(_DWORD *)(a1 + 4 * v22 + 1748));
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v23 = *(unsigned int *)(v6 + 884);
      WPP_SF_qLDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        61,
        v23,
        a1,
        *(_DWORD *)(v6 + 884),
        *(_DWORD *)(a1 + 4 * v23 + 1760),
        *(_DWORD *)(a1 + 4 * v23 + 1772),
        *(_DWORD *)(v6 + 4 * v23 + 972),
        *(_DWORD *)(v6 + 4 * v23 + 1008));
    }
  }
  if ( v11 && v11 != *(struct _NPAGED_LOOKASIDE_LIST **)(v6 + 9008) )
  {
    ExDeleteNPagedLookasideList(v11);
    ExFreePoolWithTag(v11, 0x30455646u);
  }
  return KeReleaseMutex((PRKMUTEX)(v6 + 9608), 0);
}

```

## disassembly

```asm
0x1400ba360  push    rbx
0x1400ba362  push    rbp
0x1400ba363  push    rsi
0x1400ba364  push    rdi
0x1400ba365  push    r12
0x1400ba367  push    r13
0x1400ba369  push    r14
0x1400ba36b  push    r15
0x1400ba36d  sub     rsp, 98h
0x1400ba374  mov     r14, [rcx+8]
0x1400ba378  mov     r13, r9
0x1400ba37b  mov     r12, r8
0x1400ba37e  mov     rsi, rdx
0x1400ba381  mov     rdi, rcx
0x1400ba384  xor     r15d, r15d
0x1400ba387  xor     r9d, r9d; Alertable
0x1400ba38a  mov     [rsp+0D8h+Timeout], r15; Timeout
0x1400ba38f  lea     rcx, [r14+2588h]; Object
0x1400ba396  xor     r8d, r8d; WaitMode
0x1400ba399  xor     edx, edx; WaitReason
0x1400ba39b  xor     bl, bl
0x1400ba39d  call    cs:__imp_KeWaitForSingleObject
0x1400ba3a4  nop     dword ptr [rax+rax+00h]
0x1400ba3a9  mov     r8, [rsi+1A0h]; Size
0x1400ba3b0  lea     rbp, [rdi+638h]
0x1400ba3b7  mov     rcx, rbp; Buf1
0x1400ba3ba  mov     rdx, rsi; Buf2
0x1400ba3bd  call    memcmp
0x1400ba3c2  test    eax, eax
0x1400ba3c4  movzx   ebx, bl
0x1400ba3c7  lea     ecx, [r15+1]
0x1400ba3cb  cmovnz  ebx, ecx
0x1400ba3ce  lea     eax, [rcx+2]
0x1400ba3d1  movups  xmm0, xmmword ptr [rsi]
0x1400ba3d4  lea     rsi, [rsi+80h]
0x1400ba3db  movups  xmmword ptr [rbp+0], xmm0
0x1400ba3df  lea     rbp, [rbp+80h]
0x1400ba3e6  movups  xmm1, xmmword ptr [rsi-70h]
0x1400ba3ea  movups  xmmword ptr [rbp-70h], xmm1
0x1400ba3ee  movups  xmm0, xmmword ptr [rsi-60h]
0x1400ba3f2  movups  xmmword ptr [rbp-60h], xmm0
0x1400ba3f6  movups  xmm1, xmmword ptr [rsi-50h]
0x1400ba3fa  movups  xmmword ptr [rbp-50h], xmm1
0x1400ba3fe  movups  xmm0, xmmword ptr [rsi-40h]
0x1400ba402  movups  xmmword ptr [rbp-40h], xmm0
0x1400ba406  movups  xmm1, xmmword ptr [rsi-30h]
0x1400ba40a  movups  xmmword ptr [rbp-30h], xmm1
0x1400ba40e  movups  xmm0, xmmword ptr [rsi-20h]
0x1400ba412  movups  xmmword ptr [rbp-20h], xmm0
0x1400ba416  movups  xmm1, xmmword ptr [rsi-10h]
0x1400ba41a  movups  xmmword ptr [rbp-10h], xmm1
0x1400ba41e  sub     rax, rcx
0x1400ba421  jnz     short loc_1400BA3D1
0x1400ba423  movups  xmm0, xmmword ptr [rsi]
0x1400ba426  movups  xmmword ptr [rbp+0], xmm0
0x1400ba42a  movups  xmm1, xmmword ptr [rsi+10h]
0x1400ba42e  movups  xmmword ptr [rbp+10h], xmm1
0x1400ba432  mov     rax, [rsi+20h]
0x1400ba436  mov     [rbp+20h], rax
0x1400ba43a  mov     eax, [r14+374h]
0x1400ba441  mov     ecx, [rdi+rax*4+638h]
0x1400ba448  cmp     ecx, [r14+rax*4+3A8h]
0x1400ba450  jz      loc_1400BA4DA
0x1400ba456  mov     edx, ecx; Length
0x1400ba458  xor     ecx, ecx; Base
0x1400ba45a  call    cs:__imp_MmSizeOfMdl
0x1400ba461  nop     dword ptr [rax+rax+00h]
0x1400ba466  mov     ecx, [r14+374h]
0x1400ba46d  xor     r8d, r8d; Free
0x1400ba470  mov     [rsp+0D8h+Depth], r8w; Depth
0x1400ba476  mov     r9d, 200h; Flags
0x1400ba47c  mov     [rsp+0D8h+Tag], 70455646h; Tag
0x1400ba484  xor     edx, edx; Allocate
0x1400ba486  mov     ecx, [rdi+rcx*4+638h]
0x1400ba48d  add     ecx, 40h ; '@'
0x1400ba490  add     ecx, eax
0x1400ba492  mov     [rsp+0D8h+Timeout], rcx; Size
0x1400ba497  mov     rcx, [r12]; Lookaside
0x1400ba49b  call    cs:__imp_ExInitializeNPagedLookasideList
0x1400ba4a2  nop     dword ptr [rax+rax+00h]
0x1400ba4a7  mov     rcx, [r12]
0x1400ba4ab  xchg    rcx, [rdi+7E0h]; Lookaside
0x1400ba4b2  mov     [r12], rcx
0x1400ba4b6  cmp     rcx, [r14+2330h]
0x1400ba4bd  jnz     short loc_1400BA4C5
0x1400ba4bf  mov     [r12], r15
0x1400ba4c3  jmp     short loc_1400BA4D6
0x1400ba4c5  test    rcx, rcx
0x1400ba4c8  jz      short loc_1400BA4D6
0x1400ba4ca  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ba4d1  nop     dword ptr [rax+rax+00h]
0x1400ba4d6  xor     eax, eax
0x1400ba4d8  jmp     short loc_1400BA4FB
0x1400ba4da  mov     rax, [r14+2330h]
0x1400ba4e1  cmp     [rdi+7E0h], rax
0x1400ba4e8  jz      short loc_1400BA4F4
0x1400ba4ea  mov     r15, rax
0x1400ba4ed  xchg    r15, [rdi+7E0h]
0x1400ba4f4  mov     rax, [r14+2338h]
0x1400ba4fb  mov     rcx, [rsp+0D8h+arg_20]
0x1400ba503  mov     [rdi+7E8h], rax
0x1400ba50a  mov     rax, [r13+0]
0x1400ba50e  xchg    rax, [rdi+808h]
0x1400ba515  mov     [r13+0], rax
0x1400ba519  mov     rax, [rcx]
0x1400ba51c  xchg    rax, [rdi+838h]
0x1400ba523  mov     [rcx], rax
0x1400ba526  mov     rcx, [rsp+0D8h+arg_28]
0x1400ba52e  mov     rax, [rcx]
0x1400ba531  xchg    rax, [rdi+840h]
0x1400ba538  mov     [rcx], rax
0x1400ba53b  test    bl, bl
0x1400ba53d  jz      loc_1400BA685
0x1400ba543  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba54a  lea     rbx, WPP_GLOBAL_Control
0x1400ba551  cmp     rcx, rbx
0x1400ba554  jz      loc_1400BA685
0x1400ba55a  mov     eax, [rcx+2Ch]
0x1400ba55d  test    al, al
0x1400ba55f  jns     loc_1400BA61F
0x1400ba565  cmp     byte ptr [rcx+29h], 4
0x1400ba569  jb      loc_1400BA61F
0x1400ba56f  mov     r8d, [r14+374h]
0x1400ba576  mov     edx, 3Ch ; '<'
0x1400ba57b  mov     rcx, [rcx+18h]
0x1400ba57f  mov     r9, rdi
0x1400ba582  mov     eax, [rdi+r8*4+6D4h]
0x1400ba58a  mov     [rsp+0D8h+var_58], eax
0x1400ba591  mov     eax, [rdi+r8*4+6C8h]
0x1400ba599  mov     [rsp+0D8h+var_60], eax
0x1400ba59d  mov     eax, [rdi+r8*4+6BCh]
0x1400ba5a5  mov     [rsp+0D8h+var_68], eax
0x1400ba5a9  mov     eax, [rdi+r8*4+6B0h]
0x1400ba5b1  mov     [rsp+0D8h+var_70], eax
0x1400ba5b5  mov     eax, [rdi+r8*4+6A4h]
0x1400ba5bd  mov     [rsp+0D8h+var_78], eax
0x1400ba5c1  mov     eax, [rdi+r8*4+698h]
0x1400ba5c9  mov     [rsp+0D8h+var_80], eax
0x1400ba5cd  mov     eax, [rdi+r8*4+68Ch]
0x1400ba5d5  mov     [rsp+0D8h+var_88], eax
0x1400ba5d9  mov     eax, [rdi+r8*4+674h]
0x1400ba5e1  mov     [rsp+0D8h+var_90], eax
0x1400ba5e5  mov     eax, [rdi+r8*4+668h]
0x1400ba5ed  mov     [rsp+0D8h+var_98], eax
0x1400ba5f1  mov     eax, [rdi+r8*4+650h]
0x1400ba5f9  mov     [rsp+0D8h+var_A0], eax
0x1400ba5fd  mov     eax, [rdi+r8*4+644h]
0x1400ba605  mov     dword ptr [rsp+0D8h+Depth], eax
0x1400ba609  mov     eax, [rdi+r8*4+638h]
0x1400ba611  mov     [rsp+0D8h+Tag], eax
0x1400ba615  mov     dword ptr [rsp+0D8h+Timeout], r8d
0x1400ba61a  call    WPP_SF_qLDDDDDDDDDDDD
0x1400ba61f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ba626  cmp     rcx, rbx
0x1400ba629  jz      short loc_1400BA685
0x1400ba62b  mov     eax, [rcx+2Ch]
0x1400ba62e  test    al, al
0x1400ba630  jns     short loc_1400BA685
0x1400ba632  cmp     byte ptr [rcx+29h], 4
0x1400ba636  jb      short loc_1400BA685
0x1400ba638  mov     r8d, [r14+374h]
0x1400ba63f  mov     edx, 3Dh ; '='
0x1400ba644  mov     rcx, [rcx+18h]
0x1400ba648  mov     r9, rdi
0x1400ba64b  mov     eax, [r14+r8*4+3F0h]
0x1400ba653  mov     [rsp+0D8h+var_98], eax
0x1400ba657  mov     eax, [r14+r8*4+3CCh]
0x1400ba65f  mov     [rsp+0D8h+var_A0], eax
0x1400ba663  mov     eax, [rdi+r8*4+6ECh]
0x1400ba66b  mov     dword ptr [rsp+0D8h+Depth], eax
0x1400ba66f  mov     eax, [rdi+r8*4+6E0h]
0x1400ba677  mov     [rsp+0D8h+Tag], eax
0x1400ba67b  mov     dword ptr [rsp+0D8h+Timeout], r8d
0x1400ba680  call    WPP_SF_qLDDDD
0x1400ba685  test    r15, r15
0x1400ba688  jz      short loc_1400BA6B6
0x1400ba68a  cmp     r15, [r14+2330h]
0x1400ba691  jz      short loc_1400BA6B6
0x1400ba693  mov     rcx, r15; Lookaside
0x1400ba696  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400ba69d  nop     dword ptr [rax+rax+00h]
0x1400ba6a2  mov     edx, 30455646h; Tag
0x1400ba6a7  mov     rcx, r15; P
0x1400ba6aa  call    cs:__imp_ExFreePoolWithTag
0x1400ba6b1  nop     dword ptr [rax+rax+00h]
0x1400ba6b6  xor     edx, edx; Wait
0x1400ba6b8  lea     rcx, [r14+2588h]; Mutex
0x1400ba6bf  call    cs:__imp_KeReleaseMutex
0x1400ba6c6  nop     dword ptr [rax+rax+00h]
0x1400ba6cb  add     rsp, 98h
0x1400ba6d2  pop     r15
0x1400ba6d4  pop     r14
0x1400ba6d6  pop     r13
0x1400ba6d8  pop     r12
0x1400ba6da  pop     rdi
0x1400ba6db  pop     rsi
0x1400ba6dc  pop     rbp
0x1400ba6dd  pop     rbx
0x1400ba6de  retn
```
