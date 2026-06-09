# GetCustomProposalConfiguration

- ea: `0x180081764`
- end: `0x180081aa6`
- name: `GetCustomProposalConfiguration`
- size: `834`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180081078`

## callees

- `0x18001945c`
- `0x1800816c0`
- `0x180081764`
- `0x180081c38`
- `0x180081c8c`
- `0x18008c630`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800818bf`
- `msvcrt!_stricmp` at `0x1800818de`
- `msvcrt!_stricmp` at `0x1800818fd`
- `msvcrt!_stricmp` at `0x18008191c`
- `msvcrt!_stricmp` at `0x1800818bf`
- `msvcrt!_stricmp` at `0x1800818de`
- `msvcrt!_stricmp` at `0x1800818fd`
- `msvcrt!_stricmp` at `0x18008191c`
- `KERNEL32!LocalFree` at `0x180081a62`
- `KERNEL32!LocalFree` at `0x180081a62`
- `KERNEL32!LocalAlloc` at `0x180081806`
- `KERNEL32!LocalAlloc` at `0x180081806`
- `ADVAPI32!RegCloseKey` at `0x180081a1d`
- `ADVAPI32!RegCloseKey` at `0x180081a72`
- `ADVAPI32!RegCloseKey` at `0x180081a1d`
- `ADVAPI32!RegCloseKey` at `0x180081a72`
- `ADVAPI32!RegOpenKeyExA` at `0x18008186c`
- `ADVAPI32!RegOpenKeyExA` at `0x18008186c`
- `ADVAPI32!RegQueryValueExA` at `0x1800817e3`
- `ADVAPI32!RegQueryValueExA` at `0x1800818a5`
- `ADVAPI32!RegQueryValueExA` at `0x180081967`
- `ADVAPI32!RegQueryValueExA` at `0x1800819b1`
- `ADVAPI32!RegQueryValueExA` at `0x1800819fa`
- `ADVAPI32!RegQueryValueExA` at `0x1800817e3`
- `ADVAPI32!RegQueryValueExA` at `0x1800818a5`
- `ADVAPI32!RegQueryValueExA` at `0x180081967`
- `ADVAPI32!RegQueryValueExA` at `0x1800819b1`
- `ADVAPI32!RegQueryValueExA` at `0x1800819fa`

## string_xrefs

- `0x18008182f`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
_QWORD *__fastcall GetCustomProposalConfiguration(_DWORD *a1)
{
  _QWORD *i; // rdi
  HKEY CustomCofigurationKey; // r14
  unsigned int v4; // r15d
  __int64 *v5; // rdx
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  BYTE lpData[272]; // [rsp+40h] [rbp-C0h] BYREF
  char pszDest[272]; // [rsp+150h] [rbp+50h] BYREF

  i = 0;
  phkResult = 0;
  CustomCofigurationKey = (HKEY)GetCustomCofigurationKey();
  *a1 = 0;
  if ( CustomCofigurationKey )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( RegQueryValueExA(CustomCofigurationKey, "CustomProposalsCount", 0, 0, Data, &cbData) )
    {
LABEL_31:
      RegCloseKey(CustomCofigurationKey);
      return i;
    }
    if ( *(_DWORD *)Data )
    {
      v4 = 0;
      for ( i = LocalAlloc(0x40u, 32LL * *(unsigned int *)Data); v4 < *(_DWORD *)Data; ++v4 )
      {
        StringCbPrintfA(
          pszDest,
          0x104u,
          "%s\\%s\\%d",
          "System\\CurrentControlSet\\Services\\rasman\\IKEv2",
          "Proposals",
          v4);
        if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, &phkResult) )
        {
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "esp_encr", 0, 0, lpData, &cbData) )
          {
            if ( !_stricmp((const char *)lpData, "3DES") )
            {
              v5 = &qword_1800B5A68;
            }
            else if ( !_stricmp((const char *)lpData, "DES") )
            {
              v5 = &qword_1800B5AB8;
            }
            else if ( !_stricmp((const char *)lpData, "AES_128") )
            {
              v5 = &qword_1800B5A90;
            }
            else
            {
              v6 = _stricmp((const char *)lpData, "AES_256");
              v5 = &qword_1800B5AC0;
              if ( v6 )
                v5 = 0;
            }
            i[4 * (unsigned int)*a1 + 1] = v5;
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "esp_auth", 0, 0, lpData, &cbData) )
          {
            v7 = 4LL * (unsigned int)*a1;
            i[v7 + 2] = StringToAuthTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "AH", 0, 0, lpData, &cbData) )
          {
            v8 = 4LL * (unsigned int)*a1;
            i[v8] = StringToAuthTransform((char *)lpData);
          }
          cbData = 260;
          if ( !RegQueryValueExA(phkResult, "PFS", 0, 0, lpData, &cbData) )
          {
            v9 = 4LL * (unsigned int)*a1;
            LODWORD(i[v9 + 3]) = StringToPFSTransform((char *)lpData);
          }
          RegCloseKey(phkResult);
          v10 = 4LL * (unsigned int)*a1;
          if ( i[v10] || i[v10 + 1] || i[v10 + 2] )
            ++*a1;
        }
      }
    }
  }
  if ( !*a1 && i )
  {
    LocalFree(i);
    i = 0;
  }
  if ( CustomCofigurationKey )
    goto LABEL_31;
  return i;
}

