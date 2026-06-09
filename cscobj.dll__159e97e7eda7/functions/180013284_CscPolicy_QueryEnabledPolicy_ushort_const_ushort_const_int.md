# CscPolicy_QueryEnabledPolicy(ushort const *,ushort const *,int *)

- ea: `0x180013284`
- end: `0x18001333d`
- name: `?CscPolicy_QueryEnabledPolicy@@YAJPEBG0PEAH@Z`
- size: `185`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012a64`
- `0x180012da4`

## callees

- `0x180013284`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800132fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800132fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001331b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001331b`

## pseudocode

```c
__int64 __fastcall CscPolicy_QueryEnabledPolicy(LPCWSTR lpSubKey, LPCWSTR lpValueName, int *a3)
{
  LSTATUS v5; // ebx
  LSTATUS v6; // eax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF

  *a3 = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  if ( !v5 )
  {
    Data = 0;
    Type = 0;
    cbData = 4;
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v6;
    if ( !v6 && Type == 4 )
    {
      LOBYTE(v6) = Data != 0;
      *a3 = v6;
    }
    RegCloseKey(hKey);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013284  mov     [rsp-18h+arg_0], rbx
0x180013289  push    rbp
0x18001328a  push    rsi
0x18001328b  push    rdi
0x18001328c  mov     rbp, rsp
0x18001328f  sub     rsp, 40h
0x180013293  mov     rsi, rdx
0x180013296  mov     dword ptr [r8], 0
0x18001329d  mov     rdx, rcx; lpSubKey
0x1800132a0  mov     [rbp+hKey], 0
0x1800132a8  mov     rdi, r8
0x1800132ab  lea     rax, [rbp+hKey]
0x1800132af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800132b6  mov     [rsp+40h+phkResult], rax; phkResult
0x1800132bb  mov     r9d, 1; samDesired
0x1800132c1  xor     r8d, r8d; ulOptions
0x1800132c4  call    cs:__imp_RegOpenKeyExW
0x1800132ca  mov     ebx, eax
0x1800132cc  test    eax, eax
0x1800132ce  jnz     short loc_180013321
0x1800132d0  mov     rcx, [rbp+hKey]; hKey
0x1800132d4  lea     r9, [rbp+Type]; lpType
0x1800132d8  mov     [rbp+Data], eax
0x1800132db  xor     r8d, r8d; lpReserved
0x1800132de  mov     [rbp+Type], eax
0x1800132e1  mov     rdx, rsi; lpValueName
0x1800132e4  lea     rax, [rbp+cbData]
0x1800132e8  mov     [rbp+cbData], 4
0x1800132ef  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800132f4  lea     rax, [rbp+Data]
0x1800132f8  mov     [rsp+40h+phkResult], rax; lpData
0x1800132fd  call    cs:__imp_RegQueryValueExW
0x180013303  mov     ebx, eax
0x180013305  test    eax, eax
0x180013307  jnz     short loc_180013317
0x180013309  cmp     [rbp+Type], 4
0x18001330d  jnz     short loc_180013317
0x18001330f  cmp     [rbp+Data], eax
0x180013312  setnz   al
0x180013315  mov     [rdi], eax
0x180013317  mov     rcx, [rbp+hKey]; hKey
0x18001331b  call    cs:__imp_RegCloseKey
0x180013321  test    ebx, ebx
0x180013323  jle     short loc_18001332E
0x180013325  movzx   ebx, bx
0x180013328  or      ebx, 80070000h
0x18001332e  mov     eax, ebx
0x180013330  mov     rbx, [rsp+40h+arg_0]
0x180013335  add     rsp, 40h
0x180013339  pop     rdi
0x18001333a  pop     rsi
0x18001333b  pop     rbp
0x18001333c  retn
```
