# NatGetInterfaceIndexesFromReg(ulong *,ulong *)

- ea: `0x180030ce8`
- end: `0x180030f5e`
- name: `?NatGetInterfaceIndexesFromReg@@YAJPEAK0@Z`
- size: `630`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030b7c`
- `0x180030f64`
- `0x18003b394`
- `0x180043450`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180030ce8`
- `0x18003eb48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030e9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030d91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030d91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030eef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030eef`

## string_xrefs

- `0x180030d74`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`
- `0x180030dd8`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 __fastcall NatGetInterfaceIndexesFromReg(unsigned int *a1, unsigned int *a2)
{
  PVOID *v4; // rcx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY v7; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+80h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+50h] BYREF
  DWORD Type; // [rsp+98h] [rbp+58h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 )
  {
    v6 = -2147467261;
    if ( v4 == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_DWORD *)v4 + 7) & 0x200) == 0 || *((_BYTE *)v4 + 25) < 2u )
      goto LABEL_34;
    WPP_SF_d(v4[2], 301, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, 2147500035LL);
    goto LABEL_33;
  }
  *a1 = -1;
  *a2 = -1;
  Data = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 1u, &hKey);
  v6 = v5;
  if ( !v5 )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"PublicIndex", 0, &Type, (LPBYTE)&Data, &cbData) )
    {
      v6 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          304,
          (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          (unsigned int)L"PublicIndex",
          Data);
      }
      v7 = hKey;
      *a1 = Data;
      Type = 4;
      cbData = 4;
      v6 = 0;
      if ( RegQueryValueExW(v7, L"PrivateIndex", 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        *a1 = -1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            306,
            (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
            (unsigned int)L"PrivateIndex",
            Data);
        }
        *a2 = Data;
      }
    }
    RegCloseKey(hKey);
    goto LABEL_33;
  }
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
LABEL_33:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      302,
      (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess",
      v6);
    goto LABEL_33;
  }
LABEL_34:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 307, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180030ce8  push    rbp
0x180030cea  push    rbx
0x180030ceb  push    rsi
0x180030cec  push    rdi
0x180030ced  push    r12
0x180030cef  push    r14
0x180030cf1  push    r15
0x180030cf3  mov     rbp, rsp
0x180030cf6  sub     rsp, 40h
0x180030cfa  mov     rsi, rdx
0x180030cfd  mov     rdi, rcx
0x180030d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d07  lea     r15, WPP_GLOBAL_Control
0x180030d0e  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180030d15  mov     r14d, 200h
0x180030d1b  cmp     rcx, r15
0x180030d1e  jz      short loc_180030D44
0x180030d20  test    [rcx+1Ch], r14d
0x180030d24  jz      short loc_180030D44
0x180030d26  cmp     byte ptr [rcx+19h], 6
0x180030d2a  jb      short loc_180030D44
0x180030d2c  mov     rcx, [rcx+10h]
0x180030d30  mov     edx, 12Ch
0x180030d35  mov     r8, r12
0x180030d38  call    WPP_SF_
0x180030d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d44  test    rdi, rdi
0x180030d47  jz      loc_180030EF7
0x180030d4d  test    rsi, rsi
0x180030d50  jz      loc_180030EF7
0x180030d56  lea     rax, [rbp+hKey]
0x180030d5a  mov     dword ptr [rdi], 0FFFFFFFFh
0x180030d60  mov     r9d, 1; samDesired
0x180030d66  mov     [rsp+40h+phkResult], rax; phkResult
0x180030d6b  xor     r8d, r8d; ulOptions
0x180030d6e  mov     dword ptr [rsi], 0FFFFFFFFh
0x180030d74  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180030d7b  mov     [rbp+Data], 0
0x180030d82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030d89  mov     [rbp+hKey], 0
0x180030d91  call    cs:__imp_RegOpenKeyExW
0x180030d97  mov     ebx, eax
0x180030d99  test    eax, eax
0x180030d9b  jz      short loc_180030DF5
0x180030d9d  jle     short loc_180030DA8
0x180030d9f  movzx   ebx, ax
0x180030da2  or      ebx, 80070000h
0x180030da8  test    ebx, ebx
0x180030daa  jns     loc_180030F21
0x180030db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180030db7  cmp     rcx, r15
0x180030dba  jz      loc_180030F4D
0x180030dc0  test    [rcx+1Ch], r14d
0x180030dc4  jz      loc_180030F28
0x180030dca  cmp     byte ptr [rcx+19h], 2
0x180030dce  jb      loc_180030F28
0x180030dd4  mov     rcx, [rcx+10h]
0x180030dd8  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180030ddf  mov     edx, 12Eh
0x180030de4  mov     dword ptr [rsp+40h+phkResult], ebx
0x180030de8  mov     r8, r12
0x180030deb  call    WPP_SF_Sd
0x180030df0  jmp     loc_180030F21
0x180030df5  mov     rcx, [rbp+hKey]; hKey
0x180030df9  lea     rax, [rbp+cbData]
0x180030dfd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180030e02  lea     r9, [rbp+Type]; lpType
0x180030e06  lea     rax, [rbp+Data]
0x180030e0a  mov     ebx, 4
0x180030e0f  xor     r8d, r8d; lpReserved
0x180030e12  mov     [rsp+40h+phkResult], rax; lpData
0x180030e17  lea     rdx, aPublicindex; "PublicIndex"
0x180030e1e  mov     [rbp+Type], ebx
0x180030e21  mov     [rbp+cbData], ebx
0x180030e24  call    cs:__imp_RegQueryValueExW
0x180030e2a  test    eax, eax
0x180030e2c  jz      short loc_180030E35
0x180030e2e  xor     ebx, ebx
0x180030e30  jmp     loc_180030EEB
0x180030e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e3c  cmp     rcx, r15
0x180030e3f  jz      short loc_180030E6C
0x180030e41  test    [rcx+1Ch], r14d
0x180030e45  jz      short loc_180030E6C
0x180030e47  cmp     byte ptr [rcx+19h], 5
0x180030e4b  jb      short loc_180030E6C
0x180030e4d  mov     eax, [rbp+Data]
0x180030e50  lea     r9, aPublicindex; "PublicIndex"
0x180030e57  mov     rcx, [rcx+10h]
0x180030e5b  mov     edx, 130h
0x180030e60  mov     r8, r12
0x180030e63  mov     dword ptr [rsp+40h+phkResult], eax
0x180030e67  call    WPP_SF_Sd
0x180030e6c  mov     eax, [rbp+Data]
0x180030e6f  lea     r9, [rbp+Type]; lpType
0x180030e73  mov     rcx, [rbp+hKey]; hKey
0x180030e77  lea     rdx, aPrivateindex; "PrivateIndex"
0x180030e7e  mov     [rdi], eax
0x180030e80  xor     r8d, r8d; lpReserved
0x180030e83  lea     rax, [rbp+cbData]
0x180030e87  mov     [rbp+Type], ebx
0x180030e8a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180030e8f  lea     rax, [rbp+Data]
0x180030e93  mov     [rsp+40h+phkResult], rax; lpData
0x180030e98  mov     [rbp+cbData], ebx
0x180030e9b  call    cs:__imp_RegQueryValueExW
0x180030ea1  xor     ebx, ebx
0x180030ea3  test    eax, eax
0x180030ea5  jz      short loc_180030EAF
0x180030ea7  mov     dword ptr [rdi], 0FFFFFFFFh
0x180030ead  jmp     short loc_180030EEB
0x180030eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180030eb6  cmp     rcx, r15
0x180030eb9  jz      short loc_180030EE6
0x180030ebb  test    [rcx+1Ch], r14d
0x180030ebf  jz      short loc_180030EE6
0x180030ec1  cmp     byte ptr [rcx+19h], 5
0x180030ec5  jb      short loc_180030EE6
0x180030ec7  mov     eax, [rbp+Data]
0x180030eca  lea     r9, aPrivateindex; "PrivateIndex"
0x180030ed1  mov     rcx, [rcx+10h]
0x180030ed5  mov     edx, 132h
0x180030eda  mov     r8, r12
0x180030edd  mov     dword ptr [rsp+40h+phkResult], eax
0x180030ee1  call    WPP_SF_Sd
0x180030ee6  mov     eax, [rbp+Data]
0x180030ee9  mov     [rsi], eax
0x180030eeb  mov     rcx, [rbp+hKey]; hKey
0x180030eef  call    cs:__imp_RegCloseKey
0x180030ef5  jmp     short loc_180030F21
0x180030ef7  mov     ebx, 80004003h
0x180030efc  cmp     rcx, r15
0x180030eff  jz      short loc_180030F4D
0x180030f01  test    [rcx+1Ch], r14d
0x180030f05  jz      short loc_180030F28
0x180030f07  cmp     byte ptr [rcx+19h], 2
0x180030f0b  jb      short loc_180030F28
0x180030f0d  mov     rcx, [rcx+10h]
0x180030f11  mov     edx, 12Dh
0x180030f16  mov     r9d, ebx
0x180030f19  mov     r8, r12
0x180030f1c  call    WPP_SF_d
0x180030f21  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f28  cmp     rcx, r15
0x180030f2b  jz      short loc_180030F4D
0x180030f2d  test    [rcx+1Ch], r14d
0x180030f31  jz      short loc_180030F4D
0x180030f33  cmp     byte ptr [rcx+19h], 6
0x180030f37  jb      short loc_180030F4D
0x180030f39  mov     rcx, [rcx+10h]
0x180030f3d  mov     edx, 133h
0x180030f42  mov     r9d, ebx
0x180030f45  mov     r8, r12
0x180030f48  call    WPP_SF_d
0x180030f4d  mov     eax, ebx
0x180030f4f  add     rsp, 40h
0x180030f53  pop     r15
0x180030f55  pop     r14
0x180030f57  pop     r12
0x180030f59  pop     rdi
0x180030f5a  pop     rsi
0x180030f5b  pop     rbx
0x180030f5c  pop     rbp
0x180030f5d  retn
```
