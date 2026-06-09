# InitSPDGlobals

- ea: `0x18000a60c`
- end: `0x18000aaac`
- name: `InitSPDGlobals`
- size: `1184`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180001e20`

## callees

- `0x180006a10`
- `0x18000a60c`
- `0x18000aab4`
- `0x18000e510`
- `0x18000f1a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a9c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa94`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a6a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a6ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a6a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a6ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a764`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a7b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a80e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a865`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a8ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a913`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a764`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a7b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a80e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a865`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a8ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a913`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a968`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a9bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a968`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000a9bb`

## pseudocode

```c
__int64 InitSPDGlobals()
{
  unsigned int LastError; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rcx
  int v7; // eax
  struct _SECURITY_ATTRIBUTES v9; // [rsp+20h] [rbp-30h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+68h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  memset(&v9, 0, sizeof(v9));
  hMem = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  LastError = InitializeSPDSecurity();
  if ( LastError )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v2 = 12;
LABEL_5:
      WPP_SF_d(v1[2], v2, WPP_1fd9306cf60736517710f840e8d73d3c_Traceguids, LastError);
    }
  }
  else if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x00100000;;;NS)", 1u, &SecurityDescriptor, 0)
         || (LastError = GetLastError()) == 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x00100000;;;NS)(A;;0x0002;;;SY)", 1u, &hMem, 0)
      || (LastError = GetLastError()) == 0 )
    {
      v9.lpSecurityDescriptor = SecurityDescriptor;
      EventAttributes.lpSecurityDescriptor = hMem;
      v9.nLength = 24;
      v9.bInheritHandle = 1;
      EventAttributes.nLength = 24;
      EventAttributes.bInheritHandle = 1;
      ghNewDSPolicyEvent = CreateEventW(&EventAttributes, 1, 0, L"IPSEC_POLICY_CHANGE_EVENT");
      if ( ghNewDSPolicyEvent || (LastError = GetLastError()) == 0 )
      {
        ghNewLocalPolicyEvent = CreateEventW(&v9, 1, 0, 0);
        if ( ghNewLocalPolicyEvent || (LastError = GetLastError()) == 0 )
        {
          ghForcedPolicyReloadEvent = CreateEventW(&v9, 1, 0, 0);
          if ( ghForcedPolicyReloadEvent || (LastError = GetLastError()) == 0 )
          {
            ghPolicyChangeNotifyEvent = CreateEventW(0, 1, 0, L"IPSEC_POLICY_CHANGE_NOTIFY");
            if ( ghPolicyChangeNotifyEvent || (LastError = GetLastError()) == 0 )
            {
              ghServiceStopEvent = CreateEventW(&v9, 1, 0, 0);
              if ( ghServiceStopEvent || (LastError = GetLastError()) == 0 )
              {
                ghGpupdateRefreshEvent = CreateEventW(&v9, 1, 0, L"IPSEC_GP_REFRESH_EVENT");
                if ( ghGpupdateRefreshEvent || (LastError = GetLastError()) == 0 )
                {
                  if ( InitializeCriticalSectionAndSpinCount(&gcServerListenSection, 0x80000FA0)
                    || (LastError = GetLastError()) == 0 )
                  {
                    gbServerListenSection = 1;
                    if ( InitializeCriticalSectionAndSpinCount(&gcSPDSection, 0x80000FA0)
                      || (LastError = GetLastError()) == 0 )
                    {
                      gbSPDSection = 1;
                      LastError = InitializeInterfaceChangeEvent();
                      if ( LastError )
                      {
                        v1 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                        {
                          v2 = 23;
                          goto LABEL_5;
                        }
                      }
                      else
                      {
                        LastError = ResetInterfaceChangeEvent(v4, v3, v5);
                        if ( LastError )
                        {
                          v1 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                          {
                            v2 = 24;
                            goto LABEL_5;
                          }
                        }
                        else
                        {
                          v6 = gpIpsecPolicyState;
                          v7 = gDefaultPollingInterval;
                          *(_OWORD *)gpIpsecPolicyState = 0;
                          *(_OWORD *)(v6 + 16) = 0;
                          *(_OWORD *)(v6 + 32) = 0;
                          *(_DWORD *)(v6 + 20) = v7;
                        }
                      }
                    }
                    else
                    {
                      v1 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        v2 = 22;
                        goto LABEL_5;
                      }
                    }
                  }
                  else
                  {
                    v1 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v2 = 21;
                      goto LABEL_5;
                    }
                  }
                }
                else
                {
                  v1 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v2 = 20;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                v1 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v2 = 19;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v1 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v2 = 18;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v1 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v2 = 17;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v1 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v2 = 16;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v2 = 15;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v2 = 14;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v2 = 13;
      goto LABEL_5;
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  return LastError;
}

```

