# CClfsLogFcbPhysical::ReadLogPagingIo(_LARGE_INTEGER const &,_CLFS_READ_BUFFER const &,ulong,IClfsRequestAsync *,ulong &)

- ea: `0x140065110`
- end: `0x14006584b`
- name: `?ReadLogPagingIo@CClfsLogFcbPhysical@@UEAAJAEBT_LARGE_INTEGER@@AEBU_CLFS_READ_BUFFER@@KPEAUIClfsRequestAsync@@AEAK@Z`
- size: `1851`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, const union _LARGE_INTEGER *@<rdx>, const struct _CLFS_READ_BUFFER *@<r8>, unsigned int@<r9d>, struct IClfsRequestAsync *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400161b0`

## callees

- `0x140005840`
- `0x14000593c`
- `0x140017f20`
- `0x140018280`
- `0x140065110`
- `0x140066cc0`
- `0x140066e00`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400657d1`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400657f2`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400657d1`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400657f2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400653a6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400653c7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400653a6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400653c7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140065731`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140065731`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::ReadLogPagingIo(
        CClfsLogFcbPhysical *this,
        const union _LARGE_INTEGER *a2,
        const struct _CLFS_READ_BUFFER *a3,
        int a4,
        struct IClfsRequestAsync *a5,
        unsigned int *ullOffset)
{
  CClfsLogFcbPhysical *v7; // r15
  int v8; // r14d
  BOOLEAN v9; // si
  BOOLEAN v10; // r12
  struct IClfsRequestAsync *v11; // rdi
  char *MappedSystemVa; // rax
  char *v13; // r13
  LONGLONG QuadPart; // rbx
  _DWORD *v15; // rdi
  CLFS_LSN v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdx
  CLFS_RECORD_INDEX idxRecord; // r12d
  CLFS_LSN v22; // rbx
  ULONGLONG ullOffset_high; // rbx
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // r8
  unsigned __int64 v27; // rdx
  CLFS_RECORD_INDEX v28; // r15d
  CLFS_LSN v29; // rdi
  ULONGLONG v30; // rdi
  union _CLS_LSN v31; // rcx
  ULONGLONG v32; // rdx
  CLFS_RECORD_INDEX v33; // ecx
  union _CLS_LSN v34; // rsi
  unsigned int v35; // ebx
  CClfsLogFcbPhysical *v36; // r10
  char v37; // al
  unsigned __int64 v38; // rdi
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rbx
  __int64 v41; // rdi
  int v42; // esi
  unsigned int *v43; // r12
  union _CLS_LSN v44; // rax
  int v45; // edx
  char v46; // al
  __int64 v47; // r8
  unsigned int v48; // ebx
  BOOLEAN v50; // [rsp+40h] [rbp-C8h]
  BOOLEAN v51; // [rsp+41h] [rbp-C7h]
  unsigned __int64 v52; // [rsp+48h] [rbp-C0h]
  unsigned __int64 v53; // [rsp+58h] [rbp-B0h]
  union _CLS_LSN v54; // [rsp+60h] [rbp-A8h] BYREF
  LONGLONG v55; // [rsp+68h] [rbp-A0h]
  PMDL MemoryDescriptorList[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v57; // [rsp+80h] [rbp-88h]
  union _CLS_LSN v58; // [rsp+88h] [rbp-80h] BYREF
  char *v59; // [rsp+90h] [rbp-78h]
  union _CLS_LSN v60; // [rsp+98h] [rbp-70h] BYREF
  _DWORD v61[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-60h]
  __int64 v63; // [rsp+B0h] [rbp-58h]
  int v64; // [rsp+B8h] [rbp-50h]
  int v65; // [rsp+BCh] [rbp-4Ch]
  unsigned __int64 v66; // [rsp+C0h] [rbp-48h]
  unsigned int v69; // [rsp+120h] [rbp+18h] BYREF
  size_t Size; // [rsp+128h] [rbp+20h]

  LODWORD(Size) = a4;
  v7 = this;
  v60 = CLFS_LSN_INVALID;
  *(_OWORD *)MemoryDescriptorList = *(_OWORD *)a3;
  v57 = *((_QWORD *)a3 + 2);
  v69 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  *ullOffset = 0;
  v11 = a5;
  (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a5 + 16LL))(a5);
  if ( MemoryDescriptorList[1] )
  {
    if ( (MemoryDescriptorList[1]->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)MemoryDescriptorList[1]->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MemoryDescriptorList[1], 0, MmCached, 0, 0, 0x40000010u);
    v13 = &MappedSystemVa[(unsigned int)v57];
  }
  else
  {
    v13 = (char *)MemoryDescriptorList[0] + (unsigned int)v57;
  }
  v59 = v13;
  if ( v13 )
  {
    QuadPart = a2->QuadPart;
    v15 = (_DWORD *)((char *)v7 + 1368);
    v62 = 0;
    if ( v7 != (CClfsLogFcbPhysical *)-1368LL && (v16 = CLFS_LSN_INVALID, CLFS_LSN_INVALID.ullOffset == *(_QWORD *)v15) )
    {
      idxRecord = 0;
      LODWORD(ullOffset_high) = -1;
    }
    else
    {
      if ( CClfsLogFcbPhysical::ValidateContainerSize(v7) )
      {
        v17 = 0xFFFFFFFFLL;
        if ( v7 != (CClfsLogFcbPhysical *)-1368LL )
          v17 = *v15 & 0xFFFFFE00;
        v18 = 0xFFFFFFFFLL;
        if ( v7 != (CClfsLogFcbPhysical *)-1368LL )
          v18 = *((unsigned int *)v7 + 343);
        v19 = *((_QWORD *)v7 + 87);
        v20 = (v17 + QuadPart + v19 * v18) % v19;
        v53 = (v17 + QuadPart + v19 * v18) / v19;
        if ( !HIDWORD(v53) && !HIDWORD(v20) )
        {
          if ( (_DWORD)v53 == -1 || (idxRecord = (v17 + QuadPart + v19 * v18) % v19, (v20 & 0x1FF) != 0) )
          {
            v16 = CLFS_LSN_INVALID;
            v22 = CLFS_LSN_INVALID;
            idxRecord = CLFS_LSN_INVALID.offset.idxRecord;
          }
          else
          {
            v55 = __PAIR64__(v53, v20);
            v16 = CLFS_LSN_INVALID;
            v22.ullOffset = __PAIR64__(v53, v20);
          }
          ullOffset_high = HIDWORD(v22.ullOffset);
          goto LABEL_19;
        }
        idxRecord = 0;
      }
      else
      {
        idxRecord = 0;
      }
      LODWORD(ullOffset_high) = -1;
      v16 = CLFS_LSN_INVALID;
    }
LABEL_19:
    v54.ullOffset = __PAIR64__(ullOffset_high, idxRecord);
    v55 = (unsigned int)Size + a2->QuadPart;
    v63 = 0;
    if ( v7 != (CClfsLogFcbPhysical *)-1368LL && v16.ullOffset == *(_QWORD *)v15
      || !CClfsLogFcbPhysical::ValidateContainerSize(v7) )
    {
      goto LABEL_58;
    }
    v24 = 0xFFFFFFFFLL;
    if ( v7 != (CClfsLogFcbPhysical *)-1368LL )
      v24 = *v15 & 0xFFFFFE00;
    v25 = 0xFFFFFFFFLL;
    if ( v7 != (CClfsLogFcbPhysical *)-1368LL )
      v25 = *((unsigned int *)v7 + 343);
    v26 = *((_QWORD *)v7 + 87);
    v27 = (v24 + v55 + v26 * v25) % v26;
    v52 = (v24 + v55 + v26 * v25) / v26;
    if ( HIDWORD(v52) || HIDWORD(v27) )
    {
LABEL_58:
      v28 = 0;
      LODWORD(v30) = -1;
    }
    else
    {
      if ( (_DWORD)v52 == -1 || (v28 = (v24 + v55 + v26 * v25) % v26, (v27 & 0x1FF) != 0) )
      {
        v29 = CLFS_LSN_INVALID;
        v28 = CLFS_LSN_INVALID.offset.idxRecord;
      }
      else
      {
        v65 = (v24 + v55 + v26 * v25) / v26;
        v64 = (v24 + v55 + v26 * v25) % v26;
        v29.ullOffset = __PAIR64__(v52, v27);
      }
      v30 = HIDWORD(v29.ullOffset);
    }
    v50 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
    v51 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 1200), 1u);
    v31 = *(union _CLS_LSN *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, _DWORD *))(*(_QWORD *)this + 352LL))(
                               this,
                               v61);
    v58 = v31;
    v32 = HIDWORD(v31.ullOffset);
    if ( v31.offset.cidContainer == -1 )
    {
      v34 = CLFS_LSN_INVALID;
      LODWORD(v32) = CLFS_LSN_INVALID.offset.cidContainer;
      v33 = CLFS_LSN_INVALID.offset.idxRecord;
    }
    else
    {
      v33 = v31.offset.idxRecord & 0xFFFFFE00;
      v61[1] = v32;
      v61[0] = v33;
      v34.ullOffset = __PAIR64__(v32, v33);
    }
    v58 = v34;
    if ( (unsigned int)v30 <= v34.offset.cidContainer && ((_DWORD)v30 != v34.offset.cidContainer || v28 < v33) )
    {
      v8 = -1073741807;
      v35 = Size;
      memset(v13, 0, (unsigned int)Size);
      *ullOffset = v35;
      v11 = a5;
      (*(void (__fastcall **)(struct IClfsRequestAsync *, __int64, _QWORD))(*(_QWORD *)a5 + 88LL))(
        a5,
        3221225489LL,
        v35);
LABEL_38:
      v7 = this;
      v9 = v50;
      v10 = v51;
      goto LABEL_70;
    }
    v36 = this;
    if ( this == (CClfsLogFcbPhysical *)-480LL )
    {
      v37 = 0;
    }
    else
    {
      if ( __PAIR64__(ullOffset_high, idxRecord) >= *((_QWORD *)this + 60) )
      {
LABEL_55:
        v48 = Size;
        memset(v13, 0, (unsigned int)Size);
        *ullOffset = v48;
        v11 = a5;
        (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a5 + 88LL))(a5, 0, v48);
        v8 = -1073741807;
        goto LABEL_38;
      }
      v37 = 1;
    }
    if ( v37 )
    {
      if ( (unsigned int)ullOffset_high > (unsigned int)v32 || (_DWORD)ullOffset_high == (_DWORD)v32 && idxRecord >= v33 )
      {
        v11 = a5;
        v42 = v57;
        v43 = ullOffset;
      }
      else
      {
        v38 = CClfsLogFcbPhysical::LsnToCacheOffset(this, &v54);
        v39 = CClfsLogFcbPhysical::LsnToCacheOffset(this, &v58);
        v40 = v39 - v38;
        v66 = v40;
        v41 = (unsigned int)(v39 - v38);
        memset(v13, 0, (unsigned int)v40);
        v54 = v34;
        v42 = v40 + v57;
        LODWORD(v57) = v40 + v57;
        v13 += v41;
        v59 = v13;
        v43 = ullOffset;
        *ullOffset += v40;
        v11 = a5;
        (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a5 + 88LL))(
          a5,
          0,
          (unsigned int)v40);
        v36 = this;
      }
      v44 = v54;
      ullOffset = (unsigned int *)v54.ullOffset;
      while ( 1 )
      {
        v45 = Size;
        if ( *v43 >= (unsigned int)Size )
          goto LABEL_38;
        if ( this == (CClfsLogFcbPhysical *)-480LL )
        {
          v46 = 0;
        }
        else
        {
          if ( v44.ullOffset >= *((_QWORD *)this + 60) )
            goto LABEL_38;
          v46 = 1;
          v45 = Size;
        }
        if ( !v46 )
          goto LABEL_38;
        v8 = CClfsLogFcbPhysical::ReadLog(
               v36,
               (const union _CLS_LSN *)&ullOffset,
               (const struct _CLFS_READ_BUFFER *)MemoryDescriptorList,
               (v45 - *v43) >> 9,
               1u,
               v11,
               &v60,
               &v69);
        v47 = v69;
        *v43 += v69;
        v42 += v47;
        LODWORD(v57) = v42;
        v13 += v47;
        v59 = v13;
        (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD))(*(_QWORD *)v11 + 88LL))(v11, (unsigned int)v8);
        if ( v8 < 0 )
          goto LABEL_38;
        v44 = v60;
        ullOffset = (unsigned int *)v60.ullOffset;
        v36 = this;
      }
    }
    goto LABEL_55;
  }
  v8 = -1073741670;
