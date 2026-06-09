# NtfsWriteFcbUsnRecordToJournal

- ea: `0x140142360`
- end: `0x140142c05`
- name: `NtfsWriteFcbUsnRecordToJournal`
- size: `2213`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1401413b0`
- `0x140190b80`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000d510`
- `0x1400410a8`
- `0x1400596c0`
- `0x1401250b0`
- `0x140142360`
- `0x140142c10`
- `0x1401436e0`
- `0x1401620c0`
- `0x1401e0660`
- `0x14026e5e0`
- `0x14029b558`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140142aaa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a7500`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140142aaa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a7500`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401424ad`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401424ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140142a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a74e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140142a8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a74e9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014277c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014277c`
- `ntoskrnl!CcUnpinData` at `0x140142ba3`
- `ntoskrnl!CcUnpinData` at `0x140142bc4`
- `ntoskrnl!CcUnpinData` at `0x140142be5`
- `ntoskrnl!CcUnpinData` at `0x140142ba3`
- `ntoskrnl!CcUnpinData` at `0x140142bc4`
- `ntoskrnl!CcUnpinData` at `0x140142be5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140142464`
- `ntoskrnl!ExAcquireFastMutex` at `0x140142464`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401428f0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a74b7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401428f0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402a74b7`

## pseudocode

```c
void __fastcall NtfsWriteFcbUsnRecordToJournal(__int64 a1, __int64 a2, int *Src, __int64 a4, __int64 a5, __int64 a6)
{
  bool v10; // si
  __int64 v11; // rcx
  unsigned int v12; // r14d
  __int64 v13; // rdx
  unsigned int *v14; // r9
  int v15; // eax
  unsigned int *v16; // rax
  _DWORD *v17; // rax
  int v18; // eax
  unsigned int v19; // ecx
  int v20; // eax
  PVOID PoolWithTag; // rax
  unsigned int *v22; // r8
  __int64 v23; // r8
  unsigned int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned int v26; // eax
  void *v27; // rcx
  int v28; // eax
  int v29; // r9d
  unsigned int *v30; // r8
  void *Srca; // [rsp+20h] [rbp-128h]
  int v32; // [rsp+30h] [rbp-118h]
  unsigned int *Entry; // [rsp+58h] [rbp-F0h]
  __int64 v34; // [rsp+68h] [rbp-E0h]
  __int64 v35; // [rsp+70h] [rbp-D8h]
  _DWORD *v36; // [rsp+80h] [rbp-C8h]
  unsigned int *v37; // [rsp+80h] [rbp-C8h]
  PVOID v38[19]; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v39; // [rsp+158h] [rbp+10h] BYREF
  int *v40; // [rsp+160h] [rbp+18h]

  v40 = Src;
  v39 = a2;
  memset(v38, 0, 0x58u);
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 96) + 4LL) & 0x80000) == 0 )
    return;
  v10 = Src[10] < 0;
  if ( !*(_QWORD *)(a4 + 496) )
    NtfsSnapshotScb(a1, a4);
  v11 = *(_QWORD *)(a4 + 32);
  v34 = v11;
  v12 = 4096 - (v11 & 0xFFF);
  if ( a5 && *(int *)(a5 + 248) < 0 )
  {
    Entry = 0;
    v35 = *(_QWORD *)(a6 + 16);
    if ( !v35 )
      v35 = *(_QWORD *)(a5 + 48);
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
    v13 = v35;
    if ( !v35
      || (*(_DWORD *)(*(_QWORD *)(a2 + 96) + 8008LL) & 1) == 0
      || (v15 = *(_DWORD *)(v35 + 144), (v15 & 5) == 0)
      || (v15 & 2) != 0 )
    {
      v14 = 0;
      goto LABEL_46;
    }
    v16 = (unsigned int *)ExAllocateFromLookasideListEx(&NtfsRangeTrackLocalStructLookasideList);
    v14 = v16;
    Entry = v16;
    if ( !v16 )
    {
LABEL_32:
      v13 = v35;
LABEL_46:
      if ( v14 )
      {
        *(_QWORD *)(a6 + 16) = v13;
        *(_DWORD *)(v13 + 144) |= 0x10u;
        *(_DWORD *)(v13 + 144) |= 0x20u;
        if ( v13 == *(_QWORD *)(a5 + 48) )
          *(_QWORD *)(a5 + 48) = 0;
      }
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a2 + 104) + 8LL));
      v27 = Entry;
      if ( Entry )
      {
        v30 = (unsigned int *)*((_QWORD *)Entry + 18);
        if ( v30 && v30 != Entry + 4 )
        {
          ExFreePoolWithTag(*((PVOID *)Entry + 18), 0);
          v27 = Entry;
        }
        ExFreeToLookasideListEx(&NtfsRangeTrackLocalStructLookasideList, v27);
        v11 = v34;
      }
      else
      {
        v11 = v34;
      }
      goto LABEL_49;
    }
    *((_QWORD *)v16 + 18) = 0;
    *((_QWORD *)v16 + 17) = v35;
    v17 = v16 + 2;
    v36 = v17;
    if ( *(_QWORD *)(v35 + 136) )
    {
      v22 = v14 + 18;
      v14[18] = 0;
      *((_WORD *)v14 + 38) = 1;
      *v14 = 80;
      *v17 = 0;
      *((_QWORD *)v14 + 10) = 0;
      *((_QWORD *)v14 + 11) = -*(_QWORD *)(*(_QWORD *)(a2 + 96) + 8016LL)
                            & (*(_QWORD *)(*(_QWORD *)(a2 + 96) + 8016LL) + *(_QWORD *)(v35 + 136) - 1LL);
      PoolWithTag = v14 + 4;
      *((_QWORD *)v14 + 18) = v14 + 4;
    }
    else
    {
      *((_OWORD *)v14 + 6) = 0;
      *((_OWORD *)v14 + 7) = 0;
      *((_QWORD *)v14 + 16) = 0;
      *((_QWORD *)v14 + 13) = 1;
      v32 = (int)v14;
      v18 = FsLibRangeTrackBufferExtents(*((_QWORD *)v14 + 17), v14 + 4, 64);
      *v36 = v18;
      if ( (int)(v18 + 0x80000000) >= 0 && v18 != -1073741789 )
      {
        v14 = Entry;
        goto LABEL_32;
      }
      v14 = Entry;
      v19 = *Entry;
      if ( !*Entry && !v18 )
        goto LABEL_32;
      v37 = Entry + 18;
      if ( Entry[18] == 1 )
      {
        v32 = (int)Entry;
        v20 = FsLibRangeTrackBufferExtents(*((_QWORD *)Entry + 17), Entry + 4, 80);
        v14 = Entry;
        Entry[2] = v20;
        if ( v20 < 0 || !*((_QWORD *)Entry + 10) && *((_QWORD *)Entry + 11) == -1 )
          goto LABEL_32;
        PoolWithTag = Entry + 4;
        *((_QWORD *)Entry + 18) = Entry + 4;
        v22 = Entry + 18;
LABEL_23:
        if ( v12 < 0x50 )
        {
          *(_QWORD *)(a1 + 16) |= 0x80000uLL;
          NtOfsPutData(a1, a4, -1, v12, 0);
          *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
          v34 += v12;
          v12 = 0;
          v14 = Entry;
          PoolWithTag = (PVOID)*((_QWORD *)Entry + 18);
          v22 = v37;
        }
        if ( *v22 )
        {
          v23 = v14[1];
          if ( v12 && (unsigned int)v23 >= v12 )
            v23 = v12;
          v32 = (int)v14;
          v24 = FsLibRangeTrackBufferExtents(*((_QWORD *)v14 + 17), PoolWithTag, v23);
          v14 = Entry;
          Entry[2] = v24;
        }
        *(_WORD *)(*((_QWORD *)v14 + 18) + 4LL) = 4;
        *(_WORD *)(*((_QWORD *)v14 + 18) + 6LL) = 0;
        *(_DWORD *)(*((_QWORD *)v14 + 18) + 48LL) = Src[10];
        *(_DWORD *)(*((_QWORD *)v14 + 18) + 52LL) = Src[11];
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 16LL) = 0;
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 8LL) = *((_QWORD *)Src + 1);
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 32LL) = 0;
        *(_QWORD *)(*((_QWORD *)v14 + 18) + 24LL) = *((_QWORD *)Src + 2);
        while ( (v14[2] & 0x80000000) == 0 )
        {
          **((_DWORD **)v14 + 18) = *v14;
          *(_QWORD *)(*((_QWORD *)v14 + 18) + 40LL) = v34;
          *(_WORD *)(*((_QWORD *)v14 + 18) + 62LL) = 16;
          *(_QWORD *)(a1 + 16) |= 0x80000uLL;
          NtOfsPutData(a1, a4, -1, *v14, *((void **)v14 + 18));
          v25 = *(_QWORD *)(a1 + 16) & 0xFFFFFFFFFFF7FFFFuLL;
          *(_QWORD *)(a1 + 16) = v25;
          v14 = Entry;
          v34 += *Entry;
          v12 = 4096 - (v34 & 0xFFF);
          if ( !Entry[2] )
            break;
          if ( v12 < 0x50 )
          {
            *(_QWORD *)(a1 + 16) = v25 | 0x80000;
            NtOfsPutData(a1, a4, -1, v12, 0);
            *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
            v34 += v12;
            v14 = Entry;
          }
          v32 = (int)v14;
          v26 = FsLibRangeTrackBufferExtents(*((_QWORD *)v14 + 17), *((_QWORD *)v14 + 18), v14[1]);
          v14 = Entry;
          Entry[2] = v26;
        }
        goto LABEL_32;
      }
      if ( v19 > 0x1000 )
        v19 = 4096;
      Entry[1] = v19;
      PoolWithTag = ExAllocatePoolWithTag(PoolType, v19, 0x5546744Eu);
      v14 = Entry;
      *((_QWORD *)Entry + 18) = PoolWithTag;
      if ( !PoolWithTag )
        goto LABEL_32;
      v22 = Entry + 18;
    }
    v37 = v22;
    goto LABEL_23;
  }
