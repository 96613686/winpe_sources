# DavReadRegistryBypassServerNames

- ea: `0x180006930`
- end: `0x180006b1a`
- name: `DavReadRegistryBypassServerNames`
- size: `490`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180005a50`

## callees

- `0x180006930`
- `0x180010be8`

## import_xrefs

- `msvcrt!tolower` at `0x180006aea`
- `msvcrt!tolower` at `0x180006aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006970`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006970`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006abf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006abf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800069f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006a9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800069f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006a9a`
- `KERNEL32!LocalAlloc` at `0x180006a1b`
- `KERNEL32!LocalAlloc` at `0x180006a1b`
- `KERNEL32!LocalFree` at `0x180006aa9`
- `KERNEL32!LocalFree` at `0x180006aa9`

## string_xrefs

- `0x18000695b`: `System\CurrentControlSet\Services\WebClient\Parameters`

## pseudocode

```c
__int64 __fastcall DavReadRegistryBypassServerNames(_QWORD *a1)
{
  __int64 v1; // rbp
  _WORD *pvData; // rsi
  unsigned int v4; // ebx
  LSTATUS ValueW; // eax
  __int64 v6; // rbx
  DWORD LastError; // eax
  __int64 v8; // rdi
  __int16 v9; // ax
  DWORD pcbData; // [rsp+70h] [rbp+8h] BYREF
  DWORD pdwType; // [rsp+78h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+18h] BYREF

  LODWORD(v1) = 0;
  pdwType = 0;
  pcbData = 0;
  hkey = 0;
  *a1 = 0;
  pvData = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\WebClient\\Parameters", 0, 1u, &hkey);
  if ( v4 )
  {
    hkey = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, v4);
  }
  else
  {
    ValueW = RegGetValueW(hkey, 0, L"AuthForwardServerList", 0x20u, &pdwType, 0, &pcbData);
    v4 = ValueW;
    if ( !ValueW || ValueW == 234 )
    {
      pcbData += 4;
      pvData = LocalAlloc(0x40u, pcbData);
      if ( pvData )
      {
        v4 = RegGetValueW(hkey, 0, L"AuthForwardServerList", 0x20u, &pdwType, pvData, &pcbData);
        if ( v4 )
        {
          LocalFree(pvData);
          pvData = 0;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          LastError = GetLastError();
          WPP_SF_d(v6, 53, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids, LastError);
        }
        v4 = 14;
      }
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  *a1 = pvData;
  if ( pvData && *pvData )
  {
    do
    {
      if ( pvData[(unsigned int)v1] )
      {
        do
        {
          v8 = (unsigned int)v1;
          v9 = tolower((unsigned __int16)pvData[v8]);
          pvData = (_WORD *)*a1;
          v1 = (unsigned int)(v1 + 1);
          pvData[v8] = v9;
        }
        while ( pvData[v1] );
      }
      v1 = (unsigned int)(v1 + 1);
    }
    while ( pvData[v1] );
  }
  return v4;
}

```

## disassembly

```asm
0x180006930  mov     rax, rsp
0x180006933  push    rbx
0x180006934  push    rbp
0x180006935  push    rsi
0x180006936  push    r14
0x180006938  sub     rsp, 48h
0x18000693c  xor     ebp, ebp
0x18000693e  mov     r14, rcx
0x180006941  mov     [rax+10h], ebp
0x180006944  mov     r9d, 1; samDesired
0x18000694a  mov     [rax+8], ebp
0x18000694d  xor     r8d, r8d; ulOptions
0x180006950  mov     [rax+18h], rbp
0x180006954  lea     rax, [rax+18h]
0x180006958  mov     [rcx], rbp
0x18000695b  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\We"...
0x180006962  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006969  mov     [rsp+68h+phkResult], rax; phkResult
0x18000696e  mov     esi, ebp
0x180006970  call    cs:__imp_RegOpenKeyExW
0x180006976  mov     ebx, eax
0x180006978  test    eax, eax
0x18000697a  jz      short loc_1800069C2
0x18000697c  mov     [rsp+68h+hkey], rbp
0x180006984  mov     rcx, cs:WPP_GLOBAL_Control
0x18000698b  lea     rax, WPP_GLOBAL_Control
0x180006992  cmp     rcx, rax
0x180006995  jz      loc_180006AB2
0x18000699b  test    byte ptr [rcx+1Ch], 1
0x18000699f  jz      loc_180006AB2
0x1800069a5  mov     rcx, [rcx+10h]
0x1800069a9  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x1800069b0  mov     edx, 34h ; '4'
0x1800069b5  mov     r9d, ebx
0x1800069b8  call    WPP_SF_d
0x1800069bd  jmp     loc_180006AB2
0x1800069c2  mov     rcx, [rsp+68h+hkey]; hkey
0x1800069ca  lea     rax, [rsp+68h+arg_0]
0x1800069cf  mov     [rsp+68h+pcbData], rax; pcbData
0x1800069d4  lea     r8, Value; "AuthForwardServerList"
0x1800069db  lea     rax, [rsp+68h+pdwType]
0x1800069e0  mov     [rsp+68h+pvData], rbp; pvData
0x1800069e5  mov     r9d, 20h ; ' '; dwFlags
0x1800069eb  mov     [rsp+68h+phkResult], rax; pdwType
0x1800069f0  xor     edx, edx; lpSubKey
0x1800069f2  call    cs:__imp_RegGetValueW
0x1800069f8  mov     ebx, eax
0x1800069fa  test    eax, eax
0x1800069fc  jz      short loc_180006A09
0x1800069fe  cmp     eax, 0EAh
0x180006a03  jnz     loc_180006AB2
0x180006a09  mov     eax, [rsp+68h+arg_0]
0x180006a0d  mov     ecx, 40h ; '@'; uFlags
0x180006a12  add     eax, 4
0x180006a15  mov     edx, eax; uBytes
0x180006a17  mov     [rsp+68h+arg_0], eax
0x180006a1b  call    cs:__imp_LocalAlloc
0x180006a21  mov     rsi, rax
0x180006a24  test    rax, rax
0x180006a27  jnz     short loc_180006A6A
0x180006a29  mov     rbx, cs:WPP_GLOBAL_Control
0x180006a30  lea     rax, WPP_GLOBAL_Control
0x180006a37  cmp     rbx, rax
0x180006a3a  jz      short loc_180006A63
0x180006a3c  test    byte ptr [rbx+1Ch], 1
0x180006a40  jz      short loc_180006A63
0x180006a42  mov     rbx, [rbx+10h]
0x180006a46  call    cs:__imp_GetLastError
0x180006a4c  mov     edx, 35h ; '5'
0x180006a51  lea     r8, WPP_db9184fc95f634e81eb114a7689fd6a6_Traceguids
0x180006a58  mov     r9d, eax
0x180006a5b  mov     rcx, rbx
0x180006a5e  call    WPP_SF_d
0x180006a63  mov     ebx, 0Eh
0x180006a68  jmp     short loc_180006AB2
0x180006a6a  mov     rcx, [rsp+68h+hkey]; hkey
0x180006a72  lea     rax, [rsp+68h+arg_0]
0x180006a77  mov     [rsp+68h+pcbData], rax; pcbData
0x180006a7c  lea     r8, Value; "AuthForwardServerList"
0x180006a83  lea     rax, [rsp+68h+pdwType]
0x180006a88  mov     [rsp+68h+pvData], rsi; pvData
0x180006a8d  mov     r9d, 20h ; ' '; dwFlags
0x180006a93  mov     [rsp+68h+phkResult], rax; pdwType
0x180006a98  xor     edx, edx; lpSubKey
0x180006a9a  call    cs:__imp_RegGetValueW
0x180006aa0  mov     ebx, eax
0x180006aa2  test    eax, eax
0x180006aa4  jz      short loc_180006AB2
0x180006aa6  mov     rcx, rsi; hMem
0x180006aa9  call    cs:__imp_LocalFree
0x180006aaf  mov     rsi, rbp
0x180006ab2  mov     rcx, [rsp+68h+hkey]; hKey
0x180006aba  test    rcx, rcx
0x180006abd  jz      short loc_180006AC5
0x180006abf  call    cs:__imp_RegCloseKey
0x180006ac5  mov     [r14], rsi
0x180006ac8  test    rsi, rsi
0x180006acb  jz      short loc_180006B0E
0x180006acd  cmp     [rsi], bp
0x180006ad0  jz      short loc_180006B0E
0x180006ad2  mov     [rsp+68h+var_28], rdi
0x180006ad7  mov     eax, ebp
0x180006ad9  cmp     word ptr [rsi+rax*2], 0
0x180006ade  jz      short loc_180006B00
0x180006ae0  mov     eax, ebp
0x180006ae2  lea     rdi, [rax+rax]
0x180006ae6  movzx   ecx, word ptr [rdi+rsi]; C
0x180006aea  call    cs:__imp_tolower
0x180006af0  mov     rsi, [r14]
0x180006af3  inc     ebp
0x180006af5  mov     [rsi+rdi], ax
0x180006af9  cmp     word ptr [rsi+rbp*2], 0
0x180006afe  jnz     short loc_180006AE0
0x180006b00  inc     ebp
0x180006b02  cmp     word ptr [rsi+rbp*2], 0
0x180006b07  jnz     short loc_180006AD7
0x180006b09  mov     rdi, [rsp+68h+var_28]
0x180006b0e  mov     eax, ebx
0x180006b10  add     rsp, 48h
0x180006b14  pop     r14
0x180006b16  pop     rsi
0x180006b17  pop     rbp
0x180006b18  pop     rbx
0x180006b19  retn
```
