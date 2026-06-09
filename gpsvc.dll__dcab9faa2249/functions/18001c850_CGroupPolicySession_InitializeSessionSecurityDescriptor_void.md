# CGroupPolicySession::InitializeSessionSecurityDescriptor(void)

- ea: `0x18001c850`
- end: `0x18001d0b1`
- name: `?InitializeSessionSecurityDescriptor@CGroupPolicySession@@AEAAKXZ`
- size: `2145`
- prototype: `unsigned int __fastcall(CGroupPolicySession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010ed0`

## callees

- `0x18000a504`
- `0x18001c850`
- `0x18001d0c0`
- `0x18001d220`
- `0x18001d380`
- `0x18001d6e8`
- `0x180072a08`
- `0x18007d320`
- `0x1800b5e10`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d081`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c89e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c89e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cc49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ca40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ccc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ceab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c9d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ca40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cca5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ccc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ceab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ce81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ceeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ce81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ceeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cd59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ce77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cee1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ce77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cee1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001cc39`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001cc39`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001cc28`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001cc28`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001cc68`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001cc68`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c962`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cae7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cb8e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cdcd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c962`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cae7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cb8e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cdcd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ca38`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ce19`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cf38`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cffb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001d023`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001d04b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ca38`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ce19`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cf38`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cffb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001d023`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001d04b`

## string_xrefs

