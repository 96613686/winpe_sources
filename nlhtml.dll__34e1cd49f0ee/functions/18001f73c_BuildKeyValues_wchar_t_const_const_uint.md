# BuildKeyValues(wchar_t const * const *,uint)

- ea: `0x18001f73c`
- end: `0x18001f8d9`
- name: `?BuildKeyValues@@YAJPEBQEB_WI@Z`
- size: `413`
- prototype: `__int64 __fastcall(const wchar_t *const *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002107c`

## callees

- `0x180014130`
- `0x18001f4f4`
- `0x18001f53c`
- `0x18001f73c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f875`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f875`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f7a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f89b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f7a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f89b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f82d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f82d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BuildKeyValues(const wchar_t *const *a1, unsigned int a2)
{
  unsigned int v4; // edi
  HKEY v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rbx
  const BYTE *v8; // rdx
  __int64 v9; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v14; // [rsp+74h] [rbp-8Ch]

  TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(v13);
  v4 = 0;
  v5 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      if ( v5 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        RegCloseKey(v5);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      (*(void (__fastcall **)(_QWORD *, const wchar_t *, _QWORD, __int64))(v13[0] + 32LL))(
        v13,
        L"\\",
        v14,
        0xFFFFFFFFLL);
      (*(void (__fastcall **)(_QWORD *, const wchar_t *const, _QWORD, __int64))(v13[0] + 32LL))(
        v13,
        a1[v6],
        v14,
        0xFFFFFFFFLL);
      dwDisposition = 0;
      v4 = RegCreateKeyExW(HKEY_CLASSES_ROOT, (LPCWSTR)v13[1], 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
      if ( v4 )
        break;
      v7 = v6 + 1;
      if ( (unsigned int)v7 < a2 )
      {
        v8 = (const BYTE *)a1[v7];
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&v8[2 * v9] );
          v4 = RegSetValueExW(hKey, 0, 0, 1u, v8, 2 * v9 + 2);
          if ( v4 )
            break;
        }
      }
      v6 = v7 + 1;
      if ( v6 >= a2 )
        break;
      v5 = hKey;
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(v13);
  return v4;
}

```

## disassembly

