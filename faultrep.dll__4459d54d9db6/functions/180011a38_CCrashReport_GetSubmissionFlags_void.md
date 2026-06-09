# CCrashReport::GetSubmissionFlags(void)

- ea: `0x180011a38`
- end: `0x180011d8e`
- name: `?GetSubmissionFlags@CCrashReport@@AEAAKXZ`
- size: `854`
- prototype: `__int64 __fastcall(CCrashReport *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ff8c`

## callees

- `0x180003a58`
- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x180011a38`
- `0x180016c20`
- `0x18001ca08`
- `0x180026ed4`
- `0x1800270c4`
- `0x1800273d8`
- `0x180038c0c`
- `0x18003bdf0`
- `0x18003e4e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180011b7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180011b7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac4`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x180011b10`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRecoveryCallback` at `0x180011b10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011bc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011bc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011ba5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011ba5`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180011a92`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180011a92`

## string_xrefs

- `0x180011ad3`: `Faultrep.dll`

## pseudocode

```c
__int64 __fastcall CCrashReport::GetSubmissionFlags(CCrashReport *this)
{
  int v2; // esi
  DWORD LastError; // eax
  int RestartCommandLine; // eax
  void **v5; // rax
  void *v6; // rcx
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  APPLICATION_RECOVERY_CALLBACK pRecoveryCallback; // [rsp+38h] [rbp-10h] BYREF
  int TokenInformation; // [rsp+90h] [rbp+48h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp+50h] BYREF
  int v14; // [rsp+A0h] [rbp+58h] BYREF
  DWORD ReturnLength; // [rsp+A8h] [rbp+60h] BYREF

  v14 = 0;
  v2 = 134283264;
  pRecoveryCallback = 0;
  LODWORD(TokenHandle) = 0;
  ReturnLength = 0;
  TokenInformation = 0;
  v10 = 0;
  if ( (unsigned __int8)IsGetProcessUIContextInformationPresent() )
  {
    if ( (unsigned int)GetProcessUIContextInformation(*((_QWORD *)this + 6), &v10) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
          (unsigned int)v10);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 1471 )
      {
        MicrosoftTelemetryAssertTriggeredArgs("Faultrep.dll", LastError);
        v2 = -2013200384;
      }
    }
  }
  if ( *((_DWORD *)this + 206) != -1073740791
    && (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0
    && !GetApplicationRecoveryCallback(*((HANDLE *)this + 6), &pRecoveryCallback, 0, 0, 0)
    && pRecoveryCallback )
  {
    v2 |= 1u;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 4) == 0 && (v10 & 0xFFFFFFFD) == 0 )
  {
    RestartCommandLine = WerpGetRestartCommandLine(*((void **)this + 6), 0, &v14, &TokenHandle);
    if ( (!RestartCommandLine || RestartCommandLine == -2147024774) && ((unsigned __int8)TokenHandle & 1) == 0 )
    {
      TokenHandle = 0;
      v5 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
      if ( OpenProcessToken(*((HANDLE *)this + 6), 8u, v5) )
      {
        TokenInformation = 0;
        if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
        {
          if ( !TokenInformation )
            v2 |= 2u;
        }
      }
      if ( (unsigned __int64)TokenHandle + 1 > 1 )
        CloseHandle(TokenHandle);
    }
  }
  if ( (*((_BYTE *)this + 4280) & 1) != 0
    && *((_WORD *)this + 2142)
    && (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 6) == 0 )
  {
    v2 |= 8u;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 1) != 0
    || (*((_BYTE *)this + 28) & 0xA) != 0
    || *((_DWORD *)this + 206) == -1073741502 && (UtilReadErrorModeForProcess(*((void **)this + 6)) & 1) != 0
    || (unsigned int)IsCrashVerticalReportingOnSelf(*((HANDLE *)this + 6)) )
  {
    v2 |= 4u;
  }
  v6 = (void *)*((_QWORD *)this + 6);
  LODWORD(TokenHandle) = 0;
  UtilGetProtectedProcessInfo(v6, (enum _PS_PROTECTED_TYPE *)&TokenHandle, 0);
  if ( (int)TokenHandle > 0 )
    v2 |= 0x200004u;
  v7 = v2 | 0x40;
  if ( !(unsigned int)IsCrashVerticalReportingOnSelf(*((HANDLE *)this + 6)) )
    v7 = v2;
  if ( *((_DWORD *)this + 3) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v7 |= 4u;
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 1) )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
    {
      WPP_SF_(v8[2], 87, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v7 |= 4u;
  }
  if ( *((_DWORD *)this + 2) )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
      WPP_SF_(v8[2], 88, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
    v7 |= 4u;
  }
  if ( (unsigned int)UtilIsSystemShuttingDown() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
    v7 |= 4u;
  }
  if ( (*(_BYTE *)(*((_QWORD *)this + 5) + 236LL) & 9) != 0 )
  {
LABEL_65:
    v7 |= 0x80000000;
    goto LABEL_66;
  }
  if ( (*((_BYTE *)this + 28) & 0x10) == 0 )
  {
    if ( (*((_BYTE *)this + 28) & 0x20) == 0
      && (unsigned int)UtilIsCurrentProcessInteractive()
      && (unsigned int)UtilIsInteractiveDesktop() )
    {
      goto LABEL_66;
    }
    goto LABEL_65;
  }
  v7 |= 0x1000000u;
LABEL_66:
  switch ( (_DWORD)v10 )
  {
    case 1:
      goto LABEL_69;
    case 2:
      v7 |= *((_DWORD *)this + 2) != 0 ? 0x80000 : 0x80000000;
      return v7;
    case 3:
LABEL_69:
      v7 |= 0x100000u;
      break;
  }
  return v7;
}

