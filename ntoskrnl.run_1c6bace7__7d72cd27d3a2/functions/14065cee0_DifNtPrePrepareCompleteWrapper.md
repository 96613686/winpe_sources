# DifNtPrePrepareCompleteWrapper

- ea: `0x14065cee0`
- end: `0x14065d036`
- name: `DifNtPrePrepareCompleteWrapper`
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
- `0x14065cee0`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPrePrepareComplete` at `0x14065cfab`
- `ext-ms-win-ntos-tm-l1-1-0!NtPrePrepareComplete` at `0x14065cfab`

## pseudocode

```c
__int64 __fastcall DifNtPrePrepareCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  __int64 APIThunkContextById; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rsi
  int v9; // eax
  BOOLEAN v10; // bp
  _QWORD *i; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  BOOLEAN v14; // di
  _QWORD **v15; // rsi
  _QWORD *j; // rbx
  __int128 v18; // [rsp+20h] [rbp-58h] BYREF
  __int128 v19; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v18 = 0;
  v19 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(547);
  v8 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v9 = *(_DWORD *)(APIThunkContextById + 12);
    if ( (v9 & 0x18) != 0 )
    {
      *(_QWORD *)&v18 = retaddr;
    }
    else if ( (v9 & 4) != 0 )
    {
      *(_QWORD *)&v18 = DifGetReturnAddressForWrappers(v6, v5, v7);
    }
    *(_QWORD *)&v19 = EnlistmentHandle;
    *((_QWORD *)&v18 + 1) = TmVirtualClock;
    if ( !VfDifRunningWithoutReboot && (v10 = 0, (VfOptionFlags & 0x800) == 0)
      || (v10 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v8 + 32); i != (_QWORD *)(v8 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v18, v5, v7);
      }
      if ( v10 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  DWORD2(v19) = NtPrePrepareComplete(EnlistmentHandle, TmVirtualClock);
  if ( v8 )
  {
    if ( !VfDifRunningWithoutReboot && (v14 = 0, (VfOptionFlags & 0x800) == 0)
      || (v14 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      v15 = (_QWORD **)(v8 + 48);
      for ( j = *v15; j != v15; j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v18, v12, v13);
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
0x14065cee0  push    rbx
0x14065cee2  push    rbp
0x14065cee3  push    rsi
0x14065cee4  push    rdi
0x14065cee5  push    r14
0x14065cee7  push    r15
0x14065cee9  sub     rsp, 48h
0x14065ceed  xorps   xmm0, xmm0
0x14065cef0  mov     r15, rcx
0x14065cef3  mov     ecx, 223h
0x14065cef8  mov     r14, rdx
0x14065cefb  movups  [rsp+78h+var_58], xmm0
0x14065cf00  movups  [rsp+78h+var_48], xmm0
0x14065cf05  call    DifGetAPIThunkContextById
0x14065cf0a  mov     rsi, rax
0x14065cf0d  test    rax, rax
0x14065cf10  jz      loc_14065CFA5
0x14065cf16  mov     eax, [rax+0Ch]
0x14065cf19  test    al, 18h
0x14065cf1b  jz      short loc_14065CF29
0x14065cf1d  mov     rcx, [rsp+78h]
0x14065cf22  mov     qword ptr [rsp+78h+var_58], rcx
0x14065cf27  jmp     short loc_14065CF37
0x14065cf29  test    al, 4
0x14065cf2b  jz      short loc_14065CF37
0x14065cf2d  call    DifGetReturnAddressForWrappers
0x14065cf32  mov     qword ptr [rsp+78h+var_58], rax
0x14065cf37  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065cf3e  mov     qword ptr [rsp+78h+var_48], r15
0x14065cf43  mov     qword ptr [rsp+78h+var_58+8], r14
0x14065cf48  jnz     short loc_14065CF59
0x14065cf4a  xor     bpl, bpl
0x14065cf4d  test    cs:VfOptionFlags, 800h
0x14065cf57  jz      short loc_14065CF6C
0x14065cf59  lea     rcx, DifRebootlessRundown; RunRef
0x14065cf60  call    ExAcquireRundownProtection_0
0x14065cf65  mov     bpl, al
0x14065cf68  test    al, al
0x14065cf6a  jz      short loc_14065CFA5
0x14065cf6c  lea     rdi, [rsi+20h]
0x14065cf70  mov     rbx, [rdi]
0x14065cf73  jmp     short loc_14065CF8F
0x14065cf75  lea     rax, [rbx-10h]
0x14065cf79  test    rax, rax
0x14065cf7c  jz      short loc_14065CF8C
0x14065cf7e  mov     rax, [rax+8]
0x14065cf82  lea     rcx, [rsp+78h+var_58]
0x14065cf87  call    _guard_dispatch_icall_no_overrides
0x14065cf8c  mov     rbx, [rbx]
0x14065cf8f  cmp     rbx, rdi
0x14065cf92  jnz     short loc_14065CF75
0x14065cf94  test    bpl, bpl
0x14065cf97  jz      short loc_14065CFA5
0x14065cf99  lea     rcx, DifRebootlessRundown; RunRef
0x14065cfa0  call    ExReleaseRundownProtection_0
0x14065cfa5  mov     rdx, r14; TmVirtualClock
0x14065cfa8  mov     rcx, r15; EnlistmentHandle
0x14065cfab  call    cs:__imp_NtPrePrepareComplete
0x14065cfb2  nop     dword ptr [rax+rax+00h]
0x14065cfb7  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065cfbb  test    rsi, rsi
0x14065cfbe  jz      short loc_14065D024
0x14065cfc0  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065cfc7  jnz     short loc_14065CFD8
0x14065cfc9  xor     dil, dil
0x14065cfcc  test    cs:VfOptionFlags, 800h
0x14065cfd6  jz      short loc_14065CFEB
0x14065cfd8  lea     rcx, DifRebootlessRundown; RunRef
0x14065cfdf  call    ExAcquireRundownProtection_0
0x14065cfe4  mov     dil, al
0x14065cfe7  test    al, al
0x14065cfe9  jz      short loc_14065D024
0x14065cfeb  add     rsi, 30h ; '0'
0x14065cfef  mov     rbx, [rsi]
0x14065cff2  jmp     short loc_14065D00E
0x14065cff4  lea     rax, [rbx-10h]
0x14065cff8  test    rax, rax
0x14065cffb  jz      short loc_14065D00B
0x14065cffd  mov     rax, [rax+8]
0x14065d001  lea     rcx, [rsp+78h+var_58]
0x14065d006  call    _guard_dispatch_icall_no_overrides
0x14065d00b  mov     rbx, [rbx]
0x14065d00e  cmp     rbx, rsi
0x14065d011  jnz     short loc_14065CFF4
0x14065d013  test    dil, dil
0x14065d016  jz      short loc_14065D024
0x14065d018  lea     rcx, DifRebootlessRundown; RunRef
0x14065d01f  call    ExReleaseRundownProtection_0
0x14065d024  mov     eax, dword ptr [rsp+78h+var_48+8]
0x14065d028  add     rsp, 48h
0x14065d02c  pop     r15
0x14065d02e  pop     r14
0x14065d030  pop     rdi
0x14065d031  pop     rsi
0x14065d032  pop     rbp
0x14065d033  pop     rbx
0x14065d034  retn
```
