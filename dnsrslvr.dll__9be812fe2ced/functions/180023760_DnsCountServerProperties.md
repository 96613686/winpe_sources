# DnsCountServerProperties

- ea: `0x180023760`
- end: `0x180023a48`
- name: `DnsCountServerProperties`
- size: `744`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180023380`

## callees

- `0x180023760`
- `0x180046ec0`
- `0x180086384`
- `0x180086b1c`
- `0x1800876a4`
- `0x18008841c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180023887`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180023887`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800238f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800239f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023a38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800238f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800239f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023a38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800239ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800238bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800239ae`

## pseudocode

```c
__int64 __fastcall DnsCountServerProperties(HKEY hKey, HKEY a2, __int64 lpSubKey, int *a4)
{
  LPCWSTR v6; // rsi
  unsigned int v8; // edi
  int v9; // r15d
  wchar_t v10; // r12
  HKEY v11; // rcx
  int v13; // eax
  size_t v14; // rax
  wchar_t *v15; // r13
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // [rsp+30h] [rbp-68h]
  unsigned int v19; // [rsp+30h] [rbp-68h]
  HKEY hKeya; // [rsp+38h] [rbp-60h] BYREF

  v6 = (LPCWSTR)lpSubKey;
  hKeya = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qSq(
      (_DWORD)hKey,
      294,
      (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
      (_DWORD)hKey,
      lpSubKey,
      (__int64)a4);
  if ( !a4 )
  {
    v8 = 87;
    goto LABEL_10;
  }
  *a4 = 0;
  if ( !v6 )
  {
    v8 = 87;
    goto LABEL_10;
  }
  if ( !a2 && !hKey )
  {
    v8 = 87;
    goto LABEL_10;
  }
  v8 = 0;
  v9 = 0;
  v10 = *v6;
  while ( 1 )
  {
    if ( !v10 )
    {
      *a4 = v9;
      goto LABEL_10;
    }
    v14 = wcscspn(v6, L" ,;");
    v10 = v6[v14];
    v15 = (wchar_t *)&v6[v14];
    *v15 = 0;
    if ( hKey )
    {
      v16 = RegOpenKeyExW(hKey, v6, 0, 0x20019u, &hKeya);
      v18 = v16;
      if ( v16 != 2 )
        break;
    }
LABEL_21:
    if ( a2 )
    {
      v17 = RegOpenKeyExW(a2, v6, 0, 0x20019u, &hKeya);
      v19 = v17;
      if ( v17 != 2 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          WPP_SF_SD(1035, 297, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (_DWORD)v6, v17);
          v17 = v19;
        }
        v8 = v17;
        if ( v17 )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_d(1035, 298, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v17);
          goto LABEL_10;
        }
        RegCloseKey(hKeya);
        ++v9;
        hKeya = 0;
      }
    }
    *v15 = v10;
    v6 = v15 + 1;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_SD(1035, 295, (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (_DWORD)v6, v16);
    v16 = v18;
  }
  v8 = v16;
  if ( !v16 )
  {
    RegCloseKey(hKeya);
    ++v9;
    hKeya = 0;
    goto LABEL_21;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 296, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v16);
LABEL_10:
  v11 = hKeya;
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    if ( a4 )
      v13 = *a4;
    else
      v13 = -1;
    WPP_SF_Dd(v11, 299, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v8, v13);
  }
  return v8;
}

