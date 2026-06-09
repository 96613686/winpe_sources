# DifNtCommitCompleteWrapper

- ea: `0x140658ac0`
- end: `0x140658c16`
- name: `DifNtCommitCompleteWrapper`
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
- `0x140658ac0`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitComplete` at `0x140658b8b`
- `ext-ms-win-ntos-tm-l1-1-0!NtCommitComplete` at `0x140658b8b`

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
0x140658ac0  push    rbx
0x140658ac2  push    rbp
0x140658ac3  push    rsi
0x140658ac4  push    rdi
0x140658ac5  push    r14
0x140658ac7  push    r15
0x140658ac9  sub     rsp, 48h
0x140658acd  xorps   xmm0, xmm0
0x140658ad0  mov     r15, rcx
0x140658ad3  mov     ecx, 225h
0x140658ad8  mov     r14, rdx
0x140658adb  movups  [rsp+78h+var_58], xmm0
0x140658ae0  movups  [rsp+78h+var_48], xmm0
0x140658ae5  call    DifGetAPIThunkContextById
0x140658aea  mov     rsi, rax
0x140658aed  test    rax, rax
0x140658af0  jz      loc_140658B85
0x140658af6  mov     eax, [rax+0Ch]
0x140658af9  test    al, 18h
0x140658afb  jz      short loc_140658B09
0x140658afd  mov     rcx, [rsp+78h]
0x140658b02  mov     qword ptr [rsp+78h+var_58], rcx
0x140658b07  jmp     short loc_140658B17
0x140658b09  test    al, 4
0x140658b0b  jz      short loc_140658B17
0x140658b0d  call    DifGetReturnAddressForWrappers
0x140658b12  mov     qword ptr [rsp+78h+var_58], rax
0x140658b17  cmp     cs:VfDifRunningWithoutReboot, 0
0x140658b1e  mov     qword ptr [rsp+78h+var_48], r15
0x140658b23  mov     qword ptr [rsp+78h+var_58+8], r14
0x140658b28  jnz     short loc_140658B39
0x140658b2a  xor     bpl, bpl
0x140658b2d  test    cs:VfOptionFlags, 800h
0x140658b37  jz      short loc_140658B4C
0x140658b39  lea     rcx, DifRebootlessRundown; RunRef
0x140658b40  call    ExAcquireRundownProtection_0
0x140658b45  mov     bpl, al
0x140658b48  test    al, al
0x140658b4a  jz      short loc_140658B85
0x140658b4c  lea     rdi, [rsi+20h]
0x140658b50  mov     rbx, [rdi]
0x140658b53  jmp     short loc_140658B6F
0x140658b55  lea     rax, [rbx-10h]
0x140658b59  test    rax, rax
0x140658b5c  jz      short loc_140658B6C
0x140658b5e  mov     rax, [rax+8]
0x140658b62  lea     rcx, [rsp+78h+var_58]
0x140658b67  call    _guard_dispatch_icall_no_overrides
0x140658b6c  mov     rbx, [rbx]
0x140658b6f  cmp     rbx, rdi
0x140658b72  jnz     short loc_140658B55
0x140658b74  test    bpl, bpl
0x140658b77  jz      short loc_140658B85
0x140658b79  lea     rcx, DifRebootlessRundown; RunRef
0x140658b80  call    ExReleaseRundownProtection_0
0x140658b85  mov     rdx, r14; TmVirtualClock
0x140658b88  mov     rcx, r15; EnlistmentHandle
0x140658b8b  call    cs:__imp_NtCommitComplete
0x140658b92  nop     dword ptr [rax+rax+00h]
0x140658b97  mov     dword ptr [rsp+78h+var_48+8], eax
0x140658b9b  test    rsi, rsi
0x140658b9e  jz      short loc_140658C04
0x140658ba0  cmp     cs:VfDifRunningWithoutReboot, 0
0x140658ba7  jnz     short loc_140658BB8
0x140658ba9  xor     dil, dil
0x140658bac  test    cs:VfOptionFlags, 800h
0x140658bb6  jz      short loc_140658BCB
0x140658bb8  lea     rcx, DifRebootlessRundown; RunRef
0x140658bbf  call    ExAcquireRundownProtection_0
0x140658bc4  mov     dil, al
0x140658bc7  test    al, al
0x140658bc9  jz      short loc_140658C04
0x140658bcb  add     rsi, 30h ; '0'
0x140658bcf  mov     rbx, [rsi]
0x140658bd2  jmp     short loc_140658BEE
0x140658bd4  lea     rax, [rbx-10h]
0x140658bd8  test    rax, rax
0x140658bdb  jz      short loc_140658BEB
0x140658bdd  mov     rax, [rax+8]
0x140658be1  lea     rcx, [rsp+78h+var_58]
0x140658be6  call    _guard_dispatch_icall_no_overrides
0x140658beb  mov     rbx, [rbx]
0x140658bee  cmp     rbx, rsi
0x140658bf1  jnz     short loc_140658BD4
0x140658bf3  test    dil, dil
0x140658bf6  jz      short loc_140658C04
0x140658bf8  lea     rcx, DifRebootlessRundown; RunRef
0x140658bff  call    ExReleaseRundownProtection_0
0x140658c04  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140658c08  add     rsp, 48h
0x140658c0c  pop     r15
0x140658c0e  pop     r14
0x140658c10  pop     rdi
0x140658c11  pop     rsi
0x140658c12  pop     rbp
0x140658c13  pop     rbx
0x140658c14  retn
```
