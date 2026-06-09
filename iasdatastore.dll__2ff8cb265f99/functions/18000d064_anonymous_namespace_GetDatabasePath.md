# _anonymous_namespace_::GetDatabasePath

- ea: `0x18000d064`
- end: `0x18000d25a`
- name: `_anonymous_namespace_::GetDatabasePath`
- size: `502`
- prototype: `LSTATUS __fastcall(wchar_t *Source, BYTE *Destination, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180008d7c`
- `0x18000be1c`

## callees

- `0x1800024f4`
- `0x18000d064`

## import_xrefs

- `msvcrt!free` at `0x18000d1e6`
- `msvcrt!free` at `0x18000d203`
- `msvcrt!free` at `0x18000d1e6`
- `msvcrt!free` at `0x18000d203`
- `msvcrt!wcsncpy_s` at `0x18000d1fa`
- `msvcrt!wcsncpy_s` at `0x18000d1fa`
- `msvcrt!wcscat_s` at `0x18000d228`
- `msvcrt!wcscat_s` at `0x18000d228`
- `ADVAPI32!RegQueryValueExW` at `0x18000d129`
- `ADVAPI32!RegQueryValueExW` at `0x18000d129`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d0d2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d0d2`
- `ADVAPI32!RegCloseKey` at `0x18000d136`
- `ADVAPI32!RegCloseKey` at `0x18000d136`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000d197`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000d1d9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000d197`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000d1d9`
- `KERNEL32!GetLastError` at `0x18000d1a4`
- `KERNEL32!GetLastError` at `0x18000d1a4`

## string_xrefs

