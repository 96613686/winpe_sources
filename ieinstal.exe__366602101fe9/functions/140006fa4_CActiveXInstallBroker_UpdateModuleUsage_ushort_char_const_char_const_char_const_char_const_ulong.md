# CActiveXInstallBroker::UpdateModuleUsage(ushort *,char const *,char const *,char const *,char const *,ulong)

- ea: `0x140006fa4`
- end: `0x140007338`
- name: `?UpdateModuleUsage@CActiveXInstallBroker@@QEAAJPEAGPEBD111K@Z`
- size: `916`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, const char *, const char *, LPCSTR lpString2, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400085b0`

## callees

- `0x140001af3`
- `0x140006fa4`
- `0x140007340`
- `0x14000d314`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400071d4`
- `ADVAPI32!RegCloseKey` at `0x1400071ea`
- `ADVAPI32!RegCloseKey` at `0x1400071d4`
- `ADVAPI32!RegCloseKey` at `0x1400071ea`
- `ADVAPI32!RegCreateKeyW` at `0x1400070fc`
- `ADVAPI32!RegCreateKeyW` at `0x1400070fc`
- `ADVAPI32!RegOpenKeyExW` at `0x1400070db`
- `ADVAPI32!RegOpenKeyExW` at `0x1400070db`
- `ADVAPI32!RegOpenKeyExA` at `0x14000712d`
- `ADVAPI32!RegOpenKeyExA` at `0x14000712d`
- `ADVAPI32!RegSetValueExA` at `0x140007283`
- `ADVAPI32!RegSetValueExA` at `0x14000730d`
- `ADVAPI32!RegSetValueExA` at `0x140007283`
- `ADVAPI32!RegSetValueExA` at `0x14000730d`
- `ADVAPI32!RegQueryValueExA` at `0x140007188`
- `ADVAPI32!RegQueryValueExA` at `0x1400072c3`
- `ADVAPI32!RegQueryValueExA` at `0x140007188`
- `ADVAPI32!RegQueryValueExA` at `0x1400072c3`
- `ADVAPI32!RegCreateKeyA` at `0x14000714c`
- `ADVAPI32!RegCreateKeyA` at `0x14000714c`
- `KERNEL32!lstrcmpiA` at `0x1400071a4`
- `KERNEL32!lstrcmpiA` at `0x1400071a4`
- `KERNEL32!LeaveCriticalSection` at `0x140007211`
- `KERNEL32!LeaveCriticalSection` at `0x140007211`
- `KERNEL32!EnterCriticalSection` at `0x14000704e`
- `KERNEL32!EnterCriticalSection` at `0x14000704e`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::UpdateModuleUsage(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        const char *a3,
        char *a4,
        const BYTE *lpString2,
        const char *a6,
        char a7)
{
  const BYTE *v7; // r14
  CActiveXInstallBroker *v10; // rcx
  __int64 v11; // r15
  __int64 v12; // rax
  int v13; // esi
  unsigned int updated; // ebx
  __int64 v15; // rdx
  int v16; // eax
  int v17; // ecx
  LSTATUS v18; // eax
  bool v19; // cc
  DWORD v21; // ecx
  const BYTE *v22; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v24; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPCSTR lpSubKey; // [rsp+58h] [rbp-A8h]
  DWORD v29[2]; // [rsp+60h] [rbp-A0h]
  char *v30; // [rsp+68h] [rbp-98h]
  BYTE Data; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[271]; // [rsp+71h] [rbp-8Fh] BYREF

  v7 = (const BYTE *)a6;
  lpSubKey = a3;
  hKey = 0;
  phkResult = 0;
  v24 = 0;
  Type = 0;
  Data = 0;
  v30 = a4;
  memset_0(v32, 0, 0x103u);
  v11 = -1;
  cbData = 260;
  v12 = -1;
  do
    ++v12;
  while ( lpString2[v12] );
  *(_QWORD *)v29 = v12;
  if ( !*(_DWORD *)this )
  {
LABEL_27:
    updated = CActiveXInstallBroker::UpdateSharedDlls(v10, v30);
    goto LABEL_28;
  }
  v13 = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 12) < 7 )
  {
    updated = -2147019873;
    goto LABEL_22;
  }
  if ( !a2 || !lpSubKey )
    goto LABEL_21;
  v15 = *((_QWORD *)this + 8) - (_QWORD)a2;
  do
  {
    v16 = *(unsigned __int16 *)((char *)a2 + v15);
    v17 = *a2 - v16;
    if ( v17 )
      break;
    ++a2;
  }
  while ( v16 );
  if ( v17 )
  {
    updated = -2147024891;
    goto LABEL_22;
  }
  updated = GetRegistrationRootKeyFromIntegrityLevel(&hKey);
  if ( updated )
    goto LABEL_22;
  if ( RegOpenKeyExW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ModuleUsage", 0, 0x2001Fu, &phkResult) )
  {
    v18 = RegCreateKeyW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ModuleUsage", &phkResult);
    v19 = v18 <= 0;
    if ( v18 )
      goto LABEL_42;
  }
  if ( RegOpenKeyExA(phkResult, lpSubKey, 0, 0x2001Fu, &v24) )
  {
    v18 = RegCreateKeyA(phkResult, lpSubKey, &v24);
    v19 = v18 <= 0;
    if ( v18 )
      goto LABEL_42;
  }
  if ( RegQueryValueExA(v24, ".Owner", 0, &Type, &Data, &cbData) )
  {
    v21 = 14;
    if ( (a7 & 1) != 0 )
      v21 = v29[0];
    v22 = lpString2;
    if ( (a7 & 1) == 0 )
      v22 = "Unknown Owner";
    v18 = RegSetValueExA(v24, ".Owner", 0, 1u, v22, v21);
    v19 = v18 <= 0;
    if ( !v18 )
      goto LABEL_36;
LABEL_42:
    if ( v19 )
      updated = v18;
    else
      updated = (unsigned __int16)v18 | 0x80070000;
    goto LABEL_22;
  }
  if ( lstrcmpiA((LPCSTR)&Data, (LPCSTR)lpString2) && (a7 & 1) != 0 )
  {
LABEL_21:
    updated = -2147024809;
    goto LABEL_22;
  }
LABEL_36:
  cbData = 260;
  if ( !RegQueryValueExA(v24, (LPCSTR)lpString2, 0, &Type, &Data, &cbData) )
  {
    v13 = 0;
    goto LABEL_22;
  }
  if ( !a6 )
    v7 = &byte_140012D60;
  do
    ++v11;
  while ( v7[v11] );
  v18 = RegSetValueExA(v24, (LPCSTR)lpString2, 0, 1u, v7, v11 + 1);
  v19 = v18 <= 0;
  if ( v18 )
    goto LABEL_42;
LABEL_22:
  if ( v24 )
    RegCloseKey(v24);
  v10 = (CActiveXInstallBroker *)phkResult;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v13 )
    goto LABEL_27;
