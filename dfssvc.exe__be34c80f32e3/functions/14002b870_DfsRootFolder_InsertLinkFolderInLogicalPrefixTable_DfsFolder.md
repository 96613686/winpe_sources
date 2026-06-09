# DfsRootFolder::InsertLinkFolderInLogicalPrefixTable(DfsFolder *)

- ea: `0x14002b870`
- end: `0x14002bbe9`
- name: `?InsertLinkFolderInLogicalPrefixTable@DfsRootFolder@@QEAAKPEAVDfsFolder@@@Z`
- size: `889`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this, struct DfsFolder *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400293c4`

## callees

- `0x1400011c4`
- `0x14000abc4`
- `0x140015f64`
- `0x140029df4`
- `0x14002b870`
- `0x1400324c8`
- `0x140032600`
- `0x140032874`
- `0x14005b158`
- `0x14005b2d0`
- `0x14005b648`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x14002b927`
- `ntdll!RtlCompareUnicodeString` at `0x14002b927`
- `ntdll!RtlNtStatusToDosError` at `0x14002ba2f`
- `ntdll!RtlNtStatusToDosError` at `0x14002ba2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002b8c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002b8c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002bbb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002bbb3`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::InsertLinkFolderInLogicalPrefixTable(DfsRootFolder *this, struct DfsFolder *a2)
{
  __int64 v2; // rbx
  ULONG v3; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rcx
  unsigned __int16 *v7; // r14
  __int64 v8; // rcx
  int v9; // r8d
  DfsGeneric *v10; // rbx
  int v11; // r8d
  unsigned __int16 *v12; // rax
  unsigned __int16 v13; // dx
  unsigned int v14; // ecx
  NTSTATUS v15; // eax
  unsigned __int16 *v16; // rax
  unsigned __int16 *RootNameString; // rax
  __int64 v18; // rcx
  _BYTE v20[8]; // [rsp+50h] [rbp-29h] BYREF
  DfsGeneric *v21; // [rsp+58h] [rbp-21h] BYREF
  __int128 v22; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v23[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v24; // [rsp+80h] [rbp+7h]
  __int64 v25; // [rsp+88h] [rbp+Fh]

  v2 = *((_QWORD *)this + 32);
  v3 = 0;
  v20[0] = 0;
  v21 = 0;
  v22 = 0;
  v5 = *(struct _RTL_CRITICAL_SECTION **)(v2 + 24);
  v7 = 0;
  *(_OWORD *)v23 = 0;
  EnterCriticalSection(v5);
  ++*(_DWORD *)(v2 + 16);
  v8 = *((_QWORD *)this + 32);
  v22 = *((_OWORD *)a2 + 5);
  if ( (unsigned int)DfsFindUnicodePrefixLocked(
                       v8,
                       (unsigned int)&v22,
                       (unsigned int)v23,
                       (unsigned int)&v21,
                       (__int64)v20) )
  {
    if ( !v20[0] )
      goto LABEL_15;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x80000020) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_ZZZ(
        *((_QWORD *)pWppControl + 2),
        (unsigned int)&v22,
        v9,
        (_DWORD)this + 432,
        (__int64)this + 296,
        (__int64)&v22);
    }
    RootNameString = (unsigned __int16 *)DfspCreateRootNameString(
                                           (const struct _UNICODE_STRING *)this + 27,
                                           (const struct _UNICODE_STRING *)((char *)this + 296));
    v7 = RootNameString;
    if ( !RootNameString )
      goto LABEL_12;
    v23[0] = RootNameString;
    v13 = 2;
    v23[1] = *((unsigned __int16 **)a2 + 11);
    v14 = -1073727279;
LABEL_11:
    DfsLogDfsEvent(v14, v13, (const unsigned __int16 **const)v23, 0);
LABEL_12:
    v3 = 183;
    goto LABEL_34;
  }
  v10 = v21;
  if ( LOWORD(v23[0]) )
  {
    if ( (*((_BYTE *)v21 + 52) & 4) != 0 )
      goto LABEL_12;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x80000020) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_ZZZZZZ(
        *((_QWORD *)pWppControl + 2),
        (_DWORD)this + 296,
        v9,
        (_DWORD)this + 432,
        (__int64)this + 296,
        (__int64)&v22,
        (__int64)this + 432,
        (__int64)this + 296,
        (__int64)v21 + 80);
    }
    v16 = (unsigned __int16 *)DfspCreateRootNameString(
                                (const struct _UNICODE_STRING *)this + 27,
                                (const struct _UNICODE_STRING *)((char *)this + 296));
    v7 = v16;
    if ( !v16 )
      goto LABEL_12;
    v23[0] = v16;
    v13 = 3;
    v23[1] = *((unsigned __int16 **)a2 + 11);
    v14 = -1073727280;
    v24 = *((_QWORD *)v10 + 11);
    goto LABEL_11;
  }
  if ( RtlCompareUnicodeString((PCUNICODE_STRING)v21 + 4, (PCUNICODE_STRING)a2 + 4, 1u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x80000020) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_ZZZZZ(
        *((_QWORD *)pWppControl + 2),
        (_DWORD)this + 296,
        v11,
        (_DWORD)this + 432,
        (__int64)this + 296,
        (__int64)v10 + 80,
        (__int64)v10 + 64,
        (__int64)a2 + 64);
    }
    v12 = (unsigned __int16 *)DfspCreateRootNameString(
                                (const struct _UNICODE_STRING *)this + 27,
                                (const struct _UNICODE_STRING *)((char *)this + 296));
    v7 = v12;
    if ( !v12 )
      goto LABEL_12;
    v23[0] = v12;
    v13 = 4;
    v23[1] = *((unsigned __int16 **)v10 + 11);
    v14 = -1073727277;
    v24 = *((_QWORD *)v10 + 9);
    v25 = *((_QWORD *)a2 + 9);
    goto LABEL_11;
  }
  if ( (unsigned int)DfsRemoveFromPrefixTableLocked(*((_QWORD *)this + 32), &v22, v10) )
    goto LABEL_12;
  *((_DWORD *)v10 + 13) &= ~1u;
  DfsGeneric::ReleaseReference(v10);
