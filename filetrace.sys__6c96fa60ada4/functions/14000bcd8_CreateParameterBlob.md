# CreateParameterBlob

- ea: `0x14000bcd8`
- end: `0x14000c8b0`
- name: `CreateParameterBlob`
- size: `3032`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400010b0`
- `0x140002110`

## callees

- `0x140003510`
- `0x140003550`
- `0x140003600`
- `0x14000bcd8`

## import_xrefs

- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000c4ea`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000c4ea`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000beec`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000bfcb`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000beec`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000bfcb`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c494`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c527`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c527`
- `ntoskrnl!ExAllocatePool2` at `0x14000bd98`
- `ntoskrnl!ExAllocatePool2` at `0x14000be05`
- `ntoskrnl!ExAllocatePool2` at `0x14000bf34`
- `ntoskrnl!ExAllocatePool2` at `0x14000c01f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c06e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c11e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c15c`
- `ntoskrnl!ExAllocatePool2` at `0x14000c2e8`
- `ntoskrnl!ExAllocatePool2` at `0x14000c33d`
- `ntoskrnl!ExAllocatePool2` at `0x14000c39b`
- `ntoskrnl!ExAllocatePool2` at `0x14000c436`
- `ntoskrnl!ExAllocatePool2` at `0x14000c4b3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c59f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5d5`
- `ntoskrnl!ExAllocatePool2` at `0x14000c611`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6ad`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6eb`
- `ntoskrnl!ExAllocatePool2` at `0x14000c723`
- `ntoskrnl!ExAllocatePool2` at `0x14000c7d1`
- `ntoskrnl!ExAllocatePool2` at `0x14000c822`
- `ntoskrnl!ExAllocatePool2` at `0x14000bd98`
- `ntoskrnl!ExAllocatePool2` at `0x14000be05`
- `ntoskrnl!ExAllocatePool2` at `0x14000bf34`
- `ntoskrnl!ExAllocatePool2` at `0x14000c01f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c06e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c11e`
- `ntoskrnl!ExAllocatePool2` at `0x14000c15c`
- `ntoskrnl!ExAllocatePool2` at `0x14000c2e8`
- `ntoskrnl!ExAllocatePool2` at `0x14000c33d`
- `ntoskrnl!ExAllocatePool2` at `0x14000c39b`
- `ntoskrnl!ExAllocatePool2` at `0x14000c436`
- `ntoskrnl!ExAllocatePool2` at `0x14000c4b3`
- `ntoskrnl!ExAllocatePool2` at `0x14000c59f`
- `ntoskrnl!ExAllocatePool2` at `0x14000c5d5`
- `ntoskrnl!ExAllocatePool2` at `0x14000c611`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6ad`
- `ntoskrnl!ExAllocatePool2` at `0x14000c6eb`
- `ntoskrnl!ExAllocatePool2` at `0x14000c723`
- `ntoskrnl!ExAllocatePool2` at `0x14000c7d1`
- `ntoskrnl!ExAllocatePool2` at `0x14000c822`

## pseudocode

```c
__int64 __fastcall CreateParameterBlob(__int64 a1, _DWORD *a2, __int64 *a3)
{
  bool v3; // r12
  __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  __int64 v14; // rax
  __int64 v15; // rcx
  _OWORD *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // r15d
  char v20; // r13
  __int64 v21; // rax
  NTSTATUS v22; // eax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  _OWORD *Pool2; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  unsigned int v33; // r8d
  unsigned int v34; // r8d
  unsigned int v35; // r8d
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  unsigned int v38; // r8d
  _OWORD *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 i; // rcx
  char v46; // al
  __int64 v47; // rax
  __int64 v48; // rcx
  _OWORD *v49; // rax
  __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  _OWORD *v52; // rax
  __int64 v53; // rcx
  _OWORD *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rcx
  _OWORD *v57; // rax
  NTSTATUS v58; // eax
  __int64 v59; // rcx
  unsigned int v60; // r8d
  unsigned int v61; // r8d
  unsigned int v62; // r8d
  unsigned int v63; // r8d
  unsigned int v64; // r8d
  unsigned int v65; // r8d
  _QWORD *v66; // rax
  _OWORD *v67; // rax
  _DWORD *v68; // rax
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  _BYTE *v76; // rax
  _OWORD *v77; // rax
  __int64 v78; // rcx
  unsigned int v79; // r8d
  unsigned int v80; // r8d
  unsigned int v81; // r8d
  unsigned int v82; // r8d
  _OWORD *v83; // rax
  _OWORD *v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rax
  ULONG BufferLength; // [rsp+30h] [rbp-40h] BYREF
  _DWORD *v88; // [rsp+38h] [rbp-38h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  int FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int16 Src; // [rsp+54h] [rbp-1Ch] BYREF
  int v92; // [rsp+56h] [rbp-1Ah]
  __int16 v93; // [rsp+5Ah] [rbp-16h]

  v3 = 0;
  v88 = a2;
  v6 = *(_QWORD *)(a1 + 16);
  LODWORD(v7) = 0;
  v8 = *(unsigned __int8 *)(v6 + 4);
  if ( v8 <= 0x15 )
  {
    if ( v8 != 21 )
    {
      if ( v8 <= 0xA )
      {
        if ( v8 != 10 )
        {
          if ( !*(_BYTE *)(v6 + 4) )
          {
            LODWORD(v7) = 72;
            Pool2 = (_OWORD *)ExAllocatePool2(66, 72, 1920224326);
            *a3 = (__int64)Pool2;
            if ( Pool2 )
            {
              v30 = *(_QWORD *)(a1 + 16);
              *Pool2 = *(_OWORD *)(v30 + 24);
              Pool2[1] = *(_OWORD *)(v30 + 40);
              Pool2[2] = *(_OWORD *)(v30 + 56);
              v31 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
              v32 = (_QWORD *)*a3;
              *((_OWORD *)v32 + 3) = *(_OWORD *)v31;
              v32[8] = *(_QWORD *)(v31 + 16);
              *(_QWORD *)*a3 = 48;
              goto LABEL_128;
            }
            return 3221225626LL;
          }
          v9 = v8 - 3;
          if ( !v9 || (v10 = v9 - 1) == 0 )
          {
            v27 = ExAllocatePool2(66, 40, 1920224326);
            *a3 = v27;
            if ( v27 )
            {
              v28 = *(_QWORD *)(a1 + 16);
              LODWORD(v7) = 40;
              *(_OWORD *)v27 = *(_OWORD *)(v28 + 24);
              *(_OWORD *)(v27 + 16) = *(_OWORD *)(v28 + 40);
              *(_QWORD *)(v27 + 32) = *(_QWORD *)(v28 + 56);
              goto LABEL_128;
            }
            return 3221225626LL;
          }
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( !v12 )
            {
              FileInformation = 4;
              Src = 0;
              v92 = 0;
              v19 = 0;
              v93 = 0;
              v20 = 0;
              LODWORD(v7) = *(_DWORD *)(v6 + 24) + 40;
              if ( (unsigned int)(*(_DWORD *)(v6 + 32) - 10) <= 1
                && *(_QWORD *)(*(_QWORD *)(v6 + 56) + 8LL)
                && (GlobalLateBoundFunctions && !(unsigned __int8)GlobalLateBoundFunctions()
                 || (**(_DWORD **)(a1 + 16) & 2) == 0) )
              {
                v21 = *(_QWORD *)(a1 + 16);
                IoStatusBlock = 0;
                v22 = ZwQueryInformationFile(
                        *(HANDLE *)(*(_QWORD *)(v21 + 56) + 8LL),
                        &IoStatusBlock,
                        &FileInformation,
                        0xCu,
                        FileNameInformation);
                if ( (int)(v22 + 0x80000000) < 0 || v22 == -2147483643 )
                {
                  v19 = FileInformation;
                  LODWORD(v7) = FileInformation + v7 + 4;
                  v20 = 1;
                  v3 = v22 == -2147483643;
                }
              }
              v23 = ExAllocatePool2(64, (unsigned int)v7, 1920224326);
              *a3 = v23;
              if ( v23 )
              {
                v24 = *(_QWORD *)(a1 + 16);
                *(_OWORD *)v23 = *(_OWORD *)(v24 + 24);
                *(_OWORD *)(v23 + 16) = *(_OWORD *)(v24 + 40);
                *(_QWORD *)(v23 + 32) = *(_QWORD *)(v24 + 56);
                memmove(
                  (void *)(*a3 + 40),
                  *(const void **)(*(_QWORD *)(a1 + 16) + 56LL),
                  *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL));
                *(_QWORD *)(*a3 + 32) = 40;
                if ( v20 )
                {
                  v25 = *a3;
                  v26 = *(_QWORD *)(a1 + 16);
                  if ( v3 )
                  {
                    IoStatusBlock = 0;
                    if ( ZwQueryInformationFile(
                           *(HANDLE *)(*(_QWORD *)(v26 + 56) + 8LL),
                           &IoStatusBlock,
                           (PVOID)(v25 + 40 + *(unsigned int *)(v26 + 24)),
                           v19 + 4,
                           FileNameInformation) < 0 )
                      LODWORD(v7) = v7 - v19;
                  }
                  else
                  {
                    *(_DWORD *)(*(unsigned int *)(v26 + 24) + v25 + 40) = v19;
                    memmove((void *)(*a3 + 44 + *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL)), &Src, v19);
                  }
                }
                goto LABEL_128;
              }
              return 3221225626LL;
            }
            v13 = v12 - 1;
            if ( !v13 )
            {
              LODWORD(v7) = *(_DWORD *)(v6 + 40) + 48;
              v17 = (_OWORD *)ExAllocatePool2(66, (unsigned int)v7, 1920224326);
              *a3 = (__int64)v17;
              if ( v17 )
              {
                v18 = *(_QWORD *)(a1 + 16);
                *v17 = *(_OWORD *)(v18 + 24);
                v17[1] = *(_OWORD *)(v18 + 40);
                v17[2] = *(_OWORD *)(v18 + 56);
                memmove(
                  (void *)(*a3 + 48),
                  *(const void **)(*(_QWORD *)(a1 + 16) + 32LL),
                  *(unsigned int *)(*(_QWORD *)(a1 + 16) + 40LL));
                *(_QWORD *)(*a3 + 8) = 48;
                goto LABEL_128;
              }
              return 3221225626LL;
            }
            if ( v13 == 1 )
            {
              LODWORD(v7) = *(_DWORD *)(v6 + 24) + 24;
              if ( (unsigned int)v7 < 0x18 )
                return 3221225621LL;
              v14 = ExAllocatePool2(66, (unsigned int)v7, 1920224326);
              *a3 = v14;
              if ( v14 )
                goto LABEL_14;
              return 3221225626LL;
            }
LABEL_81:
            *a3 = 0;
            goto LABEL_128;
          }
        }
LABEL_63:
        v47 = ExAllocatePool2(66, 24, 1920224326);
        *a3 = v47;
        if ( v47 )
        {
          v48 = *(_QWORD *)(a1 + 16);
          LODWORD(v7) = 24;
          *(_OWORD *)v47 = *(_OWORD *)(v48 + 24);
          *(_QWORD *)(v47 + 16) = *(_QWORD *)(v48 + 40);
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v33 = v8 - 11;
      if ( !v33 )
      {
        v7 = (unsigned int)(*(_DWORD *)(v6 + 24) + 24);
        v55 = ExAllocatePool2(66, v7, 1920224326);
        *a3 = v55;
        if ( v55 )
        {
          v56 = *(_QWORD *)(a1 + 16);
          *(_OWORD *)v55 = *(_OWORD *)(v56 + 24);
          *(_QWORD *)(v55 + 16) = *(_QWORD *)(v56 + 40);
          memmove(
            (void *)(*a3 + 24),
            *(const void **)(*(_QWORD *)(a1 + 16) + 40LL),
            *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL));
          *(_QWORD *)(*a3 + 16) = 24;
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        if ( *(_BYTE *)(v6 + 5) == 1 )
        {
          v51 = *(unsigned __int16 **)(v6 + 32);
          LODWORD(v7) = 48;
          if ( v51 )
            LODWORD(v7) = *v51 + 64;
          v52 = (_OWORD *)ExAllocatePool2(66, (unsigned int)v7, 1920224326);
          *a3 = (__int64)v52;
          if ( v52 )
          {
            v53 = *(_QWORD *)(a1 + 16);
            *v52 = *(_OWORD *)(v53 + 24);
            v52[1] = *(_OWORD *)(v53 + 40);
            v52[2] = *(_OWORD *)(v53 + 56);
            v54 = *(_OWORD **)(*(_QWORD *)(a1 + 16) + 32LL);
            if ( v54 )
            {
              *(_OWORD *)(*a3 + 48) = *v54;
              memmove(
                (void *)(*a3 + 64),
                *(const void **)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL) + 8LL),
                **(unsigned __int16 **)(*(_QWORD *)(a1 + 16) + 32LL));
              *(_QWORD *)(*a3 + 8) = 48;
              *(_QWORD *)(*a3 + 56) = 16;
            }
            goto LABEL_128;
          }
          return 3221225626LL;
        }
        if ( *(_BYTE *)(v6 + 5) == 2 )
        {
          v49 = (_OWORD *)ExAllocatePool2(66, 48, 1920224326);
          *a3 = (__int64)v49;
          if ( v49 )
          {
            v50 = *(_QWORD *)(a1 + 16);
            LODWORD(v7) = 48;
            *v49 = *(_OWORD *)(v50 + 24);
            v49[1] = *(_OWORD *)(v50 + 40);
            v49[2] = *(_OWORD *)(v50 + 56);
            goto LABEL_128;
          }
          return 3221225626LL;
        }
        goto LABEL_81;
      }
      v35 = v34 - 1;
      if ( v35 )
      {
        v36 = v35 - 1;
        if ( !v36 )
          goto LABEL_63;
        v37 = v36 - 1;
        if ( !v37 )
          goto LABEL_63;
        v38 = v37 - 2;
        if ( !v38 )
        {
          v41 = ExAllocatePool2(66, 48, 1920224326);
          *a3 = v41;
          if ( v41 )
          {
            v42 = *(_QWORD *)(a1 + 16);
            LODWORD(v7) = 48;
            switch ( *(_BYTE *)(v42 + 5) )
            {
              case 1:
                *(_OWORD *)v41 = *(_OWORD *)(v42 + 24);
                *(_OWORD *)(v41 + 16) = *(_OWORD *)(v42 + 40);
                *(_QWORD *)(v41 + 32) = *(_QWORD *)(v42 + 56);
                *(_QWORD *)(*a3 + 40) = **(_QWORD **)(*(_QWORD *)(a1 + 16) + 24LL);
                *(_QWORD *)*a3 = 40;
                goto LABEL_128;
              case 2:
                *(_QWORD *)v41 = 40;
                *(_DWORD *)(*a3 + 8) = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
                *(_QWORD *)(*a3 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 40LL);
                for ( i = 0; i != 2; ++i )
                  *(_BYTE *)(*a3 + i + 32) = 0;
                *(_QWORD *)(*a3 + 24) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
                *(_QWORD *)(*a3 + 40) = **(_QWORD **)(*(_QWORD *)(a1 + 16) + 24LL);
                goto LABEL_128;
              case 3:
                *(_QWORD *)v41 = 40;
                v44 = 0;
                *(_DWORD *)(*a3 + 8) = 0;
                *(_QWORD *)(*a3 + 16) = 0;
                do
                  *(_BYTE *)(*a3 + v44++ + 32) = 0;
                while ( v44 != 2 );
                break;
              case 4:
                *(_QWORD *)v41 = 40;
                *(_DWORD *)(*a3 + 8) = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
                v43 = 0;
                *(_QWORD *)(*a3 + 16) = 0;
                do
                  *(_BYTE *)(*a3 + v43++ + 32) = 0;
                while ( v43 != 2 );
                break;
              default:
                goto LABEL_128;
            }
            *(_QWORD *)(*a3 + 24) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
            *(_QWORD *)(*a3 + 40) = 0;
            goto LABEL_128;
          }
          return 3221225626LL;
        }
        if ( v38 != 3 )
          goto LABEL_81;
LABEL_43:
        LODWORD(v7) = 32;
        v39 = (_OWORD *)ExAllocatePool2(66, 32, 1920224326);
        *a3 = (__int64)v39;
        if ( v39 )
        {
          v40 = *(_QWORD *)(a1 + 16);
          *v39 = *(_OWORD *)(v40 + 24);
          v39[1] = *(_OWORD *)(v40 + 40);
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v46 = *(_BYTE *)(v6 + 5);
      if ( !v46 )
        goto LABEL_63;
      if ( v46 != 2 )
      {
        if ( v46 != 4 )
          goto LABEL_81;
        goto LABEL_63;
      }
LABEL_93:
      v67 = (_OWORD *)ExAllocatePool2(66, 16, 1920224326);
      *a3 = (__int64)v67;
      if ( v67 )
      {
        LODWORD(v7) = 16;
        *v67 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
        goto LABEL_128;
      }
      return 3221225626LL;
    }
    BufferLength = 0;
    BufferLength = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(v6 + 32));
    LODWORD(v7) = BufferLength + 16;
    v57 = (_OWORD *)ExAllocatePool2(66, BufferLength + 16, 1920224326);
    *a3 = (__int64)v57;
    if ( !v57 )
      return 3221225626LL;
    *v57 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
    v58 = RtlAbsoluteToSelfRelativeSD(
            *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(a1 + 16) + 32LL),
            (PSECURITY_DESCRIPTOR)(*a3 + 16),
            &BufferLength);
    if ( v58 >= 0 )
      goto LABEL_128;
    v59 = *a3;
    if ( v58 != -1073741593 )
    {
      ExFreePoolWithTag((PVOID)v59, 0x72744C46u);
      LODWORD(v7) = 0;
      goto LABEL_81;
    }
    memmove((void *)(v59 + 16), *(const void **)(*(_QWORD *)(a1 + 16) + 32LL), BufferLength);
