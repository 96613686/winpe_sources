# WskSendDatagram

- ea: `0x14001e1e0`
- end: `0x14001e3e3`
- name: `WskSendDatagram`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017b50`

## callees

- `0x140007710`
- `0x14001e1e0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e3ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001e3ba`
- `ntoskrnl!IoFreeIrp` at `0x14001e3d2`
- `ntoskrnl!IoFreeIrp` at `0x14001e3d2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001e292`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001e292`
- `ntoskrnl!IoAllocateIrp` at `0x14001e273`
- `ntoskrnl!IoAllocateIrp` at `0x14001e273`

## pseudocode

```c
__int64 __fastcall WskSendDatagram(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, __int64 a7)
{
  PIRP Irp; // rsi
  void *v11; // rdi
  __int64 v12; // r14
  __int64 v13; // r13
  __int64 v14; // r12
  char *v15; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v17; // ebp
  __int128 v19; // [rsp+50h] [rbp-48h] BYREF
  __int64 v20; // [rsp+60h] [rbp-38h]
  int v21; // [rsp+C8h] [rbp+30h]

  v19 = 0;
  v20 = 0;
  if ( *(_QWORD *)(a1 + 64) )
  {
    Irp = 0;
    v11 = 0;
    v12 = *(_QWORD *)(a7 + 8);
    if ( (*(_DWORD *)(a1 + 392) & 0x20) != 0 )
    {
      if ( !a2 )
      {
        v17 = -1073741811;
LABEL_11:
        (*(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned int))(a1 + 64))(
          *(_QWORD *)(a1 + 8),
          a4,
          a5,
          0,
          v12,
          v17);
        if ( v11 )
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256), v11);
        if ( Irp )
          IoFreeIrp(Irp);
        return v17;
      }
      v13 = *(unsigned int *)(a7 + 24);
      v14 = *(_QWORD *)(a1 + 384);
      v21 = *(_DWORD *)(a7 + 16);
      Irp = IoAllocateIrp(1, 0);
      if ( Irp )
      {
        v15 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 256));
        v11 = v15;
        if ( v15 )
        {
          *((_DWORD *)v15 + 7) = 0;
          *(_QWORD *)(v15 + 52) = 0;
          *((_DWORD *)v15 + 15) = 0;
          *(_QWORD *)v15 = a1;
          *((_QWORD *)v15 + 4) = v12;
          *((_QWORD *)v15 + 1) = a4;
          *((_QWORD *)v15 + 2) = a5;
          *((_DWORD *)v15 + 6) = 0;
          *((_QWORD *)v15 + 5) = 0;
          *((_DWORD *)v15 + 12) = 0;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 512));
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskSendCompletion;
          CurrentStackLocation[-1].Context = v11;
          CurrentStackLocation[-1].Control = -32;
          DWORD2(v19) = v21;
          *(_QWORD *)&v19 = v12;
          v20 = v13;
          return (*(unsigned int (__fastcall **)(__int64, __int128 *, _QWORD, __int64, _DWORD, _QWORD, PIRP))(*(_QWORD *)v14 + 24LL))(
                   v14,
                   &v19,
                   0,
                   a2,
                   0,
                   0,
                   Irp);
        }
      }
    }
    v17 = -1073741670;
    goto LABEL_11;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14001e1e0  mov     r11, rsp
0x14001e1e3  push    rbx
0x14001e1e4  push    rbp
0x14001e1e5  push    r15
0x14001e1e7  sub     rsp, 80h
0x14001e1ee  xor     eax, eax
0x14001e1f0  mov     qword ptr [r11-50h], 10h
0x14001e1f8  xorps   xmm0, xmm0
0x14001e1fb  mov     r15, r9
0x14001e1fe  mov     rbp, rdx
0x14001e201  mov     rbx, rcx
0x14001e204  movups  [rsp+98h+var_48], xmm0
0x14001e209  mov     [r11-38h], rax
0x14001e20d  mov     qword ptr [r11-58h], 1
0x14001e215  cmp     [rcx+40h], rax
0x14001e219  jz      loc_14001E369
0x14001e21f  mov     rcx, [rsp+98h+arg_30]
0x14001e227  mov     eax, [rbx+188h]
0x14001e22d  mov     [r11+8], rsi
0x14001e231  xor     esi, esi
0x14001e233  mov     [r11+10h], rdi
0x14001e237  xor     edi, edi
0x14001e239  mov     [r11+18h], r12
0x14001e23d  mov     [r11-20h], r13
0x14001e241  mov     [r11-28h], r14
0x14001e245  mov     r14, [rcx+8]
0x14001e249  test    al, 20h
0x14001e24b  jz      loc_14001E382
0x14001e251  test    rdx, rdx
0x14001e254  jz      loc_14001E37B
0x14001e25a  mov     eax, [rcx+10h]
0x14001e25d  xor     edx, edx; ChargeQuota
0x14001e25f  mov     r13d, [rcx+18h]
0x14001e263  mov     cl, 1; StackSize
0x14001e265  mov     r12, [rbx+180h]
0x14001e26c  mov     [rsp+98h+arg_28], eax
0x14001e273  call    cs:__imp_IoAllocateIrp
0x14001e27a  nop     dword ptr [rax+rax+00h]
0x14001e27f  mov     rsi, rax
0x14001e282  test    rax, rax
0x14001e285  jz      loc_14001E382
0x14001e28b  lea     rcx, [rbx+100h]; Lookaside
0x14001e292  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001e299  nop     dword ptr [rax+rax+00h]
0x14001e29e  mov     rdi, rax
0x14001e2a1  test    rax, rax
0x14001e2a4  jz      loc_14001E382
0x14001e2aa  xor     edx, edx
0x14001e2ac  mov     [rax+1Ch], edx
0x14001e2af  mov     [rax+34h], rdx
0x14001e2b3  mov     [rax+3Ch], edx
0x14001e2b6  mov     [rax], rbx
0x14001e2b9  mov     [rax+20h], r14
0x14001e2bd  mov     [rax+8], r15
0x14001e2c1  mov     rax, [rsp+98h+arg_20]
0x14001e2c9  mov     [rdi+10h], rax
0x14001e2cd  mov     [rdi+18h], edx
0x14001e2d0  mov     [rdi+28h], rdx
0x14001e2d4  mov     [rdi+30h], edx
0x14001e2d7  lock inc dword ptr [rbx+200h]
0x14001e2de  mov     rax, [rsi+0B8h]
0x14001e2e5  lea     rcx, WskSendCompletion
0x14001e2ec  mov     [rsp+98h+var_68], rsi
0x14001e2f1  mov     r9, rbp
0x14001e2f4  mov     [rsp+98h+var_70], rdx
0x14001e2f9  xor     r8d, r8d
0x14001e2fc  mov     dword ptr [rsp+98h+var_78], edx
0x14001e300  lea     rdx, [rsp+98h+var_48]
0x14001e305  mov     [rax-10h], rcx
0x14001e309  mov     rcx, r12
0x14001e30c  mov     [rax-8], rdi
0x14001e310  mov     byte ptr [rax-45h], 0E0h
0x14001e314  mov     eax, [rsp+98h+arg_28]
0x14001e31b  mov     dword ptr [rsp+98h+var_48+8], eax
0x14001e31f  mov     qword ptr [rsp+98h+var_48], r14
0x14001e324  mov     [rsp+98h+var_38], r13
0x14001e329  mov     rax, [r12]
0x14001e32d  mov     rax, [rax+18h]
0x14001e331  call    _guard_dispatch_icall
0x14001e336  mov     ebp, eax
0x14001e338  mov     r14, [rsp+98h+var_28]
0x14001e33d  mov     eax, ebp
0x14001e33f  mov     r13, [rsp+98h+var_20]
0x14001e344  mov     r12, [rsp+98h+arg_10]
0x14001e34c  mov     rdi, [rsp+98h+arg_8]
0x14001e354  mov     rsi, [rsp+98h+arg_0]
0x14001e35c  add     rsp, 80h
0x14001e363  pop     r15
0x14001e365  pop     rbp
0x14001e366  pop     rbx
0x14001e367  retn
0x14001e369  mov     eax, 0C000000Dh
0x14001e36e  add     rsp, 80h
0x14001e375  pop     r15
0x14001e377  pop     rbp
0x14001e378  pop     rbx
0x14001e379  retn
0x14001e37b  mov     ebp, 0C000000Dh
0x14001e380  jmp     short loc_14001E387
0x14001e382  mov     ebp, 0C000009Ah
0x14001e387  mov     rax, [rbx+40h]
0x14001e38b  xor     r9d, r9d
0x14001e38e  mov     r8, [rsp+98h+arg_20]
0x14001e396  mov     rdx, r15
0x14001e399  mov     rcx, [rbx+8]
0x14001e39d  mov     dword ptr [rsp+98h+var_70], ebp
0x14001e3a1  mov     [rsp+98h+var_78], r14
0x14001e3a6  call    _guard_dispatch_icall
0x14001e3ab  test    rdi, rdi
0x14001e3ae  jz      short loc_14001E3C6
0x14001e3b0  lea     rcx, [rbx+100h]; Lookaside
0x14001e3b7  mov     rdx, rdi; Entry
0x14001e3ba  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001e3c1  nop     dword ptr [rax+rax+00h]
0x14001e3c6  test    rsi, rsi
0x14001e3c9  jz      loc_14001E338
0x14001e3cf  mov     rcx, rsi; Irp
0x14001e3d2  call    cs:__imp_IoFreeIrp
0x14001e3d9  nop     dword ptr [rax+rax+00h]
0x14001e3de  jmp     loc_14001E338
```
