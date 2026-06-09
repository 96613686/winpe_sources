# DhcpDynDnsRegisterDhcpOrRasAdapter

- ea: `0x180003ea0`
- end: `0x18000411e`
- name: `DhcpDynDnsRegisterDhcpOrRasAdapter`
- size: `638`
- prototype: `__int64 __fastcall(HKEY hKey, int *, __int64, unsigned int, unsigned int, wchar_t *S2, rsize_t, void *Src, size_t, _BYTE *, int, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800095d8`

## callees

- `0x180003ea0`
- `0x180004124`
- `0x1800042b8`
- `0x1800057f0`
- `0x180005da4`
- `0x180007294`
- `0x1800083b8`
- `0x18001cef0`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d310`

## import_xrefs

- `DNSAPI!DnsNotifyResolver` at `0x180003f04`
- `DNSAPI!DnsNotifyResolver` at `0x180003f04`
- `DNSAPI!DnsQueryConfigDword` at `0x180003f45`
- `DNSAPI!DnsQueryConfigDword` at `0x180003f45`
- `WS2_32!__imp_inet_addr` at `0x1800040e5`
- `WS2_32!__imp_inet_addr` at `0x1800040e5`

## pseudocode

```c
__int64 __fastcall DhcpDynDnsRegisterDhcpOrRasAdapter(
        HKEY hKey,
        int *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        wchar_t *S2,
        rsize_t a7,
        void *Src,
        size_t a9,
        _BYTE *a10,
        int a11,
        _DWORD *a12)
{
  int v13; // edi
  __int64 v17; // rcx
  unsigned int RegistryString; // eax
  unsigned int v20; // edi
  rsize_t N; // [rsp+30h] [rbp-C9h]
  size_t Size; // [rsp+40h] [rbp-B9h]
  PCWSTR SourceString; // [rsp+58h] [rbp-A1h] BYREF
  __int128 v24; // [rsp+60h] [rbp-99h]
  __int64 v25; // [rsp+70h] [rbp-89h]
  char cp[112]; // [rsp+80h] [rbp-79h] BYREF

  v13 = DhcpGlobalUseMHAsyncDns;
  v25 = 0;
  v24 = 0;
  if ( !a4 )
    DnsNotifyResolver(0, 0);
  if ( !v13 )
    goto LABEL_4;
  if ( !(unsigned int)DnsQueryConfigDword(65552, a2) )
  {
    *a12 = 32;
    return DhcpDynDnsDeregisterAdapter(v17, a2, a4, v13);
  }
  if ( a4 )
  {
    SourceString = 0;
    RegistryString = GetRegistryString(hKey, L"DhcpIPAddress", &SourceString, 0);
    v20 = RegistryString;
    if ( RegistryString )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_SD(1025, 30, (unsigned int)WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, (_DWORD)a2, RegistryString);
      return v20;
    }
    if ( !DhcpUnicodeToOem(SourceString) )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_S(1025, 31, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, SourceString);
      DhcpPunycodeFree(&SourceString);
      return 13;
    }
    DhcpPunycodeFree(&SourceString);
    a5 = inet_addr(cp);
  }
  LODWORD(v24) = a5;
  LODWORD(v25) = 1;
  *a12 = 0;
  if ( a4 )
    *a12 = 24;
  GetPerAdapterRegConfig(hKey, 0);
  if ( a11 && *a10 == 3 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 33, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids);
LABEL_4:
    *a12 = 64;
    return 0;
  }
  LODWORD(Size) = a9;
  LODWORD(N) = a7;
  return DhcpDynDnsRegisterAdapterCheckingForStatic(hKey, (__int64)a12, S2, N, Src, Size, 0);
}

