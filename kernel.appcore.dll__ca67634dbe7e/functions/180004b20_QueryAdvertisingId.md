# QueryAdvertisingId

- ea: `0x180004b20`
- end: `0x180004d63`
- name: `QueryAdvertisingId`
- size: `579`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004b20`
- `0x180005f54`
- `0x180006324`
- `0x1800064d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004cd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004b71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004caf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004b71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004caf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004bb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004bb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d08`

## pseudocode

```c
__int64 __fastcall QueryAdvertisingId(unsigned __int16 *a1, __int64 a2, int a3)
{
  LSTATUS v5; // eax
  signed int v6; // esi
  unsigned int v7; // eax
  unsigned int i; // eax
  __int16 v9; // dx
  int UserAdvertisingRegPath; // eax
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  int phkResult; // [rsp+20h] [rbp-38h]
  int phkResulta; // [rsp+20h] [rbp-38h]
  unsigned int phkResultb; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD cbData; // [rsp+60h] [rbp+8h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( !a1 )
  {
    v5 = RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\AdvertisingInfo",
           0,
           0x20119u,
           &hKey);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_5;
LABEL_21:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v6,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  lpSubKey = 0;
  UserAdvertisingRegPath = AdvertisingIdHelpers::GetUserAdvertisingRegPath(a1);
  v6 = UserAdvertisingRegPath;
  if ( UserAdvertisingRegPath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)UserAdvertisingRegPath,
      phkResult);
    goto LABEL_21;
  }
  v12 = RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x20119u, &hKey);
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_21;
LABEL_5:
  cbData = 2 * a3;
  v7 = RegQueryValueExW(hKey, L"Id", 0, &Type, (LPBYTE)a2, &cbData);
  if ( v7 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2DE,
            (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
            (const char *)v7,
            phkResultb);
    if ( hKey )
      RegCloseKey(hKey);
    return v13;
  }
  else if ( Type == 1 && (cbData & 0xFFFFFFFE) == 0x42 && !*(_WORD *)(a2 + 64) )
  {
    for ( i = 0; i < 0x20; ++i )
    {
      v9 = *(_WORD *)(a2 + 2LL * i);
      if ( (unsigned __int16)(v9 - 48) > 9u && (unsigned __int16)(v9 - 97) > 5u && (unsigned __int16)(v9 - 65) > 5u )
        goto LABEL_15;
    }
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
LABEL_15:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180004b20  mov     [rsp+arg_8], rbx
0x180004b25  mov     [rsp+arg_10], rbp
0x180004b2a  push    rsi
0x180004b2b  push    rdi
0x180004b2c  push    r14
0x180004b2e  sub     rsp, 40h
0x180004b32  xor     ebp, ebp
0x180004b34  mov     r14d, r8d
0x180004b37  mov     [rsp+58h+hKey], rbp
0x180004b3c  mov     rdi, rdx
0x180004b3f  mov     [rsp+58h+cbData], ebp
0x180004b43  mov     [rsp+58h+Type], ebp
0x180004b47  test    rcx, rcx
0x180004b4a  jnz     loc_180004C74
0x180004b50  lea     rax, [rsp+58h+hKey]
0x180004b55  mov     r9d, 20119h; samDesired
0x180004b5b  xor     r8d, r8d; ulOptions
0x180004b5e  mov     [rsp+58h+phkResult], rax; int
0x180004b63  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004b6a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180004b71  call    cs:__imp_RegOpenKeyExW
0x180004b77  mov     esi, eax
0x180004b79  test    eax, eax
0x180004b7b  jg      loc_180004D15
0x180004b81  test    esi, esi
0x180004b83  js      loc_180004C47
0x180004b89  mov     rcx, [rsp+58h+hKey]; hKey
0x180004b8e  lea     eax, [r14+r14]
0x180004b92  mov     [rsp+58h+cbData], eax
0x180004b96  lea     r9, [rsp+58h+Type]; lpType
0x180004b9b  lea     rax, [rsp+58h+cbData]
0x180004ba0  xor     r8d, r8d; lpReserved
0x180004ba3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180004ba8  lea     rdx, ValueName; "Id"
0x180004baf  mov     [rsp+58h+phkResult], rdi; unsigned int
0x180004bb4  call    cs:__imp_RegQueryValueExW
0x180004bba  test    eax, eax
0x180004bbc  jnz     loc_180004CE3
0x180004bc2  cmp     [rsp+58h+Type], 1
0x180004bc7  jnz     short loc_180004C0B
0x180004bc9  mov     eax, [rsp+58h+cbData]
0x180004bcd  and     eax, 0FFFFFFFEh
0x180004bd0  cmp     eax, 42h ; 'B'
0x180004bd3  jnz     short loc_180004C0B
0x180004bd5  cmp     [rdi+40h], bp
0x180004bd9  jnz     short loc_180004C0B
0x180004bdb  mov     eax, ebp
0x180004bdd  nop     dword ptr [rax]
0x180004be0  cmp     eax, 20h ; ' '
0x180004be3  jnb     short loc_180004C22
0x180004be5  mov     ecx, eax
0x180004be7  movzx   edx, word ptr [rdi+rcx*2]
0x180004beb  lea     ecx, [rdx-30h]
0x180004bee  cmp     cx, 9
0x180004bf2  ja      short loc_180004BF8
0x180004bf4  inc     eax
0x180004bf6  jmp     short loc_180004BE0
0x180004bf8  lea     ecx, [rdx-61h]
0x180004bfb  cmp     cx, 5
0x180004bff  jbe     short loc_180004BF4
0x180004c01  sub     dx, 41h ; 'A'
0x180004c05  cmp     dx, 5
0x180004c09  jbe     short loc_180004BF4
0x180004c0b  mov     rcx, [rsp+58h+hKey]; hKey
0x180004c10  test    rcx, rcx
0x180004c13  jz      short loc_180004C1B
0x180004c15  call    cs:__imp_RegCloseKey
0x180004c1b  mov     eax, 80070002h
0x180004c20  jmp     short loc_180004C34
0x180004c22  mov     rcx, [rsp+58h+hKey]; hKey
0x180004c27  test    rcx, rcx
0x180004c2a  jz      short loc_180004C32
0x180004c2c  call    cs:__imp_RegCloseKey
0x180004c32  mov     eax, ebp
0x180004c34  mov     rbx, [rsp+58h+arg_8]
0x180004c39  mov     rbp, [rsp+58h+arg_10]
0x180004c3e  add     rsp, 40h
0x180004c42  pop     r14
0x180004c44  pop     rdi
0x180004c45  pop     rsi
0x180004c46  retn
0x180004c47  mov     rcx, [rsp+58h]; this
0x180004c4c  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180004c53  mov     r9d, esi; char *
0x180004c56  mov     edx, 2D2h; void *
0x180004c5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004c60  mov     rcx, [rsp+58h+hKey]; hKey
0x180004c65  test    rcx, rcx
0x180004c68  jz      short loc_180004C70
0x180004c6a  call    cs:__imp_RegCloseKey
0x180004c70  mov     eax, esi
0x180004c72  jmp     short loc_180004C34
0x180004c74  lea     rdx, [rsp+58h+lpSubKey]
0x180004c79  mov     [rsp+58h+lpSubKey], rbp
0x180004c7e  call    AdvertisingIdHelpers__GetUserAdvertisingRegPath
0x180004c83  mov     esi, eax
0x180004c85  test    eax, eax
0x180004c87  js      loc_180004D23
0x180004c8d  mov     rbx, [rsp+58h+lpSubKey]
0x180004c92  lea     rax, [rsp+58h+hKey]
0x180004c97  mov     rdx, rbx; lpSubKey
0x180004c9a  mov     [rsp+58h+phkResult], rax; phkResult
0x180004c9f  mov     r9d, 20119h; samDesired
0x180004ca5  xor     r8d, r8d; ulOptions
0x180004ca8  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180004caf  call    cs:__imp_RegOpenKeyExW
0x180004cb5  mov     esi, eax
0x180004cb7  test    eax, eax
0x180004cb9  jle     short loc_180004CC4
0x180004cbb  movzx   esi, ax
0x180004cbe  or      esi, 80070000h
0x180004cc4  test    esi, esi
0x180004cc6  jns     loc_180004D4C
0x180004ccc  test    rbx, rbx
0x180004ccf  jz      loc_180004C47
0x180004cd5  mov     rcx, rbx; hMem
0x180004cd8  call    cs:__imp_LocalFree
0x180004cde  jmp     loc_180004C47
0x180004ce3  mov     rcx, [rsp+58h]; this
0x180004ce8  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180004cef  mov     r9d, eax; char *
0x180004cf2  mov     edx, 2DEh; void *
0x180004cf7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180004cfc  mov     rcx, [rsp+58h+hKey]; hKey
0x180004d01  mov     ebx, eax
0x180004d03  test    rcx, rcx
0x180004d06  jz      short loc_180004D0E
0x180004d08  call    cs:__imp_RegCloseKey
0x180004d0e  mov     eax, ebx
0x180004d10  jmp     loc_180004C34
0x180004d15  movzx   esi, ax
0x180004d18  or      esi, 80070000h
0x180004d1e  jmp     loc_180004B81
0x180004d23  mov     rcx, [rsp+58h]; this
0x180004d28  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180004d2f  mov     r9d, eax; char *
0x180004d32  mov     edx, 328h; void *
0x180004d37  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004d3c  mov     rcx, [rsp+58h+lpSubKey]
0x180004d41  test    rcx, rcx
0x180004d44  jz      loc_180004C47
0x180004d4a  jmp     short loc_180004CD8
0x180004d4c  test    rbx, rbx
0x180004d4f  jz      loc_180004B89
0x180004d55  mov     rcx, rbx; hMem
0x180004d58  call    cs:__imp_LocalFree
0x180004d5e  jmp     loc_180004B89
```