LABEL_15:
  v15 = DfsInsertInPrefixTableLocked(*((_QWORD *)this + 32), &v22, a2);
  if ( v15 )
  {
    v3 = RtlNtStatusToDosError(v15);
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
    *((_DWORD *)a2 + 13) |= 1u;
  }
LABEL_34:
  operator delete(v7);
  v18 = *((_QWORD *)this + 32);
  --*(_DWORD *)(v18 + 16);
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v18 + 24));
  return v3;
}

```

## disassembly

```asm
0x14002b870  mov     [rsp-8+arg_10], rbx
0x14002b875  push    rbp
0x14002b876  push    rsi
0x14002b877  push    rdi
0x14002b878  push    r12
0x14002b87a  push    r13
0x14002b87c  push    r14
0x14002b87e  push    r15
0x14002b880  lea     rbp, [rsp-27h]
0x14002b885  sub     rsp, 0A0h
0x14002b88c  mov     rax, cs:__security_cookie
0x14002b893  xor     rax, rsp
0x14002b896  mov     [rbp+57h+var_40], rax
0x14002b89a  mov     rbx, [rcx+100h]
0x14002b8a1  xor     edi, edi
0x14002b8a3  xorps   xmm0, xmm0
0x14002b8a6  mov     [rbp+57h+var_80], dil
0x14002b8aa  mov     rsi, rcx
0x14002b8ad  mov     [rbp+57h+var_78], rdi
0x14002b8b1  movups  [rbp+57h+var_70], xmm0
0x14002b8b5  mov     rcx, [rbx+18h]; lpCriticalSection
0x14002b8b9  mov     r15, rdx
0x14002b8bc  xorps   xmm1, xmm1
0x14002b8bf  mov     r14d, edi
0x14002b8c2  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x14002b8c6  call    cs:__imp_EnterCriticalSection
0x14002b8cd  nop     dword ptr [rax+rax+00h]
0x14002b8d2  inc     dword ptr [rbx+10h]
0x14002b8d5  lea     rax, [rbp+57h+var_80]
0x14002b8d9  movups  xmm0, xmmword ptr [r15+50h]
0x14002b8de  mov     rcx, [rsi+100h]
0x14002b8e5  lea     r9, [rbp+57h+var_78]
0x14002b8e9  lea     r8, [rbp+57h+var_60]
0x14002b8ed  mov     [rsp+0D0h+var_B0], rax
0x14002b8f2  lea     rdx, [rbp+57h+var_70]
0x14002b8f6  movdqu  [rbp+57h+var_70], xmm0
0x14002b8fb  call    DfsFindUnicodePrefixLocked
0x14002b900  test    eax, eax
0x14002b902  jnz     loc_14002BAF6
0x14002b908  mov     rbx, [rbp+57h+var_78]
0x14002b90c  cmp     word ptr [rbp+57h+var_60], di
0x14002b910  jnz     loc_14002BA42
0x14002b916  lea     r12, [r15+40h]
0x14002b91a  mov     r8b, 1; CaseInsensitive
0x14002b91d  lea     r13, [rbx+40h]
0x14002b921  mov     rdx, r12; String2
0x14002b924  mov     rcx, r13; String1
0x14002b927  call    cs:__imp_RtlCompareUnicodeString
0x14002b92e  nop     dword ptr [rax+rax+00h]
0x14002b933  test    eax, eax
0x14002b935  jz      loc_14002B9EF
0x14002b93b  lea     rax, WPP_GLOBAL_Control
0x14002b942  cmp     cs:WPP_GLOBAL_Control, rax
0x14002b949  jz      short loc_14002B998
0x14002b94b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002b952  test    rcx, rcx
0x14002b955  jz      short loc_14002B998
0x14002b957  lea     eax, [rdi+20h]
0x14002b95a  bts     eax, 1Fh
0x14002b95e  test    [rcx+1Ch], eax
0x14002b961  jz      short loc_14002B998
0x14002b963  cmp     byte ptr [rcx+19h], 1
0x14002b967  jb      short loc_14002B998
0x14002b969  mov     rcx, [rcx+10h]
0x14002b96d  lea     rax, [rbx+50h]
0x14002b971  mov     [rsp+0D0h+var_98], r12
0x14002b976  lea     rdx, [rsi+128h]
0x14002b97d  mov     [rsp+0D0h+var_A0], r13
0x14002b982  lea     r9, [rsi+1B0h]
0x14002b989  mov     [rsp+0D0h+var_A8], rax
0x14002b98e  mov     [rsp+0D0h+var_B0], rdx
0x14002b993  call    WPP_SF_ZZZZZ
0x14002b998  lea     rdx, [rsi+128h]; struct _UNICODE_STRING *
0x14002b99f  lea     rcx, [rsi+1B0h]; struct _UNICODE_STRING *
0x14002b9a6  call    ?DfspCreateRootNameString@@YAPEBGPEBU_UNICODE_STRING@@0@Z; DfspCreateRootNameString(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x14002b9ab  mov     r14, rax
0x14002b9ae  test    rax, rax
0x14002b9b1  jz      short loc_14002B9E5
0x14002b9b3  mov     [rbp+57h+var_60], rax
0x14002b9b7  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x14002b9bb  mov     rax, [rbx+58h]
0x14002b9bf  mov     edx, 4; unsigned __int16
0x14002b9c4  mov     [rbp+57h+var_60+8], rax
0x14002b9c8  mov     ecx, 0C00038D3h; unsigned int
0x14002b9cd  mov     rax, [rbx+48h]
0x14002b9d1  mov     [rbp+57h+var_50], rax
0x14002b9d5  mov     rax, [r15+48h]
0x14002b9d9  mov     [rbp+57h+var_48], rax
0x14002b9dd  xor     r9d, r9d; unsigned int
0x14002b9e0  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x14002b9e5  mov     edi, 0B7h
0x14002b9ea  jmp     loc_14002BB9D
0x14002b9ef  mov     rcx, [rsi+100h]
0x14002b9f6  lea     rdx, [rbp+57h+var_70]
0x14002b9fa  mov     r8, rbx
0x14002b9fd  call    DfsRemoveFromPrefixTableLocked
0x14002ba02  test    eax, eax
0x14002ba04  jnz     short loc_14002B9E5
0x14002ba06  and     dword ptr [rbx+34h], 0FFFFFFFEh
0x14002ba0a  mov     rcx, rbx; this
0x14002ba0d  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14002ba12  mov     rcx, [rsi+100h]
0x14002ba19  lea     rdx, [rbp+57h+var_70]
0x14002ba1d  mov     r8, r15
0x14002ba20  call    DfsInsertInPrefixTableLocked
0x14002ba25  test    eax, eax
0x14002ba27  jz      loc_14002BB93
0x14002ba2d  mov     ecx, eax; Status
0x14002ba2f  call    cs:__imp_RtlNtStatusToDosError
0x14002ba36  nop     dword ptr [rax+rax+00h]
0x14002ba3b  mov     edi, eax
0x14002ba3d  jmp     loc_14002BB9D
0x14002ba42  test    byte ptr [rbx+34h], 4
0x14002ba46  jnz     short loc_14002B9E5
0x14002ba48  lea     rax, WPP_GLOBAL_Control
0x14002ba4f  cmp     cs:WPP_GLOBAL_Control, rax
0x14002ba56  jz      short loc_14002BAB0
0x14002ba58  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002ba5f  test    rcx, rcx
0x14002ba62  jz      short loc_14002BAB0
0x14002ba64  mov     eax, 20h ; ' '
0x14002ba69  bts     eax, 1Fh
0x14002ba6d  test    [rcx+1Ch], eax
0x14002ba70  jz      short loc_14002BAB0
0x14002ba72  cmp     byte ptr [rcx+19h], 1
0x14002ba76  jb      short loc_14002BAB0
0x14002ba78  mov     rcx, [rcx+10h]
0x14002ba7c  lea     rdx, [rsi+128h]
0x14002ba83  lea     rax, [rbx+50h]
0x14002ba87  mov     [rsp+0D0h+var_90], rax
0x14002ba8c  lea     r9, [rsi+1B0h]
0x14002ba93  mov     [rsp+0D0h+var_98], rdx
0x14002ba98  lea     rax, [rbp+57h+var_70]
0x14002ba9c  mov     [rsp+0D0h+var_A0], r9
0x14002baa1  mov     [rsp+0D0h+var_A8], rax
0x14002baa6  mov     [rsp+0D0h+var_B0], rdx
0x14002baab  call    WPP_SF_ZZZZZZ
0x14002bab0  lea     rdx, [rsi+128h]; struct _UNICODE_STRING *
0x14002bab7  lea     rcx, [rsi+1B0h]; struct _UNICODE_STRING *
0x14002babe  call    ?DfspCreateRootNameString@@YAPEBGPEBU_UNICODE_STRING@@0@Z; DfspCreateRootNameString(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x14002bac3  mov     r14, rax
0x14002bac6  test    rax, rax
0x14002bac9  jz      loc_14002B9E5
0x14002bacf  mov     [rbp+57h+var_60], rax
0x14002bad3  lea     r8, [rbp+57h+var_60]
0x14002bad7  mov     rax, [r15+58h]
0x14002badb  mov     edx, 3
0x14002bae0  mov     [rbp+57h+var_60+8], rax
0x14002bae4  mov     ecx, 0C00038D0h
0x14002bae9  mov     rax, [rbx+58h]
0x14002baed  mov     [rbp+57h+var_50], rax
0x14002baf1  jmp     loc_14002B9DD
0x14002baf6  cmp     [rbp+57h+var_80], dil
0x14002bafa  jz      loc_14002BA12
0x14002bb00  lea     rax, WPP_GLOBAL_Control
0x14002bb07  cmp     cs:WPP_GLOBAL_Control, rax
0x14002bb0e  jz      short loc_14002BB55
0x14002bb10  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002bb17  test    rcx, rcx
0x14002bb1a  jz      short loc_14002BB55
0x14002bb1c  mov     eax, 20h ; ' '
0x14002bb21  bts     eax, 1Fh
0x14002bb25  test    [rcx+1Ch], eax
0x14002bb28  jz      short loc_14002BB55
0x14002bb2a  cmp     byte ptr [rcx+19h], 1
0x14002bb2e  jb      short loc_14002BB55
0x14002bb30  mov     rcx, [rcx+10h]
0x14002bb34  lea     rdx, [rbp+57h+var_70]
0x14002bb38  lea     rax, [rsi+128h]
0x14002bb3f  mov     [rsp+0D0h+var_A8], rdx
0x14002bb44  lea     r9, [rsi+1B0h]
0x14002bb4b  mov     [rsp+0D0h+var_B0], rax
0x14002bb50  call    WPP_SF_ZZZ
0x14002bb55  lea     rdx, [rsi+128h]; struct _UNICODE_STRING *
0x14002bb5c  lea     rcx, [rsi+1B0h]; struct _UNICODE_STRING *
0x14002bb63  call    ?DfspCreateRootNameString@@YAPEBGPEBU_UNICODE_STRING@@0@Z; DfspCreateRootNameString(_UNICODE_STRING const *,_UNICODE_STRING const *)
0x14002bb68  mov     r14, rax
0x14002bb6b  test    rax, rax
0x14002bb6e  jz      loc_14002B9E5
0x14002bb74  mov     [rbp+57h+var_60], rax
0x14002bb78  lea     r8, [rbp+57h+var_60]
0x14002bb7c  mov     rax, [r15+58h]
0x14002bb80  mov     edx, 2
0x14002bb85  mov     [rbp+57h+var_60+8], rax
0x14002bb89  mov     ecx, 0C00038D1h
0x14002bb8e  jmp     loc_14002B9DD
0x14002bb93  lock inc dword ptr [r15+8]
0x14002bb98  or      dword ptr [r15+34h], 1
0x14002bb9d  mov     rcx, r14; Block
0x14002bba0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002bba5  mov     rcx, [rsi+100h]
0x14002bbac  dec     dword ptr [rcx+10h]
0x14002bbaf  mov     rcx, [rcx+18h]; lpCriticalSection
0x14002bbb3  call    cs:__imp_LeaveCriticalSection
0x14002bbba  nop     dword ptr [rax+rax+00h]
0x14002bbbf  mov     eax, edi
0x14002bbc1  mov     rcx, [rbp+57h+var_40]
0x14002bbc5  xor     rcx, rsp; StackCookie
0x14002bbc8  call    __security_check_cookie
0x14002bbcd  mov     rbx, [rsp+0D0h+arg_10]
0x14002bbd5  add     rsp, 0A0h
0x14002bbdc  pop     r15
0x14002bbde  pop     r14
0x14002bbe0  pop     r13
0x14002bbe2  pop     r12
0x14002bbe4  pop     rdi
0x14002bbe5  pop     rsi
0x14002bbe6  pop     rbp
0x14002bbe7  retn
```
