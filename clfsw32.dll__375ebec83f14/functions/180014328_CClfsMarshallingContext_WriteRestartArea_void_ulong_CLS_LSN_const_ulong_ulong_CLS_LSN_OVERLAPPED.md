# CClfsMarshallingContext::WriteRestartArea(void *,ulong,_CLS_LSN const &,ulong,ulong &,_CLS_LSN &,_OVERLAPPED *)

- ea: `0x180014328`
- end: `0x180014997`
- name: `?WriteRestartArea@CClfsMarshallingContext@@QEAAKPEAXKAEBT_CLS_LSN@@KAEAKAEAT2@PEAU_OVERLAPPED@@@Z`
- size: `1647`
- prototype: `unsigned int __usercall@<eax>(CClfsMarshallingContext *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const union _CLS_LSN *@<r9>, char, unsigned int *, union _CLS_LSN *, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000dc40`

## callees

- `0x180009378`
- `0x18000e534`
- `0x18000e8e4`
- `0x18000efa0`
- `0x18000f60c`
- `0x18000f770`
- `0x1800101c8`
- `0x1800106f8`
- `0x1800130a0`
- `0x180014008`
- `0x180014328`
- `0x180014dce`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180014984`
- `ntdll!RtlLeaveCriticalSection` at `0x180015ccd`
- `ntdll!RtlLeaveCriticalSection` at `0x180014984`
- `ntdll!RtlLeaveCriticalSection` at `0x180015ccd`
- `ntdll!RtlEnterCriticalSection` at `0x1800143be`
- `ntdll!RtlEnterCriticalSection` at `0x1800143be`

## pseudocode

```c
__int64 __fastcall CClfsMarshallingContext::WriteRestartArea(
        CClfsMarshallingContext *this,
        void *a2,
        ULONG a3,
        union _CLS_LSN *a4,
        char a5,
        unsigned int *a6,
        union _CLS_LSN *a7,
        struct _OVERLAPPED *a8)
{
  ULONG ByteLength; // ebx
  int v11; // r13d
  struct _RTL_CRITICAL_SECTION *v13; // r14
  char v14; // r15
  unsigned int Iocb; // ebx
  int v16; // ecx
  __int64 v17; // rax
  union _CLS_LSN *ullOffset; // rax
  struct CLogIocb **v19; // r14
  __int64 v20; // rdx
  struct CLogIocb *v21; // r10
  ULONG v22; // r8d
  ULONG v23; // edx
  ULONG v24; // r9d
  unsigned int v25; // edx
  int v26; // eax
  unsigned int v27; // eax
  struct CLogIocb *v28; // rax
  __int64 v29; // rbx
  CLFS_LSN *v30; // rdi
  unsigned __int64 v31; // rax
  CLFS_RECORD_INDEX *v32; // rcx
  unsigned int appended; // eax
  struct _CLFS_RECORD_HEADER *v34; // r9
  DWORD *v35; // rbx
  __int64 v36; // rdi
  union _CLS_LSN *v37; // r9
  union _CLS_LSN *v38; // r10
  unsigned int v39; // eax
  unsigned int v40; // ecx
  char v41; // al
  union _CLS_LSN *v42; // rdx
  unsigned int v43; // r9d
  __int64 v44; // r8
  struct _CLFS_RECORD_HEADER *v45; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v46; // [rsp+80h] [rbp-88h]
  union _CLS_LSN v47; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v48; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v49; // [rsp+94h] [rbp-74h] BYREF
  struct _CLFS_RECORD_HEADER *v50; // [rsp+98h] [rbp-70h] BYREF
  struct _CLFS_RECORD_HEADER *v51; // [rsp+A0h] [rbp-68h] BYREF
  _CLS_WRITE_ENTRY v52; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v53; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-48h]
  __int64 v55; // [rsp+C8h] [rbp-40h]
  _CLS_WRITE_ENTRY v56; // [rsp+118h] [rbp+10h]

  v56.ByteLength = a3;
  v56.Buffer = a2;
  ByteLength = a3;
  v52.Buffer = 0;
  *(_QWORD *)&v52.ByteLength = 0;
  v50 = 0;
  v51 = 0;
  LODWORD(a8) = 0;
  v49 = 0;
  v48 = 0;
  v11 = 2;
  *a7 = CLFS_LSN_NULL;
  *a6 = 0;
  if ( !*((_DWORD *)this + 31) )
    return 6605;
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 288));
  v14 = 1;
  if ( !*((_BYTE *)this + 100) )
  {
    v16 = *((_DWORD *)this + 34);
    if ( v16 )
      v17 = -v16 & (unsigned int)(v16 + *((_DWORD *)this + 32) + 983);
    else
      v17 = 0;
    v53 = v17;
    if ( *((_DWORD *)this + 33) < ByteLength )
    {
      Iocb = 122;
      goto LABEL_70;
    }
    ullOffset = (union _CLS_LSN *)CLFS_LSN_INVALID.ullOffset;
    if ( a4 && CLFS_LSN_INVALID.ullOffset == a4->ullOffset )
    {
      v19 = (struct CLogIocb **)((char *)this + 160);
    }
    else
    {
      v19 = (struct CLogIocb **)((char *)this + 160);
      v20 = *((_QWORD *)this + 20);
      if ( v20 )
      {
        v47 = CLFS_LSN_INVALID;
        v45 = 0;
        ClfsFindLsnInBlock(a4, *(unsigned __int8 **)(v20 + 64), &v45, &v47);
        if ( !a4 || a4->ullOffset != v47.ullOffset )
          v45 = 0;
        if ( v45 )
          v11 = 0;
        ullOffset = (union _CLS_LSN *)CLFS_LSN_INVALID.ullOffset;
      }
      if ( v11 )
      {
        Iocb = CClfsMarshallingContext::ValidateLogBase(this, a4);
        if ( Iocb )
          goto LABEL_69;
        LOBYTE(v11) = 0;
        ullOffset = (union _CLS_LSN *)CLFS_LSN_INVALID.ullOffset;
        ByteLength = v56.ByteLength;
      }
    }
    v21 = *v19;
    if ( *v19 )
    {
      v22 = *((_DWORD *)v21 + 18);
      v23 = v22 + ((ByteLength + 7) & 0xFFFFFFF8) + 40;
      if ( v23 < v22 )
      {
        Iocb = 87;
        v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
        goto LABEL_71;
      }
      v24 = v22 + ((ByteLength + 7) & 0xFFFFFFF8) + 40;
      v25 = v23 / 0x1FE;
      v46 = v24 / 0x1FE;
      if ( v24 != 510 * (v24 / 0x1FE) )
        v46 = ++v25;
      v26 = *((_DWORD *)this + 34);
      v27 = v26 ? ~(v26 - 1) & (v24 + v26 - 1 + ((2 * v25 + 7) & 0xFFFFFFF8)) : 0;
      if ( v27 > *((_DWORD *)this + 33) || ((*((_DWORD *)v21 + 19) + 1) & 0xFFFFFE00) != 0 )
      {
        Iocb = CClfsMarshallingContext::AppendWriteBlockToFlushQueue(this, 0, 0, 0);
        if ( Iocb )
          goto LABEL_69;
      }
    }
    if ( !*v19 )
    {
      Iocb = CClfsMarshallingContext::AllocateIocb(this, 1, v19);
      if ( Iocb )
        goto LABEL_69;
      v28 = *v19;
      v45 = v28;
      if ( !v28 )
        goto LABEL_69;
      v29 = *((unsigned int *)this + 32);
      v30 = (CLFS_LSN *)*((_QWORD *)v28 + 8);
      memset_0(v30, 0, 0x70u);
      LOBYTE(v30->offset.idxRecord) = 21;
      v30[3] = CLFS_LSN_INVALID;
      v30[4] = CLFS_LSN_INVALID;
      v30[5].offset.idxRecord = 112;
      v31 = (unsigned __int64)(v29 - 40) >> 9;
      HIWORD(v30->ullOffset) = v31;
      WORD2(v30->ullOffset) = v31;
      *((_DWORD *)v45 + 18) = 112;
      v30[5].offset.idxRecord = 0;
    }
    v52 = v56;
    v32 = (CLFS_RECORD_INDEX *)*v19;
    v54 = *((_QWORD *)*v19 + 10);
    v47.offset.idxRecord = v32[18];
    CLogIocb::GetLastRecord((CLogIocb *)v32, &v51);
    LODWORD(v45) = *((_DWORD *)this + 38);
    v55 = *((_QWORD *)this + 22);
    appended = CClfsMarshallingContext::AppendRecord(
                 this,
                 &v52,
                 1u,
                 1u,
                 0,
                 0,
                 a5,
                 &v50,
                 &v49,
                 &v48,
                 (unsigned int *)&a8);
    Iocb = appended;
    if ( appended )
    {
      if ( appended == 234 )
        Iocb = 122;
      goto LABEL_69;
    }
    v34 = v50;
    *((_BYTE *)v50 + 36) |= 2u;
    *((_QWORD *)v34 + 2) = *((_QWORD *)this + 28);
    v35 = a6;
    *a6 += (unsigned int)a8;
    *((_WORD *)*v19 + 14) |= 8u;
    a6 = (unsigned int *)a4->ullOffset;
    v36 = *((_QWORD *)*v19 + 8);
    ClfsStampLogBlock((struct _CLFS_LOG_BLOCK_HEADER *)v36, *((_DWORD *)*v19 + 18), *((_DWORD *)this + 34), v34);
    v38 = a7;
    *a7 = *v37;
    v39 = NtWriteLogRestartAreaInternal(
            *((void **)this + 6),
            a4,
            *((_QWORD **)*v19 + 8),
            *(unsigned __int16 *)(v36 + 4) << 9,
            (__int64 *const)*v19 + 10,
            (__int64 *)this + 24,
            &v53,
            v38,
            (union _CLS_LSN *)&a6,
            v35,
            *((void **)*v19 + 7),
            v11);
    Iocb = v39;
    if ( !v39 )
    {
      *((_QWORD *)this + 23) = *((_QWORD *)this + 22);
      v40 = HIDWORD(a6);
      if ( this == (CClfsMarshallingContext *)-200LL )
      {
        v41 = 0;
      }
      else
      {
        if ( (unsigned __int64)a6 <= *((_QWORD *)this + 25) )
          goto LABEL_49;
        v41 = 1;
      }
      if ( v41 )
        *((_QWORD *)this + 25) = a6;
LABEL_49:
      v42 = (union _CLS_LSN *)((char *)this + 208);
      if ( this == (CClfsMarshallingContext *)-208LL )
      {
        v14 = 0;
      }
      else if ( *((_DWORD *)this + 53) > v40
             || *((_DWORD *)this + 53) == v40 && v42->offset.idxRecord >= (unsigned int)a6 )
      {
LABEL_57:
        *((union _CLS_LSN *)this + 28) = *a7;
        CClfsMarshallingContext::ReleaseFlushElements(this, v42);
        goto LABEL_68;
      }
      if ( v14 )
        v42->ullOffset = (ULONGLONG)a6;
      goto LABEL_57;
    }
    if ( v39 != 6627 )
    {
      if ( v39 == 6643 )
        *((_BYTE *)this + 100) = 1;
      goto LABEL_68;
    }
    *((_QWORD *)*v19 + 10) = v54;
    *((_DWORD *)*v19 + 18) = v47.offset.idxRecord;
    *((_DWORD *)this + 38) = (_DWORD)v45;
    *((_QWORD *)this + 22) = v55;
    if ( v51 )
      *((_BYTE *)v51 + 36) |= 0x20u;
    v43 = --*((_DWORD *)*v19 + 19);
    v44 = v43 / 0x1F;
    if ( v43 == 31 * (_DWORD)v44 && v43 < 0x1F0 )
      *(_DWORD *)(v36 + 4 * v44 + 40) = 0;
    if ( *((_DWORD *)*v19 + 19) )
    {
LABEL_68:
      CClfsMarshallingContext::FreeIocb(this, *v19);
      *v19 = 0;
      goto LABEL_69;
    }
    *(CLFS_LSN *)(v36 + 24) = CLFS_LSN_INVALID;
LABEL_69:
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 288);
    goto LABEL_70;
  }
  Iocb = 6643;
