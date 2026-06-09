# InitializeTrigCOMSecurity(void)

- ea: `0x14000d9d0`
- end: `0x14000e0a8`
- name: `?InitializeTrigCOMSecurity@@YAXXZ`
- size: `1752`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000d75c`

## callees

- `0x140005e20`
- `0x14000752c`
- `0x140007554`
- `0x14000d9d0`
- `0x14000e370`
- `0x14000ed18`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14000dd4b`
- `ADVAPI32!GetLengthSid` at `0x14000dd61`
- `ADVAPI32!GetLengthSid` at `0x14000dd4b`
- `ADVAPI32!GetLengthSid` at `0x14000dd61`
- `ADVAPI32!OpenProcessToken` at `0x14000da01`
- `ADVAPI32!OpenProcessToken` at `0x14000da01`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000da5b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x14000da5b`
- `ADVAPI32!GetTokenInformation` at `0x14000dad1`
- `ADVAPI32!GetTokenInformation` at `0x14000db0c`
- `ADVAPI32!GetTokenInformation` at `0x14000dc26`
- `ADVAPI32!GetTokenInformation` at `0x14000dc60`
- `ADVAPI32!GetTokenInformation` at `0x14000dad1`
- `ADVAPI32!GetTokenInformation` at `0x14000db0c`
- `ADVAPI32!GetTokenInformation` at `0x14000dc26`
- `ADVAPI32!GetTokenInformation` at `0x14000dc60`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14000db79`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x14000db79`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x14000dcc5`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x14000dcc5`
- `ADVAPI32!InitializeAcl` at `0x14000dd88`
- `ADVAPI32!InitializeAcl` at `0x14000dd88`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000de00`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000de70`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000de00`
- `ADVAPI32!AddAccessAllowedAce` at `0x14000de70`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000dee1`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x14000dee1`
- `KERNEL32!GetCurrentProcess` at `0x14000d9f0`
- `KERNEL32!GetCurrentProcess` at `0x14000d9f0`
- `KERNEL32!GetLastError` at `0x14000da0b`
- `KERNEL32!GetLastError` at `0x14000da65`
- `KERNEL32!GetLastError` at `0x14000dad7`
- `KERNEL32!GetLastError` at `0x14000db16`
- `KERNEL32!GetLastError` at `0x14000db83`
- `KERNEL32!GetLastError` at `0x14000dc2c`
- `KERNEL32!GetLastError` at `0x14000dc6a`
- `KERNEL32!GetLastError` at `0x14000dccf`
- `KERNEL32!GetLastError` at `0x14000dd95`
- `KERNEL32!GetLastError` at `0x14000de0a`
- `KERNEL32!GetLastError` at `0x14000de7a`
- `KERNEL32!GetLastError` at `0x14000deeb`
- `KERNEL32!GetLastError` at `0x14000da0b`
- `KERNEL32!GetLastError` at `0x14000da65`
- `KERNEL32!GetLastError` at `0x14000dad7`
- `KERNEL32!GetLastError` at `0x14000db16`
- `KERNEL32!GetLastError` at `0x14000db83`
- `KERNEL32!GetLastError` at `0x14000dc2c`
- `KERNEL32!GetLastError` at `0x14000dc6a`
- `KERNEL32!GetLastError` at `0x14000dccf`
- `KERNEL32!GetLastError` at `0x14000dd95`
- `KERNEL32!GetLastError` at `0x14000de0a`
- `KERNEL32!GetLastError` at `0x14000de7a`
- `KERNEL32!GetLastError` at `0x14000deeb`
- `msvcrt!free` at `0x14000db56`
- `msvcrt!free` at `0x14000db60`
- `msvcrt!free` at `0x14000dbc3`
- `msvcrt!free` at `0x14000dbcd`
- `msvcrt!free` at `0x14000dca2`
- `msvcrt!free` at `0x14000dcac`
- `msvcrt!free` at `0x14000dd09`
- `msvcrt!free` at `0x14000dd13`
- `msvcrt!free` at `0x14000ddce`
- `msvcrt!free` at `0x14000ddd8`
- `msvcrt!free` at `0x14000dde2`
- `msvcrt!free` at `0x14000de43`
- `msvcrt!free` at `0x14000de4d`
- `msvcrt!free` at `0x14000de57`
- `msvcrt!free` at `0x14000deb4`
- `msvcrt!free` at `0x14000debe`
- `msvcrt!free` at `0x14000dec8`
- `msvcrt!free` at `0x14000df25`
- `msvcrt!free` at `0x14000df2f`
- `msvcrt!free` at `0x14000df39`
- `msvcrt!free` at `0x14000dfdb`
- `msvcrt!free` at `0x14000dfe5`
- `msvcrt!free` at `0x14000dfef`
- `msvcrt!free` at `0x14000e02e`
- `msvcrt!free` at `0x14000e038`
- `msvcrt!free` at `0x14000e07b`
- `msvcrt!free` at `0x14000e084`
- `msvcrt!free` at `0x14000db56`
- `msvcrt!free` at `0x14000db60`
- `msvcrt!free` at `0x14000dbc3`
- `msvcrt!free` at `0x14000dbcd`
- `msvcrt!free` at `0x14000dca2`
- `msvcrt!free` at `0x14000dcac`
- `msvcrt!free` at `0x14000dd09`
- `msvcrt!free` at `0x14000dd13`
- `msvcrt!free` at `0x14000ddce`
- `msvcrt!free` at `0x14000ddd8`
- `msvcrt!free` at `0x14000dde2`
- `msvcrt!free` at `0x14000de43`
- `msvcrt!free` at `0x14000de4d`
- `msvcrt!free` at `0x14000de57`
- `msvcrt!free` at `0x14000deb4`
- `msvcrt!free` at `0x14000debe`
- `msvcrt!free` at `0x14000dec8`
- `msvcrt!free` at `0x14000df25`
- `msvcrt!free` at `0x14000df2f`
- `msvcrt!free` at `0x14000df39`
- `msvcrt!free` at `0x14000dfdb`
- `msvcrt!free` at `0x14000dfe5`
- `msvcrt!free` at `0x14000dfef`
- `msvcrt!free` at `0x14000e02e`
- `msvcrt!free` at `0x14000e038`
- `msvcrt!free` at `0x14000e07b`
- `msvcrt!free` at `0x14000e084`
- `ole32!CoInitializeSecurity` at `0x14000df6e`
- `ole32!CoInitializeSecurity` at `0x14000df6e`
- `mqsec!MQSec_GetLocalSystemSid` at `0x14000dd54`
- `mqsec!MQSec_GetLocalSystemSid` at `0x14000dd54`

