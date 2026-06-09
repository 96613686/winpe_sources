# UxpWskCreateIoContext

- ea: `0x1c0013e20`
- end: `0x1c0013fcf`
- name: `UxpWskCreateIoContext`
- size: `431`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0013c60`
- `0x1c0051b60`
- `0x1c0051e74`

## callees

- `0x1c0001118`
- `0x1c0013e20`
- `0x1c0014194`
- `0x1c001b610`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0026ceb`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c0026ceb`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0013e8a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0026c2b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0013e8a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0026c2b`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0026cd3`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0026d3a`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0026cd3`
- `ntoskrnl!ExQueryDepthSList` at `0x1c0026d3a`
- `ntoskrnl!IoInitializeIrp` at `0x1c0013f02`
- `ntoskrnl!IoInitializeIrp` at `0x1c0013f02`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0026beb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0026c93`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0026beb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0026c93`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0013f7e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0013f7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0013f2d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0013f2d`

## pseudocode

```c
__int64 __fastcall UxpWskCreateIoContext(
        PSLIST_ENTRY *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        struct _SLIST_ENTRY *a5,
        __int64 a6,
        __int64 a7)
{
  bool v8; // zf
  unsigned int v11; // r8d
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdi
  PSLIST_ENTRY v16; // rbx
  unsigned int v17; // ebp
  __int64 v18; // rcx
  KIRQL v19; // r8
  struct _SLIST_ENTRY **v20; // rdx
  struct _SLIST_ENTRY *v21; // rax
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 (__fastcall *v26)(__int64, __int64, __int64, __int64); // rax
  __int64 v27; // rbx
  int CurrentNodeNumber; // r10d
  __int64 v29; // rax
  unsigned int v30; // r10d
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rsi
  unsigned int v34; // r8d
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdi
  unsigned int v39; // r8d
  unsigned int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rax
  void (__fastcall *v43)(PSLIST_ENTRY, __int64); // rax

  v8 = UxCompactMode == 0;
  *a1 = 0;
  if ( v8 )
  {
    v11 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v12 = *(_DWORD *)qword_1C0074330 - 1;
    if ( v11 < *(_DWORD *)qword_1C0074330 )
      v12 = v11;
    v13 = v12;
    v14 = *(_QWORD *)(qword_1C0074330 + 32);
    v15 = *(_QWORD *)(v14 + 8 * v13);
    if ( !*(_BYTE *)(v15 + 112) )
      PplpLazyInitializeLookasideList(qword_1C0074330, *(_QWORD *)(v14 + 8 * v13));
    ++*(_DWORD *)(v15 + 20);
    v16 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v15);
    if ( v16 )
      goto LABEL_7;
LABEL_13:
    v23 = *(unsigned int *)(v15 + 40);
    v24 = *(unsigned int *)(v15 + 44);
    v25 = *(unsigned int *)(v15 + 36);
    v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v15 + 48);
    ++*(_DWORD *)(v15 + 24);
    v16 = (PSLIST_ENTRY)v26(v25, v24, v23, v15);
    goto LABEL_7;
  }
  v27 = qword_1C0074330;
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  v29 = *(_QWORD *)(v27 + 32);
  v30 = CurrentNodeNumber + 1;
  v31 = (unsigned int)(*(_DWORD *)v27 - 1);
  if ( v30 < *(_DWORD *)v27 )
    v31 = v30;
  v15 = *(_QWORD *)(v29 + 8 * v31);
  if ( !*(_BYTE *)(v15 + 112) )
    PplpLazyInitializeLookasideList(v27, *(_QWORD *)(v29 + 8 * v31));
  ++*(_DWORD *)(v15 + 20);
  v16 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v15);
  if ( !v16 )
    goto LABEL_13;
LABEL_7:
  if ( !v16 )
    return (unsigned int)-1073741670;
  v17 = 0;
  *(struct _SLIST_ENTRY **)((char *)&v16->Next + 4) = 0;
  *((_DWORD *)&v16->Next + 3) = 0;
  v16[1].Next = (struct _SLIST_ENTRY *)1;
  v16[3].Next = 0;
  *((_QWORD *)&v16[3].Next + 1) = 0;
  v16[4].Next = 0;
  *((_QWORD *)&v16[4].Next + 1) = 0;
  v16[2].Next = a5;
  *((_QWORD *)&v16[2].Next + 1) = a6;
  LODWORD(v16->Next) = a4;
  *((_QWORD *)&v16[1].Next + 1) = a2;
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 36));
  IoInitializeIrp((PIRP)&v16[5], 0x118u, 1);
  v18 = *((_QWORD *)&v16[16].Next + 1);
  *(_QWORD *)(v18 - 16) = a7;
  *(_QWORD *)(v18 - 8) = v16;
  *(_BYTE *)(v18 - 69) = -32;
  v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 120));
  if ( *(_BYTE *)(a2 + 144) )
  {
    v17 = -1073741436;
  }
  else
  {
    v20 = *(struct _SLIST_ENTRY ***)(a2 + 136);
    v21 = v16 + 3;
    if ( *v20 != (struct _SLIST_ENTRY *)(a2 + 128) )
      __fastfail(3u);
    v21->Next = (struct _SLIST_ENTRY *)(a2 + 128);
    *((_QWORD *)&v16[3].Next + 1) = v20;
    *v20 = v21;
    *a1 = v16;
    v16 = 0;
    *(_QWORD *)(a2 + 136) = v21;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 120), v19);
  if ( v16 )
  {
    v32 = *((_QWORD *)&v16[1].Next + 1);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 + 36), 0xFFFFFFFF) == 1 )
      UxTlDestroyConnection(v32);
    *((_QWORD *)&v16[1].Next + 1) = 0;
    _InterlockedDecrement((volatile signed __int32 *)&v16[1]);
    if ( UxCompactMode )
    {
      v33 = qword_1C0074330;
      v34 = KeGetCurrentNodeNumber() + 1;
      v35 = *(_DWORD *)v33 - 1;
      if ( v34 < *(_DWORD *)v33 )
        v35 = v34;
      v36 = v35;
      v37 = *(_QWORD *)(v33 + 32);
      v38 = *(_QWORD *)(v37 + 8 * v36);
      if ( !*(_BYTE *)(v38 + 112) )
        PplpLazyInitializeLookasideList(v33, *(_QWORD *)(v37 + 8 * v36));
      ++*(_DWORD *)(v38 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v38) < *(_WORD *)(v38 + 16) )
      {
LABEL_31:
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v38, v16);
        return v17;
      }
    }
    else
    {
      v39 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v40 = *(_DWORD *)qword_1C0074330 - 1;
      if ( v39 < *(_DWORD *)qword_1C0074330 )
        v40 = v39;
      v41 = v40;
      v42 = *(_QWORD *)(qword_1C0074330 + 32);
      v38 = *(_QWORD *)(v42 + 8 * v41);
      if ( !*(_BYTE *)(v38 + 112) )
        PplpLazyInitializeLookasideList(qword_1C0074330, *(_QWORD *)(v42 + 8 * v41));
      ++*(_DWORD *)(v38 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v38) < *(_WORD *)(v38 + 16) )
        goto LABEL_31;
    }
    v43 = *(void (__fastcall **)(PSLIST_ENTRY, __int64))(v38 + 56);
    ++*(_DWORD *)(v38 + 32);
    v43(v16, v38);
  }
  return v17;
}

```

