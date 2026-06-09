# NcaRegIsKeyPresent

- ea: `0x180003240`
- end: `0x1800033b4`
- name: `NcaRegIsKeyPresent`
- size: `372`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800026d0`
- `0x1800031f0`

## callees

- `0x180003240`
- `0x1800033bc`
- `0x180004f34`
- `0x1800199b4`
- `0x180019dac`
- `0x18001a7c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003395`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003395`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800032b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800032b5`

## string_xrefs

- `0x180003275`: `SOFTWARE\Policies\Microsoft\Windows NT\DNSClient\DnsPolicyConfig`
- `0x1800032a5`: `SOFTWARE\Policies\Microsoft\Windows NT\DNSClient\DnsPolicyConfig`
- `0x1800032da`: `NcaRegOpenKey`
- `0x1800032ec`: `NcaRegOpenKey`
- `0x1800032d0`: `RegOpenKeyExW`

## pseudocode

```c
_BOOL8 __fastcall NcaRegIsKeyPresent(__int64 a1)
{
  HKEY v1; // rdi
  unsigned int v2; // eax
  BOOL v3; // ebx
  int v4; // eax
  __int64 v5; // r9
  _BOOL8 result; // rax
  int NumKeys; // eax
  __int64 cSubKeys; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  cSubKeys = a1;
  phkResult = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_149084e4aca63d179354f111bb13106e_Traceguids,
      L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\DNSClient\\DnsPolicyConfig");
  v1 = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\DNSClient\\DnsPolicyConfig",
         0,
         9u,
         &phkResult);
  if ( v2 == 2 )
  {
    v3 = 0;
    goto LABEL_14;
  }
  if ( !v2 )
  {
    v1 = phkResult;
    v3 = 1;
    goto LABEL_14;
  }
  v3 = 0;
  v4 = NcaReportErrorAsWinError("NcaRegOpenKey", "RegOpenKeyExW", v2);
  if ( v4 >= 0 )
  {
LABEL_14:
    if ( v3 )
    {
      LODWORD(cSubKeys) = 0;
      NumKeys = NcaRegQueryNumKeys(v1, (LPDWORD)&cSubKeys);
      if ( NumKeys >= 0 )
      {
        v3 = cSubKeys != 0;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_149084e4aca63d179354f111bb13106e_Traceguids,
          (unsigned int)NumKeys);
      }
    }
    if ( v1 )
      RegCloseKey(v1);
    return v3;
  }
  v5 = (unsigned int)NcaReportReturnError("NcaRegOpenKey", (unsigned int)v4);
  result = 0;
  if ( (int)v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_149084e4aca63d179354f111bb13106e_Traceguids, v5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180003240  mov     [rsp+arg_18], rbp
0x180003245  mov     [rsp+cSubKeys], rcx
0x18000324a  push    rdi
0x18000324b  sub     rsp, 30h
0x18000324f  mov     [rsp+38h+arg_8], 0
0x180003258  mov     rcx, cs:WPP_GLOBAL_Control
0x18000325f  lea     rbp, WPP_GLOBAL_Control
0x180003266  cmp     rcx, rbp
0x180003269  jz      short loc_18000328D
0x18000326b  test    byte ptr [rcx+1Ch], 8
0x18000326f  jz      short loc_18000328D
0x180003271  mov     rcx, [rcx+10h]
0x180003275  lea     r9, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x18000327c  mov     edx, 0Bh
0x180003281  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x180003288  call    WPP_SF_S
0x18000328d  lea     rax, [rsp+38h+arg_8]
0x180003292  mov     [rsp+38h+arg_10], rbx
0x180003297  mov     r9d, 9; samDesired
0x18000329d  mov     [rsp+38h+phkResult], rax; phkResult
0x1800032a2  xor     r8d, r8d; ulOptions
0x1800032a5  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x1800032ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800032b3  xor     edi, edi
0x1800032b5  call    cs:__imp_RegOpenKeyExW
0x1800032bc  nop     dword ptr [rax+rax+00h]
0x1800032c1  cmp     eax, 2
0x1800032c4  jnz     short loc_1800032CA
0x1800032c6  xor     ebx, ebx
0x1800032c8  jmp     short loc_18000333B
0x1800032ca  test    eax, eax
0x1800032cc  jz      short loc_180003331
0x1800032ce  xor     ebx, ebx
0x1800032d0  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800032d7  mov     r8d, eax
0x1800032da  lea     rcx, aNcaregopenkey; "NcaRegOpenKey"
0x1800032e1  call    NcaReportErrorAsWinError
0x1800032e6  test    eax, eax
0x1800032e8  jns     short loc_18000333B
0x1800032ea  mov     edx, eax
0x1800032ec  lea     rcx, aNcaregopenkey; "NcaRegOpenKey"
0x1800032f3  call    NcaReportReturnError
0x1800032f8  mov     r9d, eax
0x1800032fb  xor     eax, eax
0x1800032fd  test    r9d, r9d
0x180003300  jns     loc_1800033A3
0x180003306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000330d  cmp     rcx, rbp
0x180003310  jz      short loc_18000332D
0x180003312  test    byte ptr [rcx+1Ch], 1
0x180003316  jz      short loc_18000332D
0x180003318  mov     rcx, [rcx+10h]
0x18000331c  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x180003323  mov     edx, 13h
0x180003328  call    WPP_SF_d
0x18000332d  xor     eax, eax
0x18000332f  jmp     short loc_1800033A3
0x180003331  mov     rdi, [rsp+38h+arg_8]
0x180003336  mov     ebx, 1
0x18000333b  test    ebx, ebx
0x18000333d  jz      short loc_18000338D
0x18000333f  lea     rdx, [rsp+38h+cSubKeys]; lpcSubKeys
0x180003344  mov     dword ptr [rsp+38h+cSubKeys], 0
0x18000334c  mov     rcx, rdi; hKey
0x18000334f  call    NcaRegQueryNumKeys
0x180003354  test    eax, eax
0x180003356  jns     short loc_180003384
0x180003358  mov     rcx, cs:WPP_GLOBAL_Control
0x18000335f  cmp     rcx, rbp
0x180003362  jz      short loc_18000338D
0x180003364  test    byte ptr [rcx+1Ch], 1
0x180003368  jz      short loc_18000338D
0x18000336a  mov     rcx, [rcx+10h]
0x18000336e  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x180003375  mov     edx, 14h
0x18000337a  mov     r9d, eax
0x18000337d  call    WPP_SF_d
0x180003382  jmp     short loc_18000338D
0x180003384  xor     ebx, ebx
0x180003386  cmp     dword ptr [rsp+38h+cSubKeys], ebx
0x18000338a  setnbe  bl
0x18000338d  test    rdi, rdi
0x180003390  jz      short loc_1800033A1
0x180003392  mov     rcx, rdi; hKey
0x180003395  call    cs:__imp_RegCloseKey
0x18000339c  nop     dword ptr [rax+rax+00h]
0x1800033a1  mov     eax, ebx
0x1800033a3  mov     rbx, [rsp+38h+arg_10]
0x1800033a8  mov     rbp, [rsp+38h+arg_18]
0x1800033ad  add     rsp, 30h
0x1800033b1  pop     rdi
0x1800033b2  retn
```
