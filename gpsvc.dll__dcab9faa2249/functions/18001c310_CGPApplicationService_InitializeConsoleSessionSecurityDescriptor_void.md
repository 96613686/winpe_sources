# CGPApplicationService::InitializeConsoleSessionSecurityDescriptor(void)

- ea: `0x18001c310`
- end: `0x18001c846`
- name: `?InitializeConsoleSessionSecurityDescriptor@CGPApplicationService@@AEAAKXZ`
- size: `1334`
- prototype: `unsigned int __fastcall(CGPApplicationService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800112dc`

## callees

- `0x18001c310`
- `0x18001d0c0`
- `0x18001d220`
- `0x18001d380`
- `0x180072a08`
- `0x18007d320`
- `0x1800b5e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c804`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c732`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c804`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c352`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c66f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c72a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c66f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c6d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c72a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c3ee`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c4c8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c56c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c609`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c3ee`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c4c8`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c56c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001c609`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c722`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c7ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c7d2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c7f9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c82f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c83a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c722`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c7ab`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c7d2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c7f9`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c82f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001c83a`

## string_xrefs

- `0x18001c739`: `AddAdministrators: Failed to initialize sid.  Error = %d`
- `0x18001c74b`: `AddNetworkService: Failed to initialize sid.  Error = %d`
- `0x18001c757`: `AddNetworkService: Not initialised or failure.`
- `0x18001c80a`: `AddAuthUsers: Failed to initialize authenticated users sid.  Error = %d`
- `0x18001c3fe`: `AddLocalSystem: Failed to initialize sid.  Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGPApplicationService::InitializeConsoleSessionSecurityDescriptor(CGPApplicationService *this)
{
  int v2; // edi
  DWORD LastError; // eax
  DWORD v4; // ebx
  unsigned int v5; // ebx
  PSID v6; // rdx
  __int64 v7; // rcx
  _DWORD *v8; // rax
  unsigned int v9; // ebx
  PSID v10; // rdx
  __int64 v11; // rcx
  _DWORD *v12; // rax
  unsigned int v13; // ebx
  PSID v14; // rdx
  __int64 v15; // rcx
  _DWORD *v16; // rax
  unsigned int v17; // ebx
  PSID v18; // rdx
  __int64 v19; // rcx
  _DWORD *v20; // rax
  struct _SECURITY_DESCRIPTOR *SD; // rbx
  void *v22; // rcx
  unsigned int i; // edi
  void *v25; // rcx
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  PSID pSid; // [rsp+60h] [rbp-19h] BYREF
  HLOCAL v30; // [rsp+68h] [rbp-11h] BYREF
  __int64 v31; // [rsp+70h] [rbp-9h]
  __int64 v32; // [rsp+78h] [rbp-1h]
  HLOCAL hMem[2]; // [rsp+80h] [rbp+7h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+17h] BYREF

  v31 = 0;
  v32 = 0;
  *(_OWORD *)hMem = 0;
  v30 = LocalAlloc(0x40u, 0xF0u);
  if ( v30 )
  {
    HIDWORD(v31) = 10;
    LODWORD(v32) = 1;
  }
  if ( !(unsigned int)CSecDesc::AddAdministratorsAsOwner((CSecDesc *)&v30)
    || !(unsigned int)CSecDesc::AddAdministratorsAsGroup((CSecDesc *)&v30) )
  {
    goto LABEL_11;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v2 = v32;
  if ( !(_DWORD)v32 || HIDWORD(v32) )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddLocalSystem: Not initialised or failure.");
    goto LABEL_9;
  }
  HIDWORD(v32) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    LastError = GetLastError();
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgCommon,
      2u,
      L"AddLocalSystem: Failed to initialize sid.  Error = %d",
      LastError);
    goto LABEL_9;
  }
  v5 = v31;
  if ( (_DWORD)v31 == HIDWORD(v31) )
  {
    if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v30) )
      goto LABEL_9;
    v2 = v32;
    v5 = v31;
  }
  v6 = pSid;
  pSid = 0;
  v7 = 3LL * v5;
  v8 = v30;
  *((_QWORD *)v30 + v7) = v6;
  v8[2 * v7 + 2] = 5;
  v8[2 * v7 + 4] = 0;
  v9 = v5 + 1;
  LODWORD(v31) = v9;
  HIDWORD(v32) = 0;
  if ( pSid )
    FreeSid(pSid);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v2 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddNetworkService: Not initialised or failure.");
    goto LABEL_9;
  }
  HIDWORD(v32) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v27 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddNetworkService: Failed to initialize sid.  Error = %d", v27);
    goto LABEL_9;
  }
  if ( v9 == HIDWORD(v31) )
  {
    if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v30) )
      goto LABEL_9;
    v2 = v32;
    v9 = v31;
  }
  v10 = pSid;
  pSid = 0;
  v11 = 3LL * v9;
  v12 = v30;
  *((_QWORD *)v30 + v11) = v10;
  v12[2 * v11 + 2] = 4;
  v12[2 * v11 + 4] = 0;
  v13 = v9 + 1;
  LODWORD(v31) = v13;
  HIDWORD(v32) = 0;
  if ( pSid )
    FreeSid(pSid);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v2 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAdministrators: Not initialised or failure.");
    goto LABEL_9;
  }
  HIDWORD(v32) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v26 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAdministrators: Failed to initialize sid.  Error = %d", v26);
    goto LABEL_9;
  }
  if ( v13 == HIDWORD(v31) )
  {
    if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v30) )
      goto LABEL_9;
    v2 = v32;
    v13 = v31;
  }
  v14 = pSid;
  pSid = 0;
  v15 = 3LL * v13;
  v16 = v30;
  *((_QWORD *)v30 + v15) = v14;
  v16[2 * v15 + 2] = 1;
  v16[2 * v15 + 4] = 0;
  v17 = v13 + 1;
  LODWORD(v31) = v17;
  HIDWORD(v32) = 0;
  if ( pSid )
    FreeSid(pSid);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  if ( !v2 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgCommon, 2u, L"AddAuthUsers: Not initialised or failure.");
    goto LABEL_9;
  }
  HIDWORD(v32) = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v28 = GetLastError();
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgCommon,
      2u,
      L"AddAuthUsers: Failed to initialize authenticated users sid.  Error = %d",
      v28);
    goto LABEL_9;
  }
  if ( v17 != HIDWORD(v31) )
    goto LABEL_28;
  if ( !(unsigned int)CSecDesc::ReAllocSidList((CSecDesc *)&v30) )
  {
LABEL_9:
    if ( pSid )
      FreeSid(pSid);
    goto LABEL_11;
  }
  v17 = v31;
