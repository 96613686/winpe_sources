# VmbusTlXPartProcessNewConnection

- ea: `0x140025280`
- end: `0x14002569e`
- name: `VmbusTlXPartProcessNewConnection`
- size: `1054`
- prototype: `void __fastcall(__int64, __int64, void *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1400238d0`

## callees

- `0x140001350`
- `0x140009df0`
- `0x14000a048`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x1400187ac`
- `0x140018a88`
- `0x14001bd20`
- `0x140025280`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025322`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025322`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140025316`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140025316`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400255c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025671`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400255c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025671`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400252ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400252ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400255ae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002565d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400255ae`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002565d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140025300`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140025300`
- `ntoskrnl!ObfReferenceObject` at `0x1400253d4`
- `ntoskrnl!ObfReferenceObject` at `0x1400253d4`

## pseudocode

```c
void __fastcall VmbusTlXPartProcessNewConnection(__int64 a1, __int64 a2, void *a3, __int64 a4)
{
  __int64 v4; // r12
  char v7; // di
  int v8; // eax
  PVOID v9; // rbx
  int v10; // esi
  char v11; // r15
  GUID *v12; // r9
  __int64 v13; // r8
  int v14; // edx
  PVOID v15; // rsi
  __int64 v16; // rcx
  int v17; // edi
  __int64 (__fastcall *v18)(__int64, PVOID); // rax
  __int64 v19; // rax
  void (__fastcall *v20)(PVOID); // rax
  __int64 v21; // rax
  void (__fastcall *v22)(PVOID); // rax
  PVOID Entry; // [rsp+40h] [rbp-79h] BYREF
  PVOID Object; // [rsp+48h] [rbp-71h]
  __int64 v25; // [rsp+50h] [rbp-69h]
  _OWORD v26[2]; // [rsp+58h] [rbp-61h] BYREF
  GUID v27; // [rsp+78h] [rbp-41h]
  int v28; // [rsp+88h] [rbp-31h]
  GUID v29; // [rsp+90h] [rbp-29h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-19h] BYREF
  GUID v31; // [rsp+B0h] [rbp-9h] BYREF

  v4 = *(_QWORD *)(a1 + 200);
  memset(v26, 0, sizeof(v26));
  Object = a3;
  v27 = 0;
  v25 = a2;
  v29 = 0;
  Entry = 0;
  v28 = 0;
  v31 = HV_GUID_ZERO;
  v30 = 0;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  v7 = *(_BYTE *)(v4 + 120);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 16));
  KeLeaveCriticalRegion();
  if ( !v7 )
    return;
  v8 = VmbusTlCreateObject(7u, 112, &Entry);
  v9 = Entry;
  v10 = v8;
  v11 = 1;
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v12 = (GUID *)(a1 + 232);
      v13 = (unsigned int)v8;
      v14 = 1025;
LABEL_29:
      HvsocketTraceGuidError((const int *)"VmbusTlXPartProcessNewConnection", v14, v13, (__int64)v12);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  *((_QWORD *)Entry + 10) = VmbusTlXPartDestroyChannelInfo;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlXPartProcessNewConnection",
      1030,
      (__int64)v9,
      *((_QWORD *)v9 + 1),
      (const int *)"Reference object");
  if ( _InterlockedIncrement64((volatile signed __int64 *)v9 + 1) <= 1 )
    __fastfail(0xEu);
  v15 = Object;
  ObfReferenceObject(Object);
  v16 = v25;
  *((_QWORD *)v9 + 12) = v25;
  *((_QWORD *)v9 + 13) = v15;
  v17 = *(_BYTE *)(a4 + 60) != 0;
  if ( !*(_BYTE *)(a4 + 61) )
  {
    v18 = *(__int64 (__fastcall **)(__int64, PVOID))(a1 + 480);
    if ( v18 )
    {
      v10 = v18(v16, v15);
      if ( v10 < 0 )
      {
        if ( (unsigned int)dword_140013058 <= 2 )
          goto LABEL_30;
        v12 = (GUID *)(a1 + 232);
        v14 = 1057;
LABEL_28:
        v13 = (unsigned int)v10;
        goto LABEL_29;
      }
    }
    if ( !*(_BYTE *)(a4 + 61) )
    {
      v29 = HV_GUID_CHILDREN;
LABEL_25:
      v10 = VmbusTlProcessNewConnection(
              v4,
              (__int64)v9,
              (__int64)&v29,
              (__int64)&HV_GUID_PARENT,
              (__int64)&v31,
              a4,
              (UUID *)(a4 + 16),
              v17);
      if ( v10 >= 0 || (unsigned int)dword_140013058 <= 2 )
        goto LABEL_30;
      v12 = &v29;
      v14 = 1117;
      goto LABEL_28;
    }
  }
  v17 |= 4u;
  if ( *(int *)(a4 + 62) < 1 )
  {
    if ( (int)HvSocketFindPassthruPartition(v4, v26) < 0 )
    {
      v13 = 3221225485LL;
      v10 = -1073741811;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v12 = (GUID *)(a1 + 232);
        v14 = 1097;
        goto LABEL_29;
      }
      goto LABEL_30;
    }
    goto LABEL_21;
  }
  v30 = *(_OWORD *)(a4 + 66);
  if ( (int)HvSocketLookupSystemId(v4, (__int64)&v30, (__int64)v26) >= 0 )
  {
    v17 |= 8u;
LABEL_21:
    v31 = (GUID)v26[0];
    v29 = v27;
    goto LABEL_25;
  }
  v13 = 3221225485LL;
  v10 = -1073741811;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v12 = (GUID *)&v30;
    v14 = 1083;
    goto LABEL_29;
  }
LABEL_30:
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlXPartProcessNewConnection",
      1121,
      (__int64)v9,
      *((_QWORD *)v9 + 1),
      (const int *)"Dereference object");
  v19 = _InterlockedDecrement64((volatile signed __int64 *)v9 + 1);
  if ( v19 > 0 )
  {
    v11 = 0;
  }
  else
  {
    if ( v19 )
      __fastfail(0xEu);
    v20 = (void (__fastcall *)(PVOID))*((_QWORD *)v9 + 10);
    if ( v20 )
      v20(v9);
    if ( *((_DWORD *)v9 + 22) == 1 )
    {
      ExFreePoolWithTag(v9, 0x69706E56u);
    }
    else if ( *((_DWORD *)v9 + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v9 + 12), v9);
    }
  }
  if ( v10 < 0 && v9 && !v11 )
  {
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlXPartProcessNewConnection",
        1129,
        (__int64)v9,
        *((_QWORD *)v9 + 1),
        (const int *)"Dereference object");
    v21 = _InterlockedDecrement64((volatile signed __int64 *)v9 + 1);
    if ( v21 <= 0 )
    {
      if ( v21 )
        __fastfail(0xEu);
      v22 = (void (__fastcall *)(PVOID))*((_QWORD *)v9 + 10);
      if ( v22 )
        v22(v9);
      if ( *((_DWORD *)v9 + 22) == 1 )
      {
        ExFreePoolWithTag(v9, 0x69706E56u);
      }
      else if ( *((_DWORD *)v9 + 22) == 2 )
      {
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v9 + 12), v9);
      }
    }
  }
}

```