LABEL_70:
  if ( v9 )
    ExReleaseResourceForThreadLite((PERESOURCE)((char *)v7 + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
  if ( v10 )
    ExReleaseResourceForThreadLite((PERESOURCE)((char *)v7 + 1200), (ERESOURCE_THREAD)KeGetCurrentThread());
  if ( v8 < 0 )
    (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)v11 + 88LL))(
      v11,
      (unsigned int)v8,
      0);
  if ( (*(unsigned int (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v11 + 24LL))(v11) )
    return 259;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140065110  mov     r11, rsp
0x140065113  mov     [r11+20h], r9d
0x140065117  mov     [r11+10h], rdx
0x14006511b  mov     [r11+8], rcx
0x14006511f  push    rbx
0x140065120  push    rsi
0x140065121  push    rdi
0x140065122  push    r12
0x140065124  push    r13
0x140065126  push    r14
0x140065128  push    r15
0x14006512a  sub     rsp, 0D0h
0x140065131  mov     rbx, rdx
0x140065134  mov     r15, rcx
0x140065137  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14006513e  mov     [r11-70h], rax
0x140065142  movups  xmm0, xmmword ptr [r8]
0x140065146  movups  xmmword ptr [rsp+108h+MemoryDescriptorList], xmm0
0x14006514b  movsd   xmm1, qword ptr [r8+10h]
0x140065151  movsd   [rsp+108h+var_88], xmm1
0x14006515a  mov     dword ptr [r11+18h], 0
0x140065162  xor     r14d, r14d
0x140065165  mov     [rsp+108h+var_B8], r14d
0x14006516a  xor     sil, sil
0x14006516d  mov     [rsp+108h+var_C8], sil
0x140065172  xor     r12b, r12b
0x140065175  mov     [rsp+108h+var_C7], r12b
0x14006517a  mov     rax, qword ptr [rsp+108h+arg_28]
0x140065182  mov     [rax], r14d
0x140065185  mov     rdi, [rsp+108h+arg_20]
0x14006518d  mov     rax, [rdi]
0x140065190  mov     rax, [rax+10h]
0x140065194  mov     rcx, rdi
0x140065197  call    _guard_dispatch_icall
0x14006519c  nop
0x14006519d  mov     rcx, [rsp+108h+MemoryDescriptorList+8]; MemoryDescriptorList
0x1400651a2  test    rcx, rcx
0x1400651a5  jz      loc_14006579C
0x1400651ab  test    byte ptr [rcx+0Ah], 5
0x1400651af  jz      loc_140065718
0x1400651b5  mov     rax, [rcx+18h]
0x1400651b9  mov     r13d, dword ptr [rsp+108h+var_88]
0x1400651c1  add     r13, rax
0x1400651c4  mov     [rsp+108h+var_78], r13
0x1400651cc  test    r13, r13
0x1400651cf  jz      loc_1400656EA
0x1400651d5  mov     rbx, [rbx]
0x1400651d8  lea     rdi, [r15+558h]
0x1400651df  mov     [rsp+108h+var_B0], 0
0x1400651e8  mov     [rsp+108h+var_60], 0
0x1400651f4  test    rdi, rdi
0x1400651f7  jz      short loc_140065209
0x1400651f9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140065200  cmp     rax, [rdi]
0x140065203  jz      loc_140065742
0x140065209  mov     rcx, r15; this
0x14006520c  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x140065211  test    al, al
0x140065213  jz      loc_140065704
0x140065219  or      esi, 0FFFFFFFFh
0x14006521c  mov     ecx, esi
0x14006521e  test    rdi, rdi
0x140065221  jz      short loc_14006522B
0x140065223  mov     ecx, [rdi]
0x140065225  and     ecx, 0FFFFFE00h
0x14006522b  mov     eax, esi
0x14006522d  test    rdi, rdi
0x140065230  jz      short loc_140065235
0x140065232  mov     eax, [rdi+4]
0x140065235  mov     r8, [r15+2B8h]
0x14006523c  imul    rax, r8
0x140065240  add     rax, rbx
0x140065243  add     rax, rcx
0x140065246  xor     edx, edx
0x140065248  div     r8
0x14006524b  mov     [rsp+108h+var_B0], rax
0x140065250  shr     rax, 20h
0x140065254  test    eax, eax
0x140065256  jnz     loc_14006574F
0x14006525c  mov     eax, dword ptr [rsp+108h+var_B0]
0x140065260  mov     [rsp+108h+var_B0], rdx
0x140065265  shr     rdx, 20h
0x140065269  test    edx, edx
0x14006526b  jnz     loc_14006574F
0x140065271  cmp     eax, esi
0x140065273  jz      loc_14006576D
0x140065279  mov     r12d, dword ptr [rsp+108h+var_B0]
0x14006527e  test    r12d, 1FFh
0x140065285  jnz     loc_14006576D
0x14006528b  mov     dword ptr [rsp+108h+var_A0+4], eax
0x14006528f  mov     dword ptr [rsp+108h+var_A0], r12d
0x140065294  mov     dword ptr [rsp+108h+var_C0], r12d
0x140065299  mov     dword ptr [rsp+108h+var_C0+4], eax
0x14006529d  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400652a4  mov     rbx, [rsp+108h+var_C0]
0x1400652a9  shr     rbx, 20h
0x1400652ad  mov     dword ptr [rsp+108h+var_A8], r12d
0x1400652b2  mov     dword ptr [rsp+108h+var_A8+4], ebx
0x1400652b6  mov     edx, dword ptr [rsp+108h+Size]
0x1400652bd  mov     rcx, [rsp+108h+arg_8]
0x1400652c5  mov     rcx, [rcx]
0x1400652c8  add     rcx, rdx
0x1400652cb  mov     [rsp+108h+var_A0], rcx
0x1400652d0  mov     [rsp+108h+var_C0], 0
0x1400652d9  mov     [rsp+108h+var_58], 0
0x1400652e5  test    rdi, rdi
0x1400652e8  jz      short loc_1400652F3
0x1400652ea  cmp     rax, [rdi]
0x1400652ed  jz      loc_1400656FA
0x1400652f3  mov     rcx, r15; this
0x1400652f6  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x1400652fb  test    al, al
0x1400652fd  jz      loc_1400656FA
0x140065303  mov     ecx, esi
0x140065305  test    rdi, rdi
0x140065308  jz      short loc_140065312
0x14006530a  mov     ecx, [rdi]
0x14006530c  and     ecx, 0FFFFFE00h
0x140065312  mov     eax, esi
0x140065314  test    rdi, rdi
0x140065317  jz      short loc_14006531C
0x140065319  mov     eax, [rdi+4]
0x14006531c  mov     r8, [r15+2B8h]
0x140065323  imul    rax, r8
0x140065327  add     rax, [rsp+108h+var_A0]
0x14006532c  add     rax, rcx
0x14006532f  xor     edx, edx
0x140065331  div     r8
0x140065334  mov     [rsp+108h+var_C0], rax
0x140065339  shr     rax, 20h
0x14006533d  test    eax, eax
0x14006533f  jnz     loc_1400656FA
0x140065345  mov     eax, dword ptr [rsp+108h+var_C0]
0x140065349  mov     [rsp+108h+var_C0], rdx
0x14006534e  shr     rdx, 20h
0x140065352  test    edx, edx
0x140065354  jnz     loc_1400656FA
0x14006535a  cmp     eax, esi
0x14006535c  jz      loc_140065786
0x140065362  mov     r15d, dword ptr [rsp+108h+var_C0]
0x140065367  test    r15d, 1FFh
0x14006536e  jnz     loc_140065786
0x140065374  mov     [rsp+108h+var_4C], eax
0x14006537b  mov     [rsp+108h+var_50], r15d
0x140065383  mov     dword ptr [rsp+108h+var_C0], r15d
0x140065388  mov     dword ptr [rsp+108h+var_C0+4], eax
0x14006538c  mov     rdi, [rsp+108h+var_C0]
0x140065391  shr     rdi, 20h
0x140065395  mov     rcx, [rsp+108h+arg_0]
0x14006539d  add     rcx, 0C8h; Resource
0x1400653a4  mov     dl, 1; Wait
0x1400653a6  call    cs:__imp_ExAcquireResourceSharedLite
0x1400653ad  nop     dword ptr [rax+rax+00h]
0x1400653b2  mov     [rsp+108h+var_C8], al
0x1400653b6  mov     rcx, [rsp+108h+arg_0]
0x1400653be  add     rcx, 4B0h; Resource
0x1400653c5  mov     dl, 1; Wait
0x1400653c7  call    cs:__imp_ExAcquireResourceSharedLite
0x1400653ce  nop     dword ptr [rax+rax+00h]
0x1400653d3  mov     [rsp+108h+var_C7], al
0x1400653d7  mov     r8, [rsp+108h+arg_0]
0x1400653df  mov     rcx, [r8]
0x1400653e2  mov     rax, [rcx+160h]
0x1400653e9  lea     rdx, [rsp+108h+var_68]
0x1400653f1  mov     rcx, r8
0x1400653f4  call    _guard_dispatch_icall
0x1400653f9  mov     rcx, [rax]
0x1400653fc  mov     qword ptr [rsp+108h+var_80], rcx
0x140065404  mov     rdx, rcx
0x140065407  shr     rdx, 20h
0x14006540b  cmp     edx, esi
0x14006540d  jz      loc_140065754
0x140065413  and     ecx, 0FFFFFE00h
0x140065419  mov     [rsp+108h+var_64], edx
0x140065420  mov     [rsp+108h+var_68], ecx
0x140065427  mov     dword ptr [rsp+108h+var_C0], ecx
0x14006542b  mov     dword ptr [rsp+108h+var_C0+4], edx
0x14006542f  mov     rsi, [rsp+108h+var_C0]
0x140065434  mov     qword ptr [rsp+108h+var_80], rsi
0x14006543c  mov     rax, rsi
0x14006543f  shr     rax, 20h
0x140065443  cmp     edi, eax
0x140065445  ja      short loc_1400654AB
0x140065447  jnz     short loc_14006544E
0x140065449  cmp     r15d, ecx
0x14006544c  jnb     short loc_1400654AB
0x14006544e  mov     r14d, 0C0000011h
0x140065454  mov     [rsp+108h+var_B8], r14d
0x140065459  mov     ebx, dword ptr [rsp+108h+Size]
0x140065460  mov     r8d, ebx; Size
0x140065463  xor     edx, edx; Val
0x140065465  mov     rcx, r13; void *
0x140065468  call    memset
0x14006546d  mov     rax, qword ptr [rsp+108h+arg_28]
0x140065475  mov     [rax], ebx
0x140065477  mov     rdi, [rsp+108h+arg_20]
0x14006547f  mov     rax, [rdi]
0x140065482  mov     rax, [rax+58h]
0x140065486  mov     r8d, ebx
0x140065489  mov     edx, r14d
0x14006548c  mov     rcx, rdi
0x14006548f  call    _guard_dispatch_icall
0x140065494  mov     r15, [rsp+108h+arg_0]
0x14006549c  mov     sil, [rsp+108h+var_C8]
0x1400654a1  mov     r12b, [rsp+108h+var_C7]
0x1400654a6  jmp     loc_1400657BC
0x1400654ab  mov     r10, [rsp+108h+arg_0]
0x1400654b3  lea     r15, [r10+1E0h]
0x1400654ba  test    r15, r15
0x1400654bd  jz      loc_1400657AE
0x1400654c3  cmp     ebx, [r15+4]
0x1400654c7  ja      loc_140065684
0x1400654cd  jnz     short loc_1400654D8
0x1400654cf  cmp     r12d, [r15]
0x1400654d2  jnb     loc_140065684
0x1400654d8  mov     al, 1
0x1400654da  test    al, al
0x1400654dc  jz      loc_140065684
0x1400654e2  cmp     ebx, edx
0x1400654e4  ja      loc_1400656CE
0x1400654ea  jnz     short loc_1400654F5
0x1400654ec  cmp     r12d, ecx
0x1400654ef  jnb     loc_1400656CE
0x1400654f5  lea     rdx, [rsp+108h+var_A8]; union _CLS_LSN *
0x1400654fa  mov     rcx, r10; this
0x1400654fd  call    ?LsnToCacheOffset@CClfsLogFcbPhysical@@AEAA_KAEBT_CLS_LSN@@@Z; CClfsLogFcbPhysical::LsnToCacheOffset(_CLS_LSN const &)
0x140065502  mov     rdi, rax
0x140065505  lea     rdx, [rsp+108h+var_80]; union _CLS_LSN *
0x14006550d  mov     rcx, [rsp+108h+arg_0]; this
0x140065515  call    ?LsnToCacheOffset@CClfsLogFcbPhysical@@AEAA_KAEBT_CLS_LSN@@@Z; CClfsLogFcbPhysical::LsnToCacheOffset(_CLS_LSN const &)
0x14006551a  mov     rbx, rax
0x14006551d  sub     rbx, rdi
0x140065520  mov     [rsp+108h+var_48], rbx
0x140065528  mov     edi, ebx
0x14006552a  mov     r8d, ebx; Size
0x14006552d  xor     edx, edx; Val
0x14006552f  mov     rcx, r13; void *
0x140065532  call    memset
0x140065537  mov     qword ptr [rsp+108h+var_A8], rsi
0x14006553c  mov     esi, dword ptr [rsp+108h+var_88]
0x140065543  add     esi, ebx
0x140065545  mov     dword ptr [rsp+108h+var_88], esi
0x14006554c  add     r13, rdi
0x14006554f  mov     [rsp+108h+var_78], r13
0x140065557  mov     r12, qword ptr [rsp+108h+arg_28]
0x14006555f  add     [r12], ebx
0x140065563  mov     rdi, [rsp+108h+arg_20]
0x14006556b  mov     rax, [rdi]
0x14006556e  mov     rax, [rax+58h]
0x140065572  mov     r8d, ebx
0x140065575  xor     edx, edx
0x140065577  mov     rcx, rdi
0x14006557a  call    _guard_dispatch_icall
0x14006557f  mov     r10, [rsp+108h+arg_0]
0x140065587  mov     rax, qword ptr [rsp+108h+var_A8]
0x14006558c  mov     qword ptr [rsp+108h+arg_28], rax
0x140065594  mov     rcx, rax
0x140065597  mov     r8d, [r12]
0x14006559b  mov     edx, dword ptr [rsp+108h+Size]
0x1400655a2  cmp     r8d, edx
0x1400655a5  jnb     loc_140065494
0x1400655ab  test    r15, r15
0x1400655ae  jz      loc_1400657B5
0x1400655b4  shr     rcx, 20h
0x1400655b8  cmp     ecx, [r15+4]
0x1400655bc  ja      loc_140065494
0x1400655c2  jnz     short loc_1400655CD
0x1400655c4  cmp     eax, [r15]
0x1400655c7  jnb     loc_140065494
0x1400655cd  mov     al, 1
0x1400655cf  mov     edx, dword ptr [rsp+108h+Size]
0x1400655d6  test    al, al
0x1400655d8  jz      loc_140065494
0x1400655de  mov     r9d, edx
0x1400655e1  sub     r9d, r8d
0x1400655e4  shr     r9d, 9; unsigned int
0x1400655e8  lea     rax, [rsp+108h+arg_10]
0x1400655f0  mov     [rsp+108h+var_D0], rax; unsigned int *
0x1400655f5  lea     rax, [rsp+108h+var_70]
0x1400655fd  mov     [rsp+108h+var_D8], rax; union _CLS_LSN *
0x140065602  mov     qword ptr [rsp+108h+Priority], rdi; struct IClfsRequestAsync *
0x140065607  mov     [rsp+108h+BugCheckOnFailure], 1; unsigned int
0x14006560f  lea     r8, [rsp+108h+MemoryDescriptorList]; struct _CLFS_READ_BUFFER *
0x140065614  lea     rdx, [rsp+108h+arg_28]; union _CLS_LSN *
0x14006561c  mov     rcx, r10; this
0x14006561f  call    ?ReadLog@CClfsLogFcbPhysical@@AEAAJAEBT_CLS_LSN@@AEBU_CLFS_READ_BUFFER@@KKPEAUIClfsRequestAsync@@AEAT2@AEAK@Z; CClfsLogFcbPhysical::ReadLog(_CLS_LSN const &,_CLFS_READ_BUFFER const &,ulong,ulong,IClfsRequestAsync *,_CLS_LSN &,ulong &)
0x140065624  mov     r14d, eax
0x140065627  mov     [rsp+108h+var_B8], eax
0x14006562b  mov     r8d, [rsp+108h+arg_10]
0x140065633  add     [r12], r8d
0x140065637  add     esi, r8d
0x14006563a  mov     dword ptr [rsp+108h+var_88], esi
0x140065641  add     r13, r8
0x140065644  mov     [rsp+108h+var_78], r13
0x14006564c  mov     rax, [rdi]
0x14006564f  mov     rax, [rax+58h]
0x140065653  mov     edx, r14d
0x140065656  mov     rcx, rdi
0x140065659  call    _guard_dispatch_icall
0x14006565e  test    r14d, r14d
  ... truncated ...
```
