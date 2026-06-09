# ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)

- ea: `0x180024c60`
- end: `0x180024d80`
- name: `?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z`
- size: `288`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800180c0`
- `0x180024c60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024cb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024cb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024d68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024d24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024d24`

## string_xrefs

- `0x180024cf2`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x180024cd2`: `Opening registry key failed\n`
- `0x180024ce4`: `ReadDwordParameterValueFromAnyService`
- `0x180024d48`: `Reading registry value failed\n`

## pseudocode

```c
__int64 __fastcall ReadDwordParameterValueFromAnyService(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int a3)
{
  signed int v5; // eax
  char *v6; // rcx
  unsigned int v7; // r8d
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  if ( v5 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      v6 = "Opening registry key failed\n";
      v7 = 152;
LABEL_6:
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
        v7,
        "ReadDwordParameterValueFromAnyService",
        v5,
        v6,
        cbData);
    }
  }
  else
  {
    v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v5 )
    {
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      if ( v5 != -2147024894 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        v6 = "Reading registry value failed\n";
        v7 = 183;
        goto LABEL_6;
      }
    }
    else if ( Type == 4 )
    {
      a3 = Data;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a3;
}

```

## disassembly

```asm
0x180024c60  mov     [rsp-8+arg_0], rbx
0x180024c65  mov     [rsp-8+arg_8], rdi
0x180024c6a  push    rbp
0x180024c6b  mov     rbp, rsp
0x180024c6e  sub     rsp, 40h
0x180024c72  mov     rdi, rdx
0x180024c75  mov     [rbp+hKey], 0
0x180024c7d  mov     rdx, rcx; lpSubKey
0x180024c80  mov     [rbp+Type], 0
0x180024c87  mov     ebx, r8d
0x180024c8a  mov     [rbp+Data], 0
0x180024c91  lea     rax, [rbp+hKey]
0x180024c95  mov     [rbp+cbData], 4
0x180024c9c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024ca3  mov     [rsp+40h+phkResult], rax; phkResult
0x180024ca8  mov     r9d, 20019h; samDesired
0x180024cae  xor     r8d, r8d; ulOptions
0x180024cb1  call    cs:__imp_RegOpenKeyExW
0x180024cb7  test    eax, eax
0x180024cb9  jz      short loc_180024D04
0x180024cbb  jle     short loc_180024CC5
0x180024cbd  movzx   eax, ax
0x180024cc0  or      eax, 80070000h
0x180024cc5  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180024ccc  jz      loc_180024D5F
0x180024cd2  lea     rcx, aOpeningRegistr; "Opening registry key failed\n"
0x180024cd9  mov     r8d, 98h; unsigned int
0x180024cdf  mov     [rsp+40h+lpcbData], rcx; char *
0x180024ce4  lea     r9, aReaddwordparam_0; "ReadDwordParameterValueFromAnyService"
0x180024ceb  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180024cf2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180024cf9  mov     dword ptr [rsp+40h+phkResult], eax; dwMessageId
0x180024cfd  call    PuDbgPrintError
0x180024d02  jmp     short loc_180024D5F
0x180024d04  mov     rcx, [rbp+hKey]; hKey
0x180024d08  lea     rax, [rbp+cbData]
0x180024d0c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180024d11  lea     r9, [rbp+Type]; lpType
0x180024d15  lea     rax, [rbp+Data]
0x180024d19  xor     r8d, r8d; lpReserved
0x180024d1c  mov     rdx, rdi; lpValueName
0x180024d1f  mov     [rsp+40h+phkResult], rax; lpData
0x180024d24  call    cs:__imp_RegQueryValueExW
0x180024d2a  test    eax, eax
0x180024d2c  jz      short loc_180024D57
0x180024d2e  jle     short loc_180024D38
0x180024d30  movzx   eax, ax
0x180024d33  or      eax, 80070000h
0x180024d38  cmp     eax, 80070002h
0x180024d3d  jz      short loc_180024D5F
0x180024d3f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180024d46  jz      short loc_180024D5F
0x180024d48  lea     rcx, aReadingRegistr; "Reading registry value failed\n"
0x180024d4f  mov     r8d, 0B7h
0x180024d55  jmp     short loc_180024CDF
0x180024d57  cmp     [rbp+Type], 4
0x180024d5b  cmovz   ebx, [rbp+Data]
0x180024d5f  mov     rcx, [rbp+hKey]; hKey
0x180024d63  test    rcx, rcx
0x180024d66  jz      short loc_180024D6E
0x180024d68  call    cs:__imp_RegCloseKey
0x180024d6e  mov     rdi, [rsp+40h+arg_8]
0x180024d73  mov     eax, ebx
0x180024d75  mov     rbx, [rsp+40h+arg_0]
0x180024d7a  add     rsp, 40h
0x180024d7e  pop     rbp
0x180024d7f  retn
```