```

## disassembly

```asm
0x180003ea0  mov     [rsp-8+arg_10], rbx
0x180003ea5  push    rbp
0x180003ea6  push    rsi
0x180003ea7  push    rdi
0x180003ea8  push    r12
0x180003eaa  push    r13
0x180003eac  push    r14
0x180003eae  push    r15
0x180003eb0  lea     rbp, [rsp-7]
0x180003eb5  sub     rsp, 100h
0x180003ebc  mov     rax, cs:__security_cookie
0x180003ec3  xor     rax, rsp
0x180003ec6  mov     [rbp+37h+var_40], rax
0x180003eca  mov     r12, [rbp+37h+arg_28]
0x180003ece  xor     eax, eax
0x180003ed0  mov     r13, [rbp+37h+arg_38]
0x180003ed4  xorps   xmm0, xmm0
0x180003ed7  mov     rbx, [rbp+37h+arg_58]
0x180003ede  mov     esi, r9d
0x180003ee1  mov     edi, cs:DhcpGlobalUseMHAsyncDns
0x180003ee7  mov     r14, rdx
0x180003eea  mov     [rsp+130h+var_C0], rax
0x180003eef  mov     r15, rcx
0x180003ef2  mov     [rsp+130h+var_E0], eax
0x180003ef6  movups  [rsp+130h+var_D0], xmm0
0x180003efb  test    r9d, r9d
0x180003efe  jnz     short loc_180003F0A
0x180003f00  xor     edx, edx
0x180003f02  xor     ecx, ecx
0x180003f04  call    cs:__imp_DnsNotifyResolver
0x180003f0a  test    edi, edi
0x180003f0c  jnz     short loc_180003F3D
0x180003f0e  mov     dword ptr [rbx], 40h ; '@'
0x180003f14  xor     eax, eax
0x180003f16  mov     rcx, [rbp+37h+var_40]
0x180003f1a  xor     rcx, rsp; StackCookie
0x180003f1d  call    __security_check_cookie
0x180003f22  mov     rbx, [rsp+130h+arg_10]
0x180003f2a  add     rsp, 100h
0x180003f31  pop     r15
0x180003f33  pop     r14
0x180003f35  pop     r13
0x180003f37  pop     r12
0x180003f39  pop     rdi
0x180003f3a  pop     rsi
0x180003f3b  pop     rbp
0x180003f3c  retn
0x180003f3d  mov     rdx, r14
0x180003f40  mov     ecx, 10010h
0x180003f45  call    cs:__imp_DnsQueryConfigDword
0x180003f4b  test    eax, eax
0x180003f4d  jz      loc_180004022
0x180003f53  test    esi, esi
0x180003f55  jnz     loc_18000403B
0x180003f5b  mov     eax, [rbp+37h+arg_20]
0x180003f5e  mov     dword ptr [rsp+130h+var_D0], eax
0x180003f62  mov     edi, 1
0x180003f67  mov     dword ptr [rsp+130h+var_C0], edi
0x180003f6b  mov     dword ptr [rbx], 0
0x180003f71  test    esi, esi
0x180003f73  jz      short loc_180003F7B
0x180003f75  mov     dword ptr [rbx], 18h
0x180003f7b  xor     r9d, r9d
0x180003f7e  mov     [rsp+130h+var_110], 0; LPDWORD
0x180003f87  lea     r8, [rsp+130h+var_E0]
0x180003f8c  mov     rdx, r14
0x180003f8f  mov     rcx, r15; hKey
0x180003f92  call    GetPerAdapterRegConfig
0x180003f97  mov     edx, [rsp+130h+var_E0]
0x180003f9b  test    edx, edx
0x180003f9d  jnz     loc_1800040F0
0x180003fa3  xor     ecx, ecx
0x180003fa5  cmp     [rbp+37h+arg_50], ecx
0x180003fab  ja      short loc_180003FE6
0x180003fad  mov     eax, dword ptr [rbp+37h+arg_40]
0x180003fb3  lea     r8, [rsp+130h+var_D0]
0x180003fb8  mov     [rsp+130h+var_E8], ecx; int
0x180003fbc  mov     rdx, r14
0x180003fbf  mov     dword ptr [rsp+130h+Size], eax; Size
0x180003fc3  mov     rcx, r15; hKey
0x180003fc6  mov     eax, dword ptr [rbp+37h+arg_30]
0x180003fc9  mov     [rsp+130h+Src], r13; Src
0x180003fce  mov     dword ptr [rsp+130h+N], eax; N
0x180003fd2  mov     [rsp+130h+S2], r12; S2
0x180003fd7  mov     [rsp+130h+var_110], rbx; __int64
0x180003fdc  call    DhcpDynDnsRegisterAdapterCheckingForStatic
0x180003fe1  jmp     loc_180003F16
0x180003fe6  mov     rax, [rbp+37h+arg_48]
0x180003fed  cmp     byte ptr [rax], 3
0x180003ff0  jnz     short loc_180003FAD
0x180003ff2  test    edx, edx
0x180003ff4  jnz     loc_1800040F8
0x180003ffa  test    byte ptr cs:xmmword_1800616A0, 10h
0x180004001  jz      loc_180003F0E
0x180004007  mov     edx, 21h ; '!'
0x18000400c  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180004013  mov     ecx, 404h
0x180004018  call    WPP_SF_
0x18000401d  jmp     loc_180003F0E
0x180004022  mov     r9d, edi
0x180004025  mov     dword ptr [rbx], 20h ; ' '
0x18000402b  mov     r8d, esi
0x18000402e  mov     rdx, r14
0x180004031  call    DhcpDynDnsDeregisterAdapter
0x180004036  jmp     loc_180003F16
0x18000403b  xor     r9d, r9d
0x18000403e  mov     [rsp+130h+SourceString], 0
0x180004047  lea     r8, [rsp+130h+SourceString]
0x18000404c  mov     rcx, r15; hKey
0x18000404f  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x180004056  call    GetRegistryString
0x18000405b  mov     edi, eax
0x18000405d  test    eax, eax
0x18000405f  jz      short loc_18000408E
0x180004061  test    byte ptr cs:xmmword_1800616A0, 2
0x180004068  jz      short loc_180004087
0x18000406a  mov     edx, 1Eh
0x18000406f  mov     dword ptr [rsp+130h+var_110], eax
0x180004073  mov     ecx, 401h
0x180004078  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x18000407f  mov     r9, r14
0x180004082  call    WPP_SF_SD
0x180004087  mov     eax, edi
0x180004089  jmp     loc_180003F16
0x18000408e  mov     rcx, [rsp+130h+SourceString]; SourceString
0x180004093  lea     rdx, [rbp+37h+cp]
0x180004097  call    DhcpUnicodeToOem
0x18000409c  test    rax, rax
0x18000409f  jnz     short loc_1800040D7
0x1800040a1  test    byte ptr cs:xmmword_1800616A0, 2
0x1800040a8  jz      short loc_1800040C3
0x1800040aa  mov     r9, [rsp+130h+SourceString]
0x1800040af  lea     edx, [rax+1Fh]
0x1800040b2  mov     ecx, 401h
0x1800040b7  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x1800040be  call    WPP_SF_S
0x1800040c3  lea     rcx, [rsp+130h+SourceString]
0x1800040c8  call    DhcpPunycodeFree
0x1800040cd  mov     eax, 0Dh
0x1800040d2  jmp     loc_180003F16
0x1800040d7  lea     rcx, [rsp+130h+SourceString]
0x1800040dc  call    DhcpPunycodeFree
0x1800040e1  lea     rcx, [rbp+37h+cp]; cp
0x1800040e5  call    cs:__imp_inet_addr
0x1800040eb  jmp     loc_180003F5E
0x1800040f0  or      dword ptr [rbx], 8
0x1800040f3  jmp     loc_180003FA3
0x1800040f8  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800040ff  jz      short loc_180004117
0x180004101  mov     edx, 20h ; ' '
0x180004106  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x18000410d  mov     ecx, 404h
0x180004112  call    WPP_SF_
0x180004117  mov     ecx, edi
0x180004119  jmp     loc_180003FAD
```
