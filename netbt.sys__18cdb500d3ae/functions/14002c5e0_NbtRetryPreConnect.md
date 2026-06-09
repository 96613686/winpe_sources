# NbtRetryPreConnect

- ea: `0x14002c5e0`
- end: `0x14002c703`
- name: `NbtRetryPreConnect`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140006900`
- `0x140007be8`
- `0x14000efd4`
- `0x14002c5e0`
- `0x140041a30`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002c6d8`
- `ntoskrnl!IofCompleteRequest` at `0x14002c6d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c657`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c6a8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c657`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c6a8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c671`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c6c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c671`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c6c4`

## pseudocode

```c
__int64 __fastcall NbtRetryPreConnect(unsigned __int8 a1, __int64 *a2, int a3)
{
  __int64 v3; // rbx
  __int64 v4; // r15
  __int64 v5; // r12
  IRP *v6; // rdi
  __int64 v8; // r14
  __int64 result; // rax
  KIRQL v10; // al
  int v11; // esi
  KIRQL v12; // al
  _OWORD v13[5]; // [rsp+40h] [rbp-58h] BYREF

  v3 = *a2;
  v4 = a2[1];
  v5 = a2[2];
  v6 = (IRP *)a2[3];
  memset(v13, 0, 32);
  v8 = *(_QWORD *)(v3 + 32);
  if ( (xmmword_140038420 & 0x80u) != 0LL )
    WPP_SF_dqdq(a1, (_DWORD)a2, a3, a1, (char)v6, v6->Cancel, v3);
  *(_QWORD *)&v13[0] = v3;
  result = NbtCancelCancelRoutine(v6);
  if ( (_DWORD)result != -1073741536 )
  {
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 248));
    *(_WORD *)(v3 + 265) = 256;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 248), v10);
    if ( a1 )
    {
      v11 = NbtConnectCommon(v13, v4, v5, v6);
      if ( v11 == 259 )
        return NBT_DEREFERENCE_DEVICE(v8, 13);
    }
    else
    {
      v11 = -1073741634;
    }
    v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 248));
    *(_QWORD *)(v3 + 152) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 248), v12);
    v6->IoStatus.Status = v11;
    IofCompleteRequest(v6, 0);
    return NBT_DEREFERENCE_DEVICE(v8, 13);
  }
  return result;
}

```

## disassembly

```asm
0x14002c5e0  push    rbx
0x14002c5e2  push    rbp
0x14002c5e3  push    rsi
0x14002c5e4  push    rdi
0x14002c5e5  push    r12
0x14002c5e7  push    r14
0x14002c5e9  push    r15
0x14002c5eb  sub     rsp, 60h
0x14002c5ef  mov     rbx, [rdx]
0x14002c5f2  xorps   xmm0, xmm0
0x14002c5f5  mov     r15, [rdx+8]
0x14002c5f9  mov     r12, [rdx+10h]
0x14002c5fd  mov     rdi, [rdx+18h]
0x14002c601  movups  [rsp+98h+var_58], xmm0
0x14002c606  movzx   esi, cl
0x14002c609  movups  [rsp+98h+var_48], xmm0
0x14002c60e  mov     r14, [rbx+20h]
0x14002c612  cmp     byte ptr cs:xmmword_140038420, 0
0x14002c619  jge     short loc_14002C635
0x14002c61b  movzx   eax, byte ptr [rdi+44h]
0x14002c61f  mov     r9d, esi
0x14002c622  mov     [rsp+98h+var_68], rbx
0x14002c627  mov     [rsp+98h+var_70], eax
0x14002c62b  mov     [rsp+98h+var_78], rdi
0x14002c630  call    WPP_SF_dqdq
0x14002c635  mov     rcx, rdi
0x14002c638  mov     qword ptr [rsp+98h+var_58], rbx
0x14002c63d  call    NbtCancelCancelRoutine
0x14002c642  cmp     eax, 0C0000120h
0x14002c647  jz      loc_14002C6F3
0x14002c64d  lea     rbp, [rbx+0F8h]
0x14002c654  mov     rcx, rbp; SpinLock
0x14002c657  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c65e  nop     dword ptr [rax+rax+00h]
0x14002c663  mov     rcx, rbp; SpinLock
0x14002c666  mov     word ptr [rbx+109h], 100h
0x14002c66f  mov     dl, al; NewIrql
0x14002c671  call    cs:__imp_KeReleaseSpinLock
0x14002c678  nop     dword ptr [rax+rax+00h]
0x14002c67d  test    sil, sil
0x14002c680  jz      short loc_14002C6A0
0x14002c682  mov     r9, rdi
0x14002c685  lea     rcx, [rsp+98h+var_58]
0x14002c68a  mov     r8, r12
0x14002c68d  mov     rdx, r15
0x14002c690  call    NbtConnectCommon
0x14002c695  mov     esi, eax
0x14002c697  cmp     eax, 103h
0x14002c69c  jz      short loc_14002C6E4
0x14002c69e  jmp     short loc_14002C6A5
0x14002c6a0  mov     esi, 0C00000BEh
0x14002c6a5  mov     rcx, rbp; SpinLock
0x14002c6a8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c6af  nop     dword ptr [rax+rax+00h]
0x14002c6b4  mov     rcx, rbp; SpinLock
0x14002c6b7  mov     qword ptr [rbx+98h], 0
0x14002c6c2  mov     dl, al; NewIrql
0x14002c6c4  call    cs:__imp_KeReleaseSpinLock
0x14002c6cb  nop     dword ptr [rax+rax+00h]
0x14002c6d0  xor     edx, edx; PriorityBoost
0x14002c6d2  mov     [rdi+30h], esi
0x14002c6d5  mov     rcx, rdi; Irp
0x14002c6d8  call    cs:__imp_IofCompleteRequest
0x14002c6df  nop     dword ptr [rax+rax+00h]
0x14002c6e4  xor     r8d, r8d
0x14002c6e7  mov     rcx, r14
0x14002c6ea  lea     edx, [r8+0Dh]
0x14002c6ee  call    NBT_DEREFERENCE_DEVICE
0x14002c6f3  add     rsp, 60h
0x14002c6f7  pop     r15
0x14002c6f9  pop     r14
0x14002c6fb  pop     r12
0x14002c6fd  pop     rdi
0x14002c6fe  pop     rsi
0x14002c6ff  pop     rbp
0x14002c700  pop     rbx
0x14002c701  retn
```
