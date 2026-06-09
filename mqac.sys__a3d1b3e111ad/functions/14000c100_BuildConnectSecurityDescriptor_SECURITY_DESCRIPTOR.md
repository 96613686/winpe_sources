# BuildConnectSecurityDescriptor(_SECURITY_DESCRIPTOR * *)

- ea: `0x14000c100`
- end: `0x14000c29f`
- name: `?BuildConnectSecurityDescriptor@@YAJPEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000c2a8`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x14000c100`
- `0x14000c388`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14000c135`
- `ntoskrnl!RtlMapGenericMask` at `0x14000c16c`
- `ntoskrnl!RtlMapGenericMask` at `0x14000c16c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c158`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14000c158`
- `ntoskrnl!RtlLengthSid` at `0x14000c187`
- `ntoskrnl!RtlLengthSid` at `0x14000c187`
- `ntoskrnl!RtlCreateAcl` at `0x14000c1dd`
- `ntoskrnl!RtlCreateAcl` at `0x14000c1dd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000c21a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14000c21a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000c244`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000c244`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000c261`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14000c261`

## pseudocode

```c
__int64 __fastcall BuildConnectSecurityDescriptor(struct _SECURITY_DESCRIPTOR **a1)
{
  int ConfiguredServiceIdentity; // eax
  void *v3; // rdi
  unsigned int v4; // ebx
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  unsigned int v6; // ebx
  ULONG v7; // esi
  struct _ACL *v8; // rax
  struct _SECURITY_DESCRIPTOR *v9; // rbx
  struct _ACL *v10; // r14
  NTSTATUS Acl; // esi
  struct _SECURITY_DESCRIPTOR *v12; // rcx
  unsigned int i; // esi
  NTSTATUS v14; // ebp
  PSID Sid[7]; // [rsp+20h] [rbp-38h]
  DWORD AccessMask; // [rsp+68h] [rbp+10h] BYREF
  void *v18; // [rsp+70h] [rbp+18h] BYREF

  v18 = 0;
  ConfiguredServiceIdentity = GetConfiguredServiceIdentity(&v18);
  v3 = v18;
  v4 = ConfiguredServiceIdentity;
  if ( ConfiguredServiceIdentity >= 0 )
  {
    Sid[1] = v18;
    Sid[0] = SeExports->SeAliasAdminsSid;
    AccessMask = 0x10000000;
    FileObjectGenericMapping = IoGetFileObjectGenericMapping();
    RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
    v6 = 0;
    v7 = 40;
    do
      v7 += RtlLengthSid(Sid[v6++]);
    while ( v6 < 2 );
    v8 = (struct _ACL *)operator new(v7 + 40LL, 0x100u, 0x5141514Du, LowPoolPriority);
    v9 = (struct _SECURITY_DESCRIPTOR *)v8;
    if ( !v8 )
    {
      operator delete(0);
      v4 = -1073741670;
      goto LABEL_17;
    }
    v10 = v8 + 5;
    Acl = RtlCreateAcl(v8 + 5, v7, 2u);
    if ( Acl >= 0 )
    {
      for ( i = 0; i < 2; ++i )
      {
        v14 = RtlAddAccessAllowedAce(v10, 2u, AccessMask, Sid[i]);
        if ( v14 < 0 )
        {
          operator delete(v9);
          v4 = v14;
          goto LABEL_17;
        }
      }
      Acl = RtlCreateSecurityDescriptor(v9, 1u);
      v12 = v9;
      if ( Acl < 0 )
        goto LABEL_8;
      Acl = RtlSetDaclSecurityDescriptor(v9, 1u, v10, 0);
      if ( Acl >= 0 )
      {
        *a1 = v9;
        operator delete(0);
        v4 = 0;
        goto LABEL_17;
      }
    }
    v12 = v9;
LABEL_8:
    operator delete(v12);
    v4 = Acl;
  }
LABEL_17:
  operator delete(v3);
  return v4;
}

```

## disassembly

