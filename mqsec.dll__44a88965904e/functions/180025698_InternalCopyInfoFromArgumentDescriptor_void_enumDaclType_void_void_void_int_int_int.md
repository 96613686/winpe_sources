# InternalCopyInfoFromArgumentDescriptor(void *,enumDaclType,void *,void * *,void * *,int *,int *,int *)

- ea: `0x180025698`
- end: `0x180025cc7`
- name: `?InternalCopyInfoFromArgumentDescriptor@@YAJPEAXW4enumDaclType@@0PEAPEAX2PEAH33@Z`
- size: `1583`
- prototype: `__int64 __fastcall(void *, int, void *, PSID *, PSID *pGroup, WINBOOL *lpbDaclPresent, WINBOOL *lpbOwnerDefaulted, WINBOOL *lpbGroupDefaulted)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025eac`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x180017430`
- `0x180025698`
- `0x180028104`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorControl` at `0x180025b0d`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180025c5b`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180025b0d`
- `ADVAPI32!SetSecurityDescriptorControl` at `0x180025c5b`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180025be9`
- `ADVAPI32!SetSecurityDescriptorSacl` at `0x180025be9`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800258ff`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800258ff`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180025857`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180025857`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002576c`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002576c`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800256bd`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800256bd`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180025b85`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180025b85`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180025a72`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180025a72`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800259c1`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800259c1`
- `KERNEL32!GetLastError` at `0x1800256ce`
- `KERNEL32!GetLastError` at `0x18002577a`
- `KERNEL32!GetLastError` at `0x180025861`
- `KERNEL32!GetLastError` at `0x180025909`
- `KERNEL32!GetLastError` at `0x1800259cf`
- `KERNEL32!GetLastError` at `0x180025a7f`
- `KERNEL32!GetLastError` at `0x180025b17`
- `KERNEL32!GetLastError` at `0x180025b8f`
- `KERNEL32!GetLastError` at `0x180025bf3`
- `KERNEL32!GetLastError` at `0x180025c68`
- `KERNEL32!GetLastError` at `0x1800256ce`
- `KERNEL32!GetLastError` at `0x18002577a`
- `KERNEL32!GetLastError` at `0x180025861`
- `KERNEL32!GetLastError` at `0x180025909`
- `KERNEL32!GetLastError` at `0x1800259cf`
- `KERNEL32!GetLastError` at `0x180025a7f`
- `KERNEL32!GetLastError` at `0x180025b17`
- `KERNEL32!GetLastError` at `0x180025b8f`
- `KERNEL32!GetLastError` at `0x180025bf3`
- `KERNEL32!GetLastError` at `0x180025c68`

## pseudocode

```c
__int64 __fastcall InternalCopyInfoFromArgumentDescriptor(
        void *a1,
        int a2,
        void *a3,
        PSID *a4,
        PSID *pGroup,
        WINBOOL *lpbDaclPresent,
        WINBOOL *lpbOwnerDefaulted,
        WINBOOL *lpbGroupDefaulted)
{
  DWORD v11; // eax
  unsigned int v12; // eax
  DWORD LastError; // eax
  unsigned int v15; // edi
  __int16 v16; // ax
  unsigned int v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  __int16 v22; // ax
  int v23; // r12d
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  WORD pControl; // [rsp+60h] [rbp-41h] BYREF
  __int16 v29; // [rsp+68h] [rbp-39h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+70h] [rbp-31h] BYREF
  WINBOOL bSaclPresent; // [rsp+74h] [rbp-2Dh] BYREF
  unsigned int v32; // [rsp+78h] [rbp-29h] BYREF
  DWORD dwRevision; // [rsp+80h] [rbp-21h] BYREF
  PACL pDacl; // [rsp+88h] [rbp-19h] BYREF
  PACL pSacl; // [rsp+90h] [rbp-11h] BYREF

  if ( IsValidSecurityDescriptor(a1) )
  {
    dwRevision = 0;
    pControl = 0;
    if ( !GetSecurityDescriptorControl(a1, &pControl, &dwRevision) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 32, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, LastError);
      if ( !v15 )
        return v15;
      v16 = 1001;
LABEL_12:
      v32 = v15;
      v29 = v16;
      if ( !g_pMSMQErrorLoggingTrace )
        goto LABEL_14;
      goto LABEL_13;
    }
    if ( !GetSecurityDescriptorOwner(a1, a4, lpbOwnerDefaulted) )
    {
      v18 = GetLastError();
      v15 = v18;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 33, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v18);
      if ( !v15 )
        return v15;
      v16 = 1002;
      goto LABEL_12;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), *lpbOwnerDefaulted);
    if ( !GetSecurityDescriptorGroup(a1, pGroup, lpbGroupDefaulted) )
    {
      v19 = GetLastError();
      v15 = v19;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 35, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v19);
      if ( !v15 )
        return v15;
      v29 = 1003;
      v32 = v15;
      if ( !g_pMSMQErrorLoggingTrace )
        goto LABEL_14;
      goto LABEL_13;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF__sid_D(*((_QWORD *)WPP_GLOBAL_Control + 32), *lpbGroupDefaulted);
    bDaclDefaulted = 0;
    pDacl = 0;
    if ( !GetSecurityDescriptorDacl(a1, lpbDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v20 = GetLastError();
      v15 = v20;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 37, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v20);
      if ( !v15 )
        return v15;
      v29 = 1004;
      v32 = v15;
      if ( !g_pMSMQErrorLoggingTrace )
        goto LABEL_14;
      goto LABEL_13;
    }
    if ( *lpbDaclPresent )
    {
      if ( !SetSecurityDescriptorDacl(a3, 1, pDacl, bDaclDefaulted) )
      {
        v21 = GetLastError();
        v15 = v21;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 38, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v21);
        if ( !v15 )
          return v15;
        v22 = 1005;
        goto LABEL_50;
      }
      v23 = a2;
      if ( a2 == 2 && !SetSecurityDescriptorControl(a3, 0x1500u, pControl & 0x1500) )
      {
        v24 = GetLastError();
        v15 = v24;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 39, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v24);
        if ( !v15 )
          return v15;
        v22 = 1006;
        goto LABEL_50;
      }
    }
    else
    {
      v23 = a2;
    }
    pSacl = 0;
    bSaclPresent = 0;
    if ( GetSecurityDescriptorSacl(a1, &bSaclPresent, &pSacl, &bDaclDefaulted) )
    {
      if ( SetSecurityDescriptorSacl(a3, bSaclPresent, pSacl, bDaclDefaulted) )
      {
        if ( !bSaclPresent || v23 != 2 || SetSecurityDescriptorControl(a3, 0x2A00u, pControl & 0x2A00) )
          return 0;
        v27 = GetLastError();
        v15 = v27;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 42, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v27);
        if ( !v15 )
          return v15;
        v22 = 1009;
      }
      else
      {
        v26 = GetLastError();
        v15 = v26;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 41, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v26);
        if ( !v15 )
          return v15;
        v22 = 1008;
      }
    }
    else
    {
      v25 = GetLastError();
      v15 = v25;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 40, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids, v25);
      if ( !v15 )
        return v15;
      v22 = 1007;
    }
