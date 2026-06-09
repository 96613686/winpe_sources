# DsRolerDcAsReplica

- ea: `0x180005e40`
- end: `0x180006594`
- name: `DsRolerDcAsReplica`
- size: `1876`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003994`
- `0x180003cb8`
- `0x180003d84`
- `0x180003fb0`
- `0x180004ef8`
- `0x180005028`
- `0x180005e40`
- `0x18000eb40`
- `0x18000f71c`
- `0x18000ffa8`
- `0x1800150cc`
- `0x180015ff0`
- `0x1800161a8`
- `0x18001f6c4`
- `0x180020b08`
- `0x180020dbc`
- `0x18002c02a`
- `0x18002c050`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000633d`
- `msvcrt!wcsstr` at `0x18000633d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006555`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006555`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006576`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006052`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800060de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005fbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006052`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800060de`

## string_xrefs

- `0x180006239`: `	SystemVolumeRootPath  %ws\n`
- `0x180006223`: `	DsDatabasePath  %ws, DsLogPath  %ws\n`
- `0x1800062de`: `Validate supplied paths\n`
- `0x1800063f2`: `Start the worker task\n`
- `0x180005f99`: `Can't reinstall a DC when performing Stage 2 promotion\n`
- `0x180006152`: `A domain controller cannot be re-promoted. Use Repair operation\n`
- `0x1800061a8`: `Promotion request for read-only replica domain controller\n`
- `0x180006281`: `	Read only DC ServerAdminGroup  %ws\n`
- `0x18000629a`: `	Read only DC RevealOnDemand  %ws\n`
- `0x1800062c1`: `	Read only DC NeverReveal  %ws\n`
- `0x180006336`: `\Active Directory`

## pseudocode