LABEL_49:
  if ( v12 < *Src )
  {
    *(_QWORD *)(a1 + 16) |= 0x80000uLL;
    NtOfsPutData(a1, a4, -1, v12, 0);
    *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
    v11 = v12 + v34;
    v34 = v11;
  }
  *((_QWORD *)Src + 3) = v11;
  *((_QWORD *)Src + 4) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a1 + 16) |= 0x80000uLL;
  NtOfsPutData(a1, a4, -1, *Src, Src);
  *(_QWORD *)(a1 + 16) &= ~0x80000uLL;
  if ( (Src[10] & 0x200) == 0 )
  {
    v28 = *(_DWORD *)(a2 + 4);
    if ( (v28 & 1) == 0 )
    {
      if ( (v28 & 0x800) == 0 )
        NtfsGrowStandardInformation(a1, a2);
      if ( Src[10] < 0 )
      {
        v39 = v34;
        LOBYTE(v32) = 0;
        if ( !(unsigned __int8)NtfsLookupInFileRecord(a1, a2, a2 + 8, 16, 0, 0, v32, 0, 0, v38) )
        {
          NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 2824709, v29, a2 + 8, a2, 0);
          NtfsAttachRepairInfoPriv(a1, 256, 0, 0xA3002B1A05LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 2824709);
          NtfsRaiseStatusInternal(a1, -1073741566, a2 + 8, a2, 2824709);
          __debugbreak();
        }
        LODWORD(Srca) = 8;
        NtfsChangeAttributeValue(a1, a2, 64, (int)&v39, (SIZE_T)Srca, 0, 0, 0, 0, v38);
      }
    }
  }
  if ( v10 )
  {
    if ( v38[2] )
    {
      CcUnpinData(v38[2]);
      v38[2] = 0;
    }
    if ( v38[5] )
    {
      CcUnpinData(v38[5]);
      v38[5] = 0;
    }
    if ( v38[9] )
      CcUnpinData(v38[9]);
  }
}

