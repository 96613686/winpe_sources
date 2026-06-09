# InitUnistor(void)

- ea: `0x18005212c`
- end: `0x180052334`
- name: `?InitUnistor@@YAXXZ`
- size: `520`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003348`
- `0x1800042ec`

## callees

- `0x18005212c`
- `0x18005233c`
- `0x18007ac50`
- `0x18007aff0`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005231c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005231c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005229c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005229c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800521e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005222e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800521e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005222e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005219e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005219e`

## string_xrefs

- `0x180052227`: `DataFilePath`

## pseudocode

```c
void InitUnistor(void)
{
  __int64 v0; // rdx
  int (*v1)(unsigned __int64, void **); // r8
  int (*v2)(void *); // r9
  int v3; // eax
  DWORD v4; // edx
  __int64 v5; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src[264]; // [rsp+260h] [rbp+160h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  if ( gfUnistorInitialized )
    return;
  gfUnistorInitialized = 1;
  Dst[0] = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\LanguagePack\\DataStore_V1.0",
          0,
          0x101u,
          &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Disable", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v3 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v3 = *(_DWORD *)Data;
    }
    if ( v3 )
      goto LABEL_13;
    cbData = 522;
    if ( RegQueryValueExW(hKey, L"DataFilePath", 0, &Type, (LPBYTE)Src, &cbData) )
      goto LABEL_13;
    v4 = Type;
    if ( Type - 1 <= 1 )
    {
      v5 = cbData >> 1;
      if ( (unsigned int)v5 > 0x104 )
        v5 = 260;
      cbData = v5;
      if ( (unsigned __int64)(2 * v5) >= 0x20A )
        _report_rangecheckfailure();
      Src[v5] = 0;
      if ( v4 != 2 )
      {
        memcpy_0(Dst, Src, 2LL * (unsigned int)(v5 + 1));
LABEL_13:
        RegCloseKey(hKey);
        goto LABEL_14;
      }
      if ( ExpandEnvironmentStringsW(Src, Dst, 0x105u) - 1 <= 0x104 )
        goto LABEL_13;
    }
    Dst[0] = 0;
    goto LABEL_13;
  }
LABEL_14:
  ghUniStore = 0;
  if ( !*(_DWORD *)Data && (!Dst[0] || (int)UniStorInit(Dst, v0, v1, v2) < 0) )
    UniStorInit(0, v0, v1, v2);
}

```

## disassembly

