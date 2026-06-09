# UseBestSourceIpEnabled

- ea: `0x1800a72ec`
- end: `0x1800a7493`
- name: `UseBestSourceIpEnabled`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800a64d4`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007efdc`
- `0x1800a72ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a735f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a735f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7428`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a739e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a739e`

## string_xrefs

- `0x1800a734f`: `System\CurrentControlSet\Services\rasman\IKEv2`

## pseudocode

```c
__int64 UseBestSourceIpEnabled()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 v2; // r9
  unsigned int v3; // eax
  _QWORD *v4; // rcx
  unsigned int Data; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
  }
  hKey = 0;
  v0 = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 0x20019u, &hKey);
  if ( !v1 )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"UseBestSourceIp", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v3 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v3);
    }
    else if ( Type == 4 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, Data);
        v4 = WPP_GLOBAL_Control;
      }
      LOBYTE(v0) = Data == 1;
LABEL_18:
      if ( hKey )
      {
        RegCloseKey(hKey);
LABEL_24:
        v4 = WPP_GLOBAL_Control;
        goto LABEL_25;
      }
      goto LABEL_25;
    }
    v4 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v0;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v1);
    goto LABEL_24;
  }
LABEL_25:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    LOBYTE(v2) = v0;
    WPP_SF_c(v4[2], 316, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v2);
  }
  return v0;
}

```

## disassembly

```asm
0x1800a72ec  push    rbp
0x1800a72ee  push    rbx
0x1800a72ef  push    rsi
0x1800a72f0  push    rdi
0x1800a72f1  push    r15
0x1800a72f3  mov     rbp, rsp
0x1800a72f6  sub     rsp, 30h
0x1800a72fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7301  lea     rsi, WPP_GLOBAL_Control
0x1800a7308  lea     r15, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800a730f  mov     edi, 800h
0x1800a7314  cmp     rcx, rsi
0x1800a7317  jz      short loc_1800A7335
0x1800a7319  test    [rcx+1Ch], edi
0x1800a731c  jz      short loc_1800A7335
0x1800a731e  cmp     byte ptr [rcx+19h], 6
0x1800a7322  jb      short loc_1800A7335
0x1800a7324  mov     rcx, [rcx+10h]
0x1800a7328  mov     edx, 138h
0x1800a732d  mov     r8, r15
0x1800a7330  call    WPP_SF_
0x1800a7335  lea     rax, [rbp+hKey]
0x1800a7339  mov     [rbp+hKey], 0
0x1800a7341  mov     r9d, 20019h; samDesired
0x1800a7347  mov     [rsp+30h+phkResult], rax; phkResult
0x1800a734c  xor     r8d, r8d; ulOptions
0x1800a734f  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\ra"...
0x1800a7356  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a735d  xor     ebx, ebx
0x1800a735f  call    cs:__imp_RegOpenKeyExW
0x1800a7365  test    eax, eax
0x1800a7367  jnz     loc_1800A7430
0x1800a736d  mov     rcx, [rbp+hKey]; hKey
0x1800a7371  lea     rax, [rbp+cbData]
0x1800a7375  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800a737a  lea     r9, [rbp+Type]; lpType
0x1800a737e  lea     rax, [rbp+Data]
0x1800a7382  mov     [rbp+Type], ebx
0x1800a7385  xor     r8d, r8d; lpReserved
0x1800a7388  mov     [rsp+30h+phkResult], rax; lpData
0x1800a738d  lea     rdx, aUsebestsourcei; "UseBestSourceIp"
0x1800a7394  mov     [rbp+Data], ebx
0x1800a7397  mov     [rbp+cbData], 4
0x1800a739e  call    cs:__imp_RegQueryValueExW
0x1800a73a4  test    eax, eax
0x1800a73a6  jnz     short loc_1800A73EA
0x1800a73a8  cmp     [rbp+Type], 4
0x1800a73ac  jnz     short loc_1800A7415
0x1800a73ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a73b5  cmp     rcx, rsi
0x1800a73b8  jz      short loc_1800A73E1
0x1800a73ba  test    [rcx+1Ch], edi
0x1800a73bd  jz      short loc_1800A73E1
0x1800a73bf  cmp     byte ptr [rcx+19h], 5
0x1800a73c3  jb      short loc_1800A73E1
0x1800a73c5  mov     r9d, [rbp+Data]
0x1800a73c9  mov     edx, 139h
0x1800a73ce  mov     rcx, [rcx+10h]
0x1800a73d2  mov     r8, r15
0x1800a73d5  call    WPP_SF_d
0x1800a73da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a73e1  cmp     [rbp+Data], 1
0x1800a73e5  setz    bl
0x1800a73e8  jmp     short loc_1800A741C
0x1800a73ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a73f1  cmp     rcx, rsi
0x1800a73f4  jz      short loc_1800A741C
0x1800a73f6  test    [rcx+1Ch], edi
0x1800a73f9  jz      short loc_1800A741C
0x1800a73fb  cmp     byte ptr [rcx+19h], 2
0x1800a73ff  jb      short loc_1800A741C
0x1800a7401  mov     rcx, [rcx+10h]
0x1800a7405  mov     edx, 13Ah
0x1800a740a  mov     r9d, eax
0x1800a740d  mov     r8, r15
0x1800a7410  call    WPP_SF_d
0x1800a7415  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a741c  mov     rax, [rbp+hKey]
0x1800a7420  test    rax, rax
0x1800a7423  jz      short loc_1800A7462
0x1800a7425  mov     rcx, rax; hKey
0x1800a7428  call    cs:__imp_RegCloseKey
0x1800a742e  jmp     short loc_1800A745B
0x1800a7430  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7437  cmp     rcx, rsi
0x1800a743a  jz      short loc_1800A7486
0x1800a743c  test    [rcx+1Ch], edi
0x1800a743f  jz      short loc_1800A7462
0x1800a7441  cmp     byte ptr [rcx+19h], 2
0x1800a7445  jb      short loc_1800A7462
0x1800a7447  mov     rcx, [rcx+10h]
0x1800a744b  mov     edx, 13Bh
0x1800a7450  mov     r9d, eax
0x1800a7453  mov     r8, r15
0x1800a7456  call    WPP_SF_d
0x1800a745b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7462  cmp     rcx, rsi
0x1800a7465  jz      short loc_1800A7486
0x1800a7467  test    [rcx+1Ch], edi
0x1800a746a  jz      short loc_1800A7486
0x1800a746c  cmp     byte ptr [rcx+19h], 6
0x1800a7470  jb      short loc_1800A7486
0x1800a7472  mov     rcx, [rcx+10h]
0x1800a7476  mov     r9b, bl
0x1800a7479  mov     edx, 13Ch
0x1800a747e  mov     r8, r15
0x1800a7481  call    WPP_SF_c
0x1800a7486  mov     eax, ebx
0x1800a7488  add     rsp, 30h
0x1800a748c  pop     r15
0x1800a748e  pop     rdi
0x1800a748f  pop     rsi
0x1800a7490  pop     rbx
0x1800a7491  pop     rbp
0x1800a7492  retn
```
