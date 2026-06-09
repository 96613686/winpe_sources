# ReadMultiStringParameterValueFromAnyService(ushort const *,ushort const *,MULTISZ *)

- ea: `0x180026870`
- end: `0x180026a8c`
- name: `?ReadMultiStringParameterValueFromAnyService@@YAJPEBG0PEAVMULTISZ@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, struct MULTISZ *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180002da0`
- `0x1800034f0`
- `0x180018ec0`
- `0x18001a630`
- `0x180026870`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800268e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800268e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026a4d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026a4d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002692b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800269f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002692b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800269f5`

## string_xrefs

- `0x180026979`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x18002695b`: `Inetinfo: Failed reading registry value \n`
- `0x180026972`: `ReadMultiStringParameterValueFromAnyService`

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
0x180026870  mov     [rsp-18h+arg_18], rbx
0x180026875  push    rbp
0x180026876  push    rsi
0x180026877  push    rdi
0x180026878  mov     rbp, rsp
0x18002687b  sub     rsp, 80h
0x180026882  mov     rax, cs:__security_cookie
0x180026889  xor     rax, rsp
0x18002688c  mov     [rbp+var_10], rax
0x180026890  lea     rax, [rbp+var_40]
0x180026894  mov     [rbp+hKey], 0
0x18002689c  mov     [rbp+lpData], rax
0x1800268a0  mov     rbx, rdx
0x1800268a3  lea     rax, [rbp+hKey]
0x1800268a7  mov     [rbp+Type], 0
0x1800268ae  mov     rsi, r8
0x1800268b1  mov     [rsp+80h+phkResult], rax; phkResult
0x1800268b6  mov     rdx, rcx; lpSubKey
0x1800268b9  mov     [rbp+cbData], 0
0x1800268c0  mov     r9d, 20019h; samDesired
0x1800268c6  mov     [rbp+var_40], 0
0x1800268ce  xor     r8d, r8d; ulOptions
0x1800268d1  mov     [rbp+var_18], 20h ; ' '
0x1800268d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800268df  mov     [rbp+var_14], 100h
0x1800268e5  call    cs:__imp_RegOpenKeyExW
0x1800268ec  nop     dword ptr [rax+rax+00h]
0x1800268f1  mov     edi, eax
0x1800268f3  test    eax, eax
0x1800268f5  jz      short loc_18002690B
0x1800268f7  jle     loc_180026A44
0x1800268fd  movzx   edi, ax
0x180026900  or      edi, 80070000h
0x180026906  jmp     loc_180026A44
0x18002690b  mov     rcx, [rbp+hKey]; hKey
0x18002690f  lea     rax, [rbp+cbData]
0x180026913  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180026918  lea     r9, [rbp+Type]; lpType
0x18002691c  xor     r8d, r8d; lpReserved
0x18002691f  mov     [rsp+80h+phkResult], 0; lpData
0x180026928  mov     rdx, rbx; lpValueName
0x18002692b  call    cs:__imp_RegQueryValueExW
0x180026932  nop     dword ptr [rax+rax+00h]
0x180026937  mov     edi, eax
0x180026939  test    eax, eax
0x18002693b  jz      short loc_18002698A
0x18002693d  jle     short loc_180026948
0x18002693f  movzx   edi, ax
0x180026942  or      edi, 80070000h
0x180026948  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002694f  jz      loc_180026A44
0x180026955  mov     r8d, 1EAh; unsigned int
0x18002695b  lea     rax, aInetinfoFailed; "Inetinfo: Failed reading registry value"...
0x180026962  mov     [rsp+80h+lpcbData], rax; char *
0x180026967  mov     dword ptr [rsp+80h+phkResult], edi; dwMessageId
0x18002696b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180026972  lea     r9, aReadmultistrin_0; "ReadMultiStringParameterValueFromAnySer"...
0x180026979  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026980  call    PuDbgPrintError
0x180026985  jmp     loc_180026A44
0x18002698a  cmp     [rbp+Type], 7
0x18002698e  jz      short loc_1800269BE
0x180026990  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180026997  mov     edi, 8000FFFFh
0x18002699c  jz      loc_180026A44
0x1800269a2  lea     rax, aKeyWasNotOfStr; "Key was not of string type \n"
0x1800269a9  mov     r8d, 1F8h
0x1800269af  mov     [rsp+80h+lpcbData], rax
0x1800269b4  mov     dword ptr [rsp+80h+phkResult], 8000FFFFh
0x1800269bc  jmp     short loc_18002696B
0x1800269be  mov     edx, [rbp+cbData]; unsigned int
0x1800269c1  lea     rcx, [rbp+var_40]; this
0x1800269c5  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800269ca  test    al, al
0x1800269cc  jnz     short loc_1800269D5
0x1800269ce  mov     edi, 80004005h
0x1800269d3  jmp     short loc_180026A44
0x1800269d5  mov     rcx, [rbp+hKey]; hKey
0x1800269d9  lea     rax, [rbp+cbData]
0x1800269dd  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800269e2  lea     r9, [rbp+Type]; lpType
0x1800269e6  mov     rax, [rbp+lpData]
0x1800269ea  xor     r8d, r8d; lpReserved
0x1800269ed  mov     rdx, rbx; lpValueName
0x1800269f0  mov     [rsp+80h+phkResult], rax; lpData
0x1800269f5  call    cs:__imp_RegQueryValueExW
0x1800269fc  nop     dword ptr [rax+rax+00h]
0x180026a01  mov     edi, eax
0x180026a03  test    eax, eax
0x180026a05  jz      short loc_180026A26
0x180026a07  jle     short loc_180026A12
0x180026a09  movzx   edi, ax
0x180026a0c  or      edi, 80070000h
0x180026a12  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180026a19  jz      short loc_180026A44
0x180026a1b  mov     r8d, 212h
0x180026a21  jmp     loc_18002695B
0x180026a26  mov     r8d, [rbp+cbData]; unsigned int
0x180026a2a  mov     rcx, rsi; this
0x180026a2d  mov     rdx, [rbp+lpData]; unsigned __int16 *
0x180026a31  xor     ebx, ebx
0x180026a33  call    ?Copy@MULTISZ@@QEAAHPEBGK@Z; MULTISZ::Copy(ushort const *,ulong)
0x180026a38  mov     edi, 80004005h
0x180026a3d  test    eax, eax
0x180026a3f  cmovz   ebx, edi
0x180026a42  mov     edi, ebx
0x180026a44  mov     rcx, [rbp+hKey]; hKey
0x180026a48  test    rcx, rcx
0x180026a4b  jz      short loc_180026A61
0x180026a4d  call    cs:__imp_RegCloseKey
0x180026a54  nop     dword ptr [rax+rax+00h]
0x180026a59  mov     [rbp+hKey], 0
0x180026a61  lea     rcx, [rbp+var_40]; this
0x180026a65  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026a6a  mov     eax, edi
0x180026a6c  mov     rcx, [rbp+var_10]
0x180026a70  xor     rcx, rsp; StackCookie
0x180026a73  call    __security_check_cookie
0x180026a78  mov     rbx, [rsp+80h+arg_18]
0x180026a80  add     rsp, 80h
0x180026a87  pop     rdi
0x180026a88  pop     rsi
0x180026a89  pop     rbp
0x180026a8a  retn
```
