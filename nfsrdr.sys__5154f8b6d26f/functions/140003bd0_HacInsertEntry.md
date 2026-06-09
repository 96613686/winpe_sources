# HacInsertEntry

- ea: `0x140003bd0`
- end: `0x140004522`
- name: `HacInsertEntry`
- size: `2386`
- prototype: ``
- caller_count: `8`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140004530`
- `0x1400070a0`
- `0x14000be20`
- `0x14000fbc0`
- `0x140019044`
- `0x14002030c`
- `0x140020884`
- `0x140025484`

## callees

- `0x140003440`
- `0x140003bd0`
- `0x140005c90`
- `0x140008140`
- `0x140008cc0`
- `0x1400145f0`
- `0x140014650`
- `0x1400159cc`
- `0x1400159fc`
- `0x1400173f8`
- `0x140017590`
- `0x140020154`
- `0x140020508`
- `0x1400206e4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140003de5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140003de5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003c2f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003f5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004006`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004134`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400041ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004482`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003c2f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003f5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004006`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004134`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400041ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004482`
- `ntoskrnl!KeReleaseMutex` at `0x140003fcd`
- `ntoskrnl!KeReleaseMutex` at `0x14000409b`
- `ntoskrnl!KeReleaseMutex` at `0x1400041af`
- `ntoskrnl!KeReleaseMutex` at `0x1400041cd`
- `ntoskrnl!KeReleaseMutex` at `0x140004262`
- `ntoskrnl!KeReleaseMutex` at `0x1400042b9`
- `ntoskrnl!KeReleaseMutex` at `0x140004373`
- `ntoskrnl!KeReleaseMutex` at `0x140004506`
- `ntoskrnl!KeReleaseMutex` at `0x140003fcd`
- `ntoskrnl!KeReleaseMutex` at `0x14000409b`
- `ntoskrnl!KeReleaseMutex` at `0x1400041af`
- `ntoskrnl!KeReleaseMutex` at `0x1400041cd`
- `ntoskrnl!KeReleaseMutex` at `0x140004262`
- `ntoskrnl!KeReleaseMutex` at `0x1400042b9`
- `ntoskrnl!KeReleaseMutex` at `0x140004373`
- `ntoskrnl!KeReleaseMutex` at `0x140004506`

## pseudocode

