# CService::CreateRCMReadyEvent(void)

- ea: `0x18002e2f4`
- end: `0x18002e652`
- name: `?CreateRCMReadyEvent@CService@@IEAAJXZ`
- size: `862`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ae4c`

## callees

- `0x1800074c0`
- `0x18002e2f4`
- `0x18004b460`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18002e60c`
- `ntdll!RtlFreeSid` at `0x18002e61b`
- `ntdll!RtlFreeSid` at `0x18002e62a`
- `ntdll!RtlFreeSid` at `0x18002e60c`
- `ntdll!RtlFreeSid` at `0x18002e61b`
- `ntdll!RtlFreeSid` at `0x18002e62a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002e582`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002e582`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002e55e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002e55e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e4e3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e50e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e539`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e4e3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e50e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18002e539`
- `ntdll!RtlCreateAcl` at `0x18002e4b2`
- `ntdll!RtlCreateAcl` at `0x18002e4b2`
- `ntdll!RtlLengthSid` at `0x18002e43b`
- `ntdll!RtlLengthSid` at `0x18002e448`
- `ntdll!RtlLengthSid` at `0x18002e455`
- `ntdll!RtlLengthSid` at `0x18002e43b`
- `ntdll!RtlLengthSid` at `0x18002e448`
- `ntdll!RtlLengthSid` at `0x18002e455`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002e383`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002e3d4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002e41f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002e383`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002e3d4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18002e41f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e5b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e5b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e47c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e5c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e46e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e46e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e5fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e5fd`

## string_xrefs

