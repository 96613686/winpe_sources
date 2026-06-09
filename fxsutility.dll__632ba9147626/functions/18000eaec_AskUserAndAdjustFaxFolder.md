# AskUserAndAdjustFaxFolder

- ea: `0x18000eaec`
- end: `0x18000eda8`
- name: `AskUserAndAdjustFaxFolder`
- size: `700`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f1dc`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180006ce8`
- `0x18000e8a8`
- `0x18000eaec`
- `0x18000edb0`
- `0x18000ef60`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x18000ec1c`
- `SHLWAPI!StrChrW` at `0x18000ec1c`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000ec31`
- `SHLWAPI!PathIsNetworkPathW` at `0x18000ec31`
- `SHLWAPI!PathIsRelativeW` at `0x18000eb77`
- `SHLWAPI!PathIsRelativeW` at `0x18000eb77`
- `KERNEL32!LocalFree` at `0x18000ed68`
- `KERNEL32!LocalFree` at `0x18000ed68`
- `KERNEL32!GetLastError` at `0x18000ec83`
- `KERNEL32!GetLastError` at `0x18000ec83`
- `SHELL32!SHCreateDirectoryExW` at `0x18000ecf3`
- `SHELL32!SHCreateDirectoryExW` at `0x18000ecf3`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ec79`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ec79`

## pseudocode

```c
__int64 __fastcall AskUserAndAdjustFaxFolder(HWND hWnd, void *a2, WCHAR *a3, unsigned int a4)
{
  unsigned int v7; // ebx
  unsigned __int16 *v9; // r8
  unsigned int v10; // edx
  HWND v11; // rcx
  BOOL IsNetworkPathW; // eax
  DWORD LastError; // eax
  unsigned int v14; // eax
  SECURITY_ATTRIBUTES psa; // [rsp+30h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+10h] BYREF

  SecurityDescriptor = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids);
  }
  v7 = 161;
  if ( a4 == 53 || a4 == 161 || a4 == 267 || a4 == 21 || !a3 || PathIsRelativeW(a3) || a4 == 111 || a4 == 7007 )
  {
    FaxMsgBox(hWnd, 0, 15000);
    return v7;
  }
  if ( a4 == 7008 )
  {
    if ( (unsigned int)FaxMsgBox(hWnd, 0, 15000) == 6 )
      return (unsigned int)SetDirPermsForFaxService(a3);
    return v7;
  }
  if ( a4 - 2 > 1 )
    return a4;
  if ( !(unsigned int)IsLocalMachineNameW() )
  {
    v10 = 15004;
LABEL_20:
    v11 = hWnd;
LABEL_21:
    FaxMessageBoxWithHelp(v11, v10, v9, 0x10u);
    return v7;
  }
  if ( StrChrW(a3, 0x25u) )
  {
    v10 = 15005;
    goto LABEL_20;
  }
  IsNetworkPathW = PathIsNetworkPathW(a3);
  v11 = hWnd;
  if ( IsNetworkPathW )
  {
    v10 = 15006;
    goto LABEL_21;
  }
  if ( (unsigned int)FaxMessageBoxWithHelp(hWnd, 0x3A9Fu, v9, 0x34u) == 6 )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;NS)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids, LastError);
      }
      return v7;
    }
    psa.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&psa.nLength = 24;
    *(_QWORD *)&psa.bInheritHandle = 0;
    v14 = SHCreateDirectoryExW(hWnd, a3, &psa);
    a4 = v14;
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids, v14);
      }
      if ( a4 == 161 )
      {
        FaxMsgBox(hWnd, 0, 15000);
      }
      else if ( a4 == 1223 )
      {
        a4 = 161;
      }
    }
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return a4;
  }
  return v7;
}

```

## disassembly

