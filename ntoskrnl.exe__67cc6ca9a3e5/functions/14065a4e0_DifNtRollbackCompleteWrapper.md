# DifNtRollbackCompleteWrapper

- ea: `0x14065a4e0`
- end: `0x14065a636`
- name: `DifNtRollbackCompleteWrapper`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x14065a4e0`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackComplete` at `0x14065a5ab`
- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackComplete` at `0x14065a5ab`

## pseudocode

```c
__int64 __fastcall DifNtRollbackCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  __int128 *APIThunkContextById; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int128 *v9; // rsi
  int v10; // eax
  BOOLEAN v11; // bp
  __int128 *i; // rbx
  BOOLEAN v13; // di
  _QWORD **v14; // rsi
  _QWORD *j; // rbx
  __int128 v17; // [rsp+20h] [rbp-58h] BYREF
  __int128 v18; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v17 = 0;
  v18 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(551);
  v9 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v10 = *((_DWORD *)APIThunkContextById + 3);
    if ( (v10 & 0x18) != 0 )
    {
      *(_QWORD *)&v17 = retaddr;
    }
    else if ( (v10 & 4) != 0 )
    {
      *(_QWORD *)&v17 = DifGetReturnAddressForWrappers(v6, v5, v7, v8);
    }
    *(_QWORD *)&v18 = EnlistmentHandle;
    *((_QWORD *)&v17 + 1) = TmVirtualClock;
    if ( !VfDifRunningWithoutReboot && (v11 = 0, (VfOptionFlags & 0x800) == 0)
      || (v11 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = (__int128 *)*((_QWORD *)v9 + 4); i != v9 + 2; i = *(__int128 **)i )
      {
        if ( i != (__int128 *)16 )
          guard_dispatch_icall_no_overrides(&v17);
      }
      if ( v11 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  DWORD2(v18) = NtRollbackComplete(EnlistmentHandle, TmVirtualClock);
  if ( v9 )
  {
    if ( !VfDifRunningWithoutReboot && (v13 = 0, (VfOptionFlags & 0x800) == 0)
      || (v13 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      v14 = (_QWORD **)(v9 + 3);
      for ( j = *v14; j != v14; j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v17);
      }
      if ( v13 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return DWORD2(v18);
}

```

## disassembly

```asm
0x14065a4e0  push    rbx
0x14065a4e2  push    rbp
0x14065a4e3  push    rsi
0x14065a4e4  push    rdi
0x14065a4e5  push    r14
0x14065a4e7  push    r15
0x14065a4e9  sub     rsp, 48h
0x14065a4ed  xorps   xmm0, xmm0
0x14065a4f0  mov     r15, rcx
0x14065a4f3  mov     ecx, 227h
0x14065a4f8  mov     r14, rdx
0x14065a4fb  movups  [rsp+78h+var_58], xmm0
0x14065a500  movups  [rsp+78h+var_48], xmm0
0x14065a505  call    DifGetAPIThunkContextById
0x14065a50a  mov     rsi, rax
0x14065a50d  test    rax, rax
0x14065a510  jz      loc_14065A5A5
0x14065a516  mov     eax, [rax+0Ch]
0x14065a519  test    al, 18h
0x14065a51b  jz      short loc_14065A529
0x14065a51d  mov     rcx, [rsp+78h]
0x14065a522  mov     qword ptr [rsp+78h+var_58], rcx
0x14065a527  jmp     short loc_14065A537
0x14065a529  test    al, 4
0x14065a52b  jz      short loc_14065A537
0x14065a52d  call    DifGetReturnAddressForWrappers
0x14065a532  mov     qword ptr [rsp+78h+var_58], rax
0x14065a537  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065a53e  mov     qword ptr [rsp+78h+var_48], r15
0x14065a543  mov     qword ptr [rsp+78h+var_58+8], r14
0x14065a548  jnz     short loc_14065A559
0x14065a54a  xor     bpl, bpl
0x14065a54d  test    cs:VfOptionFlags, 800h
0x14065a557  jz      short loc_14065A56C
0x14065a559  lea     rcx, DifRebootlessRundown; RunRef
0x14065a560  call    ExAcquireRundownProtection_0
0x14065a565  mov     bpl, al
0x14065a568  test    al, al
0x14065a56a  jz      short loc_14065A5A5
0x14065a56c  lea     rdi, [rsi+20h]
0x14065a570  mov     rbx, [rdi]
0x14065a573  jmp     short loc_14065A58F
0x14065a575  lea     rax, [rbx-10h]
0x14065a579  test    rax, rax
0x14065a57c  jz      short loc_14065A58C
0x14065a57e  mov     rax, [rax+8]
0x14065a582  lea     rcx, [rsp+78h+var_58]
0x14065a587  call    _guard_dispatch_icall_no_overrides
0x14065a58c  mov     rbx, [rbx]
0x14065a58f  cmp     rbx, rdi
0x14065a592  jnz     short loc_14065A575
0x14065a594  test    bpl, bpl
0x14065a597  jz      short loc_14065A5A5
0x14065a599  lea     rcx, DifRebootlessRundown; RunRef
0x14065a5a0  call    ExReleaseRundownProtection_0
0x14065a5a5  mov     rdx, r14; TmVirtualClock
0x14065a5a8  mov     rcx, r15; EnlistmentHandle
0x14065a5ab  call    cs:__imp_NtRollbackComplete
0x14065a5b2  nop     dword ptr [rax+rax+00h]
0x14065a5b7  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065a5bb  test    rsi, rsi
0x14065a5be  jz      short loc_14065A624
0x14065a5c0  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065a5c7  jnz     short loc_14065A5D8
0x14065a5c9  xor     dil, dil
0x14065a5cc  test    cs:VfOptionFlags, 800h
0x14065a5d6  jz      short loc_14065A5EB
0x14065a5d8  lea     rcx, DifRebootlessRundown; RunRef
0x14065a5df  call    ExAcquireRundownProtection_0
0x14065a5e4  mov     dil, al
0x14065a5e7  test    al, al
0x14065a5e9  jz      short loc_14065A624
0x14065a5eb  add     rsi, 30h ; '0'
0x14065a5ef  mov     rbx, [rsi]
0x14065a5f2  jmp     short loc_14065A60E
0x14065a5f4  lea     rax, [rbx-10h]
0x14065a5f8  test    rax, rax
0x14065a5fb  jz      short loc_14065A60B
0x14065a5fd  mov     rax, [rax+8]
0x14065a601  lea     rcx, [rsp+78h+var_58]
0x14065a606  call    _guard_dispatch_icall_no_overrides
0x14065a60b  mov     rbx, [rbx]
0x14065a60e  cmp     rbx, rsi
0x14065a611  jnz     short loc_14065A5F4
0x14065a613  test    dil, dil
0x14065a616  jz      short loc_14065A624
0x14065a618  lea     rcx, DifRebootlessRundown; RunRef
0x14065a61f  call    ExReleaseRundownProtection_0
0x14065a624  mov     eax, dword ptr [rsp+78h+var_48+8]
0x14065a628  add     rsp, 48h
0x14065a62c  pop     r15
0x14065a62e  pop     r14
0x14065a630  pop     rdi
0x14065a631  pop     rsi
0x14065a632  pop     rbp
0x14065a633  pop     rbx
0x14065a634  retn
```
