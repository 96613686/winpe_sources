# CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong)

- ea: `0x1400572a0`
- end: `0x1400577b8`
- name: `?AppendWriteBlockToFlushQueue@CClfsKernelMarshallingContext@@AEAAJEK@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CClfsKernelMarshallingContext *__hidden this, unsigned __int8, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140034a38`
- `0x1400548c4`
- `0x140055ef0`
- `0x1400587cc`
- `0x14006e500`

## callees

- `0x14000bf48`
- `0x1400572a0`
- `0x1400577c0`
- `0x140057980`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400572e5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005743e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400572e5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005743e`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005775a`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005777b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007995f`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140079985`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005775a`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14005777b`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007995f`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140079985`
- `ntoskrnl!KeBugCheckEx` at `0x140057643`
- `ntoskrnl!KeBugCheckEx` at `0x14005771f`
- `ntoskrnl!KeBugCheckEx` at `0x140057643`
- `ntoskrnl!KeBugCheckEx` at `0x14005771f`

## pseudocode

```c
__int64 __fastcall CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(
        CClfsKernelMarshallingContext *this,
        __int64 a2,
        int a3)
{
  BOOLEAN v5; // r15
  BOOLEAN v6; // r13
  int v7; // r9d
  int v8; // r8d
  union _CLS_LSN v9; // rax
  __int64 v10; // rax
  ULONG_PTR v11; // rdi
  int v12; // r9d
  unsigned int v13; // ecx
  int v14; // edx
  int v15; // ecx
  unsigned int appended; // r14d
  __int64 v17; // rax
  _QWORD **v18; // rdi
  CClfsKernelMarshallingContext **v19; // rcx
  CClfsKernelMarshallingContext *v20; // rax
  _QWORD *v21; // rcx
  union _CLS_LSN *v22; // rcx
  CLFS_CONTAINER_ID cidContainer; // r12d
  union _CLS_LSN v24; // rax
  _QWORD *v25; // rsi
  union _CLS_LSN v26; // rcx
  _QWORD *v27; // r10
  ULONG_PTR v28; // r8
  _QWORD *v29; // r9
  _QWORD *v30; // r8
  _QWORD *v31; // rax
  void *v32; // rdx
  unsigned int v33; // r10d
  unsigned int v34; // edx
  char v36; // [rsp+60h] [rbp-68h]
  struct _IRP *v37; // [rsp+68h] [rbp-60h]
  union _CLS_LSN v38; // [rsp+80h] [rbp-48h] BYREF
  __int64 v39; // [rsp+D8h] [rbp+10h] BYREF
  union _CLS_LSN v40; // [rsp+E8h] [rbp+20h] BYREF

  v40 = CLFS_LSN_INVALID;
  v5 = 0;
  v6 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 17), 1u);
  if ( *((_BYTE *)this + 188) )
  {
    v32 = (void *)*((_QWORD *)this + 16);
    if ( v32 )
    {
      CClfsKernelMarshallingContext::DeallocateIocb(this, v32);
      *((_QWORD *)this + 16) = 0;
    }
    appended = -1072037845;
    if ( !*(&CClfsLogFcbCommon::m_infoGlobalError + 2) )
    {
      *(&CClfsLogFcbCommon::m_infoGlobalError + 2) = 21;
      *(&CClfsLogFcbCommon::m_infoGlobalError + 3) = -1072037845;
    }
    goto LABEL_30;
  }
  v7 = *((_DWORD *)this + 17);
  v8 = -v7;
  if ( v7 )
    v9.ullOffset = v8 & (unsigned int)(v7 + *((_DWORD *)this + 11) + 983);
  else
    v9.ullOffset = 0;
  v38 = v9;
  v10 = *((_QWORD *)this + 16);
  if ( *(_DWORD *)(v10 + 20) )
  {
    v11 = *(_QWORD *)(v10 + 8);
    v33 = *(_DWORD *)(v10 + 16);
    v34 = v33 / 0x1FE;
    if ( v33 != 510 * (v33 / 0x1FE) )
      ++v34;
    if ( v7 )
      v13 = v8 & (v7 + v33 + ((2 * v34 + 7) & 0xFFFFFFF8) - 1);
    else
      v13 = 0;
    v14 = (unsigned __int16)(v13 >> 9);
    *(_WORD *)(v11 + 6) = v14;
    *(_WORD *)(v11 + 4) = v14;
    *(_DWORD *)(v11 + 104) = v13 - ((2 * v14 + 7) & 0xFFFFFFF8);
    v15 = *((_DWORD *)this + 17);
    if ( v15 )
      v12 = -v15 & (v15 + (v14 << 9) - 1);
    else
      v12 = 0;
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
  appended = ClfsReserveAndAppendLogInternal(
               *((_QWORD *)this + 1),
               (unsigned int)*((_QWORD *)this + 16) + 160,
               v11,
               v12,
               (__int64 *)(*((_QWORD *)this + 16) + 32LL),
               (__int64 *)this + 10,
               (__int64 *)&v38,
               a3,
               (union _CLS_LSN *)(*((_QWORD *)this + 16) + 120LL),
               (__int64)&v39,
               (union _CLS_LSN *)(*((_QWORD *)this + 16) + 88LL),
               &v40,
               v36,
               v37);
  if ( (int)(appended + 0x80000000) >= 0 && appended != -1072037841 )
  {
    if ( appended == -1072037845 )
    {
      *((_BYTE *)this + 188) = 1;
      CClfsKernelMarshallingContext::DeallocateIocb(this, *((PVOID *)this + 16));
      *((_QWORD *)this + 16) = 0;
    }
LABEL_30:
    v26 = CLFS_LSN_INVALID;
    goto LABEL_56;
  }
  if ( (a3 & 2) != 0
    && v11
    && (*((_QWORD *)this + 16) == -112 || *(_QWORD *)(*((_QWORD *)this + 16) + 112LL) >= v40.ullOffset)
    && appended != -1072037841 )
  {
    KeBugCheckEx(0xC1F5u, 0x40u, v11, (ULONG_PTR)this, 0);
  }
  *((_QWORD *)this + 12) = *((_QWORD *)this + 11);
  v5 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 18), 1u);
  v17 = *((_QWORD *)this + 16);
  if ( *(_DWORD *)(v17 + 20) )
  {
    v18 = (_QWORD **)((char *)this + 152);
    v19 = (CClfsKernelMarshallingContext **)*((_QWORD *)this + 20);
    if ( *v19 != (CClfsKernelMarshallingContext *)((char *)this + 152) )
LABEL_55:
      __fastfail(3u);
    v20 = (CClfsKernelMarshallingContext *)(v17 + 136);
    *(_QWORD *)v20 = v18;
    *((_QWORD *)v20 + 1) = v19;
    *v19 = v20;
    *((_QWORD *)this + 20) = v20;
    _InterlockedIncrement((volatile signed __int32 *)this + 10);
    v21 = (_QWORD *)(*((_QWORD *)this + 16) + 88LL);
    if ( *((_QWORD *)this + 16) != -88
      && this != (CClfsKernelMarshallingContext *)-104LL
      && *v21 > *((_QWORD *)this + 13) )
    {
      *((_QWORD *)this + 13) = *v21;
    }
  }
  else
  {
    CClfsKernelMarshallingContext::DeallocateIocb(this, *((PVOID *)this + 16));
    v18 = (_QWORD **)((char *)this + 152);
  }
  *((_QWORD *)this + 16) = 0;
  v22 = (union _CLS_LSN *)((char *)this + 112);
  if ( this == (CClfsKernelMarshallingContext *)-112LL )
    goto LABEL_30;
  cidContainer = v40.offset.cidContainer;
  if ( v40.offset.cidContainer < *((_DWORD *)this + 29) )
    goto LABEL_30;
  v24 = v40;
  if ( v40.offset.cidContainer == *((_DWORD *)this + 29) && v40.offset.idxRecord <= v22->offset.idxRecord )
    goto LABEL_30;
  *v22 = v40;
  v25 = *v18;
  v26 = CLFS_LSN_INVALID;
  while ( v25 != v18 )
  {
    v27 = v25 - 17;
    v28 = *((_QWORD *)this + 16);
    if ( (_QWORD *)v28 == v25 - 17 )
      KeBugCheckEx(0xC1F5u, 0x41u, v28, (ULONG_PTR)(v25 - 17), (ULONG_PTR)this);
    v29 = v25;
    v30 = (_QWORD *)*v25;
    v25 = (_QWORD *)*v25;
    if ( v27[1] != -24 && *(_QWORD *)(v27[1] + 24LL) < __PAIR64__(cidContainer, v24.offset.idxRecord)
      || v26.ullOffset == v24.ullOffset )
    {
      if ( (_QWORD *)v30[1] != v29 )
        goto LABEL_55;
      v31 = (_QWORD *)v29[1];
      if ( (_QWORD *)*v31 != v29 )
        goto LABEL_55;
      *v31 = v30;
      v30[1] = v31;
      CClfsKernelMarshallingContext::DeallocateIocb(this, v27);
      _InterlockedDecrement((volatile signed __int32 *)this + 10);
      v24 = v40;
      cidContainer = v40.offset.cidContainer;
      v26 = CLFS_LSN_INVALID;
    }
  }
LABEL_56:
  if ( appended == -1072037848 || appended == -1072037845 )
  {
    v38 = v26;
    CClfsKernelMarshallingContext::ReleaseFlushElements(this, &v38);
  }
  if ( v5 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 18), (ERESOURCE_THREAD)KeGetCurrentThread());
  if ( v6 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 17), (ERESOURCE_THREAD)KeGetCurrentThread());
  return appended;
}

```

