# Microsoft::Windows::MDM::OmadmClient::Utilities::GetTestSettingDword(ushort const *,ushort const *,ulong *)

- ea: `0x140053720`
- end: `0x140053890`
- name: `?GetTestSettingDword@Utilities@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBG0PEAK@Z`
- size: `368`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::Utilities *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b0f4`
- `0x140053720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400537cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400537cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140053840`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140053840`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400537f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005387a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400537f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140053865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005387a`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x140053750`
- `dmEnrollEngine!__imp_OpenEnrollmentsHKEY` at `0x140053750`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::Utilities::GetTestSettingDword(
        Microsoft::Windows::MDM::OmadmClient::Utilities *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4)
{
  int v7; // eax
  unsigned int v8; // edi
  LSTATUS v10; // eax
  unsigned int v11; // ebx
  bool v12; // cc
  int phkResult; // [rsp+20h] [rbp-30h]
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  HKEY v17[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v17[0] = 0;
  hKey = 0;
  v7 = OpenEnrollmentsHKEY(131103, v17);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\utilities.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v17[0] )
      RegCloseKey(v17[0]);
    return v8;
  }
  v10 = RegOpenKeyExW(v17[0], a2, 0, 0x2001Fu, &hKey);
  v11 = v10;
  v12 = v10 <= 0;
  if ( v10
    || (Type = 0, cbData = 4, v10 = RegQueryValueExW(hKey, a3, 0, &Type, a4, &cbData), v11 = v10, v12 = v10 <= 0, v10) )
  {
    if ( !v12 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v17[0] )
      RegCloseKey(v17[0]);
    return v11;
  }
  else
  {
    if ( Type == 4 )
      goto LABEL_3;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v17[0] )
      RegCloseKey(v17[0]);
    return 2147944029LL;
  }
}

```

## disassembly

```asm
0x140053720  push    rbp
0x140053722  push    rbx
0x140053723  push    rsi
0x140053724  push    rdi
0x140053725  push    r14
0x140053727  mov     rbp, rsp
0x14005372a  sub     rsp, 50h
0x14005372e  mov     rbx, rdx
0x140053731  mov     [rbp+var_10], 0
0x140053739  lea     rdx, [rbp+var_10]
0x14005373d  mov     [rbp+hKey], 0
0x140053745  mov     ecx, 2001Fh
0x14005374a  mov     rsi, r9
0x14005374d  mov     r14, r8
0x140053750  call    cs:__imp_OpenEnrollmentsHKEY
0x140053757  nop     dword ptr [rax+rax+00h]
0x14005375c  mov     edi, eax
0x14005375e  test    eax, eax
0x140053760  jns     short loc_1400537B2
0x140053762  mov     rcx, [rbp+28h]; this
0x140053766  lea     r8, aOnecoreuapAdmi_9; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14005376d  mov     r9d, eax; char *
0x140053770  mov     edx, 168h; void *
0x140053775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005377a  mov     rcx, [rbp+hKey]; hKey
0x14005377e  test    rcx, rcx
0x140053781  jz      short loc_14005378F
0x140053783  call    cs:__imp_RegCloseKey
0x14005378a  nop     dword ptr [rax+rax+00h]
0x14005378f  mov     rcx, [rbp+var_10]; hKey
0x140053793  test    rcx, rcx
0x140053796  jz      short loc_1400537A4
0x140053798  call    cs:__imp_RegCloseKey
0x14005379f  nop     dword ptr [rax+rax+00h]
0x1400537a4  mov     eax, edi
0x1400537a6  add     rsp, 50h
0x1400537aa  pop     r14
0x1400537ac  pop     rdi
0x1400537ad  pop     rsi
0x1400537ae  pop     rbx
0x1400537af  pop     rbp
0x1400537b0  retn
0x1400537b2  mov     rcx, [rbp+var_10]; hKey
0x1400537b6  lea     rax, [rbp+hKey]
0x1400537ba  mov     r9d, 2001Fh; samDesired
0x1400537c0  mov     [rsp+50h+phkResult], rax; phkResult
0x1400537c5  xor     r8d, r8d; ulOptions
0x1400537c8  mov     rdx, rbx; lpSubKey
0x1400537cb  call    cs:__imp_RegOpenKeyExW
0x1400537d2  nop     dword ptr [rax+rax+00h]
0x1400537d7  mov     ebx, eax
0x1400537d9  test    eax, eax
0x1400537db  jz      short loc_140053816
0x1400537dd  jle     short loc_1400537E8
0x1400537df  movzx   ebx, ax
0x1400537e2  or      ebx, 80070000h
0x1400537e8  mov     rcx, [rbp+hKey]; hKey
0x1400537ec  test    rcx, rcx
0x1400537ef  jz      short loc_1400537FD
0x1400537f1  call    cs:__imp_RegCloseKey
0x1400537f8  nop     dword ptr [rax+rax+00h]
0x1400537fd  mov     rcx, [rbp+var_10]; hKey
0x140053801  test    rcx, rcx
0x140053804  jz      short loc_140053812
0x140053806  call    cs:__imp_RegCloseKey
0x14005380d  nop     dword ptr [rax+rax+00h]
0x140053812  mov     eax, ebx
0x140053814  jmp     short loc_1400537A6
0x140053816  mov     rcx, [rbp+hKey]; hKey
0x14005381a  lea     rax, [rbp+cbData]
0x14005381e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140053823  lea     r9, [rbp+Type]; lpType
0x140053827  xor     r8d, r8d; lpReserved
0x14005382a  mov     [rsp+50h+phkResult], rsi; lpData
0x14005382f  mov     rdx, r14; lpValueName
0x140053832  mov     [rbp+Type], 0
0x140053839  mov     [rbp+cbData], 4
0x140053840  call    cs:__imp_RegQueryValueExW
0x140053847  nop     dword ptr [rax+rax+00h]
0x14005384c  mov     ebx, eax
0x14005384e  test    eax, eax
0x140053850  jnz     short loc_1400537DD
0x140053852  cmp     [rbp+Type], 4
0x140053856  jz      loc_14005377A
0x14005385c  mov     rcx, [rbp+hKey]; hKey
0x140053860  test    rcx, rcx
0x140053863  jz      short loc_140053871
0x140053865  call    cs:__imp_RegCloseKey
0x14005386c  nop     dword ptr [rax+rax+00h]
0x140053871  mov     rcx, [rbp+var_10]; hKey
0x140053875  test    rcx, rcx
0x140053878  jz      short loc_140053886
0x14005387a  call    cs:__imp_RegCloseKey
0x140053881  nop     dword ptr [rax+rax+00h]
0x140053886  mov     eax, 8007065Dh
0x14005388b  jmp     loc_1400537A6
```
