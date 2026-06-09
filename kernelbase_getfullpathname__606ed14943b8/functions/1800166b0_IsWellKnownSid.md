# IsWellKnownSid

- ea: `0x1800166b0`
- end: `0x1800169b7`
- name: `IsWellKnownSid`
- size: `775`
- prototype: `BOOL __stdcall(PSID pSid, WELL_KNOWN_SID_TYPE WellKnownSidType)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800169c0`

## callees

- `0x1800166b0`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180016756`
- `ntdll!RtlSubAuthoritySid` at `0x1800167d3`
- `ntdll!RtlSubAuthoritySid` at `0x18001688c`
- `ntdll!RtlSubAuthoritySid` at `0x180199b86`
- `ntdll!RtlSubAuthoritySid` at `0x180199ba3`
- `ntdll!RtlSubAuthoritySid` at `0x180199bc0`
- `ntdll!RtlSubAuthoritySid` at `0x180199bdd`
- `ntdll!RtlSubAuthoritySid` at `0x180199bfa`
- `ntdll!RtlSubAuthoritySid` at `0x180016756`
- `ntdll!RtlSubAuthoritySid` at `0x1800167d3`
- `ntdll!RtlSubAuthoritySid` at `0x18001688c`
- `ntdll!RtlSubAuthoritySid` at `0x180199b86`
- `ntdll!RtlSubAuthoritySid` at `0x180199ba3`
- `ntdll!RtlSubAuthoritySid` at `0x180199bc0`
- `ntdll!RtlSubAuthoritySid` at `0x180199bdd`
- `ntdll!RtlSubAuthoritySid` at `0x180199bfa`
- `ntdll!RtlSetLastWin32Error` at `0x1800166d5`
- `ntdll!RtlSetLastWin32Error` at `0x1800166d5`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001670e`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001670e`
- `ntdll!RtlValidSid` at `0x1800166bf`
- `ntdll!RtlValidSid` at `0x1800166bf`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800166e4`
- `ntdll!RtlIdentifierAuthoritySid` at `0x1800166e4`

## pseudocode

