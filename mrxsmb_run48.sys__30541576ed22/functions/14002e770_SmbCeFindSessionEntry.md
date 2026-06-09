# SmbCeFindSessionEntry

- ea: `0x14002e770`
- end: `0x14002ed72`
- name: `SmbCeFindSessionEntry`
- size: `1538`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002dff0`

## callees

- `0x140005b20`
- `0x1400186e8`
- `0x140018abc`
- `0x140021130`
- `0x14002e770`
- `0x140037fa4`
- `0x14003fa24`
- `0x14003fb30`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!ExBlockOnAddressPushLock` at `0x14002e942`
- `ntoskrnl!ExBlockOnAddressPushLock` at `0x14002ea62`
- `ntoskrnl!ExBlockOnAddressPushLock` at `0x14002e942`
- `ntoskrnl!ExBlockOnAddressPushLock` at `0x14002ea62`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002e8ee`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ea14`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ebd4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002e8ee`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ea14`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ebd4`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002e7fd`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002e960`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002ea80`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002e7fd`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002e960`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002ea80`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002e80c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002e96f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002ea8f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002e80c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002e96f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002ea8f`
- `ntoskrnl!SeAccessCheck` at `0x14002ecee`
- `ntoskrnl!SeAccessCheck` at `0x14002ecee`
- `rdbss!RxDiagnosticTrace` at `0x14002eb62`
- `rdbss!RxDiagnosticTrace` at `0x14002eb62`

## pseudocode

