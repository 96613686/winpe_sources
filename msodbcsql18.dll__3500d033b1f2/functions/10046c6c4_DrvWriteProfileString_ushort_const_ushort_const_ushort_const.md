# DrvWriteProfileString(ushort const *,ushort const *,ushort const *)

- ea: `0x10046c6c4`
- end: `0x10046c7da`
- name: `?DrvWriteProfileString@@YAHPEBG00@Z`
- size: `278`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x10053f624`

## callees

- `0x10046c6c4`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x10046c776`
- `ADVAPI32!RegDeleteValueW` at `0x10046c776`
- `ADVAPI32!RegDeleteKeyW` at `0x10046c6eb`
- `ADVAPI32!RegDeleteKeyW` at `0x10046c6eb`
- `ADVAPI32!RegSetValueExW` at `0x10046c7af`
- `ADVAPI32!RegSetValueExW` at `0x10046c7af`
- `ADVAPI32!RegCreateKeyExW` at `0x10046c758`
- `ADVAPI32!RegCreateKeyExW` at `0x10046c758`
- `ADVAPI32!RegOpenKeyExW` at `0x10046c711`
- `ADVAPI32!RegOpenKeyExW` at `0x10046c711`
- `ADVAPI32!RegCloseKey` at `0x10046c7bf`
- `ADVAPI32!RegCloseKey` at `0x10046c7bf`

## pseudocode

```c
__int64 __fastcall DrvWriteProfileString(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *lpData)
{
  unsigned int v4; // ebx
  LSTATUS v8; // eax
  __int64 v9; // rax
  LSTATUS v10; // edi
  DWORD dwDisposition; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  if ( !lpValueName )
  {
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey);
    return 1;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey) )
  {
    if ( !lpData )
      return 1;
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
      return 0;
    goto LABEL_10;
  }
  if ( lpData )
  {
LABEL_10:
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&lpData[2 * v9] );
    v8 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v9 + 2);
    goto LABEL_13;
  }
  v8 = RegDeleteValueW(hKey, lpValueName);
LABEL_13:
  v10 = v8;
  RegCloseKey(hKey);
  LOBYTE(v4) = v10 == 0;
  return v4;
}

```

## disassembly

```asm
0x10046c6c4  mov     [rsp+arg_0], rbx
0x10046c6c9  push    rbp
0x10046c6ca  push    rdi
0x10046c6cb  push    r14
0x10046c6cd  sub     rsp, 50h
0x10046c6d1  mov     rbp, rcx
0x10046c6d4  xor     ebx, ebx
0x10046c6d6  test    rdx, rdx
0x10046c6d9  mov     r14, rdx
0x10046c6dc  mov     rdx, rbp; lpSubKey
0x10046c6df  mov     rdi, r8
0x10046c6e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10046c6e9  jnz     short loc_10046C6FB
0x10046c6eb  call    cs:__imp_RegDeleteKeyW
0x10046c6f1  mov     eax, 1
0x10046c6f6  jmp     loc_10046C7CC
0x10046c6fb  lea     rax, [rsp+68h+hKey]
0x10046c703  mov     r9d, 2001Fh; samDesired
0x10046c709  xor     r8d, r8d; ulOptions
0x10046c70c  mov     [rsp+68h+phkResult], rax; phkResult
0x10046c711  call    cs:__imp_RegOpenKeyExW
0x10046c717  test    eax, eax
0x10046c719  jz      short loc_10046C766
0x10046c71b  test    rdi, rdi
0x10046c71e  jz      short loc_10046C6F1
0x10046c720  lea     rax, [rsp+68h+dwDisposition]
0x10046c725  xor     r9d, r9d; lpClass
0x10046c728  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x10046c72d  xor     r8d, r8d; Reserved
0x10046c730  lea     rax, [rsp+68h+hKey]
0x10046c738  mov     rdx, rbp; lpSubKey
0x10046c73b  mov     [rsp+68h+var_30], rax; phkResult
0x10046c740  mov     rcx, 0FFFFFFFF80000002h; hKey
0x10046c747  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x10046c74c  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x10046c754  mov     dword ptr [rsp+68h+phkResult], ebx; dwOptions
0x10046c758  call    cs:__imp_RegCreateKeyExW
0x10046c75e  test    eax, eax
0x10046c760  jz      short loc_10046C77E
0x10046c762  xor     eax, eax
0x10046c764  jmp     short loc_10046C7CC
0x10046c766  test    rdi, rdi
0x10046c769  jnz     short loc_10046C77E
0x10046c76b  mov     rcx, [rsp+68h+hKey]; hKey
0x10046c773  mov     rdx, r14; lpValueName
0x10046c776  call    cs:__imp_RegDeleteValueW
0x10046c77c  jmp     short loc_10046C7B5
0x10046c77e  or      rax, 0FFFFFFFFFFFFFFFFh
0x10046c782  inc     rax
0x10046c785  cmp     [rdi+rax*2], bx
0x10046c789  jnz     short loc_10046C782
0x10046c78b  mov     rcx, [rsp+68h+hKey]; hKey
0x10046c793  lea     eax, ds:2[rax*2]
0x10046c79a  mov     [rsp+68h+samDesired], eax; cbData
0x10046c79e  mov     r9d, 1; dwType
0x10046c7a4  xor     r8d, r8d; Reserved
0x10046c7a7  mov     [rsp+68h+phkResult], rdi; lpData
0x10046c7ac  mov     rdx, r14; lpValueName
0x10046c7af  call    cs:__imp_RegSetValueExW
0x10046c7b5  mov     rcx, [rsp+68h+hKey]; hKey
0x10046c7bd  mov     edi, eax
0x10046c7bf  call    cs:__imp_RegCloseKey
0x10046c7c5  test    edi, edi
0x10046c7c7  setz    bl
0x10046c7ca  mov     eax, ebx
0x10046c7cc  mov     rbx, [rsp+68h+arg_0]
0x10046c7d1  add     rsp, 50h
0x10046c7d5  pop     r14
0x10046c7d7  pop     rdi
0x10046c7d8  pop     rbp
0x10046c7d9  retn
```
