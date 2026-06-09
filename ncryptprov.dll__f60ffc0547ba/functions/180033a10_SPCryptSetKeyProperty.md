# SPCryptSetKeyProperty

- ea: `0x180033a10`
- end: `0x180034b9b`
- name: `SPCryptSetKeyProperty`
- size: `4491`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int *, size_t Size, unsigned int)`
- caller_count: `2`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b460`
- `0x18004ae24`

## callees

- `0x180004400`
- `0x180004428`
- `0x18000af80`
- `0x18000afd0`
- `0x18000c050`
- `0x18000ceb0`
- `0x18000d3d0`
- `0x18000def0`
- `0x1800140b4`
- `0x180014160`
- `0x180014dd0`
- `0x1800155f4`
- `0x180017330`
- `0x180017a80`
- `0x180019f20`
- `0x18001cdbc`
- `0x180029004`
- `0x180033a10`
- `0x180035318`
- `0x18003568c`
- `0x1800398b0`
- `0x180050eb8`
- `0x18005100c`
- `0x18005c514`
- `0x1800622e0`
- `0x180063010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180033b3d`
- `ntdll!RtlAcquireResourceExclusive` at `0x180033b3d`
- `ntdll!RtlReleaseResource` at `0x180034b67`
- `ntdll!RtlReleaseResource` at `0x180034b7b`
- `ntdll!RtlReleaseResource` at `0x180034b67`
- `ntdll!RtlReleaseResource` at `0x180034b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034050`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034050`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180034003`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180034003`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180033fc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180033fc7`

## string_xrefs

- `0x180033a4e`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180033a90`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180034025`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800344de`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18003485b`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800348dd`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180034ab4`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180034b4d`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180033adf`: `Security Descr`
- `0x180033f9a`: `Security Descr`
- `0x180034645`: `Key Access Policy`

## pseudocode

