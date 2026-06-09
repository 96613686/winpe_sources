# DwGetInstalledProtocolsEx

- ea: `0x18005bdf4`
- end: `0x18005bf9c`
- name: `DwGetInstalledProtocolsEx`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f500`

## callees

- `0x18005bdf4`
- `0x18005c8f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bea0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005beeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005bea0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005beeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005be5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005be5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005bf77`

## string_xrefs

- `0x18005be92`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall DwGetInstalledProtocolsEx(int a1, int a2, int a3)
{
  unsigned int v3; // ebx
  unsigned int i; // edi
  unsigned int j; // edi
  const WCHAR *v8; // rdx
  HKEY v9; // rsi
  int v10; // eax
  int v11; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  int v14; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v14 = a2;
  v3 = 0;
  hKey = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)qword_1800EC5D0[3 * (int)i + 1], 0, 0x2000000u, &hKey) )
    {
      v3 |= LODWORD(qword_1800EC5D0[3 * (int)i]);
      RegCloseKey(hKey);
    }
  }
  if ( (a1 || a3) && v3 )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
           0,
           0x2000000u,
           &hKey) )
    {
      return 0;
    }
    else
    {
      for ( j = 0; j < 2; ++j )
      {
        if ( (v3 & qword_1800EC5D0[3 * (int)j]) != 0 )
        {
          v8 = (const WCHAR *)qword_1800EC5D0[3 * (int)j + 2];
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey, v8, 0, 0x2000000u, &phkResult) )
          {
            v9 = phkResult;
            v14 = 0;
            if ( !a3 || (v10 = RegQueryDword(phkResult, L"EnableIn", &v14), v10 != 2) && (v10 || !v14) )
            {
              if ( !a1 || (v11 = RegQueryDword(v9, L"EnableRoute", &v14), v11 != 2) && (v11 || !v14) )
                v3 &= ~LODWORD(qword_1800EC5D0[3 * (int)j]);
            }
            RegCloseKey(phkResult);
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005bdf4  mov     [rsp-28h+arg_0], rbx
0x18005bdf9  mov     [rsp-28h+arg_10], rsi
0x18005bdfe  mov     [rsp-28h+arg_8], edx
0x18005be02  push    rbp
0x18005be03  push    rdi
0x18005be04  push    r12
0x18005be06  push    r14
0x18005be08  push    r15
0x18005be0a  mov     rbp, rsp
0x18005be0d  sub     rsp, 40h
0x18005be11  xor     ebx, ebx
0x18005be13  lea     r14, qword_1800EC5D0
0x18005be1a  mov     [rbp+hKey], rbx
0x18005be1e  xor     edi, edi
0x18005be20  mov     r15d, r8d
0x18005be23  mov     r12d, ecx
0x18005be26  movsxd  rax, edi
0x18005be29  mov     r9d, 2000000h; samDesired
0x18005be2f  xor     r8d, r8d; ulOptions
0x18005be32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005be39  lea     rsi, [rax+rax*2]
0x18005be3d  mov     rdx, [r14+rsi*8+8]; lpSubKey
0x18005be42  lea     rax, [rbp+hKey]
0x18005be46  mov     [rsp+40h+phkResult], rax; phkResult
0x18005be4b  call    cs:__imp_RegOpenKeyExW
0x18005be51  test    eax, eax
0x18005be53  jnz     short loc_18005BE63
0x18005be55  or      ebx, [r14+rsi*8]
0x18005be59  mov     rcx, [rbp+hKey]; hKey
0x18005be5d  call    cs:__imp_RegCloseKey
0x18005be63  inc     edi
0x18005be65  cmp     edi, 2
0x18005be68  jb      short loc_18005BE26
0x18005be6a  test    r12d, r12d
0x18005be6d  jnz     short loc_18005BE78
0x18005be6f  test    r15d, r15d
0x18005be72  jz      loc_18005BF81
0x18005be78  test    ebx, ebx
0x18005be7a  jz      loc_18005BF81
0x18005be80  lea     rax, [rbp+hKey]
0x18005be84  mov     r9d, 2000000h; samDesired
0x18005be8a  xor     r8d, r8d; ulOptions
0x18005be8d  mov     [rsp+40h+phkResult], rax; phkResult
0x18005be92  lea     rdx, aSystemCurrentc_30; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18005be99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bea0  call    cs:__imp_RegOpenKeyExW
0x18005bea6  test    eax, eax
0x18005bea8  jnz     loc_18005BF7F
0x18005beae  xor     edi, edi
0x18005beb0  lea     rcx, qword_1800EC5D0
0x18005beb7  movsxd  rax, edi
0x18005beba  lea     r14, [rax+rax*2]
0x18005bebe  test    [rcx+r14*8], ebx
0x18005bec2  jz      loc_18005BF68
0x18005bec8  mov     rdx, [rcx+r14*8+10h]; lpSubKey
0x18005becd  lea     rax, [rbp+var_10]
0x18005bed1  mov     rcx, [rbp+hKey]; hKey
0x18005bed5  mov     r9d, 2000000h; samDesired
0x18005bedb  xor     r8d, r8d; ulOptions
0x18005bede  mov     [rsp+40h+phkResult], rax; phkResult
0x18005bee3  mov     [rbp+var_10], 0
0x18005beeb  call    cs:__imp_RegOpenKeyExW
0x18005bef1  test    eax, eax
0x18005bef3  jnz     short loc_18005BF61
0x18005bef5  mov     rsi, [rbp+var_10]
0x18005bef9  mov     [rbp+arg_8], eax
0x18005befc  test    r15d, r15d
0x18005beff  jz      short loc_18005BF22
0x18005bf01  lea     r8, [rbp+arg_8]
0x18005bf05  mov     rcx, rsi
0x18005bf08  lea     rdx, aEnablein; "EnableIn"
0x18005bf0f  call    RegQueryDword
0x18005bf14  cmp     eax, 2
0x18005bf17  jz      short loc_18005BF57
0x18005bf19  test    eax, eax
0x18005bf1b  jnz     short loc_18005BF22
0x18005bf1d  cmp     [rbp+arg_8], eax
0x18005bf20  jnz     short loc_18005BF57
0x18005bf22  test    r12d, r12d
0x18005bf25  jz      short loc_18005BF48
0x18005bf27  lea     r8, [rbp+arg_8]
0x18005bf2b  mov     rcx, rsi
0x18005bf2e  lea     rdx, aEnableroute; "EnableRoute"
0x18005bf35  call    RegQueryDword
0x18005bf3a  cmp     eax, 2
0x18005bf3d  jz      short loc_18005BF57
0x18005bf3f  test    eax, eax
0x18005bf41  jnz     short loc_18005BF48
0x18005bf43  cmp     [rbp+arg_8], eax
0x18005bf46  jnz     short loc_18005BF57
0x18005bf48  lea     rax, qword_1800EC5D0
0x18005bf4f  mov     eax, [rax+r14*8]
0x18005bf53  not     eax
0x18005bf55  and     ebx, eax
0x18005bf57  mov     rcx, [rbp+var_10]; hKey
0x18005bf5b  call    cs:__imp_RegCloseKey
0x18005bf61  lea     rcx, qword_1800EC5D0
0x18005bf68  inc     edi
0x18005bf6a  cmp     edi, 2
0x18005bf6d  jb      loc_18005BEB7
0x18005bf73  mov     rcx, [rbp+hKey]; hKey
0x18005bf77  call    cs:__imp_RegCloseKey
0x18005bf7d  jmp     short loc_18005BF81
0x18005bf7f  xor     ebx, ebx
0x18005bf81  lea     r11, [rsp+40h+var_s0]
0x18005bf86  mov     eax, ebx
0x18005bf88  mov     rbx, [r11+30h]
0x18005bf8c  mov     rsi, [r11+40h]
0x18005bf90  mov     rsp, r11
0x18005bf93  pop     r15
0x18005bf95  pop     r14
0x18005bf97  pop     r12
0x18005bf99  pop     rdi
0x18005bf9a  pop     rbp
0x18005bf9b  retn
```