- `0x18001ce40`: `AddAdministrators: Failed to initialize sid.  Error = %d`
- `0x18001ce92`: `AddNetworkService: Failed to initialize sid.  Error = %d`
- `0x18001cef6`: `AddNetworkService: Not initialised or failure.`
- `0x18001d05c`: `AddAuthUsers: Failed to initialize authenticated users sid.  Error = %d`
- `0x18001cf6a`: `AddSid: Not initialised or failure.`
- `0x18001cf98`: `AddSid: Not a vaild Sid.`
- `0x18001cfaa`: `AddSid: Couldn't allocate memory. Error %d`
- `0x18001c976`: `AddLocalSystem: Failed to initialize sid.  Error = %d`
- `0x18001d08a`: `AddSid: Couldn't copy Sid. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGroupPolicySession::InitializeSessionSecurityDescriptor(CGroupPolicySession *this)
{
  DWORD v2; // esi
  int v3; // r15d
  DWORD LastError; // eax
  PSID v5; // rcx
  unsigned int i; // ebx
  char *v8; // rdx
  void *v9; // rcx
  unsigned int v10; // ebx
  PSID v11; // rdx
  __int64 v12; // rcx
  _DWORD *v13; // rax
  unsigned int v14; // ebx
  PSID v15; // rdx
  __int64 v16; // rcx
  _DWORD *v17; // rax
  unsigned int v18; // ebx
  PSID v19; // rdx
  __int64 v20; // rcx
  _DWORD *v21; // rax
  __int64 v22; // rbx
  PSID v23; // r15
  SIZE_T LengthSid; // r12
  HLOCAL v25; // rax
  HLOCAL v26; // rdi
  __int64 v27; // rcx
  _DWORD *v28; // rax
  struct _SECURITY_DESCRIPTOR *SD; // rbx
  void *v30; // rcx
  int v31; // edi
  PSID v32; // rdx
  __int64 v33; // rcx
  _DWORD *v34; // rax
  DWORD v35; // eax
  DWORD v36; // eax
  DWORD v37; // eax
  DWORD v38; // eax
  DWORD v39; // eax
  PSID pSid; // [rsp+60h] [rbp-49h] BYREF
  PSID pSourceSid; // [rsp+68h] [rbp-41h] BYREF
  HLOCAL v42; // [rsp+70h] [rbp-39h] BYREF
  __int64 v43; // [rsp+78h] [rbp-31h]
  __int64 v44; // [rsp+80h] [rbp-29h]
  HLOCAL hMem[2]; // [rsp+88h] [rbp-21h]
  DWORD cbData; // [rsp+98h] [rbp-11h] BYREF
  BYTE Data[4]; // [rsp+9Ch] [rbp-Dh] BYREF
  int v48; // [rsp+A0h] [rbp-9h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A4h] [rbp-5h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v50; // [rsp+ACh] [rbp+3h] BYREF

  v48 = 1;
  v43 = 0;
  v44 = 0;
  *(_OWORD *)hMem = 0;
  v42 = LocalAlloc(0x40u, 0xF0u);
  if ( v42 )
  {
    HIDWORD(v43) = 10;
    LODWORD(v44) = 1;
  }
  v2 = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 23) + 16LL))((char *)this + 184, &v48);
  if ( v2 )
    goto LABEL_12;
  if ( !(unsigned int)CSecDesc::AddAdministratorsAsOwner((CSecDesc *)&v42)
    || !(unsigned int)CSecDesc::AddAdministratorsAsGroup((CSecDesc *)&v42) )
  {
    goto LABEL_11;
  }
  *(_DWORD *)pIdentifierAuthority.Value = v2;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v3 = v44;
  if ( !(_DWORD)v44 || HIDWORD(v44) != v2 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddLocalSystem: Not initialised or failure.");
    goto LABEL_11;
  }
  HIDWORD(v44) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgCommon,
      2u,
      L"AddLocalSystem: Failed to initialize sid.  Error = %d",
      LastError);
    goto LABEL_10;
  }
  v10 = v43;
  if ( (_DWORD)v43 == HIDWORD(v43) )
  {
    if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v42) )
    {
      v5 = pSid;
      if ( !pSid )
        goto LABEL_11;
      goto LABEL_70;
    }
    v3 = v44;
    v10 = v43;
  }
  v11 = pSid;
  pSid = 0;
  v12 = 3LL * v10;
  v13 = v42;
  *((_QWORD *)v42 + v12) = v11;
  v13[2 * v12 + 2] = 13;
  v13[2 * v12 + 4] = 0;
  v14 = v10 + 1;
  LODWORD(v43) = v14;
  HIDWORD(v44) = 0;
  if ( pSid )
    FreeSid(pSid);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v3 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAdministrators: Not initialised or failure.");
    goto LABEL_10;
  }
  HIDWORD(v44) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v35 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAdministrators: Failed to initialize sid.  Error = %d", v35);
    goto LABEL_10;
  }
  if ( v14 == HIDWORD(v43) )
  {
    if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v42) )
      goto LABEL_10;
    v3 = v44;
    v14 = v43;
  }
  v15 = pSid;
  pSid = 0;
  v16 = 3LL * v14;
  v17 = v42;
  *((_QWORD *)v42 + v16) = v15;
  v17[2 * v16 + 2] = 13;
  v17[2 * v16 + 4] = 0;
  v18 = v14 + 1;
  LODWORD(v43) = v18;
  HIDWORD(v44) = 0;
  if ( pSid )
    FreeSid(pSid);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v3 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddNetworkService: Not initialised or failure.");
    goto LABEL_10;
  }
  HIDWORD(v44) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v36 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddNetworkService: Failed to initialize sid.  Error = %d", v36);
    goto LABEL_10;
  }
  if ( v18 == HIDWORD(v43) )
  {
    if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v42) )
      goto LABEL_10;
    v3 = v44;
    v18 = v43;
  }
  v19 = pSid;
  pSid = 0;
  v20 = 3LL * v18;
  v21 = v42;
  *((_QWORD *)v42 + v20) = v19;
  v21[2 * v20 + 2] = 13;
  v21[2 * v20 + 4] = 0;
  v22 = v18 + 1;
  LODWORD(v43) = v22;
  HIDWORD(v44) = 0;
  if ( pSid )
    FreeSid(pSid);
  pSourceSid = 0;
  if ( v48 )
  {
    *(_DWORD *)Data = 0;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    cbData = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            0,
            0x20019u,
            (PHKEY)&pSourceSid) )
    {
      cbData = 4;
      RegQueryValueExW((HKEY)pSourceSid, L"DenyUsersFromMachGP", 0, (LPDWORD)pIdentifierAuthority.Value, Data, &cbData);
      RegCloseKey((HKEY)pSourceSid);
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\System",
            0,
            0x20019u,
            (PHKEY)&pSourceSid) )
    {
      cbData = 4;
      RegQueryValueExW((HKEY)pSourceSid, L"DenyUsersFromMachGP", 0, (LPDWORD)pIdentifierAuthority.Value, Data, &cbData);
      RegCloseKey((HKEY)pSourceSid);
    }
    if ( *(_DWORD *)Data )
    {
      v31 = 5;
      CGPOperationalTraceEvent::ReportOperationalEvent(0x100Fu, 0);
    }
    else
    {
      v31 = 13;
    }
    *(_DWORD *)v50.Value = 0;
    *(_WORD *)&v50.Value[4] = 1280;
    pSid = 0;
    if ( !v3 )
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAuthUsers: Not initialised or failure.");
      v5 = pSid;
      if ( !pSid )
        goto LABEL_11;
      goto LABEL_70;
    }
    HIDWORD(v44) = 1;
    if ( AllocateAndInitializeSid(&v50, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( (_DWORD)v22 != HIDWORD(v43) )
        goto LABEL_61;
      if ( (unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v42) )
      {
        LODWORD(v22) = v43;
LABEL_61:
        v32 = pSid;
        pSid = 0;
        v33 = 3LL * (unsigned int)v22;
        v34 = v42;
        *((_QWORD *)v42 + v33) = v32;
        v34[2 * v33 + 2] = v31;
        v34[2 * v33 + 4] = 0;
        LODWORD(v43) = v22 + 1;
        HIDWORD(v44) = 0;
        if ( pSid )
          FreeSid(pSid);
LABEL_48:
        SD = CSecDesc::MakeSD((CSecDesc *)&v42);
        v30 = (void *)*((_QWORD *)this + 52);
        if ( v30 )
          LocalFree(v30);
        *((_QWORD *)this + 52) = SD;
        if ( SD )
        {
          *((_DWORD *)this + 106) = 5;
          *(_QWORD *)((char *)this + 428) = 8;
          *((_DWORD *)this + 109) = 13;
          goto LABEL_12;
        }
        goto LABEL_11;
      }
    }
    else
    {
      v38 = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgCommon,
        2u,
        L"AddAuthUsers: Failed to initialize authenticated users sid.  Error = %d",
        v38);
    }
LABEL_10:
    v5 = pSid;
    if ( !pSid )
    {
LABEL_11:
      v2 = GetLastError();
      goto LABEL_12;
    }
LABEL_70:
    FreeSid(v5);
    goto LABEL_11;
  }
  v2 = (*(__int64 (__fastcall **)(char *, PSID *))(*((_QWORD *)this + 23) + 72LL))((char *)this + 184, &pSourceSid);
  if ( !v2 )
  {
    if ( v3 )
    {
      v23 = pSourceSid;
      HIDWORD(v44) = 1;
      if ( IsValidSid(pSourceSid) )
      {
        LengthSid = GetLengthSid(v23);
        v25 = LocalAlloc(0x40u, LengthSid);
        v26 = v25;
        pSid = v25;
        if ( v25 )
        {
          if ( CopySid(LengthSid, v25, v23) )
          {
            v27 = 3 * v22;
            v28 = v42;
            *((_QWORD *)v42 + v27) = v26;
            v28[2 * v27 + 2] = 13;
            *(_QWORD *)&v28[2 * v27 + 3] = 1;
            LODWORD(v43) = v22 + 1;
            HIDWORD(v44) = 0;
            if ( pSourceSid )
              LocalFree(pSourceSid);
            goto LABEL_48;
          }
          v39 = GetLastError();
          CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Couldn't copy Sid. Error %d", v39);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSid);
        }
        else
        {
          v37 = GetLastError();
          CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Couldn't allocate memory. Error %d", v37);
        }
      }
      else
      {
        CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Not a vaild Sid.");
      }
    }
    else
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddSid: Not initialised or failure.");
    }
    v2 = GetLastError();
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSourceSid);
    goto LABEL_12;
  }
  if ( pSourceSid )
    LocalFree(pSourceSid);
LABEL_12:
  if ( v42 )
  {
    for ( i = 0; i < HIDWORD(v43); ++i )
    {
      v8 = (char *)v42 + 24 * i;
      v9 = *(void **)v8;
      if ( *(_QWORD *)v8 )
      {
        if ( *((_DWORD *)v8 + 3) )
          LocalFree(v9);
        else
          FreeSid(v9);
      }
    }
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v42 )
    LocalFree(v42);
  return v2;
}

```

