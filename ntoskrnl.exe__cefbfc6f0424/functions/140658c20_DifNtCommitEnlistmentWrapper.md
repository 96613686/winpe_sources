# DifNtCommitEnlistmentWrapper

- ea: `0x140658c20`
- end: `0x140658d76`
- name: `DifNtCommitEnlistmentWrapper`
- size: `342`
- prototype: `__int64 __fastcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x140658c20`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitEnlistment` at `0x140658ceb`
- `ext-ms-win-ntos-tm-l1-1-0!NtCommitEnlistment` at `0x140658ceb`

## pseudocode

```c
__int64 __fastcall DifNtCommitEnlistmentWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  APIThunkContextById = DifGetAPIThunkContextById(545);
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
  DWORD2(v21) = NtCommitEnlistment(EnlistmentHandle, TmVirtualClock);
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
0x140658c20  push    rbx
0x140658c22  push    rbp
0x140658c23  push    rsi
0x140658c24  push    rdi
0x140658c25  push    r14
0x140658c27  push    r15
0x140658c29  sub     rsp, 48h
0x140658c2d  xorps   xmm0, xmm0
0x140658c30  mov     r15, rcx
0x140658c33  mov     ecx, 221h
0x140658c38  mov     r14, rdx
0x140658c3b  movups  [rsp+78h+var_58], xmm0
0x140658c40  movups  [rsp+78h+var_48], xmm0
0x140658c45  call    DifGetAPIThunkContextById
0x140658c4a  mov     rsi, rax
0x140658c4d  test    rax, rax
0x140658c50  jz      loc_140658CE5
0x140658c56  mov     eax, [rax+0Ch]
0x140658c59  test    al, 18h
0x140658c5b  jz      short loc_140658C69
0x140658c5d  mov     rcx, [rsp+78h]
0x140658c62  mov     qword ptr [rsp+78h+var_58], rcx
0x140658c67  jmp     short loc_140658C77
0x140658c69  test    al, 4
0x140658c6b  jz      short loc_140658C77
0x140658c6d  call    DifGetReturnAddressForWrappers
0x140658c72  mov     qword ptr [rsp+78h+var_58], rax
0x140658c77  cmp     cs:VfDifRunningWithoutReboot, 0
0x140658c7e  mov     qword ptr [rsp+78h+var_48], r15
0x140658c83  mov     qword ptr [rsp+78h+var_58+8], r14
0x140658c88  jnz     short loc_140658C99
0x140658c8a  xor     bpl, bpl
0x140658c8d  test    cs:VfOptionFlags, 800h
0x140658c97  jz      short loc_140658CAC
0x140658c99  lea     rcx, DifRebootlessRundown; RunRef
0x140658ca0  call    ExAcquireRundownProtection_0
0x140658ca5  mov     bpl, al
0x140658ca8  test    al, al
0x140658caa  jz      short loc_140658CE5
0x140658cac  lea     rdi, [rsi+20h]
0x140658cb0  mov     rbx, [rdi]
0x140658cb3  jmp     short loc_140658CCF
0x140658cb5  lea     rax, [rbx-10h]
0x140658cb9  test    rax, rax
0x140658cbc  jz      short loc_140658CCC
0x140658cbe  mov     rax, [rax+8]
0x140658cc2  lea     rcx, [rsp+78h+var_58]
0x140658cc7  call    _guard_dispatch_icall_no_overrides
0x140658ccc  mov     rbx, [rbx]
0x140658ccf  cmp     rbx, rdi
0x140658cd2  jnz     short loc_140658CB5
0x140658cd4  test    bpl, bpl
0x140658cd7  jz      short loc_140658CE5
0x140658cd9  lea     rcx, DifRebootlessRundown; RunRef
0x140658ce0  call    ExReleaseRundownProtection_0
0x140658ce5  mov     rdx, r14; TmVirtualClock
0x140658ce8  mov     rcx, r15; EnlistmentHandle
0x140658ceb  call    cs:__imp_NtCommitEnlistment
0x140658cf2  nop     dword ptr [rax+rax+00h]
0x140658cf7  mov     dword ptr [rsp+78h+var_48+8], eax
0x140658cfb  test    rsi, rsi
0x140658cfe  jz      short loc_140658D64
0x140658d00  cmp     cs:VfDifRunningWithoutReboot, 0
0x140658d07  jnz     short loc_140658D18
0x140658d09  xor     dil, dil
0x140658d0c  test    cs:VfOptionFlags, 800h
0x140658d16  jz      short loc_140658D2B
0x140658d18  lea     rcx, DifRebootlessRundown; RunRef
0x140658d1f  call    ExAcquireRundownProtection_0
0x140658d24  mov     dil, al
0x140658d27  test    al, al
0x140658d29  jz      short loc_140658D64
0x140658d2b  add     rsi, 30h ; '0'
0x140658d2f  mov     rbx, [rsi]
0x140658d32  jmp     short loc_140658D4E
0x140658d34  lea     rax, [rbx-10h]
0x140658d38  test    rax, rax
0x140658d3b  jz      short loc_140658D4B
0x140658d3d  mov     rax, [rax+8]
0x140658d41  lea     rcx, [rsp+78h+var_58]
0x140658d46  call    _guard_dispatch_icall_no_overrides
0x140658d4b  mov     rbx, [rbx]
0x140658d4e  cmp     rbx, rsi
0x140658d51  jnz     short loc_140658D34
0x140658d53  test    dil, dil
0x140658d56  jz      short loc_140658D64
0x140658d58  lea     rcx, DifRebootlessRundown; RunRef
0x140658d5f  call    ExReleaseRundownProtection_0
0x140658d64  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140658d68  add     rsp, 48h
0x140658d6c  pop     r15
0x140658d6e  pop     r14
0x140658d70  pop     rdi
0x140658d71  pop     rsi
0x140658d72  pop     rbp
0x140658d73  pop     rbx
0x140658d74  retn
```
