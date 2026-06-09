# DestroyKeyValues(wchar_t const * const *,int)

- ea: `0x18001f904`
- end: `0x18001fa93`
- name: `?DestroyKeyValues@@YAJPEBQEB_WH@Z`
- size: `399`
- prototype: `__int64 __fastcall(const wchar_t *const *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180020854`
- `0x18002122c`

## callees

- `0x1800111bc`
- `0x180014130`
- `0x18001f4f4`
- `0x18001f53c`
- `0x18001f904`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f9af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fa48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f9af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fa48`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001f9d1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001fa5c`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001f9d1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001fa5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DestroyKeyValues(LPCWSTR *a1, int a2)
{
  int i; // ebx
  unsigned int j; // r14d
  unsigned int v6; // edi
  __int64 v7; // rdx
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h]
  unsigned int v12; // [rsp+54h] [rbp-ACh]

  TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(&v10);
  for ( i = 0; i < a2; i += 2 )
  {
    (*(void (__fastcall **)(__int64 *, const wchar_t *, _QWORD, __int64))(v10 + 32))(&v10, L"\\", v12, 0xFFFFFFFFLL);
    (*(void (__fastcall **)(__int64 *, LPCWSTR, _QWORD, __int64))(v10 + 32))(&v10, a1[i], v12, 0xFFFFFFFFLL);
  }
  hKey[0] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  for ( j = v12; ; CLMString::Truncate((CLMString *)&v10, j) )
  {
    i -= 2;
    if ( i < 0 )
      break;
    v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, hKey);
    if ( v6 )
      goto LABEL_15;
    if ( i + 2 < a2 )
    {
      v6 = RegDeleteKeyW(hKey[0], a1[(unsigned int)i + 2]);
      if ( v6 )
        goto LABEL_15;
    }
    if ( hKey[0] != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    v7 = -1;
    do
      ++v7;
    while ( a1[i][v7] );
    j += -1 - v7;
  }
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, hKey);
  if ( !v6 )
    v6 = RegDeleteKeyW(hKey[0], *a1);
LABEL_15:
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(&v10);
  return v6;
}

```

## disassembly

```asm
0x18001f904  push    rbp
0x18001f906  push    rbx
0x18001f907  push    rsi
0x18001f908  push    rdi
0x18001f909  push    r12
0x18001f90b  push    r13
0x18001f90d  push    r14
0x18001f90f  push    r15
0x18001f911  lea     rbp, [rsp-778h]
0x18001f919  sub     rsp, 878h
0x18001f920  mov     rax, cs:__security_cookie
0x18001f927  xor     rax, rsp
0x18001f92a  mov     [rbp+7B0h+var_50], rax
0x18001f931  mov     r15d, edx
0x18001f934  mov     rsi, rcx
0x18001f937  lea     rcx, [rsp+8B0h+var_870]
0x18001f93c  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEB_W@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(wchar_t const *)
0x18001f941  nop
0x18001f942  xor     r12d, r12d
0x18001f945  mov     ebx, r12d
0x18001f948  or      edi, 0FFFFFFFFh
0x18001f94b  test    r15d, r15d
0x18001f94e  jle     short loc_18001F99C
0x18001f950  mov     rax, [rsp+8B0h+var_870]
0x18001f955  mov     r9d, edi
0x18001f958  mov     r8d, [rsp+8B0h+var_85C]
0x18001f95d  lea     rdx, asc_180031388; "\\"
0x18001f964  lea     rcx, [rsp+8B0h+var_870]
0x18001f969  mov     rax, [rax+20h]
0x18001f96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f972  movsxd  rdx, ebx
0x18001f975  mov     rax, [rsp+8B0h+var_870]
0x18001f97a  mov     r9d, edi
0x18001f97d  mov     r8d, [rsp+8B0h+var_85C]
0x18001f982  mov     rdx, [rsi+rdx*8]
0x18001f986  lea     rcx, [rsp+8B0h+var_870]
0x18001f98b  mov     rax, [rax+20h]
0x18001f98f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f994  add     ebx, 2
0x18001f997  cmp     ebx, r15d
0x18001f99a  jl      short loc_18001F950
0x18001f99c  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001f9a0  mov     [rsp+8B0h+hKey], r13
0x18001f9a5  mov     r14d, [rsp+8B0h+var_85C]
0x18001f9aa  jmp     short loc_18001FA20
0x18001f9ac  xor     r8d, r8d; ulOptions
0x18001f9af  call    cs:__imp_RegOpenKeyExW
0x18001f9b5  mov     edi, eax
0x18001f9b7  test    eax, eax
0x18001f9b9  jnz     loc_18001FA64
0x18001f9bf  lea     eax, [rbx+2]
0x18001f9c2  cmp     eax, r15d
0x18001f9c5  jge     short loc_18001F9E1
0x18001f9c7  mov     rdx, [rsi+rbx*8+10h]; lpSubKey
0x18001f9cc  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18001f9d1  call    cs:__imp_RegDeleteKeyW
0x18001f9d7  mov     edi, eax
0x18001f9d9  test    eax, eax
0x18001f9db  jnz     loc_18001FA64
0x18001f9e1  mov     eax, ebx
0x18001f9e3  mov     edi, ebx
0x18001f9e5  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18001f9ea  cmp     rcx, r13
0x18001f9ed  jz      short loc_18001F9FA
0x18001f9ef  call    cs:__imp_RegCloseKey
0x18001f9f5  mov     [rsp+8B0h+hKey], r13
0x18001f9fa  mov     rax, [rsi+rdi*8]
0x18001f9fe  mov     rdx, r13
0x18001fa01  inc     rdx
0x18001fa04  cmp     [rax+rdx*2], r12w
0x18001fa09  jnz     short loc_18001FA01
0x18001fa0b  or      eax, 0FFFFFFFFh
0x18001fa0e  sub     eax, edx
0x18001fa10  add     r14d, eax
0x18001fa13  mov     edx, r14d; unsigned int
0x18001fa16  lea     rcx, [rsp+8B0h+var_870]; this
0x18001fa1b  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x18001fa20  sub     ebx, 2
0x18001fa23  lea     rax, [rsp+8B0h+hKey]
0x18001fa28  mov     r9d, 2001Fh; samDesired
0x18001fa2e  mov     rdx, [rsp+8B0h+lpSubKey]; lpSubKey
0x18001fa33  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001fa3a  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18001fa3f  jns     loc_18001F9AC
0x18001fa45  xor     r8d, r8d; ulOptions
0x18001fa48  call    cs:__imp_RegOpenKeyExW
0x18001fa4e  mov     edi, eax
0x18001fa50  test    eax, eax
0x18001fa52  jnz     short loc_18001FA64
0x18001fa54  mov     rdx, [rsi]; lpSubKey
0x18001fa57  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18001fa5c  call    cs:__imp_RegDeleteKeyW
0x18001fa62  mov     edi, eax
0x18001fa64  lea     rcx, [rsp+8B0h+var_870]
0x18001fa69  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001fa6e  mov     eax, edi
0x18001fa70  mov     rcx, [rbp+7B0h+var_50]
0x18001fa77  xor     rcx, rsp; StackCookie
0x18001fa7a  call    __security_check_cookie
0x18001fa7f  add     rsp, 878h
0x18001fa86  pop     r15
0x18001fa88  pop     r14
0x18001fa8a  pop     r13
0x18001fa8c  pop     r12
0x18001fa8e  pop     rdi
0x18001fa8f  pop     rsi
0x18001fa90  pop     rbx
0x18001fa91  pop     rbp
0x18001fa92  retn
```
