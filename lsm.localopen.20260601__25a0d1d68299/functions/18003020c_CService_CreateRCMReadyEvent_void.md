# CService::CreateRCMReadyEvent(void)

- ea: `0x18003020c`
- end: `0x1800305e6`
- name: `?CreateRCMReadyEvent@CService@@IEAAJXZ`
- size: `986`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002cf00`

## callees

- `0x1800077a0`
- `0x18003020c`
- `0x18004e850`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18003058d`
- `ntdll!RtlFreeSid` at `0x1800305a2`
- `ntdll!RtlFreeSid` at `0x1800305b7`
- `ntdll!RtlFreeSid` at `0x18003058d`
- `ntdll!RtlFreeSid` at `0x1800305a2`
- `ntdll!RtlFreeSid` at `0x1800305b7`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800304eb`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800304eb`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800304be`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800304be`
- `ntdll!RtlAddAccessAllowedAce` at `0x180030431`
- `ntdll!RtlAddAccessAllowedAce` at `0x180030462`
- `ntdll!RtlAddAccessAllowedAce` at `0x180030493`
- `ntdll!RtlAddAccessAllowedAce` at `0x180030431`
- `ntdll!RtlAddAccessAllowedAce` at `0x180030462`
- `ntdll!RtlAddAccessAllowedAce` at `0x180030493`
- `ntdll!RtlCreateAcl` at `0x1800303fa`
- `ntdll!RtlCreateAcl` at `0x1800303fa`
- `ntdll!RtlLengthSid` at `0x180030365`
- `ntdll!RtlLengthSid` at `0x180030378`
- `ntdll!RtlLengthSid` at `0x18003038b`
- `ntdll!RtlLengthSid` at `0x180030365`
- `ntdll!RtlLengthSid` at `0x180030378`
- `ntdll!RtlLengthSid` at `0x18003038b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18003029b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800302f2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180030343`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18003029b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800302f2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180030343`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030526`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003053b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800303be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003053b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800303aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800303aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030578`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030578`

## string_xrefs

