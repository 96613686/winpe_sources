# NbtCancelPreConnect

- ea: `0x14002c360`
- end: `0x14002c4ea`
- name: `NbtCancelPreConnect`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140006900`
- `0x14002c360`
- `0x140030f80`
- `0x140040590`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14002c44b`
- `ntoskrnl!KfRaiseIrql` at `0x14002c44b`
- `ntoskrnl!KeLowerIrql` at `0x14002c4bf`
- `ntoskrnl!KeLowerIrql` at `0x14002c4bf`
- `ntoskrnl!IofCompleteRequest` at `0x14002c4b0`
- `ntoskrnl!IofCompleteRequest` at `0x14002c4b0`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002c423`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002c4d2`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002c423`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002c4d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c483`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c483`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c49f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c49f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c434`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c434`
- `ntoskrnl!ExAllocatePool2` at `0x14002c3a7`
- `ntoskrnl!ExAllocatePool2` at `0x14002c3a7`

## pseudocode

```c
char __fastcall NbtCancelPreConnect(__int64 a1, __int64 a2)
{
  __int64 v3; // rbp
  char *Pool2; // rbx
  char v5; // di
  KIRQL v6; // al
  KIRQL v7; // di
  KIRQL v8; // al

  v3 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL) + 24LL);
  if ( v3
    && ((*(_DWORD *)(v3 + 16) - 829321027) & 0xFEFFFFFF) == 0
    && (Pool2 = (char *)ExAllocatePool2(64, 1028, 1098146382)) != 0 )
  {
    if ( (xmmword_140038420 & 0x80u) != 0LL )
      WPP_SF_qq(1031, 11, WPP_39f1e1c971f83cf429ccc88df75b8d05_Traceguids, a2, v3);
    *(_DWORD *)Pool2 = 2;
    *(_OWORD *)(Pool2 + 4) = *(_OWORD *)(v3 + 52);
    v5 = ((__int64 (__fastcall *)(__int64, char *, __int64 (__fastcall *)(int, int, int, int, __int64), __int64))qword_1400391F0)(
           1315075104,
           Pool2,
           NbtCancelAutoDialRequest,
           a2);
    if ( v5 )
      _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0);
    IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
    ExFreePoolWithTag(Pool2, 0);
    if ( v5 )
    {
      v6 = KfRaiseIrql(2u);
      *(_DWORD *)(a2 + 48) = -1073741536;
      *(_QWORD *)(a2 + 56) = 0;
      v7 = v6;
      NBT_DEREFERENCE_DEVICE(*(_QWORD *)(v3 + 32), 13);
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 248));
      *(_QWORD *)(v3 + 152) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 248), v8);
      IofCompleteRequest((PIRP)a2, 0);
      KeLowerIrql(v7);
      return 1;
    }
  }
  else
  {
    IoReleaseCancelSpinLock(*(_BYTE *)(a2 + 69));
  }
  return 0;
}

