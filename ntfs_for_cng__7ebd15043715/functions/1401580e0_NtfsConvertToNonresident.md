# NtfsConvertToNonresident

- ea: `0x1401580e0`
- end: `0x140158ae0`
- name: `NtfsConvertToNonresident`
- size: `2560`
- prototype: `void __fastcall(__int64, __int64, __int64, char, __int64 *)`
- caller_count: `23`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140024338`
- `0x1400c0ca8`
- `0x1400c1808`
- `0x1400c8204`
- `0x1400d2740`
- `0x1400d7558`
- `0x1400da814`
- `0x140109e58`
- `0x1401101f8`
- `0x140134a58`
- `0x1401436e0`
- `0x14014516c`
- `0x140151ac8`
- `0x1401e7e28`
- `0x1401ea058`
- `0x14020d830`
- `0x14025cc9c`
- `0x140265544`
- `0x140268608`
- `0x14026fae8`
- `0x14027af08`
- `0x14028a29c`
- `0x14029130c`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x1400410a8`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x1401250b0`
- `0x1401436e0`
- `0x140150bc0`
- `0x1401578a0`
- `0x1401580e0`
- `0x140159768`
- `0x14015a570`
- `0x1401620c0`
- `0x140163f78`
- `0x14019a718`
- `0x1401e0660`

## import_xrefs

- `ntoskrnl!CcSetFileSizesEx` at `0x140158357`
- `ntoskrnl!CcSetFileSizesEx` at `0x140158357`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401589fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a85e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401589fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a85e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140158758`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140158758`
- `ntoskrnl!CcUnpinData` at `0x140158456`
- `ntoskrnl!CcUnpinData` at `0x140158472`
- `ntoskrnl!CcUnpinData` at `0x14015848b`
- `ntoskrnl!CcUnpinData` at `0x140158a1b`
- `ntoskrnl!CcUnpinData` at `0x140158a36`
- `ntoskrnl!CcUnpinData` at `0x140158a4f`
- `ntoskrnl!CcUnpinData` at `0x140158456`
- `ntoskrnl!CcUnpinData` at `0x140158472`
- `ntoskrnl!CcUnpinData` at `0x14015848b`
- `ntoskrnl!CcUnpinData` at `0x140158a1b`
- `ntoskrnl!CcUnpinData` at `0x140158a36`
- `ntoskrnl!CcUnpinData` at `0x140158a4f`
- `ntoskrnl!CcMdlReadComplete` at `0x140158a73`
- `ntoskrnl!CcMdlReadComplete` at `0x1402a861c`
- `ntoskrnl!CcMdlReadComplete` at `0x140158a73`
- `ntoskrnl!CcMdlReadComplete` at `0x1402a861c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140158797`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140158797`
- `ntoskrnl!CcMdlRead` at `0x1401586b4`
- `ntoskrnl!CcMdlRead` at `0x1401586b4`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401582c5`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1401582c5`
- `ntoskrnl!ExRaiseStatus` at `0x140158916`
- `ntoskrnl!ExRaiseStatus` at `0x140158916`

## pseudocode

