# PlaliGetVersion(ushort const *,_PLALI_VERSION_ *)

- ea: `0x180130fb0`
- end: `0x180131202`
- name: `?PlaliGetVersion@@YAJPEBGPEAU_PLALI_VERSION_@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(LPCWSTR lpMachineName, struct _PLALI_VERSION_ *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062c70`
- `0x1800b3bb0`
- `0x180131208`

## callees

- `0x18012f320`
- `0x180130fb0`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wtol` at `0x180131103`
- `msvcrt!_wtol` at `0x18013119c`
- `msvcrt!_wtol` at `0x180131103`
- `msvcrt!_wtol` at `0x18013119c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013105c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013105c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801311be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801311ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801311be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801311ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18013108f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801310ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131130`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18013118b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18013108f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801310ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180131130`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18013118b`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18013102d`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18013102d`

## pseudocode

```c
__int64 __fastcall PlaliGetVersion(LPCWSTR lpMachineName, struct _PLALI_VERSION_ *a2)
{
  HKEY v3; // rcx
  __int64 v5; // rax
  LSTATUS v6; // ebx
  HKEY v7; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v13; // [rsp+48h] [rbp-B8h]
  wchar_t Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  cbData = 0;
  v3 = HKEY_LOCAL_MACHINE;
  phkResult = HKEY_LOCAL_MACHINE;
  Type = 0;
  v13 = 0;
  if ( lpMachineName )
  {
    v5 = -1;
    do
      ++v5;
    while ( lpMachineName[v5] );
    if ( v5 )
    {
      v6 = RegConnectRegistryW(lpMachineName, HKEY_LOCAL_MACHINE, &phkResult);
      if ( v6 )
        goto LABEL_18;
      v3 = phkResult;
    }
  }
  v6 = RegOpenKeyExW(v3, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey);
  if ( !v6 )
  {
    v6 = RegQueryValueExW(hKey, L"CurrentVersion", 0, &Type, 0, &cbData);
    if ( !v6 )
    {
      if ( cbData - 3 <= 0x204 && Type == 1 )
      {
        memset_0(Data, 0, 0x104u);
        v6 = RegQueryValueExW(hKey, L"CurrentVersion", 0, &Type, (LPBYTE)Data, &cbData);
        if ( v6 )
          goto LABEL_18;
        LODWORD(v13) = _wtol(Data);
      }
      v6 = RegQueryValueExW(hKey, L"CurrentBuildNumber", 0, &Type, 0, &cbData);
      if ( !v6 && cbData - 3 <= 0x204 && Type == 1 )
      {
        memset_0(Data, 0, 0x104u);
        v6 = RegQueryValueExW(hKey, L"CurrentBuildNumber", 0, &Type, (LPBYTE)Data, &cbData);
        if ( !v6 )
          DWORD2(v13) = _wtol(Data);
      }
    }
  }
LABEL_18:
  v7 = phkResult;
  *(_OWORD *)a2 = v13;
  if ( v7 && v7 != HKEY_LOCAL_MACHINE )
    RegCloseKey(v7);
  if ( hKey )
    RegCloseKey(hKey);
  return PlaliErrorToPdhStatus(v6);
}

