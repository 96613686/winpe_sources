# FindAppRegKey(ushort const *,uint)

- ea: `0x1802d8694`
- end: `0x1802d893b`
- name: `?FindAppRegKey@@YA_NPEBGI@Z`
- size: `679`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802d84d8`

## callees

- `0x1801b0294`
- `0x18025b100`
- `0x1802d8544`
- `0x1802d8694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802d8760`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802d8760`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802d86f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802d87c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802d86f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802d87c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802d882f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802d8879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802d8901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802d882f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802d8879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1802d8901`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802d8743`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1802d8743`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802d880c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802d886c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802d880c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1802d886c`

## pseudocode

```c
bool __fastcall FindAppRegKey(const unsigned __int16 *a1, int a2)
{
  unsigned int v3; // esi
  int v4; // edi
  unsigned __int64 v5; // r15
  DWORD v6; // r14d
  DWORD v7; // r12d
  LSTATUS v8; // ebx
  int v9; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v18; // [rsp+68h] [rbp-98h]
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  BYTE v21[528]; // [rsp+490h] [rbp+390h] BYREF

  v18 = a1;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Direct3D", 0, 0x20019u, &hKey) )
    return 0;
  v3 = 261;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  while ( v4 != 1 )
  {
    cchName = 261;
    if ( RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, 0) )
      break;
    ++v6;
    if ( (unsigned int)_o__wcsicmp(Name, L"MostRecentApplication") )
    {
      if ( StringCchPrintfW(SubKey, 0x105u, L"%s\\%s", L"Software\\Microsoft\\Direct3D", Name) < 0 )
        return 0;
      v7 = cchName;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &phkResult) )
      {
        Type = 0;
        *(_DWORD *)Data = 0;
        cbData = 4;
        if ( RegQueryValueExW(phkResult, L"Size", 0, &Type, Data, &cbData)
          || Type != 4
          || !*(_DWORD *)Data
          || *(_DWORD *)Data == a2 )
        {
          cbData = 522;
          v8 = RegQueryValueExW(phkResult, L"Name", 0, &Type, v21, &cbData);
          RegCloseKey(phkResult);
          if ( !v8 && Type == 1 )
          {
            v16 = 0;
            v9 = EvaluatePathCandidate(v21, v18, &v16);
            if ( v9 == 1 )
              goto LABEL_23;
            if ( v9 == 2 )
            {
              if ( v4 != 2 )
                goto LABEL_23;
            }
            else if ( v9 == 3 && v4 != 2 && (v4 != 3 || v16 > v5) )
            {
LABEL_23:
              v5 = v16;
              v3 = v7 + 29;
              v4 = v9;
            }
          }
        }
        else
        {
          RegCloseKey(phkResult);
        }
      }
    }
  }
  RegCloseKey(hKey);
  if ( v4 )
    return v3 <= 0x105;
  return 0;
}

```

## disassembly

