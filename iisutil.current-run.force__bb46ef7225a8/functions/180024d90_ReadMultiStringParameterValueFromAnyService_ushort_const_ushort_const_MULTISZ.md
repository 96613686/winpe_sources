# ReadMultiStringParameterValueFromAnyService(ushort const *,ushort const *,MULTISZ *)

- ea: `0x180024d90`
- end: `0x180024f93`
- name: `?ReadMultiStringParameterValueFromAnyService@@YAJPEBG0PEAVMULTISZ@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, struct MULTISZ *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002470`
- `0x180002b60`
- `0x1800180c0`
- `0x1800197d0`
- `0x180024d90`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024e05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024f5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024e45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024e45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024f09`

## string_xrefs

- `0x180024e8d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x180024e6f`: `Inetinfo: Failed reading registry value \n`
- `0x180024e86`: `ReadMultiStringParameterValueFromAnyService`

## pseudocode

```c
__int64 __fastcall ReadMultiStringParameterValueFromAnyService(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        struct MULTISZ *this)
{
  LSTATUS v5; // eax
  DWORD v6; // edi
  LSTATUS v7; // eax
  unsigned int v8; // r8d
  LSTATUS v9; // eax
  int v10; // ebx
  DWORD cbData; // [rsp+30h] [rbp-50h] BYREF
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v15[4]; // [rsp+40h] [rbp-40h] BYREF
  LPBYTE lpData; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+68h] [rbp-18h]
  __int16 v18; // [rsp+6Ch] [rbp-14h]

  hKey = 0;
  lpData = (LPBYTE)v15;
  Type = 0;
  cbData = 0;
  v15[0] = 0;
  v17 = 32;
  v18 = 256;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_24;
  }
  v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v6 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      v8 = 490;
LABEL_9:
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
        v8,
        "ReadMultiStringParameterValueFromAnyService",
        v6,
        "Inetinfo: Failed reading registry value \n",
        cbData);
    }
  }
  else if ( Type == 7 )
  {
    if ( !BUFFER::Resize((BUFFER *)v15, cbData) )
    {
      v6 = -2147467259;
      goto LABEL_24;
    }
    v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        v8 = 530;
        goto LABEL_9;
      }
    }
    else
    {
      v10 = 0;
      if ( !(unsigned int)MULTISZ::Copy(this, (const unsigned __int16 *)lpData, cbData) )
        v10 = -2147467259;
      v6 = v10;
    }
  }
  else
  {
    v6 = -2147418113;
    if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
        0x1F8u,
        "ReadMultiStringParameterValueFromAnyService",
        0x8000FFFF,
        "Key was not of string type \n",
        cbData);
  }
LABEL_24:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v15);
  return v6;
}

