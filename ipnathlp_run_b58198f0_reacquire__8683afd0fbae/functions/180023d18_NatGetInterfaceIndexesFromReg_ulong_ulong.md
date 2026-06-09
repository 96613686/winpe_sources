# NatGetInterfaceIndexesFromReg(ulong *,ulong *)

- ea: `0x180023d18`
- end: `0x180023fa7`
- name: `?NatGetInterfaceIndexesFromReg@@YAJPEAK0@Z`
- size: `655`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023bac`
- `0x180023fb0`
- `0x18003e574`
- `0x180046db0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180023d18`
- `0x180041d80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023e5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023ed7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023e5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023ed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023dc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023dc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f31`

## string_xrefs

- `0x180023da4`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`
- `0x180023e0e`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

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
0x180023d18  push    rbp
0x180023d1a  push    rbx
0x180023d1b  push    rsi
0x180023d1c  push    rdi
0x180023d1d  push    r12
0x180023d1f  push    r14
0x180023d21  push    r15
0x180023d23  mov     rbp, rsp
0x180023d26  sub     rsp, 40h
0x180023d2a  mov     rsi, rdx
0x180023d2d  mov     rdi, rcx
0x180023d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d37  lea     r15, WPP_GLOBAL_Control
0x180023d3e  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180023d45  mov     r14d, 200h
0x180023d4b  cmp     rcx, r15
0x180023d4e  jz      short loc_180023D74
0x180023d50  test    [rcx+1Ch], r14d
0x180023d54  jz      short loc_180023D74
0x180023d56  cmp     byte ptr [rcx+19h], 6
0x180023d5a  jb      short loc_180023D74
0x180023d5c  mov     rcx, [rcx+10h]
0x180023d60  mov     edx, 12Ch
0x180023d65  mov     r8, r12
0x180023d68  call    WPP_SF_
0x180023d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d74  test    rdi, rdi
0x180023d77  jz      loc_180023F3F
0x180023d7d  test    rsi, rsi
0x180023d80  jz      loc_180023F3F
0x180023d86  lea     rax, [rbp+hKey]
0x180023d8a  mov     dword ptr [rdi], 0FFFFFFFFh
0x180023d90  mov     r9d, 1; samDesired
0x180023d96  mov     [rsp+40h+phkResult], rax; phkResult
0x180023d9b  xor     r8d, r8d; ulOptions
0x180023d9e  mov     dword ptr [rsi], 0FFFFFFFFh
0x180023da4  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023dab  mov     [rbp+Data], 0
0x180023db2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023db9  mov     [rbp+hKey], 0
0x180023dc1  call    cs:__imp_RegOpenKeyExW
0x180023dc8  nop     dword ptr [rax+rax+00h]
0x180023dcd  mov     ebx, eax
0x180023dcf  test    eax, eax
0x180023dd1  jz      short loc_180023E2B
0x180023dd3  jle     short loc_180023DDE
0x180023dd5  movzx   ebx, ax
0x180023dd8  or      ebx, 80070000h
0x180023dde  test    ebx, ebx
0x180023de0  jns     loc_180023F69
0x180023de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ded  cmp     rcx, r15
0x180023df0  jz      loc_180023F95
0x180023df6  test    [rcx+1Ch], r14d
0x180023dfa  jz      loc_180023F70
0x180023e00  cmp     byte ptr [rcx+19h], 2
0x180023e04  jb      loc_180023F70
0x180023e0a  mov     rcx, [rcx+10h]
0x180023e0e  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023e15  mov     edx, 12Eh
0x180023e1a  mov     dword ptr [rsp+40h+phkResult], ebx
0x180023e1e  mov     r8, r12
0x180023e21  call    WPP_SF_Sd
0x180023e26  jmp     loc_180023F69
0x180023e2b  mov     rcx, [rbp+hKey]; hKey
0x180023e2f  lea     rax, [rbp+cbData]
0x180023e33  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023e38  lea     r9, [rbp+Type]; lpType
0x180023e3c  lea     rax, [rbp+Data]
0x180023e40  mov     ebx, 4
0x180023e45  xor     r8d, r8d; lpReserved
0x180023e48  mov     [rsp+40h+phkResult], rax; lpData
0x180023e4d  lea     rdx, aPublicindex; "PublicIndex"
0x180023e54  mov     [rbp+Type], ebx
0x180023e57  mov     [rbp+cbData], ebx
0x180023e5a  call    cs:__imp_RegQueryValueExW
0x180023e61  nop     dword ptr [rax+rax+00h]
0x180023e66  test    eax, eax
0x180023e68  jz      short loc_180023E71
0x180023e6a  xor     ebx, ebx
0x180023e6c  jmp     loc_180023F2D
0x180023e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e78  cmp     rcx, r15
0x180023e7b  jz      short loc_180023EA8
0x180023e7d  test    [rcx+1Ch], r14d
0x180023e81  jz      short loc_180023EA8
0x180023e83  cmp     byte ptr [rcx+19h], 5
0x180023e87  jb      short loc_180023EA8
0x180023e89  mov     eax, [rbp+Data]
0x180023e8c  lea     r9, aPublicindex; "PublicIndex"
0x180023e93  mov     rcx, [rcx+10h]
0x180023e97  mov     edx, 130h
0x180023e9c  mov     r8, r12
0x180023e9f  mov     dword ptr [rsp+40h+phkResult], eax
0x180023ea3  call    WPP_SF_Sd
0x180023ea8  mov     eax, [rbp+Data]
0x180023eab  lea     r9, [rbp+Type]; lpType
0x180023eaf  mov     rcx, [rbp+hKey]; hKey
0x180023eb3  lea     rdx, aPrivateindex; "PrivateIndex"
0x180023eba  mov     [rdi], eax
0x180023ebc  xor     r8d, r8d; lpReserved
0x180023ebf  lea     rax, [rbp+cbData]
0x180023ec3  mov     [rbp+Type], ebx
0x180023ec6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023ecb  lea     rax, [rbp+Data]
0x180023ecf  mov     [rsp+40h+phkResult], rax; lpData
0x180023ed4  mov     [rbp+cbData], ebx
0x180023ed7  call    cs:__imp_RegQueryValueExW
0x180023ede  nop     dword ptr [rax+rax+00h]
0x180023ee3  xor     ebx, ebx
0x180023ee5  test    eax, eax
0x180023ee7  jz      short loc_180023EF1
0x180023ee9  mov     dword ptr [rdi], 0FFFFFFFFh
0x180023eef  jmp     short loc_180023F2D
0x180023ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ef8  cmp     rcx, r15
0x180023efb  jz      short loc_180023F28
0x180023efd  test    [rcx+1Ch], r14d
0x180023f01  jz      short loc_180023F28
0x180023f03  cmp     byte ptr [rcx+19h], 5
0x180023f07  jb      short loc_180023F28
0x180023f09  mov     eax, [rbp+Data]
0x180023f0c  lea     r9, aPrivateindex; "PrivateIndex"
0x180023f13  mov     rcx, [rcx+10h]
0x180023f17  mov     edx, 132h
0x180023f1c  mov     r8, r12
0x180023f1f  mov     dword ptr [rsp+40h+phkResult], eax
0x180023f23  call    WPP_SF_Sd
0x180023f28  mov     eax, [rbp+Data]
0x180023f2b  mov     [rsi], eax
0x180023f2d  mov     rcx, [rbp+hKey]; hKey
0x180023f31  call    cs:__imp_RegCloseKey
0x180023f38  nop     dword ptr [rax+rax+00h]
0x180023f3d  jmp     short loc_180023F69
0x180023f3f  mov     ebx, 80004003h
0x180023f44  cmp     rcx, r15
0x180023f47  jz      short loc_180023F95
0x180023f49  test    [rcx+1Ch], r14d
0x180023f4d  jz      short loc_180023F70
0x180023f4f  cmp     byte ptr [rcx+19h], 2
0x180023f53  jb      short loc_180023F70
0x180023f55  mov     rcx, [rcx+10h]
0x180023f59  mov     edx, 12Dh
0x180023f5e  mov     r9d, ebx
0x180023f61  mov     r8, r12
0x180023f64  call    WPP_SF_d
0x180023f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f70  cmp     rcx, r15
0x180023f73  jz      short loc_180023F95
0x180023f75  test    [rcx+1Ch], r14d
0x180023f79  jz      short loc_180023F95
0x180023f7b  cmp     byte ptr [rcx+19h], 6
0x180023f7f  jb      short loc_180023F95
0x180023f81  mov     rcx, [rcx+10h]
0x180023f85  mov     edx, 133h
0x180023f8a  mov     r9d, ebx
0x180023f8d  mov     r8, r12
0x180023f90  call    WPP_SF_d
0x180023f95  mov     eax, ebx
0x180023f97  add     rsp, 40h
0x180023f9b  pop     r15
0x180023f9d  pop     r14
0x180023f9f  pop     r12
0x180023fa1  pop     rdi
0x180023fa2  pop     rsi
0x180023fa3  pop     rbx
0x180023fa4  pop     rbp
0x180023fa5  retn
```
