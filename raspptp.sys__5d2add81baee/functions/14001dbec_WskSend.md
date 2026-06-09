# WskSend

- ea: `0x14001dbec`
- end: `0x14001dd8d`
- name: `WskSend`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013164`

## callees

- `0x140007710`
- `0x14001dbec`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dcd6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001dcd6`
- `ntoskrnl!IoFreeIrp` at `0x14001dc94`
- `ntoskrnl!IoFreeIrp` at `0x14001dc94`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001dcea`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001dcea`
- `ntoskrnl!IoAllocateMdl` at `0x14001dc7d`
- `ntoskrnl!IoAllocateMdl` at `0x14001dc7d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001dc50`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001dc50`
- `ntoskrnl!IoAllocateIrp` at `0x14001dc35`
- `ntoskrnl!IoAllocateIrp` at `0x14001dc35`

## pseudocode

```c
__int64 __fastcall WskSend(__int64 a1, __int64 a2, __int64 a3, void *a4, ULONG Length)
{
  _QWORD *v8; // rdi
  __int64 v9; // r15
  PIRP Irp; // rsi
  struct _MDL *Mdl; // rax
  struct _MDL *v12; // r14
  unsigned int v13; // esi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int128 v15; // [rsp+40h] [rbp-58h] BYREF
  __int64 v16; // [rsp+50h] [rbp-48h]

  v15 = 0;
  v16 = 0;
  if ( !*(_QWORD *)(a1 + 64) )
    return 3221225485LL;
  v8 = 0;
  if ( (*(_DWORD *)(a1 + 392) & 0x20) == 0 )
    goto LABEL_8;
  v9 = *(_QWORD *)(a1 + 384);
  Irp = IoAllocateIrp(1, 0);
  if ( !Irp )
    goto LABEL_8;
  v8 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256));
  if ( !v8 || (Mdl = IoAllocateMdl(a4, Length, 0, 0, 0), (v12 = Mdl) == 0) )
  {
    IoFreeIrp(Irp);
LABEL_8:
    v13 = -1073741670;
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, void *, int))(a1 + 64))(
      *(_QWORD *)(a1 + 8),
      0,
      0,
      0,
      a4,
      -1073741670);
    if ( v8 )
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256), v8);
    return v13;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  *v8 = a1;
  v8[4] = a4;
  v8[1] = 0;
  v8[2] = 0;
  v8[7] = v12;
  *((_DWORD *)v8 + 6) = 0;
  v8[5] = 0;
  *((_DWORD *)v8 + 12) = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskSendCompletion;
  CurrentStackLocation[-1].Context = v8;
  CurrentStackLocation[-1].Control = -32;
  v16 = Length;
  *(_QWORD *)&v15 = v12;
  DWORD2(v15) = 0;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
  return (*(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD, PIRP))(*(_QWORD *)v9 + 48LL))(v9, &v15, 0, Irp);
}

