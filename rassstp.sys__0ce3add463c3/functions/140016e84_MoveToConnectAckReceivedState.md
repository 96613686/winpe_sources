# MoveToConnectAckReceivedState

- ea: `0x140016e84`
- end: `0x140016f45`
- name: `MoveToConnectAckReceivedState`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140017550`

## callees

- `0x140002f88`
- `0x140005a9c`
- `0x140005ef0`
- `0x140016e84`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016f2d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140016f2d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016f04`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140016f04`

## pseudocode

```c
void __fastcall MoveToConnectAckReceivedState(__int64 a1)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
  }
  *(_DWORD *)(a1 + 24) = 3;
  SstpTimerReschedule(a1 + 48, (_DWORD)off_14000A038, a1, 1, dword_14000A030, 0);
  *(_BYTE *)(a1 + 325) = 0;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 16));
  (*((void (__fastcall **)(_QWORD, _QWORD))SstpFsmGlobalInfo + 12))(*(_QWORD *)(a1 + 136), 0);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 16));
}

```

## disassembly

```asm
0x140016e84  mov     [rsp+arg_0], rbx
0x140016e89  push    rdi
0x140016e8a  sub     rsp, 30h
0x140016e8e  mov     rdi, rcx
0x140016e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e98  lea     rax, WPP_GLOBAL_Control
0x140016e9f  cmp     rcx, rax
0x140016ea2  jz      short loc_140016ECD
0x140016ea4  mov     eax, [rcx+2Ch]
0x140016ea7  test    al, 4
0x140016ea9  jz      short loc_140016ECD
0x140016eab  cmp     byte ptr [rcx+29h], 3
0x140016eaf  jb      short loc_140016ECD
0x140016eb1  mov     rcx, [rcx+18h]
0x140016eb5  lea     r9, [rdi+16Ch]
0x140016ebc  mov     edx, 45h ; 'E'
0x140016ec1  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016ec8  call    WPP_SF__guid_
0x140016ecd  mov     dword ptr [rdi+18h], 3
0x140016ed4  lea     rcx, [rdi+30h]
0x140016ed8  mov     eax, cs:dword_14000A030
0x140016ede  mov     r9b, 1
0x140016ee1  mov     rdx, cs:off_14000A038
0x140016ee8  mov     r8, rdi
0x140016eeb  mov     [rsp+38h+var_10], 0
0x140016ef0  mov     [rsp+38h+var_18], eax
0x140016ef4  call    SstpTimerReschedule
0x140016ef9  lea     rcx, [rdi+10h]; SpinLock
0x140016efd  mov     byte ptr [rdi+145h], 0
0x140016f04  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140016f0b  nop     dword ptr [rax+rax+00h]
0x140016f10  mov     rax, cs:SstpFsmGlobalInfo
0x140016f17  xor     edx, edx
0x140016f19  mov     rcx, [rdi+88h]
0x140016f20  mov     rax, [rax+60h]
0x140016f24  call    _guard_dispatch_icall
0x140016f29  lea     rcx, [rdi+10h]; SpinLock
0x140016f2d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140016f34  nop     dword ptr [rax+rax+00h]
0x140016f39  mov     rbx, [rsp+38h+arg_0]
0x140016f3e  add     rsp, 30h
0x140016f42  pop     rdi
0x140016f43  retn
```