```c
void __fastcall NtfsConvertToNonresident(__int64 a1, __int64 a2, __int64 a3, char a4, __int64 *a5)
{
  __int64 *v9; // rsi
  int v10; // r14d
  bool v11; // al
  char v12; // di
  USHORT Length; // cx
  int v14; // r9d
  unsigned int v15; // r13d
  __int64 Scb; // rax
  __int64 v17; // r14
  int v18; // r8d
  __int64 v19; // rax
  struct _FILE_OBJECT *v20; // r9
  NTSTATUS v21; // eax
  ULONG v22; // r12d
  _BYTE *v23; // rdi
  LARGE_INTEGER *v24; // rbx
  int v25; // r12d
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  int v29; // r9d
  const void *v30; // rdx
  LARGE_INTEGER AllocationSize; // rbx
  __int64 v32; // rax
  int v33; // ecx
  PVOID MappedSystemVa; // rax
  int v35; // ecx
  __int64 v36; // rax
  __int128 v37; // xmm1
  __int64 v38; // rax
  unsigned int v39; // ecx
  unsigned int v40; // r8d
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  PIO_STATUS_BLOCK IoStatus; // [rsp+20h] [rbp-188h]
  int Priority; // [rsp+28h] [rbp-180h]
  char v46; // [rsp+60h] [rbp-148h]
  char v47; // [rsp+61h] [rbp-147h]
  char v48[2]; // [rsp+62h] [rbp-146h] BYREF
  __int16 v49; // [rsp+64h] [rbp-144h]
  unsigned int v50; // [rsp+68h] [rbp-140h]
  UNICODE_STRING v51; // [rsp+70h] [rbp-138h] BYREF
  void *v52; // [rsp+80h] [rbp-128h]
  PMDL MdlChain; // [rsp+88h] [rbp-120h] BYREF
  unsigned int v54; // [rsp+90h] [rbp-118h]
  unsigned int v55; // [rsp+94h] [rbp-114h]
  ULONG v56; // [rsp+98h] [rbp-110h]
  unsigned int v57; // [rsp+9Ch] [rbp-10Ch]
  PVOID P; // [rsp+A0h] [rbp-108h]
  LARGE_INTEGER *v59; // [rsp+A8h] [rbp-100h]
  __int64 *v60; // [rsp+B0h] [rbp-F8h]
  __int64 v61; // [rsp+B8h] [rbp-F0h]
  struct _FILE_OBJECT *v62; // [rsp+C0h] [rbp-E8h]
  _BYTE *v63; // [rsp+C8h] [rbp-E0h]
  _BYTE v64[96]; // [rsp+D0h] [rbp-D8h] BYREF
  struct _CC_FILE_SIZES v65; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v66[32]; // [rsp+148h] [rbp-60h] BYREF

  v59 = (LARGE_INTEGER *)a2;
  v9 = a5;
  v60 = a5;
  P = 0;
  memset(v64, 0, 0x58u);
  v10 = *(_DWORD *)a3;
  v57 = *(_DWORD *)a3;
  v49 = *(_WORD *)(a3 + 12);
  v52 = 0;
  v61 = 0;
  MdlChain = 0;
  v47 = 0;
  v48[0] = 0;
  v11 = a4 && v10 == 128;
  v46 = v11;
  v12 = 0;
  v51 = 0;
  if ( *(_QWORD *)(a1 + 400) && v10 == 128 && !v11 )
  {
    v46 = 1;
    v12 = 1;
  }
  Length = 2 * *(unsigned __int8 *)(a3 + 9);
  v51.Length = Length;
  v51.MaximumLength = Length;
  v51.Buffer = (PWSTR)(a3 + *(unsigned __int16 *)(a3 + 10));
  if ( !a5 )
  {
    v9 = (__int64 *)v64;
    v60 = (__int64 *)v64;
    v47 = 1;
    if ( !NtfsLookupInFileRecord(a1, a2, (_DWORD *)(a2 + 8), v10, &v51, 0, 0, 0, 0, (__int64)v64) )
    {
      NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 202713, v14, a2 + 8, a2, 0);
      NtfsAttachRepairInfoPriv(a1, 256, 0, (struct _LIST_ENTRY *)0x37000317D9LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0x317D9u);
      NtfsRaiseStatusInternal(a1, -1073741566, a2 + 8, a2, 202713);
    }
    Length = v51.Length;
  }
  v15 = Length;
  v54 = Length;
  Scb = NtfsCreateScb(a1, a2, v10, (unsigned int)&v51, 0, 0, (__int64)v48);
  v17 = Scb;
  v61 = Scb;
  if ( v12 )
  {
    if ( (*(_DWORD *)(Scb + 200) & 0x200) != 0 )
    {
      v40 = *(_DWORD *)(Scb + 32);
      if ( v40 != *(_DWORD *)(a3 + 16) )
      {
        LODWORD(IoStatus) = 0;
        NtfsChangeAttributeValue(a1, a2, v40, 0, (SIZE_T)IoStatus, 1, 1, 1, 1, v9);
      }
    }
  }
  NtfsUpdateScbFromAttribute(a1, v17, a3);
  *(_DWORD *)(v17 + 512) |= 0x4000u;
  v19 = *(_QWORD *)(v17 + 496);
  if ( v19 )
    *(_QWORD *)(v19 + 96) = a1;
  if ( *(_DWORD *)(v17 + 256) == 128
    && (v46 || !MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v17 + 288) + 16LL), 0)) )
  {
    v32 = *(_QWORD *)(a2 + 96);
    v22 = *(_DWORD *)(a3 + 16);
    v50 = *(_DWORD *)(v32 + 484) & (v22 + *(_DWORD *)(v32 + 480));
    v55 = v50;
    v15 += v50;
    v54 = v15;
    v56 = v22;
    if ( v22 )
    {
      if ( *(_BYTE *)(a1 + 32) == 4 )
      {
        v35 = *(_DWORD *)(a1 + 12);
        if ( (v35 & 0x100) == 0 )
        {
          v36 = *(_QWORD *)(a1 + 112);
          if ( v36 )
          {
            if ( (*(_DWORD *)(v36 + 16) & 2) == 0 && *(_QWORD *)(v17 + 16) )
            {
              *(_DWORD *)(a1 + 12) = v35 | 0x100;
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 202809);
            }
          }
        }
      }
    }
    v46 = 1;
  }
  else
  {
    v50 = 0;
    v55 = 0;
    LOBYTE(v18) = 1;
    NtfsCreateInternalAttributeStream(a1, v17, v18, 0, (__int64)L",.", 0);
    v20 = *(struct _FILE_OBJECT **)(v17 + 280);
    v62 = v20;
    if ( v20 && v20->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v17 + 288) + 16LL) )
    {
      NtfsCreateInternalAttributeStream(a1, v17, 0, 0, 0, 0);
      v20 = *(struct _FILE_OBJECT **)(v17 + 280);
      v62 = v20;
    }
    if ( *(_QWORD *)(*(_QWORD *)(v17 + 288) + 24LL) )
    {
      if ( (*(_DWORD *)(v17 + 512) & 1) != 0 )
      {
        v37 = *(_OWORD *)(v17 + 24);
        *(_OWORD *)&v65.AllocationSize.LowPart = v37;
        v65.ValidDataLength.QuadPart = *(_QWORD *)(v17 + 40);
        v65.AllocationSize.QuadPart = v37 - *(_QWORD *)(*(_QWORD *)(v17 + 192) + 1952LL);
        v65.FileSize.QuadPart = *((_QWORD *)&v37 + 1) - *(_QWORD *)(*(_QWORD *)(v17 + 192) + 1952LL);
        NtfsSetCcFileSizes(v20, v17, &v65);
      }
      else
      {
        v21 = CcSetFileSizesEx(v20, (PCC_FILE_SIZES)(v17 + 24));
        if ( v21 < 0 && *(_DWORD *)(v17 + 220) )
          ExRaiseStatus(v21);
        if ( NtfsStatusDebugFlags
          && v21
          && v21 != 294
          && (unsigned int)(v21 - 298) > 1
          && (unsigned int)v21 < 0xFFFFFFED
          && v21 != -1073741608
          && v21 != -1073741802
          && v21 != -1073741807
          && (unsigned int)(v21 + 2147483643) > 1
          && v21 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(0, v21, 0x516ADu);
        }
      }
    }
    v22 = *(_DWORD *)(v17 + 40);
    v56 = v22;
    if ( v22 )
    {
      *(_OWORD *)&v65.AllocationSize.LowPart = 0;
      if ( *(_BYTE *)(a1 + 32) == 4 )
      {
        v33 = *(_DWORD *)(a1 + 12);
        if ( (v33 & 0x100) == 0 )
        {
          v38 = *(_QWORD *)(a1 + 112);
          if ( v38 )
          {
            if ( (*(_DWORD *)(v38 + 16) & 2) == 0 && *(_QWORD *)(v17 + 16) )
            {
              v39 = v33 & 0xFFFFFFFE;
              *(_DWORD *)(a1 + 12) = v39;
              *(_DWORD *)(a1 + 12) = v39 | 0x100;
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 202888);
            }
          }
        }
      }
      CcMdlRead(*(PFILE_OBJECT *)(v17 + 280), &NtfsLarge0, v22, &MdlChain, (PIO_STATUS_BLOCK)&v65);
      if ( (MdlChain->MdlFlags & 5) != 0 )
        MappedSystemVa = MdlChain->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlChain, 0, MmCached, 0, 0, 0x40000010u);
      v52 = MappedSystemVa;
      v63 = MappedSystemVa;
      if ( !MappedSystemVa )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000009A, 0x31895u);
        NtfsRaiseStatusInternal(a1, -1073741670, 0, (int)v59, 202901);
      }
    }
  }
  if ( v15 > 8 )
  {
    P = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v15, 0x4146744Eu);
    v23 = P;
    v65.AllocationSize.QuadPart = (LONGLONG)P;
  }
  else
  {
    v23 = v66;
    v65.AllocationSize.QuadPart = (LONGLONG)v66;
  }
  v51.Buffer = (PWSTR)&v23[v50];
  memmove(v51.Buffer, (const void *)(a3 + *(unsigned __int16 *)(a3 + 10)), v51.Length);
  if ( v46 )
  {
    v52 = v23;
    v63 = v23;
    if ( v22 )
    {
      v30 = (const void *)(a3 + *(unsigned __int16 *)(a3 + 20));
      AllocationSize = v65.AllocationSize;
      memmove((void *)v65.AllocationSize.QuadPart, v30, v22);
      memset((void *)(v22 + AllocationSize.QuadPart), 0, v15 - v51.Length - v22);
    }
  }
  v24 = v59;
  NtfsDeleteAttributeRecord(a1, v59, 15, v9);
  Priority = v22;
  v25 = v57;
  NtfsCreateNonresidentWithValue(
    a1,
    v24,
    v57,
    (__int128 *)&v51,
    v52,
    Priority,
    v49,
    (LARGE_INTEGER *)v17,
    1,
    1,
    (__int64)v9);
  if ( !v47 )
  {
    v26 = (void *)v9[2];
    if ( v26 )
    {
      CcUnpinData(v26);
      v9[2] = 0;
    }
    v27 = (void *)v9[5];
    if ( v27 )
    {
      CcUnpinData(v27);
      v9[5] = 0;
    }
    v28 = (void *)v9[9];
    if ( v28 )
    {
      CcUnpinData(v28);
      v9[9] = 0;
    }
    memset(v9, 0, 0x58u);
    if ( !NtfsLookupInFileRecord(a1, (__int64)v24, &v24[1], v25, &v51, 0, 0, 0, 0, (__int64)v9) )
    {
      NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 203004, v29, (__int64)&v24[1], (__int64)v24, 0);
      NtfsAttachRepairInfoPriv(a1, 256, 0, (struct _LIST_ENTRY *)0x38000318FCLL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0x318FCu);
      NtfsRaiseStatusInternal(a1, -1073741566, (_DWORD)v24 + 8, (int)v24, 203004);
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( v47 )
  {
    v41 = (void *)v9[2];
    if ( v41 )
    {
      CcUnpinData(v41);
      v9[2] = 0;
    }
    v42 = (void *)v9[5];
    if ( v42 )
    {
      CcUnpinData(v42);
      v9[5] = 0;
    }
    v43 = (void *)v9[9];
    if ( v43 )
    {
      CcUnpinData(v43);
      v9[9] = 0;
    }
  }
  if ( MdlChain )
    CcMdlReadComplete(*(PFILE_OBJECT *)(v17 + 280), MdlChain);
}

```

