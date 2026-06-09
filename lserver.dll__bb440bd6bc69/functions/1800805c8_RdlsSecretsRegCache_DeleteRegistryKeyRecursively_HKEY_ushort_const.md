# RdlsSecretsRegCache::DeleteRegistryKeyRecursively(HKEY__ *,ushort const *)

- ea: `0x1800805c8`
- end: `0x180080841`
- name: `?DeleteRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG@Z`
- size: `633`
- prototype: `unsigned int __fastcall(RdlsSecretsRegCache *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800805a0`
- `0x1800805c8`
- `0x180080d90`
- `0x180081730`

## callees

- `0x180005665`
- `0x1800805c8`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18008067a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18008067a`
- `ADVAPI32!RegDeleteValueW` at `0x1800807be`
- `ADVAPI32!RegDeleteValueW` at `0x1800807be`
- `ADVAPI32!RegEnumValueW` at `0x1800807a5`
- `ADVAPI32!RegEnumValueW` at `0x1800807a5`
- `ADVAPI32!RegEnumKeyExW` at `0x18008073f`
- `ADVAPI32!RegEnumKeyExW` at `0x18008073f`
- `ADVAPI32!RegOpenKeyExW` at `0x180080626`
- `ADVAPI32!RegOpenKeyExW` at `0x180080626`
- `ADVAPI32!RegCloseKey` at `0x1800807da`
- `ADVAPI32!RegCloseKey` at `0x1800807da`
- `ADVAPI32!RegDeleteKeyW` at `0x1800807ec`
- `ADVAPI32!RegDeleteKeyW` at `0x1800807ec`
- `KERNEL32!LocalAlloc` at `0x1800806b0`
- `KERNEL32!LocalAlloc` at `0x1800806f4`
- `KERNEL32!LocalAlloc` at `0x1800806b0`
- `KERNEL32!LocalAlloc` at `0x1800806f4`
- `KERNEL32!LocalFree` at `0x180080802`
- `KERNEL32!LocalFree` at `0x180080816`
- `KERNEL32!LocalFree` at `0x180080802`
- `KERNEL32!LocalFree` at `0x180080816`

## pseudocode

```c
LSTATUS __fastcall RdlsSecretsRegCache::DeleteRegistryKeyRecursively(
        RdlsSecretsRegCache *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HLOCAL v6; // rdi
  HLOCAL v7; // rbx
  LSTATUS result; // eax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  LSTATUS v11; // esi
  LSTATUS v12; // esi
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-18h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-14h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C8h] [rbp+48h] BYREF

  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  v6 = 0;
  v7 = 0;
  result = RegOpenKeyExW(a2, a3, 0, 0xF003Fu, &hKey);
  if ( result )
    return result;
  if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, &cbMaxValueNameLen, 0, 0, 0) )
  {
    v9 = 2LL * ++cbMaxValueNameLen;
    if ( v9 > 0xFFFFFFFF )
      goto LABEL_15;
    v7 = LocalAlloc(0x40u, (unsigned int)v9);
    if ( v7 && cSubKeys )
    {
      v10 = 2LL * ++cbMaxSubKeyLen;
      if ( v10 > 0xFFFFFFFF )
      {
        v11 = 0;
LABEL_11:
        while ( !v11 )
        {
          cchValueName = cbMaxValueNameLen;
          memset_0(v7, 0, 2LL * cbMaxValueNameLen);
          v11 = RegEnumValueW(hKey, 0, (LPWSTR)v7, &cchValueName, 0, 0, 0, 0);
          if ( !v11 )
            RegDeleteValueW(hKey, (LPCWSTR)v7);
        }
        goto LABEL_15;
      }
      v6 = LocalAlloc(0x40u, (unsigned int)v10);
      if ( v6 )
      {
        do
        {
          cchName = cbMaxSubKeyLen;
          memset_0(v6, 0, 2LL * cbMaxSubKeyLen);
        }
        while ( !RegEnumKeyExW(hKey, 0, (LPWSTR)v6, &cchName, 0, 0, 0, 0)
             && !RdlsSecretsRegCache::DeleteRegistryKeyRecursively(this, hKey, (const unsigned __int16 *)v6) );
      }
    }
  }
  v11 = 0;
  if ( v7 )
    goto LABEL_11;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  v12 = RegDeleteKeyW(a2, a3);
  if ( v7 )
    LocalFree(v7);
  if ( v6 )
    LocalFree(v6);
  return v12;
}

