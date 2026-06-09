# FatCreateEa

- ea: `0x140035234`
- end: `0x1400355ff`
- name: `FatCreateEa`
- size: `971`
- prototype: `__int64 __fastcall(__int64, __int64, char *, unsigned int, const void **, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x140028cc0`
- `0x140029774`
- `0x14002cbe4`

## callees

- `0x14000c380`
- `0x14000c680`
- `0x140034678`
- `0x1400350f0`
- `0x140035234`
- `0x140035dc0`
- `0x140035e50`
- `0x140036658`
- `0x1400366f0`
- `0x1400367d8`
- `0x140036c78`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x140035566`
- `ntoskrnl!CcFlushCache` at `0x140035566`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400355ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d706`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400355ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d706`
- `ntoskrnl!CcUnpinData` at `0x1400355c3`
- `ntoskrnl!CcUnpinData` at `0x14005d71c`
- `ntoskrnl!CcUnpinData` at `0x1400355c3`
- `ntoskrnl!CcUnpinData` at `0x14005d71c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035590`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d6e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140035590`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d6e1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400352c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400352c4`
- `ntoskrnl!ExRaiseStatus` at `0x14003534b`
- `ntoskrnl!ExRaiseStatus` at `0x140035379`
- `ntoskrnl!ExRaiseStatus` at `0x1400353cc`
- `ntoskrnl!ExRaiseStatus` at `0x1400353f8`
- `ntoskrnl!ExRaiseStatus` at `0x1400354a0`
- `ntoskrnl!ExRaiseStatus` at `0x14003534b`
- `ntoskrnl!ExRaiseStatus` at `0x140035379`
- `ntoskrnl!ExRaiseStatus` at `0x1400353cc`
- `ntoskrnl!ExRaiseStatus` at `0x1400353f8`
- `ntoskrnl!ExRaiseStatus` at `0x1400354a0`

## pseudocode

```c
__int64 __fastcall FatCreateEa(
        __int64 a1,
        __int64 a2,
        char *a3,
        unsigned int a4,
        const void **a5,
        unsigned __int16 *a6)
{
  __int64 v6; // r14
  int v10; // r13d
  unsigned int v11; // ebx
  char *PoolWithTag; // rax
  char *v13; // rsi
  char *v14; // rbx
  char *v15; // r14
  char *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // ebx
  char v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  PVOID v25; // rcx
  unsigned int v27; // [rsp+44h] [rbp-D4h] BYREF
  unsigned int v28; // [rsp+48h] [rbp-D0h] BYREF
  PVOID Bcb; // [rsp+50h] [rbp-C8h] BYREF
  unsigned int v30; // [rsp+58h] [rbp-C0h] BYREF
  char *v31; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+68h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+80h] [rbp-98h] BYREF
  int v35[24]; // [rsp+90h] [rbp-88h] BYREF

  v6 = a4;
  v31 = 0;
  Bcb = 0;
  memset(v35, 0, sizeof(v35));
  v32 = 0;
  v28 = 0;
  v27 = 0;
  v10 = 1 << *(_BYTE *)(a2 + 378);
  v11 = -v10 & (v10 + 29);
  v28 = v11;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v11, 0x65746146u);
  v13 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v11);
  v31 = v13;
  memmove(v13 + 8, a5[1], *(unsigned __int16 *)a5);
  v28 = v11 - 30;
  v14 = a3;
  while ( 1 )
  {
    v15 = &a3[v6];
    if ( v14 >= v15 )
      break;
    v33 = 0;
    v30 = 0;
    v16 = v14 + 11;
    if ( v14 + 11 > v15 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 48LL) = -1073741789;
      *(_DWORD *)(a1 + 72) = -1073741789;
      ExRaiseStatus(-1073741789);
    }
    if ( &v16[(unsigned __int8)v14[5] + (unsigned __int64)*((unsigned __int16 *)v14 + 3)] > v15 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 48LL) = -2147483643;
      *(_DWORD *)(a1 + 72) = -2147483643;
      ExRaiseStatus(-2147483643);
    }
    LOWORD(v33) = (unsigned __int8)v14[5];
    *((_QWORD *)&v33 + 1) = v14 + 8;
    v34 = v33;
    if ( !(unsigned __int8)FatIsEaNameValid(v16, &v34) )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 56LL) = v14 - a3;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 48LL) = -2147483629;
      *(_DWORD *)(a1 + 72) = -2147483629;
      ExRaiseStatus(-2147483629);
    }
    if ( (v14[4] & 0x7F) != 0 )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 40) + 56LL) = v14 - a3;
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 48LL) = -2147483629;
      *(_DWORD *)(a1 + 72) = -2147483629;
      ExRaiseStatus(-2147483629);
    }
    if ( (unsigned __int8)FatLocateEaByName(v17, v13 + 30, v27, &v33, &v30) )
      FatDeletePackedEa(v18, v13, &v27, v30);
    if ( *((_WORD *)v14 + 3) )
    {
      FatAppendPackedEa(v18, (unsigned int)&v31, (unsigned int)&v27, (unsigned int)&v28, (__int64)v14, v10);
      v13 = v31;
    }
    v19 = *(unsigned int *)v14;
    if ( (_DWORD)v19 )
      v14 += v19;
    else
      v14 = v15;
    v6 = a4;
  }
  if ( v27 )
  {
    v20 = v27 + 4;
    if ( v27 + 4 > 0xFFFF )
    {
      *(_DWORD *)(a1 + 72) = -1073741744;
      ExRaiseStatus(-1073741744);
    }
    FatGetEaFile(a1, a2, (__int64)&v32, &Bcb, 1, 1);
    v21 = 1;
    FatAddEaSet(a1, a2, v27 + 30, (__int64)Bcb, v32, a6, (_WORD **)v35);
    v22 = *(_QWORD *)v35;
    v27 = v20;
    *(_DWORD *)(v13 + 26) = v20;
    memmove((void *)(v22 + 4), v13 + 4, v20 + 22);
    FatMarkEaRangeDirty(v23, *(_QWORD *)(a2 + 776), v35);
    FatUnpinEaRange(v24, v35);
    CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(a2 + 776) + 40LL), 0, 0, 0);
  }
  else
  {
    *a6 = 0;
    v21 = 0;
  }
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( v21 )
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a2 + 784) + 8LL));
  v25 = Bcb;
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  return FatUnpinEaRange(v25, v35);
}