LABEL_50:
    v29 = v22;
    v32 = v15;
    if ( !g_pMSMQErrorLoggingTrace )
    {
LABEL_14:
      if ( (int)v15 > 0 )
        return (unsigned __int16)v15 | 0x80070000;
      return v15;
    }
LABEL_13:
    v17 = mqwcslen(L"acssctrl/secdscrp");
    CMSMQTrace::MSMQTraceEvent(
      g_pMSMQErrorLoggingTrace,
      1,
      2,
      2LL * (v17 + 1),
      L"acssctrl/secdscrp",
      2,
      &v29,
      4,
      &v32,
      0,
      0);
    goto LABEL_14;
  }
  v11 = GetLastError();
  if ( v11 )
  {
    v29 = 1000;
    v32 = v11;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v12 = mqwcslen(L"acssctrl/secdscrp");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        2,
        2LL * (v12 + 1),
        L"acssctrl/secdscrp",
        2,
        &v29,
        4,
        &v32,
        0,
        0);
    }
  }
  return 3222142977LL;
}

```

## disassembly

```asm
0x180025698  mov     [rsp-8+arg_8], edx
0x18002569c  push    rbp
0x18002569d  push    rbx
0x18002569e  push    rsi
0x18002569f  push    rdi
0x1800256a0  push    r12
0x1800256a2  push    r13
0x1800256a4  push    r14
0x1800256a6  push    r15
0x1800256a8  lea     rbp, [rsp-7]
0x1800256ad  sub     rsp, 0A8h
0x1800256b4  mov     r14, r9
0x1800256b7  mov     r13, r8
0x1800256ba  mov     rdi, rcx
0x1800256bd  call    cs:__imp_IsValidSecurityDescriptor
0x1800256c3  xor     r12d, r12d
0x1800256c6  test    eax, eax
0x1800256c8  jnz     loc_180025758
0x1800256ce  call    cs:__imp_GetLastError
0x1800256d4  test    eax, eax
0x1800256d6  jz      short loc_18002574E
0x1800256d8  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800256df  mov     ecx, 3E8h
0x1800256e4  mov     [rbp+3Fh+var_78], cx
0x1800256e8  mov     [rbp+3Fh+var_68], eax
0x1800256eb  jz      short loc_18002574E
0x1800256ed  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x1800256f4  mov     rcx, rsi; wchar_t *
0x1800256f7  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800256fc  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180025703  lea     ebx, [r12+1]
0x180025708  mov     [rsp+0E0h+var_90], r12
0x18002570d  lea     r14d, [r12+2]
0x180025712  mov     [rsp+0E0h+var_98], r12
0x180025717  lea     r15d, [r12+4]
0x18002571c  lea     r9d, [rbx+rax]
0x180025720  mov     r8d, r14d
0x180025723  lea     rax, [rbp+3Fh+var_68]
0x180025727  add     r9, r9
0x18002572a  mov     [rsp+0E0h+var_A0], rax
0x18002572f  mov     edx, ebx
0x180025731  mov     [rsp+0E0h+var_A8], r15
0x180025736  lea     rax, [rbp+3Fh+var_78]
0x18002573a  mov     [rsp+0E0h+var_B0], rax
0x18002573f  mov     [rsp+0E0h+var_B8], r14
0x180025744  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x180025749  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18002574e  mov     eax, 0C00E0001h
0x180025753  jmp     loc_180025CB3
0x180025758  lea     r8, [rbp+3Fh+dwRevision]; lpdwRevision
0x18002575c  mov     [rbp+3Fh+dwRevision], r12d
0x180025760  lea     rdx, [rbp+3Fh+pControl]; pControl
0x180025764  mov     [rbp+3Fh+pControl], r12w
0x180025769  mov     rcx, rdi; pSecurityDescriptor
0x18002576c  call    cs:__imp_GetSecurityDescriptorControl
0x180025772  test    eax, eax
0x180025774  jnz     loc_18002584A
0x18002577a  call    cs:__imp_GetLastError
0x180025780  mov     edi, eax
0x180025782  mov     rcx, cs:WPP_GLOBAL_Control
0x180025789  lea     rsi, WPP_GLOBAL_Control
0x180025790  mov     ebx, 1
0x180025795  cmp     rcx, rsi
0x180025798  jz      short loc_1800257BB
0x18002579a  test    [rcx+10Ch], bl
0x1800257a0  jz      short loc_1800257BB
0x1800257a2  mov     rcx, [rcx+100h]
0x1800257a9  lea     edx, [rbx+1Fh]
0x1800257ac  mov     r9d, eax
0x1800257af  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x1800257b6  call    WPP_SF_d
0x1800257bb  test    edi, edi
0x1800257bd  jz      loc_180025843
0x1800257c3  mov     eax, 3E9h
0x1800257c8  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800257cf  mov     [rbp+3Fh+var_68], edi
0x1800257d2  mov     [rbp+3Fh+var_78], ax
0x1800257d6  jz      short loc_180025836
0x1800257d8  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x1800257df  mov     rcx, rsi; wchar_t *
0x1800257e2  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800257e7  mov     r15d, 4
0x1800257ed  mov     [rsp+0E0h+var_90], r12
0x1800257f2  mov     [rsp+0E0h+var_98], r12
0x1800257f7  mov     r14d, 2
0x1800257fd  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180025804  lea     r9d, [rbx+rax]
0x180025808  lea     rax, [rbp+3Fh+var_68]
0x18002580c  add     r9, r9
0x18002580f  mov     [rsp+0E0h+var_A0], rax
0x180025814  mov     r8d, r14d
0x180025817  mov     [rsp+0E0h+var_A8], r15
0x18002581c  lea     rax, [rbp+3Fh+var_78]
0x180025820  mov     [rsp+0E0h+var_B0], rax
0x180025825  mov     edx, ebx
0x180025827  mov     [rsp+0E0h+var_B8], r14
0x18002582c  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x180025831  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180025836  test    edi, edi
0x180025838  jle     short loc_180025843
0x18002583a  movzx   edi, di
0x18002583d  or      edi, 80070000h
0x180025843  mov     eax, edi
0x180025845  jmp     loc_180025CB3
0x18002584a  mov     rbx, [rbp+3Fh+lpbOwnerDefaulted]
0x18002584e  mov     rdx, r14; pOwner
0x180025851  mov     r8, rbx; lpbOwnerDefaulted
0x180025854  mov     rcx, rdi; pSecurityDescriptor
0x180025857  call    cs:__imp_GetSecurityDescriptorOwner
0x18002585d  test    eax, eax
0x18002585f  jnz     short loc_1800258B0
0x180025861  call    cs:__imp_GetLastError
0x180025867  mov     edi, eax
0x180025869  mov     rcx, cs:WPP_GLOBAL_Control
0x180025870  lea     rsi, WPP_GLOBAL_Control
0x180025877  mov     ebx, 1
0x18002587c  cmp     rcx, rsi
0x18002587f  jz      short loc_1800258A2
0x180025881  test    [rcx+10Ch], bl
0x180025887  jz      short loc_1800258A2
0x180025889  mov     rcx, [rcx+100h]
0x180025890  lea     edx, [rbx+20h]
0x180025893  mov     r9d, eax
0x180025896  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x18002589d  call    WPP_SF_d
0x1800258a2  test    edi, edi
0x1800258a4  jz      short loc_180025843
0x1800258a6  mov     eax, 3EAh
0x1800258ab  jmp     loc_1800257C8
0x1800258b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258b7  lea     rsi, WPP_GLOBAL_Control
0x1800258be  mov     r15d, 4
0x1800258c4  cmp     rcx, rsi
0x1800258c7  jz      short loc_1800258EB
0x1800258c9  test    [rcx+10Ch], r15b
0x1800258d0  jz      short loc_1800258EB
0x1800258d2  mov     eax, [rbx]
0x1800258d4  lea     edx, [r15+1Eh]
0x1800258d8  mov     r9, [r14]
0x1800258db  mov     rcx, [rcx+100h]; LoggerHandle
0x1800258e2  mov     dword ptr [rsp+0E0h+var_C0], eax; char
0x1800258e6  call    WPP_SF__sid_D
0x1800258eb  mov     rbx, [rbp+3Fh+lpbGroupDefaulted]
0x1800258f2  mov     rcx, rdi; pSecurityDescriptor
0x1800258f5  mov     r14, [rbp+3Fh+pGroup]
0x1800258f9  mov     r8, rbx; lpbGroupDefaulted
0x1800258fc  mov     rdx, r14; pGroup
0x1800258ff  call    cs:__imp_GetSecurityDescriptorGroup
0x180025905  test    eax, eax
0x180025907  jnz     short loc_180025978
0x180025909  call    cs:__imp_GetLastError
0x18002590f  mov     edi, eax
0x180025911  mov     rcx, cs:WPP_GLOBAL_Control
0x180025918  mov     ebx, 1
0x18002591d  cmp     rcx, rsi
0x180025920  jz      short loc_180025943
0x180025922  test    [rcx+10Ch], bl
0x180025928  jz      short loc_180025943
0x18002592a  mov     rcx, [rcx+100h]
0x180025931  lea     edx, [rbx+22h]
0x180025934  mov     r9d, eax
0x180025937  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x18002593e  call    WPP_SF_d
0x180025943  test    edi, edi
0x180025945  jz      loc_180025843
0x18002594b  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180025952  mov     eax, 3EBh
0x180025957  mov     [rbp+3Fh+var_78], ax
0x18002595b  mov     [rbp+3Fh+var_68], edi
0x18002595e  jz      loc_180025836
0x180025964  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x18002596b  mov     rcx, rsi; wchar_t *
0x18002596e  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180025973  jmp     loc_1800257ED
0x180025978  mov     rcx, cs:WPP_GLOBAL_Control
0x18002597f  cmp     rcx, rsi
0x180025982  jz      short loc_1800259A7
0x180025984  test    [rcx+10Ch], r15b
0x18002598b  jz      short loc_1800259A7
0x18002598d  mov     eax, [rbx]
0x18002598f  mov     edx, 24h ; '$'
0x180025994  mov     r9, [r14]
0x180025997  mov     rcx, [rcx+100h]; LoggerHandle
0x18002599e  mov     dword ptr [rsp+0E0h+var_C0], eax; char
0x1800259a2  call    WPP_SF__sid_D
0x1800259a7  mov     [rbp+3Fh+bDaclDefaulted], r12d
0x1800259ab  lea     r9, [rbp+3Fh+bDaclDefaulted]; lpbDaclDefaulted
0x1800259af  mov     [rbp+3Fh+pDacl], r12
0x1800259b3  lea     r8, [rbp+3Fh+pDacl]; pDacl
0x1800259b7  mov     r12, [rbp+3Fh+lpbDaclPresent]
0x1800259bb  mov     rcx, rdi; pSecurityDescriptor
0x1800259be  mov     rdx, r12; lpbDaclPresent
0x1800259c1  call    cs:__imp_GetSecurityDescriptorDacl
0x1800259c7  test    eax, eax
0x1800259c9  jnz     loc_180025A51
0x1800259cf  call    cs:__imp_GetLastError
0x1800259d5  mov     edi, eax
0x1800259d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259de  mov     ebx, 1
0x1800259e3  cmp     rcx, rsi
0x1800259e6  jz      short loc_180025A09
0x1800259e8  test    [rcx+10Ch], bl
0x1800259ee  jz      short loc_180025A09
0x1800259f0  mov     rcx, [rcx+100h]
0x1800259f7  lea     edx, [rbx+24h]
0x1800259fa  mov     r9d, eax
0x1800259fd  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180025a04  call    WPP_SF_d
0x180025a09  test    edi, edi
0x180025a0b  jz      loc_180025843
0x180025a11  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180025a19  mov     eax, 3ECh
0x180025a1e  mov     [rbp+3Fh+var_78], ax
0x180025a22  mov     [rbp+3Fh+var_68], edi
0x180025a25  jz      loc_180025836
0x180025a2b  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180025a32  mov     rcx, rsi; wchar_t *
0x180025a35  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180025a3a  mov     [rsp+0E0h+var_90], 0
0x180025a43  mov     [rsp+0E0h+var_98], 0
0x180025a4c  jmp     loc_1800257F7
0x180025a51  cmp     dword ptr [r12], 0
0x180025a56  mov     ebx, 1
0x180025a5b  lea     r14d, [rbx+1]
0x180025a5f  jz      loc_180025B63
0x180025a65  mov     r9d, [rbp+3Fh+bDaclDefaulted]; bDaclDefaulted
0x180025a69  mov     edx, ebx; bDaclPresent
0x180025a6b  mov     r8, [rbp+3Fh+pDacl]; pDacl
0x180025a6f  mov     rcx, r13; pSecurityDescriptor
0x180025a72  call    cs:__imp_SetSecurityDescriptorDacl
0x180025a78  xor     r12d, r12d
0x180025a7b  test    eax, eax
0x180025a7d  jnz     short loc_180025AF3
0x180025a7f  call    cs:__imp_GetLastError
0x180025a85  mov     edi, eax
0x180025a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a8e  cmp     rcx, rsi
0x180025a91  jz      short loc_180025AB4
0x180025a93  test    [rcx+10Ch], bl
0x180025a99  jz      short loc_180025AB4
0x180025a9b  mov     rcx, [rcx+100h]
0x180025aa2  lea     edx, [rbx+25h]
0x180025aa5  mov     r9d, eax
0x180025aa8  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180025aaf  call    WPP_SF_d
0x180025ab4  test    edi, edi
0x180025ab6  jz      loc_180025843
0x180025abc  mov     eax, 3EDh
0x180025ac1  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, r12; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180025ac8  mov     [rbp+3Fh+var_78], ax
0x180025acc  mov     [rbp+3Fh+var_68], edi
0x180025acf  jz      loc_180025836
0x180025ad5  lea     rsi, aAcssctrlSecdsc; "acssctrl/secdscrp"
0x180025adc  mov     rcx, rsi; wchar_t *
0x180025adf  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180025ae4  mov     [rsp+0E0h+var_90], r12
0x180025ae9  mov     [rsp+0E0h+var_98], r12
0x180025aee  jmp     loc_1800257FD
0x180025af3  mov     r12d, [rbp+3Fh+arg_8]
0x180025af7  cmp     r12d, r14d
0x180025afa  jnz     short loc_180025B67
0x180025afc  movzx   r8d, [rbp+3Fh+pControl]
0x180025b01  mov     edx, 1500h; ControlBitsOfInterest
0x180025b06  and     r8w, dx; ControlBitsToSet
0x180025b0a  mov     rcx, r13; pSecurityDescriptor
0x180025b0d  call    cs:__imp_SetSecurityDescriptorControl
0x180025b13  test    eax, eax
0x180025b15  jnz     short loc_180025B67
0x180025b17  call    cs:__imp_GetLastError
0x180025b1d  mov     edi, eax
0x180025b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b26  cmp     rcx, rsi
0x180025b29  jz      short loc_180025B4E
0x180025b2b  test    [rcx+10Ch], bl
0x180025b31  jz      short loc_180025B4E
0x180025b33  mov     rcx, [rcx+100h]
0x180025b3a  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x180025b41  mov     edx, 27h ; '''
0x180025b46  mov     r9d, eax
0x180025b49  call    WPP_SF_d
0x180025b4e  xor     r12d, r12d
0x180025b51  test    edi, edi
0x180025b53  jz      loc_180025843
0x180025b59  mov     eax, 3EEh
0x180025b5e  jmp     loc_180025AC1
0x180025b63  mov     r12d, [rbp+3Fh+arg_8]
0x180025b67  lea     r9, [rbp+3Fh+bDaclDefaulted]; lpbSaclDefaulted
0x180025b6b  mov     [rbp+3Fh+pSacl], 0
0x180025b73  lea     r8, [rbp+3Fh+pSacl]; pSacl
0x180025b77  mov     [rbp+3Fh+bSaclPresent], 0
0x180025b7e  lea     rdx, [rbp+3Fh+bSaclPresent]; lpbSaclPresent
0x180025b82  mov     rcx, rdi; pSecurityDescriptor
0x180025b85  call    cs:__imp_GetSecurityDescriptorSacl
0x180025b8b  test    eax, eax
0x180025b8d  jnz     short loc_180025BDB
0x180025b8f  call    cs:__imp_GetLastError
0x180025b95  mov     edi, eax
0x180025b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b9e  cmp     rcx, rsi
0x180025ba1  jz      short loc_180025BC6
  ... truncated ...
```
