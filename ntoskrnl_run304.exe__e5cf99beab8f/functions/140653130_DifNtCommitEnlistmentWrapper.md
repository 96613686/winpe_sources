# DifNtCommitEnlistmentWrapper

- ea: `0x140653130`
- end: `0x140653286`
- name: `DifNtCommitEnlistmentWrapper`
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
- `0x140653130`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitEnlistment` at `0x1406531fb`
- `ext-ms-win-ntos-tm-l1-1-0!NtCommitEnlistment` at `0x1406531fb`

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
  BOOLEAN v15; // di
  _QWORD **v16; // rsi
  _QWORD *j; // rbx
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v19 = 0;
  v20 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(545);
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
  DWORD2(v20) = NtCommitEnlistment(EnlistmentHandle, TmVirtualClock);
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
0x140653130  push    rbx
0x140653132  push    rbp
0x140653133  push    rsi
0x140653134  push    rdi
0x140653135  push    r14
0x140653137  push    r15
0x140653139  sub     rsp, 48h
0x14065313d  xorps   xmm0, xmm0
0x140653140  mov     r15, rcx
0x140653143  mov     ecx, 221h
0x140653148  mov     r14, rdx
0x14065314b  movups  [rsp+78h+var_58], xmm0
0x140653150  movups  [rsp+78h+var_48], xmm0
0x140653155  call    DifGetAPIThunkContextById
0x14065315a  mov     rsi, rax
0x14065315d  test    rax, rax
0x140653160  jz      loc_1406531F5
0x140653166  mov     eax, [rax+0Ch]
0x140653169  test    al, 18h
0x14065316b  jz      short loc_140653179
0x14065316d  mov     rcx, [rsp+78h]
0x140653172  mov     qword ptr [rsp+78h+var_58], rcx
0x140653177  jmp     short loc_140653187
0x140653179  test    al, 4
0x14065317b  jz      short loc_140653187
0x14065317d  call    DifGetReturnAddressForWrappers
0x140653182  mov     qword ptr [rsp+78h+var_58], rax
0x140653187  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065318e  mov     qword ptr [rsp+78h+var_48], r15
0x140653193  mov     qword ptr [rsp+78h+var_58+8], r14
0x140653198  jnz     short loc_1406531A9
0x14065319a  xor     bpl, bpl
0x14065319d  test    cs:VfOptionFlags, 800h
0x1406531a7  jz      short loc_1406531BC
0x1406531a9  lea     rcx, DifRebootlessRundown; RunRef
0x1406531b0  call    ExAcquireRundownProtection_0
0x1406531b5  mov     bpl, al
0x1406531b8  test    al, al
0x1406531ba  jz      short loc_1406531F5
0x1406531bc  lea     rdi, [rsi+20h]
0x1406531c0  mov     rbx, [rdi]
0x1406531c3  jmp     short loc_1406531DF
0x1406531c5  lea     rax, [rbx-10h]
0x1406531c9  test    rax, rax
0x1406531cc  jz      short loc_1406531DC
0x1406531ce  mov     rax, [rax+8]
0x1406531d2  lea     rcx, [rsp+78h+var_58]
0x1406531d7  call    _guard_dispatch_icall_no_overrides
0x1406531dc  mov     rbx, [rbx]
0x1406531df  cmp     rbx, rdi
0x1406531e2  jnz     short loc_1406531C5
0x1406531e4  test    bpl, bpl
0x1406531e7  jz      short loc_1406531F5
0x1406531e9  lea     rcx, DifRebootlessRundown; RunRef
0x1406531f0  call    ExReleaseRundownProtection_0
0x1406531f5  mov     rdx, r14; TmVirtualClock
0x1406531f8  mov     rcx, r15; EnlistmentHandle
0x1406531fb  call    cs:__imp_NtCommitEnlistment
0x140653202  nop     dword ptr [rax+rax+00h]
0x140653207  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065320b  test    rsi, rsi
0x14065320e  jz      short loc_140653274
0x140653210  cmp     cs:VfDifRunningWithoutReboot, 0
0x140653217  jnz     short loc_140653228
0x140653219  xor     dil, dil
0x14065321c  test    cs:VfOptionFlags, 800h
0x140653226  jz      short loc_14065323B
0x140653228  lea     rcx, DifRebootlessRundown; RunRef
0x14065322f  call    ExAcquireRundownProtection_0
0x140653234  mov     dil, al
0x140653237  test    al, al
0x140653239  jz      short loc_140653274
0x14065323b  add     rsi, 30h ; '0'
0x14065323f  mov     rbx, [rsi]
0x140653242  jmp     short loc_14065325E
0x140653244  lea     rax, [rbx-10h]
0x140653248  test    rax, rax
0x14065324b  jz      short loc_14065325B
0x14065324d  mov     rax, [rax+8]
0x140653251  lea     rcx, [rsp+78h+var_58]
0x140653256  call    _guard_dispatch_icall_no_overrides
0x14065325b  mov     rbx, [rbx]
0x14065325e  cmp     rbx, rsi
0x140653261  jnz     short loc_140653244
0x140653263  test    dil, dil
0x140653266  jz      short loc_140653274
0x140653268  lea     rcx, DifRebootlessRundown; RunRef
0x14065326f  call    ExReleaseRundownProtection_0
0x140653274  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140653278  add     rsp, 48h
0x14065327c  pop     r15
0x14065327e  pop     r14
0x140653280  pop     rdi
0x140653281  pop     rsi
0x140653282  pop     rbp
0x140653283  pop     rbx
0x140653284  retn
```
