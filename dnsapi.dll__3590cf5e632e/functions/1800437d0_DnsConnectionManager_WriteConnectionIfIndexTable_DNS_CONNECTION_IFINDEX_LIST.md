# DnsConnectionManager::WriteConnectionIfIndexTable(_DNS_CONNECTION_IFINDEX_LIST *)

- ea: `0x1800437d0`
- end: `0x180043b51`
- name: `?WriteConnectionIfIndexTable@DnsConnectionManager@@AEAAJPEAU_DNS_CONNECTION_IFINDEX_LIST@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(DnsConnectionManager *__hidden this, struct _DNS_CONNECTION_IFINDEX_LIST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180041cd8`

## callees

- `0x180001780`
- `0x18004148c`
- `0x180041e00`
- `0x1800437d0`
- `0x1800577b4`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004397d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004397d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043aee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043a1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043a5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043a1f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043a5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800438e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800439c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800438e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800439c2`

## string_xrefs

- `0x18004388f`: `Dnscache`
- `0x180043888`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::WriteConnectionIfIndexTable(
        DnsConnectionManager *this,
        struct _DNS_CONNECTION_IFINDEX_LIST *a2)
{
  signed int PersistedRegistryLocation; // ebx
  LSTATUS v5; // eax
  unsigned int v6; // esi
  DNS_CONNECTION_IFINDEX_ENTRY *pConnectionIfIndexEntries; // r15
  __int64 v8; // r14
  DWORD *p_dwIfIndex; // r12
  LSTATUS v10; // eax
  const BYTE *pwszConnectionName; // rcx
  __int64 v12; // rax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  lpSubKey[0] = &word_1800F66E0;
  lpSubKey[1] = 0;
  phkResult = 0;
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qq(1035, 66, (unsigned int)WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (_DWORD)this, (__int64)a2);
  if ( a2 )
  {
    PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                  (unsigned int)L"Dnscache",
                                  (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                  (unsigned int)L"Parameters\\DnsActiveIfs",
                                  (unsigned int)SubKey,
                                  520);
    if ( PersistedRegistryLocation >= 0 )
    {
      v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
      PersistedRegistryLocation = v5;
      if ( v5 > 0 )
        PersistedRegistryLocation = (unsigned __int16)v5 | 0x80070000;
      if ( PersistedRegistryLocation >= 0 )
      {
        v6 = 0;
        if ( !a2->nEntries )
          goto LABEL_30;
        while ( 1 )
        {
          pConnectionIfIndexEntries = a2->pConnectionIfIndexEntries;
          v8 = v6;
          p_dwIfIndex = &a2->pConnectionIfIndexEntries[v8].dwIfIndex;
          PersistedRegistryLocation = CWxString::Format(
                                        (CWxString *)lpSubKey,
                                        L"%s_%u",
                                        a2->pConnectionIfIndexEntries[v8].pwszConnectionName,
                                        *p_dwIfIndex);
          if ( PersistedRegistryLocation < 0 )
            break;
          if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_S(1054, 67, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, lpSubKey[0]);
          if ( hKey )
          {
            RegCloseKey(hKey);
            hKey = 0;
          }
          v10 = RegCreateKeyExW(phkResult, lpSubKey[0], 0, 0, 1u, 0x2001Fu, 0, &hKey, 0);
          PersistedRegistryLocation = v10;
          if ( v10 > 0 )
            PersistedRegistryLocation = (unsigned __int16)v10 | 0x80070000;
          if ( PersistedRegistryLocation < 0 )
            break;
          pwszConnectionName = (const BYTE *)pConnectionIfIndexEntries[v8].pwszConnectionName;
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&pwszConnectionName[2 * v12] );
          v13 = RegSetValueExW(hKey, L"Connection", 0, 1u, pwszConnectionName, 2 * v12 + 2);
          PersistedRegistryLocation = v13;
          if ( v13 > 0 )
            PersistedRegistryLocation = (unsigned __int16)v13 | 0x80070000;
          if ( PersistedRegistryLocation < 0 )
            break;
          v14 = RegSetValueExW(hKey, L"ActiveInterfaces", 0, 4u, (const BYTE *)p_dwIfIndex, 4u);
          PersistedRegistryLocation = v14;
          if ( v14 > 0 )
            PersistedRegistryLocation = (unsigned __int16)v14 | 0x80070000;
          if ( PersistedRegistryLocation < 0 )
            break;
          if ( ++v6 >= a2->nEntries )
            goto LABEL_30;
        }
      }
    }
  }
  else
  {
    PersistedRegistryLocation = -2147024809;
  }
  if ( hKey )
    DnsConnectionManager::DeleteConnectionIfIndexTable(this);
LABEL_30:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 68, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (unsigned int)PersistedRegistryLocation);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  CWxString::_Release((CWxString *)lpSubKey);
  return (unsigned int)PersistedRegistryLocation;
}

```

