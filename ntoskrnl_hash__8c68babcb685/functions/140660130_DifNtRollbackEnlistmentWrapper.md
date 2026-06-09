# DifNtRollbackEnlistmentWrapper

- ea: `0x140660130`
- end: `0x140660286`
- name: `DifNtRollbackEnlistmentWrapper`
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
- `0x140660130`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackEnlistment` at `0x1406601fb`
- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackEnlistment` at `0x1406601fb`

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
  BOOLEAN v14; // di
  _QWORD **v15; // rsi
  _QWORD *j; // rbx
  __int128 v18; // [rsp+20h] [rbp-58h] BYREF
  __int128 v19; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v18 = 0;
  v19 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(546);
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
  DWORD2(v19) = NtRollbackEnlistment(EnlistmentHandle, TmVirtualClock);
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
0x140660130  push    rbx
0x140660132  push    rbp
0x140660133  push    rsi
0x140660134  push    rdi
0x140660135  push    r14
0x140660137  push    r15
0x140660139  sub     rsp, 48h
0x14066013d  xorps   xmm0, xmm0
0x140660140  mov     r15, rcx
0x140660143  mov     ecx, 222h
0x140660148  mov     r14, rdx
0x14066014b  movups  [rsp+78h+var_58], xmm0
0x140660150  movups  [rsp+78h+var_48], xmm0
0x140660155  call    DifGetAPIThunkContextById
0x14066015a  mov     rsi, rax
0x14066015d  test    rax, rax
0x140660160  jz      loc_1406601F5
0x140660166  mov     eax, [rax+0Ch]
0x140660169  test    al, 18h
0x14066016b  jz      short loc_140660179
0x14066016d  mov     rcx, [rsp+78h]
0x140660172  mov     qword ptr [rsp+78h+var_58], rcx
0x140660177  jmp     short loc_140660187
0x140660179  test    al, 4
0x14066017b  jz      short loc_140660187
0x14066017d  call    DifGetReturnAddressForWrappers
0x140660182  mov     qword ptr [rsp+78h+var_58], rax
0x140660187  cmp     cs:VfDifRunningWithoutReboot, 0
0x14066018e  mov     qword ptr [rsp+78h+var_48], r15
0x140660193  mov     qword ptr [rsp+78h+var_58+8], r14
0x140660198  jnz     short loc_1406601A9
0x14066019a  xor     bpl, bpl
0x14066019d  test    cs:VfOptionFlags, 800h
0x1406601a7  jz      short loc_1406601BC
0x1406601a9  lea     rcx, DifRebootlessRundown; RunRef
0x1406601b0  call    ExAcquireRundownProtection_0
0x1406601b5  mov     bpl, al
0x1406601b8  test    al, al
0x1406601ba  jz      short loc_1406601F5
0x1406601bc  lea     rdi, [rsi+20h]
0x1406601c0  mov     rbx, [rdi]
0x1406601c3  jmp     short loc_1406601DF
0x1406601c5  lea     rax, [rbx-10h]
0x1406601c9  test    rax, rax
0x1406601cc  jz      short loc_1406601DC
0x1406601ce  mov     rax, [rax+8]
0x1406601d2  lea     rcx, [rsp+78h+var_58]
0x1406601d7  call    _guard_dispatch_icall_no_overrides
0x1406601dc  mov     rbx, [rbx]
0x1406601df  cmp     rbx, rdi
0x1406601e2  jnz     short loc_1406601C5
0x1406601e4  test    bpl, bpl
0x1406601e7  jz      short loc_1406601F5
0x1406601e9  lea     rcx, DifRebootlessRundown; RunRef
0x1406601f0  call    ExReleaseRundownProtection_0
0x1406601f5  mov     rdx, r14; TmVirtualClock
0x1406601f8  mov     rcx, r15; EnlistmentHandle
0x1406601fb  call    cs:__imp_NtRollbackEnlistment
0x140660202  nop     dword ptr [rax+rax+00h]
0x140660207  mov     dword ptr [rsp+78h+var_48+8], eax
0x14066020b  test    rsi, rsi
0x14066020e  jz      short loc_140660274
0x140660210  cmp     cs:VfDifRunningWithoutReboot, 0
0x140660217  jnz     short loc_140660228
0x140660219  xor     dil, dil
0x14066021c  test    cs:VfOptionFlags, 800h
0x140660226  jz      short loc_14066023B
0x140660228  lea     rcx, DifRebootlessRundown; RunRef
0x14066022f  call    ExAcquireRundownProtection_0
0x140660234  mov     dil, al
0x140660237  test    al, al
0x140660239  jz      short loc_140660274
0x14066023b  add     rsi, 30h ; '0'
0x14066023f  mov     rbx, [rsi]
0x140660242  jmp     short loc_14066025E
0x140660244  lea     rax, [rbx-10h]
0x140660248  test    rax, rax
0x14066024b  jz      short loc_14066025B
0x14066024d  mov     rax, [rax+8]
0x140660251  lea     rcx, [rsp+78h+var_58]
0x140660256  call    _guard_dispatch_icall_no_overrides
0x14066025b  mov     rbx, [rbx]
0x14066025e  cmp     rbx, rsi
0x140660261  jnz     short loc_140660244
0x140660263  test    dil, dil
0x140660266  jz      short loc_140660274
0x140660268  lea     rcx, DifRebootlessRundown; RunRef
0x14066026f  call    ExReleaseRundownProtection_0
0x140660274  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140660278  add     rsp, 48h
0x14066027c  pop     r15
0x14066027e  pop     r14
0x140660280  pop     rdi
0x140660281  pop     rsi
0x140660282  pop     rbp
0x140660283  pop     rbx
0x140660284  retn
```
