# LDAPConnection::IsEncryptionDisabled(void)

- ea: `0x18001e1ac`
- end: `0x18001e3f5`
- name: `?IsEncryptionDisabled@LDAPConnection@@KAHXZ`
- size: `585`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001eb48`

## callees

- `0x18001426c`
- `0x18001daa8`
- `0x18001e1ac`
- `0x1800254a0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001e3de`
- `ADVAPI32!RegCloseKey` at `0x18001e3de`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e1f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e1f8`
- `ADVAPI32!RegQueryValueExW` at `0x18001e288`
- `ADVAPI32!RegQueryValueExW` at `0x18001e288`

## string_xrefs

- `0x18001e229`: `Cannot open the reg key %S, error %ld`
- `0x18001e2ce`: `Cannot read value %S. Error %ld`
- `0x18001e316`: `The registry value %S does not exist. Using default %ld`
- `0x18001e391`: `Cannot read value %S.  Wrong type %ld. Size = %ld. Value = %ld`
- `0x18001e1e7`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Policy`

## pseudocode

```c
_BOOL8 LDAPConnection::IsEncryptionDisabled(void)
{
  LSTATUS v0; // eax
  char v1; // bl
  int v2; // r9d
  LSTATUS v4; // eax
  char v5; // bl
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  unsigned int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 0;
  Data = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
         0,
         0x20019u,
         &hKey);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Cannot open the reg key %S, error %ld");
      WPP_SF_sSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_5e533440ec7237f17173738acd6b67e7_Traceguids,
        v2,
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Policy",
        v1);
    }
    return 0;
  }
  else
  {
    v4 = RegQueryValueExW(hKey, L"DisableLdapEncryption", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("The registry value %S does not exist. Using default %ld");
          WPP_SF_sSl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_5e533440ec7237f17173738acd6b67e7_Traceguids,
            v7,
            (__int64)L"DisableLdapEncryption",
            0);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Cannot read value %S. Error %ld");
        WPP_SF_sSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_5e533440ec7237f17173738acd6b67e7_Traceguids,
          v6,
          (__int64)L"DisableLdapEncryption",
          v5);
      }
    }
    else if ( Type != 4 || cbData != 4 || Data >= 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Cannot read value %S.  Wrong type %ld. Size = %ld. Value = %ld");
        WPP_SF_sSlll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_5e533440ec7237f17173738acd6b67e7_Traceguids,
          v8,
          (__int64)L"DisableLdapEncryption",
          Type,
          cbData,
          Data);
      }
      Data = 0;
    }
    RegCloseKey(hKey);
    return Data != 0;
  }
}

