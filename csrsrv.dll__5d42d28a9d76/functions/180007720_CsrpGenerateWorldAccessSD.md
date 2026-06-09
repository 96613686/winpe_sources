# CsrpGenerateWorldAccessSD

- ea: `0x180007720`
- end: `0x180007b60`
- name: `CsrpGenerateWorldAccessSD`
- size: `1088`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800073d0`
- `0x1800095c0`

## callees

- `0x180007720`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180007774`
- `ntdll!RtlAllocateHeap` at `0x180007917`
- `ntdll!RtlAllocateHeap` at `0x180007aba`
- `ntdll!RtlAllocateHeap` at `0x180007774`
- `ntdll!RtlAllocateHeap` at `0x180007917`
- `ntdll!RtlAllocateHeap` at `0x180007aba`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180007a2d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180007a2d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800077f6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000784c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000789c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007a82`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800077f6`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000784c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000789c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007a82`
- `ntdll!RtlLengthSid` at `0x1800078b5`
- `ntdll!RtlLengthSid` at `0x1800078cc`
- `ntdll!RtlLengthSid` at `0x1800078e3`
- `ntdll!RtlLengthSid` at `0x1800078f5`
- `ntdll!RtlLengthSid` at `0x180007a9b`
- `ntdll!RtlLengthSid` at `0x1800078b5`
- `ntdll!RtlLengthSid` at `0x1800078cc`
- `ntdll!RtlLengthSid` at `0x1800078e3`
- `ntdll!RtlLengthSid` at `0x1800078f5`
- `ntdll!RtlLengthSid` at `0x180007a9b`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000796a`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800079a1`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800079d4`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007a04`
- `ntdll!RtlAddAccessAllowedAce` at `0x18000796a`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800079a1`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800079d4`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007a04`
- `ntdll!RtlFreeSid` at `0x1800079b5`
- `ntdll!RtlFreeSid` at `0x1800079e8`
- `ntdll!RtlFreeSid` at `0x180007a15`
- `ntdll!RtlFreeSid` at `0x180007b13`
- `ntdll!RtlFreeSid` at `0x1800079b5`
- `ntdll!RtlFreeSid` at `0x1800079e8`
- `ntdll!RtlFreeSid` at `0x180007a15`
- `ntdll!RtlFreeSid` at `0x180007b13`
- `ntdll!RtlFreeHeap` at `0x180007982`
- `ntdll!RtlFreeHeap` at `0x180007982`
- `ntdll!RtlCreateAcl` at `0x180007950`
- `ntdll!RtlCreateAcl` at `0x180007ad9`
- `ntdll!RtlCreateAcl` at `0x180007950`
- `ntdll!RtlCreateAcl` at `0x180007ad9`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007938`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007938`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180007b2b`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180007b2b`
- `ntdll!RtlAddProcessTrustLabelAce` at `0x180007b02`
- `ntdll!RtlAddProcessTrustLabelAce` at `0x180007b02`
- `ntdll!RtlInitializeSid` at `0x180007799`
- `ntdll!RtlInitializeSid` at `0x180007799`
- `ntdll!RtlSubAuthoritySid` at `0x1800077aa`
- `ntdll!RtlSubAuthoritySid` at `0x1800077aa`
- `ntdll!RtlLengthRequiredSid` at `0x18000775c`
- `ntdll!RtlLengthRequiredSid` at `0x18000775c`

## pseudocode

