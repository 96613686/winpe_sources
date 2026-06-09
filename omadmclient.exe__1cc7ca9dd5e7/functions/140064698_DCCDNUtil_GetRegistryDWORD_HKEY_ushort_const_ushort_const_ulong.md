# DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x140064698`
- end: `0x1400647bf`
- name: `?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `295`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140064af8`

## callees

- `0x14000b0f4`
- `0x140064698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140064719`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140064719`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140064762`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140064762`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400647a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400647a3`

## pseudocode

```c
__int64 __fastcall DCCDNUtil_GetRegistryDWORD(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned int v6; // ebx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+64h] [rbp+24h]
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+74h] [rbp+34h]

  v18 = HIDWORD(a3);
  v16 = HIDWORD(a1);
  Data = 0;
  Type = 4;
  hKey = 0;
  cbData = 4;
  if ( !a4 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return v6;
  }
  v7 = HKEY_LOCAL_MACHINE;
  if ( a2 )
  {
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, &hKey);
    v6 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
LABEL_16:
      if ( hKey )
        RegCloseKey(hKey);
      return v6;
    }
    v7 = hKey;
  }
  else
  {
    hKey = HKEY_LOCAL_MACHINE;
  }
  v9 = RegQueryValueExW(v7, L"RefreshInterval", 0, &Type, (LPBYTE)&Data, &cbData);
  v6 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
  }
  else if ( Type == 4 )
  {
    v6 = 0;
    *a4 = Data;
  }
  else
  {
    v6 = -2147418113;
  }
  if ( a2 )
    goto LABEL_16;
  return v6;
}

```

## disassembly

```asm
0x140064698  mov     [rsp-18h+arg_8], rbx
0x14006469d  mov     qword ptr [rsp-18h+Type], r8
0x1400646a2  mov     qword ptr [rsp-18h+Data], rcx
0x1400646a7  push    rbp
0x1400646a8  push    rsi
0x1400646a9  push    rdi
0x1400646aa  mov     rbp, rsp
0x1400646ad  sub     rsp, 40h
0x1400646b1  mov     [rbp+Data], 0
0x1400646b8  mov     rsi, r9
0x1400646bb  mov     [rbp+Type], 4
0x1400646c2  mov     rdi, rdx
0x1400646c5  mov     [rbp+hKey], 0
0x1400646cd  mov     [rbp+cbData], 4
0x1400646d4  test    r9, r9
0x1400646d7  jnz     short loc_1400646FB
0x1400646d9  mov     rcx, [rbp+18h]; this
0x1400646dd  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1400646e4  mov     ebx, 80070057h
0x1400646e9  mov     edx, 0AEh; void *
0x1400646ee  mov     r9d, ebx; char *
0x1400646f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400646f6  jmp     loc_1400647AF
0x1400646fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140064702  test    rdi, rdi
0x140064705  jz      short loc_14006473E
0x140064707  lea     rax, [rbp+hKey]
0x14006470b  mov     r9d, 20119h; samDesired
0x140064711  xor     r8d, r8d; ulOptions
0x140064714  mov     [rsp+40h+phkResult], rax; phkResult
0x140064719  call    cs:__imp_RegOpenKeyExW
0x140064720  nop     dword ptr [rax+rax+00h]
0x140064725  mov     ebx, eax
0x140064727  test    eax, eax
0x140064729  jz      short loc_140064738
0x14006472b  jle     short loc_14006479A
0x14006472d  movzx   ebx, ax
0x140064730  or      ebx, 80070000h
0x140064736  jmp     short loc_14006479A
0x140064738  mov     rcx, [rbp+hKey]
0x14006473c  jmp     short loc_140064742
0x14006473e  mov     [rbp+hKey], rcx
0x140064742  lea     rax, [rbp+cbData]
0x140064746  xor     r8d, r8d; lpReserved
0x140064749  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14006474e  lea     r9, [rbp+Type]; lpType
0x140064752  lea     rax, [rbp+Data]
0x140064756  lea     rdx, aRefreshinterva; "RefreshInterval"
0x14006475d  mov     [rsp+40h+phkResult], rax; lpData
0x140064762  call    cs:__imp_RegQueryValueExW
0x140064769  nop     dword ptr [rax+rax+00h]
0x14006476e  mov     ebx, eax
0x140064770  test    eax, eax
0x140064772  jz      short loc_140064781
0x140064774  jle     short loc_140064795
0x140064776  movzx   ebx, ax
0x140064779  or      ebx, 80070000h
0x14006477f  jmp     short loc_140064795
0x140064781  cmp     [rbp+Type], 4
0x140064785  jz      short loc_14006478E
0x140064787  mov     ebx, 8000FFFFh
0x14006478c  jmp     short loc_140064795
0x14006478e  mov     eax, [rbp+Data]
0x140064791  xor     ebx, ebx
0x140064793  mov     [rsi], eax
0x140064795  test    rdi, rdi
0x140064798  jz      short loc_1400647AF
0x14006479a  mov     rcx, [rbp+hKey]; hKey
0x14006479e  test    rcx, rcx
0x1400647a1  jz      short loc_1400647AF
0x1400647a3  call    cs:__imp_RegCloseKey
0x1400647aa  nop     dword ptr [rax+rax+00h]
0x1400647af  mov     eax, ebx
0x1400647b1  mov     rbx, [rsp+40h+arg_8]
0x1400647b6  add     rsp, 40h
0x1400647ba  pop     rdi
0x1400647bb  pop     rsi
0x1400647bc  pop     rbp
0x1400647bd  retn
```
