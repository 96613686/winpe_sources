# BiCreateKeySecurityDescriptor

- ea: `0x180032604`
- end: `0x180032906`
- name: `BiCreateKeySecurityDescriptor`
- size: `770`
- prototype: `__int64 __fastcall(ACCESS_MASK AccessMask)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003223c`
- `0x1800322e4`
- `0x180033914`

## callees

- `0x180002690`
- `0x180003bb5`
- `0x180032604`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x1800327d3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1800327d3`
- `ntdll!RtlCreateAcl` at `0x18003275a`
- `ntdll!RtlCreateAcl` at `0x18003275a`
- `ntdll!RtlFreeSid` at `0x18003288e`
- `ntdll!RtlFreeSid` at `0x1800328a3`
- `ntdll!RtlFreeSid` at `0x18003288e`
- `ntdll!RtlFreeSid` at `0x1800328a3`
- `ntdll!RtlLengthSid` at `0x1800326e1`
- `ntdll!RtlLengthSid` at `0x1800326f3`
- `ntdll!RtlLengthSid` at `0x180032708`
- `ntdll!RtlLengthSid` at `0x18003281b`
- `ntdll!RtlLengthSid` at `0x18003284d`
- `ntdll!RtlLengthSid` at `0x1800326e1`
- `ntdll!RtlLengthSid` at `0x1800326f3`
- `ntdll!RtlLengthSid` at `0x180032708`
- `ntdll!RtlLengthSid` at `0x18003281b`
- `ntdll!RtlLengthSid` at `0x18003284d`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18003267c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800326c7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18003267c`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800326c7`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180032786`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800327b5`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180032786`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800327b5`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800327f4`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800327f4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180032871`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180032871`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180032809`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180032838`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180032809`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180032838`
- `ntdll!RtlFreeHeap` at `0x1800328cf`
- `ntdll!RtlFreeHeap` at `0x1800328cf`
- `ntdll!RtlAllocateHeap` at `0x18003272d`
- `ntdll!RtlAllocateHeap` at `0x18003272d`

## pseudocode

```c
struct _ACL *__fastcall BiCreateKeySecurityDescriptor(ACCESS_MASK AccessMask)
{
  struct _ACL *v2; // rdi
  NTSTATUS Acl; // ebx
  ULONG v4; // ebx
  ULONG v5; // ebx
  ULONG v6; // r15d
  struct _ACL *Heap; // rax
  struct _ACL *v8; // rsi
  ULONG v9; // ebx
  char *v10; // rbx
  ULONG v11; // eax
  PSID pSid; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = 0;
  pSid = 0;
  Sid = 0;
  Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid);
  if ( Acl >= 0 )
  {
    Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
    if ( Acl >= 0 )
    {
      v4 = RtlLengthSid(Sid);
      v5 = RtlLengthSid(pSid) + 24 + v4;
      v6 = v5 + RtlLengthSid(pSid) + 40;
      Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v2 = Heap;
      if ( Heap )
      {
        v8 = Heap + 5;
        Acl = RtlCreateAcl(Heap + 5, v5, 2u);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v8, 2u, 0, AccessMask, pSid);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v8, 2u, 0, 0xF003Fu, Sid);
            if ( Acl >= 0 )
            {
              Acl = RtlCreateSecurityDescriptor(v2, 1u);
              if ( Acl >= 0 )
              {
                Acl = RtlSetDaclSecurityDescriptor(v2, 1u, v8, 0);
                if ( Acl >= 0 )
                {
                  v9 = RtlLengthSecurityDescriptor(v2);
                  if ( RtlLengthSid(pSid) + v9 >= v6 )
                  {
                    v10 = (char *)v2 + RtlLengthSecurityDescriptor(v2);
                    v11 = RtlLengthSid(pSid);
                    memcpy_0(v10, pSid, v11);
                    Acl = RtlSetOwnerSecurityDescriptor(v2, v10, 0);
                    if ( Acl >= 0 )
                      Acl = 0;
                  }
                  else
                  {
                    Acl = -1073741789;
                  }
                }
              }
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
  if ( pSid )
    RtlFreeSid(pSid);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Acl >= 0 )
    return v2;
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  return 0;
}

```

## disassembly

