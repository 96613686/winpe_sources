# PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc(void *,void * *)

- ea: `0x18002a214`
- end: `0x18002a586`
- name: `?CreateRegistrySecDesc@PROTOCOL_MESSAGING_HANDLER@@AEAAJPEAXPEAPEAX@Z`
- size: `882`
- prototype: `__int64 __fastcall(PROTOCOL_MESSAGING_HANDLER *this, void *, struct _ACL **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029da0`
- `0x18002a6a8`

## callees

- `0x18002a214`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a3c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a4ea`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002a368`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002a368`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002a49e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002a49e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002a4e0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002a4e0`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a3b7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a409`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a456`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a3b7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a409`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a456`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a2e5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a2f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a2fe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a2e5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a2f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a2fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a316`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a316`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a53c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a53c`
- `iisutil!PuDbgPrintError` at `0x18002a29a`
- `iisutil!PuDbgPrintError` at `0x18002a533`
- `iisutil!PuDbgPrintError` at `0x18002a29a`
- `iisutil!PuDbgPrintError` at `0x18002a533`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002a24b`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002a2ae`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002a24b`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18002a2ae`
- `iisutil!FreeWellKnownSid` at `0x18002a554`
- `iisutil!FreeWellKnownSid` at `0x18002a56d`
- `iisutil!FreeWellKnownSid` at `0x18002a554`
- `iisutil!FreeWellKnownSid` at `0x18002a56d`

## string_xrefs

- `0x18002a28f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002a528`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002a26f`: `Error getting the SID for Local System\n`
- `0x18002a283`: `PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc`
- `0x18002a51c`: `PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc`
- `0x18002a2d2`: `Error getting the SID for Administrators\n`
- `0x18002a394`: `Error initializing ACL\n`
- `0x18002a3e3`: `Error adding ACE to ACL\n`
- `0x18002a435`: `Error adding ACE to ACL\n`
- `0x18002a482`: `Error adding ACE to ACL\n`
- `0x18002a4c6`: `Error initializing security descriptor\n`
- `0x18002a508`: `Error setting security descriptor on ACL\n`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc(
        PROTOCOL_MESSAGING_HANDLER *this,
        void *a2,
        struct _ACL **a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // rax
  __int64 v8; // r8
  int v9; // eax
  DWORD LengthSid; // r15d
  DWORD v11; // r15d
  DWORD v12; // r15d
  struct _ACL *v13; // rax
  struct _ACL *v14; // rdi
  signed int LastError; // eax
  struct _ACL *v16; // rbx
  signed int v17; // eax
  const char *v18; // rax
  __int64 v19; // r8
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  PSID v26; // [rsp+60h] [rbp+30h] BYREF
  PSID pSid; // [rsp+78h] [rbp+48h] BYREF

  v26 = 0;
  pSid = 0;
  v5 = AllocateAndCreateWellKnownSid(WinLocalSystemSid, &v26);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v7 = "Error getting the SID for Local System\n";
      v8 = 303;
LABEL_6:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
        v8,
        "PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc",
        v6,
        v7);
      goto LABEL_50;
    }
    goto LABEL_50;
  }
  v9 = AllocateAndCreateWellKnownSid(WinBuiltinAdministratorsSid, &pSid);
  v6 = v9;
  if ( !v9 )
  {
    LengthSid = GetLengthSid(pSid);
    v11 = GetLengthSid(v26) + LengthSid;
    v12 = GetLengthSid(a2) + 32 + v11;
    v13 = (struct _ACL *)LocalAlloc(0x40u, v12 + 40LL);
    v14 = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v7 = "Failed to allocate memory for SD\n";
        v8 = 347;
        goto LABEL_6;
      }
      goto LABEL_50;
    }
    v16 = v13 + 5;
    if ( InitializeAcl(v13 + 5, v12, 2u) )
    {
      if ( AddAccessAllowedAce(v16, 2u, 0x20019u, a2) )
      {
        if ( AddAccessAllowedAce(v16, 2u, 0xF003Fu, v26) )
        {
          if ( AddAccessAllowedAce(v16, 2u, 0xF003Fu, pSid) )
          {
            if ( InitializeSecurityDescriptor(v14, 1u) )
            {
              if ( SetSecurityDescriptorDacl(v14, 1, v16, 0) )
              {
                v6 = 0;
                *a3 = v14;
                goto LABEL_50;
              }
              v24 = GetLastError();
              v6 = v24;
              if ( v24 > 0 )
                v6 = (unsigned __int16)v24 | 0x80070000;
              if ( (g_dwDebugFlags & 0xF) == 0 )
              {
LABEL_48:
                LocalFree(v14);
                goto LABEL_50;
              }
              v18 = "Error setting security descriptor on ACL\n";
              v19 = 424;
            }
            else
            {
              v23 = GetLastError();
              v6 = v23;
              if ( v23 > 0 )
                v6 = (unsigned __int16)v23 | 0x80070000;
              if ( (g_dwDebugFlags & 0xF) == 0 )
                goto LABEL_48;
              v18 = "Error initializing security descriptor\n";
              v19 = 412;
            }
          }
          else
          {
            v22 = GetLastError();
            v6 = v22;
            if ( v22 > 0 )
              v6 = (unsigned __int16)v22 | 0x80070000;
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_48;
            v18 = "Error adding ACE to ACL\n";
            v19 = 400;
          }
        }
        else
        {
          v21 = GetLastError();
          v6 = v21;
          if ( v21 > 0 )
            v6 = (unsigned __int16)v21 | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_48;
          v18 = "Error adding ACE to ACL\n";
          v19 = 388;
        }
      }
      else
      {
        v20 = GetLastError();
        v6 = v20;
        if ( v20 > 0 )
          v6 = (unsigned __int16)v20 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_48;
        v18 = "Error adding ACE to ACL\n";
        v19 = 376;
      }
    }
    else
    {
      v17 = GetLastError();
      v6 = v17;
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_48;
      v18 = "Error initializing ACL\n";
      v19 = 363;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      v19,
      "PROTOCOL_MESSAGING_HANDLER::CreateRegistrySecDesc",
      v6,
      v18);
    goto LABEL_48;
  }
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v7 = "Error getting the SID for Administrators\n";
    v8 = 316;
    goto LABEL_6;
  }
