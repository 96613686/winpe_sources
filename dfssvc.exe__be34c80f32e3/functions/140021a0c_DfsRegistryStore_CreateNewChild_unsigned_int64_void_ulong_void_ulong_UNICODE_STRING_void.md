# DfsRegistryStore::CreateNewChild(unsigned __int64,void *,ulong,void *,ulong,_UNICODE_STRING *,void *)

- ea: `0x140021a0c`
- end: `0x140021b75`
- name: `?CreateNewChild@DfsRegistryStore@@QEAAK_KPEAXK1KPEAU_UNICODE_STRING@@1@Z`
- size: `361`
- prototype: `unsigned int(DfsRegistryStore *__hidden this, unsigned __int64, void *, unsigned int, void *, unsigned int, struct _UNICODE_STRING *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140021920`

## callees

- `0x140005f20`
- `0x140021a0c`
- `0x140024768`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140021af4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140021af4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140021a73`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140021a73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140021b2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140021b2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140021b47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140021b47`

## string_xrefs

- `0x140021b08`: `ReparsePointSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall DfsRegistryStore::CreateNewChild(
        DfsRegistryStore *this,
        HKEY a2,
        void *a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        struct _UNICODE_STRING *a7,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  struct _UNICODE_STRING *v9; // rbp
  DfsRegistryStore *v12; // rcx
  unsigned int v13; // ebx
  DfsRegistryStore *v14; // rcx
  void *v15; // rdi
  DWORD SecurityDescriptorLength; // eax
  DfsRegistryStore *v17; // rcx
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  int v20; // [rsp+58h] [rbp-20h]
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  v19 = 0;
  v9 = a7;
  v20 = 0;
  hKey = 0;
  v13 = RegCreateKeyExW(a2, a7->Buffer, 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &hKey, 0);
  if ( !v13 )
  {
    v13 = DfsRegistryStore::SetMetadata(v12, hKey, 0, L"ID", a3, a4);
    if ( !v13 )
    {
      v13 = DfsRegistryStore::SetMetadata(v14, hKey, 0, L"Svc", a5, a6);
      if ( !v13 )
      {
        v15 = pSecurityDescriptor;
        if ( pSecurityDescriptor )
        {
          SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
          v13 = DfsRegistryStore::SetMetadata(
                  v17,
                  hKey,
                  0,
                  L"ReparsePointSecurityDescriptor",
                  v15,
                  SecurityDescriptorLength);
        }
      }
    }
    RegCloseKey(hKey);
    if ( v13 )
      RegDeleteKeyExW(a2, v9->Buffer, 0, 0);
  }
  CRegistry::~CRegistry((CRegistry *)&v19);
  return v13;
}

```

## disassembly

