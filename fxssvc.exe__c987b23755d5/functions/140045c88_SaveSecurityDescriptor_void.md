# SaveSecurityDescriptor(void *)

- ea: `0x140045c88`
- end: `0x140045f93`
- name: `?SaveSecurityDescriptor@@YAKPEAX@Z`
- size: `779`
- prototype: `unsigned int __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004501c`
- `0x140046610`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140045c88`
- `0x140065d14`
- `0x140065dbc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140045f6a`
- `ADVAPI32!RegCloseKey` at `0x140045f6a`
- `ADVAPI32!RegCreateKeyExW` at `0x140045d3e`
- `ADVAPI32!RegCreateKeyExW` at `0x140045d3e`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140045d8c`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140045d8c`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140045dde`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x140045dde`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x140045e21`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x140045e21`
- `ADVAPI32!RegSetValueExW` at `0x140045e52`
- `ADVAPI32!RegSetValueExW` at `0x140045f29`
- `ADVAPI32!RegSetValueExW` at `0x140045e52`
- `ADVAPI32!RegSetValueExW` at `0x140045f29`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140045ed8`
- `ADVAPI32!MakeSelfRelativeSD` at `0x140045ed8`
- `KERNEL32!GetLastError` at `0x140045de8`
- `KERNEL32!GetLastError` at `0x140045ee2`
- `KERNEL32!GetLastError` at `0x140045de8`
- `KERNEL32!GetLastError` at `0x140045ee2`

## string_xrefs

- `0x140045d1e`: `Software\Microsoft\Fax\Security`
- `0x140045e39`: `Descriptor`
- `0x140045f0c`: `Descriptor`

## pseudocode

```c
__int64 __fastcall SaveSecurityDescriptor(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  BYTE *v4; // rdi
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  DWORD LastError; // eax
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  DWORD SecurityDescriptorLength; // eax
  BYTE *v11; // rax
  DWORD dwRevision; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  WORD pControl; // [rsp+98h] [rbp+38h] BYREF
  DWORD dwBufferLength; // [rsp+A0h] [rbp+40h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  dwBufferLength = 0;
  pControl = 0x8000;
  hKey = 0;
  dwDisposition = 0;
  dwRevision = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Fax\\Security",
         0,
         (LPWSTR)&Class,
         0,
         0x20006u,
         0,
         &hKey,
         &dwDisposition);
  v3 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v2);
    }
    return v3;
  }
  v4 = 0;
  if ( !IsValidSecurityDescriptor(pAbsoluteSecurityDescriptor) )
  {
    v3 = 1338;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v6 = 24;
    goto LABEL_15;
  }
  if ( !GetSecurityDescriptorControl(pAbsoluteSecurityDescriptor, &pControl, &dwRevision) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v9 = 25;
    goto LABEL_42;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(pAbsoluteSecurityDescriptor);
  dwBufferLength = SecurityDescriptorLength;
  if ( (pControl & 0x8000u) != 0 )
  {
    LastError = RegSetValueExW(
                  hKey,
                  L"Descriptor",
                  0,
                  3u,
                  (const BYTE *)pAbsoluteSecurityDescriptor,
                  SecurityDescriptorLength);
    v3 = LastError;
    if ( !LastError )
      goto LABEL_43;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v9 = 26;
    goto LABEL_42;
  }
  v11 = (BYTE *)pMemAlloc(SecurityDescriptorLength);
  v4 = v11;
  if ( v11 )
  {
    if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v11, &dwBufferLength) )
    {
      LastError = RegSetValueExW(hKey, L"Descriptor", 0, 3u, v4, dwBufferLength);
      v3 = LastError;
      if ( !LastError )
        goto LABEL_43;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v9 = 29;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v9 = 28;
    }
LABEL_42:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    goto LABEL_43;
  }
  v3 = 8;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_43;
  }
  v6 = 27;
LABEL_15:
  WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
    pMemFree(v4);
  return v3;
}

```

## disassembly

