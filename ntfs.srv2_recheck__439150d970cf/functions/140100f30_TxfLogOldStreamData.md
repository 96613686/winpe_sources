# TxfLogOldStreamData

- ea: `0x140100f30`
- end: `0x1401015b3`
- name: `TxfLogOldStreamData`
- size: `1667`
- prototype: `__int64 __fastcall(int, int, int, int, PLARGE_INTEGER, ULONG Length, __int64, __int64, __int64, int, int, int, int, __int16, char, PVOID Buffer)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140039038`

## callees

- `0x14000c450`
- `0x140012e70`
- `0x1400593c0`
- `0x1400b6e90`
- `0x14010046c`
- `0x140100e38`
- `0x140100f30`
- `0x140101650`
- `0x140163f78`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1401010f2`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1401010f2`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1401014c9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c4c6b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1401014c9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c4c6b`
- `ntoskrnl!CcMapData` at `0x14010118c`
- `ntoskrnl!CcMapData` at `0x14010118c`
- `ntoskrnl!CcPreparePinWrite` at `0x140101278`
- `ntoskrnl!CcPreparePinWrite` at `0x140101278`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401011b2`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1401011b2`
- `ntoskrnl!CcUnpinData` at `0x14010151b`
- `ntoskrnl!CcUnpinData` at `0x140101534`
- `ntoskrnl!CcUnpinData` at `0x1402c4cbe`
- `ntoskrnl!CcUnpinData` at `0x1402c4cd7`
- `ntoskrnl!CcUnpinData` at `0x14010151b`
- `ntoskrnl!CcUnpinData` at `0x140101534`
- `ntoskrnl!CcUnpinData` at `0x1402c4cbe`
- `ntoskrnl!CcUnpinData` at `0x1402c4cd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401013c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101493`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101579`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4b0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4c35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4d30`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401013c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101493`
- `ntoskrnl!ExReleaseResourceLite` at `0x140101579`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4b0d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4c35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c4d30`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401010b3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401013e5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401014b3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4b59`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4c55`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401010b3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401013e5`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401014b3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4b59`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402c4c55`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010113e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401014dc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4a92`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4c7e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14010113e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401014dc`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4a92`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402c4c7e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14010137c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402c4ab3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x14010137c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnInvalid` at `0x1402c4ab3`

## pseudocode

