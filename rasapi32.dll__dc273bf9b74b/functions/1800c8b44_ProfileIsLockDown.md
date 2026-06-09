# ProfileIsLockDown

- ea: `0x1800c8b44`
- end: `0x1800c8c94`
- name: `ProfileIsLockDown`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800cbe28`

## callees

- `0x180009dd0`
- `0x18004eab4`
- `0x1800c8b44`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8bd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c8bd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c8c65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c8c12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c8c12`

## string_xrefs

- `0x1800c8bac`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x1800c8bbe`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`

## pseudocode

```c
__int64 __fastcall ProfileIsLockDown(__int64 a1, wchar_t *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const WCHAR *v6; // rdx
  BYTE *v7; // rax
  __int64 v8; // rdi
  int v9; // r8d
  int v10; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  v4 = 0;
  memset_0(Data, 0, 0x105u);
  v5 = StateSepEnabled();
  v6 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !v5 )
    v6 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"LockDownProfileEntryName", 0, &Type, Data, &cbData) && Type - 1 <= 1 )
    {
      v7 = Data;
      v8 = a1 - (_QWORD)Data;
      do
      {
        v9 = *(unsigned __int16 *)&v7[v8];
        v10 = *(unsigned __int16 *)v7 - v9;
        if ( v10 )
          break;
        v7 += 2;
      }
      while ( v9 );
      if ( !v10 && (unsigned int)IsPublicPhonebook(a2) )
        v4 = 1;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800c8b44  mov     [rsp-8+arg_0], rbx
0x1800c8b49  mov     [rsp-8+arg_10], rsi
0x1800c8b4e  push    rbp
0x1800c8b4f  push    rdi
0x1800c8b50  push    r15
0x1800c8b52  lea     rbp, [rsp-160h]
0x1800c8b5a  sub     rsp, 260h
0x1800c8b61  mov     rax, cs:__security_cookie
0x1800c8b68  xor     rax, rsp
0x1800c8b6b  mov     [rbp+170h+var_20], rax
0x1800c8b72  mov     rsi, rdx
0x1800c8b75  mov     [rsp+270h+cbData], 0
0x1800c8b7d  mov     rdi, rcx
0x1800c8b80  mov     [rsp+270h+Type], 0
0x1800c8b88  xor     edx, edx; Val
0x1800c8b8a  mov     [rsp+270h+hKey], 0
0x1800c8b93  lea     rcx, [rsp+270h+Data]; void *
0x1800c8b98  mov     r8d, 105h; Size
0x1800c8b9e  xor     ebx, ebx
0x1800c8ba0  call    memset_0
0x1800c8ba5  call    StateSepEnabled
0x1800c8baa  test    eax, eax
0x1800c8bac  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800c8bb3  lea     rax, [rsp+270h+hKey]
0x1800c8bb8  mov     r9d, 20019h; samDesired
0x1800c8bbe  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800c8bc5  mov     [rsp+270h+phkResult], rax; phkResult
0x1800c8bca  cmovz   rdx, rcx; lpSubKey
0x1800c8bce  xor     r8d, r8d; ulOptions
0x1800c8bd1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c8bd8  call    cs:__imp_RegOpenKeyExW
0x1800c8bde  test    eax, eax
0x1800c8be0  jnz     short loc_1800C8C5B
0x1800c8be2  mov     rcx, [rsp+270h+hKey]; hKey
0x1800c8be7  lea     rax, [rsp+270h+cbData]
0x1800c8bec  mov     [rsp+270h+lpcbData], rax; lpcbData
0x1800c8bf1  lea     r9, [rsp+270h+Type]; lpType
0x1800c8bf6  lea     rax, [rsp+270h+Data]
0x1800c8bfb  mov     [rsp+270h+cbData], 208h
0x1800c8c03  xor     r8d, r8d; lpReserved
0x1800c8c06  mov     [rsp+270h+phkResult], rax; lpData
0x1800c8c0b  lea     rdx, ValueName; "LockDownProfileEntryName"
0x1800c8c12  call    cs:__imp_RegQueryValueExW
0x1800c8c18  test    eax, eax
0x1800c8c1a  jnz     short loc_1800C8C5B
0x1800c8c1c  mov     eax, [rsp+270h+Type]
0x1800c8c20  lea     r15d, [rbx+1]
0x1800c8c24  dec     eax
0x1800c8c26  cmp     eax, r15d
0x1800c8c29  ja      short loc_1800C8C5B
0x1800c8c2b  lea     rax, [rsp+270h+Data]
0x1800c8c30  sub     rdi, rax
0x1800c8c33  movzx   edx, word ptr [rax]
0x1800c8c36  movzx   r8d, word ptr [rax+rdi]
0x1800c8c3b  sub     edx, r8d
0x1800c8c3e  jnz     short loc_1800C8C49
0x1800c8c40  add     rax, 2
0x1800c8c44  test    r8d, r8d
0x1800c8c47  jnz     short loc_1800C8C33
0x1800c8c49  test    edx, edx
0x1800c8c4b  jnz     short loc_1800C8C5B
0x1800c8c4d  mov     rcx, rsi
0x1800c8c50  call    IsPublicPhonebook
0x1800c8c55  test    eax, eax
0x1800c8c57  cmovnz  ebx, r15d
0x1800c8c5b  mov     rcx, [rsp+270h+hKey]; hKey
0x1800c8c60  test    rcx, rcx
0x1800c8c63  jz      short loc_1800C8C6B
0x1800c8c65  call    cs:__imp_RegCloseKey
0x1800c8c6b  mov     eax, ebx
0x1800c8c6d  mov     rcx, [rbp+170h+var_20]
0x1800c8c74  xor     rcx, rsp; StackCookie
0x1800c8c77  call    __security_check_cookie
0x1800c8c7c  lea     r11, [rsp+270h+var_10]
0x1800c8c84  mov     rbx, [r11+20h]
0x1800c8c88  mov     rsi, [r11+30h]
0x1800c8c8c  mov     rsp, r11
0x1800c8c8f  pop     r15
0x1800c8c91  pop     rdi
0x1800c8c92  pop     rbp
0x1800c8c93  retn
```