```asm
0x18005212c  mov     [rsp-8+arg_0], rbx
0x180052131  mov     [rsp-8+arg_8], rdi
0x180052136  push    rbp
0x180052137  lea     rbp, [rsp-380h]
0x18005213f  sub     rsp, 480h
0x180052146  mov     rax, cs:__security_cookie
0x18005214d  xor     rax, rsp
0x180052150  mov     [rbp+380h+var_10], rax
0x180052157  xor     ebx, ebx
0x180052159  cmp     cs:?gfUnistorInitialized@@3HA, ebx; int gfUnistorInitialized
0x18005215f  mov     [rsp+480h+hKey], rbx
0x180052164  mov     dword ptr [rsp+480h+Data], ebx
0x180052168  jnz     loc_1800522CB
0x18005216e  lea     rax, [rsp+480h+hKey]
0x180052173  mov     cs:?gfUnistorInitialized@@3HA, 1; int gfUnistorInitialized
0x18005217d  mov     r9d, 101h; samDesired
0x180052183  mov     [rsp+480h+phkResult], rax; phkResult
0x180052188  xor     r8d, r8d; ulOptions
0x18005218b  mov     [rsp+480h+Dst], bx
0x180052190  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180052197  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005219e  call    cs:__imp_RegOpenKeyExW
0x1800521a4  test    eax, eax
0x1800521a6  jnz     loc_1800522A2
0x1800521ac  mov     rcx, [rsp+480h+hKey]; hKey
0x1800521b1  lea     rax, [rsp+480h+cbData]
0x1800521b6  mov     [rsp+480h+lpcbData], rax; lpcbData
0x1800521bb  lea     r9, [rsp+480h+Type]; lpType
0x1800521c0  lea     rax, [rsp+480h+Data]
0x1800521c5  mov     [rsp+480h+Type], ebx
0x1800521c9  xor     r8d, r8d; lpReserved
0x1800521cc  mov     [rsp+480h+phkResult], rax; lpData
0x1800521d1  lea     rdx, aDisable; "Disable"
0x1800521d8  mov     [rsp+480h+cbData], 4
0x1800521e0  call    cs:__imp_RegQueryValueExW
0x1800521e6  test    eax, eax
0x1800521e8  jz      loc_1800522F6
0x1800521ee  mov     eax, ebx
0x1800521f0  mov     dword ptr [rsp+480h+Data], ebx
0x1800521f4  test    eax, eax
0x1800521f6  jnz     loc_180052297
0x1800521fc  mov     rcx, [rsp+480h+hKey]; hKey
0x180052201  lea     rax, [rsp+480h+cbData]
0x180052206  mov     [rsp+480h+lpcbData], rax; unsigned int *
0x18005220b  lea     r9, [rsp+480h+Type]; lpType
0x180052210  lea     rax, [rbp+380h+Src]
0x180052217  mov     [rsp+480h+cbData], 20Ah
0x18005221f  xor     r8d, r8d; lpReserved
0x180052222  mov     [rsp+480h+phkResult], rax; void **
0x180052227  lea     rdx, aDatafilepath; "DataFilePath"
0x18005222e  call    cs:__imp_RegQueryValueExW
0x180052234  test    eax, eax
0x180052236  jnz     short loc_180052297
0x180052238  mov     edx, [rsp+480h+Type]
0x18005223c  lea     eax, [rdx-1]
0x18005223f  cmp     eax, 1
0x180052242  ja      loc_1800522EF
0x180052248  mov     ecx, [rsp+480h+cbData]
0x18005224c  mov     edi, 104h
0x180052251  shr     ecx, 1
0x180052253  cmp     ecx, edi
0x180052255  cmova   ecx, edi
0x180052258  mov     [rsp+480h+cbData], ecx
0x18005225c  lea     r8, [rcx+rcx]
0x180052260  cmp     r8, 20Ah
0x180052267  jnb     loc_18005232E
0x18005226d  mov     [rbp+r8+380h+Src], bx
0x180052276  cmp     edx, 2
0x180052279  jz      loc_18005230A
0x18005227f  lea     r8d, [rcx+1]
0x180052283  add     r8, r8; Size
0x180052286  lea     rdx, [rbp+380h+Src]; Src
0x18005228d  lea     rcx, [rsp+480h+Dst]; void *
0x180052292  call    memcpy_0
0x180052297  mov     rcx, [rsp+480h+hKey]; hKey
0x18005229c  call    cs:__imp_RegCloseKey
0x1800522a2  mov     cs:?ghUniStore@@3PEAXEA, rbx; void * ghUniStore
0x1800522a9  cmp     dword ptr [rsp+480h+Data], ebx
0x1800522ad  jnz     short loc_1800522CB
0x1800522af  cmp     [rsp+480h+Dst], bx
0x1800522b4  jz      short loc_1800522C4
0x1800522b6  lea     rcx, [rsp+480h+Dst]; lpFileName
0x1800522bb  call    ?UniStorInit@@YAJPEB_WHP6AJ_KPEAPEAX@ZP6AJPEAX@Z2PEAK@Z; UniStorInit(wchar_t const *,int,long (*)(unsigned __int64,void * *),long (*)(void *),void * *,ulong *)
0x1800522c0  test    eax, eax
0x1800522c2  jns     short loc_1800522CB
0x1800522c4  xor     ecx, ecx; lpFileName
0x1800522c6  call    ?UniStorInit@@YAJPEB_WHP6AJ_KPEAPEAX@ZP6AJPEAX@Z2PEAK@Z; UniStorInit(wchar_t const *,int,long (*)(unsigned __int64,void * *),long (*)(void *),void * *,ulong *)
0x1800522cb  mov     rcx, [rbp+380h+var_10]
0x1800522d2  xor     rcx, rsp; StackCookie
0x1800522d5  call    __security_check_cookie
0x1800522da  lea     r11, [rsp+480h+var_s0]
0x1800522e2  mov     rbx, [r11+10h]
0x1800522e6  mov     rdi, [r11+18h]
0x1800522ea  mov     rsp, r11
0x1800522ed  pop     rbp
0x1800522ee  retn
0x1800522ef  mov     [rsp+480h+Dst], bx
0x1800522f4  jmp     short loc_180052297
0x1800522f6  cmp     [rsp+480h+Type], 4
0x1800522fb  jnz     loc_1800521EE
0x180052301  mov     eax, dword ptr [rsp+480h+Data]
0x180052305  jmp     loc_1800521F4
0x18005230a  mov     r8d, 105h; nSize
0x180052310  lea     rdx, [rsp+480h+Dst]; lpDst
0x180052315  lea     rcx, [rbp+380h+Src]; lpSrc
0x18005231c  call    cs:__imp_ExpandEnvironmentStringsW
0x180052322  dec     eax
0x180052324  cmp     eax, edi
0x180052326  jbe     loc_180052297
0x18005232c  jmp     short loc_1800522EF
0x18005232e  call    __report_rangecheckfailure
```
