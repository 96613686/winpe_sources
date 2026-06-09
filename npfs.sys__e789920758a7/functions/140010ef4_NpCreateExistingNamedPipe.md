# NpCreateExistingNamedPipe

- ea: `0x140010ef4`
- end: `0x1400111ba`
- name: `NpCreateExistingNamedPipe`
- size: `710`
- prototype: `PNTSTATUS __fastcall(PNTSTATUS AccessStatus, __int64, __int64, __int64, int, PACCESS_STATE AccessState, KPROCESSOR_MODE AccessMode, int, __int16, _DWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011aa0`

## callees

- `0x140001010`
- `0x14000b030`
- `0x140010d18`
- `0x140010ef4`
- `0x1400111c0`

## import_xrefs

- `ntoskrnl!SeAppendPrivileges` at `0x14001116d`
- `ntoskrnl!SeAppendPrivileges` at `0x14001116d`
- `ntoskrnl!SeFreePrivileges` at `0x14001117d`
- `ntoskrnl!SeFreePrivileges` at `0x14001117d`
- `ntoskrnl!SeAccessCheck` at `0x140010f98`
- `ntoskrnl!SeAccessCheck` at `0x140010f98`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140010f51`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140010f51`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x14001100a`
- `ntoskrnl!SeOpenObjectAuditAlarm` at `0x14001100a`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140011019`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140011019`
- `ntoskrnl!SeLockSubjectContext` at `0x140010f45`
- `ntoskrnl!SeLockSubjectContext` at `0x140010f45`

## pseudocode

```c
PNTSTATUS __fastcall NpCreateExistingNamedPipe(
        PNTSTATUS AccessStatus,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        PACCESS_STATE AccessState,
        KPROCESSOR_MODE AccessMode,
        int a8,
        __int16 a9,
        _DWORD *a10,
        int a11,
        __int64 a12)
{
  ACCESS_MASK v12; // r15d
  PACCESS_STATE v13; // rsi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v19; // r15
  DWORD v20; // eax
  void *v21; // r9
  __int16 v22; // ax
  int v23; // eax
  __int64 v24; // rsi
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v29; // rdx
  struct _UNICODE_STRING ObjectTypeName; // [rsp+50h] [rbp-10h] BYREF
  DWORD GrantedAccess; // [rsp+A0h] [rbp+40h] BYREF
  PPRIVILEGE_SET Privileges; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v33; // [rsp+B8h] [rbp+58h] BYREF

  v12 = a5;
  v13 = AccessState;
  GrantedAccess = 0;
  *(_OWORD *)AccessStatus = 0;
  v12 |= 4u;
  v33 = 0;
  Privileges = 0;
  a5 = v12;
  ObjectTypeName = 0;
  SeLockSubjectContext(&v13->SubjectSecurityContext);
  GenericMapping = IoGetFileObjectGenericMapping();
  v19 = SeAccessCheck(
          *(PSECURITY_DESCRIPTOR *)(a3 + 152),
          &v13->SubjectSecurityContext,
          1u,
          v12,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          AccessStatus);
  if ( Privileges )
  {
    SeAppendPrivileges(v13, Privileges);
    SeFreePrivileges(Privileges);
  }
  if ( v19 )
  {
    v20 = GrantedAccess;
    v13->PreviouslyGrantedAccess |= GrantedAccess;
    v13->RemainingDesiredAccess &= ~(v20 | 0x2000000);
  }
  v21 = *(void **)(a3 + 152);
  ObjectTypeName.Buffer = L"NamedPipe";
  *(_DWORD *)&ObjectTypeName.Length = 1310738;
  SeOpenObjectAuditAlarm(
    &ObjectTypeName,
    0,
    (PUNICODE_STRING)(a4 + 88),
    v21,
    v13,
    0,
    v19,
    AccessMode,
    &v13->GenerateOnClose);
  SeUnlockSubjectContext(&v13->SubjectSecurityContext);
  if ( v19 )
  {
    if ( *(_DWORD *)(a3 + 120) >= *(_DWORD *)(a3 + 252) )
    {
      *AccessStatus = -1073741653;
    }
    else
    {
      v22 = 2;
      if ( a8 == 2 )
        goto LABEL_17;
      if ( (unsigned __int16)*(_DWORD *)(a3 + 256) == 1 )
      {
        v22 = 1;
      }
      else if ( (unsigned __int16)*(_DWORD *)(a3 + 256) )
      {
        v22 = 3;
      }
      if ( v22 != a9 )
      {
LABEL_17:
        *AccessStatus = -1073741790;
      }
      else
      {
        v23 = NpCreateCcb(a3, a4, (unsigned int)((a5 & 0xF2000003) != 0) + 1, a10[1], a10[2], a10[4], a10[5], &v33);
        *AccessStatus = v23;
        if ( v23 >= 0 )
        {
          v24 = a12;
          v25 = NpCancelWaiter((_QWORD *)(a2 + 144), (const UNICODE_STRING *)(a3 + 160), 0, a12);
          *AccessStatus = v25;
          if ( v25 < 0 )
          {
            v29 = v33;
            --*(_DWORD *)(*(_QWORD *)(v33 + 40) + 248LL);
            NpDeleteCcb(a2, v29, v24);
          }
          else
          {
            _InterlockedAdd((volatile signed __int32 *)(a3 + 124), 1u);
            v26 = v33;
            v27 = *(_QWORD *)(v33 + 40);
            *(_DWORD *)(a4 + 80) |= 0x80u;
            *(_QWORD *)(a4 + 24) = v27;
            *(_QWORD *)(a4 + 48) = 1;
            *(_QWORD *)(a4 + 32) = v26 | 3;
            *(_QWORD *)(v26 + 56) = a4;
            NpCheckForNotifyWithFilter(a2, v24, 64, (const void **)(a3 + 160), 3);
            *AccessStatus = 0;
            *((_QWORD *)AccessStatus + 1) = 1;
          }
        }
      }
    }
  }
  return AccessStatus;
}

