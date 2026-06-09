# NbtOpenAddress

- ea: `0x1400031bc`
- end: `0x140003ba3`
- name: `NbtOpenAddress`
- size: `2535`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x140001ee4`
- `0x14004bd7c`

## callees

- `0x140001938`
- `0x1400031bc`
- `0x140003bac`
- `0x140003d04`
- `0x140004038`
- `0x140006e2c`
- `0x1400089c8`
- `0x140009600`
- `0x14000da94`
- `0x14001f6dc`
- `0x140030f80`
- `0x140031020`
- `0x140031440`
- `0x140041580`
- `0x1400439bc`
- `0x14004ffb0`
- `0x1400504dc`

## import_xrefs

- `ntoskrnl!ExInterlockedInsertTailList` at `0x140003491`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x140003491`
- `ntoskrnl!KeInitializeSpinLock` at `0x140003326`
- `ntoskrnl!KeInitializeSpinLock` at `0x140003326`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000342e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400034c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000358a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003aaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000342e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400034c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000358a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140003aaf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003422`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400034b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000357e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003aa3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003422`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400034b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000357e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140003aa3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000325d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000325d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003247`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140003247`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003270`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000360f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003629`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a34`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003270`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000360f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003629`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a1d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a34`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400032ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000353c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003556`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003758`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003772`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400039e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400039fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ada`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400032ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000353c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003556`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003758`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003772`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400037d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400039e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400039fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003865`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003865`
- `ntoskrnl!ExAllocatePool2` at `0x1400032eb`
- `ntoskrnl!ExAllocatePool2` at `0x1400032eb`

## pseudocode

```c
__int64 __fastcall NbtOpenAddress(__int64 *a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  int v5; // r14d
  int v6; // ebx
  __int16 v8; // r13
  _BYTE *v9; // rbp
  KIRQL v10; // r12
  int v11; // eax
  _QWORD *v12; // rdi
  NTSTATUS v13; // esi
  int v14; // ebx
  void *Pool2; // rax
  __int64 v16; // rdi
  __int64 ClientBlock; // rax
  __int64 v18; // rcx
  int v19; // r9d
  __int64 v20; // rsi
  __int64 v21; // r14
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  KIRQL v28; // dl
  __int64 v29; // rdx
  __int64 v31; // r14
  __int64 v32; // rcx
  __int64 v33; // r13
  int v34; // ecx
  char v35; // r12
  __int64 v36; // rax
  __int64 v37; // rsi
  __int64 v38; // rcx
  _QWORD *v39; // rax
  KIRQL v40; // dl
  KIRQL v41; // dl
  KIRQL v42; // dl
  int v43; // ecx
  int v44; // r9d
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int v49; // eax
  size_t v50; // r8
  void *v51; // rcx
  __int64 v52; // [rsp+28h] [rbp-70h]
  __int16 v53; // [rsp+40h] [rbp-58h]
  int v54; // [rsp+44h] [rbp-54h]
  _QWORD *v56; // [rsp+A8h] [rbp+10h] BYREF
  int NewIrql; // [rsp+B0h] [rbp+18h]

  v5 = *(unsigned __int16 *)(a2 + 2);
  v6 = 2130706432;
  if ( a3 )
    v6 = a3;
  v54 = *(unsigned __int16 *)(a2 + 2);
  NewIrql = v6;
  if ( v5 == 17 )
  {
    v8 = *(_WORD *)(a2 + 4);
    v9 = (_BYTE *)(a2 + 6);
LABEL_5:
    v53 = v8;
    if ( !memcmp("*", v9, 0x10u) && v8 != 1 )
    {
      v8 = 1;
      v53 = 1;
    }
    if ( *v9 == 42 && v5 == 17 )
    {
      *(_QWORD *)(v9 + 1) = 0;
      *(_DWORD *)(v9 + 9) = 0;
      *(_WORD *)(v9 + 13) = 0;
      v9[15] = 0;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    v10 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v56 = 0;
    v11 = FindInHashTable(qword_140039460, v9, Str2, &v56);
    v12 = v56;
    v13 = v11;
    if ( v11 < 0 )
      goto LABEL_8;
    v31 = v56[15];
    if ( !v31 )
    {
      v5 = v54;
LABEL_8:
      if ( v56 )
      {
        v46 = v56[10];
        v47 = *(_QWORD *)(a4 + 560);
        if ( (v46 & v47) != 0 )
        {
          v56[10] = v46 & ~v47;
        }
        else
        {
          v48 = v56[12];
          if ( (v48 & v47) != 0 )
            v56[12] = v48 & ~v47;
        }
      }
      KeReleaseSpinLock(&SpinLock, v10);
      v14 = -1073741670;
      Pool2 = (void *)ExAllocatePool2(64, 176, 1131700814);
      v16 = (__int64)Pool2;
      if ( !Pool2 )
        goto LABEL_27;
      memset(Pool2, 0, 0xB0u);
      *(_QWORD *)(v16 + 8) = v16;
      *(_QWORD *)v16 = v16;
      *(_QWORD *)(v16 + 32) = v16 + 24;
      *(_QWORD *)(v16 + 24) = v16 + 24;
      KeInitializeSpinLock((PKSPIN_LOCK)(v16 + 56));
      *(_DWORD *)(v16 + 48) = v5;
      *(_WORD *)(v16 + 52) = (v8 & 0xFFFD) != 0;
      *(_DWORD *)(v16 + 16) = 1919181889;
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *(_DWORD *)(v16 + 20),
          14,
          (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
          v16,
          *(_DWORD *)(v16 + 20),
          *(_DWORD *)(v16 + 20) + 1,
          79,
          (__int64)"minio\\netbt\\sys\\name.c");
      _InterlockedAdd((volatile signed __int32 *)(v16 + 20), 1u);
      ClientBlock = NbtAllocateClientBlock(v16, a4);
      v20 = ClientBlock;
      if ( !ClientBlock )
      {
        NTQueueToWorkerThread(v16 + 64, (unsigned int)DelayedFreeAddrObj, 0, v16, 0, 0, 0, 10);
        goto LABEL_27;
      }
      *(_DWORD *)(ClientBlock + 48) = v5;
      v21 = a5;
      *(_QWORD *)(ClientBlock + 24) = a5;
      if ( !v21 )
      {
LABEL_16:
        *a1 = v20;
        if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
          WPP_SF_qddds(
            *(_DWORD *)(v16 + 20),
            14,
            (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
            v16,
            *(_DWORD *)(v16 + 20),
            *(_DWORD *)(v16 + 20) + 1,
            134,
            (__int64)"minio\\netbt\\sys\\name.c");
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 20));
        v14 = NbtRegisterName(v18, NewIrql, (int)v9, v19, v20, v52, v8, a4);
        if ( v14 < 0 )
        {
          if ( v21 )
          {
            *(_QWORD *)(v20 + 24) = 0;
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v21 + 184) + 48LL) + 24LL) = 0;
          }
          ExReleaseResourceLite(&Resource);
          KeLeaveCriticalRegion();
          NbtDereferenceClient((PVOID)v20);
          NbtDereferenceAddress(v16, v25, 936, "minio\\netbt\\sys\\name.c");
          return (unsigned int)v14;
        }
        if ( v14 != 259 )
        {
          *(_BYTE *)(v20 + 273) = 1;
          *(_QWORD *)(v20 + 24) = 0;
        }
        if ( (BYTE11(xmmword_140038420) & 2) != 0 )
          WPP_SF_zDq(v23, 0, v24, (_DWORD)v9, v9[15], v20);
        ExInterlockedInsertTailList(&ListHead, (PLIST_ENTRY)v16, &SpinLock);
        NbtDereferenceAddress(v16, v26, 951, "minio\\netbt\\sys\\name.c");
LABEL_27:
        ExReleaseResourceLite(&Resource);
        KeLeaveCriticalRegion();
        if ( v14 >= 0 && *v9 != 42 && v9[15] == 32 )
        {
          ++*(_DWORD *)(a4 + 904);
          LOBYTE(v27) = 1;
          CheckSetWakeupPattern(a4, v9, v27, 0);
        }
        return (unsigned int)v14;
      }
      v14 = NTSetSharedAccess(v18, v21, v16);
      if ( v14 >= 0 )
      {
        v18 = *(_QWORD *)(*(_QWORD *)(v20 + 24) + 184LL);
        v22 = *(_QWORD *)(v18 + 48);
        *(_QWORD *)(v22 + 24) = v20;
        *(_QWORD *)(v22 + 32) = 1;
        goto LABEL_16;
      }
      NTQueueToWorkerThread(v16 + 64, (unsigned int)DelayedFreeAddrObj, 0, v16, 0, 0, 0, 10);
      *(_DWORD *)(v20 + 16) += 10;
      ExFreePoolWithTag((PVOID)v20, 0);
