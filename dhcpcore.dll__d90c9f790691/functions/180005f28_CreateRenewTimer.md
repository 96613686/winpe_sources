# CreateRenewTimer

- ea: `0x180005f28`
- end: `0x18000624c`
- name: `CreateRenewTimer`
- size: `804`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023928`

## callees

- `0x180005f28`
- `0x180006440`
- `0x18001cef0`
- `0x18001d826`
- `0x18004d9e8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180006219`
- `ntdll!RtlNtStatusToDosError` at `0x180006219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000618d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000618d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000615f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000615f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000614f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000614f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005fac`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005fac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006027`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006027`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005fd5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006014`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005fd5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006014`
- `EventAggregation!EaCreateAggregatedEvent` at `0x18000612d`
- `EventAggregation!EaCreateAggregatedEvent` at `0x18000612d`

## pseudocode

```c
__int64 __fastcall CreateRenewTimer(unsigned int a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v5; // r14
  HANDLE CurrentProcess; // rax
  _QWORD *v8; // rdi
  NTSTATUS AggregatedEvent; // eax
  DWORD v10; // ebx
  DWORD LastError; // eax
  __int64 v13; // rdx
  ULONG v14; // eax
  __int64 v15; // rdx
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  _FILETIME v19; // [rsp+68h] [rbp-98h]
  _QWORD v20[10]; // [rsp+70h] [rbp-90h] BYREF
  GUID v21; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v22; // [rsp+D0h] [rbp-30h]
  const wchar_t *v23; // [rsp+E0h] [rbp-20h] BYREF
  int v24; // [rsp+E8h] [rbp-18h]
  int v25; // [rsp+F0h] [rbp-10h]
  const wchar_t *v26; // [rsp+100h] [rbp+0h]
  int v27; // [rsp+108h] [rbp+8h]
  __int64 v28; // [rsp+110h] [rbp+10h]
  const wchar_t *v29; // [rsp+120h] [rbp+20h]
  int v30; // [rsp+128h] [rbp+28h]
  int v31; // [rsp+130h] [rbp+30h]
  const wchar_t *v32; // [rsp+140h] [rbp+40h]
  int v33; // [rsp+148h] [rbp+48h]
  int v34; // [rsp+150h] [rbp+50h]
  const wchar_t *v35; // [rsp+160h] [rbp+60h]
  int v36; // [rsp+168h] [rbp+68h]
  const wchar_t *v37; // [rsp+170h] [rbp+70h]

  v5 = a1;
  TokenHandle = 0;
  TokenInformationLength = 0;
  SystemTimeAsFileTime = 0;
  memset_0(v20, 0, 0x48u);
  *a4 = 0;
  v21 = 0;
  v22 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_7;
    v13 = 69;
    goto LABEL_15;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError != 122 )
    {
      if ( (xmmword_1800616A0 & 2) == 0 )
        goto LABEL_7;
      v13 = 70;
      goto LABEL_15;
    }
  }
  v8 = (_QWORD *)DhcpAlloc(TokenInformationLength);
  if ( v8 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v19 = SystemTimeAsFileTime;
      v23 = L"Type";
      v26 = L"InitialDueTime";
      v29 = L"WakeEnabled";
      v32 = L"WindowInSeconds";
      v35 = L"ClientId";
      LOWORD(v22) = 5;
      *((_QWORD *)&v22 + 1) = &v23;
      v20[0] = &v21;
      v24 = 0;
      v25 = 4;
      v27 = 1;
      v30 = 0;
      v31 = 1;
      v33 = 0;
      v34 = 20;
      v36 = 2;
      v21 = GUID_TIME_BROKER;
      v28 = *(_QWORD *)&SystemTimeAsFileTime + 10000 * v5;
      v37 = L"DHCP Renew App";
      v20[7] = L"DHCP Renew App";
      v20[8] = *v8;
      AggregatedEvent = EaCreateAggregatedEvent(v20, 0, &OnTimeoutCallback, 0, 0, 0, a2, 0, a4);
      v10 = 0;
      if ( AggregatedEvent >= 0 )
        goto LABEL_6;
      v14 = RtlNtStatusToDosError(AggregatedEvent);
      v10 = v14;
      if ( (xmmword_1800616A0 & 2) == 0 )
        goto LABEL_6;
      v15 = 73;
    }
    else
    {
      v14 = GetLastError();
      v10 = v14;
      if ( (xmmword_1800616A0 & 2) == 0 )
      {
LABEL_6:
        HeapFree(NtCurrentPeb()->ProcessHeap, 0, v8);
        goto LABEL_7;
      }
      v15 = 72;
    }
    WPP_SF_d(1025, v15, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, v14);
    goto LABEL_6;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( (xmmword_1800616A0 & 2) != 0 )
  {
    v13 = 71;
LABEL_15:
    WPP_SF_d(1025, v13, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, LastError);
  }