## pseudocode

```c
void InitializeTrigCOMSecurity(void)
{
  HANDLE CurrentProcess; // rax
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  PSID *v3; // rbx
  PSID v4; // r13
  PSID *v5; // rdi
  DWORD LengthSid; // r14d
  DWORD v7; // r14d
  struct _ACL *v8; // rsi
  PSID pSid; // [rsp+50h] [rbp-29h]
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v11; // [rsp+80h] [rbp+7h]
  DWORD TokenInformationLength; // [rsp+E0h] [rbp+67h] BYREF
  void *TokenHandle; // [rsp+E8h] [rbp+6Fh] BYREF
  PSID *v14; // [rsp+F0h] [rbp+77h]
  PSID *v15; // [rsp+F8h] [rbp+7Fh]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    v11 = 0;
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      TokenInformationLength = 0;
      v14 = 0;
      v15 = 0;
      GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
      if ( GetLastError() == 122 )
      {
        v3 = (PSID *)MmAllocate(TokenInformationLength);
        v14 = v3;
        if ( GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
        {
          v4 = *v3;
          if ( SetSecurityDescriptorOwner(pSecurityDescriptor, *v3, 1) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
              WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
            TokenInformationLength = 0;
            GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength);
            if ( GetLastError() == 122 )
            {
              v5 = (PSID *)MmAllocate(TokenInformationLength);
              v15 = v5;
              if ( GetTokenInformation(
                     TokenHandle,
                     TokenPrimaryGroup,
                     v5,
                     TokenInformationLength,
                     &TokenInformationLength) )
              {
                if ( SetSecurityDescriptorGroup(pSecurityDescriptor, *v5, 1) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
                    WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 32));
                  LengthSid = GetLengthSid(v4);
                  pSid = MQSec_GetLocalSystemSid();
                  v7 = GetLengthSid(pSid) + 24 + LengthSid;
                  v8 = (struct _ACL *)MmAllocate(v7);
                  if ( InitializeAcl(v8, v7, 2u) )
                  {
                    if ( AddAccessAllowedAce(v8, 2u, 1u, v4) )
                    {
                      if ( AddAccessAllowedAce(v8, 2u, 1u, pSid) )
                      {
                        if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v8, 0) )
                        {
                          if ( CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 2u, 3u, 0, 0, 0) >= 0 )
                          {
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
                            {
                              WPP_SF_(
                                *((_QWORD *)WPP_GLOBAL_Control + 32),
                                25,
                                &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
                            }
                          }
                          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                 && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 32),
                              24,
                              &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
                          }
                        }
                        else
                        {
                          GetLastError();
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 32),
                              23,
                              &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
                          }
                        }
                      }
                      else
                      {
                        GetLastError();
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 32),
                            22,
                            &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
                        }
                      }
                    }
                    else
                    {
                      GetLastError();
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 32),
                          21,
                          &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
                    }
                  }
                  else
                  {
                    GetLastError();
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 32),
                        20,
                        &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
                  }
                  free(v8);
                  free(v5);
                  free(v3);
                  goto LABEL_74;
                }
                GetLastError();
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 18, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
              }
              else
              {
                GetLastError();
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
              }
              free(v5);
              free(v3);
              goto LABEL_74;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
          }
          else
          {
            GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 14, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
          }
        }
        else
        {
          GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
        }
        free(0);
        free(v3);
        goto LABEL_74;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
      free(0);
      free(0);
    }
    else
    {
      GetLastError();
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v2 = 11;
        goto LABEL_9;
      }
    }
  }
  else
  {
    GetLastError();
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v2 = 10;
LABEL_9:
      WPP_SF_d(v1[32], v2, &WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids);
    }
  }
LABEL_74:
  CHandle::~CHandle(&TokenHandle);
}

```