LABEL_28:
  v18 = pSid;
  pSid = 0;
  v19 = 3LL * v17;
  v20 = v30;
  *((_QWORD *)v30 + v19) = v18;
  v20[2 * v19 + 2] = 1;
  v20[2 * v19 + 4] = 0;
  LODWORD(v31) = v17 + 1;
  HIDWORD(v32) = 0;
  if ( pSid )
    FreeSid(pSid);
  SD = CSecDesc::MakeSD((CSecDesc *)&v30);
  v22 = (void *)*((_QWORD *)this + 36);
  if ( v22 )
    LocalFree(v22);
  *((_QWORD *)this + 36) = SD;
  if ( SD )
  {
    v4 = 0;
    *((_QWORD *)this + 37) = 5;
    *((_DWORD *)this + 76) = 0;
    *((_DWORD *)this + 77) = 5;
    goto LABEL_34;
  }
LABEL_11:
  v4 = GetLastError();
LABEL_34:
  if ( v30 )
  {
    for ( i = 0; i < HIDWORD(v31); ++i )
    {
      v25 = (void *)*((_QWORD *)v30 + 3 * i);
      if ( v25 )
      {
        if ( *((_DWORD *)v30 + 6 * i + 3) )
          LocalFree(v25);
        else
          FreeSid(v25);
      }
    }
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v30 )
    LocalFree(v30);
  return v4;
}

