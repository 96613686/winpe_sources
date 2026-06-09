# DwGetCalledIdInfo

- ea: `0x1800173a4`
- end: `0x1800175d2`
- name: `DwGetCalledIdInfo`
- size: `558`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800030f0`
- `0x18000de88`

## callees

- `0x180016b30`
- `0x1800173a4`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017508`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017508`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017593`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017448`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017517`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800174e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017552`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800174e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017552`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800174a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017580`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001743e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001743e`

## pseudocode

```c
__int64 __fastcall DwGetCalledIdInfo(HKEY hKey, __int64 a2)
{
  HKEY v2; // rdi
  HKEY v4; // r14
  int v5; // edi
  DWORD LastError; // ebx
  unsigned __int8 *v7; // rcx
  bool v8; // zf
  LSTATUS v9; // eax
  BYTE *v10; // rax
  void *v11; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[256]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  cbData = 0;
  Type = 0;
  hKeya = 0;
  v4 = hKey;
  phkResult = 0;
  if ( hKey )
  {
LABEL_10:
    *(_QWORD *)(a2 + 40) = 0;
    v9 = RegQueryValueExW(v4, L"CalledIDInformation", 0, &Type, 0, &cbData);
    LastError = v9;
    if ( !v9 || v9 == 234 )
    {
      v10 = (BYTE *)LocalAlloc(0x40u, cbData + 8LL);
      *(_QWORD *)(a2 + 40) = v10;
      if ( v10 )
      {
        LastError = RegQueryValueExW(v4, L"CalledIDInformation", 0, &Type, v10 + 4, &cbData);
        if ( !LastError )
          **(_DWORD **)(a2 + 40) = cbData;
      }
      else
      {
        LastError = GetLastError();
      }
    }
    goto LABEL_18;
  }
  v5 = (unsigned __int16)*(_DWORD *)(a2 + 96);
  memset_0(WideCharStr, 0, sizeof(WideCharStr));
  if ( !MultiByteToWideChar(0, 0, (LPCCH)(a2 + 133), -1, WideCharStr, 256) )
  {
    LastError = GetLastError();
    goto LABEL_20;
  }
  v7 = (unsigned __int8 *)WideCharStr;
  if ( v5 )
    v7 = (unsigned __int8 *)(a2 + 100);
  LastError = lrGetRegKeyFromGuid(v7, &hKeya, 0, v5 == 0);
  if ( LastError )
  {
    v2 = hKeya;
  }
  else
  {
    v8 = v5 == 0;
    v2 = hKeya;
    if ( !v8 )
    {
      v4 = hKeya;
      goto LABEL_10;
    }
    LastError = RegOpenKeyExW(hKeya, L"Clients\\Ras", 0, 0xF003Fu, &phkResult);
    if ( !LastError )
    {
      v4 = phkResult;
      goto LABEL_10;
    }
  }
LABEL_18:
  if ( v2 )
    RegCloseKey(v2);
LABEL_20:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( LastError )
  {
    v11 = *(void **)(a2 + 40);
    if ( v11 )
    {
      LocalFree(v11);
      *(_QWORD *)(a2 + 40) = 0;
    }
    if ( LastError == 2 )
      return 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800173a4  mov     [rsp-8+arg_10], rbx
0x1800173a9  mov     [rsp-8+arg_18], rsi
0x1800173ae  push    rbp
0x1800173af  push    rdi
0x1800173b0  push    r14
0x1800173b2  lea     rbp, [rsp-160h]
0x1800173ba  sub     rsp, 260h
0x1800173c1  mov     rax, cs:__security_cookie
0x1800173c8  xor     rax, rsp
0x1800173cb  mov     [rbp+170h+var_20], rax
0x1800173d2  xor     edi, edi
0x1800173d4  mov     [rsp+270h+cbData], 0
0x1800173dc  mov     [rsp+270h+Type], 0
0x1800173e4  mov     rsi, rdx
0x1800173e7  mov     [rsp+270h+hKey], rdi
0x1800173ec  mov     r14, rcx
0x1800173ef  mov     [rsp+270h+phkResult], rdi
0x1800173f4  test    rcx, rcx
0x1800173f7  jnz     loc_1800174BB
0x1800173fd  mov     edi, [rdx+60h]
0x180017400  mov     ebx, ecx
0x180017402  and     edi, 0FFFFh
0x180017408  lea     rcx, [rsp+270h+WideCharStr]; void *
0x18001740d  mov     r8d, 200h; Size
0x180017413  setz    bl
0x180017416  xor     edx, edx; Val
0x180017418  call    memset_0
0x18001741d  lea     rax, [rsp+270h+WideCharStr]
0x180017422  mov     [rsp+270h+cchWideChar], 100h; cchWideChar
0x18001742a  lea     r8, [rsi+85h]; lpMultiByteStr
0x180017431  mov     [rsp+270h+lpWideCharStr], rax; lpWideCharStr
0x180017436  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001743a  xor     edx, edx; dwFlags
0x18001743c  xor     ecx, ecx; CodePage
0x18001743e  call    cs:__imp_MultiByteToWideChar
0x180017444  test    eax, eax
0x180017446  jnz     short loc_180017455
0x180017448  call    cs:__imp_GetLastError
0x18001744e  mov     ebx, eax
0x180017450  jmp     loc_180017576
0x180017455  lea     rcx, [rsp+270h+WideCharStr]
0x18001745a  test    edi, edi
0x18001745c  jz      short loc_180017462
0x18001745e  lea     rcx, [rsi+64h]; unsigned __int8 *
0x180017462  mov     r9d, ebx; int
0x180017465  lea     rdx, [rsp+270h+hKey]; HKEY *
0x18001746a  xor     r8d, r8d; unsigned int *
0x18001746d  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x180017472  mov     ebx, eax
0x180017474  test    eax, eax
0x180017476  jnz     loc_180017526
0x18001747c  test    edi, edi
0x18001747e  mov     rdi, [rsp+270h+hKey]
0x180017483  jnz     loc_180017521
0x180017489  lea     rax, [rsp+270h+phkResult]
0x18001748e  mov     r9d, 0F003Fh; samDesired
0x180017494  xor     r8d, r8d; ulOptions
0x180017497  mov     [rsp+270h+lpWideCharStr], rax; phkResult
0x18001749c  lea     rdx, aClientsRas; "Clients\\Ras"
0x1800174a3  mov     rcx, rdi; hKey
0x1800174a6  call    cs:__imp_RegOpenKeyExW
0x1800174ac  mov     ebx, eax
0x1800174ae  test    eax, eax
0x1800174b0  jnz     loc_180017568
0x1800174b6  mov     r14, [rsp+270h+phkResult]
0x1800174bb  lea     rax, [rsp+270h+cbData]
0x1800174c0  mov     qword ptr [rsi+28h], 0
0x1800174c8  mov     qword ptr [rsp+270h+cchWideChar], rax; lpcbData
0x1800174cd  lea     r9, [rsp+270h+Type]; lpType
0x1800174d2  xor     r8d, r8d; lpReserved
0x1800174d5  mov     [rsp+270h+lpWideCharStr], 0; lpData
0x1800174de  lea     rdx, aCalledidinform; "CalledIDInformation"
0x1800174e5  mov     rcx, r14; hKey
0x1800174e8  call    cs:__imp_RegQueryValueExW
0x1800174ee  mov     ebx, eax
0x1800174f0  test    eax, eax
0x1800174f2  jz      short loc_1800174FB
0x1800174f4  cmp     eax, 0EAh
0x1800174f9  jnz     short loc_180017568
0x1800174fb  mov     edx, [rsp+270h+cbData]
0x1800174ff  mov     ecx, 40h ; '@'; uFlags
0x180017504  add     rdx, 8; uBytes
0x180017508  call    cs:__imp_LocalAlloc
0x18001750e  mov     [rsi+28h], rax
0x180017512  test    rax, rax
0x180017515  jnz     short loc_18001752D
0x180017517  call    cs:__imp_GetLastError
0x18001751d  mov     ebx, eax
0x18001751f  jmp     short loc_180017568
0x180017521  mov     r14, rdi
0x180017524  jmp     short loc_1800174BB
0x180017526  mov     rdi, [rsp+270h+hKey]
0x18001752b  jmp     short loc_180017568
0x18001752d  lea     rcx, [rsp+270h+cbData]
0x180017532  add     rax, 4
0x180017536  mov     qword ptr [rsp+270h+cchWideChar], rcx; lpcbData
0x18001753b  lea     r9, [rsp+270h+Type]; lpType
0x180017540  mov     rcx, r14; hKey
0x180017543  mov     [rsp+270h+lpWideCharStr], rax; lpData
0x180017548  xor     r8d, r8d; lpReserved
0x18001754b  lea     rdx, aCalledidinform; "CalledIDInformation"
0x180017552  call    cs:__imp_RegQueryValueExW
0x180017558  mov     ebx, eax
0x18001755a  test    eax, eax
0x18001755c  jnz     short loc_180017568
0x18001755e  mov     rdx, [rsi+28h]
0x180017562  mov     eax, [rsp+270h+cbData]
0x180017566  mov     [rdx], eax
0x180017568  test    rdi, rdi
0x18001756b  jz      short loc_180017576
0x18001756d  mov     rcx, rdi; hKey
0x180017570  call    cs:__imp_RegCloseKey
0x180017576  mov     rcx, [rsp+270h+phkResult]; hKey
0x18001757b  test    rcx, rcx
0x18001757e  jz      short loc_180017586
0x180017580  call    cs:__imp_RegCloseKey
0x180017586  test    ebx, ebx
0x180017588  jz      short loc_1800175A9
0x18001758a  mov     rcx, [rsi+28h]; hMem
0x18001758e  test    rcx, rcx
0x180017591  jz      short loc_1800175A1
0x180017593  call    cs:__imp_LocalFree
0x180017599  mov     qword ptr [rsi+28h], 0
0x1800175a1  xor     eax, eax
0x1800175a3  cmp     ebx, 2
0x1800175a6  cmovz   ebx, eax
0x1800175a9  mov     eax, ebx
0x1800175ab  mov     rcx, [rbp+170h+var_20]
0x1800175b2  xor     rcx, rsp; StackCookie
0x1800175b5  call    __security_check_cookie
0x1800175ba  lea     r11, [rsp+270h+var_10]
0x1800175c2  mov     rbx, [r11+30h]
0x1800175c6  mov     rsi, [r11+38h]
0x1800175ca  mov     rsp, r11
0x1800175cd  pop     r14
0x1800175cf  pop     rdi
0x1800175d0  pop     rbp
0x1800175d1  retn
```
