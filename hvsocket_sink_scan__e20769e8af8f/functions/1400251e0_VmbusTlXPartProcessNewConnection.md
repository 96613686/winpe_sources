# VmbusTlXPartProcessNewConnection

- ea: `0x1400251e0`
- end: `0x1400255fe`
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
- `0x1400251e0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025282`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140025282`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140025276`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140025276`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025522`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400255d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025522`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400255d1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002524f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002524f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002550e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400255bd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002550e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400255bd`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140025260`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140025260`
- `ntoskrnl!ObfReferenceObject` at `0x140025334`
- `ntoskrnl!ObfReferenceObject` at `0x140025334`

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
  __int64 v14; // rdx
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
  v8 = VmbusTlCreateObject(7, 112, &Entry);
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
      HvsocketTraceGuidError("VmbusTlXPartProcessNewConnection", v14, v13, v12);
      goto LABEL_30;
    }
    goto LABEL_30;
  }
  *((_QWORD *)Entry + 10) = VmbusTlXPartDestroyChannelInfo;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlXPartProcessNewConnection",
      1030,
      (_DWORD)v9,
      *((_QWORD *)v9 + 1),
      (__int64)"Reference object");
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
      v10 = VmbusTlProcessNewConnection(v4, v9, &v29, &HV_GUID_PARENT, &v31, a4, a4 + 16, v17);
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
  if ( (int)HvSocketLookupSystemId(v4, &v30, v26) >= 0 )
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
      (unsigned int)"VmbusTlXPartProcessNewConnection",
      1121,
      (_DWORD)v9,
      *((_QWORD *)v9 + 1),
      (__int64)"Dereference object");
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
        (unsigned int)"VmbusTlXPartProcessNewConnection",
        1129,
        (_DWORD)v9,
        *((_QWORD *)v9 + 1),
        (__int64)"Dereference object");
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
0x1400251e0  push    rbp
0x1400251e2  push    rbx
0x1400251e3  push    rsi
0x1400251e4  push    rdi
0x1400251e5  push    r12
0x1400251e7  push    r13
0x1400251e9  push    r14
0x1400251eb  push    r15
0x1400251ed  lea     rbp, [rsp-1Fh]
0x1400251f2  sub     rsp, 0D8h
0x1400251f9  mov     rax, cs:__security_cookie
0x140025200  xor     rax, rsp
0x140025203  mov     [rbp+57h+var_50], rax
0x140025207  mov     r12, [rcx+0C8h]
0x14002520e  xorps   xmm0, xmm0
0x140025211  movups  [rbp+57h+var_B8], xmm0
0x140025215  xor     eax, eax
0x140025217  mov     r14, r9
0x14002521a  movups  [rbp+57h+var_A8], xmm0
0x14002521e  mov     [rbp+57h+Object], r8
0x140025222  mov     r13, rcx
0x140025225  movups  [rbp+57h+var_98], xmm0
0x140025229  mov     [rbp+57h+var_C0], rdx
0x14002522d  movups  [rbp+57h+var_80], xmm0
0x140025231  mov     [rbp+57h+Entry], 0
0x140025239  movups  xmm0, xmmword ptr cs:HV_GUID_ZERO.Data1
0x140025240  mov     [rbp+57h+var_88], eax
0x140025243  xorps   xmm1, xmm1
0x140025246  movdqu  [rbp+57h+var_60], xmm0
0x14002524b  movups  [rbp+57h+var_70], xmm1
0x14002524f  call    cs:__imp_KeEnterCriticalRegion
0x140025256  nop     dword ptr [rax+rax+00h]
0x14002525b  lea     rcx, [r12+10h]; FastMutex
0x140025260  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140025267  nop     dword ptr [rax+rax+00h]
0x14002526c  mov     dil, [r12+78h]
0x140025271  lea     rcx, [r12+10h]; FastMutex
0x140025276  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002527d  nop     dword ptr [rax+rax+00h]
0x140025282  call    cs:__imp_KeLeaveCriticalRegion
0x140025289  nop     dword ptr [rax+rax+00h]
0x14002528e  test    dil, dil
0x140025291  jz      loc_1400255DD
0x140025297  mov     edx, 70h ; 'p'
0x14002529c  lea     r8, [rbp+57h+Entry]
0x1400252a0  lea     ecx, [rdx-69h]
0x1400252a3  call    VmbusTlCreateObject
0x1400252a8  mov     rbx, [rbp+57h+Entry]
0x1400252ac  mov     esi, eax
0x1400252ae  mov     r15d, 1
0x1400252b4  test    eax, eax
0x1400252b6  jns     short loc_1400252DB
0x1400252b8  mov     ecx, cs:dword_140013058
0x1400252be  cmp     ecx, 2
0x1400252c1  jbe     loc_14002549D
0x1400252c7  lea     r9, [r13+0E8h]
0x1400252ce  mov     r8d, eax
0x1400252d1  mov     edx, 401h
0x1400252d6  jmp     loc_140025491
0x1400252db  lea     rax, VmbusTlXPartDestroyChannelInfo
0x1400252e2  mov     [rbx+50h], rax
0x1400252e6  mov     eax, cs:dword_140013058
0x1400252ec  cmp     eax, 5
0x1400252ef  jbe     short loc_140025315
0x1400252f1  mov     r9, [rbx+8]
0x1400252f5  lea     rax, aReferenceObjec; "Reference object"
0x1400252fc  mov     r8, rbx
0x1400252ff  mov     [rsp+110h+var_F0], rax
0x140025304  mov     edx, 406h
0x140025309  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x140025310  call    HvsocketTraceReferenceCount
0x140025315  mov     rax, r15
0x140025318  lock xadd [rbx+8], rax
0x14002531e  add     rax, r15
0x140025321  cmp     rax, r15
0x140025324  jg      short loc_14002532D
0x140025326  mov     ecx, 0Eh
0x14002532b  int     29h; Win8: RtlFailFast(ecx)
0x14002532d  mov     rsi, [rbp+57h+Object]
0x140025331  mov     rcx, rsi; Object
0x140025334  call    cs:__imp_ObfReferenceObject
0x14002533b  nop     dword ptr [rax+rax+00h]
0x140025340  mov     rcx, [rbp+57h+var_C0]
0x140025344  xor     edi, edi
0x140025346  mov     [rbx+60h], rcx
0x14002534a  mov     [rbx+68h], rsi
0x14002534e  cmp     [r14+3Ch], dil
0x140025352  setnz   dil
0x140025356  cmp     byte ptr [r14+3Dh], 0
0x14002535b  jnz     short loc_1400253A2
0x14002535d  mov     rax, [r13+1E0h]
0x140025364  test    rax, rax
0x140025367  jz      short loc_140025397
0x140025369  mov     rdx, rsi
0x14002536c  call    _guard_dispatch_icall
0x140025371  mov     esi, eax
0x140025373  test    eax, eax
0x140025375  jns     short loc_140025397
0x140025377  mov     eax, cs:dword_140013058
0x14002537d  cmp     eax, 2
0x140025380  jbe     loc_14002549D
0x140025386  lea     r9, [r13+0E8h]
0x14002538d  mov     edx, 421h
0x140025392  jmp     loc_14002548E
0x140025397  cmp     byte ptr [r14+3Dh], 0
0x14002539c  jz      loc_140025437
0x1400253a2  or      edi, 4
0x1400253a5  mov     rcx, r12
0x1400253a8  cmp     [r14+3Eh], r15d
0x1400253ac  jl      short loc_1400253F4
0x1400253ae  movups  xmm0, xmmword ptr [r14+42h]
0x1400253b3  lea     r8, [rbp+57h+var_B8]
0x1400253b7  lea     rdx, [rbp+57h+var_70]
0x1400253bb  movdqu  [rbp+57h+var_70], xmm0
0x1400253c0  call    HvSocketLookupSystemId
0x1400253c5  test    eax, eax
0x1400253c7  js      short loc_1400253CE
0x1400253c9  or      edi, 8
0x1400253cc  jmp     short loc_140025401
0x1400253ce  mov     eax, cs:dword_140013058
0x1400253d4  mov     r8d, 0C000000Dh
0x1400253da  mov     esi, r8d
0x1400253dd  cmp     eax, 2
0x1400253e0  jbe     loc_14002549D
0x1400253e6  lea     r9, [rbp+57h+var_70]
0x1400253ea  mov     edx, 43Bh
0x1400253ef  jmp     loc_140025491
0x1400253f4  lea     rdx, [rbp+57h+var_B8]
0x1400253f8  call    HvSocketFindPassthruPartition
0x1400253fd  test    eax, eax
0x1400253ff  js      short loc_140025415
0x140025401  movups  xmm0, [rbp+57h+var_B8]
0x140025405  movups  xmm1, [rbp+57h+var_98]
0x140025409  movdqu  [rbp+57h+var_60], xmm0
0x14002540e  movdqu  [rbp+57h+var_80], xmm1
0x140025413  jmp     short loc_140025443
0x140025415  mov     eax, cs:dword_140013058
0x14002541b  mov     r8d, 0C000000Dh
0x140025421  mov     esi, r8d
0x140025424  cmp     eax, 2
0x140025427  jbe     short loc_14002549D
0x140025429  lea     r9, [r13+0E8h]
0x140025430  mov     edx, 449h
0x140025435  jmp     short loc_140025491
0x140025437  movups  xmm0, xmmword ptr cs:HV_GUID_CHILDREN.Data1
0x14002543e  movdqu  [rbp+57h+var_80], xmm0
0x140025443  mov     [rsp+110h+var_D8], edi
0x140025447  lea     rax, [r14+10h]
0x14002544b  mov     [rsp+110h+var_E0], rax
0x140025450  lea     r9, HV_GUID_PARENT
0x140025457  lea     rax, [rbp+57h+var_60]
0x14002545b  mov     [rsp+110h+var_E8], r14
0x140025460  lea     r8, [rbp+57h+var_80]
0x140025464  mov     [rsp+110h+var_F0], rax
0x140025469  mov     rdx, rbx
0x14002546c  mov     rcx, r12
0x14002546f  call    VmbusTlProcessNewConnection
0x140025474  mov     esi, eax
0x140025476  test    eax, eax
0x140025478  jns     short loc_14002549D
0x14002547a  mov     eax, cs:dword_140013058
0x140025480  cmp     eax, 2
0x140025483  jbe     short loc_14002549D
0x140025485  lea     r9, [rbp+57h+var_80]
0x140025489  mov     edx, 45Dh
0x14002548e  mov     r8d, esi
0x140025491  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x140025498  call    HvsocketTraceGuidError
0x14002549d  mov     eax, cs:dword_140013058
0x1400254a3  lea     r12, aDereferenceObj; "Dereference object"
0x1400254aa  cmp     eax, 5
0x1400254ad  jbe     short loc_1400254CC
0x1400254af  mov     r9, [rbx+8]
0x1400254b3  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x1400254ba  mov     r8, rbx
0x1400254bd  mov     [rsp+110h+var_F0], r12
0x1400254c2  mov     edx, 461h
0x1400254c7  call    HvsocketTraceReferenceCount
0x1400254cc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400254d0  mov     rax, rdi
0x1400254d3  lock xadd [rbx+8], rax
0x1400254d9  add     rax, rdi
0x1400254dc  mov     r14d, 69706E56h
0x1400254e2  test    rax, rax
0x1400254e5  jg      short loc_140025537
0x1400254e7  jnz     short loc_140025530
0x1400254e9  mov     rax, [rbx+50h]
0x1400254ed  test    rax, rax
0x1400254f0  jz      short loc_1400254FA
0x1400254f2  mov     rcx, rbx
0x1400254f5  call    _guard_dispatch_icall
0x1400254fa  mov     ecx, [rbx+58h]
0x1400254fd  sub     ecx, r15d
0x140025500  jz      short loc_14002551C
0x140025502  cmp     ecx, r15d
0x140025505  jnz     short loc_14002553A
0x140025507  mov     rcx, [rbx+60h]; Lookaside
0x14002550b  mov     rdx, rbx; Entry
0x14002550e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025515  nop     dword ptr [rax+rax+00h]
0x14002551a  jmp     short loc_14002553A
0x14002551c  mov     edx, r14d; Tag
0x14002551f  mov     rcx, rbx; P
0x140025522  call    cs:__imp_ExFreePoolWithTag
0x140025529  nop     dword ptr [rax+rax+00h]
0x14002552e  jmp     short loc_14002553A
0x140025530  mov     ecx, 0Eh
0x140025535  int     29h; Win8: RtlFailFast(ecx)
0x140025537  xor     r15b, r15b
0x14002553a  test    esi, esi
0x14002553c  jns     loc_1400255DD
0x140025542  test    rbx, rbx
0x140025545  jz      loc_1400255DD
0x14002554b  test    r15b, r15b
0x14002554e  jnz     loc_1400255DD
0x140025554  mov     eax, cs:dword_140013058
0x14002555a  cmp     eax, 5
0x14002555d  jbe     short loc_14002557C
0x14002555f  mov     r9, [rbx+8]
0x140025563  lea     rcx, aVmbustlxpartpr; "VmbusTlXPartProcessNewConnection"
0x14002556a  mov     r8, rbx
0x14002556d  mov     [rsp+110h+var_F0], r12
0x140025572  mov     edx, 469h
0x140025577  call    HvsocketTraceReferenceCount
0x14002557c  mov     rax, rdi
0x14002557f  lock xadd [rbx+8], rax
0x140025585  add     rax, rdi
0x140025588  test    rax, rax
0x14002558b  jg      short loc_1400255DD
0x14002558d  jz      short loc_140025598
0x14002558f  mov     ecx, 0Eh
0x140025594  int     29h; Win8: RtlFailFast(ecx)
0x140025596  jmp     short loc_1400255DD
0x140025598  mov     rax, [rbx+50h]
0x14002559c  test    rax, rax
0x14002559f  jz      short loc_1400255A9
0x1400255a1  mov     rcx, rbx
0x1400255a4  call    _guard_dispatch_icall
0x1400255a9  mov     ecx, [rbx+58h]
0x1400255ac  sub     ecx, 1
0x1400255af  jz      short loc_1400255CB
0x1400255b1  cmp     ecx, 1
0x1400255b4  jnz     short loc_1400255DD
0x1400255b6  mov     rcx, [rbx+60h]; Lookaside
0x1400255ba  mov     rdx, rbx; Entry
0x1400255bd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400255c4  nop     dword ptr [rax+rax+00h]
0x1400255c9  jmp     short loc_1400255DD
0x1400255cb  mov     edx, r14d; Tag
0x1400255ce  mov     rcx, rbx; P
0x1400255d1  call    cs:__imp_ExFreePoolWithTag
0x1400255d8  nop     dword ptr [rax+rax+00h]
0x1400255dd  mov     rcx, [rbp+57h+var_50]
0x1400255e1  xor     rcx, rsp; StackCookie
0x1400255e4  call    __security_check_cookie
0x1400255e9  add     rsp, 0D8h
0x1400255f0  pop     r15
0x1400255f2  pop     r14
0x1400255f4  pop     r13
0x1400255f6  pop     r12
0x1400255f8  pop     rdi
0x1400255f9  pop     rsi
0x1400255fa  pop     rbx
0x1400255fb  pop     rbp
0x1400255fc  retn
```