## disassembly

```asm
0x140025280  push    rbp
0x140025282  push    rbx
0x140025283  push    rsi
0x140025284  push    rdi
0x140025285  push    r12
0x140025287  push    r13
0x140025289  push    r14
0x14002528b  push    r15
0x14002528d  lea     rbp, [rsp-1Fh]
0x140025292  sub     rsp, 0D8h
0x140025299  mov     rax, cs:__security_cookie
0x1400252a0  xor     rax, rsp
0x1400252a3  mov     [rbp+57h+var_50], rax
0x1400252a7  mov     r12, [rcx+0C8h]
0x1400252ae  xorps   xmm0, xmm0
0x1400252b1  movups  [rbp+57h+var_B8], xmm0
0x1400252b5  xor     eax, eax
0x1400252b7  mov     r14, r9
0x1400252ba  movups  [rbp+57h+var_A8], xmm0
0x1400252be  mov     [rbp+57h+Object], r8
0x1400252c2  mov     r13, rcx
0x1400252c5  movups  [rbp+57h+var_98], xmm0
0x1400252c9  mov     [rbp+57h+var_C0], rdx
0x1400252cd  movups  [rbp+57h+var_80], xmm0
0x1400252d1  mov     [rbp+57h+Entry], 0
0x1400252d9  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x1400252e0  mov     [rbp+57h+var_88], eax
0x1400252e3  xorps   xmm1, xmm1
0x1400252e6  movdqu  [rbp+57h+var_60], xmm0
0x1400252eb  movups  [rbp+57h+var_70], xmm1
0x1400252ef  call    cs:__imp_KeEnterCriticalRegion
0x1400252f6  nop     dword ptr [rax+rax+00h]
0x1400252fb  lea     rcx, [r12+10h]; FastMutex
0x140025300  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140025307  nop     dword ptr [rax+rax+00h]
0x14002530c  mov     dil, [r12+78h]
0x140025311  lea     rcx, [r12+10h]; FastMutex
0x140025316  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002531d  nop     dword ptr [rax+rax+00h]
0x140025322  call    cs:__imp_KeLeaveCriticalRegion
0x140025329  nop     dword ptr [rax+rax+00h]
0x14002532e  test    dil, dil
0x140025331  jz      loc_14002567D
0x140025337  mov     edx, 70h ; 'p'
0x14002533c  lea     r8, [rbp+57h+Entry]
0x140025340  lea     ecx, [rdx-69h]
0x140025343  call    VmbusTlCreateObject
0x140025348  mov     rbx, [rbp+57h+Entry]
0x14002534c  mov     esi, eax
0x14002534e  mov     r15d, 1
0x140025354  test    eax, eax
0x140025356  jns     short loc_14002537B
0x140025358  mov     ecx, cs:dword_140013058
0x14002535e  cmp     ecx, 2
0x140025361  jbe     loc_14002553D
0x140025367  lea     r9, [r13+0E8h]
0x14002536e  mov     r8d, eax
0x140025371  mov     edx, 401h
0x140025376  jmp     loc_140025531
0x14002537b  lea     rax, VmbusTlXPartDestroyChannelInfo
0x140025382  mov     [rbx+50h], rax
0x140025386  mov     eax, cs:dword_140013058
0x14002538c  cmp     eax, 5
0x14002538f  jbe     short loc_1400253B5
0x140025391  mov     r9, [rbx+8]
0x140025395  lea     rax, aReferenceObjec; "Reference object"
0x14002539c  mov     r8, rbx
0x14002539f  mov     [rsp+110h+var_F0], rax
0x1400253a4  mov     edx, 406h
0x1400253a9  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x1400253b0  call    HvsocketTraceReferenceCount
0x1400253b5  mov     rax, r15
0x1400253b8  lock xadd [rbx+8], rax
0x1400253be  add     rax, r15
0x1400253c1  cmp     rax, r15
0x1400253c4  jg      short loc_1400253CD
0x1400253c6  mov     ecx, 0Eh
0x1400253cb  int     29h; Win8: RtlFailFast(ecx)
0x1400253cd  mov     rsi, [rbp+57h+Object]
0x1400253d1  mov     rcx, rsi; Object
0x1400253d4  call    cs:__imp_ObfReferenceObject
0x1400253db  nop     dword ptr [rax+rax+00h]
0x1400253e0  mov     rcx, [rbp+57h+var_C0]
0x1400253e4  xor     edi, edi
0x1400253e6  mov     [rbx+60h], rcx
0x1400253ea  mov     [rbx+68h], rsi
0x1400253ee  cmp     [r14+3Ch], dil
0x1400253f2  setnz   dil
0x1400253f6  cmp     byte ptr [r14+3Dh], 0
0x1400253fb  jnz     short loc_140025442
0x1400253fd  mov     rax, [r13+1E0h]
0x140025404  test    rax, rax
0x140025407  jz      short loc_140025437
0x140025409  mov     rdx, rsi
0x14002540c  call    _guard_dispatch_icall
0x140025411  mov     esi, eax
0x140025413  test    eax, eax
0x140025415  jns     short loc_140025437
0x140025417  mov     eax, cs:dword_140013058
0x14002541d  cmp     eax, 2
0x140025420  jbe     loc_14002553D
0x140025426  lea     r9, [r13+0E8h]
0x14002542d  mov     edx, 421h
0x140025432  jmp     loc_14002552E
0x140025437  cmp     byte ptr [r14+3Dh], 0
0x14002543c  jz      loc_1400254D7
0x140025442  or      edi, 4
0x140025445  mov     rcx, r12
0x140025448  cmp     [r14+3Eh], r15d
0x14002544c  jl      short loc_140025494
0x14002544e  movups  xmm0, xmmword ptr [r14+42h]
0x140025453  lea     r8, [rbp+57h+var_B8]
0x140025457  lea     rdx, [rbp+57h+var_70]
0x14002545b  movdqu  [rbp+57h+var_70], xmm0
0x140025460  call    HvSocketLookupSystemId
0x140025465  test    eax, eax
0x140025467  js      short loc_14002546E
0x140025469  or      edi, 8
0x14002546c  jmp     short loc_1400254A1
0x14002546e  mov     eax, cs:dword_140013058
0x140025474  mov     r8d, 0C000000Dh
0x14002547a  mov     esi, r8d
0x14002547d  cmp     eax, 2
0x140025480  jbe     loc_14002553D
0x140025486  lea     r9, [rbp+57h+var_70]
0x14002548a  mov     edx, 43Bh
0x14002548f  jmp     loc_140025531
0x140025494  lea     rdx, [rbp+57h+var_B8]
0x140025498  call    HvSocketFindPassthruPartition
0x14002549d  test    eax, eax
0x14002549f  js      short loc_1400254B5
0x1400254a1  movups  xmm0, [rbp+57h+var_B8]
0x1400254a5  movups  xmm1, [rbp+57h+var_98]
0x1400254a9  movdqu  [rbp+57h+var_60], xmm0
0x1400254ae  movdqu  [rbp+57h+var_80], xmm1
0x1400254b3  jmp     short loc_1400254E3
0x1400254b5  mov     eax, cs:dword_140013058
0x1400254bb  mov     r8d, 0C000000Dh
0x1400254c1  mov     esi, r8d
0x1400254c4  cmp     eax, 2
0x1400254c7  jbe     short loc_14002553D
0x1400254c9  lea     r9, [r13+0E8h]
0x1400254d0  mov     edx, 449h
0x1400254d5  jmp     short loc_140025531
0x1400254d7  movups  xmm0, xmmword ptr cs:HV_GUID_CHILDREN.Data1
0x1400254de  movdqu  [rbp+57h+var_80], xmm0
0x1400254e3  mov     [rsp+110h+var_D8], edi
0x1400254e7  lea     rax, [r14+10h]
0x1400254eb  mov     [rsp+110h+var_E0], rax
0x1400254f0  lea     r9, HV_GUID_PARENT
0x1400254f7  lea     rax, [rbp+57h+var_60]
0x1400254fb  mov     [rsp+110h+var_E8], r14
0x140025500  lea     r8, [rbp+57h+var_80]
0x140025504  mov     [rsp+110h+var_F0], rax
0x140025509  mov     rdx, rbx
0x14002550c  mov     rcx, r12
0x14002550f  call    VmbusTlProcessNewConnection
0x140025514  mov     esi, eax
0x140025516  test    eax, eax
0x140025518  jns     short loc_14002553D
0x14002551a  mov     eax, cs:dword_140013058
0x140025520  cmp     eax, 2
0x140025523  jbe     short loc_14002553D
0x140025525  lea     r9, [rbp+57h+var_80]
0x140025529  mov     edx, 45Dh
0x14002552e  mov     r8d, esi
0x140025531  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x140025538  call    HvsocketTraceGuidError
0x14002553d  mov     eax, cs:dword_140013058
0x140025543  lea     r12, aDereferenceObj; "Dereference object"
0x14002554a  cmp     eax, 5
0x14002554d  jbe     short loc_14002556C
0x14002554f  mov     r9, [rbx+8]
0x140025553  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x14002555a  mov     r8, rbx
0x14002555d  mov     [rsp+110h+var_F0], r12
0x140025562  mov     edx, 461h
0x140025567  call    HvsocketTraceReferenceCount
0x14002556c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140025570  mov     rax, rdi
0x140025573  lock xadd [rbx+8], rax
0x140025579  add     rax, rdi
0x14002557c  mov     r14d, 69706E56h
0x140025582  test    rax, rax
0x140025585  jg      short loc_1400255D7
0x140025587  jnz     short loc_1400255D0
0x140025589  mov     rax, [rbx+50h]
0x14002558d  test    rax, rax
0x140025590  jz      short loc_14002559A
0x140025592  mov     rcx, rbx
0x140025595  call    _guard_dispatch_icall
0x14002559a  mov     ecx, [rbx+58h]
0x14002559d  sub     ecx, r15d
0x1400255a0  jz      short loc_1400255BC
0x1400255a2  cmp     ecx, r15d
0x1400255a5  jnz     short loc_1400255DA
0x1400255a7  mov     rcx, [rbx+60h]; Lookaside
0x1400255ab  mov     rdx, rbx; Entry
0x1400255ae  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400255b5  nop     dword ptr [rax+rax+00h]
0x1400255ba  jmp     short loc_1400255DA
0x1400255bc  mov     edx, r14d; Tag
0x1400255bf  mov     rcx, rbx; P
0x1400255c2  call    cs:__imp_ExFreePoolWithTag
0x1400255c9  nop     dword ptr [rax+rax+00h]
0x1400255ce  jmp     short loc_1400255DA
0x1400255d0  mov     ecx, 0Eh
0x1400255d5  int     29h; Win8: RtlFailFast(ecx)
0x1400255d7  xor     r15b, r15b
0x1400255da  test    esi, esi
0x1400255dc  jns     loc_14002567D
0x1400255e2  test    rbx, rbx
0x1400255e5  jz      loc_14002567D
0x1400255eb  test    r15b, r15b
0x1400255ee  jnz     loc_14002567D
0x1400255f4  mov     eax, cs:dword_140013058
0x1400255fa  cmp     eax, 5
0x1400255fd  jbe     short loc_14002561C
0x1400255ff  mov     r9, [rbx+8]
0x140025603  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x14002560a  mov     r8, rbx
0x14002560d  mov     [rsp+110h+var_F0], r12
0x140025612  mov     edx, 469h
0x140025617  call    HvsocketTraceReferenceCount
0x14002561c  mov     rax, rdi
0x14002561f  lock xadd [rbx+8], rax
0x140025625  add     rax, rdi
0x140025628  test    rax, rax
0x14002562b  jg      short loc_14002567D
0x14002562d  jz      short loc_140025638
0x14002562f  mov     ecx, 0Eh
0x140025634  int     29h; Win8: RtlFailFast(ecx)
0x140025636  jmp     short loc_14002567D
0x140025638  mov     rax, [rbx+50h]
0x14002563c  test    rax, rax
0x14002563f  jz      short loc_140025649
0x140025641  mov     rcx, rbx
0x140025644  call    _guard_dispatch_icall
0x140025649  mov     ecx, [rbx+58h]
0x14002564c  sub     ecx, 1
0x14002564f  jz      short loc_14002566B
0x140025651  cmp     ecx, 1
0x140025654  jnz     short loc_14002567D
0x140025656  mov     rcx, [rbx+60h]; Lookaside
0x14002565a  mov     rdx, rbx; Entry
0x14002565d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025664  nop     dword ptr [rax+rax+00h]
0x140025669  jmp     short loc_14002567D
0x14002566b  mov     edx, r14d; Tag
0x14002566e  mov     rcx, rbx; P
0x140025671  call    cs:__imp_ExFreePoolWithTag
0x140025678  nop     dword ptr [rax+rax+00h]
0x14002567d  mov     rcx, [rbp+57h+var_50]
0x140025681  xor     rcx, rsp; StackCookie
0x140025684  call    __security_check_cookie
0x140025689  add     rsp, 0D8h
0x140025690  pop     r15
0x140025692  pop     r14
0x140025694  pop     r13
0x140025696  pop     r12
0x140025698  pop     rdi
0x140025699  pop     rsi
0x14002569a  pop     rbx
0x14002569b  pop     rbp
0x14002569c  retn
```
