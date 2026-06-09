# Dhcpv6ReadSavedConfigurations

- ea: `0x180006468`
- end: `0x180006784`
- name: `Dhcpv6ReadSavedConfigurations`
- size: `796`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800062e8`
- `0x180010340`
- `0x180010d18`

## callees

- `0x180006468`
- `0x180007564`
- `0x1800078c0`
- `0x18000c740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18003098c`
- `0x180033900`
- `0x180033de4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000663b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000663b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800064ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800064ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000659c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000659c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800065cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006601`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006601`

## pseudocode

```c
__int64 __fastcall Dhcpv6ReadSavedConfigurations(HKEY hKey, _QWORD *a2, DWORD *a3)
{
  __int64 v5; // rax
  unsigned int Configs; // ebx
  char *v9; // r14
  DWORD i; // edi
  char *v11; // r15
  DWORD j; // esi
  __int64 v13; // rcx
  void *v14; // rax
  __int64 v15; // rdx
  LPVOID *v16; // rcx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[104]; // [rsp+70h] [rbp-90h] BYREF

  *a2 = 0;
  v5 = *a3;
  cSubKeys = 0;
  cchName = 0;
  phkResult = 0;
  if ( (_DWORD)v5 )
  {
    cSubKeys = v5;
    v9 = (char *)DhcpAlloc(24 * v5);
    if ( v9 )
    {
      Configs = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= cSubKeys )
        {
          *a2 = v9;
          return Configs;
        }
        cchName = 100;
        memset_0(Name, 0, 0xC8u);
        Configs = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( Configs )
          break;
        Configs = RegOpenKeyExW(hKey, Name, 0, 0x2001Bu, &phkResult);
        if ( Configs )
        {
          if ( (xmmword_1800423E0 & 0x10) == 0 )
            goto LABEL_11;
          v15 = 81;
          goto LABEL_29;
        }
        v11 = &v9[24 * i];
        Configs = ReadConfigs(phkResult);
        RegCloseKey(phkResult);
        if ( Configs )
        {
          if ( (xmmword_1800423E0 & 0x10) == 0 )
            goto LABEL_11;
          v15 = 82;
LABEL_29:
          WPP_SF_(1028, v15, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
          goto LABEL_11;
        }
        v13 = 2 * cchName + 2LL;
        cchName *= 2;
        v14 = (void *)DhcpAlloc(v13);
        *(_QWORD *)v11 = v14;
        if ( !v14 )
        {
          Configs = 8;
          if ( (xmmword_1800423E0 & 0x10) == 0 )
            goto LABEL_11;
          v15 = 83;
          goto LABEL_29;
        }
        memcpy_0(v14, Name, cchName);
        *(_WORD *)(*(_QWORD *)v11 + 2 * ((unsigned __int64)cchName >> 1)) = 0;
      }
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_d(1028, 80, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, i);
LABEL_11:
      for ( j = 0; j < i; ++j )
      {
        v16 = (LPVOID *)&v9[24 * j];
        if ( *v16 )
          DhcpFree(v16);
      }
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v9);
    }
    else
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 79, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      return 8;
    }
  }
  else
  {
    Configs = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !Configs )
    {
      *a3 = cSubKeys;
      return 0;
    }
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 78, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
  }
  return Configs;
}

```

## disassembly

