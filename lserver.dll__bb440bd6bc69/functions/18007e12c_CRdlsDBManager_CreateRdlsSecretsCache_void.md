# CRdlsDBManager::CreateRdlsSecretsCache(void)

- ea: `0x18007e12c`
- end: `0x18007e2aa`
- name: `?CreateRdlsSecretsCache@CRdlsDBManager@@AEAAXXZ`
- size: `382`
- prototype: `void __fastcall(CRdlsDBManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18007f368`

## callees

- `0x18000205c`
- `0x180005665`
- `0x180066200`
- `0x18007da44`
- `0x18007e04c`
- `0x18007e12c`
- `0x180082e00`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18007e1a7`
- `ADVAPI32!RegQueryValueExW` at `0x18007e1a7`
- `ADVAPI32!RegOpenKeyExW` at `0x18007e171`
- `ADVAPI32!RegOpenKeyExW` at `0x18007e171`
- `ADVAPI32!RegCloseKey` at `0x18007e1b8`
- `ADVAPI32!RegCloseKey` at `0x18007e1b8`

## string_xrefs

- `0x18007e163`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x18007e19b`: `RdlsSecretsCacheType`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CRdlsDBManager::CreateRdlsSecretsCache(CRdlsDBManager *this)
{
  struct IRdlsDBConnection *v2; // rsi
  _QWORD *v3; // rax
  struct RdlsSecretsCache *Instance; // rbx
  _QWORD *v5; // rax
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v9; // [rsp+68h] [rbp+20h]

  hKey = 0;
  Data = 1;
  cbData = 4;
  *((_QWORD *)this + 329) = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
          0,
          1u,
          &hKey) )
    RegQueryValueExW(hKey, L"RdlsSecretsCacheType", 0, 0, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  if ( Data == 3 )
  {
    v2 = CRdlsDBManager::AcquireRdlsDBConnection(this);
    v3 = operator new(0x338u);
    Instance = (struct RdlsSecretsCache *)v3;
    v9 = v3;
    if ( v3 )
    {
      *v3 = &IRdlsSecretsCache::`vftable';
      *v3 = &RdlsSecretsCache::`vftable';
      memset_0(v3 + 1, 0, 0x50u);
      *(_QWORD *)Instance = &RdlsSecretsDBCache::`vftable';
      __RdlsSecret::__RdlsSecret((struct RdlsSecretsCache *)((char *)Instance + 88));
      *((_QWORD *)Instance + 102) = v2;
      RdlsSecretsDBCache::ReadOrSetupInitalSecrets(Instance);
    }
    else
    {
      Instance = 0;
    }
  }
  else if ( Data == 2 )
  {
    Instance = RdlsSecretsMemCache::CreateInstance();
  }
  else
  {
    v5 = operator new(0x60u);
    Instance = (struct RdlsSecretsCache *)v5;
    v9 = v5;
    if ( v5 )
    {
      *v5 = &IRdlsSecretsCache::`vftable';
      *v5 = &RdlsSecretsCache::`vftable';
      memset_0(v5 + 1, 0, 0x50u);
      *(_QWORD *)Instance = &RdlsSecretsRegCache::`vftable';
      *((_QWORD *)Instance + 11) = 0;
    }
    else
    {
      Instance = 0;
    }
  }
  *((_QWORD *)this + 329) = Instance;
}