```c
__int64 __fastcall SPCryptSetKeyProperty(__int64 a1, __int64 a2, __int64 a3, int *a4, size_t Size, unsigned int a6)
{
  unsigned int v7; // r13d
  unsigned int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  __int64 v15; // rbx
  int v16; // eax
  unsigned int v17; // r15d
  size_t v18; // r14
  __int64 v19; // r9
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // ecx
  int v24; // edx
  int updated; // eax
  int v26; // r14d
  __int64 v27; // rcx
  signed int LastError; // eax
  DWORD v29; // eax
  void *v30; // rcx
  int v31; // ecx
  _BYTE *v32; // rax
  void *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  void *v38; // rax
  __int64 v39; // rcx
  _DWORD *v40; // r14
  unsigned int v41; // eax
  __int64 v42; // r9
  unsigned int v43; // ebx
  int v44; // eax
  _BYTE *v45; // rax
  __int64 v46; // rcx
  unsigned int v47; // eax
  __int64 v48; // rdx
  PSECURITY_DESCRIPTOR *v49; // rdx
  PSECURITY_DESCRIPTOR *v50; // r8
  unsigned int v51; // eax
  __int64 v52; // r9
  __int64 v53; // rcx
  __int64 v54; // r8
  _QWORD *v55; // r9
  unsigned int v56; // r14d
  unsigned int v57; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-28h] BYREF
  __int64 v60; // [rsp+48h] [rbp-20h] BYREF
  __int64 v61; // [rsp+50h] [rbp-18h]
  ULONG SecurityDescriptorSize; // [rsp+C0h] [rbp+58h] BYREF

  v7 = 0;
  v60 = 0;
  SecurityDescriptor = 0;
  v61 = KspValidateAndLockProvider(a1, 0);
  if ( v61 )
  {
    v11 = KspValidateKeyHandle(a2);
    if ( !v11 )
    {
      v10 = -2146893786;
      v12 = 2991;
      v13 = 2148073510LL;
LABEL_5:
      DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v12);
LABEL_328:
      RtlReleaseResource((PRTL_RESOURCE)(v61 + 64));
      return v10;
    }
    if ( !a3 )
    {
      v12 = 2998;
LABEL_8:
      v10 = -2146893785;
      v13 = 2148073511LL;
      goto LABEL_5;
    }
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(a3 + 2 * v14) );
    v15 = 64;
    if ( v14 > 0x40 )
    {
      v12 = 3005;
      goto LABEL_8;
    }
    v16 = wcscmp_0((const wchar_t *)a3, L"Security Descr");
    v17 = a6;
    if ( v16 )
    {
      if ( (a6 & 0x3FFFFFBF) != 0 )
      {
        v12 = 3042;
        goto LABEL_16;
      }
    }
    else
    {
      v17 = a6 & 0xFFFFFFBF;
      if ( (a6 & 0xFFFFFFBF) == 0 )
      {
        v12 = 3017;
LABEL_16:
        v10 = -2146893815;
        v13 = 2148073481LL;
        goto LABEL_5;
      }
      if ( (a6 & 0x7FFFFFA0) != 0 )
      {
        v12 = 3031;
        goto LABEL_16;
      }
    }
    SecurityDescriptorSize = 0;
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(v11 + 304), 1u);
    if ( (v17 & 0x40000000) != 0 )
    {
      if ( !a4 || (LODWORD(v18) = Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3067;
LABEL_325:
        v20 = 2148073511LL;
        v10 = -2146893785;
        goto LABEL_326;
      }
      goto LABEL_273;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Export Policy") )
    {
      if ( !a4 || (LODWORD(v18) = Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3083;
        goto LABEL_325;
      }
      if ( (_DWORD)Size != 4 )
      {
        v19 = 3090;
LABEL_30:
        v10 = -2146893819;
        v20 = 2148073477LL;
LABEL_326:
        DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v19);
        goto LABEL_327;
      }
      if ( *(_QWORD *)(v11 + 224) )
      {
        v19 = 3098;
        goto LABEL_33;
      }
      v21 = *a4;
      if ( (*a4 & 0xFFFFFFE0) != 0 )
      {
        v19 = 3112;
LABEL_36:
        v10 = -2146893783;
        v20 = 2148073513LL;
        goto LABEL_326;
      }
      if ( !*(_DWORD *)(v11 + 144) )
      {
        v22 = *(_QWORD *)(v11 + 416);
        if ( v22 && (*(_BYTE *)(v22 + 4) & 4) != 0 && v21 )
        {
          v19 = 3178;
          goto LABEL_325;
        }
        *(_DWORD *)(v11 + 36) = v21;
        v23 = v21;
        if ( (v21 & 4) != 0 )
        {
          v23 = v21 | 1;
          *(_DWORD *)(v11 + 36) = v21 | 1;
        }
        if ( (v21 & 8) != 0 )
          *(_DWORD *)(v11 + 36) = v23 | 2;
        v7 = 3;
        v17 = 0x80000000;
LABEL_273:
        v47 = LookupExistingKeyProperty(v11, a3, &SecurityDescriptor);
        v10 = v47;
        if ( v47 )
        {
          DebugTraceError(v47, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 4290);
          goto LABEL_292;
        }
        if ( SecurityDescriptor )
        {
          v49 = (PSECURITY_DESCRIPTOR *)*((_QWORD *)SecurityDescriptor + 19);
          if ( v49[1] != (char *)SecurityDescriptor + 152 )
            goto LABEL_284;
          v50 = (PSECURITY_DESCRIPTOR *)*((_QWORD *)SecurityDescriptor + 20);
          if ( *v50 != (char *)SecurityDescriptor + 152 )
            goto LABEL_284;
          *v50 = v49;
          v49[1] = v50;
          MSCryptFree();
        }
        v51 = CreateNewProperty(v7, a3, a4, (unsigned int)v18, v17, &v60);
        v10 = v51;
        if ( v51 )
        {
          v52 = 4314;
          goto LABEL_281;
        }
        v54 = v60;
        v48 = v11 + 288;
        *(_DWORD *)(v60 + 148) = 1;
        v55 = *(_QWORD **)(v11 + 296);
        if ( *v55 == v11 + 288 )
        {
          *(_QWORD *)(v54 + 152) = v48;
          *(_QWORD *)(v54 + 160) = v55;
          *v55 = v54 + 152;
          *(_QWORD *)(v11 + 296) = v54 + 152;
          if ( !*(_DWORD *)(v54 + 144) )
            goto LABEL_291;
          if ( (*(_BYTE *)(v11 + 428) & 0x20) != 0 )
          {
            v10 = -2146893808;
            v52 = 4332;
            v53 = 2148073488LL;
            goto LABEL_282;
          }
          if ( !*(_QWORD *)(v11 + 224) || (v51 = WriteKeyToStore(v11, 0, 0), (v10 = v51) == 0) )
          {
LABEL_291:
            v10 = 0;
LABEL_292:
            if ( SecurityDescriptorSize )
              goto LABEL_293;
LABEL_327:
            RtlReleaseResource((PRTL_RESOURCE)(v11 + 304));
            goto LABEL_328;
          }
          v52 = 4348;
LABEL_281:
          v53 = v51;
LABEL_282:
          DebugTraceError(v53, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v52);
          goto LABEL_292;
        }
LABEL_284:
        __fastfail(3u);
      }
      if ( v21 )
      {
        v19 = 3164;
        goto LABEL_36;
      }
LABEL_39:
      v10 = 0;
      goto LABEL_327;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Key Usage") )
    {
      if ( !a4 || (LODWORD(v18) = Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3209;
        goto LABEL_325;
      }
      if ( (_DWORD)Size != 4 )
      {
        v19 = 3216;
        goto LABEL_30;
      }
      v24 = *a4;
      if ( *a4 != 0xFFFFFF
        && (v24 & 0x10) != 0
        && (((*(_DWORD *)(*(_QWORD *)(v11 + 64) + 8LL) - 3) & 0xFFFFFFFD) != 0 || (v24 & 0xFFFBFF4F) != 0) )
      {
        v19 = 3231;
        goto LABEL_325;
      }
      if ( !*(_QWORD *)(v11 + 224) )
      {
        v7 = 5;
        *(_DWORD *)(v11 + 40) = v24;
        v17 = 0x80000000;
        goto LABEL_273;
      }
      v19 = 3242;
LABEL_33:
      v10 = -2146893813;
      v20 = 2148073483LL;
      goto LABEL_326;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"HWND Handle") )
    {
      if ( !a4 || (LODWORD(v18) = Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3257;
        goto LABEL_325;
      }
      if ( (unsigned int)Size > 8 )
      {
        v19 = 3266;
        goto LABEL_30;
      }
      v7 = 17;
      memcpy_0((void *)(v11 + 400), a4, (unsigned int)Size);
      *(_DWORD *)(v11 + 408) = v18;
      goto LABEL_146;
    }
    if ( *(_WORD *)a3 == 73 && *(_WORD *)(a3 + 2) == 86 && !*(_WORD *)(a3 + 4) )
    {
      if ( !a4 || (unsigned int)Size > 0x7FFFFFFF )
      {
        v19 = 3286;
        goto LABEL_325;
      }
      if ( *(_QWORD *)(v11 + 112) || (updated = KspCheckStrongKeyAndUnprotect(v11, v17), v10 = updated, updated >= 0) )
      {
        updated = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD, _DWORD))(*(_QWORD *)(v11 + 168)
                                                                                            + 24LL))(
                    *(_QWORD *)(v11 + 112),
                    L"IV",
                    a4,
                    (unsigned int)Size,
                    0);
        v10 = updated;
        if ( updated >= 0 )
          goto LABEL_327;
        v19 = 3311;
      }
      else
      {
        v19 = 3297;
      }
      goto LABEL_80;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Chaining Mode") )
    {
      if ( !a4 || (unsigned int)Size > 0x7FFFFFFF )
      {
        v19 = 3323;
        goto LABEL_325;
      }
      if ( *(_QWORD *)(v11 + 112) || (updated = KspCheckStrongKeyAndUnprotect(v11, v17), v10 = updated, updated >= 0) )
      {
        updated = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD, _DWORD))(*(_QWORD *)(v11 + 168)
                                                                                            + 24LL))(
                    *(_QWORD *)(v11 + 112),
                    L"ChainingMode",
                    a4,
                    (unsigned int)Size,
                    0);
        v10 = updated;
        if ( updated >= 0 )
          goto LABEL_327;
        v19 = 3348;
      }
      else
      {
        v19 = 3334;
      }
      goto LABEL_80;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Length") )
    {
      if ( !*(_DWORD *)(*(_QWORD *)(v11 + 64) + 96LL) )
      {
        v19 = 3361;
        goto LABEL_36;
      }
      if ( !a4 || (unsigned int)Size > 0x7FFFFFFF )
      {
        v19 = 3369;
        goto LABEL_325;
      }
      if ( (_DWORD)Size != 4 )
      {
        v19 = 3378;
        goto LABEL_30;
      }
      if ( *(_QWORD *)(v11 + 224) )
      {
        v19 = 3386;
        goto LABEL_33;
      }
      v26 = *(_DWORD *)(v11 + 28);
      *(_DWORD *)(v11 + 28) = *a4;
      updated = KspValidateKeyLength(v11);
      v10 = updated;
      if ( updated )
      {
        v19 = 3403;
      }
      else
      {
        if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) - 196618) <= 1 )
        {
          if ( *(_QWORD *)(v11 + 552) && v26 == *(_DWORD *)(v11 + 28) )
            goto LABEL_327;
          v19 = 3419;
          goto LABEL_325;
        }
        v27 = *(_QWORD *)(v11 + 112);
        if ( !v27 )
          goto LABEL_327;
        updated = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, _DWORD))(*(_QWORD *)(v11 + 168)
                                                                                              + 24LL))(
                    v27,
                    L"KeyLength",
                    a4,
                    4,
                    0);
        v10 = updated;
        if ( updated >= 0 )
          goto LABEL_327;
        v19 = 3441;
      }
      goto LABEL_80;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Security Descr") )
    {
      SecurityDescriptor = 0;
      SecurityDescriptorSize = 0;
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              (LPCWSTR)a4,
              1u,
              &SecurityDescriptor,
              &SecurityDescriptorSize) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v19 = 3465;
        goto LABEL_117;
      }
      if ( !IsValidSecurityDescriptor(SecurityDescriptor) )
      {
        v29 = GetLastError();
        DebugTraceError(v29, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 3473);
        v10 = -2146893819;
        goto LABEL_327;
      }
      v30 = *(void **)(v11 + 272);
      if ( v30 )
        LocalFree(v30);
      *(_DWORD *)(v11 + 280) = SecurityDescriptorSize;
      *(_QWORD *)(v11 + 272) = SecurityDescriptor;
      *(_DWORD *)(v11 + 268) = v17 & 0x7FFFFFFF;
      if ( !*(_QWORD *)(v11 + 224) )
        goto LABEL_39;
      updated = WriteKeyToStore(v11, 1, 0);
      v10 = updated;
      if ( !updated )
        goto LABEL_39;
      v19 = 3501;
LABEL_80:
      v20 = (unsigned int)updated;
      goto LABEL_326;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"MSSP/UI Internal Flags") )
    {
      if ( !a4 || (LODWORD(v18) = Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3517;
        goto LABEL_325;
      }
      if ( (_DWORD)Size != 4 )
      {
        v19 = 3525;
        goto LABEL_325;
      }
      v31 = *a4;
      if ( (*a4 & 0xFFFFFFC0) != 0 )
      {
        v19 = 3541;
        goto LABEL_325;
      }
      if ( !*(_QWORD *)(v11 + 224) )
      {
        v17 |= 0x80000000;
        v7 = 18;
        *a4 &= 1u;
        *(_DWORD *)(v11 + 428) = v31;
        goto LABEL_273;
      }
      *(_DWORD *)(v11 + 428) = v31 ^ (*(_DWORD *)(v11 + 428) ^ v31) & 1;
      goto LABEL_39;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"MSSP/UI Password Hash") )
    {
      if ( !a4 || (v18 = (unsigned int)Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3578;
        goto LABEL_325;
      }
      if ( (unsigned int)Size > 0x40 )
      {
        v19 = 3587;
        goto LABEL_30;
      }
      if ( (*(_BYTE *)(v11 + 428) & 2) == 0 )
      {
        v19 = 3595;
        goto LABEL_36;
      }
      v7 = 19;
      v32 = (_BYTE *)(v11 + 432);
      do
      {
        *v32++ = 0;
        --v15;
      }
      while ( v15 );
      memcpy_0((void *)(v11 + 432), a4, v18);
LABEL_146:
      v17 &= ~0x80000000;
      goto LABEL_273;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Use Context") )
    {
      if ( !a4 || (v18 = (unsigned int)Size, (unsigned int)Size > 0x7FFFFFFD) )
      {
        v19 = 3615;
        goto LABEL_325;
      }
      if ( *(_QWORD *)(v11 + 504) )
        MSCryptFree();
      v33 = (void *)SafeAllocaAllocateFromHeap(v18 + 2);
      *(_QWORD *)(v11 + 504) = v33;
      if ( v33 )
      {
        v7 = 21;
        v17 &= ~0x80000000;
        memcpy_0(v33, a4, v18);
        *(_WORD *)(*(_QWORD *)(v11 + 504) + 2 * (v18 >> 1)) = 0;
        goto LABEL_273;
      }
      v19 = 3633;
      goto LABEL_155;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"UI Policy") )
    {
      if ( !a4 || (v18 = (unsigned int)Size, (unsigned int)Size > 0x7FFFFFFF) )
      {
        v19 = 3648;
        goto LABEL_325;
      }
      if ( (unsigned int)Size < 0x14 )
      {
        v19 = 3662;
        goto LABEL_30;
      }
      v34 = (unsigned int)a4[4];
      v35 = (unsigned int)a4[3];
      if ( (unsigned int)Size != v35 + v34 + (unsigned int)a4[2] + 20LL )
      {
        v19 = 3673;
        goto LABEL_30;
      }
      v36 = a4[1];
      if ( (v36 & 0xFFFFFFF8) != 0 )
      {
        v19 = 3685;
        goto LABEL_325;
      }
      if ( (v36 & 4) != 0
        && ((v36 & 0xFFFFFFFB) != 0 || (*(_BYTE *)(v11 + 36) & 0x1F) != 0 || *(_DWORD *)(v11 + 32) == 1) )
      {
        v19 = 3704;
        goto LABEL_325;
      }
      if ( (unsigned int)v35 > 0x102 || (unsigned int)v34 > 0x2002 )
      {
        v19 = 3715;
        goto LABEL_325;
      }
      if ( *(_QWORD *)(v11 + 224) )
      {
        v37 = *(_QWORD *)(v11 + 416);
        if ( v37 )
        {
          if ( v36 != *(_DWORD *)(v37 + 4) )
          {
            v19 = 3730;
            goto LABEL_33;
          }
        }
        else if ( v36 )
        {
          v19 = 3739;
          goto LABEL_33;
        }
      }
      else if ( (*(_BYTE *)(v11 + 428) & 1) != 0 )
      {
        v19 = 3752;
        goto LABEL_36;
      }
      if ( *(_QWORD *)(v11 + 416) )
        MSCryptFree();
      v38 = (void *)SafeAllocaAllocateFromHeap(v18);
      *(_QWORD *)(v11 + 416) = v38;
      if ( v38 )
      {
        *(_DWORD *)(v11 + 424) = v18;
        v7 = 12;
        v17 = 0x80000000;
        memcpy_0(v38, a4, v18);
        goto LABEL_273;
      }
      v19 = 3769;
LABEL_155:
      v10 = -2146893810;
      v20 = 2148073486LL;
      goto LABEL_326;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"SmartCardPin") )
    {
      if ( (unsigned int)Size > 0x7FFFFFFF )
      {
        v19 = 3790;
        goto LABEL_325;
      }
      v39 = *(_QWORD *)(v11 + 416);
      if ( !*(_DWORD *)(v11 + 44) )
      {
        if ( !v39 || (*(_BYTE *)(v39 + 4) & 2) == 0 || (v40 = (_DWORD *)(v11 + 428), (*(_BYTE *)(v11 + 428) & 1) != 0) )
        {
          v19 = 3806;
          goto LABEL_36;
        }
        if ( !a4 || (_DWORD)Size == 2 && !*(_WORD *)a4 )
        {
          v19 = 3816;
          goto LABEL_325;
        }
LABEL_208:
        updated = ComputeAndSetPasswordHashOnTheKey(v11, a4, (unsigned int)Size);
        v10 = updated;
        if ( updated )
        {
          v19 = 3925;
          goto LABEL_80;
        }
        if ( !*(_DWORD *)(v11 + 44) )
        {
          *v40 |= 1u;
          SecurityDescriptorSize = 1;
          updated = SetUIKeyProperties(
                      v11,
                      (unsigned int)L"MSSP/UI Internal Flags",
                      18,
                      (unsigned int)&SecurityDescriptorSize,
                      4);
          v10 = updated;
          if ( !updated )
          {
            *v40 |= 0x10u;
            goto LABEL_327;
          }
          v19 = 3990;
          goto LABEL_80;
        }
        if ( *(_QWORD *)(v11 + 240) )
        {
          v41 = UnprotectPrivateKey(v11);
          v42 = 3938;
        }
        else
        {
          if ( !*(_QWORD *)(v11 + 256) )
            goto LABEL_217;
          v41 = UnprotectLegacyPrivateKey(v11);
          v42 = 3943;
        }
        v43 = v41;
        DebugTraceError(v41, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v42);
        if ( v43 )
        {
          v10 = -2146893773;
          goto LABEL_327;
        }
LABEL_217:
        v10 = SKCacheAdd(v11);
        if ( !v10 )
          *(_DWORD *)(v11 + 428) |= 0x18u;
        goto LABEL_327;
      }
      if ( !v39 || (v40 = (_DWORD *)(v11 + 428), (*(_BYTE *)(v11 + 428) & 1) == 0) )
      {
        if ( a4 && ((_DWORD)Size != 2 || *(_WORD *)a4) )
        {
          v19 = 3845;
          goto LABEL_325;
        }
        goto LABEL_39;
      }
      if ( a4 && ((_DWORD)Size != 2 || *(_WORD *)a4) )
      {
        if ( *(_QWORD *)(v11 + 112) )
        {
          v19 = 3911;
          goto LABEL_33;
        }
        goto LABEL_208;
      }
      if ( !*(_QWORD *)(v11 + 112) )
      {
        v19 = 3864;
        goto LABEL_33;
      }
      v44 = (*(__int64 (**)(void))(*(_QWORD *)(v11 + 168) + 136LL))();
      v10 = v44 | 0x10000000;
      if ( v44 >= 0 )
      {
        *(_QWORD *)(v11 + 112) = 0;
        v45 = (_BYTE *)(v11 + 432);
        v46 = 64;
        do
        {
          *v45++ = 0;
          --v46;
        }
        while ( v46 );
        updated = SKCacheRemove(v11);
        v10 = updated;
        if ( updated >= 0 )
          goto LABEL_327;
        if ( updated == -2146893807 )
          goto LABEL_39;
        v19 = 3893;
        goto LABEL_80;
      }
      v19 = 3872;
LABEL_117:
      v20 = v10;
      goto LABEL_326;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"PCP_CHANGEPASSWORD") )
    {
      updated = ChangePasswordOnTheKey(v11, a4, (unsigned int)Size);
      v10 = updated;
      if ( !updated )
        goto LABEL_327;
      v19 = 4014;
      goto LABEL_80;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"Key Access Policy") )
    {
      updated = SetKeyAccessPolicy(v11, a4, (unsigned int)Size);
      v10 = updated;
      if ( !updated )
        goto LABEL_327;
      v19 = 4026;
      goto LABEL_80;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"KDFKeySecret") )
    {
      if ( !a4 || (unsigned int)Size > 0x7FFFFFFF )
      {
        v19 = 4044;
        goto LABEL_325;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v11 + 64) + 8LL) == 7 || *(_DWORD *)(v11 + 44) != 1 )
      {
        if ( *(_DWORD *)(v11 + 144) )
        {
          v19 = 4061;
          goto LABEL_36;
        }
        updated = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int *, _DWORD, _DWORD))(*(_QWORD *)(v11 + 168) + 64LL))(
                    *(_QWORD *)(v11 + 152),
                    v11 + 112,
                    0,
                    0,
                    a4,
                    Size,
                    0);
        v10 = updated;
        if ( updated >= 0 )
          goto LABEL_39;
        v19 = 4076;
        goto LABEL_80;
      }
      v10 = 50;
      v19 = 4052;
      goto LABEL_117;
    }
    if ( !wcscmp_0((const wchar_t *)a3, L"SmartCardKeyCertificate") )
    {
      LODWORD(v18) = Size;
      updated = SetCertificateProperty(v11, a4, (unsigned int)Size);
      v10 = updated;
      if ( updated )
      {
        v19 = 4095;
        goto LABEL_80;
      }
      if ( *(_QWORD *)(v11 + 224) )
      {
        updated = WriteKeyToStore(v11, 0, 0);
        v10 = updated;
        if ( updated )
        {
          v19 = 4111;
          goto LABEL_80;
        }
      }
      v7 = 24;
LABEL_272:
      v17 |= 0x80000000;
      goto LABEL_273;
    }
    if ( wcscmp_0((const wchar_t *)a3, L"ECCCurveName") )
    {
      if ( !wcscmp_0((const wchar_t *)a3, L"ParameterSetName") )
      {
        if ( !a4
          || (v56 = Size, (unsigned int)Size > 0x7FFFFFFF)
          || (Size & 1) != 0
          || (unsigned int)Size <= 2
          || *((_WORD *)a4 + ((unsigned __int64)(unsigned int)Size >> 1) - 1) )
        {
          v19 = 4186;
          goto LABEL_325;
        }
        if ( *(_QWORD *)(v11 + 112) || (updated = KspCheckStrongKeyAndUnprotect(v11, v17), v10 = updated, updated >= 0) )
        {
          updated = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, int *, _QWORD, _DWORD))(*(_QWORD *)(v11 + 168)
                                                                                              + 24LL))(
                      *(_QWORD *)(v11 + 112),
                      L"ParameterSetName",
                      a4,
                      v56,
                      0);
          v10 = updated;
          if ( updated >= 0 )
            goto LABEL_327;
          v19 = 4211;
        }
        else
        {
          v19 = 4197;
        }
      }
      else
      {
        if ( wcscmp_0((const wchar_t *)a3, L"KEMSharedSecretLength")
          && wcscmp_0((const wchar_t *)a3, L"KEMCiphertextLength") )
        {
          if ( !a4 || (unsigned int)Size > 0x7FFFFFFF )
          {
            v19 = 4262;
            goto LABEL_325;
          }
          v57 = SetPrivateKeyProperty(v11, a3, a4);
          v10 = v57;
          if ( v57 )
          {
            DebugTraceError(v57, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 4274);
LABEL_315:
            KspCryptAuditKeyMigrationOperation(0, v48, v11, 2465, v10);
            goto LABEL_327;
          }
LABEL_293:
          if ( !v10 )
          {
            KspCryptAuditKeyMigrationOperation(1, v48, v11, 2465, 0);
            goto LABEL_327;
          }
          goto LABEL_315;
        }
        if ( !a4 || (unsigned int)Size > 4 )
        {
          v19 = 4224;
          goto LABEL_325;
        }
        if ( *(_QWORD *)(v11 + 112) || (updated = KspCheckStrongKeyAndUnprotect(v11, v17), v10 = updated, updated >= 0) )
        {
          updated = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, _QWORD, _DWORD))(*(_QWORD *)(v11 + 168) + 24LL))(
                      *(_QWORD *)(v11 + 112),
                      a3,
                      a4,
                      (unsigned int)Size,
                      0);
          v10 = updated;
          if ( updated >= 0 )
            goto LABEL_327;
          v19 = 4249;
        }
        else
        {
          v19 = 4235;
        }
      }
      goto LABEL_80;
    }
    if ( !a4 || (LODWORD(v18) = Size, (unsigned int)Size > 0x7FFFFFFF) )
    {
      v19 = 4122;
      goto LABEL_325;
    }
    if ( *(_DWORD *)(v11 + 44) == 1 )
    {
      v19 = 4129;
    }
    else
    {
      if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v11 + 64) + 32LL) - 196618) <= 1 )
      {
        if ( *(_QWORD *)(v11 + 552) )
        {
          v19 = 4158;
          goto LABEL_36;
        }
        updated = UpdateECCHandleWithCurve(v11, a3, a4, (unsigned int)Size);
        v10 = updated;
        if ( updated )
        {
          v19 = 4169;
          goto LABEL_80;
        }
        SecurityDescriptorSize = 1;
        v7 = 25;
        goto LABEL_272;
      }
      v19 = 4140;
    }
    v10 = -2146893786;
    v20 = 2148073510LL;
    goto LABEL_326;
  }
  v10 = -2146893786;
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 2982);
  return v10;
}

```

