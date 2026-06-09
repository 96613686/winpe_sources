# LsapCreateDatabaseProtection(_SECURITY_DESCRIPTOR *)

- ea: `0x18010909c`
- end: `0x1801091e9`
- name: `?LsapCreateDatabaseProtection@@YAJPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180108fe8`

## callees

- `0x18010909c`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x1801090b8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801090b8`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801091d1`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801091d1`
- `ntdll!RtlGetAce` at `0x1801091a7`
- `ntdll!RtlGetAce` at `0x1801091a7`
- `ntdll!RtlAllocateHeap` at `0x18010910d`
- `ntdll!RtlAllocateHeap` at `0x18010910d`
- `ntdll!RtlAddAccessAllowedAce` at `0x18010915e`
- `ntdll!RtlAddAccessAllowedAce` at `0x180109186`
- `ntdll!RtlAddAccessAllowedAce` at `0x18010915e`
- `ntdll!RtlAddAccessAllowedAce` at `0x180109186`
- `ntdll!RtlCreateAcl` at `0x180109136`
- `ntdll!RtlCreateAcl` at `0x180109136`
- `ntdll!RtlLengthSid` at `0x1801090d9`
- `ntdll!RtlLengthSid` at `0x1801090ea`
- `ntdll!RtlLengthSid` at `0x1801090d9`
- `ntdll!RtlLengthSid` at `0x1801090ea`

## pseudocode

```c
__int64 __fastcall LsapCreateDatabaseProtection(PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  void *v2; // rdi
  ULONG v3; // ebx
  ULONG v4; // edi
  struct _ACL *Heap; // rax
  struct _ACL *v6; // rbx
  WORD i; // di
  PVOID Ace; // [rsp+58h] [rbp+10h] BYREF

  Ace = 0;
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v2 = (void *)*((_QWORD *)WellKnownSids + 96);
  v3 = RtlLengthSid(*((PSID *)WellKnownSids + 90));
  v4 = v3 + RtlLengthSid(v2) + 40;
  Heap = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  v6 = Heap;
  if ( !Heap )
    return 3221225495LL;
  RtlCreateAcl(Heap, v4, 2u);
  RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, *((PSID *)WellKnownSids + 90));
  RtlAddAccessAllowedAce(v6, 2u, 0x60000u, *((PSID *)WellKnownSids + 96));
  for ( i = 0; i < v6->AceCount; *((_BYTE *)Ace + 1) |= 2u )
    RtlGetAce(v6, i++, &Ace);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
  return 0;
}

```

## disassembly

```asm
0x18010909c  push    rbx
0x18010909e  push    rbp
0x18010909f  push    rsi
0x1801090a0  push    rdi
0x1801090a1  sub     rsp, 28h
0x1801090a5  mov     ebp, 1
0x1801090aa  mov     [rsp+48h+Ace], 0
0x1801090b3  mov     edx, ebp; Revision
0x1801090b5  mov     rsi, rcx
0x1801090b8  call    cs:__imp_RtlCreateSecurityDescriptor
0x1801090bf  nop     dword ptr [rax+rax+00h]
0x1801090c4  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1801090cb  mov     rdi, [rcx+300h]
0x1801090d2  mov     rcx, [rcx+2D0h]; Sid
0x1801090d9  call    cs:__imp_RtlLengthSid
0x1801090e0  nop     dword ptr [rax+rax+00h]
0x1801090e5  mov     rcx, rdi; Sid
0x1801090e8  mov     ebx, eax
0x1801090ea  call    cs:__imp_RtlLengthSid
0x1801090f1  nop     dword ptr [rax+rax+00h]
0x1801090f6  mov     rcx, gs:60h
0x1801090ff  xor     edx, edx; Flags
0x180109101  lea     edi, [rax+28h]
0x180109104  mov     rcx, [rcx+30h]; HeapHandle
0x180109108  add     edi, ebx
0x18010910a  mov     r8d, edi; Size
0x18010910d  call    cs:__imp_RtlAllocateHeap
0x180109114  nop     dword ptr [rax+rax+00h]
0x180109119  mov     rbx, rax
0x18010911c  test    rax, rax
0x18010911f  jnz     short loc_18010912B
0x180109121  mov     eax, 0C0000017h
0x180109126  jmp     loc_1801091DF
0x18010912b  mov     r8d, 2; AclRevision
0x180109131  mov     edx, edi; AclSize
0x180109133  mov     rcx, rbx; Acl
0x180109136  call    cs:__imp_RtlCreateAcl
0x18010913d  nop     dword ptr [rax+rax+00h]
0x180109142  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180109149  mov     edx, 2; Revision
0x18010914e  mov     r8d, 10000000h; AccessMask
0x180109154  mov     rcx, rbx; Acl
0x180109157  mov     r9, [r9+2D0h]; Sid
0x18010915e  call    cs:__imp_RtlAddAccessAllowedAce
0x180109165  nop     dword ptr [rax+rax+00h]
0x18010916a  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180109171  mov     edx, 2; Revision
0x180109176  mov     r8d, 60000h; AccessMask
0x18010917c  mov     rcx, rbx; Acl
0x18010917f  mov     r9, [r9+300h]; Sid
0x180109186  call    cs:__imp_RtlAddAccessAllowedAce
0x18010918d  nop     dword ptr [rax+rax+00h]
0x180109192  xor     eax, eax
0x180109194  xor     edi, edi
0x180109196  cmp     ax, [rbx+4]
0x18010919a  jnb     short loc_1801091C5
0x18010919c  movzx   edx, di; AceIndex
0x18010919f  lea     r8, [rsp+48h+Ace]; Ace
0x1801091a4  mov     rcx, rbx; Acl
0x1801091a7  call    cs:__imp_RtlGetAce
0x1801091ae  nop     dword ptr [rax+rax+00h]
0x1801091b3  mov     rax, [rsp+48h+Ace]
0x1801091b8  add     di, bp
0x1801091bb  or      byte ptr [rax+1], 2
0x1801091bf  cmp     di, [rbx+4]
0x1801091c3  jb      short loc_18010919C
0x1801091c5  xor     r9d, r9d; DaclDefaulted
0x1801091c8  mov     r8, rbx; Dacl
0x1801091cb  mov     dl, bpl; DaclPresent
0x1801091ce  mov     rcx, rsi; SecurityDescriptor
0x1801091d1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1801091d8  nop     dword ptr [rax+rax+00h]
0x1801091dd  xor     eax, eax
0x1801091df  add     rsp, 28h
0x1801091e3  pop     rdi
0x1801091e4  pop     rsi
0x1801091e5  pop     rbp
0x1801091e6  pop     rbx
0x1801091e7  retn
```
