# CRegistryObject::AddAdministratorsToPerms(void)

- ea: `0x180312a48`
- end: `0x180312ca2`
- name: `?AddAdministratorsToPerms@CRegistryObject@@AEAAJXZ`
- size: `602`
- prototype: `NTSTATUS __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180314350`

## callees

- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180312a48`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180312b56`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180312b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180312b60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180312b60`
- `ntdll!RtlAllocateHeap` at `0x180312abd`
- `ntdll!RtlAllocateHeap` at `0x180312b10`
- `ntdll!RtlAllocateHeap` at `0x180312b8a`
- `ntdll!RtlAllocateHeap` at `0x180312abd`
- `ntdll!RtlAllocateHeap` at `0x180312b10`
- `ntdll!RtlAllocateHeap` at `0x180312b8a`
- `ntdll!RtlLengthRequiredSid` at `0x180312b72`
- `ntdll!RtlLengthRequiredSid` at `0x180312b72`
- `ntdll!NtSetSecurityObject` at `0x180312c33`
- `ntdll!NtSetSecurityObject` at `0x180312c33`
- `ntdll!RtlGetAce` at `0x180312bf3`
- `ntdll!RtlGetAce` at `0x180312bf3`
- `ntdll!RtlInitializeSid` at `0x180312bac`
- `ntdll!RtlInitializeSid` at `0x180312bac`
- `ntdll!RtlFreeHeap` at `0x180312c5a`
- `ntdll!RtlFreeHeap` at `0x180312c72`
- `ntdll!RtlFreeHeap` at `0x180312c5a`
- `ntdll!RtlFreeHeap` at `0x180312c72`
- `ntdll!RtlSubAuthoritySid` at `0x180312bb7`
- `ntdll!RtlSubAuthoritySid` at `0x180312bcb`
- `ntdll!RtlSubAuthoritySid` at `0x180312bb7`
- `ntdll!RtlSubAuthoritySid` at `0x180312bcb`
- `ntdll!NtQuerySecurityObject` at `0x180312a8e`
- `ntdll!NtQuerySecurityObject` at `0x180312aee`
- `ntdll!NtQuerySecurityObject` at `0x180312a8e`
- `ntdll!NtQuerySecurityObject` at `0x180312aee`
- `ntdll!RtlEqualSid` at `0x180312c0f`
- `ntdll!RtlEqualSid` at `0x180312c0f`

## pseudocode

```c
NTSTATUS __fastcall CRegistryObject::AddAdministratorsToPerms(HANDLE *this)
{
  ULONG *LengthNeeded; // rdi
  NTSTATUS result; // eax
  PVOID Heap; // rax
  int SecurityObject; // ebx
  PVOID v6; // rax
  void *v7; // r14
  ULONG v8; // eax
  PVOID v9; // rax
  void *v10; // r15
  ULONG v11; // edi
  NTSTATUS v12; // eax
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-38h] BYREF
  WINBOOL bDaclPresent; // [rsp+34h] [rbp-34h] BYREF
  PVOID Ace; // [rsp+38h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+48h] [rbp-20h] BYREF

  LengthNeeded = (ULONG *)(this + 1);
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  result = NtQuerySecurityObject(*this, 4u, 0, 0, (PULONG)this + 2);
  if ( (int)(result + 0x80000000) < 0 || result == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *LengthNeeded);
    this[2] = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, *LengthNeeded);
      SecurityObject = NtQuerySecurityObject(*this, 4u, this[2], *LengthNeeded, LengthNeeded);
      if ( SecurityObject < 0 )
        return SecurityObject;
      v6 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *LengthNeeded);
      v7 = v6;
      if ( v6 )
      {
        memcpy_0(v6, this[2], *LengthNeeded);
        bDaclPresent = 0;
        bDaclDefaulted = 0;
        pDacl = 0;
        if ( GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          v8 = RtlLengthRequiredSid(2u);
          v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
          v10 = v9;
          if ( v9 )
          {
            RtlInitializeSid(v9, &IdentifierAuthority, 2u);
            *RtlSubAuthoritySid(v10, 0) = 32;
            v11 = 0;
            *RtlSubAuthoritySid(v10, 1u) = 544;
            while ( v11 < pDacl->AceCount )
            {
              Ace = 0;
              SecurityObject = RtlGetAce(pDacl, v11, &Ace);
              if ( SecurityObject < 0 )
                goto LABEL_18;
              if ( !*(_BYTE *)Ace )
              {
                if ( RtlEqualSid((char *)Ace + 8, v10) )
                  *((_DWORD *)Ace + 1) = 393241;
              }
              ++v11;
            }
            v12 = NtSetSecurityObject(*this, 4u, v7);
            ++CRegistryObject::_ulKeysWithPermChange;
            SecurityObject = v12;
            *((_DWORD *)this + 6) = 1;
LABEL_18:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
          }
          else
          {
            SecurityObject = -1073741801;
          }
        }
        else
        {
          SecurityObject = GetLastError();
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        if ( SecurityObject >= 0 )
          return 0;
        return SecurityObject;
      }
    }
    return -1073741801;
  }
  return result;
}