LABEL_36:
      ExReleaseResourceLite(&Resource);
      KeLeaveCriticalRegion();
      return (unsigned int)v14;
    }
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *(_DWORD *)(v31 + 20),
        14,
        (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
        v31,
        *(_DWORD *)(v31 + 20),
        *(_DWORD *)(v31 + 20) + 1,
        202,
        (__int64)"minio\\netbt\\sys\\name.c");
    _InterlockedIncrement((volatile signed __int32 *)(v31 + 20));
    KeReleaseSpinLock(&SpinLock, v10);
    v33 = a5;
    if ( a5 )
      v13 = NTCheckSharedAccess(v32, a5, v12[15]);
    LOBYTE(v56) = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    LOBYTE(NewIrql) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v31 + 56));
    if ( v6 != 2130706432 && (v12[9] & 2) != 0 )
      *((_DWORD *)v12 + 8) = v6;
    if ( v13 >= 0 )
      goto LABEL_47;
    if ( !(_BYTE)word_140039670 || (*(_QWORD *)(a4 + 560) & v12[10]) != 0 )
    {
      v49 = *(_DWORD *)(a4 + 728);
      v50 = 6;
      if ( v49 < 6 )
        v50 = v49;
      if ( !memcmp((char *)v12 + 174, (const void *)(a4 + 732), v50) )
      {
        if ( **(_QWORD **)(v31 + 24) == v31 + 24 )
          v13 = 0;
        if ( v13 < 0 )
          goto LABEL_34;
LABEL_47:
        v34 = *((_DWORD *)v12 + 18);
        if ( (v34 & 0x40) != 0 )
        {
          v51 = (void *)v12[14];
          if ( v51 )
          {
            v12[14] = 0;
            StopTimer(v51);
          }
          if ( *(_QWORD *)(v31 + 24) != v31 + 24 )
          {
            v14 = -1073741635;
            goto LABEL_35;
          }
          *((_DWORD *)v12 + 18) = v12[9] & 0xFFFFFF0F | 0x10;
          NbtCheckNameAddrTimer(v12);
          v35 = 1;
        }
        else
        {
          if ( (v53 & 0xFFFD) != 0 )
          {
            if ( (v34 & 4) == 0 )
              goto LABEL_34;
          }
          else if ( (v34 & 2) == 0 )
          {
            v13 = -1073741757;
          }
          v35 = 0;
          v14 = v13;
          if ( v13 < 0 )
            goto LABEL_35;
        }
        v36 = NbtAllocateClientBlock(v31, a4);
        v37 = v36;
        if ( v36 )
        {
          *(_QWORD *)(v36 + 24) = v33;
          *(_DWORD *)(v36 + 48) = v54;
          *a1 = v36;
          if ( v33 )
          {
            v38 = *(_QWORD *)(*(_QWORD *)(v33 + 184) + 48LL);
            *(_QWORD *)(v38 + 24) = v36;
            *(_QWORD *)(v38 + 32) = 1;
          }
          v39 = (_QWORD *)(v31 + 24);
          while ( 1 )
          {
            v39 = (_QWORD *)*v39;
            if ( v39 == (_QWORD *)(v31 + 24) )
              break;
            if ( v39 != (_QWORD *)v37 && v39[4] == a4 )
            {
              *(_BYTE *)(v31 + 54) = 1;
              goto LABEL_63;
            }
          }
          if ( *(_DWORD *)(a4 + 340) == 1 )
          {
            *((_DWORD *)v12 + 40) |= 1u;
          }
          else
          {
            v12[10] |= *(_QWORD *)(a4 + 560);
            if ( (v12[9] & 0x10) != 0 )
              v35 = 1;
          }
LABEL_63:
          if ( (v12[9] & 0x10) == 0 || v35 )
          {
            v41 = NewIrql;
            *(_QWORD *)(v37 + 24) = v33;
            KeReleaseSpinLock((PKSPIN_LOCK)(v31 + 56), v41);
            v42 = (unsigned __int8)v56;
            if ( v35 )
            {
              *(_BYTE *)(v37 + 274) = 0;
              KeReleaseSpinLock(&SpinLock, v42);
              v45 = NbtRegisterName(v43, 0, (int)v9, v44, v37, v52, v53, a4);
              v14 = v45;
              if ( v45 < 0 )
              {
                if ( v33 )
                {
                  *(_QWORD *)(v37 + 24) = 0;
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v33 + 184) + 48LL) + 24LL) = 0;
                }
                ExReleaseResourceLite(&Resource);
                KeLeaveCriticalRegion();
                NbtDereferenceClient((PVOID)v37);
                return (unsigned int)v14;
              }
              if ( v45 != 259 )
              {
                *(_BYTE *)(v37 + 273) = 1;
                *(_QWORD *)(v37 + 24) = 0;
              }
            }
            else
            {
              *(_BYTE *)(v37 + 274) = 1;
              KeReleaseSpinLock(&SpinLock, v42);
              v14 = 259;
            }
          }
          else
          {
            v40 = NewIrql;
            v14 = 0;
            *(_QWORD *)(v37 + 24) = 0;
            KeReleaseSpinLock((PKSPIN_LOCK)(v31 + 56), v40);
            KeReleaseSpinLock(&SpinLock, (KIRQL)v56);
            *(_BYTE *)(v37 + 274) = 0;
          }
          goto LABEL_27;
        }
        v14 = -1073741670;
        goto LABEL_35;
      }
      if ( (v12[9] & 0x40) == 0 )
      {
LABEL_34:
        v14 = -1073741757;
LABEL_35:
        v28 = NewIrql;
        *a1 = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)(v31 + 56), v28);
        KeReleaseSpinLock(&SpinLock, (KIRQL)v56);
        NbtDereferenceAddress(v31, v29, 1179, "minio\\netbt\\sys\\name.c");
        goto LABEL_36;
      }
    }
    v13 = 0;
    goto LABEL_47;
  }
  if ( v5 == 22 )
  {
    v8 = 2;
    v9 = (_BYTE *)(a2 + 4);
    goto LABEL_5;
  }
  return 3221225991LL;
}

