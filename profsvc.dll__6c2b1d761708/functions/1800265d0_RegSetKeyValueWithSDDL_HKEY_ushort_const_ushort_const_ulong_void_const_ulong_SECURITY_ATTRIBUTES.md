# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800265d0`
- end: `0x18002669e`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `206`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037140`
- `0x180041504`

## callees

- `0x1800265d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002668e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002668e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002661d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002661d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026674`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180026674`

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
0x1800265d0  mov     [rsp+arg_0], rbx
0x1800265d5  mov     [rsp+arg_10], rsi
0x1800265da  push    rdi
0x1800265db  sub     rsp, 50h
0x1800265df  mov     rbx, rcx
0x1800265e2  mov     edi, r9d
0x1800265e5  xor     ecx, ecx
0x1800265e7  mov     rsi, r8
0x1800265ea  mov     [rsp+58h+hKey], rcx
0x1800265ef  test    rdx, rdx
0x1800265f2  jnz     short loc_180026646
0x1800265f4  mov     rcx, rbx; hKey
0x1800265f7  mov     [rsp+58h+hKey], rbx
0x1800265fc  mov     eax, [rsp+58h+arg_28]
0x180026603  mov     r9d, edi; dwType
0x180026606  mov     [rsp+58h+cbData], eax; cbData
0x18002660a  xor     r8d, r8d; Reserved
0x18002660d  mov     rax, [rsp+58h+arg_20]
0x180026615  mov     rdx, rsi; lpValueName
0x180026618  mov     [rsp+58h+lpData], rax; lpData
0x18002661d  call    cs:__imp_RegSetValueExW
0x180026624  nop     dword ptr [rax+rax+00h]
0x180026629  mov     rcx, [rsp+58h+hKey]; hKey
0x18002662e  mov     edi, eax
0x180026630  cmp     rcx, rbx
0x180026633  jnz     short loc_18002668E
0x180026635  mov     rbx, [rsp+58h+arg_0]
0x18002663a  mov     rsi, [rsp+58h+arg_10]
0x18002663f  add     rsp, 50h
0x180026643  pop     rdi
0x180026644  retn
0x180026646  cmp     [rdx], cx
0x180026649  jz      short loc_1800265F4
0x18002664b  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180026650  lea     rax, [rsp+58h+hKey]
0x180026655  mov     [rsp+58h+phkResult], rax; phkResult
0x18002665a  xor     r9d, r9d; lpClass
0x18002665d  mov     [rsp+58h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180026662  xor     r8d, r8d; Reserved
0x180026665  mov     [rsp+58h+cbData], 2; samDesired
0x18002666d  mov     dword ptr [rsp+58h+lpData], ecx; dwOptions
0x180026671  mov     rcx, rbx; hKey
0x180026674  call    cs:__imp_RegCreateKeyExW
0x18002667b  nop     dword ptr [rax+rax+00h]
0x180026680  test    eax, eax
0x180026682  jnz     short loc_180026635
0x180026684  mov     rcx, [rsp+58h+hKey]
0x180026689  jmp     loc_1800265FC
0x18002668e  call    cs:__imp_RegCloseKey
0x180026695  nop     dword ptr [rax+rax+00h]
0x18002669a  mov     eax, edi
0x18002669c  jmp     short loc_180026635
```
