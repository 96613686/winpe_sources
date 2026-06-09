# GetTasksFolder(ushort * *)

- ea: `0x180006ba0`
- end: `0x180006dc4`
- name: `?GetTasksFolder@@YAJPEAPEAG@Z`
- size: `548`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180006550`

## callees

- `0x180006ba0`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006c61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ccf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006c52`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006c52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006beb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006beb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006cbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006cbf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006d3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006d7d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006d3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006d7d`

## string_xrefs

- `0x180006c0f`: `%WinDir%\Tasks`
- `0x180006be4`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x180006c7a`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x180006c3b`: `TasksFolder`
- `0x180006ca2`: `TasksFolder`

## pseudocode

```c
signed int __fastcall GetTasksFolder(unsigned __int16 **a1)
{
  const BYTE *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rdx
  BYTE *v5; // rax
  __int64 v6; // r8
  BYTE *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // edi
  unsigned __int16 *v10; // rbx
  signed int result; // eax
  HKEY hKey; // [rsp+30h] [rbp-258h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-250h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-248h] BYREF
  _BYTE v15[518]; // [rsp+42h] [rbp-246h] BYREF
  __int16 v16; // [rsp+248h] [rbp-40h]

  hKey = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  *(_WORD *)Data = 0;
  memset_0(v15, 0, 0x208u);
  v2 = L"%WinDir%\\Tasks";
  v16 = 0;
  if ( hKey )
  {
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"TasksFolder", 0, 0, Data, &cbData) )
    {
      RegCloseKey(hKey);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 2u, &hKey) )
      {
        hKey = 0;
        goto LABEL_8;
      }
      RegSetValueExW(hKey, L"TasksFolder", 0, 2u, L"%WinDir%\\Tasks", 0x1Eu);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
