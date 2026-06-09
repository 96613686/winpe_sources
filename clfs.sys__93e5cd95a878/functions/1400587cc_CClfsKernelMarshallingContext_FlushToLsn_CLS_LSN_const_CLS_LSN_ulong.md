# CClfsKernelMarshallingContext::FlushToLsn(_CLS_LSN const &,_CLS_LSN &,ulong)

- ea: `0x1400587cc`
- end: `0x140058c60`
- name: `?FlushToLsn@CClfsKernelMarshallingContext@@QEAAJAEBT_CLS_LSN@@AEAT2@K@Z`
- size: `1172`
- prototype: `__int64 __fastcall(CClfsKernelMarshallingContext *__hidden this, const union _CLS_LSN *, union _CLS_LSN *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140058c70`
- `0x14006e500`

## callees

- `0x140005840`
- `0x14000a340`
- `0x14000bf48`
- `0x14000ed64`
- `0x140055440`
- `0x1400572a0`
- `0x1400577c0`
- `0x1400587cc`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005885f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140058957`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005885f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140058957`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140058bf5`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140058c18`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140058bf5`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140058c18`
- `ntoskrnl!KeBugCheckEx` at `0x140058bbc`
- `ntoskrnl!KeBugCheckEx` at `0x140058bbc`

## pseudocode

