# AdjustProcessSecurityToAllowPowerUsersToWait(void)

- ea: `0x180032728`
- end: `0x180032a71`
- name: `?AdjustProcessSecurityToAllowPowerUsersToWait@@YAJXZ`
- size: `841`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033480`

## callees

- `0x180032728`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003276c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003276c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032a51`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18003289f`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18003289f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003295c`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18003295c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800329b3`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800329b3`
- `iisutil!PuDbgPrintError` at `0x180032a00`
- `iisutil!PuDbgPrintError` at `0x180032a00`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18003277d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x1800327bd`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x1800327fd`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18003283d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18003277d`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x1800327bd`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x1800327fd`
- `iisutil!AllocateAndCreateWellKnownSid` at `0x18003283d`
- `iisutil!FreeWellKnownSid` at `0x180032a0b`
- `iisutil!FreeWellKnownSid` at `0x180032a16`
- `iisutil!FreeWellKnownSid` at `0x180032a21`
- `iisutil!FreeWellKnownSid` at `0x180032a2c`
- `iisutil!FreeWellKnownSid` at `0x180032a0b`
- `iisutil!FreeWellKnownSid` at `0x180032a16`
- `iisutil!FreeWellKnownSid` at `0x180032a21`
- `iisutil!FreeWellKnownSid` at `0x180032a2c`
- `iisutil!SetExplicitAccessSettings` at `0x1800328fe`
- `iisutil!SetExplicitAccessSettings` at `0x180032915`
- `iisutil!SetExplicitAccessSettings` at `0x18003292c`
- `iisutil!SetExplicitAccessSettings` at `0x180032943`
- `iisutil!SetExplicitAccessSettings` at `0x1800328fe`
- `iisutil!SetExplicitAccessSettings` at `0x180032915`
- `iisutil!SetExplicitAccessSettings` at `0x18003292c`
- `iisutil!SetExplicitAccessSettings` at `0x180032943`

## string_xrefs

- `0x1800329f5`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\perf_manager.cxx`
- `0x1800327a1`: `Creating Power User SID failed\n`
- `0x1800329e9`: `AdjustProcessSecurityToAllowPowerUsersToWait`
- `0x1800327e1`: `Creating System Operators SID failed\n`
- `0x180032821`: `Creating perf log user SID failed\n`
- `0x180032861`: `Creating perf mon user SID failed\n`
- `0x1800328c3`: `Could not get security info for the current process \n`
- `0x180032980`: `Could not set Acls into security descriptor \n`
- `0x1800329d5`: `Could not set process security info \n`

## pseudocode