```asm
0x140045c88  mov     [rsp-28h+arg_0], rbx
0x140045c8d  push    rbp
0x140045c8e  push    rsi
0x140045c8f  push    rdi
0x140045c90  push    r12
0x140045c92  push    r13
0x140045c94  mov     rbp, rsp
0x140045c97  sub     rsp, 60h
0x140045c9b  mov     eax, 8000h
0x140045ca0  mov     [rbp+dwBufferLength], 0
0x140045ca7  mov     [rbp+pControl], ax
0x140045cab  mov     rsi, rcx
0x140045cae  mov     [rbp+hKey], 0
0x140045cb6  mov     [rbp+dwDisposition], 0
0x140045cbd  mov     [rbp+dwRevision], 0
0x140045cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140045ccb  lea     r12, WPP_GLOBAL_Control
0x140045cd2  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140045cd9  cmp     rcx, r12
0x140045cdc  jz      short loc_140045CFB
0x140045cde  test    byte ptr [rcx+1Ch], 4
0x140045ce2  jz      short loc_140045CFB
0x140045ce4  cmp     byte ptr [rcx+19h], 5
0x140045ce8  jb      short loc_140045CFB
0x140045cea  mov     rcx, [rcx+10h]
0x140045cee  mov     edx, 16h
0x140045cf3  mov     r8, r13
0x140045cf6  call    WPP_SF_
0x140045cfb  lea     rax, [rbp+dwDisposition]
0x140045cff  xor     r8d, r8d; Reserved
0x140045d02  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x140045d07  lea     r9, Class; lpClass
0x140045d0e  lea     rax, [rbp+hKey]
0x140045d12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140045d19  mov     [rsp+60h+phkResult], rax; phkResult
0x140045d1e  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Fax\\Security"
0x140045d25  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140045d2e  mov     [rsp+60h+samDesired], 20006h; samDesired
0x140045d36  mov     [rsp+60h+dwOptions], 0; dwOptions
0x140045d3e  call    cs:__imp_RegCreateKeyExW
0x140045d44  mov     ebx, eax
0x140045d46  test    eax, eax
0x140045d48  jz      short loc_140045D87
0x140045d4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045d51  cmp     rcx, r12
0x140045d54  jz      loc_140045F7D
0x140045d5a  test    byte ptr [rcx+1Ch], 4
0x140045d5e  jz      loc_140045F7D
0x140045d64  cmp     byte ptr [rcx+19h], 2
0x140045d68  jb      loc_140045F7D
0x140045d6e  mov     rcx, [rcx+10h]
0x140045d72  mov     edx, 17h
0x140045d77  mov     r9d, eax
0x140045d7a  mov     r8, r13
0x140045d7d  call    WPP_SF_d
0x140045d82  jmp     loc_140045F7D
0x140045d87  mov     rcx, rsi; pSecurityDescriptor
0x140045d8a  xor     edi, edi
0x140045d8c  call    cs:__imp_IsValidSecurityDescriptor
0x140045d92  test    eax, eax
0x140045d94  jnz     short loc_140045DD3
0x140045d96  mov     ebx, 53Ah
0x140045d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045da2  cmp     rcx, r12
0x140045da5  jz      loc_140045F61
0x140045dab  test    byte ptr [rcx+1Ch], 4
0x140045daf  jz      loc_140045F61
0x140045db5  cmp     byte ptr [rcx+19h], 2
0x140045db9  jb      loc_140045F61
0x140045dbf  lea     edx, [rdi+18h]
0x140045dc2  mov     rcx, [rcx+10h]
0x140045dc6  mov     r8, r13
0x140045dc9  call    WPP_SF_
0x140045dce  jmp     loc_140045F61
0x140045dd3  lea     r8, [rbp+dwRevision]; lpdwRevision
0x140045dd7  mov     rcx, rsi; pSecurityDescriptor
0x140045dda  lea     rdx, [rbp+pControl]; pControl
0x140045dde  call    cs:__imp_GetSecurityDescriptorControl
0x140045de4  test    eax, eax
0x140045de6  jnz     short loc_140045E1E
0x140045de8  call    cs:__imp_GetLastError
0x140045dee  mov     ebx, eax
0x140045df0  mov     rcx, cs:WPP_GLOBAL_Control
0x140045df7  cmp     rcx, r12
0x140045dfa  jz      loc_140045F61
0x140045e00  test    byte ptr [rcx+1Ch], 4
0x140045e04  jz      loc_140045F61
0x140045e0a  cmp     byte ptr [rcx+19h], 2
0x140045e0e  jb      loc_140045F61
0x140045e14  mov     edx, 19h
0x140045e19  jmp     loc_140045F52
0x140045e1e  mov     rcx, rsi; pSecurityDescriptor
0x140045e21  call    cs:__imp_GetSecurityDescriptorLength
0x140045e27  mov     ecx, 8000h
0x140045e2c  mov     [rbp+dwBufferLength], eax
0x140045e2f  test    [rbp+pControl], cx
0x140045e33  jz      short loc_140045E90
0x140045e35  mov     rcx, [rbp+hKey]; hKey
0x140045e39  lea     rdx, aDescriptor; "Descriptor"
0x140045e40  mov     [rsp+60h+samDesired], eax; cbData
0x140045e44  mov     r9d, 3; dwType
0x140045e4a  xor     r8d, r8d; Reserved
0x140045e4d  mov     qword ptr [rsp+60h+dwOptions], rsi; lpData
0x140045e52  call    cs:__imp_RegSetValueExW
0x140045e58  mov     ebx, eax
0x140045e5a  test    eax, eax
0x140045e5c  jz      loc_140045F61
0x140045e62  mov     rcx, cs:WPP_GLOBAL_Control
0x140045e69  cmp     rcx, r12
0x140045e6c  jz      loc_140045F61
0x140045e72  test    byte ptr [rcx+1Ch], 4
0x140045e76  jz      loc_140045F61
0x140045e7c  cmp     byte ptr [rcx+19h], 2
0x140045e80  jb      loc_140045F61
0x140045e86  mov     edx, 1Ah
0x140045e8b  jmp     loc_140045F52
0x140045e90  mov     ecx, eax; dwBytes
0x140045e92  call    pMemAlloc
0x140045e97  mov     rdi, rax
0x140045e9a  test    rax, rax
0x140045e9d  jnz     short loc_140045ECE
0x140045e9f  lea     ebx, [rax+8]
0x140045ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x140045ea9  cmp     rcx, r12
0x140045eac  jz      loc_140045F61
0x140045eb2  test    byte ptr [rcx+1Ch], 4
0x140045eb6  jz      loc_140045F61
0x140045ebc  cmp     byte ptr [rcx+19h], 2
0x140045ec0  jb      loc_140045F61
0x140045ec6  lea     edx, [rax+1Bh]
0x140045ec9  jmp     loc_140045DC2
0x140045ece  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x140045ed2  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x140045ed5  mov     rcx, rsi; pAbsoluteSecurityDescriptor
0x140045ed8  call    cs:__imp_MakeSelfRelativeSD
0x140045ede  test    eax, eax
0x140045ee0  jnz     short loc_140045F09
0x140045ee2  call    cs:__imp_GetLastError
0x140045ee8  mov     ebx, eax
0x140045eea  mov     rcx, cs:WPP_GLOBAL_Control
0x140045ef1  cmp     rcx, r12
0x140045ef4  jz      short loc_140045F61
0x140045ef6  test    byte ptr [rcx+1Ch], 4
0x140045efa  jz      short loc_140045F61
0x140045efc  cmp     byte ptr [rcx+19h], 2
0x140045f00  jb      short loc_140045F61
0x140045f02  mov     edx, 1Ch
0x140045f07  jmp     short loc_140045F52
0x140045f09  mov     eax, [rbp+dwBufferLength]
0x140045f0c  lea     rdx, aDescriptor; "Descriptor"
0x140045f13  mov     rcx, [rbp+hKey]; hKey
0x140045f17  mov     r9d, 3; dwType
0x140045f1d  mov     [rsp+60h+samDesired], eax; cbData
0x140045f21  xor     r8d, r8d; Reserved
0x140045f24  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x140045f29  call    cs:__imp_RegSetValueExW
0x140045f2f  mov     ebx, eax
0x140045f31  test    eax, eax
0x140045f33  jz      short loc_140045F61
0x140045f35  mov     rcx, cs:WPP_GLOBAL_Control
0x140045f3c  cmp     rcx, r12
0x140045f3f  jz      short loc_140045F61
0x140045f41  test    byte ptr [rcx+1Ch], 4
0x140045f45  jz      short loc_140045F61
0x140045f47  cmp     byte ptr [rcx+19h], 2
0x140045f4b  jb      short loc_140045F61
0x140045f4d  mov     edx, 1Dh
0x140045f52  mov     rcx, [rcx+10h]
0x140045f56  mov     r9d, eax
0x140045f59  mov     r8, r13
0x140045f5c  call    WPP_SF_d
0x140045f61  mov     rcx, [rbp+hKey]; hKey
0x140045f65  test    rcx, rcx
0x140045f68  jz      short loc_140045F70
0x140045f6a  call    cs:__imp_RegCloseKey
0x140045f70  test    rdi, rdi
0x140045f73  jz      short loc_140045F7D
0x140045f75  mov     rcx, rdi; lpMem
0x140045f78  call    pMemFree
0x140045f7d  mov     eax, ebx
0x140045f7f  mov     rbx, [rsp+60h+arg_0]
0x140045f87  add     rsp, 60h
0x140045f8b  pop     r13
0x140045f8d  pop     r12
0x140045f8f  pop     rdi
0x140045f90  pop     rsi
0x140045f91  pop     rbp
0x140045f92  retn
```