- `0x18000d0c4`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::GetDatabasePath(wchar_t *Source, BYTE *Destination, unsigned int *a3)
{
  unsigned int v6; // edi
  LSTATUS result; // eax
  rsize_t v8; // r13
  LSTATUS v9; // esi
  __int64 v10; // r15
  __int64 v11; // rcx
  unsigned int v12; // edi
  DWORD v13; // eax
  unsigned __int64 v14; // r12
  unsigned __int128 v15; // rax
  WCHAR *v16; // rax
  WCHAR *v17; // rdi
  unsigned int v18; // [rsp+30h] [rbp-48h]
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  DWORD Type; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  if ( Source )
  {
    if ( Destination )
    {
      if ( a3 )
      {
        v6 = *a3;
        if ( *a3 )
        {
          *a3 = 0;
          hKey = 0;
          result = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
                     0,
                     0x20019u,
                     &hKey);
          if ( result )
            return result;
          v8 = v6 - 1;
          v18 = v6 - 1;
          cbData = 2 * v8;
          Type = 0;
          v9 = RegQueryValueExW(hKey, L"ProductDir", 0, &Type, Destination, &cbData);
          RegCloseKey(hKey);
          v10 = -1;
          v11 = -1;
          do
            ++v11;
          while ( Source[v11] );
          v12 = v11 + (cbData >> 1);
          if ( v9 )
          {
            if ( v9 != 234 )
              return v9;
LABEL_10:
            *a3 = v12;
            return v9;
          }
          if ( Type != 1 )
          {
            if ( Type != 2 )
              return -2147221165;
            v13 = ExpandEnvironmentStringsW((LPCWSTR)Destination, 0, 0);
            v14 = v13;
            if ( !v13 )
              return GetLastError();
            v15 = v13 * (unsigned __int128)2uLL;
            if ( !is_mul_ok(v14, 2u) )
              *(_QWORD *)&v15 = -1;
            v16 = (WCHAR *)operator new[](v15, *((const struct std::nothrow_t **)&v15 + 1));
            v17 = v16;
            if ( !v16 )
              return 8;
            if ( !ExpandEnvironmentStringsW((LPCWSTR)Destination, v16, v14) )
            {
              free(v17);
              return GetLastError();
            }
            wcsncpy_s((wchar_t *)Destination, v8, v17, v14);
            free(v17);
            do
              ++v10;
            while ( Source[v10] );
            v12 = v10 + v14;
          }
          if ( v12 > v18 )
            v9 = 234;
          else
            wcscat_s((wchar_t *)Destination, v8, Source);
          goto LABEL_10;
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x18000d064  mov     r11, rsp
0x18000d067  mov     [r11+10h], rbx
0x18000d06b  push    rbp
0x18000d06c  push    rsi
0x18000d06d  push    rdi
0x18000d06e  push    r12
0x18000d070  push    r13
0x18000d072  push    r14
0x18000d074  push    r15
0x18000d076  sub     rsp, 40h
0x18000d07a  xor     r12d, r12d
0x18000d07d  mov     rbx, r8
0x18000d080  mov     rbp, rdx
0x18000d083  mov     r14, rcx
0x18000d086  test    rcx, rcx
0x18000d089  jz      loc_18000D23D
0x18000d08f  test    rdx, rdx
0x18000d092  jz      loc_18000D23D
0x18000d098  test    rbx, rbx
0x18000d09b  jz      loc_18000D23D
0x18000d0a1  mov     edi, [r8]
0x18000d0a4  test    edi, edi
0x18000d0a6  jz      loc_18000D23D
0x18000d0ac  mov     [r8], r12d
0x18000d0af  lea     rax, [r11-40h]
0x18000d0b3  xor     r8d, r8d; ulOptions
0x18000d0b6  mov     [r11-58h], rax
0x18000d0ba  mov     r9d, 20019h; samDesired
0x18000d0c0  mov     [r11-40h], r12
0x18000d0c4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18000d0cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d0d2  call    cs:__imp_RegOpenKeyExW
0x18000d0d8  test    eax, eax
0x18000d0da  jnz     loc_18000D242
0x18000d0e0  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d0e5  lea     r13d, [rdi-1]
0x18000d0e9  lea     eax, ds:0[r13*2]
0x18000d0f1  mov     [rsp+78h+var_48], r13d
0x18000d0f6  mov     [rsp+78h+cbData], eax
0x18000d0fd  lea     r9, [rsp+78h+Type]; lpType
0x18000d105  lea     rax, [rsp+78h+cbData]
0x18000d10d  mov     [rsp+78h+Type], r12d
0x18000d115  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000d11a  lea     rdx, ValueName; "ProductDir"
0x18000d121  xor     r8d, r8d; lpReserved
0x18000d124  mov     [rsp+78h+lpData], rbp; lpData
0x18000d129  call    cs:__imp_RegQueryValueExW
0x18000d12f  mov     rcx, [rsp+78h+hKey]; hKey
0x18000d134  mov     esi, eax
0x18000d136  call    cs:__imp_RegCloseKey
0x18000d13c  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000d140  mov     rcx, r15
0x18000d143  inc     rcx
0x18000d146  cmp     [r14+rcx*2], r12w
0x18000d14b  jnz     short loc_18000D143
0x18000d14d  mov     edi, [rsp+78h+cbData]
0x18000d154  shr     edi, 1
0x18000d156  add     edi, ecx
0x18000d158  test    esi, esi
0x18000d15a  jz      short loc_18000D16D
0x18000d15c  cmp     esi, 0EAh
0x18000d162  jnz     short loc_18000D166
0x18000d164  mov     [rbx], edi
0x18000d166  mov     eax, esi
0x18000d168  jmp     loc_18000D242
0x18000d16d  cmp     [rsp+78h+Type], 1
0x18000d175  jz      loc_18000D219
0x18000d17b  cmp     [rsp+78h+Type], 2
0x18000d183  jz      short loc_18000D18F
0x18000d185  mov     eax, 80040153h
0x18000d18a  jmp     loc_18000D242
0x18000d18f  xor     r8d, r8d; nSize
0x18000d192  xor     edx, edx; lpDst
0x18000d194  mov     rcx, rbp; lpSrc
0x18000d197  call    cs:__imp_ExpandEnvironmentStringsW
0x18000d19d  mov     r12d, eax
0x18000d1a0  test    eax, eax
0x18000d1a2  jnz     short loc_18000D1AF
0x18000d1a4  call    cs:__imp_GetLastError
0x18000d1aa  jmp     loc_18000D242
0x18000d1af  mov     eax, 2
0x18000d1b4  mul     r12
0x18000d1b7  cmovb   rax, r15
0x18000d1bb  mov     rcx, rax; Size
0x18000d1be  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000d1c3  mov     rdi, rax
0x18000d1c6  test    rax, rax
0x18000d1c9  jnz     short loc_18000D1D0
0x18000d1cb  lea     eax, [rdi+8]
0x18000d1ce  jmp     short loc_18000D242
0x18000d1d0  mov     r8d, r12d; nSize
0x18000d1d3  mov     rdx, rdi; lpDst
0x18000d1d6  mov     rcx, rbp; lpSrc
0x18000d1d9  call    cs:__imp_ExpandEnvironmentStringsW
0x18000d1df  test    eax, eax
0x18000d1e1  jnz     short loc_18000D1EE
0x18000d1e3  mov     rcx, rdi; Block
0x18000d1e6  call    cs:__imp_free
0x18000d1ec  jmp     short loc_18000D1A4
0x18000d1ee  mov     r9, r12; MaxCount
0x18000d1f1  mov     r8, rdi; Source
0x18000d1f4  mov     rdx, r13; SizeInWords
0x18000d1f7  mov     rcx, rbp; Destination
0x18000d1fa  call    cs:__imp_wcsncpy_s
0x18000d200  mov     rcx, rdi; Block
0x18000d203  call    cs:__imp_free
0x18000d209  xor     eax, eax
0x18000d20b  inc     r15
0x18000d20e  cmp     [r14+r15*2], ax
0x18000d213  jnz     short loc_18000D20B
0x18000d215  lea     edi, [r15+r12]
0x18000d219  cmp     edi, [rsp+78h+var_48]
0x18000d21d  ja      short loc_18000D233
0x18000d21f  mov     r8, r14; Source
0x18000d222  mov     rdx, r13; SizeInWords
0x18000d225  mov     rcx, rbp; Destination
0x18000d228  call    cs:__imp_wcscat_s
0x18000d22e  jmp     loc_18000D164
0x18000d233  mov     esi, 0EAh
0x18000d238  jmp     loc_18000D164
0x18000d23d  mov     eax, 57h ; 'W'
0x18000d242  mov     rbx, [rsp+78h+arg_8]
0x18000d24a  add     rsp, 40h
0x18000d24e  pop     r15
0x18000d250  pop     r14
0x18000d252  pop     r13
0x18000d254  pop     r12
0x18000d256  pop     rdi
0x18000d257  pop     rsi
0x18000d258  pop     rbp
0x18000d259  retn
```
