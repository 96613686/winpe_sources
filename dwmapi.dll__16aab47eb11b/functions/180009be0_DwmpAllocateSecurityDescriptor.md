# DwmpAllocateSecurityDescriptor

- ea: `0x180009be0`
- end: `0x180009dad`
- name: `DwmpAllocateSecurityDescriptor`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013570`

## callees

- `0x180003370`
- `0x180009be0`
- `0x18000d0a0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x180009d7d`
- `ntdll!RtlFreeSid` at `0x180009d7d`
- `ntdll!RtlFreeHeap` at `0x180009d67`
- `ntdll!RtlFreeHeap` at `0x180009d67`
- `ntdll!RtlAddAccessAllowedAce` at `0x180009d1f`
- `ntdll!RtlAddAccessAllowedAce` at `0x180009d1f`
- `ntdll!RtlCreateAcl` at `0x180009cfd`
- `ntdll!RtlCreateAcl` at `0x180009cfd`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180009cda`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180009cda`
- `ntdll!RtlAllocateHeap` at `0x180009cba`
- `ntdll!RtlAllocateHeap` at `0x180009cba`
- `ntdll!RtlLengthSid` at `0x180009c9b`
- `ntdll!RtlLengthSid` at `0x180009c9b`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180009c76`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180009c76`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180009d3d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180009d3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d59`

## pseudocode

```c
__int64 __fastcall DwmpAllocateSecurityDescriptor(struct _ACL **a1, ACCESS_MASK a2)
{
  NTSTATUS v4; // ebx
  unsigned int v5; // ebx
  unsigned int v6; // edx
  ULONG v7; // eax
  ULONG v8; // r14d
  ULONG v9; // ebx
  HANDLE ProcessHeap; // rax
  struct _ACL *Heap; // rax
  struct _ACL *v12; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  unsigned int v14; // edx
  HANDLE v15; // rax
  PSID Sid; // [rsp+60h] [rbp-20h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  Sid = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v4 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 3u, 0x5Au, 0, NtCurrentPeb()->SessionId, 0, 0, 0, 0, 0, &Sid);
  if ( v4 < 0 )
  {
    v5 = v4 | 0x10000000;
    v6 = 48;
LABEL_3:
    DoStackCaptureDirect(v5, v6);
    goto LABEL_16;
  }
  v7 = RtlLengthSid(Sid);
  v8 = v7 + 20;
  v9 = v7 + 60;
  ProcessHeap = GetProcessHeap();
  Heap = (struct _ACL *)RtlAllocateHeap(ProcessHeap, 8u, v9);
  v12 = Heap;
  if ( !Heap )
  {
    v5 = -2147024882;
    v6 = 58;
    goto LABEL_3;
  }
  SecurityDescriptor = RtlCreateSecurityDescriptor(Heap, 1u);
  if ( SecurityDescriptor < 0 )
  {
    v14 = 60;
LABEL_14:
    v5 = SecurityDescriptor | 0x10000000;
    DoStackCaptureDirect(v5, v14);
    v15 = GetProcessHeap();
    RtlFreeHeap(v15, 0, v12);
    goto LABEL_16;
  }
  SecurityDescriptor = RtlCreateAcl(v12 + 5, v8, 2u);
  if ( SecurityDescriptor < 0 )
  {
    v14 = 64;
    goto LABEL_14;
  }
  SecurityDescriptor = RtlAddAccessAllowedAce(v12 + 5, 2u, a2, Sid);
  if ( SecurityDescriptor < 0 )
  {
    v14 = 69;
    goto LABEL_14;
  }
  SecurityDescriptor = RtlSetDaclSecurityDescriptor(v12, 1u, v12 + 5, 0);
  if ( SecurityDescriptor < 0 )
  {
    v14 = 71;
    goto LABEL_14;
  }
  v5 = 0;
  *a1 = v12;
LABEL_16:
  if ( Sid )
    RtlFreeSid(Sid);
  return v5;
}

```

## disassembly

