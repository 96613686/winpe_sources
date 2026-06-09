# FatLocateDirent

- ea: `0x140031e8c`
- end: `0x140032de3`
- name: `FatLocateDirent`
- size: `3927`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, PCUNICODE_STRING SourceString, __int64)`
- caller_count: `10`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14000363c`
- `0x1400268c0`
- `0x14002c910`
- `0x14002ed1c`
- `0x140030b04`
- `0x140031d74`
- `0x140032dec`
- `0x1400333d0`
- `0x14003bea4`
- `0x1400447c8`

## callees

- `0x14000c230`
- `0x14000c380`
- `0x140024584`
- `0x1400302a8`
- `0x14003055c`
- `0x140031908`
- `0x140031938`
- `0x140031e8c`
- `0x14003958c`
- `0x140044518`
- `0x140048680`
- `0x1400486ec`

## import_xrefs

- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003281c`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140032a7a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140032c6e`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14003281c`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140032a7a`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140032c6e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400327f1`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140032a4f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140032c43`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400327f1`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140032a4f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140032c43`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14003287e`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400328e0`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x140032945`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14003299b`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x140032cde`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x140032d35`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14003287e`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x1400328e0`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x140032945`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x14003299b`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x140032cde`
- `ntoskrnl!FsRtlAreNamesEqual` at `0x140032d35`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140032cc2`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140032cc2`
- `ntoskrnl!FsRtlIsDbcsInExpression` at `0x140032b7c`
- `ntoskrnl!FsRtlIsDbcsInExpression` at `0x140032b7c`
- `ntoskrnl!CcUnpinData` at `0x1400322ce`
- `ntoskrnl!CcUnpinData` at `0x140032357`
- `ntoskrnl!CcUnpinData` at `0x14003239e`
- `ntoskrnl!CcUnpinData` at `0x140032d60`
- `ntoskrnl!CcUnpinData` at `0x1400322ce`
- `ntoskrnl!CcUnpinData` at `0x140032357`
- `ntoskrnl!CcUnpinData` at `0x14003239e`
- `ntoskrnl!CcUnpinData` at `0x140032d60`
- `ntoskrnl!ExRaiseStatus` at `0x1400325c9`
- `ntoskrnl!ExRaiseStatus` at `0x14003282a`
- `ntoskrnl!ExRaiseStatus` at `0x140032a88`
- `ntoskrnl!ExRaiseStatus` at `0x140032c7c`
- `ntoskrnl!ExRaiseStatus` at `0x1400325c9`
- `ntoskrnl!ExRaiseStatus` at `0x14003282a`
- `ntoskrnl!ExRaiseStatus` at `0x140032a88`
- `ntoskrnl!ExRaiseStatus` at `0x140032c7c`

## pseudocode

```c
__int64 __fastcall FatLocateDirent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int *a5,
        PVOID *a6,
        PVOID *a7,
        unsigned int *a8,
        _BYTE *a9,
        UNICODE_STRING *SourceString,
        _WORD *a11)
{
  UNICODE_STRING *v13; // r15
  __int64 v14; // r8
  PVOID v15; // r9
  NTSTATUS v16; // r12d
  PWSTR v17; // rcx
  int v18; // eax
  size_t v19; // r8
  __int64 v20; // rdx
  PWSTR Buffer; // rcx
  char v22; // al
  int v23; // r9d
  char IsPfile; // al
  __int64 v25; // rcx
  char v26; // al
  PVOID *v27; // rcx
  PVOID *v28; // rsi
  _QWORD *v29; // rdx
  char v30; // r13
  __int64 v31; // r11
  PVOID v32; // rcx
  PVOID v33; // rcx
  PVOID *v34; // rax
  unsigned int *v35; // r12
  unsigned __int8 *v36; // rsi
  char v37; // r9
  PWSTR v38; // rcx
  PWSTR v39; // rcx
  int v40; // eax
  unsigned int v41; // eax
  char v42; // r15
  __int64 v43; // rbx
  int v44; // r13d
  __int64 v45; // r10
  PWSTR v46; // rcx
  __int64 v47; // rcx
  unsigned int v48; // edx
  int v49; // r9d
  int v50; // eax
  char v51; // al
  UNICODE_STRING *v52; // r10
  char v53; // dl
  UNICODE_STRING v54; // xmm0
  NTSTATUS v55; // eax
  char v56; // si
  BOOLEAN v57; // al
  BOOLEAN v58; // al
  BOOLEAN v59; // al
  BOOLEAN v60; // al
  NTSTATUS v61; // eax
  char v62; // al
  int v63; // esi
  int v64; // eax
  __int64 v65; // rcx
  BOOLEAN IsDbcsInExpression; // al
  __int16 v67; // cx
  NTSTATUS v68; // eax
  struct _UNICODE_STRING *v69; // rcx
  BOOLEAN IsNameInExpression; // al
  BOOLEAN v71; // al
  PVOID v72; // rcx
  __int64 result; // rax
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  char v77; // [rsp+40h] [rbp-238h]
  char v78; // [rsp+41h] [rbp-237h]
  unsigned __int8 v79; // [rsp+42h] [rbp-236h]
  unsigned __int8 v80; // [rsp+43h] [rbp-235h]
  char v81; // [rsp+45h] [rbp-233h]
  char v82; // [rsp+46h] [rbp-232h]
  int v83; // [rsp+48h] [rbp-230h]
  bool v84; // [rsp+4Dh] [rbp-22Bh]
  int v85; // [rsp+5Ch] [rbp-21Ch]
  __int64 v86; // [rsp+60h] [rbp-218h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-208h] BYREF
  unsigned int *v88; // [rsp+80h] [rbp-1F8h]
  PVOID *v89; // [rsp+88h] [rbp-1F0h]
  int v90[2]; // [rsp+90h] [rbp-1E8h]
  _WORD *v91; // [rsp+98h] [rbp-1E0h]
  int v92; // [rsp+A0h] [rbp-1D8h]
  unsigned int v93; // [rsp+A4h] [rbp-1D4h]
  unsigned __int8 v94; // [rsp+A8h] [rbp-1D0h]
  PCUNICODE_STRING v95; // [rsp+B0h] [rbp-1C8h]
  int v96; // [rsp+B8h] [rbp-1C0h]
  UNICODE_STRING v97; // [rsp+C0h] [rbp-1B8h] BYREF
  UNICODE_STRING v98; // [rsp+D0h] [rbp-1A8h] BYREF
  int v99; // [rsp+E0h] [rbp-198h]
  int v100[2]; // [rsp+E8h] [rbp-190h]
  _BYTE *v101; // [rsp+F0h] [rbp-188h]
  unsigned int v102; // [rsp+F8h] [rbp-180h]
  struct _STRING v103; // [rsp+100h] [rbp-178h] BYREF
  UNICODE_STRING ConstantNameB; // [rsp+110h] [rbp-168h] BYREF
  UNICODE_STRING ConstantNameA; // [rsp+120h] [rbp-158h] BYREF
  UNICODE_STRING v106; // [rsp+130h] [rbp-148h] BYREF
  UNICODE_STRING v107; // [rsp+140h] [rbp-138h]
  struct _STRING Name; // [rsp+150h] [rbp-128h] BYREF
  struct _STRING Expression; // [rsp+160h] [rbp-118h] BYREF
  __int64 v110; // [rsp+170h] [rbp-108h] BYREF
  __int16 v111; // [rsp+178h] [rbp-100h]
  char v112; // [rsp+17Ah] [rbp-FEh]
  __int64 v113; // [rsp+180h] [rbp-F8h] BYREF
  __int16 v114; // [rsp+188h] [rbp-F0h]
  char v115; // [rsp+18Ah] [rbp-EEh]
  char v116; // [rsp+190h] [rbp-E8h] BYREF
  _BYTE v117[80]; // [rsp+1A0h] [rbp-D8h] BYREF
  char v118; // [rsp+1F0h] [rbp-88h] BYREF

  *(_QWORD *)v90 = a2;
  *(_QWORD *)v100 = a1;
  v91 = a11;
  v13 = SourceString;
  v95 = SourceString;
  v89 = a7;
  v14 = (__int64)a8;
  v88 = a8;
  v101 = a9;
  v15 = 0;
  v16 = 0;
  LODWORD(v86) = 0;
  v103 = 0;
  DestinationString = 0;
  *(_QWORD *)&v97.Length = 5242880;
  v82 = 0;
  v98 = 0;
  v81 = 0;
  v106 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  LOBYTE(v92) = 0;
  ConstantNameA = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v84 = 0;
  v107 = 0;
  ConstantNameB = 0;
  v77 = 0;
  v80 = 0;
  v83 = 0;
  v85 = 0;
  v79 = 0;
  v93 = 0;
  v97.Buffer = (PWSTR)v117;
  v17 = (PWSTR)*(unsigned int *)(*(_QWORD *)(a2 + 184) + 200LL);
  if ( ((unsigned int)v17 & 0x400000) != 0 )
  {
    if ( a5 )
    {
      v18 = *a5;
      if ( (*a5 & 0xF) != 0 && !*(_BYTE *)(a3 + 8) )
      {
        if ( (v18 & 8) != 0 )
        {
          FatEnsureStringBufferEnough(&v97);
          v82 = 1;
          v19 = *(unsigned __int16 *)(a3 + 48);
          v97.Length = v19 + 24;
          memmove(v97.Buffer, *(const void **)(a3 + 56), v19);
          v20 = *(unsigned __int16 *)(a3 + 48);
          Buffer = v97.Buffer;
          *(_QWORD *)((char *)v97.Buffer + v20) = *(_QWORD *)L".PFILE";
          *(_DWORD *)((char *)Buffer + v20 + 8) = *(_DWORD *)L"LE";
          a2 = *(unsigned __int16 *)(a3 + 48);
          v17 = v97.Buffer;
          *(_QWORD *)((char *)v97.Buffer + a2 + 12) = *(_QWORD *)L".PFILE";
          *(_DWORD *)((char *)v17 + a2 + 20) = *(_DWORD *)L"LE";
          if ( (*a5 & 4) != 0 )
          {
            v98.Length = v97.Length - 12;
            v98.MaximumLength = v97.MaximumLength;
            v98.Buffer = v97.Buffer;
          }
        }
        else if ( (v18 & 4) != 0 )
        {
          *(_DWORD *)&v98.Length = 5242880;
          v98.Buffer = (PWSTR)v117;
          FatEnsureStringBufferEnough(&v98);
          v81 = 1;
          memmove(v98.Buffer, *(const void **)(a3 + 56), *(unsigned __int16 *)(a3 + 48));
          a2 = *(unsigned __int16 *)(a3 + 48);
          v17 = v98.Buffer;
          *(_QWORD *)((char *)v98.Buffer + a2) = *(_QWORD *)L".PFILE";
          *(_DWORD *)((char *)v17 + a2 + 8) = *(_DWORD *)L"LE";
        }
        if ( (*a5 & 2) != 0 )
        {
          v106.Buffer = *(PWSTR *)(a3 + 56);
          v106.MaximumLength = *(_WORD *)(a3 + 50);
          v106.Length = *(_WORD *)(a3 + 48);
          v22 = FatConvertQueryStringTo8dot3(v17, &v106, &v113);
          v23 = (unsigned __int8)v92;
          if ( v22 )
            v23 = 1;
          v92 = v23;
        }
        if ( (*a5 & 1) != 0 )
        {
          LOBYTE(a2) = 1;
          IsPfile = FatFileExtensionIsPfile(a3 + 48, a2);
          v15 = 0;
          if ( IsPfile )
          {
            ConstantNameA.Buffer = *(PWSTR *)(a3 + 56);
            ConstantNameA.MaximumLength = *(_WORD *)(a3 + 50);
            ConstantNameA.Length = *(_WORD *)(a3 + 48) - 12;
            v26 = FatConvertQueryStringTo8dot3(v25, &ConstantNameA, &v110);
            v15 = 0;
            v84 = v26 != 0;
          }
          else
          {
            *a5 &= ~1u;
          }
        }
        else
        {
          v15 = 0;
        }
        v14 = (__int64)v88;
      }
    }
  }
  v103.MaximumLength = 12;
  v103.Buffer = &v116;
  *(_DWORD *)&DestinationString.Length = 0x400000;
  DestinationString.Buffer = (PWSTR)&v118;
  ConstantNameB = DestinationString;
  v27 = v89;
  if ( !*v89 )
    goto LABEL_25;
  if ( ((a4 ^ *(_DWORD *)v14) & 0xFFFFF000) != 0 )
  {
    CcUnpinData(*v89);
    v27 = v89;
    v15 = 0;
    *v89 = 0;
LABEL_25:
    v28 = a6;
    goto LABEL_26;
  }
  v28 = a6;
  *a6 = (char *)*a6 + ((a4 - *(_DWORD *)v14) & 0xFFFFFFE0);
  v27 = v89;
LABEL_26:
  if ( SourceString )
    SourceString->Length = 0;
  if ( v91 )
    *v91 = 0;
  if ( v101 )
    *v101 = 0;
  v29 = v88;
  *v88 = (a4 + 31) & 0xFFFFFFE0;
  while ( 1 )
  {
    v30 = (char)v15;
    v31 = *(_QWORD *)v90;
    if ( *(_DWORD *)v29 < *(_DWORD *)(*(_QWORD *)v90 + 24LL) )
    {
      if ( (*(_DWORD *)v29 & 0xFFF) == 0 || *v27 == v15 )
      {
        v33 = *v27;
        if ( v33 )
        {
          CcUnpinData(v33);
          v34 = v89;
          LOBYTE(v15) = 0;
          *v89 = 0;
          LODWORD(v31) = v90[0];
        }
        else
        {
          v34 = v89;
        }
        v35 = v88;
        FatReadDirectoryFile(v100[0], v31, *v88 & 0xFFFFF000, 4096, (char)v15, v34, v28, (__int64)&v86);
        *v28 = (char *)*v28 + (*v35 & 0xFFF);
        v16 = v86;
        v31 = *(_QWORD *)v90;
        v15 = 0;
LABEL_42:
        v27 = v89;
      }
    }
    else
    {
      v16 = -1073741807;
      LODWORD(v86) = -1073741807;
      v32 = *v27;
      if ( !v32 )
        goto LABEL_42;
      CcUnpinData(v32);
      v27 = v89;
      v15 = 0;
      *v89 = 0;
      v31 = *(_QWORD *)v90;
    }
    if ( v16 == -1073741807 )
      break;
    v36 = (unsigned __int8 *)*v28;
    v29 = (_QWORD *)*v36;
    if ( !(_BYTE)v29 )
      break;
    if ( (_BYTE)v29 == 0xE5 )
    {
      v77 = (char)v15;
LABEL_47:
      v15 = 0;
      goto LABEL_48;
    }
    if ( (byte_140017D4C & 1) != 0 && v13 && v36[11] == 15 )
    {
      v37 = v77;
      if ( v77 )
      {
        if ( ((unsigned __int8)v29 & 0x40) != 0 || (_DWORD)v29 != v79 - 1 || v36[13] != v80 || *((_WORD *)v36 + 13) )
        {
          v37 = 0;
          v77 = 0;
        }
        else
        {
          v14 = (unsigned int)(v85 - 13);
          v85 = v14;
          v96 = v14;
          v38 = v13->Buffer;
          *(_QWORD *)&v38[v14] = *(_QWORD *)(v36 + 1);
          v38[v14 + 4] = *(_WORD *)(v36 + 9);
          v39 = v13->Buffer;
          *(_QWORD *)&v39[(unsigned int)(v14 + 5)] = *(_QWORD *)(v36 + 14);
          *(_DWORD *)&v39[(unsigned int)(v14 + 5) + 4] = *(_DWORD *)(v36 + 22);
          *(_DWORD *)&v13->Buffer[(unsigned int)(v14 + 11)] = *((_DWORD *)v36 + 7);
          v79 = *v36;
          v93 = *v88;
          v102 = v93;
        }
        if ( v37 )
          goto LABEL_47;
      }
      v40 = *v36;
      v15 = 0;
      if ( (v40 & 0x40) != 0 )
      {
        v41 = v40 & 0xFFFFFFBF;
        if ( v41 <= 0x14 && !*((_WORD *)v36 + 13) )
        {
          v42 = 0;
          v79 = v41;
          if ( !(_BYTE)v41 )
          {
            v43 = *(_QWORD *)v100;
            FatPopUpFileCorrupt(*(_QWORD *)v100, v31);
            *(_DWORD *)(v43 + 72) = -1073741566;
            ExRaiseStatus(-1073741566);
          }
          v44 = 13 * (unsigned __int8)v41;
          v85 = v44 - 13;
          v96 = v44 - 13;
          FatEnsureStringBufferEnough(v95);
          v45 = (unsigned int)(v44 - 13);
          v14 = (__int64)v95;
          v46 = v95->Buffer;
          *(_QWORD *)&v46[v45] = *(_QWORD *)(v36 + 1);
          v46[v45 + 4] = *(_WORD *)(v36 + 9);
          v47 = *(_QWORD *)(v14 + 8);
          *(_QWORD *)(v47 + 2LL * (unsigned int)(v45 + 5)) = *(_QWORD *)(v36 + 14);
          *(_DWORD *)(v47 + 2LL * (unsigned int)(v45 + 5) + 8) = *(_DWORD *)(v36 + 22);
          *(_DWORD *)(*(_QWORD *)(v14 + 8) + 2LL * (unsigned int)(v45 + 11)) = *((_DWORD *)v36 + 7);
          v48 = v44 - 13;
          while ( 1 )
          {
            v49 = v45;
            if ( (_DWORD)v45 == v44 )
              break;
            v14 = *(unsigned __int16 *)(*(_QWORD *)(v14 + 8) + 2LL * v48);
            if ( v42 )
            {
              if ( (_WORD)v14 != 0xFFFF )
                break;
            }
            else if ( !(_WORD)v14 )
            {
              v83 = v45;
              v99 = v45;
              v42 = 1;
            }
            LODWORD(v45) = v45 + 1;
            v85 = v49 + 1;
            v48 = v49 + 1;
            v96 = v49 + 1;
            v14 = (__int64)v95;
          }
          v15 = 0;
          if ( v48 == v44 )
          {
            v50 = v83;
            if ( !v42 )
              v50 = v45;
            v83 = v50;
            v99 = v50;
            v85 = v48 - 13;
            v96 = v48 - 13;
            v77 = 1;
            v80 = v36[13];
            v94 = v80;
            v93 = *v88;
            v102 = v93;
          }
          v13 = (UNICODE_STRING *)v95;
        }
      }
      goto LABEL_48;
    }
    if ( (v36[11] & 8) != 0 )
    {
      if ( (*(_DWORD *)(a3 + 4) & 0x4000) != 0 )
        goto LABEL_169;
      goto LABEL_48;
    }
    if ( v77 != (_BYTE)v15
      && *v88 == v93 + 32LL
      && v85 == (_DWORD)v15
      && (v51 = FatComputeLfnChecksum(v36), v15 = 0, v51 == v80) )
    {
      v53 = 1;
      v78 = 1;
      v13->Length = 2 * v83;
      v54 = *v13;
      v107 = *v13;
      if ( v52 )
        *v52 = v54;
    }
    else
    {
      v53 = (char)v15;
      v78 = (char)v15;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(v31 + 184) + 200LL) & 0x400000) != 0 && v53 && a5 && (*a5 & 0xF) != 0 )
    {
      FatEnsureStringBufferEnough(&DestinationString);
      v16 = RtlUpcaseUnicodeString(&DestinationString, v13, 0);
      LODWORD(v86) = v16;
      if ( v16 < 0 )
      {
        *(_DWORD *)(*(_QWORD *)v100 + 72LL) = v16;
        v55 = FsRtlNormalizeNtstatus(v16, -1073741591);
        ExRaiseStatus(v55);
      }
      v56 = FatFileExtensionIsPfile(&DestinationString, 0);
      ConstantNameB = DestinationString;
      v30 = 1;
      v15 = 0;
      if ( (*a5 & 1) != 0 )
      {
        v57 = FsRtlAreNamesEqual(&ConstantNameA, &DestinationString, (*(_DWORD *)(a3 + 4) & 0x1000) != 0, 0);
        v15 = 0;
        if ( v57 )
        {
          *a5 |= 0x10u;
        }
        else if ( v84 && (unsigned __int8)FatFast8dot3Check(&v110, *a6, v14, 0) )
        {
          *a5 |= 0x110u;
        }
      }
      if ( (*a5 & 2) != 0 )
      {
        v58 = FsRtlAreNamesEqual(&v106, &DestinationString, (*(_DWORD *)(a3 + 4) & 0x1000) != 0, 0);
        v15 = 0;
        if ( v58 )
        {
          *a5 |= 0x20u;
        }
        else if ( (_BYTE)v92 && (unsigned __int8)FatFast8dot3Check(&v113, *a6, v14, 0) )
        {
          *a5 |= 0x220u;
        }
      }
      if ( (*a5 & 4) != 0 )
      {
        v59 = FsRtlAreNamesEqual(&v98, &DestinationString, (*(_DWORD *)(a3 + 4) & 0x1000) != 0, 0);
        v15 = 0;
        if ( v59 )
        {
          *a5 |= 0x40u;
          if ( (*((_BYTE *)*a6 + 12) & 1) != 0 )
          {
            if ( v56 )
              *a5 |= 0x400u;
          }
        }
      }
      if ( (*a5 & 8) != 0
        && (v60 = FsRtlAreNamesEqual(&v97, &DestinationString, (*(_DWORD *)(a3 + 4) & 0x1000) != 0, 0), v15 = 0, v60)
        && (*a5 |= 0x80u, (*((_BYTE *)*a6 + 12) & 1) != 0) )
      {
        v31 = *(_QWORD *)v90;
        if ( v56 )
          *a5 |= 0x800u;
      }
      else
      {
        v31 = *(_QWORD *)v90;
      }
    }
    if ( !v13
      || (*(_DWORD *)(*(_QWORD *)(v31 + 184) + 200LL) & 0x400000) == 0
      || v78 == (_BYTE)v15
      || a5 && (*a5 & 0x10000000) != 0 )
    {
      v29 = a6;
    }
    else
    {
      v29 = a6;
      if ( (*((_BYTE *)*a6 + 12) & 1) != 0 )
      {
        if ( !v30 )
        {
          FatEnsureStringBufferEnough(&DestinationString);
          v16 = RtlUpcaseUnicodeString(&DestinationString, v13, 0);
          LODWORD(v86) = v16;
          if ( v16 < 0 )
          {
            *(_DWORD *)(*(_QWORD *)v100 + 72LL) = v16;
            v61 = FsRtlNormalizeNtstatus(v16, -1073741591);
            ExRaiseStatus(v61);
          }
          ConstantNameB = DestinationString;
          v30 = 1;
        }
        LOBYTE(v29) = 1;
        v62 = FatFileExtensionIsPfile(&DestinationString, v29);
        v15 = 0;
        v29 = a6;
        if ( v62 )
        {
          v13->Length -= 12;
          DestinationString.Length -= 12;
          v63 = v83 - 6;
          v83 = v63;
          v99 = v63;
          goto LABEL_131;
        }
      }
    }
    LOWORD(v63) = v83;
