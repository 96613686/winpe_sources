# GetRegistryControlsForInetinfoCrash(ulong *,ulong *,ulong *)

- ea: `0x180025418`
- end: `0x1800255ab`
- name: `?GetRegistryControlsForInetinfoCrash@@YAXPEAK00@Z`
- size: `403`
- prototype: `void __fastcall(unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180024bf8`

## callees

- `0x180025418`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002549b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002549b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025591`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800254da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025524`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002556e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800254da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025524`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002556e`

## string_xrefs

- `0x180025486`: `System\CurrentControlSet\Services\IISAdmin\Parameters`

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
0x180025418  test    rcx, rcx
0x18002541b  jz      locret_1800255A9
0x180025421  mov     [rsp-18h+arg_8], rbx
0x180025426  push    rbp
0x180025427  push    rsi
0x180025428  push    rdi
0x180025429  mov     rbp, rsp
0x18002542c  sub     rsp, 40h
0x180025430  mov     [rbp+hKey], 0
0x180025438  mov     rbx, r8
0x18002543b  mov     dword ptr [rbp+Data], 0
0x180025442  mov     rdi, rdx
0x180025445  mov     [rbp+Type], 0
0x18002544c  mov     rsi, rcx
0x18002544f  mov     [rbp+cbData], 0
0x180025456  test    rdx, rdx
0x180025459  jz      loc_18002559D
0x18002545f  test    rbx, rbx
0x180025462  jz      loc_18002559D
0x180025468  mov     dword ptr [rcx], 0EA60h
0x18002546e  lea     rax, [rbp+hKey]
0x180025472  mov     dword ptr [rdx], 1D4C0h
0x180025478  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002547f  mov     dword ptr [r8], 1388h
0x180025486  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\II"...
0x18002548d  xor     r8d, r8d; ulOptions
0x180025490  mov     [rsp+40h+phkResult], rax; phkResult
0x180025495  mov     r9d, 20019h; samDesired
0x18002549b  call    cs:__imp_RegOpenKeyExW
0x1800254a2  nop     dword ptr [rax+rax+00h]
0x1800254a7  test    eax, eax
0x1800254a9  jnz     loc_18002559D
0x1800254af  mov     rcx, [rbp+hKey]; hKey
0x1800254b3  lea     rax, [rbp+cbData]
0x1800254b7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800254bc  lea     r9, [rbp+Type]; lpType
0x1800254c0  lea     rax, [rbp+Data]
0x1800254c4  mov     [rbp+cbData], 4
0x1800254cb  xor     r8d, r8d; lpReserved
0x1800254ce  mov     [rsp+40h+phkResult], rax; lpData
0x1800254d3  lea     rdx, aMillisecondsto; "MillisecondsToWaitForShutdownAfterCrash"
0x1800254da  call    cs:__imp_RegQueryValueExW
0x1800254e1  nop     dword ptr [rax+rax+00h]
0x1800254e6  test    eax, eax
0x1800254e8  jnz     short loc_1800254F9
0x1800254ea  cmp     [rbp+Type], 4
0x1800254ee  jnz     short loc_1800254F9
0x1800254f0  mov     eax, dword ptr [rbp+Data]
0x1800254f3  test    eax, eax
0x1800254f5  jz      short loc_1800254F9
0x1800254f7  mov     [rsi], eax
0x1800254f9  mov     rcx, [rbp+hKey]; hKey
0x1800254fd  lea     rax, [rbp+cbData]
0x180025501  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180025506  lea     r9, [rbp+Type]; lpType
0x18002550a  lea     rax, [rbp+Data]
0x18002550e  mov     [rbp+cbData], 4
0x180025515  xor     r8d, r8d; lpReserved
0x180025518  mov     [rsp+40h+phkResult], rax; lpData
0x18002551d  lea     rdx, aMillisecondsto_0; "MillisecondsToWaitForInetinfoRestartAft"...
0x180025524  call    cs:__imp_RegQueryValueExW
0x18002552b  nop     dword ptr [rax+rax+00h]
0x180025530  test    eax, eax
0x180025532  jnz     short loc_180025543
0x180025534  cmp     [rbp+Type], 4
0x180025538  jnz     short loc_180025543
0x18002553a  mov     eax, dword ptr [rbp+Data]
0x18002553d  test    eax, eax
0x18002553f  jz      short loc_180025543
0x180025541  mov     [rdi], eax
0x180025543  mov     rcx, [rbp+hKey]; hKey
0x180025547  lea     rax, [rbp+cbData]
0x18002554b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180025550  lea     r9, [rbp+Type]; lpType
0x180025554  lea     rax, [rbp+Data]
0x180025558  mov     [rbp+cbData], 4
0x18002555f  xor     r8d, r8d; lpReserved
0x180025562  mov     [rsp+40h+phkResult], rax; lpData
0x180025567  lea     rdx, aMillisecondsch; "MillisecondsCheckIntervalForInetinfoToR"...
0x18002556e  call    cs:__imp_RegQueryValueExW
0x180025575  nop     dword ptr [rax+rax+00h]
0x18002557a  test    eax, eax
0x18002557c  jnz     short loc_18002558D
0x18002557e  cmp     [rbp+Type], 4
0x180025582  jnz     short loc_18002558D
0x180025584  mov     eax, dword ptr [rbp+Data]
0x180025587  test    eax, eax
0x180025589  jz      short loc_18002558D
0x18002558b  mov     [rbx], eax
0x18002558d  mov     rcx, [rbp+hKey]; hKey
0x180025591  call    cs:__imp_RegCloseKey
0x180025598  nop     dword ptr [rax+rax+00h]
0x18002559d  mov     rbx, [rsp+40h+arg_8]
0x1800255a2  add     rsp, 40h
0x1800255a6  pop     rdi
0x1800255a7  pop     rsi
0x1800255a8  pop     rbp
0x1800255a9  retn
```
