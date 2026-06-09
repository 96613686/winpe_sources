# DifNtRollbackCompleteWrapper

- ea: `0x14065ffd0`
- end: `0x140660126`
- name: `DifNtRollbackCompleteWrapper`
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
- `0x14065ffd0`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackComplete` at `0x14066009b`
- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackComplete` at `0x14066009b`

## pseudocode

```c
__int64 __fastcall DifNtRollbackCompleteWrapper(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
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
  APIThunkContextById = DifGetAPIThunkContextById(551);
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
  DWORD2(v21) = NtRollbackComplete(EnlistmentHandle, TmVirtualClock);
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
0x14065ffd0  push    rbx
0x14065ffd2  push    rbp
0x14065ffd3  push    rsi
0x14065ffd4  push    rdi
0x14065ffd5  push    r14
0x14065ffd7  push    r15
0x14065ffd9  sub     rsp, 48h
0x14065ffdd  xorps   xmm0, xmm0
0x14065ffe0  mov     r15, rcx
0x14065ffe3  mov     ecx, 227h
0x14065ffe8  mov     r14, rdx
0x14065ffeb  movups  [rsp+78h+var_58], xmm0
0x14065fff0  movups  [rsp+78h+var_48], xmm0
0x14065fff5  call    DifGetAPIThunkContextById
0x14065fffa  mov     rsi, rax
0x14065fffd  test    rax, rax
0x140660000  jz      loc_140660095
0x140660006  mov     eax, [rax+0Ch]
0x140660009  test    al, 18h
0x14066000b  jz      short loc_140660019
0x14066000d  mov     rcx, [rsp+78h]
0x140660012  mov     qword ptr [rsp+78h+var_58], rcx
0x140660017  jmp     short loc_140660027
0x140660019  test    al, 4
0x14066001b  jz      short loc_140660027
0x14066001d  call    DifGetReturnAddressForWrappers
0x140660022  mov     qword ptr [rsp+78h+var_58], rax
0x140660027  cmp     cs:VfDifRunningWithoutReboot, 0
0x14066002e  mov     qword ptr [rsp+78h+var_48], r15
0x140660033  mov     qword ptr [rsp+78h+var_58+8], r14
0x140660038  jnz     short loc_140660049
0x14066003a  xor     bpl, bpl
0x14066003d  test    cs:VfOptionFlags, 800h
0x140660047  jz      short loc_14066005C
0x140660049  lea     rcx, DifRebootlessRundown; RunRef
0x140660050  call    ExAcquireRundownProtection_0
0x140660055  mov     bpl, al
0x140660058  test    al, al
0x14066005a  jz      short loc_140660095
0x14066005c  lea     rdi, [rsi+20h]
0x140660060  mov     rbx, [rdi]
0x140660063  jmp     short loc_14066007F
0x140660065  lea     rax, [rbx-10h]
0x140660069  test    rax, rax
0x14066006c  jz      short loc_14066007C
0x14066006e  mov     rax, [rax+8]
0x140660072  lea     rcx, [rsp+78h+var_58]
0x140660077  call    _guard_dispatch_icall_no_overrides
0x14066007c  mov     rbx, [rbx]
0x14066007f  cmp     rbx, rdi
0x140660082  jnz     short loc_140660065
0x140660084  test    bpl, bpl
0x140660087  jz      short loc_140660095
0x140660089  lea     rcx, DifRebootlessRundown; RunRef
0x140660090  call    ExReleaseRundownProtection_0
0x140660095  mov     rdx, r14; TmVirtualClock
0x140660098  mov     rcx, r15; EnlistmentHandle
0x14066009b  call    cs:__imp_NtRollbackComplete
0x1406600a2  nop     dword ptr [rax+rax+00h]
0x1406600a7  mov     dword ptr [rsp+78h+var_48+8], eax
0x1406600ab  test    rsi, rsi
0x1406600ae  jz      short loc_140660114
0x1406600b0  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406600b7  jnz     short loc_1406600C8
0x1406600b9  xor     dil, dil
0x1406600bc  test    cs:VfOptionFlags, 800h
0x1406600c6  jz      short loc_1406600DB
0x1406600c8  lea     rcx, DifRebootlessRundown; RunRef
0x1406600cf  call    ExAcquireRundownProtection_0
0x1406600d4  mov     dil, al
0x1406600d7  test    al, al
0x1406600d9  jz      short loc_140660114
0x1406600db  add     rsi, 30h ; '0'
0x1406600df  mov     rbx, [rsi]
0x1406600e2  jmp     short loc_1406600FE
0x1406600e4  lea     rax, [rbx-10h]
0x1406600e8  test    rax, rax
0x1406600eb  jz      short loc_1406600FB
0x1406600ed  mov     rax, [rax+8]
0x1406600f1  lea     rcx, [rsp+78h+var_58]
0x1406600f6  call    _guard_dispatch_icall_no_overrides
0x1406600fb  mov     rbx, [rbx]
0x1406600fe  cmp     rbx, rsi
0x140660101  jnz     short loc_1406600E4
0x140660103  test    dil, dil
0x140660106  jz      short loc_140660114
0x140660108  lea     rcx, DifRebootlessRundown; RunRef
0x14066010f  call    ExReleaseRundownProtection_0
0x140660114  mov     eax, dword ptr [rsp+78h+var_48+8]
0x140660118  add     rsp, 48h
0x14066011c  pop     r15
0x14066011e  pop     r14
0x140660120  pop     rdi
0x140660121  pop     rsi
0x140660122  pop     rbp
0x140660123  pop     rbx
0x140660124  retn
```