```

## disassembly

```asm
0x140010ef4  mov     [rsp-38h+arg_8], rbx
0x140010ef9  push    rbp
0x140010efa  push    rsi
0x140010efb  push    rdi
0x140010efc  push    r12
0x140010efe  push    r13
0x140010f00  push    r14
0x140010f02  push    r15
0x140010f04  mov     rbp, rsp
0x140010f07  sub     rsp, 60h
0x140010f0b  mov     r15d, [rbp+arg_20]
0x140010f0f  xor     eax, eax
0x140010f11  mov     rsi, [rbp+AccessState]
0x140010f15  xorps   xmm0, xmm0
0x140010f18  mov     rbx, rcx
0x140010f1b  mov     [rbp+arg_0], eax
0x140010f1e  movups  xmmword ptr [rcx], xmm0
0x140010f21  or      r15d, 4
0x140010f25  mov     [rbp+arg_18], rax
0x140010f29  lea     r12, [rsi+20h]
0x140010f2d  mov     [rbp+arg_10], rax
0x140010f31  mov     rcx, r12; SubjectContext
0x140010f34  mov     [rbp+arg_20], r15d
0x140010f38  mov     r14, r9
0x140010f3b  mov     rdi, r8
0x140010f3e  mov     r13, rdx
0x140010f41  movups  xmmword ptr [rbp+ObjectTypeName.Length], xmm0
0x140010f45  call    cs:__imp_SeLockSubjectContext
0x140010f4c  nop     dword ptr [rax+rax+00h]
0x140010f51  call    cs:__imp_IoGetFileObjectGenericMapping
0x140010f58  nop     dword ptr [rax+rax+00h]
0x140010f5d  mov     [rsp+60h+AccessStatus], rbx; AccessStatus
0x140010f62  lea     rcx, [rbp+arg_0]
0x140010f66  mov     [rsp+60h+GrantedAccess], rcx; GrantedAccess
0x140010f6b  mov     r9d, r15d; DesiredAccess
0x140010f6e  mov     cl, [rbp+arg_30]
0x140010f71  mov     r8b, 1; SubjectContextLocked
0x140010f74  mov     [rsp+60h+AccessMode], cl; AccessMode
0x140010f78  mov     rdx, r12; SubjectSecurityContext
0x140010f7b  mov     rcx, [rdi+98h]; SecurityDescriptor
0x140010f82  mov     [rsp+60h+GenericMapping], rax; GenericMapping
0x140010f87  lea     rax, [rbp+arg_10]
0x140010f8b  mov     [rsp+60h+Privileges], rax; Privileges
0x140010f90  mov     [rsp+60h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140010f98  call    cs:__imp_SeAccessCheck
0x140010f9f  nop     dword ptr [rax+rax+00h]
0x140010fa4  mov     rdx, [rbp+arg_10]; Privileges
0x140010fa8  mov     r15b, al
0x140010fab  test    rdx, rdx
0x140010fae  jnz     loc_14001116A
0x140010fb4  test    r15b, r15b
0x140010fb7  jz      short loc_140010FC8
0x140010fb9  mov     eax, [rbp+arg_0]
0x140010fbc  or      [rsi+14h], eax
0x140010fbf  bts     eax, 19h
0x140010fc3  not     eax
0x140010fc5  and     [rsi+10h], eax
0x140010fc8  mov     r9, [rdi+98h]; SecurityDescriptor
0x140010fcf  lea     rax, aNamedpipe; "NamedPipe"
0x140010fd6  mov     [rbp+ObjectTypeName.Buffer], rax
0x140010fda  lea     r8, [r14+58h]; AbsoluteObjectName
0x140010fde  lea     rax, [rsi+0Ah]
0x140010fe2  mov     dword ptr [rbp+ObjectTypeName.Length], 140012h
0x140010fe9  mov     [rsp+60h+GrantedAccess], rax; GenerateOnClose
0x140010fee  lea     rcx, [rbp+ObjectTypeName]; ObjectTypeName
0x140010ff2  mov     al, [rbp+arg_30]
0x140010ff5  xor     edx, edx; Object
0x140010ff7  mov     [rsp+60h+AccessMode], al; AccessMode
0x140010ffb  mov     byte ptr [rsp+60h+GenericMapping], r15b; AccessGranted
0x140011000  mov     byte ptr [rsp+60h+Privileges], 0; ObjectCreated
0x140011005  mov     qword ptr [rsp+60h+PreviouslyGrantedAccess], rsi; AccessState
0x14001100a  call    cs:__imp_SeOpenObjectAuditAlarm
0x140011011  nop     dword ptr [rax+rax+00h]
0x140011016  mov     rcx, r12; SubjectContext
0x140011019  call    cs:__imp_SeUnlockSubjectContext
0x140011020  nop     dword ptr [rax+rax+00h]
0x140011025  test    r15b, r15b
0x140011028  jz      loc_140011146
0x14001102e  mov     eax, [rdi+0FCh]
0x140011034  cmp     [rdi+78h], eax
0x140011037  jnb     loc_140011162
0x14001103d  mov     eax, 2
0x140011042  cmp     [rbp+arg_38], eax
0x140011045  jz      loc_14001118E
0x14001104b  mov     ecx, [rdi+100h]
0x140011051  lea     r12d, [rax-1]
0x140011055  movzx   ecx, cx
0x140011058  lea     edx, [rax+1]
0x14001105b  cmp     ecx, r12d
0x14001105e  jz      loc_140011196
0x140011064  test    ecx, ecx
0x140011066  jz      short loc_14001106B
0x140011068  movzx   eax, dx
0x14001106b  cmp     ax, [rbp+arg_40]
0x140011072  jnz     loc_14001118E
0x140011078  mov     r9, [rbp+arg_48]
0x14001107f  lea     rax, [rbp+arg_18]
0x140011083  test    [rbp+arg_20], 0F2000003h
0x14001108a  mov     r8d, 0
0x140011090  mov     qword ptr [rsp+60h+AccessMode], rax
0x140011095  mov     rdx, r14
0x140011098  setnz   r8b
0x14001109c  mov     rcx, rdi
0x14001109f  mov     eax, [r9+14h]
0x1400110a3  add     r8d, r12d
0x1400110a6  mov     dword ptr [rsp+60h+GenericMapping], eax
0x1400110aa  mov     eax, [r9+10h]
0x1400110ae  mov     dword ptr [rsp+60h+Privileges], eax
0x1400110b2  mov     eax, [r9+8]
0x1400110b6  mov     r9d, [r9+4]
0x1400110ba  mov     [rsp+60h+PreviouslyGrantedAccess], eax
0x1400110be  call    NpCreateCcb
0x1400110c3  mov     [rbx], eax
0x1400110c5  test    eax, eax
0x1400110c7  js      short loc_140011146
0x1400110c9  mov     rsi, [rbp+arg_58]
0x1400110d0  lea     r15, [rdi+0A0h]
0x1400110d7  mov     r9, rsi
0x1400110da  lea     rcx, [r13+90h]
0x1400110e1  mov     rdx, r15
0x1400110e4  xor     r8d, r8d
0x1400110e7  call    NpCancelWaiter
0x1400110ec  mov     [rbx], eax
0x1400110ee  test    eax, eax
0x1400110f0  js      loc_14001119F
0x1400110f6  lock add [rdi+7Ch], r12d
0x1400110fb  mov     rcx, [rbp+arg_18]
0x1400110ff  mov     r9, r15
0x140011102  mov     r8d, 40h ; '@'
0x140011108  mov     [rsp+60h+PreviouslyGrantedAccess], 3
0x140011110  mov     rdx, rsi
0x140011113  mov     rax, [rcx+28h]
0x140011117  bts     dword ptr [r14+50h], 7
0x14001111d  mov     [r14+18h], rax
0x140011121  mov     rax, rcx
0x140011124  or      rax, 3
0x140011128  mov     [r14+30h], r12
0x14001112c  mov     [r14+20h], rax
0x140011130  mov     [rcx+38h], r14
0x140011134  mov     rcx, r13
0x140011137  call    NpCheckForNotifyWithFilter
0x14001113c  mov     dword ptr [rbx], 0
0x140011142  mov     [rbx+8], r12
0x140011146  mov     rax, rbx
0x140011149  mov     rbx, [rsp+60h+arg_8]
0x140011151  add     rsp, 60h
0x140011155  pop     r15
0x140011157  pop     r14
0x140011159  pop     r13
0x14001115b  pop     r12
0x14001115d  pop     rdi
0x14001115e  pop     rsi
0x14001115f  pop     rbp
0x140011160  retn
0x140011162  mov     dword ptr [rbx], 0C00000ABh
0x140011168  jmp     short loc_140011146
0x14001116a  mov     rcx, rsi; AccessState
0x14001116d  call    cs:__imp_SeAppendPrivileges
0x140011174  nop     dword ptr [rax+rax+00h]
0x140011179  mov     rcx, [rbp+arg_10]; Privileges
0x14001117d  call    cs:__imp_SeFreePrivileges
0x140011184  nop     dword ptr [rax+rax+00h]
0x140011189  jmp     loc_140010FB4
0x14001118e  mov     dword ptr [rbx], 0C0000022h
0x140011194  jmp     short loc_140011146
0x140011196  movzx   eax, r12w
0x14001119a  jmp     loc_14001106B
0x14001119f  mov     rdx, [rbp+arg_18]
0x1400111a3  mov     r8, rsi
0x1400111a6  mov     rcx, r13
0x1400111a9  mov     rax, [rdx+28h]
0x1400111ad  dec     dword ptr [rax+0F8h]
0x1400111b3  call    NpDeleteCcb
0x1400111b8  jmp     short loc_140011146
```
