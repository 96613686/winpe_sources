# RasEapSetRetryFlag

- ea: `0x180017ae0`
- end: `0x180017bbd`
- name: `RasEapSetRetryFlag`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180017ae0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180017b42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180017b42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180017b7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180017b7a`

## string_xrefs

- `0x180017b32`: `System\CurrentControlSet\Services\Rasman\PPP\EAP\26`

## pseudocode

```c
__int64 __fastcall RasEapSetRetryFlag(int a1, int a2, __int64 a3)
{
  BOOL v6; // ebx
  int v7; // edi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  int Data; // [rsp+88h] [rbp+48h] BYREF

  cbData = 0;
  Type = 0;
  Data = 0;
  hKey = 0;
  if ( a1 != 26 )
    return 2147500033LL;
  v6 = 0;
  v7 = 1;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP\\26",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(hKey, "DisableAuthRetry", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v6 = Data == 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !a2 || v6 )
    v7 = 0;
  *(_DWORD *)(a3 + 1352) = v7;
  return 0;
}

```

## disassembly

```asm
0x180017ae0  push    rbp
0x180017ae2  push    rbx
0x180017ae3  push    rsi
0x180017ae4  push    rdi
0x180017ae5  push    r14
0x180017ae7  mov     rbp, rsp
0x180017aea  sub     rsp, 40h
0x180017aee  mov     [rbp+cbData], 0
0x180017af5  mov     rsi, r8
0x180017af8  mov     [rbp+Type], 0
0x180017aff  mov     r14d, edx
0x180017b02  mov     [rbp+Data], 0
0x180017b09  mov     [rbp+hKey], 0
0x180017b11  cmp     ecx, 1Ah
0x180017b14  jz      short loc_180017B20
0x180017b16  mov     eax, 80004001h
0x180017b1b  jmp     loc_180017BB2
0x180017b20  lea     rax, [rbp+hKey]
0x180017b24  mov     r9d, 20019h; samDesired
0x180017b2a  xor     r8d, r8d; ulOptions
0x180017b2d  mov     [rsp+40h+phkResult], rax; phkResult
0x180017b32  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Ra"...
0x180017b39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017b40  xor     ebx, ebx
0x180017b42  call    cs:__imp_RegOpenKeyExA
0x180017b48  lea     edi, [rbx+1]
0x180017b4b  test    eax, eax
0x180017b4d  jnz     short loc_180017B90
0x180017b4f  mov     rcx, [rbp+hKey]; hKey
0x180017b53  lea     rax, [rbp+cbData]
0x180017b57  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180017b5c  lea     r9, [rbp+Type]; lpType
0x180017b60  lea     rax, [rbp+Data]
0x180017b64  mov     [rbp+cbData], 4
0x180017b6b  xor     r8d, r8d; lpReserved
0x180017b6e  mov     [rsp+40h+phkResult], rax; lpData
0x180017b73  lea     rdx, aDisableauthret; "DisableAuthRetry"
0x180017b7a  call    cs:__imp_RegQueryValueExA
0x180017b80  test    eax, eax
0x180017b82  jnz     short loc_180017B90
0x180017b84  cmp     [rbp+Type], 4
0x180017b88  jnz     short loc_180017B90
0x180017b8a  cmp     [rbp+Data], edi
0x180017b8d  cmovz   ebx, edi
0x180017b90  mov     rcx, [rbp+hKey]; hKey
0x180017b94  test    rcx, rcx
0x180017b97  jz      short loc_180017B9F
0x180017b99  call    cs:__imp_RegCloseKey
0x180017b9f  test    r14d, r14d
0x180017ba2  jz      short loc_180017BA8
0x180017ba4  test    ebx, ebx
0x180017ba6  jz      short loc_180017BAA
0x180017ba8  xor     edi, edi
0x180017baa  mov     [rsi+548h], edi
0x180017bb0  xor     eax, eax
0x180017bb2  add     rsp, 40h
0x180017bb6  pop     r14
0x180017bb8  pop     rdi
0x180017bb9  pop     rsi
0x180017bba  pop     rbx
0x180017bbb  pop     rbp
0x180017bbc  retn
```