- `0x18002e394`: `RtlAllocateAndInitializeSid - System failed: 0x%x in %s`
- `0x18002e5e9`: `CService::CreateRCMReadyEvent`
- `0x18002e3e0`: `RtlAllocateAndInitializeSid - NetworkService failed: 0x%x in %s`
- `0x18002e42b`: `RtlAllocateAndInitializeSid - World failed: 0x%x in %s`
- `0x18002e4c5`: `RtlCreateAcl failed: 0x%x in %s`
- `0x18002e4f0`: `RtlAddAccessAllowedAce - pSystemSid failed: 0x%x in %s`
- `0x18002e51b`: `RtlAddAccessAllowedAce - pNetworkServiceSid failed: 0x%x in %s`
- `0x18002e546`: `RtlAddAccessAllowedAce - pWorldSid failed: 0x%x in %s`
- `0x18002e56e`: `RtlCreateSecurityDescriptor failed: 0x%x in %s`
- `0x18002e592`: `RtlSetDaclSecurityDescriptor failed: 0x%x in %s`
- `0x18002e5a1`: `Global\RCMReadyEvent`
- `0x18002e5df`: `CreateEvent failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CService::CreateRCMReadyEvent(CService *this)
{
  struct _ACL *v2; // rdi
  NTSTATUS v3; // eax
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  ULONG v7; // r14d
  ULONG v8; // r14d
  ULONG v9; // r14d
  signed int LastError; // eax
  NTSTATUS Acl; // eax
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax
  NTSTATUS v14; // eax
  NTSTATUS SecurityDescriptor; // eax
  NTSTATUS v16; // eax
  HANDLE EventW; // rax
  signed int v18; // eax
  PSID v20; // [rsp+60h] [rbp-29h] BYREF
  PSID v21; // [rsp+68h] [rbp-21h] BYREF
  PSID Sid; // [rsp+70h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v24; // [rsp+80h] [rbp-9h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v25; // [rsp+88h] [rbp-1h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  v2 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v21 = 0;
  *(_DWORD *)v24.Value = 0;
  *(_WORD *)&v24.Value[4] = 1280;
  v20 = 0;
  *(_DWORD *)v25.Value = 0;
  *(_WORD *)&v25.Value[4] = 256;
  v3 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  v4 = v3 | 0x10000000;
  if ( v3 >= 0 )
  {
    v5 = RtlAllocateAndInitializeSid(&v24, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &v21);
    v4 = v5 | 0x10000000;
    if ( v5 >= 0 )
    {
      v6 = RtlAllocateAndInitializeSid(&v25, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v20);
      v4 = v6 | 0x10000000;
      if ( v6 >= 0 )
      {
        v7 = RtlLengthSid(v20);
        v8 = RtlLengthSid(v21) + v7;
        v9 = RtlLengthSid(Sid) + v8;
        v2 = (struct _ACL *)LocalAlloc(0x40u, v9 + 76 + 40LL);
        if ( v2 )
          goto LABEL_12;
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (v4 & 0x80000000) == 0 )
        {
LABEL_12:
          Acl = RtlCreateAcl(v2 + 8, v9 + 52, 2u);
          v4 = Acl | 0x10000000;
          if ( Acl >= 0 )
          {
            v12 = RtlAddAccessAllowedAce(v2 + 8, 2u, 0x100002u, Sid);
            v4 = v12 | 0x10000000;
            if ( v12 >= 0 )
            {
              v13 = RtlAddAccessAllowedAce(v2 + 8, 2u, 0x100002u, v21);
              v4 = v13 | 0x10000000;
              if ( v13 >= 0 )
              {
                v14 = RtlAddAccessAllowedAce(v2 + 8, 2u, 0x100000u, v20);
                v4 = v14 | 0x10000000;
                if ( v14 >= 0 )
                {
                  SecurityDescriptor = RtlCreateSecurityDescriptor(&v2[3], 1u);
                  v4 = SecurityDescriptor | 0x10000000;
                  if ( SecurityDescriptor >= 0 )
                  {
                    v16 = RtlSetDaclSecurityDescriptor(&v2[3], 1u, v2 + 8, 0);
                    v4 = v16 | 0x10000000;
                    if ( v16 >= 0 )
                    {
                      *(_DWORD *)&v2->AclRevision = v9 + 76;
                      v2[1] = (struct _ACL)&v2[3];
                      *(_DWORD *)&v2[2].AclRevision = 0;
                      EventW = CreateEventW((LPSECURITY_ATTRIBUTES)v2, 1, 0, L"Global\\RCMReadyEvent");
                      *((_QWORD *)this + 10) = EventW;
                      if ( !EventW )
                      {
                        v18 = GetLastError();
                        v4 = v18;
                        if ( v18 > 0 )
                          v4 = (unsigned __int16)v18 | 0x80070000;
                        if ( (v4 & 0x80000000) != 0 )
                          _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", v4, "CService::CreateRCMReadyEvent");
                      }
                    }
                    else
                    {
                      _DbgPrintMessage(
                        8,
                        "RtlSetDaclSecurityDescriptor failed: 0x%x in %s",
                        v4,
                        "CService::CreateRCMReadyEvent");
                    }
                  }
                  else
                  {
                    _DbgPrintMessage(
                      8,
                      "RtlCreateSecurityDescriptor failed: 0x%x in %s",
                      v4,
                      "CService::CreateRCMReadyEvent");
                  }
                }
                else
                {
                  _DbgPrintMessage(
                    8,
                    "RtlAddAccessAllowedAce - pWorldSid failed: 0x%x in %s",
                    v4,
                    "CService::CreateRCMReadyEvent");
                }
              }
              else
              {
                _DbgPrintMessage(
                  8,
                  "RtlAddAccessAllowedAce - pNetworkServiceSid failed: 0x%x in %s",
                  v4,
                  "CService::CreateRCMReadyEvent");
              }
            }
            else
            {
              _DbgPrintMessage(
                8,
                "RtlAddAccessAllowedAce - pSystemSid failed: 0x%x in %s",
                v4,
                "CService::CreateRCMReadyEvent");
            }
          }
          else
          {
            _DbgPrintMessage(8, "RtlCreateAcl failed: 0x%x in %s", v4, "CService::CreateRCMReadyEvent");
          }
        }
        else
        {
          _DbgPrintMessage(8, "LocalAlloc failed: 0x%x in %s", v4, "CService::CreateRCMReadyEvent");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "RtlAllocateAndInitializeSid - World failed: 0x%x in %s",
          v4,
          "CService::CreateRCMReadyEvent");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "RtlAllocateAndInitializeSid - NetworkService failed: 0x%x in %s",
        v4,
        "CService::CreateRCMReadyEvent");
    }
  }
  else
  {
    _DbgPrintMessage(8, "RtlAllocateAndInitializeSid - System failed: 0x%x in %s", v4, "CService::CreateRCMReadyEvent");
  }
  LocalFree(v2);
  if ( v20 )
    RtlFreeSid(v20);
  if ( v21 )
    RtlFreeSid(v21);
  if ( Sid )
    RtlFreeSid(Sid);
  return v4;
}

```

