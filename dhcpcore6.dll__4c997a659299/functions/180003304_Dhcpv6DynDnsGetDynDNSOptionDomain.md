# Dhcpv6DynDnsGetDynDNSOptionDomain

- ea: `0x180003304`
- end: `0x1800034c2`
- name: `Dhcpv6DynDnsGetDynDNSOptionDomain`
- size: `446`
- prototype: `__int64 __fastcall(void *, unsigned int *, HKEY, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003100`

## callees

- `0x180003304`
- `0x18000490c`
- `0x1800077e0`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800304d4`
- `0x18003098c`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800033ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800033ea`

## pseudocode

```c
__int64 __fastcall Dhcpv6DynDnsGetDynDNSOptionDomain(void *a1, unsigned int *a2, HKEY a3, const wchar_t *a4)
{
  size_t v8; // rdx
  DWORD LastError; // ebx
  HRESULT v10; // eax
  int v11; // edi
  unsigned int v12; // edi
  size_t pcchLength; // [rsp+38h] [rbp-C8h] BYREF
  DWORD nSize[4]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t psz[256]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(psz, 0, 0x1FEu);
  nSize[0] = 510;
  GetPerAdapterRegConfig(a3, a4, nSize);
  nSize[0] = 255;
  if ( GetComputerNameExW(ComputerNameDnsDomain, psz, nSize) || (LastError = GetLastError()) == 0 )
  {
    pcchLength = 0;
    v10 = StringCchLengthW(psz, v8, &pcchLength);
    if ( v10 >= 0 )
    {
      v11 = pcchLength;
    }
    else
    {
      HIDWORD(pcchLength) = 81;
      v11 = 0;
    }
    LastError = WX_WIN32_FROM_HR((unsigned int)v10);
    if ( !LastError )
    {
      if ( !psz[0] )
      {
        *a2 = 0;
        return LastError;
      }
      v12 = 2 * v11;
      if ( v12 <= *a2 )
      {
        *a2 = v12;
        memcpy_0(a1, psz, v12);
        return LastError;
      }
      LastError = 122;
    }
  }
  if ( (BYTE1(xmmword_1800423E0) & 0x20) != 0 )
    WPP_SF_D(1037, 32, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180003304  push    rbp
0x180003306  push    rbx
0x180003307  push    rsi
0x180003308  push    rdi
0x180003309  push    r12
0x18000330b  push    r14
0x18000330d  push    r15
0x18000330f  lea     rbp, [rsp-160h]
0x180003317  sub     rsp, 260h
0x18000331e  mov     rax, cs:__security_cookie
0x180003325  xor     rax, rsp
0x180003328  mov     [rbp+190h+var_40], rax
0x18000332f  mov     rbx, r8
0x180003332  mov     r14, rdx
0x180003335  mov     r15, rcx
0x180003338  mov     esi, 1FEh
0x18000333d  mov     r8d, esi; Size
0x180003340  lea     rcx, [rsp+290h+psz]; void *
0x180003345  xor     edx, edx; Val
0x180003347  mov     rdi, r9
0x18000334a  call    memset_0
0x18000334f  lea     rax, [rsp+290h+nSize]
0x180003354  mov     [rsp+290h+nSize], esi
0x180003358  xor     r12d, r12d
0x18000335b  mov     [rsp+290h+var_270], rax; LPDWORD
0x180003360  lea     r9, [rsp+290h+psz]
0x180003365  mov     [rsp+290h+var_260], r12d
0x18000336a  lea     r8, [rsp+290h+var_260]
0x18000336f  mov     rdx, rdi; pszSrc
0x180003372  mov     rcx, rbx; hKey
0x180003375  call    GetPerAdapterRegConfig
0x18000337a  cmp     [rsp+290h+var_260], r12d
0x18000337f  jz      short loc_1800033D3
0x180003381  test    eax, eax
0x180003383  jnz     short loc_1800033D3
0x180003385  mov     dword ptr [rsp+290h+pcchLength+4], r12d
0x18000338a  lea     r8, [rsp+290h+pcchLength]; pcchLength
0x18000338f  lea     rcx, [rsp+290h+psz]; psz
0x180003394  mov     [rsp+290h+pcchLength], r12
0x180003399  mov     [rsp+290h+var_260], r12d
0x18000339e  call    StringCchLengthW
0x1800033a3  test    eax, eax
0x1800033a5  jns     short loc_1800033B4
0x1800033a7  mov     dword ptr [rsp+290h+pcchLength+4], 51h ; 'Q'
0x1800033af  mov     edi, r12d
0x1800033b2  jmp     short loc_1800033B8
0x1800033b4  mov     edi, dword ptr [rsp+290h+pcchLength]
0x1800033b8  mov     ecx, eax
0x1800033ba  call    WX_WIN32_FROM_HR
0x1800033bf  mov     ebx, eax
0x1800033c1  test    eax, eax
0x1800033c3  jnz     loc_180003465
0x1800033c9  lea     rsi, [rsp+290h+psz]
0x1800033ce  mov     ebx, r12d
0x1800033d1  jmp     short loc_180003451
0x1800033d3  lea     r8, [rsp+290h+nSize]; nSize
0x1800033d8  mov     [rsp+290h+nSize], 0FFh
0x1800033e0  lea     rdx, [rsp+290h+psz]; lpBuffer
0x1800033e5  mov     ecx, 2; NameType
0x1800033ea  call    cs:__imp_GetComputerNameExW
0x1800033f1  nop     dword ptr [rax+rax+00h]
0x1800033f6  test    eax, eax
0x1800033f8  jnz     short loc_18000340C
0x1800033fa  call    cs:__imp_GetLastError
0x180003401  nop     dword ptr [rax+rax+00h]
0x180003406  mov     ebx, eax
0x180003408  test    eax, eax
0x18000340a  jnz     short loc_180003465
0x18000340c  mov     dword ptr [rsp+290h+pcchLength+4], r12d
0x180003411  lea     r8, [rsp+290h+pcchLength]; pcchLength
0x180003416  lea     rcx, [rsp+290h+psz]; psz
0x18000341b  mov     [rsp+290h+pcchLength], r12
0x180003420  mov     [rsp+290h+var_260], r12d
0x180003425  lea     rsi, [rsp+290h+psz]
0x18000342a  call    StringCchLengthW
0x18000342f  test    eax, eax
0x180003431  jns     short loc_180003440
0x180003433  mov     dword ptr [rsp+290h+pcchLength+4], 51h ; 'Q'
0x18000343b  mov     edi, r12d
0x18000343e  jmp     short loc_180003444
0x180003440  mov     edi, dword ptr [rsp+290h+pcchLength]
0x180003444  mov     ecx, eax
0x180003446  call    WX_WIN32_FROM_HR
0x18000344b  mov     ebx, eax
0x18000344d  test    eax, eax
0x18000344f  jnz     short loc_180003465
0x180003451  cmp     [rsi], r12w
0x180003455  jz      short loc_1800034BD
0x180003457  add     edi, edi
0x180003459  mov     eax, edi
0x18000345b  cmp     edi, [r14]
0x18000345e  jbe     short loc_1800034AA
0x180003460  mov     ebx, 7Ah ; 'z'
0x180003465  mov     edx, 20h ; ' '
0x18000346a  test    byte ptr cs:xmmword_1800423E0+1, dl
0x180003470  jz      short loc_180003486
0x180003472  mov     ecx, 40Dh
0x180003477  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x18000347e  mov     r9d, ebx
0x180003481  call    WPP_SF_D
0x180003486  mov     eax, ebx
0x180003488  mov     rcx, [rbp+190h+var_40]
0x18000348f  xor     rcx, rsp; StackCookie
0x180003492  call    __security_check_cookie
0x180003497  add     rsp, 260h
0x18000349e  pop     r15
0x1800034a0  pop     r14
0x1800034a2  pop     r12
0x1800034a4  pop     rdi
0x1800034a5  pop     rsi
0x1800034a6  pop     rbx
0x1800034a7  pop     rbp
0x1800034a8  retn
0x1800034aa  mov     r8, rax; Size
0x1800034ad  mov     [r14], edi
0x1800034b0  mov     rdx, rsi; Src
0x1800034b3  mov     rcx, r15; void *
0x1800034b6  call    memcpy_0
0x1800034bb  jmp     short loc_180003486
0x1800034bd  mov     [r14], r12d
0x1800034c0  jmp     short loc_180003486
```
