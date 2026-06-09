# CFolderAclEngine::_s_IsSystemAce(CAce *,int)

- ea: `0x1800127e0`
- end: `0x180012b13`
- name: `?_s_IsSystemAce@CFolderAclEngine@@CAHPEAVCAce@@H@Z`
- size: `819`
- prototype: `__int64 __fastcall(struct CAce *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000bea0`
- `0x18000c6f0`

## callees

- `0x180011c80`
- `0x1800127e0`
- `0x18001bf88`
- `0x1800254e0`
- `0x18002596c`
- `0x180025b70`
- `0x180025bd8`
- `0x180025d64`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180012914`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180012914`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800128dc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800128dc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800128ec`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800128ec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800128b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800128b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012af7`
- `KERNEL32!GetComputerNameW` at `0x180012a01`
- `KERNEL32!GetComputerNameW` at `0x180012a01`
- `SHLWAPI!StrRChrW` at `0x180012889`
- `SHLWAPI!StrRChrW` at `0x180012889`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001289f`
- `SHLWAPI!__imp_StrCmpICW` at `0x18001289f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012873`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012adc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012873`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012adc`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180012977`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180012977`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180012a3a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180012ac7`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180012a3a`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180012ac7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall CFolderAclEngine::_s_IsSystemAce(struct CAce *a1, __int64 a2)
{
  int v2; // r12d
  void *v4; // r14
  const WCHAR *v5; // rbx
  BOOL v6; // edi
  PWSTR v7; // rax
  LPWSTR v8; // rcx
  int v9; // eax
  BOOL v10; // edi
  unsigned int i; // ebx
  BOOL result; // eax
  char v13; // al
  HLOCAL v14; // rbx
  unsigned __int64 v15; // rax
  WCHAR *v16; // rdi
  DWORD cbSid; // [rsp+30h] [rbp-39h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-35h] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-31h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-29h] BYREF
  LPWSTR v21; // [rsp+48h] [rbp-21h] BYREF
  HLOCAL v22; // [rsp+50h] [rbp-19h] BYREF
  WCHAR Buffer[16]; // [rsp+58h] [rbp-11h] BYREF

  v2 = a2;
  if ( (*((_BYTE *)a1 + 28) & 1) == 0 )
    return 1;
  v4 = (void *)*((_QWORD *)a1 + 1);
  if ( dword_1800972D8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800972D8, a2);
    if ( dword_1800972D8 == -1 )
    {
      pszStr1 = 0;
      atexit(GetMachineStringSid_::_2_::_dynamic_atexit_destructor_for__s_spszMachineSid__);
      Init_thread_footer(&dword_1800972D8);
    }
  }
  if ( !dword_180096B74 )
  {
    dword_180096B74 = 1;
    LODWORD(StringSid) = 16;
    if ( GetComputerNameW(Buffer, (LPDWORD)&StringSid) )
    {
      cbSid = 0;
      cchReferencedDomainName = 0;
      cchName = 0;
      if ( !LookupAccountNameLocalW(Buffer, 0, &cbSid, 0, &cchReferencedDomainName, (PSID_NAME_USE)&cchName)
        && cbSid
        && cchReferencedDomainName )
      {
        v14 = LocalAlloc(0x40u, cbSid);
        v22 = v14;
        if ( v14 )
        {
          v15 = 2LL * cchReferencedDomainName;
          if ( !is_mul_ok(cchReferencedDomainName, 2u) )
            v15 = -1;
          v16 = (WCHAR *)operator new[](v15, (const struct std::nothrow_t *)std::nothrow);
          if ( v16 )
          {
            if ( LookupAccountNameLocalW(Buffer, v14, &cbSid, v16, &cchReferencedDomainName, (PSID_NAME_USE)&cchName) )
            {
              v21 = 0;
              ConvertSidToStringSidW(v14, &v21);
              if ( _InterlockedCompareExchange64((volatile signed __int64 *)&pszStr1, (signed __int64)v21, 0) )
                LocalFree(v21);
            }
          }
          operator delete(v16);
        }
        CLocalMemPtr<void>::~CLocalMemPtr<void>(&v22);
      }
    }
  }
  v5 = pszStr1;
  if ( pszStr1 )
  {
    v6 = 0;
    StringSid = 0;
    if ( ConvertSidToStringSidW(v4, &StringSid) )
    {
      v7 = StrRChrW(StringSid, 0, 0x2Du);
      if ( v7 )
      {
        *v7 = 0;
        v6 = StrCmpICW(v5, StringSid) == 0;
      }
    }
    v8 = StringSid;
    StringSid = 0;
    LocalFree(v8);
    if ( v6 )
    {
      cchName = 0;
      cbSid = 0;
      LODWORD(StringSid) = 0;
      if ( !LookupAccountSidLocalW(v4, 0, &cchName, 0, &cbSid, (PSID_NAME_USE)&StringSid) && !cchName && !cbSid )
        return 1;
    }
  }
  if ( v2 )
  {
    v9 = *((_DWORD *)a1 + 7);
    if ( (v9 & 0x20) == 0 && (v9 & 1) != 0 )
    {
      v13 = *((_BYTE *)a1 + 1);
      if ( !v13 || v13 == 9 )
        return 1;
    }
  }
  v10 = 0;
  if ( GetSidSubAuthorityCount(v4) )
  {
    if ( *GetSidSubAuthority(v4, 0) == 80 )
      return 1;
  }
  for ( i = 0; i < 2; ++i )
  {
    result = IsWellKnownSid(*((PSID *)a1 + 1), *((WELL_KNOWN_SID_TYPE *)&rgSystemSids + i));
    v10 = result;
    if ( result )
      return result;
  }
  return v10;
}

```

