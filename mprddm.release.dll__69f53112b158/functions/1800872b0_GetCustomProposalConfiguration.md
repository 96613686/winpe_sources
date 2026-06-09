# GetCustomProposalConfiguration

- ea: `0x1800872b0`
- end: `0x1800875af`
- name: `GetCustomProposalConfiguration`
- size: `767`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180086adc`

## callees

- `0x180019d50`
- `0x180087204`
- `0x1800872b0`
- `0x180087758`
- `0x1800877c0`
- `0x180087870`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180087562`
- `KERNEL32!LocalFree` at `0x180087562`
- `KERNEL32!LocalAlloc` at `0x180087359`
- `KERNEL32!LocalAlloc` at `0x180087359`
- `ADVAPI32!RegCloseKey` at `0x180087519`
- `ADVAPI32!RegCloseKey` at `0x180087573`
- `ADVAPI32!RegCloseKey` at `0x180087519`
- `ADVAPI32!RegCloseKey` at `0x180087573`
- `ADVAPI32!RegOpenKeyExA` at `0x1800873c2`
- `ADVAPI32!RegOpenKeyExA` at `0x1800873c2`
- `ADVAPI32!RegQueryValueExA` at `0x180087330`
- `ADVAPI32!RegQueryValueExA` at `0x180087401`
- `ADVAPI32!RegQueryValueExA` at `0x180087451`
- `ADVAPI32!RegQueryValueExA` at `0x1800874a1`
- `ADVAPI32!RegQueryValueExA` at `0x1800874f0`
- `ADVAPI32!RegQueryValueExA` at `0x180087330`
- `ADVAPI32!RegQueryValueExA` at `0x180087401`
- `ADVAPI32!RegQueryValueExA` at `0x180087451`
- `ADVAPI32!RegQueryValueExA` at `0x1800874a1`
- `ADVAPI32!RegQueryValueExA` at `0x1800874f0`

## string_xrefs

- `0x180087385`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
_QWORD *__fastcall GetCustomProposalConfiguration(_DWORD *a1)
{
  _QWORD *i; // rbx
  HKEY CustomCofigurationKey; // r14
  unsigned int v4; // esi
  __int64 v5; // rax
  BYTE Data[8]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C8h] BYREF
  BYTE lpData[272]; // [rsp+48h] [rbp-C0h] BYREF
  char pszDest[272]; // [rsp+158h] [rbp+50h] BYREF

  i = 0;
  phkResult = 0;
  CustomCofigurationKey = (HKEY)GetCustomCofigurationKey();
  *a1 = 0;
  if ( CustomCofigurationKey )
  {
    *(_DWORD *)&Data[4] = 0;
    *(_DWORD *)Data = 4;
    if ( !RegQueryValueExA(CustomCofigurationKey, "CustomProposalsCount", 0, 0, &Data[4], (LPDWORD)Data) )
    {
      if ( *(_DWORD *)&Data[4] )
      {
        v4 = 0;
        for ( i = LocalAlloc(0x40u, 32LL * *(unsigned int *)&Data[4]); v4 < *(_DWORD *)&Data[4]; ++v4 )
        {
          StringCbPrintfA(
            pszDest,
            0x104u,
            "%s\\%s\\%d",
            "System\\CurrentControlSet\\Services\\rasman\\IKEv2",
            "Proposals",
            v4);
          if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, &phkResult) )
          {
            *(_DWORD *)Data = 260;
            if ( !RegQueryValueExA(phkResult, "esp_encr", 0, 0, lpData, (LPDWORD)Data) )
              i[4 * (unsigned int)*a1 + 1] = StringToEncrTransform((char *)lpData);
            *(_DWORD *)Data = 260;
            if ( !RegQueryValueExA(phkResult, "esp_auth", 0, 0, lpData, (LPDWORD)Data) )
              i[4 * (unsigned int)*a1 + 2] = StringToAuthTransform((char *)lpData);
            *(_DWORD *)Data = 260;
            if ( !RegQueryValueExA(phkResult, "AH", 0, 0, lpData, (LPDWORD)Data) )
              i[4 * (unsigned int)*a1] = StringToAuthTransform((char *)lpData);
            *(_DWORD *)Data = 260;
            if ( !RegQueryValueExA(phkResult, "PFS", 0, 0, lpData, (LPDWORD)Data) )
              LODWORD(i[4 * (unsigned int)*a1 + 3]) = StringToPFSTransform((char *)lpData);
            RegCloseKey(phkResult);
            v5 = 4LL * (unsigned int)*a1;
            if ( i[v5] || i[v5 + 1] || i[v5 + 2] )
              ++*a1;
          }
        }
      }
      if ( !*a1 && i )
      {
        LocalFree(i);
        i = 0;
      }
    }
    RegCloseKey(CustomCofigurationKey);
  }
  return i;
}

