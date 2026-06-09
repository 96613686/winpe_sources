# CsrSetDirectorySecurity

- ea: `0x180007b70`
- end: `0x180007ed0`
- name: `CsrSetDirectorySecurity`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005180`

## callees

- `0x1800035c0`
- `0x180007b70`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180007d0c`
- `ntdll!RtlAllocateHeap` at `0x180007d0c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180007e0b`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180007e0b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007be9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007c34`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007c8e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007be9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007c34`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007c8e`
- `ntdll!NtSetSecurityObject` at `0x180007e2f`
- `ntdll!NtSetSecurityObject` at `0x180007e2f`
- `ntdll!RtlLengthSid` at `0x180007cbd`
- `ntdll!RtlLengthSid` at `0x180007cd0`
- `ntdll!RtlLengthSid` at `0x180007ce3`
- `ntdll!RtlLengthSid` at `0x180007cbd`
- `ntdll!RtlLengthSid` at `0x180007cd0`
- `ntdll!RtlLengthSid` at `0x180007ce3`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007d8b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007dba`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007de6`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007d8b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007dba`
- `ntdll!RtlAddAccessAllowedAce` at `0x180007de6`
- `ntdll!RtlFreeSid` at `0x180007e86`
- `ntdll!RtlFreeSid` at `0x180007eab`
- `ntdll!RtlFreeSid` at `0x180007e86`
- `ntdll!RtlFreeSid` at `0x180007eab`
- `ntdll!RtlFreeHeap` at `0x180007e61`
- `ntdll!RtlFreeHeap` at `0x180007e61`
- `ntdll!RtlCreateAcl` at `0x180007d5c`
- `ntdll!RtlCreateAcl` at `0x180007d5c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007d32`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007d32`

## string_xrefs

- `0x180007e49`: `CsrSetDirectorySecurity`

## pseudocode

```c
__int64 CsrSetDirectorySecurity()
{
  HANDLE v0; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  ULONG v2; // r15d
  ULONG v3; // r15d
  ULONG v4; // r15d
  struct _ACL *Heap; // rax
  struct _ACL *v6; // r14
  PSID v8; // [rsp+68h] [rbp+17h] BYREF
  PSID Sid; // [rsp+70h] [rbp+1Fh] BYREF
  PSID v10; // [rsp+78h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+80h] [rbp+2Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp+37h] BYREF

  v0 = CsrObjectDirectory;
  v8 = 0;
  Sid = 0;
  v10 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 256;
  *(_DWORD *)v11.Value = 0;
  *(_WORD *)&v11.Value[4] = 1280;
  SecurityDescriptor = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v8);
  if ( SecurityDescriptor >= 0 )
  {
    SecurityDescriptor = RtlAllocateAndInitializeSid(&v11, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlAllocateAndInitializeSid(
                             &v11,
                             3u,
                             0x5Au,
                             0,
                             *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL),
                             0,
                             0,
                             0,
                             0,
                             0,
                             &v10);
      if ( SecurityDescriptor >= 0 )
      {
        v2 = RtlLengthSid(v10);
        v3 = RtlLengthSid(Sid) + v2;
        v4 = RtlLengthSid(v8) + v3;
        Heap = (struct _ACL *)RtlAllocateHeap(CsrHeap, (CsrBaseTag + 1310720) | 8, v4 + 84);
        v6 = Heap;
        if ( Heap )
        {
          SecurityDescriptor = RtlCreateSecurityDescriptor(Heap, 1u);
          if ( SecurityDescriptor < 0
            || (SecurityDescriptor = RtlCreateAcl(v6 + 5, v4 + 44, 2u), SecurityDescriptor < 0)
            || (SecurityDescriptor = RtlAddAccessAllowedAce(v6 + 5, 2u, 0x20003u, v8), SecurityDescriptor < 0)
            || (SecurityDescriptor = RtlAddAccessAllowedAce(v6 + 5, 2u, 0xF000Fu, Sid), SecurityDescriptor < 0)
            || (SecurityDescriptor = RtlAddAccessAllowedAce(v6 + 5, 2u, 0xF000Fu, v10), SecurityDescriptor < 0)
            || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(v6, 1u, v6 + 5, 0), SecurityDescriptor < 0)
            || (SecurityDescriptor = NtSetSecurityObject(v0, 4u, v6), SecurityDescriptor < 0) )
          {
            CsrpLogFailure("CsrSetDirectorySecurity");
          }
          RtlFreeHeap(CsrHeap, 0, v6);
        }
        else
        {
          SecurityDescriptor = -1073741801;
        }
      }
      else
      {
        v10 = 0;
      }
    }
    else
    {
      Sid = 0;
    }
    if ( v8 )
      RtlFreeSid(v8);
  }
  else
  {
    v8 = 0;
  }
  if ( Sid )
    RtlFreeSid(Sid);
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x180007b70  mov     r11, rsp
0x180007b73  push    rbp
0x180007b74  push    rbx
0x180007b75  lea     rbp, [r11-5Fh]
0x180007b79  sub     rsp, 98h
0x180007b80  mov     rax, cs:__security_cookie
0x180007b87  xor     rax, rsp
0x180007b8a  mov     [rbp+57h+var_18], rax
0x180007b8e  mov     [r11+8], rsi
0x180007b92  lea     rax, [rbp+57h+var_40]
0x180007b96  xor     esi, esi
0x180007b98  mov     [r11-58h], rax
0x180007b9c  mov     [rsp+0A0h+SubAuthority7], esi; SubAuthority7
0x180007ba0  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x180007ba4  mov     [rsp+0A0h+SubAuthority6], esi; SubAuthority6
0x180007ba8  xor     r9d, r9d; SubAuthority1
0x180007bab  mov     [rsp+0A0h+SubAuthority5], esi; SubAuthority5
0x180007baf  xor     r8d, r8d; SubAuthority0
0x180007bb2  mov     [rsp+0A0h+SubAuthority4], esi; SubAuthority4
0x180007bb6  mov     dl, 1; SubAuthorityCount
0x180007bb8  mov     [r11+10h], rdi
0x180007bbc  mov     rdi, cs:CsrObjectDirectory
0x180007bc3  mov     [rsp+0A0h+SubAuthority3], esi; SubAuthority3
0x180007bc7  mov     [rsp+0A0h+SubAuthority2], esi; SubAuthority2
0x180007bcb  mov     [rbp+57h+var_40], rsi
0x180007bcf  mov     [rbp+57h+Sid], rsi
0x180007bd3  mov     [rbp+57h+var_30], rsi
0x180007bd7  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], esi
0x180007bda  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 100h
0x180007be0  mov     dword ptr [rbp+57h+var_28.Value], esi
0x180007be3  mov     word ptr [rbp+57h+var_28.Value+4], 500h
0x180007be9  call    cs:__imp_RtlAllocateAndInitializeSid
0x180007bf0  nop     dword ptr [rax+rax+00h]
0x180007bf5  mov     ebx, eax
0x180007bf7  test    eax, eax
0x180007bf9  jns     short loc_180007C04
0x180007bfb  mov     [rbp+57h+var_40], rsi
0x180007bff  jmp     loc_180007E92
0x180007c04  lea     rax, [rbp+57h+Sid]
0x180007c08  xor     r9d, r9d; SubAuthority1
0x180007c0b  mov     [rsp+50h], rax; Sid
0x180007c10  lea     rcx, [rbp+57h+var_28]; IdentifierAuthority
0x180007c14  mov     [rsp+0A0h+SubAuthority7], esi; SubAuthority7
0x180007c18  mov     r8d, 12h; SubAuthority0
0x180007c1e  mov     [rsp+0A0h+SubAuthority6], esi; SubAuthority6
0x180007c22  mov     dl, 1; SubAuthorityCount
0x180007c24  mov     [rsp+0A0h+SubAuthority5], esi; SubAuthority5
0x180007c28  mov     [rsp+0A0h+SubAuthority4], esi; SubAuthority4
0x180007c2c  mov     [rsp+0A0h+SubAuthority3], esi; SubAuthority3
0x180007c30  mov     [rsp+0A0h+SubAuthority2], esi; SubAuthority2
0x180007c34  call    cs:__imp_RtlAllocateAndInitializeSid
0x180007c3b  nop     dword ptr [rax+rax+00h]
0x180007c40  mov     ebx, eax
0x180007c42  test    eax, eax
0x180007c44  jns     short loc_180007C4F
0x180007c46  mov     [rbp+57h+Sid], rsi
0x180007c4a  jmp     loc_180007E7D
0x180007c4f  mov     rax, gs:60h
0x180007c58  lea     rcx, [rbp+57h+var_30]
0x180007c5c  mov     [rsp+50h], rcx; Sid
0x180007c61  xor     r9d, r9d; SubAuthority1
0x180007c64  mov     [rsp+0A0h+SubAuthority7], esi; SubAuthority7
0x180007c68  lea     rcx, [rbp+57h+var_28]; IdentifierAuthority
0x180007c6c  mov     [rsp+0A0h+SubAuthority6], esi; SubAuthority6
0x180007c70  mov     r8d, 5Ah ; 'Z'; SubAuthority0
0x180007c76  mov     eax, [rax+2C0h]
0x180007c7c  mov     dl, 3; SubAuthorityCount
0x180007c7e  mov     [rsp+0A0h+SubAuthority5], esi; SubAuthority5
0x180007c82  mov     [rsp+0A0h+SubAuthority4], esi; SubAuthority4
0x180007c86  mov     [rsp+0A0h+SubAuthority3], esi; SubAuthority3
0x180007c8a  mov     [rsp+0A0h+SubAuthority2], eax; SubAuthority2
0x180007c8e  call    cs:__imp_RtlAllocateAndInitializeSid
0x180007c95  nop     dword ptr [rax+rax+00h]
0x180007c9a  mov     ebx, eax
0x180007c9c  test    eax, eax
0x180007c9e  jns     short loc_180007CA9
0x180007ca0  mov     [rbp+57h+var_30], rsi
0x180007ca4  jmp     loc_180007E7D
0x180007ca9  mov     rcx, [rbp+57h+var_30]; Sid
0x180007cad  mov     [rsp+0A0h+arg_10], r14
0x180007cb5  mov     [rsp+90h], r15
0x180007cbd  call    cs:__imp_RtlLengthSid
0x180007cc4  nop     dword ptr [rax+rax+00h]
0x180007cc9  mov     rcx, [rbp+57h+Sid]; Sid
0x180007ccd  mov     r15d, eax
0x180007cd0  call    cs:__imp_RtlLengthSid
0x180007cd7  nop     dword ptr [rax+rax+00h]
0x180007cdc  mov     rcx, [rbp+57h+var_40]; Sid
0x180007ce0  add     r15d, eax
0x180007ce3  call    cs:__imp_RtlLengthSid
0x180007cea  nop     dword ptr [rax+rax+00h]
0x180007cef  mov     edx, cs:CsrBaseTag
0x180007cf5  add     r15d, eax
0x180007cf8  mov     rcx, cs:CsrHeap; HeapHandle
0x180007cff  add     edx, 140000h
0x180007d05  or      edx, 8; Flags
0x180007d08  lea     r8d, [r15+54h]; Size
0x180007d0c  call    cs:__imp_RtlAllocateHeap
0x180007d13  nop     dword ptr [rax+rax+00h]
0x180007d18  mov     r14, rax
0x180007d1b  test    rax, rax
0x180007d1e  jnz     short loc_180007D2A
0x180007d20  mov     ebx, 0C0000017h
0x180007d25  jmp     loc_180007E6D
0x180007d2a  mov     edx, 1; Revision
0x180007d2f  mov     rcx, r14; SecurityDescriptor
0x180007d32  call    cs:__imp_RtlCreateSecurityDescriptor
0x180007d39  nop     dword ptr [rax+rax+00h]
0x180007d3e  mov     ebx, eax
0x180007d40  test    eax, eax
0x180007d42  jns     short loc_180007D4E
0x180007d44  mov     edx, 510h
0x180007d49  jmp     loc_180007E46
0x180007d4e  mov     r8d, 2; AclRevision
0x180007d54  lea     edx, [r15+2Ch]; AclLength
0x180007d58  lea     rcx, [r14+28h]; Acl
0x180007d5c  call    cs:__imp_RtlCreateAcl
0x180007d63  nop     dword ptr [rax+rax+00h]
0x180007d68  mov     ebx, eax
0x180007d6a  test    eax, eax
0x180007d6c  jns     short loc_180007D78
0x180007d6e  mov     edx, 521h
0x180007d73  jmp     loc_180007E46
0x180007d78  mov     r9, [rbp+57h+var_40]; Sid
0x180007d7c  lea     rcx, [r14+28h]; Acl
0x180007d80  mov     edx, 2; AceRevision
0x180007d85  mov     r8d, 20003h; AccessMask
0x180007d8b  call    cs:__imp_RtlAddAccessAllowedAce
0x180007d92  nop     dword ptr [rax+rax+00h]
0x180007d97  mov     ebx, eax
0x180007d99  test    eax, eax
0x180007d9b  jns     short loc_180007DA7
0x180007d9d  mov     edx, 532h
0x180007da2  jmp     loc_180007E46
0x180007da7  mov     r9, [rbp+57h+Sid]; Sid
0x180007dab  lea     rcx, [r14+28h]; Acl
0x180007daf  mov     edx, 2; AceRevision
0x180007db4  mov     r8d, 0F000Fh; AccessMask
0x180007dba  call    cs:__imp_RtlAddAccessAllowedAce
0x180007dc1  nop     dword ptr [rax+rax+00h]
0x180007dc6  mov     ebx, eax
0x180007dc8  test    eax, eax
0x180007dca  jns     short loc_180007DD3
0x180007dcc  mov     edx, 542h
0x180007dd1  jmp     short loc_180007E46
0x180007dd3  mov     r9, [rbp+57h+var_30]; Sid
0x180007dd7  lea     rcx, [r14+28h]; Acl
0x180007ddb  mov     edx, 2; AceRevision
0x180007de0  mov     r8d, 0F000Fh; AccessMask
0x180007de6  call    cs:__imp_RtlAddAccessAllowedAce
0x180007ded  nop     dword ptr [rax+rax+00h]
0x180007df2  mov     ebx, eax
0x180007df4  test    eax, eax
0x180007df6  jns     short loc_180007DFF
0x180007df8  mov     edx, 552h
0x180007dfd  jmp     short loc_180007E46
0x180007dff  xor     r9d, r9d; DaclDefaulted
0x180007e02  lea     r8, [r14+28h]; Dacl
0x180007e06  mov     dl, 1; DaclPresent
0x180007e08  mov     rcx, r14; SecurityDescriptor
0x180007e0b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180007e12  nop     dword ptr [rax+rax+00h]
0x180007e17  mov     ebx, eax
0x180007e19  test    eax, eax
0x180007e1b  jns     short loc_180007E24
0x180007e1d  mov     edx, 566h
0x180007e22  jmp     short loc_180007E46
0x180007e24  mov     r8, r14; SecurityDescriptor
0x180007e27  mov     edx, 4; SecurityInformation
0x180007e2c  mov     rcx, rdi; Handle
0x180007e2f  call    cs:__imp_NtSetSecurityObject
0x180007e36  nop     dword ptr [rax+rax+00h]
0x180007e3b  mov     ebx, eax
0x180007e3d  test    eax, eax
0x180007e3f  jns     short loc_180007E55
0x180007e41  mov     edx, 579h
0x180007e46  mov     r8d, eax
0x180007e49  lea     rcx, aCsrsetdirector; "CsrSetDirectorySecurity"
0x180007e50  call    CsrpLogFailure
0x180007e55  mov     rcx, cs:CsrHeap; HeapHandle
0x180007e5c  mov     r8, r14; BaseAddress
0x180007e5f  xor     edx, edx; Flags
0x180007e61  call    cs:__imp_RtlFreeHeap
0x180007e68  nop     dword ptr [rax+rax+00h]
0x180007e6d  mov     r14, [rsp+0A0h+arg_10]
0x180007e75  mov     r15, [rsp+90h]
0x180007e7d  mov     rcx, [rbp+57h+var_40]; Sid
0x180007e81  test    rcx, rcx
0x180007e84  jz      short loc_180007E92
0x180007e86  call    cs:__imp_RtlFreeSid
0x180007e8d  nop     dword ptr [rax+rax+00h]
0x180007e92  mov     rcx, [rbp+57h+Sid]; Sid
0x180007e96  mov     rdi, [rsp+0A0h+arg_8]
0x180007e9e  mov     rsi, [rsp+0A0h+arg_0]
0x180007ea6  test    rcx, rcx
0x180007ea9  jz      short loc_180007EB7
0x180007eab  call    cs:__imp_RtlFreeSid
0x180007eb2  nop     dword ptr [rax+rax+00h]
0x180007eb7  mov     eax, ebx
0x180007eb9  mov     rcx, [rbp+57h+var_18]
0x180007ebd  xor     rcx, rsp; StackCookie
0x180007ec0  call    __security_check_cookie
0x180007ec5  add     rsp, 98h
0x180007ecc  pop     rbx
0x180007ecd  pop     rbp
0x180007ece  retn
```
