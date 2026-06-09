# NbtFindAndReferenceDevice

- ea: `0x1400061ac`
- end: `0x1400062a8`
- name: `NbtFindAndReferenceDevice`
- size: `252`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027200`
- `0x14002e8c0`
- `0x1400471c0`
- `0x140047630`
- `0x140047a84`

## callees

- `0x1400061ac`
- `0x140006900`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140006241`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140006241`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400061c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006258`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400061c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006258`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006219`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006289`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006219`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006289`

## pseudocode

```c
__int64 *__fastcall NbtFindAndReferenceDevice(PCUNICODE_STRING String1, char a2)
{
  KIRQL v4; // al
  __int64 *v5; // rdi
  KIRQL v6; // si
  __int64 *v7; // rbx
  KIRQL v8; // al

  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v5 = (__int64 *)NbtConfig;
  v6 = v4;
  while ( 1 )
  {
    if ( v5 == &NbtConfig )
    {
      KeReleaseSpinLock(&SpinLock, v6);
      return 0;
    }
    v7 = v5 - 43;
    if ( v5 != (__int64 *)344 && *((_DWORD *)v7 + 90) == 1131832644 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v7 + 91);
      ++*((_DWORD *)v7 + 277);
    }
    KeReleaseSpinLock(&SpinLock, v6);
    if ( !RtlCompareUnicodeString(
            String1,
            (PCUNICODE_STRING)((char *)v7 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 472),
            1u) )
      break;
    v8 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v5 = (__int64 *)*v5;
    v6 = v8;
    NBT_DEREFERENCE_DEVICE(v7, 6);
  }
  return v5 - 43;
}

```

## disassembly

```asm
0x1400061ac  push    rbx
0x1400061ae  push    rbp
0x1400061af  push    rsi
0x1400061b0  push    rdi
0x1400061b1  push    r14
0x1400061b3  sub     rsp, 20h
0x1400061b7  mov     r14, rcx
0x1400061ba  mov     bpl, dl
0x1400061bd  lea     rcx, SpinLock; SpinLock
0x1400061c4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400061cb  nop     dword ptr [rax+rax+00h]
0x1400061d0  mov     rdi, cs:NbtConfig
0x1400061d7  mov     sil, al
0x1400061da  lea     rax, NbtConfig
0x1400061e1  cmp     rdi, rax
0x1400061e4  jz      loc_14000627F
0x1400061ea  lea     rbx, [rdi-158h]
0x1400061f1  test    rbx, rbx
0x1400061f4  jz      short loc_14000620F
0x1400061f6  cmp     dword ptr [rbx+168h], 43766544h
0x140006200  jnz     short loc_14000620F
0x140006202  lock inc dword ptr [rbx+16Ch]
0x140006209  inc     dword ptr [rbx+454h]
0x14000620f  mov     dl, sil; NewIrql
0x140006212  lea     rcx, SpinLock; SpinLock
0x140006219  call    cs:__imp_KeReleaseSpinLock
0x140006220  nop     dword ptr [rax+rax+00h]
0x140006225  mov     al, bpl
0x140006228  mov     r8b, 1; CaseInSensitive
0x14000622b  neg     al
0x14000622d  mov     rcx, r14; String1
0x140006230  sbb     rdx, rdx
0x140006233  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140006237  add     rdx, 1D8h
0x14000623e  add     rdx, rbx; String2
0x140006241  call    cs:__imp_RtlCompareUnicodeString
0x140006248  nop     dword ptr [rax+rax+00h]
0x14000624d  test    eax, eax
0x14000624f  jz      short loc_1400062A3
0x140006251  lea     rcx, SpinLock; SpinLock
0x140006258  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000625f  nop     dword ptr [rax+rax+00h]
0x140006264  mov     rdi, [rdi]
0x140006267  mov     r8b, 1
0x14000626a  mov     edx, 6
0x14000626f  mov     rcx, rbx
0x140006272  mov     sil, al
0x140006275  call    NBT_DEREFERENCE_DEVICE
0x14000627a  jmp     loc_1400061DA
0x14000627f  mov     dl, sil; NewIrql
0x140006282  lea     rcx, SpinLock; SpinLock
0x140006289  call    cs:__imp_KeReleaseSpinLock
0x140006290  nop     dword ptr [rax+rax+00h]
0x140006295  xor     eax, eax
0x140006297  add     rsp, 20h
0x14000629b  pop     r14
0x14000629d  pop     rdi
0x14000629e  pop     rsi
0x14000629f  pop     rbp
0x1400062a0  pop     rbx
0x1400062a1  retn
0x1400062a3  mov     rax, rbx
0x1400062a6  jmp     short loc_140006297
```
