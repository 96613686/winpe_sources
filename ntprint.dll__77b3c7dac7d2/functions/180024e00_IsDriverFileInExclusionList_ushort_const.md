# IsDriverFileInExclusionList(ushort const *)

- ea: `0x180024e00`
- end: `0x180024f6a`
- name: `?IsDriverFileInExclusionList@@YAHPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800281a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x180024764`
- `0x180024e00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f09`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024edc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024edc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024f47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024f47`

## string_xrefs

- `0x180024f2e`: `Error accessing the driver exclusion list! Error %d`

## pseudocode

```c
__int64 __fastcall IsDriverFileInExclusionList(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  WCHAR *v3; // rdi
  unsigned int v4; // eax
  unsigned int FileHash; // eax
  LPCWSTR lpValue; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pvData[528]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  v3 = 0;
  hkey = 0;
  lpValue = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\Driver\\ExclusionList",
         0,
         0x20019u,
         &hkey);
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      ClassInstallerTelemetry::WriteDbgTraceError("IsDriverFileInExclusionList", L"Driver exclusion list is not set!");
      return v2;
    }
    ClassInstallerTelemetry::WriteDbgTraceError(
      "IsDriverFileInExclusionList",
      L"Error accessing the driver exclusion list! Error %d",
      v4);
    v2 = 1;
  }
  else
  {
    FileHash = GetFileHash(a1, (unsigned __int16 **)&lpValue);
    v3 = (WCHAR *)lpValue;
    if ( FileHash )
    {
      ClassInstallerTelemetry::WriteDbgTraceError(
        "IsDriverFileInExclusionList",
        L"Failed to get the hash for the driver file (%ws)! Error %d",
        a1,
        FileHash);
      v2 = 1;
    }
    else
    {
      memset_0(pvData, 0, 0x208u);
      LODWORD(lpValue) = 520;
      if ( !RegGetValueW(hkey, 0, v3, 2u, 0, pvData, (LPDWORD)&lpValue) )
      {
        v2 = 1;
        ClassInstallerTelemetry::WriteDbgTraceError(
          "IsDriverFileInExclusionList",
          L"Driver with hash %ws is in the exclusion list and is not valid! Offending file: %ws",
          v3,
          pvData);
      }
    }
    RegCloseKey(hkey);
  }
  if ( v3 )
    LocalFree(v3);
  return v2;
}

```

## disassembly

```asm
0x180024e00  push    rbp
0x180024e02  push    rbx
0x180024e03  push    rsi
0x180024e04  push    rdi
0x180024e05  lea     rbp, [rsp-178h]
0x180024e0d  sub     rsp, 278h
0x180024e14  mov     rax, cs:__security_cookie
0x180024e1b  xor     rax, rsp
0x180024e1e  mov     [rbp+190h+var_30], rax
0x180024e25  mov     rsi, rcx
0x180024e28  lea     rax, [rsp+290h+hkey]
0x180024e2d  xor     ebx, ebx
0x180024e2f  mov     [rsp+290h+phkResult], rax; phkResult
0x180024e34  xor     edi, edi
0x180024e36  mov     [rsp+290h+hkey], rbx
0x180024e3b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024e42  mov     [rsp+290h+lpValue], rdi
0x180024e47  mov     r9d, 20019h; samDesired
0x180024e4d  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x180024e54  xor     r8d, r8d; ulOptions
0x180024e57  call    cs:__imp_RegOpenKeyExW
0x180024e5d  test    eax, eax
0x180024e5f  jnz     loc_180024F11
0x180024e65  lea     rdx, [rsp+290h+lpValue]; unsigned __int16 **
0x180024e6a  mov     rcx, rsi; unsigned __int16 *
0x180024e6d  call    ?GetFileHash@@YAKPEBGPEAPEAG@Z; GetFileHash(ushort const *,ushort * *)
0x180024e72  mov     rdi, [rsp+290h+lpValue]
0x180024e77  test    eax, eax
0x180024e79  jz      short loc_180024E9B
0x180024e7b  mov     r9d, eax
0x180024e7e  lea     rdx, aFailedToGetThe; "Failed to get the hash for the driver f"...
0x180024e85  mov     r8, rsi
0x180024e88  lea     rcx, aIsdriverfilein; "IsDriverFileInExclusionList"
0x180024e8f  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024e94  mov     ebx, 1
0x180024e99  jmp     short loc_180024F04
0x180024e9b  mov     esi, 208h
0x180024ea0  lea     rcx, [rsp+290h+var_240]; void *
0x180024ea5  mov     r8d, esi; Size
0x180024ea8  xor     edx, edx; Val
0x180024eaa  call    memset_0
0x180024eaf  mov     rcx, [rsp+290h+hkey]; hkey
0x180024eb4  lea     rax, [rsp+290h+lpValue]
0x180024eb9  mov     [rsp+290h+pcbData], rax; pcbData
0x180024ebe  mov     r9d, 2; dwFlags
0x180024ec4  lea     rax, [rsp+290h+var_240]
0x180024ec9  mov     dword ptr [rsp+290h+lpValue], esi
0x180024ecd  mov     [rsp+290h+pvData], rax; pvData
0x180024ed2  mov     r8, rdi; lpValue
0x180024ed5  xor     edx, edx; lpSubKey
0x180024ed7  mov     [rsp+290h+phkResult], rbx; pdwType
0x180024edc  call    cs:__imp_RegGetValueW
0x180024ee2  test    eax, eax
0x180024ee4  jnz     short loc_180024F04
0x180024ee6  lea     r9, [rsp+290h+var_240]
0x180024eeb  mov     r8, rdi
0x180024eee  lea     rdx, aDriverWithHash; "Driver with hash %ws is in the exclusio"...
0x180024ef5  lea     rcx, aIsdriverfilein; "IsDriverFileInExclusionList"
0x180024efc  lea     ebx, [rax+1]
0x180024eff  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024f04  mov     rcx, [rsp+290h+hkey]; hKey
0x180024f09  call    cs:__imp_RegCloseKey
0x180024f0f  jmp     short loc_180024F3F
0x180024f11  lea     rcx, aIsdriverfilein; "IsDriverFileInExclusionList"
0x180024f18  cmp     eax, 2
0x180024f1b  jnz     short loc_180024F2B
0x180024f1d  lea     rdx, aDriverExclusio; "Driver exclusion list is not set!"
0x180024f24  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024f29  jmp     short loc_180024F4D
0x180024f2b  mov     r8d, eax
0x180024f2e  lea     rdx, aErrorAccessing; "Error accessing the driver exclusion li"...
0x180024f35  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024f3a  mov     ebx, 1
0x180024f3f  test    rdi, rdi
0x180024f42  jz      short loc_180024F4D
0x180024f44  mov     rcx, rdi; hMem
0x180024f47  call    cs:__imp_LocalFree
0x180024f4d  mov     eax, ebx
0x180024f4f  mov     rcx, [rbp+190h+var_30]
0x180024f56  xor     rcx, rsp; StackCookie
0x180024f59  call    __security_check_cookie
0x180024f5e  add     rsp, 278h
0x180024f65  pop     rdi
0x180024f66  pop     rsi
0x180024f67  pop     rbx
0x180024f68  pop     rbp
0x180024f69  retn
```
