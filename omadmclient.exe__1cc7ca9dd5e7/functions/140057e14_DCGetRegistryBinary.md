# DCGetRegistryBinary

- ea: `0x140057e14`
- end: `0x140057f8a`
- name: `DCGetRegistryBinary`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14005c570`

## callees

- `0x1400036e4`
- `0x140005888`
- `0x14000b0f4`
- `0x140057e14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057e81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140057e81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140057ecd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140057f26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140057ecd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140057f26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057f6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140057f6e`

## string_xrefs

- `0x140057e4c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\ObjectModel\lib\DeclaredConfigurationCommon.h`

## pseudocode

```c
__int64 __fastcall DCGetRegistryBinary(HKEY a1, const WCHAR *a2, const WCHAR *a3, BYTE **a4, DWORD *a5)
{
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD v11; // ecx
  BYTE *v12; // rdi
  DWORD *v13; // rax
  int phkResult; // [rsp+20h] [rbp-28h]
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF

  Type = 3;
  hKey = 0;
  cbData = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\ObjectModel\\lib\\DeclaredConfigurationCommon.h",
      (const char *)0x80070057LL,
      phkResult);
    return v8;
  }
  if ( a2 )
  {
    v9 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
LABEL_21:
      if ( hKey )
        RegCloseKey(hKey);
      return v8;
    }
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v10 = RegQueryValueExW(a1, a3, 0, &Type, 0, &cbData);
  v8 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
LABEL_20:
    if ( !a2 )
      return v8;
    goto LABEL_21;
  }
  if ( Type != 3 )
  {
    v8 = -2147418113;
    goto LABEL_20;
  }
  v11 = cbData;
  v12 = 0;
  if ( !cbData )
  {
LABEL_19:
    v13 = a5;
    v8 = 0;
    *a4 = v12;
    cbData = 0;
    *v13 = v11;
    goto LABEL_20;
  }
  v12 = (BYTE *)operator new[](cbData);
  v8 = RegQueryValueExW(hKey, a3, 0, &Type, v12, &cbData);
  if ( !v8 )
  {
    v11 = cbData;
    goto LABEL_19;
  }
  operator delete(v12);
  if ( (int)v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return v8;
}

```

## disassembly

```asm
0x140057e14  push    rbp
0x140057e16  push    rbx
0x140057e17  push    rsi
0x140057e18  push    rdi
0x140057e19  push    r14
0x140057e1b  push    r15
0x140057e1d  mov     rbp, rsp
0x140057e20  sub     rsp, 48h
0x140057e24  mov     [rbp+Type], 3
0x140057e2b  mov     r15, r9
0x140057e2e  mov     [rbp+hKey], 0
0x140057e36  mov     r14, r8
0x140057e39  mov     [rbp+cbData], 0
0x140057e40  mov     rsi, rdx
0x140057e43  test    rcx, rcx
0x140057e46  jnz     short loc_140057E6A
0x140057e48  mov     rcx, [rbp+30h]; this
0x140057e4c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x140057e53  mov     ebx, 80070057h
0x140057e58  mov     edx, 2A7h; void *
0x140057e5d  mov     r9d, ebx; char *
0x140057e60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140057e65  jmp     loc_140057F7A
0x140057e6a  test    rsi, rsi
0x140057e6d  jz      short loc_140057EAD
0x140057e6f  lea     rax, [rbp+hKey]
0x140057e73  mov     r9d, 20119h; samDesired
0x140057e79  xor     r8d, r8d; ulOptions
0x140057e7c  mov     [rsp+48h+phkResult], rax; phkResult
0x140057e81  call    cs:__imp_RegOpenKeyExW
0x140057e88  nop     dword ptr [rax+rax+00h]
0x140057e8d  mov     ebx, eax
0x140057e8f  test    eax, eax
0x140057e91  jz      short loc_140057EA7
0x140057e93  jle     loc_140057F65
0x140057e99  movzx   ebx, ax
0x140057e9c  or      ebx, 80070000h
0x140057ea2  jmp     loc_140057F65
0x140057ea7  mov     rcx, [rbp+hKey]; hKey
0x140057eab  jmp     short loc_140057EB1
0x140057ead  mov     [rbp+hKey], rcx
0x140057eb1  lea     rax, [rbp+cbData]
0x140057eb5  xor     r8d, r8d; lpReserved
0x140057eb8  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140057ebd  lea     r9, [rbp+Type]; lpType
0x140057ec1  mov     rdx, r14; lpValueName
0x140057ec4  mov     [rsp+48h+phkResult], 0; lpData
0x140057ecd  call    cs:__imp_RegQueryValueExW
0x140057ed4  nop     dword ptr [rax+rax+00h]
0x140057ed9  mov     ebx, eax
0x140057edb  test    eax, eax
0x140057edd  jz      short loc_140057EEC
0x140057edf  jle     short loc_140057F60
0x140057ee1  movzx   ebx, ax
0x140057ee4  or      ebx, 80070000h
0x140057eea  jmp     short loc_140057F60
0x140057eec  cmp     [rbp+Type], 3
0x140057ef0  jz      short loc_140057EF9
0x140057ef2  mov     ebx, 8000FFFFh
0x140057ef7  jmp     short loc_140057F60
0x140057ef9  mov     ecx, [rbp+cbData]; unsigned __int64
0x140057efc  xor     edi, edi
0x140057efe  test    ecx, ecx
0x140057f00  jz      short loc_140057F52
0x140057f02  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140057f07  mov     rcx, [rbp+hKey]; hKey
0x140057f0b  lea     r9, [rbp+Type]; lpType
0x140057f0f  mov     rdi, rax
0x140057f12  xor     r8d, r8d; lpReserved
0x140057f15  lea     rax, [rbp+cbData]
0x140057f19  mov     rdx, r14; lpValueName
0x140057f1c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140057f21  mov     [rsp+48h+phkResult], rdi; lpData
0x140057f26  call    cs:__imp_RegQueryValueExW
0x140057f2d  nop     dword ptr [rax+rax+00h]
0x140057f32  mov     ebx, eax
0x140057f34  test    eax, eax
0x140057f36  jz      short loc_140057F4F
0x140057f38  mov     rcx, rdi; Block
0x140057f3b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140057f40  test    ebx, ebx
0x140057f42  jle     short loc_140057F7A
0x140057f44  movzx   ebx, bx
0x140057f47  or      ebx, 80070000h
0x140057f4d  jmp     short loc_140057F7A
0x140057f4f  mov     ecx, [rbp+cbData]
0x140057f52  mov     rax, [rbp+arg_20]
0x140057f56  xor     ebx, ebx
0x140057f58  mov     [r15], rdi
0x140057f5b  mov     [rbp+cbData], ebx
0x140057f5e  mov     [rax], ecx
0x140057f60  test    rsi, rsi
0x140057f63  jz      short loc_140057F7A
0x140057f65  mov     rcx, [rbp+hKey]; hKey
0x140057f69  test    rcx, rcx
0x140057f6c  jz      short loc_140057F7A
0x140057f6e  call    cs:__imp_RegCloseKey
0x140057f75  nop     dword ptr [rax+rax+00h]
0x140057f7a  mov     eax, ebx
0x140057f7c  add     rsp, 48h
0x140057f80  pop     r15
0x140057f82  pop     r14
0x140057f84  pop     rdi
0x140057f85  pop     rsi
0x140057f86  pop     rbx
0x140057f87  pop     rbp
0x140057f88  retn
```