```c
LONG __fastcall HacInsertEntry(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // r10d
  unsigned int v10; // ebx
  unsigned int i; // esi
  unsigned int v12; // eax
  unsigned __int16 *v13; // rdx
  unsigned int v14; // ecx
  int v15; // eax
  __int64 v16; // rdx
  __int64 *j; // rbx
  int v18; // r8d
  char v19; // si
  unsigned __int16 k; // ax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rcx
  struct _KMUTANT *v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  struct _KMUTANT *v31; // r8
  struct _LIST_ENTRY *v32; // rax
  __int64 v33; // rcx
  __int16 v34; // bx
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rcx
  struct _KMUTANT *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rax
  _DWORD *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int16 v47; // ax
  __int16 v48; // cx
  void *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  KeWaitForSingleObject(*(PVOID *)(a2 + 40), Executive, 0, 0, 0);
  v6 = *(_QWORD *)(a2 + 40);
  if ( !*(_QWORD *)(v6 + 88) )
  {
    *(_QWORD *)(v6 + 88) = a2;
LABEL_12:
    *(_QWORD *)(v6 + 96) = a2;
    goto LABEL_13;
  }
  if ( *(_QWORD *)(v6 + 96) != a2 )
  {
    v7 = *(_QWORD *)(a2 + 16);
    if ( v7 )
    {
      v8 = *(_QWORD *)(a2 + 24);
      if ( v8 )
      {
        *(_QWORD *)(v8 + 16) = v7;
        *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = *(_QWORD *)(a2 + 24);
      }
      else
      {
        *(_QWORD *)(v6 + 88) = v7;
        *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = 0;
      }
    }
    *(_QWORD *)(*(_QWORD *)(v6 + 96) + 16LL) = a2;
    *(_QWORD *)(a2 + 24) = *(_QWORD *)(v6 + 96);
    *(_QWORD *)(a2 + 16) = 0;
    goto LABEL_12;
  }
LABEL_13:
  v9 = dword_1400411C4;
  v10 = *(_DWORD *)(*(_QWORD *)(a2 + 40) + 56LL);
  if ( !dword_1400411C4 || dword_1400411C4 > v10 )
  {
    for ( i = 15; ; --i )
    {
      if ( !i )
      {
        v9 = dword_1400411C4;
        goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids,
          i,
          *((_DWORD *)PowerOf2Primes + i));
      }
      v4 = *((unsigned int *)PowerOf2Primes + i);
      if ( (unsigned int)v4 < v10 )
        break;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids, v10, v4);
    v9 = *((_DWORD *)PowerOf2Primes + i);
    dword_1400411C4 = v9;
  }
LABEL_27:
  v12 = *(unsigned __int16 *)(a2 + 64);
  if ( !(_WORD)v12 )
    goto LABEL_32;
  v13 = *(unsigned __int16 **)(a2 + 72);
  v5 = v12 >> 1;
  v14 = 0;
  v4 = 0;
  if ( v12 >> 1 )
  {
    do
    {
      v15 = *v13++;
      v4 = (unsigned int)(v4 + 1);
      v14 = __ROR4__(v15 ^ v14, 27);
    }
    while ( (unsigned int)v4 < (unsigned int)v5 );
  }
  if ( v9 )
    v16 = v14 % v9;
  else
LABEL_32:
    v16 = 0;
  for ( j = *(__int64 **)(*(_QWORD *)(*(_QWORD *)(a2 + 40) + 120LL) + 8 * v16); ; j = (__int64 *)*j )
  {
    if ( !j )
      goto LABEL_128;
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)j + 4, (PCUNICODE_STRING)(a2 + 64), 0) )
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  if ( *((_DWORD *)j + 32) != *(_DWORD *)(a2 + 128) || j[22] != *(_QWORD *)(a2 + 176) || j[23] != *(_QWORD *)(a2 + 184) )
    goto LABEL_59;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
  v18 = *((_DWORD *)j + 54);
  if ( v18 != *(_DWORD *)(a2 + 216) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
LABEL_59:
    v19 = 1;
    goto LABEL_60;
  }
  v19 = 0;
  if ( (unsigned __int16)v18 >= 0x40u )
    LOWORD(v18) = 64;
  for ( k = 0; k < (unsigned __int16)v18; ++k )
  {
    if ( *((_BYTE *)j + k + 220) != *(_BYTE *)(k + a2 + 220) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_cca3db0522623f5e31396e1525c29988_Traceguids);
      goto LABEL_59;
    }
  }
LABEL_60:
  if ( j[15] >= *(_QWORD *)(a2 + 120) && (j[6] & 8) == 0 )
  {
    *(_WORD *)(a2 + 48) |= 1u;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    KeWaitForSingleObject((PVOID)j[5], Executive, 0, 0, 0);
    v21 = j[5];
    if ( *(_QWORD *)(v21 + 88) )
    {
      if ( *(__int64 **)(v21 + 96) == j )
        goto LABEL_71;
      v22 = j[2];
      if ( v22 )
      {
        v23 = j[3];
        if ( v23 )
        {
          *(_QWORD *)(v23 + 16) = v22;
          *(_QWORD *)(j[2] + 24) = j[3];
        }
        else
        {
          *(_QWORD *)(v21 + 88) = v22;
          *(_QWORD *)(j[2] + 24) = 0;
        }
      }
      *(_QWORD *)(*(_QWORD *)(v21 + 96) + 16LL) = j;
      j[3] = *(_QWORD *)(v21 + 96);
      j[2] = 0;
    }
    else
    {
      *(_QWORD *)(v21 + 88) = j;
    }
    *(_QWORD *)(v21 + 96) = j;
LABEL_71:
    v24 = (struct _KMUTANT *)j[5];
    ++*((_DWORD *)j + 13);
    KeReleaseMutex(v24, 0);
    if ( (*(_BYTE *)(a2 + 48) & 0x10) != 0 )
      *((_WORD *)j + 24) |= 0x10u;
    *((_DWORD *)j + 14) += *(_DWORD *)(a2 + 56);
    HacDereference(a1, j);
    KeWaitForSingleObject(*(PVOID *)(a2 + 40), Executive, 0, 0, 0);
    v26 = *(_QWORD *)(a2 + 40);
    if ( v19 )
    {
      if ( *(_QWORD *)(v26 + 88) )
      {
        if ( *(_QWORD *)(v26 + 96) == a2 )
        {
LABEL_83:
          HacAcquireLock(a2, v26, v25);
          if ( !(unsigned __int8)HacIsEntryFake(a2) )
            HacpRemoveEntry(a2);
          KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
          *(_WORD *)(a2 + 48) |= 2u;
          if ( *(_DWORD *)(a2 + 128) == 2 )
            HacPurgePostfix(a1, a2);
LABEL_107:
          KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
          return KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
        }
        v27 = *(_QWORD *)(a2 + 16);
        if ( v27 )
        {
          v28 = *(_QWORD *)(a2 + 24);
          if ( v28 )
          {
            *(_QWORD *)(v28 + 16) = v27;
            *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = *(_QWORD *)(a2 + 24);
          }
          else
          {
            *(_QWORD *)(v26 + 88) = v27;
            *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = 0;
          }
        }
        *(_QWORD *)(*(_QWORD *)(v26 + 96) + 16LL) = a2;
        *(_QWORD *)(a2 + 24) = *(_QWORD *)(v26 + 96);
        *(_QWORD *)(a2 + 16) = 0;
      }
      else
      {
        *(_QWORD *)(v26 + 88) = a2;
      }
      *(_QWORD *)(v26 + 96) = a2;
      goto LABEL_83;
    }
    if ( *(_QWORD *)(v26 + 88) )
    {
      if ( *(_QWORD *)(v26 + 96) == a2 )
        goto LABEL_96;
      v29 = *(_QWORD *)(a2 + 16);
      if ( v29 )
      {
        v30 = *(_QWORD *)(a2 + 24);
        if ( v30 )
        {
          *(_QWORD *)(v30 + 16) = v29;
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = *(_QWORD *)(a2 + 24);
        }
        else
        {
          *(_QWORD *)(v26 + 88) = v29;
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = 0;
        }
      }
      *(_QWORD *)(*(_QWORD *)(v26 + 96) + 16LL) = a2;
      *(_QWORD *)(a2 + 24) = *(_QWORD *)(v26 + 96);
      *(_QWORD *)(a2 + 16) = 0;
    }
    else
    {
      *(_QWORD *)(v26 + 88) = a2;
    }
    *(_QWORD *)(v26 + 96) = a2;
LABEL_96:
    KeWaitForSingleObject(*(PVOID *)(a2 + 40), Executive, 0, 0, 0);
    v31 = *(struct _KMUTANT **)(a2 + 40);
    if ( v31[1].MutantListEntry.Blink )
    {
      if ( v31[1].OwnerThread == (struct _KTHREAD *)a2 )
        goto LABEL_105;
      v32 = *(struct _LIST_ENTRY **)(a2 + 16);
      if ( v32 )
      {
        v33 = *(_QWORD *)(a2 + 24);
        if ( v33 )
        {
          *(_QWORD *)(v33 + 16) = v32;
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = *(_QWORD *)(a2 + 24);
        }
        else
        {
          v31[1].MutantListEntry.Blink = v32;
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = 0;
        }
      }
      *((_QWORD *)v31[1].OwnerThread + 2) = a2;
      *(_QWORD *)(a2 + 24) = v31[1].OwnerThread;
      *(_QWORD *)(a2 + 16) = 0;
    }
    else
    {
      v31[1].MutantListEntry.Blink = (struct _LIST_ENTRY *)a2;
    }
    v31[1].OwnerThread = (struct _KTHREAD *)a2;
    v31 = *(struct _KMUTANT **)(a2 + 40);
LABEL_105:
    v34 = *(_WORD *)(a2 + 48) >> 15;
    KeReleaseMutex(v31, 0);
    if ( !(_BYTE)v34 )
      HacpRemoveEntry(a2);
    goto LABEL_107;
  }
  KeWaitForSingleObject((PVOID)j[5], Executive, 0, 0, 0);
  v35 = j[5];
  if ( !*(_QWORD *)(v35 + 88) )
  {
    *(_QWORD *)(v35 + 88) = j;
LABEL_116:
    *(_QWORD *)(v35 + 96) = j;
    goto LABEL_117;
  }
  if ( *(__int64 **)(v35 + 96) != j )
  {
    v36 = j[2];
    if ( v36 )
    {
      v37 = j[3];
      if ( v37 )
      {
        *(_QWORD *)(v37 + 16) = v36;
        *(_QWORD *)(j[2] + 24) = j[3];
      }
      else
      {
        *(_QWORD *)(v35 + 88) = v36;
        *(_QWORD *)(j[2] + 24) = 0;
      }
    }
    *(_QWORD *)(*(_QWORD *)(v35 + 96) + 16LL) = j;
    j[3] = *(_QWORD *)(v35 + 96);
    j[2] = 0;
    goto LABEL_116;
  }
LABEL_117:
  v38 = (struct _KMUTANT *)j[5];
  ++*((_DWORD *)j + 13);
  KeReleaseMutex(v38, 0);
  if ( *((_DWORD *)j + 13) > 1u || *((_DWORD *)j + 14) > 1u )
  {
    v47 = *((_WORD *)j + 24);
    v48 = *(_WORD *)(a2 + 48);
    *((_WORD *)j + 24) = v48;
    if ( (v47 & 0x10) != 0 )
      *((_WORD *)j + 24) = v48 | 0x10;
    *((_DWORD *)j + 26) = *(_DWORD *)(a2 + 104);
    *(__int64 *)((char *)j + 108) = *(_QWORD *)(a2 + 108);
    j[15] = *(_QWORD *)(a2 + 120);
    *((_OWORD *)j + 8) = *(_OWORD *)(a2 + 128);
    *((_OWORD *)j + 9) = *(_OWORD *)(a2 + 144);
    *((_OWORD *)j + 10) = *(_OWORD *)(a2 + 160);
    *((_OWORD *)j + 11) = *(_OWORD *)(a2 + 176);
    *((_OWORD *)j + 12) = *(_OWORD *)(a2 + 192);
    j[26] = *(_QWORD *)(a2 + 208);
    *(_OWORD *)(j + 27) = *(_OWORD *)(a2 + 216);
    *(_OWORD *)(j + 29) = *(_OWORD *)(a2 + 232);
    *(_OWORD *)(j + 31) = *(_OWORD *)(a2 + 248);
    *(_OWORD *)(j + 33) = *(_OWORD *)(a2 + 264);
    *((_DWORD *)j + 70) = *(_DWORD *)(a2 + 280);
    *((_DWORD *)j + 14) += *(_DWORD *)(a2 + 56);
    v49 = *(void **)(a2 + 40);
    *(_WORD *)(a2 + 48) |= 1u;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    KeWaitForSingleObject(v49, Executive, 0, 0, 0);
    v50 = *(_QWORD *)(a2 + 40);
    if ( *(_QWORD *)(v50 + 88) )
    {
      if ( *(_QWORD *)(v50 + 96) == a2 )
      {
LABEL_148:
        if ( !(unsigned __int8)HacIsEntryFake(a2) )
          HacpRemoveEntry(a2);
        KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
        HacDereference(a1, j);
        return KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
      }
      v51 = *(_QWORD *)(a2 + 16);
      if ( v51 )
      {
        v52 = *(_QWORD *)(a2 + 24);
        if ( v52 )
        {
          *(_QWORD *)(v52 + 16) = v51;
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = *(_QWORD *)(a2 + 24);
        }
        else
        {
          *(_QWORD *)(v50 + 88) = v51;
          *(_QWORD *)(*(_QWORD *)(a2 + 16) + 24LL) = 0;
        }
      }
      *(_QWORD *)(*(_QWORD *)(v50 + 96) + 16LL) = a2;
      *(_QWORD *)(a2 + 24) = *(_QWORD *)(v50 + 96);
      *(_QWORD *)(a2 + 16) = 0;
    }
    else
    {
      *(_QWORD *)(v50 + 88) = a2;
    }
    *(_QWORD *)(v50 + 96) = a2;
    goto LABEL_148;
  }
  if ( v19 )
  {
    HacOrphanStaleEntry(a1, j);
  }
  else
  {
    HacAcquireLock(j, v39, v40);
    v41 = j[4];
    if ( v41 && !*(_QWORD *)(a2 + 32) )
    {
      *(_QWORD *)(a2 + 32) = v41;
      j[4] = 0;
    }
    KeReleaseMutex((PRKMUTEX)j[5], 0);
    HacOrphanEntry(j);
  }
  if ( (j[6] & 0x10) != 0 )
    *(_WORD *)(a2 + 48) |= 0x10u;
  *(_DWORD *)(a2 + 56) += *((_DWORD *)j + 14);
  HacDereference(a1, j);
LABEL_128:
  v42 = *(_DWORD **)(a2 + 40);
  if ( v42[18] > v42[16]
    && !(unsigned int)HacpAdjustTable(v42, (unsigned int)(2 * v42[14]), v4, v5)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  }
  v43 = (unsigned int)HacpHashFunction(*(unsigned int *)(*(_QWORD *)(a2 + 40) + 56LL), a2 + 64, v4, v5);
  v44 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 120LL);
  v45 = *(_QWORD *)(v44 + 8 * v43);
  if ( v45 )
    *(_QWORD *)(v45 + 8) = a2;
  *(_QWORD *)a2 = *(_QWORD *)(v44 + 8 * v43);
  *(_QWORD *)(v44 + 8 * v43) = a2;
  *(_WORD *)(a2 + 48) &= ~1u;
  ++*(_DWORD *)(*(_QWORD *)(a2 + 40) + 72LL);
  return KeReleaseMutex(*(PRKMUTEX *)(a2 + 40), 0);
}

```