```asm
0x14000c100  mov     [rsp+arg_0], rbx
0x14000c105  push    rbp
0x14000c106  push    rsi
0x14000c107  push    rdi
0x14000c108  push    r14
0x14000c10a  push    r15
0x14000c10c  sub     rsp, 30h
0x14000c110  mov     r15, rcx
0x14000c113  mov     [rsp+58h+arg_10], 0
0x14000c11c  lea     rcx, [rsp+58h+arg_10]; void **
0x14000c121  call    ?GetConfiguredServiceIdentity@@YAJPEAPEAX@Z; GetConfiguredServiceIdentity(void * *)
0x14000c126  mov     rdi, [rsp+58h+arg_10]
0x14000c12b  mov     ebx, eax
0x14000c12d  test    eax, eax
0x14000c12f  js      loc_14000C283
0x14000c135  mov     rax, cs:__imp_SeExports
0x14000c13c  mov     [rsp+58h+var_30], rdi
0x14000c141  mov     rcx, [rax]
0x14000c144  mov     rax, [rcx+110h]
0x14000c14b  mov     [rsp+58h+Sid], rax
0x14000c150  mov     [rsp+58h+AccessMask], 10000000h
0x14000c158  call    cs:__imp_IoGetFileObjectGenericMapping
0x14000c15f  nop     dword ptr [rax+rax+00h]
0x14000c164  mov     rdx, rax; GenericMapping
0x14000c167  lea     rcx, [rsp+58h+AccessMask]; AccessMask
0x14000c16c  call    cs:__imp_RtlMapGenericMask
0x14000c173  nop     dword ptr [rax+rax+00h]
0x14000c178  xor     ebx, ebx
0x14000c17a  mov     esi, 28h ; '('
0x14000c17f  movsxd  rcx, ebx
0x14000c182  mov     rcx, [rsp+rcx*8+58h+Sid]; Sid
0x14000c187  call    cs:__imp_RtlLengthSid
0x14000c18e  nop     dword ptr [rax+rax+00h]
0x14000c193  add     esi, eax
0x14000c195  inc     ebx
0x14000c197  cmp     ebx, 2
0x14000c19a  jb      short loc_14000C17F
0x14000c19c  mov     ecx, esi
0x14000c19e  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000c1a1  add     rcx, 28h ; '('; unsigned __int64
0x14000c1a5  mov     edx, 100h; unsigned __int64
0x14000c1aa  mov     r8d, 5141514Dh; unsigned int
0x14000c1b0  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000c1b5  mov     rbx, rax
0x14000c1b8  test    rax, rax
0x14000c1bb  jnz     short loc_14000C1CE
0x14000c1bd  xor     ecx, ecx; void *
0x14000c1bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c1c4  mov     ebx, 0C000009Ah
0x14000c1c9  jmp     loc_14000C283
0x14000c1ce  lea     r14, [rax+28h]
0x14000c1d2  mov     r8d, 2; AclRevision
0x14000c1d8  mov     rcx, r14; Acl
0x14000c1db  mov     edx, esi; AclLength
0x14000c1dd  call    cs:__imp_RtlCreateAcl
0x14000c1e4  nop     dword ptr [rax+rax+00h]
0x14000c1e9  mov     esi, eax
0x14000c1eb  test    eax, eax
0x14000c1ed  jns     short loc_14000C1FE
0x14000c1ef  mov     rcx, rbx; void *
0x14000c1f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c1f7  mov     ebx, esi
0x14000c1f9  jmp     loc_14000C283
0x14000c1fe  xor     esi, esi
0x14000c200  cmp     esi, 2
0x14000c203  jnb     short loc_14000C23C
0x14000c205  mov     r8d, [rsp+58h+AccessMask]; AccessMask
0x14000c20a  mov     edx, 2; AceRevision
0x14000c20f  movsxd  r9, esi
0x14000c212  mov     rcx, r14; Acl
0x14000c215  mov     r9, [rsp+r9*8+58h+Sid]; Sid
0x14000c21a  call    cs:__imp_RtlAddAccessAllowedAce
0x14000c221  nop     dword ptr [rax+rax+00h]
0x14000c226  mov     ebp, eax
0x14000c228  test    eax, eax
0x14000c22a  js      short loc_14000C230
0x14000c22c  inc     esi
0x14000c22e  jmp     short loc_14000C200
0x14000c230  mov     rcx, rbx; void *
0x14000c233  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c238  mov     ebx, ebp
0x14000c23a  jmp     short loc_14000C283
0x14000c23c  mov     edx, 1; Revision
0x14000c241  mov     rcx, rbx; SecurityDescriptor
0x14000c244  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000c24b  nop     dword ptr [rax+rax+00h]
0x14000c250  mov     esi, eax
0x14000c252  mov     rcx, rbx; SecurityDescriptor
0x14000c255  test    eax, eax
0x14000c257  js      short loc_14000C1F2
0x14000c259  xor     r9d, r9d; DaclDefaulted
0x14000c25c  mov     r8, r14; Dacl
0x14000c25f  mov     dl, 1; DaclPresent
0x14000c261  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14000c268  nop     dword ptr [rax+rax+00h]
0x14000c26d  mov     esi, eax
0x14000c26f  test    eax, eax
0x14000c271  js      loc_14000C1EF
0x14000c277  xor     ecx, ecx; void *
0x14000c279  mov     [r15], rbx
0x14000c27c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c281  xor     ebx, ebx
0x14000c283  mov     rcx, rdi; void *
0x14000c286  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000c28b  mov     eax, ebx
0x14000c28d  mov     rbx, [rsp+58h+arg_0]
0x14000c292  add     rsp, 30h
0x14000c296  pop     r15
0x14000c298  pop     r14
0x14000c29a  pop     rdi
0x14000c29b  pop     rsi
0x14000c29c  pop     rbp
0x14000c29d  retn
```
