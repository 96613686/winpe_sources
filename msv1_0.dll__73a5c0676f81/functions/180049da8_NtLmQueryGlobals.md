# NtLmQueryGlobals

- ea: `0x180049da8`
- end: `0x18004a100`
- name: `NtLmQueryGlobals`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a1c0`

## callees

- `0x180007700`
- `0x18002ee7c`
- `0x18002fb50`
- `0x180030844`
- `0x180047f50`
- `0x1800483a4`
- `0x180048a10`
- `0x180049da8`
- `0x18005a58c`
- `0x18006bd74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049eb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049e09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049e09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049f56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049fdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a06c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049f56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049fdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004a06c`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180049efd`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180049efd`
- `ntdll!RtlInitUnicodeString` at `0x180049fab`
- `ntdll!RtlInitUnicodeString` at `0x18004a034`
- `ntdll!RtlInitUnicodeString` at `0x180049fab`
- `ntdll!RtlInitUnicodeString` at `0x18004a034`

## pseudocode

```c
DWORD NtLmQueryGlobals()
{
  unsigned int (*v0)(void *); // rdx
  HKEY v1; // rcx
  __int64 v2; // r8
  void *v3; // r9
  DWORD LastError; // eax
  __int64 v6; // rdx
  DWORD v7; // eax
  HKEY v8; // rdi
  int v9; // esi
  WCHAR *v10; // rax
  WCHAR *v11; // rax
  __int64 v12; // r9
  DWORD lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD lpcbData; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v17[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[512]; // [rsp+40h] [rbp-C0h] BYREF

  Type = 0;
  memset_0(Data, 0, sizeof(Data));
  cbData = 0;
  *(_DWORD *)v17 = 0;
  lpcbData = 0;
  NtLmGlobalRegChangeNotifyEvent = CreateEventW(0, 0, 0, 0);
  if ( !NtLmGlobalRegChangeNotifyEvent )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, LastError);
    }
LABEL_5:
    if ( (int)GetLastError() > 0 )
      return (unsigned __int16)GetLastError() | 0xC0070000;
    else
      return GetLastError();
  }
  qword_180089C80 = SspRegistry::RegistryWatcher::CreateCommon(v1, v0, v2, v3, lpData);
  if ( !qword_180089C80 )
  {
    NtlmQueryPolicyChangeCallback(0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, v7);
    }
  }
  LOBYTE(v6) = 1;
  NtLmQueryDynamicGlobals(0, v6);
  NtLmGlobalRegWaitObject = (HANDLE)RegisterWaitForSingleObjectEx(
                                      NtLmGlobalRegChangeNotifyEvent,
                                      NtLmQueryDynamicGlobals,
                                      0,
                                      0xFFFFFFFFLL,
                                      128);
  if ( !NtLmGlobalRegWaitObject )
    goto LABEL_5;
  v8 = NtLmGlobalLsaMsv1_0Key;
  if ( !NtLmGlobalLsaMsv1_0Key )
    return 0;
  cbData = 510;
  v9 = 0;
  if ( RegQueryValueExW(NtLmGlobalLsaMsv1_0Key, L"MappedDomain", 0, &Type, Data, &cbData) || cbData > 0xFFFF )
  {
    RtlInitUnicodeString(&NtLmLocklessGlobalMappedDomainString, 0);
  }
  else
  {
    NtLmLocklessGlobalMappedDomainString.MaximumLength = cbData;
    NtLmLocklessGlobalMappedDomainString.Length = cbData - 2;
    v10 = (WCHAR *)NtLmAllocate(cbData);
    NtLmLocklessGlobalMappedDomainString.Buffer = v10;
    if ( v10 )
      memcpy_0(v10, Data, cbData);
  }
  cbData = 510;
  if ( RegQueryValueExW(v8, L"PreferredDomain", 0, &Type, Data, &cbData) || cbData > 0xFFFF )
  {
    RtlInitUnicodeString(&NtLmLocklessGlobalPreferredDomainString, 0);
  }
  else
  {
    NtLmLocklessGlobalPreferredDomainString.MaximumLength = cbData;
    NtLmLocklessGlobalPreferredDomainString.Length = cbData - 2;
    v11 = (WCHAR *)NtLmAllocate(cbData);
    NtLmLocklessGlobalPreferredDomainString.Buffer = v11;
    if ( v11 )
      memcpy_0(v11, Data, cbData);
  }
  lpcbData = 4;
  if ( !RegQueryValueExW(NtLmGlobalLsaMsv1_0Key, L"IPAddressRefreshInterval", 0, &Type, v17, &lpcbData)
    && lpcbData == 4
    && Type == 4 )
  {
    v12 = *(unsigned int *)v17;
    NtLmGlobalIPAddressRefreshInterval = *(_DWORD *)v17;
    if ( *(_DWORD *)v17 >= 0x5Au )
      goto LABEL_32;
    v12 = 90;
  }
  else
  {
    v12 = 180;
  }
  NtLmGlobalIPAddressRefreshInterval = v12;
