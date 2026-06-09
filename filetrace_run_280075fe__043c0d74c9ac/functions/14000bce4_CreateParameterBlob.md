# CreateParameterBlob

- ea: `0x14000bce4`
- end: `0x14000c8e4`
- name: `CreateParameterBlob`
- size: `3072`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400010b0`
- `0x140002110`

## callees

- `0x140003510`
- `0x140003550`
- `0x140003600`
- `0x140003900`
- `0x14000bce4`

## import_xrefs

- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000c514`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14000c514`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000bef8`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000bfea`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000bef8`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000bfea`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c4be`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14000c4be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c551`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c551`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bda4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000be11`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bf43`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c040`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c091`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c143`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c183`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c310`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c367`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c3c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c460`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c4dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c5cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c603`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c641`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c6de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c71c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c754`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c803`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c856`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bda4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000be11`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000bf43`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c040`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c091`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c143`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c183`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c310`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c367`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c3c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c460`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c4dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c5cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c603`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c641`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c6de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c71c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c754`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c803`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c856`

## pseudocode

```c
__int64 __fastcall CreateParameterBlob(__int64 a1, _DWORD *a2, __int64 *a3)
{
  bool v3; // r12
  __int64 v6; // rcx
  SIZE_T v7; // rsi
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _OWORD *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // r15d
  char v20; // r13
  __int64 v21; // rax
  NTSTATUS v22; // eax
  PVOID v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _OWORD *v28; // rax
  __int64 v29; // rcx
  _OWORD *PoolWithTag; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  _QWORD *v33; // rax
  unsigned int v34; // r8d
  unsigned int v35; // r8d
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  unsigned int v38; // r8d
  unsigned int v39; // r8d
  _OWORD *v40; // rax
  __int64 v41; // rcx
  _OWORD *v42; // rax
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 i; // rcx
  char v47; // al
  _QWORD *v48; // rax
  __int64 v49; // rcx
  _OWORD *v50; // rax
  __int64 v51; // rcx
  unsigned __int16 *v52; // rax
  _OWORD *v53; // rax
  __int64 v54; // rcx
  _OWORD *v55; // rcx
  _QWORD *v56; // rax
  __int64 v57; // rcx
  _OWORD *v58; // rax
  NTSTATUS v59; // eax
  __int64 v60; // rcx
  unsigned int v61; // r8d
  unsigned int v62; // r8d
  unsigned int v63; // r8d
  unsigned int v64; // r8d
  unsigned int v65; // r8d
  unsigned int v66; // r8d
  _QWORD *v67; // rax
  _OWORD *v68; // rax
  _DWORD *v69; // rax
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  _BYTE *v77; // rax
  _OWORD *v78; // rax
  __int64 v79; // rcx
  unsigned int v80; // r8d
  unsigned int v81; // r8d
  unsigned int v82; // r8d
  unsigned int v83; // r8d
  _OWORD *v84; // rax
  _OWORD *v85; // rax
  __int64 v86; // rcx
  __int64 v87; // rax
  ULONG BufferLength; // [rsp+30h] [rbp-40h] BYREF
  _DWORD *v89; // [rsp+38h] [rbp-38h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  int FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int16 Src; // [rsp+54h] [rbp-1Ch] BYREF
  int v93; // [rsp+56h] [rbp-1Ah]
  __int16 v94; // [rsp+5Ah] [rbp-16h]

  v3 = 0;
  v89 = a2;
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
            PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x72744C46u);
            *a3 = (__int64)PoolWithTag;
            if ( PoolWithTag )
            {
              v31 = *(_QWORD *)(a1 + 16);
              *PoolWithTag = *(_OWORD *)(v31 + 24);
              PoolWithTag[1] = *(_OWORD *)(v31 + 40);
              PoolWithTag[2] = *(_OWORD *)(v31 + 56);
              v32 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
              v33 = (_QWORD *)*a3;
              *((_OWORD *)v33 + 3) = *(_OWORD *)v32;
              v33[8] = *(_QWORD *)(v32 + 16);
              *(_QWORD *)*a3 = 48;
              goto LABEL_128;
            }
            return 3221225626LL;
          }
          v9 = v8 - 3;
          if ( !v9 || (v10 = v9 - 1) == 0 )
          {
            v28 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x28u, 0x72744C46u);
            *a3 = (__int64)v28;
            if ( v28 )
            {
              v29 = *(_QWORD *)(a1 + 16);
              LODWORD(v7) = 40;
              *v28 = *(_OWORD *)(v29 + 24);
              v28[1] = *(_OWORD *)(v29 + 40);
              *((_QWORD *)v28 + 4) = *(_QWORD *)(v29 + 56);
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
              v93 = 0;
              v19 = 0;
              v94 = 0;
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
              v23 = ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)v7, 0x72744C46u);
              *a3 = (__int64)v23;
              if ( v23 )
              {
                memset(v23, 0, (unsigned int)v7);
                v24 = *(_QWORD *)(a1 + 16);
                v25 = (_QWORD *)*a3;
                *(_OWORD *)v25 = *(_OWORD *)(v24 + 24);
                *((_OWORD *)v25 + 1) = *(_OWORD *)(v24 + 40);
                v25[4] = *(_QWORD *)(v24 + 56);
                memmove(
                  (void *)(*a3 + 40),
                  *(const void **)(*(_QWORD *)(a1 + 16) + 56LL),
                  *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL));
                *(_QWORD *)(*a3 + 32) = 40;
                if ( v20 )
                {
                  v26 = *a3;
                  v27 = *(_QWORD *)(a1 + 16);
                  if ( v3 )
                  {
                    IoStatusBlock = 0;
                    if ( ZwQueryInformationFile(
                           *(HANDLE *)(*(_QWORD *)(v27 + 56) + 8LL),
                           &IoStatusBlock,
                           (PVOID)(v26 + 40 + *(unsigned int *)(v27 + 24)),
                           v19 + 4,
                           FileNameInformation) < 0 )
                      LODWORD(v7) = v7 - v19;
                  }
                  else
                  {
                    *(_DWORD *)(*(unsigned int *)(v27 + 24) + v26 + 40) = v19;
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
              v17 = ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)v7, 0x72744C46u);
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
              v14 = ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)v7, 0x72744C46u);
              *a3 = (__int64)v14;
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
        v48 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x72744C46u);
        *a3 = (__int64)v48;
        if ( v48 )
        {
          v49 = *(_QWORD *)(a1 + 16);
          LODWORD(v7) = 24;
          *(_OWORD *)v48 = *(_OWORD *)(v49 + 24);
          v48[2] = *(_QWORD *)(v49 + 40);
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v34 = v8 - 11;
      if ( !v34 )
      {
        v7 = (unsigned int)(*(_DWORD *)(v6 + 24) + 24);
        v56 = ExAllocatePoolWithTag((POOL_TYPE)512, v7, 0x72744C46u);
        *a3 = (__int64)v56;
        if ( v56 )
        {
          v57 = *(_QWORD *)(a1 + 16);
          *(_OWORD *)v56 = *(_OWORD *)(v57 + 24);
          v56[2] = *(_QWORD *)(v57 + 40);
          memmove(
            (void *)(*a3 + 24),
            *(const void **)(*(_QWORD *)(a1 + 16) + 40LL),
            *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL));
          *(_QWORD *)(*a3 + 16) = 24;
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
        if ( *(_BYTE *)(v6 + 5) == 1 )
        {
          v52 = *(unsigned __int16 **)(v6 + 32);
          LODWORD(v7) = 48;
          if ( v52 )
            LODWORD(v7) = *v52 + 64;
          v53 = ExAllocatePoolWithTag((POOL_TYPE)512, (unsigned int)v7, 0x72744C46u);
          *a3 = (__int64)v53;
          if ( v53 )
          {
            v54 = *(_QWORD *)(a1 + 16);
            *v53 = *(_OWORD *)(v54 + 24);
            v53[1] = *(_OWORD *)(v54 + 40);
            v53[2] = *(_OWORD *)(v54 + 56);
            v55 = *(_OWORD **)(*(_QWORD *)(a1 + 16) + 32LL);
            if ( v55 )
            {
              *(_OWORD *)(*a3 + 48) = *v55;
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
          v50 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x30u, 0x72744C46u);
          *a3 = (__int64)v50;
          if ( v50 )
          {
            v51 = *(_QWORD *)(a1 + 16);
            LODWORD(v7) = 48;
            *v50 = *(_OWORD *)(v51 + 24);
            v50[1] = *(_OWORD *)(v51 + 40);
            v50[2] = *(_OWORD *)(v51 + 56);
            goto LABEL_128;
          }
          return 3221225626LL;
        }
        goto LABEL_81;
      }
      v36 = v35 - 1;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( !v37 )
          goto LABEL_63;
        v38 = v37 - 1;
        if ( !v38 )
          goto LABEL_63;
        v39 = v38 - 2;
        if ( !v39 )
        {
          v42 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x30u, 0x72744C46u);
          *a3 = (__int64)v42;
          if ( v42 )
          {
            v43 = *(_QWORD *)(a1 + 16);
            LODWORD(v7) = 48;
            switch ( *(_BYTE *)(v43 + 5) )
            {
              case 1:
                *v42 = *(_OWORD *)(v43 + 24);
                v42[1] = *(_OWORD *)(v43 + 40);
                *((_QWORD *)v42 + 4) = *(_QWORD *)(v43 + 56);
                *(_QWORD *)(*a3 + 40) = **(_QWORD **)(*(_QWORD *)(a1 + 16) + 24LL);
                *(_QWORD *)*a3 = 40;
                goto LABEL_128;
              case 2:
                *(_QWORD *)v42 = 40;
                *(_DWORD *)(*a3 + 8) = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
                *(_QWORD *)(*a3 + 16) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 40LL);
                for ( i = 0; i != 2; ++i )
                  *(_BYTE *)(*a3 + i + 32) = 0;
                *(_QWORD *)(*a3 + 24) = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL);
                *(_QWORD *)(*a3 + 40) = **(_QWORD **)(*(_QWORD *)(a1 + 16) + 24LL);
                goto LABEL_128;
              case 3:
                *(_QWORD *)v42 = 40;
                v45 = 0;
                *(_DWORD *)(*a3 + 8) = 0;
                *(_QWORD *)(*a3 + 16) = 0;
                do
                  *(_BYTE *)(*a3 + v45++ + 32) = 0;
                while ( v45 != 2 );
                break;
              case 4:
                *(_QWORD *)v42 = 40;
                *(_DWORD *)(*a3 + 8) = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
                v44 = 0;
                *(_QWORD *)(*a3 + 16) = 0;
                do
                  *(_BYTE *)(*a3 + v44++ + 32) = 0;
                while ( v44 != 2 );
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
        if ( v39 != 3 )
          goto LABEL_81;
LABEL_43:
        LODWORD(v7) = 32;
        v40 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x20u, 0x72744C46u);
        *a3 = (__int64)v40;
        if ( v40 )
        {
          v41 = *(_QWORD *)(a1 + 16);
          *v40 = *(_OWORD *)(v41 + 24);
          v40[1] = *(_OWORD *)(v41 + 40);
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v47 = *(_BYTE *)(v6 + 5);
      if ( !v47 )
        goto LABEL_63;
      if ( v47 != 2 )
      {
        if ( v47 != 4 )
          goto LABEL_81;
        goto LABEL_63;
      }
LABEL_93:
      v68 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x10u, 0x72744C46u);
      *a3 = (__int64)v68;
      if ( v68 )
      {
        LODWORD(v7) = 16;
        *v68 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
        goto LABEL_128;
      }
      return 3221225626LL;
    }
    BufferLength = 0;
    BufferLength = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(v6 + 32));
    LODWORD(v7) = BufferLength + 16;
    v58 = ExAllocatePoolWithTag((POOL_TYPE)512, BufferLength + 16, 0x72744C46u);
    *a3 = (__int64)v58;
    if ( !v58 )
      return 3221225626LL;
    *v58 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
    v59 = RtlAbsoluteToSelfRelativeSD(
            *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)(a1 + 16) + 32LL),
            (PSECURITY_DESCRIPTOR)(*a3 + 16),
            &BufferLength);
    if ( v59 >= 0 )
      goto LABEL_128;
    v60 = *a3;
    if ( v59 != -1073741593 )
    {
      ExFreePoolWithTag((PVOID)v60, 0x72744C46u);
      LODWORD(v7) = 0;
      goto LABEL_81;
    }
    memmove((void *)(v60 + 16), *(const void **)(*(_QWORD *)(a1 + 16) + 32LL), BufferLength);
LABEL_127:
    *(_QWORD *)(*a3 + 8) = 16;
    goto LABEL_128;
  }
  if ( (unsigned __int8)v8 > 0xF1u )
  {
    v80 = v8 - 242;
    if ( !v80 )
    {
      LODWORD(v7) = 72;
      v85 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x72744C46u);
      *a3 = (__int64)v85;
      if ( !v85 )
        return 3221225626LL;
      *v85 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      v86 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
      v87 = *a3;
      *(_OWORD *)(v87 + 16) = *(_OWORD *)v86;
      *(_OWORD *)(v87 + 32) = *(_OWORD *)(v86 + 16);
      *(_OWORD *)(v87 + 48) = *(_OWORD *)(v86 + 32);
      *(_QWORD *)(v87 + 64) = *(_QWORD *)(v86 + 48);
      goto LABEL_127;
    }
    v81 = v80 - 1;
    if ( !v81 )
      goto LABEL_43;
    v82 = v81 - 9;
    if ( v82 )
    {
      v83 = v82 - 1;
      if ( !v83 )
      {
        v84 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x72744C46u);
        *a3 = (__int64)v84;
        if ( v84 )
        {
          LODWORD(v7) = 24;
          *v84 = *(_OWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
          *(_QWORD *)(*a3 + 16) = **(_QWORD **)(*(_QWORD *)(a1 + 16) + 24LL);
          *(_QWORD *)*a3 = 16;
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      if ( v83 != 2 )
        goto LABEL_81;
      goto LABEL_63;
    }
LABEL_91:
    LODWORD(v7) = 8;
    v67 = ExAllocatePoolWithTag((POOL_TYPE)512, 8u, 0x72744C46u);
    *a3 = (__int64)v67;
    if ( v67 )
    {
      *v67 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      goto LABEL_128;
    }
    return 3221225626LL;
  }
  if ( (_BYTE)v8 == 0xF1 )
    goto LABEL_43;
  v61 = v8 - 25;
  if ( !v61 )
  {
    v7 = (unsigned int)(*(_DWORD *)(v6 + 48) + 48);
    v78 = ExAllocatePoolWithTag((POOL_TYPE)512, v7, 0x72744C46u);
    *a3 = (__int64)v78;
    if ( v78 )
    {
      v79 = *(_QWORD *)(a1 + 16);
      *v78 = *(_OWORD *)(v79 + 24);
      v78[1] = *(_OWORD *)(v79 + 40);
      v78[2] = *(_OWORD *)(v79 + 56);
      memmove(
        (void *)(*a3 + 48),
        *(const void **)(*(_QWORD *)(a1 + 16) + 40LL),
        *(unsigned int *)(*(_QWORD *)(a1 + 16) + 48LL));
      *(_QWORD *)(*a3 + 16) = 48;
      goto LABEL_128;
    }
    return 3221225626LL;
  }
  v62 = v61 - 1;
  if ( v62 )
  {
    v63 = v62 - 1;
    if ( v63 )
    {
      v64 = v63 - 210;
      if ( v64 )
      {
        v65 = v64 - 1;
        if ( !v65 )
          goto LABEL_93;
        v66 = v65 - 1;
        if ( !v66 )
          goto LABEL_43;
        if ( v66 != 1 )
          goto LABEL_81;
        goto LABEL_91;
      }
LABEL_95:
      v69 = ExAllocatePoolWithTag((POOL_TYPE)512, 4u, 0x72744C46u);
      *a3 = (__int64)v69;
      if ( v69 )
      {
        LODWORD(v7) = 4;
        *v69 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
        goto LABEL_128;
      }
      return 3221225626LL;
    }
    v70 = *(unsigned __int8 *)(v6 + 5);
    if ( v70 > 0xD )
    {
      v74 = v70 - 15;
      if ( !v74 )
        goto LABEL_43;
      v75 = v74 - 1;
      if ( !v75 )
        goto LABEL_43;
      v76 = v75 - 2;
      if ( !v76 )
      {
        v77 = ExAllocatePoolWithTag((POOL_TYPE)512, 1u, 0x72744C46u);
        *a3 = (__int64)v77;
        if ( v77 )
        {
          LODWORD(v7) = 1;
          *v77 = *(_BYTE *)(*(_QWORD *)(a1 + 16) + 24LL);
          goto LABEL_128;
        }
        return 3221225626LL;
      }
      v73 = v76 - 1;
      if ( !v73 )
        goto LABEL_95;
    }
    else
    {
      if ( v70 == 13 )
        goto LABEL_91;
      if ( !v70 )
        goto LABEL_93;
      v71 = v70 - 7;
      if ( !v71 )
        goto LABEL_95;
      v72 = v71 - 1;
      if ( !v72 )
        goto LABEL_43;
      v73 = v72 - 1;
      if ( !v73 )
        goto LABEL_91;
    }
    if ( v73 != 3 )
      goto LABEL_128;
    goto LABEL_93;
  }
  v7 = (unsigned int)(*(_DWORD *)(v6 + 24) + 24);
  v14 = ExAllocatePoolWithTag((POOL_TYPE)512, v7, 0x72744C46u);
  *a3 = (__int64)v14;
  if ( !v14 )
    return 3221225626LL;
LABEL_14:
  v15 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)v14 = *(_OWORD *)(v15 + 24);
  v14[2] = *(_QWORD *)(v15 + 40);
  memmove(
    (void *)(*a3 + 24),
    *(const void **)(*(_QWORD *)(a1 + 16) + 32LL),
    *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL));
  *(_QWORD *)(*a3 + 8) = 24;
LABEL_128:
  *v89 = v7;
  return 0;
}

```

