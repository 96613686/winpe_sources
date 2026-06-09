# SmbCeFindVNetRootContext

- ea: `0x140017e60`
- end: `0x1400181ea`
- name: `SmbCeFindVNetRootContext`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400302f0`

## callees

- `0x140003480`
- `0x1400097e0`
- `0x140017e60`
- `0x140018680`
- `0x1400186e8`
- `0x1400189c0`
- `0x14003fa24`
- `0x14003fb30`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140017f1c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001800c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140017f1c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001800c`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140017ebe`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140017ebe`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017ece`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140017ece`
- `ntoskrnl!SeAccessCheck` at `0x1400181b9`
- `ntoskrnl!SeAccessCheck` at `0x1400181b9`
- `rdbss!RxDiagnosticTrace` at `0x140017fe9`
- `rdbss!RxDiagnosticTrace` at `0x140017fe9`

## pseudocode

```c
__int64 __fastcall SmbCeFindVNetRootContext(__int64 a1, _DWORD *a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v4; // rdi
  __int64 v5; // r14
  ULONG_PTR v6; // rsi
  char v9; // r12
  char v10; // dl
  _QWORD *v11; // r13
  __int64 v12; // rbx
  int v14; // ecx
  bool v15; // al
  _DWORD *v16; // rax
  int v17; // edx
  signed __int32 v18; // r9d
  int v19; // eax
  int v20; // ecx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rax
  void *v27; // rcx
  int v28; // ecx
  char v29; // [rsp+50h] [rbp-68h]
  KIRQL v30; // [rsp+51h] [rbp-67h]
  bool v31; // [rsp+52h] [rbp-66h]
  int AccessStatus; // [rsp+54h] [rbp-64h] BYREF
  _DWORD *v33; // [rsp+58h] [rbp-60h]
  DWORD GrantedAccess; // [rsp+60h] [rbp-58h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-50h] BYREF

  v3 = *(_QWORD *)(a1 + 32);
  v4 = 0;
  v5 = *(_QWORD *)(a3 + 24);
  v6 = 0;
  v33 = a2;
  v9 = (*(_BYTE *)(v3 + 749) & 8) != 0 && (*(_DWORD *)(v3 + 528) & 4) != 0;
  v30 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920));
  *(_DWORD *)(v5 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v10 = v9;
  v11 = (_QWORD *)(a3 + 48);
LABEL_5:
  v29 = v10;
  if ( (_QWORD *)*v11 == v11 )
    v12 = 0;
  else
    v12 = *v11 - 400LL;
  while ( 1 )
  {
    if ( !v12 )
    {
      if ( v10 )
      {
        *(_DWORD *)(v5 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v30);
        goto LABEL_10;
      }
      v10 = 1;
      goto LABEL_5;
    }
    v14 = *(_DWORD *)(v12 + 96);
    v15 = v14 == `RxIsGlobalMappingLuid'::`2'::globalMappingLuid && *(_DWORD *)(v12 + 100) == dword_14007025C;
    v31 = v15;
    if ( *(int *)(v12 + 12) <= 5 )
    {
      if ( *(_DWORD *)(v12 + 432) )
        break;
    }
LABEL_29:
    v25 = *(_QWORD **)(v12 + 400);
    v12 = 0;
    if ( v25 != v11 )
      v12 = (__int64)(v25 - 50);
  }
  if ( v15 )
  {
    if ( !v10 )
      goto LABEL_29;
  }
  else
  {
    v16 = v33;
    v17 = v33[18];
    if ( v14 == v17 )
    {
      if ( *(_DWORD *)(v12 + 100) == v33[19] )
        goto LABEL_20;
      v16 = v33;
    }
    if ( *(_DWORD *)(v12 + 104) != v17 || *(_DWORD *)(v12 + 108) != v16[19] )
    {
LABEL_28:
      v10 = v29;
      goto LABEL_29;
    }
  }