```c
__int64 AdjustProcessSecurityToAllowPowerUsersToWait(void)
{
  HANDLE CurrentProcess; // rdi
  int v1; // eax
  unsigned int v2; // ebx
  const char *v3; // rax
  __int64 v4; // r8
  int v5; // eax
  int v6; // eax
  int v7; // eax
  signed int SecurityInfo; // eax
  __int64 v9; // rcx
  struct _EXPLICIT_ACCESS_W *p_pListOfExplicitEntries; // rax
  signed int v11; // eax
  signed int v12; // eax
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  void *v15; // [rsp+48h] [rbp-B8h] BYREF
  void *v16; // [rsp+50h] [rbp-B0h] BYREF
  void *v17; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+60h] [rbp-A0h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-98h] BYREF
  PACL OldAcl; // [rsp+70h] [rbp-90h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+80h] [rbp-80h] BYREF
  struct _EXPLICIT_ACCESS_W v22; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXPLICIT_ACCESS_W v23; // [rsp+E0h] [rbp-20h] BYREF
  struct _EXPLICIT_ACCESS_W v24; // [rsp+110h] [rbp+10h] BYREF

  v14 = 0;
  v15 = 0;
  v17 = 0;
  v16 = 0;
  NewAcl = 0;
  OldAcl = 0;
  hMem = 0;
  CurrentProcess = GetCurrentProcess();
  v1 = AllocateAndCreateWellKnownSid(WinBuiltinPowerUsersSid, &v14);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      v3 = "Creating Power User SID failed\n";
      v4 = 3357;
LABEL_39:
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\perf_manager.cxx",
        v4,
        "AdjustProcessSecurityToAllowPowerUsersToWait",
        v2,
        v3);
    }
  }
  else
  {
    v5 = AllocateAndCreateWellKnownSid(WinBuiltinSystemOperatorsSid, &v15);
    v2 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        v3 = "Creating System Operators SID failed\n";
        v4 = 3376;
        goto LABEL_39;
      }
    }
    else
    {
      v6 = AllocateAndCreateWellKnownSid(WinBuiltinPerfLoggingUsersSid, &v16);
      v2 = v6;
      if ( v6 )
      {
        if ( v6 > 0 )
          v2 = (unsigned __int16)v6 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          v3 = "Creating perf log user SID failed\n";
          v4 = 3394;
          goto LABEL_39;
        }
      }
      else
      {
        v7 = AllocateAndCreateWellKnownSid(WinBuiltinPerfMonitoringUsersSid, &v17);
        v2 = v7;
        if ( v7 )
        {
          if ( v7 > 0 )
            v2 = (unsigned __int16)v7 | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            v3 = "Creating perf mon user SID failed\n";
            v4 = 3412;
            goto LABEL_39;
          }
        }
        else
        {
          SecurityInfo = GetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
          v2 = SecurityInfo;
          if ( SecurityInfo )
          {
            if ( SecurityInfo > 0 )
              v2 = (unsigned __int16)SecurityInfo | 0x80070000;
            if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              v3 = "Could not get security info for the current process \n";
              v4 = 3441;
              goto LABEL_39;
            }
          }
          else
          {
            v9 = 192;
            p_pListOfExplicitEntries = &pListOfExplicitEntries;
            do
            {
              LOBYTE(p_pListOfExplicitEntries->grfAccessPermissions) = 0;
              p_pListOfExplicitEntries = (struct _EXPLICIT_ACCESS_W *)((char *)p_pListOfExplicitEntries + 1);
              --v9;
            }
            while ( v9 );
            SetExplicitAccessSettings(&pListOfExplicitEntries, 0x100000u, GRANT_ACCESS, v14);
            SetExplicitAccessSettings(&v22, 0x100000u, GRANT_ACCESS, v15);
            SetExplicitAccessSettings(&v23, 0x100000u, GRANT_ACCESS, v17);
            SetExplicitAccessSettings(&v24, 0x100000u, GRANT_ACCESS, v16);
            v11 = SetEntriesInAclW(4u, &pListOfExplicitEntries, OldAcl, &NewAcl);
            v2 = v11;
            if ( v11 )
            {
              if ( v11 > 0 )
                v2 = (unsigned __int16)v11 | 0x80070000;
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                v3 = "Could not set Acls into security descriptor \n";
                v4 = 3484;
                goto LABEL_39;
              }
            }
            else
            {
              v2 = 0;
              v12 = SetSecurityInfo(CurrentProcess, SE_KERNEL_OBJECT, 4u, 0, 0, NewAcl, 0);
              if ( v12 )
              {
                v2 = v12 > 0 ? (unsigned __int16)v12 | 0x80070000 : v12;
                if ( (g_dwDebugFlags & 0xF) != 0 )
                {
                  v3 = "Could not set process security info \n";
                  v4 = 3506;
                  goto LABEL_39;
                }
              }
            }
          }
        }
      }
    }
  }
  FreeWellKnownSid(&v14);
  FreeWellKnownSid(&v15);
  FreeWellKnownSid(&v16);
  FreeWellKnownSid(&v17);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( NewAcl )
    LocalFree(NewAcl);
  return v2;
}

```

## disassembly