```c
void __fastcall TxfLogOldStreamData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        union _LARGE_INTEGER *a4,
        PLARGE_INTEGER a5,
        ULONG Length,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        int a10,
        int a11,
        int a12,
        int a13,
        __int16 a14,
        char a15,
        CLFS_LSN *Buffer)
{
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  char v22; // r12
  _QWORD *v23; // r13
  unsigned int v24; // r15d
  unsigned __int64 v25; // rcx
  CLFS_RECORD_INDEX idxRecord; // eax
  __int64 i; // rcx
  __int64 v28; // rdx
  __int64 v29; // r10
  __int64 j; // r9
  __int64 n; // rdx
  char v32; // r12
  _BYTE *v33; // r9
  __int64 v34; // rdx
  unsigned int ii; // r8d
  __int64 k; // r8
  __int64 m; // rdx
  PVOID v38; // rdi
  __int64 jj; // r8
  char v40; // [rsp+51h] [rbp-A7h]
  unsigned __int8 NewElement; // [rsp+53h] [rbp-A5h] BYREF
  int v42; // [rsp+54h] [rbp-A4h]
  int v43; // [rsp+58h] [rbp-A0h]
  unsigned int v44; // [rsp+5Ch] [rbp-9Ch] BYREF
  int v45; // [rsp+60h] [rbp-98h]
  PVOID VirtualAddress; // [rsp+68h] [rbp-90h] BYREF
  PVOID inserted; // [rsp+70h] [rbp-88h]
  __int64 v48; // [rsp+78h] [rbp-80h]
  int v49; // [rsp+80h] [rbp-78h]
  __int64 v50; // [rsp+88h] [rbp-70h]
  __int64 v51; // [rsp+90h] [rbp-68h]
  PVOID v52; // [rsp+98h] [rbp-60h] BYREF
  PVOID Bcb; // [rsp+A0h] [rbp-58h] BYREF
  PVOID Src; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-48h]
  __int64 v56; // [rsp+B8h] [rbp-40h]
  PFILE_OBJECT FileObject; // [rsp+108h] [rbp+10h]
  union _LARGE_INTEGER *FileOffset; // [rsp+118h] [rbp+20h]
  char v59; // [rsp+170h] [rbp+78h]

  FileOffset = a4;
  FileObject = (PFILE_OBJECT)a2;
  Src = 0;
  VirtualAddress = 0;
  Bcb = 0;
  v52 = 0;
  v19 = *(_QWORD *)(a2 + 24);
  v20 = *(_QWORD *)(v19 + 184);
  v50 = v20;
  v21 = *(_QWORD *)(v20 + 320);
  v55 = v21;
  NewElement = 0;
  v44 = 0;
  if ( !Buffer && !a7 )
    return;
  v56 = v20;
  v40 = 0;
  v45 = 0;
  inserted = 0;
  v59 = 0;
  v22 = 0;
  v51 = 0;
  v23 = (_QWORD *)(v21 + 280);
  v48 = v21 + 280;
  if ( !a10 && !*(_QWORD *)(a2 + 48) )
  {
    NtfsCreateInternalAttributeStream(a1, v19, 0, 0, 0, 0);
    FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(a2 + 24) + 280LL);
    a4 = FileOffset;
  }
  if ( Buffer )
  {
    Buffer[2] = CLFS_LSN_INVALID_EXT;
    BYTE6(Buffer[3].ullOffset) = 0;
    Buffer->ullOffset = (unsigned __int64)a4->QuadPart >> 12;
    v24 = Length;
    Buffer[3].offset.idxRecord = Length >> 12;
    Buffer[1].ullOffset = (unsigned int)((unsigned __int64)a5->QuadPart >> 12);
    WORD2(Buffer[3].ullOffset) = a14;
    v25 = *(_QWORD *)(a3 + 96);
    if ( a4->QuadPart + (unsigned __int64)Length <= v25 )
      Buffer[4].offset.idxRecord = Length;
    else
      Buffer[4].offset.idxRecord = v25 - a4->QuadPart;
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    v45 = 1;
    idxRecord = Buffer[3].offset.idxRecord;
    if ( a12 )
    {
      BYTE6(Buffer[3].ullOffset) |= 2u;
      inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), Buffer, 16 * idxRecord + 36, &NewElement);
    }
    else
    {
      v51 = TxfInsertNewTopsRange(*(_QWORD *)(v55 + 16), a3, Buffer[1].ullOffset, idxRecord, 0, (__int64)&v44);
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
    v45 = 0;
    if ( a10 )
    {
      if ( !ExIsResourceAcquiredSharedLite((PERESOURCE)(*(_QWORD *)(v50 + 104) + 64LL)) )
      {
        NtfsAcquireSharedFcb(a1, v50, 0, 0);
        v40 = 1;
      }
    }
    else
    {
      CcMapData(FileObject, FileOffset, Length, 1u, &Bcb, &Src);
    }
    v59 = NtfsAcquireScbPagingResourceShared(a1, *v23);
    if ( a1 )
    {
      v49 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v49 = i;
        if ( (unsigned int)i >= 2 )
          break;
        v28 = *(_QWORD *)(a1 + 8 * i + 48);
        if ( !v28 || v28 == *(_QWORD *)(*v23 + 184LL) )
        {
          *(_QWORD *)(a1 + 8LL * (unsigned int)i + 48) = *(_QWORD *)(*v23 + 184LL);
          break;
        }
      }
    }
    CcPreparePinWrite(*(PFILE_OBJECT *)(*v23 + 280LL), a5, Length, 0, 3u, &v52, &VirtualAddress);
    if ( a10 )
      TxfReadFileNonCached(FileObject, FileOffset, Length, VirtualAddress);
    else
      memmove(VirtualAddress, Src, Length);
    v29 = 0;
    for ( j = 0; ; j = (unsigned int)(j + 512) )
    {
      v43 = v29;
      v42 = j;
      if ( (unsigned int)j >= Length )
        break;
      *((_WORD *)&Buffer[4].ullOffset + v29 + 2) = *(_WORD *)((char *)VirtualAddress + j);
      *(_WORD *)((char *)VirtualAddress + j) = WORD2(Buffer[3].ullOffset);
      v29 = (unsigned int)(v29 + 1);
    }
    v22 = 1;
  }
  else
  {
    v24 = Length;
  }
  TxfDoWriteFileLogging(a1, a3, *((_QWORD *)FileObject->FsContext + 23), a7, a8, a9, (__int64)Buffer, a11, a13);
  if ( Buffer )
  {
    if ( ClfsLsnInvalid(Buffer + 2) )
    {
      if ( v22 )
      {
        for ( k = 0; (unsigned int)k < v24; k = (unsigned int)(k + 512) )
          *(_WORD *)((char *)VirtualAddress + k) = 0;
      }
      v32 = v59;
      if ( v59 )
      {
        if ( a1 )
        {
          for ( m = 0; m != 2; ++m )
          {
            if ( *(_QWORD *)(a1 + 8 * m + 48) == *(_QWORD *)(*v23 + 184LL) )
              *(_QWORD *)(a1 + 8 * m + 48) = 0;
          }
        }
        ExReleaseResourceLite(*(PERESOURCE *)(*v23 + 16LL));
        v32 = 0;
      }
      v38 = inserted;
      if ( !inserted )
      {
        if ( v51 )
          *(_WORD *)(16LL * v44 + v51 + 26) |= 1u;
        goto LABEL_59;
      }
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a3 + 152), v38);
    }
    else
    {
      if ( a1 )
      {
        for ( n = 0; n != 2; ++n )
        {
          if ( *(_QWORD *)(a1 + 8 * n + 48) == *(_QWORD *)(*v23 + 184LL) )
            *(_QWORD *)(a1 + 8 * n + 48) = 0;
        }
      }
      ExReleaseResourceLite(*(PERESOURCE *)(*v23 + 16LL));
      v32 = 0;
      if ( !inserted )
        goto LABEL_59;
      ExAcquireFastMutex(*(PFAST_MUTEX *)(a3 + 256));
      v33 = inserted;
      *((CLFS_LSN *)inserted + 2) = Buffer[2];
      v33[30] |= 1u;
      v34 = 0;
      for ( ii = 0; ii < v24; ii += 512 )
      {
        *(_WORD *)&v33[2 * v34 + 36] = *((_WORD *)&Buffer[4].ullOffset + v34 + 2);
        v34 = (unsigned int)(v34 + 1);
      }
    }
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a3 + 256));
  }
  else
  {
    v32 = v59;
  }
LABEL_59:
  if ( v52 )
    CcUnpinData(v52);
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v32 )
  {
    if ( a1 )
    {
      for ( jj = 0; jj != 2; ++jj )
      {
        if ( *(_QWORD *)(a1 + 8 * jj + 48) == *(_QWORD *)(*v23 + 184LL) )
          *(_QWORD *)(a1 + 8 * jj + 48) = 0;
      }
    }
    ExReleaseResourceLite(*(PERESOURCE *)(*v23 + 16LL));
  }
  if ( v40 )
    NtfsReleaseFcbEx(a1, v50, 0);
}

```

