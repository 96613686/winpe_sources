# SetStringParameterValueInAnyService(ushort const *,ushort const *,ushort const *)

- ea: `0x180017c90`
- end: `0x180017da4`
- name: `?SetStringParameterValueInAnyService@@YAKPEBG00@Z`
- size: `276`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180017c90`
- `0x180018ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017d2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017cc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017cc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d8c`

## string_xrefs

- `0x180017d72`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x180017d64`: `SetStringParameterValueInAnyService`
- `0x180017cee`: `Openning registry key for write failed\n`

## pseudocode

```c
__int64 __fastcall SetStringParameterValueInAnyService(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  char *v7; // rcx
  unsigned int v8; // r8d
  __int64 v9; // rax
  char v11; // [rsp+30h] [rbp-28h]
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
      goto LABEL_14;
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v7 = "Openning registry key for write failed\n";
    v8 = 264;
    goto LABEL_13;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&lpData[2 * v9] );
  v5 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v9 + 2);
  v6 = v5;
  if ( v5 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
  {
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v7 = "Failed writing string value\n";
    v8 = 288;
LABEL_13:
    PuDbgPrintError(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
      v8,
      "SetStringParameterValueInAnyService",
      v5,
      v7,
      v11);
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180017c90  push    rbx
0x180017c92  push    rbp
0x180017c93  push    rsi
0x180017c94  push    rdi
0x180017c95  sub     rsp, 38h
0x180017c99  mov     rsi, rdx
0x180017c9c  lea     rax, [rsp+58h+hKey]
0x180017ca1  mov     rdx, rcx; lpSubKey
0x180017ca4  mov     [rsp+58h+phkResult], rax; phkResult
0x180017ca9  mov     rdi, r8
0x180017cac  xor     ebp, ebp
0x180017cae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017cb5  mov     [rsp+58h+hKey], rbp
0x180017cba  mov     r9d, 20006h; samDesired
0x180017cc0  xor     r8d, r8d; ulOptions
0x180017cc3  call    cs:__imp_RegOpenKeyExW
0x180017cca  nop     dword ptr [rax+rax+00h]
0x180017ccf  mov     ebx, eax
0x180017cd1  test    eax, eax
0x180017cd3  jz      short loc_180017CFD
0x180017cd5  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017cdc  jz      loc_180017D82
0x180017ce2  test    eax, eax
0x180017ce4  jle     short loc_180017CEE
0x180017ce6  movzx   eax, ax
0x180017ce9  or      eax, 80070000h
0x180017cee  lea     rcx, aOpenningRegist; "Openning registry key for write failed"...
0x180017cf5  mov     r8d, 108h
0x180017cfb  jmp     short loc_180017D5F
0x180017cfd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017d01  inc     rax
0x180017d04  cmp     [rdi+rax*2], bp
0x180017d08  jnz     short loc_180017D01
0x180017d0a  mov     rcx, [rsp+58h+hKey]; hKey
0x180017d0f  lea     eax, ds:2[rax*2]
0x180017d16  mov     [rsp+58h+cbData], eax; cbData
0x180017d1a  mov     r9d, 1; dwType
0x180017d20  xor     r8d, r8d; Reserved
0x180017d23  mov     [rsp+58h+phkResult], rdi; lpData
0x180017d28  mov     rdx, rsi; lpValueName
0x180017d2b  call    cs:__imp_RegSetValueExW
0x180017d32  nop     dword ptr [rax+rax+00h]
0x180017d37  mov     ebx, eax
0x180017d39  test    eax, eax
0x180017d3b  jz      short loc_180017D82
0x180017d3d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017d44  jz      short loc_180017D82
0x180017d46  test    eax, eax
0x180017d48  jle     short loc_180017D52
0x180017d4a  movzx   eax, ax
0x180017d4d  or      eax, 80070000h
0x180017d52  lea     rcx, aFailedWritingS; "Failed writing string value\n"
0x180017d59  mov     r8d, 120h; unsigned int
0x180017d5f  mov     qword ptr [rsp+58h+cbData], rcx; char *
0x180017d64  lea     r9, aSetstringparam_0; "SetStringParameterValueInAnyService"
0x180017d6b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017d72  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017d79  mov     dword ptr [rsp+58h+phkResult], eax; dwMessageId
0x180017d7d  call    PuDbgPrintError
0x180017d82  mov     rcx, [rsp+58h+hKey]; hKey
0x180017d87  test    rcx, rcx
0x180017d8a  jz      short loc_180017D98
0x180017d8c  call    cs:__imp_RegCloseKey
0x180017d93  nop     dword ptr [rax+rax+00h]
0x180017d98  mov     eax, ebx
0x180017d9a  add     rsp, 38h
0x180017d9e  pop     rdi
0x180017d9f  pop     rsi
0x180017da0  pop     rbp
0x180017da1  pop     rbx
0x180017da2  retn
```
