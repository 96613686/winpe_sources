# DifNtPrepareCompleteWrapper

- ea: `0x14065d1a0`
- end: `0x14065d2f6`
- name: `DifNtPrepareCompleteWrapper`
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
- `0x14065d1a0`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPrepareComplete` at `0x14065d26b`
- `ext-ms-win-ntos-tm-l1-1-0!NtPrepareComplete` at `0x14065d26b`

## pseudocode

```c
__int64 __fastcall DifNtPrepareCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  BOOLEAN v14; // di
  _QWORD **v15; // rsi
  _QWORD *j; // rbx
  __int128 v18; // [rsp+20h] [rbp-58h] BYREF
  __int128 v19; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v18 = 0;
  v19 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(548);
  v9 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v10 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v10 & 0x18) != 0 )
    {
      *(_QWORD *)&v18 = retaddr;
    }
    else if ( (v10 & 4) != 0 )
    {
      *(_QWORD *)&v18 = DifGetReturnAddressForWrappers(v6, v5, v7, v8);
    }
    *(_QWORD *)&v19 = EnlistmentHandle;
    *((_QWORD *)&v18 + 1) = TmVirtualClock;
    if ( !VfDifRunningWithoutReboot && (v11 = 0, (VfOptionFlags & 0x800) == 0)
      || (v11 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v9 + 32); i != (_QWORD *)(v9 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v18, v5);
      }
      if ( v11 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  DWORD2(v19) = NtPrepareComplete(EnlistmentHandle, TmVirtualClock);
  if ( v9 )
  {
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      v15 = (_QWORD **)(v9 + 48);
      for ( j = *v15; j != v15; j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v18, v13);
      }
      if ( v14 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return DWORD2(v19);
}

```

## disassembly

```asm
0x14065d1a0  push    rbx
0x14065d1a2  push    rbp
0x14065d1a3  push    rsi
0x14065d1a4  push    rdi
0x14065d1a5  push    r14
0x14065d1a7  push    r15
0x14065d1a9  sub     rsp, 48h
0x14065d1ad  xorps   xmm0, xmm0
0x14065d1b0  mov     r15, rcx
0x14065d1b3  mov     ecx, 224h
0x14065d1b8  mov     r14, rdx
0x14065d1bb  movups  [rsp+78h+var_58], xmm0
0x14065d1c0  movups  [rsp+78h+var_48], xmm0
0x14065d1c5  call    DifGetAPIThunkContextById
0x14065d1ca  mov     rsi, rax
0x14065d1cd  test    rax, rax
0x14065d1d0  jz      loc_14065D265
0x14065d1d6  mov     eax, [rax+0Ch]
0x14065d1d9  test    al, 18h
0x14065d1db  jz      short loc_14065D1E9
0x14065d1dd  mov     rcx, [rsp+78h]
0x14065d1e2  mov     qword ptr [rsp+78h+var_58], rcx
0x14065d1e7  jmp     short loc_14065D1F7
0x14065d1e9  test    al, 4
0x14065d1eb  jz      short loc_14065D1F7
0x14065d1ed  call    DifGetReturnAddressForWrappers
0x14065d1f2  mov     qword ptr [rsp+78h+var_58], rax
0x14065d1f7  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065d1fe  mov     qword ptr [rsp+78h+var_48], r15
0x14065d203  mov     qword ptr [rsp+78h+var_58+8], r14
0x14065d208  jnz     short loc_14065D219
0x14065d20a  xor     bpl, bpl
0x14065d20d  test    cs:VfOptionFlags, 800h
0x14065d217  jz      short loc_14065D22C
0x14065d219  lea     rcx, DifRebootlessRundown; RunRef
0x14065d220  call    ExAcquireRundownProtection_0
0x14065d225  mov     bpl, al
0x14065d228  test    al, al
0x14065d22a  jz      short loc_14065D265
0x14065d22c  lea     rdi, [rsi+20h]
0x14065d230  mov     rbx, [rdi]
0x14065d233  jmp     short loc_14065D24F
0x14065d235  lea     rax, [rbx-10h]
0x14065d239  test    rax, rax
0x14065d23c  jz      short loc_14065D24C
0x14065d23e  mov     rax, [rax+8]
0x14065d242  lea     rcx, [rsp+78h+var_58]
0x14065d247  call    _guard_dispatch_icall_no_overrides
0x14065d24c  mov     rbx, [rbx]
0x14065d24f  cmp     rbx, rdi
0x14065d252  jnz     short loc_14065D235
0x14065d254  test    bpl, bpl
0x14065d257  jz      short loc_14065D265
0x14065d259  lea     rcx, DifRebootlessRundown; RunRef
0x14065d260  call    ExReleaseRundownProtection_0
0x14065d265  mov     rdx, r14; TmVirtualClock
0x14065d268  mov     rcx, r15; EnlistmentHandle
0x14065d26b  call    cs:__imp_NtPrepareComplete
0x14065d272  nop     dword ptr [rax+rax+00h]
0x14065d277  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065d27b  test    rsi, rsi
0x14065d27e  jz      short loc_14065D2E4
0x14065d280  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065d287  jnz     short loc_14065D298
0x14065d289  xor     dil, dil
0x14065d28c  test    cs:VfOptionFlags, 800h
0x14065d296  jz      short loc_14065D2AB
0x14065d298  lea     rcx, DifRebootlessRundown; RunRef
0x14065d29f  call    ExAcquireRundownProtection_0
0x14065d2a4  mov     dil, al
0x14065d2a7  test    al, al
0x14065d2a9  jz      short loc_14065D2E4
0x14065d2ab  add     rsi, 30h ; '0'
0x14065d2af  mov     rbx, [rsi]
0x14065d2b2  jmp     short loc_14065D2CE
0x14065d2b4  lea     rax, [rbx-10h]
0x14065d2b8  test    rax, rax
0x14065d2bb  jz      short loc_14065D2CB
0x14065d2bd  mov     rax, [rax+8]
0x14065d2c1  lea     rcx, [rsp+78h+var_58]
0x14065d2c6  call    _guard_dispatch_icall_no_overrides
0x14065d2cb  mov     rbx, [rbx]
0x14065d2ce  cmp     rbx, rsi
0x14065d2d1  jnz     short loc_14065D2B4
0x14065d2d3  test    dil, dil
0x14065d2d6  jz      short loc_14065D2E4
0x14065d2d8  lea     rcx, DifRebootlessRundown; RunRef
0x14065d2df  call    ExReleaseRundownProtection_0
0x14065d2e4  mov     eax, dword ptr [rsp+78h+var_48+8]
0x14065d2e8  add     rsp, 48h
0x14065d2ec  pop     r15
0x14065d2ee  pop     r14
0x14065d2f0  pop     rdi
0x14065d2f1  pop     rsi
0x14065d2f2  pop     rbp
0x14065d2f3  pop     rbx
0x14065d2f4  retn
```
