# hijackTestGetNames

- ea: `0x180033754`
- end: `0x180033949`
- name: `hijackTestGetNames`
- size: `501`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, STRSAFE_LPWSTR)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18003064c`

## callees

- `0x1800088f0`
- `0x180008b00`
- `0x18002039c`
- `0x180033754`
- `0x180046ec0`
- `0x180047818`
- `0x180086384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033916`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003388d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003388d`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180033819`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180033819`

## string_xrefs

- `0x1800337d6`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x1800337dd`: `Dnscache`

## pseudocode

```c
__int64 __fastcall hijackTestGetNames(STRSAFE_LPWSTR pszDest, STRSAFE_LPWSTR a2)
{
  unsigned int v4; // ebx
  int PersistedRegistryLocation; // eax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  const wchar_t *v9; // r10
  unsigned int v10; // r11d
  int v11; // r11d
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[528]; // [rsp+150h] [rbp+50h] BYREF

  cbData = 258;
  Type = 0;
  if ( !pszDest || !a2 )
    return 0;
  v4 = 0;
  memset_0(v17, 0, 0x20Au);
  hKey = 0;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                L"Dnscache",
                                L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                L"Parameters",
                                v17,
                                522);
  if ( PersistedRegistryLocation >= 0 )
    v6 = RegOpenKeyExInternalW(-2147483646, v17, 0, 131097, &hKey, 0);
  else
    v6 = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v17, v6);
  }
  else
  {
    memset_0(Data, 0, 0x102u);
    if ( !RegQueryValueExW(hKey, L"HijackingProbeNames", 0, &Type, Data, &cbData) && Type == 7 )
    {
      v7 = -1;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&Data[2 * v8] );
      if ( (unsigned __int64)(v8 - 1) <= 0x3E )
      {
        do
          ++v7;
        while ( *(_WORD *)&Data[2 * v8 + 2 + 2 * v7] );
        if ( (unsigned __int64)(v7 - 1) <= 0x3E
          && StringCchCopyW(pszDest, 0x40u, (STRSAFE_LPCWSTR)Data) >= 0
          && StringCchCopyW(a2, v10, v9) >= 0 )
        {
          v4 = v11 - 63;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180033754  mov     [rsp-8+arg_10], rbx
0x180033759  mov     [rsp-8+arg_18], rsi
0x18003375e  push    rbp
0x18003375f  push    rdi
0x180033760  push    r15
0x180033762  lea     rbp, [rsp-270h]
0x18003376a  sub     rsp, 370h
0x180033771  mov     rax, cs:__security_cookie
0x180033778  xor     rax, rsp
0x18003377b  mov     [rbp+280h+var_20], rax
0x180033782  xor     r15d, r15d
0x180033785  mov     [rsp+380h+cbData], 102h
0x18003378d  mov     [rsp+380h+Type], r15d
0x180033792  mov     rdi, rdx
0x180033795  mov     rsi, rcx
0x180033798  test    rcx, rcx
0x18003379b  jz      loc_180033920
0x1800337a1  test    rdx, rdx
0x1800337a4  jz      loc_180033920
0x1800337aa  xor     edx, edx; Val
0x1800337ac  lea     rcx, [rbp+280h+var_230]; void *
0x1800337b0  mov     r8d, 20Ah; Size
0x1800337b6  mov     ebx, r15d
0x1800337b9  call    memset_0
0x1800337be  lea     r9, [rbp+280h+var_230]
0x1800337c2  mov     [rsp+380h+hKey], r15
0x1800337c7  lea     r8, aParameters; "Parameters"
0x1800337ce  mov     dword ptr [rsp+380h+lpData], 20Ah
0x1800337d6  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800337dd  lea     rcx, aDnscache_0; "Dnscache"
0x1800337e4  call    WxGetPersistedRegistryLocation
0x1800337e9  test    eax, eax
0x1800337eb  jns     short loc_1800337F6
0x1800337ed  mov     ecx, eax
0x1800337ef  call    WX_WIN32_FROM_HR
0x1800337f4  jmp     short loc_18003381F
0x1800337f6  lea     rax, [rsp+380h+hKey]
0x1800337fb  mov     [rsp+380h+lpcbData], r15
0x180033800  mov     r9d, 20019h
0x180033806  mov     [rsp+380h+lpData], rax
0x18003380b  xor     r8d, r8d
0x18003380e  lea     rdx, [rbp+280h+var_230]
0x180033812  mov     rcx, 0FFFFFFFF80000002h
0x180033819  call    cs:__imp_RegOpenKeyExInternalW
0x18003381f  test    eax, eax
0x180033821  jz      short loc_180033853
0x180033823  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003382a  jz      loc_18003390C
0x180033830  mov     edx, 0Ah
0x180033835  mov     dword ptr [rsp+380h+lpData], eax
0x180033839  mov     ecx, 40Bh
0x18003383e  lea     r9, [rbp+280h+var_230]
0x180033842  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180033849  call    WPP_SF_SD
0x18003384e  jmp     loc_18003390C
0x180033853  xor     edx, edx; Val
0x180033855  lea     rcx, [rsp+380h+Data]; void *
0x18003385a  mov     r8d, 102h; Size
0x180033860  call    memset_0
0x180033865  mov     rcx, [rsp+380h+hKey]; hKey
0x18003386a  lea     rax, [rsp+380h+cbData]
0x18003386f  mov     [rsp+380h+lpcbData], rax; lpcbData
0x180033874  lea     r9, [rsp+380h+Type]; lpType
0x180033879  lea     rax, [rsp+380h+Data]
0x18003387e  xor     r8d, r8d; lpReserved
0x180033881  lea     rdx, aHijackingprobe; "HijackingProbeNames"
0x180033888  mov     [rsp+380h+lpData], rax; lpData
0x18003388d  call    cs:__imp_RegQueryValueExW
0x180033893  test    eax, eax
0x180033895  jnz     short loc_18003390C
0x180033897  cmp     [rsp+380h+Type], 7
0x18003389c  jnz     short loc_18003390C
0x18003389e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800338a2  lea     rax, [rsp+380h+Data]
0x1800338a7  mov     rcx, rdx
0x1800338aa  inc     rcx
0x1800338ad  cmp     [rax+rcx*2], r15w
0x1800338b2  jnz     short loc_1800338AA
0x1800338b4  lea     rax, [rcx-1]
0x1800338b8  cmp     rax, 3Eh ; '>'
0x1800338bc  ja      short loc_18003390C
0x1800338be  lea     r10, [rsp+380h+var_33E]
0x1800338c3  lea     r10, [r10+rcx*2]
0x1800338c7  inc     rdx
0x1800338ca  cmp     [r10+rdx*2], r15w
0x1800338cf  jnz     short loc_1800338C7
0x1800338d1  lea     rax, [rdx-1]
0x1800338d5  cmp     rax, 3Eh ; '>'
0x1800338d9  ja      short loc_18003390C
0x1800338db  mov     r11d, 40h ; '@'
0x1800338e1  lea     r8, [rsp+380h+Data]; pszSrc
0x1800338e6  mov     edx, r11d; cchDest
0x1800338e9  mov     rcx, rsi; pszDest
0x1800338ec  call    StringCchCopyW
0x1800338f1  test    eax, eax
0x1800338f3  js      short loc_18003390C
0x1800338f5  mov     r8, r10; pszSrc
0x1800338f8  mov     edx, r11d; cchDest
0x1800338fb  mov     rcx, rdi; pszDest
0x1800338fe  call    StringCchCopyW
0x180033903  test    eax, eax
0x180033905  lea     ecx, [r11-3Fh]
0x180033909  cmovns  ebx, ecx
0x18003390c  mov     rcx, [rsp+380h+hKey]; hKey
0x180033911  test    rcx, rcx
0x180033914  jz      short loc_18003391C
0x180033916  call    cs:__imp_RegCloseKey
0x18003391c  mov     eax, ebx
0x18003391e  jmp     short loc_180033922
0x180033920  xor     eax, eax
0x180033922  mov     rcx, [rbp+280h+var_20]
0x180033929  xor     rcx, rsp; StackCookie
0x18003392c  call    __security_check_cookie
0x180033931  lea     r11, [rsp+380h+var_10]
0x180033939  mov     rbx, [r11+30h]
0x18003393d  mov     rsi, [r11+38h]
0x180033941  mov     rsp, r11
0x180033944  pop     r15
0x180033946  pop     rdi
0x180033947  pop     rbp
0x180033948  retn
```
