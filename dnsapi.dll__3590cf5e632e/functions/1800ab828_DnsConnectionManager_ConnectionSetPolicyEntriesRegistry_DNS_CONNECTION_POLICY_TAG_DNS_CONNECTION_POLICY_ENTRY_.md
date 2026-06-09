# DnsConnectionManager::ConnectionSetPolicyEntriesRegistry(DNS_CONNECTION_POLICY_TAG,_DNS_CONNECTION_POLICY_ENTRY_LIST *)

- ea: `0x1800ab828`
- end: `0x1800aba52`
- name: `?ConnectionSetPolicyEntriesRegistry@DnsConnectionManager@@QEAAJW4DNS_CONNECTION_POLICY_TAG@@PEAU_DNS_CONNECTION_POLICY_ENTRY_LIST@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(DnsConnectionManager *__hidden this, enum DNS_CONNECTION_POLICY_TAG, struct _DNS_CONNECTION_POLICY_ENTRY_LIST *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18008679c`

## callees

- `0x180001780`
- `0x18005a60c`
- `0x180065520`
- `0x180067dc4`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800ab350`
- `0x1800ab828`
- `0x1800abe50`
- `0x1800dc9e0`
- `0x1800e1720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aba22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aba22`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ab950`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ab950`

## string_xrefs

- `0x1800ab8f3`: `Dnscache`
- `0x1800ab8ec`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::ConnectionSetPolicyEntriesRegistry(
        DnsConnectionManager *this,
        __int32 a2,
        struct _DNS_CONNECTION_POLICY_ENTRY_LIST *a3)
{
  int PersistedRegistryLocation; // ebx
  LSTATUS v7; // eax
  DWORD i; // esi
  __int64 v9; // r15
  DnsConnectionManager *v11; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v12; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v11 = this;
  hKey = 0;
  v12 = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qdq(1035, 37, (unsigned int)WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (_DWORD)this, a2, (__int64)a3);
  if ( a3 )
  {
    AutoSrw::LockExclusive((AutoSrw *)&v11);
    PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                  (unsigned int)L"Dnscache",
                                  (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                  (unsigned int)L"Parameters\\DnsConnections",
                                  (unsigned int)SubKey,
                                  520);
    if ( PersistedRegistryLocation >= 0 )
    {
      v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
      PersistedRegistryLocation = v7;
      if ( v7 > 0 )
        PersistedRegistryLocation = (unsigned __int16)v7 | 0x80070000;
      if ( PersistedRegistryLocation >= 0 )
      {
        for ( i = 0; i < a3->nEntries; ++i )
        {
          v9 = i;
          PersistedRegistryLocation = DnsConnectionManager::WriteConnectionPolicyRule(
                                        this,
                                        hKey,
                                        a2,
                                        &a3->pPolicyEntries[v9]);
          if ( PersistedRegistryLocation < 0 )
            break;
          PersistedRegistryLocation = DnsConnectionManager::AddPolicyRule(
                                        this,
                                        (enum DNS_CONNECTION_POLICY_TAG)a2,
                                        &a3->pPolicyEntries[v9]);
          if ( PersistedRegistryLocation < 0 )
            break;
        }
      }
    }
  }
  else
  {
    PersistedRegistryLocation = -2147024809;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 38, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (unsigned int)PersistedRegistryLocation);
  if ( (_DWORD)v12 )
    AutoSrw::UnlockShared((AutoSrw *)&v11);
  if ( HIDWORD(v12) )
    AutoSrw::UnlockExclusive((AutoSrw *)&v11);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)PersistedRegistryLocation;
}

```

## disassembly

