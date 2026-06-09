# CClfsLogFcbPhysical::CompleteAsyncReadBlock(_CLS_LSN const &,ulong,void *,ulong,unsigned __int64 &,_CLS_LSN &)

- ea: `0x140066640`
- end: `0x140066cb2`
- name: `?CompleteAsyncReadBlock@CClfsLogFcbPhysical@@UEAAJAEBT_CLS_LSN@@KPEAXKAEA_KAEAT2@@Z`
- size: `1650`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, const union _CLS_LSN *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int, unsigned __int64 *, union _CLS_LSN *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140005f00`
- `0x14000a610`
- `0x14000ae40`
- `0x140017f20`
- `0x140066640`
- `0x140066cc0`
- `0x140066e90`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400666fe`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140066847`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400666fe`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140066847`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140066686`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140066686`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::CompleteAsyncReadBlock(
        CClfsLogFcbPhysical *this,
        const union _CLS_LSN *a2,
        int a3,
        char *a4,
        unsigned int a5,
        unsigned __int64 *a6,
        union _CLS_LSN *a7)
{
  char *v9; // r14
  unsigned __int64 v10; // rcx
  ULONGLONG ullOffset; // rax
  int v13; // esi
  int v14; // r11d
  unsigned int v15; // ebx
  unsigned int v16; // r9d
  __int64 v17; // r10
  unsigned int v18; // eax
  unsigned __int64 v19; // r8
  __int64 v20; // r12
  union _CLS_LSN *v21; // rdi
  _QWORD *v22; // rsi
  char *v23; // rdi
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // r14
  __int64 v26; // r15
  _DWORD *v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // r9
  unsigned __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int64 v36; // r8
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // rtt
  unsigned __int64 v39; // r8
  char ullOffset_high; // al
  int v41; // ecx
  int v42; // r15d
  char v43; // al
  CClfsLogFcbPhysical *v44; // rcx
  CLFS_LSN v45; // rbx
  const CLFS_LSN *v46; // rcx
  unsigned int v47; // r14d
  unsigned __int64 v48; // r12
  __int128 v49; // rax
  unsigned __int64 v50; // r8
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rdx
  CLFS_RECORD_INDEX idxRecord; // r14d
  union _CLS_LSN v54; // rax
  unsigned __int64 v55; // rcx
  union _CLS_LSN *v56; // rdx
  unsigned __int64 *v57; // rcx
  union _CLS_LSN *v58; // rdx
  signed __int32 v59; // ett
  unsigned int v60; // [rsp+34h] [rbp-4Dh]
  union _CLS_LSN v61; // [rsp+58h] [rbp-29h] BYREF
  char v62; // [rsp+60h] [rbp-21h] BYREF
  union _CLS_LSN v63; // [rsp+68h] [rbp-19h] BYREF
  union _CLS_LSN v64; // [rsp+70h] [rbp-11h] BYREF
  int v65; // [rsp+D0h] [rbp+4Fh] BYREF
  unsigned int v66; // [rsp+D8h] [rbp+57h] BYREF
  int v67; // [rsp+E0h] [rbp+5Fh]
  char *v68; // [rsp+E8h] [rbp+67h]

  v68 = a4;
  v67 = a3;
  v9 = a4;
  v66 = 0;
  *a7 = CLFS_LSN_INVALID;
  ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
  v10 = *(_QWORD *)(*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, int *))(*(_QWORD *)this + 352LL))(this, &v65);
  if ( HIDWORD(v10) == -1 )
    ullOffset = CLFS_LSN_INVALID.ullOffset;
  else
    ullOffset = (unsigned int)v10 & 0xFFFFFE00 | (HIDWORD(v10) << 32);
  if ( a2 && a2->ullOffset < ullOffset )
  {
    ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
    return 3222929427LL;
  }
  v13 = 0;
  LODWORD(v20) = 0;
  v65 = 0;
  ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
  v21 = a7;
  *a7 = *a2;
  v61 = *a2;
  while ( (unsigned int)v20 < *a6 - 40 )
  {
    v22 = (_QWORD *)((char *)this + 488);
    v23 = &v9[(unsigned int)v20];
    if ( this == (CClfsLogFcbPhysical *)-488LL || (v24 = CLFS_LSN_INVALID.ullOffset, CLFS_LSN_INVALID.ullOffset != *v22) )
    {
      CClfsLogFcbPhysical::ValidateContainerSize(this);
      v24 = CLFS_LSN_INVALID.ullOffset;
    }
    v25 = (unsigned __int64)*((unsigned __int16 *)v23 + 2) << 9;
    if ( !is_mul_ok(*((unsigned __int16 *)v23 + 2), 0x200u) )
      goto LABEL_44;
    v26 = *((_QWORD *)this + 10);
    v27 = v23 + 24;
    if ( v23 == (char *)-24LL || v24 != *(_QWORD *)v27 )
    {
      if ( !CClfsLogFcbPhysical::ValidateContainerSize(this)
        || (v23 == (char *)-24LL
          ? (v28 = 0xFFFFFFFFLL, v29 = 0xFFFFFFFFLL)
          : (v28 = *((unsigned int *)v23 + 7), v29 = *v27 & 0xFFFFFE00),
            v30 = *((_QWORD *)this + 87),
            v31 = (v25 + v30 * v28 + v29) % v30,
            v32 = (v25 + v30 * v28 + v29) / v30,
            HIDWORD(v32)) )
      {
        v24 = CLFS_LSN_INVALID.ullOffset;
      }
      else
      {
        v24 = CLFS_LSN_INVALID.ullOffset;
        if ( !HIDWORD(v31) && (_DWORD)v32 != -1 && (v31 & 0x1FF) == 0 )
        {
          v33 = (unsigned int)v31 | ((unsigned __int64)(unsigned int)v32 << 32);
          goto LABEL_32;
        }
      }
    }
    v33 = v24;
LABEL_32:
    if ( this != (CClfsLogFcbPhysical *)-488LL && v24 == *v22 )
    {
      *(_WORD *)((char *)&v60 + 1) = *(_WORD *)((char *)&CLFS_LSN_INVALID.ullOffset + 5);
      ullOffset_high = HIBYTE(CLFS_LSN_INVALID.ullOffset);
      LOBYTE(v60) = -1;
    }
    else if ( !CClfsLogFcbPhysical::ValidateContainerSize(this)
           || (this == (CClfsLogFcbPhysical *)-488LL
             ? (v34 = 0xFFFFFFFFLL, v35 = 0xFFFFFFFFLL)
             : (v34 = *((unsigned int *)this + 123), v35 = *(_DWORD *)v22 & 0xFFFFFE00),
               (v36 = *((_QWORD *)this + 87), v38 = v26 + v36 * v34 + v35,
                                              v37 = v38 % v36,
                                              v39 = v38 / v36,
                                              HIDWORD(v39))
            || HIDWORD(v37)) )
    {
      LODWORD(v24) = CLFS_LSN_INVALID.offset.idxRecord;
      *(_WORD *)((char *)&v60 + 1) = *(_WORD *)((char *)&CLFS_LSN_INVALID.ullOffset + 5);
      ullOffset_high = HIBYTE(CLFS_LSN_INVALID.ullOffset);
      LOBYTE(v60) = -1;
    }
    else
    {
      if ( (_DWORD)v39 == -1 || (v37 & 0x1FF) != 0 )
        v24 = CLFS_LSN_INVALID.ullOffset;
      else
        v24 = (unsigned int)v37 | ((unsigned __int64)(unsigned int)v39 << 32);
      LOBYTE(v60) = BYTE4(v24);
      *(_WORD *)((char *)&v60 + 1) = HIDWORD(v24) >> 8;
      ullOffset_high = HIBYTE(v24);
    }
    HIBYTE(v60) = ullOffset_high;
    if ( __PAIR64__(v60, v24) < v33 )
      goto LABEL_44;
    v13 = ClfsValidateBlock(&v61, (struct _CLFS_LOG_BLOCK_HEADER *)v23, a5 - (unsigned int)v20 - 40, v23[2], 4, &v66);
    if ( v13 < 0 )
      goto LABEL_13;
    v14 = *((_DWORD *)v23 + 3);
    v15 = *((unsigned __int16 *)v23 + 2);
    if ( !v14 )
    {
LABEL_12:
      v13 = ClfsDecodeBlockPrivate((struct _CLFS_LOG_BLOCK_HEADER *)v23, v15, v23[2], 4u, &v66);
      goto LABEL_13;
    }
    if ( v14 == -1 )
    {
LABEL_44:
      v13 = -1072037878;
      goto LABEL_13;
    }
    *((_DWORD *)v23 + 3) = 0;
    v16 = v15 << 9;
    v17 = 0;
    v18 = -1;
    if ( v15 << 9 )
    {
      do
      {
        v19 = (unsigned __int8)v23[v17];
        v17 = (unsigned int)(v17 + 1);
        v18 = *((_DWORD *)&CCrc32::m_rgCrcTable + ((unsigned __int8)v18 ^ v19)) ^ (v18 >> 8);
        --v16;
      }
      while ( v16 );
      LODWORD(v20) = v65;
      if ( v14 == ~v18 )
        goto LABEL_12;
    }
    *((_DWORD *)v23 + 3) = v14;
    v13 = -1072037878;
LABEL_13:
    if ( v13 < 0 )
    {
      if ( !(_DWORD)v20 )
        return (unsigned int)v13;
      v21 = a7;
      v13 = 0;
      v9 = v68;
      break;
    }
    v41 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
    if ( v41 )
      v42 = -v41 & (v41 + (*((unsigned __int16 *)v23 + 2) << 9) - 1);
    else
      v42 = 0;
    v43 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this);
    v44 = this;
    if ( !v43 )
    {
      v21 = a7;
      v56 = (union _CLS_LSN *)&v62;
      goto LABEL_58;
    }
    if ( (*(unsigned __int8 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this) )
    {
      v45 = CLFS_LSN_INVALID;
      v46 = (const CLFS_LSN *)(v23 + 24);
      if ( v23 == (char *)-24LL )
      {
        v47 = -1;
LABEL_52:
        v48 = *((_QWORD *)this + 87);
        v49 = (__int64)(v48 * v47 + ClfsLsnBlockOffset(v46));
        v50 = ((DWORD2(v49) & 0x7FFFF) + (_QWORD)v49) & 0xFFFFFFFFFFF80000uLL;
        v51 = (v50 + 520192) / v48;
        if ( (_DWORD)v51 != -1 )
        {
          v52 = (v50 + 520192) % v48;
          if ( (v52 & 0x1FF) == 0 )
            v45.ullOffset = __PAIR64__(v51, v52);
        }
        LODWORD(v20) = v65;
        idxRecord = v45.offset.idxRecord;
        goto LABEL_56;
      }
      if ( CLFS_LSN_INVALID.ullOffset != v46->ullOffset )
      {
        v47 = *((_DWORD *)v23 + 7);
        goto LABEL_52;
      }
    }
    idxRecord = 0;
    v45.offset.cidContainer = -1;
LABEL_56:
    v54 = CClfsLogFcbPhysical::AddLsnOffset(this, &v63, (int)v23 + 24);
    v21 = a7;
    v55 = *(_QWORD *)v54.ullOffset;
    *a7 = *(union _CLS_LSN *)v54.ullOffset;
    if ( __PAIR64__(v45.offset.cidContainer, idxRecord) > v55 )
      goto LABEL_59;
    v56 = &v64;
    v44 = this;
LABEL_58:
    *v21 = **(union _CLS_LSN **)&CClfsLogFcbPhysical::AddLsnOffset(v44, v56, (unsigned int)v21);
LABEL_59:
    v9 = v68;
    v20 = (unsigned int)(v42 + v20);
    v65 = v20;
    v61 = *(union _CLS_LSN *)&v68[v20 + 24];
    if ( (v67 & 1) != 0 )
      break;
  }
  v57 = a6;
  v58 = (union _CLS_LSN *)&v9[a5];
  v58[-4] = *v21;
  *v57 = (unsigned int)v20;
  _m_prefetchw(&v58[-2]);
  do
    v59 = v58[-2].offset.idxRecord;
  while ( v59 != _InterlockedCompareExchange((volatile signed __int32 *)&v58[-2], v59 & 0xFFFFFF7F, v59) );
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140066640  mov     [rsp-8+arg_18], r9
0x140066645  mov     [rsp-8+arg_10], r8d
0x14006664a  push    rbp
0x14006664b  push    rbx
0x14006664c  push    rdi
0x14006664d  push    r13
0x14006664f  push    r14
0x140066651  push    r15
0x140066653  lea     rbp, [rsp-17h]
0x140066658  sub     rsp, 98h
0x14006665f  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140066666  mov     r13, rcx
0x140066669  mov     rcx, [rbp+3Fh+arg_30]
0x14006666d  mov     rbx, rdx
0x140066670  xor     r15d, r15d
0x140066673  mov     dl, 1; Wait
0x140066675  mov     r14, r9
0x140066678  mov     [rbp+3Fh+arg_8], r15d
0x14006667c  mov     [rcx], rax
0x14006667f  lea     rcx, [r13+0C8h]; Resource
0x140066686  call    cs:__imp_ExAcquireResourceSharedLite
0x14006668d  nop     dword ptr [rax+rax+00h]
0x140066692  mov     rax, [r13+0]
0x140066696  lea     rdx, [rbp+3Fh+arg_0]
0x14006669a  mov     rcx, r13
0x14006669d  mov     rax, [rax+160h]
0x1400666a4  call    _guard_dispatch_icall
0x1400666a9  mov     edx, 0FFFFFE00h
0x1400666ae  mov     rcx, [rax]
0x1400666b1  mov     rax, rcx
0x1400666b4  shr     rax, 20h
0x1400666b8  cmp     eax, 0FFFFFFFFh
0x1400666bb  jz      loc_140066C41
0x1400666c1  shl     rax, 20h
0x1400666c5  and     rcx, rdx
0x1400666c8  or      rax, rcx
0x1400666cb  test    rbx, rbx
0x1400666ce  jz      loc_14006681D
0x1400666d4  mov     rcx, rax
0x1400666d7  shr     rcx, 20h
0x1400666db  cmp     [rbx+4], ecx
0x1400666de  ja      loc_14006681D
0x1400666e4  jnz     short loc_1400666EE
0x1400666e6  cmp     [rbx], eax
0x1400666e8  jnb     loc_14006681D
0x1400666ee  mov     rdx, gs:188h; ResourceThreadId
0x1400666f7  lea     rcx, [r13+0C8h]; Resource
0x1400666fe  call    cs:__imp_ExReleaseResourceForThreadLite
0x140066705  nop     dword ptr [rax+rax+00h]
0x14006670a  mov     eax, 0C01A0013h
0x14006670f  add     rsp, 98h
0x140066716  pop     r15
0x140066718  pop     r14
0x14006671a  pop     r13
0x14006671c  pop     rdi
0x14006671d  pop     rbx
0x14006671e  pop     rbp
0x14006671f  retn
0x140066721  mov     r8d, [rbp+3Fh+arg_20]
0x140066725  lea     rax, [rbp+3Fh+arg_8]
0x140066729  movzx   r9d, byte ptr [rdi+2]; unsigned __int8
0x14006672e  lea     rcx, [rbp+3Fh+var_68]; union _CLS_LSN *
0x140066732  sub     r8d, r12d
0x140066735  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x14006673a  sub     r8d, 28h ; '('; unsigned int
0x14006673e  mov     byte ptr [rsp+0C0h+var_A0], 4; char
0x140066743  mov     rdx, rdi; struct _CLFS_LOG_BLOCK_HEADER *
0x140066746  call    ?ClfsValidateBlock@@YAJAEBT_CLS_LSN@@PEAU_CLFS_LOG_BLOCK_HEADER@@KEEAEAK@Z; ClfsValidateBlock(_CLS_LSN const &,_CLFS_LOG_BLOCK_HEADER *,ulong,uchar,uchar,ulong &)
0x14006674b  mov     esi, eax
0x14006674d  test    eax, eax
0x14006674f  js      loc_1400667E8
0x140066755  mov     r11d, [rdi+0Ch]
0x140066759  movzx   ebx, word ptr [rdi+4]
0x14006675d  test    r11d, r11d
0x140066760  jz      short loc_1400667CB
0x140066762  cmp     r11d, 0FFFFFFFFh
0x140066766  jz      loc_140066A21
0x14006676c  mov     r9d, ebx
0x14006676f  mov     dword ptr [rdi+0Ch], 0
0x140066776  shl     r9d, 9
0x14006677a  xor     r10d, r10d
0x14006677d  mov     eax, 0FFFFFFFFh
0x140066782  test    r9d, r9d
0x140066785  jz      loc_140066BED
0x14006678b  lea     r12, ?m_rgCrcTable@CCrc32@@0PAKA; ulong near * CCrc32::m_rgCrcTable
0x140066792  nop     dword ptr [rax+00h]
0x140066796  nop     word ptr [rax+rax+00000000h]
0x1400667a0  movzx   r8d, byte ptr [r10+rdi]
0x1400667a5  lea     r10d, [r10+1]
0x1400667a9  movzx   edx, al
0x1400667ac  xor     r8, rdx
0x1400667af  shr     eax, 8
0x1400667b2  xor     eax, [r12+r8*4]
0x1400667b6  add     r9d, 0FFFFFFFFh
0x1400667ba  jnz     short loc_1400667A0
0x1400667bc  mov     r12d, [rbp+3Fh+arg_0]
0x1400667c0  not     eax
0x1400667c2  cmp     r11d, eax
0x1400667c5  jnz     loc_140066BED
0x1400667cb  movzx   r8d, byte ptr [rdi+2]; unsigned __int8
0x1400667d0  lea     rax, [rbp+3Fh+arg_8]
0x1400667d4  mov     r9b, 4; unsigned __int8
0x1400667d7  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x1400667dc  mov     edx, ebx; unsigned int
0x1400667de  mov     rcx, rdi; struct _CLFS_LOG_BLOCK_HEADER *
0x1400667e1  call    ?ClfsDecodeBlockPrivate@@YAJPEAU_CLFS_LOG_BLOCK_HEADER@@KEEAEAK@Z; ClfsDecodeBlockPrivate(_CLFS_LOG_BLOCK_HEADER *,ulong,uchar,uchar,ulong &)
0x1400667e6  mov     esi, eax
0x1400667e8  test    esi, esi
0x1400667ea  jns     loc_140066A2B
0x1400667f0  test    r12d, r12d
0x1400667f3  jnz     loc_140066CA3
0x1400667f9  mov     r12, [rsp+0C0h+var_38]
0x140066801  mov     eax, esi
0x140066803  mov     rsi, [rsp+0C0h+var_30]
0x14006680b  add     rsp, 98h
0x140066812  pop     r15
0x140066814  pop     r14
0x140066816  pop     r13
0x140066818  pop     rdi
0x140066819  pop     rbx
0x14006681a  pop     rbp
0x14006681b  retn
0x14006681d  mov     [rsp+0C0h+var_30], rsi
0x140066825  lea     rcx, [r13+0C8h]; Resource
0x14006682c  mov     edx, 188h
0x140066831  mov     [rsp+0C0h+var_38], r12
0x140066839  mov     esi, r15d
0x14006683c  mov     r12d, r15d
0x14006683f  mov     rdx, gs:[rdx]; ResourceThreadId
0x140066843  mov     [rbp+3Fh+arg_0], r15d
0x140066847  call    cs:__imp_ExReleaseResourceForThreadLite
0x14006684e  nop     dword ptr [rax+rax+00h]
0x140066853  mov     rax, [rbx]
0x140066856  mov     rdi, [rbp+3Fh+arg_30]
0x14006685a  mov     [rdi], rax
0x14006685d  mov     rax, [rbx]
0x140066860  mov     qword ptr [rbp+3Fh+var_68], rax
0x140066864  mov     rax, [rbp+3Fh+arg_28]
0x140066868  mov     ecx, r12d
0x14006686b  mov     rax, [rax]
0x14006686e  sub     rax, 28h ; '('
0x140066872  cmp     rcx, rax
0x140066875  jnb     loc_140066B8B
0x14006687b  lea     rsi, [r13+1E8h]
0x140066882  lea     rdi, [rcx+r14]
0x140066886  test    rsi, rsi
0x140066889  jz      short loc_140066897
0x14006688b  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x140066892  cmp     r8, [rsi]
0x140066895  jz      short loc_1400668A6
0x140066897  mov     rcx, r13; this
0x14006689a  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x14006689f  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x1400668a6  movzx   ecx, word ptr [rdi+4]
0x1400668aa  mov     eax, 200h
0x1400668af  mul     rcx
0x1400668b2  mov     [rbp+3Fh+var_78], r15
0x1400668b6  mov     r14, rax
0x1400668b9  test    rdx, rdx
0x1400668bc  jnz     loc_140066A21
0x1400668c2  mov     r15, [r13+50h]
0x1400668c6  lea     rbx, [rdi+18h]
0x1400668ca  test    rbx, rbx
0x1400668cd  jz      short loc_1400668D8
0x1400668cf  cmp     r8, [rbx]
0x1400668d2  jz      loc_140066BC3
0x1400668d8  mov     rcx, r13; this
0x1400668db  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x1400668e0  test    al, al
0x1400668e2  jz      loc_140066BBC
0x1400668e8  test    rbx, rbx
0x1400668eb  jz      loc_140066C6A
0x1400668f1  mov     eax, [rbx]
0x1400668f3  mov     edx, 0FFFFFE00h
0x1400668f8  mov     ecx, [rbx+4]
0x1400668fb  and     eax, edx
0x1400668fd  mov     r8, [r13+2B8h]
0x140066904  xor     edx, edx
0x140066906  imul    rcx, r8
0x14006690a  add     rcx, r14
0x14006690d  add     rax, rcx
0x140066910  div     r8
0x140066913  mov     rcx, rax
0x140066916  mov     r9, rax
0x140066919  shr     rcx, 20h
0x14006691d  test    ecx, ecx
0x14006691f  jnz     loc_140066BBC
0x140066925  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x14006692c  mov     rax, rdx
0x14006692f  shr     rax, 20h
0x140066933  test    eax, eax
0x140066935  jnz     loc_140066BC3
0x14006693b  cmp     r9d, 0FFFFFFFFh
0x14006693f  jz      loc_140066BC3
0x140066945  test    edx, 1FFh
0x14006694b  jnz     loc_140066BC3
0x140066951  mov     ebx, r9d
0x140066954  shl     rbx, 20h
0x140066958  mov     eax, edx
0x14006695a  or      rbx, rax
0x14006695d  mov     [rbp+3Fh+var_88], rbx
0x140066961  test    rsi, rsi
0x140066964  jz      short loc_14006696F
0x140066966  cmp     r8, [rsi]
0x140066969  jz      loc_140066C12
0x14006696f  mov     rcx, r13; this
0x140066972  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x140066977  test    al, al
0x140066979  jz      loc_140066BCB
0x14006697f  test    rsi, rsi
0x140066982  jz      loc_140066C79
0x140066988  mov     eax, [rsi]
0x14006698a  mov     edx, 0FFFFFE00h
0x14006698f  mov     ecx, [rsi+4]
0x140066992  and     eax, edx
0x140066994  mov     r8, [r13+2B8h]
0x14006699b  xor     edx, edx
0x14006699d  imul    rcx, r8
0x1400669a1  add     rcx, r15
0x1400669a4  add     rax, rcx
0x1400669a7  div     r8
0x1400669aa  mov     rcx, rax
0x1400669ad  mov     r8, rax
0x1400669b0  shr     rcx, 20h
0x1400669b4  test    ecx, ecx
0x1400669b6  jnz     loc_140066BCB
0x1400669bc  mov     rax, rdx
0x1400669bf  shr     rax, 20h
0x1400669c3  test    eax, eax
0x1400669c5  jnz     loc_140066BCB
0x1400669cb  cmp     r8d, 0FFFFFFFFh
0x1400669cf  jz      loc_140066C4D
0x1400669d5  test    edx, 1FFh
0x1400669db  jnz     loc_140066C4D
0x1400669e1  mov     r8d, r8d
0x1400669e4  shl     r8, 20h
0x1400669e8  mov     eax, edx
0x1400669ea  or      r8, rax
0x1400669ed  mov     [rbp+3Fh+var_78], r8
0x1400669f1  mov     rax, r8
0x1400669f4  shr     rax, 20h
0x1400669f8  mov     byte ptr [rbp+3Fh+var_8C], al
0x1400669fb  movzx   eax, word ptr [rbp+3Fh+var_78+5]
0x1400669ff  mov     word ptr [rbp+3Fh+var_8C+1], ax
0x140066a03  movzx   eax, byte ptr [rbp+3Fh+var_78+7]
0x140066a07  mov     byte ptr [rbp+3Fh+var_8C+3], al
0x140066a0a  mov     eax, dword ptr [rbp+3Fh+var_88+4]
0x140066a0d  cmp     [rbp+3Fh+var_8C], eax
0x140066a10  ja      loc_140066721
0x140066a16  jnz     short loc_140066A21
0x140066a18  cmp     r8d, ebx
0x140066a1b  jnb     loc_140066721
0x140066a21  mov     esi, 0C01A000Ah
0x140066a26  jmp     loc_1400667E8
0x140066a2b  mov     rax, [r13+2C8h]
0x140066a32  mov     ecx, [rax+90h]
0x140066a38  test    ecx, ecx
0x140066a3a  jz      loc_140066C62
0x140066a40  movzx   r15d, word ptr [rdi+4]
0x140066a45  shl     r15d, 9
0x140066a49  dec     r15d
0x140066a4c  add     r15d, ecx
0x140066a4f  neg     ecx
0x140066a51  and     r15d, ecx
0x140066a54  mov     rax, [r13+0]
0x140066a58  mov     rcx, r13
0x140066a5b  mov     rax, [rax+138h]
0x140066a62  call    _guard_dispatch_icall
0x140066a67  mov     rcx, r13
0x140066a6a  test    al, al
0x140066a6c  jz      loc_140066C88
0x140066a72  mov     rax, [r13+0]
0x140066a76  mov     rax, [rax+138h]
0x140066a7d  call    _guard_dispatch_icall
0x140066a82  test    al, al
0x140066a84  jz      loc_140066BFB
0x140066a8a  mov     rbx, qword ptr cs:CLFS_LSN_INVALID
0x140066a91  lea     rcx, [rdi+18h]; plsn
0x140066a95  test    rcx, rcx
0x140066a98  jz      loc_140066C98
0x140066a9e  cmp     rbx, [rcx]
0x140066aa1  jz      loc_140066BFB
0x140066aa7  mov     r14d, [rcx+4]
0x140066aab  mov     r12, [r13+2B8h]
0x140066ab2  call    ClfsLsnBlockOffset
0x140066ab7  mov     eax, eax
0x140066ab9  mov     ecx, r14d
0x140066abc  imul    rcx, r12
0x140066ac0  add     rax, rcx
0x140066ac3  cqo
0x140066ac5  and     edx, 7FFFFh
0x140066acb  lea     r8, [rdx+rax]
0x140066acf  xor     edx, edx
0x140066ad1  and     r8, 0FFFFFFFFFFF80000h
0x140066ad8  lea     rax, [r8+7F000h]
0x140066adf  div     r12
0x140066ae2  mov     rcx, rax
0x140066ae5  cmp     eax, 0FFFFFFFFh
0x140066ae8  jz      loc_140066C59
0x140066aee  xor     edx, edx
  ... truncated ...
```
