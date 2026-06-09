# InitSecurityAcls

- ea: `0x1800173cc`
- end: `0x1800175a5`
- name: `InitSecurityAcls`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800175ac`

## callees

- `0x180007740`
- `0x1800173cc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800174a1`
- `ntdll!RtlLengthSid` at `0x1800174ad`
- `ntdll!RtlLengthSid` at `0x1800174a1`
- `ntdll!RtlLengthSid` at `0x1800174ad`
- `ntdll!RtlAddAccessAllowedAce` at `0x180017510`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001752e`
- `ntdll!RtlAddAccessAllowedAce` at `0x180017510`
- `ntdll!RtlAddAccessAllowedAce` at `0x18001752e`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180017542`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180017542`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017446`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001748d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180017446`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18001748d`
- `ntdll!RtlCreateAcl` at `0x1800174f2`
- `ntdll!RtlCreateAcl` at `0x1800174f2`
- `ntdll!RtlFreeSid` at `0x18001756a`
- `ntdll!RtlFreeSid` at `0x180017579`
- `ntdll!RtlFreeSid` at `0x18001756a`
- `ntdll!RtlFreeSid` at `0x180017579`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180017559`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180017559`
- `ntdll!RtlAllocateHeap` at `0x1800174ce`
- `ntdll!RtlAllocateHeap` at `0x1800174ce`

## pseudocode

```c
__int64 __fastcall InitSecurityAcls(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS Acl; // ebx
  ULONG v3; // ebx
  ULONG v4; // ebx
  struct _ACL *Heap; // rax
  struct _ACL *v6; // rdi
  PSID Sid; // [rsp+68h] [rbp+17h] BYREF
  PSID v9; // [rsp+70h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+80h] [rbp+2Fh] BYREF

  *(_WORD *)&v11.Value[4] = 1280;
  *a1 = 0;
  *(_DWORD *)v11.Value = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  v9 = 0;
  Sid = 0;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( Acl >= 0 )
  {
    Acl = RtlAllocateAndInitializeSid(&v11, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v9);
    if ( Acl >= 0 )
    {
      v3 = RtlLengthSid(Sid);
      v4 = RtlLengthSid(v9) + 24 + v3;
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4 + 40LL);
      *a1 = Heap;
      if ( Heap )
      {
        v6 = Heap + 5;
        Acl = RtlCreateAcl(Heap + 5, v4, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v6, 2u, 0x3003Fu, Sid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, v9);
            if ( Acl >= 0 )
            {
              Acl = RtlCreateSecurityDescriptor(*a1, 1u);
              if ( Acl >= 0 )
                Acl = RtlSetDaclSecurityDescriptor(*a1, 1u, v6, 0);
            }
          }
        }
      }
      else
      {
        Acl = -1073741670;
      }
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  if ( v9 )
    RtlFreeSid(v9);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1800173cc  mov     r11, rsp
