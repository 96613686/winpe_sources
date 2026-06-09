# RegOpenRDInterfaceKey

- ea: `0x18000a728`
- end: `0x18000aa02`
- name: `RegOpenRDInterfaceKey`
- size: `730`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, PHKEY phkResult, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800093b0`

## callees

- `0x180007c0c`
- `0x18000a728`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000a7c7`
- `ADVAPI32!RegEnumKeyExW` at `0x18000a7c7`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a884`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a884`
- `ADVAPI32!RegQueryValueExW` at `0x18000a90e`
- `ADVAPI32!RegQueryValueExW` at `0x18000a90e`
- `ADVAPI32!RegCloseKey` at `0x18000a9d1`
- `ADVAPI32!RegCloseKey` at `0x18000a9d1`

## string_xrefs

- `0x18000a7f5`: `RegOpenRDInterfaceKey: RegEnumKeyEx failed with error = %d`
- `0x18000a8b3`: `RegOpenRDInterfaceKey: RegOpenKeyEx (%s) failed with error = %d`
- `0x18000a94d`: `RegOpenRDInterfaceKey: RegQueryValueEx (%s) failed with error = %d`

## pseudocode

```c
__int64 __fastcall RegOpenRDInterfaceKey(HKEY hKey, DWORD dwIndex, PHKEY phkResult, LPBYTE lpData)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r8
  __int64 v14; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-B0h] BYREF
  int *v20; // [rsp+60h] [rbp-A0h]
  int v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+6Ch] [rbp-94h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v25[2044]; // [rsp+284h] [rbp+184h] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  memset_0(Name, 0, 0x202u);
  cchName = 257;
  Type = 0;
  cbData = 514;
  *phkResult = 0;
  v8 = RegEnumKeyExW(hKey, dwIndex, Name, &cchName, 0, 0, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"RegOpenRDInterfaceKey: RegEnumKeyEx failed with error = %d", v8);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v25[2 * v11 - 4] );
LABEL_6:
        v22 = 0;
        v21 = 2 * v11 + 2;
        v20 = &v24;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v10, 2, v19);
        goto LABEL_22;
      }
    }
    goto LABEL_22;
  }
  v12 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, phkResult);
  v9 = v12;
  if ( !v12 )
  {
    v9 = RegQueryValueExW(*phkResult, L"InterfaceName", 0, &Type, lpData, &cbData);
    if ( !v9 )
    {
      if ( Type == 1 )
        goto LABEL_21;
      v9 = 1015;
    }
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"RegOpenRDInterfaceKey: RegQueryValueEx (%s) failed with error = %d", Name, v9);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&v25[2 * v14 - 4] );
        v22 = 0;
        v21 = 2 * v14 + 2;
        v20 = &v24;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v13, 2, v19);
      }
    }
LABEL_21:
    *((_WORD *)lpData + 256) = 0;
    if ( !v9 )
      return v9;
    goto LABEL_22;
  }
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"RegOpenRDInterfaceKey: RegOpenKeyEx (%s) failed with error = %d", Name, v12);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v25[2 * v11 - 4] );
      goto LABEL_6;
    }
  }
LABEL_22:
  if ( *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18000a728  push    rbp
0x18000a72a  push    rbx
0x18000a72b  push    rsi
0x18000a72c  push    rdi
0x18000a72d  push    r12
0x18000a72f  push    r14
0x18000a731  lea     rbp, [rsp-998h]
0x18000a739  sub     rsp, 0A98h
0x18000a740  mov     rax, cs:__security_cookie
0x18000a747  xor     rax, rsp
0x18000a74a  mov     [rbp+9C0h+var_40], rax
0x18000a751  mov     rdi, r8
0x18000a754  mov     ebx, edx
0x18000a756  mov     r14, rcx
0x18000a759  xor     r12d, r12d
0x18000a75c  xor     edx, edx; Val
0x18000a75e  mov     [rbp+9C0h+var_840], r12d
0x18000a765  mov     r8d, 7FCh; Size
0x18000a76b  lea     rcx, [rbp+9C0h+var_83C]; void *
0x18000a772  mov     rsi, r9
0x18000a775  call    memset_0
0x18000a77a  xor     edx, edx; Val
0x18000a77c  lea     rcx, [rsp+0AC0h+Name]; void *
0x18000a781  mov     r8d, 202h; Size
0x18000a787  call    memset_0
0x18000a78c  mov     [rsp+0AC0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000a791  lea     r9, [rsp+0AC0h+cchName]; lpcchName
0x18000a796  mov     [rsp+0AC0h+lpcchClass], r12; lpcchClass
0x18000a79b  lea     r8, [rsp+0AC0h+Name]; lpName
0x18000a7a0  mov     [rsp+0AC0h+lpClass], r12; lpClass
0x18000a7a5  mov     edx, ebx; dwIndex
0x18000a7a7  mov     rcx, r14; hKey
0x18000a7aa  mov     [rsp+0AC0h+lpReserved], r12; lpReserved
0x18000a7af  mov     [rsp+0AC0h+cchName], 101h
0x18000a7b7  mov     [rsp+0AC0h+Type], r12d
0x18000a7bc  mov     [rsp+0AC0h+cbData], 202h
0x18000a7c4  mov     [rdi], r12
0x18000a7c7  call    cs:__imp_RegEnumKeyExW
0x18000a7ce  nop     dword ptr [rax+rax+00h]
0x18000a7d3  mov     ebx, eax
0x18000a7d5  test    eax, eax
0x18000a7d7  jz      loc_18000A86E
0x18000a7dd  test    cs:byte_1800CF404, 8
0x18000a7e4  jz      loc_18000A9C9
0x18000a7ea  mov     r8d, eax
0x18000a7ed  mov     word ptr [rbp+9C0h+var_840], r12w
0x18000a7f5  lea     rdx, aRegopenrdinter; "RegOpenRDInterfaceKey: RegEnumKeyEx fai"...
0x18000a7fc  lea     rcx, [rbp+9C0h+var_840]
0x18000a803  call    FormatRRASErrorString
0x18000a808  test    cs:byte_1800CF404, 8
0x18000a80f  jz      loc_18000A9C9
0x18000a815  lea     rcx, [rbp+9C0h+var_840]
0x18000a81c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a820  inc     rax
0x18000a823  cmp     [rcx+rax*2], r12w
0x18000a828  jnz     short loc_18000A820
0x18000a82a  lea     eax, ds:2[rax*2]
0x18000a831  mov     [rsp+0AC0h+var_A54], r12d
0x18000a836  lea     rcx, [rbp+9C0h+var_840]
0x18000a83d  mov     [rsp+0AC0h+var_A58], eax
0x18000a841  lea     rax, [rsp+0AC0h+var_A70]
0x18000a846  mov     [rsp+0AC0h+var_A60], rcx
0x18000a84b  mov     r9d, 2
0x18000a851  mov     [rsp+0AC0h+lpReserved], rax
0x18000a856  lea     rdx, RasDdmTraceError
0x18000a85d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a864  call    McGenEventWrite_EventWriteTransfer
0x18000a869  jmp     loc_18000A9C9
0x18000a86e  mov     r9d, 20019h; samDesired
0x18000a874  mov     [rsp+0AC0h+lpReserved], rdi; phkResult
0x18000a879  xor     r8d, r8d; ulOptions
0x18000a87c  lea     rdx, [rsp+0AC0h+Name]; lpSubKey
0x18000a881  mov     rcx, r14; hKey
0x18000a884  call    cs:__imp_RegOpenKeyExW
0x18000a88b  nop     dword ptr [rax+rax+00h]
0x18000a890  mov     ebx, eax
0x18000a892  test    eax, eax
0x18000a894  jz      short loc_18000A8ED
0x18000a896  test    cs:byte_1800CF404, 8
0x18000a89d  jz      loc_18000A9C9
0x18000a8a3  mov     r9d, eax
0x18000a8a6  mov     word ptr [rbp+9C0h+var_840], r12w
0x18000a8ae  lea     r8, [rsp+0AC0h+Name]
0x18000a8b3  lea     rdx, aRegopenrdinter_0; "RegOpenRDInterfaceKey: RegOpenKeyEx (%s"...
0x18000a8ba  lea     rcx, [rbp+9C0h+var_840]
0x18000a8c1  call    FormatRRASErrorString
0x18000a8c6  test    cs:byte_1800CF404, 8
0x18000a8cd  jz      loc_18000A9C9
0x18000a8d3  lea     rcx, [rbp+9C0h+var_840]
0x18000a8da  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a8de  inc     rax
0x18000a8e1  cmp     [rcx+rax*2], r12w
0x18000a8e6  jnz     short loc_18000A8DE
0x18000a8e8  jmp     loc_18000A82A
0x18000a8ed  mov     rcx, [rdi]; hKey
0x18000a8f0  lea     rax, [rsp+0AC0h+cbData]
0x18000a8f5  mov     [rsp+0AC0h+lpClass], rax; lpcbData
0x18000a8fa  lea     r9, [rsp+0AC0h+Type]; lpType
0x18000a8ff  xor     r8d, r8d; lpReserved
0x18000a902  mov     [rsp+0AC0h+lpReserved], rsi; lpData
0x18000a907  lea     rdx, aInterfacename; "InterfaceName"
0x18000a90e  call    cs:__imp_RegQueryValueExW
0x18000a915  nop     dword ptr [rax+rax+00h]
0x18000a91a  mov     ebx, eax
0x18000a91c  test    eax, eax
0x18000a91e  jnz     short loc_18000A930
0x18000a920  cmp     [rsp+0AC0h+Type], 1
0x18000a925  jz      loc_18000A9BD
0x18000a92b  mov     ebx, 3F7h
0x18000a930  test    cs:byte_1800CF404, 8
0x18000a937  jz      loc_18000A9BD
0x18000a93d  mov     r9d, ebx
0x18000a940  mov     word ptr [rbp+9C0h+var_840], r12w
0x18000a948  lea     r8, [rsp+0AC0h+Name]
0x18000a94d  lea     rdx, aRegopenrdinter_1; "RegOpenRDInterfaceKey: RegQueryValueEx "...
0x18000a954  lea     rcx, [rbp+9C0h+var_840]
0x18000a95b  call    FormatRRASErrorString
0x18000a960  test    cs:byte_1800CF404, 8
0x18000a967  jz      short loc_18000A9BD
0x18000a969  lea     rcx, [rbp+9C0h+var_840]
0x18000a970  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a974  inc     rax
0x18000a977  cmp     [rcx+rax*2], r12w
0x18000a97c  jnz     short loc_18000A974
0x18000a97e  lea     eax, ds:2[rax*2]
0x18000a985  mov     [rsp+0AC0h+var_A54], r12d
0x18000a98a  lea     rcx, [rbp+9C0h+var_840]
0x18000a991  mov     [rsp+0AC0h+var_A58], eax
0x18000a995  lea     rax, [rsp+0AC0h+var_A70]
0x18000a99a  mov     [rsp+0AC0h+var_A60], rcx
0x18000a99f  mov     r9d, 2
0x18000a9a5  mov     [rsp+0AC0h+lpReserved], rax
0x18000a9aa  lea     rdx, RasDdmTraceError
0x18000a9b1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a9b8  call    McGenEventWrite_EventWriteTransfer
0x18000a9bd  mov     [rsi+200h], r12w
0x18000a9c5  test    ebx, ebx
0x18000a9c7  jz      short loc_18000A9E0
0x18000a9c9  mov     rcx, [rdi]; hKey
0x18000a9cc  test    rcx, rcx
0x18000a9cf  jz      short loc_18000A9E0
0x18000a9d1  call    cs:__imp_RegCloseKey
0x18000a9d8  nop     dword ptr [rax+rax+00h]
0x18000a9dd  mov     [rdi], r12
0x18000a9e0  mov     eax, ebx
0x18000a9e2  mov     rcx, [rbp+9C0h+var_40]
0x18000a9e9  xor     rcx, rsp; StackCookie
0x18000a9ec  call    __security_check_cookie
0x18000a9f1  add     rsp, 0A98h
0x18000a9f8  pop     r14
0x18000a9fa  pop     r12
0x18000a9fc  pop     rdi
0x18000a9fd  pop     rsi
0x18000a9fe  pop     rbx
0x18000a9ff  pop     rbp
0x18000aa00  retn
```