```c
__int64 __fastcall CClfsKernelMarshallingContext::FlushToLsn(
        CClfsKernelMarshallingContext *this,
        const union _CLS_LSN *a2,
        union _CLS_LSN *a3,
        unsigned int a4)
{
  CLFS_RECORD_INDEX v8; // eax
  BOOLEAN v9; // r13
  ULONGLONG ullOffset; // rdx
  union _CLS_LSN v11; // rcx
  union _CLS_LSN *v12; // r14
  union _CLS_LSN *v13; // rbx
  char v14; // al
  int v15; // esi
  union _CLS_LSN v16; // rcx
  char v17; // al
  int v18; // ebx
  union _CLS_LSN *v19; // rbx
  char v20; // al
  CClfsKernelMarshallingContext *v21; // r14
  _QWORD *v22; // rdx
  ULONG_PTR v23; // r8
  CClfsKernelMarshallingContext *v24; // r10
  CClfsKernelMarshallingContext *v25; // r11
  __int64 v26; // rax
  char v27; // al
  CClfsKernelMarshallingContext **v28; // rax
  BOOLEAN v30; // [rsp+30h] [rbp-58h]
  int v31; // [rsp+38h] [rbp-50h] BYREF
  union _CLS_LSN v32; // [rsp+40h] [rbp-48h] BYREF
  union _CLS_LSN v33; // [rsp+48h] [rbp-40h] BYREF
  union _CLS_LSN v34; // [rsp+50h] [rbp-38h] BYREF

  v32 = CLFS_LSN_NULL;
  v34 = CLFS_LSN_INVALID;
  v33 = CLFS_LSN_INVALID;
  v31 = 0;
  if ( a2 && CLFS_LSN_INVALID.ullOffset == a2->ullOffset )
    return 3221225485LL;
  v8 = -1;
  if ( a2 )
    v8 = a2->offset.idxRecord & 0xFFFFFE00;
  if ( v8 % *((_DWORD *)this + 17) )
    return 3221225485LL;
  v9 = 0;
  if ( !*((_DWORD *)this + 16) )
    return 0;
  v30 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 17), 1u);
  ullOffset = a2->ullOffset;
  v32.ullOffset = ullOffset;
  v11 = CLFS_LSN_NULL;
  v12 = (union _CLS_LSN *)((char *)this + 104);
  if ( CLFS_LSN_NULL.ullOffset == ullOffset )
  {
    ullOffset = v12->ullOffset;
    v32 = *v12;
  }
  if ( this == (CClfsKernelMarshallingContext *)-104LL )
  {
    v14 = 0;
    v13 = 0;
  }
  else
  {
    ullOffset >>= 32;
    v13 = (union _CLS_LSN *)((char *)this + 104);
    if ( (unsigned int)ullOffset > *((_DWORD *)this + 27) )
      goto LABEL_16;
    if ( (_DWORD)ullOffset == *((_DWORD *)this + 27) )
    {
      if ( v32.offset.idxRecord >= v12->offset.idxRecord )
        goto LABEL_16;
      v13 = (union _CLS_LSN *)((char *)this + 104);
    }
    v14 = 1;
  }
  if ( v14 )
  {
    CClfsKernelMarshallingContext::FindFlushQLsnUpperBound(this, &v32, &v34, &v33);
    if ( CLFS_LSN_INVALID.ullOffset != v33.ullOffset )
      v32 = v33;
    v11 = CLFS_LSN_NULL;
    goto LABEL_49;
  }
LABEL_16:
  if ( *((_QWORD *)this + 16) )
  {
    v15 = CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(this, ullOffset, 2);
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          19,
          (unsigned int)WPP_3dc8eff30e5c308205752052206957b1_Traceguids,
          (unsigned int)"CClfsKernelMarshallingContext::FlushToLsn",
          79,
          v15);
      }
    }
    else
    {
      *a3 = *(union _CLS_LSN *)((char *)this + 112);
    }
    goto LABEL_19;
  }
LABEL_49:
  if ( v13 )
  {
    if ( v32.ullOffset <= v13->ullOffset )
      goto LABEL_51;
    v17 = 1;
  }
  else
  {
    v17 = 0;
  }
  if ( v17 )
  {
LABEL_21:
    v32 = v11;
    v18 = a4 & 2;
    goto LABEL_22;
  }
LABEL_51:
  if ( v11.ullOffset == a2->ullOffset )
    goto LABEL_21;
  v18 = a4 & 2;
  if ( (a4 & 2) != 0 )
    goto LABEL_21;
LABEL_22:
  ClfsReleaseResourceLite(*((_QWORD *)this + 17));
  v30 = 0;
  v15 = ClfsFlushToLsnInternal(*((_QWORD *)this + 1), a4, &v32, &v31);
  if ( v15 < 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
  {
    WPP_SF_slD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      20,
      (unsigned int)WPP_3dc8eff30e5c308205752052206957b1_Traceguids,
      (unsigned int)"CClfsKernelMarshallingContext::FlushToLsn",
      121,
      v15);
  }
  if ( v15 >= 0 || v18 )
  {
    v9 = ExAcquireResourceExclusiveLite(*((PERESOURCE *)this + 18), 1u);
    if ( v15 < 0 && v18 )
    {
      v19 = (union _CLS_LSN *)((char *)this + 112);
      *((union _CLS_LSN *)this + 14) = *v12;
      goto LABEL_30;
    }
    v19 = (union _CLS_LSN *)((char *)this + 112);
    if ( this == (CClfsKernelMarshallingContext *)-112LL )
    {
      v20 = 0;
    }
    else
    {
      if ( *((_QWORD *)this + 14) >= v32.ullOffset )
      {
LABEL_30:
        *a3 = *v19;
        v21 = (CClfsKernelMarshallingContext *)*((_QWORD *)this + 19);
        v16 = CLFS_LSN_INVALID;
        while ( 1 )
        {
          if ( v21 == (CClfsKernelMarshallingContext *)((char *)this + 152) )
            goto LABEL_71;
          v22 = (_QWORD *)((char *)v21 - 136);
          v23 = *((_QWORD *)this + 16);
          if ( (CClfsKernelMarshallingContext *)v23 == (CClfsKernelMarshallingContext *)((char *)v21 - 136) )
            KeBugCheckEx(0xC1F5u, 0x41u, v23, (ULONG_PTR)v21 - 136, (ULONG_PTR)this);
          v24 = v21;
          v25 = *(CClfsKernelMarshallingContext **)v21;
          v21 = *(CClfsKernelMarshallingContext **)v21;
          v26 = v22[1];
          if ( v26 == -24 || !v19 )
            break;
          if ( *(_QWORD *)(v26 + 24) < v19->ullOffset )
          {
            v27 = 1;
            goto LABEL_37;
          }
LABEL_44:
          if ( v19 && v16.ullOffset == v19->ullOffset )
          {
LABEL_38:
            if ( *((CClfsKernelMarshallingContext **)v25 + 1) != v24
              || (v28 = (CClfsKernelMarshallingContext **)*((_QWORD *)v24 + 1), *v28 != v24) )
            {
              __fastfail(3u);
            }
            *v28 = v25;
            *((_QWORD *)v25 + 1) = v28;
            CClfsKernelMarshallingContext::DeallocateIocb(this, v22);
            _InterlockedDecrement((volatile signed __int32 *)this + 10);
            v16 = CLFS_LSN_INVALID;
          }
        }
        v27 = 0;
LABEL_37:
        if ( v27 )
          goto LABEL_38;
        goto LABEL_44;
      }
      v20 = 1;
    }
    if ( v20 )
      *v19 = v32;
    goto LABEL_30;
  }
LABEL_19:
  v16 = CLFS_LSN_INVALID;
LABEL_71:
  if ( v15 == -1072037848 || v15 == -1072037845 )
  {
    v33 = v16;
    CClfsKernelMarshallingContext::ReleaseFlushElements(this, &v33);
  }
  if ( v9 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 18), (ERESOURCE_THREAD)KeGetCurrentThread());
  if ( v30 )
    ExReleaseResourceForThreadLite(*((PERESOURCE *)this + 17), (ERESOURCE_THREAD)KeGetCurrentThread());
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400587cc  mov     r11, rsp
0x1400587cf  mov     [r11+10h], rbx
0x1400587d3  mov     [r11+18h], rsi
0x1400587d7  mov     [r11+8], rcx
0x1400587db  push    rdi
0x1400587dc  push    r12
0x1400587de  push    r13
0x1400587e0  push    r14
0x1400587e2  push    r15
0x1400587e4  sub     rsp, 60h
0x1400587e8  mov     r15d, r9d
0x1400587eb  mov     r12, r8
0x1400587ee  mov     rsi, rdx
0x1400587f1  mov     rdi, rcx
0x1400587f4  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1400587fb  mov     [r11-48h], rax
0x1400587ff  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140058806  mov     [r11-38h], rax
0x14005880a  mov     [r11-40h], rax
0x14005880e  xor     ebx, ebx
0x140058810  mov     [rsp+88h+var_50], ebx
0x140058814  test    rdx, rdx
0x140058817  jz      short loc_140058822
0x140058819  cmp     rax, [rdx]
0x14005881c  jz      loc_140058C41
0x140058822  or      eax, 0FFFFFFFFh
0x140058825  test    rsi, rsi
0x140058828  jz      short loc_140058831
0x14005882a  mov     eax, [rdx]
0x14005882c  and     eax, 0FFFFFE00h
0x140058831  xor     edx, edx
0x140058833  div     dword ptr [rcx+44h]
0x140058836  test    edx, edx
0x140058838  jnz     loc_140058C41
0x14005883e  mov     [rsp+88h+var_54], ebx
0x140058842  mov     [rsp+88h+var_58], bl
0x140058846  mov     r13b, bl
0x140058849  mov     [rsp+88h+var_57], bl
0x14005884d  cmp     [rcx+40h], ebx
0x140058850  jz      loc_140058C48
0x140058856  mov     dl, 1; Wait
0x140058858  mov     rcx, [rcx+88h]; Resource
0x14005885f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140058866  nop     dword ptr [rax+rax+00h]
0x14005886b  mov     [rsp+88h+var_58], al
0x14005886f  mov     rdx, [rsi]
0x140058872  mov     qword ptr [rsp+88h+var_48], rdx
0x140058877  mov     rcx, qword ptr cs:CLFS_LSN_NULL
0x14005887e  lea     r14, [rdi+68h]
0x140058882  cmp     rcx, rdx
0x140058885  jnz     short loc_14005888F
0x140058887  mov     rdx, [r14]
0x14005888a  mov     qword ptr [rsp+88h+var_48], rdx
0x14005888f  test    r14, r14
0x140058892  jz      loc_140058AD3
0x140058898  shr     rdx, 20h; unsigned __int8
0x14005889c  mov     rbx, r14
0x14005889f  cmp     edx, [r14+4]
0x1400588a3  ja      short loc_1400588BE
0x1400588a5  jnz     short loc_1400588B4
0x1400588a7  mov     eax, [r14]
0x1400588aa  cmp     dword ptr [rsp+88h+var_48], eax
0x1400588ae  jnb     short loc_1400588BE
0x1400588b0  lea     rbx, [rdi+68h]
0x1400588b4  mov     al, 1
0x1400588b6  test    al, al
0x1400588b8  jnz     loc_140058AA0
0x1400588be  cmp     qword ptr [rdi+80h], 0
0x1400588c6  jz      loc_140058A61
0x1400588cc  mov     r8d, 2; unsigned int
0x1400588d2  mov     rcx, rdi; this
0x1400588d5  call    ?AppendWriteBlockToFlushQueue@CClfsKernelMarshallingContext@@AEAAJEK@Z; CClfsKernelMarshallingContext::AppendWriteBlockToFlushQueue(uchar,ulong)
0x1400588da  mov     esi, eax
0x1400588dc  mov     [rsp+88h+var_54], eax
0x1400588e0  test    eax, eax
0x1400588e2  js      loc_140058ADD
0x1400588e8  mov     rcx, [rdi+70h]
0x1400588ec  mov     [r12], rcx
0x1400588f0  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x1400588f7  jmp     loc_140058BD0
0x1400588fc  mov     al, 1
0x1400588fe  test    al, al
0x140058900  jz      loc_140058A73
0x140058906  mov     qword ptr [rsp+88h+var_48], rcx
0x14005890b  mov     ebx, r15d
0x14005890e  and     ebx, 2
0x140058911  mov     rcx, [rdi+88h]
0x140058918  call    ClfsReleaseResourceLite
0x14005891d  mov     [rsp+88h+var_58], 0
0x140058922  lea     r9, [rsp+88h+var_50]
0x140058927  lea     r8, [rsp+88h+var_48]
0x14005892c  mov     edx, r15d
0x14005892f  mov     rcx, [rdi+8]
0x140058933  call    ClfsFlushToLsnInternal
0x140058938  mov     esi, eax
0x14005893a  mov     [rsp+88h+var_54], eax
0x14005893e  test    eax, eax
0x140058940  js      loc_140058B35
0x140058946  test    esi, esi
0x140058948  js      loc_140058A54
0x14005894e  mov     dl, 1; Wait
0x140058950  mov     rcx, [rdi+90h]; Resource
0x140058957  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005895e  nop     dword ptr [rax+rax+00h]
0x140058963  mov     r13b, al
0x140058966  mov     [rsp+88h+var_57], al
0x14005896a  test    esi, esi
0x14005896c  js      loc_140058B86
0x140058972  lea     rbx, [rdi+70h]
0x140058976  test    rbx, rbx
0x140058979  jz      loc_140058A41
0x14005897f  mov     eax, [rbx+4]
0x140058982  cmp     eax, dword ptr [rsp+88h+var_48+4]
0x140058986  ja      short loc_14005899C
0x140058988  jnz     short loc_140058992
0x14005898a  mov     eax, dword ptr [rsp+88h+var_48]
0x14005898e  cmp     [rbx], eax
0x140058990  jnb     short loc_14005899C
0x140058992  mov     al, 1
0x140058994  test    al, al
0x140058996  jnz     loc_140058B9D
0x14005899c  mov     rax, [rbx]
0x14005899f  mov     [r12], rax
0x1400589a3  lea     r15, [rdi+98h]
0x1400589aa  mov     r14, [r15]
0x1400589ad  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x1400589b4  cmp     r14, r15
0x1400589b7  jz      loc_140058BD0
0x1400589bd  lea     rdx, [r14-88h]; Entry
0x1400589c4  mov     r8, [rdi+80h]; BugCheckParameter2
0x1400589cb  cmp     r8, rdx
0x1400589ce  jz      loc_140058BAA
0x1400589d4  mov     r10, r14
0x1400589d7  mov     r11, [r14]
0x1400589da  mov     r14, r11
0x1400589dd  mov     rax, [rdx+8]
0x1400589e1  lea     r8, [rax+18h]
0x1400589e5  test    r8, r8
0x1400589e8  jz      short loc_140058A3D
0x1400589ea  test    rbx, rbx
0x1400589ed  jz      short loc_140058A3D
0x1400589ef  mov     eax, [rbx+4]
0x1400589f2  cmp     [r8+4], eax
0x1400589f6  ja      short loc_140058A48
0x1400589f8  jnz     short loc_140058A01
0x1400589fa  mov     eax, [rbx]
0x1400589fc  cmp     [r8], eax
0x1400589ff  jnb     short loc_140058A48
0x140058a01  mov     al, 1
0x140058a03  test    al, al
0x140058a05  jz      short loc_140058A48
0x140058a07  cmp     [r11+8], r10
0x140058a0b  jnz     loc_140058BC9
0x140058a11  mov     rax, [r10+8]
0x140058a15  cmp     [rax], r10
0x140058a18  jnz     loc_140058BC9
0x140058a1e  mov     [rax], r11
0x140058a21  mov     [r11+8], rax
0x140058a25  mov     rcx, rdi; this
0x140058a28  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140058a2d  lock dec dword ptr [rdi+28h]
0x140058a31  mov     rcx, qword ptr cs:CLFS_LSN_INVALID
0x140058a38  jmp     loc_1400589B4
0x140058a3d  xor     al, al
0x140058a3f  jmp     short loc_140058A03
0x140058a41  xor     al, al
0x140058a43  jmp     loc_140058994
0x140058a48  test    rbx, rbx
0x140058a4b  jz      short loc_140058A38
0x140058a4d  cmp     rcx, [rbx]
0x140058a50  jnz     short loc_140058A38
0x140058a52  jmp     short loc_140058A07
0x140058a54  test    ebx, ebx
0x140058a56  jnz     loc_14005894E
0x140058a5c  jmp     loc_1400588F0
0x140058a61  test    rbx, rbx
0x140058a64  jz      loc_140058B2E
0x140058a6a  mov     eax, [rbx+4]
0x140058a6d  cmp     dword ptr [rsp+88h+var_48+4], eax
0x140058a71  jnb     short loc_140058A8D
0x140058a73  cmp     rcx, [rsi]
0x140058a76  jz      loc_140058906
0x140058a7c  mov     ebx, r15d
0x140058a7f  and     ebx, 2
0x140058a82  jz      loc_140058911
0x140058a88  jmp     loc_140058906
0x140058a8d  jnz     loc_1400588FC
0x140058a93  mov     eax, [rbx]
0x140058a95  cmp     dword ptr [rsp+88h+var_48], eax
0x140058a99  jbe     short loc_140058A73
0x140058a9b  jmp     loc_1400588FC
0x140058aa0  lea     r9, [rsp+88h+var_40]; union _CLS_LSN *
0x140058aa5  lea     r8, [rsp+88h+var_38]; union _CLS_LSN *
0x140058aaa  lea     rdx, [rsp+88h+var_48]; union _CLS_LSN *
0x140058aaf  mov     rcx, rdi; this
0x140058ab2  call    ?FindFlushQLsnUpperBound@CClfsKernelMarshallingContext@@AEAAJAEBT_CLS_LSN@@AEAT2@1@Z; CClfsKernelMarshallingContext::FindFlushQLsnUpperBound(_CLS_LSN const &,_CLS_LSN &,_CLS_LSN &)
0x140058ab7  mov     rax, qword ptr [rsp+88h+var_40]
0x140058abc  cmp     qword ptr cs:CLFS_LSN_INVALID, rax
0x140058ac3  jz      short loc_140058ACA
0x140058ac5  mov     qword ptr [rsp+88h+var_48], rax
0x140058aca  mov     rcx, qword ptr cs:CLFS_LSN_NULL
0x140058ad1  jmp     short loc_140058A61
0x140058ad3  mov     al, bl
0x140058ad5  mov     rbx, r14
0x140058ad8  jmp     loc_1400588B6
0x140058add  lea     rax, WPP_GLOBAL_Control
0x140058ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x140058aeb  cmp     rcx, rax
0x140058aee  jz      loc_1400588F0
0x140058af4  mov     eax, [rcx+2Ch]
0x140058af7  bt      eax, 1Bh
0x140058afb  jnb     loc_1400588F0
0x140058b01  mov     edx, 13h
0x140058b06  mov     [rsp+88h+var_60], esi
0x140058b0a  mov     dword ptr [rsp+88h+BugCheckParameter4], 144Fh
0x140058b12  lea     r9, aCclfskernelmar_7; "CClfsKernelMarshallingContext::FlushToL"...
0x140058b19  lea     r8, WPP_3dc8eff30e5c308205752052206957b1_Traceguids
0x140058b20  mov     rcx, [rcx+18h]
0x140058b24  call    WPP_SF_slD
0x140058b29  jmp     loc_1400588F0
0x140058b2e  xor     al, al
0x140058b30  jmp     loc_1400588FE
0x140058b35  lea     rax, WPP_GLOBAL_Control
0x140058b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140058b43  cmp     rcx, rax
0x140058b46  jz      loc_140058946
0x140058b4c  mov     eax, [rcx+2Ch]
0x140058b4f  bt      eax, 1Bh
0x140058b53  jnb     loc_140058946
0x140058b59  mov     edx, 14h
0x140058b5e  mov     [rsp+88h+var_60], esi
0x140058b62  mov     dword ptr [rsp+88h+BugCheckParameter4], 1479h
0x140058b6a  lea     r9, aCclfskernelmar_7; "CClfsKernelMarshallingContext::FlushToL"...
0x140058b71  lea     r8, WPP_3dc8eff30e5c308205752052206957b1_Traceguids
0x140058b78  mov     rcx, [rcx+18h]
0x140058b7c  call    WPP_SF_slD
0x140058b81  jmp     loc_140058946
0x140058b86  test    ebx, ebx
0x140058b88  jz      loc_140058972
0x140058b8e  lea     rbx, [rdi+70h]
0x140058b92  mov     rcx, [r14]
0x140058b95  mov     [rbx], rcx
0x140058b98  jmp     loc_14005899C
0x140058b9d  mov     rax, qword ptr [rsp+88h+var_48]
0x140058ba2  mov     [rbx], rax
0x140058ba5  jmp     loc_14005899C
0x140058baa  mov     [rsp+88h+BugCheckParameter4], rdi; BugCheckParameter4
0x140058baf  mov     r9, rdx; BugCheckParameter3
0x140058bb2  mov     edx, 41h ; 'A'; BugCheckParameter1
0x140058bb7  mov     ecx, 0C1F5h; BugCheckCode
0x140058bbc  call    cs:__imp_KeBugCheckEx
0x140058bc9  mov     ecx, 3
0x140058bce  int     29h; Win8: RtlFailFast(ecx)
0x140058bd0  cmp     esi, 0C01A0028h
0x140058bd6  jz      short loc_140058C4C
0x140058bd8  cmp     esi, 0C01A002Bh
0x140058bde  jz      short loc_140058C4C
0x140058be0  test    r13b, r13b
0x140058be3  jz      short loc_140058C01
0x140058be5  mov     rdx, gs:188h; ResourceThreadId
0x140058bee  mov     rcx, [rdi+90h]; Resource
0x140058bf5  call    cs:__imp_ExReleaseResourceForThreadLite
0x140058bfc  nop     dword ptr [rax+rax+00h]
0x140058c01  cmp     [rsp+88h+var_58], 0
0x140058c06  jz      short loc_140058C24
0x140058c08  mov     rdx, gs:188h; ResourceThreadId
0x140058c11  mov     rcx, [rdi+88h]; Resource
0x140058c18  call    cs:__imp_ExReleaseResourceForThreadLite
0x140058c1f  nop     dword ptr [rax+rax+00h]
0x140058c24  mov     eax, esi
0x140058c26  lea     r11, [rsp+88h+var_28]
0x140058c2b  mov     rbx, [r11+38h]
0x140058c2f  mov     rsi, [r11+40h]
0x140058c33  mov     rsp, r11
0x140058c36  pop     r15
0x140058c38  pop     r14
0x140058c3a  pop     r13
0x140058c3c  pop     r12
0x140058c3e  pop     rdi
0x140058c3f  retn
0x140058c41  mov     eax, 0C000000Dh
0x140058c46  jmp     short loc_140058C26
0x140058c48  xor     eax, eax
0x140058c4a  jmp     short loc_140058C26
0x140058c4c  mov     qword ptr [rsp+88h+var_40], rcx
0x140058c51  lea     rdx, [rsp+88h+var_40]; union _CLS_LSN *
0x140058c56  mov     rcx, rdi; this
0x140058c59  call    ?ReleaseFlushElements@CClfsKernelMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z; CClfsKernelMarshallingContext::ReleaseFlushElements(_CLS_LSN &)
0x140058c5e  jmp     short loc_140058BE0
0x140079b25  push    rbp
0x140079b27  sub     rsp, 30h
0x140079b2b  mov     rbp, rdx
0x140079b2e  cmp     dword ptr [rbp+34h], 0C01A0028h
0x140079b35  jz      short loc_140079B40
0x140079b37  cmp     dword ptr [rbp+34h], 0C01A002Bh
0x140079b3e  jnz     short loc_140079B5C
0x140079b40  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140079b47  mov     [rbp+48h], rax
0x140079b4b  lea     rdx, [rbp+48h]; union _CLS_LSN *
0x140079b4f  mov     rcx, [rbp+90h]; this
  ... truncated ...
```
