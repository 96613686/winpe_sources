# OpenAttributeForRestart

- ea: `0x14015d274`
- end: `0x14015d63d`
- name: `OpenAttributeForRestart`
- size: `969`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `reparse_path`

## callers

- `0x14015d1d8`
- `0x14015e3f4`
- `0x14015e9f0`
- `0x1401af1c4`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140014e74`
- `0x14001e810`
- `0x1400224cc`
- `0x140022a00`
- `0x1400286d0`
- `0x140029cb0`
- `0x14002b680`
- `0x140031410`
- `0x14003c4e4`
- `0x14012c1ec`
- `0x140150bc0`
- `0x14015d274`
- `0x140163f78`
- `0x140260578`

## import_xrefs

- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14015d62c`
- `ntoskrnl!CcSetAdditionalCacheAttributes` at `0x14015d62c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a89c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a89c4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402c952c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402c952c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14015d376`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c9566`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c962a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14015d376`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c9566`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c962a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14015d3bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8a09`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8a4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c968c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c9706`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c97ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14015d3bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8a09`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a8a4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c968c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c9706`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c97ce`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14015d559`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402c9757`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14015d559`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402c9757`
- `ntoskrnl!CcFlushCache` at `0x1402c992b`
- `ntoskrnl!CcFlushCache` at `0x1402c992b`

## pseudocode

