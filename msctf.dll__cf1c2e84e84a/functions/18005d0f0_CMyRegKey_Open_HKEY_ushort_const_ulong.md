# CMyRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18005d0f0`
- end: `0x18005d18e`
- name: `?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `158`
- prototype: `int(CMyRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `37`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025490`
- `0x180026d28`
- `0x180048ccc`
- `0x180052aa8`
- `0x18005322c`
- `0x1800582ac`
- `0x180076428`
- `0x18007c39c`
- `0x180083b84`
- `0x180086068`
- `0x1800a5730`
- `0x1800a735c`
- `0x1800a77c0`
- `0x1800a7a50`
- `0x1800a7f90`
- `0x1800a8080`
- `0x1800a821c`
- `0x1800aa584`
- `0x1800b3654`
- `0x1800b3748`
- `0x1800b3954`
- `0x1800b3da0`
- `0x1800b3e6c`
- `0x1800bb878`
- `0x1800bc480`
- `0x1800cba4c`
- `0x1800cbc44`
- `0x1800cc114`
- `0x1800cc7cc`
- `0x1800d3608`
- `0x1800d4df4`
- `0x1800d5148`
- `0x1800d553c`
- `0x1800d5700`
- `0x1800d5b30`
- `0x1800d7a24`
- `0x1800e6f00`

## callees

- `0x18005d0f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d136`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d136`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d14b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d166`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d14b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d166`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005d17e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005d17e`

## pseudocode

```c
__int64 __fastcall CMyRegKey::Open(CMyRegKey *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  HKEY v6; // rbx
  unsigned int v8; // ebx
  HKEY v9; // rcx
  HKEY phkResult; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  phkResult = 0;
  hKey = 0;
  v6 = a2;
  if ( a2 == HKEY_CURRENT_USER && !RegOpenCurrentUser(a4, &hKey) )
    v6 = hKey;
  v8 = RegOpenKeyExW(v6, a3, 0, a4, &phkResult);
  if ( !v8 )
  {
    v9 = (HKEY)*((_QWORD *)this + 1);
    if ( v9 )
      v8 = RegCloseKey(v9);
    *((_QWORD *)this + 1) = phkResult;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18005d0f0  push    rbx
0x18005d0f2  push    rbp
0x18005d0f3  push    rsi
0x18005d0f4  push    rdi
0x18005d0f5  sub     rsp, 48h
0x18005d0f9  mov     [rsp+68h+var_38], 0
0x18005d102  mov     esi, r9d
0x18005d105  mov     [rsp+68h+hKey], 0
0x18005d10e  mov     rbp, r8
0x18005d111  mov     rbx, rdx
0x18005d114  mov     rdi, rcx
0x18005d117  cmp     rdx, 0FFFFFFFF80000001h
0x18005d11e  jz      short loc_18005D177
0x18005d120  lea     rax, [rsp+68h+var_38]
0x18005d125  mov     r9d, esi; samDesired
0x18005d128  xor     r8d, r8d; ulOptions
0x18005d12b  mov     [rsp+68h+phkResult], rax; phkResult
0x18005d130  mov     rdx, rbp; lpSubKey
0x18005d133  mov     rcx, rbx; hKey
0x18005d136  call    cs:__imp_RegOpenKeyExW
0x18005d13c  mov     ebx, eax
0x18005d13e  test    eax, eax
0x18005d140  jnz     short loc_18005D15C
0x18005d142  mov     rcx, [rdi+8]; hKey
0x18005d146  test    rcx, rcx
0x18005d149  jz      short loc_18005D153
0x18005d14b  call    cs:__imp_RegCloseKey
0x18005d151  mov     ebx, eax
0x18005d153  mov     rax, [rsp+68h+var_38]
0x18005d158  mov     [rdi+8], rax
0x18005d15c  mov     rcx, [rsp+68h+hKey]; hKey
0x18005d161  test    rcx, rcx
0x18005d164  jz      short loc_18005D16C
0x18005d166  call    cs:__imp_RegCloseKey
0x18005d16c  mov     eax, ebx
0x18005d16e  add     rsp, 48h
0x18005d172  pop     rdi
0x18005d173  pop     rsi
0x18005d174  pop     rbp
0x18005d175  pop     rbx
0x18005d176  retn
0x18005d177  lea     rdx, [rsp+68h+hKey]; phkResult
0x18005d17c  mov     ecx, esi; samDesired
0x18005d17e  call    cs:__imp_RegOpenCurrentUser
0x18005d184  test    eax, eax
0x18005d186  cmovz   rbx, [rsp+68h+hKey]
0x18005d18c  jmp     short loc_18005D120
```
