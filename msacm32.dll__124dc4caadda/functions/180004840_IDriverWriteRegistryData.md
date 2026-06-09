# IDriverWriteRegistryData

- ea: `0x180004840`
- end: `0x180004aa1`
- name: `IDriverWriteRegistryData`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800040a0`

## callees

- `0x180004840`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000497d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a3b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000497d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800049dc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004a3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004a7e`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800048d1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180004942`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800048d1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180004942`

## string_xrefs

- `0x180004891`: `Software\Microsoft\AudioCompressionManager\DriverCache`
- `0x1800049c7`: `aFormatTagCache`
- `0x180004a26`: `aFilterTagCache`

## pseudocode

```c
__int64 __fastcall IDriverWriteRegistryData(__int64 a1)
{
  int v1; // eax
  const BYTE *v4; // rbp
  int v5; // esi
  int v6; // edi
  const BYTE *v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // rcx
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  __int64 v12; // rdx
  WCHAR *v13; // rcx
  HKEY hKey; // [rsp+30h] [rbp-168h] BYREF
  BYTE lpData[4]; // [rsp+38h] [rbp-160h] BYREF
  BYTE v16[4]; // [rsp+3Ch] [rbp-15Ch] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-158h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-150h] BYREF
  WCHAR SubKey[144]; // [rsp+50h] [rbp-148h] BYREF

  v1 = *(_DWORD *)(a1 + 52) & 7;
  phkResult = 0;
  hKey = 0;
  if ( (_BYTE)v1 != 1 )
    return 8;
  v4 = *(const BYTE **)(a1 + 68);
  v5 = *(_DWORD *)(a1 + 76);
  v6 = *(_DWORD *)(a1 + 64);
  v7 = *(const BYTE **)(a1 + 80);
  *(_DWORD *)Data = *(_DWORD *)(a1 + 60);
  *(_DWORD *)lpData = v6;
  *(_DWORD *)v16 = v5;
  if ( RegCreateKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\AudioCompressionManager\\DriverCache", &phkResult) )
  {
    phkResult = 0;
    v8 = 7;
  }
  else
  {
    v9 = 2147483646;
    v10 = SubKey;
    v11 = (WCHAR *)(a1 + 120);
    v12 = 144;
    do
    {
      if ( !v9 )
        break;
      if ( !*v11 )
        break;
      *v10++ = *v11++;
      --v9;
      --v12;
    }
    while ( v12 );
    v13 = v10 - 1;
    if ( v12 )
      v13 = v10;
    *v13 = 0;
    if ( RegCreateKeyW(phkResult, SubKey, &hKey) )
    {
      v8 = 7;
    }
    else
    {
      RegSetValueExW(hKey, gszValfdwSupport, 0, 4u, Data, 4u);
      RegSetValueExW(hKey, gszValcFormatTags, 0, 4u, lpData, 4u);
      if ( *(_DWORD *)lpData )
        RegSetValueExW(hKey, gszValaFormatTagCache, 0, 3u, v4, 8 * v6);
      RegSetValueExW(hKey, gszValcFilterTags, 0, 4u, v16, 4u);
      if ( *(_DWORD *)v16 )
        RegSetValueExW(hKey, gszValaFilterTagCache, 0, 3u, v7, 8 * v5);
      v8 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v8;
}

```

## disassembly

