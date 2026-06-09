# UxpTpAllocateTransmitPacket

- ea: `0x1c000da40`
- end: `0x1c000dce6`
- name: `UxpTpAllocateTransmitPacket`
- size: `678`
- prototype: `__int64 __fastcall(int, int, int, int, __int16, PEPROCESS Process, PVOID Object, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00c2f70`

## callees

- `0x1c0001118`
- `0x1c000da40`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c004dd84`
- `0x1c00c3270`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c000dae5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0023593`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c000dae5`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0023593`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c000da7d`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x1c000da7d`
- `ntoskrnl!PsReturnPoolQuota` at `0x1c00235fc`
- `ntoskrnl!PsReturnPoolQuota` at `0x1c00235fc`
- `ntoskrnl!ObfReferenceObject` at `0x1c000dc12`
- `ntoskrnl!ObfReferenceObject` at `0x1c000dc26`
- `ntoskrnl!ObfReferenceObject` at `0x1c000dc12`
- `ntoskrnl!ObfReferenceObject` at `0x1c000dc26`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0023553`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0023553`

## pseudocode

```c
PSLIST_ENTRY __fastcall UxpTpAllocateTransmitPacket(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int16 a5,
        PEPROCESS Process,
        PVOID Object,
        int a8,
        struct _SLIST_ENTRY *a9,
        __int64 a10,
        struct _SLIST_ENTRY *a11,
        struct _SLIST_ENTRY *a12,
        __int64 a13,
        struct _SLIST_ENTRY *a14,
        struct _SLIST_ENTRY *a15,
        struct _SLIST_ENTRY *a16)
{
  struct _KPROCESS *v16; // rsi
  __int64 v18; // r14
  unsigned int v21; // r8d
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rbp
  PSLIST_ENTRY v26; // rdi
  __int64 v27; // rdx
  __int16 Next; // ax
  int v30; // r8d
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 (__fastcall *v34)(__int64, __int64, __int64, __int64); // rax
  __int64 v35; // rdi
  unsigned int v36; // r8d
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rax

  v16 = Process;
  v18 = a3;
  if ( !Process )
    v16 = UxSystemProcess;
  if ( PsChargeProcessPoolQuota(v16, (POOL_TYPE)512, (unsigned int)UxTpTransmitPacketSize) < 0 )
    return 0;
  if ( UxCompactMode )
  {
    v35 = qword_1C0074300;
    v36 = KeGetCurrentNodeNumber() + 1;
    v37 = *(_DWORD *)v35 - 1;
    if ( v36 < *(_DWORD *)v35 )
      v37 = v36;
    v38 = v37;
    v39 = *(_QWORD *)(v35 + 32);
    v25 = *(_QWORD *)(v39 + 8 * v38);
    if ( !*(_BYTE *)(v25 + 112) )
      PplpLazyInitializeLookasideList(v35, *(_QWORD *)(v39 + 8 * v38));
    ++*(_DWORD *)(v25 + 20);
    v26 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v25);
    if ( v26 )
      goto LABEL_10;
  }
  else
  {
    v21 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v22 = *(_DWORD *)qword_1C0074300 - 1;
    if ( v21 < *(_DWORD *)qword_1C0074300 )
      v22 = v21;
    v23 = v22;
    v24 = *(_QWORD *)(qword_1C0074300 + 32);
    v25 = *(_QWORD *)(v24 + 8 * v23);
    if ( !*(_BYTE *)(v25 + 112) )
      PplpLazyInitializeLookasideList(qword_1C0074300, *(_QWORD *)(v24 + 8 * v23));
    ++*(_DWORD *)(v25 + 20);
    v26 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v25);
    if ( v26 )
      goto LABEL_10;
  }
  v31 = *(unsigned int *)(v25 + 40);
  v32 = *(unsigned int *)(v25 + 44);
  v33 = *(unsigned int *)(v25 + 36);
  v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v25 + 48);
  ++*(_DWORD *)(v25 + 24);
  v26 = (PSLIST_ENTRY)v34(v33, v32, v31, v25);
LABEL_10:
  if ( v26 )
  {
    memset(v26, 0, 0xE0u);
    LOWORD(v26[6].Next) = a5;
    v26[9].Next = a14;
    LODWORD(v26[4].Next) = a8;
    v26[5].Next = a9;
    *((_QWORD *)&v26[5].Next + 1) = a10;
    v26[10].Next = a12;
    *((_QWORD *)&v26[10].Next + 1) = a13;
    v26[11].Next = a11;
    LODWORD(v26[1].Next) = 1095789653;
    v26[3].Next = (struct _SLIST_ENTRY *)v16;
    *((_QWORD *)&v26[3].Next + 1) = Object;
    *((_QWORD *)&v26[8].Next + 1) = a2;
    LODWORD(v26[8].Next) = v18;
    *((_DWORD *)&v26[9].Next + 2) = a4;
    HIDWORD(v26[8].Next) = -1;
    *((_QWORD *)&v26[2].Next + 1) = a1;
    if ( a15 )
      *(PSLIST_ENTRY)((char *)v26 + 184) = *a15;
    v26[13].Next = a16;
    *((_QWORD *)&v26[6].Next + 1) = v26 + 14;
    LODWORD(v26[15].Next) = 1262709845;
    *(_DWORD *)(*((_QWORD *)&v26[6].Next + 1) + 20LL) = 2;
    HIDWORD(v26[1].Next) = 1;
    if ( v16 && v16 != UxSystemProcess )
      ObfReferenceObject(v16);
    if ( Object )
      ObfReferenceObject(Object);
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 8) + 20LL));
    if ( (int)v18 > 0 )
    {
      v27 = v18;
      do
      {
        if ( a2 )
        {
          if ( *(_DWORD *)a2 == 2 )
          {
            v30 = *(char *)(*(_QWORD *)(a2 + 48) + 76LL);
            if ( v30 > BYTE2(v26[6].Next) )
              BYTE2(v26[6].Next) = v30;
          }
        }
        a2 += 80;
        --v27;
      }
      while ( v27 );
    }
    UxpTpIncrementChunkPointer(v26);
    Next = (__int16)v26[6].Next;
    if ( (Next & 0x4000) != 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&v26[9].Next[1].Next + 2);
    }
    else if ( Next < 0 && !(unsigned __int8)UlHkeReferenceCalloutContext(v26[9].Next) )
    {
      v26[9].Next = 0;
      LOWORD(v26[6].Next) &= ~0x8000u;
    }
  }
  else
  {
    PsReturnPoolQuota(v16, (POOL_TYPE)512, (unsigned int)UxTpTransmitPacketSize);
  }
  return v26;
}

```

