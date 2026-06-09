# NtfsProcessRollbackStruct

- ea: `0x140140ab0`
- end: `0x140140f54`
- name: `NtfsProcessRollbackStruct`
- size: `1188`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140129500`
- `0x14012b220`
- `0x140140320`
- `0x140140660`

## callees

- `0x1400211b0`
- `0x14010c050`
- `0x140140ab0`
- `0x140140f5c`
- `0x140173ab0`
- `0x140196e30`
- `0x1401d9484`
- `0x14020d70c`
- `0x14022f4cc`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c86d9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c86d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140140bbd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c858e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140140bbd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c858e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c88c8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c88c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140b83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140c88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140dbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140b83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140c88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140dbb`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140140ea4`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140140ea4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140c31`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140d1f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140de5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c8b1c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140c31`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140d1f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140140de5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c8b1c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140cc4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140d60`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c860c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8708`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8b63`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140cc4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140d60`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c860c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8708`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c8b63`

## pseudocode

```c
void __fastcall NtfsProcessRollbackStruct(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  int v3; // eax
  int v5; // eax
  _DWORD *v6; // rdi
  unsigned __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  unsigned __int16 *v10; // rax
  unsigned __int16 **v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // rbp
  void *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _DWORD *v22; // r8
  __int64 v23; // rcx
  struct _ERESOURCE *v24; // rcx
  _QWORD *v25; // rdx
  signed __int64 v26; // r8
  signed __int64 v27; // rax
  bool v28; // zf
  __int64 v29; // rtt
  signed __int64 v30; // rax
  __int64 v31; // rtt
  signed __int64 v32; // r8
  signed __int64 v33; // rax
  __int64 v34; // rtt
  signed __int64 v35; // rax
  __int64 v36; // rtt
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  signed __int64 v44; // r8
  signed __int64 v45; // rax
  __int64 v46; // rtt
  signed __int64 v47; // rax
  __int64 v48; // rtt
  unsigned __int16 *v49; // rdx
  unsigned __int16 *v50; // r9
  _DWORD *v51; // r14
  unsigned __int16 *v52; // rsi
  char **v53; // rdi
  __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned __int16 *v56; // r15
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r9
  __int64 v63; // r8
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // r8
  int v67; // eax

  v3 = *a2;
  if ( (_WORD)v3 != 1831 )
  {
    if ( (a3 & 0x10) != 0 )
    {
      if ( v3 == 1827 )
      {
        if ( (*((_DWORD *)a2 + 1) & 0x100) != 0 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 60LL));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 64LL), 0xFFFFFFFF) == 1 )
            TxfDeleteTxfRmcb(*((char **)a2 + 10));
        }
      }
      else if ( v3 == 1864 && (*((_DWORD *)a2 + 1) & 1) != 0 )
      {
        v19 = (void *)*((_QWORD *)a2 + 5);
        if ( v19 )
          ExFreePoolWithTag(v19, 0);
      }
      v9 = *((_QWORD *)a2 + 1);
      v10 = a2 + 4;
      if ( *(unsigned __int16 **)(v9 + 8) != a2 + 4 )
        goto LABEL_24;
      goto LABEL_16;
    }
    if ( (a3 & 5) == 0 )
      return;
    if ( v3 != 1827 )
    {
      v7 = (unsigned int)(v3 - 1828);
      switch ( *a2 )
      {
        case 0x724u:
          if ( (a3 & 4) == 0 )
            goto LABEL_79;
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*((_QWORD *)a2 + 3) + 136LL), 1u);
          if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
            **(_DWORD **)(*((_QWORD *)a2 + 3) + 48LL) = 0;
          if ( (*((_DWORD *)a2 + 1) & 2) == 0 )
            goto LABEL_70;
          ExAcquireResourceExclusiveLite(
            (PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL) + 24LL) + 80LL),
            1u);
          v15 = (_QWORD *)*((_QWORD *)a2 + 4);
          v16 = *v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_24;
          v17 = (_QWORD *)v15[1];
          if ( (_QWORD *)*v17 != v15 )
            goto LABEL_24;
          *v17 = v16;
          *(_QWORD *)(v16 + 8) = v17;
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 24LL) + 24LL) + 80LL));
          v18 = *(void **)(*((_QWORD *)a2 + 4) + 32LL);
          if ( v18 )
            TxfDereferenceTxfFcb(v18);
          ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, *((PVOID *)a2 + 4));
LABEL_70:
          if ( (*((_DWORD *)a2 + 1) & 4) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 20LL) -= *((_DWORD *)a2 + 10);
          if ( (*((_DWORD *)a2 + 1) & 8) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~4u;
          if ( (*((_DWORD *)a2 + 1) & 0x20) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~0x200000u;
          if ( (*((_DWORD *)a2 + 1) & 0x10) != 0 )
          {
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~0x80000u;
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 48LL) + 52LL) = 0;
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 48LL) + 48LL) = 0;
            *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 48LL) + 54LL) = 0;
          }
          ExReleaseResourceLite(*(PERESOURCE *)(*((_QWORD *)a2 + 3) + 136LL));
