# GetDisableEndEntityClientCheck(int *)

- ea: `0x18005ec10`
- end: `0x18005ed7f`
- name: `?GetDisableEndEntityClientCheck@@YAXPEAH@Z`
- size: `367`
- prototype: `void __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002e6b4`
- `0x18005e454`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18005ec10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ec8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ece5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005ece5`

## string_xrefs

- `0x18005ec6e`: `SYSTEM\CurrentControlSet\Services\RasMan\PPP\EAP\13`

## pseudocode

```c
void __fastcall GetDisableEndEntityClientCheck(int *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
  Data = 0;
  cbData = 4;
  hKey = 0;
  *a1 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13", 0, 1u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_12;
    v5 = 32;
  }
  else
  {
    v2 = RegQueryValueExW(hKey, L"DisableEndEntityClientCertCheck", 0, 0, (LPBYTE)&Data, &cbData);
    v3 = v2;
    if ( !v2 )
    {
      *a1 = Data == 1;
      goto LABEL_11;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_12;
    v5 = 33;
  }
  WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v2);
LABEL_11:
  v4 = WPP_GLOBAL_Control;
LABEL_12:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v4 = WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( *a1 )
  {
    if ( v4 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      return;
    v6 = 34;
  }
  else
  {
    if ( v4 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      return;
    v6 = 35;
  }
  WPP_SF_d(*((_QWORD *)v4 + 2), v6, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v3);
}

```

## disassembly

```asm
0x18005ec10  mov     [rsp+arg_18], rbx
0x18005ec15  push    rbp
0x18005ec16  push    rdi
0x18005ec17  push    r14
0x18005ec19  sub     rsp, 30h
0x18005ec1d  mov     rdi, rcx
0x18005ec20  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec27  lea     rbp, WPP_GLOBAL_Control
0x18005ec2e  lea     r14, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005ec35  cmp     rcx, rbp
0x18005ec38  jz      short loc_18005EC4B
0x18005ec3a  mov     rcx, [rcx+10h]
0x18005ec3e  mov     edx, 1Fh
0x18005ec43  mov     r8, r14
0x18005ec46  call    WPP_SF_
0x18005ec4b  lea     rax, [rsp+48h+hKey]
0x18005ec50  mov     [rsp+48h+Data], 0
0x18005ec58  mov     r9d, 1; samDesired
0x18005ec5e  mov     [rsp+48h+phkResult], rax; phkResult
0x18005ec63  xor     r8d, r8d; ulOptions
0x18005ec66  mov     [rsp+48h+cbData], 4
0x18005ec6e  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18005ec75  mov     [rsp+48h+hKey], 0
0x18005ec7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ec85  mov     dword ptr [rdi], 0
0x18005ec8b  call    cs:__imp_RegOpenKeyExW
0x18005ec92  nop     dword ptr [rax+rax+00h]
0x18005ec97  mov     ebx, eax
0x18005ec99  test    eax, eax
0x18005ec9b  jz      short loc_18005ECBF
0x18005ec9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eca4  cmp     rcx, rbp
0x18005eca7  jz      short loc_18005ED1D
0x18005eca9  mov     edx, 20h ; ' '
0x18005ecae  mov     rcx, [rcx+10h]
0x18005ecb2  mov     r9d, eax
0x18005ecb5  mov     r8, r14
0x18005ecb8  call    WPP_SF_d
0x18005ecbd  jmp     short loc_18005ED16
0x18005ecbf  mov     rcx, [rsp+48h+hKey]; hKey
0x18005ecc4  lea     rax, [rsp+48h+cbData]
0x18005ecc9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18005ecce  lea     rdx, aDisableendenti; "DisableEndEntityClientCertCheck"
0x18005ecd5  lea     rax, [rsp+48h+Data]
0x18005ecda  xor     r9d, r9d; lpType
0x18005ecdd  xor     r8d, r8d; lpReserved
0x18005ece0  mov     [rsp+48h+phkResult], rax; lpData
0x18005ece5  call    cs:__imp_RegQueryValueExW
0x18005ecec  nop     dword ptr [rax+rax+00h]
0x18005ecf1  mov     ebx, eax
0x18005ecf3  test    eax, eax
0x18005ecf5  jz      short loc_18005ED0A
0x18005ecf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ecfe  cmp     rcx, rbp
0x18005ed01  jz      short loc_18005ED1D
0x18005ed03  mov     edx, 21h ; '!'
0x18005ed08  jmp     short loc_18005ECAE
0x18005ed0a  xor     eax, eax
0x18005ed0c  cmp     [rsp+48h+Data], 1
0x18005ed11  setz    al
0x18005ed14  mov     [rdi], eax
0x18005ed16  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed1d  mov     rax, [rsp+48h+hKey]
0x18005ed22  test    rax, rax
0x18005ed25  jz      short loc_18005ED46
0x18005ed27  mov     rcx, rax; hKey
0x18005ed2a  call    cs:__imp_RegCloseKey
0x18005ed31  nop     dword ptr [rax+rax+00h]
0x18005ed36  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ed3d  mov     [rsp+48h+hKey], 0
0x18005ed46  cmp     dword ptr [rdi], 0
0x18005ed49  jz      short loc_18005ED57
0x18005ed4b  cmp     rcx, rbp
0x18005ed4e  jz      short loc_18005ED70
0x18005ed50  mov     edx, 22h ; '"'
0x18005ed55  jmp     short loc_18005ED61
0x18005ed57  cmp     rcx, rbp
0x18005ed5a  jz      short loc_18005ED70
0x18005ed5c  mov     edx, 23h ; '#'
0x18005ed61  mov     rcx, [rcx+10h]
0x18005ed65  mov     r9d, ebx
0x18005ed68  mov     r8, r14
0x18005ed6b  call    WPP_SF_d
0x18005ed70  mov     rbx, [rsp+48h+arg_18]
0x18005ed75  add     rsp, 30h
0x18005ed79  pop     r14
0x18005ed7b  pop     rdi
0x18005ed7c  pop     rbp
0x18005ed7d  retn
```