```

## disassembly

```asm
0x1400031bc  mov     rax, rsp
0x1400031bf  mov     [rax+20h], rbx
0x1400031c3  mov     [rax+8], rcx
0x1400031c7  push    rbp
0x1400031c8  push    rsi
0x1400031c9  push    rdi
0x1400031ca  push    r12
0x1400031cc  push    r13
0x1400031ce  push    r14
0x1400031d0  push    r15
0x1400031d2  sub     rsp, 60h
0x1400031d6  movzx   r14d, word ptr [rdx+2]
0x1400031db  xor     edi, edi
0x1400031dd  test    r8d, r8d
0x1400031e0  mov     [rax-50h], rdi
0x1400031e4  mov     ebx, 7F000000h
0x1400031e9  mov     [rax-48h], rdi
0x1400031ed  cmovnz  ebx, r8d
0x1400031f1  mov     [rsp+98h+var_54], r14d
0x1400031f6  mov     [rsp+98h+NewIrql], ebx
0x1400031fd  mov     r15, r9
0x140003200  lea     eax, [rdi+2]
0x140003203  cmp     r14d, 11h
0x140003207  jnz     loc_140003789
0x14000320d  movzx   r13d, word ptr [rdx+4]
0x140003212  lea     rbp, [rdx+6]
0x140003216  mov     r8d, 10h; Size
0x14000321c  mov     dword ptr [rsp+98h+var_58], r13d
0x140003221  mov     rdx, rbp; Buf2
0x140003224  lea     rcx, asc_1400331A0; "*"
0x14000322b  call    memcmp
0x140003230  mov     esi, 1
0x140003235  test    eax, eax
0x140003237  jz      loc_140003876
0x14000323d  cmp     byte ptr [rbp+0], 2Ah ; '*'
0x140003241  jz      loc_1400038BC
0x140003247  call    cs:__imp_KeEnterCriticalRegion
0x14000324e  nop     dword ptr [rax+rax+00h]
0x140003253  mov     dl, sil; Wait
0x140003256  lea     rcx, Resource; Resource
0x14000325d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140003264  nop     dword ptr [rax+rax+00h]
0x140003269  lea     rcx, SpinLock; SpinLock
0x140003270  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003277  nop     dword ptr [rax+rax+00h]
0x14000327c  mov     r8, cs:Str2
0x140003283  lea     r9, [rsp+98h+arg_8]
0x14000328b  mov     rcx, cs:qword_140039460
0x140003292  mov     rdx, rbp
0x140003295  mov     r12b, al
0x140003298  mov     [rsp+98h+arg_8], rdi
0x1400032a0  call    FindInHashTable
0x1400032a5  mov     rdi, [rsp+98h+arg_8]
0x1400032ad  mov     esi, eax
0x1400032af  test    eax, eax
0x1400032b1  jns     loc_1400035B1
0x1400032b7  test    rdi, rdi
0x1400032ba  jnz     loc_14000388C
0x1400032c0  mov     dl, r12b; NewIrql
0x1400032c3  lea     rcx, SpinLock; SpinLock
0x1400032ca  call    cs:__imp_KeReleaseSpinLock
0x1400032d1  nop     dword ptr [rax+rax+00h]
0x1400032d6  mov     esi, 0B0h
0x1400032db  mov     r8d, 4374624Eh
0x1400032e1  mov     edx, esi
0x1400032e3  mov     ebx, 0C000009Ah
0x1400032e8  lea     ecx, [rsi-70h]
0x1400032eb  call    cs:__imp_ExAllocatePool2
0x1400032f2  nop     dword ptr [rax+rax+00h]
0x1400032f7  mov     rdi, rax
0x1400032fa  test    rax, rax
0x1400032fd  jz      loc_1400034AE
0x140003303  mov     r8d, esi; Size
0x140003306  xor     edx, edx; Val
0x140003308  mov     rcx, rax; void *
0x14000330b  call    memset
0x140003310  lea     rcx, [rdi+18h]
0x140003314  mov     [rdi+8], rdi
0x140003318  mov     [rdi], rdi
0x14000331b  mov     [rcx+8], rcx
0x14000331f  mov     [rcx], rcx
0x140003322  lea     rcx, [rdi+38h]; SpinLock
0x140003326  call    cs:__imp_KeInitializeSpinLock
0x14000332d  nop     dword ptr [rax+rax+00h]
0x140003332  mov     eax, 0FFFDh
0x140003337  mov     [rdi+30h], r14d
0x14000333b  mov     esi, 1
0x140003340  test    ax, r13w
0x140003344  jnz     loc_140003681
0x14000334a  xor     eax, eax
0x14000334c  mov     [rdi+34h], ax
0x140003350  mov     dword ptr [rdi+10h], 72646441h
0x140003357  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000335e  lea     r12, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140003365  jnz     loc_140003B09
0x14000336b  lock add [rdi+14h], esi
0x14000336f  mov     rdx, r15
0x140003372  mov     rcx, rdi
0x140003375  call    NbtAllocateClientBlock
0x14000337a  xor     edx, edx
0x14000337c  mov     rsi, rax
0x14000337f  test    rax, rax
0x140003382  jz      loc_140003689
0x140003388  mov     [rax+30h], r14d
0x14000338c  mov     r14, [rsp+98h+arg_20]
0x140003394  mov     [rax+18h], r14
0x140003398  test    r14, r14
0x14000339b  jz      short loc_1400033CF
0x14000339d  mov     r8, rdi
0x1400033a0  mov     rdx, r14
0x1400033a3  call    NTSetSharedAccess
0x1400033a8  xor     edx, edx
0x1400033aa  mov     ebx, eax
0x1400033ac  test    eax, eax
0x1400033ae  js      loc_140003833
0x1400033b4  mov     rax, [rsi+18h]
0x1400033b8  mov     rcx, [rax+0B8h]; int
0x1400033bf  mov     rax, [rcx+30h]
0x1400033c3  mov     [rax+18h], rsi
0x1400033c7  mov     qword ptr [rax+20h], 1
0x1400033cf  mov     rax, [rsp+98h+arg_0]
0x1400033d7  mov     [rax], rsi
0x1400033da  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400033e1  jnz     loc_140003B3D
0x1400033e7  lock inc dword ptr [rdi+14h]
0x1400033eb  mov     edx, [rsp+98h+NewIrql]; int
0x1400033f2  mov     r8, rbp; int
0x1400033f5  mov     [rsp+98h+var_60], r15; __int64
0x1400033fa  mov     word ptr [rsp+98h+var_68], r13w; NewIrql
0x140003400  mov     [rsp+98h+var_78], rsi; __int64
0x140003405  call    NbtRegisterName
0x14000340a  xor     edx, edx
0x14000340c  mov     ebx, eax
0x14000340e  test    eax, eax
0x140003410  jns     short loc_140003460
0x140003412  test    r14, r14
0x140003415  jnz     loc_140003B8B
0x14000341b  lea     rcx, Resource; Resource
0x140003422  call    cs:__imp_ExReleaseResourceLite
0x140003429  nop     dword ptr [rax+rax+00h]
0x14000342e  call    cs:__imp_KeLeaveCriticalRegion
0x140003435  nop     dword ptr [rax+rax+00h]
0x14000343a  mov     r8, r12
0x14000343d  mov     edx, 3A7h
0x140003442  mov     rcx, rsi; P
0x140003445  call    NbtDereferenceClient
0x14000344a  mov     r9, r12
0x14000344d  mov     r8d, 3A8h
0x140003453  mov     rcx, rdi
0x140003456  call    NbtDereferenceAddress
0x14000345b  jmp     loc_140003596
0x140003460  cmp     ebx, 103h
0x140003466  jz      short loc_140003473
0x140003468  mov     byte ptr [rsi+111h], 1
0x14000346f  mov     [rsi+18h], rdx
0x140003473  test    byte ptr cs:xmmword_140038420+0Bh, 2
0x14000347a  jnz     loc_140003B71
0x140003480  lea     r8, SpinLock; Lock
0x140003487  mov     rdx, rdi; ListEntry
0x14000348a  lea     rcx, ListHead; ListHead
0x140003491  call    cs:__imp_ExInterlockedInsertTailList
0x140003498  nop     dword ptr [rax+rax+00h]
0x14000349d  mov     r9, r12
0x1400034a0  mov     r8d, 3B7h
0x1400034a6  mov     rcx, rdi
0x1400034a9  call    NbtDereferenceAddress
0x1400034ae  lea     rcx, Resource; Resource
0x1400034b5  call    cs:__imp_ExReleaseResourceLite
0x1400034bc  nop     dword ptr [rax+rax+00h]
0x1400034c1  call    cs:__imp_KeLeaveCriticalRegion
0x1400034c8  nop     dword ptr [rax+rax+00h]
0x1400034cd  test    ebx, ebx
0x1400034cf  js      loc_140003596
0x1400034d5  cmp     byte ptr [rbp+0], 2Ah ; '*'
0x1400034d9  jz      loc_140003596
0x1400034df  cmp     byte ptr [rbp+0Fh], 20h ; ' '
0x1400034e3  jnz     loc_140003596
0x1400034e9  inc     dword ptr [r15+388h]
0x1400034f0  xor     r9d, r9d
0x1400034f3  mov     r8b, 1
0x1400034f6  mov     rdx, rbp
0x1400034f9  mov     rcx, r15
0x1400034fc  call    CheckSetWakeupPattern
0x140003501  jmp     loc_140003596
0x140003506  xor     eax, eax
0x140003508  lea     rdx, [r14+18h]
0x14000350c  mov     rcx, [rdx]
0x14000350f  cmp     [rcx], rdx
0x140003512  cmovz   esi, eax
0x140003515  test    esi, esi
0x140003517  jns     loc_140003657
0x14000351d  mov     ebx, 0C0000043h
0x140003522  mov     rax, [rsp+98h+arg_0]
0x14000352a  lea     rcx, [r14+38h]; SpinLock
0x14000352e  mov     dl, byte ptr [rsp+98h+NewIrql]; NewIrql
0x140003535  mov     qword ptr [rax], 0
0x14000353c  call    cs:__imp_KeReleaseSpinLock
0x140003543  nop     dword ptr [rax+rax+00h]
0x140003548  mov     dl, byte ptr [rsp+98h+arg_8]; NewIrql
0x14000354f  lea     rcx, SpinLock; SpinLock
0x140003556  call    cs:__imp_KeReleaseSpinLock
0x14000355d  nop     dword ptr [rax+rax+00h]
0x140003562  lea     r9, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140003569  mov     r8d, 49Bh
0x14000356f  mov     rcx, r14
0x140003572  call    NbtDereferenceAddress
0x140003577  lea     rcx, Resource; Resource
0x14000357e  call    cs:__imp_ExReleaseResourceLite
0x140003585  nop     dword ptr [rax+rax+00h]
0x14000358a  call    cs:__imp_KeLeaveCriticalRegion
0x140003591  nop     dword ptr [rax+rax+00h]
0x140003596  mov     eax, ebx
0x140003598  mov     rbx, [rsp+98h+arg_18]
0x1400035a0  add     rsp, 60h
0x1400035a4  pop     r15
0x1400035a6  pop     r14
0x1400035a8  pop     r13
0x1400035aa  pop     r12
0x1400035ac  pop     rdi
0x1400035ad  pop     rsi
0x1400035ae  pop     rbp
0x1400035af  retn
0x1400035b1  mov     r14, [rdi+78h]
0x1400035b5  test    r14, r14
0x1400035b8  jz      loc_140003AF0
0x1400035be  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400035c5  lea     r8, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x1400035cc  jnz     loc_14000391B
0x1400035d2  lock inc dword ptr [r14+14h]
0x1400035d7  mov     dl, r12b; NewIrql
0x1400035da  lea     rcx, SpinLock; SpinLock
0x1400035e1  call    cs:__imp_KeReleaseSpinLock
0x1400035e8  nop     dword ptr [rax+rax+00h]
0x1400035ed  mov     r13, [rsp+98h+arg_20]
0x1400035f5  test    r13, r13
0x1400035f8  jz      short loc_140003608
0x1400035fa  mov     r8, [rdi+78h]
0x1400035fe  mov     rdx, r13
0x140003601  call    NTCheckSharedAccess
0x140003606  mov     esi, eax
0x140003608  lea     rcx, SpinLock; SpinLock
0x14000360f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003616  nop     dword ptr [rax+rax+00h]
0x14000361b  lea     rcx, [r14+38h]; SpinLock
0x14000361f  mov     byte ptr [rsp+98h+arg_8], al
0x140003626  mov     r12b, al
0x140003629  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003630  nop     dword ptr [rax+rax+00h]
0x140003635  mov     byte ptr [rsp+98h+NewIrql], al
0x14000363c  cmp     ebx, 7F000000h
0x140003642  jz      short loc_14000364F
0x140003644  mov     ecx, [rdi+48h]
0x140003647  test    cl, 2
0x14000364a  jz      short loc_14000364F
0x14000364c  mov     [rdi+20h], ebx
0x14000364f  test    esi, esi
0x140003651  js      loc_140003950
0x140003657  mov     ecx, [rdi+48h]
0x14000365a  test    cl, 40h
0x14000365d  jnz     loc_1400039A8
0x140003663  test    esi, esi
0x140003665  js      loc_14000351D
0x14000366b  mov     eax, 0FFFDh
0x140003670  test    word ptr [rsp+98h+var_58], ax
0x140003675  jz      short loc_1400036B7
0x140003677  test    cl, 4
0x14000367a  jnz     short loc_1400036C2
0x14000367c  jmp     loc_14000351D
0x140003681  movzx   eax, si
0x140003684  jmp     loc_14000334C
0x140003689  mov     byte ptr [rsp+98h+var_60], 0Ah
0x14000368e  lea     rcx, [rdi+40h]
0x140003692  mov     [rsp+98h+var_68], dl
0x140003696  mov     r9, rdi
0x140003699  mov     [rsp+98h+var_70], rdx
0x14000369e  xor     r8d, r8d
0x1400036a1  mov     [rsp+98h+var_78], rdx
0x1400036a6  lea     rdx, DelayedFreeAddrObj
0x1400036ad  call    NTQueueToWorkerThread
0x1400036b2  jmp     loc_1400034AE
0x1400036b7  test    cl, 2
0x1400036ba  mov     ebx, 0C0000043h
0x1400036bf  cmovz   esi, ebx
0x1400036c2  xor     r12b, r12b
0x1400036c5  mov     ebx, esi
0x1400036c7  test    esi, esi
0x1400036c9  js      loc_140003522
0x1400036cf  mov     ebx, 1
0x1400036d4  mov     rdx, r15
0x1400036d7  mov     rcx, r14
0x1400036da  call    NbtAllocateClientBlock
0x1400036df  mov     rsi, rax
0x1400036e2  test    rax, rax
0x1400036e5  jz      loc_140003A6F
0x1400036eb  mov     [rax+18h], r13
0x1400036ef  mov     eax, [rsp+98h+var_54]
0x1400036f3  mov     [rsi+30h], eax
0x1400036f6  mov     rax, [rsp+98h+arg_0]
0x1400036fe  mov     [rax], rsi
0x140003701  test    r13, r13
  ... truncated ...
```