```

## disassembly

```asm
0x14002c360  push    rbx
0x14002c362  push    rbp
0x14002c363  push    rsi
0x14002c364  push    rdi
0x14002c365  sub     rsp, 38h
0x14002c369  mov     rax, [rdx+0B8h]
0x14002c370  mov     rsi, rdx
0x14002c373  mov     rcx, [rax+30h]
0x14002c377  mov     rbp, [rcx+18h]
0x14002c37b  test    rbp, rbp
0x14002c37e  jz      loc_14002C4CF
0x14002c384  mov     eax, [rbp+10h]
0x14002c387  sub     eax, 316E6F43h
0x14002c38c  test    eax, 0FEFFFFFFh
0x14002c391  jnz     loc_14002C4CF
0x14002c397  mov     edx, 404h
0x14002c39c  mov     ecx, 40h ; '@'
0x14002c3a1  mov     r8d, 4174624Eh
0x14002c3a7  call    cs:__imp_ExAllocatePool2
0x14002c3ae  nop     dword ptr [rax+rax+00h]
0x14002c3b3  mov     rbx, rax
0x14002c3b6  test    rax, rax
0x14002c3b9  jz      loc_14002C4CF
0x14002c3bf  cmp     byte ptr cs:xmmword_140038420, 0
0x14002c3c6  jge     short loc_14002C3E6
0x14002c3c8  mov     edx, 0Bh
0x14002c3cd  mov     [rsp+58h+var_38], rbp
0x14002c3d2  mov     ecx, 407h
0x14002c3d7  lea     r8, WPP_39f1e1c971f83cf429ccc88df75b8d05_Traceguids
0x14002c3de  mov     r9, rsi
0x14002c3e1  call    WPP_SF_qq
0x14002c3e6  mov     dword ptr [rbx], 2
0x14002c3ec  lea     r8, NbtCancelAutoDialRequest
0x14002c3f3  movups  xmm0, xmmword ptr [rbp+34h]
0x14002c3f7  mov     r9, rsi
0x14002c3fa  mov     rdx, rbx
0x14002c3fd  mov     ecx, 4E627420h
0x14002c402  movdqu  xmmword ptr [rbx+4], xmm0
0x14002c407  mov     rax, cs:qword_1400391F0
0x14002c40e  call    _guard_dispatch_icall
0x14002c413  mov     dil, al
0x14002c416  test    al, al
0x14002c418  jz      short loc_14002C420
0x14002c41a  xor     ecx, ecx
0x14002c41c  xchg    rcx, [rsi+68h]
0x14002c420  mov     cl, [rsi+45h]; Irql
0x14002c423  call    cs:__imp_IoReleaseCancelSpinLock
0x14002c42a  nop     dword ptr [rax+rax+00h]
0x14002c42f  xor     edx, edx; Tag
0x14002c431  mov     rcx, rbx; P
0x14002c434  call    cs:__imp_ExFreePoolWithTag
0x14002c43b  nop     dword ptr [rax+rax+00h]
0x14002c440  test    dil, dil
0x14002c443  jz      loc_14002C4DE
0x14002c449  mov     cl, 2; NewIrql
0x14002c44b  call    cs:__imp_KfRaiseIrql
0x14002c452  nop     dword ptr [rax+rax+00h]
0x14002c457  xor     r8d, r8d
0x14002c45a  mov     dword ptr [rsi+30h], 0C0000120h
0x14002c461  mov     qword ptr [rsi+38h], 0
0x14002c469  mov     dil, al
0x14002c46c  mov     rcx, [rbp+20h]
0x14002c470  lea     edx, [r8+0Dh]
0x14002c474  call    NBT_DEREFERENCE_DEVICE
0x14002c479  lea     rbx, [rbp+0F8h]
0x14002c480  mov     rcx, rbx; SpinLock
0x14002c483  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002c48a  nop     dword ptr [rax+rax+00h]
0x14002c48f  mov     rcx, rbx; SpinLock
0x14002c492  mov     qword ptr [rbp+98h], 0
0x14002c49d  mov     dl, al; NewIrql
0x14002c49f  call    cs:__imp_KeReleaseSpinLock
0x14002c4a6  nop     dword ptr [rax+rax+00h]
0x14002c4ab  xor     edx, edx; PriorityBoost
0x14002c4ad  mov     rcx, rsi; Irp
0x14002c4b0  call    cs:__imp_IofCompleteRequest
0x14002c4b7  nop     dword ptr [rax+rax+00h]
0x14002c4bc  mov     cl, dil; NewIrql
0x14002c4bf  call    cs:__imp_KeLowerIrql
0x14002c4c6  nop     dword ptr [rax+rax+00h]
0x14002c4cb  mov     al, 1
0x14002c4cd  jmp     short loc_14002C4E0
0x14002c4cf  mov     cl, [rsi+45h]; Irql
0x14002c4d2  call    cs:__imp_IoReleaseCancelSpinLock
0x14002c4d9  nop     dword ptr [rax+rax+00h]
0x14002c4de  xor     al, al
0x14002c4e0  add     rsp, 38h
0x14002c4e4  pop     rdi
0x14002c4e5  pop     rsi
0x14002c4e6  pop     rbp
0x14002c4e7  pop     rbx
0x14002c4e8  retn
```
