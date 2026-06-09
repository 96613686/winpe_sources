# MRxDAVPrecompleteUserModeQueryDirectoryRequest

- ea: `0x14001e6a0`
- end: `0x14001f6b5`
- name: `MRxDAVPrecompleteUserModeQueryDirectoryRequest`
- size: `4117`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001838`
- `0x1400018d4`
- `0x1400019bc`
- `0x140001b64`
- `0x140001c30`
- `0x140002138`
- `0x140002374`
- `0x1400039b0`
- `0x140005b3c`
- `0x140006900`
- `0x140006c00`
- `0x14001e6a0`
- `0x1400255d4`
- `0x140027658`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e71f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e761`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e820`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e8a0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e902`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e978`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e9e8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eb16`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eb83`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ebfd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ec87`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ed10`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eddd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eefc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001efb0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f0ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f1e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f4cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f503`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f539`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f58b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f5b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f5e3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f641`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e71f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e761`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e820`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e8a0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e902`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e978`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001e9e8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eb16`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eb83`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ebfd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ec87`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ed10`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eddd`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001eefc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001efb0`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f0ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f1e9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f4cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f503`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f539`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f58b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f5b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f5e3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f641`
- `ntoskrnl!ExAllocatePool2` at `0x14001ea74`
- `ntoskrnl!ExAllocatePool2` at `0x14001ea74`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f35a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f688`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f35a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f688`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ece1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ece1`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14001ed64`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14001ed64`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14001ed8c`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14001ed8c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001ed9e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001ed9e`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeQueryDirectoryRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  const UNICODE_STRING *v5; // r13
  PWSTR Buffer; // r15
  __int64 v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  int v14; // r12d
  __int64 v15; // rsi
  int v16; // r14d
  __int64 v17; // rbx
  HANDLE v18; // rax
  unsigned int v19; // r14d
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rbx
  HANDLE v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rbx
  HANDLE v27; // rax
  char v28; // di
  __int64 v29; // rbx
  HANDLE v30; // rax
  unsigned __int16 *v32; // rbx
  unsigned __int16 v33; // cx
  USHORT Length; // ax
  void *Pool2; // rax
  char v36; // al
  char v37; // di
  _DWORD *v38; // rsi
  size_t v39; // r12
  int v40; // r13d
  __int64 v41; // rbx
  HANDLE v42; // rax
  __int64 v43; // rax
  __int64 v44; // rbx
  HANDLE v45; // rax
  __int64 v46; // rax
  __int64 *v47; // r13
  unsigned int *v48; // r12
  __int64 v49; // rsi
  USHORT MaximumLength; // bx
  USHORT v51; // di
  unsigned int v52; // eax
  int v53; // edx
  int v54; // r8d
  int v55; // ecx
  const WCHAR *v56; // rdx
  __int64 v57; // rbx
  __int64 v58; // rdi
  unsigned int v59; // eax
  __int64 v60; // rdi
  BOOLEAN IsNameInExpression; // bl
  __int64 *v62; // rcx
  __int64 v63; // rdi
  __int64 v64; // rbx
  unsigned int v65; // eax
  int v66; // edx
  int v67; // eax
  unsigned int v68; // ecx
  __int64 v69; // rbx
  HANDLE v70; // rax
  unsigned int v71; // ebx
  STRSAFE_LPCWSTR *v72; // r8
  unsigned int v73; // eax
  __int64 v74; // rbx
  HANDLE v75; // rax
  unsigned int v76; // ebx
  int *v77; // rdi
  int v78; // eax
  wchar_t *v79; // rcx
  unsigned int v80; // eax
  __int64 v81; // rbx
  HANDLE v82; // rax
  int v83; // eax
  __int64 v84; // rbx
  HANDLE v85; // rax
  int v86; // eax
  STRSAFE_LPCWSTR *v87; // r8
  unsigned int v88; // eax
  __int64 v89; // r14
  char v90; // al
  char v91; // cl
  unsigned int v92; // eax
  unsigned int v93; // r12d
  __int64 v94; // rdx
  __int64 v95; // rdx
  bool v96; // zf
  bool v97; // cf
  __int64 v98; // rbx
  HANDLE v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rbx
  HANDLE v102; // rax
  __int64 v103; // rbx
  HANDLE v104; // rax
  unsigned int v105; // [rsp+48h] [rbp-A1h]
  int v106; // [rsp+4Ch] [rbp-9Dh]
  unsigned int ValueName; // [rsp+50h] [rbp-99h]
  struct _UNICODE_STRING ValueName_8; // [rsp+58h] [rbp-91h] BYREF
  PVOID P_8[2]; // [rsp+68h] [rbp-81h] BYREF
  __int128 v110; // [rsp+78h] [rbp-71h] BYREF
  __int64 v111; // [rsp+88h] [rbp-61h]
  int v112; // [rsp+90h] [rbp-59h]
  int v113; // [rsp+94h] [rbp-55h]
  __int128 v114; // [rsp+98h] [rbp-51h] BYREF
  __int128 v115; // [rsp+A8h] [rbp-41h]
  __int64 v116; // [rsp+B8h] [rbp-31h]
  PCUNICODE_STRING SourceString; // [rsp+C0h] [rbp-29h]
  unsigned __int16 *v118; // [rsp+C8h] [rbp-21h]
  unsigned int *v119; // [rsp+D0h] [rbp-19h]
  struct _UNICODE_STRING Expression; // [rsp+D8h] [rbp-11h] BYREF
  __int64 v121; // [rsp+E8h] [rbp-1h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp+7h] BYREF
  __int64 v123; // [rsp+148h] [rbp+5Fh] BYREF
  __int64 v124; // [rsp+150h] [rbp+67h]
  NTSTATUS v125; // [rsp+158h] [rbp+6Fh] BYREF

  v124 = a2;
  v123 = a1;
  v5 = *(const UNICODE_STRING **)(a2 + 64);
  Buffer = 0;
  v8 = a2;
  v116 = 0;
  v9 = a1;
  v111 = 0;
  v118 = 0;
  DestinationString = 0;
  v114 = 0;
  v115 = 0;
  v110 = 0;
  *(_OWORD *)P_8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v10 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v10, 43, WPP_609949de13fe38daba556366630c430b_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      WPP_SF_qqq(v12, 44, WPP_609949de13fe38daba556366630c430b_Traceguids, v13, v9, v8);
    }
  }
  v14 = a5;
  P_8[1] = 0;
  LODWORD(P_8[0]) = 0;
  if ( !a5 )
  {
    v118 = (unsigned __int16 *)(*(_QWORD *)(v8 + 56) + 360LL);
    if ( v5 )
      Buffer = v5[3].Buffer;
  }
  if ( !*(_DWORD *)(a3 + 632) )
  {
    if ( a5 )
    {
      if ( !*(_DWORD *)(v9 + 128) && *(_QWORD *)(a3 + 2312) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v23 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v24 = PsGetCurrentThreadId();
          WPP_SF_q(v23, 46, WPP_609949de13fe38daba556366630c430b_Traceguids, v24);
        }
        *(_DWORD *)(a3 + 24) = 1;
      }
    }
    else if ( !*(_DWORD *)(v9 + 128) )
    {
      v15 = *(_QWORD *)(a3 + 2312);
      if ( v15 )
      {
        *(_QWORD *)Buffer = v15;
        v16 = *(_DWORD *)(a3 + 2320);
        *((_DWORD *)Buffer + 2) = v16;
        *((_DWORD *)Buffer + 3) = 0;
        *((_QWORD *)Buffer + 259) = v15 + 64;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v18 = PsGetCurrentThreadId();
          WPP_SF_qqD(v17, 45, WPP_609949de13fe38daba556366630c430b_Traceguids, v18, v15, v16);
        }
        v9 = v123;
      }
      v8 = v124;
    }
    if ( *(_QWORD *)(a3 + 648) )
    {
      v19 = UMRxFreeSecondaryBuffer(v9);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
        {
          goto LABEL_195;
        }
        v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v21 = PsGetCurrentThreadId();
        v22 = 47;
        goto LABEL_24;
      }
    }
    if ( *(_QWORD *)(a3 + 664) )
    {
      v25 = v123;
      v19 = UMRxFreeSecondaryBuffer(v123);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v26 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v27 = PsGetCurrentThreadId();
          WPP_SF_qD(v26, 48, WPP_609949de13fe38daba556366630c430b_Traceguids, v27, v19);
        }
        goto LABEL_196;
      }
    }
    v9 = v123;
  }
  v28 = *(_BYTE *)(v9 + 208) & 1;
  if ( v28 )
  {
    UMRxFinalizeAsyncEngineContext(&v123);
    v9 = v123;
  }
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v29 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v30 = PsGetCurrentThreadId();
      WPP_SF_q(v29, 49, WPP_609949de13fe38daba556366630c430b_Traceguids, v30);
    }
    if ( v28 )
      UMRxFinalizeAsyncEngineContext(&v123);
    return 0;
  }
  v32 = v118;
  v33 = *v118;
  if ( *v118 > 0x208u || (Length = v5[5].Length, SourceString = v5 + 5, Length > 0x208u) )
  {
LABEL_194:
    v19 = -1073741562;
    goto LABEL_195;
  }
  WORD1(P_8[0]) = v33 + Length + 2;
  LOWORD(P_8[0]) = WORD1(P_8[0]);
  if ( WORD1(P_8[0]) > 0x208u )
  {
LABEL_193:
    LODWORD(P_8[0]) = 0;
    goto LABEL_194;
  }
  Pool2 = (void *)ExAllocatePool2(258, 520, 1683052100);
  P_8[1] = Pool2;
  if ( !Pool2 )
  {
    v19 = -1073741670;
    goto LABEL_195;
  }
  memset(Pool2, 0, 0x208u);
  memmove(P_8[1], *((const void **)v118 + 1), *v118);
  *((_WORD *)P_8[1] + ((unsigned __int64)*v118 >> 1)) = 92;
  memmove((char *)P_8[1] + 2 * (*v32 >> 1) + 2, v5[5].Buffer, v5[5].Length);
  v19 = *(_DWORD *)(v9 + 128);
  v125 = v19;
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
      goto LABEL_195;
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    v22 = 50;
LABEL_24:
    WPP_SF_qD(v20, v22, WPP_609949de13fe38daba556366630c430b_Traceguids, v21, v19);
    goto LABEL_195;
  }
  v36 = *(_BYTE *)(v8 + 517);
  v37 = *(_BYTE *)(v8 + 516);
  v38 = *(_DWORD **)(v8 + 456);
  LOBYTE(a5) = v36;
  *(_QWORD *)&ValueName_8.Length = v38;
  v39 = *(unsigned int *)(v124 + 472);
  v40 = *(_DWORD *)(v124 + 448);
  v105 = *(_DWORD *)(v124 + 472);
  v112 = v40;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v41 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v42 = PsGetCurrentThreadId();
    WPP_SF_qD(v41, 51, WPP_609949de13fe38daba556366630c430b_Traceguids, v42, v40);
  }
  memset(v38, 0, v39);
  if ( v37 )
  {
    v43 = *(_QWORD *)Buffer + 64LL;
    *((_DWORD *)Buffer + 3) = 0;
    *((_QWORD *)Buffer + 259) = v43;
  }
  if ( *((_DWORD *)Buffer + 3) == *((_DWORD *)Buffer + 2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v44 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v45 = PsGetCurrentThreadId();
      WPP_SF_q(v44, 52, WPP_609949de13fe38daba556366630c430b_Traceguids, v45);
    }
    v19 = -2147483642;
LABEL_65:
    v46 = *(_QWORD *)Buffer + 64LL;
    *((_DWORD *)Buffer + 3) = 0;
    *((_QWORD *)Buffer + 259) = v46;
    goto LABEL_195;
  }
  v47 = (__int64 *)*((_QWORD *)Buffer + 259);
  v48 = 0;
  v106 = 0;
  ValueName = 0;
  v121 = *(_QWORD *)Buffer;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v49 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    MaximumLength = SourceString->MaximumLength;
    v51 = SourceString->Length;
    v52 = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qddZ(v49, v53, v54, v52, v51, MaximumLength, (__int64)SourceString);
    v38 = *(_DWORD **)&ValueName_8.Length;
  }
  v55 = *((_DWORD *)Buffer + 3);
  v113 = v55;
  while ( 1 )
  {
    if ( !*((_DWORD *)v47 - 16) )
    {
      v56 = (const WCHAR *)v47[4];
      *(_QWORD *)&ValueName_8.Length = v47 + 4;
      if ( v56 )
        break;
    }
    v66 = v55;
    v47 = (__int64 *)*v47;
    *((_QWORD *)Buffer + 259) = v47;
    v67 = v55 + 1;
LABEL_160:
    v55 = v67;
    *((_DWORD *)Buffer + 3) = v67;
LABEL_161:
    if ( v47 == (__int64 *)(v121 + 64) || (unsigned int)(v66 + 1) >= *((_DWORD *)Buffer + 2) )
    {
      v60 = v124;
      goto LABEL_164;
    }
  }
  RtlInitUnicodeString(&DestinationString, v56);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v57 = v47[4];
    v58 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v59 = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qS(v58, 54, (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids, v59, v57);
  }
  v60 = v124;
  if ( !*(_BYTE *)(v124 + 520) )
  {
LABEL_82:
    if ( *((_DWORD *)Buffer + 3) || !*(_BYTE *)(v60 + 520) )
    {
      if ( !*((_DWORD *)v47 - 14) )
        *((_DWORD *)v47 - 14) = 32;
      if ( *v118 > 0x208u )
        goto LABEL_193;
      if ( DestinationString.Length > 0x208u )
        goto LABEL_193;
      WORD1(P_8[0]) = DestinationString.Length + *v118 + 2;
      LOWORD(P_8[0]) = WORD1(P_8[0]);
      if ( WORD1(P_8[0]) > 0x208u )
        goto LABEL_193;
      v68 = (*v118 >> 1) + 1;
      v119 = v38;
      memmove((char *)P_8[1] + 2 * v68, DestinationString.Buffer, DestinationString.Length);
      if ( v112 == 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
        {
          v84 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v85 = PsGetCurrentThreadId();
          WPP_SF_q(v84, 59, WPP_609949de13fe38daba556366630c430b_Traceguids, v85);
        }
        if ( v48 )
          *v48 = ValueName;
        v76 = (2 * *((_DWORD *)v47 + 6) + 81) & 0xFFFFFFF8;
        ValueName = v76;
        if ( v76 > v105 )
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
          {
            goto LABEL_187;
          }
          v98 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v99 = PsGetCurrentThreadId();
          v100 = 60;
LABEL_186:
          WPP_SF_q(v98, v100, WPP_609949de13fe38daba556366630c430b_Traceguids, v99);
          goto LABEL_187;
        }
        *v38 = 0;
        v77 = v38 + 14;
        v38[1] = *((_DWORD *)v47 - 15);
        v38[2] = *((_DWORD *)v47 - 12);
        v38[3] = *((_DWORD *)v47 - 11);
        v38[4] = *((_DWORD *)v47 - 8);
        v38[5] = *((_DWORD *)v47 - 7);
        v38[6] = *((_DWORD *)v47 - 8);
        v38[7] = *((_DWORD *)v47 - 7);
        v38[8] = *((_DWORD *)v47 - 8);
        v38[9] = *((_DWORD *)v47 - 7);
        v38[10] = *((_DWORD *)v47 - 2);
        v38[11] = *((_DWORD *)v47 - 1);
        v38[12] = *((_DWORD *)v47 - 2);
        v38[13] = *((_DWORD *)v47 - 1);
        v86 = *((_DWORD *)v47 - 14);
        v38[14] = v86;
        if ( *((_BYTE *)v47 + 20) )
        {
          v86 |= 0x10u;
          *v77 = v86;
        }
        if ( *((_DWORD *)v47 + 4) )
          *v77 = v86 | 2;
        v79 = (wchar_t *)(v38 + 16);
      }
      else
      {
        switch ( v112 )
        {
          case 2:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v81 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v82 = PsGetCurrentThreadId();
              WPP_SF_q(v81, 61, WPP_609949de13fe38daba556366630c430b_Traceguids, v82);
            }
            if ( v48 )
              *v48 = ValueName;
            v76 = (2 * *((_DWORD *)v47 + 6) + 81) & 0xFFFFFFF8;
            ValueName = v76;
            if ( v76 > v105 )
            {
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
              {
                goto LABEL_187;
              }
              v98 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v99 = PsGetCurrentThreadId();
              v100 = 62;
              goto LABEL_186;
            }
            *v38 = 0;
            v77 = v38 + 14;
            v38[1] = *((_DWORD *)v47 - 15);
            v38[2] = *((_DWORD *)v47 - 12);
            v38[3] = *((_DWORD *)v47 - 11);
            v38[4] = *((_DWORD *)v47 - 8);
            v38[5] = *((_DWORD *)v47 - 7);
            v38[6] = *((_DWORD *)v47 - 8);
            v38[7] = *((_DWORD *)v47 - 7);
            v38[8] = *((_DWORD *)v47 - 8);
            v38[9] = *((_DWORD *)v47 - 7);
            v38[10] = *((_DWORD *)v47 - 2);
            v38[11] = *((_DWORD *)v47 - 1);
            v38[12] = *((_DWORD *)v47 - 2);
            v38[13] = *((_DWORD *)v47 - 1);
            v83 = *((_DWORD *)v47 - 14);
            v38[14] = v83;
            if ( *((_BYTE *)v47 + 20) )
            {
              v83 |= 0x10u;
              *v77 = v83;
            }
            if ( *((_DWORD *)v47 + 4) )
              *v77 = v83 | 2;
            v79 = (wchar_t *)(v38 + 17);
            break;
          case 3:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v74 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v75 = PsGetCurrentThreadId();
              WPP_SF_q(v74, 63, WPP_609949de13fe38daba556366630c430b_Traceguids, v75);
            }
            if ( v48 )
              *v48 = ValueName;
            v76 = (2 * *((_DWORD *)v47 + 6) + 105) & 0xFFFFFFF8;
            ValueName = v76;
            if ( v76 > v105 )
            {
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0 )
              {
                goto LABEL_187;
              }
              v98 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v99 = PsGetCurrentThreadId();
              v100 = 64;
              goto LABEL_186;
            }
            *v38 = 0;
            v77 = v38 + 14;
            v38[1] = *((_DWORD *)v47 - 15);
            v38[2] = *((_DWORD *)v47 - 12);
            v38[3] = *((_DWORD *)v47 - 11);
            v38[4] = *((_DWORD *)v47 - 8);
            v38[5] = *((_DWORD *)v47 - 7);
            v38[6] = *((_DWORD *)v47 - 8);
            v38[7] = *((_DWORD *)v47 - 7);
            v38[8] = *((_DWORD *)v47 - 8);
            v38[9] = *((_DWORD *)v47 - 7);
            v38[10] = *((_DWORD *)v47 - 2);
            v38[11] = *((_DWORD *)v47 - 1);
            v38[12] = *((_DWORD *)v47 - 2);
            v38[13] = *((_DWORD *)v47 - 1);
            v78 = *((_DWORD *)v47 - 14);
            v38[14] = v78;
            if ( *((_BYTE *)v47 + 20) )
            {
              v78 |= 0x10u;
              *v77 = v78;
            }
            if ( *((_DWORD *)v47 + 4) )
              *v77 = v78 | 2;
            *((_BYTE *)v38 + 68) = 0;
            *((_WORD *)v38 + 35) = 0;
            v79 = (wchar_t *)v38 + 47;
            break;
          case 12:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v69 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v70 = PsGetCurrentThreadId();
              WPP_SF_q(v69, 57, WPP_609949de13fe38daba556366630c430b_Traceguids, v70);
            }
            if ( v48 )
              *v48 = ValueName;
            v71 = (2 * *((_DWORD *)v47 + 6) + 25) & 0xFFFFFFF8;
            ValueName = v71;
            if ( v71 > v105 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
              {
                v98 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v99 = PsGetCurrentThreadId();
                v100 = 58;
                goto LABEL_186;
              }
LABEL_187:
              if ( v48 )
                *v48 = 0;
              v19 = 0;
LABEL_164:
              if ( !v106 && v47 == (__int64 *)(v121 + 64) )
              {
                v97 = v113 != 0;
                v113 = -v113;
                v19 = v97 ? -2147483642 : -1073741809;
                goto LABEL_65;
              }
              *(_DWORD *)(v60 + 472) -= v106;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
              {
                v103 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v104 = PsGetCurrentThreadId();
                WPP_SF_q(v103, 66, WPP_609949de13fe38daba556366630c430b_Traceguids, v104);
              }
              goto LABEL_195;
            }
            v72 = *(STRSAFE_LPCWSTR **)&ValueName_8.Length;
            *v38 = 0;
            v38[1] = *((_DWORD *)v47 - 15);
            v73 = 2 * *((_DWORD *)v47 + 6) + 2;
            v38[2] = v73;
            StringCbCopyW((STRSAFE_LPWSTR)v38 + 6, v73, *v72);
            v105 -= v71;
            v38 = (_DWORD *)((char *)v38 + v71);
            v106 += v71;
            goto LABEL_157;
          default:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
            {
              v101 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v102 = PsGetCurrentThreadId();
              WPP_SF_qD(v101, 65, WPP_609949de13fe38daba556366630c430b_Traceguids, v102, v112);
            }
            v19 = -1073741637;
            goto LABEL_195;
        }
        v38[16] = 0;
      }
      v87 = *(STRSAFE_LPCWSTR **)&ValueName_8.Length;
      v88 = 2 * *((_DWORD *)v47 + 6) + 2;
      v38[15] = v88;
      StringCbCopyW(v79, v88, *v87);
      v89 = v124;
      v90 = MRxDAVIsBasicFileInfoCacheFound(v124, &v114, &v125, P_8);
      v91 = *((_BYTE *)v47 + 20);
      if ( v90 )
      {
        if ( v91 && (v116 & 0x4000) != 0 )
          *v77 |= 0x4000u;
        v19 = v125;
      }
      else
      {
        if ( v91 )
        {
          ValueName_8 = 0;
          v92 = MRxDAVGetFullDirectoryPath(v89, P_8, &ValueName_8);
          v19 = v92;
          v125 = v92;
          if ( ValueName_8.Buffer )
          {
            if ( (*v77 & 0x4000) != 0 )
            {
              v80 = MRxDAVCreateEncryptedDirectoryKey(&ValueName_8);
              v19 = v80;
              v125 = v80;
LABEL_143:
              v93 = v80;
            }
            else
            {
              v80 = MRxDAVQueryEncryptedDirectoryKey(&ValueName_8);
              v125 = v80;
              v19 = v80;
              if ( v80 )
              {
                if ( v80 != -1073741772 )
                  goto LABEL_143;
                v19 = 0;
                v125 = 0;
              }
              else
              {
                *v77 |= 0x4000u;
              }
              v93 = 0;
            }
            ExFreePoolWithTag(ValueName_8.Buffer, 0);
          }
          else
          {
            v93 = v92;
          }
          if ( v93 )
            goto LABEL_195;
        }
        else
        {
          v19 = v125;
        }
        v114 = *(_OWORD *)(v38 + 2);
        v94 = *(_QWORD *)(v124 + 56);
        v115 = *(_OWORD *)(v38 + 6);
        v95 = *(_QWORD *)(v94 + 120);
        LODWORD(v116) = *v77;
        *(_QWORD *)&v110 = *((_QWORD *)v38 + 6);
        *((_QWORD *)&v110 + 1) = *((_QWORD *)v38 + 5);
        BYTE5(v111) = *((_BYTE *)v47 + 20);
        LODWORD(v111) = 1;
        BYTE4(v111) = 0;
        MRxDAVCreateFileInfoCacheWithName(P_8, v95, &v114, &v110);
      }
      v105 -= v76;
      v106 += v76;
      v38 = (_DWORD *)((char *)v38 + v76);
      *v77 &= ~0x100u;
      v60 = v124;
