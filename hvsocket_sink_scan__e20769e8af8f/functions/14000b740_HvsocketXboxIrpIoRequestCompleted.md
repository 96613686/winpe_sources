# HvsocketXboxIrpIoRequestCompleted

- ea: `0x14000b740`
- end: `0x14000b818`
- name: `HvsocketXboxIrpIoRequestCompleted`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004898`
- `0x140007794`
- `0x140009a94`
- `0x14000b520`
- `0x14000b740`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b7da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b7da`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b7f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b7f6`

## string_xrefs

- `0x14000b7ba`: `HvsocketXboxIrpIoRequestCompleted`

## pseudocode

```c
__int64 __fastcall HvsocketXboxIrpIoRequestCompleted(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  __int64 v5; // rsi
  int v6; // eax
  KIRQL v7; // bl

  v3 = *(_DWORD *)(a2 + 48);
  v5 = *(_QWORD *)(a3 + 128);
  if ( v3 == -1073741647 || v3 == -1073741493 || v3 == -1073741722 || v3 == -1073741536 )
    *(_DWORD *)(a2 + 48) = -1073741247;
  if ( *(_DWORD *)(a3 + 120) == 1 )
    *(_QWORD *)(a3 + 200) = *(_QWORD *)(a2 + 56);
  VmbusTlConnectIoRequestCompleted((char *)v5, (char *)a3);
  v6 = HvsocketXboxClosePipeForGracefulShutdown(v5);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointIoRequestError(
        (unsigned int)"HvsocketXboxIrpIoRequestCompleted",
        761,
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
0x14000b740  mov     [rsp+arg_0], rbx
0x14000b745  mov     [rsp+arg_8], rsi
0x14000b74a  push    rdi
0x14000b74b  sub     rsp, 30h
0x14000b74f  mov     eax, [rdx+30h]
0x14000b752  mov     rbx, r8
0x14000b755  mov     rsi, [r8+80h]
0x14000b75c  cmp     eax, 0C00000B1h
0x14000b761  jz      short loc_14000B778
0x14000b763  cmp     eax, 0C000014Bh
0x14000b768  jz      short loc_14000B778
0x14000b76a  cmp     eax, 0C0000066h
0x14000b76f  jz      short loc_14000B778
0x14000b771  cmp     eax, 0C0000120h
0x14000b776  jnz     short loc_14000B77F
0x14000b778  mov     dword ptr [rdx+30h], 0C0000241h
0x14000b77f  cmp     dword ptr [r8+78h], 1
0x14000b784  jnz     short loc_14000B791
0x14000b786  mov     rax, [rdx+38h]
0x14000b78a  mov     [r8+0C8h], rax
0x14000b791  mov     rdx, rbx; PVOID
0x14000b794  mov     rcx, rsi; P
0x14000b797  call    VmbusTlConnectIoRequestCompleted
0x14000b79c  mov     rcx, rsi
0x14000b79f  call    HvsocketXboxClosePipeForGracefulShutdown
0x14000b7a4  test    eax, eax
0x14000b7a6  jns     short loc_14000B802
0x14000b7a8  mov     ecx, cs:dword_140013058
0x14000b7ae  cmp     ecx, 2
0x14000b7b1  jbe     short loc_14000B7D6
0x14000b7b3  mov     rdx, [rbx+0F0h]
0x14000b7ba  lea     rcx, aHvsocketxboxir; "HvsocketXboxIrpIoRequestCompleted"
0x14000b7c1  mov     [rsp+38h+var_18], rdx
0x14000b7c6  mov     r9, rsi
0x14000b7c9  mov     edx, 2F9h
0x14000b7ce  mov     r8d, eax
0x14000b7d1  call    HvsocketTraceEndpointIoRequestError
0x14000b7d6  lea     rcx, [rsi+48h]; SpinLock
0x14000b7da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b7e1  nop     dword ptr [rax+rax+00h]
0x14000b7e6  mov     rcx, rsi
0x14000b7e9  mov     bl, al
0x14000b7eb  call    VmbusTlDisconnectAbort
0x14000b7f0  mov     dl, bl; NewIrql
0x14000b7f2  lea     rcx, [rsi+48h]; SpinLock
0x14000b7f6  call    cs:__imp_KeReleaseSpinLock
0x14000b7fd  nop     dword ptr [rax+rax+00h]
0x14000b802  mov     rbx, [rsp+38h+arg_0]
0x14000b807  mov     eax, 0C0000016h
0x14000b80c  mov     rsi, [rsp+38h+arg_8]
0x14000b811  add     rsp, 30h
0x14000b815  pop     rdi
0x14000b816  retn
```
