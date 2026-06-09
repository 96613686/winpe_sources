# DnsGetDhcpServerPropertiesImplOld

- ea: `0x180022140`
- end: `0x1800223e3`
- name: `DnsGetDhcpServerPropertiesImplOld`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800217f0`

## callees

- `0x180021384`
- `0x180022140`
- `0x1800223f0`
- `0x180046ec0`
- `0x180085e68`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022267`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022267`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002227c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002227c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022299`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022299`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800221e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800221e9`

## pseudocode

```c
__int64 __fastcall DnsGetDhcpServerPropertiesImplOld(const NPI_MODULEID *a1, __int64 a2, LPVOID *a3)
{
  HKEY v6; // rbx
  HKEY v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int Value; // r14d
  void *v11; // rdi
  HANDLE ProcessHeap; // rax
  int v14; // r9d
  __int64 v15; // [rsp+28h] [rbp-50h]
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF

  LODWORD(v16) = 0;
  v6 = 0;
  lpMem = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    Value = 87;
    goto LABEL_13;
  }
  if ( !a3 )
  {
    Value = 87;
    goto LABEL_13;
  }
  hKey = 0;
  if ( a1 != &NPI_MS_IPV4_MODULEID )
  {
    if ( a1 != &NPI_MS_IPV6_MODULEID )
      goto LABEL_10;
    goto LABEL_21;
  }
  if ( a1 == &NPI_MS_IPV6_MODULEID )
  {
LABEL_21:
    v7 = g_Dhcpv6Key;
    goto LABEL_8;
  }
  v7 = g_Dhcpv4Key;
LABEL_8:
  if ( v7 )
  {
    v8 = RegOpenKeyExW(v7, (LPCWSTR)(a2 + 104), 0, 0x20019u, &hKey);
    v9 = v8;
    if ( !v8 )
      goto LABEL_10;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 17, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, v8);
    if ( v9 == 1168 )
      goto LABEL_10;
    goto LABEL_26;
  }
  v9 = 2;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_d(1035, 16, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, 2);
LABEL_26:
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 18, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, v9);
  }
LABEL_10:
  v6 = hKey;
  if ( !hKey || a1 != &NPI_MS_IPV4_MODULEID )
    goto LABEL_22;
  Value = privateRegReadValue(hKey, L"DhcpNameServer", (__int64)a3, 1, (BYTE *)&lpMem, (DWORD *)&v16);
  if ( Value )
    goto LABEL_13;
  if ( (unsigned int)v16 >= 2 && *(_WORD *)lpMem )
  {
    Value = 0;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      LODWORD(v15) = (unsigned __int16)GetFamilyFromModuleId(a1);
      WPP_SF_SSd(1035, 24, (unsigned int)WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids, v14, a2 + 104, v15);
    }
    *a3 = lpMem;
    lpMem = 0;
  }
  else
  {
LABEL_22:
    Value = 1168;
  }
LABEL_13:
  v11 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, v11);
  }
  lpMem = 0;
  if ( v6 )
    RegCloseKey(v6);
  return Value;
}

```

## disassembly

