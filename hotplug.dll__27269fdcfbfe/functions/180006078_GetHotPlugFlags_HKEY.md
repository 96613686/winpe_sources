# GetHotPlugFlags(HKEY__ * *)

- ea: `0x180006078`
- end: `0x18000611b`
- name: `?GetHotPlugFlags@@YAKPEAPEAUHKEY__@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004114`
- `0x1800048d8`

## callees

- `0x180006078`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800060e7`
- `ADVAPI32!RegQueryValueExW` at `0x1800060e7`
- `ADVAPI32!RegCreateKeyW` at `0x1800060af`
- `ADVAPI32!RegCreateKeyW` at `0x1800060af`
- `ADVAPI32!RegCloseKey` at `0x1800060fe`
- `ADVAPI32!RegCloseKey` at `0x1800060fe`

## pseudocode

```c
__int64 __fastcall GetHotPlugFlags(HKEY *a1)
{
  LSTATUS v2; // edi
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 0;
  if ( RegCreateKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Applets\\SysTray", &hKey) )
    return 0;
  cbData = 4;
  v2 = RegQueryValueExW(hKey, szHotPlugFlags, 0, 0, (LPBYTE)&Data, &cbData);
  if ( a1 )
    *a1 = hKey;
  else
    RegCloseKey(hKey);
  if ( v2 )
    return 0;
  else
    return Data;
}

```

## disassembly

```asm
0x180006078  mov     rax, rsp
0x18000607b  mov     [rax+8], rbx
0x18000607f  push    rdi
0x180006080  sub     rsp, 30h
0x180006084  mov     rbx, rcx
0x180006087  mov     qword ptr [rax+20h], 0
0x18000608f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006096  mov     dword ptr [rax+18h], 0
0x18000609d  lea     r8, [rax+20h]; phkResult
0x1800060a1  mov     dword ptr [rax+10h], 0
0x1800060a8  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800060af  call    cs:__imp_RegCreateKeyW
0x1800060b5  test    eax, eax
0x1800060b7  jnz     short loc_18000610E
0x1800060b9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800060be  lea     rax, [rsp+38h+cbData]
0x1800060c3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800060c8  lea     rdx, ?szHotPlugFlags@@3PAGA; "HotPlugFlags"
0x1800060cf  lea     rax, [rsp+38h+Data]
0x1800060d4  mov     [rsp+38h+cbData], 4
0x1800060dc  xor     r9d, r9d; lpType
0x1800060df  mov     [rsp+38h+lpData], rax; lpData
0x1800060e4  xor     r8d, r8d; lpReserved
0x1800060e7  call    cs:__imp_RegQueryValueExW
0x1800060ed  mov     rcx, [rsp+38h+hKey]; hKey
0x1800060f2  mov     edi, eax
0x1800060f4  test    rbx, rbx
0x1800060f7  jz      short loc_1800060FE
0x1800060f9  mov     [rbx], rcx
0x1800060fc  jmp     short loc_180006104
0x1800060fe  call    cs:__imp_RegCloseKey
0x180006104  test    edi, edi
0x180006106  jnz     short loc_18000610E
0x180006108  mov     eax, [rsp+38h+Data]
0x18000610c  jmp     short loc_180006110
0x18000610e  xor     eax, eax
0x180006110  mov     rbx, [rsp+38h+arg_0]
0x180006115  add     rsp, 30h
0x180006119  pop     rdi
0x18000611a  retn
```