## disassembly

```asm
0x180033a10  push    rbp
0x180033a12  push    rbx
0x180033a13  push    rsi
0x180033a14  push    rdi
0x180033a15  push    r12
0x180033a17  push    r13
0x180033a19  push    r14
0x180033a1b  push    r15
0x180033a1d  mov     rbp, rsp
0x180033a20  sub     rsp, 68h
0x180033a24  mov     rbx, rdx
0x180033a27  xor     r13d, r13d
0x180033a2a  xor     edx, edx
0x180033a2c  mov     [rbp+var_20], r13
0x180033a30  mov     [rbp+SecurityDescriptor], r13
0x180033a34  mov     rsi, r9
0x180033a37  mov     r12, r8
0x180033a3a  call    KspValidateAndLockProvider
0x180033a3f  mov     [rbp+var_18], rax
0x180033a43  test    rax, rax
0x180033a46  jnz     short loc_180033A70
0x180033a48  mov     r9d, 0BA6h
0x180033a4e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180033a55  lea     rdx, aStatus; "Status"
0x180033a5c  mov     ecx, 80090026h
0x180033a61  mov     ebx, 80090026h
0x180033a66  call    DebugTraceError
0x180033a6b  jmp     loc_180034B87
0x180033a70  mov     rcx, rbx
0x180033a73  call    KspValidateKeyHandle
0x180033a78  mov     rdi, rax
0x180033a7b  test    rax, rax
0x180033a7e  jnz     short loc_180033AA8
0x180033a80  mov     ebx, 80090026h
0x180033a85  mov     r9d, 0BAFh
0x180033a8b  mov     ecx, 80090026h
0x180033a90  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180033a97  lea     rdx, aStatus; "Status"
0x180033a9e  call    DebugTraceError
0x180033aa3  jmp     loc_180034B73
0x180033aa8  test    r12, r12
0x180033aab  jnz     short loc_180033ABF
0x180033aad  mov     r9d, 0BB6h
0x180033ab3  mov     ebx, 80090027h
0x180033ab8  mov     ecx, 80090027h
0x180033abd  jmp     short loc_180033A90
0x180033abf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033ac3  inc     rax
0x180033ac6  cmp     [r12+rax*2], r13w
0x180033acb  jnz     short loc_180033AC3
0x180033acd  mov     ebx, 40h ; '@'
0x180033ad2  cmp     rax, rbx
0x180033ad5  jbe     short loc_180033ADF
0x180033ad7  mov     r9d, 0BBDh
0x180033add  jmp     short loc_180033AB3
0x180033adf  lea     rdx, aSecurityDescr; "Security Descr"
0x180033ae6  mov     rcx, r12; String1
0x180033ae9  call    wcscmp_0
0x180033aee  mov     r15d, [rbp+arg_28]
0x180033af2  test    eax, eax
0x180033af4  jnz     short loc_180033B1F
0x180033af6  and     r15d, 0FFFFFFBFh
0x180033afa  jnz     short loc_180033B0E
0x180033afc  mov     r9d, 0BC9h
0x180033b02  mov     ebx, 80090009h
0x180033b07  mov     ecx, 80090009h
0x180033b0c  jmp     short loc_180033A90
0x180033b0e  test    r15d, 7FFFFFE0h
0x180033b15  jz      short loc_180033B30
0x180033b17  mov     r9d, 0BD7h
0x180033b1d  jmp     short loc_180033B02
0x180033b1f  test    r15d, 3FFFFFBFh
0x180033b26  jz      short loc_180033B30
0x180033b28  mov     r9d, 0BE2h
0x180033b2e  jmp     short loc_180033B02
0x180033b30  lea     rcx, [rdi+130h]; Resource
0x180033b37  mov     [rbp+SecurityDescriptorSize], r13d
0x180033b3b  mov     dl, 1; Wait
0x180033b3d  call    cs:__imp_RtlAcquireResourceExclusive
0x180033b44  nop     dword ptr [rax+rax+00h]
0x180033b49  bt      r15d, 1Eh
0x180033b4e  jnb     short loc_180033B71
0x180033b50  test    rsi, rsi
0x180033b53  jz      short loc_180033B66
0x180033b55  mov     r14d, dword ptr [rbp+Size]
0x180033b59  cmp     r14d, 7FFFFFFFh
0x180033b60  jbe     loc_180034840
0x180033b66  mov     r9d, 0BFBh
0x180033b6c  jmp     loc_180034B43
0x180033b71  lea     rdx, aExportPolicy; "Export Policy"
0x180033b78  mov     rcx, r12; String1
0x180033b7b  call    wcscmp_0
0x180033b80  test    eax, eax
0x180033b82  jnz     loc_180033C6C
0x180033b88  test    rsi, rsi
0x180033b8b  jz      loc_180033C61
0x180033b91  mov     r14d, dword ptr [rbp+Size]
0x180033b95  cmp     r14d, 7FFFFFFFh
0x180033b9c  ja      loc_180033C61
0x180033ba2  cmp     r14d, 4
0x180033ba6  jz      short loc_180033BBD
0x180033ba8  mov     r9d, 0C12h
0x180033bae  mov     ebx, 80090005h
0x180033bb3  mov     ecx, 80090005h
0x180033bb8  jmp     loc_180034B4D
0x180033bbd  cmp     [rdi+0E0h], r13
0x180033bc4  jz      short loc_180033BDB
0x180033bc6  mov     r9d, 0C1Ah
0x180033bcc  mov     ebx, 8009000Bh
0x180033bd1  mov     ecx, 8009000Bh
0x180033bd6  jmp     loc_180034B4D
0x180033bdb  mov     eax, [rsi]
0x180033bdd  test    eax, 0FFFFFFE0h
0x180033be2  jz      short loc_180033BF9
0x180033be4  mov     r9d, 0C28h
0x180033bea  mov     ebx, 80090029h
0x180033bef  mov     ecx, 80090029h
0x180033bf4  jmp     loc_180034B4D
0x180033bf9  cmp     [rdi+90h], r13d
0x180033c00  jz      short loc_180033C16
0x180033c02  test    eax, eax
0x180033c04  jnz     short loc_180033C0E
0x180033c06  mov     ebx, r13d
0x180033c09  jmp     loc_180034B60
0x180033c0e  mov     r9d, 0C5Ch
0x180033c14  jmp     short loc_180033BEA
0x180033c16  mov     rcx, [rdi+1A0h]
0x180033c1d  test    rcx, rcx
0x180033c20  jz      short loc_180033C37
0x180033c22  test    byte ptr [rcx+4], 4
0x180033c26  jz      short loc_180033C37
0x180033c28  test    eax, eax
0x180033c2a  jz      short loc_180033C37
0x180033c2c  mov     r9d, 0C6Ah
0x180033c32  jmp     loc_180034B43
0x180033c37  mov     [rdi+24h], eax
0x180033c3a  mov     ecx, eax
0x180033c3c  test    al, 4
0x180033c3e  jz      short loc_180033C46
0x180033c40  or      ecx, 1
0x180033c43  mov     [rdi+24h], ecx
0x180033c46  test    al, 8
0x180033c48  jz      short loc_180033C50
0x180033c4a  or      ecx, 2
0x180033c4d  mov     [rdi+24h], ecx
0x180033c50  mov     r13d, 3
0x180033c56  mov     r15d, 80000000h
0x180033c5c  jmp     loc_180034840
0x180033c61  mov     r9d, 0C0Bh
0x180033c67  jmp     loc_180034B43
0x180033c6c  lea     rdx, aKeyUsage; "Key Usage"
0x180033c73  mov     rcx, r12; String1
0x180033c76  call    wcscmp_0
0x180033c7b  test    eax, eax
0x180033c7d  jnz     loc_180033D0D
0x180033c83  test    rsi, rsi
0x180033c86  jz      short loc_180033D02
0x180033c88  mov     r14d, dword ptr [rbp+Size]
0x180033c8c  cmp     r14d, 7FFFFFFFh
0x180033c93  ja      short loc_180033D02
0x180033c95  cmp     r14d, 4
0x180033c99  jz      short loc_180033CA6
0x180033c9b  mov     r9d, 0C90h
0x180033ca1  jmp     loc_180033BAE
0x180033ca6  mov     edx, [rsi]
0x180033ca8  cmp     edx, 0FFFFFFh
0x180033cae  jz      short loc_180033CDA
0x180033cb0  test    dl, 10h
0x180033cb3  jz      short loc_180033CDA
0x180033cb5  mov     rax, [rdi+40h]
0x180033cb9  mov     ecx, [rax+8]
0x180033cbc  sub     ecx, 3
0x180033cbf  test    ecx, 0FFFFFFFDh
0x180033cc5  jnz     short loc_180033CCF
0x180033cc7  test    edx, 0FFFBFF4Fh
0x180033ccd  jz      short loc_180033CDA
0x180033ccf  mov     r9d, 0C9Fh
0x180033cd5  jmp     loc_180034B43
0x180033cda  cmp     [rdi+0E0h], r13
0x180033ce1  jz      short loc_180033CEE
0x180033ce3  mov     r9d, 0CAAh
0x180033ce9  jmp     loc_180033BCC
0x180033cee  mov     r13d, 5
0x180033cf4  mov     [rdi+28h], edx
0x180033cf7  mov     r15d, 80000000h
0x180033cfd  jmp     loc_180034840
0x180033d02  mov     r9d, 0C89h
0x180033d08  jmp     loc_180034B43
0x180033d0d  lea     rdx, aHwndHandle; "HWND Handle"
0x180033d14  mov     rcx, r12; String1
0x180033d17  call    wcscmp_0
0x180033d1c  test    eax, eax
0x180033d1e  jnz     short loc_180033D72
0x180033d20  test    rsi, rsi
0x180033d23  jz      short loc_180033D67
0x180033d25  mov     r14d, dword ptr [rbp+Size]
0x180033d29  cmp     r14d, 7FFFFFFFh
0x180033d30  ja      short loc_180033D67
0x180033d32  cmp     r14d, 8
0x180033d36  jbe     short loc_180033D43
0x180033d38  mov     r9d, 0CC2h
0x180033d3e  jmp     loc_180033BAE
0x180033d43  mov     r8, r14; Size
0x180033d46  lea     rcx, [rdi+190h]; void *
0x180033d4d  mov     rdx, rsi; Src
0x180033d50  mov     r13d, 11h
0x180033d56  call    memcpy_0
0x180033d5b  mov     [rdi+198h], r14d
0x180033d62  jmp     loc_1800341AF
0x180033d67  mov     r9d, 0CB9h
0x180033d6d  jmp     loc_180034B43
0x180033d72  cmp     word ptr [r12], 49h ; 'I'
0x180033d78  jnz     loc_180033E05
0x180033d7e  cmp     word ptr [r12+2], 56h ; 'V'
0x180033d85  jnz     short loc_180033E05
0x180033d87  cmp     [r12+4], r13w
0x180033d8d  jnz     short loc_180033E05
0x180033d8f  test    rsi, rsi
0x180033d92  jz      short loc_180033DFA
0x180033d94  cmp     dword ptr [rbp+Size], 7FFFFFFFh
0x180033d9b  ja      short loc_180033DFA
0x180033d9d  cmp     [rdi+70h], r13
0x180033da1  jnz     short loc_180033DC1
0x180033da3  mov     edx, r15d
0x180033da6  mov     rcx, rdi
0x180033da9  call    KspCheckStrongKeyAndUnprotect
0x180033dae  mov     ebx, eax
0x180033db0  test    eax, eax
0x180033db2  jns     short loc_180033DC1
0x180033db4  mov     r9d, 0CE1h
0x180033dba  mov     ecx, eax
0x180033dbc  jmp     loc_180034B4D
0x180033dc1  mov     rax, [rdi+0A8h]
0x180033dc8  lea     rdx, aIv; "IV"
0x180033dcf  mov     r9d, dword ptr [rbp+Size]
0x180033dd3  mov     r8, rsi
0x180033dd6  mov     rcx, [rdi+70h]
0x180033dda  mov     dword ptr [rsp+68h+var_48], r13d
0x180033ddf  mov     rax, [rax+18h]
0x180033de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033de8  mov     ebx, eax
0x180033dea  test    eax, eax
0x180033dec  jns     loc_180034B60
0x180033df2  mov     r9d, 0CEFh
0x180033df8  jmp     short loc_180033DBA
0x180033dfa  mov     r9d, 0CD6h
0x180033e00  jmp     loc_180034B43
0x180033e05  lea     rdx, aChainingMode; "Chaining Mode"
0x180033e0c  mov     rcx, r12; String1
0x180033e0f  call    wcscmp_0
0x180033e14  test    eax, eax
0x180033e16  jnz     short loc_180033E8F
0x180033e18  test    rsi, rsi
0x180033e1b  jz      short loc_180033E84
0x180033e1d  cmp     dword ptr [rbp+Size], 7FFFFFFFh
0x180033e24  ja      short loc_180033E84
0x180033e26  cmp     [rdi+70h], r13
0x180033e2a  jnz     short loc_180033E48
0x180033e2c  mov     edx, r15d
0x180033e2f  mov     rcx, rdi
0x180033e32  call    KspCheckStrongKeyAndUnprotect
0x180033e37  mov     ebx, eax
0x180033e39  test    eax, eax
0x180033e3b  jns     short loc_180033E48
0x180033e3d  mov     r9d, 0D06h
0x180033e43  jmp     loc_180033DBA
0x180033e48  mov     rax, [rdi+0A8h]
0x180033e4f  lea     rdx, aChainingmode; "ChainingMode"
0x180033e56  mov     r9d, dword ptr [rbp+Size]
0x180033e5a  mov     r8, rsi
0x180033e5d  mov     rcx, [rdi+70h]
0x180033e61  mov     dword ptr [rsp+68h+var_48], r13d
0x180033e66  mov     rax, [rax+18h]
0x180033e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e6f  mov     ebx, eax
0x180033e71  test    eax, eax
0x180033e73  jns     loc_180034B60
0x180033e79  mov     r9d, 0D14h
0x180033e7f  jmp     loc_180033DBA
0x180033e84  mov     r9d, 0CFBh
0x180033e8a  jmp     loc_180034B43
0x180033e8f  lea     rdx, aLength; "Length"
0x180033e96  mov     rcx, r12; String1
0x180033e99  call    wcscmp_0
0x180033e9e  test    eax, eax
0x180033ea0  jnz     loc_180033F9A
0x180033ea6  mov     rax, [rdi+40h]
0x180033eaa  cmp     [rax+60h], r13d
0x180033eae  jnz     short loc_180033EBB
0x180033eb0  mov     r9d, 0D21h
0x180033eb6  jmp     loc_180033BEA
0x180033ebb  test    rsi, rsi
0x180033ebe  jz      loc_180033F8F
0x180033ec4  cmp     dword ptr [rbp+Size], 7FFFFFFFh
0x180033ecb  ja      loc_180033F8F
0x180033ed1  cmp     dword ptr [rbp+Size], 4
0x180033ed5  jz      short loc_180033EE2
0x180033ed7  mov     r9d, 0D32h
0x180033edd  jmp     loc_180033BAE
0x180033ee2  cmp     [rdi+0E0h], r13
  ... truncated ...
```
