# UpgradeSecureVpnOption

- ea: `0x18007ebf8`
- end: `0x18007edd2`
- name: `UpgradeSecureVpnOption`
- size: `474`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18007e950`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18007ebf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ecb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ecb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ed8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007ed8b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007ed6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007ed6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ed20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007ed20`

## string_xrefs

- `0x18007eca6`: `System\CurrentControlSet\Services\Rasman\PPP`

## pseudocode

```c
__int64 __fastcall UpgradeSecureVpnOption(HKEY hKey, __int64 a2)
{
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // rdx
  HKEY hKeya; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 864, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  hKeya = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( !a2 )
  {
    v5 = 87;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    {
      v6 = 865;
LABEL_31:
      WPP_SF_d(v4[1].Flink, v6, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\Rasman\\PPP", 0, 0x20019u, &hKeya);
  v5 = v7;
  if ( v7 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 866;
LABEL_15:
      WPP_SF_d(v4[1].Flink, v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
LABEL_24:
      v4 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v7 = RegQueryValueExW(hKeya, L"SecureVPN", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v7;
    if ( !v7 )
    {
      if ( Data )
        *(_DWORD *)(a2 + 164) = 512;
      RegDeleteValueW(hKeya, L"SecureVPN");
      goto LABEL_24;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 867;
      goto LABEL_15;
    }
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
  {
    v6 = 868;
    goto LABEL_31;
  }
  return v5;
}

```

## disassembly

