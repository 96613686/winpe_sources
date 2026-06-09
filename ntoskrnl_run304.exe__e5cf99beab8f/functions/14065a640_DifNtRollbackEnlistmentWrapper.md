# DifNtRollbackEnlistmentWrapper

- ea: `0x14065a640`
- end: `0x14065a796`
- name: `DifNtRollbackEnlistmentWrapper`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x14065a640`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackEnlistment` at `0x14065a70b`
- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackEnlistment` at `0x14065a70b`

## pseudocode

```c
__int64 __fastcall DifNtRollbackEnlistmentWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  __int64 APIThunkContextById; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rsi
  int v10; // eax
  BOOLEAN v11; // bp
  _QWORD *i; // rbx
  __int64 v13; // rdx
  __int64 v14; // r8
  BOOLEAN v15; // di
  _QWORD **v16; // rsi
  _QWORD *j; // rbx
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v19 = 0;
  v20 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(546);
  v9 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v10 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v10 & 0x18) != 0 )
    {
      *(_QWORD *)&v19 = retaddr;
    }
    else if ( (v10 & 4) != 0 )
    {
      *(_QWORD *)&v19 = DifGetReturnAddressForWrappers(v6, v5, v7, v8);
    }
    *(_QWORD *)&v20 = EnlistmentHandle;
    *((_QWORD *)&v19 + 1) = TmVirtualClock;
    if ( !VfDifRunningWithoutReboot && (v11 = 0, (VfOptionFlags & 0x800) == 0)
      || (v11 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v9 + 32); i != (_QWORD *)(v9 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v19, v5, v7);
      }
      if ( v11 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  DWORD2(v20) = NtRollbackEnlistment(EnlistmentHandle, TmVirtualClock);
  if ( v9 )
  {
    if ( !VfDifRunningWithoutReboot && (v15 = 0, (VfOptionFlags & 0x800) == 0)
      || (v15 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      v16 = (_QWORD **)(v9 + 48);
      for ( j = *v16; j != v16; j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v19, v13, v14);
      }
      if ( v15 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return DWORD2(v20);
}

```

## disassembly

```asm
0x14065a640  push    rbx
0x14065a642  push    rbp
0x14065a643  push    rsi
0x14065a644  push    rdi
0x14065a645  push    r14
0x14065a647  push    r15
0x14065a649  sub     rsp, 48h
0x14065a64d  xorps   xmm0, xmm0
0x14065a650  mov     r15, rcx
0x14065a653  mov     ecx, 222h
0x14065a658  mov     r14, rdx
0x14065a65b  movups  [rsp+78h+var_58], xmm0
0x14065a660  movups  [rsp+78h+var_48], xmm0
0x14065a665  call    DifGetAPIThunkContextById
0x14065a66a  mov     rsi, rax
0x14065a66d  test    rax, rax
0x14065a670  jz      loc_14065A705
0x14065a676  mov     eax, [rax+0Ch]
0x14065a679  test    al, 18h
0x14065a67b  jz      short loc_14065A689
0x14065a67d  mov     rcx, [rsp+78h]
0x14065a682  mov     qword ptr [rsp+78h+var_58], rcx
0x14065a687  jmp     short loc_14065A697
0x14065a689  test    al, 4
0x14065a68b  jz      short loc_14065A697
0x14065a68d  call    DifGetReturnAddressForWrappers
0x14065a692  mov     qword ptr [rsp+78h+var_58], rax
0x14065a697  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065a69e  mov     qword ptr [rsp+78h+var_48], r15
0x14065a6a3  mov     qword ptr [rsp+78h+var_58+8], r14
0x14065a6a8  jnz     short loc_14065A6B9
0x14065a6aa  xor     bpl, bpl
0x14065a6ad  test    cs:VfOptionFlags, 800h
0x14065a6b7  jz      short loc_14065A6CC
0x14065a6b9  lea     rcx, DifRebootlessRundown; RunRef
0x14065a6c0  call    ExAcquireRundownProtection_0
0x14065a6c5  mov     bpl, al
0x14065a6c8  test    al, al
0x14065a6ca  jz      short loc_14065A705
0x14065a6cc  lea     rdi, [rsi+20h]
0x14065a6d0  mov     rbx, [rdi]
0x14065a6d3  jmp     short loc_14065A6EF
0x14065a6d5  lea     rax, [rbx-10h]
0x14065a6d9  test    rax, rax
0x14065a6dc  jz      short loc_14065A6EC
0x14065a6de  mov     rax, [rax+8]
0x14065a6e2  lea     rcx, [rsp+78h+var_58]
0x14065a6e7  call    _guard_dispatch_icall_no_overrides
0x14065a6ec  mov     rbx, [rbx]
0x14065a6ef  cmp     rbx, rdi
0x14065a6f2  jnz     short loc_14065A6D5
0x14065a6f4  test    bpl, bpl
0x14065a6f7  jz      short loc_14065A705
0x14065a6f9  lea     rcx, DifRebootlessRundown; RunRef
0x14065a700  call    ExReleaseRundownProtection_0
0x14065a705  mov     rdx, r14; TmVirtualClock
0x14065a708  mov     rcx, r15; EnlistmentHandle
0x14065a70b  call    cs:__imp_NtRollbackEnlistment
0x14065a712  nop     dword ptr [rax+rax+00h]
0x14065a717  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065a71b  test    rsi, rsi
0x14065a71e  jz      short loc_14065A784
0x14065a720  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065a727  jnz     short loc_14065A738
0x14065a729  xor     dil, dil
0x14065a72c  test    cs:VfOptionFlags, 800h
0x14065a736  jz      short loc_14065A74B
0x14065a738  lea     rcx, DifRebootlessRundown; RunRef
0x14065a73f  call    ExAcquireRundownProtection_0
0x14065a744  mov     dil, al
0x14065a747  test    al, al
0x14065a749  jz      short loc_14065A784
0x14065a74b  add     rsi, 30h ; '0'
0x14065a74f  mov     rbx, [rsi]
0x14065a752  jmp     short loc_14065A76E
0x14065a754  lea     rax, [rbx-10h]
0x14065a758  test    rax, rax
0x14065a75b  jz      short loc_14065A76B
0x14065a75d  mov     rax, [rax+8]
0x14065a761  lea     rcx, [rsp+78h+var_58]
0x14065a766  call    _guard_dispatch_icall_no_overrides
0x14065a76b  mov     rbx, [rbx]
0x14065a76e  cmp     rbx, rsi
0x14065a771  jnz     short loc_14065A754
0x14065a773  test    dil, dil
0x14065a776  jz      short loc_14065A784
0x14065a778  lea     rcx, DifRebootlessRundown; RunRef
0x14065a77f  call    ExReleaseRundownProtection_0
0x14065a784  mov     eax, dword ptr [rsp+78h+var_48+8]
0x14065a788  add     rsp, 48h
0x14065a78c  pop     r15
0x14065a78e  pop     r14
0x14065a790  pop     rdi
0x14065a791  pop     rsi
0x14065a792  pop     rbp
0x14065a793  pop     rbx
0x14065a794  retn
```
