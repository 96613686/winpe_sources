# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180023cb0`
- end: `0x180023d6b`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `187`
- prototype: `LSTATUS __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036a6c`
- `0x18003fd14`

## callees

- `0x180023cb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023d61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023d61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023cfd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023cfd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023d4d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023d4d`

## pseudocode

```c
LSTATUS __fastcall _RegSetKeyValueWithSDDL(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v6; // rbx
  LSTATUS result; // eax
  unsigned int v10; // edi
  HKEY hKeya; // [rsp+68h] [rbp+10h] BYREF

  v6 = hKey;
  hKeya = 0;
  if ( a2 && *a2 )
  {
    result = RegCreateKeyExW(hKey, a2, 0, 0, 0, 2u, 0, &hKeya, 0);
    if ( result )
      return result;
    hKey = hKeya;
  }
  else
  {
    hKeya = hKey;
  }
  result = RegSetValueExW(hKey, a3, 0, a4, lpData, cbData);
  v10 = result;
  if ( hKeya != v6 )
  {
    RegCloseKey(hKeya);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180023cb0  mov     [rsp+arg_0], rbx
0x180023cb5  mov     [rsp+arg_10], rsi
0x180023cba  push    rdi
0x180023cbb  sub     rsp, 50h
0x180023cbf  mov     rbx, rcx
0x180023cc2  mov     edi, r9d
0x180023cc5  xor     ecx, ecx
0x180023cc7  mov     rsi, r8
0x180023cca  mov     [rsp+58h+hKey], rcx
0x180023ccf  test    rdx, rdx
0x180023cd2  jnz     short loc_180023D1F
0x180023cd4  mov     rcx, rbx; hKey
0x180023cd7  mov     [rsp+58h+hKey], rbx
0x180023cdc  mov     eax, [rsp+58h+arg_28]
0x180023ce3  mov     r9d, edi; dwType
0x180023ce6  mov     [rsp+58h+cbData], eax; cbData
0x180023cea  xor     r8d, r8d; Reserved
0x180023ced  mov     rax, [rsp+58h+arg_20]
0x180023cf5  mov     rdx, rsi; lpValueName
0x180023cf8  mov     [rsp+58h+lpData], rax; lpData
0x180023cfd  call    cs:__imp_RegSetValueExW
0x180023d03  mov     rcx, [rsp+58h+hKey]; hKey
0x180023d08  mov     edi, eax
0x180023d0a  cmp     rcx, rbx
0x180023d0d  jnz     short loc_180023D61
0x180023d0f  mov     rbx, [rsp+58h+arg_0]
0x180023d14  mov     rsi, [rsp+58h+arg_10]
0x180023d19  add     rsp, 50h
0x180023d1d  pop     rdi
0x180023d1e  retn
0x180023d1f  cmp     [rdx], cx
0x180023d22  jz      short loc_180023CD4
0x180023d24  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180023d29  lea     rax, [rsp+58h+hKey]
0x180023d2e  mov     [rsp+58h+phkResult], rax; phkResult
0x180023d33  xor     r9d, r9d; lpClass
0x180023d36  mov     [rsp+58h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180023d3b  xor     r8d, r8d; Reserved
0x180023d3e  mov     [rsp+58h+cbData], 2; samDesired
0x180023d46  mov     dword ptr [rsp+58h+lpData], ecx; dwOptions
0x180023d4a  mov     rcx, rbx; hKey
0x180023d4d  call    cs:__imp_RegCreateKeyExW
0x180023d53  test    eax, eax
0x180023d55  jnz     short loc_180023D0F
0x180023d57  mov     rcx, [rsp+58h+hKey]
0x180023d5c  jmp     loc_180023CDC
0x180023d61  call    cs:__imp_RegCloseKey
0x180023d67  mov     eax, edi
0x180023d69  jmp     short loc_180023D0F
```
