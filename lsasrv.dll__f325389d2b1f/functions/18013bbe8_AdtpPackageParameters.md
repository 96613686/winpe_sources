# AdtpPackageParameters

- ea: `0x18013bbe8`
- end: `0x18013cbaf`
- name: `AdtpPackageParameters`
- size: `4039`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18013cbb8`

## callees

- `0x180079d78`
- `0x1800bd6ec`
- `0x18013b9e0`
- `0x18013baf8`
- `0x18013bbe8`
- `0x18013cf40`
- `0x18013d454`
- `0x18013d744`
- `0x18013db10`
- `0x18013f3ec`
- `0x18013f670`
- `0x18013fd48`
- `0x180140138`
- `0x180140384`
- `0x180140478`
- `0x180140608`
- `0x180140874`
- `0x180140934`
- `0x180140b34`
- `0x180140da8`
- `0x180141298`
- `0x18014140c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18013c69b`
- `ntdll!RtlFreeHeap` at `0x18013c7dd`
- `ntdll!RtlFreeHeap` at `0x18013c80e`
- `ntdll!RtlFreeHeap` at `0x18013cb37`
- `ntdll!RtlFreeHeap` at `0x18013cb64`
- `ntdll!RtlFreeHeap` at `0x18013c69b`
- `ntdll!RtlFreeHeap` at `0x18013c7dd`
- `ntdll!RtlFreeHeap` at `0x18013c80e`
- `ntdll!RtlFreeHeap` at `0x18013cb37`
- `ntdll!RtlFreeHeap` at `0x18013cb64`
- `ntdll!RtlpConvertRelativeToAbsoluteSecurityAttribute` at `0x18013c8d3`
- `ntdll!RtlpConvertRelativeToAbsoluteSecurityAttribute` at `0x18013c92a`
- `ntdll!RtlpConvertRelativeToAbsoluteSecurityAttribute` at `0x18013c8d3`
- `ntdll!RtlpConvertRelativeToAbsoluteSecurityAttribute` at `0x18013c92a`
- `ntdll!RtlAllocateHeap` at `0x18013c878`
- `ntdll!RtlAllocateHeap` at `0x18013c900`
- `ntdll!RtlAllocateHeap` at `0x18013c878`
- `ntdll!RtlAllocateHeap` at `0x18013c900`
- `ntdll!RtlValidSid` at `0x18013be99`
- `ntdll!RtlValidSid` at `0x18013be99`
- `ntdll!RtlLengthSid` at `0x18013bdf3`
- `ntdll!RtlLengthSid` at `0x18013be7d`
- `ntdll!RtlLengthSid` at `0x18013c647`
- `ntdll!RtlLengthSid` at `0x18013c6c5`
- `ntdll!RtlLengthSid` at `0x18013bdf3`
- `ntdll!RtlLengthSid` at `0x18013be7d`
- `ntdll!RtlLengthSid` at `0x18013c647`
- `ntdll!RtlLengthSid` at `0x18013c6c5`

## pseudocode

```c
__int64 __fastcall AdtpPackageParameters(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned __int16 *a7,
        __int64 a8)
{
  unsigned __int16 v8; // r14
  __int64 v9; // r8
  __int64 v10; // rbx
  _QWORD *v11; // r9
  __int64 v12; // r13
  unsigned int v13; // ecx
  __int64 v14; // r15
  int v15; // r11d
  int v16; // esi
  unsigned int v17; // eax
  __int64 v18; // r12
  int v19; // edx
  unsigned int *v20; // r10
  unsigned int v21; // ecx
  unsigned int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  ULONG v25; // eax
  __int64 v26; // rcx
  unsigned __int16 v27; // r14
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // rax
  void *v31; // rbx
  ULONG v32; // edi
  __int64 v33; // rcx
  __int64 v34; // rdi
  const UNICODE_STRING *v35; // rcx
  _WORD *v36; // rcx
  unsigned __int16 v37; // bx
  char *v38; // rdx
  int v39; // eax
  int v40; // edx
  __int64 *v41; // rcx
  __int64 v42; // rax
  __int64 v43; // r10
  unsigned __int16 *v44; // rbx
  unsigned int v45; // ecx
  __int64 v46; // rdi
  int v47; // edx
  int v48; // edx
  int v49; // edx
  int v50; // edx
  int v51; // edx
  int v52; // edx
  int v53; // edx
  __int64 v54; // rcx
  __int64 v55; // rax
  int v56; // ecx
  SIZE_T *p_Size; // r8
  __int64 *v58; // rcx
  PVOID *p_P; // rdx
  char v60; // bl
  unsigned __int16 *v61; // rdi
  int v62; // eax
  __int64 v63; // rbx
  unsigned int v64; // ecx
  int v65; // eax
  __int64 v66; // r8
  unsigned __int16 *v67; // rdi
  __int64 v68; // rbx
  __int64 v69; // rax
  __int64 v70; // r10
  unsigned int v71; // ecx
  __int64 v72; // r8
  int v73; // ecx
  __int64 v74; // rax
  int v75; // r9d
  __int64 v76; // r10
  __int64 v77; // r8
  __int64 v78; // rdx
  unsigned int v79; // ecx
  __int64 v80; // rcx
  unsigned __int16 *v81; // rdi
  void *v82; // rbx
  ULONG v83; // eax
  __int64 v84; // rcx
  __int16 *v85; // rbx
  char v86; // di
  ULONG v87; // eax
  __int64 v88; // rcx
  __int64 v89; // rax
  __int64 v90; // rax
  int v91; // edx
  __int64 v92; // rdi
  __int64 v93; // r10
  __int64 v94; // rcx
  unsigned __int16 v95; // r14
  __int64 v96; // rcx
  int v97; // edx
  __int64 v98; // rcx
  unsigned int v99; // esi
  unsigned int *v100; // rdi
  __int64 v101; // rbx
  void *v102; // r8
  int v103; // r9d
  int v104; // ecx
  __int64 i; // rbx
  __int64 v106; // rdx
  unsigned int v107; // r12d
  PVOID v108; // rax
  __int64 v109; // r8
  unsigned int v110; // eax
  __int64 v111; // r10
  unsigned __int16 *v112; // rdi
  __int64 v113; // rbx
  unsigned int v114; // ecx
  __int64 v115; // rbx
  void *v116; // r8
  PUNICODE_STRING DestinationString; // [rsp+28h] [rbp-81h]
  PUNICODE_STRING v119; // [rsp+38h] [rbp-71h]
  unsigned int v120; // [rsp+68h] [rbp-41h]
  unsigned int v121; // [rsp+6Ch] [rbp-3Dh]
  int v122; // [rsp+70h] [rbp-39h]
  _QWORD *Heap; // [rsp+78h] [rbp-31h]
  int v124; // [rsp+80h] [rbp-29h] BYREF
  char v125; // [rsp+84h] [rbp-25h] BYREF
  unsigned int v126; // [rsp+88h] [rbp-21h]
  PVOID P; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int16 *v128; // [rsp+98h] [rbp-11h]
  __int64 v130; // [rsp+100h] [rbp+57h] BYREF
  SIZE_T Size; // [rsp+108h] [rbp+5Fh] BYREF
  __int64 v132; // [rsp+110h] [rbp+67h]

  v132 = a4;
  LODWORD(Size) = a3;
  v130 = a2;
  v8 = 0;
  LODWORD(v9) = 0;
  v10 = a4;
  v124 = 0;
  v11 = 0;
  v120 = 0;
  Heap = 0;
  v12 = a1;
  if ( !a1 )
    goto LABEL_168;
  v13 = *(_DWORD *)(a1 + 8);
  v14 = a6;
  LOWORD(v15) = 0;
  v16 = 0;
  v122 = 0;
  v17 = 0;
  v121 = v13;
  while ( 1 )
  {
    v126 = v17;
    if ( v17 >= v13 )
      goto LABEL_159;
    if ( v8 >= 0x2Au || (unsigned __int16)v15 >= 0xEu )
      goto LABEL_168;
    v18 = 32LL * v17;
    v19 = *(_DWORD *)(v18 + v12 + 24);
    if ( v19 > 18 )
      break;
    if ( v19 == 18 )
    {
      v55 = 2LL * v8++;
      *(_QWORD *)(v14 + 8 * v55) = &v130;
      *(_QWORD *)(v14 + 8 * v55 + 8) = 8;
      goto LABEL_156;
    }
    if ( v19 > 9 )
    {
      v47 = v19 - 10;
      if ( !v47 )
        goto LABEL_97;
      v48 = v47 - 1;
      if ( !v48 )
        goto LABEL_65;
      v49 = v48 - 1;
      if ( !v49 )
        goto LABEL_65;
      v50 = v49 - 1;
      if ( v50 )
      {
        v51 = v50 - 1;
        if ( v51 )
        {
          v52 = v51 - 1;
          if ( v52 )
          {
            v53 = v52 - 1;
            if ( v53 )
            {
              if ( v53 != 1 )
                goto LABEL_168;
              v23 = AdtpBuildSidListString(
                      *(_QWORD *)(v18 + v12 + 48),
                      1,
                      (unsigned int)v14 + 16 * v8,
                      v10,
                      (__int64)&v124,
                      v8 + a8);
            }
            else
            {
              v23 = AdtpBuildStringListString(
                      *(_QWORD *)(v18 + v12 + 48),
                      0,
                      (unsigned int)v14 + 16 * v8,
                      v10,
                      (__int64)&v124,
                      v8 + a8);
            }
            goto LABEL_26;
          }
        }
LABEL_65:
        v54 = 2LL * v8;
        *(_QWORD *)(v14 + 8 * v54) = v18 + v12 + 32;
        *(_QWORD *)(v14 + 8 * v54 + 8) = 8;
        goto LABEL_49;
      }
      v41 = AdtpNullGuid;
      if ( *(_QWORD *)(v18 + v12 + 48) )
        v41 = *(__int64 **)(v18 + v12 + 48);
      v42 = 2LL * v8;
      *(_QWORD *)(v14 + 16LL * v8 + 8) = 16;
    }
    else
    {
      if ( v19 == 9 )
      {
        if ( *(_DWORD *)(v18 + v12 + 40) >= v17 )
          goto LABEL_168;
        v43 = 32LL * *(unsigned int *)(v18 + v12 + 40);
        if ( *(_DWORD *)(v43 + v12 + 24) != 1 )
          goto LABEL_168;
        v44 = (unsigned __int16 *)(a5 + 16LL * (unsigned __int16)v15);
        LODWORD(DestinationString) = a5 + 16 * (unsigned __int16)v15;
        AdtpBuildObjectTypeStrings(
          *(_QWORD *)(v12 + 80),
          *(_QWORD *)(v43 + v12 + 48),
          *(_QWORD *)(v18 + v12 + 48),
          *(_DWORD *)(v18 + v12 + 28) / 0x18u);
        v45 = *v44 + 2;
        v15 = v122;
        v46 = 2LL * v8;
        *(_QWORD *)(v14 + 8 * v46) = *((_QWORD *)v44 + 1);
        *(_QWORD *)(v14 + 8 * v46 + 8) = v45;
        goto LABEL_53;
      }
      if ( v19 )
      {
        switch ( v19 )
        {
          case 1:
            if ( !(unsigned __int8)AdtpIsCorrectlyFormedUnicodeString(*(_QWORD *)(v18 + v12 + 48)) )
              goto LABEL_168;
            v23 = AdtpEtwBuildString((unsigned int)v14 + 16 * v8, v40, v10, (unsigned int)&v124, v8 + a8);
            goto LABEL_26;
          case 2:
            v34 = *(_QWORD *)(v18 + v12 + 48);
            if ( !(unsigned __int8)AdtpIsCorrectlyFormedUnicodeString(v34) )
              goto LABEL_168;
            LOWORD(v130) = 0;
            LOWORD(Size) = 0;
            if ( (unsigned __int8)AdtpLookupDriveLetter(v35) )
            {
              v36 = *(_WORD **)(v34 + 8);
              v37 = *(_WORD *)v34 - Size;
              v38 = (char *)v36 + (unsigned __int16)Size;
              *v36 = v130;
              v36[1] = 58;
              memmove_0(v36 + 2, v38, v37);
              *(_WORD *)v34 = v37 + 4;
              v10 = v132;
            }
            v39 = AdtpEtwBuildString((unsigned int)v14 + 16 * v8, v34, v10, (unsigned int)&v124, v8 + a8);
LABEL_43:
            LODWORD(v9) = v120;
            v16 = v39;
            if ( v39 < 0 )
              goto LABEL_159;
            goto LABEL_27;
          case 3:
            v23 = AdtpBuildUlongString(*(_DWORD *)(v18 + v12 + 32), (__int64)&v124, v8 + a8);
            goto LABEL_26;
        }
        if ( v19 != 4 )
        {
          if ( v19 != 5 )
          {
            switch ( v19 )
            {
              case 6:
                v25 = RtlLengthSid(&AdtpNullSid);
                v26 = 2LL * v8;
                v27 = v8 + 1;
                *(_QWORD *)(v14 + 8 * v26) = &AdtpNullSid;
                *(_DWORD *)(v14 + 8 * v26 + 8) = v25;
                *(_DWORD *)(v14 + 8 * v26 + 12) = 0;
                v28 = 2;
                do
                {
                  v29 = v27++;
                  v29 *= 2;
                  *(_QWORD *)(v14 + 8 * v29) = byte_1801736C8;
                  *(_QWORD *)(v14 + 8 * v29 + 8) = 4;
                  --v28;
                }
                while ( v28 );
                LOWORD(v15) = v122;
                LODWORD(v9) = v120;
                v30 = 2LL * v27;
                v8 = v27 + 1;
                *(_QWORD *)(v14 + 8 * v30) = AdtpNullLuid;
                *(_QWORD *)(v14 + 8 * v30 + 8) = 8;
                goto LABEL_154;
              case 7:
                if ( *(_DWORD *)(v18 + v12 + 40) >= v126 )
                  goto LABEL_168;
                v24 = 32LL * *(unsigned int *)(v18 + v12 + 40);
                if ( *(_DWORD *)(v24 + v12 + 24) != 1 )
                  goto LABEL_168;
                v23 = AdtpBuildAccessesString(
                        *(_QWORD *)(v12 + 80),
                        *(_QWORD *)(v24 + v12 + 48),
                        *(_DWORD *)(v18 + v12 + 32),
                        0,
                        0,
                        v14 + 16LL * v8,
                        v10,
                        (__int64)&v124,
                        v8 + a8);
                break;
              case 8:
                v20 = *(unsigned int **)(v18 + v12 + 48);
                if ( !v20 )
                  goto LABEL_168;
                v21 = *v20;
                v22 = *v20 ? 12 * v21 + 8 : 8;
                if ( *(_DWORD *)(v18 + v12 + 28) < v22 || v21 > 0x42 )
                  goto LABEL_168;
                DestinationString = (PUNICODE_STRING)&v124;
                v23 = AdtpBuildPrivilegeAuditString(*(_QWORD *)(v18 + v12 + 48), 0, v14 + 16LL * v8, v10);
                break;
              default:
                goto LABEL_168;
            }
LABEL_26:
            LODWORD(v9) = v120;
            v16 = v23;
            if ( v23 < 0 )
              goto LABEL_159;
LABEL_27:
            ++v8;
            goto LABEL_28;
          }
LABEL_80:
          LOBYTE(Size) = 0;
          LOBYTE(v130) = 0;
          v125 = 0;
          P = 0;
          if ( v19 == 33 )
          {
            p_Size = 0;
            v58 = AdtpNullLuid;
            p_P = 0;
            v60 = 1;
          }
          else
          {
            v60 = 0;
            v58 = (__int64 *)(v18 + v12 + 32);
            p_Size = &Size;
            p_P = &P;
          }
          v119 = (PUNICODE_STRING)&v125;
          v81 = (unsigned __int16 *)(a5 + 16LL * (unsigned __int16)v15);
          v128 = v81;
          DestinationString = (PUNICODE_STRING)&v130;
          v16 = AdtpBuildLogonIdStrings(v58, p_P, p_Size, v81);
          if ( v16 < 0 )
            goto LABEL_158;
          if ( *(_DWORD *)(v18 + v12 + 24) == 5 || *(_DWORD *)(v18 + v12 + 24) == 35 )
          {
            v85 = (__int16 *)P;
            if ( P )
            {
              v86 = Size;
            }
            else
            {
              v85 = &AdtpNullSid;
              v86 = 0;
            }
            v87 = RtlLengthSid(v85);
            v88 = 2LL * v8;
            *(_DWORD *)(v14 + 8 * v88 + 8) = v87;
            v89 = a8;
            *(_QWORD *)(v14 + 8 * v88) = v85;
            *(_DWORD *)(v14 + 8 * v88 + 12) = 0;
            *(_BYTE *)(v8 + v89) = v86;
            v81 = v128;
LABEL_119:
            ++v8;
          }
          else
          {
            if ( v60 )
            {
              v82 = *(void **)(v18 + v12 + 48);
              v83 = RtlLengthSid(v82);
              v84 = 2LL * v8;
              *(_DWORD *)(v14 + 8 * v84 + 8) = v83;
              LOBYTE(v83) = Size;
              *(_QWORD *)(v14 + 8 * v84) = v82;
              *(_DWORD *)(v14 + 8 * v84 + 12) = 0;
              *(_BYTE *)(v8 + a8) = v83;
              goto LABEL_119;
            }
            if ( (_BYTE)Size && P )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
          }
          v90 = *((_QWORD *)v81 + 1);
          v91 = *v81;
          v92 = a8;
          v93 = a5;
          HIWORD(v15) = HIWORD(v122);
          v94 = 2LL * v8;
          *(_QWORD *)(v14 + 8 * v94) = v90;
          LOBYTE(v90) = v130;
          *(_DWORD *)(v14 + 8 * v94 + 8) = v91 + 2;
          *(_DWORD *)(v14 + 8 * v94 + 12) = 0;
          *(_BYTE *)(v8 + v92) = v90;
          v95 = v8 + 1;
          v96 = 2LL * v95;
          v97 = *(unsigned __int16 *)(v93 + 16LL * (unsigned __int16)(v122 + 1));
          *(_QWORD *)(v14 + 8 * v96) = *(_QWORD *)(v93 + 16LL * (unsigned __int16)(v122 + 1) + 8);
          LOBYTE(v90) = v125;
          *(_QWORD *)(v14 + 8 * v96 + 8) = (unsigned int)(v97 + 2);
          *(_BYTE *)(v95 + v92) = v90;
          v8 = v95 + 1;
          LOWORD(v15) = v122 + 2;
          v98 = 2LL * v8;
          *(_QWORD *)(v14 + 8 * v98) = v18 + v12 + 32;
          *(_QWORD *)(v14 + 8 * v98 + 8) = 8;
LABEL_54:
          ++v8;
          goto LABEL_151;
        }
        v31 = *(void **)(v18 + v12 + 48);
        v32 = RtlLengthSid(v31);
        if ( *(_DWORD *)(v18 + v12 + 28) < v32 || !RtlValidSid(v31) )
        {
          v16 = -1073741704;
LABEL_158:
          LODWORD(v9) = v120;
          goto LABEL_159;
        }
        LOWORD(v15) = v122;
        v33 = 2LL * v8;
        *(_DWORD *)(v14 + 8 * v33 + 8) = v32;
        ++v8;
        *(_QWORD *)(v14 + 8 * v33) = v31;
        *(_DWORD *)(v14 + 8 * v33 + 12) = 0;
LABEL_152:
        LODWORD(v9) = v120;
        goto LABEL_153;
      }
      v41 = (__int64 *)byte_1801736C8;
      v42 = 2LL * v8;
      *(_QWORD *)(v14 + 16LL * v8 + 8) = 4;
    }
    *(_QWORD *)(v14 + 8 * v42) = v41;
LABEL_49:
    ++v8;
LABEL_155:
    v13 = v121;
LABEL_156:
    v17 = v126 + 1;
  }
  if ( v19 <= 27 )
  {
    if ( v19 != 27 )
    {
      if ( v19 != 19 )
      {
        switch ( v19 )
        {
          case 20:
            v73 = 3;
            do
            {
              v74 = v8++;
              v74 *= 2;
              *(_QWORD *)(v14 + 8 * v74) = byte_1801736C8;
              *(_QWORD *)(v14 + 8 * v74 + 8) = 4;
              --v73;
            }
            while ( v73 );
            goto LABEL_155;
          case 21:
            v23 = AdtpBuildMessageString(
                    *(_DWORD *)(v18 + v12 + 32),
                    21,
                    (unsigned int)v14 + 16 * v8,
                    v10,
                    (__int64)&v124,
                    v8 + a8);
            goto LABEL_26;
          case 22:
            v23 = AdtpBuildDateTimeString(
                    (int)v18 + (int)v12 + 32,
                    22,
                    (unsigned int)v14 + 16 * v8,
                    v10,
                    (__int64)&v124,
                    v8 + a8);
            goto LABEL_26;
        }
        if ( v19 != 23 )
        {
          if ( v19 != 24 )
          {
            v56 = v19 - 25;
            if ( v19 != 25 )
              goto LABEL_79;
            v61 = (unsigned __int16 *)(a5 + 16LL * (unsigned __int16)v15);
            v62 = AdtpBuildLogonHoursString(
                    **(unsigned __int16 **)(v18 + v12 + 48),
                    *(_QWORD *)(*(_QWORD *)(v18 + v12 + 48) + 8LL),
                    v61,
                    v8 + a8);
            LODWORD(v9) = v120;
            v16 = v62;
            if ( v62 < 0 )
              goto LABEL_159;
            v63 = 2LL * v8;
            v64 = *v61 + 2;
            HIWORD(v15) = HIWORD(v122);
            ++v8;
            LOWORD(v15) = v122 + 1;
            *(_QWORD *)(v14 + 8 * v63) = *((_QWORD *)v61 + 1);
            v122 = v15;
            *(_QWORD *)(v14 + 8 * v63 + 8) = v64;
LABEL_153:
            v10 = v132;
LABEL_154:
            v11 = Heap;
            goto LABEL_155;
          }
          ++v126;
          v65 = AdtpBuildSecurityDescriptorChangeString(
                  *(_DWORD *)(v18 + v12 + 32),
                  v14 + 16LL * v8,
                  v8 + a8,
                  (int)v119,
                  v14 + 16LL * v8 + 16,
                  v8 + a8 + 1,
                  v10,
                  (__int64)&v124);
          LODWORD(v9) = v120;
          v16 = v65;
          if ( v65 < 0 )
            goto LABEL_159;
          v8 += 2;
LABEL_28:
          LOWORD(v15) = v122;
          goto LABEL_154;
        }
        v66 = v8 + a8;
        v67 = (unsigned __int16 *)(a5 + 16LL * (unsigned __int16)v15);
        LODWORD(DestinationString) = v66 + 1;
        v16 = AdtpBuildSockAddrString(*(_QWORD *)(v18 + v12 + 48), v67, v66, v67 + 8);
        if ( v16 < 0 )
          goto LABEL_158;
        v68 = 2LL * v8;
        v69 = *((_QWORD *)v67 + 1);
        v70 = a5;
        HIWORD(v15) = HIWORD(v122);
        ++v8;
        *(_DWORD *)(v14 + 8 * v68 + 8) = *v67 + 2;
        LOWORD(v15) = v122 + 1;
        *(_QWORD *)(v14 + 8 * v68) = v69;
        *(_DWORD *)(v14 + 8 * v68 + 12) = 0;
        v71 = *(unsigned __int16 *)(v70 + 16LL * (unsigned __int16)(v122 + 1)) + 2;
        v72 = 2LL * v8;
        *(_QWORD *)(v14 + 8 * v72) = *(_QWORD *)(v70 + 16LL * (unsigned __int16)(v122 + 1) + 8);
        *(_QWORD *)(v14 + 8 * v72 + 8) = v71;
LABEL_53:
        LOWORD(v15) = v15 + 1;
        goto LABEL_54;
      }
      v16 = AdtpBuildUserAccountControlString(
              *(_DWORD *)(v18 + v12 + 32),
              *(_DWORD *)(v18 + v12 + 40),
              (PUNICODE_STRING)(a5 + 16LL * (unsigned __int16)v122),
              (PUNICODE_STRING)(a5 + 16LL * ((unsigned int)(unsigned __int16)v15 + 1)),
              a8 + (unsigned int)v8 + 1,
              (PUNICODE_STRING)(a5 + 16LL * ((unsigned int)(unsigned __int16)v15 + 2)),
              a8 + (unsigned int)v8 + 2);
      if ( v16 < 0 )
        goto LABEL_158;
      v15 = v122;
      v75 = 3;
      v76 = a5;
      do
      {
        v77 = (unsigned __int16)v15;
        LOWORD(v15) = v15 + 1;
        v77 *= 2;
        v78 = 2LL * v8++;
        v79 = *(unsigned __int16 *)(v76 + 8 * v77) + 2;
        *(_QWORD *)(v14 + 8 * v78) = *(_QWORD *)(v76 + 8 * v77 + 8);
        *(_QWORD *)(v14 + 8 * v78 + 8) = v79;
        --v75;
      }
      while ( v75 );
      v12 = a1;
LABEL_151:
      v122 = v15;
      goto LABEL_152;
    }
LABEL_97:
    v80 = 2LL * v8;
    *(_QWORD *)(v14 + 8 * v80) = v18 + v12 + 32;
    *(_QWORD *)(v14 + 8 * v80 + 8) = 4;
    goto LABEL_49;
  }
  switch ( v19 )
  {
    case 28:
      v112 = (unsigned __int16 *)(a5 + 16LL * (unsigned __int16)v15);
      LODWORD(DestinationString) = 0;
      v16 = AdtpBuildSockAddrString(*(_QWORD *)(v18 + v12 + 48), v112, v8 + a8, 0);
      if ( v16 < 0 )
        goto LABEL_158;
      v113 = 2LL * v8;
      v114 = *v112 + 2;
      HIWORD(v15) = HIWORD(v122);
      ++v8;
      *(_QWORD *)(v14 + 8 * v113) = *((_QWORD *)v112 + 1);
      LOWORD(v15) = v122 + 1;
      *(_QWORD *)(v14 + 8 * v113 + 8) = v114;
      goto LABEL_151;
    case 29:
LABEL_146:
      v109 = *(_QWORD *)(v18 + v12 + 48);
      v110 = *(_DWORD *)(v109 + 132);
      if ( v110 >= v126 || (v111 = 32LL * v110, *(_DWORD *)(v111 + v12 + 24) != 1) )
      {
        v16 = -1073741811;
        goto LABEL_158;
      }
      LOBYTE(v11) = v19 == 30;
      v23 = AdtpBuildAccessReasonAuditString(
              *(_QWORD *)(v12 + 80),
              *(_QWORD *)(v111 + v12 + 48),
              v109,
              (_DWORD)v11,
              (_DWORD)DestinationString,
              v14 + 16LL * v8,
              v10,
              (__int64)&v124,
              v8 + a8);
      goto LABEL_26;
    case 30:
      if ( *(_QWORD *)(v18 + v12 + 32) || *(_QWORD *)(v18 + v12 + 40) )
        goto LABEL_168;
      goto LABEL_146;
    case 31:
      if ( *(_DWORD *)(v18 + v12 + 32) != 32 || *(_QWORD *)(v18 + v12 + 40) )
        goto LABEL_168;
      v23 = AdtpBuildSecurityDescriptorUnicodeString(
              0x20u,
              *(PSECURITY_DESCRIPTOR *)(v18 + v12 + 48),
              v10,
              (__int64)&v124,
              v8 + a8);
      goto LABEL_26;
  }
  if ( v19 != 32 )
  {
    if ( v19 != 33 )
    {
      v56 = v19 - 34;
      if ( v19 == 34 )
      {
        v23 = AdtpBuildMultiSzStringListString(*(_QWORD *)(v18 + v12 + 48), v14 + 16LL * v8, v8 + a8);
        goto LABEL_26;
      }
LABEL_79:
      if ( v56 != 1 )
        goto LABEL_168;
    }
    goto LABEL_80;
  }
  v99 = *(_DWORD *)(v18 + v12 + 28);
  v100 = *(unsigned int **)(v18 + v12 + 48);
  LODWORD(P) = v99;
  if ( v11 )
  {
    v101 = 0;
    if ( (_DWORD)v9 )
    {
      do
      {
        v102 = (void *)v11[v101];
        if ( !v102 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v102);
        v11 = Heap;
        Heap[v101] = 0;
        v101 = (unsigned int)(v101 + 1);
      }
      while ( (unsigned int)v101 < v120 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    Heap = 0;
  }
  v9 = *(unsigned int *)(v18 + v12 + 32);
  v120 = *(_DWORD *)(v18 + v12 + 32);
  if ( v100 && (_DWORD)v9 && v99 >= 8 && *(_QWORD *)(v18 + v12 + 32) <= 0xFFFFFFFF && !*(_QWORD *)(v18 + v12 + 40) )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8 * v9);
    if ( Heap )
    {
      v104 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        LODWORD(v9) = v120;
        LODWORD(v130) = v104;
        if ( (unsigned int)i >= v120 )
        {
          v10 = v132;
          v39 = AdtpBuildClaimsAuditString(
                  v120,
                  (_DWORD)Heap,
                  v120,
                  v103,
                  v14 + 16LL * v8,
                  v132,
                  (__int64)&v124,
                  v8 + a8);
          goto LABEL_43;
        }
        LODWORD(Size) = 0;
        if ( v99 - v104 < 8 )
          goto LABEL_168;
        v106 = *v100;
        v107 = v106 + 8;
        if ( v99 - v104 < (int)v106 + 8 )
          goto LABEL_168;
        if ( (unsigned int)RtlpConvertRelativeToAbsoluteSecurityAttribute(v100 + 2, v106, 0, &Size) != -1073741789 )
          break;
        v108 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
        Heap[i] = v108;
        if ( !v108 )
          goto LABEL_166;
        v16 = RtlpConvertRelativeToAbsoluteSecurityAttribute(v100 + 2, *v100, v108, &Size);
        if ( v16 < 0 )
          goto LABEL_158;
        v99 = (unsigned int)P;
        v104 = v107 + v130;
        v100 = (unsigned int *)((char *)v100 + v107);
      }
      v16 = -1073741595;
    }
    else
    {
LABEL_166:
      v16 = -1073741801;
    }
    goto LABEL_158;
  }
