# PxClDeleteVc

- ea: `0x14000f630`
- end: `0x14000f745`
- name: `PxClDeleteVc`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140001b54`
- `0x140001b84`
- `0x140001bc8`
- `0x140006e08`
- `0x140007254`
- `0x14000f630`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f6c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f6c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f6fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f6fc`

## pseudocode

```c
__int64 __fastcall PxClDeleteVc(unsigned __int64 a1)
{
  _DWORD *v2; // rbx
  bool v4; // zf
  PVOID Entry; // [rsp+38h] [rbp+10h] BYREF

  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids);
  GetVcFromCtx(a1, &Entry);
  v2 = Entry;
  if ( Entry )
  {
    *((_BYTE *)v2 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
    RemoveVcFromClAfList(v2);
    v4 = v2[7] == 2;
    v2[7] -= 2;
    if ( v4 )
      DoDerefVcWork(v2);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v2 + 64, *((_BYTE *)v2 + 520));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids, 0);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned int)((_DWORD)Entry + 16),
        WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids,
        a1);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x14000f630  mov     [rsp+arg_0], rbx
0x14000f635  mov     [rsp+arg_10], rsi
0x14000f63a  push    rdi
0x14000f63b  sub     rsp, 20h
0x14000f63f  mov     rdi, rcx
0x14000f642  mov     [rsp+28h+Entry], 0
0x14000f64b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f652  lea     rsi, WPP_GLOBAL_Control
0x14000f659  cmp     rcx, rsi
0x14000f65c  jz      short loc_14000F679
0x14000f65e  cmp     byte ptr [rcx+29h], 5
0x14000f662  jb      short loc_14000F679
0x14000f664  mov     rcx, [rcx+18h]
0x14000f668  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f66f  mov     edx, 0Fh
0x14000f674  call    WPP_SF_
0x14000f679  lea     rdx, [rsp+28h+Entry]
0x14000f67e  mov     rcx, rdi
0x14000f681  call    GetVcFromCtx
0x14000f686  mov     rbx, [rsp+28h+Entry]
0x14000f68b  test    rbx, rbx
0x14000f68e  jnz     short loc_14000F6BF
0x14000f690  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f697  cmp     rcx, rsi
0x14000f69a  jz      short loc_14000F6B8
0x14000f69c  cmp     byte ptr [rcx+29h], 3
0x14000f6a0  jb      short loc_14000F6B8
0x14000f6a2  mov     rcx, [rcx+18h]
0x14000f6a6  lea     edx, [rbx+10h]
0x14000f6a9  mov     r9, rdi
0x14000f6ac  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f6b3  call    WPP_SF_q
0x14000f6b8  mov     eax, 0C0000001h
0x14000f6bd  jmp     short loc_14000F734
0x14000f6bf  lea     rdi, [rbx+200h]
0x14000f6c6  mov     rcx, rdi; SpinLock
0x14000f6c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f6d0  nop     dword ptr [rax+rax+00h]
0x14000f6d5  mov     rcx, rbx
0x14000f6d8  mov     [rbx+208h], al
0x14000f6de  call    RemoveVcFromClAfList
0x14000f6e3  add     dword ptr [rbx+1Ch], 0FFFFFFFEh
0x14000f6e7  jnz     short loc_14000F6F3
0x14000f6e9  mov     rcx, rbx; Entry
0x14000f6ec  call    DoDerefVcWork
0x14000f6f1  jmp     short loc_14000F708
0x14000f6f3  mov     dl, [rbx+208h]; NewIrql
0x14000f6f9  mov     rcx, rdi; SpinLock
0x14000f6fc  call    cs:__imp_KeReleaseSpinLock
0x14000f703  nop     dword ptr [rax+rax+00h]
0x14000f708  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f70f  cmp     rcx, rsi
0x14000f712  jz      short loc_14000F732
0x14000f714  cmp     byte ptr [rcx+29h], 5
0x14000f718  jb      short loc_14000F732
0x14000f71a  mov     rcx, [rcx+18h]
0x14000f71e  lea     r8, WPP_1813aecb678d3d45053dbb1f2dab7046_Traceguids
0x14000f725  mov     edx, 11h
0x14000f72a  xor     r9d, r9d
0x14000f72d  call    WPP_SF_d
0x14000f732  xor     eax, eax
0x14000f734  mov     rbx, [rsp+28h+arg_0]
0x14000f739  mov     rsi, [rsp+28h+arg_10]
0x14000f73e  add     rsp, 20h
0x14000f742  pop     rdi
0x14000f743  retn
```
