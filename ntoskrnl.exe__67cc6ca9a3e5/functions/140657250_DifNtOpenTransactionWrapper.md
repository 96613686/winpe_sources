# DifNtOpenTransactionWrapper

- ea: `0x140657250`
- end: `0x1406573dd`
- name: `DifNtOpenTransactionWrapper`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x140657250`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransaction` at `0x140657351`
- `ext-ms-win-ntos-tm-l1-1-0!NtOpenTransaction` at `0x140657351`

## pseudocode

```c
__int64 __fastcall DifNtOpenTransactionWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        OBJECT_ATTRIBUTES *a3,
        GUID *a4,
        HANDLE TmHandle)
{
  __int128 *APIThunkContextById; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int128 *v12; // r14
  __int64 v13; // rcx
  BOOLEAN v14; // si
  __int128 *i; // rbx
  BOOLEAN v16; // di
  __int128 *j; // rbx
  __int128 v19; // [rsp+30h] [rbp-48h] BYREF
  __int128 v20; // [rsp+40h] [rbp-38h]
  __int128 v21; // [rsp+50h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v22 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(535);
  v12 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v13 = *((unsigned int *)APIThunkContextById + 3);
    if ( (v13 & 0x18) != 0 )
    {
      *(_QWORD *)&v19 = retaddr;
    }
    else if ( (v13 & 4) != 0 )
    {
      *(_QWORD *)&v19 = DifGetReturnAddressForWrappers(v13, v9, v10, v11);
    }
    *((_QWORD *)&v21 + 1) = a1;
    *((_QWORD *)&v19 + 1) = TmHandle;
    LODWORD(v21) = a2;
    *((_QWORD *)&v20 + 1) = a3;
    *(_QWORD *)&v20 = a4;
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = (__int128 *)*((_QWORD *)v12 + 4); i != v12 + 2; i = *(__int128 **)i )
      {
        if ( i != (__int128 *)16 )
          guard_dispatch_icall_no_overrides(&v19);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v22) = NtOpenTransaction(a1, a2, a3, a4, TmHandle);
  if ( v12 )
  {
    if ( !VfDifRunningWithoutReboot && (v16 = 0, (VfOptionFlags & 0x800) == 0)
      || (v16 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = (__int128 *)*((_QWORD *)v12 + 6); j != v12 + 3; j = *(__int128 **)j )
      {
        if ( j != (__int128 *)16 )
          guard_dispatch_icall_no_overrides(&v19);
      }
      if ( v16 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140657250  mov     [rsp-40h+TransactionHandle], rcx
0x140657255  push    rbp
0x140657256  push    rbx
0x140657257  push    rsi
0x140657258  push    rdi
0x140657259  push    r12
0x14065725b  push    r13
0x14065725d  push    r14
0x14065725f  push    r15
0x140657261  mov     rbp, rsp
0x140657264  sub     rsp, 78h
0x140657268  xorps   xmm0, xmm0
0x14065726b  xor     eax, eax
0x14065726d  mov     ecx, 217h
0x140657272  mov     [rbp+var_18], rax
0x140657276  movups  [rbp+var_48], xmm0
0x14065727a  mov     r15, r9
0x14065727d  mov     r12, r8
0x140657280  movups  [rbp+var_38], xmm0
0x140657284  mov     r13d, edx
0x140657287  movups  [rbp+var_28], xmm0
0x14065728b  call    DifGetAPIThunkContextById
0x140657290  mov     r14, rax
0x140657293  test    rax, rax
0x140657296  jz      loc_14065733B
0x14065729c  mov     ecx, [rax+0Ch]
0x14065729f  test    cl, 18h
0x1406572a2  jz      short loc_1406572AE
0x1406572a4  mov     rcx, [rbp+40h]
0x1406572a8  mov     qword ptr [rbp+var_48], rcx
0x1406572ac  jmp     short loc_1406572BC
0x1406572ae  test    cl, 4
0x1406572b1  jz      short loc_1406572BC
0x1406572b3  call    DifGetReturnAddressForWrappers
0x1406572b8  mov     qword ptr [rbp+var_48], rax
0x1406572bc  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406572c3  mov     rax, [rbp+TransactionHandle]
0x1406572c7  mov     qword ptr [rbp+var_28+8], rax
0x1406572cb  mov     rax, [rbp+arg_20]
0x1406572cf  mov     qword ptr [rbp+var_48+8], rax
0x1406572d3  mov     dword ptr [rbp+var_28], r13d
0x1406572d7  mov     qword ptr [rbp+var_38+8], r12
0x1406572db  mov     qword ptr [rbp+var_38], r15
0x1406572df  jnz     short loc_1406572F0
0x1406572e1  xor     sil, sil
0x1406572e4  test    cs:VfOptionFlags, 800h
0x1406572ee  jz      short loc_140657303
0x1406572f0  lea     rcx, DifRebootlessRundown; RunRef
0x1406572f7  call    ExAcquireRundownProtection_0
0x1406572fc  mov     sil, al
0x1406572ff  test    al, al
0x140657301  jz      short loc_14065733B
0x140657303  lea     rdi, [r14+20h]
0x140657307  mov     rbx, [rdi]
0x14065730a  jmp     short loc_140657325
0x14065730c  lea     rax, [rbx-10h]
0x140657310  test    rax, rax
0x140657313  jz      short loc_140657322
0x140657315  mov     rax, [rax+8]
0x140657319  lea     rcx, [rbp+var_48]
0x14065731d  call    _guard_dispatch_icall_no_overrides
0x140657322  mov     rbx, [rbx]
0x140657325  cmp     rbx, rdi
0x140657328  jnz     short loc_14065730C
0x14065732a  test    sil, sil
0x14065732d  jz      short loc_14065733B
0x14065732f  lea     rcx, DifRebootlessRundown; RunRef
0x140657336  call    ExReleaseRundownProtection_0
0x14065733b  mov     rax, [rbp+arg_20]
0x14065733f  mov     r9, r15; Uow
0x140657342  mov     rcx, [rbp+TransactionHandle]; TransactionHandle
0x140657346  mov     r8, r12; ObjectAttributes
0x140657349  mov     edx, r13d; DesiredAccess
0x14065734c  mov     [rsp+78h+TmHandle], rax; TmHandle
0x140657351  call    cs:__imp_NtOpenTransaction
0x140657358  nop     dword ptr [rax+rax+00h]
0x14065735d  mov     dword ptr [rbp+var_18], eax
0x140657360  test    r14, r14
0x140657363  jz      short loc_1406573C8
0x140657365  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065736c  jnz     short loc_14065737D
0x14065736e  xor     dil, dil
0x140657371  test    cs:VfOptionFlags, 800h
0x14065737b  jz      short loc_140657390
0x14065737d  lea     rcx, DifRebootlessRundown; RunRef
0x140657384  call    ExAcquireRundownProtection_0
0x140657389  mov     dil, al
0x14065738c  test    al, al
0x14065738e  jz      short loc_1406573C8
0x140657390  lea     rsi, [r14+30h]
0x140657394  mov     rbx, [rsi]
0x140657397  jmp     short loc_1406573B2
0x140657399  lea     rax, [rbx-10h]
0x14065739d  test    rax, rax
0x1406573a0  jz      short loc_1406573AF
0x1406573a2  mov     rax, [rax+8]
0x1406573a6  lea     rcx, [rbp+var_48]
0x1406573aa  call    _guard_dispatch_icall_no_overrides
0x1406573af  mov     rbx, [rbx]
0x1406573b2  cmp     rbx, rsi
0x1406573b5  jnz     short loc_140657399
0x1406573b7  test    dil, dil
0x1406573ba  jz      short loc_1406573C8
0x1406573bc  lea     rcx, DifRebootlessRundown; RunRef
0x1406573c3  call    ExReleaseRundownProtection_0
0x1406573c8  mov     eax, dword ptr [rbp+var_18]
0x1406573cb  add     rsp, 78h
0x1406573cf  pop     r15
0x1406573d1  pop     r14
0x1406573d3  pop     r13
0x1406573d5  pop     r12
0x1406573d7  pop     rdi
0x1406573d8  pop     rsi
0x1406573d9  pop     rbx
0x1406573da  pop     rbp
0x1406573db  retn
```
