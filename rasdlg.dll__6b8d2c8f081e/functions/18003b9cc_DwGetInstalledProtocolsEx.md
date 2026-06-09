# DwGetInstalledProtocolsEx

- ea: `0x18003b9cc`
- end: `0x18003bb94`
- name: `DwGetInstalledProtocolsEx`
- size: `456`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800449fc`

## callees

- `0x18003b9cc`
- `0x18003c5c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ba23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ba78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bac3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ba23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ba78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bac3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ba35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bb33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bb4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ba35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bb33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bb4f`
- `rtutils!TracePrintfExA` at `0x18003bb73`
- `rtutils!TracePrintfExA` at `0x18003bb73`

## string_xrefs

- `0x18003bb67`: `GetInstalledProtocolsEx=0x%x. `
- `0x18003ba6a`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

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
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)qword_180050530[3 * (int)i + 1], 0, 0x2000000u, &hKey) )
    {
      v3 |= LODWORD(qword_180050530[3 * (int)i]);
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
      v3 = 0;
    }
    else
    {
      for ( j = 0; j < 2; ++j )
      {
        if ( (v3 & qword_180050530[3 * (int)j]) != 0 )
        {
          v8 = (const WCHAR *)qword_180050530[3 * (int)j + 2];
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey, v8, 0, 0x2000000u, &phkResult) )
          {
            v9 = phkResult;
            v14 = 0;
            if ( !a3 || (v10 = RegQueryDword(phkResult, L"EnableIn", &v14), v10 != 2) && (v10 || !v14) )
            {
              if ( !a1 || (v11 = RegQueryDword(v9, L"EnableRoute", &v14), v11 != 2) && (v11 || !v14) )
                v3 &= ~LODWORD(qword_180050530[3 * (int)j]);
            }
            RegCloseKey(phkResult);
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GetInstalledProtocolsEx=0x%x. ", v3);
  return v3;
}

```

## disassembly