## disassembly

```asm
0x1400572a0  mov     r11, rsp
0x1400572a3  mov     [r11+8], rcx
0x1400572a7  push    rbx
0x1400572a8  push    rsi
0x1400572a9  push    rdi
0x1400572aa  push    r12
0x1400572ac  push    r13
0x1400572ae  push    r14
0x1400572b0  push    r15
0x1400572b2  sub     rsp, 90h
0x1400572b9  mov     esi, r8d
0x1400572bc  mov     rbx, rcx
0x1400572bf  xor     r12d, r12d
0x1400572c2  mov     [r11-54h], r12d
0x1400572c6  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400572cd  mov     [r11+20h], rax
0x1400572d1  mov     [r11-57h], r12b
0x1400572d5  xor     r15b, r15b
0x1400572d8  mov     [r11-58h], r15b
0x1400572dc  mov     dl, 1; Wait
0x1400572de  mov     rcx, [rcx+88h]; Resource
0x1400572e5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400572ec  nop     dword ptr [rax+rax+00h]
0x1400572f1  movzx   r13d, al
0x1400572f5  mov     [rsp+0C8h+var_57], al
0x1400572f9  cmp     [rbx+0BCh], r15b
0x140057300  jnz     loc_14005768C
0x140057306  mov     r9d, [rbx+44h]
0x14005730a  mov     r8d, r9d
0x14005730d  neg     r8d
0x140057310  test    r9d, r9d
0x140057313  jz      loc_140057684
0x140057319  mov     eax, [rbx+2Ch]
0x14005731c  add     eax, 3D7h
0x140057321  add     eax, r9d
0x140057324  and     eax, r8d
0x140057327  mov     qword ptr [rsp+0C8h+var_48], rax
0x14005732f  mov     rax, [rbx+80h]
0x140057336  cmp     dword ptr [rax+14h], 0
0x14005733a  jnz     loc_1400576D7
0x140057340  mov     rdi, r12
0x140057343  mov     r9d, r12d
0x140057346  jmp     short loc_1400573A4
0x140057348  test    r9d, r9d
0x14005734b  jz      loc_140057674
0x140057351  lea     rcx, ds:7[rdx*2]
0x140057359  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14005735d  dec     ecx
0x14005735f  add     ecx, r10d
0x140057362  add     ecx, r9d
0x140057365  and     ecx, r8d
0x140057368  mov     eax, ecx
0x14005736a  shr     eax, 9
0x14005736d  movzx   edx, ax
0x140057370  mov     [rdi+6], dx
0x140057374  mov     [rdi+4], dx
0x140057378  lea     eax, ds:7[rdx*2]
0x14005737f  and     eax, 0FFFFFFF8h
0x140057382  sub     ecx, eax
0x140057384  mov     [rdi+68h], ecx
0x140057387  mov     ecx, [rbx+44h]
0x14005738a  test    ecx, ecx
0x14005738c  jz      loc_14005767C
0x140057392  mov     r9d, edx
0x140057395  shl     r9d, 9
0x140057399  dec     r9d
0x14005739c  add     r9d, ecx
0x14005739f  neg     ecx
0x1400573a1  and     r9d, ecx; int
0x1400573a4  mov     rdx, [rbx+80h]
0x1400573ab  lea     rax, [rdx+58h]
0x1400573af  lea     rcx, [rdx+78h]
0x1400573b3  lea     r8, [rbx+50h]
0x1400573b7  lea     r10, [rdx+20h]
0x1400573bb  add     rdx, 0A0h; int
0x1400573c2  lea     r11, [rsp+0C8h+arg_18]
0x1400573ca  mov     [rsp+0C8h+var_70], r11; union _CLS_LSN *
0x1400573cf  mov     [rsp+0C8h+var_78], rax; union _CLS_LSN *
0x1400573d4  lea     rax, [rsp+0C8h+arg_8]
0x1400573dc  mov     [rsp+0C8h+var_80], rax; __int64
0x1400573e1  mov     [rsp+0C8h+var_88], rcx; union _CLS_LSN *
0x1400573e6  mov     [rsp+0C8h+var_90], esi; int
0x1400573ea  lea     rax, [rsp+0C8h+var_48]
0x1400573f2  mov     [rsp+0C8h+var_98], rax; __int64 *
0x1400573f7  mov     [rsp+0C8h+var_A0], r8; __int64 *
0x1400573fc  mov     [rsp+0C8h+BugCheckParameter4], r10; __int64 *
0x140057401  mov     r8, rdi; int
0x140057404  mov     rcx, [rbx+8]; int
0x140057408  call    ClfsReserveAndAppendLogInternal
0x14005740d  mov     r14d, eax
0x140057410  mov     [rsp+0C8h+var_54], eax
0x140057414  mov     ecx, 80000000h
0x140057419  add     eax, ecx
0x14005741b  test    ecx, eax
0x14005741d  jz      loc_1400575AB
0x140057423  test    sil, 2
0x140057427  jnz     loc_1400575EA
0x14005742d  mov     rax, [rbx+58h]
0x140057431  mov     [rbx+60h], rax
0x140057435  mov     dl, 1; Wait
0x140057437  mov     rcx, [rbx+90h]; Resource
0x14005743e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140057445  nop     dword ptr [rax+rax+00h]
0x14005744a  movzx   r15d, al
0x14005744e  mov     [rsp+0C8h+var_58], al
0x140057452  mov     rax, [rbx+80h]
0x140057459  cmp     dword ptr [rax+14h], 0
0x14005745d  jz      loc_14005765D
0x140057463  lea     rdi, [rbx+98h]
0x14005746a  mov     rcx, [rdi+8]
0x14005746e  cmp     [rcx], rdi
0x140057471  jnz     loc_14005772C
0x140057477  add     rax, 88h
0x14005747d  mov     [rax], rdi
0x140057480  mov     [rax+8], rcx
0x140057484  mov     [rcx], rax
0x140057487  mov     [rdi+8], rax
0x14005748b  lock inc dword ptr [rbx+28h]
0x14005748f  mov     rcx, [rbx+80h]
0x140057496  add     rcx, 58h ; 'X'
0x14005749a  jnz     loc_1400575BA
0x1400574a0  mov     [rbx+80h], r12
0x1400574a7  lea     rcx, [rbx+70h]
0x1400574ab  test    rcx, rcx
0x1400574ae  jz      loc_14005759F
0x1400574b4  mov     r12d, dword ptr [rsp+0C8h+arg_18+4]
0x1400574bc  cmp     r12d, [rcx+4]
0x1400574c0  jb      loc_14005759F
0x1400574c6  mov     rax, qword ptr [rsp+0C8h+arg_18]
0x1400574ce  jnz     short loc_1400574D8
0x1400574d0  cmp     eax, [rcx]
0x1400574d2  jbe     loc_14005759F
0x1400574d8  mov     [rcx], rax
0x1400574db  mov     rsi, [rdi]
0x1400574de  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x1400574e5  cmp     rsi, rdi
0x1400574e8  jz      loc_1400575A6
0x1400574ee  lea     r10, [rsi-88h]
0x1400574f5  mov     r8, [rbx+80h]; BugCheckParameter2
0x1400574fc  cmp     r8, r10
0x1400574ff  jz      loc_14005770D
0x140057505  mov     r9, rsi
0x140057508  mov     r8, [rsi]
0x14005750b  mov     rsi, r8
0x14005750e  mov     rdx, [r10+8]
0x140057512  add     rdx, 18h
0x140057516  jz      loc_14005764F
0x14005751c  cmp     [rdx+4], r12d
0x140057520  ja      loc_14005764F
0x140057526  jnz     short loc_140057530
0x140057528  cmp     [rdx], eax
0x14005752a  jnb     loc_14005764F
0x140057530  cmp     [r8+8], r9
0x140057534  jnz     loc_14005772C
0x14005753a  mov     rax, [r9+8]
0x14005753e  cmp     [rax], r9
0x140057541  jnz     loc_14005772C
0x140057547  mov     [rax], r8
0x14005754a  mov     [r8+8], rax
0x14005754e  mov     rdx, r10; Entry
0x140057551  mov     rcx, rbx; this
0x140057554  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140057559  lock dec dword ptr [rbx+28h]
0x14005755d  mov     rax, qword ptr [rsp+0C8h+arg_18]
0x140057565  mov     r12d, dword ptr [rsp+0C8h+arg_18+4]
0x14005756d  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x140057574  jmp     loc_1400574E5
0x140057579  cmp     r14d, 0C01A002Bh
0x140057580  jnz     short loc_14005759F
0x140057582  mov     byte ptr [rbx+0BCh], 1
0x140057589  mov     rdx, [rbx+80h]; Entry
0x140057590  mov     rcx, rbx; this
0x140057593  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140057598  mov     [rbx+80h], r12
0x14005759f  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x1400575a6  jmp     loc_140057733
0x1400575ab  cmp     r14d, 0C01A002Fh
0x1400575b2  jz      loc_140057423
0x1400575b8  jmp     short loc_140057579
0x1400575ba  lea     rdx, [rbx+68h]
0x1400575be  test    rdx, rdx
0x1400575c1  jz      loc_1400574A0
0x1400575c7  mov     eax, [rdx+4]
0x1400575ca  cmp     [rcx+4], eax
0x1400575cd  jb      loc_1400574A0
0x1400575d3  jnz     short loc_1400575DF
0x1400575d5  mov     eax, [rdx]
0x1400575d7  cmp     [rcx], eax
0x1400575d9  jbe     loc_1400574A0
0x1400575df  mov     rax, [rcx]
0x1400575e2  mov     [rdx], rax
0x1400575e5  jmp     loc_1400574A0
0x1400575ea  test    rdi, rdi
0x1400575ed  jz      loc_14005742D
0x1400575f3  mov     rcx, [rbx+80h]
0x1400575fa  add     rcx, 70h ; 'p'
0x1400575fe  jz      short loc_140057621
0x140057600  mov     eax, dword ptr [rsp+0C8h+arg_18+4]
0x140057607  cmp     [rcx+4], eax
0x14005760a  ja      short loc_140057621
0x14005760c  jnz     loc_14005742D
0x140057612  mov     eax, dword ptr [rsp+0C8h+arg_18]
0x140057619  cmp     [rcx], eax
0x14005761b  jb      loc_14005742D
0x140057621  cmp     r14d, 0C01A002Fh
0x140057628  jz      loc_14005742D
0x14005762e  mov     [rsp+0C8h+BugCheckParameter4], r12; BugCheckParameter4
0x140057633  mov     r9, rbx; BugCheckParameter3
0x140057636  mov     r8, rdi; BugCheckParameter2
0x140057639  mov     edx, 40h ; '@'; BugCheckParameter1
0x14005763e  mov     ecx, 0C1F5h; BugCheckCode
0x140057643  call    cs:__imp_KeBugCheckEx
0x14005764f  cmp     rcx, rax
0x140057652  jnz     loc_140057574
0x140057658  jmp     loc_140057530
0x14005765d  mov     rdx, rax; Entry
0x140057660  mov     rcx, rbx; this
0x140057663  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140057668  lea     rdi, [rbx+98h]
0x14005766f  jmp     loc_1400574A0
0x140057674  mov     ecx, r12d
0x140057677  jmp     loc_140057368
0x14005767c  mov     r9d, r12d
0x14005767f  jmp     loc_1400573A4
0x140057684  mov     eax, r12d
0x140057687  jmp     loc_140057327
0x14005768c  mov     rdx, [rbx+80h]; Entry
0x140057693  test    rdx, rdx
0x140057696  jnz     short loc_1400576C6
0x140057698  mov     r14d, 0C01A002Bh
0x14005769e  mov     [rsp+0C8h+var_54], r14d
0x1400576a3  cmp     dword ptr cs:?m_infoGlobalError@CClfsLogFcbCommon@@2U_CLFS_ERROR_INFO@@A+8, 0; _CLFS_ERROR_INFO CClfsLogFcbCommon::m_infoGlobalError
0x1400576aa  jnz     loc_14005759F
0x1400576b0  mov     dword ptr cs:?m_infoGlobalError@CClfsLogFcbCommon@@2U_CLFS_ERROR_INFO@@A+8, 15h; _CLFS_ERROR_INFO CClfsLogFcbCommon::m_infoGlobalError
0x1400576ba  mov     dword ptr cs:?m_infoGlobalError@CClfsLogFcbCommon@@2U_CLFS_ERROR_INFO@@A+0Ch, r14d; _CLFS_ERROR_INFO CClfsLogFcbCommon::m_infoGlobalError
0x1400576c1  jmp     loc_14005759F
0x1400576c6  mov     rcx, rbx; this
0x1400576c9  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x1400576ce  mov     [rbx+80h], r12
0x1400576d5  jmp     short loc_140057698
0x1400576d7  mov     rdi, [rax+8]
0x1400576db  mov     r10d, [rax+10h]
0x1400576df  mov     [rsp+0C8h+var_50], r12d
0x1400576e4  mov     eax, 80808081h
0x1400576e9  mul     r10d
0x1400576ec  shr     edx, 8
0x1400576ef  mov     [rsp+0C8h+var_50], edx
0x1400576f3  imul    ecx, edx, 1FEh
0x1400576f9  cmp     r10d, ecx
0x1400576fc  jz      loc_140057348
0x140057702  inc     edx
0x140057704  mov     [rsp+0C8h+var_50], edx
0x140057708  jmp     loc_140057348
0x14005770d  mov     [rsp+0C8h+BugCheckParameter4], rbx; BugCheckParameter4
0x140057712  mov     r9, r10; BugCheckParameter3
0x140057715  mov     edx, 41h ; 'A'; BugCheckParameter1
0x14005771a  mov     ecx, 0C1F5h; BugCheckCode
0x14005771f  call    cs:__imp_KeBugCheckEx
0x14005772c  mov     ecx, 3
0x140057731  int     29h; Win8: RtlFailFast(ecx)
0x140057733  cmp     r14d, 0C01A0028h
0x14005773a  jz      short loc_14005779E
0x14005773c  cmp     r14d, 0C01A002Bh
0x140057743  jz      short loc_14005779E
0x140057745  test    r15b, r15b
0x140057748  jz      short loc_140057766
0x14005774a  mov     rdx, gs:188h; ResourceThreadId
0x140057753  mov     rcx, [rbx+90h]; Resource
0x14005775a  call    cs:__imp_ExReleaseResourceForThreadLite
0x140057761  nop     dword ptr [rax+rax+00h]
0x140057766  test    r13b, r13b
0x140057769  jz      short loc_140057787
0x14005776b  mov     rdx, gs:188h; ResourceThreadId
0x140057774  mov     rcx, [rbx+88h]; Resource
0x14005777b  call    cs:__imp_ExReleaseResourceForThreadLite
0x140057782  nop     dword ptr [rax+rax+00h]
0x140057787  mov     eax, r14d
0x14005778a  add     rsp, 90h
0x140057791  pop     r15
0x140057793  pop     r14
0x140057795  pop     r13
0x140057797  pop     r12
0x140057799  pop     rdi
0x14005779a  pop     rsi
0x14005779b  pop     rbx
0x14005779c  retn
0x14005779e  mov     qword ptr [rsp+0C8h+var_48], rcx
0x1400577a6  lea     rdx, [rsp+0C8h+var_48]; union _CLS_LSN *
0x1400577ae  mov     rcx, rbx; this
0x1400577b1  call    ?ReleaseFlushElements@CClfsKernelMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsKernelMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x1400577b6  jmp     short loc_140057745
0x140079900  push    rbx
0x140079902  push    rbp
0x140079903  sub     rsp, 78h
0x140079907  mov     rbp, rdx
0x14007990a  mov     eax, [rbp+74h]
0x14007990d  cmp     eax, 0C01A0028h
0x140079912  jz      short loc_140079924
0x140079914  cmp     eax, 0C01A002Bh
0x140079919  jz      short loc_140079924
  ... truncated ...
```
