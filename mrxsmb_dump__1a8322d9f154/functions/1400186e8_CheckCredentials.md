# CheckCredentials

- ea: `0x1400186e8`
- end: `0x1400189b5`
- name: `CheckCredentials`
- size: `717`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017e60`
- `0x14002e770`

## callees

- `0x1400186e8`
- `0x140039fd8`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!LsaFreeReturnBuffer` at `0x14001895b`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x14001895b`
- `ntoskrnl!ExAllocatePool2` at `0x1400187a5`
- `ntoskrnl!ExAllocatePool2` at `0x1400187e5`
- `ntoskrnl!ExAllocatePool2` at `0x1400187a5`
- `ntoskrnl!ExAllocatePool2` at `0x1400187e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018979`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018997`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018979`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018997`
- `ksecdd!GetSecurityUserInfo` at `0x140018778`
- `ksecdd!GetSecurityUserInfo` at `0x140018778`
- `ksecdd!SspiEncodeStringsAsAuthIdentity` at `0x140018821`
- `ksecdd!SspiEncodeStringsAsAuthIdentity` at `0x140018821`
- `ksecdd!MapSecurityError` at `0x140018832`
- `ksecdd!MapSecurityError` at `0x1400188b7`
- `ksecdd!MapSecurityError` at `0x140018832`
- `ksecdd!MapSecurityError` at `0x1400188b7`
- `ksecdd!SspiCompareAuthIdentities` at `0x1400188a6`
- `ksecdd!SspiCompareAuthIdentities` at `0x1400188a6`
- `ksecdd!SspiFreeAuthIdentity` at `0x14001893f`
- `ksecdd!SspiFreeAuthIdentity` at `0x14001893f`

## pseudocode

```c
__int64 __fastcall CheckCredentials(__int64 a1, __int64 a2, char a3)
{
  __int64 v3; // r14
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE v5; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  WCHAR *v9; // rsi
  WCHAR *v10; // rdi
  char v11; // r15
  size_t Length; // rbx
  size_t v13; // r15
  WCHAR *Pool2; // rax
  WCHAR *v15; // rax
  SECURITY_STATUS v16; // r15d
  NTSTATUS v17; // eax
  SECURITY_STATUS v18; // r12d
  NTSTATUS v19; // eax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+30h] [rbp-10h] BYREF
  BOOLEAN SameSuppliedIdentity; // [rsp+80h] [rbp+40h] BYREF
  BOOLEAN SameSuppliedUser; // [rsp+88h] [rbp+48h] BYREF
  PSecurityUserData UserInformation; // [rsp+98h] [rbp+58h] BYREF

  v3 = *(_QWORD *)(a2 + 104);
  v5 = 0;
  UserInformation = 0;
  ppAuthIdentity = 0;
  SameSuppliedUser = 0;
  SameSuppliedIdentity = 0;
  if ( a1 )
  {
    v5 = *(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(a1 + 8);
    ppAuthIdentity = v5;
  }
  if ( !v3 )
    return 0;
  if ( a3 )
  {
    v8 = *(_QWORD *)(v3 + 56);
    if ( v8 )
    {
      if ( *(_QWORD *)(a1 + 56) != v8 )
        return (unsigned int)-1073741419;
    }
  }
  if ( !*(_QWORD *)(v3 + 8) )
    return 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( v5 )
    goto LABEL_23;
  if ( GetSecurityUserInfo((PLUID)(a2 + 72), 1u, &UserInformation) < 0 )
  {
    v9 = (WCHAR *)&qword_140063918;
    v10 = (WCHAR *)&qword_140063918;
    goto LABEL_17;
  }
  Length = UserInformation->UserName.Length;
  v13 = UserInformation->LogonDomainName.Length;
  Pool2 = (WCHAR *)ExAllocatePool2(64, Length + 2, 1917024338);
  v9 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, UserInformation->UserName.Buffer, Length);
    v15 = (WCHAR *)ExAllocatePool2(64, v13 + 2, 1917024338);
    v10 = v15;
    if ( v15 )
    {
      memmove(v15, UserInformation->LogonDomainName.Buffer, v13);
LABEL_17:
      v16 = SspiEncodeStringsAsAuthIdentity(v9, v10, 0, &ppAuthIdentity);
      v17 = MapSecurityError(v16);
      v7 = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
            (unsigned int)v17,
            v16);
        }
        goto LABEL_38;
      }
      v5 = ppAuthIdentity;
      v11 = 1;
LABEL_23:
      v18 = SspiCompareAuthIdentities(
              v5,
              *(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(v3 + 8),
              &SameSuppliedUser,
              &SameSuppliedIdentity);
      v19 = MapSecurityError(v18);
      v7 = v19;
      if ( v19 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
            (unsigned int)v19,
            v18);
        }
        goto LABEL_35;
      }
      if ( v11 || !*(_QWORD *)(v3 + 24) )
      {
        if ( !SameSuppliedUser )
        {
          v7 = -1073741419;
LABEL_35:
          if ( v11 && ppAuthIdentity )
            SspiFreeAuthIdentity(ppAuthIdentity);
          goto LABEL_38;
        }
      }
      else if ( !SameSuppliedIdentity )
      {
        v7 = -1073741419;
        goto LABEL_38;
      }
      v7 = 0;
      goto LABEL_35;
    }
  }
  v7 = -1073741670;
LABEL_38:
  if ( UserInformation )
    LsaFreeReturnBuffer(UserInformation);
  if ( v9 && v9 != (WCHAR *)&qword_140063918 )
    ExFreePoolWithTag(v9, 0x72437852u);
  if ( v10 && v10 != (WCHAR *)&qword_140063918 )
    ExFreePoolWithTag(v10, 0x72437852u);
  return v7;
}

```

