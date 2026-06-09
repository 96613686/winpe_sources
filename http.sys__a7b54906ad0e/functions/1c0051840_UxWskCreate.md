# UxWskCreate

- ea: `0x1c0051840`
- end: `0x1c0051b57`
- name: `UxWskCreate`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0056320`

## callees

- `0x1c0001118`
- `0x1c000a178`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c0051840`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00518ef`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0051a3d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0051aac`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c00518ef`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0051a3d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0051aac`
- `ntoskrnl!IoAllocateIrp` at `0x1c00519cb`
- `ntoskrnl!IoAllocateIrp` at `0x1c00519cb`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c005187e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00519fc`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c005187e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c00519fc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c005198c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0051aee`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c005198c`
- `ntoskrnl!KeInitializeSpinLock` at `0x1c0051aee`

## pseudocode

```c
__int64 __fastcall UxWskCreate(__int64 a1, PSLIST_ENTRY *a2, _QWORD *a3, _QWORD *a4)
{
  bool v5; // zf
  _QWORD *v6; // r14
  __int64 v9; // rbx
  unsigned int v10; // r11d
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rcx
  unsigned int v14; // r8d
  unsigned int v15; // eax
  PSLIST_ENTRY v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 (__fastcall *v20)(__int64, __int64, __int64, __int64); // rax
  unsigned int v21; // edi
  PIRP Irp; // rax
  __int64 v23; // r14
  unsigned int v24; // r8d
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdi
  PSLIST_ENTRY v29; // rax
  unsigned int v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdi

  v5 = UxCompactMode == 0;
  v6 = a3;
  *a2 = 0;
  if ( v5 )
  {
    v13 = qword_1C00745D0;
    v14 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v15 = *(_DWORD *)qword_1C00745D0 - 1;
    if ( v14 < *(_DWORD *)qword_1C00745D0 )
      v15 = v14;
    v12 = *(_QWORD *)(*(_QWORD *)(qword_1C00745D0 + 32) + 8LL * v15);
    if ( !*(_BYTE *)(v12 + 112) )
      goto LABEL_9;
  }
  else
  {
    v9 = qword_1C00745D0;
    v10 = KeGetCurrentNodeNumber() + 1;
    v11 = (unsigned int)(*(_DWORD *)v9 - 1);
    if ( v10 < *(_DWORD *)v9 )
      v11 = v10;
    v12 = *(_QWORD *)(*(_QWORD *)(v9 + 32) + 8 * v11);
    if ( !*(_BYTE *)(v12 + 112) )
    {
      v13 = v9;
LABEL_9:
      PplpLazyInitializeLookasideList(v13, v12);
    }
  }
  ++*(_DWORD *)(v12 + 20);
  v16 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v12);
  if ( !v16 )
  {
    v17 = *(unsigned int *)(v12 + 40);
    v18 = *(unsigned int *)(v12 + 44);
    v19 = *(unsigned int *)(v12 + 36);
    v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v12 + 48);
    ++*(_DWORD *)(v12 + 24);
    v16 = (PSLIST_ENTRY)v20(v19, v18, v17, v12);
  }
  if ( v16 )
  {
    LODWORD(v16[2].Next) = 1129606229;
    HIDWORD(v16[2].Next) = 1;
    memset(&v16[2].Next + 1, 0, 0x1F8u);
    *((_BYTE *)&v16[12].Next + 12) = 1;
    v16[27].Next = 0;
    v16[28].Next = 0;
    *(struct _SLIST_ENTRY *)((char *)&v16[2] + 8) = 0;
    *((_QWORD *)&v16[3].Next + 1) = 0;
    *((_DWORD *)&v16[3].Next + 2) = 1;
    *((_QWORD *)&v16[1].Next + 1) = v16 + 1;
    v16[1].Next = v16 + 1;
    KeInitializeSpinLock((PKSPIN_LOCK)&v16[7].Next + 1);
    v16[15].Next = 0;
    *((_QWORD *)&v16[8].Next + 1) = v16 + 8;
    v16[8].Next = v16 + 8;
    LODWORD(v16[32].Next) = 2;
    *((_QWORD *)&v16[13].Next + 1) = a1;
    if ( a1 )
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
    Irp = IoAllocateIrp(1, 0);
    v16[6].Next = (struct _SLIST_ENTRY *)Irp;
    if ( !Irp )
      goto LABEL_17;
    if ( UxCompactMode )
    {
      v23 = qword_1C0074330;
      v24 = KeGetCurrentNodeNumber() + 1;
      v25 = *(_DWORD *)v23 - 1;
      if ( v24 < *(_DWORD *)v23 )
        v25 = v24;
      v26 = v25;
      v27 = *(_QWORD *)(v23 + 32);
      v28 = *(_QWORD *)(v27 + 8 * v26);
      if ( !*(_BYTE *)(v28 + 112) )
        PplpLazyInitializeLookasideList(v23, *(_QWORD *)(v27 + 8 * v26));
      ++*(_DWORD *)(v28 + 20);
      v29 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v28);
      if ( !v29 )
      {
        ++*(_DWORD *)(v28 + 24);
        v29 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v28 + 48))(
                              *(unsigned int *)(v28 + 36),
                              *(unsigned int *)(v28 + 44),
                              *(unsigned int *)(v28 + 40),
                              v28);
      }
      v6 = a3;
    }
    else
    {
      v30 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v31 = *(_DWORD *)qword_1C0074330 - 1;
      if ( v30 < *(_DWORD *)qword_1C0074330 )
        v31 = v30;
      v32 = v31;
      v33 = *(_QWORD *)(qword_1C0074330 + 32);
      v34 = *(_QWORD *)(v33 + 8 * v32);
      if ( !*(_BYTE *)(v34 + 112) )
        PplpLazyInitializeLookasideList(qword_1C0074330, *(_QWORD *)(v33 + 8 * v32));
      ++*(_DWORD *)(v34 + 20);
      v29 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v34);
      if ( !v29 )
      {
        ++*(_DWORD *)(v34 + 24);
        v29 = (PSLIST_ENTRY)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v34 + 48))(
                              *(unsigned int *)(v34 + 36),
                              *(unsigned int *)(v34 + 44),
                              *(unsigned int *)(v34 + 40),
                              v34);
      }
    }
    *((_QWORD *)&v16[6].Next + 1) = v29;
    if ( v29 )
    {
      *((_QWORD *)&v16[4].Next + 1) = 0;
      v21 = 0;
      KeInitializeSpinLock((PKSPIN_LOCK)&v16[4]);
      *((_QWORD *)&v16[2].Next + 1) = *a4;
      v16[3].Next = (struct _SLIST_ENTRY *)&UcHttpDispatch;
      *((_DWORD *)&v16[3].Next + 2) = 3;
      *a4 = 0;
      _InterlockedIncrement((volatile signed __int32 *)&v16[2].Next + 1);
      *a2 = v16;
      *v6 = UxTlDispatch;
      v16 = 0;
    }
    else
    {
LABEL_17:
      v21 = -1073741670;
    }
    if ( v16 )
      UxTlCleanupConnection(v16, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v21;
}

