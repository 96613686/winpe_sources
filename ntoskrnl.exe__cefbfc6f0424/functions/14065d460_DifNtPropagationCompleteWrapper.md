# DifNtPropagationCompleteWrapper

- ea: `0x14065d460`
- end: `0x14065d5d8`
- name: `DifNtPropagationCompleteWrapper`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1402a3fe0`
- `0x1402a5f60`
- `0x1402c0554`
- `0x1402c0584`
- `0x14065d460`
- `0x1406eb0e0`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPropagationComplete` at `0x14065d54c`
- `ext-ms-win-ntos-tm-l1-1-0!NtPropagationComplete` at `0x14065d54c`

## pseudocode

```c
__int64 __fastcall DifNtPropagationCompleteWrapper(void *a1, ULONG a2, ULONG a3, void *a4)
{
  __int64 APIThunkContextById; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r14
  __int64 v12; // rcx
  BOOLEAN v13; // si
  _QWORD *i; // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  BOOLEAN v18; // di
  _QWORD *j; // rbx
  __int128 v21; // [rsp+20h] [rbp-38h] BYREF
  __int128 v22; // [rsp+30h] [rbp-28h]
  __int64 v23; // [rsp+40h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+40h]

  v23 = 0;
  v21 = 0;
  v22 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(557);
  v11 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v12 = *(unsigned int *)(APIThunkContextById + 12);
    if ( (v12 & 0x18) != 0 )
    {
      *(_QWORD *)&v21 = retaddr;
    }
    else if ( (v12 & 4) != 0 )
    {
      *(_QWORD *)&v21 = DifGetReturnAddressForWrappers(v12, v8, v9, v10);
    }
    *((_QWORD *)&v22 + 1) = a1;
    *(_QWORD *)&v22 = __PAIR64__(a2, a3);
    *((_QWORD *)&v21 + 1) = a4;
    if ( !VfDifRunningWithoutReboot && (v13 = 0, (VfOptionFlags & 0x800) == 0)
      || (v13 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v11 + 32); i != (_QWORD *)(v11 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v21, v8, v9, v10);
      }
      if ( v13 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v23) = NtPropagationComplete(a1, a2, a3, a4);
  if ( v11 )
  {
    if ( !VfDifRunningWithoutReboot && (v18 = 0, (VfOptionFlags & 0x800) == 0)
      || (v18 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v11 + 48); j != (_QWORD *)(v11 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v21, v15, v16, v17);
      }
      if ( v18 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14065d460  mov     [rsp-40h+ResourceManagerHandle], rcx
0x14065d465  push    rbp
0x14065d466  push    rbx
0x14065d467  push    rsi
0x14065d468  push    rdi
0x14065d469  push    r12
0x14065d46b  push    r13
0x14065d46d  push    r14
0x14065d46f  push    r15
0x14065d471  mov     rbp, rsp
0x14065d474  sub     rsp, 58h
0x14065d478  xorps   xmm0, xmm0
0x14065d47b  xor     eax, eax
0x14065d47d  mov     ecx, 22Dh
0x14065d482  mov     [rbp+var_18], rax
0x14065d486  movups  [rbp+var_38], xmm0
0x14065d48a  mov     r15, r9
0x14065d48d  mov     r12d, r8d
0x14065d490  movups  [rbp+var_28], xmm0
0x14065d494  mov     r13d, edx
0x14065d497  call    DifGetAPIThunkContextById
0x14065d49c  mov     r14, rax
0x14065d49f  test    rax, rax
0x14065d4a2  jz      loc_14065D53F
0x14065d4a8  mov     ecx, [rax+0Ch]
0x14065d4ab  test    cl, 18h
0x14065d4ae  jz      short loc_14065D4BA
0x14065d4b0  mov     rcx, [rbp+40h]
0x14065d4b4  mov     qword ptr [rbp+var_38], rcx
0x14065d4b8  jmp     short loc_14065D4C8
0x14065d4ba  test    cl, 4
0x14065d4bd  jz      short loc_14065D4C8
0x14065d4bf  call    DifGetReturnAddressForWrappers
0x14065d4c4  mov     qword ptr [rbp+var_38], rax
0x14065d4c8  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065d4cf  mov     rax, [rbp+ResourceManagerHandle]
0x14065d4d3  mov     qword ptr [rbp+var_28+8], rax
0x14065d4d7  mov     dword ptr [rbp+var_28+4], r13d
0x14065d4db  mov     dword ptr [rbp+var_28], r12d
0x14065d4df  mov     qword ptr [rbp+var_38+8], r15
0x14065d4e3  jnz     short loc_14065D4F4
0x14065d4e5  xor     sil, sil
0x14065d4e8  test    cs:VfOptionFlags, 800h
0x14065d4f2  jz      short loc_14065D507
0x14065d4f4  lea     rcx, DifRebootlessRundown; RunRef
0x14065d4fb  call    ExAcquireRundownProtection_0
0x14065d500  mov     sil, al
0x14065d503  test    al, al
0x14065d505  jz      short loc_14065D53F
0x14065d507  lea     rdi, [r14+20h]
0x14065d50b  mov     rbx, [rdi]
0x14065d50e  jmp     short loc_14065D529
0x14065d510  lea     rax, [rbx-10h]
0x14065d514  test    rax, rax
0x14065d517  jz      short loc_14065D526
0x14065d519  mov     rax, [rax+8]
0x14065d51d  lea     rcx, [rbp+var_38]
0x14065d521  call    _guard_dispatch_icall_no_overrides
0x14065d526  mov     rbx, [rbx]
0x14065d529  cmp     rbx, rdi
0x14065d52c  jnz     short loc_14065D510
0x14065d52e  test    sil, sil
0x14065d531  jz      short loc_14065D53F
0x14065d533  lea     rcx, DifRebootlessRundown; RunRef
0x14065d53a  call    ExReleaseRundownProtection_0
0x14065d53f  mov     rcx, [rbp+ResourceManagerHandle]; ResourceManagerHandle
0x14065d543  mov     r9, r15; Buffer
0x14065d546  mov     r8d, r12d; BufferLength
0x14065d549  mov     edx, r13d; RequestCookie
0x14065d54c  call    cs:__imp_NtPropagationComplete
0x14065d553  nop     dword ptr [rax+rax+00h]
0x14065d558  mov     dword ptr [rbp+var_18], eax
0x14065d55b  test    r14, r14
0x14065d55e  jz      short loc_14065D5C3
0x14065d560  cmp     cs:VfDifRunningWithoutReboot, 0
0x14065d567  jnz     short loc_14065D578
0x14065d569  xor     dil, dil
0x14065d56c  test    cs:VfOptionFlags, 800h
0x14065d576  jz      short loc_14065D58B
0x14065d578  lea     rcx, DifRebootlessRundown; RunRef
0x14065d57f  call    ExAcquireRundownProtection_0
0x14065d584  mov     dil, al
0x14065d587  test    al, al
0x14065d589  jz      short loc_14065D5C3
0x14065d58b  lea     rsi, [r14+30h]
0x14065d58f  mov     rbx, [rsi]
0x14065d592  jmp     short loc_14065D5AD
0x14065d594  lea     rax, [rbx-10h]
0x14065d598  test    rax, rax
0x14065d59b  jz      short loc_14065D5AA
0x14065d59d  mov     rax, [rax+8]
0x14065d5a1  lea     rcx, [rbp+var_38]
0x14065d5a5  call    _guard_dispatch_icall_no_overrides
0x14065d5aa  mov     rbx, [rbx]
0x14065d5ad  cmp     rbx, rsi
0x14065d5b0  jnz     short loc_14065D594
0x14065d5b2  test    dil, dil
0x14065d5b5  jz      short loc_14065D5C3
0x14065d5b7  lea     rcx, DifRebootlessRundown; RunRef
0x14065d5be  call    ExReleaseRundownProtection_0
0x14065d5c3  mov     eax, dword ptr [rbp+var_18]
0x14065d5c6  add     rsp, 58h
0x14065d5ca  pop     r15
0x14065d5cc  pop     r14
0x14065d5ce  pop     r13
0x14065d5d0  pop     r12
0x14065d5d2  pop     rdi
0x14065d5d3  pop     rsi
0x14065d5d4  pop     rbx
0x14065d5d5  pop     rbp
0x14065d5d6  retn
```