## disassembly

```asm
0x14000d9d0  push    rbp
0x14000d9d2  push    rbx
0x14000d9d3  push    rsi
0x14000d9d4  push    rdi
0x14000d9d5  push    r12
0x14000d9d7  push    r13
0x14000d9d9  push    r14
0x14000d9db  push    r15
0x14000d9dd  lea     rbp, [rsp-1Fh]
0x14000d9e2  sub     rsp, 98h
0x14000d9e9  xor     r14d, r14d
0x14000d9ec  mov     [rbp+57h+TokenHandle], r14
0x14000d9f0  call    cs:__imp_GetCurrentProcess
0x14000d9f6  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14000d9fa  lea     edx, [r14+8]; DesiredAccess
0x14000d9fe  mov     rcx, rax; ProcessHandle
0x14000da01  call    cs:__imp_OpenProcessToken
0x14000da07  test    eax, eax
0x14000da09  jnz     short loc_14000DA3F
0x14000da0b  call    cs:__imp_GetLastError
0x14000da11  lea     r15, WPP_GLOBAL_Control
0x14000da18  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da1f  cmp     rcx, r15
0x14000da22  jz      loc_14000E08B
0x14000da28  lea     r12d, [r14+1]
0x14000da2c  test    [rcx+10Ch], r12b
0x14000da33  jz      loc_14000E08B
0x14000da39  lea     edx, [r14+0Ah]
0x14000da3d  jmp     short loc_14000DA94
0x14000da3f  xorps   xmm0, xmm0
0x14000da42  xor     eax, eax
0x14000da44  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x14000da48  movups  [rbp+57h+var_60], xmm0
0x14000da4c  mov     [rbp+57h+var_50], rax
0x14000da50  lea     r12d, [rax+1]
0x14000da54  mov     edx, r12d; dwRevision
0x14000da57  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14000da5b  call    cs:__imp_InitializeSecurityDescriptor
0x14000da61  test    eax, eax
0x14000da63  jnz     short loc_14000DAAF
0x14000da65  call    cs:__imp_GetLastError
0x14000da6b  lea     r15, WPP_GLOBAL_Control
0x14000da72  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da79  cmp     rcx, r15
0x14000da7c  jz      loc_14000E08B
0x14000da82  test    [rcx+10Ch], r12b
0x14000da89  jz      loc_14000E08B
0x14000da8f  lea     edx, [r12+0Ah]
0x14000da94  mov     r9d, eax
0x14000da97  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000da9e  mov     rcx, [rcx+100h]
0x14000daa5  call    WPP_SF_d
0x14000daaa  jmp     loc_14000E08B
0x14000daaf  mov     [rbp+57h+TokenInformationLength], r14d
0x14000dab3  mov     [rbp+57h+arg_10], r14
0x14000dab7  mov     [rbp+57h+arg_18], r14
0x14000dabb  lea     rax, [rbp+57h+TokenInformationLength]
0x14000dabf  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x14000dac4  xor     r9d, r9d; TokenInformationLength
0x14000dac7  xor     r8d, r8d; TokenInformation
0x14000daca  mov     edx, r12d; TokenInformationClass
0x14000dacd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14000dad1  call    cs:__imp_GetTokenInformation
0x14000dad7  call    cs:__imp_GetLastError
0x14000dadd  cmp     eax, 7Ah ; 'z'
0x14000dae0  jnz     loc_14000E041
0x14000dae6  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x14000dae9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000daee  mov     rbx, rax
0x14000daf1  mov     [rbp+57h+arg_10], rax
0x14000daf5  lea     rax, [rbp+57h+TokenInformationLength]
0x14000daf9  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x14000dafe  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x14000db02  mov     r8, rbx; TokenInformation
0x14000db05  mov     edx, r12d; TokenInformationClass
0x14000db08  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14000db0c  call    cs:__imp_GetTokenInformation
0x14000db12  test    eax, eax
0x14000db14  jnz     short loc_14000DB6C
0x14000db16  call    cs:__imp_GetLastError
0x14000db1c  lea     r15, WPP_GLOBAL_Control
0x14000db23  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db2a  cmp     rcx, r15
0x14000db2d  jz      short loc_14000DB54
0x14000db2f  test    [rcx+10Ch], r12b
0x14000db36  jz      short loc_14000DB54
0x14000db38  mov     edx, 0Ch
0x14000db3d  mov     r9d, eax
0x14000db40  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000db47  mov     rcx, [rcx+100h]
0x14000db4e  call    WPP_SF_d
0x14000db53  nop
0x14000db54  xor     ecx, ecx; Block
0x14000db56  call    cs:__imp_free
0x14000db5c  nop
0x14000db5d  mov     rcx, rbx; Block
0x14000db60  call    cs:__imp_free
0x14000db66  nop
0x14000db67  jmp     loc_14000E08B
0x14000db6c  mov     r13, [rbx]
0x14000db6f  mov     r8d, r12d; bOwnerDefaulted
0x14000db72  mov     rdx, r13; pOwner
0x14000db75  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14000db79  call    cs:__imp_SetSecurityDescriptorOwner
0x14000db7f  test    eax, eax
0x14000db81  jnz     short loc_14000DBD9
0x14000db83  call    cs:__imp_GetLastError
0x14000db89  lea     r15, WPP_GLOBAL_Control
0x14000db90  mov     rcx, cs:WPP_GLOBAL_Control
0x14000db97  cmp     rcx, r15
0x14000db9a  jz      short loc_14000DBC1
0x14000db9c  test    [rcx+10Ch], r12b
0x14000dba3  jz      short loc_14000DBC1
0x14000dba5  mov     edx, 0Eh
0x14000dbaa  mov     r9d, eax
0x14000dbad  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000dbb4  mov     rcx, [rcx+100h]
0x14000dbbb  call    WPP_SF_d
0x14000dbc0  nop
0x14000dbc1  xor     ecx, ecx; Block
0x14000dbc3  call    cs:__imp_free
0x14000dbc9  nop
0x14000dbca  mov     rcx, rbx; Block
0x14000dbcd  call    cs:__imp_free
0x14000dbd3  nop
0x14000dbd4  jmp     loc_14000E08B
0x14000dbd9  lea     r15, WPP_GLOBAL_Control
0x14000dbe0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dbe7  cmp     rcx, r15
0x14000dbea  jz      short loc_14000DC09
0x14000dbec  test    byte ptr [rcx+10Ch], 4
0x14000dbf3  jz      short loc_14000DC09
0x14000dbf5  mov     edx, 0Fh
0x14000dbfa  mov     r9, r13
0x14000dbfd  mov     rcx, [rcx+100h]; LoggerHandle
0x14000dc04  call    WPP_SF__sid_
0x14000dc09  mov     [rbp+57h+TokenInformationLength], r14d
0x14000dc0d  lea     rax, [rbp+57h+TokenInformationLength]
0x14000dc11  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x14000dc16  xor     r9d, r9d; TokenInformationLength
0x14000dc19  xor     r8d, r8d; TokenInformation
0x14000dc1c  lea     esi, [r9+5]
0x14000dc20  mov     edx, esi; TokenInformationClass
0x14000dc22  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14000dc26  call    cs:__imp_GetTokenInformation
0x14000dc2c  call    cs:__imp_GetLastError
0x14000dc32  cmp     eax, 7Ah ; 'z'
0x14000dc35  jnz     loc_14000DFFB
0x14000dc3b  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x14000dc3e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000dc43  mov     rdi, rax
0x14000dc46  mov     [rbp+57h+arg_18], rax
0x14000dc4a  lea     rax, [rbp+57h+TokenInformationLength]
0x14000dc4e  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x14000dc53  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x14000dc57  mov     r8, rdi; TokenInformation
0x14000dc5a  mov     edx, esi; TokenInformationClass
0x14000dc5c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14000dc60  call    cs:__imp_GetTokenInformation
0x14000dc66  test    eax, eax
0x14000dc68  jnz     short loc_14000DCB8
0x14000dc6a  call    cs:__imp_GetLastError
0x14000dc70  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc77  cmp     rcx, r15
0x14000dc7a  jz      short loc_14000DC9F
0x14000dc7c  test    [rcx+10Ch], r12b
0x14000dc83  jz      short loc_14000DC9F
0x14000dc85  lea     edx, [rsi+0Bh]
0x14000dc88  mov     r9d, eax
0x14000dc8b  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000dc92  mov     rcx, [rcx+100h]
0x14000dc99  call    WPP_SF_d
0x14000dc9e  nop
0x14000dc9f  mov     rcx, rdi; Block
0x14000dca2  call    cs:__imp_free
0x14000dca8  nop
0x14000dca9  mov     rcx, rbx; Block
0x14000dcac  call    cs:__imp_free
0x14000dcb2  nop
0x14000dcb3  jmp     loc_14000E08B
0x14000dcb8  mov     rsi, [rdi]
0x14000dcbb  mov     r8d, r12d; bGroupDefaulted
0x14000dcbe  mov     rdx, rsi; pGroup
0x14000dcc1  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14000dcc5  call    cs:__imp_SetSecurityDescriptorGroup
0x14000dccb  test    eax, eax
0x14000dccd  jnz     short loc_14000DD1F
0x14000dccf  call    cs:__imp_GetLastError
0x14000dcd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dcdc  cmp     rcx, r15
0x14000dcdf  jz      short loc_14000DD06
0x14000dce1  test    [rcx+10Ch], r12b
0x14000dce8  jz      short loc_14000DD06
0x14000dcea  mov     edx, 12h
0x14000dcef  mov     r9d, eax
0x14000dcf2  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000dcf9  mov     rcx, [rcx+100h]
0x14000dd00  call    WPP_SF_d
0x14000dd05  nop
0x14000dd06  mov     rcx, rdi; Block
0x14000dd09  call    cs:__imp_free
0x14000dd0f  nop
0x14000dd10  mov     rcx, rbx; Block
0x14000dd13  call    cs:__imp_free
0x14000dd19  nop
0x14000dd1a  jmp     loc_14000E08B
0x14000dd1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd26  cmp     rcx, r15
0x14000dd29  jz      short loc_14000DD48
0x14000dd2b  test    byte ptr [rcx+10Ch], 4
0x14000dd32  jz      short loc_14000DD48
0x14000dd34  mov     edx, 13h
0x14000dd39  mov     r9, rsi
0x14000dd3c  mov     rcx, [rcx+100h]; LoggerHandle
0x14000dd43  call    WPP_SF__sid_
0x14000dd48  mov     rcx, r13; pSid
0x14000dd4b  call    cs:__imp_GetLengthSid
0x14000dd51  mov     r14d, eax
0x14000dd54  call    cs:__imp_?MQSec_GetLocalSystemSid@@YAPEAXXZ; MQSec_GetLocalSystemSid(void)
0x14000dd5a  mov     [rbp+57h+pSid], rax
0x14000dd5e  mov     rcx, rax; pSid
0x14000dd61  call    cs:__imp_GetLengthSid
0x14000dd67  add     eax, 18h
0x14000dd6a  add     r14d, eax
0x14000dd6d  mov     ecx, r14d; unsigned __int64
0x14000dd70  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000dd75  mov     rsi, rax
0x14000dd78  mov     [rbp+57h+var_78], rax
0x14000dd7c  mov     r8d, 2; dwAclRevision
0x14000dd82  mov     edx, r14d; nAclLength
0x14000dd85  mov     rcx, rax; pAcl
0x14000dd88  call    cs:__imp_InitializeAcl
0x14000dd8e  xor     r14d, r14d
0x14000dd91  test    eax, eax
0x14000dd93  jnz     short loc_14000DDEE
0x14000dd95  call    cs:__imp_GetLastError
0x14000dd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dda2  cmp     rcx, r15
0x14000dda5  jz      short loc_14000DDCB
0x14000dda7  test    [rcx+10Ch], r12b
0x14000ddae  jz      short loc_14000DDCB
0x14000ddb0  lea     edx, [r14+14h]
0x14000ddb4  mov     r9d, eax
0x14000ddb7  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000ddbe  mov     rcx, [rcx+100h]
0x14000ddc5  call    WPP_SF_d
0x14000ddca  nop
0x14000ddcb  mov     rcx, rsi; Block
0x14000ddce  call    cs:__imp_free
0x14000ddd4  nop
0x14000ddd5  mov     rcx, rdi; Block
0x14000ddd8  call    cs:__imp_free
0x14000ddde  nop
0x14000dddf  mov     rcx, rbx; Block
0x14000dde2  call    cs:__imp_free
0x14000dde8  nop
0x14000dde9  jmp     loc_14000E08B
0x14000ddee  mov     r9, r13; pSid
0x14000ddf1  mov     r8d, r12d; AccessMask
0x14000ddf4  mov     r13d, 2
0x14000ddfa  mov     edx, r13d; dwAceRevision
0x14000ddfd  mov     rcx, rsi; pAcl
0x14000de00  call    cs:__imp_AddAccessAllowedAce
0x14000de06  test    eax, eax
0x14000de08  jnz     short loc_14000DE63
0x14000de0a  call    cs:__imp_GetLastError
0x14000de10  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de17  cmp     rcx, r15
0x14000de1a  jz      short loc_14000DE40
0x14000de1c  test    [rcx+10Ch], r12b
0x14000de23  jz      short loc_14000DE40
0x14000de25  lea     edx, [r13+13h]
0x14000de29  mov     r9d, eax
0x14000de2c  lea     r8, WPP_1bd4877bb0de30ad778717a3a22d258c_Traceguids
0x14000de33  mov     rcx, [rcx+100h]
0x14000de3a  call    WPP_SF_d
0x14000de3f  nop
0x14000de40  mov     rcx, rsi; Block
0x14000de43  call    cs:__imp_free
0x14000de49  nop
0x14000de4a  mov     rcx, rdi; Block
0x14000de4d  call    cs:__imp_free
0x14000de53  nop
0x14000de54  mov     rcx, rbx; Block
0x14000de57  call    cs:__imp_free
0x14000de5d  nop
0x14000de5e  jmp     loc_14000E08B
0x14000de63  mov     r9, [rbp+57h+pSid]; pSid
0x14000de67  mov     r8d, r12d; AccessMask
0x14000de6a  mov     edx, r13d; dwAceRevision
0x14000de6d  mov     rcx, rsi; pAcl
0x14000de70  call    cs:__imp_AddAccessAllowedAce
0x14000de76  test    eax, eax
0x14000de78  jnz     short loc_14000DED4
0x14000de7a  call    cs:__imp_GetLastError
0x14000de80  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de87  cmp     rcx, r15
0x14000de8a  jz      short loc_14000DEB1
0x14000de8c  test    [rcx+10Ch], r12b
0x14000de93  jz      short loc_14000DEB1
  ... truncated ...
```