```

## disassembly

```asm
0x1c0051840  mov     [rsp+arg_0], rbx
0x1c0051845  mov     [rsp+arg_8], rbp
0x1c005184a  mov     [rsp+arg_10], r8
0x1c005184f  push    rdi
0x1c0051850  push    r12
0x1c0051852  push    r13
0x1c0051854  push    r14
0x1c0051856  push    r15
0x1c0051858  sub     rsp, 30h
0x1c005185c  xor     r15d, r15d
0x1c005185f  mov     r13, r9
0x1c0051862  cmp     cs:UxCompactMode, r15b
0x1c0051869  mov     r14, r8
0x1c005186c  mov     r12, rdx
0x1c005186f  mov     [rdx], r15
0x1c0051872  mov     rbp, rcx
0x1c0051875  jz      short loc_1C00518B2
0x1c0051877  mov     rbx, cs:qword_1C00745D0
0x1c005187e  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0051885  nop     dword ptr [rax+rax+00h]
0x1c005188a  mov     r10d, [rbx]
0x1c005188d  movzx   r11d, ax
0x1c0051891  mov     rax, [rbx+20h]
0x1c0051895  inc     r11d
0x1c0051898  cmp     r11d, r10d
0x1c005189b  lea     edx, [r10-1]
0x1c005189f  cmovb   edx, r11d
0x1c00518a3  mov     rdi, [rax+rdx*8]
0x1c00518a7  cmp     [rdi+70h], r15b
0x1c00518ab  jnz     short loc_1C00518E9
0x1c00518ad  mov     rcx, rbx
0x1c00518b0  jmp     short loc_1C00518E1
0x1c00518b2  mov     eax, gs:1A4h
0x1c00518ba  mov     rcx, cs:qword_1C00745D0
0x1c00518c1  lea     r8d, [rax+1]
0x1c00518c5  mov     edx, [rcx]
0x1c00518c7  cmp     r8d, edx
0x1c00518ca  lea     eax, [rdx-1]
0x1c00518cd  cmovb   eax, r8d
0x1c00518d1  mov     edx, eax
0x1c00518d3  mov     rax, [rcx+20h]
0x1c00518d7  mov     rdi, [rax+rdx*8]
0x1c00518db  cmp     [rdi+70h], r15b
0x1c00518df  jnz     short loc_1C00518E9
0x1c00518e1  mov     rdx, rdi
0x1c00518e4  call    PplpLazyInitializeLookasideList
0x1c00518e9  inc     dword ptr [rdi+14h]
0x1c00518ec  mov     rcx, rdi; ListHead
0x1c00518ef  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c00518f6  nop     dword ptr [rax+rax+00h]
0x1c00518fb  mov     rbx, rax
0x1c00518fe  test    rax, rax
0x1c0051901  jnz     short loc_1C0051920
0x1c0051903  mov     r8d, [rdi+28h]
0x1c0051907  mov     r9, rdi
0x1c005190a  mov     edx, [rdi+2Ch]
0x1c005190d  mov     ecx, [rdi+24h]
0x1c0051910  mov     rax, [rdi+30h]
0x1c0051914  inc     dword ptr [rdi+18h]
0x1c0051917  call    cs:__guard_dispatch_icall_fptr
0x1c005191d  mov     rbx, rax
0x1c0051920  test    rbx, rbx
0x1c0051923  jnz     short loc_1C005192F
0x1c0051925  mov     edi, 0C000009Ah
0x1c005192a  jmp     loc_1C0051B3C
0x1c005192f  lea     r15, [rbx+28h]
0x1c0051933  mov     dword ptr [rbx+20h], 43546C55h
0x1c005193a  mov     rcx, r15; void *
0x1c005193d  mov     dword ptr [rbx+24h], 1
0x1c0051944  xor     edx, edx; Val
0x1c0051946  mov     r8d, 1F8h; Size
0x1c005194c  call    memset
0x1c0051951  mov     byte ptr [rbx+0CCh], 1
0x1c0051958  lea     rcx, [rbx+78h]; SpinLock
0x1c005195c  xor     eax, eax
0x1c005195e  xor     edi, edi
0x1c0051960  mov     [rbx+1B0h], rdi
0x1c0051967  xorps   xmm0, xmm0
0x1c005196a  mov     [rbx+1C0h], rdi
0x1c0051971  movups  xmmword ptr [r15], xmm0
0x1c0051975  mov     [r15+10h], rax
0x1c0051979  lea     rax, [rbx+10h]
0x1c005197d  mov     dword ptr [r15+10h], 1
0x1c0051985  mov     [rax+8], rax
0x1c0051989  mov     [rax], rax
0x1c005198c  call    cs:__imp_KeInitializeSpinLock
0x1c0051993  nop     dword ptr [rax+rax+00h]
0x1c0051998  mov     [rbx+0F0h], rdi
0x1c005199f  lea     rax, [rbx+80h]
0x1c00519a6  mov     [rax+8], rax
0x1c00519aa  mov     [rax], rax
0x1c00519ad  mov     dword ptr [rbx+200h], 2
0x1c00519b7  mov     [rbx+0D8h], rbp
0x1c00519be  test    rbp, rbp
0x1c00519c1  jz      short loc_1C00519C7
0x1c00519c3  lock inc dword ptr [rbp+4]
0x1c00519c7  xor     edx, edx; ChargeQuota
0x1c00519c9  mov     cl, 1; StackSize
0x1c00519cb  call    cs:__imp_IoAllocateIrp
0x1c00519d2  nop     dword ptr [rax+rax+00h]
0x1c00519d7  xor     ebp, ebp
0x1c00519d9  mov     [rbx+60h], rax
0x1c00519dd  test    rax, rax
0x1c00519e0  jnz     short loc_1C00519EC
0x1c00519e2  mov     edi, 0C000009Ah
0x1c00519e7  jmp     loc_1C0051B2D
0x1c00519ec  cmp     cs:UxCompactMode, bpl
0x1c00519f3  jz      short loc_1C0051A6F
0x1c00519f5  mov     r14, cs:qword_1C0074330
0x1c00519fc  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0051a03  nop     dword ptr [rax+rax+00h]
0x1c0051a08  mov     edx, [r14]
0x1c0051a0b  movzx   r8d, ax
0x1c0051a0f  inc     r8d
0x1c0051a12  cmp     r8d, edx
0x1c0051a15  lea     eax, [rdx-1]
0x1c0051a18  cmovb   eax, r8d
0x1c0051a1c  mov     edx, eax
0x1c0051a1e  mov     rax, [r14+20h]
0x1c0051a22  mov     rdi, [rax+rdx*8]
0x1c0051a26  cmp     [rdi+70h], bpl
0x1c0051a2a  jnz     short loc_1C0051A37
0x1c0051a2c  mov     rdx, rdi
0x1c0051a2f  mov     rcx, r14
0x1c0051a32  call    PplpLazyInitializeLookasideList
0x1c0051a37  inc     dword ptr [rdi+14h]
0x1c0051a3a  mov     rcx, rdi; ListHead
0x1c0051a3d  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0051a44  nop     dword ptr [rax+rax+00h]
0x1c0051a49  test    rax, rax
0x1c0051a4c  jnz     short loc_1C0051A68
0x1c0051a4e  inc     dword ptr [rdi+18h]
0x1c0051a51  mov     r9, rdi
0x1c0051a54  mov     edx, [rdi+2Ch]
0x1c0051a57  mov     rax, [rdi+30h]
0x1c0051a5b  mov     r8d, [rdi+28h]
0x1c0051a5f  mov     ecx, [rdi+24h]
0x1c0051a62  call    cs:__guard_dispatch_icall_fptr
0x1c0051a68  mov     r14, [rsp+58h+arg_10]
0x1c0051a6d  jmp     short loc_1C0051AD7
0x1c0051a6f  mov     eax, gs:1A4h
0x1c0051a77  mov     rcx, cs:qword_1C0074330
0x1c0051a7e  lea     r8d, [rax+1]
0x1c0051a82  mov     edx, [rcx]
0x1c0051a84  cmp     r8d, edx
0x1c0051a87  lea     eax, [rdx-1]
0x1c0051a8a  cmovb   eax, r8d
0x1c0051a8e  mov     edx, eax
0x1c0051a90  mov     rax, [rcx+20h]
0x1c0051a94  mov     rdi, [rax+rdx*8]
0x1c0051a98  cmp     [rdi+70h], bpl
0x1c0051a9c  jnz     short loc_1C0051AA6
0x1c0051a9e  mov     rdx, rdi
0x1c0051aa1  call    PplpLazyInitializeLookasideList
0x1c0051aa6  inc     dword ptr [rdi+14h]
0x1c0051aa9  mov     rcx, rdi; ListHead
0x1c0051aac  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0051ab3  nop     dword ptr [rax+rax+00h]
0x1c0051ab8  test    rax, rax
0x1c0051abb  jnz     short loc_1C0051AD7
0x1c0051abd  inc     dword ptr [rdi+18h]
0x1c0051ac0  mov     r9, rdi
0x1c0051ac3  mov     edx, [rdi+2Ch]
0x1c0051ac6  mov     rax, [rdi+30h]
0x1c0051aca  mov     r8d, [rdi+28h]
0x1c0051ace  mov     ecx, [rdi+24h]
0x1c0051ad1  call    cs:__guard_dispatch_icall_fptr
0x1c0051ad7  mov     [rbx+68h], rax
0x1c0051adb  test    rax, rax
0x1c0051ade  jz      loc_1C00519E2
0x1c0051ae4  lea     rcx, [rbx+40h]; SpinLock
0x1c0051ae8  mov     [rbx+48h], rbp
0x1c0051aec  mov     edi, ebp
0x1c0051aee  call    cs:__imp_KeInitializeSpinLock
0x1c0051af5  nop     dword ptr [rax+rax+00h]
0x1c0051afa  mov     rax, [r13+0]
0x1c0051afe  mov     [r15], rax
0x1c0051b01  lea     rax, UcHttpDispatch
0x1c0051b08  mov     [r15+8], rax
0x1c0051b0c  mov     dword ptr [r15+10h], 3
0x1c0051b14  mov     [r13+0], rbp
0x1c0051b18  lock inc dword ptr [rbx+24h]
0x1c0051b1c  lea     rax, UxTlDispatch
0x1c0051b23  mov     [r12], rbx
0x1c0051b27  mov     [r14], rax
0x1c0051b2a  mov     rbx, rbp
0x1c0051b2d  test    rbx, rbx
0x1c0051b30  jz      short loc_1C0051B3C
0x1c0051b32  xor     edx, edx
0x1c0051b34  mov     rcx, rbx
0x1c0051b37  call    UxTlCleanupConnection
0x1c0051b3c  mov     rbx, [rsp+58h+arg_0]
0x1c0051b41  mov     eax, edi
0x1c0051b43  mov     rbp, [rsp+58h+arg_8]
0x1c0051b48  add     rsp, 30h
0x1c0051b4c  pop     r15
0x1c0051b4e  pop     r14
0x1c0051b50  pop     r13
0x1c0051b52  pop     r12
0x1c0051b54  pop     rdi
0x1c0051b55  retn
```