## disassembly

```asm
0x140003bd0  mov     [rsp+arg_10], rbx
0x140003bd5  push    rbp
0x140003bd6  push    rdi
0x140003bd7  push    r13
0x140003bd9  push    r14
0x140003bdb  push    r15
0x140003bdd  sub     rsp, 30h
0x140003be1  mov     rdi, rdx
0x140003be4  mov     rbp, rcx
0x140003be7  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bee  lea     r14, WPP_GLOBAL_Control
0x140003bf5  cmp     rcx, r14
0x140003bf8  jz      short loc_140003C1B
0x140003bfa  test    dword ptr [rcx+2Ch], 800h
0x140003c01  jz      short loc_140003C1B
0x140003c03  mov     rcx, [rcx+18h]
0x140003c07  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140003c0e  mov     edx, 23h ; '#'
0x140003c13  mov     r9, rdi
0x140003c16  call    WPP_SF_q
0x140003c1b  mov     rcx, [rdi+28h]; Object
0x140003c1f  xor     r13d, r13d
0x140003c22  xor     r9d, r9d; Alertable
0x140003c25  mov     [rsp+58h+Timeout], r13; Timeout
0x140003c2a  xor     r8d, r8d; WaitMode
0x140003c2d  xor     edx, edx; WaitReason
0x140003c2f  call    cs:__imp_KeWaitForSingleObject
0x140003c36  nop     dword ptr [rax+rax+00h]
0x140003c3b  mov     rdx, [rdi+28h]
0x140003c3f  cmp     [rdx+58h], r13
0x140003c43  jz      short loc_140003C91
0x140003c45  cmp     [rdx+60h], rdi
0x140003c49  jz      short loc_140003C99
0x140003c4b  mov     rax, [rdi+10h]
0x140003c4f  test    rax, rax
0x140003c52  jz      short loc_140003C7B
0x140003c54  mov     rcx, [rdi+18h]
0x140003c58  test    rcx, rcx
0x140003c5b  jz      short loc_140003C6F
0x140003c5d  mov     [rcx+10h], rax
0x140003c61  mov     rcx, [rdi+10h]
0x140003c65  mov     rax, [rdi+18h]
0x140003c69  mov     [rcx+18h], rax
0x140003c6d  jmp     short loc_140003C7B
0x140003c6f  mov     [rdx+58h], rax
0x140003c73  mov     rax, [rdi+10h]
0x140003c77  mov     [rax+18h], r13
0x140003c7b  mov     rax, [rdx+60h]
0x140003c7f  mov     [rax+10h], rdi
0x140003c83  mov     rax, [rdx+60h]
0x140003c87  mov     [rdi+18h], rax
0x140003c8b  mov     [rdi+10h], r13
0x140003c8f  jmp     short loc_140003C95
0x140003c91  mov     [rdx+58h], rdi
0x140003c95  mov     [rdx+60h], rdi
0x140003c99  mov     rax, [rdi+28h]
0x140003c9d  mov     r10d, cs:dword_1400411C4
0x140003ca4  mov     [rsp+58h+arg_0], rsi
0x140003ca9  mov     ebx, [rax+38h]
0x140003cac  test    r10d, r10d
0x140003caf  jz      short loc_140003CBA
0x140003cb1  cmp     r10d, ebx
0x140003cb4  jbe     loc_140003D7C
0x140003cba  mov     [rsp+58h+arg_8], r12
0x140003cbf  mov     esi, 0Fh
0x140003cc4  lea     r12, PowerOf2Primes
0x140003ccb  test    esi, esi
0x140003ccd  jz      loc_140003D70
0x140003cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cda  cmp     rcx, r14
0x140003cdd  jz      short loc_140003D0A
0x140003cdf  test    dword ptr [rcx+2Ch], 800h
0x140003ce6  jz      short loc_140003D0A
0x140003ce8  mov     rcx, [rcx+18h]
0x140003cec  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140003cf3  mov     eax, esi
0x140003cf5  mov     edx, 0Ah
0x140003cfa  mov     r9d, esi
0x140003cfd  mov     eax, [r12+rax*4]
0x140003d01  mov     dword ptr [rsp+58h+Timeout], eax
0x140003d05  call    WPP_SF_dd
0x140003d0a  mov     eax, esi
0x140003d0c  mov     r8d, [r12+rax*4]
0x140003d10  lea     r14, [r12+rax*4]
0x140003d14  cmp     r8d, ebx
0x140003d17  jb      short loc_140003D24
0x140003d19  dec     esi
0x140003d1b  lea     r14, WPP_GLOBAL_Control
0x140003d22  jmp     short loc_140003CCB
0x140003d24  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d2b  lea     rax, WPP_GLOBAL_Control
0x140003d32  cmp     rcx, rax
0x140003d35  jz      short loc_140003D5D
0x140003d37  test    dword ptr [rcx+2Ch], 800h
0x140003d3e  jz      short loc_140003D5D
0x140003d40  mov     rcx, [rcx+18h]
0x140003d44  mov     edx, 0Bh
0x140003d49  mov     dword ptr [rsp+58h+Timeout], r8d
0x140003d4e  mov     r9d, ebx
0x140003d51  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140003d58  call    WPP_SF_dd
0x140003d5d  mov     r10d, [r14]
0x140003d60  lea     r14, WPP_GLOBAL_Control
0x140003d67  mov     cs:dword_1400411C4, r10d
0x140003d6e  jmp     short loc_140003D77
0x140003d70  mov     r10d, cs:dword_1400411C4
0x140003d77  mov     r12, [rsp+58h+arg_8]
0x140003d7c  movzx   eax, word ptr [rdi+40h]
0x140003d80  test    ax, ax
0x140003d83  jz      short loc_140003DC2
0x140003d85  mov     rdx, [rdi+48h]
0x140003d89  mov     r9d, eax
0x140003d8c  shr     r9d, 1
0x140003d8f  mov     ecx, r13d
0x140003d92  mov     r8d, r13d
0x140003d95  jz      short loc_140003DB4
0x140003d97  nop     word ptr [rax+rax+00000000h]
0x140003da0  movzx   eax, word ptr [rdx]
0x140003da3  lea     rdx, [rdx+2]
0x140003da7  xor     ecx, eax
0x140003da9  inc     r8d
0x140003dac  ror     ecx, 1Bh
0x140003daf  cmp     r8d, r9d
0x140003db2  jb      short loc_140003DA0
0x140003db4  test    r10d, r10d
0x140003db7  jz      short loc_140003DC2
0x140003db9  xor     edx, edx
0x140003dbb  mov     eax, ecx
0x140003dbd  div     r10d
0x140003dc0  jmp     short loc_140003DC5
0x140003dc2  mov     edx, r13d
0x140003dc5  mov     rax, [rdi+28h]
0x140003dc9  mov     rcx, [rax+78h]
0x140003dcd  mov     rbx, [rcx+rdx*8]
0x140003dd1  test    rbx, rbx
0x140003dd4  jz      loc_1400042E9
0x140003dda  lea     rcx, [rbx+40h]; String1
0x140003dde  xor     r8d, r8d; CaseInSensitive
0x140003de1  lea     rdx, [rdi+40h]; String2
0x140003de5  call    cs:__imp_RtlCompareUnicodeString
0x140003dec  nop     dword ptr [rax+rax+00h]
0x140003df1  test    eax, eax
0x140003df3  jz      short loc_140003DFA
0x140003df5  mov     rbx, [rbx]
0x140003df8  jmp     short loc_140003DD1
0x140003dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e01  cmp     rcx, r14
0x140003e04  jz      short loc_140003E27
0x140003e06  test    dword ptr [rcx+2Ch], 1000h
0x140003e0d  jz      short loc_140003E27
0x140003e0f  mov     rcx, [rcx+18h]
0x140003e13  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x140003e1a  mov     edx, 24h ; '$'
0x140003e1f  mov     r9, rbx
0x140003e22  call    WPP_SF_q
0x140003e27  mov     eax, [rdi+80h]
0x140003e2d  cmp     [rbx+80h], eax
0x140003e33  jnz     loc_140003F22
0x140003e39  mov     rax, [rdi+0B0h]
0x140003e40  cmp     [rbx+0B0h], rax
0x140003e47  jnz     loc_140003F22
0x140003e4d  mov     rax, [rdi+0B8h]
0x140003e54  cmp     [rbx+0B8h], rax
0x140003e5b  jnz     loc_140003F22
0x140003e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e68  cmp     rcx, r14
0x140003e6b  jz      short loc_140003E89
0x140003e6d  mov     eax, [rcx+2Ch]
0x140003e70  test    al, 10h
0x140003e72  jz      short loc_140003E89
0x140003e74  mov     rcx, [rcx+18h]
0x140003e78  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003e7f  mov     edx, 0Ah
0x140003e84  call    WPP_SF_
0x140003e89  mov     r8d, [rbx+0D8h]
0x140003e90  cmp     r8d, [rdi+0D8h]
0x140003e97  jz      short loc_140003EC3
0x140003e99  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ea0  cmp     rcx, r14
0x140003ea3  jz      short loc_140003F22
0x140003ea5  mov     eax, [rcx+2Ch]
0x140003ea8  test    al, 20h
0x140003eaa  jz      short loc_140003F22
0x140003eac  mov     rcx, [rcx+18h]
0x140003eb0  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003eb7  mov     edx, 0Bh
0x140003ebc  call    WPP_SF_
0x140003ec1  jmp     short loc_140003F22
0x140003ec3  xor     sil, sil
0x140003ec6  cmp     r8w, 40h ; '@'
0x140003ecb  jb      short loc_140003ED3
0x140003ecd  mov     r8d, 40h ; '@'
0x140003ed3  mov     eax, r13d
0x140003ed6  cmp     ax, r8w
0x140003eda  jnb     short loc_140003F25
0x140003edc  movzx   edx, ax
0x140003edf  movzx   ecx, byte ptr [rdx+rdi+0DCh]
0x140003ee7  cmp     [rdx+rbx+0DCh], cl
0x140003eee  jnz     short loc_140003EF5
0x140003ef0  inc     ax
0x140003ef3  jmp     short loc_140003ED6
0x140003ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003efc  cmp     rcx, r14
0x140003eff  jz      short loc_140003F22
0x140003f01  mov     edx, [rcx+2Ch]
0x140003f04  test    dl, 20h
0x140003f07  jz      short loc_140003F22
0x140003f09  mov     rcx, [rcx+18h]
0x140003f0d  lea     r8, WPP_cca3db0522623f5e31396e1525c29988_Traceguids
0x140003f14  movzx   r9d, ax
0x140003f18  mov     edx, 0Ch
0x140003f1d  call    WPP_SF_d
0x140003f22  mov     sil, 1
0x140003f25  mov     rax, [rdi+78h]
0x140003f29  cmp     [rbx+78h], rax
0x140003f2d  jl      loc_1400041DE
0x140003f33  test    byte ptr [rbx+30h], 8
0x140003f37  jnz     loc_1400041DE
0x140003f3d  or      word ptr [rdi+30h], 1
0x140003f42  xor     r9d, r9d; Alertable
0x140003f45  mov     [rdi], r13
0x140003f48  xor     r8d, r8d; WaitMode
0x140003f4b  mov     [rdi+8], r13
0x140003f4f  xor     edx, edx; WaitReason
0x140003f51  mov     rcx, [rbx+28h]; Object
0x140003f55  mov     [rsp+58h+Timeout], r13; Timeout
0x140003f5a  call    cs:__imp_KeWaitForSingleObject
0x140003f61  nop     dword ptr [rax+rax+00h]
0x140003f66  mov     rdx, [rbx+28h]
0x140003f6a  cmp     [rdx+58h], r13
0x140003f6e  jz      short loc_140003FBC
0x140003f70  cmp     [rdx+60h], rbx
0x140003f74  jz      short loc_140003FC4
0x140003f76  mov     rax, [rbx+10h]
0x140003f7a  test    rax, rax
0x140003f7d  jz      short loc_140003FA6
0x140003f7f  mov     rcx, [rbx+18h]
0x140003f83  test    rcx, rcx
0x140003f86  jz      short loc_140003F9A
0x140003f88  mov     [rcx+10h], rax
0x140003f8c  mov     rcx, [rbx+10h]
0x140003f90  mov     rax, [rbx+18h]
0x140003f94  mov     [rcx+18h], rax
0x140003f98  jmp     short loc_140003FA6
0x140003f9a  mov     [rdx+58h], rax
0x140003f9e  mov     rax, [rbx+10h]
0x140003fa2  mov     [rax+18h], r13
0x140003fa6  mov     rax, [rdx+60h]
0x140003faa  mov     [rax+10h], rbx
0x140003fae  mov     rax, [rdx+60h]
0x140003fb2  mov     [rbx+18h], rax
0x140003fb6  mov     [rbx+10h], r13
0x140003fba  jmp     short loc_140003FC0
0x140003fbc  mov     [rdx+58h], rbx
0x140003fc0  mov     [rdx+60h], rbx
0x140003fc4  mov     rcx, [rbx+28h]; Mutex
0x140003fc8  xor     edx, edx; Wait
0x140003fca  inc     dword ptr [rbx+34h]
0x140003fcd  call    cs:__imp_KeReleaseMutex
0x140003fd4  nop     dword ptr [rax+rax+00h]
0x140003fd9  test    byte ptr [rdi+30h], 10h
0x140003fdd  jz      short loc_140003FE4
0x140003fdf  or      word ptr [rbx+30h], 10h
0x140003fe4  mov     eax, [rdi+38h]
0x140003fe7  mov     rdx, rbx
0x140003fea  add     [rbx+38h], eax
0x140003fed  mov     rcx, rbp
0x140003ff0  call    HacDereference
0x140003ff5  mov     rcx, [rdi+28h]; Object
0x140003ff9  xor     r9d, r9d; Alertable
0x140003ffc  xor     r8d, r8d; WaitMode
0x140003fff  mov     [rsp+58h+Timeout], r13; Timeout
0x140004004  xor     edx, edx; WaitReason
0x140004006  call    cs:__imp_KeWaitForSingleObject
0x14000400d  nop     dword ptr [rax+rax+00h]
0x140004012  mov     rdx, [rdi+28h]
0x140004016  test    sil, sil
0x140004019  jz      loc_1400040C9
0x14000401f  cmp     [rdx+58h], r13
0x140004023  jz      short loc_140004071
0x140004025  cmp     [rdx+60h], rdi
0x140004029  jz      short loc_140004079
0x14000402b  mov     rax, [rdi+10h]
0x14000402f  test    rax, rax
0x140004032  jz      short loc_14000405B
0x140004034  mov     rcx, [rdi+18h]
0x140004038  test    rcx, rcx
0x14000403b  jz      short loc_14000404F
0x14000403d  mov     [rcx+10h], rax
0x140004041  mov     rcx, [rdi+10h]
0x140004045  mov     rax, [rdi+18h]
0x140004049  mov     [rcx+18h], rax
0x14000404d  jmp     short loc_14000405B
0x14000404f  mov     [rdx+58h], rax
0x140004053  mov     rax, [rdi+10h]
0x140004057  mov     [rax+18h], r13
0x14000405b  mov     rax, [rdx+60h]
0x14000405f  mov     [rax+10h], rdi
0x140004063  mov     rax, [rdx+60h]
0x140004067  mov     [rdi+18h], rax
  ... truncated ...
```
