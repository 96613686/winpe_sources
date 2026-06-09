# CleanupStaleReusableIsatapInterfaces

- ea: `0x1800370d4`
- end: `0x180037308`
- name: `CleanupStaleReusableIsatapInterfaces`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180041c20`

## callees

- `0x18000d7b0`
- `0x180022b30`
- `0x1800370d4`
- `0x18004b630`
- `0x1800527c0`
- `0x1800591d0`
- `0x18005b4a8`
- `0x180076cd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037287`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800372c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037287`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800372c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800371dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003724e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800371dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003724e`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180037228`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180037228`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037169`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037169`

## string_xrefs

- `0x180037150`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180037181`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x1800372e1`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x1800371ce`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\Isatap`

## pseudocode

```c
time_t CleanupStaleReusableIsatapInterfaces()
{
  time_t result; // rax
  time_t v1; // r14
  HANDLE v2; // rdi
  DWORD v3; // eax
  const wchar_t *v4; // rdx
  DWORD v5; // ebx
  __int64 v6; // rdi
  time_t v7; // r14
  __int64 v8; // rsi
  int v9; // ebx
  __int64 v10; // [rsp+28h] [rbp-61h]
  HKEY hKey; // [rsp+40h] [rbp-49h] BYREF
  int v12; // [rsp+48h] [rbp-41h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-39h] BYREF
  time_t v14; // [rsp+58h] [rbp-31h] BYREF
  WCHAR SubKey[40]; // [rsp+60h] [rbp-29h] BYREF

  phkResult = 0;
  hKey = 0;
  v14 = 0;
  v12 = 8;
  result = time(0);
  v1 = result;
  if ( !g_StopServiceEventSet )
  {
    v2 = g_IsatapLock;
    EventWrite0(
      0x800000,
      L"Get lock (%p) invoked at %S : %S : %u",
      g_IsatapLock,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
      "CleanupStaleReusableIsatapInterfaces",
      4123);
    v3 = WaitForSingleObject(v2, 0xFFFFFFFF);
    v4 = L"Lock (%p) acquired at %S : %S : %u. Return %d";
    v5 = v3;
    LODWORD(v10) = 4123;
    if ( v3 )
      v4 = L"Lock (%p) failed at %S : %S : %u. Return %d";
    result = EventWrite0(
               0x800000,
               v4,
               v2,
               "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
               "CleanupStaleReusableIsatapInterfaces",
               v10,
               v3);
    if ( !v5 )
    {
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Parameters\\Isatap",
              0,
              0x20019u,
              &hKey) )
      {
        v6 = qword_1800CA958;
        v7 = v1 - 2592000;
        if ( qword_1800CA958 )
        {
          do
          {
            v8 = *(_QWORD *)v6;
            if ( *(int *)(v6 + 2676) > 0 )
            {
              ConvertGuidToStringW(v6 + 2592, SubKey, 39);
              if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
              {
                v9 = QueryRegistryValueWithType(phkResult, L"DefunctTimestamp", 11, &v14, &v12);
                RegCloseKey(phkResult);
                if ( !v9 && v14 < v7 )
                  DeleteIsatapInterface(v6);
              }
            }
            v6 = v8;
          }
          while ( v8 );
        }
        DeleteStaleUnattachedInterfaces(hKey);
        RegCloseKey(hKey);
      }
      return ReleaseAndTraceLock(
               "onecoreuap\\net\\netio\\iphlpsvc\\service\\isatap.c",
               "CleanupStaleReusableIsatapInterfaces",
               4187,
               g_IsatapLock);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800370d4  push    rbp
0x1800370d6  push    rbx
0x1800370d7  push    rsi
0x1800370d8  push    rdi
0x1800370d9  push    r14
0x1800370db  lea     rbp, [rsp-37h]
0x1800370e0  sub     rsp, 0C0h
0x1800370e7  mov     rax, cs:__security_cookie
0x1800370ee  xor     rax, rsp
0x1800370f1  mov     [rbp+57h+var_30], rax
0x1800370f5  xor     ecx, ecx; Time
0x1800370f7  mov     [rbp+57h+var_90], 0
0x1800370ff  mov     [rbp+57h+hKey], 0
0x180037107  mov     [rbp+57h+var_88], 0
0x18003710f  mov     [rbp+57h+var_98], 8
0x180037116  call    time
0x18003711b  cmp     cs:g_StopServiceEventSet, 0
0x180037122  mov     r14, rax
0x180037125  jnz     loc_1800372ED
0x18003712b  mov     rdi, cs:g_IsatapLock
0x180037132  lea     rax, aCleanupstalere; "CleanupStaleReusableIsatapInterfaces"
0x180037139  mov     esi, 800000h
0x18003713e  mov     dword ptr [rsp+0E0h+var_B8], 101Bh
0x180037146  mov     r8, rdi
0x180037149  mov     [rsp+0E0h+phkResult], rax
0x18003714e  mov     ecx, esi
0x180037150  lea     r9, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180037157  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18003715e  call    EventWrite0
0x180037163  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037166  mov     rcx, rdi; hHandle
0x180037169  call    cs:__imp_WaitForSingleObject
0x180037170  nop     dword ptr [rax+rax+00h]
0x180037175  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x18003717c  mov     r8, rdi
0x18003717f  mov     ebx, eax
0x180037181  lea     r9, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180037188  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x18003718f  mov     [rsp+0E0h+var_B0], ebx
0x180037193  test    ebx, ebx
0x180037195  mov     dword ptr [rsp+0E0h+var_B8], 101Bh
0x18003719d  mov     ecx, esi
0x18003719f  cmovnz  rdx, rax
0x1800371a3  lea     rax, aCleanupstalere; "CleanupStaleReusableIsatapInterfaces"
0x1800371aa  mov     [rsp+0E0h+phkResult], rax
0x1800371af  call    EventWrite0
0x1800371b4  test    ebx, ebx
0x1800371b6  jnz     loc_1800372ED
0x1800371bc  lea     rax, [rbp+57h+hKey]
0x1800371c0  mov     r9d, 20019h; samDesired
0x1800371c6  xor     r8d, r8d; ulOptions
0x1800371c9  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800371ce  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\IP"...
0x1800371d5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800371dc  call    cs:__imp_RegOpenKeyExW
0x1800371e3  nop     dword ptr [rax+rax+00h]
0x1800371e8  test    eax, eax
0x1800371ea  jnz     loc_1800372CD
0x1800371f0  mov     rdi, cs:qword_1800CA958
0x1800371f7  add     r14, 0FFFFFFFFFFD87300h
0x1800371fe  test    rdi, rdi
0x180037201  jz      loc_1800372B1
0x180037207  cmp     dword ptr [rdi+0A74h], 0
0x18003720e  mov     rsi, [rdi]
0x180037211  jle     loc_1800372A5
0x180037217  lea     rcx, [rdi+0A20h]
0x18003721e  mov     r8d, 27h ; '''
0x180037224  lea     rdx, [rbp+57h+SubKey]
0x180037228  call    cs:__imp_ConvertGuidToStringW
0x18003722f  nop     dword ptr [rax+rax+00h]
0x180037234  mov     rcx, [rbp+57h+hKey]; hKey
0x180037238  lea     rax, [rbp+57h+var_90]
0x18003723c  mov     r9d, 20019h; samDesired
0x180037242  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180037247  xor     r8d, r8d; ulOptions
0x18003724a  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003724e  call    cs:__imp_RegOpenKeyExW
0x180037255  nop     dword ptr [rax+rax+00h]
0x18003725a  test    eax, eax
0x18003725c  jnz     short loc_1800372A5
0x18003725e  mov     rcx, [rbp+57h+var_90]
0x180037262  lea     rax, [rbp+57h+var_98]
0x180037266  lea     r9, [rbp+57h+var_88]
0x18003726a  mov     [rsp+0E0h+phkResult], rax
0x18003726f  mov     r8d, 0Bh
0x180037275  lea     rdx, aDefuncttimesta; "DefunctTimestamp"
0x18003727c  call    QueryRegistryValueWithType
0x180037281  mov     rcx, [rbp+57h+var_90]; hKey
0x180037285  mov     ebx, eax
0x180037287  call    cs:__imp_RegCloseKey
0x18003728e  nop     dword ptr [rax+rax+00h]
0x180037293  test    ebx, ebx
0x180037295  jnz     short loc_1800372A5
0x180037297  cmp     [rbp+57h+var_88], r14
0x18003729b  jge     short loc_1800372A5
0x18003729d  mov     rcx, rdi
0x1800372a0  call    DeleteIsatapInterface
0x1800372a5  mov     rdi, rsi
0x1800372a8  test    rsi, rsi
0x1800372ab  jnz     loc_180037207
0x1800372b1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800372b5  mov     rdx, r14
0x1800372b8  call    DeleteStaleUnattachedInterfaces
0x1800372bd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800372c1  call    cs:__imp_RegCloseKey
0x1800372c8  nop     dword ptr [rax+rax+00h]
0x1800372cd  mov     r9, cs:g_IsatapLock
0x1800372d4  lea     rdx, aCleanupstalere; "CleanupStaleReusableIsatapInterfaces"
0x1800372db  mov     r8d, 105Bh
0x1800372e1  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800372e8  call    ReleaseAndTraceLock
0x1800372ed  mov     rcx, [rbp+57h+var_30]
0x1800372f1  xor     rcx, rsp; StackCookie
0x1800372f4  call    __security_check_cookie
0x1800372f9  add     rsp, 0C0h
0x180037300  pop     r14
0x180037302  pop     rdi
0x180037303  pop     rsi
0x180037304  pop     rbx
0x180037305  pop     rbp
0x180037306  retn
```