```

## disassembly

```asm
0x1800872b0  mov     rax, rsp
0x1800872b3  mov     [rax+10h], rbx
0x1800872b7  mov     [rax+18h], rsi
0x1800872bb  mov     [rax+20h], rdi
0x1800872bf  push    rbp
0x1800872c0  push    r12
0x1800872c2  push    r14
0x1800872c4  lea     rbp, [rax-188h]
0x1800872cb  sub     rsp, 270h
0x1800872d2  mov     rax, cs:__security_cookie
0x1800872d9  xor     rax, rsp
0x1800872dc  mov     [rbp+180h+var_20], rax
0x1800872e3  mov     rdi, rcx
0x1800872e6  xor     ebx, ebx
0x1800872e8  call    GetCustomCofigurationKey
0x1800872ed  and     [rsp+280h+phkResult], rbx
0x1800872f2  mov     r14, rax
0x1800872f5  and     [rdi], ebx
0x1800872f7  test    rax, rax
0x1800872fa  jz      loc_18008757F
0x180087300  and     dword ptr [rsp+280h+Data+4], ebx
0x180087304  lea     rax, [rsp+280h+Data]
0x180087309  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18008730e  lea     rdx, aCustomproposal; "CustomProposalsCount"
0x180087315  lea     rax, [rsp+280h+Data+4]
0x18008731a  mov     dword ptr [rsp+280h+Data], 4
0x180087322  xor     r9d, r9d; lpType
0x180087325  mov     [rsp+280h+lpData], rax; lpData
0x18008732a  xor     r8d, r8d; lpReserved
0x18008732d  mov     rcx, r14; hKey
0x180087330  call    cs:__imp_RegQueryValueExA
0x180087337  nop     dword ptr [rax+rax+00h]
0x18008733c  test    eax, eax
0x18008733e  jnz     loc_180087570
0x180087344  mov     eax, dword ptr [rsp+280h+Data+4]
0x180087348  test    eax, eax
0x18008734a  jz      loc_180087555
0x180087350  mov     edx, eax
0x180087352  lea     ecx, [rbx+40h]; uFlags
0x180087355  shl     rdx, 5; uBytes
0x180087359  call    cs:__imp_LocalAlloc
0x180087360  nop     dword ptr [rax+rax+00h]
0x180087365  xor     esi, esi
0x180087367  mov     rbx, rax
0x18008736a  cmp     dword ptr [rsp+280h+Data+4], esi
0x18008736e  jbe     loc_180087555
0x180087374  mov     r12d, 104h
0x18008737a  lea     rax, aProposals; "Proposals"
0x180087381  mov     dword ptr [rsp+280h+lpcbData], esi
0x180087385  lea     r9, aSystemCurrentc_28; "System\\CurrentControlSet\\Services\\ra"...
0x18008738c  mov     [rsp+280h+lpData], rax
0x180087391  lea     r8, aSSD; "%s\\%s\\%d"
0x180087398  mov     rdx, r12; cbDest
0x18008739b  lea     rcx, [rbp+180h+pszDest]; pszDest
0x18008739f  call    StringCbPrintfA
0x1800873a4  lea     rax, [rsp+280h+phkResult]
0x1800873a9  mov     r9d, 1; samDesired
0x1800873af  xor     r8d, r8d; ulOptions
0x1800873b2  mov     [rsp+280h+lpData], rax; phkResult
0x1800873b7  lea     rdx, [rbp+180h+pszDest]; lpSubKey
0x1800873bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800873c2  call    cs:__imp_RegOpenKeyExA
0x1800873c9  nop     dword ptr [rax+rax+00h]
0x1800873ce  test    eax, eax
0x1800873d0  jnz     loc_180087549
0x1800873d6  mov     rcx, [rsp+280h+phkResult]; hKey
0x1800873db  lea     rax, [rsp+280h+Data]
0x1800873e0  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800873e5  lea     rdx, aEspEncr; "esp_encr"
0x1800873ec  lea     rax, [rsp+280h+var_240]
0x1800873f1  mov     dword ptr [rsp+280h+Data], r12d
0x1800873f6  xor     r9d, r9d; lpType
0x1800873f9  mov     [rsp+280h+lpData], rax; lpData
0x1800873fe  xor     r8d, r8d; lpReserved
0x180087401  call    cs:__imp_RegQueryValueExA
0x180087408  nop     dword ptr [rax+rax+00h]
0x18008740d  test    eax, eax
0x18008740f  jnz     short loc_180087426
0x180087411  lea     rcx, [rsp+280h+var_240]; String1
0x180087416  call    StringToEncrTransform
0x18008741b  mov     ecx, [rdi]
0x18008741d  shl     rcx, 5
0x180087421  mov     [rcx+rbx+8], rax
0x180087426  mov     rcx, [rsp+280h+phkResult]; hKey
0x18008742b  lea     rax, [rsp+280h+Data]
0x180087430  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180087435  lea     rdx, aEspAuth; "esp_auth"
0x18008743c  lea     rax, [rsp+280h+var_240]
0x180087441  mov     dword ptr [rsp+280h+Data], r12d
0x180087446  xor     r9d, r9d; lpType
0x180087449  mov     [rsp+280h+lpData], rax; lpData
0x18008744e  xor     r8d, r8d; lpReserved
0x180087451  call    cs:__imp_RegQueryValueExA
0x180087458  nop     dword ptr [rax+rax+00h]
0x18008745d  test    eax, eax
0x18008745f  jnz     short loc_180087476
0x180087461  lea     rcx, [rsp+280h+var_240]; String1
0x180087466  call    StringToAuthTransform
0x18008746b  mov     ecx, [rdi]
0x18008746d  shl     rcx, 5
0x180087471  mov     [rcx+rbx+10h], rax
0x180087476  mov     rcx, [rsp+280h+phkResult]; hKey
0x18008747b  lea     rax, [rsp+280h+Data]
0x180087480  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180087485  lea     rdx, aAh; "AH"
0x18008748c  lea     rax, [rsp+280h+var_240]
0x180087491  mov     dword ptr [rsp+280h+Data], r12d
0x180087496  xor     r9d, r9d; lpType
0x180087499  mov     [rsp+280h+lpData], rax; lpData
0x18008749e  xor     r8d, r8d; lpReserved
0x1800874a1  call    cs:__imp_RegQueryValueExA
0x1800874a8  nop     dword ptr [rax+rax+00h]
0x1800874ad  test    eax, eax
0x1800874af  jnz     short loc_1800874C5
0x1800874b1  lea     rcx, [rsp+280h+var_240]; String1
0x1800874b6  call    StringToAuthTransform
0x1800874bb  mov     ecx, [rdi]
0x1800874bd  shl     rcx, 5
0x1800874c1  mov     [rcx+rbx], rax
0x1800874c5  mov     rcx, [rsp+280h+phkResult]; hKey
0x1800874ca  lea     rax, [rsp+280h+Data]
0x1800874cf  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800874d4  lea     rdx, aPfs; "PFS"
0x1800874db  lea     rax, [rsp+280h+var_240]
0x1800874e0  mov     dword ptr [rsp+280h+Data], r12d
0x1800874e5  xor     r9d, r9d; lpType
0x1800874e8  mov     [rsp+280h+lpData], rax; lpData
0x1800874ed  xor     r8d, r8d; lpReserved
0x1800874f0  call    cs:__imp_RegQueryValueExA
0x1800874f7  nop     dword ptr [rax+rax+00h]
0x1800874fc  test    eax, eax
0x1800874fe  jnz     short loc_180087514
0x180087500  lea     rcx, [rsp+280h+var_240]; String1
0x180087505  call    StringToPFSTransform
0x18008750a  mov     ecx, [rdi]
0x18008750c  shl     rcx, 5
0x180087510  mov     [rcx+rbx+18h], eax
0x180087514  mov     rcx, [rsp+280h+phkResult]; hKey
0x180087519  call    cs:__imp_RegCloseKey
0x180087520  nop     dword ptr [rax+rax+00h]
0x180087525  mov     ecx, [rdi]
0x180087527  mov     eax, ecx
0x180087529  shl     rax, 5
0x18008752d  cmp     qword ptr [rax+rbx], 0
0x180087532  jnz     short loc_180087544
0x180087534  cmp     qword ptr [rax+rbx+8], 0
0x18008753a  jnz     short loc_180087544
0x18008753c  cmp     qword ptr [rax+rbx+10h], 0
0x180087542  jz      short loc_180087549
0x180087544  lea     eax, [rcx+1]
0x180087547  mov     [rdi], eax
0x180087549  inc     esi
0x18008754b  cmp     esi, dword ptr [rsp+280h+Data+4]
0x18008754f  jb      loc_18008737A
0x180087555  cmp     dword ptr [rdi], 0
0x180087558  jnz     short loc_180087570
0x18008755a  test    rbx, rbx
0x18008755d  jz      short loc_180087570
0x18008755f  mov     rcx, rbx; hMem
0x180087562  call    cs:__imp_LocalFree
0x180087569  nop     dword ptr [rax+rax+00h]
0x18008756e  xor     ebx, ebx
0x180087570  mov     rcx, r14; hKey
0x180087573  call    cs:__imp_RegCloseKey
0x18008757a  nop     dword ptr [rax+rax+00h]
0x18008757f  mov     rax, rbx
0x180087582  mov     rcx, [rbp+180h+var_20]
0x180087589  xor     rcx, rsp; StackCookie
0x18008758c  call    __security_check_cookie
0x180087591  lea     r11, [rsp+280h+var_10]
0x180087599  mov     rbx, [r11+28h]
0x18008759d  mov     rsi, [r11+30h]
0x1800875a1  mov     rdi, [r11+38h]
0x1800875a5  mov     rsp, r11
0x1800875a8  pop     r14
0x1800875aa  pop     r12
0x1800875ac  pop     rbp
0x1800875ad  retn
```
