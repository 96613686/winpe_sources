# SanitizeUnimodemBlob

- ea: `0x1800c5ee8`
- end: `0x1800c5fbe`
- name: `SanitizeUnimodemBlob`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c5a2c`

## callees

- `0x1800c4f8c`
- `0x1800c5ee8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5f55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5f55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5f7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c5f7a`
- `rtutils!TracePrintfExA` at `0x1800c5f2e`
- `rtutils!TracePrintfExA` at `0x1800c5f2e`

## pseudocode

```c
__int64 __fastcall SanitizeUnimodemBlob(unsigned int *a1)
{
  int v1; // edi
  char *v2; // rbx
  __int64 v3; // rsi
  __int64 result; // rax
  int v5; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  v2 = (char *)a1 + *a1;
  hKey = 0;
  v5 = 0;
  v3 = *((unsigned int *)v2 + 13);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "SanitizeUnimodemBlob: mdm prot=%d", *(_DWORD *)&v2[v3 + 44] & 0xFFFF000);
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\RAS Phonebook", 0, 0x20019u, &hKey) )
  {
    GetRegDword(hKey, L"AllowOverrideSerialPort", &v5);
    RegCloseKey(hKey);
    v1 = v5;
  }
  *((_WORD *)v2 + 4) = 0;
  result = *((_DWORD *)v2 + 7) & 0xFFFFB044 | 0x13;
  *((_DWORD *)v2 + 7) = result;
  if ( !v1 )
  {
    *((_WORD *)v2 + 19) = 8;
    v2[40] = 0;
  }
  *(_DWORD *)&v2[v3 + 32] = 0;
  return result;
}

```

## disassembly

```asm
0x1800c5ee8  mov     rax, rsp
0x1800c5eeb  mov     [rax+18h], rbx
0x1800c5eef  mov     [rax+20h], rsi
0x1800c5ef3  push    rdi
0x1800c5ef4  sub     rsp, 30h
0x1800c5ef8  mov     ebx, [rcx]
0x1800c5efa  xor     edi, edi
0x1800c5efc  add     rbx, rcx
0x1800c5eff  mov     qword ptr [rax+10h], 0
0x1800c5f07  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c5f0d  mov     [rax+8], edi
0x1800c5f10  mov     esi, [rbx+34h]
0x1800c5f13  cmp     ecx, 0FFFFFFFFh
0x1800c5f16  jz      short loc_1800C5F34
0x1800c5f18  mov     r9d, [rsi+rbx+2Ch]
0x1800c5f1d  lea     r8, aSanitizeunimod; "SanitizeUnimodemBlob: mdm prot=%d"
0x1800c5f24  and     r9d, 0FFFF000h
0x1800c5f2b  lea     edx, [rdi+0Ch]; dwFlags
0x1800c5f2e  call    cs:__imp_TracePrintfExA
0x1800c5f34  lea     rax, [rsp+38h+hKey]
0x1800c5f39  mov     r9d, 20019h; samDesired
0x1800c5f3f  xor     r8d, r8d; ulOptions
0x1800c5f42  mov     [rsp+38h+phkResult], rax; phkResult
0x1800c5f47  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RAS Phonebook"
0x1800c5f4e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800c5f55  call    cs:__imp_RegOpenKeyExW
0x1800c5f5b  test    eax, eax
0x1800c5f5d  jnz     short loc_1800C5F84
0x1800c5f5f  mov     rcx, [rsp+38h+hKey]
0x1800c5f64  lea     r8, [rsp+38h+arg_0]
0x1800c5f69  lea     rdx, aAllowoverrides; "AllowOverrideSerialPort"
0x1800c5f70  call    GetRegDword
0x1800c5f75  mov     rcx, [rsp+38h+hKey]; hKey
0x1800c5f7a  call    cs:__imp_RegCloseKey
0x1800c5f80  mov     edi, [rsp+38h+arg_0]
0x1800c5f84  xor     eax, eax
0x1800c5f86  mov     [rbx+8], ax
0x1800c5f8a  mov     eax, [rbx+1Ch]
0x1800c5f8d  and     eax, 0FFFFB057h
0x1800c5f92  or      eax, 13h
0x1800c5f95  mov     [rbx+1Ch], eax
0x1800c5f98  test    edi, edi
0x1800c5f9a  jnz     short loc_1800C5FA6
0x1800c5f9c  mov     word ptr [rbx+26h], 8
0x1800c5fa2  mov     [rbx+28h], dil
0x1800c5fa6  mov     dword ptr [rsi+rbx+20h], 0
0x1800c5fae  mov     rbx, [rsp+38h+arg_10]
0x1800c5fb3  mov     rsi, [rsp+38h+arg_18]
0x1800c5fb8  add     rsp, 30h
0x1800c5fbc  pop     rdi
0x1800c5fbd  retn
```