```asm
0x180022140  mov     r11, rsp
0x180022143  push    rbx
0x180022144  sub     rsp, 70h
0x180022148  mov     rax, cs:__security_cookie
0x18002214f  xor     rax, rsp
0x180022152  mov     [rsp+78h+var_30], rax
0x180022157  mov     [r11+8], rbp
0x18002215b  mov     rbp, rdx
0x18002215e  mov     [r11-10h], rsi
0x180022162  mov     rsi, rcx
0x180022165  mov     [r11-18h], rdi
0x180022169  mov     rdi, r8
0x18002216c  mov     [r11-28h], r15
0x180022170  xor     r15d, r15d
0x180022173  mov     [r11-48h], r15d
0x180022177  mov     ebx, r15d
0x18002217a  mov     [r11-40h], r15
0x18002217e  test    r8, r8
0x180022181  jz      short loc_180022186
0x180022183  mov     [r8], r15
0x180022186  mov     [rsp+78h+var_20], r14
0x18002218b  test    rbp, rbp
0x18002218e  jz      loc_18002234A
0x180022194  test    rdi, rdi
0x180022197  jz      loc_1800223D8
0x18002219d  lea     r14, NPI_MS_IPV4_MODULEID
0x1800221a4  mov     [rsp+78h+hKey], r15
0x1800221a9  lea     rax, NPI_MS_IPV6_MODULEID
0x1800221b0  cmp     rsi, r14
0x1800221b3  jnz     loc_1800222BA
0x1800221b9  cmp     rsi, rax
0x1800221bc  jz      loc_1800222C3
0x1800221c2  mov     rcx, cs:g_Dhcpv4Key; hKey
0x1800221c9  test    rcx, rcx
0x1800221cc  jz      loc_180022373
0x1800221d2  lea     rax, [rsp+78h+hKey]
0x1800221d7  add     rdx, 68h ; 'h'; lpSubKey
0x1800221db  mov     r9d, 20019h; samDesired
0x1800221e1  mov     [rsp+78h+phkResult], rax; phkResult
0x1800221e6  xor     r8d, r8d; ulOptions
0x1800221e9  call    cs:__imp_RegOpenKeyExW
0x1800221ef  mov     ebx, eax
0x1800221f1  test    eax, eax
0x1800221f3  jnz     loc_1800222DA
0x1800221f9  mov     rbx, [rsp+78h+hKey]
0x1800221fe  test    rbx, rbx
0x180022201  jz      loc_1800222CF
0x180022207  cmp     rsi, r14
0x18002220a  jnz     loc_1800222CF
0x180022210  lea     rax, [rsp+78h+var_48]
0x180022215  mov     r9d, 1
0x18002221b  mov     [rsp+78h+var_50], rax; __int64
0x180022220  lea     rdx, aDhcpnameserver; "DhcpNameServer"
0x180022227  lea     rax, [rsp+78h+lpMem]
0x18002222c  mov     rcx, rbx; hKey
0x18002222f  mov     [rsp+78h+phkResult], rax; __int64
0x180022234  call    privateRegReadValue
0x180022239  mov     r14d, eax
0x18002223c  test    eax, eax
0x18002223e  jz      loc_18002231A
0x180022244  mov     rdi, [rsp+78h+lpMem]
0x180022249  mov     rsi, [rsp+78h+var_10]
0x18002224e  mov     rbp, [rsp+78h+arg_0]
0x180022256  test    rdi, rdi
0x180022259  jz      short loc_180022282
0x18002225b  mov     rax, cs:g_hProcessHeap
0x180022262  test    rax, rax
0x180022265  jnz     short loc_180022274
0x180022267  call    cs:__imp_GetProcessHeap
0x18002226d  mov     cs:g_hProcessHeap, rax
0x180022274  mov     r8, rdi; lpMem
0x180022277  xor     edx, edx; dwFlags
0x180022279  mov     rcx, rax; hHeap
0x18002227c  call    cs:__imp_HeapFree
0x180022282  mov     rdi, [rsp+78h+var_18]
0x180022287  mov     [rsp+78h+lpMem], r15
0x18002228c  mov     r15, [rsp+78h+var_28]
0x180022291  test    rbx, rbx
0x180022294  jz      short loc_18002229F
0x180022296  mov     rcx, rbx; hKey
0x180022299  call    cs:__imp_RegCloseKey
0x18002229f  mov     eax, r14d
0x1800222a2  mov     r14, [rsp+78h+var_20]
0x1800222a7  mov     rcx, [rsp+78h+var_30]
0x1800222ac  xor     rcx, rsp; StackCookie
0x1800222af  call    __security_check_cookie
0x1800222b4  add     rsp, 70h
0x1800222b8  pop     rbx
0x1800222b9  retn
0x1800222ba  cmp     rsi, rax
0x1800222bd  jnz     loc_1800221F9
0x1800222c3  mov     rcx, cs:g_Dhcpv6Key
0x1800222ca  jmp     loc_1800221C9
0x1800222cf  mov     r14d, 490h
0x1800222d5  jmp     loc_180022244
0x1800222da  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800222e1  jnz     short loc_180022355
0x1800222e3  cmp     ebx, 490h
0x1800222e9  jz      loc_1800221F9
0x1800222ef  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800222f6  jz      loc_1800221F9
0x1800222fc  mov     edx, 12h
0x180022301  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180022308  mov     ecx, 40Bh
0x18002230d  mov     r9d, ebx
0x180022310  call    WPP_SF_d
0x180022315  jmp     loc_1800221F9
0x18002231a  cmp     dword ptr [rsp+78h+var_48], 2
0x18002231f  jb      short loc_1800222CF
0x180022321  mov     r9, [rsp+78h+lpMem]
0x180022326  cmp     [r9], r15w
0x18002232a  jz      short loc_1800222CF
0x18002232c  mov     r14d, r15d
0x18002232f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180022336  jnz     short loc_1800223A3
0x180022338  mov     rax, [rsp+78h+lpMem]
0x18002233d  mov     [rdi], rax
0x180022340  mov     [rsp+78h+lpMem], r15
0x180022345  jmp     loc_180022244
0x18002234a  mov     r14d, 57h ; 'W'
0x180022350  jmp     loc_180022244
0x180022355  mov     edx, 11h
0x18002235a  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180022361  mov     ecx, 40Bh
0x180022366  mov     r9d, ebx
0x180022369  call    WPP_SF_d
0x18002236e  jmp     loc_1800222E3
0x180022373  mov     ebx, 2
0x180022378  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002237f  jz      loc_1800221F9
0x180022385  mov     edx, 10h
0x18002238a  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x180022391  mov     ecx, 40Bh
0x180022396  mov     r9d, ebx
0x180022399  call    WPP_SF_d
0x18002239e  jmp     loc_1800222EF
0x1800223a3  mov     rcx, rsi
0x1800223a6  call    GetFamilyFromModuleId
0x1800223ab  movzx   r10d, ax
0x1800223af  lea     r8, WPP_caccfeb905c83e320acfcbeb12c6208a_Traceguids
0x1800223b6  lea     rax, [rbp+68h]
0x1800223ba  mov     dword ptr [rsp+78h+var_50], r10d
0x1800223bf  mov     edx, 18h
0x1800223c4  mov     [rsp+78h+phkResult], rax
0x1800223c9  mov     ecx, 40Bh
0x1800223ce  call    WPP_SF_SSd
0x1800223d3  jmp     loc_180022338
0x1800223d8  mov     r14d, 57h ; 'W'
0x1800223de  jmp     loc_180022244
```
