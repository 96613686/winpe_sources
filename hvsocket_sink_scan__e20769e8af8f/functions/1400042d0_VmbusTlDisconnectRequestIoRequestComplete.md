# VmbusTlDisconnectRequestIoRequestComplete

- ea: `0x1400042d0`
- end: `0x14000434b`
- name: `VmbusTlDisconnectRequestIoRequestComplete`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400042d0`
- `0x140004898`
- `0x1400049a0`
- `0x14000975c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400042e2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400042e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004335`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004335`

## string_xrefs

- `0x140004312`: `VmbusTlDisconnectRequestIoRequestComplete`

## pseudocode

```c
void __fastcall VmbusTlDisconnectRequestIoRequestComplete(__int64 a1, int a2)
{
  KIRQL v4; // bp

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  if ( a2 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError("VmbusTlDisconnectRequestIoRequestComplete", 420, (unsigned int)a2, a1);
    VmbusTlDisconnectAbort(a1);
  }
  else
  {
    VmbusTlTransitionDisconnectState(a1, 2);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v4);
}

```

## disassembly

```asm
0x1400042d0  push    rbx
0x1400042d2  push    rbp
0x1400042d3  push    rsi
0x1400042d4  push    rdi
0x1400042d5  sub     rsp, 28h
0x1400042d9  mov     rbx, rcx
0x1400042dc  mov     esi, edx
0x1400042de  add     rcx, 48h ; 'H'; SpinLock
0x1400042e2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400042e9  nop     dword ptr [rax+rax+00h]
0x1400042ee  mov     bpl, al
0x1400042f1  test    esi, esi
0x1400042f3  js      short loc_140004304
0x1400042f5  mov     edx, 2
0x1400042fa  mov     rcx, rbx
0x1400042fd  call    VmbusTlTransitionDisconnectState
0x140004302  jmp     short loc_14000432E
0x140004304  mov     eax, cs:dword_140013058
0x14000430a  cmp     eax, 2
0x14000430d  jbe     short loc_140004326
0x14000430f  mov     r9, rbx
0x140004312  lea     rcx, aVmbustldisconn_0; "VmbusTlDisconnectRequestIoRequestComple"...
0x140004319  mov     r8d, esi
0x14000431c  mov     edx, 1A4h
0x140004321  call    HvsocketTraceEndpointError
0x140004326  mov     rcx, rbx
0x140004329  call    VmbusTlDisconnectAbort
0x14000432e  mov     dl, bpl; NewIrql
0x140004331  lea     rcx, [rbx+48h]; SpinLock
0x140004335  call    cs:__imp_KeReleaseSpinLock
0x14000433c  nop     dword ptr [rax+rax+00h]
0x140004341  add     rsp, 28h
0x140004345  pop     rdi
0x140004346  pop     rsi
0x140004347  pop     rbp
0x140004348  pop     rbx
0x140004349  retn
```
