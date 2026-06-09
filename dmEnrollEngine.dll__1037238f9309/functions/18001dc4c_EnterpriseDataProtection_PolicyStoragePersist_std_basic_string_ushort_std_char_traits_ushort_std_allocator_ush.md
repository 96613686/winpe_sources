# EnterpriseDataProtection::PolicyStoragePersist(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,bool)

- ea: `0x18001dc4c`
- end: `0x18001de11`
- name: `?PolicyStoragePersist@EnterpriseDataProtection@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N1@Z`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18006d75c`

## callees

- `0x18000e0d0`
- `0x18001dc4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dd49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dd85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ddc3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dd49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001dd85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001ddc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dcc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dcc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dd00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dde9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ddfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dd00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dde9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ddfc`

## pseudocode

```c
__int64 __fastcall EnterpriseDataProtection::PolicyStoragePersist(
        __int64 a1,
        const WCHAR *a2,
        __int64 *a3,
        unsigned __int8 a4,
        unsigned __int8 a5)
{
  int v6; // r14d
  int v8; // esi
  HKEY v9; // rcx
  bool v11; // cc
  LSTATUS v12; // eax
  signed int v13; // ebx
  HKEY v14; // rcx
  HKEY v15; // rcx
  __int64 v16; // rax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  HKEY v20; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  __int64 Data; // [rsp+80h] [rbp+38h] BYREF

  Data = a1;
  v6 = a4;
  hKey = 0;
  v8 = EEDBManager::OpenEnrollmentsHKEY(0x2001Fu, &hKey);
  if ( v8 < 0 )
  {
    v9 = hKey;
    hKey = 0;
    if ( v9 )
      RegCloseKey(v9);
    return (unsigned int)v8;
  }
  v11 = *((_QWORD *)a2 + 3) <= 7u;
  phkResult = 0;
  if ( !v11 )
    a2 = *(const WCHAR **)a2;
  v12 = RegOpenKeyExW(hKey, a2, 0, 0x2001Fu, &phkResult);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
  {
    v14 = phkResult;
LABEL_11:
    phkResult = 0;
LABEL_12:
    if ( v14 )
      RegCloseKey(v14);
    v15 = hKey;
    hKey = 0;
    if ( v15 )
      RegCloseKey(v15);
    return (unsigned int)v13;
  }
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 *)*a3;
  v16 = -1;
  do
    ++v16;
  while ( *((_WORD *)a3 + v16) );
  v17 = RegSetValueExW(phkResult, L"EnterpriseDataProtectionIdsToRevoke", 0, 1u, (const BYTE *)a3, 2 * v16 + 2);
  v13 = v17;
  if ( v17 > 0 )
    v13 = (unsigned __int16)v17 | 0x80070000;
  v14 = phkResult;
  if ( v13 < 0 )
    goto LABEL_11;
  LODWORD(Data) = v6;
  v18 = RegSetValueExW(phkResult, L"RevokeOnUnenroll", 0, 4u, (const BYTE *)&Data, 4u);
  v13 = v18;
  if ( v18 > 0 )
    v13 = (unsigned __int16)v18 | 0x80070000;
  v14 = phkResult;
  if ( v13 < 0 )
    goto LABEL_11;
  LODWORD(Data) = a5;
  v19 = RegSetValueExW(phkResult, L"RevokeOnMDMHandoff", 0, 4u, (const BYTE *)&Data, 4u);
  v13 = v19;
  if ( v19 > 0 )
    v13 = (unsigned __int16)v19 | 0x80070000;
  v14 = phkResult;
  phkResult = 0;
  if ( v13 < 0 )
    goto LABEL_12;
  if ( v14 )
    RegCloseKey(v14);
  v20 = hKey;
  hKey = 0;
  if ( v20 )
    RegCloseKey(v20);
  return 0;
}