```c
__int64 __fastcall DsRolerDcAsReplica(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  int v13; // eax
  _BYTE *v15; // r13
  unsigned int MachineType; // ebx
  _OWORD *v17; // rax
  _OWORD *v18; // rcx
  __int128 v19; // xmm1
  _OWORD *v20; // r14
  _BYTE *v21; // r12
  __int64 v22; // rcx
  _OWORD *v23; // rax
  __int64 v24; // r8
  __int128 v25; // xmm1
  __int64 v26; // rax
  __int64 v27; // rdx
  const char *v28; // rdx
  const wchar_t *v29; // rbx
  const wchar_t *v30; // r8
  const wchar_t *v31; // r8
  __int64 i; // rbx
  __int64 v33; // rbx
  wchar_t *v34; // rax
  __int64 v35; // r15
  __int64 v36; // rdx
  __int64 v37; // rdi
  __int64 v38; // rcx
  _BYTE *v39; // rax
  _BYTE *v40; // rax
  _BYTE *v41; // rax
  __int64 v42; // rcx
  signed __int32 v43; // [rsp+B0h] [rbp-80h] BYREF
  _QWORD *v44; // [rsp+B8h] [rbp-78h]
  __int64 v45; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v46; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v47; // [rsp+D0h] [rbp-60h]
  _QWORD v48[2]; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v49[2]; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v50[2]; // [rsp+F8h] [rbp-38h] BYREF
  __int128 v51; // [rsp+108h] [rbp-28h] BYREF

  v44 = a3;
  v47 = a1;
  v43 = 0;
  v3 = a3;
  v45 = 0;
  v51 = 0;
  v46 = 0;
  *(_OWORD *)v49 = 0;
  *(_OWORD *)v50 = 0;
  DsRolepDisableServiceStop();
  if ( !*(_QWORD *)a2 )
    return 87;
  v5 = *(_QWORD *)(a2 + 24);
  if ( !v5 )
    return 87;
  v6 = *(_QWORD *)(a2 + 32);
  if ( !v6 )
    return 87;
  v7 = *(_QWORD *)(a2 + 48);
  if ( !v7 )
    return 87;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v5 + 2 * v9) );
  if ( v9 > 0x104 )
    return 87;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(v6 + 2 * v10) );
  if ( v10 > 0x104 )
    return 87;
  v11 = *(_QWORD *)(a2 + 40);
  if ( v11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v11 + 2 * v12) );
    if ( v12 > 0x104 )
      return 87;
  }
  do
    ++v8;
  while ( *(_WORD *)(v7 + 2 * v8) );
  if ( v8 > 0x104 )
    return 87;
  v13 = *(_DWORD *)(a2 + 88);
  if ( (v13 & 0x40000) != 0 )
  {
    if ( !*(_QWORD *)(a2 + 16) )
    {
      DsRolepLogPrintRoutine(4, "RODC promotion, site name is set to NULL\n");
      return 87;
    }
    if ( !*(_QWORD *)(a2 + 112) && *(_DWORD *)(a2 + 104) )
    {
      DsRolepLogPrintRoutine(4, "RODC promotion, Reveal on Demanad group is set to NULL but count != 0\n");
      return 87;
    }
    if ( !*(_QWORD *)(a2 + 128) && *(_DWORD *)(a2 + 120) )
    {
      DsRolepLogPrintRoutine(4, "RODC promotion, Never Reveal group is set to NULL but count != 0\n");
      return 87;
    }
  }
  if ( (v13 & 0x80004) == 0x80004 )
  {
    DsRolepLogPrintRoutine(4, "Can't reinstall a DC when performing Stage 2 promotion\n");
    return 87;
  }
  v15 = 0;
  if ( !*(_QWORD *)(a2 + 72) )
  {
LABEL_35:
    v20 = 0;
    v21 = 0;
    v22 = 40;
    if ( *(_QWORD *)(a2 + 80) )
    {
      v21 = LocalAlloc(0x40u, 0x20Cu);
      if ( !v21 )
      {
LABEL_37:
        MachineType = 14;
        goto LABEL_92;
      }
      v23 = *(_OWORD **)(a2 + 80);
      v11 = (__int64)v21;
      v24 = 4;
      do
      {
        *(_OWORD *)v11 = *v23;
        *(_OWORD *)(v11 + 16) = v23[1];
        *(_OWORD *)(v11 + 32) = v23[2];
        *(_OWORD *)(v11 + 48) = v23[3];
        *(_OWORD *)(v11 + 64) = v23[4];
        *(_OWORD *)(v11 + 80) = v23[5];
        *(_OWORD *)(v11 + 96) = v23[6];
        v25 = v23[7];
        v23 += 8;
        *(_OWORD *)(v11 + 112) = v25;
        v11 += 128;
        --v24;
      }
      while ( v24 );
      v22 = 40;
      *(_OWORD *)(v11 - 4) = *(_OWORD *)((char *)v23 - 4);
    }
    if ( *(_QWORD *)(a2 + 56) )
    {
      v20 = LocalAlloc(0x40u, 0x28u);
      if ( !v20 )
        goto LABEL_37;
      v26 = *(_QWORD *)(a2 + 56);
      *v20 = *(_OWORD *)v26;
      v20[1] = *(_OWORD *)(v26 + 16);
      *((_QWORD *)v20 + 4) = *(_QWORD *)(v26 + 32);
    }
    v48[0] = v15;
    v48[1] = v21;
    MachineType = DsRolepInitializeOperationHandle(v22, v11);
    if ( MachineType )
      goto LABEL_92;
    MachineType = DsRolepGetMachineType(&v43);
    if ( MachineType )
      goto LABEL_92;
    if ( v43 )
    {
      if ( v43 != 2 || (*(_DWORD *)(a2 + 88) & 0x200000) != 0 )
      {
        MachineType = DsRolepCheckClientAccess(DsRolepPromoteSD, v27, 1);
        if ( MachineType )
          goto LABEL_92;
        DsRolepInitializeLogHelper(1);
        MachineType = DsRolepIsValidProductSuite(0, 1, *(_QWORD *)a2);
        if ( MachineType )
          goto LABEL_92;
        v28 = "Promotion request for read-only replica domain controller\n";
        if ( (*(_DWORD *)(a2 + 88) & 0x40000) == 0 )
          v28 = "Promotion request for replica domain controller\n";
        DsRolepLogPrintRoutine(4, v28);
        if ( (*(_DWORD *)(a2 + 88) & 0x80000) != 0 )
          DsRolepLogPrintRoutine(4, "Promotion request for second-stage promotion only\n");
        DsRolepLogPrintRoutine(4, "DnsDomainName  %ws\n", *(_QWORD *)a2);
        v29 = L"(NULL)";
        v30 = L"(NULL)";
        if ( *(_QWORD *)(a2 + 8) )
          v30 = *(const wchar_t **)(a2 + 8);
        DsRolepLogPrintRoutine(4, "\tReplicaPartner  %ws\n", v30);
        v31 = L"(NULL)";
        if ( *(_QWORD *)(a2 + 16) )
          v31 = *(const wchar_t **)(a2 + 16);
        DsRolepLogPrintRoutine(4, "\tSiteName  %ws\n", v31);
        DsRolepLogPrintRoutine(4, "\tDsDatabasePath  %ws, DsLogPath  %ws\n", *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
        DsRolepLogPrintRoutine(4, "\tSystemVolumeRootPath  %ws\n", *(_QWORD *)(a2 + 48));
        if ( *(_QWORD *)(a2 + 64) )
          v29 = *(const wchar_t **)(a2 + 64);
        DsRolepLogPrintRoutine(4, "\tAccount %ws\n", v29);
        DsRolepLogPrintRoutine(4, "\tOptions  %lu\n", *(_DWORD *)(a2 + 88));
        if ( (*(_DWORD *)(a2 + 88) & 0x40000) != 0 )
        {
          DsRolepLogPrintRoutine(4, "\tRead only DC ServerAdminGroup  %ws\n", *(_QWORD *)(a2 + 96));
          for ( i = 0; (unsigned int)i < *(_DWORD *)(a2 + 104); i = (unsigned int)(i + 1) )
            DsRolepLogPrintRoutine(
              4,
              "\tRead only DC RevealOnDemand  %ws\n",
              *(_QWORD *)(*(_QWORD *)(a2 + 112) + 8 * i));
          v33 = 0;
          if ( *(_DWORD *)(a2 + 120) )
          {
            do
            {
              DsRolepLogPrintRoutine(
                4,
                "\tRead only DC NeverReveal  %ws\n",
                *(_QWORD *)(*(_QWORD *)(a2 + 128) + 8 * v33));
              v33 = (unsigned int)(v33 + 1);
            }
            while ( (unsigned int)v33 < *(_DWORD *)(a2 + 120) );
            v3 = v44;
          }
        }
        DsRolepLogPrintRoutine(4, "Validate supplied paths\n");
        MachineType = DsRolepCheckFilePaths(
                        *(STRSAFE_PCNZWCH *)(a2 + 24),
                        *(STRSAFE_PCNZWCH *)(a2 + 32),
                        *(STRSAFE_PCNZWCH *)(a2 + 48));
        if ( MachineType )
          goto LABEL_92;
        if ( *(_QWORD *)(a2 + 40) )
        {
          v43 = _InterlockedCompareExchange(&DsRolepCurrentIfmOperationHandle, 1, 0);
          if ( v43 || dword_18004DBD4 == MachineType )
            MachineType = 6;
          v34 = wcsstr((const wchar_t *)String2, L"\\Active Directory");
          if ( !v34
            || (v35 = ((char *)v34 - (_BYTE *)String2) >> 1,
                wcsncmp_0(*(const wchar_t **)(a2 + 40), (const wchar_t *)String2, (unsigned int)v35))
            || wcsncmp_0(*(const wchar_t **)(a2 + 40), (const wchar_t *)qword_18004DBE0, (unsigned int)v35) )
          {
            MachineType = 6;
          }
          if ( v43 )
          {
            if ( MachineType )
              goto LABEL_92;
          }
          else if ( MachineType )
          {
            DsRolepCurrentIfmOperationHandle = 0;
            goto LABEL_92;
          }
          v3 = v44;
        }
        MachineType = DsRolepDecryptPasswordsWithKey(v47, (unsigned int)v48, 2, (unsigned int)v49, (__int64)&v51);
        if ( MachineType )
          goto LABEL_92;
        if ( v20 )
        {
          MachineType = DsRolepDecryptHash(&v51, v20, &v46);
          if ( MachineType )
            goto LABEL_92;
        }
        DsRolepLogPrintRoutine(4, "Start the worker task\n");
        MachineType = DsRolepBuildPromoteArgumentBlock(
                        *(STRSAFE_LPCWSTR *)a2,
                        0,
                        *(STRSAFE_LPCWSTR *)(a2 + 16),
                        *(STRSAFE_LPCWSTR *)(a2 + 24),
                        *(STRSAFE_LPCWSTR *)(a2 + 32),
                        (unsigned __int64)&String2 & -(__int64)(*(_QWORD *)(a2 + 40) != 0),
                        *(STRSAFE_LPCWSTR *)(a2 + 48),
                        v46,
                        0,
                        *(STRSAFE_LPCWSTR *)(a2 + 8),
                        *(STRSAFE_LPCWSTR *)(a2 + 64),
                        (__int64)v49,
                        0,
                        (__int64)v50,
                        *(_DWORD *)(a2 + 88),
                        *(_DWORD *)(a2 + 136),
                        *(_QWORD *)(a2 + 144),
                        a2 + 96,
                        0,
                        0,
                        (__int64)&v45);
        DsRolepFreePasswords(v49, 2);
        if ( !MachineType )
        {
          MachineType = DsRolepSpinWorkerThread(1, v45);
          if ( !MachineType )
          {
            *v3 = &DsRolepCurrentOperationHandle;
            goto LABEL_92;
          }
          LOBYTE(v36) = 1;
          DsRolepFreeArgumentBlock(&v45, v36);
        }
        DsRolepResetOperationHandle(0);
LABEL_92:
        v37 = 524;
        if ( v15 )
        {
          v38 = 524;
          v39 = v15;
          do
          {
            *v39++ = 0;
            --v38;
          }
          while ( v38 );
          LocalFree(v15);
        }
        if ( v21 )
        {
          v40 = v21;
          do
          {
            *v40++ = 0;
            --v37;
          }
          while ( v37 );
          LocalFree(v21);
        }
        if ( v20 )
        {
          v41 = v20;
          v42 = 40;
          do
          {
            *v41++ = 0;
            --v42;
          }
          while ( v42 );
          LocalFree(v20);
        }
        goto LABEL_104;
      }
      DsRolepLogPrintRoutine(4, "A domain controller cannot be re-promoted. Use Repair operation\n");
    }
    else
    {
      DsRolepLogPrintRoutine(4, "A workstation cannot be promoted as a domain controller\n");
    }
    MachineType = 1352;
    goto LABEL_92;
  }
  v15 = LocalAlloc(0x40u, 0x20Cu);
  if ( v15 )
  {
    v17 = *(_OWORD **)(a2 + 72);
    v18 = v15;
    v11 = 4;
    do
    {
      *v18 = *v17;
      v18[1] = v17[1];
      v18[2] = v17[2];
      v18[3] = v17[3];
      v18[4] = v17[4];
      v18[5] = v17[5];
      v18[6] = v17[6];
      v19 = v17[7];
      v17 += 8;
      v18[7] = v19;
      v18 += 8;
      --v11;
    }
    while ( v11 );
    *(_OWORD *)((char *)v18 - 4) = *(_OWORD *)((char *)v17 - 4);
    goto LABEL_35;
  }
  MachineType = 14;
LABEL_104:
  DsRolepLogPrintRoutine(4, "Request for promotion returning %lu\n", MachineType);
  return MachineType;
}

```

