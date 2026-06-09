# AddressPoolInit

- ea: `0x1800164b4`
- end: `0x1800167f4`
- name: `AddressPoolInit`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x1800164b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800165a4`
- `KERNEL32!GetLastError` at `0x18001662a`
- `KERNEL32!GetLastError` at `0x1800166ec`
- `KERNEL32!GetLastError` at `0x180016779`
- `KERNEL32!GetLastError` at `0x1800165a4`
- `KERNEL32!GetLastError` at `0x18001662a`
- `KERNEL32!GetLastError` at `0x1800166ec`
- `KERNEL32!GetLastError` at `0x180016779`
- `KERNEL32!LocalAlloc` at `0x180016590`
- `KERNEL32!LocalAlloc` at `0x180016616`
- `KERNEL32!LocalAlloc` at `0x1800166d8`
- `KERNEL32!LocalAlloc` at `0x180016765`
- `KERNEL32!LocalAlloc` at `0x180016590`
- `KERNEL32!LocalAlloc` at `0x180016616`
- `KERNEL32!LocalAlloc` at `0x1800166d8`
- `KERNEL32!LocalAlloc` at `0x180016765`
- `ADVAPI32!RegOpenKeyExW` at `0x180016506`
- `ADVAPI32!RegOpenKeyExW` at `0x180016506`
- `ADVAPI32!RegQueryValueExW` at `0x180016563`
- `ADVAPI32!RegQueryValueExW` at `0x1800165d4`
- `ADVAPI32!RegQueryValueExW` at `0x1800166a9`
- `ADVAPI32!RegQueryValueExW` at `0x18001671e`
- `ADVAPI32!RegQueryValueExW` at `0x180016563`
- `ADVAPI32!RegQueryValueExW` at `0x1800165d4`
- `ADVAPI32!RegQueryValueExW` at `0x1800166a9`
- `ADVAPI32!RegQueryValueExW` at `0x18001671e`
- `ADVAPI32!RegCloseKey` at `0x1800167d0`
- `ADVAPI32!RegCloseKey` at `0x1800167d0`

## string_xrefs

- `0x1800164df`: `System\CurrentControlSet\Services\PptpProtocol\Parameters`

## pseudocode

```c
__int64 AddressPoolInit()
{
  unsigned int v0; // ebx
  DWORD j; // esi
  HKEY v2; // rdi
  BYTE *v3; // rsi
  unsigned int v4; // edi
  BYTE *i; // rcx
  __int64 v6; // rax
  _QWORD *v7; // r14
  int v8; // ecx
  __int64 v9; // rax
  HKEY v10; // rdi
  BYTE *v11; // r14
  unsigned int v12; // edi
  BYTE *v13; // rdx
  __int64 v14; // rax
  _QWORD *v15; // r15
  int v16; // ecx
  __int64 v17; // rax
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+50h] BYREF

  v0 = 0;
  hKey = 0;
  dword_1800CF62C = 0;
  hMem = 0;
  dword_1800CF638 = 0;
  qword_1800CF640 = 0;
  j = RegOpenKeyExW(
        HKEY_LOCAL_MACHINE,
        L"System\\CurrentControlSet\\Services\\PptpProtocol\\Parameters",
        0,
        0x20019u,
        &hKey);
  if ( !j )
  {
    v2 = hKey;
    Type = 0;
    cbData = 0;
    if ( hKey )
    {
      dword_1800CF62C = 0;
      hMem = 0;
      if ( !RegQueryValueExW(hKey, L"AnalogIPAddressPool", 0, &Type, 0, &cbData) && Type == 7 && cbData )
      {
        v3 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v3 )
        {
          if ( !RegQueryValueExW(v2, L"AnalogIPAddressPool", 0, &Type, v3, &cbData) )
          {
            v4 = 0;
            for ( i = v3; *(_WORD *)i; i += 2 * v6 + 2 )
            {
              v6 = -1;
              do
                ++v6;
              while ( *(_WORD *)&i[2 * v6] );
              ++v4;
            }
            v7 = LocalAlloc(0x40u, 8LL * v4);
            if ( v7 )
            {
              v8 = 0;
              while ( *(_WORD *)v3 )
              {
                v7[v8] = v3;
                v9 = -1;
                do
                  ++v9;
                while ( *(_WORD *)&v3[2 * v9] );
                v3 += 2 * v9 + 2;
                ++v8;
              }
            }
            else
            {
              GetLastError();
            }
            dword_1800CF62C = v4;
            hMem = v7;
          }
        }
        else
        {
          GetLastError();
        }
      }
    }
    v10 = hKey;
    Type = 0;
    cbData = 0;
    if ( hKey )
    {
      dword_1800CF638 = 0;
      qword_1800CF640 = 0;
      j = RegQueryValueExW(hKey, L"DigitalIPAddressPool", 0, &Type, 0, &cbData);
      if ( !j && Type == 7 && cbData )
      {
        v11 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v11 )
        {
          j = RegQueryValueExW(v10, L"DigitalIPAddressPool", 0, &Type, v11, &cbData);
          if ( !j )
          {
            v12 = 0;
            v13 = v11;
            for ( j = 0; *(_WORD *)v13; v13 += 2 * v14 + 2 )
            {
              v14 = -1;
              do
                ++v14;
              while ( *(_WORD *)&v13[2 * v14] );
              ++v12;
            }
            v15 = LocalAlloc(0x40u, 8LL * v12);
            if ( v15 )
            {
              v16 = 0;
              while ( *(_WORD *)v11 )
              {
                v15[v16] = v11;
                v17 = -1;
                do
                  ++v17;
                while ( *(_WORD *)&v11[2 * v17] );
                v11 += 2 * v17 + 2;
                ++v16;
              }
            }
            else
            {
              j = GetLastError();
            }
            dword_1800CF638 = v12;
            qword_1800CF640 = v15;
          }
        }
        else
        {
          j = GetLastError();
        }
      }
    }
    else
    {
      j = 6;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( j != 2 )
    return j;
  return v0;
}

