# ReadDnsWellKnownServersReg

- ea: `0x180052d1c`
- end: `0x180053063`
- name: `ReadDnsWellKnownServersReg`
- size: `839`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180024100`
- `0x180024550`
- `0x18002f5e8`

## callees

- `0x18000b130`
- `0x180024ad0`
- `0x180041290`
- `0x180046a70`
- `0x180046ec0`
- `0x180047818`
- `0x180052890`
- `0x180052d1c`
- `0x1800535a4`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180052ec7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180052ec7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005301e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005301e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052e66`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180052e66`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052e1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052e1d`

## string_xrefs

- `0x180052e0f`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\DohWellKnownServers`

## pseudocode

```c
__int64 ReadDnsWellKnownServersReg()
{
  DnsWellKnownAddrMap *v0; // rax
  DnsWellKnownAddrMap *v1; // rbx
  unsigned int v2; // eax
  unsigned int v3; // ebx
  DWORD i; // edi
  unsigned int WellKnownServerReg; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v9; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  void *v11[2]; // [rsp+70h] [rbp-90h] BYREF
  void *v12[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v13; // [rsp+90h] [rbp-70h]
  DWORD cSubKeys; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchName; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v16[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+B0h] [rbp-50h]
  WCHAR Name[72]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  memset_0(Name, 0, 0x82u);
  cchName = 0;
  cSubKeys = 0;
  v17 = 0;
  *(_OWORD *)v16 = 0;
  v13 = 0;
  *(_OWORD *)v11 = 0;
  *(_OWORD *)v12 = 0;
  v9 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 31, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids);
  if ( g_spDnsWellKnownAddrMap )
    goto LABEL_7;
  g_spDnsWellKnownAddrMap = 0;
  v0 = (DnsWellKnownAddrMap *)operator new(0x18u);
  v1 = v0;
  if ( !v0 )
  {
LABEL_16:
    v3 = 14;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_36;
    v6 = 32;
    v7 = 14;
    goto LABEL_35;
  }
  *((_QWORD *)v0 + 1) = 0;
  *((_QWORD *)v0 + 2) = 0;
  *(_QWORD *)v0 = 0;
  *((_DWORD *)v0 + 2) = 1;
  *((_DWORD *)v0 + 4) = 1;
  if ( (int)CWxRefMap<DnsWellKnownAddrMap,DnsWellKnownServerNode>::FinalConstruct(v0) < 0 )
  {
    DnsWellKnownAddrMap::Release(v1);
    goto LABEL_16;
  }
  g_spDnsWellKnownAddrMap = v1;
LABEL_7:
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\DohWellKnownServers",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_36;
    v6 = 33;
  }
  else
  {
    v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v3 = v2;
    if ( v2 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_36;
      v6 = 34;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= cSubKeys )
        {
          v3 = 0;
          goto LABEL_36;
        }
        MIDL_user_free(v11[0]);
        v11[0] = 0;
        MIDL_user_free(v12[0]);
        v12[0] = 0;
        cchName = 65;
        v2 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        v3 = v2;
        if ( v2 )
          break;
        WellKnownServerReg = ReadWellKnownServerReg(hKey, Name, (__int64)v12, (__int64)&v9, (__int64)v16);
        if ( WellKnownServerReg )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_d(1035, v3 + 36, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, WellKnownServerReg);
        }
        else
        {
          if ( (_DWORD)v9 )
          {
            v2 = DnsAddWellKnownServerToMap(v16, 2, 0, v12);
            v3 = v2;
            if ( v2 )
            {
              if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
                goto LABEL_36;
              v6 = 37;
              goto LABEL_34;
            }
          }
          if ( HIDWORD(v9) )
          {
            v2 = DnsAddWellKnownServerToMap(v16, 1, v11, 0);
            v3 = v2;
            if ( v2 )
            {
              if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
                goto LABEL_36;
              v6 = 38;
              goto LABEL_34;
            }
          }
        }
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_36;
      v6 = 35;
    }
  }
LABEL_34:
  v7 = v2;
LABEL_35:
  WPP_SF_d(1035, v6, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v7);