```c
__int64 __fastcall SmbCeFindSessionEntry(__int64 a1, __int64 a2, ULONG_PTR *a3, __int64 a4)
{
  __int64 v4; // rax
  ULONG_PTR v5; // rbp
  __int64 v6; // r12
  bool v8; // zf
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // r14
  int v12; // eax
  KIRQL v13; // di
  __int64 v14; // rax
  __int64 v15; // rbx
  ULONG_PTR v16; // rbx
  __int64 v17; // rdx
  int v18; // ecx
  signed __int32 v19; // r8d
  int v20; // r9d
  signed __int32 v21; // r8d
  __int64 v22; // rcx
  int v23; // edi
  int v25; // eax
  int v26; // r9d
  __int64 v27; // rcx
  signed __int32 v28; // r8d
  int v29; // eax
  int v30; // ecx
  __int64 v31; // rax
  void *v32; // rcx
  BOOLEAN v33; // al
  char i; // [rsp+50h] [rbp-88h] BYREF
  unsigned __int8 v35; // [rsp+51h] [rbp-87h]
  DWORD GrantedAccess[2]; // [rsp+58h] [rbp-80h] BYREF
  int AccessStatus[2]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v38; // [rsp+68h] [rbp-70h]
  ULONG_PTR *v39; // [rsp+70h] [rbp-68h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-60h] BYREF

  v4 = *(_QWORD *)(a2 + 32);
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 32);
  v38 = a1;
  v8 = (*(_BYTE *)(v6 + 749) & 8) == 0;
  v9 = *(_QWORD *)(v4 + 32);
  *(_QWORD *)AccessStatus = a4;
  v39 = a3;
  v10 = *(_QWORD *)(v9 + 32);
  v11 = *(_QWORD *)(v10 + 24);
  if ( v8 || (v12 = *(_DWORD *)(v6 + 528), v35 = 1, (v12 & 4) == 0) )
    v35 = 0;
  v13 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920));
  *(_DWORD *)(v11 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v14 = v10 + 528;
  v15 = *(_QWORD *)(v10 + 528);
  *(_QWORD *)GrantedAccess = v14;
  if ( v15 == v14 || (v16 = v15 - 392) == 0 )
  {
LABEL_37:
    **(_BYTE **)AccessStatus = v13;
    v23 = -1073741275;
    goto LABEL_38;
  }
  v17 = v14;
  while ( 1 )
  {
    if ( *(int *)(v16 + 12) > 5 )
      goto LABEL_34;
    v18 = *(_DWORD *)(a2 + 72);
    if ( (*(_DWORD *)(v16 + 96) != v18 || *(_DWORD *)(v16 + 100) != *(_DWORD *)(a2 + 76))
      && (*(_DWORD *)(v16 + 104) != v18 || *(_DWORD *)(v16 + 108) != *(_DWORD *)(a2 + 76)) )
    {
      goto LABEL_34;
    }
    if ( *(_BYTE *)(v16 + 657) )
      break;
    v19 = _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
        v16,
        v19 - 1,
        v19);
    }
    *(_DWORD *)(v11 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920), v13);
    if ( v5 )
      SmbCeDereferenceSessionEntryEx(v5);
    for ( i = *(_BYTE *)(v16 + 657); !i; i = *(_BYTE *)(v16 + 657) )
      ExBlockOnAddressPushLock(v16 + 664, v16 + 657, &i, 1, 0);
    v13 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920));
    *(_DWORD *)(v11 + 2352) = (unsigned int)PsGetCurrentThreadId();
    v5 = v16;
    if ( *(int *)(v16 + 12) <= 5 )
      break;
LABEL_33:
    v17 = *(_QWORD *)GrantedAccess;
LABEL_34:
    v22 = *(_QWORD *)(v16 + 392);
    v16 = 0;
    if ( v22 != v17 )
      v16 = v22 - 392;
    if ( !v16 )
      goto LABEL_37;
  }
  v20 = *(_DWORD *)(v16 + 424);
  if ( !v20 )
  {
    if ( !*(_BYTE *)(v16 + 658) )
    {
      v21 = _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
          v16,
          v21 - 1,
          v21);
      }
      *(_DWORD *)(v11 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920), v13);
      if ( v5 )
        SmbCeDereferenceSessionEntryEx(v5);
      for ( i = *(_BYTE *)(v16 + 658); !i; i = *(_BYTE *)(v16 + 658) )
        ExBlockOnAddressPushLock(v16 + 664, v16 + 658, &i, 1, 0);
      v13 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920));
      *(_DWORD *)(v11 + 2352) = (unsigned int)PsGetCurrentThreadId();
      v5 = v16;
    }
    goto LABEL_33;
  }
  v25 = ++*(_DWORD *)(v16 + 428);
  v26 = v20 + 1;
  v27 = *(_QWORD *)(v16 + 16);
  *(_DWORD *)(v16 + 424) = v26;
  RxDiagnosticTrace(v27, 2, "Active VnrCtxts++ %x, Total VnrCtxts++ %x", v26, v25);
  v28 = _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      &WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
      v16,
      v28 - 1,
      v28);
  }
  *(_DWORD *)(v11 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920), v13);
  if ( v5 )
  {
    SmbCeDereferenceSessionEntryEx(v5);
    v5 = 0;
  }
  v29 = CheckCredentials(*(_QWORD *)(v16 + 128), a2, v35);
  v23 = v29;
  if ( v29 == -1073741419 )
  {
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v30, (unsigned int)&SessionSetupError, v6 + 412, -1073741419, 222);
    goto LABEL_50;
  }
  if ( v29 < 0 )
    goto LABEL_50;
  v31 = *(_QWORD *)(v16 + 128);
  AccessStatus[0] = -1073741790;
  GrantedAccess[0] = 0;
  GenericMapping.GenericRead = 1179785;
  GenericMapping.GenericWrite = 1179926;
  GenericMapping.GenericExecute = 1179808;
  GenericMapping.GenericAll = 2032127;
  if ( !v31
    || (v32 = *(void **)(v31 + 56)) == 0
    || (v33 = SeAccessCheck(
                v32,
                *(PSECURITY_SUBJECT_CONTEXT *)(v38 + 40),
                0,
                1u,
                0,
                0,
                &GenericMapping,
                *(_BYTE *)(v6 + 36),
                GrantedAccess,
                AccessStatus),
        v23 = AccessStatus[0],
        v33) )
  {
    v23 = 0;
  }
  if ( v23 >= 0 )
  {
    *v39 = v16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qLqL(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (unsigned int)&WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
        v6,
        *(_BYTE *)(v6 + 36),
        v16,
        v23);
    }
LABEL_50:
    SmbCeDecrementActiveVNetRootContextsOnSession(v16);
    SmbCeDecrementTotalVNetRootContextsOnSession(v16);
    v5 = v16;
  }
LABEL_38:
  if ( v5 )
    SmbCeDereferenceSessionEntryEx(v5);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14002e770  mov     r11, rsp
0x14002e773  push    rbp
0x14002e774  push    rdi
0x14002e775  sub     rsp, 0C8h
0x14002e77c  mov     rax, cs:__security_cookie
0x14002e783  xor     rax, rsp
0x14002e786  mov     [rsp+0D8h+var_50], rax
0x14002e78e  mov     rax, [rdx+20h]
0x14002e792  xor     ebp, ebp
0x14002e794  mov     [r11-18h], rbx
0x14002e798  mov     [r11-28h], r12
0x14002e79c  mov     r12, [rcx+20h]
0x14002e7a0  mov     [r11-30h], r13
0x14002e7a4  mov     r13, rdx
0x14002e7a7  mov     [r11-38h], r14
0x14002e7ab  mov     [rsp+0D8h+var_70], rcx
0x14002e7b0  test    byte ptr [r12+2EDh], 8
0x14002e7b9  mov     rcx, [rax+20h]
0x14002e7bd  mov     [r11-40h], r15
0x14002e7c1  mov     qword ptr [rsp+0D8h+var_78], r9
0x14002e7c6  mov     [rsp+0D8h+var_68], r8
0x14002e7cb  mov     rbx, [rcx+20h]
0x14002e7cf  mov     r14, [rbx+18h]
0x14002e7d3  jz      short loc_14002E7E6
0x14002e7d5  mov     eax, [r12+210h]
0x14002e7dd  mov     [rsp+0D8h+var_87], 1
0x14002e7e2  test    al, 4
0x14002e7e4  jnz     short loc_14002E7EB
0x14002e7e6  mov     [rsp+0D8h+var_87], bpl
0x14002e7eb  lea     r15, [r14+780h]
0x14002e7f2  mov     [rsp+0D8h+var_20], rsi
0x14002e7fa  mov     rcx, r15; SpinLock
0x14002e7fd  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002e804  nop     dword ptr [rax+rax+00h]
0x14002e809  movzx   edi, al
0x14002e80c  call    cs:__imp_PsGetCurrentThreadId
0x14002e813  nop     dword ptr [rax+rax+00h]
0x14002e818  mov     [r14+930h], eax
0x14002e81f  lea     rax, [rbx+210h]
0x14002e826  mov     rbx, [rax]
0x14002e829  mov     qword ptr [rsp+0D8h+var_80], rax
0x14002e82e  cmp     rbx, rax
0x14002e831  jz      loc_14002EACA
0x14002e837  add     rbx, 0FFFFFFFFFFFFFE78h
0x14002e83e  jz      loc_14002EACA
0x14002e844  mov     rdx, rax
0x14002e847  cmp     dword ptr [rbx+0Ch], 5
0x14002e84b  lea     r10, WPP_GLOBAL_Control
0x14002e852  jg      loc_14002EAAA
0x14002e858  mov     ecx, [r13+48h]
0x14002e85c  cmp     [rbx+60h], ecx
0x14002e85f  jnz     short loc_14002E86A
0x14002e861  mov     eax, [r13+4Ch]
0x14002e865  cmp     [rbx+64h], eax
0x14002e868  jz      short loc_14002E880
0x14002e86a  cmp     [rbx+68h], ecx
0x14002e86d  jnz     loc_14002EAAA
0x14002e873  mov     eax, [r13+4Ch]
0x14002e877  cmp     [rbx+6Ch], eax
0x14002e87a  jnz     loc_14002EAAA
0x14002e880  movzx   eax, byte ptr [rbx+291h]
0x14002e887  test    al, al
0x14002e889  jnz     loc_14002E996
0x14002e88f  mov     r8d, 1
0x14002e895  lock xadd [rbx+8], r8d
0x14002e89b  inc     r8d
0x14002e89e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e8a5  cmp     rcx, r10
0x14002e8a8  jz      short loc_14002E8DC
0x14002e8aa  mov     eax, [rcx+2Ch]
0x14002e8ad  test    al, 40h
0x14002e8af  jz      short loc_14002E8DC
0x14002e8b1  cmp     byte ptr [rcx+29h], 4
0x14002e8b5  jb      short loc_14002E8DC
0x14002e8b7  mov     rcx, [rcx+18h]
0x14002e8bb  lea     eax, [r8-1]
0x14002e8bf  mov     dword ptr [rsp+0D8h+Privileges], r8d
0x14002e8c4  mov     edx, 14h
0x14002e8c9  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002e8d0  mov     [rsp+0D8h+PreviouslyGrantedAccess], eax
0x14002e8d4  mov     r9, rbx
0x14002e8d7  call    WPP_SF_qDD
0x14002e8dc  movzx   edx, dil; OldIrql
0x14002e8e0  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x14002e8eb  mov     rcx, r15; SpinLock
0x14002e8ee  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002e8f5  nop     dword ptr [rax+rax+00h]
0x14002e8fa  test    rbp, rbp
0x14002e8fd  jz      short loc_14002E909
0x14002e8ff  xor     edx, edx
0x14002e901  mov     rcx, rbp; BugCheckParameter2
0x14002e904  call    SmbCeDereferenceSessionEntryEx
0x14002e909  movzx   eax, byte ptr [rbx+291h]
0x14002e910  mov     [rsp+0D8h+var_88], al
0x14002e914  test    al, al
0x14002e916  jnz     short loc_14002E95D
0x14002e918  nop     dword ptr [rax+rax+00000000h]
0x14002e920  mov     r9d, 1
0x14002e926  mov     qword ptr [rsp+0D8h+PreviouslyGrantedAccess], 0
0x14002e92f  lea     r8, [rsp+0D8h+var_88]
0x14002e934  lea     rdx, [rbx+291h]
0x14002e93b  lea     rcx, [rbx+298h]
0x14002e942  call    cs:__imp_ExBlockOnAddressPushLock
0x14002e949  nop     dword ptr [rax+rax+00h]
0x14002e94e  movzx   eax, byte ptr [rbx+291h]
0x14002e955  mov     [rsp+0D8h+var_88], al
0x14002e959  test    al, al
0x14002e95b  jz      short loc_14002E920
0x14002e95d  mov     rcx, r15; SpinLock
0x14002e960  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002e967  nop     dword ptr [rax+rax+00h]
0x14002e96c  movzx   edi, al
0x14002e96f  call    cs:__imp_PsGetCurrentThreadId
0x14002e976  nop     dword ptr [rax+rax+00h]
0x14002e97b  mov     [r14+930h], eax
0x14002e982  mov     rbp, rbx
0x14002e985  cmp     dword ptr [rbx+0Ch], 5
0x14002e989  jg      loc_14002EAA5
0x14002e98f  lea     r10, WPP_GLOBAL_Control
0x14002e996  mov     r9d, [rbx+1A8h]
0x14002e99d  test    r9d, r9d
0x14002e9a0  jnz     loc_14002EB38
0x14002e9a6  movzx   eax, byte ptr [rbx+292h]
0x14002e9ad  test    al, al
0x14002e9af  jnz     loc_14002EAA5
0x14002e9b5  mov     r8d, 1
0x14002e9bb  lock xadd [rbx+8], r8d
0x14002e9c1  inc     r8d
0x14002e9c4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e9cb  cmp     rcx, r10
0x14002e9ce  jz      short loc_14002EA02
0x14002e9d0  mov     eax, [rcx+2Ch]
0x14002e9d3  test    al, 40h
0x14002e9d5  jz      short loc_14002EA02
0x14002e9d7  cmp     byte ptr [rcx+29h], 4
0x14002e9db  jb      short loc_14002EA02
0x14002e9dd  mov     rcx, [rcx+18h]
0x14002e9e1  lea     eax, [r8-1]
0x14002e9e5  mov     dword ptr [rsp+0D8h+Privileges], r8d
0x14002e9ea  mov     edx, 14h
0x14002e9ef  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002e9f6  mov     [rsp+0D8h+PreviouslyGrantedAccess], eax
0x14002e9fa  mov     r9, rbx
0x14002e9fd  call    WPP_SF_qDD
0x14002ea02  movzx   edx, dil; OldIrql
0x14002ea06  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x14002ea11  mov     rcx, r15; SpinLock
0x14002ea14  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002ea1b  nop     dword ptr [rax+rax+00h]
0x14002ea20  test    rbp, rbp
0x14002ea23  jz      short loc_14002EA2F
0x14002ea25  xor     edx, edx
0x14002ea27  mov     rcx, rbp; BugCheckParameter2
0x14002ea2a  call    SmbCeDereferenceSessionEntryEx
0x14002ea2f  movzx   eax, byte ptr [rbx+292h]
0x14002ea36  mov     [rsp+0D8h+var_88], al
0x14002ea3a  test    al, al
0x14002ea3c  jnz     short loc_14002EA7D
0x14002ea3e  xchg    ax, ax
0x14002ea40  mov     r9d, 1
0x14002ea46  mov     qword ptr [rsp+0D8h+PreviouslyGrantedAccess], 0
0x14002ea4f  lea     r8, [rsp+0D8h+var_88]
0x14002ea54  lea     rdx, [rbx+292h]
0x14002ea5b  lea     rcx, [rbx+298h]
0x14002ea62  call    cs:__imp_ExBlockOnAddressPushLock
0x14002ea69  nop     dword ptr [rax+rax+00h]
0x14002ea6e  movzx   eax, byte ptr [rbx+292h]
0x14002ea75  mov     [rsp+0D8h+var_88], al
0x14002ea79  test    al, al
0x14002ea7b  jz      short loc_14002EA40
0x14002ea7d  mov     rcx, r15; SpinLock
0x14002ea80  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002ea87  nop     dword ptr [rax+rax+00h]
0x14002ea8c  movzx   edi, al
0x14002ea8f  call    cs:__imp_PsGetCurrentThreadId
0x14002ea96  nop     dword ptr [rax+rax+00h]
0x14002ea9b  mov     [r14+930h], eax
0x14002eaa2  mov     rbp, rbx
0x14002eaa5  mov     rdx, qword ptr [rsp+0D8h+var_80]
0x14002eaaa  mov     rcx, [rbx+188h]
0x14002eab1  xor     ebx, ebx
0x14002eab3  cmp     rcx, rdx
0x14002eab6  lea     rax, [rcx-188h]
0x14002eabd  cmovnz  rbx, rax
0x14002eac1  test    rbx, rbx
0x14002eac4  jnz     loc_14002E847
0x14002eaca  mov     rax, qword ptr [rsp+0D8h+var_78]
0x14002eacf  mov     sil, 1
0x14002ead2  mov     [rax], dil
0x14002ead5  mov     edi, 0C0000225h
0x14002eada  mov     r15, [rsp+0D8h+var_40]
0x14002eae2  mov     r14, [rsp+0D8h+var_38]
0x14002eaea  mov     r13, [rsp+0D8h+var_30]
0x14002eaf2  mov     r12, [rsp+0D8h+var_28]
0x14002eafa  mov     rbx, [rsp+0D8h+var_18]
0x14002eb02  test    rbp, rbp
0x14002eb05  jz      short loc_14002EB13
0x14002eb07  movzx   edx, sil
0x14002eb0b  mov     rcx, rbp; BugCheckParameter2
0x14002eb0e  call    SmbCeDereferenceSessionEntryEx
0x14002eb13  mov     rsi, [rsp+0D8h+var_20]
0x14002eb1b  mov     eax, edi
0x14002eb1d  mov     rcx, [rsp+0D8h+var_50]
0x14002eb25  xor     rcx, rsp; StackCookie
0x14002eb28  call    __security_check_cookie
0x14002eb2d  add     rsp, 0C8h
0x14002eb34  pop     rdi
0x14002eb35  pop     rbp
0x14002eb36  retn
0x14002eb38  inc     dword ptr [rbx+1ACh]
0x14002eb3e  lea     r8, aActiveVnrctxts_0; "Active VnrCtxts++ %x, Total VnrCtxts++ "...
0x14002eb45  mov     eax, [rbx+1ACh]
0x14002eb4b  inc     r9d
0x14002eb4e  mov     rcx, [rbx+10h]
0x14002eb52  mov     edx, 2
0x14002eb57  mov     [rbx+1A8h], r9d
0x14002eb5e  mov     [rsp+0D8h+PreviouslyGrantedAccess], eax
0x14002eb62  call    cs:__imp_RxDiagnosticTrace
0x14002eb69  nop     dword ptr [rax+rax+00h]
0x14002eb6e  mov     r8d, 1
0x14002eb74  lock xadd [rbx+8], r8d
0x14002eb7a  inc     r8d
0x14002eb7d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002eb84  lea     rax, WPP_GLOBAL_Control
0x14002eb8b  cmp     rcx, rax
0x14002eb8e  jz      short loc_14002EBC2
0x14002eb90  mov     eax, [rcx+2Ch]
0x14002eb93  test    al, 40h
0x14002eb95  jz      short loc_14002EBC2
0x14002eb97  cmp     byte ptr [rcx+29h], 4
0x14002eb9b  jb      short loc_14002EBC2
0x14002eb9d  mov     rcx, [rcx+18h]
0x14002eba1  lea     eax, [r8-1]
0x14002eba5  mov     dword ptr [rsp+0D8h+Privileges], r8d
0x14002ebaa  mov     edx, 14h
0x14002ebaf  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x14002ebb6  mov     [rsp+0D8h+PreviouslyGrantedAccess], eax
0x14002ebba  mov     r9, rbx
0x14002ebbd  call    WPP_SF_qDD
0x14002ebc2  movzx   edx, dil; OldIrql
0x14002ebc6  mov     dword ptr [r14+930h], 0FFFFFFFFh
0x14002ebd1  mov     rcx, r15; SpinLock
0x14002ebd4  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002ebdb  nop     dword ptr [rax+rax+00h]
0x14002ebe0  xor     sil, sil
0x14002ebe3  test    rbp, rbp
0x14002ebe6  jz      short loc_14002EBFA
0x14002ebe8  xor     edx, edx
0x14002ebea  mov     rcx, rbp; BugCheckParameter2
0x14002ebed  call    SmbCeDereferenceSessionEntryEx
0x14002ebf2  xor     r14d, r14d
0x14002ebf5  mov     ebp, r14d
0x14002ebf8  jmp     short loc_14002EBFD
0x14002ebfa  xor     r14d, r14d
0x14002ebfd  movzx   r8d, [rsp+0D8h+var_87]
0x14002ec03  mov     rdx, r13
0x14002ec06  mov     rcx, [rbx+80h]
0x14002ec0d  call    CheckCredentials
0x14002ec12  mov     edi, eax
0x14002ec14  cmp     eax, 0C0000195h
0x14002ec19  jnz     short loc_14002EC5E
0x14002ec1b  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x14002ec22  jz      short loc_14002EC46
0x14002ec24  lea     r8, [r12+19Ch]
0x14002ec2c  mov     [rsp+0D8h+PreviouslyGrantedAccess], 302002DEh
0x14002ec34  mov     r9d, 0C0000195h
0x14002ec3a  lea     rdx, SessionSetupError
0x14002ec41  call    McTemplateK0qqq_EtwWriteTransfer
0x14002ec46  mov     rcx, rbx
0x14002ec49  call    SmbCeDecrementActiveVNetRootContextsOnSession
0x14002ec4e  mov     rcx, rbx
0x14002ec51  call    SmbCeDecrementTotalVNetRootContextsOnSession
0x14002ec56  mov     rbp, rbx
0x14002ec59  jmp     loc_14002EADA
0x14002ec5e  test    eax, eax
0x14002ec60  js      short loc_14002EC46
0x14002ec62  mov     rax, [rbx+80h]
0x14002ec69  mov     [rsp+0D8h+var_78], 0C0000022h
0x14002ec71  mov     [rsp+0D8h+var_80], r14d
0x14002ec76  mov     [rsp+0D8h+var_60.GenericRead], 120089h
0x14002ec7e  mov     [rsp+0D8h+var_60.GenericWrite], 120116h
0x14002ec86  mov     [rsp+0D8h+var_60.GenericExecute], 1200A0h
0x14002ec91  mov     [rsp+0D8h+var_60.GenericAll], 1F01FFh
0x14002ec9c  test    rax, rax
0x14002ec9f  jz      short loc_14002ED02
0x14002eca1  mov     rcx, [rax+38h]; SecurityDescriptor
0x14002eca5  test    rcx, rcx
0x14002eca8  jz      short loc_14002ED02
0x14002ecaa  mov     rdx, [rsp+0D8h+var_70]
0x14002ecaf  lea     rax, [rsp+0D8h+var_78]
0x14002ecb4  mov     [rsp+0D8h+AccessStatus], rax; AccessStatus
0x14002ecb9  mov     r9d, 1; DesiredAccess
0x14002ecbf  lea     rax, [rsp+0D8h+var_80]
0x14002ecc4  xor     r8d, r8d; SubjectContextLocked
0x14002ecc7  mov     [rsp+0D8h+GrantedAccess], rax; GrantedAccess
0x14002eccc  movzx   eax, byte ptr [r12+24h]
0x14002ecd2  mov     rdx, [rdx+28h]; SubjectSecurityContext
0x14002ecd6  mov     [rsp+0D8h+AccessMode], al; AccessMode
0x14002ecda  lea     rax, [rsp+0D8h+var_60]
0x14002ecdf  mov     [rsp+0D8h+GenericMapping], rax; GenericMapping
  ... truncated ...
```