```

## disassembly

```asm
0x18001e1ac  push    rbp
0x18001e1ae  push    rbx
0x18001e1af  push    r14
0x18001e1b1  mov     rbp, rsp
0x18001e1b4  sub     rsp, 40h
0x18001e1b8  mov     [rbp+hKey], 0
0x18001e1c0  mov     [rbp+cbData], 4
0x18001e1c7  mov     [rbp+Type], 0
0x18001e1ce  mov     [rbp+Data], 0
0x18001e1d5  lea     rax, [rbp+hKey]
0x18001e1d9  mov     [rsp+40h+phkResult], rax; phkResult
0x18001e1de  mov     r9d, 20019h; samDesired
0x18001e1e4  xor     r8d, r8d; ulOptions
0x18001e1e7  lea     r14, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18001e1ee  mov     rdx, r14; lpSubKey
0x18001e1f1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e1f8  call    cs:__imp_RegOpenKeyExW
0x18001e1fe  mov     ebx, eax
0x18001e200  test    eax, eax
0x18001e202  jz      short loc_18001E261
0x18001e204  lea     rcx, WPP_GLOBAL_Control
0x18001e20b  mov     rdx, cs:WPP_GLOBAL_Control
0x18001e212  cmp     rdx, rcx
0x18001e215  jz      short loc_18001E25A
0x18001e217  cmp     byte ptr [rdx+19h], 2
0x18001e21b  jb      short loc_18001E25A
0x18001e21d  test    byte ptr [rdx+1Ch], 4
0x18001e221  jz      short loc_18001E25A
0x18001e223  mov     r8d, eax
0x18001e226  mov     rdx, r14
0x18001e229  lea     rcx, aCannotOpenTheR; "Cannot open the reg key %S, error %ld"
0x18001e230  call    WppDbgPrint
0x18001e235  mov     edx, 13h
0x18001e23a  mov     dword ptr [rsp+40h+lpcbData], ebx
0x18001e23e  mov     [rsp+40h+phkResult], r14
0x18001e243  lea     r8, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001e24a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e251  mov     rcx, [rcx+10h]
0x18001e255  call    WPP_SF_sSl
0x18001e25a  xor     eax, eax
0x18001e25c  jmp     loc_18001E3EC
0x18001e261  lea     rax, [rbp+cbData]
0x18001e265  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001e26a  lea     rax, [rbp+Data]
0x18001e26e  mov     [rsp+40h+phkResult], rax; lpData
0x18001e273  lea     r9, [rbp+Type]; lpType
0x18001e277  xor     r8d, r8d; lpReserved
0x18001e27a  lea     r14, aDisableldapenc; "DisableLdapEncryption"
0x18001e281  mov     rdx, r14; lpValueName
0x18001e284  mov     rcx, [rbp+hKey]; hKey
0x18001e288  call    cs:__imp_RegQueryValueExW
0x18001e28e  mov     ebx, eax
0x18001e290  test    eax, eax
0x18001e292  jz      loc_18001E350
0x18001e298  cmp     eax, 2
0x18001e29b  jz      short loc_18001E2E5
0x18001e29d  lea     rcx, WPP_GLOBAL_Control
0x18001e2a4  mov     rdx, cs:WPP_GLOBAL_Control
0x18001e2ab  cmp     rdx, rcx
0x18001e2ae  jz      loc_18001E3DA
0x18001e2b4  cmp     byte ptr [rdx+19h], 2
0x18001e2b8  jb      loc_18001E3DA
0x18001e2be  test    byte ptr [rdx+1Ch], 4
0x18001e2c2  jz      loc_18001E3DA
0x18001e2c8  mov     r8d, eax
0x18001e2cb  mov     rdx, r14
0x18001e2ce  lea     rcx, aCannotReadValu_3; "Cannot read value %S. Error %ld"
0x18001e2d5  call    WppDbgPrint
0x18001e2da  mov     edx, 14h
0x18001e2df  mov     dword ptr [rsp+40h+lpcbData], ebx
0x18001e2e3  jmp     short loc_18001E32F
0x18001e2e5  lea     rcx, WPP_GLOBAL_Control
0x18001e2ec  mov     rax, cs:WPP_GLOBAL_Control
0x18001e2f3  cmp     rax, rcx
0x18001e2f6  jz      loc_18001E3DA
0x18001e2fc  cmp     byte ptr [rax+19h], 4
0x18001e300  jb      loc_18001E3DA
0x18001e306  test    byte ptr [rax+1Ch], 4
0x18001e30a  jz      loc_18001E3DA
0x18001e310  xor     r8d, r8d
0x18001e313  mov     rdx, r14
0x18001e316  lea     rcx, aTheRegistryVal; "The registry value %S does not exist. U"...
0x18001e31d  call    WppDbgPrint
0x18001e322  mov     edx, 15h
0x18001e327  mov     dword ptr [rsp+40h+lpcbData], 0
0x18001e32f  mov     [rsp+40h+phkResult], r14
0x18001e334  lea     r8, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001e33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e342  mov     rcx, [rcx+10h]
0x18001e346  call    WPP_SF_sSl
0x18001e34b  jmp     loc_18001E3DA
0x18001e350  mov     r9d, [rbp+cbData]
0x18001e354  mov     edx, [rbp+Data]
0x18001e357  mov     r8d, [rbp+Type]
0x18001e35b  cmp     r8d, 4
0x18001e35f  jnz     short loc_18001E36B
0x18001e361  cmp     r9d, r8d
0x18001e364  jnz     short loc_18001E36B
0x18001e366  cmp     edx, 2
0x18001e369  jb      short loc_18001E3DA
0x18001e36b  lea     rcx, WPP_GLOBAL_Control
0x18001e372  mov     rax, cs:WPP_GLOBAL_Control
0x18001e379  cmp     rax, rcx
0x18001e37c  jz      short loc_18001E3D3
0x18001e37e  cmp     byte ptr [rax+19h], 2
0x18001e382  jb      short loc_18001E3D3
0x18001e384  test    byte ptr [rax+1Ch], 4
0x18001e388  jz      short loc_18001E3D3
0x18001e38a  mov     dword ptr [rsp+40h+phkResult], edx
0x18001e38e  mov     rdx, r14
0x18001e391  lea     rcx, aCannotReadValu; "Cannot read value %S.  Wrong type %ld. "...
0x18001e398  call    WppDbgPrint
0x18001e39d  mov     edx, 16h
0x18001e3a2  mov     eax, [rbp+Data]
0x18001e3a5  mov     [rsp+40h+var_8], eax
0x18001e3a9  mov     eax, [rbp+cbData]
0x18001e3ac  mov     [rsp+40h+var_10], eax
0x18001e3b0  mov     eax, [rbp+Type]
0x18001e3b3  mov     dword ptr [rsp+40h+lpcbData], eax
0x18001e3b7  mov     [rsp+40h+phkResult], r14
0x18001e3bc  lea     r8, WPP_5e533440ec7237f17173738acd6b67e7_Traceguids
0x18001e3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3ca  mov     rcx, [rcx+10h]
0x18001e3ce  call    WPP_SF_sSlll
0x18001e3d3  mov     [rbp+Data], 0
0x18001e3da  mov     rcx, [rbp+hKey]; hKey
0x18001e3de  call    cs:__imp_RegCloseKey
0x18001e3e4  xor     eax, eax
0x18001e3e6  cmp     [rbp+Data], eax
0x18001e3e9  setnz   al
0x18001e3ec  add     rsp, 40h
0x18001e3f0  pop     r14
0x18001e3f2  pop     rbx
0x18001e3f3  pop     rbp
0x18001e3f4  retn
```