LABEL_20:
  SmbCeReferenceVNetRootContext(v12);
  v18 = _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 432), 1u);
  RxDiagnosticTrace(*(_QWORD *)(v12 + 16), 2, "Active VNetRoots++ %x VNetRoot %p", v18 + 1, v33);
  *(_DWORD *)(v5 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v5 + 1920), v30);
  if ( v6 )
  {
    SmbCeDereferenceVNetRootContext(v6);
    v6 = 0;
  }
  v19 = CheckCredentials(*(_QWORD *)(v12 + 128), (__int64)v33, v9);
  if ( v19 == -1073741419 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v20, (unsigned int)SessionSetupError, v3 + 412, -1073741419, 246);
    goto LABEL_24;
  }
  if ( v19 < 0 )
  {
LABEL_24:
    SmbCeDecrementActiveVNetRootsOnVNetRootContext(v12, v33, v21, v22);
    v6 = v12;
    if ( v9 || !v31 )
      goto LABEL_50;
    v30 = SmbCeAcquireSpinLock(v5, v23, v24);
    goto LABEL_28;
  }
  v26 = *(_QWORD *)(v12 + 128);
  AccessStatus = -1073741790;
  GrantedAccess = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  if ( v26
    && (v27 = *(void **)(v26 + 56)) != 0
    && !SeAccessCheck(
          v27,
          *(PSECURITY_SUBJECT_CONTEXT *)(a1 + 40),
          0,
          1u,
          0,
          0,
          &GenericMapping,
          *(_BYTE *)(v3 + 36),
          &GrantedAccess,
          &AccessStatus) )
  {
    v28 = AccessStatus;
  }
  else
  {
    v28 = 0;
    AccessStatus = 0;
  }
  if ( v28 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qLqL(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        (unsigned int)WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
        v3,
        *(_BYTE *)(v3 + 36),
        v12,
        v28);
    }
    goto LABEL_24;
  }
  v4 = v12;
LABEL_10:
  if ( !v6 )
    return v4;
LABEL_50:
  SmbCeDereferenceVNetRootContext(v6);
  return v4;
}