```asm
0x18007ebf8  push    rbp
0x18007ebfa  push    rbx
0x18007ebfb  push    rdi
0x18007ebfc  push    r12
0x18007ebfe  push    r15
0x18007ec00  mov     rbp, rsp
0x18007ec03  sub     rsp, 40h
0x18007ec07  mov     rdi, rdx
0x18007ec0a  mov     rbx, rcx
0x18007ec0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec14  lea     r15, WPP_GLOBAL_Control
0x18007ec1b  lea     r12, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007ec22  cmp     rcx, r15
0x18007ec25  jz      short loc_18007EC4B
0x18007ec27  test    byte ptr [rcx+1Ch], 80h
0x18007ec2b  jz      short loc_18007EC4B
0x18007ec2d  cmp     byte ptr [rcx+19h], 6
0x18007ec31  jb      short loc_18007EC4B
0x18007ec33  mov     rcx, [rcx+10h]
0x18007ec37  mov     edx, 360h
0x18007ec3c  mov     r8, r12
0x18007ec3f  call    WPP_SF_
0x18007ec44  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec4b  mov     [rbp+hKey], 0
0x18007ec53  mov     eax, 4
0x18007ec58  mov     [rbp+Type], eax
0x18007ec5b  mov     [rbp+cbData], eax
0x18007ec5e  mov     [rbp+Data], 0
0x18007ec65  test    rdi, rdi
0x18007ec68  jnz     short loc_18007EC94
0x18007ec6a  lea     ebx, [rax+53h]
0x18007ec6d  cmp     rcx, r15
0x18007ec70  jz      loc_18007EDC3
0x18007ec76  test    byte ptr [rcx+1Ch], 80h
0x18007ec7a  jz      loc_18007EDC3
0x18007ec80  cmp     byte ptr [rcx+19h], 6
0x18007ec84  jb      loc_18007EDC3
0x18007ec8a  mov     edx, 361h
0x18007ec8f  jmp     loc_18007EDB4
0x18007ec94  lea     rax, [rbp+hKey]
0x18007ec98  mov     r9d, 20019h; samDesired
0x18007ec9e  xor     r8d, r8d; ulOptions
0x18007eca1  mov     [rsp+40h+phkResult], rax; phkResult
0x18007eca6  lea     rdx, c_pszRegKeySecureVpn; "System\\CurrentControlSet\\Services\\Ra"...
0x18007ecad  mov     rcx, rbx; hKey
0x18007ecb0  call    cs:__imp_RegOpenKeyExW
0x18007ecb7  nop     dword ptr [rax+rax+00h]
0x18007ecbc  mov     ebx, eax
0x18007ecbe  test    eax, eax
0x18007ecc0  jz      short loc_18007ECFC
0x18007ecc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ecc9  cmp     rcx, r15
0x18007eccc  jz      loc_18007ED7F
0x18007ecd2  test    byte ptr [rcx+1Ch], 80h
0x18007ecd6  jz      loc_18007ED7F
0x18007ecdc  cmp     byte ptr [rcx+19h], 2
0x18007ece0  jb      loc_18007ED7F
0x18007ece6  mov     edx, 362h
0x18007eceb  mov     rcx, [rcx+10h]
0x18007ecef  mov     r9d, eax
0x18007ecf2  mov     r8, r12
0x18007ecf5  call    WPP_SF_d
0x18007ecfa  jmp     short loc_18007ED78
0x18007ecfc  mov     rcx, [rbp+hKey]; hKey
0x18007ed00  lea     rax, [rbp+cbData]
0x18007ed04  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18007ed09  lea     r9, [rbp+Type]; lpType
0x18007ed0d  lea     rax, [rbp+Data]
0x18007ed11  xor     r8d, r8d; lpReserved
0x18007ed14  lea     rdx, c_pszRegValSecureVpn; "SecureVPN"
0x18007ed1b  mov     [rsp+40h+phkResult], rax; lpData
0x18007ed20  call    cs:__imp_RegQueryValueExW
0x18007ed27  nop     dword ptr [rax+rax+00h]
0x18007ed2c  mov     ebx, eax
0x18007ed2e  test    eax, eax
0x18007ed30  jz      short loc_18007ED51
0x18007ed32  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed39  cmp     rcx, r15
0x18007ed3c  jz      short loc_18007ED7F
0x18007ed3e  test    byte ptr [rcx+1Ch], 80h
0x18007ed42  jz      short loc_18007ED7F
0x18007ed44  cmp     byte ptr [rcx+19h], 2
0x18007ed48  jb      short loc_18007ED7F
0x18007ed4a  mov     edx, 363h
0x18007ed4f  jmp     short loc_18007ECEB
0x18007ed51  cmp     [rbp+Data], 0
0x18007ed55  jz      short loc_18007ED61
0x18007ed57  mov     dword ptr [rdi+0A4h], 200h
0x18007ed61  mov     rcx, [rbp+hKey]; hKey
0x18007ed65  lea     rdx, c_pszRegValSecureVpn; "SecureVPN"
0x18007ed6c  call    cs:__imp_RegDeleteValueW
0x18007ed73  nop     dword ptr [rax+rax+00h]
0x18007ed78  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed7f  mov     rax, [rbp+hKey]
0x18007ed83  test    rax, rax
0x18007ed86  jz      short loc_18007ED9E
0x18007ed88  mov     rcx, rax; hKey
0x18007ed8b  call    cs:__imp_RegCloseKey
0x18007ed92  nop     dword ptr [rax+rax+00h]
0x18007ed97  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed9e  cmp     rcx, r15
0x18007eda1  jz      short loc_18007EDC3
0x18007eda3  test    byte ptr [rcx+1Ch], 80h
0x18007eda7  jz      short loc_18007EDC3
0x18007eda9  cmp     byte ptr [rcx+19h], 6
0x18007edad  jb      short loc_18007EDC3
0x18007edaf  mov     edx, 364h
0x18007edb4  mov     rcx, [rcx+10h]
0x18007edb8  mov     r9d, ebx
0x18007edbb  mov     r8, r12
0x18007edbe  call    WPP_SF_d
0x18007edc3  mov     eax, ebx
0x18007edc5  add     rsp, 40h
0x18007edc9  pop     r15
0x18007edcb  pop     r12
0x18007edcd  pop     rdi
0x18007edce  pop     rbx
0x18007edcf  pop     rbp
0x18007edd0  retn
```
