# DifNtReadOnlyEnlistmentWrapper

- ea: `0x14065fa40`
- end: `0x14065fb96`
- name: `DifNtReadOnlyEnlistmentWrapper`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x14065fa40`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtReadOnlyEnlistment` at `0x14065fb0b`
- `ext-ms-win-ntos-tm-l1-1-0!NtReadOnlyEnlistment` at `0x14065fb0b`

## pseudocode

```c
__int64 __fastcall DifNtReadOnlyEnlistmentWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  __int64 v15; // r9
  BOOLEAN v16; // di
  _QWORD **v17; // rsi
  _QWORD *j; // rbx
  __int128 v20; // [rsp+20h] [rbp-58h] BYREF
  __int128 v21; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v20 = 0;
  v21 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(550);
  v9 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v10 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v10 & 0x18) != 0 )
    {
      *(_QWORD *)&v20 = retaddr;
    }
    else if ( (v10 & 4) != 0 )
    {
      *(_QWORD *)&v20 = DifGetReturnAddressForWrappers(v6, v5, v7, v8);
    }
    *(_QWORD *)&v21 = EnlistmentHandle;
    *((_QWORD *)&v20 + 1) = TmVirtualClock;
    if ( !VfDifRunningWithoutReboot && (v11 = 0, (VfOptionFlags & 0x800) == 0)
      || (v11 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v9 + 32); i != (_QWORD *)(v9 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v20, v5, v7, v8);
      }
      if ( v11 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  DWORD2(v21) = NtReadOnlyEnlistment(EnlistmentHandle, TmVirtualClock);
  if ( v9 )
  {
    if ( !VfDifRunningWithoutReboot && (v16 = 0, (VfOptionFlags & 0x800) == 0)
      || (v16 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      v17 = (_QWORD **)(v9 + 48);
      for ( j = *v17; j != v17; j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v20, v13, v14, v15);
      }
      if ( v16 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return DWORD2(v21);
}

```

## disassembly

```asm
0x14065fa40  push    rbx
0x14065fa42  push    rbp
0x14065fa43  push    rsi
0x14065fa44  push    rdi
0x14065fa45  push    r14
0x14065fa47  push    r15
0x14065fa49  sub     rsp, 48h
0x14065fa4d  xorps   xmm0, xmm0
0x14065fa50  mov     r15, rcx
0x14065fa53  mov     ecx, 226h
0x14065fa58  mov     r14, rdx
0x14065fa5b  movups  [rsp+78h+var_58], xmm0
0x14065fa60  movups  [rsp+78h+var_48], xmm0
0x14065fa65  call    DifGetAPIThunkContextById
0x14065fa6a  mov     rsi, rax
0x14065fa6d  test    rax, rax
0x14065fa70  jz      loc_14065FB05
0x14065fa76  mov     eax, [rax+0Ch]
0x14065fa79  test    al, 18h
0x14065fa7b  jz      short loc_14065FA89
0x14065fa7d  mov     rcx, [rsp+78h]
0x14065fa82  mov     qword ptr [rsp+78h+var_58], rcx
0x14065fa87  jmp     short loc_14065FA97
0x14065fa89  test    al, 4
0x14065fa8b  jz      short loc_14065FA97
0x14065fa8d  call    DifGetReturnAddressForWrappers
0x14065fa92  mov     qword ptr [rsp+78h+var_58], rax
0x14065fa97  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065fa9e  mov     qword ptr [rsp+78h+var_48], r15
0x14065faa3  mov     qword ptr [rsp+78h+var_58+8], r14
0x14065faa8  jnz     short loc_14065FAB9
0x14065faaa  xor     bpl, bpl
0x14065faad  test    cs:VfOptionFlags, 800h
0x14065fab7  jz      short loc_14065FACC
0x14065fab9  lea     rcx, DifRebootlessRundown; RunRef
0x14065fac0  call    ExAcquireRundownProtection_0
0x14065fac5  mov     bpl, al
0x14065fac8  test    al, al
0x14065faca  jz      short loc_14065FB05
0x14065facc  lea     rdi, [rsi+20h]
0x14065fad0  mov     rbx, [rdi]
0x14065fad3  jmp     short loc_14065FAEF
0x14065fad5  lea     rax, [rbx-10h]
0x14065fad9  test    rax, rax
0x14065fadc  jz      short loc_14065FAEC
0x14065fade  mov     rax, [rax+8]
0x14065fae2  lea     rcx, [rsp+78h+var_58]
0x14065fae7  call    _guard_dispatch_icall_no_overrides
0x14065faec  mov     rbx, [rbx]
0x14065faef  cmp     rbx, rdi
0x14065faf2  jnz     short loc_14065FAD5
0x14065faf4  test    bpl, bpl
0x14065faf7  jz      short loc_14065FB05
0x14065faf9  lea     rcx, DifRebootlessRundown; RunRef
0x14065fb00  call    ExReleaseRundownProtection_0
0x14065fb05  mov     rdx, r14; TmVirtualClock
0x14065fb08  mov     rcx, r15; EnlistmentHandle
0x14065fb0b  call    cs:__imp_NtReadOnlyEnlistment
0x14065fb12  nop     dword ptr [rax+rax+00h]
0x14065fb17  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065fb1b  test    rsi, rsi
0x14065fb1e  jz      short loc_14065FB84
0x14065fb20  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065fb27  jnz     short loc_14065FB38
0x14065fb29  xor     dil, dil
0x14065fb2c  test    cs:VfOptionFlags, 800h
0x14065fb36  jz      short loc_14065FB4B
0x14065fb38  lea     rcx, DifRebootlessRundown; RunRef
0x14065fb3f  call    ExAcquireRundownProtection_0
0x14065fb44  mov     dil, al
0x14065fb47  test    al, al
0x14065fb49  jz      short loc_14065FB84
0x14065fb4b  add     rsi, 30h ; '0'
0x14065fb4f  mov     rbx, [rsi]
0x14065fb52  jmp     short loc_14065FB6E
0x14065fb54  lea     rax, [rbx-10h]
0x14065fb58  test    rax, rax
0x14065fb5b  jz      short loc_14065FB6B
0x14065fb5d  mov     rax, [rax+8]
0x14065fb61  lea     rcx, [rsp+78h+var_58]
0x14065fb66  call    _guard_dispatch_icall_no_overrides
0x14065fb6b  mov     rbx, [rbx]
0x14065fb6e  cmp     rbx, rsi
0x14065fb71  jnz     short loc_14065FB54
0x14065fb73  test    dil, dil
0x14065fb76  jz      short loc_14065FB84
0x14065fb78  lea     rcx, DifRebootlessRundown; RunRef
0x14065fb7f  call    ExReleaseRundownProtection_0
0x14065fb84  mov     eax, dword ptr [rsp+78h+var_48+8]
0x14065fb88  add     rsp, 48h
0x14065fb8c  pop     r15
0x14065fb8e  pop     r14
0x14065fb90  pop     rdi
0x14065fb91  pop     rsi
0x14065fb92  pop     rbp
0x14065fb93  pop     rbx
0x14065fb94  retn
```
