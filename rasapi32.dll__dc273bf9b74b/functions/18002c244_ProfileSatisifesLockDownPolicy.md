# ProfileSatisifesLockDownPolicy

- ea: `0x18002c244`
- end: `0x18002c39d`
- name: `ProfileSatisifesLockDownPolicy`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180029cd0`

## callees

- `0x180009dd0`
- `0x18002c244`
- `0x18004eab4`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c2cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c2cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c37a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c37a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c319`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c319`

## string_xrefs

- `0x18002c2a1`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18002c2b3`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`

## pseudocode

```c
__int64 __fastcall ProfileSatisifesLockDownPolicy(__int64 a1, wchar_t *a2)
{
  int v4; // eax
  const WCHAR *v5; // rdx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  BYTE *v8; // rax
  __int64 v9; // rdi
  int v10; // r8d
  int v11; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  memset_0(Data, 0, 0x105u);
  v4 = StateSepEnabled();
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  if ( !v4 )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hKey);
  v7 = v6;
  if ( v6
    || (cbData = 520, v6 = RegQueryValueExW(hKey, L"LockDownProfileEntryName", 0, &Type, Data, &cbData), (v7 = v6) != 0) )
  {
    if ( v6 != 2 )
      goto LABEL_15;
    goto LABEL_5;
  }
  if ( Type - 1 > 1 || !*(_WORD *)Data )
    goto LABEL_5;
  v8 = Data;
  v9 = a1 - (_QWORD)Data;
  do
  {
    v10 = *(unsigned __int16 *)&v8[v9];
    v11 = *(unsigned __int16 *)v8 - v10;
    if ( v11 )
      break;
    v8 += 2;
  }
  while ( v10 );
  if ( !v11 && (unsigned int)IsPublicPhonebook(a2) )
  {
LABEL_5:
    v7 = 0;
    goto LABEL_15;
  }
  v7 = 5;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18002c244  push    rbp
0x18002c246  push    rbx
0x18002c247  push    rsi
0x18002c248  push    rdi
0x18002c249  lea     rbp, [rsp-168h]
0x18002c251  sub     rsp, 268h
0x18002c258  mov     rax, cs:__security_cookie
0x18002c25f  xor     rax, rsp
0x18002c262  mov     [rbp+180h+var_30], rax
0x18002c269  mov     rsi, rdx
0x18002c26c  mov     [rsp+280h+cbData], 0
0x18002c274  mov     rdi, rcx
0x18002c277  mov     [rsp+280h+Type], 0
0x18002c27f  xor     edx, edx; Val
0x18002c281  mov     [rsp+280h+hKey], 0
0x18002c28a  lea     rcx, [rsp+280h+Data]; void *
0x18002c28f  mov     r8d, 105h; Size
0x18002c295  call    memset_0
0x18002c29a  call    StateSepEnabled
0x18002c29f  test    eax, eax
0x18002c2a1  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18002c2a8  lea     rax, [rsp+280h+hKey]
0x18002c2ad  mov     r9d, 20019h; samDesired
0x18002c2b3  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18002c2ba  mov     [rsp+280h+phkResult], rax; phkResult
0x18002c2bf  cmovz   rdx, rcx; lpSubKey
0x18002c2c3  xor     r8d, r8d; ulOptions
0x18002c2c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c2cd  call    cs:__imp_RegOpenKeyExW
0x18002c2d3  mov     ebx, eax
0x18002c2d5  test    eax, eax
0x18002c2d7  jz      short loc_18002C2E9
0x18002c2d9  cmp     eax, 2
0x18002c2dc  jnz     loc_18002C370
0x18002c2e2  xor     ebx, ebx
0x18002c2e4  jmp     loc_18002C370
0x18002c2e9  mov     rcx, [rsp+280h+hKey]; hKey
0x18002c2ee  lea     rax, [rsp+280h+cbData]
0x18002c2f3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18002c2f8  lea     r9, [rsp+280h+Type]; lpType
0x18002c2fd  lea     rax, [rsp+280h+Data]
0x18002c302  mov     [rsp+280h+cbData], 208h
0x18002c30a  xor     r8d, r8d; lpReserved
0x18002c30d  mov     [rsp+280h+phkResult], rax; lpData
0x18002c312  lea     rdx, ValueName; "LockDownProfileEntryName"
0x18002c319  call    cs:__imp_RegQueryValueExW
0x18002c31f  mov     ebx, eax
0x18002c321  test    eax, eax
0x18002c323  jnz     short loc_18002C2D9
0x18002c325  mov     eax, [rsp+280h+Type]
0x18002c329  dec     eax
0x18002c32b  cmp     eax, 1
0x18002c32e  ja      short loc_18002C2E2
0x18002c330  xor     eax, eax
0x18002c332  cmp     word ptr [rsp+280h+Data], ax
0x18002c337  jz      short loc_18002C2E2
0x18002c339  lea     rax, [rsp+280h+Data]
0x18002c33e  sub     rdi, rax
0x18002c341  movzx   edx, word ptr [rax]
0x18002c344  movzx   r8d, word ptr [rax+rdi]
0x18002c349  sub     edx, r8d
0x18002c34c  jnz     short loc_18002C357
0x18002c34e  add     rax, 2
0x18002c352  test    r8d, r8d
0x18002c355  jnz     short loc_18002C341
0x18002c357  test    edx, edx
0x18002c359  jnz     short loc_18002C36B
0x18002c35b  mov     rcx, rsi
0x18002c35e  call    IsPublicPhonebook
0x18002c363  test    eax, eax
0x18002c365  jnz     loc_18002C2E2
0x18002c36b  mov     ebx, 5
0x18002c370  mov     rcx, [rsp+280h+hKey]; hKey
0x18002c375  test    rcx, rcx
0x18002c378  jz      short loc_18002C380
0x18002c37a  call    cs:__imp_RegCloseKey
0x18002c380  mov     eax, ebx
0x18002c382  mov     rcx, [rbp+180h+var_30]
0x18002c389  xor     rcx, rsp; StackCookie
0x18002c38c  call    __security_check_cookie
0x18002c391  add     rsp, 268h
0x18002c398  pop     rdi
0x18002c399  pop     rsi
0x18002c39a  pop     rbx
0x18002c39b  pop     rbp
0x18002c39c  retn
```