LABEL_28:
  if ( *(_DWORD *)this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return updated;
}

```

## disassembly

```asm
0x140006fa4  mov     [rsp-8+arg_8], rbx
0x140006fa9  push    rbp
0x140006faa  push    rsi
0x140006fab  push    rdi
0x140006fac  push    r12
0x140006fae  push    r13
0x140006fb0  push    r14
0x140006fb2  push    r15
0x140006fb4  lea     rbp, [rsp-90h]
0x140006fbc  sub     rsp, 190h
0x140006fc3  mov     rax, cs:__security_cookie
0x140006fca  xor     rax, rsp
0x140006fcd  mov     [rbp+0C0h+var_40], rax
0x140006fd4  mov     r14, [rbp+0C0h+arg_28]
0x140006fdb  xor     esi, esi
0x140006fdd  mov     r12, [rbp+0C0h+lpString2]
0x140006fe4  mov     rbx, rdx
0x140006fe7  mov     [rsp+1C0h+lpSubKey], r8
0x140006fec  mov     r13, rcx
0x140006fef  xor     edx, edx; Val
0x140006ff1  mov     [rsp+1C0h+hKey], rsi
0x140006ff6  mov     r8d, 103h; Size
0x140006ffc  mov     [rsp+1C0h+var_178], rsi
0x140007001  lea     rcx, [rsp+1C0h+var_14F]; void *
0x140007006  mov     [rsp+1C0h+var_188], rsi
0x14000700b  mov     [rsp+1C0h+Type], esi
0x14000700f  mov     [rsp+1C0h+Data], sil
0x140007014  mov     [rsp+1C0h+var_158], r9
0x140007019  call    memset_0
0x14000701e  or      r15, 0FFFFFFFFFFFFFFFFh
0x140007022  mov     [rsp+1C0h+cbData], 104h
0x14000702a  mov     rax, r15
0x14000702d  inc     rax
0x140007030  cmp     [r12+rax], sil
0x140007034  jnz     short loc_14000702D
0x140007036  mov     qword ptr [rsp+1C0h+var_160], rax
0x14000703b  cmp     [r13+0], esi
0x14000703f  jz      loc_1400071FA
0x140007045  lea     rcx, [r13+8]; lpCriticalSection
0x140007049  mov     esi, 1
0x14000704e  call    cs:__imp_EnterCriticalSection
0x140007055  nop     dword ptr [rax+rax+00h]
0x14000705a  cmp     dword ptr [r13+30h], 7
0x14000705f  jge     short loc_14000706B
0x140007061  mov     ebx, 8007139Fh
0x140007066  jmp     loc_1400071CA
0x14000706b  test    rbx, rbx
0x14000706e  jz      loc_1400071C5
0x140007074  cmp     [rsp+1C0h+lpSubKey], 0
0x14000707a  jz      loc_1400071C5
0x140007080  mov     rdx, [r13+40h]
0x140007084  sub     rdx, rbx
0x140007087  movzx   ecx, word ptr [rbx]
0x14000708a  movzx   eax, word ptr [rbx+rdx]
0x14000708e  sub     ecx, eax
0x140007090  jnz     short loc_14000709A
0x140007092  add     rbx, 2
0x140007096  test    eax, eax
0x140007098  jnz     short loc_140007087
0x14000709a  test    ecx, ecx
0x14000709c  jz      short loc_1400070A8
0x14000709e  mov     ebx, 80070005h
0x1400070a3  jmp     loc_1400071CA
0x1400070a8  lea     rcx, [rsp+1C0h+hKey]; HKEY *
0x1400070ad  call    ?GetRegistrationRootKeyFromIntegrityLevel@@YAJPEAPEAUHKEY__@@@Z; GetRegistrationRootKeyFromIntegrityLevel(HKEY__ * *)
0x1400070b2  mov     ebx, eax
0x1400070b4  test    eax, eax
0x1400070b6  jnz     loc_1400071CA
0x1400070bc  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1400070c1  lea     rax, [rsp+1C0h+var_178]
0x1400070c6  mov     r9d, 2001Fh; samDesired
0x1400070cc  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1400070d1  xor     r8d, r8d; ulOptions
0x1400070d4  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400070db  call    cs:__imp_RegOpenKeyExW
0x1400070e2  nop     dword ptr [rax+rax+00h]
0x1400070e7  test    eax, eax
0x1400070e9  jz      short loc_140007110
0x1400070eb  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1400070f0  lea     r8, [rsp+1C0h+var_178]; phkResult
0x1400070f5  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400070fc  call    cs:__imp_RegCreateKeyW
0x140007103  nop     dword ptr [rax+rax+00h]
0x140007108  test    eax, eax
0x14000710a  jnz     loc_140007321
0x140007110  mov     rdx, [rsp+1C0h+lpSubKey]; lpSubKey
0x140007115  lea     rax, [rsp+1C0h+var_188]
0x14000711a  mov     rcx, [rsp+1C0h+var_178]; hKey
0x14000711f  mov     r9d, 2001Fh; samDesired
0x140007125  xor     r8d, r8d; ulOptions
0x140007128  mov     [rsp+1C0h+phkResult], rax; phkResult
0x14000712d  call    cs:__imp_RegOpenKeyExA
0x140007134  nop     dword ptr [rax+rax+00h]
0x140007139  test    eax, eax
0x14000713b  jz      short loc_140007160
0x14000713d  mov     rdx, [rsp+1C0h+lpSubKey]; lpSubKey
0x140007142  lea     r8, [rsp+1C0h+var_188]; phkResult
0x140007147  mov     rcx, [rsp+1C0h+var_178]; hKey
0x14000714c  call    cs:__imp_RegCreateKeyA
0x140007153  nop     dword ptr [rax+rax+00h]
0x140007158  test    eax, eax
0x14000715a  jnz     loc_140007321
0x140007160  mov     rcx, [rsp+1C0h+var_188]; hKey
0x140007165  lea     rax, [rsp+1C0h+cbData]
0x14000716a  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x14000716f  lea     r9, [rsp+1C0h+Type]; lpType
0x140007174  lea     rax, [rsp+1C0h+Data]
0x140007179  xor     r8d, r8d; lpReserved
0x14000717c  lea     rdx, aOwner; ".Owner"
0x140007183  mov     [rsp+1C0h+phkResult], rax; lpData
0x140007188  call    cs:__imp_RegQueryValueExA
0x14000718f  nop     dword ptr [rax+rax+00h]
0x140007194  test    eax, eax
0x140007196  jnz     loc_14000724A
0x14000719c  mov     rdx, r12; lpString2
0x14000719f  lea     rcx, [rsp+1C0h+Data]; lpString1
0x1400071a4  call    cs:__imp_lstrcmpiA
0x1400071ab  nop     dword ptr [rax+rax+00h]
0x1400071b0  test    eax, eax
0x1400071b2  jz      loc_140007297
0x1400071b8  test    byte ptr [rbp+0C0h+arg_30], sil
0x1400071bf  jz      loc_140007297
0x1400071c5  mov     ebx, 80070057h
0x1400071ca  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1400071cf  test    rcx, rcx
0x1400071d2  jz      short loc_1400071E0
0x1400071d4  call    cs:__imp_RegCloseKey
0x1400071db  nop     dword ptr [rax+rax+00h]
0x1400071e0  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1400071e5  test    rcx, rcx
0x1400071e8  jz      short loc_1400071F6
0x1400071ea  call    cs:__imp_RegCloseKey
0x1400071f1  nop     dword ptr [rax+rax+00h]
0x1400071f6  test    esi, esi
0x1400071f8  jz      short loc_140007206
0x1400071fa  mov     rdx, [rsp+1C0h+var_158]; char *
0x1400071ff  call    ?UpdateSharedDlls@CActiveXInstallBroker@@AEAAJPEBD@Z; CActiveXInstallBroker::UpdateSharedDlls(char const *)
0x140007204  mov     ebx, eax
0x140007206  cmp     dword ptr [r13+0], 0
0x14000720b  jz      short loc_14000721D
0x14000720d  lea     rcx, [r13+8]; lpCriticalSection
0x140007211  call    cs:__imp_LeaveCriticalSection
0x140007218  nop     dword ptr [rax+rax+00h]
0x14000721d  mov     eax, ebx
0x14000721f  mov     rcx, [rbp+0C0h+var_40]
0x140007226  xor     rcx, rsp; StackCookie
0x140007229  call    __security_check_cookie
0x14000722e  mov     rbx, [rsp+1C0h+arg_8]
0x140007236  add     rsp, 190h
0x14000723d  pop     r15
0x14000723f  pop     r14
0x140007241  pop     r13
0x140007243  pop     r12
0x140007245  pop     rdi
0x140007246  pop     rsi
0x140007247  pop     rbp
0x140007248  retn
0x14000724a  test    [rbp+0C0h+arg_30], esi
0x140007250  lea     r9, aUnknownOwner; "Unknown Owner"
0x140007257  mov     ecx, 0Eh
0x14000725c  lea     rdx, aOwner; ".Owner"
0x140007263  cmovnz  ecx, [rsp+1C0h+var_160]
0x140007268  mov     rax, r12
0x14000726b  cmovz   rax, r9
0x14000726f  mov     dword ptr [rsp+1C0h+lpcbData], ecx; cbData
0x140007273  mov     rcx, [rsp+1C0h+var_188]; hKey
0x140007278  mov     r9d, esi; dwType
0x14000727b  xor     r8d, r8d; Reserved
0x14000727e  mov     [rsp+1C0h+phkResult], rax; lpData
0x140007283  call    cs:__imp_RegSetValueExA
0x14000728a  nop     dword ptr [rax+rax+00h]
0x14000728f  test    eax, eax
0x140007291  jnz     loc_140007321
0x140007297  mov     rcx, [rsp+1C0h+var_188]; hKey
0x14000729c  lea     rax, [rsp+1C0h+cbData]
0x1400072a1  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1400072a6  lea     r9, [rsp+1C0h+Type]; lpType
0x1400072ab  lea     rax, [rsp+1C0h+Data]
0x1400072b0  mov     [rsp+1C0h+cbData], 104h
0x1400072b8  xor     r8d, r8d; lpReserved
0x1400072bb  mov     [rsp+1C0h+phkResult], rax; lpData
0x1400072c0  mov     rdx, r12; lpValueName
0x1400072c3  call    cs:__imp_RegQueryValueExA
0x1400072ca  nop     dword ptr [rax+rax+00h]
0x1400072cf  test    eax, eax
0x1400072d1  jnz     short loc_1400072DA
0x1400072d3  xor     esi, esi
0x1400072d5  jmp     loc_1400071CA
0x1400072da  test    r14, r14
0x1400072dd  lea     rax, byte_140012D60
0x1400072e4  cmovz   r14, rax
0x1400072e8  inc     r15
0x1400072eb  cmp     byte ptr [r14+r15], 0
0x1400072f0  jnz     short loc_1400072E8
0x1400072f2  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1400072f7  lea     eax, [r15+1]
0x1400072fb  mov     dword ptr [rsp+1C0h+lpcbData], eax; cbData
0x1400072ff  mov     r9d, esi; dwType
0x140007302  xor     r8d, r8d; Reserved
0x140007305  mov     [rsp+1C0h+phkResult], r14; lpData
0x14000730a  mov     rdx, r12; lpValueName
0x14000730d  call    cs:__imp_RegSetValueExA
0x140007314  nop     dword ptr [rax+rax+00h]
0x140007319  test    eax, eax
0x14000731b  jz      loc_1400071CA
0x140007321  jg      short loc_14000732A
0x140007323  mov     ebx, eax
0x140007325  jmp     loc_1400071CA
0x14000732a  movzx   ebx, ax
0x14000732d  or      ebx, 80070000h
0x140007333  jmp     loc_1400071CA
```