```c
BOOL __stdcall IsWellKnownSid(PSID pSid, WELL_KNOWN_SID_TYPE WellKnownSidType)
{
  PSID_IDENTIFIER_AUTHORITY v4; // rbx
  int v5; // ebp
  int v6; // ecx
  ULONG v7; // ecx
  BOOL v8; // r14d
  __int64 *v10; // rdi
  unsigned int v11; // ebx
  ULONG v12; // r8d
  __int64 j; // rax
  int v14; // eax
  __int64 i; // rdx
  __int64 v16; // r8
  int v17; // ecx
  int v18; // ecx
  ULONG v19; // ecx
  int v20; // ecx
  int v21; // ecx

  if ( RtlValidSid(pSid) )
  {
    RtlSetLastWin32Error(0);
    v4 = RtlIdentifierAuthoritySid(pSid);
    if ( v4 )
    {
      v5 = *RtlSubAuthorityCountSid(pSid);
      if ( !(_BYTE)v5 )
      {
        v21 = *(_DWORD *)v4->Value;
        if ( !*(_DWORD *)v4->Value )
          v21 = *(unsigned __int16 *)&v4->Value[4] - 1280;
        if ( !v21 )
        {
          v14 = 7;
          v8 = 1;
          goto LABEL_24;
        }
        return 0;
      }
      if ( (_BYTE)v5 == 1 )
      {
        for ( i = 0; (unsigned int)i < 0xD; i = (unsigned int)(i + 1) )
        {
          v16 = 3 * i;
          v17 = *(_DWORD *)v4->Value - LODWORD(KnownAuthoritiesAndDomains[3 * i]);
          if ( *(_DWORD *)v4->Value == LODWORD(KnownAuthoritiesAndDomains[3 * i]) )
            v17 = *(unsigned __int16 *)&v4->Value[4] - WORD2(KnownAuthoritiesAndDomains[v16]);
          if ( !v17 )
          {
            _mm_lfence();
            v10 = (__int64 *)KnownAuthoritiesAndDomains[v16 + 1];
            if ( v10 )
            {
              v11 = KnownAuthoritiesAndDomains[v16 + 2];
              goto LABEL_18;
            }
            break;
          }
        }
        v20 = *(_DWORD *)v4->Value;
        if ( !*(_DWORD *)v4->Value )
          v20 = *(unsigned __int16 *)&v4->Value[4] - 4096;
        if ( v20 )
          return 0;
        v10 = SecurityMandatorySids;
        v11 = 6;
        if ( !SecurityMandatorySids )
          return 0;
      }
      else
      {
        v6 = *(_DWORD *)v4->Value;
        if ( !*(_DWORD *)v4->Value )
          v6 = *(unsigned __int16 *)&v4->Value[4] - 1280;
        if ( v6 )
        {
          v18 = *(_DWORD *)v4->Value;
          if ( !*(_DWORD *)v4->Value )
            v18 = *(unsigned __int16 *)&v4->Value[4] - 3840;
          if ( v18 )
            return 0;
          v19 = *RtlSubAuthoritySid(pSid, 0);
          if ( v19 == 2 )
          {
            if ( (_BYTE)v5 != 2 )
              return 0;
            v8 = 1;
            v10 = ApplicationPackageTypeSids;
            v11 = 1;
            goto LABEL_19;
          }
          if ( (_BYTE)v5 != 2 || v19 != 3 )
            return 0;
          v10 = ApplicationCapabilityTypeSids;
          v11 = 12;
        }
        else
        {
          v7 = *RtlSubAuthoritySid(pSid, 0);
          switch ( v7 )
          {
            case 0x20u:
              if ( (_BYTE)v5 != 2 )
                return 0;
              v10 = BuiltinDomainSids;
              v11 = 35;
              break;
            case 0x15u:
              if ( (_BYTE)v5 != 5 )
                return 0;
              v10 = AccountDomainSids;
              v11 = 22;
              break;
            case 5u:
              if ( (_BYTE)v5 == 3 )
              {
                v14 = 21;
                v8 = 1;
                goto LABEL_24;
              }
              return 0;
            case 0x40u:
              if ( (_BYTE)v5 != 2 )
                return 0;
              v10 = SecurityPackageSids;
              v11 = 3;
              break;
            case 0x41u:
              if ( (_BYTE)v5 != 2 )
                return 0;
              v8 = 1;
              v10 = &CredTypeSids;
              v11 = 1;
LABEL_19:
              v12 = *RtlSubAuthoritySid(pSid, v5 - 1);
              for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
              {
                if ( v12 == LODWORD(v10[j]) )
                {
                  v14 = HIDWORD(v10[j]);
                  goto LABEL_24;
                }
              }
              return 0;
            default:
              if ( v7 == 84 && (_BYTE)v5 == 6 )
              {
                v8 = 1;
                if ( !*RtlSubAuthoritySid(pSid, 1u)
                  && !*RtlSubAuthoritySid(pSid, 2u)
                  && !*RtlSubAuthoritySid(pSid, 3u)
                  && !*RtlSubAuthoritySid(pSid, 4u)
                  && !*RtlSubAuthoritySid(pSid, 5u) )
                {
                  v14 = 98;
LABEL_24:
                  if ( v14 == WellKnownSidType )
                    return v8;
                  return 0;
                }
              }
              return 0;
          }
        }
      }
LABEL_18:
      v8 = 1;
      goto LABEL_19;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800166b0  push    rbx
0x1800166b2  push    rsi
0x1800166b3  push    r15
0x1800166b5  sub     rsp, 20h
0x1800166b9  mov     r15d, edx
0x1800166bc  mov     rsi, rcx
0x1800166bf  call    cs:__imp_RtlValidSid
0x1800166c6  nop     dword ptr [rax+rax+00h]
0x1800166cb  test    al, al
0x1800166cd  jz      loc_180016991
0x1800166d3  xor     ecx, ecx; LastError
0x1800166d5  call    cs:__imp_RtlSetLastWin32Error
0x1800166dc  nop     dword ptr [rax+rax+00h]
0x1800166e1  mov     rcx, rsi; Sid
0x1800166e4  call    cs:__imp_RtlIdentifierAuthoritySid
0x1800166eb  nop     dword ptr [rax+rax+00h]
0x1800166f0  mov     rbx, rax
0x1800166f3  test    rax, rax
0x1800166f6  jz      loc_180016991
0x1800166fc  mov     [rsp+38h+arg_0], rbp
0x180016701  mov     rcx, rsi; Sid
0x180016704  mov     [rsp+38h+arg_10], r14
0x180016709  mov     [rsp+38h+arg_8], rdi
0x18001670e  call    cs:__imp_RtlSubAuthorityCountSid
0x180016715  nop     dword ptr [rax+rax+00h]
0x18001671a  movzx   ebp, byte ptr [rax]
0x18001671d  test    bpl, bpl
0x180016720  jz      loc_1800168FA
0x180016726  cmp     bpl, 1
0x18001672a  jz      loc_180016814
0x180016730  jbe     short loc_180016796
0x180016732  mov     ecx, [rbx]
0x180016734  sub     ecx, cs:dword_1801A5150
0x18001673a  jnz     short loc_180016749
0x18001673c  movzx   ecx, word ptr [rbx+4]
0x180016740  movzx   eax, cs:word_1801A5154
0x180016747  sub     ecx, eax
0x180016749  test    ecx, ecx
0x18001674b  jnz     loc_180016868
0x180016751  xor     edx, edx; SubAuthority
0x180016753  mov     rcx, rsi; Sid
0x180016756  call    cs:__imp_RtlSubAuthoritySid
0x18001675d  nop     dword ptr [rax+rax+00h]
0x180016762  mov     ecx, [rax]
0x180016764  cmp     ecx, 20h ; ' '
0x180016767  jz      loc_180016800
0x18001676d  cmp     ecx, 15h
0x180016770  jz      short loc_1800167B5
0x180016772  cmp     ecx, 5
0x180016775  jz      loc_18001694D
0x18001677b  cmp     ecx, 40h ; '@'
0x18001677e  jz      loc_180016967
0x180016784  cmp     ecx, 41h ; 'A'
0x180016787  jz      loc_180016998
0x18001678d  cmp     ecx, 54h ; 'T'
0x180016790  jz      loc_180016982
0x180016796  xor     r14d, r14d
0x180016799  mov     rdi, [rsp+38h+arg_8]
0x18001679e  mov     eax, r14d
0x1800167a1  mov     r14, [rsp+38h+arg_10]
0x1800167a6  mov     rbp, [rsp+38h+arg_0]
0x1800167ab  add     rsp, 20h
0x1800167af  pop     r15
0x1800167b1  pop     rsi
0x1800167b2  pop     rbx
0x1800167b3  retn
0x1800167b5  cmp     bpl, 5
0x1800167b9  jnz     short loc_180016796
0x1800167bb  lea     rdi, AccountDomainSids
0x1800167c2  mov     ebx, 16h
0x1800167c7  mov     r14d, 1
0x1800167cd  lea     edx, [rbp-1]; SubAuthority
0x1800167d0  mov     rcx, rsi; Sid
0x1800167d3  call    cs:__imp_RtlSubAuthoritySid
0x1800167da  nop     dword ptr [rax+rax+00h]
0x1800167df  mov     r8d, [rax]
0x1800167e2  xor     eax, eax
0x1800167e4  cmp     eax, ebx
0x1800167e6  jnb     short loc_180016796
0x1800167e8  cmp     r8d, [rdi+rax*8]
0x1800167ec  lea     rdx, [rdi+rax*8]
0x1800167f0  jz      short loc_1800167F6
0x1800167f2  inc     eax
0x1800167f4  jmp     short loc_1800167E4
0x1800167f6  mov     eax, [rdx+4]
0x1800167f9  cmp     eax, r15d
0x1800167fc  jz      short loc_180016799
0x1800167fe  jmp     short loc_180016796
0x180016800  cmp     bpl, 2
0x180016804  jnz     short loc_180016796
0x180016806  lea     rdi, BuiltinDomainSids
0x18001680d  mov     ebx, 23h ; '#'
0x180016812  jmp     short loc_1800167C7
0x180016814  xor     edx, edx
0x180016816  lea     r9, KnownAuthoritiesAndDomains
0x18001681d  nop     dword ptr [rax]
0x180016820  cmp     edx, 0Dh
0x180016823  jnb     loc_1800168C1
0x180016829  lea     rcx, [rdx+rdx*2]
0x18001682d  lea     r8, ds:0[rcx*8]
0x180016835  mov     ecx, [rbx]
0x180016837  sub     ecx, [r8+r9]
0x18001683b  jnz     short loc_180016849
0x18001683d  movzx   ecx, word ptr [rbx+4]
0x180016841  movzx   eax, word ptr [r8+r9+4]
0x180016847  sub     ecx, eax
0x180016849  test    ecx, ecx
0x18001684b  jz      short loc_180016851
0x18001684d  inc     edx
0x18001684f  jmp     short loc_180016820
0x180016851  lfence
0x180016854  mov     rdi, [r8+r9+8]
0x180016859  test    rdi, rdi
0x18001685c  jz      short loc_1800168C1
0x18001685e  mov     ebx, [r8+r9+10h]
0x180016863  jmp     loc_1800167C7
0x180016868  mov     ecx, [rbx]
0x18001686a  sub     ecx, cs:dword_1801A51E0
0x180016870  jnz     short loc_18001687F
0x180016872  movzx   ecx, word ptr [rbx+4]
0x180016876  movzx   eax, cs:word_1801A51E4
0x18001687d  sub     ecx, eax
0x18001687f  test    ecx, ecx
0x180016881  jnz     loc_180016796
0x180016887  xor     edx, edx; SubAuthority
0x180016889  mov     rcx, rsi; Sid
0x18001688c  call    cs:__imp_RtlSubAuthoritySid
0x180016893  nop     dword ptr [rax+rax+00h]
0x180016898  mov     ecx, [rax]
0x18001689a  cmp     ecx, 2
0x18001689d  jnz     loc_180016929
0x1800168a3  cmp     bpl, cl
0x1800168a6  jnz     loc_180016796
0x1800168ac  mov     r14d, 1
0x1800168b2  lea     rdi, ApplicationPackageTypeSids
0x1800168b9  mov     ebx, r14d
0x1800168bc  jmp     loc_1800167CD
0x1800168c1  mov     ecx, [rbx]
0x1800168c3  sub     ecx, cs:dword_1801A51B0
0x1800168c9  jnz     short loc_1800168D8
0x1800168cb  movzx   ecx, word ptr [rbx+4]
0x1800168cf  movzx   eax, cs:word_1801A51B4
0x1800168d6  sub     ecx, eax
0x1800168d8  test    ecx, ecx
0x1800168da  jnz     loc_180016796
0x1800168e0  mov     rdi, cs:off_1801A51B8
0x1800168e7  mov     ebx, 6
0x1800168ec  test    rdi, rdi
0x1800168ef  jz      loc_180016796
0x1800168f5  jmp     loc_1800167C7
0x1800168fa  mov     ecx, [rbx]
0x1800168fc  sub     ecx, cs:dword_1801A5150
0x180016902  jnz     short loc_180016911
0x180016904  movzx   ecx, word ptr [rbx+4]
0x180016908  movzx   eax, cs:word_1801A5154
0x18001690f  sub     ecx, eax
0x180016911  test    ecx, ecx
0x180016913  jnz     loc_180016796
0x180016919  mov     eax, 7
0x18001691e  mov     r14d, 1
0x180016924  jmp     loc_1800167F9
0x180016929  cmp     bpl, 2
0x18001692d  jnz     loc_180016796
0x180016933  cmp     ecx, 3
0x180016936  jnz     loc_180016796
0x18001693c  lea     rdi, ApplicationCapabilityTypeSids
0x180016943  mov     ebx, 0Ch
0x180016948  jmp     loc_1800167C7
0x18001694d  cmp     bpl, 3
0x180016951  jnz     loc_180016796
0x180016957  mov     eax, 15h
0x18001695c  mov     r14d, 1
0x180016962  jmp     loc_1800167F9
0x180016967  cmp     bpl, 2
0x18001696b  jnz     loc_180016796
0x180016971  lea     rdi, SecurityPackageSids
0x180016978  mov     ebx, 3
0x18001697d  jmp     loc_1800167C7
0x180016982  cmp     bpl, 6
0x180016986  jnz     loc_180016796
0x18001698c  jmp     loc_180199B7A
0x180016991  xor     eax, eax
0x180016993  jmp     loc_1800167AB
0x180016998  cmp     bpl, 2
0x18001699c  jnz     loc_180016796
0x1800169a2  mov     r14d, 1
0x1800169a8  lea     rdi, CredTypeSids
0x1800169af  mov     ebx, r14d
0x1800169b2  jmp     loc_1800167CD
0x180199b7a  mov     r14d, 1
0x180199b80  mov     rcx, rsi; Sid
0x180199b83  mov     edx, r14d; SubAuthority
0x180199b86  call    cs:__imp_RtlSubAuthoritySid
0x180199b8d  nop     dword ptr [rax+rax+00h]
0x180199b92  cmp     dword ptr [rax], 0
0x180199b95  jnz     loc_180016796
0x180199b9b  mov     edx, 2; SubAuthority
0x180199ba0  mov     rcx, rsi; Sid
0x180199ba3  call    cs:__imp_RtlSubAuthoritySid
0x180199baa  nop     dword ptr [rax+rax+00h]
0x180199baf  cmp     dword ptr [rax], 0
0x180199bb2  jnz     loc_180016796
0x180199bb8  mov     edx, 3; SubAuthority
0x180199bbd  mov     rcx, rsi; Sid
0x180199bc0  call    cs:__imp_RtlSubAuthoritySid
0x180199bc7  nop     dword ptr [rax+rax+00h]
0x180199bcc  cmp     dword ptr [rax], 0
0x180199bcf  jnz     loc_180016796
0x180199bd5  mov     edx, 4; SubAuthority
0x180199bda  mov     rcx, rsi; Sid
0x180199bdd  call    cs:__imp_RtlSubAuthoritySid
0x180199be4  nop     dword ptr [rax+rax+00h]
0x180199be9  cmp     dword ptr [rax], 0
0x180199bec  jnz     loc_180016796
0x180199bf2  mov     edx, 5; SubAuthority
0x180199bf7  mov     rcx, rsi; Sid
0x180199bfa  call    cs:__imp_RtlSubAuthoritySid
0x180199c01  nop     dword ptr [rax+rax+00h]
0x180199c06  cmp     dword ptr [rax], 0
0x180199c09  jnz     loc_180016796
0x180199c0f  mov     eax, 62h ; 'b'
0x180199c14  jmp     loc_1800167F9
```
