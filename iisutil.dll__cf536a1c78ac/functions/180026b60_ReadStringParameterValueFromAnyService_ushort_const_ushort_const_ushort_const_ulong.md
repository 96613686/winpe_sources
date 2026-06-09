# ReadStringParameterValueFromAnyService(ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x180026b60`
- end: `0x180026c98`
- name: `?ReadStringParameterValueFromAnyService@@YAJPEBG00PEAK@Z`
- size: `312`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180018ec0`
- `0x180026b60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ba0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026ba0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026c80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026be0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026be0`

## string_xrefs

- `0x180026c6a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x180026c0f`: `Inetinfo: Failed reading registry value \n`
- `0x180026c63`: `ReadStringParameterValueFromAnyService`

## pseudocode

```c
__int64 __fastcall ReadStringParameterValueFromAnyService(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        LPBYTE lpData,
        LPDWORD lpcbData)
{
  LSTATUS v7; // eax
  DWORD v8; // ebx
  LSTATUS v9; // eax
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF

  hKey = 0;
  Type = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, lpcbData);
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      else
        v8 = v9;
      if ( v9 != 234 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
          0x180u,
          "ReadStringParameterValueFromAnyService",
          v8,
          "Inetinfo: Failed reading registry value \n",
          Type);
    }
    else
    {
      v8 = 0;
      if ( Type - 1 > 1 )
      {
        v8 = -2147418113;
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          PuDbgPrintError(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
            0x18Fu,
            "ReadStringParameterValueFromAnyService",
            0x8000FFFF,
            "Key was not of string type \n",
            Type);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180026b60  push    rbx
0x180026b62  push    rbp
0x180026b63  push    rsi
0x180026b64  push    rdi
0x180026b65  sub     rsp, 48h
0x180026b69  mov     rbp, rdx
0x180026b6c  mov     [rsp+68h+hKey], 0
0x180026b75  mov     rdx, rcx; lpSubKey
0x180026b78  mov     [rsp+68h+Type], 0; char
0x180026b80  mov     rdi, r9
0x180026b83  lea     rax, [rsp+68h+hKey]
0x180026b88  mov     rsi, r8
0x180026b8b  mov     [rsp+68h+phkResult], rax; phkResult
0x180026b90  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026b97  mov     r9d, 20019h; samDesired
0x180026b9d  xor     r8d, r8d; ulOptions
0x180026ba0  call    cs:__imp_RegOpenKeyExW
0x180026ba7  nop     dword ptr [rax+rax+00h]
0x180026bac  mov     ebx, eax
0x180026bae  test    eax, eax
0x180026bb0  jz      short loc_180026BC6
0x180026bb2  jle     loc_180026C76
0x180026bb8  movzx   ebx, ax
0x180026bbb  or      ebx, 80070000h
0x180026bc1  jmp     loc_180026C76
0x180026bc6  mov     rcx, [rsp+68h+hKey]; hKey
0x180026bcb  lea     r9, [rsp+68h+Type]; lpType
0x180026bd0  mov     [rsp+68h+lpcbData], rdi; lpcbData
0x180026bd5  xor     r8d, r8d; lpReserved
0x180026bd8  mov     rdx, rbp; lpValueName
0x180026bdb  mov     [rsp+68h+phkResult], rsi; lpData
0x180026be0  call    cs:__imp_RegQueryValueExW
0x180026be7  nop     dword ptr [rax+rax+00h]
0x180026bec  test    eax, eax
0x180026bee  jz      short loc_180026C27
0x180026bf0  jg      short loc_180026BF6
0x180026bf2  mov     ebx, eax
0x180026bf4  jmp     short loc_180026BFF
0x180026bf6  movzx   ebx, ax
0x180026bf9  or      ebx, 80070000h
0x180026bff  cmp     eax, 0EAh
0x180026c04  jz      short loc_180026C76
0x180026c06  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180026c0d  jz      short loc_180026C76
0x180026c0f  lea     rax, aInetinfoFailed; "Inetinfo: Failed reading registry value"...
0x180026c16  mov     r8d, 180h
0x180026c1c  mov     [rsp+68h+lpcbData], rax
0x180026c21  mov     dword ptr [rsp+68h+phkResult], ebx
0x180026c25  jmp     short loc_180026C5C
0x180026c27  mov     eax, [rsp+68h+Type]
0x180026c2b  xor     ebx, ebx
0x180026c2d  dec     eax
0x180026c2f  cmp     eax, 1
0x180026c32  jbe     short loc_180026C76
0x180026c34  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180026c3b  mov     ebx, 8000FFFFh
0x180026c40  jz      short loc_180026C76
0x180026c42  lea     rax, aKeyWasNotOfStr; "Key was not of string type \n"
0x180026c49  mov     r8d, 18Fh; unsigned int
0x180026c4f  mov     [rsp+68h+lpcbData], rax; char *
0x180026c54  mov     dword ptr [rsp+68h+phkResult], 8000FFFFh; dwMessageId
0x180026c5c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180026c63  lea     r9, aReadstringpara_0; "ReadStringParameterValueFromAnyService"
0x180026c6a  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026c71  call    PuDbgPrintError
0x180026c76  mov     rcx, [rsp+68h+hKey]; hKey
0x180026c7b  test    rcx, rcx
0x180026c7e  jz      short loc_180026C8C
0x180026c80  call    cs:__imp_RegCloseKey
0x180026c87  nop     dword ptr [rax+rax+00h]
0x180026c8c  mov     eax, ebx
0x180026c8e  add     rsp, 48h
0x180026c92  pop     rdi
0x180026c93  pop     rsi
0x180026c94  pop     rbp
0x180026c95  pop     rbx
0x180026c96  retn
```
