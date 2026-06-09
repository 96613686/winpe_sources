# InitUnistor(void)

- ea: `0x180057cc8`
- end: `0x180057eef`
- name: `?InitUnistor@@YAXXZ`
- size: `551`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ad28`
- `0x18001c3c4`

## callees

- `0x180057cc8`
- `0x180057ef8`
- `0x18007f800`
- `0x18007fba0`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180057ed1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180057ed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057e4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057e4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057d82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057dd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057d82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180057dd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057d3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057d3a`

## string_xrefs

- `0x180057dcf`: `DataFilePath`

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
0x180057cc8  mov     [rsp-8+arg_0], rbx
0x180057ccd  mov     [rsp-8+arg_8], rdi
0x180057cd2  push    rbp
0x180057cd3  lea     rbp, [rsp-380h]
0x180057cdb  sub     rsp, 480h
0x180057ce2  mov     rax, cs:__security_cookie
0x180057ce9  xor     rax, rsp
0x180057cec  mov     [rbp+380h+var_10], rax
0x180057cf3  xor     ebx, ebx
0x180057cf5  cmp     cs:?gfUnistorInitialized@@3HA, ebx; int gfUnistorInitialized
0x180057cfb  mov     [rsp+480h+hKey], rbx
0x180057d00  mov     dword ptr [rsp+480h+Data], ebx
0x180057d04  jnz     loc_180057E7F
0x180057d0a  lea     rax, [rsp+480h+hKey]
0x180057d0f  mov     cs:?gfUnistorInitialized@@3HA, 1; int gfUnistorInitialized
0x180057d19  mov     r9d, 101h; samDesired
0x180057d1f  mov     [rsp+480h+phkResult], rax; phkResult
0x180057d24  xor     r8d, r8d; ulOptions
0x180057d27  mov     [rsp+480h+Dst], bx
0x180057d2c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180057d33  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180057d3a  call    cs:__imp_RegOpenKeyExW
0x180057d41  nop     dword ptr [rax+rax+00h]
0x180057d46  test    eax, eax
0x180057d48  jnz     loc_180057E56
0x180057d4e  mov     rcx, [rsp+480h+hKey]; hKey
0x180057d53  lea     rax, [rsp+480h+cbData]
0x180057d58  mov     [rsp+480h+lpcbData], rax; lpcbData
0x180057d5d  lea     r9, [rsp+480h+Type]; lpType
0x180057d62  lea     rax, [rsp+480h+Data]
0x180057d67  mov     [rsp+480h+Type], ebx
0x180057d6b  xor     r8d, r8d; lpReserved
0x180057d6e  mov     [rsp+480h+phkResult], rax; lpData
0x180057d73  lea     rdx, aDisable; "Disable"
0x180057d7a  mov     [rsp+480h+cbData], 4
0x180057d82  call    cs:__imp_RegQueryValueExW
0x180057d89  nop     dword ptr [rax+rax+00h]
0x180057d8e  test    eax, eax
0x180057d90  jz      loc_180057EAB
0x180057d96  mov     eax, ebx
0x180057d98  mov     dword ptr [rsp+480h+Data], ebx
0x180057d9c  test    eax, eax
0x180057d9e  jnz     loc_180057E45
0x180057da4  mov     rcx, [rsp+480h+hKey]; hKey
0x180057da9  lea     rax, [rsp+480h+cbData]
0x180057dae  mov     [rsp+480h+lpcbData], rax; unsigned int *
0x180057db3  lea     r9, [rsp+480h+Type]; lpType
0x180057db8  lea     rax, [rbp+380h+Src]
0x180057dbf  mov     [rsp+480h+cbData], 20Ah
0x180057dc7  xor     r8d, r8d; lpReserved
0x180057dca  mov     [rsp+480h+phkResult], rax; void **
0x180057dcf  lea     rdx, aDatafilepath; "DataFilePath"
0x180057dd6  call    cs:__imp_RegQueryValueExW
0x180057ddd  nop     dword ptr [rax+rax+00h]
0x180057de2  test    eax, eax
0x180057de4  jnz     short loc_180057E45
0x180057de6  mov     edx, [rsp+480h+Type]
0x180057dea  lea     eax, [rdx-1]
0x180057ded  cmp     eax, 1
0x180057df0  ja      loc_180057EA4
0x180057df6  mov     ecx, [rsp+480h+cbData]
0x180057dfa  mov     edi, 104h
0x180057dff  shr     ecx, 1
0x180057e01  cmp     ecx, edi
0x180057e03  cmova   ecx, edi
0x180057e06  mov     [rsp+480h+cbData], ecx
0x180057e0a  lea     r8, [rcx+rcx]
0x180057e0e  cmp     r8, 20Ah
0x180057e15  jnb     loc_180057EE9
0x180057e1b  mov     [rbp+r8+380h+Src], bx
0x180057e24  cmp     edx, 2
0x180057e27  jz      loc_180057EBF
0x180057e2d  lea     r8d, [rcx+1]
0x180057e31  add     r8, r8; Size
0x180057e34  lea     rdx, [rbp+380h+Src]; Src
0x180057e3b  lea     rcx, [rsp+480h+Dst]; void *
0x180057e40  call    memcpy_0
0x180057e45  mov     rcx, [rsp+480h+hKey]; hKey
0x180057e4a  call    cs:__imp_RegCloseKey
0x180057e51  nop     dword ptr [rax+rax+00h]
0x180057e56  mov     cs:?ghUniStore@@3PEAXEA, rbx; void * ghUniStore
0x180057e5d  cmp     dword ptr [rsp+480h+Data], ebx
0x180057e61  jnz     short loc_180057E7F
0x180057e63  cmp     [rsp+480h+Dst], bx
0x180057e68  jz      short loc_180057E78
0x180057e6a  lea     rcx, [rsp+480h+Dst]; lpFileName
0x180057e6f  call    ?UniStorInit@@YAJPEB_WHP6AJ_KPEAPEAX@ZP6AJPEAX@Z2PEAK@Z; UniStorInit(wchar_t const *,int,long (*)(unsigned __int64,void * *),long (*)(void *),void * *,ulong *)
0x180057e74  test    eax, eax
0x180057e76  jns     short loc_180057E7F
0x180057e78  xor     ecx, ecx; lpFileName
0x180057e7a  call    ?UniStorInit@@YAJPEB_WHP6AJ_KPEAPEAX@ZP6AJPEAX@Z2PEAK@Z; UniStorInit(wchar_t const *,int,long (*)(unsigned __int64,void * *),long (*)(void *),void * *,ulong *)
0x180057e7f  mov     rcx, [rbp+380h+var_10]
0x180057e86  xor     rcx, rsp; StackCookie
0x180057e89  call    __security_check_cookie
0x180057e8e  lea     r11, [rsp+480h+var_s0]
0x180057e96  mov     rbx, [r11+10h]
0x180057e9a  mov     rdi, [r11+18h]
0x180057e9e  mov     rsp, r11
0x180057ea1  pop     rbp
0x180057ea2  retn
0x180057ea4  mov     [rsp+480h+Dst], bx
0x180057ea9  jmp     short loc_180057E45
0x180057eab  cmp     [rsp+480h+Type], 4
0x180057eb0  jnz     loc_180057D96
0x180057eb6  mov     eax, dword ptr [rsp+480h+Data]
0x180057eba  jmp     loc_180057D9C
0x180057ebf  mov     r8d, 105h; nSize
0x180057ec5  lea     rdx, [rsp+480h+Dst]; lpDst
0x180057eca  lea     rcx, [rbp+380h+Src]; lpSrc
0x180057ed1  call    cs:__imp_ExpandEnvironmentStringsW
0x180057ed8  nop     dword ptr [rax+rax+00h]
0x180057edd  dec     eax
0x180057edf  cmp     eax, edi
0x180057ee1  jbe     loc_180057E45
0x180057ee7  jmp     short loc_180057EA4
0x180057ee9  call    __report_rangecheckfailure
```
