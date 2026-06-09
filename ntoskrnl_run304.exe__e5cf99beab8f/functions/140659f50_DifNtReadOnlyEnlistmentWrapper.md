# DifNtReadOnlyEnlistmentWrapper

- ea: `0x140659f50`
- end: `0x14065a0a6`
- name: `DifNtReadOnlyEnlistmentWrapper`
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
- `0x140659f50`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtReadOnlyEnlistment` at `0x14065a01b`
- `ext-ms-win-ntos-tm-l1-1-0!NtReadOnlyEnlistment` at `0x14065a01b`

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
  BOOLEAN v15; // di
  _QWORD **v16; // rsi
  _QWORD *j; // rbx
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v19 = 0;
  v20 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(550);
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
  DWORD2(v20) = NtReadOnlyEnlistment(EnlistmentHandle, TmVirtualClock);
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
0x140659f50  push    rbx
0x140659f52  push    rbp
0x140659f53  push    rsi
0x140659f54  push    rdi
0x140659f55  push    r14
0x140659f57  push    r15
0x140659f59  sub     rsp, 48h
0x140659f5d  xorps   xmm0, xmm0
0x140659f60  mov     r15, rcx
0x140659f63  mov     ecx, 226h
0x140659f68  mov     r14, rdx
0x140659f6b  movups  [rsp+78h+var_58], xmm0
0x140659f70  movups  [rsp+78h+var_48], xmm0
0x140659f75  call    DifGetAPIThunkContextById
0x140659f7a  mov     rsi, rax
0x140659f7d  test    rax, rax
0x140659f80  jz      loc_14065A015
0x140659f86  mov     eax, [rax+0Ch]
0x140659f89  test    al, 18h
0x140659f8b  jz      short loc_140659F99
0x140659f8d  mov     rcx, [rsp+78h]
0x140659f92  mov     qword ptr [rsp+78h+var_58], rcx
0x140659f97  jmp     short loc_140659FA7
0x140659f99  test    al, 4
0x140659f9b  jz      short loc_140659FA7
0x140659f9d  call    DifGetReturnAddressForWrappers
0x140659fa2  mov     qword ptr [rsp+78h+var_58], rax
0x140659fa7  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659fae  mov     qword ptr [rsp+78h+var_48], r15
0x140659fb3  mov     qword ptr [rsp+78h+var_58+8], r14
0x140659fb8  jnz     short loc_140659FC9
0x140659fba  xor     bpl, bpl
0x140659fbd  test    cs:VfOptionFlags, 800h
0x140659fc7  jz      short loc_140659FDC
0x140659fc9  lea     rcx, DifRebootlessRundown; RunRef
0x140659fd0  call    ExAcquireRundownProtection_0
0x140659fd5  mov     bpl, al
0x140659fd8  test    al, al
0x140659fda  jz      short loc_14065A015
0x140659fdc  lea     rdi, [rsi+20h]
0x140659fe0  mov     rbx, [rdi]
0x140659fe3  jmp     short loc_140659FFF
0x140659fe5  lea     rax, [rbx-10h]
0x140659fe9  test    rax, rax
0x140659fec  jz      short loc_140659FFC
0x140659fee  mov     rax, [rax+8]
0x140659ff2  lea     rcx, [rsp+78h+var_58]
0x140659ff7  call    _guard_dispatch_icall_no_overrides
0x140659ffc  mov     rbx, [rbx]
0x140659fff  cmp     rbx, rdi
0x14065a002  jnz     short loc_140659FE5
0x14065a004  test    bpl, bpl
0x14065a007  jz      short loc_14065A015
0x14065a009  lea     rcx, DifRebootlessRundown; RunRef
0x14065a010  call    ExReleaseRundownProtection_0
0x14065a015  mov     rdx, r14; TmVirtualClock
0x14065a018  mov     rcx, r15; EnlistmentHandle
0x14065a01b  call    cs:__imp_NtReadOnlyEnlistment
0x14065a022  nop     dword ptr [rax+rax+00h]
0x14065a027  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065a02b  test    rsi, rsi
0x14065a02e  jz      short loc_14065A094
0x14065a030  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065a037  jnz     short loc_14065A048
0x14065a039  xor     dil, dil
0x14065a03c  test    cs:VfOptionFlags, 800h
0x14065a046  jz      short loc_14065A05B
0x14065a048  lea     rcx, DifRebootlessRundown; RunRef
0x14065a04f  call    ExAcquireRundownProtection_0
0x14065a054  mov     dil, al
0x14065a057  test    al, al
0x14065a059  jz      short loc_14065A094
0x14065a05b  add     rsi, 30h ; '0'
0x14065a05f  mov     rbx, [rsi]
0x14065a062  jmp     short loc_14065A07E
0x14065a064  lea     rax, [rbx-10h]
0x14065a068  test    rax, rax
0x14065a06b  jz      short loc_14065A07B
0x14065a06d  mov     rax, [rax+8]
0x14065a071  lea     rcx, [rsp+78h+var_58]
0x14065a076  call    _guard_dispatch_icall_no_overrides
0x14065a07b  mov     rbx, [rbx]
0x14065a07e  cmp     rbx, rsi
0x14065a081  jnz     short loc_14065A064
0x14065a083  test    dil, dil
0x14065a086  jz      short loc_14065A094
0x14065a088  lea     rcx, DifRebootlessRundown; RunRef
0x14065a08f  call    ExReleaseRundownProtection_0
0x14065a094  mov     eax, dword ptr [rsp+78h+var_48+8]
0x14065a098  add     rsp, 48h
0x14065a09c  pop     r15
0x14065a09e  pop     r14
0x14065a0a0  pop     rdi
0x14065a0a1  pop     rsi
0x14065a0a2  pop     rbp
0x14065a0a3  pop     rbx
0x14065a0a4  retn
```
