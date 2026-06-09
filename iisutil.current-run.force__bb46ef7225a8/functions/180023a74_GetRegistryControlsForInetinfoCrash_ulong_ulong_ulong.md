# GetRegistryControlsForInetinfoCrash(ulong *,ulong *,ulong *)

- ea: `0x180023a74`
- end: `0x180023be8`
- name: `?GetRegistryControlsForInetinfoCrash@@YAXPEAK00@Z`
- size: `372`
- prototype: `void __fastcall(unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180023308`

## callees

- `0x180023a74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023af7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023af7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023bd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023bd5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023b30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023b74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023bb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023b30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023b74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023bb8`

## string_xrefs

- `0x180023ae2`: `System\CurrentControlSet\Services\IISAdmin\Parameters`

## pseudocode

```c
void __fastcall GetRegistryControlsForInetinfoCrash(unsigned int *a1, unsigned int *a2, unsigned int *a3)
{
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  if ( a1 )
  {
    hKey = 0;
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 0;
    if ( a2 )
    {
      if ( a3 )
      {
        *a1 = 60000;
        *a2 = 120000;
        *a3 = 5000;
        if ( !RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\IISAdmin\\Parameters",
                0,
                0x20019u,
                &hKey) )
        {
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"MillisecondsToWaitForShutdownAfterCrash", 0, &Type, Data, &cbData)
            && Type == 4
            && *(_DWORD *)Data )
          {
            *a1 = *(_DWORD *)Data;
          }
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"MillisecondsToWaitForInetinfoRestartAfterCrash", 0, &Type, Data, &cbData)
            && Type == 4
            && *(_DWORD *)Data )
          {
            *a2 = *(_DWORD *)Data;
          }
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"MillisecondsCheckIntervalForInetinfoToRestart", 0, &Type, Data, &cbData)
            && Type == 4 )
          {
            if ( *(_DWORD *)Data )
              *a3 = *(_DWORD *)Data;
          }
          RegCloseKey(hKey);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180023a74  test    rcx, rcx
0x180023a77  jz      locret_180023BE7
0x180023a7d  mov     [rsp-18h+arg_8], rbx
0x180023a82  push    rbp
0x180023a83  push    rsi
0x180023a84  push    rdi
0x180023a85  mov     rbp, rsp
0x180023a88  sub     rsp, 40h
0x180023a8c  mov     [rbp+hKey], 0
0x180023a94  mov     rbx, r8
0x180023a97  mov     dword ptr [rbp+Data], 0
0x180023a9e  mov     rdi, rdx
0x180023aa1  mov     [rbp+Type], 0
0x180023aa8  mov     rsi, rcx
0x180023aab  mov     [rbp+cbData], 0
0x180023ab2  test    rdx, rdx
0x180023ab5  jz      loc_180023BDB
0x180023abb  test    rbx, rbx
0x180023abe  jz      loc_180023BDB
0x180023ac4  mov     dword ptr [rcx], 0EA60h
0x180023aca  lea     rax, [rbp+hKey]
0x180023ace  mov     dword ptr [rdx], 1D4C0h
0x180023ad4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023adb  mov     dword ptr [r8], 1388h
0x180023ae2  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\II"...
0x180023ae9  xor     r8d, r8d; ulOptions
0x180023aec  mov     [rsp+40h+phkResult], rax; phkResult
0x180023af1  mov     r9d, 20019h; samDesired
0x180023af7  call    cs:__imp_RegOpenKeyExW
0x180023afd  test    eax, eax
0x180023aff  jnz     loc_180023BDB
0x180023b05  mov     rcx, [rbp+hKey]; hKey
0x180023b09  lea     rax, [rbp+cbData]
0x180023b0d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023b12  lea     r9, [rbp+Type]; lpType
0x180023b16  lea     rax, [rbp+Data]
0x180023b1a  mov     [rbp+cbData], 4
0x180023b21  xor     r8d, r8d; lpReserved
0x180023b24  mov     [rsp+40h+phkResult], rax; lpData
0x180023b29  lea     rdx, aMillisecondsto; "MillisecondsToWaitForShutdownAfterCrash"
0x180023b30  call    cs:__imp_RegQueryValueExW
0x180023b36  test    eax, eax
0x180023b38  jnz     short loc_180023B49
0x180023b3a  cmp     [rbp+Type], 4
0x180023b3e  jnz     short loc_180023B49
0x180023b40  mov     eax, dword ptr [rbp+Data]
0x180023b43  test    eax, eax
0x180023b45  jz      short loc_180023B49
0x180023b47  mov     [rsi], eax
0x180023b49  mov     rcx, [rbp+hKey]; hKey
0x180023b4d  lea     rax, [rbp+cbData]
0x180023b51  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023b56  lea     r9, [rbp+Type]; lpType
0x180023b5a  lea     rax, [rbp+Data]
0x180023b5e  mov     [rbp+cbData], 4
0x180023b65  xor     r8d, r8d; lpReserved
0x180023b68  mov     [rsp+40h+phkResult], rax; lpData
0x180023b6d  lea     rdx, aMillisecondsto_0; "MillisecondsToWaitForInetinfoRestartAft"...
0x180023b74  call    cs:__imp_RegQueryValueExW
0x180023b7a  test    eax, eax
0x180023b7c  jnz     short loc_180023B8D
0x180023b7e  cmp     [rbp+Type], 4
0x180023b82  jnz     short loc_180023B8D
0x180023b84  mov     eax, dword ptr [rbp+Data]
0x180023b87  test    eax, eax
0x180023b89  jz      short loc_180023B8D
0x180023b8b  mov     [rdi], eax
0x180023b8d  mov     rcx, [rbp+hKey]; hKey
0x180023b91  lea     rax, [rbp+cbData]
0x180023b95  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023b9a  lea     r9, [rbp+Type]; lpType
0x180023b9e  lea     rax, [rbp+Data]
0x180023ba2  mov     [rbp+cbData], 4
0x180023ba9  xor     r8d, r8d; lpReserved
0x180023bac  mov     [rsp+40h+phkResult], rax; lpData
0x180023bb1  lea     rdx, aMillisecondsch; "MillisecondsCheckIntervalForInetinfoToR"...
0x180023bb8  call    cs:__imp_RegQueryValueExW
0x180023bbe  test    eax, eax
0x180023bc0  jnz     short loc_180023BD1
0x180023bc2  cmp     [rbp+Type], 4
0x180023bc6  jnz     short loc_180023BD1
0x180023bc8  mov     eax, dword ptr [rbp+Data]
0x180023bcb  test    eax, eax
0x180023bcd  jz      short loc_180023BD1
0x180023bcf  mov     [rbx], eax
0x180023bd1  mov     rcx, [rbp+hKey]; hKey
0x180023bd5  call    cs:__imp_RegCloseKey
0x180023bdb  mov     rbx, [rsp+40h+arg_8]
0x180023be0  add     rsp, 40h
0x180023be4  pop     rdi
0x180023be5  pop     rsi
0x180023be6  pop     rbp
0x180023be7  retn
```