```

## disassembly

```asm
0x140017e60  mov     [rsp+arg_18], rbx
0x140017e65  push    rbp
0x140017e66  push    rsi
0x140017e67  push    rdi
0x140017e68  push    r12
0x140017e6a  push    r13
0x140017e6c  push    r14
0x140017e6e  push    r15
0x140017e70  sub     rsp, 80h
0x140017e77  mov     rax, cs:__security_cookie
0x140017e7e  xor     rax, rsp
0x140017e81  mov     [rsp+0B8h+var_40], rax
0x140017e86  mov     rbp, [rcx+20h]
0x140017e8a  xor     edi, edi
0x140017e8c  mov     r14, [r8+18h]
0x140017e90  xor     esi, esi
0x140017e92  mov     rbx, r8
0x140017e95  mov     [rsp+0B8h+var_60], rdx
0x140017e9a  mov     r15, rcx
0x140017e9d  test    byte ptr [rbp+2EDh], 8
0x140017ea4  jz      short loc_140017EB4
0x140017ea6  mov     eax, [rbp+210h]
0x140017eac  test    al, 4
0x140017eae  jnz     loc_140018106
0x140017eb4  xor     r12b, r12b
0x140017eb7  lea     rcx, [r14+780h]; SpinLock
0x140017ebe  call    cs:__imp_ExAcquireSpinLockExclusive
0x140017ec5  nop     dword ptr [rax+rax+00h]
0x140017eca  mov     [rsp+0B8h+var_67], al
0x140017ece  call    cs:__imp_PsGetCurrentThreadId
0x140017ed5  nop     dword ptr [rax+rax+00h]
0x140017eda  mov     [r14+930h], eax
0x140017ee1  movzx   edx, r12b
0x140017ee5  lea     r13, [rbx+30h]
0x140017ee9  mov     rbx, [r13+0]
0x140017eed  mov     [rsp+0B8h+var_68], dl
0x140017ef1  cmp     rbx, r13
0x140017ef4  jnz     short loc_140017F5D
0x140017ef6  xor     ebx, ebx
0x140017ef8  test    rbx, rbx
0x140017efb  jnz     short loc_140017F66
0x140017efd  test    dl, dl
0x140017eff  jz      loc_1400181D6
0x140017f05  movzx   edx, [rsp+0B8h+var_67]; OldIrql
0x140017f0a  lea     rcx, [r14+780h]; SpinLock
0x140017f11  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x140017f1c  call    cs:__imp_ExReleaseSpinLockExclusive
0x140017f23  nop     dword ptr [rax+rax+00h]
0x140017f28  test    rsi, rsi
0x140017f2b  jnz     loc_1400181DD
0x140017f31  mov     rax, rdi
0x140017f34  mov     rcx, [rsp+0B8h+var_40]
0x140017f39  xor     rcx, rsp; StackCookie
0x140017f3c  call    __security_check_cookie
0x140017f41  mov     rbx, [rsp+0B8h+arg_18]
0x140017f49  add     rsp, 80h
0x140017f50  pop     r15
0x140017f52  pop     r14
0x140017f54  pop     r13
0x140017f56  pop     r12
0x140017f58  pop     rdi
0x140017f59  pop     rsi
0x140017f5a  pop     rbp
0x140017f5b  retn
0x140017f5d  add     rbx, 0FFFFFFFFFFFFFE70h
0x140017f64  jmp     short loc_140017EF8
0x140017f66  mov     ecx, [rbx+60h]
0x140017f69  cmp     ecx, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x140017f6f  jz      loc_14001810E
0x140017f75  xor     al, al
0x140017f77  cmp     dword ptr [rbx+0Ch], 5
0x140017f7b  mov     [rsp+0B8h+var_66], al
0x140017f7f  jg      loc_140018081
0x140017f85  cmp     [rbx+1B0h], edi
0x140017f8b  jz      loc_140018081
0x140017f91  test    al, al
0x140017f93  jnz     loc_140018124
0x140017f99  mov     rax, [rsp+0B8h+var_60]
0x140017f9e  mov     edx, [rax+48h]
0x140017fa1  cmp     ecx, edx
0x140017fa3  jnz     loc_140018077
0x140017fa9  mov     eax, [rax+4Ch]
0x140017fac  cmp     [rbx+64h], eax
0x140017faf  jnz     loc_140018131
0x140017fb5  mov     rcx, rbx
0x140017fb8  call    SmbCeReferenceVNetRootContext
0x140017fbd  mov     r9d, 1
0x140017fc3  lock xadd [rbx+1B0h], r9d
0x140017fcc  mov     rax, [rsp+0B8h+var_60]
0x140017fd1  lea     r8, aActiveVnetroot; "Active VNetRoots++ %x VNetRoot %p"
0x140017fd8  mov     rcx, [rbx+10h]
0x140017fdc  inc     r9d
0x140017fdf  mov     edx, 2
0x140017fe4  mov     qword ptr [rsp+0B8h+PreviouslyGrantedAccess], rax
0x140017fe9  call    cs:__imp_RxDiagnosticTrace
0x140017ff0  nop     dword ptr [rax+rax+00h]
0x140017ff5  movzx   edx, [rsp+0B8h+var_67]; OldIrql
0x140017ffa  lea     rcx, [r14+780h]; SpinLock
0x140018001  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x14001800c  call    cs:__imp_ExReleaseSpinLockExclusive
0x140018013  nop     dword ptr [rax+rax+00h]
0x140018018  test    rsi, rsi
0x14001801b  jnz     loc_14001813B
0x140018021  mov     rdx, [rsp+0B8h+var_60]
0x140018026  movzx   r8d, r12b
0x14001802a  mov     rcx, [rbx+80h]
0x140018031  call    CheckCredentials
0x140018036  cmp     eax, 0C0000195h
0x14001803b  jz      loc_14001814A
0x140018041  test    eax, eax
0x140018043  jns     short loc_1400180AB
0x140018045  mov     rdx, [rsp+0B8h+var_60]
0x14001804a  mov     rcx, rbx
0x14001804d  call    SmbCeDecrementActiveVNetRootsOnVNetRootContext
0x140018052  mov     rsi, rbx
0x140018055  test    r12b, r12b
0x140018058  jnz     loc_1400181DD
0x14001805e  cmp     [rsp+0B8h+var_66], dil
0x140018063  jz      loc_1400181DD
0x140018069  mov     rcx, r14
0x14001806c  call    SmbCeAcquireSpinLock
0x140018071  mov     [rsp+0B8h+var_67], al
0x140018075  jmp     short loc_14001807C
0x140018077  cmp     [rbx+68h], edx
0x14001807a  jz      short loc_14001809D
0x14001807c  movzx   edx, [rsp+0B8h+var_68]
0x140018081  mov     rcx, [rbx+190h]
0x140018088  xor     ebx, ebx
0x14001808a  cmp     rcx, r13
0x14001808d  lea     rax, [rcx-190h]
0x140018094  cmovnz  rbx, rax
0x140018098  jmp     loc_140017EF8
0x14001809d  mov     eax, [rax+4Ch]
0x1400180a0  cmp     [rbx+6Ch], eax
0x1400180a3  jz      loc_140017FB5
0x1400180a9  jmp     short loc_14001807C
0x1400180ab  mov     rax, [rbx+80h]
0x1400180b2  mov     [rsp+0B8h+var_64], 0C0000022h
0x1400180ba  mov     [rsp+0B8h+var_58], edi
0x1400180be  mov     [rsp+0B8h+var_50.GenericRead], 120089h
0x1400180c6  mov     [rsp+0B8h+var_50.GenericWrite], 120116h
0x1400180ce  mov     [rsp+0B8h+var_50.GenericExecute], 1200A0h
0x1400180d6  mov     [rsp+0B8h+var_50.GenericAll], 1F01FFh
0x1400180de  test    rax, rax
0x1400180e1  jz      short loc_1400180F0
0x1400180e3  mov     rcx, [rax+38h]; SecurityDescriptor
0x1400180e7  test    rcx, rcx
0x1400180ea  jnz     loc_14001817D
0x1400180f0  xor     ecx, ecx
0x1400180f2  mov     [rsp+0B8h+var_64], ecx
0x1400180f6  test    ecx, ecx
0x1400180f8  js      loc_14005DE3A
0x1400180fe  mov     rdi, rbx
0x140018101  jmp     loc_140017F28
0x140018106  mov     r12b, 1
0x140018109  jmp     loc_140017EB7
0x14001810e  mov     eax, cs:dword_14007025C
0x140018114  cmp     [rbx+64h], eax
0x140018117  jnz     loc_140017F75
0x14001811d  mov     al, 1
0x14001811f  jmp     loc_140017F77
0x140018124  test    dl, dl
0x140018126  jz      loc_140018081
0x14001812c  jmp     loc_140017FB5
0x140018131  mov     rax, [rsp+0B8h+var_60]
0x140018136  jmp     loc_140018077
0x14001813b  mov     rcx, rsi; BugCheckParameter2
0x14001813e  call    SmbCeDereferenceVNetRootContext
0x140018143  xor     esi, esi
0x140018145  jmp     loc_140018021
0x14001814a  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140018151  jz      loc_140018045
0x140018157  lea     r8, [rbp+19Ch]
0x14001815e  mov     [rsp+0B8h+PreviouslyGrantedAccess], 303006F6h
0x140018166  mov     r9d, 0C0000195h
0x14001816c  lea     rdx, SessionSetupError
0x140018173  call    McTemplateK0qqq_EtwWriteTransfer
0x140018178  jmp     loc_140018045
0x14001817d  mov     rdx, [r15+28h]; SubjectSecurityContext
0x140018181  lea     rax, [rsp+0B8h+var_64]
0x140018186  mov     [rsp+0B8h+AccessStatus], rax; AccessStatus
0x14001818b  mov     r9d, 1; DesiredAccess
0x140018191  lea     rax, [rsp+0B8h+var_58]
0x140018196  xor     r8d, r8d; SubjectContextLocked
0x140018199  mov     [rsp+0B8h+GrantedAccess], rax; GrantedAccess
0x14001819e  movzx   eax, byte ptr [rbp+24h]
0x1400181a2  mov     [rsp+0B8h+AccessMode], al; AccessMode
0x1400181a6  lea     rax, [rsp+0B8h+var_50]
0x1400181ab  mov     [rsp+0B8h+GenericMapping], rax; GenericMapping
0x1400181b0  mov     [rsp+0B8h+Privileges], rdi; Privileges
0x1400181b5  mov     [rsp+0B8h+PreviouslyGrantedAccess], edi; PreviouslyGrantedAccess
0x1400181b9  call    cs:__imp_SeAccessCheck
0x1400181c0  nop     dword ptr [rax+rax+00h]
0x1400181c5  test    al, al
0x1400181c7  jnz     loc_1400180F0
0x1400181cd  mov     ecx, [rsp+0B8h+var_64]
0x1400181d1  jmp     loc_1400180F6
0x1400181d6  mov     dl, 1
0x1400181d8  jmp     loc_140017EE9
0x1400181dd  mov     rcx, rsi; BugCheckParameter2
0x1400181e0  call    SmbCeDereferenceVNetRootContext
0x1400181e5  jmp     loc_140017F31
0x14005de3a  mov     r10, cs:WPP_GLOBAL_Control
0x14005de41  lea     rax, WPP_GLOBAL_Control
0x14005de48  cmp     r10, rax
0x14005de4b  jz      loc_140018045
0x14005de51  mov     eax, [r10+2Ch]
0x14005de55  test    al, 1
0x14005de57  jz      loc_140018045
0x14005de5d  cmp     byte ptr [r10+29h], 1
0x14005de62  jb      loc_140018045
0x14005de68  movsx   eax, byte ptr [rbp+24h]
0x14005de6c  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14005de73  mov     dword ptr [rsp+0B8h+GenericMapping], ecx
0x14005de77  mov     edx, 20h ; ' '
0x14005de7c  mov     rcx, [r10+18h]
0x14005de80  mov     r9, rbp
0x14005de83  mov     [rsp+0B8h+Privileges], rbx
0x14005de88  mov     [rsp+0B8h+PreviouslyGrantedAccess], eax
0x14005de8c  call    WPP_SF_qLqL
0x14005de91  nop
0x14005de92  jmp     loc_140018045
```