```

## disassembly

```asm
0x140142360  mov     [rsp+arg_10], r8
0x140142365  mov     [rsp+arg_8], rdx
0x14014236a  mov     [rsp+arg_0], rcx
0x14014236f  push    rbx
0x140142370  push    rsi
0x140142371  push    rdi
0x140142372  push    r12
0x140142374  push    r13
0x140142376  push    r14
0x140142378  push    r15
0x14014237a  sub     rsp, 110h
0x140142381  mov     r12, r9
0x140142384  mov     rbx, r8
0x140142387  mov     r13, rdx
0x14014238a  mov     rdi, rcx
0x14014238d  xor     edx, edx; Val
0x14014238f  mov     r8d, 58h ; 'X'; Size
0x140142395  lea     rcx, [rsp+148h+var_98]; void *
0x14014239d  call    memset
0x1401423a2  mov     rax, [r13+60h]
0x1401423a6  test    dword ptr [rax+4], 80000h
0x1401423ad  jz      loc_140142BF1
0x1401423b3  mov     [rsp+148h+var_B0], 0FFFFFFFFFFFFFFFFh
0x1401423bf  xor     al, al
0x1401423c1  mov     [rsp+148h+var_F8], al
0x1401423c5  movzx   esi, al
0x1401423c8  mov     eax, 1
0x1401423cd  cmp     dword ptr [rbx+28h], 0
0x1401423d1  cmovl   esi, eax
0x1401423d4  mov     [rsp+148h+var_E8], sil
0x1401423d9  cmp     qword ptr [r12+1F0h], 0
0x1401423e2  jz      loc_140142B34
0x1401423e8  mov     rcx, [r12+20h]
0x1401423ed  mov     [rsp+148h+var_E0], rcx
0x1401423f2  mov     [rsp+148h+var_C0], rcx
0x1401423fa  mov     eax, ecx
0x1401423fc  and     eax, 0FFFh
0x140142401  mov     r14d, 1000h
0x140142407  sub     r14d, eax
0x14014240a  mov     [rsp+148h+var_D0], r14d
0x14014240f  mov     rax, [rsp+148h+arg_20]
0x140142417  test    rax, rax
0x14014241a  jz      loc_140142911
0x140142420  cmp     dword ptr [rax+0F8h], 0
0x140142427  jge     loc_140142911
0x14014242d  xor     r15d, r15d
0x140142430  mov     [rsp+148h+Entry], r15
0x140142435  mov     rcx, [rsp+148h+arg_28]
0x14014243d  mov     rcx, [rcx+10h]
0x140142441  mov     [rsp+148h+var_D8], rcx
0x140142446  test    rcx, rcx
0x140142449  jnz     short loc_140142454
0x14014244b  mov     rcx, [rax+30h]
0x14014244f  mov     [rsp+148h+var_D8], rcx
0x140142454  mov     [rsp+148h+var_A8], rcx
0x14014245c  mov     rcx, [r13+68h]
0x140142460  add     rcx, 8; FastMutex
0x140142464  call    cs:__imp_ExAcquireFastMutex
0x14014246b  nop     dword ptr [rax+rax+00h]
0x140142470  mov     [rsp+148h+var_F8], 1
0x140142475  mov     rdx, [rsp+148h+var_D8]
0x14014247a  test    rdx, rdx
0x14014247d  jz      short loc_14014248E
0x14014247f  mov     rax, [r13+60h]
0x140142483  mov     ecx, [rax+1F48h]
0x140142489  test    cl, 1
0x14014248c  jnz     short loc_140142498
0x14014248e  mov     r9, [rsp+148h+Entry]
0x140142493  jmp     loc_1401428DF
0x140142498  mov     eax, [rdx+90h]
0x14014249e  test    al, 5
0x1401424a0  jz      short loc_14014248E
0x1401424a2  test    al, 2
0x1401424a4  jnz     short loc_14014248E
0x1401424a6  lea     rcx, NtfsRangeTrackLocalStructLookasideList; Lookaside
0x1401424ad  call    cs:__imp_ExAllocateFromLookasideListEx
0x1401424b4  nop     dword ptr [rax+rax+00h]
0x1401424b9  mov     r9, rax
0x1401424bc  mov     [rsp+148h+Entry], rax
0x1401424c1  test    rax, rax
0x1401424c4  jz      loc_1401426F6
0x1401424ca  mov     [rax+90h], r15
0x1401424d1  mov     rcx, [rsp+148h+var_D8]
0x1401424d6  mov     [rax+88h], rcx
0x1401424dd  add     rax, 8
0x1401424e1  mov     [rsp+148h+var_C8], rax
0x1401424e9  mov     edx, 1
0x1401424ee  cmp     qword ptr [rcx+88h], 0
0x1401424f6  jnz     loc_140142700
0x1401424fc  lea     rcx, [r9+60h]
0x140142500  mov     [rsp+148h+var_B8], rcx
0x140142508  xorps   xmm0, xmm0
0x14014250b  xor     eax, eax
0x14014250d  movups  xmmword ptr [rcx], xmm0
0x140142510  movups  xmmword ptr [rcx+10h], xmm0
0x140142514  mov     [rcx+20h], rax
0x140142518  mov     [r9+68h], rdx
0x14014251c  lea     rdx, [r9+10h]
0x140142520  mov     qword ptr [rsp+148h+var_118], r9
0x140142525  mov     qword ptr [rsp+148h+var_120], rcx
0x14014252a  mov     r8d, 40h ; '@'
0x140142530  mov     rcx, [r9+88h]
0x140142537  call    FsLibRangeTrackBufferExtents
0x14014253c  mov     rcx, [rsp+148h+var_C8]
0x140142544  mov     [rcx], eax
0x140142546  mov     edx, 80000000h
0x14014254b  lea     ecx, [rax+rdx]
0x14014254e  test    edx, ecx
0x140142550  jz      loc_1401428CA
0x140142556  mov     r9, [rsp+148h+Entry]
0x14014255b  mov     ecx, [r9]
0x14014255e  test    ecx, ecx
0x140142560  jnz     short loc_14014256A
0x140142562  test    eax, eax
0x140142564  jz      loc_1401426F6
0x14014256a  lea     rax, [r9+48h]
0x14014256e  mov     [rsp+148h+var_C8], rax
0x140142576  cmp     dword ptr [rax], 1
0x140142579  jnz     loc_140142760
0x14014257f  mov     qword ptr [rsp+148h+var_118], r9
0x140142584  lea     rcx, [r9+60h]
0x140142588  mov     qword ptr [rsp+148h+var_120], rcx
0x14014258d  mov     r8d, 50h ; 'P'
0x140142593  lea     rdx, [r9+10h]
0x140142597  mov     rcx, [r9+88h]
0x14014259e  call    FsLibRangeTrackBufferExtents
0x1401425a3  mov     r9, [rsp+148h+Entry]
0x1401425a8  mov     [r9+8], eax
0x1401425ac  test    eax, eax
0x1401425ae  js      loc_1401426F6
0x1401425b4  cmp     qword ptr [r9+50h], 0
0x1401425b9  jnz     short loc_1401425C6
0x1401425bb  cmp     qword ptr [r9+58h], 0FFFFFFFFFFFFFFFFh
0x1401425c0  jz      loc_1401426F6
0x1401425c6  lea     rax, [r9+10h]
0x1401425ca  mov     [r9+90h], rax
0x1401425d1  lea     r8, [r9+48h]
0x1401425d5  cmp     r14d, 50h ; 'P'
0x1401425d9  jnb     short loc_14014263A
0x1401425db  or      qword ptr [rdi+10h], 80000h
0x1401425e3  mov     [rsp+148h+Src], r15; Src
0x1401425e8  mov     r9d, r14d; int
0x1401425eb  mov     r8, 0FFFFFFFFFFFFFFFFh; int
0x1401425f2  mov     rdx, r12; int
0x1401425f5  mov     rcx, rdi; int
0x1401425f8  call    NtOfsPutData
0x1401425fd  nop
0x1401425fe  and     qword ptr [rdi+10h], 0FFFFFFFFFFF7FFFFh
0x140142606  mov     eax, r14d
0x140142609  mov     rcx, [rsp+148h+var_E0]
0x14014260e  add     rcx, rax
0x140142611  mov     [rsp+148h+var_E0], rcx
0x140142616  mov     [rsp+148h+var_C0], rcx
0x14014261e  mov     r14d, r15d
0x140142621  mov     [rsp+148h+var_D0], r15d
0x140142626  mov     r9, [rsp+148h+Entry]
0x14014262b  mov     rax, [r9+90h]
0x140142632  mov     r8, [rsp+148h+var_C8]
0x14014263a  cmp     dword ptr [r8], 0
0x14014263e  jz      short loc_14014267B
0x140142640  mov     r8d, [r9+4]
0x140142644  test    r14d, r14d
0x140142647  jz      loc_1401428BD
0x14014264d  cmp     r8d, r14d
0x140142650  jb      short loc_140142655
0x140142652  mov     r8d, r14d
0x140142655  lea     rcx, [r9+60h]
0x140142659  mov     qword ptr [rsp+148h+var_118], r9
0x14014265e  mov     qword ptr [rsp+148h+var_120], rcx
0x140142663  mov     rdx, rax
0x140142666  mov     rcx, [r9+88h]
0x14014266d  call    FsLibRangeTrackBufferExtents
0x140142672  mov     r9, [rsp+148h+Entry]
0x140142677  mov     [r9+8], eax
0x14014267b  mov     rax, [r9+90h]
0x140142682  mov     ecx, 4
0x140142687  mov     [rax+4], cx
0x14014268b  mov     rax, [r9+90h]
0x140142692  mov     [rax+6], r15w
0x140142697  mov     rcx, [r9+90h]
0x14014269e  mov     eax, [rbx+28h]
0x1401426a1  mov     [rcx+30h], eax
0x1401426a4  mov     rcx, [r9+90h]
0x1401426ab  mov     eax, [rbx+2Ch]
0x1401426ae  mov     [rcx+34h], eax
0x1401426b1  mov     rax, [r9+90h]
0x1401426b8  mov     [rax+10h], r15
0x1401426bc  mov     rcx, [r9+90h]
0x1401426c3  mov     rax, [rbx+8]
0x1401426c7  mov     [rcx+8], rax
0x1401426cb  mov     rax, [r9+90h]
0x1401426d2  mov     [rax+20h], r15
0x1401426d6  mov     rcx, [r9+90h]
0x1401426dd  mov     rax, [rbx+10h]
0x1401426e1  mov     [rcx+18h], rax
0x1401426e5  mov     r8d, 10h
0x1401426eb  cmp     dword ptr [r9+8], 0
0x1401426f0  jge     loc_1401427A3
0x1401426f6  mov     rdx, [rsp+148h+var_D8]
0x1401426fb  jmp     loc_1401428DF
0x140142700  lea     r8, [r9+48h]
0x140142704  mov     [r8], r15d
0x140142707  mov     [r9+4Ch], dx
0x14014270c  mov     dword ptr [r9], 50h ; 'P'
0x140142713  mov     [rax], r15d
0x140142716  mov     [r9+50h], r15
0x14014271a  mov     rax, [r13+60h]
0x14014271e  mov     rdx, [rax+1F50h]
0x140142725  mov     rcx, [rcx+88h]
0x14014272c  dec     rcx
0x14014272f  add     rcx, rdx
0x140142732  neg     rdx
0x140142735  and     rcx, rdx
0x140142738  mov     [r9+58h], rcx
0x14014273c  lea     rax, [r9+10h]
0x140142740  mov     [r9+90h], rax
0x140142747  lea     rcx, [r9+60h]
0x14014274b  mov     [rsp+148h+var_C8], r8
0x140142753  mov     [rsp+148h+var_B8], rcx
0x14014275b  jmp     loc_1401425D5
0x140142760  mov     eax, 1000h
0x140142765  cmp     ecx, eax
0x140142767  cmova   ecx, eax
0x14014276a  mov     edx, ecx; NumberOfBytes
0x14014276c  mov     [r9+4], edx
0x140142770  mov     ecx, cs:PoolType; PoolType
0x140142776  mov     r8d, 5546744Eh; Tag
0x14014277c  call    cs:__imp_ExAllocatePoolWithTag
0x140142783  nop     dword ptr [rax+rax+00h]
0x140142788  mov     r9, [rsp+148h+Entry]
0x14014278d  mov     [r9+90h], rax
0x140142794  test    rax, rax
0x140142797  jz      loc_1401426F6
0x14014279d  lea     r8, [r9+48h]
0x1401427a1  jmp     short loc_140142747
0x1401427a3  mov     rcx, [r9+90h]
0x1401427aa  mov     eax, [r9]
0x1401427ad  mov     [rcx], eax
0x1401427af  mov     rax, [r9+90h]
0x1401427b6  mov     r14, [rsp+148h+var_E0]
0x1401427bb  mov     [rax+28h], r14
0x1401427bf  mov     rax, [r9+90h]
0x1401427c6  mov     [rax+3Eh], r8w
0x1401427cb  or      qword ptr [rdi+10h], 80000h
0x1401427d3  mov     rax, [r9+90h]
0x1401427da  mov     [rsp+148h+Src], rax; Src
0x1401427df  mov     r9d, [r9]; int
0x1401427e2  mov     r8, 0FFFFFFFFFFFFFFFFh; int
0x1401427e9  mov     rdx, r12; int
0x1401427ec  mov     rcx, rdi; int
0x1401427ef  call    NtOfsPutData
0x1401427f4  nop
0x1401427f5  mov     rcx, [rdi+10h]
0x1401427f9  btr     rcx, 13h
0x1401427fe  mov     [rdi+10h], rcx
0x140142802  mov     r9, [rsp+148h+Entry]
0x140142807  mov     eax, [r9]
0x14014280a  add     r14, rax
0x14014280d  mov     [rsp+148h+var_E0], r14
0x140142812  mov     [rsp+148h+var_C0], r14
0x14014281a  mov     eax, r14d
0x14014281d  and     eax, 0FFFh
0x140142822  mov     r14d, 1000h
0x140142828  sub     r14d, eax
0x14014282b  mov     [rsp+148h+var_D0], r14d
0x140142830  cmp     dword ptr [r9+8], 0
0x140142835  jz      loc_1401426F6
0x14014283b  cmp     r14d, 50h ; 'P'
0x14014283f  jnb     short loc_14014288A
0x140142841  bts     rcx, 13h
0x140142846  mov     [rdi+10h], rcx
0x14014284a  mov     [rsp+148h+Src], r15; Src
0x14014284f  mov     r9d, r14d; int
0x140142852  mov     r8, 0FFFFFFFFFFFFFFFFh; int
0x140142859  mov     rdx, r12; int
0x14014285c  mov     rcx, rdi; int
0x14014285f  call    NtOfsPutData
0x140142864  nop
0x140142865  and     qword ptr [rdi+10h], 0FFFFFFFFFFF7FFFFh
0x14014286d  mov     eax, r14d
0x140142870  mov     rcx, [rsp+148h+var_E0]
0x140142875  add     rcx, rax
0x140142878  mov     [rsp+148h+var_E0], rcx
0x14014287d  mov     [rsp+148h+var_C0], rcx
0x140142885  mov     r9, [rsp+148h+Entry]
0x14014288a  lea     rax, [r9+60h]
0x14014288e  mov     qword ptr [rsp+148h+var_118], r9
0x140142893  mov     qword ptr [rsp+148h+var_120], rax
0x140142898  mov     r8d, [r9+4]
0x14014289c  mov     rdx, [r9+90h]
0x1401428a3  mov     rcx, [r9+88h]
0x1401428aa  call    FsLibRangeTrackBufferExtents
0x1401428af  mov     r9, [rsp+148h+Entry]
0x1401428b4  mov     [r9+8], eax
0x1401428b8  jmp     loc_1401426E5
0x1401428bd  mov     rcx, [rsp+148h+var_B8]
0x1401428c5  jmp     loc_140142659
0x1401428ca  cmp     eax, 0C0000023h
0x1401428cf  jz      loc_140142556
0x1401428d5  mov     r9, [rsp+148h+Entry]
  ... truncated ...
```