```asm
0x180004840  push    rbx
0x180004842  push    r15
0x180004844  sub     rsp, 188h
0x18000484b  mov     rax, cs:__security_cookie
0x180004852  xor     rax, rsp
0x180004855  mov     [rsp+198h+var_28], rax
0x18000485d  mov     eax, [rcx+34h]
0x180004860  xor     r15d, r15d
0x180004863  and     eax, 7
0x180004866  mov     [rsp+198h+phkResult], r15
0x18000486b  mov     [rsp+198h+hKey], r15
0x180004870  mov     rbx, rcx
0x180004873  cmp     al, 1
0x180004875  jz      short loc_180004881
0x180004877  mov     eax, 8
0x18000487c  jmp     loc_180004A86
0x180004881  mov     eax, [rcx+3Ch]
0x180004884  lea     r8, [rsp+198h+phkResult]; phkResult
0x180004889  mov     [rsp+198h+arg_8], rbp
0x180004891  lea     rdx, gszDriverCache; "Software\\Microsoft\\AudioCompressionMa"...
0x180004898  mov     rbp, [rcx+44h]
0x18000489c  mov     [rsp+198h+arg_10], rsi
0x1800048a4  mov     esi, [rcx+4Ch]
0x1800048a7  mov     [rsp+198h+arg_18], rdi
0x1800048af  mov     edi, [rcx+40h]
0x1800048b2  mov     [rsp+198h+var_18], r14
0x1800048ba  mov     r14, [rcx+50h]
0x1800048be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800048c5  mov     dword ptr [rsp+198h+Data], eax
0x1800048c9  mov     dword ptr [rsp+198h+var_160], edi
0x1800048cd  mov     dword ptr [rsp+198h+var_15C], esi
0x1800048d1  call    cs:__imp_RegCreateKeyW
0x1800048d7  test    eax, eax
0x1800048d9  jz      short loc_1800048EA
0x1800048db  mov     [rsp+198h+phkResult], r15
0x1800048e0  mov     ebx, 7
0x1800048e5  jmp     loc_180004A44
0x1800048ea  mov     ecx, 7FFFFFFEh
0x1800048ef  lea     rax, [rsp+198h+SubKey]
0x1800048f4  add     rbx, 78h ; 'x'
0x1800048f8  mov     edx, 90h
0x1800048fd  nop     dword ptr [rax]
0x180004900  test    rcx, rcx
0x180004903  jz      short loc_180004924
0x180004905  movzx   r8d, word ptr [rbx]
0x180004909  test    r8w, r8w
0x18000490d  jz      short loc_180004924
0x18000490f  mov     [rax], r8w
0x180004913  add     rbx, 2
0x180004917  add     rax, 2
0x18000491b  dec     rcx
0x18000491e  sub     rdx, 1
0x180004922  jnz     short loc_180004900
0x180004924  test    rdx, rdx
0x180004927  lea     rcx, [rax-2]
0x18000492b  lea     r8, [rsp+198h+hKey]; phkResult
0x180004930  cmovnz  rcx, rax
0x180004934  lea     rdx, [rsp+198h+SubKey]; lpSubKey
0x180004939  mov     [rcx], r15w
0x18000493d  mov     rcx, [rsp+198h+phkResult]; hKey
0x180004942  call    cs:__imp_RegCreateKeyW
0x180004948  test    eax, eax
0x18000494a  jz      short loc_180004956
0x18000494c  mov     ebx, 7
0x180004951  jmp     loc_180004A44
0x180004956  mov     rcx, [rsp+198h+hKey]; hKey
0x18000495b  lea     rax, [rsp+198h+Data]
0x180004960  mov     [rsp+198h+cbData], 4; cbData
0x180004968  lea     rdx, gszValfdwSupport; "fdwSupport"
0x18000496f  mov     r9d, 4; dwType
0x180004975  mov     [rsp+198h+lpData], rax; lpData
0x18000497a  xor     r8d, r8d; Reserved
0x18000497d  call    cs:__imp_RegSetValueExW
0x180004983  mov     rcx, [rsp+198h+hKey]; hKey
0x180004988  lea     rax, [rsp+198h+var_160]
0x18000498d  mov     [rsp+198h+cbData], 4; cbData
0x180004995  lea     rdx, gszValcFormatTags; "cFormatTags"
0x18000499c  mov     r9d, 4; dwType
0x1800049a2  mov     [rsp+198h+lpData], rax; lpData
0x1800049a7  xor     r8d, r8d; Reserved
0x1800049aa  call    cs:__imp_RegSetValueExW
0x1800049b0  cmp     dword ptr [rsp+198h+var_160], r15d
0x1800049b5  jz      short loc_1800049E2
0x1800049b7  mov     rcx, [rsp+198h+hKey]; hKey
0x1800049bc  lea     eax, ds:0[rdi*8]
0x1800049c3  mov     [rsp+198h+cbData], eax; cbData
0x1800049c7  lea     rdx, gszValaFormatTagCache; "aFormatTagCache"
0x1800049ce  mov     r9d, 3; dwType
0x1800049d4  mov     [rsp+198h+lpData], rbp; lpData
0x1800049d9  xor     r8d, r8d; Reserved
0x1800049dc  call    cs:__imp_RegSetValueExW
0x1800049e2  mov     rcx, [rsp+198h+hKey]; hKey
0x1800049e7  lea     rax, [rsp+198h+var_15C]
0x1800049ec  mov     [rsp+198h+cbData], 4; cbData
0x1800049f4  lea     rdx, gszValcFilterTags; "cFilterTags"
0x1800049fb  mov     r9d, 4; dwType
0x180004a01  mov     [rsp+198h+lpData], rax; lpData
0x180004a06  xor     r8d, r8d; Reserved
0x180004a09  call    cs:__imp_RegSetValueExW
0x180004a0f  cmp     dword ptr [rsp+198h+var_15C], r15d
0x180004a14  jz      short loc_180004A41
0x180004a16  mov     rcx, [rsp+198h+hKey]; hKey
0x180004a1b  lea     eax, ds:0[rsi*8]
0x180004a22  mov     [rsp+198h+cbData], eax; cbData
0x180004a26  lea     rdx, gszValaFilterTagCache; "aFilterTagCache"
0x180004a2d  mov     r9d, 3; dwType
0x180004a33  mov     [rsp+198h+lpData], r14; lpData
0x180004a38  xor     r8d, r8d; Reserved
0x180004a3b  call    cs:__imp_RegSetValueExW
0x180004a41  mov     ebx, r15d
0x180004a44  mov     rcx, [rsp+198h+hKey]; hKey
0x180004a49  mov     r14, [rsp+198h+var_18]
0x180004a51  mov     rdi, [rsp+198h+arg_18]
0x180004a59  mov     rsi, [rsp+198h+arg_10]
0x180004a61  mov     rbp, [rsp+198h+arg_8]
0x180004a69  test    rcx, rcx
0x180004a6c  jz      short loc_180004A74
0x180004a6e  call    cs:__imp_RegCloseKey
0x180004a74  mov     rcx, [rsp+198h+phkResult]; hKey
0x180004a79  test    rcx, rcx
0x180004a7c  jz      short loc_180004A84
0x180004a7e  call    cs:__imp_RegCloseKey
0x180004a84  mov     eax, ebx
0x180004a86  mov     rcx, [rsp+198h+var_28]
0x180004a8e  xor     rcx, rsp; StackCookie
0x180004a91  call    __security_check_cookie
0x180004a96  add     rsp, 188h
0x180004a9d  pop     r15
0x180004a9f  pop     rbx
0x180004aa0  retn
```
