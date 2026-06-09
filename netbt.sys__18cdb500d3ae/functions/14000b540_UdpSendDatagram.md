# UdpSendDatagram

- ea: `0x14000b540`
- end: `0x14000b7e2`
- name: `UdpSendDatagram`
- size: `674`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x140006a60`
- `0x14000a7b0`
- `0x14000ebe0`
- `0x1400167d4`
- `0x140016c14`
- `0x140017a3c`
- `0x14001d580`
- `0x140029570`
- `0x1400304c8`

## callees

- `0x140006900`
- `0x14000b540`
- `0x14000d070`
- `0x14000da94`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b571`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b571`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b6ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b61b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b6bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b70f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b771`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b61b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b6bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b70f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b771`

## pseudocode

```c
__int64 __fastcall UdpSendDatagram(
        __int64 a1,
        unsigned int a2,
        void (__fastcall *a3)(__int64, __int64, _QWORD),
        __int64 a4,
        __int16 a5,
        int a6)
{
  KIRQL v10; // al
  __int64 v11; // r10
  KIRQL v12; // r15
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // rcx
  unsigned int v17; // r9d
  unsigned int v18; // r12d
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int16 v21; // ax
  unsigned int v22; // ebx
  KIRQL v23; // al
  bool v24; // zf
  KIRQL v25; // si
  KIRQL v26; // dl
  _QWORD v27[13]; // [rsp+40h] [rbp-68h] BYREF
  int v28; // [rsp+B0h] [rbp+8h] BYREF

  v27[3] = 0;
  v28 = 0;
  v10 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v11 = *(_QWORD *)(a1 + 32);
  v12 = v10;
  if ( v11 && *(_DWORD *)(v11 + 360) == 1131832644 )
  {
    v13 = 0;
    v14 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 364));
    ++*(_DWORD *)(v11 + 1128);
    v15 = *(_QWORD *)(a1 + 32);
    if ( *(_DWORD *)(v15 + 488) )
    {
      v14 = *(_QWORD *)(v15 + 616);
      if ( v14 )
      {
        if ( a6 == 16 )
        {
          v13 = *(_QWORD *)(v14 + 24);
        }
        else if ( a6 == 32 )
        {
          v13 = *(_QWORD *)(v14 + 48);
        }
        if ( !a2 )
          a2 = *(_DWORD *)(v15 + 496);
        if ( a2 == 2130706432 )
        {
          v13 = 0;
        }
        else if ( v13 && a3 )
        {
LABEL_17:
          v17 = *(_DWORD *)(a1 + 56);
          v18 = v17 + *(_DWORD *)(a1 + 72);
          if ( v18 < v17 )
          {
            v22 = -1073741675;
            if ( a3 )
            {
              NBT_DEREFERENCE_DEVICE(*(_QWORD *)(a1 + 32), 0xBu, 1);
              KeReleaseSpinLock(&SpinLock, v12);
              a3(a4, 3221225621LL, 0);
              return v22;
            }
            v26 = v12;
          }
          else
          {
            v27[0] = v13;
            v19 = *(_QWORD *)(a1 + 120);
            v27[1] = a3;
            v27[2] = a4;
            v20 = *(_QWORD *)(v19 + 40);
            *(_DWORD *)(v19 + 32) = (unsigned __int16)word_1400395DE + 11;
            *(_DWORD *)v20 = 1;
            *(_WORD *)(v20 + 4) = word_1400395DE;
            v21 = a5;
            *(_WORD *)(v20 + 6) = 2;
            *(_DWORD *)(v20 + 10) = _byteswap_ulong(a2);
            *(_WORD *)(v20 + 8) = __ROR2__(v21, 8);
            ++*(_DWORD *)v14;
            KeReleaseSpinLock(&SpinLock, v12);
            v22 = TdiSendDatagram((unsigned int)v27, v19, v18, (unsigned int)&v28, a1);
            v23 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
            v24 = (*(_DWORD *)v14)-- == 1;
            v25 = v23;
            if ( v24 )
              NTQueueToWorkerThread(v14 + 56, (__int64)&DelayedNbtCloseFileHandles, 0, v14, 0, 0, 1, 64);
            v26 = v25;
          }
          KeReleaseSpinLock(&SpinLock, v26);
          return v22;
        }
      }
    }
    NBT_DEREFERENCE_DEVICE(v15, 0xBu, 1);
    if ( v13 )
      goto LABEL_17;
  }
  KeReleaseSpinLock(&SpinLock, v12);
  if ( a3 )
    a3(a4, 3221225473LL, 0);
  return 0;
}