```c
void __fastcall OpenAttributeForRestart(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // r13
  __int64 v6; // r14
  __int64 v7; // r12
  __int64 v8; // rsi
  unsigned int v9; // ecx
  char *Pointer; // r12
  __int64 v11; // r15
  LONGLONG v12; // r8
  unsigned int v13; // r15d
  unsigned __int16 *v14; // r9
  __int16 v15; // r11
  __int64 v16; // r8
  _DWORD *v17; // rsi
  char v18; // r12
  __int64 v19; // rcx
  __int64 v20; // r10
  char *v21; // rcx
  _QWORD *v22; // rcx
  unsigned __int16 *v23; // rdx
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  _OWORD *PoolWithTag; // r12
  __int64 v28; // rdx
  __int64 RestartTableIndex; // r15
  unsigned __int16 *v30; // rax
  __int64 RestartTableFromIndex; // rsi
  int v32; // ecx
  __int64 v33; // r13
  __int64 PrerestartScb; // rax
  unsigned __int16 *v35; // rdx
  __int64 v36; // r8
  char *v37; // r8
  struct _ERESOURCE *v38; // rcx
  char v39; // r8
  char v40; // r15
  unsigned int v41; // edx
  int v42; // ecx
  __int64 v43; // rsi
  _QWORD *v44; // rax
  int v45; // edx
  signed __int64 v46; // r9
  signed __int64 v47; // r8
  _QWORD *v48; // rax
  int v49; // ecx
  signed __int64 v50; // r8
  signed __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // [rsp+60h] [rbp-78h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+68h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+70h] [rbp-68h] BYREF
  _OWORD *v56; // [rsp+80h] [rbp-58h]
  __int64 v57; // [rsp+88h] [rbp-50h] BYREF
  _QWORD v58[9]; // [rsp+90h] [rbp-48h] BYREF
  __int64 v62; // [rsp+F8h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = a1;
  if ( !*a4 )
  {
    v13 = 0;
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a2 + 4920), 1u);
    v14 = *(unsigned __int16 **)(*(_QWORD *)(v6 + 4920) + 208LL);
    v15 = v14[3] & 1;
    v16 = *(unsigned __int16 *)(v5 + 12);
    if ( v15 )
    {
      if ( (_WORD)v16 && (unsigned __int16)v16 <= v14[1] )
      {
        v20 = *(unsigned __int16 *)(v5 + 12);
LABEL_25:
        if ( v15 )
          v21 = (char *)v14 + *v14 * ((int)v16 - 1) + 24;
        else
          v21 = (char *)v14 + v20;
        v17 = (_DWORD *)(v6 + 4892);
        if ( *(_DWORD *)v21 == -1 )
        {
          v18 = 0;
          if ( *v17 )
            *a4 = *(_QWORD *)(*((_QWORD *)v21 + 4) + 24LL);
          else
            v13 = *((_DWORD *)v21 + 1);
LABEL_15:
          ExReleaseResourceLite(*(PERESOURCE *)(v6 + 4920));
          if ( v18 )
          {
            PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x30u, 0x5246744Eu);
            v56 = PoolWithTag;
            *PoolWithTag = 0;
            PoolWithTag[1] = 0;
            PoolWithTag[2] = 0;
            *((_DWORD *)PoolWithTag + 4) = *(unsigned __int16 *)(v5 + 12);
            ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 832), 1u);
            v28 = v6 + 832;
            if ( *(_DWORD *)(v6 + 4892) )
            {
              LODWORD(RestartTableIndex) = *(unsigned __int16 *)(v5 + 12);
              RestartTableFromIndex = NtfsAllocateRestartTableFromIndex(a1, v28, *(unsigned __int16 *)(v5 + 12));
            }
            else
            {
              RestartTableIndex = (unsigned int)NtfsAllocateRestartTableIndex(a1, v28);
              v30 = *(unsigned __int16 **)(v6 + 1040);
              if ( (v30[3] & 1) != 0 )
                RestartTableFromIndex = (__int64)v30 + (unsigned int)*v30 * ((_DWORD)RestartTableIndex - 1) + 24;
              else
                RestartTableFromIndex = (__int64)v30 + RestartTableIndex;
            }
            v32 = 128;
            if ( *(_WORD *)(v5 + 22) )
              v32 = 160;
            *(_DWORD *)(RestartTableFromIndex + 8) = v32;
            *(_DWORD *)(RestartTableFromIndex + 4) = *(unsigned __int16 *)(v5 + 22) << 9;
            *(_QWORD *)(RestartTableFromIndex + 16) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 192) + 184LL) + 8LL);
            if ( !*(_DWORD *)(v6 + 4892) )
            {
              ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v6 + 4920), 1u);
              v33 = NtfsAllocateRestartTableFromIndex(a1, *(_QWORD *)(v6 + 4920), *(unsigned __int16 *)(v5 + 12));
              v62 = v33;
              ExReleaseResourceLite(*(PERESOURCE *)(v6 + 4920));
              *(_DWORD *)(v33 + 40) = *(_DWORD *)(RestartTableFromIndex + 4);
              *(_DWORD *)(v33 + 28) = *(_DWORD *)(RestartTableFromIndex + 8);
              *(_QWORD *)(v33 + 8) = *(_QWORD *)(RestartTableFromIndex + 16);
              *(_QWORD *)(v33 + 16) = *(_QWORD *)(RestartTableFromIndex + 24);
              *(_DWORD *)(v33 + 4) = RestartTableIndex;
              v5 = a3;
            }
            *(_QWORD *)(RestartTableFromIndex + 32) = PoolWithTag;
            v22 = *(_QWORD **)(v6 + 4936);
            if ( *v22 != v6 + 4928 )
              __fastfail(3u);
            *(_QWORD *)PoolWithTag = v6 + 4928;
            *((_QWORD *)PoolWithTag + 1) = v22;
            *v22 = PoolWithTag;
            *(_QWORD *)(v6 + 4936) = PoolWithTag;
            *(_QWORD *)(*(_QWORD *)(RestartTableFromIndex + 32) + 40LL) = 0;
            *(_BYTE *)(*(_QWORD *)(RestartTableFromIndex + 32) + 20LL) = 0;
            *(_WORD *)(*(_QWORD *)(RestartTableFromIndex + 32) + 32LL) = 0;
            *(_WORD *)(*(_QWORD *)(RestartTableFromIndex + 32) + 34LL) = 0;
            ExReleaseResourceLite((PERESOURCE)(v6 + 832));
            PrerestartScb = NtfsCreatePrerestartScb(
                              a1,
                              v6,
                              (int)RestartTableFromIndex + 16,
                              *(_DWORD *)(RestartTableFromIndex + 8),
                              0,
                              *(_DWORD *)(RestartTableFromIndex + 4),
                              1);
            *a4 = PrerestartScb;
            SetFlagInterlocked(PrerestartScb + 200, 32);
            ExAcquireResourceSharedLite((PERESOURCE)(v6 + 832), 1u);
            v35 = *(unsigned __int16 **)(v6 + 1040);
            if ( (v35[3] & 1) != 0 )
              v36 = (unsigned int)*v35 * ((_DWORD)RestartTableIndex - 1) + 24LL;
            else
              v36 = (unsigned int)RestartTableIndex;
            v37 = (char *)v35 + v36;
            *(_QWORD *)(*((_QWORD *)v37 + 4) + 24LL) = *a4;
            *(_DWORD *)(*(_QWORD *)(*a4 + 288) + 8LL) = *(_DWORD *)(*((_QWORD *)v37 + 4) + 16LL);
            *(_DWORD *)(*(_QWORD *)(*a4 + 288) + 4LL) = RestartTableIndex;
            v38 = (struct _ERESOURCE *)(v6 + 832);
          }
          else
          {
            if ( *v17 )
            {
LABEL_17:
              v7 = a1;
              goto LABEL_2;
            }
            ExAcquireResourceSharedLite((PERESOURCE)(v6 + 832), 1u);
            v23 = *(unsigned __int16 **)(v6 + 1040);
            if ( (v23[3] & 1) != 0 )
              v24 = (v13 - 1) * *v23 + 24LL;
            else
              v24 = v13;
            *a4 = *(_QWORD *)(*(_QWORD *)((char *)v23 + v24 + 32) + 24LL);
            v38 = (struct _ERESOURCE *)(v6 + 832);
          }
          ExReleaseResourceLite(v38);
          goto LABEL_17;
        }
LABEL_14:
        v18 = 1;
        goto LABEL_15;
      }
    }
    else if ( (unsigned __int16)v16 >= 0x18u && (unsigned int)v16 < *v14 * (unsigned int)v14[1] + 24 )
    {
      v20 = *(unsigned __int16 *)(v5 + 12);
      if ( !((v16 - 24) % (unsigned __int64)*v14) )
        goto LABEL_25;
    }
    v17 = (_DWORD *)(v6 + 4892);
    goto LABEL_14;
  }
LABEL_2:
  if ( (*(_DWORD *)(v6 + 4) & 0x10) != 0 )
  {
    if ( *(_WORD *)(v5 + 14) )
    {
      v62 = 0;
      v53 = 0;
      v58[0] = 0;
      v39 = NtfsLookupNtfsMcbEntryWithSyncFlag(*a4 + 400, *(_QWORD *)(v5 + 24), &v62, &v53, 0, v58, 0, 0);
      if ( !v39 || v62 == -1 || (unsigned int)v53 < *(unsigned __int16 *)(v5 + 14) )
      {
        FileOffset.QuadPart = 0;
        v40 = 0;
        v41 = *(_DWORD *)(v6 + 404);
        v42 = *(_DWORD *)(v5 + 24) & (v41 - 1);
        v43 = *(_QWORD *)(v5 + 24) & -v41;
        if ( v39 )
        {
          if ( v62 == -1 && v42 + (int)v53 >= v41 && (unsigned int)(v42 + v53) <= LODWORD(v58[0]) )
          {
LABEL_82:
            FileOffset.QuadPart = v43 << *(_BYTE *)(v6 + 488);
            if ( v40 )
            {
              IoStatus = 0;
              CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*a4 + 288) + 16LL), &FileOffset, 0x1000u, &IoStatus);
              NtfsNormalizeAndCleanupTransaction(v7, &IoStatus);
              if ( !(unsigned __int8)NtfsPurgeCacheSection(v7, *a4, &FileOffset, 4096, 0) )
              {
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(v7, 3221225701LL, 1971592);
                NtfsRaiseStatusInternal(v7, -1073741595, 0, 0, 1971592);
                __debugbreak();
              }
            }
            goto LABEL_3;
          }
        }
        else
        {
          IoStatus.Pointer = 0;
          v57 = 0;
          if ( !v42 || !(unsigned __int8)NtfsLookupLastNtfsMcbEntry(*a4 + 400, &v57, &IoStatus) || v57 < v43 )
            goto LABEL_82;
        }
        v40 = 1;
        goto LABEL_82;
      }
    }
  }
LABEL_3:
  IoStatus.Pointer = *(PVOID *)(v5 + 24);
  v8 = ((__int64)IoStatus.Pointer + 1) << *(_BYTE *)(v6 + 488);
  v9 = 0;
  LODWORD(v62) = 0;
  if ( !*(_WORD *)(v5 + 14) )
    goto LABEL_9;
  Pointer = (char *)IoStatus.Pointer;
  do
  {
    v11 = v9;
    v12 = *(_QWORD *)(v5 + 8LL * v9 + 32);
    if ( v12 )
    {
      v19 = *a4;
      if ( (*(_DWORD *)(*(_QWORD *)(*a4 + 184) + 8LL) > 1u
         || v8 >= (unsigned int)(4 * *(_DWORD *)(v6 + 360))
         || *(_DWORD *)(v19 + 256) != 128)
        && !NtfsAddNtfsMcbEntry(v19 + 400, (__int64)Pointer, v12, 1u, 0, 1u) )
      {
        do
          NtfsRemoveNtfsMcbEntry(*a4 + 400, Pointer);
        while ( !NtfsAddNtfsMcbEntry(*a4 + 400, (__int64)Pointer, *(_QWORD *)(v5 + 8 * v11 + 32), 1u, 0, 1u) );
        v6 = a2;
      }
      v9 = v62;
    }
    if ( v8 > *(_QWORD *)(*a4 + 24) )
    {
      *(_QWORD *)(*a4 + 24) = v8;
      v25 = (_QWORD *)*a4;
      if ( (*(_DWORD *)(*a4 + 200) & 0x20000) == 0 || v25[4] >= v8 )
        goto LABEL_96;
      v26 = v25[58];
      if ( v8 < v26 )
        v26 = v8;
      if ( v26 <= v25[5] )
      {
LABEL_96:
        *(_QWORD *)(*a4 + 32) = v8;
        v48 = (_QWORD *)*a4;
        v49 = *(_DWORD *)(*a4 + 200);
        if ( (v49 & 0x20000) != 0 )
        {
          v50 = v48[58];
          if ( v50 < v8 )
          {
LABEL_103:
            *(_QWORD *)(*a4 + 464) = v8;
            goto LABEL_104;
          }
          if ( v48[5] > v8 )
          {
            if ( *(_QWORD *)(v48[36] + 16LL) && v8 != 0x7FFFFFFFFFFFFFFFLL )
            {
              v51 = (v8 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v51 < v50 )
                *(_QWORD *)(*a4 + 464) = v51;
              goto LABEL_104;
            }
            goto LABEL_103;
          }
        }
LABEL_104:
        *(_QWORD *)(*a4 + 40) = v8;
        v52 = *(_QWORD *)(*a4 + 280);
        if ( v52 )
          NtfsSetCcFileSizes(v52, *a4, *a4 + 24);
        v9 = v62;
        goto LABEL_7;
      }
      v44 = (_QWORD *)*a4;
      v45 = *(_DWORD *)(*a4 + 200);
      if ( (v45 & 0x20000) != 0 )
      {
        v46 = v44[58];
        if ( v46 < v26 )
        {
LABEL_94:
          *(_QWORD *)(*a4 + 464) = v26;
          goto LABEL_95;
        }
        if ( v44[5] > v26 )
        {
          if ( *(_QWORD *)(v44[36] + 16LL) && v26 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v47 = (v26 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v47 < v46 )
              *(_QWORD *)(*a4 + 464) = v47;
            goto LABEL_95;
          }
          goto LABEL_94;
        }
      }
LABEL_95:
      *(_QWORD *)(*a4 + 40) = v26;
      goto LABEL_96;
    }
LABEL_7:
    LODWORD(v62) = ++v9;
    ++Pointer;
    v8 += *(unsigned int *)(v6 + 356);
  }
  while ( v9 < *(unsigned __int16 *)(v5 + 14) );
  v7 = a1;
LABEL_9:
  if ( !*(_QWORD *)(*a4 + 280) )
  {
    NtfsCreateInternalAttributeStream(v7, *a4, 1, 0, 0, 0);
    if ( (*(_DWORD *)(*(_QWORD *)(v7 + 104) + 4LL) & 0x10) != 0 )
      CcSetAdditionalCacheAttributes(*(PFILE_OBJECT *)(*a4 + 280), 1u, 1u);
  }
}

```