```

## disassembly

```asm
0x180312a48  push    rbp
0x180312a4a  push    rbx
0x180312a4b  push    rsi
0x180312a4c  push    rdi
0x180312a4d  push    r14
0x180312a4f  push    r15
0x180312a51  mov     rbp, rsp
0x180312a54  sub     rsp, 68h
0x180312a58  mov     rax, cs:__security_cookie
0x180312a5f  xor     rax, rsp
0x180312a62  mov     [rbp+var_18], rax
0x180312a66  lea     rdi, [rcx+8]
0x180312a6a  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x180312a71  xor     r9d, r9d; Length
0x180312a74  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180312a7a  mov     rsi, rcx
0x180312a7d  mov     [rsp+68h+LengthNeeded], rdi; LengthNeeded
0x180312a82  mov     rcx, [rcx]; Handle
0x180312a85  xor     r8d, r8d; SecurityDescriptor
0x180312a88  lea     ebx, [r9+4]
0x180312a8c  mov     edx, ebx; SecurityInformation
0x180312a8e  call    cs:__imp_NtQuerySecurityObject
0x180312a94  mov     edx, 80000000h
0x180312a99  lea     ecx, [rax+rdx]
0x180312a9c  test    edx, ecx
0x180312a9e  jnz     short loc_180312AAB
0x180312aa0  cmp     eax, 0C0000023h
0x180312aa5  jnz     loc_180312C89
0x180312aab  mov     rcx, gs:60h
0x180312ab4  xor     edx, edx; Flags
0x180312ab6  mov     r8d, [rdi]; Size
0x180312ab9  mov     rcx, [rcx+30h]; HeapHandle
0x180312abd  call    cs:__imp_RtlAllocateHeap
0x180312ac3  mov     [rsi+10h], rax
0x180312ac7  test    rax, rax
0x180312aca  jz      loc_180312C84
0x180312ad0  mov     r8d, [rdi]; Size
0x180312ad3  xor     edx, edx; Val
0x180312ad5  mov     rcx, rax; void *
0x180312ad8  call    memset_0
0x180312add  mov     r9d, [rdi]; Length
0x180312ae0  mov     edx, ebx; SecurityInformation
0x180312ae2  mov     r8, [rsi+10h]; SecurityDescriptor
0x180312ae6  mov     rcx, [rsi]; Handle
0x180312ae9  mov     [rsp+68h+LengthNeeded], rdi; LengthNeeded
0x180312aee  call    cs:__imp_NtQuerySecurityObject
0x180312af4  mov     ebx, eax
0x180312af6  test    eax, eax
0x180312af8  js      loc_180312C80
0x180312afe  mov     rcx, gs:60h
0x180312b07  xor     edx, edx; Flags
0x180312b09  mov     r8d, [rdi]; Size
0x180312b0c  mov     rcx, [rcx+30h]; HeapHandle
0x180312b10  call    cs:__imp_RtlAllocateHeap
0x180312b16  mov     r14, rax
0x180312b19  test    rax, rax
0x180312b1c  jz      loc_180312C84
0x180312b22  mov     r8d, [rdi]; Size
0x180312b25  mov     rcx, rax; void *
0x180312b28  mov     rdx, [rsi+10h]; Src
0x180312b2c  call    memcpy_0
0x180312b31  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180312b35  mov     [rbp+bDaclPresent], 0
0x180312b3c  lea     r8, [rbp+pDacl]; pDacl
0x180312b40  mov     [rbp+bDaclDefaulted], 0
0x180312b47  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180312b4b  mov     [rbp+pDacl], 0
0x180312b53  mov     rcx, r14; pSecurityDescriptor
0x180312b56  call    cs:__imp_GetSecurityDescriptorDacl
0x180312b5c  test    eax, eax
0x180312b5e  jnz     short loc_180312B6D
0x180312b60  call    cs:__imp_GetLastError
0x180312b66  mov     ebx, eax
0x180312b68  jmp     loc_180312C60
0x180312b6d  mov     ecx, 2; SubAuthorityCount
0x180312b72  call    cs:__imp_RtlLengthRequiredSid
0x180312b78  mov     rcx, gs:60h
0x180312b81  xor     edx, edx; Flags
0x180312b83  mov     r8d, eax; Size
0x180312b86  mov     rcx, [rcx+30h]; HeapHandle
0x180312b8a  call    cs:__imp_RtlAllocateHeap
0x180312b90  mov     r15, rax
0x180312b93  test    rax, rax
0x180312b96  jnz     short loc_180312BA2
0x180312b98  mov     ebx, 0C0000017h
0x180312b9d  jmp     loc_180312C60
0x180312ba2  mov     r8b, 2; SubAuthorityCount
0x180312ba5  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180312ba9  mov     rcx, r15; Sid
0x180312bac  call    cs:__imp_RtlInitializeSid
0x180312bb2  xor     edx, edx; SubAuthority
0x180312bb4  mov     rcx, r15; Sid
0x180312bb7  call    cs:__imp_RtlSubAuthoritySid
0x180312bbd  mov     edx, 1; SubAuthority
0x180312bc2  mov     rcx, r15; Sid
0x180312bc5  mov     dword ptr [rax], 20h ; ' '
0x180312bcb  call    cs:__imp_RtlSubAuthoritySid
0x180312bd1  xor     edi, edi
0x180312bd3  mov     dword ptr [rax], 220h
0x180312bd9  mov     rcx, [rbp+pDacl]; Acl
0x180312bdd  movzx   eax, word ptr [rcx+4]
0x180312be1  cmp     edi, eax
0x180312be3  jnb     short loc_180312C28
0x180312be5  lea     r8, [rbp+Ace]; Ace
0x180312be9  mov     [rbp+Ace], 0
0x180312bf1  mov     edx, edi; AceIndex
0x180312bf3  call    cs:__imp_RtlGetAce
0x180312bf9  mov     ebx, eax
0x180312bfb  test    eax, eax
0x180312bfd  js      short loc_180312C48
0x180312bff  mov     rcx, [rbp+Ace]
0x180312c03  cmp     byte ptr [rcx], 0
0x180312c06  jnz     short loc_180312C24
0x180312c08  add     rcx, 8; Sid1
0x180312c0c  mov     rdx, r15; Sid2
0x180312c0f  call    cs:__imp_RtlEqualSid
0x180312c15  test    al, al
0x180312c17  jz      short loc_180312C24
0x180312c19  mov     rax, [rbp+Ace]
0x180312c1d  mov     dword ptr [rax+4], 60019h
0x180312c24  inc     edi
0x180312c26  jmp     short loc_180312BD9
0x180312c28  mov     rcx, [rsi]; Handle
0x180312c2b  mov     r8, r14; SecurityDescriptor
0x180312c2e  mov     edx, 4; SecurityInformation
0x180312c33  call    cs:__imp_NtSetSecurityObject
0x180312c39  inc     cs:?_ulKeysWithPermChange@CRegistryObject@@0KA; ulong CRegistryObject::_ulKeysWithPermChange
0x180312c3f  mov     ebx, eax
0x180312c41  mov     dword ptr [rsi+18h], 1
0x180312c48  mov     rcx, gs:60h
0x180312c51  mov     r8, r15; P
0x180312c54  xor     edx, edx; Flags
0x180312c56  mov     rcx, [rcx+30h]; HeapHandle
0x180312c5a  call    cs:__imp_RtlFreeHeap
0x180312c60  mov     rcx, gs:60h
0x180312c69  mov     r8, r14; P
0x180312c6c  xor     edx, edx; Flags
0x180312c6e  mov     rcx, [rcx+30h]; HeapHandle
0x180312c72  call    cs:__imp_RtlFreeHeap
0x180312c78  test    ebx, ebx
0x180312c7a  js      short loc_180312C80
0x180312c7c  xor     eax, eax
0x180312c7e  jmp     short loc_180312C89
0x180312c80  mov     eax, ebx
0x180312c82  jmp     short loc_180312C89
0x180312c84  mov     eax, 0C0000017h
0x180312c89  mov     rcx, [rbp+var_18]
0x180312c8d  xor     rcx, rsp; StackCookie
0x180312c90  call    __security_check_cookie
0x180312c95  add     rsp, 68h
0x180312c99  pop     r15
0x180312c9b  pop     r14
0x180312c9d  pop     rdi
0x180312c9e  pop     rsi
0x180312c9f  pop     rbx
0x180312ca0  pop     rbp
0x180312ca1  retn
```