## disassembly

```asm
0x18001c850  push    rbp
0x18001c852  push    rbx
0x18001c853  push    rsi
0x18001c854  push    rdi
0x18001c855  push    r12
0x18001c857  push    r13
0x18001c859  push    r14
0x18001c85b  push    r15
0x18001c85d  lea     rbp, [rsp-1Fh]
0x18001c862  sub     rsp, 0C8h
0x18001c869  mov     rax, cs:__security_cookie
0x18001c870  xor     rax, rsp
0x18001c873  mov     [rbp+57h+var_48], rax
0x18001c877  mov     r14, rcx
0x18001c87a  mov     [rbp+57h+var_60], 1
0x18001c881  xor     r13d, r13d
0x18001c884  mov     [rbp+57h+var_88], r13
0x18001c888  mov     [rbp+57h+var_80], r13
0x18001c88c  xorps   xmm0, xmm0
0x18001c88f  movdqu  xmmword ptr [rbp+57h+hMem], xmm0
0x18001c894  mov     edx, 0F0h; uBytes
0x18001c899  mov     ecx, 40h ; '@'; uFlags
0x18001c89e  call    cs:__imp_LocalAlloc
0x18001c8a4  mov     [rbp+57h+var_90], rax
0x18001c8a8  test    rax, rax
0x18001c8ab  jz      short loc_18001C8BB
0x18001c8ad  mov     dword ptr [rbp+57h+var_88+4], 0Ah
0x18001c8b4  mov     dword ptr [rbp+57h+var_80], 1
0x18001c8bb  mov     rax, [r14+0B8h]
0x18001c8c2  lea     rdx, [rbp+57h+var_60]
0x18001c8c6  lea     rcx, [r14+0B8h]
0x18001c8cd  mov     rax, [rax+10h]
0x18001c8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d6  mov     esi, eax
0x18001c8d8  test    eax, eax
0x18001c8da  jnz     loc_18001C9A6
0x18001c8e0  lea     rcx, [rbp+57h+var_90]; this
0x18001c8e4  call    ?AddAdministratorsAsOwner@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsOwner(void)
0x18001c8e9  test    eax, eax
0x18001c8eb  jz      loc_18001C99E
0x18001c8f1  lea     rcx, [rbp+57h+var_90]; this
0x18001c8f5  call    ?AddAdministratorsAsGroup@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsGroup(void)
0x18001c8fa  test    eax, eax
0x18001c8fc  jz      loc_18001C99E
0x18001c902  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18001c905  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001c90b  mov     [rbp+57h+var_A0], r13
0x18001c90f  mov     r15d, dword ptr [rbp+57h+var_80]
0x18001c913  test    r15d, r15d
0x18001c916  jz      loc_18001CF13
0x18001c91c  cmp     dword ptr [rbp+57h+var_80+4], esi
0x18001c91f  jnz     loc_18001CF13
0x18001c925  mov     dword ptr [rbp+57h+var_80+4], 1
0x18001c92c  lea     rax, [rbp+57h+var_A0]
0x18001c930  mov     [rsp+100h+pSid], rax; pSid
0x18001c935  mov     [rsp+100h+nSubAuthority7], r13d; nSubAuthority7
0x18001c93a  mov     [rsp+100h+nSubAuthority6], r13d; nSubAuthority6
0x18001c93f  mov     [rsp+100h+nSubAuthority5], r13d; nSubAuthority5
0x18001c944  mov     [rsp+100h+nSubAuthority4], r13d; nSubAuthority4
0x18001c949  mov     [rsp+100h+nSubAuthority3], r13d; nSubAuthority3
0x18001c94e  mov     [rsp+100h+nSubAuthority2], r13d; nSubAuthority2
0x18001c953  xor     r9d, r9d; nSubAuthority1
0x18001c956  mov     r8d, 12h; nSubAuthority0
0x18001c95c  mov     dl, 1; nSubAuthorityCount
0x18001c95e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001c962  call    cs:__imp_AllocateAndInitializeSid
0x18001c968  test    eax, eax
0x18001c96a  jnz     loc_18001CA48
0x18001c970  call    cs:__imp_GetLastError
0x18001c976  lea     r8, aAddlocalsystem_0; "AddLocalSystem: Failed to initialize si"...
0x18001c97d  mov     r9d, eax
0x18001c980  mov     edx, 2; unsigned int
0x18001c985  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001c98c  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001c991  mov     rcx, [rbp+57h+var_A0]
0x18001c995  test    rcx, rcx
0x18001c998  jnz     loc_18001CF38
0x18001c99e  call    cs:__imp_GetLastError
0x18001c9a4  mov     esi, eax
0x18001c9a6  cmp     [rbp+57h+var_90], 0
0x18001c9ab  jnz     short loc_18001C9FC
0x18001c9ad  mov     rcx, [rbp+57h+hMem+8]; hMem
0x18001c9b1  test    rcx, rcx
0x18001c9b4  jz      short loc_18001C9BC
0x18001c9b6  call    cs:__imp_LocalFree
0x18001c9bc  mov     rcx, [rbp+57h+hMem]; hMem
0x18001c9c0  test    rcx, rcx
0x18001c9c3  jz      short loc_18001C9CB
0x18001c9c5  call    cs:__imp_LocalFree
0x18001c9cb  mov     rcx, [rbp+57h+var_90]; hMem
0x18001c9cf  test    rcx, rcx
0x18001c9d2  jz      short loc_18001C9DA
0x18001c9d4  call    cs:__imp_LocalFree
0x18001c9da  mov     eax, esi
0x18001c9dc  mov     rcx, [rbp+57h+var_48]
0x18001c9e0  xor     rcx, rsp; StackCookie
0x18001c9e3  call    __security_check_cookie
0x18001c9e8  add     rsp, 0C8h
0x18001c9ef  pop     r15
0x18001c9f1  pop     r14
0x18001c9f3  pop     r13
0x18001c9f5  pop     r12
0x18001c9f7  pop     rdi
0x18001c9f8  pop     rsi
0x18001c9f9  pop     rbx
0x18001c9fa  pop     rbp
0x18001c9fb  retn
0x18001c9fc  mov     ebx, r13d
0x18001c9ff  cmp     dword ptr [rbp+57h+var_88+4], r13d
0x18001ca03  jbe     short loc_18001C9AD
0x18001ca05  nop     word ptr [rax+rax+00000000h]
0x18001ca10  mov     eax, ebx
0x18001ca12  lea     rcx, [rax+rax*2]
0x18001ca16  mov     rax, [rbp+57h+var_90]
0x18001ca1a  lea     rdx, [rax+rcx*8]
0x18001ca1e  mov     rcx, [rdx]; hMem
0x18001ca21  test    rcx, rcx
0x18001ca24  jnz     short loc_18001CA32
0x18001ca26  inc     ebx
0x18001ca28  cmp     ebx, dword ptr [rbp+57h+var_88+4]
0x18001ca2b  jb      short loc_18001CA10
0x18001ca2d  jmp     loc_18001C9AD
0x18001ca32  cmp     dword ptr [rdx+0Ch], 0
0x18001ca36  jnz     short loc_18001CA40
0x18001ca38  call    cs:__imp_FreeSid
0x18001ca3e  jmp     short loc_18001CA26
0x18001ca40  call    cs:__imp_LocalFree
0x18001ca46  jmp     short loc_18001CA26
0x18001ca48  mov     ebx, dword ptr [rbp+57h+var_88]
0x18001ca4b  cmp     ebx, dword ptr [rbp+57h+var_88+4]
0x18001ca4e  jz      loc_18001CFE2
0x18001ca54  mov     rdx, [rbp+57h+var_A0]
0x18001ca58  mov     [rbp+57h+var_A0], r13
0x18001ca5c  mov     eax, ebx
0x18001ca5e  lea     rcx, [rax+rax*2]
0x18001ca62  mov     rax, [rbp+57h+var_90]
0x18001ca66  mov     [rax+rcx*8], rdx
0x18001ca6a  mov     dword ptr [rax+rcx*8+8], 0Dh
0x18001ca72  mov     [rax+rcx*8+10h], r13d
0x18001ca77  inc     ebx
0x18001ca79  mov     dword ptr [rbp+57h+var_88], ebx
0x18001ca7c  mov     dword ptr [rbp+57h+var_80+4], r13d
0x18001ca80  mov     rcx, [rbp+57h+var_A0]; pSid
0x18001ca84  test    rcx, rcx
0x18001ca87  jnz     loc_18001CFFB
0x18001ca8d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x18001ca94  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001ca9a  mov     [rbp+57h+var_A0], r13
0x18001ca9e  test    r15d, r15d
0x18001caa1  jz      loc_18001CFC4
0x18001caa7  mov     dword ptr [rbp+57h+var_80+4], 1
0x18001caae  lea     rax, [rbp+57h+var_A0]
0x18001cab2  mov     [rsp+100h+pSid], rax; pSid
0x18001cab7  mov     [rsp+100h+nSubAuthority7], r13d; nSubAuthority7
0x18001cabc  mov     [rsp+100h+nSubAuthority6], r13d; nSubAuthority6
0x18001cac1  mov     [rsp+100h+nSubAuthority5], r13d; nSubAuthority5
0x18001cac6  mov     [rsp+100h+nSubAuthority4], r13d; nSubAuthority4
0x18001cacb  mov     [rsp+100h+nSubAuthority3], r13d; nSubAuthority3
0x18001cad0  mov     [rsp+100h+nSubAuthority2], r13d; nSubAuthority2
0x18001cad5  mov     r9d, 220h; nSubAuthority1
0x18001cadb  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001cae1  mov     dl, 2; nSubAuthorityCount
0x18001cae3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001cae7  call    cs:__imp_AllocateAndInitializeSid
0x18001caed  test    eax, eax
0x18001caef  jz      loc_18001CE3A
0x18001caf5  cmp     ebx, dword ptr [rbp+57h+var_88+4]
0x18001caf8  jz      loc_18001D006
0x18001cafe  mov     rdx, [rbp+57h+var_A0]
0x18001cb02  mov     [rbp+57h+var_A0], r13
0x18001cb06  mov     eax, ebx
0x18001cb08  lea     rcx, [rax+rax*2]
0x18001cb0c  mov     rax, [rbp+57h+var_90]
0x18001cb10  mov     [rax+rcx*8], rdx
0x18001cb14  mov     dword ptr [rax+rcx*8+8], 0Dh
0x18001cb1c  mov     [rax+rcx*8+10h], r13d
0x18001cb21  inc     ebx
0x18001cb23  mov     dword ptr [rbp+57h+var_88], ebx
0x18001cb26  mov     dword ptr [rbp+57h+var_80+4], r13d
0x18001cb2a  mov     rcx, [rbp+57h+var_A0]; pSid
0x18001cb2e  test    rcx, rcx
0x18001cb31  jnz     loc_18001D023
0x18001cb37  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], 0
0x18001cb3e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001cb44  mov     [rbp+57h+var_A0], r13
0x18001cb48  test    r15d, r15d
0x18001cb4b  jz      loc_18001CEF6
0x18001cb51  mov     dword ptr [rbp+57h+var_80+4], 1
0x18001cb58  lea     rax, [rbp+57h+var_A0]
0x18001cb5c  mov     [rsp+100h+pSid], rax; pSid
0x18001cb61  mov     [rsp+100h+nSubAuthority7], r13d; nSubAuthority7
0x18001cb66  mov     [rsp+100h+nSubAuthority6], r13d; nSubAuthority6
0x18001cb6b  mov     [rsp+100h+nSubAuthority5], r13d; nSubAuthority5
0x18001cb70  mov     [rsp+100h+nSubAuthority4], r13d; nSubAuthority4
0x18001cb75  mov     [rsp+100h+nSubAuthority3], r13d; nSubAuthority3
0x18001cb7a  mov     [rsp+100h+nSubAuthority2], r13d; nSubAuthority2
0x18001cb7f  xor     r9d, r9d; nSubAuthority1
0x18001cb82  mov     r8d, 14h; nSubAuthority0
0x18001cb88  mov     dl, 1; nSubAuthorityCount
0x18001cb8a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001cb8e  call    cs:__imp_AllocateAndInitializeSid
0x18001cb94  test    eax, eax
0x18001cb96  jz      loc_18001CE8C
0x18001cb9c  cmp     ebx, dword ptr [rbp+57h+var_88+4]
0x18001cb9f  jz      loc_18001D02E
0x18001cba5  mov     rdx, [rbp+57h+var_A0]
0x18001cba9  mov     [rbp+57h+var_A0], r13
0x18001cbad  mov     eax, ebx
0x18001cbaf  lea     rcx, [rax+rax*2]
0x18001cbb3  mov     rax, [rbp+57h+var_90]
0x18001cbb7  mov     [rax+rcx*8], rdx
0x18001cbbb  mov     dword ptr [rax+rcx*8+8], 0Dh
0x18001cbc3  mov     [rax+rcx*8+10h], r13d
0x18001cbc8  inc     ebx
0x18001cbca  mov     dword ptr [rbp+57h+var_88], ebx
0x18001cbcd  mov     dword ptr [rbp+57h+var_80+4], r13d
0x18001cbd1  mov     rcx, [rbp+57h+var_A0]; pSid
0x18001cbd5  test    rcx, rcx
0x18001cbd8  jnz     loc_18001D04B
0x18001cbde  mov     [rbp+57h+pSourceSid], r13
0x18001cbe2  cmp     [rbp+57h+var_60], 0
0x18001cbe6  jnz     loc_18001CCFF
0x18001cbec  mov     rax, [r14+0B8h]
0x18001cbf3  lea     rdx, [rbp+57h+pSourceSid]
0x18001cbf7  lea     rcx, [r14+0B8h]
0x18001cbfe  mov     rax, [rax+48h]
0x18001cc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc07  mov     esi, eax
0x18001cc09  test    eax, eax
0x18001cc0b  jnz     loc_18001CE9E
0x18001cc11  test    r15d, r15d
0x18001cc14  jz      loc_18001CF6A
0x18001cc1a  mov     r15, [rbp+57h+pSourceSid]
0x18001cc1e  mov     dword ptr [rbp+57h+var_80+4], 1
0x18001cc25  mov     rcx, r15; pSid
0x18001cc28  call    cs:__imp_IsValidSid
0x18001cc2e  test    eax, eax
0x18001cc30  jz      loc_18001CF98
0x18001cc36  mov     rcx, r15; pSid
0x18001cc39  call    cs:__imp_GetLengthSid
0x18001cc3f  mov     r12d, eax
0x18001cc42  mov     edx, eax; uBytes
0x18001cc44  mov     ecx, 40h ; '@'; uFlags
0x18001cc49  call    cs:__imp_LocalAlloc
0x18001cc4f  mov     rdi, rax
0x18001cc52  mov     [rbp+57h+var_A0], rax
0x18001cc56  test    rax, rax
0x18001cc59  jz      loc_18001CFA1
0x18001cc5f  mov     r8, r15; pSourceSid
0x18001cc62  mov     rdx, rax; pDestinationSid
0x18001cc65  mov     ecx, r12d; nDestinationSidLength
0x18001cc68  call    cs:__imp_CopySid
0x18001cc6e  test    eax, eax
0x18001cc70  jz      loc_18001D081
0x18001cc76  lea     rcx, [rbx+rbx*2]
0x18001cc7a  mov     rax, [rbp+57h+var_90]
0x18001cc7e  mov     [rax+rcx*8], rdi
0x18001cc82  mov     dword ptr [rax+rcx*8+8], 0Dh
0x18001cc8a  mov     qword ptr [rax+rcx*8+0Ch], 1
0x18001cc93  inc     ebx
0x18001cc95  mov     dword ptr [rbp+57h+var_88], ebx
0x18001cc98  mov     dword ptr [rbp+57h+var_80+4], r13d
0x18001cc9c  mov     rcx, [rbp+57h+pSourceSid]; hMem
0x18001cca0  test    rcx, rcx
0x18001cca3  jz      short loc_18001CCAB
0x18001cca5  call    cs:__imp_LocalFree
0x18001ccab  lea     rcx, [rbp+57h+var_90]; this
0x18001ccaf  call    ?MakeSD@CSecDesc@@QEAAPEAU_SECURITY_DESCRIPTOR@@XZ; CSecDesc::MakeSD(void)
0x18001ccb4  mov     rbx, rax
0x18001ccb7  mov     rcx, [r14+1A0h]; hMem
0x18001ccbe  test    rcx, rcx
0x18001ccc1  jz      short loc_18001CCC9
0x18001ccc3  call    cs:__imp_LocalFree
0x18001ccc9  mov     [r14+1A0h], rbx
0x18001ccd0  test    rbx, rbx
0x18001ccd3  jz      loc_18001C99E
0x18001ccd9  mov     dword ptr [r14+1A8h], 5
0x18001cce4  mov     qword ptr [r14+1ACh], 8
0x18001ccef  mov     dword ptr [r14+1B4h], 0Dh
0x18001ccfa  jmp     loc_18001C9A6
0x18001ccff  mov     dword ptr [rbp+57h+Data], r13d
0x18001cd03  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x18001cd07  mov     [rbp+57h+cbData], r13d
0x18001cd0b  lea     rax, [rbp+57h+pSourceSid]
0x18001cd0f  mov     qword ptr [rsp+100h+nSubAuthority2], rax; phkResult
0x18001cd14  mov     r9d, 20019h; samDesired
0x18001cd1a  xor     r8d, r8d; ulOptions
0x18001cd1d  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001cd24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cd2b  call    cs:__imp_RegOpenKeyExW
0x18001cd31  test    eax, eax
0x18001cd33  jz      loc_18001CEB6
0x18001cd39  lea     rax, [rbp+57h+pSourceSid]
0x18001cd3d  mov     qword ptr [rsp+100h+nSubAuthority2], rax; phkResult
0x18001cd42  mov     r9d, 20019h; samDesired
0x18001cd48  xor     r8d, r8d; ulOptions
0x18001cd4b  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18001cd52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cd59  call    cs:__imp_RegOpenKeyExW
0x18001cd5f  test    eax, eax
  ... truncated ...
```