```

## disassembly

```asm
0x18001c310  push    rbp
0x18001c312  push    rbx
0x18001c313  push    rsi
0x18001c314  push    rdi
0x18001c315  push    r12
0x18001c317  push    r14
0x18001c319  lea     rbp, [rsp-2Fh]
0x18001c31e  sub     rsp, 0A8h
0x18001c325  mov     rax, cs:__security_cookie
0x18001c32c  xor     rax, rsp
0x18001c32f  mov     [rbp+57h+var_38], rax
0x18001c333  mov     rsi, rcx
0x18001c336  xor     r14d, r14d
0x18001c339  mov     [rbp+57h+var_60], r14
0x18001c33d  mov     [rbp+57h+var_58], r14
0x18001c341  xorps   xmm0, xmm0
0x18001c344  movdqu  xmmword ptr [rbp+57h+hMem], xmm0
0x18001c349  mov     edx, 0F0h; uBytes
0x18001c34e  lea     ecx, [r14+40h]; uFlags
0x18001c352  call    cs:__imp_LocalAlloc
0x18001c358  mov     [rbp+57h+var_68], rax
0x18001c35c  lea     r12d, [r14+1]
0x18001c360  test    rax, rax
0x18001c363  jz      short loc_18001C370
0x18001c365  mov     dword ptr [rbp+57h+var_60+4], 0Ah
0x18001c36c  mov     dword ptr [rbp+57h+var_58], r12d
0x18001c370  lea     rcx, [rbp+57h+var_68]; this
0x18001c374  call    ?AddAdministratorsAsOwner@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsOwner(void)
0x18001c379  test    eax, eax
0x18001c37b  jz      loc_18001C426
0x18001c381  lea     rcx, [rbp+57h+var_68]; this
0x18001c385  call    ?AddAdministratorsAsGroup@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsGroup(void)
0x18001c38a  test    eax, eax
0x18001c38c  jz      loc_18001C426
0x18001c392  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001c396  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001c39c  mov     [rbp+57h+var_70], r14
0x18001c3a0  mov     edi, dword ptr [rbp+57h+var_58]
0x18001c3a3  test    edi, edi
0x18001c3a5  jz      loc_18001C77D
0x18001c3ab  cmp     dword ptr [rbp+57h+var_58+4], r14d
0x18001c3af  jnz     loc_18001C77D
0x18001c3b5  mov     dword ptr [rbp+57h+var_58+4], r12d
0x18001c3b9  lea     rax, [rbp+57h+var_70]
0x18001c3bd  mov     [rsp+0D0h+pSid], rax; pSid
0x18001c3c2  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x18001c3c7  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x18001c3cc  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x18001c3d1  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x18001c3d6  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x18001c3db  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x18001c3e0  xor     r9d, r9d; nSubAuthority1
0x18001c3e3  lea     r8d, [r9+12h]; nSubAuthority0
0x18001c3e7  mov     dl, r12b; nSubAuthorityCount
0x18001c3ea  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001c3ee  call    cs:__imp_AllocateAndInitializeSid
0x18001c3f4  test    eax, eax
0x18001c3f6  jnz     short loc_18001C433
0x18001c3f8  call    cs:__imp_GetLastError
0x18001c3fe  lea     r8, aAddlocalsystem_0; "AddLocalSystem: Failed to initialize si"...
0x18001c405  mov     r9d, eax
0x18001c408  mov     edx, 2; unsigned int
0x18001c40d  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001c414  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001c419  mov     rcx, [rbp+57h+var_70]; pSid
0x18001c41d  test    rcx, rcx
0x18001c420  jnz     loc_18001C83A
0x18001c426  call    cs:__imp_GetLastError
0x18001c42c  mov     ebx, eax
0x18001c42e  jmp     loc_18001C6A4
0x18001c433  mov     ebx, dword ptr [rbp+57h+var_60]
0x18001c436  cmp     ebx, dword ptr [rbp+57h+var_60+4]
0x18001c439  jz      loc_18001C78F
0x18001c43f  mov     rdx, [rbp+57h+var_70]
0x18001c443  mov     [rbp+57h+var_70], r14
0x18001c447  mov     eax, ebx
0x18001c449  lea     rcx, [rax+rax*2]
0x18001c44d  mov     rax, [rbp+57h+var_68]
0x18001c451  mov     [rax+rcx*8], rdx
0x18001c455  mov     dword ptr [rax+rcx*8+8], 5
0x18001c45d  mov     [rax+rcx*8+10h], r14d
0x18001c462  add     ebx, r12d
0x18001c465  mov     dword ptr [rbp+57h+var_60], ebx
0x18001c468  mov     dword ptr [rbp+57h+var_58+4], r14d
0x18001c46c  mov     rcx, [rbp+57h+var_70]; pSid
0x18001c470  test    rcx, rcx
0x18001c473  jnz     loc_18001C7AB
0x18001c479  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001c47d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001c483  mov     [rbp+57h+var_70], r14
0x18001c487  test    edi, edi
0x18001c489  jz      loc_18001C757
0x18001c48f  mov     dword ptr [rbp+57h+var_58+4], r12d
0x18001c493  lea     rax, [rbp+57h+var_70]
0x18001c497  mov     [rsp+0D0h+pSid], rax; pSid
0x18001c49c  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x18001c4a1  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x18001c4a6  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x18001c4ab  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x18001c4b0  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x18001c4b5  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x18001c4ba  xor     r9d, r9d; nSubAuthority1
0x18001c4bd  lea     r8d, [r9+14h]; nSubAuthority0
0x18001c4c1  mov     dl, r12b; nSubAuthorityCount
0x18001c4c4  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001c4c8  call    cs:__imp_AllocateAndInitializeSid
0x18001c4ce  test    eax, eax
0x18001c4d0  jz      loc_18001C745
0x18001c4d6  cmp     ebx, dword ptr [rbp+57h+var_60+4]
0x18001c4d9  jz      loc_18001C7B6
0x18001c4df  mov     rdx, [rbp+57h+var_70]
0x18001c4e3  mov     [rbp+57h+var_70], r14
0x18001c4e7  mov     eax, ebx
0x18001c4e9  lea     rcx, [rax+rax*2]
0x18001c4ed  mov     rax, [rbp+57h+var_68]
0x18001c4f1  mov     [rax+rcx*8], rdx
0x18001c4f5  mov     dword ptr [rax+rcx*8+8], 4
0x18001c4fd  mov     [rax+rcx*8+10h], r14d
0x18001c502  add     ebx, r12d
0x18001c505  mov     dword ptr [rbp+57h+var_60], ebx
0x18001c508  mov     dword ptr [rbp+57h+var_58+4], r14d
0x18001c50c  mov     rcx, [rbp+57h+var_70]; pSid
0x18001c510  test    rcx, rcx
0x18001c513  jnz     loc_18001C7D2
0x18001c519  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001c51d  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001c523  mov     [rbp+57h+var_70], r14
0x18001c527  test    edi, edi
0x18001c529  jz      loc_18001C786
0x18001c52f  mov     dword ptr [rbp+57h+var_58+4], r12d
0x18001c533  lea     rax, [rbp+57h+var_70]
0x18001c537  mov     [rsp+0D0h+pSid], rax; pSid
0x18001c53c  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x18001c541  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x18001c546  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x18001c54b  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x18001c550  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x18001c555  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x18001c55a  mov     r9d, 220h; nSubAuthority1
0x18001c560  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001c566  mov     dl, 2; nSubAuthorityCount
0x18001c568  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001c56c  call    cs:__imp_AllocateAndInitializeSid
0x18001c572  test    eax, eax
0x18001c574  jz      loc_18001C732
0x18001c57a  cmp     ebx, dword ptr [rbp+57h+var_60+4]
0x18001c57d  jz      loc_18001C7DD
0x18001c583  mov     rdx, [rbp+57h+var_70]
0x18001c587  mov     [rbp+57h+var_70], r14
0x18001c58b  mov     eax, ebx
0x18001c58d  lea     rcx, [rax+rax*2]
0x18001c591  mov     rax, [rbp+57h+var_68]
0x18001c595  mov     [rax+rcx*8], rdx
0x18001c599  mov     [rax+rcx*8+8], r12d
0x18001c59e  mov     [rax+rcx*8+10h], r14d
0x18001c5a3  add     ebx, r12d
0x18001c5a6  mov     dword ptr [rbp+57h+var_60], ebx
0x18001c5a9  mov     dword ptr [rbp+57h+var_58+4], r14d
0x18001c5ad  mov     rcx, [rbp+57h+var_70]; pSid
0x18001c5b1  test    rcx, rcx
0x18001c5b4  jnz     loc_18001C7F9
0x18001c5ba  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18001c5be  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001c5c4  mov     [rbp+57h+var_70], r14
0x18001c5c8  test    edi, edi
0x18001c5ca  jz      loc_18001C774
0x18001c5d0  mov     dword ptr [rbp+57h+var_58+4], r12d
0x18001c5d4  lea     rax, [rbp+57h+var_70]
0x18001c5d8  mov     [rsp+0D0h+pSid], rax; pSid
0x18001c5dd  mov     [rsp+0D0h+nSubAuthority7], r14d; nSubAuthority7
0x18001c5e2  mov     [rsp+0D0h+nSubAuthority6], r14d; nSubAuthority6
0x18001c5e7  mov     [rsp+0D0h+nSubAuthority5], r14d; nSubAuthority5
0x18001c5ec  mov     [rsp+0D0h+nSubAuthority4], r14d; nSubAuthority4
0x18001c5f1  mov     [rsp+0D0h+nSubAuthority3], r14d; nSubAuthority3
0x18001c5f6  mov     [rsp+0D0h+nSubAuthority2], r14d; nSubAuthority2
0x18001c5fb  xor     r9d, r9d; nSubAuthority1
0x18001c5fe  lea     r8d, [r9+0Bh]; nSubAuthority0
0x18001c602  mov     dl, r12b; nSubAuthorityCount
0x18001c605  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001c609  call    cs:__imp_AllocateAndInitializeSid
0x18001c60f  test    eax, eax
0x18001c611  jz      loc_18001C804
0x18001c617  cmp     ebx, dword ptr [rbp+57h+var_60+4]
0x18001c61a  jz      loc_18001C816
0x18001c620  mov     rdx, [rbp+57h+var_70]
0x18001c624  mov     [rbp+57h+var_70], r14
0x18001c628  mov     eax, ebx
0x18001c62a  lea     rcx, [rax+rax*2]
0x18001c62e  mov     rax, [rbp+57h+var_68]
0x18001c632  mov     [rax+rcx*8], rdx
0x18001c636  mov     [rax+rcx*8+8], r12d
0x18001c63b  mov     [rax+rcx*8+10h], r14d
0x18001c640  add     ebx, r12d
0x18001c643  mov     dword ptr [rbp+57h+var_60], ebx
0x18001c646  mov     dword ptr [rbp+57h+var_58+4], r14d
0x18001c64a  mov     rcx, [rbp+57h+var_70]; pSid
0x18001c64e  test    rcx, rcx
0x18001c651  jnz     loc_18001C82F
0x18001c657  lea     rcx, [rbp+57h+var_68]; this
0x18001c65b  call    ?MakeSD@CSecDesc@@QEAAPEAU_SECURITY_DESCRIPTOR@@XZ; CSecDesc::MakeSD(void)
0x18001c660  mov     rbx, rax
0x18001c663  mov     rcx, [rsi+120h]; hMem
0x18001c66a  test    rcx, rcx
0x18001c66d  jz      short loc_18001C675
0x18001c66f  call    cs:__imp_LocalFree
0x18001c675  mov     [rsi+120h], rbx
0x18001c67c  test    rbx, rbx
0x18001c67f  jz      loc_18001C426
0x18001c685  mov     ebx, r14d
0x18001c688  mov     qword ptr [rsi+128h], 5
0x18001c693  mov     [rsi+130h], r14d
0x18001c69a  mov     dword ptr [rsi+134h], 5
0x18001c6a4  cmp     [rbp+57h+var_68], r14
0x18001c6a8  jnz     short loc_18001C6F5
0x18001c6aa  mov     rcx, [rbp+57h+hMem+8]; hMem
0x18001c6ae  test    rcx, rcx
0x18001c6b1  jz      short loc_18001C6B9
0x18001c6b3  call    cs:__imp_LocalFree
0x18001c6b9  mov     rcx, [rbp+57h+hMem]; hMem
0x18001c6bd  test    rcx, rcx
0x18001c6c0  jz      short loc_18001C6C8
0x18001c6c2  call    cs:__imp_LocalFree
0x18001c6c8  mov     rcx, [rbp+57h+var_68]; hMem
0x18001c6cc  test    rcx, rcx
0x18001c6cf  jz      short loc_18001C6D7
0x18001c6d1  call    cs:__imp_LocalFree
0x18001c6d7  mov     eax, ebx
0x18001c6d9  mov     rcx, [rbp+57h+var_38]
0x18001c6dd  xor     rcx, rsp; StackCookie
0x18001c6e0  call    __security_check_cookie
0x18001c6e5  add     rsp, 0A8h
0x18001c6ec  pop     r14
0x18001c6ee  pop     r12
0x18001c6f0  pop     rdi
0x18001c6f1  pop     rsi
0x18001c6f2  pop     rbx
0x18001c6f3  pop     rbp
0x18001c6f4  retn
0x18001c6f5  mov     edi, r14d
0x18001c6f8  cmp     dword ptr [rbp+57h+var_60+4], r14d
0x18001c6fc  jbe     short loc_18001C6AA
0x18001c6fe  mov     eax, edi
0x18001c700  lea     rdx, [rax+rax*2]
0x18001c704  mov     rax, [rbp+57h+var_68]
0x18001c708  mov     rcx, [rax+rdx*8]; hMem
0x18001c70c  test    rcx, rcx
0x18001c70f  jnz     short loc_18001C71B
0x18001c711  add     edi, r12d
0x18001c714  cmp     edi, dword ptr [rbp+57h+var_60+4]
0x18001c717  jb      short loc_18001C6FE
0x18001c719  jmp     short loc_18001C6AA
0x18001c71b  cmp     [rax+rdx*8+0Ch], r14d
0x18001c720  jnz     short loc_18001C72A
0x18001c722  call    cs:__imp_FreeSid
0x18001c728  jmp     short loc_18001C711
0x18001c72a  call    cs:__imp_LocalFree
0x18001c730  jmp     short loc_18001C711
0x18001c732  call    cs:__imp_GetLastError
0x18001c738  nop
0x18001c739  lea     r8, aAddadministrat_0; "AddAdministrators: Failed to initialize"...
0x18001c740  jmp     loc_18001C405
0x18001c745  call    cs:__imp_GetLastError
0x18001c74b  lea     r8, aAddnetworkserv; "AddNetworkService: Failed to initialize"...
0x18001c752  jmp     loc_18001C405
0x18001c757  lea     r8, aAddnetworkserv_0; "AddNetworkService: Not initialised or f"...
0x18001c75e  mov     edx, 2; unsigned int
0x18001c763  lea     rcx, ?dbgCommon@@3VCDebugWrapper@@A; this
0x18001c76a  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18001c76f  jmp     loc_18001C419
0x18001c774  lea     r8, aAddauthusersNo; "AddAuthUsers: Not initialised or failur"...
0x18001c77b  jmp     short loc_18001C75E
0x18001c77d  lea     r8, aAddlocalsystem; "AddLocalSystem: Not initialised or fail"...
0x18001c784  jmp     short loc_18001C75E
0x18001c786  lea     r8, aAddadministrat; "AddAdministrators: Not initialised or f"...
0x18001c78d  jmp     short loc_18001C75E
0x18001c78f  lea     rcx, [rbp+57h+var_68]; this
0x18001c793  call    ?ReAllocSidList@CSecDesc@@AEAAHXZ; CSecDesc::ReAllocSidList(void)
0x18001c798  test    eax, eax
0x18001c79a  jz      loc_18001C419
0x18001c7a0  mov     edi, dword ptr [rbp+57h+var_58]
0x18001c7a3  mov     ebx, dword ptr [rbp+57h+var_60]
0x18001c7a6  jmp     loc_18001C43F
0x18001c7ab  call    cs:__imp_FreeSid
0x18001c7b1  jmp     loc_18001C479
0x18001c7b6  lea     rcx, [rbp+57h+var_68]; this
0x18001c7ba  call    ?ReAllocSidList@CSecDesc@@AEAAHXZ; CSecDesc::ReAllocSidList(void)
0x18001c7bf  test    eax, eax
0x18001c7c1  jz      loc_18001C419
0x18001c7c7  mov     edi, dword ptr [rbp+57h+var_58]
0x18001c7ca  mov     ebx, dword ptr [rbp+57h+var_60]
0x18001c7cd  jmp     loc_18001C4DF
0x18001c7d2  call    cs:__imp_FreeSid
0x18001c7d8  jmp     loc_18001C519
0x18001c7dd  lea     rcx, [rbp+57h+var_68]; this
0x18001c7e1  call    ?ReAllocSidList@CSecDesc@@AEAAHXZ; CSecDesc::ReAllocSidList(void)
0x18001c7e6  test    eax, eax
0x18001c7e8  jz      loc_18001C419
0x18001c7ee  mov     edi, dword ptr [rbp+57h+var_58]
0x18001c7f1  mov     ebx, dword ptr [rbp+57h+var_60]
0x18001c7f4  jmp     loc_18001C583
  ... truncated ...
```