0x1800173cf  mov     [r11+10h], rbx
0x1800173d3  mov     [r11+18h], rsi
0x1800173d7  push    rbp
0x1800173d8  push    rdi
0x1800173d9  push    r14
0x1800173db  lea     rbp, [r11-5Fh]
0x1800173df  sub     rsp, 90h
0x1800173e6  mov     rax, cs:__security_cookie
0x1800173ed  xor     rax, rsp
0x1800173f0  mov     [rbp+57h+var_20], rax
0x1800173f4  xor     r14d, r14d
0x1800173f7  mov     word ptr [rbp+57h+var_28.Value+4], 500h
0x1800173fd  lea     rax, [rbp+57h+var_40]
0x180017401  mov     [rcx], r14
0x180017404  mov     [r11-58h], rax
0x180017408  mov     rsi, rcx
0x18001740b  mov     [r11-60h], r14d
0x18001740f  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180017413  mov     [r11-68h], r14d
0x180017417  xor     r9d, r9d; SubAuthority1
0x18001741a  mov     [r11-70h], r14d
0x18001741e  xor     r8d, r8d; SubAuthority0
0x180017421  mov     [r11-78h], r14d
0x180017425  mov     dl, 1; SubAuthorityCount
0x180017427  mov     [r11-80h], r14d
0x18001742b  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x180017430  mov     dword ptr [rbp+57h+var_28.Value], r14d
0x180017434  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r14d
0x180017438  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 100h
0x18001743e  mov     [rbp+57h+var_38], r14
0x180017442  mov     [rbp+57h+var_40], r14
0x180017446  call    cs:__imp_RtlAllocateAndInitializeSid
0x18001744c  mov     ebx, eax
0x18001744e  test    eax, eax
0x180017450  js      loc_180017561
0x180017456  lea     rax, [rbp+57h+var_38]
0x18001745a  mov     r9d, 220h; SubAuthority1
0x180017460  mov     [rsp+0A0h+Sid], rax; Sid
0x180017465  lea     r8d, [r14+20h]; SubAuthority0
0x180017469  mov     [rsp+0A0h+SubAuthority7], r14d; SubAuthority7
0x18001746e  lea     rcx, [rbp+57h+var_28]; IdentifierAuthority
0x180017472  mov     [rsp+0A0h+SubAuthority6], r14d; SubAuthority6
0x180017477  mov     dl, 2; SubAuthorityCount
0x180017479  mov     [rsp+0A0h+SubAuthority5], r14d; SubAuthority5
0x18001747e  mov     [rsp+0A0h+SubAuthority4], r14d; SubAuthority4
0x180017483  mov     [rsp+0A0h+SubAuthority3], r14d; SubAuthority3
0x180017488  mov     [rsp+0A0h+SubAuthority2], r14d; SubAuthority2
0x18001748d  call    cs:__imp_RtlAllocateAndInitializeSid
0x180017493  mov     ebx, eax
0x180017495  test    eax, eax
0x180017497  js      loc_180017561
0x18001749d  mov     rcx, [rbp+57h+var_40]; Sid
0x1800174a1  call    cs:__imp_RtlLengthSid
0x1800174a7  mov     rcx, [rbp+57h+var_38]; Sid
0x1800174ab  mov     ebx, eax
0x1800174ad  call    cs:__imp_RtlLengthSid
0x1800174b3  mov     rcx, gs:60h
0x1800174bc  xor     edx, edx; Flags
0x1800174be  add     eax, 18h
0x1800174c1  add     ebx, eax
0x1800174c3  mov     r8d, ebx
0x1800174c6  mov     rcx, [rcx+30h]; HeapHandle
0x1800174ca  add     r8, 28h ; '('; Size
0x1800174ce  call    cs:__imp_RtlAllocateHeap
0x1800174d4  mov     [rsi], rax
0x1800174d7  test    rax, rax
0x1800174da  jnz     short loc_1800174E3
0x1800174dc  mov     ebx, 0C000009Ah
0x1800174e1  jmp     short loc_180017561
0x1800174e3  lea     rdi, [rax+28h]
0x1800174e7  mov     r8d, 2; AclRevision
0x1800174ed  mov     rcx, rdi; Acl
0x1800174f0  mov     edx, ebx; AclSize
0x1800174f2  call    cs:__imp_RtlCreateAcl
0x1800174f8  mov     ebx, eax
0x1800174fa  test    eax, eax
0x1800174fc  js      short loc_180017561
0x1800174fe  mov     r9, [rbp+57h+var_40]; Sid
0x180017502  mov     edx, 2; Revision
0x180017507  mov     r8d, 3003Fh; AccessMask
0x18001750d  mov     rcx, rdi; Acl
0x180017510  call    cs:__imp_RtlAddAccessAllowedAce
0x180017516  mov     ebx, eax
0x180017518  test    eax, eax
0x18001751a  js      short loc_180017561
0x18001751c  mov     r9, [rbp+57h+var_38]; Sid
0x180017520  mov     edx, 2; Revision
0x180017525  mov     r8d, 10000000h; AccessMask
0x18001752b  mov     rcx, rdi; Acl
0x18001752e  call    cs:__imp_RtlAddAccessAllowedAce
0x180017534  mov     ebx, eax
0x180017536  test    eax, eax
0x180017538  js      short loc_180017561
0x18001753a  mov     rcx, [rsi]; SecurityDescriptor
0x18001753d  mov     edx, 1; Revision
0x180017542  call    cs:__imp_RtlCreateSecurityDescriptor
0x180017548  mov     ebx, eax
0x18001754a  test    eax, eax
0x18001754c  js      short loc_180017561
0x18001754e  mov     rcx, [rsi]; SecurityDescriptor
0x180017551  xor     r9d, r9d; DaclDefaulted
0x180017554  mov     r8, rdi; Dacl
0x180017557  mov     dl, 1; DaclPresent
0x180017559  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18001755f  mov     ebx, eax
0x180017561  mov     rcx, [rbp+57h+var_40]; Sid
0x180017565  test    rcx, rcx
0x180017568  jz      short loc_180017570
0x18001756a  call    cs:__imp_RtlFreeSid
0x180017570  mov     rcx, [rbp+57h+var_38]; Sid
0x180017574  test    rcx, rcx
0x180017577  jz      short loc_18001757F
0x180017579  call    cs:__imp_RtlFreeSid
0x18001757f  mov     eax, ebx
0x180017581  mov     rcx, [rbp+57h+var_20]
0x180017585  xor     rcx, rsp; StackCookie
0x180017588  call    __security_check_cookie
0x18001758d  lea     r11, [rsp+0A0h+var_10]
0x180017595  mov     rbx, [r11+28h]
0x180017599  mov     rsi, [r11+30h]
0x18001759d  mov     rsp, r11
0x1800175a0  pop     r14
0x1800175a2  pop     rdi
0x1800175a3  pop     rbp
0x1800175a4  retn
```