## disassembly

```asm
0x140100f30  mov     rax, rsp
0x140100f33  mov     [rax+20h], r9
0x140100f37  mov     [rax+18h], r8
0x140100f3b  mov     [rax+10h], rdx
0x140100f3f  mov     [rax+8], rcx
0x140100f43  push    rbx
0x140100f44  push    rsi
0x140100f45  push    rdi
0x140100f46  push    r12
0x140100f48  push    r13
0x140100f4a  push    r14
0x140100f4c  push    r15
0x140100f4e  sub     rsp, 0C0h
0x140100f55  mov     r14, r8
0x140100f58  mov     rsi, rdx
0x140100f5b  mov     rbx, rcx
0x140100f5e  xor     r8d, r8d
0x140100f61  mov     [rax-50h], r8
0x140100f65  mov     [rsp+0F8h+VirtualAddress], r8
0x140100f6a  mov     [rax-58h], r8
0x140100f6e  mov     [rax-60h], r8
0x140100f72  mov     rdx, [rdx+18h]
0x140100f76  mov     rax, [rdx+0B8h]
0x140100f7d  mov     [rsp+0F8h+var_70], rax
0x140100f85  mov     rcx, [rax+140h]
0x140100f8c  mov     [rsp+0F8h+var_48], rcx
0x140100f94  mov     [rsp+0F8h+NewElement], r8b
0x140100f99  mov     [rsp+0F8h+var_9C], r8d
0x140100f9e  mov     rdi, [rsp+0F8h+Buffer]
0x140100fa6  test    rdi, rdi
0x140100fa9  jnz     short loc_140100FB9
0x140100fab  cmp     [rsp+0F8h+arg_30], r8
0x140100fb3  jz      loc_14010159F
0x140100fb9  mov     [rsp+0F8h+var_40], rax
0x140100fc1  mov     [rsp+0F8h+var_A7], r8b
0x140100fc6  mov     [rsp+0F8h+var_98], r8d
0x140100fcb  mov     [rsp+0F8h+var_88], r8
0x140100fd0  mov     al, r8b
0x140100fd3  mov     [rsp+0F8h+arg_70], al
0x140100fda  mov     [rsp+0F8h+var_A8], al
0x140100fde  mov     r12b, r8b
0x140100fe1  mov     [rsp+0F8h+var_A6], r8b
0x140100fe6  mov     [rsp+0F8h+var_68], r8
0x140100fee  lea     r13, [rcx+118h]
0x140100ff5  mov     [rsp+0F8h+var_80], r13
0x140100ffa  cmp     [rsp+0F8h+arg_48], r8d
0x140101002  jnz     short loc_14010103D
0x140101004  cmp     [rsi+30h], r8
0x140101008  jnz     short loc_14010103D
0x14010100a  mov     [rsp+0F8h+var_D0], r8
0x14010100f  mov     [rsp+0F8h+Bcb], r8
0x140101014  xor     r9d, r9d
0x140101017  mov     rcx, rbx
0x14010101a  call    NtfsCreateInternalAttributeStream
0x14010101f  mov     rax, [rsi+18h]
0x140101023  mov     rsi, [rax+118h]
0x14010102a  mov     [rsp+0F8h+FileObject], rsi
0x140101032  mov     r9, [rsp+0F8h+FileOffset]
0x14010103a  xor     r8d, r8d
0x14010103d  test    rdi, rdi
0x140101040  jz      loc_140101306
0x140101046  mov     rax, qword ptr cs:CLFS_LSN_INVALID_EXT
0x14010104d  mov     [rdi+10h], rax
0x140101051  mov     [rdi+1Eh], r8b
0x140101055  mov     rax, [r9]
0x140101058  shr     rax, 0Ch
0x14010105c  mov     [rdi], rax
0x14010105f  mov     r15d, [rsp+0F8h+Length]
0x140101067  mov     eax, r15d
0x14010106a  shr     eax, 0Ch
0x14010106d  mov     [rdi+18h], eax
0x140101070  mov     rax, [rsp+0F8h+arg_20]
0x140101078  mov     rax, [rax]
0x14010107b  shr     rax, 0Ch
0x14010107f  mov     eax, eax
0x140101081  mov     [rdi+8], rax
0x140101085  movzx   eax, [rsp+0F8h+arg_68]
0x14010108d  mov     [rdi+1Ch], ax
0x140101091  mov     rcx, [r14+60h]
0x140101095  mov     rdx, [r9]
0x140101098  lea     rax, [rdx+r15]
0x14010109c  cmp     rax, rcx
0x14010109f  jbe     short loc_1401010A8
0x1401010a1  sub     ecx, edx
0x1401010a3  mov     [rdi+20h], ecx
0x1401010a6  jmp     short loc_1401010AC
0x1401010a8  mov     [rdi+20h], r15d
0x1401010ac  mov     rcx, [r14+100h]; FastMutex
0x1401010b3  call    cs:__imp_ExAcquireFastMutex
0x1401010ba  nop     dword ptr [rax+rax+00h]
0x1401010bf  mov     esi, 1
0x1401010c4  mov     [rsp+0F8h+var_98], esi
0x1401010c8  mov     eax, [rdi+18h]
0x1401010cb  xor     r12d, r12d
0x1401010ce  cmp     [rsp+0F8h+arg_58], r12d
0x1401010d6  jz      short loc_140101105
0x1401010d8  or      byte ptr [rdi+1Eh], 2
0x1401010dc  shl     eax, 4
0x1401010df  lea     r8d, [rax+24h]; BufferSize
0x1401010e3  lea     rcx, [r14+98h]; Table
0x1401010ea  lea     r9, [rsp+0F8h+NewElement]; NewElement
0x1401010ef  mov     rdx, rdi; Buffer
0x1401010f2  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1401010f9  nop     dword ptr [rax+rax+00h]
0x1401010fe  mov     [rsp+0F8h+var_88], rax
0x140101103  jmp     short loc_140101137
0x140101105  lea     rcx, [rsp+0F8h+var_9C]
0x14010110a  mov     [rsp+0F8h+var_D0], rcx
0x14010110f  mov     [rsp+0F8h+Bcb], r12
0x140101114  mov     r9d, eax
0x140101117  mov     r8, [rdi+8]
0x14010111b  mov     rdx, r14
0x14010111e  mov     rcx, [rsp+0F8h+var_48]
0x140101126  mov     rcx, [rcx+10h]
0x14010112a  call    TxfInsertNewTopsRange
0x14010112f  mov     [rsp+0F8h+var_68], rax
0x140101137  mov     rcx, [r14+100h]; FastMutex
0x14010113e  call    cs:__imp_ExReleaseFastMutex
0x140101145  nop     dword ptr [rax+rax+00h]
0x14010114a  mov     [rsp+0F8h+var_98], r12d
0x14010114f  cmp     [rsp+0F8h+arg_48], r12d
0x140101157  mov     r12, [rsp+0F8h+FileObject]
0x14010115f  jnz     short loc_140101198
0x140101161  lea     rax, [rsp+0F8h+Src]
0x140101169  mov     [rsp+0F8h+var_D0], rax; Buffer
0x14010116e  lea     rax, [rsp+0F8h+var_58]
0x140101176  mov     [rsp+0F8h+Bcb], rax; Bcb
0x14010117b  mov     r9d, esi; Flags
0x14010117e  mov     r8d, r15d; Length
0x140101181  mov     rdx, [rsp+0F8h+FileOffset]; FileOffset
0x140101189  mov     rcx, r12; FileObject
0x14010118c  call    cs:__imp_CcMapData
0x140101193  nop     dword ptr [rax+rax+00h]
0x140101198  cmp     [rsp+0F8h+arg_48], 0
0x1401011a0  jz      short loc_1401011DD
0x1401011a2  mov     rcx, [rsp+0F8h+var_70]
0x1401011aa  mov     rcx, [rcx+68h]
0x1401011ae  add     rcx, 40h ; '@'; Resource
0x1401011b2  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x1401011b9  nop     dword ptr [rax+rax+00h]
0x1401011be  test    eax, eax
0x1401011c0  jnz     short loc_1401011DD
0x1401011c2  xor     r9d, r9d
0x1401011c5  xor     r8d, r8d
0x1401011c8  mov     rdx, [rsp+0F8h+var_70]
0x1401011d0  mov     rcx, rbx
0x1401011d3  call    NtfsAcquireSharedFcb
0x1401011d8  mov     [rsp+0F8h+var_A7], sil
0x1401011dd  mov     rdx, [r13+0]
0x1401011e1  mov     rcx, rbx
0x1401011e4  call    NtfsAcquireScbPagingResourceShared
0x1401011e9  mov     [rsp+0F8h+arg_70], al
0x1401011f0  mov     [rsp+0F8h+var_A8], al
0x1401011f4  test    rbx, rbx
0x1401011f7  jz      short loc_140101240
0x1401011f9  mov     [rsp+0F8h+var_78], 0
0x140101204  xor     ecx, ecx
0x140101206  mov     [rsp+0F8h+var_78], ecx
0x14010120d  cmp     ecx, 2
0x140101210  jnb     short loc_140101240
0x140101212  mov     r8d, ecx
0x140101215  mov     rdx, [rbx+rcx*8+30h]
0x14010121a  test    rdx, rdx
0x14010121d  jz      short loc_140101230
0x14010121f  mov     rax, [r13+0]
0x140101223  cmp     rdx, [rax+0B8h]
0x14010122a  jz      short loc_140101230
0x14010122c  add     ecx, esi
0x14010122e  jmp     short loc_140101206
0x140101230  mov     rax, [r13+0]
0x140101234  mov     rcx, [rax+0B8h]
0x14010123b  mov     [rbx+r8*8+30h], rcx
0x140101240  mov     rcx, [r13+0]
0x140101244  lea     rax, [rsp+0F8h+VirtualAddress]
0x140101249  mov     [rsp+0F8h+var_C8], rax; Buffer
0x14010124e  lea     rax, [rsp+0F8h+var_60]
0x140101256  mov     [rsp+0F8h+var_D0], rax; Bcb
0x14010125b  mov     dword ptr [rsp+0F8h+Bcb], 3; Flags
0x140101263  xor     r9d, r9d; Zero
0x140101266  mov     r8d, r15d; Length
0x140101269  mov     rdx, [rsp+0F8h+arg_20]; FileOffset
0x140101271  mov     rcx, [rcx+118h]; FileObject
0x140101278  call    cs:__imp_CcPreparePinWrite
0x14010127f  nop     dword ptr [rax+rax+00h]
0x140101284  cmp     [rsp+0F8h+arg_48], 0
0x14010128c  jz      short loc_1401012A8
0x14010128e  mov     r9, [rsp+0F8h+VirtualAddress]; VirtualAddress
0x140101293  mov     r8d, r15d; Length
0x140101296  mov     rdx, [rsp+0F8h+FileOffset]; StartingOffset
0x14010129e  mov     rcx, r12; FileObject
0x1401012a1  call    TxfReadFileNonCached
0x1401012a6  jmp     short loc_1401012BD
0x1401012a8  mov     r8, r15; Size
0x1401012ab  mov     rdx, [rsp+0F8h+Src]; Src
0x1401012b3  mov     rcx, [rsp+0F8h+VirtualAddress]; void *
0x1401012b8  call    memmove
0x1401012bd  xor     r10d, r10d
0x1401012c0  xor     r9d, r9d
0x1401012c3  mov     [rsp+0F8h+var_A0], r10d
0x1401012c8  mov     [rsp+0F8h+var_A4], r9d
0x1401012cd  cmp     r9d, r15d
0x1401012d0  jnb     short loc_1401012FC
0x1401012d2  mov     rax, [rsp+0F8h+VirtualAddress]
0x1401012d7  movzx   ecx, word ptr [r9+rax]
0x1401012dc  mov     [rdi+r10*2+24h], cx
0x1401012e2  movzx   ecx, word ptr [rdi+1Ch]
0x1401012e6  mov     rax, [rsp+0F8h+VirtualAddress]
0x1401012eb  mov     [r9+rax], cx
0x1401012f0  add     r10d, esi
0x1401012f3  add     r9d, 200h
0x1401012fa  jmp     short loc_1401012C3
0x1401012fc  mov     r12b, sil
0x1401012ff  mov     [rsp+0F8h+var_A6], sil
0x140101304  jmp     short loc_140101313
0x140101306  mov     esi, 1
0x14010130b  mov     r15d, [rsp+0F8h+Length]
0x140101313  mov     r8, [rsp+0F8h+FileObject]
0x14010131b  mov     r8, [r8+18h]
0x14010131f  mov     eax, [rsp+0F8h+arg_60]
0x140101326  mov     [rsp+0F8h+var_B8], eax
0x14010132a  mov     eax, [rsp+0F8h+arg_50]
0x140101331  mov     [rsp+0F8h+var_C0], eax
0x140101335  mov     [rsp+0F8h+var_C8], rdi
0x14010133a  mov     rax, [rsp+0F8h+arg_40]
0x140101342  mov     [rsp+0F8h+var_D0], rax
0x140101347  mov     rax, [rsp+0F8h+arg_38]
0x14010134f  mov     [rsp+0F8h+Bcb], rax
0x140101354  mov     r9, [rsp+0F8h+arg_30]
0x14010135c  mov     r8, [r8+0B8h]
0x140101363  mov     rdx, r14
0x140101366  mov     rcx, rbx
0x140101369  call    TxfDoWriteFileLogging
0x14010136e  nop
0x14010136f  test    rdi, rdi
0x140101372  jz      loc_140101506
0x140101378  lea     rcx, [rdi+10h]; plsn
0x14010137c  call    cs:__imp_ClfsLsnInvalid
0x140101383  nop     dword ptr [rax+rax+00h]
0x140101388  test    al, al
0x14010138a  jnz     loc_14010142E
0x140101390  test    rbx, rbx
0x140101393  jz      short loc_1401013BB
0x140101395  xor     edx, edx
0x140101397  mov     rax, [r13+0]
0x14010139b  mov     rcx, [rax+0B8h]
0x1401013a2  cmp     [rbx+rdx*8+30h], rcx
0x1401013a7  jnz     short loc_1401013B2
0x1401013a9  mov     qword ptr [rbx+rdx*8+30h], 0
0x1401013b2  add     rdx, rsi
0x1401013b5  cmp     rdx, 2
0x1401013b9  jnz     short loc_140101397
0x1401013bb  mov     rcx, [r13+0]
0x1401013bf  mov     rcx, [rcx+10h]; Resource
0x1401013c3  call    cs:__imp_ExReleaseResourceLite
0x1401013ca  nop     dword ptr [rax+rax+00h]
0x1401013cf  xor     r12b, r12b
0x1401013d2  cmp     [rsp+0F8h+var_88], 0
0x1401013d8  jz      loc_14010150E
0x1401013de  mov     rcx, [r14+100h]; FastMutex
0x1401013e5  call    cs:__imp_ExAcquireFastMutex
0x1401013ec  nop     dword ptr [rax+rax+00h]
0x1401013f1  mov     rax, [rdi+10h]
0x1401013f5  mov     r9, [rsp+0F8h+var_88]
0x1401013fa  mov     [r9+10h], rax
0x1401013fe  or      [r9+1Eh], sil
0x140101402  xor     edx, edx
0x140101404  xor     r8d, r8d
0x140101407  test    r15d, r15d
0x14010140a  jz      loc_1401014D5
0x140101410  movzx   eax, word ptr [rdi+rdx*2+24h]
0x140101415  mov     [r9+rdx*2+24h], ax
0x14010141b  add     edx, esi
0x14010141d  add     r8d, 200h
0x140101424  cmp     r8d, r15d
0x140101427  jb      short loc_140101410
0x140101429  jmp     loc_1401014D5
0x14010142e  test    r12b, r12b
0x140101431  jz      short loc_140101453
0x140101433  xor     r8d, r8d
0x140101436  test    r15d, r15d
0x140101439  jz      short loc_140101453
0x14010143b  xor     ecx, ecx
0x14010143d  mov     rax, [rsp+0F8h+VirtualAddress]
0x140101442  mov     [r8+rax], cx
0x140101447  add     r8d, 200h
0x14010144e  cmp     r8d, r15d
0x140101451  jb      short loc_14010143B
0x140101453  mov     r12b, [rsp+0F8h+arg_70]
0x14010145b  test    r12b, r12b
0x14010145e  jz      short loc_1401014A2
0x140101460  test    rbx, rbx
0x140101463  jz      short loc_14010148B
0x140101465  xor     edx, edx
0x140101467  mov     rax, [r13+0]
0x14010146b  mov     rcx, [rax+0B8h]
0x140101472  cmp     [rbx+rdx*8+30h], rcx
0x140101477  jnz     short loc_140101482
0x140101479  mov     qword ptr [rbx+rdx*8+30h], 0
0x140101482  add     rdx, rsi
0x140101485  cmp     rdx, 2
  ... truncated ...
```