LABEL_32:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids, v12);
  if ( (dword_180087A84 & 0x20) != 0 )
    return UpdateCredentialIsolationSecret();
  return v9;
}

```

## disassembly

```asm
0x180049da8  push    rbp
0x180049daa  push    rbx
0x180049dab  push    rsi
0x180049dac  push    rdi
0x180049dad  lea     rbp, [rsp-158h]
0x180049db5  sub     rsp, 258h
0x180049dbc  mov     rax, cs:__security_cookie
0x180049dc3  xor     rax, rsp
0x180049dc6  mov     [rbp+170h+var_30], rax
0x180049dcd  xor     edx, edx; Val
0x180049dcf  mov     [rsp+270h+Type], 0
0x180049dd7  mov     r8d, 200h; Size
0x180049ddd  lea     rcx, [rsp+270h+Data]; void *
0x180049de2  call    memset_0
0x180049de7  xor     r9d, r9d; lpName
0x180049dea  mov     [rsp+270h+cbData], 0
0x180049df2  xor     r8d, r8d; bInitialState
0x180049df5  mov     dword ptr [rsp+270h+var_234], 0
0x180049dfd  xor     edx, edx; bManualReset
0x180049dff  mov     [rsp+270h+var_238], 0
0x180049e07  xor     ecx, ecx; lpEventAttributes
0x180049e09  call    cs:__imp_CreateEventW
0x180049e0f  mov     cs:NtLmGlobalRegChangeNotifyEvent, rax
0x180049e16  test    rax, rax
0x180049e19  jnz     short loc_180049E81
0x180049e1b  mov     rax, cs:WPP_GLOBAL_Control
0x180049e22  lea     rbx, WPP_GLOBAL_Control
0x180049e29  cmp     rax, rbx
0x180049e2c  jz      short loc_180049E59
0x180049e2e  test    byte ptr [rax+1Ch], 2
0x180049e32  jz      short loc_180049E59
0x180049e34  call    cs:__imp_GetLastError
0x180049e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e41  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x180049e48  mov     edx, 52h ; 'R'
0x180049e4d  mov     r9d, eax
0x180049e50  mov     rcx, [rcx+10h]
0x180049e54  call    WPP_SF_d
0x180049e59  call    cs:__imp_GetLastError
0x180049e5f  test    eax, eax
0x180049e61  jg      short loc_180049E6E
0x180049e63  call    cs:__imp_GetLastError
0x180049e69  jmp     loc_18004A0E5
0x180049e6e  call    cs:__imp_GetLastError
0x180049e74  movzx   eax, ax
0x180049e77  or      eax, 0C0070000h
0x180049e7c  jmp     loc_18004A0E5
0x180049e81  call    ?CreateCommon@RegistryWatcher@SspRegistry@@CAPEAV12@PEAUHKEY__@@P6AKPEAX@Z_N133@Z; SspRegistry::RegistryWatcher::CreateCommon(HKEY__ *,ulong (*)(void *),bool,void *,bool,bool)
0x180049e86  mov     cs:qword_180089C80, rax
0x180049e8d  lea     rbx, WPP_GLOBAL_Control
0x180049e94  test    rax, rax
0x180049e97  jnz     short loc_180049ED7
0x180049e99  xor     ecx, ecx; void *
0x180049e9b  call    ?NtlmQueryPolicyChangeCallback@@YAKPEAX@Z; NtlmQueryPolicyChangeCallback(void *)
0x180049ea0  mov     rax, cs:WPP_GLOBAL_Control
0x180049ea7  cmp     rax, rbx
0x180049eaa  jz      short loc_180049ED7
0x180049eac  test    byte ptr [rax+1Ch], 2
0x180049eb0  jz      short loc_180049ED7
0x180049eb2  call    cs:__imp_GetLastError
0x180049eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ebf  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x180049ec6  mov     edx, 53h ; 'S'
0x180049ecb  mov     r9d, eax
0x180049ece  mov     rcx, [rcx+10h]
0x180049ed2  call    WPP_SF_d
0x180049ed7  mov     dl, 1
0x180049ed9  xor     ecx, ecx
0x180049edb  call    NtLmQueryDynamicGlobals
0x180049ee0  mov     rcx, cs:NtLmGlobalRegChangeNotifyEvent
0x180049ee7  lea     rdx, NtLmQueryDynamicGlobals
0x180049eee  or      r9d, 0FFFFFFFFh
0x180049ef2  mov     dword ptr [rsp+270h+lpData], 80h
0x180049efa  xor     r8d, r8d
0x180049efd  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180049f03  mov     cs:NtLmGlobalRegWaitObject, rax
0x180049f0a  test    rax, rax
0x180049f0d  jz      loc_180049E59
0x180049f13  mov     rdi, cs:NtLmGlobalLsaMsv1_0Key
0x180049f1a  test    rdi, rdi
0x180049f1d  jnz     short loc_180049F26
0x180049f1f  xor     eax, eax
0x180049f21  jmp     loc_18004A0E5
0x180049f26  lea     rax, [rsp+270h+cbData]
0x180049f2b  mov     [rsp+270h+cbData], 1FEh
0x180049f33  mov     [rsp+270h+lpcbData], rax; lpcbData
0x180049f38  lea     r9, [rsp+270h+Type]; lpType
0x180049f3d  lea     rax, [rsp+270h+Data]
0x180049f42  xor     r8d, r8d; lpReserved
0x180049f45  lea     rdx, aMappeddomain; "MappedDomain"
0x180049f4c  mov     [rsp+270h+lpData], rax; lpData
0x180049f51  mov     rcx, rdi; hKey
0x180049f54  xor     esi, esi
0x180049f56  call    cs:__imp_RegQueryValueExW
0x180049f5c  test    eax, eax
0x180049f5e  jnz     short loc_180049FA2
0x180049f60  mov     ecx, [rsp+270h+cbData]; uBytes
0x180049f64  cmp     ecx, 0FFFFh
0x180049f6a  ja      short loc_180049FA2
0x180049f6c  lea     eax, [rcx-2]
0x180049f6f  mov     cs:NtLmLocklessGlobalMappedDomainString.MaximumLength, cx
0x180049f76  mov     cs:NtLmLocklessGlobalMappedDomainString.Length, ax
0x180049f7d  call    NtLmAllocate
0x180049f82  mov     cs:NtLmLocklessGlobalMappedDomainString.Buffer, rax
0x180049f89  test    rax, rax
0x180049f8c  jz      short loc_180049FB1
0x180049f8e  mov     r8d, [rsp+270h+cbData]; Size
0x180049f93  lea     rdx, [rsp+270h+Data]; Src
0x180049f98  mov     rcx, rax; void *
0x180049f9b  call    memcpy_0
0x180049fa0  jmp     short loc_180049FB1
0x180049fa2  xor     edx, edx; SourceString
0x180049fa4  lea     rcx, NtLmLocklessGlobalMappedDomainString; DestinationString
0x180049fab  call    cs:__imp_RtlInitUnicodeString
0x180049fb1  lea     rax, [rsp+270h+cbData]
0x180049fb6  mov     [rsp+270h+cbData], 1FEh
0x180049fbe  mov     [rsp+270h+lpcbData], rax; lpcbData
0x180049fc3  lea     r9, [rsp+270h+Type]; lpType
0x180049fc8  lea     rax, [rsp+270h+Data]
0x180049fcd  xor     r8d, r8d; lpReserved
0x180049fd0  lea     rdx, aPreferreddomai; "PreferredDomain"
0x180049fd7  mov     [rsp+270h+lpData], rax; lpData
0x180049fdc  mov     rcx, rdi; hKey
0x180049fdf  call    cs:__imp_RegQueryValueExW
0x180049fe5  test    eax, eax
0x180049fe7  jnz     short loc_18004A02B
0x180049fe9  mov     ecx, [rsp+270h+cbData]; uBytes
0x180049fed  cmp     ecx, 0FFFFh
0x180049ff3  ja      short loc_18004A02B
0x180049ff5  lea     eax, [rcx-2]
0x180049ff8  mov     cs:NtLmLocklessGlobalPreferredDomainString.MaximumLength, cx
0x180049fff  mov     cs:NtLmLocklessGlobalPreferredDomainString.Length, ax
0x18004a006  call    NtLmAllocate
0x18004a00b  mov     cs:NtLmLocklessGlobalPreferredDomainString.Buffer, rax
0x18004a012  test    rax, rax
0x18004a015  jz      short loc_18004A03A
0x18004a017  mov     r8d, [rsp+270h+cbData]; Size
0x18004a01c  lea     rdx, [rsp+270h+Data]; Src
0x18004a021  mov     rcx, rax; void *
0x18004a024  call    memcpy_0
0x18004a029  jmp     short loc_18004A03A
0x18004a02b  xor     edx, edx; SourceString
0x18004a02d  lea     rcx, NtLmLocklessGlobalPreferredDomainString; DestinationString
0x18004a034  call    cs:__imp_RtlInitUnicodeString
0x18004a03a  mov     rcx, cs:NtLmGlobalLsaMsv1_0Key; hKey
0x18004a041  lea     rax, [rsp+270h+var_238]
0x18004a046  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18004a04b  lea     r9, [rsp+270h+Type]; lpType
0x18004a050  lea     rax, [rsp+270h+var_234]
0x18004a055  mov     [rsp+270h+var_238], 4
0x18004a05d  xor     r8d, r8d; lpReserved
0x18004a060  mov     [rsp+270h+lpData], rax; lpData
0x18004a065  lea     rdx, aIpaddressrefre; "IPAddressRefreshInterval"
0x18004a06c  call    cs:__imp_RegQueryValueExW
0x18004a072  test    eax, eax
0x18004a074  jnz     short loc_18004A09C
0x18004a076  cmp     [rsp+270h+var_238], 4
0x18004a07b  jnz     short loc_18004A09C
0x18004a07d  cmp     [rsp+270h+Type], 4
0x18004a082  jnz     short loc_18004A09C
0x18004a084  mov     r9d, dword ptr [rsp+270h+var_234]
0x18004a089  mov     cs:NtLmGlobalIPAddressRefreshInterval, r9d
0x18004a090  cmp     r9d, 5Ah ; 'Z'
0x18004a094  jnb     short loc_18004A0A9
0x18004a096  lea     r9d, [rax+5Ah]
0x18004a09a  jmp     short loc_18004A0A2
0x18004a09c  mov     r9d, 0B4h
0x18004a0a2  mov     cs:NtLmGlobalIPAddressRefreshInterval, r9d
0x18004a0a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0b0  cmp     rcx, rbx
0x18004a0b3  jz      short loc_18004A0D3
0x18004a0b5  test    dword ptr [rcx+1Ch], 1000h
0x18004a0bc  jz      short loc_18004A0D3
0x18004a0be  mov     rcx, [rcx+10h]
0x18004a0c2  lea     r8, WPP_0f9030aed77d334c8db677e9a1d706bf_Traceguids
0x18004a0c9  mov     edx, 54h ; 'T'
0x18004a0ce  call    WPP_SF_d
0x18004a0d3  test    byte ptr cs:dword_180087A84, 20h
0x18004a0da  jz      short loc_18004A0E3
0x18004a0dc  call    ?UpdateCredentialIsolationSecret@@YAJXZ; UpdateCredentialIsolationSecret(void)
0x18004a0e1  mov     esi, eax
0x18004a0e3  mov     eax, esi
0x18004a0e5  mov     rcx, [rbp+170h+var_30]
0x18004a0ec  xor     rcx, rsp; StackCookie
0x18004a0ef  call    __security_check_cookie
0x18004a0f4  add     rsp, 258h
0x18004a0fb  pop     rdi
0x18004a0fc  pop     rsi
0x18004a0fd  pop     rbx
0x18004a0fe  pop     rbp
0x18004a0ff  retn
```