LABEL_8:
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&Data[2 * v3] );
  if ( !v3 )
  {
    v4 = 261;
    v5 = Data;
    v6 = 2147483646;
    do
    {
      if ( !v6 )
        break;
      if ( !*(_WORD *)v2 )
        break;
      *(_WORD *)v5 = *(_WORD *)v2;
      v2 += 2;
      v5 += 2;
      --v6;
      --v4;
    }
    while ( v4 );
    v7 = v5 - 2;
    if ( v4 )
      v7 = v5;
    *(_WORD *)v7 = 0;
  }
  v8 = ExpandEnvironmentStringsW((LPCWSTR)Data, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = (unsigned __int16 *)operator new(saturated_mul(v8, 2u));
    if ( !v10 )
      return -2147024882;
    *v10 = 0;
    if ( ExpandEnvironmentStringsW((LPCWSTR)Data, v10, v9) )
    {
      *a1 = v10;
      return 0;
    }
    operator delete(v10);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180006ba0  push    rbx
0x180006ba2  push    rbp
0x180006ba3  push    rsi
0x180006ba4  push    rdi
0x180006ba5  sub     rsp, 268h
0x180006bac  mov     rax, cs:__security_cookie
0x180006bb3  xor     rax, rsp
0x180006bb6  mov     [rsp+288h+var_38], rax
0x180006bbe  mov     rsi, rcx
0x180006bc1  mov     [rsp+288h+hKey], 0
0x180006bca  lea     rax, [rsp+288h+hKey]
0x180006bcf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006bd6  mov     r9d, 20019h; samDesired
0x180006bdc  mov     [rsp+288h+phkResult], rax; phkResult
0x180006be1  xor     r8d, r8d; ulOptions
0x180006be4  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x180006beb  call    cs:__imp_RegOpenKeyExW
0x180006bf1  xor     eax, eax
0x180006bf3  lea     rcx, [rsp+288h+var_246]; void *
0x180006bf8  xor     edx, edx; Val
0x180006bfa  mov     word ptr [rsp+288h+Data], ax
0x180006bff  mov     r8d, 208h; Size
0x180006c05  call    memset_0
0x180006c0a  mov     rcx, [rsp+288h+hKey]; hKey
0x180006c0f  lea     rbx, Data; "%WinDir%\\Tasks"
0x180006c16  xor     eax, eax
0x180006c18  mov     [rsp+288h+var_40], ax
0x180006c20  test    rcx, rcx
0x180006c23  jz      loc_180006CD5
0x180006c29  lea     rax, [rsp+288h+cbData]
0x180006c2e  mov     [rsp+288h+cbData], 208h
0x180006c36  mov     [rsp+288h+lpcbData], rax; lpcbData
0x180006c3b  lea     rdx, aTasksfolder; "TasksFolder"
0x180006c42  lea     rax, [rsp+288h+Data]
0x180006c47  xor     r9d, r9d; lpType
0x180006c4a  xor     r8d, r8d; lpReserved
0x180006c4d  mov     [rsp+288h+phkResult], rax; lpData
0x180006c52  call    cs:__imp_RegQueryValueExW
0x180006c58  test    eax, eax
0x180006c5a  jz      short loc_180006CC5
0x180006c5c  mov     rcx, [rsp+288h+hKey]; hKey
0x180006c61  call    cs:__imp_RegCloseKey
0x180006c67  lea     rax, [rsp+288h+hKey]
0x180006c6c  mov     r9d, 2; samDesired
0x180006c72  xor     r8d, r8d; ulOptions
0x180006c75  mov     [rsp+288h+phkResult], rax; phkResult
0x180006c7a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x180006c81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006c88  call    cs:__imp_RegOpenKeyExW
0x180006c8e  test    eax, eax
0x180006c90  jz      short loc_180006C9D
0x180006c92  mov     [rsp+288h+hKey], 0
0x180006c9b  jmp     short loc_180006CD5
0x180006c9d  mov     rcx, [rsp+288h+hKey]; hKey
0x180006ca2  lea     rdx, aTasksfolder; "TasksFolder"
0x180006ca9  mov     dword ptr [rsp+288h+lpcbData], 1Eh; cbData
0x180006cb1  mov     r9d, 2; dwType
0x180006cb7  xor     r8d, r8d; Reserved
0x180006cba  mov     [rsp+288h+phkResult], rbx; lpData
0x180006cbf  call    cs:__imp_RegSetValueExW
0x180006cc5  mov     rcx, [rsp+288h+hKey]; hKey
0x180006cca  test    rcx, rcx
0x180006ccd  jz      short loc_180006CD5
0x180006ccf  call    cs:__imp_RegCloseKey
0x180006cd5  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180006cdc  lea     rcx, [rsp+288h+Data]
0x180006ce1  mov     rax, rbp
0x180006ce4  inc     rax
0x180006ce7  cmp     word ptr [rcx+rax*2], 0
0x180006cec  jnz     short loc_180006CE4
0x180006cee  test    rax, rax
0x180006cf1  jnz     short loc_180006D34
0x180006cf3  mov     edx, 105h
0x180006cf8  lea     rax, [rsp+288h+Data]
0x180006cfd  mov     r8d, 7FFFFFFEh
0x180006d03  test    r8, r8
0x180006d06  jz      short loc_180006D24
0x180006d08  movzx   ecx, word ptr [rbx]
0x180006d0b  test    cx, cx
0x180006d0e  jz      short loc_180006D24
0x180006d10  mov     [rax], cx
0x180006d13  add     rbx, 2
0x180006d17  add     rax, 2
0x180006d1b  dec     r8
0x180006d1e  sub     rdx, 1
0x180006d22  jnz     short loc_180006D03
0x180006d24  test    rdx, rdx
0x180006d27  lea     rcx, [rax-2]
0x180006d2b  cmovnz  rcx, rax
0x180006d2f  xor     eax, eax
0x180006d31  mov     [rcx], ax
0x180006d34  xor     r8d, r8d; nSize
0x180006d37  lea     rcx, [rsp+288h+Data]; lpSrc
0x180006d3c  xor     edx, edx; lpDst
0x180006d3e  call    cs:__imp_ExpandEnvironmentStringsW
0x180006d44  mov     edi, eax
0x180006d46  test    eax, eax
0x180006d48  jz      short loc_180006D8F
0x180006d4a  mov     eax, 2
0x180006d4f  mul     rdi
0x180006d52  cmovb   rax, rbp
0x180006d56  mov     rcx, rax; Size
0x180006d59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d5e  mov     rbx, rax
0x180006d61  test    rax, rax
0x180006d64  jnz     short loc_180006D6D
0x180006d66  mov     eax, 8007000Eh
0x180006d6b  jmp     short loc_180006DA8
0x180006d6d  xor     eax, eax
0x180006d6f  lea     rcx, [rsp+288h+Data]; lpSrc
0x180006d74  mov     r8d, edi; nSize
0x180006d77  mov     [rbx], ax
0x180006d7a  mov     rdx, rbx; lpDst
0x180006d7d  call    cs:__imp_ExpandEnvironmentStringsW
0x180006d83  test    eax, eax
0x180006d85  jnz     short loc_180006DA3
0x180006d87  mov     rcx, rbx; Block
0x180006d8a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006d8f  call    cs:__imp_GetLastError
0x180006d95  test    eax, eax
0x180006d97  jle     short loc_180006DA8
0x180006d99  movzx   eax, ax
0x180006d9c  or      eax, 80070000h
0x180006da1  jmp     short loc_180006DA8
0x180006da3  mov     [rsi], rbx
0x180006da6  xor     eax, eax
0x180006da8  mov     rcx, [rsp+288h+var_38]
0x180006db0  xor     rcx, rsp; StackCookie
0x180006db3  call    __security_check_cookie
0x180006db8  add     rsp, 268h
0x180006dbf  pop     rdi
0x180006dc0  pop     rsi
0x180006dc1  pop     rbp
0x180006dc2  pop     rbx
0x180006dc3  retn
```
