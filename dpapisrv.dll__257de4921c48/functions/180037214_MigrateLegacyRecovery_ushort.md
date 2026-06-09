# MigrateLegacyRecovery(ushort *)

- ea: `0x180037214`
- end: `0x1800373a5`
- name: `?MigrateLegacyRecovery@@YAKPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800376a0`

## callees

- `0x180007f10`
- `0x180013c10`
- `0x18001c9c0`
- `0x180036a6c`
- `0x180037214`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800372a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800372a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037313`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180037303`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180037303`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18003734c`
- `api-ms-win-core-registry-l2-1-0!RegSaveKeyW` at `0x18003734c`

## string_xrefs

- `0x1800372be`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x18003736b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180037298`: `Security\Recovery\`

## pseudocode

```c
__int64 __fastcall MigrateLegacyRecovery(LPCWSTR lpFile)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  DWORD LastError; // eax
  __int64 v5; // r9
  HKEY *p_hKey; // [rsp+50h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR *p_SecurityDescriptor; // [rsp+58h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-20h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+A8h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+38h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  hKey = 0;
  p_hKey = &hKey;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Security\\Recovery\\", 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &hKey, 0);
  v3 = v2;
  if ( !v2 )
  {
    SecurityDescriptor = 0;
    SecurityDescriptorSize = 0;
    p_SecurityDescriptor = &SecurityDescriptor;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:SYD:P(A;OICI;FA;;;SY)(A;OICI;WDRC;;;BA)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      LastError = RegSaveKeyW(hKey, lpFile, &SecurityAttributes);
      v3 = LastError;
      if ( !LastError || LastError == 183 )
      {
        v3 = 0;
        goto LABEL_13;
      }
      v5 = 1390;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      v5 = 1375;
    }
    DebugTraceError(LastError, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v5);
LABEL_13:
    ScopedLocalFree::~ScopedLocalFree((ScopedLocalFree *)&p_SecurityDescriptor);
    goto LABEL_14;
  }
  DebugTraceError(v2, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 1360);
LABEL_14:
  ScopedRegClose::~ScopedRegClose((ScopedRegClose *)&p_hKey);
  return v3;
}

```

## disassembly

```asm
0x180037214  push    rbp
0x180037216  push    rbx
0x180037217  push    rdi
0x180037218  mov     rbp, rsp
0x18003721b  sub     rsp, 80h
0x180037222  mov     rdi, rcx
0x180037225  lea     rax, WPP_GLOBAL_Control
0x18003722c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037233  cmp     rcx, rax
0x180037236  jz      short loc_180037253
0x180037238  test    byte ptr [rcx+1Ch], 4
0x18003723c  jz      short loc_180037253
0x18003723e  mov     edx, 15h
0x180037243  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x18003724a  mov     rcx, [rcx+10h]
0x18003724e  call    WPP_SF_
0x180037253  mov     [rbp+hKey], 0
0x18003725b  lea     rax, [rbp+hKey]
0x18003725f  mov     [rbp+var_30], rax
0x180037263  mov     [rsp+80h+lpdwDisposition], 0; lpdwDisposition
0x18003726c  lea     rax, [rbp+hKey]
0x180037270  mov     [rsp+80h+phkResult], rax; phkResult
0x180037275  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003727e  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x180037286  mov     [rsp+80h+dwOptions], 0; dwOptions
0x18003728e  lea     r9, Class; lpClass
0x180037295  xor     r8d, r8d; Reserved
0x180037298  lea     rdx, aSecurityRecove; "Security\\Recovery\\"
0x18003729f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800372a6  call    cs:__imp_RegCreateKeyExW
0x1800372ad  nop     dword ptr [rax+rax+00h]
0x1800372b2  mov     ebx, eax
0x1800372b4  test    eax, eax
0x1800372b6  jz      short loc_1800372D8
0x1800372b8  mov     r9d, 550h
0x1800372be  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800372c5  lea     rdx, aDwerror; "dwError"
0x1800372cc  mov     ecx, eax
0x1800372ce  call    DebugTraceError
0x1800372d3  jmp     loc_18003738E
0x1800372d8  mov     [rbp+SecurityDescriptor], 0
0x1800372e0  mov     [rbp+SecurityDescriptorSize], 0
0x1800372e7  lea     rax, [rbp+SecurityDescriptor]
0x1800372eb  mov     [rbp+var_28], rax
0x1800372ef  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800372f3  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800372f7  mov     edx, 1; StringSDRevision
0x1800372fc  lea     rcx, aOSydPAOiciFaSy; "O:SYD:P(A;OICI;FA;;;SY)(A;OICI;WDRC;;;B"...
0x180037303  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003730a  nop     dword ptr [rax+rax+00h]
0x18003730f  test    eax, eax
0x180037311  jnz     short loc_180037329
0x180037313  call    cs:__imp_GetLastError
0x18003731a  nop     dword ptr [rax+rax+00h]
0x18003731f  mov     ebx, eax
0x180037321  mov     r9d, 55Fh
0x180037327  jmp     short loc_18003736B
0x180037329  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x180037331  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x180037339  mov     rax, [rbp+SecurityDescriptor]
0x18003733d  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x180037341  lea     r8, [rbp+SecurityAttributes]; lpSecurityAttributes
0x180037345  mov     rdx, rdi; lpFile
0x180037348  mov     rcx, [rbp+hKey]; hKey
0x18003734c  call    cs:__imp_RegSaveKeyW
0x180037353  nop     dword ptr [rax+rax+00h]
0x180037358  mov     ebx, eax
0x18003735a  test    eax, eax
0x18003735c  jz      short loc_180037382
0x18003735e  cmp     eax, 0B7h
0x180037363  jz      short loc_180037382
0x180037365  mov     r9d, 56Eh
0x18003736b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180037372  lea     rdx, aDwerror; "dwError"
0x180037379  mov     ecx, eax
0x18003737b  call    DebugTraceError
0x180037380  jmp     short loc_180037384
0x180037382  xor     ebx, ebx
0x180037384  lea     rcx, [rbp+var_28]; this
0x180037388  call    ??1ScopedLocalFree@@QEAA@XZ; ScopedLocalFree::~ScopedLocalFree(void)
0x18003738d  nop
0x18003738e  lea     rcx, [rbp+var_30]; this
0x180037392  call    ??1ScopedRegClose@@QEAA@XZ; ScopedRegClose::~ScopedRegClose(void)
0x180037397  mov     eax, ebx
0x180037399  add     rsp, 80h
0x1800373a0  pop     rdi
0x1800373a1  pop     rbx
0x1800373a2  pop     rbp
0x1800373a3  retn
```
