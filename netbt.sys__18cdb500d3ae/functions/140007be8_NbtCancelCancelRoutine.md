# NbtCancelCancelRoutine

- ea: `0x140007be8`
- end: `0x140007c46`
- name: `NbtCancelCancelRoutine`
- size: `94`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140007a08`
- `0x140007b3c`
- `0x1400104d8`
- `0x14001a900`
- `0x14001ba80`
- `0x14002410c`
- `0x1400297c0`
- `0x14002c5e0`
- `0x14003005c`
- `0x14005006c`
- `0x140052100`

## callees

- `0x140007be8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007c27`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007c27`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140007c05`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140007c05`

## pseudocode

```c
__int64 __fastcall NbtCancelCancelRoutine(__int64 a1)
{
  unsigned int v1; // esi
  int v3; // esi

  v1 = 0;
  if ( a1 )
  {
    IoAcquireCancelSpinLock((PKIRQL)(a1 + 69));
    v3 = -(*(_BYTE *)(a1 + 68) != 0);
    _InterlockedExchange64((volatile __int64 *)(a1 + 104), 0);
    v1 = v3 & 0xC0000120;
    IoReleaseCancelSpinLock(*(_BYTE *)(a1 + 69));
  }
  return v1;
}

```

## disassembly

```asm
0x140007be8  mov     [rsp+arg_0], rbx
0x140007bed  mov     [rsp+arg_8], rsi
0x140007bf2  push    rdi
0x140007bf3  sub     rsp, 20h
0x140007bf7  xor     esi, esi
0x140007bf9  mov     rdi, rcx
0x140007bfc  test    rcx, rcx
0x140007bff  jz      short loc_140007C33
0x140007c01  add     rcx, 45h ; 'E'; Irql
0x140007c05  call    cs:__imp_IoAcquireCancelSpinLock
0x140007c0c  nop     dword ptr [rax+rax+00h]
0x140007c11  mov     al, [rdi+44h]
0x140007c14  neg     al
0x140007c16  sbb     esi, esi
0x140007c18  xor     edx, edx
0x140007c1a  xchg    rdx, [rdi+68h]
0x140007c1e  mov     cl, [rdi+45h]; Irql
0x140007c21  and     esi, 0C0000120h
0x140007c27  call    cs:__imp_IoReleaseCancelSpinLock
0x140007c2e  nop     dword ptr [rax+rax+00h]
0x140007c33  mov     rbx, [rsp+28h+arg_0]
0x140007c38  mov     eax, esi
0x140007c3a  mov     rsi, [rsp+28h+arg_8]
0x140007c3f  add     rsp, 20h
0x140007c43  pop     rdi
0x140007c44  retn
```
