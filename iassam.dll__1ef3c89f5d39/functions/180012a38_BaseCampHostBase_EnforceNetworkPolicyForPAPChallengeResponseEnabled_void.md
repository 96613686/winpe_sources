# BaseCampHostBase::EnforceNetworkPolicyForPAPChallengeResponseEnabled(void)

- ea: `0x180012a38`
- end: `0x180012c6d`
- name: `?EnforceNetworkPolicyForPAPChallengeResponseEnabled@BaseCampHostBase@@IEAA_NXZ`
- size: `565`
- prototype: `bool __fastcall(BaseCampHostBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180012c74`

## callees

- `0x18000e754`
- `0x180012a38`
- `0x18001426c`
- `0x1800254a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180012bba`
- `ADVAPI32!RegCloseKey` at `0x180012bba`
- `ADVAPI32!RegOpenKeyW` at `0x180012ac3`
- `ADVAPI32!RegOpenKeyW` at `0x180012ac3`
- `ADVAPI32!RegQueryValueExW` at `0x180012ba9`
- `ADVAPI32!RegQueryValueExW` at `0x180012ba9`

## string_xrefs

- `0x180012ab2`: `System\CurrentControlSet\Services\AuthSrv\Parameters`
- `0x180012aff`: `%S doesn't exist; no extensions loaded.`
- `0x180012b55`: `RegOpenKeyW for %S failed with error %ld.`
- `0x180012a85`: `Looking for Registry value for key %S`
- `0x180012bf7`: `%S registry value is not of type REG_DWORD or has incorrect value.`

## pseudocode