```

## disassembly

```asm
0x14001dbec  push    rbx
0x14001dbee  push    rbp
0x14001dbef  push    rsi
0x14001dbf0  push    rdi
0x14001dbf1  push    r14
0x14001dbf3  push    r15
0x14001dbf5  sub     rsp, 68h
0x14001dbf9  xor     eax, eax
0x14001dbfb  xorps   xmm0, xmm0
0x14001dbfe  mov     rbp, r9
0x14001dc01  mov     rbx, rcx
0x14001dc04  movups  [rsp+98h+var_58], xmm0
0x14001dc09  mov     [rsp+98h+var_48], rax
0x14001dc0e  cmp     [rcx+40h], rax
0x14001dc12  jnz     short loc_14001DC1E
0x14001dc14  mov     eax, 0C000000Dh
0x14001dc19  jmp     loc_14001DD7F
0x14001dc1e  mov     eax, [rcx+188h]
0x14001dc24  xor     edi, edi
0x14001dc26  test    al, 20h
0x14001dc28  jz      short loc_14001DCA0
0x14001dc2a  mov     r15, [rcx+180h]
0x14001dc31  xor     edx, edx; ChargeQuota
0x14001dc33  mov     cl, 1; StackSize
0x14001dc35  call    cs:__imp_IoAllocateIrp
0x14001dc3c  nop     dword ptr [rax+rax+00h]
0x14001dc41  mov     rsi, rax
0x14001dc44  test    rax, rax
0x14001dc47  jz      short loc_14001DCA0
0x14001dc49  lea     rcx, [rbx+100h]; Lookaside
0x14001dc50  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001dc57  nop     dword ptr [rax+rax+00h]
0x14001dc5c  mov     rdi, rax
0x14001dc5f  test    rax, rax
0x14001dc62  jz      short loc_14001DC91
0x14001dc64  mov     edx, [rsp+98h+Length]; Length
0x14001dc6b  xor     r9d, r9d; ChargeQuota
0x14001dc6e  xor     r8d, r8d; SecondaryBuffer
0x14001dc71  mov     [rsp+98h+Irp], 0; Irp
0x14001dc7a  mov     rcx, rbp; VirtualAddress
0x14001dc7d  call    cs:__imp_IoAllocateMdl
0x14001dc84  nop     dword ptr [rax+rax+00h]
0x14001dc89  mov     r14, rax
0x14001dc8c  test    rax, rax
0x14001dc8f  jnz     short loc_14001DCE7
0x14001dc91  mov     rcx, rsi; Irp
0x14001dc94  call    cs:__imp_IoFreeIrp
0x14001dc9b  nop     dword ptr [rax+rax+00h]
0x14001dca0  mov     rax, [rbx+40h]
0x14001dca4  mov     esi, 0C000009Ah
0x14001dca9  mov     rcx, [rbx+8]
0x14001dcad  xor     r9d, r9d
0x14001dcb0  mov     [rsp+98h+var_70], esi
0x14001dcb4  xor     r8d, r8d
0x14001dcb7  xor     edx, edx
0x14001dcb9  mov     [rsp+98h+Irp], rbp
0x14001dcbe  call    _guard_dispatch_icall
0x14001dcc3  test    rdi, rdi
0x14001dcc6  jz      loc_14001DD7D
0x14001dccc  lea     rcx, [rbx+100h]; Lookaside
0x14001dcd3  mov     rdx, rdi; Entry
0x14001dcd6  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001dcdd  nop     dword ptr [rax+rax+00h]
0x14001dce2  jmp     loc_14001DD7D
0x14001dce7  mov     rcx, r14; MemoryDescriptorList
0x14001dcea  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001dcf1  nop     dword ptr [rax+rax+00h]
0x14001dcf6  mov     [rdi], rbx
0x14001dcf9  lea     rcx, WskSendCompletion
0x14001dd00  mov     [rdi+20h], rbp
0x14001dd04  mov     qword ptr [rdi+8], 0
0x14001dd0c  mov     qword ptr [rdi+10h], 0
0x14001dd14  mov     [rdi+38h], r14
0x14001dd18  mov     dword ptr [rdi+18h], 0
0x14001dd1f  mov     qword ptr [rdi+28h], 0
0x14001dd27  mov     dword ptr [rdi+30h], 0
0x14001dd2e  mov     rax, [rsi+0B8h]
0x14001dd35  mov     [rax-10h], rcx
0x14001dd39  mov     [rax-8], rdi
0x14001dd3d  mov     byte ptr [rax-45h], 0E0h
0x14001dd41  mov     eax, [rsp+98h+Length]
0x14001dd48  mov     [rsp+98h+var_48], rax
0x14001dd4d  mov     qword ptr [rsp+98h+var_58], r14
0x14001dd52  mov     dword ptr [rsp+98h+var_58+8], 0
0x14001dd5a  lock inc dword ptr [rbx+200h]
0x14001dd61  mov     rax, [r15]
0x14001dd64  lea     rdx, [rsp+98h+var_58]
0x14001dd69  mov     r9, rsi
0x14001dd6c  xor     r8d, r8d
0x14001dd6f  mov     rcx, r15
0x14001dd72  mov     rax, [rax+30h]
0x14001dd76  call    _guard_dispatch_icall
0x14001dd7b  mov     esi, eax
0x14001dd7d  mov     eax, esi
0x14001dd7f  add     rsp, 68h
0x14001dd83  pop     r15
0x14001dd85  pop     r14
0x14001dd87  pop     rdi
0x14001dd88  pop     rsi
0x14001dd89  pop     rbp
0x14001dd8a  pop     rbx
0x14001dd8b  retn
```