```

## disassembly

```asm
0x1800164b4  push    rbp
0x1800164b6  push    rbx
0x1800164b7  push    rsi
0x1800164b8  push    rdi
0x1800164b9  push    r12
0x1800164bb  push    r14
0x1800164bd  push    r15
0x1800164bf  mov     rbp, rsp
0x1800164c2  sub     rsp, 30h
0x1800164c6  xor     ebx, ebx
0x1800164c8  lea     rax, [rbp+hKey]
0x1800164cc  mov     r9d, 20019h; samDesired
0x1800164d2  mov     [rbp+hKey], rbx
0x1800164d6  xor     r8d, r8d; ulOptions
0x1800164d9  mov     cs:dword_1800CF62C, ebx
0x1800164df  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Pp"...
0x1800164e6  mov     cs:hMem, rbx
0x1800164ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800164f4  mov     cs:dword_1800CF638, ebx
0x1800164fa  mov     cs:qword_1800CF640, rbx
0x180016501  mov     [rsp+30h+phkResult], rax; phkResult
0x180016506  call    cs:__imp_RegOpenKeyExW
0x18001650d  nop     dword ptr [rax+rax+00h]
0x180016512  mov     esi, eax
0x180016514  test    eax, eax
0x180016516  jnz     loc_1800167C4
0x18001651c  mov     rdi, [rbp+hKey]
0x180016520  lea     r15d, [rbx+40h]
0x180016524  or      r12, 0FFFFFFFFFFFFFFFFh
0x180016528  mov     [rbp+Type], ebx
0x18001652b  mov     [rbp+cbData], ebx
0x18001652e  test    rdi, rdi
0x180016531  jz      loc_18001666A
0x180016537  lea     rax, [rbp+cbData]
0x18001653b  mov     cs:dword_1800CF62C, ebx
0x180016541  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180016546  lea     r9, [rbp+Type]; lpType
0x18001654a  xor     r8d, r8d; lpReserved
0x18001654d  mov     [rsp+30h+phkResult], rbx; lpData
0x180016552  lea     rdx, aAnalogipaddres; "AnalogIPAddressPool"
0x180016559  mov     cs:hMem, rbx
0x180016560  mov     rcx, rdi; hKey
0x180016563  call    cs:__imp_RegQueryValueExW
0x18001656a  nop     dword ptr [rax+rax+00h]
0x18001656f  test    eax, eax
0x180016571  jnz     loc_18001666A
0x180016577  cmp     [rbp+Type], 7
0x18001657b  jnz     loc_18001666A
0x180016581  cmp     [rbp+cbData], ebx
0x180016584  jz      loc_18001666A
0x18001658a  mov     edx, [rbp+cbData]; uBytes
0x18001658d  mov     ecx, r15d; uFlags
0x180016590  call    cs:__imp_LocalAlloc
0x180016597  nop     dword ptr [rax+rax+00h]
0x18001659c  mov     rsi, rax
0x18001659f  test    rax, rax
0x1800165a2  jnz     short loc_1800165B5
0x1800165a4  call    cs:__imp_GetLastError
0x1800165ab  nop     dword ptr [rax+rax+00h]
0x1800165b0  jmp     loc_18001666A
0x1800165b5  lea     rax, [rbp+cbData]
0x1800165b9  xor     r8d, r8d; lpReserved
0x1800165bc  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800165c1  lea     r9, [rbp+Type]; lpType
0x1800165c5  lea     rdx, aAnalogipaddres; "AnalogIPAddressPool"
0x1800165cc  mov     [rsp+30h+phkResult], rsi; lpData
0x1800165d1  mov     rcx, rdi; hKey
0x1800165d4  call    cs:__imp_RegQueryValueExW
0x1800165db  nop     dword ptr [rax+rax+00h]
0x1800165e0  test    eax, eax
0x1800165e2  jnz     loc_18001666A
0x1800165e8  mov     edi, ebx
0x1800165ea  mov     rcx, rsi
0x1800165ed  cmp     bx, [rsi]
0x1800165f0  jz      short loc_18001660D
0x1800165f2  mov     rax, r12
0x1800165f5  inc     rax
0x1800165f8  cmp     [rcx+rax*2], bx
0x1800165fc  jnz     short loc_1800165F5
0x1800165fe  lea     rcx, [rcx+rax*2]
0x180016602  inc     edi
0x180016604  add     rcx, 2
0x180016608  cmp     bx, [rcx]
0x18001660b  jnz     short loc_1800165F2
0x18001660d  mov     edx, edi
0x18001660f  mov     ecx, r15d; uFlags
0x180016612  shl     rdx, 3; uBytes
0x180016616  call    cs:__imp_LocalAlloc
0x18001661d  nop     dword ptr [rax+rax+00h]
0x180016622  mov     r14, rax
0x180016625  test    rax, rax
0x180016628  jnz     short loc_180016638
0x18001662a  call    cs:__imp_GetLastError
0x180016631  nop     dword ptr [rax+rax+00h]
0x180016636  jmp     short loc_18001665D
0x180016638  mov     ecx, ebx
0x18001663a  jmp     short loc_180016658
0x18001663c  mov     eax, ecx
0x18001663e  mov     [r14+rax*8], rsi
0x180016642  mov     rax, r12
0x180016645  inc     rax
0x180016648  cmp     [rsi+rax*2], bx
0x18001664c  jnz     short loc_180016645
0x18001664e  lea     rsi, [rsi+rax*2]
0x180016652  add     rsi, 2
0x180016656  inc     ecx
0x180016658  cmp     bx, [rsi]
0x18001665b  jnz     short loc_18001663C
0x18001665d  mov     cs:dword_1800CF62C, edi
0x180016663  mov     cs:hMem, r14
0x18001666a  mov     rdi, [rbp+hKey]
0x18001666e  mov     [rbp+Type], ebx
0x180016671  mov     [rbp+cbData], ebx
0x180016674  test    rdi, rdi
0x180016677  jz      loc_1800167BF
0x18001667d  lea     rax, [rbp+cbData]
0x180016681  mov     cs:dword_1800CF638, ebx
0x180016687  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001668c  lea     r9, [rbp+Type]; lpType
0x180016690  xor     r8d, r8d; lpReserved
0x180016693  mov     [rsp+30h+phkResult], rbx; lpData
0x180016698  lea     rdx, aDigitalipaddre; "DigitalIPAddressPool"
0x18001669f  mov     cs:qword_1800CF640, rbx
0x1800166a6  mov     rcx, rdi; hKey
0x1800166a9  call    cs:__imp_RegQueryValueExW
0x1800166b0  nop     dword ptr [rax+rax+00h]
0x1800166b5  mov     esi, eax
0x1800166b7  test    eax, eax
0x1800166b9  jnz     loc_1800167C4
0x1800166bf  cmp     [rbp+Type], 7
0x1800166c3  jnz     loc_1800167C4
0x1800166c9  cmp     [rbp+cbData], ebx
0x1800166cc  jz      loc_1800167C4
0x1800166d2  mov     edx, [rbp+cbData]; uBytes
0x1800166d5  mov     ecx, r15d; uFlags
0x1800166d8  call    cs:__imp_LocalAlloc
0x1800166df  nop     dword ptr [rax+rax+00h]
0x1800166e4  mov     r14, rax
0x1800166e7  test    rax, rax
0x1800166ea  jnz     short loc_1800166FF
0x1800166ec  call    cs:__imp_GetLastError
0x1800166f3  nop     dword ptr [rax+rax+00h]
0x1800166f8  mov     esi, eax
0x1800166fa  jmp     loc_1800167C4
0x1800166ff  lea     rax, [rbp+cbData]
0x180016703  xor     r8d, r8d; lpReserved
0x180016706  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001670b  lea     r9, [rbp+Type]; lpType
0x18001670f  lea     rdx, aDigitalipaddre; "DigitalIPAddressPool"
0x180016716  mov     [rsp+30h+phkResult], r14; lpData
0x18001671b  mov     rcx, rdi; hKey
0x18001671e  call    cs:__imp_RegQueryValueExW
0x180016725  nop     dword ptr [rax+rax+00h]
0x18001672a  mov     esi, eax
0x18001672c  test    eax, eax
0x18001672e  jnz     loc_1800167C4
0x180016734  mov     edi, ebx
0x180016736  mov     rdx, r14
0x180016739  mov     esi, ebx
0x18001673b  cmp     bx, [r14]
0x18001673f  jz      short loc_18001675C
0x180016741  mov     rax, r12
0x180016744  inc     rax
0x180016747  cmp     [rdx+rax*2], bx
0x18001674b  jnz     short loc_180016744
0x18001674d  lea     rdx, [rdx+rax*2]
0x180016751  inc     edi
0x180016753  add     rdx, 2
0x180016757  cmp     bx, [rdx]
0x18001675a  jnz     short loc_180016741
0x18001675c  mov     edx, edi
0x18001675e  mov     ecx, r15d; uFlags
0x180016761  shl     rdx, 3; uBytes
0x180016765  call    cs:__imp_LocalAlloc
0x18001676c  nop     dword ptr [rax+rax+00h]
0x180016771  mov     r15, rax
0x180016774  test    rax, rax
0x180016777  jnz     short loc_180016789
0x180016779  call    cs:__imp_GetLastError
0x180016780  nop     dword ptr [rax+rax+00h]
0x180016785  mov     esi, eax
0x180016787  jmp     short loc_1800167B0
0x180016789  mov     ecx, ebx
0x18001678b  jmp     short loc_1800167AA
0x18001678d  mov     eax, ecx
0x18001678f  mov     [r15+rax*8], r14
0x180016793  mov     rax, r12
0x180016796  inc     rax
0x180016799  cmp     [r14+rax*2], bx
0x18001679e  jnz     short loc_180016796
0x1800167a0  lea     r14, [r14+rax*2]
0x1800167a4  add     r14, 2
0x1800167a8  inc     ecx
0x1800167aa  cmp     bx, [r14]
0x1800167ae  jnz     short loc_18001678D
0x1800167b0  mov     cs:dword_1800CF638, edi
0x1800167b6  mov     cs:qword_1800CF640, r15
0x1800167bd  jmp     short loc_1800167C4
0x1800167bf  mov     esi, 6
0x1800167c4  mov     rdi, [rbp+hKey]
0x1800167c8  test    rdi, rdi
0x1800167cb  jz      short loc_1800167DC
0x1800167cd  mov     rcx, rdi; hKey
0x1800167d0  call    cs:__imp_RegCloseKey
0x1800167d7  nop     dword ptr [rax+rax+00h]
0x1800167dc  cmp     esi, 2
0x1800167df  cmovnz  ebx, esi
0x1800167e2  mov     eax, ebx
0x1800167e4  add     rsp, 30h
0x1800167e8  pop     r15
0x1800167ea  pop     r14
0x1800167ec  pop     r12
0x1800167ee  pop     rdi
0x1800167ef  pop     rsi
0x1800167f0  pop     rbx
0x1800167f1  pop     rbp
0x1800167f2  retn
```
