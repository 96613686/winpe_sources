# VmbusTlCommonCancelConnection

- ea: `0x140001fa0`
- end: `0x1400020bb`
- name: `VmbusTlCommonCancelConnection`
- size: `283`
- prototype: `void __fastcall(KSPIN_LOCK *P, __int64, char)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000440c`
- `0x140006000`
- `0x140008c0c`
- `0x14000ab20`
- `0x14000b220`
- `0x140019110`
- `0x1400209c0`

## callees

- `0x140001fa0`
- `0x1400023b0`
- `0x140004898`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000200e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002080`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000200e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002080`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000203f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000209b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000203f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000209b`

## pseudocode

```c
void __fastcall VmbusTlCommonCancelConnection(KSPIN_LOCK *P, __int64 a2, char a3)
{
  KSPIN_LOCK v3; // rax
  int (*v7)(void); // rax
  char v8; // bl
  KIRQL v9; // al
  KIRQL v10; // bl

  v3 = P[92];
  if ( v3 && (v7 = *(int (**)(void))(v3 + 128)) != 0 && v7() >= 0 )
    v8 = 1;
  else
    v8 = VmbusTlConnectComplete(P);
  v9 = KeAcquireSpinLockRaiseToDpc(P + 9);
  if ( v8 )
    *((_DWORD *)P + 129) |= 0x100u;
  *((_DWORD *)P + 239) = v8 == 0 ? 0xC0000001 : 0;
  KeReleaseSpinLock(P + 9, v9);
  if ( a2 && *(_QWORD *)a2 )
    (*(void (__fastcall **)(_QWORD, _QWORD))a2)(*(_QWORD *)(a2 + 8), *((unsigned int *)P + 239));
  if ( v8 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(P[14] + 1208));
  }
  else if ( a3 )
  {
    v10 = KeAcquireSpinLockRaiseToDpc(P + 9);
    VmbusTlDisconnectAbort(P);
    KeReleaseSpinLock(P + 9, v10);
  }
}

```

## disassembly

```asm
0x140001fa0  mov     [rsp+arg_8], rbx
0x140001fa5  mov     [rsp+arg_10], rbp
0x140001faa  push    rsi
0x140001fab  push    rdi
0x140001fac  push    r14
0x140001fae  sub     rsp, 20h
0x140001fb2  mov     rax, [rcx+2E0h]
0x140001fb9  mov     bpl, r8b
0x140001fbc  mov     r14, rdx
0x140001fbf  mov     rdi, rcx
0x140001fc2  test    rax, rax
0x140001fc5  jz      short loc_140001FE0
0x140001fc7  mov     rax, [rax+80h]
0x140001fce  test    rax, rax
0x140001fd1  jz      short loc_140001FE0
0x140001fd3  call    _guard_dispatch_icall
0x140001fd8  test    eax, eax
0x140001fda  js      short loc_140001FE0
0x140001fdc  mov     bl, 1
0x140001fde  jmp     short loc_140002007
0x140001fe0  mov     eax, [rdi+204h]
0x140001fe6  lea     rdx, [rsp+38h+arg_0]
0x140001feb  and     al, 1
0x140001fed  mov     rcx, rdi; P
0x140001ff0  neg     al
0x140001ff2  sbb     eax, eax
0x140001ff4  and     eax, 0FFFFFF95h
0x140001ff7  add     eax, 0C0000120h
0x140001ffc  mov     [rsp+38h+arg_0], eax
0x140002000  call    VmbusTlConnectComplete
0x140002005  mov     bl, al
0x140002007  lea     rsi, [rdi+48h]
0x14000200b  mov     rcx, rsi; SpinLock
0x14000200e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002015  nop     dword ptr [rax+rax+00h]
0x14000201a  test    bl, bl
0x14000201c  jz      short loc_140002026
0x14000201e  bts     dword ptr [rdi+204h], 8
0x140002026  mov     cl, bl
0x140002028  neg     cl
0x14000202a  mov     rcx, rsi; SpinLock
0x14000202d  sbb     edx, edx
0x14000202f  not     edx
0x140002031  and     edx, 0C0000001h
0x140002037  mov     [rdi+3BCh], edx
0x14000203d  mov     dl, al; NewIrql
0x14000203f  call    cs:__imp_KeReleaseSpinLock
0x140002046  nop     dword ptr [rax+rax+00h]
0x14000204b  test    r14, r14
0x14000204e  jz      short loc_140002067
0x140002050  mov     rax, [r14]
0x140002053  test    rax, rax
0x140002056  jz      short loc_140002067
0x140002058  mov     edx, [rdi+3BCh]
0x14000205e  mov     rcx, [r14+8]
0x140002062  call    _guard_dispatch_icall
0x140002067  test    bl, bl
0x140002069  jz      short loc_140002078
0x14000206b  mov     rax, [rdi+70h]
0x14000206f  lock inc dword ptr [rax+4B8h]
0x140002076  jmp     short loc_1400020A7
0x140002078  test    bpl, bpl
0x14000207b  jz      short loc_1400020A7
0x14000207d  mov     rcx, rsi; SpinLock
0x140002080  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002087  nop     dword ptr [rax+rax+00h]
0x14000208c  mov     rcx, rdi
0x14000208f  mov     bl, al
0x140002091  call    VmbusTlDisconnectAbort
0x140002096  mov     dl, bl; NewIrql
0x140002098  mov     rcx, rsi; SpinLock
0x14000209b  call    cs:__imp_KeReleaseSpinLock
0x1400020a2  nop     dword ptr [rax+rax+00h]
0x1400020a7  mov     rbx, [rsp+38h+arg_8]
0x1400020ac  mov     rbp, [rsp+38h+arg_10]
0x1400020b1  add     rsp, 20h
0x1400020b5  pop     r14
0x1400020b7  pop     rdi
0x1400020b8  pop     rsi
0x1400020b9  retn
```