LABEL_131:
    v64 = *(_DWORD *)(a3 + 4);
    if ( (v64 & 1) != 0 )
      goto LABEL_169;
    if ( (v64 & 2) == 0 )
    {
      v65 = *v29;
      if ( *(_BYTE *)(a3 + 8) == (_BYTE)v15 )
      {
        if ( (*(_BYTE *)(v65 + 11) & 8) == 0
          && *(_DWORD *)(a3 + 32) == *(_DWORD *)v65
          && *(_DWORD *)(a3 + 36) == *(_DWORD *)(v65 + 4)
          && *(_WORD *)(a3 + 40) == *(_WORD *)(v65 + 8)
          && *(_BYTE *)(a3 + 42) == *(_BYTE *)(v65 + 10) )
        {
          goto LABEL_139;
        }
      }
      else
      {
        Fat8dot3ToString(v65, *v29, 0, &v103);
        if ( v103.Length == 2 && *(_WORD *)v103.Buffer == 11822 && *(_WORD *)(a3 + 32) > 1u )
          v103.Length = 1;
        Name = v103;
        Expression = *(struct _STRING *)(a3 + 32);
        IsDbcsInExpression = FsRtlIsDbcsInExpression(&Expression, &Name);
        v15 = 0;
        if ( IsDbcsInExpression )
        {
LABEL_139:
          if ( v101 )
            *v101 = 1;
          *(_DWORD *)(a3 + 4) |= 0x800u;
          goto LABEL_169;
        }
      }
    }
    if ( v78 != (_BYTE)v15 )
    {
      if ( *(_BYTE *)(a3 + 8) == (_BYTE)v15 )
      {
        v67 = *(_WORD *)(a3 + 48);
        if ( v67 != 2 * (_WORD)v63 && v67 != v107.Length )
        {
LABEL_151:
          v13->Length = (unsigned __int16)v15;
          v107.Length = (unsigned __int16)v15;
          if ( v91 )
            *v91 = (_WORD)v15;
          goto LABEL_48;
        }
      }
      if ( !v30 )
      {
        FatEnsureStringBufferEnough(&DestinationString);
        v16 = RtlUpcaseUnicodeString(&DestinationString, v13, 0);
        LODWORD(v86) = v16;
        if ( v16 < 0 )
        {
          *(_DWORD *)(*(_QWORD *)v100 + 72LL) = v16;
          v68 = FsRtlNormalizeNtstatus(v16, -1073741591);
          ExRaiseStatus(v68);
        }
        ConstantNameB = DestinationString;
        FatFileExtensionIsPfile(&DestinationString, 0);
        LOBYTE(v15) = 0;
      }
      v69 = (struct _UNICODE_STRING *)(a3 + 48);
      if ( *(_BYTE *)(a3 + 8) == (_BYTE)v15 )
      {
        v71 = FsRtlAreNamesEqual(v69, &DestinationString, (*(_DWORD *)(a3 + 4) & 0x1000) != 0, 0);
        v15 = 0;
        if ( v71 )
          goto LABEL_169;
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)v90 + 184LL) + 200LL) & 0x400000) != 0
          && ConstantNameB.Length != DestinationString.Length )
        {
          IsNameInExpression = FsRtlAreNamesEqual(
                                 (PCUNICODE_STRING)(a3 + 48),
                                 &ConstantNameB,
                                 (*(_DWORD *)(a3 + 4) & 0x1000) != 0,
                                 0);
          goto LABEL_163;
        }
      }
      else
      {
        IsNameInExpression = FsRtlIsNameInExpression(v69, &DestinationString, 1u, 0);
LABEL_163:
        v15 = 0;
        if ( IsNameInExpression )
          goto LABEL_169;
      }
      if ( !v78 )
        goto LABEL_48;
      goto LABEL_151;
    }
