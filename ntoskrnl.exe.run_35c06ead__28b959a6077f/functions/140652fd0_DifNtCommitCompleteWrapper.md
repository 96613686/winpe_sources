# DifNtCommitCompleteWrapper

- ea: `0x140652fd0`
- end: `0x140653126`
- name: `DifNtCommitCompleteWrapper`
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
- `0x140652fd0`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitComplete` at `0x14065309b`
- `ext-ms-win-ntos-tm-l1-1-0!NtCommitComplete` at `0x14065309b`

## pseudocode

```c
__int64 __fastcall DifNtCommitCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  APIThunkContextById = DifGetAPIThunkContextById(549);
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
  DWORD2(v21) = NtCommitComplete(EnlistmentHandle, TmVirtualClock);
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
0x140652fd0  push    rbx
0x140652fd2  push    rbp
0x140652fd3  push    rsi
0x140652fd4  push    rdi
0x140652fd5  push    r14
0x140652fd7  push    r15
0x140652fd9  sub     rsp, 48h
0x140652fdd  xorps   xmm0, xmm0
0x140652fe0  mov     r15, rcx
0x140652fe3  mov     ecx, 225h
0x140652fe8  mov     r14, rdx
0x140652feb  movups  [rsp+78h+var_58], xmm0
0x140652ff0  movups  [rsp+78h+var_48], xmm0
0x140652ff5  call    DifGetAPIThunkContextById
0x140652ffa  mov     rsi, rax
0x140652ffd  test    rax, rax
0x140653000  jz      loc_140653095
0x140653006  mov     eax, [rax+0Ch]
0x140653009  test    al, 18h
0x14065300b  jz      short loc_140653019
0x14065300d  mov     rcx, [rsp+78h]
0x140653012  mov     qword ptr [rsp+78h+var_58], rcx
0x140653017  jmp     short loc_140653027
0x140653019  test    al, 4
0x14065301b  jz      short loc_140653027
0x14065301d  call    DifGetReturnAddressForWrappers
0x140653022  mov     qword ptr [rsp+78h+var_58], rax
0x140653027  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065302e  mov     qword ptr [rsp+78h+var_48], r15
0x140653033  mov     qword ptr [rsp+78h+var_58+8], r14
0x140653038  jnz     short loc_140653049
0x14065303a  xor     bpl, bpl
0x14065303d  test    cs:VfOptionFlags, 800h
0x140653047  jz      short loc_14065305C
0x140653049  lea     rcx, DifRebootlessRundown; RunRef
0x140653050  call    ExAcquireRundownProtection_0
0x140653055  mov     bpl, al
0x140653058  test    al, al
0x14065305a  jz      short loc_140653095
0x14065305c  lea     rdi, [rsi+20h]
0x140653060  mov     rbx, [rdi]
0x140653063  jmp     short loc_14065307F
0x140653065  lea     rax, [rbx-10h]
0x140653069  test    rax, rax
0x14065306c  jz      short loc_14065307C
0x14065306e  mov     rax, [rax+8]
0x140653072  lea     rcx, [rsp+78h+var_58]
0x140653077  call    _guard_dispatch_icall_no_overrides
0x14065307c  mov     rbx, [rbx]
0x14065307f  cmp     rbx, rdi
0x140653082  jnz     short loc_140653065
0x140653084  test    bpl, bpl
0x140653087  jz      short loc_140653095
0x140653089  lea     rcx, DifRebootlessRundown; RunRef
0x140653090  call    ExReleaseRundownProtection_0
0x140653095  mov     rdx, r14; TmVirtualClock
0x140653098  mov     rcx, r15; EnlistmentHandle
0x14065309b  call    cs:__imp_NtCommitComplete
0x1406530a2  nop     dword ptr [rax+rax+00h]
0x1406530a7  mov     dword ptr [rsp+78h+var_48+8], eax
0x1406530ab  test    rsi, rsi
0x1406530ae  jz      short loc_140653114
0x1406530b0  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406530b7  jnz     short loc_1406530C8
0x1406530b9  xor     dil, dil
0x1406530bc  test    cs:VfOptionFlags, 800h
0x1406530c6  jz      short loc_1406530DB
0x1406530c8  lea     rcx, DifRebootlessRundown; RunRef
0x1406530cf  call    ExAcquireRundownProtection_0
0x1406530d4  mov     dil, al
0x1406530d7  test    al, al
0x1406530d9  jz      short loc_140653114
0x1406530db  add     rsi, 30h ; '0'
0x1406530df  mov     rbx, [rsi]
0x1406530e2  jmp     short loc_1406530FE
0x1406530e4  lea     rax, [rbx-10h]
0x1406530e8  test    rax, rax
0x1406530eb  jz      short loc_1406530FB
0x1406530ed  mov     rax, [rax+8]
0x1406530f1  lea     rcx, [rsp+78h+var_58]
0x1406530f6  call    _guard_dispatch_icall_no_overrides
0x1406530fb  mov     rbx, [rbx]
0x1406530fe  cmp     rbx, rsi
0x140653101  jnz     short loc_1406530E4
0x140653103  test    dil, dil
0x140653106  jz      short loc_140653114
0x140653108  lea     rcx, DifRebootlessRundown; RunRef
0x14065310f  call    ExReleaseRundownProtection_0
0x140653114  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140653118  add     rsp, 48h
0x14065311c  pop     r15
0x14065311e  pop     r14
0x140653120  pop     rdi
0x140653121  pop     rsi
0x140653122  pop     rbp
0x140653123  pop     rbx
0x140653124  retn
```
