# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x18000bc54`
- end: `0x18000be57`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `515`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, char, DWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000b2f8`
- `0x18001b5b4`
- `0x18001f924`
- `0x1800363ac`

## callees

- `0x1800028b4`
- `0x180009e04`
- `0x18000a004`
- `0x18000a074`
- `0x18000aac8`
- `0x18000bc54`
- `0x18000c1a8`

## import_xrefs

- `ntdll!wcsnlen` at `0x18000bdb9`
- `ntdll!wcsnlen` at `0x18000bdb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000be36`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bd4a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bd9f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bd4a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bd9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bcf6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bcf6`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValue,
        __int64 a4,
        __int64 a5,
        char a6,
        DWORD pcbData)
{
  __int64 v7; // rsi
  __int64 v13; // r8
  unsigned int v14; // ebx
  HKEY *phkResult; // rax
  LSTATUS ValueW; // eax
  bool v17; // cc
  HKEY v18; // r14
  size_t v19; // rax
  _WORD *v20; // rcx
  PVOID pvData; // [rsp+40h] [rbp-20h] BYREF
  char *v22; // [rsp+48h] [rbp-18h]
  _WORD v23[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+90h] [rbp+30h] BYREF

  v7 = a5;
  pvData = v23;
  pcbData = 0;
  v22 = (char *)v23;
  hkey = 0;
  v23[0] = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a4 + 2 * v13) );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &pvData,
                             a4) )
      goto LABEL_7;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  ValueW = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult);
  v14 = ValueW;
  if ( ValueW
    || (v18 = hkey, pcbData = 0, ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData), (v14 = ValueW) != 0) )
  {
    if ( a4 )
      goto LABEL_19;
    v17 = ValueW <= 0;
    goto LABEL_11;
  }
  v22 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v18, 0, lpValue, 2u, 0, pvData, &pcbData);
    v14 = ValueW;
    v17 = ValueW <= 0;
    if ( !ValueW )
    {
      v19 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
      if ( v19 > (v22 - (_BYTE *)pvData) >> 1 )
        __int2c();
      v22 = (char *)pvData + 2 * v19;
      *(_WORD *)v22 = 0;
LABEL_19:
      v14 = 0;
      if ( a6 )
        v14 = UtilExpandEnvironmentStrings((LPCWSTR)pvData);
      else
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v7, &pvData);
      if ( !v14 )
        goto LABEL_24;
      goto LABEL_23;
    }
LABEL_11:
    if ( !v17 )
      v14 = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_23;
  }
LABEL_7:
  v14 = -2147024882;
LABEL_23:
  v20 = *(_WORD **)v7;
  *(_QWORD *)(v7 + 8) = *(_QWORD *)v7;
  *v20 = 0;
LABEL_24:
  if ( pvData != v23 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return v14;
}

