# CSettingsManager::GetSettingFromRegistry(_RASettingDWORD,ulong *)

- ea: `0x140037168`
- end: `0x1400372b8`
- name: `?GetSettingFromRegistry@CSettingsManager@@QEAAJW4_RASettingDWORD@@PEAK@Z`
- size: `336`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a858`
- `0x14001b5d4`
- `0x14001fb14`
- `0x14001ffb8`
- `0x140020c24`
- `0x14002ad4c`
- `0x14002b7f0`
- `0x14002bd4c`

## callees

- `0x140037168`
- `0x14003747c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140037274`
- `ADVAPI32!RegCloseKey` at `0x140037274`
- `ADVAPI32!RegOpenKeyExW` at `0x140037202`
- `ADVAPI32!RegOpenKeyExW` at `0x140037202`
- `ADVAPI32!RegQueryValueExW` at `0x140037240`
- `ADVAPI32!RegQueryValueExW` at `0x140037240`
- `KERNEL32!ReleaseMutex` at `0x140037290`
- `KERNEL32!ReleaseMutex` at `0x140037290`
- `KERNEL32!WaitForSingleObject` at `0x1400371c1`
- `KERNEL32!WaitForSingleObject` at `0x1400371c1`

## pseudocode

```c
__int64 __fastcall CSettingsManager::GetSettingFromRegistry(HANDLE *a1, int a2, _DWORD *a3)
{
  __int64 v4; // r15
  HANDLE v5; // rcx
  unsigned int v7; // ebx
  int v8; // esi
  const WCHAR *v9; // rdx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+88h] [rbp+48h] BYREF

  v4 = a2;
  v5 = *a1;
  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 4;
  if ( !v5 )
    return (unsigned int)-2147418113;
  if ( WaitForSingleObject(v5, 0x64u) == 258 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Remote Assistance", 0, 1u, &hKey) )
    {
      v9 = (const WCHAR *)(&RA_SETTINGS_DWORD)[v4];
      cbData = 4;
      v7 = 0;
      if ( RegQueryValueExW(hKey, v9, 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        CSettingsManager::LoadDefaultSetting(a1, (unsigned int)v4);
        *a3 = *((_DWORD *)a1 + v4 + 2);
      }
      else
      {
        *a3 = Data;
      }
      goto LABEL_10;
    }
  }
  v7 = -2147467259;
LABEL_10:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v8 == 1 )
    ReleaseMutex(*a1);
  return v7;
}

```

## disassembly

```asm
0x140037168  mov     [rsp-28h+arg_8], rbx
0x14003716d  mov     [rsp-28h+arg_10], rsi
0x140037172  push    rbp
0x140037173  push    rdi
0x140037174  push    r12
0x140037176  push    r14
0x140037178  push    r15
0x14003717a  mov     rbp, rsp
0x14003717d  sub     rsp, 40h
0x140037181  mov     rdi, rcx
0x140037184  movsxd  r15, edx
0x140037187  mov     rcx, [rcx]; hHandle
0x14003718a  mov     r12d, 4
0x140037190  mov     [rbp+hKey], 0
0x140037198  mov     r14, r8
0x14003719b  mov     [rbp+cbData], 0
0x1400371a2  mov     [rbp+Data], 0
0x1400371a9  mov     [rbp+Type], r12d
0x1400371ad  test    rcx, rcx
0x1400371b0  jnz     short loc_1400371BC
0x1400371b2  mov     ebx, 8000FFFFh
0x1400371b7  jmp     loc_14003729C
0x1400371bc  mov     edx, 64h ; 'd'; dwMilliseconds
0x1400371c1  call    cs:__imp_WaitForSingleObject
0x1400371c8  nop     dword ptr [rax+rax+00h]
0x1400371cd  cmp     eax, 102h
0x1400371d2  jnz     short loc_1400371E0
0x1400371d4  xor     esi, esi
0x1400371d6  mov     ebx, 80004005h
0x1400371db  jmp     loc_14003726B
0x1400371e0  lea     rax, [rbp+hKey]
0x1400371e4  mov     esi, 1
0x1400371e9  mov     r9d, esi; samDesired
0x1400371ec  mov     [rsp+40h+phkResult], rax; phkResult
0x1400371f1  xor     r8d, r8d; ulOptions
0x1400371f4  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Remote Assistance"
0x1400371fb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140037202  call    cs:__imp_RegOpenKeyExW
0x140037209  nop     dword ptr [rax+rax+00h]
0x14003720e  test    eax, eax
0x140037210  jnz     short loc_1400371D6
0x140037212  mov     rcx, [rbp+hKey]; hKey
0x140037216  lea     rax, [rbp+cbData]
0x14003721a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14003721f  lea     rdx, ?RA_SETTINGS_DWORD@@3PAPEBGA; ushort const * near * RA_SETTINGS_DWORD
0x140037226  mov     rdx, [rdx+r15*8]; lpValueName
0x14003722a  lea     rax, [rbp+Data]
0x14003722e  lea     r9, [rbp+Type]; lpType
0x140037232  mov     [rsp+40h+phkResult], rax; lpData
0x140037237  xor     r8d, r8d; lpReserved
0x14003723a  mov     [rbp+cbData], r12d
0x14003723e  xor     ebx, ebx
0x140037240  call    cs:__imp_RegQueryValueExW
0x140037247  nop     dword ptr [rax+rax+00h]
0x14003724c  test    eax, eax
0x14003724e  jz      short loc_140037265
0x140037250  mov     edx, r15d
0x140037253  mov     rcx, rdi
0x140037256  call    ?LoadDefaultSetting@CSettingsManager@@QEAAJW4_RASettingDWORD@@@Z; CSettingsManager::LoadDefaultSetting(_RASettingDWORD)
0x14003725b  mov     ecx, [rdi+r15*4+8]
0x140037260  mov     [r14], ecx
0x140037263  jmp     short loc_14003726B
0x140037265  mov     eax, [rbp+Data]
0x140037268  mov     [r14], eax
0x14003726b  mov     rcx, [rbp+hKey]; hKey
0x14003726f  test    rcx, rcx
0x140037272  jz      short loc_140037288
0x140037274  call    cs:__imp_RegCloseKey
0x14003727b  nop     dword ptr [rax+rax+00h]
0x140037280  mov     [rbp+hKey], 0
0x140037288  cmp     esi, 1
0x14003728b  jnz     short loc_14003729C
0x14003728d  mov     rcx, [rdi]; hMutex
0x140037290  call    cs:__imp_ReleaseMutex
0x140037297  nop     dword ptr [rax+rax+00h]
0x14003729c  lea     r11, [rsp+40h+var_s0]
0x1400372a1  mov     eax, ebx
0x1400372a3  mov     rbx, [r11+38h]
0x1400372a7  mov     rsi, [r11+40h]
0x1400372ab  mov     rsp, r11
0x1400372ae  pop     r15
0x1400372b0  pop     r14
0x1400372b2  pop     r12
0x1400372b4  pop     rdi
0x1400372b5  pop     rbp
0x1400372b6  retn
```
