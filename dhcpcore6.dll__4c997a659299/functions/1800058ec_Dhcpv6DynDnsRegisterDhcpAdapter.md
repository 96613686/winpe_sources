# Dhcpv6DynDnsRegisterDhcpAdapter

- ea: `0x1800058ec`
- end: `0x180005b80`
- name: `Dhcpv6DynDnsRegisterDhcpAdapter`
- size: `660`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, __int64, unsigned int, _BYTE *, unsigned int, void *, int, _BYTE *, int, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180010fd4`

## callees

- `0x18000490c`
- `0x180004d78`
- `0x1800058ec`
- `0x180005b88`
- `0x180006904`
- `0x180007564`
- `0x180007a80`
- `0x180019ad0`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005aa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005aa2`
- `DNSAPI!DnsQueryConfigDword` at `0x1800059a4`
- `DNSAPI!DnsQueryConfigDword` at `0x1800059a4`

## pseudocode

```c
__int64 __fastcall Dhcpv6DynDnsRegisterDhcpAdapter(
        HKEY a1,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        _BYTE *a6,
        unsigned int a7,
        void *a8,
        int a9,
        _BYTE *a10,
        int a11,
        int *a12)
{
  unsigned int v14; // ebx
  __int64 v16; // r9
  const wchar_t *v17; // rdi
  __int64 v18; // rbx
  _DWORD *v19; // rsi
  unsigned int v20; // r8d
  int v21; // ecx
  unsigned int v22; // ebx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  const wchar_t *v27; // rbx
  size_t Size; // [rsp+40h] [rbp-C0h]
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+54h] [rbp-ACh]
  HKEY hKey; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  void *Src; // [rsp+68h] [rbp-98h]
  _WORD v34[256]; // [rsp+70h] [rbp-90h] BYREF

  v14 = Dhcpv6GlobalUseMHAsyncDns;
  Src = a8;
  v32 = a4;
  hKey = a1;
  v30 = 0;
  v29 = 0;
  NotifyDnsCache();
  if ( !v14 )
    return 0;
  if ( !(unsigned int)DnsQueryConfigDword(65552, a2) )
    return Dhcpv6DynDnsDeregisterAdapter(a2, v14, a4, a5);
  if ( (unsigned int)DhcpGetUnicodeNameFromWireName(a6, a7, v34, v16, &v29) )
  {
    v17 = 0;
    LODWORD(v18) = 0;
  }
  else
  {
    v17 = v34;
    v27 = &v34[v29];
    if ( v27 > v34 )
    {
      do
      {
        if ( *v17 == 46 )
          break;
        ++v17;
      }
      while ( v27 > v17 );
    }
    v18 = v27 - v17;
  }
  v19 = (_DWORD *)DhcpAlloc(24LL * a5);
  if ( !v19 )
    return 8;
  v20 = 0;
  if ( a5 )
  {
    v23 = v32;
    v24 = 0;
    do
    {
      v25 = 3 * v24;
      v19[6 * v24 + 4] = 8;
      if ( !a11 )
        v19[6 * v24 + 4] = 10;
      ++v20;
      v26 = 2 * v24++;
      *(_OWORD *)&v19[2 * v25] = *(_OWORD *)(v23 + 8 * v26);
    }
    while ( v20 < a5 );
  }
  v21 = 8;
  if ( a11 )
    v21 = 0;
  *a12 = v21;
  GetPerAdapterRegConfig(hKey, a2, 0);
  if ( v30 )
    *a12 |= 8u;
  if ( a11 && *a10 == 3 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 31, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids);
    *a12 = 64;
    v22 = 0;
  }
  else
  {
    LODWORD(Size) = a9;
    v22 = Dhcpv6DynDnsRegisterAdapterCheckingForStatic(hKey, a2, (__int64)a12, v17, v18, Src, Size);
  }
  HeapFree(NtCurrentPeb()->ProcessHeap, 0, v19);
  return v22;
}

```

## disassembly