LABEL_157:
      v96 = (_BYTE)a5 == 0;
      v66 = *((_DWORD *)Buffer + 3);
      v47 = (__int64 *)*v47;
      *((_QWORD *)Buffer + 259) = v47;
      v55 = v66 + 1;
      *((_DWORD *)Buffer + 3) = v66 + 1;
      if ( !v96 )
        goto LABEL_164;
      v48 = v119;
      goto LABEL_161;
    }
    v66 = 0;
    v47 = (__int64 *)*v47;
    *((_QWORD *)Buffer + 259) = v47;
    v67 = 1;
    goto LABEL_160;
  }
  *(_QWORD *)&Expression.Length = 0;
  Expression.Buffer = 0;
  v125 = RtlUpcaseUnicodeString(&Expression, SourceString, 1u);
  v19 = v125;
  if ( !v125 )
  {
    IsNameInExpression = FsRtlIsNameInExpression(&Expression, &DestinationString, 1u, 0);
    RtlFreeUnicodeString(&Expression);
    if ( !IsNameInExpression )
    {
      v62 = (__int64 *)*v47;
      v47 = (__int64 *)*v47;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v63 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v64 = **(_QWORD **)&ValueName_8.Length;
        v65 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qS(v63, 56, (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids, v65, v64);
        v62 = v47;
      }
      v66 = *((_DWORD *)Buffer + 3);
      *((_QWORD *)Buffer + 259) = v62;
      v55 = v66 + 1;
      *((_DWORD *)Buffer + 3) = v66 + 1;
      goto LABEL_161;
    }
    goto LABEL_82;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v21 = PsGetCurrentThreadId();
    v22 = 55;
    goto LABEL_24;
  }
