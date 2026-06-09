# UlAccessCheck

- ea: `0x1c00a5768`
- end: `0x1c00a594d`
- name: `UlAccessCheck`
- size: `485`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, PACCESS_STATE AccessState, ACCESS_MASK DesiredAccess, KPROCESSOR_MODE AccessMode, __int64, char)`
- caller_count: `7`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c00021bc`
- `0x1c0048438`
- `0x1c00a4f2c`
- `0x1c00a5240`
- `0x1c010308c`
- `0x1c012d8e8`
- `0x1c0153bdc`

## callees

- `0x1c00022d0`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c00a5768`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c00a57c3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c00a57c3`
- `ntoskrnl!SeLockSubjectContext` at `0x1c00a57b7`
- `ntoskrnl!SeLockSubjectContext` at `0x1c00a57b7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c00a5916`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1c00a5916`
- `ntoskrnl!SeAccessCheck` at `0x1c00a5804`
- `ntoskrnl!SeAccessCheck` at `0x1c00a5804`
- `ntoskrnl!SeAppendPrivileges` at `0x1c00a581f`
- `ntoskrnl!SeAppendPrivileges` at `0x1c00a581f`
- `ntoskrnl!SeFreePrivileges` at `0x1c00a582f`
- `ntoskrnl!SeFreePrivileges` at `0x1c00a582f`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1c00a5907`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x1c00a5907`

## pseudocode

```c
__int64 __fastcall UlAccessCheck(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PACCESS_STATE AccessState,
        ACCESS_MASK DesiredAccess,
        KPROCESSOR_MODE AccessMode,
        __int64 a5,
        char a6)
{
  SECURITY_SUBJECT_CONTEXT *p_SubjectSecurityContext; // r15
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v12; // si
  DWORD v13; // ebx
  __int64 result; // rax
  int AccessStatus; // [rsp+50h] [rbp-30h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING AbsoluteObjectName; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+70h] [rbp-10h] BYREF
  DWORD GrantedAccess; // [rsp+B8h] [rbp+38h] BYREF

  p_SubjectSecurityContext = &AccessState->SubjectSecurityContext;
  AccessStatus = 0;
  Privileges = 0;
  GrantedAccess = 0;
  AbsoluteObjectName = 0;
  ObjectTypeName = 0;
  SeLockSubjectContext(&AccessState->SubjectSecurityContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v12 = SeAccessCheck(
          SecurityDescriptor,
          p_SubjectSecurityContext,
          1u,
          DesiredAccess,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          &AccessStatus);
  if ( Privileges )
  {
    SeAppendPrivileges(AccessState, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( !a6 )
  {
LABEL_12:
    if ( v12 )
      goto LABEL_13;
    goto LABEL_15;
  }
  if ( v12 )
  {
LABEL_13:
    v13 = GrantedAccess;
LABEL_14:
    AccessState->PreviouslyGrantedAccess |= v13;
    AccessState->RemainingDesiredAccess &= ~(v13 | 0x2000000);
    goto LABEL_15;
  }
  if ( (AccessState->Flags & 0x106) == 0x106 )
  {
    v13 = 917504;
    if ( DesiredAccess == 917504 )
    {
      if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
        WPP_SF_(10, WPP_a4225cd4341630c95ff0a5fde8e1f8f3_Traceguids);
      GrantedAccess = 917504;
      v12 = 1;
      goto LABEL_14;
    }
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
  {
    WPP_SF_D(11, WPP_a4225cd4341630c95ff0a5fde8e1f8f3_Traceguids);
    goto LABEL_12;
  }
LABEL_15:
  if ( (int)UlInitUnicodeStringEx(&ObjectTypeName, L"Ul") >= 0
    && (int)UlInitUnicodeStringEx(&AbsoluteObjectName, a5) >= 0 )
  {
    SeOpenObjectAuditAlarm(
      &ObjectTypeName,
      0,
      &AbsoluteObjectName,
      SecurityDescriptor,
      AccessState,
      0,
      v12,
      AccessMode,
      &AccessState->GenerateOnClose);
  }
  SeUnlockSubjectContext(p_SubjectSecurityContext);
  result = (unsigned int)AccessStatus;
  if ( v12 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1c00a5768  mov     [rsp-28h+arg_0], rbx
0x1c00a576d  mov     [rsp-28h+arg_10], rsi
0x1c00a5772  mov     [rsp-28h+arg_18], rdi
0x1c00a5777  push    rbp
0x1c00a5778  push    r12
0x1c00a577a  push    r13
0x1c00a577c  push    r14
0x1c00a577e  push    r15
0x1c00a5780  mov     rbp, rsp
0x1c00a5783  sub     rsp, 80h
0x1c00a578a  xor     ebx, ebx
0x1c00a578c  lea     r15, [rdx+20h]
0x1c00a5790  mov     r13, rcx
0x1c00a5793  mov     [rbp+var_30], ebx
0x1c00a5796  xorps   xmm0, xmm0
0x1c00a5799  mov     [rbp+var_28], rbx
0x1c00a579d  xorps   xmm1, xmm1
0x1c00a57a0  mov     [rbp+arg_8], ebx
0x1c00a57a3  mov     rcx, r15; SubjectContext
0x1c00a57a6  mov     r12b, r9b
0x1c00a57a9  mov     r14d, r8d
0x1c00a57ac  mov     rdi, rdx
0x1c00a57af  movups  xmmword ptr [rbp+AbsoluteObjectName.Length], xmm0
0x1c00a57b3  movups  xmmword ptr [rbp+ObjectTypeName.Length], xmm1
0x1c00a57b7  call    cs:__imp_SeLockSubjectContext
0x1c00a57be  nop     dword ptr [rax+rax+00h]
0x1c00a57c3  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c00a57ca  nop     dword ptr [rax+rax+00h]
0x1c00a57cf  lea     rcx, [rbp+var_30]
0x1c00a57d3  mov     r9d, r14d; DesiredAccess
0x1c00a57d6  mov     [rsp+80h+AccessStatus], rcx; AccessStatus
0x1c00a57db  mov     r8b, 1; SubjectContextLocked
0x1c00a57de  lea     rcx, [rbp+arg_8]
0x1c00a57e2  mov     rdx, r15; SubjectSecurityContext
0x1c00a57e5  mov     [rsp+80h+GrantedAccess], rcx; GrantedAccess
0x1c00a57ea  mov     rcx, r13; SecurityDescriptor
0x1c00a57ed  mov     [rsp+80h+AccessMode], r12b; AccessMode
0x1c00a57f2  mov     [rsp+80h+GenericMapping], rax; GenericMapping
0x1c00a57f7  lea     rax, [rbp+var_28]
0x1c00a57fb  mov     [rsp+80h+Privileges], rax; Privileges
0x1c00a5800  mov     [rsp+80h+PreviouslyGrantedAccess], ebx; PreviouslyGrantedAccess
0x1c00a5804  call    cs:__imp_SeAccessCheck
0x1c00a580b  nop     dword ptr [rax+rax+00h]
0x1c00a5810  mov     rdx, [rbp+var_28]; Privileges
0x1c00a5814  mov     sil, al
0x1c00a5817  test    rdx, rdx
0x1c00a581a  jz      short loc_1C00A583B
0x1c00a581c  mov     rcx, rdi; AccessState
0x1c00a581f  call    cs:__imp_SeAppendPrivileges
0x1c00a5826  nop     dword ptr [rax+rax+00h]
0x1c00a582b  mov     rcx, [rbp+var_28]; Privileges
0x1c00a582f  call    cs:__imp_SeFreePrivileges
0x1c00a5836  nop     dword ptr [rax+rax+00h]
0x1c00a583b  cmp     [rbp+arg_28], bl
0x1c00a583e  jz      short loc_1C00A58A3
0x1c00a5840  test    sil, sil
0x1c00a5843  jnz     short loc_1C00A58A8
0x1c00a5845  mov     r8d, [rdi+0Ch]
0x1c00a5849  mov     ecx, 106h
0x1c00a584e  mov     eax, r8d
0x1c00a5851  and     eax, ecx
0x1c00a5853  cmp     eax, ecx
0x1c00a5855  jnz     short loc_1C00A5886
0x1c00a5857  mov     ebx, 0E0000h
0x1c00a585c  cmp     r14d, ebx
0x1c00a585f  jnz     short loc_1C00A5886
0x1c00a5861  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00a586b  jz      short loc_1C00A587E
0x1c00a586d  mov     ecx, 0Ah
0x1c00a5872  lea     rdx, WPP_a4225cd4341630c95ff0a5fde8e1f8f3_Traceguids
0x1c00a5879  call    WPP_SF_
0x1c00a587e  mov     [rbp+arg_8], ebx
0x1c00a5881  mov     sil, 1
0x1c00a5884  jmp     short loc_1C00A58AB
0x1c00a5886  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c00a5890  jz      short loc_1C00A58B7
0x1c00a5892  mov     ecx, 0Bh
0x1c00a5897  lea     rdx, WPP_a4225cd4341630c95ff0a5fde8e1f8f3_Traceguids
0x1c00a589e  call    WPP_SF_D
0x1c00a58a3  test    sil, sil
0x1c00a58a6  jz      short loc_1C00A58B7
0x1c00a58a8  mov     ebx, [rbp+arg_8]
0x1c00a58ab  or      [rdi+14h], ebx
0x1c00a58ae  bts     ebx, 19h
0x1c00a58b2  not     ebx
0x1c00a58b4  and     [rdi+10h], ebx
0x1c00a58b7  lea     rdx, aUl; "Ul"
0x1c00a58be  lea     rcx, [rbp+ObjectTypeName]
0x1c00a58c2  call    UlInitUnicodeStringEx
0x1c00a58c7  xor     ebx, ebx
0x1c00a58c9  test    eax, eax
0x1c00a58cb  js      short loc_1C00A5913
0x1c00a58cd  mov     rdx, [rbp+arg_20]
0x1c00a58d1  lea     rcx, [rbp+AbsoluteObjectName]
0x1c00a58d5  call    UlInitUnicodeStringEx
0x1c00a58da  test    eax, eax
0x1c00a58dc  js      short loc_1C00A5913
0x1c00a58de  lea     rax, [rdi+0Ah]
0x1c00a58e2  mov     r9, r13; SecurityDescriptor
0x1c00a58e5  mov     [rsp+80h+GrantedAccess], rax; GenerateOnClose
0x1c00a58ea  lea     r8, [rbp+AbsoluteObjectName]; AbsoluteObjectName
0x1c00a58ee  mov     [rsp+80h+AccessMode], r12b; AccessMode
0x1c00a58f3  lea     rcx, [rbp+ObjectTypeName]; ObjectTypeName
0x1c00a58f7  mov     byte ptr [rsp+80h+GenericMapping], sil; AccessGranted
0x1c00a58fc  xor     edx, edx; Object
0x1c00a58fe  mov     byte ptr [rsp+80h+Privileges], bl; ObjectCreated
0x1c00a5902  mov     qword ptr [rsp+80h+PreviouslyGrantedAccess], rdi; AccessState
0x1c00a5907  call    cs:__imp_SeOpenObjectAuditAlarm
0x1c00a590e  nop     dword ptr [rax+rax+00h]
0x1c00a5913  mov     rcx, r15; SubjectContext
0x1c00a5916  call    cs:__imp_SeUnlockSubjectContext
0x1c00a591d  nop     dword ptr [rax+rax+00h]
0x1c00a5922  mov     eax, [rbp+var_30]
0x1c00a5925  lea     r11, [rsp+80h+var_s0]
0x1c00a592d  mov     rdi, [r11+48h]
0x1c00a5931  test    sil, sil
0x1c00a5934  mov     rsi, [r11+40h]
0x1c00a5938  cmovnz  eax, ebx
0x1c00a593b  mov     rbx, [r11+30h]
0x1c00a593f  mov     rsp, r11
0x1c00a5942  pop     r15
0x1c00a5944  pop     r14
0x1c00a5946  pop     r13
0x1c00a5948  pop     r12
0x1c00a594a  pop     rbp
0x1c00a594b  retn
```