```

## disassembly

```asm
0x18001dc4c  mov     [rsp-30h+Data], rcx
0x18001dc51  push    rbp
0x18001dc52  push    rbx
0x18001dc53  push    rsi
0x18001dc54  push    rdi
0x18001dc55  push    r14
0x18001dc57  push    r15
0x18001dc59  mov     rbp, rsp
0x18001dc5c  sub     rsp, 48h
0x18001dc60  mov     rbx, rdx
0x18001dc63  movzx   r14d, r9b
0x18001dc67  xor     r15d, r15d
0x18001dc6a  lea     rdx, [rbp+hKey]; HKEY *
0x18001dc6e  mov     ecx, 2001Fh; unsigned int
0x18001dc73  mov     [rbp+hKey], r15
0x18001dc77  mov     rdi, r8
0x18001dc7a  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18001dc7f  mov     esi, eax
0x18001dc81  test    eax, eax
0x18001dc83  jns     short loc_18001DC9F
0x18001dc85  mov     rcx, [rbp+hKey]; hKey
0x18001dc89  mov     [rbp+hKey], r15
0x18001dc8d  test    rcx, rcx
0x18001dc90  jz      short loc_18001DC98
0x18001dc92  call    cs:__imp_RegCloseKey
0x18001dc98  mov     eax, esi
0x18001dc9a  jmp     loc_18001DE04
0x18001dc9f  cmp     qword ptr [rbx+18h], 7
0x18001dca4  mov     [rbp+var_18], r15
0x18001dca8  jbe     short loc_18001DCAD
0x18001dcaa  mov     rbx, [rbx]
0x18001dcad  mov     rcx, [rbp+hKey]; hKey
0x18001dcb1  lea     rax, [rbp+var_18]
0x18001dcb5  mov     r9d, 2001Fh; samDesired
0x18001dcbb  mov     [rsp+48h+phkResult], rax; phkResult
0x18001dcc0  xor     r8d, r8d; ulOptions
0x18001dcc3  mov     rdx, rbx; lpSubKey
0x18001dcc6  call    cs:__imp_RegOpenKeyExW
0x18001dccc  mov     ebx, eax
0x18001dcce  mov     esi, 80070000h
0x18001dcd3  test    eax, eax
0x18001dcd5  jle     short loc_18001DCDC
0x18001dcd7  movzx   ebx, ax
0x18001dcda  or      ebx, esi
0x18001dcdc  test    ebx, ebx
0x18001dcde  jns     short loc_18001DD0D
0x18001dce0  mov     rcx, [rbp+var_18]; hKey
0x18001dce4  mov     [rbp+var_18], r15
0x18001dce8  test    rcx, rcx
0x18001dceb  jz      short loc_18001DCF3
0x18001dced  call    cs:__imp_RegCloseKey
0x18001dcf3  mov     rcx, [rbp+hKey]; hKey
0x18001dcf7  mov     [rbp+hKey], r15
0x18001dcfb  test    rcx, rcx
0x18001dcfe  jz      short loc_18001DD06
0x18001dd00  call    cs:__imp_RegCloseKey
0x18001dd06  mov     eax, ebx
0x18001dd08  jmp     loc_18001DE04
0x18001dd0d  cmp     qword ptr [rdi+18h], 7
0x18001dd12  jbe     short loc_18001DD17
0x18001dd14  mov     rdi, [rdi]
0x18001dd17  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001dd1b  inc     rax
0x18001dd1e  cmp     [rdi+rax*2], r15w
0x18001dd23  jnz     short loc_18001DD1B
0x18001dd25  mov     rcx, [rbp+var_18]; hKey
0x18001dd29  lea     eax, ds:2[rax*2]
0x18001dd30  mov     [rsp+48h+cbData], eax; cbData
0x18001dd34  lea     rdx, aEnterprisedata; "EnterpriseDataProtectionIdsToRevoke"
0x18001dd3b  mov     r9d, 1; dwType
0x18001dd41  mov     [rsp+48h+phkResult], rdi; lpData
0x18001dd46  xor     r8d, r8d; Reserved
0x18001dd49  call    cs:__imp_RegSetValueExW
0x18001dd4f  mov     ebx, eax
0x18001dd51  test    eax, eax
0x18001dd53  jle     short loc_18001DD5A
0x18001dd55  movzx   ebx, ax
0x18001dd58  or      ebx, esi
0x18001dd5a  mov     rcx, [rbp+var_18]; hKey
0x18001dd5e  test    ebx, ebx
0x18001dd60  js      short loc_18001DCE4
0x18001dd62  mov     edi, 4
0x18001dd67  mov     dword ptr [rbp+Data], r14d
0x18001dd6b  lea     rax, [rbp+Data]
0x18001dd6f  mov     [rsp+48h+cbData], edi; cbData
0x18001dd73  mov     r9d, edi; dwType
0x18001dd76  mov     [rsp+48h+phkResult], rax; lpData
0x18001dd7b  xor     r8d, r8d; Reserved
0x18001dd7e  lea     rdx, aRevokeonunenro_0; "RevokeOnUnenroll"
0x18001dd85  call    cs:__imp_RegSetValueExW
0x18001dd8b  mov     ebx, eax
0x18001dd8d  test    eax, eax
0x18001dd8f  jle     short loc_18001DD96
0x18001dd91  movzx   ebx, ax
0x18001dd94  or      ebx, esi
0x18001dd96  mov     rcx, [rbp+var_18]; hKey
0x18001dd9a  test    ebx, ebx
0x18001dd9c  js      loc_18001DCE4
0x18001dda2  movzx   eax, [rbp+arg_20]
0x18001dda6  lea     rdx, aRevokeonmdmhan_0; "RevokeOnMDMHandoff"
0x18001ddad  mov     dword ptr [rbp+Data], eax
0x18001ddb0  mov     r9d, edi; dwType
0x18001ddb3  lea     rax, [rbp+Data]
0x18001ddb7  mov     [rsp+48h+cbData], edi; cbData
0x18001ddbb  xor     r8d, r8d; Reserved
0x18001ddbe  mov     [rsp+48h+phkResult], rax; lpData
0x18001ddc3  call    cs:__imp_RegSetValueExW
0x18001ddc9  mov     ebx, eax
0x18001ddcb  test    eax, eax
0x18001ddcd  jle     short loc_18001DDD4
0x18001ddcf  movzx   ebx, ax
0x18001ddd2  or      ebx, esi
0x18001ddd4  mov     rcx, [rbp+var_18]; hKey
0x18001ddd8  mov     [rbp+var_18], r15
0x18001dddc  test    ebx, ebx
0x18001ddde  js      loc_18001DCE8
0x18001dde4  test    rcx, rcx
0x18001dde7  jz      short loc_18001DDEF
0x18001dde9  call    cs:__imp_RegCloseKey
0x18001ddef  mov     rcx, [rbp+hKey]; hKey
0x18001ddf3  mov     [rbp+hKey], r15
0x18001ddf7  test    rcx, rcx
0x18001ddfa  jz      short loc_18001DE02
0x18001ddfc  call    cs:__imp_RegCloseKey
0x18001de02  xor     eax, eax
0x18001de04  add     rsp, 48h
0x18001de08  pop     r15
0x18001de0a  pop     r14
0x18001de0c  pop     rdi
0x18001de0d  pop     rsi
0x18001de0e  pop     rbx
0x18001de0f  pop     rbp
0x18001de10  retn
```