LABEL_195:
  v25 = v123;
LABEL_196:
  *(_DWORD *)(v25 + 128) = v19;
  if ( P_8[1] )
    ExFreePoolWithTag(P_8[1], 0);
  return 1;
}

```

## disassembly

```asm
0x14001e6a0  mov     rax, rsp
0x14001e6a3  mov     [rax+20h], rbx
0x14001e6a7  mov     [rax+10h], rdx
0x14001e6ab  mov     [rax+8], rcx
0x14001e6af  push    rbp
0x14001e6b0  push    rsi
0x14001e6b1  push    rdi
0x14001e6b2  push    r12
0x14001e6b4  push    r13
0x14001e6b6  push    r14
0x14001e6b8  push    r15
0x14001e6ba  lea     rbp, [rax-57h]
0x14001e6be  sub     rsp, 100h
0x14001e6c5  mov     r13, [rdx+40h]
0x14001e6c9  xorps   xmm0, xmm0
0x14001e6cc  xor     r15d, r15d
0x14001e6cf  mov     rdi, r8
0x14001e6d2  xor     eax, eax
0x14001e6d4  mov     rsi, rdx
0x14001e6d7  mov     [rbp+4Fh+var_80], rax
0x14001e6db  mov     r14, rcx
0x14001e6de  mov     [rbp+4Fh+var_B0], rax
0x14001e6e2  mov     [rbp+4Fh+var_70], rax
0x14001e6e6  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14001e6ea  movups  [rbp+4Fh+var_A0], xmm0
0x14001e6ee  movups  [rbp+4Fh+var_90], xmm0
0x14001e6f2  movups  [rbp+4Fh+var_C0], xmm0
0x14001e6f6  movups  xmmword ptr [rsp+130h+P+8], xmm0
0x14001e6fb  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e702  lea     rcx, WPP_GLOBAL_Control
0x14001e709  cmp     rbx, rcx
0x14001e70c  jz      loc_14001E795
0x14001e712  test    dword ptr [rbx+2Ch], 2000h
0x14001e719  jz      short loc_14001E748
0x14001e71b  mov     rbx, [rbx+18h]
0x14001e71f  call    cs:__imp_PsGetCurrentThreadId
0x14001e726  nop     dword ptr [rax+rax+00h]
0x14001e72b  lea     edx, [r15+2Bh]
0x14001e72f  mov     rcx, rbx
0x14001e732  mov     r9, rax
0x14001e735  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e73c  call    WPP_SF_q
0x14001e741  lea     rcx, WPP_GLOBAL_Control
0x14001e748  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e74f  cmp     rbx, rcx
0x14001e752  jz      short loc_14001E795
0x14001e754  test    dword ptr [rbx+2Ch], 2000h
0x14001e75b  jz      short loc_14001E795
0x14001e75d  mov     rbx, [rbx+18h]
0x14001e761  call    cs:__imp_PsGetCurrentThreadId
0x14001e768  nop     dword ptr [rax+rax+00h]
0x14001e76d  mov     edx, 2Ch ; ','
0x14001e772  mov     [rsp+130h+var_108], rsi
0x14001e777  mov     r9, rax
0x14001e77a  mov     [rsp+130h+var_110], r14
0x14001e77f  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e786  mov     rcx, rbx
0x14001e789  call    WPP_SF_qqq
0x14001e78e  lea     rcx, WPP_GLOBAL_Control
0x14001e795  mov     r12d, [rbp+4Fh+arg_20]
0x14001e799  xor     eax, eax
0x14001e79b  mov     [rbp+4Fh+var_C8], r15
0x14001e79f  mov     dword ptr [rsp+130h+P+8], eax
0x14001e7a3  test    r12d, r12d
0x14001e7a6  jnz     short loc_14001E7BF
0x14001e7a8  mov     rax, [rsi+38h]
0x14001e7ac  add     rax, 168h
0x14001e7b2  mov     [rbp+4Fh+var_70], rax
0x14001e7b6  test    r13, r13
0x14001e7b9  jz      short loc_14001E7BF
0x14001e7bb  mov     r15, [r13+38h]
0x14001e7bf  cmp     dword ptr [rdi+278h], 0
0x14001e7c6  jnz     loc_14001E9A9
0x14001e7cc  test    r12d, r12d
0x14001e7cf  jnz     loc_14001E8CD
0x14001e7d5  cmp     [r14+80h], r12d
0x14001e7dc  jnz     short loc_14001E855
0x14001e7de  mov     rsi, [rdi+908h]
0x14001e7e5  test    rsi, rsi
0x14001e7e8  jz      short loc_14001E851
0x14001e7ea  mov     [r15], rsi
0x14001e7ed  lea     rax, [rsi+40h]
0x14001e7f1  mov     r14d, [rdi+910h]
0x14001e7f8  mov     [r15+8], r14d
0x14001e7fc  mov     [r15+0Ch], r12d
0x14001e800  mov     [r15+818h], rax
0x14001e807  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e80e  cmp     rbx, rcx
0x14001e811  jz      short loc_14001E84D
0x14001e813  test    dword ptr [rbx+2Ch], 2000h
0x14001e81a  jz      short loc_14001E84D
0x14001e81c  mov     rbx, [rbx+18h]
0x14001e820  call    cs:__imp_PsGetCurrentThreadId
0x14001e827  nop     dword ptr [rax+rax+00h]
0x14001e82c  lea     edx, [r12+2Dh]
0x14001e831  mov     dword ptr [rsp+130h+var_108], r14d
0x14001e836  mov     r9, rax
0x14001e839  mov     [rsp+130h+var_110], rsi
0x14001e83e  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e845  mov     rcx, rbx
0x14001e848  call    WPP_SF_qqD
0x14001e84d  mov     r14, [rbp+4Fh+arg_0]
0x14001e851  mov     rsi, [rbp+4Fh+arg_8]
0x14001e855  mov     rdx, [rdi+288h]
0x14001e85c  test    rdx, rdx
0x14001e85f  jz      loc_14001E931
0x14001e865  mov     rcx, r14
0x14001e868  call    UMRxFreeSecondaryBuffer
0x14001e86d  mov     r14d, eax
0x14001e870  test    eax, eax
0x14001e872  jz      loc_14001E931
0x14001e878  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e87f  lea     rax, WPP_GLOBAL_Control
0x14001e886  cmp     rbx, rax
0x14001e889  jz      loc_14001F672
0x14001e88f  test    dword ptr [rbx+2Ch], 2000h
0x14001e896  jz      loc_14001F672
0x14001e89c  mov     rbx, [rbx+18h]
0x14001e8a0  call    cs:__imp_PsGetCurrentThreadId
0x14001e8a7  nop     dword ptr [rax+rax+00h]
0x14001e8ac  mov     edx, 2Fh ; '/'
0x14001e8b1  mov     r9, rax
0x14001e8b4  mov     dword ptr [rsp+130h+var_110], r14d
0x14001e8b9  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e8c0  mov     rcx, rbx
0x14001e8c3  call    WPP_SF_qD
0x14001e8c8  jmp     loc_14001F672
0x14001e8cd  cmp     dword ptr [r14+80h], 0
0x14001e8d5  jnz     loc_14001E855
0x14001e8db  cmp     qword ptr [rdi+908h], 0
0x14001e8e3  jz      loc_14001E855
0x14001e8e9  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e8f0  cmp     rbx, rcx
0x14001e8f3  jz      short loc_14001E925
0x14001e8f5  test    dword ptr [rbx+2Ch], 4000h
0x14001e8fc  jz      short loc_14001E925
0x14001e8fe  mov     rbx, [rbx+18h]
0x14001e902  call    cs:__imp_PsGetCurrentThreadId
0x14001e909  nop     dword ptr [rax+rax+00h]
0x14001e90e  mov     edx, 2Eh ; '.'
0x14001e913  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e91a  mov     r9, rax
0x14001e91d  mov     rcx, rbx
0x14001e920  call    WPP_SF_q
0x14001e925  mov     dword ptr [rdi+18h], 1
0x14001e92c  jmp     loc_14001E855
0x14001e931  mov     rdx, [rdi+298h]
0x14001e938  test    rdx, rdx
0x14001e93b  jz      short loc_14001E9A5
0x14001e93d  mov     rdi, [rbp+4Fh+arg_0]
0x14001e941  mov     rcx, rdi
0x14001e944  call    UMRxFreeSecondaryBuffer
0x14001e949  mov     r14d, eax
0x14001e94c  test    eax, eax
0x14001e94e  jz      short loc_14001E9A5
0x14001e950  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e957  lea     rax, WPP_GLOBAL_Control
0x14001e95e  cmp     rbx, rax
0x14001e961  jz      loc_14001F676
0x14001e967  test    dword ptr [rbx+2Ch], 2000h
0x14001e96e  jz      loc_14001F676
0x14001e974  mov     rbx, [rbx+18h]
0x14001e978  call    cs:__imp_PsGetCurrentThreadId
0x14001e97f  nop     dword ptr [rax+rax+00h]
0x14001e984  mov     edx, 30h ; '0'
0x14001e989  mov     dword ptr [rsp+130h+var_110], r14d
0x14001e98e  mov     r9, rax
0x14001e991  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001e998  mov     rcx, rbx
0x14001e99b  call    WPP_SF_qD
0x14001e9a0  jmp     loc_14001F676
0x14001e9a5  mov     r14, [rbp+4Fh+arg_0]
0x14001e9a9  mov     dil, [r14+0D0h]
0x14001e9b0  and     dil, 1
0x14001e9b4  jz      short loc_14001E9C3
0x14001e9b6  lea     rcx, [rbp+4Fh+arg_0]
0x14001e9ba  call    UMRxFinalizeAsyncEngineContext
0x14001e9bf  mov     r14, [rbp+4Fh+arg_0]
0x14001e9c3  test    r12d, r12d
0x14001e9c6  jz      short loc_14001EA20
0x14001e9c8  mov     rbx, cs:WPP_GLOBAL_Control
0x14001e9cf  lea     rax, WPP_GLOBAL_Control
0x14001e9d6  cmp     rbx, rax
0x14001e9d9  jz      short loc_14001EA0B
0x14001e9db  test    dword ptr [rbx+2Ch], 2000h
0x14001e9e2  jz      short loc_14001EA0B
0x14001e9e4  mov     rbx, [rbx+18h]
0x14001e9e8  call    cs:__imp_PsGetCurrentThreadId
0x14001e9ef  nop     dword ptr [rax+rax+00h]
0x14001e9f4  mov     edx, 31h ; '1'
0x14001e9f9  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001ea00  mov     r9, rax
0x14001ea03  mov     rcx, rbx
0x14001ea06  call    WPP_SF_q
0x14001ea0b  test    dil, dil
0x14001ea0e  jz      short loc_14001EA19
0x14001ea10  lea     rcx, [rbp+4Fh+arg_0]
0x14001ea14  call    UMRxFinalizeAsyncEngineContext
0x14001ea19  xor     eax, eax
0x14001ea1b  jmp     loc_14001F699
0x14001ea20  mov     rbx, [rbp+4Fh+var_70]
0x14001ea24  mov     r12d, 208h
0x14001ea2a  movzx   ecx, word ptr [rbx]
0x14001ea2d  cmp     r12w, cx
0x14001ea31  jb      loc_14001F66C
0x14001ea37  lea     rdi, [r13+50h]
0x14001ea3b  movzx   eax, word ptr [rdi]
0x14001ea3e  mov     [rbp+4Fh+SourceString], rdi
0x14001ea42  cmp     r12w, ax
0x14001ea46  jb      loc_14001F66C
0x14001ea4c  add     ax, 2
0x14001ea50  add     ax, cx
0x14001ea53  mov     word ptr [rbp+4Fh+P+0Ah], ax
0x14001ea57  mov     word ptr [rsp+130h+P+8], ax
0x14001ea5c  cmp     ax, r12w
0x14001ea60  ja      loc_14001F666
0x14001ea66  mov     r8d, 64515644h
0x14001ea6c  mov     edx, r12d
0x14001ea6f  mov     ecx, 102h
0x14001ea74  call    cs:__imp_ExAllocatePool2
0x14001ea7b  nop     dword ptr [rax+rax+00h]
0x14001ea80  mov     [rbp+4Fh+var_C8], rax
0x14001ea84  test    rax, rax
0x14001ea87  jnz     short loc_14001EA94
0x14001ea89  mov     r14d, 0C000009Ah
0x14001ea8f  jmp     loc_14001F672
0x14001ea94  mov     r8, r12; Size
0x14001ea97  xor     edx, edx; Val
0x14001ea99  mov     rcx, rax; void *
0x14001ea9c  call    memset
0x14001eaa1  movzx   r8d, word ptr [rbx]; Size
0x14001eaa5  mov     rdx, [rbx+8]; Src
0x14001eaa9  mov     rcx, [rbp+4Fh+var_C8]; void *
0x14001eaad  call    memmove
0x14001eab2  movzx   ecx, word ptr [rbx]
0x14001eab5  mov     rax, [rbp+4Fh+var_C8]
0x14001eab9  shr     rcx, 1
0x14001eabc  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x14001eac2  movzx   ecx, word ptr [rbx]
0x14001eac5  mov     rax, [rbp+4Fh+var_C8]
0x14001eac9  movzx   r8d, word ptr [rdi]; Size
0x14001eacd  mov     rdx, [r13+58h]; Src
0x14001ead1  shr     ecx, 1
0x14001ead3  inc     ecx
0x14001ead5  lea     rcx, [rax+rcx*2]; void *
0x14001ead9  call    memmove
0x14001eade  mov     r14d, [r14+80h]
0x14001eae5  mov     [rbp+4Fh+arg_10], r14d
0x14001eae9  test    r14d, r14d
0x14001eaec  jz      short loc_14001EB2C
0x14001eaee  mov     rbx, cs:WPP_GLOBAL_Control
0x14001eaf5  lea     rax, WPP_GLOBAL_Control
0x14001eafc  cmp     rbx, rax
0x14001eaff  jz      loc_14001F672
0x14001eb05  test    dword ptr [rbx+2Ch], 2000h
0x14001eb0c  jz      loc_14001F672
0x14001eb12  mov     rbx, [rbx+18h]
0x14001eb16  call    cs:__imp_PsGetCurrentThreadId
0x14001eb1d  nop     dword ptr [rax+rax+00h]
0x14001eb22  mov     edx, 32h ; '2'
0x14001eb27  jmp     loc_14001E8B1
0x14001eb2c  mov     al, [rsi+205h]
0x14001eb32  mov     dil, [rsi+204h]
0x14001eb39  mov     rsi, [rsi+1C8h]
0x14001eb40  mov     byte ptr [rbp+4Fh+arg_20], al
0x14001eb43  mov     rax, [rbp+4Fh+arg_8]
0x14001eb47  mov     [rsp+130h+ValueName.Buffer], rsi
0x14001eb4c  mov     r12d, [rax+1D8h]
0x14001eb53  mov     r13d, [rax+1C0h]
0x14001eb5a  mov     [rsp+130h+var_F0], r12d
0x14001eb5f  mov     [rbp+4Fh+var_A8], r13d
0x14001eb63  mov     rbx, cs:WPP_GLOBAL_Control
0x14001eb6a  lea     rax, WPP_GLOBAL_Control
0x14001eb71  cmp     rbx, rax
0x14001eb74  jz      short loc_14001EBAB
0x14001eb76  test    dword ptr [rbx+2Ch], 4000h
0x14001eb7d  jz      short loc_14001EBAB
0x14001eb7f  mov     rbx, [rbx+18h]
0x14001eb83  call    cs:__imp_PsGetCurrentThreadId
0x14001eb8a  nop     dword ptr [rax+rax+00h]
0x14001eb8f  mov     edx, 33h ; '3'
0x14001eb94  mov     dword ptr [rsp+130h+var_110], r13d
0x14001eb99  mov     r9, rax
0x14001eb9c  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001eba3  mov     rcx, rbx
0x14001eba6  call    WPP_SF_qD
0x14001ebab  mov     r8, r12; Size
0x14001ebae  xor     edx, edx; Val
0x14001ebb0  mov     rcx, rsi; void *
0x14001ebb3  call    memset
0x14001ebb8  test    dil, dil
0x14001ebbb  jz      short loc_14001EBD3
0x14001ebbd  mov     rax, [r15]
0x14001ebc0  add     rax, 40h ; '@'
0x14001ebc4  mov     dword ptr [r15+0Ch], 0
0x14001ebcc  mov     [r15+818h], rax
0x14001ebd3  mov     eax, [r15+8]
0x14001ebd7  cmp     [r15+0Ch], eax
0x14001ebdb  jnz     short loc_14001EC41
0x14001ebdd  mov     rbx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
