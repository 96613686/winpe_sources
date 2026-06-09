# SetStringParameterValueInAnyService(ushort const *,ushort const *,ushort const *)

- ea: `0x180016fe0`
- end: `0x1800170e1`
- name: `?SetStringParameterValueInAnyService@@YAKPEBG00@Z`
- size: `257`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180016fe0`
- `0x1800180c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017075`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017075`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017013`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017013`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800170d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800170d0`

## string_xrefs

- `0x1800170b6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x1800170a8`: `SetStringParameterValueInAnyService`
- `0x180017038`: `Openning registry key for write failed\n`

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
0x180016fe0  push    rbx
0x180016fe2  push    rbp
0x180016fe3  push    rsi
0x180016fe4  push    rdi
0x180016fe5  sub     rsp, 38h
0x180016fe9  mov     rsi, rdx
0x180016fec  lea     rax, [rsp+58h+hKey]
0x180016ff1  mov     rdx, rcx; lpSubKey
0x180016ff4  mov     [rsp+58h+phkResult], rax; phkResult
0x180016ff9  mov     rdi, r8
0x180016ffc  xor     ebp, ebp
0x180016ffe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017005  mov     [rsp+58h+hKey], rbp
0x18001700a  mov     r9d, 20006h; samDesired
0x180017010  xor     r8d, r8d; ulOptions
0x180017013  call    cs:__imp_RegOpenKeyExW
0x180017019  mov     ebx, eax
0x18001701b  test    eax, eax
0x18001701d  jz      short loc_180017047
0x18001701f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017026  jz      loc_1800170C6
0x18001702c  test    eax, eax
0x18001702e  jle     short loc_180017038
0x180017030  movzx   eax, ax
0x180017033  or      eax, 80070000h
0x180017038  lea     rcx, aOpenningRegist; "Openning registry key for write failed"...
0x18001703f  mov     r8d, 108h
0x180017045  jmp     short loc_1800170A3
0x180017047  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001704b  inc     rax
0x18001704e  cmp     [rdi+rax*2], bp
0x180017052  jnz     short loc_18001704B
0x180017054  mov     rcx, [rsp+58h+hKey]; hKey
0x180017059  lea     eax, ds:2[rax*2]
0x180017060  mov     [rsp+58h+cbData], eax; cbData
0x180017064  mov     r9d, 1; dwType
0x18001706a  xor     r8d, r8d; Reserved
0x18001706d  mov     [rsp+58h+phkResult], rdi; lpData
0x180017072  mov     rdx, rsi; lpValueName
0x180017075  call    cs:__imp_RegSetValueExW
0x18001707b  mov     ebx, eax
0x18001707d  test    eax, eax
0x18001707f  jz      short loc_1800170C6
0x180017081  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017088  jz      short loc_1800170C6
0x18001708a  test    eax, eax
0x18001708c  jle     short loc_180017096
0x18001708e  movzx   eax, ax
0x180017091  or      eax, 80070000h
0x180017096  lea     rcx, aFailedWritingS; "Failed writing string value\n"
0x18001709d  mov     r8d, 120h; unsigned int
0x1800170a3  mov     qword ptr [rsp+58h+cbData], rcx; char *
0x1800170a8  lea     r9, aSetstringparam_0; "SetStringParameterValueInAnyService"
0x1800170af  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800170b6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800170bd  mov     dword ptr [rsp+58h+phkResult], eax; dwMessageId
0x1800170c1  call    PuDbgPrintError
0x1800170c6  mov     rcx, [rsp+58h+hKey]; hKey
0x1800170cb  test    rcx, rcx
0x1800170ce  jz      short loc_1800170D6
0x1800170d0  call    cs:__imp_RegCloseKey
0x1800170d6  mov     eax, ebx
0x1800170d8  add     rsp, 38h
0x1800170dc  pop     rdi
0x1800170dd  pop     rsi
0x1800170de  pop     rbp
0x1800170df  pop     rbx
0x1800170e0  retn
```