LABEL_127:
    *(_QWORD *)(*a3 + 8) = 16;
    goto LABEL_128;
  }
  if ( (unsigned __int8)v8 > 0xF1u )
  {
    v79 = v8 - 242;
    if ( !v79 )
    {
      LODWORD(v7) = 72;
      v84 = (_OWORD *)ExAllocatePool2(66, 72, 1920224326);
      *a3 = (__int64)v84;
      if ( !v84 )
        return 3221225626LL;
      *v84 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      v85 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
      v86 = *a3;
      *(_OWORD *)(v86 + 16) = *(_OWORD *)v85;
      *(_OWORD *)(v86 + 32) = *(_OWORD *)(v85 + 16);
      *(_OWORD *)(v86 + 48) = *(_OWORD *)(v85 + 32);
      *(_QWORD *)(v86 + 64) = *(_QWORD *)(v85 + 48);
      goto LABEL_127;
    }
    v80 = v79 - 1;
    if ( !v80 )
      goto LABEL_43;
    v81 = v80 - 9;
    if ( v81 )
    {
      v82 = v81 - 1;
      if ( !v82 )
      {
        v83 = (_OWORD *)ExAllocatePool2(66, 24, 1920224326);
        *a3 = (__int64)v83;
        if ( v83 )
        {
          LODWORD(v7) = 24;
          *v83 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
          *(_QWORD *)(*a3 + 16) = **(_QWORD **)(*(_QWORD *)(a1 + 16) + 24LL);
          *(_QWORD *)*a3 = 16;
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      if ( v82 != 2 )
        goto LABEL_81;
      goto LABEL_63;
    }
LABEL_91:
    LODWORD(v7) = 8;
    v66 = (_QWORD *)ExAllocatePool2(66, 8, 1920224326);
    *a3 = (__int64)v66;
    if ( v66 )
    {
      *v66 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      goto LABEL_128;
    }
    return 3221225626LL;
  }
  if ( (_BYTE)v8 == 0xF1 )
    goto LABEL_43;
  v60 = v8 - 25;
  if ( !v60 )
  {
    v7 = (unsigned int)(*(_DWORD *)(v6 + 48) + 48);
    v77 = (_OWORD *)ExAllocatePool2(64, v7, 1920224326);
    *a3 = (__int64)v77;
    if ( v77 )
    {
      v78 = *(_QWORD *)(a1 + 16);
      *v77 = *(_OWORD *)(v78 + 24);
      v77[1] = *(_OWORD *)(v78 + 40);
      v77[2] = *(_OWORD *)(v78 + 56);
      memmove(
        (void *)(*a3 + 48),
        *(const void **)(*(_QWORD *)(a1 + 16) + 40LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 16) + 48LL));
      *(_QWORD *)(*a3 + 16) = 48;
      goto LABEL_128;
    }
    return 3221225626LL;
  }
  v61 = v60 - 1;
  if ( v61 )
  {
    v62 = v61 - 1;
    if ( v62 )
    {
      v63 = v62 - 210;
      if ( v63 )
      {
        v64 = v63 - 1;
        if ( !v64 )
          goto LABEL_93;
        v65 = v64 - 1;
        if ( !v65 )
          goto LABEL_43;
        if ( v65 != 1 )
          goto LABEL_81;
        goto LABEL_91;
      }
LABEL_95:
      v68 = (_DWORD *)ExAllocatePool2(66, 4, 1920224326);
      *a3 = (__int64)v68;
      if ( v68 )
      {
        LODWORD(v7) = 4;
        *v68 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
        goto LABEL_128;
      }
      return 3221225626LL;
    }
    v69 = *(unsigned __int8 *)(v6 + 5);
    if ( v69 > 0xD )
    {
      v73 = v69 - 15;
      if ( !v73 )
        goto LABEL_43;
      v74 = v73 - 1;
      if ( !v74 )
        goto LABEL_43;
      v75 = v74 - 2;
      if ( !v75 )
      {
        v76 = (_BYTE *)ExAllocatePool2(66, 1, 1920224326);
        *a3 = (__int64)v76;
        if ( v76 )
        {
          LODWORD(v7) = 1;
          *v76 = *(_BYTE *)(*(_QWORD *)(a1 + 16) + 24LL);
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v72 = v75 - 1;
      if ( !v72 )
        goto LABEL_95;
    }
    else
    {
      if ( v69 == 13 )
        goto LABEL_91;
      if ( !v69 )
        goto LABEL_93;
      v70 = v69 - 7;
      if ( !v70 )
        goto LABEL_95;
      v71 = v70 - 1;
      if ( !v71 )
        goto LABEL_43;
      v72 = v71 - 1;
      if ( !v72 )
        goto LABEL_91;
    }
    if ( v72 != 3 )
      goto LABEL_128;
    goto LABEL_93;
  }
  v7 = (unsigned int)(*(_DWORD *)(v6 + 24) + 24);
  v14 = ExAllocatePool2(66, v7, 1920224326);
  *a3 = v14;
  if ( !v14 )
    return 3221225626LL;
LABEL_14:
  v15 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)v14 = *(_OWORD *)(v15 + 24);
  *(_QWORD *)(v14 + 16) = *(_QWORD *)(v15 + 40);
  memmove(
    (void *)(*a3 + 24),
    *(const void **)(*(_QWORD *)(a1 + 16) + 32LL),
    *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL));
  *(_QWORD *)(*a3 + 8) = 24;
LABEL_128:
  *v88 = v7;
  return 0;
}