## disassembly

```asm
0x180005e40  mov     [rsp-8+arg_18], rbx
0x180005e45  push    rbp
0x180005e46  push    rsi
0x180005e47  push    rdi
0x180005e48  push    r12
0x180005e4a  push    r13
0x180005e4c  push    r14
0x180005e4e  push    r15
0x180005e50  lea     rbp, [rsp+10h]
0x180005e55  sub     rsp, 120h
0x180005e5c  mov     rax, cs:__security_cookie
0x180005e63  xor     rax, rsp
0x180005e66  mov     [rbp+20h+var_38], rax
0x180005e6a  xorps   xmm0, xmm0
0x180005e6d  mov     [rbp+20h+var_98], r8
0x180005e71  xor     ebx, ebx
0x180005e73  mov     [rbp+20h+var_80], rcx
0x180005e77  mov     [rbp+20h+var_A0], ebx
0x180005e7a  mov     r15, r8
0x180005e7d  mov     [rbp+20h+var_90], rbx
0x180005e81  mov     rdi, rdx
0x180005e84  movups  [rbp+20h+var_48], xmm0
0x180005e88  mov     [rbp+20h+var_88], rbx
0x180005e8c  movups  xmmword ptr [rbp+20h+var_68], xmm0
0x180005e90  movups  xmmword ptr [rbp+20h+var_58], xmm0
0x180005e94  call    DsRolepDisableServiceStop
0x180005e99  cmp     [rdi], rbx
0x180005e9c  jz      loc_180005F37
0x180005ea2  mov     rdx, [rdi+18h]
0x180005ea6  test    rdx, rdx
0x180005ea9  jz      loc_180005F37
0x180005eaf  mov     r8, [rdi+20h]
0x180005eb3  test    r8, r8
0x180005eb6  jz      short loc_180005F37
0x180005eb8  mov     r9, [rdi+30h]
0x180005ebc  test    r9, r9
0x180005ebf  jz      short loc_180005F37
0x180005ec1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ec5  mov     rcx, rax
0x180005ec8  inc     rcx
0x180005ecb  cmp     [rdx+rcx*2], bx
0x180005ecf  jnz     short loc_180005EC8
0x180005ed1  mov     r10d, 104h
0x180005ed7  cmp     rcx, r10
0x180005eda  ja      short loc_180005F37
0x180005edc  mov     rcx, rax
0x180005edf  inc     rcx
0x180005ee2  cmp     [r8+rcx*2], bx
0x180005ee7  jnz     short loc_180005EDF
0x180005ee9  cmp     rcx, r10
0x180005eec  ja      short loc_180005F37
0x180005eee  mov     rdx, [rdi+28h]
0x180005ef2  test    rdx, rdx
0x180005ef5  jz      short loc_180005F08
0x180005ef7  mov     rcx, rax
0x180005efa  inc     rcx
0x180005efd  cmp     [rdx+rcx*2], bx
0x180005f01  jnz     short loc_180005EFA
0x180005f03  cmp     rcx, r10
0x180005f06  ja      short loc_180005F37
0x180005f08  inc     rax
0x180005f0b  cmp     [r9+rax*2], bx
0x180005f10  jnz     short loc_180005F08
0x180005f12  cmp     rax, r10
0x180005f15  ja      short loc_180005F37
0x180005f17  mov     eax, [rdi+58h]
0x180005f1a  bt      eax, 12h
0x180005f1e  jnb     short loc_180005F8E
0x180005f20  cmp     [rdi+10h], rbx
0x180005f24  jnz     short loc_180005F63
0x180005f26  lea     rdx, aRodcPromotionS; "RODC promotion, site name is set to NUL"...
0x180005f2d  mov     ecx, 4
0x180005f32  call    DsRolepLogPrintRoutine
0x180005f37  mov     eax, 57h ; 'W'
0x180005f3c  mov     rcx, [rbp+20h+var_38]
0x180005f40  xor     rcx, rsp; StackCookie
0x180005f43  call    __security_check_cookie
0x180005f48  mov     rbx, [rsp+150h+arg_18]
0x180005f50  add     rsp, 120h
0x180005f57  pop     r15
0x180005f59  pop     r14
0x180005f5b  pop     r13
0x180005f5d  pop     r12
0x180005f5f  pop     rdi
0x180005f60  pop     rsi
0x180005f61  pop     rbp
0x180005f62  retn
0x180005f63  cmp     [rdi+70h], rbx
0x180005f67  jnz     short loc_180005F77
0x180005f69  cmp     [rdi+68h], ebx
0x180005f6c  jz      short loc_180005F77
0x180005f6e  lea     rdx, aRodcPromotionR; "RODC promotion, Reveal on Demanad group"...
0x180005f75  jmp     short loc_180005F2D
0x180005f77  cmp     [rdi+80h], rbx
0x180005f7e  jnz     short loc_180005F8E
0x180005f80  cmp     [rdi+78h], ebx
0x180005f83  jz      short loc_180005F8E
0x180005f85  lea     rdx, aRodcPromotionN; "RODC promotion, Never Reveal group is s"...
0x180005f8c  jmp     short loc_180005F2D
0x180005f8e  mov     ecx, 80004h
0x180005f93  and     eax, ecx
0x180005f95  cmp     eax, ecx
0x180005f97  jnz     short loc_180005FA2
0x180005f99  lea     rdx, aCanTReinstallA; "Can't reinstall a DC when performing St"...
0x180005fa0  jmp     short loc_180005F2D
0x180005fa2  mov     esi, 4
0x180005fa7  mov     r13, rbx
0x180005faa  mov     eax, 20Ch
0x180005faf  lea     r14d, [rsi+7Ch]
0x180005fb3  cmp     [rdi+48h], rbx
0x180005fb7  jz      short loc_180006035
0x180005fb9  mov     edx, eax; uBytes
0x180005fbb  lea     ecx, [rsi+3Ch]; uFlags
0x180005fbe  call    cs:__imp_LocalAlloc
0x180005fc4  mov     r13, rax
0x180005fc7  test    rax, rax
0x180005fca  jnz     short loc_180005FD4
0x180005fcc  lea     ebx, [rsi+0Ah]
0x180005fcf  jmp     loc_18000657C
0x180005fd4  mov     rax, [rdi+48h]
0x180005fd8  mov     rcx, r13
0x180005fdb  mov     rdx, rsi
0x180005fde  movups  xmm0, xmmword ptr [rax]
0x180005fe1  movups  xmmword ptr [rcx], xmm0
0x180005fe4  movups  xmm1, xmmword ptr [rax+10h]
0x180005fe8  movups  xmmword ptr [rcx+10h], xmm1
0x180005fec  movups  xmm0, xmmword ptr [rax+20h]
0x180005ff0  movups  xmmword ptr [rcx+20h], xmm0
0x180005ff4  movups  xmm1, xmmword ptr [rax+30h]
0x180005ff8  movups  xmmword ptr [rcx+30h], xmm1
0x180005ffc  movups  xmm0, xmmword ptr [rax+40h]
0x180006000  movups  xmmword ptr [rcx+40h], xmm0
0x180006004  movups  xmm1, xmmword ptr [rax+50h]
0x180006008  movups  xmmword ptr [rcx+50h], xmm1
0x18000600c  movups  xmm0, xmmword ptr [rax+60h]
0x180006010  movups  xmmword ptr [rcx+60h], xmm0
0x180006014  movups  xmm1, xmmword ptr [rax+70h]
0x180006018  add     rax, r14
0x18000601b  movups  xmmword ptr [rcx+70h], xmm1
0x18000601f  add     rcx, r14
0x180006022  sub     rdx, 1
0x180006026  jnz     short loc_180005FDE
0x180006028  movups  xmm0, xmmword ptr [rax-4]
0x18000602c  mov     eax, 20Ch
0x180006031  movups  xmmword ptr [rcx-4], xmm0
0x180006035  mov     r14, rbx
0x180006038  mov     r12, rbx
0x18000603b  mov     ecx, 28h ; '('
0x180006040  cmp     [rdi+50h], rbx
0x180006044  jz      loc_1800060D0
0x18000604a  mov     rdx, rax; uBytes
0x18000604d  mov     ecx, 40h ; '@'; uFlags
0x180006052  call    cs:__imp_LocalAlloc
0x180006058  mov     r12, rax
0x18000605b  test    rax, rax
0x18000605e  jnz     short loc_18000606A
0x180006060  mov     ebx, 0Eh
0x180006065  jmp     loc_180006516
0x18000606a  mov     rax, [rdi+50h]
0x18000606e  mov     rdx, r12
0x180006071  mov     r8, rsi
0x180006074  mov     r9d, 80h
0x18000607a  movups  xmm0, xmmword ptr [rax]
0x18000607d  movups  xmmword ptr [rdx], xmm0
0x180006080  movups  xmm1, xmmword ptr [rax+10h]
0x180006084  movups  xmmword ptr [rdx+10h], xmm1
0x180006088  movups  xmm0, xmmword ptr [rax+20h]
0x18000608c  movups  xmmword ptr [rdx+20h], xmm0
0x180006090  movups  xmm1, xmmword ptr [rax+30h]
0x180006094  movups  xmmword ptr [rdx+30h], xmm1
0x180006098  movups  xmm0, xmmword ptr [rax+40h]
0x18000609c  movups  xmmword ptr [rdx+40h], xmm0
0x1800060a0  movups  xmm1, xmmword ptr [rax+50h]
0x1800060a4  movups  xmmword ptr [rdx+50h], xmm1
0x1800060a8  movups  xmm0, xmmword ptr [rax+60h]
0x1800060ac  movups  xmmword ptr [rdx+60h], xmm0
0x1800060b0  movups  xmm1, xmmword ptr [rax+70h]
0x1800060b4  add     rax, r9
0x1800060b7  movups  xmmword ptr [rdx+70h], xmm1
0x1800060bb  add     rdx, r9
0x1800060be  sub     r8, 1
0x1800060c2  jnz     short loc_18000607A
0x1800060c4  movups  xmm0, xmmword ptr [rax-4]
0x1800060c8  lea     ecx, [r8+28h]
0x1800060cc  movups  xmmword ptr [rdx-4], xmm0
0x1800060d0  cmp     [rdi+38h], rbx
0x1800060d4  jz      short loc_18000610F
0x1800060d6  mov     rdx, rcx; uBytes
0x1800060d9  mov     ecx, 40h ; '@'; uFlags
0x1800060de  call    cs:__imp_LocalAlloc
0x1800060e4  mov     r14, rax
0x1800060e7  test    rax, rax
0x1800060ea  jz      loc_180006060
0x1800060f0  mov     rax, [rdi+38h]
0x1800060f4  movups  xmm0, xmmword ptr [rax]
0x1800060f7  movups  xmmword ptr [r14], xmm0
0x1800060fb  movups  xmm1, xmmword ptr [rax+10h]
0x1800060ff  movups  xmmword ptr [r14+10h], xmm1
0x180006104  movsd   xmm0, qword ptr [rax+20h]
0x180006109  movsd   qword ptr [r14+20h], xmm0
0x18000610f  mov     [rbp+20h+var_78], r13
0x180006113  mov     [rbp+20h+var_70], r12
0x180006117  call    DsRolepInitializeOperationHandle
0x18000611c  mov     ebx, eax
0x18000611e  test    eax, eax
0x180006120  jnz     loc_180006516
0x180006126  lea     rcx, [rbp+20h+var_A0]
0x18000612a  call    DsRolepGetMachineType
0x18000612f  mov     ebx, eax
0x180006131  test    eax, eax
0x180006133  jnz     loc_180006516
0x180006139  mov     eax, [rbp+20h+var_A0]
0x18000613c  test    eax, eax
0x18000613e  jz      loc_180006503
0x180006144  cmp     eax, 2
0x180006147  jnz     short loc_18000615E
0x180006149  test    dword ptr [rdi+58h], 200000h
0x180006150  jnz     short loc_18000615E
0x180006152  lea     rdx, aADomainControl; "A domain controller cannot be re-promot"...
0x180006159  jmp     loc_18000650A
0x18000615e  mov     r8d, 1
0x180006164  lea     rcx, DsRolepPromoteSD; pSecurityDescriptor
0x18000616b  call    DsRolepCheckClientAccess
0x180006170  mov     ebx, eax
0x180006172  test    eax, eax
0x180006174  jnz     loc_180006516
0x18000617a  lea     ebx, [rax+1]
0x18000617d  mov     ecx, ebx
0x18000617f  call    DsRolepInitializeLogHelper
0x180006184  mov     r8, [rdi]
0x180006187  mov     edx, ebx
0x180006189  xor     ecx, ecx
0x18000618b  call    DsRolepIsValidProductSuite
0x180006190  mov     ebx, eax
0x180006192  test    eax, eax
0x180006194  jnz     loc_180006516
0x18000619a  test    dword ptr [rdi+58h], 40000h
0x1800061a1  lea     rax, aPromotionReque_2; "Promotion request for replica domain co"...
0x1800061a8  lea     rdx, aPromotionReque_1; "Promotion request for read-only replica"...
0x1800061af  mov     ecx, esi
0x1800061b1  cmovz   rdx, rax
0x1800061b5  call    DsRolepLogPrintRoutine
0x1800061ba  test    dword ptr [rdi+58h], 80000h
0x1800061c1  jz      short loc_1800061D1
0x1800061c3  lea     rdx, aPromotionReque; "Promotion request for second-stage prom"...
0x1800061ca  mov     ecx, esi
0x1800061cc  call    DsRolepLogPrintRoutine
0x1800061d1  mov     r8, [rdi]
0x1800061d4  lea     rdx, aDnsdomainnameW; "DnsDomainName  %ws\n"
0x1800061db  mov     ecx, esi
0x1800061dd  call    DsRolepLogPrintRoutine
0x1800061e2  cmp     qword ptr [rdi+8], 0
0x1800061e7  lea     rbx, aNull; "(NULL)"
0x1800061ee  mov     r8, rbx
0x1800061f1  lea     rdx, aReplicapartner; "\tReplicaPartner  %ws\n"
0x1800061f8  cmovnz  r8, [rdi+8]
0x1800061fd  mov     ecx, esi
0x1800061ff  call    DsRolepLogPrintRoutine
0x180006204  cmp     qword ptr [rdi+10h], 0
0x180006209  lea     rdx, aSitenameWs; "\tSiteName  %ws\n"
0x180006210  mov     r8, rbx
0x180006213  mov     ecx, esi
0x180006215  cmovnz  r8, [rdi+10h]
0x18000621a  call    DsRolepLogPrintRoutine
0x18000621f  mov     r9, [rdi+20h]
0x180006223  lea     rdx, aDsdatabasepath; "\tDsDatabasePath  %ws, DsLogPath  %ws\n"
0x18000622a  mov     r8, [rdi+18h]
0x18000622e  mov     ecx, esi
0x180006230  call    DsRolepLogPrintRoutine
0x180006235  mov     r8, [rdi+30h]
0x180006239  lea     rdx, aSystemvolumero; "\tSystemVolumeRootPath  %ws\n"
0x180006240  mov     ecx, esi
0x180006242  call    DsRolepLogPrintRoutine
0x180006247  cmp     qword ptr [rdi+40h], 0
0x18000624c  lea     rdx, aAccountWs; "\tAccount %ws\n"
0x180006253  mov     ecx, esi
0x180006255  cmovnz  rbx, [rdi+40h]
0x18000625a  mov     r8, rbx
0x18000625d  call    DsRolepLogPrintRoutine
0x180006262  mov     r8d, [rdi+58h]
0x180006266  lea     rdx, aOptionsLu; "\tOptions  %lu\n"
0x18000626d  mov     ecx, esi
0x18000626f  call    DsRolepLogPrintRoutine
0x180006274  test    dword ptr [rdi+58h], 40000h
0x18000627b  jz      short loc_1800062DE
0x18000627d  mov     r8, [rdi+60h]
0x180006281  lea     rdx, aReadOnlyDcServ; "\tRead only DC ServerAdminGroup  %ws\n"
0x180006288  mov     ecx, esi
0x18000628a  call    DsRolepLogPrintRoutine
0x18000628f  xor     ebx, ebx
0x180006291  cmp     [rdi+68h], ebx
0x180006294  jbe     short loc_1800062B3
0x180006296  mov     r8, [rdi+70h]
0x18000629a  lea     rdx, aReadOnlyDcReve; "\tRead only DC RevealOnDemand  %ws\n"
0x1800062a1  mov     ecx, esi
0x1800062a3  mov     r8, [r8+rbx*8]
0x1800062a7  call    DsRolepLogPrintRoutine
0x1800062ac  inc     ebx
0x1800062ae  cmp     ebx, [rdi+68h]
0x1800062b1  jb      short loc_180006296
  ... truncated ...
```
