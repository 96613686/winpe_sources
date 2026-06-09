# CreateMigrationRegistryForProvider

- ea: `0x1800317c8`
- end: `0x180031911`
- name: `CreateMigrationRegistryForProvider`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032294`

## callees

- `0x1800317c8`
- `0x1800327cc`
- `0x18003592c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031825`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031825`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031876`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800318bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031876`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800318bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800318e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800318e8`

## string_xrefs

- `0x180031837`: `Failed to open provider's key`
- `0x180031888`: `Failed to write protocol info 1.1`
- `0x1800318cd`: `Failed to write Winsock 2.0 provider ID`

## pseudocode

```c
__int64 __fastcall CreateMigrationRegistryForProvider(
        HKEY a1,
        int a2,
        const WCHAR *a3,
        int a4,
        BYTE *lpData,
        DWORD cbData,
        BYTE *a7)
{
  unsigned int v11; // eax
  unsigned int v12; // ebx
  const wchar_t *v13; // rdx
  DWORD v15; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF

  v15 = 0;
  hKey = 0;
  v11 = RegCreateKeyExW(a1, a3, 0, (LPWSTR)&Data, 0, 0x2001Fu, 0, &hKey, &v15);
  v12 = v11;
  if ( v11 )
  {
    v13 = L"Failed to open provider's key";
  }
  else if ( a4
         || a2
         || (v11 = RegSetValueExW(hKey, L"WinSock 1.1 Provider Data", 0, 3u, lpData, cbData), (v12 = v11) == 0) )
  {
    v11 = RegSetValueExW(hKey, L"WinSock 2.0 Provider ID", 0, 3u, a7, 0x10u);
    v12 = v11;
    if ( !v11 )
      goto LABEL_10;
    v13 = L"Failed to write Winsock 2.0 provider ID";
  }
  else
  {
    v13 = L"Failed to write protocol info 1.1";
  }
  LogErrorWithProvider(v11, v13, a3);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v12 )
    RecursivelyDeleteRegistryTree(a1, a3);
  return v12;
}

```

## disassembly

```asm
0x1800317c8  mov     r11, rsp
0x1800317cb  push    rbx
0x1800317cc  push    rbp
0x1800317cd  push    rsi
0x1800317ce  push    rdi
0x1800317cf  push    r14
0x1800317d1  sub     rsp, 60h
0x1800317d5  lea     rax, [r11-38h]
0x1800317d9  mov     [rsp+88h+var_38], 0
0x1800317e1  mov     [r11-48h], rax
0x1800317e5  mov     rdi, r8
0x1800317e8  lea     rax, [r11-30h]
0x1800317ec  mov     qword ptr [r11-30h], 0
0x1800317f4  mov     [r11-50h], rax
0x1800317f8  mov     ebp, r9d
0x1800317fb  mov     qword ptr [r11-58h], 0
0x180031803  lea     r9, Data; lpClass
0x18003180a  mov     esi, edx
0x18003180c  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x180031814  xor     r8d, r8d; Reserved
0x180031817  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18003181f  mov     rdx, rdi; lpSubKey
0x180031822  mov     r14, rcx
0x180031825  call    cs:__imp_RegCreateKeyExW
0x18003182c  nop     dword ptr [rax+rax+00h]
0x180031831  mov     ebx, eax
0x180031833  test    eax, eax
0x180031835  jz      short loc_180031843
0x180031837  lea     rdx, aFailedToOpenPr_0; "Failed to open provider's key"
0x18003183e  jmp     loc_1800318D4
0x180031843  test    ebp, ebp
0x180031845  jnz     short loc_180031891
0x180031847  test    esi, esi
0x180031849  jnz     short loc_180031891
0x18003184b  mov     eax, [rsp+88h+cbData]
0x180031852  lea     r9d, [rbp+3]; dwType
0x180031856  mov     rcx, [rsp+88h+hKey]; hKey
0x18003185b  lea     rdx, aWinsock11Provi; "WinSock 1.1 Provider Data"
0x180031862  mov     [rsp+88h+samDesired], eax; cbData
0x180031866  xor     r8d, r8d; Reserved
0x180031869  mov     rax, [rsp+88h+lpData]
0x180031871  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180031876  call    cs:__imp_RegSetValueExW
0x18003187d  nop     dword ptr [rax+rax+00h]
0x180031882  mov     ebx, eax
0x180031884  test    eax, eax
0x180031886  jz      short loc_180031891
0x180031888  lea     rdx, aFailedToWriteP; "Failed to write protocol info 1.1"
0x18003188f  jmp     short loc_1800318D4
0x180031891  mov     rax, [rsp+88h+arg_30]
0x180031899  lea     rdx, aWinsock20Provi; "WinSock 2.0 Provider ID"
0x1800318a0  mov     rcx, [rsp+88h+hKey]; hKey
0x1800318a5  mov     r9d, 3; dwType
0x1800318ab  mov     [rsp+88h+samDesired], 10h; cbData
0x1800318b3  xor     r8d, r8d; Reserved
0x1800318b6  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1800318bb  call    cs:__imp_RegSetValueExW
0x1800318c2  nop     dword ptr [rax+rax+00h]
0x1800318c7  mov     ebx, eax
0x1800318c9  test    eax, eax
0x1800318cb  jz      short loc_1800318DE
0x1800318cd  lea     rdx, aFailedToWriteW; "Failed to write Winsock 2.0 provider ID"
0x1800318d4  mov     r8, rdi
0x1800318d7  mov     ecx, eax
0x1800318d9  call    LogErrorWithProvider
0x1800318de  mov     rcx, [rsp+88h+hKey]; hKey
0x1800318e3  test    rcx, rcx
0x1800318e6  jz      short loc_1800318F4
0x1800318e8  call    cs:__imp_RegCloseKey
0x1800318ef  nop     dword ptr [rax+rax+00h]
0x1800318f4  test    ebx, ebx
0x1800318f6  jz      short loc_180031903
0x1800318f8  mov     rdx, rdi
0x1800318fb  mov     rcx, r14
0x1800318fe  call    RecursivelyDeleteRegistryTree
0x180031903  mov     eax, ebx
0x180031905  add     rsp, 60h
0x180031909  pop     r14
0x18003190b  pop     rdi
0x18003190c  pop     rsi
0x18003190d  pop     rbp
0x18003190e  pop     rbx
0x18003190f  retn
```