LABEL_48:
    v29 = v88;
    *v88 += 32;
    v28 = a6;
    *a6 = (char *)*a6 + 32;
    v27 = v89;
  }
  v72 = *v27;
  if ( v72 )
  {
    CcUnpinData(v72);
    v15 = 0;
    *v89 = 0;
  }
  *a6 = v15;
  *v88 = (unsigned int)v15;
LABEL_169:
  result = FatFreeStringBuffer(&DestinationString, v29, v14, v15);
  if ( v81 )
    result = FatFreeStringBuffer(&v98, v74, v75, v76);
  if ( v82 )
    return FatFreeStringBuffer(&v97, v74, v75, v76);
  return result;
}

```

## disassembly

```asm
0x140031e8c  mov     r11, rsp
0x140031e8f  push    rbx
0x140031e90  push    rsi
0x140031e91  push    rdi
0x140031e92  push    r12
0x140031e94  push    r13
0x140031e96  push    r14
0x140031e98  push    r15
0x140031e9a  sub     rsp, 240h
0x140031ea1  mov     rax, cs:__security_cookie
0x140031ea8  xor     rax, rsp
0x140031eab  mov     [rsp+278h+var_48], rax
0x140031eb3  mov     r13d, r9d
0x140031eb6  mov     rbx, r8
0x140031eb9  mov     qword ptr [rsp+278h+var_1E8], rdx
0x140031ec1  mov     qword ptr [rsp+278h+var_190], rcx
0x140031ec9  mov     rax, [rsp+278h+arg_50]
0x140031ed1  mov     [rsp+278h+var_1E0], rax
0x140031ed9  mov     r15, [rsp+278h+SourceString]
0x140031ee1  mov     [rsp+278h+var_1C8], r15
0x140031ee9  mov     r14, [rsp+278h+arg_20]
0x140031ef1  mov     rax, [rsp+278h+arg_28]
0x140031ef9  mov     [rsp+278h+var_228], rax
0x140031efe  mov     rax, [rsp+278h+arg_30]
0x140031f06  mov     [rsp+278h+var_1F0], rax
0x140031f0e  mov     r8, [rsp+278h+arg_38]
0x140031f16  mov     [rsp+278h+var_1F8], r8
0x140031f1e  mov     rax, [rsp+278h+arg_40]
0x140031f26  mov     [rsp+278h+var_188], rax
0x140031f2e  xor     r9d, r9d
0x140031f31  mov     r12d, r9d
0x140031f34  mov     dword ptr [rsp+278h+var_218], r9d
0x140031f39  xorps   xmm0, xmm0
0x140031f3c  movups  [rsp+278h+var_178], xmm0
0x140031f44  xorps   xmm1, xmm1
0x140031f47  movups  xmmword ptr [rsp+278h+DestinationString.Length], xmm1
0x140031f4c  mov     qword ptr [r11-1B8h], 500000h
0x140031f57  mov     [rsp+278h+var_232], r9b
0x140031f5c  movups  xmmword ptr [rsp+278h+var_1A8.Length], xmm0
0x140031f64  mov     [rsp+278h+var_233], r9b
0x140031f69  movups  xmmword ptr [rsp+278h+var_148.Length], xmm0
0x140031f71  xor     eax, eax
0x140031f73  mov     [r11-0F8h], rax
0x140031f7a  mov     [rsp+278h+var_F0], ax
0x140031f82  mov     [rsp+278h+var_EE], al
0x140031f89  mov     byte ptr [rsp+278h+var_1D8], r9b
0x140031f91  movups  xmmword ptr [rsp+278h+ConstantNameA.Length], xmm0
0x140031f99  mov     [r11-108h], rax
0x140031fa0  mov     [rsp+278h+var_100], ax
0x140031fa8  mov     [rsp+278h+var_FE], al
0x140031faf  mov     [rsp+278h+var_22B], r9b
0x140031fb4  movups  [rsp+278h+var_138], xmm0
0x140031fbc  movups  xmmword ptr [rsp+278h+ConstantNameB.Length], xmm1
0x140031fc4  mov     [rsp+278h+var_238], r9b
0x140031fc9  mov     [rsp+278h+var_235], r9b
0x140031fce  mov     [rsp+278h+var_230], r9d
0x140031fd3  mov     [rsp+278h+var_21C], r9d
0x140031fd8  mov     [rsp+278h+var_236], r9b
0x140031fdd  mov     [r11-1D4h], r9d
0x140031fe4  lea     rax, [r11-0D8h]
0x140031feb  mov     [r11-1B0h], rax
0x140031ff2  mov     rax, [rdx+0B8h]
0x140031ff9  mov     ecx, [rax+0C8h]
0x140031fff  bt      ecx, 16h
0x140032003  jnb     loc_14003223F
0x140032009  test    r14, r14
0x14003200c  jz      loc_14003223F
0x140032012  mov     eax, [r14]
0x140032015  test    al, 0Fh
0x140032017  jz      loc_14003223F
0x14003201d  cmp     [rbx+8], r9b
0x140032021  jnz     loc_14003223F
0x140032027  test    al, 8
0x140032029  jz      loc_1400320FC
0x14003202f  movzx   edx, word ptr [rbx+30h]
0x140032033  add     dx, 18h
0x140032037  lea     rcx, [r11-1B8h]
0x14003203e  call    FatEnsureStringBufferEnough
0x140032043  mov     edi, 1
0x140032048  mov     [rsp+278h+var_232], dil
0x14003204d  movzx   r8d, word ptr [rbx+30h]; Size
0x140032052  lea     eax, [r8+18h]
0x140032056  mov     [rsp+278h+var_1B8.Length], ax
0x14003205e  mov     rdx, [rbx+38h]; Src
0x140032062  mov     rcx, [rsp+278h+var_1B8.Buffer]; void *
0x14003206a  call    memmove
0x14003206f  movzx   edx, word ptr [rbx+30h]
0x140032073  mov     rcx, [rsp+278h+var_1B8.Buffer]
0x14003207b  movsd   xmm0, qword ptr cs:aPfile_0; ".PFILE"
0x140032083  movsd   qword ptr [rdx+rcx], xmm0
0x140032088  mov     eax, dword ptr cs:aPfile_0+8; "LE"
0x14003208e  mov     [rdx+rcx+8], eax
0x140032092  movzx   edx, word ptr [rbx+30h]
0x140032096  mov     rcx, [rsp+278h+var_1B8.Buffer]
0x14003209e  movsd   xmm0, qword ptr cs:aPfile_0; ".PFILE"
0x1400320a6  movsd   qword ptr [rdx+rcx+0Ch], xmm0
0x1400320ac  mov     eax, dword ptr cs:aPfile_0+8; "LE"
0x1400320b2  mov     [rdx+rcx+14h], eax
0x1400320b6  mov     eax, [r14]
0x1400320b9  lea     esi, [rdi+0Bh]
0x1400320bc  test    al, 4
0x1400320be  jz      loc_14003217C
0x1400320c4  movzx   eax, [rsp+278h+var_1B8.Length]
0x1400320cc  sub     ax, si
0x1400320cf  mov     [rsp+278h+var_1A8.Length], ax
0x1400320d7  movzx   eax, [rsp+278h+var_1B8.MaximumLength]
0x1400320df  mov     [rsp+278h+var_1A8.MaximumLength], ax
0x1400320e7  mov     rax, [rsp+278h+var_1B8.Buffer]
0x1400320ef  mov     [rsp+278h+var_1A8.Buffer], rax
0x1400320f7  jmp     loc_14003217C
0x1400320fc  mov     esi, 0Ch
0x140032101  test    al, 4
0x140032103  jz      short loc_140032177
0x140032105  mov     dword ptr [rsp+278h+var_1A8.Length], 500000h
0x140032110  lea     rax, [rsp+278h+var_D8]
0x140032118  mov     [rsp+278h+var_1A8.Buffer], rax
0x140032120  movzx   edx, word ptr [rbx+30h]
0x140032124  add     dx, si
0x140032127  lea     rcx, [rsp+278h+var_1A8]
0x14003212f  call    FatEnsureStringBufferEnough
0x140032134  lea     edi, [rsi-0Bh]
0x140032137  mov     [rsp+278h+var_233], dil
0x14003213c  movzx   r8d, word ptr [rbx+30h]; Size
0x140032141  mov     rdx, [rbx+38h]; Src
0x140032145  mov     rcx, [rsp+278h+var_1A8.Buffer]; void *
0x14003214d  call    memmove
0x140032152  movzx   edx, word ptr [rbx+30h]
0x140032156  mov     rcx, [rsp+278h+var_1A8.Buffer]
0x14003215e  movsd   xmm0, qword ptr cs:aPfile_0; ".PFILE"
0x140032166  movsd   qword ptr [rdx+rcx], xmm0
0x14003216b  mov     eax, dword ptr cs:aPfile_0+8; "LE"
0x140032171  mov     [rdx+rcx+8], eax
0x140032175  jmp     short loc_14003217C
0x140032177  mov     edi, 1
0x14003217c  mov     eax, [r14]
0x14003217f  test    al, 2
0x140032181  jz      short loc_1400321D6
0x140032183  mov     rax, [rbx+38h]
0x140032187  mov     [rsp+278h+var_148.Buffer], rax
0x14003218f  movzx   eax, word ptr [rbx+32h]
0x140032193  mov     [rsp+278h+var_148.MaximumLength], ax
0x14003219b  movzx   eax, word ptr [rbx+30h]
0x14003219f  mov     [rsp+278h+var_148.Length], ax
0x1400321a7  lea     r8, [rsp+278h+var_F8]
0x1400321af  lea     rdx, [rsp+278h+var_148]
0x1400321b7  call    FatConvertQueryStringTo8dot3
0x1400321bc  mov     r9d, [rsp+278h+var_1D8]
0x1400321c4  movzx   r9d, r9b
0x1400321c8  test    al, al
0x1400321ca  cmovnz  r9d, edi
0x1400321ce  mov     [rsp+278h+var_1D8], r9d
0x1400321d6  mov     eax, [r14]
0x1400321d9  test    dil, al
0x1400321dc  jz      short loc_140032249
0x1400321de  mov     dl, dil
0x1400321e1  lea     rcx, [rbx+30h]
0x1400321e5  call    FatFileExtensionIsPfile
0x1400321ea  xor     r9d, r9d
0x1400321ed  test    al, al
0x1400321ef  jz      short loc_140032239
0x1400321f1  mov     rax, [rbx+38h]
0x1400321f5  mov     [rsp+278h+ConstantNameA.Buffer], rax
0x1400321fd  movzx   eax, word ptr [rbx+32h]
0x140032201  mov     [rsp+278h+ConstantNameA.MaximumLength], ax
0x140032209  movzx   eax, word ptr [rbx+30h]
0x14003220d  sub     ax, si
0x140032210  mov     [rsp+278h+ConstantNameA.Length], ax
0x140032218  lea     r8, [rsp+278h+var_108]
0x140032220  lea     rdx, [rsp+278h+ConstantNameA]
0x140032228  call    FatConvertQueryStringTo8dot3
0x14003222d  xor     r9d, r9d
0x140032230  test    al, al
0x140032232  setnz   [rsp+278h+var_22B]
0x140032237  jmp     short loc_14003224C
0x140032239  and     dword ptr [r14], 0FFFFFFFEh
0x14003223d  jmp     short loc_14003224C
0x14003223f  mov     edi, 1
0x140032244  lea     esi, [rdi+0Bh]
0x140032247  jmp     short loc_140032254
0x140032249  xor     r9d, r9d
0x14003224c  mov     r8, [rsp+278h+var_1F8]
0x140032254  mov     word ptr [rsp+278h+var_178+2], si
0x14003225c  lea     rax, [rsp+278h+var_E8]
0x140032264  mov     qword ptr [rsp+278h+var_178+8], rax
0x14003226c  mov     dword ptr [rsp+278h+DestinationString.Length], 400000h
0x140032274  lea     rax, [rsp+278h+var_88]
0x14003227c  mov     [rsp+278h+DestinationString.Buffer], rax
0x140032281  movaps  xmm0, xmmword ptr [rsp+278h+DestinationString.Length]
0x140032286  movdqa  xmmword ptr [rsp+278h+ConstantNameB.Length], xmm0
0x14003228f  mov     rcx, [rsp+278h+var_1F0]
0x140032297  mov     rdx, [rcx]
0x14003229a  test    rdx, rdx
0x14003229d  jz      short loc_1400322E8
0x14003229f  mov     ecx, [r8]
0x1400322a2  mov     eax, ecx
0x1400322a4  xor     eax, r13d
0x1400322a7  test    eax, 0FFFFF000h
0x1400322ac  jnz     short loc_1400322CB
0x1400322ae  mov     eax, r13d
0x1400322b1  sub     eax, ecx
0x1400322b3  mov     ecx, eax
0x1400322b5  and     rcx, 0FFFFFFFFFFFFFFE0h
0x1400322b9  mov     rsi, [rsp+278h+var_228]
0x1400322be  add     [rsi], rcx
0x1400322c1  mov     rcx, [rsp+278h+var_1F0]
0x1400322c9  jmp     short loc_1400322ED
0x1400322cb  mov     rcx, rdx; Bcb
0x1400322ce  call    cs:__imp_CcUnpinData
0x1400322d5  nop     dword ptr [rax+rax+00h]
0x1400322da  mov     rcx, [rsp+278h+var_1F0]
0x1400322e2  xor     r9d, r9d
0x1400322e5  mov     [rcx], r9
0x1400322e8  mov     rsi, [rsp+278h+var_228]
0x1400322ed  test    r15, r15
0x1400322f0  jz      short loc_1400322F6
0x1400322f2  mov     [r15], r9w
0x1400322f6  mov     r10, [rsp+278h+var_1E0]
0x1400322fe  test    r10, r10
0x140032301  jz      short loc_140032307
0x140032303  mov     [r10], r9w
0x140032307  mov     rax, [rsp+278h+var_188]
0x14003230f  test    rax, rax
0x140032312  jz      short loc_140032317
0x140032314  mov     [rax], r9b
0x140032317  lea     eax, [r13+1Fh]
0x14003231b  and     eax, 0FFFFFFE0h
0x14003231e  mov     rdx, [rsp+278h+var_1F8]
0x140032326  mov     [rdx], eax
0x140032328  mov     r13b, r9b
0x14003232b  mov     [rsp+278h+var_234], r9b
0x140032330  mov     eax, [rdx]
0x140032332  mov     r11, qword ptr [rsp+278h+var_1E8]
0x14003233a  cmp     eax, [r11+18h]
0x14003233e  jb      short loc_140032386
0x140032340  mov     r12d, 0C0000011h
0x140032346  mov     dword ptr [rsp+278h+var_218], r12d
0x14003234b  mov     rcx, [rcx]; Bcb
0x14003234e  test    rcx, rcx
0x140032351  jz      loc_140032430
0x140032357  call    cs:__imp_CcUnpinData
0x14003235e  nop     dword ptr [rax+rax+00h]
0x140032363  mov     rcx, [rsp+278h+var_1F0]
0x14003236b  xor     r9d, r9d
0x14003236e  mov     [rcx], r9
0x140032371  mov     r10, [rsp+278h+var_1E0]
0x140032379  mov     r11, qword ptr [rsp+278h+var_1E8]
0x140032381  jmp     loc_140032438
0x140032386  test    eax, 0FFFh
0x14003238b  jz      short loc_140032396
0x14003238d  cmp     [rcx], r9
0x140032390  jnz     loc_140032438
0x140032396  mov     rcx, [rcx]; Bcb
0x140032399  test    rcx, rcx
0x14003239c  jz      short loc_1400323C2
0x14003239e  call    cs:__imp_CcUnpinData
0x1400323a5  nop     dword ptr [rax+rax+00h]
0x1400323aa  mov     rax, [rsp+278h+var_1F0]
0x1400323b2  xor     r9d, r9d
0x1400323b5  mov     [rax], r9
0x1400323b8  mov     r11, qword ptr [rsp+278h+var_1E8]
0x1400323c0  jmp     short loc_1400323CA
0x1400323c2  mov     rax, [rsp+278h+var_1F0]
0x1400323ca  mov     r12, [rsp+278h+var_1F8]
0x1400323d2  mov     r8d, [r12]
0x1400323d6  and     r8d, 0FFFFF000h; int
0x1400323dd  lea     rcx, [rsp+278h+var_218]
0x1400323e2  mov     [rsp+278h+var_240], rcx; __int64
0x1400323e7  mov     [rsp+278h+var_248], rsi; PVOID *
0x1400323ec  mov     [rsp+278h+var_250], rax; PVOID *
0x1400323f1  mov     [rsp+278h+var_258], r9b; char
0x1400323f6  mov     r9d, 1000h; int
0x1400323fc  mov     rdx, r11; int
0x1400323ff  mov     rcx, qword ptr [rsp+278h+var_190]; int
0x140032407  call    FatReadDirectoryFile
0x14003240c  mov     eax, [r12]
0x140032410  and     eax, 0FFFh
0x140032415  add     [rsi], rax
0x140032418  mov     r12d, dword ptr [rsp+278h+var_218]
0x14003241d  mov     r10, [rsp+278h+var_1E0]
0x140032425  mov     r11, qword ptr [rsp+278h+var_1E8]
0x14003242d  xor     r9d, r9d
0x140032430  mov     rcx, [rsp+278h+var_1F0]
0x140032438  cmp     r12d, 0C0000011h
0x14003243f  jz      loc_140032D58
0x140032445  mov     rsi, [rsi]
0x140032448  movzx   edx, byte ptr [rsi]
0x14003244b  test    dl, dl
0x14003244d  jz      loc_140032D58
0x140032453  cmp     dl, 0E5h
0x140032456  jnz     short loc_140032486
0x140032458  mov     [rsp+278h+var_238], r9b
0x14003245d  mov     [rsp+278h+var_22C], r9b
0x140032462  xor     r9d, r9d
0x140032465  mov     rdx, [rsp+278h+var_1F8]
0x14003246d  add     dword ptr [rdx], 20h ; ' '
0x140032470  mov     rsi, [rsp+278h+var_228]
0x140032475  add     qword ptr [rsi], 20h ; ' '
0x140032479  mov     rcx, [rsp+278h+var_1F0]
0x140032481  jmp     loc_140032328
0x140032486  test    cs:byte_140017D4C, dil
  ... truncated ...
```
