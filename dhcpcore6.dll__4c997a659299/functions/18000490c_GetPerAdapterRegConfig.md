# GetPerAdapterRegConfig

- ea: `0x18000490c`
- end: `0x180004a83`
- name: `GetPerAdapterRegConfig`
- size: `375`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, STRSAFE_LPCWSTR pszSrc@<rdx>, LPDWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003304`
- `0x1800058ec`

## callees

- `0x18000163c`
- `0x18000490c`
- `0x180004a8c`
- `0x180004c3c`
- `0x180004d00`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004a6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004a6e`
- `DNSAPI!DnsQueryConfigDword` at `0x18000496b`
- `DNSAPI!DnsQueryConfigDword` at `0x18000496b`

## pseudocode

```c
__int64 __fastcall GetPerAdapterRegConfig(HKEY hKey, STRSAFE_LPCWSTR pszSrc, unsigned int *a3, BYTE *a4, LPDWORD a5)
{
  unsigned int Value; // ebx
  int v10; // esi
  unsigned int ConfigDword; // eax
  __int64 v12; // rcx
  unsigned int v13; // edi
  size_t v15; // rdx
  STRSAFE_LPWSTR *v16; // r9
  size_t *pcchRemaining; // [rsp+20h] [rbp-1A8h]
  DWORD lpcbData; // [rsp+28h] [rbp-1A0h]
  _DWORD v19[40]; // [rsp+30h] [rbp-198h] BYREF
  wchar_t pszDest[80]; // [rsp+D0h] [rbp-F8h] BYREF

  Value = 0;
  memset_0(v19, 0, 0x140u);
  if ( !a4 || (v10 = 1, !a5) )
    v10 = 0;
  ConfigDword = DnsQueryConfigDword(10, pszSrc);
  v12 = 0;
  v13 = ConfigDword;
  if ( !ConfigDword )
    goto LABEL_4;
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_SD(1025, 11, (unsigned int)WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, (_DWORD)pszSrc, ConfigDword);
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(v12, ErrorQueryingDNS, pszSrc, v13);
  InitializeTraceElementFromContext(v19, 0, v13, 42);
  StringCchCopyExW(pszDest, v15, pszSrc, v16, pcchRemaining, lpcbData);
  TraceLogEx(v19);
  if ( v13 == 1 )
  {
    if ( !v10 )
      goto LABEL_8;
    Value = RegQueryValueExW(hKey, L"Domain", 0, 0, a4, a5);
  }
  else
  {
LABEL_4:
    if ( !v10 )
      goto LABEL_8;
  }
  if ( !Value && !*(_WORD *)a4 )
    Value = 1012;
LABEL_8:
  *a3 = v13;
  return Value;
}

```

## disassembly

```asm
0x18000490c  push    rbx
0x18000490e  push    rbp
0x18000490f  push    rsi
0x180004910  push    rdi
0x180004911  push    r12
0x180004913  push    r13
0x180004915  push    r14
0x180004917  push    r15
0x180004919  sub     rsp, 188h
0x180004920  mov     rax, cs:__security_cookie
0x180004927  xor     rax, rsp
0x18000492a  mov     [rsp+1C8h+var_58], rax
0x180004932  mov     r15, [rsp+1C8h+arg_20]
0x18000493a  mov     r12, r8
0x18000493d  mov     rbp, rdx
0x180004940  mov     r13, rcx
0x180004943  xor     edi, edi
0x180004945  lea     rcx, [rsp+1C8h+var_198]; void *
0x18000494a  xor     edx, edx; Val
0x18000494c  mov     r8d, 140h; Size
0x180004952  mov     ebx, edi
0x180004954  mov     r14, r9
0x180004957  call    memset_0
0x18000495c  test    r14, r14
0x18000495f  jnz     short loc_1800049C2
0x180004961  mov     esi, edi
0x180004963  mov     rdx, rbp
0x180004966  mov     ecx, 0Ah
0x18000496b  call    cs:__imp_DnsQueryConfigDword
0x180004972  nop     dword ptr [rax+rax+00h]
0x180004977  xor     ecx, ecx
0x180004979  mov     edi, eax
0x18000497b  test    eax, eax
0x18000497d  jnz     loc_180004A09
0x180004983  test    esi, esi
0x180004985  jz      short loc_180004997
0x180004987  test    ebx, ebx
0x180004989  jnz     short loc_180004997
0x18000498b  cmp     [r14], cx
0x18000498f  mov     eax, 3F4h
0x180004994  cmovz   ebx, eax
0x180004997  mov     [r12], edi
0x18000499b  mov     eax, ebx
0x18000499d  mov     rcx, [rsp+1C8h+var_58]
0x1800049a5  xor     rcx, rsp; StackCookie
0x1800049a8  call    __security_check_cookie
0x1800049ad  add     rsp, 188h
0x1800049b4  pop     r15
0x1800049b6  pop     r14
0x1800049b8  pop     r13
0x1800049ba  pop     r12
0x1800049bc  pop     rdi
0x1800049bd  pop     rsi
0x1800049be  pop     rbp
0x1800049bf  pop     rbx
0x1800049c0  retn
0x1800049c2  mov     esi, 1
0x1800049c7  test    r15, r15
0x1800049ca  jnz     short loc_180004963
0x1800049cc  jmp     short loc_180004961
0x1800049ce  mov     r9d, 2Ah ; '*'
0x1800049d4  lea     rcx, [rsp+1C8h+var_198]
0x1800049d9  mov     r8d, edi
0x1800049dc  xor     edx, edx
0x1800049de  call    InitializeTraceElementFromContext
0x1800049e3  mov     r8, rbp; pszSrc
0x1800049e6  lea     rcx, [rsp+1C8h+pszDest]; pszDest
0x1800049ee  call    StringCchCopyExW
0x1800049f3  lea     rcx, [rsp+1C8h+var_198]
0x1800049f8  call    TraceLogEx
0x1800049fd  cmp     edi, 1
0x180004a00  jz      short loc_180004A4C
0x180004a02  xor     ecx, ecx
0x180004a04  jmp     loc_180004983
0x180004a09  test    byte ptr cs:xmmword_1800423E0, 2
0x180004a10  jz      short loc_180004A2F
0x180004a12  mov     edx, 0Bh
0x180004a17  mov     dword ptr [rsp+1C8h+pcchRemaining], edi; pcchRemaining
0x180004a1b  mov     ecx, 401h
0x180004a20  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180004a27  mov     r9, rbp
0x180004a2a  call    WPP_SF_SD
0x180004a2f  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180004a36  jz      short loc_1800049CE
0x180004a38  mov     r9d, edi
0x180004a3b  lea     rdx, ErrorQueryingDNS
0x180004a42  mov     r8, rbp
0x180004a45  call    McTemplateU0zq_EtwEventWriteTransfer
0x180004a4a  jmp     short loc_1800049CE
0x180004a4c  test    esi, esi
0x180004a4e  jz      loc_180004997
0x180004a54  mov     [rsp+1C8h+lpcbData], r15; lpcbData
0x180004a59  lea     rdx, ValueName; "Domain"
0x180004a60  xor     r9d, r9d; lpType
0x180004a63  mov     [rsp+1C8h+pcchRemaining], r14; lpData
0x180004a68  xor     r8d, r8d; lpReserved
0x180004a6b  mov     rcx, r13; hKey
0x180004a6e  call    cs:__imp_RegQueryValueExW
0x180004a75  nop     dword ptr [rax+rax+00h]
0x180004a7a  mov     ebx, eax
0x180004a7c  xor     ecx, ecx
0x180004a7e  jmp     loc_180004987
```