- `0x1800302b2`: `RtlAllocateAndInitializeSid - System failed: 0x%x in %s`
- `0x180030564`: `CService::CreateRCMReadyEvent`
- `0x180030304`: `RtlAllocateAndInitializeSid - NetworkService failed: 0x%x in %s`
- `0x180030355`: `RtlAllocateAndInitializeSid - World failed: 0x%x in %s`
- `0x180030413`: `RtlCreateAcl failed: 0x%x in %s`
- `0x180030444`: `RtlAddAccessAllowedAce - pSystemSid failed: 0x%x in %s`
- `0x180030475`: `RtlAddAccessAllowedAce - pNetworkServiceSid failed: 0x%x in %s`
- `0x1800304a6`: `RtlAddAccessAllowedAce - pWorldSid failed: 0x%x in %s`
- `0x1800304d4`: `RtlCreateSecurityDescriptor failed: 0x%x in %s`
- `0x180030501`: `RtlSetDaclSecurityDescriptor failed: 0x%x in %s`
- `0x180030510`: `Global\RCMReadyEvent`
- `0x18003055a`: `CreateEvent failed: 0x%x in %s`

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
0x18003020c  push    rbp
0x18003020e  push    rbx
0x18003020f  push    rsi
0x180030210  push    rdi
0x180030211  push    r12
0x180030213  push    r13
0x180030215  push    r14
0x180030217  push    r15
0x180030219  lea     rbp, [rsp-1Fh]
0x18003021e  sub     rsp, 0A8h
0x180030225  mov     rax, cs:__security_cookie
0x18003022c  xor     rax, rsp
0x18003022f  mov     [rbp+57h+var_50], rax
0x180030233  xor     r12d, r12d
0x180030236  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18003023c  lea     rax, [rbp+57h+var_70]
0x180030240  mov     [rbp+57h+var_70], r12
0x180030244  mov     [rsp+0E0h+Sid], rax; Sid
0x180030249  mov     r13, rcx
0x18003024c  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x180030251  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180030255  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18003025a  lea     r8d, [r12+12h]; SubAuthority0
0x18003025f  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x180030264  xor     r9d, r9d; SubAuthority1
0x180030267  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x18003026c  mov     dl, 1; SubAuthorityCount
0x18003026e  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x180030273  mov     edi, r12d
0x180030276  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x18003027b  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r12d
0x18003027f  mov     [rbp+57h+var_78], r12
0x180030283  mov     dword ptr [rbp+57h+var_60.Value], r12d
0x180030287  mov     word ptr [rbp+57h+var_60.Value+4], 500h
0x18003028d  mov     [rbp+57h+var_80], r12
0x180030291  mov     dword ptr [rbp+57h+var_58.Value], r12d
0x180030295  mov     word ptr [rbp+57h+var_58.Value+4], 100h
0x18003029b  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800302a2  nop     dword ptr [rax+rax+00h]
0x1800302a7  mov     ebx, eax
0x1800302a9  mov     esi, 10000000h
0x1800302ae  or      ebx, esi
0x1800302b0  jge     short loc_1800302BE
0x1800302b2  lea     rdx, aRtlallocateand_0; "RtlAllocateAndInitializeSid - System fa"...
0x1800302b9  jmp     loc_180030561
0x1800302be  lea     rax, [rbp+57h+var_78]
0x1800302c2  xor     r9d, r9d; SubAuthority1
0x1800302c5  mov     [rsp+0E0h+Sid], rax; Sid
0x1800302ca  lea     rcx, [rbp+57h+var_60]; IdentifierAuthority
0x1800302ce  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x1800302d3  mov     dl, 1; SubAuthorityCount
0x1800302d5  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x1800302da  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x1800302df  lea     r8d, [r9+14h]; SubAuthority0
0x1800302e3  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x1800302e8  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x1800302ed  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x1800302f2  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800302f9  nop     dword ptr [rax+rax+00h]
0x1800302fe  mov     ebx, eax
0x180030300  or      ebx, esi
0x180030302  jge     short loc_180030310
0x180030304  lea     rdx, aRtlallocateand; "RtlAllocateAndInitializeSid - NetworkSe"...
0x18003030b  jmp     loc_180030561
0x180030310  lea     rax, [rbp+57h+var_80]
0x180030314  xor     r9d, r9d; SubAuthority1
0x180030317  mov     [rsp+0E0h+Sid], rax; Sid
0x18003031c  lea     rcx, [rbp+57h+var_58]; IdentifierAuthority
0x180030320  mov     [rsp+0E0h+SubAuthority7], r12d; SubAuthority7
0x180030325  xor     r8d, r8d; SubAuthority0
0x180030328  mov     [rsp+0E0h+SubAuthority6], r12d; SubAuthority6
0x18003032d  mov     dl, 1; SubAuthorityCount
0x18003032f  mov     [rsp+0E0h+SubAuthority5], r12d; SubAuthority5
0x180030334  mov     [rsp+0E0h+SubAuthority4], r12d; SubAuthority4
0x180030339  mov     [rsp+0E0h+SubAuthority3], r12d; SubAuthority3
0x18003033e  mov     [rsp+0E0h+SubAuthority2], r12d; SubAuthority2
0x180030343  call    cs:__imp_RtlAllocateAndInitializeSid
0x18003034a  nop     dword ptr [rax+rax+00h]
0x18003034f  mov     ebx, eax
0x180030351  or      ebx, esi
0x180030353  jge     short loc_180030361
0x180030355  lea     rdx, aRtlallocateand_1; "RtlAllocateAndInitializeSid - World fai"...
0x18003035c  jmp     loc_180030561
0x180030361  mov     rcx, [rbp+57h+var_80]; Sid
0x180030365  call    cs:__imp_RtlLengthSid
0x18003036c  nop     dword ptr [rax+rax+00h]
0x180030371  mov     rcx, [rbp+57h+var_78]; Sid
0x180030375  mov     r14d, eax
0x180030378  call    cs:__imp_RtlLengthSid
0x18003037f  nop     dword ptr [rax+rax+00h]
0x180030384  mov     rcx, [rbp+57h+var_70]; Sid
0x180030388  add     r14d, eax
0x18003038b  call    cs:__imp_RtlLengthSid
0x180030392  nop     dword ptr [rax+rax+00h]
0x180030397  add     r14d, eax
0x18003039a  mov     ecx, 40h ; '@'; uFlags
0x18003039f  lea     r15d, [r14+4Ch]
0x1800303a3  mov     edx, r15d
0x1800303a6  add     rdx, 28h ; '('; uBytes
0x1800303aa  call    cs:__imp_LocalAlloc
0x1800303b1  nop     dword ptr [rax+rax+00h]
0x1800303b6  mov     rdi, rax
0x1800303b9  test    rax, rax
0x1800303bc  jnz     short loc_1800303E9
0x1800303be  call    cs:__imp_GetLastError
0x1800303c5  nop     dword ptr [rax+rax+00h]
0x1800303ca  mov     ebx, eax
0x1800303cc  test    eax, eax
0x1800303ce  jle     short loc_1800303D9
0x1800303d0  movzx   ebx, ax
0x1800303d3  or      ebx, 80070000h
0x1800303d9  test    ebx, ebx
0x1800303db  jns     short loc_1800303E9
0x1800303dd  lea     rdx, aLocalallocFail; "LocalAlloc failed: 0x%x in %s"
0x1800303e4  jmp     loc_180030561
0x1800303e9  lea     rsi, [rdi+40h]
0x1800303ed  mov     r8d, 2; AclRevision
0x1800303f3  mov     rcx, rsi; Acl
0x1800303f6  lea     edx, [r14+34h]; AclSize
0x1800303fa  call    cs:__imp_RtlCreateAcl
0x180030401  nop     dword ptr [rax+rax+00h]
0x180030406  mov     ebx, eax
0x180030408  mov     r14d, 10000000h
0x18003040e  or      ebx, r14d
0x180030411  jge     short loc_18003041F
0x180030413  lea     rdx, aRtlcreateaclFa; "RtlCreateAcl failed: 0x%x in %s"
0x18003041a  jmp     loc_180030561
0x18003041f  mov     r9, [rbp+57h+var_70]; Sid
0x180030423  mov     edx, 2; Revision
0x180030428  mov     r8d, 100002h; AccessMask
0x18003042e  mov     rcx, rsi; Acl
0x180030431  call    cs:__imp_RtlAddAccessAllowedAce
0x180030438  nop     dword ptr [rax+rax+00h]
0x18003043d  mov     ebx, eax
0x18003043f  or      ebx, r14d
0x180030442  jge     short loc_180030450
0x180030444  lea     rdx, aRtladdaccessal_1; "RtlAddAccessAllowedAce - pSystemSid fai"...
0x18003044b  jmp     loc_180030561
0x180030450  mov     r9, [rbp+57h+var_78]; Sid
0x180030454  mov     edx, 2; Revision
0x180030459  mov     r8d, 100002h; AccessMask
0x18003045f  mov     rcx, rsi; Acl
0x180030462  call    cs:__imp_RtlAddAccessAllowedAce
0x180030469  nop     dword ptr [rax+rax+00h]
0x18003046e  mov     ebx, eax
0x180030470  or      ebx, r14d
0x180030473  jge     short loc_180030481
0x180030475  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAce - pNetworkServic"...
0x18003047c  jmp     loc_180030561
0x180030481  mov     r9, [rbp+57h+var_80]; Sid
0x180030485  mov     edx, 2; Revision
0x18003048a  mov     r8d, 100000h; AccessMask
0x180030490  mov     rcx, rsi; Acl
0x180030493  call    cs:__imp_RtlAddAccessAllowedAce
0x18003049a  nop     dword ptr [rax+rax+00h]
0x18003049f  mov     ebx, eax
0x1800304a1  or      ebx, r14d
0x1800304a4  jge     short loc_1800304B2
0x1800304a6  lea     rdx, aRtladdaccessal_2; "RtlAddAccessAllowedAce - pWorldSid fail"...
0x1800304ad  jmp     loc_180030561
0x1800304b2  lea     r14, [rdi+18h]
0x1800304b6  mov     edx, 1; Revision
0x1800304bb  mov     rcx, r14; SecurityDescriptor
0x1800304be  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800304c5  nop     dword ptr [rax+rax+00h]
0x1800304ca  mov     ebx, eax
0x1800304cc  or      ebx, 10000000h
0x1800304d2  jge     short loc_1800304E0
0x1800304d4  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor failed: 0x%"...
0x1800304db  jmp     loc_180030561
0x1800304e0  xor     r9d, r9d; DaclDefaulted
0x1800304e3  mov     r8, rsi; Dacl
0x1800304e6  mov     dl, 1; DaclPresent
0x1800304e8  mov     rcx, r14; SecurityDescriptor
0x1800304eb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800304f2  nop     dword ptr [rax+rax+00h]
0x1800304f7  mov     ebx, eax
0x1800304f9  or      ebx, 10000000h
0x1800304ff  jge     short loc_18003050A
0x180030501  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor failed: 0x"...
0x180030508  jmp     short loc_180030561
0x18003050a  xor     r8d, r8d; bInitialState
0x18003050d  mov     [rdi], r15d
0x180030510  lea     r9, Name; "Global\\RCMReadyEvent"
0x180030517  mov     [rdi+8], r14
0x18003051b  mov     rcx, rdi; lpEventAttributes
0x18003051e  mov     [rdi+10h], r12d
0x180030522  lea     edx, [r8+1]; bManualReset
0x180030526  call    cs:__imp_CreateEventW
0x18003052d  nop     dword ptr [rax+rax+00h]
0x180030532  mov     [r13+50h], rax
0x180030536  test    rax, rax
0x180030539  jnz     short loc_180030575
0x18003053b  call    cs:__imp_GetLastError
0x180030542  nop     dword ptr [rax+rax+00h]
0x180030547  mov     ebx, eax
0x180030549  test    eax, eax
0x18003054b  jle     short loc_180030556
0x18003054d  movzx   ebx, ax
0x180030550  or      ebx, 80070000h
0x180030556  test    ebx, ebx
0x180030558  jns     short loc_180030575
0x18003055a  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x180030561  mov     r8d, ebx
0x180030564  lea     r9, aCserviceCreate; "CService::CreateRCMReadyEvent"
0x18003056b  mov     ecx, 8; int
0x180030570  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030575  mov     rcx, rdi; hMem
0x180030578  call    cs:__imp_LocalFree
0x18003057f  nop     dword ptr [rax+rax+00h]
0x180030584  mov     rcx, [rbp+57h+var_80]; Sid
0x180030588  test    rcx, rcx
0x18003058b  jz      short loc_180030599
0x18003058d  call    cs:__imp_RtlFreeSid
0x180030594  nop     dword ptr [rax+rax+00h]
0x180030599  mov     rcx, [rbp+57h+var_78]; Sid
0x18003059d  test    rcx, rcx
0x1800305a0  jz      short loc_1800305AE
0x1800305a2  call    cs:__imp_RtlFreeSid
0x1800305a9  nop     dword ptr [rax+rax+00h]
0x1800305ae  mov     rcx, [rbp+57h+var_70]; Sid
0x1800305b2  test    rcx, rcx
0x1800305b5  jz      short loc_1800305C3
0x1800305b7  call    cs:__imp_RtlFreeSid
0x1800305be  nop     dword ptr [rax+rax+00h]
0x1800305c3  mov     eax, ebx
0x1800305c5  mov     rcx, [rbp+57h+var_50]
0x1800305c9  xor     rcx, rsp; StackCookie
0x1800305cc  call    __security_check_cookie
0x1800305d1  add     rsp, 0A8h
0x1800305d8  pop     r15
0x1800305da  pop     r14
0x1800305dc  pop     r13
0x1800305de  pop     r12
0x1800305e0  pop     rdi
0x1800305e1  pop     rsi
0x1800305e2  pop     rbx
0x1800305e3  pop     rbp
0x1800305e4  retn
```
