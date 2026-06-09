# PerflibciEnsureCounterSetList(void)

- ea: `0x180006bc0`
- end: `0x180006f31`
- name: `?PerflibciEnsureCounterSetList@@YAKXZ`
- size: `881`
- prototype: `DWORD(void)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180002810`
- `0x180003b40`
- `0x1800044a0`
- `0x180005f20`
- `0x18000e054`
- `0x180015250`

## callees

- `0x180005da0`
- `0x180006bc0`
- `0x1800072d0`
- `0x180008042`
- `0x180008050`
- `0x18000c2b0`
- `0x18000d158`
- `0x18000d478`
- `0x18000d9c4`
- `0x18000dc48`
- `0x18000e158`

## import_xrefs

- `ntdll!NtEnumerateKey` at `0x180006ddb`
- `ntdll!NtEnumerateKey` at `0x180006ddb`
- `ntdll!RtlNtStatusToDosError` at `0x180006e12`
- `ntdll!RtlNtStatusToDosError` at `0x180006e12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006eb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006e7f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006eb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006c04`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006c04`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ee1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ee1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006c28`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006c28`

## string_xrefs

- `0x180006c63`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`
- `0x180006c87`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
DWORD PerflibciEnsureCounterSetList(void)
{
  DWORD result; // eax
  char v1; // di
  unsigned int *v2; // r8
  __int64 v3; // rcx
  ULONG v4; // ebx
  unsigned int *v5; // r8
  unsigned int v6; // ecx
  char *v7; // rsi
  ULONG v8; // ebx
  int i; // r14d
  int v10; // eax
  unsigned int v11; // ecx
  unsigned __int8 v12[4]; // [rsp+40h] [rbp+7h] BYREF
  ULONG ResultLength; // [rsp+44h] [rbp+Bh] BYREF
  HKEY hKey; // [rsp+48h] [rbp+Fh] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+17h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp+1Fh] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+67h] BYREF
  unsigned int v18; // [rsp+A8h] [rbp+6Fh] BYREF
  unsigned int v19; // [rsp+B0h] [rbp+77h] BYREF
  unsigned int v20; // [rsp+B8h] [rbp+7Fh] BYREF

  hKey = 0;
  KeyHandle = 0;
  ResultLength = 0;
  *(_DWORD *)v12 = 0;
  v20 = 0;
  Data = 0;
  SystemTimeAsFileTime = 0;
  if ( !g_hGlobalMutex )
    return 87;
  result = WaitForSingleObject(g_hGlobalMutex, 0xEA60u);
  if ( result )
    return result;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *(_QWORD *)&SystemTimeAsFileTime < g_LastRefreshTime + 18000000000LL )
  {
    v4 = 0;
    goto LABEL_37;
  }
  PerflibciSetObjectsValidityState(0);
  if ( (unsigned int)PerfpAcquireInstallationMutex() )
  {
    v1 = 0;
LABEL_8:
    v4 = PerflibciOpenKey(
           0,
           L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
           0x20019u,
           (void **)&hKey);
    if ( v4 )
      goto LABEL_34;
    goto LABEL_9;
  }
  v1 = 1;
  if ( PerflibciOpenKey(
         0,
         L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
         0x2001Fu,
         (void **)&hKey) )
  {
    goto LABEL_8;
  }