```asm
0x18003b9cc  mov     [rsp-28h+arg_0], rbx
0x18003b9d1  mov     [rsp-28h+arg_10], rsi
0x18003b9d6  mov     [rsp-28h+arg_8], edx
0x18003b9da  push    rbp
0x18003b9db  push    rdi
0x18003b9dc  push    r12
0x18003b9de  push    r14
0x18003b9e0  push    r15
0x18003b9e2  mov     rbp, rsp
0x18003b9e5  sub     rsp, 40h
0x18003b9e9  xor     ebx, ebx
0x18003b9eb  lea     r14, qword_180050530
0x18003b9f2  mov     [rbp+hKey], rbx
0x18003b9f6  xor     edi, edi
0x18003b9f8  mov     r15d, r8d
0x18003b9fb  mov     r12d, ecx
0x18003b9fe  movsxd  rax, edi
0x18003ba01  mov     r9d, 2000000h; samDesired
0x18003ba07  xor     r8d, r8d; ulOptions
0x18003ba0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ba11  lea     rsi, [rax+rax*2]
0x18003ba15  mov     rdx, [r14+rsi*8+8]; lpSubKey
0x18003ba1a  lea     rax, [rbp+hKey]
0x18003ba1e  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ba23  call    cs:__imp_RegOpenKeyExW
0x18003ba29  test    eax, eax
0x18003ba2b  jnz     short loc_18003BA3B
0x18003ba2d  or      ebx, [r14+rsi*8]
0x18003ba31  mov     rcx, [rbp+hKey]; hKey
0x18003ba35  call    cs:__imp_RegCloseKey
0x18003ba3b  inc     edi
0x18003ba3d  cmp     edi, 2
0x18003ba40  jb      short loc_18003B9FE
0x18003ba42  test    r12d, r12d
0x18003ba45  jnz     short loc_18003BA50
0x18003ba47  test    r15d, r15d
0x18003ba4a  jz      loc_18003BB59
0x18003ba50  test    ebx, ebx
0x18003ba52  jz      loc_18003BB59
0x18003ba58  lea     rax, [rbp+hKey]
0x18003ba5c  mov     r9d, 2000000h; samDesired
0x18003ba62  xor     r8d, r8d; ulOptions
0x18003ba65  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ba6a  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18003ba71  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ba78  call    cs:__imp_RegOpenKeyExW
0x18003ba7e  test    eax, eax
0x18003ba80  jnz     loc_18003BB57
0x18003ba86  xor     edi, edi
0x18003ba88  lea     rcx, qword_180050530
0x18003ba8f  movsxd  rax, edi
0x18003ba92  lea     r14, [rax+rax*2]
0x18003ba96  test    [rcx+r14*8], ebx
0x18003ba9a  jz      loc_18003BB40
0x18003baa0  mov     rdx, [rcx+r14*8+10h]; lpSubKey
0x18003baa5  lea     rax, [rbp+var_10]
0x18003baa9  mov     rcx, [rbp+hKey]; hKey
0x18003baad  mov     r9d, 2000000h; samDesired
0x18003bab3  xor     r8d, r8d; ulOptions
0x18003bab6  mov     [rsp+40h+phkResult], rax; phkResult
0x18003babb  mov     [rbp+var_10], 0
0x18003bac3  call    cs:__imp_RegOpenKeyExW
0x18003bac9  test    eax, eax
0x18003bacb  jnz     short loc_18003BB39
0x18003bacd  mov     rsi, [rbp+var_10]
0x18003bad1  mov     [rbp+arg_8], eax
0x18003bad4  test    r15d, r15d
0x18003bad7  jz      short loc_18003BAFA
0x18003bad9  lea     r8, [rbp+arg_8]
0x18003badd  mov     rcx, rsi
0x18003bae0  lea     rdx, aEnablein_0; "EnableIn"
0x18003bae7  call    RegQueryDword
0x18003baec  cmp     eax, 2
0x18003baef  jz      short loc_18003BB2F
0x18003baf1  test    eax, eax
0x18003baf3  jnz     short loc_18003BAFA
0x18003baf5  cmp     [rbp+arg_8], eax
0x18003baf8  jnz     short loc_18003BB2F
0x18003bafa  test    r12d, r12d
0x18003bafd  jz      short loc_18003BB20
0x18003baff  lea     r8, [rbp+arg_8]
0x18003bb03  mov     rcx, rsi
0x18003bb06  lea     rdx, aEnableroute; "EnableRoute"
0x18003bb0d  call    RegQueryDword
0x18003bb12  cmp     eax, 2
0x18003bb15  jz      short loc_18003BB2F
0x18003bb17  test    eax, eax
0x18003bb19  jnz     short loc_18003BB20
0x18003bb1b  cmp     [rbp+arg_8], eax
0x18003bb1e  jnz     short loc_18003BB2F
0x18003bb20  lea     rax, qword_180050530
0x18003bb27  mov     eax, [rax+r14*8]
0x18003bb2b  not     eax
0x18003bb2d  and     ebx, eax
0x18003bb2f  mov     rcx, [rbp+var_10]; hKey
0x18003bb33  call    cs:__imp_RegCloseKey
0x18003bb39  lea     rcx, qword_180050530
0x18003bb40  inc     edi
0x18003bb42  cmp     edi, 2
0x18003bb45  jb      loc_18003BA8F
0x18003bb4b  mov     rcx, [rbp+hKey]; hKey
0x18003bb4f  call    cs:__imp_RegCloseKey
0x18003bb55  jmp     short loc_18003BB59
0x18003bb57  xor     ebx, ebx
0x18003bb59  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003bb5f  cmp     ecx, 0FFFFFFFFh
0x18003bb62  jz      short loc_18003BB79
0x18003bb64  mov     r9d, ebx
0x18003bb67  lea     r8, aGetinstalledpr; "GetInstalledProtocolsEx=0x%x. "
0x18003bb6e  mov     edx, 0Ch; dwFlags
0x18003bb73  call    cs:__imp_TracePrintfExA
0x18003bb79  lea     r11, [rsp+40h+var_s0]
0x18003bb7e  mov     eax, ebx
0x18003bb80  mov     rbx, [r11+30h]
0x18003bb84  mov     rsi, [r11+40h]
0x18003bb88  mov     rsp, r11
0x18003bb8b  pop     r15
0x18003bb8d  pop     r14
0x18003bb8f  pop     r12
0x18003bb91  pop     rdi
0x18003bb92  pop     rbp
0x18003bb93  retn
```