LABEL_50:
  if ( v26 )
  {
    FreeWellKnownSid(&v26);
    v26 = 0;
  }
  if ( pSid )
    FreeWellKnownSid(&pSid);
  return v6;
}

```

## disassembly

```asm
0x18002a214  mov     [rsp-28h+arg_8], rbx
0x18002a219  mov     [rsp-28h+arg_0], rcx
0x18002a21e  push    rbp
0x18002a21f  push    rsi
0x18002a220  push    rdi
0x18002a221  push    r14
0x18002a223  push    r15
0x18002a225  mov     rbp, rsp
0x18002a228  sub     rsp, 30h
0x18002a22c  mov     rsi, rdx
0x18002a22f  mov     [rbp+arg_0], 0
0x18002a237  lea     rdx, [rbp+arg_0]
0x18002a23b  mov     [rbp+pSid], 0
0x18002a243  mov     ecx, 16h
0x18002a248  mov     r14, r8
0x18002a24b  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002a251  mov     ebx, eax
0x18002a253  test    eax, eax
0x18002a255  jz      short loc_18002A2A5
0x18002a257  jle     short loc_18002A262
0x18002a259  movzx   ebx, ax
0x18002a25c  or      ebx, 80070000h
0x18002a262  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a269  jz      loc_18002A549
0x18002a26f  lea     rax, aErrorGettingTh; "Error getting the SID for Local System"...
0x18002a276  mov     r8d, 12Fh
0x18002a27c  mov     rcx, cs:g_pDebug
0x18002a283  lea     r9, aProtocolMessag_32; "PROTOCOL_MESSAGING_HANDLER::CreateRegis"...
0x18002a28a  mov     [rsp+30h+var_8], rax
0x18002a28f  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a296  mov     [rsp+30h+var_10], ebx
0x18002a29a  call    cs:__imp_PuDbgPrintError
0x18002a2a0  jmp     loc_18002A549
0x18002a2a5  lea     rdx, [rbp+pSid]
0x18002a2a9  mov     ecx, 1Ah
0x18002a2ae  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x18002a2b4  mov     ebx, eax
0x18002a2b6  test    eax, eax
0x18002a2b8  jz      short loc_18002A2E1
0x18002a2ba  jle     short loc_18002A2C5
0x18002a2bc  movzx   ebx, ax
0x18002a2bf  or      ebx, 80070000h
0x18002a2c5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a2cc  jz      loc_18002A549
0x18002a2d2  lea     rax, aErrorGettingTh_0; "Error getting the SID for Administrator"...
0x18002a2d9  mov     r8d, 13Ch
0x18002a2df  jmp     short loc_18002A27C
0x18002a2e1  mov     rcx, [rbp+pSid]; pSid
0x18002a2e5  call    cs:__imp_GetLengthSid
0x18002a2eb  mov     rcx, [rbp+arg_0]; pSid
0x18002a2ef  mov     r15d, eax
0x18002a2f2  call    cs:__imp_GetLengthSid
0x18002a2f8  mov     rcx, rsi; pSid
0x18002a2fb  add     r15d, eax
0x18002a2fe  call    cs:__imp_GetLengthSid
0x18002a304  add     eax, 20h ; ' '
0x18002a307  mov     ecx, 40h ; '@'; uFlags
0x18002a30c  add     r15d, eax
0x18002a30f  mov     edx, r15d
0x18002a312  add     rdx, 28h ; '('; uBytes
0x18002a316  call    cs:__imp_LocalAlloc
0x18002a31c  mov     rdi, rax
0x18002a31f  test    rax, rax
0x18002a322  jnz     short loc_18002A358
0x18002a324  call    cs:__imp_GetLastError
0x18002a32a  mov     ebx, eax
0x18002a32c  test    eax, eax
0x18002a32e  jle     short loc_18002A339
0x18002a330  movzx   ebx, ax
0x18002a333  or      ebx, 80070000h
0x18002a339  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a340  jz      loc_18002A549
0x18002a346  lea     rax, aFailedToAlloca_0; "Failed to allocate memory for SD\n"
0x18002a34d  mov     r8d, 15Bh
0x18002a353  jmp     loc_18002A27C
0x18002a358  lea     rbx, [rax+28h]
0x18002a35c  mov     r8d, 2; dwAclRevision
0x18002a362  mov     rcx, rbx; pAcl
0x18002a365  mov     edx, r15d; nAclLength
0x18002a368  call    cs:__imp_InitializeAcl
0x18002a36e  test    eax, eax
0x18002a370  jnz     short loc_18002A3A6
0x18002a372  call    cs:__imp_GetLastError
0x18002a378  mov     ebx, eax
0x18002a37a  test    eax, eax
0x18002a37c  jle     short loc_18002A387
0x18002a37e  movzx   ebx, ax
0x18002a381  or      ebx, 80070000h
0x18002a387  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a38e  jz      loc_18002A539
0x18002a394  lea     rax, aErrorInitializ_1; "Error initializing ACL\n"
0x18002a39b  mov     r8d, 16Bh
0x18002a3a1  jmp     loc_18002A515
0x18002a3a6  mov     r9, rsi; pSid
0x18002a3a9  mov     edx, 2; dwAceRevision
0x18002a3ae  mov     r8d, 20019h; AccessMask
0x18002a3b4  mov     rcx, rbx; pAcl
0x18002a3b7  call    cs:__imp_AddAccessAllowedAce
0x18002a3bd  test    eax, eax
0x18002a3bf  jnz     short loc_18002A3F5
0x18002a3c1  call    cs:__imp_GetLastError
0x18002a3c7  mov     ebx, eax
0x18002a3c9  test    eax, eax
0x18002a3cb  jle     short loc_18002A3D6
0x18002a3cd  movzx   ebx, ax
0x18002a3d0  or      ebx, 80070000h
0x18002a3d6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a3dd  jz      loc_18002A539
0x18002a3e3  lea     rax, aErrorAddingAce; "Error adding ACE to ACL\n"
0x18002a3ea  mov     r8d, 178h
0x18002a3f0  jmp     loc_18002A515
0x18002a3f5  mov     r9, [rbp+arg_0]; pSid
0x18002a3f9  mov     esi, 0F003Fh
0x18002a3fe  mov     r8d, esi; AccessMask
0x18002a401  mov     edx, 2; dwAceRevision
0x18002a406  mov     rcx, rbx; pAcl
0x18002a409  call    cs:__imp_AddAccessAllowedAce
0x18002a40f  test    eax, eax
0x18002a411  jnz     short loc_18002A447
0x18002a413  call    cs:__imp_GetLastError
0x18002a419  mov     ebx, eax
0x18002a41b  test    eax, eax
0x18002a41d  jle     short loc_18002A428
0x18002a41f  movzx   ebx, ax
0x18002a422  or      ebx, 80070000h
0x18002a428  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a42f  jz      loc_18002A539
0x18002a435  lea     rax, aErrorAddingAce; "Error adding ACE to ACL\n"
0x18002a43c  mov     r8d, 184h
0x18002a442  jmp     loc_18002A515
0x18002a447  mov     r9, [rbp+pSid]; pSid
0x18002a44b  mov     r8d, esi; AccessMask
0x18002a44e  mov     edx, 2; dwAceRevision
0x18002a453  mov     rcx, rbx; pAcl
0x18002a456  call    cs:__imp_AddAccessAllowedAce
0x18002a45c  test    eax, eax
0x18002a45e  jnz     short loc_18002A494
0x18002a460  call    cs:__imp_GetLastError
0x18002a466  mov     ebx, eax
0x18002a468  test    eax, eax
0x18002a46a  jle     short loc_18002A475
0x18002a46c  movzx   ebx, ax
0x18002a46f  or      ebx, 80070000h
0x18002a475  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a47c  jz      loc_18002A539
0x18002a482  lea     rax, aErrorAddingAce; "Error adding ACE to ACL\n"
0x18002a489  mov     r8d, 190h
0x18002a48f  jmp     loc_18002A515
0x18002a494  mov     esi, 1
0x18002a499  mov     rcx, rdi; pSecurityDescriptor
0x18002a49c  mov     edx, esi; dwRevision
0x18002a49e  call    cs:__imp_InitializeSecurityDescriptor
0x18002a4a4  test    eax, eax
0x18002a4a6  jnz     short loc_18002A4D5
0x18002a4a8  call    cs:__imp_GetLastError
0x18002a4ae  mov     ebx, eax
0x18002a4b0  test    eax, eax
0x18002a4b2  jle     short loc_18002A4BD
0x18002a4b4  movzx   ebx, ax
0x18002a4b7  or      ebx, 80070000h
0x18002a4bd  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a4c4  jz      short loc_18002A539
0x18002a4c6  lea     rax, aErrorInitializ_2; "Error initializing security descriptor"...
0x18002a4cd  mov     r8d, 19Ch
0x18002a4d3  jmp     short loc_18002A515
0x18002a4d5  xor     r9d, r9d; bDaclDefaulted
0x18002a4d8  mov     r8, rbx; pDacl
0x18002a4db  mov     edx, esi; bDaclPresent
0x18002a4dd  mov     rcx, rdi; pSecurityDescriptor
0x18002a4e0  call    cs:__imp_SetSecurityDescriptorDacl
0x18002a4e6  test    eax, eax
0x18002a4e8  jnz     short loc_18002A544
0x18002a4ea  call    cs:__imp_GetLastError
0x18002a4f0  mov     ebx, eax
0x18002a4f2  test    eax, eax
0x18002a4f4  jle     short loc_18002A4FF
0x18002a4f6  movzx   ebx, ax
0x18002a4f9  or      ebx, 80070000h
0x18002a4ff  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a506  jz      short loc_18002A539
0x18002a508  lea     rax, aErrorSettingSe; "Error setting security descriptor on AC"...
0x18002a50f  mov     r8d, 1A8h
0x18002a515  mov     rcx, cs:g_pDebug
0x18002a51c  lea     r9, aProtocolMessag_32; "PROTOCOL_MESSAGING_HANDLER::CreateRegis"...
0x18002a523  mov     [rsp+30h+var_8], rax
0x18002a528  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a52f  mov     [rsp+30h+var_10], ebx
0x18002a533  call    cs:__imp_PuDbgPrintError
0x18002a539  mov     rcx, rdi; hMem
0x18002a53c  call    cs:__imp_LocalFree
0x18002a542  jmp     short loc_18002A549
0x18002a544  xor     ebx, ebx
0x18002a546  mov     [r14], rdi
0x18002a549  cmp     [rbp+arg_0], 0
0x18002a54e  jz      short loc_18002A562
0x18002a550  lea     rcx, [rbp+arg_0]
0x18002a554  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18002a55a  mov     [rbp+arg_0], 0
0x18002a562  cmp     [rbp+pSid], 0
0x18002a567  jz      short loc_18002A573
0x18002a569  lea     rcx, [rbp+pSid]
0x18002a56d  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x18002a573  mov     eax, ebx
0x18002a575  mov     rbx, [rsp+30h+arg_8]
0x18002a57a  add     rsp, 30h
0x18002a57e  pop     r15
0x18002a580  pop     r14
0x18002a582  pop     rdi
0x18002a583  pop     rsi
0x18002a584  pop     rbp
0x18002a585  retn
```
