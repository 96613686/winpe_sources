# CClfsLogFcbVirtual::WriteRestart(_FILE_OBJECT *,void *,ulong,__int64 const &,__int64 &,__int64 const &,uchar,uchar,uchar,IClfsRequestAsync *,_CLS_LSN const &,_CLS_LSN const &,_CLS_LSN &,_CLS_LSN &,ulong &,__int64 &)

- ea: `0x1400763b0`
- end: `0x140076b44`
- name: `?WriteRestart@CClfsLogFcbVirtual@@UEAAJPEAU_FILE_OBJECT@@PEAXKAEB_JAEA_J2EEEPEAUIClfsRequestAsync@@AEBT_CLS_LSN@@5AEAT4@6AEAK3@Z`
- size: `1940`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, struct _FILE_OBJECT *@<rdx>, void *@<r8>, unsigned int@<r9d>, const __int64 *, __int64 *, const __int64 *, char, char, char, ULONG_PTR BugCheckParameter3, CLFS_LSN *plsn1, const union _CLS_LSN *, union _CLS_LSN *, union _CLS_LSN *, unsigned int *, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140005840`
- `0x1400075b0`
- `0x140008c40`
- `0x14000a29c`
- `0x14000a8e0`
- `0x14000c018`
- `0x14000ed64`
- `0x140015ff0`
- `0x140017f20`
- `0x1400763b0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140076452`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400768f4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140076452`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400768f4`
- `ntoskrnl!KeBugCheckEx` at `0x1400766d7`
- `ntoskrnl!KeBugCheckEx` at `0x1400766d7`

## string_xrefs

- `0x1400768c6`: `CClfsLogFcbVirtual::WriteRestart`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbVirtual::WriteRestart(
        char *Context,
        struct _FILE_OBJECT *a2,
        void *a3,
        unsigned int a4,
        const __int64 *a5,
        __int64 *a6,
        const __int64 *a7,
        char a8,
        char a9,
        char a10,
        void (__fastcall ***BugCheckParameter3)(_QWORD),
        CLFS_LSN *plsn1,
        const union _CLS_LSN *a13,
        union _CLS_LSN *a14,
        union _CLS_LSN *a15,
        unsigned int *a16,
        __int64 *a17)
{
  __int64 v19; // r8
  CLFS_LSN *v20; // r15
  CLFS_LSN v21; // rbx
  CLFS_LSN *v22; // rdi
  char v23; // si
  __int64 v24; // rdx
  int v25; // eax
  int v26; // esi
  int v27; // eax
  ULONG_PTR v28; // r12
  CLFS_LSN v29; // rcx
  CLFS_LSN *v30; // r13
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  __int64 (__fastcall *v34)(char *, struct _FILE_OBJECT *, void *, _QWORD, __int64 *, __int64 *, const __int64 *, _BYTE, ULONG_PTR, const CLFS_LSN *, __int64 *, __int64 *, union _CLS_LSN *, CLFS_CONTAINER_ID *, CLFS_LSN *); // r10
  union _CLS_LSN *v35; // rdi
  char v36; // bl
  ULONG v37; // eax
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, __int64, __int64, char *); // rdi
  char v40; // bl
  __int64 v41; // rax
  __int64 v42; // r8
  CLFS_LSN *v43; // rax
  _QWORD *v44; // rax
  __int64 v45; // rdi
  void (__fastcall *v46)(__int64, __int64); // rbx
  __int64 v47; // rdx
  __int64 v48; // [rsp+28h] [rbp-D0h]
  BOOLEAN v49; // [rsp+80h] [rbp-78h]
  CLFS_LSN v50; // [rsp+88h] [rbp-70h] BYREF
  CLFS_CONTAINER_ID cidContainer[2]; // [rsp+90h] [rbp-68h] BYREF
  CLFS_LSN v52; // [rsp+98h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-58h] BYREF
  CLFS_LSN v54; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-40h]
  void *v58; // [rsp+110h] [rbp+18h] BYREF
  unsigned int v59; // [rsp+118h] [rbp+20h]

  v59 = a4;
  v58 = a3;
  v55 = 0;
  v56 = 0;
  v50 = CLFS_LSN_INVALID;
  *(CLFS_LSN *)cidContainer = CLFS_LSN_INVALID;
  v52 = CLFS_LSN_INVALID;
  if ( !a3 )
    return 3221225485LL;
  *a16 = 0;
  *a17 = 0;
  v49 = ExAcquireResourceExclusiveLite((PERESOURCE)(Context + 200), 1u);
  v20 = (CLFS_LSN *)(Context + 488);
  v21 = CLFS_LSN_INVALID;
  if ( Context == (char *)-488LL || CLFS_LSN_INVALID.ullOffset != v20->ullOffset )
  {
    v22 = plsn1;
    if ( ClfsLsnLess(plsn1, (const CLFS_LSN *)Context + 61) )
      goto LABEL_24;
  }
  else
  {
    v22 = plsn1;
  }
  v23 = Context[648];
  if ( v23 || v22 && CLFS_LSN_INVALID.ullOffset == v22->ullOffset || !ClfsLsnLess(v22, (const CLFS_LSN *)Context + 63) )
  {
    if ( !a10
      && (!v22 || CLFS_LSN_INVALID.ullOffset != v22->ullOffset)
      && a8
      && (unsigned __int8)operator!=(v22, Context + 488)
      && (!v22 || CLFS_LSN_NULL.ullOffset != v22->ullOffset || v23) )
    {
      v50 = *v22;
      LOBYTE(v24) = Context[616];
      v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, CLFS_LSN *, char *))(**((_QWORD **)Context + 80) + 184LL))(
              *((_QWORD *)Context + 80),
              v24,
              &v50,
              Context + 536);
      v26 = v25;
      if ( v25 < 0 )
      {
        if ( v25 == -1073741275 || v25 == -1073741807 || v25 == -1072037869 )
          v26 = -1072037860;
        goto LABEL_63;
      }
    }
    v27 = *((_DWORD *)Context + 91);
    if ( (v27 & 0x100) != 0 || (v27 & 0x200) != 0 )
    {
      v28 = (ULONG_PTR)BugCheckParameter3;
      if ( BugCheckParameter3 )
      {
        (**BugCheckParameter3)(BugCheckParameter3);
        (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v28 + 104LL))(v28);
        v31 = (*(__int64 (__fastcall **)(_QWORD, ULONG_PTR))(**((_QWORD **)Context + 80) + 408LL))(
                *((_QWORD *)Context + 80),
                v28);
        v26 = v31;
        if ( v31 )
        {
          if ( v31 < 0 )
            KeBugCheckEx(0xC1F5u, 0x20u, v31, v28, *((_QWORD *)Context + 80));
          (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v28 + 8LL))(v28);
        }
        else
        {
          v26 = 259;
        }
        goto LABEL_63;
      }
    }
    else
    {
      v28 = (ULONG_PTR)BugCheckParameter3;
    }
    *((_DWORD *)Context + 91) = v27 | 0x100;
    v29 = *v20;
    *((CLFS_LSN *)Context + 65) = *v20;
    *((_QWORD *)Context + 66) = *((_QWORD *)Context + 64);
    v30 = (CLFS_LSN *)(Context + 536);
    *((CLFS_LSN *)Context + 67) = CLFS_LSN_INVALID;
    if ( v22 && CLFS_LSN_INVALID.ullOffset == v22->ullOffset )
    {
      v50 = v29;
      LOBYTE(v19) = Context[616];
      *v30 = *(CLFS_LSN *)(*(__int64 (__fastcall **)(_QWORD, CLFS_LSN *, __int64))(**((_QWORD **)Context + 80) + 288LL))(
                            *((_QWORD *)Context + 80),
                            &v54,
                            v19);
    }
    else if ( ClfsLsnLess((const CLFS_LSN *)Context + 61, v22) )
    {
      v50 = *v22;
      LOBYTE(v32) = Context[616];
      v33 = (*(__int64 (__fastcall **)(_QWORD, __int64, CLFS_LSN *, char *))(**((_QWORD **)Context + 80) + 184LL))(
              *((_QWORD *)Context + 80),
              v32,
              &v50,
              Context + 536);
      v26 = v33;
      if ( v33 < 0 && v33 != -1073741807 && v33 != -1073741275 )
      {
LABEL_63:
        v21 = CLFS_LSN_INVALID;
        goto LABEL_64;
      }
    }
    *((union _CLS_LSN *)Context + 68) = *a13;
    v34 = *(__int64 (__fastcall **)(char *, struct _FILE_OBJECT *, void *, _QWORD, __int64 *, __int64 *, const __int64 *, _BYTE, ULONG_PTR, const CLFS_LSN *, __int64 *, __int64 *, union _CLS_LSN *, CLFS_CONTAINER_ID *, CLFS_LSN *))(*(_QWORD *)Context + 120LL);
    v53 = *a5;
    v35 = a15;
    v26 = v34(Context, a2, v58, v59, &v53, a6, a7, 0, v28, &CLFS_LSN_NULL, &v55, a17, a15, cidContainer, &v52);
    if ( v26 < 0 )
    {
      v36 = 1;
    }
    else
    {
      LODWORD(v58) = 0;
      v54 = CLFS_LSN_NULL;
      ClfsReleaseResourceLite((struct _ERESOURCE *)(Context + 200));
      v26 = (*(__int64 (__fastcall **)(char *, CLFS_LSN *, _QWORD, _QWORD, void **))(*(_QWORD *)Context + 192LL))(
              Context,
              &v54,
              0,
              0,
              &v58);
      if ( v26 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
        {
          LODWORD(v48) = v26;
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            12,
            (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
            (unsigned int)"CClfsLogFcbVirtual::WriteRestart",
            30,
            v48);
        }
        v26 = -1072037841;
      }
      v36 = 1;
      v49 = ExAcquireResourceExclusiveLite((PERESOURCE)(Context + 200), 1u);
    }
    *a14 = *v35;
    if ( v26 )
      goto LABEL_63;
    if ( CLFS_LSN_INVALID.ullOffset != v50.ullOffset )
    {
      if ( Context == (char *)-488LL )
      {
        v36 = 0;
LABEL_55:
        if ( v36 )
        {
          *v20 = v50;
          if ( Context != (char *)-536LL && CLFS_LSN_INVALID.ullOffset == v30->ullOffset )
          {
            v37 = ClfsLsnRecordSequence((const CLFS_LSN *)Context + 61);
            *v30 = ClfsLsnCreate(cidContainer[1], cidContainer[0] & 0xFFFFFE00, v37);
          }
          v38 = *((_QWORD *)Context + 80);
          v39 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v38 + 304LL);
          v40 = Context[616];
          v41 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)v28 + 56LL))(v28);
          LOBYTE(v42) = v40;
          v26 = v39(v38, v41, v42, Context + 536);
          if ( v26 < 0 )
            goto LABEL_63;
        }
        goto LABEL_60;
      }
      if ( *((_QWORD *)Context + 61) < v50.ullOffset )
        goto LABEL_55;
    }
LABEL_60:
    *((_QWORD *)Context + 64) = *((_QWORD *)Context + 68);
    *a16 = v56;
    if ( (Context[376] & 0x20) == 0 )
      *((CLFS_LSN *)Context + 62) = *v20;
    v26 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)Context + 112LL))(Context);
    goto LABEL_63;
  }
LABEL_24:
  v26 = -1072037860;
LABEL_64:
  if ( v26 != 259 )
  {
    if ( v26 < 0 )
    {
      v43 = (CLFS_LSN *)(Context + 520);
      if ( Context == (char *)-520LL || v21.ullOffset != v43->ullOffset )
      {
        *v20 = *v43;
        v21 = CLFS_LSN_INVALID;
      }
      v44 = Context + 528;
      if ( Context == (char *)-528LL || v21.ullOffset != *v44 )
        *((_QWORD *)Context + 64) = *v44;
    }
    *((_DWORD *)Context + 91) &= ~0x100u;
    *((CLFS_LSN *)Context + 65) = CLFS_LSN_INVALID;
    *((CLFS_LSN *)Context + 66) = CLFS_LSN_INVALID;
    *((CLFS_LSN *)Context + 67) = CLFS_LSN_INVALID;
    *((CLFS_LSN *)Context + 68) = CLFS_LSN_INVALID;
    v45 = *((_QWORD *)Context + 80);
    v46 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 432LL);
    LOBYTE(v47) = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)Context + 304LL))(Context);
    v46(v45, v47);
    CClfsLogFcbCommon::NotifyObservers((CClfsLogFcbCommon *)Context, 0xCF00u, Context + 488, 0);
  }
  if ( v49 )
    ClfsReleaseResourceLite((struct _ERESOURCE *)(Context + 200));
  if ( !a9 && v26 >= 0 && v26 != 259 )
    CClfsLogFcbCommon::QueueRundownContainerDeleteQ(Context);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1400763b0  mov     r11, rsp
0x1400763b3  mov     [r11+20h], r9d
0x1400763b7  mov     [r11+18h], r8
0x1400763bb  mov     [r11+10h], rdx
0x1400763bf  mov     [r11+8], rcx
0x1400763c3  push    rbx
0x1400763c4  push    rsi
0x1400763c5  push    rdi
0x1400763c6  push    r12
0x1400763c8  push    r13
0x1400763ca  push    r14
0x1400763cc  push    r15
0x1400763ce  sub     rsp, 0C0h
0x1400763d5  mov     r14, rcx
0x1400763d8  mov     qword ptr [r11-48h], 0
0x1400763e0  mov     qword ptr [r11-40h], 0
0x1400763e8  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1400763ef  mov     [r11-70h], rax
0x1400763f3  mov     [r11-68h], rax
0x1400763f7  mov     [r11-60h], rax
0x1400763fb  test    r8, r8
0x1400763fe  jnz     short loc_140076419
0x140076400  mov     eax, 0C000000Dh
0x140076405  add     rsp, 0C0h
0x14007640c  pop     r15
0x14007640e  pop     r14
0x140076410  pop     r13
0x140076412  pop     r12
0x140076414  pop     rdi
0x140076415  pop     rsi
0x140076416  pop     rbx
0x140076417  retn
0x140076419  mov     [rsp+0F8h+var_74], 0
0x140076424  mov     [rsp+0F8h+var_78], 0
0x14007642c  mov     rax, [rsp+0F8h+arg_78]
0x140076434  mov     dword ptr [rax], 0
0x14007643a  mov     rax, [rsp+0F8h+arg_80]
0x140076442  mov     qword ptr [rax], 0
0x140076449  add     rcx, 0C8h; Resource
0x140076450  mov     dl, 1; Wait
0x140076452  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140076459  nop     dword ptr [rax+rax+00h]
0x14007645e  mov     [rsp+0F8h+var_78], al
0x140076465  lea     r15, [r14+1E8h]
0x14007646c  mov     rbx, qword ptr cs:CLFS_LSN_INVALID
0x140076473  test    r15, r15
0x140076476  jz      loc_14007657F
0x14007647c  cmp     rbx, [r15]
0x14007647f  jnz     loc_14007657F
0x140076485  mov     rdi, [rsp+0F8h+plsn1]
0x14007648d  mov     sil, [r14+288h]
0x140076494  test    sil, sil
0x140076497  jnz     short loc_1400764BA
0x140076499  test    rdi, rdi
0x14007649c  jz      short loc_1400764A3
0x14007649e  cmp     rbx, [rdi]
0x1400764a1  jz      short loc_1400764BA
0x1400764a3  lea     rdx, [r14+1F8h]; plsn2
0x1400764aa  mov     rcx, rdi; plsn1
0x1400764ad  call    ClfsLsnLess
0x1400764b2  test    al, al
0x1400764b4  jnz     loc_14007659A
0x1400764ba  cmp     [rsp+0F8h+arg_48], 0
0x1400764c2  jnz     loc_1400765AB
0x1400764c8  test    rdi, rdi
0x1400764cb  jz      short loc_1400764D6
0x1400764cd  cmp     rbx, [rdi]
0x1400764d0  jz      loc_1400765AB
0x1400764d6  cmp     [rsp+0F8h+arg_38], 0
0x1400764de  jz      loc_1400765AB
0x1400764e4  mov     rdx, r15
0x1400764e7  mov     rcx, rdi
0x1400764ea  call    ??9@YAEAEBT_CLS_LSN@@0@Z; operator!=(_CLS_LSN const &,_CLS_LSN const &)
0x1400764ef  test    al, al
0x1400764f1  jz      loc_1400765AB
0x1400764f7  test    rdi, rdi
0x1400764fa  jz      short loc_140076511
0x1400764fc  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140076503  cmp     rax, [rdi]
0x140076506  jnz     short loc_140076511
0x140076508  test    sil, sil
0x14007650b  jz      loc_1400765AB
0x140076511  mov     rax, [rdi]
0x140076514  mov     [rsp+0F8h+var_70], rax
0x14007651c  mov     rcx, [r14+280h]
0x140076523  mov     rax, [rcx]
0x140076526  lea     r9, [r14+218h]
0x14007652d  mov     rax, [rax+0B8h]
0x140076534  lea     r8, [rsp+0F8h+var_70]
0x14007653c  mov     dl, [r14+268h]
0x140076543  call    _guard_dispatch_icall
0x140076548  mov     esi, eax
0x14007654a  mov     [rsp+0F8h+var_74], eax
0x140076551  test    eax, eax
0x140076553  jns     short loc_1400765AB
0x140076555  cmp     eax, 0C0000225h
0x14007655a  jz      short loc_14007656E
0x14007655c  cmp     eax, 0C0000011h
0x140076561  jz      short loc_14007656E
0x140076563  cmp     eax, 0C01A0013h
0x140076568  jnz     loc_140076A35
0x14007656e  mov     esi, 0C01A001Ch
0x140076573  mov     [rsp+0F8h+var_74], esi
0x14007657a  jmp     loc_140076A35
0x14007657f  mov     rdx, r15; plsn2
0x140076582  mov     rdi, [rsp+0F8h+plsn1]
0x14007658a  mov     rcx, rdi; plsn1
0x14007658d  call    ClfsLsnLess
0x140076592  test    al, al
0x140076594  jz      loc_14007648D
0x14007659a  mov     esi, 0C01A001Ch
0x14007659f  mov     [rsp+0F8h+var_74], esi
0x1400765a6  jmp     loc_140076A3C
0x1400765ab  mov     eax, [r14+16Ch]
0x1400765b2  mov     ecx, 100h
0x1400765b7  test    ecx, eax
0x1400765b9  jnz     loc_140076658
0x1400765bf  bt      eax, 9
0x1400765c3  jb      loc_140076658
0x1400765c9  mov     r12, [rsp+0F8h+BugCheckParameter3]
0x1400765d1  or      eax, ecx
0x1400765d3  mov     [r14+16Ch], eax
0x1400765da  mov     rcx, [r15]
0x1400765dd  mov     [r14+208h], rcx
0x1400765e4  mov     rax, [r14+200h]
0x1400765eb  mov     [r14+210h], rax
0x1400765f2  lea     r13, [r14+218h]
0x1400765f9  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140076600  mov     [r13+0], rax
0x140076604  xor     ebx, ebx
0x140076606  test    rdi, rdi
0x140076609  jz      loc_1400766F8
0x14007660f  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140076616  cmp     rax, [rdi]
0x140076619  jnz     loc_1400766F8
0x14007661f  mov     [rsp+0F8h+var_70], rcx
0x140076627  mov     rcx, [r14+280h]
0x14007662e  mov     rax, [rcx]
0x140076631  mov     rax, [rax+120h]
0x140076638  mov     r8b, [r14+268h]
0x14007663f  lea     rdx, [rsp+0F8h+var_50]
0x140076647  call    _guard_dispatch_icall
0x14007664c  mov     rcx, [rax]
0x14007664f  mov     [r13+0], rcx
0x140076653  jmp     loc_140076759
0x140076658  mov     r12, [rsp+0F8h+BugCheckParameter3]
0x140076660  test    r12, r12
0x140076663  jz      loc_1400765D1
0x140076669  mov     rax, [r12]
0x14007666d  mov     rax, [rax]
0x140076670  mov     rcx, r12
0x140076673  call    _guard_dispatch_icall
0x140076678  mov     rax, [r12]
0x14007667c  mov     rax, [rax+68h]
0x140076680  mov     rcx, r12
0x140076683  call    _guard_dispatch_icall
0x140076688  mov     rcx, [r14+280h]
0x14007668f  mov     rax, [rcx]
0x140076692  mov     rax, [rax+198h]
0x140076699  mov     rdx, r12
0x14007669c  call    _guard_dispatch_icall
0x1400766a1  movsxd  rsi, eax
0x1400766a4  mov     [rsp+0F8h+var_74], esi
0x1400766ab  test    eax, eax
0x1400766ad  jnz     short loc_1400766B9
0x1400766af  mov     esi, 103h
0x1400766b4  jmp     loc_140076573
0x1400766b9  jns     short loc_1400766E3
0x1400766bb  mov     r8, rsi; BugCheckParameter2
0x1400766be  mov     rax, [r14+280h]
0x1400766c5  mov     [rsp+0F8h+BugCheckParameter4], rax; BugCheckParameter4
0x1400766ca  mov     r9, r12; BugCheckParameter3
0x1400766cd  mov     edx, 20h ; ' '; BugCheckParameter1
0x1400766d2  mov     ecx, 0C1F5h; BugCheckCode
0x1400766d7  call    cs:__imp_KeBugCheckEx
0x1400766e3  mov     rax, [r12]
0x1400766e7  mov     rax, [rax+8]
0x1400766eb  mov     rcx, r12
0x1400766ee  call    _guard_dispatch_icall
0x1400766f3  jmp     loc_140076A35
0x1400766f8  mov     rdx, rdi; plsn2
0x1400766fb  mov     rcx, r15; plsn1
0x1400766fe  call    ClfsLsnLess
0x140076703  test    al, al
0x140076705  jz      short loc_140076759
0x140076707  mov     rax, [rdi]
0x14007670a  mov     [rsp+0F8h+var_70], rax
0x140076712  mov     rcx, [r14+280h]
0x140076719  mov     rax, [rcx]
0x14007671c  mov     rax, [rax+0B8h]
0x140076723  mov     r9, r13
0x140076726  lea     r8, [rsp+0F8h+var_70]
0x14007672e  mov     dl, [r14+268h]
0x140076735  call    _guard_dispatch_icall
0x14007673a  mov     esi, eax
0x14007673c  mov     [rsp+0F8h+var_74], eax
0x140076743  test    eax, eax
0x140076745  jns     short loc_140076759
0x140076747  cmp     eax, 0C0000011h
0x14007674c  jz      short loc_140076759
0x14007674e  cmp     eax, 0C0000225h
0x140076753  jnz     loc_140076A35
0x140076759  mov     rax, [rsp+0F8h+arg_60]
0x140076761  mov     rcx, [rax]
0x140076764  mov     [r14+220h], rcx
0x14007676b  mov     rax, [r14]
0x14007676e  mov     r10, [rax+78h]
0x140076772  mov     rax, [rsp+0F8h+arg_20]
0x14007677a  mov     rcx, [rax]
0x14007677d  mov     [rsp+0F8h+var_58], rcx
0x140076785  lea     rax, [rsp+0F8h+var_60]
0x14007678d  mov     [rsp+0F8h+var_88], rax
0x140076792  lea     rax, [rsp+0F8h+cidContainer]
0x14007679a  mov     [rsp+0F8h+var_90], rax
0x14007679f  mov     rdi, [rsp+0F8h+arg_70]
0x1400767a7  mov     [rsp+0F8h+var_98], rdi
0x1400767ac  mov     rax, [rsp+0F8h+arg_80]
0x1400767b4  mov     [rsp+0F8h+var_A0], rax
0x1400767b9  lea     rax, [rsp+0F8h+var_48]
0x1400767c1  mov     [rsp+0F8h+var_A8], rax
0x1400767c6  lea     rax, CLFS_LSN_NULL
0x1400767cd  mov     [rsp+0F8h+var_B0], rax
0x1400767d2  mov     [rsp+0F8h+var_B8], r12
0x1400767d7  mov     [rsp+0F8h+var_C0], bl
0x1400767db  mov     rcx, [rsp+0F8h+arg_30]
0x1400767e3  mov     [rsp+0F8h+var_C8], rcx
0x1400767e8  mov     rcx, [rsp+0F8h+arg_28]
0x1400767f0  mov     [rsp+0F8h+var_D0], rcx
0x1400767f5  lea     rax, [rsp+0F8h+var_58]
0x1400767fd  mov     [rsp+0F8h+BugCheckParameter4], rax
0x140076802  mov     r9d, [rsp+0F8h+arg_18]
0x14007680a  mov     r8, [rsp+0F8h+arg_10]
0x140076812  mov     rdx, [rsp+0F8h+arg_8]
0x14007681a  mov     rcx, r14
0x14007681d  mov     rax, r10
0x140076820  call    _guard_dispatch_icall
0x140076825  mov     esi, eax
0x140076827  mov     [rsp+0F8h+var_74], eax
0x14007682e  test    eax, eax
0x140076830  js      loc_140076909
0x140076836  mov     dword ptr [rsp+0F8h+arg_10], ebx
0x14007683d  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x140076844  mov     [rsp+0F8h+var_50], rax
0x14007684c  lea     rcx, [r14+0C8h]
0x140076853  call    ClfsReleaseResourceLite
0x140076858  mov     [rsp+0F8h+var_78], bl
0x14007685f  mov     rax, [r14]
0x140076862  mov     rax, [rax+0C0h]
0x140076869  lea     rcx, [rsp+0F8h+arg_10]
0x140076871  mov     [rsp+0F8h+BugCheckParameter4], rcx
0x140076876  xor     r9d, r9d
0x140076879  xor     r8d, r8d
0x14007687c  lea     rdx, [rsp+0F8h+var_50]
0x140076884  mov     rcx, r14
0x140076887  call    _guard_dispatch_icall
0x14007688c  mov     esi, eax
0x14007688e  mov     [rsp+0F8h+var_74], eax
0x140076895  test    eax, eax
0x140076897  jns     short loc_1400768E9
0x140076899  lea     rax, WPP_GLOBAL_Control
0x1400768a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400768a7  cmp     rcx, rax
0x1400768aa  jz      short loc_1400768DD
0x1400768ac  test    dword ptr [rcx+2Ch], 8000000h
0x1400768b3  jz      short loc_1400768DD
0x1400768b5  mov     edx, 0Ch
0x1400768ba  mov     dword ptr [rsp+0F8h+var_D0], esi
0x1400768be  mov     dword ptr [rsp+0F8h+BugCheckParameter4], 121Eh
0x1400768c6  lea     r9, aCclfslogfcbvir_1; "CClfsLogFcbVirtual::WriteRestart"
0x1400768cd  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x1400768d4  mov     rcx, [rcx+18h]
0x1400768d8  call    WPP_SF_slD
0x1400768dd  mov     esi, 0C01A002Fh
0x1400768e2  mov     [rsp+0F8h+var_74], esi
0x1400768e9  mov     bl, 1
0x1400768eb  mov     dl, bl; Wait
0x1400768ed  lea     rcx, [r14+0C8h]; Resource
0x1400768f4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400768fb  nop     dword ptr [rax+rax+00h]
0x140076900  mov     [rsp+0F8h+var_78], al
0x140076907  jmp     short loc_14007690B
0x140076909  mov     bl, 1
0x14007690b  mov     rcx, [rdi]
0x14007690e  mov     rax, [rsp+0F8h+arg_68]
0x140076916  mov     [rax], rcx
0x140076919  test    esi, esi
0x14007691b  jnz     loc_140076A35
0x140076921  mov     rax, [rsp+0F8h+var_70]
0x140076929  cmp     qword ptr cs:CLFS_LSN_INVALID, rax
0x140076930  jz      loc_1400769EA
0x140076936  test    r15, r15
0x140076939  jz      short loc_140076959
0x14007693b  mov     ecx, [r15+4]
0x14007693f  cmp     ecx, dword ptr [rsp+0F8h+var_70+4]
0x140076946  ja      loc_1400769EA
0x14007694c  jnz     short loc_14007695B
0x14007694e  cmp     [r15], eax
0x140076951  jnb     loc_1400769EA
0x140076957  jmp     short loc_14007695B
0x140076959  xor     bl, bl
  ... truncated ...
```
