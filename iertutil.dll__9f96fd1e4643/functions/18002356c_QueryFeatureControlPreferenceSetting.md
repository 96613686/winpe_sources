# _QueryFeatureControlPreferenceSetting

- ea: `0x18002356c`
- end: `0x18002366a`
- name: `_QueryFeatureControlPreferenceSetting`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002331c`

## callees

- `0x18002356c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002359a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002359a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800235e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023626`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800235e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023626`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023634`

## pseudocode

```c
char __fastcall QueryFeatureControlPreferenceSetting(
        HKEY a1,
        const WCHAR *a2,
        const WCHAR *a3,
        int a4,
        unsigned int *a5)
{
  char v7; // bl
  unsigned int v9; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-18h] BYREF
  unsigned int pvData; // [rsp+44h] [rbp-14h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-10h] BYREF

  hkey = 0;
  v7 = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, 1u, &hkey) )
  {
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(hkey, 0, a3, 0x10u, 0, &pvData, &pcbData) || (v9 = pvData, a4) && pvData > 1 )
    {
      pcbData = 4;
      if ( RegGetValueW(hkey, 0, L"*", 0x10u, 0, &pvData, &pcbData) )
        goto LABEL_5;
      v9 = pvData;
      if ( a4 )
      {
        if ( pvData > 1 )
          goto LABEL_5;
      }
    }
    else
    {
      pcbData = 4;
    }
    v7 = 1;
    *a5 = v9;
LABEL_5:
    RegCloseKey(hkey);
  }
  return v7;
}

```

## disassembly

```asm
0x18002356c  push    rbp
0x18002356e  push    rbx
0x18002356f  push    rsi
0x180023570  push    rdi
0x180023571  mov     rbp, rsp
0x180023574  sub     rsp, 58h
0x180023578  mov     edi, r9d
0x18002357b  mov     [rbp+hkey], 0
0x180023583  mov     rsi, r8
0x180023586  lea     rax, [rbp+hkey]
0x18002358a  mov     r9d, 1; samDesired
0x180023590  mov     [rsp+58h+phkResult], rax; phkResult
0x180023595  xor     r8d, r8d; ulOptions
0x180023598  xor     bl, bl
0x18002359a  call    cs:__imp_RegOpenKeyExW
0x1800235a0  test    eax, eax
0x1800235a2  jz      short loc_1800235AF
0x1800235a4  mov     al, bl
0x1800235a6  add     rsp, 58h
0x1800235aa  pop     rdi
0x1800235ab  pop     rsi
0x1800235ac  pop     rbx
0x1800235ad  pop     rbp
0x1800235ae  retn
0x1800235af  mov     rcx, [rbp+hkey]; hkey
0x1800235b3  lea     rax, [rbp+var_18]
0x1800235b7  mov     [rsp+58h+pcbData], rax; pcbData
0x1800235bc  mov     r9d, 10h; dwFlags
0x1800235c2  lea     rax, [rbp+var_14]
0x1800235c6  mov     [rbp+var_14], 0
0x1800235cd  mov     [rsp+58h+pvData], rax; pvData
0x1800235d2  mov     r8, rsi; lpValue
0x1800235d5  xor     edx, edx; lpSubKey
0x1800235d7  mov     [rsp+58h+phkResult], 0; pdwType
0x1800235e0  mov     [rbp+var_18], 4
0x1800235e7  call    cs:__imp_RegGetValueW
0x1800235ed  test    eax, eax
0x1800235ef  jz      short loc_18002363F
0x1800235f1  mov     rcx, [rbp+hkey]; hkey
0x1800235f5  lea     rax, [rbp+var_18]
0x1800235f9  mov     [rsp+58h+pcbData], rax; pcbData
0x1800235fe  lea     r8, Value; "*"
0x180023605  lea     rax, [rbp+var_14]
0x180023609  mov     [rbp+var_18], 4
0x180023610  mov     [rsp+58h+pvData], rax; pvData
0x180023615  mov     r9d, 10h; dwFlags
0x18002361b  xor     edx, edx; lpSubKey
0x18002361d  mov     [rsp+58h+phkResult], 0; pdwType
0x180023626  call    cs:__imp_RegGetValueW
0x18002362c  test    eax, eax
0x18002362e  jz      short loc_180023654
0x180023630  mov     rcx, [rbp+hkey]; hKey
0x180023634  call    cs:__imp_RegCloseKey
0x18002363a  jmp     loc_1800235A4
0x18002363f  mov     ecx, [rbp+var_14]
0x180023642  test    edi, edi
0x180023644  jz      short loc_18002364B
0x180023646  cmp     ecx, 1
0x180023649  ja      short loc_1800235F1
0x18002364b  mov     [rbp+var_18], 4
0x180023652  jmp     short loc_180023660
0x180023654  mov     ecx, [rbp+var_14]
0x180023657  test    edi, edi
0x180023659  jz      short loc_180023660
0x18002365b  cmp     ecx, 1
0x18002365e  ja      short loc_180023630
0x180023660  mov     rax, [rbp+arg_20]
0x180023664  mov     bl, 1
0x180023666  mov     [rax], ecx
0x180023668  jmp     short loc_180023630
```