```

## disassembly

```asm
0x14000b540  mov     rax, rsp
0x14000b543  push    rbx
0x14000b544  push    rbp
0x14000b545  push    rsi
0x14000b546  push    rdi
0x14000b547  push    r12
0x14000b549  push    r13
0x14000b54b  push    r14
0x14000b54d  push    r15
0x14000b54f  sub     rsp, 68h
0x14000b553  mov     rbp, rcx
0x14000b556  xor     r12d, r12d
0x14000b559  lea     rcx, SpinLock; SpinLock
0x14000b560  mov     [rax-50h], r12
0x14000b564  mov     [rax+8], r12d
0x14000b568  mov     r13, r9
0x14000b56b  mov     rsi, r8
0x14000b56e  mov     r14d, edx
0x14000b571  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b578  nop     dword ptr [rax+rax+00h]
0x14000b57d  mov     r10, [rbp+20h]
0x14000b581  mov     r15b, al
0x14000b584  test    r10, r10
0x14000b587  jz      loc_14000B611
0x14000b58d  cmp     dword ptr [r10+168h], 43766544h
0x14000b598  jnz     short loc_14000B611
0x14000b59a  mov     ebx, r12d
0x14000b59d  mov     edi, r12d
0x14000b5a0  lock inc dword ptr [r10+16Ch]
0x14000b5a8  inc     dword ptr [r10+468h]
0x14000b5af  mov     rcx, [rbp+20h]
0x14000b5b3  cmp     [rcx+1E8h], r12d
0x14000b5ba  jz      short loc_14000B5FF
0x14000b5bc  mov     rdi, [rcx+268h]
0x14000b5c3  test    rdi, rdi
0x14000b5c6  jz      short loc_14000B5FF
0x14000b5c8  cmp     [rsp+0A8h+arg_28], 10h
0x14000b5d0  jz      loc_14000B73A
0x14000b5d6  cmp     [rsp+0A8h+arg_28], 20h ; ' '
0x14000b5de  jz      loc_14000B743
0x14000b5e4  test    r14d, r14d
0x14000b5e7  jz      loc_14000B797
0x14000b5ed  cmp     r14d, 7F000000h
0x14000b5f4  jz      loc_14000B7A3
0x14000b5fa  test    rbx, rbx
0x14000b5fd  jnz     short loc_14000B644
0x14000b5ff  mov     r8b, 1
0x14000b602  mov     edx, 0Bh
0x14000b607  call    NBT_DEREFERENCE_DEVICE
0x14000b60c  test    rbx, rbx
0x14000b60f  jnz     short loc_14000B649
0x14000b611  mov     dl, r15b; NewIrql
0x14000b614  lea     rcx, SpinLock; SpinLock
0x14000b61b  call    cs:__imp_KeReleaseSpinLock
0x14000b622  nop     dword ptr [rax+rax+00h]
0x14000b627  test    rsi, rsi
0x14000b62a  jnz     loc_14000B722
0x14000b630  xor     eax, eax
0x14000b632  add     rsp, 68h
0x14000b636  pop     r15
0x14000b638  pop     r14
0x14000b63a  pop     r13
0x14000b63c  pop     r12
0x14000b63e  pop     rdi
0x14000b63f  pop     rsi
0x14000b640  pop     rbp
0x14000b641  pop     rbx
0x14000b642  retn
0x14000b644  test    rsi, rsi
0x14000b647  jz      short loc_14000B5FF
0x14000b649  mov     r9d, [rbp+38h]
0x14000b64d  mov     r12d, [rbp+48h]
0x14000b651  add     r12d, r9d
0x14000b654  cmp     r12d, r9d
0x14000b657  jb      loc_14000B74C
0x14000b65d  movzx   eax, cs:word_1400395DE
0x14000b664  mov     dl, r15b; NewIrql
0x14000b667  add     eax, 0Bh
0x14000b66a  mov     [rsp+0A8h+var_68], rbx
0x14000b66f  mov     rbx, [rbp+78h]
0x14000b673  bswap   r14d
0x14000b676  mov     [rsp+0A8h+var_60], rsi
0x14000b67b  mov     [rsp+0A8h+var_58], r13
0x14000b680  mov     rcx, [rbx+28h]
0x14000b684  mov     [rbx+20h], eax
0x14000b687  mov     dword ptr [rcx], 1
0x14000b68d  movzx   eax, cs:word_1400395DE
0x14000b694  mov     [rcx+4], ax
0x14000b698  movzx   eax, [rsp+0A8h+arg_20]
0x14000b6a0  mov     word ptr [rcx+6], 2
0x14000b6a6  mov     [rcx+0Ah], r14d
0x14000b6aa  ror     ax, 8
0x14000b6ae  mov     [rcx+8], ax
0x14000b6b2  lea     rcx, SpinLock; SpinLock
0x14000b6b9  inc     dword ptr [rdi]
0x14000b6bb  call    cs:__imp_KeReleaseSpinLock
0x14000b6c2  nop     dword ptr [rax+rax+00h]
0x14000b6c7  lea     r9, [rsp+0A8h+arg_0]
0x14000b6cf  mov     [rsp+0A8h+var_88], rbp
0x14000b6d4  mov     r8d, r12d
0x14000b6d7  lea     rcx, [rsp+0A8h+var_68]
0x14000b6dc  mov     rdx, rbx
0x14000b6df  call    TdiSendDatagram
0x14000b6e4  lea     rcx, SpinLock; SpinLock
0x14000b6eb  mov     ebx, eax
0x14000b6ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b6f4  nop     dword ptr [rax+rax+00h]
0x14000b6f9  add     dword ptr [rdi], 0FFFFFFFFh
0x14000b6fc  mov     sil, al
0x14000b6ff  jz      loc_14000B7AB
0x14000b705  mov     dl, sil; NewIrql
0x14000b708  lea     rcx, SpinLock; SpinLock
0x14000b70f  call    cs:__imp_KeReleaseSpinLock
0x14000b716  nop     dword ptr [rax+rax+00h]
0x14000b71b  mov     eax, ebx
0x14000b71d  jmp     loc_14000B632
0x14000b722  xor     r8d, r8d
0x14000b725  mov     edx, 0C0000001h
0x14000b72a  mov     rcx, r13
0x14000b72d  mov     rax, rsi
0x14000b730  call    _guard_dispatch_icall
0x14000b735  jmp     loc_14000B630
0x14000b73a  mov     rbx, [rdi+18h]
0x14000b73e  jmp     loc_14000B5E4
0x14000b743  mov     rbx, [rdi+30h]
0x14000b747  jmp     loc_14000B5E4
0x14000b74c  mov     ebx, 0C0000095h
0x14000b751  test    rsi, rsi
0x14000b754  jz      short loc_14000B78F
0x14000b756  mov     rcx, [rbp+20h]
0x14000b75a  mov     r8b, 1
0x14000b75d  mov     edx, 0Bh
0x14000b762  call    NBT_DEREFERENCE_DEVICE
0x14000b767  mov     dl, r15b; NewIrql
0x14000b76a  lea     rcx, SpinLock; SpinLock
0x14000b771  call    cs:__imp_KeReleaseSpinLock
0x14000b778  nop     dword ptr [rax+rax+00h]
0x14000b77d  xor     r8d, r8d
0x14000b780  mov     edx, ebx
0x14000b782  mov     rcx, r13
0x14000b785  mov     rax, rsi
0x14000b788  call    _guard_dispatch_icall
0x14000b78d  jmp     short loc_14000B71B
0x14000b78f  mov     dl, r15b
0x14000b792  jmp     loc_14000B708
0x14000b797  mov     r14d, [rcx+1F0h]
0x14000b79e  jmp     loc_14000B5ED
0x14000b7a3  mov     rbx, r12
0x14000b7a6  jmp     loc_14000B5FF
0x14000b7ab  mov     [rsp+0A8h+var_70], 40h ; '@'
0x14000b7b0  lea     rcx, [rdi+38h]
0x14000b7b4  mov     [rsp+0A8h+var_78], 1
0x14000b7b9  lea     rdx, DelayedNbtCloseFileHandles
0x14000b7c0  mov     [rsp+0A8h+var_80], 0
0x14000b7c9  mov     r9, rdi
0x14000b7cc  xor     r8d, r8d
0x14000b7cf  mov     [rsp+0A8h+var_88], 0
0x14000b7d8  call    NTQueueToWorkerThread
0x14000b7dd  jmp     loc_14000B705
```