```asm
0x1802d8694  push    rbp
0x1802d8696  push    rbx
0x1802d8697  push    rsi
0x1802d8698  push    rdi
0x1802d8699  push    r12
0x1802d869b  push    r13
0x1802d869d  push    r14
0x1802d869f  push    r15
0x1802d86a1  lea     rbp, [rsp-5B8h]
0x1802d86a9  sub     rsp, 6B8h
0x1802d86b0  mov     rax, cs:__security_cookie
0x1802d86b7  xor     rax, rsp
0x1802d86ba  mov     [rbp+5F0h+var_50], rax
0x1802d86c1  mov     r13d, edx
0x1802d86c4  mov     [rsp+6F0h+var_688], rcx
0x1802d86c9  lea     rax, [rsp+6F0h+hKey]
0x1802d86ce  xor     ebx, ebx
0x1802d86d0  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Direct3D"
0x1802d86d7  mov     [rsp+6F0h+hKey], rbx
0x1802d86dc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1802d86e3  mov     [rsp+6F0h+phkResult], rax; phkResult
0x1802d86e8  mov     r9d, 20019h; samDesired
0x1802d86ee  xor     r8d, r8d; ulOptions
0x1802d86f1  call    cs:__imp_RegOpenKeyExW
0x1802d86f7  test    eax, eax
0x1802d86f9  jnz     loc_1802D8916
0x1802d86ff  mov     esi, 105h
0x1802d8704  mov     edi, ebx
0x1802d8706  mov     r15d, ebx
0x1802d8709  mov     r14d, ebx
0x1802d870c  cmp     edi, 1
0x1802d870f  jz      loc_1802D88FC
0x1802d8715  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1802d871a  lea     r9, [rsp+6F0h+cchName]; lpcchName
0x1802d871f  mov     [rsp+6F0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1802d8724  lea     r8, [rsp+6F0h+Name]; lpName
0x1802d8729  mov     [rsp+6F0h+lpcchClass], rbx; lpcchClass
0x1802d872e  mov     edx, r14d; dwIndex
0x1802d8731  mov     [rsp+6F0h+lpClass], rbx; lpClass
0x1802d8736  mov     [rsp+6F0h+phkResult], rbx; lpReserved
0x1802d873b  mov     [rsp+6F0h+cchName], 105h
0x1802d8743  call    cs:__imp_RegEnumKeyExW
0x1802d8749  test    eax, eax
0x1802d874b  jnz     loc_1802D88FC
0x1802d8751  lea     rdx, aMostrecentappl; "MostRecentApplication"
0x1802d8758  inc     r14d
0x1802d875b  lea     rcx, [rsp+6F0h+Name]
0x1802d8760  call    cs:__imp__o__wcsicmp
0x1802d8766  test    eax, eax
0x1802d8768  jz      short loc_1802D870C
0x1802d876a  lea     rax, [rsp+6F0h+Name]
0x1802d876f  mov     edx, 105h; unsigned __int64
0x1802d8774  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\Direct3D"
0x1802d877b  mov     [rsp+6F0h+phkResult], rax
0x1802d8780  lea     r8, aSS; "%s\\%s"
0x1802d8787  lea     rcx, [rbp+5F0h+SubKey]; unsigned __int16 *
0x1802d878e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1802d8793  test    eax, eax
0x1802d8795  js      loc_1802D8916
0x1802d879b  mov     r12d, [rsp+6F0h+cchName]
0x1802d87a0  lea     rax, [rsp+6F0h+var_6A0]
0x1802d87a5  mov     r9d, 20019h; samDesired
0x1802d87ab  mov     [rsp+6F0h+phkResult], rax; phkResult
0x1802d87b0  xor     r8d, r8d; ulOptions
0x1802d87b3  mov     [rsp+6F0h+var_6A0], rbx
0x1802d87b8  lea     rdx, [rbp+5F0h+SubKey]; lpSubKey
0x1802d87bf  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1802d87c6  call    cs:__imp_RegOpenKeyExW
0x1802d87cc  test    eax, eax
0x1802d87ce  jnz     loc_1802D870C
0x1802d87d4  mov     rcx, [rsp+6F0h+var_6A0]; hKey
0x1802d87d9  lea     rax, [rsp+6F0h+cbData]
0x1802d87de  mov     [rsp+6F0h+lpClass], rax; lpcbData
0x1802d87e3  lea     r9, [rsp+6F0h+Type]; lpType
0x1802d87e8  lea     rax, [rsp+6F0h+Data]
0x1802d87ed  mov     [rsp+6F0h+Type], ebx
0x1802d87f1  xor     r8d, r8d; lpReserved
0x1802d87f4  mov     [rsp+6F0h+phkResult], rax; lpData
0x1802d87f9  lea     rdx, aSize; "Size"
0x1802d8800  mov     dword ptr [rsp+6F0h+Data], ebx
0x1802d8804  mov     [rsp+6F0h+cbData], 4
0x1802d880c  call    cs:__imp_RegQueryValueExW
0x1802d8812  test    eax, eax
0x1802d8814  jnz     short loc_1802D883A
0x1802d8816  cmp     [rsp+6F0h+Type], 4
0x1802d881b  jnz     short loc_1802D883A
0x1802d881d  mov     eax, dword ptr [rsp+6F0h+Data]
0x1802d8821  test    eax, eax
0x1802d8823  jz      short loc_1802D883A
0x1802d8825  cmp     eax, r13d
0x1802d8828  jz      short loc_1802D883A
0x1802d882a  mov     rcx, [rsp+6F0h+var_6A0]; hKey
0x1802d882f  call    cs:__imp_RegCloseKey
0x1802d8835  jmp     loc_1802D870C
0x1802d883a  mov     rcx, [rsp+6F0h+var_6A0]; hKey
0x1802d883f  lea     rax, [rsp+6F0h+cbData]
0x1802d8844  mov     [rsp+6F0h+lpClass], rax; lpcbData
0x1802d8849  lea     r9, [rsp+6F0h+Type]; lpType
0x1802d884e  lea     rax, [rbp+5F0h+var_260]
0x1802d8855  mov     [rsp+6F0h+cbData], 20Ah
0x1802d885d  xor     r8d, r8d; lpReserved
0x1802d8860  mov     [rsp+6F0h+phkResult], rax; lpData
0x1802d8865  lea     rdx, aName; "Name"
0x1802d886c  call    cs:__imp_RegQueryValueExW
0x1802d8872  mov     rcx, [rsp+6F0h+var_6A0]; hKey
0x1802d8877  mov     ebx, eax
0x1802d8879  call    cs:__imp_RegCloseKey
0x1802d887f  test    ebx, ebx
0x1802d8881  mov     ebx, 0
0x1802d8886  jnz     loc_1802D870C
0x1802d888c  cmp     [rsp+6F0h+Type], 1
0x1802d8891  jnz     loc_1802D870C
0x1802d8897  mov     rdx, [rsp+6F0h+var_688]
0x1802d889c  lea     r8, [rsp+6F0h+var_698]
0x1802d88a1  lea     rcx, [rbp+5F0h+var_260]
0x1802d88a8  mov     [rsp+6F0h+var_698], rbx
0x1802d88ad  call    ?EvaluatePathCandidate@@YA?AW4PATH_CANDIDATE_EVALUATION@@PEBG0PEA_K@Z; EvaluatePathCandidate(ushort const *,ushort const *,unsigned __int64 *)
0x1802d88b2  mov     edx, eax
0x1802d88b4  sub     edx, 1
0x1802d88b7  jz      short loc_1802D88EB
0x1802d88b9  sub     edx, 1
0x1802d88bc  jz      short loc_1802D88E2
0x1802d88be  cmp     edx, 1
0x1802d88c1  jnz     loc_1802D870C
0x1802d88c7  cmp     edi, 2
0x1802d88ca  jz      loc_1802D870C
0x1802d88d0  cmp     edi, 3
0x1802d88d3  jnz     short loc_1802D88EB
0x1802d88d5  cmp     [rsp+6F0h+var_698], r15
0x1802d88da  jbe     loc_1802D870C
0x1802d88e0  jmp     short loc_1802D88EB
0x1802d88e2  cmp     edi, 2
0x1802d88e5  jz      loc_1802D870C
0x1802d88eb  mov     r15, [rsp+6F0h+var_698]
0x1802d88f0  lea     esi, [r12+1Dh]
0x1802d88f5  mov     edi, eax
0x1802d88f7  jmp     loc_1802D870C
0x1802d88fc  mov     rcx, [rsp+6F0h+hKey]; hKey
0x1802d8901  call    cs:__imp_RegCloseKey
0x1802d8907  test    edi, edi
0x1802d8909  jz      short loc_1802D8916
0x1802d890b  cmp     esi, 105h
0x1802d8911  setbe   al
0x1802d8914  jmp     short loc_1802D8918
0x1802d8916  xor     al, al
0x1802d8918  mov     rcx, [rbp+5F0h+var_50]
0x1802d891f  xor     rcx, rsp; StackCookie
0x1802d8922  call    __security_check_cookie
0x1802d8927  add     rsp, 6B8h
0x1802d892e  pop     r15
0x1802d8930  pop     r14
0x1802d8932  pop     r13
0x1802d8934  pop     r12
0x1802d8936  pop     rdi
0x1802d8937  pop     rsi
0x1802d8938  pop     rbx
0x1802d8939  pop     rbp
0x1802d893a  retn
```