```asm
0x180006468  mov     [rsp-8+arg_18], rbx
0x18000646d  push    rbp
0x18000646e  push    rsi
0x18000646f  push    rdi
0x180006470  push    r12
0x180006472  push    r13
0x180006474  push    r14
0x180006476  push    r15
0x180006478  lea     rbp, [rsp-50h]
0x18000647d  sub     rsp, 150h
0x180006484  mov     rax, cs:__security_cookie
0x18000648b  xor     rax, rsp
0x18000648e  mov     [rbp+80h+var_40], rax
0x180006492  xor     r13d, r13d
0x180006495  mov     rdi, r8
0x180006498  mov     [rdx], r13
0x18000649b  mov     r12, rdx
0x18000649e  mov     eax, [r8]
0x1800064a1  mov     rsi, rcx
0x1800064a4  mov     [rsp+180h+cSubKeys], r13d
0x1800064a9  mov     [rsp+180h+cchName], r13d
0x1800064ae  mov     [rsp+180h+phkResult], r13
0x1800064b3  test    eax, eax
0x1800064b5  jnz     short loc_180006532
0x1800064b7  mov     [rsp+180h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800064bc  lea     rax, [rsp+180h+cSubKeys]
0x1800064c1  mov     [rsp+180h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800064c6  xor     r9d, r9d; lpReserved
0x1800064c9  mov     [rsp+180h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800064ce  xor     r8d, r8d; lpcchClass
0x1800064d1  mov     [rsp+180h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800064d6  xor     edx, edx; lpClass
0x1800064d8  mov     [rsp+180h+lpcValues], r13; lpcValues
0x1800064dd  mov     [rsp+180h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800064e2  mov     [rsp+180h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800064e7  mov     [rsp+180h+lpcSubKeys], rax; lpcSubKeys
0x1800064ec  call    cs:__imp_RegQueryInfoKeyW
0x1800064f3  nop     dword ptr [rax+rax+00h]
0x1800064f8  mov     ebx, eax
0x1800064fa  test    eax, eax
0x1800064fc  jnz     loc_1800066F7
0x180006502  mov     eax, [rsp+180h+cSubKeys]
0x180006506  mov     [rdi], eax
0x180006508  xor     eax, eax
0x18000650a  mov     rcx, [rbp+80h+var_40]
0x18000650e  xor     rcx, rsp; StackCookie
0x180006511  call    __security_check_cookie
0x180006516  mov     rbx, [rsp+180h+arg_18]
0x18000651e  add     rsp, 150h
0x180006525  pop     r15
0x180006527  pop     r14
0x180006529  pop     r13
0x18000652b  pop     r12
0x18000652d  pop     rdi
0x18000652e  pop     rsi
0x18000652f  pop     rbp
0x180006530  retn
0x180006532  lea     rcx, [rax+rax*2]
0x180006536  mov     [rsp+180h+cSubKeys], eax
0x18000653a  shl     rcx, 3
0x18000653e  call    DhcpAlloc
0x180006543  mov     r14, rax
0x180006546  test    rax, rax
0x180006549  jz      loc_180006692
0x18000654f  mov     ebx, r13d
0x180006552  mov     edi, r13d
0x180006555  cmp     edi, [rsp+180h+cSubKeys]
0x180006559  jnb     loc_1800066A2
0x18000655f  xor     edx, edx; Val
0x180006561  mov     [rsp+180h+cchName], 64h ; 'd'
0x180006569  mov     r8d, 0C8h; Size
0x18000656f  lea     rcx, [rsp+180h+Name]; void *
0x180006574  call    memset_0
0x180006579  mov     [rsp+180h+lpcValues], r13; lpftLastWriteTime
0x18000657e  lea     r9, [rsp+180h+cchName]; lpcchName
0x180006583  mov     [rsp+180h+lpcbMaxClassLen], r13; lpcchClass
0x180006588  lea     r8, [rsp+180h+Name]; lpName
0x18000658d  mov     [rsp+180h+lpcbMaxSubKeyLen], r13; lpClass
0x180006592  mov     edx, edi; dwIndex
0x180006594  mov     rcx, rsi; hKey
0x180006597  mov     [rsp+180h+lpcSubKeys], r13; lpReserved
0x18000659c  call    cs:__imp_RegEnumKeyExW
0x1800065a3  nop     dword ptr [rax+rax+00h]
0x1800065a8  mov     ebx, eax
0x1800065aa  test    eax, eax
0x1800065ac  jnz     loc_1800066CC
0x1800065b2  lea     rax, [rsp+180h+phkResult]
0x1800065b7  mov     r9d, 2001Bh; samDesired
0x1800065bd  xor     r8d, r8d; ulOptions
0x1800065c0  mov     [rsp+180h+lpcSubKeys], rax; phkResult
0x1800065c5  lea     rdx, [rsp+180h+Name]; lpSubKey
0x1800065ca  mov     rcx, rsi; hKey
0x1800065cd  call    cs:__imp_RegOpenKeyExW
0x1800065d4  nop     dword ptr [rax+rax+00h]
0x1800065d9  mov     ebx, eax
0x1800065db  test    eax, eax
0x1800065dd  jnz     loc_1800066B5
0x1800065e3  mov     eax, edi
0x1800065e5  lea     rcx, [rax+rax*2]
0x1800065e9  lea     r15, [r14+rcx*8]
0x1800065ed  mov     rcx, [rsp+180h+phkResult]; hKey
0x1800065f2  mov     rdx, r15
0x1800065f5  call    ReadConfigs
0x1800065fa  mov     rcx, [rsp+180h+phkResult]; hKey
0x1800065ff  mov     ebx, eax
0x180006601  call    cs:__imp_RegCloseKey
0x180006608  nop     dword ptr [rax+rax+00h]
0x18000660d  test    ebx, ebx
0x18000660f  jz      short loc_180006649
0x180006611  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006618  jnz     loc_18000674A
0x18000661e  mov     esi, r13d
0x180006621  test    edi, edi
0x180006623  jnz     loc_180006765
0x180006629  mov     rcx, gs:60h
0x180006632  mov     r8, r14; lpMem
0x180006635  xor     edx, edx; dwFlags
0x180006637  mov     rcx, [rcx+30h]; hHeap
0x18000663b  call    cs:__imp_HeapFree
0x180006642  nop     dword ptr [rax+rax+00h]
0x180006647  jmp     short loc_1800066AE
0x180006649  mov     eax, [rsp+180h+cchName]
0x18000664d  add     eax, eax
0x18000664f  mov     ecx, eax
0x180006651  add     rcx, 2
0x180006655  mov     [rsp+180h+cchName], eax
0x180006659  call    DhcpAlloc
0x18000665e  mov     [r15], rax
0x180006661  test    rax, rax
0x180006664  jz      loc_180006733
0x18000666a  mov     r8d, [rsp+180h+cchName]; Size
0x18000666f  lea     rdx, [rsp+180h+Name]; Src
0x180006674  mov     rcx, rax; void *
0x180006677  call    memcpy_0
0x18000667c  mov     edx, [rsp+180h+cchName]
0x180006680  mov     rcx, [r15]
0x180006683  shr     rdx, 1
0x180006686  inc     edi
0x180006688  mov     [rcx+rdx*2], r13w
0x18000668d  jmp     loc_180006555
0x180006692  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006699  jnz     short loc_180006718
0x18000669b  mov     ebx, 8
0x1800066a0  jmp     short loc_1800066AE
0x1800066a2  mov     [r12], r14
0x1800066a6  test    ebx, ebx
0x1800066a8  jnz     loc_18000661E
0x1800066ae  mov     eax, ebx
0x1800066b0  jmp     loc_18000650A
0x1800066b5  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800066bc  jz      loc_18000661E
0x1800066c2  mov     edx, 51h ; 'Q'
0x1800066c7  jmp     loc_18000674F
0x1800066cc  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800066d3  jz      loc_18000661E
0x1800066d9  mov     edx, 50h ; 'P'
0x1800066de  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x1800066e5  mov     ecx, 404h
0x1800066ea  mov     r9d, edi
0x1800066ed  call    WPP_SF_d
0x1800066f2  jmp     loc_18000661E
0x1800066f7  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800066fe  jz      short loc_1800066AE
0x180006700  mov     edx, 4Eh ; 'N'
0x180006705  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000670c  mov     ecx, 404h
0x180006711  call    WPP_SF_
0x180006716  jmp     short loc_1800066AE
0x180006718  mov     edx, 4Fh ; 'O'
0x18000671d  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180006724  mov     ecx, 404h
0x180006729  call    WPP_SF_
0x18000672e  jmp     loc_18000669B
0x180006733  mov     ebx, 8
0x180006738  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000673f  jz      loc_18000661E
0x180006745  lea     edx, [rbx+4Bh]
0x180006748  jmp     short loc_18000674F
0x18000674a  mov     edx, 52h ; 'R'
0x18000674f  mov     ecx, 404h
0x180006754  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000675b  call    WPP_SF_
0x180006760  jmp     loc_18000661E
0x180006765  mov     eax, esi
0x180006767  lea     rcx, [rax+rax*2]
0x18000676b  lea     rcx, [r14+rcx*8]
0x18000676f  cmp     [rcx], r13
0x180006772  jz      short loc_180006779
0x180006774  call    DhcpFree
0x180006779  inc     esi
0x18000677b  cmp     esi, edi
0x18000677d  jb      short loc_180006765
0x18000677f  jmp     loc_180006629
```
