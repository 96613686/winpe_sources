# WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)

- ea: `0x180036ec4`
- end: `0x180037091`
- name: `?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z`
- size: `461`
- prototype: `__int64 __fastcall(HKEY hKey, enum _ACCESS_MODE, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b4c4`
- `0x18002ce14`
- `0x18002ecac`
- `0x180036a5c`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x1800047cc`
- `0x180036ec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036f1f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180036f15`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180036f15`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180037044`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180037044`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180036f88`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180036fc5`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180036f88`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180036fc5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ff0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036ff0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003705d`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x18003702a`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x18003702a`

## pseudocode

```c
__int64 __fastcall WerPluginAdjustAppContainerAccessToKey(HKEY hKey, enum _ACCESS_MODE a2, DWORD a3)
{
  void *pOldSD; // rbx
  signed int LastError; // eax
  const struct std::nothrow_t *v7; // rdx
  LSTATUS KeySecurity; // edi
  bool v9; // cc
  void *v10; // rax
  HLOCAL v11; // rcx
  DWORD cbSid; // [rsp+50h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-51h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfAccessEntries; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pSid[80]; // [rsp+90h] [rbp-19h] BYREF

  cbSid = 68;
  pOldSD = 0;
  hMem = 0;
  memset(&pListOfAccessEntries, 0, sizeof(pListOfAccessEntries));
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    KeySecurity = LastError;
    v9 = LastError <= 0;
    goto LABEL_3;
  }
  memset(&pListOfAccessEntries.grfInheritance + 1, 0, 20);
  pListOfAccessEntries.grfAccessPermissions = a3;
  *((_DWORD *)&pListOfAccessEntries.Trustee.TrusteeType + 1) = 0;
  pListOfAccessEntries.grfAccessMode = GRANT_ACCESS;
  pListOfAccessEntries.grfInheritance = 3;
  pListOfAccessEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  pListOfAccessEntries.Trustee.ptstrName = (LPWCH)pSid;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSid);
  if ( KeySecurity == 122 )
  {
    v10 = operator new[](cbSid, (const struct std::nothrow_t *)&std::nothrow);
    pOldSD = v10;
    if ( !v10 )
    {
      KeySecurity = -2147024882;
      goto LABEL_20;
    }
    KeySecurity = RegGetKeySecurity(hKey, 4u, v10, &cbSid);
  }
  if ( KeySecurity )
  {
    if ( KeySecurity <= 0 )
    {
LABEL_6:
      if ( KeySecurity >= 0 )
        KeySecurity = -2147467259;
      goto LABEL_20;
    }
    KeySecurity = (unsigned __int16)KeySecurity;
LABEL_5:
    KeySecurity |= 0x80070000;
    goto LABEL_6;
  }
  v11 = hMem;
  hMem = 0;
  if ( v11 )
    LocalFree(v11);
  LastError = BuildSecurityDescriptorW(0, 0, 1u, &pListOfAccessEntries, 0, 0, pOldSD, &cbSid, &hMem);
  KeySecurity = LastError;
  v9 = LastError <= 0;
  if ( LastError
    || (LastError = RegSetKeySecurity(hKey, 4u, hMem), KeySecurity = LastError, v9 = LastError <= 0, LastError) )
  {
LABEL_3:
    if ( v9 )
      goto LABEL_6;
    KeySecurity = (unsigned __int16)LastError;
    goto LABEL_5;
  }
LABEL_20:
  if ( hMem )
    LocalFree(hMem);
  if ( pOldSD )
    operator delete(pOldSD, v7);
  return (unsigned int)KeySecurity;
}

```

## disassembly