```

## disassembly

```asm
0x180130fb0  mov     [rsp-8+arg_10], rbx
0x180130fb5  mov     [rsp-8+arg_18], rsi
0x180130fba  push    rbp
0x180130fbb  push    rdi
0x180130fbc  push    r14
0x180130fbe  lea     rbp, [rsp-180h]
0x180130fc6  sub     rsp, 280h
0x180130fcd  mov     rax, cs:__security_cookie
0x180130fd4  xor     rax, rsp
0x180130fd7  mov     [rbp+190h+var_20], rax
0x180130fde  xor     esi, esi
0x180130fe0  mov     r9, rcx
0x180130fe3  mov     [rsp+290h+hKey], rsi
0x180130fe8  mov     r14, 0FFFFFFFF80000002h
0x180130fef  mov     [rsp+290h+cbData], esi
0x180130ff3  mov     rcx, r14
0x180130ff6  mov     [rsp+290h+phkResult], rcx
0x180130ffb  xorps   xmm0, xmm0
0x180130ffe  mov     [rsp+290h+Type], esi
0x180131002  mov     rdi, rdx
0x180131005  movups  [rsp+290h+var_248], xmm0
0x18013100a  test    r9, r9
0x18013100d  jz      short loc_180131042
0x18013100f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180131013  inc     rax
0x180131016  cmp     [r9+rax*2], si
0x18013101b  jnz     short loc_180131013
0x18013101d  test    rax, rax
0x180131020  jz      short loc_180131042
0x180131022  lea     r8, [rsp+290h+phkResult]; phkResult
0x180131027  mov     rdx, r14; hKey
0x18013102a  mov     rcx, r9; lpMachineName
0x18013102d  call    cs:__imp_RegConnectRegistryW
0x180131033  mov     ebx, eax
0x180131035  test    eax, eax
0x180131037  jnz     loc_1801311A6
0x18013103d  mov     rcx, [rsp+290h+phkResult]; hKey
0x180131042  lea     rax, [rsp+290h+hKey]
0x180131047  mov     r9d, 20019h; samDesired
0x18013104d  xor     r8d, r8d; ulOptions
0x180131050  mov     [rsp+290h+var_270], rax; phkResult
0x180131055  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18013105c  call    cs:__imp_RegOpenKeyExW
0x180131062  mov     ebx, eax
0x180131064  test    eax, eax
0x180131066  jnz     loc_1801311A6
0x18013106c  mov     rcx, [rsp+290h+hKey]; hKey
0x180131071  lea     rax, [rsp+290h+cbData]
0x180131076  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18013107b  lea     r9, [rsp+290h+Type]; lpType
0x180131080  xor     r8d, r8d; lpReserved
0x180131083  mov     [rsp+290h+var_270], rsi; lpData
0x180131088  lea     rdx, aCurrentversion; "CurrentVersion"
0x18013108f  call    cs:__imp_RegQueryValueExW
0x180131095  mov     ebx, eax
0x180131097  test    eax, eax
0x180131099  jnz     loc_1801311A6
0x18013109f  mov     eax, [rsp+290h+cbData]
0x1801310a3  add     eax, 0FFFFFFFDh
0x1801310a6  cmp     eax, 204h
0x1801310ab  ja      short loc_18013110D
0x1801310ad  cmp     [rsp+290h+Type], 1
0x1801310b2  jnz     short loc_18013110D
0x1801310b4  xor     edx, edx; Val
0x1801310b6  lea     rcx, [rsp+290h+Data]; void *
0x1801310bb  mov     r8d, 104h; Size
0x1801310c1  call    memset_0
0x1801310c6  mov     rcx, [rsp+290h+hKey]; hKey
0x1801310cb  lea     rax, [rsp+290h+cbData]
0x1801310d0  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1801310d5  lea     r9, [rsp+290h+Type]; lpType
0x1801310da  lea     rax, [rsp+290h+Data]
0x1801310df  xor     r8d, r8d; lpReserved
0x1801310e2  lea     rdx, aCurrentversion; "CurrentVersion"
0x1801310e9  mov     [rsp+290h+var_270], rax; lpData
0x1801310ee  call    cs:__imp_RegQueryValueExW
0x1801310f4  mov     ebx, eax
0x1801310f6  test    eax, eax
0x1801310f8  jnz     loc_1801311A6
0x1801310fe  lea     rcx, [rsp+290h+Data]; String
0x180131103  call    cs:__imp__wtol
0x180131109  mov     dword ptr [rsp+290h+var_248], eax
0x18013110d  mov     rcx, [rsp+290h+hKey]; hKey
0x180131112  lea     rax, [rsp+290h+cbData]
0x180131117  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18013111c  lea     r9, [rsp+290h+Type]; lpType
0x180131121  xor     r8d, r8d; lpReserved
0x180131124  mov     [rsp+290h+var_270], rsi; lpData
0x180131129  lea     rdx, aCurrentbuildnu; "CurrentBuildNumber"
0x180131130  call    cs:__imp_RegQueryValueExW
0x180131136  mov     ebx, eax
0x180131138  test    eax, eax
0x18013113a  jnz     short loc_1801311A6
0x18013113c  mov     eax, [rsp+290h+cbData]
0x180131140  add     eax, 0FFFFFFFDh
0x180131143  cmp     eax, 204h
0x180131148  ja      short loc_1801311A6
0x18013114a  cmp     [rsp+290h+Type], 1
0x18013114f  jnz     short loc_1801311A6
0x180131151  xor     edx, edx; Val
0x180131153  lea     rcx, [rsp+290h+Data]; void *
0x180131158  mov     r8d, 104h; Size
0x18013115e  call    memset_0
0x180131163  mov     rcx, [rsp+290h+hKey]; hKey
0x180131168  lea     rax, [rsp+290h+cbData]
0x18013116d  mov     [rsp+290h+lpcbData], rax; lpcbData
0x180131172  lea     r9, [rsp+290h+Type]; lpType
0x180131177  lea     rax, [rsp+290h+Data]
0x18013117c  xor     r8d, r8d; lpReserved
0x18013117f  lea     rdx, aCurrentbuildnu; "CurrentBuildNumber"
0x180131186  mov     [rsp+290h+var_270], rax; lpData
0x18013118b  call    cs:__imp_RegQueryValueExW
0x180131191  mov     ebx, eax
0x180131193  test    eax, eax
0x180131195  jnz     short loc_1801311A6
0x180131197  lea     rcx, [rsp+290h+Data]; String
0x18013119c  call    cs:__imp__wtol
0x1801311a2  mov     dword ptr [rsp+290h+var_248+8], eax
0x1801311a6  movups  xmm0, [rsp+290h+var_248]
0x1801311ab  mov     rcx, [rsp+290h+phkResult]; hKey
0x1801311b0  movdqu  xmmword ptr [rdi], xmm0
0x1801311b4  test    rcx, rcx
0x1801311b7  jz      short loc_1801311C4
0x1801311b9  cmp     rcx, r14
0x1801311bc  jz      short loc_1801311C4
0x1801311be  call    cs:__imp_RegCloseKey
0x1801311c4  mov     rcx, [rsp+290h+hKey]; hKey
0x1801311c9  test    rcx, rcx
0x1801311cc  jz      short loc_1801311D4
0x1801311ce  call    cs:__imp_RegCloseKey
0x1801311d4  mov     ecx, ebx; unsigned int
0x1801311d6  call    ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
0x1801311db  mov     rcx, [rbp+190h+var_20]
0x1801311e2  xor     rcx, rsp; StackCookie
0x1801311e5  call    __security_check_cookie
0x1801311ea  lea     r11, [rsp+290h+var_10]
0x1801311f2  mov     rbx, [r11+30h]
0x1801311f6  mov     rsi, [r11+38h]
0x1801311fa  mov     rsp, r11
0x1801311fd  pop     r14
0x1801311ff  pop     rdi
0x180131200  pop     rbp
0x180131201  retn
```