LABEL_79:
          *((_DWORD *)a2 + 1) &= 0xFFFFFFC0;
          *((_DWORD *)a2 + 10) = 0;
          break;
        case 0x725u:
          if ( (a3 & 4) != 0 )
          {
            if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
              TxfReserveSpaceForAbortPriv(
                0,
                *(_QWORD *)(*((_QWORD *)a2 + 3) + 208LL),
                *((_QWORD *)a2 + 3),
                *((_QWORD *)a2 + 5));
            if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
              TxfReleaseSpaceForAbortPriv(*(_QWORD *)(*((_QWORD *)a2 + 3) + 208LL), *((_QWORD *)a2 + 3));
          }
          goto LABEL_86;
        case 0x726u:
          if ( (a3 & 4) != 0 )
          {
            if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
              *(_OWORD *)(*((_QWORD *)a2 + 3) + 264LL) = *((_OWORD *)a2 + 2);
            if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
            {
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 452LL) = *((_DWORD *)a2 + 12);
              *(_BYTE *)(*((_QWORD *)a2 + 3) + 462LL) = *((_BYTE *)a2 + 54);
              *(_WORD *)(*((_QWORD *)a2 + 3) + 460LL) = a2[26];
            }
            if ( (*((_DWORD *)a2 + 1) & 4) != 0 )
            {
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 512LL) &= ~*((_DWORD *)a2 + 15);
              *(_DWORD *)(*((_QWORD *)a2 + 3) + 512LL) |= *((_DWORD *)a2 + 15) & *((_DWORD *)a2 + 14);
            }
          }
          if ( (a2[2] & 8) != 0 && (a3 & 1) != 0 )
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 512LL) &= ~0x2000000u;
          *((_DWORD *)a2 + 1) &= 0xFFFFFFF0;
          break;
        case 0x728u:
          if ( (a3 & 4) == 0 )
            goto LABEL_86;
          if ( (*((_DWORD *)a2 + 1) & 2) != 0 )
          {
            v7 = *((_QWORD *)a2 + 3);
            *(_DWORD *)v7 = *((_DWORD *)a2 + 8);
          }
          if ( (*((_DWORD *)a2 + 1) & 1) != 0 )
          {
            LOBYTE(a3) = 1;
            NtfsAcquireResourceExclusive(v7, **(_QWORD **)(*((_QWORD *)a2 + 5) + 96LL), a3);
            RtlDeleteElementGenericTableAvl(*((PRTL_AVL_TABLE *)a2 + 5), *((PVOID *)a2 + 3));
            v23 = **(_QWORD **)(*((_QWORD *)a2 + 5) + 96LL);
            if ( *(_WORD *)v23 == 1794 )
              v24 = (struct _ERESOURCE *)(*(_QWORD *)(v23 + 104) + 64LL);
            else
              v24 = *(struct _ERESOURCE **)(v23 + 8);
            ExReleaseResourceLite(v24);
            *((_DWORD *)a2 + 1) &= 0xFFFFFFFC;
          }
          else
          {
LABEL_86:
            *((_DWORD *)a2 + 1) &= 0xFFFFFFFC;
          }
          break;
        case 0x742u:
          if ( (a3 & 4) != 0 && (*((_DWORD *)a2 + 1) & 1) != 0 )
            *(_QWORD *)(*((_QWORD *)a2 + 3) + 64LL) = *((_QWORD *)a2 + 4);
          goto LABEL_19;
        case 0x748u:
          if ( (*((_DWORD *)a2 + 1) & 1) == 0 )
            goto LABEL_19;
          if ( (a3 & 4) != 0 )
          {
            v12 = 0;
            ExAcquireResourceExclusiveLite((PERESOURCE)(*((_QWORD *)a2 + 3) + 10792LL), 1u);
            if ( *((_QWORD *)a2 + 5) )
              v12 = NtfsCalculateVcbStorageReserveTotalReserved(*((_QWORD *)a2 + 3));
            v13 = *((_QWORD *)a2 + 3);
            if ( *(_QWORD *)(v13 + 10904) )
              v12 -= NtfsCalculateVcbStorageReserveTotalReserved(*((_QWORD *)a2 + 3));
            if ( v12 )
            {
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v13 + 720));
              *(_QWORD *)(*((_QWORD *)a2 + 3) + 328LL) += v12;
              v20 = (_QWORD *)*((_QWORD *)a2 + 3);
              v21 = v20[41];
              if ( v12 <= 0 )
              {
                if ( v21 < v20[1039] )
                  v20[1039] = v21;
                v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                v32 = v25[38] - ((__int64)v25[41] >> 8) - v25[796] - v25[41];
                if ( v32 <= 0 )
                  v32 = 0;
                do
                {
                  v33 = v25[1043];
                  if ( v32 >= v33 )
                    break;
                  v34 = v25[1043];
                  v28 = v34 == _InterlockedCompareExchange64(v25 + 1043, v32, v33);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
                do
                {
                  v35 = v25[1044];
                  if ( v32 <= v35 )
                    break;
                  v36 = v25[1044];
                  v28 = v36 == _InterlockedCompareExchange64(v25 + 1044, v32, v35);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
              }
              else
              {
                if ( v21 > v20[1040] )
                  v20[1040] = v21;
                v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                v26 = v25[38] - ((__int64)v25[41] >> 8) - v25[796] - v25[41];
                if ( v26 <= 0 )
                  v26 = 0;
                do
                {
                  v27 = v25[1043];
                  if ( v26 >= v27 )
                    break;
                  v29 = v25[1043];
                  v28 = v29 == _InterlockedCompareExchange64(v25 + 1043, v26, v27);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
                do
                {
                  v30 = v25[1044];
                  if ( v26 <= v30 )
                    break;
                  v31 = v25[1044];
                  v28 = v31 == _InterlockedCompareExchange64(v25 + 1044, v26, v30);
                  v25 = (_QWORD *)*((_QWORD *)a2 + 3);
                }
                while ( !v28 );
              }
              v37 = v25[41];
              v38 = v37;
              if ( v37 <= 0 )
                v38 = 0;
              if ( v38 >= 0xFFFFFFFFLL )
              {
                v37 = 0xFFFFFFFFLL;
              }
              else if ( v37 <= 0 )
              {
                v37 = 0;
              }
              v25[41] = v37;
              v39 = *((_QWORD *)a2 + 3);
              v40 = *(_QWORD *)(v39 + 328);
              if ( v40 > *(_QWORD *)(v39 + 8320) )
                *(_QWORD *)(v39 + 8320) = v40;
              v41 = *((_QWORD *)a2 + 3);
              v42 = *(_QWORD *)(v41 + 328);
              if ( v42 < *(_QWORD *)(v41 + 8312) )
                *(_QWORD *)(v41 + 8312) = v42;
              v43 = *((_QWORD *)a2 + 3);
              v44 = *(_QWORD *)(v43 + 304)
                  - (*(__int64 *)(v43 + 328) >> 8)
                  - *(_QWORD *)(v43 + 6368)
                  - *(_QWORD *)(v43 + 328);
              if ( v44 <= 0 )
                v44 = 0;
              do
              {
                v45 = *(_QWORD *)(v43 + 8344);
                if ( v44 >= v45 )
                  break;
                v46 = *(_QWORD *)(v43 + 8344);
                v28 = v46 == _InterlockedCompareExchange64((volatile signed __int64 *)(v43 + 8344), v44, v45);
                v43 = *((_QWORD *)a2 + 3);
              }
              while ( !v28 );
              do
              {
                v47 = *(_QWORD *)(v43 + 8352);
                if ( v44 <= v47 )
                  break;
                v48 = *(_QWORD *)(v43 + 8352);
                v28 = v48 == _InterlockedCompareExchange64((volatile signed __int64 *)(v43 + 8352), v44, v47);
                v43 = *((_QWORD *)a2 + 3);
              }
              while ( !v28 );
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v43 + 720));
            }
            v14 = *(void **)(*((_QWORD *)a2 + 3) + 10904LL);
            if ( v14 )
              ExFreePoolWithTag(v14, 0);
            *(_DWORD *)(*((_QWORD *)a2 + 3) + 10900LL) = *((_DWORD *)a2 + 8);
            *(_QWORD *)(*((_QWORD *)a2 + 3) + 10904LL) = *((_QWORD *)a2 + 5);
            NtfsCalculateVcbStorageReserveFields(*((_QWORD *)a2 + 3));
            ExReleaseResourceLite((PERESOURCE)(*((_QWORD *)a2 + 3) + 10792LL));
            *((_DWORD *)a2 + 1) &= ~1u;
          }
          else
          {
            v8 = (void *)*((_QWORD *)a2 + 5);
            if ( v8 )
            {
              ExFreePoolWithTag(v8, 0);
              *((_DWORD *)a2 + 1) &= ~1u;
            }
            else
            {
LABEL_19:
              *((_DWORD *)a2 + 1) &= ~1u;
            }
          }
          break;
        default:
          break;
      }
