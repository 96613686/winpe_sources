# PerfDiagStartupResourceUtilizationReporting::GetBootCKCLTraceSizeMB

- ea: `0x1800415b4`
- end: `0x1800416e0`
- name: `PerfDiagStartupResourceUtilizationReporting::GetBootCKCLTraceSizeMB`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180016dec`
- `0x1800375cc`

## callees

- `0x1800415b4`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004163e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004163e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041602`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800416b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800416b7`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004165a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18004165a`
- `KERNEL32!GetFileAttributesExW` at `0x180041694`
- `KERNEL32!GetFileAttributesExW` at `0x180041694`

## pseudocode

```c
__int64 PerfDiagStartupResourceUtilizationReporting::GetBootCKCLTraceSizeMB()
{
  unsigned __int16 v0; // bx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD FileInformation[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v5; // [rsp+60h] [rbp-A0h]
  WCHAR Data[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Dst[264]; // [rsp+280h] [rbp+180h] BYREF

  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Diagnostics\\Performance\\BootCKCLSettings",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"FileName", 0, 0, (LPBYTE)Data, &cbData) )
    {
      if ( !ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
      {
        RegCloseKey(hKey);
        return 0;
      }
      v5 = 0;
      memset(FileInformation, 0, sizeof(FileInformation));
      if ( GetFileAttributesExW(Dst, GetFileExInfoStandard, FileInformation) )
        v0 = v5 / 0x100000;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1800415b4  mov     [rsp-8+arg_0], rbx
0x1800415b9  push    rbp
0x1800415ba  lea     rbp, [rsp-3A0h]
0x1800415c2  sub     rsp, 4A0h
0x1800415c9  mov     rax, cs:__security_cookie
0x1800415d0  xor     rax, rsp
0x1800415d3  mov     [rbp+3A0h+var_10], rax
0x1800415da  lea     rax, [rsp+4A0h+hKey]
0x1800415df  xor     ebx, ebx
0x1800415e1  mov     r9d, 20019h; samDesired
0x1800415e7  mov     [rsp+4A0h+hKey], rbx
0x1800415ec  xor     r8d, r8d; ulOptions
0x1800415ef  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800415f4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Dia"...
0x1800415fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041602  call    cs:__imp_RegOpenKeyExW
0x180041608  test    eax, eax
0x18004160a  jnz     loc_1800416AD
0x180041610  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180041615  lea     rax, [rsp+4A0h+cbData]
0x18004161a  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18004161f  lea     rdx, aFilename; "FileName"
0x180041626  lea     rax, [rsp+4A0h+Data]
0x18004162b  mov     [rsp+4A0h+cbData], 208h
0x180041633  xor     r9d, r9d; lpType
0x180041636  mov     [rsp+4A0h+phkResult], rax; lpData
0x18004163b  xor     r8d, r8d; lpReserved
0x18004163e  call    cs:__imp_RegQueryValueExW
0x180041644  test    eax, eax
0x180041646  jnz     short loc_1800416AD
0x180041648  mov     r8d, 104h; nSize
0x18004164e  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x180041655  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x18004165a  call    cs:__imp_ExpandEnvironmentStringsW
0x180041660  test    eax, eax
0x180041662  jnz     short loc_180041673
0x180041664  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180041669  call    cs:__imp_RegCloseKey
0x18004166f  xor     eax, eax
0x180041671  jmp     short loc_1800416C0
0x180041673  xorps   xmm0, xmm0
0x180041676  lea     r8, [rsp+4A0h+FileInformation]; lpFileInformation
0x18004167b  xor     eax, eax
0x18004167d  lea     rcx, [rbp+3A0h+Dst]; lpFileName
0x180041684  xor     edx, edx; fInfoLevelId
0x180041686  mov     [rsp+4A0h+var_440], eax
0x18004168a  movups  [rsp+4A0h+FileInformation], xmm0
0x18004168f  movups  [rsp+4A0h+var_450], xmm0
0x180041694  call    cs:__imp_GetFileAttributesExW
0x18004169a  test    eax, eax
0x18004169c  jz      short loc_1800416AD
0x18004169e  mov     eax, [rsp+4A0h+var_440]
0x1800416a2  mov     ecx, 100000h
0x1800416a7  cdq
0x1800416a8  idiv    ecx
0x1800416aa  movzx   ebx, ax
0x1800416ad  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800416b2  test    rcx, rcx
0x1800416b5  jz      short loc_1800416BD
0x1800416b7  call    cs:__imp_RegCloseKey
0x1800416bd  movzx   eax, bx
0x1800416c0  mov     rcx, [rbp+3A0h+var_10]
0x1800416c7  xor     rcx, rsp; StackCookie
0x1800416ca  call    __security_check_cookie
0x1800416cf  mov     rbx, [rsp+4A0h+arg_0]
0x1800416d7  add     rsp, 4A0h
0x1800416de  pop     rbp
0x1800416df  retn
```
