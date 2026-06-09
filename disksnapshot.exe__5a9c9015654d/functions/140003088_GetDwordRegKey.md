# GetDwordRegKey

- ea: `0x140003088`
- end: `0x14000314e`
- name: `GetDwordRegKey`
- size: `198`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400032c4`

## callees

- `0x140003088`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000313e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000313e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003122`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003122`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400030dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400030dd`

## pseudocode

```c
__int64 __fastcall GetDwordRegKey(__int64 a1, const WCHAR *a2, const WCHAR *a3, _DWORD *a4)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  bool v8; // cc
  __int64 Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  Data = a1;
  *a4 = 0;
  v8 = *((_QWORD *)a2 + 3) <= 7u;
  hKey = 0;
  LODWORD(Data) = 0;
  cbData = 4;
  if ( !v8 )
    a2 = *(const WCHAR **)a2;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
    goto LABEL_4;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v6 = RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)&Data, &cbData);
  v7 = v6;
  v8 = v6 <= 0;
  if ( v6 )
  {
LABEL_4:
    if ( !v8 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    *a4 = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x140003088  mov     rax, rsp
0x14000308b  mov     [rax+8], rcx
0x14000308f  push    rbx
0x140003090  push    rsi
0x140003091  push    rdi
0x140003092  sub     rsp, 30h
0x140003096  mov     dword ptr [r9], 0
0x14000309d  mov     rsi, r9
0x1400030a0  cmp     qword ptr [rdx+18h], 7
0x1400030a5  mov     rdi, r8
0x1400030a8  mov     qword ptr [rax+20h], 0
0x1400030b0  mov     dword ptr [rax+8], 0
0x1400030b7  mov     dword ptr [rax+10h], 4
0x1400030be  jbe     short loc_1400030C3
0x1400030c0  mov     rdx, [rdx]; lpSubKey
0x1400030c3  lea     rax, [rsp+48h+hKey]
0x1400030c8  mov     r9d, 20019h; samDesired
0x1400030ce  xor     r8d, r8d; ulOptions
0x1400030d1  mov     [rsp+48h+phkResult], rax; phkResult
0x1400030d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400030dd  call    cs:__imp_RegOpenKeyExW
0x1400030e3  mov     ebx, eax
0x1400030e5  test    eax, eax
0x1400030e7  jz      short loc_1400030F6
0x1400030e9  jle     short loc_140003134
0x1400030eb  movzx   ebx, ax
0x1400030ee  or      ebx, 80070000h
0x1400030f4  jmp     short loc_140003134
0x1400030f6  cmp     qword ptr [rdi+18h], 7
0x1400030fb  jbe     short loc_140003100
0x1400030fd  mov     rdi, [rdi]
0x140003100  mov     rcx, [rsp+48h+hKey]; hKey
0x140003105  lea     rax, [rsp+48h+cbData]
0x14000310a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x14000310f  xor     r9d, r9d; lpType
0x140003112  lea     rax, [rsp+48h+Data]
0x140003117  xor     r8d, r8d; lpReserved
0x14000311a  mov     rdx, rdi; lpValueName
0x14000311d  mov     [rsp+48h+phkResult], rax; lpData
0x140003122  call    cs:__imp_RegQueryValueExW
0x140003128  mov     ebx, eax
0x14000312a  test    eax, eax
0x14000312c  jnz     short loc_1400030E9
0x14000312e  mov     ecx, dword ptr [rsp+48h+Data]
0x140003132  mov     [rsi], ecx
0x140003134  mov     rcx, [rsp+48h+hKey]; hKey
0x140003139  test    rcx, rcx
0x14000313c  jz      short loc_140003144
0x14000313e  call    cs:__imp_RegCloseKey
0x140003144  mov     eax, ebx
0x140003146  add     rsp, 30h
0x14000314a  pop     rdi
0x14000314b  pop     rsi
0x14000314c  pop     rbx
0x14000314d  retn
```
