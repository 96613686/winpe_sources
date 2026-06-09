# _RegRtlUnlockKey

- ea: `0x18007c9c0`
- end: `0x18007ccdb`
- name: `_RegRtlUnlockKey`
- size: `795`
- prototype: `__int64 __fastcall(HANDLE Handle, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003f50`

## callees

- `0x18003bc80`
- `0x18007c8c8`
- `0x18007c9c0`

## import_xrefs

- `ntdll!RtlAddAce` at `0x18007cbda`
- `ntdll!RtlAddAce` at `0x18007cbda`
- `ntdll!RtlCopySid` at `0x18007cb6a`
- `ntdll!RtlCopySid` at `0x18007cb6a`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18007caa3`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18007caa3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18007cc0c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18007cc0c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18007cbf2`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18007cbf2`
- `ntdll!RtlLengthSid` at `0x18007cb09`
- `ntdll!RtlLengthSid` at `0x18007cb5a`
- `ntdll!RtlLengthSid` at `0x18007cb09`
- `ntdll!RtlLengthSid` at `0x18007cb5a`
- `ntdll!RtlSubAuthoritySid` at `0x18007cae4`
- `ntdll!RtlSubAuthoritySid` at `0x18007caf9`
- `ntdll!RtlSubAuthoritySid` at `0x18007cae4`
- `ntdll!RtlSubAuthoritySid` at `0x18007caf9`
- `ntdll!RtlCreateAcl` at `0x18007cbb5`
- `ntdll!RtlCreateAcl` at `0x18007cbb5`
- `ntdll!RtlInitializeSid` at `0x18007cace`
- `ntdll!RtlInitializeSid` at `0x18007cace`
- `ntdll!RtlFreeHeap` at `0x18007ca5b`
- `ntdll!RtlFreeHeap` at `0x18007cc69`
- `ntdll!RtlFreeHeap` at `0x18007cc88`
- `ntdll!RtlFreeHeap` at `0x18007ccac`
- `ntdll!RtlFreeHeap` at `0x18007ca5b`
- `ntdll!RtlFreeHeap` at `0x18007cc69`
- `ntdll!RtlFreeHeap` at `0x18007cc88`
- `ntdll!RtlFreeHeap` at `0x18007ccac`
- `ntdll!RtlAllocateHeap` at `0x18007ca74`
- `ntdll!RtlAllocateHeap` at `0x18007cb2e`
- `ntdll!RtlAllocateHeap` at `0x18007cb92`
- `ntdll!RtlAllocateHeap` at `0x18007ca74`
- `ntdll!RtlAllocateHeap` at `0x18007cb2e`
- `ntdll!RtlAllocateHeap` at `0x18007cb92`
- `ntdll!NtSetSecurityObject` at `0x18007cc41`
- `ntdll!NtSetSecurityObject` at `0x18007cc41`

## pseudocode

```c
__int64 __fastcall RegRtlUnlockKey(HANDLE Handle, _QWORD *a2)
{
  _WORD *Heap; // rdi
  int KeySecurity; // eax
  NTSTATUS DaclSecurityDescriptor; // ebx
  ULONG v7; // eax
  unsigned int v8; // r14d
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  ULONG v11; // eax
  ULONG v12; // ebx
  struct _ACL *v13; // rax
  struct _ACL *v14; // r14
  __int16 v15; // r15
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 DaclDefaulted[3]; // [rsp+31h] [rbp-38h] BYREF
  _DWORD Size[3]; // [rsp+34h] [rbp-35h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-1h] BYREF
  _BYTE Sid[16]; // [rsp+70h] [rbp+7h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  DaclPresent = 0;
  DaclDefaulted[0] = 0;
  *(_QWORD *)&Size[1] = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v21 = 0;
  SecurityDescriptor[0] = 0;
  *a2 = 0;
  Heap = 0;
  SecurityDescriptor[1] = 0;
  Size[0] = 0;
  while ( 1 )
  {
    KeySecurity = RegRtlGetKeySecurity(Handle, 4, Heap, Size);
    DaclSecurityDescriptor = KeySecurity;
    if ( KeySecurity != -1073741789 )
      break;
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size[0]);
    if ( !Heap )
      return (unsigned int)-1073741801;
  }
  if ( KeySecurity >= 0 )
  {
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(Heap, &DaclPresent, (PACL *)&Size[1], DaclDefaulted);
    if ( DaclSecurityDescriptor >= 0 )
    {
      if ( DaclPresent )
      {
        DaclSecurityDescriptor = RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
        if ( DaclSecurityDescriptor >= 0 )
        {
          *RtlSubAuthoritySid(Sid, 0) = 32;
          *RtlSubAuthoritySid(Sid, 1u) = 544;
          v7 = RtlLengthSid(Sid);
          v8 = v7 + 8;
          if ( v7 + 8 < v7 )
          {
            DaclSecurityDescriptor = -1073741675;
          }
          else
          {
            v9 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v8);
            v10 = v9;
            if ( v9 )
            {
              *v9 = 0;
              v9[1] = v8;
              *((_DWORD *)v9 + 1) = 983103;
              v11 = RtlLengthSid(Sid);
              RtlCopySid(v11, v10 + 4, Sid);
              v12 = v8 + 8;
              if ( v8 + 8 < v8 )
              {
                DaclSecurityDescriptor = -1073741675;
              }
              else
              {
                v13 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
                v14 = v13;
                if ( v13 )
                {
                  DaclSecurityDescriptor = RtlCreateAcl(v13, v12, 2u);
                  if ( DaclSecurityDescriptor >= 0 )
                  {
                    DaclSecurityDescriptor = RtlAddAce(v14, 2u, 0, v10, v10[1]);
                    if ( DaclSecurityDescriptor >= 0 )
                    {
                      v15 = Heap[1];
                      DaclSecurityDescriptor = RtlCreateSecurityDescriptor(SecurityDescriptor, *(unsigned __int8 *)Heap);
                      if ( DaclSecurityDescriptor >= 0 )
                      {
                        DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(
                                                   SecurityDescriptor,
                                                   DaclPresent,
                                                   v14,
                                                   DaclDefaulted[0]);
                        if ( DaclSecurityDescriptor >= 0 )
                        {
                          WORD1(SecurityDescriptor[0]) = v15 & 0x1000 | WORD1(SecurityDescriptor[0]) & 0xEFFF;
                          DaclSecurityDescriptor = NtSetSecurityObject(Handle, 4u, SecurityDescriptor);
                          if ( DaclSecurityDescriptor >= 0 )
                          {
                            *a2 = Heap;
                            Heap = 0;
                          }
                        }
                      }
                    }
                  }
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
                }
                else
                {
                  DaclSecurityDescriptor = -1073741801;
                }
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
            }
            else
            {
              DaclSecurityDescriptor = -1073741801;
            }
          }
        }
      }
      else
      {
        DaclSecurityDescriptor = -1073741811;
      }
    }
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x18007c9c0  mov     [rsp-8+arg_10], rbx
0x18007c9c5  push    rbp
0x18007c9c6  push    rsi
0x18007c9c7  push    rdi
0x18007c9c8  push    r12
0x18007c9ca  push    r13
0x18007c9cc  push    r14
0x18007c9ce  push    r15
0x18007c9d0  lea     rbp, [rsp-27h]
0x18007c9d5  sub     rsp, 90h
0x18007c9dc  mov     rax, cs:__security_cookie
0x18007c9e3  xor     rax, rsp
0x18007c9e6  mov     [rbp+57h+var_40], rax
0x18007c9ea  xor     r15d, r15d
0x18007c9ed  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 500h
0x18007c9f3  xor     eax, eax
0x18007c9f5  mov     [rbp+57h+DaclPresent], r15b
0x18007c9f9  xorps   xmm0, xmm0
0x18007c9fc  mov     [rbp+57h+DaclDefaulted], r15b
0x18007ca00  mov     r12, rdx
0x18007ca03  mov     qword ptr [rbp+57h+Size+4], r15
0x18007ca07  mov     r13, rcx
0x18007ca0a  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], r15d
0x18007ca0e  lea     esi, [rax+8]
0x18007ca11  mov     [rbp+57h+var_60], rax
0x18007ca15  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18007ca19  mov     [rdx], r15
0x18007ca1c  mov     edi, r15d
0x18007ca1f  movups  [rbp+57h+var_70], xmm0
0x18007ca23  mov     dword ptr [rbp+57h+Size], r15d
0x18007ca27  lea     r9, [rbp+57h+Size]
0x18007ca2b  mov     r8, rdi
0x18007ca2e  mov     edx, 4
0x18007ca33  mov     rcx, r13
0x18007ca36  call    _RegRtlGetKeySecurity
0x18007ca3b  mov     ebx, eax
0x18007ca3d  cmp     eax, 0C0000023h
0x18007ca42  jnz     short loc_18007CA8C
0x18007ca44  test    rdi, rdi
0x18007ca47  jz      short loc_18007CA61
0x18007ca49  mov     rcx, gs:60h
0x18007ca52  mov     r8, rdi; P
0x18007ca55  xor     edx, edx; Flags
0x18007ca57  mov     rcx, [rcx+30h]; HeapHandle
0x18007ca5b  call    cs:__imp_RtlFreeHeap
0x18007ca61  mov     rcx, gs:60h
0x18007ca6a  mov     edx, esi; Flags
0x18007ca6c  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x18007ca70  mov     rcx, [rcx+30h]; HeapHandle
0x18007ca74  call    cs:__imp_RtlAllocateHeap
0x18007ca7a  mov     rdi, rax
0x18007ca7d  test    rax, rax
0x18007ca80  jnz     short loc_18007CA27
0x18007ca82  mov     ebx, 0C0000017h
0x18007ca87  jmp     loc_18007CCB2
0x18007ca8c  test    eax, eax
0x18007ca8e  js      loc_18007CC95
0x18007ca94  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18007ca98  mov     rcx, rdi; SecurityDescriptor
0x18007ca9b  lea     r8, [rbp+57h+Size+4]; Dacl
0x18007ca9f  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x18007caa3  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18007caa9  mov     ebx, eax
0x18007caab  test    eax, eax
0x18007caad  js      loc_18007CC95
0x18007cab3  cmp     [rbp+57h+DaclPresent], r15b
0x18007cab7  jnz     short loc_18007CAC3
0x18007cab9  mov     ebx, 0C000000Dh
0x18007cabe  jmp     loc_18007CC95
0x18007cac3  mov     r8b, 2; SubAuthorityCount
0x18007cac6  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18007caca  lea     rcx, [rbp+57h+Sid]; Sid
0x18007cace  call    cs:__imp_RtlInitializeSid
0x18007cad4  mov     ebx, eax
0x18007cad6  test    eax, eax
0x18007cad8  js      loc_18007CC95
0x18007cade  xor     edx, edx; SubAuthority
0x18007cae0  lea     rcx, [rbp+57h+Sid]; Sid
0x18007cae4  call    cs:__imp_RtlSubAuthoritySid
0x18007caea  mov     edx, 1; SubAuthority
0x18007caef  lea     rcx, [rbp+57h+Sid]; Sid
0x18007caf3  mov     dword ptr [rax], 20h ; ' '
0x18007caf9  call    cs:__imp_RtlSubAuthoritySid
0x18007caff  lea     rcx, [rbp+57h+Sid]; Sid
0x18007cb03  mov     dword ptr [rax], 220h
0x18007cb09  call    cs:__imp_RtlLengthSid
0x18007cb0f  lea     r14d, [rax+8]
0x18007cb13  cmp     r14d, eax
0x18007cb16  jb      loc_18007CC90
0x18007cb1c  mov     rcx, gs:60h
0x18007cb25  mov     edx, esi; Flags
0x18007cb27  mov     r8d, r14d; Size
0x18007cb2a  mov     rcx, [rcx+30h]; HeapHandle
0x18007cb2e  call    cs:__imp_RtlAllocateHeap
0x18007cb34  mov     rsi, rax
0x18007cb37  test    rax, rax
0x18007cb3a  jnz     short loc_18007CB46
0x18007cb3c  mov     ebx, 0C0000017h
0x18007cb41  jmp     loc_18007CC95
0x18007cb46  lea     rcx, [rbp+57h+Sid]; Sid
0x18007cb4a  mov     [rax], r15w
0x18007cb4e  mov     [rax+2], r14w
0x18007cb53  mov     dword ptr [rax+4], 0F003Fh
0x18007cb5a  call    cs:__imp_RtlLengthSid
0x18007cb60  mov     ecx, eax; DestinationSidLength
0x18007cb62  lea     r8, [rbp+57h+Sid]; SourceSid
0x18007cb66  lea     rdx, [rsi+8]; DestinationSid
0x18007cb6a  call    cs:__imp_RtlCopySid
0x18007cb70  lea     ebx, [r14+8]
0x18007cb74  cmp     ebx, r14d
0x18007cb77  jb      loc_18007CC71
0x18007cb7d  mov     rcx, gs:60h
0x18007cb86  mov     edx, 8; Flags
0x18007cb8b  mov     r8d, ebx; Size
0x18007cb8e  mov     rcx, [rcx+30h]; HeapHandle
0x18007cb92  call    cs:__imp_RtlAllocateHeap
0x18007cb98  mov     r14, rax
0x18007cb9b  test    rax, rax
0x18007cb9e  jnz     short loc_18007CBAA
0x18007cba0  mov     ebx, 0C0000017h
0x18007cba5  jmp     loc_18007CC76
0x18007cbaa  mov     r8d, 2; AclRevision
0x18007cbb0  mov     edx, ebx; AclSize
0x18007cbb2  mov     rcx, r14; Acl
0x18007cbb5  call    cs:__imp_RtlCreateAcl
0x18007cbbb  mov     ebx, eax
0x18007cbbd  test    eax, eax
0x18007cbbf  js      loc_18007CC57
0x18007cbc5  movzx   eax, word ptr [rsi+2]
0x18007cbc9  xor     r8d, r8d; StartingAceIndex
0x18007cbcc  mov     r9, rsi; AceList
0x18007cbcf  mov     [rsp+0C0h+AceListLength], eax; AceListLength
0x18007cbd3  mov     rcx, r14; Acl
0x18007cbd6  lea     edx, [r8+2]; AceRevision
0x18007cbda  call    cs:__imp_RtlAddAce
0x18007cbe0  mov     ebx, eax
0x18007cbe2  test    eax, eax
0x18007cbe4  js      short loc_18007CC57
0x18007cbe6  movzx   edx, byte ptr [rdi]; Revision
0x18007cbe9  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18007cbed  movzx   r15d, word ptr [rdi+2]
0x18007cbf2  call    cs:__imp_RtlCreateSecurityDescriptor
0x18007cbf8  mov     ebx, eax
0x18007cbfa  test    eax, eax
0x18007cbfc  js      short loc_18007CC57
0x18007cbfe  mov     r9b, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18007cc02  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18007cc06  mov     dl, [rbp+57h+DaclPresent]; DaclPresent
0x18007cc09  mov     r8, r14; Dacl
0x18007cc0c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18007cc12  mov     ebx, eax
0x18007cc14  test    eax, eax
0x18007cc16  js      short loc_18007CC57
0x18007cc18  movzx   eax, word ptr [rbp+57h+SecurityDescriptor+2]
0x18007cc1c  mov     ecx, 0EFFFh
0x18007cc21  and     ax, cx
0x18007cc24  mov     ecx, 1000h
0x18007cc29  and     r15w, cx
0x18007cc2d  or      ax, r15w
0x18007cc31  mov     word ptr [rbp+57h+SecurityDescriptor+2], ax
0x18007cc35  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18007cc39  mov     edx, 4; SecurityInformation
0x18007cc3e  mov     rcx, r13; Handle
0x18007cc41  call    cs:__imp_NtSetSecurityObject
0x18007cc47  xor     r15d, r15d
0x18007cc4a  mov     ebx, eax
0x18007cc4c  test    eax, eax
0x18007cc4e  js      short loc_18007CC57
0x18007cc50  mov     [r12], rdi
0x18007cc54  mov     edi, r15d
0x18007cc57  mov     rcx, gs:60h
0x18007cc60  mov     r8, r14; P
0x18007cc63  xor     edx, edx; Flags
0x18007cc65  mov     rcx, [rcx+30h]; HeapHandle
0x18007cc69  call    cs:__imp_RtlFreeHeap
0x18007cc6f  jmp     short loc_18007CC76
0x18007cc71  mov     ebx, 0C0000095h
0x18007cc76  mov     rcx, gs:60h
0x18007cc7f  mov     r8, rsi; P
0x18007cc82  xor     edx, edx; Flags
0x18007cc84  mov     rcx, [rcx+30h]; HeapHandle
0x18007cc88  call    cs:__imp_RtlFreeHeap
0x18007cc8e  jmp     short loc_18007CC95
0x18007cc90  mov     ebx, 0C0000095h
0x18007cc95  test    rdi, rdi
0x18007cc98  jz      short loc_18007CCB2
0x18007cc9a  mov     rcx, gs:60h
0x18007cca3  mov     r8, rdi; P
0x18007cca6  xor     edx, edx; Flags
0x18007cca8  mov     rcx, [rcx+30h]; HeapHandle
0x18007ccac  call    cs:__imp_RtlFreeHeap
0x18007ccb2  mov     eax, ebx
0x18007ccb4  mov     rcx, [rbp+57h+var_40]
0x18007ccb8  xor     rcx, rsp; StackCookie
0x18007ccbb  call    __security_check_cookie
0x18007ccc0  mov     rbx, [rsp+0C0h+arg_10]
0x18007ccc8  add     rsp, 90h
0x18007cccf  pop     r15
0x18007ccd1  pop     r14
0x18007ccd3  pop     r13
0x18007ccd5  pop     r12
0x18007ccd7  pop     rdi
0x18007ccd8  pop     rsi
0x18007ccd9  pop     rbp
0x18007ccda  retn
```
