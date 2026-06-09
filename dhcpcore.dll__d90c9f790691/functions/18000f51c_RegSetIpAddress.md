# RegSetIpAddress

- ea: `0x18000f51c`
- end: `0x18000f785`
- name: `RegSetIpAddress`
- size: `617`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180015fec`

## callees

- `0x180005670`
- `0x1800057f0`
- `0x180005da4`
- `0x180006440`
- `0x18000bba0`
- `0x18000f51c`
- `0x18000f85c`
- `0x18001cef0`
- `0x180047a48`
- `0x180047e3c`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f5f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f73f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f5f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f73f`
- `WS2_32!__imp_inet_ntoa` at `0x18000f567`
- `WS2_32!__imp_inet_ntoa` at `0x18000f567`

## pseudocode

```c
__int64 __fastcall RegSetIpAddress(HKEY hKey, const WCHAR *a2, DWORD a3, struct in_addr a4)
{
  const BYTE *v5; // r14
  char *v6; // rax
  const wchar_t *v7; // rax
  size_t v8; // rdx
  const BYTE *lpData; // rsi
  HRESULT v10; // eax
  int v11; // edi
  unsigned int v12; // ebx
  int v13; // r12d
  unsigned int RegistryString; // eax
  size_t v15; // rdx
  STRSAFE_PCNZWCH v16; // rsi
  int v17; // edi
  HRESULT v18; // eax
  unsigned int v19; // r13d
  unsigned int v20; // edi
  unsigned int v21; // r15d
  void *v22; // rax
  unsigned int v23; // eax
  size_t pcbLength; // [rsp+38h] [rbp-51h] BYREF
  DWORD v26; // [rsp+40h] [rbp-49h] BYREF
  DWORD dwType; // [rsp+44h] [rbp-45h]
  LPCWSTR lpValueName; // [rsp+48h] [rbp-41h]
  STRSAFE_PCNZWCH psz; // [rsp+50h] [rbp-39h] BYREF
  LPVOID v30; // [rsp+58h] [rbp-31h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+60h] [rbp-29h]
  HKEY hKeya; // [rsp+68h] [rbp-21h]

  hKeya = hKey;
  psz = 0;
  v30 = 0;
  v5 = 0;
  v26 = 0;
  dwType = a3;
  lpValueName = a2;
  v6 = inet_ntoa(a4);
  v7 = (const wchar_t *)DhcpOemToUnicode(v6);
  lpData = (const BYTE *)v7;
  pszSrc = v7;
  pcbLength = 0;
  if ( !v7 )
  {
    v10 = -2147024809;
    HIDWORD(pcbLength) = 104;
LABEL_3:
    v11 = 0;
    goto LABEL_7;
  }
  v10 = StringCbLengthW(v7, v8, &pcbLength);
  if ( v10 < 0 )
  {
    HIDWORD(pcbLength) = 108;
    goto LABEL_3;
  }
  v11 = pcbLength;
LABEL_7:
  v12 = WX_WIN32_FROM_HR((unsigned int)v10);
  if ( v12 )
    return v12;
  v13 = v11 + 2;
  if ( dwType == 1 )
    return (unsigned int)RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, v11 + 2);
  RegistryString = GetRegistryString(hKey, lpValueName, &psz, &v26);
  v16 = psz;
  v12 = RegistryString;
  if ( RegistryString )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 25, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, RegistryString);
LABEL_26:
    if ( v16 )
      DhcpPunycodeFree((LPVOID *)&psz);
    if ( v5 )
      DhcpPunycodeFree(&v30);
    return v12;
  }
  if ( psz )
  {
    pcbLength = 0;
    v18 = StringCbLengthW(psz, v15, &pcbLength);
    if ( v18 >= 0 )
    {
      v17 = pcbLength;
    }
    else
    {
      HIDWORD(pcbLength) = 108;
      v17 = 0;
    }
    v12 = WX_WIN32_FROM_HR((unsigned int)v18);
    if ( !v12 )
    {
      v19 = v17 + 2;
      v20 = v26 - (v17 + 2);
      v21 = v20 + v13;
      if ( v20 + v13 >= v20 )
      {
        v22 = DhcpAlloc(v21);
        v30 = v22;
        v5 = (const BYTE *)v22;
        if ( v22 )
        {
          v23 = StringCbCopyW((STRSAFE_LPWSTR)v22, v21, pszSrc);
          v12 = WX_WIN32_FROM_HR(v23);
          if ( !v12 )
          {
            memcpy_0((void *)&v5[v13], (char *)v16 + v19, v20);
            v12 = RegSetValueExW(hKeya, lpValueName, 0, dwType, v5, v20 + v13);
          }
        }
        else
        {
          v12 = 8;
        }
      }
      else
      {
        v12 = 122;
      }
    }
    goto LABEL_26;
  }
  v12 = 1015;
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, (unsigned int)((_DWORD)psz + 26), WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, 1015);
  return v12;
}

```