```

## disassembly

```asm
0x180081764  mov     [rsp-8+arg_8], rbx
0x180081769  mov     [rsp-8+arg_10], rsi
0x18008176e  push    rbp
0x18008176f  push    rdi
0x180081770  push    r13
0x180081772  push    r14
0x180081774  push    r15
0x180081776  lea     rbp, [rsp-170h]
0x18008177e  sub     rsp, 270h
0x180081785  mov     rax, cs:__security_cookie
0x18008178c  xor     rax, rsp
0x18008178f  mov     [rbp+190h+var_30], rax
0x180081796  mov     rsi, rcx
0x180081799  xor     edi, edi
0x18008179b  call    GetCustomCofigurationKey
0x1800817a0  mov     [rsp+290h+phkResult], rdi
0x1800817a5  mov     r14, rax
0x1800817a8  mov     [rsi], edi
0x1800817aa  test    rax, rax
0x1800817ad  jz      loc_180081A55
0x1800817b3  lea     rax, [rsp+290h+cbData]
0x1800817b8  mov     dword ptr [rsp+290h+Data], edi
0x1800817bc  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800817c1  lea     rdx, aCustomproposal; "CustomProposalsCount"
0x1800817c8  lea     rax, [rsp+290h+Data]
0x1800817cd  mov     [rsp+290h+cbData], 4
0x1800817d5  xor     r9d, r9d; lpType
0x1800817d8  mov     [rsp+290h+lpData], rax; lpData
0x1800817dd  xor     r8d, r8d; lpReserved
0x1800817e0  mov     rcx, r14; hKey
0x1800817e3  call    cs:__imp_RegQueryValueExA
0x1800817e9  test    eax, eax
0x1800817eb  jnz     loc_180081A6F
0x1800817f1  mov     eax, dword ptr [rsp+290h+Data]
0x1800817f5  test    eax, eax
0x1800817f7  jz      loc_180081A55
0x1800817fd  mov     edx, eax
0x1800817ff  lea     ecx, [rdi+40h]; uFlags
0x180081802  shl     rdx, 5; uBytes
0x180081806  call    cs:__imp_LocalAlloc
0x18008180c  xor     r15d, r15d
0x18008180f  mov     rdi, rax
0x180081812  cmp     dword ptr [rsp+290h+Data], r15d
0x180081817  jbe     loc_180081A55
0x18008181d  mov     r13d, 104h
0x180081823  lea     rax, aProposals; "Proposals"
0x18008182a  mov     dword ptr [rsp+290h+lpcbData], r15d
0x18008182f  lea     r9, aSystemCurrentc_28; "System\\CurrentControlSet\\Services\\ra"...
0x180081836  mov     [rsp+290h+lpData], rax
0x18008183b  lea     r8, aSSD; "%s\\%s\\%d"
0x180081842  mov     rdx, r13; cbDest
0x180081845  lea     rcx, [rbp+190h+pszDest]; pszDest
0x180081849  call    StringCbPrintfA
0x18008184e  lea     rax, [rsp+290h+phkResult]
0x180081853  mov     r9d, 1; samDesired
0x180081859  xor     r8d, r8d; ulOptions
0x18008185c  mov     [rsp+290h+lpData], rax; phkResult
0x180081861  lea     rdx, [rbp+190h+pszDest]; lpSubKey
0x180081865  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008186c  call    cs:__imp_RegOpenKeyExA
0x180081872  test    eax, eax
0x180081874  jnz     loc_180081A47
0x18008187a  mov     rcx, [rsp+290h+phkResult]; hKey
0x18008187f  lea     rax, [rsp+290h+cbData]
0x180081884  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180081889  lea     rdx, aEspEncr; "esp_encr"
0x180081890  lea     rax, [rsp+290h+var_250]
0x180081895  mov     [rsp+290h+cbData], r13d
0x18008189a  xor     r9d, r9d; lpType
0x18008189d  mov     [rsp+290h+lpData], rax; lpData
0x1800818a2  xor     r8d, r8d; lpReserved
0x1800818a5  call    cs:__imp_RegQueryValueExA
0x1800818ab  test    eax, eax
0x1800818ad  jnz     loc_18008193C
0x1800818b3  lea     rdx, a3des; "3DES"
0x1800818ba  lea     rcx, [rsp+290h+var_250]; String1
0x1800818bf  call    cs:__imp__stricmp
0x1800818c5  test    eax, eax
0x1800818c7  jnz     short loc_1800818D2
0x1800818c9  lea     rdx, qword_1800B5A68
0x1800818d0  jmp     short loc_180081931
0x1800818d2  lea     rdx, aDes; "DES"
0x1800818d9  lea     rcx, [rsp+290h+var_250]; String1
0x1800818de  call    cs:__imp__stricmp
0x1800818e4  test    eax, eax
0x1800818e6  jnz     short loc_1800818F1
0x1800818e8  lea     rdx, qword_1800B5AB8
0x1800818ef  jmp     short loc_180081931
0x1800818f1  lea     rdx, aAes128; "AES_128"
0x1800818f8  lea     rcx, [rsp+290h+var_250]; String1
0x1800818fd  call    cs:__imp__stricmp
0x180081903  test    eax, eax
0x180081905  jnz     short loc_180081910
0x180081907  lea     rdx, qword_1800B5A90
0x18008190e  jmp     short loc_180081931
0x180081910  lea     rdx, aAes256; "AES_256"
0x180081917  lea     rcx, [rsp+290h+var_250]; String1
0x18008191c  call    cs:__imp__stricmp
0x180081922  xor     ecx, ecx
0x180081924  lea     rdx, qword_1800B5AC0
0x18008192b  test    eax, eax
0x18008192d  cmovnz  rdx, rcx
0x180081931  mov     eax, [rsi]
0x180081933  shl     rax, 5
0x180081937  mov     [rax+rdi+8], rdx
0x18008193c  mov     rcx, [rsp+290h+phkResult]; hKey
0x180081941  lea     rax, [rsp+290h+cbData]
0x180081946  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18008194b  lea     rdx, aEspAuth; "esp_auth"
0x180081952  lea     rax, [rsp+290h+var_250]
0x180081957  mov     [rsp+290h+cbData], r13d
0x18008195c  xor     r9d, r9d; lpType
0x18008195f  mov     [rsp+290h+lpData], rax; lpData
0x180081964  xor     r8d, r8d; lpReserved
0x180081967  call    cs:__imp_RegQueryValueExA
0x18008196d  test    eax, eax
0x18008196f  jnz     short loc_180081986
0x180081971  mov     ebx, [rsi]
0x180081973  lea     rcx, [rsp+290h+var_250]; String1
0x180081978  shl     rbx, 5
0x18008197c  call    StringToAuthTransform
0x180081981  mov     [rbx+rdi+10h], rax
0x180081986  mov     rcx, [rsp+290h+phkResult]; hKey
0x18008198b  lea     rax, [rsp+290h+cbData]
0x180081990  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180081995  lea     rdx, aAh; "AH"
0x18008199c  lea     rax, [rsp+290h+var_250]
0x1800819a1  mov     [rsp+290h+cbData], r13d
0x1800819a6  xor     r9d, r9d; lpType
0x1800819a9  mov     [rsp+290h+lpData], rax; lpData
0x1800819ae  xor     r8d, r8d; lpReserved
0x1800819b1  call    cs:__imp_RegQueryValueExA
0x1800819b7  test    eax, eax
0x1800819b9  jnz     short loc_1800819CF
0x1800819bb  mov     ebx, [rsi]
0x1800819bd  lea     rcx, [rsp+290h+var_250]; String1
0x1800819c2  shl     rbx, 5
0x1800819c6  call    StringToAuthTransform
0x1800819cb  mov     [rbx+rdi], rax
0x1800819cf  mov     rcx, [rsp+290h+phkResult]; hKey
0x1800819d4  lea     rax, [rsp+290h+cbData]
0x1800819d9  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800819de  lea     rdx, aPfs; "PFS"
0x1800819e5  lea     rax, [rsp+290h+var_250]
0x1800819ea  mov     [rsp+290h+cbData], r13d
0x1800819ef  xor     r9d, r9d; lpType
0x1800819f2  mov     [rsp+290h+lpData], rax; lpData
0x1800819f7  xor     r8d, r8d; lpReserved
0x1800819fa  call    cs:__imp_RegQueryValueExA
0x180081a00  test    eax, eax
0x180081a02  jnz     short loc_180081A18
0x180081a04  mov     ebx, [rsi]
0x180081a06  lea     rcx, [rsp+290h+var_250]; String1
0x180081a0b  shl     rbx, 5
0x180081a0f  call    StringToPFSTransform
0x180081a14  mov     [rbx+rdi+18h], eax
0x180081a18  mov     rcx, [rsp+290h+phkResult]; hKey
0x180081a1d  call    cs:__imp_RegCloseKey
0x180081a23  mov     ecx, [rsi]
0x180081a25  mov     eax, ecx
0x180081a27  shl     rax, 5
0x180081a2b  cmp     qword ptr [rax+rdi], 0
0x180081a30  jnz     short loc_180081A42
0x180081a32  cmp     qword ptr [rax+rdi+8], 0
0x180081a38  jnz     short loc_180081A42
0x180081a3a  cmp     qword ptr [rax+rdi+10h], 0
0x180081a40  jz      short loc_180081A47
0x180081a42  lea     eax, [rcx+1]
0x180081a45  mov     [rsi], eax
0x180081a47  inc     r15d
0x180081a4a  cmp     r15d, dword ptr [rsp+290h+Data]
0x180081a4f  jb      loc_180081823
0x180081a55  cmp     dword ptr [rsi], 0
0x180081a58  jnz     short loc_180081A6A
0x180081a5a  test    rdi, rdi
0x180081a5d  jz      short loc_180081A6A
0x180081a5f  mov     rcx, rdi; hMem
0x180081a62  call    cs:__imp_LocalFree
0x180081a68  xor     edi, edi
0x180081a6a  test    r14, r14
0x180081a6d  jz      short loc_180081A78
0x180081a6f  mov     rcx, r14; hKey
0x180081a72  call    cs:__imp_RegCloseKey
0x180081a78  mov     rax, rdi
0x180081a7b  mov     rcx, [rbp+190h+var_30]
0x180081a82  xor     rcx, rsp; StackCookie
0x180081a85  call    __security_check_cookie
0x180081a8a  lea     r11, [rsp+290h+var_20]
0x180081a92  mov     rbx, [r11+38h]
0x180081a96  mov     rsi, [r11+40h]
0x180081a9a  mov     rsp, r11
0x180081a9d  pop     r15
0x180081a9f  pop     r14
0x180081aa1  pop     r13
0x180081aa3  pop     rdi
0x180081aa4  pop     rbp
0x180081aa5  retn
```
