# SaveDefaultIPv4Settings

- ea: `0x180015828`
- end: `0x18001598e`
- name: `SaveDefaultIPv4Settings`
- size: `358`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180026b90`

## callees

- `0x180015498`
- `0x180015828`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001597d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001597d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800158a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800158d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001592f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001595d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800158a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800158d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015905`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001592f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001595d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015867`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015867`

## string_xrefs

- `0x180015859`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x1800158c5`: `AllowNetworkAccess`

## pseudocode

```c
__int64 __fastcall SaveDefaultIPv4Settings(int a1)
{
  unsigned int v1; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-18h] BYREF
  BYTE v4[16]; // [rsp+38h] [rbp-10h] BYREF
  int v5; // [rsp+70h] [rbp+28h] BYREF
  int v6; // [rsp+78h] [rbp+30h] BYREF
  int v7; // [rsp+80h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+40h] BYREF

  v5 = a1;
  hKey = 0;
  *(_DWORD *)Data = 1;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
         0,
         0xF003Fu,
         &hKey);
  if ( !v1 )
  {
    v5 = 1;
    v6 = 1;
    v7 = 1;
    *(_QWORD *)v4 = 0;
    v1 = RegSetValueExW(hKey, L"EnableIn", 0, 4u, Data, 4u);
    if ( !v1 )
    {
      v1 = RegSetValueExW(hKey, L"AllowNetworkAccess", 0, 4u, (const BYTE *)&v5, 4u);
      if ( !v1 )
      {
        v1 = RegSetValueExW(hKey, L"UseDhcpAddressing", 0, 4u, (const BYTE *)&v6, 4u);
        if ( !v1 )
        {
          v1 = RegSetValueExW(hKey, L"EnableNetbtBcastFwd", 0, 4u, (const BYTE *)&v7, 4u);
          if ( !v1 )
          {
            v1 = RegSetValueExW(hKey, L"NetworkAdapterGUID", 0, 1u, v4, 8u);
            if ( !v1 )
              v1 = ResetIPAddressPool(hKey);
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180015828  mov     [rsp-20h+arg_0], ecx
0x18001582c  push    rbp
0x18001582d  push    rbx
0x18001582e  push    rsi
0x18001582f  push    rdi
0x180015830  mov     rbp, rsp
0x180015833  sub     rsp, 48h
0x180015837  lea     rax, [rbp+hKey]
0x18001583b  mov     [rbp+hKey], 0
0x180015843  mov     esi, 1
0x180015848  mov     [rsp+48h+phkResult], rax; phkResult
0x18001584d  mov     r9d, 0F003Fh; samDesired
0x180015853  mov     dword ptr [rbp+Data], esi
0x180015856  xor     r8d, r8d; ulOptions
0x180015859  lea     rdx, c_szRegKeyRasIp; "System\\CurrentControlSet\\Services\\Re"...
0x180015860  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015867  call    cs:__imp_RegOpenKeyExW
0x18001586d  mov     ebx, eax
0x18001586f  test    eax, eax
0x180015871  jnz     loc_180015974
0x180015877  mov     rcx, [rbp+hKey]; hKey
0x18001587b  lea     edi, [rsi+3]
0x18001587e  lea     rax, [rbp+Data]
0x180015882  mov     [rsp+48h+cbData], edi; cbData
0x180015886  mov     r9d, edi; dwType
0x180015889  mov     [rsp+48h+phkResult], rax; lpData
0x18001588e  xor     r8d, r8d; Reserved
0x180015891  mov     [rbp+arg_0], esi
0x180015894  lea     rdx, c_szRegValEnableIn; "EnableIn"
0x18001589b  mov     [rbp+arg_8], esi
0x18001589e  mov     [rbp+arg_10], esi
0x1800158a1  mov     qword ptr [rbp+var_10], 0
0x1800158a9  call    cs:__imp_RegSetValueExW
0x1800158af  mov     ebx, eax
0x1800158b1  test    eax, eax
0x1800158b3  jnz     loc_180015974
0x1800158b9  mov     rcx, [rbp+hKey]; hKey
0x1800158bd  lea     rax, [rbp+arg_0]
0x1800158c1  mov     [rsp+48h+cbData], edi; cbData
0x1800158c5  lea     rdx, c_szRegValAllowNetAccess; "AllowNetworkAccess"
0x1800158cc  mov     r9d, edi; dwType
0x1800158cf  mov     [rsp+48h+phkResult], rax; lpData
0x1800158d4  xor     r8d, r8d; Reserved
0x1800158d7  call    cs:__imp_RegSetValueExW
0x1800158dd  mov     ebx, eax
0x1800158df  test    eax, eax
0x1800158e1  jnz     loc_180015974
0x1800158e7  mov     rcx, [rbp+hKey]; hKey
0x1800158eb  lea     rax, [rbp+arg_8]
0x1800158ef  mov     [rsp+48h+cbData], edi; cbData
0x1800158f3  lea     rdx, c_szRegValDhcpAddressing; "UseDhcpAddressing"
0x1800158fa  mov     r9d, edi; dwType
0x1800158fd  mov     [rsp+48h+phkResult], rax; lpData
0x180015902  xor     r8d, r8d; Reserved
0x180015905  call    cs:__imp_RegSetValueExW
0x18001590b  mov     ebx, eax
0x18001590d  test    eax, eax
0x18001590f  jnz     short loc_180015974
0x180015911  mov     rcx, [rbp+hKey]; hKey
0x180015915  lea     rax, [rbp+arg_10]
0x180015919  mov     [rsp+48h+cbData], edi; cbData
0x18001591d  lea     rdx, c_szRegValEnableNetbtBcastFwd; "EnableNetbtBcastFwd"
0x180015924  mov     r9d, edi; dwType
0x180015927  mov     [rsp+48h+phkResult], rax; lpData
0x18001592c  xor     r8d, r8d; Reserved
0x18001592f  call    cs:__imp_RegSetValueExW
0x180015935  mov     ebx, eax
0x180015937  test    eax, eax
0x180015939  jnz     short loc_180015974
0x18001593b  mov     rcx, [rbp+hKey]; hKey
0x18001593f  lea     rax, [rbp+var_10]
0x180015943  mov     [rsp+48h+cbData], 8; cbData
0x18001594b  lea     rdx, c_szRegValNetworkAdapterGUID; "NetworkAdapterGUID"
0x180015952  mov     r9d, esi; dwType
0x180015955  mov     [rsp+48h+phkResult], rax; lpData
0x18001595a  xor     r8d, r8d; Reserved
0x18001595d  call    cs:__imp_RegSetValueExW
0x180015963  mov     ebx, eax
0x180015965  test    eax, eax
0x180015967  jnz     short loc_180015974
0x180015969  mov     rcx, [rbp+hKey]; hKey
0x18001596d  call    ResetIPAddressPool
0x180015972  mov     ebx, eax
0x180015974  mov     rcx, [rbp+hKey]; hKey
0x180015978  test    rcx, rcx
0x18001597b  jz      short loc_180015983
0x18001597d  call    cs:__imp_RegCloseKey
0x180015983  mov     eax, ebx
0x180015985  add     rsp, 48h
0x180015989  pop     rdi
0x18001598a  pop     rsi
0x18001598b  pop     rbx
0x18001598c  pop     rbp
0x18001598d  retn
```
