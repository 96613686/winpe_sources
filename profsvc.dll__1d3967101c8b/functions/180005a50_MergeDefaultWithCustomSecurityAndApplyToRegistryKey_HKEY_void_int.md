# MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY__ *,void *,int)

- ea: `0x180005a50`
- end: `0x180005ee5`
- name: `?MergeDefaultWithCustomSecurityAndApplyToRegistryKey_@@YAJPEAUHKEY__@@PEAXH@Z`
- size: `1173`
- prototype: `__int64 __fastcall(HKEY hKey, void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005864`

## callees

- `0x180004ff4`
- `0x180005a50`
- `0x180005ef0`
- `0x180006580`
- `0x1800220f0`
- `0x18003e8fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005aa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005aa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005bf3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005bbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005be5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dca`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180005ac8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180005d73`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180005ac8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180005d73`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180005b97`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180005b97`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180005eb4`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180005eb4`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180005b4d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180005d2e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180005b4d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180005d2e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180005cd7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180005e81`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180005cd7`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180005e81`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180005b0a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180005b0a`

## pseudocode

```c
__int64 __fastcall MergeDefaultWithCustomSecurityAndApplyToRegistryKey_(HKEY hKey, void *a2, int a3)
{
  PACL v4; // r14
  PSECURITY_DESCRIPTOR v6; // r15
  HANDLE ProcessHeap; // rax
  struct _ACL *v8; // rax
  PACL v9; // rsi
  int KeySecurity; // eax
  bool v11; // sf
  struct _ACL *v12; // rcx
  DWORD v13; // ebx
  unsigned __int16 v14; // r12
  DWORD AceCount; // edi
  void *v16; // rbx
  LSTATUS v17; // eax
  unsigned int v18; // ebx
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  DWORD i; // ebx
  BOOL Ace; // eax
  LSTATUS v25; // eax
  signed int LastError; // eax
  bool v27; // sf
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  bool v31; // sf
  int v32; // eax
  DWORD dwDaclSize; // [rsp+68h] [rbp-19h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp-15h] BYREF
  LPVOID pAce; // [rsp+70h] [rbp-11h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-9h] BYREF
  WINBOOL bDaclPresent; // [rsp+80h] [rbp-1h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+84h] [rbp+3h] BYREF
  DWORD dwOwnerSize; // [rsp+88h] [rbp+7h] BYREF
  DWORD dwSaclSize; // [rsp+8Ch] [rbp+Bh] BYREF
  PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor; // [rsp+90h] [rbp+Fh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+98h] [rbp+17h] BYREF
  PACL pAcl; // [rsp+A0h] [rbp+1Fh] BYREF
  DWORD cbSecurityDescriptor; // [rsp+100h] [rbp+7Fh] BYREF

  v4 = 0;
  v6 = 0;
  pAbsoluteSecurityDescriptor = 0;
  pAcl = 0;
  cbSecurityDescriptor = 512;
  ProcessHeap = GetProcessHeap();
  v8 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, 0x200u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_33;
  KeySecurity = RegGetKeySecurity(hKey, 4u, v8, &cbSecurityDescriptor);
  if ( KeySecurity > 0 )
    KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
  if ( KeySecurity != -2147024774 )
    goto LABEL_5;
  pDacl = 0;
  if ( (int)ResultFromHeapReAlloc(v9, cbSecurityDescriptor, (void **)&pDacl) < 0 )
  {
LABEL_33:
    v16 = a2;
    goto LABEL_17;
  }
  v9 = pDacl;
  v25 = RegGetKeySecurity(hKey, 4u, pDacl, &cbSecurityDescriptor);
  v11 = v25 < 0;
  if ( v25 > 0 )
  {
    KeySecurity = (unsigned __int16)v25 | 0x80070000;
LABEL_5:
    v11 = KeySecurity < 0;
  }
  if ( v11 )
    goto LABEL_33;
  if ( !a3 )
    goto LABEL_33;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(v9, &bDaclPresent, &pDacl, &bDaclDefaulted) && (int)ResultFromKnownLastError() < 0 )
    goto LABEL_33;
  if ( !bDaclPresent )
    goto LABEL_33;
  v12 = pDacl;
  if ( !pDacl )
    goto LABEL_33;
  v13 = 0;
  v14 = 0;
  pAce = 0;
  AceCount = pDacl->AceCount;
  if ( pDacl->AceCount )
  {
    while ( GetAce(v12, v13, &pAce) || (int)ResultFromKnownLastError() >= 0 )
    {
      if ( (unsigned int)IsCapabilityAce_((struct _ACE_HEADER *)pAce) )
        v14 += *((_WORD *)pAce + 1);
      if ( ++v13 >= AceCount )
        goto LABEL_16;
      v12 = pDacl;
    }
    goto LABEL_56;
  }
LABEL_16:
  v16 = a2;
  if ( v14 )
  {
    dwAbsoluteSecurityDescriptorSize = 0;
    dwDaclSize = 0;
    dwSaclSize = 0;
    dwOwnerSize = 0;
    dwPrimaryGroupSize = 0;
    if ( MakeAbsoluteSD(
           a2,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize)
      || GetLastError() == 122 )
    {
      goto LABEL_36;
    }
    LastError = GetLastError();
    v27 = LastError < 0;
    if ( LastError > 0 )
      v27 = 1;
    if ( !v27 )
    {
LABEL_36:
      if ( (int)ResultFromHeapAlloc(dwAbsoluteSecurityDescriptorSize, &pAbsoluteSecurityDescriptor) < 0 )
      {
        v6 = pAbsoluteSecurityDescriptor;
        goto LABEL_17;
      }
      v32 = ResultFromHeapAlloc(dwDaclSize + v14, (void **)&pAcl);
      v6 = pAbsoluteSecurityDescriptor;
      if ( v32 >= 0 )
      {
        v4 = pAcl;
        if ( MakeAbsoluteSD(
               a2,
               pAbsoluteSecurityDescriptor,
               &dwAbsoluteSecurityDescriptorSize,
               pAcl,
               &dwDaclSize,
               0,
               &dwSaclSize,
               0,
               &dwOwnerSize,
               0,
               &dwPrimaryGroupSize) )
        {
          goto LABEL_39;
        }
        v28 = GetLastError();
        v29 = v28 < 0;
        if ( v28 > 0 )
          v29 = 1;
        if ( !v29 )
        {
LABEL_39:
          v4->AclRevision = 2;
          v4->AclSize += v14;
          for ( i = 0; ; ++i )
          {
            if ( i >= AceCount )
              goto LABEL_44;
            Ace = GetAce(pDacl, i, &pAce);
            if ( (int)ResultFromWin32Bool(Ace) < 0 )
              goto LABEL_56;
            if ( (unsigned int)IsCapabilityAce_((struct _ACE_HEADER *)pAce) )
            {
              *((_BYTE *)pAce + 1) &= ~0x10u;
              if ( !AddAce(v4, 2u, 0, pAce, *((unsigned __int16 *)pAce + 1)) )
                break;
            }
          }
          v30 = GetLastError();
          v31 = v30 < 0;
          if ( v30 > 0 )
            v31 = 1;
          if ( !v31 )
          {
LABEL_44:
            v16 = v6;
            goto LABEL_17;
          }
        }
LABEL_56:
        v16 = a2;
        goto LABEL_17;
      }
      v4 = pAcl;
    }
  }
LABEL_17:
  v17 = RegSetKeySecurity(hKey, 4u, v16);
  v18 = v17;
  if ( v17 > 0 )
    v18 = (unsigned __int16)v17 | 0x80070000;
  if ( v6 )
  {
    v19 = GetProcessHeap();
    if ( !HeapFree(v19, 0, v6) )
      ResultFromKnownLastError();
  }
  if ( v9 )
  {
    v20 = GetProcessHeap();
    if ( !HeapFree(v20, 0, v9) )
      ResultFromKnownLastError();
  }
  if ( v4 )
  {
    v21 = GetProcessHeap();
    if ( !HeapFree(v21, 0, v4) )
      ResultFromKnownLastError();
  }
  return v18;
}

```

