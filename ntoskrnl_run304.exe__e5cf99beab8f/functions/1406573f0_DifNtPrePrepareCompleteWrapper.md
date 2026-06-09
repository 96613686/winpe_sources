# DifNtPrePrepareCompleteWrapper

- ea: `0x1406573f0`
- end: `0x140657546`
- name: `DifNtPrePrepareCompleteWrapper`
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
- `0x1406573f0`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPrePrepareComplete` at `0x1406574bb`
- `ext-ms-win-ntos-tm-l1-1-0!NtPrePrepareComplete` at `0x1406574bb`

## pseudocode

```c
__int64 __fastcall DifNtPrePrepareCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  APIThunkContextById = DifGetAPIThunkContextById(547);
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
  DWORD2(v20) = NtPrePrepareComplete(EnlistmentHandle, TmVirtualClock);
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
0x1406573f0  push    rbx
0x1406573f2  push    rbp
0x1406573f3  push    rsi
0x1406573f4  push    rdi
0x1406573f5  push    r14
0x1406573f7  push    r15
0x1406573f9  sub     rsp, 48h
0x1406573fd  xorps   xmm0, xmm0
0x140657400  mov     r15, rcx
0x140657403  mov     ecx, 223h
0x140657408  mov     r14, rdx
0x14065740b  movups  [rsp+78h+var_58], xmm0
0x140657410  movups  [rsp+78h+var_48], xmm0
0x140657415  call    DifGetAPIThunkContextById
0x14065741a  mov     rsi, rax
0x14065741d  test    rax, rax
0x140657420  jz      loc_1406574B5
0x140657426  mov     eax, [rax+0Ch]
0x140657429  test    al, 18h
0x14065742b  jz      short loc_140657439
0x14065742d  mov     rcx, [rsp+78h]
0x140657432  mov     qword ptr [rsp+78h+var_58], rcx
0x140657437  jmp     short loc_140657447
0x140657439  test    al, 4
0x14065743b  jz      short loc_140657447
0x14065743d  call    DifGetReturnAddressForWrappers
0x140657442  mov     qword ptr [rsp+78h+var_58], rax
0x140657447  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065744e  mov     qword ptr [rsp+78h+var_48], r15
0x140657453  mov     qword ptr [rsp+78h+var_58+8], r14
0x140657458  jnz     short loc_140657469
0x14065745a  xor     bpl, bpl
0x14065745d  test    cs:VfOptionFlags, 800h
0x140657467  jz      short loc_14065747C
0x140657469  lea     rcx, DifRebootlessRundown; RunRef
0x140657470  call    ExAcquireRundownProtection_0
0x140657475  mov     bpl, al
0x140657478  test    al, al
0x14065747a  jz      short loc_1406574B5
0x14065747c  lea     rdi, [rsi+20h]
0x140657480  mov     rbx, [rdi]
0x140657483  jmp     short loc_14065749F
0x140657485  lea     rax, [rbx-10h]
0x140657489  test    rax, rax
0x14065748c  jz      short loc_14065749C
0x14065748e  mov     rax, [rax+8]
0x140657492  lea     rcx, [rsp+78h+var_58]
0x140657497  call    _guard_dispatch_icall_no_overrides
0x14065749c  mov     rbx, [rbx]
0x14065749f  cmp     rbx, rdi
0x1406574a2  jnz     short loc_140657485
0x1406574a4  test    bpl, bpl
0x1406574a7  jz      short loc_1406574B5
0x1406574a9  lea     rcx, DifRebootlessRundown; RunRef
0x1406574b0  call    ExReleaseRundownProtection_0
0x1406574b5  mov     rdx, r14; TmVirtualClock
0x1406574b8  mov     rcx, r15; EnlistmentHandle
0x1406574bb  call    cs:__imp_NtPrePrepareComplete
0x1406574c2  nop     dword ptr [rax+rax+00h]
0x1406574c7  mov     dword ptr [rsp+78h+var_48+8], eax
0x1406574cb  test    rsi, rsi
0x1406574ce  jz      short loc_140657534
0x1406574d0  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406574d7  jnz     short loc_1406574E8
0x1406574d9  xor     dil, dil
0x1406574dc  test    cs:VfOptionFlags, 800h
0x1406574e6  jz      short loc_1406574FB
0x1406574e8  lea     rcx, DifRebootlessRundown; RunRef
0x1406574ef  call    ExAcquireRundownProtection_0
0x1406574f4  mov     dil, al
0x1406574f7  test    al, al
0x1406574f9  jz      short loc_140657534
0x1406574fb  add     rsi, 30h ; '0'
0x1406574ff  mov     rbx, [rsi]
0x140657502  jmp     short loc_14065751E
0x140657504  lea     rax, [rbx-10h]
0x140657508  test    rax, rax
0x14065750b  jz      short loc_14065751B
0x14065750d  mov     rax, [rax+8]
0x140657511  lea     rcx, [rsp+78h+var_58]
0x140657516  call    _guard_dispatch_icall_no_overrides
0x14065751b  mov     rbx, [rbx]
0x14065751e  cmp     rbx, rsi
0x140657521  jnz     short loc_140657504
0x140657523  test    dil, dil
0x140657526  jz      short loc_140657534
0x140657528  lea     rcx, DifRebootlessRundown; RunRef
0x14065752f  call    ExReleaseRundownProtection_0
0x140657534  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140657538  add     rsp, 48h
0x14065753c  pop     r15
0x14065753e  pop     r14
0x140657540  pop     rdi
0x140657541  pop     rsi
0x140657542  pop     rbp
0x140657543  pop     rbx
0x140657544  retn
```