## disassembly

```asm
0x18000f51c  push    rbp
0x18000f51e  push    rbx
0x18000f51f  push    rsi
0x18000f520  push    rdi
0x18000f521  push    r12
0x18000f523  push    r13
0x18000f525  push    r14
0x18000f527  push    r15
0x18000f529  lea     rbp, [rsp-1Fh]
0x18000f52e  sub     rsp, 0A8h
0x18000f535  mov     rax, cs:__security_cookie
0x18000f53c  xor     rax, rsp
0x18000f53f  mov     [rbp+57h+var_50], rax
0x18000f543  xor     r12d, r12d
0x18000f546  mov     [rbp+57h+hKey], rcx
0x18000f54a  mov     r13, rcx
0x18000f54d  mov     [rbp+57h+psz], r12
0x18000f551  mov     ecx, r9d; in
0x18000f554  mov     [rbp+57h+var_88], r12
0x18000f558  mov     r14d, r12d
0x18000f55b  mov     [rbp+57h+var_A0], r12d
0x18000f55f  mov     [rbp+57h+dwType], r8d
0x18000f563  mov     [rbp+57h+lpValueName], rdx
0x18000f567  call    cs:__imp_inet_ntoa
0x18000f56d  mov     rcx, rax; SourceString
0x18000f570  lea     rdx, [rbp+57h+var_70]
0x18000f574  call    DhcpOemToUnicode
0x18000f579  mov     dword ptr [rbp+57h+pcbLength+4], r12d
0x18000f57d  mov     rsi, rax
0x18000f580  mov     [rbp+57h+pszSrc], rax
0x18000f584  mov     r15d, 80070057h
0x18000f58a  mov     [rbp-51h], r12
0x18000f58e  mov     [rbp+57h+var_B0], r12d
0x18000f592  test    rax, rax
0x18000f595  jnz     short loc_18000F5A6
0x18000f597  mov     eax, r15d
0x18000f59a  mov     dword ptr [rbp+57h+pcbLength+4], 68h ; 'h'
0x18000f5a1  mov     edi, r12d
0x18000f5a4  jmp     short loc_18000F5C2
0x18000f5a6  lea     r8, [rbp+57h+pcbLength]; pcbLength
0x18000f5aa  mov     rcx, rsi; psz
0x18000f5ad  call    StringCbLengthW
0x18000f5b2  test    eax, eax
0x18000f5b4  jns     short loc_18000F5BF
0x18000f5b6  mov     dword ptr [rbp+57h+pcbLength+4], 6Ch ; 'l'
0x18000f5bd  jmp     short loc_18000F5A1
0x18000f5bf  mov     edi, dword ptr [rbp+57h+pcbLength]
0x18000f5c2  mov     ecx, eax
0x18000f5c4  call    WX_WIN32_FROM_HR
0x18000f5c9  mov     ebx, eax
0x18000f5cb  test    eax, eax
0x18000f5cd  jnz     loc_18000F763
0x18000f5d3  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x18000f5d7  lea     r9d, [rax+1]; dwType
0x18000f5db  lea     r12d, [rdi+2]
0x18000f5df  mov     rcx, r13; hKey
0x18000f5e2  cmp     [rbp+57h+dwType], r9d
0x18000f5e6  jnz     short loc_18000F602
0x18000f5e8  mov     [rsp+0E0h+cbData], r12d; cbData
0x18000f5ed  xor     r8d, r8d; Reserved
0x18000f5f0  mov     [rsp+0E0h+lpData], rsi; lpData
0x18000f5f5  call    cs:__imp_RegSetValueExW
0x18000f5fb  mov     ebx, eax
0x18000f5fd  jmp     loc_18000F763
0x18000f602  lea     r9, [rbp+57h+var_A0]
0x18000f606  lea     r8, [rbp+57h+psz]
0x18000f60a  call    GetRegistryString
0x18000f60f  mov     rsi, [rbp+57h+psz]
0x18000f613  mov     ebx, eax
0x18000f615  test    eax, eax
0x18000f617  jz      short loc_18000F644
0x18000f619  test    byte ptr cs:xmmword_1800616A0, 2
0x18000f620  jz      loc_18000F747
0x18000f626  mov     edx, 19h
0x18000f62b  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18000f632  mov     ecx, 401h
0x18000f637  mov     r9d, eax
0x18000f63a  call    WPP_SF_D
0x18000f63f  jmp     loc_18000F747
0x18000f644  xor     ebx, ebx
0x18000f646  test    rsi, rsi
0x18000f649  jnz     short loc_18000F677
0x18000f64b  mov     ebx, 3F7h
0x18000f650  test    byte ptr cs:xmmword_1800616A0, 2
0x18000f657  jz      loc_18000F763
0x18000f65d  lea     edx, [rsi+1Ah]
0x18000f660  mov     r9d, ebx
0x18000f663  lea     ecx, [rbx+0Ah]
0x18000f666  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18000f66d  call    WPP_SF_D
0x18000f672  jmp     loc_18000F763
0x18000f677  mov     dword ptr [rbp+57h+pcbLength+4], ebx
0x18000f67a  mov     [rbp+57h+pcbLength], rbx
0x18000f67e  mov     [rbp+57h+var_B0], ebx
0x18000f681  test    rsi, rsi
0x18000f684  jnz     short loc_18000F691
0x18000f686  mov     dword ptr [rbp+57h+pcbLength+4], 68h ; 'h'
0x18000f68d  mov     edi, ebx
0x18000f68f  jmp     short loc_18000F6B0
0x18000f691  lea     r8, [rbp+57h+pcbLength]; pcbLength
0x18000f695  mov     rcx, rsi; psz
0x18000f698  call    StringCbLengthW
0x18000f69d  mov     r15d, eax
0x18000f6a0  test    eax, eax
0x18000f6a2  jns     short loc_18000F6AD
0x18000f6a4  mov     dword ptr [rbp+57h+pcbLength+4], 6Ch ; 'l'
0x18000f6ab  jmp     short loc_18000F68D
0x18000f6ad  mov     edi, dword ptr [rbp+57h+pcbLength]
0x18000f6b0  mov     ecx, r15d
0x18000f6b3  call    WX_WIN32_FROM_HR
0x18000f6b8  mov     ebx, eax
0x18000f6ba  test    eax, eax
0x18000f6bc  jnz     loc_18000F747
0x18000f6c2  lea     r13d, [rdi+2]
0x18000f6c6  mov     edi, [rbp+57h+var_A0]
0x18000f6c9  sub     edi, r13d
0x18000f6cc  lea     r15d, [rdi+r12]
0x18000f6d0  cmp     r15d, edi
0x18000f6d3  jnb     short loc_18000F6DA
0x18000f6d5  lea     ebx, [rax+7Ah]
0x18000f6d8  jmp     short loc_18000F747
0x18000f6da  mov     ecx, r15d
0x18000f6dd  mov     ebx, r15d
0x18000f6e0  call    DhcpAlloc
0x18000f6e5  mov     [rbp+57h+var_88], rax
0x18000f6e9  mov     r14, rax
0x18000f6ec  test    rax, rax
0x18000f6ef  jnz     short loc_18000F6F6
0x18000f6f1  lea     ebx, [rax+8]
0x18000f6f4  jmp     short loc_18000F747
0x18000f6f6  mov     r8, [rbp+57h+pszSrc]; pszSrc
0x18000f6fa  mov     rdx, rbx; cbDest
0x18000f6fd  mov     rcx, r14; pszDest
0x18000f700  call    StringCbCopyW
0x18000f705  mov     ecx, eax
0x18000f707  call    WX_WIN32_FROM_HR
0x18000f70c  mov     ebx, eax
0x18000f70e  test    eax, eax
0x18000f710  jnz     short loc_18000F747
0x18000f712  mov     edx, r13d
0x18000f715  mov     ecx, r12d
0x18000f718  add     rdx, rsi; Src
0x18000f71b  add     rcx, r14; void *
0x18000f71e  mov     r8d, edi; Size
0x18000f721  call    memcpy_0
0x18000f726  mov     r9d, [rbp+57h+dwType]; dwType
0x18000f72a  xor     r8d, r8d; Reserved
0x18000f72d  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x18000f731  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f735  mov     [rsp+0E0h+cbData], r15d; cbData
0x18000f73a  mov     [rsp+0E0h+lpData], r14; lpData
0x18000f73f  call    cs:__imp_RegSetValueExW
0x18000f745  mov     ebx, eax
0x18000f747  test    rsi, rsi
0x18000f74a  jz      short loc_18000F755
0x18000f74c  lea     rcx, [rbp+57h+psz]
0x18000f750  call    DhcpPunycodeFree
0x18000f755  test    r14, r14
0x18000f758  jz      short loc_18000F763
0x18000f75a  lea     rcx, [rbp+57h+var_88]
0x18000f75e  call    DhcpPunycodeFree
0x18000f763  mov     eax, ebx
0x18000f765  mov     rcx, [rbp+57h+var_50]
0x18000f769  xor     rcx, rsp; StackCookie
0x18000f76c  call    __security_check_cookie
0x18000f771  add     rsp, 0A8h
0x18000f778  pop     r15
0x18000f77a  pop     r14
0x18000f77c  pop     r13
0x18000f77e  pop     r12
0x18000f780  pop     rdi
0x18000f781  pop     rsi
0x18000f782  pop     rbx
0x18000f783  pop     rbp
0x18000f784  retn
```
