# DifNtOpenTransactionWrapper

- ea: `0x14065cd40`
- end: `0x14065cecd`
- name: `DifNtOpenTransactionWrapper`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x14065cd40`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransaction` at `0x14065ce41`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransaction` at `0x14065ce41`

## pseudocode

```c
__int64 __fastcall DifNtOpenTransactionWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        OBJECT_ATTRIBUTES *a3,
        GUID *a4,
        HANDLE TmHandle)
{
  __int64 APIThunkContextById; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r14
  __int64 v13; // rcx
  BOOLEAN v14; // si
  _QWORD *i; // rbx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  BOOLEAN v19; // di
  _QWORD *j; // rbx
  __int128 v22; // [rsp+30h] [rbp-48h] BYREF
  __int128 v23; // [rsp+40h] [rbp-38h]
  __int128 v24; // [rsp+50h] [rbp-28h]
  __int64 v25; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v25 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(535);
  v12 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v13 = *(unsigned int *)(APIThunkContextById + 12);
    if ( (v13 & 0x18) != 0 )
    {
      *(_QWORD *)&v22 = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      *(_QWORD *)&v22 = DifGetReturnAddressForWrappers(v13, v9, v10, v11);
    }
    *((_QWORD *)&v24 + 1) = a1;
    *((_QWORD *)&v22 + 1) = TmHandle;
    LODWORD(v24) = a2;
    *((_QWORD *)&v23 + 1) = a3;
    *(_QWORD *)&v23 = a4;
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v12 + 32); i != (_QWORD *)(v12 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v22, v9, v10, v11);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v25) = NtOpenTransaction(a1, a2, a3, a4, TmHandle);
  if ( v12 )
  {
    if ( !VfDifRunningWithoutReboot && (v19 = 0, (VfOptionFlags & 0x800) == 0)
      || (v19 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v12 + 48); j != (_QWORD *)(v12 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v22, v16, v17, v18);
      }
      if ( v19 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14065cd40  mov     [rsp-40h+TransactionHandle], rcx
0x14065cd45  push    rbp
0x14065cd46  push    rbx
0x14065cd47  push    rsi
0x14065cd48  push    rdi
0x14065cd49  push    r12
0x14065cd4b  push    r13
0x14065cd4d  push    r14
0x14065cd4f  push    r15
0x14065cd51  mov     rbp, rsp
0x14065cd54  sub     rsp, 78h
0x14065cd58  xorps   xmm0, xmm0
0x14065cd5b  xor     eax, eax
0x14065cd5d  mov     ecx, 217h
0x14065cd62  mov     [rbp+var_18], rax
0x14065cd66  movups  [rbp+var_48], xmm0
0x14065cd6a  mov     r15, r9
0x14065cd6d  mov     r12, r8
0x14065cd70  movups  [rbp+var_38], xmm0
0x14065cd74  mov     r13d, edx
0x14065cd77  movups  [rbp+var_28], xmm0
0x14065cd7b  call    DifGetAPIThunkContextById
0x14065cd80  mov     r14, rax
0x14065cd83  test    rax, rax
0x14065cd86  jz      loc_14065CE2B
0x14065cd8c  mov     ecx, [rax+0Ch]
0x14065cd8f  test    cl, 18h
0x14065cd92  jz      short loc_14065CD9E
0x14065cd94  mov     rcx, [rbp+40h]
0x14065cd98  mov     qword ptr [rbp+var_48], rcx
0x14065cd9c  jmp     short loc_14065CDAC
0x14065cd9e  test    cl, 4
0x14065cda1  jz      short loc_14065CDAC
0x14065cda3  call    DifGetReturnAddressForWrappers
0x14065cda8  mov     qword ptr [rbp+var_48], rax
0x14065cdac  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065cdb3  mov     rax, [rbp+TransactionHandle]
0x14065cdb7  mov     qword ptr [rbp+var_28+8], rax
0x14065cdbb  mov     rax, [rbp+arg_20]
0x14065cdbf  mov     qword ptr [rbp+var_48+8], rax
0x14065cdc3  mov     dword ptr [rbp+var_28], r13d
0x14065cdc7  mov     qword ptr [rbp+var_38+8], r12
0x14065cdcb  mov     qword ptr [rbp+var_38], r15
0x14065cdcf  jnz     short loc_14065CDE0
0x14065cdd1  xor     sil, sil
0x14065cdd4  test    cs:VfOptionFlags, 800h
0x14065cdde  jz      short loc_14065CDF3
0x14065cde0  lea     rcx, DifRebootlessRundown; RunRef
0x14065cde7  call    ExAcquireRundownProtection_0
0x14065cdec  mov     sil, al
0x14065cdef  test    al, al
0x14065cdf1  jz      short loc_14065CE2B
0x14065cdf3  lea     rdi, [r14+20h]
0x14065cdf7  mov     rbx, [rdi]
0x14065cdfa  jmp     short loc_14065CE15
0x14065cdfc  lea     rax, [rbx-10h]
0x14065ce00  test    rax, rax
0x14065ce03  jz      short loc_14065CE12
0x14065ce05  mov     rax, [rax+8]
0x14065ce09  lea     rcx, [rbp+var_48]
0x14065ce0d  call    _guard_dispatch_icall_no_overrides
0x14065ce12  mov     rbx, [rbx]
0x14065ce15  cmp     rbx, rdi
0x14065ce18  jnz     short loc_14065CDFC
0x14065ce1a  test    sil, sil
0x14065ce1d  jz      short loc_14065CE2B
0x14065ce1f  lea     rcx, DifRebootlessRundown; RunRef
0x14065ce26  call    ExReleaseRundownProtection_0
0x14065ce2b  mov     rax, [rbp+arg_20]
0x14065ce2f  mov     r9, r15; Uow
0x14065ce32  mov     rcx, [rbp+TransactionHandle]; TransactionHandle
0x14065ce36  mov     r8, r12; ObjectAttributes
0x14065ce39  mov     edx, r13d; DesiredAccess
0x14065ce3c  mov     [rsp+78h+TmHandle], rax; TmHandle
0x14065ce41  call    cs:__imp_NtOpenTransaction
0x14065ce48  nop     dword ptr [rax+rax+00h]
0x14065ce4d  mov     dword ptr [rbp+var_18], eax
0x14065ce50  test    r14, r14
0x14065ce53  jz      short loc_14065CEB8
0x14065ce55  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065ce5c  jnz     short loc_14065CE6D
0x14065ce5e  xor     dil, dil
0x14065ce61  test    cs:VfOptionFlags, 800h
0x14065ce6b  jz      short loc_14065CE80
0x14065ce6d  lea     rcx, DifRebootlessRundown; RunRef
0x14065ce74  call    ExAcquireRundownProtection_0
0x14065ce79  mov     dil, al
0x14065ce7c  test    al, al
0x14065ce7e  jz      short loc_14065CEB8
0x14065ce80  lea     rsi, [r14+30h]
0x14065ce84  mov     rbx, [rsi]
0x14065ce87  jmp     short loc_14065CEA2
0x14065ce89  lea     rax, [rbx-10h]
0x14065ce8d  test    rax, rax
0x14065ce90  jz      short loc_14065CE9F
0x14065ce92  mov     rax, [rax+8]
0x14065ce96  lea     rcx, [rbp+var_48]
0x14065ce9a  call    _guard_dispatch_icall_no_overrides
0x14065ce9f  mov     rbx, [rbx]
0x14065cea2  cmp     rbx, rsi
0x14065cea5  jnz     short loc_14065CE89
0x14065cea7  test    dil, dil
0x14065ceaa  jz      short loc_14065CEB8
0x14065ceac  lea     rcx, DifRebootlessRundown; RunRef
0x14065ceb3  call    ExReleaseRundownProtection_0
0x14065ceb8  mov     eax, dword ptr [rbp+var_18]
0x14065cebb  add     rsp, 78h
0x14065cebf  pop     r15
0x14065cec1  pop     r14
0x14065cec3  pop     r13
0x14065cec5  pop     r12
0x14065cec7  pop     rdi
0x14065cec8  pop     rsi
0x14065cec9  pop     rbx
0x14065ceca  pop     rbp
0x14065cecb  retn
```