```asm
0x180036ec4  mov     [rsp-8+arg_8], rbx
0x180036ec9  push    rbp
0x180036eca  push    rsi
0x180036ecb  push    rdi
0x180036ecc  lea     rbp, [rsp-47h]
0x180036ed1  sub     rsp, 0F0h
0x180036ed8  mov     rax, cs:__security_cookie
0x180036edf  xor     rax, rsp
0x180036ee2  mov     [rbp+57h+var_20], rax
0x180036ee6  xorps   xmm0, xmm0
0x180036ee9  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180036ef0  xor     ebx, ebx
0x180036ef2  lea     r9, [rbp+57h+cbSid]; cbSid
0x180036ef6  mov     edi, r8d
0x180036ef9  mov     [rbp+57h+hMem], rbx
0x180036efd  mov     rsi, rcx
0x180036f00  lea     r8, [rbp+57h+pSid]; pSid
0x180036f04  xor     edx, edx; DomainSid
0x180036f06  lea     ecx, [rbx+54h]; WellKnownSidType
0x180036f09  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x180036f0d  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x180036f11  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x180036f15  call    cs:__imp_CreateWellKnownSid
0x180036f1b  test    eax, eax
0x180036f1d  jnz     short loc_180036F43
0x180036f1f  call    cs:__imp_GetLastError
0x180036f25  mov     edi, eax
0x180036f27  test    eax, eax
0x180036f29  jle     short loc_180036F34
0x180036f2b  movzx   edi, ax
0x180036f2e  or      edi, 80070000h
0x180036f34  test    edi, edi
0x180036f36  mov     eax, 80004005h
0x180036f3b  cmovns  edi, eax
0x180036f3e  jmp     loc_180037054
0x180036f43  xorps   xmm0, xmm0
0x180036f46  lea     rax, [rbp+57h+pSid]
0x180036f4a  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x180036f4e  xor     r8d, r8d; pSecurityDescriptor
0x180036f51  lea     r9, [rbp+57h+cbSid]; lpcbSecurityDescriptor
0x180036f55  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x180036f59  mov     rcx, rsi; hKey
0x180036f5c  mov     [rbp+57h+pListOfAccessEntries.grfAccessPermissions], edi
0x180036f5f  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x180036f63  lea     edx, [r8+4]; SecurityInformation
0x180036f67  mov     [rbp+57h+pListOfAccessEntries.grfAccessMode], 1
0x180036f6e  mov     [rbp+57h+pListOfAccessEntries.grfInheritance], 3
0x180036f75  mov     [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], rbx
0x180036f79  mov     qword ptr [rbp+57h+pListOfAccessEntries.Trustee.MultipleTrusteeOperation], rbx
0x180036f7d  mov     [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], 5
0x180036f84  mov     [rbp+57h+pListOfAccessEntries.Trustee.ptstrName], rax
0x180036f88  call    cs:__imp_RegGetKeySecurity
0x180036f8e  mov     edi, eax
0x180036f90  cmp     eax, 7Ah ; 'z'
0x180036f93  jnz     short loc_180036FCD
0x180036f95  mov     ecx, [rbp+57h+cbSid]; unsigned __int64
0x180036f98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036f9f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180036fa4  mov     rbx, rax
0x180036fa7  test    rax, rax
0x180036faa  jnz     short loc_180036FB6
0x180036fac  mov     edi, 8007000Eh
0x180036fb1  jmp     loc_180037054
0x180036fb6  lea     r9, [rbp+57h+cbSid]; lpcbSecurityDescriptor
0x180036fba  mov     r8, rax; pSecurityDescriptor
0x180036fbd  mov     edx, 4; SecurityInformation
0x180036fc2  mov     rcx, rsi; hKey
0x180036fc5  call    cs:__imp_RegGetKeySecurity
0x180036fcb  mov     edi, eax
0x180036fcd  test    edi, edi
0x180036fcf  jz      short loc_180036FDF
0x180036fd1  jle     loc_180036F34
0x180036fd7  movzx   edi, di
0x180036fda  jmp     loc_180036F2E
0x180036fdf  mov     rcx, [rbp+57h+hMem]; hMem
0x180036fe3  mov     [rbp+57h+hMem], 0
0x180036feb  test    rcx, rcx
0x180036fee  jz      short loc_180036FF6
0x180036ff0  call    cs:__imp_LocalFree
0x180036ff6  lea     rax, [rbp+57h+hMem]
0x180036ffa  xor     edx, edx; pGroup
0x180036ffc  mov     [rsp+100h+pNewSD], rax; pNewSD
0x180037001  lea     r9, [rbp+57h+pListOfAccessEntries]; pListOfAccessEntries
0x180037005  lea     rax, [rbp+57h+cbSid]
0x180037009  xor     ecx, ecx; pOwner
0x18003700b  mov     [rsp+100h+pSizeNewSD], rax; pSizeNewSD
0x180037010  mov     [rsp+100h+pOldSD], rbx; pOldSD
0x180037015  lea     r8d, [rdx+1]; cCountOfAccessEntries
0x180037019  mov     [rsp+100h+pListOfAuditEntries], 0; pListOfAuditEntries
0x180037022  mov     [rsp+100h+cCountOfAuditEntries], 0; cCountOfAuditEntries
0x18003702a  call    cs:__imp_BuildSecurityDescriptorW
0x180037030  mov     edi, eax
0x180037032  test    eax, eax
0x180037034  jnz     loc_180036F29
0x18003703a  mov     r8, [rbp+57h+hMem]; pSecurityDescriptor
0x18003703e  lea     edx, [rax+4]; SecurityInformation
0x180037041  mov     rcx, rsi; hKey
0x180037044  call    cs:__imp_RegSetKeySecurity
0x18003704a  mov     edi, eax
0x18003704c  test    eax, eax
0x18003704e  jnz     loc_180036F29
0x180037054  mov     rcx, [rbp+57h+hMem]; hMem
0x180037058  test    rcx, rcx
0x18003705b  jz      short loc_180037063
0x18003705d  call    cs:__imp_LocalFree
0x180037063  test    rbx, rbx
0x180037066  jz      short loc_180037070
0x180037068  mov     rcx, rbx; void *
0x18003706b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180037070  mov     eax, edi
0x180037072  mov     rcx, [rbp+57h+var_20]
0x180037076  xor     rcx, rsp; StackCookie
0x180037079  call    __security_check_cookie
0x18003707e  mov     rbx, [rsp+100h+arg_8]
0x180037086  add     rsp, 0F0h
0x18003708d  pop     rdi
0x18003708e  pop     rsi
0x18003708f  pop     rbp
0x180037090  retn
```