```

## disassembly

```asm
0x140035234  mov     rax, rsp
0x140035237  mov     [rax+8], rbx
0x14003523b  mov     [rax+18h], rsi
0x14003523f  mov     [rax+20h], r9d
0x140035243  mov     [rax+10h], rdx
0x140035247  push    rdi
0x140035248  push    r12
0x14003524a  push    r13
0x14003524c  push    r14
0x14003524e  push    r15
0x140035250  sub     rsp, 0F0h
0x140035257  mov     r14d, r9d
0x14003525a  mov     r15, r8
0x14003525d  mov     r12, rdx
0x140035260  mov     rdi, rcx
0x140035263  xor     ebx, ebx
0x140035265  mov     [rsp+118h+var_B8], rbx
0x14003526a  mov     [rsp+118h+Bcb], rbx
0x14003526f  mov     [rsp+118h+var_D8], bl
0x140035273  xor     edx, edx; Val
0x140035275  lea     r8d, [rbx+60h]; Size
0x140035279  lea     rcx, [rax-88h]; void *
0x140035280  call    memset
0x140035285  nop
0x140035286  mov     [rsp+118h+var_B0], rbx
0x14003528b  mov     [rsp+118h+var_D4], ebx
0x14003528f  mov     [rsp+118h+var_D0], ebx
0x140035293  mov     [rsp+118h+var_D4], ebx
0x140035297  mov     cl, [r12+17Ah]
0x14003529f  lea     r13d, [rbx+1]
0x1400352a3  shl     r13d, cl
0x1400352a6  lea     ecx, [r13+1Dh]
0x1400352aa  mov     eax, r13d
0x1400352ad  neg     eax
0x1400352af  and     ecx, eax
0x1400352b1  mov     ebx, ecx
0x1400352b3  mov     [rsp+118h+var_D0], ebx
0x1400352b7  mov     r8d, 65746146h; Tag
0x1400352bd  mov     edx, ecx; NumberOfBytes
0x1400352bf  mov     ecx, 411h; PoolType
0x1400352c4  call    cs:__imp_ExAllocatePoolWithTag
0x1400352cb  nop     dword ptr [rax+rax+00h]
0x1400352d0  mov     rsi, rax
0x1400352d3  xor     ecx, ecx
0x1400352d5  cmp     cs:ExPoolZeroingNativelySupported, cl
0x1400352db  jnz     short loc_1400352EF
0x1400352dd  test    rax, rax
0x1400352e0  jz      short loc_1400352EF
0x1400352e2  mov     r8d, ebx; Size
0x1400352e5  xor     edx, edx; Val
0x1400352e7  mov     rcx, rax; void *
0x1400352ea  call    memset
0x1400352ef  mov     [rsp+118h+var_B8], rsi
0x1400352f4  mov     rdx, [rsp+118h+arg_20]
0x1400352fc  movzx   r8d, word ptr [rdx]; Size
0x140035300  lea     rcx, [rsi+8]; void *
0x140035304  mov     rdx, [rdx+8]; Src
0x140035308  call    memmove
0x14003530d  lea     eax, [rbx-1Eh]
0x140035310  mov     [rsp+118h+var_D0], eax
0x140035314  mov     rbx, r15
0x140035317  add     r14, r15
0x14003531a  cmp     rbx, r14
0x14003531d  jnb     loc_14003547F
0x140035323  xorps   xmm0, xmm0
0x140035326  movups  [rsp+118h+var_A8], xmm0
0x14003532b  mov     [rsp+118h+var_C0], 0
0x140035333  lea     rcx, [rbx+0Bh]
0x140035337  cmp     rcx, r14
0x14003533a  jbe     short loc_140035357
0x14003533c  mov     rax, [rdi+28h]
0x140035340  mov     ecx, 0C0000023h; Status
0x140035345  mov     [rax+30h], ecx
0x140035348  mov     [rdi+48h], ecx
0x14003534b  call    cs:__imp_ExRaiseStatus
0x140035357  movzx   edx, byte ptr [rbx+5]
0x14003535b  movzx   eax, word ptr [rbx+6]
0x14003535f  add     rax, rdx
0x140035362  add     rax, rcx
0x140035365  cmp     rax, r14
0x140035368  jbe     short loc_140035385
0x14003536a  mov     rax, [rdi+28h]
0x14003536e  mov     ecx, 80000005h; Status
0x140035373  mov     [rax+30h], ecx
0x140035376  mov     [rdi+48h], ecx
0x140035379  call    cs:__imp_ExRaiseStatus
0x140035385  mov     word ptr [rsp+118h+var_A8], dx
0x14003538a  lea     rax, [rbx+8]
0x14003538e  mov     qword ptr [rsp+118h+var_A8+8], rax
0x140035393  movaps  xmm0, [rsp+118h+var_A8]
0x140035398  movdqa  [rsp+118h+var_98], xmm0
0x1400353a1  lea     rdx, [rsp+118h+var_98]
0x1400353a9  call    FatIsEaNameValid
0x1400353ae  test    al, al
0x1400353b0  jnz     short loc_1400353D8
0x1400353b2  sub     rbx, r15
0x1400353b5  mov     rax, [rdi+28h]
0x1400353b9  mov     [rax+38h], rbx
0x1400353bd  mov     rax, [rdi+28h]
0x1400353c1  mov     ecx, 80000013h; Status
0x1400353c6  mov     [rax+30h], ecx
0x1400353c9  mov     [rdi+48h], ecx
0x1400353cc  call    cs:__imp_ExRaiseStatus
0x1400353d8  test    byte ptr [rbx+4], 7Fh
0x1400353dc  jz      short loc_140035404
0x1400353de  sub     rbx, r15
0x1400353e1  mov     rax, [rdi+28h]
0x1400353e5  mov     [rax+38h], rbx
0x1400353e9  mov     rax, [rdi+28h]
0x1400353ed  mov     ecx, 80000013h; Status
0x1400353f2  mov     [rax+30h], ecx
0x1400353f5  mov     [rdi+48h], ecx
0x1400353f8  call    cs:__imp_ExRaiseStatus
0x140035404  lea     rdx, [rsi+1Eh]
0x140035408  lea     rax, [rsp+118h+var_C0]
0x14003540d  mov     qword ptr [rsp+118h+var_F8], rax
0x140035412  lea     r9, [rsp+118h+var_A8]
0x140035417  mov     r8d, [rsp+118h+var_D4]
0x14003541c  call    FatLocateEaByName
0x140035421  test    al, al
0x140035423  jz      short loc_140035437
0x140035425  mov     r9d, [rsp+118h+var_C0]
0x14003542a  lea     r8, [rsp+118h+var_D4]
0x14003542f  mov     rdx, rsi
0x140035432  call    FatDeletePackedEa
0x140035437  xor     eax, eax
0x140035439  cmp     [rbx+6], ax
0x14003543d  jnz     short loc_140035441
0x14003543f  jmp     short loc_140035464
0x140035441  mov     dword ptr [rsp+118h+var_F0], r13d
0x140035446  mov     qword ptr [rsp+118h+var_F8], rbx
0x14003544b  lea     r9, [rsp+118h+var_D0]
0x140035450  lea     r8, [rsp+118h+var_D4]
0x140035455  lea     rdx, [rsp+118h+var_B8]
0x14003545a  call    FatAppendPackedEa
0x14003545f  mov     rsi, [rsp+118h+var_B8]
0x140035464  mov     eax, [rbx]
0x140035466  test    eax, eax
0x140035468  jnz     short loc_14003546F
0x14003546a  mov     rbx, r14
0x14003546d  jmp     short loc_140035472
0x14003546f  add     rbx, rax
0x140035472  mov     r14d, [rsp+118h+arg_18]
0x14003547a  jmp     loc_140035317
0x14003547f  mov     eax, [rsp+118h+var_D4]
0x140035483  xor     ebx, ebx
0x140035485  test    eax, eax
0x140035487  jz      loc_140035576
0x14003548d  lea     ebx, [rax+4]
0x140035490  cmp     ebx, 0FFFFh
0x140035496  jbe     short loc_1400354AC
0x140035498  mov     ecx, 0C0000050h; Status
0x14003549d  mov     [rdi+48h], ecx
0x1400354a0  call    cs:__imp_ExRaiseStatus
0x1400354ac  mov     [rsp+118h+var_F0], 1; char
0x1400354b1  mov     [rsp+118h+var_F8], 1; char
0x1400354b6  lea     r9, [rsp+118h+Bcb]
0x1400354bb  lea     r8, [rsp+118h+var_B0]
0x1400354c0  mov     rdx, r12; int
0x1400354c3  mov     rcx, rdi; int
0x1400354c6  call    FatGetEaFile
0x1400354cb  mov     r14b, 1
0x1400354ce  mov     [rsp+118h+var_D8], r14b
0x1400354d3  mov     r8d, [rsp+118h+var_D4]
0x1400354d8  add     r8d, 1Eh
0x1400354dc  lea     rax, [rsp+118h+var_88]
0x1400354e4  mov     qword ptr [rsp+118h+var_E8], rax; int
0x1400354e9  mov     rax, [rsp+118h+arg_28]
0x1400354f1  mov     qword ptr [rsp+118h+var_F0], rax; __int64
0x1400354f6  mov     rax, [rsp+118h+var_B0]
0x1400354fb  mov     qword ptr [rsp+118h+var_F8], rax; __int64
0x140035500  mov     r9, [rsp+118h+Bcb]
0x140035505  mov     rdx, r12; int
0x140035508  mov     rcx, rdi; int
0x14003550b  call    FatAddEaSet
0x140035510  mov     rcx, qword ptr [rsp+118h+var_88]
0x140035518  mov     [rsp+118h+var_D4], ebx
0x14003551c  mov     [rsi+1Ah], ebx
0x14003551f  lea     r8d, [rbx+16h]; Size
0x140035523  lea     rdx, [rsi+4]; Src
0x140035527  add     rcx, 4; void *
0x14003552b  call    memmove
0x140035530  lea     r8, [rsp+118h+var_88]
0x140035538  mov     rdx, [r12+308h]
0x140035540  call    FatMarkEaRangeDirty
0x140035545  lea     rdx, [rsp+118h+var_88]
0x14003554d  call    FatUnpinEaRange
0x140035552  mov     rcx, [r12+308h]
0x14003555a  xor     r9d, r9d; IoStatus
0x14003555d  xor     r8d, r8d; Length
0x140035560  xor     edx, edx; FileOffset
0x140035562  mov     rcx, [rcx+28h]; SectionObjectPointer
0x140035566  call    cs:__imp_CcFlushCache
0x14003556d  nop     dword ptr [rax+rax+00h]
0x140035572  xor     ebx, ebx
0x140035574  jmp     short loc_140035586
0x140035576  mov     rax, [rsp+118h+arg_28]
0x14003557e  mov     [rax], bx
0x140035581  mov     r14b, [rsp+118h+var_D8]
0x140035586  test    rsi, rsi
0x140035589  jz      short loc_14003559C
0x14003558b  xor     edx, edx; Tag
0x14003558d  mov     rcx, rsi; P
0x140035590  call    cs:__imp_ExFreePoolWithTag
0x140035597  nop     dword ptr [rax+rax+00h]
0x14003559c  test    r14b, r14b
0x14003559f  jz      short loc_1400355B9
0x1400355a1  mov     rcx, [r12+310h]
0x1400355a9  mov     rcx, [rcx+8]; Resource
0x1400355ad  call    cs:__imp_ExReleaseResourceLite
0x1400355b4  nop     dword ptr [rax+rax+00h]
0x1400355b9  mov     rcx, [rsp+118h+Bcb]; Bcb
0x1400355be  test    rcx, rcx
0x1400355c1  jz      short loc_1400355D4
0x1400355c3  call    cs:__imp_CcUnpinData
0x1400355ca  nop     dword ptr [rax+rax+00h]
0x1400355cf  mov     [rsp+118h+Bcb], rbx
0x1400355d4  lea     rdx, [rsp+118h+var_88]
0x1400355dc  call    FatUnpinEaRange
0x1400355e1  lea     r11, [rsp+118h+var_28]
0x1400355e9  mov     rbx, [r11+30h]
0x1400355ed  mov     rsi, [r11+40h]
0x1400355f1  mov     rsp, r11
0x1400355f4  pop     r15
0x1400355f6  pop     r14
0x1400355f8  pop     r13
0x1400355fa  pop     r12
0x1400355fc  pop     rdi
0x1400355fd  retn
0x14005d6cd  push    rbp
0x14005d6cf  sub     rsp, 40h
0x14005d6d3  mov     rbp, rdx
0x14005d6d6  mov     rcx, [rbp+60h]; P
0x14005d6da  test    rcx, rcx
0x14005d6dd  jz      short loc_14005D6EE
0x14005d6df  xor     edx, edx; Tag
0x14005d6e1  call    cs:__imp_ExFreePoolWithTag
0x14005d6e8  nop     dword ptr [rax+rax+00h]
0x14005d6ed  nop
0x14005d6ee  cmp     byte ptr [rbp+40h], 0
0x14005d6f2  jz      short loc_14005D713
0x14005d6f4  mov     rax, [rbp+128h]
0x14005d6fb  mov     rcx, [rax+310h]
0x14005d702  mov     rcx, [rcx+8]; Resource
0x14005d706  call    cs:__imp_ExReleaseResourceLite
0x14005d70d  nop     dword ptr [rax+rax+00h]
0x14005d712  nop
0x14005d713  mov     rcx, [rbp+50h]; Bcb
0x14005d717  test    rcx, rcx
0x14005d71a  jz      short loc_14005D730
0x14005d71c  call    cs:__imp_CcUnpinData
0x14005d723  nop     dword ptr [rax+rax+00h]
0x14005d728  mov     qword ptr [rbp+50h], 0
0x14005d730  lea     rdx, [rbp+90h]
0x14005d737  call    FatUnpinEaRange
0x14005d73c  nop
0x14005d73d  add     rsp, 40h
0x14005d741  pop     rbp
0x14005d742  retn
```