```

## disassembly

```asm
0x180011a38  push    rbp
0x180011a3a  push    rbx
0x180011a3b  push    rsi
0x180011a3c  push    rdi
0x180011a3d  push    r12
0x180011a3f  push    r13
0x180011a41  push    r14
0x180011a43  push    r15
0x180011a45  mov     rbp, rsp
0x180011a48  sub     rsp, 48h
0x180011a4c  xor     r14d, r14d
0x180011a4f  mov     rdi, rcx
0x180011a52  mov     [rbp+arg_10], r14d
0x180011a56  mov     esi, 8010000h
0x180011a5b  mov     [rbp+pRecoveryCallback], r14
0x180011a5f  mov     dword ptr [rbp+TokenHandle], r14d
0x180011a63  mov     [rbp+ReturnLength], r14d
0x180011a67  mov     [rbp+TokenInformation], r14d
0x180011a6b  mov     [rbp+var_18], r14
0x180011a6f  call    IsGetProcessUIContextInformationPresent
0x180011a74  lea     r12, WPP_GLOBAL_Control
0x180011a7b  lea     r15d, [r14+4]
0x180011a7f  lea     r13, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180011a86  test    al, al
0x180011a88  jz      short loc_180011AE4
0x180011a8a  mov     rcx, [rdi+30h]
0x180011a8e  lea     rdx, [rbp+var_18]
0x180011a92  call    cs:__imp_GetProcessUIContextInformation
0x180011a98  test    eax, eax
0x180011a9a  jz      short loc_180011AC4
0x180011a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011aa3  cmp     rcx, r12
0x180011aa6  jz      short loc_180011AE4
0x180011aa8  test    [rcx+1Ch], r15b
0x180011aac  jz      short loc_180011AE4
0x180011aae  mov     r9d, dword ptr [rbp+var_18]
0x180011ab2  lea     edx, [r14+55h]
0x180011ab6  mov     rcx, [rcx+10h]
0x180011aba  mov     r8, r13
0x180011abd  call    WPP_SF_d
0x180011ac2  jmp     short loc_180011AE4
0x180011ac4  call    cs:__imp_GetLastError
0x180011aca  cmp     eax, 5BFh
0x180011acf  jz      short loc_180011AE4
0x180011ad1  mov     edx, eax
0x180011ad3  lea     rcx, aFaultrepDll_0; "Faultrep.dll"
0x180011ada  call    MicrosoftTelemetryAssertTriggeredArgs
0x180011adf  mov     esi, 88010000h
0x180011ae4  cmp     dword ptr [rdi+338h], 0C0000409h
0x180011aee  jz      short loc_180011B23
0x180011af0  mov     rax, [rdi+28h]
0x180011af4  test    [rax+0ECh], r15b
0x180011afb  jnz     short loc_180011B23
0x180011afd  mov     rcx, [rdi+30h]; hProcess
0x180011b01  lea     rdx, [rbp+pRecoveryCallback]; pRecoveryCallback
0x180011b05  xor     r9d, r9d; pdwPingInterval
0x180011b08  mov     [rsp+48h+pdwFlags], r14; pdwFlags
0x180011b0d  xor     r8d, r8d; ppvParameter
0x180011b10  call    cs:__imp_GetApplicationRecoveryCallback
0x180011b16  test    eax, eax
0x180011b18  jnz     short loc_180011B23
0x180011b1a  cmp     [rbp+pRecoveryCallback], r14
0x180011b1e  jz      short loc_180011B23
0x180011b20  or      esi, 1
0x180011b23  mov     rax, [rdi+28h]
0x180011b27  test    [rax+0ECh], r15b
0x180011b2e  jnz     loc_180011BCC
0x180011b34  test    dword ptr [rbp+var_18], 0FFFFFFFDh
0x180011b3b  jnz     loc_180011BCC
0x180011b41  mov     rcx, [rdi+30h]
0x180011b45  lea     r9, [rbp+TokenHandle]
0x180011b49  lea     r8, [rbp+arg_10]
0x180011b4d  xor     edx, edx
0x180011b4f  call    WerpGetRestartCommandLine
0x180011b54  test    eax, eax
0x180011b56  jz      short loc_180011B5F
0x180011b58  cmp     eax, 8007007Ah
0x180011b5d  jnz     short loc_180011BCC
0x180011b5f  test    byte ptr [rbp+TokenHandle], 1
0x180011b63  jnz     short loc_180011BCC
0x180011b65  lea     rcx, [rbp+TokenHandle]
0x180011b69  mov     [rbp+TokenHandle], r14
0x180011b6d  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180011b72  mov     rcx, [rdi+30h]; ProcessHandle
0x180011b76  mov     r8, rax; TokenHandle
0x180011b79  mov     edx, 8; DesiredAccess
0x180011b7e  call    cs:__imp_OpenProcessToken
0x180011b84  test    eax, eax
0x180011b86  jz      short loc_180011BB8
0x180011b88  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180011b8c  lea     rax, [rbp+ReturnLength]
0x180011b90  mov     r9d, r15d; TokenInformationLength
0x180011b93  mov     [rsp+48h+pdwFlags], rax; ReturnLength
0x180011b98  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180011b9c  mov     [rbp+TokenInformation], r14d
0x180011ba0  mov     edx, 1Dh; TokenInformationClass
0x180011ba5  call    cs:__imp_GetTokenInformation
0x180011bab  test    eax, eax
0x180011bad  jz      short loc_180011BB8
0x180011baf  cmp     [rbp+TokenInformation], r14d
0x180011bb3  jnz     short loc_180011BB8
0x180011bb5  or      esi, 2
0x180011bb8  mov     rcx, [rbp+TokenHandle]; hObject
0x180011bbc  lea     rax, [rcx+1]
0x180011bc0  cmp     rax, 1
0x180011bc4  jbe     short loc_180011BCC
0x180011bc6  call    cs:__imp_CloseHandle
0x180011bcc  test    byte ptr [rdi+10B8h], 1
0x180011bd3  jz      short loc_180011BEF
0x180011bd5  cmp     [rdi+10BCh], r14w
0x180011bdd  jz      short loc_180011BEF
0x180011bdf  mov     rax, [rdi+28h]
0x180011be3  test    byte ptr [rax+0ECh], 6
0x180011bea  jnz     short loc_180011BEF
0x180011bec  or      esi, 8
0x180011bef  mov     rax, [rdi+28h]
0x180011bf3  test    byte ptr [rax+0ECh], 1
0x180011bfa  jnz     short loc_180011C28
0x180011bfc  test    byte ptr [rdi+1Ch], 0Ah
0x180011c00  jnz     short loc_180011C28
0x180011c02  cmp     dword ptr [rdi+338h], 0C0000142h
0x180011c0c  jnz     short loc_180011C1B
0x180011c0e  mov     rcx, [rdi+30h]; void *
0x180011c12  call    ?UtilReadErrorModeForProcess@@YAKPEAX@Z; UtilReadErrorModeForProcess(void *)
0x180011c17  test    al, 1
0x180011c19  jnz     short loc_180011C28
0x180011c1b  mov     rcx, [rdi+30h]; hProcess
0x180011c1f  call    ?IsCrashVerticalReportingOnSelf@@YAHPEAX@Z; IsCrashVerticalReportingOnSelf(void *)
0x180011c24  test    eax, eax
0x180011c26  jz      short loc_180011C2B
0x180011c28  or      esi, r15d
0x180011c2b  mov     rcx, [rdi+30h]; void *
0x180011c2f  lea     rdx, [rbp+TokenHandle]; enum _PS_PROTECTED_TYPE *
0x180011c33  xor     r8d, r8d; enum _PS_PROTECTED_SIGNER *
0x180011c36  mov     dword ptr [rbp+TokenHandle], r14d
0x180011c3a  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x180011c3f  cmp     dword ptr [rbp+TokenHandle], r14d
0x180011c43  jle     short loc_180011C4B
0x180011c45  or      esi, 200004h
0x180011c4b  mov     rcx, [rdi+30h]; hProcess
0x180011c4f  call    ?IsCrashVerticalReportingOnSelf@@YAHPEAX@Z; IsCrashVerticalReportingOnSelf(void *)
0x180011c54  mov     ebx, esi
0x180011c56  or      ebx, 40h
0x180011c59  test    eax, eax
0x180011c5b  cmovz   ebx, esi
0x180011c5e  cmp     [rdi+0Ch], r14d
0x180011c62  jz      short loc_180011C93
0x180011c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c6b  cmp     rcx, r12
0x180011c6e  jz      short loc_180011C8E
0x180011c70  test    [rcx+1Ch], r15b
0x180011c74  jz      short loc_180011C8E
0x180011c76  mov     rcx, [rcx+10h]
0x180011c7a  mov     edx, 56h ; 'V'
0x180011c7f  mov     r8, r13
0x180011c82  call    WPP_SF_
0x180011c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c8e  or      ebx, r15d
0x180011c91  jmp     short loc_180011C9A
0x180011c93  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c9a  cmp     [rdi+4], r14d
0x180011c9e  jz      short loc_180011CC6
0x180011ca0  cmp     rcx, r12
0x180011ca3  jz      short loc_180011CC3
0x180011ca5  test    [rcx+1Ch], r15b
0x180011ca9  jz      short loc_180011CC3
0x180011cab  mov     rcx, [rcx+10h]
0x180011caf  mov     edx, 57h ; 'W'
0x180011cb4  mov     r8, r13
0x180011cb7  call    WPP_SF_
0x180011cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cc3  or      ebx, r15d
0x180011cc6  cmp     [rdi+8], r14d
0x180011cca  jz      short loc_180011CEB
0x180011ccc  cmp     rcx, r12
0x180011ccf  jz      short loc_180011CE8
0x180011cd1  test    [rcx+1Ch], r15b
0x180011cd5  jz      short loc_180011CE8
0x180011cd7  mov     rcx, [rcx+10h]
0x180011cdb  mov     edx, 58h ; 'X'
0x180011ce0  mov     r8, r13
0x180011ce3  call    WPP_SF_
0x180011ce8  or      ebx, r15d
0x180011ceb  call    ?UtilIsSystemShuttingDown@@YAHXZ; UtilIsSystemShuttingDown(void)
0x180011cf0  test    eax, eax
0x180011cf2  jz      short loc_180011D1A
0x180011cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cfb  cmp     rcx, r12
0x180011cfe  jz      short loc_180011D17
0x180011d00  test    [rcx+1Ch], r15b
0x180011d04  jz      short loc_180011D17
0x180011d06  mov     rcx, [rcx+10h]
0x180011d0a  mov     edx, 59h ; 'Y'
0x180011d0f  mov     r8, r13
0x180011d12  call    WPP_SF_
0x180011d17  or      ebx, r15d
0x180011d1a  mov     rax, [rdi+28h]
0x180011d1e  mov     esi, 80000000h
0x180011d23  test    byte ptr [rax+0ECh], 9
0x180011d2a  jnz     short loc_180011D50
0x180011d2c  test    byte ptr [rdi+1Ch], 10h
0x180011d30  jz      short loc_180011D38
0x180011d32  bts     ebx, 18h
0x180011d36  jmp     short loc_180011D52
0x180011d38  test    byte ptr [rdi+1Ch], 20h
0x180011d3c  jnz     short loc_180011D50
0x180011d3e  call    ?UtilIsCurrentProcessInteractive@@YAHXZ; UtilIsCurrentProcessInteractive(void)
0x180011d43  test    eax, eax
0x180011d45  jz      short loc_180011D50
0x180011d47  call    ?UtilIsInteractiveDesktop@@YAHXZ; UtilIsInteractiveDesktop(void)
0x180011d4c  test    eax, eax
0x180011d4e  jnz     short loc_180011D52
0x180011d50  or      ebx, esi
0x180011d52  mov     ecx, dword ptr [rbp+var_18]
0x180011d55  sub     ecx, 1
0x180011d58  jz      short loc_180011D64
0x180011d5a  sub     ecx, 1
0x180011d5d  jz      short loc_180011D7B
0x180011d5f  cmp     ecx, 1
0x180011d62  jnz     short loc_180011D68
0x180011d64  bts     ebx, 14h
0x180011d68  mov     eax, ebx
0x180011d6a  add     rsp, 48h
0x180011d6e  pop     r15
0x180011d70  pop     r14
0x180011d72  pop     r13
0x180011d74  pop     r12
0x180011d76  pop     rdi
0x180011d77  pop     rsi
0x180011d78  pop     rbx
0x180011d79  pop     rbp
0x180011d7a  retn
0x180011d7b  mov     eax, [rdi+8]
0x180011d7e  neg     eax
0x180011d80  sbb     ecx, ecx
0x180011d82  and     ecx, 80080000h
0x180011d88  add     ecx, esi
0x180011d8a  or      ebx, ecx
0x180011d8c  jmp     short loc_180011D68
```