LABEL_9:
  v18 = 0;
  v19 = 4;
  v4 = PrivateRegQueryValueExT(hKey, L"Last Counter", v2, &v18, v12, &v19, 1);
  if ( v4 )
    goto LABEL_34;
  if ( v18 != 4 )
    goto LABEL_33;
  v18 = 0;
  v19 = 4;
  v4 = PrivateRegQueryValueExT(hKey, L"Last Help", v5, &v18, (unsigned __int8 *)&v20, &v19, 1);
  if ( v4 )
    goto LABEL_34;
  if ( v18 == 4 )
  {
    v6 = v20;
    if ( *(_DWORD *)v12 > v20 )
      v6 = *(_DWORD *)v12;
    Data = v6;
    if ( v1 && !PerflibciOpenKey(hKey, L"_V2Providers", 0x2001Fu, &KeyHandle)
      || (v4 = PerflibciOpenKey(hKey, L"_V2Providers", 0x20019u, &KeyHandle)) == 0 )
    {
      v7 = (char *)operator new(0x418u);
      if ( v7 )
      {
        v8 = 0;
        for ( i = 0; ; ++i )
        {
          memset_0(v7, 0, 0x418u);
          v10 = NtEnumerateKey(KeyHandle, v8, KeyBasicInformation, v7, 0x418u, &ResultLength);
          v8 = i + 1;
          if ( v10 < 0 )
            break;
          PerflibciBuildProvider(KeyHandle, v7 + 16, &Data);
        }
        if ( v10 == -2147483622 )
          v4 = 0;
        else
          v4 = RtlNtStatusToDosError(v10);
        operator delete(v7);
        PerflibciCloseKey(KeyHandle);
        if ( !v4 )
        {
          g_LastRefreshTime = (unsigned __int64)SystemTimeAsFileTime;
          if ( v1 )
          {
            v11 = v20;
            if ( *(_DWORD *)v12 > v20 )
              v11 = *(_DWORD *)v12;
            if ( v11 != Data && !RegSetValueExW(hKey, L"Last Counter", 0, 4u, (const BYTE *)&Data, 4u) )
            {
              ++Data;
              RegSetValueExW(hKey, L"Last Help", 0, 4u, (const BYTE *)&Data, 4u);
            }
            goto LABEL_35;
          }
          goto LABEL_37;
        }
      }
      else
      {
        v4 = 14;
        PerflibciCloseKey(KeyHandle);
      }
    }
  }
  else
  {
LABEL_33:
    v4 = 13;
  }
LABEL_34:
  LOBYTE(v3) = 1;
  PerflibciSetObjectsValidityState(v3);
  if ( v1 )
LABEL_35:
    ReleaseMutex(hMutex);
LABEL_37:
  PerflibciLocalReleaseMutex(g_hGlobalMutex);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    PerflibciCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180006bc0  push    rbp
