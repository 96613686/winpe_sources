# DifNtPropagationCompleteWrapper

- ea: `0x140657970`
- end: `0x140657ae8`
- name: `DifNtPropagationCompleteWrapper`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140210ee0`
- `0x1402121a0`
- `0x1402b0d54`
- `0x1402b0d84`
- `0x140657970`
- `0x1406e8590`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPropagationComplete` at `0x140657a5c`
- `ext-ms-win-ntos-tm-l1-1-0!NtPropagationComplete` at `0x140657a5c`

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
  BOOLEAN v17; // di
  _QWORD *j; // rbx
  __int128 v20; // [rsp+20h] [rbp-38h] BYREF
  __int128 v21; // [rsp+30h] [rbp-28h]
  __int64 v22; // [rsp+40h] [rbp-18h]
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+40h]

  v22 = 0;
  v20 = 0;
  v21 = 0;
  APIThunkContextById = DifGetAPIThunkContextById(557);
  v11 = APIThunkContextById;
  if ( APIThunkContextById )
  {
    v12 = *(unsigned int *)(APIThunkContextById + 12);
    if ( (v12 & 0x18) != 0 )
    {
      *(_QWORD *)&v20 = retaddr;
    }
    else if ( (v12 & 4) != 0 )
    {
      *(_QWORD *)&v20 = DifGetReturnAddressForWrappers(v12, v8, v9, v10);
    }
    *((_QWORD *)&v21 + 1) = a1;
    *(_QWORD *)&v21 = __PAIR64__(a2, a3);
    *((_QWORD *)&v20 + 1) = a4;
    if ( !VfDifRunningWithoutReboot && (v13 = 0, (VfOptionFlags & 0x800) == 0)
      || (v13 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( i = *(_QWORD **)(v11 + 32); i != (_QWORD *)(v11 + 32); i = (_QWORD *)*i )
      {
        if ( i != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v20, v8, v9);
      }
      if ( v13 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  LODWORD(v22) = NtPropagationComplete(a1, a2, a3, a4);
  if ( v11 )
  {
    if ( !VfDifRunningWithoutReboot && (v17 = 0, (VfOptionFlags & 0x800) == 0)
      || (v17 = ExAcquireRundownProtection_0(&DifRebootlessRundown)) != 0 )
    {
      for ( j = *(_QWORD **)(v11 + 48); j != (_QWORD *)(v11 + 48); j = (_QWORD *)*j )
      {
        if ( j != (_QWORD *)16 )
          guard_dispatch_icall_no_overrides(&v20, v15, v16);
      }
      if ( v17 )
        ExReleaseRundownProtection_0(&DifRebootlessRundown);
    }
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140657970  mov     [rsp-40h+ResourceManagerHandle], rcx
0x140657975  push    rbp
0x140657976  push    rbx
0x140657977  push    rsi
0x140657978  push    rdi
0x140657979  push    r12
0x14065797b  push    r13
0x14065797d  push    r14
0x14065797f  push    r15
0x140657981  mov     rbp, rsp
0x140657984  sub     rsp, 58h
0x140657988  xorps   xmm0, xmm0
0x14065798b  xor     eax, eax
0x14065798d  mov     ecx, 22Dh
0x140657992  mov     [rbp+var_18], rax
0x140657996  movups  [rbp+var_38], xmm0
0x14065799a  mov     r15, r9
0x14065799d  mov     r12d, r8d
0x1406579a0  movups  [rbp+var_28], xmm0
0x1406579a4  mov     r13d, edx
0x1406579a7  call    DifGetAPIThunkContextById
0x1406579ac  mov     r14, rax
0x1406579af  test    rax, rax
0x1406579b2  jz      loc_140657A4F
0x1406579b8  mov     ecx, [rax+0Ch]
0x1406579bb  test    cl, 18h
0x1406579be  jz      short loc_1406579CA
0x1406579c0  mov     rcx, [rbp+40h]
0x1406579c4  mov     qword ptr [rbp+var_38], rcx
0x1406579c8  jmp     short loc_1406579D8
0x1406579ca  test    cl, 4
0x1406579cd  jz      short loc_1406579D8
0x1406579cf  call    DifGetReturnAddressForWrappers
0x1406579d4  mov     qword ptr [rbp+var_38], rax
0x1406579d8  cmp     cs:VfDifRunningWithoutReboot, 0
0x1406579df  mov     rax, [rbp+ResourceManagerHandle]
0x1406579e3  mov     qword ptr [rbp+var_28+8], rax
0x1406579e7  mov     dword ptr [rbp+var_28+4], r13d
0x1406579eb  mov     dword ptr [rbp+var_28], r12d
0x1406579ef  mov     qword ptr [rbp+var_38+8], r15
0x1406579f3  jnz     short loc_140657A04
0x1406579f5  xor     sil, sil
0x1406579f8  test    cs:VfOptionFlags, 800h
0x140657a02  jz      short loc_140657A17
0x140657a04  lea     rcx, DifRebootlessRundown; RunRef
0x140657a0b  call    ExAcquireRundownProtection_0
0x140657a10  mov     sil, al
0x140657a13  test    al, al
0x140657a15  jz      short loc_140657A4F
0x140657a17  lea     rdi, [r14+20h]
0x140657a1b  mov     rbx, [rdi]
0x140657a1e  jmp     short loc_140657A39
0x140657a20  lea     rax, [rbx-10h]
0x140657a24  test    rax, rax
0x140657a27  jz      short loc_140657A36
0x140657a29  mov     rax, [rax+8]
0x140657a2d  lea     rcx, [rbp+var_38]
0x140657a31  call    _guard_dispatch_icall_no_overrides
0x140657a36  mov     rbx, [rbx]
0x140657a39  cmp     rbx, rdi
0x140657a3c  jnz     short loc_140657A20
0x140657a3e  test    sil, sil
0x140657a41  jz      short loc_140657A4F
0x140657a43  lea     rcx, DifRebootlessRundown; RunRef
0x140657a4a  call    ExReleaseRundownProtection_0
0x140657a4f  mov     rcx, [rbp+ResourceManagerHandle]; ResourceManagerHandle
0x140657a53  mov     r9, r15; Buffer
0x140657a56  mov     r8d, r12d; BufferLength
0x140657a59  mov     edx, r13d; RequestCookie
0x140657a5c  call    cs:__imp_NtPropagationComplete
0x140657a63  nop     dword ptr [rax+rax+00h]
0x140657a68  mov     dword ptr [rbp+var_18], eax
0x140657a6b  test    r14, r14
0x140657a6e  jz      short loc_140657AD3
0x140657a70  cmp     cs:VfDifRunningWithoutReboot, 0
0x140657a77  jnz     short loc_140657A88
0x140657a79  xor     dil, dil
0x140657a7c  test    cs:VfOptionFlags, 800h
0x140657a86  jz      short loc_140657A9B
0x140657a88  lea     rcx, DifRebootlessRundown; RunRef
0x140657a8f  call    ExAcquireRundownProtection_0
0x140657a94  mov     dil, al
0x140657a97  test    al, al
0x140657a99  jz      short loc_140657AD3
0x140657a9b  lea     rsi, [r14+30h]
0x140657a9f  mov     rbx, [rsi]
0x140657aa2  jmp     short loc_140657ABD
0x140657aa4  lea     rax, [rbx-10h]
0x140657aa8  test    rax, rax
0x140657aab  jz      short loc_140657ABA
0x140657aad  mov     rax, [rax+8]
0x140657ab1  lea     rcx, [rbp+var_38]
0x140657ab5  call    _guard_dispatch_icall_no_overrides
0x140657aba  mov     rbx, [rbx]
0x140657abd  cmp     rbx, rsi
0x140657ac0  jnz     short loc_140657AA4
0x140657ac2  test    dil, dil
0x140657ac5  jz      short loc_140657AD3
0x140657ac7  lea     rcx, DifRebootlessRundown; RunRef
0x140657ace  call    ExReleaseRundownProtection_0
0x140657ad3  mov     eax, dword ptr [rbp+var_18]
0x140657ad6  add     rsp, 58h
0x140657ada  pop     r15
0x140657adc  pop     r14
0x140657ade  pop     r13
0x140657ae0  pop     r12
0x140657ae2  pop     rdi
0x140657ae3  pop     rsi
0x140657ae4  pop     rbx
0x140657ae5  pop     rbp
0x140657ae6  retn
```
