# CShareInfo::InitInstance(void)

- ea: `0x1800115cc`
- end: `0x180011782`
- name: `?InitInstance@CShareInfo@@QEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(CShareInfo *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180010fa0`
- `0x180011480`
- `0x18002ad40`
- `0x180061b1c`
- `0x180062a2c`
- `0x18006337c`

## callees

- `0x1800115cc`
- `0x1800259bc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180011753`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180011753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011717`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011717`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001176a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001176a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001168e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001168e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800116b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011746`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800116b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011746`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116c8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800116eb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800116eb`

## string_xrefs

- `0x180011610`: `System\CurrentControlSet\Services\LanmanServer\DefaultSecurity`

## pseudocode

```c
__int64 __fastcall CShareInfo::InitInstance(CShareInfo *this)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  HLOCAL v5; // rdi
  int v6; // ebp
  __int64 v7; // r14
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    v3 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    *((_QWORD *)this + 3) = v3;
    if ( v3 )
    {
      v3[7] = 0;
      v4 = (_QWORD *)*((_QWORD *)this + 3);
      cbData = 0;
      hKey = 0;
      v5 = 0;
      v6 = 0;
      *v4 = 0;
      *(_DWORD *)(*((_QWORD *)this + 3) + 8LL) = 0;
      *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 3) + 24LL) = 9;
      *(_DWORD *)(*((_QWORD *)this + 3) + 28LL) = -1;
      *(_QWORD *)(*((_QWORD *)this + 3) + 40LL) = 0;
      *(_QWORD *)(*((_QWORD *)this + 3) + 48LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 3) + 64LL) = 0;
      v7 = *((_QWORD *)this + 3);
      *(_QWORD *)(v7 + 72) = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"System\\CurrentControlSet\\Services\\LanmanServer\\DefaultSecurity",
              0,
              0x80000000,
              &hKey) )
      {
        if ( !RegQueryValueExW(hKey, L"SrvsvcDefaultShareInfo", 0, 0, 0, &cbData) )
        {
          v5 = LocalAlloc(0x40u, cbData);
          if ( v5 )
          {
            if ( RegQueryValueExW(hKey, L"SrvsvcDefaultShareInfo", 0, 0, (LPBYTE)v5, &cbData)
              || !IsValidSecurityDescriptor(v5) )
            {
              LocalFree(v5);
              v5 = 0;
            }
            else
            {
              v6 = 1;
            }
          }
        }
        RegCloseKey(hKey);
      }
      *(_QWORD *)(v7 + 72) = v5;
      if ( !v6
        && !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:(A;;GRGX;;;WD)",
              1u,
              (PSECURITY_DESCRIPTOR *)(*((_QWORD *)this + 3) + 72LL),
              0) )
      {
        return (unsigned int)-2147024891;
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800115cc  mov     [rsp+arg_10], rbx
0x1800115d1  push    rbp
0x1800115d2  push    rsi
0x1800115d3  push    rdi
0x1800115d4  push    r14
0x1800115d6  push    r15
0x1800115d8  sub     rsp, 30h
0x1800115dc  xor     r15d, r15d
0x1800115df  mov     rsi, rcx
0x1800115e2  mov     ebx, r15d
0x1800115e5  cmp     [rcx+10h], r15d
0x1800115e9  jz      loc_1800116FB
0x1800115ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800115f6  lea     ecx, [r15+50h]; unsigned __int64
0x1800115fa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800115ff  mov     [rsi+18h], rax
0x180011603  test    rax, rax
0x180011606  jz      loc_180011778
0x18001160c  mov     [rax+38h], r15
0x180011610  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\La"...
0x180011617  mov     rax, [rsi+18h]
0x18001161b  mov     r9d, 80000000h; samDesired
0x180011621  xor     r8d, r8d; ulOptions
0x180011624  mov     [rsp+58h+cbData], r15d
0x180011629  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011630  mov     [rsp+58h+hKey], r15
0x180011635  mov     edi, r15d
0x180011638  mov     ebp, r15d
0x18001163b  mov     [rax], r15
0x18001163e  mov     rax, [rsi+18h]
0x180011642  mov     [rax+8], r15d
0x180011646  mov     rax, [rsi+18h]
0x18001164a  mov     [rax+10h], r15
0x18001164e  mov     rax, [rsi+18h]
0x180011652  mov     dword ptr [rax+18h], 9
0x180011659  mov     rax, [rsi+18h]
0x18001165d  mov     dword ptr [rax+1Ch], 0FFFFFFFFh
0x180011664  mov     rax, [rsi+18h]
0x180011668  mov     [rax+28h], r15
0x18001166c  mov     rax, [rsi+18h]
0x180011670  mov     [rax+30h], r15
0x180011674  mov     rax, [rsi+18h]
0x180011678  mov     [rax+40h], r15d
0x18001167c  lea     rax, [rsp+58h+hKey]
0x180011681  mov     r14, [rsi+18h]
0x180011685  mov     [rsp+58h+phkResult], rax; phkResult
0x18001168a  mov     [r14+48h], r15
0x18001168e  call    cs:__imp_RegOpenKeyExW
0x180011694  test    eax, eax
0x180011696  jnz     short loc_1800116CE
0x180011698  mov     rcx, [rsp+58h+hKey]; hKey
0x18001169d  lea     rax, [rsp+58h+cbData]
0x1800116a2  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800116a7  lea     rdx, ValueName; "SrvsvcDefaultShareInfo"
0x1800116ae  xor     r9d, r9d; lpType
0x1800116b1  mov     [rsp+58h+phkResult], r15; lpData
0x1800116b6  xor     r8d, r8d; lpReserved
0x1800116b9  call    cs:__imp_RegQueryValueExW
0x1800116bf  test    eax, eax
0x1800116c1  jz      short loc_18001170E
0x1800116c3  mov     rcx, [rsp+58h+hKey]; hKey
0x1800116c8  call    cs:__imp_RegCloseKey
0x1800116ce  mov     [r14+48h], rdi
0x1800116d2  test    ebp, ebp
0x1800116d4  jnz     short loc_1800116FB
0x1800116d6  mov     r8, [rsi+18h]
0x1800116da  lea     edx, [rbp+1]; StringSDRevision
0x1800116dd  add     r8, 48h ; 'H'; SecurityDescriptor
0x1800116e1  lea     rcx, ?c_szReadonlyShareSD@@3QBGB; "D:(A;;GRGX;;;WD)"
0x1800116e8  xor     r9d, r9d; SecurityDescriptorSize
0x1800116eb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800116f1  test    eax, eax
0x1800116f3  mov     ecx, 80070005h
0x1800116f8  cmovz   ebx, ecx
0x1800116fb  mov     eax, ebx
0x1800116fd  mov     rbx, [rsp+58h+arg_10]
0x180011702  add     rsp, 30h
0x180011706  pop     r15
0x180011708  pop     r14
0x18001170a  pop     rdi
0x18001170b  pop     rsi
0x18001170c  pop     rbp
0x18001170d  retn
0x18001170e  mov     edx, [rsp+58h+cbData]; uBytes
0x180011712  mov     ecx, 40h ; '@'; uFlags
0x180011717  call    cs:__imp_LocalAlloc
0x18001171d  mov     rdi, rax
0x180011720  test    rax, rax
0x180011723  jz      short loc_1800116C3
0x180011725  mov     rcx, [rsp+58h+hKey]; hKey
0x18001172a  lea     rax, [rsp+58h+cbData]
0x18001172f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180011734  lea     rdx, ValueName; "SrvsvcDefaultShareInfo"
0x18001173b  xor     r9d, r9d; lpType
0x18001173e  mov     [rsp+58h+phkResult], rdi; lpData
0x180011743  xor     r8d, r8d; lpReserved
0x180011746  call    cs:__imp_RegQueryValueExW
0x18001174c  test    eax, eax
0x18001174e  jnz     short loc_180011767
0x180011750  mov     rcx, rdi; pSecurityDescriptor
0x180011753  call    cs:__imp_IsValidSecurityDescriptor
0x180011759  test    eax, eax
0x18001175b  jz      short loc_180011767
0x18001175d  mov     ebp, 1
0x180011762  jmp     loc_1800116C3
0x180011767  mov     rcx, rdi; hMem
0x18001176a  call    cs:__imp_LocalFree
0x180011770  mov     rdi, r15
0x180011773  jmp     loc_1800116C3
0x180011778  mov     ebx, 8007000Eh
0x18001177d  jmp     loc_1800116FB
```