```asm
0x180009be0  mov     [rsp-28h+arg_10], rbx
0x180009be5  mov     [rsp-28h+arg_18], rsi
0x180009bea  push    rbp
0x180009beb  push    rdi
0x180009bec  push    r12
0x180009bee  push    r14
0x180009bf0  push    r15
0x180009bf2  mov     rbp, rsp
0x180009bf5  sub     rsp, 80h
0x180009bfc  mov     rax, cs:__security_cookie
0x180009c03  xor     rax, rsp
0x180009c06  mov     [rbp+var_10], rax
0x180009c0a  mov     r15, rcx
0x180009c0d  mov     [rbp+var_20], 0
0x180009c15  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x180009c1c  lea     rcx, [rbp+var_20]
0x180009c20  mov     [rsp+80h+Sid], rcx; Sid
0x180009c25  xor     r9d, r9d; SubAuthority1
0x180009c28  mov     [rsp+80h+SubAuthority7], 0; SubAuthority7
0x180009c30  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180009c34  mov     [rsp+80h+SubAuthority6], 0; SubAuthority6
0x180009c3c  mov     r12d, edx
0x180009c3f  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180009c45  mov     dl, 3; SubAuthorityCount
0x180009c47  mov     rax, gs:60h
0x180009c50  lea     r8d, [r9+5Ah]; SubAuthority0
0x180009c54  mov     [rsp+80h+SubAuthority5], 0; SubAuthority5
0x180009c5c  mov     [rsp+80h+SubAuthority4], 0; SubAuthority4
0x180009c64  mov     [rsp+80h+SubAuthority3], 0; SubAuthority3
0x180009c6c  mov     eax, [rax+2C0h]
0x180009c72  mov     [rsp+80h+SubAuthority2], eax; SubAuthority2
0x180009c76  call    cs:__imp_RtlAllocateAndInitializeSid
0x180009c7c  mov     ebx, eax
0x180009c7e  test    eax, eax
0x180009c80  jns     short loc_180009C97
0x180009c82  bts     ebx, 1Ch
0x180009c86  mov     edx, 30h ; '0'; unsigned int
0x180009c8b  mov     ecx, ebx; int
0x180009c8d  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180009c92  jmp     loc_180009D74
0x180009c97  mov     rcx, [rbp+var_20]; Sid
0x180009c9b  call    cs:__imp_RtlLengthSid
0x180009ca1  lea     r14d, [rax+14h]
0x180009ca5  lea     ebx, [r14+28h]
0x180009ca9  call    cs:__imp_GetProcessHeap
0x180009caf  mov     r8d, ebx; Size
0x180009cb2  mov     edx, 8; Flags
0x180009cb7  mov     rcx, rax; HeapHandle
0x180009cba  call    cs:__imp_RtlAllocateHeap
0x180009cc0  mov     rdi, rax
0x180009cc3  test    rax, rax
0x180009cc6  jnz     short loc_180009CD2
0x180009cc8  mov     ebx, 8007000Eh
0x180009ccd  lea     edx, [rax+3Ah]
0x180009cd0  jmp     short loc_180009C8B
0x180009cd2  mov     edx, 1; Revision
0x180009cd7  mov     rcx, rdi; SecurityDescriptor
0x180009cda  call    cs:__imp_RtlCreateSecurityDescriptor
0x180009ce0  mov     ebx, eax
0x180009ce2  test    eax, eax
0x180009ce4  jns     short loc_180009CED
0x180009ce6  mov     edx, 3Ch ; '<'
0x180009ceb  jmp     short loc_180009D4E
0x180009ced  lea     rsi, [rdi+28h]
0x180009cf1  mov     r8d, 2; AclRevision
0x180009cf7  mov     rcx, rsi; Acl
0x180009cfa  mov     edx, r14d; AclSize
0x180009cfd  call    cs:__imp_RtlCreateAcl
0x180009d03  mov     ebx, eax
0x180009d05  test    eax, eax
0x180009d07  jns     short loc_180009D10
0x180009d09  mov     edx, 40h ; '@'
0x180009d0e  jmp     short loc_180009D4E
0x180009d10  mov     r9, [rbp+var_20]; Sid
0x180009d14  mov     r8d, r12d; AccessMask
0x180009d17  mov     edx, 2; Revision
0x180009d1c  mov     rcx, rsi; Acl
0x180009d1f  call    cs:__imp_RtlAddAccessAllowedAce
0x180009d25  mov     ebx, eax
0x180009d27  test    eax, eax
0x180009d29  jns     short loc_180009D32
0x180009d2b  mov     edx, 45h ; 'E'
0x180009d30  jmp     short loc_180009D4E
0x180009d32  xor     r9d, r9d; DaclDefaulted
0x180009d35  mov     r8, rsi; Dacl
0x180009d38  mov     dl, 1; DaclPresent
0x180009d3a  mov     rcx, rdi; SecurityDescriptor
0x180009d3d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180009d43  mov     ebx, eax
0x180009d45  test    eax, eax
0x180009d47  jns     short loc_180009D6F
0x180009d49  mov     edx, 47h ; 'G'; unsigned int
0x180009d4e  bts     ebx, 1Ch
0x180009d52  mov     ecx, ebx; int
0x180009d54  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180009d59  call    cs:__imp_GetProcessHeap
0x180009d5f  mov     r8, rdi; P
0x180009d62  xor     edx, edx; Flags
0x180009d64  mov     rcx, rax; HeapHandle
0x180009d67  call    cs:__imp_RtlFreeHeap
0x180009d6d  jmp     short loc_180009D74
0x180009d6f  xor     ebx, ebx
0x180009d71  mov     [r15], rdi
0x180009d74  mov     rcx, [rbp+var_20]; Sid
0x180009d78  test    rcx, rcx
0x180009d7b  jz      short loc_180009D83
0x180009d7d  call    cs:__imp_RtlFreeSid
0x180009d83  mov     eax, ebx
0x180009d85  mov     rcx, [rbp+var_10]
0x180009d89  xor     rcx, rsp; StackCookie
0x180009d8c  call    __security_check_cookie
0x180009d91  lea     r11, [rsp+80h+var_s0]
0x180009d99  mov     rbx, [r11+40h]
0x180009d9d  mov     rsi, [r11+48h]
0x180009da1  mov     rsp, r11
0x180009da4  pop     r15
0x180009da6  pop     r14
0x180009da8  pop     r12
0x180009daa  pop     rdi
0x180009dab  pop     rbp
0x180009dac  retn
```