## disassembly

```asm
0x18002e2f4  push    rbp
0x18002e2f6  push    rbx
0x18002e2f7  push    rsi
0x18002e2f8  push    rdi
0x18002e2f9  push    r12
0x18002e2fb  push    r13
0x18002e2fd  push    r14
0x18002e2ff  push    r15
0x18002e301  lea     rbp, [rsp-1Fh]
0x18002e306  sub     rsp, 0A8h
0x18002e30d  mov     rax, cs:__security_cookie
0x18002e314  xor     rax, rsp
0x18002e317  mov     [rbp+57h+var_50], rax
0x18002e31b  xor     r12d, r12d
0x18002e31e  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18002e324  lea     rax, [rbp+57h+var_70]
0x18002e328  mov     [rbp+57h+var_70], r12
0x18002e32c  mov     [rsp+0E0h+Sid], rax; Sid
0x18002e331  mov     r13, rcx
0x18002e334  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x18002e339  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18002e33d  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18002e342  lea     r8d, [r12+12h]; SubAuthority0
0x18002e347  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x18002e34c  xor     r9d, r9d; SubAuthority1
0x18002e34f  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x18002e354  mov     dl, 1; SubAuthorityCount
0x18002e356  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x18002e35b  mov     edi, r12d
0x18002e35e  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x18002e363  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x18002e367  mov     [rbp+57h+var_78], r12
0x18002e36b  mov     dword ptr [rbp+57h+var_60.Value], r12d
0x18002e36f  mov     word ptr [rbp+57h+var_60.Value+4], 500h
0x18002e375  mov     [rbp+57h+var_80], r12
0x18002e379  mov     dword ptr [rbp+57h+var_58.Value], r12d
0x18002e37d  mov     word ptr [rbp+57h+var_58.Value+4], 100h
0x18002e383  call    cs:__imp_RtlAllocateAndInitializeSid
0x18002e389  mov     ebx, eax
0x18002e38b  mov     esi, 10000000h
0x18002e390  or      ebx, esi
0x18002e392  jge     short loc_18002E3A0
0x18002e394  lea     rdx, aRtlallocateand_0; "RtlAllocateAndInitializeSid - System fa"...
0x18002e39b  jmp     loc_18002E5E6
0x18002e3a0  lea     rax, [rbp+57h+var_78]
0x18002e3a4  xor     r9d, r9d; SubAuthority1
0x18002e3a7  mov     [rsp+0E0h+Sid], rax; Sid
0x18002e3ac  lea     rcx, [rbp+57h+var_60]; IdentifierAuthority
0x18002e3b0  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x18002e3b5  mov     dl, 1; SubAuthorityCount
0x18002e3b7  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18002e3bc  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x18002e3c1  lea     r8d, [r9+14h]; SubAuthority0
0x18002e3c5  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x18002e3ca  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x18002e3cf  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x18002e3d4  call    cs:__imp_RtlAllocateAndInitializeSid
0x18002e3da  mov     ebx, eax
0x18002e3dc  or      ebx, esi
0x18002e3de  jge     short loc_18002E3EC
0x18002e3e0  lea     rdx, aRtlallocateand; "RtlAllocateAndInitializeSid - NetworkSe"...
0x18002e3e7  jmp     loc_18002E5E6
0x18002e3ec  lea     rax, [rbp+57h+var_80]
0x18002e3f0  xor     r9d, r9d; SubAuthority1
0x18002e3f3  mov     [rsp+0E0h+Sid], rax; Sid
0x18002e3f8  lea     rcx, [rbp+57h+var_58]; IdentifierAuthority
0x18002e3fc  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x18002e401  xor     r8d, r8d; SubAuthority0
0x18002e404  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18002e409  mov     dl, 1; SubAuthorityCount
0x18002e40b  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x18002e410  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x18002e415  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x18002e41a  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x18002e41f  call    cs:__imp_RtlAllocateAndInitializeSid
0x18002e425  mov     ebx, eax
0x18002e427  or      ebx, esi
0x18002e429  jge     short loc_18002E437
0x18002e42b  lea     rdx, aRtlallocateand_1; "RtlAllocateAndInitializeSid - World fai"...
0x18002e432  jmp     loc_18002E5E6
0x18002e437  mov     rcx, [rbp+57h+var_80]; Sid
0x18002e43b  call    cs:__imp_RtlLengthSid
0x18002e441  mov     rcx, [rbp+57h+var_78]; Sid
0x18002e445  mov     r14d, eax
0x18002e448  call    cs:__imp_RtlLengthSid
0x18002e44e  mov     rcx, [rbp+57h+var_70]; Sid
0x18002e452  add     r14d, eax
0x18002e455  call    cs:__imp_RtlLengthSid
0x18002e45b  add     r14d, eax
0x18002e45e  mov     ecx, 40h ; '@'; uFlags
0x18002e463  lea     r15d, [r14+4Ch]
0x18002e467  mov     edx, r15d
0x18002e46a  add     rdx, 28h ; '('; uBytes
0x18002e46e  call    cs:__imp_LocalAlloc
0x18002e474  mov     rdi, rax
0x18002e477  test    rax, rax
0x18002e47a  jnz     short loc_18002E4A1
0x18002e47c  call    cs:__imp_GetLastError
0x18002e482  mov     ebx, eax
0x18002e484  test    eax, eax
0x18002e486  jle     short loc_18002E491
0x18002e488  movzx   ebx, ax
0x18002e48b  or      ebx, 80070000h
0x18002e491  test    ebx, ebx
0x18002e493  jns     short loc_18002E4A1
0x18002e495  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x18002e49c  jmp     loc_18002E5E6
0x18002e4a1  lea     rsi, [rdi+40h]
0x18002e4a5  mov     r8d, 2; AclRevision
0x18002e4ab  mov     rcx, rsi; Acl
0x18002e4ae  lea     edx, [r14+34h]; AclSize
0x18002e4b2  call    cs:__imp_RtlCreateAcl
0x18002e4b8  mov     ebx, eax
0x18002e4ba  mov     r14d, 10000000h
0x18002e4c0  or      ebx, r14d
0x18002e4c3  jge     short loc_18002E4D1
0x18002e4c5  lea     rdx, aRtlcreateaclFa; "RtlCreateAcl failed: 0x%x in %s"
0x18002e4cc  jmp     loc_18002E5E6
0x18002e4d1  mov     r9, [rbp+57h+var_70]; Sid
0x18002e4d5  mov     edx, 2; Revision
0x18002e4da  mov     r8d, 100002h; AccessMask
0x18002e4e0  mov     rcx, rsi; Acl
0x18002e4e3  call    cs:__imp_RtlAddAccessAllowedAce
0x18002e4e9  mov     ebx, eax
0x18002e4eb  or      ebx, r14d
0x18002e4ee  jge     short loc_18002E4FC
0x18002e4f0  lea     rdx, aRtladdaccessal_1; "RtlAddAccessAllowedAce - pSystemSid fai"...
0x18002e4f7  jmp     loc_18002E5E6
0x18002e4fc  mov     r9, [rbp+57h+var_78]; Sid
0x18002e500  mov     edx, 2; Revision
0x18002e505  mov     r8d, 100002h; AccessMask
0x18002e50b  mov     rcx, rsi; Acl
0x18002e50e  call    cs:__imp_RtlAddAccessAllowedAce
0x18002e514  mov     ebx, eax
0x18002e516  or      ebx, r14d
0x18002e519  jge     short loc_18002E527
0x18002e51b  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce - pNetworkServic"...
0x18002e522  jmp     loc_18002E5E6
0x18002e527  mov     r9, [rbp+57h+var_80]; Sid
0x18002e52b  mov     edx, 2; Revision
0x18002e530  mov     r8d, 100000h; AccessMask
0x18002e536  mov     rcx, rsi; Acl
0x18002e539  call    cs:__imp_RtlAddAccessAllowedAce
0x18002e53f  mov     ebx, eax
0x18002e541  or      ebx, r14d
0x18002e544  jge     short loc_18002E552
0x18002e546  lea     rdx, aRtladdaccessal_2; "RtlAddAccessAllowedAce - pWorldSid fail"...
0x18002e54d  jmp     loc_18002E5E6
0x18002e552  lea     r14, [rdi+18h]
0x18002e556  mov     edx, 1; Revision
0x18002e55b  mov     rcx, r14; SecurityDescriptor
0x18002e55e  call    cs:__imp_RtlCreateSecurityDescriptor
0x18002e564  mov     ebx, eax
0x18002e566  or      ebx, 10000000h
0x18002e56c  jge     short loc_18002E577
0x18002e56e  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor failed: 0x%"...
0x18002e575  jmp     short loc_18002E5E6
0x18002e577  xor     r9d, r9d; DaclDefaulted
0x18002e57a  mov     r8, rsi; Dacl
0x18002e57d  mov     dl, 1; DaclPresent
0x18002e57f  mov     rcx, r14; SecurityDescriptor
0x18002e582  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18002e588  mov     ebx, eax
0x18002e58a  or      ebx, 10000000h
0x18002e590  jge     short loc_18002E59B
0x18002e592  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor failed: 0x"...
0x18002e599  jmp     short loc_18002E5E6
0x18002e59b  xor     r8d, r8d; bInitialState
0x18002e59e  mov     [rdi], r15d
0x18002e5a1  lea     r9, Name; "Global\\RCMReadyEvent"
0x18002e5a8  mov     [rdi+8], r14
0x18002e5ac  mov     rcx, rdi; lpEventAttributes
0x18002e5af  mov     [rdi+10h], r12d
0x18002e5b3  lea     edx, [r8+1]; bManualReset
0x18002e5b7  call    cs:__imp_CreateEventW
0x18002e5bd  mov     [r13+50h], rax
0x18002e5c1  test    rax, rax
0x18002e5c4  jnz     short loc_18002E5FA
0x18002e5c6  call    cs:__imp_GetLastError
0x18002e5cc  mov     ebx, eax
0x18002e5ce  test    eax, eax
0x18002e5d0  jle     short loc_18002E5DB
0x18002e5d2  movzx   ebx, ax
0x18002e5d5  or      ebx, 80070000h
0x18002e5db  test    ebx, ebx
0x18002e5dd  jns     short loc_18002E5FA
0x18002e5df  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18002e5e6  mov     r8d, ebx
0x18002e5e9  lea     r9, aCserviceCreate; "CService::CreateRCMReadyEvent"
0x18002e5f0  mov     ecx, 8; int
0x18002e5f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e5fa  mov     rcx, rdi; hMem
0x18002e5fd  call    cs:__imp_LocalFree
0x18002e603  mov     rcx, [rbp+57h+var_80]; Sid
0x18002e607  test    rcx, rcx
0x18002e60a  jz      short loc_18002E612
0x18002e60c  call    cs:__imp_RtlFreeSid
0x18002e612  mov     rcx, [rbp+57h+var_78]; Sid
0x18002e616  test    rcx, rcx
0x18002e619  jz      short loc_18002E621
0x18002e61b  call    cs:__imp_RtlFreeSid
0x18002e621  mov     rcx, [rbp+57h+var_70]; Sid
0x18002e625  test    rcx, rcx
0x18002e628  jz      short loc_18002E630
0x18002e62a  call    cs:__imp_RtlFreeSid
0x18002e630  mov     eax, ebx
0x18002e632  mov     rcx, [rbp+57h+var_50]
0x18002e636  xor     rcx, rsp; StackCookie
0x18002e639  call    __security_check_cookie
0x18002e63e  add     rsp, 0A8h
0x18002e645  pop     r15
0x18002e647  pop     r14
0x18002e649  pop     r13
0x18002e64b  pop     r12
0x18002e64d  pop     rdi
0x18002e64e  pop     rsi
0x18002e64f  pop     rbx
0x18002e650  pop     rbp
0x18002e651  retn
```