```asm
0x140021a0c  mov     r11, rsp
0x140021a0f  mov     [r11+10h], rbx
0x140021a13  mov     [r11+18h], rbp
0x140021a17  mov     [r11+8], rcx
0x140021a1b  push    rsi
0x140021a1c  push    rdi
0x140021a1d  push    r14
0x140021a1f  sub     rsp, 60h
0x140021a23  and     qword ptr [r11-38h], 0
0x140021a28  lea     rax, [r11+8]
0x140021a2c  and     qword ptr [r11-28h], 0
0x140021a31  mov     rsi, rdx
0x140021a34  mov     rbp, [rsp+78h+arg_30]
0x140021a3c  mov     edi, r9d
0x140021a3f  and     [rsp+78h+var_20], 0
0x140021a44  lea     r9, Class; lpClass
0x140021a4b  and     qword ptr [r11+8], 0
0x140021a50  mov     r14, r8
0x140021a53  mov     [r11-40h], rax
0x140021a57  xor     r8d, r8d; Reserved
0x140021a5a  and     qword ptr [r11-48h], 0
0x140021a5f  mov     rcx, rsi; hKey
0x140021a62  mov     rdx, [rbp+8]; lpSubKey
0x140021a66  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x140021a6e  and     dword ptr [rsp+78h+var_58], 0
0x140021a73  call    cs:__imp_RegCreateKeyExW
0x140021a7a  nop     dword ptr [rax+rax+00h]
0x140021a7f  mov     ebx, eax
0x140021a81  test    eax, eax
0x140021a83  jnz     loc_140021B53
0x140021a89  mov     rdx, [rsp+78h+hKey]; HKEY
0x140021a91  lea     r9, aId; "ID"
0x140021a98  mov     [rsp+78h+samDesired], edi; unsigned int
0x140021a9c  xor     r8d, r8d; unsigned __int16 *
0x140021a9f  mov     [rsp+78h+var_58], r14; void *
0x140021aa4  call    ?SetMetadata@DfsRegistryStore@@AEAAKPEAUHKEY__@@PEBG1PEAXK@Z; DfsRegistryStore::SetMetadata(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x140021aa9  mov     ebx, eax
0x140021aab  test    eax, eax
0x140021aad  jnz     short loc_140021B22
0x140021aaf  mov     eax, [rsp+78h+arg_28]
0x140021ab6  lea     r9, aSvc; "Svc"
0x140021abd  mov     rdx, [rsp+78h+hKey]; HKEY
0x140021ac5  xor     r8d, r8d; unsigned __int16 *
0x140021ac8  mov     [rsp+78h+samDesired], eax; unsigned int
0x140021acc  mov     rax, [rsp+78h+arg_20]
0x140021ad4  mov     [rsp+78h+var_58], rax; void *
0x140021ad9  call    ?SetMetadata@DfsRegistryStore@@AEAAKPEAUHKEY__@@PEBG1PEAXK@Z; DfsRegistryStore::SetMetadata(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x140021ade  mov     ebx, eax
0x140021ae0  test    eax, eax
0x140021ae2  jnz     short loc_140021B22
0x140021ae4  mov     rdi, [rsp+78h+pSecurityDescriptor]
0x140021aec  test    rdi, rdi
0x140021aef  jz      short loc_140021B22
0x140021af1  mov     rcx, rdi; pSecurityDescriptor
0x140021af4  call    cs:__imp_GetSecurityDescriptorLength
0x140021afb  nop     dword ptr [rax+rax+00h]
0x140021b00  mov     rdx, [rsp+78h+hKey]; HKEY
0x140021b08  lea     r9, aReparsepointse; "ReparsePointSecurityDescriptor"
0x140021b0f  mov     [rsp+78h+samDesired], eax; unsigned int
0x140021b13  xor     r8d, r8d; unsigned __int16 *
0x140021b16  mov     [rsp+78h+var_58], rdi; void *
0x140021b1b  call    ?SetMetadata@DfsRegistryStore@@AEAAKPEAUHKEY__@@PEBG1PEAXK@Z; DfsRegistryStore::SetMetadata(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x140021b20  mov     ebx, eax
0x140021b22  mov     rcx, [rsp+78h+hKey]; hKey
0x140021b2a  call    cs:__imp_RegCloseKey
0x140021b31  nop     dword ptr [rax+rax+00h]
0x140021b36  test    ebx, ebx
0x140021b38  jz      short loc_140021B53
0x140021b3a  mov     rdx, [rbp+8]; lpSubKey
0x140021b3e  xor     r9d, r9d; Reserved
0x140021b41  xor     r8d, r8d; samDesired
0x140021b44  mov     rcx, rsi; hKey
0x140021b47  call    cs:__imp_RegDeleteKeyExW
0x140021b4e  nop     dword ptr [rax+rax+00h]
0x140021b53  lea     rcx, [rsp+78h+var_28]; this
0x140021b58  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140021b5d  lea     r11, [rsp+78h+var_18]
0x140021b62  mov     eax, ebx
0x140021b64  mov     rbx, [r11+28h]
0x140021b68  mov     rbp, [r11+30h]
0x140021b6c  mov     rsp, r11
0x140021b6f  pop     r14
0x140021b71  pop     rdi
0x140021b72  pop     rsi
0x140021b73  retn
```