```c
NTSTATUS __fastcall CsrpGenerateWorldAccessSD(ACCESS_MASK AccessMask, _DWORD *a2, struct _ACL **a3)
{
  ULONG v3; // ebx
  ULONG v7; // eax
  PVOID Heap; // rax
  void *v9; // rbx
  NTSTATUS result; // eax
  ULONG v11; // r15d
  ULONG v12; // r15d
  ULONG v13; // r15d
  ULONG v14; // r15d
  struct _ACL *v15; // rdi
  struct _ACL *v16; // rbx
  SIZE_T v17; // rbp
  struct _ACL *v18; // rax
  ULONG SubAuthority2; // [rsp+20h] [rbp-88h]
  PSID v20; // [rsp+60h] [rbp-48h] BYREF
  PSID v21; // [rsp+68h] [rbp-40h] BYREF
  PSID Sid; // [rsp+C0h] [rbp+18h] BYREF
  PSID v23; // [rsp+C8h] [rbp+20h] BYREF

  v3 = CsrBaseTag;
  Sid = 0;
  v23 = 0;
  v20 = 0;
  v21 = 0;
  v7 = RtlLengthRequiredSid(1u);
  Heap = RtlAllocateHeap(CsrHeap, v3, v7);
  v9 = Heap;
  if ( !Heap )
    return -1073741801;
  RtlInitializeSid(Heap, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v9, 0) = 0;
  result = RtlAllocateAndInitializeSid(&stru_18000FCFC, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( result >= 0 )
  {
    result = RtlAllocateAndInitializeSid(&stru_18000FCF4, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &v23);
    if ( result >= 0 )
    {
      result = RtlAllocateAndInitializeSid(&stru_18000FCF4, 2u, 2u, 2u, 0, 0, 0, 0, 0, 0, &v20);
      if ( result >= 0 )
      {
        v11 = RtlLengthSid(v20);
        v12 = RtlLengthSid(v23) + v11;
        v13 = RtlLengthSid(Sid) + v12;
        v14 = RtlLengthSid(v9) + 56 + v13;
        v15 = (struct _ACL *)RtlAllocateHeap(CsrHeap, CsrBaseTag, v14);
        if ( v15 )
        {
          RtlCreateSecurityDescriptor(a3 + 2, 1u);
          RtlCreateAcl(v15, v14, 2u);
          RtlAddAccessAllowedAce(v15, 2u, AccessMask, v9);
          RtlFreeHeap(CsrHeap, 0, v9);
          RtlAddAccessAllowedAce(v15, 2u, AccessMask, Sid);
          RtlFreeSid(Sid);
          RtlAddAccessAllowedAce(v15, 2u, AccessMask, v23);
          RtlFreeSid(v23);
          RtlAddAccessAllowedAce(v15, 2u, AccessMask, v20);
          RtlFreeSid(v20);
          RtlSetDaclSecurityDescriptor(a3 + 2, 1u, v15, 0);
          v16 = 0;
          if ( !a2 )
          {
LABEL_10:
            *a3 = v15;
            result = 0;
            a3[1] = v16;
            return result;
          }
          result = RtlAllocateAndInitializeSid(&stru_18000FD04, 2u, 0x200u, 0x2000u, 0, 0, 0, 0, 0, 0, &v21);
          if ( result < 0 )
            return result;
          v17 = RtlLengthSid(v21) + 20;
          v18 = (struct _ACL *)RtlAllocateHeap(CsrHeap, CsrBaseTag, v17);
          v16 = v18;
          if ( v18 )
          {
            RtlCreateAcl(v18, v17, 2u);
            LOBYTE(SubAuthority2) = 20;
            RtlAddProcessTrustLabelAce(v16, 2, 0, v21, SubAuthority2, *a2);
            RtlFreeSid(v21);
            RtlSetSaclSecurityDescriptor(a3 + 2, 1u, v16, 0);
            goto LABEL_10;
          }
        }
        return -1073741801;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007720  mov     rax, rsp
0x180007723  mov     [rax+8], rbx
0x180007727  push    rbp
0x180007728  push    rsi
0x180007729  push    rdi
0x18000772a  push    r12
0x18000772c  push    r13
0x18000772e  push    r14
0x180007730  push    r15
0x180007732  sub     rsp, 70h
0x180007736  mov     ebx, cs:CsrBaseTag
0x18000773c  xor     r13d, r13d
0x18000773f  mov     ebp, ecx
0x180007741  mov     [rax+18h], r13
0x180007745  mov     ecx, 1; SubAuthorityCount
0x18000774a  mov     [rax+20h], r13
0x18000774e  mov     [rax-48h], r13
0x180007752  mov     rsi, r8
0x180007755  mov     [rax-40h], r13
0x180007759  mov     r14, rdx
0x18000775c  call    cs:__imp_RtlLengthRequiredSid
0x180007763  nop     dword ptr [rax+rax+00h]
0x180007768  mov     rcx, cs:CsrHeap; HeapHandle
0x18000776f  mov     edx, ebx; Flags
0x180007771  mov     r8d, eax; Size
0x180007774  call    cs:__imp_RtlAllocateHeap
0x18000777b  nop     dword ptr [rax+rax+00h]
0x180007780  mov     rbx, rax
0x180007783  test    rax, rax
0x180007786  jz      loc_180007B42
0x18000778c  mov     r8b, 1; SubAuthorityCount
0x18000778f  lea     rdx, IdentifierAuthority; IdentifierAuthority
0x180007796  mov     rcx, rax; Sid
0x180007799  call    cs:__imp_RtlInitializeSid
0x1800077a0  nop     dword ptr [rax+rax+00h]
0x1800077a5  xor     edx, edx; SubAuthority
0x1800077a7  mov     rcx, rbx; Sid
0x1800077aa  call    cs:__imp_RtlSubAuthoritySid
0x1800077b1  nop     dword ptr [rax+rax+00h]
0x1800077b6  xor     r9d, r9d; SubAuthority1
0x1800077b9  lea     rcx, stru_18000FCFC; IdentifierAuthority
0x1800077c0  mov     r8d, 0Ch; SubAuthority0
0x1800077c6  mov     dl, 1; SubAuthorityCount
0x1800077c8  mov     [rax], r13d
0x1800077cb  lea     rax, [rsp+0A8h+arg_10]
0x1800077d3  mov     [rsp+0A8h+Sid], rax; Sid
0x1800077d8  mov     [rsp+0A8h+SubAuthority7], r13d; SubAuthority7
0x1800077dd  mov     [rsp+0A8h+SubAuthority6], r13d; SubAuthority6
0x1800077e2  mov     [rsp+0A8h+SubAuthority5], r13d; SubAuthority5
0x1800077e7  mov     [rsp+0A8h+SubAuthority4], r13d; SubAuthority4
0x1800077ec  mov     [rsp+0A8h+SubAuthority3], r13d; SubAuthority3
0x1800077f1  mov     [rsp+0A8h+SubAuthority2], r13d; SubAuthority2
0x1800077f6  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800077fd  nop     dword ptr [rax+rax+00h]
0x180007802  test    eax, eax
0x180007804  js      loc_180007B47
0x18000780a  lea     rax, [rsp+0A8h+arg_18]
0x180007812  mov     r8d, 2; SubAuthority0
0x180007818  mov     [rsp+0A8h+Sid], rax; Sid
0x18000781d  lea     rcx, stru_18000FCF4; IdentifierAuthority
0x180007824  mov     [rsp+0A8h+SubAuthority7], r13d; SubAuthority7
0x180007829  mov     r9d, 1; SubAuthority1
0x18000782f  mov     [rsp+0A8h+SubAuthority6], r13d; SubAuthority6
0x180007834  movzx   edx, r8b; SubAuthorityCount
0x180007838  mov     [rsp+0A8h+SubAuthority5], r13d; SubAuthority5
0x18000783d  mov     [rsp+0A8h+SubAuthority4], r13d; SubAuthority4
0x180007842  mov     [rsp+0A8h+SubAuthority3], r13d; SubAuthority3
0x180007847  mov     [rsp+0A8h+SubAuthority2], r13d; SubAuthority2
0x18000784c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180007853  nop     dword ptr [rax+rax+00h]
0x180007858  test    eax, eax
0x18000785a  js      loc_180007B47
0x180007860  lea     rax, [rsp+0A8h+var_48]
0x180007865  mov     r9d, 2; SubAuthority1
0x18000786b  mov     [rsp+0A8h+Sid], rax; Sid
0x180007870  lea     rcx, stru_18000FCF4; IdentifierAuthority
0x180007877  mov     [rsp+0A8h+SubAuthority7], r13d; SubAuthority7
0x18000787c  mov     r8d, r9d; SubAuthority0
0x18000787f  mov     [rsp+0A8h+SubAuthority6], r13d; SubAuthority6
0x180007884  movzx   edx, r8b; SubAuthorityCount
0x180007888  mov     [rsp+0A8h+SubAuthority5], r13d; SubAuthority5
0x18000788d  mov     [rsp+0A8h+SubAuthority4], r13d; SubAuthority4
0x180007892  mov     [rsp+0A8h+SubAuthority3], r13d; SubAuthority3
0x180007897  mov     [rsp+0A8h+SubAuthority2], r13d; SubAuthority2
0x18000789c  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800078a3  nop     dword ptr [rax+rax+00h]
0x1800078a8  test    eax, eax
0x1800078aa  js      loc_180007B47
0x1800078b0  mov     rcx, [rsp+0A8h+var_48]; Sid
0x1800078b5  call    cs:__imp_RtlLengthSid
0x1800078bc  nop     dword ptr [rax+rax+00h]
0x1800078c1  mov     rcx, [rsp+0A8h+arg_18]; Sid
0x1800078c9  mov     r15d, eax
0x1800078cc  call    cs:__imp_RtlLengthSid
0x1800078d3  nop     dword ptr [rax+rax+00h]
0x1800078d8  mov     rcx, [rsp+0A8h+arg_10]; Sid
0x1800078e0  add     r15d, eax
0x1800078e3  call    cs:__imp_RtlLengthSid
0x1800078ea  nop     dword ptr [rax+rax+00h]
0x1800078ef  mov     rcx, rbx; Sid
0x1800078f2  add     r15d, eax
0x1800078f5  call    cs:__imp_RtlLengthSid
0x1800078fc  nop     dword ptr [rax+rax+00h]
0x180007901  mov     edx, cs:CsrBaseTag; Flags
0x180007907  add     eax, 38h ; '8'
0x18000790a  mov     rcx, cs:CsrHeap; HeapHandle
0x180007911  add     r15d, eax
0x180007914  mov     r8d, r15d; Size
0x180007917  call    cs:__imp_RtlAllocateHeap
0x18000791e  nop     dword ptr [rax+rax+00h]
0x180007923  mov     rdi, rax
0x180007926  test    rax, rax
0x180007929  jz      loc_180007B42
0x18000792f  mov     edx, 1; Revision
0x180007934  lea     rcx, [rsi+10h]; SecurityDescriptor
0x180007938  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000793f  nop     dword ptr [rax+rax+00h]
0x180007944  mov     r8d, 2; AclRevision
0x18000794a  mov     edx, r15d; AclLength
0x18000794d  mov     rcx, rdi; Acl
0x180007950  call    cs:__imp_RtlCreateAcl
0x180007957  nop     dword ptr [rax+rax+00h]
0x18000795c  mov     r9, rbx; Sid
0x18000795f  mov     r8d, ebp; AccessMask
0x180007962  mov     edx, 2; AceRevision
0x180007967  mov     rcx, rdi; Acl
0x18000796a  call    cs:__imp_RtlAddAccessAllowedAce
0x180007971  nop     dword ptr [rax+rax+00h]
0x180007976  mov     rcx, cs:CsrHeap; HeapHandle
0x18000797d  mov     r8, rbx; BaseAddress
0x180007980  xor     edx, edx; Flags
0x180007982  call    cs:__imp_RtlFreeHeap
0x180007989  nop     dword ptr [rax+rax+00h]
0x18000798e  mov     r9, [rsp+0A8h+arg_10]; Sid
0x180007996  mov     r8d, ebp; AccessMask
0x180007999  mov     edx, 2; AceRevision
0x18000799e  mov     rcx, rdi; Acl
0x1800079a1  call    cs:__imp_RtlAddAccessAllowedAce
0x1800079a8  nop     dword ptr [rax+rax+00h]
0x1800079ad  mov     rcx, [rsp+0A8h+arg_10]; Sid
0x1800079b5  call    cs:__imp_RtlFreeSid
0x1800079bc  nop     dword ptr [rax+rax+00h]
0x1800079c1  mov     r9, [rsp+0A8h+arg_18]; Sid
0x1800079c9  mov     r8d, ebp; AccessMask
0x1800079cc  mov     edx, 2; AceRevision
0x1800079d1  mov     rcx, rdi; Acl
0x1800079d4  call    cs:__imp_RtlAddAccessAllowedAce
0x1800079db  nop     dword ptr [rax+rax+00h]
0x1800079e0  mov     rcx, [rsp+0A8h+arg_18]; Sid
0x1800079e8  call    cs:__imp_RtlFreeSid
0x1800079ef  nop     dword ptr [rax+rax+00h]
0x1800079f4  mov     r9, [rsp+0A8h+var_48]; Sid
0x1800079f9  mov     r8d, ebp; AccessMask
0x1800079fc  mov     edx, 2; AceRevision
0x180007a01  mov     rcx, rdi; Acl
0x180007a04  call    cs:__imp_RtlAddAccessAllowedAce
0x180007a0b  nop     dword ptr [rax+rax+00h]
0x180007a10  mov     rcx, [rsp+0A8h+var_48]; Sid
0x180007a15  call    cs:__imp_RtlFreeSid
0x180007a1c  nop     dword ptr [rax+rax+00h]
0x180007a21  xor     r9d, r9d; DaclDefaulted
0x180007a24  lea     rcx, [rsi+10h]; SecurityDescriptor
0x180007a28  mov     r8, rdi; Dacl
0x180007a2b  mov     dl, 1; DaclPresent
0x180007a2d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180007a34  nop     dword ptr [rax+rax+00h]
0x180007a39  mov     ebx, r13d
0x180007a3c  test    r14, r14
0x180007a3f  jz      loc_180007B37
0x180007a45  lea     rax, [rsp+0A8h+var_40]
0x180007a4a  mov     r9d, 2000h; SubAuthority1
0x180007a50  mov     [rsp+0A8h+Sid], rax; Sid
0x180007a55  lea     rcx, stru_18000FD04; IdentifierAuthority
0x180007a5c  mov     [rsp+0A8h+SubAuthority7], r13d; SubAuthority7
0x180007a61  mov     r8d, 200h; SubAuthority0
0x180007a67  mov     [rsp+0A8h+SubAuthority6], r13d; SubAuthority6
0x180007a6c  mov     dl, 2; SubAuthorityCount
0x180007a6e  mov     [rsp+0A8h+SubAuthority5], r13d; SubAuthority5
0x180007a73  mov     [rsp+0A8h+SubAuthority4], r13d; SubAuthority4
0x180007a78  mov     [rsp+0A8h+SubAuthority3], r13d; SubAuthority3
0x180007a7d  mov     [rsp+0A8h+SubAuthority2], r13d; SubAuthority2
0x180007a82  call    cs:__imp_RtlAllocateAndInitializeSid
0x180007a89  nop     dword ptr [rax+rax+00h]
0x180007a8e  test    eax, eax
0x180007a90  js      loc_180007B47
0x180007a96  mov     rcx, [rsp+0A8h+var_40]; Sid
0x180007a9b  call    cs:__imp_RtlLengthSid
0x180007aa2  nop     dword ptr [rax+rax+00h]
0x180007aa7  mov     edx, cs:CsrBaseTag; Flags
0x180007aad  mov     rcx, cs:CsrHeap; HeapHandle
0x180007ab4  lea     ebp, [rax+14h]
0x180007ab7  mov     r8d, ebp; Size
0x180007aba  call    cs:__imp_RtlAllocateHeap
0x180007ac1  nop     dword ptr [rax+rax+00h]
0x180007ac6  mov     rbx, rax
0x180007ac9  test    rax, rax
0x180007acc  jz      short loc_180007B42
0x180007ace  mov     r8d, 2; AclRevision
0x180007ad4  mov     edx, ebp; AclLength
0x180007ad6  mov     rcx, rax; Acl
0x180007ad9  call    cs:__imp_RtlCreateAcl
0x180007ae0  nop     dword ptr [rax+rax+00h]
0x180007ae5  mov     r8d, [r14]
0x180007ae8  mov     edx, 2
0x180007aed  mov     r9, [rsp+0A8h+var_40]
0x180007af2  mov     rcx, rbx
0x180007af5  mov     [rsp+0A8h+SubAuthority3], r8d
0x180007afa  xor     r8d, r8d
0x180007afd  mov     byte ptr [rsp+0A8h+SubAuthority2], 14h
0x180007b02  call    cs:__imp_RtlAddProcessTrustLabelAce
0x180007b09  nop     dword ptr [rax+rax+00h]
0x180007b0e  mov     rcx, [rsp+0A8h+var_40]; Sid
0x180007b13  call    cs:__imp_RtlFreeSid
0x180007b1a  nop     dword ptr [rax+rax+00h]
0x180007b1f  xor     r9d, r9d; SaclDefaulted
0x180007b22  lea     rcx, [rsi+10h]; SecurityDescriptor
0x180007b26  mov     r8, rbx; Sacl
0x180007b29  mov     dl, 1; SaclPresent
0x180007b2b  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x180007b32  nop     dword ptr [rax+rax+00h]
0x180007b37  mov     [rsi], rdi
0x180007b3a  xor     eax, eax
0x180007b3c  mov     [rsi+8], rbx
0x180007b40  jmp     short loc_180007B47
0x180007b42  mov     eax, 0C0000017h
0x180007b47  mov     rbx, [rsp+0A8h+arg_0]
0x180007b4f  add     rsp, 70h
0x180007b53  pop     r15
0x180007b55  pop     r14
0x180007b57  pop     r13
0x180007b59  pop     r12
0x180007b5b  pop     rdi
0x180007b5c  pop     rsi
0x180007b5d  pop     rbp
0x180007b5e  retn
```