LABEL_7:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x180005f28  mov     [rsp-8+arg_0], rbx
0x180005f2d  push    rbp
0x180005f2e  push    rsi
0x180005f2f  push    rdi
0x180005f30  push    r14
0x180005f32  push    r15
0x180005f34  lea     rbp, [rsp-90h]
0x180005f3c  sub     rsp, 190h
0x180005f43  mov     rax, cs:__security_cookie
0x180005f4a  xor     rax, rsp
0x180005f4d  mov     [rbp+0B0h+var_30], rax
0x180005f54  mov     r15, rdx
0x180005f57  mov     r14d, ecx
0x180005f5a  xor     edx, edx; Val
0x180005f5c  mov     [rsp+1B0h+TokenHandle], 0
0x180005f65  lea     rcx, [rsp+1B0h+var_140]; void *
0x180005f6a  mov     [rsp+1B0h+TokenInformationLength], 0
0x180005f72  mov     rsi, r9
0x180005f75  mov     qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180005f7e  lea     r8d, [rdx+48h]; Size
0x180005f82  call    memset_0
0x180005f87  xorps   xmm0, xmm0
0x180005f8a  mov     qword ptr [rsi], 0
0x180005f91  movups  [rbp+0B0h+var_F0], xmm0
0x180005f95  movups  [rbp+0B0h+var_E0], xmm0
0x180005f99  call    cs:__imp_GetCurrentProcess
0x180005f9f  lea     r8, [rsp+1B0h+TokenHandle]; TokenHandle
0x180005fa4  mov     edx, 20008h; DesiredAccess
0x180005fa9  mov     rcx, rax; ProcessHandle
0x180005fac  call    cs:__imp_OpenProcessToken
0x180005fb2  test    eax, eax
0x180005fb4  jz      loc_1800061AE
0x180005fba  mov     r9d, [rsp+1B0h+TokenInformationLength]; TokenInformationLength
0x180005fbf  lea     rax, [rsp+1B0h+TokenInformationLength]
0x180005fc4  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x180005fc9  xor     r8d, r8d; TokenInformation
0x180005fcc  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x180005fd1  lea     edx, [r8+1]; TokenInformationClass
0x180005fd5  call    cs:__imp_GetTokenInformation
0x180005fdb  test    eax, eax
0x180005fdd  jz      loc_18000618D
0x180005fe3  mov     ecx, [rsp+1B0h+TokenInformationLength]
0x180005fe7  call    DhcpAlloc
0x180005fec  mov     rdi, rax
0x180005fef  test    rax, rax
0x180005ff2  jz      loc_1800061E4
0x180005ff8  mov     r9d, [rsp+1B0h+TokenInformationLength]; TokenInformationLength
0x180005ffd  lea     rax, [rsp+1B0h+TokenInformationLength]
0x180006002  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x180006007  mov     r8, rdi; TokenInformation
0x18000600a  mov     edx, 1; TokenInformationClass
0x18000600f  mov     [rsp+1B0h+ReturnLength], rax; ReturnLength
0x180006014  call    cs:__imp_GetTokenInformation
0x18000601a  test    eax, eax
0x18000601c  jz      loc_1800061FB
0x180006022  lea     rcx, [rsp+1B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006027  call    cs:__imp_GetSystemTimeAsFileTime
0x18000602d  mov     eax, [rsp+1B0h+SystemTimeAsFileTime.dwHighDateTime]
0x180006031  lea     r8, OnTimeoutCallback
0x180006038  movups  xmm0, xmmword ptr cs:GUID_TIME_BROKER.Data1
0x18000603f  mov     dword ptr [rsp+1B0h+var_148+4], eax
0x180006043  xor     r9d, r9d
0x180006046  mov     eax, [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime]
0x18000604a  xor     edx, edx
0x18000604c  mov     dword ptr [rsp+1B0h+var_148], eax
0x180006050  lea     rax, aType; "Type"
0x180006057  mov     [rbp+0B0h+var_D0], rax
0x18000605b  lea     rax, aInitialduetime; "InitialDueTime"
0x180006062  mov     [rbp+0B0h+var_B0], rax
0x180006066  lea     rax, aWakeenabled; "WakeEnabled"
0x18000606d  mov     [rbp+0B0h+var_90], rax
0x180006071  lea     rax, aWindowinsecond; "WindowInSeconds"
0x180006078  mov     [rbp+0B0h+var_70], rax
0x18000607c  lea     rax, aClientid; "ClientId"
0x180006083  mov     [rbp+0B0h+var_50], rax
0x180006087  mov     eax, 5
0x18000608c  mov     word ptr [rbp+0B0h+var_E0], ax
0x180006090  lea     rax, [rbp+0B0h+var_D0]
0x180006094  mov     [rsp+1B0h+var_170], rsi
0x180006099  mov     qword ptr [rbp+0B0h+var_E0+8], rax
0x18000609d  lea     rax, [rbp+0B0h+var_F0]
0x1800060a1  mov     [rsp+1B0h+var_178], 0
0x1800060a9  mov     [rsp+1B0h+var_140], rax
0x1800060ae  mov     [rbp+0B0h+var_C8], 0
0x1800060b5  mov     [rbp+0B0h+var_C0], 4
0x1800060bc  mov     [rbp+0B0h+var_A8], 1
0x1800060c3  mov     [rbp+0B0h+var_88], 0
0x1800060ca  mov     [rbp+0B0h+var_80], 1
0x1800060d1  mov     [rbp+0B0h+var_68], 0
0x1800060d8  mov     [rbp+0B0h+var_60], 14h
0x1800060df  mov     [rbp+0B0h+var_48], 2
0x1800060e6  movdqu  [rbp+0B0h+var_F0], xmm0
0x1800060eb  mov     [rsp+1B0h+var_180], r15
0x1800060f0  imul    rcx, r14, 2710h
0x1800060f7  mov     [rsp+1B0h+var_188], 0
0x180006100  add     rcx, [rsp+1B0h+var_148]
0x180006105  mov     [rbp+0B0h+var_A0], rcx
0x180006109  lea     rcx, aDhcpRenewApp; "DHCP Renew App"
0x180006110  mov     [rbp+0B0h+var_40], rcx
0x180006114  mov     [rbp+0B0h+var_108], rcx
0x180006118  lea     rcx, [rsp+1B0h+var_140]
0x18000611d  mov     rax, [rdi]
0x180006120  mov     [rbp+0B0h+var_100], rax
0x180006124  mov     [rsp+1B0h+ReturnLength], 0
0x18000612d  call    cs:__imp_EaCreateAggregatedEvent
0x180006133  xor     ebx, ebx
0x180006135  test    eax, eax
0x180006137  js      loc_180006217
0x18000613d  mov     rcx, gs:60h
0x180006146  mov     r8, rdi; lpMem
0x180006149  xor     edx, edx; dwFlags
0x18000614b  mov     rcx, [rcx+30h]; hHeap
0x18000614f  call    cs:__imp_HeapFree
0x180006155  mov     rcx, [rsp+1B0h+TokenHandle]; hObject
0x18000615a  test    rcx, rcx
0x18000615d  jz      short loc_180006165
0x18000615f  call    cs:__imp_CloseHandle
0x180006165  mov     eax, ebx
0x180006167  mov     rcx, [rbp+0B0h+var_30]
0x18000616e  xor     rcx, rsp; StackCookie
0x180006171  call    __security_check_cookie
0x180006176  mov     rbx, [rsp+1B0h+arg_0]
0x18000617e  add     rsp, 190h
0x180006185  pop     r15
0x180006187  pop     r14
0x180006189  pop     rdi
0x18000618a  pop     rsi
0x18000618b  pop     rbp
0x18000618c  retn
0x18000618d  call    cs:__imp_GetLastError
0x180006193  mov     ebx, eax
0x180006195  cmp     eax, 7Ah ; 'z'
0x180006198  jz      loc_180005FE3
0x18000619e  test    byte ptr cs:xmmword_1800616A0, 2
0x1800061a5  jz      short loc_180006155
0x1800061a7  mov     edx, 46h ; 'F'
0x1800061ac  jmp     short loc_1800061CB
0x1800061ae  call    cs:__imp_GetLastError
0x1800061b4  mov     ebx, eax
0x1800061b6  test    byte ptr cs:xmmword_1800616A0, 2
0x1800061bd  jz      short loc_180006155
0x1800061bf  mov     edx, 45h ; 'E'
0x1800061c4  jmp     short loc_1800061CB
0x1800061c6  mov     edx, 47h ; 'G'
0x1800061cb  mov     ecx, 401h
0x1800061d0  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x1800061d7  mov     r9d, eax
0x1800061da  call    WPP_SF_d
0x1800061df  jmp     loc_180006155
0x1800061e4  call    cs:__imp_GetLastError
0x1800061ea  mov     ebx, eax
0x1800061ec  test    byte ptr cs:xmmword_1800616A0, 2
0x1800061f3  jz      loc_180006155
0x1800061f9  jmp     short loc_1800061C6
0x1800061fb  call    cs:__imp_GetLastError
0x180006201  mov     ebx, eax
0x180006203  test    byte ptr cs:xmmword_1800616A0, 2
0x18000620a  jz      loc_18000613D
0x180006210  mov     edx, 48h ; 'H'
0x180006215  jmp     short loc_180006233
0x180006217  mov     ecx, eax; Status
0x180006219  call    cs:__imp_RtlNtStatusToDosError
0x18000621f  mov     ebx, eax
0x180006221  test    byte ptr cs:xmmword_1800616A0, 2
0x180006228  jz      loc_18000613D
0x18000622e  mov     edx, 49h ; 'I'
0x180006233  mov     r9d, eax
0x180006236  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18000623d  mov     ecx, 401h
0x180006242  call    WPP_SF_d
0x180006247  jmp     loc_18000613D
```