LABEL_168:
  v16 = -1073741811;
LABEL_159:
  *a7 = v8;
  if ( Heap )
  {
    v115 = 0;
    if ( (_DWORD)v9 )
    {
      do
      {
        v116 = (void *)Heap[v115];
        if ( !v116 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v116);
        Heap[v115] = 0;
        v115 = (unsigned int)(v115 + 1);
      }
      while ( (unsigned int)v115 < v120 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18013bbe8  mov     rax, rsp
0x18013bbeb  mov     [rax+20h], r9
0x18013bbef  mov     [rax+18h], r8d
0x18013bbf3  mov     [rax+10h], rdx
0x18013bbf7  mov     [rax+8], rcx
0x18013bbfb  push    rbp
0x18013bbfc  push    rbx
0x18013bbfd  push    rsi
0x18013bbfe  push    rdi
0x18013bbff  push    r12
0x18013bc01  push    r13
0x18013bc03  push    r14
0x18013bc05  push    r15
0x18013bc07  lea     rbp, [rax-47h]
0x18013bc0b  sub     rsp, 0A8h
0x18013bc12  xor     r14d, r14d
0x18013bc15  xor     r8d, r8d
0x18013bc18  mov     rbx, r9
0x18013bc1b  mov     dword ptr [rbp+3Fh+var_68], r14d
0x18013bc1f  xor     r9d, r9d
0x18013bc22  mov     [rbp+3Fh+var_80], r8d
0x18013bc26  mov     [rbp+3Fh+var_70], r9
0x18013bc2a  mov     r13, rcx
0x18013bc2d  lea     edi, [r14+1]
0x18013bc31  test    rcx, rcx
0x18013bc34  jz      loc_18013CBA5
0x18013bc3a  mov     ecx, [rcx+8]
0x18013bc3d  lea     r10d, [r14+4]
0x18013bc41  mov     r15, [rbp+3Fh+arg_28]
0x18013bc45  xor     r11d, r11d
0x18013bc48  xor     esi, esi
0x18013bc4a  mov     [rbp+3Fh+var_78], r11d
0x18013bc4e  xor     eax, eax
0x18013bc50  mov     [rbp+3Fh+var_7C], ecx
0x18013bc53  mov     [rbp+3Fh+var_60], eax
0x18013bc56  cmp     eax, ecx
0x18013bc58  jnb     loc_18013CB07
0x18013bc5e  cmp     r14w, 2Ah ; '*'
0x18013bc63  jnb     loc_18013CBA5
0x18013bc69  cmp     r11w, 0Eh
0x18013bc6e  jnb     loc_18013CBA5
0x18013bc74  mov     r12d, eax
0x18013bc77  shl     r12, 5
0x18013bc7b  mov     edx, [r12+r13+18h]
0x18013bc80  cmp     edx, 12h
0x18013bc83  jg      loc_18013C1CE
0x18013bc89  jz      loc_18013C1AD
0x18013bc8f  cmp     edx, 9
0x18013bc92  jg      loc_18013C0BF
0x18013bc98  jz      loc_18013C01B
0x18013bc9e  mov     ecx, edx
0x18013bca0  test    edx, edx
0x18013bca2  jz      loc_18013BFF7
0x18013bca8  sub     ecx, 1
0x18013bcab  jz      loc_18013BFB7
0x18013bcb1  sub     ecx, 1
0x18013bcb4  jz      loc_18013BF0D
0x18013bcba  sub     ecx, 1
0x18013bcbd  jz      loc_18013BED8
0x18013bcc3  sub     ecx, 1
0x18013bcc6  jz      loc_18013BE75
0x18013bccc  sub     ecx, 1
0x18013bccf  jz      loc_18013C223
0x18013bcd5  sub     ecx, 1
0x18013bcd8  jz      loc_18013BDE9
0x18013bcde  sub     ecx, 1
0x18013bce1  jz      loc_18013BD75
0x18013bce7  cmp     ecx, 1
0x18013bcea  jnz     loc_18013CBA5
0x18013bcf0  mov     r10, [r12+r13+30h]
0x18013bcf5  test    r10, r10
0x18013bcf8  jz      loc_18013CBA5
0x18013bcfe  mov     ecx, [r10]
0x18013bd01  test    ecx, ecx
0x18013bd03  jz      short loc_18013BD11
0x18013bd05  lea     eax, [rcx+rcx*2]
0x18013bd08  lea     eax, ds:8[rax*4]
0x18013bd0f  jmp     short loc_18013BD16
0x18013bd11  mov     eax, 8
0x18013bd16  cmp     [r12+r13+1Ch], eax
0x18013bd1b  jb      loc_18013CBA5
0x18013bd21  cmp     ecx, 42h ; 'B'
0x18013bd24  ja      loc_18013CBA5
0x18013bd2a  mov     rax, [rbp+3Fh+arg_38]
0x18013bd31  mov     r9, rbx
0x18013bd34  movzx   r8d, r14w
0x18013bd38  xor     edx, edx
0x18013bd3a  add     rax, r8
0x18013bd3d  mov     rcx, r10
0x18013bd40  mov     [rsp+0E0h+var_B8], rax
0x18013bd45  lea     rax, [rbp+3Fh+var_68]
0x18013bd49  shl     r8, 4
0x18013bd4d  add     r8, r15
0x18013bd50  mov     [rsp+0E0h+DestinationString], rax
0x18013bd55  call    AdtpBuildPrivilegeAuditString
0x18013bd5a  mov     r8d, [rbp+3Fh+var_80]
0x18013bd5e  mov     esi, eax
0x18013bd60  test    eax, eax
0x18013bd62  js      loc_18013CB07
0x18013bd68  add     r14w, di
0x18013bd6c  mov     r11d, [rbp+3Fh+var_78]
0x18013bd70  jmp     loc_18013CAE7
0x18013bd75  mov     r10d, [rbp+3Fh+var_60]
0x18013bd79  cmp     [r12+r13+28h], r10d
0x18013bd7e  jnb     loc_18013CBA5
0x18013bd84  mov     edx, [r12+r13+28h]
0x18013bd89  shl     rdx, 5
0x18013bd8d  cmp     [rdx+r13+18h], edi
0x18013bd92  jnz     loc_18013CBA5
0x18013bd98  mov     rax, [rbp+3Fh+arg_38]
0x18013bd9f  xor     r9d, r9d; int
0x18013bda2  mov     r8d, [r12+r13+20h]; int
0x18013bda7  mov     rdx, [rdx+r13+30h]; int
0x18013bdac  movzx   ecx, r14w
0x18013bdb0  add     rax, rcx
0x18013bdb3  shl     rcx, 4
0x18013bdb7  mov     [rsp+0E0h+var_A0], rax; __int64
0x18013bdbc  add     rcx, r15
0x18013bdbf  lea     rax, [rbp+3Fh+var_68]
0x18013bdc3  mov     [rsp+0E0h+var_A8], rax; __int64
0x18013bdc8  mov     [rsp+0E0h+var_B0], rbx; __int64
0x18013bdcd  mov     [rsp+0E0h+var_B8], rcx; __int64
0x18013bdd2  mov     rcx, [r13+50h]; int
0x18013bdd6  mov     [rsp+0E0h+DestinationString], 0; DestinationString
0x18013bddf  call    AdtpBuildAccessesString
0x18013bde4  jmp     loc_18013BD5A
0x18013bde9  lea     r12, AdtpNullSid
0x18013bdf0  mov     rcx, r12; Sid
0x18013bdf3  call    cs:__imp_RtlLengthSid
0x18013bdfa  nop     dword ptr [rax+rax+00h]
0x18013bdff  movzx   ecx, r14w
0x18013be03  lea     r8, byte_1801736C8
0x18013be0a  add     rcx, rcx
0x18013be0d  mov     edx, 0FFFFFFFFh
0x18013be12  add     r14w, di
0x18013be16  mov     [r15+rcx*8], r12
0x18013be1a  mov     [r15+rcx*8+8], eax
0x18013be1f  mov     dword ptr [r15+rcx*8+0Ch], 0
0x18013be28  mov     ecx, 2
0x18013be2d  lea     r10d, [rcx+2]
0x18013be31  movzx   eax, r14w
0x18013be35  add     r14w, di
0x18013be39  add     rax, rax
0x18013be3c  mov     [r15+rax*8], r8
0x18013be40  mov     [r15+rax*8+8], r10
0x18013be45  add     ecx, edx
0x18013be47  jnz     short loc_18013BE31
0x18013be49  mov     r11d, [rbp+3Fh+var_78]
0x18013be4d  lea     rcx, AdtpNullLuid
0x18013be54  mov     r8d, [rbp+3Fh+var_80]
0x18013be58  movzx   eax, r14w
0x18013be5c  add     rax, rax
0x18013be5f  add     r14w, di
0x18013be63  mov     [r15+rax*8], rcx
0x18013be67  mov     qword ptr [r15+rax*8+8], 8
0x18013be70  jmp     loc_18013CAED
0x18013be75  mov     rbx, [r12+r13+30h]
0x18013be7a  mov     rcx, rbx; Sid
0x18013be7d  call    cs:__imp_RtlLengthSid
0x18013be84  nop     dword ptr [rax+rax+00h]
0x18013be89  mov     edi, eax
0x18013be8b  cmp     [r12+r13+1Ch], eax
0x18013be90  jb      loc_18013CAFE
0x18013be96  mov     rcx, rbx; Sid
0x18013be99  call    cs:__imp_RtlValidSid
0x18013bea0  nop     dword ptr [rax+rax+00h]
0x18013bea5  test    al, al
0x18013bea7  jz      loc_18013CAFE
0x18013bead  mov     r11d, [rbp+3Fh+var_78]
0x18013beb1  movzx   ecx, r14w
0x18013beb5  add     rcx, rcx
0x18013beb8  mov     [r15+rcx*8+8], edi
0x18013bebd  mov     edi, 1
0x18013bec2  add     r14w, di
0x18013bec6  mov     [r15+rcx*8], rbx
0x18013beca  mov     dword ptr [r15+rcx*8+0Ch], 0
0x18013bed3  jmp     loc_18013CADF
0x18013bed8  mov     rax, [rbp+3Fh+arg_38]
0x18013bedf  mov     r9, rbx
0x18013bee2  mov     ecx, [r12+r13+20h]; Value
0x18013bee7  movzx   r8d, r14w
0x18013beeb  add     rax, r8
0x18013beee  shl     r8, 4
0x18013bef2  mov     [rsp+0E0h+var_B8], rax; __int64
0x18013bef7  add     r8, r15
0x18013befa  lea     rax, [rbp+3Fh+var_68]
0x18013befe  mov     [rsp+0E0h+DestinationString], rax; __int64
0x18013bf03  call    AdtpBuildUlongString
0x18013bf08  jmp     loc_18013BD5A
0x18013bf0d  mov     rdi, [r12+r13+30h]
0x18013bf12  mov     rcx, rdi
0x18013bf15  call    AdtpIsCorrectlyFormedUnicodeString
0x18013bf1a  test    al, al
0x18013bf1c  jz      loc_18013CBA5
0x18013bf22  xor     eax, eax
0x18013bf24  lea     r8, [rbp+3Fh+arg_8]
0x18013bf28  lea     rdx, [rbp+3Fh+Size]
0x18013bf2c  mov     word ptr [rbp+3Fh+arg_8], ax
0x18013bf30  mov     word ptr [rbp+3Fh+Size], ax
0x18013bf34  call    AdtpLookupDriveLetter
0x18013bf39  test    al, al
0x18013bf3b  jz      short loc_18013BF76
0x18013bf3d  mov     rcx, [rdi+8]
0x18013bf41  movzx   eax, word ptr [rdi]
0x18013bf44  sub     ax, word ptr [rbp+3Fh+Size]
0x18013bf48  movzx   edx, word ptr [rbp+3Fh+Size]
0x18013bf4c  movzx   ebx, ax
0x18013bf4f  add     rdx, rcx; Src
0x18013bf52  movzx   eax, word ptr [rbp+3Fh+arg_8]
0x18013bf56  mov     r8d, ebx; Size
0x18013bf59  mov     [rcx], ax
0x18013bf5c  mov     word ptr [rcx+2], 3Ah ; ':'
0x18013bf62  add     rcx, 4; void *
0x18013bf66  call    memmove_0
0x18013bf6b  add     bx, 4
0x18013bf6f  mov     [rdi], bx
0x18013bf72  mov     rbx, [rbp+3Fh+arg_18]
0x18013bf76  mov     rax, [rbp+3Fh+arg_38]
0x18013bf7d  lea     r9, [rbp+3Fh+var_68]
0x18013bf81  movzx   ecx, r14w
0x18013bf85  mov     r8, rbx
0x18013bf88  add     rax, rcx
0x18013bf8b  mov     rdx, rdi
0x18013bf8e  shl     rcx, 4
0x18013bf92  add     rcx, r15
0x18013bf95  mov     [rsp+0E0h+DestinationString], rax
0x18013bf9a  call    AdtpEtwBuildString
0x18013bf9f  mov     r8d, [rbp+3Fh+var_80]
0x18013bfa3  mov     esi, eax
0x18013bfa5  test    eax, eax
0x18013bfa7  js      loc_18013CB07
0x18013bfad  mov     edi, 1
0x18013bfb2  jmp     loc_18013BD68
0x18013bfb7  mov     rdx, [r12+r13+30h]
0x18013bfbc  mov     rcx, rdx
0x18013bfbf  call    AdtpIsCorrectlyFormedUnicodeString
0x18013bfc4  test    al, al
0x18013bfc6  jz      loc_18013CBA5
0x18013bfcc  mov     rax, [rbp+3Fh+arg_38]
0x18013bfd3  lea     r9, [rbp+3Fh+var_68]
0x18013bfd7  movzx   ecx, r14w
0x18013bfdb  mov     r8, rbx
0x18013bfde  add     rax, rcx
0x18013bfe1  shl     rcx, 4
0x18013bfe5  add     rcx, r15
0x18013bfe8  mov     [rsp+0E0h+DestinationString], rax
0x18013bfed  call    AdtpEtwBuildString
0x18013bff2  jmp     loc_18013BD5A
0x18013bff7  movzx   eax, r14w
0x18013bffb  lea     rcx, byte_1801736C8
0x18013c002  add     rax, rax
0x18013c005  mov     qword ptr [r15+rax*8+8], 4
0x18013c00e  mov     [r15+rax*8], rcx
0x18013c012  add     r14w, di
0x18013c016  jmp     loc_18013CAF1
0x18013c01b  cmp     [r12+r13+28h], eax
0x18013c020  jnb     loc_18013CBA5
0x18013c026  mov     r10d, [r12+r13+28h]
0x18013c02b  shl     r10, 5
0x18013c02f  cmp     [r10+r13+18h], edi
0x18013c034  jnz     loc_18013CBA5
0x18013c03a  mov     ecx, [r12+r13+1Ch]
0x18013c03f  mov     rax, 0AAAAAAAAAAAAAAABh
0x18013c049  mov     r8, [rbp+3Fh+arg_38]
0x18013c050  mul     rcx
0x18013c053  mov     rcx, [r13+50h]
0x18013c057  shr     rdx, 4
0x18013c05b  movzx   ebx, r11w
0x18013c05f  mov     r9d, edx
0x18013c062  mov     rdx, [r10+r13+30h]
0x18013c067  movzx   edi, r14w
0x18013c06b  add     r8, rdi
0x18013c06e  shl     rbx, 4
0x18013c072  add     rbx, [rbp+3Fh+arg_20]
0x18013c076  mov     [rsp+0E0h+var_B8], r8
0x18013c07b  mov     r8, [r12+r13+30h]
0x18013c080  mov     [rsp+0E0h+DestinationString], rbx
0x18013c085  call    AdtpBuildObjectTypeStrings
0x18013c08a  movzx   ecx, word ptr [rbx]
0x18013c08d  mov     rax, [rbx+8]
0x18013c091  add     ecx, 2
0x18013c094  mov     r11d, [rbp+3Fh+var_78]
0x18013c098  add     rdi, rdi
0x18013c09b  mov     [r15+rdi*8], rax
0x18013c09f  mov     [r15+rdi*8+8], ecx
0x18013c0a4  mov     dword ptr [r15+rdi*8+0Ch], 0
0x18013c0ad  mov     edi, 1
0x18013c0b2  add     r11w, di
0x18013c0b6  add     r14w, di
0x18013c0ba  jmp     loc_18013CADB
0x18013c0bf  sub     edx, 0Ah
0x18013c0c2  jz      loc_18013C558
0x18013c0c8  sub     edx, 1
0x18013c0cb  jz      loc_18013C165
0x18013c0d1  sub     edx, 1
0x18013c0d4  jz      loc_18013C165
0x18013c0da  sub     edx, 1
0x18013c0dd  jz      loc_18013C185
0x18013c0e3  sub     edx, 1
0x18013c0e6  jz      short loc_18013C165
  ... truncated ...
```