## disassembly

```asm
0x1800437d0  mov     [rsp-8+arg_10], rbx
0x1800437d5  push    rbp
0x1800437d6  push    rsi
0x1800437d7  push    rdi
0x1800437d8  push    r12
0x1800437da  push    r13
0x1800437dc  push    r14
0x1800437de  push    r15
0x1800437e0  lea     rbp, [rsp-1A0h]
0x1800437e8  sub     rsp, 2A0h
0x1800437ef  mov     rax, cs:__security_cookie
0x1800437f6  xor     rax, rsp
0x1800437f9  mov     [rbp+1D0h+var_40], rax
0x180043800  xor     r14d, r14d
0x180043803  lea     rax, word_1800F66E0
0x18004380a  mov     rdi, rdx
0x18004380d  mov     [rsp+2D0h+var_27C], r14d
0x180043812  mov     r13, rcx
0x180043815  mov     [rsp+2D0h+lpSubKey], rax
0x18004381a  mov     ebx, 208h
0x18004381f  mov     [rsp+2D0h+var_260], r14
0x180043824  mov     r8d, ebx; Size
0x180043827  mov     [rsp+2D0h+var_270], r14
0x18004382c  xor     edx, edx; Val
0x18004382e  mov     [rsp+2D0h+hKey], r14
0x180043833  lea     rcx, [rbp+1D0h+SubKey]; void *
0x180043837  call    memset_0
0x18004383c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180043843  jz      short loc_180043862
0x180043845  lea     edx, [r14+42h]
0x180043849  mov     qword ptr [rsp+2D0h+dwOptions], rdi
0x18004384e  mov     ecx, 40Bh
0x180043853  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x18004385a  mov     r9, r13
0x18004385d  call    WPP_SF_qq
0x180043862  test    rdi, rdi
0x180043865  jnz     short loc_180043879
0x180043867  mov     ebx, 80070057h
0x18004386c  mov     [rsp+2D0h+var_27C], 5ECh
0x180043874  jmp     loc_180043AB3
0x180043879  lea     r9, [rbp+1D0h+SubKey]
0x18004387d  mov     [rsp+2D0h+dwOptions], ebx
0x180043881  lea     r8, aParametersDnsa; "Parameters\\DnsActiveIfs"
0x180043888  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18004388f  lea     rcx, aDnscache_1; "Dnscache"
0x180043896  call    WxGetPersistedRegistryLocation
0x18004389b  mov     ebx, eax
0x18004389d  test    eax, eax
0x18004389f  jns     short loc_1800438AE
0x1800438a1  mov     [rsp+2D0h+var_27C], 5F6h
0x1800438a9  jmp     loc_180043AB3
0x1800438ae  mov     [rsp+2D0h+lpdwDisposition], r14; lpdwDisposition
0x1800438b3  lea     rax, [rsp+2D0h+var_270]
0x1800438b8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800438bd  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800438c1  mov     [rsp+2D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800438c6  xor     r9d, r9d; lpClass
0x1800438c9  mov     [rsp+2D0h+samDesired], 2001Fh; samDesired
0x1800438d1  xor     r8d, r8d; Reserved
0x1800438d4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800438db  mov     [rsp+2D0h+dwOptions], r14d; dwOptions
0x1800438e0  call    cs:__imp_RegCreateKeyExW
0x1800438e7  nop     dword ptr [rax+rax+00h]
0x1800438ec  mov     ebx, eax
0x1800438ee  test    eax, eax
0x1800438f0  jle     short loc_1800438FB
0x1800438f2  movzx   ebx, ax
0x1800438f5  or      ebx, 80070000h
0x1800438fb  test    ebx, ebx
0x1800438fd  jns     short loc_18004390C
0x1800438ff  mov     [rsp+2D0h+var_27C], 600h
0x180043907  jmp     loc_180043AB3
0x18004390c  mov     esi, r14d
0x18004390f  cmp     [rdi+8], r14d
0x180043913  jbe     loc_180043AC2
0x180043919  mov     r15, [rdi]
0x18004391c  lea     rdx, aSU; "%s_%u"
0x180043923  mov     r14d, esi
0x180043926  lea     rcx, [rsp+2D0h+lpSubKey]; this
0x18004392b  shl     r14, 4
0x18004392f  lea     r12, [r15+8]
0x180043933  add     r12, r14
0x180043936  mov     r8, [r14+r15]
0x18004393a  mov     r9d, [r12]
0x18004393e  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x180043943  mov     ebx, eax
0x180043945  test    eax, eax
0x180043947  js      loc_180043AA8
0x18004394d  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x180043954  jz      short loc_180043971
0x180043956  mov     r9, [rsp+2D0h+lpSubKey]
0x18004395b  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x180043962  mov     edx, 43h ; 'C'
0x180043967  mov     ecx, 41Eh
0x18004396c  call    WPP_SF_S
0x180043971  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180043976  xor     ebx, ebx
0x180043978  test    rcx, rcx
0x18004397b  jz      short loc_18004398E
0x18004397d  call    cs:__imp_RegCloseKey
0x180043984  nop     dword ptr [rax+rax+00h]
0x180043989  mov     [rsp+2D0h+hKey], rbx
0x18004398e  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x180043993  lea     rax, [rsp+2D0h+hKey]
0x180043998  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18004399d  xor     r9d, r9d; lpClass
0x1800439a0  mov     [rsp+2D0h+lpdwDisposition], rbx; lpdwDisposition
0x1800439a5  xor     r8d, r8d; Reserved
0x1800439a8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800439ad  mov     [rsp+2D0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800439b2  mov     [rsp+2D0h+samDesired], 2001Fh; samDesired
0x1800439ba  mov     [rsp+2D0h+dwOptions], 1; dwOptions
0x1800439c2  call    cs:__imp_RegCreateKeyExW
0x1800439c9  nop     dword ptr [rax+rax+00h]
0x1800439ce  mov     ebx, eax
0x1800439d0  test    eax, eax
0x1800439d2  jle     short loc_1800439DD
0x1800439d4  movzx   ebx, ax
0x1800439d7  or      ebx, 80070000h
0x1800439dd  test    ebx, ebx
0x1800439df  js      loc_180043A9E
0x1800439e5  mov     rcx, [r14+r15]
0x1800439e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800439ed  xor     r14d, r14d
0x1800439f0  inc     rax
0x1800439f3  cmp     [rcx+rax*2], r14w
0x1800439f8  jnz     short loc_1800439F0
0x1800439fa  lea     eax, ds:2[rax*2]
0x180043a01  mov     r9d, 1; dwType
0x180043a07  mov     [rsp+2D0h+samDesired], eax; cbData
0x180043a0b  lea     rdx, aConnection; "Connection"
0x180043a12  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x180043a17  xor     r8d, r8d; Reserved
0x180043a1a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180043a1f  call    cs:__imp_RegSetValueExW
0x180043a26  nop     dword ptr [rax+rax+00h]
0x180043a2b  mov     ebx, eax
0x180043a2d  test    eax, eax
0x180043a2f  jle     short loc_180043A3A
0x180043a31  movzx   ebx, ax
0x180043a34  or      ebx, 80070000h
0x180043a3a  test    ebx, ebx
0x180043a3c  js      short loc_180043A94
0x180043a3e  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180043a43  lea     rdx, aActiveinterfac; "ActiveInterfaces"
0x180043a4a  mov     eax, 4
0x180043a4f  xor     r8d, r8d; Reserved
0x180043a52  mov     [rsp+2D0h+samDesired], eax; cbData
0x180043a56  mov     r9d, eax; dwType
0x180043a59  mov     qword ptr [rsp+2D0h+dwOptions], r12; lpData
0x180043a5e  call    cs:__imp_RegSetValueExW
0x180043a65  nop     dword ptr [rax+rax+00h]
0x180043a6a  mov     ebx, eax
0x180043a6c  test    eax, eax
0x180043a6e  jle     short loc_180043A79
0x180043a70  movzx   ebx, ax
0x180043a73  or      ebx, 80070000h
0x180043a79  test    ebx, ebx
0x180043a7b  js      short loc_180043A8A
0x180043a7d  inc     esi
0x180043a7f  cmp     esi, [rdi+8]
0x180043a82  jb      loc_180043919
0x180043a88  jmp     short loc_180043AC2
0x180043a8a  mov     [rsp+2D0h+var_27C], 62Dh
0x180043a92  jmp     short loc_180043AB3
0x180043a94  mov     [rsp+2D0h+var_27C], 626h
0x180043a9c  jmp     short loc_180043AB3
0x180043a9e  mov     [rsp+2D0h+var_27C], 61Dh
0x180043aa6  jmp     short loc_180043AB0
0x180043aa8  mov     [rsp+2D0h+var_27C], 608h
0x180043ab0  xor     r14d, r14d
0x180043ab3  cmp     [rsp+2D0h+hKey], r14
0x180043ab8  jz      short loc_180043AC2
0x180043aba  mov     rcx, r13; this
0x180043abd  call    ?DeleteConnectionIfIndexTable@DnsConnectionManager@@AEAAJXZ; DnsConnectionManager::DeleteConnectionIfIndexTable(void)
0x180043ac2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180043ac9  jz      short loc_180043AE4
0x180043acb  mov     edx, 44h ; 'D'
0x180043ad0  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x180043ad7  mov     ecx, 40Bh
0x180043adc  mov     r9d, ebx
0x180043adf  call    WPP_SF_d
0x180043ae4  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180043ae9  test    rcx, rcx
0x180043aec  jz      short loc_180043AFF
0x180043aee  call    cs:__imp_RegCloseKey
0x180043af5  nop     dword ptr [rax+rax+00h]
0x180043afa  mov     [rsp+2D0h+hKey], r14
0x180043aff  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180043b04  test    rcx, rcx
0x180043b07  jz      short loc_180043B1A
0x180043b09  call    cs:__imp_RegCloseKey
0x180043b10  nop     dword ptr [rax+rax+00h]
0x180043b15  mov     [rsp+2D0h+var_270], r14
0x180043b1a  lea     rcx, [rsp+2D0h+lpSubKey]; this
0x180043b1f  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x180043b24  mov     eax, ebx
0x180043b26  mov     rcx, [rbp+1D0h+var_40]
0x180043b2d  xor     rcx, rsp; StackCookie
0x180043b30  call    __security_check_cookie
0x180043b35  mov     rbx, [rsp+2D0h+arg_10]
0x180043b3d  add     rsp, 2A0h
0x180043b44  pop     r15
0x180043b46  pop     r14
0x180043b48  pop     r13
0x180043b4a  pop     r12
0x180043b4c  pop     rdi
0x180043b4d  pop     rsi
0x180043b4e  pop     rbp
0x180043b4f  retn
```