```asm
0x1800ab828  push    rbp
0x1800ab82a  push    rbx
0x1800ab82b  push    rsi
0x1800ab82c  push    rdi
0x1800ab82d  push    r12
0x1800ab82f  push    r14
0x1800ab831  push    r15
0x1800ab833  lea     rbp, [rsp-190h]
0x1800ab83b  sub     rsp, 290h
0x1800ab842  mov     rax, cs:__security_cookie
0x1800ab849  xor     rax, rsp
0x1800ab84c  mov     [rbp+1C0h+var_40], rax
0x1800ab853  mov     rdi, r8
0x1800ab856  mov     [rsp+2C0h+var_268], rcx
0x1800ab85b  mov     r12d, edx
0x1800ab85e  mov     [rsp+2C0h+var_26C], 0
0x1800ab866  mov     r14, rcx
0x1800ab869  mov     [rsp+2C0h+hKey], 0
0x1800ab872  mov     ebx, 208h
0x1800ab877  mov     [rsp+2C0h+var_260], 0
0x1800ab880  mov     r8d, ebx; Size
0x1800ab883  lea     rcx, [rsp+2C0h+SubKey]; void *
0x1800ab888  xor     edx, edx; Val
0x1800ab88a  call    memset_0
0x1800ab88f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800ab896  jz      short loc_1800AB8BB
0x1800ab898  mov     edx, 25h ; '%'
0x1800ab89d  mov     qword ptr [rsp+2C0h+samDesired], rdi
0x1800ab8a2  mov     ecx, 40Bh
0x1800ab8a7  mov     [rsp+2C0h+dwOptions], r12d
0x1800ab8ac  mov     r9, r14
0x1800ab8af  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ab8b6  call    WPP_SF_qdq
0x1800ab8bb  test    rdi, rdi
0x1800ab8be  jnz     short loc_1800AB8D2
0x1800ab8c0  mov     ebx, 80070057h
0x1800ab8c5  mov     [rsp+2C0h+var_26C], 2DBh
0x1800ab8cd  jmp     loc_1800AB9D4
0x1800ab8d2  lea     rcx, [rsp+2C0h+var_268]; this
0x1800ab8d7  call    ?LockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::LockExclusive(void)
0x1800ab8dc  lea     r9, [rsp+2C0h+SubKey]
0x1800ab8e1  mov     [rsp+2C0h+dwOptions], ebx
0x1800ab8e5  lea     r8, aParametersDnsc; "Parameters\\DnsConnections"
0x1800ab8ec  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800ab8f3  lea     rcx, aDnscache_1; "Dnscache"
0x1800ab8fa  call    WxGetPersistedRegistryLocation
0x1800ab8ff  mov     ebx, eax
0x1800ab901  test    eax, eax
0x1800ab903  jns     short loc_1800AB912
0x1800ab905  mov     [rsp+2C0h+var_26C], 2E3h
0x1800ab90d  jmp     loc_1800AB9D4
0x1800ab912  mov     [rsp+2C0h+lpdwDisposition], 0; lpdwDisposition
0x1800ab91b  lea     rax, [rsp+2C0h+hKey]
0x1800ab920  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800ab925  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x1800ab92a  mov     [rsp+2C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ab933  xor     r9d, r9d; lpClass
0x1800ab936  mov     [rsp+2C0h+samDesired], 2001Fh; samDesired
0x1800ab93e  xor     r8d, r8d; Reserved
0x1800ab941  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab948  mov     [rsp+2C0h+dwOptions], 0; dwOptions
0x1800ab950  call    cs:__imp_RegCreateKeyExW
0x1800ab957  nop     dword ptr [rax+rax+00h]
0x1800ab95c  mov     ebx, eax
0x1800ab95e  test    eax, eax
0x1800ab960  jle     short loc_1800AB96B
0x1800ab962  movzx   ebx, ax
0x1800ab965  or      ebx, 80070000h
0x1800ab96b  test    ebx, ebx
0x1800ab96d  jns     short loc_1800AB979
0x1800ab96f  mov     [rsp+2C0h+var_26C], 2EDh
0x1800ab977  jmp     short loc_1800AB9D4
0x1800ab979  xor     esi, esi
0x1800ab97b  cmp     [rdi+8], esi
0x1800ab97e  jbe     short loc_1800AB9D4
0x1800ab980  mov     r9, [rdi]
0x1800ab983  mov     r8d, r12d; unsigned int
0x1800ab986  mov     rdx, [rsp+2C0h+hKey]; HKEY
0x1800ab98b  mov     rcx, r14; this
0x1800ab98e  mov     eax, esi
0x1800ab990  imul    r15, rax, 38h ; '8'
0x1800ab994  add     r9, r15; struct _DNS_CONNECTION_POLICY_ENTRY *
0x1800ab997  call    ?WriteConnectionPolicyRule@DnsConnectionManager@@AEAAJPEAUHKEY__@@KPEAU_DNS_CONNECTION_POLICY_ENTRY@@@Z; DnsConnectionManager::WriteConnectionPolicyRule(HKEY__ *,ulong,_DNS_CONNECTION_POLICY_ENTRY *)
0x1800ab99c  mov     ebx, eax
0x1800ab99e  test    eax, eax
0x1800ab9a0  js      short loc_1800AB9CC
0x1800ab9a2  mov     r8, [rdi]
0x1800ab9a5  mov     edx, r12d; enum DNS_CONNECTION_POLICY_TAG
0x1800ab9a8  add     r8, r15; struct _DNS_CONNECTION_POLICY_ENTRY *
0x1800ab9ab  mov     rcx, r14; this
0x1800ab9ae  call    ?AddPolicyRule@DnsConnectionManager@@AEAAJW4DNS_CONNECTION_POLICY_TAG@@PEAU_DNS_CONNECTION_POLICY_ENTRY@@@Z; DnsConnectionManager::AddPolicyRule(DNS_CONNECTION_POLICY_TAG,_DNS_CONNECTION_POLICY_ENTRY *)
0x1800ab9b3  mov     ebx, eax
0x1800ab9b5  test    eax, eax
0x1800ab9b7  js      short loc_1800AB9C2
0x1800ab9b9  inc     esi
0x1800ab9bb  cmp     esi, [rdi+8]
0x1800ab9be  jb      short loc_1800AB980
0x1800ab9c0  jmp     short loc_1800AB9D4
0x1800ab9c2  mov     [rsp+2C0h+var_26C], 2F6h
0x1800ab9ca  jmp     short loc_1800AB9D4
0x1800ab9cc  mov     [rsp+2C0h+var_26C], 2F3h
0x1800ab9d4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800ab9db  jz      short loc_1800AB9F6
0x1800ab9dd  mov     edx, 26h ; '&'
0x1800ab9e2  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ab9e9  mov     ecx, 40Bh
0x1800ab9ee  mov     r9d, ebx
0x1800ab9f1  call    WPP_SF_d
0x1800ab9f6  cmp     dword ptr [rsp+2C0h+var_260], 0
0x1800ab9fb  jz      short loc_1800ABA07
0x1800ab9fd  lea     rcx, [rsp+2C0h+var_268]; this
0x1800aba02  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x1800aba07  cmp     dword ptr [rsp+2C0h+var_260+4], 0
0x1800aba0c  jz      short loc_1800ABA18
0x1800aba0e  lea     rcx, [rsp+2C0h+var_268]; this
0x1800aba13  call    ?UnlockExclusive@AutoSrw@@QEAAXXZ; AutoSrw::UnlockExclusive(void)
0x1800aba18  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800aba1d  test    rcx, rcx
0x1800aba20  jz      short loc_1800ABA2E
0x1800aba22  call    cs:__imp_RegCloseKey
0x1800aba29  nop     dword ptr [rax+rax+00h]
0x1800aba2e  mov     eax, ebx
0x1800aba30  mov     rcx, [rbp+1C0h+var_40]
0x1800aba37  xor     rcx, rsp; StackCookie
0x1800aba3a  call    __security_check_cookie
0x1800aba3f  add     rsp, 290h
0x1800aba46  pop     r15
0x1800aba48  pop     r14
0x1800aba4a  pop     r12
0x1800aba4c  pop     rdi
0x1800aba4d  pop     rsi
0x1800aba4e  pop     rbx
0x1800aba4f  pop     rbp
0x1800aba50  retn
```