## disassembly

```asm
0x1800127e0  push    rbp
0x1800127e2  push    rbx
0x1800127e3  push    rsi
0x1800127e4  push    rdi
0x1800127e5  push    r12
0x1800127e7  push    r13
0x1800127e9  push    r14
0x1800127eb  push    r15
0x1800127ed  lea     rbp, [rsp-1Fh]
0x1800127f2  sub     rsp, 88h
0x1800127f9  mov     rax, cs:__security_cookie
0x180012800  xor     rax, rsp
0x180012803  mov     [rbp+57h+var_48], rax
0x180012807  mov     r12d, edx
0x18001280a  mov     rsi, rcx
0x18001280d  test    byte ptr [rcx+1Ch], 1
0x180012811  jz      loc_180012942
0x180012817  mov     r14, [rcx+8]
0x18001281b  mov     r8d, cs:_tls_index
0x180012822  mov     rax, gs:58h
0x18001282b  mov     ecx, 4
0x180012830  mov     rax, [rax+r8*8]
0x180012834  xor     r13d, r13d
0x180012837  mov     eax, [rcx+rax]
0x18001283a  cmp     cs:dword_1800972D8, eax
0x180012840  jg      loc_1800129AE
0x180012846  mov     r15d, 1
0x18001284c  cmp     cs:dword_180096B74, r13d
0x180012853  jz      loc_1800129EB
0x180012859  mov     rbx, cs:pszStr1
0x180012860  test    rbx, rbx
0x180012863  jz      short loc_1800128C2
0x180012865  mov     edi, r13d
0x180012868  mov     [rbp+57h+StringSid], r13
0x18001286c  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180012870  mov     rcx, r14; Sid
0x180012873  call    cs:__imp_ConvertSidToStringSidW
0x180012879  test    eax, eax
0x18001287b  jz      short loc_1800128AB
0x18001287d  xor     edx, edx; pszEnd
0x18001287f  mov     r8d, 2Dh ; '-'; wMatch
0x180012885  mov     rcx, [rbp+57h+StringSid]; pszStart
0x180012889  call    cs:__imp_StrRChrW
0x18001288f  test    rax, rax
0x180012892  jz      short loc_1800128AB
0x180012894  mov     [rax], r13w
0x180012898  mov     rdx, [rbp+57h+StringSid]; pszStr2
0x18001289c  mov     rcx, rbx; pszStr1
0x18001289f  call    cs:__imp_StrCmpICW
0x1800128a5  test    eax, eax
0x1800128a7  cmovz   edi, r15d
0x1800128ab  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800128af  mov     [rbp+57h+StringSid], r13
0x1800128b3  call    cs:__imp_LocalFree
0x1800128b9  nop
0x1800128ba  test    edi, edi
0x1800128bc  jnz     loc_18001294D
0x1800128c2  test    r12d, r12d
0x1800128c5  jz      short loc_1800128D6
0x1800128c7  mov     eax, [rsi+1Ch]
0x1800128ca  test    al, 20h
0x1800128cc  jnz     short loc_1800128D6
0x1800128ce  test    al, 1
0x1800128d0  jnz     loc_18001299C
0x1800128d6  mov     edi, r13d
0x1800128d9  mov     rcx, r14; pSid
0x1800128dc  call    cs:__imp_GetSidSubAuthorityCount
0x1800128e2  test    rax, rax
0x1800128e5  jz      short loc_1800128F7
0x1800128e7  xor     edx, edx; nSubAuthority
0x1800128e9  mov     rcx, r14; pSid
0x1800128ec  call    cs:__imp_GetSidSubAuthority
0x1800128f2  cmp     dword ptr [rax], 50h ; 'P'
0x1800128f5  jz      short loc_180012948
0x1800128f7  mov     ebx, r13d
0x1800128fa  lea     r14, ?rgSystemSids@@3PAW4WELL_KNOWN_SID_TYPE@@A; WELL_KNOWN_SID_TYPE near * rgSystemSids
0x180012901  cmp     ebx, 2
0x180012904  jnb     loc_180012998
0x18001290a  mov     edx, ebx
0x18001290c  mov     edx, [r14+rdx*4]; WellKnownSidType
0x180012910  mov     rcx, [rsi+8]; pSid
0x180012914  call    cs:__imp_IsWellKnownSid
0x18001291a  mov     edi, eax
0x18001291c  inc     ebx
0x18001291e  test    eax, eax
0x180012920  jz      short loc_180012901
0x180012922  mov     rcx, [rbp+57h+var_48]
0x180012926  xor     rcx, rsp; StackCookie
0x180012929  call    __security_check_cookie
0x18001292e  add     rsp, 88h
0x180012935  pop     r15
0x180012937  pop     r14
0x180012939  pop     r13
0x18001293b  pop     r12
0x18001293d  pop     rdi
0x18001293e  pop     rsi
0x18001293f  pop     rbx
0x180012940  pop     rbp
0x180012941  retn
0x180012942  mov     r15d, 1
0x180012948  mov     eax, r15d
0x18001294b  jmp     short loc_180012922
0x18001294d  mov     [rbp+57h+cchName], r13d
0x180012951  mov     [rbp+57h+cbSid], r13d
0x180012955  mov     dword ptr [rbp+57h+StringSid], r13d
0x180012959  lea     rax, [rbp+57h+StringSid]
0x18001295d  mov     [rsp+0C0h+peUse], rax; peUse
0x180012962  lea     rax, [rbp+57h+cbSid]
0x180012966  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001296b  xor     r9d, r9d; ReferencedDomainName
0x18001296e  lea     r8, [rbp+57h+cchName]; cchName
0x180012972  xor     edx, edx; Name
0x180012974  mov     rcx, r14; Sid
0x180012977  call    cs:__imp_LookupAccountSidLocalW
0x18001297d  test    eax, eax
0x18001297f  jnz     loc_1800128C2
0x180012985  cmp     [rbp+57h+cchName], eax
0x180012988  jnz     loc_1800128C2
0x18001298e  cmp     [rbp+57h+cbSid], eax
0x180012991  jz      short loc_180012948
0x180012993  jmp     loc_1800128C2
0x180012998  mov     eax, edi
0x18001299a  jmp     short loc_180012922
0x18001299c  movzx   eax, byte ptr [rsi+1]
0x1800129a0  test    al, al
0x1800129a2  jz      short loc_180012948
0x1800129a4  cmp     al, 9
0x1800129a6  jnz     loc_1800128D6
0x1800129ac  jmp     short loc_180012948
0x1800129ae  lea     rcx, dword_1800972D8
0x1800129b5  call    _Init_thread_header
0x1800129ba  cmp     cs:dword_1800972D8, 0FFFFFFFFh
0x1800129c1  jnz     loc_180012846
0x1800129c7  mov     cs:pszStr1, r13
0x1800129ce  lea     rcx, _GetMachineStringSid____2____dynamic_atexit_destructor_for__s_spszMachineSid__; void (__cdecl *)()
0x1800129d5  call    atexit
0x1800129da  lea     rcx, dword_1800972D8
0x1800129e1  call    _Init_thread_footer
0x1800129e6  jmp     loc_180012846
0x1800129eb  mov     cs:dword_180096B74, r15d
0x1800129f2  mov     dword ptr [rbp+57h+StringSid], 10h
0x1800129f9  lea     rdx, [rbp+57h+StringSid]; nSize
0x1800129fd  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x180012a01  call    cs:__imp_GetComputerNameW
0x180012a07  test    eax, eax
0x180012a09  jz      loc_180012859
0x180012a0f  mov     [rbp+57h+cbSid], r13d
0x180012a13  mov     [rbp+57h+var_88], r13d
0x180012a17  mov     [rbp+57h+cchName], r13d
0x180012a1b  lea     rax, [rbp+57h+cchName]
0x180012a1f  mov     [rsp+0C0h+peUse], rax; peUse
0x180012a24  lea     rax, [rbp+57h+var_88]
0x180012a28  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180012a2d  xor     r9d, r9d; ReferencedDomainName
0x180012a30  lea     r8, [rbp+57h+cbSid]; cbSid
0x180012a34  xor     edx, edx; Sid
0x180012a36  lea     rcx, [rbp+57h+Buffer]; lpAccountName
0x180012a3a  call    cs:__imp_LookupAccountNameLocalW
0x180012a40  test    eax, eax
0x180012a42  jnz     loc_180012859
0x180012a48  mov     eax, [rbp+57h+cbSid]
0x180012a4b  test    eax, eax
0x180012a4d  jz      loc_180012859
0x180012a53  cmp     [rbp+57h+var_88], r13d
0x180012a57  jz      loc_180012859
0x180012a5d  mov     edx, eax; uBytes
0x180012a5f  mov     ecx, 40h ; '@'; uFlags
0x180012a64  call    cs:__imp_LocalAlloc
0x180012a6a  mov     rbx, rax
0x180012a6d  mov     [rbp+57h+var_70], rax
0x180012a71  test    rax, rax
0x180012a74  jz      loc_180012B05
0x180012a7a  mov     ecx, [rbp+57h+var_88]
0x180012a7d  mov     eax, 2
0x180012a82  mul     rcx
0x180012a85  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012a8c  cmovb   rax, rcx
0x180012a90  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012a97  mov     rcx, rax; unsigned __int64
0x180012a9a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012a9f  mov     rdi, rax
0x180012aa2  test    rax, rax
0x180012aa5  jz      short loc_180012AFD
0x180012aa7  lea     rax, [rbp+57h+cchName]
0x180012aab  mov     [rsp+0C0h+peUse], rax; peUse
0x180012ab0  lea     rax, [rbp+57h+var_88]
0x180012ab4  mov     [rsp+0C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180012ab9  mov     r9, rdi; ReferencedDomainName
0x180012abc  lea     r8, [rbp+57h+cbSid]; cbSid
0x180012ac0  mov     rdx, rbx; Sid
0x180012ac3  lea     rcx, [rbp+57h+Buffer]; lpAccountName
0x180012ac7  call    cs:__imp_LookupAccountNameLocalW
0x180012acd  test    eax, eax
0x180012acf  jz      short loc_180012AFD
0x180012ad1  mov     [rbp+57h+var_78], r13
0x180012ad5  lea     rdx, [rbp+57h+var_78]; StringSid
0x180012ad9  mov     rcx, rbx; Sid
0x180012adc  call    cs:__imp_ConvertSidToStringSidW
0x180012ae2  mov     rcx, [rbp+57h+var_78]
0x180012ae6  xor     eax, eax
0x180012ae8  lock cmpxchg cs:pszStr1, rcx
0x180012af1  jz      short loc_180012AFD
0x180012af3  mov     rcx, [rbp+57h+var_78]; hMem
0x180012af7  call    cs:__imp_LocalFree
0x180012afd  mov     rcx, rdi; lpMem
0x180012b00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b05  lea     rcx, [rbp+57h+var_70]
0x180012b09  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x180012b0e  jmp     loc_180012859
```
