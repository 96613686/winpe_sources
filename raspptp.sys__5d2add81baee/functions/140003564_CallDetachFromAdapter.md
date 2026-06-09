# CallDetachFromAdapter

- ea: `0x140003564`
- end: `0x140003605`
- name: `CallDetachFromAdapter`
- size: `161`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e78`
- `0x140005bf0`
- `0x14000f588`
- `0x14000fbac`
- `0x140011050`

## callees

- `0x140003564`
- `0x140003e38`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400035e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400035e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400035b5`

## pseudocode

```c
void __fastcall CallDetachFromAdapter(__int64 a1)
{
  __int64 v2; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x22u,
      (__int64)WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
      *(_DWORD *)(a1 + 200));
  }
  v2 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(v2 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 8));
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 32LL) + 8LL * *(_QWORD *)(a1 + 200)) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(a1 + 56) + 8LL), *(_BYTE *)(*(_QWORD *)(a1 + 56) + 16LL));
  *(_BYTE *)(a1 + 193) = 0;
}

```

## disassembly

```asm
0x140003564  mov     [rsp+arg_0], rbx
0x140003569  push    rdi
0x14000356a  sub     rsp, 20h
0x14000356e  mov     rdi, rcx
0x140003571  mov     rcx, cs:WPP_GLOBAL_Control
0x140003578  lea     rax, WPP_GLOBAL_Control
0x14000357f  cmp     rcx, rax
0x140003582  jz      short loc_1400035AD
0x140003584  mov     eax, [rcx+2Ch]
0x140003587  test    al, 10h
0x140003589  jz      short loc_1400035AD
0x14000358b  cmp     byte ptr [rcx+29h], 2
0x14000358f  jb      short loc_1400035AD
0x140003591  mov     r9d, [rdi+0C8h]
0x140003598  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14000359f  mov     rcx, [rcx+18h]
0x1400035a3  mov     edx, 22h ; '"'
0x1400035a8  call    WPP_SF_d
0x1400035ad  mov     rbx, [rdi+38h]
0x1400035b1  lea     rcx, [rbx+8]; SpinLock
0x1400035b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400035bc  nop     dword ptr [rax+rax+00h]
0x1400035c1  mov     [rbx+10h], al
0x1400035c4  mov     rax, [rdi+38h]
0x1400035c8  mov     rdx, [rdi+0C8h]
0x1400035cf  mov     rcx, [rax+20h]
0x1400035d3  mov     qword ptr [rcx+rdx*8], 0
0x1400035db  mov     rdx, [rdi+38h]
0x1400035df  lea     rcx, [rdx+8]; SpinLock
0x1400035e3  mov     dl, [rdx+10h]; NewIrql
0x1400035e6  call    cs:__imp_KeReleaseSpinLock
0x1400035ed  nop     dword ptr [rax+rax+00h]
0x1400035f2  mov     rbx, [rsp+28h+arg_0]
0x1400035f7  mov     byte ptr [rdi+0C1h], 0
0x1400035fe  add     rsp, 20h
0x140003602  pop     rdi
0x140003603  retn
```