## disassembly

```asm
0x14000bce4  mov     [rsp-38h+arg_18], rbx
0x14000bce9  push    rbp
0x14000bcea  push    rsi
0x14000bceb  push    rdi
0x14000bcec  push    r12
0x14000bcee  push    r13
0x14000bcf0  push    r14
0x14000bcf2  push    r15
0x14000bcf4  mov     rbp, rsp
0x14000bcf7  sub     rsp, 70h
0x14000bcfb  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000bd02  xor     rax, rsp
0x14000bd05  mov     [rbp+var_10], rax
0x14000bd09  xor     r12d, r12d
0x14000bd0c  mov     [rbp+var_38], rdx
0x14000bd10  mov     rdi, rcx
0x14000bd13  mov     rbx, r8
0x14000bd16  mov     rcx, [rcx+10h]
0x14000bd1a  mov     esi, r12d
0x14000bd1d  movzx   r8d, byte ptr [rcx+4]
0x14000bd22  cmp     r8d, 15h
0x14000bd26  ja      loc_14000C568
0x14000bd2c  jz      loc_14000C4B6
0x14000bd32  cmp     r8d, 0Ah
0x14000bd36  ja      loc_14000C0EF
0x14000bd3c  jz      loc_14000C2FC
0x14000bd42  test    r8d, r8d
0x14000bd45  jz      loc_14000C07F
0x14000bd4b  sub     r8d, 3
0x14000bd4f  jz      loc_14000C030
0x14000bd55  sub     r8d, 1
0x14000bd59  jz      loc_14000C030
0x14000bd5f  sub     r8d, 1
0x14000bd63  jz      loc_14000C2FC
0x14000bd69  sub     r8d, 1
0x14000bd6d  jz      loc_14000BE6C
0x14000bd73  sub     r8d, 1
0x14000bd77  jz      loc_14000BDFE
0x14000bd7d  cmp     r8d, 1
0x14000bd81  jnz     loc_14000C560
0x14000bd87  mov     esi, [rcx+18h]
0x14000bd8a  lea     r14d, [r12+18h]
0x14000bd8f  add     esi, 18h
0x14000bd92  cmp     esi, r14d
0x14000bd95  jb      short loc_14000BDF4
0x14000bd97  mov     edx, esi; NumberOfBytes
0x14000bd99  mov     ecx, 200h; PoolType
0x14000bd9e  mov     r8d, 72744C46h; Tag
0x14000bda4  call    cs:__imp_ExAllocatePoolWithTag
0x14000bdab  nop     dword ptr [rax+rax+00h]
0x14000bdb0  mov     [rbx], rax
0x14000bdb3  test    rax, rax
0x14000bdb6  jz      loc_14000C86D
0x14000bdbc  mov     rcx, [rdi+10h]
0x14000bdc0  movups  xmm0, xmmword ptr [rcx+18h]
0x14000bdc4  movups  xmmword ptr [rax], xmm0
0x14000bdc7  movsd   xmm1, qword ptr [rcx+28h]
0x14000bdcc  movsd   qword ptr [rax+10h], xmm1
0x14000bdd1  mov     rdx, [rdi+10h]
0x14000bdd5  mov     rcx, [rbx]
0x14000bdd8  add     rcx, r14; void *
0x14000bddb  mov     r8d, [rdx+18h]; Size
0x14000bddf  mov     rdx, [rdx+20h]; Src
0x14000bde3  call    memmove
0x14000bde8  mov     rax, [rbx]
0x14000bdeb  mov     [rax+8], r14
0x14000bdef  jmp     loc_14000C8B7
0x14000bdf4  mov     eax, 0C0000095h
0x14000bdf9  jmp     loc_14000C8BF
0x14000bdfe  mov     esi, [rcx+28h]
0x14000be01  mov     r8d, 72744C46h; Tag
0x14000be07  add     esi, 30h ; '0'
0x14000be0a  mov     ecx, 200h; PoolType
0x14000be0f  mov     edx, esi; NumberOfBytes
0x14000be11  call    cs:__imp_ExAllocatePoolWithTag
0x14000be18  nop     dword ptr [rax+rax+00h]
0x14000be1d  mov     [rbx], rax
0x14000be20  test    rax, rax
0x14000be23  jz      loc_14000C86D
0x14000be29  mov     rcx, [rdi+10h]
0x14000be2d  movups  xmm0, xmmword ptr [rcx+18h]
0x14000be31  movups  xmmword ptr [rax], xmm0
0x14000be34  movups  xmm1, xmmword ptr [rcx+28h]
0x14000be38  movups  xmmword ptr [rax+10h], xmm1
0x14000be3c  movups  xmm0, xmmword ptr [rcx+38h]
0x14000be40  movups  xmmword ptr [rax+20h], xmm0
0x14000be44  mov     rdx, [rdi+10h]
0x14000be48  mov     rcx, [rbx]
0x14000be4b  add     rcx, 30h ; '0'; void *
0x14000be4f  mov     r8d, [rdx+28h]; Size
0x14000be53  mov     rdx, [rdx+20h]; Src
0x14000be57  call    memmove
0x14000be5c  mov     rax, [rbx]
0x14000be5f  mov     qword ptr [rax+8], 30h ; '0'
0x14000be67  jmp     loc_14000C8B7
0x14000be6c  xor     eax, eax
0x14000be6e  mov     [rbp+FileInformation], 4
0x14000be75  mov     [rbp+Src], ax
0x14000be79  mov     r14d, 1
0x14000be7f  mov     [rbp+var_1A], eax
0x14000be82  mov     r15d, r12d
0x14000be85  mov     [rbp+var_16], ax
0x14000be89  mov     r13b, r12b
0x14000be8c  mov     esi, [rcx+18h]
0x14000be8f  mov     eax, [rcx+20h]
0x14000be92  add     esi, 28h ; '('
0x14000be95  sub     eax, 0Ah
0x14000be98  cmp     eax, r14d
0x14000be9b  ja      loc_14000BF33
0x14000bea1  mov     rax, [rcx+38h]
0x14000bea5  cmp     [rax+8], r12
0x14000bea9  jz      loc_14000BF33
0x14000beaf  mov     rax, cs:GlobalLateBoundFunctions
0x14000beb6  test    rax, rax
0x14000beb9  jz      short loc_14000BEC4
0x14000bebb  call    _guard_dispatch_icall
0x14000bec0  test    al, al
0x14000bec2  jz      short loc_14000BECF
0x14000bec4  mov     rax, [rdi+10h]
0x14000bec8  mov     ecx, [rax]
0x14000beca  test    cl, 2
0x14000becd  jnz     short loc_14000BF33
0x14000becf  mov     rax, [rdi+10h]
0x14000bed3  lea     r8, [rbp+FileInformation]; FileInformation
0x14000bed7  xorps   xmm0, xmm0
0x14000beda  mov     [rsp+70h+FileInformationClass], 9; FileInformationClass
0x14000bee2  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000bee6  mov     r9d, 0Ch; Length
0x14000beec  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14000bef0  mov     rcx, [rax+38h]
0x14000bef4  mov     rcx, [rcx+8]; FileHandle
0x14000bef8  call    cs:__imp_ZwQueryInformationFile
0x14000beff  nop     dword ptr [rax+rax+00h]
0x14000bf04  mov     edx, 80000000h
0x14000bf09  mov     r8d, 80000005h
0x14000bf0f  lea     ecx, [rax+rdx]
0x14000bf12  test    edx, ecx
0x14000bf14  jnz     short loc_14000BF1B
0x14000bf16  cmp     eax, r8d
0x14000bf19  jnz     short loc_14000BF33
0x14000bf1b  mov     r15d, [rbp+FileInformation]
0x14000bf1f  add     esi, 4
0x14000bf22  add     esi, r15d
0x14000bf25  movzx   r12d, r12b
0x14000bf29  cmp     eax, r8d
0x14000bf2c  mov     r13b, r14b
0x14000bf2f  cmovz   r12d, r14d
0x14000bf33  mov     r8d, 72744C46h; Tag
0x14000bf39  mov     edx, esi; NumberOfBytes
0x14000bf3b  mov     ecx, 200h; PoolType
0x14000bf40  mov     r14d, esi
0x14000bf43  call    cs:__imp_ExAllocatePoolWithTag
0x14000bf4a  nop     dword ptr [rax+rax+00h]
0x14000bf4f  mov     [rbx], rax
0x14000bf52  test    rax, rax
0x14000bf55  jz      loc_14000C86D
0x14000bf5b  mov     r8d, r14d; Size
0x14000bf5e  xor     edx, edx; Val
0x14000bf60  mov     rcx, rax; void *
0x14000bf63  call    memset
0x14000bf68  mov     rax, [rdi+10h]
0x14000bf6c  mov     rcx, [rbx]
0x14000bf6f  movups  xmm0, xmmword ptr [rax+18h]
0x14000bf73  movups  xmmword ptr [rcx], xmm0
0x14000bf76  movups  xmm1, xmmword ptr [rax+28h]
0x14000bf7a  movups  xmmword ptr [rcx+10h], xmm1
0x14000bf7e  movsd   xmm0, qword ptr [rax+38h]
0x14000bf83  movsd   qword ptr [rcx+20h], xmm0
0x14000bf88  mov     rdx, [rdi+10h]
0x14000bf8c  mov     rcx, [rbx]
0x14000bf8f  add     rcx, 28h ; '('; void *
0x14000bf93  mov     r8d, [rdx+18h]; Size
0x14000bf97  mov     rdx, [rdx+38h]; Src
0x14000bf9b  call    memmove
0x14000bfa0  mov     rax, [rbx]
0x14000bfa3  mov     qword ptr [rax+20h], 28h ; '('
0x14000bfab  test    r13b, r13b
0x14000bfae  jz      loc_14000C8B7
0x14000bfb4  mov     rdx, [rbx]
0x14000bfb7  mov     rcx, [rdi+10h]
0x14000bfbb  test    r12b, r12b
0x14000bfbe  jz      short loc_14000C006
0x14000bfc0  add     rdx, 28h ; '('
0x14000bfc4  mov     [rsp+70h+FileInformationClass], 9; FileInformationClass
0x14000bfcc  xorps   xmm0, xmm0
0x14000bfcf  lea     r9d, [r15+4]; Length
0x14000bfd3  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14000bfd7  mov     r8d, [rcx+18h]
0x14000bfdb  mov     rcx, [rcx+38h]
0x14000bfdf  add     r8, rdx; FileInformation
0x14000bfe2  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14000bfe6  mov     rcx, [rcx+8]; FileHandle
0x14000bfea  call    cs:__imp_ZwQueryInformationFile
0x14000bff1  nop     dword ptr [rax+rax+00h]
0x14000bff6  test    eax, eax
0x14000bff8  jns     loc_14000C8B7
0x14000bffe  sub     esi, r15d
0x14000c001  jmp     loc_14000C8B7
0x14000c006  mov     eax, [rcx+18h]
0x14000c009  mov     r8d, r15d; Size
0x14000c00c  mov     [rax+rdx+28h], r15d
0x14000c011  lea     rdx, [rbp+Src]; Src
0x14000c015  mov     rax, [rdi+10h]
0x14000c019  mov     ecx, [rax+18h]
0x14000c01c  mov     rax, [rbx]
0x14000c01f  add     rax, 2Ch ; ','
0x14000c023  add     rcx, rax; void *
0x14000c026  call    memmove
0x14000c02b  jmp     loc_14000C8B7
0x14000c030  mov     edx, 28h ; '('; NumberOfBytes
0x14000c035  mov     ecx, 200h; PoolType
0x14000c03a  mov     r8d, 72744C46h; Tag
0x14000c040  call    cs:__imp_ExAllocatePoolWithTag
0x14000c047  nop     dword ptr [rax+rax+00h]
0x14000c04c  mov     [rbx], rax
0x14000c04f  test    rax, rax
0x14000c052  jz      loc_14000C86D
0x14000c058  mov     rcx, [rdi+10h]
0x14000c05c  mov     esi, 28h ; '('
0x14000c061  movups  xmm0, xmmword ptr [rcx+18h]
0x14000c065  movups  xmmword ptr [rax], xmm0
0x14000c068  movups  xmm1, xmmword ptr [rcx+28h]
0x14000c06c  movups  xmmword ptr [rax+10h], xmm1
0x14000c070  movsd   xmm0, qword ptr [rcx+38h]
0x14000c075  movsd   qword ptr [rax+20h], xmm0
0x14000c07a  jmp     loc_14000C8B7
0x14000c07f  mov     esi, 48h ; 'H'
0x14000c084  mov     r8d, 72744C46h; Tag
0x14000c08a  mov     edx, esi; NumberOfBytes
0x14000c08c  mov     ecx, 200h; PoolType
0x14000c091  call    cs:__imp_ExAllocatePoolWithTag
0x14000c098  nop     dword ptr [rax+rax+00h]
0x14000c09d  mov     [rbx], rax
0x14000c0a0  test    rax, rax
0x14000c0a3  jz      loc_14000C86D
0x14000c0a9  mov     rcx, [rdi+10h]
0x14000c0ad  movups  xmm0, xmmword ptr [rcx+18h]
0x14000c0b1  movups  xmmword ptr [rax], xmm0
0x14000c0b4  movups  xmm1, xmmword ptr [rcx+28h]
0x14000c0b8  movups  xmmword ptr [rax+10h], xmm1
0x14000c0bc  movups  xmm0, xmmword ptr [rcx+38h]
0x14000c0c0  movups  xmmword ptr [rax+20h], xmm0
0x14000c0c4  mov     rax, [rdi+10h]
0x14000c0c8  mov     rcx, [rax+18h]
0x14000c0cc  mov     rax, [rbx]
0x14000c0cf  movups  xmm0, xmmword ptr [rcx]
0x14000c0d2  movups  xmmword ptr [rax+30h], xmm0
0x14000c0d6  movsd   xmm1, qword ptr [rcx+10h]
0x14000c0db  movsd   qword ptr [rax+40h], xmm1
0x14000c0e0  mov     rax, [rbx]
0x14000c0e3  mov     qword ptr [rax], 30h ; '0'
0x14000c0ea  jmp     loc_14000C8B7
0x14000c0ef  sub     r8d, 0Bh
0x14000c0f3  jz      loc_14000C44B
0x14000c0f9  sub     r8d, 1
0x14000c0fd  jz      loc_14000C345
0x14000c103  sub     r8d, 1
0x14000c107  jz      loc_14000C2E5
0x14000c10d  sub     r8d, 1
0x14000c111  jz      loc_14000C2FC
0x14000c117  sub     r8d, 1
0x14000c11b  jz      loc_14000C2FC
0x14000c121  sub     r8d, 2
0x14000c125  jz      short loc_14000C173
0x14000c127  cmp     r8d, 3
0x14000c12b  jnz     loc_14000C560
0x14000c131  mov     esi, 20h ; ' '
0x14000c136  mov     r8d, 72744C46h; Tag
0x14000c13c  mov     edx, esi; NumberOfBytes
0x14000c13e  mov     ecx, 200h; PoolType
0x14000c143  call    cs:__imp_ExAllocatePoolWithTag
0x14000c14a  nop     dword ptr [rax+rax+00h]
0x14000c14f  mov     [rbx], rax
0x14000c152  test    rax, rax
0x14000c155  jz      loc_14000C86D
0x14000c15b  mov     rcx, [rdi+10h]
0x14000c15f  movups  xmm0, xmmword ptr [rcx+18h]
0x14000c163  movups  xmmword ptr [rax], xmm0
0x14000c166  movups  xmm1, xmmword ptr [rcx+28h]
0x14000c16a  movups  xmmword ptr [rax+10h], xmm1
0x14000c16e  jmp     loc_14000C8B7
0x14000c173  mov     edx, 30h ; '0'; NumberOfBytes
0x14000c178  mov     ecx, 200h; PoolType
0x14000c17d  mov     r8d, 72744C46h; Tag
0x14000c183  call    cs:__imp_ExAllocatePoolWithTag
0x14000c18a  nop     dword ptr [rax+rax+00h]
0x14000c18f  mov     [rbx], rax
0x14000c192  test    rax, rax
0x14000c195  jz      loc_14000C86D
0x14000c19b  mov     r8, [rdi+10h]
0x14000c19f  mov     esi, 30h ; '0'
0x14000c1a4  movzx   edx, byte ptr [r8+5]
0x14000c1a9  sub     edx, 1
0x14000c1ac  jz      loc_14000C2A8
0x14000c1b2  sub     edx, 1
0x14000c1b5  jz      loc_14000C245
0x14000c1bb  sub     edx, 1
0x14000c1be  jz      short loc_14000C1FC
0x14000c1c0  cmp     edx, 1
0x14000c1c3  jnz     loc_14000C8B7
  ... truncated ...
```