```

## disassembly

```asm
0x14000bcd8  mov     [rsp-38h+arg_18], rbx
0x14000bcdd  push    rbp
0x14000bcde  push    rsi
0x14000bcdf  push    rdi
0x14000bce0  push    r12
0x14000bce2  push    r13
0x14000bce4  push    r14
0x14000bce6  push    r15
0x14000bce8  mov     rbp, rsp
0x14000bceb  sub     rsp, 70h
0x14000bcef  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000bcf6  xor     rax, rsp
0x14000bcf9  mov     [rbp+var_10], rax
0x14000bcfd  xor     r12d, r12d
0x14000bd00  mov     [rbp+var_38], rdx
0x14000bd04  mov     rsi, rcx
0x14000bd07  mov     rbx, r8
0x14000bd0a  mov     rcx, [rcx+10h]
0x14000bd0e  mov     edi, r12d
0x14000bd11  movzx   r8d, byte ptr [rcx+4]
0x14000bd16  cmp     r8d, 15h
0x14000bd1a  ja      loc_14000C53E
0x14000bd20  jz      loc_14000C48C
0x14000bd26  cmp     r8d, 0Ah
0x14000bd2a  ja      loc_14000C0CC
0x14000bd30  jz      loc_14000C2D5
0x14000bd36  test    r8d, r8d
0x14000bd39  jz      loc_14000C05E
0x14000bd3f  sub     r8d, 3
0x14000bd43  jz      loc_14000C011
0x14000bd49  sub     r8d, 1
0x14000bd4d  jz      loc_14000C011
0x14000bd53  sub     r8d, 1
0x14000bd57  jz      loc_14000C2D5
0x14000bd5d  sub     r8d, 1
0x14000bd61  jz      loc_14000BE60
0x14000bd67  sub     r8d, 1
0x14000bd6b  jz      loc_14000BDF2
0x14000bd71  cmp     r8d, 1
0x14000bd75  jnz     loc_14000C536
0x14000bd7b  mov     edi, [rcx+18h]
0x14000bd7e  lea     r14d, [r12+18h]
0x14000bd83  add     edi, 18h
0x14000bd86  cmp     edi, r14d
0x14000bd89  jb      short loc_14000BDE8
0x14000bd8b  mov     edx, edi
0x14000bd8d  lea     ecx, [r12+42h]
0x14000bd92  mov     r8d, 72744C46h
0x14000bd98  call    cs:__imp_ExAllocatePool2
0x14000bd9f  nop     dword ptr [rax+rax+00h]
0x14000bda4  mov     [rbx], rax
0x14000bda7  test    rax, rax
0x14000bdaa  jz      loc_14000C839
0x14000bdb0  mov     rcx, [rsi+10h]
0x14000bdb4  movups  xmm0, xmmword ptr [rcx+18h]
0x14000bdb8  movups  xmmword ptr [rax], xmm0
0x14000bdbb  movsd   xmm1, qword ptr [rcx+28h]
0x14000bdc0  movsd   qword ptr [rax+10h], xmm1
0x14000bdc5  mov     rdx, [rsi+10h]
0x14000bdc9  mov     rcx, [rbx]
0x14000bdcc  add     rcx, r14; void *
0x14000bdcf  mov     r8d, [rdx+18h]; Size
0x14000bdd3  mov     rdx, [rdx+20h]; Src
0x14000bdd7  call    memmove
0x14000bddc  mov     rax, [rbx]
0x14000bddf  mov     [rax+8], r14
0x14000bde3  jmp     loc_14000C883
0x14000bde8  mov     eax, 0C0000095h
0x14000bded  jmp     loc_14000C88B
0x14000bdf2  mov     edi, [rcx+28h]
0x14000bdf5  mov     r8d, 72744C46h
0x14000bdfb  add     edi, 30h ; '0'
0x14000bdfe  mov     ecx, 42h ; 'B'
0x14000be03  mov     edx, edi
0x14000be05  call    cs:__imp_ExAllocatePool2
0x14000be0c  nop     dword ptr [rax+rax+00h]
0x14000be11  mov     [rbx], rax
0x14000be14  test    rax, rax
0x14000be17  jz      loc_14000C839
0x14000be1d  mov     rcx, [rsi+10h]
0x14000be21  movups  xmm0, xmmword ptr [rcx+18h]
0x14000be25  movups  xmmword ptr [rax], xmm0
0x14000be28  movups  xmm1, xmmword ptr [rcx+28h]
0x14000be2c  movups  xmmword ptr [rax+10h], xmm1
0x14000be30  movups  xmm0, xmmword ptr [rcx+38h]
0x14000be34  movups  xmmword ptr [rax+20h], xmm0
0x14000be38  mov     rdx, [rsi+10h]
0x14000be3c  mov     rcx, [rbx]
0x14000be3f  add     rcx, 30h ; '0'; void *
0x14000be43  mov     r8d, [rdx+28h]; Size
0x14000be47  mov     rdx, [rdx+20h]; Src
0x14000be4b  call    memmove
0x14000be50  mov     rax, [rbx]
0x14000be53  mov     qword ptr [rax+8], 30h ; '0'
0x14000be5b  jmp     loc_14000C883
0x14000be60  xor     eax, eax
0x14000be62  mov     [rbp+FileInformation], 4
0x14000be69  mov     [rbp+Src], ax
0x14000be6d  mov     r14d, 1
0x14000be73  mov     [rbp+var_1A], eax
0x14000be76  mov     r15d, r12d
0x14000be79  mov     [rbp+var_16], ax
0x14000be7d  mov     r13b, r12b
0x14000be80  mov     edi, [rcx+18h]
0x14000be83  mov     eax, [rcx+20h]
0x14000be86  add     edi, 28h ; '('
0x14000be89  sub     eax, 0Ah
0x14000be8c  cmp     eax, r14d
0x14000be8f  ja      loc_14000BF27
0x14000be95  mov     rax, [rcx+38h]
0x14000be99  cmp     [rax+8], r12
0x14000be9d  jz      loc_14000BF27
0x14000bea3  mov     rax, cs:GlobalLateBoundFunctions
0x14000beaa  test    rax, rax
0x14000bead  jz      short loc_14000BEB8
0x14000beaf  call    _guard_dispatch_icall
0x14000beb4  test    al, al
0x14000beb6  jz      short loc_14000BEC3
0x14000beb8  mov     rax, [rsi+10h]
0x14000bebc  mov     ecx, [rax]
0x14000bebe  test    cl, 2
0x14000bec1  jnz     short loc_14000BF27
0x14000bec3  mov     rax, [rsi+10h]
0x14000bec7  lea     r8, [rbp+FileInformation]; FileInformation
0x14000becb  xorps   xmm0, xmm0
0x14000bece  mov     [rsp+70h+FileInformationClass], 9; FileInformationClass
0x14000bed6  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000beda  mov     r9d, 0Ch; Length
0x14000bee0  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14000bee4  mov     rcx, [rax+38h]
0x14000bee8  mov     rcx, [rcx+8]; FileHandle
0x14000beec  call    cs:__imp_ZwQueryInformationFile
0x14000bef3  nop     dword ptr [rax+rax+00h]
0x14000bef8  mov     edx, 80000000h
0x14000befd  mov     r8d, 80000005h
0x14000bf03  lea     ecx, [rax+rdx]
0x14000bf06  test    edx, ecx
0x14000bf08  jnz     short loc_14000BF0F
0x14000bf0a  cmp     eax, r8d
0x14000bf0d  jnz     short loc_14000BF27
0x14000bf0f  mov     r15d, [rbp+FileInformation]
0x14000bf13  add     edi, 4
0x14000bf16  add     edi, r15d
0x14000bf19  movzx   r12d, r12b
0x14000bf1d  cmp     eax, r8d
0x14000bf20  mov     r13b, r14b
0x14000bf23  cmovz   r12d, r14d
0x14000bf27  mov     edx, edi
0x14000bf29  mov     ecx, 40h ; '@'
0x14000bf2e  mov     r8d, 72744C46h
0x14000bf34  call    cs:__imp_ExAllocatePool2
0x14000bf3b  nop     dword ptr [rax+rax+00h]
0x14000bf40  mov     [rbx], rax
0x14000bf43  test    rax, rax
0x14000bf46  jz      loc_14000C839
0x14000bf4c  mov     rcx, [rsi+10h]
0x14000bf50  movups  xmm0, xmmword ptr [rcx+18h]
0x14000bf54  movups  xmmword ptr [rax], xmm0
0x14000bf57  movups  xmm1, xmmword ptr [rcx+28h]
0x14000bf5b  movups  xmmword ptr [rax+10h], xmm1
0x14000bf5f  movsd   xmm0, qword ptr [rcx+38h]
0x14000bf64  movsd   qword ptr [rax+20h], xmm0
0x14000bf69  mov     rdx, [rsi+10h]
0x14000bf6d  mov     rcx, [rbx]
0x14000bf70  add     rcx, 28h ; '('; void *
0x14000bf74  mov     r8d, [rdx+18h]; Size
0x14000bf78  mov     rdx, [rdx+38h]; Src
0x14000bf7c  call    memmove
0x14000bf81  mov     rax, [rbx]
0x14000bf84  mov     qword ptr [rax+20h], 28h ; '('
0x14000bf8c  test    r13b, r13b
0x14000bf8f  jz      loc_14000C883
0x14000bf95  mov     rdx, [rbx]
0x14000bf98  mov     rcx, [rsi+10h]
0x14000bf9c  test    r12b, r12b
0x14000bf9f  jz      short loc_14000BFE7
0x14000bfa1  add     rdx, 28h ; '('
0x14000bfa5  mov     [rsp+70h+FileInformationClass], 9; FileInformationClass
0x14000bfad  xorps   xmm0, xmm0
0x14000bfb0  lea     r9d, [r15+4]; Length
0x14000bfb4  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000bfb8  mov     r8d, [rcx+18h]
0x14000bfbc  mov     rcx, [rcx+38h]
0x14000bfc0  add     r8, rdx; FileInformation
0x14000bfc3  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14000bfc7  mov     rcx, [rcx+8]; FileHandle
0x14000bfcb  call    cs:__imp_ZwQueryInformationFile
0x14000bfd2  nop     dword ptr [rax+rax+00h]
0x14000bfd7  test    eax, eax
0x14000bfd9  jns     loc_14000C883
0x14000bfdf  sub     edi, r15d
0x14000bfe2  jmp     loc_14000C883
0x14000bfe7  mov     eax, [rcx+18h]
0x14000bfea  mov     r8d, r15d; Size
0x14000bfed  mov     [rax+rdx+28h], r15d
0x14000bff2  lea     rdx, [rbp+Src]; Src
0x14000bff6  mov     rax, [rsi+10h]
0x14000bffa  mov     ecx, [rax+18h]
0x14000bffd  mov     rax, [rbx]
0x14000c000  add     rax, 2Ch ; ','
0x14000c004  add     rcx, rax; void *
0x14000c007  call    memmove
0x14000c00c  jmp     loc_14000C883
0x14000c011  mov     edx, 28h ; '('
0x14000c016  mov     r8d, 72744C46h
0x14000c01c  lea     ecx, [rdx+1Ah]
0x14000c01f  call    cs:__imp_ExAllocatePool2
0x14000c026  nop     dword ptr [rax+rax+00h]
0x14000c02b  mov     [rbx], rax
0x14000c02e  test    rax, rax
0x14000c031  jz      loc_14000C839
0x14000c037  mov     rcx, [rsi+10h]
0x14000c03b  mov     edi, 28h ; '('
0x14000c040  movups  xmm0, xmmword ptr [rcx+18h]
0x14000c044  movups  xmmword ptr [rax], xmm0
0x14000c047  movups  xmm1, xmmword ptr [rcx+28h]
0x14000c04b  movups  xmmword ptr [rax+10h], xmm1
0x14000c04f  movsd   xmm0, qword ptr [rcx+38h]
0x14000c054  movsd   qword ptr [rax+20h], xmm0
0x14000c059  jmp     loc_14000C883
0x14000c05e  mov     edi, 48h ; 'H'
0x14000c063  mov     r8d, 72744C46h
0x14000c069  mov     edx, edi
0x14000c06b  lea     ecx, [rdi-6]
0x14000c06e  call    cs:__imp_ExAllocatePool2
0x14000c075  nop     dword ptr [rax+rax+00h]
0x14000c07a  mov     [rbx], rax
0x14000c07d  test    rax, rax
0x14000c080  jz      loc_14000C839
0x14000c086  mov     rcx, [rsi+10h]
0x14000c08a  movups  xmm0, xmmword ptr [rcx+18h]
0x14000c08e  movups  xmmword ptr [rax], xmm0
0x14000c091  movups  xmm1, xmmword ptr [rcx+28h]
0x14000c095  movups  xmmword ptr [rax+10h], xmm1
0x14000c099  movups  xmm0, xmmword ptr [rcx+38h]
0x14000c09d  movups  xmmword ptr [rax+20h], xmm0
0x14000c0a1  mov     rax, [rsi+10h]
0x14000c0a5  mov     rcx, [rax+18h]
0x14000c0a9  mov     rax, [rbx]
0x14000c0ac  movups  xmm0, xmmword ptr [rcx]
0x14000c0af  movups  xmmword ptr [rax+30h], xmm0
0x14000c0b3  movsd   xmm1, qword ptr [rcx+10h]
0x14000c0b8  movsd   qword ptr [rax+40h], xmm1
0x14000c0bd  mov     rax, [rbx]
0x14000c0c0  mov     qword ptr [rax], 30h ; '0'
0x14000c0c7  jmp     loc_14000C883
0x14000c0cc  sub     r8d, 0Bh
0x14000c0d0  jz      loc_14000C421
0x14000c0d6  sub     r8d, 1
0x14000c0da  jz      loc_14000C31D
0x14000c0e0  sub     r8d, 1
0x14000c0e4  jz      loc_14000C2BE
0x14000c0ea  sub     r8d, 1
0x14000c0ee  jz      loc_14000C2D5
0x14000c0f4  sub     r8d, 1
0x14000c0f8  jz      loc_14000C2D5
0x14000c0fe  sub     r8d, 2
0x14000c102  jz      short loc_14000C14E
0x14000c104  cmp     r8d, 3
0x14000c108  jnz     loc_14000C536
0x14000c10e  mov     edi, 20h ; ' '
0x14000c113  mov     r8d, 72744C46h
0x14000c119  mov     edx, edi
0x14000c11b  lea     ecx, [rdi+22h]
0x14000c11e  call    cs:__imp_ExAllocatePool2
0x14000c125  nop     dword ptr [rax+rax+00h]
0x14000c12a  mov     [rbx], rax
0x14000c12d  test    rax, rax
0x14000c130  jz      loc_14000C839
0x14000c136  mov     rcx, [rsi+10h]
0x14000c13a  movups  xmm0, xmmword ptr [rcx+18h]
0x14000c13e  movups  xmmword ptr [rax], xmm0
0x14000c141  movups  xmm1, xmmword ptr [rcx+28h]
0x14000c145  movups  xmmword ptr [rax+10h], xmm1
0x14000c149  jmp     loc_14000C883
0x14000c14e  mov     edx, 30h ; '0'
0x14000c153  mov     r8d, 72744C46h
0x14000c159  lea     ecx, [rdx+12h]
0x14000c15c  call    cs:__imp_ExAllocatePool2
0x14000c163  nop     dword ptr [rax+rax+00h]
0x14000c168  mov     [rbx], rax
0x14000c16b  test    rax, rax
0x14000c16e  jz      loc_14000C839
0x14000c174  mov     r8, [rsi+10h]
0x14000c178  mov     edi, 30h ; '0'
0x14000c17d  movzx   edx, byte ptr [r8+5]
0x14000c182  sub     edx, 1
0x14000c185  jz      loc_14000C281
0x14000c18b  sub     edx, 1
0x14000c18e  jz      loc_14000C21E
0x14000c194  sub     edx, 1
0x14000c197  jz      short loc_14000C1D5
0x14000c199  cmp     edx, 1
0x14000c19c  jnz     loc_14000C883
0x14000c1a2  mov     qword ptr [rax], 28h ; '('
0x14000c1a9  mov     r14d, edx
0x14000c1ac  mov     rax, [rsi+10h]
0x14000c1b0  mov     rcx, [rbx]
0x14000c1b3  mov     eax, [rax+20h]
0x14000c1b6  mov     [rcx+8], eax
  ... truncated ...
```