```

## disassembly

```asm
0x18007e12c  mov     rax, rsp
0x18007e12f  push    rbx
0x18007e130  push    rsi
0x18007e131  push    rdi
0x18007e132  sub     rsp, 30h
0x18007e136  mov     rdi, rcx
0x18007e139  and     qword ptr [rax+18h], 0
0x18007e13e  mov     r9d, 1; samDesired
0x18007e144  mov     [rax+8], r9d
0x18007e148  mov     dword ptr [rax+10h], 4
0x18007e14f  and     qword ptr [rcx+0A48h], 0
0x18007e157  lea     rax, [rax+18h]
0x18007e15b  mov     [rsp+48h+phkResult], rax; phkResult
0x18007e160  xor     r8d, r8d; ulOptions
0x18007e163  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18007e16a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e171  call    cs:__imp_RegOpenKeyExW
0x18007e178  nop     dword ptr [rax+rax+00h]
0x18007e17d  test    eax, eax
0x18007e17f  jnz     short loc_18007E1B3
0x18007e181  lea     rax, [rsp+48h+cbData]
0x18007e186  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007e18b  lea     rax, [rsp+48h+Data]
0x18007e190  mov     [rsp+48h+phkResult], rax; lpData
0x18007e195  xor     r9d, r9d; lpType
0x18007e198  xor     r8d, r8d; lpReserved
0x18007e19b  lea     rdx, aRdlssecretscac; "RdlsSecretsCacheType"
0x18007e1a2  mov     rcx, [rsp+48h+hKey]; hKey
0x18007e1a7  call    cs:__imp_RegQueryValueExW
0x18007e1ae  nop     dword ptr [rax+rax+00h]
0x18007e1b3  mov     rcx, [rsp+48h+hKey]; hKey
0x18007e1b8  call    cs:__imp_RegCloseKey
0x18007e1bf  nop     dword ptr [rax+rax+00h]
0x18007e1c4  cmp     [rsp+48h+Data], 3
0x18007e1c9  jnz     short loc_18007E23B
0x18007e1cb  mov     rcx, rdi; this
0x18007e1ce  call    ?AcquireRdlsDBConnection@CRdlsDBManager@@QEAAPEAVIRdlsDBConnection@@XZ; CRdlsDBManager::AcquireRdlsDBConnection(void)
0x18007e1d3  mov     rsi, rax
0x18007e1d6  mov     ecx, 338h; Size
0x18007e1db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e1e0  mov     rbx, rax
0x18007e1e3  mov     [rsp+48h+arg_18], rax
0x18007e1e8  test    rax, rax
0x18007e1eb  jz      short loc_18007E237
0x18007e1ed  lea     rcx, ??_7IRdlsSecretsCache@@6B@; const IRdlsSecretsCache::`vftable'
0x18007e1f4  mov     [rax], rcx
0x18007e1f7  lea     rax, ??_7RdlsSecretsCache@@6B@; const RdlsSecretsCache::`vftable'
0x18007e1fe  mov     [rbx], rax
0x18007e201  lea     rcx, [rbx+8]; void *
0x18007e205  xor     edx, edx; Val
0x18007e207  lea     r8d, [rdx+50h]; Size
0x18007e20b  call    memset_0
0x18007e210  nop
0x18007e211  lea     rax, ??_7RdlsSecretsDBCache@@6B@; const RdlsSecretsDBCache::`vftable'
0x18007e218  mov     [rbx], rax
0x18007e21b  lea     rcx, [rbx+58h]; this
0x18007e21f  call    ??0__RdlsSecret@@QEAA@XZ; __RdlsSecret::__RdlsSecret(void)
0x18007e224  nop
0x18007e225  mov     [rbx+330h], rsi
0x18007e22c  mov     rcx, rbx; this
0x18007e22f  call    ?ReadOrSetupInitalSecrets@RdlsSecretsDBCache@@AEAAKXZ; RdlsSecretsDBCache::ReadOrSetupInitalSecrets(void)
0x18007e234  nop
0x18007e235  jmp     short loc_18007E239
0x18007e237  xor     ebx, ebx
0x18007e239  jmp     short loc_18007E29A
0x18007e23b  cmp     [rsp+48h+Data], 2
0x18007e240  jnz     short loc_18007E24C
0x18007e242  call    ?CreateInstance@RdlsSecretsMemCache@@SAPEAVRdlsSecretsCache@@XZ; RdlsSecretsMemCache::CreateInstance(void)
0x18007e247  mov     rbx, rax
0x18007e24a  jmp     short loc_18007E29A
0x18007e24c  mov     ecx, 60h ; '`'; Size
0x18007e251  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007e256  mov     rbx, rax
0x18007e259  mov     [rsp+48h+arg_18], rax
0x18007e25e  test    rax, rax
0x18007e261  jz      short loc_18007E298
0x18007e263  lea     rcx, ??_7IRdlsSecretsCache@@6B@; const IRdlsSecretsCache::`vftable'
0x18007e26a  mov     [rax], rcx
0x18007e26d  lea     rax, ??_7RdlsSecretsCache@@6B@; const RdlsSecretsCache::`vftable'
0x18007e274  mov     [rbx], rax
0x18007e277  lea     rcx, [rbx+8]; void *
0x18007e27b  xor     edx, edx; Val
0x18007e27d  lea     r8d, [rdx+50h]; Size
0x18007e281  call    memset_0
0x18007e286  nop
0x18007e287  lea     rax, ??_7RdlsSecretsRegCache@@6B@; const RdlsSecretsRegCache::`vftable'
0x18007e28e  mov     [rbx], rax
0x18007e291  and     qword ptr [rbx+58h], 0
0x18007e296  jmp     short loc_18007E29A
0x18007e298  xor     ebx, ebx
0x18007e29a  mov     [rdi+0A48h], rbx
0x18007e2a1  add     rsp, 30h
0x18007e2a5  pop     rdi
0x18007e2a6  pop     rsi
0x18007e2a7  pop     rbx
0x18007e2a8  retn
```
