# RdlsSecretsRegCache::LoadCHEndorsedCertificates(void)

- ea: `0x180080984`
- end: `0x180080b5f`
- name: `?LoadCHEndorsedCertificates@RdlsSecretsRegCache@@AEAAKXZ`
- size: `475`
- prototype: `unsigned int __fastcall(RdlsSecretsRegCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080b70`

## callees

- `0x180080984`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800809f6`
- `ADVAPI32!RegQueryValueExW` at `0x180080a61`
- `ADVAPI32!RegQueryValueExW` at `0x180080a95`
- `ADVAPI32!RegQueryValueExW` at `0x180080aef`
- `ADVAPI32!RegQueryValueExW` at `0x1800809f6`
- `ADVAPI32!RegQueryValueExW` at `0x180080a61`
- `ADVAPI32!RegQueryValueExW` at `0x180080a95`
- `ADVAPI32!RegQueryValueExW` at `0x180080aef`
- `ADVAPI32!RegOpenKeyExW` at `0x1800809c2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800809c2`
- `ADVAPI32!RegCloseKey` at `0x180080b45`
- `ADVAPI32!RegCloseKey` at `0x180080b45`
- `KERNEL32!GetLastError` at `0x180080a31`
- `KERNEL32!GetLastError` at `0x180080ac2`
- `KERNEL32!GetLastError` at `0x180080a31`
- `KERNEL32!GetLastError` at `0x180080ac2`
- `KERNEL32!LocalAlloc` at `0x180080a1d`
- `KERNEL32!LocalAlloc` at `0x180080aae`
- `KERNEL32!LocalAlloc` at `0x180080a1d`
- `KERNEL32!LocalAlloc` at `0x180080aae`
- `KERNEL32!LocalFree` at `0x180080b1c`
- `KERNEL32!LocalFree` at `0x180080b2b`
- `KERNEL32!LocalFree` at `0x180080b1c`
- `KERNEL32!LocalFree` at `0x180080b2b`

## pseudocode

```c
__int64 __fastcall RdlsSecretsRegCache::LoadCHEndorsedCertificates(RdlsSecretsRegCache *this)
{
  LSTATUS v2; // eax
  BYTE *v3; // rdi
  LSTATUS v4; // eax
  BYTE *v5; // rbx
  unsigned int v6; // esi
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD lpcbData; // [rsp+80h] [rbp+40h] BYREF

  cbData = 0;
  lpcbData = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates", 0, 0x20019u, &hKey) )
  {
    v2 = RegQueryValueExW(hKey, L"Parm1", 0, 0, 0, &cbData);
    if ( v2 == 234 || !v2 )
    {
      v3 = (BYTE *)LocalAlloc(0x40u, cbData);
      if ( v3 )
      {
        if ( !RegQueryValueExW(hKey, L"Parm1", 0, 0, v3, &cbData) )
        {
          v4 = RegQueryValueExW(hKey, L"Parm2", 0, 0, 0, &lpcbData);
          if ( v4 == 234 || !v4 )
          {
            v5 = (BYTE *)LocalAlloc(0x40u, lpcbData);
            if ( v5 )
            {
              v6 = RegQueryValueExW(hKey, L"Parm2", 0, 0, v5, &lpcbData);
              if ( !v6 )
              {
                *((_DWORD *)this + 6) = cbData;
                *((_DWORD *)this + 10) = lpcbData;
                *((_QWORD *)this + 4) = v3;
                *((_QWORD *)this + 6) = v5;
                goto LABEL_16;
              }
              LocalFree(v5);
            }
            else
            {
              GetLastError();
            }
          }
        }
        LocalFree(v3);
      }
      else
      {
        GetLastError();
      }
    }
  }
  v6 = -1073676254;
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180080984  push    rbp
0x180080986  push    rbx
0x180080987  push    rsi
0x180080988  push    rdi
0x180080989  push    r14
0x18008098b  mov     rbp, rsp
0x18008098e  sub     rsp, 40h
0x180080992  and     [rbp+cbData], 0
0x180080996  lea     rax, [rbp+hKey]
0x18008099a  and     [rbp+arg_10], 0
0x18008099e  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x1800809a5  and     [rbp+hKey], 0
0x1800809aa  mov     r14, rcx
0x1800809ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800809b4  mov     [rsp+40h+phkResult], rax; lpData
0x1800809b9  mov     r9d, 20019h; samDesired
0x1800809bf  xor     r8d, r8d; ulOptions
0x1800809c2  call    cs:__imp_RegOpenKeyExW
0x1800809c9  nop     dword ptr [rax+rax+00h]
0x1800809ce  test    eax, eax
0x1800809d0  jnz     loc_180080B37
0x1800809d6  mov     rcx, [rbp+hKey]; hKey
0x1800809da  lea     rax, [rbp+cbData]
0x1800809de  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800809e3  lea     rdx, aParm1; "Parm1"
0x1800809ea  and     [rsp+40h+phkResult], 0
0x1800809f0  xor     r9d, r9d; lpType
0x1800809f3  xor     r8d, r8d; lpReserved
0x1800809f6  call    cs:__imp_RegQueryValueExW
0x1800809fd  nop     dword ptr [rax+rax+00h]
0x180080a02  mov     esi, 0EAh
0x180080a07  cmp     eax, esi
0x180080a09  jz      short loc_180080A13
0x180080a0b  test    eax, eax
0x180080a0d  jnz     loc_180080B37
0x180080a13  mov     edx, [rbp+cbData]; uBytes
0x180080a16  mov     ebx, 40h ; '@'
0x180080a1b  mov     ecx, ebx; uFlags
0x180080a1d  call    cs:__imp_LocalAlloc
0x180080a24  nop     dword ptr [rax+rax+00h]
0x180080a29  mov     rdi, rax
0x180080a2c  test    rax, rax
0x180080a2f  jnz     short loc_180080A42
0x180080a31  call    cs:__imp_GetLastError
0x180080a38  nop     dword ptr [rax+rax+00h]
0x180080a3d  jmp     loc_180080B37
0x180080a42  mov     rcx, [rbp+hKey]; hKey
0x180080a46  lea     rax, [rbp+cbData]
0x180080a4a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180080a4f  lea     rdx, aParm1; "Parm1"
0x180080a56  xor     r9d, r9d; lpType
0x180080a59  mov     [rsp+40h+phkResult], rdi; lpData
0x180080a5e  xor     r8d, r8d; lpReserved
0x180080a61  call    cs:__imp_RegQueryValueExW
0x180080a68  nop     dword ptr [rax+rax+00h]
0x180080a6d  test    eax, eax
0x180080a6f  jnz     loc_180080B28
0x180080a75  mov     rcx, [rbp+hKey]; hKey
0x180080a79  lea     rax, [rbp+arg_10]
0x180080a7d  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180080a82  lea     rdx, aParm2; "Parm2"
0x180080a89  and     [rsp+40h+phkResult], 0
0x180080a8f  xor     r9d, r9d; lpType
0x180080a92  xor     r8d, r8d; lpReserved
0x180080a95  call    cs:__imp_RegQueryValueExW
0x180080a9c  nop     dword ptr [rax+rax+00h]
0x180080aa1  cmp     eax, esi
0x180080aa3  jz      short loc_180080AA9
0x180080aa5  test    eax, eax
0x180080aa7  jnz     short loc_180080B28
0x180080aa9  mov     edx, [rbp+arg_10]; uBytes
0x180080aac  mov     ecx, ebx; uFlags
0x180080aae  call    cs:__imp_LocalAlloc
0x180080ab5  nop     dword ptr [rax+rax+00h]
0x180080aba  mov     rbx, rax
0x180080abd  test    rax, rax
0x180080ac0  jnz     short loc_180080AD0
0x180080ac2  call    cs:__imp_GetLastError
0x180080ac9  nop     dword ptr [rax+rax+00h]
0x180080ace  jmp     short loc_180080B28
0x180080ad0  mov     rcx, [rbp+hKey]; hKey
0x180080ad4  lea     rax, [rbp+arg_10]
0x180080ad8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180080add  lea     rdx, aParm2; "Parm2"
0x180080ae4  xor     r9d, r9d; lpType
0x180080ae7  mov     [rsp+40h+phkResult], rbx; lpData
0x180080aec  xor     r8d, r8d; lpReserved
0x180080aef  call    cs:__imp_RegQueryValueExW
0x180080af6  nop     dword ptr [rax+rax+00h]
0x180080afb  mov     esi, eax
0x180080afd  test    eax, eax
0x180080aff  jnz     short loc_180080B19
0x180080b01  mov     eax, [rbp+cbData]
0x180080b04  mov     [r14+18h], eax
0x180080b08  mov     eax, [rbp+arg_10]
0x180080b0b  mov     [r14+28h], eax
0x180080b0f  mov     [r14+20h], rdi
0x180080b13  mov     [r14+30h], rbx
0x180080b17  jmp     short loc_180080B3C
0x180080b19  mov     rcx, rbx; hMem
0x180080b1c  call    cs:__imp_LocalFree
0x180080b23  nop     dword ptr [rax+rax+00h]
0x180080b28  mov     rcx, rdi; hMem
0x180080b2b  call    cs:__imp_LocalFree
0x180080b32  nop     dword ptr [rax+rax+00h]
0x180080b37  mov     esi, 0C0010022h
0x180080b3c  mov     rcx, [rbp+hKey]; hKey
0x180080b40  test    rcx, rcx
0x180080b43  jz      short loc_180080B51
0x180080b45  call    cs:__imp_RegCloseKey
0x180080b4c  nop     dword ptr [rax+rax+00h]
0x180080b51  mov     eax, esi
0x180080b53  add     rsp, 40h
0x180080b57  pop     r14
0x180080b59  pop     rdi
0x180080b5a  pop     rsi
0x180080b5b  pop     rbx
0x180080b5c  pop     rbp
0x180080b5d  retn
```