## disassembly

```asm
0x1400186e8  push    rbp
0x1400186ea  push    rbx
0x1400186eb  push    rsi
0x1400186ec  push    rdi
0x1400186ed  push    r12
0x1400186ef  push    r14
0x1400186f1  push    r15
0x1400186f3  mov     rbp, rsp
0x1400186f6  sub     rsp, 40h
0x1400186fa  mov     r14, [rdx+68h]
0x1400186fe  mov     rax, rcx
0x140018701  xor     ecx, ecx
0x140018703  mov     [rbp+UserInformation], 0
0x14001870b  mov     [rbp+ppAuthIdentity], rcx
0x14001870f  mov     r9, rdx
0x140018712  mov     [rbp+SameSuppliedUser], cl
0x140018715  mov     [rbp+SameSuppliedIdentity], cl
0x140018718  test    rax, rax
0x14001871b  jz      short loc_140018725
0x14001871d  mov     rcx, [rax+8]
0x140018721  mov     [rbp+ppAuthIdentity], rcx
0x140018725  test    r14, r14
0x140018728  jnz     short loc_140018731
0x14001872a  xor     ebx, ebx
0x14001872c  jmp     loc_1400189A3
0x140018731  test    r8b, r8b
0x140018734  jz      short loc_14001874F
0x140018736  mov     rdx, [r14+38h]
0x14001873a  test    rdx, rdx
0x14001873d  jz      short loc_14001874F
0x14001873f  cmp     [rax+38h], rdx
0x140018743  jz      short loc_14001874F
0x140018745  mov     ebx, 0C0000195h
0x14001874a  jmp     loc_1400189A3
0x14001874f  cmp     qword ptr [r14+8], 0
0x140018754  jz      short loc_14001872A
0x140018756  xor     esi, esi
0x140018758  lea     r12, qword_140063918
0x14001875f  xor     edi, edi
0x140018761  xor     r15b, r15b
0x140018764  test    rcx, rcx
0x140018767  jnz     loc_14001889A
0x14001876d  lea     rcx, [r9+48h]; LogonId
0x140018771  lea     r8, [rbp+UserInformation]; UserInformation
0x140018775  lea     edx, [rsi+1]; Flags
0x140018778  call    cs:__imp_GetSecurityUserInfo
0x14001877f  nop     dword ptr [rax+rax+00h]
0x140018784  test    eax, eax
0x140018786  js      loc_14001880E
0x14001878c  mov     rax, [rbp+UserInformation]
0x140018790  lea     ecx, [rsi+40h]
0x140018793  mov     r8d, 72437852h
0x140018799  movzx   ebx, word ptr [rax]
0x14001879c  movzx   r15d, word ptr [rax+10h]
0x1400187a1  lea     rdx, [rbx+2]
0x1400187a5  call    cs:__imp_ExAllocatePool2
0x1400187ac  nop     dword ptr [rax+rax+00h]
0x1400187b1  mov     rsi, rax
0x1400187b4  test    rax, rax
0x1400187b7  jnz     short loc_1400187C3
0x1400187b9  mov     ebx, 0C000009Ah
0x1400187be  jmp     loc_140018952
0x1400187c3  mov     rdx, [rbp+UserInformation]
0x1400187c7  mov     r8, rbx; Size
0x1400187ca  mov     rcx, rax; void *
0x1400187cd  mov     rdx, [rdx+8]; Src
0x1400187d1  call    memmove
0x1400187d6  lea     rdx, [r15+2]
0x1400187da  mov     ecx, 40h ; '@'
0x1400187df  mov     r8d, 72437852h
0x1400187e5  call    cs:__imp_ExAllocatePool2
0x1400187ec  nop     dword ptr [rax+rax+00h]
0x1400187f1  mov     rdi, rax
0x1400187f4  test    rax, rax
0x1400187f7  jz      short loc_1400187B9
0x1400187f9  mov     rdx, [rbp+UserInformation]
0x1400187fd  mov     r8, r15; Size
0x140018800  mov     rcx, rax; void *
0x140018803  mov     rdx, [rdx+18h]; Src
0x140018807  call    memmove
0x14001880c  jmp     short loc_140018814
0x14001880e  mov     rsi, r12
0x140018811  mov     rdi, r12
0x140018814  lea     r9, [rbp+ppAuthIdentity]; ppAuthIdentity
0x140018818  xor     r8d, r8d; pszPackedCredentialsString
0x14001881b  mov     rdx, rdi; pszDomainName
0x14001881e  mov     rcx, rsi; pszUserName
0x140018821  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x140018828  nop     dword ptr [rax+rax+00h]
0x14001882d  mov     ecx, eax; SecStatus
0x14001882f  mov     r15d, eax
0x140018832  call    cs:__imp_MapSecurityError
0x140018839  nop     dword ptr [rax+rax+00h]
0x14001883e  mov     ebx, eax
0x140018840  test    eax, eax
0x140018842  jns     short loc_140018893
0x140018844  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001884b  lea     rdx, WPP_GLOBAL_Control
0x140018852  cmp     rcx, rdx
0x140018855  jz      loc_140018952
0x14001885b  mov     edx, [rcx+2Ch]
0x14001885e  test    dl, 1
0x140018861  jz      loc_140018952
0x140018867  cmp     byte ptr [rcx+29h], 1
0x14001886b  jb      loc_140018952
0x140018871  mov     rcx, [rcx+18h]
0x140018875  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14001887c  mov     edx, 0Ah
0x140018881  mov     [rsp+40h+var_20], r15d
0x140018886  mov     r9d, eax
0x140018889  call    WPP_SF_Dd
0x14001888e  jmp     loc_140018952
0x140018893  mov     rcx, [rbp+ppAuthIdentity]; AuthIdentity1
0x140018897  mov     r15b, 1
0x14001889a  mov     rdx, [r14+8]; AuthIdentity2
0x14001889e  lea     r9, [rbp+SameSuppliedIdentity]; SameSuppliedIdentity
0x1400188a2  lea     r8, [rbp+SameSuppliedUser]; SameSuppliedUser
0x1400188a6  call    cs:__imp_SspiCompareAuthIdentities
0x1400188ad  nop     dword ptr [rax+rax+00h]
0x1400188b2  mov     ecx, eax; SecStatus
0x1400188b4  mov     r12d, eax
0x1400188b7  call    cs:__imp_MapSecurityError
0x1400188be  nop     dword ptr [rax+rax+00h]
0x1400188c3  mov     ebx, eax
0x1400188c5  test    eax, eax
0x1400188c7  jns     short loc_140018909
0x1400188c9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400188d0  lea     rdx, WPP_GLOBAL_Control
0x1400188d7  cmp     rcx, rdx
0x1400188da  jz      short loc_140018931
0x1400188dc  mov     edx, [rcx+2Ch]
0x1400188df  test    dl, 1
0x1400188e2  jz      short loc_140018931
0x1400188e4  cmp     byte ptr [rcx+29h], 1
0x1400188e8  jb      short loc_140018931
0x1400188ea  mov     rcx, [rcx+18h]
0x1400188ee  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x1400188f5  mov     edx, 0Bh
0x1400188fa  mov     [rsp+40h+var_20], r12d
0x1400188ff  mov     r9d, eax
0x140018902  call    WPP_SF_Dd
0x140018907  jmp     short loc_140018931
0x140018909  test    r15b, r15b
0x14001890c  jnz     short loc_140018922
0x14001890e  cmp     qword ptr [r14+18h], 0
0x140018913  jz      short loc_140018922
0x140018915  cmp     [rbp+SameSuppliedIdentity], r15b
0x140018919  jnz     short loc_14001892F
0x14001891b  mov     ebx, 0C0000195h
0x140018920  jmp     short loc_14001894B
0x140018922  cmp     [rbp+SameSuppliedUser], 0
0x140018926  jnz     short loc_14001892F
0x140018928  mov     ebx, 0C0000195h
0x14001892d  jmp     short loc_140018931
0x14001892f  xor     ebx, ebx
0x140018931  test    r15b, r15b
0x140018934  jz      short loc_14001894B
0x140018936  mov     rcx, [rbp+ppAuthIdentity]; AuthData
0x14001893a  test    rcx, rcx
0x14001893d  jz      short loc_14001894B
0x14001893f  call    cs:__imp_SspiFreeAuthIdentity
0x140018946  nop     dword ptr [rax+rax+00h]
0x14001894b  lea     r12, qword_140063918
0x140018952  mov     rcx, [rbp+UserInformation]; Buffer
0x140018956  test    rcx, rcx
0x140018959  jz      short loc_140018967
0x14001895b  call    cs:__imp_LsaFreeReturnBuffer
0x140018962  nop     dword ptr [rax+rax+00h]
0x140018967  test    rsi, rsi
0x14001896a  jz      short loc_140018985
0x14001896c  cmp     rsi, r12
0x14001896f  jz      short loc_140018985
0x140018971  mov     edx, 72437852h; Tag
0x140018976  mov     rcx, rsi; P
0x140018979  call    cs:__imp_ExFreePoolWithTag
0x140018980  nop     dword ptr [rax+rax+00h]
0x140018985  test    rdi, rdi
0x140018988  jz      short loc_1400189A3
0x14001898a  cmp     rdi, r12
0x14001898d  jz      short loc_1400189A3
0x14001898f  mov     edx, 72437852h; Tag
0x140018994  mov     rcx, rdi; P
0x140018997  call    cs:__imp_ExFreePoolWithTag
0x14001899e  nop     dword ptr [rax+rax+00h]
0x1400189a3  mov     eax, ebx
0x1400189a5  add     rsp, 40h
0x1400189a9  pop     r15
0x1400189ab  pop     r14
0x1400189ad  pop     r12
0x1400189af  pop     rdi
0x1400189b0  pop     rsi
0x1400189b1  pop     rbx
0x1400189b2  pop     rbp
0x1400189b3  retn
```