LABEL_8:
      if ( *((_DWORD *)a2 + 1) )
        return;
      v9 = *((_QWORD *)a2 + 1);
      v10 = a2 + 4;
      if ( *(unsigned __int16 **)(v9 + 8) != a2 + 4 )
LABEL_24:
        __fastfail(3u);
LABEL_16:
      v11 = (unsigned __int16 **)*((_QWORD *)v10 + 1);
      if ( *v11 == v10 )
      {
        *v11 = (unsigned __int16 *)v9;
        *(_QWORD *)(v9 + 8) = v11;
        ExFreeToLookasideListEx(&NtfsRollbackStructLookasideList, a2);
        return;
      }
      goto LABEL_24;
    }
    v5 = *((_DWORD *)a2 + 1);
    v6 = a2 + 2;
    if ( (a3 & 4) == 0 )
    {
      if ( (v5 & 0x100) != 0 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 60LL));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 64LL), 0xFFFFFFFF) == 1 )
          TxfDeleteTxfRmcb(*((char **)a2 + 10));
      }
LABEL_7:
      *v6 &= 0xFFFFC000;
      *((_DWORD *)a2 + 9) = 0;
      a2[53] = 0;
      goto LABEL_8;
    }
    v22 = a2 + 2;
    if ( (v5 & 1) != 0 )
    {
      *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) &= ~*((_DWORD *)a2 + 9);
      *(_DWORD *)(*((_QWORD *)a2 + 3) + 4LL) |= *((_DWORD *)a2 + 9) & *((_DWORD *)a2 + 8);
    }
    v49 = a2 + 12;
    if ( (*v6 & 0x1000) != 0 )
    {
      *(_QWORD *)(*(_QWORD *)v49 + 136LL) = *((_QWORD *)a2 + 14);
      *(_QWORD *)(*(_QWORD *)v49 + 144LL) = *((_QWORD *)a2 + 15);
      *(_QWORD *)(*(_QWORD *)v49 + 192LL) = *((_QWORD *)a2 + 16);
    }
    else
    {
      v22 = v6;
    }
    v50 = a2 + 12;
    if ( (*v6 & 2) != 0 )
    {
      *(_WORD *)(*(_QWORD *)v49 + 188LL) -= a2[53];
      *(_WORD *)(*(_QWORD *)v49 + 190LL) -= a2[52];
    }
    if ( (*v22 & 4) != 0 )
    {
      v51 = a2 + 2;
      *(_QWORD *)(*(_QWORD *)v49 + 240LL) = *((_QWORD *)a2 + 7);
    }
    else
    {
      v51 = v22;
      v50 = a2 + 12;
    }
    if ( (*v22 & 8) != 0 )
      *(_QWORD *)(*(_QWORD *)v50 + 256LL) = *((_QWORD *)a2 + 8);
    else
      v51 = v22;
    if ( (*v22 & 0x80u) == 0 )
    {
      v52 = v50;
    }
    else
    {
      v52 = a2 + 12;
      *(_QWORD *)(*(_QWORD *)v50 + 248LL) = *((_QWORD *)a2 + 9);
    }
    if ( (*v51 & 0x100) != 0 )
    {
      v53 = (char **)(a2 + 40);
      v54 = *((_QWORD *)a2 + 10);
      if ( *(_QWORD *)(*(_QWORD *)v50 + 320LL) != v54 )
      {
        if ( v54 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v54 + 64));
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)a2 + 10) + 36LL));
          v52 = a2 + 12;
        }
        v55 = *(_QWORD *)(*(_QWORD *)v52 + 320LL);
        if ( v55
          && (_InterlockedDecrement((volatile signed __int32 *)(v55 + 36)),
              _InterlockedExchangeAdd(
                (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)v52 + 320LL) + 64LL),
                0xFFFFFFFF) == 1) )
        {
          TxfDeleteTxfRmcb(*(char **)(*(_QWORD *)v52 + 320LL));
        }
        else
        {
          v53 = (char **)(a2 + 40);
        }
        v51 = a2 + 2;
        *(_QWORD *)(*(_QWORD *)v52 + 320LL) = *((_QWORD *)a2 + 10);
      }
      _InterlockedDecrement((volatile signed __int32 *)*v53 + 15);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v53 + 16, 0xFFFFFFFF) == 1 )
        TxfDeleteTxfRmcb(*v53);
    }
    if ( (*v51 & 0x10) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)v52 + 176LL) &= ~*((_DWORD *)a2 + 11);
      *(_DWORD *)(*(_QWORD *)v52 + 176LL) |= *((_DWORD *)a2 + 11) & *((_DWORD *)a2 + 10);
    }
    if ( (*v51 & 0x20) != 0 )
    {
      v56 = a2 + 12;
      v6 = a2 + 2;
      *(_DWORD *)(*(_QWORD *)v52 + 184LL) &= ~*((_DWORD *)a2 + 13);
      *(_DWORD *)(*(_QWORD *)v52 + 184LL) |= *((_DWORD *)a2 + 13) & *((_DWORD *)a2 + 12);
    }
    else
    {
      v6 = v51;
      v56 = v52;
    }
    if ( (*v51 & 0x40) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)v52 + 180LL) = *((_DWORD *)a2 + 22);
    }
    else
    {
      v6 = v51;
      v56 = v52;
    }
    if ( (*v51 & 0x2000) != 0 )
      *(_BYTE *)(*(_QWORD *)v56 + 37LL) = *((_BYTE *)a2 + 92);
    if ( (*v6 & 0x200) == 0 )
      goto LABEL_7;
    if ( (*v6 & 0x400) == 0 )
    {
      v57 = *(_QWORD *)v56;
      v58 = *((_QWORD *)a2 + 12);
      if ( v58 == *(_QWORD *)(*(_QWORD *)v56 + 40LL) )
      {
        if ( *((_BYTE *)a2 + 93) == *(_BYTE *)(v57 + 38) || !v58 )
          goto LABEL_167;
        v56 = a2 + 12;
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v57 + 96) + 10688LL), 1u);
      NtfsAdjustStorageReserveClustersUsed(
        v59,
        *(_QWORD *)(*(_QWORD *)v56 + 96LL),
        *(unsigned __int8 *)(*(_QWORD *)v56 + 38LL),
        -*(_QWORD *)(*(_QWORD *)v56 + 40LL));
      NtfsAdjustStorageReserveClustersUsed(
        v60,
        *(_QWORD *)(*(_QWORD *)v56 + 96LL),
        *((unsigned __int8 *)a2 + 93),
        *((_QWORD *)a2 + 12));
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)v56 + 96LL) + 10688LL));
    }