0x180006bc2  push    r15
0x180006bc4  lea     rbp, [rsp-4Fh]
0x180006bc9  sub     rsp, 88h
0x180006bd0  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; hHandle
0x180006bd7  xor     r15d, r15d
0x180006bda  mov     [rbp+57h+hKey], r15
0x180006bde  mov     [rbp+57h+KeyHandle], r15
0x180006be2  mov     [rbp+57h+var_4C], r15d
0x180006be6  mov     dword ptr [rbp+57h+var_50], r15d
0x180006bea  mov     [rbp+57h+arg_18], r15d
0x180006bee  mov     [rbp+57h+Data], r15d
0x180006bf2  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180006bf6  test    rcx, rcx
0x180006bf9  jz      loc_180006F21
0x180006bff  mov     edx, 0EA60h; dwMilliseconds
0x180006c04  call    cs:__imp_WaitForSingleObject
0x180006c0a  test    eax, eax
0x180006c0c  jnz     loc_180006F26
0x180006c12  mov     [rsp+90h+var_10], rbx
0x180006c1a  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006c1e  mov     [rsp+90h+var_18], rsi
0x180006c23  mov     [rsp+90h+var_20], rdi
0x180006c28  call    cs:__imp_GetSystemTimeAsFileTime
0x180006c2e  mov     rcx, 430E23400h
0x180006c38  add     rcx, cs:?g_LastRefreshTime@@3_KA; unsigned __int64 g_LastRefreshTime
0x180006c3f  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180006c43  jb      loc_180006EE9
0x180006c49  xor     ecx, ecx
0x180006c4b  call    PerflibciSetObjectsValidityState
0x180006c50  call    PerfpAcquireInstallationMutex
0x180006c55  test    eax, eax
0x180006c57  jnz     short loc_180006C7A
0x180006c59  lea     r9, [rbp+57h+hKey]
0x180006c5d  mov     r8d, 2001Fh
0x180006c63  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180006c6a  xor     ecx, ecx
0x180006c6c  mov     dil, 1
0x180006c6f  call    PerflibciOpenKey
0x180006c74  test    eax, eax
0x180006c76  jnz     short loc_180006C7D
0x180006c78  jmp     short loc_180006C9F
0x180006c7a  xor     dil, dil
0x180006c7d  lea     r9, [rbp+57h+hKey]
0x180006c81  mov     r8d, 20019h
0x180006c87  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180006c8e  xor     ecx, ecx
0x180006c90  call    PerflibciOpenKey
0x180006c95  mov     ebx, eax
0x180006c97  test    eax, eax
0x180006c99  jnz     loc_180006ECE
0x180006c9f  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x180006ca3  lea     rax, [rbp+57h+arg_10]
0x180006ca7  mov     [rsp+90h+var_60], 1; int
0x180006caf  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180006cb3  mov     [rsp+90h+ResultLength], rax; unsigned int *
0x180006cb8  lea     rdx, ?LastCounter@@3QBGB; "Last Counter"
0x180006cbf  lea     rax, [rbp+57h+var_50]
0x180006cc3  mov     [rbp+57h+arg_8], r15d
0x180006cc7  mov     qword ptr [rsp+90h+Length], rax; unsigned __int8 *
0x180006ccc  mov     [rbp+57h+arg_10], 4
0x180006cd3  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180006cd8  mov     ebx, eax
0x180006cda  test    eax, eax
0x180006cdc  jnz     loc_180006ECE
0x180006ce2  cmp     [rbp+57h+arg_8], 4
0x180006ce6  jnz     loc_180006EC9
0x180006cec  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x180006cf0  lea     rax, [rbp+57h+arg_10]
0x180006cf4  mov     [rsp+90h+var_60], 1; int
0x180006cfc  lea     r9, [rbp+57h+arg_8]; unsigned int *
0x180006d00  mov     [rsp+90h+ResultLength], rax; unsigned int *
0x180006d05  lea     rdx, ?LastHelp@@3QBGB; "Last Help"
0x180006d0c  lea     rax, [rbp+57h+arg_18]
0x180006d10  mov     [rbp+57h+arg_8], r15d
0x180006d14  mov     qword ptr [rsp+90h+Length], rax; unsigned __int8 *
0x180006d19  mov     [rbp+57h+arg_10], 4
0x180006d20  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180006d25  mov     ebx, eax
0x180006d27  test    eax, eax
0x180006d29  jnz     loc_180006ECE
0x180006d2f  cmp     [rbp+57h+arg_8], 4
0x180006d33  jnz     loc_180006EC9
0x180006d39  mov     ecx, [rbp+57h+arg_18]
0x180006d3c  cmp     dword ptr [rbp+57h+var_50], ecx
0x180006d3f  cmova   ecx, dword ptr [rbp+57h+var_50]
0x180006d43  mov     [rbp+57h+Data], ecx
0x180006d46  test    dil, dil
0x180006d49  jz      short loc_180006D69
0x180006d4b  mov     rcx, [rbp+57h+hKey]
0x180006d4f  lea     r9, [rbp+57h+KeyHandle]
0x180006d53  mov     r8d, 2001Fh
0x180006d59  lea     rdx, aV2providers; "_V2Providers"
0x180006d60  call    PerflibciOpenKey
0x180006d65  test    eax, eax
0x180006d67  jz      short loc_180006D8D
0x180006d69  mov     rcx, [rbp+57h+hKey]
0x180006d6d  lea     r9, [rbp+57h+KeyHandle]
0x180006d71  mov     r8d, 20019h
0x180006d77  lea     rdx, aV2providers; "_V2Providers"
0x180006d7e  call    PerflibciOpenKey
0x180006d83  mov     ebx, eax
0x180006d85  test    eax, eax
0x180006d87  jnz     loc_180006ECE
0x180006d8d  mov     ecx, 418h
0x180006d92  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180006d97  mov     rsi, rax
0x180006d9a  test    rax, rax
0x180006d9d  jz      loc_180006EB9
0x180006da3  mov     [rsp+90h+var_28], r14
0x180006da8  mov     ebx, r15d
0x180006dab  mov     r14d, r15d
0x180006dae  xor     edx, edx; Val
0x180006db0  mov     r8d, 418h; Size
0x180006db6  mov     rcx, rsi; void *
0x180006db9  call    memset_0
0x180006dbe  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180006dc2  lea     rax, [rbp+57h+var_4C]
0x180006dc6  mov     [rsp+90h+ResultLength], rax; ResultLength
0x180006dcb  mov     r9, rsi; KeyInformation
0x180006dce  xor     r8d, r8d; KeyInformationClass
0x180006dd1  mov     [rsp+90h+Length], 418h; Length
0x180006dd9  mov     edx, ebx; Index
0x180006ddb  call    cs:__imp_NtEnumerateKey
0x180006de1  lea     ebx, [r14+1]
0x180006de5  test    eax, eax
0x180006de7  js      short loc_180006DFF
0x180006de9  mov     rcx, [rbp+57h+KeyHandle]
0x180006ded  lea     rdx, [rsi+10h]
0x180006df1  lea     r8, [rbp+57h+Data]
0x180006df5  call    PerflibciBuildProvider
0x180006dfa  mov     r14d, ebx
0x180006dfd  jmp     short loc_180006DAE
0x180006dff  mov     r14, [rsp+90h+var_28]
0x180006e04  cmp     eax, 8000001Ah
0x180006e09  jnz     short loc_180006E10
0x180006e0b  mov     ebx, r15d
0x180006e0e  jmp     short loc_180006E1A
0x180006e10  mov     ecx, eax; Status
0x180006e12  call    cs:__imp_RtlNtStatusToDosError
0x180006e18  mov     ebx, eax
0x180006e1a  mov     rcx, rsi; Block
0x180006e1d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006e22  mov     rcx, [rbp+57h+KeyHandle]
0x180006e26  call    PerflibciCloseKey
0x180006e2b  test    ebx, ebx
0x180006e2d  jnz     loc_180006ECE
0x180006e33  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180006e37  mov     cs:?g_LastRefreshTime@@3_KA, rax; unsigned __int64 g_LastRefreshTime
0x180006e3e  test    dil, dil
0x180006e41  jz      loc_180006EEC
0x180006e47  mov     ecx, [rbp+57h+arg_18]
0x180006e4a  cmp     dword ptr [rbp+57h+var_50], ecx
0x180006e4d  cmova   ecx, dword ptr [rbp+57h+var_50]
0x180006e51  cmp     ecx, [rbp+57h+Data]
0x180006e54  jz      loc_180006EDA
0x180006e5a  mov     rcx, [rbp+57h+hKey]; hKey
0x180006e5e  lea     rax, [rbp+57h+Data]
0x180006e62  mov     dword ptr [rsp+90h+ResultLength], 4; cbData
0x180006e6a  lea     rdx, ?LastCounter@@3QBGB; "Last Counter"
0x180006e71  mov     r9d, 4; dwType
0x180006e77  mov     qword ptr [rsp+90h+Length], rax; lpData
0x180006e7c  xor     r8d, r8d; Reserved
0x180006e7f  call    cs:__imp_RegSetValueExW
0x180006e85  test    eax, eax
0x180006e87  jnz     short loc_180006EDA
0x180006e89  inc     [rbp+57h+Data]
0x180006e8c  lea     rax, [rbp+57h+Data]
0x180006e90  mov     rcx, [rbp+57h+hKey]; hKey
0x180006e94  lea     rdx, ?LastHelp@@3QBGB; "Last Help"
0x180006e9b  mov     dword ptr [rsp+90h+ResultLength], 4; cbData
0x180006ea3  mov     r9d, 4; dwType
0x180006ea9  xor     r8d, r8d; Reserved
0x180006eac  mov     qword ptr [rsp+90h+Length], rax; lpData
0x180006eb1  call    cs:__imp_RegSetValueExW
0x180006eb7  jmp     short loc_180006EDA
0x180006eb9  mov     rcx, [rbp+57h+KeyHandle]
0x180006ebd  mov     ebx, 0Eh
0x180006ec2  call    PerflibciCloseKey
0x180006ec7  jmp     short loc_180006ECE
0x180006ec9  mov     ebx, 0Dh
0x180006ece  mov     cl, 1
0x180006ed0  call    PerflibciSetObjectsValidityState
0x180006ed5  test    dil, dil
0x180006ed8  jz      short loc_180006EEC
0x180006eda  mov     rcx, cs:hMutex; hMutex
0x180006ee1  call    cs:__imp_ReleaseMutex
0x180006ee7  jmp     short loc_180006EEC
0x180006ee9  mov     ebx, r15d
0x180006eec  mov     rcx, cs:?g_hGlobalMutex@@3PEAXEA; void *
0x180006ef3  call    ?PerflibciLocalReleaseMutex@@YAKPEAX@Z; PerflibciLocalReleaseMutex(void *)
0x180006ef8  mov     rcx, [rbp+57h+hKey]
0x180006efc  mov     rdi, [rsp+90h+var_20]
0x180006f01  mov     rsi, [rsp+90h+var_18]
0x180006f06  lea     rax, [rcx-1]
0x180006f0a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006f0e  ja      short loc_180006F15
0x180006f10  call    PerflibciCloseKey
0x180006f15  mov     eax, ebx
0x180006f17  mov     rbx, [rsp+90h+var_10]
0x180006f1f  jmp     short loc_180006F26
0x180006f21  mov     eax, 57h ; 'W'
0x180006f26  add     rsp, 88h
0x180006f2d  pop     r15
0x180006f2f  pop     rbp
0x180006f30  retn
```