## disassembly

```asm
0x1401580e0  push    rbx
0x1401580e2  push    rsi
0x1401580e3  push    rdi
0x1401580e4  push    r12
0x1401580e6  push    r13
0x1401580e8  push    r14
0x1401580ea  push    r15
0x1401580ec  sub     rsp, 170h
0x1401580f3  mov     rax, cs:__security_cookie
0x1401580fa  xor     rax, rsp
0x1401580fd  mov     [rsp+1A8h+var_40], rax
0x140158105  movzx   edi, r9b
0x140158109  mov     rbx, r8
0x14015810c  mov     r12, rdx
0x14015810f  mov     [rsp+1A8h+var_100], rdx
0x140158117  mov     r15, rcx
0x14015811a  mov     rsi, [rsp+1A8h+arg_20]
0x140158122  mov     [rsp+1A8h+var_F8], rsi
0x14015812a  xor     r13d, r13d
0x14015812d  mov     [rsp+1A8h+P], r13
0x140158135  xor     edx, edx; Val
0x140158137  mov     r8d, 58h ; 'X'; Size
0x14015813d  lea     rcx, [rsp+1A8h+var_D8]; void *
0x140158145  call    memset
0x14015814a  mov     r14d, [rbx]
0x14015814d  mov     [rsp+1A8h+var_10C], r14d
0x140158155  movzx   eax, word ptr [rbx+0Ch]
0x140158159  mov     [rsp+1A8h+var_144], ax
0x14015815e  mov     [rsp+1A8h+var_128], r13
0x140158166  mov     [rsp+1A8h+var_F0], r13
0x14015816e  mov     [rsp+1A8h+MdlChain], r13
0x140158176  mov     [rsp+1A8h+var_147], r13b
0x14015817b  mov     [rsp+1A8h+var_146], r13b
0x140158180  test    dil, dil
0x140158183  jnz     loc_140158AA3
0x140158189  xor     al, al
0x14015818b  mov     [rsp+1A8h+var_148], al
0x14015818f  xor     dil, dil
0x140158192  xorps   xmm0, xmm0
0x140158195  movups  [rsp+1A8h+var_138], xmm0
0x14015819a  cmp     [r15+190h], r13
0x1401581a1  jnz     loc_140158ABE
0x1401581a7  movzx   ecx, byte ptr [rbx+9]
0x1401581ab  add     cx, cx
0x1401581ae  mov     word ptr [rsp+1A8h+var_138], cx
0x1401581b3  mov     word ptr [rsp+1A8h+var_138+2], cx
0x1401581b8  movzx   eax, word ptr [rbx+0Ah]
0x1401581bc  add     rax, rbx
0x1401581bf  mov     qword ptr [rsp+1A8h+var_138+8], rax
0x1401581c4  test    rsi, rsi
0x1401581c7  jnz     short loc_14015822C
0x1401581c9  lea     rsi, [rsp+1A8h+var_D8]
0x1401581d1  mov     [rsp+1A8h+var_F8], rsi
0x1401581d9  mov     [rsp+1A8h+var_147], 1
0x1401581de  lea     r13, [r12+8]
0x1401581e3  lea     rax, [rsp+1A8h+var_D8]
0x1401581eb  mov     [rsp+1A8h+var_160], rax
0x1401581f0  xor     eax, eax
0x1401581f2  mov     dword ptr [rsp+1A8h+var_168], eax
0x1401581f6  mov     qword ptr [rsp+1A8h+var_170], rax
0x1401581fb  mov     [rsp+1A8h+var_178], al
0x1401581ff  mov     qword ptr [rsp+1A8h+Priority], rax
0x140158204  lea     rax, [rsp+1A8h+var_138]
0x140158209  mov     [rsp+1A8h+IoStatus], rax
0x14015820e  mov     r9d, r14d
0x140158211  mov     r8, r13
0x140158214  mov     rdx, r12
0x140158217  mov     rcx, r15
0x14015821a  call    NtfsLookupInFileRecord
0x14015821f  test    al, al
0x140158221  jz      loc_140158923
0x140158227  movzx   ecx, word ptr [rsp+1A8h+var_138]
0x14015822c  movzx   r13d, cx
0x140158230  mov     [rsp+1A8h+var_118], r13d
0x140158238  lea     rax, [rsp+1A8h+var_146]
0x14015823d  mov     qword ptr [rsp+1A8h+var_178], rax
0x140158242  mov     qword ptr [rsp+1A8h+Priority], 0
0x14015824b  mov     byte ptr [rsp+1A8h+IoStatus], 0
0x140158250  lea     r9, [rsp+1A8h+var_138]
0x140158255  mov     r8d, r14d
0x140158258  mov     rdx, r12
0x14015825b  mov     rcx, r15
0x14015825e  call    NtfsCreateScb
0x140158263  mov     r14, rax
0x140158266  mov     [rsp+1A8h+var_F0], rax
0x14015826e  test    dil, dil
0x140158271  jnz     loc_140158999
0x140158277  mov     r8, rbx
0x14015827a  mov     rdx, r14
0x14015827d  mov     rcx, r15
0x140158280  call    NtfsUpdateScbFromAttribute
0x140158285  or      dword ptr [r14+200h], 4000h
0x140158290  mov     rax, [r14+1F0h]
0x140158297  test    rax, rax
0x14015829a  jz      short loc_1401582A0
0x14015829c  mov     [rax+60h], r15
0x1401582a0  cmp     dword ptr [r14+100h], 80h
0x1401582ab  jnz     short loc_1401582D9
0x1401582ad  cmp     [rsp+1A8h+var_148], 0
0x1401582b2  jnz     loc_140158625
0x1401582b8  mov     rcx, [r14+120h]
0x1401582bf  add     rcx, 10h; SectionPointer
0x1401582c3  xor     edx, edx; NewFileSize
0x1401582c5  call    cs:__imp_MmCanFileBeTruncated
0x1401582cc  nop     dword ptr [rax+rax+00h]
0x1401582d1  test    al, al
0x1401582d3  jz      loc_140158625
0x1401582d9  xor     eax, eax
0x1401582db  mov     [rsp+1A8h+var_140], eax
0x1401582df  mov     [rsp+1A8h+var_114], eax
0x1401582e6  mov     qword ptr [rsp+1A8h+Priority], rax
0x1401582eb  lea     rax, asc_140062070; ",."
0x1401582f2  mov     [rsp+1A8h+IoStatus], rax
0x1401582f7  xor     r9d, r9d
0x1401582fa  mov     r8b, 1
0x1401582fd  mov     rdx, r14
0x140158300  mov     rcx, r15
0x140158303  call    NtfsCreateInternalAttributeStream
0x140158308  mov     r9, [r14+118h]
0x14015830f  mov     [rsp+1A8h+var_E8], r9
0x140158317  test    r9, r9
0x14015831a  jz      short loc_140158331
0x14015831c  mov     rax, [r14+120h]
0x140158323  add     rax, 10h
0x140158327  cmp     [r9+28h], rax
0x14015832b  jnz     loc_1401588CE
0x140158331  mov     rax, [r14+120h]
0x140158338  mov     rcx, [rax+18h]
0x14015833c  test    rcx, rcx
0x14015833f  jz      short loc_14015837C
0x140158341  mov     eax, [r14+200h]
0x140158348  mov     rcx, r9; FileObject
0x14015834b  test    al, 1
0x14015834d  jnz     loc_140158817
0x140158353  lea     rdx, [r14+18h]; FileSizes
0x140158357  call    cs:__imp_CcSetFileSizesEx
0x14015835e  nop     dword ptr [rax+rax+00h]
0x140158363  mov     edx, eax
0x140158365  test    eax, eax
0x140158367  js      loc_1401588FF
0x14015836d  movzx   eax, cs:NtfsStatusDebugFlags
0x140158374  test    al, al
0x140158376  jnz     loc_1401585A8
0x14015837c  mov     r12d, [r14+28h]
0x140158380  mov     [rsp+1A8h+var_110], r12d
0x140158388  test    r12d, r12d
0x14015838b  jnz     loc_14015866E
0x140158391  cmp     r13d, 8
0x140158395  ja      loc_140158746
0x14015839b  lea     rdi, [rsp+1A8h+var_60]
0x1401583a3  mov     qword ptr [rsp+1A8h+var_78], rdi
0x1401583ab  mov     ecx, [rsp+1A8h+var_140]
0x1401583af  add     rcx, rdi; void *
0x1401583b2  mov     qword ptr [rsp+1A8h+var_138+8], rcx
0x1401583b7  movzx   r8d, word ptr [rsp+1A8h+var_138]; Size
0x1401583bd  movzx   edx, word ptr [rbx+0Ah]
0x1401583c1  add     rdx, rbx; Src
0x1401583c4  call    memmove
0x1401583c9  cmp     [rsp+1A8h+var_148], 0
0x1401583ce  jnz     loc_140158551
0x1401583d4  mov     r9, rsi
0x1401583d7  mov     r8d, 0Fh
0x1401583dd  mov     rbx, [rsp+1A8h+var_100]
0x1401583e5  mov     rdx, rbx
0x1401583e8  mov     rcx, r15
0x1401583eb  call    NtfsDeleteAttributeRecord
0x1401583f0  mov     [rsp+1A8h+var_158], rsi
0x1401583f5  mov     byte ptr [rsp+1A8h+var_160], 1
0x1401583fa  mov     [rsp+1A8h+var_168], 1
0x1401583ff  mov     qword ptr [rsp+1A8h+var_170], r14
0x140158404  movzx   eax, [rsp+1A8h+var_144]
0x140158409  mov     word ptr [rsp+1A8h+var_178], ax
0x14015840e  mov     [rsp+1A8h+Priority], r12d
0x140158413  mov     rax, [rsp+1A8h+var_128]
0x14015841b  mov     [rsp+1A8h+IoStatus], rax
0x140158420  lea     r9, [rsp+1A8h+var_138]
0x140158425  mov     r12d, [rsp+1A8h+var_10C]
0x14015842d  mov     r8d, r12d
0x140158430  mov     rdx, rbx
0x140158433  mov     rcx, r15
0x140158436  call    NtfsCreateNonresidentWithValue
0x14015843b  movzx   edi, [rsp+1A8h+var_147]
0x140158440  test    dil, dil
0x140158443  jnz     loc_1401589EB
0x140158449  mov     rcx, [rsi+10h]; Bcb
0x14015844d  test    rcx, rcx
0x140158450  jz      loc_14015880F
0x140158456  call    cs:__imp_CcUnpinData
0x14015845d  nop     dword ptr [rax+rax+00h]
0x140158462  xor     r13d, r13d
0x140158465  mov     [rsi+10h], r13
0x140158469  mov     rcx, [rsi+28h]; Bcb
0x14015846d  test    rcx, rcx
0x140158470  jz      short loc_140158482
0x140158472  call    cs:__imp_CcUnpinData
0x140158479  nop     dword ptr [rax+rax+00h]
0x14015847e  mov     [rsi+28h], r13
0x140158482  mov     rcx, [rsi+48h]; Bcb
0x140158486  test    rcx, rcx
0x140158489  jz      short loc_14015849B
0x14015848b  call    cs:__imp_CcUnpinData
0x140158492  nop     dword ptr [rax+rax+00h]
0x140158497  mov     [rsi+48h], r13
0x14015849b  xor     edx, edx; Val
0x14015849d  mov     r8d, 58h ; 'X'; Size
0x1401584a3  mov     rcx, rsi; void *
0x1401584a6  call    memset
0x1401584ab  lea     r13, [rbx+8]
0x1401584af  mov     [rsp+1A8h+var_160], rsi
0x1401584b4  xor     eax, eax
0x1401584b6  mov     dword ptr [rsp+1A8h+var_168], eax
0x1401584ba  mov     qword ptr [rsp+1A8h+var_170], rax
0x1401584bf  mov     [rsp+1A8h+var_178], al
0x1401584c3  mov     qword ptr [rsp+1A8h+Priority], rax
0x1401584c8  lea     rax, [rsp+1A8h+var_138]
0x1401584cd  mov     [rsp+1A8h+IoStatus], rax
0x1401584d2  mov     r9d, r12d
0x1401584d5  mov     r8, r13
0x1401584d8  mov     rdx, rbx
0x1401584db  mov     rcx, r15
0x1401584de  call    NtfsLookupInFileRecord
0x1401584e3  test    al, al
0x1401584e5  jnz     loc_1401589EB
0x1401584eb  mov     edx, 2
0x1401584f0  mov     [rsp+1A8h+var_178], al
0x1401584f4  mov     qword ptr [rsp+1A8h+Priority], rbx
0x1401584f9  mov     [rsp+1A8h+IoStatus], r13
0x1401584fe  mov     rdi, 38000318FCh
0x140158508  mov     r8, rdi
0x14015850b  mov     rcx, r15
0x14015850e  call    NtfsAttachCorruption_BadOrOrphanFRS
0x140158513  mov     r9, rdi
0x140158516  xor     r8d, r8d
0x140158519  mov     edx, 100h
0x14015851e  mov     rcx, r15
0x140158521  call    NtfsAttachRepairInfoPriv
0x140158526  movzx   eax, cs:NtfsStatusDebugFlags
0x14015852d  test    al, al
0x14015852f  jnz     loc_14015872E
0x140158535  mov     [rsp+1A8h+IoStatus], 318FCh
0x14015853e  mov     r9, rbx
0x140158541  mov     r8, r13
0x140158544  mov     edx, 0C0000102h
0x140158549  mov     rcx, r15
0x14015854c  call    NtfsRaiseStatusInternal
0x140158551  mov     rax, rdi
0x140158554  mov     [rsp+1A8h+var_128], rax
0x14015855c  mov     [rsp+1A8h+var_E0], rax
0x140158564  test    r12d, r12d
0x140158567  jz      loc_1401583D4
0x14015856d  mov     edi, r12d
0x140158570  movzx   edx, word ptr [rbx+14h]
0x140158574  add     rdx, rbx; Src
0x140158577  mov     r8d, r12d; Size
0x14015857a  mov     rbx, qword ptr [rsp+1A8h+var_78]
0x140158582  mov     rcx, rbx; void *
0x140158585  call    memmove
0x14015858a  movzx   eax, word ptr [rsp+1A8h+var_138]
0x14015858f  sub     r13d, eax
0x140158592  sub     r13d, r12d
0x140158595  mov     r8d, r13d; Size
0x140158598  lea     rcx, [rdi+rbx]; void *
0x14015859c  xor     edx, edx; Val
0x14015859e  call    memset
0x1401585a3  jmp     loc_1401583D4
0x1401585a8  test    edx, edx
0x1401585aa  jz      loc_14015837C
0x1401585b0  cmp     edx, 126h
0x1401585b6  jz      loc_14015837C
0x1401585bc  lea     eax, [rdx-12Ah]
0x1401585c2  cmp     eax, 1
0x1401585c5  jbe     loc_14015837C
0x1401585cb  cmp     edx, 0FFFFFFEDh
0x1401585ce  jnb     loc_14015837C
0x1401585d4  cmp     edx, 0C00000D8h
0x1401585da  jz      loc_14015837C
0x1401585e0  cmp     edx, 0C0000016h
0x1401585e6  jz      loc_14015837C
0x1401585ec  cmp     edx, 0C0000011h
0x1401585f2  jz      loc_14015837C
0x1401585f8  lea     eax, [rdx+7FFFFFFBh]
0x1401585fe  cmp     eax, 1
0x140158601  jbe     loc_14015837C
0x140158607  cmp     edx, 103h
0x14015860d  jz      loc_14015837C
0x140158613  xor     ecx, ecx
0x140158615  mov     r8d, 516ADh
0x14015861b  call    NtfsStatusTraceAndDebugInternal
0x140158620  jmp     loc_14015837C
0x140158625  mov     rax, [r12+60h]
0x14015862a  mov     r12d, [rbx+10h]
0x14015862e  mov     edi, [rax+1E0h]
0x140158634  add     edi, r12d
0x140158637  and     edi, [rax+1E4h]
0x14015863d  mov     [rsp+1A8h+var_140], edi
0x140158641  mov     [rsp+1A8h+var_114], edi
0x140158648  add     r13d, edi
0x14015864b  mov     [rsp+1A8h+var_118], r13d
0x140158653  mov     [rsp+1A8h+var_110], r12d
0x14015865b  test    r12d, r12d
  ... truncated ...
```