```asm
0x18000eaec  mov     [rsp+arg_0], rbx
0x18000eaf1  mov     [rsp+arg_10], rbp
0x18000eaf6  mov     [rsp+SecurityDescriptor], rdx
0x18000eafb  push    rsi
0x18000eafc  push    rdi
0x18000eafd  push    r15
0x18000eaff  sub     rsp, 50h
0x18000eb03  mov     edi, r9d
0x18000eb06  mov     rbp, r8
0x18000eb09  mov     rsi, rcx
0x18000eb0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb13  lea     r15, WPP_GLOBAL_Control
0x18000eb1a  cmp     rcx, r15
0x18000eb1d  jz      short loc_18000EB40
0x18000eb1f  test    byte ptr [rcx+1Ch], 2
0x18000eb23  jz      short loc_18000EB40
0x18000eb25  cmp     byte ptr [rcx+19h], 5
0x18000eb29  jb      short loc_18000EB40
0x18000eb2b  mov     rcx, [rcx+10h]
0x18000eb2f  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x18000eb36  mov     edx, 13h
0x18000eb3b  call    WPP_SF_
0x18000eb40  mov     ebx, 0A1h
0x18000eb45  cmp     edi, 35h ; '5'
0x18000eb48  jz      loc_18000ED73
0x18000eb4e  cmp     edi, ebx
0x18000eb50  jz      loc_18000ED73
0x18000eb56  cmp     edi, 10Bh
0x18000eb5c  jz      loc_18000ED73
0x18000eb62  cmp     edi, 15h
0x18000eb65  jz      loc_18000ED73
0x18000eb6b  test    rbp, rbp
0x18000eb6e  jz      loc_18000ED73
0x18000eb74  mov     rcx, rbp; pszPath
0x18000eb77  call    cs:__imp_PathIsRelativeW
0x18000eb7d  test    eax, eax
0x18000eb7f  jnz     loc_18000ED73
0x18000eb85  cmp     edi, 6Fh ; 'o'
0x18000eb88  jnz     short loc_18000EB95
0x18000eb8a  mov     r9d, 3AA0h
0x18000eb90  jmp     loc_18000ED79
0x18000eb95  cmp     edi, 1B5Fh
0x18000eb9b  jnz     short loc_18000EBA8
0x18000eb9d  mov     r9d, 3A9Ah
0x18000eba3  jmp     loc_18000ED79
0x18000eba8  cmp     edi, 1B60h
0x18000ebae  jnz     short loc_18000EBE4
0x18000ebb0  mov     r9d, 3AA1h
0x18000ebb6  mov     [rsp+68h+var_48], 34h ; '4'
0x18000ebbe  xor     edx, edx
0x18000ebc0  mov     rcx, rsi
0x18000ebc3  lea     r8d, [r9-9]
0x18000ebc7  call    FaxMsgBox
0x18000ebcc  cmp     eax, 6
0x18000ebcf  jnz     loc_18000ED91
0x18000ebd5  mov     rcx, rbp; pObjectName
0x18000ebd8  call    SetDirPermsForFaxService
0x18000ebdd  mov     ebx, eax
0x18000ebdf  jmp     loc_18000ED91
0x18000ebe4  lea     eax, [rdi-2]
0x18000ebe7  cmp     eax, 1
0x18000ebea  jbe     short loc_18000EBF3
0x18000ebec  mov     eax, edi
0x18000ebee  jmp     loc_18000ED93
0x18000ebf3  call    IsLocalMachineNameW
0x18000ebf8  test    eax, eax
0x18000ebfa  jnz     short loc_18000EC14
0x18000ebfc  mov     edx, 3A9Ch; unsigned int
0x18000ec01  mov     rcx, rsi; hWnd
0x18000ec04  mov     r9d, 10h; unsigned int
0x18000ec0a  call    ?FaxMessageBoxWithHelp@@YAHPEAUHWND__@@KPEAGI@Z; FaxMessageBoxWithHelp(HWND__ *,ulong,ushort *,uint)
0x18000ec0f  jmp     loc_18000ED91
0x18000ec14  mov     edx, 25h ; '%'; wMatch
0x18000ec19  mov     rcx, rbp; pszStart
0x18000ec1c  call    cs:__imp_StrChrW
0x18000ec22  test    rax, rax
0x18000ec25  jz      short loc_18000EC2E
0x18000ec27  mov     edx, 3A9Dh
0x18000ec2c  jmp     short loc_18000EC01
0x18000ec2e  mov     rcx, rbp; pszPath
0x18000ec31  call    cs:__imp_PathIsNetworkPathW
0x18000ec37  mov     rcx, rsi; hWnd
0x18000ec3a  test    eax, eax
0x18000ec3c  jz      short loc_18000EC45
0x18000ec3e  mov     edx, 3A9Eh
0x18000ec43  jmp     short loc_18000EC04
0x18000ec45  mov     edx, 3A9Fh; unsigned int
0x18000ec4a  mov     r9d, 34h ; '4'; unsigned int
0x18000ec50  call    ?FaxMessageBoxWithHelp@@YAHPEAUHWND__@@KPEAGI@Z; FaxMessageBoxWithHelp(HWND__ *,ulong,ushort *,uint)
0x18000ec55  cmp     eax, 6
0x18000ec58  jnz     loc_18000ED91
0x18000ec5e  xor     r9d, r9d; SecurityDescriptorSize
0x18000ec61  mov     [rsp+68h+SecurityDescriptor], 0
0x18000ec6a  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x18000ec6f  lea     edx, [rax-5]; StringSDRevision
0x18000ec72  lea     rcx, StringSecurityDescriptor; "D:PAI(A;OICI;FA;;;BA)(A;OICI;FA;;;NS)"
0x18000ec79  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000ec7f  test    eax, eax
0x18000ec81  jnz     short loc_18000ECCC
0x18000ec83  call    cs:__imp_GetLastError
0x18000ec89  mov     ebx, eax
0x18000ec8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec92  cmp     rcx, r15
0x18000ec95  jz      loc_18000ED91
0x18000ec9b  test    byte ptr [rcx+1Ch], 2
0x18000ec9f  jz      loc_18000ED91
0x18000eca5  cmp     byte ptr [rcx+19h], 2
0x18000eca9  jb      loc_18000ED91
0x18000ecaf  mov     rcx, [rcx+10h]
0x18000ecb3  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x18000ecba  mov     edx, 14h
0x18000ecbf  mov     r9d, eax
0x18000ecc2  call    WPP_SF_d
0x18000ecc7  jmp     loc_18000ED91
0x18000eccc  mov     rax, [rsp+68h+SecurityDescriptor]
0x18000ecd1  lea     r8, [rsp+68h+psa]; psa
0x18000ecd6  mov     rdx, rbp; pszPath
0x18000ecd9  mov     [rsp+68h+psa.lpSecurityDescriptor], rax
0x18000ecde  mov     rcx, rsi; hwnd
0x18000ece1  mov     qword ptr [rsp+68h+psa.nLength], 18h
0x18000ecea  mov     qword ptr [rsp+68h+psa.bInheritHandle], 0
0x18000ecf3  call    cs:__imp_SHCreateDirectoryExW
0x18000ecf9  mov     edi, eax
0x18000ecfb  test    eax, eax
0x18000ecfd  jz      short loc_18000ED5A
0x18000ecff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed06  cmp     rcx, r15
0x18000ed09  jz      short loc_18000ED2F
0x18000ed0b  test    byte ptr [rcx+1Ch], 2
0x18000ed0f  jz      short loc_18000ED2F
0x18000ed11  cmp     byte ptr [rcx+19h], 2
0x18000ed15  jb      short loc_18000ED2F
0x18000ed17  mov     rcx, [rcx+10h]
0x18000ed1b  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x18000ed22  mov     edx, 15h
0x18000ed27  mov     r9d, eax
0x18000ed2a  call    WPP_SF_d
0x18000ed2f  cmp     edi, ebx
0x18000ed31  jnz     short loc_18000ED51
0x18000ed33  mov     r9d, 3A99h
0x18000ed39  mov     [rsp+68h+var_48], 10h
0x18000ed41  xor     edx, edx
0x18000ed43  mov     rcx, rsi
0x18000ed46  lea     r8d, [r9-1]
0x18000ed4a  call    FaxMsgBox
0x18000ed4f  jmp     short loc_18000ED5A
0x18000ed51  cmp     edi, 4C7h
0x18000ed57  cmovz   edi, ebx
0x18000ed5a  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x18000ed5f  test    rcx, rcx
0x18000ed62  jz      loc_18000EBEC
0x18000ed68  call    cs:__imp_LocalFree
0x18000ed6e  jmp     loc_18000EBEC
0x18000ed73  mov     r9d, 3A99h
0x18000ed79  mov     r8d, 3A98h
0x18000ed7f  mov     [rsp+68h+var_48], 10h
0x18000ed87  xor     edx, edx
0x18000ed89  mov     rcx, rsi
0x18000ed8c  call    FaxMsgBox
0x18000ed91  mov     eax, ebx
0x18000ed93  lea     r11, [rsp+68h+var_18]
0x18000ed98  mov     rbx, [r11+20h]
0x18000ed9c  mov     rbp, [r11+30h]
0x18000eda0  mov     rsp, r11
0x18000eda3  pop     r15
0x18000eda5  pop     rdi
0x18000eda6  pop     rsi
0x18000eda7  retn
```
