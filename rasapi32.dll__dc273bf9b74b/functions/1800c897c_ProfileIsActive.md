# ProfileIsActive

- ea: `0x1800c897c`
- end: `0x1800c8b3d`
- name: `ProfileIsActive`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800cbe28`

## callees

- `0x18004eab4`
- `0x1800c897c`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8a26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8a26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8b18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8b18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c8a64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c8ab7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c8a64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c8ab7`

## string_xrefs

- `0x1800c89fa`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800c8a0c`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800c8ab0`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall ProfileIsActive(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const WCHAR *v6; // rdx
  BYTE *v7; // rax
  __int64 v8; // rsi
  int v9; // edx
  int v10; // ecx
  BYTE *v11; // rax
  __int64 v12; // rdi
  int v13; // ecx
  int v14; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v20[528]; // [rsp+250h] [rbp+150h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  v4 = 0;
  memset_0(Data, 0, 0x105u);
  memset_0(v20, 0, 0x105u);
  if ( a2 )
  {
    v5 = StateSepEnabled();
    v6 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !v5 )
      v6 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
    {
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, Data, &cbData) && Type - 1 <= 1 )
      {
        cbData = 520;
        if ( !RegQueryValueExW(hKey, L"AutoTriggerProfilePhonebookPath", 0, &Type, v20, &cbData) && Type - 1 <= 1 )
        {
          v7 = Data;
          v8 = a1 - (_QWORD)Data;
          do
          {
            v9 = *(unsigned __int16 *)&v7[v8];
            v10 = *(unsigned __int16 *)v7 - v9;
            if ( v10 )
              break;
            v7 += 2;
          }
          while ( v9 );
          if ( !v10 )
          {
            v11 = v20;
            v12 = a2 - (_QWORD)v20;
            do
            {
              v13 = *(unsigned __int16 *)&v11[v12];
              v14 = *(unsigned __int16 *)v11 - v13;
              if ( v14 )
                break;
              v11 += 2;
            }
            while ( v13 );
            if ( !v14 )
              v4 = 1;
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800c897c  push    rbp
0x1800c897e  push    rbx
0x1800c897f  push    rsi
0x1800c8980  push    rdi
0x1800c8981  push    r14
0x1800c8983  lea     rbp, [rsp-370h]
0x1800c898b  sub     rsp, 470h
0x1800c8992  mov     rax, cs:__security_cookie
0x1800c8999  xor     rax, rsp
0x1800c899c  mov     [rbp+390h+var_30], rax
0x1800c89a3  mov     rdi, rdx
0x1800c89a6  mov     [rsp+490h+cbData], 0
0x1800c89ae  mov     rsi, rcx
0x1800c89b1  mov     [rsp+490h+Type], 0
0x1800c89b9  mov     r14d, 105h
0x1800c89bf  mov     [rsp+490h+hKey], 0
0x1800c89c8  mov     r8d, r14d; Size
0x1800c89cb  lea     rcx, [rsp+490h+Data]; void *
0x1800c89d0  xor     edx, edx; Val
0x1800c89d2  xor     ebx, ebx
0x1800c89d4  call    memset_0
0x1800c89d9  mov     r8d, r14d; Size
0x1800c89dc  lea     rcx, [rbp+390h+var_240]; void *
0x1800c89e3  xor     edx, edx; Val
0x1800c89e5  call    memset_0
0x1800c89ea  test    rdi, rdi
0x1800c89ed  jz      loc_1800C8B1E
0x1800c89f3  call    StateSepEnabled
0x1800c89f8  test    eax, eax
0x1800c89fa  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800c8a01  lea     rax, [rsp+490h+hKey]
0x1800c8a06  mov     r9d, 20019h; samDesired
0x1800c8a0c  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800c8a13  mov     [rsp+490h+phkResult], rax; phkResult
0x1800c8a18  cmovz   rdx, rcx; lpSubKey
0x1800c8a1c  xor     r8d, r8d; ulOptions
0x1800c8a1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c8a26  call    cs:__imp_RegOpenKeyExW
0x1800c8a2c  test    eax, eax
0x1800c8a2e  jnz     loc_1800C8B0E
0x1800c8a34  mov     rcx, [rsp+490h+hKey]; hKey
0x1800c8a39  lea     rax, [rsp+490h+cbData]
0x1800c8a3e  mov     [rsp+490h+lpcbData], rax; lpcbData
0x1800c8a43  lea     r9, [rsp+490h+Type]; lpType
0x1800c8a48  lea     rax, [rsp+490h+Data]
0x1800c8a4d  mov     [rsp+490h+cbData], 208h
0x1800c8a55  xor     r8d, r8d; lpReserved
0x1800c8a58  mov     [rsp+490h+phkResult], rax; lpData
0x1800c8a5d  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x1800c8a64  call    cs:__imp_RegQueryValueExW
0x1800c8a6a  test    eax, eax
0x1800c8a6c  jnz     loc_1800C8B0E
0x1800c8a72  mov     eax, [rsp+490h+Type]
0x1800c8a76  lea     r14d, [rbx+1]
0x1800c8a7a  dec     eax
0x1800c8a7c  cmp     eax, r14d
0x1800c8a7f  ja      loc_1800C8B0E
0x1800c8a85  mov     rcx, [rsp+490h+hKey]; hKey
0x1800c8a8a  lea     rax, [rsp+490h+cbData]
0x1800c8a8f  mov     [rsp+490h+lpcbData], rax; lpcbData
0x1800c8a94  lea     r9, [rsp+490h+Type]; lpType
0x1800c8a99  lea     rax, [rbp+390h+var_240]
0x1800c8aa0  mov     [rsp+490h+cbData], 208h
0x1800c8aa8  xor     r8d, r8d; lpReserved
0x1800c8aab  mov     [rsp+490h+phkResult], rax; lpData
0x1800c8ab0  lea     rdx, aAutotriggerpro_0; "AutoTriggerProfilePhonebookPath"
0x1800c8ab7  call    cs:__imp_RegQueryValueExW
0x1800c8abd  test    eax, eax
0x1800c8abf  jnz     short loc_1800C8B0E
0x1800c8ac1  mov     eax, [rsp+490h+Type]
0x1800c8ac5  dec     eax
0x1800c8ac7  cmp     eax, r14d
0x1800c8aca  ja      short loc_1800C8B0E
0x1800c8acc  lea     rax, [rsp+490h+Data]
0x1800c8ad1  sub     rsi, rax
0x1800c8ad4  movzx   ecx, word ptr [rax]
0x1800c8ad7  movzx   edx, word ptr [rax+rsi]
0x1800c8adb  sub     ecx, edx
0x1800c8add  jnz     short loc_1800C8AE7
0x1800c8adf  add     rax, 2
0x1800c8ae3  test    edx, edx
0x1800c8ae5  jnz     short loc_1800C8AD4
0x1800c8ae7  test    ecx, ecx
0x1800c8ae9  jnz     short loc_1800C8B0E
0x1800c8aeb  lea     rax, [rbp+390h+var_240]
0x1800c8af2  sub     rdi, rax
0x1800c8af5  movzx   edx, word ptr [rax]
0x1800c8af8  movzx   ecx, word ptr [rax+rdi]
0x1800c8afc  sub     edx, ecx
0x1800c8afe  jnz     short loc_1800C8B08
0x1800c8b00  add     rax, 2
0x1800c8b04  test    ecx, ecx
0x1800c8b06  jnz     short loc_1800C8AF5
0x1800c8b08  test    edx, edx
0x1800c8b0a  cmovz   ebx, r14d
0x1800c8b0e  mov     rcx, [rsp+490h+hKey]; hKey
0x1800c8b13  test    rcx, rcx
0x1800c8b16  jz      short loc_1800C8B1E
0x1800c8b18  call    cs:__imp_RegCloseKey
0x1800c8b1e  mov     eax, ebx
0x1800c8b20  mov     rcx, [rbp+390h+var_30]
0x1800c8b27  xor     rcx, rsp; StackCookie
0x1800c8b2a  call    __security_check_cookie
0x1800c8b2f  add     rsp, 470h
0x1800c8b36  pop     r14
0x1800c8b38  pop     rdi
0x1800c8b39  pop     rsi
0x1800c8b3a  pop     rbx
0x1800c8b3b  pop     rbp
0x1800c8b3c  retn
```
