# RassrvRegGetDwEx

- ea: `0x180033d3c`
- end: `0x180033e04`
- name: `RassrvRegGetDwEx`
- size: `200`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180035134`
- `0x1800358a8`
- `0x1800359e0`
- `0x1800365a8`
- `0x18003664c`
- `0x1800367b4`
- `0x180037c70`
- `0x180037d70`
- `0x180038038`

## callees

- `0x180033d3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033d9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033d9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033de9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033de9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033dc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033dc8`

## pseudocode

```c
__int64 __fastcall RassrvRegGetDwEx(_DWORD *a1, int a2, const WCHAR *a3, const WCHAR *a4, int Data)
{
  unsigned int v9; // ebx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF

  Data = 0;
  hKey = 0;
  Type = 4;
  cbData = 4;
  if ( !a1 )
    return 87;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
  if ( !v9 )
  {
    v9 = RegQueryValueExW(hKey, a4, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v9 )
    {
      v9 = 0;
      Data = a2;
    }
    else
    {
      a2 = Data;
    }
    *a1 = a2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180033d3c  mov     [rsp-18h+arg_8], rbx
0x180033d41  mov     [rsp-18h+arg_10], rsi
0x180033d46  push    rbp
0x180033d47  push    rdi
0x180033d48  push    r14
0x180033d4a  mov     rbp, rsp
0x180033d4d  sub     rsp, 40h
0x180033d51  mov     rsi, rcx
0x180033d54  mov     [rbp+Data], 0
0x180033d5b  mov     [rbp+hKey], 0
0x180033d63  mov     ecx, 4
0x180033d68  mov     [rbp+Type], ecx
0x180033d6b  mov     r14, r9
0x180033d6e  mov     [rbp+cbData], ecx
0x180033d71  mov     rax, r8
0x180033d74  mov     edi, edx
0x180033d76  test    rsi, rsi
0x180033d79  jnz     short loc_180033D80
0x180033d7b  lea     eax, [rcx+53h]
0x180033d7e  jmp     short loc_180033DF1
0x180033d80  lea     rcx, [rbp+hKey]
0x180033d84  mov     r9d, 20019h; samDesired
0x180033d8a  mov     [rsp+40h+phkResult], rcx; phkResult
0x180033d8f  xor     r8d, r8d; ulOptions
0x180033d92  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033d99  mov     rdx, rax; lpSubKey
0x180033d9c  call    cs:__imp_RegOpenKeyExW
0x180033da2  mov     ebx, eax
0x180033da4  test    eax, eax
0x180033da6  jnz     short loc_180033DE0
0x180033da8  mov     rcx, [rbp+hKey]; hKey
0x180033dac  lea     rax, [rbp+cbData]
0x180033db0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180033db5  lea     r9, [rbp+Type]; lpType
0x180033db9  lea     rax, [rbp+Data]
0x180033dbd  xor     r8d, r8d; lpReserved
0x180033dc0  mov     rdx, r14; lpValueName
0x180033dc3  mov     [rsp+40h+phkResult], rax; lpData
0x180033dc8  call    cs:__imp_RegQueryValueExW
0x180033dce  mov     ebx, eax
0x180033dd0  test    eax, eax
0x180033dd2  jz      short loc_180033DDB
0x180033dd4  xor     ebx, ebx
0x180033dd6  mov     [rbp+Data], edi
0x180033dd9  jmp     short loc_180033DDE
0x180033ddb  mov     edi, [rbp+Data]
0x180033dde  mov     [rsi], edi
0x180033de0  mov     rcx, [rbp+hKey]; hKey
0x180033de4  test    rcx, rcx
0x180033de7  jz      short loc_180033DEF
0x180033de9  call    cs:__imp_RegCloseKey
0x180033def  mov     eax, ebx
0x180033df1  mov     rbx, [rsp+40h+arg_8]
0x180033df6  mov     rsi, [rsp+40h+arg_10]
0x180033dfb  add     rsp, 40h
0x180033dff  pop     r14
0x180033e01  pop     rdi
0x180033e02  pop     rbp
0x180033e03  retn
```
