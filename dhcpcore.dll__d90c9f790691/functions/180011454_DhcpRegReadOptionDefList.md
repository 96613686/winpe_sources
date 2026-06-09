# DhcpRegReadOptionDefList

- ea: `0x180011454`
- end: `0x1800116eb`
- name: `DhcpRegReadOptionDefList`
- size: `663`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x18003619c`

## callees

- `0x180005670`
- `0x1800057f0`
- `0x180005da4`
- `0x180006440`
- `0x1800069d0`
- `0x180011454`
- `0x1800116f4`
- `0x180018cd4`
- `0x180018fbc`
- `0x18001b91c`
- `0x18003b520`
- `0x180047a48`
- `0x180047e3c`
- `0x18004d1a0`
- `0x18004d310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011591`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011591`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001155d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001155d`

## string_xrefs

- `0x1800114ff`: `System\CurrentControlSet\Services\Dhcp\Parameters\Options`
- `0x180011658`: `System\CurrentControlSet\Services\Dhcp\Parameters\Options`

## pseudocode

```c
LSTATUS DhcpRegReadOptionDefList()
{
  unsigned int v0; // r15d
  unsigned int v1; // eax
  unsigned int inited; // eax
  int IsWCOSSystem; // eax
  size_t v4; // rdx
  const wchar_t *v5; // r13
  const wchar_t *v6; // rcx
  HRESULT v7; // eax
  int v8; // r14d
  LSTATUS result; // eax
  int v10; // eax
  const WCHAR *v11; // rdx
  size_t v12; // r14
  int RegistryString; // ebx
  unsigned int v14; // esi
  const wchar_t *v15; // rdi
  STRSAFE_LPCWSTR v16; // rbx
  const wchar_t *v17; // r12
  unsigned int v18; // esi
  const wchar_t *i; // rcx
  __int64 v20; // r12
  wchar_t *v21; // r15
  int v22; // r11d
  size_t pcbLength; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v24; // [rsp+90h] [rbp+48h] BYREF
  STRSAFE_LPCWSTR v25; // [rsp+98h] [rbp+50h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+A0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+60h] BYREF

  v0 = 0;
  hKey = 0;
  LODWORD(v25) = 0;
  v24 = 0;
  if ( (unsigned int)DhcpIsWCOSSystem() )
  {
    v1 = DhcpWCOSInitOptionDefList();
    if ( v1 )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 28, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, v1);
    }
    return 0;
  }
  inited = DhcpInitOptionDefList();
  if ( inited && (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 29, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids, inited);
  IsWCOSSystem = DhcpIsWCOSSystem();
  v5 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  pcbLength = 0;
  v6 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  LODWORD(pszSrc) = 0;
  if ( !IsWCOSSystem )
    v6 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
  v7 = StringCbLengthW(v6, v4, &pcbLength);
  if ( v7 >= 0 )
  {
    v8 = pcbLength;
  }
  else
  {
    HIDWORD(pcbLength) = 108;
    v8 = 0;
  }
  result = WX_WIN32_FROM_HR((unsigned int)v7);
  if ( !result )
  {
    v10 = DhcpIsWCOSSystem();
    v11 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
    if ( !v10 )
      v11 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
    result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0xFu, &hKey);
    if ( !result )
    {
      pszSrc = 0;
      v12 = (unsigned int)(v8 + 2);
      RegistryString = GetRegistryString(hKey, L"DhcpOptionLocationList");
      RegCloseKey(hKey);
      if ( RegistryString || (v14 = (unsigned int)v25) == 0 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_SD(
            1025,
            30,
            (unsigned int)WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids,
            (unsigned int)L"DhcpOptionLocationList",
            RegistryString);
        v15 = L"1";
        v14 = 84;
        v16 = 0;
      }
      else
      {
        v15 = pszSrc;
        v16 = pszSrc;
      }
      v25 = v16;
      v17 = v15;
      v18 = v14 >> 1;
      for ( i = v15; (int)WxStringCchLengthDWordW(i, v18, &v24) >= 0 && v24; i = v17 )
      {
        if ( v24 > v0 )
          v0 = v24;
        v17 += v24 + 1;
      }
      v20 = (unsigned int)v12 + 2 * (v0 + 2);
      pszSrc = (STRSAFE_LPCWSTR)DhcpAlloc(v20);
      v21 = (wchar_t *)pszSrc;
      if ( pszSrc )
      {
        if ( !(unsigned int)DhcpIsWCOSSystem() )
          v5 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
        memcpy_0(v21, v5, v12);
        *(wchar_t *)((char *)v21 + v12 - 2) = 92;
        while ( (int)WxStringCchLengthDWordW(v15, v18, &v24) >= 0 && v24 )
        {
          result = StringCchCopyW((wchar_t *)((char *)v21 + v12), v20 - (v12 >> 1), v15);
          if ( result < 0 )
            return result;
          v15 += (unsigned int)(v22 + 1);
          DhcpRegReadOptionDef(v21);
        }
        if ( v16 )
          DhcpPunycodeFree(&v25);
        DhcpPunycodeFree(&pszSrc);
        return 0;
      }
      if ( v16 )
        DhcpPunycodeFree(&v25);
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011454  push    rbp
0x180011456  push    rbx
0x180011457  push    rsi
0x180011458  push    rdi
0x180011459  push    r12
0x18001145b  push    r13
0x18001145d  push    r14
0x18001145f  push    r15
0x180011461  mov     rbp, rsp
0x180011464  sub     rsp, 48h
0x180011468  xor     r15d, r15d
0x18001146b  mov     [rbp+hKey], r15
0x18001146f  mov     dword ptr [rbp+arg_8], r15d
0x180011473  mov     [rbp+arg_0], r15d
0x180011477  call    DhcpIsWCOSSystem
0x18001147c  test    eax, eax
0x18001147e  jz      short loc_1800114B7
0x180011480  call    DhcpWCOSInitOptionDefList
0x180011485  test    eax, eax
0x180011487  jz      loc_1800116D8
0x18001148d  test    byte ptr cs:xmmword_1800616A0, 2
0x180011494  jz      loc_1800116D8
0x18001149a  lea     edx, [r15+1Ch]
0x18001149e  mov     ecx, 401h
0x1800114a3  mov     r9d, eax
0x1800114a6  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800114ad  call    WPP_SF_D
0x1800114b2  jmp     loc_1800116D8
0x1800114b7  call    DhcpInitOptionDefList
0x1800114bc  test    eax, eax
0x1800114be  jz      short loc_1800114E2
0x1800114c0  test    byte ptr cs:xmmword_1800616A0, 2
0x1800114c7  jz      short loc_1800114E2
0x1800114c9  mov     edx, 1Dh
0x1800114ce  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800114d5  mov     ecx, 401h
0x1800114da  mov     r9d, eax
0x1800114dd  call    WPP_SF_D
0x1800114e2  call    DhcpIsWCOSSystem
0x1800114e7  mov     dword ptr [rbp+pcbLength+4], r15d
0x1800114eb  lea     r13, aOsdataNetworki_8; "OSDATA\\Networking\\Dhcp\\Client4\\Para"...
0x1800114f2  test    eax, eax
0x1800114f4  mov     [rbp-18h], r15
0x1800114f8  mov     rcx, r13
0x1800114fb  mov     dword ptr [rbp+pszSrc], r15d
0x1800114ff  lea     rbx, psz; "System\\CurrentControlSet\\Services\\Dh"...
0x180011506  cmovz   rcx, rbx; psz
0x18001150a  lea     r8, [rbp+pcbLength]; pcbLength
0x18001150e  call    StringCbLengthW
0x180011513  test    eax, eax
0x180011515  jns     short loc_180011523
0x180011517  mov     dword ptr [rbp+pcbLength+4], 6Ch ; 'l'
0x18001151e  mov     r14d, r15d
0x180011521  jmp     short loc_180011527
0x180011523  mov     r14d, dword ptr [rbp+pcbLength]
0x180011527  mov     ecx, eax
0x180011529  call    WX_WIN32_FROM_HR
0x18001152e  test    eax, eax
0x180011530  jnz     loc_1800116DA
0x180011536  call    DhcpIsWCOSSystem
0x18001153b  test    eax, eax
0x18001153d  mov     rdx, r13
0x180011540  lea     rax, [rbp+hKey]
0x180011544  mov     r9d, 0Fh; samDesired
0x18001154a  cmovz   rdx, rbx; lpSubKey
0x18001154e  mov     [rsp+48h+phkResult], rax; phkResult
0x180011553  xor     r8d, r8d; ulOptions
0x180011556  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001155d  call    cs:__imp_RegOpenKeyExW
0x180011563  test    eax, eax
0x180011565  jnz     loc_1800116DA
0x18001156b  mov     rcx, [rbp+hKey]; hKey
0x18001156f  lea     r9, [rbp+arg_8]
0x180011573  lea     r8, [rbp+pszSrc]
0x180011577  mov     [rbp+pszSrc], r15
0x18001157b  lea     rdx, aDhcpoptionloca; "DhcpOptionLocationList"
0x180011582  add     r14d, 2
0x180011586  call    GetRegistryString
0x18001158b  mov     rcx, [rbp+hKey]; hKey
0x18001158f  mov     ebx, eax
0x180011591  call    cs:__imp_RegCloseKey
0x180011597  test    ebx, ebx
0x180011599  jnz     short loc_1800115AB
0x18001159b  mov     esi, dword ptr [rbp+arg_8]
0x18001159e  test    esi, esi
0x1800115a0  jz      short loc_1800115AB
0x1800115a2  mov     rdi, [rbp+pszSrc]
0x1800115a6  mov     rbx, rdi
0x1800115a9  jmp     short loc_1800115E4
0x1800115ab  test    byte ptr cs:xmmword_1800616A0, 2
0x1800115b2  jz      short loc_1800115D5
0x1800115b4  mov     edx, 1Eh
0x1800115b9  mov     dword ptr [rsp+48h+phkResult], ebx
0x1800115bd  mov     ecx, 401h
0x1800115c2  lea     r9, aDhcpoptionloca; "DhcpOptionLocationList"
0x1800115c9  lea     r8, WPP_5b94a9fc2174303e55b47f5e3f4ecc4f_Traceguids
0x1800115d0  call    WPP_SF_SD
0x1800115d5  lea     rdi, a1; "1"
0x1800115dc  mov     esi, 54h ; 'T'
0x1800115e1  mov     rbx, r15
0x1800115e4  mov     [rbp+arg_8], rbx
0x1800115e8  mov     r12, rdi
0x1800115eb  shr     esi, 1
0x1800115ed  mov     rcx, rdi
0x1800115f0  jmp     short loc_180011609
0x1800115f2  mov     eax, [rbp+arg_0]
0x1800115f5  test    eax, eax
0x1800115f7  jz      short loc_180011618
0x1800115f9  cmp     eax, r15d
0x1800115fc  cmova   r15d, eax
0x180011600  inc     eax
0x180011602  lea     r12, [r12+rax*2]
0x180011606  mov     rcx, r12
0x180011609  lea     r8, [rbp+arg_0]
0x18001160d  mov     edx, esi
0x18001160f  call    WxStringCchLengthDWordW
0x180011614  test    eax, eax
0x180011616  jns     short loc_1800115F2
0x180011618  lea     r15d, [r15+2]
0x18001161c  lea     eax, [r14+r15*2]
0x180011620  mov     ecx, eax
0x180011622  mov     r12d, eax
0x180011625  call    DhcpAlloc
0x18001162a  mov     [rbp+pszSrc], rax
0x18001162e  mov     r15, rax
0x180011631  test    rax, rax
0x180011634  jnz     short loc_18001164E
0x180011636  test    rbx, rbx
0x180011639  jz      short loc_180011644
0x18001163b  lea     rcx, [rbp+arg_8]
0x18001163f  call    DhcpPunycodeFree
0x180011644  mov     eax, 8
0x180011649  jmp     loc_1800116DA
0x18001164e  call    DhcpIsWCOSSystem
0x180011653  test    eax, eax
0x180011655  mov     r8, r14; Size
0x180011658  lea     rax, psz; "System\\CurrentControlSet\\Services\\Dh"...
0x18001165f  mov     rcx, r15; void *
0x180011662  cmovz   r13, rax
0x180011666  mov     rdx, r13; Src
0x180011669  call    memcpy_0
0x18001166e  lea     r13, [r14+r15]
0x180011672  mov     word ptr [r13-2], 5Ch ; '\'
0x180011679  lea     r8, [rbp+arg_0]
0x18001167d  mov     edx, esi
0x18001167f  mov     rcx, rdi
0x180011682  call    WxStringCchLengthDWordW
0x180011687  test    eax, eax
0x180011689  js      short loc_1800116C1
0x18001168b  mov     r11d, [rbp+arg_0]
0x18001168f  test    r11d, r11d
0x180011692  jz      short loc_1800116C1
0x180011694  mov     rax, r14
0x180011697  mov     rdx, r12
0x18001169a  shr     rax, 1
0x18001169d  mov     r8, rdi; pszSrc
0x1800116a0  sub     rdx, rax; cchDest
0x1800116a3  mov     rcx, r13; pszDest
0x1800116a6  call    StringCchCopyW
0x1800116ab  test    eax, eax
0x1800116ad  js      short loc_1800116DA
0x1800116af  lea     eax, [r11+1]
0x1800116b3  mov     rcx, r15; Str
0x1800116b6  lea     rdi, [rdi+rax*2]
0x1800116ba  call    DhcpRegReadOptionDef
0x1800116bf  jmp     short loc_180011679
0x1800116c1  test    rbx, rbx
0x1800116c4  jz      short loc_1800116CF
0x1800116c6  lea     rcx, [rbp+arg_8]
0x1800116ca  call    DhcpPunycodeFree
0x1800116cf  lea     rcx, [rbp+pszSrc]
0x1800116d3  call    DhcpPunycodeFree
0x1800116d8  xor     eax, eax
0x1800116da  add     rsp, 48h
0x1800116de  pop     r15
0x1800116e0  pop     r14
0x1800116e2  pop     r13
0x1800116e4  pop     r12
0x1800116e6  pop     rdi
0x1800116e7  pop     rsi
0x1800116e8  pop     rbx
0x1800116e9  pop     rbp
0x1800116ea  retn
```
