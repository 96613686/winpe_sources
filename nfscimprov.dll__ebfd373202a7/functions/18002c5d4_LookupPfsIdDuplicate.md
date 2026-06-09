# LookupPfsIdDuplicate

- ea: `0x18002c5d4`
- end: `0x18002c777`
- name: `LookupPfsIdDuplicate`
- size: `419`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002bd00`
- `0x18002c780`

## callees

- `0x18002c5d4`
- `0x18002c780`
- `0x18002ccf4`
- `0x180035b40`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18002c6e5`
- `ADVAPI32!RegEnumKeyExW` at `0x18002c6e5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002c67f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002c67f`
- `CLUSAPI!ClusterRegQueryInfoKey` at `0x18002c640`
- `CLUSAPI!ClusterRegQueryInfoKey` at `0x18002c640`
- `CLUSAPI!ClusterRegEnumKey` at `0x18002c6c9`
- `CLUSAPI!ClusterRegEnumKey` at `0x18002c6c9`

## pseudocode

```c
int __fastcall LookupPfsIdDuplicate(HKEY hKey, char a2, int a3)
{
  int result; // eax
  __int64 v7; // rdx
  DWORD v8; // ecx
  DWORD i; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  int v13; // [rsp+6Ch] [rbp-94h]
  WCHAR szName[256]; // [rsp+70h] [rbp-90h] BYREF

  cchName = 0;
  cSubKeys = 0;
  cValues = 0;
  if ( a2 )
    result = ClusterRegQueryInfoKey(hKey, &cSubKeys, 0, &cValues, 0, 0, 0, 0);
  else
    result = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0);
  if ( !result )
  {
    v8 = cSubKeys;
    if ( !cSubKeys )
      goto LABEL_18;
    for ( i = 0; i < v8; ++i )
    {
      if ( result )
        return result;
      cchName = 255;
      if ( a2 )
        result = ClusterRegEnumKey(hKey, i, szName, &cchName, 0);
      else
        result = RegEnumKeyExW(hKey, i, szName, &cchName, 0, 0, 0, 0);
      if ( result == 259 )
      {
        result = 0;
        goto LABEL_18;
      }
      if ( !result )
        result = LookupPfsIdDuplicateRecursive(hKey, a2, szName);
      v8 = cSubKeys;
    }
    if ( !result )
    {
LABEL_18:
      if ( cValues )
      {
        v13 = 0;
        LOBYTE(v7) = a2;
        result = QueryPFsIdKeyValue(hKey, v7);
        if ( result == 2 )
        {
          return 0;
        }
        else if ( !result && a3 == v13 )
        {
          return 183;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c5d4  mov     [rsp-8+arg_18], rbx
0x18002c5d9  push    rbp
0x18002c5da  push    rsi
0x18002c5db  push    rdi
0x18002c5dc  push    r14
0x18002c5de  push    r15
0x18002c5e0  lea     rbp, [rsp-180h]
0x18002c5e8  sub     rsp, 280h
0x18002c5ef  mov     rax, cs:__security_cookie
0x18002c5f6  xor     rax, rsp
0x18002c5f9  mov     [rbp+1A0h+var_30], rax
0x18002c600  xor     r15d, r15d
0x18002c603  mov     r14d, r8d
0x18002c606  xor     r8d, r8d; lpcchClass
0x18002c609  mov     [rsp+2A0h+cchName], r15d
0x18002c60e  mov     [rsp+2A0h+cSubKeys], r15d
0x18002c613  mov     sil, dl
0x18002c616  mov     [rsp+2A0h+cValues], r15d
0x18002c61b  mov     rdi, rcx
0x18002c61e  test    dl, dl
0x18002c620  jz      short loc_18002C648
0x18002c622  mov     [rsp+2A0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002c627  lea     r9, [rsp+2A0h+cValues]; lpcValues
0x18002c62c  mov     [rsp+2A0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002c631  lea     rdx, [rsp+2A0h+cSubKeys]; lpcSubKeys
0x18002c636  mov     [rsp+2A0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18002c63b  mov     [rsp+2A0h+lpcchMaxValueNameLen], r15; lpcchMaxValueNameLen
0x18002c640  call    cs:__imp_ClusterRegQueryInfoKey
0x18002c646  jmp     short loc_18002C685
0x18002c648  mov     [rsp+2A0h+var_248], r15; lpftLastWriteTime
0x18002c64d  lea     rax, [rsp+2A0h+cValues]
0x18002c652  mov     [rsp+2A0h+var_250], r15; lpcbSecurityDescriptor
0x18002c657  xor     r9d, r9d; lpReserved
0x18002c65a  mov     [rsp+2A0h+var_258], r15; lpcbMaxValueLen
0x18002c65f  xor     edx, edx; lpClass
0x18002c661  mov     [rsp+2A0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18002c666  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpcValues
0x18002c66b  lea     rax, [rsp+2A0h+cSubKeys]
0x18002c670  mov     [rsp+2A0h+lpcbSecurityDescriptor], r15; lpcbMaxClassLen
0x18002c675  mov     [rsp+2A0h+lpcbMaxValueLen], r15; lpcbMaxSubKeyLen
0x18002c67a  mov     [rsp+2A0h+lpcchMaxValueNameLen], rax; lpcSubKeys
0x18002c67f  call    cs:__imp_RegQueryInfoKeyW
0x18002c685  test    eax, eax
0x18002c687  jnz     loc_18002C751
0x18002c68d  mov     ecx, [rsp+2A0h+cSubKeys]
0x18002c691  test    ecx, ecx
0x18002c693  jz      loc_18002C71A
0x18002c699  mov     ebx, r15d
0x18002c69c  cmp     ebx, ecx
0x18002c69e  jnb     short loc_18002C716
0x18002c6a0  test    eax, eax
0x18002c6a2  jnz     loc_18002C751
0x18002c6a8  mov     [rsp+2A0h+cchName], 0FFh
0x18002c6b0  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18002c6b5  lea     r8, [rsp+2A0h+szName]; lpName
0x18002c6ba  mov     edx, ebx; dwIndex
0x18002c6bc  mov     rcx, rdi; hKey
0x18002c6bf  test    sil, sil
0x18002c6c2  jz      short loc_18002C6D1
0x18002c6c4  mov     [rsp+2A0h+lpcchMaxValueNameLen], r15; lpftLastWriteTime
0x18002c6c9  call    cs:__imp_ClusterRegEnumKey
0x18002c6cf  jmp     short loc_18002C6EB
0x18002c6d1  mov     [rsp+2A0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002c6d6  mov     [rsp+2A0h+lpcbSecurityDescriptor], r15; lpcchClass
0x18002c6db  mov     [rsp+2A0h+lpcbMaxValueLen], r15; lpClass
0x18002c6e0  mov     [rsp+2A0h+lpcchMaxValueNameLen], r15; lpReserved
0x18002c6e5  call    cs:__imp_RegEnumKeyExW
0x18002c6eb  cmp     eax, 103h
0x18002c6f0  jz      short loc_18002C711
0x18002c6f2  test    eax, eax
0x18002c6f4  jnz     short loc_18002C709
0x18002c6f6  mov     r9d, r14d
0x18002c6f9  lea     r8, [rsp+2A0h+szName]
0x18002c6fe  mov     dl, sil
0x18002c701  mov     rcx, rdi
0x18002c704  call    LookupPfsIdDuplicateRecursive
0x18002c709  mov     ecx, [rsp+2A0h+cSubKeys]
0x18002c70d  inc     ebx
0x18002c70f  jmp     short loc_18002C69C
0x18002c711  mov     eax, r15d
0x18002c714  jmp     short loc_18002C71A
0x18002c716  test    eax, eax
0x18002c718  jnz     short loc_18002C751
0x18002c71a  cmp     [rsp+2A0h+cValues], r15d
0x18002c71f  jz      short loc_18002C751
0x18002c721  lea     r8, [rsp+2A0h+var_234]
0x18002c726  mov     [rsp+2A0h+var_234], r15d
0x18002c72b  mov     dl, sil
0x18002c72e  mov     rcx, rdi
0x18002c731  call    QueryPFsIdKeyValue
0x18002c736  cmp     eax, 2
0x18002c739  jnz     short loc_18002C740
0x18002c73b  mov     eax, r15d
0x18002c73e  jmp     short loc_18002C751
0x18002c740  test    eax, eax
0x18002c742  jnz     short loc_18002C751
0x18002c744  cmp     r14d, [rsp+2A0h+var_234]
0x18002c749  mov     ecx, 0B7h
0x18002c74e  cmovz   eax, ecx
0x18002c751  mov     rcx, [rbp+1A0h+var_30]
0x18002c758  xor     rcx, rsp; StackCookie
0x18002c75b  call    __security_check_cookie
0x18002c760  mov     rbx, [rsp+2A0h+arg_18]
0x18002c768  add     rsp, 280h
0x18002c76f  pop     r15
0x18002c771  pop     r14
0x18002c773  pop     rdi
0x18002c774  pop     rsi
0x18002c775  pop     rbp
0x18002c776  retn
```
