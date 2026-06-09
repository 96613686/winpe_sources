# RdlsSecretsRegCache::UninstallCHX509Certs(void)

- ea: `0x180081730`
- end: `0x180081816`
- name: `?UninstallCHX509Certs@RdlsSecretsRegCache@@UEAAKXZ`
- size: `230`
- prototype: `unsigned int __fastcall(RdlsSecretsRegCache *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800805c8`
- `0x180081730`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180081782`
- `ADVAPI32!RegDeleteValueW` at `0x18008179a`
- `ADVAPI32!RegDeleteValueW` at `0x1800817b2`
- `ADVAPI32!RegDeleteValueW` at `0x180081782`
- `ADVAPI32!RegDeleteValueW` at `0x18008179a`
- `ADVAPI32!RegDeleteValueW` at `0x1800817b2`
- `ADVAPI32!RegOpenKeyExW` at `0x180081766`
- `ADVAPI32!RegOpenKeyExW` at `0x180081766`
- `ADVAPI32!RegCloseKey` at `0x1800817c8`
- `ADVAPI32!RegCloseKey` at `0x1800817c8`

## string_xrefs

- `0x1800817e6`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters\Certificates.001`
- `0x1800817d4`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters\Certificates.000`

## pseudocode

```c
unsigned int __fastcall RdlsSecretsRegCache::UninstallCHX509Certs(RdlsSecretsRegCache *this)
{
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates", 0, 0xF003Fu, &hKey) )
  {
    RegDeleteValueW(hKey, L"Parm1");
    RegDeleteValueW(hKey, L"Parm2");
    RegDeleteValueW(hKey, L"Parm0");
  }
  if ( hKey )
    RegCloseKey(hKey);
  RdlsSecretsRegCache::DeleteRegistryKeyRecursively(
    this,
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters\\Certificates.000");
  RdlsSecretsRegCache::DeleteRegistryKeyRecursively(
    this,
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters\\Certificates.001");
  return RdlsSecretsRegCache::DeleteRegistryKeyRecursively(
           this,
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\TermServLicensing\\Certificates");
}

```

## disassembly

```asm
0x180081730  mov     r11, rsp
0x180081733  mov     [r11+8], rbx
0x180081737  push    rdi
0x180081738  sub     rsp, 30h
0x18008173c  and     qword ptr [r11+10h], 0
0x180081741  lea     rax, [r11+10h]
0x180081745  mov     rbx, rcx
0x180081748  mov     [r11-18h], rax
0x18008174c  mov     rdi, 0FFFFFFFF80000002h
0x180081753  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x18008175a  mov     rcx, rdi; hKey
0x18008175d  mov     r9d, 0F003Fh; samDesired
0x180081763  xor     r8d, r8d; ulOptions
0x180081766  call    cs:__imp_RegOpenKeyExW
0x18008176d  nop     dword ptr [rax+rax+00h]
0x180081772  test    eax, eax
0x180081774  jnz     short loc_1800817BE
0x180081776  mov     rcx, [rsp+38h+hKey]; hKey
0x18008177b  lea     rdx, aParm1; "Parm1"
0x180081782  call    cs:__imp_RegDeleteValueW
0x180081789  nop     dword ptr [rax+rax+00h]
0x18008178e  mov     rcx, [rsp+38h+hKey]; hKey
0x180081793  lea     rdx, aParm2; "Parm2"
0x18008179a  call    cs:__imp_RegDeleteValueW
0x1800817a1  nop     dword ptr [rax+rax+00h]
0x1800817a6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800817ab  lea     rdx, aParm0; "Parm0"
0x1800817b2  call    cs:__imp_RegDeleteValueW
0x1800817b9  nop     dword ptr [rax+rax+00h]
0x1800817be  mov     rcx, [rsp+38h+hKey]; hKey
0x1800817c3  test    rcx, rcx
0x1800817c6  jz      short loc_1800817D4
0x1800817c8  call    cs:__imp_RegCloseKey
0x1800817cf  nop     dword ptr [rax+rax+00h]
0x1800817d4  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x1800817db  mov     rdx, rdi; HKEY
0x1800817de  mov     rcx, rbx; this
0x1800817e1  call    ?DeleteRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG@Z; RdlsSecretsRegCache::DeleteRegistryKeyRecursively(HKEY__ *,ushort const *)
0x1800817e6  lea     r8, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x1800817ed  mov     rdx, rdi; HKEY
0x1800817f0  mov     rcx, rbx; this
0x1800817f3  call    ?DeleteRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG@Z; RdlsSecretsRegCache::DeleteRegistryKeyRecursively(HKEY__ *,ushort const *)
0x1800817f8  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x1800817ff  mov     rdx, rdi; HKEY
0x180081802  mov     rcx, rbx; this
0x180081805  call    ?DeleteRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG@Z; RdlsSecretsRegCache::DeleteRegistryKeyRecursively(HKEY__ *,ushort const *)
0x18008180a  mov     rbx, [rsp+38h+arg_0]
0x18008180f  add     rsp, 30h
0x180081813  pop     rdi
0x180081814  retn
```
