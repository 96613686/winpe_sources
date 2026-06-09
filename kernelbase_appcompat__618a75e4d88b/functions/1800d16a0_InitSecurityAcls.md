# InitSecurityAcls

- ea: `0x1800d16a0`
- end: `0x1800d18b2`
- name: `InitSecurityAcls`
- size: `530`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d1400`
- `0x1800d1550`

## callees

- `0x1800d16a0`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800d186f`
- `ntdll!RtlFreeSid` at `0x1800d1884`
- `ntdll!RtlFreeSid` at `0x1800d186f`
- `ntdll!RtlFreeSid` at `0x1800d1884`
- `ntdll!RtlCreateAcl` at `0x1800d17d9`
- `ntdll!RtlCreateAcl` at `0x1800d17d9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800d183b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800d183b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800d1858`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800d1858`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d1716`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d175f`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d1716`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800d175f`
- `ntdll!RtlLengthSid` at `0x1800d1779`
- `ntdll!RtlLengthSid` at `0x1800d178b`
- `ntdll!RtlLengthSid` at `0x1800d1779`
- `ntdll!RtlLengthSid` at `0x1800d178b`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800d17fd`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800d1821`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800d17fd`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800d1821`
- `ntdll!RtlAllocateHeap` at `0x1800d17b2`
- `ntdll!RtlAllocateHeap` at `0x1800d17b2`

## pseudocode

```c
__int64 __fastcall InitSecurityAcls(PSECURITY_DESCRIPTOR *a1)
{
  NTSTATUS Acl; // ebx
  ULONG v3; // ebx
  ULONG v4; // ebx
  ACL *Heap; // rax
  ACL *v6; // rdi
  PSID Sid; // [rsp+60h] [rbp+7h] BYREF
  PSID v9; // [rsp+68h] [rbp+Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+78h] [rbp+1Fh] BYREF

  *(_DWORD *)v11.Value = 0;
  *a1 = 0;
  *(_WORD *)&v11.Value[4] = 1280;
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
      Heap = (ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4 + 40LL);
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
0x1800d16a0  push    rbp
0x1800d16a2  push    rbx
0x1800d16a3  push    rsi
0x1800d16a4  push    rdi
0x1800d16a5  lea     rbp, [rsp-3Fh]
0x1800d16aa  sub     rsp, 98h
0x1800d16b1  mov     rax, cs:__security_cookie
0x1800d16b8  xor     rax, rsp
0x1800d16bb  mov     [rbp+57h+var_30], rax
0x1800d16bf  xor     edi, edi
0x1800d16c1  mov     dword ptr [rbp+57h+var_38.Value], 0
0x1800d16c8  lea     rax, [rbp+57h+var_50]
0x1800d16cc  mov     [rcx], rdi
0x1800d16cf  mov     [rsp+0B0h+Sid], rax; Sid
0x1800d16d4  mov     rsi, rcx
0x1800d16d7  mov     [rsp+0B0h+SubAuthority7], edi; SubAuthority7
0x1800d16db  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x1800d16df  mov     [rsp+0B0h+SubAuthority6], edi; SubAuthority6
0x1800d16e3  xor     r9d, r9d; SubAuthority1
0x1800d16e6  mov     [rsp+0B0h+SubAuthority5], edi; SubAuthority5
0x1800d16ea  xor     r8d, r8d; SubAuthority0
0x1800d16ed  mov     [rsp+0B0h+SubAuthority4], edi; SubAuthority4
0x1800d16f1  mov     dl, 1; SubAuthorityCount
0x1800d16f3  mov     [rsp+0B0h+SubAuthority3], edi; SubAuthority3
0x1800d16f7  mov     [rsp+0B0h+SubAuthority2], edi; SubAuthority2
0x1800d16fb  mov     word ptr [rbp+57h+var_38.Value+4], 500h
0x1800d1701  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x1800d1708  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 100h
0x1800d170e  mov     [rbp+57h+var_48], rdi
0x1800d1712  mov     [rbp+57h+var_50], rdi
0x1800d1716  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800d171d  nop     dword ptr [rax+rax+00h]
0x1800d1722  mov     ebx, eax
0x1800d1724  test    eax, eax
0x1800d1726  js      loc_1800D1866
0x1800d172c  lea     rax, [rbp+57h+var_48]
0x1800d1730  mov     r9d, 220h; SubAuthority1
0x1800d1736  mov     [rsp+0B0h+Sid], rax; Sid
0x1800d173b  lea     rcx, [rbp+57h+var_38]; IdentifierAuthority
0x1800d173f  mov     [rsp+0B0h+SubAuthority7], edi; SubAuthority7
0x1800d1743  mov     r8d, 20h ; ' '; SubAuthority0
0x1800d1749  mov     [rsp+0B0h+SubAuthority6], edi; SubAuthority6
0x1800d174d  mov     dl, 2; SubAuthorityCount
0x1800d174f  mov     [rsp+0B0h+SubAuthority5], edi; SubAuthority5
0x1800d1753  mov     [rsp+0B0h+SubAuthority4], edi; SubAuthority4
0x1800d1757  mov     [rsp+0B0h+SubAuthority3], edi; SubAuthority3
0x1800d175b  mov     [rsp+0B0h+SubAuthority2], edi; SubAuthority2
0x1800d175f  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800d1766  nop     dword ptr [rax+rax+00h]
0x1800d176b  mov     ebx, eax
0x1800d176d  test    eax, eax
0x1800d176f  js      loc_1800D1866
0x1800d1775  mov     rcx, [rbp+57h+var_50]; Sid
0x1800d1779  call    cs:__imp_RtlLengthSid
0x1800d1780  nop     dword ptr [rax+rax+00h]
0x1800d1785  mov     rcx, [rbp+57h+var_48]; Sid
0x1800d1789  mov     ebx, eax
0x1800d178b  call    cs:__imp_RtlLengthSid
0x1800d1792  nop     dword ptr [rax+rax+00h]
0x1800d1797  mov     rcx, gs:60h
0x1800d17a0  xor     edx, edx; Flags
0x1800d17a2  add     eax, 18h
0x1800d17a5  add     ebx, eax
0x1800d17a7  mov     r8d, ebx
0x1800d17aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800d17ae  add     r8, 28h ; '('; Size
0x1800d17b2  call    cs:__imp_RtlAllocateHeap
0x1800d17b9  nop     dword ptr [rax+rax+00h]
0x1800d17be  mov     [rsi], rax
0x1800d17c1  test    rax, rax
0x1800d17c4  jz      loc_1800D18AB
0x1800d17ca  lea     rdi, [rax+28h]
0x1800d17ce  mov     r8d, 2; AclRevision
0x1800d17d4  mov     rcx, rdi; Acl
0x1800d17d7  mov     edx, ebx; AclSize
0x1800d17d9  call    cs:__imp_RtlCreateAcl
0x1800d17e0  nop     dword ptr [rax+rax+00h]
0x1800d17e5  mov     ebx, eax
0x1800d17e7  test    eax, eax
0x1800d17e9  js      short loc_1800D1866
0x1800d17eb  mov     r9, [rbp+57h+var_50]; Sid
0x1800d17ef  mov     edx, 2; Revision
0x1800d17f4  mov     r8d, 3003Fh; AccessMask
0x1800d17fa  mov     rcx, rdi; Acl
0x1800d17fd  call    cs:__imp_RtlAddAccessAllowedAce
0x1800d1804  nop     dword ptr [rax+rax+00h]
0x1800d1809  mov     ebx, eax
0x1800d180b  test    eax, eax
0x1800d180d  js      short loc_1800D1866
0x1800d180f  mov     r9, [rbp+57h+var_48]; Sid
0x1800d1813  mov     edx, 2; Revision
0x1800d1818  mov     r8d, 10000000h; AccessMask
0x1800d181e  mov     rcx, rdi; Acl
0x1800d1821  call    cs:__imp_RtlAddAccessAllowedAce
0x1800d1828  nop     dword ptr [rax+rax+00h]
0x1800d182d  mov     ebx, eax
0x1800d182f  test    eax, eax
0x1800d1831  js      short loc_1800D1866
0x1800d1833  mov     rcx, [rsi]; SecurityDescriptor
0x1800d1836  mov     edx, 1; Revision
0x1800d183b  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800d1842  nop     dword ptr [rax+rax+00h]
0x1800d1847  mov     ebx, eax
0x1800d1849  test    eax, eax
0x1800d184b  js      short loc_1800D1866
0x1800d184d  mov     rcx, [rsi]; SecurityDescriptor
0x1800d1850  xor     r9d, r9d; DaclDefaulted
0x1800d1853  mov     r8, rdi; Dacl
0x1800d1856  mov     dl, 1; DaclPresent
0x1800d1858  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800d185f  nop     dword ptr [rax+rax+00h]
0x1800d1864  mov     ebx, eax
0x1800d1866  mov     rcx, [rbp+57h+var_50]; Sid
0x1800d186a  test    rcx, rcx
0x1800d186d  jz      short loc_1800D187B
0x1800d186f  call    cs:__imp_RtlFreeSid
0x1800d1876  nop     dword ptr [rax+rax+00h]
0x1800d187b  mov     rcx, [rbp+57h+var_48]; Sid
0x1800d187f  test    rcx, rcx
0x1800d1882  jz      short loc_1800D1890
0x1800d1884  call    cs:__imp_RtlFreeSid
0x1800d188b  nop     dword ptr [rax+rax+00h]
0x1800d1890  mov     eax, ebx
0x1800d1892  mov     rcx, [rbp+57h+var_30]
0x1800d1896  xor     rcx, rsp; StackCookie
0x1800d1899  call    __security_check_cookie
0x1800d189e  add     rsp, 98h
0x1800d18a5  pop     rdi
0x1800d18a6  pop     rsi
0x1800d18a7  pop     rbx
0x1800d18a8  pop     rbp
0x1800d18a9  retn
0x1800d18ab  mov     ebx, 0C000009Ah
0x1800d18b0  jmp     short loc_1800D1866
```
