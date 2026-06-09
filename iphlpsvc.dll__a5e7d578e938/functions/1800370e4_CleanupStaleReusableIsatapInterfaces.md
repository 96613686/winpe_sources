# CleanupStaleReusableIsatapInterfaces

- ea: `0x1800370e4`
- end: `0x180037318`
- name: `CleanupStaleReusableIsatapInterfaces`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180041be0`

## callees

- `0x18000d7c0`
- `0x180022b40`
- `0x1800370e4`
- `0x18004b5f0`
- `0x180052780`
- `0x1800591f0`
- `0x18005b4c8`
- `0x180076cf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037297`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800372d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037297`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800372d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800371ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003725e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800371ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003725e`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180037238`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180037238`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037179`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037179`

## string_xrefs

- `0x180037160`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x180037191`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x1800372f1`: `onecoreuap\net\netio\iphlpsvc\service\isatap.c`
- `0x1800371de`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\Isatap`

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
  __int64 v7; // r14
  __int64 v8; // rsi
  int v9; // ebx
  __int64 v10; // [rsp+28h] [rbp-61h]
  HKEY hKey; // [rsp+40h] [rbp-49h] BYREF
  int v12; // [rsp+48h] [rbp-41h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-39h] BYREF
  __int64 v14; // [rsp+58h] [rbp-31h] BYREF
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
        DeleteStaleUnattachedInterfaces(hKey, v7);
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
0x1800370e4  push    rbp
0x1800370e6  push    rbx
0x1800370e7  push    rsi
0x1800370e8  push    rdi
0x1800370e9  push    r14
0x1800370eb  lea     rbp, [rsp-37h]
0x1800370f0  sub     rsp, 0C0h
0x1800370f7  mov     rax, cs:__security_cookie
0x1800370fe  xor     rax, rsp
0x180037101  mov     [rbp+57h+var_30], rax
0x180037105  xor     ecx, ecx; Time
0x180037107  mov     [rbp+57h+var_90], 0
0x18003710f  mov     [rbp+57h+hKey], 0
0x180037117  mov     [rbp+57h+var_88], 0
0x18003711f  mov     [rbp+57h+var_98], 8
0x180037126  call    time
0x18003712b  cmp     cs:g_StopServiceEventSet, 0
0x180037132  mov     r14, rax
0x180037135  jnz     loc_1800372FD
0x18003713b  mov     rdi, cs:g_IsatapLock
0x180037142  lea     rax, aCleanupstalere; "CleanupStaleReusableIsatapInterfaces"
0x180037149  mov     esi, 800000h
0x18003714e  mov     dword ptr [rsp+0E0h+var_B8], 101Bh
0x180037156  mov     r8, rdi
0x180037159  mov     [rsp+0E0h+phkResult], rax
0x18003715e  mov     ecx, esi
0x180037160  lea     r9, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180037167  lea     rdx, aGetLockPInvoke; "Get lock (%p) invoked at %S : %S : %u"
0x18003716e  call    EventWrite0
0x180037173  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037176  mov     rcx, rdi; hHandle
0x180037179  call    cs:__imp_WaitForSingleObject
0x180037180  nop     dword ptr [rax+rax+00h]
0x180037185  lea     rdx, aLockPAcquiredA; "Lock (%p) acquired at %S : %S : %u. Ret"...
0x18003718c  mov     r8, rdi
0x18003718f  mov     ebx, eax
0x180037191  lea     r9, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180037198  lea     rax, aLockPFailedAtS; "Lock (%p) failed at %S : %S : %u. Retur"...
0x18003719f  mov     [rsp+0E0h+var_B0], ebx
0x1800371a3  test    ebx, ebx
0x1800371a5  mov     dword ptr [rsp+0E0h+var_B8], 101Bh
0x1800371ad  mov     ecx, esi
0x1800371af  cmovnz  rdx, rax
0x1800371b3  lea     rax, aCleanupstalere; "CleanupStaleReusableIsatapInterfaces"
0x1800371ba  mov     [rsp+0E0h+phkResult], rax
0x1800371bf  call    EventWrite0
0x1800371c4  test    ebx, ebx
0x1800371c6  jnz     loc_1800372FD
0x1800371cc  lea     rax, [rbp+57h+hKey]
0x1800371d0  mov     r9d, 20019h; samDesired
0x1800371d6  xor     r8d, r8d; ulOptions
0x1800371d9  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800371de  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\IP"...
0x1800371e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800371ec  call    cs:__imp_RegOpenKeyExW
0x1800371f3  nop     dword ptr [rax+rax+00h]
0x1800371f8  test    eax, eax
0x1800371fa  jnz     loc_1800372DD
0x180037200  mov     rdi, cs:qword_1800CA958
0x180037207  add     r14, 0FFFFFFFFFFD87300h
0x18003720e  test    rdi, rdi
0x180037211  jz      loc_1800372C1
0x180037217  cmp     dword ptr [rdi+0A74h], 0
0x18003721e  mov     rsi, [rdi]
0x180037221  jle     loc_1800372B5
0x180037227  lea     rcx, [rdi+0A20h]
0x18003722e  mov     r8d, 27h ; '''
0x180037234  lea     rdx, [rbp+57h+SubKey]
0x180037238  call    cs:__imp_ConvertGuidToStringW
0x18003723f  nop     dword ptr [rax+rax+00h]
0x180037244  mov     rcx, [rbp+57h+hKey]; hKey
0x180037248  lea     rax, [rbp+57h+var_90]
0x18003724c  mov     r9d, 20019h; samDesired
0x180037252  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180037257  xor     r8d, r8d; ulOptions
0x18003725a  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18003725e  call    cs:__imp_RegOpenKeyExW
0x180037265  nop     dword ptr [rax+rax+00h]
0x18003726a  test    eax, eax
0x18003726c  jnz     short loc_1800372B5
0x18003726e  mov     rcx, [rbp+57h+var_90]
0x180037272  lea     rax, [rbp+57h+var_98]
0x180037276  lea     r9, [rbp+57h+var_88]
0x18003727a  mov     [rsp+0E0h+phkResult], rax
0x18003727f  mov     r8d, 0Bh
0x180037285  lea     rdx, aDefuncttimesta; "DefunctTimestamp"
0x18003728c  call    QueryRegistryValueWithType
0x180037291  mov     rcx, [rbp+57h+var_90]; hKey
0x180037295  mov     ebx, eax
0x180037297  call    cs:__imp_RegCloseKey
0x18003729e  nop     dword ptr [rax+rax+00h]
0x1800372a3  test    ebx, ebx
0x1800372a5  jnz     short loc_1800372B5
0x1800372a7  cmp     [rbp+57h+var_88], r14
0x1800372ab  jge     short loc_1800372B5
0x1800372ad  mov     rcx, rdi
0x1800372b0  call    DeleteIsatapInterface
0x1800372b5  mov     rdi, rsi
0x1800372b8  test    rsi, rsi
0x1800372bb  jnz     loc_180037217
0x1800372c1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800372c5  mov     rdx, r14
0x1800372c8  call    DeleteStaleUnattachedInterfaces
0x1800372cd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800372d1  call    cs:__imp_RegCloseKey
0x1800372d8  nop     dword ptr [rax+rax+00h]
0x1800372dd  mov     r9, cs:g_IsatapLock
0x1800372e4  lea     rdx, aCleanupstalere; "CleanupStaleReusableIsatapInterfaces"
0x1800372eb  mov     r8d, 105Bh
0x1800372f1  lea     rcx, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800372f8  call    ReleaseAndTraceLock
0x1800372fd  mov     rcx, [rbp+57h+var_30]
0x180037301  xor     rcx, rsp; StackCookie
0x180037304  call    __security_check_cookie
0x180037309  add     rsp, 0C0h
0x180037310  pop     r14
0x180037312  pop     rdi
0x180037313  pop     rsi
0x180037314  pop     rbx
0x180037315  pop     rbp
0x180037316  retn
```
