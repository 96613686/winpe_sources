# IDriverReadRegistryData

- ea: `0x180005100`
- end: `0x180005492`
- name: `IDriverReadRegistryData`
- size: `914`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004b70`

## callees

- `0x180005100`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000523e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005292`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005311`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005362`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800053d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000523e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005292`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005311`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005362`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800053d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005466`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005456`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005466`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005421`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000542f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005421`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000542f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000539c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800052d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000539c`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000518e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180005200`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x18000518e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x180005200`

## string_xrefs

- `0x180005178`: `Software\Microsoft\AudioCompressionManager\DriverCache`
- `0x180005306`: `aFormatTagCache`
- `0x1800053cd`: `aFilterTagCache`

## pseudocode

```c
__int64 __fastcall IDriverReadRegistryData(__int64 a1)
{
  int v1; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  WCHAR *v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // r8
  WCHAR *v9; // rcx
  HLOCAL v10; // rdi
  HLOCAL v11; // rsi
  DWORD v12; // ebx
  int v13; // ecx
  DWORD v14; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v17[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE lpData[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[144]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = *(_DWORD *)(a1 + 52) & 7;
  *(_DWORD *)Data = 0;
  *(_DWORD *)lpData = 0;
  *(_DWORD *)v17 = 0;
  Type = 0;
  cbData = 0;
  phkResult = 0;
  hKey = 0;
  if ( (_BYTE)v1 != 1 )
    return 8;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\AudioCompressionManager\\DriverCache", &phkResult) )
  {
    v5 = 2147483646;
    v6 = (WCHAR *)(a1 + 120);
    v7 = 144;
    v8 = SubKey;
    do
    {
      if ( !v5 )
        break;
      if ( !*v6 )
        break;
      *v8++ = *v6++;
      --v5;
      --v7;
    }
    while ( v7 );
    v9 = v8 - 1;
    if ( v7 )
      v9 = v8;
    *v9 = 0;
    if ( RegOpenKeyW(phkResult, SubKey, &hKey)
      || (cbData = 4, RegQueryValueExW(hKey, gszValfdwSupport, 0, &Type, Data, &cbData))
      || Type != 4
      || cbData != 4
      || (cbData = 4, RegQueryValueExW(hKey, gszValcFormatTags, 0, &Type, lpData, &cbData))
      || Type != 4
      || cbData != 4 )
    {
      v4 = 512;
      goto LABEL_42;
    }
    v10 = 0;
    v11 = 0;
    if ( *(_DWORD *)lpData )
    {
      v12 = 8 * *(_DWORD *)lpData;
      v10 = LocalAlloc(0x40u, (unsigned int)(8 * *(_DWORD *)lpData));
      if ( !v10 )
      {
        v4 = 7;
        goto LABEL_42;
      }
      cbData = v12;
      if ( RegQueryValueExW(hKey, gszValaFormatTagCache, 0, &Type, (LPBYTE)v10, &cbData) || Type != 3 || v12 != cbData )
      {
        v4 = 512;
LABEL_38:
        LocalFree(v10);
LABEL_39:
        if ( v11 )
          LocalFree(v11);
        goto LABEL_42;
      }
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, gszValcFilterTags, 0, &Type, v17, &cbData) && Type == 4 && cbData == 4 )
    {
      v13 = *(_DWORD *)v17;
      if ( !*(_DWORD *)v17 )
      {
LABEL_35:
        v4 = 0;
        *(_DWORD *)(a1 + 60) = *(_DWORD *)Data;
        *(_DWORD *)(a1 + 64) = *(_DWORD *)lpData;
        *(_QWORD *)(a1 + 68) = v10;
        *(_DWORD *)(a1 + 76) = v13;
        *(_QWORD *)(a1 + 80) = v11;
        goto LABEL_42;
      }
      v14 = 8 * *(_DWORD *)v17;
      v11 = LocalAlloc(0x40u, (unsigned int)(8 * *(_DWORD *)v17));
      if ( !v11 )
      {
        v4 = 7;
        goto LABEL_37;
      }
      cbData = v14;
      if ( !RegQueryValueExW(hKey, gszValaFilterTagCache, 0, &Type, (LPBYTE)v11, &cbData) && Type == 3 && v14 == cbData )
      {
        v13 = *(_DWORD *)v17;
        goto LABEL_35;
      }
    }
    v4 = 512;
LABEL_37:
    if ( !v10 )
      goto LABEL_39;
    goto LABEL_38;
  }
  phkResult = 0;
  v4 = 7;
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v4;
}

```

## disassembly

```asm
0x180005100  push    rbp
0x180005102  push    r14
0x180005104  push    r15
0x180005106  lea     rbp, [rsp-90h]
0x18000510e  sub     rsp, 190h
0x180005115  mov     rax, cs:__security_cookie
0x18000511c  xor     rax, rsp
0x18000511f  mov     [rbp+0A0h+var_20], rax
0x180005126  mov     eax, [rcx+34h]
0x180005129  xor     r15d, r15d
0x18000512c  and     eax, 7
0x18000512f  mov     dword ptr [rsp+1A0h+Data], r15d
0x180005134  mov     dword ptr [rsp+1A0h+var_164], r15d
0x180005139  mov     r14, rcx
0x18000513c  mov     dword ptr [rsp+1A0h+var_168], r15d
0x180005141  mov     [rsp+1A0h+Type], r15d
0x180005146  mov     [rsp+1A0h+cbData], r15d
0x18000514b  mov     [rsp+1A0h+phkResult], r15
0x180005150  mov     [rsp+1A0h+hKey], r15
0x180005155  cmp     al, 1
0x180005157  jz      short loc_180005163
0x180005159  mov     eax, 8
0x18000515e  jmp     loc_180005476
0x180005163  mov     [rsp+1A0h+arg_8], rbx
0x18000516b  lea     r8, [rsp+1A0h+phkResult]; phkResult
0x180005170  mov     [rsp+1A0h+arg_10], rsi
0x180005178  lea     rdx, gszDriverCache; "Software\\Microsoft\\AudioCompressionMa"...
0x18000517f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005186  mov     [rsp+1A0h+arg_18], rdi
0x18000518e  call    cs:__imp_RegOpenKeyW
0x180005194  test    eax, eax
0x180005196  jz      short loc_1800051A7
0x180005198  mov     [rsp+1A0h+phkResult], r15
0x18000519d  mov     ebx, 7
0x1800051a2  jmp     loc_18000543C
0x1800051a7  mov     eax, 7FFFFFFEh
0x1800051ac  lea     rdx, [r14+78h]
0x1800051b0  mov     r9d, 90h
0x1800051b6  lea     r8, [rsp+1A0h+SubKey]
0x1800051bb  nop     dword ptr [rax+rax+00h]
0x1800051c0  test    rax, rax
0x1800051c3  jz      short loc_1800051E2
0x1800051c5  movzx   ecx, word ptr [rdx]
0x1800051c8  test    cx, cx
0x1800051cb  jz      short loc_1800051E2
0x1800051cd  mov     [r8], cx
0x1800051d1  add     rdx, 2
0x1800051d5  add     r8, 2
0x1800051d9  dec     rax
0x1800051dc  sub     r9, 1
0x1800051e0  jnz     short loc_1800051C0
0x1800051e2  lea     rcx, [r8-2]
0x1800051e6  test    r9, r9
0x1800051e9  lea     rdx, [rsp+1A0h+SubKey]; lpSubKey
0x1800051ee  cmovnz  rcx, r8
0x1800051f2  lea     r8, [rsp+1A0h+hKey]; phkResult
0x1800051f7  mov     [rcx], r15w
0x1800051fb  mov     rcx, [rsp+1A0h+phkResult]; hKey
0x180005200  call    cs:__imp_RegOpenKeyW
0x180005206  test    eax, eax
0x180005208  jnz     loc_180005437
0x18000520e  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180005213  lea     rax, [rsp+1A0h+cbData]
0x180005218  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x18000521d  lea     r9, [rsp+1A0h+Type]; lpType
0x180005222  lea     rax, [rsp+1A0h+Data]
0x180005227  mov     [rsp+1A0h+cbData], 4
0x18000522f  xor     r8d, r8d; lpReserved
0x180005232  mov     [rsp+1A0h+lpData], rax; lpData
0x180005237  lea     rdx, gszValfdwSupport; "fdwSupport"
0x18000523e  call    cs:__imp_RegQueryValueExW
0x180005244  test    eax, eax
0x180005246  jnz     loc_180005437
0x18000524c  cmp     [rsp+1A0h+Type], 4
0x180005251  jnz     loc_180005437
0x180005257  cmp     [rsp+1A0h+cbData], 4
0x18000525c  jnz     loc_180005437
0x180005262  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180005267  lea     rax, [rsp+1A0h+cbData]
0x18000526c  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180005271  lea     r9, [rsp+1A0h+Type]; lpType
0x180005276  lea     rax, [rsp+1A0h+var_164]
0x18000527b  mov     [rsp+1A0h+cbData], 4
0x180005283  xor     r8d, r8d; lpReserved
0x180005286  mov     [rsp+1A0h+lpData], rax; lpData
0x18000528b  lea     rdx, gszValcFormatTags; "cFormatTags"
0x180005292  call    cs:__imp_RegQueryValueExW
0x180005298  test    eax, eax
0x18000529a  jnz     loc_180005437
0x1800052a0  cmp     [rsp+1A0h+Type], 4
0x1800052a5  jnz     loc_180005437
0x1800052ab  cmp     [rsp+1A0h+cbData], 4
0x1800052b0  jnz     loc_180005437
0x1800052b6  mov     eax, dword ptr [rsp+1A0h+var_164]
0x1800052ba  mov     rdi, r15
0x1800052bd  mov     rsi, r15
0x1800052c0  test    eax, eax
0x1800052c2  jz      short loc_180005332
0x1800052c4  lea     ebx, ds:0[rax*8]
0x1800052cb  mov     ecx, 40h ; '@'; uFlags
0x1800052d0  mov     edx, ebx; uBytes
0x1800052d2  call    cs:__imp_LocalAlloc
0x1800052d8  mov     rdi, rax
0x1800052db  test    rax, rax
0x1800052de  jnz     short loc_1800052EA
0x1800052e0  mov     ebx, 7
0x1800052e5  jmp     loc_18000543C
0x1800052ea  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800052ef  lea     rax, [rsp+1A0h+cbData]
0x1800052f4  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800052f9  lea     r9, [rsp+1A0h+Type]; lpType
0x1800052fe  xor     r8d, r8d; lpReserved
0x180005301  mov     [rsp+1A0h+lpData], rdi; lpData
0x180005306  lea     rdx, gszValaFormatTagCache; "aFormatTagCache"
0x18000530d  mov     [rsp+1A0h+cbData], ebx
0x180005311  call    cs:__imp_RegQueryValueExW
0x180005317  test    eax, eax
0x180005319  jnz     short loc_180005328
0x18000531b  cmp     [rsp+1A0h+Type], 3
0x180005320  jnz     short loc_180005328
0x180005322  cmp     ebx, [rsp+1A0h+cbData]
0x180005326  jz      short loc_180005332
0x180005328  mov     ebx, 200h
0x18000532d  jmp     loc_18000541E
0x180005332  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180005337  lea     rax, [rsp+1A0h+cbData]
0x18000533c  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x180005341  lea     r9, [rsp+1A0h+Type]; lpType
0x180005346  lea     rax, [rsp+1A0h+var_168]
0x18000534b  mov     [rsp+1A0h+cbData], 4
0x180005353  xor     r8d, r8d; lpReserved
0x180005356  mov     [rsp+1A0h+lpData], rax; lpData
0x18000535b  lea     rdx, gszValcFilterTags; "cFilterTags"
0x180005362  call    cs:__imp_RegQueryValueExW
0x180005368  test    eax, eax
0x18000536a  jnz     loc_180005414
0x180005370  cmp     [rsp+1A0h+Type], 4
0x180005375  jnz     loc_180005414
0x18000537b  cmp     [rsp+1A0h+cbData], 4
0x180005380  jnz     loc_180005414
0x180005386  mov     ecx, dword ptr [rsp+1A0h+var_168]
0x18000538a  test    ecx, ecx
0x18000538c  jz      short loc_1800053F3
0x18000538e  lea     ebx, ds:0[rcx*8]
0x180005395  mov     ecx, 40h ; '@'; uFlags
0x18000539a  mov     edx, ebx; uBytes
0x18000539c  call    cs:__imp_LocalAlloc
0x1800053a2  mov     rsi, rax
0x1800053a5  test    rax, rax
0x1800053a8  jnz     short loc_1800053B1
0x1800053aa  mov     ebx, 7
0x1800053af  jmp     short loc_180005419
0x1800053b1  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800053b6  lea     rax, [rsp+1A0h+cbData]
0x1800053bb  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x1800053c0  lea     r9, [rsp+1A0h+Type]; lpType
0x1800053c5  xor     r8d, r8d; lpReserved
0x1800053c8  mov     [rsp+1A0h+lpData], rsi; lpData
0x1800053cd  lea     rdx, gszValaFilterTagCache; "aFilterTagCache"
0x1800053d4  mov     [rsp+1A0h+cbData], ebx
0x1800053d8  call    cs:__imp_RegQueryValueExW
0x1800053de  test    eax, eax
0x1800053e0  jnz     short loc_180005414
0x1800053e2  cmp     [rsp+1A0h+Type], 3
0x1800053e7  jnz     short loc_180005414
0x1800053e9  cmp     ebx, [rsp+1A0h+cbData]
0x1800053ed  jnz     short loc_180005414
0x1800053ef  mov     ecx, dword ptr [rsp+1A0h+var_168]
0x1800053f3  mov     eax, dword ptr [rsp+1A0h+Data]
0x1800053f7  mov     ebx, r15d
0x1800053fa  mov     [r14+3Ch], eax
0x1800053fe  mov     eax, dword ptr [rsp+1A0h+var_164]
0x180005402  mov     [r14+40h], eax
0x180005406  mov     [r14+44h], rdi
0x18000540a  mov     [r14+4Ch], ecx
0x18000540e  mov     [r14+50h], rsi
0x180005412  jmp     short loc_18000543C
0x180005414  mov     ebx, 200h
0x180005419  test    rdi, rdi
0x18000541c  jz      short loc_180005427
0x18000541e  mov     rcx, rdi; hMem
0x180005421  call    cs:__imp_LocalFree
0x180005427  test    rsi, rsi
0x18000542a  jz      short loc_18000543C
0x18000542c  mov     rcx, rsi; hMem
0x18000542f  call    cs:__imp_LocalFree
0x180005435  jmp     short loc_18000543C
0x180005437  mov     ebx, 200h
0x18000543c  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180005441  mov     rdi, [rsp+1A0h+arg_18]
0x180005449  mov     rsi, [rsp+1A0h+arg_10]
0x180005451  test    rcx, rcx
0x180005454  jz      short loc_18000545C
0x180005456  call    cs:__imp_RegCloseKey
0x18000545c  mov     rcx, [rsp+1A0h+phkResult]; hKey
0x180005461  test    rcx, rcx
0x180005464  jz      short loc_18000546C
0x180005466  call    cs:__imp_RegCloseKey
0x18000546c  mov     eax, ebx
0x18000546e  mov     rbx, [rsp+1A0h+arg_8]
0x180005476  mov     rcx, [rbp+0A0h+var_20]
0x18000547d  xor     rcx, rsp; StackCookie
0x180005480  call    __security_check_cookie
0x180005485  add     rsp, 190h
0x18000548c  pop     r15
0x18000548e  pop     r14
0x180005490  pop     rbp
0x180005491  retn
```
