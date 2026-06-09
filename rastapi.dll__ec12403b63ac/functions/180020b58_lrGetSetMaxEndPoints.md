# lrGetSetMaxEndPoints

- ea: `0x180020b58`
- end: `0x180020c56`
- name: `lrGetSetMaxEndPoints`
- size: `254`
- prototype: `__int64 __fastcall(LPBYTE lpData, LPBYTE)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800030f0`

## callees

- `0x180020a20`
- `0x180020b58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020bce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020c01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020bce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020c01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020b9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020b9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020c0d`

## string_xrefs

- `0x180020baf`: `LimitSimultaneousIncomingCalls`
- `0x180020b7e`: `System\CurrentControlSet\Services\Rasman\Parameters`

## pseudocode

```c
__int64 __fastcall lrGetSetMaxEndPoints(LPBYTE lpData, LPBYTE a2, DWORD a3)
{
  LSTATUS v5; // esi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  cbData = a3;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 0x20007u, &hKey) )
    goto LABEL_5;
  Type = 0;
  cbData = 4;
  v5 = RegQueryValueExW(hKey, L"LimitSimultaneousIncomingCalls", 0, &Type, a2, &cbData);
  if ( !v5 )
  {
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"LimitSimultaneousOutgoingCalls", 0, &Type, lpData, &cbData);
  }
  RegCloseKey(hKey);
  if ( v5 )
  {
LABEL_5:
    cbData = 0;
    lrGetProductType(&cbData);
    if ( cbData == 1 )
    {
      *(_DWORD *)a2 = 3;
      *(_DWORD *)lpData = 4;
    }
    else
    {
      *(_DWORD *)lpData = 3;
      *(_DWORD *)a2 = 0x7FFFFFFF;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020b58  mov     [rsp-18h+arg_0], rbx
0x180020b5d  mov     [rsp-18h+cbData], r8d
0x180020b62  push    rbp
0x180020b63  push    rsi
0x180020b64  push    rdi
0x180020b65  mov     rbp, rsp
0x180020b68  sub     rsp, 40h
0x180020b6c  mov     rbx, rdx
0x180020b6f  mov     [rbp+hKey], 0
0x180020b77  mov     rdi, rcx
0x180020b7a  lea     rax, [rbp+hKey]
0x180020b7e  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x180020b85  mov     [rsp+40h+phkResult], rax; phkResult
0x180020b8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020b91  mov     r9d, 20007h; samDesired
0x180020b97  xor     r8d, r8d; ulOptions
0x180020b9a  call    cs:__imp_RegOpenKeyExW
0x180020ba0  test    eax, eax
0x180020ba2  jnz     short loc_180020C17
0x180020ba4  mov     rcx, [rbp+hKey]; hKey
0x180020ba8  lea     r9, [rbp+Type]; lpType
0x180020bac  mov     [rbp+Type], eax
0x180020baf  lea     rdx, aLimitsimultane; "LimitSimultaneousIncomingCalls"
0x180020bb6  lea     rax, [rbp+cbData]
0x180020bba  mov     [rbp+cbData], 4
0x180020bc1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180020bc6  xor     r8d, r8d; lpReserved
0x180020bc9  mov     [rsp+40h+phkResult], rbx; lpData
0x180020bce  call    cs:__imp_RegQueryValueExW
0x180020bd4  mov     esi, eax
0x180020bd6  test    eax, eax
0x180020bd8  jnz     short loc_180020C09
0x180020bda  mov     rcx, [rbp+hKey]; hKey
0x180020bde  lea     rax, [rbp+cbData]
0x180020be2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180020be7  lea     r9, [rbp+Type]; lpType
0x180020beb  xor     r8d, r8d; lpReserved
0x180020bee  mov     [rsp+40h+phkResult], rdi; lpData
0x180020bf3  lea     rdx, aLimitsimultane_0; "LimitSimultaneousOutgoingCalls"
0x180020bfa  mov     [rbp+cbData], 4
0x180020c01  call    cs:__imp_RegQueryValueExW
0x180020c07  mov     esi, eax
0x180020c09  mov     rcx, [rbp+hKey]; hKey
0x180020c0d  call    cs:__imp_RegCloseKey
0x180020c13  test    esi, esi
0x180020c15  jz      short loc_180020C47
0x180020c17  lea     rcx, [rbp+cbData]
0x180020c1b  mov     [rbp+cbData], 0
0x180020c22  call    lrGetProductType
0x180020c27  cmp     [rbp+cbData], 1
0x180020c2b  jnz     short loc_180020C3B
0x180020c2d  mov     dword ptr [rbx], 3
0x180020c33  mov     dword ptr [rdi], 4
0x180020c39  jmp     short loc_180020C47
0x180020c3b  mov     dword ptr [rdi], 3
0x180020c41  mov     dword ptr [rbx], 7FFFFFFFh
0x180020c47  mov     rbx, [rsp+40h+arg_0]
0x180020c4c  xor     eax, eax
0x180020c4e  add     rsp, 40h
0x180020c52  pop     rdi
0x180020c53  pop     rsi
0x180020c54  pop     rbp
0x180020c55  retn
```