LABEL_70:
  ullOffset = (union _CLS_LSN *)CLFS_LSN_INVALID.ullOffset;
LABEL_71:
  if ( Iocb == 6640 || Iocb == 6643 )
  {
    a7 = ullOffset;
    CClfsMarshallingContext::ReleaseFlushElements(this, (union _CLS_LSN *)&a7);
  }
  RtlLeaveCriticalSection(v13);
  return Iocb;
}

```

## disassembly

```asm
0x180014328  mov     rax, rsp
0x18001432b  mov     [rax+18h], r8d
0x18001432f  mov     [rax+10h], rdx
0x180014333  mov     [rax+8], rcx
0x180014337  push    rbx
0x180014338  push    rsi
0x180014339  push    rdi
0x18001433a  push    r12
0x18001433c  push    r13
0x18001433e  push    r14
0x180014340  push    r15
0x180014342  sub     rsp, 0D0h
0x180014349  mov     r12, r9
0x18001434c  mov     ebx, r8d
0x18001434f  mov     rsi, rcx
0x180014352  xor     edi, edi
0x180014354  mov     [rax-60h], rdi
0x180014358  mov     [rax-58h], rdi
0x18001435c  mov     [rax-70h], rdi
0x180014360  mov     [rax-68h], rdi
0x180014364  mov     [rsp+108h+var_98], dil
0x180014369  mov     [rsp+108h+var_94], edi
0x18001436d  mov     [rax+40h], edi
0x180014370  mov     [rax-74h], edi
0x180014373  mov     [rax-78h], edi
0x180014376  lea     r13d, [rdi+2]
0x18001437a  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x180014381  mov     rcx, qword ptr [rsp+108h+arg_30]
0x180014389  mov     [rcx], rax
0x18001438c  mov     rax, qword ptr [rsp+108h+arg_28]
0x180014394  mov     [rax], edi
0x180014396  cmp     [rsi+7Ch], edi
0x180014399  jnz     short loc_1800143B4
0x18001439b  mov     eax, 19CDh
0x1800143a0  add     rsp, 0D0h
0x1800143a7  pop     r15
0x1800143a9  pop     r14
0x1800143ab  pop     r13
0x1800143ad  pop     r12
0x1800143af  pop     rdi
0x1800143b0  pop     rsi
0x1800143b1  pop     rbx
0x1800143b2  retn
0x1800143b4  lea     r14, [rsi+120h]
0x1800143bb  mov     rcx, r14; CriticalSection
0x1800143be  call    cs:__imp_RtlEnterCriticalSection
0x1800143c5  nop     dword ptr [rax+rax+00h]
0x1800143ca  mov     r15d, 1
0x1800143d0  mov     [rsp+108h+var_98], r15b
0x1800143d5  cmp     [rsi+64h], dil
0x1800143d9  jz      short loc_1800143E9
0x1800143db  mov     ebx, 19F3h
0x1800143e0  mov     [rsp+108h+var_94], ebx
0x1800143e4  jmp     loc_180014952
0x1800143e9  mov     ecx, [rsi+88h]
0x1800143ef  test    ecx, ecx
0x1800143f1  jnz     short loc_1800143F7
0x1800143f3  mov     eax, edi
0x1800143f5  jmp     short loc_180014408
0x1800143f7  mov     eax, [rsi+80h]
0x1800143fd  add     eax, 3D7h
0x180014402  add     eax, ecx
0x180014404  neg     ecx
0x180014406  and     eax, ecx
0x180014408  mov     [rsp+108h+var_50], rax
0x180014410  cmp     [rsi+84h], ebx
0x180014416  jnb     short loc_18001441F
0x180014418  mov     ebx, 7Ah ; 'z'
0x18001441d  jmp     short loc_1800143E0
0x18001441f  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180014426  test    r12, r12
0x180014429  jz      short loc_18001443D
0x18001442b  cmp     rax, [r12]
0x18001442f  jnz     short loc_18001443D
0x180014431  lea     r14, [rsi+0A0h]
0x180014438  jmp     loc_1800144CA
0x18001443d  lea     r14, [rsi+0A0h]
0x180014444  mov     rdx, [r14]
0x180014447  test    rdx, rdx
0x18001444a  jz      short loc_18001449A
0x18001444c  mov     qword ptr [rsp+108h+var_80], rax
0x180014454  mov     [rsp+108h+var_90], rdi
0x180014459  lea     r9, [rsp+108h+var_80]; union _CLS_LSN *
0x180014461  lea     r8, [rsp+108h+var_90]; struct _CLFS_RECORD_HEADER **
0x180014466  mov     rdx, [rdx+40h]; unsigned __int8 *
0x18001446a  mov     rcx, r12; union _CLS_LSN *
0x18001446d  call    ?ClfsFindLsnInBlock@@YAKAEBT_CLS_LSN@@PEAEAEAPEAU_CLFS_RECORD_HEADER@@AEAT1@@Z; ClfsFindLsnInBlock(_CLS_LSN const &,uchar *,_CLFS_RECORD_HEADER * &,_CLS_LSN &)
0x180014472  test    r12, r12
0x180014475  jz      short loc_180014485
0x180014477  mov     rax, qword ptr [rsp+108h+var_80]
0x18001447f  cmp     [r12], rax
0x180014483  jz      short loc_18001448A
0x180014485  mov     [rsp+108h+var_90], rdi
0x18001448a  cmp     [rsp+108h+var_90], rdi
0x18001448f  cmovnz  r13d, edi
0x180014493  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001449a  test    r13d, r13d
0x18001449d  jz      short loc_1800144CA
0x18001449f  mov     rdx, r12; union _CLS_LSN *
0x1800144a2  mov     rcx, rsi; this
0x1800144a5  call    ?ValidateLogBase@CClfsMarshallingContext@@AEAAKAEBT_CLS_LSN@@@Z; CClfsMarshallingContext::ValidateLogBase(_CLS_LSN const &)
0x1800144aa  mov     ebx, eax
0x1800144ac  test    eax, eax
0x1800144ae  jz      short loc_1800144B9
0x1800144b0  mov     [rsp+108h+var_94], eax
0x1800144b4  jmp     loc_18001494B
0x1800144b9  mov     r13d, edi
0x1800144bc  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1800144c3  mov     ebx, dword ptr [rsp+108h+arg_8+8]
0x1800144ca  mov     r10, [r14]
0x1800144cd  test    r10, r10
0x1800144d0  jz      loc_1800145AC
0x1800144d6  mov     r8d, [r10+48h]
0x1800144da  lea     edx, [rbx+7]
0x1800144dd  mov     r11d, 0FFFFFFF8h
0x1800144e3  and     edx, r11d
0x1800144e6  add     edx, 28h ; '('
0x1800144e9  add     edx, r8d
0x1800144ec  or      r9d, 0FFFFFFFFh
0x1800144f0  cmp     edx, r8d
0x1800144f3  cmovnb  r9d, edx
0x1800144f7  sbb     ecx, ecx
0x1800144f9  and     ecx, 80070216h
0x1800144ff  mov     [rsp+108h+var_94], ecx
0x180014503  cmp     edx, r8d
0x180014506  jnb     short loc_18001451D
0x180014508  mov     ebx, 57h ; 'W'
0x18001450d  mov     [rsp+108h+var_94], ebx
0x180014511  lea     r14, [rsi+120h]
0x180014518  jmp     loc_180014959
0x18001451d  mov     r8d, r9d
0x180014520  mov     [rsp+108h+var_88], edi
0x180014527  mov     eax, 80808081h
0x18001452c  mul     r9d
0x18001452f  shr     edx, 8
0x180014532  mov     [rsp+108h+var_88], edx
0x180014539  imul    eax, edx, 1FEh
0x18001453f  cmp     r9d, eax
0x180014542  jz      short loc_18001454D
0x180014544  inc     edx
0x180014546  mov     [rsp+108h+var_88], edx
0x18001454d  mov     eax, [rsi+88h]
0x180014553  test    eax, eax
0x180014555  jnz     short loc_18001455C
0x180014557  mov     rax, rdi
0x18001455a  jmp     short loc_180014578
0x18001455c  lea     ecx, [rax-1]
0x18001455f  mov     eax, edx
0x180014561  lea     rax, ds:7[rax*2]
0x180014569  and     rax, r11
0x18001456c  add     rax, rcx
0x18001456f  add     rax, r8
0x180014572  not     rcx
0x180014575  and     rax, rcx
0x180014578  cmp     eax, [rsi+84h]
0x18001457e  ja      short loc_18001458E
0x180014580  mov     eax, [r10+4Ch]
0x180014584  add     eax, r15d
0x180014587  test    eax, 0FFFFFE00h
0x18001458c  jz      short loc_1800145AC
0x18001458e  xor     r9d, r9d; struct _OVERLAPPED *
0x180014591  xor     r8d, r8d; unsigned int
0x180014594  xor     edx, edx; unsigned __int8
0x180014596  mov     rcx, rsi; this
0x180014599  call    ?AppendWriteBlockToFlushQueue@CClfsMarshallingContext@@AEAAKEKPEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong,_OVERLAPPED *)
0x18001459e  mov     ebx, eax
0x1800145a0  mov     [rsp+108h+var_94], eax
0x1800145a4  test    eax, eax
0x1800145a6  jnz     loc_18001494B
0x1800145ac  cmp     [r14], rdi
0x1800145af  jnz     loc_18001463F
0x1800145b5  mov     r8, r14
0x1800145b8  mov     edx, r15d
0x1800145bb  mov     rcx, rsi
0x1800145be  call    ?AllocateIocb@CClfsMarshallingContext@@AEAAKW4_LOGIOCB_TYPE@1@AEAPEAVCLogIocb@@@Z; CClfsMarshallingContext::AllocateIocb(CClfsMarshallingContext::_LOGIOCB_TYPE,CLogIocb * &)
0x1800145c3  mov     ebx, eax
0x1800145c5  mov     [rsp+108h+var_94], eax
0x1800145c9  test    eax, eax
0x1800145cb  jnz     loc_18001494B
0x1800145d1  mov     rax, [r14]
0x1800145d4  mov     [rsp+108h+var_90], rax
0x1800145d9  test    rax, rax
0x1800145dc  jz      loc_18001494B
0x1800145e2  mov     ebx, [rsi+80h]
0x1800145e8  mov     rdi, [rax+40h]
0x1800145ec  xor     edx, edx; Val
0x1800145ee  lea     r8d, [rdx+70h]; Size
0x1800145f2  mov     rcx, rdi; void *
0x1800145f5  call    memset_0
0x1800145fa  mov     byte ptr [rdi], 15h
0x1800145fd  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180014604  mov     [rdi+18h], rax
0x180014608  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x18001460f  mov     [rdi+20h], rax
0x180014613  mov     dword ptr [rdi+28h], 70h ; 'p'
0x18001461a  lea     rax, [rbx-28h]
0x18001461e  shr     rax, 9
0x180014622  mov     [rdi+6], ax
0x180014626  mov     [rdi+4], ax
0x18001462a  mov     rax, [rsp+108h+var_90]
0x18001462f  mov     dword ptr [rax+48h], 70h ; 'p'
0x180014636  mov     dword ptr [rdi+28h], 0
0x18001463d  xor     edi, edi
0x18001463f  mov     rax, qword ptr [rsp+108h+arg_8]
0x180014647  mov     [rsp+108h+var_60.Buffer], rax
0x18001464f  mov     eax, dword ptr [rsp+108h+arg_8+8]
0x180014656  mov     [rsp+108h+var_60.ByteLength], eax
0x18001465d  mov     rcx, [r14]; this
0x180014660  mov     rax, [rcx+50h]
0x180014664  mov     [rsp+108h+var_48], rax
0x18001466c  mov     eax, [rcx+48h]
0x18001466f  mov     dword ptr [rsp+108h+var_80], eax
0x180014676  lea     rdx, [rsp+108h+var_68]; struct _CLFS_RECORD_HEADER **
0x18001467e  call    ?GetLastRecord@CLogIocb@@QEAAKAEAPEAU_CLFS_RECORD_HEADER@@@Z; CLogIocb::GetLastRecord(_CLFS_RECORD_HEADER * &)
0x180014683  mov     eax, [rsi+98h]
0x180014689  mov     dword ptr [rsp+108h+var_90], eax
0x18001468d  mov     rax, [rsi+0B0h]
0x180014694  mov     [rsp+108h+var_40], rax
0x18001469c  lea     rcx, [rsp+108h+arg_38]
0x1800146a4  mov     [rsp+108h+var_B8], rcx; unsigned int *
0x1800146a9  lea     rax, [rsp+108h+var_78]
0x1800146b1  mov     [rsp+108h+var_C0], rax; unsigned int *
0x1800146b6  lea     rax, [rsp+108h+var_74]
0x1800146be  mov     [rsp+108h+var_C8], rax; unsigned int *
0x1800146c3  lea     rax, [rsp+108h+var_70]
0x1800146cb  mov     [rsp+108h+var_D0], rax; struct _CLFS_RECORD_HEADER **
0x1800146d0  mov     eax, dword ptr [rsp+108h+arg_20]
0x1800146d7  mov     dword ptr [rsp+108h+var_D8], eax; char
0x1800146db  mov     [rsp+108h+var_E0], rdi; __int64 *
0x1800146e0  mov     dword ptr [rsp+108h+var_E8], edi; unsigned int
0x1800146e4  mov     r9d, r15d; unsigned int
0x1800146e7  mov     r8d, r15d; unsigned int
0x1800146ea  lea     rdx, [rsp+108h+var_60]; struct _CLS_WRITE_ENTRY *
0x1800146f2  mov     rcx, rsi; this
0x1800146f5  call    ?AppendRecord@CClfsMarshallingContext@@AEAAKPEAU_CLS_WRITE_ENTRY@@KKKQEA_JKAEAPEAU_CLFS_RECORD_HEADER@@AEAK33@Z; CClfsMarshallingContext::AppendRecord(_CLS_WRITE_ENTRY *,ulong,ulong,ulong,__int64 * const,ulong,_CLFS_RECORD_HEADER * &,ulong &,ulong &,ulong &)
0x1800146fa  mov     ebx, eax
0x1800146fc  mov     [rsp+108h+var_94], eax
0x180014700  test    eax, eax
0x180014702  jz      short loc_18001471B
0x180014704  cmp     eax, 0EAh
0x180014709  jnz     loc_18001494B
0x18001470f  lea     ebx, [rax-70h]
0x180014712  mov     [rsp+108h+var_94], ebx
0x180014716  jmp     loc_18001494B
0x18001471b  mov     r9, [rsp+108h+var_70]; struct _CLFS_RECORD_HEADER *
0x180014723  or      byte ptr [r9+24h], 2
0x180014728  mov     rax, [rsi+0E0h]
0x18001472f  mov     [r9+10h], rax
0x180014733  mov     eax, dword ptr [rsp+108h+arg_38]
0x18001473a  mov     rbx, qword ptr [rsp+108h+arg_28]
0x180014742  add     [rbx], eax
0x180014744  mov     rax, [r14]
0x180014747  or      word ptr [rax+1Ch], 8
0x18001474c  mov     rax, [r12]
0x180014750  mov     qword ptr [rsp+108h+arg_28], rax
0x180014758  mov     rdx, [r14]
0x18001475b  mov     rdi, [rdx+40h]
0x18001475f  mov     r8d, [rsi+88h]; unsigned int
0x180014766  mov     edx, [rdx+48h]; unsigned int
0x180014769  mov     rcx, rdi; struct _CLFS_LOG_BLOCK_HEADER *
0x18001476c  call    ?ClfsStampLogBlock@@YAXPEAU_CLFS_LOG_BLOCK_HEADER@@KKPEAU_CLFS_RECORD_HEADER@@@Z; ClfsStampLogBlock(_CLFS_LOG_BLOCK_HEADER *,ulong,ulong,_CLFS_RECORD_HEADER *)
0x180014771  mov     r9, [r9]
0x180014774  mov     r10, qword ptr [rsp+108h+arg_30]
0x18001477c  mov     [r10], r9
0x18001477f  mov     r8, [r14]
0x180014782  lea     rcx, [rsi+0C0h]
0x180014789  lea     rdx, [r8+50h]
0x18001478d  movzx   r9d, word ptr [rdi+4]
0x180014792  shl     r9d, 9; unsigned int
0x180014796  mov     [rsp+108h+var_B0], r13d; unsigned int
0x18001479b  mov     rax, [r8+38h]
0x18001479f  mov     [rsp+108h+var_B8], rax; void *
0x1800147a4  mov     [rsp+108h+var_C0], rbx; unsigned int *
0x1800147a9  lea     rax, [rsp+108h+arg_28]
0x1800147b1  mov     [rsp+108h+var_C8], rax; union _CLS_LSN *
0x1800147b6  mov     [rsp+108h+var_D0], r10; union _CLS_LSN *
0x1800147bb  lea     rax, [rsp+108h+var_50]
0x1800147c3  mov     [rsp+108h+var_D8], rax; __int64 *
0x1800147c8  mov     [rsp+108h+var_E0], rcx; __int64 *
0x1800147cd  mov     [rsp+108h+var_E8], rdx; __int64 *
0x1800147d2  mov     r8, [r8+40h]; void *
0x1800147d6  mov     rdx, r12; union _CLS_LSN *
0x1800147d9  mov     rcx, [rsi+30h]; void *
0x1800147dd  call    ?NtWriteLogRestartAreaInternal@@YAKPEAXPEAT_CLS_LSN@@0KQEA_JPEA_J211PEAK0KPEAU_OVERLAPPED@@@Z; NtWriteLogRestartAreaInternal(void *,_CLS_LSN *,void *,ulong,__int64 * const,__int64 *,__int64 * const,_CLS_LSN *,_CLS_LSN *,ulong *,void *,ulong,_OVERLAPPED *)
0x1800147e2  mov     ebx, eax
0x1800147e4  mov     [rsp+108h+var_94], eax
0x1800147e8  xor     r12d, r12d
0x1800147eb  test    eax, eax
0x1800147ed  jnz     loc_18001488F
0x1800147f3  mov     rax, [rsi+0B0h]
0x1800147fa  mov     [rsi+0B8h], rax
0x180014801  lea     rdx, [rsi+0C8h]
0x180014808  mov     ecx, dword ptr [rsp+108h+arg_28+4]
0x18001480f  test    rdx, rdx
0x180014812  jz      short loc_18001482B
0x180014814  cmp     ecx, [rdx+4]
0x180014817  jb      short loc_18001483D
0x180014819  jnz     short loc_180014826
0x18001481b  mov     eax, [rdx]
0x18001481d  cmp     dword ptr [rsp+108h+arg_28], eax
  ... truncated ...
```
