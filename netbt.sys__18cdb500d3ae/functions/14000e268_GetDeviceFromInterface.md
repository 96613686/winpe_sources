# GetDeviceFromInterface

- ea: `0x14000e268`
- end: `0x14000e313`
- name: `GetDeviceFromInterface`
- size: `171`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000d594`
- `0x14000efd4`
- `0x14001f8d0`
- `0x140025430`
- `0x14002984c`
- `0x14002b9c8`
- `0x14002bb80`
- `0x14004f224`
- `0x14005006c`

## callees

- `0x14000dc40`
- `0x14000e268`
- `0x14000e31c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e2a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000e2a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e2ec`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000e2ec`

## pseudocode

```c
__int64 *__fastcall GetDeviceFromInterface(__int64 a1, __int64 a2, char a3)
{
  KIRQL v5; // di
  __int64 *v6; // rcx
  __int64 *v7; // rbx
  int v8; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  if ( (int)NbtGetOutgoingInterfaceForSend(a1, a2, &v8) < 0 )
    return 0;
  v5 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v6 = &NbtConfig;
  do
  {
    v6 = (__int64 *)*v6;
    if ( v6 == &NbtConfig )
    {
      v7 = 0;
      goto LABEL_8;
    }
    v7 = v6 - 43;
  }
  while ( *((_DWORD *)v6 + 89) != v8 );
  if ( a3 )
    NBT_REFERENCE_DEVICE((__int64)(v6 - 43), 0xAu, 1);
LABEL_8:
  KeReleaseSpinLock(&SpinLock, v5);
  return v7;
}

```

## disassembly

```asm
0x14000e268  mov     rax, rsp
0x14000e26b  mov     [rax+8], rbx
0x14000e26f  mov     [rax+10h], rsi
0x14000e273  push    rdi
0x14000e274  sub     rsp, 20h
0x14000e278  mov     sil, r8b
0x14000e27b  mov     dword ptr [rax+20h], 0
0x14000e282  lea     r8, [rax+20h]
0x14000e286  call    NbtGetOutgoingInterfaceForSend
0x14000e28b  test    eax, eax
0x14000e28d  jns     short loc_14000E2A2
0x14000e28f  xor     eax, eax
0x14000e291  mov     rbx, [rsp+28h+arg_0]
0x14000e296  mov     rsi, [rsp+28h+arg_8]
0x14000e29b  add     rsp, 20h
0x14000e29f  pop     rdi
0x14000e2a0  retn
0x14000e2a2  lea     rcx, SpinLock; SpinLock
0x14000e2a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000e2b0  nop     dword ptr [rax+rax+00h]
0x14000e2b5  mov     edx, [rsp+28h+arg_18]
0x14000e2b9  mov     dil, al
0x14000e2bc  lea     rax, NbtConfig
0x14000e2c3  mov     rcx, rax
0x14000e2c6  mov     rcx, [rcx]
0x14000e2c9  cmp     rcx, rax
0x14000e2cc  jz      short loc_14000E2FD
0x14000e2ce  lea     rbx, [rcx-158h]
0x14000e2d5  cmp     [rbx+2BCh], edx
0x14000e2db  jnz     short loc_14000E2C6
0x14000e2dd  test    sil, sil
0x14000e2e0  jnz     short loc_14000E301
0x14000e2e2  mov     dl, dil; NewIrql
0x14000e2e5  lea     rcx, SpinLock; SpinLock
0x14000e2ec  call    cs:__imp_KeReleaseSpinLock
0x14000e2f3  nop     dword ptr [rax+rax+00h]
0x14000e2f8  mov     rax, rbx
0x14000e2fb  jmp     short loc_14000E291
0x14000e2fd  xor     ebx, ebx
0x14000e2ff  jmp     short loc_14000E2E2
0x14000e301  mov     r8b, 1
0x14000e304  mov     edx, 0Ah
0x14000e309  mov     rcx, rbx
0x14000e30c  call    NBT_REFERENCE_DEVICE
0x14000e311  jmp     short loc_14000E2E2
```
