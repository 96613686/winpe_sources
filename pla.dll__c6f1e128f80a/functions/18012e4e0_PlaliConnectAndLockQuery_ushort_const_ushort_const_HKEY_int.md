# PlaliConnectAndLockQuery(ushort const *,ushort const *,HKEY__ * *,int)

- ea: `0x18012e4e0`
- end: `0x18012e715`
- name: `?PlaliConnectAndLockQuery@@YAJPEBG0PEAPEAUHKEY__@@H@Z`
- size: `565`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, HKEY *, int)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a3370`
- `0x1800b16b0`
- `0x18012ec18`
- `0x18012f530`
- `0x180130b28`
- `0x180130e6c`
- `0x1801326c0`
- `0x180132960`

## callees

- `0x18012e4e0`
- `0x18012e71c`
- `0x18012f320`
- `0x1801317fc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18012e62c`
- `msvcrt!_wcsicmp` at `0x18012e666`
- `msvcrt!_wcsicmp` at `0x18012e62c`
- `msvcrt!_wcsicmp` at `0x18012e666`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e61a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012e61a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e67e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e6d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e67e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012e6d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012e57b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012e57b`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012e5e5`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012e5e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012e5b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012e5b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e5a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e69d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e6b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e5a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e69d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012e6b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012e6ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012e6bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012e6ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012e6bf`

## pseudocode

