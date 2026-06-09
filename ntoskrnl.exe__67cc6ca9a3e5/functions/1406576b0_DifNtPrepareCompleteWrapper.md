# DifNtPrepareCompleteWrapper

- ea: `0x1406576b0`
- end: `0x140657806`
- name: `DifNtPrepareCompleteWrapper`
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
- `0x1406576b0`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPrepareComplete` at `0x14065777b`
- `ext-ms-win-ntos-tm-l1-1-0!NtPrepareComplete` at `0x14065777b`

## pseudocode

```c
__int64 __fastcall DifNtPrepareCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  __int128 *APIThunkContextById; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int128 *v9; // rsi
  int v10; // eax
  BOOLEAN v11; // bp
  __int128 *i; // rbx
  BOOLEAN v13; // di
  _QWORD **v14; // rsi
  _QWORD *j; // rbx
  __int128 v17; // [rsp+20h] [rbp-58h] BYREF
  __int128 v18; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h]

  v17 = 0;
  v18 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(548);
  v9 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v10 = *((_DWORD *)APIThunkContextById + 3);
    if ( (v10 & 0x18) != 0 )
    {
      *(_QWORD *)&v17 = retaddr;
    }
    else if ( (v10 & 4) != 0 )
    {
      *(_QWORD *)&v17 = DifGetReturnAddressForWrappers(v6, v5, v7, v8);
    }
    *(_QWORD *)&v18 = EnlistmentHandle;
    *((_QWORD *)&v17 + 1) = TmVirtualClock;
    if ( !VfDifRunningWithoutReboot && (v11 = 0, (VfOptionFlags & 0x800) == 0)
      || (v11 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = (__int128 *)*((_QWORD *)v9 + 4); i != v9 + 2; i = *(__int128 **)i )
      {
        if ( i != (__int128 *)16 )
          guard_dispatch_icall_no_overrides(&v17);
      }
      if ( v11 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  DWORD2(v18) = NtPrepareComplete(EnlistmentHandle, TmVirtualClock);
  if ( v9 )
  {
    if ( !VfDifRunningWithoutReboot && (v13 = 0, (VfOptionFlags & 0x800) == 0)
      || (v13 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      v14 = (_QWORD **)(v9 + 3);
      for ( j = *v14; j != v14; j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v17);
      }
      if ( v13 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return DWORD2(v18);
}

```

## disassembly

```asm
0x1406576b0  push    rbx
0x1406576b2  push    rbp
0x1406576b3  push    rsi
0x1406576b4  push    rdi
0x1406576b5  push    r14
0x1406576b7  push    r15
0x1406576b9  sub     rsp, 48h
0x1406576bd  xorps   xmm0, xmm0
0x1406576c0  mov     r15, rcx
0x1406576c3  mov     ecx, 224h
0x1406576c8  mov     r14, rdx
0x1406576cb  movups  [rsp+78h+var_58], xmm0
0x1406576d0  movups  [rsp+78h+var_48], xmm0
0x1406576d5  call    DifGetAPIThunkContextById
0x1406576da  mov     rsi, rax
0x1406576dd  test    rax, rax
0x1406576e0  jz      loc_140657775
0x1406576e6  mov     eax, [rax+0Ch]
0x1406576e9  test    al, 18h
0x1406576eb  jz      short loc_1406576F9
0x1406576ed  mov     rcx, [rsp+78h]
0x1406576f2  mov     qword ptr [rsp+78h+var_58], rcx
0x1406576f7  jmp     short loc_140657707
0x1406576f9  test    al, 4
0x1406576fb  jz      short loc_140657707
0x1406576fd  call    DifGetReturnAddressForWrappers
0x140657702  mov     qword ptr [rsp+78h+var_58], rax
0x140657707  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065770e  mov     qword ptr [rsp+78h+var_48], r15
0x140657713  mov     qword ptr [rsp+78h+var_58+8], r14
0x140657718  jnz     short loc_140657729
0x14065771a  xor     bpl, bpl
0x14065771d  test    cs:VfOptionFlags, 800h
0x140657727  jz      short loc_14065773C
0x140657729  lea     rcx, DifRebootlessRundown; RunRef
0x140657730  call    ExAcquireRundownProtection_0
0x140657735  mov     bpl, al
0x140657738  test    al, al
0x14065773a  jz      short loc_140657775
0x14065773c  lea     rdi, [rsi+20h]
0x140657740  mov     rbx, [rdi]
0x140657743  jmp     short loc_14065775F
0x140657745  lea     rax, [rbx-10h]
0x140657749  test    rax, rax
0x14065774c  jz      short loc_14065775C
0x14065774e  mov     rax, [rax+8]
0x140657752  lea     rcx, [rsp+78h+var_58]
0x140657757  call    _guard_dispatch_icall_no_overrides
0x14065775c  mov     rbx, [rbx]
0x14065775f  cmp     rbx, rdi
0x140657762  jnz     short loc_140657745
0x140657764  test    bpl, bpl
0x140657767  jz      short loc_140657775
0x140657769  lea     rcx, DifRebootlessRundown; RunRef
0x140657770  call    ExReleaseRundownProtection_0
0x140657775  mov     rdx, r14; TmVirtualClock
0x140657778  mov     rcx, r15; EnlistmentHandle
0x14065777b  call    cs:__imp_NtPrepareComplete
0x140657782  nop     dword ptr [rax+rax+00h]
0x140657787  mov     dword ptr [rsp+78h+var_48+8], eax
0x14065778b  test    rsi, rsi
0x14065778e  jz      short loc_1406577F4
0x140657790  cmp     cs:VfDifRunningWithoutReboot, 0
0x140657797  jnz     short loc_1406577A8
0x140657799  xor     dil, dil
0x14065779c  test    cs:VfOptionFlags, 800h
0x1406577a6  jz      short loc_1406577BB
0x1406577a8  lea     rcx, DifRebootlessRundown; RunRef
0x1406577af  call    ExAcquireRundownProtection_0
0x1406577b4  mov     dil, al
0x1406577b7  test    al, al
0x1406577b9  jz      short loc_1406577F4
0x1406577bb  add     rsi, 30h ; '0'
0x1406577bf  mov     rbx, [rsi]
0x1406577c2  jmp     short loc_1406577DE
0x1406577c4  lea     rax, [rbx-10h]
0x1406577c8  test    rax, rax
0x1406577cb  jz      short loc_1406577DB
0x1406577cd  mov     rax, [rax+8]
0x1406577d1  lea     rcx, [rsp+78h+var_58]
0x1406577d6  call    _guard_dispatch_icall_no_overrides
0x1406577db  mov     rbx, [rbx]
0x1406577de  cmp     rbx, rsi
0x1406577e1  jnz     short loc_1406577C4
0x1406577e3  test    dil, dil
0x1406577e6  jz      short loc_1406577F4
0x1406577e8  lea     rcx, DifRebootlessRundown; RunRef
0x1406577ef  call    ExReleaseRundownProtection_0
0x1406577f4  mov     eax, dword ptr [rsp+78h+var_48+8]
0x1406577f8  add     rsp, 48h
0x1406577fc  pop     r15
0x1406577fe  pop     r14
0x140657800  pop     rdi
0x140657801  pop     rsi
0x140657802  pop     rbp
0x140657803  pop     rbx
0x140657804  retn
```
