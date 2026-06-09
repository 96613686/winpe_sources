# DeclaredConfigurationStore_PersistScheduleRecord(ushort const *)

- ea: `0x1400649a8`
- end: `0x140064aef`
- name: `?DeclaredConfigurationStore_PersistScheduleRecord@@YAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140064c78`

## callees

- `0x1400649a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400649df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400649df`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140064abd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140064abd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064a0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064ad5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064a0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064ad5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140064a72`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140064a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400649fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400649fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064a1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064a1d`

## string_xrefs

- `0x140064aae`: `DCConfigRefresh`

## pseudocode

```c
__int64 __fastcall DeclaredConfigurationStore_PersistScheduleRecord(const unsigned __int16 *a1)
{
  HKEY v1; // rdi
  DWORD LastError; // ebx
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  const unsigned __int16 *Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey) != 2 )
    goto LABEL_7;
  v1 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v1);
    SetLastError(LastError);
  }
  hKey = 0;
  v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20106u, 0, &hKey, 0);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
LABEL_7:
    LODWORD(Data) = 1;
    v4 = RegSetValueExW(hKey, L"DCConfigRefresh", 0, 4u, (const BYTE *)&Data, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1400649a8  mov     r11, rsp
0x1400649ab  mov     [r11+18h], rbx
0x1400649af  mov     [r11+8], rcx
0x1400649b3  push    rdi
0x1400649b4  sub     rsp, 50h
0x1400649b8  mov     rdx, cs:lpSubKey; lpSubKey
0x1400649bf  lea     rax, [r11+10h]
0x1400649c3  mov     r9d, 0F003Fh; samDesired
0x1400649c9  mov     [r11-38h], rax
0x1400649cd  xor     r8d, r8d; ulOptions
0x1400649d0  mov     qword ptr [r11+10h], 0
0x1400649d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400649df  call    cs:__imp_RegOpenKeyExW
0x1400649e6  nop     dword ptr [rax+rax+00h]
0x1400649eb  cmp     eax, 2
0x1400649ee  jnz     loc_140064A91
0x1400649f4  mov     rdi, [rsp+58h+hKey]
0x1400649f9  test    rdi, rdi
0x1400649fc  jz      short loc_140064A29
0x1400649fe  call    cs:__imp_GetLastError
0x140064a05  nop     dword ptr [rax+rax+00h]
0x140064a0a  mov     rcx, rdi; hKey
0x140064a0d  mov     ebx, eax
0x140064a0f  call    cs:__imp_RegCloseKey
0x140064a16  nop     dword ptr [rax+rax+00h]
0x140064a1b  mov     ecx, ebx; dwErrCode
0x140064a1d  call    cs:__imp_SetLastError
0x140064a24  nop     dword ptr [rax+rax+00h]
0x140064a29  mov     rdx, cs:lpSubKey; lpSubKey
0x140064a30  lea     rax, [rsp+58h+hKey]
0x140064a35  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x140064a3e  xor     r9d, r9d; lpClass
0x140064a41  mov     [rsp+58h+phkResult], rax; phkResult
0x140064a46  xor     r8d, r8d; Reserved
0x140064a49  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140064a52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140064a59  mov     [rsp+58h+samDesired], 20106h; samDesired
0x140064a61  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140064a69  mov     [rsp+58h+hKey], 0
0x140064a72  call    cs:__imp_RegCreateKeyExW
0x140064a79  nop     dword ptr [rax+rax+00h]
0x140064a7e  mov     ebx, eax
0x140064a80  test    eax, eax
0x140064a82  jz      short loc_140064A91
0x140064a84  jle     short loc_140064ACB
0x140064a86  movzx   ebx, ax
0x140064a89  or      ebx, 80070000h
0x140064a8f  jmp     short loc_140064ACB
0x140064a91  mov     rcx, [rsp+58h+hKey]; hKey
0x140064a96  lea     rax, [rsp+58h+Data]
0x140064a9b  mov     r9d, 4; dwType
0x140064aa1  mov     dword ptr [rsp+58h+Data], 1
0x140064aa9  mov     [rsp+58h+samDesired], r9d; cbData
0x140064aae  lea     rdx, aDcconfigrefres; "DCConfigRefresh"
0x140064ab5  xor     r8d, r8d; Reserved
0x140064ab8  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x140064abd  call    cs:__imp_RegSetValueExW
0x140064ac4  nop     dword ptr [rax+rax+00h]
0x140064ac9  mov     ebx, eax
0x140064acb  mov     rcx, [rsp+58h+hKey]; hKey
0x140064ad0  test    rcx, rcx
0x140064ad3  jz      short loc_140064AE1
0x140064ad5  call    cs:__imp_RegCloseKey
0x140064adc  nop     dword ptr [rax+rax+00h]
0x140064ae1  mov     eax, ebx
0x140064ae3  mov     rbx, [rsp+58h+arg_10]
0x140064ae8  add     rsp, 50h
0x140064aec  pop     rdi
0x140064aed  retn
```
