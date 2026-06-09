# GetDisableEndEntityClientCheck(int *)

- ea: `0x18005b734`
- end: `0x18005b890`
- name: `?GetDisableEndEntityClientCheck@@YAXPEAH@Z`
- size: `348`
- prototype: `void __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18002c214`
- `0x18005b00c`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18005b734`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b842`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b842`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b7af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005b803`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005b803`

## string_xrefs

- `0x18005b792`: `SYSTEM\CurrentControlSet\Services\RasMan\PPP\EAP\13`

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
0x18005b734  mov     [rsp+arg_18], rbx
0x18005b739  push    rbp
0x18005b73a  push    rdi
0x18005b73b  push    r14
0x18005b73d  sub     rsp, 30h
0x18005b741  mov     rdi, rcx
0x18005b744  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b74b  lea     rbp, WPP_GLOBAL_Control
0x18005b752  lea     r14, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x18005b759  cmp     rcx, rbp
0x18005b75c  jz      short loc_18005B76F
0x18005b75e  mov     rcx, [rcx+10h]
0x18005b762  mov     edx, 1Fh
0x18005b767  mov     r8, r14
0x18005b76a  call    WPP_SF_
0x18005b76f  lea     rax, [rsp+48h+hKey]
0x18005b774  mov     [rsp+48h+Data], 0
0x18005b77c  mov     r9d, 1; samDesired
0x18005b782  mov     [rsp+48h+phkResult], rax; phkResult
0x18005b787  xor     r8d, r8d; ulOptions
0x18005b78a  mov     [rsp+48h+cbData], 4
0x18005b792  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18005b799  mov     [rsp+48h+hKey], 0
0x18005b7a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b7a9  mov     dword ptr [rdi], 0
0x18005b7af  call    cs:__imp_RegOpenKeyExW
0x18005b7b5  mov     ebx, eax
0x18005b7b7  test    eax, eax
0x18005b7b9  jz      short loc_18005B7DD
0x18005b7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b7c2  cmp     rcx, rbp
0x18005b7c5  jz      short loc_18005B835
0x18005b7c7  mov     edx, 20h ; ' '
0x18005b7cc  mov     rcx, [rcx+10h]
0x18005b7d0  mov     r9d, eax
0x18005b7d3  mov     r8, r14
0x18005b7d6  call    WPP_SF_d
0x18005b7db  jmp     short loc_18005B82E
0x18005b7dd  mov     rcx, [rsp+48h+hKey]; hKey
0x18005b7e2  lea     rax, [rsp+48h+cbData]
0x18005b7e7  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18005b7ec  lea     rdx, aDisableendenti; "DisableEndEntityClientCertCheck"
0x18005b7f3  lea     rax, [rsp+48h+Data]
0x18005b7f8  xor     r9d, r9d; lpType
0x18005b7fb  xor     r8d, r8d; lpReserved
0x18005b7fe  mov     [rsp+48h+phkResult], rax; lpData
0x18005b803  call    cs:__imp_RegQueryValueExW
0x18005b809  mov     ebx, eax
0x18005b80b  test    eax, eax
0x18005b80d  jz      short loc_18005B822
0x18005b80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b816  cmp     rcx, rbp
0x18005b819  jz      short loc_18005B835
0x18005b81b  mov     edx, 21h ; '!'
0x18005b820  jmp     short loc_18005B7CC
0x18005b822  xor     eax, eax
0x18005b824  cmp     [rsp+48h+Data], 1
0x18005b829  setz    al
0x18005b82c  mov     [rdi], eax
0x18005b82e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b835  mov     rax, [rsp+48h+hKey]
0x18005b83a  test    rax, rax
0x18005b83d  jz      short loc_18005B858
0x18005b83f  mov     rcx, rax; hKey
0x18005b842  call    cs:__imp_RegCloseKey
0x18005b848  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b84f  mov     [rsp+48h+hKey], 0
0x18005b858  cmp     dword ptr [rdi], 0
0x18005b85b  jz      short loc_18005B869
0x18005b85d  cmp     rcx, rbp
0x18005b860  jz      short loc_18005B882
0x18005b862  mov     edx, 22h ; '"'
0x18005b867  jmp     short loc_18005B873
0x18005b869  cmp     rcx, rbp
0x18005b86c  jz      short loc_18005B882
0x18005b86e  mov     edx, 23h ; '#'
0x18005b873  mov     rcx, [rcx+10h]
0x18005b877  mov     r9d, ebx
0x18005b87a  mov     r8, r14
0x18005b87d  call    WPP_SF_d
0x18005b882  mov     rbx, [rsp+48h+arg_18]
0x18005b887  add     rsp, 30h
0x18005b88b  pop     r14
0x18005b88d  pop     rdi
0x18005b88e  pop     rbp
0x18005b88f  retn
```