```asm
0x180032728  push    rbp
0x18003272a  push    rbx
0x18003272b  push    rsi
0x18003272c  push    rdi
0x18003272d  lea     rbp, [rsp-58h]
0x180032732  sub     rsp, 158h
0x180032739  mov     rax, cs:__security_cookie
0x180032740  xor     rax, rsp
0x180032743  mov     [rbp+70h+var_30], rax
0x180032747  xor     esi, esi
0x180032749  mov     [rsp+170h+var_130], rsi
0x18003274e  mov     [rsp+170h+var_128], rsi
0x180032753  mov     [rsp+170h+var_118], rsi
0x180032758  mov     [rsp+170h+var_120], rsi
0x18003275d  mov     [rsp+170h+NewAcl], rsi
0x180032762  mov     [rsp+170h+OldAcl], rsi
0x180032767  mov     [rsp+170h+hMem], rsi
0x18003276c  call    cs:__imp_GetCurrentProcess
0x180032772  lea     rdx, [rsp+170h+var_130]
0x180032777  mov     rdi, rax
0x18003277a  lea     ecx, [rsi+1Dh]
0x18003277d  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180032783  mov     ebx, eax
0x180032785  test    eax, eax
0x180032787  jz      short loc_1800327B3
0x180032789  jle     short loc_180032794
0x18003278b  movzx   ebx, ax
0x18003278e  or      ebx, 80070000h
0x180032794  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18003279b  jz      loc_180032A06
0x1800327a1  lea     rax, aCreatingPowerU; "Creating Power User SID failed\n"
0x1800327a8  mov     r8d, 0D1Dh
0x1800327ae  jmp     loc_1800329E2
0x1800327b3  lea     rdx, [rsp+170h+var_128]
0x1800327b8  mov     ecx, 1Fh
0x1800327bd  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800327c3  mov     ebx, eax
0x1800327c5  test    eax, eax
0x1800327c7  jz      short loc_1800327F3
0x1800327c9  jle     short loc_1800327D4
0x1800327cb  movzx   ebx, ax
0x1800327ce  or      ebx, 80070000h
0x1800327d4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800327db  jz      loc_180032A06
0x1800327e1  lea     rax, aCreatingSystem; "Creating System Operators SID failed\n"
0x1800327e8  mov     r8d, 0D30h
0x1800327ee  jmp     loc_1800329E2
0x1800327f3  lea     rdx, [rsp+170h+var_120]
0x1800327f8  mov     ecx, 3Ah ; ':'
0x1800327fd  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180032803  mov     ebx, eax
0x180032805  test    eax, eax
0x180032807  jz      short loc_180032833
0x180032809  jle     short loc_180032814
0x18003280b  movzx   ebx, ax
0x18003280e  or      ebx, 80070000h
0x180032814  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18003281b  jz      loc_180032A06
0x180032821  lea     rax, aCreatingPerfLo; "Creating perf log user SID failed\n"
0x180032828  mov     r8d, 0D42h
0x18003282e  jmp     loc_1800329E2
0x180032833  lea     rdx, [rsp+170h+var_118]
0x180032838  mov     ecx, 39h ; '9'
0x18003283d  call    cs:__imp_?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180032843  mov     ebx, eax
0x180032845  test    eax, eax
0x180032847  jz      short loc_180032873
0x180032849  jle     short loc_180032854
0x18003284b  movzx   ebx, ax
0x18003284e  or      ebx, 80070000h
0x180032854  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18003285b  jz      loc_180032A06
0x180032861  lea     rax, aCreatingPerfMo; "Creating perf mon user SID failed\n"
0x180032868  mov     r8d, 0D54h
0x18003286e  jmp     loc_1800329E2
0x180032873  xor     r9d, r9d; ppsidOwner
0x180032876  lea     rax, [rsp+170h+hMem]
0x18003287b  mov     [rsp+170h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180032880  mov     rcx, rdi; handle
0x180032883  lea     rax, [rsp+170h+OldAcl]
0x180032888  mov     [rsp+170h+ppSacl], rsi; ppSacl
0x18003288d  mov     [rsp+170h+ppDacl], rax; ppDacl
0x180032892  lea     edx, [r9+6]; ObjectType
0x180032896  mov     [rsp+170h+ppsidGroup], rsi; ppsidGroup
0x18003289b  lea     r8d, [r9+4]; SecurityInfo
0x18003289f  call    cs:__imp_GetSecurityInfo
0x1800328a5  mov     ebx, eax
0x1800328a7  test    eax, eax
0x1800328a9  jz      short loc_1800328D5
0x1800328ab  jle     short loc_1800328B6
0x1800328ad  movzx   ebx, ax
0x1800328b0  or      ebx, 80070000h
0x1800328b6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800328bd  jz      loc_180032A06
0x1800328c3  lea     rax, aCouldNotGetSec; "Could not get security info for the cur"...
0x1800328ca  mov     r8d, 0D71h
0x1800328d0  jmp     loc_1800329E2
0x1800328d5  mov     ecx, 0C0h
0x1800328da  lea     rax, [rbp+70h+pListOfExplicitEntries]
0x1800328de  mov     [rax], sil
0x1800328e1  inc     rax
0x1800328e4  sub     rcx, 1
0x1800328e8  jnz     short loc_1800328DE
0x1800328ea  mov     r9, [rsp+170h+var_130]
0x1800328ef  lea     r8d, [rcx+1]
0x1800328f3  mov     ebx, 100000h
0x1800328f8  lea     rcx, [rbp+70h+pListOfExplicitEntries]
0x1800328fc  mov     edx, ebx
0x1800328fe  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x180032904  mov     r9, [rsp+170h+var_128]
0x180032909  lea     rcx, [rbp+70h+var_C0]
0x18003290d  mov     r8d, 1
0x180032913  mov     edx, ebx
0x180032915  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x18003291b  mov     r9, [rsp+170h+var_118]
0x180032920  lea     rcx, [rbp+70h+var_90]
0x180032924  mov     r8d, 1
0x18003292a  mov     edx, ebx
0x18003292c  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x180032932  mov     r9, [rsp+170h+var_120]
0x180032937  lea     rcx, [rbp+70h+var_60]
0x18003293b  mov     r8d, 1
0x180032941  mov     edx, ebx
0x180032943  call    cs:__imp_?SetExplicitAccessSettings@@YAXPEAU_EXPLICIT_ACCESS_W@@KW4_ACCESS_MODE@@PEAX@Z; SetExplicitAccessSettings(_EXPLICIT_ACCESS_W *,ulong,_ACCESS_MODE,void *)
0x180032949  mov     r8, [rsp+170h+OldAcl]; OldAcl
0x18003294e  lea     r9, [rsp+170h+NewAcl]; NewAcl
0x180032953  lea     rdx, [rbp+70h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180032957  mov     ecx, 4; cCountOfExplicitEntries
0x18003295c  call    cs:__imp_SetEntriesInAclW
0x180032962  mov     ebx, eax
0x180032964  test    eax, eax
0x180032966  jz      short loc_18003298F
0x180032968  jle     short loc_180032973
0x18003296a  movzx   ebx, ax
0x18003296d  or      ebx, 80070000h
0x180032973  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18003297a  jz      loc_180032A06
0x180032980  lea     rax, aCouldNotSetAcl; "Could not set Acls into security descri"...
0x180032987  mov     r8d, 0D9Ch
0x18003298d  jmp     short loc_1800329E2
0x18003298f  mov     rax, [rsp+170h+NewAcl]
0x180032994  xor     r9d, r9d; psidOwner
0x180032997  mov     [rsp+170h+ppSacl], rsi; pSacl
0x18003299c  mov     rcx, rdi; handle
0x18003299f  mov     [rsp+170h+ppDacl], rax; pDacl
0x1800329a4  mov     ebx, esi
0x1800329a6  mov     [rsp+170h+ppsidGroup], rsi; psidGroup
0x1800329ab  lea     edx, [r9+6]; ObjectType
0x1800329af  lea     r8d, [r9+4]; SecurityInfo
0x1800329b3  call    cs:__imp_SetSecurityInfo
0x1800329b9  test    eax, eax
0x1800329bb  jz      short loc_180032A06
0x1800329bd  jg      short loc_1800329C3
0x1800329bf  mov     ebx, eax
0x1800329c1  jmp     short loc_1800329CC
0x1800329c3  movzx   ebx, ax
0x1800329c6  or      ebx, 80070000h
0x1800329cc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800329d3  jz      short loc_180032A06
0x1800329d5  lea     rax, aCouldNotSetPro; "Could not set process security info \n"
0x1800329dc  mov     r8d, 0DB2h
0x1800329e2  mov     rcx, cs:g_pDebug
0x1800329e9  lea     r9, aAdjustprocesss; "AdjustProcessSecurityToAllowPowerUsersT"...
0x1800329f0  mov     [rsp+170h+ppDacl], rax
0x1800329f5  lea     rdx, aServercommonIn_15; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800329fc  mov     dword ptr [rsp+170h+ppsidGroup], ebx
0x180032a00  call    cs:__imp_PuDbgPrintError
0x180032a06  lea     rcx, [rsp+170h+var_130]
0x180032a0b  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180032a11  lea     rcx, [rsp+170h+var_128]
0x180032a16  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180032a1c  lea     rcx, [rsp+170h+var_120]
0x180032a21  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180032a27  lea     rcx, [rsp+170h+var_118]
0x180032a2c  call    cs:__imp_?FreeWellKnownSid@@YAXPEAPEAX@Z; FreeWellKnownSid(void * *)
0x180032a32  mov     rcx, [rsp+170h+hMem]; hMem
0x180032a37  test    rcx, rcx
0x180032a3a  jz      short loc_180032A47
0x180032a3c  call    cs:__imp_LocalFree
0x180032a42  mov     [rsp+170h+hMem], rsi
0x180032a47  mov     rcx, [rsp+170h+NewAcl]; hMem
0x180032a4c  test    rcx, rcx
0x180032a4f  jz      short loc_180032A57
0x180032a51  call    cs:__imp_LocalFree
0x180032a57  mov     eax, ebx
0x180032a59  mov     rcx, [rbp+70h+var_30]
0x180032a5d  xor     rcx, rsp; StackCookie
0x180032a60  call    __security_check_cookie
0x180032a65  add     rsp, 158h
0x180032a6c  pop     rdi
0x180032a6d  pop     rsi
0x180032a6e  pop     rbx
0x180032a6f  pop     rbp
0x180032a70  retn
```