```

## disassembly

```asm
0x180024d90  mov     [rsp-18h+arg_18], rbx
0x180024d95  push    rbp
0x180024d96  push    rsi
0x180024d97  push    rdi
0x180024d98  mov     rbp, rsp
0x180024d9b  sub     rsp, 80h
0x180024da2  mov     rax, cs:__security_cookie
0x180024da9  xor     rax, rsp
0x180024dac  mov     [rbp+var_10], rax
0x180024db0  lea     rax, [rbp+var_40]
0x180024db4  mov     [rbp+hKey], 0
0x180024dbc  mov     [rbp+lpData], rax
0x180024dc0  mov     rbx, rdx
0x180024dc3  lea     rax, [rbp+hKey]
0x180024dc7  mov     [rbp+Type], 0
0x180024dce  mov     rsi, r8
0x180024dd1  mov     [rsp+80h+phkResult], rax; phkResult
0x180024dd6  mov     rdx, rcx; lpSubKey
0x180024dd9  mov     [rbp+cbData], 0
0x180024de0  mov     r9d, 20019h; samDesired
0x180024de6  mov     [rbp+var_40], 0
0x180024dee  xor     r8d, r8d; ulOptions
0x180024df1  mov     [rbp+var_18], 20h ; ' '
0x180024df8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024dff  mov     [rbp+var_14], 100h
0x180024e05  call    cs:__imp_RegOpenKeyExW
0x180024e0b  mov     edi, eax
0x180024e0d  test    eax, eax
0x180024e0f  jz      short loc_180024E25
0x180024e11  jle     loc_180024F52
0x180024e17  movzx   edi, ax
0x180024e1a  or      edi, 80070000h
0x180024e20  jmp     loc_180024F52
0x180024e25  mov     rcx, [rbp+hKey]; hKey
0x180024e29  lea     rax, [rbp+cbData]
0x180024e2d  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180024e32  lea     r9, [rbp+Type]; lpType
0x180024e36  xor     r8d, r8d; lpReserved
0x180024e39  mov     [rsp+80h+phkResult], 0; lpData
0x180024e42  mov     rdx, rbx; lpValueName
0x180024e45  call    cs:__imp_RegQueryValueExW
0x180024e4b  mov     edi, eax
0x180024e4d  test    eax, eax
0x180024e4f  jz      short loc_180024E9E
0x180024e51  jle     short loc_180024E5C
0x180024e53  movzx   edi, ax
0x180024e56  or      edi, 80070000h
0x180024e5c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180024e63  jz      loc_180024F52
0x180024e69  mov     r8d, 1EAh; unsigned int
0x180024e6f  lea     rax, aInetinfoFailed; "Inetinfo: Failed reading registry value"...
0x180024e76  mov     [rsp+80h+lpcbData], rax; char *
0x180024e7b  mov     dword ptr [rsp+80h+phkResult], edi; dwMessageId
0x180024e7f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180024e86  lea     r9, aReadmultistrin_0; "ReadMultiStringParameterValueFromAnySer"...
0x180024e8d  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180024e94  call    PuDbgPrintError
0x180024e99  jmp     loc_180024F52
0x180024e9e  cmp     [rbp+Type], 7
0x180024ea2  jz      short loc_180024ED2
0x180024ea4  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180024eab  mov     edi, 8000FFFFh
0x180024eb0  jz      loc_180024F52
0x180024eb6  lea     rax, aKeyWasNotOfStr; "Key was not of string type \n"
0x180024ebd  mov     r8d, 1F8h
0x180024ec3  mov     [rsp+80h+lpcbData], rax
0x180024ec8  mov     dword ptr [rsp+80h+phkResult], 8000FFFFh
0x180024ed0  jmp     short loc_180024E7F
0x180024ed2  mov     edx, [rbp+cbData]; unsigned int
0x180024ed5  lea     rcx, [rbp+var_40]; this
0x180024ed9  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024ede  test    al, al
0x180024ee0  jnz     short loc_180024EE9
0x180024ee2  mov     edi, 80004005h
0x180024ee7  jmp     short loc_180024F52
0x180024ee9  mov     rcx, [rbp+hKey]; hKey
0x180024eed  lea     rax, [rbp+cbData]
0x180024ef1  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180024ef6  lea     r9, [rbp+Type]; lpType
0x180024efa  mov     rax, [rbp+lpData]
0x180024efe  xor     r8d, r8d; lpReserved
0x180024f01  mov     rdx, rbx; lpValueName
0x180024f04  mov     [rsp+80h+phkResult], rax; lpData
0x180024f09  call    cs:__imp_RegQueryValueExW
0x180024f0f  mov     edi, eax
0x180024f11  test    eax, eax
0x180024f13  jz      short loc_180024F34
0x180024f15  jle     short loc_180024F20
0x180024f17  movzx   edi, ax
0x180024f1a  or      edi, 80070000h
0x180024f20  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180024f27  jz      short loc_180024F52
0x180024f29  mov     r8d, 212h
0x180024f2f  jmp     loc_180024E6F
0x180024f34  mov     r8d, [rbp+cbData]; unsigned int
0x180024f38  mov     rcx, rsi; this
0x180024f3b  mov     rdx, [rbp+lpData]; unsigned __int16 *
0x180024f3f  xor     ebx, ebx
0x180024f41  call    ?Copy@MULTISZ@@QEAAHPEBGK@Z; MULTISZ::Copy(ushort const *,ulong)
0x180024f46  mov     edi, 80004005h
0x180024f4b  test    eax, eax
0x180024f4d  cmovz   ebx, edi
0x180024f50  mov     edi, ebx
0x180024f52  mov     rcx, [rbp+hKey]; hKey
0x180024f56  test    rcx, rcx
0x180024f59  jz      short loc_180024F69
0x180024f5b  call    cs:__imp_RegCloseKey
0x180024f61  mov     [rbp+hKey], 0
0x180024f69  lea     rcx, [rbp+var_40]; this
0x180024f6d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180024f72  mov     eax, edi
0x180024f74  mov     rcx, [rbp+var_10]
0x180024f78  xor     rcx, rsp; StackCookie
0x180024f7b  call    __security_check_cookie
0x180024f80  mov     rbx, [rsp+80h+arg_18]
0x180024f88  add     rsp, 80h
0x180024f8f  pop     rdi
0x180024f90  pop     rsi
0x180024f91  pop     rbp
0x180024f92  retn
```
