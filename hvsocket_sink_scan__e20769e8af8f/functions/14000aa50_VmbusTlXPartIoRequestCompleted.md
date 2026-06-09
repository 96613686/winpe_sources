# VmbusTlXPartIoRequestCompleted

- ea: `0x14000aa50`
- end: `0x14000ab1a`
- name: `VmbusTlXPartIoRequestCompleted`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004898`
- `0x140007794`
- `0x140009a94`
- `0x14000a7c0`
- `0x14000aa50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aadc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aadc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aaf8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aaf8`

## string_xrefs

- `0x14000aabc`: `VmbusTlXPartIoRequestCompleted`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartIoRequestCompleted(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  __int64 v5; // rsi
  int v6; // eax
  KIRQL v7; // bl

  v3 = *(_DWORD *)(a2 + 48);
  v5 = *(_QWORD *)(a3 + 128);
  if ( v3 == -1073741647 || v3 == -1073741536 )
    *(_DWORD *)(a2 + 48) = -1073741247;
  if ( *(_DWORD *)(a3 + 120) == 1 )
    *(_QWORD *)(a3 + 200) = *(_QWORD *)(a2 + 56);
  VmbusTlConnectIoRequestCompleted((char *)v5, (char *)a3);
  v6 = VmbusTlXPartClosePipeForGracefulShutdown(v5);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointIoRequestError(
        (unsigned int)"VmbusTlXPartIoRequestCompleted",
        856,
        v6,
        v5,
        *(_QWORD *)(a3 + 240));
    v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 72));
    VmbusTlDisconnectAbort(v5);
    KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 72), v7);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000aa50  mov     [rsp+arg_0], rbx
0x14000aa55  mov     [rsp+arg_8], rsi
0x14000aa5a  push    rdi
0x14000aa5b  sub     rsp, 30h
0x14000aa5f  mov     eax, [rdx+30h]
0x14000aa62  mov     rbx, r8
0x14000aa65  mov     rsi, [r8+80h]
0x14000aa6c  cmp     eax, 0C00000B1h
0x14000aa71  jz      short loc_14000AA7A
0x14000aa73  cmp     eax, 0C0000120h
0x14000aa78  jnz     short loc_14000AA81
0x14000aa7a  mov     dword ptr [rdx+30h], 0C0000241h
0x14000aa81  cmp     dword ptr [r8+78h], 1
0x14000aa86  jnz     short loc_14000AA93
0x14000aa88  mov     rax, [rdx+38h]
0x14000aa8c  mov     [r8+0C8h], rax
0x14000aa93  mov     rdx, rbx; PVOID
0x14000aa96  mov     rcx, rsi; P
0x14000aa99  call    VmbusTlConnectIoRequestCompleted
0x14000aa9e  mov     rcx, rsi
0x14000aaa1  call    VmbusTlXPartClosePipeForGracefulShutdown
0x14000aaa6  test    eax, eax
0x14000aaa8  jns     short loc_14000AB04
0x14000aaaa  mov     ecx, cs:dword_140013058
0x14000aab0  cmp     ecx, 2
0x14000aab3  jbe     short loc_14000AAD8
0x14000aab5  mov     rdx, [rbx+0F0h]
0x14000aabc  lea     rcx, aVmbustlxpartio; "VmbusTlXPartIoRequestCompleted"
0x14000aac3  mov     [rsp+38h+var_18], rdx
0x14000aac8  mov     r9, rsi
0x14000aacb  mov     edx, 358h
0x14000aad0  mov     r8d, eax
0x14000aad3  call    HvsocketTraceEndpointIoRequestError
0x14000aad8  lea     rcx, [rsi+48h]; SpinLock
0x14000aadc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000aae3  nop     dword ptr [rax+rax+00h]
0x14000aae8  mov     rcx, rsi
0x14000aaeb  mov     bl, al
0x14000aaed  call    VmbusTlDisconnectAbort
0x14000aaf2  mov     dl, bl; NewIrql
0x14000aaf4  lea     rcx, [rsi+48h]; SpinLock
0x14000aaf8  call    cs:__imp_KeReleaseSpinLock
0x14000aaff  nop     dword ptr [rax+rax+00h]
0x14000ab04  mov     rbx, [rsp+38h+arg_0]
0x14000ab09  mov     eax, 0C0000016h
0x14000ab0e  mov     rsi, [rsp+38h+arg_8]
0x14000ab13  add     rsp, 30h
0x14000ab17  pop     rdi
0x14000ab18  retn
```
