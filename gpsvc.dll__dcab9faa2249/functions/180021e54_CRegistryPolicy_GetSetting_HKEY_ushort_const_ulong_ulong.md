# CRegistryPolicy::GetSetting(HKEY__ *,ushort const *,ulong *,ulong)

- ea: `0x180021e54`
- end: `0x180022064`
- name: `?GetSetting@CRegistryPolicy@@QEBAKPEAUHKEY__@@PEBGPEAKK@Z`
- size: `528`
- prototype: `unsigned int(CRegistryPolicy *__hidden this, HKEY, const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021994`
- `0x180063c74`
- `0x180075004`
- `0x180094498`
- `0x180094afc`
- `0x1800b96cc`

## callees

- `0x180021e54`
- `0x180022bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022008`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022059`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022008`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022059`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021f8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021eb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021f8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021ee8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021fb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021ee8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021fb9`

## pseudocode

```c
__int64 __fastcall CRegistryPolicy::GetSetting(
        CRegistryPolicy *this,
        HKEY a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD Type)
{
  unsigned int v5; // esi
  unsigned int v7; // ebx
  const WCHAR *v8; // rdx
  const WCHAR *v12; // rdx
  unsigned int v13; // esi
  LSTATUS v15; // eax
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  v5 = Type;
  *(_DWORD *)a4 = Type;
  v7 = 0;
  v8 = (const WCHAR *)*((_QWORD *)this + 1);
  if ( !v8 )
    goto LABEL_2;
  hKey = 0;
  Type = 0;
  v15 = RegOpenKeyExW(a2, v8, 0, 0x20019u, &hKey);
  if ( !v15 )
  {
    cbData = 4;
    v15 = RegQueryValueExW(hKey, a3, 0, &Type, a4, &cbData);
    if ( !v15 )
    {
      if ( Type != 4 )
        *(_DWORD *)a4 = v5;
      goto LABEL_27;
    }
    *(_DWORD *)a4 = v5;
  }
  if ( v15 != 2 )
  {
LABEL_27:
    XKey::Free((XKey *)&hKey);
    goto LABEL_2;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL
    && (unsigned __int64)(hKey + 0x20000000) > 6
    && hKey != HKEY_PERFORMANCE_TEXT
    && hKey != HKEY_PERFORMANCE_NLSTEXT )
  {
    RegCloseKey(hKey);
  }
LABEL_2:
  v12 = (const WCHAR *)*((_QWORD *)this + 2);
  if ( !v12 )
    return v7;
  v13 = *(_DWORD *)a4;
  hKey = 0;
  Type = 0;
  v7 = RegOpenKeyExW(a2, v12, 0, 0x20019u, &hKey);
  if ( !v7 )
  {
    cbData = 4;
    v7 = RegQueryValueExW(hKey, a3, 0, &Type, a4, &cbData);
    if ( !v7 )
    {
      if ( Type != 4 )
      {
        *(_DWORD *)a4 = v13;
        v7 = 13;
      }
      goto LABEL_11;
    }
    *(_DWORD *)a4 = v13;
  }
  if ( v7 == 2 )
  {
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL
      && (unsigned __int64)(hKey + 0x20000000) > 6
      && hKey != HKEY_PERFORMANCE_TEXT
      && hKey != HKEY_PERFORMANCE_NLSTEXT )
    {
      RegCloseKey(hKey);
    }
    return 0;
  }
LABEL_11:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL
    && (unsigned __int64)(hKey + 0x20000000) > 6
    && hKey != HKEY_PERFORMANCE_TEXT
    && hKey != HKEY_PERFORMANCE_NLSTEXT )
  {
    RegCloseKey(hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x180021e54  mov     [rsp-28h+arg_8], rbx
0x180021e59  mov     [rsp-28h+arg_10], rsi
0x180021e5e  push    rbp
0x180021e5f  push    rdi
0x180021e60  push    r12
0x180021e62  push    r14
0x180021e64  push    r15
0x180021e66  mov     rbp, rsp
0x180021e69  sub     rsp, 30h
0x180021e6d  mov     esi, [rbp+Type]
0x180021e70  mov     r12, rdx
0x180021e73  mov     [r9], esi
0x180021e76  xor     ebx, ebx
0x180021e78  mov     rdx, [rcx+8]; lpSubKey
0x180021e7c  mov     rdi, r9
0x180021e7f  mov     r15, r8
0x180021e82  mov     r14, rcx
0x180021e85  test    rdx, rdx
0x180021e88  jnz     loc_180021F70
0x180021e8e  mov     rdx, [r14+10h]; lpSubKey
0x180021e92  test    rdx, rdx
0x180021e95  jz      loc_180021F21
0x180021e9b  mov     esi, [rdi]
0x180021e9d  lea     rax, [rbp+hKey]
0x180021ea1  mov     r9d, 20019h; samDesired
0x180021ea7  mov     [rsp+30h+phkResult], rax; phkResult
0x180021eac  xor     r8d, r8d; ulOptions
0x180021eaf  mov     [rbp+hKey], rbx
0x180021eb3  mov     rcx, r12; hKey
0x180021eb6  mov     [rbp+Type], ebx
0x180021eb9  call    cs:__imp_RegOpenKeyExW
0x180021ebf  mov     ebx, eax
0x180021ec1  test    eax, eax
0x180021ec3  jnz     short loc_180021EFA
0x180021ec5  mov     rcx, [rbp+hKey]; hKey
0x180021ec9  lea     rax, [rbp+cbData]
0x180021ecd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180021ed2  lea     r9, [rbp+Type]; lpType
0x180021ed6  xor     r8d, r8d; lpReserved
0x180021ed9  mov     [rsp+30h+phkResult], rdi; lpData
0x180021ede  mov     rdx, r15; lpValueName
0x180021ee1  mov     [rbp+cbData], 4
0x180021ee8  call    cs:__imp_RegQueryValueExW
0x180021eee  mov     ebx, eax
0x180021ef0  test    eax, eax
0x180021ef2  jz      loc_180022029
0x180021ef8  mov     [rdi], esi
0x180021efa  cmp     ebx, 2
0x180021efd  jnz     short loc_180021F3A
0x180021eff  mov     rcx, [rbp+hKey]; hKey
0x180021f03  lea     rax, [rcx-1]
0x180021f07  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021f0b  ja      short loc_180021F1F
0x180021f0d  mov     eax, 80000000h
0x180021f12  add     rax, rcx
0x180021f15  cmp     rax, 6
0x180021f19  ja      loc_18002203F
0x180021f1f  xor     ebx, ebx
0x180021f21  mov     rsi, [rsp+30h+arg_10]
0x180021f26  mov     eax, ebx
0x180021f28  mov     rbx, [rsp+30h+arg_8]
0x180021f2d  add     rsp, 30h
0x180021f31  pop     r15
0x180021f33  pop     r14
0x180021f35  pop     r12
0x180021f37  pop     rdi
0x180021f38  pop     rbp
0x180021f39  retn
0x180021f3a  mov     rcx, [rbp+hKey]; hKey
0x180021f3e  lea     rax, [rcx-1]
0x180021f42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021f46  ja      short loc_180021F21
0x180021f48  mov     eax, 80000000h
0x180021f4d  add     rax, rcx
0x180021f50  cmp     rax, 6
0x180021f54  jbe     short loc_180021F21
0x180021f56  cmp     rcx, 0FFFFFFFF80000050h
0x180021f5d  jz      short loc_180021F21
0x180021f5f  cmp     rcx, 0FFFFFFFF80000060h
0x180021f66  jz      short loc_180021F21
0x180021f68  call    cs:__imp_RegCloseKey
0x180021f6e  jmp     short loc_180021F21
0x180021f70  lea     rax, [rbp+hKey]
0x180021f74  mov     [rbp+hKey], rbx
0x180021f78  mov     r9d, 20019h; samDesired
0x180021f7e  mov     [rsp+30h+phkResult], rax; phkResult
0x180021f83  xor     r8d, r8d; ulOptions
0x180021f86  mov     [rbp+Type], ebx
0x180021f89  mov     rcx, r12; hKey
0x180021f8c  call    cs:__imp_RegOpenKeyExW
0x180021f92  test    eax, eax
0x180021f94  jnz     short loc_180021FC5
0x180021f96  mov     rcx, [rbp+hKey]; hKey
0x180021f9a  lea     rax, [rbp+cbData]
0x180021f9e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180021fa3  lea     r9, [rbp+Type]; lpType
0x180021fa7  xor     r8d, r8d; lpReserved
0x180021faa  mov     [rsp+30h+phkResult], rdi; lpData
0x180021faf  mov     rdx, r15; lpValueName
0x180021fb2  mov     [rbp+cbData], 4
0x180021fb9  call    cs:__imp_RegQueryValueExW
0x180021fbf  test    eax, eax
0x180021fc1  jz      short loc_180022013
0x180021fc3  mov     [rdi], esi
0x180021fc5  cmp     eax, 2
0x180021fc8  jnz     short loc_18002201B
0x180021fca  mov     rcx, [rbp+hKey]; hKey
0x180021fce  lea     rax, [rcx-1]
0x180021fd2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021fd6  ja      loc_180021E8E
0x180021fdc  mov     eax, 80000000h
0x180021fe1  add     rax, rcx
0x180021fe4  cmp     rax, 6
0x180021fe8  jbe     loc_180021E8E
0x180021fee  cmp     rcx, 0FFFFFFFF80000050h
0x180021ff5  jz      loc_180021E8E
0x180021ffb  cmp     rcx, 0FFFFFFFF80000060h
0x180022002  jz      loc_180021E8E
0x180022008  call    cs:__imp_RegCloseKey
0x18002200e  jmp     loc_180021E8E
0x180022013  cmp     [rbp+Type], 4
0x180022017  jz      short loc_18002201B
0x180022019  mov     [rdi], esi
0x18002201b  lea     rcx, [rbp+hKey]; this
0x18002201f  call    ?Free@XKey@@QEAAXXZ; XKey::Free(void)
0x180022024  jmp     loc_180021E8E
0x180022029  cmp     [rbp+Type], 4
0x18002202d  jz      loc_180021F3A
0x180022033  mov     [rdi], esi
0x180022035  mov     ebx, 0Dh
0x18002203a  jmp     loc_180021F3A
0x18002203f  cmp     rcx, 0FFFFFFFF80000050h
0x180022046  jz      loc_180021F1F
0x18002204c  cmp     rcx, 0FFFFFFFF80000060h
0x180022053  jz      loc_180021F1F
0x180022059  call    cs:__imp_RegCloseKey
0x18002205f  jmp     loc_180021F1F
```
