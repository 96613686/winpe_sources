# ReadStringParameterValueFromAnyService(ushort const *,ushort const *,ushort const *,ulong *)

- ea: `0x180025050`
- end: `0x180025175`
- name: `?ReadStringParameterValueFromAnyService@@YAJPEBG00PEAK@Z`
- size: `293`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800180c0`
- `0x180025050`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025090`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025090`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025164`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025164`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800250ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800250ca`

## string_xrefs

- `0x18002514e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x1800250f3`: `Inetinfo: Failed reading registry value \n`
- `0x180025147`: `ReadStringParameterValueFromAnyService`

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
0x180025050  push    rbx
0x180025052  push    rbp
0x180025053  push    rsi
0x180025054  push    rdi
0x180025055  sub     rsp, 48h
0x180025059  mov     rbp, rdx
0x18002505c  mov     [rsp+68h+hKey], 0
0x180025065  mov     rdx, rcx; lpSubKey
0x180025068  mov     [rsp+68h+Type], 0; char
0x180025070  mov     rdi, r9
0x180025073  lea     rax, [rsp+68h+hKey]
0x180025078  mov     rsi, r8
0x18002507b  mov     [rsp+68h+phkResult], rax; phkResult
0x180025080  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025087  mov     r9d, 20019h; samDesired
0x18002508d  xor     r8d, r8d; ulOptions
0x180025090  call    cs:__imp_RegOpenKeyExW
0x180025096  mov     ebx, eax
0x180025098  test    eax, eax
0x18002509a  jz      short loc_1800250B0
0x18002509c  jle     loc_18002515A
0x1800250a2  movzx   ebx, ax
0x1800250a5  or      ebx, 80070000h
0x1800250ab  jmp     loc_18002515A
0x1800250b0  mov     rcx, [rsp+68h+hKey]; hKey
0x1800250b5  lea     r9, [rsp+68h+Type]; lpType
0x1800250ba  mov     [rsp+68h+lpcbData], rdi; lpcbData
0x1800250bf  xor     r8d, r8d; lpReserved
0x1800250c2  mov     rdx, rbp; lpValueName
0x1800250c5  mov     [rsp+68h+phkResult], rsi; lpData
0x1800250ca  call    cs:__imp_RegQueryValueExW
0x1800250d0  test    eax, eax
0x1800250d2  jz      short loc_18002510B
0x1800250d4  jg      short loc_1800250DA
0x1800250d6  mov     ebx, eax
0x1800250d8  jmp     short loc_1800250E3
0x1800250da  movzx   ebx, ax
0x1800250dd  or      ebx, 80070000h
0x1800250e3  cmp     eax, 0EAh
0x1800250e8  jz      short loc_18002515A
0x1800250ea  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800250f1  jz      short loc_18002515A
0x1800250f3  lea     rax, aInetinfoFailed; "Inetinfo: Failed reading registry value"...
0x1800250fa  mov     r8d, 180h
0x180025100  mov     [rsp+68h+lpcbData], rax
0x180025105  mov     dword ptr [rsp+68h+phkResult], ebx
0x180025109  jmp     short loc_180025140
0x18002510b  mov     eax, [rsp+68h+Type]
0x18002510f  xor     ebx, ebx
0x180025111  dec     eax
0x180025113  cmp     eax, 1
0x180025116  jbe     short loc_18002515A
0x180025118  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002511f  mov     ebx, 8000FFFFh
0x180025124  jz      short loc_18002515A
0x180025126  lea     rax, aKeyWasNotOfStr; "Key was not of string type \n"
0x18002512d  mov     r8d, 18Fh; unsigned int
0x180025133  mov     [rsp+68h+lpcbData], rax; char *
0x180025138  mov     dword ptr [rsp+68h+phkResult], 8000FFFFh; dwMessageId
0x180025140  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180025147  lea     r9, aReadstringpara_0; "ReadStringParameterValueFromAnyService"
0x18002514e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180025155  call    PuDbgPrintError
0x18002515a  mov     rcx, [rsp+68h+hKey]; hKey
0x18002515f  test    rcx, rcx
0x180025162  jz      short loc_18002516A
0x180025164  call    cs:__imp_RegCloseKey
0x18002516a  mov     eax, ebx
0x18002516c  add     rsp, 48h
0x180025170  pop     rdi
0x180025171  pop     rsi
0x180025172  pop     rbp
0x180025173  pop     rbx
0x180025174  retn
```