## disassembly

```asm
0x1c000da40  mov     [rsp+arg_10], rbx
0x1c000da45  mov     [rsp+arg_18], rsi
0x1c000da4a  push    r12
0x1c000da4c  push    r14
0x1c000da4e  push    r15
0x1c000da50  sub     rsp, 30h
0x1c000da54  mov     rsi, [rsp+48h+Process]
0x1c000da59  mov     r12d, r9d
0x1c000da5c  mov     r14d, r8d
0x1c000da5f  mov     rbx, rdx
0x1c000da62  mov     r15, rcx
0x1c000da65  test    rsi, rsi
0x1c000da68  jz      loc_1C000DCD6
0x1c000da6e  mov     r8d, cs:UxTpTransmitPacketSize; Amount
0x1c000da75  mov     edx, 200h; PoolType
0x1c000da7a  mov     rcx, rsi; Process
0x1c000da7d  call    cs:__imp_PsChargeProcessPoolQuota
0x1c000da84  nop     dword ptr [rax+rax+00h]
0x1c000da89  test    eax, eax
0x1c000da8b  js      loc_1C000DCE2
0x1c000da91  cmp     cs:UxCompactMode, 0
0x1c000da98  mov     [rsp+48h+arg_0], rbp
0x1c000da9d  mov     [rsp+48h+arg_8], rdi
0x1c000daa2  jnz     loc_1C002354C
0x1c000daa8  mov     eax, gs:1A4h
0x1c000dab0  mov     rcx, cs:qword_1C0074300
0x1c000dab7  lea     r8d, [rax+1]
0x1c000dabb  mov     edx, [rcx]
0x1c000dabd  cmp     r8d, edx
0x1c000dac0  lea     eax, [rdx-1]
0x1c000dac3  cmovb   eax, r8d
0x1c000dac7  mov     edx, eax
0x1c000dac9  mov     rax, [rcx+20h]
0x1c000dacd  mov     rbp, [rax+rdx*8]
0x1c000dad1  cmp     byte ptr [rbp+70h], 0
0x1c000dad5  jnz     short loc_1C000DADF
0x1c000dad7  mov     rdx, rbp
0x1c000dada  call    PplpLazyInitializeLookasideList
0x1c000dadf  inc     dword ptr [rbp+14h]
0x1c000dae2  mov     rcx, rbp; ListHead
0x1c000dae5  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c000daec  nop     dword ptr [rax+rax+00h]
0x1c000daf1  mov     rdi, rax
0x1c000daf4  test    rax, rax
0x1c000daf7  jz      loc_1C000DCB4
0x1c000dafd  test    rdi, rdi
0x1c000db00  jz      loc_1C00235ED
0x1c000db06  xor     edx, edx; Val
0x1c000db08  mov     r8d, 0E0h; Size
0x1c000db0e  mov     rcx, rdi; void *
0x1c000db11  call    memset
0x1c000db16  movzx   eax, [rsp+48h+arg_20]
0x1c000db1b  mov     rbp, [rsp+48h+Object]
0x1c000db23  mov     [rdi+60h], ax
0x1c000db27  mov     rax, [rsp+48h+arg_68]
0x1c000db2f  mov     [rdi+90h], rax
0x1c000db36  mov     eax, [rsp+48h+arg_38]
0x1c000db3d  mov     [rdi+40h], eax
0x1c000db40  mov     rax, [rsp+48h+arg_40]
0x1c000db48  mov     [rdi+50h], rax
0x1c000db4c  mov     rax, [rsp+48h+arg_48]
0x1c000db54  mov     [rdi+58h], rax
0x1c000db58  mov     rax, [rsp+48h+arg_58]
0x1c000db60  mov     [rdi+0A0h], rax
0x1c000db67  mov     rax, [rsp+48h+arg_60]
0x1c000db6f  mov     [rdi+0A8h], rax
0x1c000db76  mov     rax, [rsp+48h+arg_50]
0x1c000db7e  mov     [rdi+0B0h], rax
0x1c000db85  mov     rax, [rsp+48h+arg_70]
0x1c000db8d  mov     dword ptr [rdi+10h], 41506C55h
0x1c000db94  mov     [rdi+30h], rsi
0x1c000db98  mov     [rdi+38h], rbp
0x1c000db9c  mov     [rdi+88h], rbx
0x1c000dba3  mov     [rdi+80h], r14d
0x1c000dbaa  mov     [rdi+98h], r12d
0x1c000dbb1  mov     dword ptr [rdi+84h], 0FFFFFFFFh
0x1c000dbbb  mov     [rdi+28h], r15
0x1c000dbbf  test    rax, rax
0x1c000dbc2  jz      short loc_1C000DBCE
0x1c000dbc4  movups  xmm0, xmmword ptr [rax]
0x1c000dbc7  movups  xmmword ptr [rdi+0B8h], xmm0
0x1c000dbce  mov     rax, [rsp+48h+arg_78]
0x1c000dbd6  mov     [rdi+0D0h], rax
0x1c000dbdd  lea     rax, [rdi+0E0h]
0x1c000dbe4  mov     [rdi+68h], rax
0x1c000dbe8  mov     dword ptr [rax+10h], 4B436C55h
0x1c000dbef  mov     rax, [rdi+68h]
0x1c000dbf3  mov     dword ptr [rax+14h], 2
0x1c000dbfa  mov     dword ptr [rdi+14h], 1
0x1c000dc01  test    rsi, rsi
0x1c000dc04  jz      short loc_1C000DC1E
0x1c000dc06  cmp     rsi, cs:UxSystemProcess
0x1c000dc0d  jz      short loc_1C000DC1E
0x1c000dc0f  mov     rcx, rsi; Object
0x1c000dc12  call    cs:__imp_ObfReferenceObject
0x1c000dc19  nop     dword ptr [rax+rax+00h]
0x1c000dc1e  test    rbp, rbp
0x1c000dc21  jz      short loc_1C000DC32
0x1c000dc23  mov     rcx, rbp; Object
0x1c000dc26  call    cs:__imp_ObfReferenceObject
0x1c000dc2d  nop     dword ptr [rax+rax+00h]
0x1c000dc32  mov     rax, [r15+8]
0x1c000dc36  lock inc dword ptr [rax+14h]
0x1c000dc3a  test    r14d, r14d
0x1c000dc3d  jle     short loc_1C000DC56
0x1c000dc3f  mov     rdx, r14
0x1c000dc42  test    rbx, rbx
0x1c000dc45  jz      short loc_1C000DC4C
0x1c000dc47  cmp     dword ptr [rbx], 2
0x1c000dc4a  jz      short loc_1C000DC9C
0x1c000dc4c  add     rbx, 50h ; 'P'
0x1c000dc50  sub     rdx, 1
0x1c000dc54  jnz     short loc_1C000DC42
0x1c000dc56  mov     rcx, rdi
0x1c000dc59  call    UxpTpIncrementChunkPointer
0x1c000dc5e  movzx   eax, word ptr [rdi+60h]
0x1c000dc62  mov     ecx, 4000h
0x1c000dc67  test    cx, ax
0x1c000dc6a  jnz     loc_1C00235B0
0x1c000dc70  test    ax, ax
0x1c000dc73  js      loc_1C00235C0
0x1c000dc79  mov     rbp, [rsp+48h+arg_0]
0x1c000dc7e  mov     rax, rdi
0x1c000dc81  mov     rdi, [rsp+48h+arg_8]
0x1c000dc86  mov     rbx, [rsp+48h+arg_10]
0x1c000dc8b  mov     rsi, [rsp+48h+arg_18]
0x1c000dc90  add     rsp, 30h
0x1c000dc94  pop     r15
0x1c000dc96  pop     r14
0x1c000dc98  pop     r12
0x1c000dc9a  retn
0x1c000dc9c  mov     rax, [rbx+30h]
0x1c000dca0  movzx   ecx, byte ptr [rdi+62h]
0x1c000dca4  movsx   r8d, byte ptr [rax+4Ch]
0x1c000dca9  cmp     r8d, ecx
0x1c000dcac  jle     short loc_1C000DC4C
0x1c000dcae  mov     [rdi+62h], r8b
0x1c000dcb2  jmp     short loc_1C000DC4C
0x1c000dcb4  mov     r8d, [rbp+28h]
0x1c000dcb8  mov     r9, rbp
0x1c000dcbb  mov     edx, [rbp+2Ch]
0x1c000dcbe  mov     ecx, [rbp+24h]
0x1c000dcc1  mov     rax, [rbp+30h]
0x1c000dcc5  inc     dword ptr [rbp+18h]
0x1c000dcc8  call    cs:__guard_dispatch_icall_fptr
0x1c000dcce  mov     rdi, rax
0x1c000dcd1  jmp     loc_1C000DAFD
0x1c000dcd6  mov     rsi, cs:UxSystemProcess
0x1c000dcdd  jmp     loc_1C000DA6E
0x1c000dce2  xor     eax, eax
0x1c000dce4  jmp     short loc_1C000DC86
0x1c002354c  mov     rdi, cs:qword_1C0074300
0x1c0023553  call    cs:__imp_KeGetCurrentNodeNumber
0x1c002355a  nop     dword ptr [rax+rax+00h]
0x1c002355f  mov     edx, [rdi]
0x1c0023561  movzx   r8d, ax
0x1c0023565  inc     r8d
0x1c0023568  cmp     r8d, edx
0x1c002356b  lea     eax, [rdx-1]
0x1c002356e  cmovb   eax, r8d
0x1c0023572  mov     edx, eax
0x1c0023574  mov     rax, [rdi+20h]
0x1c0023578  mov     rbp, [rax+rdx*8]
0x1c002357c  cmp     byte ptr [rbp+70h], 0
0x1c0023580  jnz     short loc_1C002358D
0x1c0023582  mov     rdx, rbp
0x1c0023585  mov     rcx, rdi
0x1c0023588  call    PplpLazyInitializeLookasideList
0x1c002358d  inc     dword ptr [rbp+14h]
0x1c0023590  mov     rcx, rbp; ListHead
0x1c0023593  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c002359a  nop     dword ptr [rax+rax+00h]
0x1c002359f  mov     rdi, rax
0x1c00235a2  test    rax, rax
0x1c00235a5  jnz     loc_1C000DAFD
0x1c00235ab  jmp     loc_1C000DCB4
0x1c00235b0  mov     rax, [rdi+90h]
0x1c00235b7  lock inc dword ptr [rax+18h]
0x1c00235bb  jmp     loc_1C000DC79
0x1c00235c0  mov     rcx, [rdi+90h]
0x1c00235c7  call    UlHkeReferenceCalloutContext
0x1c00235cc  test    al, al
0x1c00235ce  jnz     loc_1C000DC79
0x1c00235d4  mov     eax, 7FFFh
0x1c00235d9  mov     qword ptr [rdi+90h], 0
0x1c00235e4  and     [rdi+60h], ax
0x1c00235e8  jmp     loc_1C000DC79
0x1c00235ed  mov     r8d, cs:UxTpTransmitPacketSize; Amount
0x1c00235f4  mov     edx, 200h; PoolType
0x1c00235f9  mov     rcx, rsi; Process
0x1c00235fc  call    cs:__imp_PsReturnPoolQuota
0x1c0023603  nop     dword ptr [rax+rax+00h]
0x1c0023608  nop
0x1c0023609  jmp     loc_1C000DC79
```
