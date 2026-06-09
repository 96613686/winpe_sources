# ReadDwordParameterValueFromAnyService(ushort const *,ushort const *,ulong)

- ea: `0x180026730`
- end: `0x180026863`
- name: `?ReadDwordParameterValueFromAnyService@@YAKPEBG0K@Z`
- size: `307`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180018ec0`
- `0x180026730`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026781`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026781`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026844`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800267fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800267fa`

## string_xrefs

- `0x1800267c8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x1800267a8`: `Opening registry key failed\n`
- `0x1800267ba`: `ReadDwordParameterValueFromAnyService`
- `0x180026824`: `Reading registry value failed\n`

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
0x180026730  mov     [rsp-8+arg_0], rbx
0x180026735  mov     [rsp-8+arg_8], rdi
0x18002673a  push    rbp
0x18002673b  mov     rbp, rsp
0x18002673e  sub     rsp, 40h
0x180026742  mov     rdi, rdx
0x180026745  mov     [rbp+hKey], 0
0x18002674d  mov     rdx, rcx; lpSubKey
0x180026750  mov     [rbp+Type], 0
0x180026757  mov     ebx, r8d
0x18002675a  mov     [rbp+Data], 0
0x180026761  lea     rax, [rbp+hKey]
0x180026765  mov     [rbp+cbData], 4
0x18002676c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026773  mov     [rsp+40h+phkResult], rax; phkResult
0x180026778  mov     r9d, 20019h; samDesired
0x18002677e  xor     r8d, r8d; ulOptions
0x180026781  call    cs:__imp_RegOpenKeyExW
0x180026788  nop     dword ptr [rax+rax+00h]
0x18002678d  test    eax, eax
0x18002678f  jz      short loc_1800267DA
0x180026791  jle     short loc_18002679B
0x180026793  movzx   eax, ax
0x180026796  or      eax, 80070000h
0x18002679b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800267a2  jz      loc_18002683B
0x1800267a8  lea     rcx, aOpeningRegistr; "Opening registry key failed\n"
0x1800267af  mov     r8d, 98h; unsigned int
0x1800267b5  mov     [rsp+40h+lpcbData], rcx; char *
0x1800267ba  lea     r9, aReaddwordparam_0; "ReadDwordParameterValueFromAnyService"
0x1800267c1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800267c8  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800267cf  mov     dword ptr [rsp+40h+phkResult], eax; dwMessageId
0x1800267d3  call    PuDbgPrintError
0x1800267d8  jmp     short loc_18002683B
0x1800267da  mov     rcx, [rbp+hKey]; hKey
0x1800267de  lea     rax, [rbp+cbData]
0x1800267e2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800267e7  lea     r9, [rbp+Type]; lpType
0x1800267eb  lea     rax, [rbp+Data]
0x1800267ef  xor     r8d, r8d; lpReserved
0x1800267f2  mov     rdx, rdi; lpValueName
0x1800267f5  mov     [rsp+40h+phkResult], rax; lpData
0x1800267fa  call    cs:__imp_RegQueryValueExW
0x180026801  nop     dword ptr [rax+rax+00h]
0x180026806  test    eax, eax
0x180026808  jz      short loc_180026833
0x18002680a  jle     short loc_180026814
0x18002680c  movzx   eax, ax
0x18002680f  or      eax, 80070000h
0x180026814  cmp     eax, 80070002h
0x180026819  jz      short loc_18002683B
0x18002681b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180026822  jz      short loc_18002683B
0x180026824  lea     rcx, aReadingRegistr; "Reading registry value failed\n"
0x18002682b  mov     r8d, 0B7h
0x180026831  jmp     short loc_1800267B5
0x180026833  cmp     [rbp+Type], 4
0x180026837  cmovz   ebx, [rbp+Data]
0x18002683b  mov     rcx, [rbp+hKey]; hKey
0x18002683f  test    rcx, rcx
0x180026842  jz      short loc_180026850
0x180026844  call    cs:__imp_RegCloseKey
0x18002684b  nop     dword ptr [rax+rax+00h]
0x180026850  mov     rdi, [rsp+40h+arg_8]
0x180026855  mov     eax, ebx
0x180026857  mov     rbx, [rsp+40h+arg_0]
0x18002685c  add     rsp, 40h
0x180026860  pop     rbp
0x180026861  retn
```