## disassembly

```asm
0x18000a60c  mov     [rsp-8+arg_10], rbx
0x18000a611  mov     [rsp-8+arg_18], rdi
0x18000a616  push    rbp
0x18000a617  mov     rbp, rsp
0x18000a61a  sub     rsp, 50h
0x18000a61e  xor     eax, eax
0x18000a620  mov     [rbp+SecurityDescriptor], 0
0x18000a628  xorps   xmm0, xmm0
0x18000a62b  mov     qword ptr [rbp+var_30.bInheritHandle], rax
0x18000a62f  xorps   xmm1, xmm1
0x18000a632  mov     qword ptr [rbp+EventAttributes.bInheritHandle], rax
0x18000a636  movups  xmmword ptr [rbp+var_30.nLength], xmm0
0x18000a63a  mov     [rbp+hMem], 0
0x18000a642  movups  xmmword ptr [rbp+EventAttributes.nLength], xmm1
0x18000a646  call    InitializeSPDSecurity
0x18000a64b  mov     ebx, eax
0x18000a64d  test    eax, eax
0x18000a64f  jz      short loc_18000A68F
0x18000a651  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a658  lea     rax, WPP_GLOBAL_Control
0x18000a65f  cmp     rcx, rax
0x18000a662  jz      loc_18000AA7C
0x18000a668  test    byte ptr [rcx+1Ch], 10h
0x18000a66c  jz      loc_18000AA7C
0x18000a672  mov     edx, 0Ch
0x18000a677  mov     rcx, [rcx+10h]
0x18000a67b  lea     r8, WPP_1fd9306cf60736517710f840e8d73d3c_Traceguids
0x18000a682  mov     r9d, ebx
0x18000a685  call    WPP_SF_d
0x18000a68a  jmp     loc_18000AA7C
0x18000a68f  xor     r9d, r9d; SecurityDescriptorSize
0x18000a692  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18000a696  lea     rcx, StringSecurityDescriptor; "D:(A;;0x00100000;;;NS)"
0x18000a69d  lea     edi, [r9+1]
0x18000a6a1  mov     edx, edi; StringSDRevision
0x18000a6a3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000a6a9  test    eax, eax
0x18000a6ab  jnz     short loc_18000A6DF
0x18000a6ad  call    cs:__imp_GetLastError
0x18000a6b3  mov     ebx, eax
0x18000a6b5  test    eax, eax
0x18000a6b7  jz      short loc_18000A6DF
0x18000a6b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6c0  lea     rax, WPP_GLOBAL_Control
0x18000a6c7  cmp     rcx, rax
0x18000a6ca  jz      loc_18000AA7C
0x18000a6d0  test    byte ptr [rcx+1Ch], 10h
0x18000a6d4  jz      loc_18000AA7C
0x18000a6da  lea     edx, [rdi+0Ch]
0x18000a6dd  jmp     short loc_18000A677
0x18000a6df  xor     r9d, r9d; SecurityDescriptorSize
0x18000a6e2  lea     r8, [rbp+hMem]; SecurityDescriptor
0x18000a6e6  mov     edx, edi; StringSDRevision
0x18000a6e8  lea     rcx, aDA0x00100000Ns_0; "D:(A;;0x00100000;;;NS)(A;;0x0002;;;SY)"
0x18000a6ef  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000a6f5  test    eax, eax
0x18000a6f7  jnz     short loc_18000A730
0x18000a6f9  call    cs:__imp_GetLastError
0x18000a6ff  mov     ebx, eax
0x18000a701  test    eax, eax
0x18000a703  jz      short loc_18000A730
0x18000a705  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a70c  lea     rax, WPP_GLOBAL_Control
0x18000a713  cmp     rcx, rax
0x18000a716  jz      loc_18000AA7C
0x18000a71c  test    byte ptr [rcx+1Ch], 10h
0x18000a720  jz      loc_18000AA7C
0x18000a726  mov     edx, 0Eh
0x18000a72b  jmp     loc_18000A677
0x18000a730  mov     rax, [rbp+SecurityDescriptor]
0x18000a734  lea     r9, Name; "IPSEC_POLICY_CHANGE_EVENT"
0x18000a73b  mov     [rbp+var_30.lpSecurityDescriptor], rax
0x18000a73f  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18000a743  mov     rax, [rbp+hMem]
0x18000a747  xor     r8d, r8d; bInitialState
0x18000a74a  mov     edx, edi; bManualReset
0x18000a74c  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x18000a750  mov     [rbp+var_30.nLength], 18h
0x18000a757  mov     [rbp+var_30.bInheritHandle], edi
0x18000a75a  mov     [rbp+EventAttributes.nLength], 18h
0x18000a761  mov     [rbp+EventAttributes.bInheritHandle], edi
0x18000a764  call    cs:__imp_CreateEventW
0x18000a76a  mov     cs:ghNewDSPolicyEvent, rax
0x18000a771  test    rax, rax
0x18000a774  jnz     short loc_18000A7AD
0x18000a776  call    cs:__imp_GetLastError
0x18000a77c  mov     ebx, eax
0x18000a77e  test    eax, eax
0x18000a780  jz      short loc_18000A7AD
0x18000a782  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a789  lea     rax, WPP_GLOBAL_Control
0x18000a790  cmp     rcx, rax
0x18000a793  jz      loc_18000AA7C
0x18000a799  test    byte ptr [rcx+1Ch], 10h
0x18000a79d  jz      loc_18000AA7C
0x18000a7a3  mov     edx, 0Fh
0x18000a7a8  jmp     loc_18000A677
0x18000a7ad  xor     r9d, r9d; lpName
0x18000a7b0  lea     rcx, [rbp+var_30]; lpEventAttributes
0x18000a7b4  xor     r8d, r8d; bInitialState
0x18000a7b7  mov     edx, edi; bManualReset
0x18000a7b9  call    cs:__imp_CreateEventW
0x18000a7bf  mov     cs:ghNewLocalPolicyEvent, rax
0x18000a7c6  test    rax, rax
0x18000a7c9  jnz     short loc_18000A802
0x18000a7cb  call    cs:__imp_GetLastError
0x18000a7d1  mov     ebx, eax
0x18000a7d3  test    eax, eax
0x18000a7d5  jz      short loc_18000A802
0x18000a7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7de  lea     rax, WPP_GLOBAL_Control
0x18000a7e5  cmp     rcx, rax
0x18000a7e8  jz      loc_18000AA7C
0x18000a7ee  test    byte ptr [rcx+1Ch], 10h
0x18000a7f2  jz      loc_18000AA7C
0x18000a7f8  mov     edx, 10h
0x18000a7fd  jmp     loc_18000A677
0x18000a802  xor     r9d, r9d; lpName
0x18000a805  lea     rcx, [rbp+var_30]; lpEventAttributes
0x18000a809  xor     r8d, r8d; bInitialState
0x18000a80c  mov     edx, edi; bManualReset
0x18000a80e  call    cs:__imp_CreateEventW
0x18000a814  mov     cs:ghForcedPolicyReloadEvent, rax
0x18000a81b  test    rax, rax
0x18000a81e  jnz     short loc_18000A857
0x18000a820  call    cs:__imp_GetLastError
0x18000a826  mov     ebx, eax
0x18000a828  test    eax, eax
0x18000a82a  jz      short loc_18000A857
0x18000a82c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a833  lea     rax, WPP_GLOBAL_Control
0x18000a83a  cmp     rcx, rax
0x18000a83d  jz      loc_18000AA7C
0x18000a843  test    byte ptr [rcx+1Ch], 10h
0x18000a847  jz      loc_18000AA7C
0x18000a84d  mov     edx, 11h
0x18000a852  jmp     loc_18000A677
0x18000a857  lea     r9, aIpsecPolicyCha_0; "IPSEC_POLICY_CHANGE_NOTIFY"
0x18000a85e  xor     r8d, r8d; bInitialState
0x18000a861  mov     edx, edi; bManualReset
0x18000a863  xor     ecx, ecx; lpEventAttributes
0x18000a865  call    cs:__imp_CreateEventW
0x18000a86b  mov     cs:ghPolicyChangeNotifyEvent, rax
0x18000a872  test    rax, rax
0x18000a875  jnz     short loc_18000A8AE
0x18000a877  call    cs:__imp_GetLastError
0x18000a87d  mov     ebx, eax
0x18000a87f  test    eax, eax
0x18000a881  jz      short loc_18000A8AE
0x18000a883  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a88a  lea     rax, WPP_GLOBAL_Control
0x18000a891  cmp     rcx, rax
0x18000a894  jz      loc_18000AA7C
0x18000a89a  test    byte ptr [rcx+1Ch], 10h
0x18000a89e  jz      loc_18000AA7C
0x18000a8a4  mov     edx, 12h
0x18000a8a9  jmp     loc_18000A677
0x18000a8ae  xor     r9d, r9d; lpName
0x18000a8b1  lea     rcx, [rbp+var_30]; lpEventAttributes
0x18000a8b5  xor     r8d, r8d; bInitialState
0x18000a8b8  mov     edx, edi; bManualReset
0x18000a8ba  call    cs:__imp_CreateEventW
0x18000a8c0  mov     cs:ghServiceStopEvent, rax
0x18000a8c7  test    rax, rax
0x18000a8ca  jnz     short loc_18000A903
0x18000a8cc  call    cs:__imp_GetLastError
0x18000a8d2  mov     ebx, eax
0x18000a8d4  test    eax, eax
0x18000a8d6  jz      short loc_18000A903
0x18000a8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8df  lea     rax, WPP_GLOBAL_Control
0x18000a8e6  cmp     rcx, rax
0x18000a8e9  jz      loc_18000AA7C
0x18000a8ef  test    byte ptr [rcx+1Ch], 10h
0x18000a8f3  jz      loc_18000AA7C
0x18000a8f9  mov     edx, 13h
0x18000a8fe  jmp     loc_18000A677
0x18000a903  lea     r9, aIpsecGpRefresh; "IPSEC_GP_REFRESH_EVENT"
0x18000a90a  xor     r8d, r8d; bInitialState
0x18000a90d  mov     edx, edi; bManualReset
0x18000a90f  lea     rcx, [rbp+var_30]; lpEventAttributes
0x18000a913  call    cs:__imp_CreateEventW
0x18000a919  mov     cs:ghGpupdateRefreshEvent, rax
0x18000a920  test    rax, rax
0x18000a923  jnz     short loc_18000A95C
0x18000a925  call    cs:__imp_GetLastError
0x18000a92b  mov     ebx, eax
0x18000a92d  test    eax, eax
0x18000a92f  jz      short loc_18000A95C
0x18000a931  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a938  lea     rax, WPP_GLOBAL_Control
0x18000a93f  cmp     rcx, rax
0x18000a942  jz      loc_18000AA7C
0x18000a948  test    byte ptr [rcx+1Ch], 10h
0x18000a94c  jz      loc_18000AA7C
0x18000a952  mov     edx, 14h
0x18000a957  jmp     loc_18000A677
0x18000a95c  mov     edx, 80000FA0h; dwSpinCount
0x18000a961  lea     rcx, gcServerListenSection; lpCriticalSection
0x18000a968  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000a96e  test    eax, eax
0x18000a970  jnz     short loc_18000A9A9
0x18000a972  call    cs:__imp_GetLastError
0x18000a978  mov     ebx, eax
0x18000a97a  test    eax, eax
0x18000a97c  jz      short loc_18000A9A9
0x18000a97e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a985  lea     rax, WPP_GLOBAL_Control
0x18000a98c  cmp     rcx, rax
0x18000a98f  jz      loc_18000AA7C
0x18000a995  test    byte ptr [rcx+1Ch], 10h
0x18000a999  jz      loc_18000AA7C
0x18000a99f  mov     edx, 15h
0x18000a9a4  jmp     loc_18000A677
0x18000a9a9  mov     edx, 80000FA0h; dwSpinCount
0x18000a9ae  mov     cs:gbServerListenSection, edi
0x18000a9b4  lea     rcx, gcSPDSection; lpCriticalSection
0x18000a9bb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000a9c1  test    eax, eax
0x18000a9c3  jnz     short loc_18000A9FC
0x18000a9c5  call    cs:__imp_GetLastError
0x18000a9cb  mov     ebx, eax
0x18000a9cd  test    eax, eax
0x18000a9cf  jz      short loc_18000A9FC
0x18000a9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9d8  lea     rax, WPP_GLOBAL_Control
0x18000a9df  cmp     rcx, rax
0x18000a9e2  jz      loc_18000AA7C
0x18000a9e8  test    byte ptr [rcx+1Ch], 10h
0x18000a9ec  jz      loc_18000AA7C
0x18000a9f2  mov     edx, 16h
0x18000a9f7  jmp     loc_18000A677
0x18000a9fc  mov     cs:gbSPDSection, edi
0x18000aa02  call    InitializeInterfaceChangeEvent
0x18000aa07  mov     ebx, eax
0x18000aa09  test    eax, eax
0x18000aa0b  jz      short loc_18000AA30
0x18000aa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa14  lea     rax, WPP_GLOBAL_Control
0x18000aa1b  cmp     rcx, rax
0x18000aa1e  jz      short loc_18000AA7C
0x18000aa20  test    byte ptr [rcx+1Ch], 10h
0x18000aa24  jz      short loc_18000AA7C
0x18000aa26  mov     edx, 17h
0x18000aa2b  jmp     loc_18000A677
0x18000aa30  call    ResetInterfaceChangeEvent
0x18000aa35  mov     ebx, eax
0x18000aa37  test    eax, eax
0x18000aa39  jz      short loc_18000AA5E
0x18000aa3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa42  lea     rax, WPP_GLOBAL_Control
0x18000aa49  cmp     rcx, rax
0x18000aa4c  jz      short loc_18000AA7C
0x18000aa4e  test    byte ptr [rcx+1Ch], 10h
0x18000aa52  jz      short loc_18000AA7C
0x18000aa54  mov     edx, 18h
0x18000aa59  jmp     loc_18000A677
0x18000aa5e  mov     rcx, cs:gpIpsecPolicyState
0x18000aa65  xorps   xmm0, xmm0
0x18000aa68  mov     eax, cs:gDefaultPollingInterval
0x18000aa6e  movups  xmmword ptr [rcx], xmm0
0x18000aa71  movups  xmmword ptr [rcx+10h], xmm0
0x18000aa75  movups  xmmword ptr [rcx+20h], xmm0
0x18000aa79  mov     [rcx+14h], eax
0x18000aa7c  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18000aa80  test    rcx, rcx
0x18000aa83  jz      short loc_18000AA8B
0x18000aa85  call    cs:__imp_LocalFree
0x18000aa8b  mov     rcx, [rbp+hMem]; hMem
0x18000aa8f  test    rcx, rcx
0x18000aa92  jz      short loc_18000AA9A
0x18000aa94  call    cs:__imp_LocalFree
0x18000aa9a  mov     rdi, [rsp+50h+arg_18]
0x18000aa9f  mov     eax, ebx
0x18000aaa1  mov     rbx, [rsp+50h+arg_10]
0x18000aaa6  add     rsp, 50h
0x18000aaaa  pop     rbp
0x18000aaab  retn
```