```asm
0x180032604  mov     r11, rsp
0x180032607  mov     [r11+10h], rbx
0x18003260b  mov     [r11+18h], rsi
0x18003260f  push    rbp
0x180032610  push    rdi
0x180032611  push    r12
0x180032613  push    r14
0x180032615  push    r15
0x180032617  mov     rbp, rsp
0x18003261a  sub     rsp, 80h
0x180032621  mov     rax, cs:__security_cookie
0x180032628  xor     rax, rsp
0x18003262b  mov     [rbp+var_8], rax
0x18003262f  xor     r12d, r12d
0x180032632  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180032638  lea     rax, [rbp+pSid]
0x18003263c  mov     dword ptr [rbp+IdentifierAuthority.Value], r12d
0x180032640  mov     [r11-58h], rax
0x180032644  mov     r14d, ecx
0x180032647  mov     [r11-60h], r12d
0x18003264b  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18003264f  mov     [r11-68h], r12d
0x180032653  lea     r8d, [r12+20h]; SubAuthority0
0x180032658  mov     [r11-70h], r12d
0x18003265c  mov     r9d, 220h; SubAuthority1
0x180032662  mov     [r11-78h], r12d
0x180032666  mov     dl, 2; SubAuthorityCount
0x180032668  mov     [r11-80h], r12d
0x18003266c  mov     edi, r12d
0x18003266f  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x180032674  mov     [rbp+pSid], r12
0x180032678  mov     [rbp+var_18], r12
0x18003267c  call    cs:__imp_RtlAllocateAndInitializeSid
0x180032683  nop     dword ptr [rax+rax+00h]
0x180032688  mov     ebx, eax
0x18003268a  test    eax, eax
0x18003268c  js      loc_180032885
0x180032692  lea     rax, [rbp+var_18]
0x180032696  xor     r9d, r9d; SubAuthority1
0x180032699  mov     [rsp+80h+Sid], rax; Sid
0x18003269e  lea     r8d, [r12+12h]; SubAuthority0
0x1800326a3  mov     [rsp+80h+SubAuthority7], r12d; SubAuthority7
0x1800326a8  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1800326ac  mov     [rsp+80h+SubAuthority6], r12d; SubAuthority6
0x1800326b1  mov     dl, 1; SubAuthorityCount
0x1800326b3  mov     [rsp+80h+SubAuthority5], r12d; SubAuthority5
0x1800326b8  mov     [rsp+80h+SubAuthority4], r12d; SubAuthority4
0x1800326bd  mov     [rsp+80h+SubAuthority3], r12d; SubAuthority3
0x1800326c2  mov     [rsp+80h+SubAuthority2], r12d; SubAuthority2
0x1800326c7  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800326ce  nop     dword ptr [rax+rax+00h]
0x1800326d3  mov     ebx, eax
0x1800326d5  test    eax, eax
0x1800326d7  js      loc_180032885
0x1800326dd  mov     rcx, [rbp+var_18]; Sid
0x1800326e1  call    cs:__imp_RtlLengthSid
0x1800326e8  nop     dword ptr [rax+rax+00h]
0x1800326ed  mov     rcx, [rbp+pSid]; Sid
0x1800326f1  mov     ebx, eax
0x1800326f3  call    cs:__imp_RtlLengthSid
0x1800326fa  nop     dword ptr [rax+rax+00h]
0x1800326ff  mov     rcx, [rbp+pSid]; Sid
0x180032703  add     eax, 18h
0x180032706  add     ebx, eax
0x180032708  call    cs:__imp_RtlLengthSid
0x18003270f  nop     dword ptr [rax+rax+00h]
0x180032714  mov     rcx, gs:60h
0x18003271d  xor     edx, edx; Flags
0x18003271f  lea     r15d, [rax+28h]
0x180032723  mov     rcx, [rcx+30h]; HeapHandle
0x180032727  add     r15d, ebx
0x18003272a  mov     r8d, r15d; Size
0x18003272d  call    cs:__imp_RtlAllocateHeap
0x180032734  nop     dword ptr [rax+rax+00h]
0x180032739  mov     rdi, rax
0x18003273c  test    rax, rax
0x18003273f  jnz     short loc_18003274B
0x180032741  mov     ebx, 0C000009Ah
0x180032746  jmp     loc_180032885
0x18003274b  lea     rsi, [rax+28h]
0x18003274f  mov     r8d, 2; AclRevision
0x180032755  mov     rcx, rsi; Acl
0x180032758  mov     edx, ebx; AclSize
0x18003275a  call    cs:__imp_RtlCreateAcl
0x180032761  nop     dword ptr [rax+rax+00h]
0x180032766  mov     ebx, eax
0x180032768  test    eax, eax
0x18003276a  js      loc_180032885
0x180032770  mov     rax, [rbp+pSid]
0x180032774  xor     r8d, r8d; AceFlags
0x180032777  mov     r9d, r14d; AccessMask
0x18003277a  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x18003277f  mov     rcx, rsi; pAcl
0x180032782  lea     edx, [r8+2]; dwAceRevision
0x180032786  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18003278d  nop     dword ptr [rax+rax+00h]
0x180032792  mov     ebx, eax
0x180032794  test    eax, eax
0x180032796  js      loc_180032885
0x18003279c  mov     rax, [rbp+var_18]
0x1800327a0  xor     r8d, r8d; AceFlags
0x1800327a3  mov     r9d, 0F003Fh; AccessMask
0x1800327a9  mov     qword ptr [rsp+80h+SubAuthority2], rax; pSid
0x1800327ae  mov     rcx, rsi; pAcl
0x1800327b1  lea     edx, [r8+2]; dwAceRevision
0x1800327b5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800327bc  nop     dword ptr [rax+rax+00h]
0x1800327c1  mov     ebx, eax
0x1800327c3  test    eax, eax
0x1800327c5  js      loc_180032885
0x1800327cb  mov     edx, 1; Revision
0x1800327d0  mov     rcx, rdi; SecurityDescriptor
0x1800327d3  call    cs:__imp_RtlCreateSecurityDescriptor
0x1800327da  nop     dword ptr [rax+rax+00h]
0x1800327df  mov     ebx, eax
0x1800327e1  test    eax, eax
0x1800327e3  js      loc_180032885
0x1800327e9  xor     r9d, r9d; DaclDefaulted
0x1800327ec  mov     r8, rsi; Dacl
0x1800327ef  mov     dl, 1; DaclPresent
0x1800327f1  mov     rcx, rdi; SecurityDescriptor
0x1800327f4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800327fb  nop     dword ptr [rax+rax+00h]
0x180032800  mov     ebx, eax
0x180032802  test    eax, eax
0x180032804  js      short loc_180032885
0x180032806  mov     rcx, rdi; SecurityDescriptor
0x180032809  call    cs:__imp_RtlLengthSecurityDescriptor
0x180032810  nop     dword ptr [rax+rax+00h]
0x180032815  mov     rcx, [rbp+pSid]; Sid
0x180032819  mov     ebx, eax
0x18003281b  call    cs:__imp_RtlLengthSid
0x180032822  nop     dword ptr [rax+rax+00h]
0x180032827  add     ebx, eax
0x180032829  cmp     ebx, r15d
0x18003282c  jnb     short loc_180032835
0x18003282e  mov     ebx, 0C0000023h
0x180032833  jmp     short loc_180032885
0x180032835  mov     rcx, rdi; SecurityDescriptor
0x180032838  call    cs:__imp_RtlLengthSecurityDescriptor
0x18003283f  nop     dword ptr [rax+rax+00h]
0x180032844  mov     rcx, [rbp+pSid]; Sid
0x180032848  mov     ebx, eax
0x18003284a  add     rbx, rdi
0x18003284d  call    cs:__imp_RtlLengthSid
0x180032854  nop     dword ptr [rax+rax+00h]
0x180032859  mov     rdx, [rbp+pSid]; Src
0x18003285d  mov     rcx, rbx; void *
0x180032860  mov     r8d, eax; Size
0x180032863  call    memcpy_0
0x180032868  xor     r8d, r8d; OwnerDefaulted
0x18003286b  mov     rdx, rbx; Owner
0x18003286e  mov     rcx, rdi; SecurityDescriptor
0x180032871  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180032878  nop     dword ptr [rax+rax+00h]
0x18003287d  test    eax, eax
0x18003287f  mov     ebx, eax
0x180032881  cmovns  ebx, r12d
0x180032885  mov     rcx, [rbp+pSid]; Sid
0x180032889  test    rcx, rcx
0x18003288c  jz      short loc_18003289A
0x18003288e  call    cs:__imp_RtlFreeSid
0x180032895  nop     dword ptr [rax+rax+00h]
0x18003289a  mov     rcx, [rbp+var_18]; Sid
0x18003289e  test    rcx, rcx
0x1800328a1  jz      short loc_1800328AF
0x1800328a3  call    cs:__imp_RtlFreeSid
0x1800328aa  nop     dword ptr [rax+rax+00h]
0x1800328af  test    ebx, ebx
0x1800328b1  js      short loc_1800328B8
0x1800328b3  mov     rax, rdi
0x1800328b6  jmp     short loc_1800328DD
0x1800328b8  test    rdi, rdi
0x1800328bb  jz      short loc_1800328DB
0x1800328bd  mov     rcx, gs:60h
0x1800328c6  mov     r8, rdi; P
0x1800328c9  xor     edx, edx; Flags
0x1800328cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800328cf  call    cs:__imp_RtlFreeHeap
0x1800328d6  nop     dword ptr [rax+rax+00h]
0x1800328db  xor     eax, eax
0x1800328dd  mov     rcx, [rbp+var_8]
0x1800328e1  xor     rcx, rsp; StackCookie
0x1800328e4  call    __security_check_cookie
0x1800328e9  lea     r11, [rsp+80h+var_s0]
0x1800328f1  mov     rbx, [r11+38h]
0x1800328f5  mov     rsi, [r11+40h]
0x1800328f9  mov     rsp, r11
0x1800328fc  pop     r15
0x1800328fe  pop     r14
0x180032900  pop     r12
0x180032902  pop     rdi
0x180032903  pop     rbp
0x180032904  retn
```