## disassembly

```asm
0x14015d274  mov     [rsp+arg_10], r8
0x14015d279  mov     [rsp+arg_8], rdx
0x14015d27e  mov     [rsp+arg_0], rcx
0x14015d283  push    rbx
0x14015d284  push    rsi
0x14015d285  push    rdi
0x14015d286  push    r12
0x14015d288  push    r13
0x14015d28a  push    r14
0x14015d28c  push    r15
0x14015d28e  sub     rsp, 0A0h
0x14015d295  mov     rbx, r9
0x14015d298  mov     r13, r8
0x14015d29b  mov     r14, rdx
0x14015d29e  mov     r12, rcx
0x14015d2a1  xor     esi, esi
0x14015d2a3  lea     edi, [rsi+1]
0x14015d2a6  cmp     [r9], rsi
0x14015d2a9  jz      loc_14015D365
0x14015d2af  mov     eax, [r14+4]
0x14015d2b3  test    al, 10h
0x14015d2b5  jnz     loc_1402C97E0
0x14015d2bb  xor     r10d, r10d
0x14015d2be  mov     rsi, [r13+18h]
0x14015d2c2  mov     qword ptr [rsp+0D8h+IoStatus], rsi
0x14015d2c7  mov     cl, [r14+1E8h]
0x14015d2ce  inc     rsi
0x14015d2d1  shl     rsi, cl
0x14015d2d4  mov     ecx, r10d
0x14015d2d7  mov     dword ptr [rsp+0D8h+arg_18], ecx
0x14015d2de  cmp     r10w, [r13+0Eh]
0x14015d2e3  jnb     short loc_14015D341
0x14015d2e5  mov     r11d, 200h
0x14015d2eb  mov     r12, qword ptr [rsp+0D8h+IoStatus]
0x14015d2f0  mov     r15d, ecx
0x14015d2f3  mov     r8, [r13+r15*8+20h]
0x14015d2f8  test    r8, r8
0x14015d2fb  jnz     loc_14015D3ED
0x14015d301  mov     rax, [rbx]
0x14015d304  cmp     rsi, [rax+18h]
0x14015d308  jg      loc_14015D5A6
0x14015d30e  add     ecx, edi
0x14015d310  mov     dword ptr [rsp+0D8h+arg_18], ecx
0x14015d317  add     r12, rdi
0x14015d31a  mov     eax, [r14+164h]
0x14015d321  add     rsi, rax
0x14015d324  movzx   eax, word ptr [r13+0Eh]
0x14015d329  cmp     ecx, eax
0x14015d32b  mov     r10d, 0
0x14015d331  mov     r11d, 200h
0x14015d337  jb      short loc_14015D2F0
0x14015d339  mov     r12, [rsp+0D8h+arg_0]
0x14015d341  mov     rdx, [rbx]
0x14015d344  cmp     [rdx+118h], r10
0x14015d34b  jz      loc_14015D5F3
0x14015d351  add     rsp, 0A0h
0x14015d358  pop     r15
0x14015d35a  pop     r14
0x14015d35c  pop     r13
0x14015d35e  pop     r12
0x14015d360  pop     rdi
0x14015d361  pop     rsi
0x14015d362  pop     rbx
0x14015d363  retn
0x14015d365  mov     r15d, esi
0x14015d368  mov     [rsp+0D8h+var_84], esi
0x14015d36c  mov     dl, dil; Wait
0x14015d36f  mov     rcx, [r14+1338h]; Resource
0x14015d376  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14015d37d  nop     dword ptr [rax+rax+00h]
0x14015d382  mov     rax, [r14+1338h]
0x14015d389  mov     r9, [rax+0D0h]
0x14015d390  movzx   r11d, word ptr [r9+6]
0x14015d395  and     r11w, di
0x14015d399  movzx   r8d, word ptr [r13+0Ch]
0x14015d39e  jz      loc_14015D448
0x14015d3a4  test    r8w, r8w
0x14015d3a8  jnz     loc_14015D539
0x14015d3ae  lea     rsi, [r14+131Ch]
0x14015d3b5  mov     r12b, dil
0x14015d3b8  mov     rcx, [r14+1338h]; Resource
0x14015d3bf  call    cs:__imp_ExReleaseResourceLite
0x14015d3c6  nop     dword ptr [rax+rax+00h]
0x14015d3cb  xor     eax, eax
0x14015d3cd  test    r12b, r12b
0x14015d3d0  jnz     loc_1402C9504
0x14015d3d6  cmp     [rsi], eax
0x14015d3d8  jz      loc_14015D54C
0x14015d3de  xor     esi, esi
0x14015d3e0  mov     r12, [rsp+0D8h+arg_0]
0x14015d3e8  jmp     loc_14015D2AF
0x14015d3ed  mov     rcx, [rbx]
0x14015d3f0  mov     rax, [rcx+0B8h]
0x14015d3f7  cmp     [rax+8], edi
0x14015d3fa  ja      short loc_14015D40F
0x14015d3fc  mov     eax, [r14+168h]
0x14015d403  shl     eax, 2
0x14015d406  cmp     rsi, rax
0x14015d409  jl      loc_14015D589
0x14015d40f  add     rcx, 190h
0x14015d416  mov     byte ptr [rsp+0D8h+var_B0], dil
0x14015d41b  mov     byte ptr [rsp+0D8h+var_B8], r10b
0x14015d420  mov     r9, rdi
0x14015d423  mov     rdx, r12
0x14015d426  call    NtfsAddNtfsMcbEntry
0x14015d42b  xor     r10d, r10d
0x14015d42e  test    al, al
0x14015d430  jz      loc_14015D59E
0x14015d436  mov     r11d, 200h
0x14015d43c  mov     ecx, dword ptr [rsp+0D8h+arg_18]
0x14015d443  jmp     loc_14015D301
0x14015d448  mov     r10d, 18h
0x14015d44e  cmp     r8w, r10w
0x14015d452  jb      loc_14015D3AE
0x14015d458  movzx   edx, word ptr [r9]
0x14015d45c  movzx   ecx, word ptr [r9+2]
0x14015d461  imul    ecx, edx
0x14015d464  add     ecx, r10d
0x14015d467  cmp     r8d, ecx
0x14015d46a  jnb     loc_14015D3AE
0x14015d470  mov     r10, r8
0x14015d473  lea     rax, [r8-18h]
0x14015d477  mov     ecx, edx
0x14015d479  xor     edx, edx
0x14015d47b  div     rcx
0x14015d47e  test    rdx, rdx
0x14015d481  jnz     loc_14015D3AE
0x14015d487  test    r11w, r11w
0x14015d48b  jnz     short loc_14015D4BA
0x14015d48d  lea     rcx, [r10+r9]
0x14015d491  lea     rsi, [r14+131Ch]
0x14015d498  cmp     dword ptr [rcx], 0FFFFFFFFh
0x14015d49b  jnz     loc_14015D3B5
0x14015d4a1  xor     eax, eax
0x14015d4a3  mov     r12b, al
0x14015d4a6  cmp     [rsi], eax
0x14015d4a8  jbe     short loc_14015D4D2
0x14015d4aa  mov     rax, [rcx+20h]
0x14015d4ae  mov     rcx, [rax+18h]
0x14015d4b2  mov     [rbx], rcx
0x14015d4b5  jmp     loc_14015D3B8
0x14015d4ba  mov     ecx, r8d
0x14015d4bd  sub     ecx, edi
0x14015d4bf  movzx   eax, word ptr [r9]
0x14015d4c3  imul    ecx, eax
0x14015d4c6  movsxd  rcx, ecx
0x14015d4c9  add     rcx, 18h
0x14015d4cd  add     rcx, r9
0x14015d4d0  jmp     short loc_14015D491
0x14015d4d2  mov     r15d, [rcx+4]
0x14015d4d6  mov     [rsp+0D8h+var_84], r15d
0x14015d4db  jmp     loc_14015D3B8
0x14015d4e0  mov     [rsi+20h], r12
0x14015d4e4  lea     rax, [r14+1340h]
0x14015d4eb  mov     rcx, [rax+8]
0x14015d4ef  cmp     [rcx], rax
0x14015d4f2  jz      loc_1402C96CD
0x14015d4f8  mov     ecx, 3
0x14015d4fd  int     29h; Win8: RtlFailFast(ecx)
0x14015d4ff  mov     al, cs:NtfsStatusDebugFlags
0x14015d505  test    al, al
0x14015d507  jz      short loc_14015D51C
0x14015d509  mov     edx, 0C00000E5h
0x14015d50e  mov     r8d, 1E1588h
0x14015d514  mov     rcx, r12
0x14015d517  call    NtfsStatusTraceAndDebugInternal
0x14015d51c  mov     [rsp+0D8h+var_B8], 1E1588h
0x14015d525  xor     r9d, r9d
0x14015d528  xor     r8d, r8d
0x14015d52b  mov     edx, 0C00000E5h
0x14015d530  mov     rcx, r12
0x14015d533  call    NtfsRaiseStatusInternal
0x14015d538  int     3; Trap to Debugger
0x14015d539  cmp     r8w, [r9+2]
0x14015d53e  ja      loc_14015D3AE
0x14015d544  mov     r10, r8
0x14015d547  jmp     loc_14015D487
0x14015d54c  lea     rsi, [r14+340h]
0x14015d553  mov     dl, dil; Wait
0x14015d556  mov     rcx, rsi; Resource
0x14015d559  call    cs:__imp_ExAcquireResourceSharedLite
0x14015d560  nop     dword ptr [rax+rax+00h]
0x14015d565  mov     rdx, [r14+410h]
0x14015d56c  test    [rdx+6], dil
0x14015d570  jz      loc_1402C97BA
0x14015d576  lea     ecx, [r15-1]
0x14015d57a  movzx   eax, word ptr [rdx]
0x14015d57d  imul    eax, ecx
0x14015d580  add     rax, 18h
0x14015d584  jmp     loc_1402C97BD
0x14015d589  cmp     dword ptr [rcx+100h], 80h
0x14015d593  jz      loc_14015D43C
0x14015d599  jmp     loc_14015D40F
0x14015d59e  xor     r14d, r14d
0x14015d5a1  jmp     loc_1402C996D
0x14015d5a6  mov     [rax+18h], rsi
0x14015d5aa  mov     rax, [rbx]
0x14015d5ad  mov     edx, [rax+0C8h]
0x14015d5b3  bt      edx, 11h
0x14015d5b7  jnb     loc_1402C9A47
0x14015d5bd  cmp     [rax+20h], rsi
0x14015d5c1  jge     loc_1402C9A47
0x14015d5c7  mov     rcx, [rax+1D0h]
0x14015d5ce  cmp     rsi, rcx
0x14015d5d1  cmovl   rcx, rsi
0x14015d5d5  cmp     rcx, [rax+28h]
0x14015d5d9  jle     loc_1402C9A47
0x14015d5df  test    r11d, edx
0x14015d5e2  jz      loc_1402C99BA
0x14015d5e8  mov     al, cs:NtfsStatusDebugFlags
0x14015d5ee  jmp     loc_1402C99BA
0x14015d5f3  mov     [rsp+0D8h+var_B0], r10
0x14015d5f8  mov     [rsp+0D8h+var_B8], r10
0x14015d5fd  xor     r9d, r9d
0x14015d600  mov     r8b, dil
0x14015d603  mov     rcx, r12
0x14015d606  call    NtfsCreateInternalAttributeStream
0x14015d60b  mov     rax, [r12+68h]
0x14015d610  mov     ecx, [rax+4]
0x14015d613  test    cl, 10h
0x14015d616  jz      loc_14015D351
0x14015d61c  mov     rcx, [rbx]
0x14015d61f  mov     r8b, dil; DisableWriteBehind
0x14015d622  mov     dl, dil; DisableReadAhead
0x14015d625  mov     rcx, [rcx+118h]; FileObject
0x14015d62c  call    cs:__imp_CcSetAdditionalCacheAttributes
0x14015d633  nop     dword ptr [rax+rax+00h]
0x14015d638  jmp     loc_14015D351
0x1402a899f  push    rbp
0x1402a89a1  sub     rsp, 50h
0x1402a89a5  mov     rbp, rdx
0x1402a89a8  test    cl, cl
0x1402a89aa  jz      loc_1402A8A5B
0x1402a89b0  mov     al, cs:NtfsStatusDebugFlags
0x1402a89b6  mov     rcx, [rbp+80h]; P
0x1402a89bd  test    rcx, rcx
0x1402a89c0  jz      short loc_1402A89D1
0x1402a89c2  xor     edx, edx; Tag
0x1402a89c4  call    cs:__imp_ExFreePoolWithTag
0x1402a89cb  nop     dword ptr [rax+rax+00h]
0x1402a89d0  nop
0x1402a89d1  cmp     byte ptr [rbp+50h], 0
0x1402a89d5  jz      short loc_1402A8A16
0x1402a89d7  mov     r8d, [rbp+58h]
0x1402a89db  test    r8d, r8d
0x1402a89de  jz      short loc_1402A89FB
0x1402a89e0  mov     rdx, [rbp+0E8h]
0x1402a89e7  mov     rdx, [rdx+1338h]
0x1402a89ee  mov     rcx, [rbp+0E0h]
0x1402a89f5  call    NtfsFreeRestartTableIndex
0x1402a89fa  nop
0x1402a89fb  mov     rcx, [rbp+0E8h]
0x1402a8a02  mov     rcx, [rcx+1338h]; Resource
0x1402a8a09  call    cs:__imp_ExReleaseResourceLite
0x1402a8a10  nop     dword ptr [rax+rax+00h]
0x1402a8a15  nop
0x1402a8a16  cmp     byte ptr [rbp+51h], 0
0x1402a8a1a  jz      short loc_1402A8A5B
0x1402a8a1c  mov     r8d, [rbp+54h]
0x1402a8a20  test    r8d, r8d
0x1402a8a23  jz      short loc_1402A8A40
0x1402a8a25  mov     rdx, [rbp+0E8h]
0x1402a8a2c  add     rdx, 340h
0x1402a8a33  mov     rcx, [rbp+0E0h]
0x1402a8a3a  call    NtfsFreeRestartTableIndex
0x1402a8a3f  nop
0x1402a8a40  mov     rcx, [rbp+0E8h]
0x1402a8a47  add     rcx, 340h; Resource
0x1402a8a4e  call    cs:__imp_ExReleaseResourceLite
0x1402a8a55  nop     dword ptr [rax+rax+00h]
0x1402a8a5a  nop
0x1402a8a5b  add     rsp, 50h
0x1402a8a5f  pop     rbp
0x1402a8a60  retn
0x1402c9504  mov     [rsp+0D8h+var_58], rax
0x1402c950c  mov     [rsp+0D8h+var_80], eax
0x1402c9510  mov     [rsp+0D8h+var_88], al
0x1402c9514  mov     [rsp+0D8h+var_87], al
0x1402c9518  mov     ecx, cs:PoolType
0x1402c951e  or      ecx, 10h; PoolType
0x1402c9521  mov     edx, 30h ; '0'; NumberOfBytes
0x1402c9526  mov     r8d, 5246744Eh; Tag
0x1402c952c  call    cs:__imp_ExAllocatePoolWithTag
0x1402c9533  nop     dword ptr [rax+rax+00h]
0x1402c9538  mov     r12, rax
0x1402c953b  mov     [rsp+0D8h+var_58], rax
0x1402c9543  xorps   xmm0, xmm0
0x1402c9546  movups  xmmword ptr [rax], xmm0
0x1402c9549  movups  xmmword ptr [rax+10h], xmm0
0x1402c954d  movups  xmmword ptr [rax+20h], xmm0
0x1402c9551  movzx   ecx, word ptr [r13+0Ch]
0x1402c9556  mov     [rax+10h], ecx
0x1402c9559  lea     rsi, [r14+340h]
0x1402c9560  mov     dl, dil; Wait
0x1402c9563  mov     rcx, rsi; Resource
0x1402c9566  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402c956d  nop     dword ptr [rax+rax+00h]
0x1402c9572  mov     [rsp+0D8h+var_87], dil
0x1402c9577  xor     eax, eax
0x1402c9579  mov     rdx, rsi
  ... truncated ...
```