```c
bool __fastcall BaseCampHostBase::EnforceNetworkPolicyForPAPChallengeResponseEnabled(BaseCampHostBase *this)
{
  int v1; // r9d
  LSTATUS v2; // eax
  LSTATUS v3; // ebx
  int v4; // r9d
  int v5; // r9d
  LSTATUS v6; // ebx
  int v8; // r9d
  int v9; // r9d
  BaseCampHostBase *Type; // [rsp+70h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+40h] BYREF
  int Data; // [rsp+80h] [rbp+48h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+50h] BYREF

  Type = this;
  phkResult = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Looking for Registry value for key %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
      v1,
      (__int64)L"EnforceNetworkPolicyForPAPBasedChallengeResponse");
  }
  v2 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\AuthSrv\\Parameters", &phkResult);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("%S doesn't exist; no extensions loaded.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v3 + 16,
          (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
          v4,
          (__int64)L"System\\CurrentControlSet\\Services\\AuthSrv\\Parameters");
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("RegOpenKeyW for %S failed with error %ld.");
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
        v5,
        (__int64)L"System\\CurrentControlSet\\Services\\AuthSrv\\Parameters",
        v3);
    }
  }
  else
  {
    LODWORD(Type) = 0;
    Data = 0;
    cbData = 4;
    v6 = RegQueryValueExW(
           phkResult,
           L"EnforceNetworkPolicyForPAPBasedChallengeResponse",
           0,
           (LPDWORD)&Type,
           (LPBYTE)&Data,
           &cbData);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("RegQueryValueExW for %S failed with error %ld.");
        WPP_SF_sSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
          v9,
          (__int64)L"EnforceNetworkPolicyForPAPBasedChallengeResponse",
          v6);
      }
    }
    else
    {
      if ( (_DWORD)Type == 4 && cbData == 4 )
        return Data == 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("%S registry value is not of type REG_DWORD or has incorrect value.");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)&WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids,
          v8,
          (__int64)L"EnforceNetworkPolicyForPAPBasedChallengeResponse");
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012a38  mov     [rsp-30h+Type], rcx
0x180012a3d  push    rbp
0x180012a3e  push    rbx
0x180012a3f  push    rsi
0x180012a40  push    r12
0x180012a42  push    r13
0x180012a44  push    r14
0x180012a46  mov     rbp, rsp
0x180012a49  sub     rsp, 38h
0x180012a4d  mov     [rbp+phkResult], 0
0x180012a55  lea     rsi, WPP_GLOBAL_Control
0x180012a5c  lea     r14, aEnforcenetwork; "EnforceNetworkPolicyForPAPBasedChalleng"...
0x180012a63  lea     r13, WPP_45e78cb6f3e23d8d6a39f2ecf0e7c99a_Traceguids
0x180012a6a  mov     rax, cs:WPP_GLOBAL_Control
0x180012a71  cmp     rax, rsi
0x180012a74  jz      short loc_180012AAE
0x180012a76  cmp     byte ptr [rax+19h], 4
0x180012a7a  jb      short loc_180012AAE
0x180012a7c  test    byte ptr [rax+1Ch], 4
0x180012a80  jz      short loc_180012AAE
0x180012a82  mov     rdx, r14
0x180012a85  lea     rcx, aLookingForRegi; "Looking for Registry value for key %S"
0x180012a8c  call    WppDbgPrint
0x180012a91  mov     edx, 11h
0x180012a96  mov     [rsp+38h+lpData], r14
0x180012a9b  mov     r8, r13
0x180012a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012aa5  mov     rcx, [rcx+10h]
0x180012aa9  call    WPP_SF_sS
0x180012aae  lea     r8, [rbp+phkResult]; phkResult
0x180012ab2  lea     r12, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Au"...
0x180012ab9  mov     rdx, r12; lpSubKey
0x180012abc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012ac3  call    cs:__imp_RegOpenKeyW
0x180012ac9  mov     ebx, eax
0x180012acb  test    eax, eax
0x180012acd  jz      loc_180012B74
0x180012ad3  cmp     eax, 2
0x180012ad6  jnz     short loc_180012B2B
0x180012ad8  mov     rax, cs:WPP_GLOBAL_Control
0x180012adf  cmp     rax, rsi
0x180012ae2  jz      loc_180012C5D
0x180012ae8  cmp     byte ptr [rax+19h], 4
0x180012aec  jb      loc_180012C5D
0x180012af2  test    byte ptr [rax+1Ch], 4
0x180012af6  jz      loc_180012C5D
0x180012afc  mov     rdx, r12
0x180012aff  lea     rcx, aSDoesnTExistNo; "%S doesn't exist; no extensions loaded."
0x180012b06  call    WppDbgPrint
0x180012b0b  lea     edx, [rbx+10h]
0x180012b0e  mov     [rsp+38h+lpData], r12
0x180012b13  mov     r8, r13
0x180012b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b1d  mov     rcx, [rcx+10h]
0x180012b21  call    WPP_SF_sS
0x180012b26  jmp     loc_180012C5D
0x180012b2b  mov     rax, cs:WPP_GLOBAL_Control
0x180012b32  cmp     rax, rsi
0x180012b35  jz      loc_180012C5D
0x180012b3b  cmp     byte ptr [rax+19h], 2
0x180012b3f  jb      loc_180012C5D
0x180012b45  test    byte ptr [rax+1Ch], 4
0x180012b49  jz      loc_180012C5D
0x180012b4f  mov     r8d, ebx
0x180012b52  mov     rdx, r12
0x180012b55  lea     rcx, aRegopenkeywFor; "RegOpenKeyW for %S failed with error %l"...
0x180012b5c  call    WppDbgPrint
0x180012b61  mov     edx, 13h
0x180012b66  mov     dword ptr [rsp+38h+lpcbData], ebx
0x180012b6a  mov     [rsp+38h+lpData], r12
0x180012b6f  jmp     loc_180012C4A
0x180012b74  mov     dword ptr [rbp+Type], 0
0x180012b7b  mov     [rbp+Data], 0
0x180012b82  mov     [rbp+cbData], 4
0x180012b89  lea     rax, [rbp+cbData]
0x180012b8d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180012b92  lea     rax, [rbp+Data]
0x180012b96  mov     [rsp+38h+lpData], rax; lpData
0x180012b9b  lea     r9, [rbp+Type]; lpType
0x180012b9f  xor     r8d, r8d; lpReserved
0x180012ba2  mov     rdx, r14; lpValueName
0x180012ba5  mov     rcx, [rbp+phkResult]; hKey
0x180012ba9  call    cs:__imp_RegQueryValueExW
0x180012baf  mov     ebx, eax
0x180012bb1  mov     rcx, [rbp+phkResult]; hKey
0x180012bb5  test    rcx, rcx
0x180012bb8  jz      short loc_180012BC0
0x180012bba  call    cs:__imp_RegCloseKey
0x180012bc0  test    ebx, ebx
0x180012bc2  jnz     short loc_180012C12
0x180012bc4  cmp     dword ptr [rbp+Type], 4
0x180012bc8  jnz     short loc_180012BDC
0x180012bca  cmp     [rbp+cbData], 4
0x180012bce  jnz     short loc_180012BDC
0x180012bd0  cmp     [rbp+Data], 1
0x180012bd4  setz    al
0x180012bd7  jmp     loc_180012C5F
0x180012bdc  mov     rax, cs:WPP_GLOBAL_Control
0x180012be3  cmp     rax, rsi
0x180012be6  jz      short loc_180012C5D
0x180012be8  cmp     byte ptr [rax+19h], 2
0x180012bec  jb      short loc_180012C5D
0x180012bee  test    byte ptr [rax+1Ch], 4
0x180012bf2  jz      short loc_180012C5D
0x180012bf4  mov     rdx, r14
0x180012bf7  lea     rcx, aSRegistryValue_0; "%S registry value is not of type REG_DW"...
0x180012bfe  call    WppDbgPrint
0x180012c03  mov     edx, 15h
0x180012c08  mov     [rsp+38h+lpData], r14
0x180012c0d  jmp     loc_180012B13
0x180012c12  mov     rax, cs:WPP_GLOBAL_Control
0x180012c19  cmp     rax, rsi
0x180012c1c  jz      short loc_180012C5D
0x180012c1e  cmp     byte ptr [rax+19h], 2
0x180012c22  jb      short loc_180012C5D
0x180012c24  test    byte ptr [rax+1Ch], 4
0x180012c28  jz      short loc_180012C5D
0x180012c2a  mov     r8d, ebx
0x180012c2d  mov     rdx, r14
0x180012c30  lea     rcx, aRegqueryvaluee; "RegQueryValueExW for %S failed with err"...
0x180012c37  call    WppDbgPrint
0x180012c3c  mov     edx, 14h
0x180012c41  mov     dword ptr [rsp+38h+lpcbData], ebx
0x180012c45  mov     [rsp+38h+lpData], r14
0x180012c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c51  mov     r8, r13
0x180012c54  mov     rcx, [rcx+10h]
0x180012c58  call    WPP_SF_sSl
0x180012c5d  xor     al, al
0x180012c5f  add     rsp, 38h
0x180012c63  pop     r14
0x180012c65  pop     r13
0x180012c67  pop     r12
0x180012c69  pop     rsi
0x180012c6a  pop     rbx
0x180012c6b  pop     rbp
0x180012c6c  retn
```