## disassembly

```asm
0x180005a50  mov     rax, rsp
0x180005a53  mov     [rax+10h], rdx
0x180005a57  push    rbp
0x180005a58  push    rbx
0x180005a59  push    r14
0x180005a5b  lea     rbp, [rax-5Fh]
0x180005a5f  sub     rsp, 0C0h
0x180005a66  mov     [rax+8], rsi
0x180005a6a  mov     ebx, r8d
0x180005a6d  mov     [rax-20h], rdi
0x180005a71  xor     edi, edi
0x180005a73  mov     [rax-30h], r13
0x180005a77  mov     r14d, edi
0x180005a7a  mov     [rax-38h], r15
0x180005a7e  mov     r13, rcx
0x180005a81  mov     r15d, edi
0x180005a84  mov     [rbp+57h+pAbsoluteSecurityDescriptor], rdi
0x180005a88  mov     [rbp+57h+pAcl], rdi
0x180005a8c  mov     [rbp+57h+cbSecurityDescriptor], 200h
0x180005a93  call    cs:__imp_GetProcessHeap
0x180005a99  mov     edx, 8; dwFlags
0x180005a9e  mov     r8d, 200h; dwBytes
0x180005aa4  mov     rcx, rax; hHeap
0x180005aa7  call    cs:__imp_HeapAlloc
0x180005aad  mov     rsi, rax
0x180005ab0  test    rax, rax
0x180005ab3  jz      loc_180005C7B
0x180005ab9  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180005abd  mov     r8, rax; pSecurityDescriptor
0x180005ac0  mov     edx, 4; SecurityInformation
0x180005ac5  mov     rcx, r13; hKey
0x180005ac8  call    cs:__imp_RegGetKeySecurity
0x180005ace  test    eax, eax
0x180005ad0  jg      loc_180005C4F
0x180005ad6  cmp     eax, 8007007Ah
0x180005adb  jz      loc_180005E0E
0x180005ae1  test    eax, eax
0x180005ae3  js      loc_180005C7B
0x180005ae9  test    ebx, ebx
0x180005aeb  jz      loc_180005C7B
0x180005af1  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180005af5  mov     [rbp+57h+pDacl], rdi
0x180005af9  lea     r8, [rbp+57h+pDacl]; pDacl
0x180005afd  mov     [rbp+57h+bDaclPresent], edi
0x180005b00  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180005b04  mov     [rbp+57h+bDaclDefaulted], edi
0x180005b07  mov     rcx, rsi; pSecurityDescriptor
0x180005b0a  call    cs:__imp_GetSecurityDescriptorDacl
0x180005b10  test    eax, eax
0x180005b12  jz      loc_180005C6E
0x180005b18  cmp     [rbp+57h+bDaclPresent], edi
0x180005b1b  jz      loc_180005C7B
0x180005b21  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180005b25  test    rcx, rcx
0x180005b28  jz      loc_180005C7B
0x180005b2e  mov     [rsp+0D0h+var_20], r12
0x180005b36  mov     ebx, edi
0x180005b38  mov     r12d, edi
0x180005b3b  mov     [rbp+57h+pAce], rdi
0x180005b3f  movzx   edi, word ptr [rcx+4]
0x180005b43  test    edi, edi
0x180005b45  jz      short loc_180005B76
0x180005b47  lea     r8, [rbp+57h+pAce]; pAce
0x180005b4b  mov     edx, ebx; dwAceIndex
0x180005b4d  call    cs:__imp_GetAce
0x180005b53  test    eax, eax
0x180005b55  jz      loc_180005C5C
0x180005b5b  mov     rcx, [rbp+57h+pAce]; struct _ACE_HEADER *
0x180005b5f  call    ?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z; IsCapabilityAce_(_ACE_HEADER *)
0x180005b64  test    eax, eax
0x180005b66  jnz     loc_180005E2E
0x180005b6c  inc     ebx
0x180005b6e  cmp     ebx, edi
0x180005b70  jb      loc_180005C46
0x180005b76  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180005b7a  test    r12w, r12w
0x180005b7e  jnz     loc_180005C84
0x180005b84  mov     r12, [rsp+0D0h+var_20]
0x180005b8c  mov     r8, rbx; pSecurityDescriptor
0x180005b8f  mov     edx, 4; SecurityInformation
0x180005b94  mov     rcx, r13; hKey
0x180005b97  call    cs:__imp_RegSetKeySecurity
0x180005b9d  mov     r13, [rsp+0D0h+var_28]
0x180005ba5  mov     ebx, eax
0x180005ba7  mov     rdi, [rsp+0B8h]
0x180005baf  test    eax, eax
0x180005bb1  jg      loc_180005C38
0x180005bb7  test    r15, r15
0x180005bba  jz      short loc_180005BD8
0x180005bbc  call    cs:__imp_GetProcessHeap
0x180005bc2  mov     r8, r15; lpMem
0x180005bc5  xor     edx, edx; dwFlags
0x180005bc7  mov     rcx, rax; hHeap
0x180005bca  call    cs:__imp_HeapFree
0x180005bd0  test    eax, eax
0x180005bd2  jz      loc_180005EC7
0x180005bd8  mov     r15, [rsp+0D0h+var_30]
0x180005be0  test    rsi, rsi
0x180005be3  jz      short loc_180005C01
0x180005be5  call    cs:__imp_GetProcessHeap
0x180005beb  mov     r8, rsi; lpMem
0x180005bee  xor     edx, edx; dwFlags
0x180005bf0  mov     rcx, rax; hHeap
0x180005bf3  call    cs:__imp_HeapFree
0x180005bf9  test    eax, eax
0x180005bfb  jz      loc_180005ED1
0x180005c01  mov     rsi, [rsp+0D0h+arg_0]
0x180005c09  test    r14, r14
0x180005c0c  jz      short loc_180005C2A
0x180005c0e  call    cs:__imp_GetProcessHeap
0x180005c14  mov     r8, r14; lpMem
0x180005c17  xor     edx, edx; dwFlags
0x180005c19  mov     rcx, rax; hHeap
0x180005c1c  call    cs:__imp_HeapFree
0x180005c22  test    eax, eax
0x180005c24  jz      loc_180005EDB
0x180005c2a  mov     eax, ebx
0x180005c2c  add     rsp, 0C0h
0x180005c33  pop     r14
0x180005c35  pop     rbx
0x180005c36  pop     rbp
0x180005c37  retn
0x180005c38  movzx   ebx, ax
0x180005c3b  or      ebx, 80070000h
0x180005c41  jmp     loc_180005BB7
0x180005c46  mov     rcx, [rbp+57h+pDacl]
0x180005c4a  jmp     loc_180005B47
0x180005c4f  movzx   eax, ax
0x180005c52  or      eax, 80070000h
0x180005c57  jmp     loc_180005AD6
0x180005c5c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005c61  test    eax, eax
0x180005c63  jns     loc_180005B5B
0x180005c69  jmp     loc_180005DE4
0x180005c6e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005c73  test    eax, eax
0x180005c75  jns     loc_180005B18
0x180005c7b  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180005c7f  jmp     loc_180005B8C
0x180005c84  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180005c88  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], r14d
0x180005c8c  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180005c91  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180005c95  mov     [rsp+0D0h+pPrimaryGroup], r14; pPrimaryGroup
0x180005c9a  lea     rax, [rbp+57h+dwOwnerSize]
0x180005c9e  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180005ca3  xor     r9d, r9d; pDacl
0x180005ca6  mov     [rsp+0D0h+pOwner], r14; pOwner
0x180005cab  lea     rax, [rbp+57h+dwSaclSize]
0x180005caf  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x180005cb4  xor     edx, edx; pAbsoluteSecurityDescriptor
0x180005cb6  lea     rax, [rbp+57h+dwDaclSize]
0x180005cba  mov     [rsp+0D0h+pSacl], r14; pSacl
0x180005cbf  mov     rcx, rbx; pSelfRelativeSecurityDescriptor
0x180005cc2  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x180005cc7  mov     [rbp+57h+dwDaclSize], r14d
0x180005ccb  mov     [rbp+57h+dwSaclSize], r14d
0x180005ccf  mov     [rbp+57h+dwOwnerSize], r14d
0x180005cd3  mov     [rbp+57h+dwPrimaryGroupSize], r14d
0x180005cd7  call    cs:__imp_MakeAbsoluteSD
0x180005cdd  test    eax, eax
0x180005cdf  jnz     short loc_180005CF0
0x180005ce1  call    cs:__imp_GetLastError
0x180005ce7  cmp     eax, 7Ah ; 'z'
0x180005cea  jnz     loc_180005D8E
0x180005cf0  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; dwBytes
0x180005cf3  lea     rdx, [rbp+57h+pAbsoluteSecurityDescriptor]; void **
0x180005cf7  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180005cfc  test    eax, eax
0x180005cfe  jns     loc_180005DED
0x180005d04  mov     r15, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180005d08  jmp     loc_180005B84
0x180005d0d  js      loc_180005DE4
0x180005d13  mov     byte ptr [r14], 2
0x180005d17  add     [r14+2], r12w
0x180005d1c  xor     ebx, ebx
0x180005d1e  xchg    ax, ax
0x180005d20  cmp     ebx, edi
0x180005d22  jnb     short loc_180005D58
0x180005d24  mov     rcx, [rbp+57h+pDacl]; pAcl
0x180005d28  lea     r8, [rbp+57h+pAce]; pAce
0x180005d2c  mov     edx, ebx; dwAceIndex
0x180005d2e  call    cs:__imp_GetAce
0x180005d34  mov     ecx, eax; int
0x180005d36  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180005d3b  test    eax, eax
0x180005d3d  js      loc_180005DE4
0x180005d43  mov     rcx, [rbp+57h+pAce]; struct _ACE_HEADER *
0x180005d47  call    ?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z; IsCapabilityAce_(_ACE_HEADER *)
0x180005d4c  test    eax, eax
0x180005d4e  jnz     loc_180005E94
0x180005d54  inc     ebx
0x180005d56  jmp     short loc_180005D20
0x180005d58  mov     rbx, r15
0x180005d5b  jmp     loc_180005B84
0x180005d60  mov     rsi, [rbp+57h+pDacl]
0x180005d64  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180005d68  mov     r8, rsi; pSecurityDescriptor
0x180005d6b  mov     edx, 4; SecurityInformation
0x180005d70  mov     rcx, r13; hKey
0x180005d73  call    cs:__imp_RegGetKeySecurity
0x180005d79  test    eax, eax
0x180005d7b  jle     loc_180005AE3
0x180005d81  movzx   eax, ax
0x180005d84  or      eax, 80070000h
0x180005d89  jmp     loc_180005AE1
0x180005d8e  call    cs:__imp_GetLastError
0x180005d94  test    eax, eax
0x180005d96  jle     short loc_180005DA2
0x180005d98  movzx   eax, ax
0x180005d9b  or      eax, 80070000h
0x180005da0  test    eax, eax
0x180005da2  js      loc_180005B84
0x180005da8  jmp     loc_180005CF0
0x180005dad  call    cs:__imp_GetLastError
0x180005db3  test    eax, eax
0x180005db5  jle     loc_180005D0D
0x180005dbb  movzx   eax, ax
0x180005dbe  or      eax, 80070000h
0x180005dc3  test    eax, eax
0x180005dc5  jmp     loc_180005D0D
0x180005dca  call    cs:__imp_GetLastError
0x180005dd0  test    eax, eax
0x180005dd2  jle     short loc_180005DDE
0x180005dd4  movzx   eax, ax
0x180005dd7  or      eax, 80070000h
0x180005ddc  test    eax, eax
0x180005dde  jns     loc_180005D58
0x180005de4  mov     rbx, [rbp+57h+pSecurityDescriptor]
0x180005de8  jmp     loc_180005B84
0x180005ded  movzx   ecx, r12w
0x180005df1  lea     rdx, [rbp+57h+pAcl]; void **
0x180005df5  add     ecx, [rbp+57h+dwDaclSize]; dwBytes
0x180005df8  call    ?ResultFromHeapAlloc@@YAJ_KPEAPEAX@Z; ResultFromHeapAlloc(unsigned __int64,void * *)
0x180005dfd  mov     r15, [rbp+57h+pAbsoluteSecurityDescriptor]
0x180005e01  test    eax, eax
0x180005e03  jns     short loc_180005E3C
0x180005e05  mov     r14, [rbp+57h+pAcl]
0x180005e09  jmp     loc_180005B84
0x180005e0e  mov     edx, [rbp+57h+cbSecurityDescriptor]; dwBytes
0x180005e11  lea     r8, [rbp+57h+pDacl]; void **
0x180005e15  mov     rcx, rsi; lpMem
0x180005e18  mov     [rbp+57h+pDacl], rdi
0x180005e1c  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180005e21  test    eax, eax
0x180005e23  js      loc_180005C7B
0x180005e29  jmp     loc_180005D60
0x180005e2e  mov     rax, [rbp+57h+pAce]
0x180005e32  add     r12w, [rax+2]
0x180005e37  jmp     loc_180005B6C
0x180005e3c  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180005e40  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x180005e44  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x180005e49  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180005e4d  mov     [rsp+0D0h+pPrimaryGroup], r14; pPrimaryGroup
0x180005e52  lea     rax, [rbp+57h+dwOwnerSize]
0x180005e56  mov     [rsp+0D0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x180005e5b  mov     rdx, r15; pAbsoluteSecurityDescriptor
0x180005e5e  mov     [rsp+0D0h+pOwner], r14; pOwner
0x180005e63  lea     rax, [rbp+57h+dwSaclSize]
0x180005e67  mov     [rsp+0D0h+lpdwSaclSize], rax; lpdwSaclSize
0x180005e6c  lea     rax, [rbp+57h+dwDaclSize]
0x180005e70  mov     [rsp+0D0h+pSacl], r14; pSacl
0x180005e75  mov     r14, [rbp+57h+pAcl]
0x180005e79  mov     r9, r14; pDacl
0x180005e7c  mov     [rsp+0D0h+lpdwDaclSize], rax; lpdwDaclSize
0x180005e81  call    cs:__imp_MakeAbsoluteSD
0x180005e87  test    eax, eax
0x180005e89  jnz     loc_180005D13
0x180005e8f  jmp     loc_180005DAD
0x180005e94  mov     rax, [rbp+57h+pAce]
0x180005e98  xor     r8d, r8d; dwStartingAceIndex
0x180005e9b  mov     edx, 2; dwAceRevision
0x180005ea0  mov     rcx, r14; pAcl
0x180005ea3  and     byte ptr [rax+1], 0EFh
0x180005ea7  mov     r9, [rbp+57h+pAce]; pAceList
0x180005eab  movzx   eax, word ptr [r9+2]
0x180005eb0  mov     dword ptr [rsp+0D0h+lpdwDaclSize], eax; nAceListLength
0x180005eb4  call    cs:__imp_AddAce
0x180005eba  test    eax, eax
0x180005ebc  jz      loc_180005DCA
0x180005ec2  jmp     loc_180005D54
0x180005ec7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005ecc  jmp     loc_180005BD8
0x180005ed1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005ed6  jmp     loc_180005C01
0x180005edb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180005ee0  jmp     loc_180005C2A
```