## disassembly

```asm
0x1c0013e20  mov     [rsp+arg_8], rbx
0x1c0013e25  push    rsi
0x1c0013e26  push    rdi
0x1c0013e27  push    r12
0x1c0013e29  push    r14
0x1c0013e2b  push    r15
0x1c0013e2d  sub     rsp, 30h
0x1c0013e31  xor     r12d, r12d
0x1c0013e34  mov     r15d, r9d
0x1c0013e37  cmp     cs:UxCompactMode, r12b
0x1c0013e3e  mov     rsi, rdx
0x1c0013e41  mov     r14, rcx
0x1c0013e44  mov     [rcx], r12
0x1c0013e47  jnz     loc_1C0026BE4
0x1c0013e4d  mov     eax, gs:1A4h
0x1c0013e55  mov     rcx, cs:qword_1C0074330
0x1c0013e5c  lea     r8d, [rax+1]
0x1c0013e60  mov     edx, [rcx]
0x1c0013e62  cmp     r8d, edx
0x1c0013e65  lea     eax, [rdx-1]
0x1c0013e68  cmovb   eax, r8d
0x1c0013e6c  mov     edx, eax
0x1c0013e6e  mov     rax, [rcx+20h]
0x1c0013e72  mov     rdi, [rax+rdx*8]
0x1c0013e76  cmp     [rdi+70h], r12b
0x1c0013e7a  jnz     short loc_1C0013E84
0x1c0013e7c  mov     rdx, rdi
0x1c0013e7f  call    PplpLazyInitializeLookasideList
0x1c0013e84  inc     dword ptr [rdi+14h]
0x1c0013e87  mov     rcx, rdi; ListHead
0x1c0013e8a  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0013e91  nop     dword ptr [rax+rax+00h]
0x1c0013e96  mov     rbx, rax
0x1c0013e99  test    rax, rax
0x1c0013e9c  jz      loc_1C0013FAD
0x1c0013ea2  mov     [rsp+58h+arg_0], rbp
0x1c0013ea7  test    rbx, rbx
0x1c0013eaa  jz      loc_1C0026C48
0x1c0013eb0  mov     rax, [rsp+58h+arg_20]
0x1c0013eb8  mov     ebp, r12d
0x1c0013ebb  mov     [rbx+4], r12
0x1c0013ebf  mov     [rbx+0Ch], r12d
0x1c0013ec3  mov     qword ptr [rbx+10h], 1
0x1c0013ecb  mov     [rbx+30h], r12
0x1c0013ecf  mov     [rbx+38h], r12
0x1c0013ed3  mov     [rbx+40h], r12
0x1c0013ed7  mov     [rbx+48h], r12
0x1c0013edb  mov     [rbx+20h], rax
0x1c0013edf  mov     rax, [rsp+58h+arg_28]
0x1c0013ee7  mov     [rbx+28h], rax
0x1c0013eeb  mov     [rbx], r15d
0x1c0013eee  mov     [rbx+18h], rsi
0x1c0013ef2  lock inc dword ptr [rsi+24h]
0x1c0013ef6  mov     edx, 118h; PacketSize
0x1c0013efb  lea     rcx, [rbx+50h]; Irp
0x1c0013eff  mov     r8b, 1; StackSize
0x1c0013f02  call    cs:__imp_IoInitializeIrp
0x1c0013f09  nop     dword ptr [rax+rax+00h]
0x1c0013f0e  mov     rcx, [rbx+108h]
0x1c0013f15  mov     rax, [rsp+58h+arg_30]
0x1c0013f1d  mov     [rcx-10h], rax
0x1c0013f21  mov     [rcx-8], rbx
0x1c0013f25  mov     byte ptr [rcx-45h], 0E0h
0x1c0013f29  lea     rcx, [rsi+78h]; SpinLock
0x1c0013f2d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c0013f34  nop     dword ptr [rax+rax+00h]
0x1c0013f39  movzx   r8d, al
0x1c0013f3d  cmp     [rsi+90h], r12b
0x1c0013f44  jnz     loc_1C0026C52
0x1c0013f4a  lea     rcx, [rsi+80h]
0x1c0013f51  mov     rdx, [rcx+8]
0x1c0013f55  lea     rax, [rbx+30h]
0x1c0013f59  cmp     [rdx], rcx
0x1c0013f5c  jnz     loc_1C0026C5C
0x1c0013f62  mov     [rax], rcx
0x1c0013f65  mov     [rax+8], rdx
0x1c0013f69  mov     [rdx], rax
0x1c0013f6c  mov     [r14], rbx
0x1c0013f6f  mov     rbx, r12
0x1c0013f72  mov     [rcx+8], rax
0x1c0013f76  movzx   edx, r8b; NewIrql
0x1c0013f7a  lea     rcx, [rsi+78h]; SpinLock
0x1c0013f7e  call    cs:__imp_KeReleaseSpinLock
0x1c0013f85  nop     dword ptr [rax+rax+00h]
0x1c0013f8a  test    rbx, rbx
0x1c0013f8d  jnz     loc_1C0026C63
0x1c0013f93  mov     rbx, [rsp+58h+arg_8]
0x1c0013f98  mov     eax, ebp
0x1c0013f9a  mov     rbp, [rsp+58h+arg_0]
0x1c0013f9f  add     rsp, 30h
0x1c0013fa3  pop     r15
0x1c0013fa5  pop     r14
0x1c0013fa7  pop     r12
0x1c0013fa9  pop     rdi
0x1c0013faa  pop     rsi
0x1c0013fab  retn
0x1c0013fad  mov     r8d, [rdi+28h]
0x1c0013fb1  mov     r9, rdi
0x1c0013fb4  mov     edx, [rdi+2Ch]
0x1c0013fb7  mov     ecx, [rdi+24h]
0x1c0013fba  mov     rax, [rdi+30h]
0x1c0013fbe  inc     dword ptr [rdi+18h]
0x1c0013fc1  call    cs:__guard_dispatch_icall_fptr
0x1c0013fc7  mov     rbx, rax
0x1c0013fca  jmp     loc_1C0013EA2
0x1c0026be4  mov     rbx, cs:qword_1C0074330
0x1c0026beb  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0026bf2  nop     dword ptr [rax+rax+00h]
0x1c0026bf7  mov     r8d, [rbx]
0x1c0026bfa  movzx   r10d, ax
0x1c0026bfe  mov     rax, [rbx+20h]
0x1c0026c02  inc     r10d
0x1c0026c05  cmp     r10d, r8d
0x1c0026c08  lea     edx, [r8-1]
0x1c0026c0c  cmovb   edx, r10d
0x1c0026c10  mov     rdi, [rax+rdx*8]
0x1c0026c14  cmp     [rdi+70h], r12b
0x1c0026c18  jnz     short loc_1C0026C25
0x1c0026c1a  mov     rdx, rdi
0x1c0026c1d  mov     rcx, rbx
0x1c0026c20  call    PplpLazyInitializeLookasideList
0x1c0026c25  inc     dword ptr [rdi+14h]
0x1c0026c28  mov     rcx, rdi; ListHead
0x1c0026c2b  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0026c32  nop     dword ptr [rax+rax+00h]
0x1c0026c37  mov     rbx, rax
0x1c0026c3a  test    rax, rax
0x1c0026c3d  jnz     loc_1C0013EA2
0x1c0026c43  jmp     loc_1C0013FAD
0x1c0026c48  mov     ebp, 0C000009Ah
0x1c0026c4d  jmp     loc_1C0013F93
0x1c0026c52  mov     ebp, 0C0000184h
0x1c0026c57  jmp     loc_1C0013F76
0x1c0026c5c  mov     ecx, 3
0x1c0026c61  int     29h; Win8: RtlFailFast(ecx)
0x1c0026c63  mov     rcx, [rbx+18h]
0x1c0026c67  mov     eax, 0FFFFFFFFh
0x1c0026c6c  lock xadd [rcx+24h], eax
0x1c0026c71  cmp     eax, 1
0x1c0026c74  jnz     short loc_1C0026C7B
0x1c0026c76  call    UxTlDestroyConnection
0x1c0026c7b  mov     [rbx+18h], r12
0x1c0026c7f  lock dec dword ptr [rbx+10h]
0x1c0026c83  cmp     cs:UxCompactMode, r12b
0x1c0026c8a  jz      short loc_1C0026CFD
0x1c0026c8c  mov     rsi, cs:qword_1C0074330
0x1c0026c93  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0026c9a  nop     dword ptr [rax+rax+00h]
0x1c0026c9f  mov     edx, [rsi]
0x1c0026ca1  movzx   r8d, ax
0x1c0026ca5  inc     r8d
0x1c0026ca8  cmp     r8d, edx
0x1c0026cab  lea     eax, [rdx-1]
0x1c0026cae  cmovb   eax, r8d
0x1c0026cb2  mov     edx, eax
0x1c0026cb4  mov     rax, [rsi+20h]
0x1c0026cb8  mov     rdi, [rax+rdx*8]
0x1c0026cbc  cmp     [rdi+70h], r12b
0x1c0026cc0  jnz     short loc_1C0026CCD
0x1c0026cc2  mov     rdx, rdi
0x1c0026cc5  mov     rcx, rsi
0x1c0026cc8  call    PplpLazyInitializeLookasideList
0x1c0026ccd  inc     dword ptr [rdi+1Ch]
0x1c0026cd0  mov     rcx, rdi; SListHead
0x1c0026cd3  call    cs:__imp_ExQueryDepthSList
0x1c0026cda  nop     dword ptr [rax+rax+00h]
0x1c0026cdf  cmp     ax, [rdi+10h]
0x1c0026ce3  jnb     short loc_1C0026D4C
0x1c0026ce5  mov     rdx, rbx; ListEntry
0x1c0026ce8  mov     rcx, rdi; ListHead
0x1c0026ceb  call    cs:__imp_ExpInterlockedPushEntrySList
0x1c0026cf2  nop     dword ptr [rax+rax+00h]
0x1c0026cf7  nop
0x1c0026cf8  jmp     loc_1C0013F93
0x1c0026cfd  mov     eax, gs:1A4h
0x1c0026d05  mov     rcx, cs:qword_1C0074330
0x1c0026d0c  lea     r8d, [rax+1]
0x1c0026d10  mov     edx, [rcx]
0x1c0026d12  cmp     r8d, edx
0x1c0026d15  lea     eax, [rdx-1]
0x1c0026d18  cmovb   eax, r8d
0x1c0026d1c  mov     edx, eax
0x1c0026d1e  mov     rax, [rcx+20h]
0x1c0026d22  mov     rdi, [rax+rdx*8]
0x1c0026d26  cmp     [rdi+70h], r12b
0x1c0026d2a  jnz     short loc_1C0026D34
0x1c0026d2c  mov     rdx, rdi
0x1c0026d2f  call    PplpLazyInitializeLookasideList
0x1c0026d34  inc     dword ptr [rdi+1Ch]
0x1c0026d37  mov     rcx, rdi; SListHead
0x1c0026d3a  call    cs:__imp_ExQueryDepthSList
0x1c0026d41  nop     dword ptr [rax+rax+00h]
0x1c0026d46  cmp     ax, [rdi+10h]
0x1c0026d4a  jb      short loc_1C0026CE5
0x1c0026d4c  mov     rax, [rdi+38h]
0x1c0026d50  mov     rdx, rdi
0x1c0026d53  inc     dword ptr [rdi+20h]
0x1c0026d56  mov     rcx, rbx
0x1c0026d59  call    cs:__guard_dispatch_icall_fptr
0x1c0026d5f  nop
0x1c0026d60  jmp     loc_1C0013F93
```
