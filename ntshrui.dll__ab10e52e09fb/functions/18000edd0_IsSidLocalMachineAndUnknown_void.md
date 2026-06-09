# IsSidLocalMachineAndUnknown(void *)

- ea: `0x18000edd0`
- end: `0x18000f06f`
- name: `?IsSidLocalMachineAndUnknown@@YAHPEAX@Z`
- size: `671`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d380`
- `0x18000dd60`
- `0x18000e8b0`

## callees

- `0x18000edd0`
- `0x18000f078`
- `0x180011c80`
- `0x18001bf88`
- `0x1800254e0`
- `0x18002596c`
- `0x180025b70`
- `0x180025bd8`
- `0x180025d64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000efc0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000efc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f053`
- `KERNEL32!GetComputerNameW` at `0x18000ef5d`
- `KERNEL32!GetComputerNameW` at `0x18000ef5d`
- `SHLWAPI!StrRChrW` at `0x18000ee6d`
- `SHLWAPI!StrRChrW` at `0x18000ee6d`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000ee83`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000ee83`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ee57`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f038`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ee57`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f038`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000eef2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18000eef2`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000ef96`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000f023`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000ef96`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18000f023`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsSidLocalMachineAndUnknown(PSID Sid)
{
  unsigned int v2; // r14d
  const WCHAR *v3; // rbx
  BOOL v4; // edi
  PWSTR v5; // rax
  HLOCAL v7; // rbx
  unsigned __int64 v8; // rax
  WCHAR *v9; // rdi
  DWORD cbSid; // [rsp+30h] [rbp-50h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-48h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR v14; // [rsp+48h] [rbp-38h] BYREF
  HLOCAL v15; // [rsp+50h] [rbp-30h] BYREF
  WCHAR Buffer[16]; // [rsp+58h] [rbp-28h] BYREF

  v2 = 0;
  if ( dword_1800972D8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800972D8, 4);
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
        v7 = LocalAlloc(0x40u, cbSid);
        v15 = v7;
        if ( v7 )
        {
          v8 = 2LL * cchReferencedDomainName;
          if ( !is_mul_ok(cchReferencedDomainName, 2u) )
            v8 = -1;
          v9 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
          if ( v9 )
          {
            if ( LookupAccountNameLocalW(Buffer, v7, &cbSid, v9, &cchReferencedDomainName, (PSID_NAME_USE)&cchName) )
            {
              v14 = 0;
              ConvertSidToStringSidW(v7, &v14);
              if ( _InterlockedCompareExchange64((volatile signed __int64 *)&pszStr1, (signed __int64)v14, 0) )
                LocalFree(v14);
            }
          }
          operator delete(v9);
        }
        CLocalMemPtr<void>::~CLocalMemPtr<void>(&v15);
      }
    }
  }
  v3 = pszStr1;
  if ( pszStr1 )
  {
    v4 = 0;
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v5 = StrRChrW(StringSid, 0, 0x2Du);
      if ( v5 )
      {
        *v5 = 0;
        v4 = StrCmpICW(v3, StringSid) == 0;
      }
    }
    CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyLocalMem>>::~CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyLocalMem>>(&StringSid);
    if ( v4 )
    {
      cchName = 0;
      cbSid = 0;
      LODWORD(StringSid) = 0;
      if ( !LookupAccountSidLocalW(Sid, 0, &cchName, 0, &cbSid, (PSID_NAME_USE)&StringSid) && !cchName && !cbSid )
        return 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000edd0  mov     [rsp-28h+arg_8], rbx
0x18000edd5  mov     [rsp-28h+arg_10], rsi
0x18000edda  push    rbp
0x18000eddb  push    rdi
0x18000eddc  push    r12
0x18000edde  push    r14
0x18000ede0  push    r15
0x18000ede2  mov     rbp, rsp
0x18000ede5  sub     rsp, 80h
0x18000edec  mov     rax, cs:__security_cookie
0x18000edf3  xor     rax, rsp
0x18000edf6  mov     [rbp+var_8], rax
0x18000edfa  mov     rsi, rcx
0x18000edfd  xor     r15d, r15d
0x18000ee00  mov     r14d, r15d
0x18000ee03  mov     ecx, cs:_tls_index
0x18000ee09  mov     rax, gs:58h
0x18000ee12  mov     edx, 4
0x18000ee17  mov     rax, [rax+rcx*8]
0x18000ee1b  mov     ecx, [rdx+rax]
0x18000ee1e  cmp     cs:dword_1800972D8, ecx
0x18000ee24  jg      loc_18000EF0A
0x18000ee2a  mov     r12d, 1
0x18000ee30  cmp     cs:dword_180096B74, r14d
0x18000ee37  jz      loc_18000EF47
0x18000ee3d  mov     rbx, cs:pszStr1
0x18000ee44  test    rbx, rbx
0x18000ee47  jz      short loc_18000EE9D
0x18000ee49  mov     edi, r15d
0x18000ee4c  mov     [rbp+StringSid], r15
0x18000ee50  lea     rdx, [rbp+StringSid]; StringSid
0x18000ee54  mov     rcx, rsi; Sid
0x18000ee57  call    cs:__imp_ConvertSidToStringSidW
0x18000ee5d  test    eax, eax
0x18000ee5f  jz      short loc_18000EE8F
0x18000ee61  xor     edx, edx; pszEnd
0x18000ee63  mov     r8d, 2Dh ; '-'; wMatch
0x18000ee69  mov     rcx, [rbp+StringSid]; pszStart
0x18000ee6d  call    cs:__imp_StrRChrW
0x18000ee73  test    rax, rax
0x18000ee76  jz      short loc_18000EE8F
0x18000ee78  mov     [rax], r15w
0x18000ee7c  mov     rdx, [rbp+StringSid]; pszStr2
0x18000ee80  mov     rcx, rbx; pszStr1
0x18000ee83  call    cs:__imp_StrCmpICW
0x18000ee89  test    eax, eax
0x18000ee8b  cmovz   edi, r12d
0x18000ee8f  lea     rcx, [rbp+StringSid]
0x18000ee93  call    ??1?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyLocalMem@@@@@@QEAA@XZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyLocalMem>>::~CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyLocalMem>>(void)
0x18000ee98  nop
0x18000ee99  test    edi, edi
0x18000ee9b  jnz     short loc_18000EEC8
0x18000ee9d  mov     eax, r14d
0x18000eea0  mov     rcx, [rbp+var_8]
0x18000eea4  xor     rcx, rsp; StackCookie
0x18000eea7  call    __security_check_cookie
0x18000eeac  lea     r11, [rsp+80h+var_s0]
0x18000eeb4  mov     rbx, [r11+38h]
0x18000eeb8  mov     rsi, [r11+40h]
0x18000eebc  mov     rsp, r11
0x18000eebf  pop     r15
0x18000eec1  pop     r14
0x18000eec3  pop     r12
0x18000eec5  pop     rdi
0x18000eec6  pop     rbp
0x18000eec7  retn
0x18000eec8  mov     [rbp+cchName], r15d
0x18000eecc  mov     [rbp+cbSid], r15d
0x18000eed0  mov     dword ptr [rbp+StringSid], r15d
0x18000eed4  lea     rax, [rbp+StringSid]
0x18000eed8  mov     [rsp+80h+peUse], rax; peUse
0x18000eedd  lea     rax, [rbp+cbSid]
0x18000eee1  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000eee6  xor     r9d, r9d; ReferencedDomainName
0x18000eee9  lea     r8, [rbp+cchName]; cchName
0x18000eeed  xor     edx, edx; Name
0x18000eeef  mov     rcx, rsi; Sid
0x18000eef2  call    cs:__imp_LookupAccountSidLocalW
0x18000eef8  test    eax, eax
0x18000eefa  jnz     short loc_18000EE9D
0x18000eefc  cmp     [rbp+cchName], eax
0x18000eeff  jnz     short loc_18000EE9D
0x18000ef01  cmp     [rbp+cbSid], eax
0x18000ef04  cmovz   r14d, r12d
0x18000ef08  jmp     short loc_18000EE9D
0x18000ef0a  lea     rcx, dword_1800972D8
0x18000ef11  call    _Init_thread_header
0x18000ef16  cmp     cs:dword_1800972D8, 0FFFFFFFFh
0x18000ef1d  jnz     loc_18000EE2A
0x18000ef23  mov     cs:pszStr1, r15
0x18000ef2a  lea     rcx, _GetMachineStringSid____2____dynamic_atexit_destructor_for__s_spszMachineSid__; void (__cdecl *)()
0x18000ef31  call    atexit
0x18000ef36  lea     rcx, dword_1800972D8
0x18000ef3d  call    _Init_thread_footer
0x18000ef42  jmp     loc_18000EE2A
0x18000ef47  mov     cs:dword_180096B74, r12d
0x18000ef4e  mov     dword ptr [rbp+StringSid], 10h
0x18000ef55  lea     rdx, [rbp+StringSid]; nSize
0x18000ef59  lea     rcx, [rbp+Buffer]; lpBuffer
0x18000ef5d  call    cs:__imp_GetComputerNameW
0x18000ef63  test    eax, eax
0x18000ef65  jz      loc_18000EE3D
0x18000ef6b  mov     [rbp+cbSid], r15d
0x18000ef6f  mov     [rbp+var_48], r15d
0x18000ef73  mov     [rbp+cchName], r15d
0x18000ef77  lea     rax, [rbp+cchName]
0x18000ef7b  mov     [rsp+80h+peUse], rax; peUse
0x18000ef80  lea     rax, [rbp+var_48]
0x18000ef84  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000ef89  xor     r9d, r9d; ReferencedDomainName
0x18000ef8c  lea     r8, [rbp+cbSid]; cbSid
0x18000ef90  xor     edx, edx; Sid
0x18000ef92  lea     rcx, [rbp+Buffer]; lpAccountName
0x18000ef96  call    cs:__imp_LookupAccountNameLocalW
0x18000ef9c  test    eax, eax
0x18000ef9e  jnz     loc_18000EE3D
0x18000efa4  mov     eax, [rbp+cbSid]
0x18000efa7  test    eax, eax
0x18000efa9  jz      loc_18000EE3D
0x18000efaf  cmp     [rbp+var_48], r14d
0x18000efb3  jz      loc_18000EE3D
0x18000efb9  mov     edx, eax; uBytes
0x18000efbb  mov     ecx, 40h ; '@'; uFlags
0x18000efc0  call    cs:__imp_LocalAlloc
0x18000efc6  mov     rbx, rax
0x18000efc9  mov     [rbp+var_30], rax
0x18000efcd  test    rax, rax
0x18000efd0  jz      loc_18000F061
0x18000efd6  mov     ecx, [rbp+var_48]
0x18000efd9  mov     eax, 2
0x18000efde  mul     rcx
0x18000efe1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000efe8  cmovb   rax, rcx
0x18000efec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eff3  mov     rcx, rax; unsigned __int64
0x18000eff6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000effb  mov     rdi, rax
0x18000effe  test    rax, rax
0x18000f001  jz      short loc_18000F059
0x18000f003  lea     rax, [rbp+cchName]
0x18000f007  mov     [rsp+80h+peUse], rax; peUse
0x18000f00c  lea     rax, [rbp+var_48]
0x18000f010  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000f015  mov     r9, rdi; ReferencedDomainName
0x18000f018  lea     r8, [rbp+cbSid]; cbSid
0x18000f01c  mov     rdx, rbx; Sid
0x18000f01f  lea     rcx, [rbp+Buffer]; lpAccountName
0x18000f023  call    cs:__imp_LookupAccountNameLocalW
0x18000f029  test    eax, eax
0x18000f02b  jz      short loc_18000F059
0x18000f02d  mov     [rbp+var_38], r15
0x18000f031  lea     rdx, [rbp+var_38]; StringSid
0x18000f035  mov     rcx, rbx; Sid
0x18000f038  call    cs:__imp_ConvertSidToStringSidW
0x18000f03e  mov     rcx, [rbp+var_38]
0x18000f042  xor     eax, eax
0x18000f044  lock cmpxchg cs:pszStr1, rcx
0x18000f04d  jz      short loc_18000F059
0x18000f04f  mov     rcx, [rbp+var_38]; hMem
0x18000f053  call    cs:__imp_LocalFree
0x18000f059  mov     rcx, rdi; lpMem
0x18000f05c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f061  lea     rcx, [rbp+var_30]
0x18000f065  call    ??1?$CLocalMemPtr@X@@QEAA@XZ; CLocalMemPtr<void>::~CLocalMemPtr<void>(void)
0x18000f06a  jmp     loc_18000EE3D
```