```asm
0x1800058ec  mov     [rsp-8+arg_10], rbx
0x1800058f1  mov     [rsp-8+arg_18], rsi
0x1800058f6  push    rbp
0x1800058f7  push    rdi
0x1800058f8  push    r13
0x1800058fa  push    r14
0x1800058fc  push    r15
0x1800058fe  lea     rbp, [rsp-180h]
0x180005906  sub     rsp, 280h
0x18000590d  mov     rax, cs:__security_cookie
0x180005914  xor     rax, rsp
0x180005917  mov     [rbp+1A0h+var_30], rax
0x18000591e  mov     rax, [rbp+1A0h+arg_38]
0x180005925  mov     rsi, r9
0x180005928  mov     r15d, [rbp+1A0h+arg_20]
0x18000592f  mov     r13, rdx
0x180005932  mov     rdi, [rbp+1A0h+arg_28]
0x180005939  mov     r14, [rbp+1A0h+arg_58]
0x180005940  mov     ebx, cs:Dhcpv6GlobalUseMHAsyncDns
0x180005946  mov     [rsp+2A0h+var_238], rax
0x18000594b  mov     [rsp+2A0h+var_240], r9
0x180005950  mov     [rsp+2A0h+hKey], rcx
0x180005955  mov     [rsp+2A0h+var_24C], 0
0x18000595d  mov     [rsp+2A0h+var_250], 0
0x180005965  call    NotifyDnsCache
0x18000596a  test    ebx, ebx
0x18000596c  jnz     short loc_18000599C
0x18000596e  xor     eax, eax
0x180005970  mov     rcx, [rbp+1A0h+var_30]
0x180005977  xor     rcx, rsp; StackCookie
0x18000597a  call    __security_check_cookie
0x18000597f  lea     r11, [rsp+2A0h+var_20]
0x180005987  mov     rbx, [r11+40h]
0x18000598b  mov     rsi, [r11+48h]
0x18000598f  mov     rsp, r11
0x180005992  pop     r15
0x180005994  pop     r14
0x180005996  pop     r13
0x180005998  pop     rdi
0x180005999  pop     rbp
0x18000599a  retn
0x18000599c  mov     rdx, r13
0x18000599f  mov     ecx, 10010h
0x1800059a4  call    cs:__imp_DnsQueryConfigDword
0x1800059ab  nop     dword ptr [rax+rax+00h]
0x1800059b0  test    eax, eax
0x1800059b2  jnz     short loc_1800059C6
0x1800059b4  mov     r9d, r15d
0x1800059b7  mov     r8, rsi
0x1800059ba  mov     edx, ebx
0x1800059bc  mov     rcx, r13
0x1800059bf  call    Dhcpv6DynDnsDeregisterAdapter
0x1800059c4  jmp     short loc_180005970
0x1800059c6  mov     edx, [rbp+1A0h+arg_30]
0x1800059cc  lea     rax, [rsp+2A0h+var_250]
0x1800059d1  lea     r8, [rsp+2A0h+var_230]
0x1800059d6  mov     [rsp+2A0h+var_280], rax
0x1800059db  mov     rcx, rdi
0x1800059de  call    DhcpGetUnicodeNameFromWireName
0x1800059e3  test    eax, eax
0x1800059e5  jz      loc_180005B41
0x1800059eb  xor     edi, edi
0x1800059ed  xor     ebx, ebx
0x1800059ef  lea     rcx, [r15+r15*2]
0x1800059f3  shl     rcx, 3
0x1800059f7  call    DhcpAlloc
0x1800059fc  mov     rsi, rax
0x1800059ff  test    rax, rax
0x180005a02  jz      loc_180005B37
0x180005a08  xor     r8d, r8d
0x180005a0b  test    r15d, r15d
0x180005a0e  jnz     loc_180005AB5
0x180005a14  xor     eax, eax
0x180005a16  lea     r8, [rsp+2A0h+var_24C]
0x180005a1b  cmp     [rbp+1A0h+arg_50], eax
0x180005a21  mov     ecx, 8
0x180005a26  mov     rdx, r13; pszSrc
0x180005a29  mov     [rsp+2A0h+var_280], rax; LPDWORD
0x180005a2e  cmovnz  ecx, eax
0x180005a31  xor     r9d, r9d
0x180005a34  mov     [r14], ecx
0x180005a37  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180005a3c  call    GetPerAdapterRegConfig
0x180005a41  cmp     [rsp+2A0h+var_24C], 0
0x180005a46  jnz     loc_180005B77
0x180005a4c  cmp     [rbp+1A0h+arg_50], 0
0x180005a53  ja      loc_180005AFA
0x180005a59  mov     eax, dword ptr [rbp+1A0h+arg_40]
0x180005a5f  mov     r9d, r15d
0x180005a62  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180005a67  mov     r8, rsi
0x180005a6a  mov     dword ptr [rsp+2A0h+Size], eax; Size
0x180005a6e  mov     rdx, r13; pszSrc
0x180005a71  mov     rax, [rsp+2A0h+var_238]
0x180005a76  mov     [rsp+2A0h+Src], rax; Src
0x180005a7b  mov     [rsp+2A0h+var_270], ebx; int
0x180005a7f  mov     [rsp+2A0h+var_278], rdi; STRSAFE_LPCWSTR
0x180005a84  mov     [rsp+2A0h+var_280], r14; __int64
0x180005a89  call    Dhcpv6DynDnsRegisterAdapterCheckingForStatic
0x180005a8e  mov     ebx, eax
0x180005a90  mov     rcx, gs:60h
0x180005a99  mov     r8, rsi; lpMem
0x180005a9c  xor     edx, edx; dwFlags
0x180005a9e  mov     rcx, [rcx+30h]; hHeap
0x180005aa2  call    cs:__imp_HeapFree
0x180005aa9  nop     dword ptr [rax+rax+00h]
0x180005aae  mov     eax, ebx
0x180005ab0  jmp     loc_180005970
0x180005ab5  mov     r9, [rsp+2A0h+var_240]
0x180005aba  xor     ecx, ecx
0x180005abc  cmp     [rbp+1A0h+arg_50], 0
0x180005ac3  lea     rdx, [rcx+rcx*2]
0x180005ac7  mov     dword ptr [rsi+rdx*8+10h], 8
0x180005acf  jnz     short loc_180005AD9
0x180005ad1  mov     dword ptr [rsi+rdx*8+10h], 0Ah
0x180005ad9  mov     rax, rcx
0x180005adc  inc     r8d
0x180005adf  add     rax, rax
0x180005ae2  inc     rcx
0x180005ae5  movups  xmm0, xmmword ptr [r9+rax*8]
0x180005aea  movdqu  xmmword ptr [rsi+rdx*8], xmm0
0x180005aef  cmp     r8d, r15d
0x180005af2  jnb     loc_180005A14
0x180005af8  jmp     short loc_180005ABC
0x180005afa  mov     rax, [rbp+1A0h+arg_48]
0x180005b01  cmp     byte ptr [rax], 3
0x180005b04  jnz     loc_180005A59
0x180005b0a  test    byte ptr cs:xmmword_1800423E0, 10h
0x180005b11  jz      short loc_180005B29
0x180005b13  mov     edx, 1Fh
0x180005b18  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180005b1f  mov     ecx, 404h
0x180005b24  call    WPP_SF_
0x180005b29  mov     dword ptr [r14], 40h ; '@'
0x180005b30  xor     ebx, ebx
0x180005b32  jmp     loc_180005A90
0x180005b37  mov     eax, 8
0x180005b3c  jmp     loc_180005970
0x180005b41  mov     eax, [rsp+2A0h+var_250]
0x180005b45  lea     rbx, [rsp+2A0h+var_230]
0x180005b4a  lea     rdi, [rsp+2A0h+var_230]
0x180005b4f  lea     rbx, [rbx+rax*2]
0x180005b53  lea     rax, [rsp+2A0h+var_230]
0x180005b58  cmp     rbx, rax
0x180005b5b  jbe     short loc_180005B6C
0x180005b5d  cmp     word ptr [rdi], 2Eh ; '.'
0x180005b61  jz      short loc_180005B6C
0x180005b63  add     rdi, 2
0x180005b67  cmp     rbx, rdi
0x180005b6a  ja      short loc_180005B5D
0x180005b6c  sub     rbx, rdi
0x180005b6f  sar     rbx, 1
0x180005b72  jmp     loc_1800059EF
0x180005b77  or      dword ptr [r14], 8
0x180005b7b  jmp     loc_180005A4C
```