LABEL_167:
    if ( (*((_DWORD *)a2 + 1) & 0x800) != 0 )
    {
      v61 = *((_QWORD *)a2 + 3);
      v62 = *(_QWORD *)(v61 + 96);
      v63 = *(unsigned __int8 *)(v61 + 38);
      v64 = *(unsigned __int16 *)(v62 + 11524);
      if ( _bittest(&v64, v63) )
        *(_QWORD *)(v62 + 8 * v63 + 11536) -= *(_QWORD *)(v61 + 40);
      v65 = *((unsigned __int8 *)a2 + 93);
      v66 = *(_QWORD *)(*((_QWORD *)a2 + 3) + 96LL);
      v67 = *(unsigned __int16 *)(v66 + 11524);
      if ( _bittest(&v67, v65) )
        *(_QWORD *)(v66 + 8 * v65 + 11536) += *((_QWORD *)a2 + 12);
    }
    v6 = a2 + 2;
    *(_BYTE *)(*((_QWORD *)a2 + 3) + 38LL) = *((_BYTE *)a2 + 93);
    *(_QWORD *)(*((_QWORD *)a2 + 3) + 40LL) = *((_QWORD *)a2 + 12);
    goto LABEL_7;
  }
}

```

## disassembly

```asm
0x140140ab0  mov     [rsp+arg_0], rcx
0x140140ab5  push    rbx
0x140140ab6  sub     rsp, 30h
0x140140aba  movzx   eax, word ptr [rdx]
0x140140abd  mov     ecx, 727h
0x140140ac2  mov     rbx, rdx
0x140140ac5  cmp     ax, cx
0x140140ac8  jnz     short loc_140140AD1
0x140140aca  add     rsp, 30h
0x140140ace  pop     rbx
0x140140acf  retn
0x140140ad1  mov     [rsp+38h+arg_8], rbp
0x140140ad6  mov     [rsp+38h+arg_10], rsi
0x140140adb  mov     [rsp+38h+arg_18], rdi
0x140140ae0  test    r8b, 10h
0x140140ae4  jnz     loc_140140D8A
0x140140aea  test    r8b, 5
0x140140aee  jz      short loc_140140B29
0x140140af0  mov     ecx, eax
0x140140af2  cmp     eax, 723h
0x140140af7  jnz     short loc_140140B3A
0x140140af9  mov     eax, [rdx+4]
0x140140afc  lea     rdi, [rdx+4]
0x140140b00  test    r8b, 4
0x140140b04  jnz     loc_140140EE8
0x140140b0a  bt      eax, 8
0x140140b0e  jb      loc_140140F27
0x140140b14  and     dword ptr [rdi], 0FFFFC000h
0x140140b1a  xor     edi, edi
0x140140b1c  mov     [rbx+24h], edi
0x140140b1f  mov     [rbx+6Ah], di
0x140140b23  cmp     dword ptr [rbx+4], 0; jumptable 0000000140140B61 default case, cases 1831,1833-1857,1859-1863
0x140140b27  jz      short loc_140140B95
0x140140b29  mov     rsi, [rsp+38h+arg_10]
0x140140b2e  mov     rbp, [rsp+38h+arg_8]
0x140140b33  mov     rdi, [rsp+38h+arg_18]
0x140140b38  jmp     short loc_140140ACA
0x140140b3a  add     ecx, 0FFFFF8DCh; switch 37 cases
0x140140b40  cmp     ecx, 24h
0x140140b43  ja      short def_140140B61; jumptable 0000000140140B61 default case, cases 1831,1833-1857,1859-1863
0x140140b45  movsxd  rax, ecx
0x140140b48  lea     rdx, cs:140000000h
0x140140b4f  movzx   eax, ds:(byte_14006E574 - 140000000h)[rdx+rax]
0x140140b57  mov     ecx, ds:(jpt_140140B61 - 140000000h)[rdx+rax*4]
0x140140b5e  add     rcx, rdx
0x140140b61  jmp     rcx; switch jump
0x140140b67  mov     eax, [rbx+4]; jumptable 0000000140140B61 case 1864
0x140140b6a  test    al, 1
0x140140b6c  jz      short loc_140140BE7
0x140140b6e  test    r8b, 4
0x140140b72  jnz     loc_140140C20
0x140140b78  mov     rcx, [rbx+28h]; P
0x140140b7c  test    rcx, rcx
0x140140b7f  jz      short loc_140140BE7
0x140140b81  xor     edx, edx; Tag
0x140140b83  call    cs:__imp_ExFreePoolWithTag
0x140140b8a  nop     dword ptr [rax+rax+00h]
0x140140b8f  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140140b93  jmp     short def_140140B61; jumptable 0000000140140B61 default case, cases 1831,1833-1857,1859-1863
0x140140b95  mov     rcx, [rbx+8]
0x140140b99  lea     rax, [rbx+8]
0x140140b9d  cmp     [rcx+8], rax
0x140140ba1  jnz     short loc_140140C19
0x140140ba3  mov     rdx, [rax+8]
0x140140ba7  cmp     [rdx], rax
0x140140baa  jnz     short loc_140140C19
0x140140bac  mov     [rdx], rcx
0x140140baf  mov     [rcx+8], rdx
0x140140bb3  mov     rdx, rbx; Entry
0x140140bb6  lea     rcx, NtfsRollbackStructLookasideList; Lookaside
0x140140bbd  call    cs:__imp_ExFreeToLookasideListEx
0x140140bc4  nop     dword ptr [rax+rax+00h]
0x140140bc9  mov     rsi, [rsp+38h+arg_10]
0x140140bce  mov     rbp, [rsp+38h+arg_8]
0x140140bd3  mov     rdi, [rsp+38h+arg_18]
0x140140bd8  jmp     loc_140140ACA
0x140140bdd  test    r8b, 4; jumptable 0000000140140B61 case 1858
0x140140be1  jnz     loc_140140E0B
0x140140be7  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140140beb  jmp     def_140140B61; jumptable 0000000140140B61 default case, cases 1831,1833-1857,1859-1863
0x140140bf0  test    r8b, 4; jumptable 0000000140140B61 case 1830
0x140140bf4  jnz     loc_140140E27
0x140140bfa  test    byte ptr [rbx+4], 8
0x140140bfe  setnz   cl
0x140140c01  test    r8b, 1
0x140140c05  setnz   al
0x140140c08  test    al, cl
0x140140c0a  jnz     loc_140140CD9
0x140140c10  and     dword ptr [rbx+4], 0FFFFFFF0h
0x140140c14  jmp     def_140140B61; jumptable 0000000140140B61 default case, cases 1831,1833-1857,1859-1863
0x140140c19  mov     ecx, 3
0x140140c1e  int     29h; Win8: RtlFailFast(ecx)
0x140140c20  mov     rcx, [rbx+18h]
0x140140c24  xor     edi, edi
0x140140c26  add     rcx, 2A28h; Resource
0x140140c2d  mov     dl, 1; Wait
0x140140c2f  mov     esi, edi
0x140140c31  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140140c38  nop     dword ptr [rax+rax+00h]
0x140140c3d  mov     rdx, [rbx+28h]
0x140140c41  test    rdx, rdx
0x140140c44  jz      short loc_140140C52
0x140140c46  mov     rcx, [rbx+18h]
0x140140c4a  call    NtfsCalculateVcbStorageReserveTotalReserved
0x140140c4f  mov     rsi, rax
0x140140c52  mov     rbp, [rbx+18h]
0x140140c56  mov     rdx, [rbp+2A98h]
0x140140c5d  test    rdx, rdx
0x140140c60  jz      short loc_140140C6D
0x140140c62  mov     rcx, rbp
0x140140c65  call    NtfsCalculateVcbStorageReserveTotalReserved
0x140140c6a  sub     rsi, rax
0x140140c6d  test    rsi, rsi
0x140140c70  jnz     loc_140140E9D
0x140140c76  mov     rax, [rbx+18h]
0x140140c7a  mov     rcx, [rax+2A98h]; P
0x140140c81  test    rcx, rcx
0x140140c84  jz      short loc_140140C94
0x140140c86  xor     edx, edx; Tag
0x140140c88  call    cs:__imp_ExFreePoolWithTag
0x140140c8f  nop     dword ptr [rax+rax+00h]
0x140140c94  mov     rcx, [rbx+18h]
0x140140c98  mov     eax, [rbx+20h]
0x140140c9b  mov     [rcx+2A94h], eax
0x140140ca1  mov     rcx, [rbx+18h]
0x140140ca5  mov     rax, [rbx+28h]
0x140140ca9  mov     [rcx+2A98h], rax
0x140140cb0  mov     rcx, [rbx+18h]
0x140140cb4  call    NtfsCalculateVcbStorageReserveFields
0x140140cb9  mov     rcx, [rbx+18h]
0x140140cbd  add     rcx, 2A28h; Resource
0x140140cc4  call    cs:__imp_ExReleaseResourceLite
0x140140ccb  nop     dword ptr [rax+rax+00h]
0x140140cd0  and     dword ptr [rbx+4], 0FFFFFFFEh
0x140140cd4  jmp     def_140140B61; jumptable 0000000140140B61 default case, cases 1831,1833-1857,1859-1863
0x140140cd9  mov     rax, [rbx+18h]
0x140140cdd  mov     ecx, [rax+200h]
0x140140ce3  mov     rax, [rbx+18h]
0x140140ce7  btr     ecx, 19h
0x140140ceb  mov     [rax+200h], ecx
0x140140cf1  jmp     loc_140140C10
0x140140cf6  mov     rcx, [rbx+8]
0x140140cfa  lea     rax, [rbx+8]
0x140140cfe  cmp     [rcx+8], rax
0x140140d02  jnz     loc_140140C19
0x140140d08  jmp     loc_140140BA3
0x140140d0d  mov     rax, [rbx+18h]
0x140140d11  mov     dl, 1; Wait
0x140140d13  mov     rcx, [rax+18h]
0x140140d17  mov     rcx, [rcx+18h]
0x140140d1b  add     rcx, 50h ; 'P'; Resource
0x140140d1f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140140d26  nop     dword ptr [rax+rax+00h]
0x140140d2b  mov     rax, [rbx+20h]
0x140140d2f  mov     rdx, [rax]
0x140140d32  cmp     [rdx+8], rax
0x140140d36  jnz     loc_140140C19
0x140140d3c  mov     rcx, [rax+8]
0x140140d40  cmp     [rcx], rax
0x140140d43  jnz     loc_140140C19
0x140140d49  mov     [rcx], rdx
0x140140d4c  mov     [rdx+8], rcx
0x140140d50  mov     rax, [rbx+18h]
0x140140d54  mov     rcx, [rax+18h]
0x140140d58  mov     rcx, [rcx+18h]
0x140140d5c  add     rcx, 50h ; 'P'; Resource
0x140140d60  call    cs:__imp_ExReleaseResourceLite
0x140140d67  nop     dword ptr [rax+rax+00h]
0x140140d6c  mov     rax, [rbx+20h]
0x140140d70  mov     rcx, [rax+20h]
0x140140d74  test    rcx, rcx
0x140140d77  jz      loc_1402C8583
0x140140d7d  xor     edx, edx
0x140140d7f  call    TxfDereferenceTxfFcb
0x140140d84  nop
0x140140d85  jmp     loc_1402C8583
0x140140d8a  mov     ecx, eax
0x140140d8c  sub     ecx, 723h
0x140140d92  jz      loc_1402C853C
0x140140d98  cmp     ecx, 25h ; '%'
0x140140d9b  jnz     loc_140140CF6
0x140140da1  mov     eax, [rdx+4]
0x140140da4  test    al, 1
0x140140da6  jz      loc_140140CF6
0x140140dac  mov     rcx, [rdx+28h]; P
0x140140db0  test    rcx, rcx
0x140140db3  jz      loc_140140CF6
0x140140db9  xor     edx, edx; Tag
0x140140dbb  call    cs:__imp_ExFreePoolWithTag
0x140140dc2  nop     dword ptr [rax+rax+00h]
0x140140dc7  jmp     loc_140140CF6
0x140140dcc  xor     edi, edi; jumptable 0000000140140B61 case 1828
0x140140dce  test    r8b, 4
0x140140dd2  jz      loc_1402C8618
0x140140dd8  mov     rcx, [rbx+18h]
0x140140ddc  mov     dl, 1; Wait
0x140140dde  mov     rcx, [rcx+88h]; Resource
0x140140de5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140140dec  nop     dword ptr [rax+rax+00h]
0x140140df1  mov     eax, [rbx+4]
0x140140df4  test    al, 1
0x140140df6  jz      loc_1402C8577
0x140140dfc  mov     rax, [rbx+18h]
0x140140e00  mov     rcx, [rax+30h]
0x140140e04  mov     [rcx], edi
0x140140e06  jmp     loc_1402C8577
0x140140e0b  mov     eax, [rbx+4]
0x140140e0e  test    al, 1
0x140140e10  jz      loc_140140BE7
0x140140e16  mov     rcx, [rbx+18h]
0x140140e1a  mov     rax, [rbx+20h]
0x140140e1e  mov     [rcx+40h], rax
0x140140e22  jmp     loc_140140BE7
0x140140e27  mov     eax, [rbx+4]
0x140140e2a  test    al, 2
0x140140e2c  jz      loc_1402C8624
0x140140e32  mov     rax, [rbx+18h]
0x140140e36  movups  xmm0, xmmword ptr [rbx+20h]
0x140140e3a  movups  xmmword ptr [rax+108h], xmm0
0x140140e41  jmp     loc_1402C8624
0x140140e46  test    r8b, 4; jumptable 0000000140140B61 case 1829
0x140140e4a  jz      loc_1402C86AE
0x140140e50  mov     eax, [rbx+4]
0x140140e53  test    al, 2
0x140140e55  jz      loc_1402C8690
0x140140e5b  mov     rdx, [rbx+18h]
0x140140e5f  xor     ecx, ecx
0x140140e61  mov     r9, [rbx+28h]
0x140140e65  mov     r8, rdx
0x140140e68  mov     rdx, [rdx+0D0h]
0x140140e6f  call    TxfReserveSpaceForAbortPriv
0x140140e74  nop
0x140140e75  jmp     loc_1402C8690
0x140140e7a  test    r8b, 4; jumptable 0000000140140B61 case 1832
0x140140e7e  jz      loc_1402C86AE
0x140140e84  mov     eax, [rbx+4]
0x140140e87  test    al, 2
0x140140e89  jz      loc_1402C86B7
0x140140e8f  mov     rcx, [rbx+18h]
0x140140e93  mov     eax, [rbx+20h]
0x140140e96  mov     [rcx], eax
0x140140e98  jmp     loc_1402C86B7
0x140140e9d  lea     rcx, [rbp+2D0h]; Mutex
0x140140ea4  call    cs:__imp_KeAcquireGuardedMutex
0x140140eab  nop     dword ptr [rax+rax+00h]
0x140140eb0  mov     rax, [rbx+18h]
0x140140eb4  add     [rax+148h], rsi
0x140140ebb  mov     rax, [rbx+18h]
0x140140ebf  mov     rcx, [rax+148h]
0x140140ec6  test    rsi, rsi
0x140140ec9  jle     loc_1402C8786
0x140140ecf  cmp     rcx, [rax+2080h]
0x140140ed6  jle     loc_1402C871D
0x140140edc  mov     [rax+2080h], rcx
0x140140ee3  jmp     loc_1402C871D
0x140140ee8  mov     [rsp+38h+var_10], r14
0x140140eed  test    al, 1
0x140140eef  jz      loc_1402C88DA
0x140140ef5  mov     edx, [rdx+24h]
0x140140ef8  lea     r8, [rbx+4]
0x140140efc  mov     rcx, [rbx+18h]
0x140140f00  not     edx
0x140140f02  mov     eax, [rcx+4]
0x140140f05  and     edx, eax
0x140140f07  mov     [rcx+4], edx
0x140140f0a  mov     eax, [rcx+4]
0x140140f0d  mov     rcx, [rbx+18h]
0x140140f11  mov     edx, [rbx+20h]
0x140140f14  and     edx, [rbx+24h]
0x140140f17  mov     eax, [rcx+4]
0x140140f1a  or      eax, edx
0x140140f1c  mov     [rcx+4], eax
0x140140f1f  mov     eax, [rcx+4]
0x140140f22  jmp     loc_1402C88DD
0x140140f27  mov     rax, [rdx+50h]
0x140140f2b  mov     ebp, 0FFFFFFFFh
0x140140f30  lock dec dword ptr [rax+3Ch]
0x140140f34  mov     rax, [rdx+50h]
0x140140f38  lock xadd [rax+40h], ebp
0x140140f3d  cmp     ebp, 1
0x140140f40  jnz     loc_140140B14
0x140140f46  mov     rcx, [rdx+50h]; P
0x140140f4a  call    TxfDeleteTxfRmcb
0x140140f4f  jmp     loc_140140B14
0x1402c853c  test    dword ptr [rdx+4], 100h
0x1402c8543  jz      loc_140140CF6
0x1402c8549  mov     rax, [rdx+50h]
0x1402c854d  mov     ebp, 0FFFFFFFFh
0x1402c8552  lock dec dword ptr [rax+3Ch]
0x1402c8556  mov     rax, [rdx+50h]
0x1402c855a  lock xadd [rax+40h], ebp
0x1402c855f  cmp     ebp, 1
0x1402c8562  jnz     loc_140140CF6
0x1402c8568  mov     rcx, [rdx+50h]; P
0x1402c856c  call    TxfDeleteTxfRmcb
0x1402c8571  nop
0x1402c8572  jmp     loc_140140CF6
0x1402c8577  mov     eax, [rbx+4]
0x1402c857a  test    al, 2
0x1402c857c  jz      short loc_1402C859A
  ... truncated ...
```