```asm
0x18001f73c  mov     [rsp-8+arg_8], rbx
0x18001f741  mov     [rsp-8+arg_10], rsi
0x18001f746  push    rbp
0x18001f747  push    rdi
0x18001f748  push    r12
0x18001f74a  push    r14
0x18001f74c  push    r15
0x18001f74e  lea     rbp, [rsp-790h]
0x18001f756  sub     rsp, 890h
0x18001f75d  mov     rax, cs:__security_cookie
0x18001f764  xor     rax, rsp
0x18001f767  mov     [rbp+7B0h+var_30], rax
0x18001f76e  mov     esi, edx
0x18001f770  mov     r14, rcx
0x18001f773  lea     rcx, [rsp+8B0h+var_850]
0x18001f778  call    ??0?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@QEAA@PEB_W@Z; TLMString<1024,1024,1048576>::TLMString<1024,1024,1048576>(wchar_t const *)
0x18001f77d  nop
0x18001f77e  xor     r15d, r15d
0x18001f781  mov     edi, r15d
0x18001f784  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001f788  mov     rcx, r12; hKey
0x18001f78b  mov     [rsp+8B0h+hKey], rcx
0x18001f790  mov     ebx, r15d
0x18001f793  test    esi, esi
0x18001f795  jz      loc_18001F8A2
0x18001f79b  cmp     rcx, r12
0x18001f79e  jz      short loc_18001F7AB
0x18001f7a0  call    cs:__imp_RegCloseKey
0x18001f7a6  mov     [rsp+8B0h+hKey], r12
0x18001f7ab  mov     rax, [rsp+8B0h+var_850]
0x18001f7b0  or      r9d, 0FFFFFFFFh
0x18001f7b4  mov     r8d, [rsp+8B0h+var_83C]
0x18001f7b9  lea     rdx, asc_180031388; "\\"
0x18001f7c0  lea     rcx, [rsp+8B0h+var_850]
0x18001f7c5  mov     rax, [rax+20h]
0x18001f7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7ce  mov     edx, ebx
0x18001f7d0  mov     rax, [rsp+8B0h+var_850]
0x18001f7d5  or      r9d, 0FFFFFFFFh
0x18001f7d9  mov     r8d, [rsp+8B0h+var_83C]
0x18001f7de  mov     rdx, [r14+rdx*8]
0x18001f7e2  lea     rcx, [rsp+8B0h+var_850]
0x18001f7e7  mov     rax, [rax+20h]
0x18001f7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7f0  mov     [rsp+8B0h+dwDisposition], r15d
0x18001f7f5  lea     rax, [rsp+8B0h+dwDisposition]
0x18001f7fa  mov     [rsp+8B0h+lpdwDisposition], rax; lpdwDisposition
0x18001f7ff  lea     rax, [rsp+8B0h+hKey]
0x18001f804  mov     [rsp+8B0h+phkResult], rax; phkResult
0x18001f809  mov     [rsp+8B0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18001f80e  mov     [rsp+8B0h+samDesired], 20006h; samDesired
0x18001f816  mov     [rsp+8B0h+dwOptions], r15d; dwOptions
0x18001f81b  xor     r9d, r9d; lpClass
0x18001f81e  xor     r8d, r8d; Reserved
0x18001f821  mov     rdx, [rsp+8B0h+lpSubKey]; lpSubKey
0x18001f826  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001f82d  call    cs:__imp_RegCreateKeyExW
0x18001f833  mov     edi, eax
0x18001f835  test    eax, eax
0x18001f837  jnz     short loc_18001F891
0x18001f839  inc     ebx
0x18001f83b  cmp     ebx, esi
0x18001f83d  jnb     short loc_18001F881
0x18001f83f  mov     rdx, [r14+rbx*8]
0x18001f843  test    rdx, rdx
0x18001f846  jz      short loc_18001F881
0x18001f848  mov     rax, r12
0x18001f84b  inc     rax
0x18001f84e  cmp     [rdx+rax*2], r15w
0x18001f853  jnz     short loc_18001F84B
0x18001f855  lea     eax, ds:2[rax*2]
0x18001f85c  mov     [rsp+8B0h+samDesired], eax; cbData
0x18001f860  mov     qword ptr [rsp+8B0h+dwOptions], rdx; lpData
0x18001f865  mov     r9d, 1; dwType
0x18001f86b  xor     r8d, r8d; Reserved
0x18001f86e  xor     edx, edx; lpValueName
0x18001f870  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18001f875  call    cs:__imp_RegSetValueExW
0x18001f87b  mov     edi, eax
0x18001f87d  test    eax, eax
0x18001f87f  jnz     short loc_18001F891
0x18001f881  inc     ebx
0x18001f883  cmp     ebx, esi
0x18001f885  jnb     short loc_18001F891
0x18001f887  mov     rcx, [rsp+8B0h+hKey]
0x18001f88c  jmp     loc_18001F79B
0x18001f891  mov     rcx, [rsp+8B0h+hKey]; hKey
0x18001f896  cmp     rcx, r12
0x18001f899  jz      short loc_18001F8A2
0x18001f89b  call    cs:__imp_RegCloseKey
0x18001f8a1  nop
0x18001f8a2  lea     rcx, [rsp+8B0h+var_850]
0x18001f8a7  call    ??1?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@UEAA@XZ; TLMString<1024,1024,1048576>::~TLMString<1024,1024,1048576>(void)
0x18001f8ac  mov     eax, edi
0x18001f8ae  mov     rcx, [rbp+7B0h+var_30]
0x18001f8b5  xor     rcx, rsp; StackCookie
0x18001f8b8  call    __security_check_cookie
0x18001f8bd  lea     r11, [rsp+8B0h+var_20]
0x18001f8c5  mov     rbx, [r11+38h]
0x18001f8c9  mov     rsi, [r11+40h]
0x18001f8cd  mov     rsp, r11
0x18001f8d0  pop     r15
0x18001f8d2  pop     r14
0x18001f8d4  pop     r12
0x18001f8d6  pop     rdi
0x18001f8d7  pop     rbp
0x18001f8d8  retn
```
