# DifNtCreateTransactionManagerWrapper

- ea: `0x140659ce0`
- end: `0x140659e76`
- name: `DifNtCreateTransactionManagerWrapper`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x140659ce0`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransactionManager` at `0x140659dea`
- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransactionManager` at `0x140659dea`

## pseudocode

```c
__int64 __fastcall DifNtCreateTransactionManagerWrapper(
        HANDLE *a1,
        ACCESS_MASK a2,
        OBJECT_ATTRIBUTES *a3,
        UNICODE_STRING *a4,
        ULONG CreateOptions,
        ULONG CommitStrength)
{
  __int64 APIThunkContextById; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r14
  __int64 v14; // rcx
  BOOLEAN v15; // si
  _QWORD *i; // rbx
  __int64 v17; // rdx
  BOOLEAN v18; // di
  _QWORD *j; // rbx
  __int128 v21; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+40h] [rbp-38h]
  __int128 v23; // [rsp+50h] [rbp-28h]
  __int64 v24; // [rsp+60h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+B8h] [rbp+40h]

  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(530);
  v13 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v14 = *(unsigned int *)(APIThunkContextById + 12);
    if ( (v14 & 0x18) != 0 )
    {
      *(_QWORD *)&v21 = retaddr;
    }
    else if ( (v14 & 4) != 0 )
    {
      *(_QWORD *)&v21 = DifGetReturnAddressForWrappers(v14, v10, v11, v12);
    }
    *((_QWORD *)&v23 + 1) = a1;
    *((_QWORD *)&v21 + 1) = __PAIR64__(CreateOptions, CommitStrength);
    LODWORD(v23) = a2;
    *((_QWORD *)&v22 + 1) = a3;
    *(_QWORD *)&v22 = a4;
    if ( !VfDifRunningWithoutReboot && (v15 = 0, (VfOptionFlags & 0x800) == 0)
      || (v15 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v13 + 32); i != (_QWORD *)(v13 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v21, v10);
      }
      if ( v15 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v24) = NtCreateTransactionManager(a1, a2, a3, a4, CreateOptions, CommitStrength);
  if ( v13 )
  {
    if ( !VfDifRunningWithoutReboot && (v18 = 0, (VfOptionFlags & 0x800) == 0)
      || (v18 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v13 + 48); j != (_QWORD *)(v13 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v21, v17);
      }
      if ( v18 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x140659ce0  mov     [rsp-40h+TmHandle], rcx
0x140659ce5  push    rbp
0x140659ce6  push    rbx
0x140659ce7  push    rsi
0x140659ce8  push    rdi
0x140659ce9  push    r12
0x140659ceb  push    r13
0x140659ced  push    r14
0x140659cef  push    r15
0x140659cf1  mov     rbp, rsp
0x140659cf4  sub     rsp, 78h
0x140659cf8  xorps   xmm0, xmm0
0x140659cfb  xor     eax, eax
0x140659cfd  mov     ecx, 212h
0x140659d02  mov     [rbp+var_18], rax
0x140659d06  movups  [rbp+var_48], xmm0
0x140659d0a  mov     r15, r9
0x140659d0d  mov     r12, r8
0x140659d10  movups  [rbp+var_38], xmm0
0x140659d14  mov     r13d, edx
0x140659d17  movups  [rbp+var_28], xmm0
0x140659d1b  call    DifGetAPIThunkContextById
0x140659d20  mov     r14, rax
0x140659d23  test    rax, rax
0x140659d26  jz      loc_140659DCF
0x140659d2c  mov     ecx, [rax+0Ch]
0x140659d2f  test    cl, 18h
0x140659d32  jz      short loc_140659D3E
0x140659d34  mov     rcx, [rbp+40h]
0x140659d38  mov     qword ptr [rbp+var_48], rcx
0x140659d3c  jmp     short loc_140659D4C
0x140659d3e  test    cl, 4
0x140659d41  jz      short loc_140659D4C
0x140659d43  call    DifGetReturnAddressForWrappers
0x140659d48  mov     qword ptr [rbp+var_48], rax
0x140659d4c  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659d53  mov     rax, [rbp+TmHandle]
0x140659d57  mov     qword ptr [rbp+var_28+8], rax
0x140659d5b  mov     eax, [rbp+arg_20]
0x140659d5e  mov     dword ptr [rbp+var_48+0Ch], eax
0x140659d61  mov     eax, [rbp+arg_28]
0x140659d64  mov     dword ptr [rbp+var_48+8], eax
0x140659d67  mov     dword ptr [rbp+var_28], r13d
0x140659d6b  mov     qword ptr [rbp+var_38+8], r12
0x140659d6f  mov     qword ptr [rbp+var_38], r15
0x140659d73  jnz     short loc_140659D84
0x140659d75  xor     sil, sil
0x140659d78  test    cs:VfOptionFlags, 800h
0x140659d82  jz      short loc_140659D97
0x140659d84  lea     rcx, DifRebootlessRundown; RunRef
0x140659d8b  call    ExAcquireRundownProtection_0
0x140659d90  mov     sil, al
0x140659d93  test    al, al
0x140659d95  jz      short loc_140659DCF
0x140659d97  lea     rdi, [r14+20h]
0x140659d9b  mov     rbx, [rdi]
0x140659d9e  jmp     short loc_140659DB9
0x140659da0  lea     rax, [rbx-10h]
0x140659da4  test    rax, rax
0x140659da7  jz      short loc_140659DB6
0x140659da9  mov     rax, [rax+8]
0x140659dad  lea     rcx, [rbp+var_48]
0x140659db1  call    _guard_dispatch_icall_no_overrides
0x140659db6  mov     rbx, [rbx]
0x140659db9  cmp     rbx, rdi
0x140659dbc  jnz     short loc_140659DA0
0x140659dbe  test    sil, sil
0x140659dc1  jz      short loc_140659DCF
0x140659dc3  lea     rcx, DifRebootlessRundown; RunRef
0x140659dca  call    ExReleaseRundownProtection_0
0x140659dcf  mov     eax, [rbp+arg_28]
0x140659dd2  mov     r9, r15; LogFileName
0x140659dd5  mov     rcx, [rbp+TmHandle]; TmHandle
0x140659dd9  mov     r8, r12; ObjectAttributes
0x140659ddc  mov     [rsp+78h+CommitStrength], eax; CommitStrength
0x140659de0  mov     edx, r13d; DesiredAccess
0x140659de3  mov     eax, [rbp+arg_20]
0x140659de6  mov     [rsp+78h+CreateOptions], eax; CreateOptions
0x140659dea  call    cs:__imp_NtCreateTransactionManager
0x140659df1  nop     dword ptr [rax+rax+00h]
0x140659df6  mov     dword ptr [rbp+var_18], eax
0x140659df9  test    r14, r14
0x140659dfc  jz      short loc_140659E61
0x140659dfe  cmp     cs:VfDifRunningWithoutReboot, 0
0x140659e05  jnz     short loc_140659E16
0x140659e07  xor     dil, dil
0x140659e0a  test    cs:VfOptionFlags, 800h
0x140659e14  jz      short loc_140659E29
0x140659e16  lea     rcx, DifRebootlessRundown; RunRef
0x140659e1d  call    ExAcquireRundownProtection_0
0x140659e22  mov     dil, al
0x140659e25  test    al, al
0x140659e27  jz      short loc_140659E61
0x140659e29  lea     rsi, [r14+30h]
0x140659e2d  mov     rbx, [rsi]
0x140659e30  jmp     short loc_140659E4B
0x140659e32  lea     rax, [rbx-10h]
0x140659e36  test    rax, rax
0x140659e39  jz      short loc_140659E48
0x140659e3b  mov     rax, [rax+8]
0x140659e3f  lea     rcx, [rbp+var_48]
0x140659e43  call    _guard_dispatch_icall_no_overrides
0x140659e48  mov     rbx, [rbx]
0x140659e4b  cmp     rbx, rsi
0x140659e4e  jnz     short loc_140659E32
0x140659e50  test    dil, dil
0x140659e53  jz      short loc_140659E61
0x140659e55  lea     rcx, DifRebootlessRundown; RunRef
0x140659e5c  call    ExReleaseRundownProtection_0
0x140659e61  mov     eax, dword ptr [rbp+var_18]
0x140659e64  add     rsp, 78h
0x140659e68  pop     r15
0x140659e6a  pop     r14
0x140659e6c  pop     r13
0x140659e6e  pop     r12
0x140659e70  pop     rdi
0x140659e71  pop     rsi
0x140659e72  pop     rbx
0x140659e73  pop     rbp
0x140659e74  retn
```