```

## disassembly

```asm
0x180023760  mov     r11, rsp
0x180023763  push    rbx
0x180023764  sub     rsp, 90h
0x18002376b  mov     rax, cs:__security_cookie
0x180023772  xor     rax, rsp
0x180023775  mov     [rsp+98h+var_58], rax
0x18002377a  mov     [r11-10h], rbp
0x18002377e  mov     rbx, r9
0x180023781  mov     [r11-18h], rsi
0x180023785  mov     rbp, rcx
0x180023788  mov     [r11-28h], r12
0x18002378c  mov     rsi, r8
0x18002378f  xor     r12d, r12d
0x180023792  mov     [r11-38h], r14
0x180023796  mov     [r11-60h], r12
0x18002379a  mov     r14, rdx
0x18002379d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800237a4  jnz     loc_18002394C
0x1800237aa  mov     [rsp+98h+var_20], rdi
0x1800237af  test    rbx, rbx
0x1800237b2  jz      loc_18002384E
0x1800237b8  mov     [rbx], r12d
0x1800237bb  test    rsi, rsi
0x1800237be  jz      loc_180023938
0x1800237c4  test    r14, r14
0x1800237c7  jnz     short loc_1800237D2
0x1800237c9  test    rbp, rbp
0x1800237cc  jz      loc_180023942
0x1800237d2  mov     [rsp+98h+var_40], r15
0x1800237d7  mov     edi, r12d
0x1800237da  mov     r15d, r12d
0x1800237dd  mov     [rsp+98h+var_30], r13
0x1800237e2  movzx   r12d, word ptr [rsi]
0x1800237e6  test    r12w, r12w
0x1800237ea  jnz     loc_18002387D
0x1800237f0  mov     [rbx], r15d
0x1800237f3  mov     r13, [rsp+98h+var_30]
0x1800237f8  xor     r12d, r12d
0x1800237fb  mov     r15, [rsp+98h+var_40]
0x180023800  mov     rcx, [rsp+98h+hKey]; hKey
0x180023805  mov     r14, [rsp+98h+var_38]
0x18002380a  mov     rsi, [rsp+98h+var_18]
0x180023812  mov     rbp, [rsp+98h+var_10]
0x18002381a  test    rcx, rcx
0x18002381d  jnz     loc_180023A38
0x180023823  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002382a  mov     r12, [rsp+98h+var_28]
0x18002382f  jnz     short loc_180023855
0x180023831  mov     eax, edi
0x180023833  mov     rdi, [rsp+98h+var_20]
0x180023838  mov     rcx, [rsp+98h+var_58]
0x18002383d  xor     rcx, rsp; StackCookie
0x180023840  call    __security_check_cookie
0x180023845  add     rsp, 90h
0x18002384c  pop     rbx
0x18002384d  retn
0x18002384e  mov     edi, 57h ; 'W'
0x180023853  jmp     short loc_180023800
0x180023855  test    rbx, rbx
0x180023858  jz      short loc_180023876
0x18002385a  mov     eax, [rbx]
0x18002385c  mov     edx, 12Bh
0x180023861  mov     dword ptr [rsp+98h+phkResult], eax
0x180023865  mov     r9d, edi
0x180023868  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18002386f  call    WPP_SF_Dd
0x180023874  jmp     short loc_180023831
0x180023876  mov     eax, 0FFFFFFFFh
0x18002387b  jmp     short loc_18002385C
0x18002387d  lea     rdx, Control; " ,;"
0x180023884  mov     rcx, rsi; String
0x180023887  call    cs:__imp_wcscspn
0x18002388d  movzx   r12d, word ptr [rsi+rax*2]
0x180023892  lea     r13, [rsi+rax*2]
0x180023896  xor     eax, eax
0x180023898  mov     [r13+0], ax
0x18002389d  test    rbp, rbp
0x1800238a0  jz      short loc_1800238CA
0x1800238a2  lea     rax, [rsp+98h+hKey]
0x1800238a7  mov     r9d, 20019h; samDesired
0x1800238ad  xor     r8d, r8d; ulOptions
0x1800238b0  mov     [rsp+98h+phkResult], rax; phkResult
0x1800238b5  mov     rdx, rsi; lpSubKey
0x1800238b8  mov     rcx, rbp; hKey
0x1800238bb  call    cs:__imp_RegOpenKeyExW
0x1800238c1  mov     [rsp+98h+var_68], eax
0x1800238c5  cmp     eax, 2
0x1800238c8  jnz     short loc_1800238E1
0x1800238ca  test    r14, r14
0x1800238cd  jnz     loc_180023995
0x1800238d3  mov     [r13+0], r12w
0x1800238d8  lea     rsi, [r13+2]
0x1800238dc  jmp     loc_1800237E6
0x1800238e1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800238e8  jnz     loc_18002396F
0x1800238ee  mov     edi, eax
0x1800238f0  test    eax, eax
0x1800238f2  jnz     short loc_18002390D
0x1800238f4  mov     rcx, [rsp+98h+hKey]; hKey
0x1800238f9  call    cs:__imp_RegCloseKey
0x1800238ff  inc     r15d
0x180023902  mov     [rsp+98h+hKey], 0
0x18002390b  jmp     short loc_1800238CA
0x18002390d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023914  jz      loc_1800237F3
0x18002391a  mov     edx, 128h
0x18002391f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023926  mov     ecx, 40Bh
0x18002392b  mov     r9d, eax
0x18002392e  call    WPP_SF_d
0x180023933  jmp     loc_1800237F3
0x180023938  mov     edi, 57h ; 'W'
0x18002393d  jmp     loc_180023800
0x180023942  mov     edi, 57h ; 'W'
0x180023947  jmp     loc_180023800
0x18002394c  mov     edx, 126h
0x180023951  mov     [rsp+98h+var_70], rbx
0x180023956  mov     r9, rbp
0x180023959  mov     [rsp+98h+phkResult], rsi
0x18002395e  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023965  call    WPP_SF_qSq
0x18002396a  jmp     loc_1800237AA
0x18002396f  mov     edx, 127h
0x180023974  mov     dword ptr [rsp+98h+phkResult], eax
0x180023978  mov     ecx, 40Bh
0x18002397d  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023984  mov     r9, rsi
0x180023987  call    WPP_SF_SD
0x18002398c  mov     eax, [rsp+98h+var_68]
0x180023990  jmp     loc_1800238EE
0x180023995  lea     rax, [rsp+98h+hKey]
0x18002399a  mov     r9d, 20019h; samDesired
0x1800239a0  xor     r8d, r8d; ulOptions
0x1800239a3  mov     [rsp+98h+phkResult], rax; phkResult
0x1800239a8  mov     rdx, rsi; lpSubKey
0x1800239ab  mov     rcx, r14; hKey
0x1800239ae  call    cs:__imp_RegOpenKeyExW
0x1800239b4  mov     [rsp+98h+var_68], eax
0x1800239b8  cmp     eax, 2
0x1800239bb  jz      loc_1800238D3
0x1800239c1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800239c8  jz      short loc_1800239EB
0x1800239ca  mov     edx, 129h
0x1800239cf  mov     dword ptr [rsp+98h+phkResult], eax
0x1800239d3  mov     ecx, 40Bh
0x1800239d8  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800239df  mov     r9, rsi
0x1800239e2  call    WPP_SF_SD
0x1800239e7  mov     eax, [rsp+98h+var_68]
0x1800239eb  mov     edi, eax
0x1800239ed  test    eax, eax
0x1800239ef  jnz     short loc_180023A0D
0x1800239f1  mov     rcx, [rsp+98h+hKey]; hKey
0x1800239f6  call    cs:__imp_RegCloseKey
0x1800239fc  inc     r15d
0x1800239ff  mov     [rsp+98h+hKey], 0
0x180023a08  jmp     loc_1800238D3
0x180023a0d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023a14  jz      loc_1800237F3
0x180023a1a  mov     edx, 12Ah
0x180023a1f  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023a26  mov     ecx, 40Bh
0x180023a2b  mov     r9d, eax
0x180023a2e  call    WPP_SF_d
0x180023a33  jmp     loc_1800237F3
0x180023a38  call    cs:__imp_RegCloseKey
0x180023a3e  mov     [rsp+98h+hKey], r12
0x180023a43  jmp     loc_180023823
```