LABEL_36:
  MIDL_user_free(v11[0]);
  v11[0] = 0;
  MIDL_user_free(v12[0]);
  v12[0] = 0;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 39, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180052d1c  push    rbp
0x180052d1e  push    rbx
0x180052d1f  push    rsi
0x180052d20  push    rdi
0x180052d21  push    r12
0x180052d23  push    r15
0x180052d25  lea     rbp, [rsp-68h]
0x180052d2a  sub     rsp, 168h
0x180052d31  mov     rax, cs:__security_cookie
0x180052d38  xor     rax, rsp
0x180052d3b  mov     [rbp+90h+var_40], rax
0x180052d3f  xor     esi, esi
0x180052d41  lea     rcx, [rbp+90h+Name]; void *
0x180052d45  xor     edx, edx; Val
0x180052d47  mov     [rsp+190h+hKey], rsi
0x180052d4c  mov     r8d, 82h; Size
0x180052d52  call    memset_0
0x180052d57  xorps   xmm0, xmm0
0x180052d5a  mov     [rbp+90h+cchName], esi
0x180052d5d  xor     eax, eax
0x180052d5f  mov     [rbp+90h+cSubKeys], esi
0x180052d62  xorps   xmm1, xmm1
0x180052d65  mov     [rbp+90h+var_E0], rax
0x180052d69  movups  xmmword ptr [rbp+90h+var_F0], xmm0
0x180052d6d  mov     [rbp+90h+var_100], rax
0x180052d71  movups  xmmword ptr [rsp+190h+var_120], xmm0
0x180052d76  mov     dword ptr [rsp+190h+var_130+4], esi
0x180052d7a  movups  xmmword ptr [rbp+90h+var_110], xmm1
0x180052d7e  mov     dword ptr [rsp+190h+var_130], esi
0x180052d82  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052d89  lea     r12, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180052d90  mov     r15d, 40Bh
0x180052d96  jz      short loc_180052DA6
0x180052d98  lea     edx, [rsi+1Fh]
0x180052d9b  mov     ecx, r15d
0x180052d9e  mov     r8, r12
0x180052da1  call    WPP_SF_
0x180052da6  cmp     cs:?g_spDnsWellKnownAddrMap@@3V?$AutoInterface@VDnsWellKnownAddrMap@@@@A, rsi; AutoInterface<DnsWellKnownAddrMap> g_spDnsWellKnownAddrMap
0x180052dad  jnz     short loc_180052DFC
0x180052daf  mov     ecx, 18h; Size
0x180052db4  mov     cs:?g_spDnsWellKnownAddrMap@@3V?$AutoInterface@VDnsWellKnownAddrMap@@@@A, rsi; AutoInterface<DnsWellKnownAddrMap> g_spDnsWellKnownAddrMap
0x180052dbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052dc0  mov     rbx, rax
0x180052dc3  test    rax, rax
0x180052dc6  jz      loc_180052F33
0x180052dcc  mov     [rax+8], rsi
0x180052dd0  mov     rcx, rax
0x180052dd3  mov     [rax+10h], rsi
0x180052dd7  mov     [rax], rsi
0x180052dda  mov     dword ptr [rax+8], 1
0x180052de1  mov     dword ptr [rax+10h], 1
0x180052de8  call    ?FinalConstruct@?$CWxRefMap@VDnsWellKnownAddrMap@@VDnsWellKnownServerNode@@@@AEAAJXZ; CWxRefMap<DnsWellKnownAddrMap,DnsWellKnownServerNode>::FinalConstruct(void)
0x180052ded  test    eax, eax
0x180052def  js      loc_180052F2B
0x180052df5  mov     cs:?g_spDnsWellKnownAddrMap@@3V?$AutoInterface@VDnsWellKnownAddrMap@@@@A, rbx; AutoInterface<DnsWellKnownAddrMap> g_spDnsWellKnownAddrMap
0x180052dfc  lea     rax, [rsp+190h+hKey]
0x180052e01  mov     r9d, 20019h; samDesired
0x180052e07  xor     r8d, r8d; ulOptions
0x180052e0a  mov     [rsp+190h+phkResult], rax; phkResult
0x180052e0f  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180052e16  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052e1d  call    cs:__imp_RegOpenKeyExW
0x180052e23  mov     ebx, eax
0x180052e25  test    eax, eax
0x180052e27  jnz     loc_180052FDC
0x180052e2d  mov     rcx, [rsp+190h+hKey]; hKey
0x180052e32  lea     rax, [rbp+90h+cSubKeys]
0x180052e36  mov     [rsp+190h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180052e3b  xor     r9d, r9d; lpReserved
0x180052e3e  mov     [rsp+190h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180052e43  xor     r8d, r8d; lpcchClass
0x180052e46  mov     [rsp+190h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180052e4b  xor     edx, edx; lpClass
0x180052e4d  mov     [rsp+190h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180052e52  mov     [rsp+190h+lpcValues], rsi; lpcValues
0x180052e57  mov     [rsp+190h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180052e5c  mov     [rsp+190h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180052e61  mov     [rsp+190h+phkResult], rax; lpcSubKeys
0x180052e66  call    cs:__imp_RegQueryInfoKeyW
0x180052e6c  mov     ebx, eax
0x180052e6e  test    eax, eax
0x180052e70  jnz     loc_180052FCC
0x180052e76  mov     edi, esi
0x180052e78  cmp     edi, [rbp+90h+cSubKeys]
0x180052e7b  jnb     loc_180052FC8
0x180052e81  mov     rcx, [rsp+190h+var_120]; void *
0x180052e86  call    MIDL_user_free
0x180052e8b  mov     rcx, [rbp+90h+var_110]; void *
0x180052e8f  mov     [rsp+190h+var_120], rsi
0x180052e94  call    MIDL_user_free
0x180052e99  mov     rcx, [rsp+190h+hKey]; hKey
0x180052e9e  lea     r9, [rbp+90h+cchName]; lpcchName
0x180052ea2  mov     [rsp+190h+lpcValues], rsi; lpftLastWriteTime
0x180052ea7  lea     r8, [rbp+90h+Name]; lpName
0x180052eab  mov     [rsp+190h+lpcbMaxClassLen], rsi; lpcchClass
0x180052eb0  mov     edx, edi; dwIndex
0x180052eb2  mov     [rsp+190h+lpcbMaxSubKeyLen], rsi; lpClass
0x180052eb7  mov     [rsp+190h+phkResult], rsi; lpReserved
0x180052ebc  mov     [rbp+90h+var_110], rsi
0x180052ec0  mov     [rbp+90h+cchName], 41h ; 'A'
0x180052ec7  call    cs:__imp_RegEnumKeyExW
0x180052ecd  mov     ebx, eax
0x180052ecf  test    eax, eax
0x180052ed1  jnz     loc_180052FB8
0x180052ed7  mov     rcx, [rsp+190h+hKey]; hKey
0x180052edc  lea     rax, [rbp+90h+var_F0]
0x180052ee0  mov     [rsp+190h+lpcbMaxClassLen], rax; __int64
0x180052ee5  lea     r9, [rsp+190h+var_130+4]
0x180052eea  lea     rax, [rsp+190h+var_130]
0x180052eef  mov     [rsp+190h+lpcbMaxSubKeyLen], rax; __int64
0x180052ef4  lea     r8, [rsp+190h+var_120]
0x180052ef9  lea     rax, [rbp+90h+var_110]
0x180052efd  lea     rdx, [rbp+90h+Name]; lpSubKey
0x180052f01  mov     [rsp+190h+phkResult], rax; __int64
0x180052f06  call    ReadWellKnownServerReg
0x180052f0b  test    eax, eax
0x180052f0d  jz      short loc_180052F50
0x180052f0f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052f16  jz      short loc_180052F91
0x180052f18  lea     edx, [rbx+24h]
0x180052f1b  mov     ecx, r15d
0x180052f1e  mov     r9d, eax
0x180052f21  mov     r8, r12
0x180052f24  call    WPP_SF_d
0x180052f29  jmp     short loc_180052F91
0x180052f2b  mov     rcx, rbx; this
0x180052f2e  call    ?Release@DnsWellKnownAddrMap@@QEAAKXZ; DnsWellKnownAddrMap::Release(void)
0x180052f33  mov     ebx, 0Eh
0x180052f38  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052f3f  jz      loc_180052FF8
0x180052f45  lea     edx, [rbx+12h]
0x180052f48  mov     r9d, ebx
0x180052f4b  jmp     loc_180052FED
0x180052f50  cmp     dword ptr [rsp+190h+var_130], esi
0x180052f54  jz      short loc_180052F70
0x180052f56  xor     r8d, r8d
0x180052f59  lea     r9, [rbp+90h+var_110]
0x180052f5d  lea     rcx, [rbp+90h+var_F0]
0x180052f61  lea     edx, [r8+2]
0x180052f65  call    DnsAddWellKnownServerToMap
0x180052f6a  mov     ebx, eax
0x180052f6c  test    eax, eax
0x180052f6e  jnz     short loc_180052F98
0x180052f70  cmp     dword ptr [rsp+190h+var_130+4], esi
0x180052f74  jz      short loc_180052F91
0x180052f76  xor     r9d, r9d
0x180052f79  lea     r8, [rsp+190h+var_120]
0x180052f7e  lea     rcx, [rbp+90h+var_F0]
0x180052f82  lea     edx, [r9+1]
0x180052f86  call    DnsAddWellKnownServerToMap
0x180052f8b  mov     ebx, eax
0x180052f8d  test    eax, eax
0x180052f8f  jnz     short loc_180052FA8
0x180052f91  inc     edi
0x180052f93  jmp     loc_180052E78
0x180052f98  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052f9f  jz      short loc_180052FF8
0x180052fa1  mov     edx, 25h ; '%'
0x180052fa6  jmp     short loc_180052FEA
0x180052fa8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052faf  jz      short loc_180052FF8
0x180052fb1  mov     edx, 26h ; '&'
0x180052fb6  jmp     short loc_180052FEA
0x180052fb8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052fbf  jz      short loc_180052FF8
0x180052fc1  mov     edx, 23h ; '#'
0x180052fc6  jmp     short loc_180052FEA
0x180052fc8  mov     ebx, esi
0x180052fca  jmp     short loc_180052FF8
0x180052fcc  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052fd3  jz      short loc_180052FF8
0x180052fd5  mov     edx, 22h ; '"'
0x180052fda  jmp     short loc_180052FEA
0x180052fdc  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052fe3  jz      short loc_180052FF8
0x180052fe5  mov     edx, 21h ; '!'
0x180052fea  mov     r9d, eax
0x180052fed  mov     r8, r12
0x180052ff0  mov     ecx, r15d
0x180052ff3  call    WPP_SF_d
0x180052ff8  mov     rcx, [rsp+190h+var_120]; void *
0x180052ffd  call    MIDL_user_free
0x180053002  mov     rcx, [rbp+90h+var_110]; void *
0x180053006  mov     [rsp+190h+var_120], rsi
0x18005300b  call    MIDL_user_free
0x180053010  mov     rcx, [rsp+190h+hKey]; hKey
0x180053015  mov     [rbp+90h+var_110], rsi
0x180053019  test    rcx, rcx
0x18005301c  jz      short loc_180053029
0x18005301e  call    cs:__imp_RegCloseKey
0x180053024  mov     [rsp+190h+hKey], rsi
0x180053029  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180053030  jz      short loc_180053045
0x180053032  mov     edx, 27h ; '''
0x180053037  mov     ecx, r15d
0x18005303a  mov     r9d, ebx
0x18005303d  mov     r8, r12
0x180053040  call    WPP_SF_d
0x180053045  mov     eax, ebx
0x180053047  mov     rcx, [rbp+90h+var_40]
0x18005304b  xor     rcx, rsp; StackCookie
0x18005304e  call    __security_check_cookie
0x180053053  add     rsp, 168h
0x18005305a  pop     r15
0x18005305c  pop     r12
0x18005305e  pop     rdi
0x18005305f  pop     rsi
0x180053060  pop     rbx
0x180053061  pop     rbp
0x180053062  retn
```