```c
__int64 __fastcall PlaliConnectAndLockQuery(wchar_t *a1, const unsigned __int16 *a2, HKEY *a3, int a4)
{
  DWORD v4; // r14d
  HKEY *v5; // r13
  LSTATUS v6; // ebx
  unsigned int v7; // esi
  wchar_t *v8; // rdi
  DWORD v9; // r12d
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // r15
  DWORD v12; // r12d
  HANDLE v13; // rax
  HANDLE v14; // rax
  DWORD cSubKeys; // [rsp+68h] [rbp-9h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-5h] BYREF
  unsigned int v18; // [rsp+70h] [rbp-1h] BYREF
  unsigned int v19; // [rsp+74h] [rbp+3h]
  HKEY hKey; // [rsp+78h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+Fh] BYREF
  wchar_t *String1; // [rsp+88h] [rbp+17h] BYREF

  v4 = 0;
  v5 = a3;
  *a3 = 0;
  phkResult = 0;
  v6 = 0;
  hKey = 0;
  v19 = PlaliConnectToRegistry(a1, &hKey, 1, a4);
  v7 = v19;
  if ( v19 )
    goto LABEL_18;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v6 )
    goto LABEL_18;
  v8 = 0;
  String1 = 0;
  v18 = 0;
  v9 = 2 * cbMaxSubKeyLen + 2;
  ProcessHeap = GetProcessHeap();
  v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
  if ( !v11 )
  {
    v6 = 14;
    goto LABEL_18;
  }
  v6 = 2;
  if ( !cSubKeys )
    goto LABEL_16;
  v12 = v9 >> 1;
  while ( 1 )
  {
    v6 = RegEnumKeyW(hKey, v4, v11, v12);
    if ( !v6 )
    {
      v6 = RegOpenKeyExW(hKey, v11, 0, a4 != 0 ? 131103 : 131097, &phkResult);
      if ( !v6 )
        break;
    }
LABEL_13:
    if ( ++v4 >= cSubKeys )
      goto LABEL_14;
  }
  if ( _wcsicmp(v11, a2) )
  {
    PlaliReadRegistryStringValue(phkResult, L"Collection Name", 1u, &String1, &v18);
    v8 = String1;
    if ( !String1 || _wcsicmp(String1, a2) )
    {
      v6 = 2;
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_13;
    }
  }
LABEL_14:
  v7 = v19;
  v5 = a3;
  if ( v8 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v8);
  }
LABEL_16:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v11);
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
  {
    if ( v7 )
      return v7;
    return PlaliErrorToPdhStatus(v6);
  }
  else
  {
    if ( !v7 )
    {
      *v5 = phkResult;
      return PlaliErrorToPdhStatus(v6);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x18012e4e0  mov     rax, rsp
0x18012e4e3  mov     [rax+8], rbx
0x18012e4e7  mov     [rax+20h], r9d
0x18012e4eb  mov     [rax+18h], r8
0x18012e4ef  mov     [rax+10h], rdx
0x18012e4f3  push    rbp
0x18012e4f4  push    rsi
0x18012e4f5  push    rdi
0x18012e4f6  push    r12
0x18012e4f8  push    r13
0x18012e4fa  push    r14
0x18012e4fc  push    r15
0x18012e4fe  lea     rbp, [rax-5Fh]
0x18012e502  sub     rsp, 90h
0x18012e509  xor     r14d, r14d
0x18012e50c  lea     rdx, [rbp+57h+hKey]; HKEY *
0x18012e510  mov     r13, r8
0x18012e513  mov     [r8], r14
0x18012e516  mov     [rbp+57h+phkResult], r14
0x18012e51a  mov     ebx, r14d
0x18012e51d  mov     [rbp+57h+hKey], r14
0x18012e521  lea     r8d, [r14+1]; int
0x18012e525  call    ?PlaliConnectToRegistry@@YAJPEBGAEAPEAUHKEY__@@HH@Z; PlaliConnectToRegistry(ushort const *,HKEY__ * &,int,int)
0x18012e52a  mov     [rbp+57h+var_54], eax
0x18012e52d  mov     esi, eax
0x18012e52f  test    eax, eax
0x18012e531  jnz     loc_18012E6CC
0x18012e537  mov     rcx, [rbp+57h+hKey]; hKey
0x18012e53b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18012e53f  mov     [rsp+58h], r14; lpftLastWriteTime
0x18012e544  xor     r9d, r9d; lpReserved
0x18012e547  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18012e54c  xor     r8d, r8d; lpcchClass
0x18012e54f  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18012e554  xor     edx, edx; lpClass
0x18012e556  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18012e55b  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x18012e560  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18012e565  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18012e56a  lea     rax, [rbp+57h+cSubKeys]
0x18012e56e  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x18012e573  mov     [rbp+57h+cSubKeys], r14d
0x18012e577  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18012e57b  call    cs:__imp_RegQueryInfoKeyW
0x18012e581  mov     ebx, eax
0x18012e583  test    eax, eax
0x18012e585  jnz     loc_18012E6CC
0x18012e58b  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18012e58e  mov     edi, r14d
0x18012e591  mov     [rbp+57h+String1], r14
0x18012e595  mov     [rbp+57h+var_58], r14d
0x18012e599  lea     r12d, ds:2[rax*2]
0x18012e5a1  call    cs:__imp_GetProcessHeap
0x18012e5a7  mov     r8d, r12d; dwBytes
0x18012e5aa  lea     edx, [rsi+8]; dwFlags
0x18012e5ad  mov     rcx, rax; hHeap
0x18012e5b0  call    cs:__imp_HeapAlloc
0x18012e5b6  mov     r15, rax
0x18012e5b9  test    rax, rax
0x18012e5bc  jz      loc_18012E6C7
0x18012e5c2  lea     ebx, [rsi+2]
0x18012e5c5  cmp     [rbp+57h+cSubKeys], edi
0x18012e5c8  jbe     loc_18012E6B1
0x18012e5ce  mov     r13, [rbp+57h+String2]
0x18012e5d2  mov     esi, [rbp+57h+arg_18]
0x18012e5d5  shr     r12d, 1
0x18012e5d8  mov     rcx, [rbp+57h+hKey]; hKey
0x18012e5dc  mov     r9d, r12d; cchName
0x18012e5df  mov     r8, r15; lpName
0x18012e5e2  mov     edx, r14d; dwIndex
0x18012e5e5  call    cs:__imp_RegEnumKeyW
0x18012e5eb  mov     ebx, eax
0x18012e5ed  test    eax, eax
0x18012e5ef  jnz     loc_18012E684
0x18012e5f5  mov     rcx, [rbp+57h+hKey]; hKey
0x18012e5f9  mov     eax, esi
0x18012e5fb  neg     eax
0x18012e5fd  mov     rdx, r15; lpSubKey
0x18012e600  lea     rax, [rbp+57h+phkResult]
0x18012e604  sbb     r9d, r9d
0x18012e607  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x18012e60c  and     r9d, 6
0x18012e610  xor     r8d, r8d; ulOptions
0x18012e613  add     r9d, 20019h; samDesired
0x18012e61a  call    cs:__imp_RegOpenKeyExW
0x18012e620  mov     ebx, eax
0x18012e622  test    eax, eax
0x18012e624  jnz     short loc_18012E684
0x18012e626  mov     rdx, r13; String2
0x18012e629  mov     rcx, r15; String1
0x18012e62c  call    cs:__imp__wcsicmp
0x18012e632  test    eax, eax
0x18012e634  jz      short loc_18012E691
0x18012e636  mov     rcx, [rbp+57h+phkResult]; hKey
0x18012e63a  lea     rax, [rbp+57h+var_58]
0x18012e63e  lea     r9, [rbp+57h+String1]; unsigned __int16 **
0x18012e642  mov     [rsp+0C0h+lpcSubKeys], rax; unsigned int *
0x18012e647  lea     r8d, [rbx+1]; unsigned int
0x18012e64b  lea     rdx, aCollectionName; "Collection Name"
0x18012e652  call    ?PlaliReadRegistryStringValue@@YAJPEAUHKEY__@@PEBGKPEAPEAGPEAK@Z; PlaliReadRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort * *,ulong *)
0x18012e657  mov     rdi, [rbp+57h+String1]
0x18012e65b  test    rdi, rdi
0x18012e65e  jz      short loc_18012E670
0x18012e660  mov     rdx, r13; String2
0x18012e663  mov     rcx, rdi; String1
0x18012e666  call    cs:__imp__wcsicmp
0x18012e66c  test    eax, eax
0x18012e66e  jz      short loc_18012E691
0x18012e670  mov     rcx, [rbp+57h+phkResult]; hKey
0x18012e674  mov     ebx, 2
0x18012e679  test    rcx, rcx
0x18012e67c  jz      short loc_18012E684
0x18012e67e  call    cs:__imp_RegCloseKey
0x18012e684  inc     r14d
0x18012e687  cmp     r14d, [rbp+57h+cSubKeys]
0x18012e68b  jb      loc_18012E5D8
0x18012e691  mov     esi, [rbp+57h+var_54]
0x18012e694  mov     r13, [rbp+57h+arg_10]
0x18012e698  test    rdi, rdi
0x18012e69b  jz      short loc_18012E6B1
0x18012e69d  call    cs:__imp_GetProcessHeap
0x18012e6a3  mov     r8, rdi; lpMem
0x18012e6a6  xor     edx, edx; dwFlags
0x18012e6a8  mov     rcx, rax; hHeap
0x18012e6ab  call    cs:__imp_HeapFree
0x18012e6b1  call    cs:__imp_GetProcessHeap
0x18012e6b7  mov     r8, r15; lpMem
0x18012e6ba  xor     edx, edx; dwFlags
0x18012e6bc  mov     rcx, rax; hHeap
0x18012e6bf  call    cs:__imp_HeapFree
0x18012e6c5  jmp     short loc_18012E6CC
0x18012e6c7  mov     ebx, 0Eh
0x18012e6cc  mov     rcx, [rbp+57h+hKey]; hKey
0x18012e6d0  test    rcx, rcx
0x18012e6d3  jz      short loc_18012E6DB
0x18012e6d5  call    cs:__imp_RegCloseKey
0x18012e6db  test    ebx, ebx
0x18012e6dd  jnz     short loc_18012E70D
0x18012e6df  test    esi, esi
0x18012e6e1  jnz     short loc_18012E711
0x18012e6e3  mov     rax, [rbp+57h+phkResult]
0x18012e6e7  mov     [r13+0], rax
0x18012e6eb  mov     ecx, ebx; unsigned int
0x18012e6ed  call    ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
0x18012e6f2  mov     rbx, [rsp+0C0h+arg_0]
0x18012e6fa  add     rsp, 90h
0x18012e701  pop     r15
0x18012e703  pop     r14
0x18012e705  pop     r13
0x18012e707  pop     r12
0x18012e709  pop     rdi
0x18012e70a  pop     rsi
0x18012e70b  pop     rbp
0x18012e70c  retn
0x18012e70d  test    esi, esi
0x18012e70f  jz      short loc_18012E6EB
0x18012e711  mov     eax, esi
0x18012e713  jmp     short loc_18012E6F2
```
