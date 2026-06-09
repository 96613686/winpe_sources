# DeleteMachineKeys(void)

- ea: `0x180019734`
- end: `0x1800197fd`
- name: `?DeleteMachineKeys@@YAJXZ`
- size: `201`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800196f8`
- `0x18001ad10`

## callees

- `0x180019734`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800197ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800197ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019762`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019762`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019788`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800197a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800197c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180019788`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800197a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800197c3`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 DeleteMachineKeys(void)
{
  unsigned int v0; // ebx
  LSTATUS v1; // eax
  int v2; // ebx
  LSTATUS v3; // eax
  LSTATUS v4; // ecx
  bool v5; // cc
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\uDRM", 0, 0x20006u, &hKey);
  if ( v1 != 2 )
  {
    if ( v1 )
    {
      if ( v1 <= 0 )
      {
        v0 = v1;
        goto LABEL_18;
      }
      v2 = (unsigned __int16)v1;
    }
    else
    {
      v3 = RegDeleteValueW(hKey, L"MK");
      v4 = 0;
      if ( v3 != 2 )
        v4 = v3;
      v5 = v4 <= 0;
      if ( !v4 )
      {
        v6 = RegDeleteValueW(hKey, L"SK");
        v4 = v6;
        if ( v6 == 2 || !v6 )
        {
          v7 = RegDeleteValueW(hKey, L"TK");
          v4 = v7;
          if ( v7 == 2 || !v7 )
            goto LABEL_18;
        }
        v5 = v4 <= 0;
      }
      if ( v5 )
      {
        v0 = v4;
        goto LABEL_18;
      }
      v2 = (unsigned __int16)v4;
    }
    v0 = v2 | 0x80070000;
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180019734  push    rbx
0x180019736  sub     rsp, 30h
0x18001973a  lea     rax, [rsp+38h+hKey]
0x18001973f  xor     ebx, ebx
0x180019741  mov     r9d, 20006h; samDesired
0x180019747  mov     [rsp+38h+hKey], rbx
0x18001974c  xor     r8d, r8d; ulOptions
0x18001974f  mov     [rsp+38h+phkResult], rax; phkResult
0x180019754  lea     rdx, ?g_wszDPAPI_Path@@3QBGB; "Software\\Microsoft\\uDRM"
0x18001975b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180019762  call    cs:__imp_RegOpenKeyExW
0x180019768  cmp     eax, 2
0x18001976b  jz      short loc_1800197E5
0x18001976d  test    eax, eax
0x18001976f  jz      short loc_18001977C
0x180019771  jg      short loc_180019777
0x180019773  mov     ebx, eax
0x180019775  jmp     short loc_1800197E5
0x180019777  movzx   ebx, ax
0x18001977a  jmp     short loc_1800197DF
0x18001977c  mov     rcx, [rsp+38h+hKey]; hKey
0x180019781  lea     rdx, ?g_wszDPAPI_MK_Key@@3QBGB; "MK"
0x180019788  call    cs:__imp_RegDeleteValueW
0x18001978e  xor     ecx, ecx
0x180019790  cmp     eax, 2
0x180019793  cmovnz  ecx, eax
0x180019796  test    ecx, ecx
0x180019798  jnz     short loc_1800197D6
0x18001979a  mov     rcx, [rsp+38h+hKey]; hKey
0x18001979f  lea     rdx, ?g_wszDPAPI_SK_Key@@3QBGB; "SK"
0x1800197a6  call    cs:__imp_RegDeleteValueW
0x1800197ac  mov     ecx, eax
0x1800197ae  cmp     eax, 2
0x1800197b1  jz      short loc_1800197B7
0x1800197b3  test    eax, eax
0x1800197b5  jnz     short loc_1800197D4
0x1800197b7  mov     rcx, [rsp+38h+hKey]; hKey
0x1800197bc  lea     rdx, ?g_wszDPAPI_TK_Key@@3QBGB; "TK"
0x1800197c3  call    cs:__imp_RegDeleteValueW
0x1800197c9  mov     ecx, eax
0x1800197cb  cmp     eax, 2
0x1800197ce  jz      short loc_1800197E5
0x1800197d0  test    eax, eax
0x1800197d2  jz      short loc_1800197E5
0x1800197d4  test    ecx, ecx
0x1800197d6  jg      short loc_1800197DC
0x1800197d8  mov     ebx, ecx
0x1800197da  jmp     short loc_1800197E5
0x1800197dc  movzx   ebx, cx
0x1800197df  or      ebx, 80070000h
0x1800197e5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800197ea  test    rcx, rcx
0x1800197ed  jz      short loc_1800197F5
0x1800197ef  call    cs:__imp_RegCloseKey
0x1800197f5  mov     eax, ebx
0x1800197f7  add     rsp, 30h
0x1800197fb  pop     rbx
0x1800197fc  retn
```