```

## disassembly

```asm
0x1800805c8  mov     [rsp-28h+arg_0], rbx
0x1800805cd  mov     [rsp-28h+arg_8], rsi
0x1800805d2  push    rbp
0x1800805d3  push    rdi
0x1800805d4  push    r12
0x1800805d6  push    r14
0x1800805d8  push    r15
0x1800805da  mov     rbp, rsp
0x1800805dd  sub     rsp, 80h
0x1800805e4  xor     r12d, r12d
0x1800805e7  lea     rax, [rbp+hKey]
0x1800805eb  mov     r14, r8
0x1800805ee  mov     [rbp+hKey], r12
0x1800805f2  mov     r15, rdx
0x1800805f5  mov     [rbp+cSubKeys], r12d
0x1800805f9  mov     rsi, rcx
0x1800805fc  mov     [rbp+cbMaxSubKeyLen], r12d
0x180080600  mov     rdx, r14; lpSubKey
0x180080603  mov     [rbp+cchName], r12d
0x180080607  mov     rcx, r15; hKey
0x18008060a  mov     [rbp+cbMaxValueNameLen], r12d
0x18008060e  mov     r9d, 0F003Fh; samDesired
0x180080614  mov     [rbp+cchValueName], r12d
0x180080618  xor     r8d, r8d; ulOptions
0x18008061b  mov     [rsp+80h+phkResult], rax; phkResult
0x180080620  mov     edi, r12d
0x180080623  mov     ebx, r12d
0x180080626  call    cs:__imp_RegOpenKeyExW
0x18008062d  nop     dword ptr [rax+rax+00h]
0x180080632  test    eax, eax
0x180080634  jnz     loc_180080824
0x18008063a  mov     rcx, [rbp+hKey]; hKey
0x18008063e  lea     rax, [rbp+cbMaxValueNameLen]
0x180080642  mov     [rsp+80h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180080647  xor     r9d, r9d; lpReserved
0x18008064a  mov     [rsp+80h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18008064f  xor     r8d, r8d; lpcchClass
0x180080652  mov     [rsp+80h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180080657  xor     edx, edx; lpClass
0x180080659  mov     [rsp+80h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18008065e  lea     rax, [rbp+cbMaxSubKeyLen]
0x180080662  mov     [rsp+80h+lpcValues], r12; lpcValues
0x180080667  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18008066c  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180080671  lea     rax, [rbp+cSubKeys]
0x180080675  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18008067a  call    cs:__imp_RegQueryInfoKeyW
0x180080681  nop     dword ptr [rax+rax+00h]
0x180080686  test    eax, eax
0x180080688  jnz     loc_180080762
0x18008068e  mov     eax, [rbp+cbMaxValueNameLen]
0x180080691  inc     eax
0x180080693  mov     ecx, eax
0x180080695  mov     [rbp+cbMaxValueNameLen], eax
0x180080698  add     rcx, rcx
0x18008069b  mov     eax, 0FFFFFFFFh
0x1800806a0  cmp     rcx, rax
0x1800806a3  ja      loc_1800807D1
0x1800806a9  mov     edx, ecx; uBytes
0x1800806ab  lea     ecx, [r12+40h]; uFlags
0x1800806b0  call    cs:__imp_LocalAlloc
0x1800806b7  nop     dword ptr [rax+rax+00h]
0x1800806bc  mov     rbx, rax
0x1800806bf  test    rax, rax
0x1800806c2  jz      loc_180080762
0x1800806c8  cmp     [rbp+cSubKeys], r12d
0x1800806cc  jbe     loc_180080762
0x1800806d2  mov     eax, [rbp+cbMaxSubKeyLen]
0x1800806d5  inc     eax
0x1800806d7  mov     edx, eax
0x1800806d9  mov     [rbp+cbMaxSubKeyLen], eax
0x1800806dc  add     rdx, rdx
0x1800806df  mov     eax, 0FFFFFFFFh
0x1800806e4  cmp     rdx, rax
0x1800806e7  ja      loc_1800807CC
0x1800806ed  mov     edx, edx; uBytes
0x1800806ef  lea     ecx, [r12+40h]; uFlags
0x1800806f4  call    cs:__imp_LocalAlloc
0x1800806fb  nop     dword ptr [rax+rax+00h]
0x180080700  mov     rdi, rax
0x180080703  test    rax, rax
0x180080706  jz      short loc_180080762
0x180080708  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18008070b  xor     edx, edx; Val
0x18008070d  mov     r8d, ecx
0x180080710  mov     [rbp+cchName], ecx
0x180080713  add     r8, r8; Size
0x180080716  mov     rcx, rdi; void *
0x180080719  call    memset_0
0x18008071e  mov     rcx, [rbp+hKey]; hKey
0x180080722  lea     r9, [rbp+cchName]; lpcchName
0x180080726  mov     [rsp+80h+lpcValues], r12; lpftLastWriteTime
0x18008072b  mov     r8, rdi; lpName
0x18008072e  mov     [rsp+80h+lpcbMaxClassLen], r12; lpcchClass
0x180080733  xor     edx, edx; dwIndex
0x180080735  mov     [rsp+80h+lpcbMaxSubKeyLen], r12; lpClass
0x18008073a  mov     [rsp+80h+phkResult], r12; lpReserved
0x18008073f  call    cs:__imp_RegEnumKeyExW
0x180080746  nop     dword ptr [rax+rax+00h]
0x18008074b  test    eax, eax
0x18008074d  jnz     short loc_180080762
0x18008074f  mov     rdx, [rbp+hKey]; HKEY
0x180080753  mov     r8, rdi; unsigned __int16 *
0x180080756  mov     rcx, rsi; this
0x180080759  call    ?DeleteRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG@Z; RdlsSecretsRegCache::DeleteRegistryKeyRecursively(HKEY__ *,ushort const *)
0x18008075e  test    eax, eax
0x180080760  jz      short loc_180080708
0x180080762  mov     esi, r12d
0x180080765  test    rbx, rbx
0x180080768  jz      short loc_1800807D1
0x18008076a  test    esi, esi
0x18008076c  jnz     short loc_1800807D1
0x18008076e  mov     eax, [rbp+cbMaxValueNameLen]
0x180080771  xor     edx, edx; Val
0x180080773  mov     r8d, eax
0x180080776  mov     [rbp+cchValueName], eax
0x180080779  add     r8, r8; Size
0x18008077c  mov     rcx, rbx; void *
0x18008077f  call    memset_0
0x180080784  mov     rcx, [rbp+hKey]; hKey
0x180080788  lea     r9, [rbp+cchValueName]; lpcchValueName
0x18008078c  mov     [rsp+80h+lpcValues], r12; lpcbData
0x180080791  mov     r8, rbx; lpValueName
0x180080794  mov     [rsp+80h+lpcbMaxClassLen], r12; lpData
0x180080799  xor     edx, edx; dwIndex
0x18008079b  mov     [rsp+80h+lpcbMaxSubKeyLen], r12; lpType
0x1800807a0  mov     [rsp+80h+phkResult], r12; lpReserved
0x1800807a5  call    cs:__imp_RegEnumValueW
0x1800807ac  nop     dword ptr [rax+rax+00h]
0x1800807b1  mov     esi, eax
0x1800807b3  test    eax, eax
0x1800807b5  jnz     short loc_18008076A
0x1800807b7  mov     rcx, [rbp+hKey]; hKey
0x1800807bb  mov     rdx, rbx; lpValueName
0x1800807be  call    cs:__imp_RegDeleteValueW
0x1800807c5  nop     dword ptr [rax+rax+00h]
0x1800807ca  jmp     short loc_18008076A
0x1800807cc  mov     esi, r12d
0x1800807cf  jmp     short loc_18008076A
0x1800807d1  mov     rcx, [rbp+hKey]; hKey
0x1800807d5  test    rcx, rcx
0x1800807d8  jz      short loc_1800807E6
0x1800807da  call    cs:__imp_RegCloseKey
0x1800807e1  nop     dword ptr [rax+rax+00h]
0x1800807e6  mov     rdx, r14; lpSubKey
0x1800807e9  mov     rcx, r15; hKey
0x1800807ec  call    cs:__imp_RegDeleteKeyW
0x1800807f3  nop     dword ptr [rax+rax+00h]
0x1800807f8  mov     esi, eax
0x1800807fa  test    rbx, rbx
0x1800807fd  jz      short loc_18008080E
0x1800807ff  mov     rcx, rbx; hMem
0x180080802  call    cs:__imp_LocalFree
0x180080809  nop     dword ptr [rax+rax+00h]
0x18008080e  test    rdi, rdi
0x180080811  jz      short loc_180080822
0x180080813  mov     rcx, rdi; hMem
0x180080816  call    cs:__imp_LocalFree
0x18008081d  nop     dword ptr [rax+rax+00h]
0x180080822  mov     eax, esi
0x180080824  lea     r11, [rsp+80h+var_s0]
0x18008082c  mov     rbx, [r11+30h]
0x180080830  mov     rsi, [r11+38h]
0x180080834  mov     rsp, r11
0x180080837  pop     r15
0x180080839  pop     r14
0x18008083b  pop     r12
0x18008083d  pop     rdi
0x18008083e  pop     rbp
0x18008083f  retn
```
