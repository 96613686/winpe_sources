# Rdp::Security::InitializeIddSecurityAttr(_SECURITY_ATTRIBUTES *,int)

- ea: `0x1800c5724`
- end: `0x1800c5d54`
- name: `?InitializeIddSecurityAttr@Security@Rdp@@YAJPEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `1584`
- prototype: `__int64 __fastcall(Rdp::Security *this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b620`
- `0x1800c1df0`

## callees

- `0x1800015f0`
- `0x180033da0`
- `0x1800c5724`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c57b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5c46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c57b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c58ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5ad1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5b92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5c46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5d1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5d2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5d0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5d1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c5d2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c5952`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c5b80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c5952`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c5b80`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800c5a0c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800c5a0c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800c5ac3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800c5ac3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800c5b70`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800c5b70`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800c5c38`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800c5c38`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800c57a1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800c57a1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c5cfd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800c5cfd`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800c58a0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800c58a0`

## string_xrefs

- `0x1800c57de`: `Failed to allocate LOCAL SERVICE sid`
- `0x1800c5805`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c58fe`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c59b4`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c5a6a`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c5b21`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c5be2`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c5c96`: `clientcore\termsrv\rdpplatform\gfxpipe\gfxsource\security.cpp`
- `0x1800c57f7`: `InitializeIddSecurityAttr`
- `0x1800c58f0`: `InitializeIddSecurityAttr`
- `0x1800c59a6`: `InitializeIddSecurityAttr`
- `0x1800c5a5c`: `InitializeIddSecurityAttr`
- `0x1800c5b13`: `InitializeIddSecurityAttr`
- `0x1800c5bd4`: `InitializeIddSecurityAttr`
- `0x1800c5c88`: `InitializeIddSecurityAttr`
- `0x1800c598d`: `Failed to allocate security descriptor`
- `0x1800c58d7`: `SetEntriesInAcl failed`
- `0x1800c5afa`: `SetSecurityDescriptorDacl failed`
- `0x1800c5a43`: `InitializeSecurityDescriptor failed`

## pseudocode

```c
__int64 __fastcall Rdp::Security::InitializeIddSecurityAttr(Rdp::Security *this, struct _SECURITY_ATTRIBUTES *a2)
{
  int v2; // r15d
  HLOCAL v4; // rdi
  HLOCAL v5; // rsi
  signed int LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  signed int v10; // ebx
  signed int v11; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  signed int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  signed int v19; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  signed int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  signed int v27; // eax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  signed int v31; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v36; // [rsp+60h] [rbp-69h] BYREF
  int v37; // [rsp+64h] [rbp-65h] BYREF
  const char *v38; // [rsp+68h] [rbp-61h] BYREF
  const char *v39; // [rsp+70h] [rbp-59h] BYREF
  const char *v40; // [rsp+78h] [rbp-51h] BYREF
  const char *v41; // [rsp+80h] [rbp-49h] BYREF
  DWORD dwBufferLength; // [rsp+88h] [rbp-41h] BYREF
  PSID pSid; // [rsp+90h] [rbp-39h] BYREF
  PACL NewAcl; // [rsp+98h] [rbp-31h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+A0h] [rbp-29h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp+7h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v2 = (int)a2;
  v4 = 0;
  NewAcl = 0;
  v5 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_8;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_8:
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    pListOfExplicitEntries.grfAccessPermissions = v2 != 0 ? 0x10000000 : -1073741824;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    if ( !SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl) )
      goto LABEL_14;
    v11 = GetLastError();
    v10 = v11;
    if ( v11 > 0 )
      v10 = (unsigned __int16)v11 | 0x80070000;
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v37 = 77;
        v41 = "SetEntriesInAcl failed";
        v36 = v10;
        v40 = "InitializeIddSecurityAttr";
        v39 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
        v38 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v12,
          (unsigned int)byte_1801A9803,
          v13,
          v14,
          (__int64)&v38,
          (__int64)&v36,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v40,
          (__int64)&v41);
      }
    }
    else
    {
LABEL_14:
      v4 = LocalAlloc(0x40u, 0x28u);
      if ( v4 )
        goto LABEL_23;
      v15 = GetLastError();
      v10 = v15;
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_23:
        if ( InitializeSecurityDescriptor(v4, 1u) )
          goto LABEL_29;
        v19 = GetLastError();
        v10 = v19;
        if ( v19 > 0 )
          v10 = (unsigned __int16)v19 | 0x80070000;
        if ( v10 >= 0 )
        {
LABEL_29:
          if ( SetSecurityDescriptorDacl(v4, 1, NewAcl, 0) )
            goto LABEL_32;
          v23 = GetLastError();
          v10 = v23;
          if ( v23 > 0 )
            v10 = (unsigned __int16)v23 | 0x80070000;
          if ( v10 >= 0 )
          {
LABEL_32:
            dwBufferLength = GetSecurityDescriptorLength(v4);
            v5 = LocalAlloc(0x40u, dwBufferLength);
            if ( v5 )
              goto LABEL_41;
            v27 = GetLastError();
            v10 = v27;
            if ( v27 > 0 )
              v10 = (unsigned __int16)v27 | 0x80070000;
            if ( v10 >= 0 )
            {
LABEL_41:
              if ( MakeSelfRelativeSD(v4, v5, &dwBufferLength) )
                goto LABEL_44;
              v31 = GetLastError();
              v10 = v31;
              if ( v31 > 0 )
                v10 = (unsigned __int16)v31 | 0x80070000;
              if ( v10 >= 0 )
              {
LABEL_44:
                *(_DWORD *)this = 24;
                v10 = 0;
                *((_QWORD *)this + 1) = v5;
                *((_DWORD *)this + 4) = 0;
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                v37 = 125;
                v41 = "MakeSelfRelativeSD failed";
                v36 = v10;
                v40 = "InitializeIddSecurityAttr";
                v39 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
                v38 = "Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v32,
                  (unsigned int)&byte_1801A9617,
                  v33,
                  v34,
                  (__int64)&v38,
                  (__int64)&v36,
                  (__int64)&v39,
                  (__int64)&v37,
                  (__int64)&v40,
                  (__int64)&v41);
              }
            }
            else if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v37 = 119;
              v41 = "Failed to allocate memory for self-relative SD";
              v36 = v10;
              v40 = "InitializeIddSecurityAttr";
              v39 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
              v38 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v28,
                (unsigned int)byte_1801A96BB,
                v29,
                v30,
                (__int64)&v38,
                (__int64)&v36,
                (__int64)&v39,
                (__int64)&v37,
                (__int64)&v40,
                (__int64)&v41);
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v37 = 107;
            v41 = "SetSecurityDescriptorDacl failed";
            v36 = v10;
            v40 = "InitializeIddSecurityAttr";
            v39 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
            v38 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v24,
              (unsigned int)byte_1801A9669,
              v25,
              v26,
              (__int64)&v38,
              (__int64)&v36,
              (__int64)&v39,
              (__int64)&v37,
              (__int64)&v40,
              (__int64)&v41);
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v37 = 95;
          v41 = "InitializeSecurityDescriptor failed";
          v36 = v10;
          v40 = "InitializeIddSecurityAttr";
          v39 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
          v38 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v20,
            (unsigned int)&byte_1801A975F,
            v21,
            v22,
            (__int64)&v38,
            (__int64)&v36,
            (__int64)&v39,
            (__int64)&v37,
            (__int64)&v40,
            (__int64)&v41);
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v37 = 88;
        v41 = "Failed to allocate security descriptor";
        v36 = v10;
        v40 = "InitializeIddSecurityAttr";
        v39 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
        v38 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v16,
          (unsigned int)byte_1801A970D,
          v17,
          v18,
          (__int64)&v38,
          (__int64)&v36,
          (__int64)&v39,
          (__int64)&v37,
          (__int64)&v40,
          (__int64)&v41);
      }
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v36 = 54;
    v38 = "Failed to allocate LOCAL SERVICE sid";
    v37 = v10;
    v39 = "InitializeIddSecurityAttr";
    v40 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\security.cpp";
    v41 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v7,
      (unsigned int)byte_1801A97B1,
      v8,
      v9,
      (__int64)&v41,
      (__int64)&v37,
      (__int64)&v40,
      (__int64)&v36,
      (__int64)&v39,
      (__int64)&v38);
  }
  if ( pSid )
    FreeSid(pSid);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v4 )
    LocalFree(v4);
  if ( v10 < 0 && v5 )
    LocalFree(v5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800c5724  push    rbp
0x1800c5726  push    rbx
0x1800c5727  push    rsi
0x1800c5728  push    rdi
0x1800c5729  push    r12
0x1800c572b  push    r13
0x1800c572d  push    r14
0x1800c572f  push    r15
0x1800c5731  lea     rbp, [rsp-1Fh]
0x1800c5736  sub     rsp, 0E8h
0x1800c573d  mov     rax, cs:__security_cookie
0x1800c5744  xor     rax, rsp
0x1800c5747  mov     [rbp+57h+var_48], rax
0x1800c574b  xor     r12d, r12d
0x1800c574e  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800c5754  lea     rax, [rbp+57h+var_90]
0x1800c5758  mov     [rbp+57h+var_90], r12
0x1800c575c  mov     [rsp+120h+pSid], rax; pSid
0x1800c5761  mov     r15d, edx
0x1800c5764  mov     [rsp+120h+nSubAuthority7], r12d; nSubAuthority7
0x1800c5769  mov     r14, rcx
0x1800c576c  mov     [rsp+120h+nSubAuthority6], r12d; nSubAuthority6
0x1800c5771  lea     r8d, [r12+13h]; nSubAuthority0
0x1800c5776  mov     [rsp+120h+nSubAuthority5], r12d; nSubAuthority5
0x1800c577b  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800c577f  mov     [rsp+120h+nSubAuthority4], r12d; nSubAuthority4
0x1800c5784  xor     r9d, r9d; nSubAuthority1
0x1800c5787  mov     [rsp+120h+nSubAuthority3], r12d; nSubAuthority3
0x1800c578c  mov     dl, 1; nSubAuthorityCount
0x1800c578e  mov     [rsp+120h+nSubAuthority2], r12d; nSubAuthority2
0x1800c5793  mov     edi, r12d
0x1800c5796  mov     [rbp+57h+NewAcl], r12
0x1800c579a  mov     esi, r12d
0x1800c579d  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1800c57a1  call    cs:__imp_AllocateAndInitializeSid
0x1800c57a7  mov     r13d, 80070000h
0x1800c57ad  test    eax, eax
0x1800c57af  jnz     loc_1800C585B
0x1800c57b5  call    cs:__imp_GetLastError
0x1800c57bb  mov     ebx, eax
0x1800c57bd  test    eax, eax
0x1800c57bf  jle     short loc_1800C57C7
0x1800c57c1  movzx   ebx, ax
0x1800c57c4  or      ebx, r13d
0x1800c57c7  test    ebx, ebx
0x1800c57c9  jns     loc_1800C585B
0x1800c57cf  mov     eax, cs:dword_1801B76C8
0x1800c57d5  cmp     eax, 2
0x1800c57d8  jbe     loc_1800C5CF4
0x1800c57de  lea     rax, aFailedToAlloca_7; "Failed to allocate LOCAL SERVICE sid"
0x1800c57e5  mov     [rbp+57h+var_C0], 36h ; '6'
0x1800c57ec  mov     [rbp+57h+var_B8], rax
0x1800c57f0  lea     rdx, byte_1801A97B1
0x1800c57f7  lea     rax, aInitializeidds; "InitializeIddSecurityAttr"
0x1800c57fe  mov     [rbp+57h+var_BC], ebx
0x1800c5801  mov     [rbp+57h+var_B0], rax
0x1800c5805  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c580c  mov     [rbp+57h+var_A8], rax
0x1800c5810  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c5817  mov     [rbp+57h+var_A0], rax
0x1800c581b  lea     rax, [rbp+57h+var_B8]
0x1800c581f  mov     qword ptr [rsp+120h+nSubAuthority7], rax
0x1800c5824  lea     rax, [rbp+57h+var_B0]
0x1800c5828  mov     qword ptr [rsp+120h+nSubAuthority6], rax
0x1800c582d  lea     rax, [rbp+57h+var_C0]
0x1800c5831  mov     qword ptr [rsp+120h+nSubAuthority5], rax
0x1800c5836  lea     rax, [rbp+57h+var_A8]
0x1800c583a  mov     qword ptr [rsp+120h+nSubAuthority4], rax
0x1800c583f  lea     rax, [rbp+57h+var_BC]
0x1800c5843  mov     qword ptr [rsp+120h+nSubAuthority3], rax
0x1800c5848  lea     rax, [rbp+57h+var_A0]
0x1800c584c  mov     qword ptr [rsp+120h+nSubAuthority2], rax
0x1800c5851  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c5856  jmp     loc_1800C5CF4
0x1800c585b  xorps   xmm0, xmm0
0x1800c585e  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x1800c5866  neg     r15d
0x1800c5869  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x1800c5871  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800c5875  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x1800c5879  sbb     eax, eax
0x1800c587b  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800c587f  and     eax, 50000000h
0x1800c5884  xor     r8d, r8d; OldAcl
0x1800c5887  add     eax, 0C0000000h
0x1800c588c  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], eax
0x1800c588f  mov     rax, [rbp+57h+var_90]
0x1800c5893  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x1800c5897  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800c589b  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x1800c58a0  call    cs:__imp_SetEntriesInAclW
0x1800c58a6  test    eax, eax
0x1800c58a8  jz      loc_1800C594A
0x1800c58ae  call    cs:__imp_GetLastError
0x1800c58b4  mov     ebx, eax
0x1800c58b6  test    eax, eax
0x1800c58b8  jle     short loc_1800C58C0
0x1800c58ba  movzx   ebx, ax
0x1800c58bd  or      ebx, r13d
0x1800c58c0  test    ebx, ebx
0x1800c58c2  jns     loc_1800C594A
0x1800c58c8  mov     eax, cs:dword_1801B76C8
0x1800c58ce  cmp     eax, 2
0x1800c58d1  jbe     loc_1800C5CF4
0x1800c58d7  lea     rax, aSetentriesinac_0; "SetEntriesInAcl failed"
0x1800c58de  mov     [rbp+57h+var_BC], 4Dh ; 'M'
0x1800c58e5  mov     [rbp+57h+var_A0], rax
0x1800c58e9  lea     rdx, byte_1801A9803
0x1800c58f0  lea     rax, aInitializeidds; "InitializeIddSecurityAttr"
0x1800c58f7  mov     [rbp+57h+var_C0], ebx
0x1800c58fa  mov     [rbp+57h+var_A8], rax
0x1800c58fe  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c5905  mov     [rbp+57h+var_B0], rax
0x1800c5909  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c5910  mov     [rbp+57h+var_B8], rax
0x1800c5914  lea     rax, [rbp+57h+var_A0]
0x1800c5918  mov     qword ptr [rsp+120h+nSubAuthority7], rax
0x1800c591d  lea     rax, [rbp+57h+var_A8]
0x1800c5921  mov     qword ptr [rsp+120h+nSubAuthority6], rax
0x1800c5926  lea     rax, [rbp+57h+var_BC]
0x1800c592a  mov     qword ptr [rsp+120h+nSubAuthority5], rax
0x1800c592f  lea     rax, [rbp+57h+var_B0]
0x1800c5933  mov     qword ptr [rsp+120h+nSubAuthority4], rax
0x1800c5938  lea     rax, [rbp+57h+var_C0]
0x1800c593c  mov     qword ptr [rsp+120h+nSubAuthority3], rax
0x1800c5941  lea     rax, [rbp+57h+var_B8]
0x1800c5945  jmp     loc_1800C584C
0x1800c594a  mov     edx, 28h ; '('; uBytes
0x1800c594f  lea     ecx, [rdx+18h]; uFlags
0x1800c5952  call    cs:__imp_LocalAlloc
0x1800c5958  mov     rdi, rax
0x1800c595b  test    rax, rax
0x1800c595e  jnz     loc_1800C5A00
0x1800c5964  call    cs:__imp_GetLastError
0x1800c596a  mov     ebx, eax
0x1800c596c  test    eax, eax
0x1800c596e  jle     short loc_1800C5976
0x1800c5970  movzx   ebx, ax
0x1800c5973  or      ebx, r13d
0x1800c5976  test    ebx, ebx
0x1800c5978  jns     loc_1800C5A00
0x1800c597e  mov     eax, cs:dword_1801B76C8
0x1800c5984  cmp     eax, 2
0x1800c5987  jbe     loc_1800C5CF4
0x1800c598d  lea     rax, aFailedToAlloca_0; "Failed to allocate security descriptor"
0x1800c5994  mov     [rbp+57h+var_BC], 58h ; 'X'
0x1800c599b  mov     [rbp+57h+var_A0], rax
0x1800c599f  lea     rdx, byte_1801A970D
0x1800c59a6  lea     rax, aInitializeidds; "InitializeIddSecurityAttr"
0x1800c59ad  mov     [rbp+57h+var_C0], ebx
0x1800c59b0  mov     [rbp+57h+var_A8], rax
0x1800c59b4  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c59bb  mov     [rbp+57h+var_B0], rax
0x1800c59bf  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c59c6  mov     [rbp+57h+var_B8], rax
0x1800c59ca  lea     rax, [rbp+57h+var_A0]
0x1800c59ce  mov     qword ptr [rsp+120h+nSubAuthority7], rax
0x1800c59d3  lea     rax, [rbp+57h+var_A8]
0x1800c59d7  mov     qword ptr [rsp+120h+nSubAuthority6], rax
0x1800c59dc  lea     rax, [rbp+57h+var_BC]
0x1800c59e0  mov     qword ptr [rsp+120h+nSubAuthority5], rax
0x1800c59e5  lea     rax, [rbp+57h+var_B0]
0x1800c59e9  mov     qword ptr [rsp+120h+nSubAuthority4], rax
0x1800c59ee  lea     rax, [rbp+57h+var_C0]
0x1800c59f2  mov     qword ptr [rsp+120h+nSubAuthority3], rax
0x1800c59f7  lea     rax, [rbp+57h+var_B8]
0x1800c59fb  jmp     loc_1800C584C
0x1800c5a00  mov     r15d, 1
0x1800c5a06  mov     rcx, rdi; pSecurityDescriptor
0x1800c5a09  mov     edx, r15d; dwRevision
0x1800c5a0c  call    cs:__imp_InitializeSecurityDescriptor
0x1800c5a12  test    eax, eax
0x1800c5a14  jnz     loc_1800C5AB6
0x1800c5a1a  call    cs:__imp_GetLastError
0x1800c5a20  mov     ebx, eax
0x1800c5a22  test    eax, eax
0x1800c5a24  jle     short loc_1800C5A2C
0x1800c5a26  movzx   ebx, ax
0x1800c5a29  or      ebx, r13d
0x1800c5a2c  test    ebx, ebx
0x1800c5a2e  jns     loc_1800C5AB6
0x1800c5a34  mov     eax, cs:dword_1801B76C8
0x1800c5a3a  cmp     eax, 2
0x1800c5a3d  jbe     loc_1800C5CF4
0x1800c5a43  lea     rax, aInitializesecu; "InitializeSecurityDescriptor failed"
0x1800c5a4a  mov     [rbp+57h+var_BC], 5Fh ; '_'
0x1800c5a51  mov     [rbp+57h+var_A0], rax
0x1800c5a55  lea     rdx, byte_1801A975F
0x1800c5a5c  lea     rax, aInitializeidds; "InitializeIddSecurityAttr"
0x1800c5a63  mov     [rbp+57h+var_C0], ebx
0x1800c5a66  mov     [rbp+57h+var_A8], rax
0x1800c5a6a  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c5a71  mov     [rbp+57h+var_B0], rax
0x1800c5a75  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c5a7c  mov     [rbp+57h+var_B8], rax
0x1800c5a80  lea     rax, [rbp+57h+var_A0]
0x1800c5a84  mov     qword ptr [rsp+120h+nSubAuthority7], rax
0x1800c5a89  lea     rax, [rbp+57h+var_A8]
0x1800c5a8d  mov     qword ptr [rsp+120h+nSubAuthority6], rax
0x1800c5a92  lea     rax, [rbp+57h+var_BC]
0x1800c5a96  mov     qword ptr [rsp+120h+nSubAuthority5], rax
0x1800c5a9b  lea     rax, [rbp+57h+var_B0]
0x1800c5a9f  mov     qword ptr [rsp+120h+nSubAuthority4], rax
0x1800c5aa4  lea     rax, [rbp+57h+var_C0]
0x1800c5aa8  mov     qword ptr [rsp+120h+nSubAuthority3], rax
0x1800c5aad  lea     rax, [rbp+57h+var_B8]
0x1800c5ab1  jmp     loc_1800C584C
0x1800c5ab6  mov     r8, [rbp+57h+NewAcl]; pDacl
0x1800c5aba  xor     r9d, r9d; bDaclDefaulted
0x1800c5abd  mov     edx, r15d; bDaclPresent
0x1800c5ac0  mov     rcx, rdi; pSecurityDescriptor
0x1800c5ac3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800c5ac9  test    eax, eax
0x1800c5acb  jnz     loc_1800C5B6D
0x1800c5ad1  call    cs:__imp_GetLastError
0x1800c5ad7  mov     ebx, eax
0x1800c5ad9  test    eax, eax
0x1800c5adb  jle     short loc_1800C5AE3
0x1800c5add  movzx   ebx, ax
0x1800c5ae0  or      ebx, r13d
0x1800c5ae3  test    ebx, ebx
0x1800c5ae5  jns     loc_1800C5B6D
0x1800c5aeb  mov     eax, cs:dword_1801B76C8
0x1800c5af1  cmp     eax, 2
0x1800c5af4  jbe     loc_1800C5CF4
0x1800c5afa  lea     rax, aSetsecuritydes; "SetSecurityDescriptorDacl failed"
0x1800c5b01  mov     [rbp+57h+var_BC], 6Bh ; 'k'
0x1800c5b08  mov     [rbp+57h+var_A0], rax
0x1800c5b0c  lea     rdx, byte_1801A9669
0x1800c5b13  lea     rax, aInitializeidds; "InitializeIddSecurityAttr"
0x1800c5b1a  mov     [rbp+57h+var_C0], ebx
0x1800c5b1d  mov     [rbp+57h+var_A8], rax
0x1800c5b21  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c5b28  mov     [rbp+57h+var_B0], rax
0x1800c5b2c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c5b33  mov     [rbp+57h+var_B8], rax
0x1800c5b37  lea     rax, [rbp+57h+var_A0]
0x1800c5b3b  mov     qword ptr [rsp+120h+nSubAuthority7], rax
0x1800c5b40  lea     rax, [rbp+57h+var_A8]
0x1800c5b44  mov     qword ptr [rsp+120h+nSubAuthority6], rax
0x1800c5b49  lea     rax, [rbp+57h+var_BC]
0x1800c5b4d  mov     qword ptr [rsp+120h+nSubAuthority5], rax
0x1800c5b52  lea     rax, [rbp+57h+var_B0]
0x1800c5b56  mov     qword ptr [rsp+120h+nSubAuthority4], rax
0x1800c5b5b  lea     rax, [rbp+57h+var_C0]
0x1800c5b5f  mov     qword ptr [rsp+120h+nSubAuthority3], rax
0x1800c5b64  lea     rax, [rbp+57h+var_B8]
0x1800c5b68  jmp     loc_1800C584C
0x1800c5b6d  mov     rcx, rdi; pSecurityDescriptor
0x1800c5b70  call    cs:__imp_GetSecurityDescriptorLength
0x1800c5b76  mov     edx, eax; uBytes
0x1800c5b78  mov     ecx, 40h ; '@'; uFlags
0x1800c5b7d  mov     [rbp+57h+dwBufferLength], edx
0x1800c5b80  call    cs:__imp_LocalAlloc
0x1800c5b86  mov     rsi, rax
0x1800c5b89  test    rax, rax
0x1800c5b8c  jnz     loc_1800C5C2E
0x1800c5b92  call    cs:__imp_GetLastError
0x1800c5b98  mov     ebx, eax
0x1800c5b9a  test    eax, eax
0x1800c5b9c  jle     short loc_1800C5BA4
0x1800c5b9e  movzx   ebx, ax
0x1800c5ba1  or      ebx, r13d
0x1800c5ba4  test    ebx, ebx
0x1800c5ba6  jns     loc_1800C5C2E
0x1800c5bac  mov     eax, cs:dword_1801B76C8
0x1800c5bb2  cmp     eax, 2
0x1800c5bb5  jbe     loc_1800C5CF4
0x1800c5bbb  lea     rax, aFailedToAlloca; "Failed to allocate memory for self-rela"...
0x1800c5bc2  mov     [rbp+57h+var_BC], 77h ; 'w'
0x1800c5bc9  mov     [rbp+57h+var_A0], rax
0x1800c5bcd  lea     rdx, byte_1801A96BB
0x1800c5bd4  lea     rax, aInitializeidds; "InitializeIddSecurityAttr"
0x1800c5bdb  mov     [rbp+57h+var_C0], ebx
0x1800c5bde  mov     [rbp+57h+var_A8], rax
0x1800c5be2  lea     rax, aClientcoreTerm_11; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800c5be9  mov     [rbp+57h+var_B0], rax
0x1800c5bed  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800c5bf4  mov     [rbp+57h+var_B8], rax
0x1800c5bf8  lea     rax, [rbp+57h+var_A0]
0x1800c5bfc  mov     qword ptr [rsp+120h+nSubAuthority7], rax
0x1800c5c01  lea     rax, [rbp+57h+var_A8]
0x1800c5c05  mov     qword ptr [rsp+120h+nSubAuthority6], rax
0x1800c5c0a  lea     rax, [rbp+57h+var_BC]
0x1800c5c0e  mov     qword ptr [rsp+120h+nSubAuthority5], rax
0x1800c5c13  lea     rax, [rbp+57h+var_B0]
0x1800c5c17  mov     qword ptr [rsp+120h+nSubAuthority4], rax
0x1800c5c1c  lea     rax, [rbp+57h+var_C0]
0x1800c5c20  mov     qword ptr [rsp+120h+nSubAuthority3], rax
0x1800c5c25  lea     rax, [rbp+57h+var_B8]
0x1800c5c29  jmp     loc_1800C584C
0x1800c5c2e  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800c5c32  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x1800c5c35  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x1800c5c38  call    cs:__imp_MakeSelfRelativeSD
0x1800c5c3e  test    eax, eax
0x1800c5c40  jnz     loc_1800C5CE2
0x1800c5c46  call    cs:__imp_GetLastError
0x1800c5c4c  mov     ebx, eax
0x1800c5c4e  test    eax, eax
  ... truncated ...
```
