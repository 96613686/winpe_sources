# InstallDtcAsAnOleTxTm

- ea: `0x1800508b4`
- end: `0x180050a73`
- name: `InstallDtcAsAnOleTxTm`
- size: `447`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012e50`
- `0x180051df0`

## callees

- `0x18000e6f4`
- `0x180011ac0`
- `0x1800508b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800509ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800509ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050975`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180050975`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18005091e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18005091e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050a21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050a21`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050a54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050a63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050a54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180050a63`

## string_xrefs

- `0x1800509b5`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050a38`: `com\complus\dtc\dtc\adme\deployment.cpp`
- `0x180050991`: `MSDTCPRX.DLL`
- `0x18005092e`: `InstallDtcAsAnOleTxTm: failed to create registry key`
- `0x180050985`: `InstallDtcAsAnOleTxTm: failed to create key`
- `0x1800509bc`: `InstallDtcAsAnOleTxTm: failed to initialize value length`
- `0x180050a31`: `InstallDtcAsAnOleTxTm: failed to set registry value`

## pseudocode

```c
__int64 InstallDtcAsAnOleTxTm()
{
  LSTATUS v0; // eax
  unsigned int v1; // r9d
  char *v2; // rdx
  int v3; // ebx
  const BYTE *v4; // r11
  DWORD dwDisposition; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int64 v9; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  v9 = 0;
  v0 = RegCreateKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Classes\\OLETransactionManagers",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( v0 )
  {
    v1 = 251;
    v2 = "InstallDtcAsAnOleTxTm: failed to create registry key";
  }
  else
  {
    v0 = RegCreateKeyExW(hKey, L"MSDTC", 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
    if ( v0 )
    {
      v1 = 264;
      v2 = "InstallDtcAsAnOleTxTm: failed to create key";
    }
    else
    {
      v3 = StringCchLengthA("MSDTCPRX.DLL", 0xDu, &v9);
      if ( v3 < 0 )
      {
        TraceFile(
          0,
          "InstallDtcAsAnOleTxTm: failed to initialize value length",
          "com\\complus\\dtc\\dtc\\adme\\deployment.cpp",
          0x112u);
        goto LABEL_13;
      }
      v0 = RegSetValueExA(phkResult, "DLL", 0, 1u, v4, v9 + 1);
      if ( v0 )
      {
        v1 = 285;
      }
      else
      {
        v0 = RegSetValueExW(hKey, L"DefaultTM", 0, 1u, (const BYTE *)L"MSDTC", 0xCu);
        if ( !v0 )
          goto LABEL_13;
        v1 = 297;
      }
      v2 = "InstallDtcAsAnOleTxTm: failed to set registry value";
    }
  }
  TraceFile(v0, v2, "com\\complus\\dtc\\dtc\\adme\\deployment.cpp", v1);
  v3 = -2147418113;
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800508b4  push    rbp
0x1800508b6  push    rbx
0x1800508b7  push    rsi
0x1800508b8  mov     rbp, rsp
0x1800508bb  sub     rsp, 50h
0x1800508bf  lea     rax, [rbp+dwDisposition]
0x1800508c3  mov     [rbp+hKey], 0
0x1800508cb  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x1800508d0  lea     rdx, aSoftwareClasse_1; "Software\\Classes\\OLETransactionManage"...
0x1800508d7  lea     rax, [rbp+hKey]
0x1800508db  mov     [rbp+arg_10], 0
0x1800508e3  mov     [rsp+50h+phkResult], rax; phkResult
0x1800508e8  mov     ebx, 0F003Fh
0x1800508ed  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800508f6  xor     r9d, r9d; lpClass
0x1800508f9  mov     [rsp+50h+samDesired], ebx; samDesired
0x1800508fd  xor     r8d, r8d; Reserved
0x180050900  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050907  mov     [rsp+50h+dwOptions], 0; dwOptions
0x18005090f  mov     [rbp+dwDisposition], 0
0x180050916  mov     [rbp+arg_18], 0
0x18005091e  call    cs:__imp_RegCreateKeyExA
0x180050924  test    eax, eax
0x180050926  jz      short loc_18005093A
0x180050928  mov     r9d, 0FBh
0x18005092e  lea     rdx, aInstalldtcasan_1; "InstallDtcAsAnOleTxTm: failed to create"...
0x180050935  jmp     loc_180050A38
0x18005093a  mov     rcx, [rbp+hKey]; hKey
0x18005093e  lea     rax, [rbp+dwDisposition]
0x180050942  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x180050947  lea     rsi, aMsdtc; "MSDTC"
0x18005094e  lea     rax, [rbp+arg_10]
0x180050952  xor     r9d, r9d; lpClass
0x180050955  mov     [rsp+50h+phkResult], rax; phkResult
0x18005095a  xor     r8d, r8d; Reserved
0x18005095d  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180050966  mov     rdx, rsi; lpSubKey
0x180050969  mov     [rsp+50h+samDesired], ebx; samDesired
0x18005096d  mov     [rsp+50h+dwOptions], 0; dwOptions
0x180050975  call    cs:__imp_RegCreateKeyExW
0x18005097b  test    eax, eax
0x18005097d  jz      short loc_180050991
0x18005097f  mov     r9d, 108h
0x180050985  lea     rdx, aInstalldtcasan_0; "InstallDtcAsAnOleTxTm: failed to create"...
0x18005098c  jmp     loc_180050A38
0x180050991  lea     r11, aMsdtcprxDll_0; "MSDTCPRX.DLL"
0x180050998  mov     edx, 0Dh; unsigned __int64
0x18005099d  mov     rcx, r11; char *
0x1800509a0  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x1800509a4  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800509a9  mov     ebx, eax
0x1800509ab  test    eax, eax
0x1800509ad  jns     short loc_1800509CC
0x1800509af  mov     r9d, 112h; unsigned int
0x1800509b5  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x1800509bc  lea     rdx, aInstalldtcasan; "InstallDtcAsAnOleTxTm: failed to initia"...
0x1800509c3  xor     ecx, ecx; int
0x1800509c5  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800509ca  jmp     short loc_180050A4B
0x1800509cc  mov     eax, dword ptr [rbp+arg_18]
0x1800509cf  lea     rdx, aDll; "DLL"
0x1800509d6  mov     rcx, [rbp+arg_10]; hKey
0x1800509da  inc     eax
0x1800509dc  mov     [rsp+50h+samDesired], eax; cbData
0x1800509e0  mov     r9d, 1; dwType
0x1800509e6  xor     r8d, r8d; Reserved
0x1800509e9  mov     qword ptr [rsp+50h+dwOptions], r11; lpData
0x1800509ee  call    cs:__imp_RegSetValueExA
0x1800509f4  test    eax, eax
0x1800509f6  jz      short loc_180050A00
0x1800509f8  mov     r9d, 11Dh
0x1800509fe  jmp     short loc_180050A31
0x180050a00  mov     rcx, [rbp+hKey]; hKey
0x180050a04  lea     rdx, aDefaulttm; "DefaultTM"
0x180050a0b  mov     [rsp+50h+samDesired], 0Ch; cbData
0x180050a13  mov     r9d, 1; dwType
0x180050a19  xor     r8d, r8d; Reserved
0x180050a1c  mov     qword ptr [rsp+50h+dwOptions], rsi; lpData
0x180050a21  call    cs:__imp_RegSetValueExW
0x180050a27  test    eax, eax
0x180050a29  jz      short loc_180050A4B
0x180050a2b  mov     r9d, 129h; unsigned int
0x180050a31  lea     rdx, aInstalldtcasan_2; "InstallDtcAsAnOleTxTm: failed to set re"...
0x180050a38  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\adme\\deploymen"...
0x180050a3f  mov     ecx, eax; int
0x180050a41  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180050a46  mov     ebx, 8000FFFFh
0x180050a4b  mov     rcx, [rbp+hKey]; hKey
0x180050a4f  test    rcx, rcx
0x180050a52  jz      short loc_180050A5A
0x180050a54  call    cs:__imp_RegCloseKey
0x180050a5a  mov     rcx, [rbp+arg_10]; hKey
0x180050a5e  test    rcx, rcx
0x180050a61  jz      short loc_180050A69
0x180050a63  call    cs:__imp_RegCloseKey
0x180050a69  mov     eax, ebx
0x180050a6b  add     rsp, 50h
0x180050a6f  pop     rsi
0x180050a70  pop     rbx
0x180050a71  pop     rbp
0x180050a72  retn
```
