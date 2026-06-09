# CFolderAclEngine::_s_GetNonSystemAceList(CAceList *,int,CAceList * *)

- ea: `0x18000dd60`
- end: `0x18000e8a7`
- name: `?_s_GetNonSystemAceList@CFolderAclEngine@@CAJPEAVCAceList@@HPEAPEAV2@@Z`
- size: `2887`
- prototype: `__int64 __fastcall(struct CAceList *, int, struct CAceList **)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bea0`
- `0x18000c6f0`
- `0x18005a6d8`

## callees

- `0x1800098dc`
- `0x18000a5f8`
- `0x18000bc00`
- `0x18000d1f0`
- `0x18000dd60`
- `0x18000edd0`
- `0x18000f4b0`
- `0x18000f7a0`
- `0x18000f7f0`
- `0x180011c80`
- `0x18001bf88`
- `0x1800254e0`
- `0x18002596c`
- `0x1800259bc`
- `0x180025b70`
- `0x180025bd8`
- `0x180025d64`
- `0x18002637c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e503`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e541`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e503`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e541`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000df57`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e037`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000df57`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000e037`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e179`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e34e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e179`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000e34e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e1bb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e390`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e1bb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000e390`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000df1e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000dffd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000df1e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000dffd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000df2e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000e00d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000df2e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000e00d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e18a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e35f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e79c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e81e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e18a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e35f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e79c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e81e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e1a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e6e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e7bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e844`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e1a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e375`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e6e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e7bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000def4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e63e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e77d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000def4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e620`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e63e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e77d`
- `ntdll!RtlMapGenericMask` at `0x18000e203`
- `ntdll!RtlMapGenericMask` at `0x18000e3da`
- `ntdll!RtlMapGenericMask` at `0x18000e203`
- `ntdll!RtlMapGenericMask` at `0x18000e3da`
- `KERNEL32!GetComputerNameW` at `0x18000e684`
- `KERNEL32!GetComputerNameW` at `0x18000e684`
- `SHLWAPI!StrRChrW` at `0x18000dec1`
- `SHLWAPI!StrRChrW` at `0x18000dec1`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000ded8`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000ded8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000deab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e762`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000deab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000e762`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000e0d1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000e0d1`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000e6bc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000e749`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000e6bc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000e749`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFolderAclEngine::_s_GetNonSystemAceList(struct CAceList *a1, int a2, struct CAceList **a3)
{
  struct CAceList *v3; // r13
  __int64 v4; // r14
  CAceList *v5; // rsi
  int Error; // r15d
  CAceList *v7; // rax
  __int64 v8; // rdx
  CAceList *v9; // rbx
  unsigned int v10; // edx
  char *v11; // rdi
  int *v12; // rbx
  int v13; // eax
  void *v14; // r12
  const WCHAR *v15; // rdi
  BOOL v16; // ebx
  PWSTR v17; // rax
  LPWSTR v18; // rcx
  int v19; // eax
  __int64 v20; // rbx
  BOOL v21; // edi
  int v22; // r12d
  int *v23; // rbx
  int v24; // eax
  __int64 v25; // rbx
  void *v26; // rdi
  int v27; // eax
  __int64 v28; // rdi
  BOOL v29; // r12d
  struct CAceList *v30; // rax
  DWORD *v32; // rax
  DWORD *v33; // rbx
  void *v34; // rdi
  SIZE_T LengthSid; // r13
  HLOCAL v36; // rax
  void *v37; // r14
  void *v38; // r14
  unsigned __int16 v39; // di
  unsigned int v40; // eax
  DWORD v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, __int64, DWORD *); // rax
  int v46; // eax
  DWORD *v47; // rax
  DWORD *v48; // rdi
  void *v49; // r12
  HLOCAL v50; // rax
  void *v51; // rbx
  void *v52; // rbx
  unsigned __int16 v53; // r12
  unsigned int v54; // eax
  DWORD v55; // eax
  __int64 v56; // rcx
  int v57; // eax
  __int64 v58; // rbx
  __int64 (__fastcall *v59)(__int64, __int64, DWORD *); // rax
  int v60; // eax
  char v61; // al
  char v62; // al
  HLOCAL v63; // rbx
  unsigned __int64 v64; // rax
  WCHAR *v65; // rdi
  DWORD v66; // ecx
  DWORD v67; // eax
  HLOCAL v68; // rax
  DWORD v69; // ecx
  DWORD v70; // eax
  HLOCAL v71; // rax
  char v72; // [rsp+30h] [rbp-69h]
  char v73; // [rsp+30h] [rbp-69h]
  char v74; // [rsp+31h] [rbp-68h]
  char v75; // [rsp+31h] [rbp-68h]
  unsigned __int16 v76; // [rsp+32h] [rbp-67h]
  unsigned __int16 v77; // [rsp+32h] [rbp-67h]
  unsigned int v79; // [rsp+38h] [rbp-61h]
  DWORD v80; // [rsp+38h] [rbp-61h]
  DWORD v81; // [rsp+3Ch] [rbp-5Dh] BYREF
  char *v82; // [rsp+40h] [rbp-59h]
  void *Src; // [rsp+48h] [rbp-51h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-49h] BYREF
  DWORD nDestinationSidLength[2]; // [rsp+58h] [rbp-41h] BYREF
  enum _SID_NAME_USE v86; // [rsp+60h] [rbp-39h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-35h] BYREF
  DWORD cchReferencedDomainName; // [rsp+68h] [rbp-31h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-29h] BYREF
  struct CAceList *v90; // [rsp+78h] [rbp-21h]
  DWORD nSize; // [rsp+80h] [rbp-19h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+84h] [rbp-15h] BYREF
  CAceList *v93; // [rsp+88h] [rbp-11h]
  struct CAceList **v94; // [rsp+90h] [rbp-9h]
  WCHAR Buffer[16]; // [rsp+98h] [rbp-1h] BYREF

  v94 = a3;
  v3 = a1;
  v90 = a1;
  v4 = 0;
  *a3 = 0;
  v5 = 0;
  v93 = 0;
  Error = -2147024882;
  v7 = (CAceList *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v7;
  Src = v7;
  if ( !v7 )
    goto LABEL_50;
  *(_QWORD *)v7 = 0;
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 1;
  Error = CAceList::_Init(v7);
  if ( Error < 0 )
  {
    CAceList::`scalar deleting destructor'(v9, v10);
    goto LABEL_50;
  }
  v5 = v9;
  v93 = v9;
  Error = 0;
  v8 = 0;
  v79 = 0;
  v11 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer + 8 * (unsigned int)tls_index;
  v82 = v11;
  while ( 1 )
  {
    v12 = (int *)*((_QWORD *)v3 + 1);
    if ( v12 )
      v13 = *v12;
    else
      v13 = 0;
    if ( (int)v8 >= v13 )
    {
      Error = 0;
      v22 = a2;
      while ( 1 )
      {
        v23 = (int *)*((_QWORD *)v3 + 2);
        if ( v23 )
          v24 = *v23;
        else
          v24 = 0;
        if ( (int)v4 >= v24 )
        {
LABEL_48:
          if ( Error >= 0 )
          {
            v30 = v5;
            v5 = 0;
            *v94 = v30;
          }
          goto LABEL_50;
        }
        if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
        {
          if ( !g_hinstCC )
          {
            DelayLoadCC();
            if ( !g_hinstCC )
            {
              qword_180095A20 = 0;
LABEL_135:
              v25 = 0;
              goto LABEL_36;
            }
          }
          qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
        }
        if ( !qword_180095A20 )
          goto LABEL_135;
        v25 = qword_180095A20(v23, (int)v4);
LABEL_36:
        if ( (*(_BYTE *)(v25 + 28) & 1) == 0 )
          goto LABEL_47;
        v26 = *(void **)(v25 + 8);
        if ( (unsigned int)IsSidLocalMachineAndUnknown(v26) )
          goto LABEL_47;
        if ( v22 )
        {
          v27 = *(_DWORD *)(v25 + 28);
          if ( (v27 & 0x20) == 0 && (v27 & 1) != 0 )
          {
            v62 = *(_BYTE *)(v25 + 1);
            if ( !v62 || v62 == 9 )
              goto LABEL_47;
          }
        }
        if ( !GetSidSubAuthorityCount(v26) || *GetSidSubAuthority(v26, 0) != 80 )
        {
          v28 = 0;
          while ( (unsigned int)v28 < 2 )
          {
            v29 = IsWellKnownSid(*(PSID *)(v25 + 8), *((WELL_KNOWN_SID_TYPE *)&rgSystemSids + v28));
            v28 = (unsigned int)(v28 + 1);
            if ( v29 )
              goto LABEL_46;
          }
          Error = -2147024882;
          v47 = (DWORD *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
          v48 = v47;
          Src = v47;
          if ( !v47 )
            goto LABEL_50;
          *v47 = 0x80000;
          v47[1] = 0;
          *((_QWORD *)v47 + 1) = 0;
          *((_QWORD *)v47 + 2) = 0;
          *((_QWORD *)v47 + 3) = 0;
          v49 = *(void **)(v25 + 8);
          Error = -2147024809;
          if ( !v49 )
            goto LABEL_112;
          Src = *(void **)(v25 + 16);
          v77 = *(_WORD *)(v25 + 2);
          v75 = *(_BYTE *)v25;
          v73 = *(_BYTE *)(v25 + 1);
          v80 = *(_DWORD *)(v25 + 4);
          if ( !IsValidSid(v49) )
            goto LABEL_111;
          nDestinationSidLength[0] = GetLengthSid(v49);
          Error = -2147024882;
          v50 = LocalAlloc(0x40u, nDestinationSidLength[0]);
          v51 = v50;
          if ( !v50 )
            goto LABEL_111;
          if ( CopySid(nDestinationSidLength[0], v50, v49) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v51);
LABEL_112:
              CAce::`scalar deleting destructor'((CAce *)v48, v8);
              goto LABEL_50;
            }
          }
          *((_QWORD *)v48 + 1) = v51;
          v52 = Src;
          if ( Src )
          {
            v69 = GetLengthSid(v49) + 8;
            v53 = v77;
            if ( v77 > v69 )
            {
              v70 = v77 - v69;
              v48[6] = v70;
              v71 = LocalAlloc(0x40u, v70);
              *((_QWORD *)v48 + 2) = v71;
              if ( !v71 )
              {
                Error = -2147024882;
                goto LABEL_112;
              }
              memcpy_0(v71, v52, v48[6]);
            }
          }
          else
          {
            v53 = v77;
          }
          *(_BYTE *)v48 = v75;
          *((_BYTE *)v48 + 1) = v73;
          *((_WORD *)v48 + 1) = v53;
          v48[1] = v80;
          RtlMapGenericMask(v48 + 1, (PGENERIC_MAPPING)&GenericMapping);
          v48[7] = 0x80000000;
          if ( !*(_BYTE *)v48 || (v54 = 0x80000000, *(_BYTE *)v48 == 9) )
          {
            v48[7] = -2147483647;
            v54 = -2147483647;
          }
          if ( (*((_BYTE *)v48 + 1) & 0x10) != 0 )
          {
            v48[7] = v54 | 0x20;
          }
          else
          {
LABEL_111:
            if ( Error < 0 )
              goto LABEL_112;
          }
          v55 = v48[7];
          v56 = v55 & 0x20;
          if ( (v55 & 0x20) != 0 )
          {
            v57 = v55 & 1;
            goto LABEL_100;
          }
          v57 = v55 & 1;
          if ( v57 )
          {
LABEL_100:
            if ( !(_DWORD)v56 && v57 )
            {
              Error = CAceList::_AddExplicitAceToDpa(v56, (char *)v5 + 8, v48);
            }
            else
            {
              v58 = *((_QWORD *)v5 + 2);
              v59 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
              if ( qword_1800959F8 == -1 )
              {
                GetProcFromComCtl32(&qword_1800959F8, 334);
                v59 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
              }
              if ( v59 )
                v60 = v59(v58, 0x7FFFFFFF, v48);
              else
                v60 = -1;
              Error = 0;
              if ( v60 == -1 )
                Error = -2147024882;
            }
          }
          else
          {
            Error = CAceList::_AddExplicitAceToDpa(v56, v5, v48);
          }
          if ( Error < 0 || Error == 1 )
            CAce::`scalar deleting destructor'((CAce *)v48, v8);
          v3 = v90;
        }
LABEL_46:
        v22 = a2;
LABEL_47:
        LODWORD(v4) = v4 + 1;
        if ( Error < 0 )
          goto LABEL_48;
      }
    }
    if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
    {
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        if ( !g_hinstCC )
        {
          qword_180095A20 = 0;
          goto LABEL_10;
        }
      }
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
      v8 = v79;
    }
    if ( qword_180095A20 )
      v4 = qword_180095A20(v12, (int)v8);
LABEL_10:
    if ( (*(_BYTE *)(v4 + 28) & 1) == 0 )
      goto LABEL_27;
    v14 = *(void **)(v4 + 8);
    if ( dword_1800972D8 > *(_DWORD *)(*(_QWORD *)v11 + 4LL) )
    {
      Init_thread_header(&dword_1800972D8, v8);
      if ( dword_1800972D8 == -1 )
      {
        pszStr1 = 0;
        atexit(GetMachineStringSid_::_2_::_dynamic_atexit_destructor_for__s_spszMachineSid__);
        Init_thread_footer(&dword_1800972D8);
      }
    }
    if ( !dword_180096B74 )
    {
      dword_180096B74 = 1;
      nSize = 16;
      if ( GetComputerNameW(Buffer, &nSize) )
      {
        cbSid = 0;
        v81 = 0;
        v86 = 0;
        if ( !LookupAccountNameLocalW(Buffer, 0, &cbSid, 0, &v81, &v86) && cbSid && v81 )
        {
          v63 = LocalAlloc(0x40u, cbSid);
          Src = v63;
          if ( v63 )
          {
            v64 = 2LL * v81;
            if ( !is_mul_ok(v81, 2u) )
              v64 = -1;
            v65 = (WCHAR *)operator new[](v64, (const struct std::nothrow_t *)std::nothrow);
            if ( v65 )
            {
              if ( LookupAccountNameLocalW(Buffer, v63, &cbSid, v65, &v81, &v86) )
              {
                *(_QWORD *)nDestinationSidLength = 0;
                ConvertSidToStringSidW(v63, (LPWSTR *)nDestinationSidLength);
                if ( _InterlockedCompareExchange64(
                       (volatile signed __int64 *)&pszStr1,
                       *(signed __int64 *)nDestinationSidLength,
                       0) )
                {
                  LocalFree(*(HLOCAL *)nDestinationSidLength);
                }
              }
            }
            operator delete(v65);
          }
          CLocalMemPtr<void>::~CLocalMemPtr<void>(&Src);
        }
      }
    }
    v15 = pszStr1;
    if ( !pszStr1 )
      goto LABEL_22;
    v16 = 0;
    StringSid = 0;
    if ( ConvertSidToStringSidW(v14, &StringSid) )
    {
      v17 = StrRChrW(StringSid, 0, 0x2Du);
      if ( v17 )
      {
        *v17 = 0;
        v16 = StrCmpICW(v15, StringSid) == 0;
      }
    }
    v18 = StringSid;
    StringSid = 0;
    LocalFree(v18);
    if ( !v16
      || (cchName = 0,
          cchReferencedDomainName = 0,
          peUse = 0,
          LookupAccountSidLocalW(v14, 0, &cchName, 0, &cchReferencedDomainName, &peUse))
      || cchName
      || cchReferencedDomainName )
    {
LABEL_22:
      if ( !a2
        || (v19 = *(_DWORD *)(v4 + 28), (v19 & 0x20) != 0)
        || (v19 & 1) == 0
        || (v61 = *(_BYTE *)(v4 + 1)) != 0 && v61 != 9 )
      {
        if ( !GetSidSubAuthorityCount(v14) || *GetSidSubAuthority(v14, 0) != 80 )
          break;
      }
    }
LABEL_26:
    v11 = v82;
LABEL_27:
    v8 = ++v79;
    if ( Error < 0 )
      goto LABEL_50;
    v4 = 0;
  }
  v20 = 0;
  while ( (unsigned int)v20 < 2 )
  {
    v21 = IsWellKnownSid(*(PSID *)(v4 + 8), *((WELL_KNOWN_SID_TYPE *)&rgSystemSids + v20));
    v20 = (unsigned int)(v20 + 1);
    if ( v21 )
      goto LABEL_26;
  }
  Error = -2147024882;
  v32 = (DWORD *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v33 = v32;
  Src = v32;
  if ( v32 )
  {
    *v32 = 0x80000;
    v32[1] = 0;
    *((_QWORD *)v32 + 1) = 0;
    *((_QWORD *)v32 + 2) = 0;
    *((_QWORD *)v32 + 3) = 0;
    v34 = *(void **)(v4 + 8);
    Error = -2147024809;
    if ( !v34 )
      goto LABEL_83;
    Src = *(void **)(v4 + 16);
    v76 = *(_WORD *)(v4 + 2);
    v72 = *(_BYTE *)v4;
    v74 = *(_BYTE *)(v4 + 1);
    nDestinationSidLength[0] = *(_DWORD *)(v4 + 4);
    if ( !IsValidSid(v34) )
      goto LABEL_82;
    LengthSid = GetLengthSid(v34);
    Error = -2147024882;
    v36 = LocalAlloc(0x40u, LengthSid);
    v37 = v36;
    if ( !v36 )
      goto LABEL_82;
    if ( CopySid(LengthSid, v36, v34) )
    {
      Error = 0;
      goto LABEL_63;
    }
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LocalFree(v37);
LABEL_83:
      CAce::`scalar deleting destructor'((CAce *)v33, v8);
      goto LABEL_50;
    }
LABEL_63:
    *((_QWORD *)v33 + 1) = v37;
    v38 = Src;
    if ( Src )
    {
      v66 = GetLengthSid(v34) + 8;
      v39 = v76;
      if ( v76 > v66 )
      {
        v67 = v76 - v66;
        v33[6] = v67;
        v68 = LocalAlloc(0x40u, v67);
        *((_QWORD *)v33 + 2) = v68;
        if ( !v68 )
        {
          Error = -2147024882;
          goto LABEL_83;
        }
        memcpy_0(v68, v38, v33[6]);
      }
    }
    else
    {
      v39 = v76;
    }
    *(_BYTE *)v33 = v72;
    *((_BYTE *)v33 + 1) = v74;
    *((_WORD *)v33 + 1) = v39;
    v33[1] = nDestinationSidLength[0];
    RtlMapGenericMask(v33 + 1, (PGENERIC_MAPPING)&GenericMapping);
    v33[7] = 0x80000000;
    if ( !*(_BYTE *)v33 || (v40 = 0x80000000, *(_BYTE *)v33 == 9) )
    {
      v33[7] = -2147483647;
      v40 = -2147483647;
    }
    if ( (*((_BYTE *)v33 + 1) & 0x10) != 0 )
    {
      v33[7] = v40 | 0x20;
    }
    else
    {
LABEL_82:
      if ( Error < 0 )
        goto LABEL_83;
    }
    v41 = v33[7];
    v42 = v41 & 0x20;
    if ( (v41 & 0x20) != 0 )
    {
      v43 = v41 & 1;
      goto LABEL_71;
    }
    v43 = v41 & 1;
    if ( v43 )
    {
LABEL_71:
      if ( !(_DWORD)v42 && v43 )
      {
        Error = CAceList::_AddExplicitAceToDpa(v42, (char *)v5 + 8, v33);
      }
      else
      {
        v44 = *((_QWORD *)v5 + 2);
        v45 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
        if ( qword_1800959F8 == -1 )
        {
          GetProcFromComCtl32(&qword_1800959F8, 334);
          v45 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
        }
        if ( v45 )
          v46 = v45(v44, 0x7FFFFFFF, v33);
        else
          v46 = -1;
        Error = 0;
        if ( v46 == -1 )
          Error = -2147024882;
      }
    }
    else
    {
      Error = CAceList::_AddExplicitAceToDpa(v42, v5, v33);
    }
    if ( Error < 0 || Error == 1 )
      CAce::`scalar deleting destructor'((CAce *)v33, v8);
    v3 = v90;
    goto LABEL_26;
  }
LABEL_50:
  if ( v5 )
    CAceList::`scalar deleting destructor'(v5, v8);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000dd60  mov     [rsp-8+arg_8], rbx
0x18000dd65  push    rbp
0x18000dd66  push    rsi
0x18000dd67  push    rdi
0x18000dd68  push    r12
0x18000dd6a  push    r13
0x18000dd6c  push    r14
0x18000dd6e  push    r15
0x18000dd70  lea     rbp, [rsp-27h]
0x18000dd75  sub     rsp, 0C0h
0x18000dd7c  mov     rax, cs:__security_cookie
0x18000dd83  xor     rax, rsp
0x18000dd86  mov     [rbp+57h+var_38], rax
0x18000dd8a  mov     [rbp+57h+var_60], r8
0x18000dd8e  mov     [rbp+57h+var_BC], edx
0x18000dd91  mov     r13, rcx
0x18000dd94  mov     [rbp+57h+var_78], rcx
0x18000dd98  xor     r14d, r14d
0x18000dd9b  mov     [r8], r14
0x18000dd9e  mov     esi, r14d
0x18000dda1  mov     [rbp+57h+var_68], r14
0x18000dda5  mov     r15d, 8007000Eh
0x18000ddab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ddb2  mov     ecx, 20h ; ' '; unsigned __int64
0x18000ddb7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ddbc  mov     rbx, rax
0x18000ddbf  mov     [rbp+57h+Src], rax
0x18000ddc3  test    rax, rax
0x18000ddc6  jz      loc_18000E067
0x18000ddcc  mov     [rax], r14
0x18000ddcf  mov     [rax+8], r14
0x18000ddd3  mov     [rax+10h], r14
0x18000ddd7  mov     qword ptr [rax+18h], 1
0x18000dddf  mov     rcx, rax; this
0x18000dde2  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x18000dde7  mov     r15d, eax
0x18000ddea  test    eax, eax
0x18000ddec  js      loc_18000E899
0x18000ddf2  mov     rsi, rbx
0x18000ddf5  mov     [rbp+57h+var_68], rbx
0x18000ddf9  mov     r15d, r14d
0x18000ddfc  mov     edx, r14d
0x18000ddff  mov     [rbp+57h+var_B8], edx
0x18000de02  mov     ecx, cs:_tls_index
0x18000de08  mov     rax, gs:58h
0x18000de11  lea     rdi, [rax+rcx*8]
0x18000de15  mov     [rbp+57h+var_B0], rdi
0x18000de19  nop     dword ptr [rax+00000000h]
0x18000de20  mov     rbx, [r13+8]
0x18000de24  test    rbx, rbx
0x18000de27  jz      loc_18000E663
0x18000de2d  mov     eax, [rbx]
0x18000de2f  cmp     edx, eax
0x18000de31  jge     loc_18000DF82
0x18000de37  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000de3f  jz      loc_18000E4DA
0x18000de45  mov     rax, cs:qword_180095A20
0x18000de4c  test    rax, rax
0x18000de4f  jz      short loc_18000DE5F
0x18000de51  movsxd  rdx, edx
0x18000de54  mov     rcx, rbx
0x18000de57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de5c  mov     r14, rax
0x18000de5f  test    byte ptr [r14+1Ch], 1
0x18000de64  jz      loc_18000DF69
0x18000de6a  mov     r12, [r14+8]
0x18000de6e  mov     ecx, 4
0x18000de73  mov     rax, [rdi]
0x18000de76  mov     ecx, [rcx+rax]
0x18000de79  cmp     cs:dword_1800972D8, ecx
0x18000de7f  jg      loc_18000E5CC
0x18000de85  cmp     cs:dword_180096B74, 0
0x18000de8c  jz      loc_18000E66B
0x18000de92  mov     rdi, cs:pszStr1
0x18000de99  test    rdi, rdi
0x18000de9c  jz      short loc_18000DF03
0x18000de9e  xor     ebx, ebx
0x18000dea0  mov     [rbp+57h+StringSid], rbx
0x18000dea4  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18000dea8  mov     rcx, r12; Sid
0x18000deab  call    cs:__imp_ConvertSidToStringSidW
0x18000deb1  test    eax, eax
0x18000deb3  jz      short loc_18000DEE8
0x18000deb5  xor     edx, edx; pszEnd
0x18000deb7  mov     r8d, 2Dh ; '-'; wMatch
0x18000debd  mov     rcx, [rbp+57h+StringSid]; pszStart
0x18000dec1  call    cs:__imp_StrRChrW
0x18000dec7  test    rax, rax
0x18000deca  jz      short loc_18000DEE8
0x18000decc  xor     edx, edx
0x18000dece  mov     [rax], dx
0x18000ded1  mov     rdx, [rbp+57h+StringSid]; pszStr2
0x18000ded5  mov     rcx, rdi; pszStr1
0x18000ded8  call    cs:__imp_StrCmpICW
0x18000dede  test    eax, eax
0x18000dee0  mov     eax, 1
0x18000dee5  cmovz   ebx, eax
0x18000dee8  mov     rcx, [rbp+57h+StringSid]; hMem
0x18000deec  mov     [rbp+57h+StringSid], 0
0x18000def4  call    cs:__imp_LocalFree
0x18000defa  nop
0x18000defb  test    ebx, ebx
0x18000defd  jnz     loc_18000E09E
0x18000df03  cmp     [rbp+57h+var_BC], 0
0x18000df07  jz      short loc_18000DF19
0x18000df09  mov     eax, [r14+1Ch]
0x18000df0d  test    al, 20h
0x18000df0f  jnz     short loc_18000DF19
0x18000df11  test    al, 1
0x18000df13  jnz     loc_18000E57B
0x18000df19  xor     edi, edi
0x18000df1b  mov     rcx, r12; pSid
0x18000df1e  call    cs:__imp_GetSidSubAuthorityCount
0x18000df24  test    rax, rax
0x18000df27  jz      short loc_18000DF39
0x18000df29  xor     edx, edx; nSubAuthority
0x18000df2b  mov     rcx, r12; pSid
0x18000df2e  call    cs:__imp_GetSidSubAuthority
0x18000df34  cmp     dword ptr [rax], 50h ; 'P'
0x18000df37  jz      short loc_18000DF65
0x18000df39  xor     ebx, ebx
0x18000df3b  nop     dword ptr [rax+rax+00h]
0x18000df40  cmp     ebx, 2
0x18000df43  jnb     loc_18000E0F6
0x18000df49  lea     rax, ?rgSystemSids@@3PAW4WELL_KNOWN_SID_TYPE@@A; WELL_KNOWN_SID_TYPE near * rgSystemSids
0x18000df50  mov     edx, [rax+rbx*4]; WellKnownSidType
0x18000df53  mov     rcx, [r14+8]; pSid
0x18000df57  call    cs:__imp_IsWellKnownSid
0x18000df5d  mov     edi, eax
0x18000df5f  inc     ebx
0x18000df61  test    eax, eax
0x18000df63  jz      short loc_18000DF40
0x18000df65  mov     rdi, [rbp+57h+var_B0]
0x18000df69  mov     edx, [rbp+57h+var_B8]
0x18000df6c  inc     edx
0x18000df6e  mov     [rbp+57h+var_B8], edx
0x18000df71  test    r15d, r15d
0x18000df74  js      loc_18000E067
0x18000df7a  xor     r14d, r14d
0x18000df7d  jmp     loc_18000DE20
0x18000df82  mov     r15d, r14d
0x18000df85  mov     r12d, [rbp+57h+var_BC]
0x18000df89  mov     rbx, [r13+10h]
0x18000df8d  test    rbx, rbx
0x18000df90  jz      loc_18000E814
0x18000df96  mov     eax, [rbx]
0x18000df98  cmp     r14d, eax
0x18000df9b  jge     loc_18000E056
0x18000dfa1  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000dfa9  jz      loc_18000E518
0x18000dfaf  mov     rax, cs:qword_180095A20
0x18000dfb6  test    rax, rax
0x18000dfb9  jz      loc_18000E5C5
0x18000dfbf  movsxd  rdx, r14d
0x18000dfc2  mov     rcx, rbx
0x18000dfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfca  mov     rbx, rax
0x18000dfcd  test    byte ptr [rbx+1Ch], 1
0x18000dfd1  jz      short loc_18000E04A
0x18000dfd3  mov     rdi, [rbx+8]
0x18000dfd7  mov     rcx, rdi; Sid
0x18000dfda  call    ?IsSidLocalMachineAndUnknown@@YAHPEAX@Z; IsSidLocalMachineAndUnknown(void *)
0x18000dfdf  test    eax, eax
0x18000dfe1  jnz     short loc_18000E04A
0x18000dfe3  test    r12d, r12d
0x18000dfe6  jz      short loc_18000DFF7
0x18000dfe8  mov     eax, [rbx+1Ch]
0x18000dfeb  test    al, 20h
0x18000dfed  jnz     short loc_18000DFF7
0x18000dfef  test    al, 1
0x18000dff1  jnz     loc_18000E595
0x18000dff7  xor     r12d, r12d
0x18000dffa  mov     rcx, rdi; pSid
0x18000dffd  call    cs:__imp_GetSidSubAuthorityCount
0x18000e003  test    rax, rax
0x18000e006  jz      short loc_18000E018
0x18000e008  xor     edx, edx; nSubAuthority
0x18000e00a  mov     rcx, rdi; pSid
0x18000e00d  call    cs:__imp_GetSidSubAuthority
0x18000e013  cmp     dword ptr [rax], 50h ; 'P'
0x18000e016  jz      short loc_18000E046
0x18000e018  xor     edi, edi
0x18000e01a  nop     word ptr [rax+rax+00h]
0x18000e020  cmp     edi, 2
0x18000e023  jnb     loc_18000E2CE
0x18000e029  lea     rax, ?rgSystemSids@@3PAW4WELL_KNOWN_SID_TYPE@@A; WELL_KNOWN_SID_TYPE near * rgSystemSids
0x18000e030  mov     edx, [rax+rdi*4]; WellKnownSidType
0x18000e033  mov     rcx, [rbx+8]; pSid
0x18000e037  call    cs:__imp_IsWellKnownSid
0x18000e03d  mov     r12d, eax
0x18000e040  inc     edi
0x18000e042  test    eax, eax
0x18000e044  jz      short loc_18000E020
0x18000e046  mov     r12d, [rbp+57h+var_BC]
0x18000e04a  inc     r14d
0x18000e04d  test    r15d, r15d
0x18000e050  jns     loc_18000DF89
0x18000e056  test    r15d, r15d
0x18000e059  js      short loc_18000E067
0x18000e05b  mov     rax, rsi
0x18000e05e  xor     esi, esi
0x18000e060  mov     rcx, [rbp+57h+var_60]
0x18000e064  mov     [rcx], rax
0x18000e067  test    rsi, rsi
0x18000e06a  jz      short loc_18000E074
0x18000e06c  mov     rcx, rsi; this
0x18000e06f  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000e074  mov     eax, r15d
0x18000e077  mov     rcx, [rbp+57h+var_38]
0x18000e07b  xor     rcx, rsp; StackCookie
0x18000e07e  call    __security_check_cookie
0x18000e083  mov     rbx, [rsp+0F0h+arg_8]
0x18000e08b  add     rsp, 0C0h
0x18000e092  pop     r15
0x18000e094  pop     r14
0x18000e096  pop     r13
0x18000e098  pop     r12
0x18000e09a  pop     rdi
0x18000e09b  pop     rsi
0x18000e09c  pop     rbp
0x18000e09d  retn
0x18000e09e  mov     [rbp+57h+cchName], 0
0x18000e0a5  mov     [rbp+57h+var_88], 0
0x18000e0ac  mov     [rbp+57h+var_6C], 0
0x18000e0b3  lea     rax, [rbp+57h+var_6C]
0x18000e0b7  mov     [rsp+0F0h+peUse], rax; peUse
0x18000e0bc  lea     rax, [rbp+57h+var_88]
0x18000e0c0  mov     [rsp+0F0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000e0c5  xor     r9d, r9d; ReferencedDomainName
0x18000e0c8  lea     r8, [rbp+57h+cchName]; cchName
0x18000e0cc  xor     edx, edx; Name
0x18000e0ce  mov     rcx, r12; Sid
0x18000e0d1  call    cs:__imp_LookupAccountSidLocalW
0x18000e0d7  test    eax, eax
0x18000e0d9  jnz     loc_18000DF03
0x18000e0df  cmp     [rbp+57h+cchName], eax
0x18000e0e2  jnz     loc_18000DF03
0x18000e0e8  cmp     [rbp+57h+var_88], eax
0x18000e0eb  jz      loc_18000DF65
0x18000e0f1  jmp     loc_18000DF03
0x18000e0f6  test    edi, edi
0x18000e0f8  jnz     loc_18000DF65
0x18000e0fe  mov     r15d, 8007000Eh
0x18000e104  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e10b  mov     ecx, 20h ; ' '; unsigned __int64
0x18000e110  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e115  mov     rbx, rax
0x18000e118  mov     [rbp+57h+Src], rax
0x18000e11c  test    rax, rax
0x18000e11f  jz      loc_18000E067
0x18000e125  mov     dword ptr [rax], 80000h
0x18000e12b  xor     eax, eax
0x18000e12d  mov     [rbx+4], eax
0x18000e130  mov     [rbx+8], rax
0x18000e134  mov     [rbx+10h], rax
0x18000e138  mov     [rbx+18h], rax
0x18000e13c  mov     rdi, [r14+8]
0x18000e140  mov     r15d, 80070057h
0x18000e146  test    rdi, rdi
0x18000e149  jz      loc_18000E2AE
0x18000e14f  mov     rax, [r14+10h]
0x18000e153  mov     [rbp+57h+Src], rax
0x18000e157  movzx   eax, word ptr [r14+2]
0x18000e15c  mov     [rbp+57h+var_BE], ax
0x18000e160  movzx   eax, byte ptr [r14]
0x18000e164  mov     [rbp+57h+var_C0], al
0x18000e167  movzx   eax, byte ptr [r14+1]
0x18000e16c  mov     [rbp+57h+var_BF], al
0x18000e16f  mov     eax, [r14+4]
0x18000e173  mov     [rbp+57h+nDestinationSidLength], eax
0x18000e176  mov     rcx, rdi; pSid
0x18000e179  call    cs:__imp_IsValidSid
0x18000e17f  test    eax, eax
0x18000e181  jz      loc_18000E2A9
0x18000e187  mov     rcx, rdi; pSid
0x18000e18a  call    cs:__imp_GetLengthSid
0x18000e190  mov     r13d, eax
0x18000e193  mov     r15d, 8007000Eh
0x18000e199  mov     edx, eax; uBytes
0x18000e19b  mov     ecx, 40h ; '@'; uFlags
0x18000e1a0  call    cs:__imp_LocalAlloc
0x18000e1a6  mov     r14, rax
0x18000e1a9  test    rax, rax
0x18000e1ac  jz      loc_18000E2A9
0x18000e1b2  mov     r8, rdi; pSourceSid
0x18000e1b5  mov     rdx, rax; pDestinationSid
0x18000e1b8  mov     ecx, r13d; nDestinationSidLength
0x18000e1bb  call    cs:__imp_CopySid
0x18000e1c1  test    eax, eax
0x18000e1c3  jz      loc_18000E60D
0x18000e1c9  xor     r15d, r15d
0x18000e1cc  mov     [rbx+8], r14
0x18000e1d0  mov     r14, [rbp+57h+Src]
0x18000e1d4  test    r14, r14
0x18000e1d7  jnz     loc_18000E799
0x18000e1dd  movzx   edi, [rbp+57h+var_BE]
0x18000e1e1  movzx   eax, [rbp+57h+var_C0]
0x18000e1e5  mov     [rbx], al
0x18000e1e7  movzx   eax, [rbp+57h+var_BF]
0x18000e1eb  mov     [rbx+1], al
  ... truncated ...
```