```

## disassembly

```asm
0x18000bc54  mov     [rsp-28h+arg_8], rbx
0x18000bc59  mov     [rsp-28h+arg_10], rsi
0x18000bc5e  push    rbp
0x18000bc5f  push    rdi
0x18000bc60  push    r12
0x18000bc62  push    r14
0x18000bc64  push    r15
0x18000bc66  mov     rbp, rsp
0x18000bc69  sub     rsp, 60h
0x18000bc6d  mov     rsi, [rbp+arg_20]
0x18000bc71  lea     rax, [rbp+var_10]
0x18000bc75  xor     r12d, r12d
0x18000bc78  mov     [rbp+var_20], rax
0x18000bc7c  mov     [rbp+arg_30], r12d
0x18000bc80  lea     rax, [rbp+var_10]
0x18000bc84  mov     [rbp+var_18], rax
0x18000bc88  mov     rdi, r9
0x18000bc8b  mov     [rbp+hkey], r12
0x18000bc8f  mov     r15, r8
0x18000bc92  mov     [rbp+var_10], r12w
0x18000bc97  mov     rbx, rdx
0x18000bc9a  mov     r14, rcx
0x18000bc9d  test    rsi, rsi
0x18000bca0  jnz     short loc_18000BCAC
0x18000bca2  mov     eax, 80070057h
0x18000bca7  jmp     loc_18000BE3E
0x18000bcac  test    rdi, rdi
0x18000bcaf  jz      short loc_18000BCD9
0x18000bcb1  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000bcb5  inc     r8
0x18000bcb8  cmp     [r9+r8*2], r12w
0x18000bcbd  jnz     short loc_18000BCB5
0x18000bcbf  mov     rdx, rdi
0x18000bcc2  lea     rcx, [rbp+var_20]
0x18000bcc6  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000bccb  test    al, al
0x18000bccd  jnz     short loc_18000BCD9
0x18000bccf  mov     ebx, 8007000Eh
0x18000bcd4  jmp     loc_18000BE09
0x18000bcd9  lea     rcx, [rbp+hkey]
0x18000bcdd  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000bce2  mov     r9d, 101h; samDesired
0x18000bce8  mov     [rsp+60h+phkResult], rax; phkResult
0x18000bced  xor     r8d, r8d; ulOptions
0x18000bcf0  mov     rdx, rbx; lpSubKey
0x18000bcf3  mov     rcx, r14; hKey
0x18000bcf6  call    cs:__imp_RegOpenKeyExW
0x18000bcfc  mov     ebx, eax
0x18000bcfe  test    eax, eax
0x18000bd00  jz      short loc_18000BD21
0x18000bd02  test    rdi, rdi
0x18000bd05  jnz     loc_18000BDE0
0x18000bd0b  test    eax, eax
0x18000bd0d  jle     loc_18000BE09
0x18000bd13  movzx   ebx, ax
0x18000bd16  or      ebx, 80070000h
0x18000bd1c  jmp     loc_18000BE09
0x18000bd21  mov     r14, [rbp+hkey]
0x18000bd25  lea     rax, [rbp+arg_30]
0x18000bd29  mov     [rsp+60h+pcbData], rax; pcbData
0x18000bd2e  mov     r9d, 2; dwFlags
0x18000bd34  mov     [rsp+60h+pvData], r12; pvData
0x18000bd39  mov     r8, r15; lpValue
0x18000bd3c  xor     edx, edx; lpSubKey
0x18000bd3e  mov     [rsp+60h+phkResult], r12; pdwType
0x18000bd43  mov     rcx, r14; hkey
0x18000bd46  mov     [rbp+arg_30], r12d
0x18000bd4a  call    cs:__imp_RegGetValueW
0x18000bd50  mov     ebx, eax
0x18000bd52  test    eax, eax
0x18000bd54  jnz     short loc_18000BD02
0x18000bd56  mov     rcx, [rbp+var_20]
0x18000bd5a  mov     [rbp+var_18], rcx
0x18000bd5e  mov     [rcx], r12w
0x18000bd62  lea     rcx, [rbp+var_20]
0x18000bd66  mov     edx, [rbp+arg_30]
0x18000bd69  shr     rdx, 1
0x18000bd6c  inc     rdx
0x18000bd6f  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18000bd74  test    al, al
0x18000bd76  jz      loc_18000BCCF
0x18000bd7c  lea     rax, [rbp+arg_30]
0x18000bd80  mov     r8, r15; lpValue
0x18000bd83  mov     [rsp+60h+pcbData], rax; pcbData
0x18000bd88  lea     r9d, [rbx+2]; dwFlags
0x18000bd8c  mov     rax, [rbp+var_20]
0x18000bd90  xor     edx, edx; lpSubKey
0x18000bd92  mov     [rsp+60h+pvData], rax; pvData
0x18000bd97  mov     rcx, r14; hkey
0x18000bd9a  mov     [rsp+60h+phkResult], r12; pdwType
0x18000bd9f  call    cs:__imp_RegGetValueW
0x18000bda5  mov     ebx, eax
0x18000bda7  test    eax, eax
0x18000bda9  jnz     loc_18000BD0D
0x18000bdaf  mov     edx, [rbp+arg_30]
0x18000bdb2  mov     rcx, [rbp+var_20]; Source
0x18000bdb6  shr     rdx, 1; MaxCount
0x18000bdb9  call    cs:__imp_wcsnlen
0x18000bdbf  mov     rcx, [rbp+var_18]
0x18000bdc3  mov     rdx, [rbp+var_20]
0x18000bdc7  sub     rcx, rdx
0x18000bdca  sar     rcx, 1
0x18000bdcd  cmp     rax, rcx
0x18000bdd0  jbe     short loc_18000BDD4
0x18000bdd2  int     2Ch; Windows NT - assertion failure
0x18000bdd4  lea     rcx, [rdx+rax*2]
0x18000bdd8  mov     [rbp+var_18], rcx
0x18000bddc  mov     [rcx], r12w
0x18000bde0  mov     ebx, r12d
0x18000bde3  cmp     [rbp+arg_28], r12b
0x18000bde7  jz      short loc_18000BDF9
0x18000bde9  mov     rcx, [rbp+var_20]; lpSrc
0x18000bded  mov     rdx, rsi
0x18000bdf0  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000bdf5  mov     ebx, eax
0x18000bdf7  jmp     short loc_18000BE05
0x18000bdf9  lea     rdx, [rbp+var_20]
0x18000bdfd  mov     rcx, rsi
0x18000be00  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000be05  test    ebx, ebx
0x18000be07  jz      short loc_18000BE14
0x18000be09  mov     rcx, [rsi]
0x18000be0c  mov     [rsi+8], rcx
0x18000be10  mov     [rcx], r12w
0x18000be14  mov     rcx, [rbp+var_20]; void *
0x18000be18  lea     rax, [rbp+var_10]
0x18000be1c  cmp     rcx, rax
0x18000be1f  jz      short loc_18000BE2D
0x18000be21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000be28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000be2d  mov     rcx, [rbp+hkey]; hKey
0x18000be31  test    rcx, rcx
0x18000be34  jz      short loc_18000BE3C
0x18000be36  call    cs:__imp_RegCloseKey
0x18000be3c  mov     eax, ebx
0x18000be3e  lea     r11, [rsp+60h+var_s0]
0x18000be43  mov     rbx, [r11+38h]
0x18000be47  mov     rsi, [r11+40h]
0x18000be4b  mov     rsp, r11
0x18000be4e  pop     r15
0x18000be50  pop     r14
0x18000be52  pop     r12
0x18000be54  pop     rdi
0x18000be55  pop     rbp
0x18000be56  retn
```
